# CDownloadUtilities::OpenUI(IMoniker *,IBindCtx *,DOWNLOADSECPARAM,int,ushort *,ulong,ulong,_tagBINDINFO *,ushort const *,uint,IUnknown *,int,ulong,HWND__ *,long,FILEDOWNLOAD_TYPE,ushort const *,CInterThreadMarshal *)

- ea: `0x1800ea5d8`
- end: `0x1800eab62`
- name: `?OpenUI@CDownloadUtilities@@SAXPEAUIMoniker@@PEAUIBindCtx@@UDOWNLOADSECPARAM@@HPEAGKKPEAU_tagBINDINFO@@PEBGIPEAUIUnknown@@HKPEAUHWND__@@JW4FILEDOWNLOAD_TYPE@@5PEAVCInterThreadMarshal@@@Z`
- size: `1418`
- prototype: `static void __high(struct IMoniker *, struct IBindCtx *, struct DOWNLOADSECPARAM, int, unsigned __int16 *, unsigned int, unsigned int, struct _tagBINDINFO *, const unsigned __int16 *, unsigned int, struct IUnknown *, int, unsigned int, HWND, int, enum FILEDOWNLOAD_TYPE, const unsigned __int16 *, struct CInterThreadMarshal *)`
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800eab68`
- `0x1800fa348`
- `0x1800fb238`

## callees

- `0x18002acc0`
- `0x180065a9c`
- `0x1800a2bf8`
- `0x1800a3750`
- `0x1800a397c`
- `0x1800e5d9c`
- `0x1800e5eac`
- `0x1800e5f84`
- `0x1800e620c`
- `0x1800e69d0`
- `0x1800e6efc`
- `0x1800e7310`
- `0x1800e7e30`
- `0x1800e88d4`
- `0x1800e946c`
- `0x1800e9a04`
- `0x1800ea5d8`
- `0x18017ce04`
- `0x1804017e8`
- `0x180550010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800eab4a`
- `KERNEL32!LocalFree` at `0x1800eab4a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ea60f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ea61e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ea60f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ea61e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800eaaf8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800eab02`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800eab0c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800eab16`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800eab20`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800eab2a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800eab33`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800eaaf8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800eab02`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800eab0c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800eab16`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800eab20`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800eab2a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800eab33`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1800ea879`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1800ea879`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800ea6d1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800ea6ee`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800ea70b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800ea728`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800ea745`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800ea6d1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800ea6ee`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800ea70b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800ea728`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800ea745`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateThread` at `0x1800eaab4`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateThread` at `0x1800eaab4`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x1800eaa7b`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x1800eaa7b`
- `urlmon!CreateAsyncBindCtxEx` at `0x1800ea91a`
- `urlmon!CreateAsyncBindCtxEx` at `0x1800ea91a`
- `urlmon!ReleaseBindInfo` at `0x1800eab41`
- `urlmon!ReleaseBindInfo` at `0x1800eab41`

## pseudocode

