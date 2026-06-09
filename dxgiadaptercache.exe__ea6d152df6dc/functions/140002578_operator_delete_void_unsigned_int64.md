# operator delete(void *,unsigned __int64)

- ea: `0x140002578`
- end: `0x14000257d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `25`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140004798`
- `0x1400048b8`
- `0x1400049f8`
- `0x140004b84`
- `0x140004d34`
- `0x140004f00`
- `0x140005f4c`
- `0x1400061c8`
- `0x1400061ec`
- `0x14000625c`
- `0x1400062d8`
- `0x140006334`
- `0x1400063a0`
- `0x140006640`
- `0x14000672c`
- `0x140006ec0`
- `0x1400070d0`
- `0x140007110`
- `0x140007150`
- `0x14000718c`
- `0x140007220`
- `0x140007280`
- `0x1400072e0`
- `0x140007320`
- `0x140010660`

## callees

- `0x140002b90`

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
0x140002578  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
