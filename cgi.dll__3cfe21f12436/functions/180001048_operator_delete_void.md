# operator delete(void *)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001aa0`
- `0x180001b20`
- `0x1800028e0`
- `0x1800028f0`
- `0x1800062a0`
- `0x180006310`
- `0x1800066a8`
- `0x1800069b4`
- `0x180006cf0`

## callees

- `0x180001526`

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
