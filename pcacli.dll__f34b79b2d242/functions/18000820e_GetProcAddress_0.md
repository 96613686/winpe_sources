# GetProcAddress_0

- ea: `0x18000820e`
- end: `0x180008214`
- name: `GetProcAddress_0`
- size: `6`
- prototype: `FARPROC __stdcall(HMODULE hModule, LPCSTR lpProcName)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004790`
- `0x1800054f0`
- `0x1800092ac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000820e`

## pseudocode

```c
// attributes: thunk
FARPROC __stdcall GetProcAddress_0(HMODULE hModule, LPCSTR lpProcName)
{
  return GetProcAddress(hModule, lpProcName);
}

```

## disassembly

```asm
0x18000820e  jmp     cs:__imp_GetProcAddress
```
