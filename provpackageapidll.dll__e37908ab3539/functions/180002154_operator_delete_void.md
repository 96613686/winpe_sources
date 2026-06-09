# operator delete(void *)

- ea: `0x180002154`
- end: `0x180002159`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800020a8`
- `0x1800020c0`

## callees

- `0x180001e42`

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
0x180002154  jmp     free
```
