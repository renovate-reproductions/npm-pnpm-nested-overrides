# npm-pnpm-nested-overrides

Reproduce nested pnpm overrides

## expected behavior

Upgrade `cookie` to `v0.7.2`.
https://github.com/renovate-reproductions/npm-pnpm-nested-overrides/blob/main/package.json#L4

# actual behavior

Dependency is marked as `invalid-name`.

```
Welcome to Node.js v20.17.0.
Type ".help" for more information.
> const v = require('validate-npm-package-name')
undefined
> v("express>cookie")
{
  validForNewPackages: false,
  validForOldPackages: false,
  errors: [ 'name can only contain URL-friendly characters' ]
}
```

https://github.com/renovatebot/renovate/blob/1562b303449c68e6529ad66a6924db5bf8a36e2a/lib/modules/manager/npm/extract/common/dependency.ts#L35-L38
