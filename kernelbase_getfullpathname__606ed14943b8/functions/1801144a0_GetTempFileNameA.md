# GetTempFileNameA

- ea: `0x1801144a0`
- end: `0x18011450d`
- name: `GetTempFileNameA`
- size: `109`
- prototype: `UINT __stdcall(LPCSTR lpPathName, LPCSTR lpPrefixString, UINT uUnique, LPSTR lpTempFileName)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18004b9d0`
- `0x180073120`
- `0x1800836d0`
- `0x1801144a0`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1801144ff`
- `ntdll!RtlFreeUnicodeString` at `0x1801a3513`
- `ntdll!RtlFreeUnicodeString` at `0x1801a3523`
- `ntdll!RtlFreeUnicodeString` at `0x1801144ff`
- `ntdll!RtlFreeUnicodeString` at `0x1801a3513`
- `ntdll!RtlFreeUnicodeString` at `0x1801a3523`
- `ntdll!RtlInitUnicodeString` at `0x1801a34b3`
- `ntdll!RtlInitUnicodeString` at `0x1801a34b3`
- `ntdll!RtlSetLastWin32Error` at `0x1801a3482`
- `ntdll!RtlSetLastWin32Error` at `0x1801a3482`
- `ntdll!RtlFreeHeap` at `0x1801a3503`
- `ntdll!RtlFreeHeap` at `0x1801a3503`
- `ntdll!RtlAllocateHeap` at `0x1801a346a`
- `ntdll!RtlAllocateHeap` at `0x1801a346a`

## pseudocode

```c

```
