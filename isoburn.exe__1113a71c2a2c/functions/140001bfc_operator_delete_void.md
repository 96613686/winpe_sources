# operator delete(void *)

- ea: `0x140001bfc`
- end: `0x140001c01`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001c54`

## callees

- `0x140002b8a`

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
0x140001bfc  jmp     free
```
