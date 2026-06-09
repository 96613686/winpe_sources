# CSnapinInfo::LoadImages(WTL::CImageList)

- ea: `0x18006a220`
- end: `0x18006a7e1`
- name: `?LoadImages@CSnapinInfo@@QEAAXVCImageList@WTL@@@Z`
- size: `1473`
- prototype: ``
- caller_count: `6`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005d3e4`
- `0x180069540`
- `0x18007615c`
- `0x180077cdc`
- `0x180078614`
- `0x180079450`

## callees

- `0x1800063c0`
- `0x180006cf0`
- `0x1800074d0`
- `0x180015b98`
- `0x180016ba0`
- `0x180026ac8`
- `0x18002cd60`
- `0x18003b7fc`
- `0x180044740`
- `0x180044e84`
- `0x18004c7c8`
- `0x180057074`
- `0x18006a220`
- `0x18006a9b4`
- `0x1800743b4`
- `0x18007c91c`
- `0x1800be538`
- `0x180134540`

## import_xrefs

- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18006a25e`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18006a25e`
- `mmcbase!?Clear@SC@mmcerror@@QEAAXXZ` at `0x18006a4ff`
- `mmcbase!?Clear@SC@mmcerror@@QEAAXXZ` at `0x18006a5a2`
- `mmcbase!?Clear@SC@mmcerror@@QEAAXXZ` at `0x18006a4ff`
- `mmcbase!?Clear@SC@mmcerror@@QEAAXXZ` at `0x18006a5a2`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x18006a38b`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x18006a38b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006a363`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006a382`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006a363`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006a382`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18006a4da`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18006a57d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18006a4da`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18006a57d`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18006a271`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18006a271`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18006a36e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18006a4f0`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18006a593`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18006a36e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18006a4f0`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18006a593`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006a4e5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006a588`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006a7b5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006a4e5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006a588`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006a7b5`
- `msvcrt!_wtoi` at `0x18006a682`
- `msvcrt!_wtoi` at `0x18006a682`
- `msvcrt!wcsrchr` at `0x18006a625`
- `msvcrt!wcsrchr` at `0x18006a625`
- `USER32!DestroyIcon` at `0x18006a6d4`
- `USER32!DestroyIcon` at `0x18006a6d4`
- `ole32!CLSIDFromString` at `0x18006a356`
- `ole32!CLSIDFromString` at `0x18006a356`
- `SHELL32!ExtractIconExW` at `0x18006a6a9`
- `SHELL32!ExtractIconExW` at `0x18006a6a9`

## string_xrefs

