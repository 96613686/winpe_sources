# CContentDirectoryFolder::_GetThumbnailProvider(_ITEMID_CHILD const *,_GUID const &,void * *)

- ea: `0x180011204`
- end: `0x180011525`
- name: `?_GetThumbnailProvider@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z`
- size: `801`
- prototype: `__int64 __fastcall(CContentDirectoryFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011150`
- `0x180011204`
- `0x180019370`

## callees

- `0x180001710`
- `0x180005790`
- `0x1800082b4`
- `0x18000ab48`
- `0x180010030`
- `0x180011204`
- `0x180014d10`
- `0x1800173a0`
- `0x180019838`
- `0x180019958`
- `0x18002c988`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112e0`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1800113b3`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1800113b3`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x180011296`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x1800112ce`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x180011296`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x1800112ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CContentDirectoryFolder::_GetThumbnailProvider(
        CContentDirectoryFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _GUID *a3,
        void **a4)
{
  int MediaTypeFromClass; // ebx
  WCHAR *v9; // rcx
  __int64 v10; // rcx
  WCHAR *v11; // rcx
  int v12; // esi
  int ThumbnailProvider; // ebx
  void *v14; // rdi
  __int64 (__fastcall *v15)(void *, _QWORD, __int64, __int64 *); // rbx
  LPITEMIDLIST v16; // rbx
  const struct _GUID *v17; // rcx
  LPITEMIDLIST v18; // rcx
  void *abID; // rax
  int v21; // [rsp+30h] [rbp-48h] BYREF
  PCWSTR v22; // [rsp+38h] [rbp-40h] BYREF
  PCWSTR pszUrl; // [rsp+40h] [rbp-38h] BYREF
  __int64 v24; // [rsp+48h] [rbp-30h] BYREF
  void *v25; // [rsp+50h] [rbp-28h] BYREF
  LPITEMIDLIST pidl; // [rsp+58h] [rbp-20h] BYREF
  unsigned __int16 *v27; // [rsp+60h] [rbp-18h] BYREF
  unsigned __int16 *v28[2]; // [rsp+68h] [rbp-10h] BYREF

  MediaTypeFromClass = 0;
  v28[0] = 0;
  pszUrl = 0;
  v22 = 0;
  if ( (Microsoft_Windows_DLNA_NamespaceEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(this, ContentDirectory_GetThumbnailProvider_Start, 0);
  if ( CContentDirectoryFolder::_GetString(this, a2, &PKEY_ItemClass, v28) >= 0 )
  {
    MediaTypeFromClass = CCDSResultsParser::GetMediaTypeFromClass(v28[0]);
    if ( MediaTypeFromClass == 8
      && CContentDirectoryFolder::_GetString(this, a2, &PKEY_DLNA_NativeResUrl, (unsigned __int16 **)&pszUrl) >= 0
      && !UrlIsW(pszUrl, URLIS_URL) )
    {
      v9 = (WCHAR *)pszUrl;
      pszUrl = 0;
      CoTaskMemFree(v9);
    }
  }
  if ( CContentDirectoryFolder::_GetString(this, a2, &PKEY_AlbumArtURI, (unsigned __int16 **)&v22) >= 0
    && !UrlIsW(v22, URLIS_URL) )
  {
    v11 = (WCHAR *)v22;
    v22 = 0;
    CoTaskMemFree(v11);
  }
  if ( !v22 && !pszUrl )
  {
    v12 = -2147467259;
    if ( MediaTypeFromClass == 64 )
    {
      v25 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v25);
      ThumbnailProvider = CContentDirectoryFolder::BindToObject(
                            (CContentDirectoryFolder *)((char *)this + 16),
                            a2,
                            0,
                            &GUID_000214e6_0000_0000_c000_000000000046,
                            &v25);
      if ( ThumbnailProvider >= 0 )
      {
        v24 = 0;
        v14 = v25;
        v15 = *(__int64 (__fastcall **)(void *, _QWORD, __int64, __int64 *))(*(_QWORD *)v25 + 32LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v24);
        ThumbnailProvider = v15(v14, 0, 64, &v24);
        if ( !ThumbnailProvider )
        {
          pidl = 0;
          v21 = 0;
          ThumbnailProvider = (*(__int64 (__fastcall **)(__int64, __int64, LPITEMIDLIST *, int *))(*(_QWORD *)v24 + 24LL))(
                                v24,
                                1,
                                &pidl,
                                &v21);
          if ( !ThumbnailProvider )
          {
            ThumbnailProvider = CContentDirectoryFolder::_GetThumbnailProvider(
                                  this,
                                  (const struct _ITEMID_CHILD *)pidl,
                                  a3,
                                  a4);
            ILFree(pidl);
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v24);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v25);
      if ( ThumbnailProvider == 1 )
        ThumbnailProvider = -2147467259;
      v12 = ThumbnailProvider;
    }
    goto LABEL_33;
  }
  pidl = 0;
  v12 = Microsoft::WRL::Details::MakeAndInitialize<CContentDirectoryThumbnailProvider,CContentDirectoryThumbnailProvider,CCoTaskMemPtr<unsigned short> &,CCoTaskMemPtr<unsigned short> &>(
          &pidl,
          &v22,
          &pszUrl);
  v16 = pidl;
  if ( v12 >= 0 )
  {
    *a4 = 0;
    if ( (unsigned int)InlineIsEqualGUID(a3, &GUID_00000000_0000_0000_c000_000000000046) )
    {
      *a4 = v16;
      (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&v16->mkid.cb + 8LL))(v16);
      v12 = 0;
    }
    else
    {
      if ( (unsigned int)InlineIsEqualGUID(v17, &GUID_e357fccd_a995_4576_b01f_234630154e96) )
      {
        v18 = v16;
        abID = v16;
LABEL_28:
        v12 = 0;
        *a4 = abID;
        (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&v18->mkid.cb + 8LL))(v18);
        goto LABEL_31;
      }
      if ( (unsigned int)InlineIsEqualGUID(a3, &GUID_382848c8_110f_4402_b0dc_21f5d4cf3938) )
      {
        v18 = (LPITEMIDLIST)((char *)v16 + 8);
        abID = v16[2].mkid.abID;
        goto LABEL_28;
      }
      v12 = -2147467262;
    }
  }
LABEL_31:
  if ( v16 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IThumbnailProvider,IThumbnailStreamProvider>::Release(v16);
LABEL_33:
  if ( (Microsoft_Windows_DLNA_NamespaceEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(v10, ContentDirectory_GetThumbnailProvider_Stop, (unsigned int)v12);
  v27 = 0;
  CContentDirectoryFolder::_GetString(this, a2, &PKEY_CDSObjectID, &v27);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      (unsigned int)&WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids,
      (_DWORD)v27,
      v12);
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v27);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v22);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&pszUrl);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(v28);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180011204  push    rbp
0x180011206  push    rbx
0x180011207  push    rsi
0x180011208  push    rdi
0x180011209  push    r12
0x18001120b  push    r13
0x18001120d  push    r14
0x18001120f  push    r15
0x180011211  mov     rbp, rsp
0x180011214  sub     rsp, 78h
0x180011218  mov     r14, r9
0x18001121b  mov     r12, r8
0x18001121e  mov     r13, rdx
0x180011221  mov     r15, rcx
0x180011224  xor     edi, edi
0x180011226  mov     ebx, edi
0x180011228  mov     [rbp+var_10], rdi
0x18001122c  mov     [rbp+pszUrl], rdi
0x180011230  mov     [rbp+var_40], rdi
0x180011234  test    cs:Microsoft_Windows_DLNA_NamespaceEnableBits, 1
0x18001123b  jz      short loc_18001124C
0x18001123d  xor     r8d, r8d
0x180011240  lea     rdx, ContentDirectory_GetThumbnailProvider_Start
0x180011247  call    McTemplateU0q_EventWriteTransfer
0x18001124c  lea     r9, [rbp+var_10]; unsigned __int16 **
0x180011250  lea     r8, PKEY_ItemClass; struct _tagpropertykey *
0x180011257  mov     rdx, r13; struct _ITEMID_CHILD *
0x18001125a  mov     rcx, r15; this
0x18001125d  call    ?_GetString@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CContentDirectoryFolder::_GetString(_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x180011262  test    eax, eax
0x180011264  js      short loc_1800112AE
0x180011266  mov     rcx, [rbp+var_10]
0x18001126a  call    ?GetMediaTypeFromClass@CCDSResultsParser@@SA?AW4_CDS_MEDIA_TYPE@@PEBG@Z; CCDSResultsParser::GetMediaTypeFromClass(ushort const *)
0x18001126f  mov     ebx, eax
0x180011271  cmp     eax, 8
0x180011274  jnz     short loc_1800112AE
0x180011276  lea     r9, [rbp+pszUrl]; unsigned __int16 **
0x18001127a  lea     r8, PKEY_DLNA_NativeResUrl; struct _tagpropertykey *
0x180011281  mov     rdx, r13; struct _ITEMID_CHILD *
0x180011284  mov     rcx, r15; this
0x180011287  call    ?_GetString@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CContentDirectoryFolder::_GetString(_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x18001128c  test    eax, eax
0x18001128e  js      short loc_1800112AE
0x180011290  xor     edx, edx; UrlIs
0x180011292  mov     rcx, [rbp+pszUrl]; pszUrl
0x180011296  call    cs:__imp_UrlIsW
0x18001129c  test    eax, eax
0x18001129e  jnz     short loc_1800112AE
0x1800112a0  mov     rcx, [rbp+pszUrl]; pv
0x1800112a4  mov     [rbp+pszUrl], rdi
0x1800112a8  call    cs:__imp_CoTaskMemFree
0x1800112ae  lea     r9, [rbp+var_40]; unsigned __int16 **
0x1800112b2  lea     r8, PKEY_AlbumArtURI; struct _tagpropertykey *
0x1800112b9  mov     rdx, r13; struct _ITEMID_CHILD *
0x1800112bc  mov     rcx, r15; this
0x1800112bf  call    ?_GetString@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CContentDirectoryFolder::_GetString(_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x1800112c4  test    eax, eax
0x1800112c6  js      short loc_1800112E6
0x1800112c8  xor     edx, edx; UrlIs
0x1800112ca  mov     rcx, [rbp+var_40]; pszUrl
0x1800112ce  call    cs:__imp_UrlIsW
0x1800112d4  test    eax, eax
0x1800112d6  jnz     short loc_1800112E6
0x1800112d8  mov     rcx, [rbp+var_40]; pv
0x1800112dc  mov     [rbp+var_40], rdi
0x1800112e0  call    cs:__imp_CoTaskMemFree
0x1800112e6  cmp     [rbp+var_40], rdi
0x1800112ea  jnz     loc_1800113DA
0x1800112f0  cmp     [rbp+pszUrl], rdi
0x1800112f4  jnz     loc_1800113DA
0x1800112fa  mov     esi, 80004005h
0x1800112ff  cmp     ebx, 40h ; '@'
0x180011302  jnz     loc_18001147C
0x180011308  mov     [rbp+var_28], rdi
0x18001130c  lea     rcx, [rbp+var_28]
0x180011310  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180011315  lea     rcx, [r15+10h]; this
0x180011319  lea     rax, [rbp+var_28]
0x18001131d  mov     [rsp+78h+var_58], rax; void **
0x180011322  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; struct _GUID *
0x180011329  xor     r8d, r8d; struct IBindCtx *
0x18001132c  mov     rdx, r13; struct _ITEMIDLIST_RELATIVE *
0x18001132f  call    ?BindToObject@CContentDirectoryFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z; CContentDirectoryFolder::BindToObject(_ITEMIDLIST_RELATIVE const *,IBindCtx *,_GUID const &,void * *)
0x180011334  mov     ebx, eax
0x180011336  test    eax, eax
0x180011338  js      loc_1800113C4
0x18001133e  mov     [rbp+var_30], rdi
0x180011342  mov     rdi, [rbp+var_28]
0x180011346  mov     rax, [rdi]
0x180011349  mov     rbx, [rax+20h]
0x18001134d  lea     rcx, [rbp+var_30]
0x180011351  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180011356  lea     r9, [rbp+var_30]
0x18001135a  xor     edx, edx
0x18001135c  lea     r8d, [rdx+40h]
0x180011360  mov     rcx, rdi
0x180011363  mov     rax, rbx
0x180011366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001136b  mov     ebx, eax
0x18001136d  xor     edi, edi
0x18001136f  test    eax, eax
0x180011371  jnz     short loc_1800113BA
0x180011373  mov     [rbp+pidl], rdi
0x180011377  mov     [rbp+var_48], edi
0x18001137a  mov     rcx, [rbp+var_30]
0x18001137e  mov     rax, [rcx]
0x180011381  lea     r9, [rbp+var_48]
0x180011385  lea     r8, [rbp+pidl]
0x180011389  lea     edx, [rbx+1]
0x18001138c  mov     rax, [rax+18h]
0x180011390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011395  mov     ebx, eax
0x180011397  test    eax, eax
0x180011399  jnz     short loc_1800113BA
0x18001139b  mov     r9, r14; void **
0x18001139e  mov     r8, r12; struct _GUID *
0x1800113a1  mov     rdx, [rbp+pidl]; struct _ITEMID_CHILD *
0x1800113a5  mov     rcx, r15; this
0x1800113a8  call    ?_GetThumbnailProvider@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z; CContentDirectoryFolder::_GetThumbnailProvider(_ITEMID_CHILD const *,_GUID const &,void * *)
0x1800113ad  mov     ebx, eax
0x1800113af  mov     rcx, [rbp+pidl]; pidl
0x1800113b3  call    cs:__imp_ILFree
0x1800113b9  nop
0x1800113ba  lea     rcx, [rbp+var_30]
0x1800113be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800113c3  nop
0x1800113c4  lea     rcx, [rbp+var_28]
0x1800113c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800113cd  cmp     ebx, 1
0x1800113d0  cmovz   ebx, esi
0x1800113d3  mov     esi, ebx
0x1800113d5  jmp     loc_18001147C
0x1800113da  mov     [rbp+pidl], rdi
0x1800113de  lea     r8, [rbp+pszUrl]
0x1800113e2  lea     rdx, [rbp+var_40]
0x1800113e6  lea     rcx, [rbp+pidl]
0x1800113ea  call    ??$MakeAndInitialize@VCContentDirectoryThumbnailProvider@@V1@AEAV?$CCoTaskMemPtr@G@@AEAV2@@Details@WRL@Microsoft@@YAJPEAPEAVCContentDirectoryThumbnailProvider@@AEAV?$CCoTaskMemPtr@G@@1@Z; Microsoft::WRL::Details::MakeAndInitialize<CContentDirectoryThumbnailProvider,CContentDirectoryThumbnailProvider,CCoTaskMemPtr<ushort> &,CCoTaskMemPtr<ushort> &>(CContentDirectoryThumbnailProvider * *,CCoTaskMemPtr<ushort> &,CCoTaskMemPtr<ushort> &)
0x1800113ef  mov     esi, eax
0x1800113f1  mov     rbx, [rbp+pidl]
0x1800113f5  test    eax, eax
0x1800113f7  js      short loc_18001146F
0x1800113f9  mov     [r14], rdi
0x1800113fc  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x180011403  mov     rcx, r12; struct _GUID *
0x180011406  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18001140b  test    eax, eax
0x18001140d  jnz     short loc_18001145B
0x18001140f  lea     rdx, _GUID_e357fccd_a995_4576_b01f_234630154e96; struct _GUID *
0x180011416  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18001141b  test    eax, eax
0x18001141d  jz      short loc_180011427
0x18001141f  mov     rcx, rbx
0x180011422  mov     rax, rbx
0x180011425  jmp     short loc_180011441
0x180011427  lea     rdx, _GUID_382848c8_110f_4402_b0dc_21f5d4cf3938; struct _GUID *
0x18001142e  mov     rcx, r12; struct _GUID *
0x180011431  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180011436  test    eax, eax
0x180011438  jz      short loc_180011454
0x18001143a  lea     rcx, [rbx+8]
0x18001143e  mov     rax, rcx
0x180011441  mov     esi, edi
0x180011443  mov     [r14], rax
0x180011446  mov     rax, [rcx]
0x180011449  mov     rax, [rax+8]
0x18001144d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011452  jmp     short loc_18001146F
0x180011454  mov     esi, 80004002h
0x180011459  jmp     short loc_18001146F
0x18001145b  mov     [r14], rbx
0x18001145e  mov     rax, [rbx]
0x180011461  mov     rcx, rbx
0x180011464  mov     rax, [rax+8]
0x180011468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001146d  mov     esi, edi
0x18001146f  test    rbx, rbx
0x180011472  jz      short loc_18001147C
0x180011474  mov     rcx, rbx
0x180011477  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIThumbnailProvider@@UIThumbnailStreamProvider@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IThumbnailProvider,IThumbnailStreamProvider>::Release(void)
0x18001147c  test    cs:Microsoft_Windows_DLNA_NamespaceEnableBits, 1
0x180011483  jz      short loc_180011494
0x180011485  mov     r8d, esi
0x180011488  lea     rdx, ContentDirectory_GetThumbnailProvider_Stop
0x18001148f  call    McTemplateU0q_EventWriteTransfer
0x180011494  mov     [rbp+var_18], rdi
0x180011498  lea     r9, [rbp+var_18]; unsigned __int16 **
0x18001149c  lea     r8, PKEY_CDSObjectID; struct _tagpropertykey *
0x1800114a3  mov     rdx, r13; struct _ITEMID_CHILD *
0x1800114a6  mov     rcx, r15; this
0x1800114a9  call    ?_GetString@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CContentDirectoryFolder::_GetString(_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x1800114ae  lea     rax, WPP_GLOBAL_Control
0x1800114b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114bc  cmp     rcx, rax
0x1800114bf  jz      short loc_1800114EB
0x1800114c1  test    byte ptr [rcx+1Ch], 40h
0x1800114c5  jz      short loc_1800114EB
0x1800114c7  cmp     byte ptr [rcx+19h], 4
0x1800114cb  jb      short loc_1800114EB
0x1800114cd  mov     edx, 1Bh
0x1800114d2  mov     dword ptr [rsp+78h+var_58], esi
0x1800114d6  mov     r9, [rbp+var_18]
0x1800114da  lea     r8, WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids
0x1800114e1  mov     rcx, [rcx+10h]
0x1800114e5  call    WPP_SF_Sd
0x1800114ea  nop
0x1800114eb  lea     rcx, [rbp+var_18]
0x1800114ef  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800114f4  nop
0x1800114f5  lea     rcx, [rbp+var_40]
0x1800114f9  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800114fe  nop
0x1800114ff  lea     rcx, [rbp+pszUrl]
0x180011503  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180011508  nop
0x180011509  lea     rcx, [rbp+var_10]
0x18001150d  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180011512  mov     eax, esi
0x180011514  add     rsp, 78h
0x180011518  pop     r15
0x18001151a  pop     r14
0x18001151c  pop     r13
0x18001151e  pop     r12
0x180011520  pop     rdi
0x180011521  pop     rsi
0x180011522  pop     rbx
0x180011523  pop     rbp
0x180011524  retn
```
