# DhcpAuditLogInit

- ea: `0x1800038fc`
- end: `0x180003c96`
- name: `DhcpAuditLogInit`
- size: `922`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180025bf4`

## callees

- `0x180003548`
- `0x1800038fc`
- `0x1800058cc`
- `0x18001e828`
- `0x1800623a4`
- `0x180062964`
- `0x18008f418`
- `0x1800cc9e0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180003a32`
- `ADVAPI32!RegSetValueExW` at `0x180003b14`
- `ADVAPI32!RegSetValueExW` at `0x180003a32`
- `ADVAPI32!RegSetValueExW` at `0x180003b14`
- `KERNEL32!InitializeCriticalSection` at `0x180003c3d`
- `KERNEL32!InitializeCriticalSection` at `0x180003c3d`
- `KERNEL32!GetLocalTime` at `0x180003b6a`
- `KERNEL32!GetLocalTime` at `0x180003b6a`
- `KERNEL32!GetLastError` at `0x180003b38`
- `KERNEL32!GetLastError` at `0x180003b54`
- `KERNEL32!GetLastError` at `0x180003c5a`
- `KERNEL32!GetLastError` at `0x180003b38`
- `KERNEL32!GetLastError` at `0x180003b54`
- `KERNEL32!GetLastError` at `0x180003c5a`

## string_xrefs

- `0x180003972`: `DhcpLogFilePath`
- `0x180003a24`: `DhcpLogFilePath`
- `0x180003b06`: `DhcpLogFilePath`

## pseudocode

```c
LSTATUS DhcpAuditLogInit()
{
  LSTATUS result; // eax
  int v1; // esi
  const WCHAR *v2; // rcx
  __int64 v3; // rbx
  const wchar_t *v4; // rax
  const BYTE *lpData; // r8
  __int64 v6; // rax
  int DirectoryPathW; // eax
  const wchar_t *v8; // r9
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-28h] BYREF

  SystemTime = 0;
  if ( dword_1800FAE24 )
    return 1247;
  if ( !DhcpGlobalRegParam )
    return 1359;
  v1 = 0;
  AuditLogFilePath = 0;
  if ( !(unsigned int)DhcpRegGetValue(DhcpGlobalRegParam, L"DhcpLogFilePath")
    && (v2 = AuditLogFilePath) != 0
    && *AuditLogFilePath )
  {
    v3 = -1;
  }
  else
  {
    v4 = (const wchar_t *)DhcpOemToUnicode(DhcpGlobalOemDatabasePath);
    lpData = (const BYTE *)v4;
    AuditLogFilePath = v4;
    if ( !v4 )
      return 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids, v4);
      lpData = (const BYTE *)AuditLogFilePath;
    }
    v3 = -1;
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&lpData[2 * v6] );
    result = RegSetValueExW(DhcpGlobalRegParam, L"DhcpLogFilePath", 0, 1u, lpData, 2 * v6 + 2);
    if ( result )
      return result;
    v1 = 1;
    v2 = AuditLogFilePath;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids, v2);
    v2 = AuditLogFilePath;
  }
  DirectoryPathW = CreateDirectoryPathW(v2);
  if ( DirectoryPathW )
  {
LABEL_31:
    GetLocalTime(&SystemTime);
    CurrentDay = SystemTime.wDayOfWeek;
    if ( (unsigned int)DhcpRegGetValue(DhcpGlobalRegParam, L"DhcpLogDiskSpaceCheckInterval") )
      DiskSpaceCheckInterval = 50;
    if ( (unsigned int)DiskSpaceCheckInterval < 2 )
      DiskSpaceCheckInterval = 2;
    if ( (unsigned int)DiskSpaceCheckInterval > 0xFFFFFFF0 )
      DiskSpaceCheckInterval = -16;
    if ( (unsigned int)DhcpRegGetValue(DhcpGlobalRegParam, L"DhcpLogFilesMaxSize") )
      MaxSizeOfLogFile = 70;
    if ( (unsigned int)DhcpRegGetValue(DhcpGlobalRegParam, L"DhcpLogMinSpaceOnDisk") || !MinSpaceOnDisk )
      MinSpaceOnDisk = 20;
    InitializeCriticalSection(&AuditLogCritSect);
    ++dword_1800FAE24;
    AuditLogStart(v11, v10);
    return 0;
  }
  if ( v1 )
  {
LABEL_29:
    if ( !DirectoryPathW )
    {
      LastError = GetLastError();
      DhcpServerEventLog(1060, 1, LastError);
      return GetLastError();
    }
    goto LABEL_31;
  }
  v8 = (const wchar_t *)DhcpOemToUnicode(DhcpGlobalOemDatabasePath);
  AuditLogFilePath = v8;
  if ( !v8 )
    return 8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids, v8);
    v8 = AuditLogFilePath;
  }
  do
    ++v3;
  while ( v8[v3] );
  result = RegSetValueExW(DhcpGlobalRegParam, L"DhcpLogFilePath", 0, 1u, (const BYTE *)v8, 2 * v3 + 2);
  if ( !result )
  {
    DirectoryPathW = CreateDirectoryPathW(AuditLogFilePath);
    goto LABEL_29;
  }
  return result;
}

