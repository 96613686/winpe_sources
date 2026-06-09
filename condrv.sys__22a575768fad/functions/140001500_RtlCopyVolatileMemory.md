# RtlCopyVolatileMemory

- ea: `0x140001500`
- end: `0x140001505`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140001154`
- `0x1400080c4`
- `0x140008da4`
- `0x140008e54`
- `0x140008f04`
- `0x140008fb4`
- `0x14000aa00`
- `0x14000ca90`
- `0x14000cc10`
- `0x14000cd40`
- `0x14000d2a0`
- `0x14000d4a0`

## callees

- `0x140001600`

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
0x140001500  jmp     memmove
```
