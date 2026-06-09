# RtlCopyVolatileMemory

- ea: `0x140004140`
- end: `0x140004145`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400010f4`
- `0x140001ba0`
- `0x14000b008`
- `0x14000bfc4`

## callees

- `0x140004240`

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
0x140004140  jmp     memmove
```
