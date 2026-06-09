# operator delete(void *)

- ea: `0x180003288`
- end: `0x18000328d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003294`
- `0x1800032a0`

## callees

- `0x180003904`

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
0x180003288  jmp     free
```
