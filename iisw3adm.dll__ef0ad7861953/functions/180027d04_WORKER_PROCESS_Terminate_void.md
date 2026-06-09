# WORKER_PROCESS::Terminate(void)

- ea: `0x180027d04`
- end: `0x180028049`
- name: `?Terminate@WORKER_PROCESS@@QEAAXXZ`
- size: `837`
- prototype: `void __fastcall(WORKER_PROCESS *__hidden this)`
- caller_count: `3`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ac94`
- `0x180024d5c`
- `0x180025244`

## callees

- `0x180004290`
- `0x180011064`
- `0x1800193e4`
- `0x180022078`
- `0x180022100`
- `0x1800221a8`
- `0x1800249b4`
- `0x1800251b0`
- `0x180027bf0`
- `0x180027d04`
- `0x18003e748`
- `0x180040d30`
- `0x180062010`

## import_xrefs

- `ntdll!RtlDeregisterWaitEx` at `0x180027dec`
- `ntdll!RtlDeregisterWaitEx` at `0x180027dec`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027ed0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027ed0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027ec6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002802a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027ec6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002802a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027eaa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027fdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027eaa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027fdc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180027fbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180027fbe`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180027f6f`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180027f6f`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180027f38`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180027f38`
- `iisutil!PuDbgPrint` at `0x180027fa7`
- `iisutil!PuDbgPrint` at `0x180027fa7`
- `iisutil!PuDbgPrintError` at `0x180027e2e`
- `iisutil!PuDbgPrintError` at `0x180027e2e`
- `iisutil!?DestroyIpmMessagePipe@IPM_MESSAGE_PIPE@@QEAAXXZ` at `0x180027dbd`
- `iisutil!?DestroyIpmMessagePipe@IPM_MESSAGE_PIPE@@QEAAXXZ` at `0x180027dbd`

## string_xrefs

- `0x180027f87`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x180027f9b`: `Worker Process: %lu removed from hashtable; total number now: %lu\n`
- `0x180027e1d`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`

## pseudocode

