# operator delete(void *)

- ea: `0x180001240`
- end: `0x180001245`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `12`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000124c`
- `0x1800017c0`
- `0x1800021c0`
- `0x180004030`
- `0x1800064f0`
- `0x180008d80`
- `0x180008db8`
- `0x180008de0`
- `0x180008e20`
- `0x18000b644`
- `0x18000bf00`
- `0x18000bf30`

## callees

- `0x1800017a5`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x180001240  jmp     free_0
```
