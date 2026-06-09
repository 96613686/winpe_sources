# DhcpV6AuditLogInit

- ea: `0x180066e90`
- end: `0x18006708c`
- name: `DhcpV6AuditLogInit`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800660dc`

## callees

- `0x1800058bc`
- `0x18001dde0`
- `0x180062128`
- `0x1800626dc`
- `0x180066e90`
- `0x180067094`
- `0x18008f5b4`
- `0x1800cdac0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180066fc4`
- `ADVAPI32!RegSetValueExW` at `0x180066fc4`
- `KERNEL32!InitializeCriticalSection` at `0x18006704a`
- `KERNEL32!InitializeCriticalSection` at `0x18006704a`
- `KERNEL32!GetLocalTime` at `0x180066edd`
- `KERNEL32!GetLocalTime` at `0x180066edd`
- `KERNEL32!GetLastError` at `0x180067017`
- `KERNEL32!GetLastError` at `0x180067035`
- `KERNEL32!GetLastError` at `0x180067066`
- `KERNEL32!GetLastError` at `0x180067017`
- `KERNEL32!GetLastError` at `0x180067035`
- `KERNEL32!GetLastError` at `0x180067066`

## string_xrefs

- `0x180066f08`: `DhcpLogFilePath`
- `0x180066fb6`: `DhcpV6LogFilePath`

## pseudocode

```c
LSTATUS DhcpV6AuditLogInit()
{
  LSTATUS result; // eax
  const wchar_t *lpData; // rcx
  __int64 v2; // rax
  DWORD LastError; // eax
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-28h] BYREF

  SystemTime = 0;
  if ( dword_1800FD1FC )
    return 1247;
  if ( !DhcpGlobalRegParam )
    return 1359;
  GetLocalTime(&SystemTime);
  DhcpV6CurrentDay = SystemTime.wDayOfWeek;
  DhcpV6AuditLogFilePath = 0;
  if ( (unsigned int)DhcpRegGetValue(DhcpGlobalRegParam, L"DhcpLogFilePath") || (lpData = DhcpV6AuditLogFilePath) == 0 )
  {
    lpData = (const wchar_t *)DhcpOemToUnicode(DhcpGlobalOemDatabasePath);
    DhcpV6AuditLogFilePath = lpData;
    if ( !lpData )
      return 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids, lpData);
      lpData = DhcpV6AuditLogFilePath;
    }
  }
  v2 = -1;
  do
    ++v2;
  while ( lpData[v2] );
  result = RegSetValueExW(DhcpGlobalRegParam, L"DhcpV6LogFilePath", 0, 1u, (const BYTE *)lpData, 2 * v2 + 2);
  if ( !result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids,
        DhcpV6AuditLogFilePath);
    if ( CreateDirectoryPathW(DhcpV6AuditLogFilePath) )
    {
      InitializeCriticalSection(&DhcpV6AuditLogCritSect);
      ++dword_1800FD1FC;
      DhcpV6AuditLogStart();
      return 0;
    }
    else
    {
      LastError = GetLastError();
      DhcpServerEventLog(1060, 1, LastError);
      return GetLastError();
    }
  }
  return result;
}

