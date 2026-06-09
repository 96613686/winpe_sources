# __threadhandle

- ea: `0x18003de60`
- end: `0x18003de67`
- name: `__threadhandle`
- size: `7`
- prototype: `uintptr_t __cdecl()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003de60`

## pseudocode

```c
// attributes: thunk
uintptr_t __cdecl _threadhandle()
{
  return (uintptr_t)GetCurrentThread();
}

```

## disassembly

```asm
0x18003de60  jmp     cs:__imp_GetCurrentThread
```
