# RemoveMasterKeyCache(_LUID *,ushort const *)

- ea: `0x1800114b4`
- end: `0x1800115fb`
- name: `?RemoveMasterKeyCache@@YAHPEAU_LUID@@PEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(struct _LUID *, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008c3c`
- `0x180011490`
- `0x180014c80`
- `0x180016370`

## callees

- `0x18000a690`
- `0x18000bea0`
- `0x1800114b4`
- `0x18001c340`
- `0x18002f810`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800115ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800115ac`
- `ntdll!RtlEnterCriticalSection` at `0x180011533`
- `ntdll!RtlEnterCriticalSection` at `0x180011533`
- `ntdll!RtlLeaveCriticalSection` at `0x1800115d9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800115d9`

## pseudocode

```c

```
