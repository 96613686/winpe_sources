# _ShellExecuteRegAppWithJobObject(ushort const *,RRA_FLAGS,IUnknown *)

- ea: `0x1401b1e1c`
- end: `0x1401b2141`
- name: `?_ShellExecuteRegAppWithJobObject@@YAJPEBGW4RRA_FLAGS@@PEAUIUnknown@@@Z`
- size: `805`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000c8cc`

## callees

- `0x14000b9e0`
- `0x14000ba70`
- `0x14000d230`
- `0x14001c330`
- `0x140020580`
- `0x140087d20`
- `0x14010e160`
- `0x14010ed90`
- `0x1401b1d98`
- `0x1401b1e1c`

## import_xrefs

- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x1401b1e5a`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x1401b1e5a`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x1401b1fa4`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x1401b1fa4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1401b2040`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1401b207d`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1401b2040`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1401b207d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1401b20d6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1401b20d6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1401b20aa`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1401b20aa`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1401b1f7d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1401b1f7d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1401b2018`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1401b2018`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b205b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b206a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b20e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b20f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b2107`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b205b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b206a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b20e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b20f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b2107`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1401b1e86`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1401b1e86`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1401b1ecf`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1401b1ecf`

## string_xrefs

- `0x1401b1ebf`: `RunDLL32.EXE`
- `0x1401b1eee`: `RunDLL32.EXE Shell32.DLL,ShellExec_RunDLL ?0x%X?%s`

## pseudocode

```c
__int64 __fastcall _ShellExecuteRegAppWithJobObject(__int64 a1, char a2, __int64 a3)
{
  HANDLE JobObjectW; // r14
  int Error; // ebx
  __int64 v8; // rcx
  UINT SystemDirectoryW; // esi
  void *v10; // rdi
  HANDLE v11; // rsi
  HWND v12; // rcx
  DWORD ProcessId; // eax
  __int64 v14; // rcx
  DWORD ThreadId; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR CommandLine[520]; // [rsp+2F0h] [rbp+1F0h] BYREF

  JobObjectW = CreateJobObjectW(0, 0);
  if ( JobObjectW || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
    if ( (byte_14024FCC1 & 0x20) != 0 )
      McTemplateU0z_EventWriteTransfer(v8, ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Start, a1);
    Error = -2147467259;
    if ( SystemDirectoryW - 1 > 0x102 )
      goto LABEL_28;
    if ( PathCchAppend(Buffer, 0x104u, L"RunDLL32.EXE") < 0 )
      goto LABEL_28;
    if ( (int)StringCchPrintfW(CommandLine, 0x208u, L"RunDLL32.EXE Shell32.DLL,ShellExec_RunDLL ?0x%X?%s", 1024, a1) < 0 )
      goto LABEL_28;
    *(_QWORD *)&StartupInfo.cb = 104;
    memset_0(&StartupInfo.lpReserved, 0, 0x60u);
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( !CreateProcessW(Buffer, CommandLine, 0, 0, 0, 4u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_28;
    }
    if ( AssignProcessToJobObject(JobObjectW, ProcessInformation.hProcess) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_26:
        TerminateProcess(ProcessInformation.hProcess, 5u);
LABEL_27:
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(ProcessInformation.hThread);
LABEL_28:
        CloseHandle(JobObjectW);
        return (unsigned int)Error;
      }
    }
    if ( (a2 & 2) != 0 )
    {
      v10 = _SetJobCompletionPort(JobObjectW);
      if ( v10 || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        ThreadId = 0;
        v11 = CreateThread(0, 0, _JobObjectWaitingThreadProc, v10, 0, &ThreadId);
        if ( v11 )
        {
          Error = 0;
        }
        else
        {
          Error = ResultFromKnownLastError();
          if ( Error < 0 )
          {
LABEL_20:
            CloseHandle(v10);
            goto LABEL_23;
          }
        }
        ResumeThread(ProcessInformation.hThread);
        SHProcessMessagesUntilEvent(v12, v11, 0xFFFFFFFF);
        CloseHandle(v11);
        goto LABEL_20;
      }
    }
    else
    {
      ResumeThread(ProcessInformation.hThread);
      if ( (a2 & 0x40) != 0 )
        IUnknown_WaitForSteadyState(a3, ProcessInformation.hProcess);
    }
LABEL_23:
    if ( (byte_14024FCC1 & 0x20) != 0 )
    {
      ProcessId = GetProcessId(ProcessInformation.hProcess);
      McTemplateU0qz_EventWriteTransfer(v14, ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Stop, ProcessId, a1);
    }
    if ( Error >= 0 )
      goto LABEL_27;
    goto LABEL_26;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1401b1e1c  mov     [rsp-8+arg_8], rbx
0x1401b1e21  mov     [rsp-8+arg_18], rsi
0x1401b1e26  push    rbp
0x1401b1e27  push    rdi
0x1401b1e28  push    r12
0x1401b1e2a  push    r14
0x1401b1e2c  push    r15
0x1401b1e2e  lea     rbp, [rsp-610h]
0x1401b1e36  sub     rsp, 710h
0x1401b1e3d  mov     rax, cs:__security_cookie
0x1401b1e44  xor     rax, rsp
0x1401b1e47  mov     [rbp+630h+var_30], rax
0x1401b1e4e  mov     edi, edx
0x1401b1e50  mov     r15, rcx
0x1401b1e53  xor     edx, edx; lpName
0x1401b1e55  xor     ecx, ecx; lpJobAttributes
0x1401b1e57  mov     r12, r8
0x1401b1e5a  call    cs:__imp_CreateJobObjectW
0x1401b1e61  nop     dword ptr [rax+rax+00h]
0x1401b1e66  mov     r14, rax
0x1401b1e69  test    rax, rax
0x1401b1e6c  jnz     short loc_1401B1E7D
0x1401b1e6e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1401b1e73  mov     ebx, eax
0x1401b1e75  test    eax, eax
0x1401b1e77  js      loc_1401B2113
0x1401b1e7d  mov     edx, 104h; uSize
0x1401b1e82  lea     rcx, [rbp+630h+Buffer]; lpBuffer
0x1401b1e86  call    cs:__imp_GetSystemDirectoryW
0x1401b1e8d  nop     dword ptr [rax+rax+00h]
0x1401b1e92  test    cs:byte_14024FCC1, 20h
0x1401b1e99  mov     esi, eax
0x1401b1e9b  jz      short loc_1401B1EAC
0x1401b1e9d  mov     r8, r15
0x1401b1ea0  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Start
0x1401b1ea7  call    McTemplateU0z_EventWriteTransfer
0x1401b1eac  lea     eax, [rsi-1]
0x1401b1eaf  mov     ebx, 80004005h
0x1401b1eb4  cmp     eax, 102h
0x1401b1eb9  ja      loc_1401B2104
0x1401b1ebf  lea     r8, aRundll32Exe; "RunDLL32.EXE"
0x1401b1ec6  mov     edx, 104h; cchPath
0x1401b1ecb  lea     rcx, [rbp+630h+Buffer]; pszPath
0x1401b1ecf  call    cs:__imp_PathCchAppend
0x1401b1ed6  nop     dword ptr [rax+rax+00h]
0x1401b1edb  test    eax, eax
0x1401b1edd  js      loc_1401B2104
0x1401b1ee3  mov     r9d, 400h
0x1401b1ee9  mov     qword ptr [rsp+730h+bInheritHandles], r15
0x1401b1eee  lea     r8, aRundll32ExeShe; "RunDLL32.EXE Shell32.DLL,ShellExec_RunD"...
0x1401b1ef5  mov     edx, 208h; unsigned __int64
0x1401b1efa  lea     rcx, [rbp+630h+CommandLine]; unsigned __int16 *
0x1401b1f01  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401b1f06  test    eax, eax
0x1401b1f08  js      loc_1401B2104
0x1401b1f0e  xor     edx, edx; Val
0x1401b1f10  mov     qword ptr [rsp+730h+StartupInfo.cb], 68h ; 'h'
0x1401b1f19  lea     rcx, [rsp+730h+StartupInfo.lpReserved]; void *
0x1401b1f1e  lea     r8d, [rdx+60h]; Size
0x1401b1f22  call    memset_0
0x1401b1f27  xor     eax, eax
0x1401b1f29  lea     rdx, [rbp+630h+CommandLine]; lpCommandLine
0x1401b1f30  mov     qword ptr [rsp+730h+ProcessInformation.dwProcessId], rax
0x1401b1f35  lea     rcx, [rbp+630h+Buffer]; lpApplicationName
0x1401b1f39  lea     rax, [rsp+730h+ProcessInformation]
0x1401b1f3e  xorps   xmm0, xmm0
0x1401b1f41  mov     [rsp+730h+lpProcessInformation], rax; lpProcessInformation
0x1401b1f46  xor     r9d, r9d; lpThreadAttributes
0x1401b1f49  lea     rax, [rsp+730h+StartupInfo]
0x1401b1f4e  xor     r8d, r8d; lpProcessAttributes
0x1401b1f51  mov     [rsp+730h+lpStartupInfo], rax; lpStartupInfo
0x1401b1f56  mov     [rsp+730h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1401b1f5f  mov     [rsp+730h+lpEnvironment], 0; lpEnvironment
0x1401b1f68  mov     [rsp+730h+dwCreationFlags], 4; dwCreationFlags
0x1401b1f70  mov     [rsp+730h+bInheritHandles], 0; bInheritHandles
0x1401b1f78  movups  xmmword ptr [rsp+730h+ProcessInformation.hProcess], xmm0
0x1401b1f7d  call    cs:__imp_CreateProcessW
0x1401b1f84  nop     dword ptr [rax+rax+00h]
0x1401b1f89  test    eax, eax
0x1401b1f8b  jnz     short loc_1401B1F9C
0x1401b1f8d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1401b1f92  mov     ebx, eax
0x1401b1f94  test    eax, eax
0x1401b1f96  js      loc_1401B2104
0x1401b1f9c  mov     rdx, [rsp+730h+ProcessInformation.hProcess]; hProcess
0x1401b1fa1  mov     rcx, r14; hJob
0x1401b1fa4  call    cs:__imp_AssignProcessToJobObject
0x1401b1fab  nop     dword ptr [rax+rax+00h]
0x1401b1fb0  test    eax, eax
0x1401b1fb2  jz      short loc_1401B1FB8
0x1401b1fb4  xor     ebx, ebx
0x1401b1fb6  jmp     short loc_1401B1FC7
0x1401b1fb8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1401b1fbd  mov     ebx, eax
0x1401b1fbf  test    eax, eax
0x1401b1fc1  js      loc_1401B20CC
0x1401b1fc7  test    dil, 2
0x1401b1fcb  jz      loc_1401B2078
0x1401b1fd1  mov     rcx, r14; hJob
0x1401b1fd4  call    ?_SetJobCompletionPort@@YAPEAXPEAX@Z; _SetJobCompletionPort(void *)
0x1401b1fd9  mov     rdi, rax
0x1401b1fdc  test    rax, rax
0x1401b1fdf  jnz     short loc_1401B1FF0
0x1401b1fe1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1401b1fe6  mov     ebx, eax
0x1401b1fe8  test    eax, eax
0x1401b1fea  js      loc_1401B209C
0x1401b1ff0  lea     rax, [rsp+730h+ThreadId]
0x1401b1ff5  mov     [rsp+730h+ThreadId], 0
0x1401b1ffd  mov     qword ptr [rsp+730h+dwCreationFlags], rax; lpThreadId
0x1401b2002  lea     r8, ?_JobObjectWaitingThreadProc@@YAKPEAX@Z; lpStartAddress
0x1401b2009  mov     r9, rdi; lpParameter
0x1401b200c  mov     [rsp+730h+bInheritHandles], 0; dwCreationFlags
0x1401b2014  xor     edx, edx; dwStackSize
0x1401b2016  xor     ecx, ecx; lpThreadAttributes
0x1401b2018  call    cs:__imp_CreateThread
0x1401b201f  nop     dword ptr [rax+rax+00h]
0x1401b2024  mov     rsi, rax
0x1401b2027  test    rax, rax
0x1401b202a  jz      short loc_1401B2030
0x1401b202c  xor     ebx, ebx
0x1401b202e  jmp     short loc_1401B203B
0x1401b2030  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1401b2035  mov     ebx, eax
0x1401b2037  test    eax, eax
0x1401b2039  js      short loc_1401B2067
0x1401b203b  mov     rcx, [rsp+730h+ProcessInformation.hThread]; hThread
0x1401b2040  call    cs:__imp_ResumeThread
0x1401b2047  nop     dword ptr [rax+rax+00h]
0x1401b204c  or      r8d, 0FFFFFFFFh; unsigned int
0x1401b2050  mov     rdx, rsi; void *
0x1401b2053  call    ?SHProcessMessagesUntilEvent@@YAKPEAUHWND__@@PEAXK@Z; SHProcessMessagesUntilEvent(HWND__ *,void *,ulong)
0x1401b2058  mov     rcx, rsi; hObject
0x1401b205b  call    cs:__imp_CloseHandle
0x1401b2062  nop     dword ptr [rax+rax+00h]
0x1401b2067  mov     rcx, rdi; hObject
0x1401b206a  call    cs:__imp_CloseHandle
0x1401b2071  nop     dword ptr [rax+rax+00h]
0x1401b2076  jmp     short loc_1401B209C
0x1401b2078  mov     rcx, [rsp+730h+ProcessInformation.hThread]; hThread
0x1401b207d  call    cs:__imp_ResumeThread
0x1401b2084  nop     dword ptr [rax+rax+00h]
0x1401b2089  test    dil, 40h
0x1401b208d  jz      short loc_1401B209C
0x1401b208f  mov     rdx, [rsp+730h+ProcessInformation.hProcess]
0x1401b2094  mov     rcx, r12
0x1401b2097  call    IUnknown_WaitForSteadyState
0x1401b209c  test    cs:byte_14024FCC1, 20h
0x1401b20a3  jz      short loc_1401B20C8
0x1401b20a5  mov     rcx, [rsp+730h+ProcessInformation.hProcess]; Process
0x1401b20aa  call    cs:__imp_GetProcessId
0x1401b20b1  nop     dword ptr [rax+rax+00h]
0x1401b20b6  mov     r9, r15
0x1401b20b9  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Stop
0x1401b20c0  mov     r8d, eax
0x1401b20c3  call    McTemplateU0qz_EventWriteTransfer
0x1401b20c8  test    ebx, ebx
0x1401b20ca  jns     short loc_1401B20E2
0x1401b20cc  mov     rcx, [rsp+730h+ProcessInformation.hProcess]; hProcess
0x1401b20d1  mov     edx, 5; uExitCode
0x1401b20d6  call    cs:__imp_TerminateProcess
0x1401b20dd  nop     dword ptr [rax+rax+00h]
0x1401b20e2  mov     rcx, [rsp+730h+ProcessInformation.hProcess]; hObject
0x1401b20e7  call    cs:__imp_CloseHandle
0x1401b20ee  nop     dword ptr [rax+rax+00h]
0x1401b20f3  mov     rcx, [rsp+730h+ProcessInformation.hThread]; hObject
0x1401b20f8  call    cs:__imp_CloseHandle
0x1401b20ff  nop     dword ptr [rax+rax+00h]
0x1401b2104  mov     rcx, r14; hObject
0x1401b2107  call    cs:__imp_CloseHandle
0x1401b210e  nop     dword ptr [rax+rax+00h]
0x1401b2113  mov     eax, ebx
0x1401b2115  mov     rcx, [rbp+630h+var_30]
0x1401b211c  xor     rcx, rsp; StackCookie
0x1401b211f  call    __security_check_cookie
0x1401b2124  lea     r11, [rsp+730h+var_20]
0x1401b212c  mov     rbx, [r11+38h]
0x1401b2130  mov     rsi, [r11+48h]
0x1401b2134  mov     rsp, r11
0x1401b2137  pop     r15
0x1401b2139  pop     r14
0x1401b213b  pop     r12
0x1401b213d  pop     rdi
0x1401b213e  pop     rbp
0x1401b213f  retn
```
