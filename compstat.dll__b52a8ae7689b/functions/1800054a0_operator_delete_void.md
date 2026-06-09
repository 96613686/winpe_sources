# operator delete(void *)

- ea: `0x1800054a0`
- end: `0x1800054a5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `16`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001ec0`
- `0x180002e00`
- `0x180004180`
- `0x180004d70`
- `0x180005190`
- `0x180005380`
- `0x180007580`
- `0x180007ef0`
- `0x180008050`
- `0x180008088`
- `0x1800080c0`
- `0x180008904`
- `0x180008bf4`
- `0x180008c30`
- `0x180008c90`
- `0x180008e54`

## callees

- `0x180005976`

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
0x1800054a0  jmp     free_0
```
