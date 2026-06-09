# _ShellExecuteRegAppWithJobObject(ushort const *,RRA_FLAGS,IUnknown *)

- ea: `0x1401b39d4`
- end: `0x1401b3cdb`
- name: `?_ShellExecuteRegAppWithJobObject@@YAJPEBGW4RRA_FLAGS@@PEAUIUnknown@@@Z`
- size: `775`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000baf4`

## callees

- `0x14000c3a4`
- `0x14000d750`
- `0x14000d7e0`
- `0x1400158a4`
- `0x140016b10`
- `0x140081c20`
- `0x1401040e0`
- `0x140104ce0`
- `0x1401b39d4`

## import_xrefs

- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x1401b3a12`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x1401b3a12`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x1401b3ba3`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x1401b3ba3`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x1401b3b43`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x1401b3b43`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1401b3bef`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1401b3bef`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1401b3c63`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1401b3c63`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1401b3c89`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1401b3c89`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1401b3c11`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1401b3c3c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1401b3c11`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1401b3c3c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1401b3b22`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1401b3b22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b3bb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b3c26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b3c2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b3c94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b3c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b3ca8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b3bb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b3c26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b3c2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b3c94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b3c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b3ca8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1401b3a38`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1401b3a38`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1401b3a7d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1401b3a7d`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1401b3b79`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1401b3b79`

## string_xrefs

- `0x1401b3a96`: `RunDLL32.EXE Shell32.DLL,ShellExec_RunDLL ?0x%X?%s`
- `0x1401b3a6d`: `RunDLL32.EXE`

## pseudocode

```c
__int64 __fastcall _ShellExecuteRegAppWithJobObject(__int64 a1, char a2, __int64 a3)
{
  HANDLE JobObjectW; // rsi
  int Error; // ebx
  __int64 v8; // rcx
  UINT SystemDirectoryW; // r14d
  HANDLE IoCompletionPort; // rax
  void *v11; // rdi
  HANDLE v12; // r14
  HWND v13; // rcx
  DWORD ProcessId; // eax
  __int64 v15; // rcx
  DWORD ThreadId; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD JobObjectInformation[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR CommandLine[520]; // [rsp+300h] [rbp+200h] BYREF

  JobObjectW = CreateJobObjectW(0, 0);
  if ( JobObjectW || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
    if ( (byte_140253B81 & 0x20) != 0 )
      McTemplateU0z_EventWriteTransfer(v8, &ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Start, a1);
    Error = -2147467259;
    if ( SystemDirectoryW - 1 > 0x102 )
      goto LABEL_30;
    if ( PathCchAppend(Buffer, 0x104u, L"RunDLL32.EXE") < 0 )
      goto LABEL_30;
    if ( (int)StringCchPrintfW(CommandLine, 0x208u, L"RunDLL32.EXE Shell32.DLL,ShellExec_RunDLL ?0x%X?%s", 1024, a1) < 0 )
      goto LABEL_30;
    *(_QWORD *)&StartupInfo.cb = 104;
    memset_0(&StartupInfo.lpReserved, 0, 0x60u);
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( !CreateProcessW(Buffer, CommandLine, 0, 0, 0, 4u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_30;
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
LABEL_28:
        TerminateProcess(ProcessInformation.hProcess, 5u);
LABEL_29:
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(ProcessInformation.hThread);
LABEL_30:
        CloseHandle(JobObjectW);
        return (unsigned int)Error;
      }
    }
    if ( (a2 & 2) == 0 )
    {
      ResumeThread(ProcessInformation.hThread);
      if ( (a2 & 0x40) != 0 )
        IUnknown_WaitForSteadyState(a3, ProcessInformation.hProcess);
LABEL_25:
      if ( (byte_140253B81 & 0x20) != 0 )
      {
        ProcessId = GetProcessId(ProcessInformation.hProcess);
        McTemplateU0qz_EventWriteTransfer(v15, &ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Stop, ProcessId, a1);
      }
      if ( Error >= 0 )
        goto LABEL_29;
      goto LABEL_28;
    }
    IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u);
    v11 = IoCompletionPort;
    if ( IoCompletionPort )
    {
      JobObjectInformation[0] = JobObjectW;
      JobObjectInformation[1] = IoCompletionPort;
      if ( SetInformationJobObject(JobObjectW, JobObjectAssociateCompletionPortInformation, JobObjectInformation, 0x10u) )
        goto LABEL_18;
      CloseHandle(v11);
      v11 = 0;
    }
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_25;
LABEL_18:
    ThreadId = 0;
    v12 = CreateThread(0, 0, _JobObjectWaitingThreadProc, v11, 0, &ThreadId);
    if ( v12 )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_22:
        CloseHandle(v11);
        goto LABEL_25;
      }
    }
    ResumeThread(ProcessInformation.hThread);
    SHProcessMessagesUntilEvent(v13, v12, 0xFFFFFFFF);
    CloseHandle(v12);
    goto LABEL_22;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1401b39d4  mov     [rsp-8+arg_8], rbx
