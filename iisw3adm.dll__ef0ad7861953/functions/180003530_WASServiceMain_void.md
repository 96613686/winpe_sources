# WASServiceMain(void)

- ea: `0x180003530`
- end: `0x180003764`
- name: `?WASServiceMain@@YAXXZ`
- size: `564`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800034e0`

## callees

- `0x180002bfc`
- `0x180003530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003621`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000362b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000366e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000362b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000366e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180003664`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180003664`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800035ba`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800035ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036e9`
- `iisutil!PuDbgPrint` at `0x180003591`
- `iisutil!PuDbgPrint` at `0x180003725`
- `iisutil!PuDbgPrint` at `0x180003591`
- `iisutil!PuDbgPrint` at `0x180003725`
- `iisutil!PuDbgPrintError` at `0x18000360e`
- `iisutil!PuDbgPrintError` at `0x1800036e0`
- `iisutil!PuDbgPrintError` at `0x18000360e`
- `iisutil!PuDbgPrintError` at `0x1800036e0`

## string_xrefs

- `0x18000355f`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\main.cxx`
- `0x180003579`: `ServiceMain entrypoint called\n`
- `0x180003543`: `WASServiceMain`
- `0x1800035f2`: `CreateThread() failed\n`
- `0x18000368c`: `GetExitCodeThread() failed\n`
- `0x1800036bd`: `WASServiceThreadProc() failed\n`
- `0x18000370d`: `Service exiting\n`

## pseudocode

```c
void WASServiceMain(void)
{
  HANDLE v0; // rax
  void *v1; // rdi
  signed int v2; // eax
  signed int v3; // ebx
  int v4; // eax
  signed int LastError; // eax
  signed int v6; // eax
  DWORD ExitCode; // [rsp+50h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+58h] [rbp+10h] BYREF

  ExitCode = 0;
  ThreadId = 0;
  if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
      463,
      "WASServiceMain",
      "ServiceMain entrypoint called\n");
  v0 = CreateThread(0, 0x8000u, WASServiceThreadProc, 0, 0, &ThreadId);
  v1 = v0;
  if ( v0 )
  {
    if ( WaitForSingleObject(v0, 0xFFFFFFFF) == -1 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
          499,
          "WASServiceMain",
          v3,
          "WaitForSingleObject() failed\n");
    }
    else if ( GetExitCodeThread(v1, &ExitCode) )
    {
      v3 = 0;
      if ( ExitCode )
      {
        v3 = (int)ExitCode > 0 ? (unsigned __int16)ExitCode | 0x80070000 : ExitCode;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
            536,
            "WASServiceMain",
            v3,
            "WASServiceThreadProc() failed\n");
      }
    }
    else
    {
      v6 = GetLastError();
      v3 = v6;
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
          518,
          "WASServiceMain",
          v3,
          "GetExitCodeThread() failed\n");
    }
    CloseHandle(v1);
    goto LABEL_25;
  }
  v2 = GetLastError();
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  v4 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
      484,
      "WASServiceMain",
      v3,
      "CreateThread() failed\n");
LABEL_25:
    v4 = g_dwDebugFlags;
  }
  if ( (v4 & 0x30000) != 0 && (v4 & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
      555,
      "WASServiceMain",
      "Service exiting\n");
  if ( !g_RegisterServiceCalled )
  {
    if ( v3 >= 0 )
      v3 = -2147467259;
    FakeServiceCtrlInCaseOfError(L"was", v3);
  }
  g_fWASStoppingInProgress = 0;
}

```

## disassembly

