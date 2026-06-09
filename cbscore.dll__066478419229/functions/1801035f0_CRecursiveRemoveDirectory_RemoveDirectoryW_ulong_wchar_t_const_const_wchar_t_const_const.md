# CRecursiveRemoveDirectory::RemoveDirectoryW(ulong,wchar_t const * const,wchar_t const * const)

- ea: `0x1801035f0`
- end: `0x180103c28`
- name: `?RemoveDirectoryW@CRecursiveRemoveDirectory@@QEAAJKQEB_W0@Z`
- size: `1592`
- prototype: `__int64 __fastcall(CRecursiveRemoveDirectory *__hidden this, unsigned int, const wchar_t *const, const wchar_t *const)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting`

## callers

- `0x180107120`
- `0x18017bd6c`

## callees

- `0x180013250`
- `0x180015420`
- `0x18002e224`
- `0x18002e280`
- `0x18004cd20`
- `0x180055fc8`
- `0x1800568a8`
- `0x180056e00`
- `0x18005eef0`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x18009f770`
- `0x18009f7a4`
- `0x1800a8678`
- `0x1800be15c`
- `0x1800d0588`
- `0x1800eb920`
- `0x1800fe364`
- `0x1801027b4`
- `0x180102dcc`
- `0x1801035f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103ab7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180103a77`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180103a77`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180103930`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180103930`

## string_xrefs

- `0x180103785`: `No directory specified`
- `0x1801036ad`: `Cannot use ContentsOnly with MoveToCbsTempBeforeDelete or RenameToTempBeforeDelete or MoveToCbsTempOnFailures`
- `0x180103718`: `Cannot use AllowReparseRoot without ContentsOnly`
- `0x1801038d4`: `Failed to acquire current thread token`
- `0x180103bab`: `Deletion of: {} successful; already deleted`
- `0x180103889`: `Deleting the contents of directory: {}`
- `0x180103897`: `Deleting directory: {}`
- `0x180103aee`: `Deletion of directory failed...moving to CbsTemp`
- `0x180103b2b`: `Failed removing directory: {}`
- `0x1801039ac`: `Unable to move directory to temp, will delete in-place instead`
- `0x180103a03`: `Failed getting parent directory: {}`

## pseudocode

