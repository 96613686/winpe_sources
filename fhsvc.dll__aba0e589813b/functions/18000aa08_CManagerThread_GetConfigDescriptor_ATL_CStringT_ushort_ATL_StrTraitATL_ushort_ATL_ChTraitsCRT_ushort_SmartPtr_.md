# CManagerThread::GetConfigDescriptor(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor> &,int)

- ea: `0x18000aa08`
- end: `0x18000ac0b`
- name: `?GetConfigDescriptor@CManagerThread@@AEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$SmartPtr@VCConfigDescriptor@@@@H@Z`
- size: `515`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD ***, int)`
- caller_count: `7`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800062b0`
- `0x1800065c0`
- `0x180009fd0`
- `0x18000a148`
- `0x18000a254`
- `0x18000efb4`
- `0x18000feb4`

## callees

- `0x1800011b0`
- `0x180006d38`
- `0x1800076a0`
- `0x180007800`
- `0x18000aa08`
- `0x18000ac14`
- `0x18000b8f0`
- `0x18000bdfc`
- `0x18000d0a8`
- `0x18000daf0`
- `0x18000ed14`
- `0x18000eefc`
- `0x18000fcd4`

## string_xrefs

- `0x18000abc3`: `ConfigDesc`

## pseudocode

```c
__int64 __fastcall CManagerThread::GetConfigDescriptor(__int64 a1, _QWORD *a2, _QWORD ***a3, int a4)
{
  int v4; // r11d
  _QWORD *v6; // rdi
  unsigned int v7; // esi
  _QWORD *v8; // r10
  _QWORD *v9; // rax
  unsigned __int16 *v10; // rcx
  int v11; // r8d
  int v12; // edx
  _QWORD *i; // rdx
  unsigned __int16 *v14; // rax
  __int64 v15; // r8
  int v16; // edx
  int v17; // ecx
  _QWORD *v18; // r9
  __int64 v19; // r10
  _QWORD ***v20; // rdx
  _QWORD ***v21; // rcx
  CConfigDescriptor *v22; // rax
  _QWORD **v23; // rax
  _QWORD *v24; // r14
  int *v25; // rcx
  int *v26; // rbx
  __int64 v27; // r13
  __int64 v28; // rax
  int v30[14]; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v31; // [rsp+60h] [rbp+8h]

  v4 = a4;
  v6 = a2;
  v7 = 0;
  v8 = 0;
  v9 = (_QWORD *)xmmword_1800198F0;
  while ( v9 != (_QWORD *)qword_180019918 )
  {
    if ( v8 )
      goto LABEL_13;
    v10 = (unsigned __int16 *)*v6;
    do
    {
      v11 = *(unsigned __int16 *)((char *)v10 + *v9 - *v6);
      v12 = *v10 - v11;
      if ( v12 )
        break;
      ++v10;
    }
    while ( v11 );
    if ( v12 )
    {
      if ( v12 >= 0 )
        v9 = (_QWORD *)v9[4];
      else
        v9 = (_QWORD *)v9[3];
    }
    else
    {
      v8 = v9;
    }
  }
  if ( v8 )
  {
LABEL_13:
    for ( i = v8; ; i = v18 )
    {
      v18 = (_QWORD *)ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Predecessor(
                        &xmmword_1800198F0,
                        i);
      if ( !v18 )
        break;
      v14 = (unsigned __int16 *)*v6;
      v15 = *v18 - *v6;
      do
      {
        v16 = *(unsigned __int16 *)((char *)v14 + v15);
        v17 = *v14 - v16;
        if ( v17 )
          break;
        ++v14;
      }
      while ( v16 );
      if ( v17 )
        break;
    }
    if ( v19 )
    {
      v20 = (_QWORD ***)(v19 + 8);
      v21 = a3;
LABEL_37:
      ((void (__fastcall *)(_QWORD ***, _QWORD ***, __int64, _QWORD *))SmartPtr<CConfigDescriptor>::operator=)(
        v21,
        v20,
        v15,
        v18);
      goto LABEL_42;
    }
  }
  if ( !v4 )
  {
    v7 = -2147023728;
    goto LABEL_42;
  }
  v22 = (CConfigDescriptor *)operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( v22 )
      v22 = CConfigDescriptor::CConfigDescriptor(v22);
    SmartPtr<CConfigDescriptor>::operator=(a3, v22);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)v30) )
    {
      v31 = v30[0];
      if ( v30[0] >= 0 )
      {
        v7 = v30[0];
        v6 = a2;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000ABE6);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
            (unsigned int)v30[0]);
        v7 = v31;
        v6 = a2;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000ABE4);
      }
      goto LABEL_42;
    }
  }
  v23 = *a3;
  if ( *a3 && *v23 )
  {
    v24 = *v23;
    v25 = (int *)(*v6 - 24LL);
    v26 = (int *)(**v23 - 24LL);
    if ( v25 != v26 )
    {
      if ( v26[4] >= 0 && *(_QWORD *)v25 == *(_QWORD *)v26 )
      {
        v27 = (__int64)ATL::CSimpleStringT<unsigned short,0>::CloneData(v25);
        ATL::CStringData::Release((ATL::CStringData *)v26);
        *v24 = v27 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(v24, *v6, *(unsigned int *)(*v6 - 16LL));
      }
    }
    v28 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Find(
            (_QWORD **)&xmmword_1800198F0,
            (unsigned __int16 *)*v6);
    if ( !v28 )
    {
      ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBInsert(
        &xmmword_1800198F0,
        *v6,
        a3);
      goto LABEL_42;
    }
    v21 = (_QWORD ***)(v28 + 8);
    v20 = a3;
    goto LABEL_37;
  }
  v7 = -2147024882;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, "ConfigDesc");
LABEL_42:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v6);
  return v7;
}

```

