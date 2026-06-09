# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Predecessor(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)

- ea: `0x18000bdfc`
- end: `0x18000be4d`
- name: `?Predecessor@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z`
- size: `81`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000aa08`
- `0x18000b8f0`

## callees

- `0x18000bdfc`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Predecessor(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax
  __int64 i; // rcx
  char v5; // dl

  if ( !a2 )
    return 0;
  result = *(_QWORD *)(a2 + 24);
  if ( result == *(_QWORD *)(a1 + 40) )
  {
    for ( i = *(_QWORD *)(a2 + 40); i != *(_QWORD *)(a1 + 40); i = *(_QWORD *)(i + 40) )
    {
      if ( a2 != *(_QWORD *)(i + 24) )
      {
        v5 = 0;
        goto LABEL_13;
      }
      a2 = i;
    }
    v5 = 1;
LABEL_13:
    result = 0;
    if ( !v5 )
      return i;
  }
  else
  {
    if ( !result )
      return 0;
    while ( *(_QWORD *)(result + 32) != *(_QWORD *)(a1 + 40) )
      result = *(_QWORD *)(result + 32);
  }
  return result;
}

```

## disassembly

```asm
0x18000bdfc  mov     r8, rcx
0x18000bdff  test    rdx, rdx
0x18000be02  jnz     short loc_18000BE07
0x18000be04  xor     eax, eax
0x18000be06  retn
0x18000be07  mov     rax, [rdx+18h]
0x18000be0b  cmp     rax, [rcx+28h]
0x18000be0f  jz      short loc_18000BE25
0x18000be11  test    rax, rax
0x18000be14  jz      short loc_18000BE04
0x18000be16  mov     rcx, [rax+20h]
0x18000be1a  cmp     rcx, [r8+28h]
0x18000be1e  jz      short locret_18000BE4C
0x18000be20  mov     rax, rcx
0x18000be23  jmp     short loc_18000BE16
0x18000be25  mov     rcx, [rdx+28h]
0x18000be29  cmp     rcx, [r8+28h]
0x18000be2d  jz      short loc_18000BE42
0x18000be2f  cmp     rdx, [rcx+18h]
0x18000be33  jnz     short loc_18000BE3E
0x18000be35  mov     rdx, rcx
0x18000be38  mov     rcx, [rcx+28h]
0x18000be3c  jmp     short loc_18000BE29
0x18000be3e  xor     dl, dl
0x18000be40  jmp     short loc_18000BE44
0x18000be42  mov     dl, 1
0x18000be44  xor     eax, eax
0x18000be46  test    dl, dl
0x18000be48  cmovz   rax, rcx
0x18000be4c  retn
```
