# operator delete(void *)

- ea: `0x180001ce4`
- end: `0x180001ce9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001d24`
- `0x1800020e0`
- `0x1800036b0`
- `0x1800036f0`
- `0x180006510`

## callees

- `0x18000270a`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x180001ce4  jmp     free
```
