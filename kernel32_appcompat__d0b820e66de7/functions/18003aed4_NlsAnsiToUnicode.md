# NlsAnsiToUnicode

- ea: `0x18003aed4`
- end: `0x18003b023`
- name: `NlsAnsiToUnicode`
- size: `335`
- prototype: `__int64 __usercall@<rax>(UINT CodePage@<ecx>, LPCCH lpMultiByteStr@<rdx>, int cbMultiByte@<r8d>, __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003a9e0`
- `0x18003ac60`
- `0x180058720`
- `0x1800595f0`
- `0x18006ae60`
- `0x18006b270`
- `0x18006b360`

## callees

- `0x18003aed4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003b006`
- `ntdll!RtlFreeHeap` at `0x18003b006`
- `ntdll!RtlAllocateHeap` at `0x18003afc2`
- `ntdll!RtlAllocateHeap` at `0x18003afc2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003af5e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003af5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003af19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003af19`

## pseudocode

```c

```
