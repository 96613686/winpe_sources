# operator delete(void *)

- ea: `0x1400025f8`
- end: `0x1400025fd`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001cb8`
- `0x140001cd0`

## callees

- `0x14000277e`

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
0x1400025f8  jmp     free
```
