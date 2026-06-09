# GetFileContents(wchar_t const *,Windows::Auto<_LBLOB> *)

- ea: `0x1800914b4`
- end: `0x1800919e0`
- name: `?GetFileContents@@YAJPEB_WPEAV?$Auto@U_LBLOB@@@Windows@@@Z`
- size: `1324`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800bd218`
- `0x18026640c`
- `0x180284338`

## callees

- `0x180019bdc`
- `0x18002e280`
- `0x18003ec0c`
- `0x180050f18`
- `0x1800914b4`
- `0x180099390`
- `0x180099548`
- `0x1800aa0c4`
- `0x1800aa104`
- `0x1800aa16c`
- `0x1800eb920`
- `0x1800ef360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800915b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800915b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091855`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180091841`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180091841`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180091591`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180091591`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18009167d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18009167d`

## string_xrefs

- `0x18009150e`: `Not-null check failed: szWin32FilePath`
- `0x1800917e4`: `__tempE`
- `0x18009187b`: `Failed to read file {0}`
- `0x1800915da`: `Could not open file {0}`
- `0x180091651`: `__tempErr`
- `0x18009172d`: `__tempErr`
- `0x1800918ef`: `__tempErr`
- `0x180091946`: `dwBytesRead == dwSizeToRead`

## pseudocode