```c
void __fastcall CDownloadUtilities::OpenUI(
        __int64 a1,
        IBindCtx *a2,
        __int64 a3,
        int a4,
        LPVOID a5,
        unsigned int a6,
        unsigned int a7,
        BINDINFO *pbindinfo,
        unsigned __int16 *a9,
        int a10,
        IUnknown *punk,
        int a12,
        int a13,
        HWND a14,
        int a15,
        int a16,
        LPVOID pv,
        CInterThreadMarshal *a18)
{
  DOWNLOADSECPARAM *v20; // rax
  HRESULT v21; // ebx
  unsigned int DownloadDlgOptionsFromMetaTag; // eax
  unsigned int v23; // edx
  const WCHAR *v24; // rcx
  unsigned int v25; // r13d
  const WCHAR *v26; // rcx
  const WCHAR *v27; // rcx
  const WCHAR *v28; // rcx
  const WCHAR *v29; // rcx
  int v30; // r13d
  unsigned __int16 *v31; // r15
  unsigned __int16 *v32; // rbx
  unsigned __int16 *v33; // rax
  bool v34; // zf
  int v35; // eax
  HRESULT v36; // eax
  __int64 v37; // rcx
  BINDINFO *v38; // rsi
  void *v39; // r12
  int v40; // ebx
  DOWNLOADSECPARAM *v41; // rax
  __int64 v42; // r8
  __int64 v43; // r10
  struct CDownloadThreadParam *v44; // rax
  struct CDownloadThreadParam *v45; // rbx
  int v46; // edi
  unsigned int v47; // edx
  LPWSTR v48; // [rsp+80h] [rbp-79h] BYREF
  LPWSTR v49; // [rsp+88h] [rbp-71h] BYREF
  LPWSTR ppwsz; // [rsp+90h] [rbp-69h] BYREF
  void *ppvOut; // [rsp+98h] [rbp-61h] BYREF
  LPWSTR v52; // [rsp+A0h] [rbp-59h] BYREF
  LPWSTR v53; // [rsp+A8h] [rbp-51h] BYREF
  _BYTE v54[128]; // [rsp+B0h] [rbp-49h] BYREF
  IBindCtx *ppBC; // [rsp+148h] [rbp+4Fh] BYREF
  int v57; // [rsp+158h] [rbp+5Fh] BYREF

  ppBC = a2;
  if ( a4 )
  {
    if ( !(unsigned __int8)IEConfiguration_GetBool(536870913) && !(unsigned __int8)IEConfiguration_GetBool(536870914)
      || !(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_ENABLE_LEGACY_DOWNLOAD_UI_BROKER_CALLS) )
    {
      v20 = DOWNLOADSECPARAM::DOWNLOADSECPARAM((DOWNLOADSECPARAM *)v54, (const struct DOWNLOADSECPARAM *)a3);
      CDownloadLegacy::OpenUI(a1, ppBC, v20, a5, a6, a7, pbindinfo, a9, a10, a13);
    }
    return;
  }
  v21 = 0;
  pv = 0;
  ppwsz = 0;
  v52 = 0;
  v48 = 0;
  v49 = 0;
  v53 = 0;
  DownloadDlgOptionsFromMetaTag = CDownloadUtilities::GetDownloadDlgOptionsFromMetaTag(punk);
  v24 = *(const WCHAR **)(a3 + 32);
  v25 = DownloadDlgOptionsFromMetaTag;
  if ( v24 )
  {
    v21 = SHStrDupW(v24, &ppwsz);
    *(_QWORD *)(a3 + 32) = ppwsz;
  }
  v26 = *(const WCHAR **)(a3 + 40);
  if ( v26 )
  {
    v21 = SHStrDupW(v26, &v52);
    *(_QWORD *)(a3 + 40) = v52;
  }
  v27 = *(const WCHAR **)(a3 + 48);
  if ( v27 )
  {
    v21 = SHStrDupW(v27, &v48);
    *(_QWORD *)(a3 + 48) = v48;
  }
  v28 = *(const WCHAR **)(a3 + 56);
  if ( v28 )
  {
    v21 = SHStrDupW(v28, &v49);
    *(_QWORD *)(a3 + 56) = v49;
  }
  v29 = *(const WCHAR **)(a3 + 64);
  if ( v29 )
  {
    v21 = SHStrDupW(v29, &v53);
    *(_QWORD *)(a3 + 64) = v53;
  }
  if ( v21 < 0
    || (*(int (__fastcall **)(__int64, IBindCtx *, _QWORD, LPVOID *))(*(_QWORD *)a1 + 160LL))(a1, ppBC, 0, &pv) < 0 )
  {
    goto LABEL_59;
  }
  v30 = a13 | v25;
  v31 = a9;
  if ( a9 && *a9 )
  {
    v32 = a9;
    goto LABEL_27;
  }
  v33 = (unsigned __int16 *)pv;
  v32 = 0;
  if ( pv )
  {
    if ( v48 )
    {
      if ( IsUrlHandledByBlobProtocol((const unsigned __int16 *)pv) )
      {
        v32 = v48;
        goto LABEL_27;
      }
      v33 = (unsigned __int16 *)pv;
    }
    v32 = v33;
  }
LABEL_27:
  if ( ppwsz )
    v34 = (unsigned int)CDownloadUtilities::IsFileExtensionSafeForShellExec(
                          ppwsz,
                          *(_DWORD *)(a3 + 20),
                          *(_DWORD *)(a3 + 28)) == 0;
  else
    v34 = a12 == 0;
  a16 = v34;
  if ( CDownloadUtilities::DownloadManagerIsSupported() )
    v35 = v30 & 4;
  else
    v35 = 0;
  v57 = v35;
  if ( (unsigned int)CDownloadUtilities::BlockDownload(punk, v32, a7, &a16, &v57, v48, v35) )
  {
LABEL_59:
    v38 = pbindinfo;
    v39 = a5;
    goto LABEL_60;
  }
  if ( v57 )
    *(_DWORD *)(a3 + 20) = 1;
  ppvOut = 0;
  v36 = IUnknown_QueryService(punk, &IID_IDownloadManager, &GUID_988934a4_064b_11d3_bb80_00104b35e7f9, &ppvOut);
  v38 = pbindinfo;
  v39 = a5;
  if ( v36 >= 0 || (int)CreateFromRegKey(v37, L"DownloadUI", &GUID_988934a4_064b_11d3_bb80_00104b35e7f9, &ppvOut) >= 0 )
  {
    v40 = (*(__int64 (__fastcall **)(void *, __int64, IBindCtx *, _QWORD, unsigned int, BINDINFO *, void *, unsigned __int16 *, int))(*(_QWORD *)ppvOut + 24LL))(
            ppvOut,
            a1,
            ppBC,
            a6,
            a7,
            v38,
            v39,
            v31,
            a10);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    if ( v40 >= 0 )
      goto LABEL_60;
  }
  if ( ppBC )
  {
    ((void (__fastcall *)(IBindCtx *))ppBC->lpVtbl->AddRef)(ppBC);
LABEL_43:
    if ( punk )
    {
      if ( !a14 && CDownloadUtilities::DownloadManagerIsSupported() )
      {
        CDownloadUtilities::GetFrameHwndAndTabIdFromIUnknown(punk, &a14, &a15);
        if ( !v49 )
          GetAppCacheManifestUrlFromUnknown(punk, &v49);
      }
    }
    if ( !operator new(0x12F8u) )
      goto LABEL_58;
    v41 = DOWNLOADSECPARAM::DOWNLOADSECPARAM((DOWNLOADSECPARAM *)v54, (const struct DOWNLOADSECPARAM *)a3);
    v44 = (struct CDownloadThreadParam *)CDownloadThreadParam::CDownloadThreadParam(
                                           v43,
                                           pv,
                                           v39,
                                           v41,
                                           a6,
                                           a7,
                                           &GUID_NULL,
                                           v38,
                                           v31,
                                           a10,
                                           v30,
                                           v42,
                                           a15);
    v45 = v44;
    if ( !v44 )
      goto LABEL_58;
    v46 = CDownloadUtilities::MarshalBindContextToStream(v44, (wchar_t *)pv, ppBC, &a18);
    ppwsz = 0;
    v52 = 0;
    v39 = 0;
    pv = 0;
    v38 = 0;
    v48 = 0;
    v49 = 0;
    v53 = 0;
    if ( CDownloadUtilities::DownloadManagerIsSupported() )
    {
      if ( (int)IsoReferenceDefaultScope(1u, 0) < 0 )
        goto LABEL_57;
      CDownloadUtilities::IncrementDownloadRefCount();
    }
    else if ( v46 < 0 )
    {
LABEL_58:
      ((void (__fastcall *)(IBindCtx *))ppBC->lpVtbl->Release)(ppBC);
      goto LABEL_60;
    }
    if ( CDownloadUtilities::DownloadManagerIsSupported() )
    {
      CDownloadState::OpenUI(v45);
      goto LABEL_58;
    }
    if ( SHCreateThread(IEDownload_ThreadProc, v45, 0x2Cu, 0) )
      goto LABEL_58;
LABEL_57:
    CDownloadThreadParam::`scalar deleting destructor'(v45, v47);
    goto LABEL_58;
  }
  if ( CreateAsyncBindCtxEx(0, 0, 0, 0, &ppBC, 0) >= 0 )
    goto LABEL_43;
