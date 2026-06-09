# ShellShim_GetHashFromFile

- ea: `0x180024e20`
- end: `0x180024f51`
- name: `ShellShim_GetHashFromFile`
- size: `305`
- prototype: `DWORD __stdcall(LPCSTR szFilePath, unsigned int *piHashAlg, BYTE *pbHash, DWORD cchHash, DWORD *pchHash)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001c10`
- `0x180024e20`
- `0x18002daf8`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180024ea0`
- `KERNEL32!GetProcAddress` at `0x180024f03`
- `KERNEL32!GetProcAddress` at `0x180024ea0`
- `KERNEL32!GetProcAddress` at `0x180024f03`

## pseudocode

```c

```
