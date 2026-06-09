# RassrvLaunchMMC

- ea: `0x1800214a0`
- end: `0x18002166e`
- name: `RassrvLaunchMMC`
- size: `462`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012a10`
- `0x18002326c`
- `0x180024fdc`
- `0x180025730`

## callees

- `0x1800214a0`
- `0x180021b70`
- `0x180021d8c`
- `0x18002f382`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021640`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002162d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021638`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002162d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021638`
- `rtutils!TracePrintfExA` at `0x1800215c5`
- `rtutils!TracePrintfExA` at `0x1800215c5`
- `KERNEL32!CreateProcessA` at `0x18002161e`
- `KERNEL32!CreateProcessA` at `0x18002161e`
- `KERNEL32!GetSystemDirectoryA` at `0x180021564`
- `KERNEL32!GetSystemDirectoryA` at `0x180021564`

## string_xrefs

- `0x180021506`: `compmgmt.msc`
- `0x180021548`: `RassrvLaunchMMC: StringCchCopyExA failed. hr = 0x%x`

## pseudocode

```c
__int64 __fastcall RassrvLaunchMMC(int a1)
{
  STRSAFE_LPSTR *v2; // r9
  int v3; // ebx
  int v4; // ebx
  const char *v5; // rbx
  unsigned int v6; // ebx
  HRESULT v7; // edi
  HRESULT v8; // eax
  size_t *dwFlags; // [rsp+20h] [rbp-E0h]
  DWORD pszFormat; // [rsp+28h] [rbp-D8h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOA StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  char pszDest[272]; // [rsp+E0h] [rbp-20h] BYREF
  CHAR Buffer[272]; // [rsp+1F0h] [rbp+F0h] BYREF

  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo, 0, 0x64u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v3 = a1 - 1;
  if ( !v3 )
  {
    v5 = "netmgmt.msc";
    goto LABEL_10;
  }
  v4 = v3 - 1;
  if ( v4 )
  {
    if ( v4 == 2 )
      v5 = "compmgmt.msc";
    else
      v5 = "rrasmgmt.msc";
LABEL_10:
    GetSystemDirectoryA(Buffer, 0x105u);
    v8 = StringCchPrintfExA(pszDest, 0x105u, 0, 0, 0x100u, "mmc %s\\%s", Buffer, v5);
    v6 = 0;
    LOWORD(v7) = v8;
    if ( v8 < 0 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "RassrvLaunchMMC: StringCchPrintfExA failed. hr = 0x%x", (unsigned int)v8);
      return (unsigned __int16)v7;
    }
    goto LABEL_14;
  }
  v6 = 0;
  v7 = StringCchCopyExA(pszDest, 0x105u, "mmc.exe", v2, dwFlags, pszFormat);
  if ( v7 < 0 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "RassrvLaunchMMC: StringCchCopyExA failed. hr = 0x%x", (unsigned int)v7);
    return (unsigned __int16)v7;
  }
LABEL_14:
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  if ( CreateProcessA(0, pszDest, 0, 0, 0, 0x20u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    CloseHandle(ProcessInformation.hThread);
    CloseHandle(ProcessInformation.hProcess);
  }
  else
  {
    return GetLastError();
  }
  return v6;
}

```

## disassembly

