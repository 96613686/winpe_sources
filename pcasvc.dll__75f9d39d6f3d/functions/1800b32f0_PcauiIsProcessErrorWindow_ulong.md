# PcauiIsProcessErrorWindow(ulong)

- ea: `0x1800b32f0`
- end: `0x1800b350f`
- name: `?PcauiIsProcessErrorWindow@@YAHK@Z`
- size: `543`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c1f20`
- `0x1800e0044`

## callees

- `0x18000dc08`
- `0x180012920`
- `0x18003859c`
- `0x18007a9cf`
- `0x1800b32f0`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlGetNtSystemRoot` at `0x1800b3357`
- `ntdll!RtlGetNtSystemRoot` at `0x1800b3357`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b3450`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b3450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3431`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800b3427`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800b3427`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800b3464`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800b3464`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b34bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b34cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b34dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b34bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b34cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b34dc`

## string_xrefs

- `0x1800b3494`: `GetUserToken failed 0x%x`
- `0x1800b335d`: `%ls\System32\pcaui.exe -c %d`
- `0x1800b337d`: `Failed to format pcaui command 0x%x`
- `0x1800b33af`: `Running pcaui command [%ws]`

## pseudocode

```c
_BOOL8 __fastcall PcauiIsProcessErrorWindow(int a1)
{
  __int64 v2; // rcx
  __int64 NtSystemRoot; // rax
  const char *v4; // r9
  int v5; // r8d
  int v6; // ecx
  DWORD ExitCode; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hToken; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  WCHAR CommandLine[520]; // [rsp+100h] [rbp+0h] BYREF

  hToken = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(CommandLine, 0, sizeof(CommandLine));
  ExitCode = 0;
  NtSystemRoot = RtlGetNtSystemRoot(v2);
  if ( StringCchPrintfW(CommandLine, 0x208u, L"%ls\\System32\\pcaui.exe -c %d", NtSystemRoot, a1) < 0 )
  {
    v4 = "Failed to format pcaui command 0x%x";
    v5 = 335;
LABEL_12:
    v6 = 1;
    goto LABEL_13;
  }
  AslLogCallPrintf(3, (unsigned int)"PcauiIsProcessErrorWindow", 339, (unsigned int)"Running pcaui command [%ws]");
  if ( (int)GetUserToken(&hToken) < 0 || !hToken )
  {
    v4 = "GetUserToken failed 0x%x";
    v5 = 344;
    goto LABEL_12;
  }
  if ( !CreateProcessAsUserW(hToken, 0, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    GetLastError();
    v4 = "Could not launch process %d";
    v5 = 361;
    goto LABEL_12;
  }
  if ( WaitForSingleObject(ProcessInformation.hProcess, 0x2710u) )
  {
    v4 = "Failed to wait for pcaui exit code [%d]";
    v5 = 373;
  }
  else
  {
    GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode);
    v4 = "Got pcaui exit code [%d]";
    v5 = 369;
  }
  v6 = 3;
LABEL_13:
  AslLogCallPrintf(v6, (unsigned int)"PcauiIsProcessErrorWindow", v5, (_DWORD)v4);
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( hToken )
    CloseHandle(hToken);
  return ExitCode == 1408;
}

