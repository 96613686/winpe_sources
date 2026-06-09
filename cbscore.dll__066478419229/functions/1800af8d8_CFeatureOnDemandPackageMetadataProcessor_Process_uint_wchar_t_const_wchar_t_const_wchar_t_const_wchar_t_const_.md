# CFeatureOnDemandPackageMetadataProcessor::Process(uint,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ICbsUIHandler *,_CbsRequiredAction *,wchar_t * *)

- ea: `0x1800af8d8`
- end: `0x1800b0082`
- name: `?Process@CFeatureOnDemandPackageMetadataProcessor@@UEAAJIPEB_W000PEAUICbsUIHandler@@PEAW4_CbsRequiredAction@@PEAPEA_W@Z`
- size: `1962`
- prototype: `__int64 __fastcall(CFeatureOnDemandPackageMetadataProcessor *__hidden this, unsigned int, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, struct ICbsUIHandler *, enum _CbsRequiredAction *, wchar_t **)`
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x18019420c`
- `0x180194ae0`
- `0x180197ea0`
- `0x18019a510`

## callees

- `0x180013250`
- `0x180015420`
- `0x180019bdc`
- `0x180019c10`
- `0x1800261e0`
- `0x180056e00`
- `0x180057c28`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad1f0`
- `0x1800af8d8`
- `0x1800bd218`
- `0x1800eb920`
- `0x1801c0d60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800afcc1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800afcc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afe45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aff7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afe45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aff7c`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x1800afd2a`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x1800aff68`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x1800afd2a`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x1800aff68`

## string_xrefs

- `0x1800affa7`: `Failed to copy action list '{}' to store`
- `0x1800afe6c`: `Failed to copy '{}' to store: {}`
- `0x1800aff23`: `ActionList.xml`
- `0x1800afa9c`: `Failed to get package store directory`
- `0x1800af9bd`: `Invalid argument: szSandboxPath`
- `0x1800afbdb`: `ActionList returns but it contains empty install action`
- `0x1800afde3`: `Failed to call DirectoryfromPath`
- `0x1800afd6f`: `Failed to create directory: {}`
- `0x1800af947`: `Invalid argument: szActionListPath`

## pseudocode

