# TextFileLogger::DetermineFile(void)

- ea: `0x180012b68`
- end: `0x180012fb6`
- name: `?DetermineFile@TextFileLogger@@AEAAJXZ`
- size: `1102`
- prototype: `__int64 __fastcall(TextFileLogger *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180013140`

## callees

- `0x180012a34`
- `0x180012b68`
- `0x180012fbc`
- `0x180013bb0`
- `0x180013c30`
- `0x180013cd8`
- `0x18002e0ca`
- `0x18002e110`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180012e8a`
- `msvcrt!_snwprintf_s` at `0x180012eba`
- `msvcrt!_snwprintf_s` at `0x180012e8a`
- `msvcrt!_snwprintf_s` at `0x180012eba`
- `KERNEL32!FindClose` at `0x180012d2e`
- `KERNEL32!FindClose` at `0x180012f44`
- `KERNEL32!FindClose` at `0x180012d2e`
- `KERNEL32!FindClose` at `0x180012f44`
- `KERNEL32!FindNextFileW` at `0x180012d10`
- `KERNEL32!FindNextFileW` at `0x180012d10`
- `KERNEL32!FindFirstFileW` at `0x180012c8d`
- `KERNEL32!FindFirstFileW` at `0x180012c8d`
- `KERNEL32!DeleteFileW` at `0x180012e9b`
- `KERNEL32!DeleteFileW` at `0x180012ecb`
- `KERNEL32!DeleteFileW` at `0x180012e9b`
- `KERNEL32!DeleteFileW` at `0x180012ecb`
- `KERNEL32!CreateFileW` at `0x180012d9b`
- `KERNEL32!CreateFileW` at `0x180012d9b`
- `KERNEL32!GetLastError` at `0x180012d1a`
- `KERNEL32!GetLastError` at `0x180012dab`
- `KERNEL32!GetLastError` at `0x180012ed5`
- `KERNEL32!GetLastError` at `0x180012d1a`
- `KERNEL32!GetLastError` at `0x180012dab`
- `KERNEL32!GetLastError` at `0x180012ed5`
- `IisRTL!PuDbgPrint` at `0x180012bef`
- `IisRTL!PuDbgPrint` at `0x180012e3a`
- `IisRTL!PuDbgPrint` at `0x180012f37`
- `IisRTL!PuDbgPrint` at `0x180012f7e`
- `IisRTL!PuDbgPrint` at `0x180012bef`
- `IisRTL!PuDbgPrint` at `0x180012e3a`
- `IisRTL!PuDbgPrint` at `0x180012f37`
- `IisRTL!PuDbgPrint` at `0x180012f7e`

## string_xrefs

- `0x180012be8`: `inetsrv\iis\mb\config\src\shared\util\textfilelogger.cpp`
- `0x180012e21`: `inetsrv\iis\mb\config\src\shared\util\textfilelogger.cpp`
- `0x180012f30`: `inetsrv\iis\mb\config\src\shared\util\textfilelogger.cpp`
- `0x180012f77`: `inetsrv\iis\mb\config\src\shared\util\textfilelogger.cpp`

## pseudocode

```c
__int64 __fastcall TextFileLogger::DetermineFile(TextFileLogger *this)
{
  wchar_t *v3; // rsi
  int v4; // eax
  signed __int64 v5; // rbx
  int v6; // edi
  TLogData *v7; // rcx
  unsigned __int16 v8; // r8
  HANDLE FirstFileW; // r14
  __int64 v10; // rsi
  unsigned int v11; // r9d
  _WIN32_FIND_DATAW *p_FindFileData; // rbx
  _WIN32_FIND_DATAW *v13; // rdi
  _WIN32_FIND_DATAW *v14; // rax
  signed int LastError; // ebx
  unsigned __int64 v16; // r8
  unsigned int *p_ftCreationTime; // rbx
  bool v18; // r14
  HANDLE FileW; // rax
  int i; // r15d
  int FirstAvailableFile; // eax
  unsigned int v22; // r14d
  unsigned int v23; // edx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v26; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *Buffer; // [rsp+48h] [rbp-B8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+2A0h] [rbp+1A0h]
  int v30; // [rsp+2A4h] [rbp+1A4h]
  int v31; // [rsp+2A8h] [rbp+1A8h]
  _BYTE v32[32]; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v33; // [rsp+2D0h] [rbp+1D0h]
  __int16 v34; // [rsp+2DCh] [rbp+1DCh]
  int v35; // [rsp+500h] [rbp+400h]
  int v36; // [rsp+504h] [rbp+404h]
  int v37; // [rsp+508h] [rbp+408h]
  WCHAR FileName[264]; // [rsp+510h] [rbp+410h] BYREF

  Buffer = 0;
  v26 = 0;
  if ( !TextFileLogger::ConstructSearchString(this, FileName, &v26, &Buffer) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\config\\src\\shared\\util\\textfilelogger.cpp",
        562,
        "TextFileLogger::DetermineFile",
        "ConstructSearchString failed\n");
    return 2147500037LL;
  }
  memset_0(v32, 0, 0x250u);
  v3 = Buffer;
  v4 = *((_DWORD *)this + 2) / *((_DWORD *)this + 3);
  v36 = 0;
  v5 = Buffer - v26;
  v6 = v4;
  v37 = v4;
  v33 = 0;
  v34 = 0;
  v35 = v5;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v30 = 0;
  v31 = v6;
  FindFileData.nFileSizeLow = 0;
  FindFileData.cFileName[0] = 0;
  v29 = v5;
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    goto LABEL_6;
  p_FindFileData = &FindFileData;
  v13 = (_WIN32_FIND_DATAW *)v32;
  do
  {
    if ( TLogData::WstrToUl(
           v7,
           &p_FindFileData->cFileName[p_FindFileData[1].dwFileAttributes],
           v8,
           (unsigned int *)&p_FindFileData[1].ftCreationTime)
      && (!v13->cFileName[0] || p_FindFileData[1].ftCreationTime.dwLowDateTime > v13[1].ftCreationTime.dwLowDateTime) )
    {
      v14 = v13;
      v13 = p_FindFileData;
      p_FindFileData = v14;
    }
  }
  while ( FindNextFileW(FirstFileW, p_FindFileData) );
  LastError = GetLastError();
  if ( LastError == 18 )
  {
    FindClose(FirstFileW);
    if ( !v13->cFileName[0] )
    {
LABEL_6:
      v10 = v3 - FileName;
      v11 = 0;
LABEL_7:
      TextFileLogger::SetGlobalFile(v7, FileName, v10, v11);
      return 0;
    }
    p_ftCreationTime = (unsigned int *)&v13[1].ftCreationTime;
    v18 = 0;
    if ( v13->nFileSizeLow < v13[1].ftCreationTime.dwHighDateTime )
    {
      TextFileLogger::SetGlobalFile(v7, FileName, v3 - FileName, *p_ftCreationTime);
      FileW = CreateFileW(&g_wszFileCur, 0x40000000u, 3u, 0, 4u, 0x80000080, 0);
      *((_QWORD *)this + 3) = FileW;
      if ( FileW == (HANDLE)-1LL )
        v18 = GetLastError() == 5;
    }
    if ( v13->nFileSizeLow < v13[1].ftCreationTime.dwHighDateTime && !v18 )
      return 0;
    for ( i = 0; i != -1; ++i )
    {
      if ( *p_ftCreationTime != -1 || i )
      {
        v23 = *p_ftCreationTime + 1;
        *p_ftCreationTime = v23;
        TLogData::SetVersion((TLogData *)v13, v23);
      }
      else
      {
        FirstAvailableFile = TextFileLogger::GetFirstAvailableFile(this, FileName, v16, v26, (struct TLogData *)v13);
        v22 = FirstAvailableFile;
        if ( FirstAvailableFile < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\mb\\config\\src\\shared\\util\\textfilelogger.cpp",
              656,
              "TextFileLogger::DetermineFile",
              "GetFirstAvailableFile returned hr=0x%x\n",
              FirstAvailableFile);
          return v22;
        }
      }
      dwCreationDisposition[0] = *p_ftCreationTime - *((_DWORD *)this + 3);
      if ( _snwprintf_s(v3, 260 - (v3 - FileName), 0xAu, L"%010lu", *(_QWORD *)dwCreationDisposition) < 0 )
        return 2147942413LL;
      DeleteFileW(FileName);
      dwCreationDispositiona[0] = *p_ftCreationTime;
      if ( _snwprintf_s(v3, 260 - (v3 - FileName), 0xAu, L"%010lu", *(_QWORD *)dwCreationDispositiona) < 0 )
        return 2147942413LL;
      if ( DeleteFileW(FileName) || GetLastError() == 2 )
      {
        v11 = *p_ftCreationTime;
        v10 = v3 - FileName;
        goto LABEL_7;
      }
    }
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\config\\src\\shared\\util\\textfilelogger.cpp",
        704,
        "TextFileLogger::DetermineFile",
        "Cannot log.  There are 0xFFFFFFFF undeletable log files.\n");
    return 2147942418LL;
  }
  else
  {
    FindClose(FirstFileW);
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\config\\src\\shared\\util\\textfilelogger.cpp",
        612,
        "TextFileLogger::DetermineFile",
        "FindNextFile returned err=%u\n",
        LastError);
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)LastError;
  }
}