```

## disassembly

```asm
0x1800b32f0  mov     [rsp-8+arg_8], rbx
0x1800b32f5  push    rbp
0x1800b32f6  lea     rbp, [rsp-420h]
0x1800b32fe  sub     rsp, 520h
0x1800b3305  mov     rax, cs:__security_cookie
0x1800b330c  xor     rax, rsp
0x1800b330f  mov     [rbp+420h+var_10], rax
0x1800b3316  xor     edx, edx; Val
0x1800b3318  mov     [rsp+520h+hToken], 0
0x1800b3321  mov     ebx, ecx
0x1800b3323  lea     rcx, [rbp+420h+StartupInfo]; void *
0x1800b3327  lea     r8d, [rdx+68h]; Size
0x1800b332b  call    memset_0
0x1800b3330  xorps   xmm0, xmm0
0x1800b3333  lea     rcx, [rbp+420h+CommandLine]; void *
0x1800b3337  xor     eax, eax
0x1800b3339  xor     edx, edx; Val
0x1800b333b  mov     r8d, 410h; Size
0x1800b3341  mov     qword ptr [rbp+420h+ProcessInformation.dwProcessId], rax
0x1800b3345  movups  xmmword ptr [rsp+520h+ProcessInformation.hProcess], xmm0
0x1800b334a  call    memset_0
0x1800b334f  mov     [rsp+520h+ExitCode], 0
0x1800b3357  call    cs:__imp_RtlGetNtSystemRoot
0x1800b335d  lea     r8, aLsSystem32Pcau_0; "%ls\\System32\\pcaui.exe -c %d"
0x1800b3364  mov     dword ptr [rsp+520h+lpThreadAttributes], ebx
0x1800b3368  mov     r9, rax
0x1800b336b  lea     rcx, [rbp+420h+CommandLine]; unsigned __int16 *
0x1800b336f  mov     edx, 208h; unsigned __int64
0x1800b3374  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b3379  test    eax, eax
0x1800b337b  jns     short loc_1800B3396
0x1800b337d  lea     r9, aFailedToFormat_1; "Failed to format pcaui command 0x%x"
0x1800b3384  mov     r8d, 14Fh
0x1800b338a  lea     rdx, aPcauiisprocess; "PcauiIsProcessErrorWindow"
0x1800b3391  jmp     loc_1800B34A4
0x1800b3396  lea     rax, [rbp+420h+CommandLine]
0x1800b339a  mov     r8d, 153h
0x1800b33a0  lea     rbx, aPcauiisprocess; "PcauiIsProcessErrorWindow"
0x1800b33a7  mov     [rsp+520h+lpThreadAttributes], rax
0x1800b33ac  mov     rdx, rbx
0x1800b33af  lea     r9, aRunningPcauiCo; "Running pcaui command [%ws]"
0x1800b33b6  mov     ecx, 3
0x1800b33bb  call    AslLogCallPrintf
0x1800b33c0  lea     rcx, [rsp+520h+hToken]; phToken
0x1800b33c5  call    ?GetUserToken@@YAJAEAPEAX@Z; GetUserToken(void * &)
0x1800b33ca  test    eax, eax
0x1800b33cc  js      loc_1800B3494
0x1800b33d2  mov     rcx, [rsp+520h+hToken]; hToken
0x1800b33d7  test    rcx, rcx
0x1800b33da  jz      loc_1800B3494
0x1800b33e0  lea     rax, [rsp+520h+ProcessInformation]
0x1800b33e5  xor     r9d, r9d; lpProcessAttributes
0x1800b33e8  mov     [rsp+520h+lpProcessInformation], rax; lpProcessInformation
0x1800b33ed  lea     r8, [rbp+420h+CommandLine]; lpCommandLine
0x1800b33f1  lea     rax, [rbp+420h+StartupInfo]
0x1800b33f5  xor     edx, edx; lpApplicationName
0x1800b33f7  mov     [rsp+520h+lpStartupInfo], rax; lpStartupInfo
0x1800b33fc  mov     [rsp+520h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800b3405  mov     [rsp+520h+lpEnvironment], 0; lpEnvironment
0x1800b340e  mov     [rsp+520h+dwCreationFlags], 0; dwCreationFlags
0x1800b3416  mov     [rsp+520h+bInheritHandles], 0; bInheritHandles
0x1800b341e  mov     [rsp+520h+lpThreadAttributes], 0; lpThreadAttributes
0x1800b3427  call    cs:__imp_CreateProcessAsUserW
0x1800b342d  test    eax, eax
0x1800b342f  jnz     short loc_1800B3446
0x1800b3431  call    cs:__imp_GetLastError
0x1800b3437  lea     r9, aCouldNotLaunch; "Could not launch process %d"
0x1800b343e  mov     r8d, 169h
0x1800b3444  jmp     short loc_1800B34A1
0x1800b3446  mov     rcx, [rsp+520h+ProcessInformation.hProcess]; hHandle
0x1800b344b  mov     edx, 2710h; dwMilliseconds
0x1800b3450  call    cs:__imp_WaitForSingleObject
0x1800b3456  test    eax, eax
0x1800b3458  jnz     short loc_1800B3485
0x1800b345a  mov     rcx, [rsp+520h+ProcessInformation.hProcess]; hProcess
0x1800b345f  lea     rdx, [rsp+520h+ExitCode]; lpExitCode
0x1800b3464  call    cs:__imp_GetExitCodeProcess
0x1800b346a  mov     eax, [rsp+520h+ExitCode]
0x1800b346e  lea     r9, aGotPcauiExitCo; "Got pcaui exit code [%d]"
0x1800b3475  mov     r8d, 171h
0x1800b347b  mov     rdx, rbx
0x1800b347e  mov     ecx, 3
0x1800b3483  jmp     short loc_1800B34A9
0x1800b3485  lea     r9, aFailedToWaitFo_1; "Failed to wait for pcaui exit code [%d]"
0x1800b348c  mov     r8d, 175h
0x1800b3492  jmp     short loc_1800B347B
0x1800b3494  lea     r9, aGetusertokenFa; "GetUserToken failed 0x%x"
0x1800b349b  mov     r8d, 158h
0x1800b34a1  mov     rdx, rbx
0x1800b34a4  mov     ecx, 1
0x1800b34a9  mov     dword ptr [rsp+520h+lpThreadAttributes], eax
0x1800b34ad  call    AslLogCallPrintf
0x1800b34b2  mov     rcx, [rsp+520h+ProcessInformation.hProcess]; hObject
0x1800b34b7  test    rcx, rcx
0x1800b34ba  jz      short loc_1800B34C2
0x1800b34bc  call    cs:__imp_CloseHandle
0x1800b34c2  mov     rcx, [rsp+520h+ProcessInformation.hThread]; hObject
0x1800b34c7  test    rcx, rcx
0x1800b34ca  jz      short loc_1800B34D2
0x1800b34cc  call    cs:__imp_CloseHandle
0x1800b34d2  mov     rcx, [rsp+520h+hToken]; hObject
0x1800b34d7  test    rcx, rcx
0x1800b34da  jz      short loc_1800B34E2
0x1800b34dc  call    cs:__imp_CloseHandle
0x1800b34e2  xor     eax, eax
0x1800b34e4  cmp     [rsp+520h+ExitCode], 580h
0x1800b34ec  setz    al
0x1800b34ef  mov     rcx, [rbp+420h+var_10]
0x1800b34f6  xor     rcx, rsp; StackCookie
0x1800b34f9  call    __security_check_cookie
0x1800b34fe  mov     rbx, [rsp+520h+arg_8]
0x1800b3506  add     rsp, 520h
0x1800b350d  pop     rbp
0x1800b350e  retn
```
