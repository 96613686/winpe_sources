# DhcpV6AuditLogInit

- ea: `0x1800670ec`
- end: `0x1800672e8`
- name: `DhcpV6AuditLogInit`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18006632c`

## callees

- `0x1800058cc`
- `0x18001e828`
- `0x1800623a4`
- `0x180062964`
- `0x1800670ec`
- `0x1800672f0`
- `0x18008f418`
- `0x1800cc9e0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180067220`
- `ADVAPI32!RegSetValueExW` at `0x180067220`
- `KERNEL32!InitializeCriticalSection` at `0x1800672a6`
- `KERNEL32!InitializeCriticalSection` at `0x1800672a6`
- `KERNEL32!GetLocalTime` at `0x180067139`
- `KERNEL32!GetLocalTime` at `0x180067139`
- `KERNEL32!GetLastError` at `0x180067273`
- `KERNEL32!GetLastError` at `0x180067291`
- `KERNEL32!GetLastError` at `0x1800672c2`
- `KERNEL32!GetLastError` at `0x180067273`
- `KERNEL32!GetLastError` at `0x180067291`
- `KERNEL32!GetLastError` at `0x1800672c2`

## string_xrefs

- `0x180067164`: `DhcpLogFilePath`
- `0x180067212`: `DhcpV6LogFilePath`

## pseudocode

```c
LSTATUS DhcpV6AuditLogInit()
{
  LSTATUS result; // eax
  const wchar_t *lpData; // rcx
  __int64 v2; // rax
  DWORD LastError; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-28h] BYREF

  SystemTime = 0;
  if ( dword_1800FB230 )
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
      ++dword_1800FB230;
      DhcpV6AuditLogStart(v5, v4);
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
0x1800670ec  mov     [rsp+arg_0], rbx
0x1800670f1  push    rdi
0x1800670f2  sub     rsp, 50h
0x1800670f6  mov     rax, cs:__security_cookie
0x1800670fd  xor     rax, rsp
0x180067100  mov     [rsp+58h+var_18], rax
0x180067105  xorps   xmm0, xmm0
0x180067108  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x18006710d  xor     edi, edi
0x18006710f  cmp     cs:dword_1800FB230, edi
0x180067115  jz      short loc_180067121
0x180067117  mov     eax, 4DFh
0x18006711c  jmp     loc_1800672CF
0x180067121  cmp     cs:DhcpGlobalRegParam, rdi
0x180067128  jnz     short loc_180067134
0x18006712a  mov     eax, 54Fh
0x18006712f  jmp     loc_1800672CF
0x180067134  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x180067139  call    cs:__imp_GetLocalTime
0x180067140  nop     dword ptr [rax+rax+00h]
0x180067145  movzx   eax, [rsp+58h+SystemTime.wDayOfWeek]
0x18006714a  mov     cs:DhcpV6CurrentDay, eax
0x180067150  mov     cs:DhcpV6AuditLogFilePath, rdi
0x180067157  lea     r9, DhcpV6AuditLogFilePath
0x18006715e  mov     r8d, 1
0x180067164  lea     rdx, ValueName; "DhcpLogFilePath"
0x18006716b  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180067172  call    DhcpRegGetValue
0x180067177  test    eax, eax
0x180067179  jnz     short loc_180067190
0x18006717b  mov     rcx, cs:DhcpV6AuditLogFilePath
0x180067182  test    rcx, rcx
0x180067185  jz      short loc_180067190
0x180067187  lea     rbx, WPP_GLOBAL_Control
0x18006718e  jmp     short loc_1800671EC
0x180067190  xor     edx, edx
0x180067192  mov     rcx, cs:DhcpGlobalOemDatabasePath; SourceString
0x180067199  call    DhcpOemToUnicode
0x18006719e  mov     rcx, rax
0x1800671a1  mov     cs:DhcpV6AuditLogFilePath, rax
0x1800671a8  test    rax, rax
0x1800671ab  jnz     short loc_1800671B5
0x1800671ad  lea     eax, [rcx+8]
0x1800671b0  jmp     loc_1800672CF
0x1800671b5  lea     rbx, WPP_GLOBAL_Control
0x1800671bc  mov     rax, cs:WPP_GLOBAL_Control
0x1800671c3  cmp     rax, rbx
0x1800671c6  jz      short loc_1800671EC
0x1800671c8  mov     edx, 10h
0x1800671cd  test    [rax+1Ch], dl
0x1800671d0  jz      short loc_1800671EC
0x1800671d2  mov     r9, rcx
0x1800671d5  lea     r8, WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids
0x1800671dc  mov     rcx, [rax+10h]
0x1800671e0  call    WPP_SF_S
0x1800671e5  mov     rcx, cs:DhcpV6AuditLogFilePath
0x1800671ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800671f0  inc     rax
0x1800671f3  cmp     [rcx+rax*2], di
0x1800671f7  jnz     short loc_1800671F0
0x1800671f9  lea     eax, ds:2[rax*2]
0x180067200  mov     [rsp+58h+cbData], eax; cbData
0x180067204  mov     [rsp+58h+lpData], rcx; lpData
0x180067209  mov     r9d, 1; dwType
0x18006720f  xor     r8d, r8d; Reserved
0x180067212  lea     rdx, aDhcpv6logfilep; "DhcpV6LogFilePath"
0x180067219  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180067220  call    cs:__imp_RegSetValueExW
0x180067227  nop     dword ptr [rax+rax+00h]
0x18006722c  test    eax, eax
0x18006722e  jnz     loc_1800672CF
0x180067234  mov     rcx, cs:WPP_GLOBAL_Control
0x18006723b  cmp     rcx, rbx
0x18006723e  jz      short loc_180067263
0x180067240  test    dword ptr [rcx+1Ch], 8000h
0x180067247  jz      short loc_180067263
0x180067249  lea     edx, [rax+11h]
0x18006724c  mov     r9, cs:DhcpV6AuditLogFilePath
0x180067253  lea     r8, WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids
0x18006725a  mov     rcx, [rcx+10h]
0x18006725e  call    WPP_SF_S
0x180067263  mov     rcx, cs:DhcpV6AuditLogFilePath; lpPathName
0x18006726a  call    CreateDirectoryPathW
0x18006726f  test    eax, eax
0x180067271  jnz     short loc_18006729F
0x180067273  call    cs:__imp_GetLastError
0x18006727a  nop     dword ptr [rax+rax+00h]
0x18006727f  mov     r8d, eax
0x180067282  mov     edx, 1
0x180067287  mov     ecx, 424h
0x18006728c  call    DhcpServerEventLog
0x180067291  call    cs:__imp_GetLastError
0x180067298  nop     dword ptr [rax+rax+00h]
0x18006729d  jmp     short loc_1800672CF
0x18006729f  lea     rcx, DhcpV6AuditLogCritSect; lpCriticalSection
0x1800672a6  call    cs:__imp_InitializeCriticalSection
0x1800672ad  nop     dword ptr [rax+rax+00h]
0x1800672b2  nop
0x1800672b3  inc     cs:dword_1800FB230
0x1800672b9  call    DhcpV6AuditLogStart
0x1800672be  xor     eax, eax
0x1800672c0  jmp     short loc_1800672CF
0x1800672c2  call    cs:__imp_GetLastError
0x1800672c9  nop     dword ptr [rax+rax+00h]
0x1800672ce  nop
0x1800672cf  mov     rcx, [rsp+58h+var_18]
0x1800672d4  xor     rcx, rsp; StackCookie
0x1800672d7  call    __security_check_cookie
0x1800672dc  mov     rbx, [rsp+58h+arg_0]
0x1800672e1  add     rsp, 50h
0x1800672e5  pop     rdi
0x1800672e6  retn
```
