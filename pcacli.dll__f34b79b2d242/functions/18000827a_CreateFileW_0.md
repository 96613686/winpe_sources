# CreateFileW_0

- ea: `0x18000827a`
- end: `0x180008280`
- name: `CreateFileW_0`
- size: `6`
- prototype: `HANDLE __stdcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, LPSECURITY_ATTRIBUTES lpSecurityAttributes, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes, HANDLE hTemplateFile)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007200`
- `0x180008d4c`
- `0x1800092ac`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000827a`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall CreateFileW_0(
        LPCWSTR lpFileName,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        HANDLE hTemplateFile)
{
  return CreateFileW(
           lpFileName,
           dwDesiredAccess,
           dwShareMode,
           lpSecurityAttributes,
           dwCreationDisposition,
           dwFlagsAndAttributes,
           hTemplateFile);
}

```

## disassembly

```asm
0x18000827a  jmp     cs:__imp_CreateFileW
```
