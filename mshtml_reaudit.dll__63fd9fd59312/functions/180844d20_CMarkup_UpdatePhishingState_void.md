# CMarkup::UpdatePhishingState(void)

- ea: `0x180844d20`
- end: `0x180845350`
- name: `?UpdatePhishingState@CMarkup@@QEAAJXZ`
- size: `1584`
- prototype: `__int64 __fastcall(CMarkup *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180844454`

## callees

- `0x1800019fc`
- `0x1800148b0`
- `0x1800f5454`
- `0x180135278`
- `0x180154a54`
- `0x1801bf528`
- `0x1801c0b08`
- `0x180223a8c`
- `0x18028ecdc`
- `0x1802e5024`
- `0x180300fa8`
- `0x18058e5d0`
- `0x18063b8a8`
- `0x180771b58`
- `0x180774afc`
- `0x1807da0a0`
- `0x180844144`
- `0x180844398`
- `0x1808448f4`
- `0x1808449f4`
- `0x180844d20`
- `0x180845358`
- `0x18086debc`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1808450d3`
- `KERNEL32!GetCurrentThreadId` at `0x1808450d3`
- `iertutil!CreateUri` at `0x180844eb2`
- `iertutil!CreateUri` at `0x180844f0d`
- `iertutil!CreateUri` at `0x180844eb2`
- `iertutil!CreateUri` at `0x180844f0d`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180845200`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180845200`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180845128`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180845128`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180845180`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180845180`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1808450e7`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1808450e7`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x180845119`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x180845119`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808451f1`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808451f1`
- `urlmon!__imp_?IECompatLogAntiphishingUrl@@YAXPEBGK@Z` at `0x180845035`
- `urlmon!__imp_?IECompatLogAntiphishingUrl@@YAXPEBGK@Z` at `0x1808452d0`
- `urlmon!__imp_?IECompatLogAntiphishingUrl@@YAXPEBGK@Z` at `0x180845035`
- `urlmon!__imp_?IECompatLogAntiphishingUrl@@YAXPEBGK@Z` at `0x1808452d0`
- `OLEAUT32!__imp_SysFreeString` at `0x180845264`
- `OLEAUT32!__imp_SysFreeString` at `0x18084527d`
- `OLEAUT32!__imp_SysFreeString` at `0x180845264`
- `OLEAUT32!__imp_SysFreeString` at `0x18084527d`
- `OLEAUT32!__imp_SysStringLen` at `0x180844ee4`
- `OLEAUT32!__imp_SysStringLen` at `0x180844f68`
- `OLEAUT32!__imp_SysStringLen` at `0x180844fcd`
- `OLEAUT32!__imp_SysStringLen` at `0x180844ee4`
- `OLEAUT32!__imp_SysStringLen` at `0x180844f68`
- `OLEAUT32!__imp_SysStringLen` at `0x180844fcd`
- `OLEAUT32!__imp_VariantClear` at `0x180845287`
- `OLEAUT32!__imp_VariantClear` at `0x180845318`
- `OLEAUT32!__imp_VariantClear` at `0x180845287`
- `OLEAUT32!__imp_VariantClear` at `0x180845318`

## pseudocode

```c
__int64 __fastcall CMarkup::UpdatePhishingState(CMarkup *this)
{
  CMarkup *v2; // rcx
  struct CWindow *v3; // r8
  __int64 v4; // rax
  __int64 v5; // r14
  _DWORD *v6; // rcx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  __int64 v11; // rcx
  UINT v12; // eax
  __int64 v13; // rcx
  unsigned int v14; // r12d
  BSTR v15; // rdx
  int v16; // eax
  int v17; // r8d
  __int64 v18; // rax
  unsigned __int16 *v19; // r13
  UINT v20; // eax
  __int64 v21; // r9
  int IsPendingPrimaryMarkup; // eax
  bool v23; // r15
  int v24; // r12d
  const unsigned __int16 *Url; // r12
  const unsigned __int16 *v26; // r13
  DWORD CurrentThreadId; // eax
  unsigned __int16 *v28; // rax
  unsigned __int16 *Src; // r15
  unsigned int v30; // r11d
  int v31; // r8d
  int v32; // r9d
  __int64 v33; // rcx
  int v34; // eax
  _DWORD *PrimaryTraceActivity; // r15
  __int64 CLSID; // rax
  int v37; // r9d
  void *v38; // r8
  __int64 v39; // rax
  struct CMarkup *v40; // rax
  CAPProcessor *v41; // rcx
  int v42; // edx
  BSTR pbstr; // [rsp+50h] [rbp-39h] BYREF
  __int64 v44; // [rsp+58h] [rbp-31h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-29h] BYREF
  IUri *ppURI; // [rsp+68h] [rbp-21h] BYREF
  IUri *v47; // [rsp+70h] [rbp-19h] BYREF
  struct _IsoUntrustedComponent *v48; // [rsp+78h] [rbp-11h] BYREF
  VARIANTARG pwzURI[4]; // [rsp+80h] [rbp-9h] BYREF
  struct CMarkup *v50; // [rsp+F0h] [rbp+67h] BYREF
  int v51; // [rsp+F8h] [rbp+6Fh]
  struct CWindow *v52; // [rsp+100h] [rbp+77h] BYREF
  LONGLONG llVal; // [rsp+108h] [rbp+7Fh] BYREF

  if ( CMarkup::Window(this) )
    v3 = (struct CWindow *)*((_QWORD *)CMarkup::Window(v2) + 15);
  else
    v3 = 0;
  v4 = *((_QWORD *)v2 + 40);
  v5 = 0;
  v52 = v3;
  if ( v4 )
    v5 = *(_QWORD *)(v4 + 16);
  v6 = (_DWORD *)*((_QWORD *)v2 + 27);
  if ( !v6 )
    return 1;
  v8 = v6[7];
  if ( (v8 & 1) != 0 )
  {
    v9 = 2;
    if ( (v8 & 0x210) == 0 )
      goto LABEL_14;
    if ( (v8 & 0x10) != 0 )
      goto LABEL_19;
  }
  v9 = ((v8 & 2) != 0) + 3;
  if ( (v8 & 0x14) != 0 )
  {
LABEL_19:
    v9 = 5;
    goto LABEL_20;
  }
  if ( (v8 & 0x200) != 0 )
  {
    v9 = 9;
LABEL_20:
    v6[13] = 6;
    goto LABEL_21;
  }
LABEL_14:
  v51 = 0;
  if ( v6[8] != 1 )
    goto LABEL_22;
  if ( v6[13] != 3 || (v10 = 6, v9 != 2) )
    v10 = 5;
  v6[13] = v10;
LABEL_21:
  v51 = 1;
LABEL_22:
  if ( v3
    && ((v9 - 5) & 0xFFFFFFFB) == 0
    && (!(unsigned int)CMarkup::IsPrimaryMarkup(this) && !(unsigned int)CMarkup::IsPendingPrimaryMarkup(this)
     || (v11 = *(_QWORD *)(*((_QWORD *)this + 27) + 16LL)) == 0
     || !(unsigned __int8)anonymous_namespace_::WasBlockedInFrame(v11, this))
    && !*((_BYTE *)this + 248)
    && (*(_BYTE *)(*((_QWORD *)this + 27) + 8LL) & 1) == 0 )
  {
    memset(pwzURI, 0, 24);
    pwzURI[0].vt = 8;
    CAPProcessor::GetURLForPhishingEval(this, &pwzURI[0].bstrVal);
    LODWORD(v50) = 0;
    GetBOOL(SettingStore::IEVALUE_PhishingFilter_PreventOverride, &v50);
    pbstr = 0;
    ppURI = 0;
    if ( CreateUri(pwzURI[0].bstrVal, 0x3002B80u, 0, &ppURI) >= 0 )
    {
      ((void (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetHost)(ppURI, &pbstr);
      ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    }
    v12 = SysStringLen(pbstr);
    v13 = *((_QWORD *)this + 27);
    bstrString = 0;
    v47 = 0;
    v14 = v12 + 33;
    if ( CreateUri(*(LPCWSTR *)(v13 + 16), 0x3002B80u, 0, &v47) >= 0 )
    {
      ((void (__fastcall *)(IUri *, BSTR *))v47->lpVtbl->GetHost)(v47, &bstrString);
      ((void (__fastcall *)(IUri *))v47->lpVtbl->Release)(v47);
    }
    if ( bstrString )
    {
      v15 = bstrString;
      do
      {
        v16 = *(BSTR)((char *)v15 + (char *)pbstr - (char *)bstrString);
        v17 = *v15 - v16;
        if ( v17 )
          break;
        ++v15;
      }
      while ( v16 );
      if ( v17 )
        v14 += SysStringLen(bstrString) + 18;
    }
    v18 = 2LL * v14;
    if ( !is_mul_ok(v14, 2u) )
      v18 = -1;
    v44 = MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v18);
    v19 = (unsigned __int16 *)v44;
    if ( v44 )
    {
      CDXDependentSurfacePresenterFlip::IsIndependent((CDXDependentSurfacePresenterFlip *)*(unsigned int *)(v5 + 5040));
      v20 = SysStringLen(pbstr);
      v21 = *(unsigned int *)(*((_QWORD *)this + 27) + 28LL);
      if ( v14 <= v20 + 33 )
        StringCchPrintfW(v19, v14, L"?Threats=%d&Block=%d&Host=%s", v21, (_DWORD)v50, pbstr);
      else
        StringCchPrintfW(
          v19,
          v14,
          L"?Threats=%d&Block=%d&Host=%s&BlockedDomain=%s",
          v21,
          (_DWORD)v50,
          pbstr,
          bstrString);
      IECompatLogAntiphishingUrl(pwzURI[0].bstrVal, 0);
      if ( (*((_DWORD *)this + 187) & 0x8000000) != 0 )
        IsPendingPrimaryMarkup = CMarkup::IsPendingPrimaryMarkup(this);
      else
        IsPendingPrimaryMarkup = CMarkup::IsPrimaryMarkup(this);
      v23 = IsPendingPrimaryMarkup == 0;
      v24 = 0;
      LODWORD(llVal) = NavigateToPhishingErrorPage(
                         (struct CDoc *)v5,
                         pwzURI[0].bstrVal,
                         v19,
                         v52,
                         IsPendingPrimaryMarkup == 0);
      if ( (int)llVal >= 0 )
      {
        if ( v23 )
        {
          v50 = 0;
          if ( (int)CMarkup::GetTopmostMarkup(this, &v50) >= 0 )
          {
            Url = CMarkup::GetUrl(this);
            if ( Url )
            {
              v26 = CMarkup::GetUrl(v50);
              if ( v26 )
              {
                LODWORD(v50) = 0;
                CurrentThreadId = GetCurrentThreadId();
                if ( (int)LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, (unsigned int *)&v50, 0) >= 0 )
                {
                  LODWORD(v52) = 0;
                  v48 = 0;
                  if ( (int)IsoGetTrustSplitComponent((unsigned int)v50, 0, 0, (unsigned int *)&v52, &v48) >= 0 )
                  {
                    v28 = (unsigned __int16 *)CoTaskMemAlloc(0x2098u);
                    Src = v28;
                    if ( v28 )
                    {
                      *(_DWORD *)v28 = (v9 != 5) + 1;
                      StringCchCopyW(v28 + 2, 0x825u, Url);
                      StringCchCopyW(Src + 2087, v30, v26);
                      TFlatIsoMessage<LCIE_CONTENT_BLOCK_MSG>::Post(*((_DWORD *)v48 + 18), (int)v50, v31, v32, Src);
                    }
                    CoTaskMemFree(Src);
                  }
                }
              }
              v19 = (unsigned __int16 *)v44;
            }
          }
        }
        v33 = *((_QWORD *)this + 27);
        v24 = 0;
        v34 = *(_DWORD *)(v33 + 8);
        if ( (v34 & 8) == 0 )
        {
          v24 = 1;
          *(_DWORD *)(v33 + 8) = v34 | 8;
        }
      }
      PrimaryTraceActivity = (_DWORD *)CDoc::GetPrimaryTraceActivity(v5);
      if ( !PrimaryTraceActivity )
        PrimaryTraceActivity = (_DWORD *)CMarkup::EnsureTraceActivity(this);
      if ( *PrimaryTraceActivity == 1
        && (unsigned int)dword_181559C88 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_181559C88, 0x410000000000LL) )
      {
        v48 = GlobalThreadState();
        CLSID = IEConfiguration_GetCLSID(268435459);
        LODWORD(v52) = v24;
        v44 = CLSID;
        LODWORD(v50) = llVal;
        llVal = pwzURI[0].llVal;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
          (unsigned int)&dword_181559C88,
          (unsigned int)&unk_1815188C7,
          (_DWORD)PrimaryTraceActivity + 8,
          v37,
          (__int64)&llVal,
          (__int64)&v52,
          (__int64)&v50,
          (__int64)&v44,
          (__int64)&v48);
      }
    }
    SysFreeString(bstrString);
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v19, v38);
    SysFreeString(pbstr);
    VariantClear(pwzURI);
  }
  if ( v51 && v5 )
  {
    if ( v9 == 4 )
    {
      memset(pwzURI, 0, 24);
      pwzURI[0].vt = 8;
      CAPProcessor::GetURLForPhishingEval(this, &pwzURI[0].bstrVal);
      IECompatLogAntiphishingUrl(pwzURI[0].bstrVal, 1u);
      v39 = *((_QWORD *)this + 27);
      LODWORD(v50) = 1;
      if ( (*(_BYTE *)(v39 + 8) & 0x20) == 0 )
      {
        v40 = CDoc::PrimaryMarkup((CDoc *)v5);
        v41 = *(CAPProcessor **)(v5 + 5856);
        if ( v41 )
        {
          if ( CAPProcessor::ShouldShowPhishingFilterDialog(v41, v40, (int *)&v50) >= 0 && !(_DWORD)v50 )
            v9 = 7;
        }
      }
      VariantClear(pwzURI);
    }
    v42 = v9 | 0x100;
    if ( *(int *)(*((_QWORD *)this + 27) + 24LL) >= 0 )
      v42 = v9;
    CDoc::SetPhishingFilterStatus((CDoc *)v5, v42);
  }
  return 0;
}

