# operator delete(void *)

- ea: `0x140002f54`
- end: `0x140002f59`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002624`
- `0x1400028f0`

## callees

- `0x140003114`

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
0x140002f54  jmp     free
```
