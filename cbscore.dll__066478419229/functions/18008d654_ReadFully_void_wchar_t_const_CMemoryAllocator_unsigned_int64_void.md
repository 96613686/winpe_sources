# ReadFully(void *,wchar_t const *,CMemoryAllocator *,unsigned __int64 *,void * *)

- ea: `0x18008d654`
- end: `0x18008dbf8`
- name: `?ReadFully@@YAJPEAXPEB_WPEAVCMemoryAllocator@@PEA_KPEAPEAX@Z`
- size: `1444`
- prototype: `int(void *, const wchar_t *, struct CMemoryAllocator *, unsigned __int64 *, void **)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180073b74`
- `0x180200c2c`
- `0x180200e78`

## callees

- `0x180028830`
- `0x180033f58`
- `0x18003404c`
- `0x18008d654`
- `0x180095924`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d8de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d9b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008db76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d8de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d9b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008db76`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008db0c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008db0c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008d8bc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008d8bc`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18008d99c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18008d99c`

## string_xrefs

- `0x18008db97`: `Failed to read from file: {}`
- `0x18008d930`: `Failed to open package file: {}`
- `0x18008d9d1`: `Failed to get size of package manifest: {}`
- `0x18008d7ef`: `No read result specified`
- `0x18008d6bb`: `No package manifest specified`
- `0x18008d84e`: `Failed to impersonate user`
- `0x18008da79`: `Failed to allocate memory for xml buffer while reading from file: {}`
- `0x18008d77b`: `No count read result specified`

## pseudocode

```c
__int64 __fastcall ReadFully(void *a1, const wchar_t *a2, struct CMemoryAllocator *a3, unsigned __int64 *a4, void **a5)
{
  unsigned int v7; // edi
  int v8; // edx
  __int64 v9; // rdx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  signed int v13; // eax
  int v14; // edx
  HANDLE FileW; // rbx
  signed int LastError; // eax
  signed int v17; // r14d
  int v18; // edx
  signed int v19; // ebx
  int v20; // edx
  DWORD v21; // eax
  __int64 v22; // rdx
  union _LARGE_INTEGER v23; // r14
  char *v24; // r15
  int v25; // edx
  unsigned __int64 v26; // rdi
  DWORD v27; // r8d
  int v29; // edx
  unsigned int v30; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-51h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-51h]
  int v33[2]; // [rsp+40h] [rbp-31h] BYREF
  unsigned int v34[2]; // [rsp+48h] [rbp-29h] BYREF
  void *v35; // [rsp+50h] [rbp-21h] BYREF
  char v36; // [rsp+58h] [rbp-19h]
  unsigned int *v37; // [rsp+60h] [rbp-11h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-9h] BYREF
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp-1h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+78h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  lpFileName = a2;
  FileSize.QuadPart = 0;
  v35 = a1;
  v36 = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    NumberOfBytesRead = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No package manifest specified");
      *(_QWORD *)v33 = &NumberOfBytesRead;
      LOBYTE(v8) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {}",
        (__int64)v33);
    }
    v9 = 321;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\parser\\helper.cpp",
      (const char *)v7,
      dwCreationDisposition);
    goto LABEL_53;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    NumberOfBytesRead = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No allocator specified");
      *(_QWORD *)v33 = &NumberOfBytesRead;
      LOBYTE(v10) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v10,
        3,
        (unsigned int)": {}",
        (__int64)v33);
    }
    v9 = 322;
    goto LABEL_13;
  }
  if ( !a4 )
  {
    v7 = -2147467261;
    NumberOfBytesRead = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No count read result specified");
      *(_QWORD *)v33 = &NumberOfBytesRead;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)v33);
    }
    v9 = 323;
    goto LABEL_13;
  }
  if ( !a5 )
  {
    v7 = -2147467261;
    NumberOfBytesRead = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No read result specified");
      *(_QWORD *)v33 = &NumberOfBytesRead;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {}",
        (__int64)v33);
    }
    v9 = 324;
    goto LABEL_13;
  }
  v13 = NestableImpersonator::Impersonate((NestableImpersonator *)&v35);
  v7 = v13;
  if ( v13 < 0 )
  {
    NumberOfBytesRead = v13;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to impersonate user");
      *(_QWORD *)v33 = &NumberOfBytesRead;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {}",
        (__int64)v33);
    }
    v9 = 326;
    goto LABEL_13;
  }
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x2000080u, 0);
  *(_QWORD *)v33 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_63;
  LastError = GetLastError();
  v17 = LastError;
  if ( LastError > 0 )
    v17 = (unsigned __int16)LastError | 0x80070000;
  v7 = -2147024894;
  if ( v17 == -2147024894 )
    goto LABEL_26;
  if ( v17 >= 0 )
  {
LABEL_63:
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      v23 = FileSize;
      v24 = (char *)CMemoryAllocator::Alloc(a3, FileSize.QuadPart);
      if ( !v24 )
      {
        v7 = -2147024882;
        NumberOfBytesRead = -2147024882;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to allocate memory for xml buffer while reading from file: {}",
            (__int64)&lpFileName);
          *(_QWORD *)v34 = &NumberOfBytesRead;
          LOBYTE(v25) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v25,
            3,
            (unsigned int)": {}",
            (__int64)v34);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x163,
          (unsigned int)"onecore\\base\\cbs\\parser\\helper.cpp",
          (const char *)0x8007000ELL,
          dwCreationDispositiona);
        goto LABEL_26;
      }
      v26 = 0;
      if ( v23.QuadPart )
      {
        while ( 1 )
        {
          v27 = v23.QuadPart - v26 <= 0xFFFFFFFF ? v23.LowPart - v26 : -1;
          NumberOfBytesRead = v27;
          if ( !ReadFile(FileW, &v24[v26], v27, &NumberOfBytesRead, 0) )
            break;
          if ( NumberOfBytesRead )
          {
            v26 += NumberOfBytesRead;
            if ( v26 < v23.QuadPart )
              continue;
          }
          goto LABEL_51;
        }
        v19 = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to read from file: {}",
            (__int64)&lpFileName);
          if ( v19 > 0 )
            v30 = (unsigned __int16)v19 | 0x80070000;
          else
            v30 = v19;
          v34[0] = v30;
          LOBYTE(v29) = 1;
          v37 = v34;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v29,
            3,
            (unsigned int)": {0}",
            (__int64)&v37);
        }
        if ( v19 )
        {
          v22 = 377;
          goto LABEL_39;
        }
      }
      else
      {
LABEL_51:
        *a5 = v24;
        *a4 = v26;
      }
    }
    else
    {
      v19 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to get size of package manifest: {}",
          (__int64)&lpFileName);
        if ( v19 > 0 )
          v21 = (unsigned __int16)v19 | 0x80070000;
        else
          v21 = v19;
        NumberOfBytesRead = v21;
        LOBYTE(v20) = 1;
        *(_QWORD *)v34 = &NumberOfBytesRead;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v20,
          3,
          (unsigned int)": {0}",
          (__int64)v34);
      }
      if ( v19 )
      {
        v22 = 347;
LABEL_39:
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v22,
               (unsigned int)"onecore\\base\\cbs\\parser\\helper.cpp",
               (const char *)(unsigned int)v19,
               dwCreationDispositiona);
