# CMarkup::UpdatePhishingState(void)

- ea: `0x180847b6c`
- end: `0x1808481d6`
- name: `?UpdatePhishingState@CMarkup@@QEAAJXZ`
- size: `1642`
- prototype: `__int64 __fastcall(CMarkup *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18084720c`

## callees

- `0x180001a08`
- `0x180051c00`
- `0x18005d080`
- `0x18005e684`
- `0x1801086ac`
- `0x180149610`
- `0x1801dc4a4`
- `0x180306090`
- `0x1803ddae0`
- `0x1803e706c`
- `0x18040ac58`
- `0x1804e4c1c`
- `0x1805c1214`
- `0x180636de0`
- `0x18077c370`
- `0x18077f8cc`
- `0x1807e50c4`
- `0x180846ee0`
- `0x180847138`
- `0x1808476ec`
- `0x180847808`
- `0x180847b6c`
- `0x1808481dc`
- `0x180873fac`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180847f10`
- `KERNEL32!GetCurrentThreadId` at `0x180847f10`
- `iertutil!CreateUri` at `0x180847ccb`
- `iertutil!CreateUri` at `0x180847d32`
- `iertutil!CreateUri` at `0x180847ccb`
- `iertutil!CreateUri` at `0x180847d32`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180848061`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180848061`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180847f77`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180847f77`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180847fd5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180847fd5`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180847f2a`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180847f2a`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x180847f62`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x180847f62`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18084804c`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18084804c`
- `urlmon!__imp_?IECompatLogAntiphishingUrl@@YAXPEBGK@Z` at `0x180847e6c`
- `urlmon!__imp_?IECompatLogAntiphishingUrl@@YAXPEBGK@Z` at `0x180848149`
- `urlmon!__imp_?IECompatLogAntiphishingUrl@@YAXPEBGK@Z` at `0x180847e6c`
- `urlmon!__imp_?IECompatLogAntiphishingUrl@@YAXPEBGK@Z` at `0x180848149`
- `OLEAUT32!__imp_SysFreeString` at `0x1808480cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1808480ea`
- `OLEAUT32!__imp_SysFreeString` at `0x1808480cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1808480ea`
- `OLEAUT32!__imp_SysStringLen` at `0x180847d03`
- `OLEAUT32!__imp_SysStringLen` at `0x180847d93`
- `OLEAUT32!__imp_SysStringLen` at `0x180847dfe`
- `OLEAUT32!__imp_SysStringLen` at `0x180847d03`
- `OLEAUT32!__imp_SysStringLen` at `0x180847d93`
- `OLEAUT32!__imp_SysStringLen` at `0x180847dfe`
- `OLEAUT32!__imp_VariantClear` at `0x1808480fa`
- `OLEAUT32!__imp_VariantClear` at `0x180848197`
- `OLEAUT32!__imp_VariantClear` at `0x1808480fa`
- `OLEAUT32!__imp_VariantClear` at `0x180848197`

## pseudocode

