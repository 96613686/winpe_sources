# CCorSvcBindToWorker::BindToRuntimeWorker(ushort *,ulong,ushort *,ICorSvcLogger *,ICorSvcWorker * *)

- ea: `0x18002e940`
- end: `0x18002f254`
- name: `?BindToRuntimeWorker@CCorSvcBindToWorker@@UEAAJPEAGK0PEAUICorSvcLogger@@PEAPEAUICorSvcWorker@@@Z`
- size: `2324`
- prototype: `__int64 __fastcall(CCorSvcBindToWorker *this, unsigned __int16 *, __int64, unsigned __int16 *, struct ICorSvcLogger *, struct ICorSvcWorker **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008304`
- `0x18000838c`
- `0x18002e940`
- `0x180030568`
- `0x180034fd4`
- `0x180036fd0`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `ucrtbase_clr0400!wcscpy_s` at `0x18002ec80`
- `ucrtbase_clr0400!wcscpy_s` at `0x18002ec8f`
- `ucrtbase_clr0400!wcscpy_s` at `0x18002ec80`
- `ucrtbase_clr0400!wcscpy_s` at `0x18002ec8f`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002ef8f`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002ef8f`
- `ole32!CoTaskMemFree` at `0x18002ef69`
- `ole32!CoTaskMemFree` at `0x18002ef69`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ef28`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f043`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ef28`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f043`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f0b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f0f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f0b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f0f3`
- `OLEAUT32!__imp_SysStringLen` at `0x18002eaea`
- `OLEAUT32!__imp_SysStringLen` at `0x18002ec69`
- `OLEAUT32!__imp_SysStringLen` at `0x18002eaea`
- `OLEAUT32!__imp_SysStringLen` at `0x18002ec69`

## string_xrefs

- `0x18002ee61`: `NGenCreateNGenWorker`

## pseudocode

```c
__int64 __fastcall CCorSvcBindToWorker::BindToRuntimeWorker(
        CCorSvcBindToWorker *this,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        struct ICorSvcLogger *a5,
        struct ICorSvcWorker **a6)
{
  int v7; // eax
  int v8; // eax
  int v9; // eax
  void *ConfigString_DontUse; // r14
  void *v11; // rsi
  int v12; // r13d
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned int v17; // r14d
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  OLECHAR *v24; // rsi
  int v25; // eax
  bool v26; // r8
  int v27; // eax
  wchar_t *v28; // r15
  int v29; // r14d
  size_t v30; // r8
  int v31; // eax
  int v32; // eax
  BSTR v33; // rax
  OLECHAR *v34; // rsi
  int v35; // edi
  int v36; // eax
  int v37; // eax
  unsigned int v38; // edi
  void ***v40; // rbx
  BOOL v41; // esi
  void ***v42; // rcx
  void ***v43; // rcx
  IErrorInfo *v44; // rax
  IErrorInfo *v45; // rdi
  __int64 v46; // [rsp+68h] [rbp-1C0h] BYREF
  int v47; // [rsp+70h] [rbp-1B8h]
  unsigned int v48; // [rsp+78h] [rbp-1B0h]
  __int64 v49; // [rsp+80h] [rbp-1A8h] BYREF
  int v50; // [rsp+88h] [rbp-1A0h]
  OLECHAR *psz; // [rsp+90h] [rbp-198h] BYREF
  void *v52; // [rsp+98h] [rbp-190h] BYREF
  int v53; // [rsp+A0h] [rbp-188h]
  void *v54; // [rsp+A8h] [rbp-180h] BYREF
  int v55; // [rsp+B0h] [rbp-178h]
  void *v56; // [rsp+B8h] [rbp-170h] BYREF
  int v57; // [rsp+C0h] [rbp-168h]
  int v58; // [rsp+C8h] [rbp-160h]
  int v59; // [rsp+CCh] [rbp-15Ch] BYREF
  int *v60; // [rsp+D0h] [rbp-158h] BYREF
  int v61; // [rsp+D8h] [rbp-150h] BYREF
  void ***v62; // [rsp+E0h] [rbp-148h]
  wchar_t *v63; // [rsp+E8h] [rbp-140h]
  int v64; // [rsp+F0h] [rbp-138h]
  void **v65; // [rsp+F8h] [rbp-130h] BYREF
  __int64 v66; // [rsp+100h] [rbp-128h]
  __int64 v67; // [rsp+108h] [rbp-120h]
  void *v68; // [rsp+110h] [rbp-118h]
  BOOL v69; // [rsp+118h] [rbp-110h]
  void *lpMem; // [rsp+120h] [rbp-108h]
  int v71; // [rsp+128h] [rbp-100h]
  void **v72; // [rsp+130h] [rbp-F8h]
  void **v73; // [rsp+138h] [rbp-F0h]
  __int64 *v74; // [rsp+140h] [rbp-E8h]
  void **v75; // [rsp+148h] [rbp-E0h]
  __int64 *v76; // [rsp+150h] [rbp-D8h]
  __int64 *v77; // [rsp+158h] [rbp-D0h]
  wchar_t Destination[64]; // [rsp+170h] [rbp-B8h] BYREF

