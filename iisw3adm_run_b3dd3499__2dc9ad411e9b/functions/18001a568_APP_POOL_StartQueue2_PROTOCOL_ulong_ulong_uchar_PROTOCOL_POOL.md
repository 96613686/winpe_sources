# APP_POOL::StartQueue2(PROTOCOL *,ulong,ulong,uchar *,PROTOCOL_POOL *)

- ea: `0x18001a568`
- end: `0x18001a912`
- name: `?StartQueue2@APP_POOL@@QEAAJPEAVPROTOCOL@@KKPEAEPEAVPROTOCOL_POOL@@@Z`
- size: `938`
- prototype: `__int64 __fastcall(APP_POOL *__hidden this, struct PROTOCOL *, unsigned int, unsigned int, unsigned __int8 *, struct PROTOCOL_POOL *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016c7c`
- `0x18001a918`

## callees

- `0x180001234`
- `0x180017040`
- `0x180017e3c`
- `0x18001889c`
- `0x18001a568`
- `0x180023064`
- `0x18003e208`
- `0x18003e7f8`
- `0x18003e918`
- `0x18003e94c`
- `0x18003e9e0`
- `0x180062010`

## import_xrefs

- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18001a7f2`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18001a7f2`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18001a6be`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18001a6be`
- `iisutil!PuDbgPrint` at `0x18001a5f5`
- `iisutil!PuDbgPrint` at `0x18001a8c8`
- `iisutil!PuDbgPrint` at `0x18001a5f5`
- `iisutil!PuDbgPrint` at `0x18001a8c8`
- `iisutil!PuDbgPrintError` at `0x18001a6a6`
- `iisutil!PuDbgPrintError` at `0x18001a704`
- `iisutil!PuDbgPrintError` at `0x18001a77f`
- `iisutil!PuDbgPrintError` at `0x18001a6a6`
- `iisutil!PuDbgPrintError` at `0x18001a704`
- `iisutil!PuDbgPrintError` at `0x18001a77f`

## string_xrefs

- `0x18001a5be`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x18001a692`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x18001a6ec`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x18001a767`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x18001a8a5`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x18001a897`: `APP_POOL::CreateWorkerProcessIfOk`
- `0x18001a5e6`: `Start queue received for app pool (ptr: %p, name: '%ws', protocol '%ws', queueid: %d )\n`

## pseudocode

```c
__int64 __fastcall APP_POOL::StartQueue2(
        APP_POOL *this,
        const unsigned __int16 **a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5,
        struct PROTOCOL_POOL *a6)
{
  int WorkerProcess; // edi
  const unsigned __int16 **v11; // rbx
  REQUEST_QUEUE_DATA *RequestQueueData; // rbx
  REQUEST_QUEUE_DATA *v13; // rax
  int v14; // r14d
  APP_POOL *v15; // rax
  APP_POOL *v16; // r12
  WORKER_PROCESS *v17; // rbp
  REQUEST_QUEUE_INSTANCE *v18; // r14
  REQUEST_QUEUE_INSTANCE *v20; // [rsp+A8h] [rbp+10h] BYREF

