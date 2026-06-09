# CDwnBindData::SignalRedirect(ushort const *,IUnknown *)

- ea: `0x18064c5c0`
- end: `0x18064d020`
- name: `?SignalRedirect@CDwnBindData@@AEAAXPEBGPEAUIUnknown@@@Z`
- size: `2656`
- prototype: `void __fastcall(CDwnBindData *__hidden this, LPCWSTR pwzURI, struct IUnknown *)`
- caller_count: `2`
- callee_count: `43`
- tags: `service_task, broker_com_uri`

## callers

- `0x1804e58d0`
- `0x1804e63b0`

## callees

- `0x1800148b0`
- `0x1800cfb54`
- `0x1800d44a0`
- `0x1800e2b08`
- `0x180154a54`
- `0x1801af6e0`
- `0x1801b0510`
- `0x1801bf344`
- `0x1801c0acc`
- `0x1801cd5ac`
- `0x1802fe254`
- `0x1802fe388`
- `0x1803a5d34`
- `0x18043c328`
- `0x180492440`
- `0x1804dcbe4`
- `0x1804de5ec`
- `0x1804e1130`
- `0x1804e1cd8`
- `0x1804e3010`
- `0x1804e4004`
- `0x1804e62d0`
- `0x1804fa5e0`
- `0x18061dde8`
- `0x18062947c`
- `0x18064c5c0`
- `0x18064d028`
- `0x18064d0bc`
- `0x18065e49c`
- `0x1806622b8`
- `0x1806809d4`
- `0x1806d3d30`
- `0x18074a720`
- `0x1807b40e4`
- `0x1807c495c`
- `0x1807dcad8`
- `0x1808585a0`
- `0x18096ee24`
- `0x1810c2c92`
- `0x1810c2cb6`
- `0x1810c2d2e`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18064cf60`
- `KERNEL32!LeaveCriticalSection` at `0x18064cf8f`
- `KERNEL32!LeaveCriticalSection` at `0x18064cf60`
- `KERNEL32!LeaveCriticalSection` at `0x18064cf8f`
- `KERNEL32!EnterCriticalSection` at `0x18064cf46`
- `KERNEL32!EnterCriticalSection` at `0x18064cf46`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x18064ca00`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x18064ca00`
- `iertutil!CreateUri` at `0x18064c6f5`
- `iertutil!CreateUri` at `0x18064c6f5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18064ce80`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18064ce80`
- `urlmon!__imp_MapUriToBrowserEmulationState` at `0x18064cd56`
- `urlmon!__imp_MapUriToBrowserEmulationState` at `0x18064cd56`
- `urlmon!__imp_MapBrowserEmulationStateToUserAgent` at `0x18064ce4f`
- `urlmon!__imp_MapBrowserEmulationStateToUserAgent` at `0x18064ce4f`
- `OLEAUT32!__imp_SysFreeString` at `0x18064ca15`
- `OLEAUT32!__imp_SysFreeString` at `0x18064ca25`
- `OLEAUT32!__imp_SysFreeString` at `0x18064ca15`
- `OLEAUT32!__imp_SysFreeString` at `0x18064ca25`
- `OLEAUT32!__imp_SysStringLen` at `0x18064c9e5`
- `OLEAUT32!__imp_SysStringLen` at `0x18064c9f0`
- `OLEAUT32!__imp_SysStringLen` at `0x18064c9e5`
- `OLEAUT32!__imp_SysStringLen` at `0x18064c9f0`

## pseudocode

