# operator delete(void *)

- ea: `0x140001748`
- end: `0x14000174d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001754`
- `0x140001760`

## callees

- `0x140001ec6`

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
0x140001748  jmp     free
```
