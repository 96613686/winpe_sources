# CContentDirectoryFolder::CompareIDs(__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x1800159c0`
- end: `0x180015ba5`
- name: `?CompareIDs@CContentDirectoryFolder@@UEAAJ_JPEFBU_ITEMIDLIST_RELATIVE@@1@Z`
- size: `485`
- prototype: `__int64 __fastcall(CContentDirectoryFolder *__hidden this, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000da80`
- `0x18000dbb8`
- `0x180011930`
- `0x1800159c0`
- `0x180015bac`
- `0x1800169b0`
- `0x180018018`
- `0x180019b84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015aef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015b00`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015aef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015b00`
- `PROPSYS!PropVariantCompareEx` at `0x180015ade`
- `PROPSYS!PropVariantCompareEx` at `0x180015ade`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentDirectoryFolder::CompareIDs(
        CContentDirectoryFolder *this,
        __int64 a2,
        const struct _ITEMIDLIST_RELATIVE *a3,
        const struct _ITEMIDLIST_RELATIVE *a4)
{
  __int64 IsValid; // rax
  __int64 v9; // r9
  _WORD *v10; // rdi
  __int64 v11; // rax
  _DWORD *v12; // rdx
  __int16 v13; // di
  int v14; // ebx
  PROPVARIANT propvar2; // [rsp+20h] [rbp-58h] BYREF
  PROPVARIANT propvar1; // [rsp+38h] [rbp-40h] BYREF
  struct _tagpropertykey v18; // [rsp+50h] [rbp-28h] BYREF

  IsValid = CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::_IsValid(a3);
  v10 = (_WORD *)((IsValid + 14) & -(__int64)(IsValid != 0));
  if ( !v10
    || (v11 = CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::_IsValid(v9),
        (v12 = (_DWORD *)((v11 + 14) & ((unsigned __int128)-(__int128)(unsigned __int64)v11 >> 64))) == 0) )
  {
    v14 = -2147024809;
    goto LABEL_23;
  }
  if ( *(_DWORD *)v10 == *v12 )
  {
    memset(&v18, 0, sizeof(v18));
    if ( (a2 & 0x10000000) != 0 )
    {
      v14 = 0;
      v18 = PKEY_ParsingName;
    }
    else
    {
      v14 = CContentDirectoryFolder::_EnsureColumnInfo((CContentDirectoryFolder *)((char *)this - 16));
      if ( v14 < 0 )
        goto LABEL_23;
      v14 = CContentDirectoryFolder::MapColumnToSCID(this, (unsigned __int16)a2, &v18);
    }
    if ( v14 < 0 )
      goto LABEL_23;
    propvar1.vt = 0;
    if ( CContentDirectoryFolder::GetPropertyWithFallback(
           (CContentDirectoryFolder *)((char *)this - 16),
           a3,
           &v18,
           &propvar1) < 0 )
    {
      v13 = 1;
    }
    else
    {
      propvar2.vt = 0;
      if ( CContentDirectoryFolder::GetPropertyWithFallback(
             (CContentDirectoryFolder *)((char *)this - 16),
             a4,
             &v18,
             &propvar2) < 0 )
        v13 = -1;
      else
        v13 = PropVariantCompareEx(&propvar1, &propvar2, PVCU_DEFAULT, 0);
      PropVariantClear(&propvar2);
    }
    PropVariantClear(&propvar1);
  }
  else
  {
    v13 = *v10 - *v12;
  }
  if ( v13 )
  {
    if ( v13 >= 0 )
      v14 = v13 > 0;
    else
      v14 = 0xFFFF;
  }
  else
  {
    v14 = CContentDirectoryFolder::CompareRelativeIDLists(
            (struct IShellFolder *)((unsigned __int64)this & -(__int64)(this != (CContentDirectoryFolder *)16)),
            a3,
            a4,
            a2);
  }
LABEL_23:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v14 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      &WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids,
      (unsigned int)v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800159c0  push    rbp
0x1800159c2  push    rbx
0x1800159c3  push    rsi
0x1800159c4  push    rdi
0x1800159c5  push    r12
0x1800159c7  push    r13
0x1800159c9  push    r14
0x1800159cb  push    r15
0x1800159cd  mov     rbp, rsp
0x1800159d0  sub     rsp, 78h
0x1800159d4  mov     rax, cs:__security_cookie
0x1800159db  xor     rax, rsp
0x1800159de  mov     [rbp+var_10], rax
0x1800159e2  mov     r12, r9
0x1800159e5  mov     r13, r8
0x1800159e8  mov     r15, rdx
0x1800159eb  mov     r14, rcx
0x1800159ee  mov     rcx, r8
0x1800159f1  call    ?_IsValid@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::_IsValid(_ITEMIDLIST_RELATIVE const *)
0x1800159f6  lea     rcx, [rax+0Eh]
0x1800159fa  neg     rax
0x1800159fd  sbb     rdi, rdi
0x180015a00  and     rdi, rcx
0x180015a03  jz      loc_180015B3D
0x180015a09  mov     rcx, r9
0x180015a0c  call    ?_IsValid@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::_IsValid(_ITEMIDLIST_RELATIVE const *)
0x180015a11  lea     rcx, [rax+0Eh]
0x180015a15  neg     rax
0x180015a18  sbb     rdx, rdx
0x180015a1b  and     rdx, rcx
0x180015a1e  jz      loc_180015B3D
0x180015a24  mov     eax, [rdx]
0x180015a26  xor     r10d, r10d
0x180015a29  lea     rsi, [r14-10h]
0x180015a2d  cmp     [rdi], eax
0x180015a2f  jz      short loc_180015A3C
0x180015a31  movzx   edi, word ptr [rdi]
0x180015a34  sub     di, ax
0x180015a37  jmp     loc_180015B09
0x180015a3c  xorps   xmm0, xmm0
0x180015a3f  xor     eax, eax
0x180015a41  movups  xmmword ptr [rbp+var_28.fmtid.Data1], xmm0
0x180015a45  mov     [rbp+var_28.pid], eax
0x180015a48  bt      r15, 1Ch
0x180015a4d  jnb     short loc_180015A68
0x180015a4f  mov     ebx, r10d
0x180015a52  movups  xmm0, xmmword ptr cs:PKEY_ParsingName.fmtid.Data1
0x180015a59  movups  xmmword ptr [rbp+var_28.fmtid.Data1], xmm0
0x180015a5d  mov     eax, cs:PKEY_ParsingName.pid
0x180015a63  mov     [rbp+var_28.pid], eax
0x180015a66  jmp     short loc_180015A8F
0x180015a68  mov     rcx, rsi; this
0x180015a6b  call    ?_EnsureColumnInfo@CContentDirectoryFolder@@AEAAJXZ; CContentDirectoryFolder::_EnsureColumnInfo(void)
0x180015a70  mov     ebx, eax
0x180015a72  test    eax, eax
0x180015a74  js      loc_180015B42
0x180015a7a  movzx   edx, r15w; unsigned int
0x180015a7e  lea     r8, [rbp+var_28]; struct _tagpropertykey *
0x180015a82  mov     rcx, r14; this
0x180015a85  call    ?MapColumnToSCID@CContentDirectoryFolder@@UEAAJIPEAU_tagpropertykey@@@Z; CContentDirectoryFolder::MapColumnToSCID(uint,_tagpropertykey *)
0x180015a8a  mov     ebx, eax
0x180015a8c  xor     r10d, r10d
0x180015a8f  test    ebx, ebx
0x180015a91  js      loc_180015B42
0x180015a97  mov     word ptr [rbp+propvar1], r10w
0x180015a9c  lea     r9, [rbp+propvar1]; struct tagPROPVARIANT *
0x180015aa0  lea     r8, [rbp+var_28]; struct _tagpropertykey *
0x180015aa4  mov     rdx, r13; struct _ITEMID_CHILD *
0x180015aa7  mov     rcx, rsi; this
0x180015aaa  call    ?GetPropertyWithFallback@CContentDirectoryFolder@@QEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CContentDirectoryFolder::GetPropertyWithFallback(_ITEMID_CHILD const *,_tagpropertykey const &,tagPROPVARIANT *)
0x180015aaf  test    eax, eax
0x180015ab1  js      short loc_180015AF7
0x180015ab3  xor     eax, eax
0x180015ab5  mov     word ptr [rbp+propvar2], ax
0x180015ab9  lea     r9, [rbp+propvar2]; struct tagPROPVARIANT *
0x180015abd  lea     r8, [rbp+var_28]; struct _tagpropertykey *
0x180015ac1  mov     rdx, r12; struct _ITEMID_CHILD *
0x180015ac4  mov     rcx, rsi; this
0x180015ac7  call    ?GetPropertyWithFallback@CContentDirectoryFolder@@QEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CContentDirectoryFolder::GetPropertyWithFallback(_ITEMID_CHILD const *,_tagpropertykey const &,tagPROPVARIANT *)
0x180015acc  test    eax, eax
0x180015ace  js      short loc_180015AE8
0x180015ad0  xor     r9d, r9d; flags
0x180015ad3  xor     r8d, r8d; unit
0x180015ad6  lea     rdx, [rbp+propvar2]; propvar2
0x180015ada  lea     rcx, [rbp+propvar1]; propvar1
0x180015ade  call    cs:__imp_PropVariantCompareEx
0x180015ae4  mov     edi, eax
0x180015ae6  jmp     short loc_180015AEB
0x180015ae8  or      edi, 0FFFFFFFFh
0x180015aeb  lea     rcx, [rbp+propvar2]; pvar
0x180015aef  call    cs:__imp_PropVariantClear
0x180015af5  jmp     short loc_180015AFC
0x180015af7  mov     edi, 1
0x180015afc  lea     rcx, [rbp+propvar1]; pvar
0x180015b00  call    cs:__imp_PropVariantClear
0x180015b06  xor     r10d, r10d
0x180015b09  test    di, di
0x180015b0c  jnz     short loc_180015B29
0x180015b0e  neg     rsi
0x180015b11  sbb     rcx, rcx
0x180015b14  and     rcx, r14; struct IShellFolder *
0x180015b17  mov     r9, r15; __int64
0x180015b1a  mov     r8, r12; struct _ITEMIDLIST_RELATIVE *
0x180015b1d  mov     rdx, r13; struct _ITEMIDLIST_RELATIVE *
0x180015b20  call    ?CompareRelativeIDLists@CContentDirectoryFolder@@SAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@1_J@Z; CContentDirectoryFolder::CompareRelativeIDLists(IShellFolder *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *,__int64)
0x180015b25  mov     ebx, eax
0x180015b27  jmp     short loc_180015B42
0x180015b29  jns     short loc_180015B32
0x180015b2b  mov     ebx, 0FFFFh
0x180015b30  jmp     short loc_180015B42
0x180015b32  mov     ebx, r10d
0x180015b35  test    di, di
0x180015b38  setnle  bl
0x180015b3b  jmp     short loc_180015B42
0x180015b3d  mov     ebx, 80070057h
0x180015b42  lea     rax, WPP_GLOBAL_Control
0x180015b49  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b50  cmp     rcx, rax
0x180015b53  jz      short loc_180015B86
0x180015b55  test    byte ptr [rcx+1Ch], 2
0x180015b59  jz      short loc_180015B86
0x180015b5b  mov     edx, ebx
0x180015b5d  sar     edx, 1Fh
0x180015b60  and     edx, 0FFFFFFFDh
0x180015b63  add     edx, 5
0x180015b66  movzx   eax, byte ptr [rcx+19h]
0x180015b6a  cmp     eax, edx
0x180015b6c  jb      short loc_180015B86
0x180015b6e  mov     edx, 16h
0x180015b73  mov     r9d, ebx
0x180015b76  lea     r8, WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids
0x180015b7d  mov     rcx, [rcx+10h]
0x180015b81  call    WPP_SF_d
0x180015b86  mov     eax, ebx
0x180015b88  mov     rcx, [rbp+var_10]
0x180015b8c  xor     rcx, rsp; StackCookie
0x180015b8f  call    __security_check_cookie
0x180015b94  add     rsp, 78h
0x180015b98  pop     r15
0x180015b9a  pop     r14
0x180015b9c  pop     r13
0x180015b9e  pop     r12
0x180015ba0  pop     rdi
0x180015ba1  pop     rsi
0x180015ba2  pop     rbx
0x180015ba3  pop     rbp
0x180015ba4  retn
```
