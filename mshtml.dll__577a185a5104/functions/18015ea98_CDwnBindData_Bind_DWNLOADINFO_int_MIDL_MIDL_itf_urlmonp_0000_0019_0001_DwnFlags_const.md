# CDwnBindData::Bind(DWNLOADINFO *,int,__MIDL___MIDL_itf_urlmonp_0000_0019_0001,DwnFlags const &)

- ea: `0x18015ea98`
- end: `0x18016032f`
- name: `?Bind@CDwnBindData@@QEAAXPEAUDWNLOADINFO@@HW4__MIDL___MIDL_itf_urlmonp_0000_0019_0001@@AEBUDwnFlags@@@Z`
- size: `6295`
- prototype: `void __fastcall(__int64, __int64, int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `54`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18015e204`

## callees

- `0x18005ce98`
- `0x18005d080`
- `0x18005e648`
- `0x18005e684`
- `0x18006b2e8`
- `0x18006b354`
- `0x1800ea428`
- `0x1801086ac`
- `0x18015b784`
- `0x18015d260`
- `0x18015daec`
- `0x18015ea98`
- `0x180160338`
- `0x1801604c8`
- `0x180160620`
- `0x180160818`
- `0x180160f84`
- `0x1801613e8`
- `0x18028e55c`
- `0x18028ead4`
- `0x1802d6a54`
- `0x1803cb43c`
- `0x1803ddae0`
- `0x1803e41f0`
- `0x1803e864c`
- `0x180400d3c`
- `0x180400e88`
- `0x1804134dc`
- `0x1804143c4`
- `0x180429e94`
- `0x18058aadc`
- `0x1805db320`
- `0x1805f7b94`
- `0x18061a494`
- `0x180640a24`
- `0x180649810`
- `0x18067bb7c`
- `0x18069bd20`
- `0x1806b2820`
- `0x1806b28d4`
- `0x1806b2910`
- `0x1806c9320`
- `0x1806ea7d4`
- `0x1806edde4`
- `0x1806fba7c`
- `0x18072d530`
- `0x1807734a0`
- `0x18077bf7c`
- `0x180783f84`
- `0x18079d2c0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18015ee25`
- `KERNEL32!LeaveCriticalSection` at `0x18015eead`
- `KERNEL32!LeaveCriticalSection` at `0x18015f4ae`
- `KERNEL32!LeaveCriticalSection` at `0x18015f4d4`
- `KERNEL32!LeaveCriticalSection` at `0x18015f535`
- `KERNEL32!LeaveCriticalSection` at `0x18015ee25`
- `KERNEL32!LeaveCriticalSection` at `0x18015eead`
- `KERNEL32!LeaveCriticalSection` at `0x18015f4ae`
- `KERNEL32!LeaveCriticalSection` at `0x18015f4d4`
- `KERNEL32!LeaveCriticalSection` at `0x18015f535`
- `KERNEL32!EnterCriticalSection` at `0x18015edff`
- `KERNEL32!EnterCriticalSection` at `0x18015ee8d`
- `KERNEL32!EnterCriticalSection` at `0x18015f482`
- `KERNEL32!EnterCriticalSection` at `0x18015f4f5`
- `KERNEL32!EnterCriticalSection` at `0x18015edff`
- `KERNEL32!EnterCriticalSection` at `0x18015ee8d`
- `KERNEL32!EnterCriticalSection` at `0x18015f482`
- `KERNEL32!EnterCriticalSection` at `0x18015f4f5`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18015ecdb`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18015ecdb`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18016017a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18016017a`
- `iertutil!CreateUri` at `0x18015f2cd`
- `iertutil!CreateUri` at `0x18015f2cd`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18015eeea`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18015eeea`
- `ole32!CreateBindCtx` at `0x18015fbbb`
- `ole32!CreateBindCtx` at `0x18015fbbb`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18015eb4b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18015eb4b`
- `urlmon!CoInternetCreateSecurityManager` at `0x18015f127`
- `urlmon!CoInternetCreateSecurityManager` at `0x18015f127`
- `urlmon!IsAsyncMoniker` at `0x18015f650`
- `urlmon!IsAsyncMoniker` at `0x18015f650`
- `urlmon!CreateURLMonikerEx2` at `0x18015fb96`
- `urlmon!CreateURLMonikerEx2` at `0x18015fb96`
- `urlmon!CoInternetParseIUri` at `0x18015fd15`
- `urlmon!CoInternetParseIUri` at `0x18015fd15`
- `urlmon!RestrictHTTP2` at `0x18015f7f9`
- `urlmon!RestrictHTTP2` at `0x18015f7f9`
- `urlmon!__imp_IERegisterDefaultAcceptHeaders` at `0x18015fbf2`
- `urlmon!__imp_IERegisterDefaultAcceptHeaders` at `0x18015fbf2`
- `urlmon!__imp_RegisterAcceptHeaderCategory` at `0x18015fa53`
- `urlmon!__imp_RegisterAcceptHeaderCategory` at `0x18015fa53`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18015f6aa`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18015f6aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18015f6ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180160081`
- `OLEAUT32!__imp_SysFreeString` at `0x18016010a`
- `OLEAUT32!__imp_SysFreeString` at `0x1801602fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180160316`
- `OLEAUT32!__imp_SysFreeString` at `0x18015f6ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180160081`
- `OLEAUT32!__imp_SysFreeString` at `0x18016010a`
- `OLEAUT32!__imp_SysFreeString` at `0x1801602fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180160316`
- `OLEAUT32!__imp_SysStringLen` at `0x1801600cf`
- `OLEAUT32!__imp_SysStringLen` at `0x180160149`
- `OLEAUT32!__imp_SysStringLen` at `0x1801600cf`
- `OLEAUT32!__imp_SysStringLen` at `0x180160149`

## pseudocode

