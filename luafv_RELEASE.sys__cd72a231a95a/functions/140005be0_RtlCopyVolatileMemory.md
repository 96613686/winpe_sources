# RtlCopyVolatileMemory

- ea: `0x140005be0`
- end: `0x140005be5`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140014b8c`
- `0x140024050`
- `0x140024614`

## callees

- `0x140005d00`

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
0x140005be0  jmp     memmove
```
