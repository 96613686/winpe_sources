# FileExecutableArchitecture

- ea: `0x180105354`
- end: `0x180105950`
- name: `FileExecutableArchitecture`
- size: `1532`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1801efae0`

## callees

- `0x18002e280`
- `0x180055fc8`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1800ec920`
- `0x1801021a4`
- `0x180105354`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801054ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801055a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801056ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801057a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801054ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801055a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801056ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801057a2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180105590`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18010578e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180105590`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18010578e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801056d7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801056d7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801054bf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801054bf`

## string_xrefs

- `0x18010550f`: `Failed to open file: {}`
- `0x1801057c4`: `Failed to read NT header from file: {}`
- `0x1801055c6`: `Failed to read DOS header from file: {}`
- `0x18010566c`: `Read invalid DOS header from file: {}`
- `0x18010584f`: `Read invalid NT header from file: {}`

## pseudocode

```c
__int64 __fastcall FileExecutableArchitecture(LPCWSTR lpFileName, _WORD *a2)
{
  unsigned int v4; // ebx
  int v5; // edx
  __int64 v6; // rdx
  int v7; // edx
  HANDLE FileW; // rax
  HANDLE v9; // rbx
  signed int LastError; // ebx
  int v11; // edx
  unsigned int v12; // eax
  __int64 v13; // rdx
  int v14; // edx
  unsigned int v15; // eax
  int v16; // edx
  __int64 v17; // rdx
  int v18; // edx
  unsigned int v19; // eax
  int v20; // edx
  int v21; // r8d
  int v22; // r9d
  int v23; // edx
  unsigned int v24; // eax
  int v25; // edx
  int v26; // edx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  unsigned int v30[2]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR v32; // [rsp+50h] [rbp-B0h] BYREF
  int v33; // [rsp+58h] [rbp-A8h] BYREF
  DWORD NumberOfBytesRead; // [rsp+5Ch] [rbp-A4h] BYREF
  _WORD Buffer[30]; // [rsp+60h] [rbp-A0h] BYREF
  LONG lDistanceToMove; // [rsp+9Ch] [rbp-64h]
  int v37; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v38; // [rsp+A4h] [rbp-5Ch]
  _WORD v39[90]; // [rsp+FCh] [rbp-4h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v32 = lpFileName;
  NumberOfBytesRead = 0;
  memset_0(Buffer, 0, 0x40u);
  memset_0(&v37, 0, 0x108u);
  if ( lpFileName )
  {
    if ( !a2 )
    {
      v4 = -2147467261;
      v33 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No architecture result specified");
        hFile = &v33;
        LOBYTE(v7) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v7,
          3,
          (unsigned int)": {}",
          (__int64)&hFile);
      }
      v6 = 180;
      goto LABEL_5;
    }
    hFile = 0;
    FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
      &hFile,
      FileW);
    v9 = hFile;
    if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      if ( ReadFile(hFile, Buffer, 0x40u, &NumberOfBytesRead, 0) )
      {
        if ( Buffer[0] == 23117 )
        {
          if ( SetFilePointer(v9, lDistanceToMove, 0, 0) == -1 )
          {
            LastError = GetLastError();
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to seek the NT header in file: {}",
                (__int64)&v32);
              if ( LastError > 0 )
                v19 = (unsigned __int16)LastError | 0x80070000;
              else
                v19 = LastError;
              v33 = v19;
              LOBYTE(v18) = 1;
              *(_QWORD *)v30 = &v33;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v18,
                3,
                (unsigned int)": {0}",
                (__int64)v30);
            }
            if ( LastError )
            {
              v13 = 196;
              goto LABEL_26;
            }
            goto LABEL_61;
          }
          if ( !ReadFile(v9, &v37, 0x108u, &NumberOfBytesRead, 0) )
          {
            LastError = GetLastError();
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to read NT header from file: {}",
                (__int64)&v32);
              if ( LastError > 0 )
                v24 = (unsigned __int16)LastError | 0x80070000;
              else
                v24 = LastError;
              v33 = v24;
              LOBYTE(v23) = 1;
              *(_QWORD *)v30 = &v33;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v23,
                3,
                (unsigned int)": {0}",
                (__int64)v30);
            }
            if ( LastError )
            {
              v13 = 199;
              goto LABEL_26;
            }
            goto LABEL_61;
          }
          if ( v37 == 17744 )
          {
            if ( v39[0] == 1 || v39[0] == 2 || v39[0] == 3 || v39[0] != 5 && v39[0] != 7 )
            {
              *a2 = v38;
              goto LABEL_61;
            }
            v4 = -2147024885;
            v33 = -2147024885;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<unsigned short,wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                v20,
                v21,
                v22,
                (__int64)v39,
                (__int64)&v32);
              *(_QWORD *)v30 = &v33;
              LOBYTE(v26) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v26,
                3,
                (unsigned int)": {}",
                (__int64)v30);
            }
            v17 = 221;
          }
          else
          {
            v4 = -2147024885;
            v33 = -2147024885;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Read invalid NT header from file: {}",
                (__int64)&v32);
              *(_QWORD *)v30 = &v33;
              LOBYTE(v25) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v25,
                3,
                (unsigned int)": {}",
                (__int64)v30);
            }
            v17 = 202;
          }
        }
        else
        {
          v4 = -2147024885;
          v33 = -2147024885;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Read invalid DOS header from file: {}",
              (__int64)&v32);
            *(_QWORD *)v30 = &v33;
            LOBYTE(v16) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v16,
              3,
              (unsigned int)": {}",
              (__int64)v30);
          }
          v17 = 193;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
          (const char *)0x8007000BLL,
          dwCreationDispositiona);
        goto LABEL_62;
      }
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to read DOS header from file: {}",
          (__int64)&v32);
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
        else
          v15 = LastError;
        v33 = v15;
        LOBYTE(v14) = 1;
        *(_QWORD *)v30 = &v33;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v14,
          3,
          (unsigned int)": {0}",
          (__int64)v30);
      }
      if ( LastError )
      {
        v13 = 190;
        goto LABEL_26;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to open file: {}",
          (__int64)&v32);
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        else
          v12 = LastError;
        v33 = v12;
        LOBYTE(v11) = 1;
        *(_QWORD *)v30 = &v33;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v11,
          3,
          (unsigned int)": {0}",
          (__int64)v30);
      }
      if ( LastError )
      {
        v13 = 186;
LABEL_26:
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v13,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
               (const char *)(unsigned int)LastError,
               dwCreationDispositiona);
