# ConstrainedImpersonateLoggedOnUser::DuplicateImpersonationToken(void * *)

- ea: `0x18005df38`
- end: `0x18005dff2`
- name: `?DuplicateImpersonationToken@ConstrainedImpersonateLoggedOnUser@@QEAAJPEAPEAX@Z`
- size: `186`
- prototype: `int(ConstrainedImpersonateLoggedOnUser *__hidden this, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18005d084`
- `0x18005f3cc`

## callees

- `0x1800076b4`
- `0x1800076d4`
- `0x18005df38`
- `0x18005e0fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005df89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005df96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005df89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005df96`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005dfc0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005dfc0`

## string_xrefs

- `0x18005df64`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`
- `0x18005dfcf`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`

## pseudocode

```c

```