```asm
0x180003530  mov     [rsp+arg_10], rbx
0x180003535  push    rbp
0x180003536  push    rdi
0x180003537  push    r14
0x180003539  sub     rsp, 30h
0x18000353d  mov     eax, cs:g_dwDebugFlags
0x180003543  lea     rbp, aWasservicemain; "WASServiceMain"
0x18000354a  test    eax, 30000h
0x18000354f  mov     [rsp+48h+ExitCode], 0
0x180003557  mov     [rsp+48h+ThreadId], 0
0x18000355f  lea     r14, aServercommonIn_39; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180003566  setnz   cl
0x180003569  test    al, 3
0x18000356b  setnz   al
0x18000356e  test    al, cl
0x180003570  jz      short loc_180003597
0x180003572  mov     rcx, cs:g_pDebug
0x180003579  lea     rax, aServicemainEnt; "ServiceMain entrypoint called\n"
0x180003580  mov     r9, rbp
0x180003583  mov     qword ptr [rsp+48h+dwCreationFlags], rax
0x180003588  mov     r8d, 1CFh
0x18000358e  mov     rdx, r14
0x180003591  call    cs:__imp_PuDbgPrint
0x180003597  lea     rax, [rsp+48h+ThreadId]
0x18000359c  xor     r9d, r9d; lpParameter
0x18000359f  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800035a4  lea     r8, ?WASServiceThreadProc@@YAKPEAX@Z; lpStartAddress
0x1800035ab  mov     edx, 8000h; dwStackSize
0x1800035b0  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800035b8  xor     ecx, ecx; lpThreadAttributes
0x1800035ba  call    cs:__imp_CreateThread
0x1800035c0  mov     rdi, rax
0x1800035c3  test    rax, rax
0x1800035c6  jnz     short loc_180003619
0x1800035c8  call    cs:__imp_GetLastError
0x1800035ce  mov     ebx, eax
0x1800035d0  test    eax, eax
0x1800035d2  jle     short loc_1800035DD
0x1800035d4  movzx   ebx, ax
0x1800035d7  or      ebx, 80070000h
0x1800035dd  mov     eax, cs:g_dwDebugFlags
0x1800035e3  test    al, 0Fh
0x1800035e5  jz      loc_1800036F5
0x1800035eb  mov     rcx, cs:g_pDebug
0x1800035f2  lea     rax, aCreatethreadFa; "CreateThread() failed\n"
0x1800035f9  mov     [rsp+48h+lpThreadId], rax
0x1800035fe  mov     r9, rbp
0x180003601  mov     r8d, 1E4h
0x180003607  mov     [rsp+48h+dwCreationFlags], ebx
0x18000360b  mov     rdx, r14
0x18000360e  call    cs:__imp_PuDbgPrintError
0x180003614  jmp     loc_1800036EF
0x180003619  or      ebx, 0FFFFFFFFh
0x18000361c  mov     rcx, rdi; hHandle
0x18000361f  mov     edx, ebx; dwMilliseconds
0x180003621  call    cs:__imp_WaitForSingleObject
0x180003627  cmp     eax, ebx
0x180003629  jnz     short loc_18000365C
0x18000362b  call    cs:__imp_GetLastError
0x180003631  mov     ebx, eax
0x180003633  test    eax, eax
0x180003635  jle     short loc_180003640
0x180003637  movzx   ebx, ax
0x18000363a  or      ebx, 80070000h
0x180003640  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003647  jz      loc_1800036E6
0x18000364d  lea     rax, aWaitforsingleo; "WaitForSingleObject() failed\n"
0x180003654  mov     r8d, 1F3h
0x18000365a  jmp     short loc_1800036CA
0x18000365c  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x180003661  mov     rcx, rdi; hThread
0x180003664  call    cs:__imp_GetExitCodeThread
0x18000366a  test    eax, eax
0x18000366c  jnz     short loc_18000369B
0x18000366e  call    cs:__imp_GetLastError
0x180003674  mov     ebx, eax
0x180003676  test    eax, eax
0x180003678  jle     short loc_180003683
0x18000367a  movzx   ebx, ax
0x18000367d  or      ebx, 80070000h
0x180003683  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000368a  jz      short loc_1800036E6
0x18000368c  lea     rax, aGetexitcodethr; "GetExitCodeThread() failed\n"
0x180003693  mov     r8d, 206h
0x180003699  jmp     short loc_1800036CA
0x18000369b  mov     eax, [rsp+48h+ExitCode]
0x18000369f  xor     ebx, ebx
0x1800036a1  test    eax, eax
0x1800036a3  jz      short loc_1800036E6
0x1800036a5  jg      short loc_1800036AB
0x1800036a7  mov     ebx, eax
0x1800036a9  jmp     short loc_1800036B4
0x1800036ab  movzx   ebx, ax
0x1800036ae  or      ebx, 80070000h
0x1800036b4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800036bb  jz      short loc_1800036E6
0x1800036bd  lea     rax, aWasservicethre_0; "WASServiceThreadProc() failed\n"
0x1800036c4  mov     r8d, 218h
0x1800036ca  mov     rcx, cs:g_pDebug
0x1800036d1  mov     r9, rbp
0x1800036d4  mov     [rsp+48h+lpThreadId], rax
0x1800036d9  mov     rdx, r14
0x1800036dc  mov     [rsp+48h+dwCreationFlags], ebx
0x1800036e0  call    cs:__imp_PuDbgPrintError
0x1800036e6  mov     rcx, rdi; hObject
0x1800036e9  call    cs:__imp_CloseHandle
0x1800036ef  mov     eax, cs:g_dwDebugFlags
0x1800036f5  test    eax, 30000h
0x1800036fa  setnz   cl
0x1800036fd  test    al, 3
0x1800036ff  setnz   al
0x180003702  test    al, cl
0x180003704  jz      short loc_18000372B
0x180003706  mov     rcx, cs:g_pDebug
0x18000370d  lea     rax, aServiceExiting; "Service exiting\n"
0x180003714  mov     r9, rbp
0x180003717  mov     qword ptr [rsp+48h+dwCreationFlags], rax
0x18000371c  mov     r8d, 22Bh
0x180003722  mov     rdx, r14
0x180003725  call    cs:__imp_PuDbgPrint
0x18000372b  cmp     cs:?g_RegisterServiceCalled@@3HA, 0; int g_RegisterServiceCalled
0x180003732  jnz     short loc_18000374C
0x180003734  test    ebx, ebx
0x180003736  lea     rcx, aWas_1; "was"
0x18000373d  mov     eax, 80004005h
0x180003742  cmovns  ebx, eax
0x180003745  mov     edx, ebx; int
0x180003747  call    ?FakeServiceCtrlInCaseOfError@@YAXPEBGJ@Z; FakeServiceCtrlInCaseOfError(ushort const *,long)
0x18000374c  mov     rbx, [rsp+48h+arg_10]
0x180003751  mov     cs:?g_fWASStoppingInProgress@@3HA, 0; int g_fWASStoppingInProgress
0x18000375b  add     rsp, 30h
0x18000375f  pop     r14
0x180003761  pop     rdi
0x180003762  pop     rbp
0x180003763  retn
```
