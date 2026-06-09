# RtlCopyVolatileMemory

- ea: `0x180010870`
- end: `0x180010875`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a64`
- `0x18001f520`

## callees

- `0x180010980`

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
0x180010870  jmp     memmove
```
