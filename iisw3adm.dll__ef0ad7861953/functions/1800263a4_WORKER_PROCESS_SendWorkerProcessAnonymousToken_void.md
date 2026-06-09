# WORKER_PROCESS::SendWorkerProcessAnonymousToken(void)

- ea: `0x1800263a4`
- end: `0x180026597`
- name: `?SendWorkerProcessAnonymousToken@WORKER_PROCESS@@AEAAJXZ`
- size: `499`
- prototype: `__int64 __fastcall(WORKER_PROCESS *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028190`

## callees

- `0x180018eb4`
- `0x1800263a4`
- `0x18002979c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002647a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002647a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026504`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026498`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026498`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800264c4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800264c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002657f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002657f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180026423`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180026423`
- `iisutil!PuDbgPrint` at `0x180026474`
- `iisutil!PuDbgPrint` at `0x1800264fe`
- `iisutil!PuDbgPrint` at `0x180026474`
- `iisutil!PuDbgPrint` at `0x1800264fe`
- `iisutil!PuDbgPrintError` at `0x18002640d`
- `iisutil!PuDbgPrintError` at `0x180026576`
- `iisutil!PuDbgPrintError` at `0x18002640d`
- `iisutil!PuDbgPrintError` at `0x180026576`

## string_xrefs

- `0x180026402`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x1800263e2`: `Prepare anonymous token failed\n`
- `0x1800263f4`: `APP_POOL::GetAnonymousToken`
- `0x18002644b`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x1800264f7`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x18002656f`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180026463`: `Could not open handle to worker process (ptr: %p; pid: %lu; realpid: %lu)\n`
- `0x18002643d`: `WORKER_PROCESS::SendWorkerProcessAnonymousToken`
- `0x1800264e5`: `WORKER_PROCESS::SendWorkerProcessAnonymousToken`
- `0x18002655e`: `WORKER_PROCESS::SendWorkerProcessAnonymousToken`
- `0x1800264de`: `Could duplicate the anonymous token handle\n`
- `0x180026552`: `Executing m_MessagingHandler.SendAnonymousUserTokenHandle() failed\n`

## pseudocode

