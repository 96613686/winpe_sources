# _EnumerateDriveSpaces(_SUEX_FILTER *,_GUID *,void *,ulong,ulong *)

- ea: `0x18003d4bc`
- end: `0x18003d9af`
- name: `?_EnumerateDriveSpaces@@YAHPEAU_SUEX_FILTER@@PEAU_GUID@@PEAXKPEAK@Z`
- size: `1267`
- prototype: `__int64 __usercall@<rax>(struct _SUEX_FILTER *@<rcx>, struct _GUID *@<rdx>, void *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x18003166c`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x180006350`
- `0x18001fa04`
- `0x180023e3c`
- `0x1800289d8`
- `0x1800296c4`
- `0x180029b04`
- `0x180037b5c`
- `0x18003a1c8`
- `0x18003d4bc`
- `0x180045130`
- `0x1800459a8`
- `0x1800b7634`
- `0x1801b84a0`
- `0x1801bb1cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d807`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d822`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d8cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d807`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d822`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d8cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d8e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d8f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d8e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d8f5`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18003d95d`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18003d95d`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18003d972`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18003d972`

## pseudocode

```c

```
