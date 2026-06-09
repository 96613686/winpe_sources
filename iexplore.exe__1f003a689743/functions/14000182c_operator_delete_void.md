# operator delete(void *)

- ea: `0x14000182c`
- end: `0x140001831`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140001cc1`

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
0x14000182c  jmp     free_0
```
