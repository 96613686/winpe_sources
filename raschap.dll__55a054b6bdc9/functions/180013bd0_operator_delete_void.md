# operator delete(void *)

- ea: `0x180013bd0`
- end: `0x180013bd5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `14`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ff18`
- `0x180013f88`
- `0x180013fa0`
- `0x180014b20`
- `0x1800246a0`
- `0x180024834`
- `0x180024a28`
- `0x180024c04`
- `0x180024ea8`
- `0x180025030`
- `0x1800251e8`
- `0x18002572c`
- `0x18002594c`
- `0x180025c90`

## callees

- `0x1800145d4`

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
0x180013bd0  jmp     free
```
