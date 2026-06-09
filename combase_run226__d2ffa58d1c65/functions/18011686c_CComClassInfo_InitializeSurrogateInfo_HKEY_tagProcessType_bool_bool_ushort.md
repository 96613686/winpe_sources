# CComClassInfo::InitializeSurrogateInfo(HKEY__ *,tagProcessType,bool,bool,ushort)

- ea: `0x18011686c`
- end: `0x1801170ac`
- name: `?InitializeSurrogateInfo@CComClassInfo@@AEAAJPEAUHKEY__@@W4tagProcessType@@_N2G@Z`
- size: `2112`
- prototype: `HRESULT __fastcall(CComClassInfo *this, HKEY__ *hKeyCLSID, tagProcessType processType, bool forceBothInprocAndOutofproc, bool selectDllHostArchitectureBasedOnDllArchitecture, unsigned __int16 defaultArchitectureForView)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010e818`

## callees

- `0x18000712c`
- `0x18000833c`
- `0x1800472a0`
- `0x18005c640`
- `0x180060bb0`
- `0x180062788`
- `0x180087534`
- `0x18008db2c`
- `0x1800a6f50`
- `0x1800bcd9c`
- `0x1800d92b8`
- `0x1800fc5e8`
- `0x18011686c`
- `0x180153648`
- `0x18015ddc0`
- `0x1801999b0`
- `0x18019a030`
- `0x18019a654`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116fd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116fd8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180116955`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180116b65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180116cb5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180116eb9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180116f7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180116955`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180116b65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180116cb5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180116eb9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180116f7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180116c59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180116c59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180116d6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180116d6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180116d52`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180116d52`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180116e4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180116e4a`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180116e3b`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180116e3b`

## string_xrefs

- `0x180116c1e`: `onecore\com\combase\catalog\class.cxx`
- `0x180116dc6`: `onecore\com\combase\catalog\class.cxx`
- `0x180116ff8`: `onecore\com\combase\catalog\class.cxx`
- `0x18011706e`: `onecore\com\combase\catalog\class.cxx`
- `0x180117059`: `CLSID:%ws %!HRESULT!`
- `0x180116ff1`: `CLSID:%ws %!WINERROR!`
- `0x180116c17`: `CLSID:%ws Binary architecture doesn't match registry view architecture. Surrogate:%ws %!HRESULT!`
- `0x180116c03`: `CComClassInfo::InitializeSurrogateInfo`
- `0x180117004`: `CComClassInfo::InitializeSurrogateInfo`
- `0x180117052`: `CComClassInfo::InitializeSurrogateInfo`

## pseudocode