```c
__int64 __fastcall WORKER_PROCESS::SendWorkerProcessAnonymousToken(WORKER_PROCESS *this)
{
  APP_POOL *v1; // rdi
  int v3; // eax
  void *v4; // rsi
  HANDLE v5; // rdi
  signed int v6; // eax
  int v7; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  __int64 v10; // rcx
  HANDLE TargetHandle; // [rsp+50h] [rbp+8h] BYREF
  HANDLE v13; // [rsp+58h] [rbp+10h]

  v1 = (APP_POOL *)*((_QWORD *)this + 7);
  TargetHandle = 0;
  if ( !*((_QWORD *)v1 + 43) )
  {
    v3 = APP_POOL::PrepareAnonymousToken(v1);
    if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
        987,
        "APP_POOL::GetAnonymousToken",
        v3,
        "Prepare anonymous token failed\n");
  }
  v4 = (void *)*((_QWORD *)v1 + 43);
  v5 = OpenProcess(0x40u, 0, *((_DWORD *)this + 19));
  if ( v5 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( DuplicateHandle(CurrentProcess, v4, v5, &TargetHandle, 0, 0, 2u) )
    {
      v10 = *((_QWORD *)this + 5);
      v13 = TargetHandle;
      v7 = MESSAGING_HANDLER::SendMessageW(v10, 0x14u);
      if ( v7 < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
          7625,
          "WORKER_PROCESS::SendWorkerProcessAnonymousToken",
          v7,
          "Executing m_MessagingHandler.SendAnonymousUserTokenHandle() failed\n");
    }
    else
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
          7610,
          "WORKER_PROCESS::SendWorkerProcessAnonymousToken",
          "Could duplicate the anonymous token handle\n");
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(v5);
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
        7588,
        "WORKER_PROCESS::SendWorkerProcessAnonymousToken",
        "Could not open handle to worker process (ptr: %p; pid: %lu; realpid: %lu)\n",
        this,
        *((_DWORD *)this + 18),
        *((_DWORD *)this + 19));
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800263a4  mov     [rsp+arg_10], rbx
0x1800263a9  mov     [rsp+arg_18], rsi
0x1800263ae  push    rdi
0x1800263af  sub     rsp, 40h
0x1800263b3  mov     rdi, [rcx+38h]
0x1800263b7  mov     rbx, rcx
0x1800263ba  mov     [rsp+48h+TargetHandle], 0
0x1800263c3  cmp     qword ptr [rdi+158h], 0
0x1800263cb  jnz     short loc_180026413
0x1800263cd  mov     rcx, rdi; this
0x1800263d0  call    ?PrepareAnonymousToken@APP_POOL@@AEAAJXZ; APP_POOL::PrepareAnonymousToken(void)
0x1800263d5  test    eax, eax
0x1800263d7  jns     short loc_180026413
0x1800263d9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800263e0  jz      short loc_180026413
0x1800263e2  lea     rcx, aPrepareAnonymo; "Prepare anonymous token failed\n"
0x1800263e9  mov     r8d, 3DBh
0x1800263ef  mov     qword ptr [rsp+48h+bInheritHandle], rcx
0x1800263f4  lea     r9, aAppPoolGetanon; "APP_POOL::GetAnonymousToken"
0x1800263fb  mov     rcx, cs:g_pDebug
0x180026402  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180026409  mov     [rsp+48h+dwDesiredAccess], eax
0x18002640d  call    cs:__imp_PuDbgPrintError
0x180026413  mov     r8d, [rbx+4Ch]; dwProcessId
0x180026417  xor     edx, edx; bInheritHandle
0x180026419  mov     rsi, [rdi+158h]
0x180026420  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180026423  call    cs:__imp_OpenProcess
0x180026429  mov     rdi, rax
0x18002642c  test    rax, rax
0x18002642f  jnz     short loc_180026498
0x180026431  test    byte ptr cs:g_dwDebugFlags, 3
0x180026438  jz      short loc_18002647A
0x18002643a  mov     eax, [rbx+4Ch]
0x18002643d  lea     r9, aWorkerProcessS_3; "WORKER_PROCESS::SendWorkerProcessAnonym"...
0x180026444  mov     rcx, cs:g_pDebug
0x18002644b  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180026452  mov     [rsp+48h+var_10], eax
0x180026456  mov     r8d, 1DA4h
0x18002645c  mov     eax, [rbx+48h]
0x18002645f  mov     [rsp+48h+dwOptions], eax
0x180026463  lea     rax, aCouldNotOpenHa; "Could not open handle to worker process"...
0x18002646a  mov     qword ptr [rsp+48h+bInheritHandle], rbx
0x18002646f  mov     qword ptr [rsp+48h+dwDesiredAccess], rax
0x180026474  call    cs:__imp_PuDbgPrint
0x18002647a  call    cs:__imp_GetLastError
0x180026480  mov     ebx, eax
0x180026482  test    eax, eax
0x180026484  jle     loc_180026585
0x18002648a  movzx   ebx, ax
0x18002648d  or      ebx, 80070000h
0x180026493  jmp     loc_180026585
0x180026498  call    cs:__imp_GetCurrentProcess
0x18002649e  mov     [rsp+48h+dwOptions], 2; dwOptions
0x1800264a6  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x1800264ab  mov     rcx, rax; hSourceProcessHandle
0x1800264ae  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x1800264b6  mov     r8, rdi; hTargetProcessHandle
0x1800264b9  mov     [rsp+48h+dwDesiredAccess], 0; dwDesiredAccess
0x1800264c1  mov     rdx, rsi; hSourceHandle
0x1800264c4  call    cs:__imp_DuplicateHandle
0x1800264ca  test    eax, eax
0x1800264cc  jnz     short loc_18002651B
0x1800264ce  test    byte ptr cs:g_dwDebugFlags, 3
0x1800264d5  jz      short loc_180026504
0x1800264d7  mov     rcx, cs:g_pDebug
0x1800264de  lea     rax, aCouldDuplicate; "Could duplicate the anonymous token han"...
0x1800264e5  lea     r9, aWorkerProcessS_3; "WORKER_PROCESS::SendWorkerProcessAnonym"...
0x1800264ec  mov     qword ptr [rsp+48h+dwDesiredAccess], rax
0x1800264f1  mov     r8d, 1DBAh
0x1800264f7  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800264fe  call    cs:__imp_PuDbgPrint
0x180026504  call    cs:__imp_GetLastError
0x18002650a  mov     ebx, eax
0x18002650c  test    eax, eax
0x18002650e  jle     short loc_18002657C
0x180026510  movzx   ebx, ax
0x180026513  or      ebx, 80070000h
0x180026519  jmp     short loc_18002657C
0x18002651b  mov     rax, [rsp+48h+TargetHandle]
0x180026520  lea     r9, [rsp+48h+arg_8]
0x180026525  mov     rcx, [rbx+28h]
0x180026529  mov     edx, 14h
0x18002652e  mov     [rsp+48h+arg_8], rax
0x180026533  lea     r8d, [rdx-0Ch]
0x180026537  call    ?SendMessageW@MESSAGING_HANDLER@@AEAAJW4IPM_OPCODE@@KPEAE@Z; MESSAGING_HANDLER::SendMessageW(IPM_OPCODE,ulong,uchar *)
0x18002653c  mov     ebx, eax
0x18002653e  test    eax, eax
0x180026540  jns     short loc_18002657C
0x180026542  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180026549  jz      short loc_18002657C
0x18002654b  mov     rcx, cs:g_pDebug
0x180026552  lea     rax, aExecutingMMess_2; "Executing m_MessagingHandler.SendAnonym"...
0x180026559  mov     qword ptr [rsp+48h+bInheritHandle], rax
0x18002655e  lea     r9, aWorkerProcessS_3; "WORKER_PROCESS::SendWorkerProcessAnonym"...
0x180026565  mov     r8d, 1DC9h
0x18002656b  mov     [rsp+48h+dwDesiredAccess], ebx
0x18002656f  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180026576  call    cs:__imp_PuDbgPrintError
0x18002657c  mov     rcx, rdi; hObject
0x18002657f  call    cs:__imp_CloseHandle
0x180026585  mov     rsi, [rsp+48h+arg_18]
0x18002658a  mov     eax, ebx
0x18002658c  mov     rbx, [rsp+48h+arg_10]
0x180026591  add     rsp, 40h
0x180026595  pop     rdi
0x180026596  retn
```
