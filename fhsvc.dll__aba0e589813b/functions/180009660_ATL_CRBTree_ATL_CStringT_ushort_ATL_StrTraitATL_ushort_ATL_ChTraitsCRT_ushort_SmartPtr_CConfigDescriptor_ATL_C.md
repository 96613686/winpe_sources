# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::GetValueAt(__POSITION *)

- ea: `0x180009660`
- end: `0x18000967d`
- name: `?GetValueAt@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@QEAAAEAV?$SmartPtr@VCConfigDescriptor@@@@PEAU__POSITION@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ac48`

## callees

- `0x180009660`
- `0x18000b48c`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::GetValueAt(
        __int64 a1,
        __int64 a2)
{
  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  return a2 + 8;
}

```

## disassembly

```asm
0x180009660  sub     rsp, 28h
0x180009664  test    rdx, rdx
0x180009667  jz      short loc_180009672
0x180009669  lea     rax, [rdx+8]
0x18000966d  add     rsp, 28h
0x180009671  retn
0x180009672  mov     ecx, 80004005h; int
0x180009677  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
