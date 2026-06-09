# operator delete(void *)

- ea: `0x140001b0c`
- end: `0x140001b11`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140013370`

## callees

- `0x1400016ee`

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
0x140001b0c  jmp     free_0
```