0x1401b39d9  mov     [rsp-8+arg_18], rsi
0x1401b39de  push    rbp
0x1401b39df  push    rdi
0x1401b39e0  push    r12
0x1401b39e2  push    r14
0x1401b39e4  push    r15
0x1401b39e6  lea     rbp, [rsp-620h]
0x1401b39ee  sub     rsp, 720h
0x1401b39f5  mov     rax, cs:__security_cookie
0x1401b39fc  xor     rax, rsp
0x1401b39ff  mov     [rbp+640h+var_30], rax
0x1401b3a06  mov     edi, edx
0x1401b3a08  mov     r15, rcx
0x1401b3a0b  xor     edx, edx; lpName
0x1401b3a0d  xor     ecx, ecx; lpJobAttributes
0x1401b3a0f  mov     r12, r8
0x1401b3a12  call    cs:__imp_CreateJobObjectW
0x1401b3a18  mov     rsi, rax
0x1401b3a1b  test    rax, rax
0x1401b3a1e  jnz     short loc_1401B3A2F
0x1401b3a20  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1401b3a25  mov     ebx, eax
0x1401b3a27  test    eax, eax
0x1401b3a29  js      loc_1401B3CAE
0x1401b3a2f  mov     edx, 104h; uSize
0x1401b3a34  lea     rcx, [rbp+640h+Buffer]; lpBuffer
0x1401b3a38  call    cs:__imp_GetSystemDirectoryW
0x1401b3a3e  test    cs:byte_140253B81, 20h
0x1401b3a45  mov     r14d, eax
0x1401b3a48  jz      short loc_1401B3A59
0x1401b3a4a  mov     r8, r15
0x1401b3a4d  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Start
0x1401b3a54  call    McTemplateU0z_EventWriteTransfer
0x1401b3a59  lea     eax, [r14-1]
0x1401b3a5d  mov     ebx, 80004005h
0x1401b3a62  cmp     eax, 102h
0x1401b3a67  ja      loc_1401B3CA5
0x1401b3a6d  lea     r8, aRundll32Exe; "RunDLL32.EXE"
0x1401b3a74  mov     edx, 104h; cchPath
0x1401b3a79  lea     rcx, [rbp+640h+Buffer]; pszPath
0x1401b3a7d  call    cs:__imp_PathCchAppend
0x1401b3a83  test    eax, eax
0x1401b3a85  js      loc_1401B3CA5
0x1401b3a8b  mov     r9d, 400h
0x1401b3a91  mov     qword ptr [rsp+740h+bInheritHandles], r15
0x1401b3a96  lea     r8, aRundll32ExeShe; "RunDLL32.EXE Shell32.DLL,ShellExec_RunD"...
0x1401b3a9d  mov     edx, 208h; unsigned __int64
0x1401b3aa2  lea     rcx, [rbp+640h+CommandLine]; unsigned __int16 *
0x1401b3aa9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401b3aae  test    eax, eax
0x1401b3ab0  js      loc_1401B3CA5
0x1401b3ab6  xor     edx, edx; Val
0x1401b3ab8  mov     qword ptr [rbp+640h+StartupInfo.cb], 68h ; 'h'
0x1401b3ac0  lea     rcx, [rbp+640h+StartupInfo.lpReserved]; void *
0x1401b3ac4  lea     r8d, [rdx+60h]; Size
0x1401b3ac8  call    memset_0
0x1401b3acd  xor     eax, eax
0x1401b3acf  lea     rdx, [rbp+640h+CommandLine]; lpCommandLine
0x1401b3ad6  mov     qword ptr [rsp+740h+ProcessInformation.dwProcessId], rax
0x1401b3adb  lea     rcx, [rbp+640h+Buffer]; lpApplicationName
0x1401b3adf  lea     rax, [rsp+740h+ProcessInformation]
0x1401b3ae4  xorps   xmm0, xmm0
0x1401b3ae7  mov     [rsp+740h+lpProcessInformation], rax; lpProcessInformation
0x1401b3aec  xor     r9d, r9d; lpThreadAttributes
0x1401b3aef  lea     rax, [rbp+640h+StartupInfo]
0x1401b3af3  xor     r8d, r8d; lpProcessAttributes
0x1401b3af6  mov     [rsp+740h+lpStartupInfo], rax; lpStartupInfo
0x1401b3afb  mov     [rsp+740h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1401b3b04  mov     [rsp+740h+lpEnvironment], 0; lpEnvironment
0x1401b3b0d  mov     [rsp+740h+dwCreationFlags], 4; dwCreationFlags
0x1401b3b15  mov     [rsp+740h+bInheritHandles], 0; bInheritHandles
0x1401b3b1d  movups  xmmword ptr [rsp+740h+ProcessInformation.hProcess], xmm0
0x1401b3b22  call    cs:__imp_CreateProcessW
0x1401b3b28  test    eax, eax
0x1401b3b2a  jnz     short loc_1401B3B3B
0x1401b3b2c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1401b3b31  mov     ebx, eax
0x1401b3b33  test    eax, eax
0x1401b3b35  js      loc_1401B3CA5
0x1401b3b3b  mov     rdx, [rsp+740h+ProcessInformation.hProcess]; hProcess
0x1401b3b40  mov     rcx, rsi; hJob
0x1401b3b43  call    cs:__imp_AssignProcessToJobObject
0x1401b3b49  test    eax, eax
0x1401b3b4b  jz      short loc_1401B3B51
0x1401b3b4d  xor     ebx, ebx
0x1401b3b4f  jmp     short loc_1401B3B60
0x1401b3b51  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1401b3b56  mov     ebx, eax
0x1401b3b58  test    eax, eax
0x1401b3b5a  js      loc_1401B3C7F
0x1401b3b60  test    dil, 2
0x1401b3b64  jz      loc_1401B3C37
0x1401b3b6a  mov     r9d, 1; NumberOfConcurrentThreads
0x1401b3b70  xor     r8d, r8d; CompletionKey
0x1401b3b73  xor     edx, edx; ExistingCompletionPort
0x1401b3b75  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x1401b3b79  call    cs:__imp_CreateIoCompletionPort
0x1401b3b7f  mov     rdi, rax
0x1401b3b82  test    rax, rax
0x1401b3b85  jz      short loc_1401B3BB8
0x1401b3b87  mov     r9d, 10h; cbJobObjectInformationLength
0x1401b3b8d  mov     [rsp+740h+JobObjectInformation], rsi
0x1401b3b92  lea     r8, [rsp+740h+JobObjectInformation]; lpJobObjectInformation
0x1401b3b97  mov     [rsp+740h+var_6C8], rax
0x1401b3b9c  mov     rcx, rsi; hJob
0x1401b3b9f  lea     edx, [r9-9]; JobObjectInformationClass
0x1401b3ba3  call    cs:__imp_SetInformationJobObject
0x1401b3ba9  test    eax, eax
0x1401b3bab  jnz     short loc_1401B3BC7
0x1401b3bad  mov     rcx, rdi; hObject
0x1401b3bb0  call    cs:__imp_CloseHandle
0x1401b3bb6  xor     edi, edi
0x1401b3bb8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1401b3bbd  mov     ebx, eax
0x1401b3bbf  test    eax, eax
0x1401b3bc1  js      loc_1401B3C55
0x1401b3bc7  lea     rax, [rsp+740h+ThreadId]
0x1401b3bcc  mov     [rsp+740h+ThreadId], 0
0x1401b3bd4  mov     qword ptr [rsp+740h+dwCreationFlags], rax; lpThreadId
0x1401b3bd9  lea     r8, ?_JobObjectWaitingThreadProc@@YAKPEAX@Z; lpStartAddress
0x1401b3be0  mov     r9, rdi; lpParameter
0x1401b3be3  mov     [rsp+740h+bInheritHandles], 0; dwCreationFlags
0x1401b3beb  xor     edx, edx; dwStackSize
0x1401b3bed  xor     ecx, ecx; lpThreadAttributes
0x1401b3bef  call    cs:__imp_CreateThread
0x1401b3bf5  mov     r14, rax
0x1401b3bf8  test    rax, rax
0x1401b3bfb  jz      short loc_1401B3C01
0x1401b3bfd  xor     ebx, ebx
0x1401b3bff  jmp     short loc_1401B3C0C
0x1401b3c01  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1401b3c06  mov     ebx, eax
0x1401b3c08  test    eax, eax
0x1401b3c0a  js      short loc_1401B3C2C
0x1401b3c0c  mov     rcx, [rsp+740h+ProcessInformation.hThread]; hThread
0x1401b3c11  call    cs:__imp_ResumeThread
0x1401b3c17  or      r8d, 0FFFFFFFFh; unsigned int
0x1401b3c1b  mov     rdx, r14; void *
0x1401b3c1e  call    ?SHProcessMessagesUntilEvent@@YAKPEAUHWND__@@PEAXK@Z; SHProcessMessagesUntilEvent(HWND__ *,void *,ulong)
0x1401b3c23  mov     rcx, r14; hObject
0x1401b3c26  call    cs:__imp_CloseHandle
0x1401b3c2c  mov     rcx, rdi; hObject
0x1401b3c2f  call    cs:__imp_CloseHandle
0x1401b3c35  jmp     short loc_1401B3C55
0x1401b3c37  mov     rcx, [rsp+740h+ProcessInformation.hThread]; hThread
0x1401b3c3c  call    cs:__imp_ResumeThread
0x1401b3c42  test    dil, 40h
0x1401b3c46  jz      short loc_1401B3C55
0x1401b3c48  mov     rdx, [rsp+740h+ProcessInformation.hProcess]
0x1401b3c4d  mov     rcx, r12
0x1401b3c50  call    IUnknown_WaitForSteadyState
0x1401b3c55  test    cs:byte_140253B81, 20h
0x1401b3c5c  jz      short loc_1401B3C7B
0x1401b3c5e  mov     rcx, [rsp+740h+ProcessInformation.hProcess]; Process
0x1401b3c63  call    cs:__imp_GetProcessId
0x1401b3c69  mov     r9, r15
0x1401b3c6c  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Stop
0x1401b3c73  mov     r8d, eax
0x1401b3c76  call    McTemplateU0qz_EventWriteTransfer
0x1401b3c7b  test    ebx, ebx
0x1401b3c7d  jns     short loc_1401B3C8F
0x1401b3c7f  mov     rcx, [rsp+740h+ProcessInformation.hProcess]; hProcess
0x1401b3c84  mov     edx, 5; uExitCode
0x1401b3c89  call    cs:__imp_TerminateProcess
0x1401b3c8f  mov     rcx, [rsp+740h+ProcessInformation.hProcess]; hObject
0x1401b3c94  call    cs:__imp_CloseHandle
0x1401b3c9a  mov     rcx, [rsp+740h+ProcessInformation.hThread]; hObject
0x1401b3c9f  call    cs:__imp_CloseHandle
0x1401b3ca5  mov     rcx, rsi; hObject
0x1401b3ca8  call    cs:__imp_CloseHandle
0x1401b3cae  mov     eax, ebx
0x1401b3cb0  mov     rcx, [rbp+640h+var_30]
0x1401b3cb7  xor     rcx, rsp; StackCookie
0x1401b3cba  call    __security_check_cookie
0x1401b3cbf  lea     r11, [rsp+740h+var_20]
0x1401b3cc7  mov     rbx, [r11+38h]
0x1401b3ccb  mov     rsi, [r11+48h]
0x1401b3ccf  mov     rsp, r11
0x1401b3cd2  pop     r15
0x1401b3cd4  pop     r14
0x1401b3cd6  pop     r12
0x1401b3cd8  pop     rdi
0x1401b3cd9  pop     rbp
0x1401b3cda  retn
```