```c
__int64 __fastcall CComClassInfo::InitializeSurrogateInfo(
        CComClassInfo *this,
        HKEY hKeyCLSID,
        tagProcessType processType,
        __int64 forceBothInprocAndOutofproc,
        bool selectDllHostArchitectureBasedOnDllArchitecture,
        unsigned __int16 defaultArchitectureForView)
{
  IUnknown *m_pProcessInfo; // rcx
  HRESULT ExeArchitectureFromRegString; // edi
  int v10; // r12d
  __int64 v11; // rsi
  unsigned __int64 v12; // rsi
  SIZE_T v13; // rax
  wchar_t *v14; // rax
  CComClassInfo *v15; // rcx
  wchar_t *v16; // r10
  __int64 v17; // rdi
  wchar_t *v18; // rcx
  __int64 v19; // rax
  unsigned __int64 v20; // rdx
  wchar_t *v21; // r8
  __int64 v22; // r9
  __int64 v23; // rcx
  wchar_t *v24; // rax
  __int64 v25; // rax
  const wchar_t *v26; // rcx
  unsigned __int64 v27; // rdx
  __int64 v28; // r8
  wchar_t *v29; // rax
  __int64 v30; // rcx
  _WORD *v31; // r10
  __int64 v32; // rax
  wchar_t *v33; // rcx
  unsigned __int64 v34; // rdx
  _WORD *v35; // r8
  CComClassInfo *v36; // r9
  _WORD *v37; // rax
  const wchar_t *v38; // rax
  _WORD *v39; // rax
  __int64 v40; // rax
  unsigned __int64 v41; // rdi
  SIZE_T v42; // rax
  unsigned __int64 v43; // kr00_8
  wchar_t *v44; // rax
  wchar_t *m_pwszSurrogateCommand; // r8
  __int64 v46; // rax
  unsigned __int64 v47; // rdi
  SIZE_T v48; // rax
  unsigned __int64 v49; // kr10_8
  wchar_t *v50; // rax
  int v51; // edx
  LSTATUS v52; // r12d
  BOOL v53; // esi
  wchar_t *m_pwszInprocServer32; // rcx
  HRESULT ModuleArchitecture; // eax
  int v56; // r12d
  BOOL v57; // ecx
  unsigned int SystemWow64Directory2W; // eax
  UINT SystemDirectoryW; // esi
  __int64 v60; // rcx
  unsigned __int64 v61; // rdi
  SIZE_T v62; // rax
  wchar_t *v63; // rax
  UINT v64; // edi
  SIZE_T v65; // rax
  wchar_t *v66; // rax
  DWORD LastError; // eax
  TraceLevel v68; // r9d
  unsigned __int64 cchSurrogateCommand; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *pszTemp; // [rsp+48h] [rbp-B8h] BYREF
  HKEY__ *hKeyInprocServer32; // [rsp+50h] [rbp-B0h] BYREF
  IComProcessInfo3 *pProcessInfo; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t wszGUID[40]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t wszSystemDirectory[264]; // [rsp+B0h] [rbp-50h] BYREF
  void *retaddr; // [rsp+308h] [rbp+208h]

  if ( processType != ProcessTypeLegacySurrogate )
  {
    ExeArchitectureFromRegString = 0;
    if ( processType != ProcessTypeComPlus )
      goto LABEL_121;
    if ( !g_bInSCM && !(_BYTE)forceBothInprocAndOutofproc )
      MicrosoftTelemetryAssertTriggeredNoArgs(this);
    hKeyInprocServer32 = 0;
    v52 = RegOpenKeyExW(hKeyCLSID, Com::Catalog::Constants::InprocServer32, 0, 0x20019u, &hKeyInprocServer32);
    v53 = v52 != 2;
    if ( hKeyInprocServer32 )
      RegCloseKey(hKeyInprocServer32);
    if ( v52 != 2 )
    {
      if ( selectDllHostArchitectureBasedOnDllArchitecture )
      {
        if ( !this->m_pwszInprocServer32 )
          CComClassInfo::InitializeForInprocActivations(this, v51, hKeyCLSID, 0, 0, 0);
        m_pwszInprocServer32 = this->m_pwszInprocServer32;
        if ( m_pwszInprocServer32 )
        {
          ModuleArchitecture = CoGetModuleArchitecture(
                                 m_pwszInprocServer32,
                                 &this->m_dwOutofprocServerBinaryArchitecture);
          v56 = ModuleArchitecture;
          if ( ModuleArchitecture < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              0x466u,
              "onecore\\com\\combase\\catalog\\class.cxx",
              ModuleArchitecture);
          v57 = 0;
          if ( v56 >= 0 )
            v57 = v53;
        }
        else
        {
          v57 = 0;
        }
LABEL_100:
        if ( !v57 )
          return (unsigned int)ExeArchitectureFromRegString;
        wszSystemDirectory[0] = 0;
        memset_0(&wszSystemDirectory[1], 0, 0x206u);
        if ( this->m_dwOutofprocServerBinaryArchitecture == GetNativeArchitecture() )
        {
          SystemDirectoryW = GetSystemDirectoryW(wszSystemDirectory, 0x103u);
          if ( SystemDirectoryW >= 0x103 )
            goto LABEL_117;
        }
        else
        {
          SystemWow64Directory2W = GetSystemWow64Directory2W(
                                     wszSystemDirectory,
                                     259,
                                     LOWORD(this->m_dwOutofprocServerBinaryArchitecture));
          SystemDirectoryW = SystemWow64Directory2W < 0x103 ? SystemWow64Directory2W : 0;
        }
        if ( SystemDirectoryW )
        {
          if ( wszSystemDirectory[SystemDirectoryW - 1] != 92 )
          {
            v60 = SystemDirectoryW++;
            wszSystemDirectory[v60] = 92;
            if ( 2 * (unsigned __int64)SystemDirectoryW >= 0x208 )
              _report_rangecheckfailure();
            wszSystemDirectory[SystemDirectoryW] = 0;
          }
          v61 = SystemDirectoryW + 62LL;
          v62 = 2 * v61;
          cchSurrogateCommand = v61;
          if ( !is_mul_ok(v61, 2u) )
            v62 = -1;
          v63 = (wchar_t *)HeapAlloc(g_hHeap, 0, v62);
          this->m_pwszSurrogateCommand = v63;
          if ( !v63 )
            goto LABEL_116;
          pszTemp = v63;
          StringCchCopyExW(v63, SystemDirectoryW + 62LL, wszSystemDirectory, &pszTemp, &cchSurrogateCommand, 0);
          StringCchCopyExW(pszTemp, cchSurrogateCommand, g_wszDllHostSlashProcessId, &pszTemp, &cchSurrogateCommand, 0);
          wStringFromGUID2(&this->m_guidProcessId, wszGUID, 39);
          ExeArchitectureFromRegString = StringCchCopyExW(
                                           pszTemp,
                                           cchSurrogateCommand,
                                           wszGUID,
                                           &pszTemp,
                                           &cchSurrogateCommand,
                                           0);
          if ( ExeArchitectureFromRegString >= 0 )
          {
            v64 = SystemDirectoryW + 12;
            v65 = 2LL * (SystemDirectoryW + 12);
            if ( !is_mul_ok(SystemDirectoryW + 12, 2u) )
              v65 = -1;
            v66 = (wchar_t *)HeapAlloc(g_hHeap, 0, v65);
            this->m_pwszServerExecutable = v66;
            if ( v66 )
            {
              StringCchCopyW(v66, v64, wszSystemDirectory);
              ExeArchitectureFromRegString = StringCchCatW(this->m_pwszServerExecutable, v64, g_wszDllHost);
              goto LABEL_121;
            }
LABEL_116:
            ExeArchitectureFromRegString = -2147024882;
          }
LABEL_121:
          this->m_clsctx |= 4u;
LABEL_122:
          if ( ExeArchitectureFromRegString == -2147024894 )
          {
            return 0;
          }
          else if ( ExeArchitectureFromRegString < 0
                 && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS)) )
          {
            ComTraceMessageT<unsigned short *,long>(
              "onecore\\com\\combase\\catalog\\class.cxx",
              "CComClassInfo::InitializeSurrogateInfo",
              1355,
              ERRORS,
              L"CLSID:%ws %!HRESULT!",
              this->m_wszClsidString,
              ExeArchitectureFromRegString);
          }
          return (unsigned int)ExeArchitectureFromRegString;
        }
LABEL_117:
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        {
          LastError = GetLastError();
          ComTraceMessageT<unsigned short *,unsigned long>(
            "onecore\\com\\combase\\catalog\\class.cxx",
            "CComClassInfo::InitializeSurrogateInfo",
            1227,
            v68,
            L"CLSID:%ws %!WINERROR!",
            this->m_wszClsidString,
            LastError);
        }
        goto LABEL_121;
      }
      this->m_dwOutofprocServerBinaryArchitecture = defaultArchitectureForView;
    }
    v57 = v52 != 2;
    goto LABEL_100;
  }
  m_pProcessInfo = this->m_pProcessInfo;
  pProcessInfo = 0;
  if ( !m_pProcessInfo )
    return (unsigned int)-2147467259;
  ExeArchitectureFromRegString = ((__int64 (__fastcall *)(IUnknown *, GUID *, IComProcessInfo3 **, __int64))m_pProcessInfo->QueryInterface)(
                                   m_pProcessInfo,
                                   &GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680,
                                   &pProcessInfo,
                                   forceBothInprocAndOutofproc);
  if ( ExeArchitectureFromRegString >= 0 )
  {
    cchSurrogateCommand = 0;
    LODWORD(pszTemp) = 0;
    v10 = 1;
    ExeArchitectureFromRegString = pProcessInfo->GetCommandPathAndDebug(
                                     pProcessInfo,
                                     (int *)&pszTemp,
                                     (wchar_t **)&cchSurrogateCommand);
    if ( ExeArchitectureFromRegString < 0 )
      goto LABEL_78;
    if ( (_DWORD)pszTemp )
    {
      v40 = -1;
      do
        ++v40;
      while ( *(_WORD *)(cchSurrogateCommand + 2 * v40) );
      v41 = v40 + 1;
      v43 = v40 + 1;
      v42 = 2 * (v40 + 1);
      if ( !is_mul_ok(v43, 2u) )
        v42 = -1;
      v44 = (wchar_t *)HeapAlloc(g_hHeap, 0, v42);
      this->m_pwszSurrogateCommand = v44;
      if ( !v44 )
        goto LABEL_77;
      ExeArchitectureFromRegString = StringCchCopyW(v44, v41, (const wchar_t *)cchSurrogateCommand);
    }
    else
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(cchSurrogateCommand + 2 * v11) );
      v12 = v11 + 51;
      v13 = 2 * v12;
      if ( !is_mul_ok(v12, 2u) )
        v13 = -1;
      v14 = (wchar_t *)HeapAlloc(g_hHeap, 0, v13);
      this->m_pwszSurrogateCommand = v14;
      v16 = v14;
      if ( v14 )
      {
        v17 = 2147483646;
        if ( !v12 )
          goto LABEL_30;
        if ( v12 <= 0x7FFFFFFF )
        {
          v18 = (wchar_t *)cchSurrogateCommand;
          v19 = 2147483646;
          v20 = v12;
          v21 = v16;
          v22 = 0;
          do
          {
            if ( !v19 )
              break;
            if ( !*v18 )
              break;
            *v21++ = *v18++;
            --v19;
            ++v22;
            --v20;
          }
          while ( v20 );
          v23 = v22 - 1;
          v24 = v21 - 1;
          if ( v20 )
          {
            v23 = v22;
            v24 = v21;
          }
          v12 -= v23;
          *v24 = 0;
          v16 += v23;
          if ( !v12 )
          {
LABEL_30:
            wStringFromGUID2(&this->m_clsid, wszGUID, 39);
            if ( v12 )
            {
              if ( v12 <= 0x7FFFFFFF )
              {
                v32 = 2147483646;
                v33 = wszGUID;
                v34 = v12;
                v35 = v31;
                v36 = 0;
                do
                {
                  if ( !v32 )
                    break;
                  if ( !*v33 )
                    break;
                  *v35++ = *v33++;
                  --v32;
                  v36 = (CComClassInfo *)((char *)v36 + 1);
                  --v34;
                }
                while ( v34 );
                v15 = (CComClassInfo *)((char *)v36 - 1);
                v37 = v35 - 1;
                if ( v34 )
                {
                  v15 = v36;
                  v37 = v35;
                }
                v12 -= (unsigned __int64)v15;
                *v37 = 0;
                v31 += (__int64)v15;
                if ( !v12 )
                  goto LABEL_48;
              }
              else
              {
                *v31 = 0;
              }
              if ( v12 <= 0x7FFFFFFF )
              {
                v38 = g_wszEmbedding;
                do
                {
                  if ( !v17 )
                    break;
                  v15 = (CComClassInfo *)*v38;
                  if ( !(_WORD)v15 )
                    break;
                  *v31 = (_WORD)v15;
                  ++v38;
                  ++v31;
                  --v17;
                  --v12;
                }
                while ( v12 );
                v39 = v31 - 1;
                if ( v12 )
                  v39 = v31;
                ExeArchitectureFromRegString = v12 == 0 ? 0x8007007A : 0;
                *v39 = 0;
                goto LABEL_57;
              }
            }
LABEL_48:
            ExeArchitectureFromRegString = -2147024809;
            if ( v12 )
              *v31 = 0;
            goto LABEL_57;
          }
        }
        else
        {
          *v14 = 0;
        }
        if ( v12 > 0x7FFFFFFF )
        {
          *v16 = 0;
        }
        else
        {
          v25 = 2147483646;
          v26 = L" ";
          v27 = v12;
          v28 = 0;
          do
          {
            if ( !v25 )
              break;
            if ( !*v26 )
              break;
            *v16++ = *v26++;
            --v25;
            ++v28;
            --v27;
          }
          while ( v27 );
          v29 = v16 - 1;
          v30 = v28 - 1;
          if ( v27 )
          {
            v29 = v16;
            v30 = v28;
          }
          v12 -= v30;
          *v29 = 0;
        }
        goto LABEL_30;
      }
      ExeArchitectureFromRegString = -2147024882;
    }
LABEL_57:
    if ( ExeArchitectureFromRegString < 0 )
      goto LABEL_78;
    ExeArchitectureFromRegString = CComClassInfo::GetExeArchitectureFromRegString(
                                     v15,
                                     this->m_pwszSurrogateCommand,
                                     &this->m_dwOutofprocServerBinaryArchitecture);
    if ( ExeArchitectureFromRegString < 0 )
      goto LABEL_78;
    if ( defaultArchitectureForView && this->m_dwOutofprocServerBinaryArchitecture != defaultArchitectureForView )
    {
      ExeArchitectureFromRegString = -2147221164;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(WARNING) )
        ComTraceMessageT<unsigned short *,unsigned short *,long>(
          "onecore\\com\\combase\\catalog\\class.cxx",
          "CComClassInfo::InitializeSurrogateInfo",
          1028,
          WARNING,
          L"CLSID:%ws Binary architecture doesn't match registry view architecture. Surrogate:%ws %!HRESULT!",
          this->m_wszClsidString,
          this->m_pwszSurrogateCommand,
          -2147221164);
      m_pwszSurrogateCommand = this->m_pwszSurrogateCommand;
      v10 = 0;
      if ( m_pwszSurrogateCommand && m_pwszSurrogateCommand != g_wszEmptyString )
        HeapFree(g_hHeap, 0, m_pwszSurrogateCommand);
      this->m_pwszSurrogateCommand = 0;
LABEL_78:
      pProcessInfo->Release(pProcessInfo);
      if ( !v10 )
        goto LABEL_122;
      goto LABEL_121;
    }
    hKeyInprocServer32 = 0;
    if ( pProcessInfo->GetSurrogateServerExecutable(pProcessInfo, (wchar_t **)&hKeyInprocServer32) < 0 )
    {
      ExeArchitectureFromRegString = 0;
      goto LABEL_78;
    }
    v46 = -1;
    do
      ++v46;
    while ( *((_WORD *)hKeyInprocServer32 + v46) );
    v47 = v46 + 1;
    v49 = v46 + 1;
    v48 = 2 * (v46 + 1);
    if ( !is_mul_ok(v49, 2u) )
      v48 = -1;
    v50 = (wchar_t *)HeapAlloc(g_hHeap, 0, v48);
    this->m_pwszServerExecutable = v50;
    if ( v50 )
    {
      ExeArchitectureFromRegString = StringCchCopyW(v50, v47, (const wchar_t *)hKeyInprocServer32);
      goto LABEL_78;
    }
LABEL_77:
    ExeArchitectureFromRegString = -2147024882;
    goto LABEL_78;
  }
  return (unsigned int)ExeArchitectureFromRegString;
}

```

