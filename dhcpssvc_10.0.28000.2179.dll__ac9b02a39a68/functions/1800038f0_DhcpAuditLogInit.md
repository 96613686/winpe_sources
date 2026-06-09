# DhcpAuditLogInit

- ea: `0x1800038f0`
- end: `0x180003c8a`
- name: `DhcpAuditLogInit`
- size: `922`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180025144`

## callees

- `0x18000353c`
- `0x1800038f0`
- `0x1800058bc`
- `0x18001dde0`
- `0x180062128`
- `0x1800626dc`
- `0x18008f5b4`
- `0x1800cdac0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180003a26`
- `ADVAPI32!RegSetValueExW` at `0x180003b08`
- `ADVAPI32!RegSetValueExW` at `0x180003a26`
- `ADVAPI32!RegSetValueExW` at `0x180003b08`
- `KERNEL32!InitializeCriticalSection` at `0x180003c31`
- `KERNEL32!InitializeCriticalSection` at `0x180003c31`
- `KERNEL32!GetLocalTime` at `0x180003b5e`
- `KERNEL32!GetLocalTime` at `0x180003b5e`
- `KERNEL32!GetLastError` at `0x180003b2c`
- `KERNEL32!GetLastError` at `0x180003b48`
- `KERNEL32!GetLastError` at `0x180003c4e`
- `KERNEL32!GetLastError` at `0x180003b2c`
- `KERNEL32!GetLastError` at `0x180003b48`
- `KERNEL32!GetLastError` at `0x180003c4e`

## string_xrefs

- `0x180003966`: `DhcpLogFilePath`
- `0x180003a18`: `DhcpLogFilePath`
- `0x180003afa`: `DhcpLogFilePath`

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
  _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-28h] BYREF

  SystemTime = 0;
  if ( dword_1800FCE44 )
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
    ++dword_1800FCE44;
    AuditLogStart();
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
0x1800038f0  mov     rax, rsp
0x1800038f3  mov     [rax+8], rbx
0x1800038f7  mov     [rax+10h], rsi
0x1800038fb  mov     [rax+18h], rdi
0x1800038ff  mov     [rax+20h], r14
0x180003903  push    r15
0x180003905  sub     rsp, 50h
0x180003909  mov     rax, cs:__security_cookie
0x180003910  xor     rax, rsp
0x180003913  mov     [rsp+58h+var_18], rax
0x180003918  xorps   xmm0, xmm0
0x18000391b  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x180003920  xor     r14d, r14d
0x180003923  cmp     cs:dword_1800FCE44, r14d
0x18000392a  jz      short loc_180003936
0x18000392c  mov     eax, 4DFh
0x180003931  jmp     loc_180003C61
0x180003936  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x18000393d  test    rcx, rcx
0x180003940  jnz     short loc_18000394C
0x180003942  mov     eax, 54Fh
0x180003947  jmp     loc_180003C61
0x18000394c  mov     esi, r14d
0x18000394f  mov     cs:AuditLogFilePath, r14
0x180003956  lea     r9, AuditLogFilePath
0x18000395d  mov     r15d, 1
0x180003963  mov     r8d, r15d
0x180003966  lea     rdx, ValueName; "DhcpLogFilePath"
0x18000396d  call    DhcpRegGetValue
0x180003972  test    eax, eax
0x180003974  jnz     short loc_180003998
0x180003976  mov     rcx, cs:AuditLogFilePath
0x18000397d  test    rcx, rcx
0x180003980  jz      short loc_180003998
0x180003982  cmp     r14w, [rcx]
0x180003986  jz      short loc_180003998
0x180003988  lea     rdi, WPP_GLOBAL_Control
0x18000398f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003993  jmp     loc_180003A44
0x180003998  xor     edx, edx
0x18000399a  mov     rcx, cs:DhcpGlobalOemDatabasePath; SourceString
0x1800039a1  call    DhcpOemToUnicode
0x1800039a6  mov     r8, rax
0x1800039a9  mov     cs:AuditLogFilePath, rax
0x1800039b0  test    rax, rax
0x1800039b3  jz      loc_180003C5C
0x1800039b9  lea     rdi, WPP_GLOBAL_Control
0x1800039c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039c7  cmp     rcx, rdi
0x1800039ca  jz      short loc_1800039F1
0x1800039cc  test    byte ptr [rcx+1Ch], 10h
0x1800039d0  jz      short loc_1800039F1
0x1800039d2  mov     edx, 14h
0x1800039d7  mov     r9, rax
0x1800039da  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x1800039e1  mov     rcx, [rcx+10h]
0x1800039e5  call    WPP_SF_S
0x1800039ea  mov     r8, cs:AuditLogFilePath
0x1800039f1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800039f5  mov     rax, rbx
0x1800039f8  inc     rax
0x1800039fb  cmp     [r8+rax*2], r14w
0x180003a00  jnz     short loc_1800039F8
0x180003a02  lea     eax, ds:2[rax*2]
0x180003a09  mov     [rsp+58h+cbData], eax; cbData
0x180003a0d  mov     [rsp+58h+lpData], r8; lpData
0x180003a12  mov     r9d, r15d; dwType
0x180003a15  xor     r8d, r8d; Reserved
0x180003a18  lea     rdx, ValueName; "DhcpLogFilePath"
0x180003a1f  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180003a26  call    cs:__imp_RegSetValueExW
0x180003a2d  nop     dword ptr [rax+rax+00h]
0x180003a32  test    eax, eax
0x180003a34  jnz     loc_180003C61
0x180003a3a  mov     esi, r15d
0x180003a3d  mov     rcx, cs:AuditLogFilePath
0x180003a44  mov     rax, cs:WPP_GLOBAL_Control
0x180003a4b  cmp     rax, rdi
0x180003a4e  jz      short loc_180003A78
0x180003a50  test    dword ptr [rax+1Ch], 8000h
0x180003a57  jz      short loc_180003A78
0x180003a59  mov     edx, 15h
0x180003a5e  mov     r9, rcx
0x180003a61  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x180003a68  mov     rcx, [rax+10h]
0x180003a6c  call    WPP_SF_S
0x180003a71  mov     rcx, cs:AuditLogFilePath; lpPathName
0x180003a78  call    CreateDirectoryPathW
0x180003a7d  test    eax, eax
0x180003a7f  jnz     loc_180003B59
0x180003a85  test    esi, esi
0x180003a87  jnz     loc_180003B28
0x180003a8d  xor     edx, edx
0x180003a8f  mov     rcx, cs:DhcpGlobalOemDatabasePath; SourceString
0x180003a96  call    DhcpOemToUnicode
0x180003a9b  mov     r9, rax
0x180003a9e  mov     cs:AuditLogFilePath, rax
0x180003aa5  test    rax, rax
0x180003aa8  jz      loc_180003C5C
0x180003aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ab5  cmp     rcx, rdi
0x180003ab8  jz      short loc_180003ADA
0x180003aba  test    byte ptr [rcx+1Ch], 10h
0x180003abe  jz      short loc_180003ADA
0x180003ac0  lea     edx, [rsi+16h]
0x180003ac3  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x180003aca  mov     rcx, [rcx+10h]
0x180003ace  call    WPP_SF_S
0x180003ad3  mov     r9, cs:AuditLogFilePath
0x180003ada  inc     rbx
0x180003add  cmp     [r9+rbx*2], r14w
0x180003ae2  jnz     short loc_180003ADA
0x180003ae4  lea     eax, ds:2[rbx*2]
0x180003aeb  mov     [rsp+58h+cbData], eax; cbData
0x180003aef  mov     [rsp+58h+lpData], r9; lpData
0x180003af4  mov     r9d, r15d; dwType
0x180003af7  xor     r8d, r8d; Reserved
0x180003afa  lea     rdx, ValueName; "DhcpLogFilePath"
0x180003b01  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180003b08  call    cs:__imp_RegSetValueExW
0x180003b0f  nop     dword ptr [rax+rax+00h]
0x180003b14  test    eax, eax
0x180003b16  jnz     loc_180003C61
0x180003b1c  mov     rcx, cs:AuditLogFilePath; lpPathName
0x180003b23  call    CreateDirectoryPathW
0x180003b28  test    eax, eax
0x180003b2a  jnz     short loc_180003B59
0x180003b2c  call    cs:__imp_GetLastError
0x180003b33  nop     dword ptr [rax+rax+00h]
0x180003b38  mov     r8d, eax
0x180003b3b  mov     edx, r15d
0x180003b3e  mov     ecx, 424h
0x180003b43  call    DhcpServerEventLog
0x180003b48  call    cs:__imp_GetLastError
0x180003b4f  nop     dword ptr [rax+rax+00h]
0x180003b54  jmp     loc_180003C61
0x180003b59  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x180003b5e  call    cs:__imp_GetLocalTime
0x180003b65  nop     dword ptr [rax+rax+00h]
0x180003b6a  movzx   eax, [rsp+58h+SystemTime.wDayOfWeek]
0x180003b6f  mov     cs:CurrentDay, eax
0x180003b75  lea     r9, DiskSpaceCheckInterval
0x180003b7c  mov     ebx, 4
0x180003b81  mov     r8d, ebx
0x180003b84  lea     rdx, aDhcplogdiskspa; "DhcpLogDiskSpaceCheckInterval"
0x180003b8b  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180003b92  call    DhcpRegGetValue
0x180003b97  test    eax, eax
0x180003b99  jz      short loc_180003BA5
0x180003b9b  mov     cs:DiskSpaceCheckInterval, 32h ; '2'
0x180003ba5  cmp     cs:DiskSpaceCheckInterval, 2
0x180003bac  jnb     short loc_180003BB8
0x180003bae  mov     cs:DiskSpaceCheckInterval, 2
0x180003bb8  mov     eax, 0FFFFFFF0h
0x180003bbd  cmp     cs:DiskSpaceCheckInterval, eax
0x180003bc3  jbe     short loc_180003BCB
0x180003bc5  mov     cs:DiskSpaceCheckInterval, eax
0x180003bcb  lea     r9, MaxSizeOfLogFile
0x180003bd2  mov     r8d, ebx
0x180003bd5  lea     rdx, aDhcplogfilesma; "DhcpLogFilesMaxSize"
0x180003bdc  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180003be3  call    DhcpRegGetValue
0x180003be8  test    eax, eax
0x180003bea  jz      short loc_180003BF6
0x180003bec  mov     cs:MaxSizeOfLogFile, 46h ; 'F'
0x180003bf6  lea     r9, MinSpaceOnDisk
0x180003bfd  mov     r8d, ebx
0x180003c00  lea     rdx, aDhcplogminspac; "DhcpLogMinSpaceOnDisk"
0x180003c07  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180003c0e  call    DhcpRegGetValue
0x180003c13  test    eax, eax
0x180003c15  jnz     short loc_180003C20
0x180003c17  cmp     cs:MinSpaceOnDisk, r14d
0x180003c1e  jnz     short loc_180003C2A
0x180003c20  mov     cs:MinSpaceOnDisk, 14h
0x180003c2a  lea     rcx, AuditLogCritSect; lpCriticalSection
0x180003c31  call    cs:__imp_InitializeCriticalSection
0x180003c38  nop     dword ptr [rax+rax+00h]
0x180003c3d  nop
0x180003c3e  add     cs:dword_1800FCE44, r15d
0x180003c45  call    AuditLogStart
0x180003c4a  xor     eax, eax
0x180003c4c  jmp     short loc_180003C61
0x180003c4e  call    cs:__imp_GetLastError
0x180003c55  nop     dword ptr [rax+rax+00h]
0x180003c5a  jmp     short loc_180003C61
0x180003c5c  mov     eax, 8
0x180003c61  mov     rcx, [rsp+58h+var_18]
0x180003c66  xor     rcx, rsp; StackCookie
0x180003c69  call    __security_check_cookie
0x180003c6e  mov     rbx, [rsp+58h+arg_0]
0x180003c73  mov     rsi, [rsp+58h+arg_8]
0x180003c78  mov     rdi, [rsp+58h+arg_10]
0x180003c7d  mov     r14, [rsp+58h+arg_18]
0x180003c82  add     rsp, 50h
0x180003c86  pop     r15
0x180003c88  retn
```
