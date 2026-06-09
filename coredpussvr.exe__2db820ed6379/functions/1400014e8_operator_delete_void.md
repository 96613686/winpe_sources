# operator delete(void *)

- ea: `0x1400014e8`
- end: `0x1400014ed`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001794`
- `0x1400017a0`
- `0x140001f20`

## callees

- `0x140002114`

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
0x1400014e8  jmp     free
```
