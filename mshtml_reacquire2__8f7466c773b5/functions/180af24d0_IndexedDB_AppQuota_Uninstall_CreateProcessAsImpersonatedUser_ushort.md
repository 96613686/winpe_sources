# IndexedDB_AppQuota_Uninstall_CreateProcessAsImpersonatedUser(ushort *)

- ea: `0x180af24d0`
- end: `0x180af26f0`
- name: `?IndexedDB_AppQuota_Uninstall_CreateProcessAsImpersonatedUser@@YAJPEAG@Z`
- size: `544`
- prototype: `__int64 __fastcall(LPWSTR lpCommandLine)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180af2920`

## callees

- `0x180af24d0`
- `0x1810f6516`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180af24ed`
- `KERNEL32!GetCurrentThread` at `0x180af24ed`
- `KERNEL32!GetLastError` at `0x180af263a`
- `KERNEL32!GetLastError` at `0x180af2667`
- `KERNEL32!GetLastError` at `0x180af2694`
- `KERNEL32!GetLastError` at `0x180af26c1`
- `KERNEL32!GetLastError` at `0x180af263a`
- `KERNEL32!GetLastError` at `0x180af2667`
- `KERNEL32!GetLastError` at `0x180af2694`
- `KERNEL32!GetLastError` at `0x180af26c1`
- `KERNEL32!CloseHandle` at `0x180af2617`
- `KERNEL32!CloseHandle` at `0x180af262c`
- `KERNEL32!CloseHandle` at `0x180af2686`
- `KERNEL32!CloseHandle` at `0x180af26b3`
- `KERNEL32!CloseHandle` at `0x180af2617`
- `KERNEL32!CloseHandle` at `0x180af262c`
- `KERNEL32!CloseHandle` at `0x180af2686`
- `KERNEL32!CloseHandle` at `0x180af26b3`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenThreadToken` at `0x180af250b`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenThreadToken` at `0x180af250b`
- `api-ms-win-downlevel-advapi32-l1-1-0!DuplicateTokenEx` at `0x180af254a`
- `api-ms-win-downlevel-advapi32-l1-1-0!DuplicateTokenEx` at `0x180af254a`
- `api-ms-win-downlevel-advapi32-l1-1-0!CreateProcessAsUserW` at `0x180af25fc`
- `api-ms-win-downlevel-advapi32-l1-1-0!CreateProcessAsUserW` at `0x180af25fc`
- `USERENV!CreateEnvironmentBlock` at `0x180af2571`
- `USERENV!CreateEnvironmentBlock` at `0x180af2571`
- `USERENV!DestroyEnvironmentBlock` at `0x180af2659`
- `USERENV!DestroyEnvironmentBlock` at `0x180af2659`

## pseudocode

```c
__int64 __fastcall IndexedDB_AppQuota_Uninstall_CreateProcessAsImpersonatedUser(LPWSTR lpCommandLine)
{
  HANDLE CurrentThread; // rax
  unsigned int v3; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  signed int v6; // eax
  signed int v7; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-39h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-19h] BYREF
  HANDLE hToken; // [rsp+108h] [rbp+6Fh] BYREF
  LPVOID Environment; // [rsp+110h] [rbp+77h] BYREF
  void *TokenHandle; // [rsp+118h] [rbp+7Fh] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000000u, 1, &TokenHandle) )
  {
    hToken = 0;
    if ( DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityImpersonation, TokenPrimary, &hToken) )
    {
      Environment = 0;
      if ( CreateEnvironmentBlock(&Environment, hToken, 0) )
      {
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        memset_0(&StartupInfo, 0, sizeof(StartupInfo));
        StartupInfo.lpDesktop = L"winsta0\\default";
        StartupInfo.cb = 104;
        if ( CreateProcessAsUserW(
               hToken,
               0,
               lpCommandLine,
               0,
               0,
               0,
               0x400u,
               Environment,
               0,
               &StartupInfo,
               &ProcessInformation) )
        {
          v3 = 0;
          if ( ProcessInformation.hThread )
            CloseHandle(ProcessInformation.hThread);
          if ( ProcessInformation.hProcess )
            CloseHandle(ProcessInformation.hProcess);
        }
        else
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
        }
        DestroyEnvironmentBlock(Environment);
      }
      else
      {
        v5 = GetLastError();
        v3 = v5;
        if ( v5 > 0 )
          v3 = (unsigned __int16)v5 | 0x80070000;
      }
      CloseHandle(hToken);
    }
    else
    {
      v6 = GetLastError();
      v3 = v6;
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    v7 = GetLastError();
    v3 = v7;
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x180af24d0  mov     [rsp-8+arg_0], rbx
0x180af24d5  push    rbp
0x180af24d6  lea     rbp, [rsp-57h]
0x180af24db  sub     rsp, 0F0h
0x180af24e2  mov     rbx, rcx
0x180af24e5  mov     [rbp+57h+TokenHandle], 0
0x180af24ed  call    cs:__imp_GetCurrentThread
0x180af24f4  nop     dword ptr [rax+rax+00h]
0x180af24f9  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180af24fd  mov     edx, 2000000h; DesiredAccess
0x180af2502  mov     rcx, rax; ThreadHandle
0x180af2505  mov     r8d, 1; OpenAsSelf
0x180af250b  call    cs:__imp_OpenThreadToken
0x180af2512  nop     dword ptr [rax+rax+00h]
0x180af2517  test    eax, eax
0x180af2519  jz      loc_180AF26C1
0x180af251f  mov     rcx, [rbp+57h+TokenHandle]; hExistingToken
0x180af2523  lea     rax, [rbp+57h+hToken]
0x180af2527  mov     [rsp+0F0h+phNewToken], rax; phNewToken
0x180af252c  mov     r9d, 2; ImpersonationLevel
0x180af2532  xor     r8d, r8d; lpTokenAttributes
0x180af2535  mov     [rsp+0F0h+TokenType], 1; TokenType
0x180af253d  mov     edx, 2000000h; dwDesiredAccess
0x180af2542  mov     [rbp+57h+hToken], 0
0x180af254a  call    cs:__imp_DuplicateTokenEx
0x180af2551  nop     dword ptr [rax+rax+00h]
0x180af2556  test    eax, eax
0x180af2558  jz      loc_180AF2694
0x180af255e  mov     rdx, [rbp+57h+hToken]; hToken
0x180af2562  lea     rcx, [rbp+57h+Environment]; lpEnvironment
0x180af2566  xor     r8d, r8d; bInherit
0x180af2569  mov     [rbp+57h+Environment], 0
0x180af2571  call    cs:__imp_CreateEnvironmentBlock
0x180af2578  nop     dword ptr [rax+rax+00h]
0x180af257d  test    eax, eax
0x180af257f  jz      loc_180AF2667
0x180af2585  xor     eax, eax
0x180af2587  lea     rcx, [rbp+57h+StartupInfo]; void *
0x180af258b  xorps   xmm0, xmm0
0x180af258e  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x180af2592  xor     edx, edx; Val
0x180af2594  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x180af2598  lea     r8d, [rax+68h]; Size
0x180af259c  call    memset_0
0x180af25a1  mov     rcx, [rbp+57h+hToken]; hToken
0x180af25a5  lea     rax, aWinsta0Default; "winsta0\\default"
0x180af25ac  mov     [rbp+57h+StartupInfo.lpDesktop], rax
0x180af25b0  xor     r9d, r9d; lpProcessAttributes
0x180af25b3  lea     rax, [rbp+57h+ProcessInformation]
0x180af25b7  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x180af25be  mov     [rsp+0F0h+lpProcessInformation], rax; lpProcessInformation
0x180af25c3  mov     r8, rbx; lpCommandLine
0x180af25c6  lea     rax, [rbp+57h+StartupInfo]
0x180af25ca  xor     edx, edx; lpApplicationName
0x180af25cc  mov     [rsp+0F0h+lpStartupInfo], rax; lpStartupInfo
0x180af25d1  mov     rax, [rbp+57h+Environment]
0x180af25d5  mov     [rsp+0F0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180af25de  mov     [rsp+0F0h+lpEnvironment], rax; lpEnvironment
0x180af25e3  mov     [rsp+0F0h+dwCreationFlags], 400h; dwCreationFlags
0x180af25eb  mov     dword ptr [rsp+0F0h+phNewToken], 0; bInheritHandles
0x180af25f3  mov     qword ptr [rsp+0F0h+TokenType], 0; lpThreadAttributes
0x180af25fc  call    cs:__imp_CreateProcessAsUserW
0x180af2603  nop     dword ptr [rax+rax+00h]
0x180af2608  test    eax, eax
0x180af260a  jz      short loc_180AF263A
0x180af260c  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x180af2610  xor     ebx, ebx
0x180af2612  test    rcx, rcx
0x180af2615  jz      short loc_180AF2623
0x180af2617  call    cs:__imp_CloseHandle
0x180af261e  nop     dword ptr [rax+rax+00h]
0x180af2623  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x180af2627  test    rcx, rcx
0x180af262a  jz      short loc_180AF2655
0x180af262c  call    cs:__imp_CloseHandle
0x180af2633  nop     dword ptr [rax+rax+00h]
0x180af2638  jmp     short loc_180AF2655
0x180af263a  call    cs:__imp_GetLastError
0x180af2641  nop     dword ptr [rax+rax+00h]
0x180af2646  mov     ebx, eax
0x180af2648  test    eax, eax
0x180af264a  jle     short loc_180AF2655
0x180af264c  movzx   ebx, ax
0x180af264f  or      ebx, 80070000h
0x180af2655  mov     rcx, [rbp+57h+Environment]; lpEnvironment
0x180af2659  call    cs:__imp_DestroyEnvironmentBlock
0x180af2660  nop     dword ptr [rax+rax+00h]
0x180af2665  jmp     short loc_180AF2682
0x180af2667  call    cs:__imp_GetLastError
0x180af266e  nop     dword ptr [rax+rax+00h]
0x180af2673  mov     ebx, eax
0x180af2675  test    eax, eax
0x180af2677  jle     short loc_180AF2682
0x180af2679  movzx   ebx, ax
0x180af267c  or      ebx, 80070000h
0x180af2682  mov     rcx, [rbp+57h+hToken]; hObject
0x180af2686  call    cs:__imp_CloseHandle
0x180af268d  nop     dword ptr [rax+rax+00h]
0x180af2692  jmp     short loc_180AF26AF
0x180af2694  call    cs:__imp_GetLastError
0x180af269b  nop     dword ptr [rax+rax+00h]
0x180af26a0  mov     ebx, eax
0x180af26a2  test    eax, eax
0x180af26a4  jle     short loc_180AF26AF
0x180af26a6  movzx   ebx, ax
0x180af26a9  or      ebx, 80070000h
0x180af26af  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180af26b3  call    cs:__imp_CloseHandle
0x180af26ba  nop     dword ptr [rax+rax+00h]
0x180af26bf  jmp     short loc_180AF26DC
0x180af26c1  call    cs:__imp_GetLastError
0x180af26c8  nop     dword ptr [rax+rax+00h]
0x180af26cd  mov     ebx, eax
0x180af26cf  test    eax, eax
0x180af26d1  jle     short loc_180AF26DC
0x180af26d3  movzx   ebx, ax
0x180af26d6  or      ebx, 80070000h
0x180af26dc  mov     eax, ebx
0x180af26de  mov     rbx, [rsp+0F0h+arg_0]
0x180af26e6  add     rsp, 0F0h
0x180af26ed  pop     rbp
0x180af26ee  retn
```
