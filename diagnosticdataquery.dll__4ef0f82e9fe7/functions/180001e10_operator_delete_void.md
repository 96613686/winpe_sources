# operator delete(void *)

- ea: `0x180001e10`
- end: `0x180001e15`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800018d0`
- `0x180001900`
- `0x180001f10`

## callees

- `0x180005146`

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
0x180001e10  jmp     free_0
```
