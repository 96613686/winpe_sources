# operator delete(void *)

- ea: `0x140002b90`
- end: `0x140002b95`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002578`
- `0x140002590`

## callees

- `0x140002d04`

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
0x140002b90  jmp     free
```