```asm
0x1800214a0  mov     [rsp-8+arg_0], rbx
0x1800214a5  mov     [rsp-8+arg_8], rdi
0x1800214aa  push    rbp
0x1800214ab  lea     rbp, [rsp-210h]
0x1800214b3  sub     rsp, 310h
0x1800214ba  mov     rax, cs:__security_cookie
0x1800214c1  xor     rax, rsp
0x1800214c4  mov     [rbp+210h+var_10], rax
0x1800214cb  xor     eax, eax
0x1800214cd  mov     ebx, ecx
0x1800214cf  xor     edx, edx; Val
0x1800214d1  mov     dword ptr [rsp+310h+StartupInfo+4], eax
0x1800214d5  lea     rcx, [rsp+310h+StartupInfo]; void *
0x1800214da  lea     r8d, [rax+64h]; Size
0x1800214de  call    memset_0
0x1800214e3  xor     eax, eax
0x1800214e5  xorps   xmm0, xmm0
0x1800214e8  mov     qword ptr [rsp+310h+ProcessInformation.dwProcessId], rax
0x1800214ed  movups  xmmword ptr [rsp+310h+ProcessInformation.hProcess], xmm0
0x1800214f2  sub     ebx, 1
0x1800214f5  jz      short loc_180021551
0x1800214f7  sub     ebx, 1
0x1800214fa  jz      short loc_180021518
0x1800214fc  sub     ebx, 1
0x1800214ff  jz      short loc_18002150F
0x180021501  cmp     ebx, 1
0x180021504  jnz     short loc_18002150F
0x180021506  lea     rbx, aCompmgmtMsc; "compmgmt.msc"
0x18002150d  jmp     short loc_180021558
0x18002150f  lea     rbx, aRrasmgmtMsc; "rrasmgmt.msc"
0x180021516  jmp     short loc_180021558
0x180021518  lea     r8, pszSrc; "mmc.exe"
0x18002151f  mov     edx, 105h; cchDest
0x180021524  lea     rcx, [rbp+210h+pszDest]; pszDest
0x180021528  call    StringCchCopyExA
0x18002152d  xor     ebx, ebx
0x18002152f  mov     edi, eax
0x180021531  test    eax, eax
0x180021533  jns     loc_1800215D0
0x180021539  mov     ecx, cs:g_dwTraceId
0x18002153f  cmp     ecx, 0FFFFFFFFh
0x180021542  jz      loc_1800215CB
0x180021548  lea     r8, aRassrvlaunchmm; "RassrvLaunchMMC: StringCchCopyExA faile"...
0x18002154f  jmp     short loc_1800215BD
0x180021551  lea     rbx, aNetmgmtMsc; "netmgmt.msc"
0x180021558  mov     edx, 105h; uSize
0x18002155d  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x180021564  call    cs:__imp_GetSystemDirectoryA
0x18002156a  mov     [rsp+310h+lpCurrentDirectory], rbx
0x18002156f  lea     rax, [rbp+210h+Buffer]
0x180021576  mov     [rsp+310h+lpEnvironment], rax
0x18002157b  lea     rcx, [rbp+210h+pszDest]; pszDest
0x18002157f  lea     rax, aMmcSS; "mmc %s\\%s"
0x180021586  xor     r9d, r9d; pcchRemaining
0x180021589  mov     [rsp+310h+pszFormat], rax; pszFormat
0x18002158e  xor     r8d, r8d; ppszDestEnd
0x180021591  mov     edx, 105h; cchDest
0x180021596  mov     dword ptr [rsp+310h+dwFlags], 100h; dwFlags
0x18002159e  call    StringCchPrintfExA
0x1800215a3  xor     ebx, ebx
0x1800215a5  mov     edi, eax
0x1800215a7  test    eax, eax
0x1800215a9  jns     short loc_1800215D0
0x1800215ab  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800215b1  cmp     ecx, 0FFFFFFFFh
0x1800215b4  jz      short loc_1800215CB
0x1800215b6  lea     r8, aRassrvlaunchmm_0; "RassrvLaunchMMC: StringCchPrintfExA fai"...
0x1800215bd  mov     r9d, edi
0x1800215c0  mov     edx, 0Ch; dwFlags
0x1800215c5  call    cs:__imp_TracePrintfExA
0x1800215cb  movzx   ebx, di
0x1800215ce  jmp     short loc_180021648
0x1800215d0  xor     edx, edx; Val
0x1800215d2  lea     rcx, [rsp+310h+StartupInfo+4]; void *
0x1800215d7  lea     r8d, [rdx+64h]; Size
0x1800215db  call    memset_0
0x1800215e0  lea     rax, [rsp+310h+ProcessInformation]
0x1800215e5  mov     [rsp+310h+StartupInfo.cb], 68h ; 'h'
0x1800215ed  mov     [rsp+310h+lpProcessInformation], rax; lpProcessInformation
0x1800215f2  lea     rdx, [rbp+210h+pszDest]; lpCommandLine
0x1800215f6  lea     rax, [rsp+310h+StartupInfo]
0x1800215fb  xor     r9d, r9d; lpThreadAttributes
0x1800215fe  mov     [rsp+310h+lpStartupInfo], rax; lpStartupInfo
0x180021603  xor     r8d, r8d; lpProcessAttributes
0x180021606  mov     [rsp+310h+lpCurrentDirectory], rbx; lpCurrentDirectory
0x18002160b  xor     ecx, ecx; lpApplicationName
0x18002160d  mov     [rsp+310h+lpEnvironment], rbx; lpEnvironment
0x180021612  mov     dword ptr [rsp+310h+pszFormat], 20h ; ' '; dwCreationFlags
0x18002161a  mov     dword ptr [rsp+310h+dwFlags], ebx; bInheritHandles
0x18002161e  call    cs:__imp_CreateProcessA
0x180021624  test    eax, eax
0x180021626  jz      short loc_180021640
0x180021628  mov     rcx, [rsp+310h+ProcessInformation.hThread]; hObject
0x18002162d  call    cs:__imp_CloseHandle
0x180021633  mov     rcx, [rsp+310h+ProcessInformation.hProcess]; hObject
0x180021638  call    cs:__imp_CloseHandle
0x18002163e  jmp     short loc_180021648
0x180021640  call    cs:__imp_GetLastError
0x180021646  mov     ebx, eax
0x180021648  mov     eax, ebx
0x18002164a  mov     rcx, [rbp+210h+var_10]
0x180021651  xor     rcx, rsp; StackCookie
0x180021654  call    __security_check_cookie
0x180021659  lea     r11, [rsp+310h+var_s0]
0x180021661  mov     rbx, [r11+10h]
0x180021665  mov     rdi, [r11+18h]
0x180021669  mov     rsp, r11
0x18002166c  pop     rbp
0x18002166d  retn
```