```c
__int64 __fastcall CFeatureOnDemandPackageMetadataProcessor::Process(
        CFeatureOnDemandPackageMetadataProcessor *this,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        struct ICbsUIHandler *a7,
        enum _CbsRequiredAction *a8,
        wchar_t **a9)
{
  int v11; // ebx
  int v12; // edx
  __int64 v13; // rdx
  int v15; // edx
  const wchar_t *v16; // r8
  CCbsSession *v17; // rcx
  int FeatureOnDemandMetadataFolder; // eax
  int v19; // edx
  __int64 v20; // rdx
  int v21; // eax
  int v22; // edx
  unsigned __int64 v23; // r9
  int v24; // eax
  int v25; // eax
  __int64 v26; // rbx
  __int64 v27; // rcx
  int v28; // edx
  char v29; // r14
  __int64 i; // rbx
  int v31; // eax
  int v32; // edi
  wchar_t *v33; // rdi
  int v34; // esi
  wchar_t *v35; // rsi
  int Directory; // r14d
  wchar_t *v37; // rsi
  int v38; // edx
  int v39; // edx
  signed int LastError; // ebx
  int v41; // edx
  unsigned int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // rdx
  int v45; // eax
  int v46; // edx
  unsigned int v47; // eax
  unsigned int v48; // [rsp+20h] [rbp-89h]
  wchar_t *v49; // [rsp+30h] [rbp-79h] BYREF
  int v50[2]; // [rsp+38h] [rbp-71h] BYREF
  wchar_t *Str; // [rsp+40h] [rbp-69h] BYREF
  wchar_t *v52; // [rsp+48h] [rbp-61h] BYREF
  wchar_t *v53; // [rsp+50h] [rbp-59h] BYREF
  wchar_t *v54; // [rsp+58h] [rbp-51h] BYREF
  __int128 v55; // [rsp+60h] [rbp-49h] BYREF
  __int64 v56; // [rsp+70h] [rbp-39h]
  int v57[2]; // [rsp+78h] [rbp-31h] BYREF
  const wchar_t *v58; // [rsp+80h] [rbp-29h] BYREF
  int v59; // [rsp+88h] [rbp-21h] BYREF
  _QWORD v60[3]; // [rsp+90h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+3Fh]

  v58 = a3;
  if ( a8 )
    *(_DWORD *)a8 = 0;
  if ( a9 )
    *a9 = 0;
  if ( !a3 )
  {
    v11 = -2147467261;
    v59 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid argument: szActionListPath");
      *(_QWORD *)v57 = &v59;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {}",
        (__int64)v57);
    }
    v13 = 3315;
    goto LABEL_9;
  }
  if ( !a4 )
  {
    v11 = -2147467261;
    v59 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid argument: szSandboxPath");
      *(_QWORD *)v57 = &v59;
      LOBYTE(v15) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v15,
        3,
        (unsigned int)": {}",
        (__int64)v57);
    }
    v13 = 3316;
    goto LABEL_9;
  }
  if ( !*((_BYTE *)this - 31) )
  {
    v16 = (const wchar_t *)*((_QWORD *)this - 2);
    v17 = (CCbsSession *)*((_QWORD *)this - 11);
    v56 = 0;
    *(_QWORD *)v57 = 0;
    v60[0] = &Windows::Rtl::PrivateHeapPool::`vftable';
    v55 = 0;
    v60[1] = 0;
    v60[2] = 0;
    v53 = 0;
    Str = 0;
    v52 = 0;
    v49 = 0;
    FeatureOnDemandMetadataFolder = CCbsSession::GetFeatureOnDemandMetadataFolder(v17, 1, v16, &v52);
    v11 = FeatureOnDemandMetadataFolder;
    if ( FeatureOnDemandMetadataFolder >= 0 )
    {
      v21 = ActionListParser::ReadActionList(v58, v60, v57, &v55);
      v11 = v21;
      if ( v21 >= 0 )
      {
        v24 = DuplicateParserString(
                (struct Windows::Rtl::IPoolAllocator *)v60,
                (const struct _LUTF8_STRING *)(*(_QWORD *)v57 + 56LL),
                &v49);
        v11 = v24;
        if ( v24 < 0 )
        {
          v23 = (unsigned int)v24;
          v20 = 3350;
          goto LABEL_29;
        }
        v25 = SczAllocFromSz((char *)this - 64, v49);
        v11 = v25;
        if ( v25 < 0 )
        {
          v23 = (unsigned int)v25;
          v20 = 3351;
          goto LABEL_29;
        }
        v26 = *(_QWORD *)v57;
        v27 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v57 + 152LL) + 96LL);
        if ( v27 )
        {
          *((_QWORD *)this - 7) = v27;
          v29 = 0;
          for ( i = *(_QWORD *)(*(_QWORD *)(v26 + 152) + 88LL); i; i = *(_QWORD *)(i + 248) )
          {
            v31 = *(_DWORD *)(i + 136);
            v49 = 0;
            if ( v31 == 8 || v31 == 2 )
            {
              v32 = DuplicateParserString(
                      (struct Windows::Rtl::IPoolAllocator *)v60,
                      (const struct _LUTF8_STRING *)(i + 96),
                      &v49);
              if ( v32 < 0 )
              {
                v44 = 3374;
                goto LABEL_69;
              }
              v32 = SczAllocFormatted(&v53, L"%s%s", a4, v49);
              if ( v32 < 0 )
              {
                v44 = 3375;
                goto LABEL_69;
              }
              v32 = SczAllocFormatted(&Str, L"%s%s", v52, v49);
              if ( v32 < 0 )
              {
                v44 = 3376;
LABEL_69:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v44,
                  (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
                  (const char *)(unsigned int)v32,
                  v48);
                v11 = v32;
                goto LABEL_81;
              }
              v33 = Str;
              if ( !v29 && wcschr(Str, 0x5Cu) )
              {
                v49 = 0;
                v34 = DirectoryFromPath(v33);
                if ( v34 < 0 )
                {
                  v59 = v34;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to call DirectoryfromPath");
                    *(_QWORD *)v50 = &v59;
                    LOBYTE(v39) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v39,
                      3,
                      (unsigned int)": {}",
                      (__int64)v50);
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xD39,
                    (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
                    (const char *)(unsigned int)v34,
                    v48);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v49);
                  v11 = v34;
                  goto LABEL_81;
                }
                v35 = v49;
                Directory = RecursivelyCreateDirectory(v49, 0);
                if ( Directory < 0 )
                {
                  v59 = Directory;
                  if ( LogAdapter::g_Logger )
                  {
                    v54 = v35;
                    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                      (_DWORD)LogAdapter::g_Logger,
                      0,
                      3,
                      (unsigned int)"Failed to create directory: {}",
                      (__int64)&v54);
                    *(_QWORD *)v50 = &v59;
                    LOBYTE(v38) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v38,
                      3,
                      (unsigned int)": {}",
                      (__int64)v50);
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xD3B,
                    (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
                    (const char *)(unsigned int)Directory,
                    v48);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v49);
                  v11 = Directory;
                  goto LABEL_81;
                }
                v29 = 1;
                Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v49);
              }
              v37 = v53;
              if ( !(unsigned int)PrivCopyFileExW(v53, v33, 0, 0, 0, 256) )
              {
                LastError = GetLastError();
                if ( LogAdapter::g_Logger )
                {
                  *(_QWORD *)v50 = v33;
                  v54 = v37;
                  LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                    (_DWORD)LogAdapter::g_Logger,
                    0,
                    3,
                    (unsigned int)"Failed to copy '{}' to store: {}",
                    (__int64)&v54,
                    (__int64)v50);
                  if ( LastError > 0 )
                    v42 = (unsigned __int16)LastError | 0x80070000;
                  else
                    v42 = LastError;
                  v59 = v42;
                  LOBYTE(v41) = 1;
                  v49 = (wchar_t *)&v59;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v41,
                    3,
                    (unsigned int)": {0}",
                    (__int64)&v49);
                }
                if ( LastError )
                {
                  v43 = 3400;
LABEL_65:
                  v11 = wil::details::in1diag3::Return_Win32(
                          retaddr,
                          (void *)v43,
                          (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
                          (const char *)(unsigned int)LastError,
                          v48);
                  goto LABEL_81;
                }
                goto LABEL_80;
              }
            }
          }
          v45 = SczAllocFormatted(&Str, L"%s%s", v52, L"ActionList.xml");
          v11 = v45;
          if ( v45 >= 0 )
          {
            if ( !(unsigned int)PrivCopyFileExW(v58, Str, 0, 0, 0, 256) )
            {
              LastError = GetLastError();
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed to copy action list '{}' to store",
                  (__int64)&v58);
                if ( LastError > 0 )
                  v47 = (unsigned __int16)LastError | 0x80070000;
                else
                  v47 = LastError;
                v59 = v47;
                LOBYTE(v46) = 1;
                *(_QWORD *)v50 = &v59;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v46,
                  3,
                  (unsigned int)": {0}",
                  (__int64)v50);
              }
              if ( LastError )
              {
                v43 = 3416;
                goto LABEL_65;
              }
