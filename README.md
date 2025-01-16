# #33650

ℹ️ Created using

```bash
 ❯ uvx copier --version
copier 9.4.1
```

## Current behavior

Fails to create a PR:

```
DEBUG: Matched 1 file(s) for manager copier: instance/.copier-answers.yml
DEBUG: Parsing Copier answers YAML failed
{
  "err": {
    "message": "Schema error",
    "stack": "ZodError: Schema error\n    at Object.get error [as error] (/usr/local/renovate/node_modules/.pnpm/zod@3.24.1/node_modules/zod/lib/types.js:55:31)\n    at ZodPipeline.parse (/usr/local/renovate/node_modules/.pnpm/zod@3.24.1/node_modules/zod/lib/types.js:131:22)\n    at Object.extractPackageFile (/usr/local/renovate/lib/modules/manager/copier/extract.ts:12:32)\n    at extractPackageFile (/usr/local/renovate/lib/modules/manager/index.ts:75:9)\n    at getManagerPackageFiles (/usr/local/renovate/lib/workers/repository/extract/manager-files.ts:58:43)\n    at /usr/local/renovate/lib/workers/repository/extract/index.ts:57:28\n    at async Promise.all (index 0)\n    at extractAllDependencies (/usr/local/renovate/lib/workers/repository/extract/index.ts:54:26)\n    at extract (/usr/local/renovate/lib/workers/repository/process/extract-update.ts:160:28)\n    at extractDependencies (/usr/local/renovate/lib/workers/repository/process/index.ts:158:26)\n    at Object.renovateRepository (/usr/local/renovate/lib/workers/repository/index.ts:71:9)\n    at attributes.repository (/usr/local/renovate/lib/workers/global/index.ts:206:11)\n    at start (/usr/local/renovate/lib/workers/global/index.ts:191:7)\n    at /usr/local/renovate/lib/renovate.ts:19:22",
    "issues": {
      "_src_path": "Invalid url"
    }
  }
  "packageFile": "instance/.copier-answers.yml"
}
```
➡️ Job ID `0194704b-ff57-7299-b266-273a6da41c4e`

## Expected behavior

Creates a PR that correctly updates the instance to template v1.1.0.

➡️ [reitzig/reproduction-renovate-33650#1](https://github.com/reitzig/reproduction-renovate-33650/pull/1)  
Created manually with

```bash
uvx copier update instance
```

## Link to the Renovate issue or Discussion

➡️ [renovatebot/renovate#33650](https://github.com/renovatebot/renovate/discussions/33650)
