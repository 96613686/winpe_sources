# operator delete(void *)

- ea: `0x180001bc4`
- end: `0x180001bc9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `49`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002220`
- `0x180003224`
- `0x1800033e0`
- `0x180003420`
- `0x180003458`
- `0x1800069b0`
- `0x1800076d8`
- `0x1800135c4`
- `0x180013610`
- `0x1800146c4`
- `0x18001472c`
- `0x1800147d8`
- `0x180014ee8`
- `0x1800153a0`
- `0x1800160c8`
- `0x180016364`
- `0x180019d5c`
- `0x18001bf28`
- `0x18001bf68`
- `0x18001dc34`
- `0x18001e004`
- `0x18001ec84`
- `0x180021368`
- `0x1800213b8`
- `0x180021730`
- `0x180021a14`
- `0x180021a4c`
- `0x180021a84`
- `0x180021aac`
- `0x180022410`
- `0x180022450`
- `0x180023a44`
- `0x1800277e0`
- `0x180027b88`
- `0x18002a2e0`
- `0x1800325d0`
- `0x1800372c0`
- `0x1800372f0`
- `0x180037cc7`
- `0x180037f3e`
- `0x180038031`
- `0x1800380ce`
- `0x18003830e`
- `0x18003856f`
- `0x180038647`
- `0x1800388f0`
- `0x180038992`
- `0x180038a91`
- `0x180038b52`

## callees

- `0x18000220d`

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
0x180001bc4  jmp     free_0
```