```c
__int64 __fastcall CRecursiveRemoveDirectory::RemoveDirectoryW(
        CRecursiveRemoveDirectory *this,
        BOOL a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  __int64 v5; // rdi
  int v8; // r15d
  unsigned int v9; // r12d
  unsigned int v10; // esi
  int v11; // edx
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // edx
  const wchar_t *v15; // rdx
  int v16; // edx
  int v17; // eax
  int v18; // edx
  bool v19; // r13
  WCHAR *v20; // rbx
  const char *v21; // r9
  int v22; // eax
  unsigned int v23; // esi
  int v24; // edx
  int v25; // edx
  int v26; // ecx
  void *v27; // rax
  int v28; // eax
  int v29; // eax
  int v30; // edx
  HANDLE FileW; // rax
  signed int LastError; // eax
  int v33; // edx
  const char *v34; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-B9h]
  int v37[2]; // [rsp+40h] [rbp-99h] BYREF
  bool v38; // [rsp+48h] [rbp-91h]
  bool v39; // [rsp+49h] [rbp-90h]
  LPCWSTR lpFileName; // [rsp+50h] [rbp-89h] BYREF
  CRecursiveRemoveDirectory *v41; // [rsp+58h] [rbp-81h] BYREF
  __int64 v42; // [rsp+60h] [rbp-79h] BYREF
  void *v43; // [rsp+68h] [rbp-71h] BYREF
  LPCWSTR v44; // [rsp+70h] [rbp-69h] BYREF
  const wchar_t *v45; // [rsp+78h] [rbp-61h] BYREF
  LPCWSTR v46; // [rsp+80h] [rbp-59h] BYREF
  __int64 v47; // [rsp+88h] [rbp-51h] BYREF
  char v48; // [rsp+90h] [rbp-49h]
  _BYTE v49[80]; // [rsp+A0h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v41 = this;
  v44 = 0;
  lpFileName = 0;
  v5 = 0;
  v42 = 0;
  v45 = a3;
  AutoThreadPriority::AutoThreadPriority((AutoThreadPriority *)v49, a2);
  v47 = 0;
  v48 = 0;
  v43 = 0;
  v38 = a2;
  LODWORD(v46) = a2 & 0x20;
  v8 = a2 & 0x10;
  LOBYTE(v9) = (a2 & 8) != 0;
  v39 = (a2 & 0x40) != 0;
  if ( a2 && ((a2 & 0x10) != 0 || (a2 & 0x20) != 0 || (a2 & 8) != 0) )
  {
    v10 = -2147024809;
    LODWORD(v46) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Cannot use ContentsOnly with MoveToCbsTempBeforeDelete or RenameToTempBeforeDelete or MoveToCbsTempOnFailures");
      *(_QWORD *)v37 = &v46;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)v37);
    }
    v12 = 2147942487LL;
    v13 = 779;
    goto LABEL_22;
  }
  if ( (a2 & 0x40) != 0 && !a2 )
  {
    v10 = -2147024809;
    LODWORD(v46) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Cannot use AllowReparseRoot without ContentsOnly");
      *(_QWORD *)v37 = &v46;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {}",
        (__int64)v37);
    }
    v12 = 2147942487LL;
    v13 = 784;
    goto LABEL_22;
  }
  v15 = v45;
  if ( !v45 )
  {
    v10 = -2147024809;
    LODWORD(v46) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        (unsigned int)((_DWORD)v45 + 3),
        "No directory specified");
      *(_QWORD *)v37 = &v46;
      LOBYTE(v16) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        (_DWORD)v45 + 3,
        (unsigned int)": {}",
        (__int64)v37);
    }
    v12 = 2147942487LL;
    v13 = 787;
    goto LABEL_22;
  }
  *((_DWORD *)this + 5) = a2;
  *((_BYTE *)this + 16) = (a2 & 2) != 0;
  if ( (a2 & 4) != 0 )
  {
    AutoThreadPriority::SetPriority(v49, 3);
    v15 = v45;
  }
  v17 = SczAllocFromSz(&lpFileName, v15);
  v10 = v17;
  if ( v17 < 0 )
  {
    v13 = 800;
LABEL_21:
    v12 = (unsigned int)v17;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v12,
      dwCreationDisposition);
    goto LABEL_75;
  }
  v17 = PathPrefix(&lpFileName);
  v10 = v17;
  if ( v17 < 0 )
  {
    v13 = 801;
    goto LABEL_21;
  }
  if ( a4 )
  {
    v17 = SczAllocFromSz(&v42, a4);
    v10 = v17;
    if ( v17 < 0 )
    {
      v13 = 805;
      goto LABEL_21;
    }
    v17 = PathPrefix(&v42);
    v10 = v17;
    if ( v17 < 0 )
    {
      v13 = 806;
      goto LABEL_21;
    }
    v5 = v42;
  }
  v19 = v38;
  v20 = (WCHAR *)lpFileName;
  *(_QWORD *)v37 = lpFileName;
  if ( v38 )
  {
    if ( !LogAdapter::g_Logger )
      goto LABEL_37;
    v21 = "Deleting the contents of directory: {}";
  }
  else
  {
    if ( !LogAdapter::g_Logger )
      goto LABEL_37;
    v21 = "Deleting directory: {}";
  }
  LOBYTE(v18) = 1;
  LogAdapter::Logger::LogNumObjects<wchar_t const *>((_DWORD)LogAdapter::g_Logger, v18, 1, (_DWORD)v21, (__int64)v37);
LABEL_37:
  v22 = RtlSystemUtil::BackupRestorePrivilegeAcquisition::Acquire((RtlSystemUtil::BackupRestorePrivilegeAcquisition *)&v47);
  v23 = v22;
  if ( v22 >= 0 )
  {
    if ( GetFileAttributesW(v20) == -1 )
    {
      v26 = (int)LogAdapter::g_Logger;
      *(_QWORD *)v37 = v20;
      if ( LogAdapter::g_Logger )
      {
        v27 = v37;
LABEL_72:
        v34 = "Deletion of: {} successful; already deleted";
        goto LABEL_73;
      }
      goto LABEL_74;
    }
    if ( v8 || (_DWORD)v46 )
    {
      v46 = v20;
      lpFileName = 0;
      if ( v8 )
      {
        v28 = MoveToCbsTemp(v20, v5, &lpFileName);
        v9 = (unsigned int)v28 >> 31;
      }
      else
      {
        LOBYTE(v9) = 0;
        v28 = RenameToTemp(v20, &lpFileName);
      }
      if ( v28 >= 0 )
      {
        v20 = (WCHAR *)lpFileName;
      }
      else
      {
        v46 = lpFileName;
        lpFileName = v20;
        LogAdapter::TraceAtLevelIfFailed<long,>(
          1,
          (unsigned int)v28,
          "Unable to move directory to temp, will delete in-place instead");
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v46);
    }
    v29 = DirectoryFromPath(v20);
    v10 = v29;
    if ( v29 < 0 )
    {
      LODWORD(v46) = v29;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v37 = v20;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed getting parent directory: {}",
          (__int64)v37);
        v41 = (CRecursiveRemoveDirectory *)&v46;
        LOBYTE(v30) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v30,
          3,
          (unsigned int)": {}",
          (__int64)&v41);
      }
      v12 = v10;
      v13 = 866;
      goto LABEL_22;
    }
    FileW = CreateFileW(v44, 0x100080u, 7u, 0, 3u, 0x2200000u, 0);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
      &v43,
      FileW);
    if ( (char *)v43 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 + 2147024894 <= 1 )
      {
        v26 = (int)LogAdapter::g_Logger;
        v41 = (CRecursiveRemoveDirectory *)v20;
        if ( LogAdapter::g_Logger )
        {
          v27 = &v41;
          goto LABEL_72;
        }
LABEL_74:
        v10 = 0;
        goto LABEL_75;
      }
    }
    else
    {
      v10 = CRecursiveRemoveDirectory::RemoveDirectoryHelperEx(v41, v39, v19, v43, v20);
    }
    if ( (v10 & 0x80000000) != 0 )
    {
      if ( !(_BYTE)v9
        || (LogAdapter::TraceAtLevelIfFailed<long,>(1, v10, "Deletion of directory failed...moving to CbsTemp"),
            v10 = MoveToCbsTemp(v20, v5, 0),
            (v10 & 0x80000000) != 0) )
      {
        LODWORD(v46) = v10;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed removing directory: {}",
            (__int64)&v45);
          v41 = (CRecursiveRemoveDirectory *)&v46;
          LOBYTE(v33) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v33,
            3,
            (unsigned int)": {}",
            (__int64)&v41);
        }
        v12 = v10;
        v13 = 898;
        goto LABEL_22;
      }
    }
    v26 = (int)LogAdapter::g_Logger;
    *(_QWORD *)v37 = v20;
    if ( LogAdapter::g_Logger )
    {
      v27 = v37;
      v34 = "Deletion of: {} successful";
LABEL_73:
      LOBYTE(v25) = 1;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(v26, v25, 1, (_DWORD)v34, (__int64)v27);
      goto LABEL_74;
    }
    goto LABEL_74;
  }
  LODWORD(v46) = v22;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to acquire current thread token");
    *(_QWORD *)v37 = &v46;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v24,
      3,
      (unsigned int)": {}",
      (__int64)v37);
  }
  v10 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x336,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
          (const char *)v23,
          dwCreationDisposition);
LABEL_75:
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v43);
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v47);
  AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v49);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v42);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v44);
  return v10;
}

```

