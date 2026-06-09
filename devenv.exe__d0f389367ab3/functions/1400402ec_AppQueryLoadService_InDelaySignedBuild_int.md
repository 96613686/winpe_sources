# AppQueryLoadService::InDelaySignedBuild(int *)

- ea: `0x1400402ec`
- end: `0x1400404ec`
- name: `?InDelaySignedBuild@AppQueryLoadService@@AEAAJPEAH@Z`
- size: `512`
- prototype: `__int64 __fastcall(AppQueryLoadService *__hidden this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x140040114`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140002f00`
- `0x140033ab0`
- `0x1400402ec`
- `0x1400408ac`
- `0x140040a0c`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x140040454`
- `KERNEL32!GetFileAttributesW` at `0x140040454`
- `KERNEL32!GetModuleFileNameW` at `0x1400403dd`
- `KERNEL32!GetModuleFileNameW` at `0x1400403dd`
- `KERNEL32!GetModuleHandleW` at `0x14004038b`
- `KERNEL32!GetModuleHandleW` at `0x14004038b`
- `KERNEL32!GetLastError` at `0x140040396`
- `KERNEL32!GetLastError` at `0x140040396`
- `VCRUNTIME140!wcsrchr` at `0x140040416`
- `VCRUNTIME140!wcsrchr` at `0x140040416`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140040337`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140040352`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140040337`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140040352`
- `MSVCP140!_Mtx_lock` at `0x14004032a`
- `MSVCP140!_Mtx_lock` at `0x14004032a`
- `MSVCP140!_Mtx_unlock` at `0x1400404b2`
- `MSVCP140!_Mtx_unlock` at `0x1400404b2`
- `mscoree!StrongNameSignatureVerificationEx` at `0x140040469`
- `mscoree!StrongNameSignatureVerificationEx` at `0x140040469`

## pseudocode

```c

```