LABEL_80:
              v11 = 0;
LABEL_81:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v52);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v53);
              Windows::Rtl::PrivateHeapPool::~PrivateHeapPool((Windows::Rtl::PrivateHeapPool *)v60);
              Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v55);
              return (unsigned int)v11;
            }
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v52);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v53);
            Windows::Rtl::PrivateHeapPool::~PrivateHeapPool((Windows::Rtl::PrivateHeapPool *)v60);
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v55);
            return 0;
          }
          v23 = (unsigned int)v45;
          v20 = 3406;
LABEL_29:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
            (const char *)v23,
            v48);
          goto LABEL_81;
        }
        v11 = -2147023728;
        v59 = -2147023728;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "ActionList returns but it contains empty install action");
          v49 = (wchar_t *)&v59;
          LOBYTE(v28) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v28,
            3,
            (unsigned int)": {}",
            (__int64)&v49);
        }
        v20 = 3357;
      }
      else
      {
        v59 = v21;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to load actions from {}",
            (__int64)&v58);
          v49 = (wchar_t *)&v59;
          LOBYTE(v22) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v22,
            3,
            (unsigned int)": {}",
            (__int64)&v49);
        }
        v20 = 3348;
      }
    }
    else
    {
      v59 = FeatureOnDemandMetadataFolder;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get package store directory");
        v49 = (wchar_t *)&v59;
        LOBYTE(v19) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v19,
          3,
          (unsigned int)": {}",
          (__int64)&v49);
      }
      v20 = 3345;
    }
    v23 = (unsigned int)v11;
    goto LABEL_29;
  }
  v11 = SczAllocFromSz((char *)this - 40, a3);
  if ( v11 < 0 )
  {
    v13 = 3323;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
      (const char *)(unsigned int)v11,
      v48);
    return (unsigned int)v11;
  }
  v11 = SczAllocFromSz((char *)this - 48, a4);
  if ( v11 < 0 )
  {
    v13 = 3324;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x1800af8d8  push    rbp
0x1800af8da  push    rbx
0x1800af8db  push    rsi
0x1800af8dc  push    rdi
0x1800af8dd  push    r12
0x1800af8df  push    r14
0x1800af8e1  push    r15
0x1800af8e3  lea     rbp, [rsp-7]
0x1800af8e8  sub     rsp, 0B0h
0x1800af8ef  mov     rax, cs:__security_cookie
0x1800af8f6  xor     rax, rsp
0x1800af8f9  mov     [rbp+37h+var_38], rax
0x1800af8fd  mov     rax, [rbp+37h+arg_40]
0x1800af904  mov     rdi, rcx
0x1800af907  mov     rcx, [rbp+37h+arg_38]
0x1800af90b  xor     r12d, r12d
0x1800af90e  mov     [rbp+37h+var_60], r8
0x1800af912  mov     r15, r9
0x1800af915  test    rcx, rcx
0x1800af918  jz      short loc_1800AF91D
0x1800af91a  mov     [rcx], r12d
0x1800af91d  test    rax, rax
0x1800af920  jz      short loc_1800AF925
0x1800af922  mov     [rax], r12
0x1800af925  test    r8, r8
0x1800af928  jnz     short loc_1800AF99B
0x1800af92a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800af931  mov     ebx, 80004003h
0x1800af936  mov     [rbp+37h+var_58], ebx
0x1800af939  test    rcx, rcx
0x1800af93c  jz      short loc_1800AF97C
0x1800af93e  lea     edi, [r8+3]
0x1800af942  xor     edx, edx
0x1800af944  mov     r8d, edi
0x1800af947  lea     r9, aInvalidArgumen_27; "Invalid argument: szActionListPath"
0x1800af94e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800af953  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800af95a  lea     rax, [rbp+37h+var_58]
0x1800af95e  mov     qword ptr [rbp+37h+var_68], rax
0x1800af962  lea     r9, asc_1802EE7AC; ": {}"
0x1800af969  lea     rax, [rbp+37h+var_68]
0x1800af96d  mov     r8d, edi
0x1800af970  mov     dl, 1
0x1800af972  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800af977  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800af97c  mov     edx, 0CF3h; void *
0x1800af981  mov     rcx, [rbp+3Fh]; this
0x1800af985  lea     r8, aOnecoreBaseCbs_141; "onecore\\base\\cbs\\core\\capabilityman"...
0x1800af98c  mov     r9d, ebx; char *
0x1800af98f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af994  mov     eax, ebx
0x1800af996  jmp     loc_1800B0063
0x1800af99b  test    r15, r15
0x1800af99e  jnz     short loc_1800AF9F9
0x1800af9a0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800af9a7  mov     ebx, 80004003h
0x1800af9ac  mov     [rbp+37h+var_58], ebx
0x1800af9af  test    rcx, rcx
0x1800af9b2  jz      short loc_1800AF9F2
0x1800af9b4  lea     edi, [r15+3]
0x1800af9b8  xor     edx, edx
0x1800af9ba  mov     r8d, edi
0x1800af9bd  lea     r9, aInvalidArgumen_0; "Invalid argument: szSandboxPath"
0x1800af9c4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800af9c9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800af9d0  lea     rax, [rbp+37h+var_58]
0x1800af9d4  mov     qword ptr [rbp+37h+var_68], rax
0x1800af9d8  lea     r9, asc_1802EE7AC; ": {}"
0x1800af9df  lea     rax, [rbp+37h+var_68]
0x1800af9e3  mov     r8d, edi
0x1800af9e6  mov     dl, 1
0x1800af9e8  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800af9ed  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800af9f2  mov     edx, 0CF4h
0x1800af9f7  jmp     short loc_1800AF981
0x1800af9f9  cmp     [rdi-1Fh], r12b
0x1800af9fd  jz      short loc_1800AFA3B
0x1800af9ff  lea     rcx, [rdi-28h]
0x1800afa03  mov     rdx, r8
0x1800afa06  call    SczAllocFromSz
0x1800afa0b  mov     ebx, eax
0x1800afa0d  test    eax, eax
0x1800afa0f  jns     short loc_1800AFA1B
0x1800afa11  mov     edx, 0CFBh
0x1800afa16  jmp     loc_1800AF981
0x1800afa1b  lea     rcx, [rdi-30h]
0x1800afa1f  mov     rdx, r15
0x1800afa22  call    SczAllocFromSz
0x1800afa27  mov     ebx, eax
0x1800afa29  test    eax, eax
0x1800afa2b  jns     loc_1800B0061
0x1800afa31  mov     edx, 0CFCh
0x1800afa36  jmp     loc_1800AF981
0x1800afa3b  mov     r8, [rdi-10h]; wchar_t *
0x1800afa3f  lea     r9, [rbp+37h+var_98]; wchar_t **
0x1800afa43  mov     rcx, [rdi-58h]; this
0x1800afa47  xor     eax, eax
0x1800afa49  mov     [rbp+37h+var_70], rax
0x1800afa4d  xorps   xmm0, xmm0
0x1800afa50  lea     rax, ??_7PrivateHeapPool@Rtl@Windows@@6B@; const Windows::Rtl::PrivateHeapPool::`vftable'
0x1800afa57  mov     qword ptr [rbp+37h+var_68], r12
0x1800afa5b  mov     dl, 1; bool
0x1800afa5d  mov     [rbp+37h+var_50], rax
0x1800afa61  movups  [rbp+37h+var_80], xmm0
0x1800afa65  mov     [rbp+37h+var_48], r12
0x1800afa69  mov     [rbp+37h+var_40], r12
0x1800afa6d  mov     [rbp+37h+var_90], r12
0x1800afa71  mov     [rbp+37h+Str], r12
0x1800afa75  mov     [rbp+37h+var_98], r12
0x1800afa79  mov     [rbp+37h+var_B0], r12
0x1800afa7d  call    ?GetFeatureOnDemandMetadataFolder@CCbsSession@@QEAAJ_NPEB_WPEAPEA_W@Z; CCbsSession::GetFeatureOnDemandMetadataFolder(bool,wchar_t const *,wchar_t * *)
0x1800afa82  mov     ebx, eax
0x1800afa84  test    eax, eax
0x1800afa86  jns     short loc_1800AFADD
0x1800afa88  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800afa8f  mov     [rbp+37h+var_58], eax
0x1800afa92  test    rcx, rcx
0x1800afa95  jz      short loc_1800AFAD6
0x1800afa97  mov     edi, 3
0x1800afa9c  lea     r9, aFailedToGetPac_15; "Failed to get package store directory"
0x1800afaa3  mov     r8d, edi
0x1800afaa6  xor     edx, edx
0x1800afaa8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800afaad  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800afab4  lea     rax, [rbp+37h+var_58]
0x1800afab8  mov     [rbp+37h+var_B0], rax
0x1800afabc  lea     r9, asc_1802EE7AC; ": {}"
0x1800afac3  lea     rax, [rbp+37h+var_B0]
0x1800afac7  mov     r8d, edi
0x1800afaca  mov     dl, 1
0x1800afacc  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800afad1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800afad6  mov     edx, 0D11h
0x1800afadb  jmp     short loc_1800AFB54
0x1800afadd  mov     rcx, [rbp+37h+var_60]
0x1800afae1  lea     r9, [rbp+37h+var_80]
0x1800afae5  lea     r8, [rbp+37h+var_68]
0x1800afae9  lea     rdx, [rbp+37h+var_50]
0x1800afaed  call    ?ReadActionList@ActionListParser@@YAJQEB_WAEAVIPoolAllocator@Rtl@Windows@@PEAPEAUActionListDocument@1@PEAV?$Auto@U_LBLOB@@@4@@Z; ActionListParser::ReadActionList(wchar_t const * const,Windows::Rtl::IPoolAllocator &,ActionListParser::ActionListDocument * *,Windows::Auto<_LBLOB> *)
0x1800afaf2  mov     ebx, eax
0x1800afaf4  test    eax, eax
0x1800afaf6  jns     short loc_1800AFB6C
0x1800afaf8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800afaff  mov     [rbp+37h+var_58], eax
0x1800afb02  test    rcx, rcx
0x1800afb05  jz      short loc_1800AFB4F
0x1800afb07  lea     rax, [rbp+37h+var_60]
0x1800afb0b  mov     edi, 3
0x1800afb10  mov     r8d, edi
0x1800afb13  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800afb18  lea     r9, aFailedToLoadAc_2; "Failed to load actions from {}"
0x1800afb1f  xor     edx, edx
0x1800afb21  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800afb26  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800afb2d  lea     rax, [rbp+37h+var_58]
0x1800afb31  mov     [rbp+37h+var_B0], rax
0x1800afb35  lea     r9, asc_1802EE7AC; ": {}"
0x1800afb3c  lea     rax, [rbp+37h+var_B0]
0x1800afb40  mov     r8d, edi
0x1800afb43  mov     dl, 1
0x1800afb45  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800afb4a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800afb4f  mov     edx, 0D14h; void *
0x1800afb54  mov     r9d, ebx; char *
0x1800afb57  mov     rcx, [rbp+3Fh]; this
0x1800afb5b  lea     r8, aOnecoreBaseCbs_141; "onecore\\base\\cbs\\core\\capabilityman"...
0x1800afb62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800afb67  jmp     loc_1800B0002
0x1800afb6c  mov     rdx, qword ptr [rbp+37h+var_68]
0x1800afb70  lea     r8, [rbp+37h+var_B0]; wchar_t **
0x1800afb74  add     rdx, 38h ; '8'; struct _LUTF8_STRING *
0x1800afb78  lea     rcx, [rbp+37h+var_50]; struct Windows::Rtl::IPoolAllocator *
0x1800afb7c  call    ?DuplicateParserString@@YAJAEAVIPoolAllocator@Rtl@Windows@@AEBU_LUTF8_STRING@@PEAPEA_W@Z; DuplicateParserString(Windows::Rtl::IPoolAllocator &,_LUTF8_STRING const &,wchar_t * *)
0x1800afb81  mov     ebx, eax
0x1800afb83  test    eax, eax
0x1800afb85  jns     short loc_1800AFB91
0x1800afb87  mov     r9d, eax
0x1800afb8a  mov     edx, 0D16h
0x1800afb8f  jmp     short loc_1800AFB57
0x1800afb91  mov     rdx, [rbp+37h+var_B0]
0x1800afb95  lea     rcx, [rdi-40h]
0x1800afb99  call    SczAllocFromSz
0x1800afb9e  mov     ebx, eax
0x1800afba0  test    eax, eax
0x1800afba2  jns     short loc_1800AFBAE
0x1800afba4  mov     r9d, eax
0x1800afba7  mov     edx, 0D17h
0x1800afbac  jmp     short loc_1800AFB57
0x1800afbae  mov     rbx, qword ptr [rbp+37h+var_68]
0x1800afbb2  mov     rax, [rbx+98h]
0x1800afbb9  mov     rcx, [rax+60h]
0x1800afbbd  test    rcx, rcx
0x1800afbc0  jnz     short loc_1800AFC1F
0x1800afbc2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800afbc9  mov     ebx, 80070490h
0x1800afbce  mov     [rbp+37h+var_58], ebx
0x1800afbd1  test    rcx, rcx
0x1800afbd4  jz      short loc_1800AFC15
0x1800afbd6  mov     edi, 3
0x1800afbdb  lea     r9, aActionlistRetu_0; "ActionList returns but it contains empt"...
0x1800afbe2  mov     r8d, edi
0x1800afbe5  xor     edx, edx
0x1800afbe7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800afbec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800afbf3  lea     rax, [rbp+37h+var_58]
0x1800afbf7  mov     [rbp+37h+var_B0], rax
0x1800afbfb  lea     r9, asc_1802EE7AC; ": {}"
0x1800afc02  lea     rax, [rbp+37h+var_B0]
0x1800afc06  mov     r8d, edi
0x1800afc09  mov     dl, 1
0x1800afc0b  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800afc10  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800afc15  mov     edx, 0D1Dh
0x1800afc1a  jmp     loc_1800AFB54
0x1800afc1f  mov     [rdi-38h], rcx
0x1800afc23  mov     r14b, r12b
0x1800afc26  mov     rbx, [rbx+98h]
0x1800afc2d  mov     rbx, [rbx+58h]
0x1800afc31  test    rbx, rbx
0x1800afc34  jz      loc_1800AFF1F
0x1800afc3a  mov     eax, [rbx+88h]
0x1800afc40  mov     [rbp+37h+var_B0], r12
0x1800afc44  cmp     eax, 8
0x1800afc47  jz      short loc_1800AFC52
0x1800afc49  cmp     eax, 2
0x1800afc4c  jnz     loc_1800AFD3E
0x1800afc52  lea     rdx, [rbx+60h]; struct _LUTF8_STRING *
0x1800afc56  lea     r8, [rbp+37h+var_B0]; wchar_t **
0x1800afc5a  lea     rcx, [rbp+37h+var_50]; struct Windows::Rtl::IPoolAllocator *
0x1800afc5e  call    ?DuplicateParserString@@YAJAEAVIPoolAllocator@Rtl@Windows@@AEBU_LUTF8_STRING@@PEAPEA_W@Z; DuplicateParserString(Windows::Rtl::IPoolAllocator &,_LUTF8_STRING const &,wchar_t * *)
0x1800afc63  mov     edi, eax
0x1800afc65  test    eax, eax
0x1800afc67  js      loc_1800AFF00
0x1800afc6d  mov     r9, [rbp+37h+var_B0]
0x1800afc71  lea     rdx, aSS_1; "%s%s"
0x1800afc78  mov     r8, r15
0x1800afc7b  lea     rcx, [rbp+37h+var_90]
0x1800afc7f  call    SczAllocFormatted
0x1800afc84  mov     edi, eax
0x1800afc86  test    eax, eax
0x1800afc88  js      loc_1800AFEF9
0x1800afc8e  mov     r9, [rbp+37h+var_B0]
0x1800afc92  lea     rdx, aSS_1; "%s%s"
0x1800afc99  mov     r8, [rbp+37h+var_98]
0x1800afc9d  lea     rcx, [rbp+37h+Str]
0x1800afca1  call    SczAllocFormatted
0x1800afca6  mov     edi, eax
0x1800afca8  test    eax, eax
0x1800afcaa  js      loc_1800AFEF2
0x1800afcb0  mov     rdi, [rbp+37h+Str]
0x1800afcb4  test    r14b, r14b
0x1800afcb7  jnz     short loc_1800AFD0D
0x1800afcb9  mov     edx, 5Ch ; '\'; Ch
0x1800afcbe  mov     rcx, rdi; Str
0x1800afcc1  call    cs:__imp_wcschr
0x1800afcc8  nop     dword ptr [rax+rax+00h]
0x1800afccd  test    rax, rax
0x1800afcd0  jz      short loc_1800AFD0D
0x1800afcd2  lea     rdx, [rbp+37h+var_B0]
0x1800afcd6  mov     [rbp+37h+var_B0], r12
0x1800afcda  mov     rcx, rdi; wchar_t *
0x1800afcdd  call    DirectoryFromPath
0x1800afce2  mov     esi, eax
0x1800afce4  test    eax, eax
0x1800afce6  js      loc_1800AFDCF
0x1800afcec  mov     rsi, [rbp+37h+var_B0]
0x1800afcf0  xor     edx, edx
0x1800afcf2  mov     rcx, rsi
0x1800afcf5  call    RecursivelyCreateDirectory
0x1800afcfa  mov     r14d, eax
0x1800afcfd  test    eax, eax
0x1800afcff  js      short loc_1800AFD4A
0x1800afd01  lea     rcx, [rbp+37h+var_B0]
0x1800afd05  mov     r14b, 1
0x1800afd08  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800afd0d  mov     rsi, [rbp+37h+var_90]
0x1800afd11  xor     r9d, r9d
0x1800afd14  mov     rcx, rsi
0x1800afd17  mov     dword ptr [rsp+0E0h+var_B8], 100h
0x1800afd1f  xor     r8d, r8d
0x1800afd22  mov     qword ptr [rsp+0E0h+var_C0], r12
0x1800afd27  mov     rdx, rdi
0x1800afd2a  call    cs:__imp_PrivCopyFileExW
0x1800afd31  nop     dword ptr [rax+rax+00h]
0x1800afd36  test    eax, eax
0x1800afd38  jz      loc_1800AFE45
0x1800afd3e  mov     rbx, [rbx+0F8h]
0x1800afd45  jmp     loc_1800AFC31
0x1800afd4a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800afd51  mov     [rbp+37h+var_58], r14d
0x1800afd55  test    rcx, rcx
0x1800afd58  jz      short loc_1800AFDA6
0x1800afd5a  lea     rax, [rbp+37h+var_88]
0x1800afd5e  mov     [rbp+37h+var_88], rsi
0x1800afd62  mov     edi, 3
0x1800afd67  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800afd6c  mov     r8d, edi
0x1800afd6f  lea     r9, aFailedToCreate; "Failed to create directory: {}"
0x1800afd76  xor     edx, edx
0x1800afd78  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
  ... truncated ...
```