```

## disassembly

```asm
0x1800038fc  mov     rax, rsp
0x1800038ff  mov     [rax+8], rbx
0x180003903  mov     [rax+10h], rsi
0x180003907  mov     [rax+18h], rdi
0x18000390b  mov     [rax+20h], r14
0x18000390f  push    r15
0x180003911  sub     rsp, 50h
0x180003915  mov     rax, cs:__security_cookie
0x18000391c  xor     rax, rsp
0x18000391f  mov     [rsp+58h+var_18], rax
0x180003924  xorps   xmm0, xmm0
0x180003927  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x18000392c  xor     r14d, r14d
0x18000392f  cmp     cs:dword_1800FAE24, r14d
0x180003936  jz      short loc_180003942
0x180003938  mov     eax, 4DFh
0x18000393d  jmp     loc_180003C6D
0x180003942  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180003949  test    rcx, rcx
0x18000394c  jnz     short loc_180003958
0x18000394e  mov     eax, 54Fh
0x180003953  jmp     loc_180003C6D
0x180003958  mov     esi, r14d
0x18000395b  mov     cs:AuditLogFilePath, r14
0x180003962  lea     r9, AuditLogFilePath
0x180003969  mov     r15d, 1
0x18000396f  mov     r8d, r15d
0x180003972  lea     rdx, ValueName; "DhcpLogFilePath"
0x180003979  call    DhcpRegGetValue
0x18000397e  test    eax, eax
0x180003980  jnz     short loc_1800039A4
0x180003982  mov     rcx, cs:AuditLogFilePath
0x180003989  test    rcx, rcx
0x18000398c  jz      short loc_1800039A4
0x18000398e  cmp     r14w, [rcx]
0x180003992  jz      short loc_1800039A4
0x180003994  lea     rdi, WPP_GLOBAL_Control
0x18000399b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000399f  jmp     loc_180003A50
0x1800039a4  xor     edx, edx
0x1800039a6  mov     rcx, cs:DhcpGlobalOemDatabasePath; SourceString
0x1800039ad  call    DhcpOemToUnicode
0x1800039b2  mov     r8, rax
0x1800039b5  mov     cs:AuditLogFilePath, rax
0x1800039bc  test    rax, rax
0x1800039bf  jz      loc_180003C68
0x1800039c5  lea     rdi, WPP_GLOBAL_Control
0x1800039cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039d3  cmp     rcx, rdi
0x1800039d6  jz      short loc_1800039FD
0x1800039d8  test    byte ptr [rcx+1Ch], 10h
0x1800039dc  jz      short loc_1800039FD
0x1800039de  mov     edx, 14h
0x1800039e3  mov     r9, rax
0x1800039e6  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x1800039ed  mov     rcx, [rcx+10h]
0x1800039f1  call    WPP_SF_S
0x1800039f6  mov     r8, cs:AuditLogFilePath
0x1800039fd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003a01  mov     rax, rbx
0x180003a04  inc     rax
0x180003a07  cmp     [r8+rax*2], r14w
0x180003a0c  jnz     short loc_180003A04
0x180003a0e  lea     eax, ds:2[rax*2]
0x180003a15  mov     [rsp+58h+cbData], eax; cbData
0x180003a19  mov     [rsp+58h+lpData], r8; lpData
0x180003a1e  mov     r9d, r15d; dwType
0x180003a21  xor     r8d, r8d; Reserved
0x180003a24  lea     rdx, ValueName; "DhcpLogFilePath"
0x180003a2b  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180003a32  call    cs:__imp_RegSetValueExW
0x180003a39  nop     dword ptr [rax+rax+00h]
0x180003a3e  test    eax, eax
0x180003a40  jnz     loc_180003C6D
0x180003a46  mov     esi, r15d
0x180003a49  mov     rcx, cs:AuditLogFilePath
0x180003a50  mov     rax, cs:WPP_GLOBAL_Control
0x180003a57  cmp     rax, rdi
0x180003a5a  jz      short loc_180003A84
0x180003a5c  test    dword ptr [rax+1Ch], 8000h
0x180003a63  jz      short loc_180003A84
0x180003a65  mov     edx, 15h
0x180003a6a  mov     r9, rcx
0x180003a6d  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x180003a74  mov     rcx, [rax+10h]
0x180003a78  call    WPP_SF_S
0x180003a7d  mov     rcx, cs:AuditLogFilePath; lpPathName
0x180003a84  call    CreateDirectoryPathW
0x180003a89  test    eax, eax
0x180003a8b  jnz     loc_180003B65
0x180003a91  test    esi, esi
0x180003a93  jnz     loc_180003B34
0x180003a99  xor     edx, edx
0x180003a9b  mov     rcx, cs:DhcpGlobalOemDatabasePath; SourceString
0x180003aa2  call    DhcpOemToUnicode
0x180003aa7  mov     r9, rax
0x180003aaa  mov     cs:AuditLogFilePath, rax
0x180003ab1  test    rax, rax
0x180003ab4  jz      loc_180003C68
0x180003aba  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ac1  cmp     rcx, rdi
0x180003ac4  jz      short loc_180003AE6
0x180003ac6  test    byte ptr [rcx+1Ch], 10h
0x180003aca  jz      short loc_180003AE6
0x180003acc  lea     edx, [rsi+16h]
0x180003acf  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x180003ad6  mov     rcx, [rcx+10h]
0x180003ada  call    WPP_SF_S
0x180003adf  mov     r9, cs:AuditLogFilePath
0x180003ae6  inc     rbx
0x180003ae9  cmp     [r9+rbx*2], r14w
0x180003aee  jnz     short loc_180003AE6
0x180003af0  lea     eax, ds:2[rbx*2]
0x180003af7  mov     [rsp+58h+cbData], eax; cbData
0x180003afb  mov     [rsp+58h+lpData], r9; lpData
0x180003b00  mov     r9d, r15d; dwType
0x180003b03  xor     r8d, r8d; Reserved
0x180003b06  lea     rdx, ValueName; "DhcpLogFilePath"
0x180003b0d  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180003b14  call    cs:__imp_RegSetValueExW
0x180003b1b  nop     dword ptr [rax+rax+00h]
0x180003b20  test    eax, eax
0x180003b22  jnz     loc_180003C6D
0x180003b28  mov     rcx, cs:AuditLogFilePath; lpPathName
0x180003b2f  call    CreateDirectoryPathW
0x180003b34  test    eax, eax
0x180003b36  jnz     short loc_180003B65
0x180003b38  call    cs:__imp_GetLastError
0x180003b3f  nop     dword ptr [rax+rax+00h]
0x180003b44  mov     r8d, eax
0x180003b47  mov     edx, r15d
0x180003b4a  mov     ecx, 424h
0x180003b4f  call    DhcpServerEventLog
0x180003b54  call    cs:__imp_GetLastError
0x180003b5b  nop     dword ptr [rax+rax+00h]
0x180003b60  jmp     loc_180003C6D
0x180003b65  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x180003b6a  call    cs:__imp_GetLocalTime
0x180003b71  nop     dword ptr [rax+rax+00h]
0x180003b76  movzx   eax, [rsp+58h+SystemTime.wDayOfWeek]
0x180003b7b  mov     cs:CurrentDay, eax
0x180003b81  lea     r9, DiskSpaceCheckInterval
0x180003b88  mov     ebx, 4
0x180003b8d  mov     r8d, ebx
0x180003b90  lea     rdx, aDhcplogdiskspa; "DhcpLogDiskSpaceCheckInterval"
0x180003b97  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180003b9e  call    DhcpRegGetValue
0x180003ba3  test    eax, eax
0x180003ba5  jz      short loc_180003BB1
0x180003ba7  mov     cs:DiskSpaceCheckInterval, 32h ; '2'
0x180003bb1  cmp     cs:DiskSpaceCheckInterval, 2
0x180003bb8  jnb     short loc_180003BC4
0x180003bba  mov     cs:DiskSpaceCheckInterval, 2
0x180003bc4  mov     eax, 0FFFFFFF0h
0x180003bc9  cmp     cs:DiskSpaceCheckInterval, eax
0x180003bcf  jbe     short loc_180003BD7
0x180003bd1  mov     cs:DiskSpaceCheckInterval, eax
0x180003bd7  lea     r9, MaxSizeOfLogFile
0x180003bde  mov     r8d, ebx
0x180003be1  lea     rdx, aDhcplogfilesma; "DhcpLogFilesMaxSize"
0x180003be8  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180003bef  call    DhcpRegGetValue
0x180003bf4  test    eax, eax
0x180003bf6  jz      short loc_180003C02
0x180003bf8  mov     cs:MaxSizeOfLogFile, 46h ; 'F'
0x180003c02  lea     r9, MinSpaceOnDisk
0x180003c09  mov     r8d, ebx
0x180003c0c  lea     rdx, aDhcplogminspac; "DhcpLogMinSpaceOnDisk"
0x180003c13  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180003c1a  call    DhcpRegGetValue
0x180003c1f  test    eax, eax
0x180003c21  jnz     short loc_180003C2C
0x180003c23  cmp     cs:MinSpaceOnDisk, r14d
0x180003c2a  jnz     short loc_180003C36
0x180003c2c  mov     cs:MinSpaceOnDisk, 14h
0x180003c36  lea     rcx, AuditLogCritSect; lpCriticalSection
0x180003c3d  call    cs:__imp_InitializeCriticalSection
0x180003c44  nop     dword ptr [rax+rax+00h]
0x180003c49  nop
0x180003c4a  add     cs:dword_1800FAE24, r15d
0x180003c51  call    AuditLogStart
0x180003c56  xor     eax, eax
0x180003c58  jmp     short loc_180003C6D
0x180003c5a  call    cs:__imp_GetLastError
0x180003c61  nop     dword ptr [rax+rax+00h]
0x180003c66  jmp     short loc_180003C6D
0x180003c68  mov     eax, 8
0x180003c6d  mov     rcx, [rsp+58h+var_18]
0x180003c72  xor     rcx, rsp; StackCookie
0x180003c75  call    __security_check_cookie
0x180003c7a  mov     rbx, [rsp+58h+arg_0]
0x180003c7f  mov     rsi, [rsp+58h+arg_8]
0x180003c84  mov     rdi, [rsp+58h+arg_10]
0x180003c89  mov     r14, [rsp+58h+arg_18]
0x180003c8e  add     rsp, 50h
0x180003c92  pop     r15
0x180003c94  retn
```
