# CDwnBindData::SignalRedirect(ushort const *,IUnknown *)

- ea: `0x1803ff520`
- end: `0x1803fffd5`
- name: `?SignalRedirect@CDwnBindData@@AEAAXPEBGPEAUIUnknown@@@Z`
- size: `2741`
- prototype: `void __fastcall(CDwnBindData *__hidden this, LPCWSTR pwzURI, struct IUnknown *)`
- caller_count: `2`
- callee_count: `43`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801621d0`
- `0x180412a00`

## callees

- `0x180013efc`
- `0x180051c00`
- `0x18005ce98`
- `0x18005e648`
- `0x18006b2e8`
- `0x1800c5000`
- `0x1800ea428`
- `0x18015a504`
- `0x18015b408`
- `0x18015b784`
- `0x180160338`
- `0x180160f84`
- `0x1801dc4a4`
- `0x18029d9dc`
- `0x1802d6a54`
- `0x180305cd8`
- `0x18030652c`
- `0x1803e4410`
- `0x1803ff520`
- `0x1803fffdc`
- `0x180400074`
- `0x180400d3c`
- `0x180400e88`
- `0x180411f40`
- `0x1804133d8`
- `0x180414378`
- `0x1805f7f7c`
- `0x18061a494`
- `0x180626970`
- `0x18065b5b0`
- `0x180680cc8`
- `0x1806d4e70`
- `0x18074f648`
- `0x1807c0534`
- `0x1807d2230`
- `0x1807e89c8`
- `0x18085d3f0`
- `0x18097ccbc`
- `0x1810f64f2`
- `0x1810f6516`
- `0x1810f658e`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1803fff09`
- `KERNEL32!LeaveCriticalSection` at `0x1803fff3e`
- `KERNEL32!LeaveCriticalSection` at `0x1803fff09`
- `KERNEL32!LeaveCriticalSection` at `0x1803fff3e`
- `KERNEL32!EnterCriticalSection` at `0x1803ffee9`
- `KERNEL32!EnterCriticalSection` at `0x1803ffee9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x1803ff97f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x1803ff97f`
- `iertutil!CreateUri` at `0x1803ff656`
- `iertutil!CreateUri` at `0x1803ff656`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803ffe1d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803ffe1d`
- `urlmon!__imp_MapUriToBrowserEmulationState` at `0x1803ffce7`
- `urlmon!__imp_MapUriToBrowserEmulationState` at `0x1803ffce7`
- `urlmon!__imp_MapBrowserEmulationStateToUserAgent` at `0x1803ffde6`
- `urlmon!__imp_MapBrowserEmulationStateToUserAgent` at `0x1803ffde6`
- `OLEAUT32!__imp_SysFreeString` at `0x1803ff99a`
- `OLEAUT32!__imp_SysFreeString` at `0x1803ff9b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1803ff99a`
- `OLEAUT32!__imp_SysFreeString` at `0x1803ff9b0`
- `OLEAUT32!__imp_SysStringLen` at `0x1803ff958`
- `OLEAUT32!__imp_SysStringLen` at `0x1803ff969`
- `OLEAUT32!__imp_SysStringLen` at `0x1803ff958`
- `OLEAUT32!__imp_SysStringLen` at `0x1803ff969`

## pseudocode

```c
void __fastcall CDwnBindData::SignalRedirect(CDwnBindData *this, WCHAR *pwzURI, struct IUnknown *a3)
{
  bool v3; // zf
  __int64 v7; // rax
  const WCHAR **v8; // rcx
  int W3COriginFromUri; // edi
  __int64 v10; // rcx
  __int64 v11; // rdx
  void *v12; // r8
  const wchar_t **v13; // r15
  __int64 v14; // rdx
  struct IUnknownVtbl *lpVtbl; // rcx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v17; // rdx
  void *v18; // r8
  HRESULT (__stdcall *v19)(IUnknown *, const IID *const, void **); // rbx
  __int64 *v20; // rax
  struct IUri *v21; // rbx
  OLECHAR *v22; // r14
  int v23; // eax
  struct IUri v24; // rax
  WCHAR *v25; // r12
  UINT v26; // ebx
  __int64 v27; // rcx
  _QWORD *v28; // rax
  _QWORD *v29; // r14
  __int64 v30; // r14
  __int64 v31; // r15
  _OWORD *v32; // rax
  _OWORD *v33; // rcx
  __int64 v34; // rdx
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  int *v43; // r14
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int64 v46; // rax
  BOOL v47; // ebx
  unsigned int v48; // edi
  BSTR v49; // rbx
  char *v50; // rax
  _OWORD *v51; // rcx
  __int128 v52; // xmm1
  CMarkup *v53; // rcx
  void *v54; // r8
  __int64 v55; // rax
  __int64 v56; // rcx
  CMarkup *v57; // rcx
  struct IUnknown *v58; // r10
  __int64 v59; // rcx
  CMSPerformanceData *v60; // rbx
  struct IInternetSecurityManager *v61; // r12
  struct IUri *v62; // r15
  struct IUri *v63; // r13
  struct tagVARIANT *v64; // [rsp+28h] [rbp-D8h]
  BSTR pbstr; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v66; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int8 v67[8]; // [rsp+50h] [rbp-B0h] BYREF
  IUri *ppURI; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v69; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v70; // [rsp+68h] [rbp-98h] BYREF
  int v71; // [rsp+70h] [rbp-90h] BYREF
  CMSPerformanceData *v72; // [rsp+78h] [rbp-88h] BYREF
  _BYTE Buf2[448]; // [rsp+80h] [rbp-80h] BYREF
  char Buf1[448]; // [rsp+240h] [rbp+140h] BYREF
  char v75[16]; // [rsp+400h] [rbp+300h] BYREF
  unsigned __int16 v76[16]; // [rsp+410h] [rbp+310h] BYREF

  v71 = 16;
  v3 = (*((_BYTE *)this + 180) & 1) == 0;
  ppURI = 0;
  v70 = 0;
  v72 = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 96) = 0;
  if ( !v3 )
  {
    v7 = *((_QWORD *)this + 10);
    if ( v7 )
    {
      v8 = *(const WCHAR ***)(v7 + 104);
      if ( v8 )
      {
        if ( IsSecurityErrorPage(v8, pwzURI) )
        {
          CDoc::Exec(*(CDoc **)(*((_QWORD *)this + 10) + 104LL), &CGID_MSHTML, 0x85Au, 2u, 0, 0);
          W3COriginFromUri = -2146697196;
LABEL_6:
          CDwnBindData::SignalDone(this, W3COriginFromUri);
          goto LABEL_7;
        }
      }
    }
  }
  W3COriginFromUri = CreateUri(pwzURI, 0x3002B84u, 0, &ppURI);
  if ( W3COriginFromUri )
    goto LABEL_6;
  v13 = (const wchar_t **)((char *)this + 528);
  CStr::_Free((CDwnBindData *)((char *)this + 528), v11, v12);
  v14 = v70;
  *((_QWORD *)this + 66) = 0;
  lpVtbl = a3->lpVtbl;
  v70 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( !((unsigned int (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
          a3,
          &IID_IWinInetHttpInfo,
          &v70) )
  {
    if ( v70 )
    {
      v64 = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64, __int64, char *, int *, _QWORD))(*(_QWORD *)v70 + 32LL))(
              v70,
              45,
              v75,
              &v71,
              0) )
      {
        if ( v71 )
        {
          AnsiToWideTrivial(v75, v76, 16, v71);
          W3COriginFromUri = CStr::Set((const unsigned __int16 **)this + 66, v76);
          if ( W3COriginFromUri )
            goto LABEL_6;
          if ( !wcscmp_0(L"POST", *v13) )
          {
            LODWORD(v66) = 0;
            LODWORD(v69) = 4;
            v64 = 0;
            if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, struct IUnknown **, _QWORD))(*(_QWORD *)v70 + 32LL))(
                    v70,
                    536870931,
                    &v66,
                    &v69,
                    0)
              && (_DWORD)v69
              && (unsigned int)(v66 - 307) > 1 )
            {
              *(_DWORD *)v67 = 0;
              pbstr = 0;
              if ( (_DWORD)v66 != 301
                || (v19 = a3->lpVtbl->QueryInterface,
                    v20 = TSmartPointer<ID3D11Device>::operator&((__int64 *)&pbstr),
                    ((int (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v19)(
                      a3,
                      &GUID_f3d8f080_a5eb_476f_9d19_a5ef24e5c2e6,
                      v20) < 0)
                || (*(int (__fastcall **)(BSTR, unsigned __int8 *))(*(_QWORD *)pbstr + 120LL))(pbstr, v67) < 0
                || !*(_DWORD *)v67 )
              {
                W3COriginFromUri = CStr::Set((const unsigned __int16 **)this + 66, L"GET");
                if ( W3COriginFromUri )
                {
                  TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>((__int64 *)&pbstr);
                  goto LABEL_6;
                }
              }
              TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>((__int64 *)&pbstr);
            }
          }
        }
      }
    }
  }
  *((_DWORD *)this + 183) = IsUriSecure(ppURI, v17, v18) != 0;
  CDwnBindData::ReportRedirectToAPFilter(this, pwzURI);
  if ( *((_DWORD *)this + 50) )
  {
    v21 = (struct IUri *)*((_QWORD *)this + 59);
    if ( v21 || (v21 = (struct IUri *)*((_QWORD *)this + 111)) != 0 )
    {
      pbstr = 0;
      v22 = 0;
      if ( (*((_DWORD *)this + 45) & 0x200) != 0
        || (v23 = GetW3COriginFromUri(v21, 0, &pbstr), v22 = pbstr, (W3COriginFromUri = v23) == 0) )
      {
        v24.lpVtbl = v21->lpVtbl;
        LODWORD(v66) = 0;
        *(_DWORD *)v67 = 0;
        if ( ((int (__fastcall *)(struct IUri *, __int64 *))v24.lpVtbl->GetScheme)(v21, &v66) >= 0
          && ((int (__fastcall *)(IUri *, unsigned __int8 *))ppURI->lpVtbl->GetScheme)(ppURI, v67) >= 0
          && (*(_DWORD *)v67 == 2 || *(_DWORD *)v67 == 11)
          && ((_DWORD)v66 != 11 || *(_DWORD *)v67 == 11) )
        {
          if ( (*((_DWORD *)this + 45) & 0x200) == 0 )
          {
            pbstr = 0;
            W3COriginFromUri = GetW3COriginFromUri(ppURI, 0, &pbstr);
            if ( !W3COriginFromUri )
            {
              v25 = pbstr;
              v26 = SysStringLen(pbstr);
              if ( SysStringLen(v22) != v26 || StrCmpW(v22, v25) )
                *((_DWORD *)this + 45) |= 0x200u;
              SysFreeString(v25);
            }
          }
        }
        else
        {
          W3COriginFromUri = -2147024891;
        }
      }
      SysFreeString(v22);
      if ( W3COriginFromUri )
        goto LABEL_6;
    }
  }
  W3COriginFromUri = CDwnBindData::SetRedirectUri((struct IUnknown **)this, (struct IUnknown *)ppURI);
  if ( W3COriginFromUri )
    goto LABEL_6;
  if ( !*v13 || wcscmp_0(L"POST", *v13) )
  {
    CDwnBindInfo::SetDwnPost(this, 0);
    v27 = *((_QWORD *)this + 36);
    if ( v27 )
    {
      pbstr = 0;
      (*(void (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v27 + 80LL))(
        v27,
        L"__HTMLLOADOPTIONSNAV",
        &pbstr);
      if ( pbstr )
      {
        v69 = 0;
        (**(void (__fastcall ***)(BSTR, GUID *, struct IUnknown **))pbstr)(pbstr, &IID_IHtmlLoadOptions, &v69);
        if ( v69 )
        {
          v66 = 0;
          *(_DWORD *)v67 = 8;
          W3COriginFromUri = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 *, unsigned __int8 *))v69->lpVtbl[1].QueryInterface)(
                               v69,
                               7,
                               &v66,
                               v67);
          if ( W3COriginFromUri || *(_DWORD *)v67 != 8 )
            v66 = 0x10000;
          else
            v66 |= 0x10000uLL;
          ((void (__fastcall *)(struct IUnknown *, __int64, __int64 *, __int64))v69->lpVtbl[1].AddRef)(v69, 7, &v66, 8);
          ReleaseInterface(v69);
        }
        ReleaseInterface((struct IUnknown *)pbstr);
      }
      else
      {
        v28 = MemoryProtection::HeapAllocClear<1>((MemoryProtection *)g_hProcessHeap, 0x40u);
        v29 = v28;
        if ( v28 )
        {
          v28[1] = 0;
          *v28 = &CBaseFT::`vftable';
          *((_DWORD *)v28 + 4) = 1;
          *((_DWORD *)v28 + 5) = 1;
          _InterlockedAdd(&g_lSecondaryObjCount, 1u);
          *v28 = &COptionArray::`vftable'{for `CBaseFT'};
          v28[3] = &COptionArray::`vftable'{for `IOptionArray'};
          *((_OWORD *)v28 + 2) = 0;
          *((GUID *)v28 + 3) = IID_IHtmlLoadOptions;
        }
        else
        {
          v29 = 0;
        }
        *(_QWORD *)v67 = 0x10000;
        COptionArray::SetOption((COptionArray *)(v29 + 3), 7u, v67, 8u);
        W3COriginFromUri = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int64))(**((_QWORD **)this + 36)
                                                                                                + 72LL))(
                             *((_QWORD *)this + 36),
                             L"__HTMLLOADOPTIONSNAV",
                             (unsigned __int64)(v29 + 3) & -(__int64)(v29 != 0));
        CBaseFT::Release((CBaseFT *)v29);
      }
    }
  }
  if ( *((char *)this + 419) < 0 )
  {
    v30 = *((_QWORD *)this + 10);
    if ( v30 )
    {
      v31 = 3;
      v32 = (_OWORD *)(v30 + 196);
      v33 = Buf2;
      v34 = 3;
      do
      {
        v35 = v32[1];
        *v33 = *v32;
        v36 = v32[2];
        v33[1] = v35;
        v37 = v32[3];
        v33[2] = v36;
        v38 = v32[4];
        v33[3] = v37;
        v39 = v32[5];
        v33[4] = v38;
        v40 = v32[6];
        v33[5] = v39;
        v41 = v32[7];
        v32 += 8;
        v33[6] = v40;
        v33[7] = v41;
        v33 += 8;
        --v34;
      }
      while ( v34 );
      v42 = *v32;
      v43 = *(int **)(v30 + 104);
      pbstr = 0;
      v44 = v32[1];
      *v33 = v42;
      v45 = v32[2];
      v46 = *((_QWORD *)v32 + 6);
      v33[1] = v44;
      v33[2] = v45;
      *((_QWORD *)v33 + 6) = v46;
      if ( v43 )
      {
        if ( (int)CDoc::EnsureSecurityManager((CDoc *)v43, (struct IInternetSecurityManagerEx2 **)&pbstr, 0) >= 0 )
        {
          v47 = IsWebPlatformHostBehaviorSupported<35>(v43[1260]);
          v48 = v47 | 4;
          if ( !CDXDependentSurfacePresenterFlip::IsIndependent((CDXDependentSurfacePresenterFlip *)(unsigned int)v43[1260]) )
            v48 = v47;
          memset_0(Buf1, 0, 0x1B8u);
          v49 = pbstr;
          W3COriginFromUri = MapUriToBrowserEmulationState(pbstr, ppURI, v48, Buf1, 0, v64);
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v49 + 16LL))(v49);
          if ( W3COriginFromUri )
            goto LABEL_6;
          MapWebPlatformVersionToEmulationMode(
            (const struct CDoc *)v43,
            (struct __MIDL___MIDL_itf_browsermode_0000_0000_0011 *)Buf1);
          if ( memcmp_0(Buf1, Buf2, 0x1B8u) )
          {
            v50 = Buf1;
            v51 = (_OWORD *)(*((_QWORD *)this + 10) + 196LL);
            do
            {
              *v51 = *(_OWORD *)v50;
              v51[1] = *((_OWORD *)v50 + 1);
              v51[2] = *((_OWORD *)v50 + 2);
              v51[3] = *((_OWORD *)v50 + 3);
              v51[4] = *((_OWORD *)v50 + 4);
              v51[5] = *((_OWORD *)v50 + 5);
              v51[6] = *((_OWORD *)v50 + 6);
              v52 = *((_OWORD *)v50 + 7);
              v50 += 128;
              v51[7] = v52;
              v51 += 8;
              --v31;
            }
            while ( v31 );
            *v51 = *(_OWORD *)v50;
            v51[1] = *((_OWORD *)v50 + 1);
            v51[2] = *((_OWORD *)v50 + 2);
            *((_QWORD *)v51 + 6) = *((_QWORD *)v50 + 6);
            v53 = *(CMarkup **)(*((_QWORD *)this + 10) + 112LL);
            if ( v53 )
              CMarkup::SetMobileEmulationState(v53, (struct __MIDL___MIDL_itf_browsermode_0000_0000_0011 *)Buf1);
            if ( (Buf1[4] & 0x40) == 0 )
            {
              pbstr = 0;
              W3COriginFromUri = MapBrowserEmulationStateToUserAgent(Buf1, &pbstr);
              if ( W3COriginFromUri )
                goto LABEL_6;
              W3COriginFromUri = CDwnDoc::SetString(
                                   (const unsigned __int16 **)(*((_QWORD *)this + 10) + 704LL),
                                   pbstr,
                                   v54);
              if ( pbstr )
                CoTaskMemFree(pbstr);
              if ( W3COriginFromUri )
                goto LABEL_6;
            }
          }
        }
      }
    }
  }
  if ( (*((_BYTE *)this + 180) & 1) != 0 )
  {
    v55 = *((_QWORD *)this + 10);
    if ( v55 )
    {
      v56 = *(_QWORD *)(v55 + 104);
      if ( v56 )
      {
        if ( *(_QWORD *)(v56 + 64) )
        {
          v57 = *(CMarkup **)(v55 + 112);
          if ( v57 )
          {
            if ( (*((_DWORD *)v57 + 188) & 0x100000) != 0 && (unsigned int)CMarkup::IsPrimaryMarkup(v57) )
              CTExec(v58, &CGID_ShellDocView, 0x8Au, 0, 0, 0);
          }
        }
      }
    }
    v59 = *((_QWORD *)this + 10);
    if ( v59 && CDwnDoc::GetPerfData(v59, &v72) )
    {
      v60 = v72;
      CMSPerformanceData::Redirected(v72);
      AddRefSharedSecurityManager();
      v61 = s_pISM;
      if ( s_pISM )
      {
        v62 = ppURI;
        v63 = (struct IUri *)*((_QWORD *)this + 111);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v60 + 48));
        if ( *((_BYTE *)v60 + 24) )
        {
          if ( !CMSPerformanceData::CheckSameOrigin(v63, v62, v61) )
          {
            *((_BYTE *)v60 + 24) = 0;
            CMSPerformanceData::SetNavigationUri(v60, v62);
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v60 + 48));
        }
        else
        {
          CMSPerformanceData::SetNavigationUri(v60, v62);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v60 + 48));
        }
      }
      DecrementSharedSecurityManager();
    }
  }
  if ( *((_QWORD *)this + 134) && *((_DWORD *)this + 267) )
  {
    AddRefSharedSecurityManager();
    if ( s_pISM )
      CMSPerformanceData::ResourceRedirected(
        *((CMSPerformanceData **)this + 134),
        (CDwnBindData *)((char *)this + 1064),
        ppURI,
        s_pISM);
    DecrementSharedSecurityManager();
  }
  if ( W3COriginFromUri )
    goto LABEL_6;
  CDwnBindData::Signal(this, 2);
  CDwnBindData::AddToPrivacyList(this);
  CDwnBindData::ResetPrivacyInfo(this);
  if ( (*((_BYTE *)this + 180) & 4) != 0 )
    CDwnBindData::AddToPrivacyList(this);
  CDwnBindData::SetSiteUri((struct IUnknown **)this, (struct IUnknown *)ppURI);
