# RtlMoveVolatileMemory

- ea: `0x14000ba60`
- end: `0x14000ba65`
- name: `RtlMoveVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000bb80`

## pseudocode

```c
// attributes: thunk
void *__cdecl RtlMoveVolatileMemory(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x14000ba60  jmp     memmove
```
