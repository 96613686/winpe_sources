# operator delete(void *)

- ea: `0x180001008`
- end: `0x18000100d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001020`
- `0x180001cc0`
- `0x180001fec`
- `0x1800020f8`
- `0x180002ad0`
- `0x1800041e0`
- `0x180004a30`
- `0x180004b30`

## callees

- `0x180001536`

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
0x180001008  jmp     free_0
```
