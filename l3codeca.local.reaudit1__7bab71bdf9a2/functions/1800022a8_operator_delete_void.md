# operator delete(void *)

- ea: `0x1800022a8`
- end: `0x1800022ad`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000229c`

## callees

- `0x180001c98`

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
0x1800022a8  jmp     free
```
