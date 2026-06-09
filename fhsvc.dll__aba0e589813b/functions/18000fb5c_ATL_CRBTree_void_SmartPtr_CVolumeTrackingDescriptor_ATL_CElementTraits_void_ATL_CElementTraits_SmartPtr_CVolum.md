# ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBInsert(void *,SmartPtr<CVolumeTrackingDescriptor> const &)

- ea: `0x18000fb5c`
- end: `0x18000fccb`
- name: `?RBInsert@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@IEAAPEAVCNode@12@PEAXAEBV?$SmartPtr@VCVolumeTrackingDescriptor@@@@@Z`
- size: `367`
- prototype: `__int64 __fastcall(unsigned __int64 **, unsigned __int64, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fe58`

## callees

- `0x18000bc04`
- `0x18000bff8`
- `0x18000f588`
- `0x18000fb5c`
- `0x18000fdf8`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBInsert(
        unsigned __int64 **a1,
        unsigned __int64 a2,
        __int64 *a3)
{
  __int64 v5; // rax
  unsigned __int64 *v6; // rcx
  int v7; // r10d
  __int64 v8; // rdi
  unsigned __int64 *v9; // rax
  __int64 v10; // rdx
  int v11; // r11d
  unsigned __int64 *v12; // rax
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax

  v5 = ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::NewNode(
         (__int64)a1,
         a2,
         a3);
  v6 = *a1;
  v7 = 0;
  v8 = v5;
  v9 = 0;
  while ( v6 != a1[5] )
  {
    v9 = v6;
    if ( a2 < *v6 || (v10 = 4, a2 == *v6) )
      v10 = 3;
    v6 = (unsigned __int64 *)v6[v10];
  }
  *(_QWORD *)(v8 + 40) = v9;
  if ( v9 )
  {
    if ( a2 <= *v9 )
      v9[3] = v8;
    else
      v9[4] = v8;
  }
  else
  {
    *a1 = (unsigned __int64 *)v8;
  }
  *(_DWORD *)(v8 + 16) = 0;
  v11 = 1;
  v12 = *a1;
  if ( (unsigned __int64 *)v8 != *a1 )
  {
    v13 = v8;
    do
    {
      v14 = *(_QWORD *)(v13 + 40);
      if ( *(_DWORD *)(v14 + 16) != v7 )
        break;
      v15 = *(_QWORD *)(v14 + 40);
      v16 = *(_QWORD *)(v15 + 24);
      if ( v14 == v16 )
      {
        v16 = *(_QWORD *)(v15 + 32);
        if ( !v16 || *(_DWORD *)(v16 + 16) != v7 )
        {
          if ( v13 == *(_QWORD *)(v14 + 32) )
            ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(
              a1,
              v14);
          *(_DWORD *)(*(_QWORD *)(v13 + 40) + 16LL) = v11;
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 40) + 40LL) + 16LL) = v7;
          ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(
            a1,
            *(_QWORD *)(*(_QWORD *)(v13 + 40) + 40LL));
          goto LABEL_27;
        }
      }
      else if ( !v16 || *(_DWORD *)(v16 + 16) != v7 )
      {
        if ( v13 == *(_QWORD *)(v14 + 24) )
          ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(
            a1,
            v14);
        *(_DWORD *)(*(_QWORD *)(v13 + 40) + 16LL) = v11;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 40) + 40LL) + 16LL) = v7;
        ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(
          a1,
          *(_QWORD *)(*(_QWORD *)(v13 + 40) + 40LL));
        goto LABEL_27;
      }
      *(_DWORD *)(v14 + 16) = v11;
      *(_DWORD *)(v16 + 16) = v11;
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 40) + 40LL) + 16LL) = v7;
      v13 = *(_QWORD *)(*(_QWORD *)(v13 + 40) + 40LL);
LABEL_27:
      v12 = *a1;
    }
    while ( (unsigned __int64 *)v13 != *a1 );
  }
  *((_DWORD *)v12 + 4) = v11;
  ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(
    a1,
    *a1 + 5);
  return v8;
}