```c
__int64 __fastcall CMarkup::UpdatePhishingState(CMarkup *this)
{
  CMarkup *v2; // rcx
  struct CWindow *v3; // r8
  struct CDoc *v4; // rax
  __int64 v5; // r8
  __int64 v6; // rcx
  _DWORD *v7; // rcx
  struct CDoc *v8; // r15
  int v10; // edx
  int v11; // edi
  int v12; // eax
  UINT v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // r12d
  BSTR v16; // rdx
  int v17; // eax
  int v18; // r8d
  SIZE_T v19; // rax
  unsigned __int16 *v20; // r13
  UINT v21; // eax
  __int64 v22; // r9
  int IsPendingPrimaryMarkup; // eax
  bool v24; // r14
  int v25; // r12d
  unsigned __int16 *Url; // r12
  unsigned __int16 *v27; // r13
  DWORD CurrentThreadId; // eax
  unsigned __int16 *v29; // rax
  unsigned __int16 *Src; // r14
  unsigned int v31; // r11d
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rcx
  int v35; // eax
  _DWORD *PrimaryTraceActivity; // r14
  unsigned __int16 *CLSID; // rax
  __int64 v38; // r9
  void *v39; // r8
  __int64 v40; // rax
  struct CMarkup *v41; // rax
  CAPProcessor *v42; // rcx
  LONG v43; // edx
  BSTR pbstr; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int16 *v45; // [rsp+58h] [rbp-31h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-29h] BYREF
  IUri *ppURI; // [rsp+68h] [rbp-21h] BYREF
  IUri *v48; // [rsp+70h] [rbp-19h] BYREF
  struct _IsoUntrustedComponent *v49; // [rsp+78h] [rbp-11h] BYREF
  VARIANTARG pwzURI[4]; // [rsp+80h] [rbp-9h] BYREF
  struct CMarkup *v51; // [rsp+F0h] [rbp+67h] BYREF
  int v52; // [rsp+F8h] [rbp+6Fh]
  struct CWindow *v53; // [rsp+100h] [rbp+77h] BYREF
  const WCHAR *bstrVal; // [rsp+108h] [rbp+7Fh] BYREF

  if ( CMarkup::Window(this) )
    v3 = (struct CWindow *)*((_QWORD *)CMarkup::Window(v2) + 15);
  else
    v3 = 0;
  v53 = v3;
  v4 = CMarkup::Doc(v2);
  v7 = *(_DWORD **)(v6 + 216);
  v8 = v4;
  if ( !v7 )
    return 1;
  v10 = v7[7];
  if ( (v10 & 1) != 0 )
  {
    v11 = 2;
    if ( (v10 & 0x210) == 0 )
      goto LABEL_12;
    if ( (v10 & 0x10) != 0 )
      goto LABEL_17;
  }
  v11 = ((v10 & 2) != 0) + 3;
  if ( (v10 & 0x14) != 0 )
  {
LABEL_17:
    v11 = 5;
    goto LABEL_18;
  }
  if ( (v10 & 0x200) != 0 )
  {
    v11 = 9;
LABEL_18:
    v7[13] = 6;
    goto LABEL_19;
  }
LABEL_12:
  v52 = 0;
  if ( v7[8] != 1 )
    goto LABEL_20;
  if ( v7[13] != 3 || (v12 = 6, v11 != 2) )
    v12 = 5;
  v7[13] = v12;
LABEL_19:
  v52 = 1;
LABEL_20:
  if ( v5
    && ((v11 - 5) & 0xFFFFFFFB) == 0
    && !anonymous_namespace_::WasBlockedInFrame(this)
    && !*((_BYTE *)this + 248)
    && (*(_BYTE *)(*((_QWORD *)this + 27) + 8LL) & 1) == 0 )
  {
    memset(pwzURI, 0, 24);
    pwzURI[0].vt = 8;
    CAPProcessor::GetURLForPhishingEval(this, &pwzURI[0].bstrVal);
    LODWORD(v51) = 0;
    GetBOOL((__int64)SettingStore::IEVALUE_PhishingFilter_PreventOverride[0], &v51);
    pbstr = 0;
    ppURI = 0;
    if ( CreateUri(pwzURI[0].bstrVal, 0x3002B80u, 0, &ppURI) >= 0 )
    {
      ((void (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetHost)(ppURI, &pbstr);
      ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    }
    v13 = SysStringLen(pbstr);
    v14 = *((_QWORD *)this + 27);
    bstrString = 0;
    v48 = 0;
    v15 = v13 + 33;
    if ( CreateUri(*(LPCWSTR *)(v14 + 16), 0x3002B80u, 0, &v48) >= 0 )
    {
      ((void (__fastcall *)(IUri *, BSTR *))v48->lpVtbl->GetHost)(v48, &bstrString);
      ((void (__fastcall *)(IUri *))v48->lpVtbl->Release)(v48);
    }
    if ( bstrString )
    {
      v16 = bstrString;
      do
      {
        v17 = *(BSTR)((char *)v16 + (char *)pbstr - (char *)bstrString);
        v18 = *v16 - v17;
        if ( v18 )
          break;
        ++v16;
      }
      while ( v17 );
      if ( v18 )
        v15 += SysStringLen(bstrString) + 18;
    }
    v19 = 2LL * v15;
    if ( !is_mul_ok(v15, 2u) )
      v19 = -1;
    v45 = (unsigned __int16 *)MemoryProtection::HeapAlloc<0>((MemoryProtection *)g_hProcessHeap, v19);
    v20 = v45;
    if ( v45 )
    {
      CDXDependentSurfacePresenterFlip::IsIndependent((CDXDependentSurfacePresenterFlip *)*((unsigned int *)v8 + 1260));
      v21 = SysStringLen(pbstr);
      v22 = *(unsigned int *)(*((_QWORD *)this + 27) + 28LL);
      if ( v15 <= v21 + 33 )
        StringCchPrintfW(v20, v15, L"?Threats=%d&Block=%d&Host=%s", v22, (_DWORD)v51, pbstr);
      else
        StringCchPrintfW(
          v20,
          v15,
          L"?Threats=%d&Block=%d&Host=%s&BlockedDomain=%s",
          v22,
          (_DWORD)v51,
          pbstr,
          bstrString);
      IECompatLogAntiphishingUrl(pwzURI[0].bstrVal, 0);
      if ( (*((_DWORD *)this + 187) & 0x8000000) != 0 )
        IsPendingPrimaryMarkup = CMarkup::IsPendingPrimaryMarkup(this);
      else
        IsPendingPrimaryMarkup = CMarkup::IsPrimaryMarkup(this);
      v24 = IsPendingPrimaryMarkup == 0;
      v25 = 0;
      LODWORD(bstrVal) = NavigateToPhishingErrorPage(
                           (const unsigned __int16 **)v8,
                           pwzURI[0].bstrVal,
                           v20,
                           v53,
                           IsPendingPrimaryMarkup == 0);
      if ( (int)bstrVal >= 0 )
      {
        if ( v24 )
        {
          v51 = 0;
          if ( (int)CMarkup::GetTopmostMarkup(this, &v51) >= 0 )
          {
            Url = (unsigned __int16 *)CMarkup::GetUrl(this);
            if ( Url )
            {
              v27 = (unsigned __int16 *)CMarkup::GetUrl(v51);
              if ( v27 )
              {
                LODWORD(v51) = 0;
                CurrentThreadId = GetCurrentThreadId();
                if ( (int)LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, (unsigned int *)&v51, 0) >= 0 )
                {
                  LODWORD(v53) = 0;
                  v49 = 0;
                  if ( (int)IsoGetTrustSplitComponent((unsigned int)v51, 0, 0, (unsigned int *)&v53, &v49) >= 0 )
                  {
                    v29 = (unsigned __int16 *)CoTaskMemAlloc(0x2098u);
                    Src = v29;
                    if ( v29 )
                    {
                      *(_DWORD *)v29 = (v11 != 5) + 1;
                      StringCchCopyW(v29 + 2, 0x825u, Url);
                      StringCchCopyW(Src + 2087, v31, v27);
                      TFlatIsoMessage<LCIE_CONTENT_BLOCK_MSG>::Post(
                        *((_DWORD *)v49 + 18),
                        (unsigned int)v51,
                        v32,
                        v33,
                        Src);
                    }
                    CoTaskMemFree(Src);
                  }
                }
              }
              v20 = v45;
            }
          }
        }
        v34 = *((_QWORD *)this + 27);
        v25 = 0;
        v35 = *(_DWORD *)(v34 + 8);
        if ( (v35 & 8) == 0 )
        {
          v25 = 1;
          *(_DWORD *)(v34 + 8) = v35 | 8;
        }
      }
      PrimaryTraceActivity = CDoc::GetPrimaryTraceActivity(v8);
      if ( !PrimaryTraceActivity )
        PrimaryTraceActivity = (_DWORD *)CMarkup::EnsureTraceActivity((__int64)this);
      if ( *PrimaryTraceActivity == 1
        && (unsigned int)dword_18158CCA8 > 5
        && tlgKeywordOn((__int64)&dword_18158CCA8, 0x410000000000LL) )
      {
        v49 = GlobalThreadState();
        CLSID = (unsigned __int16 *)IEConfiguration_GetCLSID(268435459);
        LODWORD(v53) = v25;
        v45 = CLSID;
        LODWORD(v51) = (_DWORD)bstrVal;
        bstrVal = pwzURI[0].bstrVal;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
          (__int64)&dword_18158CCA8,
          (__int64)&byte_18154B927,
          (__int64)(PrimaryTraceActivity + 2),
          v38,
          &bstrVal,
          (__int64)&v53,
          (__int64)&v51,
          (__int64 *)&v45,
          (__int64 *)&v49);
      }
    }
    SysFreeString(bstrString);
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v20, v39);
    SysFreeString(pbstr);
    VariantClear(pwzURI);
  }
  if ( v52 && v8 )
  {
    if ( v11 == 4 )
    {
      memset(pwzURI, 0, 24);
      pwzURI[0].vt = 8;
      CAPProcessor::GetURLForPhishingEval(this, &pwzURI[0].bstrVal);
      IECompatLogAntiphishingUrl(pwzURI[0].bstrVal, 1u);
      v40 = *((_QWORD *)this + 27);
      LODWORD(v51) = 1;
      if ( (*(_BYTE *)(v40 + 8) & 0x20) == 0 )
      {
        v41 = CDoc::PrimaryMarkup(v8);
        v42 = (CAPProcessor *)*((_QWORD *)v8 + 732);
        if ( v42 )
        {
          if ( (int)CAPProcessor::ShouldShowPhishingFilterDialog(v42, v41, (int *)&v51) >= 0 && !(_DWORD)v51 )
            v11 = 7;
        }
      }
      VariantClear(pwzURI);
    }
    v43 = v11 | 0x100;
    if ( *(int *)(*((_QWORD *)this + 27) + 24LL) >= 0 )
      v43 = v11;
    CDoc::SetPhishingFilterStatus(v8, v43);
  }
  return 0;
}

```

