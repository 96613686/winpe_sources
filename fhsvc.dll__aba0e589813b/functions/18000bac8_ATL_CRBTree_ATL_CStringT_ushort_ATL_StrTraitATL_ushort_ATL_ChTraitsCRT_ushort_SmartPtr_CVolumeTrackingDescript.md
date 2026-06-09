# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::NewNode(ushort const *,SmartPtr<CVolumeTrackingDescriptor> const &)

- ea: `0x18000bac8`
- end: `0x18000bbfb`
- name: `?NewNode@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAPEAVCNode@12@PEBGAEBV?$SmartPtr@VCVolumeTrackingDescriptor@@@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f4e4`

## callees

- `0x18000b48c`
- `0x18000bac8`
- `0x18000bc04`
- `0x18000bc2c`
- `0x18000f0b8`

## import_xrefs

- `msvcrt!malloc` at `0x18000baf1`
- `msvcrt!malloc` at `0x18000baf1`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::NewNode(
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
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v12,
    a2);
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
0x18000bac8  push    rbx
0x18000baca  push    rbp
0x18000bacb  push    rsi
0x18000bacc  push    rdi
0x18000bacd  sub     rsp, 28h
0x18000bad1  cmp     qword ptr [rcx+10h], 0
0x18000bad6  mov     rbx, r8
0x18000bad9  mov     rbp, rdx
0x18000badc  mov     rdi, rcx
0x18000badf  jnz     loc_18000BB87
0x18000bae5  cmp     qword ptr [rcx+28h], 0
0x18000baea  jnz     short loc_18000BB3C
0x18000baec  mov     ecx, 30h ; '0'; Size
0x18000baf1  call    cs:__imp_malloc
0x18000baf7  mov     [rdi+28h], rax
0x18000bafb  test    rax, rax
0x18000bafe  jz      short loc_18000BB51
0x18000bb00  xorps   xmm0, xmm0
0x18000bb03  movups  xmmword ptr [rax], xmm0
0x18000bb06  movups  xmmword ptr [rax+10h], xmm0
0x18000bb0a  movups  xmmword ptr [rax+20h], xmm0
0x18000bb0e  mov     rax, [rdi+28h]
0x18000bb12  mov     dword ptr [rax+10h], 1
0x18000bb19  mov     rax, [rdi+28h]
0x18000bb1d  mov     [rax+20h], rax
0x18000bb21  mov     rax, [rdi+28h]
0x18000bb25  mov     rcx, [rax+20h]
0x18000bb29  mov     [rax+18h], rcx
0x18000bb2d  mov     rax, [rdi+28h]
0x18000bb31  mov     [rax+28h], rcx
0x18000bb35  mov     rax, [rdi+28h]
0x18000bb39  mov     [rdi], rax
0x18000bb3c  mov     rdx, [rdi+20h]; unsigned __int64
0x18000bb40  lea     rcx, [rdi+18h]; struct ATL::CAtlPlex **
0x18000bb44  call    ?Create@CAtlPlex@ATL@@SAPEAU12@AEAPEAU12@_K1@Z; ATL::CAtlPlex::Create(ATL::CAtlPlex * &,unsigned __int64,unsigned __int64)
0x18000bb49  mov     rdx, rax
0x18000bb4c  test    rax, rax
0x18000bb4f  jnz     short loc_18000BB5C
0x18000bb51  mov     ecx, 8007000Eh; int
0x18000bb56  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000bb5c  mov     rcx, [rdi+20h]
0x18000bb60  lea     rax, [rcx+rcx*2]
0x18000bb64  shl     rax, 4
0x18000bb68  add     rax, 0FFFFFFFFFFFFFFD8h
0x18000bb6c  add     rdx, rax
0x18000bb6f  jmp     short loc_18000BB81
0x18000bb71  mov     rax, [rdi+10h]
0x18000bb75  mov     [rdx+18h], rax
0x18000bb79  mov     [rdi+10h], rdx
0x18000bb7d  sub     rdx, 30h ; '0'
0x18000bb81  sub     rcx, 1
0x18000bb85  jns     short loc_18000BB71
0x18000bb87  mov     rsi, [rdi+10h]
0x18000bb8b  mov     rdx, rbp
0x18000bb8e  mov     rcx, rsi
0x18000bb91  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000bb96  mov     rax, [rbx]
0x18000bb99  mov     [rsi+8], rax
0x18000bb9d  test    rax, rax
0x18000bba0  jz      short loc_18000BBA5
0x18000bba2  inc     dword ptr [rax+8]
0x18000bba5  mov     dword ptr [rsi+10h], 1
0x18000bbac  lea     rdx, [rsi+18h]
0x18000bbb0  mov     qword ptr [rsi+28h], 0
0x18000bbb8  mov     rcx, [rdi+10h]
0x18000bbbc  mov     r8, [rcx+18h]
0x18000bbc0  mov     rcx, rdi
0x18000bbc3  mov     [rdi+10h], r8
0x18000bbc7  mov     dword ptr [rsi+10h], 0
0x18000bbce  call    ?SetNil@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode * *)
0x18000bbd3  lea     rdx, [rsi+20h]
0x18000bbd7  mov     rcx, rdi
0x18000bbda  call    ?SetNil@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode * *)
0x18000bbdf  lea     rdx, [rsi+28h]
0x18000bbe3  mov     rcx, rdi
0x18000bbe6  call    ?SetNil@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetNil(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode * *)
0x18000bbeb  inc     qword ptr [rdi+8]
0x18000bbef  mov     rax, rsi
0x18000bbf2  add     rsp, 28h
0x18000bbf6  pop     rdi
0x18000bbf7  pop     rsi
0x18000bbf8  pop     rbp
0x18000bbf9  pop     rbx
0x18000bbfa  retn
```
