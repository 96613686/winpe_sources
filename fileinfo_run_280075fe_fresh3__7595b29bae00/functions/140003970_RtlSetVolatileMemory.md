# RtlSetVolatileMemory

- ea: `0x140003970`
- end: `0x140003975`
- name: `RtlSetVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d114`
- `0x14000d8cc`
- `0x140016fa0`
- `0x140017284`

## callees

- `0x140003d80`

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
0x140003970  jmp     memset
```
