# operator delete(void *)

- ea: `0x180001f00`
- end: `0x180001f05`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001804`
- `0x180001d00`
- `0x180023e00`
- `0x180023e30`

## callees

- `0x180002360`

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
0x180001f00  jmp     free
```