- `0x18006a3d7`: `CLSID\`

## pseudocode

```c
void __fastcall CSnapinInfo::LoadImages(__int64 a1, __int64 a2)
{
  HBITMAP v4; // rdx
  HBITMAP v5; // rsi
  int v6; // r14d
  int v7; // eax
  __int64 v8; // r14
  unsigned int v9; // eax
  mmcerror::SC *v10; // rax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // esi
  wchar_t *v17; // rax
  const wchar_t *v18; // rcx
  wchar_t v19; // ax
  int v20; // eax
  HICON phiconSmall; // [rsp+30h] [rbp-D0h] BYREF
  void **v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h]
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  void **v25; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR *v26; // [rsp+58h] [rbp-A8h]
  __int64 v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+68h] [rbp-98h]
  int v29; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[24]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v31[3]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v32[24]; // [rsp+A8h] [rbp-58h] BYREF
  GUID pclsid; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Str[264]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v35; // [rsp+328h] [rbp+228h] BYREF

  v35 = a2;
  mmcerror::SC::SC((mmcerror::SC *)v30, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v30, L"CSnapinInfo::LoadImages");
  if ( *(_DWORD *)(a1 + 120) != -1 )
    goto LABEL_47;
  if ( (*(_BYTE *)(a1 + 152) & 1) != 0 && !*(_DWORD *)a1 )
    CSnapinAbout::GetInformation((CSnapinAbout *)a1, 0);
  v4 = *(HBITMAP *)(a1 + 48);
  v5 = *(HBITMAP *)(a1 + 56);
  v6 = *(_DWORD *)(a1 + 72);
  if ( v4 )
    *(_DWORD *)(a1 + 120) = AddWTLBitmapToWTLImagelist((struct WTL::CImageList *)&v35, v4, v6);
  if ( v5 )
    v7 = AddWTLBitmapToWTLImagelist((struct WTL::CImageList *)&v35, v5, v6);
  else
    v7 = *(_DWORD *)(a1 + 120);
  *(_DWORD *)(a1 + 124) = v7;
  if ( *(_DWORD *)(a1 + 120) == -1 )
  {
    CSnapinAbout::GetSnapInReference(a1, &v22);
    v8 = v23;
    if ( !v23 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
        WPP_SF_(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)(v23 + 17),
          WPP_ee98353176bb36a24e89b23920f5a524_Traceguids);
      v22 = &CSnapInReferencePtr::`vftable';
      CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v22);
      goto LABEL_43;
    }
    pclsid = 0;
    v9 = CLSIDFromString(*(LPCOLESTR *)(v23 + 24), &pclsid);
    mmcerror::SC::operator=(v30, v9);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v30) )
    {
      v10 = (mmcerror::SC *)mmcerror::SC::operator=(v30, 2147549183LL);
      mmcerror::SC::TraceAndClear(v10);
      v22 = &CSnapInReferencePtr::`vftable';
      CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v22);
      goto LABEL_43;
    }
    v25 = &CStr::`vftable';
    v26 = &CStr::s_rgwchEmptyStringBuffer;
    v27 = 0;
    v28 = 0;
    v11 = CStr::Assign((CStr *)&v25, L"CLSID\\");
    if ( v11 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        18,
        WPP_ee98353176bb36a24e89b23920f5a524_Traceguids,
        (unsigned int)v11);
    v12 = CStr::Append((CStr *)&v25, *(const unsigned __int16 **)(v8 + 24));
    if ( v12 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        19,
        WPP_ee98353176bb36a24e89b23920f5a524_Traceguids,
        (unsigned int)v12);
    v13 = CStr::Append((CStr *)&v25, L"\\DefaultIcon");
    if ( v13 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        20,
        WPP_ee98353176bb36a24e89b23920f5a524_Traceguids,
        (unsigned int)v13);
    memset(v31, 0, sizeof(v31));
    v14 = CRegKeyEx::ScOpen(v31, v32, 0xFFFFFFFF80000000uLL, v26, 1);
    mmcerror::SC::operator=(v30, v14);
    mmcerror::SC::~SC((mmcerror::SC *)v32);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v30)
      || (v29 = 520,
          v24 = 0,
          v15 = CRegKeyEx::ScQueryValue(v31, v32, 0, &v24, Str, &v29),
          mmcerror::SC::operator=(v30, v15),
          mmcerror::SC::~SC((mmcerror::SC *)v32),
          (unsigned __int8)mmcerror::SC::operator bool(v30)) )
    {
      mmcerror::SC::Clear((mmcerror::SC *)v30);
      ATL::CRegKey::Close((ATL::CRegKey *)v31);
      v25 = &CStr::`vftable';
      CStr::Empty((CStr *)&v25);
      v22 = &CSnapInReferencePtr::`vftable';
      CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v22);
      goto LABEL_43;
    }
    if ( v24 != 1 )
      goto LABEL_34;
    v16 = 0;
    v17 = wcsrchr(Str, 0x2Cu);
    if ( v17 )
    {
      *v17 = 0;
      v18 = v17 + 1;
      v19 = v17[1];
      if ( v19 != 45 && (unsigned __int16)(v19 - 48) > 9u )
      {
LABEL_34:
        ATL::CRegKey::Close((ATL::CRegKey *)v31);
        v25 = &CStr::`vftable';
        CStr::Empty((CStr *)&v25);
        v22 = &CSnapInReferencePtr::`vftable';
        CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v22);
        goto LABEL_43;
      }
      v16 = _wtoi(v18);
    }
    phiconSmall = 0;
    if ( ExtractIconExW(Str, v16, 0, &phiconSmall, 1u) == 1 && phiconSmall )
    {
      v20 = IsolationAwareImageList_ReplaceIcon(a2, 0xFFFFFFFFLL, phiconSmall);
      *(_DWORD *)(a1 + 124) = v20;
      *(_DWORD *)(a1 + 120) = v20;
      DestroyIcon(phiconSmall);
      ATL::CRegKey::Close((ATL::CRegKey *)v31);
      v25 = &CStr::`vftable';
      CStr::Empty((CStr *)&v25);
      v22 = &CSnapInReferencePtr::`vftable';
      CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v22);
    }
    else
    {
      ATL::CRegKey::Close((ATL::CRegKey *)v31);
      v25 = &CStr::`vftable';
      CStr::Empty((CStr *)&v25);
      v22 = &CSnapInReferencePtr::`vftable';
      CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v22);
    }
LABEL_43:
    if ( *(_DWORD *)(a1 + 120) == -1 )
    {
      phiconSmall = 0;
      LoadResourceToWTLCBitmap(&phiconSmall, 1088);
      *(_DWORD *)(a1 + 120) = IsolationAwareImageList_Add(a2, phiconSmall);
      WTL::CFontT<1>::~CFontT<1>(&phiconSmall);
    }
  }
  if ( *(_DWORD *)(a1 + 124) == -1 )
  {
    phiconSmall = 0;
    LoadResourceToWTLCBitmap(&phiconSmall, 1090);
    *(_DWORD *)(a1 + 124) = IsolationAwareImageList_Add(a2, phiconSmall);
    WTL::CFontT<1>::~CFontT<1>(&phiconSmall);
  }
LABEL_47:
  mmcerror::SC::~SC((mmcerror::SC *)v30);
}

```

