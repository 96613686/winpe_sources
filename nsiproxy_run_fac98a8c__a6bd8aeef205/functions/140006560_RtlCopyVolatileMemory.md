# RtlCopyVolatileMemory

- ea: `0x140006560`
- end: `0x140006565`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x140001010`
- `0x140001880`
- `0x140002280`
- `0x140002850`
- `0x140002eb0`
- `0x1400033c0`
- `0x140003700`
- `0x140003af0`
- `0x140003e20`
- `0x1400043d0`
- `0x140004ca0`
- `0x1400056e8`
- `0x140005c3c`
- `0x1400060e8`
- `0x14000d08c`

## callees

- `0x140006680`

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
0x140006560  jmp     memmove
```