```c
void __fastcall WORKER_PROCESS::Terminate(WORKER_PROCESS *this)
{
  WEB_ADMIN_SERVICE *v2; // rcx
  const unsigned __int16 *v3; // rdx
  WORKER_PROCESS *v4; // rcx
  WORKER_PROCESS *v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rcx
  IPM_MESSAGE_PIPE *v8; // rcx
  void *v9; // rcx
  NTSTATUS v10; // eax
  char *v11; // rbp
  int v12; // ebx
  WORKER_PROCESS *v13; // rcx
  WEB_ADMIN_SERVICE *v14; // rbx
  unsigned int v15; // eax
  WEB_ADMIN_SERVICE *v16; // rbx
  DWORD TickCount; // eax
  __int64 v18; // rdi
  DWORD v19; // ebp
  int v20; // ebx
  unsigned int v21; // ebp
  unsigned int v22; // edx
  struct PROTOCOL *v23; // [rsp+80h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 12) != 8 )
  {
    *((_DWORD *)this + 12) = 8;
    if ( !*((_DWORD *)this + 28) )
    {
      ++*(_DWORD *)(*((_QWORD *)this + 7) + 124LL);
      ++*((_DWORD *)g_pWebAdminService + 133);
      *((_DWORD *)this + 28) = 1;
    }
    WORKER_PROCESS::CancelStartupTimer(this);
    WORKER_PROCESS::CancelShutdownTimer(this);
    WEB_ADMIN_SERVICE::CancelTimer(v2, (struct _TP_TIMER **)this + 19);
    WORKER_PROCESS::CancelPingResponseTimer(this);
    v4 = (WORKER_PROCESS *)*((_QWORD *)this + 44);
    if ( v4 != (WORKER_PROCESS *)((char *)this + 352) )
    {
      do
      {
        v5 = *(WORKER_PROCESS **)v4;
        WORKER_PROCESS_QUERY::Terminate((WORKER_PROCESS *)((char *)v4 - 72), -2147023829);
        v4 = v5;
      }
      while ( v5 != (WORKER_PROCESS *)((char *)this + 352) );
    }
    v6 = *((_QWORD *)this + 5);
    if ( v6 )
    {
      v7 = *(_QWORD *)(v6 + 32);
      if ( v7 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
        *(_QWORD *)(v6 + 32) = 0;
      }
      v8 = *(IPM_MESSAGE_PIPE **)(v6 + 24);
      if ( v8 )
      {
        IPM_MESSAGE_PIPE::DestroyIpmMessagePipe(v8);
        *(_QWORD *)(v6 + 24) = 0;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + 8LL))(*((_QWORD *)this + 5) + 8LL);
      *((_QWORD *)this + 5) = 0;
    }
    v9 = (void *)*((_QWORD *)this + 12);
    if ( v9 )
    {
      v10 = RtlDeregisterWaitEx(v9, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      if ( v10 >= 0 )
      {
        ProcessHandleSignaledCallback(this, 1u);
        *((_QWORD *)this + 12) = 0;
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
          6265,
          "WORKER_PROCESS::DeregisterProcessWait",
          v10 | 0x10000000,
          "Could not de-register wait on process handle\n");
      }
    }
    if ( *((_DWORD *)this + 19) )
    {
      v23 = 0;
      if ( (int)UL_AND_WORKER_MANAGER::FindProtocol((WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 112), v3, &v23) >= 0 )
      {
        v11 = *((_DWORD *)v23 + 92) ? (char *)v23 + 392 : 0LL;
        if ( v11 && (v11[10520] & 4) != 0 )
        {
          v12 = *((_DWORD *)this + 19);
          EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 35104));
          *(_DWORD *)&v11[4 * (*((_DWORD *)v11 + 10834))++ + 35144] = v12;
          LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 35104));
          SetEvent(*((HANDLE *)v11 + 7));
        }
      }
    }
    if ( *((_DWORD *)this + 26) )
      WORKER_PROCESS::KillProcess(this);
    v13 = (WORKER_PROCESS *)*((_QWORD *)this + 23);
    if ( v13 )
    {
      WORKER_PROCESS::StartShutdown(v13, 0);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 8LL))(*((_QWORD *)this + 23));
      *((_QWORD *)this + 23) = 0;
    }
    REQUEST_QUEUE_INSTANCE_TABLE::Terminate((WORKER_PROCESS *)((char *)this + 264));
    if ( *((_DWORD *)this + 19) )
    {
      v14 = g_pWebAdminService;
      if ( !(unsigned int)CLKRHashTable::DeleteRecord((char *)g_pWebAdminService + 448, this) )
      {
        (*(void (__fastcall **)(WORKER_PROCESS *))(*(_QWORD *)this + 8LL))(this);
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x30000) != 0 )
        {
          v15 = CLKRHashTable::Size((WEB_ADMIN_SERVICE *)((char *)v14 + 448));
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
            1774,
            "UL_AND_WORKER_MANAGER::StopTrackingWorkerProcess",
            "Worker Process: %lu removed from hashtable; total number now: %lu\n",
            *((_DWORD *)this + 19),
            v15);
        }
      }
      --*(_DWORD *)(*((_QWORD *)this + 7) + 128LL);
    }
    v16 = g_pWebAdminService;
    TickCount = GetTickCount();
    v18 = *((_QWORD *)v16 + 231);
    v19 = TickCount;
    if ( v18 )
    {
      v20 = *((_DWORD *)this + 32);
      EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 80));
      v21 = v19 - v20;
      if ( v21 )
      {
        if ( v21 > 0xEA60 )
          v22 = v21 / 0xEA60;
        else
          v22 = 1;
      }
      else
      {
        v22 = 0;
      }
      *(_DWORD *)(v18 + 40) += v22;
      ++*(_DWORD *)(v18 + 44);
      if ( !*(_DWORD *)(v18 + 28) || v21 > *(_DWORD *)(v18 + 28) )
        *(_DWORD *)(v18 + 28) = v21;
      if ( !*(_DWORD *)(v18 + 32) || v21 < *(_DWORD *)(v18 + 32) )
        *(_DWORD *)(v18 + 32) = v21;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 80));
    }
    APP_POOL::RemoveWorkerProcessFromList(*((APP_POOL **)this + 7), this);
  }
}

```

## disassembly

