# RtlSetVolatileMemory

- ea: `0x140001e60`
- end: `0x140001e65`
- name: `RtlSetVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b0b8`
- `0x140014ed4`

## callees

- `0x140002240`

## pseudocode

```c
// attributes: thunk
void *__cdecl RtlSetVolatileMemory(void *a1, int Val, size_t Size)
{
  return memset(a1, Val, Size);
}

```

## disassembly

```asm
0x140001e60  jmp     memset
```
