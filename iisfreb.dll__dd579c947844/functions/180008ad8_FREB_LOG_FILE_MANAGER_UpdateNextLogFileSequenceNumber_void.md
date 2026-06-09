# FREB_LOG_FILE_MANAGER::UpdateNextLogFileSequenceNumber(void)

- ea: `0x180008ad8`
- end: `0x180008d8f`
- name: `?UpdateNextLogFileSequenceNumber@FREB_LOG_FILE_MANAGER@@AEAAJXZ`
- size: `695`
- prototype: `__int64 __fastcall(FREB_LOG_FILE_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180008178`

## callees

- `0x180008ad8`
- `0x18000ac52`
- `0x18000ac90`

## import_xrefs

- `msvcrt!wcstoul` at `0x180008cdf`
- `msvcrt!wcstoul` at `0x180008cdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cb6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180008c0d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180008c0d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180008cac`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180008cac`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180008d52`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180008d52`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008d5d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008d68`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008d5d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008d68`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008b4c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008b76`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008b4c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008b76`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008b88`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008b88`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180008be3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180008be3`
- `iisutil!PuDbgPrintError` at `0x180008bcc`
- `iisutil!PuDbgPrintError` at `0x180008d49`
- `iisutil!PuDbgPrintError` at `0x180008bcc`
- `iisutil!PuDbgPrintError` at `0x180008d49`

## string_xrefs

- `0x180008bd7`: `fr*.xml`
- `0x180008bb5`: `FREB_LOG_FILE_MANAGER::UpdateNextLogFileSequenceNumber`
- `0x180008d3b`: `FREB_LOG_FILE_MANAGER::UpdateNextLogFileSequenceNumber`
- `0x180008bc1`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_log_file_manager.cxx`
- `0x180008d42`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_log_file_manager.cxx`
- `0x180008cf9`: `Last write time is not available. File system may not support that\n`

## pseudocode