LABEL_7:
  ReleaseInterface((struct IUnknown *)ppURI);
  TSmartPointer<CMSPerformanceData>::~TSmartPointer<CMSPerformanceData>((volatile signed __int32 **)&v72);
  v10 = v70;
  v70 = 0;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
}

```

## disassembly

```asm
0x1803ff520  mov     [rsp-8+arg_18], rbx
0x1803ff525  push    rbp
0x1803ff526  push    rsi
0x1803ff527  push    rdi
0x1803ff528  push    r12
0x1803ff52a  push    r13
0x1803ff52c  push    r14
0x1803ff52e  push    r15
0x1803ff530  lea     rbp, [rsp-340h]
0x1803ff538  sub     rsp, 440h
0x1803ff53f  mov     rax, cs:__security_cookie
0x1803ff546  xor     rax, rsp
0x1803ff549  mov     [rbp+370h+var_40], rax
0x1803ff550  xor     r13d, r13d
0x1803ff553  mov     [rsp+470h+var_400], 10h
0x1803ff55b  test    byte ptr [rcx+0B4h], 1
0x1803ff562  mov     r14, r8
0x1803ff565  mov     r12, rdx
0x1803ff568  mov     [rsp+470h+ppURI], r13
0x1803ff56d  mov     rsi, rcx
0x1803ff570  mov     [rsp+470h+var_408], r13
0x1803ff575  mov     [rsp+470h+var_3F8], r13
0x1803ff57a  mov     [rcx+1C8h], r13
0x1803ff581  mov     [rcx+300h], r13
0x1803ff588  jz      loc_1803FF646
0x1803ff58e  mov     rax, [rcx+50h]
0x1803ff592  test    rax, rax
0x1803ff595  jz      loc_1803FF646
0x1803ff59b  mov     rcx, [rax+68h]; struct CDoc *
0x1803ff59f  test    rcx, rcx
0x1803ff5a2  jz      loc_1803FF646
0x1803ff5a8  call    ?IsSecurityErrorPage@@YAHPEAVCDoc@@PEBG@Z; IsSecurityErrorPage(CDoc *,ushort const *)
0x1803ff5ad  test    eax, eax
0x1803ff5af  jz      loc_1803FF646
0x1803ff5b5  mov     rcx, [rsi+50h]
0x1803ff5b9  lea     r9d, [r13+2]; unsigned int
0x1803ff5bd  mov     [rsp+470h+var_448], r13; struct tagVARIANT *
0x1803ff5c2  lea     rdx, CGID_MSHTML; struct _GUID *
0x1803ff5c9  mov     r8d, 85Ah; unsigned int
0x1803ff5cf  mov     [rsp+470h+var_450], r13; struct tagVARIANT *
0x1803ff5d4  mov     rcx, [rcx+68h]; this
0x1803ff5d8  call    ?Exec@CDoc@@UEAAJPEBU_GUID@@KKPEAUtagVARIANT@@1@Z; CDoc::Exec(_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x1803ff5dd  mov     edi, 800C0014h
0x1803ff5e2  mov     edx, edi; int
0x1803ff5e4  mov     rcx, rsi; this
0x1803ff5e7  call    ?SignalDone@CDwnBindData@@AEAAXJ@Z; CDwnBindData::SignalDone(long)
0x1803ff5ec  mov     rcx, [rsp+470h+ppURI]; struct IUnknown *
0x1803ff5f1  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1803ff5f6  lea     rcx, [rsp+470h+var_3F8]
0x1803ff5fb  call    ??1?$TSmartPointer@VCMSPerformanceData@@@@QEAA@XZ; TSmartPointer<CMSPerformanceData>::~TSmartPointer<CMSPerformanceData>(void)
0x1803ff600  mov     rcx, [rsp+470h+var_408]
0x1803ff605  mov     [rsp+470h+var_408], r13
0x1803ff60a  test    rcx, rcx
0x1803ff60d  jz      short loc_1803FF61B
0x1803ff60f  mov     rax, [rcx]
0x1803ff612  mov     rax, [rax+10h]
0x1803ff616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803ff61b  mov     rcx, [rbp+370h+var_40]
0x1803ff622  xor     rcx, rsp; StackCookie
0x1803ff625  call    __security_check_cookie
0x1803ff62a  mov     rbx, [rsp+470h+arg_18]
0x1803ff632  add     rsp, 440h
0x1803ff639  pop     r15
0x1803ff63b  pop     r14
0x1803ff63d  pop     r13
0x1803ff63f  pop     r12
0x1803ff641  pop     rdi
0x1803ff642  pop     rsi
0x1803ff643  pop     rbp
0x1803ff644  retn
0x1803ff646  lea     r9, [rsp+470h+ppURI]; ppURI
0x1803ff64b  xor     r8d, r8d; dwReserved
0x1803ff64e  mov     edx, 3002B84h; dwFlags
0x1803ff653  mov     rcx, r12; pwzURI
0x1803ff656  call    cs:__imp_CreateUri
0x1803ff65d  nop     dword ptr [rax+rax+00h]
0x1803ff662  mov     edi, eax
0x1803ff664  test    eax, eax
0x1803ff666  jnz     loc_1803FF5E2
0x1803ff66c  lea     r15, [rsi+210h]
0x1803ff673  mov     rcx, r15; this
0x1803ff676  call    ?_Free@CStr@@AEAAXXZ; CStr::_Free(void)
0x1803ff67b  mov     rdx, [rsp+470h+var_408]
0x1803ff680  mov     [r15], r13
0x1803ff683  mov     rcx, [r14]
0x1803ff686  mov     [rsp+470h+var_408], r13
0x1803ff68b  mov     rbx, [rcx]
0x1803ff68e  test    rdx, rdx
0x1803ff691  jz      short loc_1803FF6A2
0x1803ff693  mov     rcx, [rdx]
0x1803ff696  mov     rax, [rcx+10h]
0x1803ff69a  mov     rcx, rdx
0x1803ff69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803ff6a2  lea     r8, [rsp+470h+var_408]
0x1803ff6a7  mov     rcx, r14
0x1803ff6aa  lea     rdx, IID_IWinInetHttpInfo
0x1803ff6b1  mov     rax, rbx
0x1803ff6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803ff6b9  test    eax, eax
0x1803ff6bb  jnz     loc_1803FF83A
0x1803ff6c1  mov     rcx, [rsp+470h+var_408]
0x1803ff6c6  test    rcx, rcx
0x1803ff6c9  jz      loc_1803FF83A
0x1803ff6cf  mov     rax, [rcx]
0x1803ff6d2  lea     r9, [rsp+470h+var_400]
0x1803ff6d7  mov     [rsp+470h+var_448], r13
0x1803ff6dc  lea     r8, [rbp+370h+var_70]
0x1803ff6e3  mov     edx, 2Dh ; '-'
0x1803ff6e8  mov     [rsp+470h+var_450], r13
0x1803ff6ed  mov     rax, [rax+20h]
0x1803ff6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803ff6f6  test    eax, eax
0x1803ff6f8  jnz     loc_1803FF83A
0x1803ff6fe  mov     r9d, [rsp+470h+var_400]; int
0x1803ff703  test    r9d, r9d
0x1803ff706  jz      loc_1803FF83A
0x1803ff70c  lea     r8d, [rax+10h]; unsigned __int64
0x1803ff710  lea     rdx, [rbp+370h+var_60]; unsigned __int16 *
0x1803ff717  lea     rcx, [rbp+370h+var_70]; char *
0x1803ff71e  call    ?AnsiToWideTrivial@@YAXPEBDPEAG_KJ@Z; AnsiToWideTrivial(char const *,ushort *,unsigned __int64,long)
0x1803ff723  lea     rdx, [rbp+370h+var_60]; unsigned __int16 *
0x1803ff72a  mov     rcx, r15; this
0x1803ff72d  call    ?Set@CStr@@QEAAJPEBG@Z; CStr::Set(ushort const *)
0x1803ff732  mov     edi, eax
0x1803ff734  test    eax, eax
0x1803ff736  jnz     loc_1803FF5E2
0x1803ff73c  mov     rdx, [r15]; String2
0x1803ff73f  lea     rcx, aPost; "POST"
0x1803ff746  call    wcscmp_0
0x1803ff74b  test    eax, eax
0x1803ff74d  jnz     loc_1803FF83A
0x1803ff753  mov     rcx, [rsp+470h+var_408]
0x1803ff758  lea     r9, [rsp+470h+var_410]
0x1803ff75d  mov     dword ptr [rsp+470h+var_428], r13d
0x1803ff762  lea     r8, [rsp+470h+var_428]
0x1803ff767  mov     dword ptr [rsp+470h+var_410], 4
0x1803ff76f  mov     edx, 20000013h
0x1803ff774  mov     [rsp+470h+var_448], r13
0x1803ff779  mov     rax, [rcx]
0x1803ff77c  mov     [rsp+470h+var_450], r13
0x1803ff781  mov     rax, [rax+20h]
0x1803ff785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803ff78a  test    eax, eax
0x1803ff78c  jnz     loc_1803FF83A
0x1803ff792  cmp     dword ptr [rsp+470h+var_410], r13d
0x1803ff797  jz      loc_1803FF83A
0x1803ff79d  mov     ecx, dword ptr [rsp+470h+var_428]
0x1803ff7a1  lea     eax, [rcx-133h]
0x1803ff7a7  cmp     eax, 1
0x1803ff7aa  jbe     loc_1803FF83A
0x1803ff7b0  mov     dword ptr [rsp+470h+var_420], r13d
0x1803ff7b5  mov     [rsp+470h+pbstr], r13
0x1803ff7ba  cmp     ecx, 12Dh
0x1803ff7c0  jnz     short loc_1803FF80C
0x1803ff7c2  mov     rax, [r14]
0x1803ff7c5  lea     rcx, [rsp+470h+pbstr]
0x1803ff7ca  mov     rbx, [rax]
0x1803ff7cd  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1803ff7d2  mov     r8, rax
0x1803ff7d5  lea     rdx, _GUID_f3d8f080_a5eb_476f_9d19_a5ef24e5c2e6
0x1803ff7dc  mov     rax, rbx
0x1803ff7df  mov     rcx, r14
0x1803ff7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803ff7e7  test    eax, eax
0x1803ff7e9  js      short loc_1803FF80C
0x1803ff7eb  mov     rcx, [rsp+470h+pbstr]
0x1803ff7f0  lea     rdx, [rsp+470h+var_420]
0x1803ff7f5  mov     rax, [rcx]
0x1803ff7f8  mov     rax, [rax+78h]
0x1803ff7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803ff801  test    eax, eax
0x1803ff803  js      short loc_1803FF80C
0x1803ff805  cmp     dword ptr [rsp+470h+var_420], r13d
0x1803ff80a  jnz     short loc_1803FF830
0x1803ff80c  lea     rdx, aGet_1; "GET"
0x1803ff813  mov     rcx, r15; this
0x1803ff816  call    ?Set@CStr@@QEAAJPEBG@Z; CStr::Set(ushort const *)
0x1803ff81b  mov     edi, eax
0x1803ff81d  test    eax, eax
0x1803ff81f  jz      short loc_1803FF830
0x1803ff821  lea     rcx, [rsp+470h+pbstr]; void *
0x1803ff826  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1803ff82b  jmp     loc_1803FF5E2
0x1803ff830  lea     rcx, [rsp+470h+pbstr]; void *
0x1803ff835  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1803ff83a  mov     rcx, [rsp+470h+ppURI]; struct IUri *
0x1803ff83f  call    ?IsUriSecure@@YAHPEAUIUri@@H@Z; IsUriSecure(IUri *,int)
0x1803ff844  mov     ecx, r13d
0x1803ff847  test    eax, eax
0x1803ff849  mov     rdx, r12; unsigned __int16 *
0x1803ff84c  setnz   cl
0x1803ff84f  mov     [rsi+2DCh], ecx
0x1803ff855  mov     rcx, rsi; this
0x1803ff858  call    ?ReportRedirectToAPFilter@CDwnBindData@@QEAAXPEBG@Z; CDwnBindData::ReportRedirectToAPFilter(ushort const *)
0x1803ff85d  test    edi, edi
0x1803ff85f  jnz     loc_1803FF5E2
0x1803ff865  cmp     [rsi+0C8h], r13d
0x1803ff86c  jz      loc_1803FF9C4
0x1803ff872  mov     rbx, [rsi+1D8h]
0x1803ff879  test    rbx, rbx
0x1803ff87c  jnz     short loc_1803FF88E
0x1803ff87e  mov     rbx, [rsi+378h]
0x1803ff885  test    rbx, rbx
0x1803ff888  jz      loc_1803FF9C4
0x1803ff88e  mov     r12d, 200h
0x1803ff894  mov     [rsp+470h+pbstr], r13
0x1803ff899  mov     r14, r13
0x1803ff89c  test    [rsi+0B4h], r12d
0x1803ff8a3  jnz     short loc_1803FF8C3
0x1803ff8a5  lea     r8, [rsp+470h+pbstr]; unsigned __int16 **
0x1803ff8aa  xor     edx, edx; bool
0x1803ff8ac  mov     rcx, rbx; struct IUri *
0x1803ff8af  call    ?GetW3COriginFromUri@@YAJPEAUIUri@@_NPEAPEAG@Z; GetW3COriginFromUri(IUri *,bool,ushort * *)
0x1803ff8b4  mov     r14, [rsp+470h+pbstr]
0x1803ff8b9  mov     edi, eax
0x1803ff8bb  test    eax, eax
0x1803ff8bd  jnz     loc_1803FF9AD
0x1803ff8c3  mov     rax, [rbx]
0x1803ff8c6  lea     rdx, [rsp+470h+var_428]
0x1803ff8cb  mov     rcx, rbx
0x1803ff8ce  mov     dword ptr [rsp+470h+var_428], r13d
0x1803ff8d3  mov     dword ptr [rsp+470h+var_420], r13d
0x1803ff8d8  mov     rax, [rax+0C0h]
0x1803ff8df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803ff8e4  test    eax, eax
0x1803ff8e6  js      loc_1803FF9A8
0x1803ff8ec  mov     rcx, [rsp+470h+ppURI]
0x1803ff8f1  lea     rdx, [rsp+470h+var_420]
0x1803ff8f6  mov     rax, [rcx]
0x1803ff8f9  mov     rax, [rax+0C0h]
0x1803ff900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803ff905  test    eax, eax
0x1803ff907  js      loc_1803FF9A8
0x1803ff90d  mov     eax, dword ptr [rsp+470h+var_420]
0x1803ff911  cmp     eax, 2
0x1803ff914  jz      short loc_1803FF91F
0x1803ff916  cmp     eax, 0Bh
0x1803ff919  jnz     loc_1803FF9A8
0x1803ff91f  cmp     dword ptr [rsp+470h+var_428], 0Bh
0x1803ff924  jnz     short loc_1803FF92B
0x1803ff926  cmp     eax, 0Bh
0x1803ff929  jnz     short loc_1803FF9A8
0x1803ff92b  test    [rsi+0B4h], r12d
0x1803ff932  jnz     short loc_1803FF9AD
0x1803ff934  mov     rcx, [rsp+470h+ppURI]; struct IUri *
0x1803ff939  lea     r8, [rsp+470h+pbstr]; unsigned __int16 **
0x1803ff93e  xor     edx, edx; bool
0x1803ff940  mov     [rsp+470h+pbstr], r13
0x1803ff945  call    ?GetW3COriginFromUri@@YAJPEAUIUri@@_NPEAPEAG@Z; GetW3COriginFromUri(IUri *,bool,ushort * *)
0x1803ff94a  mov     edi, eax
0x1803ff94c  test    eax, eax
0x1803ff94e  jnz     short loc_1803FF9AD
0x1803ff950  mov     r12, [rsp+470h+pbstr]
0x1803ff955  mov     rcx, r12; pbstr
0x1803ff958  call    cs:__imp_SysStringLen
0x1803ff95f  nop     dword ptr [rax+rax+00h]
0x1803ff964  mov     rcx, r14; pbstr
0x1803ff967  mov     ebx, eax
0x1803ff969  call    cs:__imp_SysStringLen
0x1803ff970  nop     dword ptr [rax+rax+00h]
0x1803ff975  cmp     eax, ebx
0x1803ff977  jnz     short loc_1803FF98F
0x1803ff979  mov     rdx, r12; psz2
0x1803ff97c  mov     rcx, r14; psz1
0x1803ff97f  call    cs:__imp_StrCmpW
0x1803ff986  nop     dword ptr [rax+rax+00h]
0x1803ff98b  test    eax, eax
0x1803ff98d  jz      short loc_1803FF997
0x1803ff98f  bts     dword ptr [rsi+0B4h], 9
0x1803ff997  mov     rcx, r12; bstrString
0x1803ff99a  call    cs:__imp_SysFreeString
0x1803ff9a1  nop     dword ptr [rax+rax+00h]
0x1803ff9a6  jmp     short loc_1803FF9AD
0x1803ff9a8  mov     edi, 80070005h
0x1803ff9ad  mov     rcx, r14; bstrString
0x1803ff9b0  call    cs:__imp_SysFreeString
0x1803ff9b7  nop     dword ptr [rax+rax+00h]
0x1803ff9bc  test    edi, edi
0x1803ff9be  jnz     loc_1803FF5E2
0x1803ff9c4  mov     rdx, [rsp+470h+ppURI]; struct IUri *
0x1803ff9c9  mov     rcx, rsi; this
0x1803ff9cc  call    ?SetRedirectUri@CDwnBindData@@QEAAJPEAUIUri@@@Z; CDwnBindData::SetRedirectUri(IUri *)
0x1803ff9d1  mov     edi, eax
0x1803ff9d3  test    eax, eax
0x1803ff9d5  jnz     loc_1803FF5E2
0x1803ff9db  mov     rdx, [r15]; String2
0x1803ff9de  test    rdx, rdx
0x1803ff9e1  jz      short loc_1803FF9F7
0x1803ff9e3  lea     rcx, aPost; "POST"
0x1803ff9ea  call    wcscmp_0
0x1803ff9ef  test    eax, eax
0x1803ff9f1  jz      loc_1803FFBA4
0x1803ff9f7  xor     edx, edx; struct CDwnPost *
0x1803ff9f9  mov     rcx, rsi; this
0x1803ff9fc  call    ?SetDwnPost@CDwnBindInfo@@QEAAXPEAVCDwnPost@@@Z; CDwnBindInfo::SetDwnPost(CDwnPost *)
0x1803ffa01  mov     rcx, [rsi+120h]
0x1803ffa08  test    rcx, rcx
0x1803ffa0b  jz      loc_1803FFBA4
0x1803ffa11  mov     [rsp+470h+pbstr], r13
0x1803ffa16  lea     r8, [rsp+470h+pbstr]
  ... truncated ...
```