```

## disassembly

```asm
0x18000fb5c  mov     [rsp+arg_0], rbx
0x18000fb61  mov     [rsp+arg_8], rsi
0x18000fb66  push    rdi
0x18000fb67  sub     rsp, 20h
0x18000fb6b  mov     rsi, rdx
0x18000fb6e  mov     rbx, rcx
0x18000fb71  call    ?NewNode@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAXAEBV?$SmartPtr@VCVolumeTrackingDescriptor@@@@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::NewNode(void *,SmartPtr<CVolumeTrackingDescriptor> const &)
0x18000fb76  mov     rcx, [rbx]
0x18000fb79  xor     r10d, r10d
0x18000fb7c  mov     rdi, rax
0x18000fb7f  mov     eax, r10d
0x18000fb82  cmp     rcx, [rbx+28h]
0x18000fb86  jz      short loc_18000FBA2
0x18000fb88  mov     rax, rcx
0x18000fb8b  cmp     rsi, [rcx]
0x18000fb8e  jb      short loc_18000FB97
0x18000fb90  mov     edx, 20h ; ' '
0x18000fb95  jnz     short loc_18000FB9C
0x18000fb97  mov     edx, 18h
0x18000fb9c  mov     rcx, [rdx+rcx]
0x18000fba0  jmp     short loc_18000FB82
0x18000fba2  mov     [rdi+28h], rax
0x18000fba6  test    rax, rax
0x18000fba9  jnz     short loc_18000FBB0
0x18000fbab  mov     [rbx], rdi
0x18000fbae  jmp     short loc_18000FBC1
0x18000fbb0  cmp     rsi, [rax]
0x18000fbb3  jb      short loc_18000FBBD
0x18000fbb5  jz      short loc_18000FBBD
0x18000fbb7  mov     [rax+20h], rdi
0x18000fbbb  jmp     short loc_18000FBC1
0x18000fbbd  mov     [rax+18h], rdi
0x18000fbc1  mov     [rdi+10h], r10d
0x18000fbc5  mov     r11d, 1
0x18000fbcb  mov     rax, [rbx]
0x18000fbce  cmp     rdi, rax
0x18000fbd1  jz      loc_18000FCA5
0x18000fbd7  mov     r9, rdi
0x18000fbda  mov     rdx, [r9+28h]
0x18000fbde  cmp     [rdx+10h], r10d
0x18000fbe2  jnz     loc_18000FCA5
0x18000fbe8  mov     rcx, [rdx+28h]
0x18000fbec  mov     rax, [rcx+18h]
0x18000fbf0  cmp     rdx, rax
0x18000fbf3  jnz     short loc_18000FC3B
0x18000fbf5  mov     rax, [rcx+20h]
0x18000fbf9  test    rax, rax
0x18000fbfc  jz      short loc_18000FC04
0x18000fbfe  cmp     [rax+10h], r10d
0x18000fc02  jz      short loc_18000FC46
0x18000fc04  cmp     r9, [rdx+20h]
0x18000fc08  jnz     short loc_18000FC15
0x18000fc0a  mov     rcx, rbx
0x18000fc0d  mov     r9, rdx
0x18000fc10  call    ?LeftRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000fc15  mov     rax, [r9+28h]
0x18000fc19  mov     [rax+10h], r11d
0x18000fc1d  mov     rax, [r9+28h]
0x18000fc21  mov     rcx, [rax+28h]
0x18000fc25  mov     [rcx+10h], r10d
0x18000fc29  mov     rcx, rbx
0x18000fc2c  mov     rdx, [r9+28h]
0x18000fc30  mov     rdx, [rdx+28h]
0x18000fc34  call    ?RightRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000fc39  jmp     short loc_18000FC99
0x18000fc3b  test    rax, rax
0x18000fc3e  jz      short loc_18000FC64
0x18000fc40  cmp     [rax+10h], r10d
0x18000fc44  jnz     short loc_18000FC64
0x18000fc46  mov     [rdx+10h], r11d
0x18000fc4a  mov     [rax+10h], r11d
0x18000fc4e  mov     rax, [r9+28h]
0x18000fc52  mov     rcx, [rax+28h]
0x18000fc56  mov     [rcx+10h], r10d
0x18000fc5a  mov     rax, [r9+28h]
0x18000fc5e  mov     r9, [rax+28h]
0x18000fc62  jmp     short loc_18000FC99
0x18000fc64  cmp     r9, [rdx+18h]
0x18000fc68  jnz     short loc_18000FC75
0x18000fc6a  mov     rcx, rbx
0x18000fc6d  mov     r9, rdx
0x18000fc70  call    ?RightRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000fc75  mov     rax, [r9+28h]
0x18000fc79  mov     [rax+10h], r11d
0x18000fc7d  mov     rax, [r9+28h]
0x18000fc81  mov     rcx, [rax+28h]
0x18000fc85  mov     [rcx+10h], r10d
0x18000fc89  mov     rcx, rbx
0x18000fc8c  mov     rdx, [r9+28h]
0x18000fc90  mov     rdx, [rdx+28h]
0x18000fc94  call    ?LeftRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000fc99  mov     rax, [rbx]
0x18000fc9c  cmp     r9, rax
0x18000fc9f  jnz     loc_18000FBDA
0x18000fca5  mov     [rax+10h], r11d
0x18000fca9  mov     rcx, rbx
0x18000fcac  mov     rdx, [rbx]
0x18000fcaf  add     rdx, 28h ; '('
0x18000fcb3  call    ?SetNil@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode * *)
0x18000fcb8  mov     rbx, [rsp+28h+arg_0]
0x18000fcbd  mov     rax, rdi
0x18000fcc0  mov     rsi, [rsp+28h+arg_8]
0x18000fcc5  add     rsp, 20h
0x18000fcc9  pop     rdi
0x18000fcca  retn
```
