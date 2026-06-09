# operator delete(void *)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001950`
- `0x180002170`
- `0x1800024d0`
- `0x18000256c`
- `0x1800025e0`
- `0x180002978`
- `0x180002b7c`
- `0x180002cb0`

## callees

- `0x180001716`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x180001048  jmp     free_0
```
