# __threadid

- ea: `0x18003de70`
- end: `0x18003de77`
- name: `__threadid`
- size: `7`
- prototype: `unsigned int __cdecl()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180020b14`
- `0x180022674`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003de70`

## pseudocode

```c
// attributes: thunk
unsigned int __cdecl _threadid()
{
  return GetCurrentThreadId();
}

```

## disassembly

```asm
0x18003de70  jmp     cs:__imp_GetCurrentThreadId
```
