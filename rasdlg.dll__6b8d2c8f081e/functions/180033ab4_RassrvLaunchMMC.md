# RassrvLaunchMMC

- ea: `0x180033ab4`
- end: `0x180033c87`
- name: `RassrvLaunchMMC`
- size: `467`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003039c`
- `0x18003218c`
- `0x1800328bc`

## callees

- `0x180033ab4`
- `0x180034194`
- `0x180034260`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033c59`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessA` at `0x180033c37`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessA` at `0x180033c37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033c46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033c51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033c46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033c51`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180033b7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180033b7d`
- `rtutils!TracePrintfExA` at `0x180033bde`
- `rtutils!TracePrintfExA` at `0x180033bde`

## string_xrefs

- `0x180033b1a`: `compmgmt.msc`
- `0x180033b61`: `RassrvLaunchMMC: StringCchCopyExA failed. hr = 0x%x`

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
  v7 = StringCchCopyExA(pszDest, 0x105u, "mmc.exe", v2, 0, pszFormat);
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
0x180033ab4  mov     [rsp-8+arg_0], rbx
0x180033ab9  mov     [rsp-8+arg_8], rdi
0x180033abe  push    rbp
0x180033abf  lea     rbp, [rsp-210h]
0x180033ac7  sub     rsp, 310h
0x180033ace  mov     rax, cs:__security_cookie
0x180033ad5  xor     rax, rsp
0x180033ad8  mov     [rbp+210h+var_10], rax
0x180033adf  xor     eax, eax
0x180033ae1  mov     ebx, ecx
0x180033ae3  xor     edx, edx; Val
0x180033ae5  mov     dword ptr [rsp+310h+StartupInfo+4], eax
0x180033ae9  lea     rcx, [rsp+310h+StartupInfo]; void *
0x180033aee  lea     r8d, [rax+64h]; Size
0x180033af2  call    memset_0
0x180033af7  xor     eax, eax
0x180033af9  xorps   xmm0, xmm0
0x180033afc  mov     qword ptr [rsp+310h+ProcessInformation.dwProcessId], rax
0x180033b01  movups  xmmword ptr [rsp+310h+ProcessInformation.hProcess], xmm0
0x180033b06  sub     ebx, 1
0x180033b09  jz      short loc_180033B6A
0x180033b0b  sub     ebx, 1
0x180033b0e  jz      short loc_180033B2C
0x180033b10  sub     ebx, 1
0x180033b13  jz      short loc_180033B23
0x180033b15  cmp     ebx, 1
0x180033b18  jnz     short loc_180033B23
0x180033b1a  lea     rbx, aCompmgmtMsc; "compmgmt.msc"
0x180033b21  jmp     short loc_180033B71
0x180033b23  lea     rbx, aRrasmgmtMsc; "rrasmgmt.msc"
0x180033b2a  jmp     short loc_180033B71
0x180033b2c  xor     ebx, ebx
0x180033b2e  lea     r8, aMmcExe; "mmc.exe"
0x180033b35  mov     edx, 105h; cchDest
0x180033b3a  mov     [rsp+310h+pcchRemaining], rbx; pcchRemaining
0x180033b3f  lea     rcx, [rbp+210h+pszDest]; pszDest
0x180033b43  call    StringCchCopyExA
0x180033b48  mov     edi, eax
0x180033b4a  test    eax, eax
0x180033b4c  jns     loc_180033BE9
0x180033b52  mov     ecx, cs:g_dwTraceId
0x180033b58  cmp     ecx, 0FFFFFFFFh
0x180033b5b  jz      loc_180033BE4
0x180033b61  lea     r8, aRassrvlaunchmm; "RassrvLaunchMMC: StringCchCopyExA faile"...
0x180033b68  jmp     short loc_180033BD6
0x180033b6a  lea     rbx, aNetmgmtMsc; "netmgmt.msc"
0x180033b71  mov     edx, 105h; uSize
0x180033b76  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x180033b7d  call    cs:__imp_GetSystemDirectoryA
0x180033b83  mov     [rsp+310h+lpCurrentDirectory], rbx
0x180033b88  lea     rax, [rbp+210h+Buffer]
0x180033b8f  mov     [rsp+310h+lpEnvironment], rax
0x180033b94  lea     rcx, [rbp+210h+pszDest]; pszDest
0x180033b98  lea     rax, aMmcSS; "mmc %s\\%s"
0x180033b9f  xor     r9d, r9d; pcchRemaining
0x180033ba2  mov     [rsp+310h+pszFormat], rax; pszFormat
0x180033ba7  xor     r8d, r8d; ppszDestEnd
0x180033baa  mov     edx, 105h; cchDest
0x180033baf  mov     dword ptr [rsp+310h+pcchRemaining], 100h; dwFlags
0x180033bb7  call    StringCchPrintfExA
0x180033bbc  xor     ebx, ebx
0x180033bbe  mov     edi, eax
0x180033bc0  test    eax, eax
0x180033bc2  jns     short loc_180033BE9
0x180033bc4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180033bca  cmp     ecx, 0FFFFFFFFh
0x180033bcd  jz      short loc_180033BE4
0x180033bcf  lea     r8, aRassrvlaunchmm_0; "RassrvLaunchMMC: StringCchPrintfExA fai"...
0x180033bd6  mov     r9d, edi
0x180033bd9  mov     edx, 0Ch; dwFlags
0x180033bde  call    cs:__imp_TracePrintfExA
0x180033be4  movzx   ebx, di
0x180033be7  jmp     short loc_180033C61
0x180033be9  xor     edx, edx; Val
0x180033beb  lea     rcx, [rsp+310h+StartupInfo+4]; void *
0x180033bf0  lea     r8d, [rdx+64h]; Size
0x180033bf4  call    memset_0
0x180033bf9  lea     rax, [rsp+310h+ProcessInformation]
0x180033bfe  mov     [rsp+310h+StartupInfo.cb], 68h ; 'h'
0x180033c06  mov     [rsp+310h+lpProcessInformation], rax; lpProcessInformation
0x180033c0b  lea     rdx, [rbp+210h+pszDest]; lpCommandLine
0x180033c0f  lea     rax, [rsp+310h+StartupInfo]
0x180033c14  xor     r9d, r9d; lpThreadAttributes
0x180033c17  mov     [rsp+310h+lpStartupInfo], rax; lpStartupInfo
0x180033c1c  xor     r8d, r8d; lpProcessAttributes
0x180033c1f  mov     [rsp+310h+lpCurrentDirectory], rbx; lpCurrentDirectory
0x180033c24  xor     ecx, ecx; lpApplicationName
0x180033c26  mov     [rsp+310h+lpEnvironment], rbx; lpEnvironment
0x180033c2b  mov     dword ptr [rsp+310h+pszFormat], 20h ; ' '; dwCreationFlags
0x180033c33  mov     dword ptr [rsp+310h+pcchRemaining], ebx; bInheritHandles
0x180033c37  call    cs:__imp_CreateProcessA
0x180033c3d  test    eax, eax
0x180033c3f  jz      short loc_180033C59
0x180033c41  mov     rcx, [rsp+310h+ProcessInformation.hThread]; hObject
0x180033c46  call    cs:__imp_CloseHandle
0x180033c4c  mov     rcx, [rsp+310h+ProcessInformation.hProcess]; hObject
0x180033c51  call    cs:__imp_CloseHandle
0x180033c57  jmp     short loc_180033C61
0x180033c59  call    cs:__imp_GetLastError
0x180033c5f  mov     ebx, eax
0x180033c61  mov     eax, ebx
0x180033c63  mov     rcx, [rbp+210h+var_10]
0x180033c6a  xor     rcx, rsp; StackCookie
0x180033c6d  call    __security_check_cookie
0x180033c72  lea     r11, [rsp+310h+var_s0]
0x180033c7a  mov     rbx, [r11+10h]
0x180033c7e  mov     rdi, [r11+18h]
0x180033c82  mov     rsp, r11
0x180033c85  pop     rbp
0x180033c86  retn
```