## disassembly

```asm
0x18011686c  mov     [rsp-8+arg_10], rbx
0x180116871  push    rbp
0x180116872  push    rsi
0x180116873  push    rdi
0x180116874  push    r12
0x180116876  push    r13
0x180116878  push    r14
0x18011687a  push    r15
0x18011687c  lea     rbp, [rsp-1D0h]
0x180116884  sub     rsp, 2D0h
0x18011688b  mov     rax, cs:__security_cookie
0x180116892  xor     rax, rsp
0x180116895  mov     [rbp+200h+var_40], rax
0x18011689c  xor     ebx, ebx
0x18011689e  mov     r13, hKeyCLSID
0x1801168a1  mov     r14, this
0x1801168a4  cmp     processType, 3
0x1801168a8  jnz     loc_180116D0D
0x1801168ae  mov     this, [this+68h]
0x1801168b2  mov     [rsp+300h+pProcessInfo], rbx
0x1801168b7  test    this, this
0x1801168ba  jz      loc_180116D03
0x1801168c0  mov     rax, [this]
0x1801168c3  lea     r8, [rsp+300h+pProcessInfo]
0x1801168c8  lea     hKeyCLSID, _GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680
0x1801168cf  mov     rax, [rax]
0x1801168d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801168d7  mov     edi, eax
0x1801168d9  test    eax, eax
0x1801168db  js      $Cleanup_7
0x1801168e1  mov     this, [rsp+300h+pProcessInfo]
0x1801168e6  lea     r8, [rsp+300h+cchSurrogateCommand]
0x1801168eb  mov     [rsp+300h+cchSurrogateCommand], rbx
0x1801168f0  lea     hKeyCLSID, [rsp+300h+pszTemp]
0x1801168f5  mov     dword ptr [rsp+300h+pszTemp], ebx
0x1801168f9  lea     r12d, [rbx+1]
0x1801168fd  mov     rax, [this]
0x180116900  mov     rax, [rax+0D0h]
0x180116907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011690c  mov     edi, eax
0x18011690e  test    eax, eax
0x180116910  js      loc_180116CE4
0x180116916  or      r13, 0FFFFFFFFFFFFFFFFh
0x18011691a  cmp     dword ptr [rsp+300h+pszTemp], ebx
0x18011691e  jnz     loc_180116B34
0x180116924  mov     rax, [rsp+300h+cchSurrogateCommand]
0x180116929  mov     rsi, r13
0x18011692c  inc     rsi
0x18011692f  cmp     [rax+rsi*2], bx
0x180116933  jnz     short loc_18011692C
0x180116935  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18011693c  mov     r15d, 2
0x180116942  mov     eax, r15d
0x180116945  add     rsi, 33h ; '3'
0x180116949  mul     rsi
0x18011694c  cmovb   rax, r13
0x180116950  xor     edx, edx; dwFlags
0x180116952  mov     r8, rax; dwBytes
0x180116955  call    cs:__imp_HeapAlloc
0x18011695b  mov     [r14+120h], rax
0x180116962  mov     r10, rax
0x180116965  test    rax, rax
0x180116968  jz      loc_180116B2D
0x18011696e  mov     edi, 7FFFFFFEh
0x180116973  test    rsi, rsi
0x180116976  jz      loc_180116A4E
0x18011697c  cmp     rsi, 7FFFFFFFh
0x180116983  jbe     short loc_18011698A
0x180116985  mov     [rax], bx
0x180116988  jmp     short loc_1801169E1
0x18011698a  mov     this, [rsp+300h+cchSurrogateCommand]
0x18011698f  mov     rax, rdi
0x180116992  mov     hKeyCLSID, rsi
0x180116995  mov     r8, r10
0x180116998  mov     r9, rbx
0x18011699b  test    rax, rax
0x18011699e  jz      short loc_1801169BF
0x1801169a0  movzx   r11d, word ptr [this]
0x1801169a4  test    r11w, r11w
0x1801169a8  jz      short loc_1801169BF
0x1801169aa  mov     [r8], r11w
0x1801169ae  add     this, r15
0x1801169b1  add     r8, r15
0x1801169b4  sub     rax, r12
0x1801169b7  add     r9, r12
0x1801169ba  sub     hKeyCLSID, r12
0x1801169bd  jnz     short loc_18011699B
0x1801169bf  test    hKeyCLSID, hKeyCLSID
0x1801169c2  lea     this, [r9-1]
0x1801169c6  lea     rax, [r8-2]
0x1801169ca  cmovnz  this, r9
0x1801169ce  cmovnz  rax, r8
0x1801169d2  sub     rsi, this
0x1801169d5  mov     [rax], bx
0x1801169d8  lea     r10, [r10+this*2]
0x1801169dc  test    rsi, rsi
0x1801169df  jz      short loc_180116A4E
0x1801169e1  cmp     rsi, 7FFFFFFFh
0x1801169e8  ja      short loc_180116A45
0x1801169ea  test    rsi, rsi
0x1801169ed  jz      short loc_180116A4E
0x1801169ef  mov     rax, rdi
0x1801169f2  lea     this, SubStr; " "
0x1801169f9  mov     hKeyCLSID, rsi
0x1801169fc  mov     r8, rbx
0x1801169ff  mov     r11, r10
0x180116a02  test    rax, rax
0x180116a05  jz      short loc_180116A26
0x180116a07  movzx   r9d, word ptr [this]
0x180116a0b  test    r9w, r9w
0x180116a0f  jz      short loc_180116A26
0x180116a11  mov     [r10], r9w
0x180116a15  add     this, r15
0x180116a18  add     r10, r15
0x180116a1b  sub     rax, r12
0x180116a1e  add     r8, r12
0x180116a21  sub     hKeyCLSID, r12
0x180116a24  jnz     short loc_180116A02
0x180116a26  test    hKeyCLSID, hKeyCLSID
0x180116a29  lea     rax, [r10-2]
0x180116a2d  lea     this, [r8-1]
0x180116a31  cmovnz  rax, r10
0x180116a35  cmovnz  this, r8
0x180116a39  sub     rsi, this
0x180116a3c  mov     [rax], bx
0x180116a3f  lea     r10, [r11+this*2]
0x180116a43  jmp     short loc_180116A4E
0x180116a45  test    rsi, rsi
0x180116a48  jz      short loc_180116A4E
0x180116a4a  mov     [r10], bx
0x180116a4e  lea     this, [r14+40h]; rguid
0x180116a52  mov     processType, 27h ; '''; cchMax
0x180116a58  lea     hKeyCLSID, [rsp+300h+wszGUID]; lpsz
0x180116a5d  call    ?wStringFromGUID2@@YAHAEBU_GUID@@PEAGH@Z; wStringFromGUID2(_GUID const &,ushort *,int)
0x180116a62  test    rsi, rsi
0x180116a65  jz      loc_180116B1D
0x180116a6b  cmp     rsi, 7FFFFFFFh
0x180116a72  jbe     short loc_180116A7A
0x180116a74  mov     [r10], bx
0x180116a78  jmp     short loc_180116AD1
0x180116a7a  mov     rax, rdi
0x180116a7d  lea     this, [rsp+300h+wszGUID]
0x180116a82  mov     hKeyCLSID, rsi
0x180116a85  mov     r8, r10
0x180116a88  mov     r9, rbx
0x180116a8b  test    rax, rax
0x180116a8e  jz      short loc_180116AAF
0x180116a90  movzx   r11d, word ptr [this]
0x180116a94  test    r11w, r11w
0x180116a98  jz      short loc_180116AAF
0x180116a9a  mov     [r8], r11w
0x180116a9e  add     this, r15
0x180116aa1  add     r8, r15
0x180116aa4  sub     rax, r12
0x180116aa7  add     r9, r12
0x180116aaa  sub     hKeyCLSID, r12
0x180116aad  jnz     short loc_180116A8B
0x180116aaf  test    hKeyCLSID, hKeyCLSID
0x180116ab2  lea     this, [r9-1]
0x180116ab6  lea     rax, [r8-2]
0x180116aba  cmovnz  this, r9
0x180116abe  cmovnz  rax, r8
0x180116ac2  sub     rsi, this
0x180116ac5  mov     [rax], bx
0x180116ac8  lea     r10, [r10+this*2]
0x180116acc  test    rsi, rsi
0x180116acf  jz      short loc_180116B1D
0x180116ad1  cmp     rsi, 7FFFFFFFh
0x180116ad8  ja      short loc_180116B1D
0x180116ada  lea     rax, ?g_wszEmbedding@@3QBGB; ushort const near * const g_wszEmbedding
0x180116ae1  test    rdi, rdi
0x180116ae4  jz      short loc_180116B00
0x180116ae6  movzx   ecx, word ptr [rax]
0x180116ae9  test    cx, cx
0x180116aec  jz      short loc_180116B00
0x180116aee  mov     [r10], cx
0x180116af2  add     rax, r15
0x180116af5  add     r10, r15
0x180116af8  sub     rdi, r12
0x180116afb  sub     rsi, r12
0x180116afe  jnz     short loc_180116AE1
0x180116b00  test    rsi, rsi
0x180116b03  lea     rax, [r10-2]
0x180116b07  cmovnz  rax, r10
0x180116b0b  neg     rsi
0x180116b0e  sbb     edi, edi
0x180116b10  not     edi
0x180116b12  and     edi, 8007007Ah
0x180116b18  mov     [rax], bx
0x180116b1b  jmp     short loc_180116B8D
0x180116b1d  mov     edi, 80070057h
0x180116b22  test    rsi, rsi
0x180116b25  jz      short loc_180116B8D
0x180116b27  mov     [r10], bx
0x180116b2b  jmp     short loc_180116B8D
0x180116b2d  mov     edi, 8007000Eh
0x180116b32  jmp     short loc_180116B8D
0x180116b34  mov     this, [rsp+300h+cchSurrogateCommand]
0x180116b39  mov     rax, r13
0x180116b3c  inc     rax
0x180116b3f  cmp     [this+rax*2], bx
0x180116b43  jnz     short loc_180116B3C
0x180116b45  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180116b4c  lea     rdi, [rax+1]
0x180116b50  mov     r15d, 2
0x180116b56  mov     eax, r15d
0x180116b59  mul     rdi
0x180116b5c  cmovb   rax, r13
0x180116b60  xor     edx, edx; dwFlags
0x180116b62  mov     r8, rax; dwBytes
0x180116b65  call    cs:__imp_HeapAlloc
0x180116b6b  mov     [r14+120h], rax
0x180116b72  test    rax, rax
0x180116b75  jz      loc_180116CDF
0x180116b7b  mov     r8, [rsp+300h+cchSurrogateCommand]; pszSrc
0x180116b80  mov     hKeyCLSID, rdi; cchDest
0x180116b83  mov     this, rax; pszDest
0x180116b86  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180116b8b  mov     edi, eax
0x180116b8d  test    edi, edi
0x180116b8f  js      loc_180116CE4
0x180116b95  mov     hKeyCLSID, [r14+120h]; pwszRegString
0x180116b9c  lea     rsi, [r14+130h]
0x180116ba3  mov     r8, rsi; pExeArchitecture
0x180116ba6  call    ?GetExeArchitectureFromRegString@CComClassInfo@@AEAAJPEBGPEAK@Z; CComClassInfo::GetExeArchitectureFromRegString(ushort const *,ulong *)
0x180116bab  mov     edi, eax
0x180116bad  test    eax, eax
0x180116baf  js      loc_180116CE4
0x180116bb5  cmp     [rbp+200h+arg_28], bx
0x180116bbc  jz      loc_180116C68
0x180116bc2  movzx   eax, [rbp+200h+arg_28]
0x180116bc9  cmp     [rsi], eax
0x180116bcb  jz      loc_180116C68
0x180116bd1  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180116bd7  mov     edi, 80040154h
0x180116bdc  test    eax, eax
0x180116bde  jnz     short loc_180116BF4
0x180116be0  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180116be6  jz      short loc_180116C35
0x180116be8  mov     ecx, r12d; level
0x180116beb  call    IsWppLevelEnabled
0x180116bf0  test    al, al
0x180116bf2  jz      short loc_180116C35
0x180116bf4  mov     rax, [r14+120h]
0x180116bfb  lea     this, [r14+70h]
0x180116bff  mov     [rsp+300h+var_2C8], edi; <args_2>
0x180116c03  lea     hKeyCLSID, aCcomclassinfoI_1; "CComClassInfo::InitializeSurrogateInfo"
0x180116c0a  mov     qword ptr [rsp+300h+var_2D0], rax; <args_1>
0x180116c0f  mov     r9d, r12d; level
0x180116c12  mov     [rsp+300h+var_2D8], this; <args_0>
0x180116c17  lea     rax, aClsidWsBinaryA; "CLSID:%ws Binary architecture doesn't m"...
0x180116c1e  lea     this, aOnecoreComComb_119; "onecore\\com\\combase\\catalog\\class.c"...
0x180116c25  mov     [rsp+300h+format], rax; format
0x180116c2a  mov     processType, 404h; line
0x180116c30  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x180116c35  mov     r8, [r14+120h]; lpMem
0x180116c3c  mov     r12d, ebx
0x180116c3f  test    r8, r8
0x180116c42  jz      short loc_180116C5F
0x180116c44  lea     rax, ?g_wszEmptyString@@3QBGB; ushort const near * const g_wszEmptyString
0x180116c4b  cmp     r8, rax
0x180116c4e  jz      short loc_180116C5F
0x180116c50  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180116c57  xor     edx, edx; dwFlags
0x180116c59  call    cs:__imp_HeapFree
0x180116c5f  mov     [r14+120h], rbx
0x180116c66  jmp     short loc_180116CE4
0x180116c68  mov     this, [rsp+300h+pProcessInfo]
0x180116c6d  lea     hKeyCLSID, [rsp+300h+hKeyInprocServer32]
0x180116c72  mov     [rsp+300h+hKeyInprocServer32], rbx
0x180116c77  mov     rax, [this]
0x180116c7a  mov     rax, [rax+0D8h]
0x180116c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116c86  test    eax, eax
0x180116c88  js      short loc_180116CDB
0x180116c8a  mov     this, [rsp+300h+hKeyInprocServer32]
0x180116c8f  mov     rax, r13
0x180116c92  inc     rax
0x180116c95  cmp     [this+rax*2], bx
0x180116c99  jnz     short loc_180116C92
0x180116c9b  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180116ca2  lea     rdi, [rax+1]
0x180116ca6  mov     rax, r15
0x180116ca9  mul     rdi
0x180116cac  cmovb   rax, r13
0x180116cb0  xor     edx, edx; dwFlags
0x180116cb2  mov     r8, rax; dwBytes
0x180116cb5  call    cs:__imp_HeapAlloc
0x180116cbb  mov     [r14+128h], rax
0x180116cc2  test    rax, rax
0x180116cc5  jz      short loc_180116CDF
0x180116cc7  mov     r8, [rsp+300h+hKeyInprocServer32]; pszSrc
0x180116ccc  mov     hKeyCLSID, rdi; cchDest
0x180116ccf  mov     this, rax; pszDest
0x180116cd2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180116cd7  mov     edi, eax
0x180116cd9  jmp     short loc_180116CE4
0x180116cdb  mov     edi, ebx
0x180116cdd  jmp     short loc_180116CE4
0x180116cdf  mov     edi, 8007000Eh
  ... truncated ...
```