```

## disassembly

```asm
0x180012b68  push    rbp
0x180012b6a  push    rbx
0x180012b6b  push    rsi
0x180012b6c  push    rdi
0x180012b6d  push    r12
0x180012b6f  push    r13
0x180012b71  push    r14
0x180012b73  push    r15
0x180012b75  lea     rbp, [rsp-638h]
0x180012b7d  sub     rsp, 738h
0x180012b84  mov     rax, cs:__security_cookie
0x180012b8b  xor     rax, rsp
0x180012b8e  mov     [rbp+670h+var_50], rax
0x180012b95  xor     r12d, r12d
0x180012b98  lea     r9, [rsp+770h+Buffer]; unsigned __int16 **
0x180012b9d  lea     r8, [rsp+770h+var_730]; unsigned __int16 **
0x180012ba2  mov     [rsp+770h+Buffer], r12
0x180012ba7  lea     rdx, [rbp+670h+FileName]; unsigned __int16 *
0x180012bae  mov     [rsp+770h+var_730], r12
0x180012bb3  mov     r13, rcx
0x180012bb6  call    ?ConstructSearchString@TextFileLogger@@AEAA_NPEAGPEAPEAG1@Z; TextFileLogger::ConstructSearchString(ushort *,ushort * *,ushort * *)
0x180012bbb  test    al, al
0x180012bbd  jnz     short loc_180012BFF
0x180012bbf  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180012bc6  jz      short loc_180012BF5
0x180012bc8  mov     rcx, cs:g_pDebug
0x180012bcf  lea     rax, aConstructsearc; "ConstructSearchString failed\n"
0x180012bd6  lea     r9, aTextfilelogger; "TextFileLogger::DetermineFile"
0x180012bdd  mov     qword ptr [rsp+770h+dwCreationDisposition], rax
0x180012be2  mov     r8d, 232h
0x180012be8  lea     rdx, aInetsrvIisMbCo_2; "inetsrv\\iis\\mb\\config\\src\\shared\\"...
0x180012bef  call    cs:__imp_PuDbgPrint
0x180012bf5  mov     eax, 80004005h
0x180012bfa  jmp     loc_180012F93
0x180012bff  mov     r14d, 250h
0x180012c05  lea     rcx, [rbp+670h+var_4C0]; void *
0x180012c0c  mov     r8d, r14d; Size
0x180012c0f  xor     edx, edx; Val
0x180012c11  call    memset_0
0x180012c16  mov     eax, [r13+8]
0x180012c1a  lea     rcx, [rsp+770h+FindFileData]; void *
0x180012c1f  mov     rsi, [rsp+770h+Buffer]
0x180012c24  xor     edx, edx
0x180012c26  div     dword ptr [r13+0Ch]
0x180012c2a  mov     rbx, rsi
0x180012c2d  mov     [rbp+670h+var_26C], r12d
0x180012c34  sub     rbx, [rsp+770h+var_730]
0x180012c39  mov     r8d, r14d; Size
0x180012c3c  sar     rbx, 1
0x180012c3f  xor     edx, edx; Val
0x180012c41  mov     edi, eax
0x180012c43  mov     [rbp+670h+var_268], eax
0x180012c49  mov     [rbp+670h+var_4A0], r12d
0x180012c50  mov     [rbp+670h+var_494], r12w
0x180012c58  mov     [rbp+670h+var_270], ebx
0x180012c5e  call    memset_0
0x180012c63  lea     rdx, [rsp+770h+FindFileData]; lpFindFileData
0x180012c68  mov     [rbp+670h+var_4CC], r12d
0x180012c6f  lea     rcx, [rbp+670h+FileName]; lpFileName
0x180012c76  mov     [rbp+670h+var_4C8], edi
0x180012c7c  mov     [rsp+770h+FindFileData.nFileSizeLow], r12d
0x180012c81  mov     [rsp+770h+FindFileData.cFileName], r12w
0x180012c87  mov     [rbp+670h+var_4D0], ebx
0x180012c8d  call    cs:__imp_FindFirstFileW
0x180012c93  mov     r14, rax
0x180012c96  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012c9a  jnz     short loc_180012CC2
0x180012c9c  lea     rax, [rbp+670h+FileName]
0x180012ca3  sub     rsi, rax
0x180012ca6  sar     rsi, 1
0x180012ca9  xor     r9d, r9d; unsigned int
0x180012cac  mov     r8d, esi; unsigned int
0x180012caf  lea     rdx, [rbp+670h+FileName]; unsigned __int16 *
0x180012cb6  call    ?SetGlobalFile@TextFileLogger@@AEAAXPEBGKK@Z; TextFileLogger::SetGlobalFile(ushort const *,ulong,ulong)
0x180012cbb  xor     eax, eax
0x180012cbd  jmp     loc_180012F93
0x180012cc2  lea     rbx, [rsp+770h+FindFileData]
0x180012cc7  lea     rdi, [rbp+670h+var_4C0]
0x180012cce  mov     eax, [rbx+250h]
0x180012cd4  lea     r15, [rbx+254h]
0x180012cdb  add     rax, 16h
0x180012cdf  mov     r9, r15; unsigned int *
0x180012ce2  lea     rdx, [rbx+rax*2]; unsigned __int16 *
0x180012ce6  call    ?WstrToUl@TLogData@@AEAA_NPEBGGPEAK@Z; TLogData::WstrToUl(ushort const *,ushort,ulong *)
0x180012ceb  test    al, al
0x180012ced  jz      short loc_180012D0A
0x180012cef  cmp     [rdi+2Ch], r12w
0x180012cf4  jz      short loc_180012D01
0x180012cf6  mov     eax, [rdi+254h]
0x180012cfc  cmp     [r15], eax
0x180012cff  jbe     short loc_180012D0A
0x180012d01  mov     rax, rdi
0x180012d04  mov     rdi, rbx
0x180012d07  mov     rbx, rax
0x180012d0a  mov     rdx, rbx; lpFindFileData
0x180012d0d  mov     rcx, r14; hFindFile
0x180012d10  call    cs:__imp_FindNextFileW
0x180012d16  test    eax, eax
0x180012d18  jnz     short loc_180012CCE
0x180012d1a  call    cs:__imp_GetLastError
0x180012d20  mov     ebx, eax
0x180012d22  mov     rcx, r14; hFindFile
0x180012d25  cmp     eax, 12h
0x180012d28  jnz     loc_180012F44
0x180012d2e  call    cs:__imp_FindClose
0x180012d34  cmp     [rdi+2Ch], r12w
0x180012d39  jz      loc_180012C9C
0x180012d3f  mov     eax, [rdi+258h]
0x180012d45  lea     rbx, [rdi+254h]
0x180012d4c  mov     r14b, r12b
0x180012d4f  cmp     [rdi+20h], eax
0x180012d52  jnb     short loc_180012DB9
0x180012d54  mov     r9d, [rbx]; unsigned int
0x180012d57  lea     rax, [rbp+670h+FileName]
0x180012d5e  mov     r8, rsi
0x180012d61  lea     rdx, [rbp+670h+FileName]; unsigned __int16 *
0x180012d68  sub     r8, rax
0x180012d6b  sar     r8, 1; unsigned int
0x180012d6e  call    ?SetGlobalFile@TextFileLogger@@AEAAXPEBGKK@Z; TextFileLogger::SetGlobalFile(ushort const *,ulong,ulong)
0x180012d73  xor     r9d, r9d; lpSecurityAttributes
0x180012d76  mov     [rsp+770h+hTemplateFile], r12; hTemplateFile
0x180012d7b  mov     [rsp+770h+dwFlagsAndAttributes], 80000080h; dwFlagsAndAttributes
0x180012d83  lea     rcx, ?g_wszFileCur@@3PAGA; lpFileName
0x180012d8a  mov     edx, 40000000h; dwDesiredAccess
0x180012d8f  mov     [rsp+770h+dwCreationDisposition], 4; dwCreationDisposition
0x180012d97  lea     r8d, [r9+3]; dwShareMode
0x180012d9b  call    cs:__imp_CreateFileW
0x180012da1  mov     [r13+18h], rax
0x180012da5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012da9  jnz     short loc_180012DB9
0x180012dab  call    cs:__imp_GetLastError
0x180012db1  cmp     eax, 5
0x180012db4  jnz     short loc_180012DB9
0x180012db6  mov     r14b, 1
0x180012db9  mov     eax, [rdi+258h]
0x180012dbf  cmp     [rdi+20h], eax
0x180012dc2  jnb     short loc_180012DCD
0x180012dc4  test    r14b, r14b
0x180012dc7  jz      loc_180012CBB
0x180012dcd  mov     r15d, r12d
0x180012dd0  cmp     r15d, 0FFFFFFFFh
0x180012dd4  jnb     loc_180012F07
0x180012dda  mov     edx, [rbx]
0x180012ddc  cmp     edx, 0FFFFFFFFh
0x180012ddf  jnz     short loc_180012E48
0x180012de1  test    r15d, r15d
0x180012de4  jnz     short loc_180012E48
0x180012de6  mov     r9, [rsp+770h+var_730]; unsigned __int16 *
0x180012deb  lea     rdx, [rbp+670h+FileName]; unsigned __int16 *
0x180012df2  mov     rcx, r13; this
0x180012df5  mov     qword ptr [rsp+770h+dwCreationDisposition], rdi; struct TLogData *
0x180012dfa  call    ?GetFirstAvailableFile@TextFileLogger@@AEAAJPEAG_K0PEAUTLogData@@@Z; TextFileLogger::GetFirstAvailableFile(ushort *,unsigned __int64,ushort *,TLogData *)
0x180012dff  mov     r14d, eax
0x180012e02  test    eax, eax
0x180012e04  jns     short loc_180012E54
0x180012e06  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180012e0d  jz      short loc_180012E40
0x180012e0f  mov     rcx, cs:g_pDebug
0x180012e16  lea     r9, aTextfilelogger; "TextFileLogger::DetermineFile"
0x180012e1d  mov     [rsp+770h+dwFlagsAndAttributes], eax
0x180012e21  lea     rdx, aInetsrvIisMbCo_2; "inetsrv\\iis\\mb\\config\\src\\shared\\"...
0x180012e28  lea     rax, aGetfirstavaila; "GetFirstAvailableFile returned hr=0x%x"...
0x180012e2f  mov     r8d, 290h
0x180012e35  mov     qword ptr [rsp+770h+dwCreationDisposition], rax
0x180012e3a  call    cs:__imp_PuDbgPrint
0x180012e40  mov     eax, r14d
0x180012e43  jmp     loc_180012F93
0x180012e48  inc     edx; unsigned int
0x180012e4a  mov     rcx, rdi; this
0x180012e4d  mov     [rbx], edx
0x180012e4f  call    ?SetVersion@TLogData@@QEAAXK@Z; TLogData::SetVersion(ulong)
0x180012e54  lea     rcx, [rbp+670h+FileName]
0x180012e5b  mov     rax, rsi
0x180012e5e  sub     rax, rcx
0x180012e61  lea     r9, a010lu; "%010lu"
0x180012e68  sar     rax, 1
0x180012e6b  mov     r14d, 104h
0x180012e71  sub     r14, rax
0x180012e74  mov     r8d, 0Ah; MaxCount
0x180012e7a  mov     eax, [rbx]
0x180012e7c  mov     rdx, r14; BufferCount
0x180012e7f  sub     eax, [r13+0Ch]
0x180012e83  mov     rcx, rsi; Buffer
0x180012e86  mov     [rsp+770h+dwCreationDisposition], eax
0x180012e8a  call    cs:__imp__snwprintf_s
0x180012e90  test    eax, eax
0x180012e92  js      short loc_180012EFD
0x180012e94  lea     rcx, [rbp+670h+FileName]; lpFileName
0x180012e9b  call    cs:__imp_DeleteFileW
0x180012ea1  mov     eax, [rbx]
0x180012ea3  lea     r9, a010lu; "%010lu"
0x180012eaa  mov     r8d, 0Ah; MaxCount
0x180012eb0  mov     [rsp+770h+dwCreationDisposition], eax
0x180012eb4  mov     rdx, r14; BufferCount
0x180012eb7  mov     rcx, rsi; Buffer
0x180012eba  call    cs:__imp__snwprintf_s
0x180012ec0  test    eax, eax
0x180012ec2  js      short loc_180012EFD
0x180012ec4  lea     rcx, [rbp+670h+FileName]; lpFileName
0x180012ecb  call    cs:__imp_DeleteFileW
0x180012ed1  test    eax, eax
0x180012ed3  jnz     short loc_180012EE8
0x180012ed5  call    cs:__imp_GetLastError
0x180012edb  cmp     eax, 2
0x180012ede  jz      short loc_180012EE8
0x180012ee0  inc     r15d
0x180012ee3  jmp     loc_180012DD0
0x180012ee8  mov     r9d, [rbx]
0x180012eeb  lea     rax, [rbp+670h+FileName]
0x180012ef2  sub     rsi, rax
0x180012ef5  sar     rsi, 1
0x180012ef8  jmp     loc_180012CAC
0x180012efd  mov     eax, 8007000Dh
0x180012f02  jmp     loc_180012F93
0x180012f07  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180012f0e  jz      short loc_180012F3D
0x180012f10  mov     rcx, cs:g_pDebug
0x180012f17  lea     rax, aCannotLogThere; "Cannot log.  There are 0xFFFFFFFF undel"...
0x180012f1e  lea     r9, aTextfilelogger; "TextFileLogger::DetermineFile"
0x180012f25  mov     qword ptr [rsp+770h+dwCreationDisposition], rax
0x180012f2a  mov     r8d, 2C0h
0x180012f30  lea     rdx, aInetsrvIisMbCo_2; "inetsrv\\iis\\mb\\config\\src\\shared\\"...
0x180012f37  call    cs:__imp_PuDbgPrint
0x180012f3d  mov     eax, 80070012h
0x180012f42  jmp     short loc_180012F93
0x180012f44  call    cs:__imp_FindClose
0x180012f4a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180012f51  jz      short loc_180012F84
0x180012f53  mov     rcx, cs:g_pDebug
0x180012f5a  lea     rax, aFindnextfileRe; "FindNextFile returned err=%u\n"
0x180012f61  mov     [rsp+770h+dwFlagsAndAttributes], ebx
0x180012f65  lea     r9, aTextfilelogger; "TextFileLogger::DetermineFile"
0x180012f6c  mov     r8d, 264h
0x180012f72  mov     qword ptr [rsp+770h+dwCreationDisposition], rax
0x180012f77  lea     rdx, aInetsrvIisMbCo_2; "inetsrv\\iis\\mb\\config\\src\\shared\\"...
0x180012f7e  call    cs:__imp_PuDbgPrint
0x180012f84  test    ebx, ebx
0x180012f86  jle     short loc_180012F91
0x180012f88  movzx   ebx, bx
0x180012f8b  or      ebx, 80070000h
0x180012f91  mov     eax, ebx
0x180012f93  mov     rcx, [rbp+670h+var_50]
0x180012f9a  xor     rcx, rsp; StackCookie
0x180012f9d  call    __security_check_cookie
0x180012fa2  add     rsp, 738h
0x180012fa9  pop     r15
0x180012fab  pop     r14
0x180012fad  pop     r13
0x180012faf  pop     r12
0x180012fb1  pop     rdi
0x180012fb2  pop     rsi
0x180012fb3  pop     rbx
0x180012fb4  pop     rbp
0x180012fb5  retn
```