```

## disassembly

```asm
0x180066e90  mov     [rsp+arg_0], rbx
0x180066e95  push    rdi
0x180066e96  sub     rsp, 50h
0x180066e9a  mov     rax, cs:__security_cookie
0x180066ea1  xor     rax, rsp
0x180066ea4  mov     [rsp+58h+var_18], rax
0x180066ea9  xorps   xmm0, xmm0
0x180066eac  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x180066eb1  xor     edi, edi
0x180066eb3  cmp     cs:dword_1800FD1FC, edi
0x180066eb9  jz      short loc_180066EC5
0x180066ebb  mov     eax, 4DFh
0x180066ec0  jmp     loc_180067073
0x180066ec5  cmp     cs:DhcpGlobalRegParam, rdi
0x180066ecc  jnz     short loc_180066ED8
0x180066ece  mov     eax, 54Fh
0x180066ed3  jmp     loc_180067073
0x180066ed8  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x180066edd  call    cs:__imp_GetLocalTime
0x180066ee4  nop     dword ptr [rax+rax+00h]
0x180066ee9  movzx   eax, [rsp+58h+SystemTime.wDayOfWeek]
0x180066eee  mov     cs:DhcpV6CurrentDay, eax
0x180066ef4  mov     cs:DhcpV6AuditLogFilePath, rdi
0x180066efb  lea     r9, DhcpV6AuditLogFilePath
0x180066f02  mov     r8d, 1
0x180066f08  lea     rdx, ValueName; "DhcpLogFilePath"
0x180066f0f  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180066f16  call    DhcpRegGetValue
0x180066f1b  test    eax, eax
0x180066f1d  jnz     short loc_180066F34
0x180066f1f  mov     rcx, cs:DhcpV6AuditLogFilePath
0x180066f26  test    rcx, rcx
0x180066f29  jz      short loc_180066F34
0x180066f2b  lea     rbx, WPP_GLOBAL_Control
0x180066f32  jmp     short loc_180066F90
0x180066f34  xor     edx, edx
0x180066f36  mov     rcx, cs:DhcpGlobalOemDatabasePath; SourceString
0x180066f3d  call    DhcpOemToUnicode
0x180066f42  mov     rcx, rax
0x180066f45  mov     cs:DhcpV6AuditLogFilePath, rax
0x180066f4c  test    rax, rax
0x180066f4f  jnz     short loc_180066F59
0x180066f51  lea     eax, [rcx+8]
0x180066f54  jmp     loc_180067073
0x180066f59  lea     rbx, WPP_GLOBAL_Control
0x180066f60  mov     rax, cs:WPP_GLOBAL_Control
0x180066f67  cmp     rax, rbx
0x180066f6a  jz      short loc_180066F90
0x180066f6c  mov     edx, 10h
0x180066f71  test    [rax+1Ch], dl
0x180066f74  jz      short loc_180066F90
0x180066f76  mov     r9, rcx
0x180066f79  lea     r8, WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids
0x180066f80  mov     rcx, [rax+10h]
0x180066f84  call    WPP_SF_S
0x180066f89  mov     rcx, cs:DhcpV6AuditLogFilePath
0x180066f90  or      rax, 0FFFFFFFFFFFFFFFFh
0x180066f94  inc     rax
0x180066f97  cmp     [rcx+rax*2], di
0x180066f9b  jnz     short loc_180066F94
0x180066f9d  lea     eax, ds:2[rax*2]
0x180066fa4  mov     [rsp+58h+cbData], eax; cbData
0x180066fa8  mov     [rsp+58h+lpData], rcx; lpData
0x180066fad  mov     r9d, 1; dwType
0x180066fb3  xor     r8d, r8d; Reserved
0x180066fb6  lea     rdx, aDhcpv6logfilep; "DhcpV6LogFilePath"
0x180066fbd  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180066fc4  call    cs:__imp_RegSetValueExW
0x180066fcb  nop     dword ptr [rax+rax+00h]
0x180066fd0  test    eax, eax
0x180066fd2  jnz     loc_180067073
0x180066fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180066fdf  cmp     rcx, rbx
0x180066fe2  jz      short loc_180067007
0x180066fe4  test    dword ptr [rcx+1Ch], 8000h
0x180066feb  jz      short loc_180067007
0x180066fed  lea     edx, [rax+11h]
0x180066ff0  mov     r9, cs:DhcpV6AuditLogFilePath
0x180066ff7  lea     r8, WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids
0x180066ffe  mov     rcx, [rcx+10h]
0x180067002  call    WPP_SF_S
0x180067007  mov     rcx, cs:DhcpV6AuditLogFilePath; lpPathName
0x18006700e  call    CreateDirectoryPathW
0x180067013  test    eax, eax
0x180067015  jnz     short loc_180067043
0x180067017  call    cs:__imp_GetLastError
0x18006701e  nop     dword ptr [rax+rax+00h]
0x180067023  mov     r8d, eax
0x180067026  mov     edx, 1
0x18006702b  mov     ecx, 424h
0x180067030  call    DhcpServerEventLog
0x180067035  call    cs:__imp_GetLastError
0x18006703c  nop     dword ptr [rax+rax+00h]
0x180067041  jmp     short loc_180067073
0x180067043  lea     rcx, DhcpV6AuditLogCritSect; lpCriticalSection
0x18006704a  call    cs:__imp_InitializeCriticalSection
0x180067051  nop     dword ptr [rax+rax+00h]
0x180067056  nop
0x180067057  inc     cs:dword_1800FD1FC
0x18006705d  call    DhcpV6AuditLogStart
0x180067062  xor     eax, eax
0x180067064  jmp     short loc_180067073
0x180067066  call    cs:__imp_GetLastError
0x18006706d  nop     dword ptr [rax+rax+00h]
0x180067072  nop
0x180067073  mov     rcx, [rsp+58h+var_18]
0x180067078  xor     rcx, rsp; StackCookie
0x18006707b  call    __security_check_cookie
0x180067080  mov     rbx, [rsp+58h+arg_0]
0x180067085  add     rsp, 50h
0x180067089  pop     rdi
0x18006708a  retn
```
