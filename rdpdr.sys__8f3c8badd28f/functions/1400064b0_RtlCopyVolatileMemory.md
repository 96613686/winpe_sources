# RtlCopyVolatileMemory

- ea: `0x1400064b0`
- end: `0x1400064b5`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140003064`
- `0x140011bfc`
- `0x140019220`
- `0x140019720`
- `0x140019aa4`
- `0x140019f18`

## callees

- `0x1400065c0`

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
0x1400064b0  jmp     memmove
```
