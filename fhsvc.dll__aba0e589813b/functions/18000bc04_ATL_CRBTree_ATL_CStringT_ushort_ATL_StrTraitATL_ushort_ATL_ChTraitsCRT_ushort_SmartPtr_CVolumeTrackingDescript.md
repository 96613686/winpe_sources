# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode * *)

- ea: `0x18000bc04`
- end: `0x18000bc24`
- name: `?SetNil@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAPEAVCNode@12@@Z`
- size: `32`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bac8`
- `0x18000bff8`
- `0x18000f6b8`
- `0x18000f7c8`
- `0x18000f8cc`
- `0x18000fb5c`
- `0x18000fcd4`

## callees

- `0x18000b48c`
- `0x18000bc04`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  result = *(_QWORD *)(a1 + 40);
  *a2 = result;
  return result;
}

```

## disassembly

```asm
0x18000bc04  sub     rsp, 28h
0x18000bc08  test    rdx, rdx
0x18000bc0b  jnz     short loc_18000BC18
0x18000bc0d  mov     ecx, 80004005h; int
0x18000bc12  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000bc18  mov     rax, [rcx+28h]
0x18000bc1c  mov     [rdx], rax
0x18000bc1f  add     rsp, 28h
0x18000bc23  retn
```
