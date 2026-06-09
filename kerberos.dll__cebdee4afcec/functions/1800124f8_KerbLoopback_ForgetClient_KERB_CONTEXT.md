# KerbLoopback::ForgetClient(_KERB_CONTEXT *)

- ea: `0x1800124f8`
- end: `0x18001262f`
- name: `?ForgetClient@KerbLoopback@@YAJPEAU_KERB_CONTEXT@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(KerbLoopback *__hidden this, struct _KERB_CONTEXT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006680`
- `0x180006ddc`

## callees

- `0x1800124f8`
- `0x180012640`
- `0x180070a50`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012525`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012525`
- `ntdll!RtlAvlRemoveNode` at `0x1800125b8`
- `ntdll!RtlAvlRemoveNode` at `0x1800125b8`
- `ntdll!RtlEnterCriticalSection` at `0x180012511`
- `ntdll!RtlEnterCriticalSection` at `0x180012511`
- `ntdll!RtlLeaveCriticalSection` at `0x18001257e`
- `ntdll!RtlLeaveCriticalSection` at `0x180012622`
- `ntdll!RtlLeaveCriticalSection` at `0x18001257e`
- `ntdll!RtlLeaveCriticalSection` at `0x180012622`

## pseudocode

```c

```
