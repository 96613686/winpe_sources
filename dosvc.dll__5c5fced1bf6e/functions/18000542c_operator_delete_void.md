# operator delete(void *)

- ea: `0x18000542c`
- end: `0x180005431`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800053f0`
- `0x180005400`

## callees

- `0x180005b14`

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
0x18000542c  jmp     free
```
