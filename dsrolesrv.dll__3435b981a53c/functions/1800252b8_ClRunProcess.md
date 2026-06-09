# ClRunProcess

- ea: `0x1800252b8`
- end: `0x18002547d`
- name: `ClRunProcess`
- size: `453`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012460`

## callees

- `0x18002527c`
- `0x1800252b8`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800253e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800253e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025434`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025449`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002545a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c6eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c6fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025449`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002545a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c6eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c6fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800253ce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800253ce`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180025387`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180025387`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002542a`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002542a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180025330`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180025330`

## string_xrefs

- `0x180025329`: `%SystemRoot%\system32\rundll32.exe %SystemRoot%\system32\DsRoleSrv.dll,DsRolepRunSysprepProvidersForCloning`
- `0x1800253a6`: `CreateProcessW Failed to run: CommandLine: '%ws' WStatus: %d\n`
- `0x180025410`: `Waiting for RunDLL32.exe to terminate, process ID %d\n`

## pseudocode

```c
__int64 ClRunProcess()
{
  int v0; // ebx
  DWORD v1; // eax
  DWORD ExitCode; // [rsp+50h] [rbp-8C8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-8C0h] BYREF
  int v5; // [rsp+70h] [rbp-8A8h]
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-898h] BYREF
  WCHAR Dst[1032]; // [rsp+F0h] [rbp-828h] BYREF

  ExitCode = 0;
  v0 = 30;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  *(_QWORD *)&ProcessInformation.dwProcessId = 0;
  *(__m128i *)&ProcessInformation.hProcess = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  StartupInfo.cb = 104;
  if ( !ExpandEnvironmentStringsW(
          L"%SystemRoot%\\system32\\rundll32.exe %SystemRoot%\\system32\\DsRoleSrv.dll,DsRolepRunSysprepProvidersForCloning",
          Dst,
          0x401u) )
    goto LABEL_13;
  if ( !CreateProcessW(0, Dst, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    ExitCode = GetLastError();
    ClLogPrint(2, L"CreateProcessW Failed to run: CommandLine: '%ws' WStatus: %d\n", Dst, ExitCode);
    goto LABEL_14;
  }
  while ( 1 )
  {
    v5 = --v0;
    if ( v0 <= 0 )
      break;
    v1 = WaitForSingleObject(ProcessInformation.hProcess, 0xEA60u);
    ExitCode = v1;
    if ( !v1 )
    {
      ExitCode = 0;
      goto LABEL_12;
    }
    if ( v1 == -1 )
    {
      ExitCode = GetLastError();
      break;
    }
    ClLogPrint(0, L"Waiting for RunDLL32.exe to terminate, process ID %d\n", ProcessInformation.dwProcessId);
  }
  if ( ExitCode )
  {
    ClLogPrint(0, L"Failed to wait for the processs: %d\n");
    goto LABEL_14;
  }
LABEL_12:
  if ( !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
LABEL_13:
    ExitCode = GetLastError();
LABEL_14:
  if ( ProcessInformation.hThread != (HANDLE)-1LL )
    CloseHandle(ProcessInformation.hThread);
  if ( ProcessInformation.hProcess != (HANDLE)-1LL )
    CloseHandle(ProcessInformation.hProcess);
  return ExitCode;
}

```

## disassembly

