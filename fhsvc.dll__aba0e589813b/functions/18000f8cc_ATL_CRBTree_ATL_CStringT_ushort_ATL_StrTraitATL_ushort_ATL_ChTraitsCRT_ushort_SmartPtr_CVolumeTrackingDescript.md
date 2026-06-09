# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDelete(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)

- ea: `0x18000f8cc`
- end: `0x18000f9d4`
- name: `?RBDelete@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAA_NPEAVCNode@12@@Z`
- size: `264`
- prototype: `char __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ac48`

## callees

- `0x18000b6f0`
- `0x18000bc04`
- `0x18000f8cc`
- `0x18000f9dc`

## pseudocode

```c
char __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDelete(
        _QWORD *a1,
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
      *a1 + 40LL);
  ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::FreeNode(
    (__int64)a1,
    (_QWORD *)a2);
  return 1;
}

```

## disassembly

```asm
0x18000f8cc  mov     [rsp+arg_0], rbx
0x18000f8d1  mov     [rsp+arg_8], rsi
0x18000f8d6  push    rdi
0x18000f8d7  sub     rsp, 20h
0x18000f8db  mov     rdi, rdx
0x18000f8de  mov     rsi, rcx
0x18000f8e1  test    rdx, rdx
0x18000f8e4  jnz     short loc_18000F8ED
0x18000f8e6  xor     al, al
0x18000f8e8  jmp     loc_18000F9C4
0x18000f8ed  mov     rax, [rcx+28h]
0x18000f8f1  cmp     [rdx+18h], rax
0x18000f8f5  jz      short loc_18000F913
0x18000f8f7  mov     rbx, [rdx+20h]
0x18000f8fb  cmp     rbx, rax
0x18000f8fe  jz      short loc_18000F913
0x18000f900  test    rbx, rbx
0x18000f903  jz      short loc_18000F916
0x18000f905  mov     rcx, [rbx+18h]
0x18000f909  cmp     rcx, rax
0x18000f90c  jz      short loc_18000F916
0x18000f90e  mov     rbx, rcx
0x18000f911  jmp     short loc_18000F905
0x18000f913  mov     rbx, rdi
0x18000f916  mov     rdx, [rbx+18h]
0x18000f91a  cmp     rdx, rax
0x18000f91d  jnz     short loc_18000F923
0x18000f91f  mov     rdx, [rbx+20h]
0x18000f923  mov     rax, [rbx+28h]
0x18000f927  mov     [rdx+28h], rax
0x18000f92b  mov     rax, [rbx+28h]
0x18000f92f  cmp     rax, [rsi+28h]
0x18000f933  jnz     short loc_18000F93A
0x18000f935  mov     [rsi], rdx
0x18000f938  jmp     short loc_18000F94A
0x18000f93a  cmp     rbx, [rax+18h]
0x18000f93e  jnz     short loc_18000F946
0x18000f940  mov     [rax+18h], rdx
0x18000f944  jmp     short loc_18000F94A
0x18000f946  mov     [rax+20h], rdx
0x18000f94a  cmp     dword ptr [rbx+10h], 1
0x18000f94e  jnz     short loc_18000F958
0x18000f950  mov     rcx, rsi
0x18000f953  call    ?RBDeleteFixup@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDeleteFixup(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000f958  cmp     rbx, rdi
0x18000f95b  jz      short loc_18000F9A3
0x18000f95d  mov     rax, [rdi+28h]
0x18000f961  mov     [rbx+28h], rax
0x18000f965  mov     rax, [rdi+28h]
0x18000f969  cmp     [rax+18h], rdi
0x18000f96d  jnz     short loc_18000F975
0x18000f96f  mov     [rax+18h], rbx
0x18000f973  jmp     short loc_18000F979
0x18000f975  mov     [rax+20h], rbx
0x18000f979  mov     rcx, [rdi+20h]
0x18000f97d  mov     [rbx+20h], rcx
0x18000f981  mov     rax, [rdi+18h]
0x18000f985  mov     [rbx+18h], rax
0x18000f989  mov     eax, [rdi+10h]
0x18000f98c  mov     [rbx+10h], eax
0x18000f98f  mov     [rcx+28h], rbx
0x18000f993  mov     rax, [rbx+18h]
0x18000f997  mov     [rax+28h], rbx
0x18000f99b  cmp     [rsi], rdi
0x18000f99e  jnz     short loc_18000F9A3
0x18000f9a0  mov     [rsi], rbx
0x18000f9a3  mov     rdx, [rsi]
0x18000f9a6  test    rdx, rdx
0x18000f9a9  jz      short loc_18000F9B7
0x18000f9ab  add     rdx, 28h ; '('
0x18000f9af  mov     rcx, rsi
0x18000f9b2  call    ?SetNil@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode * *)
0x18000f9b7  mov     rdx, rdi
0x18000f9ba  mov     rcx, rsi
0x18000f9bd  call    ?FreeNode@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::FreeNode(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000f9c2  mov     al, 1
0x18000f9c4  mov     rbx, [rsp+28h+arg_0]
0x18000f9c9  mov     rsi, [rsp+28h+arg_8]
0x18000f9ce  add     rsp, 20h
0x18000f9d2  pop     rdi
0x18000f9d3  retn
```
