# ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDelete(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)

- ea: `0x18000f6b8`
- end: `0x18000f7c0`
- name: `?RBDelete@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAA_NPEAVCNode@12@@Z`
- size: `264`
- prototype: `char __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ac48`

## callees

- `0x18000b65c`
- `0x18000bc04`
- `0x18000f6b8`
- `0x18000f9dc`

## pseudocode

```c
char __fastcall ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDelete(
        __int64 *a1,
        __int64 a2)
{
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx

  if ( !a2 )
    return 0;
  v5 = a1[5];
  if ( *(_QWORD *)(a2 + 24) == v5 || (v6 = *(_QWORD *)(a2 + 32), v6 == v5) )
  {
    v6 = a2;
  }
  else if ( v6 )
  {
    while ( *(_QWORD *)(v6 + 24) != v5 )
      v6 = *(_QWORD *)(v6 + 24);
  }
  v7 = *(_QWORD *)(v6 + 24);
  if ( v7 == v5 )
    v7 = *(_QWORD *)(v6 + 32);
  *(_QWORD *)(v7 + 40) = *(_QWORD *)(v6 + 40);
  v8 = *(_QWORD *)(v6 + 40);
  if ( v8 == a1[5] )
  {
    *a1 = v7;
  }
  else if ( v6 == *(_QWORD *)(v8 + 24) )
  {
    *(_QWORD *)(v8 + 24) = v7;
  }
  else
  {
    *(_QWORD *)(v8 + 32) = v7;
  }
  if ( *(_DWORD *)(v6 + 16) == 1 )
    ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDeleteFixup(a1);
  if ( v6 != a2 )
  {
    *(_QWORD *)(v6 + 40) = *(_QWORD *)(a2 + 40);
    v9 = *(_QWORD *)(a2 + 40);
    if ( *(_QWORD *)(v9 + 24) == a2 )
      *(_QWORD *)(v9 + 24) = v6;
    else
      *(_QWORD *)(v9 + 32) = v6;
    v10 = *(_QWORD *)(a2 + 32);
    *(_QWORD *)(v6 + 32) = v10;
    *(_QWORD *)(v6 + 24) = *(_QWORD *)(a2 + 24);
    *(_DWORD *)(v6 + 16) = *(_DWORD *)(a2 + 16);
    *(_QWORD *)(v10 + 40) = v6;
    *(_QWORD *)(*(_QWORD *)(v6 + 24) + 40LL) = v6;
    if ( *a1 == a2 )
      *a1 = v6;
  }
  if ( *a1 )
    ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(
      a1,
      *a1 + 40);
  ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::FreeNode(
    (__int64)a1,
    a2);
  return 1;
}

```

## disassembly

```asm
0x18000f6b8  mov     [rsp+arg_0], rbx
0x18000f6bd  mov     [rsp+arg_8], rsi
0x18000f6c2  push    rdi
0x18000f6c3  sub     rsp, 20h
0x18000f6c7  mov     rdi, rdx
0x18000f6ca  mov     rsi, rcx
0x18000f6cd  test    rdx, rdx
0x18000f6d0  jnz     short loc_18000F6D9
0x18000f6d2  xor     al, al
0x18000f6d4  jmp     loc_18000F7B0
0x18000f6d9  mov     rax, [rcx+28h]
0x18000f6dd  cmp     [rdx+18h], rax
0x18000f6e1  jz      short loc_18000F6FF
0x18000f6e3  mov     rbx, [rdx+20h]
0x18000f6e7  cmp     rbx, rax
0x18000f6ea  jz      short loc_18000F6FF
0x18000f6ec  test    rbx, rbx
0x18000f6ef  jz      short loc_18000F702
0x18000f6f1  mov     rcx, [rbx+18h]
0x18000f6f5  cmp     rcx, rax
0x18000f6f8  jz      short loc_18000F702
0x18000f6fa  mov     rbx, rcx
0x18000f6fd  jmp     short loc_18000F6F1
0x18000f6ff  mov     rbx, rdi
0x18000f702  mov     rdx, [rbx+18h]
0x18000f706  cmp     rdx, rax
0x18000f709  jnz     short loc_18000F70F
0x18000f70b  mov     rdx, [rbx+20h]
0x18000f70f  mov     rax, [rbx+28h]
0x18000f713  mov     [rdx+28h], rax
0x18000f717  mov     rax, [rbx+28h]
0x18000f71b  cmp     rax, [rsi+28h]
0x18000f71f  jnz     short loc_18000F726
0x18000f721  mov     [rsi], rdx
0x18000f724  jmp     short loc_18000F736
0x18000f726  cmp     rbx, [rax+18h]
0x18000f72a  jnz     short loc_18000F732
0x18000f72c  mov     [rax+18h], rdx
0x18000f730  jmp     short loc_18000F736
0x18000f732  mov     [rax+20h], rdx
0x18000f736  cmp     dword ptr [rbx+10h], 1
0x18000f73a  jnz     short loc_18000F744
0x18000f73c  mov     rcx, rsi
0x18000f73f  call    ?RBDeleteFixup@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDeleteFixup(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000f744  cmp     rbx, rdi
0x18000f747  jz      short loc_18000F78F
0x18000f749  mov     rax, [rdi+28h]
0x18000f74d  mov     [rbx+28h], rax
0x18000f751  mov     rax, [rdi+28h]
0x18000f755  cmp     [rax+18h], rdi
0x18000f759  jnz     short loc_18000F761
0x18000f75b  mov     [rax+18h], rbx
0x18000f75f  jmp     short loc_18000F765
0x18000f761  mov     [rax+20h], rbx
0x18000f765  mov     rcx, [rdi+20h]
0x18000f769  mov     [rbx+20h], rcx
0x18000f76d  mov     rax, [rdi+18h]
0x18000f771  mov     [rbx+18h], rax
0x18000f775  mov     eax, [rdi+10h]
0x18000f778  mov     [rbx+10h], eax
0x18000f77b  mov     [rcx+28h], rbx
0x18000f77f  mov     rax, [rbx+18h]
0x18000f783  mov     [rax+28h], rbx
0x18000f787  cmp     [rsi], rdi
0x18000f78a  jnz     short loc_18000F78F
0x18000f78c  mov     [rsi], rbx
0x18000f78f  mov     rdx, [rsi]
0x18000f792  test    rdx, rdx
0x18000f795  jz      short loc_18000F7A3
0x18000f797  add     rdx, 28h ; '('
0x18000f79b  mov     rcx, rsi
0x18000f79e  call    ?SetNil@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode * *)
0x18000f7a3  mov     rdx, rdi
0x18000f7a6  mov     rcx, rsi
0x18000f7a9  call    ?FreeNode@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::FreeNode(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000f7ae  mov     al, 1
0x18000f7b0  mov     rbx, [rsp+28h+arg_0]
0x18000f7b5  mov     rsi, [rsp+28h+arg_8]
0x18000f7ba  add     rsp, 20h
0x18000f7be  pop     rdi
0x18000f7bf  retn
```