```c
__int64 __fastcall GetFileContents(const WCHAR *a1, __int128 *a2)
{
  const char *v3; // rax
  HANDLE FileW; // rdi
  signed int LastError; // ebx
  int v7; // edx
  unsigned int v8; // eax
  __int128 *v9; // rdx
  int v10; // edx
  unsigned int v11; // eax
  unsigned int v12; // ebx
  DWORD LowPart; // ebx
  int v14; // edx
  NTSTATUS v15; // eax
  unsigned int v16; // eax
  signed int v17; // ebx
  int v18; // edx
  unsigned int v19; // eax
  __int128 v20; // xmm2
  void *v21; // xmm3_8
  LPVOID v22; // xmm1_8
  int *v23; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v24; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpBuffer; // [rsp+58h] [rbp-A8h]
  const char *v26; // [rsp+60h] [rbp-A0h]
  HANDLE v27; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v28[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v29[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v30[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v31[4]; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR lpFileName; // [rsp+F0h] [rbp-10h] BYREF
  int v33; // [rsp+F8h] [rbp-8h] BYREF
  int v34; // [rsp+FCh] [rbp-4h] BYREF
  DWORD NumberOfBytesRead; // [rsp+100h] [rbp+0h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+108h] [rbp+8h] BYREF

  lpFileName = a1;
  v33 = 0;
  if ( !a1 )
  {
    lpBuffer = (LPVOID)58;
    *(_QWORD *)&v24 = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
    *((_QWORD *)&v24 + 1) = "GetFileContents";
    v3 = "Not-null check failed: szWin32FilePath";
LABEL_3:
    v26 = v3;
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v33,
             &v24);
  }
  if ( !a2 )
  {
    lpBuffer = (LPVOID)59;
    *(_QWORD *)&v24 = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
    *((_QWORD *)&v24 + 1) = "GetFileContents";
    v3 = "Not-null check failed: pContents";
    goto LABEL_3;
  }
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(a2);
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v27 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Could not open file {0}",
        (__int64)&lpFileName);
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      else
        v8 = LastError;
      v34 = v8;
      LOBYTE(v7) = 1;
      v23 = &v34;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v7,
        3,
        (unsigned int)": {0}",
        (__int64)&v23);
    }
    if ( LastError )
    {
      lpBuffer = (LPVOID)74;
      *(_QWORD *)&v24 = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
      *((_QWORD *)&v24 + 1) = "GetFileContents";
      v26 = "__tempErr";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v9 = &v24;
LABEL_26:
      v12 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
              &v33,
              v9,
              (unsigned int)LastError);
LABEL_46:
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v27);
      return v12;
    }
    goto LABEL_48;
  }
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Could not query file size for {0}",
        (__int64)&lpFileName);
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      else
        v11 = LastError;
      v34 = v11;
      LOBYTE(v10) = 1;
      v23 = &v34;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v10,
        3,
        (unsigned int)": {0}",
        (__int64)&v23);
    }
    if ( LastError )
    {
      v28[2] = 78;
      v28[0] = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
      v28[1] = "GetFileContents";
      v28[3] = "__tempErr";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v9 = (__int128 *)v28;
      goto LABEL_26;
    }
LABEL_48:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1800919DFLL);
  }
  LowPart = FileSize.LowPart;
  if ( FileSize.QuadPart > 0xFFFFFFFFLL )
  {
    LastError = -2147024673;
    v34 = -2147024673;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"File too large {0}",
        (__int64)&lpFileName);
      v23 = &v34;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {}",
        (__int64)&v23);
    }
    v29[2] = 82;
    v29[0] = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
    v9 = (__int128 *)v29;
    v29[1] = "GetFileContents";
    v29[3] = "__tempE";
    goto LABEL_26;
  }
  lpBuffer = 0;
  v24 = 0;
  v15 = RtlAllocateLBlob(FileSize.LowPart, &v24);
  if ( v15 < 0 )
  {
    v16 = ConvertNtStatusToHResult(v15);
    goto LABEL_45;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(FileW, lpBuffer, LowPart, &NumberOfBytesRead, 0) )
  {
    v17 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to read file {0}",
        (__int64)&lpFileName);
      if ( v17 > 0 )
        v19 = (unsigned __int16)v17 | 0x80070000;
      else
        v19 = v17;
      v34 = v19;
      LOBYTE(v18) = 1;
      v23 = &v34;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v18,
        3,
        (unsigned int)": {0}",
        (__int64)&v23);
    }
    if ( !v17 )
      goto LABEL_48;
    v30[2] = 91;
    v30[0] = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
    v30[1] = "GetFileContents";
    v30[3] = "__tempErr";
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    v16 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
            &v33,
            v30,
            (unsigned int)v17);
LABEL_45:
    v12 = v16;
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v24);
    goto LABEL_46;
  }
  if ( NumberOfBytesRead != LowPart )
  {
    v31[2] = 93;
    v31[0] = "onecore\\base\\servicing\\util\\servicinghelper.cpp";
    v31[1] = "GetFileContents";
    v31[3] = "dwBytesRead == dwSizeToRead";
    v16 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(
            &v33,
            v31,
            3221225473LL);
    goto LABEL_45;
  }
  v20 = *a2;
  *(_QWORD *)&v24 = LowPart;
  v21 = (void *)*((_QWORD *)a2 + 2);
  v22 = lpBuffer;
  *a2 = v24;
  *((_QWORD *)a2 + 2) = v22;
  v24 = v20;
  lpBuffer = v21;
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v24);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v27);
  return 0;
}

```

## disassembly

