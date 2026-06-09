# operator delete(void *)

- ea: `0x140002178`
- end: `0x14000217d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400021b4`
- `0x140002210`

## callees

- `0x140002be4`

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
0x140002178  jmp     free
```