```asm
0x1800252b8  push    rbx
0x1800252ba  sub     rsp, 910h
0x1800252c1  mov     rax, cs:__security_cookie
0x1800252c8  xor     rax, rsp
0x1800252cb  mov     [rsp+918h+var_18], rax
0x1800252d3  mov     [rsp+918h+ExitCode], 0
0x1800252db  mov     ebx, 1Eh
0x1800252e0  xor     edx, edx; Val
0x1800252e2  lea     r8d, [rbx+4Ah]; Size
0x1800252e6  lea     rcx, [rsp+918h+StartupInfo]; void *
0x1800252ee  call    memset_0
0x1800252f3  xorps   xmm0, xmm0
0x1800252f6  xor     eax, eax
0x1800252f8  movups  xmmword ptr [rsp+918h+ProcessInformation.hProcess], xmm0
0x1800252fd  mov     qword ptr [rsp+918h+ProcessInformation.dwProcessId], rax
0x180025302  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18002530a  movdqu  xmmword ptr [rsp+918h+ProcessInformation.hProcess], xmm0
0x180025310  mov     [rsp+918h+StartupInfo.cb], 68h ; 'h'
0x18002531b  mov     r8d, 401h; nSize
0x180025321  lea     rdx, [rsp+918h+Dst]; lpDst
0x180025329  lea     rcx, aSystemrootSyst_1; "%SystemRoot%\\system32\\rundll32.exe %S"...
0x180025330  call    cs:__imp_ExpandEnvironmentStringsW
0x180025336  test    eax, eax
0x180025338  jz      loc_180025434
0x18002533e  lea     rax, [rsp+918h+ProcessInformation]
0x180025343  mov     [rsp+918h+lpProcessInformation], rax; lpProcessInformation
0x180025348  lea     rax, [rsp+918h+StartupInfo]
0x180025350  mov     [rsp+918h+lpStartupInfo], rax; lpStartupInfo
0x180025355  mov     [rsp+918h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18002535e  mov     [rsp+918h+lpEnvironment], 0; lpEnvironment
0x180025367  mov     [rsp+918h+dwCreationFlags], 0; dwCreationFlags
0x18002536f  mov     [rsp+918h+bInheritHandles], 0; bInheritHandles
0x180025377  xor     r9d, r9d; lpThreadAttributes
0x18002537a  xor     r8d, r8d; lpProcessAttributes
0x18002537d  lea     rdx, [rsp+918h+Dst]; lpCommandLine
0x180025385  xor     ecx, ecx; lpApplicationName
0x180025387  call    cs:__imp_CreateProcessW
0x18002538d  test    eax, eax
0x18002538f  jnz     short loc_1800253BA
0x180025391  call    cs:__imp_GetLastError
0x180025397  mov     [rsp+918h+ExitCode], eax
0x18002539b  mov     r9d, eax
0x18002539e  lea     r8, [rsp+918h+Dst]
0x1800253a6  lea     rdx, aCreateprocessw; "CreateProcessW Failed to run: CommandLi"...
0x1800253ad  lea     ecx, [rbx-1Ch]
0x1800253b0  call    ClLogPrint
0x1800253b5  jmp     loc_18002543E
0x1800253ba  dec     ebx
0x1800253bc  mov     [rsp+918h+var_8A8], ebx
0x1800253c0  test    ebx, ebx
0x1800253c2  jle     short loc_1800253F1
0x1800253c4  mov     edx, 0EA60h; dwMilliseconds
0x1800253c9  mov     rcx, [rsp+918h+ProcessInformation.hProcess]; hHandle
0x1800253ce  call    cs:__imp_WaitForSingleObject
0x1800253d4  mov     [rsp+918h+ExitCode], eax
0x1800253d8  test    eax, eax
0x1800253da  jnz     short loc_1800253E2
0x1800253dc  mov     [rsp+918h+ExitCode], eax
0x1800253e0  jmp     short loc_180025420
0x1800253e2  cmp     eax, 0FFFFFFFFh
0x1800253e5  jnz     short loc_18002540B
0x1800253e7  call    cs:__imp_GetLastError
0x1800253ed  mov     [rsp+918h+ExitCode], eax
0x1800253f1  mov     r8d, [rsp+918h+ExitCode]
0x1800253f6  test    r8d, r8d
0x1800253f9  jz      short loc_180025420
0x1800253fb  lea     rdx, aFailedToWaitFo; "Failed to wait for the processs: %d\n"
0x180025402  xor     ecx, ecx
0x180025404  call    ClLogPrint
0x180025409  jmp     short loc_18002543E
0x18002540b  mov     r8d, [rsp+918h+ProcessInformation.dwProcessId]
0x180025410  lea     rdx, aWaitingForRund; "Waiting for RunDLL32.exe to terminate, "...
0x180025417  xor     ecx, ecx
0x180025419  call    ClLogPrint
0x18002541e  jmp     short loc_1800253BA
0x180025420  lea     rdx, [rsp+918h+ExitCode]; lpExitCode
0x180025425  mov     rcx, [rsp+918h+ProcessInformation.hProcess]; hProcess
0x18002542a  call    cs:__imp_GetExitCodeProcess
0x180025430  test    eax, eax
0x180025432  jnz     short loc_18002543E
0x180025434  call    cs:__imp_GetLastError
0x18002543a  mov     [rsp+918h+ExitCode], eax
0x18002543e  mov     rcx, [rsp+918h+ProcessInformation.hThread]; hObject
0x180025443  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180025447  jz      short loc_18002544F
0x180025449  call    cs:__imp_CloseHandle
0x18002544f  mov     rcx, [rsp+918h+ProcessInformation.hProcess]; hObject
0x180025454  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180025458  jz      short loc_180025460
0x18002545a  call    cs:__imp_CloseHandle
0x180025460  mov     eax, [rsp+918h+ExitCode]
0x180025464  mov     rcx, [rsp+918h+var_18]
0x18002546c  xor     rcx, rsp; StackCookie
0x18002546f  call    __security_check_cookie
0x180025474  add     rsp, 910h
0x18002547b  pop     rbx
0x18002547c  retn
0x18002c6d8  push    rbp
0x18002c6da  sub     rsp, 50h
0x18002c6de  mov     rbp, rdx
0x18002c6e1  mov     rcx, [rbp+60h]; hObject
0x18002c6e5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002c6e9  jz      short loc_18002C6F2
0x18002c6eb  call    cs:__imp_CloseHandle
0x18002c6f1  nop
0x18002c6f2  mov     rcx, [rbp+58h]; hObject
0x18002c6f6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002c6fa  jz      short loc_18002C703
0x18002c6fc  call    cs:__imp_CloseHandle
0x18002c702  nop
0x18002c703  add     rsp, 50h
0x18002c707  pop     rbp
0x18002c708  retn
```