```c
void __fastcall CDwnBindData::Bind(__int64 a1, __int64 a2, int a3, unsigned int a4, __int64 a5)
{
  int v5; // r15d
  __int64 v7; // rcx
  __int64 v9; // rax
  CMarkup *v10; // r12
  bool v11; // zf
  int (__fastcall ***v12)(__int64, GUID *, volatile signed __int32 **); // rbx
  int UriFromMoniker; // esi
  BOOL v14; // r14d
  BOOL v15; // r15d
  int (__fastcall **v16)(__int64, GUID *, volatile signed __int32 **); // rax
  _QWORD *v17; // rsi
  const unsigned __int16 *v18; // rbx
  __int64 v19; // rax
  unsigned int v20; // r15d
  __int64 v21; // rax
  unsigned __int16 *v22; // r14
  int v23; // eax
  void *v24; // r8
  __int64 v25; // rcx
  int v26; // eax
  char v27; // bl
  __int64 v28; // rbx
  __int64 v29; // rbx
  int v30; // eax
  volatile signed __int32 *v31; // rbx
  char v32; // al
  int v33; // edx
  int v34; // eax
  __int64 v35; // rbx
  __int64 v36; // rcx
  __int64 v37; // rbx
  int v38; // r14d
  int *v39; // rcx
  BOOL v40; // ebx
  __int64 v41; // rcx
  BOOL v42; // ebx
  __int64 v43; // rcx
  CMarkup *v44; // rax
  bool v45; // bl
  CMarkup *v46; // rax
  __int64 v47; // rax
  int v48; // edx
  bool v49; // r14
  bool v50; // si
  CFilterSecurityManagerDelegate *v51; // rax
  CFilterSecurityManagerDelegate *v52; // rax
  CFilterSecurityManagerDelegate *v53; // rbx
  const WCHAR *OriginUrl; // rax
  IUri *v55; // rbx
  __int64 v56; // rbx
  int v57; // r14d
  __int64 v58; // r15
  int v59; // r12d
  OLECHAR *v60; // rcx
  __int64 v61; // rcx
  CUString *v62; // r12
  struct _RTL_CRITICAL_SECTION *v63; // r14
  __int64 v64; // rbx
  __int64 v65; // rsi
  __int64 v66; // r14
  int started; // eax
  int v68; // ebx
  IUri *v69; // rdx
  struct IMoniker *v70; // r8
  struct IUri *v71; // rdx
  OLECHAR *v72; // rsi
  int v73; // r14d
  volatile signed __int32 *v74; // rax
  int v75; // edx
  unsigned int *v76; // rax
  unsigned __int8 v77; // al
  _DWORD *v78; // rbx
  int v79; // edx
  __int64 v80; // rcx
  int v81; // eax
  unsigned int v82; // r14d
  BOOL v83; // eax
  __int64 v84; // rcx
  bool v85; // al
  unsigned int v86; // eax
  int v87; // edx
  struct IMoniker *v88; // r12
  struct IBindCtx *v89; // r14
  __int64 v90; // rcx
  CMarkup *v91; // rbx
  CMarkup *v92; // rcx
  __int64 v93; // rcx
  CDoc *v94; // rcx
  int v95; // eax
  unsigned int v96; // r9d
  int v97; // eax
  struct CDoc *v98; // rax
  CBindContextParam *v99; // rax
  CBindContextParam *v100; // r15
  __int64 v101; // rcx
  struct IBindHost *v102; // rbx
  void *v103; // r8
  DWORD v104; // r8d
  LPCWSTR *v105; // rbx
  unsigned int *v106; // rax
  unsigned int *v107; // rbx
  bool v108; // al
  int v109; // eax
  CStr *v110; // rcx
  void *v111; // r8
  void *v112; // r8
  struct CTimeManager *TimeManager; // rsi
  CMSPerformanceData *v114; // rax
  CMSPerformanceData *v115; // rax
  const unsigned __int16 *Url; // rax
  OLECHAR **v117; // r12
  OLECHAR *v118; // rcx
  int v119; // eax
  unsigned int cchResult; // [rsp+20h] [rbp-E0h]
  char v121; // [rsp+60h] [rbp-A0h]
  IUri *pUri; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcchResult[2]; // [rsp+70h] [rbp-90h] BYREF
  struct IBindHost *v124; // [rsp+78h] [rbp-88h] BYREF
  volatile signed __int32 *v125; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v126; // [rsp+88h] [rbp-78h]
  int v127; // [rsp+8Ch] [rbp-74h]
  int v128; // [rsp+90h] [rbp-70h] BYREF
  struct IInternetSecurityManager *v129; // [rsp+98h] [rbp-68h]
  void **v130; // [rsp+A0h] [rbp-60h] BYREF
  int (__fastcall ***v131)(__int64, GUID *, volatile signed __int32 **); // [rsp+A8h] [rbp-58h]
  unsigned int v132; // [rsp+B0h] [rbp-50h]
  LPCWSTR pcszURL[2]; // [rsp+B8h] [rbp-48h] BYREF
  UINT ui; // [rsp+C8h] [rbp-38h] BYREF
  struct IInternetSecurityManager *v135; // [rsp+D0h] [rbp-30h] BYREF
  CMarkup *v136; // [rsp+D8h] [rbp-28h]
  IInternetSecurityManager *ppSM; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v138; // [rsp+E8h] [rbp-18h]
  LPBC ppbc; // [rsp+F0h] [rbp-10h] BYREF
  LPMONIKER ppmk; // [rsp+F8h] [rbp-8h] BYREF
  IUri *ppURI; // [rsp+100h] [rbp+0h] BYREF
  void **v142; // [rsp+108h] [rbp+8h] BYREF
  __int64 v143; // [rsp+110h] [rbp+10h]
  int v144; // [rsp+118h] [rbp+18h]
  BSTR bstrString[2]; // [rsp+120h] [rbp+20h]
  int v146; // [rsp+130h] [rbp+30h]
  PARSEDURLW ppu; // [rsp+138h] [rbp+38h] BYREF
  WCHAR pwzResult[264]; // [rsp+160h] [rbp+60h] BYREF

  v5 = 0;
  v126 = a4;
  v127 = a3;
  v7 = *(_QWORD *)(a2 + 8);
  ppmk = 0;
  ppbc = 0;
  v138 = v7;
  if ( v7 )
  {
    v9 = v7;
    v124 = *(struct IBindHost **)(v7 + 120);
  }
  else
  {
    v9 = *(_QWORD *)(a1 + 80);
    v124 = 0;
  }
  v136 = *(CMarkup **)(v9 + 112);
  v10 = v136;
  v144 = 11;
  v132 = 11;
  ppURI = 0;
  pUri = 0;
  v142 = &CUString::`vftable';
  v143 = 0;
  *(_OWORD *)bstrString = 0;
  v146 = 0;
  v130 = &CUString::`vftable';
  v131 = 0;
  *(_OWORD *)pcszURL = 0;
  ui = 0;
  v128 = 0;
  v129 = 0;
  *(_OWORD *)(a1 + 1080) = *(_OWORD *)GlobalThreadState();
  *(_BYTE *)(a1 + 819) = (*(_BYTE *)(a5 + 4) & 2) != 0;
  if ( !v10 )
    goto LABEL_4;
  v129 = 0;
  ppSM = 0;
  UriFromMoniker = CoInternetCreateSecurityManager(0, &ppSM, 0);
  if ( !UriFromMoniker && ppSM )
  {
    v135 = 0;
    UriFromMoniker = ((__int64 (__fastcall *)(IInternetSecurityManager *, GUID *, struct IInternetSecurityManager **))ppSM->lpVtbl->QueryInterface)(
                       ppSM,
                       &GUID_f1e50292_a795_4117_8e09_2b560a72ac60,
                       &v135);
    if ( UriFromMoniker )
    {
LABEL_136:
      ((void (__fastcall *)(IInternetSecurityManager *))ppSM->lpVtbl->Release)(ppSM);
      goto LABEL_137;
    }
    v43 = *((_QWORD *)v10 + 18);
    v44 = v10;
    v45 = 0;
    if ( v43 )
      v44 = (CMarkup *)*((_QWORD *)v10 + 18);
    if ( (*((_DWORD *)v44 + 187) & 0x4000000) != 0 )
    {
      if ( (*((_DWORD *)v10 + 187) & 0x8000000) == 0 )
      {
        v46 = v10;
        if ( v43 )
          v46 = (CMarkup *)*((_QWORD *)v10 + 18);
        if ( (*((_DWORD *)v46 + 187) & 0x4000000) != 0 )
          v47 = *((_QWORD *)v46 + 44);
        else
          v47 = 0;
        goto LABEL_124;
      }
    }
    else if ( (*((_DWORD *)v10 + 187) & 0x8000000) == 0 )
    {
LABEL_126:
      v48 = *((_DWORD *)v10 + 189);
      if ( (*((_BYTE *)v10 + 97) & 2) != 0 || (v49 = 0, (v48 & 0x10001) != 0 || (*((_BYTE *)v10 + 752) & 0x40) != 0) )
        v49 = 1;
      if ( (v48 & 0x100) == 0 || (v50 = 0, (v48 & 0x800) != 0) )
        v50 = 1;
      v51 = (CFilterSecurityManagerDelegate *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 32);
      if ( v51
        && (v52 = CFilterSecurityManagerDelegate::CFilterSecurityManagerDelegate(v51, v50, v49, v45), (v53 = v52) != 0) )
      {
        UriFromMoniker = ((__int64 (__fastcall *)(struct IInternetSecurityManager *, __int64))v135->lpVtbl->SetSecuritySite)(
                           v135,
                           (__int64)v52 + 8);
        if ( !UriFromMoniker )
        {
          ((void (__fastcall *)(struct IInternetSecurityManager *))v135->lpVtbl->AddRef)(v135);
          v129 = v135;
        }
        CFilterSecurityManagerDelegate::Release(v53);
      }
      else
      {
        UriFromMoniker = -2147024882;
      }
      ((void (__fastcall *)(struct IInternetSecurityManager *))v135->lpVtbl->Release)(v135);
      goto LABEL_136;
    }
    v47 = *((_QWORD *)v10 + 44);
LABEL_124:
    if ( v47 )
      v45 = (*(_BYTE *)(*(_QWORD *)(v47 + 120) + 224LL) & 0x40) != 0;
    goto LABEL_126;
  }
LABEL_137:
  if ( UriFromMoniker < 0 )
    goto LABEL_81;
  OriginUrl = CMarkup::GetOriginUrl(v10);
  if ( CreateUri(OriginUrl, 0x3002B80u, 0, &ppURI) < 0 )
    goto LABEL_81;
  v55 = ppURI;
  if ( *(_QWORD *)(a1 + 832) )
  {
    CUString::Set((CUString *)(a1 + 840), 0, Uri_PROPERTY_ABSOLUTE_URI);
    ReleaseInterface(*(struct IUnknown **)(a1 + 832));
  }
  *(_QWORD *)(a1 + 832) = v55;
  if ( v55 )
  {
    ((void (__fastcall *)(IUri *))v55->lpVtbl->AddRef)(v55);
    v56 = *(_QWORD *)(a1 + 832);
    v57 = 0;
    v58 = *(_QWORD *)(a1 + 848);
    v59 = *(_DWORD *)(a1 + 856);
    if ( v56 != v58 || v59 )
    {
      v60 = *(OLECHAR **)(a1 + 864);
      if ( v60 )
      {
        SysFreeString(v60);
        *(_QWORD *)(a1 + 864) = 0;
      }
      *(_QWORD *)(a1 + 872) = 0;
      *(_DWORD *)(a1 + 880) = 0;
      if ( v56 != v58 )
      {
        v61 = *(_QWORD *)(a1 + 848);
        if ( v61 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
          *(_QWORD *)(a1 + 848) = 0;
        }
      }
    }
    *(_DWORD *)(a1 + 856) = 0;
    if ( v56 && (v59 || v56 != v58) )
    {
      *(_QWORD *)pcchResult = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, DWORD *))v56)(
             v56,
             &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
             pcchResult) < 0 )
      {
        v117 = (OLECHAR **)(a1 + 864);
        v57 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v56 + 24LL))(
                v56,
                *(unsigned int *)(a1 + 856),
                a1 + 864,
                0);
        if ( v57 >= 0 )
        {
          v118 = *v117;
          *(_QWORD *)(a1 + 872) = *v117;
          *(_DWORD *)(a1 + 880) = SysStringLen(v118);
        }
        v62 = (CUString *)(a1 + 840);
      }
      else
      {
        v62 = (CUString *)(a1 + 840);
        v57 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**(_QWORD **)pcchResult + 224LL))(
                *(_QWORD *)pcchResult,
                *(unsigned int *)(a1 + 856),
                a1 + 872,
                a1 + 880);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcchResult + 16LL))(*(_QWORD *)pcchResult);
      }
      if ( v56 != v58 && v57 >= 0 )
      {
        *(_QWORD *)(a1 + 848) = v56;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 8LL))(v56);
      }
      if ( v57 == 1 )
        v57 = CUString::Set(v62, *(struct IUri **)(a1 + 832), Uri_PROPERTY_RAW_URI);
    }
    v5 = 0;
    if ( v57 < 0 )
      goto LABEL_81;
    v10 = v136;
  }
LABEL_4:
  v11 = g_EnableSyncAsyncErrorHandling == 0;
  *(_DWORD *)(a1 + 176) = v126;
  if ( !v11 )
  {
    *(_WORD *)(a1 + 822) = 0;
    *(_BYTE *)(a1 + 824) = 0;
    *(_DWORD *)(a1 + 828) = 0;
  }
  v12 = *(int (__fastcall ****)(__int64, GUID *, volatile signed __int32 **))(a2 + 32);
  UriFromMoniker = 0;
  v14 = v12 != v131;
  LOBYTE(v5) = v132 != 0;
  if ( v12 != v131 || v5 )
  {
    if ( pcszURL[0] )
    {
      SysFreeString((BSTR)pcszURL[0]);
      pcszURL[0] = 0;
    }
    pcszURL[1] = 0;
    ui = 0;
    if ( v14 && v131 )
    {
      ((void (__fastcall *)(int (__fastcall ***)(__int64, GUID *, volatile signed __int32 **)))(*v131)[2])(v131);
      v131 = 0;
    }
  }
  v132 = 0;
  if ( !v12 )
  {
    v15 = 0;
    goto LABEL_22;
  }
  if ( v5 )
  {
    v15 = 0;
  }
  else
  {
    v15 = 0;
    if ( !v14 )
      goto LABEL_22;
  }
  v16 = *v12;
  v125 = 0;
  if ( (*v16)((__int64)v12, &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60, &v125) < 0 )
  {
    UriFromMoniker = ((__int64 (__fastcall *)(int (__fastcall ***)(__int64, GUID *, volatile signed __int32 **), _QWORD, LPCWSTR *, _QWORD))(*v12)[3])(
                       v12,
                       v132,
                       pcszURL,
                       0);
    if ( UriFromMoniker >= 0 )
    {
      pcszURL[1] = pcszURL[0];
      ui = SysStringLen((BSTR)pcszURL[0]);
    }
  }
  else
  {
    UriFromMoniker = (*(__int64 (__fastcall **)(volatile signed __int32 *, _QWORD, LPCWSTR *, UINT *))(*(_QWORD *)v125 + 224LL))(
                       v125,
                       v132,
                       &pcszURL[1],
                       &ui);
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v125 + 16LL))(v125);
  }
  if ( v14 && UriFromMoniker >= 0 )
  {
    v131 = v12;
    ((void (__fastcall *)(int (__fastcall ***)(__int64, GUID *, volatile signed __int32 **)))(*v12)[1])(v12);
  }
  if ( UriFromMoniker == 1 )
    UriFromMoniker = CUString::Set((CUString *)&v130, *(struct IUri **)(a2 + 32), Uri_PROPERTY_RAW_URI);
LABEL_22:
  if ( UriFromMoniker )
    goto LABEL_81;
  v17 = (_QWORD *)a5;
  if ( *(char *)(a5 + 3) >= 0 )
  {
    v18 = pcszURL[1];
    memset(&ppu, 0, sizeof(ppu));
    if ( pcszURL[1] )
    {
      ppu.cbSize = 40;
      if ( ParseURLW(pcszURL[1], &ppu) >= 0 && ppu.nScheme == 9 )
      {
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        v20 = v19 + 1;
        if ( (int)v19 + 1 < (unsigned int)v19 )
          goto LABEL_30;
        v21 = 2LL * v20;
        if ( !is_mul_ok(v20, 2u) )
          v21 = -1;
        v22 = (unsigned __int16 *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v21);
        if ( v22 )
        {
          UriFromMoniker = 0;
          v23 = IsFloppy(v18, v22, v20);
          v15 = 0;
          if ( v23 )
          {
            if ( PathFileExistsW(v22) )
            {
              _InterlockedExchange(&dword_1815C4B98, 0);
            }
            else
            {
              UriFromMoniker = -2147024891;
              if ( _InterlockedIncrement(&dword_1815C4B98) <= dword_1815B54B0 )
                UriFromMoniker = 0;
            }
          }
          MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v22, v24);
          if ( UriFromMoniker < 0 )
            goto LABEL_81;
          v17 = (_QWORD *)a5;
        }
        else
        {
LABEL_30:
          v15 = 0;
        }
      }
    }
  }
  v25 = v138;
  *(_QWORD *)(a1 + 416) = *v17;
  if ( v25 )
  {
    *(_DWORD *)(a1 + 416) |= *(_DWORD *)(v25 + 168);
    *(_DWORD *)(a1 + 420) |= *(_DWORD *)(v25 + 172);
  }
  v26 = *(_DWORD *)(a1 + 180);
  if ( (*(_BYTE *)(a1 + 418) & 0x20) != 0 )
  {
    v26 |= 1u;
    *(_DWORD *)(a1 + 180) = v26;
  }
  if ( *(char *)(a1 + 419) < 0 )
    *(_DWORD *)(a1 + 180) = v26 | 4;
  if ( (Microsoft_IEEnableBits & 2) != 0 )
  {
    McTemplateU0qz_EventWriteTransfer(v25, MSHTML_CDWNBINDDATA_BIND_START, *(unsigned int *)(a1 + 416), pcszURL[1]);
    v25 = v138;
  }
  v27 = *(_BYTE *)(a1 + 418);
  v121 = v27;
  if ( (*(_BYTE *)(a1 + 180) & 1) != 0 && (v27 & 0x40) == 0 && !*(_DWORD *)(a2 + 104) )
  {
    v28 = v25;
    if ( !v25 )
      v28 = *(_QWORD *)(a1 + 80);
    EnterCriticalSection(&g_csDwnDoc);
    if ( !*(_QWORD *)(v28 + 104) )
      goto LABEL_52;
    v29 = *(_QWORD *)(v28 + 112);
    if ( !v29 )
      goto LABEL_52;
    v63 = (struct _RTL_CRITICAL_SECTION *)(v29 + 632);
    EnterCriticalSection((LPCRITICAL_SECTION)(v29 + 632));
    if ( !*(_QWORD *)(v29 + 616) )
    {
      TimeManager = CMarkup::GetTimeManager((CMarkup *)v29);
      if ( TimeManager )
      {
        v114 = (CMSPerformanceData *)MemoryProtection::HeapAllocClear<1>(g_hProcessHeap, 208);
        if ( v114 )
          v115 = CMSPerformanceData::CMSPerformanceData(v114, TimeManager);
        else
          v115 = 0;
        *(_QWORD *)(v29 + 616) = v115;
      }
    }
    v64 = *(_QWORD *)(v29 + 616);
    if ( v64 )
      _InterlockedIncrement((volatile signed __int32 *)(v64 + 8));
    LeaveCriticalSection(v63);
    if ( v64 )
    {
      LeaveCriticalSection(&g_csDwnDoc);
      CMSPerformanceData::Mark(v64, 5);
      v65 = *(_QWORD *)(a2 + 32);
      EnterCriticalSection((LPCRITICAL_SECTION)(v64 + 48));
      v66 = *(_QWORD *)(v64 + 40);
      *(_QWORD *)(v64 + 40) = v65;
      if ( v65 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 8LL))(v65);
      if ( v66 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v64 + 48));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v64 + 8), 0xFFFFFFFF) == 1 )
      {
        CMSPerformanceData::~CMSPerformanceData((CMSPerformanceData *)v64);
        MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, (void *)v64, v111);
      }
      v15 = 0;
    }
    else
    {
LABEL_52:
      LeaveCriticalSection(&g_csDwnDoc);
    }
    v27 = v121;
  }
  if ( ((*(_BYTE *)(a1 + 417) & 0x40) == 0
     || !(unsigned int)CDataProtocol::IsUriHandledByDataProt(*(struct IUri **)(a2 + 32)))
    && !*(_DWORD *)(a2 + 104) )
  {
    if ( v10 )
    {
      v30 = *(_DWORD *)(a1 + 180);
      if ( (v30 & 4) == 0 && !*(_QWORD *)(a1 + 1072) && !*(_DWORD *)(a1 + 1068) )
      {
        if ( (v30 & 1) != 0 )
        {
          if ( (v27 & 0x40) != 0 )
            goto LABEL_69;
          v125 = 0;
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v10 + 632));
          v31 = (volatile signed __int32 *)*((_QWORD *)v10 + 78);
          if ( v31 )
            _InterlockedIncrement(v31 + 2);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v10 + 632));
          v32 = v31 != 0;
        }
        else
        {
          v125 = 0;
          v32 = CMarkup::AcquirePerfData(v10);
          v31 = v125;
        }
        if ( v32 )
        {
          if ( ui )
          {
            v72 = SysAllocStringLen(pcszURL[1], ui);
            if ( v72 )
            {
              v73 = CMSPerformanceData::ConvertDownloadInitiatorToResourceInitiator(*(unsigned int *)(a2 + 144));
              AddRefSharedSecurityManager();
              if ( s_pISM )
              {
                if ( (v75 = *(_DWORD *)(a2 + 144), v75 == 88) && (*((_DWORD *)v10 + 34) & 0x400LL) == 0
                  || v73 != 6
                  || v75 == 82 )
                {
                  *(_QWORD *)(a1 + 1064) = *(_QWORD *)CMSPerformanceData::StartResource(
                                                        (__int64)v31,
                                                        &v125,
                                                        v72,
                                                        v73,
                                                        *(struct IUri **)(a2 + 32),
                                                        s_pISM,
                                                        0);
                }
              }
              DecrementSharedSecurityManager();
              SysFreeString(v72);
              if ( *(_DWORD *)(a1 + 1068) )
              {
                v74 = v31;
                v31 = 0;
                *(_QWORD *)(a1 + 1072) = v74;
              }
            }
          }
        }
        if ( v31 && _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
        {
          CMSPerformanceData::~CMSPerformanceData((CMSPerformanceData *)v31);
          MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, (void *)v31, v112);
        }
      }
    }
  }
LABEL_69:
  CDwnBindData::ResetPrivacyInfo((CDwnBindData *)a1);
  if ( (unsigned __int8)IEConfiguration_GetBool(536870925) )
  {
    v76 = (unsigned int *)CMarkup::Doc(v10);
    if ( v76 )
    {
      v77 = IsWebPlatformHostBehaviorSupported<85>(v76[1260], v76[1261], v76[1263], v76[1262]);
      RestrictHTTP2(v77);
    }
  }
  if ( *(_QWORD *)(a2 + 40) )
  {
    if ( *(_DWORD *)(a2 + 76) || (v11 = (unsigned int)IsUriSecure(*(struct IUri **)(a2 + 32), v33) == 0, v34 = 1, v11) )
      v34 = 0;
    *(_DWORD *)(a1 + 732) = v34;
    UriFromMoniker = CDwnBindData::SetBindOnApt((CDwnBindData *)a1);
    if ( !UriFromMoniker )
    {
      v35 = *(_QWORD *)(a2 + 40);
      if ( v35 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v35 + 8LL))(*(_QWORD *)(a2 + 40));
      v36 = *(_QWORD *)(a1 + 328);
      *(_QWORD *)(a1 + 328) = v35;
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      *(_BYTE *)(a1 + 251) = 0;
      CDwnBindData::SignalData((CDwnBindData *)a1);
      UriFromMoniker = 0;
      v37 = *(_QWORD *)(a2 + 32);
      if ( *(_QWORD *)(a1 + 888) )
      {
        CUString::Set((CUString *)(a1 + 896), 0, Uri_PROPERTY_ABSOLUTE_URI);
        ReleaseInterface(*(struct IUnknown **)(a1 + 888));
      }
      *(_QWORD *)(a1 + 888) = v37;
      if ( v37 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
        UriFromMoniker = CUString::Set((CUString *)(a1 + 896), *(struct IUri **)(a1 + 888), Uri_PROPERTY_ABSOLUTE_URI);
        if ( UriFromMoniker == 1 )
        {
          started = CUString::Set((CUString *)(a1 + 896), *(struct IUri **)(a1 + 888), Uri_PROPERTY_RAW_URI);
LABEL_272:
          UriFromMoniker = started;
          goto LABEL_81;
        }
      }
    }
    goto LABEL_81;
  }
  if ( *(_DWORD *)(a2 + 68) || !*(_QWORD *)(a2 + 48) && !*(_QWORD *)(a2 + 32) )
  {
    if ( *(_DWORD *)(a2 + 76) || (v11 = (unsigned int)IsUriSecure(*(struct IUri **)(a2 + 32), v33) == 0, v109 = 1, v11) )
      v109 = 0;
    *(_DWORD *)(a1 + 732) = v109;
LABEL_269:
    UriFromMoniker = 0;
    goto LABEL_81;
  }
  v69 = *(IUri **)(a2 + 32);
  pUri = v69;
  if ( v69 )
  {
    ((void (__fastcall *)(IUri *))v69->lpVtbl->AddRef)(v69);
    v71 = pUri;
  }
  else
  {
    if ( !IsAsyncMoniker(*(IMoniker **)(a2 + 48)) )
    {
      UriFromMoniker = GetUriFromMoniker(*(struct IMoniker **)(a2 + 48), 0, v70, 5u, cchResult, &pUri);
      if ( UriFromMoniker )
        goto LABEL_81;
    }
    v71 = pUri;
  }
  UriFromMoniker = CDwnBindData::SetSiteUri((CDwnBindData *)a1, v71);
  if ( !UriFromMoniker )
  {
    v78 = (_DWORD *)(a1 + 752);
    if ( ((unsigned int (__fastcall *)(IUri *, __int64))pUri->lpVtbl->GetScheme)(pUri, a1 + 752) )
      *v78 = 0;
    if ( !*v78 )
    {
      if ( v10 )
      {
        v106 = (unsigned int *)CMarkup::Doc(v10);
        v107 = v106;
        if ( v106 )
        {
          if ( (unsigned __int8)IsWebPlatformHostBehaviorSupported<35>(v106[1260], v106[1261], v106[1263], v106[1262])
            || (unsigned __int8)IsWebPlatformHostBehaviorSupported<12>(v107[1260], v107[1261], v107[1263], v107[1262]) )
          {
            v108 = IsWWAHostScheme(pUri);
            v15 = v108;
            if ( !v108 && *(_DWORD *)(a1 + 176) == 4 )
              v15 = IsUriHandledByBlobProtocol(pUri);
          }
        }
      }
    }
    v80 = *(_QWORD *)(a2 + 48);
    if ( v80 )
    {
      pcchResult[0] = 0;
      if ( (*(unsigned int (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v80 + 176LL))(v80, pcchResult)
        || pcchResult[0] != 6 )
      {
        *(_DWORD *)(a1 + 752) = 0;
      }
    }
    if ( (*(_BYTE *)(a1 + 417) & 0x40) != 0 && (unsigned int)CDataProtocol::IsUriHandledByDataProt(pUri) )
    {
      v82 = 1;
      v83 = *(_DWORD *)(a2 + 76) == 0;
    }
    else
    {
      v81 = *(_DWORD *)(a1 + 752);
      v82 = 0;
      v83 = v81 != 2
         && v81 != 9
         && !*(_DWORD *)(a2 + 76)
         && ((unsigned int)IsUriSecure(pUri, v79) || (unsigned int)UriHasNoContent(pUri));
    }
    *(_DWORD *)(a1 + 732) = v83;
    if ( *(_DWORD *)(a1 + 752) == 9 && (*(_BYTE *)(a1 + 418) & 0xC) != 0 )
    {
      pcchResult[0] = 0;
      if ( !v10 || (v104 = 0x40000, (*((_DWORD *)v10 + 189) & 4) == 0) )
        v104 = 0;
      if ( !CoInternetParseIUri(pUri, PARSE_PATH_FROM_URL, v104, pwzResult, 0x104u, pcchResult, 0) )
      {
        v105 = (LPCWSTR *)(a1 + 736);
        if ( !(unsigned int)CStr::Set((const unsigned __int16 **)(a1 + 736), pwzResult)
          && *v105
          && (*(_BYTE *)(a1 + 418) & 4) != 0 )
        {
          GetFileLastModTime(*v105, (struct _FILETIME *)(a1 + 696));
        }
      }
    }
    UriFromMoniker = CUString::Set((CUString *)&v142, pUri, Uri_PROPERTY_ABSOLUTE_URI);
    if ( !UriFromMoniker )
    {
      v85 = v138 && (v84 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 104LL)) != 0 && (*(_DWORD *)(v84 + 4328) & 0x4000000) != 0;
      if ( !pUri
        || !*(_QWORD *)(a2 + 24)
        || v124
        || *(_QWORD *)(a2 + 56)
        || (*(_BYTE *)(a1 + 180) & 1) != 0 && v85
        || ((v86 = *(_DWORD *)(a1 + 752), v86 > 0xB) || (v87 = 2564, !_bittest(&v87, v86))) && !v82 && !v15 )
      {
        if ( *(_DWORD *)(a2 + 64) )
        {
          UriFromMoniker = -2147467259;
          goto LABEL_81;
        }
        v88 = *(struct IMoniker **)(a2 + 48);
        if ( !v88 )
        {
          UriFromMoniker = CreateURLMonikerEx2(0, pUri, &ppmk, 1u);
          if ( UriFromMoniker )
            goto LABEL_81;
          v88 = ppmk;
        }
        UriFromMoniker = CDwnBindData::SetBindOnApt((CDwnBindData *)a1);
        if ( UriFromMoniker )
          goto LABEL_81;
        v89 = *(struct IBindCtx **)(a2 + 56);
        if ( v89 )
          goto LABEL_250;
        UriFromMoniker = CreateBindCtx(0, &ppbc);
        if ( UriFromMoniker )
          goto LABEL_81;
        v89 = ppbc;
        if ( ppbc )
LABEL_250:
          ((void (__fastcall *)(struct IBindCtx *))v89->lpVtbl->AddRef)(v89);
        v90 = *(_QWORD *)(a1 + 288);
        *(_QWORD *)(a1 + 288) = v89;
        if ( v90 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
        v91 = v136;
        if ( (*(_BYTE *)(a1 + 180) & 1) != 0 && v136 && *((_QWORD *)CMarkup::Doc(v136) + 641) )
        {
          v98 = CMarkup::Doc(v92);
          IERegisterDefaultAcceptHeaders(v89, *((_QWORD *)v98 + 641));
        }
        if ( (*(_BYTE *)(a1 + 419) & 0x20) != 0
          && ((unsigned int)(*(_DWORD *)(a1 + 752) - 15) <= 2 || !pUri || !*bstrString[1]) )
        {
          *(_QWORD *)pcchResult = 0;
          Url = CMarkup::GetUrl(v91);
          UriFromMoniker = CStr::Set((const unsigned __int16 **)pcchResult, Url);
          if ( UriFromMoniker )
          {
            v110 = (CStr *)pcchResult;
            goto LABEL_316;
          }
          v119 = AddBindContextParam(v89, (struct CStr *)pcchResult, 0, 0, 0);
          v110 = (CStr *)pcchResult;
          UriFromMoniker = v119;
          if ( v119 )
            goto LABEL_316;
          CStr::_Free((CStr *)pcchResult);
        }
        CTridentFilterHost::Passivate((CTridentFilterHost *)(a1 + 240));
        if ( v124 )
        {
          v97 = CTridentFilterHost::BindToBindHost(
                  (CTridentFilterHost *)(a1 + 240),
                  bstrString[1],
                  v127,
                  v88,
                  v89,
                  v124,
                  (struct DWNLOADINFO *)a2,
                  v129,
                  &v128);
          *(_BYTE *)(a1 + 822) = 1;
          UriFromMoniker = v97;
          if ( v97 < 0 )
            goto LABEL_81;
LABEL_267:
          if ( v128 )
            CDwnBindData::SignalData((CDwnBindData *)a1);
          goto LABEL_269;
        }
        v93 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 104LL);
        if ( v93 )
        {
          if ( *(_QWORD *)(v93 + 56) != v93 )
          {
            UriFromMoniker = ((__int64 (__fastcall *)(struct IBindCtx *, const wchar_t *))v89->lpVtbl->RegisterObjectParam)(
                               v89,
                               L"AGG");
            if ( UriFromMoniker < 0 )
              goto LABEL_81;
          }
        }
        v94 = *(CDoc **)(*(_QWORD *)(a1 + 80) + 104LL);
        if ( v94 )
          CDoc::GetIgnoreMimeSettings(v94);
        UriFromMoniker = RegisterAcceptHeaderCategory(v89, v126);
        if ( UriFromMoniker < 0 )
          goto LABEL_81;
        if ( !*(_DWORD *)(a2 + 108) )
        {
LABEL_265:
          v95 = CTridentFilterHost::BindToMoniker(
                  (CTridentFilterHost *)(a1 + 240),
                  bstrString[1],
                  v127,
                  v88,
                  v89,
                  (struct DWNLOADINFO *)a2,
                  v129,
                  &v128);
          *(_BYTE *)(a1 + 822) = 1;
          UriFromMoniker = v95;
          if ( v95 < 0 )
            goto LABEL_81;
          if ( v95 == 262632 && *(_BYTE *)(a1 + 807) )
            CDwnBindData::SignalDone((CDwnBindData *)a1, -2146697209);
          goto LABEL_267;
        }
        v124 = 0;
        UriFromMoniker = CStr::Set((const unsigned __int16 **)&v124, L"WillUseIntermediateCode");
        if ( UriFromMoniker >= 0 )
        {
          v99 = (CBindContextParam *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, 40);
          if ( v99 && (v100 = CBindContextParam::CBindContextParam(v99)) != 0 )
          {
            *((_DWORD *)v100 + 8) = 0;
            v101 = *((_QWORD *)v100 + 3);
            *((_QWORD *)v100 + 3) = 0;
            if ( v101 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
            v102 = v124;
            UriFromMoniker = CStr::Set((const unsigned __int16 **)v100 + 2, (const unsigned __int16 *)v124);
            if ( !UriFromMoniker )
              UriFromMoniker = ((__int64 (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, CBindContextParam *))v89->lpVtbl->RegisterObjectParam)(
                                 v89,
                                 L"WillUseIntermediateCode",
                                 v100);
            CBindContextParam::Release(v100);
            if ( UriFromMoniker >= 0 )
            {
              if ( v102 )
                MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, (char *)&v102[-1].lpVtbl + 4, v103);
              goto LABEL_265;
            }
          }
          else
          {
            UriFromMoniker = -2147024882;
          }
        }
        v110 = (CStr *)&v124;
LABEL_316:
        CStr::_Free(v110);
        goto LABEL_81;
      }
      UriFromMoniker = CTridentFilterHost::BindToInetProt(a1 + 240, bstrString[1], v82, (unsigned int)v127, a2);
      if ( !UriFromMoniker )
      {
        started = CTridentFilterHost::StartFilter((CTridentFilterHost *)(a1 + 240), bstrString[1], pUri, v96);
        goto LABEL_272;
      }
    }
  }
LABEL_81:
  if ( g_EnableSyncAsyncErrorHandling && *(int *)(a1 + 828) < 0 )
    UriFromMoniker = *(_DWORD *)(a1 + 828);
  v38 = 0;
  if ( UriFromMoniker != -2146697190 )
    v38 = UriFromMoniker;
  if ( v38 )
    CDwnBindData::SignalDone((CDwnBindData *)a1, v38);
  if ( ppbc )
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  if ( ppmk )
    ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
  if ( v129 )
    ((void (__fastcall *)(struct IInternetSecurityManager *))v129->lpVtbl->Release)(v129);
  if ( ppURI )
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
  LODWORD(v39) = (_DWORD)pUri;
  if ( pUri )
    ((void (__fastcall *)(IUri *))pUri->lpVtbl->Release)(pUri);
  if ( g_EnableSyncAsyncErrorHandling )
  {
    v68 = *(_DWORD *)(a1 + 828);
    if ( v68 < 0 || *(_BYTE *)(a1 + 823) && *(_BYTE *)(a1 + 824) != 1 )
    {
LABEL_190:
      *(_DWORD *)(a1 + 828) = v68;
      if ( v68 < 0 )
        CDwnBindData::HandleFailedNavigation((CDwnBindData *)a1, v68);
      goto LABEL_97;
    }
    if ( v38 != -2146697203 )
    {
LABEL_189:
      v68 = v38;
      goto LABEL_190;
    }
    v39 = (int *)v136;
    if ( (*(_BYTE *)(a1 + 180) & 1) != 0 )
    {
      if ( !v136 )
        goto LABEL_190;
      if ( !CMarkup::Doc(v136) )
        goto LABEL_365;
      if ( *((char *)CMarkup::Doc((CMarkup *)v39) + 4868) < 0 )
        goto LABEL_189;
    }
    if ( !v39 )
      goto LABEL_190;
LABEL_365:
    if ( v39[212] >= 90000 )
    {
      LODWORD(v39) = bstrString[1];
      if ( bstrString[1] )
      {
        if ( (unsigned int)CDataProtocol::IsUrlHandledByDataProt(bstrString[1]) )
          v68 = -2146697203;
      }
    }
    goto LABEL_190;
  }
LABEL_97:
  if ( (Microsoft_IEEnableBits & 2) != 0 )
    McTemplateU0qqqz_EventWriteTransfer(
      (_DWORD)v39,
      (unsigned int)MSHTML_CDWNBINDDATA_BIND_STOP,
      v38,
      g_EnableSyncAsyncErrorHandling,
      *(_DWORD *)(a1 + 828),
      (__int64)pcszURL[1]);
  v130 = &CUString::`vftable';
  v40 = v131 != 0;
  if ( v131 || v132 != 11 )
  {
    if ( pcszURL[0] )
    {
      SysFreeString((BSTR)pcszURL[0]);
      pcszURL[0] = 0;
    }
    pcszURL[1] = 0;
    ui = 0;
    if ( v40 && v131 )
    {
      ((void (__fastcall *)(int (__fastcall ***)(__int64, GUID *, volatile signed __int32 **)))(*v131)[2])(v131);
      v131 = 0;
    }
  }
  v41 = v143;
  v132 = 11;
  v142 = &CUString::`vftable';
  v42 = v143 != 0;
  if ( v143 || v144 != 11 )
  {
    if ( bstrString[0] )
    {
      SysFreeString(bstrString[0]);
      v41 = v143;
      bstrString[0] = 0;
    }
    bstrString[1] = 0;
    v146 = 0;
    if ( v42 )
    {
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
  }
}

```

