# RenameManifestsIfNameDoesNotMatchIdentity(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x1800cb9b4`
- end: `0x1800cbe53`
- name: `?RenameManifestsIfNameDoesNotMatchIdentity@@YAJPEB_W000@Z`
- size: `1183`
- prototype: `__int64 __fastcall(const wchar_t *String2, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x18012737c`
- `0x18018f688`

## callees

- `0x18000b46c`
- `0x180013250`
- `0x1800261e0`
- `0x180056e00`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800cb9b4`
- `0x1800eb920`
- `0x1802cf7a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cbb82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cbc80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cbd7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cbb82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cbc80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cbd7c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800cbb6e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800cbc6c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800cbd68`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800cbb6e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800cbc6c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800cbd68`

## string_xrefs

- `0x1800cbba9`: `Failed to move file from:{} to {}`
- `0x1800cbca7`: `Failed to move file from:{} to {}`
- `0x1800cbda3`: `Failed to move file from:{} to {}`

## pseudocode

```c
__int64 __fastcall RenameManifestsIfNameDoesNotMatchIdentity(
        const wchar_t *String2,
        WCHAR *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  unsigned int v6; // ebx
  int v7; // edx
  __int64 v8; // rdx
  int v9; // edx
  __int64 v10; // r9
  const wchar_t *v11; // rax
  unsigned int v12; // r9d
  int v13; // eax
  __int64 v14; // rdx
  int v15; // edi
  __int64 v16; // rdx
  LPCWSTR v17; // rdi
  signed int v18; // ebx
  int v19; // edx
  unsigned int v20; // eax
  __int64 v21; // rdx
  unsigned __int64 v22; // r9
  LPCWSTR v23; // rdi
  int v24; // edx
  unsigned int v25; // eax
  LPCWSTR v26; // rbx
  signed int LastError; // esi
  int v28; // edx
  unsigned int v29; // eax
  unsigned int v31; // [rsp+20h] [rbp-39h]
  int v32[2]; // [rsp+30h] [rbp-29h] BYREF
  int *v33; // [rsp+38h] [rbp-21h] BYREF
  unsigned int v34[2]; // [rsp+40h] [rbp-19h] BYREF
  LPCWSTR v35; // [rsp+48h] [rbp-11h] BYREF
  LPCWSTR v36; // [rsp+50h] [rbp-9h] BYREF
  LPCWSTR lpNewFileName; // [rsp+58h] [rbp-1h] BYREF
  LPCWSTR v38; // [rsp+60h] [rbp+7h] BYREF
  LPCWSTR v39; // [rsp+68h] [rbp+Fh] BYREF
  LPCWSTR lpExistingFileName; // [rsp+70h] [rbp+17h] BYREF
  int v41; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  lpExistingFileName = a2;
  v38 = a3;
  v39 = a4;
  if ( String2 )
  {
    if ( !*String2 )
    {
      v6 = -2147024809;
      v41 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Specified identity is empty");
        *(_QWORD *)v32 = &v41;
        LOBYTE(v9) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v9,
          3,
          (unsigned int)": {}",
          (__int64)v32);
      }
      v8 = 2049;
      goto LABEL_5;
    }
    *(_QWORD *)v32 = 0;
    lpNewFileName = 0;
    v36 = 0;
    v35 = 0;
    if ( a2 )
    {
      v10 = -1;
      do
        ++v10;
      while ( String2[v10] );
      v11 = (const wchar_t *)FileFromPath(a2);
      if ( wcsncmp_0(v11, String2, v12) )
      {
        v13 = DirectoryFromPath(a2);
        v6 = v13;
        if ( v13 < 0 )
        {
          v14 = 2065;
LABEL_43:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v14,
            (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
            (const char *)(unsigned int)v13,
            v31);
          goto LABEL_53;
        }
        v15 = SczAllocFormatted(&lpNewFileName, L"%ws%ws.mum", *(_QWORD *)v32, String2);
        if ( v15 < 0 )
        {
          v16 = 2066;
LABEL_18:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
            (const char *)(unsigned int)v15,
            v31);
          v6 = v15;
LABEL_53:
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v35);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v36);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v32);
          return v6;
        }
        v17 = lpNewFileName;
        if ( MoveFileExW(lpExistingFileName, lpNewFileName, 1u) )
        {
          if ( !v38 )
            goto LABEL_50;
          v15 = SczAllocFormatted(&v36, L"%ws%ws.cat", *(_QWORD *)v32, String2);
          if ( v15 < 0 )
          {
            v16 = 2073;
            goto LABEL_18;
          }
          v23 = v36;
          if ( MoveFileExW(v38, v36, 1u) )
          {
LABEL_50:
            if ( v39 )
            {
              v13 = SczAllocFormatted(&v35, L"%ws%ws.ses", *(_QWORD *)v32, String2);
              v6 = v13;
              if ( v13 < 0 )
              {
                v14 = 2081;
                goto LABEL_43;
              }
              v26 = v35;
              if ( !MoveFileExW(v39, v35, 1u) )
              {
                LastError = GetLastError();
                if ( LogAdapter::g_Logger )
                {
                  *(_QWORD *)v34 = v26;
                  LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                    (_DWORD)LogAdapter::g_Logger,
                    0,
                    3,
                    (unsigned int)"Failed to move file from:{} to {}",
                    (__int64)&v39,
                    (__int64)v34);
                  if ( LastError > 0 )
                    v29 = (unsigned __int16)LastError | 0x80070000;
                  else
                    v29 = LastError;
                  v41 = v29;
                  LOBYTE(v28) = 1;
                  v33 = &v41;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v28,
                    3,
                    (unsigned int)": {0}",
                    (__int64)&v33);
                }
                if ( LastError )
                {
                  v22 = (unsigned int)LastError;
                  v21 = 2085;
                  goto LABEL_28;
                }
              }
            }
          }
          else
          {
            v18 = GetLastError();
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v34 = v23;
              LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to move file from:{} to {}",
                (__int64)&v38,
                (__int64)v34);
              if ( v18 > 0 )
                v25 = (unsigned __int16)v18 | 0x80070000;
              else
                v25 = v18;
              v41 = v25;
              LOBYTE(v24) = 1;
              v33 = &v41;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v24,
                3,
                (unsigned int)": {0}",
                (__int64)&v33);
            }
            if ( v18 )
            {
              v21 = 2076;
              goto LABEL_27;
            }
          }
        }
        else
        {
          v18 = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            v33 = (int *)v17;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to move file from:{} to {}",
              (__int64)&lpExistingFileName,
              (__int64)&v33);
            if ( v18 > 0 )
              v20 = (unsigned __int16)v18 | 0x80070000;
            else
              v20 = v18;
            v41 = v20;
            LOBYTE(v19) = 1;
            *(_QWORD *)v34 = &v41;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v19,
              3,
              (unsigned int)": {0}",
              (__int64)v34);
          }
          if ( v18 )
          {
            v21 = 2069;
LABEL_27:
            v22 = (unsigned int)v18;
LABEL_28:
            v6 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v21,
                   (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
                   (const char *)v22,
                   v31);
            goto LABEL_53;
          }
        }
      }
    }
    v6 = 0;
    goto LABEL_53;
  }
  v6 = -2147024809;
  v41 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No identity specified");
    *(_QWORD *)v32 = &v41;
    LOBYTE(v7) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v7,
      3,
      (unsigned int)": {}",
      (__int64)v32);
  }
  v8 = 2048;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
    (const char *)0x80070057LL,
    v31);
  return v6;
}

```