LABEL_62:
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
        return v4;
      }
    }
LABEL_61:
    v4 = 0;
    goto LABEL_62;
  }
  v4 = -2147024809;
  v33 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No file specified");
    hFile = &v33;
    LOBYTE(v5) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v5,
      3,
      (unsigned int)": {}",
      (__int64)&hFile);
  }
  v6 = 179;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
    (const char *)v4,
    dwCreationDisposition);
  return v4;
}

```

## disassembly

```asm
0x180105354  mov     [rsp-8+arg_10], rbx
0x180105359  push    rbp
0x18010535a  push    rsi
0x18010535b  push    rdi
0x18010535c  lea     rbp, [rsp-0C0h]
0x180105364  sub     rsp, 1C0h
0x18010536b  mov     rax, cs:__security_cookie
0x180105372  xor     rax, rsp
0x180105375  mov     [rbp+0D0h+var_20], rax
0x18010537c  mov     rsi, rdx
0x18010537f  mov     [rsp+1D0h+var_180], rcx
0x180105384  xor     edx, edx; Val
0x180105386  mov     [rsp+1D0h+NumberOfBytesRead], 0
0x18010538e  mov     rbx, rcx
0x180105391  lea     rcx, [rsp+1D0h+Buffer]; void *
0x180105396  lea     r8d, [rdx+40h]; Size
0x18010539a  call    memset_0
0x18010539f  xor     edx, edx; Val
0x1801053a1  lea     rcx, [rbp+0D0h+var_130]; void *
0x1801053a5  mov     r8d, 108h; Size
0x1801053ab  call    memset_0
0x1801053b0  test    rbx, rbx
0x1801053b3  jnz     short loc_18010542C
0x1801053b5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801053bc  mov     ebx, 80070057h
0x1801053c1  mov     [rsp+1D0h+var_178], ebx
0x1801053c5  test    rcx, rcx
0x1801053c8  jz      short loc_18010540C
0x1801053ca  mov     edi, 3
0x1801053cf  lea     r9, aNoFileSpecifie; "No file specified"
0x1801053d6  mov     r8d, edi
0x1801053d9  xor     edx, edx
0x1801053db  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801053e0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801053e7  lea     rax, [rsp+1D0h+var_178]
0x1801053ec  mov     [rsp+1D0h+hFile], rax
0x1801053f1  lea     r9, asc_1802EE7AC; ": {}"
0x1801053f8  lea     rax, [rsp+1D0h+hFile]
0x1801053fd  mov     r8d, edi
0x180105400  mov     dl, 1
0x180105402  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax; int
0x180105407  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010540c  mov     edx, 0B3h; void *
0x180105411  mov     rcx, [rbp+0D8h]; this
0x180105418  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18010541f  mov     r9d, ebx; char *
0x180105422  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105427  jmp     loc_18010592B
0x18010542c  test    rsi, rsi
0x18010542f  jnz     short loc_18010548D
0x180105431  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105438  mov     ebx, 80004003h
0x18010543d  mov     [rsp+1D0h+var_178], ebx
0x180105441  test    rcx, rcx
0x180105444  jz      short loc_180105486
0x180105446  lea     edi, [rsi+3]
0x180105449  xor     edx, edx
0x18010544b  mov     r8d, edi
0x18010544e  lea     r9, aNoArchitecture_0; "No architecture result specified"
0x180105455  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010545a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105461  lea     rax, [rsp+1D0h+var_178]
0x180105466  mov     [rsp+1D0h+hFile], rax
0x18010546b  lea     r9, asc_1802EE7AC; ": {}"
0x180105472  lea     rax, [rsp+1D0h+hFile]
0x180105477  mov     r8d, edi
0x18010547a  mov     dl, 1
0x18010547c  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x180105481  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180105486  mov     edx, 0B4h
0x18010548b  jmp     short loc_180105411
0x18010548d  mov     edi, 3
0x180105492  mov     [rsp+1D0h+hTemplateFile], 0; hTemplateFile
0x18010549b  mov     [rsp+1D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1801054a3  xor     r9d, r9d; lpSecurityAttributes
0x1801054a6  mov     edx, 80000000h; dwDesiredAccess
0x1801054ab  mov     [rsp+1D0h+hFile], 0
0x1801054b4  mov     rcx, rbx; lpFileName
0x1801054b7  mov     [rsp+1D0h+dwCreationDisposition], edi; dwCreationDisposition
0x1801054bb  lea     r8d, [rdi-2]; dwShareMode
0x1801054bf  call    cs:__imp_CreateFileW
0x1801054c6  nop     dword ptr [rax+rax+00h]
0x1801054cb  mov     rdx, rax
0x1801054ce  lea     rcx, [rsp+1D0h+hFile]
0x1801054d3  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x1801054d8  mov     rbx, [rsp+1D0h+hFile]
0x1801054dd  lea     rax, [rbx+1]
0x1801054e1  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801054e7  jnz     loc_180105574
0x1801054ed  call    cs:__imp_GetLastError
0x1801054f4  nop     dword ptr [rax+rax+00h]
0x1801054f9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105500  mov     ebx, eax
0x180105502  test    rcx, rcx
0x180105505  jz      short loc_180105562
0x180105507  lea     rax, [rsp+1D0h+var_180]
0x18010550c  mov     r8d, edi
0x18010550f  lea     r9, aFailedToOpenFi_1; "Failed to open file: {}"
0x180105516  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18010551b  xor     edx, edx
0x18010551d  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180105522  test    ebx, ebx
0x180105524  jg      short loc_18010552A
0x180105526  mov     eax, ebx
0x180105528  jmp     short loc_180105532
0x18010552a  movzx   eax, bx
0x18010552d  or      eax, 80070000h
0x180105532  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105539  lea     r9, a0; ": {0}"
0x180105540  mov     [rsp+1D0h+var_178], eax
0x180105544  mov     r8d, edi
0x180105547  lea     rax, [rsp+1D0h+var_178]
0x18010554c  mov     dl, 1
0x18010554e  mov     qword ptr [rsp+1D0h+var_190], rax
0x180105553  lea     rax, [rsp+1D0h+var_190]
0x180105558  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18010555d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180105562  test    ebx, ebx
0x180105564  jz      loc_18010591F
0x18010556a  mov     edx, 0BAh
0x18010556f  jmp     loc_180105626
0x180105574  lea     r9, [rsp+1D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180105579  mov     qword ptr [rsp+1D0h+dwCreationDisposition], 0; lpOverlapped
0x180105582  mov     r8d, 40h ; '@'; nNumberOfBytesToRead
0x180105588  lea     rdx, [rsp+1D0h+Buffer]; lpBuffer
0x18010558d  mov     rcx, rbx; hFile
0x180105590  call    cs:__imp_ReadFile
0x180105597  nop     dword ptr [rax+rax+00h]
0x18010559c  test    eax, eax
0x18010559e  jnz     loc_180105643
0x1801055a4  call    cs:__imp_GetLastError
0x1801055ab  nop     dword ptr [rax+rax+00h]
0x1801055b0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801055b7  mov     ebx, eax
0x1801055b9  test    rcx, rcx
0x1801055bc  jz      short loc_180105619
0x1801055be  lea     rax, [rsp+1D0h+var_180]
0x1801055c3  mov     r8d, edi
0x1801055c6  lea     r9, aFailedToReadDo; "Failed to read DOS header from file: {}"
0x1801055cd  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x1801055d2  xor     edx, edx
0x1801055d4  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801055d9  test    ebx, ebx
0x1801055db  jg      short loc_1801055E1
0x1801055dd  mov     eax, ebx
0x1801055df  jmp     short loc_1801055E9
0x1801055e1  movzx   eax, bx
0x1801055e4  or      eax, 80070000h
0x1801055e9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801055f0  lea     r9, a0; ": {0}"
0x1801055f7  mov     [rsp+1D0h+var_178], eax
0x1801055fb  mov     r8d, edi
0x1801055fe  lea     rax, [rsp+1D0h+var_178]
0x180105603  mov     dl, 1
0x180105605  mov     qword ptr [rsp+1D0h+var_190], rax
0x18010560a  lea     rax, [rsp+1D0h+var_190]
0x18010560f  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax; unsigned int
0x180105614  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180105619  test    ebx, ebx
0x18010561b  jz      loc_18010591F
0x180105621  mov     edx, 0BEh; void *
0x180105626  mov     rcx, [rbp+0D8h]; this
0x18010562d  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180105634  mov     r9d, ebx; char *
0x180105637  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010563c  mov     ebx, eax
0x18010563e  jmp     loc_180105921
0x180105643  mov     eax, 5A4Dh
0x180105648  cmp     [rsp+1D0h+Buffer], ax
0x18010564d  jz      short loc_1801056CB
0x18010564f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105656  mov     ebx, 8007000Bh
0x18010565b  mov     [rsp+1D0h+var_178], ebx
0x18010565f  test    rcx, rcx
0x180105662  jz      short loc_1801056AB
0x180105664  lea     rax, [rsp+1D0h+var_180]
0x180105669  mov     r8d, edi
0x18010566c  lea     r9, aReadInvalidDos; "Read invalid DOS header from file: {}"
0x180105673  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x180105678  xor     edx, edx
0x18010567a  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18010567f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105686  lea     rax, [rsp+1D0h+var_178]
0x18010568b  mov     qword ptr [rsp+1D0h+var_190], rax
0x180105690  lea     r9, asc_1802EE7AC; ": {}"
0x180105697  lea     rax, [rsp+1D0h+var_190]
0x18010569c  mov     r8d, edi
0x18010569f  mov     dl, 1
0x1801056a1  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax; int
0x1801056a6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801056ab  mov     edx, 0C1h; void *
0x1801056b0  mov     rcx, [rbp+0D8h]; this
0x1801056b7  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1801056be  mov     r9d, ebx; char *
0x1801056c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801056c6  jmp     loc_180105921
0x1801056cb  mov     edx, [rbp+0D0h+lDistanceToMove]; lDistanceToMove
0x1801056ce  xor     r9d, r9d; dwMoveMethod
0x1801056d1  xor     r8d, r8d; lpDistanceToMoveHigh
0x1801056d4  mov     rcx, rbx; hFile
0x1801056d7  call    cs:__imp_SetFilePointer
0x1801056de  nop     dword ptr [rax+rax+00h]
0x1801056e3  cmp     eax, 0FFFFFFFFh
0x1801056e6  jnz     loc_180105773
0x1801056ec  call    cs:__imp_GetLastError
0x1801056f3  nop     dword ptr [rax+rax+00h]
0x1801056f8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801056ff  mov     ebx, eax
0x180105701  test    rcx, rcx
0x180105704  jz      short loc_180105761
0x180105706  lea     rax, [rsp+1D0h+var_180]
0x18010570b  mov     r8d, edi
0x18010570e  lea     r9, aFailedToSeekTh; "Failed to seek the NT header in file: {"...
0x180105715  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18010571a  xor     edx, edx
0x18010571c  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180105721  test    ebx, ebx
0x180105723  jg      short loc_180105729
0x180105725  mov     eax, ebx
0x180105727  jmp     short loc_180105731
0x180105729  movzx   eax, bx
0x18010572c  or      eax, 80070000h
0x180105731  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105738  lea     r9, a0; ": {0}"
0x18010573f  mov     [rsp+1D0h+var_178], eax
0x180105743  mov     r8d, edi
0x180105746  lea     rax, [rsp+1D0h+var_178]
0x18010574b  mov     dl, 1
0x18010574d  mov     qword ptr [rsp+1D0h+var_190], rax
0x180105752  lea     rax, [rsp+1D0h+var_190]
0x180105757  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18010575c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180105761  test    ebx, ebx
0x180105763  jz      loc_18010591F
0x180105769  mov     edx, 0C4h
0x18010576e  jmp     loc_180105626
0x180105773  lea     r9, [rsp+1D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180105778  mov     qword ptr [rsp+1D0h+dwCreationDisposition], 0; lpOverlapped
0x180105781  mov     r8d, 108h; nNumberOfBytesToRead
0x180105787  lea     rdx, [rbp+0D0h+var_130]; lpBuffer
0x18010578b  mov     rcx, rbx; hFile
0x18010578e  call    cs:__imp_ReadFile
0x180105795  nop     dword ptr [rax+rax+00h]
0x18010579a  test    eax, eax
0x18010579c  jnz     loc_180105829
0x1801057a2  call    cs:__imp_GetLastError
0x1801057a9  nop     dword ptr [rax+rax+00h]
0x1801057ae  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801057b5  mov     ebx, eax
0x1801057b7  test    rcx, rcx
0x1801057ba  jz      short loc_180105817
0x1801057bc  lea     rax, [rsp+1D0h+var_180]
0x1801057c1  mov     r8d, edi
0x1801057c4  lea     r9, aFailedToReadNt; "Failed to read NT header from file: {}"
0x1801057cb  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x1801057d0  xor     edx, edx
0x1801057d2  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801057d7  test    ebx, ebx
0x1801057d9  jg      short loc_1801057DF
0x1801057db  mov     eax, ebx
0x1801057dd  jmp     short loc_1801057E7
0x1801057df  movzx   eax, bx
0x1801057e2  or      eax, 80070000h
0x1801057e7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801057ee  lea     r9, a0; ": {0}"
0x1801057f5  mov     [rsp+1D0h+var_178], eax
0x1801057f9  mov     r8d, edi
0x1801057fc  lea     rax, [rsp+1D0h+var_178]
0x180105801  mov     dl, 1
0x180105803  mov     qword ptr [rsp+1D0h+var_190], rax
0x180105808  lea     rax, [rsp+1D0h+var_190]
0x18010580d  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x180105812  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180105817  test    ebx, ebx
0x180105819  jz      loc_18010591F
0x18010581f  mov     edx, 0C7h
0x180105824  jmp     loc_180105626
0x180105829  cmp     [rbp+0D0h+var_130], 4550h
0x180105830  jz      short loc_180105898
0x180105832  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105839  mov     ebx, 8007000Bh
0x18010583e  mov     [rsp+1D0h+var_178], ebx
0x180105842  test    rcx, rcx
0x180105845  jz      short loc_18010588E
0x180105847  lea     rax, [rsp+1D0h+var_180]
0x18010584c  mov     r8d, edi
0x18010584f  lea     r9, aReadInvalidNtH; "Read invalid NT header from file: {}"
0x180105856  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18010585b  xor     edx, edx
0x18010585d  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180105862  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105869  lea     rax, [rsp+1D0h+var_178]
0x18010586e  mov     qword ptr [rsp+1D0h+var_190], rax
0x180105873  lea     r9, asc_1802EE7AC; ": {}"
0x18010587a  lea     rax, [rsp+1D0h+var_190]
0x18010587f  mov     r8d, edi
0x180105882  mov     dl, 1
0x180105884  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x180105889  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010588e  mov     edx, 0CAh
  ... truncated ...
```
