# Win32LiveSystemProvider::GetCurrentThreadId(void)

- ea: `0x180012c80`
- end: `0x180012c87`
- name: `?GetCurrentThreadId@Win32LiveSystemProvider@@UEAAKXZ`
- size: `7`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012c80`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall Win32LiveSystemProvider::GetCurrentThreadId()
{
  return GetCurrentThreadId();
}

```

## disassembly

```asm
0x180012c80  jmp     cs:__imp_GetCurrentThreadId
```
