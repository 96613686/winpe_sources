# _EnumerateDriveSpaces(_SUEX_FILTER *,_GUID *,void *,ulong,ulong *)

- ea: `0x18003c2ec`
- end: `0x18003c7b4`
- name: `?_EnumerateDriveSpaces@@YAHPEAU_SUEX_FILTER@@PEAU_GUID@@PEAXKPEAK@Z`
- size: `1224`
- prototype: `__int64 __usercall@<rax>(struct _SUEX_FILTER *@<rcx>, struct _GUID *@<rdx>, void *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x180030808`

## callees

- `0x1800011b0`
- `0x1800015b8`
- `0x180006290`
- `0x18001f294`
- `0x180023508`
- `0x180027ed0`
- `0x180028b9c`
- `0x180028f84`
- `0x180036a98`
- `0x18003902c`
- `0x18003c2ec`
- `0x180043de4`
- `0x1800445d0`
- `0x1800b4940`
- `0x1801b2370`
- `0x1801b4e9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c637`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c64c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c6f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c637`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c64c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c6f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c6ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c70d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c6ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c70d`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18003c76f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18003c76f`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18003c77e`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18003c77e`

## pseudocode

```c

```