## disassembly

```asm
0x180847b6c  push    rbp
0x180847b6e  push    rbx
0x180847b6f  push    rsi
0x180847b70  push    rdi
0x180847b71  push    r12
0x180847b73  push    r13
0x180847b75  push    r14
0x180847b77  push    r15
0x180847b79  lea     rbp, [rsp-1Fh]
0x180847b7e  sub     rsp, 0A8h
0x180847b85  mov     rbx, rcx
0x180847b88  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x180847b8d  xor     r14d, r14d
0x180847b90  test    rax, rax
0x180847b93  jz      short loc_180847BA0
0x180847b95  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x180847b9a  mov     r8, [rax+78h]
0x180847b9e  jmp     short loc_180847BA3
0x180847ba0  mov     r8, r14
0x180847ba3  mov     [rbp+57h+arg_10], r8
0x180847ba7  call    ?Doc@CMarkup@@QEBAPEAVCDoc@@XZ; CMarkup::Doc(void)
0x180847bac  mov     rcx, [rcx+0D8h]
0x180847bb3  mov     r15, rax
0x180847bb6  test    rcx, rcx
0x180847bb9  jnz     short loc_180847BC3
0x180847bbb  lea     eax, [rcx+1]
0x180847bbe  jmp     loc_1808481C1
0x180847bc3  mov     edx, [rcx+1Ch]
0x180847bc6  mov     esi, 1
0x180847bcb  lea     r9d, [rsi+4]
0x180847bcf  lea     r13d, [rsi+1]
0x180847bd3  test    sil, dl
0x180847bd6  jz      short loc_180847BE8
0x180847bd8  mov     edi, r13d
0x180847bdb  test    edx, 210h
0x180847be1  jz      short loc_180847C08
0x180847be3  test    dl, 10h
0x180847be6  jnz     short loc_180847C29
0x180847be8  mov     eax, edx
0x180847bea  and     al, r13b
0x180847bed  neg     al
0x180847bef  sbb     edi, edi
0x180847bf1  neg     edi
0x180847bf3  add     edi, 3
0x180847bf6  test    dl, 14h
0x180847bf9  jnz     short loc_180847C29
0x180847bfb  bt      edx, 9
0x180847bff  jnb     short loc_180847C08
0x180847c01  mov     edi, 9
0x180847c06  jmp     short loc_180847C2C
0x180847c08  mov     [rbp+57h+arg_8], r14d
0x180847c0c  cmp     [rcx+20h], esi
0x180847c0f  jnz     short loc_180847C36
0x180847c11  cmp     dword ptr [rcx+34h], 3
0x180847c15  jnz     short loc_180847C21
0x180847c17  mov     eax, 6
0x180847c1c  cmp     edi, r13d
0x180847c1f  jz      short loc_180847C24
0x180847c21  mov     eax, r9d
0x180847c24  mov     [rcx+34h], eax
0x180847c27  jmp     short loc_180847C33
0x180847c29  mov     edi, r9d
0x180847c2c  mov     dword ptr [rcx+34h], 6
0x180847c33  mov     [rbp+57h+arg_8], esi
0x180847c36  mov     r12d, 8
0x180847c3c  test    r8, r8
0x180847c3f  jz      loc_18084810D
0x180847c45  lea     eax, [rdi-5]
0x180847c48  test    eax, 0FFFFFFFBh
0x180847c4d  jnz     loc_18084810D
0x180847c53  mov     rcx, rbx
0x180847c56  call    _anonymous_namespace___WasBlockedInFrame
0x180847c5b  test    al, al
0x180847c5d  jnz     loc_18084810D
0x180847c63  cmp     [rbx+0F8h], r14b
0x180847c6a  jnz     loc_18084810D
0x180847c70  mov     rax, [rbx+0D8h]
0x180847c77  test    [rax+8], sil
0x180847c7b  jnz     loc_18084810D
0x180847c81  xorps   xmm0, xmm0
0x180847c84  lea     rdx, [rbp+57h+pwzURI+8]; unsigned __int16 **
0x180847c88  xor     eax, eax
0x180847c8a  mov     rcx, rbx; struct CMarkup *
0x180847c8d  movups  xmmword ptr [rbp-9], xmm0
0x180847c91  mov     word ptr [rbp+57h+pwzURI], r12w
0x180847c96  mov     [rbp+57h+var_50], rax
0x180847c9a  call    ?GetURLForPhishingEval@CAPProcessor@@SAJPEAVCMarkup@@PEAPEAG@Z; CAPProcessor::GetURLForPhishingEval(CMarkup *,ushort * *)
0x180847c9f  mov     rcx, cs:?IEVALUE_PhishingFilter_PreventOverride@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_PhishingFilter_PreventOverride
0x180847ca6  lea     rdx, [rbp+57h+arg_0]
0x180847caa  mov     dword ptr [rbp+57h+arg_0], r14d
0x180847cae  call    GetBOOL
0x180847cb3  mov     rcx, [rbp+57h+pwzURI+8]; pwzURI
0x180847cb7  lea     r9, [rbp+57h+ppURI]; ppURI
0x180847cbb  xor     r8d, r8d; dwReserved
0x180847cbe  mov     [rbp+57h+pbstr], r14
0x180847cc2  mov     edx, 3002B80h; dwFlags
0x180847cc7  mov     [rbp+57h+ppURI], r14
0x180847ccb  call    cs:__imp_CreateUri
0x180847cd2  nop     dword ptr [rax+rax+00h]
0x180847cd7  test    eax, eax
0x180847cd9  js      short loc_180847CFF
0x180847cdb  mov     rcx, [rbp+57h+ppURI]
0x180847cdf  lea     rdx, [rbp+57h+pbstr]
0x180847ce3  mov     rax, [rcx]
0x180847ce6  mov     rax, [rax+68h]
0x180847cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180847cef  mov     rcx, [rbp+57h+ppURI]
0x180847cf3  mov     rax, [rcx]
0x180847cf6  mov     rax, [rax+10h]
0x180847cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180847cff  mov     rcx, [rbp+57h+pbstr]; pbstr
0x180847d03  call    cs:__imp_SysStringLen
0x180847d0a  nop     dword ptr [rax+rax+00h]
0x180847d0f  mov     rcx, [rbx+0D8h]
0x180847d16  lea     r9, [rbp+57h+var_70]; ppURI
0x180847d1a  mov     [rbp+57h+bstrString], r14
0x180847d1e  xor     r8d, r8d; dwReserved
0x180847d21  mov     [rbp+57h+var_70], r14
0x180847d25  mov     edx, 3002B80h; dwFlags
0x180847d2a  lea     r12d, [rax+21h]
0x180847d2e  mov     rcx, [rcx+10h]; pwzURI
0x180847d32  call    cs:__imp_CreateUri
0x180847d39  nop     dword ptr [rax+rax+00h]
0x180847d3e  test    eax, eax
0x180847d40  js      short loc_180847D66
0x180847d42  mov     rcx, [rbp+57h+var_70]
0x180847d46  lea     rdx, [rbp+57h+bstrString]
0x180847d4a  mov     rax, [rcx]
0x180847d4d  mov     rax, [rax+68h]
0x180847d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180847d56  mov     rcx, [rbp+57h+var_70]
0x180847d5a  mov     rax, [rcx]
0x180847d5d  mov     rax, [rax+10h]
0x180847d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180847d66  mov     rcx, [rbp+57h+bstrString]; pbstr
0x180847d6a  test    rcx, rcx
0x180847d6d  jz      short loc_180847DA6
0x180847d6f  mov     r9, [rbp+57h+pbstr]
0x180847d73  mov     rdx, rcx
0x180847d76  sub     r9, rcx
0x180847d79  movzx   r8d, word ptr [rdx]
0x180847d7d  movzx   eax, word ptr [rdx+r9]
0x180847d82  sub     r8d, eax
0x180847d85  jnz     short loc_180847D8E
0x180847d87  add     rdx, r13
0x180847d8a  test    eax, eax
0x180847d8c  jnz     short loc_180847D79
0x180847d8e  test    r8d, r8d
0x180847d91  jz      short loc_180847DA6
0x180847d93  call    cs:__imp_SysStringLen
0x180847d9a  nop     dword ptr [rax+rax+00h]
0x180847d9f  add     r12d, 12h
0x180847da3  add     r12d, eax
0x180847da6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180847dad  mov     r14d, r12d
0x180847db0  mov     rax, r13
0x180847db3  mul     r14
0x180847db6  cmovb   rax, rcx
0x180847dba  mov     rcx, cs:g_hProcessHeap
0x180847dc1  mov     rdx, rax
0x180847dc4  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180847dc9  mov     [rbp+57h+var_88], rax
0x180847dcd  mov     r13, rax
0x180847dd0  test    rax, rax
0x180847dd3  jz      loc_1808480C7
0x180847dd9  mov     r9d, [r15+13B8h]
0x180847de0  mov     r8d, [r15+13BCh]
0x180847de7  mov     edx, [r15+13B4h]
0x180847dee  mov     ecx, [r15+13B0h]; this
0x180847df5  call    ?IsIndependent@CDXDependentSurfacePresenterFlip@@UEAA_NXZ; CDXDependentSurfacePresenterFlip::IsIndependent(void)
0x180847dfa  mov     rcx, [rbp+57h+pbstr]; pbstr
0x180847dfe  call    cs:__imp_SysStringLen
0x180847e05  nop     dword ptr [rax+rax+00h]
0x180847e0a  mov     rcx, [rbx+0D8h]
0x180847e11  mov     edx, r14d; unsigned __int64
0x180847e14  add     eax, 21h ; '!'
0x180847e17  mov     r9d, [rcx+1Ch]
0x180847e1b  mov     rcx, r13; unsigned __int16 *
0x180847e1e  cmp     r12d, eax
0x180847e21  jbe     short loc_180847E4A
0x180847e23  mov     rax, [rbp+57h+bstrString]
0x180847e27  lea     r8, aThreatsDBlockD_0; "?Threats=%d&Block=%d&Host=%s&BlockedDom"...
0x180847e2e  mov     [rsp+0E0h+var_B0], rax
0x180847e33  mov     rax, [rbp+57h+pbstr]
0x180847e37  mov     [rsp+0E0h+var_B8], rax
0x180847e3c  mov     eax, dword ptr [rbp+57h+arg_0]
0x180847e3f  mov     dword ptr [rsp+0E0h+Src], eax
0x180847e43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180847e48  jmp     short loc_180847E66
0x180847e4a  mov     rax, [rbp+57h+pbstr]
0x180847e4e  lea     r8, aThreatsDBlockD_1; "?Threats=%d&Block=%d&Host=%s"
0x180847e55  mov     [rsp+0E0h+var_B8], rax
0x180847e5a  mov     eax, dword ptr [rbp+57h+arg_0]
0x180847e5d  mov     dword ptr [rsp+0E0h+Src], eax
0x180847e61  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180847e66  mov     rcx, [rbp+57h+pwzURI+8]
0x180847e6a  xor     edx, edx
0x180847e6c  call    cs:__imp_?IECompatLogAntiphishingUrl@@YAXPEBGK@Z; IECompatLogAntiphishingUrl(ushort const *,ulong)
0x180847e73  nop     dword ptr [rax+rax+00h]
0x180847e78  test    dword ptr [rbx+2ECh], 8000000h
0x180847e82  mov     rcx, rbx; this
0x180847e85  jz      short loc_180847E8E
0x180847e87  call    ?IsPendingPrimaryMarkup@CMarkup@@QEBAHXZ; CMarkup::IsPendingPrimaryMarkup(void)
0x180847e8c  jmp     short loc_180847E93
0x180847e8e  call    ?IsPrimaryMarkup@CMarkup@@QEBAHXZ; CMarkup::IsPrimaryMarkup(void)
0x180847e93  mov     r9, [rbp+57h+arg_10]; struct CWindow *
0x180847e97  test    eax, eax
0x180847e99  mov     rdx, [rbp+57h+pwzURI+8]; unsigned __int16 *
0x180847e9d  mov     r8, r13; unsigned __int16 *
0x180847ea0  setz    r14b
0x180847ea4  mov     rcx, r15; struct CDoc *
0x180847ea7  mov     byte ptr [rsp+0E0h+Src], r14b; bool
0x180847eac  call    ?NavigateToPhishingErrorPage@@YAJPEAVCDoc@@PEBG1PEAVCWindow@@_N@Z; NavigateToPhishingErrorPage(CDoc *,ushort const *,ushort const *,CWindow *,bool)
0x180847eb1  xor     r12d, r12d
0x180847eb4  mov     dword ptr [rbp+57h+arg_18], eax
0x180847eb7  test    eax, eax
0x180847eb9  js      loc_180847FFF
0x180847ebf  test    r14b, r14b
0x180847ec2  jz      loc_180847FE5
0x180847ec8  lea     rdx, [rbp+57h+arg_0]; struct CMarkup **
0x180847ecc  mov     [rbp+57h+arg_0], r12
0x180847ed0  mov     rcx, rbx; this
0x180847ed3  call    ?GetTopmostMarkup@CMarkup@@QEAAJPEAPEAV1@@Z; CMarkup::GetTopmostMarkup(CMarkup * *)
0x180847ed8  test    eax, eax
0x180847eda  js      loc_180847FE5
0x180847ee0  mov     rcx, rbx; struct CMarkup *
0x180847ee3  call    ?GetUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetUrl(CMarkup const * const)
0x180847ee8  mov     r12, rax
0x180847eeb  test    rax, rax
0x180847eee  jz      loc_180847FE5
0x180847ef4  mov     rcx, [rbp+57h+arg_0]; struct CMarkup *
0x180847ef8  call    ?GetUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetUrl(CMarkup const * const)
0x180847efd  mov     r13, rax
0x180847f00  test    rax, rax
0x180847f03  jz      loc_180847FE1
0x180847f09  mov     dword ptr [rbp+57h+arg_0], 0
0x180847f10  call    cs:__imp_GetCurrentThreadId
0x180847f17  nop     dword ptr [rax+rax+00h]
0x180847f1c  xor     r9d, r9d
0x180847f1f  lea     r8, [rbp+57h+arg_0]
0x180847f23  mov     edx, eax
0x180847f25  mov     ecx, 203h
0x180847f2a  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x180847f31  nop     dword ptr [rax+rax+00h]
0x180847f36  test    eax, eax
0x180847f38  js      loc_180847FE1
0x180847f3e  mov     ecx, dword ptr [rbp+57h+arg_0]
0x180847f41  lea     rax, [rbp+57h+var_68]
0x180847f45  lea     r9, [rbp+57h+arg_10]
0x180847f49  mov     [rsp+0E0h+Src], rax
0x180847f4e  xor     r8d, r8d
0x180847f51  mov     dword ptr [rbp+57h+arg_10], 0
0x180847f58  xor     edx, edx
0x180847f5a  mov     [rbp+57h+var_68], 0
0x180847f62  call    cs:__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z; IsoGetTrustSplitComponent(ulong,ulong,_IsoComponent * *,ulong *,_IsoUntrustedComponent * *)
0x180847f69  nop     dword ptr [rax+rax+00h]
0x180847f6e  test    eax, eax
0x180847f70  js      short loc_180847FE1
0x180847f72  mov     ecx, 2098h; cb
0x180847f77  call    cs:__imp_CoTaskMemAlloc
0x180847f7e  nop     dword ptr [rax+rax+00h]
0x180847f83  mov     r14, rax
0x180847f86  test    rax, rax
0x180847f89  jz      short loc_180847FD2
0x180847f8b  xor     ecx, ecx
0x180847f8d  mov     r11d, 825h
0x180847f93  cmp     edi, 5
0x180847f96  mov     r8, r12; unsigned __int16 *
0x180847f99  mov     edx, r11d; unsigned __int64
0x180847f9c  setnz   cl
0x180847f9f  add     ecx, esi
0x180847fa1  mov     [rax], ecx
0x180847fa3  lea     rcx, [rax+4]; unsigned __int16 *
0x180847fa7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180847fac  lea     rcx, [r14+104Eh]; unsigned __int16 *
0x180847fb3  mov     r8, r13; unsigned __int16 *
0x180847fb6  mov     edx, r11d; unsigned __int64
0x180847fb9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180847fbe  mov     rcx, [rbp+57h+var_68]
0x180847fc2  mov     edx, dword ptr [rbp+57h+arg_0]; int
0x180847fc5  mov     [rsp+0E0h+Src], r14; Src
0x180847fca  mov     ecx, [rcx+48h]; int
0x180847fcd  call    ?Post@?$TFlatIsoMessage@ULCIE_CONTENT_BLOCK_MSG@@@@SAJKKKKPEBULCIE_CONTENT_BLOCK_MSG@@@Z; TFlatIsoMessage<LCIE_CONTENT_BLOCK_MSG>::Post(ulong,ulong,ulong,ulong,LCIE_CONTENT_BLOCK_MSG const *)
0x180847fd2  mov     rcx, r14; pv
0x180847fd5  call    cs:__imp_CoTaskMemFree
0x180847fdc  nop     dword ptr [rax+rax+00h]
0x180847fe1  mov     r13, [rbp+57h+var_88]
0x180847fe5  mov     rcx, [rbx+0D8h]
0x180847fec  xor     r12d, r12d
0x180847fef  mov     eax, [rcx+8]
0x180847ff2  test    al, 8
0x180847ff4  jnz     short loc_180847FFF
0x180847ff6  or      eax, 8
0x180847ff9  mov     r12d, esi
0x180847ffc  mov     [rcx+8], eax
0x180847fff  mov     rcx, r15
0x180848002  call    ?GetPrimaryTraceActivity@CDoc@@QEAAPEBV?$TraceLoggingActivity@$1?g_hAsimovProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAC@$04U_TlgReflectorTag_Param0IsHProvider@@@@XZ; CDoc::GetPrimaryTraceActivity(void)
0x180848007  mov     r14, rax
0x18084800a  test    rax, rax
0x18084800d  jnz     short loc_18084801A
  ... truncated ...
```