## disassembly

```asm
0x18000aa08  mov     [rsp+arg_10], rbx
0x18000aa0d  mov     [rsp+arg_8], rdx
0x18000aa12  mov     [rsp+arg_0], rcx
0x18000aa17  push    rsi
0x18000aa18  push    rdi
0x18000aa19  push    r13
0x18000aa1b  push    r14
0x18000aa1d  push    r15
0x18000aa1f  sub     rsp, 30h
0x18000aa23  mov     r11d, r9d
0x18000aa26  mov     r15, r8
0x18000aa29  mov     rdi, rdx
0x18000aa2c  xor     esi, esi
0x18000aa2e  xor     r10d, r10d
0x18000aa31  mov     rax, qword ptr cs:xmmword_1800198F0
0x18000aa38  cmp     rax, cs:qword_180019918
0x18000aa3f  jz      short loc_18000AA7C
0x18000aa41  test    r10, r10
0x18000aa44  jnz     short loc_18000AA81
0x18000aa46  mov     rcx, [rdi]
0x18000aa49  mov     r9, [rax]
0x18000aa4c  sub     r9, rcx
0x18000aa4f  movzx   edx, word ptr [rcx]
0x18000aa52  movzx   r8d, word ptr [rcx+r9]
0x18000aa57  sub     edx, r8d
0x18000aa5a  jnz     short loc_18000AA65
0x18000aa5c  add     rcx, 2
0x18000aa60  test    r8d, r8d
0x18000aa63  jnz     short loc_18000AA4F
0x18000aa65  test    edx, edx
0x18000aa67  jnz     short loc_18000AA6E
0x18000aa69  mov     r10, rax
0x18000aa6c  jmp     short loc_18000AA38
0x18000aa6e  jns     short loc_18000AA76
0x18000aa70  mov     rax, [rax+18h]
0x18000aa74  jmp     short loc_18000AA38
0x18000aa76  mov     rax, [rax+20h]
0x18000aa7a  jmp     short loc_18000AA38
0x18000aa7c  test    r10, r10
0x18000aa7f  jz      short loc_18000AAD2
0x18000aa81  mov     rdx, r10
0x18000aa84  jmp     short loc_18000AAAD
0x18000aa86  mov     rax, [rdi]
0x18000aa89  mov     r8, [r9]
0x18000aa8c  sub     r8, rax
0x18000aa8f  movzx   ecx, word ptr [rax]
0x18000aa92  movzx   edx, word ptr [rax+r8]
0x18000aa97  sub     ecx, edx
0x18000aa99  jnz     short loc_18000AAA3
0x18000aa9b  add     rax, 2
0x18000aa9f  test    edx, edx
0x18000aaa1  jnz     short loc_18000AA8F
0x18000aaa3  test    ecx, ecx
0x18000aaa5  jnz     short loc_18000AAC1
0x18000aaa7  mov     r10, r9
0x18000aaaa  mov     rdx, r9
0x18000aaad  lea     rcx, xmmword_1800198F0
0x18000aab4  call    ?Predecessor@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Predecessor(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000aab9  test    rax, rax
0x18000aabc  mov     r9, rax
0x18000aabf  jnz     short loc_18000AA86
0x18000aac1  test    r10, r10
0x18000aac4  jz      short loc_18000AAD2
0x18000aac6  lea     rdx, [r10+8]
0x18000aaca  mov     rcx, r15
0x18000aacd  jmp     loc_18000AB98
0x18000aad2  test    r11d, r11d
0x18000aad5  jz      loc_18000ABDD
0x18000aadb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000aae2  mov     ecx, 0A0h; unsigned __int64
0x18000aae7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000aaec  mov     [rsp+58h+arg_0], rax
0x18000aaf1  test    rax, rax
0x18000aaf4  jz      short loc_18000AAFF
0x18000aaf6  mov     rcx, rax; this
0x18000aaf9  call    ??0CConfigDescriptor@@QEAA@XZ; CConfigDescriptor::CConfigDescriptor(void)
0x18000aafe  nop
0x18000aaff  mov     rdx, rax
0x18000ab02  mov     rcx, r15
0x18000ab05  call    ??4?$SmartPtr@VCConfigDescriptor@@@@QEAAAEAV0@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::operator=(CConfigDescriptor *)
0x18000ab0a  mov     rax, [r15]
0x18000ab0d  test    rax, rax
0x18000ab10  jz      loc_18000ABA0
0x18000ab16  cmp     qword ptr [rax], 0
0x18000ab1a  jz      loc_18000ABA0
0x18000ab20  mov     r14, [rax]
0x18000ab23  mov     rdx, [rdi]
0x18000ab26  lea     rcx, [rdx-18h]
0x18000ab2a  mov     rbx, [r14]
0x18000ab2d  add     rbx, 0FFFFFFFFFFFFFFE8h
0x18000ab31  cmp     rcx, rbx
0x18000ab34  jz      short loc_18000AB69
0x18000ab36  cmp     dword ptr [rbx+10h], 0
0x18000ab3a  jl      short loc_18000AB5D
0x18000ab3c  mov     rax, [rbx]
0x18000ab3f  cmp     [rcx], rax
0x18000ab42  jnz     short loc_18000AB5D
0x18000ab44  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000ab49  mov     r13, rax
0x18000ab4c  mov     rcx, rbx; this
0x18000ab4f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000ab54  lea     rax, [r13+18h]
0x18000ab58  mov     [r14], rax
0x18000ab5b  jmp     short loc_18000AB69
0x18000ab5d  mov     r8d, [rdx-10h]
0x18000ab61  mov     rcx, r14
0x18000ab64  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000ab69  mov     rdx, [rdi]
0x18000ab6c  lea     rcx, xmmword_1800198F0
0x18000ab73  call    ?Find@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEBG@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Find(ushort const *)
0x18000ab78  test    rax, rax
0x18000ab7b  jnz     short loc_18000AB91
0x18000ab7d  mov     r8, r15
0x18000ab80  mov     rdx, [rdi]
0x18000ab83  lea     rcx, xmmword_1800198F0
0x18000ab8a  call    ?RBInsert@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@IEAAPEAVCNode@12@PEBGAEBV?$SmartPtr@VCVolumeTrackingDescriptor@@@@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBInsert(ushort const *,SmartPtr<CVolumeTrackingDescriptor> const &)
0x18000ab8f  jmp     short loc_18000AB9E
0x18000ab91  lea     rcx, [rax+8]
0x18000ab95  mov     rdx, r15
0x18000ab98  call    ??4?$SmartPtr@VCConfigDescriptor@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<CConfigDescriptor>::operator=(SmartPtr<CConfigDescriptor> const &)
0x18000ab9d  nop
0x18000ab9e  jmp     short loc_18000ABEF
0x18000aba0  mov     esi, 8007000Eh
0x18000aba5  lea     rax, WPP_GLOBAL_Control
0x18000abac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abb3  cmp     rcx, rax
0x18000abb6  jz      short loc_18000ABDB
0x18000abb8  test    byte ptr [rcx+1Ch], 1
0x18000abbc  jz      short loc_18000ABDB
0x18000abbe  mov     edx, 2Ah ; '*'
0x18000abc3  lea     r9, aConfigdesc; "ConfigDesc"
0x18000abca  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000abd1  mov     rcx, [rcx+10h]
0x18000abd5  call    WPP_SF_s
0x18000abda  nop
0x18000abdb  jmp     short loc_18000ABEF
0x18000abdd  mov     esi, 80070490h
0x18000abe2  jmp     short loc_18000ABEF
0x18000abe4  jmp     short $+2
0x18000abe6  mov     esi, dword ptr [rsp+58h+arg_0]
0x18000abea  mov     rdi, [rsp+58h+arg_8]
0x18000abef  mov     rcx, rdi
0x18000abf2  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000abf7  mov     eax, esi
0x18000abf9  mov     rbx, [rsp+58h+arg_10]
0x18000abfe  add     rsp, 30h
0x18000ac02  pop     r15
0x18000ac04  pop     r14
0x18000ac06  pop     r13
0x18000ac08  pop     rdi
0x18000ac09  pop     rsi
0x18000ac0a  retn
```
