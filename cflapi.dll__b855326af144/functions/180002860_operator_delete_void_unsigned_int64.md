# operator delete(void *,unsigned __int64)

- ea: `0x180002860`
- end: `0x180002865`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `65`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004ab0`
- `0x180004af0`
- `0x1800087f0`
- `0x180008868`
- `0x180008a68`
- `0x180008ad0`
- `0x180009490`
- `0x1800094d0`
- `0x180009510`
- `0x180009570`
- `0x1800099c4`
- `0x180009adc`
- `0x180011540`
- `0x18001479c`
- `0x180014b74`
- `0x180014ce0`
- `0x18001539c`
- `0x1800154ac`
- `0x180015794`
- `0x1800158b8`
- `0x1800159b0`
- `0x180015b04`
- `0x180015c78`
- `0x180015db8`
- `0x180015ef8`
- `0x18001606c`
- `0x1800161cc`
- `0x180016350`
- `0x180016488`
- `0x1800169ac`
- `0x18001a954`
- `0x18001a978`
- `0x18001aa1c`
- `0x18001aa8c`
- `0x18001ab24`
- `0x18001ab94`
- `0x18001b050`
- `0x18001b074`
- `0x18001b098`
- `0x18001b0bc`
- `0x18001b128`
- `0x18001b19c`
- `0x18001b20c`
- `0x18001b294`
- `0x18001b31c`
- `0x18001b3fc`
- `0x18001b49c`
- `0x18001b900`
- `0x18001b940`
- `0x18001b970`

## callees

- `0x180002d7c`

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
0x180002860  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