## disassembly

```asm
0x18006a220  mov     [rsp-8+arg_10], rbx
0x18006a225  mov     [rsp-8+arg_8], rdx
0x18006a22a  push    rbp
0x18006a22b  push    rsi
0x18006a22c  push    rdi
0x18006a22d  push    r12
0x18006a22f  push    r14
0x18006a231  lea     rbp, [rsp-1F0h]
0x18006a239  sub     rsp, 2F0h
0x18006a240  mov     rax, cs:__security_cookie
0x18006a247  xor     rax, rsp
0x18006a24a  mov     [rbp+210h+var_30], rax
0x18006a251  mov     rbx, rdx
0x18006a254  mov     rdi, rcx
0x18006a257  xor     edx, edx
0x18006a259  lea     rcx, [rsp+310h+var_298]
0x18006a25e  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18006a264  nop
0x18006a265  lea     rdx, aCsnapininfoLoa; "CSnapinInfo::LoadImages"
0x18006a26c  lea     rcx, [rsp+310h+var_298]
0x18006a271  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18006a277  cmp     dword ptr [rdi+78h], 0FFFFFFFFh
0x18006a27b  jnz     loc_18006A7B0
0x18006a281  test    byte ptr [rdi+98h], 1
0x18006a288  jz      short loc_18006A299
0x18006a28a  cmp     dword ptr [rdi], 0
0x18006a28d  jnz     short loc_18006A299
0x18006a28f  xor     edx, edx; int
0x18006a291  mov     rcx, rdi; this
0x18006a294  call    ?GetInformation@CSnapinAbout@@AEAAHH@Z; CSnapinAbout::GetInformation(int)
0x18006a299  mov     rdx, [rdi+30h]; HBITMAP
0x18006a29d  mov     rsi, [rdi+38h]
0x18006a2a1  mov     r14d, [rdi+48h]
0x18006a2a5  test    rdx, rdx
0x18006a2a8  jz      short loc_18006A2BC
0x18006a2aa  mov     r8d, r14d; int
0x18006a2ad  lea     rcx, [rbp+210h+arg_8]; struct WTL::CImageList *
0x18006a2b4  call    ?AddWTLBitmapToWTLImagelist@@YAHAEAVCImageList@WTL@@PEAUHBITMAP__@@J@Z; AddWTLBitmapToWTLImagelist(WTL::CImageList &,HBITMAP__ *,long)
0x18006a2b9  mov     [rdi+78h], eax
0x18006a2bc  test    rsi, rsi
0x18006a2bf  jz      short loc_18006A2D5
0x18006a2c1  mov     r8d, r14d; int
0x18006a2c4  mov     rdx, rsi; HBITMAP
0x18006a2c7  lea     rcx, [rbp+210h+arg_8]; struct WTL::CImageList *
0x18006a2ce  call    ?AddWTLBitmapToWTLImagelist@@YAHAEAVCImageList@WTL@@PEAUHBITMAP__@@J@Z; AddWTLBitmapToWTLImagelist(WTL::CImageList &,HBITMAP__ *,long)
0x18006a2d3  jmp     short loc_18006A2D8
0x18006a2d5  mov     eax, [rdi+78h]
0x18006a2d8  mov     [rdi+7Ch], eax
0x18006a2db  cmp     dword ptr [rdi+78h], 0FFFFFFFFh
0x18006a2df  jnz     loc_18006A777
0x18006a2e5  lea     rdx, [rsp+310h+var_2D8]
0x18006a2ea  mov     rcx, rdi
0x18006a2ed  call    ?GetSnapInReference@CSnapinAbout@@QEBA?AVCSnapInReferencePtr@@XZ; CSnapinAbout::GetSnapInReference(void)
0x18006a2f2  nop
0x18006a2f3  mov     r14, [rsp+310h+var_2D0]
0x18006a2f8  test    r14, r14
0x18006a2fb  jnz     short loc_18006A347
0x18006a2fd  lea     rsi, WPP_GLOBAL_Control
0x18006a304  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a30b  cmp     rcx, rsi
0x18006a30e  jz      short loc_18006A32B
0x18006a310  cmp     byte ptr [rcx+19h], 3
0x18006a314  jb      short loc_18006A32B
0x18006a316  lea     edx, [r14+11h]
0x18006a31a  lea     r8, WPP_ee98353176bb36a24e89b23920f5a524_Traceguids
0x18006a321  mov     rcx, [rcx+10h]
0x18006a325  call    WPP_SF_
0x18006a32a  nop
0x18006a32b  lea     rax, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x18006a332  mov     [rsp+310h+var_2D8], rax
0x18006a337  lea     rcx, [rsp+310h+var_2D8]; this
0x18006a33c  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x18006a341  nop
0x18006a342  jmp     loc_18006A73F
0x18006a347  xorps   xmm0, xmm0
0x18006a34a  movups  xmmword ptr [rbp+210h+pclsid.Data1], xmm0
0x18006a34e  lea     rdx, [rbp+210h+pclsid]; pclsid
0x18006a352  mov     rcx, [r14+18h]; lpsz
0x18006a356  call    cs:__imp_CLSIDFromString
0x18006a35c  mov     edx, eax
0x18006a35e  lea     rcx, [rsp+310h+var_298]
0x18006a363  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18006a369  lea     rcx, [rsp+310h+var_298]
0x18006a36e  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18006a374  test    al, al
0x18006a376  jz      short loc_18006A3AE
0x18006a378  mov     edx, 8000FFFFh
0x18006a37d  lea     rcx, [rsp+310h+var_298]
0x18006a382  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18006a388  mov     rcx, rax
0x18006a38b  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x18006a391  nop
0x18006a392  lea     rax, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x18006a399  mov     [rsp+310h+var_2D8], rax
0x18006a39e  lea     rcx, [rsp+310h+var_2D8]; this
0x18006a3a3  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x18006a3a8  nop
0x18006a3a9  jmp     loc_18006A73F
0x18006a3ae  lea     r12, ??_7CStr@@6B@; const CStr::`vftable'
0x18006a3b5  mov     [rsp+310h+var_2C0], r12
0x18006a3ba  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x18006a3c1  mov     [rsp+310h+var_2B8], rax
0x18006a3c6  mov     [rsp+310h+var_2B0], 0
0x18006a3cf  mov     [rsp+310h+var_2A8], 0
0x18006a3d7  lea     rdx, aClsid; "CLSID\\"
0x18006a3de  lea     rcx, [rsp+310h+var_2C0]; this
0x18006a3e3  call    ?Assign@CStr@@QEAAJPEBG@Z; CStr::Assign(ushort const *)
0x18006a3e8  lea     rsi, WPP_GLOBAL_Control
0x18006a3ef  test    eax, eax
0x18006a3f1  jns     short loc_18006A41D
0x18006a3f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a3fa  cmp     rcx, rsi
0x18006a3fd  jz      short loc_18006A41D
0x18006a3ff  cmp     byte ptr [rcx+19h], 3
0x18006a403  jb      short loc_18006A41D
0x18006a405  mov     edx, 12h
0x18006a40a  mov     r9d, eax
0x18006a40d  lea     r8, WPP_ee98353176bb36a24e89b23920f5a524_Traceguids
0x18006a414  mov     rcx, [rcx+10h]
0x18006a418  call    WPP_SF_d
0x18006a41d  mov     rdx, [r14+18h]; unsigned __int16 *
0x18006a421  lea     rcx, [rsp+310h+var_2C0]; this
0x18006a426  call    ?Append@CStr@@QEAAJPEBG@Z; CStr::Append(ushort const *)
0x18006a42b  test    eax, eax
0x18006a42d  jns     short loc_18006A459
0x18006a42f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a436  cmp     rcx, rsi
0x18006a439  jz      short loc_18006A459
0x18006a43b  cmp     byte ptr [rcx+19h], 3
0x18006a43f  jb      short loc_18006A459
0x18006a441  mov     edx, 13h
0x18006a446  mov     r9d, eax
0x18006a449  lea     r8, WPP_ee98353176bb36a24e89b23920f5a524_Traceguids
0x18006a450  mov     rcx, [rcx+10h]
0x18006a454  call    WPP_SF_d
0x18006a459  lea     rdx, aDefaulticon; "\\DefaultIcon"
0x18006a460  lea     rcx, [rsp+310h+var_2C0]; this
0x18006a465  call    ?Append@CStr@@QEAAJPEBG@Z; CStr::Append(ushort const *)
0x18006a46a  test    eax, eax
0x18006a46c  jns     short loc_18006A498
0x18006a46e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a475  cmp     rcx, rsi
0x18006a478  jz      short loc_18006A498
0x18006a47a  cmp     byte ptr [rcx+19h], 3
0x18006a47e  jb      short loc_18006A498
0x18006a480  mov     edx, 14h
0x18006a485  mov     r9d, eax
0x18006a488  lea     r8, WPP_ee98353176bb36a24e89b23920f5a524_Traceguids
0x18006a48f  mov     rcx, [rcx+10h]
0x18006a493  call    WPP_SF_d
0x18006a498  mov     [rbp+210h+var_280], 0
0x18006a4a0  mov     [rbp+210h+var_278], 0
0x18006a4a8  mov     [rbp+210h+var_270], 0
0x18006a4b0  mov     [rsp+310h+nIcons], 1
0x18006a4b8  mov     r9, [rsp+310h+var_2B8]
0x18006a4bd  mov     r8, 0FFFFFFFF80000000h
0x18006a4c4  lea     rdx, [rbp+210h+var_268]
0x18006a4c8  lea     rcx, [rbp+210h+var_280]
0x18006a4cc  call    ?ScOpen@CRegKeyEx@@QEAA?AVSC@mmcerror@@PEAUHKEY__@@PEBGK@Z; CRegKeyEx::ScOpen(HKEY__ *,ushort const *,ulong)
0x18006a4d1  nop
0x18006a4d2  mov     rdx, rax
0x18006a4d5  lea     rcx, [rsp+310h+var_298]
0x18006a4da  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18006a4e0  nop
0x18006a4e1  lea     rcx, [rbp+210h+var_268]
0x18006a4e5  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18006a4eb  lea     rcx, [rsp+310h+var_298]
0x18006a4f0  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18006a4f6  test    al, al
0x18006a4f8  jz      short loc_18006A53C
0x18006a4fa  lea     rcx, [rsp+310h+var_298]
0x18006a4ff  call    cs:__imp_?Clear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::Clear(void)
0x18006a505  nop
0x18006a506  lea     rcx, [rbp+210h+var_280]; this
0x18006a50a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006a50f  nop
0x18006a510  mov     [rsp+310h+var_2C0], r12
0x18006a515  lea     rcx, [rsp+310h+var_2C0]; this
0x18006a51a  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18006a51f  nop
0x18006a520  lea     rax, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x18006a527  mov     [rsp+310h+var_2D8], rax
0x18006a52c  lea     rcx, [rsp+310h+var_2D8]; this
0x18006a531  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x18006a536  nop
0x18006a537  jmp     loc_18006A73F
0x18006a53c  mov     [rsp+310h+var_2A0], 208h
0x18006a544  mov     [rsp+310h+var_2C8], 0
0x18006a54c  lea     rax, [rsp+310h+var_2A0]
0x18006a551  mov     [rsp+310h+var_2E8], rax
0x18006a556  lea     rax, [rbp+210h+Str]
0x18006a55a  mov     qword ptr [rsp+310h+nIcons], rax
0x18006a55f  lea     r9, [rsp+310h+var_2C8]
0x18006a564  xor     r8d, r8d
0x18006a567  lea     rdx, [rbp+210h+var_268]
0x18006a56b  lea     rcx, [rbp+210h+var_280]
0x18006a56f  call    ?ScQueryValue@CRegKeyEx@@QEAA?AVSC@mmcerror@@PEBGPEAKPEAX1@Z; CRegKeyEx::ScQueryValue(ushort const *,ulong *,void *,ulong *)
0x18006a574  nop
0x18006a575  mov     rdx, rax
0x18006a578  lea     rcx, [rsp+310h+var_298]
0x18006a57d  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18006a583  nop
0x18006a584  lea     rcx, [rbp+210h+var_268]
0x18006a588  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18006a58e  lea     rcx, [rsp+310h+var_298]
0x18006a593  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18006a599  test    al, al
0x18006a59b  jz      short loc_18006A5DF
0x18006a59d  lea     rcx, [rsp+310h+var_298]
0x18006a5a2  call    cs:__imp_?Clear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::Clear(void)
0x18006a5a8  nop
0x18006a5a9  lea     rcx, [rbp+210h+var_280]; this
0x18006a5ad  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006a5b2  nop
0x18006a5b3  mov     [rsp+310h+var_2C0], r12
0x18006a5b8  lea     rcx, [rsp+310h+var_2C0]; this
0x18006a5bd  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18006a5c2  nop
0x18006a5c3  lea     rax, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x18006a5ca  mov     [rsp+310h+var_2D8], rax
0x18006a5cf  lea     rcx, [rsp+310h+var_2D8]; this
0x18006a5d4  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x18006a5d9  nop
0x18006a5da  jmp     loc_18006A73F
0x18006a5df  cmp     [rsp+310h+var_2C8], 1
0x18006a5e4  jz      short loc_18006A61C
0x18006a5e6  lea     rcx, [rbp+210h+var_280]; this
0x18006a5ea  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006a5ef  nop
0x18006a5f0  mov     [rsp+310h+var_2C0], r12
0x18006a5f5  lea     rcx, [rsp+310h+var_2C0]; this
0x18006a5fa  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18006a5ff  nop
0x18006a600  lea     rax, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x18006a607  mov     [rsp+310h+var_2D8], rax
0x18006a60c  lea     rcx, [rsp+310h+var_2D8]; this
0x18006a611  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x18006a616  nop
0x18006a617  jmp     loc_18006A73F
0x18006a61c  xor     esi, esi
0x18006a61e  lea     edx, [rsi+2Ch]; Ch
0x18006a621  lea     rcx, [rbp+210h+Str]; Str
0x18006a625  call    cs:__imp_wcsrchr
0x18006a62b  test    rax, rax
0x18006a62e  jz      short loc_18006A68A
0x18006a630  xor     ecx, ecx
0x18006a632  mov     [rax], cx
0x18006a635  lea     rcx, [rax+2]; String
0x18006a639  movzx   eax, word ptr [rcx]
0x18006a63c  cmp     ax, 2Dh ; '-'
0x18006a640  jz      short loc_18006A682
0x18006a642  sub     ax, 30h ; '0'
0x18006a646  cmp     ax, 9
0x18006a64a  jbe     short loc_18006A682
0x18006a64c  lea     rcx, [rbp+210h+var_280]; this
0x18006a650  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006a655  nop
0x18006a656  mov     [rsp+310h+var_2C0], r12
0x18006a65b  lea     rcx, [rsp+310h+var_2C0]; this
0x18006a660  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18006a665  nop
0x18006a666  lea     rax, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x18006a66d  mov     [rsp+310h+var_2D8], rax
0x18006a672  lea     rcx, [rsp+310h+var_2D8]; this
0x18006a677  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x18006a67c  nop
0x18006a67d  jmp     loc_18006A73F
0x18006a682  call    cs:__imp__wtoi
0x18006a688  mov     esi, eax
0x18006a68a  mov     [rsp+310h+phiconSmall], 0
0x18006a693  mov     [rsp+310h+nIcons], 1; nIcons
0x18006a69b  lea     r9, [rsp+310h+phiconSmall]; phiconSmall
0x18006a6a0  xor     r8d, r8d; phiconLarge
0x18006a6a3  mov     edx, esi; nIconIndex
0x18006a6a5  lea     rcx, [rbp+210h+Str]; lpszFile
0x18006a6a9  call    cs:__imp_ExtractIconExW
0x18006a6af  cmp     eax, 1
0x18006a6b2  jnz     short loc_18006A70E
0x18006a6b4  mov     r8, [rsp+310h+phiconSmall]
0x18006a6b9  test    r8, r8
0x18006a6bc  jz      short loc_18006A70E
0x18006a6be  or      edx, 0FFFFFFFFh
0x18006a6c1  mov     rcx, rbx
0x18006a6c4  call    IsolationAwareImageList_ReplaceIcon
0x18006a6c9  mov     [rdi+7Ch], eax
0x18006a6cc  mov     [rdi+78h], eax
0x18006a6cf  mov     rcx, [rsp+310h+phiconSmall]; hIcon
0x18006a6d4  call    cs:__imp_DestroyIcon
0x18006a6da  nop
0x18006a6db  lea     rcx, [rbp+210h+var_280]; this
0x18006a6df  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006a6e4  nop
0x18006a6e5  mov     [rsp+310h+var_2C0], r12
0x18006a6ea  lea     rcx, [rsp+310h+var_2C0]; this
0x18006a6ef  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18006a6f4  nop
0x18006a6f5  lea     rax, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x18006a6fc  mov     [rsp+310h+var_2D8], rax
0x18006a701  lea     rcx, [rsp+310h+var_2D8]; this
0x18006a706  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
  ... truncated ...
```