  WorkerProcess = 0;
  if ( !a2 )
  {
    RequestQueueData = 0;
    goto LABEL_22;
  }
  v11 = a2 + 19;
  if ( (g_dwDebugFlags & 0x410000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
      6031,
      "APP_POOL::StartQueue2",
      "Start queue received for app pool (ptr: %p, name: '%ws', protocol '%ws', queueid: %d )\n",
      this,
      *((_QWORD *)this + 7),
      *v11,
      a3);
  RequestQueueData = APP_POOL::FindRequestQueueData(this, *v11, a3);
  if ( RequestQueueData )
  {
LABEL_15:
    if ( *((_DWORD *)RequestQueueData + 47) == 1 || !*((_DWORD *)RequestQueueData + 45) )
      return 0;
    *((_DWORD *)RequestQueueData + 45) = 0;
    _InterlockedAdd((volatile signed __int32 *)RequestQueueData + 3, 1u);
    ++*((_DWORD *)RequestQueueData + 26);
LABEL_22:
    if ( *((_DWORD *)this + 5) == 3 )
    {
      if ( a2 )
      {
        v14 = 0;
        v15 = (APP_POOL *)*((_QWORD *)this + 13);
        if ( v15 != (APP_POOL *)((char *)this + 104) )
        {
          while ( !v14 )
          {
            v16 = *(APP_POOL **)v15;
            v17 = (APP_POOL *)((char *)v15 - 16);
            if ( !*((_DWORD *)v15 + 24) )
            {
              v20 = 0;
              if ( (unsigned int)CLKRHashTable::FindKey((char *)v17 + 272, (char *)RequestQueueData + 24, &v20) == 2
                && (int)WORKER_PROCESS::CreateRequestQueueInstance(v17, RequestQueueData, &v20) >= 0 )
              {
                v18 = v20;
                if ( (unsigned int)(*((_DWORD *)v17 + 12) - 5) <= 1 )
                  REQUEST_QUEUE_INSTANCE::SendStartQueueInfo(v20);
                (*(void (__fastcall **)(REQUEST_QUEUE_INSTANCE *))(*(_QWORD *)v18 + 8LL))(v18);
                v14 = 1;
              }
            }
            v15 = v16;
            if ( v16 == (APP_POOL *)((char *)this + 104) )
            {
              if ( v14 )
                goto LABEL_40;
              goto LABEL_34;
            }
          }
          goto LABEL_40;
        }
      }
LABEL_34:
      if ( !APP_POOL::IsOkToCreateWorkerProcess(this, 1) )
        goto LABEL_38;
      if ( (g_dwDebugFlags & 0x410000) != 0 && (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
          3783,
          "APP_POOL::CreateWorkerProcessIfOk",
          "Demand start request received for app pool (ptr: %p; id: %S); creating worker process\n",
          this,
          *((const wchar_t **)this + 7));
      WorkerProcess = APP_POOL::CreateWorkerProcess(this, 1, 0, RequestQueueData);
      if ( WorkerProcess < 0 )
LABEL_38:
        WorkerProcess = 0;
    }
    if ( !a2 )
      return (unsigned int)WorkerProcess;
LABEL_40:
    --*((_DWORD *)RequestQueueData + 26);
    REQUEST_QUEUE_DATA::CheckIfShouldTerminate(RequestQueueData);
LABEL_41:
    REQUEST_QUEUE_DATA::Dereference(RequestQueueData);
    return (unsigned int)WorkerProcess;
  }
  v13 = (REQUEST_QUEUE_DATA *)operator new(0xF0u);
  if ( v13 )
  {
    RequestQueueData = REQUEST_QUEUE_DATA::REQUEST_QUEUE_DATA(v13);
    if ( RequestQueueData )
    {
      WorkerProcess = REQUEST_QUEUE_DATA::Initialize(RequestQueueData, a2, a3, a4, a5, this, a6);
      if ( WorkerProcess < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
            6079,
            "APP_POOL::StartQueue2",
            WorkerProcess,
            "Initializing a Request Queue Data failed\n");
        goto LABEL_41;
      }
      if ( (unsigned int)CLKRHashTable::InsertRecord((char *)this + 240, RequestQueueData, 0) )
      {
        REQUEST_QUEUE_DATA::CheckIfShouldTerminate(RequestQueueData);
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
            6100,
            "APP_POOL::StartQueue2",
            -2147467259,
            "Inserting request queue into hashtable failed\n");
        return (unsigned int)-2147467259;
      }
      *((_DWORD *)RequestQueueData + 58) = 1;
      goto LABEL_15;
    }
  }
  WorkerProcess = -2147024882;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
      6062,
      "APP_POOL::StartQueue2",
      -2147024882,
      "Creating a Request Queue Data failed\n");
  return (unsigned int)WorkerProcess;
}

