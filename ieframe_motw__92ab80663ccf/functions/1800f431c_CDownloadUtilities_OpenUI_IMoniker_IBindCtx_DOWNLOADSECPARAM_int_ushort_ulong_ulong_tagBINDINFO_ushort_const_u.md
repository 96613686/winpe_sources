# CDownloadUtilities::OpenUI(IMoniker *,IBindCtx *,DOWNLOADSECPARAM,int,ushort *,ulong,ulong,_tagBINDINFO *,ushort const *,uint,IUnknown *,int,ulong,HWND__ *,long,FILEDOWNLOAD_TYPE,ushort const *,CInterThreadMarshal *)

- ea: `0x1800f431c`
- end: `0x1800f491f`
- name: `?OpenUI@CDownloadUtilities@@SAXPEAUIMoniker@@PEAUIBindCtx@@UDOWNLOADSECPARAM@@HPEAGKKPEAU_tagBINDINFO@@PEBGIPEAUIUnknown@@HKPEAUHWND__@@JW4FILEDOWNLOAD_TYPE@@5PEAVCInterThreadMarshal@@@Z`
- size: `1539`
- prototype: `static void __high(struct IMoniker *, struct IBindCtx *, struct DOWNLOADSECPARAM, int, unsigned __int16 *, unsigned int, unsigned int, struct _tagBINDINFO *, const unsigned __int16 *, unsigned int, struct IUnknown *, int, unsigned int, HWND, int, enum FILEDOWNLOAD_TYPE, const unsigned __int16 *, struct CInterThreadMarshal *)`
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f4928`
- `0x1801053cc`
- `0x1801063a4`

## callees

- `0x180007010`
- `0x1800692fc`
- `0x1800a8e64`
- `0x1800a9a60`
- `0x1800a9cb0`
- `0x1800ef50c`
- `0x1800ef620`
- `0x1800ef710`
- `0x1800ef9b0`
- `0x1800f01ec`
- `0x1800f074c`
- `0x1800f0bb0`
- `0x1800f1794`
- `0x1800f235c`
- `0x1800f3074`
- `0x1800f3660`
- `0x1800f431c`
- `0x18018f1e4`
- `0x180438b04`
- `0x180594010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800f4900`
- `KERNEL32!LocalFree` at `0x1800f4900`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800f4353`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800f4368`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800f4353`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800f4368`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800f487e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800f488e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800f489e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800f48ae`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800f48be`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800f48ce`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800f48dd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800f487e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800f488e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800f489e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800f48ae`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800f48be`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800f48ce`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800f48dd`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1800f45e7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1800f45e7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800f4421`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800f4444`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800f4467`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800f448a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800f44ad`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800f4421`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800f4444`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800f4467`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800f448a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1800f44ad`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateThread` at `0x1800f4834`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateThread` at `0x1800f4834`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x1800f47f5`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x1800f47f5`
- `urlmon!CreateAsyncBindCtxEx` at `0x1800f468e`
- `urlmon!CreateAsyncBindCtxEx` at `0x1800f468e`
- `urlmon!ReleaseBindInfo` at `0x1800f48f1`
- `urlmon!ReleaseBindInfo` at `0x1800f48f1`

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
0x1800f431c  mov     [rsp-8+arg_8], rdx
0x1800f4321  mov     [rsp-8+arg_0], rcx
0x1800f4326  push    rbp
0x1800f4327  push    rbx
0x1800f4328  push    rsi
0x1800f4329  push    rdi
0x1800f432a  push    r12
0x1800f432c  push    r13
0x1800f432e  push    r15
0x1800f4330  lea     rbp, [rsp-7]
0x1800f4335  sub     rsp, 100h
0x1800f433c  xor     r12d, r12d
0x1800f433f  mov     rdi, r8
0x1800f4342  mov     rsi, rcx
0x1800f4345  test    r9d, r9d
0x1800f4348  jz      loc_1800F43E7
0x1800f434e  mov     ecx, 20000001h
0x1800f4353  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800f435a  nop     dword ptr [rax+rax+00h]
0x1800f435f  test    al, al
0x1800f4361  jnz     short loc_1800F4378
0x1800f4363  mov     ecx, 20000002h
0x1800f4368  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800f436f  nop     dword ptr [rax+rax+00h]
0x1800f4374  test    al, al
0x1800f4376  jz      short loc_1800F438C
0x1800f4378  lea     rcx, ?FEATURE_ENABLE_LEGACY_DOWNLOAD_UI_BROKER_CALLS@FCK@@3VCFeatureControlKey@@A; this
0x1800f437f  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1800f4384  test    eax, eax
0x1800f4386  jnz     loc_1800F490C
0x1800f438c  mov     rdx, rdi; struct DOWNLOADSECPARAM *
0x1800f438f  lea     rcx, [rbp+37h+var_80]; this
0x1800f4393  call    ??0DOWNLOADSECPARAM@@QEAA@AEBU0@@Z; DOWNLOADSECPARAM::DOWNLOADSECPARAM(DOWNLOADSECPARAM const &)
0x1800f4398  mov     ecx, [rbp+37h+arg_60]
0x1800f439e  mov     r8, rax
0x1800f43a1  mov     r9, [rbp+37h+arg_20]
0x1800f43a5  mov     rdx, [rbp+37h+arg_8]
0x1800f43a9  mov     [rsp+130h+var_E8], ecx
0x1800f43ad  mov     ecx, [rbp+37h+arg_48]
0x1800f43b3  mov     dword ptr [rsp+130h+var_F0], ecx
0x1800f43b7  mov     rcx, [rbp+37h+arg_40]
0x1800f43be  mov     [rsp+130h+var_F8], rcx
0x1800f43c3  mov     rcx, [rbp+37h+pbindinfo]
0x1800f43c7  mov     qword ptr [rsp+130h+var_100], rcx
0x1800f43cc  mov     ecx, [rbp+37h+arg_30]
0x1800f43cf  mov     [rsp+130h+reserved], ecx
0x1800f43d3  mov     ecx, [rbp+37h+arg_28]
0x1800f43d6  mov     dword ptr [rsp+130h+ppBC], ecx
0x1800f43da  mov     rcx, rsi
0x1800f43dd  call    ?OpenUI@CDownloadLegacy@@SAXPEAUIMoniker@@PEAUIBindCtx@@UDOWNLOADSECPARAM@@PEAGKKPEAU_tagBINDINFO@@PEBGIK@Z; CDownloadLegacy::OpenUI(IMoniker *,IBindCtx *,DOWNLOADSECPARAM,ushort *,ulong,ulong,_tagBINDINFO *,ushort const *,uint,ulong)
0x1800f43e2  jmp     loc_1800F490C
0x1800f43e7  mov     rcx, [rbp+37h+punk]; struct IUnknown *
0x1800f43ee  mov     ebx, r12d
0x1800f43f1  mov     [rbp+37h+pv], r12
0x1800f43f8  mov     [rbp+37h+ppwsz], r12
0x1800f43fc  mov     [rbp+37h+var_90], r12
0x1800f4400  mov     [rbp+37h+var_B0], r12
0x1800f4404  mov     [rbp+37h+var_A8], r12
0x1800f4408  mov     [rbp+37h+var_88], r12
0x1800f440c  call    ?GetDownloadDlgOptionsFromMetaTag@CDownloadUtilities@@SAKPEAUIUnknown@@@Z; CDownloadUtilities::GetDownloadDlgOptionsFromMetaTag(IUnknown *)
0x1800f4411  mov     rcx, [rdi+20h]; psz
0x1800f4415  mov     r13d, eax
0x1800f4418  test    rcx, rcx
0x1800f441b  jz      short loc_1800F4437
0x1800f441d  lea     rdx, [rbp+37h+ppwsz]; ppwsz
0x1800f4421  call    cs:__imp_SHStrDupW
0x1800f4428  nop     dword ptr [rax+rax+00h]
0x1800f442d  mov     rcx, [rbp+37h+ppwsz]
0x1800f4431  mov     ebx, eax
0x1800f4433  mov     [rdi+20h], rcx
0x1800f4437  mov     rcx, [rdi+28h]; psz
0x1800f443b  test    rcx, rcx
0x1800f443e  jz      short loc_1800F445A
0x1800f4440  lea     rdx, [rbp+37h+var_90]; ppwsz
0x1800f4444  call    cs:__imp_SHStrDupW
0x1800f444b  nop     dword ptr [rax+rax+00h]
0x1800f4450  mov     ebx, eax
0x1800f4452  mov     rax, [rbp+37h+var_90]
0x1800f4456  mov     [rdi+28h], rax
0x1800f445a  mov     rcx, [rdi+30h]; psz
0x1800f445e  test    rcx, rcx
0x1800f4461  jz      short loc_1800F447D
0x1800f4463  lea     rdx, [rbp+37h+var_B0]; ppwsz
0x1800f4467  call    cs:__imp_SHStrDupW
0x1800f446e  nop     dword ptr [rax+rax+00h]
0x1800f4473  mov     ebx, eax
0x1800f4475  mov     rax, [rbp+37h+var_B0]
0x1800f4479  mov     [rdi+30h], rax
0x1800f447d  mov     rcx, [rdi+38h]; psz
0x1800f4481  test    rcx, rcx
0x1800f4484  jz      short loc_1800F44A0
0x1800f4486  lea     rdx, [rbp+37h+var_A8]; ppwsz
0x1800f448a  call    cs:__imp_SHStrDupW
0x1800f4491  nop     dword ptr [rax+rax+00h]
0x1800f4496  mov     ebx, eax
0x1800f4498  mov     rax, [rbp+37h+var_A8]
0x1800f449c  mov     [rdi+38h], rax
0x1800f44a0  mov     rcx, [rdi+40h]; psz
0x1800f44a4  test    rcx, rcx
0x1800f44a7  jz      short loc_1800F44C3
0x1800f44a9  lea     rdx, [rbp+37h+var_88]; ppwsz
0x1800f44ad  call    cs:__imp_SHStrDupW
0x1800f44b4  nop     dword ptr [rax+rax+00h]
0x1800f44b9  mov     ebx, eax
0x1800f44bb  mov     rax, [rbp+37h+var_88]
0x1800f44bf  mov     [rdi+40h], rax
0x1800f44c3  test    ebx, ebx
0x1800f44c5  js      loc_1800F485E
0x1800f44cb  mov     rax, [rsi]
0x1800f44ce  lea     r9, [rbp+37h+pv]
0x1800f44d5  mov     rdx, [rbp+37h+arg_8]
0x1800f44d9  xor     r8d, r8d
0x1800f44dc  mov     rcx, rsi
0x1800f44df  mov     rax, [rax+0A0h]
0x1800f44e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f44eb  test    eax, eax
0x1800f44ed  js      loc_1800F485E
0x1800f44f3  or      r13d, [rbp+37h+arg_60]
0x1800f44fa  mov     r15, [rbp+37h+arg_40]
0x1800f4501  test    r15, r15
0x1800f4504  jz      short loc_1800F4511
0x1800f4506  cmp     [r15], r12w
0x1800f450a  jz      short loc_1800F4511
0x1800f450c  mov     rbx, r15
0x1800f450f  jmp     short loc_1800F4542
0x1800f4511  mov     rax, [rbp+37h+pv]
0x1800f4518  mov     rbx, r12
0x1800f451b  test    rax, rax
0x1800f451e  jz      short loc_1800F4542
0x1800f4520  cmp     [rbp+37h+var_B0], r12
0x1800f4524  jz      short loc_1800F453F
0x1800f4526  mov     rcx, rax; unsigned __int16 *
0x1800f4529  call    ?IsUrlHandledByBlobProtocol@@YA_NPEBG@Z; IsUrlHandledByBlobProtocol(ushort const *)
0x1800f452e  test    al, al
0x1800f4530  jz      short loc_1800F4538
0x1800f4532  mov     rbx, [rbp+37h+var_B0]
0x1800f4536  jmp     short loc_1800F4542
0x1800f4538  mov     rax, [rbp+37h+pv]
0x1800f453f  mov     rbx, rax
0x1800f4542  mov     rcx, [rbp+37h+ppwsz]; unsigned __int16 *
0x1800f4546  test    rcx, rcx
0x1800f4549  jz      short loc_1800F455B
0x1800f454b  mov     r8d, [rdi+1Ch]; int
0x1800f454f  mov     edx, [rdi+14h]; int
0x1800f4552  call    ?IsFileExtensionSafeForShellExec@CDownloadUtilities@@KAHPEBGHH@Z; CDownloadUtilities::IsFileExtensionSafeForShellExec(ushort const *,int,int)
0x1800f4557  test    eax, eax
0x1800f4559  jmp     short loc_1800F4562
0x1800f455b  cmp     [rbp+37h+arg_58], r12d
0x1800f4562  mov     ecx, r12d
0x1800f4565  setz    cl
0x1800f4568  mov     [rbp+37h+arg_78], ecx
0x1800f456e  call    ?DownloadManagerIsSupported@CDownloadUtilities@@SA_NXZ; CDownloadUtilities::DownloadManagerIsSupported(void)
0x1800f4573  test    al, al
0x1800f4575  jz      short loc_1800F457F
0x1800f4577  mov     eax, r13d
0x1800f457a  and     eax, 4
0x1800f457d  jmp     short loc_1800F4582
0x1800f457f  mov     eax, r12d
0x1800f4582  mov     r8d, [rbp+37h+arg_30]; unsigned int
0x1800f4586  lea     r9, [rbp+37h+arg_78]; int *
0x1800f458d  mov     rcx, [rbp+37h+punk]; struct IUnknown *
0x1800f4594  mov     rdx, rbx; unsigned __int16 *
0x1800f4597  mov     [rsp+130h+var_100], eax; int
0x1800f459b  mov     [rbp+37h+arg_18], eax
0x1800f459e  mov     rax, [rbp+37h+var_B0]
0x1800f45a2  mov     qword ptr [rsp+130h+reserved], rax; unsigned __int16 *
0x1800f45a7  lea     rax, [rbp+37h+arg_18]
0x1800f45ab  mov     [rsp+130h+ppBC], rax; int *
0x1800f45b0  call    ?BlockDownload@CDownloadUtilities@@SAHPEAUIUnknown@@PEBGKPEAH21H@Z; CDownloadUtilities::BlockDownload(IUnknown *,ushort const *,ulong,int *,int *,ushort const *,int)
0x1800f45b5  test    eax, eax
0x1800f45b7  jnz     loc_1800F485E
0x1800f45bd  cmp     [rbp+37h+arg_18], r12d
0x1800f45c1  jz      short loc_1800F45CA
0x1800f45c3  mov     dword ptr [rdi+14h], 1
0x1800f45ca  mov     rcx, [rbp+37h+punk]; punk
0x1800f45d1  lea     r9, [rbp+37h+ppvOut]; ppvOut
0x1800f45d5  lea     r8, _GUID_988934a4_064b_11d3_bb80_00104b35e7f9; riid
0x1800f45dc  mov     [rbp+37h+ppvOut], r12
0x1800f45e0  lea     rdx, IID_IDownloadManager; guidService
0x1800f45e7  call    cs:__imp_IUnknown_QueryService
0x1800f45ee  nop     dword ptr [rax+rax+00h]
0x1800f45f3  mov     rsi, [rbp+37h+pbindinfo]
0x1800f45f7  mov     r12, [rbp+37h+arg_20]
0x1800f45fb  test    eax, eax
0x1800f45fd  jns     short loc_1800F461A
0x1800f45ff  lea     r9, [rbp+37h+ppvOut]
0x1800f4603  lea     r8, _GUID_988934a4_064b_11d3_bb80_00104b35e7f9
0x1800f460a  lea     rdx, aDownloadui; "DownloadUI"
0x1800f4611  call    CreateFromRegKey
0x1800f4616  test    eax, eax
0x1800f4618  js      short loc_1800F4670
0x1800f461a  mov     edx, [rbp+37h+arg_48]
0x1800f4620  mov     rcx, [rbp+37h+ppvOut]
0x1800f4624  mov     r9d, [rbp+37h+arg_28]
0x1800f4628  mov     r8, [rbp+37h+arg_8]
0x1800f462c  mov     dword ptr [rsp+130h+var_F0], edx
0x1800f4630  mov     rax, [rcx]
0x1800f4633  mov     edx, [rbp+37h+arg_30]
0x1800f4636  mov     [rsp+130h+var_F8], r15
0x1800f463b  mov     qword ptr [rsp+130h+var_100], r12
0x1800f4640  mov     rax, [rax+18h]
0x1800f4644  mov     qword ptr [rsp+130h+reserved], rsi
0x1800f4649  mov     dword ptr [rsp+130h+ppBC], edx
0x1800f464d  mov     rdx, [rbp+37h+arg_0]
0x1800f4651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4656  mov     rcx, [rbp+37h+ppvOut]
0x1800f465a  mov     ebx, eax
0x1800f465c  mov     rdx, [rcx]
0x1800f465f  mov     rax, [rdx+10h]
0x1800f4663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4668  test    ebx, ebx
0x1800f466a  jns     loc_1800F4866
0x1800f4670  mov     rcx, [rbp+37h+arg_8]; pbc
0x1800f4674  test    rcx, rcx
0x1800f4677  jnz     short loc_1800F46A4
0x1800f4679  lea     rax, [rbp+37h+arg_8]
0x1800f467d  mov     [rsp+130h+reserved], ecx; reserved
0x1800f4681  xor     r9d, r9d; pEnum
0x1800f4684  mov     [rsp+130h+ppBC], rax; ppBC
0x1800f4689  xor     r8d, r8d; pBSCb
0x1800f468c  xor     edx, edx; dwOptions
0x1800f468e  call    cs:__imp_CreateAsyncBindCtxEx
0x1800f4695  nop     dword ptr [rax+rax+00h]
0x1800f469a  test    eax, eax
0x1800f469c  js      loc_1800F4866
0x1800f46a2  jmp     short loc_1800F46B0
0x1800f46a4  mov     rax, [rcx]
0x1800f46a7  mov     rax, [rax+8]
0x1800f46ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f46b0  cmp     [rbp+37h+punk], 0
0x1800f46b8  jz      short loc_1800F46FE
0x1800f46ba  cmp     [rbp+37h+arg_68], 0
0x1800f46c2  jnz     short loc_1800F46FE
0x1800f46c4  call    ?DownloadManagerIsSupported@CDownloadUtilities@@SA_NXZ; CDownloadUtilities::DownloadManagerIsSupported(void)
0x1800f46c9  test    al, al
0x1800f46cb  jz      short loc_1800F46FE
0x1800f46cd  mov     rcx, [rbp+37h+punk]; struct IUnknown *
0x1800f46d4  lea     r8, [rbp+37h+arg_70]; int *
0x1800f46db  lea     rdx, [rbp+37h+arg_68]; HWND *
0x1800f46e2  call    ?GetFrameHwndAndTabIdFromIUnknown@CDownloadUtilities@@SAJPEAUIUnknown@@PEAPEAUHWND__@@PEAJ@Z; CDownloadUtilities::GetFrameHwndAndTabIdFromIUnknown(IUnknown *,HWND__ * *,long *)
0x1800f46e7  cmp     [rbp+37h+var_A8], 0
0x1800f46ec  jnz     short loc_1800F46FE
0x1800f46ee  mov     rcx, [rbp+37h+punk]; struct IUnknown *
0x1800f46f5  lea     rdx, [rbp+37h+var_A8]; unsigned __int16 **
0x1800f46f9  call    ?GetAppCacheManifestUrlFromUnknown@@YAJPEAUIUnknown@@PEAPEAG@Z; GetAppCacheManifestUrlFromUnknown(IUnknown *,ushort * *)
0x1800f46fe  mov     ecx, 12F8h; dwBytes
0x1800f4703  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f4708  mov     r10, rax
0x1800f470b  test    rax, rax
0x1800f470e  jz      loc_1800F484C
0x1800f4714  mov     r8, [rbp+37h+arg_68]
0x1800f471b  lea     rcx, [rbp+37h+var_80]; this
0x1800f471f  mov     rdx, rdi; struct DOWNLOADSECPARAM *
0x1800f4722  call    ??0DOWNLOADSECPARAM@@QEAA@AEBU0@@Z; DOWNLOADSECPARAM::DOWNLOADSECPARAM(DOWNLOADSECPARAM const &)
0x1800f4727  mov     ecx, [rbp+37h+arg_70]
0x1800f472d  mov     r9, rax
0x1800f4730  mov     rdx, [rbp+37h+pv]
0x1800f4737  mov     [rsp+130h+var_C0], 0
0x1800f4740  mov     [rsp+130h+var_D0], ecx
0x1800f4744  mov     ecx, [rbp+37h+arg_48]
0x1800f474a  mov     [rsp+130h+var_D8], r8
0x1800f474f  mov     r8, r12
0x1800f4752  mov     [rsp+130h+var_E0], r13d
0x1800f4757  mov     [rsp+130h+var_E8], ecx
0x1800f475b  lea     rcx, GUID_NULL
0x1800f4762  mov     [rsp+130h+var_F0], r15
0x1800f4767  mov     [rsp+130h+var_F8], rsi
0x1800f476c  mov     qword ptr [rsp+130h+var_100], rcx
0x1800f4771  mov     ecx, [rbp+37h+arg_30]
0x1800f4774  mov     [rsp+130h+reserved], ecx
0x1800f4778  mov     ecx, [rbp+37h+arg_28]
0x1800f477b  mov     dword ptr [rsp+130h+ppBC], ecx
0x1800f477f  mov     rcx, r10
0x1800f4782  call    ??0CDownloadThreadParam@@QEAA@PEAG0UDOWNLOADSECPARAM@@KKAEBU_GUID@@PEAU_tagBINDINFO@@PEBGIKPEAUHWND__@@JW4FILEDOWNLOAD_TYPE@@4@Z; CDownloadThreadParam::CDownloadThreadParam(ushort *,ushort *,DOWNLOADSECPARAM,ulong,ulong,_GUID const &,_tagBINDINFO *,ushort const *,uint,ulong,HWND__ *,long,FILEDOWNLOAD_TYPE,ushort const *)
0x1800f4787  mov     rbx, rax
0x1800f478a  test    rax, rax
0x1800f478d  jz      loc_1800F484C
0x1800f4793  mov     r8, [rbp+37h+arg_8]; struct IBindCtx *
0x1800f4797  lea     r9, [rbp+37h+arg_88]; struct CInterThreadMarshal **
0x1800f479e  mov     rdx, [rbp+37h+pv]; String1
0x1800f47a5  mov     rcx, rax; this
0x1800f47a8  call    ?MarshalBindContextToStream@CDownloadUtilities@@SAJPEAVCDownloadThreadParam@@PEAGPEAUIBindCtx@@PEAPEAVCInterThreadMarshal@@@Z; CDownloadUtilities::MarshalBindContextToStream(CDownloadThreadParam *,ushort *,IBindCtx *,CInterThreadMarshal * *)
0x1800f47ad  mov     edi, eax
0x1800f47af  mov     [rbp+37h+ppwsz], 0
0x1800f47b7  mov     [rbp+37h+var_90], 0
0x1800f47bf  xor     r12d, r12d
0x1800f47c2  mov     [rbp+37h+pv], 0
0x1800f47cd  xor     esi, esi
0x1800f47cf  mov     [rbp+37h+var_B0], 0
0x1800f47d7  mov     [rbp+37h+var_A8], 0
0x1800f47df  mov     [rbp+37h+var_88], 0
0x1800f47e7  call    ?DownloadManagerIsSupported@CDownloadUtilities@@SA_NXZ; CDownloadUtilities::DownloadManagerIsSupported(void)
0x1800f47ec  test    al, al
0x1800f47ee  jz      short loc_1800F480C
0x1800f47f0  xor     edx, edx
0x1800f47f2  lea     ecx, [rsi+1]
0x1800f47f5  call    cs:__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z; IsoReferenceDefaultScope(ulong,IsoScope * *)
0x1800f47fc  nop     dword ptr [rax+rax+00h]
0x1800f4801  test    eax, eax
0x1800f4803  js      short loc_1800F4844
  ... truncated ...
```