```

## disassembly

```asm
0x180844d20  push    rbp
0x180844d22  push    rbx
0x180844d23  push    rsi
0x180844d24  push    rdi
0x180844d25  push    r12
0x180844d27  push    r13
0x180844d29  push    r14
0x180844d2b  push    r15
0x180844d2d  lea     rbp, [rsp-1Fh]
0x180844d32  sub     rsp, 0A8h
0x180844d39  mov     rbx, rcx
0x180844d3c  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x180844d41  xor     r15d, r15d
0x180844d44  test    rax, rax
0x180844d47  jz      short loc_180844D54
0x180844d49  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x180844d4e  mov     r8, [rax+78h]
0x180844d52  jmp     short loc_180844D57
0x180844d54  mov     r8, r15
0x180844d57  mov     rax, [rcx+140h]
0x180844d5e  mov     r14, r15
0x180844d61  mov     [rbp+57h+arg_10], r8
0x180844d65  test    rax, rax
0x180844d68  jz      short loc_180844D6E
0x180844d6a  mov     r14, [rax+10h]
0x180844d6e  mov     rcx, [rcx+0D8h]
0x180844d75  test    rcx, rcx
0x180844d78  jnz     short loc_180844D82
0x180844d7a  lea     eax, [rcx+1]
0x180844d7d  jmp     loc_18084533C
0x180844d82  mov     edx, [rcx+1Ch]
0x180844d85  mov     esi, 1
0x180844d8a  lea     r9d, [rsi+4]
0x180844d8e  lea     r13d, [rsi+1]
0x180844d92  test    sil, dl
0x180844d95  jz      short loc_180844DA7
0x180844d97  mov     edi, r13d
0x180844d9a  test    edx, 210h
0x180844da0  jz      short loc_180844DC7
0x180844da2  test    dl, 10h
0x180844da5  jnz     short loc_180844DE8
0x180844da7  mov     eax, edx
0x180844da9  and     al, r13b
0x180844dac  neg     al
0x180844dae  sbb     edi, edi
0x180844db0  neg     edi
0x180844db2  add     edi, 3
0x180844db5  test    dl, 14h
0x180844db8  jnz     short loc_180844DE8
0x180844dba  bt      edx, 9
0x180844dbe  jnb     short loc_180844DC7
0x180844dc0  mov     edi, 9
0x180844dc5  jmp     short loc_180844DEB
0x180844dc7  mov     [rbp+57h+arg_8], r15d
0x180844dcb  cmp     [rcx+20h], esi
0x180844dce  jnz     short loc_180844DF5
0x180844dd0  cmp     dword ptr [rcx+34h], 3
0x180844dd4  jnz     short loc_180844DE0
0x180844dd6  mov     eax, 6
0x180844ddb  cmp     edi, r13d
0x180844dde  jz      short loc_180844DE3
0x180844de0  mov     eax, r9d
0x180844de3  mov     [rcx+34h], eax
0x180844de6  jmp     short loc_180844DF2
0x180844de8  mov     edi, r9d
0x180844deb  mov     dword ptr [rcx+34h], 6
0x180844df2  mov     [rbp+57h+arg_8], esi
0x180844df5  mov     r12d, 8
0x180844dfb  test    r8, r8
0x180844dfe  jz      loc_180845294
0x180844e04  lea     eax, [rdi-5]
0x180844e07  test    eax, 0FFFFFFFBh
0x180844e0c  jnz     loc_180845294
0x180844e12  mov     rcx, rbx; this
0x180844e15  call    ?IsPrimaryMarkup@CMarkup@@QEBAHXZ; CMarkup::IsPrimaryMarkup(void)
0x180844e1a  test    eax, eax
0x180844e1c  jnz     short loc_180844E2A
0x180844e1e  mov     rcx, rbx; this
0x180844e21  call    ?IsPendingPrimaryMarkup@CMarkup@@QEBAHXZ; CMarkup::IsPendingPrimaryMarkup(void)
0x180844e26  test    eax, eax
0x180844e28  jz      short loc_180844E4A
0x180844e2a  mov     rax, [rbx+0D8h]
0x180844e31  mov     rcx, [rax+10h]
0x180844e35  test    rcx, rcx
0x180844e38  jz      short loc_180844E4A
0x180844e3a  mov     rdx, rbx
0x180844e3d  call    _anonymous_namespace___WasBlockedInFrame
0x180844e42  test    al, al
0x180844e44  jnz     loc_180845294
0x180844e4a  cmp     [rbx+0F8h], r15b
0x180844e51  jnz     loc_180845294
0x180844e57  mov     rax, [rbx+0D8h]
0x180844e5e  test    [rax+8], sil
0x180844e62  jnz     loc_180845294
0x180844e68  xorps   xmm0, xmm0
0x180844e6b  lea     rdx, [rbp+57h+pwzURI+8]; unsigned __int16 **
0x180844e6f  xor     eax, eax
0x180844e71  mov     rcx, rbx; struct CMarkup *
0x180844e74  movups  xmmword ptr [rbp-9], xmm0
0x180844e78  mov     word ptr [rbp+57h+pwzURI], r12w
0x180844e7d  mov     [rbp+57h+var_50], rax
0x180844e81  call    ?GetURLForPhishingEval@CAPProcessor@@SAJPEAVCMarkup@@PEAPEAG@Z; CAPProcessor::GetURLForPhishingEval(CMarkup *,ushort * *)
0x180844e86  mov     rcx, cs:?IEVALUE_PhishingFilter_PreventOverride@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_PhishingFilter_PreventOverride
0x180844e8d  lea     rdx, [rbp+57h+arg_0]
0x180844e91  mov     dword ptr [rbp+57h+arg_0], r15d
0x180844e95  call    GetBOOL
0x180844e9a  mov     rcx, [rbp+57h+pwzURI+8]; pwzURI
0x180844e9e  lea     r9, [rbp+57h+ppURI]; ppURI
0x180844ea2  xor     r8d, r8d; dwReserved
0x180844ea5  mov     [rbp+57h+pbstr], r15
0x180844ea9  mov     edx, 3002B80h; dwFlags
0x180844eae  mov     [rbp+57h+ppURI], r15
0x180844eb2  call    cs:__imp_CreateUri
0x180844eb8  test    eax, eax
0x180844eba  js      short loc_180844EE0
0x180844ebc  mov     rcx, [rbp+57h+ppURI]
0x180844ec0  lea     rdx, [rbp+57h+pbstr]
0x180844ec4  mov     rax, [rcx]
0x180844ec7  mov     rax, [rax+68h]
0x180844ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180844ed0  mov     rcx, [rbp+57h+ppURI]
0x180844ed4  mov     rax, [rcx]
0x180844ed7  mov     rax, [rax+10h]
0x180844edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180844ee0  mov     rcx, [rbp+57h+pbstr]; pbstr
0x180844ee4  call    cs:__imp_SysStringLen
0x180844eea  mov     rcx, [rbx+0D8h]
0x180844ef1  lea     r9, [rbp+57h+var_70]; ppURI
0x180844ef5  mov     [rbp+57h+bstrString], r15
0x180844ef9  xor     r8d, r8d; dwReserved
0x180844efc  mov     [rbp+57h+var_70], r15
0x180844f00  mov     edx, 3002B80h; dwFlags
0x180844f05  lea     r12d, [rax+21h]
0x180844f09  mov     rcx, [rcx+10h]; pwzURI
0x180844f0d  call    cs:__imp_CreateUri
0x180844f13  test    eax, eax
0x180844f15  js      short loc_180844F3B
0x180844f17  mov     rcx, [rbp+57h+var_70]
0x180844f1b  lea     rdx, [rbp+57h+bstrString]
0x180844f1f  mov     rax, [rcx]
0x180844f22  mov     rax, [rax+68h]
0x180844f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180844f2b  mov     rcx, [rbp+57h+var_70]
0x180844f2f  mov     rax, [rcx]
0x180844f32  mov     rax, [rax+10h]
0x180844f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180844f3b  mov     rcx, [rbp+57h+bstrString]; pbstr
0x180844f3f  test    rcx, rcx
0x180844f42  jz      short loc_180844F75
0x180844f44  mov     r9, [rbp+57h+pbstr]
0x180844f48  mov     rdx, rcx
0x180844f4b  sub     r9, rcx
0x180844f4e  movzx   r8d, word ptr [rdx]
0x180844f52  movzx   eax, word ptr [rdx+r9]
0x180844f57  sub     r8d, eax
0x180844f5a  jnz     short loc_180844F63
0x180844f5c  add     rdx, r13
0x180844f5f  test    eax, eax
0x180844f61  jnz     short loc_180844F4E
0x180844f63  test    r8d, r8d
0x180844f66  jz      short loc_180844F75
0x180844f68  call    cs:__imp_SysStringLen
0x180844f6e  add     r12d, 12h
0x180844f72  add     r12d, eax
0x180844f75  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180844f7c  mov     r15d, r12d
0x180844f7f  mov     rax, r13
0x180844f82  mul     r15
0x180844f85  cmovb   rax, rcx
0x180844f89  mov     rcx, cs:g_hProcessHeap
0x180844f90  mov     rdx, rax
0x180844f93  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180844f98  mov     [rbp+57h+var_88], rax
0x180844f9c  mov     r13, rax
0x180844f9f  test    rax, rax
0x180844fa2  jz      loc_180845260
0x180844fa8  mov     r9d, [r14+13B8h]
0x180844faf  mov     r8d, [r14+13BCh]
0x180844fb6  mov     edx, [r14+13B4h]
0x180844fbd  mov     ecx, [r14+13B0h]; this
0x180844fc4  call    ?IsIndependent@CDXDependentSurfacePresenterFlip@@UEAA_NXZ; CDXDependentSurfacePresenterFlip::IsIndependent(void)
0x180844fc9  mov     rcx, [rbp+57h+pbstr]; pbstr
0x180844fcd  call    cs:__imp_SysStringLen
0x180844fd3  mov     rcx, [rbx+0D8h]
0x180844fda  mov     edx, r15d; unsigned __int64
0x180844fdd  add     eax, 21h ; '!'
0x180844fe0  mov     r9d, [rcx+1Ch]
0x180844fe4  mov     rcx, r13; unsigned __int16 *
0x180844fe7  cmp     r12d, eax
0x180844fea  jbe     short loc_180845013
0x180844fec  mov     rax, [rbp+57h+bstrString]
0x180844ff0  lea     r8, aThreatsDBlockD_0; "?Threats=%d&Block=%d&Host=%s&BlockedDom"...
0x180844ff7  mov     [rsp+0E0h+var_B0], rax
0x180844ffc  mov     rax, [rbp+57h+pbstr]
0x180845000  mov     [rsp+0E0h+var_B8], rax
0x180845005  mov     eax, dword ptr [rbp+57h+arg_0]
0x180845008  mov     dword ptr [rsp+0E0h+Src], eax
0x18084500c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180845011  jmp     short loc_18084502F
0x180845013  mov     rax, [rbp+57h+pbstr]
0x180845017  lea     r8, aThreatsDBlockD_1; "?Threats=%d&Block=%d&Host=%s"
0x18084501e  mov     [rsp+0E0h+var_B8], rax
0x180845023  mov     eax, dword ptr [rbp+57h+arg_0]
0x180845026  mov     dword ptr [rsp+0E0h+Src], eax
0x18084502a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18084502f  mov     rcx, [rbp+57h+pwzURI+8]
0x180845033  xor     edx, edx
0x180845035  call    cs:__imp_?IECompatLogAntiphishingUrl@@YAXPEBGK@Z; IECompatLogAntiphishingUrl(ushort const *,ulong)
0x18084503b  test    dword ptr [rbx+2ECh], 8000000h
0x180845045  mov     rcx, rbx; this
0x180845048  jz      short loc_180845051
0x18084504a  call    ?IsPendingPrimaryMarkup@CMarkup@@QEBAHXZ; CMarkup::IsPendingPrimaryMarkup(void)
0x18084504f  jmp     short loc_180845056
0x180845051  call    ?IsPrimaryMarkup@CMarkup@@QEBAHXZ; CMarkup::IsPrimaryMarkup(void)
0x180845056  mov     r9, [rbp+57h+arg_10]; struct CWindow *
0x18084505a  test    eax, eax
0x18084505c  mov     rdx, [rbp+57h+pwzURI+8]; unsigned __int16 *
0x180845060  mov     r8, r13; unsigned __int16 *
0x180845063  setz    r15b
0x180845067  mov     rcx, r14; struct CDoc *
0x18084506a  mov     byte ptr [rsp+0E0h+Src], r15b; bool
0x18084506f  call    ?NavigateToPhishingErrorPage@@YAJPEAVCDoc@@PEBG1PEAVCWindow@@_N@Z; NavigateToPhishingErrorPage(CDoc *,ushort const *,ushort const *,CWindow *,bool)
0x180845074  xor     r12d, r12d
0x180845077  mov     dword ptr [rbp+57h+arg_18], eax
0x18084507a  test    eax, eax
0x18084507c  js      loc_1808451A4
0x180845082  test    r15b, r15b
0x180845085  jz      loc_18084518A
0x18084508b  lea     rdx, [rbp+57h+arg_0]; struct CMarkup **
0x18084508f  mov     [rbp+57h+arg_0], r12
0x180845093  mov     rcx, rbx; this
0x180845096  call    ?GetTopmostMarkup@CMarkup@@QEAAJPEAPEAV1@@Z; CMarkup::GetTopmostMarkup(CMarkup * *)
0x18084509b  test    eax, eax
0x18084509d  js      loc_18084518A
0x1808450a3  mov     rcx, rbx; struct CMarkup *
0x1808450a6  call    ?GetUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetUrl(CMarkup const * const)
0x1808450ab  mov     r12, rax
0x1808450ae  test    rax, rax
0x1808450b1  jz      loc_18084518A
0x1808450b7  mov     rcx, [rbp+57h+arg_0]; struct CMarkup *
0x1808450bb  call    ?GetUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetUrl(CMarkup const * const)
0x1808450c0  mov     r13, rax
0x1808450c3  test    rax, rax
0x1808450c6  jz      loc_180845186
0x1808450cc  mov     dword ptr [rbp+57h+arg_0], 0
0x1808450d3  call    cs:__imp_GetCurrentThreadId
0x1808450d9  xor     r9d, r9d
0x1808450dc  lea     r8, [rbp+57h+arg_0]
0x1808450e0  mov     edx, eax
0x1808450e2  mov     ecx, 203h
0x1808450e7  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x1808450ed  test    eax, eax
0x1808450ef  js      loc_180845186
0x1808450f5  mov     ecx, dword ptr [rbp+57h+arg_0]
0x1808450f8  lea     rax, [rbp+57h+var_68]
0x1808450fc  lea     r9, [rbp+57h+arg_10]
0x180845100  mov     [rsp+0E0h+Src], rax
0x180845105  xor     r8d, r8d
0x180845108  mov     dword ptr [rbp+57h+arg_10], 0
0x18084510f  xor     edx, edx
0x180845111  mov     [rbp+57h+var_68], 0
0x180845119  call    cs:__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z; IsoGetTrustSplitComponent(ulong,ulong,_IsoComponent * *,ulong *,_IsoUntrustedComponent * *)
0x18084511f  test    eax, eax
0x180845121  js      short loc_180845186
0x180845123  mov     ecx, 2098h; cb
0x180845128  call    cs:__imp_CoTaskMemAlloc
0x18084512e  mov     r15, rax
0x180845131  test    rax, rax
0x180845134  jz      short loc_18084517D
0x180845136  xor     ecx, ecx
0x180845138  mov     r11d, 825h
0x18084513e  cmp     edi, 5
0x180845141  mov     r8, r12; unsigned __int16 *
0x180845144  mov     edx, r11d; unsigned __int64
0x180845147  setnz   cl
0x18084514a  add     ecx, esi
0x18084514c  mov     [rax], ecx
0x18084514e  lea     rcx, [rax+4]; unsigned __int16 *
0x180845152  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180845157  lea     rcx, [r15+104Eh]; unsigned __int16 *
0x18084515e  mov     r8, r13; unsigned __int16 *
0x180845161  mov     edx, r11d; unsigned __int64
0x180845164  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180845169  mov     rcx, [rbp+57h+var_68]
0x18084516d  mov     edx, dword ptr [rbp+57h+arg_0]; int
0x180845170  mov     [rsp+0E0h+Src], r15; Src
0x180845175  mov     ecx, [rcx+48h]; int
0x180845178  call    ?Post@?$TFlatIsoMessage@ULCIE_CONTENT_BLOCK_MSG@@@@SAJKKKKPEBULCIE_CONTENT_BLOCK_MSG@@@Z; TFlatIsoMessage<LCIE_CONTENT_BLOCK_MSG>::Post(ulong,ulong,ulong,ulong,LCIE_CONTENT_BLOCK_MSG const *)
0x18084517d  mov     rcx, r15; pv
0x180845180  call    cs:__imp_CoTaskMemFree
0x180845186  mov     r13, [rbp+57h+var_88]
0x18084518a  mov     rcx, [rbx+0D8h]
0x180845191  xor     r12d, r12d
0x180845194  mov     eax, [rcx+8]
0x180845197  test    al, 8
0x180845199  jnz     short loc_1808451A4
0x18084519b  or      eax, 8
0x18084519e  mov     r12d, esi
0x1808451a1  mov     [rcx+8], eax
0x1808451a4  mov     rcx, r14
  ... truncated ...
```