  psz = (OLECHAR *)a6;
  v48 = 0;
  v61 = 0;
  v62 = 0;
  try
  {
    v60 = &v61;
    v46 = 0;
    v47 = 0;
    v57 = 0;
    v72 = &v56;
    v56 = 0;
    v7 = CLRCreateInstanceDelayImport(&CLSID_CLRShimControlInternal, &IID_ICLRShimControlInternal, &v56);
    if ( v7 < 0 )
      ThrowHR(v7);
    v8 = v57;
    if ( v56 )
      v8 = 1;
    v57 = v8;
    v9 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v56 + 24LL))(v56, 1);
    if ( v9 < 0 )
      ThrowHR(v9);
    ConfigString_DontUse = (void *)REGUTIL::GetConfigString_DontUse_(L"DefaultVersion", 1, 7, 1);
    v68 = ConfigString_DontUse;
    v69 = ConfigString_DontUse != 0;
    v11 = (void *)REGUTIL::GetConfigString_DontUse_(L"Version", 1, 7, 1);
    lpMem = v11;
    v12 = 0;
    v71 = 0;
    if ( v11 )
    {
      v12 = 1;
      v71 = 1;
    }
    if ( !SysStringLen(a2) || ConfigString_DontUse || v11 )
    {
      v17 = 64;
      v58 = 64;
      if ( SysStringLen(a2) )
      {
        wcscpy_s(Destination, 0x40u, a2);
      }
      else
      {
        wcscpy_s(Destination, 0x40u, L"v4.0.0");
        v17 = 72;
        v58 = 72;
      }
      v55 = 0;
      v75 = &v54;
      v54 = 0;
      v18 = CLRCreateInstanceDelayImport(&CLSID_CLRMetaHostPolicy, &IID_ICLRMetaHostPolicy, &v54);
      if ( v18 < 0 )
        ThrowHR(v18);
      v19 = v55;
      if ( v54 )
        v19 = 1;
      v55 = v19;
      v59 = 64;
      v76 = &v46;
      v46 = 0;
      v20 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, _QWORD, wchar_t *, int *, _QWORD, _QWORD, _QWORD, GUID *, __int64 *))(*(_QWORD *)v54 + 24LL))(
              v54,
              v17,
              0,
              0,
              Destination,
              &v59,
              0,
              0,
              0,
              &IID_ICLRRuntimeInfo,
              &v46);
      if ( v20 < 0 )
        ThrowHR(v20);
      v21 = v47;
      if ( v46 )
        v21 = 1;
      v47 = v21;
      if ( v55 )
      {
        if ( v54 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v54 + 16LL))(v54);
        v55 = 0;
      }
    }
    else
    {
      v53 = 0;
      v73 = &v52;
      v52 = 0;
      v13 = CLRCreateInstanceDelayImport(&CLSID_CLRMetaHost, &IID_ICLRMetaHost, &v52);
      if ( v13 < 0 )
        ThrowHR(v13);
      v14 = v53;
      if ( v52 )
        v14 = 1;
      v53 = v14;
      v74 = &v46;
      v46 = 0;
      v15 = (*(__int64 (__fastcall **)(void *, unsigned __int16 *, GUID *, __int64 *))(*(_QWORD *)v52 + 24LL))(
              v52,
              a2,
              &IID_ICLRRuntimeInfo,
              &v46);
      if ( v15 < 0 )
        ThrowHR(v15);
      v16 = v47;
      if ( v46 )
        v16 = 1;
      v47 = v16;
      if ( v53 )
      {
        if ( v52 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v52 + 16LL))(v52);
        v53 = 0;
      }
    }
    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 104LL))(v46);
    if ( v22 < 0 )
      ThrowHR(v22);
    v60 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64, const char *, int **))(*(_QWORD *)v46 + 64LL))(
            v46,
            "NGenCreateNGenWorker",
            &v60);
    if ( v23 < 0 )
      ThrowHR(v23);
    if ( !v60 )
      ThrowHR(-2147467259);
    v24 = psz;
    v25 = ((__int64 (__fastcall *)(OLECHAR *, void ***, struct ICorSvcLogger *))v60)(psz, &g_LocalServerLifetime, a5);
    if ( v25 < 0 )
      ThrowHR(v25);
    if ( wszLocalAppData && wszPackage )
    {
      if ( !IsCLRSHGetKnownFolderPathAvailable() )
        ThrowHR(-2146230518);
      psz = 0;
      while ( !qword_18006FFE0 )
      {
        if ( bSHGetKnownFolderPathProbed || !IsCLRSHGetKnownFolderPathAvailable() )
          goto LABEL_47;
      }
      v27 = qword_18006FFE0(&FOLDERID_LocalAppData, 0, 0, &psz);
      if ( v27 < 0 )
        ThrowHR(v27);
LABEL_47:
      v28 = SysAllocString(psz);
      v63 = v28;
      v29 = 0;
      v64 = 0;
      if ( v28 )
      {
        v29 = 1;
        v64 = 1;
      }
      CoTaskMemFree(psz);
      psz = 0;
      v30 = -1;
      do
        ++v30;
      while ( wszLocalAppData[v30] );
      if ( _wcsnicmp(wszLocalAppData, v28, v30) )
        ThrowHR(-2146230518);
      v50 = 0;
      v77 = &v49;
      v49 = 0;
      v31 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v24)(*(_QWORD *)v24, &IID_ICorSvcAppX, &v49);
      if ( v31 < 0 )
        ThrowHR(v31);
      v32 = v50;
      if ( v49 )
        v32 = 1;
      v50 = v32;
      v33 = SysAllocString(wszPackage);
      v34 = v33;
      v65 = (void **)v33;
      v35 = 0;
      LODWORD(v66) = 0;
      if ( v33 )
      {
        v35 = 1;
        LODWORD(v66) = 1;
      }
      v36 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v49 + 24LL))(v49, v33);
      if ( v36 < 0 )
        ThrowHR(v36);
      v37 = (*(__int64 (__fastcall **)(__int64, wchar_t *))(*(_QWORD *)v49 + 32LL))(v49, v28);
      if ( v37 < 0 )
        ThrowHR(v37);
      if ( v35 )
      {
        SysFreeString(v34);
        LODWORD(v66) = 0;
      }
      if ( v50 )
      {
        if ( v49 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        v50 = 0;
      }
      if ( v29 )
      {
        SysFreeString(v28);
        v64 = 0;
      }
    }
    if ( v12 )
    {
      operator delete(lpMem);
      v71 = 0;
    }
    if ( v69 )
    {
      operator delete(v68);
      v69 = 0;
    }
    if ( v57 )
    {
      if ( v56 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v56 + 16LL))(v56);
      v57 = 0;
    }
    if ( v47 )
    {
      if ( v46 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      v47 = 0;
    }
  }
  catch ( ... )
  {
    v66 = 0;
    v65 = &DelegatingException::`vftable';
    v67 = -1;
    v40 = v62;
    v63 = (wchar_t *)v62;
    v41 = v62 != 0;
    v64 = v41;
    Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v61, 366, v26);
    v42 = &v65;
    if ( v40 )
      v42 = v40;
    v48 = ((__int64 (__fastcall *)(void ***))(*v42)[2])(v42);
    v43 = &v65;
    if ( v40 )
      v43 = v40;
    v44 = (IErrorInfo *)((__int64 (__fastcall *)(void ***))(*v43)[4])(v43);
    v45 = v44;
    if ( v44 )
    {
      SetErrorInfo(0, v44);
      ((void (__fastcall *)(IErrorInfo *))v45->lpVtbl->Release)(v45);
    }
    if ( v41 )
    {
      if ( v40 )
      {
        if ( !((unsigned int (__fastcall *)(void ***))(*v40)[10])(v40) )
          ((void (__fastcall *)(void ***, __int64))**v40)(v40, 5);
      }
      v64 = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)&v65);
  }
  v38 = v48;
  if ( (v61 & 2) != 0 && g_fpHandleStackOverflowAfterCatch )
    g_fpHandleStackOverflowAfterCatch();
  return v38;
}

```

## disassembly

```asm
0x18002e940  mov     r11, rsp
0x18002e943  mov     [r11+8], rbx
0x18002e947  mov     [r11+18h], rsi
0x18002e94b  push    rdi
0x18002e94c  push    r12
0x18002e94e  push    r13
0x18002e950  push    r14
0x18002e952  push    r15
0x18002e954  sub     rsp, 200h
0x18002e95b  mov     rax, cs:__security_cookie
0x18002e962  xor     rax, rsp
0x18002e965  mov     [rsp+228h+var_38], rax
0x18002e96d  mov     r15, rdx
0x18002e970  mov     r12, [rsp+228h+arg_20]
0x18002e978  mov     rax, [rsp+228h+arg_28]
0x18002e980  mov     [rsp+228h+psz], rax
0x18002e988  xor     ebx, ebx
0x18002e98a  mov     [rsp+228h+var_1C8], ebx
0x18002e98e  mov     [rsp+228h+var_1B0], ebx
0x18002e992  mov     [rsp+228h+var_150], ebx
0x18002e999  mov     [r11-148h], rbx
0x18002e9a0  lea     rax, [r11-150h]
0x18002e9a7  mov     [r11-158h], rax
0x18002e9ae  mov     [rsp+228h+var_1C0], rbx
0x18002e9b3  mov     [rsp+228h+var_1B8], ebx
0x18002e9b7  mov     [r11-170h], rbx
0x18002e9be  mov     [rsp+228h+var_168], ebx
0x18002e9c5  lea     rax, [r11-170h]
0x18002e9cc  mov     [r11-0F8h], rax
0x18002e9d3  cmp     [rsp+228h+var_168], ebx
0x18002e9da  jz      short loc_18002E9FC
0x18002e9dc  mov     rcx, [r11-170h]
0x18002e9e3  test    rcx, rcx
0x18002e9e6  jz      short loc_18002E9F5
0x18002e9e8  mov     rax, [rcx]
0x18002e9eb  mov     rax, [rax+10h]
0x18002e9ef  call    cs:__guard_dispatch_icall_fptr
0x18002e9f5  mov     [rsp+228h+var_168], ebx
0x18002e9fc  mov     [rsp+228h+var_170], rbx
0x18002ea04  mov     r13d, 1
0x18002ea0a  mov     [rsp+228h+var_1C8], r13d
0x18002ea0f  lea     r8, [rsp+228h+var_170]; void **
0x18002ea17  lea     rdx, IID_ICLRShimControlInternal; struct _GUID *
0x18002ea1e  lea     rcx, CLSID_CLRShimControlInternal; struct _GUID *
0x18002ea25  call    ?CLRCreateInstanceDelayImport@@YAJAEBU_GUID@@0PEAPEAX@Z; CLRCreateInstanceDelayImport(_GUID const &,_GUID const &,void * *)
0x18002ea2a  test    eax, eax
0x18002ea2c  js      loc_18002F1D0
0x18002ea32  mov     edi, r13d
0x18002ea35  and     edi, 0FFFFFFFEh
0x18002ea38  mov     [rsp+228h+var_1C8], edi
0x18002ea3c  mov     eax, [rsp+228h+var_168]
0x18002ea43  mov     rcx, [rsp+228h+var_170]
0x18002ea4b  test    rcx, rcx
0x18002ea4e  cmovnz  eax, r13d
0x18002ea52  mov     [rsp+228h+var_168], eax
0x18002ea59  mov     rax, [rcx]
0x18002ea5c  mov     edx, r13d
0x18002ea5f  mov     rax, [rax+18h]
0x18002ea63  call    cs:__guard_dispatch_icall_fptr
0x18002ea69  test    eax, eax
0x18002ea6b  js      loc_18002F1D8
0x18002ea71  mov     r9d, r13d
0x18002ea74  mov     esi, 7
0x18002ea79  mov     r8d, esi
0x18002ea7c  mov     edx, r13d
0x18002ea7f  lea     rcx, aDefaultversion; "DefaultVersion"
0x18002ea86  call    ?GetConfigString_DontUse_@REGUTIL@@SAPEAGPEBGHW4CORConfigLevel@1@H@Z; REGUTIL::GetConfigString_DontUse_(ushort const *,int,REGUTIL::CORConfigLevel,int)
0x18002ea8b  mov     r14, rax
0x18002ea8e  mov     [rsp+228h+var_118], rax
0x18002ea96  mov     [rsp+228h+var_110], ebx
0x18002ea9d  test    rax, rax
0x18002eaa0  jz      short loc_18002EAAA
0x18002eaa2  mov     [rsp+228h+var_110], r13d
0x18002eaaa  mov     r9d, r13d
0x18002eaad  mov     r8d, esi
0x18002eab0  mov     edx, r13d
0x18002eab3  lea     rcx, aVersion_0; "Version"
0x18002eaba  call    ?GetConfigString_DontUse_@REGUTIL@@SAPEAGPEBGHW4CORConfigLevel@1@H@Z; REGUTIL::GetConfigString_DontUse_(ushort const *,int,REGUTIL::CORConfigLevel,int)
0x18002eabf  mov     rsi, rax
0x18002eac2  mov     [rsp+228h+lpMem], rax
0x18002eaca  mov     r13d, ebx
0x18002eacd  mov     [rsp+228h+var_100], ebx
0x18002ead4  test    rax, rax
0x18002ead7  jz      short loc_18002EAE7
0x18002ead9  mov     r13d, 1
0x18002eadf  mov     [rsp+228h+var_100], r13d
0x18002eae7  mov     rcx, r15; pbstr
0x18002eaea  call    cs:__imp_SysStringLen
0x18002eaf0  test    eax, eax
0x18002eaf2  jz      loc_18002EC57
0x18002eaf8  test    r14, r14
0x18002eafb  jnz     loc_18002EC57
0x18002eb01  test    rsi, rsi
0x18002eb04  jnz     loc_18002EC57
0x18002eb0a  mov     [rsp+228h+var_190], rbx
0x18002eb12  mov     [rsp+228h+var_188], ebx
0x18002eb19  lea     rax, [rsp+228h+var_190]
0x18002eb21  mov     [rsp+228h+var_F0], rax
0x18002eb29  cmp     [rsp+228h+var_188], ebx
0x18002eb30  jz      short loc_18002EB53
0x18002eb32  mov     rcx, [rsp+228h+var_190]
0x18002eb3a  test    rcx, rcx
0x18002eb3d  jz      short loc_18002EB4C
0x18002eb3f  mov     rax, [rcx]
0x18002eb42  mov     rax, [rax+10h]
0x18002eb46  call    cs:__guard_dispatch_icall_fptr
0x18002eb4c  mov     [rsp+228h+var_188], ebx
0x18002eb53  mov     [rsp+228h+var_190], rbx
0x18002eb5b  or      edi, 8
0x18002eb5e  mov     [rsp+228h+var_1C8], edi
0x18002eb62  lea     r8, [rsp+228h+var_190]; void **
0x18002eb6a  lea     rdx, IID_ICLRMetaHost; struct _GUID *
0x18002eb71  lea     rcx, CLSID_CLRMetaHost; struct _GUID *
0x18002eb78  call    ?CLRCreateInstanceDelayImport@@YAJAEBU_GUID@@0PEAPEAX@Z; CLRCreateInstanceDelayImport(_GUID const &,_GUID const &,void * *)
0x18002eb7d  test    eax, eax
0x18002eb7f  js      loc_18002F1E0
0x18002eb85  and     edi, 0FFFFFFF7h
0x18002eb88  mov     [rsp+228h+var_1C8], edi
0x18002eb8c  mov     eax, [rsp+228h+var_188]
0x18002eb93  mov     rsi, [rsp+228h+var_190]
0x18002eb9b  test    rsi, rsi
0x18002eb9e  mov     r14d, 1
0x18002eba4  cmovnz  eax, r14d
0x18002eba8  mov     [rsp+228h+var_188], eax
0x18002ebaf  lea     rax, [rsp+228h+var_1C0]
0x18002ebb4  mov     [rsp+228h+var_E8], rax
0x18002ebbc  cmp     [rsp+228h+var_1B8], ebx
0x18002ebc0  jz      short loc_18002EBDD
0x18002ebc2  mov     rcx, [rsp+228h+var_1C0]
0x18002ebc7  test    rcx, rcx
0x18002ebca  jz      short loc_18002EBD9
0x18002ebcc  mov     rax, [rcx]
0x18002ebcf  mov     rax, [rax+10h]
0x18002ebd3  call    cs:__guard_dispatch_icall_fptr
0x18002ebd9  mov     [rsp+228h+var_1B8], ebx
0x18002ebdd  mov     [rsp+228h+var_1C0], rbx
0x18002ebe2  or      edi, 10h
0x18002ebe5  mov     [rsp+228h+var_1C8], edi
0x18002ebe9  mov     rax, [rsi]
0x18002ebec  lea     r9, [rsp+228h+var_1C0]
0x18002ebf1  lea     r8, IID_ICLRRuntimeInfo
0x18002ebf8  mov     rdx, r15
0x18002ebfb  mov     rcx, rsi
0x18002ebfe  mov     rax, [rax+18h]
0x18002ec02  call    cs:__guard_dispatch_icall_fptr
0x18002ec08  test    eax, eax
0x18002ec0a  js      loc_18002F1E8
0x18002ec10  and     edi, 0FFFFFFEFh
0x18002ec13  mov     [rsp+228h+var_1C8], edi
0x18002ec17  mov     eax, [rsp+228h+var_1B8]
0x18002ec1b  cmp     [rsp+228h+var_1C0], rbx
0x18002ec20  cmovnz  eax, r14d
0x18002ec24  mov     [rsp+228h+var_1B8], eax
0x18002ec28  cmp     [rsp+228h+var_188], ebx
0x18002ec2f  jz      short loc_18002EC52
0x18002ec31  mov     rcx, [rsp+228h+var_190]
0x18002ec39  test    rcx, rcx
0x18002ec3c  jz      short loc_18002EC4B
0x18002ec3e  mov     rax, [rcx]
0x18002ec41  mov     rax, [rax+10h]
0x18002ec45  call    cs:__guard_dispatch_icall_fptr
0x18002ec4b  mov     [rsp+228h+var_188], ebx
0x18002ec52  jmp     loc_18002EE2F
0x18002ec57  mov     esi, 40h ; '@'
0x18002ec5c  mov     r14d, esi
0x18002ec5f  mov     [rsp+228h+var_160], esi
0x18002ec66  mov     rcx, r15; pbstr
0x18002ec69  call    cs:__imp_SysStringLen
0x18002ec6f  mov     edx, esi; SizeInWords
0x18002ec71  lea     rcx, [rsp+228h+Destination]; Destination
0x18002ec79  test    eax, eax
0x18002ec7b  jz      short loc_18002EC88
0x18002ec7d  mov     r8, r15; Source
0x18002ec80  call    cs:__imp_wcscpy_s
0x18002ec86  jmp     short loc_18002ECA3
0x18002ec88  lea     r8, aV400; "v4.0.0"
0x18002ec8f  call    cs:__imp_wcscpy_s
0x18002ec95  mov     r14d, 48h ; 'H'
0x18002ec9b  mov     [rsp+228h+var_160], r14d
0x18002eca3  mov     [rsp+228h+var_180], rbx
0x18002ecab  mov     [rsp+228h+var_178], ebx
0x18002ecb2  lea     rax, [rsp+228h+var_180]
0x18002ecba  mov     [rsp+228h+var_E0], rax
0x18002ecc2  cmp     [rsp+228h+var_178], ebx
0x18002ecc9  jz      short loc_18002ECEC
0x18002eccb  mov     rcx, [rsp+228h+var_180]
0x18002ecd3  test    rcx, rcx
0x18002ecd6  jz      short loc_18002ECE5
0x18002ecd8  mov     rax, [rcx]
0x18002ecdb  mov     rax, [rax+10h]
0x18002ecdf  call    cs:__guard_dispatch_icall_fptr
0x18002ece5  mov     [rsp+228h+var_178], ebx
0x18002ecec  mov     [rsp+228h+var_180], rbx
0x18002ecf4  or      edi, 2
0x18002ecf7  mov     [rsp+228h+var_1C8], edi
0x18002ecfb  lea     r8, [rsp+228h+var_180]; void **
0x18002ed03  lea     rdx, IID_ICLRMetaHostPolicy; struct _GUID *
0x18002ed0a  lea     rcx, CLSID_CLRMetaHostPolicy; struct _GUID *
0x18002ed11  call    ?CLRCreateInstanceDelayImport@@YAJAEBU_GUID@@0PEAPEAX@Z; CLRCreateInstanceDelayImport(_GUID const &,_GUID const &,void * *)
0x18002ed16  test    eax, eax
0x18002ed18  js      loc_18002F1F0
0x18002ed1e  and     edi, 0FFFFFFFDh
0x18002ed21  mov     [rsp+228h+var_1C8], edi
0x18002ed25  mov     eax, [rsp+228h+var_178]
0x18002ed2c  mov     rsi, [rsp+228h+var_180]
0x18002ed34  test    rsi, rsi
0x18002ed37  mov     r15d, 1
0x18002ed3d  cmovnz  eax, r15d
0x18002ed41  mov     [rsp+228h+var_178], eax
0x18002ed48  mov     [rsp+228h+var_15C], 40h ; '@'
0x18002ed53  lea     rax, [rsp+228h+var_1C0]
0x18002ed58  mov     [rsp+228h+var_D8], rax
0x18002ed60  cmp     [rsp+228h+var_1B8], ebx
0x18002ed64  jz      short loc_18002ED81
0x18002ed66  mov     rcx, [rsp+228h+var_1C0]
0x18002ed6b  test    rcx, rcx
0x18002ed6e  jz      short loc_18002ED7D
0x18002ed70  mov     rax, [rcx]
0x18002ed73  mov     rax, [rax+10h]
0x18002ed77  call    cs:__guard_dispatch_icall_fptr
0x18002ed7d  mov     [rsp+228h+var_1B8], ebx
0x18002ed81  mov     [rsp+228h+var_1C0], rbx
0x18002ed86  or      edi, 4
0x18002ed89  mov     [rsp+228h+var_1C8], edi
0x18002ed8d  mov     rax, [rsi]
0x18002ed90  lea     rcx, [rsp+228h+var_1C0]
0x18002ed95  mov     [rsp+228h+var_1D8], rcx
0x18002ed9a  lea     rcx, IID_ICLRRuntimeInfo
0x18002eda1  mov     [rsp+228h+var_1E0], rcx
0x18002eda6  mov     [rsp+228h+var_1E8], rbx
0x18002edab  mov     [rsp+228h+var_1F0], rbx
0x18002edb0  mov     [rsp+228h+var_1F8], rbx
0x18002edb5  lea     rcx, [rsp+228h+var_15C]
0x18002edbd  mov     [rsp+228h+var_200], rcx
0x18002edc2  lea     rcx, [rsp+228h+Destination]
0x18002edca  mov     [rsp+228h+var_208], rcx
0x18002edcf  xor     r9d, r9d
0x18002edd2  xor     r8d, r8d
0x18002edd5  mov     edx, r14d
0x18002edd8  mov     rcx, rsi
0x18002eddb  mov     rax, [rax+18h]
0x18002eddf  call    cs:__guard_dispatch_icall_fptr
0x18002ede5  test    eax, eax
0x18002ede7  js      loc_18002F1F8
0x18002eded  and     edi, 0FFFFFFFBh
0x18002edf0  mov     [rsp+228h+var_1C8], edi
0x18002edf4  mov     eax, [rsp+228h+var_1B8]
0x18002edf8  cmp     [rsp+228h+var_1C0], rbx
0x18002edfd  cmovnz  eax, r15d
0x18002ee01  mov     [rsp+228h+var_1B8], eax
0x18002ee05  cmp     [rsp+228h+var_178], ebx
0x18002ee0c  jz      short loc_18002EE2F
0x18002ee0e  mov     rcx, [rsp+228h+var_180]
0x18002ee16  test    rcx, rcx
0x18002ee19  jz      short loc_18002EE28
0x18002ee1b  mov     rax, [rcx]
0x18002ee1e  mov     rax, [rax+10h]
0x18002ee22  call    cs:__guard_dispatch_icall_fptr
0x18002ee28  mov     [rsp+228h+var_178], ebx
0x18002ee2f  mov     rcx, [rsp+228h+var_1C0]
0x18002ee34  mov     rax, [rcx]
0x18002ee37  mov     rax, [rax+68h]
0x18002ee3b  call    cs:__guard_dispatch_icall_fptr
0x18002ee41  test    eax, eax
0x18002ee43  js      loc_18002F200
0x18002ee49  mov     [rsp+228h+var_158], rbx
0x18002ee51  mov     rcx, [rsp+228h+var_1C0]
0x18002ee56  mov     rax, [rcx]
0x18002ee59  lea     r8, [rsp+228h+var_158]
0x18002ee61  lea     rdx, aNgencreatengen; "NGenCreateNGenWorker"
0x18002ee68  mov     rax, [rax+40h]
0x18002ee6c  call    cs:__guard_dispatch_icall_fptr
0x18002ee72  test    eax, eax
0x18002ee74  js      loc_18002F207
0x18002ee7a  mov     rax, [rsp+228h+var_158]
0x18002ee82  test    rax, rax
0x18002ee85  jz      loc_18002F20E
0x18002ee8b  mov     r8, r12
0x18002ee8e  lea     rdx, ?g_LocalServerLifetime@@3VCLocalServerLifetime@@A; CLocalServerLifetime g_LocalServerLifetime
0x18002ee95  mov     rsi, [rsp+228h+psz]
0x18002ee9d  mov     rcx, rsi
0x18002eea0  call    cs:__guard_dispatch_icall_fptr
0x18002eea6  test    eax, eax
0x18002eea8  js      loc_18002F218
0x18002eeae  cmp     cs:?wszLocalAppData@@3PEBGEB, rbx; ushort const * const wszLocalAppData
0x18002eeb5  jz      loc_18002F100
0x18002eebb  cmp     cs:?wszPackage@@3PEBGEB, rbx; ushort const * const wszPackage
0x18002eec2  jz      loc_18002F100
0x18002eec8  call    ?IsCLRSHGetKnownFolderPathAvailable@@YA_NXZ; IsCLRSHGetKnownFolderPathAvailable(void)
0x18002eecd  test    al, al
0x18002eecf  jz      loc_18002F21F
0x18002eed5  mov     [rsp+228h+psz], rbx
0x18002eedd  mov     rax, cs:qword_18006FFE0
0x18002eee4  test    rax, rax
0x18002eee7  jz      short loc_18002EF0D
0x18002eee9  lea     r9, [rsp+228h+psz]
0x18002eef1  xor     r8d, r8d
0x18002eef4  xor     edx, edx
0x18002eef6  lea     rcx, FOLDERID_LocalAppData
0x18002eefd  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