LABEL_26:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v33);
        goto LABEL_53;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v33);
    v7 = 0;
    goto LABEL_53;
  }
  NumberOfBytesRead = v17;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed to open package file: {}",
      (__int64)&lpFileName);
    *(_QWORD *)v34 = &NumberOfBytesRead;
    LOBYTE(v18) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v18,
      3,
      (unsigned int)": {}",
      (__int64)v34);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x157,
    (unsigned int)"onecore\\base\\cbs\\parser\\helper.cpp",
    (const char *)(unsigned int)v17,
    dwCreationDispositiona);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v33);
  v7 = v17;
LABEL_53:
  ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&v35);
  return v7;
}

```

## disassembly

```asm
0x18008d654  mov     [rsp-8+arg_0], rbx
0x18008d659  push    rbp
0x18008d65a  push    rsi
0x18008d65b  push    rdi
0x18008d65c  push    r12
0x18008d65e  push    r13
0x18008d660  push    r14
0x18008d662  push    r15
0x18008d664  lea     rbp, [rsp-1Fh]
0x18008d669  sub     rsp, 90h
0x18008d670  mov     rax, cs:__security_cookie
0x18008d677  xor     rax, rsp
0x18008d67a  mov     [rbp+4Fh+var_40], rax
0x18008d67e  mov     r13, [rbp+4Fh+arg_20]
0x18008d682  mov     r12, r9
0x18008d685  mov     [rbp+4Fh+lpFileName], rdx
0x18008d689  mov     r15, r8
0x18008d68c  mov     qword ptr [rbp+4Fh+FileSize], 0
0x18008d694  mov     [rbp+4Fh+var_70], rcx
0x18008d698  mov     [rbp+4Fh+var_68], 0
0x18008d69c  test    rdx, rdx
0x18008d69f  jnz     short loc_18008D6FA
0x18008d6a1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008d6a8  mov     edi, 80070057h
0x18008d6ad  mov     [rbp+4Fh+NumberOfBytesRead], edi
0x18008d6b0  test    rcx, rcx
0x18008d6b3  jz      short loc_18008D6F0
0x18008d6b5  lea     esi, [rdx+3]
0x18008d6b8  mov     r8d, esi
0x18008d6bb  lea     r9, aNoPackageManif_0; "No package manifest specified"
0x18008d6c2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008d6c7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008d6ce  lea     rax, [rbp+4Fh+NumberOfBytesRead]
0x18008d6d2  mov     qword ptr [rbp+4Fh+var_80], rax
0x18008d6d6  lea     r9, asc_1802EE7AC; ": {}"
0x18008d6dd  lea     rax, [rbp+4Fh+var_80]
0x18008d6e1  mov     r8d, esi
0x18008d6e4  mov     dl, 1
0x18008d6e6  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x18008d6eb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008d6f0  mov     edx, 141h
0x18008d6f5  jmp     loc_18008D7B5
0x18008d6fa  test    r15, r15
0x18008d6fd  jnz     short loc_18008D758
0x18008d6ff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008d706  mov     edi, 80070057h
0x18008d70b  mov     [rbp+4Fh+NumberOfBytesRead], edi
0x18008d70e  test    rcx, rcx
0x18008d711  jz      short loc_18008D751
0x18008d713  lea     esi, [r15+3]
0x18008d717  xor     edx, edx
0x18008d719  mov     r8d, esi
0x18008d71c  lea     r9, aNoAllocatorSpe; "No allocator specified"
0x18008d723  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008d728  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008d72f  lea     rax, [rbp+4Fh+NumberOfBytesRead]
0x18008d733  mov     qword ptr [rbp+4Fh+var_80], rax
0x18008d737  lea     r9, asc_1802EE7AC; ": {}"
0x18008d73e  lea     rax, [rbp+4Fh+var_80]
0x18008d742  mov     r8d, esi
0x18008d745  mov     dl, 1
0x18008d747  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x18008d74c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008d751  mov     edx, 142h
0x18008d756  jmp     short loc_18008D7B5
0x18008d758  test    r12, r12
0x18008d75b  jnz     short loc_18008D7CD
0x18008d75d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008d764  mov     edi, 80004003h
0x18008d769  mov     [rbp+4Fh+NumberOfBytesRead], edi
0x18008d76c  test    rcx, rcx
0x18008d76f  jz      short loc_18008D7B0
0x18008d771  lea     esi, [r12+3]
0x18008d776  xor     edx, edx
0x18008d778  mov     r8d, esi
0x18008d77b  lea     r9, aNoCountReadRes; "No count read result specified"
0x18008d782  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008d787  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008d78e  lea     rax, [rbp+4Fh+NumberOfBytesRead]
0x18008d792  mov     qword ptr [rbp+4Fh+var_80], rax
0x18008d796  lea     r9, asc_1802EE7AC; ": {}"
0x18008d79d  lea     rax, [rbp+4Fh+var_80]
0x18008d7a1  mov     r8d, esi
0x18008d7a4  mov     dl, 1
0x18008d7a6  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; int
0x18008d7ab  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008d7b0  mov     edx, 143h; void *
0x18008d7b5  mov     rcx, [rbp+57h]; this
0x18008d7b9  lea     r8, aOnecoreBaseCbs_31; "onecore\\base\\cbs\\parser\\helper.cpp"
0x18008d7c0  mov     r9d, edi; char *
0x18008d7c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d7c8  jmp     loc_18008DB43
0x18008d7cd  test    r13, r13
0x18008d7d0  jnz     short loc_18008D82B
0x18008d7d2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008d7d9  mov     edi, 80004003h
0x18008d7de  mov     [rbp+4Fh+NumberOfBytesRead], edi
0x18008d7e1  test    rcx, rcx
0x18008d7e4  jz      short loc_18008D824
0x18008d7e6  lea     esi, [r13+3]
0x18008d7ea  xor     edx, edx
0x18008d7ec  mov     r8d, esi
0x18008d7ef  lea     r9, aNoReadResultSp; "No read result specified"
0x18008d7f6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008d7fb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008d802  lea     rax, [rbp+4Fh+NumberOfBytesRead]
0x18008d806  mov     qword ptr [rbp+4Fh+var_80], rax
0x18008d80a  lea     r9, asc_1802EE7AC; ": {}"
0x18008d811  lea     rax, [rbp+4Fh+var_80]
0x18008d815  mov     r8d, esi
0x18008d818  mov     dl, 1
0x18008d81a  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x18008d81f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008d824  mov     edx, 144h
0x18008d829  jmp     short loc_18008D7B5
0x18008d82b  lea     rcx, [rbp+4Fh+var_70]; this
0x18008d82f  call    ?Impersonate@NestableImpersonator@@QEAAJXZ; NestableImpersonator::Impersonate(void)
0x18008d834  mov     edi, eax
0x18008d836  test    eax, eax
0x18008d838  jns     short loc_18008D892
0x18008d83a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008d841  mov     [rbp+4Fh+NumberOfBytesRead], eax
0x18008d844  test    rcx, rcx
0x18008d847  jz      short loc_18008D888
0x18008d849  mov     esi, 3
0x18008d84e  lea     r9, aFailedToImpers_1; "Failed to impersonate user"
0x18008d855  mov     r8d, esi
0x18008d858  xor     edx, edx
0x18008d85a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008d85f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008d866  lea     rax, [rbp+4Fh+NumberOfBytesRead]
0x18008d86a  mov     qword ptr [rbp+4Fh+var_80], rax
0x18008d86e  lea     r9, asc_1802EE7AC; ": {}"
0x18008d875  lea     rax, [rbp+4Fh+var_80]
0x18008d879  mov     r8d, esi
0x18008d87c  mov     dl, 1
0x18008d87e  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x18008d883  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008d888  mov     edx, 146h
0x18008d88d  jmp     loc_18008D7B5
0x18008d892  mov     rcx, [rbp+4Fh+lpFileName]; lpFileName
0x18008d896  mov     esi, 3
0x18008d89b  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18008d8a4  xor     r9d, r9d; lpSecurityAttributes
0x18008d8a7  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18008d8af  mov     edx, 80000000h; dwDesiredAccess
0x18008d8b4  mov     [rsp+0C0h+dwCreationDisposition], esi; dwCreationDisposition
0x18008d8b8  lea     r8d, [rsi-2]; dwShareMode
0x18008d8bc  call    cs:__imp_CreateFileW
0x18008d8c3  nop     dword ptr [rax+rax+00h]
0x18008d8c8  mov     rbx, rax
0x18008d8cb  mov     qword ptr [rbp+4Fh+var_80], rax
0x18008d8cf  inc     rax
0x18008d8d2  test    rax, 0FFFFFFFFFFFFFFFEh
0x18008d8d8  jnz     loc_18008D995
0x18008d8de  call    cs:__imp_GetLastError
0x18008d8e5  nop     dword ptr [rax+rax+00h]
0x18008d8ea  mov     r14d, eax
0x18008d8ed  test    eax, eax
0x18008d8ef  jle     short loc_18008D8FC
0x18008d8f1  movzx   r14d, ax
0x18008d8f5  or      r14d, 80070000h
0x18008d8fc  mov     edi, 80070002h
0x18008d901  cmp     r14d, edi
0x18008d904  jnz     short loc_18008D914
0x18008d906  lea     rcx, [rbp+4Fh+var_80]
0x18008d90a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008d90f  jmp     loc_18008DB43
0x18008d914  test    r14d, r14d
0x18008d917  jns     short loc_18008D995
0x18008d919  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008d920  mov     [rbp+4Fh+NumberOfBytesRead], r14d
0x18008d924  test    rcx, rcx
0x18008d927  jz      short loc_18008D96C
0x18008d929  lea     rax, [rbp+4Fh+lpFileName]
0x18008d92d  mov     r8d, esi
0x18008d930  lea     r9, aFailedToOpenPa_6; "Failed to open package file: {}"
0x18008d937  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x18008d93c  xor     edx, edx
0x18008d93e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18008d943  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008d94a  lea     rax, [rbp+4Fh+NumberOfBytesRead]
0x18008d94e  mov     qword ptr [rbp+4Fh+var_78], rax
0x18008d952  lea     r9, asc_1802EE7AC; ": {}"
0x18008d959  lea     rax, [rbp+4Fh+var_78]
0x18008d95d  mov     r8d, esi
0x18008d960  mov     dl, 1
0x18008d962  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; int
0x18008d967  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008d96c  mov     rcx, [rbp+57h]; this
0x18008d970  lea     r8, aOnecoreBaseCbs_31; "onecore\\base\\cbs\\parser\\helper.cpp"
0x18008d977  mov     r9d, r14d; char *
0x18008d97a  mov     edx, 157h; void *
0x18008d97f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d984  lea     rcx, [rbp+4Fh+var_80]
0x18008d988  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008d98d  mov     edi, r14d
0x18008d990  jmp     loc_18008DB43
0x18008d995  lea     rdx, [rbp+4Fh+FileSize]; lpFileSize
0x18008d999  mov     rcx, rbx; hFile
0x18008d99c  call    cs:__imp_GetFileSizeEx
0x18008d9a3  nop     dword ptr [rax+rax+00h]
0x18008d9a8  test    eax, eax
0x18008d9aa  jnz     loc_18008DA47
0x18008d9b0  call    cs:__imp_GetLastError
0x18008d9b7  nop     dword ptr [rax+rax+00h]
0x18008d9bc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008d9c3  mov     ebx, eax
0x18008d9c5  test    rcx, rcx
0x18008d9c8  jz      short loc_18008DA20
0x18008d9ca  lea     rax, [rbp+4Fh+lpFileName]
0x18008d9ce  mov     r8d, esi
0x18008d9d1  lea     r9, aFailedToGetSiz; "Failed to get size of package manifest:"...
0x18008d9d8  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x18008d9dd  xor     edx, edx
0x18008d9df  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18008d9e4  test    ebx, ebx
0x18008d9e6  jg      short loc_18008D9EC
0x18008d9e8  mov     eax, ebx
0x18008d9ea  jmp     short loc_18008D9F4
0x18008d9ec  movzx   eax, bx
0x18008d9ef  or      eax, 80070000h
0x18008d9f4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008d9fb  lea     r9, a0; ": {0}"
0x18008da02  mov     [rbp+4Fh+NumberOfBytesRead], eax
0x18008da05  mov     r8d, esi
0x18008da08  lea     rax, [rbp+4Fh+NumberOfBytesRead]
0x18008da0c  mov     dl, 1
0x18008da0e  mov     qword ptr [rbp+4Fh+var_78], rax
0x18008da12  lea     rax, [rbp+4Fh+var_78]
0x18008da16  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; unsigned int
0x18008da1b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008da20  test    ebx, ebx
0x18008da22  jz      loc_18008DB38
0x18008da28  mov     edx, 15Bh; void *
0x18008da2d  mov     rcx, [rbp+57h]; this
0x18008da31  lea     r8, aOnecoreBaseCbs_31; "onecore\\base\\cbs\\parser\\helper.cpp"
0x18008da38  mov     r9d, ebx; char *
0x18008da3b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008da40  mov     edi, eax
0x18008da42  jmp     loc_18008D906
0x18008da47  mov     r14, qword ptr [rbp+4Fh+FileSize]
0x18008da4b  mov     rcx, r15; this
0x18008da4e  mov     rdx, r14; unsigned __int64
0x18008da51  call    ?Alloc@CMemoryAllocator@@QEAAPEAX_K@Z; CMemoryAllocator::Alloc(unsigned __int64)
0x18008da56  mov     r15, rax
0x18008da59  test    rax, rax
0x18008da5c  jnz     short loc_18008DAD2
0x18008da5e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008da65  mov     edi, 8007000Eh
0x18008da6a  mov     [rbp+4Fh+NumberOfBytesRead], edi
0x18008da6d  test    rcx, rcx
0x18008da70  jz      short loc_18008DAB5
0x18008da72  lea     rax, [rbp+4Fh+lpFileName]
0x18008da76  mov     r8d, esi
0x18008da79  lea     r9, aFailedToAlloca_16; "Failed to allocate memory for xml buffe"...
0x18008da80  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x18008da85  xor     edx, edx
0x18008da87  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18008da8c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008da93  lea     rax, [rbp+4Fh+NumberOfBytesRead]
0x18008da97  mov     qword ptr [rbp+4Fh+var_78], rax
0x18008da9b  lea     r9, asc_1802EE7AC; ": {}"
0x18008daa2  lea     rax, [rbp+4Fh+var_78]
0x18008daa6  mov     r8d, esi
0x18008daa9  mov     dl, 1
0x18008daab  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; int
0x18008dab0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008dab5  mov     rcx, [rbp+57h]; this
0x18008dab9  lea     r8, aOnecoreBaseCbs_31; "onecore\\base\\cbs\\parser\\helper.cpp"
0x18008dac0  mov     r9d, edi; char *
0x18008dac3  mov     edx, 163h; void *
0x18008dac8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008dacd  jmp     loc_18008D906
0x18008dad2  xor     edi, edi
0x18008dad4  test    r14, r14
0x18008dad7  jz      short loc_18008DB30
0x18008dad9  mov     ecx, 0FFFFFFFFh
0x18008dade  mov     rax, r14
0x18008dae1  sub     rax, rdi
0x18008dae4  cmp     rax, rcx
0x18008dae7  jbe     short loc_18008DAEE
0x18008dae9  mov     r8d, ecx
0x18008daec  jmp     short loc_18008DAF4
0x18008daee  mov     r8d, r14d
0x18008daf1  sub     r8d, edi; nNumberOfBytesToRead
0x18008daf4  lea     rdx, [rdi+r15]; lpBuffer
0x18008daf8  mov     [rbp+4Fh+NumberOfBytesRead], r8d
0x18008dafc  lea     r9, [rbp+4Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x18008db00  mov     qword ptr [rsp+0C0h+dwCreationDisposition], 0; lpOverlapped
0x18008db09  mov     rcx, rbx; hFile
0x18008db0c  call    cs:__imp_ReadFile
0x18008db13  nop     dword ptr [rax+rax+00h]
0x18008db18  test    eax, eax
0x18008db1a  jz      short loc_18008DB76
0x18008db1c  mov     eax, [rbp+4Fh+NumberOfBytesRead]
0x18008db1f  test    eax, eax
0x18008db21  jz      short loc_18008DB30
0x18008db23  add     rdi, rax
0x18008db26  mov     ecx, 0FFFFFFFFh
  ... truncated ...
```