## disassembly

```asm
0x1800cb9b4  push    rbp
0x1800cb9b6  push    rbx
0x1800cb9b7  push    rsi
0x1800cb9b8  push    rdi
0x1800cb9b9  push    r14
0x1800cb9bb  lea     rbp, [rsp-37h]
0x1800cb9c0  sub     rsp, 90h
0x1800cb9c7  mov     rax, cs:__security_cookie
0x1800cb9ce  xor     rax, rsp
0x1800cb9d1  mov     [rbp+57h+var_30], rax
0x1800cb9d5  xor     r14d, r14d
0x1800cb9d8  mov     [rbp+57h+lpExistingFileName], rdx
0x1800cb9dc  mov     [rbp+57h+var_50], r8
0x1800cb9e0  mov     rbx, rdx
0x1800cb9e3  mov     [rbp+57h+var_48], r9
0x1800cb9e7  mov     rsi, rcx
0x1800cb9ea  test    rcx, rcx
0x1800cb9ed  jnz     short loc_1800CBA5D
0x1800cb9ef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cb9f6  mov     ebx, 80070057h
0x1800cb9fb  mov     [rbp+57h+var_38], ebx
0x1800cb9fe  test    rcx, rcx
0x1800cba01  jz      short loc_1800CBA40
0x1800cba03  lea     edi, [rsi+3]
0x1800cba06  xor     edx, edx
0x1800cba08  mov     r8d, edi
0x1800cba0b  lea     r9, aNoIdentitySpec; "No identity specified"
0x1800cba12  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cba17  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cba1e  lea     rax, [rbp+57h+var_38]
0x1800cba22  mov     qword ptr [rbp+57h+var_80], rax
0x1800cba26  lea     r9, asc_1802EE7AC; ": {}"
0x1800cba2d  lea     rax, [rbp+57h+var_80]
0x1800cba31  mov     r8d, edi
0x1800cba34  mov     dl, 1
0x1800cba36  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1800cba3b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cba40  mov     edx, 800h; void *
0x1800cba45  mov     rcx, [rbp+5Fh]; this
0x1800cba49  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800cba50  mov     r9d, ebx; char *
0x1800cba53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cba58  jmp     loc_1800CBE36
0x1800cba5d  cmp     [rcx], r14w
0x1800cba61  jnz     short loc_1800CBABD
0x1800cba63  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cba6a  mov     ebx, 80070057h
0x1800cba6f  mov     [rbp+57h+var_38], ebx
0x1800cba72  test    rcx, rcx
0x1800cba75  jz      short loc_1800CBAB6
0x1800cba77  mov     edi, 3
0x1800cba7c  lea     r9, aSpecifiedIdent; "Specified identity is empty"
0x1800cba83  mov     r8d, edi
0x1800cba86  xor     edx, edx
0x1800cba88  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cba8d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cba94  lea     rax, [rbp+57h+var_38]
0x1800cba98  mov     qword ptr [rbp+57h+var_80], rax
0x1800cba9c  lea     r9, asc_1802EE7AC; ": {}"
0x1800cbaa3  lea     rax, [rbp+57h+var_80]
0x1800cbaa7  mov     r8d, edi
0x1800cbaaa  mov     dl, 1
0x1800cbaac  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800cbab1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cbab6  mov     edx, 801h
0x1800cbabb  jmp     short loc_1800CBA45
0x1800cbabd  mov     qword ptr [rbp+57h+var_80], r14
0x1800cbac1  mov     [rbp+57h+lpNewFileName], r14
0x1800cbac5  mov     [rbp+57h+var_60], r14
0x1800cbac9  mov     [rbp+57h+var_68], r14
0x1800cbacd  test    rbx, rbx
0x1800cbad0  jz      loc_1800CBE0F
0x1800cbad6  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800cbada  inc     r9
0x1800cbadd  cmp     [rcx+r9*2], r14w
0x1800cbae2  jnz     short loc_1800CBADA
0x1800cbae4  mov     rcx, rbx
0x1800cbae7  call    FileFromPath
0x1800cbaec  mov     rcx, rax; String1
0x1800cbaef  mov     r8d, r9d; MaxCount
0x1800cbaf2  mov     rdx, rsi; String2
0x1800cbaf5  call    wcsncmp_0
0x1800cbafa  test    eax, eax
0x1800cbafc  jz      loc_1800CBE0F
0x1800cbb02  lea     rdx, [rbp+57h+var_80]
0x1800cbb06  mov     rcx, rbx; wchar_t *
0x1800cbb09  call    DirectoryFromPath
0x1800cbb0e  mov     ebx, eax
0x1800cbb10  test    eax, eax
0x1800cbb12  jns     short loc_1800CBB1E
0x1800cbb14  mov     edx, 811h
0x1800cbb19  jmp     loc_1800CBD3F
0x1800cbb1e  mov     rbx, qword ptr [rbp+57h+var_80]
0x1800cbb22  lea     rdx, aWsWsMum; "%ws%ws.mum"
0x1800cbb29  mov     r8, rbx
0x1800cbb2c  lea     rcx, [rbp+57h+lpNewFileName]
0x1800cbb30  mov     r9, rsi
0x1800cbb33  call    SczAllocFormatted
0x1800cbb38  mov     edi, eax
0x1800cbb3a  test    eax, eax
0x1800cbb3c  jns     short loc_1800CBB5D
0x1800cbb3e  mov     edx, 812h; void *
0x1800cbb43  mov     rcx, [rbp+5Fh]; this
0x1800cbb47  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800cbb4e  mov     r9d, edi; char *
0x1800cbb51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cbb56  mov     ebx, edi
0x1800cbb58  jmp     loc_1800CBE12
0x1800cbb5d  mov     rdi, [rbp+57h+lpNewFileName]
0x1800cbb61  mov     r8d, 1; dwFlags
0x1800cbb67  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x1800cbb6b  mov     rdx, rdi; lpNewFileName
0x1800cbb6e  call    cs:__imp_MoveFileExW
0x1800cbb75  nop     dword ptr [rax+rax+00h]
0x1800cbb7a  test    eax, eax
0x1800cbb7c  jnz     loc_1800CBC2B
0x1800cbb82  call    cs:__imp_GetLastError
0x1800cbb89  nop     dword ptr [rax+rax+00h]
0x1800cbb8e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cbb95  mov     ebx, eax
0x1800cbb97  test    rcx, rcx
0x1800cbb9a  jz      short loc_1800CBC04
0x1800cbb9c  lea     rax, [rbp+57h+var_78]
0x1800cbba0  mov     [rbp+57h+var_78], rdi
0x1800cbba4  mov     [rsp+0B0h+var_88], rax
0x1800cbba9  lea     r9, aFailedToMoveFi_0; "Failed to move file from:{} to {}"
0x1800cbbb0  lea     rax, [rbp+57h+lpExistingFileName]
0x1800cbbb4  mov     edi, 3
0x1800cbbb9  mov     r8d, edi
0x1800cbbbc  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800cbbc1  xor     edx, edx
0x1800cbbc3  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800cbbc8  test    ebx, ebx
0x1800cbbca  jg      short loc_1800CBBD0
0x1800cbbcc  mov     eax, ebx
0x1800cbbce  jmp     short loc_1800CBBD8
0x1800cbbd0  movzx   eax, bx
0x1800cbbd3  or      eax, 80070000h
0x1800cbbd8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cbbdf  lea     r9, a0; ": {0}"
0x1800cbbe6  mov     [rbp+57h+var_38], eax
0x1800cbbe9  mov     r8d, edi
0x1800cbbec  lea     rax, [rbp+57h+var_38]
0x1800cbbf0  mov     dl, 1
0x1800cbbf2  mov     qword ptr [rbp+57h+var_70], rax
0x1800cbbf6  lea     rax, [rbp+57h+var_70]
0x1800cbbfa  mov     qword ptr [rsp+0B0h+var_90], rax; unsigned int
0x1800cbbff  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cbc04  test    ebx, ebx
0x1800cbc06  jz      loc_1800CBE0F
0x1800cbc0c  mov     edx, 815h; void *
0x1800cbc11  mov     r9d, ebx; char *
0x1800cbc14  mov     rcx, [rbp+5Fh]; this
0x1800cbc18  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800cbc1f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cbc24  mov     ebx, eax
0x1800cbc26  jmp     loc_1800CBE12
0x1800cbc2b  cmp     [rbp+57h+var_50], r14
0x1800cbc2f  jz      loc_1800CBD14
0x1800cbc35  mov     r9, rsi
0x1800cbc38  lea     rdx, aWsWsCat; "%ws%ws.cat"
0x1800cbc3f  mov     r8, rbx
0x1800cbc42  lea     rcx, [rbp+57h+var_60]
0x1800cbc46  call    SczAllocFormatted
0x1800cbc4b  mov     edi, eax
0x1800cbc4d  test    eax, eax
0x1800cbc4f  jns     short loc_1800CBC5B
0x1800cbc51  mov     edx, 819h
0x1800cbc56  jmp     loc_1800CBB43
0x1800cbc5b  mov     rdi, [rbp+57h+var_60]
0x1800cbc5f  mov     r8d, 1; dwFlags
0x1800cbc65  mov     rcx, [rbp+57h+var_50]; lpExistingFileName
0x1800cbc69  mov     rdx, rdi; lpNewFileName
0x1800cbc6c  call    cs:__imp_MoveFileExW
0x1800cbc73  nop     dword ptr [rax+rax+00h]
0x1800cbc78  test    eax, eax
0x1800cbc7a  jnz     loc_1800CBD14
0x1800cbc80  call    cs:__imp_GetLastError
0x1800cbc87  nop     dword ptr [rax+rax+00h]
0x1800cbc8c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cbc93  mov     ebx, eax
0x1800cbc95  test    rcx, rcx
0x1800cbc98  jz      short loc_1800CBD02
0x1800cbc9a  lea     rax, [rbp+57h+var_70]
0x1800cbc9e  mov     qword ptr [rbp+57h+var_70], rdi
0x1800cbca2  mov     [rsp+0B0h+var_88], rax
0x1800cbca7  lea     r9, aFailedToMoveFi_0; "Failed to move file from:{} to {}"
0x1800cbcae  lea     rax, [rbp+57h+var_50]
0x1800cbcb2  mov     edi, 3
0x1800cbcb7  mov     r8d, edi
0x1800cbcba  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800cbcbf  xor     edx, edx
0x1800cbcc1  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800cbcc6  test    ebx, ebx
0x1800cbcc8  jg      short loc_1800CBCCE
0x1800cbcca  mov     eax, ebx
0x1800cbccc  jmp     short loc_1800CBCD6
0x1800cbcce  movzx   eax, bx
0x1800cbcd1  or      eax, 80070000h
0x1800cbcd6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cbcdd  lea     r9, a0; ": {0}"
0x1800cbce4  mov     [rbp+57h+var_38], eax
0x1800cbce7  mov     r8d, edi
0x1800cbcea  lea     rax, [rbp+57h+var_38]
0x1800cbcee  mov     dl, 1
0x1800cbcf0  mov     [rbp+57h+var_78], rax
0x1800cbcf4  lea     rax, [rbp+57h+var_78]
0x1800cbcf8  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800cbcfd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cbd02  test    ebx, ebx
0x1800cbd04  jz      loc_1800CBE0F
0x1800cbd0a  mov     edx, 81Ch
0x1800cbd0f  jmp     loc_1800CBC11
0x1800cbd14  cmp     [rbp+57h+var_48], r14
0x1800cbd18  jz      loc_1800CBE0F
0x1800cbd1e  mov     r9, rsi
0x1800cbd21  lea     rdx, aWsWsSes; "%ws%ws.ses"
0x1800cbd28  mov     r8, rbx
0x1800cbd2b  lea     rcx, [rbp+57h+var_68]
0x1800cbd2f  call    SczAllocFormatted
0x1800cbd34  mov     ebx, eax
0x1800cbd36  test    eax, eax
0x1800cbd38  jns     short loc_1800CBD57
0x1800cbd3a  mov     edx, 821h; void *
0x1800cbd3f  mov     rcx, [rbp+5Fh]; this
0x1800cbd43  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800cbd4a  mov     r9d, eax; char *
0x1800cbd4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cbd52  jmp     loc_1800CBE12
0x1800cbd57  mov     rbx, [rbp+57h+var_68]
0x1800cbd5b  mov     r8d, 1; dwFlags
0x1800cbd61  mov     rcx, [rbp+57h+var_48]; lpExistingFileName
0x1800cbd65  mov     rdx, rbx; lpNewFileName
0x1800cbd68  call    cs:__imp_MoveFileExW
0x1800cbd6f  nop     dword ptr [rax+rax+00h]
0x1800cbd74  test    eax, eax
0x1800cbd76  jnz     loc_1800CBE0F
0x1800cbd7c  call    cs:__imp_GetLastError
0x1800cbd83  nop     dword ptr [rax+rax+00h]
0x1800cbd88  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cbd8f  mov     esi, eax
0x1800cbd91  test    rcx, rcx
0x1800cbd94  jz      short loc_1800CBDFE
0x1800cbd96  lea     rax, [rbp+57h+var_70]
0x1800cbd9a  mov     qword ptr [rbp+57h+var_70], rbx
0x1800cbd9e  mov     [rsp+0B0h+var_88], rax
0x1800cbda3  lea     r9, aFailedToMoveFi_0; "Failed to move file from:{} to {}"
0x1800cbdaa  lea     rax, [rbp+57h+var_48]
0x1800cbdae  mov     edi, 3
0x1800cbdb3  mov     r8d, edi
0x1800cbdb6  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800cbdbb  xor     edx, edx
0x1800cbdbd  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800cbdc2  test    esi, esi
0x1800cbdc4  jg      short loc_1800CBDCA
0x1800cbdc6  mov     eax, esi
0x1800cbdc8  jmp     short loc_1800CBDD2
0x1800cbdca  movzx   eax, si
0x1800cbdcd  or      eax, 80070000h
0x1800cbdd2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cbdd9  lea     r9, a0; ": {0}"
0x1800cbde0  mov     [rbp+57h+var_38], eax
0x1800cbde3  mov     r8d, edi
0x1800cbde6  lea     rax, [rbp+57h+var_38]
0x1800cbdea  mov     dl, 1
0x1800cbdec  mov     [rbp+57h+var_78], rax
0x1800cbdf0  lea     rax, [rbp+57h+var_78]
0x1800cbdf4  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800cbdf9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cbdfe  test    esi, esi
0x1800cbe00  jz      short loc_1800CBE0F
0x1800cbe02  mov     r9d, esi
0x1800cbe05  mov     edx, 825h
0x1800cbe0a  jmp     loc_1800CBC14
0x1800cbe0f  mov     ebx, r14d
0x1800cbe12  lea     rcx, [rbp+57h+var_68]
0x1800cbe16  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800cbe1b  lea     rcx, [rbp+57h+var_60]
0x1800cbe1f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800cbe24  lea     rcx, [rbp+57h+lpNewFileName]
0x1800cbe28  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800cbe2d  lea     rcx, [rbp+57h+var_80]
0x1800cbe31  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800cbe36  mov     eax, ebx
0x1800cbe38  mov     rcx, [rbp+57h+var_30]
0x1800cbe3c  xor     rcx, rsp; StackCookie
0x1800cbe3f  call    __security_check_cookie
0x1800cbe44  add     rsp, 90h
0x1800cbe4b  pop     r14
0x1800cbe4d  pop     rdi
0x1800cbe4e  pop     rsi
0x1800cbe4f  pop     rbx
0x1800cbe50  pop     rbp
0x1800cbe51  retn
```
