# RtlCopyVolatileMemory

- ea: `0x140005e40`
- end: `0x140005e45`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002aa0`
- `0x14000e008`

## callees

- `0x140005f40`

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
0x140005e40  jmp     memmove
```
