# operator delete(void *,unsigned __int64)

- ea: `0x180002c8c`
- end: `0x180002c91`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `30`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000402c`
- `0x1800047a0`
- `0x1800047e0`
- `0x180004820`
- `0x180004870`
- `0x1800048b0`
- `0x1800051d8`
- `0x18000b294`
- `0x18000d844`
- `0x18000dcb0`
- `0x18000de50`
- `0x18000dea0`
- `0x18000df00`
- `0x18000eba8`
- `0x18000f210`
- `0x1800113e0`
- `0x180011d60`
- `0x180011fc8`
- `0x180011fec`
- `0x180012010`
- `0x180012098`
- `0x180012108`
- `0x180012144`
- `0x18001219c`
- `0x180012208`
- `0x1800122c4`
- `0x1800130f4`
- `0x1800136bc`
- `0x18001382c`
- `0x180014770`

## callees

- `0x180002df0`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180002c8c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
