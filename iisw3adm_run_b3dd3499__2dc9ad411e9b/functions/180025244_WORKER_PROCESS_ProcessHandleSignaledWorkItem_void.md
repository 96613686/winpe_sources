# WORKER_PROCESS::ProcessHandleSignaledWorkItem(void)

- ea: `0x180025244`
- end: `0x1800253ed`
- name: `?ProcessHandleSignaledWorkItem@WORKER_PROCESS@@AEAAJXZ`
- size: `425`
- prototype: `__int64 __fastcall(WORKER_PROCESS *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180023390`

## callees

- `0x180024d5c`
- `0x180025244`
- `0x180027d04`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252e6`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800252d0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800252d0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800252dc`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800252dc`
- `iisutil!PuDbgPrint` at `0x1800252aa`
- `iisutil!PuDbgPrint` at `0x180025383`
- `iisutil!PuDbgPrint` at `0x1800252aa`
- `iisutil!PuDbgPrint` at `0x180025383`
- `iisutil!PuDbgPrintError` at `0x180025333`
- `iisutil!PuDbgPrintError` at `0x180025333`

## string_xrefs

- `0x18002527e`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x18002532c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180025366`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`

## pseudocode

```c
__int64 __fastcall WORKER_PROCESS::ProcessHandleSignaledWorkItem(WORKER_PROCESS *this)
{
  WEB_ADMIN_SERVICE *v2; // rax
  BOOL ExitCodeThread; // eax
  signed int LastError; // eax
  unsigned int v5; // edi
  DWORD ExitCode; // [rsp+50h] [rbp+8h] BYREF

  ExitCode = 0;
  if ( (g_dwDebugFlags & 0x410000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
      6333,
      "WORKER_PROCESS::ProcessHandleSignaledWorkItem",
      "Process handle has been signaled (ptr: %p; pid: %lu; realpid: %lu)\n",
      this,
      *((_DWORD *)this + 18),
      *((_DWORD *)this + 19));
  v2 = g_pWebAdminService;
  *((_DWORD *)this + 26) = 0;
  if ( *((_DWORD *)v2 + 412) )
    ExitCodeThread = GetExitCodeThread(*((HANDLE *)this + 11), &ExitCode);
  else
    ExitCodeThread = GetExitCodeProcess(*((HANDLE *)this + 10), &ExitCode);
  if ( ExitCodeThread )
  {
    v5 = 0;
    if ( (g_dwDebugFlags & 0x410000) != 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
        6386,
        "WORKER_PROCESS::ProcessHandleSignaledWorkItem",
        "Process exit code was: %x\n",
        ExitCode);
    if ( ExitCode + 18 > 0xF )
    {
      if ( *((_DWORD *)this + 12) == 7 && (ExitCode == -2 || *(_DWORD *)(*((_QWORD *)this + 7) + 20LL) != 3) )
      {
        WORKER_PROCESS::Terminate(this);
        goto LABEL_16;
      }
    }
    else if ( *((_DWORD *)this + 12) == 8 )
    {
      goto LABEL_16;
    }
    WORKER_PROCESS::MarkAsTerminallyIll(this, 1);
    goto LABEL_16;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
      6374,
      "WORKER_PROCESS::ProcessHandleSignaledWorkItem",
      v5,
      "Getting process exit code failed\n");
LABEL_16:
  (*(void (__fastcall **)(WORKER_PROCESS *))(*(_QWORD *)this + 8LL))(this);
  return v5;
}

```

## disassembly

```asm
0x180025244  mov     [rsp+arg_8], rbx
0x180025249  push    rdi
0x18002524a  sub     rsp, 40h
0x18002524e  mov     eax, cs:g_dwDebugFlags
0x180025254  mov     rbx, rcx
0x180025257  test    eax, 410000h
0x18002525c  mov     [rsp+48h+ExitCode], 0
0x180025264  setnz   dl
0x180025267  test    al, 3
0x180025269  setnz   al
0x18002526c  test    al, dl
0x18002526e  jz      short loc_1800252B0
0x180025270  mov     eax, [rcx+4Ch]
0x180025273  lea     r9, aWorkerProcessP; "WORKER_PROCESS::ProcessHandleSignaledWo"...
0x18002527a  mov     [rsp+48h+var_10], eax
0x18002527e  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180025285  mov     eax, [rcx+48h]
0x180025288  mov     r8d, 18BDh
0x18002528e  mov     [rsp+48h+var_18], eax
0x180025292  lea     rax, aProcessHandleH; "Process handle has been signaled (ptr: "...
0x180025299  mov     [rsp+48h+var_20], rcx
0x18002529e  mov     rcx, cs:g_pDebug
0x1800252a5  mov     [rsp+48h+var_28], rax
0x1800252aa  call    cs:__imp_PuDbgPrint
0x1800252b0  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x1800252b7  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x1800252bc  mov     dword ptr [rbx+68h], 0
0x1800252c3  cmp     dword ptr [rax+670h], 0
0x1800252ca  jz      short loc_1800252D8
0x1800252cc  mov     rcx, [rbx+58h]; hThread
0x1800252d0  call    cs:__imp_GetExitCodeThread
0x1800252d6  jmp     short loc_1800252E2
0x1800252d8  mov     rcx, [rbx+50h]; hProcess
0x1800252dc  call    cs:__imp_GetExitCodeProcess
0x1800252e2  test    eax, eax
0x1800252e4  jnz     short loc_18002533B
0x1800252e6  call    cs:__imp_GetLastError
0x1800252ec  mov     edi, eax
0x1800252ee  test    eax, eax
0x1800252f0  jle     short loc_1800252FB
0x1800252f2  movzx   edi, ax
0x1800252f5  or      edi, 80070000h
0x1800252fb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180025302  jz      loc_1800253B1
0x180025308  mov     rcx, cs:g_pDebug
0x18002530f  lea     rax, aGettingProcess; "Getting process exit code failed\n"
0x180025316  mov     [rsp+48h+var_20], rax
0x18002531b  lea     r9, aWorkerProcessP; "WORKER_PROCESS::ProcessHandleSignaledWo"...
0x180025322  mov     r8d, 18E6h
0x180025328  mov     dword ptr [rsp+48h+var_28], edi
0x18002532c  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180025333  call    cs:__imp_PuDbgPrintError
0x180025339  jmp     short loc_1800253B1
0x18002533b  mov     eax, cs:g_dwDebugFlags
0x180025341  xor     edi, edi
0x180025343  test    eax, 410000h
0x180025348  setnz   cl
0x18002534b  test    al, 3
0x18002534d  setnz   al
0x180025350  test    al, cl
0x180025352  jz      short loc_180025389
0x180025354  mov     eax, [rsp+48h+ExitCode]
0x180025358  lea     r9, aWorkerProcessP; "WORKER_PROCESS::ProcessHandleSignaledWo"...
0x18002535f  mov     rcx, cs:g_pDebug
0x180025366  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002536d  mov     dword ptr [rsp+48h+var_20], eax
0x180025371  mov     r8d, 18F2h
0x180025377  lea     rax, aProcessExitCod; "Process exit code was: %x\n"
0x18002537e  mov     [rsp+48h+var_28], rax
0x180025383  call    cs:__imp_PuDbgPrint
0x180025389  mov     r8d, [rsp+48h+ExitCode]
0x18002538e  lea     eax, [r8+12h]
0x180025392  cmp     eax, 0Fh
0x180025395  ja      short loc_1800253CD
0x180025397  cmp     dword ptr [rbx+30h], 8
0x18002539b  jz      short loc_1800253B1
0x18002539d  xor     r9d, r9d
0x1800253a0  mov     [rsp+48h+var_28], rdi
0x1800253a5  mov     rcx, rbx
0x1800253a8  lea     edx, [r9+1]
0x1800253ac  call    ?MarkAsTerminallyIll@WORKER_PROCESS@@AEAAXW4WORKER_PROCESS_TERMINAL_ILLNESS_REASON@@KJPEBG@Z; WORKER_PROCESS::MarkAsTerminallyIll(WORKER_PROCESS_TERMINAL_ILLNESS_REASON,ulong,long,ushort const *)
0x1800253b1  mov     rcx, [rbx]
0x1800253b4  mov     rax, [rcx+8]
0x1800253b8  mov     rcx, rbx
0x1800253bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253c0  mov     rbx, [rsp+48h+arg_8]
0x1800253c5  mov     eax, edi
0x1800253c7  add     rsp, 40h
0x1800253cb  pop     rdi
0x1800253cc  retn
0x1800253cd  cmp     dword ptr [rbx+30h], 7
0x1800253d1  jnz     short loc_18002539D
0x1800253d3  cmp     r8d, 0FFFFFFFEh
0x1800253d7  jz      short loc_1800253E3
0x1800253d9  mov     rax, [rbx+38h]
0x1800253dd  cmp     dword ptr [rax+14h], 3
0x1800253e1  jz      short loc_18002539D
0x1800253e3  mov     rcx, rbx; this
0x1800253e6  call    ?Terminate@WORKER_PROCESS@@QEAAXXZ; WORKER_PROCESS::Terminate(void)
0x1800253eb  jmp     short loc_1800253B1
```
