# GetTempPathW

- ea: `0x1800f0a40`
- end: `0x1800f0c94`
- name: `GetTempPathW`
- size: `596`
- prototype: `DWORD __stdcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18018de10`

## callees

- `0x1800395b0`
- `0x18004b9d0`
- `0x1800f0a40`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800f0c52`
- `ntdll!RtlFreeHeap` at `0x1800f0c77`
- `ntdll!RtlFreeHeap` at `0x1801984be`
- `ntdll!RtlFreeHeap` at `0x1800f0c52`
- `ntdll!RtlFreeHeap` at `0x1800f0c77`
- `ntdll!RtlFreeHeap` at `0x1801984be`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1800f0ab7`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1800f0bda`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1800f0c0e`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1800f0ab7`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1800f0bda`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1800f0c0e`
- `ntdll!RtlGetFullPathName_U` at `0x1800f0b08`
- `ntdll!RtlGetFullPathName_U` at `0x1800f0b08`
- `ntdll!RtlAllocateHeap` at `0x1800f0a8f`
- `ntdll!RtlAllocateHeap` at `0x1800f0a8f`

## pseudocode

```c

```
