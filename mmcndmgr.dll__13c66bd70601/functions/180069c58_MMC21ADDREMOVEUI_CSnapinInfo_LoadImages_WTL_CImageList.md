# MMC21ADDREMOVEUI::CSnapinInfo::LoadImages(WTL::CImageList)

- ea: `0x180069c58`
- end: `0x18006a219`
- name: `?LoadImages@CSnapinInfo@MMC21ADDREMOVEUI@@QEAAXVCImageList@WTL@@@Z`
- size: `1473`
- prototype: ``
- caller_count: `5`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b30a0`
- `0x1800b4258`
- `0x1800b5f14`
- `0x1800b6824`
- `0x1800b86a0`

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
- `0x180069c58`
- `0x18006a9b4`
- `0x1800743b4`
- `0x18007c91c`
- `0x1800be538`
- `0x180134540`

## import_xrefs

- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180069c96`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180069c96`
- `mmcbase!?Clear@SC@mmcerror@@QEAAXXZ` at `0x180069f37`
- `mmcbase!?Clear@SC@mmcerror@@QEAAXXZ` at `0x180069fda`
- `mmcbase!?Clear@SC@mmcerror@@QEAAXXZ` at `0x180069f37`
- `mmcbase!?Clear@SC@mmcerror@@QEAAXXZ` at `0x180069fda`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x180069dc3`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x180069dc3`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180069d9b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180069dba`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180069d9b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180069dba`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180069f12`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180069fb5`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180069f12`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180069fb5`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180069ca9`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180069ca9`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180069da6`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180069f28`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180069fcb`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180069da6`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180069f28`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180069fcb`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180069f1d`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180069fc0`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006a1ed`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180069f1d`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180069fc0`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006a1ed`
- `msvcrt!_wtoi` at `0x18006a0ba`
- `msvcrt!_wtoi` at `0x18006a0ba`
- `msvcrt!wcsrchr` at `0x18006a05d`
- `msvcrt!wcsrchr` at `0x18006a05d`
- `USER32!DestroyIcon` at `0x18006a10c`
- `USER32!DestroyIcon` at `0x18006a10c`
- `ole32!CLSIDFromString` at `0x180069d8e`
- `ole32!CLSIDFromString` at `0x180069d8e`
- `SHELL32!ExtractIconExW` at `0x18006a0e1`
- `SHELL32!ExtractIconExW` at `0x18006a0e1`

## string_xrefs

- `0x180069e0f`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall MMC21ADDREMOVEUI::CSnapinInfo::LoadImages(__int64 a1, __int64 a2)
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
          (unsigned int)(v23 + 21),
          WPP_e6286f7ff16332d569bebdaa5a195f02_Traceguids);
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
        22,
        WPP_e6286f7ff16332d569bebdaa5a195f02_Traceguids,
        (unsigned int)v11);
    v12 = CStr::Append((CStr *)&v25, *(const unsigned __int16 **)(v8 + 24));
    if ( v12 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        23,
        WPP_e6286f7ff16332d569bebdaa5a195f02_Traceguids,
        (unsigned int)v12);
    v13 = CStr::Append((CStr *)&v25, L"\\DefaultIcon");
    if ( v13 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        24,
        WPP_e6286f7ff16332d569bebdaa5a195f02_Traceguids,
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
0x180069c58  mov     [rsp-8+arg_10], rbx
0x180069c5d  mov     [rsp-8+arg_8], rdx
0x180069c62  push    rbp
0x180069c63  push    rsi
0x180069c64  push    rdi
0x180069c65  push    r12
0x180069c67  push    r14
0x180069c69  lea     rbp, [rsp-1F0h]
0x180069c71  sub     rsp, 2F0h
0x180069c78  mov     rax, cs:__security_cookie
0x180069c7f  xor     rax, rsp
0x180069c82  mov     [rbp+210h+var_30], rax
0x180069c89  mov     rbx, rdx
0x180069c8c  mov     rdi, rcx
0x180069c8f  xor     edx, edx
0x180069c91  lea     rcx, [rsp+310h+var_298]
0x180069c96  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x180069c9c  nop
0x180069c9d  lea     rdx, aCsnapininfoLoa; "CSnapinInfo::LoadImages"
0x180069ca4  lea     rcx, [rsp+310h+var_298]
0x180069ca9  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x180069caf  cmp     dword ptr [rdi+78h], 0FFFFFFFFh
0x180069cb3  jnz     loc_18006A1E8
0x180069cb9  test    byte ptr [rdi+98h], 1
0x180069cc0  jz      short loc_180069CD1
0x180069cc2  cmp     dword ptr [rdi], 0
0x180069cc5  jnz     short loc_180069CD1
0x180069cc7  xor     edx, edx; int
0x180069cc9  mov     rcx, rdi; this
0x180069ccc  call    ?GetInformation@CSnapinAbout@@AEAAHH@Z; CSnapinAbout::GetInformation(int)
0x180069cd1  mov     rdx, [rdi+30h]; HBITMAP
0x180069cd5  mov     rsi, [rdi+38h]
0x180069cd9  mov     r14d, [rdi+48h]
0x180069cdd  test    rdx, rdx
0x180069ce0  jz      short loc_180069CF4
0x180069ce2  mov     r8d, r14d; int
0x180069ce5  lea     rcx, [rbp+210h+arg_8]; struct WTL::CImageList *
0x180069cec  call    ?AddWTLBitmapToWTLImagelist@@YAHAEAVCImageList@WTL@@PEAUHBITMAP__@@J@Z; AddWTLBitmapToWTLImagelist(WTL::CImageList &,HBITMAP__ *,long)
0x180069cf1  mov     [rdi+78h], eax
0x180069cf4  test    rsi, rsi
0x180069cf7  jz      short loc_180069D0D
0x180069cf9  mov     r8d, r14d; int
0x180069cfc  mov     rdx, rsi; HBITMAP
0x180069cff  lea     rcx, [rbp+210h+arg_8]; struct WTL::CImageList *
0x180069d06  call    ?AddWTLBitmapToWTLImagelist@@YAHAEAVCImageList@WTL@@PEAUHBITMAP__@@J@Z; AddWTLBitmapToWTLImagelist(WTL::CImageList &,HBITMAP__ *,long)
0x180069d0b  jmp     short loc_180069D10
0x180069d0d  mov     eax, [rdi+78h]
0x180069d10  mov     [rdi+7Ch], eax
0x180069d13  cmp     dword ptr [rdi+78h], 0FFFFFFFFh
0x180069d17  jnz     loc_18006A1AF
0x180069d1d  lea     rdx, [rsp+310h+var_2D8]
0x180069d22  mov     rcx, rdi
0x180069d25  call    ?GetSnapInReference@CSnapinAbout@@QEBA?AVCSnapInReferencePtr@@XZ; CSnapinAbout::GetSnapInReference(void)
0x180069d2a  nop
0x180069d2b  mov     r14, [rsp+310h+var_2D0]
0x180069d30  test    r14, r14
0x180069d33  jnz     short loc_180069D7F
0x180069d35  lea     rsi, WPP_GLOBAL_Control
0x180069d3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180069d43  cmp     rcx, rsi
0x180069d46  jz      short loc_180069D63
0x180069d48  cmp     byte ptr [rcx+19h], 3
0x180069d4c  jb      short loc_180069D63
0x180069d4e  lea     edx, [r14+15h]
0x180069d52  lea     r8, WPP_e6286f7ff16332d569bebdaa5a195f02_Traceguids
0x180069d59  mov     rcx, [rcx+10h]
0x180069d5d  call    WPP_SF_
0x180069d62  nop
0x180069d63  lea     rax, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x180069d6a  mov     [rsp+310h+var_2D8], rax
0x180069d6f  lea     rcx, [rsp+310h+var_2D8]; this
0x180069d74  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x180069d79  nop
0x180069d7a  jmp     loc_18006A177
0x180069d7f  xorps   xmm0, xmm0
0x180069d82  movups  xmmword ptr [rbp+210h+pclsid.Data1], xmm0
0x180069d86  lea     rdx, [rbp+210h+pclsid]; pclsid
0x180069d8a  mov     rcx, [r14+18h]; lpsz
0x180069d8e  call    cs:__imp_CLSIDFromString
0x180069d94  mov     edx, eax
0x180069d96  lea     rcx, [rsp+310h+var_298]
0x180069d9b  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180069da1  lea     rcx, [rsp+310h+var_298]
0x180069da6  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180069dac  test    al, al
0x180069dae  jz      short loc_180069DE6
0x180069db0  mov     edx, 8000FFFFh
0x180069db5  lea     rcx, [rsp+310h+var_298]
0x180069dba  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180069dc0  mov     rcx, rax
0x180069dc3  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x180069dc9  nop
0x180069dca  lea     rax, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x180069dd1  mov     [rsp+310h+var_2D8], rax
0x180069dd6  lea     rcx, [rsp+310h+var_2D8]; this
0x180069ddb  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x180069de0  nop
0x180069de1  jmp     loc_18006A177
0x180069de6  lea     r12, ??_7CStr@@6B@; const CStr::`vftable'
0x180069ded  mov     [rsp+310h+var_2C0], r12
0x180069df2  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x180069df9  mov     [rsp+310h+var_2B8], rax
0x180069dfe  mov     [rsp+310h+var_2B0], 0
0x180069e07  mov     [rsp+310h+var_2A8], 0
0x180069e0f  lea     rdx, aClsid; "CLSID\\"
0x180069e16  lea     rcx, [rsp+310h+var_2C0]; this
0x180069e1b  call    ?Assign@CStr@@QEAAJPEBG@Z; CStr::Assign(ushort const *)
0x180069e20  lea     rsi, WPP_GLOBAL_Control
0x180069e27  test    eax, eax
0x180069e29  jns     short loc_180069E55
0x180069e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180069e32  cmp     rcx, rsi
0x180069e35  jz      short loc_180069E55
0x180069e37  cmp     byte ptr [rcx+19h], 3
0x180069e3b  jb      short loc_180069E55
0x180069e3d  mov     edx, 16h
0x180069e42  mov     r9d, eax
0x180069e45  lea     r8, WPP_e6286f7ff16332d569bebdaa5a195f02_Traceguids
0x180069e4c  mov     rcx, [rcx+10h]
0x180069e50  call    WPP_SF_d
0x180069e55  mov     rdx, [r14+18h]; unsigned __int16 *
0x180069e59  lea     rcx, [rsp+310h+var_2C0]; this
0x180069e5e  call    ?Append@CStr@@QEAAJPEBG@Z; CStr::Append(ushort const *)
0x180069e63  test    eax, eax
0x180069e65  jns     short loc_180069E91
0x180069e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180069e6e  cmp     rcx, rsi
0x180069e71  jz      short loc_180069E91
0x180069e73  cmp     byte ptr [rcx+19h], 3
0x180069e77  jb      short loc_180069E91
0x180069e79  mov     edx, 17h
0x180069e7e  mov     r9d, eax
0x180069e81  lea     r8, WPP_e6286f7ff16332d569bebdaa5a195f02_Traceguids
0x180069e88  mov     rcx, [rcx+10h]
0x180069e8c  call    WPP_SF_d
0x180069e91  lea     rdx, aDefaulticon; "\\DefaultIcon"
0x180069e98  lea     rcx, [rsp+310h+var_2C0]; this
0x180069e9d  call    ?Append@CStr@@QEAAJPEBG@Z; CStr::Append(ushort const *)
0x180069ea2  test    eax, eax
0x180069ea4  jns     short loc_180069ED0
0x180069ea6  mov     rcx, cs:WPP_GLOBAL_Control
0x180069ead  cmp     rcx, rsi
0x180069eb0  jz      short loc_180069ED0
0x180069eb2  cmp     byte ptr [rcx+19h], 3
0x180069eb6  jb      short loc_180069ED0
0x180069eb8  mov     edx, 18h
0x180069ebd  mov     r9d, eax
0x180069ec0  lea     r8, WPP_e6286f7ff16332d569bebdaa5a195f02_Traceguids
0x180069ec7  mov     rcx, [rcx+10h]
0x180069ecb  call    WPP_SF_d
0x180069ed0  mov     [rbp+210h+var_280], 0
0x180069ed8  mov     [rbp+210h+var_278], 0
0x180069ee0  mov     [rbp+210h+var_270], 0
0x180069ee8  mov     [rsp+310h+nIcons], 1
0x180069ef0  mov     r9, [rsp+310h+var_2B8]
0x180069ef5  mov     r8, 0FFFFFFFF80000000h
0x180069efc  lea     rdx, [rbp+210h+var_268]
0x180069f00  lea     rcx, [rbp+210h+var_280]
0x180069f04  call    ?ScOpen@CRegKeyEx@@QEAA?AVSC@mmcerror@@PEAUHKEY__@@PEBGK@Z; CRegKeyEx::ScOpen(HKEY__ *,ushort const *,ulong)
0x180069f09  nop
0x180069f0a  mov     rdx, rax
0x180069f0d  lea     rcx, [rsp+310h+var_298]
0x180069f12  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180069f18  nop
0x180069f19  lea     rcx, [rbp+210h+var_268]
0x180069f1d  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180069f23  lea     rcx, [rsp+310h+var_298]
0x180069f28  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180069f2e  test    al, al
0x180069f30  jz      short loc_180069F74
0x180069f32  lea     rcx, [rsp+310h+var_298]
0x180069f37  call    cs:__imp_?Clear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::Clear(void)
0x180069f3d  nop
0x180069f3e  lea     rcx, [rbp+210h+var_280]; this
0x180069f42  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180069f47  nop
0x180069f48  mov     [rsp+310h+var_2C0], r12
0x180069f4d  lea     rcx, [rsp+310h+var_2C0]; this
0x180069f52  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180069f57  nop
0x180069f58  lea     rax, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x180069f5f  mov     [rsp+310h+var_2D8], rax
0x180069f64  lea     rcx, [rsp+310h+var_2D8]; this
0x180069f69  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x180069f6e  nop
0x180069f6f  jmp     loc_18006A177
0x180069f74  mov     [rsp+310h+var_2A0], 208h
0x180069f7c  mov     [rsp+310h+var_2C8], 0
0x180069f84  lea     rax, [rsp+310h+var_2A0]
0x180069f89  mov     [rsp+310h+var_2E8], rax
0x180069f8e  lea     rax, [rbp+210h+Str]
0x180069f92  mov     qword ptr [rsp+310h+nIcons], rax
0x180069f97  lea     r9, [rsp+310h+var_2C8]
0x180069f9c  xor     r8d, r8d
0x180069f9f  lea     rdx, [rbp+210h+var_268]
0x180069fa3  lea     rcx, [rbp+210h+var_280]
0x180069fa7  call    ?ScQueryValue@CRegKeyEx@@QEAA?AVSC@mmcerror@@PEBGPEAKPEAX1@Z; CRegKeyEx::ScQueryValue(ushort const *,ulong *,void *,ulong *)
0x180069fac  nop
0x180069fad  mov     rdx, rax
0x180069fb0  lea     rcx, [rsp+310h+var_298]
0x180069fb5  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180069fbb  nop
0x180069fbc  lea     rcx, [rbp+210h+var_268]
0x180069fc0  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180069fc6  lea     rcx, [rsp+310h+var_298]
0x180069fcb  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180069fd1  test    al, al
0x180069fd3  jz      short loc_18006A017
0x180069fd5  lea     rcx, [rsp+310h+var_298]
0x180069fda  call    cs:__imp_?Clear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::Clear(void)
0x180069fe0  nop
0x180069fe1  lea     rcx, [rbp+210h+var_280]; this
0x180069fe5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180069fea  nop
0x180069feb  mov     [rsp+310h+var_2C0], r12
0x180069ff0  lea     rcx, [rsp+310h+var_2C0]; this
0x180069ff5  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180069ffa  nop
0x180069ffb  lea     rax, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x18006a002  mov     [rsp+310h+var_2D8], rax
0x18006a007  lea     rcx, [rsp+310h+var_2D8]; this
0x18006a00c  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x18006a011  nop
0x18006a012  jmp     loc_18006A177
0x18006a017  cmp     [rsp+310h+var_2C8], 1
0x18006a01c  jz      short loc_18006A054
0x18006a01e  lea     rcx, [rbp+210h+var_280]; this
0x18006a022  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006a027  nop
0x18006a028  mov     [rsp+310h+var_2C0], r12
0x18006a02d  lea     rcx, [rsp+310h+var_2C0]; this
0x18006a032  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18006a037  nop
0x18006a038  lea     rax, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x18006a03f  mov     [rsp+310h+var_2D8], rax
0x18006a044  lea     rcx, [rsp+310h+var_2D8]; this
0x18006a049  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x18006a04e  nop
0x18006a04f  jmp     loc_18006A177
0x18006a054  xor     esi, esi
0x18006a056  lea     edx, [rsi+2Ch]; Ch
0x18006a059  lea     rcx, [rbp+210h+Str]; Str
0x18006a05d  call    cs:__imp_wcsrchr
0x18006a063  test    rax, rax
0x18006a066  jz      short loc_18006A0C2
0x18006a068  xor     ecx, ecx
0x18006a06a  mov     [rax], cx
0x18006a06d  lea     rcx, [rax+2]; String
0x18006a071  movzx   eax, word ptr [rcx]
0x18006a074  cmp     ax, 2Dh ; '-'
0x18006a078  jz      short loc_18006A0BA
0x18006a07a  sub     ax, 30h ; '0'
0x18006a07e  cmp     ax, 9
0x18006a082  jbe     short loc_18006A0BA
0x18006a084  lea     rcx, [rbp+210h+var_280]; this
0x18006a088  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006a08d  nop
0x18006a08e  mov     [rsp+310h+var_2C0], r12
0x18006a093  lea     rcx, [rsp+310h+var_2C0]; this
0x18006a098  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18006a09d  nop
0x18006a09e  lea     rax, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x18006a0a5  mov     [rsp+310h+var_2D8], rax
0x18006a0aa  lea     rcx, [rsp+310h+var_2D8]; this
0x18006a0af  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x18006a0b4  nop
0x18006a0b5  jmp     loc_18006A177
0x18006a0ba  call    cs:__imp__wtoi
0x18006a0c0  mov     esi, eax
0x18006a0c2  mov     [rsp+310h+phiconSmall], 0
0x18006a0cb  mov     [rsp+310h+nIcons], 1; nIcons
0x18006a0d3  lea     r9, [rsp+310h+phiconSmall]; phiconSmall
0x18006a0d8  xor     r8d, r8d; phiconLarge
0x18006a0db  mov     edx, esi; nIconIndex
0x18006a0dd  lea     rcx, [rbp+210h+Str]; lpszFile
0x18006a0e1  call    cs:__imp_ExtractIconExW
0x18006a0e7  cmp     eax, 1
0x18006a0ea  jnz     short loc_18006A146
0x18006a0ec  mov     r8, [rsp+310h+phiconSmall]
0x18006a0f1  test    r8, r8
0x18006a0f4  jz      short loc_18006A146
0x18006a0f6  or      edx, 0FFFFFFFFh
0x18006a0f9  mov     rcx, rbx
0x18006a0fc  call    IsolationAwareImageList_ReplaceIcon
0x18006a101  mov     [rdi+7Ch], eax
0x18006a104  mov     [rdi+78h], eax
0x18006a107  mov     rcx, [rsp+310h+phiconSmall]; hIcon
0x18006a10c  call    cs:__imp_DestroyIcon
0x18006a112  nop
0x18006a113  lea     rcx, [rbp+210h+var_280]; this
0x18006a117  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006a11c  nop
0x18006a11d  mov     [rsp+310h+var_2C0], r12
0x18006a122  lea     rcx, [rsp+310h+var_2C0]; this
0x18006a127  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18006a12c  nop
0x18006a12d  lea     rax, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x18006a134  mov     [rsp+310h+var_2D8], rax
0x18006a139  lea     rcx, [rsp+310h+var_2D8]; this
0x18006a13e  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
  ... truncated ...
```
