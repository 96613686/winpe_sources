# operator delete(void *,unsigned __int64)

- ea: `0x180001824`
- end: `0x180001829`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `45`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001830`
- `0x180003618`
- `0x1800039f0`
- `0x180003ca0`
- `0x180003ce0`
- `0x180006138`
- `0x180007f80`
- `0x180007fc0`
- `0x180008ca8`
- `0x1800096c4`
- `0x1800098e0`
- `0x180009920`
- `0x180009960`
- `0x1800099a0`
- `0x18000b7b0`
- `0x18000c234`
- `0x18000f600`
- `0x180011bc0`
- `0x180011c14`
- `0x180011eec`
- `0x180011ff4`
- `0x1800123c0`
- `0x1800129cc`
- `0x1800153a8`
- `0x180015764`
- `0x1800180b0`
- `0x180019054`
- `0x1800191a0`
- `0x180019540`
- `0x180019e28`
- `0x18001b740`
- `0x18001d5d8`
- `0x18001d7d0`
- `0x18001fa60`
- `0x180020dd0`
- `0x180021650`
- `0x180022630`
- `0x1800261d2`
- `0x180026247`
- `0x180026493`
- `0x1800264db`
- `0x18002664c`
- `0x180026783`
- `0x1800268a6`
- `0x180026992`

## callees

- `0x180001f20`

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
0x180001824  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
