# ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::NewNode(void *,SmartPtr<CVolumeTrackingDescriptor> const &)

- ea: `0x18000bff8`
- end: `0x18000c123`
- name: `?NewNode@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAXAEBV?$SmartPtr@VCVolumeTrackingDescriptor@@@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000fb5c`

## callees

- `0x18000b48c`
- `0x18000bc04`
- `0x18000bff8`
- `0x18000f0b8`

## import_xrefs

- `msvcrt!malloc` at `0x18000c021`
- `msvcrt!malloc` at `0x18000c021`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::NewNode(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  _OWORD *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rcx
  struct ATL::CAtlPlex *v9; // rdx
  __int64 v10; // rcx
  char *i; // rdx
  __int64 v12; // rsi
  __int64 v13; // rax

  if ( !*(_QWORD *)(a1 + 16) )
  {
    if ( !*(_QWORD *)(a1 + 40) )
    {
      v6 = malloc(0x30u);
      *(_QWORD *)(a1 + 40) = v6;
      if ( !v6 )
        goto LABEL_6;
      *v6 = 0;
      v6[1] = 0;
      v6[2] = 0;
      *(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) = 1;
      *(_QWORD *)(*(_QWORD *)(a1 + 40) + 32LL) = *(_QWORD *)(a1 + 40);
      v7 = *(_QWORD *)(a1 + 40);
      v8 = *(_QWORD *)(v7 + 32);
      *(_QWORD *)(v7 + 24) = v8;
      *(_QWORD *)(*(_QWORD *)(a1 + 40) + 40LL) = v8;
      *(_QWORD *)a1 = *(_QWORD *)(a1 + 40);
    }
    v9 = ATL::CAtlPlex::Create((struct ATL::CAtlPlex **)(a1 + 24), *(_QWORD *)(a1 + 32));
    if ( !v9 )
LABEL_6:
      ATL::AtlThrowImpl(-2147024882);
    v10 = *(_QWORD *)(a1 + 32);
    for ( i = (char *)v9 + 48 * v10 - 40; --v10 >= 0; i -= 48 )
    {
      *((_QWORD *)i + 3) = *(_QWORD *)(a1 + 16);
      *(_QWORD *)(a1 + 16) = i;
    }
  }
  v12 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)v12 = a2;
  v13 = *a3;
  *(_QWORD *)(v12 + 8) = *a3;
  if ( v13 )
    ++*(_DWORD *)(v13 + 8);
  *(_DWORD *)(v12 + 16) = 1;
  *(_QWORD *)(v12 + 40) = 0;
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
  *(_DWORD *)(v12 + 16) = 0;
  ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(
    a1,
    v12 + 24);
  ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(
    a1,
    v12 + 32);
  ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(
    a1,
    v12 + 40);
  ++*(_QWORD *)(a1 + 8);
  return v12;
}

```

## disassembly

```asm
0x18000bff8  push    rbx
0x18000bffa  push    rbp
0x18000bffb  push    rsi
0x18000bffc  push    rdi
0x18000bffd  sub     rsp, 28h
0x18000c001  cmp     qword ptr [rcx+10h], 0
0x18000c006  mov     rbx, r8
0x18000c009  mov     rbp, rdx
0x18000c00c  mov     rdi, rcx
0x18000c00f  jnz     loc_18000C0B7
0x18000c015  cmp     qword ptr [rcx+28h], 0
0x18000c01a  jnz     short loc_18000C06C
0x18000c01c  mov     ecx, 30h ; '0'; Size
0x18000c021  call    cs:__imp_malloc
0x18000c027  mov     [rdi+28h], rax
0x18000c02b  test    rax, rax
0x18000c02e  jz      short loc_18000C081
0x18000c030  xorps   xmm0, xmm0
0x18000c033  movups  xmmword ptr [rax], xmm0
0x18000c036  movups  xmmword ptr [rax+10h], xmm0
0x18000c03a  movups  xmmword ptr [rax+20h], xmm0
0x18000c03e  mov     rax, [rdi+28h]
0x18000c042  mov     dword ptr [rax+10h], 1
0x18000c049  mov     rax, [rdi+28h]
0x18000c04d  mov     [rax+20h], rax
0x18000c051  mov     rax, [rdi+28h]
0x18000c055  mov     rcx, [rax+20h]
0x18000c059  mov     [rax+18h], rcx
0x18000c05d  mov     rax, [rdi+28h]
0x18000c061  mov     [rax+28h], rcx
0x18000c065  mov     rax, [rdi+28h]
0x18000c069  mov     [rdi], rax
0x18000c06c  mov     rdx, [rdi+20h]; unsigned __int64
0x18000c070  lea     rcx, [rdi+18h]; struct ATL::CAtlPlex **
0x18000c074  call    ?Create@CAtlPlex@ATL@@SAPEAU12@AEAPEAU12@_K1@Z; ATL::CAtlPlex::Create(ATL::CAtlPlex * &,unsigned __int64,unsigned __int64)
0x18000c079  mov     rdx, rax
0x18000c07c  test    rax, rax
0x18000c07f  jnz     short loc_18000C08C
0x18000c081  mov     ecx, 8007000Eh; int
0x18000c086  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c08c  mov     rcx, [rdi+20h]
0x18000c090  lea     rax, [rcx+rcx*2]
0x18000c094  shl     rax, 4
0x18000c098  add     rax, 0FFFFFFFFFFFFFFD8h
0x18000c09c  add     rdx, rax
0x18000c09f  jmp     short loc_18000C0B1
0x18000c0a1  mov     rax, [rdi+10h]
0x18000c0a5  mov     [rdx+18h], rax
0x18000c0a9  mov     [rdi+10h], rdx
0x18000c0ad  sub     rdx, 30h ; '0'
0x18000c0b1  sub     rcx, 1
0x18000c0b5  jns     short loc_18000C0A1
0x18000c0b7  mov     rsi, [rdi+10h]
0x18000c0bb  mov     [rsi], rbp
0x18000c0be  mov     rax, [rbx]
0x18000c0c1  mov     [rsi+8], rax
0x18000c0c5  test    rax, rax
0x18000c0c8  jz      short loc_18000C0CD
0x18000c0ca  inc     dword ptr [rax+8]
0x18000c0cd  mov     dword ptr [rsi+10h], 1
0x18000c0d4  lea     rdx, [rsi+18h]
0x18000c0d8  mov     qword ptr [rsi+28h], 0
0x18000c0e0  mov     rcx, [rdi+10h]
0x18000c0e4  mov     r8, [rcx+18h]
0x18000c0e8  mov     rcx, rdi
0x18000c0eb  mov     [rdi+10h], r8
0x18000c0ef  mov     dword ptr [rsi+10h], 0
0x18000c0f6  call    ?SetNil@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode * *)
0x18000c0fb  lea     rdx, [rsi+20h]
0x18000c0ff  mov     rcx, rdi
0x18000c102  call    ?SetNil@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode * *)
0x18000c107  lea     rdx, [rsi+28h]
0x18000c10b  mov     rcx, rdi
0x18000c10e  call    ?SetNil@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode * *)
0x18000c113  inc     qword ptr [rdi+8]
0x18000c117  mov     rax, rsi
0x18000c11a  add     rsp, 28h
0x18000c11e  pop     rdi
0x18000c11f  pop     rsi
0x18000c120  pop     rbp
0x18000c121  pop     rbx
0x18000c122  retn
```
