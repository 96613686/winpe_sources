# operator delete(void *,unsigned __int64)

- ea: `0x1800067f4`
- end: `0x1800067f9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `21`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180009200`
- `0x180009240`
- `0x180009280`
- `0x1800092c0`
- `0x180009300`
- `0x180009340`
- `0x180009380`
- `0x1800093c0`
- `0x180009400`
- `0x180009440`
- `0x180009480`
- `0x1800094c0`
- `0x18000eebc`
- `0x18000ef14`
- `0x180011520`
- `0x180011560`
- `0x1800172ec`
- `0x180017c70`
- `0x180017cb0`
- `0x18002020e`
- `0x1800202af`

## callees

- `0x180006314`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x1800067f4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