## disassembly

```asm
0x1801035f0  mov     [rsp-8+arg_8], rbx
0x1801035f5  push    rbp
0x1801035f6  push    rsi
0x1801035f7  push    rdi
0x1801035f8  push    r12
0x1801035fa  push    r13
0x1801035fc  push    r14
0x1801035fe  push    r15
0x180103600  lea     rbp, [rsp-27h]
0x180103605  sub     rsp, 100h
0x18010360c  mov     rax, cs:__security_cookie
0x180103613  xor     rax, rsp
0x180103616  mov     [rbp+57h+var_40], rax
0x18010361a  xor     r14d, r14d
0x18010361d  mov     [rsp+130h+var_D8], rcx
0x180103622  mov     rsi, rcx
0x180103625  mov     [rbp+57h+var_C0], r14
0x180103629  lea     rcx, [rbp+57h+var_90]; this
0x18010362d  mov     [rsp+130h+lpFileName], r14
0x180103632  mov     edi, r14d
0x180103635  mov     [rbp+57h+var_D0], r14
0x180103639  mov     r13, r9
0x18010363c  mov     [rbp+57h+var_B8], r8
0x180103640  mov     ebx, edx
0x180103642  call    ??0AutoThreadPriority@@QEAA@_N@Z; AutoThreadPriority::AutoThreadPriority(bool)
0x180103647  mov     dl, bl
0x180103649  mov     [rbp+57h+var_A8], r14
0x18010364d  and     dl, 1
0x180103650  mov     [rbp+57h+var_A0], r14b
0x180103654  mov     r8d, ebx
0x180103657  mov     [rbp+57h+var_C8], r14
0x18010365b  and     r8d, 20h
0x18010365f  mov     [rsp+130h+var_E8], dl
0x180103663  mov     r15d, ebx
0x180103666  mov     dword ptr [rbp+57h+var_B0], r8d
0x18010366a  and     r15d, 10h
0x18010366e  mov     eax, ebx
0x180103670  and     eax, 8
0x180103673  mov     ecx, ebx
0x180103675  setnz   r12b
0x180103679  and     ecx, 40h
0x18010367c  setnz   [rsp+130h+var_E7]
0x180103681  test    dl, dl
0x180103683  jz      short loc_1801036F6
0x180103685  test    r15d, r15d
0x180103688  jnz     short loc_180103693
0x18010368a  test    r8d, r8d
0x18010368d  jnz     short loc_180103693
0x18010368f  test    eax, eax
0x180103691  jz      short loc_1801036F6
0x180103693  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010369a  mov     esi, 80070057h
0x18010369f  mov     dword ptr [rbp+57h+var_B0], esi
0x1801036a2  test    rcx, rcx
0x1801036a5  jz      short loc_1801036E9
0x1801036a7  mov     r14d, 3
0x1801036ad  lea     r9, aCannotUseConte; "Cannot use ContentsOnly with MoveToCbsT"...
0x1801036b4  mov     r8d, r14d
0x1801036b7  xor     edx, edx
0x1801036b9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801036be  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801036c5  lea     rax, [rbp+57h+var_B0]
0x1801036c9  mov     qword ptr [rsp+130h+var_F0], rax
0x1801036ce  lea     r9, asc_1802EE7AC; ": {}"
0x1801036d5  lea     rax, [rsp+130h+var_F0]
0x1801036da  mov     r8d, r14d
0x1801036dd  mov     dl, 1
0x1801036df  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x1801036e4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801036e9  mov     r9d, esi
0x1801036ec  mov     edx, 30Bh
0x1801036f1  jmp     loc_180103805
0x1801036f6  test    ecx, ecx
0x1801036f8  jz      short loc_180103761
0x1801036fa  test    dl, dl
0x1801036fc  jnz     short loc_180103761
0x1801036fe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180103705  mov     esi, 80070057h
0x18010370a  mov     dword ptr [rbp+57h+var_B0], esi
0x18010370d  test    rcx, rcx
0x180103710  jz      short loc_180103754
0x180103712  mov     r14d, 3
0x180103718  lea     r9, aCannotUseAllow; "Cannot use AllowReparseRoot without Con"...
0x18010371f  mov     r8d, r14d
0x180103722  xor     edx, edx
0x180103724  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180103729  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180103730  lea     rax, [rbp+57h+var_B0]
0x180103734  mov     qword ptr [rsp+130h+var_F0], rax
0x180103739  lea     r9, asc_1802EE7AC; ": {}"
0x180103740  lea     rax, [rsp+130h+var_F0]
0x180103745  mov     r8d, r14d
0x180103748  mov     dl, 1
0x18010374a  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x18010374f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180103754  mov     r9d, esi
0x180103757  mov     edx, 310h
0x18010375c  jmp     loc_180103805
0x180103761  mov     rdx, [rbp+57h+var_B8]
0x180103765  test    rdx, rdx
0x180103768  jnz     short loc_1801037C6
0x18010376a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180103771  mov     esi, 80070057h
0x180103776  mov     dword ptr [rbp+57h+var_B0], esi
0x180103779  test    rcx, rcx
0x18010377c  jz      short loc_1801037BC
0x18010377e  lea     r14d, [rdx+3]
0x180103782  mov     r8d, r14d
0x180103785  lea     r9, aNoDirectorySpe; "No directory specified"
0x18010378c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180103791  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180103798  lea     rax, [rbp+57h+var_B0]
0x18010379c  mov     qword ptr [rsp+130h+var_F0], rax
0x1801037a1  lea     r9, asc_1802EE7AC; ": {}"
0x1801037a8  lea     rax, [rsp+130h+var_F0]
0x1801037ad  mov     r8d, r14d
0x1801037b0  mov     dl, 1
0x1801037b2  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x1801037b7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801037bc  mov     r9d, esi
0x1801037bf  mov     edx, 313h
0x1801037c4  jmp     short loc_180103805
0x1801037c6  mov     eax, ebx
0x1801037c8  mov     [rsi+14h], ebx
0x1801037cb  shr     eax, 1
0x1801037cd  mov     r14d, 3
0x1801037d3  and     al, 1
0x1801037d5  mov     [rsi+10h], al
0x1801037d8  test    bl, 4
0x1801037db  jz      short loc_1801037ED
0x1801037dd  mov     edx, r14d
0x1801037e0  lea     rcx, [rbp+57h+var_90]
0x1801037e4  call    ?SetPriority@AutoThreadPriority@@QEAAXW4PriorityType@1@@Z; AutoThreadPriority::SetPriority(AutoThreadPriority::PriorityType)
0x1801037e9  mov     rdx, [rbp+57h+var_B8]
0x1801037ed  lea     rcx, [rsp+130h+lpFileName]
0x1801037f2  call    SczAllocFromSz
0x1801037f7  mov     esi, eax
0x1801037f9  test    eax, eax
0x1801037fb  jns     short loc_18010381A
0x1801037fd  mov     edx, 320h; void *
0x180103802  mov     r9d, eax; char *
0x180103805  mov     rcx, [rbp+5Fh]; this
0x180103809  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180103810  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180103815  jmp     loc_180103BC7
0x18010381a  lea     rcx, [rsp+130h+lpFileName]
0x18010381f  call    PathPrefix
0x180103824  mov     esi, eax
0x180103826  test    eax, eax
0x180103828  jns     short loc_180103831
0x18010382a  mov     edx, 321h
0x18010382f  jmp     short loc_180103802
0x180103831  test    r13, r13
0x180103834  jz      short loc_180103869
0x180103836  mov     rdx, r13
0x180103839  lea     rcx, [rbp+57h+var_D0]
0x18010383d  call    SczAllocFromSz
0x180103842  mov     esi, eax
0x180103844  test    eax, eax
0x180103846  jns     short loc_18010384F
0x180103848  mov     edx, 325h
0x18010384d  jmp     short loc_180103802
0x18010384f  lea     rcx, [rbp+57h+var_D0]
0x180103853  call    PathPrefix
0x180103858  mov     esi, eax
0x18010385a  test    eax, eax
0x18010385c  jns     short loc_180103865
0x18010385e  mov     edx, 326h
0x180103863  jmp     short loc_180103802
0x180103865  mov     rdi, [rbp+57h+var_D0]
0x180103869  mov     r13b, [rsp+130h+var_E8]
0x18010386e  mov     rbx, [rsp+130h+lpFileName]
0x180103873  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010387a  mov     qword ptr [rsp+130h+var_F0], rbx
0x18010387f  test    r13b, r13b
0x180103882  jz      short loc_180103892
0x180103884  test    rcx, rcx
0x180103887  jz      short loc_1801038B6
0x180103889  lea     r9, aDeletingTheCon; "Deleting the contents of directory: {}"
0x180103890  jmp     short loc_18010389E
0x180103892  test    rcx, rcx
0x180103895  jz      short loc_1801038B6
0x180103897  lea     r9, aDeletingDirect; "Deleting directory: {}"
0x18010389e  mov     r8d, 1
0x1801038a4  lea     rax, [rsp+130h+var_F0]
0x1801038a9  mov     dl, r8b
0x1801038ac  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x1801038b1  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801038b6  lea     rcx, [rbp+57h+var_A8]; this
0x1801038ba  call    ?Acquire@BackupRestorePrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ; RtlSystemUtil::BackupRestorePrivilegeAcquisition::Acquire(void)
0x1801038bf  mov     esi, eax
0x1801038c1  test    eax, eax
0x1801038c3  jns     short loc_18010392D
0x1801038c5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801038cc  mov     dword ptr [rbp+57h+var_B0], eax
0x1801038cf  test    rcx, rcx
0x1801038d2  jz      short loc_18010390E
0x1801038d4  lea     r9, aFailedToAcquir_7; "Failed to acquire current thread token"
0x1801038db  mov     r8d, r14d
0x1801038de  xor     edx, edx
0x1801038e0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801038e5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801038ec  lea     rax, [rbp+57h+var_B0]
0x1801038f0  mov     qword ptr [rsp+130h+var_F0], rax
0x1801038f5  lea     r9, asc_1802EE7AC; ": {}"
0x1801038fc  lea     rax, [rsp+130h+var_F0]
0x180103901  mov     r8d, r14d
0x180103904  mov     qword ptr [rsp+130h+dwCreationDisposition], rax; int
0x180103909  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18010390e  mov     rcx, [rbp+5Fh]; this
0x180103912  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180103919  mov     r9d, esi; char *
0x18010391c  mov     edx, 336h; void *
0x180103921  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180103926  mov     esi, eax
0x180103928  jmp     loc_180103BC7
0x18010392d  mov     rcx, rbx; lpFileName
0x180103930  call    cs:__imp_GetFileAttributesW
0x180103937  nop     dword ptr [rax+rax+00h]
0x18010393c  cmp     eax, 0FFFFFFFFh
0x18010393f  jnz     short loc_180103960
0x180103941  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180103948  mov     qword ptr [rsp+130h+var_F0], rbx
0x18010394d  test    rcx, rcx
0x180103950  jz      loc_180103BC5
0x180103956  lea     rax, [rsp+130h+var_F0]
0x18010395b  jmp     loc_180103BAB
0x180103960  test    r15d, r15d
0x180103963  jnz     short loc_18010396B
0x180103965  cmp     dword ptr [rbp+57h+var_B0], r15d
0x180103969  jz      short loc_1801039D8
0x18010396b  mov     [rbp+57h+var_B0], rbx
0x18010396f  mov     rcx, rbx
0x180103972  mov     [rsp+130h+lpFileName], 0
0x18010397b  test    r15d, r15d
0x18010397e  jz      short loc_180103996
0x180103980  lea     r8, [rsp+130h+lpFileName]
0x180103985  mov     rdx, rdi
0x180103988  call    MoveToCbsTemp
0x18010398d  mov     r12d, eax
0x180103990  shr     r12d, 1Fh
0x180103994  jmp     short loc_1801039A3
0x180103996  xor     r12b, r12b
0x180103999  lea     rdx, [rsp+130h+lpFileName]
0x18010399e  call    RenameToTemp
0x1801039a3  test    eax, eax
0x1801039a5  jns     short loc_1801039CA
0x1801039a7  mov     rcx, [rsp+130h+lpFileName]
0x1801039ac  lea     r8, aUnableToMoveDi; "Unable to move directory to temp, will "...
0x1801039b3  mov     [rbp+57h+var_B0], rcx
0x1801039b7  mov     edx, eax
0x1801039b9  mov     ecx, 1
0x1801039be  mov     [rsp+130h+lpFileName], rbx
0x1801039c3  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1801039c8  jmp     short loc_1801039CF
0x1801039ca  mov     rbx, [rsp+130h+lpFileName]
0x1801039cf  lea     rcx, [rbp+57h+var_B0]
0x1801039d3  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801039d8  lea     rdx, [rbp+57h+var_C0]
0x1801039dc  mov     rcx, rbx; wchar_t *
0x1801039df  call    DirectoryFromPath
0x1801039e4  mov     esi, eax
0x1801039e6  test    eax, eax
0x1801039e8  jns     short loc_180103A51
0x1801039ea  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801039f1  mov     dword ptr [rbp+57h+var_B0], eax
0x1801039f4  test    rcx, rcx
0x1801039f7  jz      short loc_180103A44
0x1801039f9  lea     rax, [rsp+130h+var_F0]
0x1801039fe  mov     qword ptr [rsp+130h+var_F0], rbx
0x180103a03  lea     r9, aFailedGettingP_1; "Failed getting parent directory: {}"
0x180103a0a  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x180103a0f  mov     r8d, r14d
0x180103a12  xor     edx, edx
0x180103a14  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180103a19  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180103a20  lea     rax, [rbp+57h+var_B0]
0x180103a24  mov     [rsp+130h+var_D8], rax
0x180103a29  lea     r9, asc_1802EE7AC; ": {}"
0x180103a30  lea     rax, [rsp+130h+var_D8]
0x180103a35  mov     r8d, r14d
0x180103a38  mov     dl, 1
0x180103a3a  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x180103a3f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180103a44  mov     r9d, esi
0x180103a47  mov     edx, 362h
0x180103a4c  jmp     loc_180103805
0x180103a51  mov     rcx, [rbp+57h+var_C0]; lpFileName
0x180103a55  xor     r9d, r9d; lpSecurityAttributes
0x180103a58  mov     [rsp+130h+hTemplateFile], 0; hTemplateFile
0x180103a61  mov     edx, 100080h; dwDesiredAccess
0x180103a66  mov     [rsp+130h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180103a6e  mov     [rsp+130h+dwCreationDisposition], r14d; dwCreationDisposition
0x180103a73  lea     r8d, [r9+7]; dwShareMode
0x180103a77  call    cs:__imp_CreateFileW
0x180103a7e  nop     dword ptr [rax+rax+00h]
0x180103a83  mov     rdx, rax
0x180103a86  lea     rcx, [rbp+57h+var_C8]
0x180103a8a  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x180103a8f  mov     r9, [rbp+57h+var_C8]; void *
  ... truncated ...
```
