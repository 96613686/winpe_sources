# operator delete(void *,unsigned __int64)

- ea: `0x1800025a0`
- end: `0x1800025a5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `103`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004850`
- `0x1800048b0`
- `0x1800048f0`
- `0x180004950`
- `0x1800098e0`
- `0x180009920`
- `0x18000d038`
- `0x18000d0e0`
- `0x18000d120`
- `0x18000d9e8`
- `0x18000dac0`
- `0x18000db40`
- `0x18000e0a0`
- `0x18000e2bc`
- `0x18000eb48`
- `0x18000ecb0`
- `0x18000ecf0`
- `0x18000ed30`
- `0x18001109c`
- `0x18001156c`
- `0x180011618`
- `0x180011780`
- `0x1800117d0`
- `0x180011840`
- `0x180012b00`
- `0x180013a04`
- `0x1800141e4`
- `0x1800144b4`
- `0x180014e04`
- `0x180014efc`
- `0x180015018`
- `0x180015158`
- `0x180015464`
- `0x1800155e8`
- `0x180015750`
- `0x1800158bc`
- `0x180016f34`
- `0x180017058`
- `0x1800171b4`
- `0x180017224`
- `0x1800172a4`
- `0x1800173b0`
- `0x180017418`
- `0x180017638`
- `0x18001767c`
- `0x1800176e8`
- `0x180017758`
- `0x180017be4`
- `0x180017da4`
- `0x180018050`

## callees

- `0x180002a4c`

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
0x1800025a0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
