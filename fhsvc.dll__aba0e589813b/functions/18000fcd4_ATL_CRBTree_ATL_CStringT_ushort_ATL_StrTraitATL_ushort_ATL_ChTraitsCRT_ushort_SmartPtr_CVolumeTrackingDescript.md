# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBInsert(ushort const *,SmartPtr<CVolumeTrackingDescriptor> const &)

- ea: `0x18000fcd4`
- end: `0x18000fdef`
- name: `?RBInsert@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@IEAAPEAVCNode@12@PEBGAEBV?$SmartPtr@VCVolumeTrackingDescriptor@@@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(__int64 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a360`
- `0x18000aa08`

## callees

- `0x18000bc04`
- `0x18000f4e4`
- `0x18000f588`
- `0x18000fcd4`
- `0x18000fdf8`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBInsert(
        __int64 *a1,
        unsigned __int16 *a2)
{
  __int64 inserted; // rax
  int v4; // r10d
  __int64 v5; // rdi
  __int64 v6; // r8
  int v7; // r11d
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax

  inserted = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::InsertImpl(
               a1,
               a2);
  v4 = 0;
  v5 = inserted;
  *(_DWORD *)(inserted + 16) = 0;
  v6 = *a1;
  v7 = 1;
  if ( inserted != *a1 )
  {
    v8 = inserted;
    do
    {
      v9 = *(_QWORD *)(v8 + 40);
      if ( *(_DWORD *)(v9 + 16) != v4 )
        break;
      v10 = *(_QWORD *)(v9 + 40);
      v11 = *(_QWORD *)(v10 + 24);
      if ( v9 == v11 )
      {
        v11 = *(_QWORD *)(v10 + 32);
        if ( !v11 || *(_DWORD *)(v11 + 16) != v4 )
        {
          if ( v8 == *(_QWORD *)(v9 + 32) )
            ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(
              a1,
              v9);
          *(_DWORD *)(*(_QWORD *)(v8 + 40) + 16LL) = v7;
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 40) + 40LL) + 16LL) = v4;
          ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(
            a1,
            *(_QWORD *)(*(_QWORD *)(v8 + 40) + 40LL));
          goto LABEL_16;
        }
      }
      else if ( !v11 || *(_DWORD *)(v11 + 16) != v4 )
      {
        if ( v8 == *(_QWORD *)(v9 + 24) )
          ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(
            a1,
            v9);
        *(_DWORD *)(*(_QWORD *)(v8 + 40) + 16LL) = v7;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 40) + 40LL) + 16LL) = v4;
        ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(
          a1,
          *(_QWORD *)(*(_QWORD *)(v8 + 40) + 40LL));
        goto LABEL_16;
      }
      *(_DWORD *)(v9 + 16) = v7;
      *(_DWORD *)(v11 + 16) = v7;
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 40) + 40LL) + 16LL) = v4;
      v8 = *(_QWORD *)(*(_QWORD *)(v8 + 40) + 40LL);
LABEL_16:
      v6 = *a1;
    }
    while ( v8 != *a1 );
  }
  *(_DWORD *)(v6 + 16) = v7;
  ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(
    a1,
    *a1 + 40);
  return v5;
}

```

## disassembly

```asm
0x18000fcd4  mov     [rsp+arg_0], rbx
0x18000fcd9  push    rdi
0x18000fcda  sub     rsp, 20h
0x18000fcde  mov     rbx, rcx
0x18000fce1  call    ?InsertImpl@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAPEAVCNode@12@PEBGAEBV?$SmartPtr@VCVolumeTrackingDescriptor@@@@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::InsertImpl(ushort const *,SmartPtr<CVolumeTrackingDescriptor> const &)
0x18000fce6  xor     r10d, r10d
0x18000fce9  mov     rdi, rax
0x18000fcec  mov     [rax+10h], r10d
0x18000fcf0  mov     r8, [rbx]
0x18000fcf3  lea     r11d, [r10+1]
0x18000fcf7  cmp     rax, r8
0x18000fcfa  jz      loc_18000FDCE
0x18000fd00  mov     r9, rax
0x18000fd03  mov     rdx, [r9+28h]
0x18000fd07  cmp     [rdx+10h], r10d
0x18000fd0b  jnz     loc_18000FDCE
0x18000fd11  mov     rcx, [rdx+28h]
0x18000fd15  mov     rax, [rcx+18h]
0x18000fd19  cmp     rdx, rax
0x18000fd1c  jnz     short loc_18000FD64
0x18000fd1e  mov     rax, [rcx+20h]
0x18000fd22  test    rax, rax
0x18000fd25  jz      short loc_18000FD2D
0x18000fd27  cmp     [rax+10h], r10d
0x18000fd2b  jz      short loc_18000FD6F
0x18000fd2d  cmp     r9, [rdx+20h]
0x18000fd31  jnz     short loc_18000FD3E
0x18000fd33  mov     rcx, rbx
0x18000fd36  mov     r9, rdx
0x18000fd39  call    ?LeftRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000fd3e  mov     rax, [r9+28h]
0x18000fd42  mov     [rax+10h], r11d
0x18000fd46  mov     rax, [r9+28h]
0x18000fd4a  mov     rcx, [rax+28h]
0x18000fd4e  mov     [rcx+10h], r10d
0x18000fd52  mov     rcx, rbx
0x18000fd55  mov     rdx, [r9+28h]
0x18000fd59  mov     rdx, [rdx+28h]
0x18000fd5d  call    ?RightRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000fd62  jmp     short loc_18000FDC2
0x18000fd64  test    rax, rax
0x18000fd67  jz      short loc_18000FD8D
0x18000fd69  cmp     [rax+10h], r10d
0x18000fd6d  jnz     short loc_18000FD8D
0x18000fd6f  mov     [rdx+10h], r11d
0x18000fd73  mov     [rax+10h], r11d
0x18000fd77  mov     rax, [r9+28h]
0x18000fd7b  mov     rcx, [rax+28h]
0x18000fd7f  mov     [rcx+10h], r10d
0x18000fd83  mov     rax, [r9+28h]
0x18000fd87  mov     r9, [rax+28h]
0x18000fd8b  jmp     short loc_18000FDC2
0x18000fd8d  cmp     r9, [rdx+18h]
0x18000fd91  jnz     short loc_18000FD9E
0x18000fd93  mov     rcx, rbx
0x18000fd96  mov     r9, rdx
0x18000fd99  call    ?RightRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000fd9e  mov     rax, [r9+28h]
0x18000fda2  mov     [rax+10h], r11d
0x18000fda6  mov     rax, [r9+28h]
0x18000fdaa  mov     rcx, [rax+28h]
0x18000fdae  mov     [rcx+10h], r10d
0x18000fdb2  mov     rcx, rbx
0x18000fdb5  mov     rdx, [r9+28h]
0x18000fdb9  mov     rdx, [rdx+28h]
0x18000fdbd  call    ?LeftRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000fdc2  mov     r8, [rbx]
0x18000fdc5  cmp     r9, r8
0x18000fdc8  jnz     loc_18000FD03
0x18000fdce  mov     [r8+10h], r11d
0x18000fdd2  mov     rcx, rbx
0x18000fdd5  mov     rdx, [rbx]
0x18000fdd8  add     rdx, 28h ; '('
0x18000fddc  call    ?SetNil@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode * *)
0x18000fde1  mov     rbx, [rsp+28h+arg_0]
0x18000fde6  mov     rax, rdi
0x18000fde9  add     rsp, 20h
0x18000fded  pop     rdi
0x18000fdee  retn
```
