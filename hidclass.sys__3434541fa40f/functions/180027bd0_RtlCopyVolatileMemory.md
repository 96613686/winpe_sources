# RtlCopyVolatileMemory

- ea: `0x180027bd0`
- end: `0x180027bd5`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800085d8`
- `0x18003802c`

## callees

- `0x180027d00`

## pseudocode

```c
// attributes: thunk
void *__cdecl RtlCopyVolatileMemory(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x180027bd0  jmp     memmove
```