```asm
0x180027d04  push    rbx
0x180027d06  push    rbp
0x180027d07  push    rsi
0x180027d08  push    rdi
0x180027d09  push    r14
0x180027d0b  push    r15
0x180027d0d  sub     rsp, 48h
0x180027d11  cmp     dword ptr [rcx+30h], 8
0x180027d15  mov     rsi, rcx
0x180027d18  jz      loc_18002803C
0x180027d1e  xor     r15d, r15d
0x180027d21  mov     dword ptr [rcx+30h], 8
0x180027d28  cmp     [rcx+70h], r15d
0x180027d2c  jnz     short loc_180027D49
0x180027d2e  mov     rax, [rcx+38h]
0x180027d32  inc     dword ptr [rax+7Ch]
0x180027d35  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180027d3c  inc     dword ptr [rax+214h]
0x180027d42  mov     dword ptr [rcx+70h], 1
0x180027d49  call    ?CancelStartupTimer@WORKER_PROCESS@@AEAAJXZ; WORKER_PROCESS::CancelStartupTimer(void)
0x180027d4e  mov     rcx, rsi; this
0x180027d51  call    ?CancelShutdownTimer@WORKER_PROCESS@@AEAAJXZ; WORKER_PROCESS::CancelShutdownTimer(void)
0x180027d56  lea     rdx, [rsi+98h]; struct _TP_TIMER **
0x180027d5d  call    ?CancelTimer@WEB_ADMIN_SERVICE@@QEAAJPEAPEAU_TP_TIMER@@@Z; WEB_ADMIN_SERVICE::CancelTimer(_TP_TIMER * *)
0x180027d62  mov     rcx, rsi; this
0x180027d65  call    ?CancelPingResponseTimer@WORKER_PROCESS@@AEAAJXZ; WORKER_PROCESS::CancelPingResponseTimer(void)
0x180027d6a  lea     rdi, [rsi+160h]
0x180027d71  mov     rcx, [rdi]
0x180027d74  cmp     rcx, rdi
0x180027d77  jz      short loc_180027D92
0x180027d79  mov     rbx, [rcx]
0x180027d7c  mov     edx, 8007042Bh; int
0x180027d81  add     rcx, 0FFFFFFFFFFFFFFB8h; this
0x180027d85  call    ?Terminate@WORKER_PROCESS_QUERY@@QEAAXJ@Z; WORKER_PROCESS_QUERY::Terminate(long)
0x180027d8a  mov     rcx, rbx
0x180027d8d  cmp     rbx, rdi
0x180027d90  jnz     short loc_180027D79
0x180027d92  mov     rbx, [rsi+28h]
0x180027d96  test    rbx, rbx
0x180027d99  jz      short loc_180027DDF
0x180027d9b  mov     rcx, [rbx+20h]
0x180027d9f  test    rcx, rcx
0x180027da2  jz      short loc_180027DB4
0x180027da4  mov     rax, [rcx]
0x180027da7  mov     rax, [rax+8]
0x180027dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027db0  mov     [rbx+20h], r15
0x180027db4  mov     rcx, [rbx+18h]
0x180027db8  test    rcx, rcx
0x180027dbb  jz      short loc_180027DC7
0x180027dbd  call    cs:__imp_?DestroyIpmMessagePipe@IPM_MESSAGE_PIPE@@QEAAXXZ; IPM_MESSAGE_PIPE::DestroyIpmMessagePipe(void)
0x180027dc3  mov     [rbx+18h], r15
0x180027dc7  mov     rcx, [rsi+28h]
0x180027dcb  add     rcx, 8
0x180027dcf  mov     rax, [rcx]
0x180027dd2  mov     rax, [rax+8]
0x180027dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ddb  mov     [rsi+28h], r15
0x180027ddf  mov     rcx, [rsi+60h]; hWaitHandle
0x180027de3  test    rcx, rcx
0x180027de6  jz      short loc_180027E44
0x180027de8  or      rdx, 0FFFFFFFFFFFFFFFFh; hCompletionEvent
0x180027dec  call    cs:__imp_RtlDeregisterWaitEx
0x180027df2  test    eax, eax
0x180027df4  jns     short loc_180027E36
0x180027df6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180027dfd  jz      short loc_180027E44
0x180027dff  lea     rcx, aCouldNotDeRegi; "Could not de-register wait on process h"...
0x180027e06  bts     eax, 1Ch
0x180027e0a  mov     [rsp+78h+var_50], rcx
0x180027e0f  lea     r9, aWorkerProcessD; "WORKER_PROCESS::DeregisterProcessWait"
0x180027e16  mov     rcx, cs:g_pDebug
0x180027e1d  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180027e24  mov     r8d, 1879h
0x180027e2a  mov     dword ptr [rsp+78h+var_58], eax
0x180027e2e  call    cs:__imp_PuDbgPrintError
0x180027e34  jmp     short loc_180027E44
0x180027e36  mov     dl, 1; BOOLEAN
0x180027e38  mov     rcx, rsi; PVOID
0x180027e3b  call    ?ProcessHandleSignaledCallback@@YAXPEAXE@Z; ProcessHandleSignaledCallback(void *,uchar)
0x180027e40  mov     [rsi+60h], r15
0x180027e44  cmp     [rsi+4Ch], r15d
0x180027e48  jz      loc_180027ED6
0x180027e4e  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180027e55  lea     r8, [rsp+78h+arg_0]; struct PROTOCOL **
0x180027e5d  add     rcx, 70h ; 'p'; this
0x180027e61  mov     [rsp+78h+arg_0], r15
0x180027e69  call    ?FindProtocol@UL_AND_WORKER_MANAGER@@QEAAJPEBGPEAPEAVPROTOCOL@@@Z; UL_AND_WORKER_MANAGER::FindProtocol(ushort const *,PROTOCOL * *)
0x180027e6e  test    eax, eax
0x180027e70  js      short loc_180027ED6
0x180027e72  mov     rbp, [rsp+78h+arg_0]
0x180027e7a  cmp     [rbp+170h], r15d
0x180027e81  jz      short loc_180027E8C
0x180027e83  add     rbp, 188h
0x180027e8a  jmp     short loc_180027E8F
0x180027e8c  mov     rbp, r15
0x180027e8f  test    rbp, rbp
0x180027e92  jz      short loc_180027ED6
0x180027e94  test    byte ptr [rbp+2918h], 4
0x180027e9b  jz      short loc_180027ED6
0x180027e9d  mov     ebx, [rsi+4Ch]
0x180027ea0  lea     rdi, [rbp+8920h]
0x180027ea7  mov     rcx, rdi; lpCriticalSection
0x180027eaa  call    cs:__imp_EnterCriticalSection
0x180027eb0  mov     eax, [rbp+0A948h]
0x180027eb6  mov     rcx, rdi; lpCriticalSection
0x180027eb9  mov     [rbp+rax*4+8948h], ebx
0x180027ec0  inc     dword ptr [rbp+0A948h]
0x180027ec6  call    cs:__imp_LeaveCriticalSection
0x180027ecc  mov     rcx, [rbp+38h]; hEvent
0x180027ed0  call    cs:__imp_SetEvent
0x180027ed6  cmp     [rsi+68h], r15d
0x180027eda  jz      short loc_180027EE4
0x180027edc  mov     rcx, rsi; this
0x180027edf  call    ?KillProcess@WORKER_PROCESS@@AEAAXXZ; WORKER_PROCESS::KillProcess(void)
0x180027ee4  mov     rcx, [rsi+0B8h]; this
0x180027eeb  test    rcx, rcx
0x180027eee  jz      short loc_180027F11
0x180027ef0  xor     edx, edx; int
0x180027ef2  call    ?StartShutdown@WORKER_PROCESS@@QEAAXH@Z; WORKER_PROCESS::StartShutdown(int)
0x180027ef7  mov     rcx, [rsi+0B8h]
0x180027efe  mov     rax, [rcx]
0x180027f01  mov     rax, [rax+8]
0x180027f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f0a  mov     [rsi+0B8h], r15
0x180027f11  lea     rcx, [rsi+108h]; this
0x180027f18  call    ?Terminate@REQUEST_QUEUE_INSTANCE_TABLE@@QEAAXXZ; REQUEST_QUEUE_INSTANCE_TABLE::Terminate(void)
0x180027f1d  cmp     [rsi+4Ch], r15d
0x180027f21  jz      loc_180027FB7
0x180027f27  mov     rbx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180027f2e  mov     rdx, rsi
0x180027f31  lea     rcx, [rbx+1C0h]
0x180027f38  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x180027f3e  test    eax, eax
0x180027f40  jnz     short loc_180027FAD
0x180027f42  mov     rax, [rsi]
0x180027f45  mov     rcx, rsi
0x180027f48  mov     rax, [rax+8]
0x180027f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f51  mov     eax, cs:g_dwDebugFlags
0x180027f57  test    al, 3
0x180027f59  setnz   dl
0x180027f5c  test    eax, 30000h
0x180027f61  setnz   al
0x180027f64  test    al, dl
0x180027f66  jz      short loc_180027FAD
0x180027f68  lea     rcx, [rbx+1C0h]
0x180027f6f  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180027f75  mov     rcx, cs:g_pDebug
0x180027f7c  lea     r9, aUlAndWorkerMan_9; "UL_AND_WORKER_MANAGER::StopTrackingWork"...
0x180027f83  mov     [rsp+78h+var_48], eax
0x180027f87  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180027f8e  mov     eax, [rsi+4Ch]
0x180027f91  mov     r8d, 6EEh
0x180027f97  mov     dword ptr [rsp+78h+var_50], eax
0x180027f9b  lea     rax, aWorkerProcessL; "Worker Process: %lu removed from hashta"...
0x180027fa2  mov     [rsp+78h+var_58], rax
0x180027fa7  call    cs:__imp_PuDbgPrint
0x180027fad  mov     rax, [rsi+38h]
0x180027fb1  dec     dword ptr [rax+80h]
0x180027fb7  mov     rbx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180027fbe  call    cs:__imp_GetTickCount
0x180027fc4  mov     rdi, [rbx+738h]
0x180027fcb  mov     ebp, eax
0x180027fcd  test    rdi, rdi
0x180027fd0  jz      short loc_180028030
0x180027fd2  mov     ebx, [rsi+80h]
0x180027fd8  lea     rcx, [rdi+50h]; lpCriticalSection
0x180027fdc  call    cs:__imp_EnterCriticalSection
0x180027fe2  sub     ebp, ebx
0x180027fe4  jnz     short loc_180027FEB
0x180027fe6  mov     edx, r15d
0x180027fe9  jmp     short loc_180028004
0x180027feb  cmp     ebp, 0EA60h
0x180027ff1  ja      short loc_180027FFA
0x180027ff3  mov     edx, 1
0x180027ff8  jmp     short loc_180028004
0x180027ffa  mov     eax, 45E7B273h
0x180027fff  mul     ebp
0x180028001  shr     edx, 0Eh
0x180028004  add     [rdi+28h], edx
0x180028007  inc     dword ptr [rdi+2Ch]
0x18002800a  cmp     [rdi+1Ch], r15d
0x18002800e  jz      short loc_180028015
0x180028010  cmp     ebp, [rdi+1Ch]
0x180028013  jbe     short loc_180028018
0x180028015  mov     [rdi+1Ch], ebp
0x180028018  cmp     [rdi+20h], r15d
0x18002801c  jz      short loc_180028023
0x18002801e  cmp     ebp, [rdi+20h]
0x180028021  jnb     short loc_180028026
0x180028023  mov     [rdi+20h], ebp
0x180028026  lea     rcx, [rdi+50h]; lpCriticalSection
0x18002802a  call    cs:__imp_LeaveCriticalSection
0x180028030  mov     rcx, [rsi+38h]; this
0x180028034  mov     rdx, rsi; struct WORKER_PROCESS *
0x180028037  call    ?RemoveWorkerProcessFromList@APP_POOL@@QEAAXPEAVWORKER_PROCESS@@@Z; APP_POOL::RemoveWorkerProcessFromList(WORKER_PROCESS *)
0x18002803c  add     rsp, 48h
0x180028040  pop     r15
0x180028042  pop     r14
0x180028044  pop     rdi
0x180028045  pop     rsi
0x180028046  pop     rbp
0x180028047  pop     rbx
0x180028048  retn
```
