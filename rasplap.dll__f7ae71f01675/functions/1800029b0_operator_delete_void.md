# operator delete(void *)

- ea: `0x1800029b0`
- end: `0x1800029b5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001410`
- `0x1800018a0`
- `0x180001e50`

## callees

- `0x180002ec1`

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
0x1800029b0  jmp     free_0
```