```asm
0x1800914b4  mov     [rsp-8+arg_10], rbx
0x1800914b9  push    rbp
0x1800914ba  push    rsi
0x1800914bb  push    rdi
0x1800914bc  push    r12
0x1800914be  push    r14
0x1800914c0  lea     rbp, [rsp-20h]
0x1800914c5  sub     rsp, 120h
0x1800914cc  mov     rax, cs:__security_cookie
0x1800914d3  xor     rax, rsp
0x1800914d6  mov     [rbp+40h+var_30], rax
0x1800914da  mov     [rbp+40h+lpFileName], rcx
0x1800914de  mov     rsi, rdx
0x1800914e1  mov     [rbp+40h+var_48], 0
0x1800914e8  test    rcx, rcx
0x1800914eb  jnz     short loc_18009152D
0x1800914ed  lea     rax, aOnecoreBaseSer_8; "onecore\\base\\servicing\\util\\servici"...
0x1800914f4  mov     [rsp+140h+lpBuffer], 3Ah ; ':'
0x1800914fd  mov     qword ptr [rsp+140h+var_F8], rax
0x180091502  lea     rax, aGetfilecontent; "GetFileContents"
0x180091509  mov     qword ptr [rsp+140h+var_F8+8], rax
0x18009150e  lea     rax, aNotNullCheckFa_26; "Not-null check failed: szWin32FilePath"
0x180091515  lea     rdx, [rsp+140h+var_F8]
0x18009151a  mov     [rsp+140h+var_E0], rax
0x18009151f  lea     rcx, [rbp+40h+var_48]
0x180091523  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180091528  jmp     loc_1800919B1
0x18009152d  test    rsi, rsi
0x180091530  jnz     short loc_18009155C
0x180091532  lea     rax, aOnecoreBaseSer_8; "onecore\\base\\servicing\\util\\servici"...
0x180091539  mov     [rsp+140h+lpBuffer], 3Bh ; ';'
0x180091542  mov     qword ptr [rsp+140h+var_F8], rax
0x180091547  lea     rax, aGetfilecontent; "GetFileContents"
0x18009154e  mov     qword ptr [rsp+140h+var_F8+8], rax
0x180091553  lea     rax, aNotNullCheckFa_99; "Not-null check failed: pContents"
0x18009155a  jmp     short loc_180091515
0x18009155c  mov     rcx, rsi
0x18009155f  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180091564  mov     rcx, [rbp+40h+lpFileName]; lpFileName
0x180091568  mov     r12d, 3
0x18009156e  mov     [rsp+140h+hTemplateFile], 0; hTemplateFile
0x180091577  xor     r9d, r9d; lpSecurityAttributes
0x18009157a  mov     [rsp+140h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180091582  mov     edx, 80000000h; dwDesiredAccess
0x180091587  mov     [rsp+140h+dwCreationDisposition], r12d; dwCreationDisposition
0x18009158c  lea     r8d, [r12-2]; dwShareMode
0x180091591  call    cs:__imp_CreateFileW
0x180091598  nop     dword ptr [rax+rax+00h]
0x18009159d  mov     rdi, rax
0x1800915a0  mov     [rsp+140h+var_D8], rax
0x1800915a5  inc     rax
0x1800915a8  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800915ae  jnz     loc_18009166E
0x1800915b4  call    cs:__imp_GetLastError
0x1800915bb  nop     dword ptr [rax+rax+00h]
0x1800915c0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800915c7  mov     edi, 80070000h
0x1800915cc  mov     ebx, eax
0x1800915ce  test    rcx, rcx
0x1800915d1  jz      short loc_180091628
0x1800915d3  lea     rax, [rbp+40h+lpFileName]
0x1800915d7  mov     r8d, r12d
0x1800915da  lea     r9, aCouldNotOpenFi; "Could not open file {0}"
0x1800915e1  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x1800915e6  xor     edx, edx
0x1800915e8  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800915ed  test    ebx, ebx
0x1800915ef  jg      short loc_1800915F5
0x1800915f1  mov     eax, ebx
0x1800915f3  jmp     short loc_1800915FA
0x1800915f5  movzx   eax, bx
0x1800915f8  or      eax, edi
0x1800915fa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180091601  lea     r9, a0; ": {0}"
0x180091608  mov     [rbp+40h+var_44], eax
0x18009160b  mov     r8d, r12d
0x18009160e  lea     rax, [rbp+40h+var_44]
0x180091612  mov     dl, 1
0x180091614  mov     [rsp+140h+var_100], rax
0x180091619  lea     rax, [rsp+140h+var_100]
0x18009161e  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x180091623  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180091628  test    ebx, ebx
0x18009162a  jz      loc_1800919D5
0x180091630  lea     rax, aOnecoreBaseSer_8; "onecore\\base\\servicing\\util\\servici"...
0x180091637  mov     [rsp+140h+lpBuffer], 4Ah ; 'J'
0x180091640  mov     qword ptr [rsp+140h+var_F8], rax
0x180091645  lea     rax, aGetfilecontent; "GetFileContents"
0x18009164c  mov     qword ptr [rsp+140h+var_F8+8], rax
0x180091651  lea     rax, aTemperr; "__tempErr"
0x180091658  mov     [rsp+140h+var_E0], rax
0x18009165d  jle     short loc_180091664
0x18009165f  movzx   ebx, bx
0x180091662  or      ebx, edi
0x180091664  lea     rdx, [rsp+140h+var_F8]
0x180091669  jmp     loc_180091744
0x18009166e  lea     rdx, [rbp+40h+FileSize]; lpFileSize
0x180091672  mov     qword ptr [rbp+40h+FileSize], 0
0x18009167a  mov     rcx, rdi; hFile
0x18009167d  call    cs:__imp_GetFileSizeEx
0x180091684  nop     dword ptr [rax+rax+00h]
0x180091689  test    eax, eax
0x18009168b  jnz     loc_180091757
0x180091691  call    cs:__imp_GetLastError
0x180091698  nop     dword ptr [rax+rax+00h]
0x18009169d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800916a4  mov     edi, 80070000h
0x1800916a9  mov     ebx, eax
0x1800916ab  test    rcx, rcx
0x1800916ae  jz      short loc_180091705
0x1800916b0  lea     rax, [rbp+40h+lpFileName]
0x1800916b4  mov     r8d, r12d
0x1800916b7  lea     r9, aCouldNotQueryF; "Could not query file size for {0}"
0x1800916be  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x1800916c3  xor     edx, edx
0x1800916c5  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800916ca  test    ebx, ebx
0x1800916cc  jg      short loc_1800916D2
0x1800916ce  mov     eax, ebx
0x1800916d0  jmp     short loc_1800916D7
0x1800916d2  movzx   eax, bx
0x1800916d5  or      eax, edi
0x1800916d7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800916de  lea     r9, a0; ": {0}"
0x1800916e5  mov     [rbp+40h+var_44], eax
0x1800916e8  mov     r8d, r12d
0x1800916eb  lea     rax, [rbp+40h+var_44]
0x1800916ef  mov     dl, 1
0x1800916f1  mov     [rsp+140h+var_100], rax
0x1800916f6  lea     rax, [rsp+140h+var_100]
0x1800916fb  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x180091700  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180091705  test    ebx, ebx
0x180091707  jz      loc_1800919D5
0x18009170d  lea     rax, aOnecoreBaseSer_8; "onecore\\base\\servicing\\util\\servici"...
0x180091714  mov     [rbp+40h+var_C0], 4Eh ; 'N'
0x18009171c  mov     [rsp+140h+var_D0], rax
0x180091721  lea     rax, aGetfilecontent; "GetFileContents"
0x180091728  mov     [rsp+140h+var_C8], rax
0x18009172d  lea     rax, aTemperr; "__tempErr"
0x180091734  mov     [rbp+40h+var_B8], rax
0x180091738  jle     short loc_18009173F
0x18009173a  movzx   ebx, bx
0x18009173d  or      ebx, edi
0x18009173f  lea     rdx, [rsp+140h+var_D0]
0x180091744  mov     r8d, ebx
0x180091747  lea     rcx, [rbp+40h+var_48]
0x18009174b  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180091750  mov     ebx, eax
0x180091752  jmp     loc_180091962
0x180091757  mov     rbx, qword ptr [rbp+40h+FileSize]
0x18009175b  mov     eax, 0FFFFFFFFh
0x180091760  cmp     rbx, rax
0x180091763  jle     loc_1800917F4
0x180091769  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180091770  mov     ebx, 800700DFh
0x180091775  mov     [rbp+40h+var_44], ebx
0x180091778  test    rcx, rcx
0x18009177b  jz      short loc_1800917C2
0x18009177d  lea     rax, [rbp+40h+lpFileName]
0x180091781  mov     r8d, r12d
0x180091784  lea     r9, aFileTooLarge0; "File too large {0}"
0x18009178b  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x180091790  xor     edx, edx
0x180091792  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180091797  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009179e  lea     rax, [rbp+40h+var_44]
0x1800917a2  mov     [rsp+140h+var_100], rax
0x1800917a7  lea     r9, asc_1802EE7AC; ": {}"
0x1800917ae  lea     rax, [rsp+140h+var_100]
0x1800917b3  mov     r8d, r12d
0x1800917b6  mov     dl, 1
0x1800917b8  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x1800917bd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800917c2  lea     rax, aOnecoreBaseSer_8; "onecore\\base\\servicing\\util\\servici"...
0x1800917c9  mov     [rbp+40h+var_A0], 52h ; 'R'
0x1800917d1  mov     [rbp+40h+var_B0], rax
0x1800917d5  lea     rdx, [rbp+40h+var_B0]
0x1800917d9  lea     rax, aGetfilecontent; "GetFileContents"
0x1800917e0  mov     [rbp+40h+var_A8], rax
0x1800917e4  lea     rax, aTempe; "__tempE"
0x1800917eb  mov     [rbp+40h+var_98], rax
0x1800917ef  jmp     loc_180091744
0x1800917f4  xorps   xmm0, xmm0
0x1800917f7  mov     ecx, ebx
0x1800917f9  xor     eax, eax
0x1800917fb  mov     r14d, ebx
0x1800917fe  lea     rdx, [rsp+140h+var_F8]
0x180091803  mov     [rsp+140h+lpBuffer], rax
0x180091808  movups  [rsp+140h+var_F8], xmm0
0x18009180d  call    RtlAllocateLBlob
0x180091812  test    eax, eax
0x180091814  jns     short loc_180091822
0x180091816  mov     ecx, eax; Status
0x180091818  call    ConvertNtStatusToHResult
0x18009181d  jmp     loc_180091956
0x180091822  mov     rdx, [rsp+140h+lpBuffer]; lpBuffer
0x180091827  lea     r9, [rbp+40h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009182b  mov     r8d, ebx; nNumberOfBytesToRead
0x18009182e  mov     [rbp+40h+NumberOfBytesRead], 0
0x180091835  mov     rcx, rdi; hFile
0x180091838  mov     qword ptr [rsp+140h+dwCreationDisposition], 0; lpOverlapped
0x180091841  call    cs:__imp_ReadFile
0x180091848  nop     dword ptr [rax+rax+00h]
0x18009184d  test    eax, eax
0x18009184f  jnz     loc_180091915
0x180091855  call    cs:__imp_GetLastError
0x18009185c  nop     dword ptr [rax+rax+00h]
0x180091861  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180091868  mov     edi, 80070000h
0x18009186d  mov     ebx, eax
0x18009186f  test    rcx, rcx
0x180091872  jz      short loc_1800918C9
0x180091874  lea     rax, [rbp+40h+lpFileName]
0x180091878  mov     r8d, r12d
0x18009187b  lea     r9, aFailedToReadFi; "Failed to read file {0}"
0x180091882  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x180091887  xor     edx, edx
0x180091889  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18009188e  test    ebx, ebx
0x180091890  jg      short loc_180091896
0x180091892  mov     eax, ebx
0x180091894  jmp     short loc_18009189B
0x180091896  movzx   eax, bx
0x180091899  or      eax, edi
0x18009189b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800918a2  lea     r9, a0; ": {0}"
0x1800918a9  mov     [rbp+40h+var_44], eax
0x1800918ac  mov     r8d, r12d
0x1800918af  lea     rax, [rbp+40h+var_44]
0x1800918b3  mov     dl, 1
0x1800918b5  mov     [rsp+140h+var_100], rax
0x1800918ba  lea     rax, [rsp+140h+var_100]
0x1800918bf  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x1800918c4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800918c9  test    ebx, ebx
0x1800918cb  jz      loc_1800919D5
0x1800918d1  mov     [rbp+40h+var_80], 5Bh ; '['
0x1800918d9  lea     rax, aOnecoreBaseSer_8; "onecore\\base\\servicing\\util\\servici"...
0x1800918e0  mov     [rbp+40h+var_90], rax
0x1800918e4  lea     rax, aGetfilecontent; "GetFileContents"
0x1800918eb  mov     [rbp+40h+var_88], rax
0x1800918ef  lea     rax, aTemperr; "__tempErr"
0x1800918f6  mov     [rbp+40h+var_78], rax
0x1800918fa  test    ebx, ebx
0x1800918fc  jle     short loc_180091903
0x1800918fe  movzx   ebx, bx
0x180091901  or      ebx, edi
0x180091903  mov     r8d, ebx
0x180091906  lea     rdx, [rbp+40h+var_90]
0x18009190a  lea     rcx, [rbp+40h+var_48]
0x18009190e  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180091913  jmp     short loc_180091956
0x180091915  cmp     [rbp+40h+NumberOfBytesRead], ebx
0x180091918  jz      short loc_180091970
0x18009191a  lea     rax, aOnecoreBaseSer_8; "onecore\\base\\servicing\\util\\servici"...
0x180091921  mov     [rbp+40h+var_60], 5Dh ; ']'
0x180091929  mov     [rbp+40h+var_70], rax
0x18009192d  lea     rdx, [rbp+40h+var_70]
0x180091931  lea     rax, aGetfilecontent; "GetFileContents"
0x180091938  mov     r8d, 0C0000001h
0x18009193e  mov     [rbp+40h+var_68], rax
0x180091942  lea     rcx, [rbp+40h+var_48]
0x180091946  lea     rax, aDwbytesreadDws; "dwBytesRead == dwSizeToRead"
0x18009194d  mov     [rbp+40h+var_58], rax
0x180091951  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180091956  lea     rcx, [rsp+140h+var_F8]
0x18009195b  mov     ebx, eax
0x18009195d  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180091962  lea     rcx, [rsp+140h+var_D8]
0x180091967  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18009196c  mov     eax, ebx
0x18009196e  jmp     short loc_1800919B1
0x180091970  movups  xmm2, xmmword ptr [rsi]
0x180091973  lea     rcx, [rsp+140h+var_F8]
0x180091978  mov     qword ptr [rsp+140h+var_F8], r14
0x18009197d  movsd   xmm3, qword ptr [rsi+10h]
0x180091982  movups  xmm0, [rsp+140h+var_F8]
0x180091987  movsd   xmm1, [rsp+140h+lpBuffer]
0x18009198d  movups  xmmword ptr [rsi], xmm0
0x180091990  movsd   qword ptr [rsi+10h], xmm1
0x180091995  movups  [rsp+140h+var_F8], xmm2
0x18009199a  movsd   [rsp+140h+lpBuffer], xmm3
0x1800919a0  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800919a5  lea     rcx, [rsp+140h+var_D8]
0x1800919aa  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1800919af  xor     eax, eax
0x1800919b1  mov     rcx, [rbp+40h+var_30]
0x1800919b5  xor     rcx, rsp; StackCookie
0x1800919b8  call    __security_check_cookie
0x1800919bd  mov     rbx, [rsp+140h+arg_10]
0x1800919c5  add     rsp, 120h
0x1800919cc  pop     r14
0x1800919ce  pop     r12
0x1800919d0  pop     rdi
0x1800919d1  pop     rsi
0x1800919d2  pop     rbp
0x1800919d3  retn
0x1800919d5  mov     ecx, 0C00000E5h; int
0x1800919da  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
  ... truncated ...
```