```

## disassembly

```asm
0x18001a568  mov     r11, rsp
0x18001a56b  push    rbx
0x18001a56c  push    rbp
0x18001a56d  push    rsi
0x18001a56e  push    rdi
0x18001a56f  push    r12
0x18001a571  push    r13
0x18001a573  push    r14
0x18001a575  push    r15
0x18001a577  sub     rsp, 58h
0x18001a57b  xor     edi, edi
0x18001a57d  mov     r14d, r9d
0x18001a580  mov     ebp, r8d
0x18001a583  mov     r13, rdx
0x18001a586  mov     rsi, rcx
0x18001a589  lea     r12d, [rdi+1]
0x18001a58d  test    rdx, rdx
0x18001a590  jz      loc_18001A791
0x18001a596  mov     eax, cs:g_dwDebugFlags
0x18001a59c  lea     rbx, [rdx+98h]
0x18001a5a3  test    eax, 410000h
0x18001a5a8  lea     r15, aAppPoolStartqu; "APP_POOL::StartQueue2"
0x18001a5af  setnz   cl
0x18001a5b2  test    al, 3
0x18001a5b4  setnz   al
0x18001a5b7  test    al, cl
0x18001a5b9  jz      short loc_18001A5FB
0x18001a5bb  mov     rax, [rbx]
0x18001a5be  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001a5c5  mov     rcx, cs:g_pDebug
0x18001a5cc  mov     r9, r15
0x18001a5cf  mov     [rsp+98h+var_58], r8d
0x18001a5d4  mov     r8d, 178Fh
0x18001a5da  mov     [r11-60h], rax
0x18001a5de  mov     rax, [rsi+38h]
0x18001a5e2  mov     [r11-68h], rax
0x18001a5e6  lea     rax, aStartQueueRece; "Start queue received for app pool (ptr:"...
0x18001a5ed  mov     [r11-70h], rsi
0x18001a5f1  mov     [r11-78h], rax
0x18001a5f5  call    cs:__imp_PuDbgPrint
0x18001a5fb  mov     rdx, [rbx]; unsigned __int16 *
0x18001a5fe  mov     r8d, ebp; unsigned int
0x18001a601  mov     rcx, rsi; this
0x18001a604  call    ?FindRequestQueueData@APP_POOL@@QEAAPEAVREQUEST_QUEUE_DATA@@PEBGK@Z; APP_POOL::FindRequestQueueData(ushort const *,ulong)
0x18001a609  mov     rbx, rax
0x18001a60c  test    rax, rax
0x18001a60f  jnz     loc_18001A71B
0x18001a615  mov     ecx, 0F0h; Size
0x18001a61a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a61f  test    rax, rax
0x18001a622  jz      loc_18001A742
0x18001a628  mov     rcx, rax; this
0x18001a62b  call    ??0REQUEST_QUEUE_DATA@@QEAA@XZ; REQUEST_QUEUE_DATA::REQUEST_QUEUE_DATA(void)
0x18001a630  mov     rbx, rax
0x18001a633  test    rax, rax
0x18001a636  jz      loc_18001A742
0x18001a63c  mov     rax, [rsp+98h+arg_28]
0x18001a644  mov     r9d, r14d; unsigned int
0x18001a647  mov     [rsp+98h+var_68], rax; struct PROTOCOL_POOL *
0x18001a64c  mov     r8d, ebp; unsigned int
0x18001a64f  mov     rax, [rsp+98h+arg_20]
0x18001a657  mov     rdx, r13; struct PROTOCOL *
0x18001a65a  mov     [rsp+98h+var_70], rsi; struct APP_POOL *
0x18001a65f  mov     rcx, rbx; this
0x18001a662  mov     [rsp+98h+var_78], rax; unsigned __int8 *
0x18001a667  call    ?Initialize@REQUEST_QUEUE_DATA@@QEAAJPEAVPROTOCOL@@KKPEAEPEAVAPP_POOL@@PEAVPROTOCOL_POOL@@@Z; REQUEST_QUEUE_DATA::Initialize(PROTOCOL *,ulong,ulong,uchar *,APP_POOL *,PROTOCOL_POOL *)
0x18001a66c  mov     edi, eax
0x18001a66e  test    eax, eax
0x18001a670  jns     short loc_18001A6B1
0x18001a672  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001a679  jz      loc_18001A8F7
0x18001a67f  mov     rcx, cs:g_pDebug
0x18001a686  lea     rax, aInitializingAR; "Initializing a Request Queue Data faile"...
0x18001a68d  mov     [rsp+98h+var_70], rax
0x18001a692  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001a699  mov     r9, r15
0x18001a69c  mov     dword ptr [rsp+98h+var_78], edi
0x18001a6a0  mov     r8d, 17BFh
0x18001a6a6  call    cs:__imp_PuDbgPrintError
0x18001a6ac  jmp     loc_18001A8F7
0x18001a6b1  lea     rcx, [rsi+0F0h]
0x18001a6b8  xor     r8d, r8d
0x18001a6bb  mov     rdx, rbx
0x18001a6be  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18001a6c4  test    eax, eax
0x18001a6c6  jz      short loc_18001A714
0x18001a6c8  mov     rcx, rbx; this
0x18001a6cb  call    ?CheckIfShouldTerminate@REQUEST_QUEUE_DATA@@QEAAXXZ; REQUEST_QUEUE_DATA::CheckIfShouldTerminate(void)
0x18001a6d0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001a6d7  jz      short loc_18001A70A
0x18001a6d9  mov     rcx, cs:g_pDebug
0x18001a6e0  lea     rax, aInsertingReque_0; "Inserting request queue into hashtable "...
0x18001a6e7  mov     [rsp+98h+var_70], rax
0x18001a6ec  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001a6f3  mov     r9, r15
0x18001a6f6  mov     dword ptr [rsp+98h+var_78], 80004005h
0x18001a6fe  mov     r8d, 17D4h
0x18001a704  call    cs:__imp_PuDbgPrintError
0x18001a70a  mov     edi, 80004005h
0x18001a70f  jmp     loc_18001A8FF
0x18001a714  mov     [rbx+0E8h], r12d
0x18001a71b  cmp     [rbx+0BCh], r12d
0x18001a722  jz      short loc_18001A78A
0x18001a724  cmp     dword ptr [rbx+0B4h], 0
0x18001a72b  jz      short loc_18001A78A
0x18001a72d  mov     dword ptr [rbx+0B4h], 0
0x18001a737  lock add [rbx+0Ch], r12d
0x18001a73c  add     [rbx+68h], r12d
0x18001a740  jmp     short loc_18001A793
0x18001a742  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001a749  mov     edi, 8007000Eh
0x18001a74e  jz      loc_18001A8FF
0x18001a754  mov     rcx, cs:g_pDebug
0x18001a75b  lea     rax, aCreatingAReque; "Creating a Request Queue Data failed\n"
0x18001a762  mov     [rsp+98h+var_70], rax
0x18001a767  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001a76e  mov     r9, r15
0x18001a771  mov     dword ptr [rsp+98h+var_78], 8007000Eh
0x18001a779  mov     r8d, 17AEh
0x18001a77f  call    cs:__imp_PuDbgPrintError
0x18001a785  jmp     loc_18001A8FF
0x18001a78a  xor     edi, edi
0x18001a78c  jmp     loc_18001A8FF
0x18001a791  xor     ebx, ebx
0x18001a793  cmp     dword ptr [rsi+14h], 3
0x18001a797  jnz     loc_18001A8E7
0x18001a79d  test    r13, r13
0x18001a7a0  jz      loc_18001A86D
0x18001a7a6  lea     r15, [rsi+68h]
0x18001a7aa  xor     r14d, r14d
0x18001a7ad  mov     rax, [r15]
0x18001a7b0  cmp     rax, r15
0x18001a7b3  jz      loc_18001A86D
0x18001a7b9  test    r14d, r14d
0x18001a7bc  jnz     loc_18001A8EC
0x18001a7c2  mov     r12, [rax]
0x18001a7c5  lea     rbp, [rax-10h]
0x18001a7c9  cmp     [rbp+70h], r14d
0x18001a7cd  jnz     loc_18001A854
0x18001a7d3  lea     rdx, [rbx+18h]
0x18001a7d7  mov     [rsp+98h+arg_8], 0
0x18001a7e3  lea     rcx, [rbp+110h]
0x18001a7ea  lea     r8, [rsp+98h+arg_8]
0x18001a7f2  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18001a7f8  mov     rcx, [rsp+98h+arg_8]
0x18001a800  mov     [rsp+98h+arg_8], rcx
0x18001a808  cmp     eax, 2
0x18001a80b  jnz     short loc_18001A854
0x18001a80d  lea     r8, [rsp+98h+arg_8]; struct REQUEST_QUEUE_INSTANCE **
0x18001a815  mov     rdx, rbx; struct REQUEST_QUEUE_DATA *
0x18001a818  mov     rcx, rbp; this
0x18001a81b  call    ?CreateRequestQueueInstance@WORKER_PROCESS@@QEAAJPEAVREQUEST_QUEUE_DATA@@PEAPEAVREQUEST_QUEUE_INSTANCE@@@Z; WORKER_PROCESS::CreateRequestQueueInstance(REQUEST_QUEUE_DATA *,REQUEST_QUEUE_INSTANCE * *)
0x18001a820  test    eax, eax
0x18001a822  js      short loc_18001A854
0x18001a824  mov     eax, [rbp+30h]
0x18001a827  mov     r14, [rsp+98h+arg_8]
0x18001a82f  sub     eax, 5
0x18001a832  cmp     eax, 1
0x18001a835  ja      short loc_18001A83F
0x18001a837  mov     rcx, r14; this
0x18001a83a  call    ?SendStartQueueInfo@REQUEST_QUEUE_INSTANCE@@QEAAXXZ; REQUEST_QUEUE_INSTANCE::SendStartQueueInfo(void)
0x18001a83f  mov     rax, [r14]
0x18001a842  mov     rcx, r14
0x18001a845  mov     rax, [rax+8]
0x18001a849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a84e  mov     r14d, 1
0x18001a854  mov     rax, r12
0x18001a857  cmp     r12, r15
0x18001a85a  jnz     loc_18001A7B9
0x18001a860  test    r14d, r14d
0x18001a863  jnz     loc_18001A8EC
0x18001a869  lea     r12d, [r14+1]
0x18001a86d  mov     edx, r12d; int
0x18001a870  mov     rcx, rsi; this
0x18001a873  call    ?IsOkToCreateWorkerProcess@APP_POOL@@QEAAHH@Z; APP_POOL::IsOkToCreateWorkerProcess(int)
0x18001a878  test    eax, eax
0x18001a87a  jz      short loc_18001A8E5
0x18001a87c  mov     eax, cs:g_dwDebugFlags
0x18001a882  test    eax, 410000h
0x18001a887  setnz   cl
0x18001a88a  test    al, 3
0x18001a88c  setnz   al
0x18001a88f  test    al, cl
0x18001a891  jz      short loc_18001A8CE
0x18001a893  mov     rax, [rsi+38h]
0x18001a897  lea     r9, aAppPoolCreatew; "APP_POOL::CreateWorkerProcessIfOk"
0x18001a89e  mov     rcx, cs:g_pDebug
0x18001a8a5  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001a8ac  mov     [rsp+98h+var_68], rax
0x18001a8b1  mov     r8d, 0EC7h
0x18001a8b7  lea     rax, aDemandStartReq; "Demand start request received for app p"...
0x18001a8be  mov     [rsp+98h+var_70], rsi
0x18001a8c3  mov     [rsp+98h+var_78], rax
0x18001a8c8  call    cs:__imp_PuDbgPrint
0x18001a8ce  mov     r9, rbx
0x18001a8d1  xor     r8d, r8d
0x18001a8d4  mov     edx, r12d
0x18001a8d7  mov     rcx, rsi
0x18001a8da  call    ?CreateWorkerProcess@APP_POOL@@AEAAJW4WORKER_PROCESS_START_REASON@@PEAVWORKER_PROCESS@@PEAVREQUEST_QUEUE_DATA@@@Z; APP_POOL::CreateWorkerProcess(WORKER_PROCESS_START_REASON,WORKER_PROCESS *,REQUEST_QUEUE_DATA *)
0x18001a8df  mov     edi, eax
0x18001a8e1  test    eax, eax
0x18001a8e3  jns     short loc_18001A8E7
0x18001a8e5  xor     edi, edi
0x18001a8e7  test    r13, r13
0x18001a8ea  jz      short loc_18001A8FF
0x18001a8ec  dec     dword ptr [rbx+68h]
0x18001a8ef  mov     rcx, rbx; this
0x18001a8f2  call    ?CheckIfShouldTerminate@REQUEST_QUEUE_DATA@@QEAAXXZ; REQUEST_QUEUE_DATA::CheckIfShouldTerminate(void)
0x18001a8f7  mov     rcx, rbx; this
0x18001a8fa  call    ?Dereference@REQUEST_QUEUE_DATA@@QEAAXXZ; REQUEST_QUEUE_DATA::Dereference(void)
0x18001a8ff  mov     eax, edi
0x18001a901  add     rsp, 58h
0x18001a905  pop     r15
0x18001a907  pop     r14
0x18001a909  pop     r13
0x18001a90b  pop     r12
0x18001a90d  pop     rdi
0x18001a90e  pop     rsi
0x18001a90f  pop     rbp
0x18001a910  pop     rbx
0x18001a911  retn
```
