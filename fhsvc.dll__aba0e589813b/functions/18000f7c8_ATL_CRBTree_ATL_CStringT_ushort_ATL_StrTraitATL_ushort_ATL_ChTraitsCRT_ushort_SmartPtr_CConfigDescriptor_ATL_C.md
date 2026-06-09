# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RBDelete(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)

- ea: `0x18000f7c8`
- end: `0x18000f8c4`
- name: `?RBDelete@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@AEAA_NPEAVCNode@12@@Z`
- size: `252`
- prototype: `char __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180003f00`

## callees

- `0x1800076d0`
- `0x18000b7ec`
- `0x18000bc04`
- `0x18000f7c8`
- `0x18000f9dc`

## pseudocode

```c
char __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RBDelete(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r9
  __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx

  if ( !a2 )
    return 0;
  v6 = a1[5];
  if ( *(_QWORD *)(a2 + 24) == v6 || *(_QWORD *)(a2 + 32) == v6 )
    v7 = a2;
  else
    v7 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Successor(
           a1,
           a2,
           a3,
           v6);
  v8 = *(_QWORD *)(v7 + 24);
  if ( v8 == v6 )
    v8 = *(_QWORD *)(v7 + 32);
  *(_QWORD *)(v8 + 40) = *(_QWORD *)(v7 + 40);
  v9 = *(_QWORD *)(v7 + 40);
  if ( v9 == a1[5] )
  {
    *a1 = v8;
  }
  else if ( v7 == *(_QWORD *)(v9 + 24) )
  {
    *(_QWORD *)(v9 + 24) = v8;
  }
  else
  {
    *(_QWORD *)(v9 + 32) = v8;
  }
  if ( *(_DWORD *)(v7 + 16) == 1 )
    ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDeleteFixup(a1);
  if ( v7 != a2 )
  {
    *(_QWORD *)(v7 + 40) = *(_QWORD *)(a2 + 40);
    v10 = *(_QWORD *)(a2 + 40);
    if ( *(_QWORD *)(v10 + 24) == a2 )
      *(_QWORD *)(v10 + 24) = v7;
    else
      *(_QWORD *)(v10 + 32) = v7;
    v11 = *(_QWORD *)(a2 + 32);
    *(_QWORD *)(v7 + 32) = v11;
    *(_QWORD *)(v7 + 24) = *(_QWORD *)(a2 + 24);
    *(_DWORD *)(v7 + 16) = *(_DWORD *)(a2 + 16);
    *(_QWORD *)(v11 + 40) = v7;
    *(_QWORD *)(*(_QWORD *)(v7 + 24) + 40LL) = v7;
    if ( *a1 == a2 )
      *a1 = v7;
  }
  if ( *a1 )
    ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(
      a1,
      *a1 + 40);
  ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::FreeNode(
    (__int64)a1,
    (_QWORD *)a2);
  return 1;
}

```

## disassembly

```asm
0x18000f7c8  mov     [rsp+arg_0], rbx
0x18000f7cd  mov     [rsp+arg_8], rsi
0x18000f7d2  push    rdi
0x18000f7d3  sub     rsp, 20h
0x18000f7d7  mov     rdi, rdx
0x18000f7da  mov     rsi, rcx
0x18000f7dd  test    rdx, rdx
0x18000f7e0  jnz     short loc_18000F7E9
0x18000f7e2  xor     al, al
0x18000f7e4  jmp     loc_18000F8B4
0x18000f7e9  mov     r9, [rcx+28h]
0x18000f7ed  cmp     [rdx+18h], r9
0x18000f7f1  jz      short loc_18000F803
0x18000f7f3  cmp     [rdx+20h], r9
0x18000f7f7  jz      short loc_18000F803
0x18000f7f9  call    ?Successor@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Successor(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000f7fe  mov     rbx, rax
0x18000f801  jmp     short loc_18000F806
0x18000f803  mov     rbx, rdi
0x18000f806  mov     rdx, [rbx+18h]
0x18000f80a  cmp     rdx, r9
0x18000f80d  jnz     short loc_18000F813
0x18000f80f  mov     rdx, [rbx+20h]
0x18000f813  mov     rax, [rbx+28h]
0x18000f817  mov     [rdx+28h], rax
0x18000f81b  mov     rax, [rbx+28h]
0x18000f81f  cmp     rax, [rsi+28h]
0x18000f823  jnz     short loc_18000F82A
0x18000f825  mov     [rsi], rdx
0x18000f828  jmp     short loc_18000F83A
0x18000f82a  cmp     rbx, [rax+18h]
0x18000f82e  jnz     short loc_18000F836
0x18000f830  mov     [rax+18h], rdx
0x18000f834  jmp     short loc_18000F83A
0x18000f836  mov     [rax+20h], rdx
0x18000f83a  cmp     dword ptr [rbx+10h], 1
0x18000f83e  jnz     short loc_18000F848
0x18000f840  mov     rcx, rsi
0x18000f843  call    ?RBDeleteFixup@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDeleteFixup(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000f848  cmp     rbx, rdi
0x18000f84b  jz      short loc_18000F893
0x18000f84d  mov     rax, [rdi+28h]
0x18000f851  mov     [rbx+28h], rax
0x18000f855  mov     rax, [rdi+28h]
0x18000f859  cmp     [rax+18h], rdi
0x18000f85d  jnz     short loc_18000F865
0x18000f85f  mov     [rax+18h], rbx
0x18000f863  jmp     short loc_18000F869
0x18000f865  mov     [rax+20h], rbx
0x18000f869  mov     rcx, [rdi+20h]
0x18000f86d  mov     [rbx+20h], rcx
0x18000f871  mov     rax, [rdi+18h]
0x18000f875  mov     [rbx+18h], rax
0x18000f879  mov     eax, [rdi+10h]
0x18000f87c  mov     [rbx+10h], eax
0x18000f87f  mov     [rcx+28h], rbx
0x18000f883  mov     rax, [rbx+18h]
0x18000f887  mov     [rax+28h], rbx
0x18000f88b  cmp     [rsi], rdi
0x18000f88e  jnz     short loc_18000F893
0x18000f890  mov     [rsi], rbx
0x18000f893  mov     rdx, [rsi]
0x18000f896  test    rdx, rdx
0x18000f899  jz      short loc_18000F8A7
0x18000f89b  add     rdx, 28h ; '('
0x18000f89f  mov     rcx, rsi
0x18000f8a2  call    ?SetNil@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode * *)
0x18000f8a7  mov     rdx, rdi
0x18000f8aa  mov     rcx, rsi
0x18000f8ad  call    ?FreeNode@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::FreeNode(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000f8b2  mov     al, 1
0x18000f8b4  mov     rbx, [rsp+28h+arg_0]
0x18000f8b9  mov     rsi, [rsp+28h+arg_8]
0x18000f8be  add     rsp, 20h
0x18000f8c2  pop     rdi
0x18000f8c3  retn
```
