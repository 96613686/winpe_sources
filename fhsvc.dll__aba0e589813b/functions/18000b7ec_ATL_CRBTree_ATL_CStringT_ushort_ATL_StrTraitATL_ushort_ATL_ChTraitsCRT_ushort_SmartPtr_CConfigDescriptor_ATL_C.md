# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::FreeNode(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)

- ea: `0x18000b7ec`
- end: `0x18000b82f`
- name: `?FreeNode@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@AEAAXPEAVCNode@12@@Z`
- size: `67`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b7a4`
- `0x18000f7c8`

## callees

- `0x18000b48c`
- `0x18000b7ec`
- `0x18000ee74`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::FreeNode(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CPair::~CPair(a2);
  result = *(_QWORD *)(a1 + 16);
  a2[3] = result;
  *(_QWORD *)(a1 + 16) = a2;
  --*(_QWORD *)(a1 + 8);
  return result;
}

```

## disassembly

```asm
0x18000b7ec  mov     [rsp+arg_0], rbx
0x18000b7f1  push    rdi
0x18000b7f2  sub     rsp, 20h
0x18000b7f6  mov     rbx, rdx
0x18000b7f9  mov     rdi, rcx
0x18000b7fc  test    rdx, rdx
0x18000b7ff  jnz     short loc_18000B80C
0x18000b801  mov     ecx, 80004005h; int
0x18000b806  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b80c  mov     rcx, rbx
0x18000b80f  call    ??1CPair@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEAA@XZ; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CPair::~CPair(void)
0x18000b814  mov     rax, [rdi+10h]
0x18000b818  mov     [rbx+18h], rax
0x18000b81c  mov     [rdi+10h], rbx
0x18000b820  dec     qword ptr [rdi+8]
0x18000b824  mov     rbx, [rsp+28h+arg_0]
0x18000b829  add     rsp, 20h
0x18000b82d  pop     rdi
0x18000b82e  retn
```
