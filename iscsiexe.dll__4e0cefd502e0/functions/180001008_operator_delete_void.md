# operator delete(void *)

- ea: `0x180001008`
- end: `0x18000100d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001ce6`

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
0x180001008  jmp     free
```
