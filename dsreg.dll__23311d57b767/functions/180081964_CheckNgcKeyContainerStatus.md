# CheckNgcKeyContainerStatus

- ea: `0x180081964`
- end: `0x180081b6d`
- name: `CheckNgcKeyContainerStatus`
- size: `521`
- prototype: `__int64 __fastcall(NgcStatusStorage *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800834f4`

## callees

- `0x180002748`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x18001288c`
- `0x180012eb8`
- `0x18001c02c`
- `0x1800204f0`
- `0x180042684`
- `0x180042b10`
- `0x180044300`
- `0x180081964`
- `0x180094d24`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081b46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081b46`
- `cryptngc!NgcGetUserIdKeyContainerStatus` at `0x1800819db`
- `cryptngc!NgcGetUserIdKeyContainerStatus` at `0x1800819db`

## string_xrefs

- `0x1800819b1`: `GetCurrentUserSid`
- `0x180081b15`: `NgcStatusStorage::Delete`
- `0x180081a06`: `%s: Cannot get NGC user ID key container status. SID: %s, UserKeyName: %s, Error code: 0x%08x.`

## pseudocode

```c

```
