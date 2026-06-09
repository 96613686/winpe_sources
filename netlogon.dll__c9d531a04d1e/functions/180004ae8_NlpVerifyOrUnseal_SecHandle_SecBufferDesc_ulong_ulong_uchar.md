# NlpVerifyOrUnseal(_SecHandle *,_SecBufferDesc *,ulong,ulong *,uchar)

- ea: `0x180004ae8`
- end: `0x1800052cd`
- name: `?NlpVerifyOrUnseal@@YAJPEAU_SecHandle@@PEAU_SecBufferDesc@@KPEAKE@Z`
- size: `2021`
- prototype: `__int64 __fastcall(struct _SecHandle *, struct _SecBufferDesc *, unsigned int, unsigned int *, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x180052070`
- `0x1800530f0`

## callees

- `0x180004ae8`
- `0x180007278`
- `0x18000d710`
- `0x18000e270`
- `0x18003f054`
- `0x18003f16c`
- `0x180051790`
- `0x18008a010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180004b8a`
- `ntdll!RtlLeaveCriticalSection` at `0x180004b8a`
- `ntdll!RtlEnterCriticalSection` at `0x180004b59`
- `ntdll!RtlEnterCriticalSection` at `0x180004b59`
- `cryptdll!CDLocateCheckSum` at `0x180004fce`
- `cryptdll!CDLocateCheckSum` at `0x180004fce`
- `cryptdll!CDLocateCSystem` at `0x180004d43`
- `cryptdll!CDLocateCSystem` at `0x180004d43`

## string_xrefs

- `0x180004ffd`: `onecore\ds\netapi\svcdlls\logonsrv\server\secpkg.cxx`
- `0x18000516f`: `onecore\ds\netapi\svcdlls\logonsrv\server\secpkg.cxx`
- `0x180005229`: `onecore\ds\netapi\svcdlls\logonsrv\server\secpkg.cxx`
- `0x180005004`: `Check->CheckSumSize <= sizeof(LocalChecksum)`

## pseudocode

```c

```
