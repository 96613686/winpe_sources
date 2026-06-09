# operator delete(void *,unsigned __int64)

- ea: `0x180003b10`
- end: `0x180003b15`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `64`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800049b8`
- `0x1800052b0`
- `0x1800052f0`
- `0x180009120`
- `0x180009150`
- `0x18000a5d4`
- `0x18000a938`
- `0x18000aac0`
- `0x18000ab00`
- `0x18000ab40`
- `0x18000ab80`
- `0x18000abc0`
- `0x18000ac00`
- `0x18000ac40`
- `0x18000b260`
- `0x18000b470`
- `0x18000b530`
- `0x18000d7d4`
- `0x18000fb28`
- `0x18000fc6c`
- `0x1800100a4`
- `0x1800100d4`
- `0x180010110`
- `0x180010150`
- `0x180010190`
- `0x180011570`
- `0x1800122a0`
- `0x1800135a0`
- `0x180013640`
- `0x180017340`
- `0x180017720`
- `0x1800189dc`
- `0x180018a0c`
- `0x180018a40`
- `0x180018a80`
- `0x180018ac0`
- `0x18001cd80`
- `0x18001cdc0`
- `0x180020bf0`
- `0x180020c30`
- `0x180020c70`
- `0x180020cb0`
- `0x1800235e0`
- `0x180028726`
- `0x1800288e6`
- `0x18002891e`
- `0x180028a36`
- `0x180028abf`
- `0x180028b21`
- `0x180028bc4`

## callees

- `0x180003b04`

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
0x180003b10  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