```c
void __fastcall CDwnBindData::SignalRedirect(CDwnBindData *this, LPCWSTR pwzURI, struct IUnknown *a3)
{
  bool v3; // zf
  __int64 v7; // rax
  struct CDoc *v8; // rcx
  HRESULT W3COriginFromUri; // edi
  __int64 v10; // rcx
  const wchar_t **v11; // r15
  __int64 v12; // rdx
  struct IUnknownVtbl *lpVtbl; // rcx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v15; // edx
  HRESULT (__stdcall *v16)(IUnknown *, const IID *const, void **); // rbx
  __int64 v17; // rax
  struct IUri *v18; // rbx
  OLECHAR *v19; // r14
  HRESULT v20; // eax
  struct IUri v21; // rax
  WCHAR *v22; // r12
  UINT v23; // ebx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // r14
  __int64 v27; // r14
  __int64 v28; // r15
  _OWORD *v29; // rax
  _OWORD *v30; // rcx
  __int64 v31; // rdx
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  unsigned int *v40; // r14
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int64 v43; // rax
  unsigned int v44; // ebx
  unsigned int v45; // edi
  BSTR v46; // rbx
  char *v47; // rax
  _OWORD *v48; // rcx
  __int128 v49; // xmm1
  CMarkup *v50; // rcx
  __int64 v51; // rax
  __int64 v52; // rcx
  CMarkup *v53; // rcx
  struct IUnknown *v54; // r10
  __int64 v55; // rcx
  CMSPerformanceData *v56; // rbx
  struct IInternetSecurityManager *v57; // r12
  struct IUri *v58; // r15
  struct IUri *v59; // r13
  BSTR pbstr; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v61; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int8 v62[8]; // [rsp+50h] [rbp-B0h] BYREF
  IUri *ppURI; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v64; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v65; // [rsp+68h] [rbp-98h] BYREF
  int v66; // [rsp+70h] [rbp-90h] BYREF
  CMSPerformanceData *v67; // [rsp+78h] [rbp-88h] BYREF
  _BYTE Buf2[448]; // [rsp+80h] [rbp-80h] BYREF
  char Buf1[448]; // [rsp+240h] [rbp+140h] BYREF
  char v70[16]; // [rsp+400h] [rbp+300h] BYREF
  unsigned __int16 v71[16]; // [rsp+410h] [rbp+310h] BYREF

  v66 = 16;
  v3 = (*((_BYTE *)this + 180) & 1) == 0;
  ppURI = 0;
  v65 = 0;
  v67 = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 96) = 0;
  if ( !v3 )
  {
    v7 = *((_QWORD *)this + 10);
    if ( v7 )
    {
      v8 = *(struct CDoc **)(v7 + 104);
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
  v11 = (const wchar_t **)((char *)this + 528);
  CStr::_Free((CDwnBindData *)((char *)this + 528));
  v12 = v65;
  *((_QWORD *)this + 66) = 0;
  lpVtbl = a3->lpVtbl;
  v65 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( !((unsigned int (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
          a3,
          &IID_IWinInetHttpInfo,
          &v65)
    && v65
    && !(*(unsigned int (__fastcall **)(__int64, __int64, char *, int *, _QWORD, _QWORD))(*(_QWORD *)v65 + 32LL))(
          v65,
          45,
          v70,
          &v66,
          0,
          0)
    && v66 )
  {
    AnsiToWideTrivial(v70, v71, 0x10u, v66);
    W3COriginFromUri = CStr::Set((CDwnBindData *)((char *)this + 528), v71);
    if ( W3COriginFromUri )
      goto LABEL_6;
    if ( !wcscmp_0(L"POST", *v11) )
    {
      LODWORD(v61) = 0;
      LODWORD(v64) = 4;
      if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, struct IUnknown **, _QWORD, _QWORD))(*(_QWORD *)v65 + 32LL))(
              v65,
              536870931,
              &v61,
              &v64,
              0,
              0)
        && (_DWORD)v64
        && (unsigned int)(v61 - 307) > 1 )
      {
        *(_DWORD *)v62 = 0;
        pbstr = 0;
        if ( (_DWORD)v61 != 301
          || (v16 = a3->lpVtbl->QueryInterface,
              v17 = TSmartPointer<ID3D11Device>::operator&(&pbstr),
              ((int (__fastcall *)(struct IUnknown *, GUID *, __int64))v16)(
                a3,
                &GUID_f3d8f080_a5eb_476f_9d19_a5ef24e5c2e6,
                v17) < 0)
          || (*(int (__fastcall **)(BSTR, unsigned __int8 *))(*(_QWORD *)pbstr + 120LL))(pbstr, v62) < 0
          || !*(_DWORD *)v62 )
        {
          W3COriginFromUri = CStr::Set((CDwnBindData *)((char *)this + 528), L"GET");
          if ( W3COriginFromUri )
          {
            TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&pbstr);
            goto LABEL_6;
          }
        }
        TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&pbstr);
      }
    }
  }
  *((_DWORD *)this + 183) = IsUriSecure(ppURI, v15) != 0;
  CDwnBindData::ReportRedirectToAPFilter(this, pwzURI);
  if ( *((_DWORD *)this + 50) )
  {
    v18 = (struct IUri *)*((_QWORD *)this + 59);
    if ( v18 || (v18 = (struct IUri *)*((_QWORD *)this + 111)) != 0 )
    {
      pbstr = 0;
      v19 = 0;
      if ( (*((_DWORD *)this + 45) & 0x200) != 0
        || (v20 = GetW3COriginFromUri(v18, 0, &pbstr), v19 = pbstr, (W3COriginFromUri = v20) == 0) )
      {
        v21.lpVtbl = v18->lpVtbl;
        LODWORD(v61) = 0;
        *(_DWORD *)v62 = 0;
        if ( ((int (__fastcall *)(struct IUri *, __int64 *))v21.lpVtbl->GetScheme)(v18, &v61) >= 0
          && ((int (__fastcall *)(IUri *, unsigned __int8 *))ppURI->lpVtbl->GetScheme)(ppURI, v62) >= 0
          && (*(_DWORD *)v62 == 2 || *(_DWORD *)v62 == 11)
          && ((_DWORD)v61 != 11 || *(_DWORD *)v62 == 11) )
        {
          if ( (*((_DWORD *)this + 45) & 0x200) == 0 )
          {
            pbstr = 0;
            W3COriginFromUri = GetW3COriginFromUri(ppURI, 0, &pbstr);
            if ( !W3COriginFromUri )
            {
              v22 = pbstr;
              v23 = SysStringLen(pbstr);
              if ( SysStringLen(v19) != v23 || StrCmpW(v19, v22) )
                *((_DWORD *)this + 45) |= 0x200u;
              SysFreeString(v22);
            }
          }
        }
        else
        {
          W3COriginFromUri = -2147024891;
        }
      }
      SysFreeString(v19);
      if ( W3COriginFromUri )
        goto LABEL_6;
    }
  }
  W3COriginFromUri = CDwnBindData::SetRedirectUri(this, ppURI);
  if ( W3COriginFromUri )
    goto LABEL_6;
  if ( !*v11 || wcscmp_0(L"POST", *v11) )
  {
    CDwnBindInfo::SetDwnPost(this, 0);
    v24 = *((_QWORD *)this + 36);
    if ( v24 )
    {
      pbstr = 0;
      (*(void (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v24 + 80LL))(
        v24,
        L"__HTMLLOADOPTIONSNAV",
        &pbstr);
      if ( pbstr )
      {
        v64 = 0;
        (**(void (__fastcall ***)(BSTR, GUID *, struct IUnknown **))pbstr)(pbstr, &IID_IHtmlLoadOptions, &v64);
        if ( v64 )
        {
          v61 = 0;
          *(_DWORD *)v62 = 8;
          W3COriginFromUri = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 *, unsigned __int8 *))v64->lpVtbl[1].QueryInterface)(
                               v64,
                               7,
                               &v61,
                               v62);
          if ( W3COriginFromUri || *(_DWORD *)v62 != 8 )
            v61 = 0x10000;
          else
            v61 |= 0x10000uLL;
          ((void (__fastcall *)(struct IUnknown *, __int64, __int64 *, __int64))v64->lpVtbl[1].AddRef)(v64, 7, &v61, 8);
          ReleaseInterface(v64);
        }
        ReleaseInterface((struct IUnknown *)pbstr);
      }
      else
      {
        v25 = MemoryProtection::HeapAllocClear<1>(g_hProcessHeap, 64);
        v26 = v25;
        if ( v25 )
        {
          *(_QWORD *)(v25 + 8) = 0;
          *(_QWORD *)v25 = &CBaseFT::`vftable';
          *(_DWORD *)(v25 + 16) = 1;
          *(_DWORD *)(v25 + 20) = 1;
          _InterlockedAdd(&g_lSecondaryObjCount, 1u);
          *(_QWORD *)v25 = &COptionArray::`vftable'{for `CBaseFT'};
          *(_QWORD *)(v25 + 24) = &COptionArray::`vftable'{for `IOptionArray'};
          *(_OWORD *)(v25 + 32) = 0;
          *(GUID *)(v25 + 48) = IID_IHtmlLoadOptions;
        }
        else
        {
          v26 = 0;
        }
        *(_QWORD *)v62 = 0x10000;
        COptionArray::SetOption((COptionArray *)(v26 + 24), 7u, v62, 8u);
        W3COriginFromUri = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 36) + 72LL))(
                             *((_QWORD *)this + 36),
                             L"__HTMLLOADOPTIONSNAV",
                             (v26 + 24) & -(__int64)(v26 != 0));
        CBaseFT::Release((CBaseFT *)v26);
      }
    }
  }
  if ( *((char *)this + 419) < 0 )
  {
    v27 = *((_QWORD *)this + 10);
    if ( v27 )
    {
      v28 = 3;
      v29 = (_OWORD *)(v27 + 196);
      v30 = Buf2;
      v31 = 3;
      do
      {
        v32 = v29[1];
        *v30 = *v29;
        v33 = v29[2];
        v30[1] = v32;
        v34 = v29[3];
        v30[2] = v33;
        v35 = v29[4];
        v30[3] = v34;
        v36 = v29[5];
        v30[4] = v35;
        v37 = v29[6];
        v30[5] = v36;
        v38 = v29[7];
        v29 += 8;
        v30[6] = v37;
        v30[7] = v38;
        v30 += 8;
        --v31;
      }
      while ( v31 );
      v39 = *v29;
      v40 = *(unsigned int **)(v27 + 104);
      pbstr = 0;
      v41 = v29[1];
      *v30 = v39;
      v42 = v29[2];
      v43 = *((_QWORD *)v29 + 6);
      v30[1] = v41;
      v30[2] = v42;
      *((_QWORD *)v30 + 6) = v43;
      if ( v40 )
      {
        if ( (int)CDoc::EnsureSecurityManager((CDoc *)v40, (struct IInternetSecurityManagerEx2 **)&pbstr, 0) >= 0 )
        {
          v44 = (unsigned __int8)IsWebPlatformHostBehaviorSupported<35>(v40[1260], v40[1261], v40[1263], v40[1262]);
          v45 = v44 | 4;
          if ( !CDXDependentSurfacePresenterFlip::IsIndependent((CDXDependentSurfacePresenterFlip *)v40[1260]) )
            v45 = v44;
          memset_0(Buf1, 0, 0x1B8u);
          v46 = pbstr;
          W3COriginFromUri = MapUriToBrowserEmulationState(pbstr, ppURI, v45, Buf1, 0);
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v46 + 16LL))(v46);
          if ( W3COriginFromUri )
            goto LABEL_6;
          MapWebPlatformVersionToEmulationMode(
            (const struct CDoc *)v40,
            (struct __MIDL___MIDL_itf_browsermode_0000_0000_0011 *)Buf1);
          if ( memcmp_0(Buf1, Buf2, 0x1B8u) )
          {
            v47 = Buf1;
            v48 = (_OWORD *)(*((_QWORD *)this + 10) + 196LL);
            do
            {
              *v48 = *(_OWORD *)v47;
              v48[1] = *((_OWORD *)v47 + 1);
              v48[2] = *((_OWORD *)v47 + 2);
              v48[3] = *((_OWORD *)v47 + 3);
              v48[4] = *((_OWORD *)v47 + 4);
              v48[5] = *((_OWORD *)v47 + 5);
              v48[6] = *((_OWORD *)v47 + 6);
              v49 = *((_OWORD *)v47 + 7);
              v47 += 128;
              v48[7] = v49;
              v48 += 8;
              --v28;
            }
            while ( v28 );
            *v48 = *(_OWORD *)v47;
            v48[1] = *((_OWORD *)v47 + 1);
            v48[2] = *((_OWORD *)v47 + 2);
            *((_QWORD *)v48 + 6) = *((_QWORD *)v47 + 6);
            v50 = *(CMarkup **)(*((_QWORD *)this + 10) + 112LL);
            if ( v50 )
              CMarkup::SetMobileEmulationState(v50, (struct __MIDL___MIDL_itf_browsermode_0000_0000_0011 *)Buf1);
            if ( (Buf1[4] & 0x40) == 0 )
            {
              pbstr = 0;
              W3COriginFromUri = MapBrowserEmulationStateToUserAgent(Buf1, &pbstr);
              if ( W3COriginFromUri )
                goto LABEL_6;
              W3COriginFromUri = CDwnDoc::SetString((struct CStr *)(*((_QWORD *)this + 10) + 704LL), pbstr);
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
    v51 = *((_QWORD *)this + 10);
    if ( v51 )
    {
      v52 = *(_QWORD *)(v51 + 104);
      if ( v52 )
      {
        if ( *(_QWORD *)(v52 + 64) )
        {
          v53 = *(CMarkup **)(v51 + 112);
          if ( v53 )
          {
            if ( (*((_DWORD *)v53 + 188) & 0x100000) != 0 && (unsigned int)CMarkup::IsPrimaryMarkup(v53) )
              CTExec(v54, &CGID_ShellDocView, 0x8Au, 0, 0, 0);
          }
        }
      }
    }
    v55 = *((_QWORD *)this + 10);
    if ( v55 && (unsigned __int8)CDwnDoc::GetPerfData(v55, &v67) )
    {
      v56 = v67;
      CMSPerformanceData::Redirected(v67);
      AddRefSharedSecurityManager();
      v57 = s_pISM;
      if ( s_pISM )
      {
        v58 = ppURI;
        v59 = (struct IUri *)*((_QWORD *)this + 111);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v56 + 48));
        if ( *((_BYTE *)v56 + 24) )
        {
          if ( !CMSPerformanceData::CheckSameOrigin(v59, v58, v57) )
          {
            *((_BYTE *)v56 + 24) = 0;
            CMSPerformanceData::SetNavigationUri(v56, v58);
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v56 + 48));
        }
        else
        {
          CMSPerformanceData::SetNavigationUri(v56, v58);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v56 + 48));
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
  CDwnBindData::SetSiteUri(this, ppURI);
LABEL_7:
  ReleaseInterface((struct IUnknown *)ppURI);
  TSmartPointer<CMSPerformanceData>::~TSmartPointer<CMSPerformanceData>(&v67);
  v10 = v65;
  v65 = 0;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
}

```

## disassembly

```asm
0x18064c5c0  mov     [rsp-8+arg_18], rbx
0x18064c5c5  push    rbp
0x18064c5c6  push    rsi
0x18064c5c7  push    rdi
0x18064c5c8  push    r12
0x18064c5ca  push    r13
0x18064c5cc  push    r14
0x18064c5ce  push    r15
0x18064c5d0  lea     rbp, [rsp-340h]
0x18064c5d8  sub     rsp, 440h
0x18064c5df  mov     rax, cs:__security_cookie
0x18064c5e6  xor     rax, rsp
0x18064c5e9  mov     [rbp+370h+var_40], rax
0x18064c5f0  xor     r13d, r13d
0x18064c5f3  mov     [rsp+470h+var_400], 10h
0x18064c5fb  test    byte ptr [rcx+0B4h], 1
0x18064c602  mov     r14, r8
0x18064c605  mov     r12, rdx
0x18064c608  mov     [rsp+470h+ppURI], r13
0x18064c60d  mov     rsi, rcx
0x18064c610  mov     [rsp+470h+var_408], r13
0x18064c615  mov     [rsp+470h+var_3F8], r13
0x18064c61a  mov     [rcx+1C8h], r13
0x18064c621  mov     [rcx+300h], r13
0x18064c628  jz      loc_18064C6E5
0x18064c62e  mov     rax, [rcx+50h]
0x18064c632  test    rax, rax
0x18064c635  jz      loc_18064C6E5
0x18064c63b  mov     rcx, [rax+68h]; struct CDoc *
0x18064c63f  test    rcx, rcx
0x18064c642  jz      loc_18064C6E5
0x18064c648  call    ?IsSecurityErrorPage@@YAHPEAVCDoc@@PEBG@Z; IsSecurityErrorPage(CDoc *,ushort const *)
0x18064c64d  test    eax, eax
0x18064c64f  jz      loc_18064C6E5
0x18064c655  mov     rcx, [rsi+50h]
0x18064c659  lea     r9d, [r13+2]; unsigned int
0x18064c65d  mov     [rsp+470h+var_448], r13; struct tagVARIANT *
0x18064c662  lea     rdx, CGID_MSHTML; struct _GUID *
0x18064c669  mov     r8d, 85Ah; unsigned int
0x18064c66f  mov     [rsp+470h+var_450], r13; struct tagVARIANT *
0x18064c674  mov     rcx, [rcx+68h]; this
0x18064c678  call    ?Exec@CDoc@@UEAAJPEBU_GUID@@KKPEAUtagVARIANT@@1@Z; CDoc::Exec(_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x18064c67d  mov     edi, 800C0014h
0x18064c682  mov     edx, edi; int
0x18064c684  mov     rcx, rsi; this
0x18064c687  call    ?SignalDone@CDwnBindData@@AEAAXJ@Z; CDwnBindData::SignalDone(long)
0x18064c68c  mov     rcx, [rsp+470h+ppURI]; struct IUnknown *
0x18064c691  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x18064c696  lea     rcx, [rsp+470h+var_3F8]
0x18064c69b  call    ??1?$TSmartPointer@VCMSPerformanceData@@@@QEAA@XZ; TSmartPointer<CMSPerformanceData>::~TSmartPointer<CMSPerformanceData>(void)
0x18064c6a0  mov     rcx, [rsp+470h+var_408]
0x18064c6a5  mov     [rsp+470h+var_408], r13
0x18064c6aa  test    rcx, rcx
0x18064c6ad  jz      short loc_18064C6BB
0x18064c6af  mov     rax, [rcx]
0x18064c6b2  mov     rax, [rax+10h]
0x18064c6b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18064c6bb  mov     rcx, [rbp+370h+var_40]
0x18064c6c2  xor     rcx, rsp; StackCookie
0x18064c6c5  call    __security_check_cookie
0x18064c6ca  mov     rbx, [rsp+470h+arg_18]
0x18064c6d2  add     rsp, 440h
0x18064c6d9  pop     r15
0x18064c6db  pop     r14
0x18064c6dd  pop     r13
0x18064c6df  pop     r12
0x18064c6e1  pop     rdi
0x18064c6e2  pop     rsi
0x18064c6e3  pop     rbp
0x18064c6e4  retn
0x18064c6e5  lea     r9, [rsp+470h+ppURI]; ppURI
0x18064c6ea  xor     r8d, r8d; dwReserved
0x18064c6ed  mov     edx, 3002B84h; dwFlags
0x18064c6f2  mov     rcx, r12; pwzURI
0x18064c6f5  call    cs:__imp_CreateUri
0x18064c6fb  mov     edi, eax
0x18064c6fd  test    eax, eax
0x18064c6ff  jnz     short loc_18064C682
0x18064c701  lea     r15, [rsi+210h]
0x18064c708  mov     rcx, r15; this
0x18064c70b  call    ?_Free@CStr@@AEAAXXZ; CStr::_Free(void)
0x18064c710  mov     rdx, [rsp+470h+var_408]
0x18064c715  mov     [r15], r13
0x18064c718  mov     rcx, [r14]
0x18064c71b  mov     [rsp+470h+var_408], r13
0x18064c720  mov     rbx, [rcx]
0x18064c723  test    rdx, rdx
0x18064c726  jz      short loc_18064C737
0x18064c728  mov     rcx, [rdx]
0x18064c72b  mov     rax, [rcx+10h]
0x18064c72f  mov     rcx, rdx
0x18064c732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18064c737  lea     r8, [rsp+470h+var_408]
0x18064c73c  mov     rcx, r14
0x18064c73f  lea     rdx, IID_IWinInetHttpInfo
0x18064c746  mov     rax, rbx
0x18064c749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18064c74e  test    eax, eax
0x18064c750  jnz     loc_18064C8CF
0x18064c756  mov     rcx, [rsp+470h+var_408]
0x18064c75b  test    rcx, rcx
0x18064c75e  jz      loc_18064C8CF
0x18064c764  mov     rax, [rcx]
0x18064c767  lea     r9, [rsp+470h+var_400]
0x18064c76c  mov     [rsp+470h+var_448], r13
0x18064c771  lea     r8, [rbp+370h+var_70]
0x18064c778  mov     edx, 2Dh ; '-'
0x18064c77d  mov     [rsp+470h+var_450], r13
0x18064c782  mov     rax, [rax+20h]
0x18064c786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18064c78b  test    eax, eax
0x18064c78d  jnz     loc_18064C8CF
0x18064c793  mov     r9d, [rsp+470h+var_400]; int
0x18064c798  test    r9d, r9d
0x18064c79b  jz      loc_18064C8CF
0x18064c7a1  lea     r8d, [rax+10h]; unsigned __int64
0x18064c7a5  lea     rdx, [rbp+370h+var_60]; unsigned __int16 *
0x18064c7ac  lea     rcx, [rbp+370h+var_70]; char *
0x18064c7b3  call    ?AnsiToWideTrivial@@YAXPEBDPEAG_KJ@Z; AnsiToWideTrivial(char const *,ushort *,unsigned __int64,long)
0x18064c7b8  lea     rdx, [rbp+370h+var_60]; unsigned __int16 *
0x18064c7bf  mov     rcx, r15; this
0x18064c7c2  call    ?Set@CStr@@QEAAJPEBG@Z; CStr::Set(ushort const *)
0x18064c7c7  mov     edi, eax
0x18064c7c9  test    eax, eax
0x18064c7cb  jnz     loc_18064C682
0x18064c7d1  mov     rdx, [r15]; String2
0x18064c7d4  lea     rcx, aPost; "POST"
0x18064c7db  call    wcscmp_0
0x18064c7e0  test    eax, eax
0x18064c7e2  jnz     loc_18064C8CF
0x18064c7e8  mov     rcx, [rsp+470h+var_408]
0x18064c7ed  lea     r9, [rsp+470h+var_410]
0x18064c7f2  mov     dword ptr [rsp+470h+var_428], r13d
0x18064c7f7  lea     r8, [rsp+470h+var_428]
0x18064c7fc  mov     dword ptr [rsp+470h+var_410], 4
0x18064c804  mov     edx, 20000013h
0x18064c809  mov     [rsp+470h+var_448], r13
0x18064c80e  mov     rax, [rcx]
0x18064c811  mov     [rsp+470h+var_450], r13
0x18064c816  mov     rax, [rax+20h]
0x18064c81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18064c81f  test    eax, eax
0x18064c821  jnz     loc_18064C8CF
0x18064c827  cmp     dword ptr [rsp+470h+var_410], r13d
0x18064c82c  jz      loc_18064C8CF
0x18064c832  mov     ecx, dword ptr [rsp+470h+var_428]
0x18064c836  lea     eax, [rcx-133h]
0x18064c83c  cmp     eax, 1
0x18064c83f  jbe     loc_18064C8CF
0x18064c845  mov     dword ptr [rsp+470h+var_420], r13d
0x18064c84a  mov     [rsp+470h+pbstr], r13
0x18064c84f  cmp     ecx, 12Dh
0x18064c855  jnz     short loc_18064C8A1
0x18064c857  mov     rax, [r14]
0x18064c85a  lea     rcx, [rsp+470h+pbstr]
0x18064c85f  mov     rbx, [rax]
0x18064c862  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x18064c867  mov     r8, rax
0x18064c86a  lea     rdx, _GUID_f3d8f080_a5eb_476f_9d19_a5ef24e5c2e6
0x18064c871  mov     rax, rbx
0x18064c874  mov     rcx, r14
0x18064c877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18064c87c  test    eax, eax
0x18064c87e  js      short loc_18064C8A1
0x18064c880  mov     rcx, [rsp+470h+pbstr]
0x18064c885  lea     rdx, [rsp+470h+var_420]
0x18064c88a  mov     rax, [rcx]
0x18064c88d  mov     rax, [rax+78h]
0x18064c891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18064c896  test    eax, eax
0x18064c898  js      short loc_18064C8A1
0x18064c89a  cmp     dword ptr [rsp+470h+var_420], r13d
0x18064c89f  jnz     short loc_18064C8C5
0x18064c8a1  lea     rdx, szVerb; "GET"
0x18064c8a8  mov     rcx, r15; this
0x18064c8ab  call    ?Set@CStr@@QEAAJPEBG@Z; CStr::Set(ushort const *)
0x18064c8b0  mov     edi, eax
0x18064c8b2  test    eax, eax
0x18064c8b4  jz      short loc_18064C8C5
0x18064c8b6  lea     rcx, [rsp+470h+pbstr]; void *
0x18064c8bb  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x18064c8c0  jmp     loc_18064C682
0x18064c8c5  lea     rcx, [rsp+470h+pbstr]; void *
0x18064c8ca  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x18064c8cf  mov     rcx, [rsp+470h+ppURI]; struct IUri *
0x18064c8d4  call    ?IsUriSecure@@YAHPEAUIUri@@H@Z; IsUriSecure(IUri *,int)
0x18064c8d9  mov     ecx, r13d
0x18064c8dc  test    eax, eax
0x18064c8de  mov     rdx, r12; unsigned __int16 *
0x18064c8e1  setnz   cl
0x18064c8e4  mov     [rsi+2DCh], ecx
0x18064c8ea  mov     rcx, rsi; this
0x18064c8ed  call    ?ReportRedirectToAPFilter@CDwnBindData@@QEAAXPEBG@Z; CDwnBindData::ReportRedirectToAPFilter(ushort const *)
0x18064c8f2  test    edi, edi
0x18064c8f4  jnz     loc_18064C682
0x18064c8fa  cmp     [rsi+0C8h], r13d
0x18064c901  jz      loc_18064CA33
0x18064c907  mov     rbx, [rsi+1D8h]
0x18064c90e  test    rbx, rbx
0x18064c911  jnz     short loc_18064C923
0x18064c913  mov     rbx, [rsi+378h]
0x18064c91a  test    rbx, rbx
0x18064c91d  jz      loc_18064CA33
0x18064c923  mov     r12d, 200h
0x18064c929  mov     [rsp+470h+pbstr], r13
0x18064c92e  mov     r14, r13
0x18064c931  test    [rsi+0B4h], r12d
0x18064c938  jnz     short loc_18064C958
0x18064c93a  lea     r8, [rsp+470h+pbstr]; unsigned __int16 **
0x18064c93f  xor     edx, edx; bool
0x18064c941  mov     rcx, rbx; struct IUri *
0x18064c944  call    ?GetW3COriginFromUri@@YAJPEAUIUri@@_NPEAPEAG@Z; GetW3COriginFromUri(IUri *,bool,ushort * *)
0x18064c949  mov     r14, [rsp+470h+pbstr]
0x18064c94e  mov     edi, eax
0x18064c950  test    eax, eax
0x18064c952  jnz     loc_18064CA22
0x18064c958  mov     rax, [rbx]
0x18064c95b  lea     rdx, [rsp+470h+var_428]
0x18064c960  mov     rcx, rbx
0x18064c963  mov     dword ptr [rsp+470h+var_428], r13d
0x18064c968  mov     dword ptr [rsp+470h+var_420], r13d
0x18064c96d  mov     rax, [rax+0C0h]
0x18064c974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18064c979  test    eax, eax
0x18064c97b  js      loc_18064CA1D
0x18064c981  mov     rcx, [rsp+470h+ppURI]
0x18064c986  lea     rdx, [rsp+470h+var_420]
0x18064c98b  mov     rax, [rcx]
0x18064c98e  mov     rax, [rax+0C0h]
0x18064c995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18064c99a  test    eax, eax
0x18064c99c  js      short loc_18064CA1D
0x18064c99e  mov     eax, dword ptr [rsp+470h+var_420]
0x18064c9a2  cmp     eax, 2
0x18064c9a5  jz      short loc_18064C9AC
0x18064c9a7  cmp     eax, 0Bh
0x18064c9aa  jnz     short loc_18064CA1D
0x18064c9ac  cmp     dword ptr [rsp+470h+var_428], 0Bh
0x18064c9b1  jnz     short loc_18064C9B8
0x18064c9b3  cmp     eax, 0Bh
0x18064c9b6  jnz     short loc_18064CA1D
0x18064c9b8  test    [rsi+0B4h], r12d
0x18064c9bf  jnz     short loc_18064CA22
0x18064c9c1  mov     rcx, [rsp+470h+ppURI]; struct IUri *
0x18064c9c6  lea     r8, [rsp+470h+pbstr]; unsigned __int16 **
0x18064c9cb  xor     edx, edx; bool
0x18064c9cd  mov     [rsp+470h+pbstr], r13
0x18064c9d2  call    ?GetW3COriginFromUri@@YAJPEAUIUri@@_NPEAPEAG@Z; GetW3COriginFromUri(IUri *,bool,ushort * *)
0x18064c9d7  mov     edi, eax
0x18064c9d9  test    eax, eax
0x18064c9db  jnz     short loc_18064CA22
0x18064c9dd  mov     r12, [rsp+470h+pbstr]
0x18064c9e2  mov     rcx, r12; pbstr
0x18064c9e5  call    cs:__imp_SysStringLen
0x18064c9eb  mov     rcx, r14; pbstr
0x18064c9ee  mov     ebx, eax
0x18064c9f0  call    cs:__imp_SysStringLen
0x18064c9f6  cmp     eax, ebx
0x18064c9f8  jnz     short loc_18064CA0A
0x18064c9fa  mov     rdx, r12; psz2
0x18064c9fd  mov     rcx, r14; psz1
0x18064ca00  call    cs:__imp_StrCmpW
0x18064ca06  test    eax, eax
0x18064ca08  jz      short loc_18064CA12
0x18064ca0a  bts     dword ptr [rsi+0B4h], 9
0x18064ca12  mov     rcx, r12; bstrString
0x18064ca15  call    cs:__imp_SysFreeString
0x18064ca1b  jmp     short loc_18064CA22
0x18064ca1d  mov     edi, 80070005h
0x18064ca22  mov     rcx, r14; bstrString
0x18064ca25  call    cs:__imp_SysFreeString
0x18064ca2b  test    edi, edi
0x18064ca2d  jnz     loc_18064C682
0x18064ca33  mov     rdx, [rsp+470h+ppURI]; struct IUri *
0x18064ca38  mov     rcx, rsi; this
0x18064ca3b  call    ?SetRedirectUri@CDwnBindData@@QEAAJPEAUIUri@@@Z; CDwnBindData::SetRedirectUri(IUri *)
0x18064ca40  mov     edi, eax
0x18064ca42  test    eax, eax
0x18064ca44  jnz     loc_18064C682
0x18064ca4a  mov     rdx, [r15]; String2
0x18064ca4d  test    rdx, rdx
0x18064ca50  jz      short loc_18064CA66
0x18064ca52  lea     rcx, aPost; "POST"
0x18064ca59  call    wcscmp_0
0x18064ca5e  test    eax, eax
0x18064ca60  jz      loc_18064CC13
0x18064ca66  xor     edx, edx; struct CDwnPost *
0x18064ca68  mov     rcx, rsi; this
0x18064ca6b  call    ?SetDwnPost@CDwnBindInfo@@QEAAXPEAVCDwnPost@@@Z; CDwnBindInfo::SetDwnPost(CDwnPost *)
0x18064ca70  mov     rcx, [rsi+120h]
0x18064ca77  test    rcx, rcx
0x18064ca7a  jz      loc_18064CC13
0x18064ca80  mov     [rsp+470h+pbstr], r13
0x18064ca85  lea     r8, [rsp+470h+pbstr]
0x18064ca8a  mov     rax, [rcx]
0x18064ca8d  lea     rdx, aHtmlloadoption_1; "__HTMLLOADOPTIONSNAV"
0x18064ca94  mov     rax, [rax+50h]
0x18064ca98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18064ca9d  mov     rcx, [rsp+470h+pbstr]
0x18064caa2  test    rcx, rcx
  ... truncated ...
```