## disassembly

```asm
0x18015ea98  push    rbp
0x18015ea9a  push    rbx
0x18015ea9b  push    rsi
0x18015ea9c  push    rdi
0x18015ea9d  push    r12
0x18015ea9f  push    r13
0x18015eaa1  push    r14
0x18015eaa3  push    r15
0x18015eaa5  lea     rbp, [rsp-288h]
0x18015eaad  sub     rsp, 388h
0x18015eab4  mov     rax, cs:__security_cookie
0x18015eabb  xor     rax, rsp
0x18015eabe  mov     [rbp+2C0h+var_50], rax
0x18015eac5  xor     r15d, r15d
0x18015eac8  mov     [rbp+2C0h+var_338], r9d
0x18015eacc  mov     rdi, rcx
0x18015eacf  mov     [rbp+2C0h+var_334], r8d
0x18015ead3  mov     rcx, [rdx+8]
0x18015ead7  mov     r13, rdx
0x18015eada  mov     [rbp+2C0h+ppmk], r15
0x18015eade  mov     [rbp+2C0h+ppbc], r15
0x18015eae2  mov     [rbp+2C0h+var_2D8], rcx
0x18015eae6  test    rcx, rcx
0x18015eae9  jz      loc_18015F7B8
0x18015eaef  mov     rbx, [rcx+78h]
0x18015eaf3  mov     rax, rcx
0x18015eaf6  mov     [rsp+3C0h+var_348], rbx
0x18015eafb  mov     r12, [rax+70h]
0x18015eaff  lea     rcx, ??_7CUString@@6B@; const CUString::`vftable'
0x18015eb06  mov     eax, 0Bh
0x18015eb0b  mov     [rbp+2C0h+var_2E8], r12
0x18015eb0f  xorps   xmm0, xmm0
0x18015eb12  mov     [rbp+2C0h+var_2A8], eax
0x18015eb15  mov     [rbp+2C0h+var_310], eax
0x18015eb18  mov     [rbp+2C0h+ppURI], r15
0x18015eb1c  mov     [rsp+3C0h+pUri], r15
0x18015eb21  mov     [rbp+2C0h+var_2B8], rcx
0x18015eb25  mov     [rbp+2C0h+var_2B0], r15
0x18015eb29  movdqu  xmmword ptr [rbp+2C0h+bstrString], xmm0
0x18015eb2e  mov     [rbp+2C0h+var_290], r15d
0x18015eb32  mov     [rbp+2C0h+var_320], rcx
0x18015eb36  mov     [rbp+2C0h+var_318], r15
0x18015eb3a  movdqu  xmmword ptr [rbp+2C0h+pcszURL], xmm0
0x18015eb3f  mov     [rbp+2C0h+ui], r15d
0x18015eb43  mov     [rbp+2C0h+var_330], r15d
0x18015eb47  mov     [rbp+2C0h+var_328], r15
0x18015eb4b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18015eb52  nop     dword ptr [rax+rax+00h]
0x18015eb57  movups  xmm0, xmmword ptr [rax]
0x18015eb5a  mov     rax, [rbp+2C0h+arg_20]
0x18015eb61  movdqu  xmmword ptr [rdi+438h], xmm0
0x18015eb69  mov     al, [rax+4]
0x18015eb6c  shr     al, 1
0x18015eb6e  and     al, 1
0x18015eb70  mov     [rdi+333h], al
0x18015eb76  test    r12, r12
0x18015eb79  jnz     loc_18015F116
0x18015eb7f  cmp     cs:?g_EnableSyncAsyncErrorHandling@@3HA, r15d; int g_EnableSyncAsyncErrorHandling
0x18015eb86  mov     eax, [rbp+2C0h+var_338]
0x18015eb89  mov     [rdi+0B0h], eax
0x18015eb8f  jz      short loc_18015EBA8
0x18015eb91  mov     word ptr [rdi+336h], 0
0x18015eb9a  mov     [rdi+338h], r15b
0x18015eba1  mov     [rdi+33Ch], r15d
0x18015eba8  mov     rbx, [r13+20h]
0x18015ebac  mov     r14d, r15d
0x18015ebaf  cmp     rbx, [rbp+2C0h+var_318]
0x18015ebb3  mov     esi, r15d
0x18015ebb6  setnz   r14b
0x18015ebba  xor     eax, eax
0x18015ebbc  cmp     [rbp+2C0h+var_310], eax
0x18015ebbf  setnz   r15b
0x18015ebc3  test    r14d, r14d
0x18015ebc6  jz      loc_18015F57E
0x18015ebcc  mov     rcx, [rbp+2C0h+pcszURL]; bstrString
0x18015ebd0  test    rcx, rcx
0x18015ebd3  jnz     loc_18016010A
0x18015ebd9  mov     [rbp+2C0h+pcszURL+8], rax
0x18015ebdd  mov     [rbp+2C0h+ui], eax
0x18015ebe0  test    r14d, r14d
0x18015ebe3  jz      short loc_18015EC00
0x18015ebe5  mov     rcx, [rbp+2C0h+var_318]
0x18015ebe9  test    rcx, rcx
0x18015ebec  jz      short loc_18015EC00
0x18015ebee  mov     rax, [rcx]
0x18015ebf1  mov     rax, [rax+10h]
0x18015ebf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ebfa  xor     eax, eax
0x18015ebfc  mov     [rbp+2C0h+var_318], rax
0x18015ec00  mov     [rbp+2C0h+var_310], eax
0x18015ec03  test    rbx, rbx
0x18015ec06  jz      loc_18015F10E
0x18015ec0c  test    r15d, r15d
0x18015ec0f  jz      loc_18015F740
0x18015ec15  xor     r15d, r15d
0x18015ec18  mov     rax, [rbx]
0x18015ec1b  lea     r8, [rbp+2C0h+var_340]
0x18015ec1f  lea     rdx, _GUID_50295b0c_6b79_4935_aed8_05d80ec86a60
0x18015ec26  mov     [rbp+2C0h+var_340], r15
0x18015ec2a  mov     rcx, rbx
0x18015ec2d  mov     rax, [rax]
0x18015ec30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ec35  mov     edx, [rbp+2C0h+var_310]
0x18015ec38  test    eax, eax
0x18015ec3a  js      loc_180160121
0x18015ec40  mov     rcx, [rbp+2C0h+var_340]
0x18015ec44  lea     r9, [rbp+2C0h+ui]
0x18015ec48  lea     r8, [rbp+2C0h+pcszURL+8]
0x18015ec4c  mov     rax, [rcx]
0x18015ec4f  mov     rax, [rax+0E0h]
0x18015ec56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ec5b  mov     rcx, [rbp+2C0h+var_340]
0x18015ec5f  mov     esi, eax
0x18015ec61  mov     rax, [rcx]
0x18015ec64  mov     rax, [rax+10h]
0x18015ec68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ec6d  test    r14d, r14d
0x18015ec70  jz      short loc_18015EC89
0x18015ec72  test    esi, esi
0x18015ec74  js      short loc_18015EC89
0x18015ec76  mov     [rbp+2C0h+var_318], rbx
0x18015ec7a  mov     rcx, rbx
0x18015ec7d  mov     rax, [rbx]
0x18015ec80  mov     rax, [rax+8]
0x18015ec84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ec89  cmp     esi, 1
0x18015ec8c  jz      loc_18016015D
0x18015ec92  test    esi, esi
0x18015ec94  jnz     loc_18015EF93
0x18015ec9a  mov     rsi, [rbp+2C0h+arg_20]
0x18015eca1  or      r14, 0FFFFFFFFFFFFFFFFh
0x18015eca5  cmp     [rsi+3], r15b
0x18015eca9  jl      loc_18015ED71
0x18015ecaf  mov     rbx, [rbp+2C0h+pcszURL+8]
0x18015ecb3  xor     eax, eax
0x18015ecb5  mov     qword ptr [rbp+2C0h+ppu.cchSuffix], rax
0x18015ecb9  xorps   xmm0, xmm0
0x18015ecbc  movups  xmmword ptr [rbp+2C0h+ppu.cbSize], xmm0
0x18015ecc0  movups  xmmword ptr [rbp+2C0h+ppu.cchProtocol], xmm0
0x18015ecc4  test    rbx, rbx
0x18015ecc7  jz      loc_18015ED71
0x18015eccd  lea     rdx, [rbp+2C0h+ppu]; ppu
0x18015ecd1  mov     [rbp+2C0h+ppu.cbSize], 28h ; '('
0x18015ecd8  mov     rcx, rbx; pcszURL
0x18015ecdb  call    cs:__imp_ParseURLW
0x18015ece2  nop     dword ptr [rax+rax+00h]
0x18015ece7  test    eax, eax
0x18015ece9  js      loc_18015ED71
0x18015ecef  cmp     [rbp+2C0h+ppu.nScheme], 9
0x18015ecf3  jnz     short loc_18015ED71
0x18015ecf5  mov     rax, r14
0x18015ecf8  inc     rax
0x18015ecfb  cmp     [rbx+rax*2], r15w
0x18015ed00  jnz     short loc_18015ECF8
0x18015ed02  lea     r15d, [rax+1]
0x18015ed06  cmp     r15d, eax
0x18015ed09  jnb     short loc_18015ED10
0x18015ed0b  xor     r15d, r15d
0x18015ed0e  jmp     short loc_18015ED71
0x18015ed10  mov     ecx, r15d
0x18015ed13  mov     eax, 2
0x18015ed18  mul     rcx
0x18015ed1b  mov     rcx, cs:g_hProcessHeap
0x18015ed22  cmovb   rax, r14
0x18015ed26  mov     rdx, rax
0x18015ed29  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x18015ed2e  mov     r14, rax
0x18015ed31  xor     eax, eax
0x18015ed33  test    r14, r14
0x18015ed36  jz      short loc_18015ED0B
0x18015ed38  mov     r8d, r15d; unsigned int
0x18015ed3b  mov     rdx, r14; unsigned __int16 *
0x18015ed3e  mov     rcx, rbx; unsigned __int16 *
0x18015ed41  mov     esi, eax
0x18015ed43  call    ?IsFloppy@@YAHPEBGPEAGI@Z; IsFloppy(ushort const *,ushort *,uint)
0x18015ed48  xor     r15d, r15d
0x18015ed4b  test    eax, eax
0x18015ed4d  jnz     loc_180160177
0x18015ed53  mov     rcx, cs:g_hProcessHeap; this
0x18015ed5a  mov     rdx, r14; void *
0x18015ed5d  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x18015ed62  test    esi, esi
0x18015ed64  js      loc_18015EF93
0x18015ed6a  mov     rsi, [rbp+2C0h+arg_20]
0x18015ed71  mov     rcx, [rbp+2C0h+var_2D8]
0x18015ed75  mov     rax, [rsi]
0x18015ed78  mov     [rdi+1A0h], rax
0x18015ed7f  test    rcx, rcx
0x18015ed82  jz      short loc_18015ED9C
0x18015ed84  mov     eax, [rcx+0A8h]
0x18015ed8a  or      [rdi+1A0h], eax
0x18015ed90  mov     eax, [rcx+0ACh]
0x18015ed96  or      [rdi+1A4h], eax
0x18015ed9c  test    byte ptr [rdi+1A2h], 20h
0x18015eda3  mov     eax, [rdi+0B4h]
0x18015eda9  jz      short loc_18015EDB4
0x18015edab  or      eax, 1
0x18015edae  mov     [rdi+0B4h], eax
0x18015edb4  cmp     [rdi+1A3h], r15b
0x18015edbb  jl      loc_18015FF22
0x18015edc1  test    byte ptr cs:Microsoft_IEEnableBits, 2
0x18015edc8  jnz     loc_1801601BB
0x18015edce  test    byte ptr [rdi+0B4h], 1
0x18015edd5  mov     bl, [rdi+1A2h]
0x18015eddb  mov     [rsp+3C0h+var_360], bl
0x18015eddf  jz      short loc_18015EE35
0x18015ede1  test    bl, 40h
0x18015ede4  jnz     short loc_18015EE35
0x18015ede6  cmp     [r13+68h], r15d
0x18015edea  jnz     short loc_18015EE35
0x18015edec  mov     rbx, rcx
0x18015edef  test    rcx, rcx
0x18015edf2  jz      loc_1801601DB
0x18015edf8  lea     rcx, ?g_csDwnDoc@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x18015edff  call    cs:__imp_EnterCriticalSection
0x18015ee06  nop     dword ptr [rax+rax+00h]
0x18015ee0b  cmp     [rbx+68h], r15
0x18015ee0f  jz      short loc_18015EE1E
0x18015ee11  mov     rbx, [rbx+70h]
0x18015ee15  test    rbx, rbx
0x18015ee18  jnz     loc_18015F478
0x18015ee1e  lea     rcx, ?g_csDwnDoc@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x18015ee25  call    cs:__imp_LeaveCriticalSection
0x18015ee2c  nop     dword ptr [rax+rax+00h]
0x18015ee31  mov     bl, [rsp+3C0h+var_360]
0x18015ee35  test    byte ptr [rdi+1A1h], 40h
0x18015ee3c  jnz     loc_18015F437
0x18015ee42  cmp     [r13+68h], r15d
0x18015ee46  jnz     loc_18015EEDD
0x18015ee4c  test    r12, r12
0x18015ee4f  jz      loc_18015EEDD
0x18015ee55  mov     eax, [rdi+0B4h]
0x18015ee5b  test    al, 4
0x18015ee5d  jnz     short loc_18015EEDD
0x18015ee5f  cmp     [rdi+430h], r15
0x18015ee66  jnz     short loc_18015EEDD
0x18015ee68  cmp     [rdi+42Ch], r15d
0x18015ee6f  jnz     short loc_18015EEDD
0x18015ee71  test    al, 1
0x18015ee73  jz      loc_18015F751
0x18015ee79  test    bl, 40h
0x18015ee7c  jnz     short loc_18015EEDD
0x18015ee7e  lea     rsi, [r12+278h]
0x18015ee86  mov     [rbp+2C0h+var_340], r15
0x18015ee8a  mov     rcx, rsi; lpCriticalSection
0x18015ee8d  call    cs:__imp_EnterCriticalSection
0x18015ee94  nop     dword ptr [rax+rax+00h]
0x18015ee99  mov     rbx, [r12+270h]
0x18015eea1  test    rbx, rbx
0x18015eea4  jz      short loc_18015EEAA
0x18015eea6  lock inc dword ptr [rbx+8]
0x18015eeaa  mov     rcx, rsi; lpCriticalSection
0x18015eead  call    cs:__imp_LeaveCriticalSection
0x18015eeb4  nop     dword ptr [rax+rax+00h]
0x18015eeb9  test    rbx, rbx
0x18015eebc  setnz   al
0x18015eebf  test    al, al
0x18015eec1  jnz     loc_18015F69B
0x18015eec7  test    rbx, rbx
0x18015eeca  jz      short loc_18015EEDD
0x18015eecc  or      eax, 0FFFFFFFFh
0x18015eecf  lock xadd [rbx+8], eax
0x18015eed4  cmp     eax, 1
0x18015eed7  jz      loc_18015FF54
0x18015eedd  mov     rcx, rdi; this
0x18015eee0  call    ?ResetPrivacyInfo@CDwnBindData@@AEAAXXZ; CDwnBindData::ResetPrivacyInfo(void)
0x18015eee5  mov     ecx, 2000000Dh
0x18015eeea  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18015eef1  nop     dword ptr [rax+rax+00h]
0x18015eef6  test    al, al
0x18015eef8  jnz     loc_18015F7C6
0x18015eefe  cmp     [r13+28h], r15
0x18015ef02  jz      loc_18015F626
0x18015ef08  cmp     [r13+4Ch], r15d
0x18015ef0c  jz      loc_18015F45D
0x18015ef12  mov     eax, r15d
0x18015ef15  mov     rcx, rdi; this
0x18015ef18  mov     [rdi+2DCh], eax
0x18015ef1e  call    ?SetBindOnApt@CDwnBindData@@AEAAJXZ; CDwnBindData::SetBindOnApt(void)
0x18015ef23  mov     esi, eax
0x18015ef25  test    eax, eax
0x18015ef27  jnz     short loc_18015EF93
0x18015ef29  mov     rbx, [r13+28h]
0x18015ef2d  test    rbx, rbx
0x18015ef30  jz      short loc_18015EF41
0x18015ef32  mov     rax, [rbx]
0x18015ef35  mov     rcx, rbx
0x18015ef38  mov     rax, [rax+8]
0x18015ef3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ef41  mov     rcx, [rdi+148h]
0x18015ef48  mov     [rdi+148h], rbx
0x18015ef4f  test    rcx, rcx
0x18015ef52  jz      short loc_18015EF60
0x18015ef54  mov     rax, [rcx]
0x18015ef57  mov     rax, [rax+10h]
0x18015ef5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ef60  mov     rcx, rdi; this
0x18015ef63  mov     [rdi+0FBh], r15b
0x18015ef6a  call    ?SignalData@CDwnBindData@@AEAAXXZ; CDwnBindData::SignalData(void)
0x18015ef6f  mov     esi, r15d
  ... truncated ...
```
