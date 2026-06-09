# NlsAnsiToUnicode

- ea: `0x1800381f8`
- end: `0x18003832b`
- name: `NlsAnsiToUnicode`
- size: `307`
- prototype: `__int64 __usercall@<rax>(UINT CodePage@<ecx>, LPCCH lpMultiByteStr@<rdx>, int cbMultiByte@<r8d>, __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180037d80`
- `0x180037fc0`
- `0x180053990`
- `0x180054680`
- `0x180064240`
- `0x180064600`
- `0x1800646e0`

## callees

- `0x1800381f8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180038317`
- `ntdll!RtlFreeHeap` at `0x180038317`
- `ntdll!RtlAllocateHeap` at `0x1800382d9`
- `ntdll!RtlAllocateHeap` at `0x1800382d9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003827b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003827b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003823d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003823d`

## pseudocode

```c

```