```c
__int64 __fastcall FREB_LOG_FILE_MANAGER::UpdateNextLogFileSequenceNumber(FREB_LOG_FILE_MANAGER *this)
{
  signed int LastError; // ebx
  __int64 v3; // r8
  HANDLE FirstFileW; // rsi
  FILETIME ftLastWriteTime; // rbx
  struct _WIN32_FIND_DATAW *p_FindFileData; // r14
  struct _WIN32_FIND_DATAW *v7; // rdi
  struct _WIN32_FIND_DATAW *i; // rdx
  FILETIME v9; // rax
  bool v10; // zf
  signed int v11; // eax
  _BYTE v13[32]; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B0h]
  _BYTE v15[56]; // [rsp+68h] [rbp-98h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF
  struct _WIN32_FIND_DATAW v17; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v18[32]; // [rsp+540h] [rbp+440h] BYREF
  unsigned __int16 v19[264]; // [rsp+580h] [rbp+480h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(&v17, 0, sizeof(v17));
  memset_0(v19, 0, 0x208u);
  STRU::STRU((STRU *)v13, v19, 0x104u);
  memset_0(v18, 0, sizeof(v18));
  STRU::STRU((STRU *)v15, v18, 0x20u);
  LastError = STRU::Copy((STRU *)v13, *(const unsigned __int16 **)(*(_QWORD *)this + 48LL));
  if ( LastError >= 0 )
  {
    LastError = STRU::Append((STRU *)v13, L"fr*.xml");
    if ( LastError >= 0 )
    {
      FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        if ( ((LastError - 2) & 0xFFFFFFEE) != 0 || LastError == 19 )
        {
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_log_file_manager.cxx",
              123,
              "FREB_LOG_FILE_MANAGER::UpdateNextLogFileSequenceNumber",
              LastError,
              "FindFirstFileW() failed\n");
        }
        else
        {
          LastError = 0;
        }
      }
      else
      {
        ftLastWriteTime = FindFileData.ftLastWriteTime;
        p_FindFileData = &FindFileData;
        v7 = &v17;
        for ( i = &v17; ; i = v7 )
        {
          if ( !FindNextFileW(FirstFileW, i) )
          {
            v11 = GetLastError();
            LastError = v11;
            if ( v11 > 0 )
              LastError = (unsigned __int16)v11 | 0x80070000;
            if ( LastError == -2147024878 )
            {
              LastError = 0;
              *((_DWORD *)this + 4) = wcstoul(&p_FindFileData->cFileName[2], 0, 10);
            }
            else if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_log_file_manager.cxx",
                166,
                "FREB_LOG_FILE_MANAGER::UpdateNextLogFileSequenceNumber",
                LastError,
                "FindNextFileW() failed\n");
            }
            goto LABEL_32;
          }
          v9 = v7->ftLastWriteTime;
          if ( !*(_QWORD *)&v9 )
            break;
          if ( *(_QWORD *)&ftLastWriteTime <= *(unsigned __int64 *)&v9 )
          {
            ftLastWriteTime = v7->ftLastWriteTime;
            p_FindFileData = v7;
            v10 = v7 == &FindFileData;
            v7 = &v17;
            if ( !v10 )
              v7 = &FindFileData;
          }
        }
        LastError = -2147024846;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_log_file_manager.cxx",
            191,
            "FREB_LOG_FILE_MANAGER::UpdateNextLogFileSequenceNumber",
            -2147024846,
            "Last write time is not available. File system may not support that\n");
LABEL_32:
        FindClose(FirstFileW);
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v3 = 93;
      goto LABEL_4;
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v3 = 81;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_log_file_manager.cxx",
      v3,
      "FREB_LOG_FILE_MANAGER::UpdateNextLogFileSequenceNumber",
      LastError,
      "Failed to build the pattern string for the FindFirstFileW()\n");
  }
  STRU::~STRU((STRU *)v15);
  STRU::~STRU((STRU *)v13);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180008ad8  push    rbp
0x180008ada  push    rbx
0x180008adb  push    rsi
0x180008adc  push    rdi
0x180008add  push    r14
0x180008adf  push    r15
0x180008ae1  lea     rbp, [rsp-6A8h]
0x180008ae9  sub     rsp, 7A8h
0x180008af0  mov     rax, cs:__security_cookie
0x180008af7  xor     rax, rsp
0x180008afa  mov     [rbp+6D0h+var_40], rax
0x180008b01  mov     r15, rcx
0x180008b04  mov     ebx, 250h
0x180008b09  mov     r8d, ebx; Size
0x180008b0c  lea     rcx, [rbp+6D0h+FindFileData]; void *
0x180008b10  xor     edx, edx; Val
0x180008b12  call    memset_0
0x180008b17  mov     r8d, ebx; Size
0x180008b1a  lea     rcx, [rbp+6D0h+var_4E0]; void *
0x180008b21  xor     edx, edx; Val
0x180008b23  call    memset_0
0x180008b28  xor     edx, edx; Val
0x180008b2a  lea     r8d, [rbx-48h]; Size
0x180008b2e  lea     rcx, [rbp+6D0h+var_250]; void *
0x180008b35  call    memset_0
0x180008b3a  mov     r8d, 104h
0x180008b40  lea     rdx, [rbp+6D0h+var_250]
0x180008b47  lea     rcx, [rsp+7D0h+var_7A0]
0x180008b4c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180008b52  xor     edx, edx; Val
0x180008b54  lea     rcx, [rbp+6D0h+var_290]; void *
0x180008b5b  lea     r8d, [rdx+40h]; Size
0x180008b5f  call    memset_0
0x180008b64  mov     r8d, 20h ; ' '
0x180008b6a  lea     rdx, [rbp+6D0h+var_290]
0x180008b71  lea     rcx, [rsp+7D0h+var_768]
0x180008b76  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180008b7c  mov     rdx, [r15]
0x180008b7f  lea     rcx, [rsp+7D0h+var_7A0]
0x180008b84  mov     rdx, [rdx+30h]
0x180008b88  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180008b8e  mov     ebx, eax
0x180008b90  test    eax, eax
0x180008b92  jns     short loc_180008BD7
0x180008b94  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008b9b  jz      loc_180008D58
0x180008ba1  mov     r8d, 51h ; 'Q'
0x180008ba7  lea     rax, aFailedToBuildT_1; "Failed to build the pattern string for "...
0x180008bae  mov     rcx, cs:g_pDebug
0x180008bb5  lea     r9, aFrebLogFileMan; "FREB_LOG_FILE_MANAGER::UpdateNextLogFil"...
0x180008bbc  mov     [rsp+7D0h+var_7A8], rax
0x180008bc1  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008bc8  mov     [rsp+7D0h+var_7B0], ebx
0x180008bcc  call    cs:__imp_PuDbgPrintError
0x180008bd2  jmp     loc_180008D58
0x180008bd7  lea     rdx, aFrXml; "fr*.xml"
0x180008bde  lea     rcx, [rsp+7D0h+var_7A0]
0x180008be3  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180008be9  mov     ebx, eax
0x180008beb  test    eax, eax
0x180008bed  jns     short loc_180008C04
0x180008bef  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008bf6  jz      loc_180008D58
0x180008bfc  mov     r8d, 5Dh ; ']'
0x180008c02  jmp     short loc_180008BA7
0x180008c04  mov     rcx, [rsp+7D0h+lpFileName]; lpFileName
0x180008c09  lea     rdx, [rbp+6D0h+FindFileData]; lpFindFileData
0x180008c0d  call    cs:__imp_FindFirstFileW
0x180008c13  mov     rsi, rax
0x180008c16  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008c1a  jnz     short loc_180008C66
0x180008c1c  call    cs:__imp_GetLastError
0x180008c22  mov     ebx, eax
0x180008c24  add     eax, 0FFFFFFFEh
0x180008c27  test    eax, 0FFFFFFEEh
0x180008c2c  jnz     short loc_180008C3A
0x180008c2e  cmp     ebx, 13h
0x180008c31  jz      short loc_180008C3A
0x180008c33  xor     ebx, ebx
0x180008c35  jmp     loc_180008D58
0x180008c3a  test    ebx, ebx
0x180008c3c  jle     short loc_180008C47
0x180008c3e  movzx   ebx, bx
0x180008c41  or      ebx, 80070000h
0x180008c47  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008c4e  jz      loc_180008D58
0x180008c54  lea     rax, aFindfirstfilew; "FindFirstFileW() failed\n"
0x180008c5b  mov     r8d, 7Bh ; '{'
0x180008c61  jmp     loc_180008BAE
0x180008c66  mov     rbx, qword ptr [rbp+6D0h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x180008c6a  lea     r14, [rbp+6D0h+FindFileData]
0x180008c6e  lea     rdi, [rbp+6D0h+var_4E0]
0x180008c75  lea     rdx, [rbp+6D0h+var_4E0]
0x180008c7c  jmp     short loc_180008CA9
0x180008c7e  mov     rax, [rdi+14h]
0x180008c82  test    rax, rax
0x180008c85  jz      short loc_180008CEB
0x180008c87  cmp     rbx, rax
0x180008c8a  ja      short loc_180008CA6
0x180008c8c  mov     rbx, rax
0x180008c8f  mov     r14, rdi
0x180008c92  lea     rax, [rbp+6D0h+FindFileData]
0x180008c96  cmp     rdi, rax
0x180008c99  lea     rdi, [rbp+6D0h+var_4E0]
0x180008ca0  jz      short loc_180008CA6
0x180008ca2  lea     rdi, [rbp+6D0h+FindFileData]
0x180008ca6  mov     rdx, rdi; lpFindFileData
0x180008ca9  mov     rcx, rsi; hFindFile
0x180008cac  call    cs:__imp_FindNextFileW
0x180008cb2  test    eax, eax
0x180008cb4  jnz     short loc_180008C7E
0x180008cb6  call    cs:__imp_GetLastError
0x180008cbc  mov     ebx, eax
0x180008cbe  test    eax, eax
0x180008cc0  jle     short loc_180008CCB
0x180008cc2  movzx   ebx, ax
0x180008cc5  or      ebx, 80070000h
0x180008ccb  cmp     ebx, 80070012h
0x180008cd1  jnz     short loc_180008D15
0x180008cd3  xor     ebx, ebx
0x180008cd5  lea     rcx, [r14+30h]; String
0x180008cd9  xor     edx, edx; EndPtr
0x180008cdb  lea     r8d, [rbx+0Ah]; Radix
0x180008cdf  call    cs:__imp_wcstoul
0x180008ce5  mov     [r15+10h], eax
0x180008ce9  jmp     short loc_180008D4F
0x180008ceb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008cf2  mov     ebx, 80070032h
0x180008cf7  jz      short loc_180008D4F
0x180008cf9  lea     rax, aLastWriteTimeI; "Last write time is not available. File "...
0x180008d00  mov     r8d, 0BFh
0x180008d06  mov     [rsp+7D0h+var_7A8], rax
0x180008d0b  mov     [rsp+7D0h+var_7B0], 80070032h
0x180008d13  jmp     short loc_180008D34
0x180008d15  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008d1c  jz      short loc_180008D4F
0x180008d1e  lea     rax, aFindnextfilewF; "FindNextFileW() failed\n"
0x180008d25  mov     r8d, 0A6h
0x180008d2b  mov     [rsp+7D0h+var_7A8], rax
0x180008d30  mov     [rsp+7D0h+var_7B0], ebx
0x180008d34  mov     rcx, cs:g_pDebug
0x180008d3b  lea     r9, aFrebLogFileMan; "FREB_LOG_FILE_MANAGER::UpdateNextLogFil"...
0x180008d42  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008d49  call    cs:__imp_PuDbgPrintError
0x180008d4f  mov     rcx, rsi; hFindFile
0x180008d52  call    cs:__imp_FindClose
0x180008d58  lea     rcx, [rsp+7D0h+var_768]
0x180008d5d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008d63  lea     rcx, [rsp+7D0h+var_7A0]
0x180008d68  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008d6e  mov     eax, ebx
0x180008d70  mov     rcx, [rbp+6D0h+var_40]
0x180008d77  xor     rcx, rsp; StackCookie
0x180008d7a  call    __security_check_cookie
0x180008d7f  add     rsp, 7A8h
0x180008d86  pop     r15
0x180008d88  pop     r14
0x180008d8a  pop     rdi
0x180008d8b  pop     rsi
0x180008d8c  pop     rbx
0x180008d8d  pop     rbp
0x180008d8e  retn
```