LABEL_60:
  if ( a18 )
    CInterThreadMarshal::`scalar deleting destructor'(a18, v23);
  CoTaskMemFree(pv);
  CoTaskMemFree(ppwsz);
  CoTaskMemFree(v52);
  CoTaskMemFree(v48);
  CoTaskMemFree(v49);
  CoTaskMemFree(v53);
  CoTaskMemFree(v39);
  if ( v38 )
  {
    ReleaseBindInfo(v38);
    LocalFree(v38);
  }
}

```

## disassembly

```asm
0x1800ea5d8  mov     [rsp-8+arg_8], rdx
0x1800ea5dd  mov     [rsp-8+arg_0], rcx
0x1800ea5e2  push    rbp
0x1800ea5e3  push    rbx
0x1800ea5e4  push    rsi
0x1800ea5e5  push    rdi
0x1800ea5e6  push    r12
0x1800ea5e8  push    r13
0x1800ea5ea  push    r15
0x1800ea5ec  lea     rbp, [rsp-7]
0x1800ea5f1  sub     rsp, 100h
0x1800ea5f8  xor     r12d, r12d
0x1800ea5fb  mov     rdi, r8
0x1800ea5fe  mov     rsi, rcx
0x1800ea601  test    r9d, r9d
0x1800ea604  jz      loc_1800EA697
0x1800ea60a  mov     ecx, 20000001h
0x1800ea60f  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800ea615  test    al, al
0x1800ea617  jnz     short loc_1800EA628
0x1800ea619  mov     ecx, 20000002h
0x1800ea61e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800ea624  test    al, al
0x1800ea626  jz      short loc_1800EA63C
0x1800ea628  lea     rcx, ?FEATURE_ENABLE_LEGACY_DOWNLOAD_UI_BROKER_CALLS@FCK@@3VCFeatureControlKey@@A; this
0x1800ea62f  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1800ea634  test    eax, eax
0x1800ea636  jnz     loc_1800EAB50
0x1800ea63c  mov     rdx, rdi; struct DOWNLOADSECPARAM *
0x1800ea63f  lea     rcx, [rbp+37h+var_80]; this
0x1800ea643  call    ??0DOWNLOADSECPARAM@@QEAA@AEBU0@@Z; DOWNLOADSECPARAM::DOWNLOADSECPARAM(DOWNLOADSECPARAM const &)
0x1800ea648  mov     ecx, [rbp+37h+arg_60]
0x1800ea64e  mov     r8, rax
0x1800ea651  mov     r9, [rbp+37h+arg_20]
0x1800ea655  mov     rdx, [rbp+37h+arg_8]
0x1800ea659  mov     [rsp+130h+var_E8], ecx
0x1800ea65d  mov     ecx, [rbp+37h+arg_48]
0x1800ea663  mov     dword ptr [rsp+130h+var_F0], ecx
0x1800ea667  mov     rcx, [rbp+37h+arg_40]
0x1800ea66e  mov     [rsp+130h+var_F8], rcx
0x1800ea673  mov     rcx, [rbp+37h+pbindinfo]
0x1800ea677  mov     qword ptr [rsp+130h+var_100], rcx
0x1800ea67c  mov     ecx, [rbp+37h+arg_30]
0x1800ea67f  mov     [rsp+130h+reserved], ecx
0x1800ea683  mov     ecx, [rbp+37h+arg_28]
0x1800ea686  mov     dword ptr [rsp+130h+ppBC], ecx
0x1800ea68a  mov     rcx, rsi
0x1800ea68d  call    ?OpenUI@CDownloadLegacy@@SAXPEAUIMoniker@@PEAUIBindCtx@@UDOWNLOADSECPARAM@@PEAGKKPEAU_tagBINDINFO@@PEBGIK@Z; CDownloadLegacy::OpenUI(IMoniker *,IBindCtx *,DOWNLOADSECPARAM,ushort *,ulong,ulong,_tagBINDINFO *,ushort const *,uint,ulong)
0x1800ea692  jmp     loc_1800EAB50
0x1800ea697  mov     rcx, [rbp+37h+punk]; struct IUnknown *
0x1800ea69e  mov     ebx, r12d
0x1800ea6a1  mov     [rbp+37h+pv], r12
0x1800ea6a8  mov     [rbp+37h+ppwsz], r12
0x1800ea6ac  mov     [rbp+37h+var_90], r12
0x1800ea6b0  mov     [rbp+37h+var_B0], r12
0x1800ea6b4  mov     [rbp+37h+var_A8], r12
0x1800ea6b8  mov     [rbp+37h+var_88], r12
0x1800ea6bc  call    ?GetDownloadDlgOptionsFromMetaTag@CDownloadUtilities@@SAKPEAUIUnknown@@@Z; CDownloadUtilities::GetDownloadDlgOptionsFromMetaTag(IUnknown *)
0x1800ea6c1  mov     rcx, [rdi+20h]; psz
0x1800ea6c5  mov     r13d, eax
0x1800ea6c8  test    rcx, rcx
0x1800ea6cb  jz      short loc_1800EA6E1
0x1800ea6cd  lea     rdx, [rbp+37h+ppwsz]; ppwsz
0x1800ea6d1  call    cs:__imp_SHStrDupW
0x1800ea6d7  mov     rcx, [rbp+37h+ppwsz]
0x1800ea6db  mov     ebx, eax
0x1800ea6dd  mov     [rdi+20h], rcx
0x1800ea6e1  mov     rcx, [rdi+28h]; psz
0x1800ea6e5  test    rcx, rcx
0x1800ea6e8  jz      short loc_1800EA6FE
0x1800ea6ea  lea     rdx, [rbp+37h+var_90]; ppwsz
0x1800ea6ee  call    cs:__imp_SHStrDupW
0x1800ea6f4  mov     ebx, eax
0x1800ea6f6  mov     rax, [rbp+37h+var_90]
0x1800ea6fa  mov     [rdi+28h], rax
0x1800ea6fe  mov     rcx, [rdi+30h]; psz
0x1800ea702  test    rcx, rcx
0x1800ea705  jz      short loc_1800EA71B
0x1800ea707  lea     rdx, [rbp+37h+var_B0]; ppwsz
0x1800ea70b  call    cs:__imp_SHStrDupW
0x1800ea711  mov     ebx, eax
0x1800ea713  mov     rax, [rbp+37h+var_B0]
0x1800ea717  mov     [rdi+30h], rax
0x1800ea71b  mov     rcx, [rdi+38h]; psz
0x1800ea71f  test    rcx, rcx
0x1800ea722  jz      short loc_1800EA738
0x1800ea724  lea     rdx, [rbp+37h+var_A8]; ppwsz
0x1800ea728  call    cs:__imp_SHStrDupW
0x1800ea72e  mov     ebx, eax
0x1800ea730  mov     rax, [rbp+37h+var_A8]
0x1800ea734  mov     [rdi+38h], rax
0x1800ea738  mov     rcx, [rdi+40h]; psz
0x1800ea73c  test    rcx, rcx
0x1800ea73f  jz      short loc_1800EA755
0x1800ea741  lea     rdx, [rbp+37h+var_88]; ppwsz
0x1800ea745  call    cs:__imp_SHStrDupW
0x1800ea74b  mov     ebx, eax
0x1800ea74d  mov     rax, [rbp+37h+var_88]
0x1800ea751  mov     [rdi+40h], rax
0x1800ea755  test    ebx, ebx
0x1800ea757  js      loc_1800EAAD8
0x1800ea75d  mov     rax, [rsi]
0x1800ea760  lea     r9, [rbp+37h+pv]
0x1800ea767  mov     rdx, [rbp+37h+arg_8]
0x1800ea76b  xor     r8d, r8d
0x1800ea76e  mov     rcx, rsi
0x1800ea771  mov     rax, [rax+0A0h]
0x1800ea778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea77d  test    eax, eax
0x1800ea77f  js      loc_1800EAAD8
0x1800ea785  or      r13d, [rbp+37h+arg_60]
0x1800ea78c  mov     r15, [rbp+37h+arg_40]
0x1800ea793  test    r15, r15
0x1800ea796  jz      short loc_1800EA7A3
0x1800ea798  cmp     [r15], r12w
0x1800ea79c  jz      short loc_1800EA7A3
0x1800ea79e  mov     rbx, r15
0x1800ea7a1  jmp     short loc_1800EA7D4
0x1800ea7a3  mov     rax, [rbp+37h+pv]
0x1800ea7aa  mov     rbx, r12
0x1800ea7ad  test    rax, rax
0x1800ea7b0  jz      short loc_1800EA7D4
0x1800ea7b2  cmp     [rbp+37h+var_B0], r12
0x1800ea7b6  jz      short loc_1800EA7D1
0x1800ea7b8  mov     rcx, rax; unsigned __int16 *
0x1800ea7bb  call    ?IsUrlHandledByBlobProtocol@@YA_NPEBG@Z; IsUrlHandledByBlobProtocol(ushort const *)
0x1800ea7c0  test    al, al
0x1800ea7c2  jz      short loc_1800EA7CA
0x1800ea7c4  mov     rbx, [rbp+37h+var_B0]
0x1800ea7c8  jmp     short loc_1800EA7D4
0x1800ea7ca  mov     rax, [rbp+37h+pv]
0x1800ea7d1  mov     rbx, rax
0x1800ea7d4  mov     rcx, [rbp+37h+ppwsz]; unsigned __int16 *
0x1800ea7d8  test    rcx, rcx
0x1800ea7db  jz      short loc_1800EA7ED
0x1800ea7dd  mov     r8d, [rdi+1Ch]; int
0x1800ea7e1  mov     edx, [rdi+14h]; int
0x1800ea7e4  call    ?IsFileExtensionSafeForShellExec@CDownloadUtilities@@KAHPEBGHH@Z; CDownloadUtilities::IsFileExtensionSafeForShellExec(ushort const *,int,int)
0x1800ea7e9  test    eax, eax
0x1800ea7eb  jmp     short loc_1800EA7F4
0x1800ea7ed  cmp     [rbp+37h+arg_58], r12d
0x1800ea7f4  mov     ecx, r12d
0x1800ea7f7  setz    cl
0x1800ea7fa  mov     [rbp+37h+arg_78], ecx
0x1800ea800  call    ?DownloadManagerIsSupported@CDownloadUtilities@@SA_NXZ; CDownloadUtilities::DownloadManagerIsSupported(void)
0x1800ea805  test    al, al
0x1800ea807  jz      short loc_1800EA811
0x1800ea809  mov     eax, r13d
0x1800ea80c  and     eax, 4
0x1800ea80f  jmp     short loc_1800EA814
0x1800ea811  mov     eax, r12d
0x1800ea814  mov     r8d, [rbp+37h+arg_30]; unsigned int
0x1800ea818  lea     r9, [rbp+37h+arg_78]; int *
0x1800ea81f  mov     rcx, [rbp+37h+punk]; struct IUnknown *
0x1800ea826  mov     rdx, rbx; unsigned __int16 *
0x1800ea829  mov     [rsp+130h+var_100], eax; int
0x1800ea82d  mov     [rbp+37h+arg_18], eax
0x1800ea830  mov     rax, [rbp+37h+var_B0]
0x1800ea834  mov     qword ptr [rsp+130h+reserved], rax; unsigned __int16 *
0x1800ea839  lea     rax, [rbp+37h+arg_18]
0x1800ea83d  mov     [rsp+130h+ppBC], rax; int *
0x1800ea842  call    ?BlockDownload@CDownloadUtilities@@SAHPEAUIUnknown@@PEBGKPEAH21H@Z; CDownloadUtilities::BlockDownload(IUnknown *,ushort const *,ulong,int *,int *,ushort const *,int)
0x1800ea847  test    eax, eax
0x1800ea849  jnz     loc_1800EAAD8
0x1800ea84f  cmp     [rbp+37h+arg_18], r12d
0x1800ea853  jz      short loc_1800EA85C
0x1800ea855  mov     dword ptr [rdi+14h], 1
0x1800ea85c  mov     rcx, [rbp+37h+punk]; punk
0x1800ea863  lea     r9, [rbp+37h+ppvOut]; ppvOut
0x1800ea867  lea     r8, _GUID_988934a4_064b_11d3_bb80_00104b35e7f9; riid
0x1800ea86e  mov     [rbp+37h+ppvOut], r12
0x1800ea872  lea     rdx, IID_IDownloadManager; guidService
0x1800ea879  call    cs:__imp_IUnknown_QueryService
0x1800ea87f  mov     rsi, [rbp+37h+pbindinfo]
0x1800ea883  mov     r12, [rbp+37h+arg_20]
0x1800ea887  test    eax, eax
0x1800ea889  jns     short loc_1800EA8A6
0x1800ea88b  lea     r9, [rbp+37h+ppvOut]
0x1800ea88f  lea     r8, _GUID_988934a4_064b_11d3_bb80_00104b35e7f9
0x1800ea896  lea     rdx, aDownloadui; "DownloadUI"
0x1800ea89d  call    CreateFromRegKey
0x1800ea8a2  test    eax, eax
0x1800ea8a4  js      short loc_1800EA8FC
0x1800ea8a6  mov     edx, [rbp+37h+arg_48]
0x1800ea8ac  mov     rcx, [rbp+37h+ppvOut]
0x1800ea8b0  mov     r9d, [rbp+37h+arg_28]
0x1800ea8b4  mov     r8, [rbp+37h+arg_8]
0x1800ea8b8  mov     dword ptr [rsp+130h+var_F0], edx
0x1800ea8bc  mov     rax, [rcx]
0x1800ea8bf  mov     edx, [rbp+37h+arg_30]
0x1800ea8c2  mov     [rsp+130h+var_F8], r15
0x1800ea8c7  mov     qword ptr [rsp+130h+var_100], r12
0x1800ea8cc  mov     rax, [rax+18h]
0x1800ea8d0  mov     qword ptr [rsp+130h+reserved], rsi
0x1800ea8d5  mov     dword ptr [rsp+130h+ppBC], edx
0x1800ea8d9  mov     rdx, [rbp+37h+arg_0]
0x1800ea8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea8e2  mov     rcx, [rbp+37h+ppvOut]
0x1800ea8e6  mov     ebx, eax
0x1800ea8e8  mov     rdx, [rcx]
0x1800ea8eb  mov     rax, [rdx+10h]
0x1800ea8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea8f4  test    ebx, ebx
0x1800ea8f6  jns     loc_1800EAAE0
0x1800ea8fc  mov     rcx, [rbp+37h+arg_8]; pbc
0x1800ea900  test    rcx, rcx
0x1800ea903  jnz     short loc_1800EA92A
0x1800ea905  lea     rax, [rbp+37h+arg_8]
0x1800ea909  mov     [rsp+130h+reserved], ecx; reserved
0x1800ea90d  xor     r9d, r9d; pEnum
0x1800ea910  mov     [rsp+130h+ppBC], rax; ppBC
0x1800ea915  xor     r8d, r8d; pBSCb
0x1800ea918  xor     edx, edx; dwOptions
0x1800ea91a  call    cs:__imp_CreateAsyncBindCtxEx
0x1800ea920  test    eax, eax
0x1800ea922  js      loc_1800EAAE0
0x1800ea928  jmp     short loc_1800EA936
0x1800ea92a  mov     rax, [rcx]
0x1800ea92d  mov     rax, [rax+8]
0x1800ea931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea936  cmp     [rbp+37h+punk], 0
0x1800ea93e  jz      short loc_1800EA984
0x1800ea940  cmp     [rbp+37h+arg_68], 0
0x1800ea948  jnz     short loc_1800EA984
0x1800ea94a  call    ?DownloadManagerIsSupported@CDownloadUtilities@@SA_NXZ; CDownloadUtilities::DownloadManagerIsSupported(void)
0x1800ea94f  test    al, al
0x1800ea951  jz      short loc_1800EA984
0x1800ea953  mov     rcx, [rbp+37h+punk]; struct IUnknown *
0x1800ea95a  lea     r8, [rbp+37h+arg_70]; int *
0x1800ea961  lea     rdx, [rbp+37h+arg_68]; HWND *
0x1800ea968  call    ?GetFrameHwndAndTabIdFromIUnknown@CDownloadUtilities@@SAJPEAUIUnknown@@PEAPEAUHWND__@@PEAJ@Z; CDownloadUtilities::GetFrameHwndAndTabIdFromIUnknown(IUnknown *,HWND__ * *,long *)
0x1800ea96d  cmp     [rbp+37h+var_A8], 0
0x1800ea972  jnz     short loc_1800EA984
0x1800ea974  mov     rcx, [rbp+37h+punk]; struct IUnknown *
0x1800ea97b  lea     rdx, [rbp+37h+var_A8]; unsigned __int16 **
0x1800ea97f  call    ?GetAppCacheManifestUrlFromUnknown@@YAJPEAUIUnknown@@PEAPEAG@Z; GetAppCacheManifestUrlFromUnknown(IUnknown *,ushort * *)
0x1800ea984  mov     ecx, 12F8h; dwBytes
0x1800ea989  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ea98e  mov     r10, rax
0x1800ea991  test    rax, rax
0x1800ea994  jz      loc_1800EAAC6
0x1800ea99a  mov     r8, [rbp+37h+arg_68]
0x1800ea9a1  lea     rcx, [rbp+37h+var_80]; this
0x1800ea9a5  mov     rdx, rdi; struct DOWNLOADSECPARAM *
0x1800ea9a8  call    ??0DOWNLOADSECPARAM@@QEAA@AEBU0@@Z; DOWNLOADSECPARAM::DOWNLOADSECPARAM(DOWNLOADSECPARAM const &)
0x1800ea9ad  mov     ecx, [rbp+37h+arg_70]
0x1800ea9b3  mov     r9, rax
0x1800ea9b6  mov     rdx, [rbp+37h+pv]
0x1800ea9bd  mov     [rsp+130h+var_C0], 0
0x1800ea9c6  mov     [rsp+130h+var_D0], ecx
0x1800ea9ca  mov     ecx, [rbp+37h+arg_48]
0x1800ea9d0  mov     [rsp+130h+var_D8], r8
0x1800ea9d5  mov     r8, r12
0x1800ea9d8  mov     [rsp+130h+var_E0], r13d
0x1800ea9dd  mov     [rsp+130h+var_E8], ecx
0x1800ea9e1  lea     rcx, GUID_NULL
0x1800ea9e8  mov     [rsp+130h+var_F0], r15
0x1800ea9ed  mov     [rsp+130h+var_F8], rsi
0x1800ea9f2  mov     qword ptr [rsp+130h+var_100], rcx
0x1800ea9f7  mov     ecx, [rbp+37h+arg_30]
0x1800ea9fa  mov     [rsp+130h+reserved], ecx
0x1800ea9fe  mov     ecx, [rbp+37h+arg_28]
0x1800eaa01  mov     dword ptr [rsp+130h+ppBC], ecx
0x1800eaa05  mov     rcx, r10
0x1800eaa08  call    ??0CDownloadThreadParam@@QEAA@PEAG0UDOWNLOADSECPARAM@@KKAEBU_GUID@@PEAU_tagBINDINFO@@PEBGIKPEAUHWND__@@JW4FILEDOWNLOAD_TYPE@@4@Z; CDownloadThreadParam::CDownloadThreadParam(ushort *,ushort *,DOWNLOADSECPARAM,ulong,ulong,_GUID const &,_tagBINDINFO *,ushort const *,uint,ulong,HWND__ *,long,FILEDOWNLOAD_TYPE,ushort const *)
0x1800eaa0d  mov     rbx, rax
0x1800eaa10  test    rax, rax
0x1800eaa13  jz      loc_1800EAAC6
0x1800eaa19  mov     r8, [rbp+37h+arg_8]; struct IBindCtx *
0x1800eaa1d  lea     r9, [rbp+37h+arg_88]; struct CInterThreadMarshal **
0x1800eaa24  mov     rdx, [rbp+37h+pv]; String1
0x1800eaa2b  mov     rcx, rax; this
0x1800eaa2e  call    ?MarshalBindContextToStream@CDownloadUtilities@@SAJPEAVCDownloadThreadParam@@PEAGPEAUIBindCtx@@PEAPEAVCInterThreadMarshal@@@Z; CDownloadUtilities::MarshalBindContextToStream(CDownloadThreadParam *,ushort *,IBindCtx *,CInterThreadMarshal * *)
0x1800eaa33  mov     edi, eax
0x1800eaa35  mov     [rbp+37h+ppwsz], 0
0x1800eaa3d  mov     [rbp+37h+var_90], 0
0x1800eaa45  xor     r12d, r12d
0x1800eaa48  mov     [rbp+37h+pv], 0
0x1800eaa53  xor     esi, esi
0x1800eaa55  mov     [rbp+37h+var_B0], 0
0x1800eaa5d  mov     [rbp+37h+var_A8], 0
0x1800eaa65  mov     [rbp+37h+var_88], 0
0x1800eaa6d  call    ?DownloadManagerIsSupported@CDownloadUtilities@@SA_NXZ; CDownloadUtilities::DownloadManagerIsSupported(void)
0x1800eaa72  test    al, al
0x1800eaa74  jz      short loc_1800EAA8C
0x1800eaa76  xor     edx, edx
0x1800eaa78  lea     ecx, [rsi+1]
0x1800eaa7b  call    cs:__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z; IsoReferenceDefaultScope(ulong,IsoScope * *)
0x1800eaa81  test    eax, eax
0x1800eaa83  js      short loc_1800EAABE
0x1800eaa85  call    ?IncrementDownloadRefCount@CDownloadUtilities@@SAJXZ; CDownloadUtilities::IncrementDownloadRefCount(void)
0x1800eaa8a  jmp     short loc_1800EAA90
0x1800eaa8c  test    edi, edi
0x1800eaa8e  js      short loc_1800EAAC6
0x1800eaa90  call    ?DownloadManagerIsSupported@CDownloadUtilities@@SA_NXZ; CDownloadUtilities::DownloadManagerIsSupported(void)
0x1800eaa95  test    al, al
0x1800eaa97  jz      short loc_1800EAAA3
0x1800eaa99  mov     rcx, rbx; this
0x1800eaa9c  call    ?OpenUI@CDownloadState@@SAXPEAVCDownloadThreadParam@@@Z; CDownloadState::OpenUI(CDownloadThreadParam *)
0x1800eaaa1  jmp     short loc_1800EAAC6
  ... truncated ...
```
