# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)

- ea: `0x180002128`
- end: `0x180002134`
- name: `??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c99c`
- `0x18000c9c0`
- `0x18000caff`
- `0x18000cb11`
- `0x18000cb23`
- `0x18000cc7b`

## callees

- `0x180003864`

## pseudocode

```c
void __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        _QWORD *a1)
{
  ATL::CStringData::Release((ATL::CStringData *)(*a1 - 24LL));
}

```

## disassembly

```asm
0x180002128  mov     rcx, [rcx]
0x18000212b  sub     rcx, 18h; this
0x18000212f  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
