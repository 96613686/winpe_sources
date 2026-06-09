# PreparePropStoreForProvider(IPropertyStore *,tagPROPVARIANT const &)

- ea: `0x180016ce4`
- end: `0x18001700e`
- name: `?PreparePropStoreForProvider@@YAJPEAUIPropertyStore@@AEBUtagPROPVARIANT@@@Z`
- size: `810`
- prototype: `__int64 __fastcall(struct IPropertyStore *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001dd80`

## callees

- `0x18000ab48`
- `0x18001681c`
- `0x180016918`
- `0x180016ce4`
- `0x180019668`
- `0x1800198d4`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016d1c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016e17`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016ed2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016f67`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016fe8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016d1c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016e17`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016ed2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016f67`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016fe8`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x180016d92`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x180016d92`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180016dc3`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180016dc3`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x180016d75`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x180016d75`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PreparePropStoreForProvider(struct IPropertyStore *a1, const struct tagPROPVARIANT *a2)
{
  int v4; // ebx
  HRESULT (__stdcall *GetValue)(IPropertyStore *, const PROPERTYKEY *const, PROPVARIANT *); // rdi
  int v6; // edi
  BYTE *v7; // rax
  ITEMIDLIST *v8; // r14
  const unsigned __int16 *String; // rax
  __int64 v10; // r10
  const unsigned __int16 *v11; // rax
  __int64 v12; // r10
  LONG v13; // eax
  PROPVARIANT v15; // [rsp+20h] [rbp-50h] BYREF
  PROPVARIANT v16; // [rsp+38h] [rbp-38h] BYREF
  PROPVARIANT pvar; // [rsp+50h] [rbp-20h] BYREF
  int v18; // [rsp+A0h] [rbp+30h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+B0h] [rbp+40h] BYREF

  v4 = 2;
  v18 = 2;
  pidl2 = 0;
  pvar.vt = 0;
  GetValue = a1->lpVtbl->GetValue;
  PropVariantClear(&pvar);
  if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))GetValue)(
         a1,
         &PKEY_Kind,
         &pvar) >= 0 )
  {
    if ( (unsigned int)IsFolder(&pvar) )
      v4 = 1;
    v18 = v4;
  }
  v6 = CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::s_CreateItemID(&v18, a1, (__int64 *)&pidl2, 0);
  if ( v6 >= 0 )
  {
    v7 = (BYTE *)ILCombine((LPCITEMIDLIST)a2->bstrblobVal.pData, pidl2);
    v8 = (ITEMIDLIST *)v7;
    if ( v7 )
    {
      *(_OWORD *)&v15.vt = 0u;
      v15.bstrblobVal.pData = v7;
      v15.lVal = ILGetSize((LPCITEMIDLIST)v7);
      v15.vt = 4113;
      v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a1->lpVtbl->SetValue)(
             a1,
             PKEY_DelegateIDList,
             &v15);
    }
    ILFree(v8);
    v16.vt = 0;
    if ( v6 >= 0
      && ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->GetValue)(
           a1,
           &PKEY_ItemUrl,
           &v16) >= 0
      && v16.vt )
    {
      v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->SetValue)(
             a1,
             &PKEY_ParsingPath,
             &v16);
    }
    PropVariantClear(&v16);
    if ( v6 >= 0 )
    {
      v15.vt = 0;
      if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->GetValue)(
             a1,
             &PKEY_ItemNameDisplay,
             &v15) >= 0
        && !v15.vt )
      {
        v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->GetValue)(
               a1,
               &PKEY_ItemName,
               &v15);
        if ( v6 >= 0 )
        {
          v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->SetValue)(
                 a1,
                 &PKEY_ItemNameDisplay,
                 &v15);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            String = CPropVariant::GetString((CPropVariant *)&v15);
            WPP_SF_S(*(_QWORD *)(v10 + 16), 35, &WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids, String);
          }
        }
      }
      PropVariantClear(&v15);
      if ( v6 >= 0 )
      {
        v15.vt = 0;
        v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, PROPVARIANT *))a1->lpVtbl->GetValue)(
               a1,
               &PKEY_CDSObjectID,
               &v15);
        if ( v6 >= 0 && v15.vt )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v11 = CPropVariant::GetString((CPropVariant *)&v15);
            WPP_SF_S(*(_QWORD *)(v12 + 16), 36, &WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids, v11);
          }
          v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a1->lpVtbl->SetValue)(
                 a1,
                 PKEY_ItemId,
                 &v15);
        }
        PropVariantClear(&v15);
        if ( v6 >= 0 )
        {
          v13 = 679739393;
          if ( v4 == 2 )
            v13 = 4456453;
          v16.vt = 19;
          v16.lVal = v13;
          v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->SetValue)(
                 a1,
                 &PKEY_SFGAOFlags,
                 &v16);
          if ( v6 >= 0 )
          {
            memset(&v16, 0, sizeof(v16));
            v16.vt = 11;
            v16.iVal = 0;
            v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a1->lpVtbl->SetValue)(
                   a1,
                   PKEY_NotUserContent,
                   &v16);
          }
        }
      }
    }
  }
  PropVariantClear(&pvar);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&pidl2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016ce4  mov     [rsp-28h+arg_8], rbx
0x180016ce9  push    rbp
0x180016cea  push    rsi
0x180016ceb  push    rdi
0x180016cec  push    r14
0x180016cee  push    r15
0x180016cf0  mov     rbp, rsp
0x180016cf3  sub     rsp, 70h
0x180016cf7  mov     r14, rdx
0x180016cfa  mov     rsi, rcx
0x180016cfd  mov     ebx, 2
0x180016d02  mov     [rbp+arg_0], ebx
0x180016d05  xor     r15d, r15d
0x180016d08  mov     [rbp+pidl2], r15
0x180016d0c  mov     word ptr [rbp+pvar], r15w
0x180016d11  mov     rax, [rcx]
0x180016d14  mov     rdi, [rax+28h]
0x180016d18  lea     rcx, [rbp+pvar]; pvar
0x180016d1c  call    cs:__imp_PropVariantClear
0x180016d22  lea     r8, [rbp+pvar]
0x180016d26  lea     rdx, PKEY_Kind
0x180016d2d  mov     rcx, rsi
0x180016d30  mov     rax, rdi
0x180016d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d38  test    eax, eax
0x180016d3a  js      short loc_180016D50
0x180016d3c  lea     rcx, [rbp+pvar]; struct tagPROPVARIANT *
0x180016d40  call    ?IsFolder@@YAHAEBUtagPROPVARIANT@@@Z; IsFolder(tagPROPVARIANT const &)
0x180016d45  lea     ecx, [rbx-1]
0x180016d48  test    eax, eax
0x180016d4a  cmovnz  ebx, ecx
0x180016d4d  mov     [rbp+arg_0], ebx
0x180016d50  xor     r9d, r9d
0x180016d53  lea     r8, [rbp+pidl2]
0x180016d57  mov     rdx, rsi
0x180016d5a  lea     rcx, [rbp+arg_0]
0x180016d5e  call    ?s_CreateItemID@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@SAJPEFBUCDSFOLDER_ITEMID@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::s_CreateItemID(CDSFOLDER_ITEMID const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)
0x180016d63  mov     edi, eax
0x180016d65  test    eax, eax
0x180016d67  js      loc_180016FE4
0x180016d6d  mov     rdx, [rbp+pidl2]; pidl2
0x180016d71  mov     rcx, [r14+10h]; pidl1
0x180016d75  call    cs:__imp_ILCombine
0x180016d7b  mov     r14, rax
0x180016d7e  test    rax, rax
0x180016d81  jz      short loc_180016DC0
0x180016d83  mov     qword ptr [rbp+var_50], r15
0x180016d87  mov     qword ptr [rbp+var_50+8], r15
0x180016d8b  mov     qword ptr [rbp+var_50+10h], rax
0x180016d8f  mov     rcx, rax; pidl
0x180016d92  call    cs:__imp_ILGetSize
0x180016d98  mov     dword ptr [rbp+var_50+8], eax
0x180016d9b  mov     eax, 1011h
0x180016da0  mov     word ptr [rbp+var_50], ax
0x180016da4  mov     rcx, [rsi]
0x180016da7  mov     rax, [rcx+30h]
0x180016dab  lea     r8, [rbp+var_50]
0x180016daf  lea     rdx, PKEY_DelegateIDList
0x180016db6  mov     rcx, rsi
0x180016db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dbe  mov     edi, eax
0x180016dc0  mov     rcx, r14; pidl
0x180016dc3  call    cs:__imp_ILFree
0x180016dc9  mov     word ptr [rbp+var_38], r15w
0x180016dce  test    edi, edi
0x180016dd0  js      short loc_180016E13
0x180016dd2  mov     rax, [rsi]
0x180016dd5  lea     r8, [rbp+var_38]
0x180016dd9  lea     rdx, PKEY_ItemUrl
0x180016de0  mov     rcx, rsi
0x180016de3  mov     rax, [rax+28h]
0x180016de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dec  test    eax, eax
0x180016dee  js      short loc_180016E13
0x180016df0  cmp     word ptr [rbp+var_38], r15w
0x180016df5  jz      short loc_180016E13
0x180016df7  mov     rax, [rsi]
0x180016dfa  lea     r8, [rbp+var_38]
0x180016dfe  lea     rdx, PKEY_ParsingPath
0x180016e05  mov     rcx, rsi
0x180016e08  mov     rax, [rax+30h]
0x180016e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e11  mov     edi, eax
0x180016e13  lea     rcx, [rbp+var_38]; pvar
0x180016e17  call    cs:__imp_PropVariantClear
0x180016e1d  test    edi, edi
0x180016e1f  js      loc_180016FE4
0x180016e25  mov     word ptr [rbp+var_50], r15w
0x180016e2a  mov     rax, [rsi]
0x180016e2d  lea     r8, [rbp+var_50]
0x180016e31  lea     rdx, PKEY_ItemNameDisplay
0x180016e38  mov     rcx, rsi
0x180016e3b  mov     rax, [rax+28h]
0x180016e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e44  lea     r14, WPP_GLOBAL_Control
0x180016e4b  test    eax, eax
0x180016e4d  js      short loc_180016ECE
0x180016e4f  cmp     word ptr [rbp+var_50], r15w
0x180016e54  jnz     short loc_180016ECE
0x180016e56  mov     rax, [rsi]
0x180016e59  lea     r8, [rbp+var_50]
0x180016e5d  lea     rdx, PKEY_ItemName
0x180016e64  mov     rcx, rsi
0x180016e67  mov     rax, [rax+28h]
0x180016e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e70  mov     edi, eax
0x180016e72  test    eax, eax
0x180016e74  js      short loc_180016ECE
0x180016e76  mov     rax, [rsi]
0x180016e79  lea     r8, [rbp+var_50]
0x180016e7d  lea     rdx, PKEY_ItemNameDisplay
0x180016e84  mov     rcx, rsi
0x180016e87  mov     rax, [rax+30h]
0x180016e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e90  mov     edi, eax
0x180016e92  mov     r10, cs:WPP_GLOBAL_Control
0x180016e99  cmp     r10, r14
0x180016e9c  jz      short loc_180016ECE
0x180016e9e  test    byte ptr [r10+1Ch], 40h
0x180016ea3  jz      short loc_180016ECE
0x180016ea5  cmp     byte ptr [r10+19h], 4
0x180016eaa  jb      short loc_180016ECE
0x180016eac  lea     rcx, [rbp+var_50]; this
0x180016eb0  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x180016eb5  mov     r9, rax
0x180016eb8  mov     edx, 23h ; '#'
0x180016ebd  lea     r8, WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids
0x180016ec4  mov     rcx, [r10+10h]
0x180016ec8  call    WPP_SF_S
0x180016ecd  nop
0x180016ece  lea     rcx, [rbp+var_50]; pvar
0x180016ed2  call    cs:__imp_PropVariantClear
0x180016ed8  test    edi, edi
0x180016eda  js      loc_180016FE4
0x180016ee0  mov     word ptr [rbp+var_50], r15w
0x180016ee5  mov     rax, [rsi]
0x180016ee8  lea     r8, [rbp+var_50]
0x180016eec  lea     rdx, PKEY_CDSObjectID
0x180016ef3  mov     rcx, rsi
0x180016ef6  mov     rax, [rax+28h]
0x180016efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016eff  mov     edi, eax
0x180016f01  test    eax, eax
0x180016f03  js      short loc_180016F63
0x180016f05  cmp     word ptr [rbp+var_50], r15w
0x180016f0a  jz      short loc_180016F63
0x180016f0c  mov     r10, cs:WPP_GLOBAL_Control
0x180016f13  cmp     r10, r14
0x180016f16  jz      short loc_180016F47
0x180016f18  test    byte ptr [r10+1Ch], 40h
0x180016f1d  jz      short loc_180016F47
0x180016f1f  cmp     byte ptr [r10+19h], 4
0x180016f24  jb      short loc_180016F47
0x180016f26  lea     rcx, [rbp+var_50]; this
0x180016f2a  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x180016f2f  mov     r9, rax
0x180016f32  mov     edx, 24h ; '$'
0x180016f37  lea     r8, WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids
0x180016f3e  mov     rcx, [r10+10h]
0x180016f42  call    WPP_SF_S
0x180016f47  mov     rax, [rsi]
0x180016f4a  lea     r8, [rbp+var_50]
0x180016f4e  lea     rdx, PKEY_ItemId
0x180016f55  mov     rcx, rsi
0x180016f58  mov     rax, [rax+30h]
0x180016f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f61  mov     edi, eax
0x180016f63  lea     rcx, [rbp+var_50]; pvar
0x180016f67  call    cs:__imp_PropVariantClear
0x180016f6d  test    edi, edi
0x180016f6f  js      short loc_180016FE4
0x180016f71  mov     eax, 28840001h
0x180016f76  mov     ecx, 440005h
0x180016f7b  cmp     ebx, 2
0x180016f7e  cmovz   eax, ecx
0x180016f81  mov     ecx, 13h
0x180016f86  mov     word ptr [rbp+var_38], cx
0x180016f8a  mov     dword ptr [rbp+var_38+8], eax
0x180016f8d  mov     rax, [rsi]
0x180016f90  lea     r8, [rbp+var_38]
0x180016f94  lea     rdx, PKEY_SFGAOFlags
0x180016f9b  mov     rcx, rsi
0x180016f9e  mov     rax, [rax+30h]
0x180016fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fa7  mov     edi, eax
0x180016fa9  test    eax, eax
0x180016fab  js      short loc_180016FE4
0x180016fad  xorps   xmm0, xmm0
0x180016fb0  xor     eax, eax
0x180016fb2  movups  xmmword ptr [rbp+var_38], xmm0
0x180016fb6  mov     qword ptr [rbp+var_38+10h], rax
0x180016fba  mov     eax, 0Bh
0x180016fbf  mov     word ptr [rbp+var_38], ax
0x180016fc3  mov     word ptr [rbp+var_38+8], r15w
0x180016fc8  mov     rax, [rsi]
0x180016fcb  lea     r8, [rbp+var_38]
0x180016fcf  lea     rdx, PKEY_NotUserContent
0x180016fd6  mov     rcx, rsi
0x180016fd9  mov     rax, [rax+30h]
0x180016fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fe2  mov     edi, eax
0x180016fe4  lea     rcx, [rbp+pvar]; pvar
0x180016fe8  call    cs:__imp_PropVariantClear
0x180016fee  nop
0x180016fef  lea     rcx, [rbp+pidl2]
0x180016ff3  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180016ff8  mov     eax, edi
0x180016ffa  mov     rbx, [rsp+70h+arg_8]
0x180017002  add     rsp, 70h
0x180017006  pop     r15
0x180017008  pop     r14
0x18001700a  pop     rdi
0x18001700b  pop     rsi
0x18001700c  pop     rbp
0x18001700d  retn
```
