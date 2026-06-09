# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemovePostOrder(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)

- ea: `0x18000b7a4`
- end: `0x18000b7e5`
- name: `?RemovePostOrder@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@AEAAXPEAVCNode@12@@Z`
- size: `65`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002350`
- `0x180007cb0`
- `0x18000b73c`
- `0x18000b7a4`

## callees

- `0x18000b7a4`
- `0x18000b7ec`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemovePostOrder(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  if ( a2 != *(_QWORD **)(a1 + 40) )
  {
    ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemovePostOrder(a1);
    ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemovePostOrder(a1);
    return ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::FreeNode(
             a1,
             a2);
  }
  return result;
}

```

## disassembly

```asm
0x18000b7a4  mov     [rsp+arg_0], rbx
0x18000b7a9  push    rdi
0x18000b7aa  sub     rsp, 20h
0x18000b7ae  mov     rbx, rdx
0x18000b7b1  mov     rdi, rcx
0x18000b7b4  cmp     rdx, [rcx+28h]
0x18000b7b8  jz      short loc_18000B7DA
0x18000b7ba  mov     rdx, [rdx+18h]
0x18000b7be  call    ?RemovePostOrder@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemovePostOrder(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000b7c3  mov     rdx, [rbx+20h]
0x18000b7c7  mov     rcx, rdi
0x18000b7ca  call    ?RemovePostOrder@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemovePostOrder(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000b7cf  mov     rdx, rbx
0x18000b7d2  mov     rcx, rdi
0x18000b7d5  call    ?FreeNode@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::FreeNode(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000b7da  mov     rbx, [rsp+28h+arg_0]
0x18000b7df  add     rsp, 20h
0x18000b7e3  pop     rdi
0x18000b7e4  retn
```
