# WEB_ADMIN_SERVICE::ProcessMainQueueDuringShutdown(void)

- ea: `0x180005b60`
- end: `0x180005ced`
- name: `?ProcessMainQueueDuringShutdown@WEB_ADMIN_SERVICE@@QEAAXXZ`
- size: `397`
- prototype: `void __fastcall(WEB_ADMIN_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012ac4`

## callees

- `0x1800041f4`
- `0x180004290`
- `0x180005b60`
- `0x1800076e0`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180005bae`
- `iisutil!PuDbgPrint` at `0x180005c9b`
- `iisutil!PuDbgPrint` at `0x180005bae`
- `iisutil!PuDbgPrint` at `0x180005c9b`
- `iisutil!PuDbgPrintError` at `0x180005c50`
- `iisutil!PuDbgPrintError` at `0x180005cdd`
- `iisutil!PuDbgPrintError` at `0x180005c50`
- `iisutil!PuDbgPrintError` at `0x180005cdd`

## string_xrefs

- `0x180005b70`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180005c3b`: `WEB_ADMIN_SERVICE::ProcessMainQueueDuringShutdown`
- `0x180005b92`: `Beginning shutdown protocol terminate timer\n`
- `0x180005b99`: `WEB_ADMIN_SERVICE::BeginShutdownProtocolTerminateTimer`
- `0x180005bfb`: `WEB_ADMIN_SERVICE::BeginShutdownProtocolTerminateTimer`
- `0x180005bee`: `Could not create shutdown protocol terminate timer\n`
- `0x180005c7f`: `Canceling shutdown protocol terminate timer\n`
- `0x180005c86`: `WEB_ADMIN_SERVICE::CancelShutdownProtocolTerminateTimer`
- `0x180005cc3`: `WEB_ADMIN_SERVICE::CancelShutdownProtocolTerminateTimer`
- `0x180005cb6`: `Could not cancel shutdown protocol terminate timer\n`

## pseudocode

```c
void __fastcall WEB_ADMIN_SERVICE::ProcessMainQueueDuringShutdown(struct _TP_TIMER **this)
{
  int v2; // eax
  int v3; // eax
  WEB_ADMIN_SERVICE *v4; // rcx
  int v5; // edx
  int v6; // eax

  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x30000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
      3560,
      "WEB_ADMIN_SERVICE::BeginShutdownProtocolTerminateTimer",
      "Beginning shutdown protocol terminate timer\n");
  v2 = WEB_ADMIN_SERVICE::BeginTimer(
         (WEB_ADMIN_SERVICE *)this,
         this + 203,
         ShutdownProtocolTerminateTimerCallback,
         0xEA60u,
         0,
         this);
  if ( v2 >= 0 )
  {
    *((_DWORD *)this + 292) = 0;
    do
    {
      v3 = WORK_QUEUE::ProcessWorkItem((WORK_QUEUE *)(this + 2));
      v5 = g_dwDebugFlags;
      if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
          1286,
          "WEB_ADMIN_SERVICE::ProcessMainQueueDuringShutdown",
          v3,
          "Processing work item failed\n");
        v5 = g_dwDebugFlags;
      }
    }
    while ( !*((_DWORD *)this + 292) );
    LOBYTE(v4) = (v5 & 3) != 0;
    if ( ((unsigned __int8)v4 & ((v5 & 0x30000) != 0)) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        3612,
        "WEB_ADMIN_SERVICE::CancelShutdownProtocolTerminateTimer",
        "Canceling shutdown protocol terminate timer\n");
    v6 = WEB_ADMIN_SERVICE::CancelTimer(v4, this + 203);
    if ( v6 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        3622,
        "WEB_ADMIN_SERVICE::CancelShutdownProtocolTerminateTimer",
        v6,
        "Could not cancel shutdown protocol terminate timer\n");
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
      3574,
      "WEB_ADMIN_SERVICE::BeginShutdownProtocolTerminateTimer",
      v2,
      "Could not create shutdown protocol terminate timer\n");
  }
}

```

## disassembly

```asm
0x180005b60  push    rbx
0x180005b62  push    rsi
0x180005b63  push    rdi
0x180005b64  push    r14
0x180005b66  sub     rsp, 38h
0x180005b6a  mov     eax, cs:g_dwDebugFlags
0x180005b70  lea     r14, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005b77  test    al, 3
0x180005b79  mov     rbx, rcx
0x180005b7c  setnz   dl
0x180005b7f  test    eax, 30000h
0x180005b84  setnz   al
0x180005b87  test    al, dl
0x180005b89  jz      short loc_180005BB4
0x180005b8b  mov     rcx, cs:g_pDebug
0x180005b92  lea     rax, aBeginningShutd_0; "Beginning shutdown protocol terminate t"...
0x180005b99  lea     r9, aWebAdminServic_25; "WEB_ADMIN_SERVICE::BeginShutdownProtoco"...
0x180005ba0  mov     qword ptr [rsp+58h+var_38], rax
0x180005ba5  mov     r8d, 0DE8h
0x180005bab  mov     rdx, r14
0x180005bae  call    cs:__imp_PuDbgPrint
0x180005bb4  lea     rdi, [rbx+658h]
0x180005bbb  mov     [rsp+58h+var_30], rbx; void *
0x180005bc0  mov     rdx, rdi; struct _TP_TIMER **
0x180005bc3  mov     [rsp+58h+var_38], 0; int
0x180005bcb  mov     r9d, 0EA60h; unsigned int
0x180005bd1  lea     r8, ?ShutdownProtocolTerminateTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *)
0x180005bd8  call    ?BeginTimer@WEB_ADMIN_SERVICE@@QEAAJPEAPEAU_TP_TIMER@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU2@@ZKH2@Z; WEB_ADMIN_SERVICE::BeginTimer(_TP_TIMER * *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *),ulong,int,void *)
0x180005bdd  test    eax, eax
0x180005bdf  jns     short loc_180005C07
0x180005be1  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005be8  jz      loc_180005CE3
0x180005bee  lea     rcx, aCouldNotCreate_4; "Could not create shutdown protocol term"...
0x180005bf5  mov     r8d, 0DF6h
0x180005bfb  lea     r9, aWebAdminServic_25; "WEB_ADMIN_SERVICE::BeginShutdownProtoco"...
0x180005c02  jmp     loc_180005CCA
0x180005c07  mov     dword ptr [rbx+490h], 0
0x180005c11  lea     rcx, [rbx+10h]; this
0x180005c15  call    ?ProcessWorkItem@WORK_QUEUE@@QEAAJXZ; WORK_QUEUE::ProcessWorkItem(void)
0x180005c1a  mov     edx, cs:g_dwDebugFlags
0x180005c20  test    eax, eax
0x180005c22  jns     short loc_180005C5C
0x180005c24  test    dl, 0Fh
0x180005c27  jz      short loc_180005C5C
0x180005c29  lea     rcx, aProcessingWork; "Processing work item failed\n"
0x180005c30  mov     r8d, 506h
0x180005c36  mov     [rsp+58h+var_30], rcx
0x180005c3b  lea     r9, aWebAdminServic_3; "WEB_ADMIN_SERVICE::ProcessMainQueueDuri"...
0x180005c42  mov     rcx, cs:g_pDebug
0x180005c49  mov     rdx, r14
0x180005c4c  mov     [rsp+58h+var_38], eax
0x180005c50  call    cs:__imp_PuDbgPrintError
0x180005c56  mov     edx, cs:g_dwDebugFlags
0x180005c5c  cmp     dword ptr [rbx+490h], 0
0x180005c63  jz      short loc_180005C11
0x180005c65  test    dl, 3
0x180005c68  setnz   cl
0x180005c6b  test    edx, 30000h
0x180005c71  setnz   al
0x180005c74  test    al, cl
0x180005c76  jz      short loc_180005CA1
0x180005c78  mov     rcx, cs:g_pDebug
0x180005c7f  lea     rax, aCancelingShutd; "Canceling shutdown protocol terminate t"...
0x180005c86  lea     r9, aWebAdminServic_12; "WEB_ADMIN_SERVICE::CancelShutdownProtoc"...
0x180005c8d  mov     qword ptr [rsp+58h+var_38], rax
0x180005c92  mov     r8d, 0E1Ch
0x180005c98  mov     rdx, r14
0x180005c9b  call    cs:__imp_PuDbgPrint
0x180005ca1  mov     rdx, rdi; struct _TP_TIMER **
0x180005ca4  call    ?CancelTimer@WEB_ADMIN_SERVICE@@QEAAJPEAPEAU_TP_TIMER@@@Z; WEB_ADMIN_SERVICE::CancelTimer(_TP_TIMER * *)
0x180005ca9  test    eax, eax
0x180005cab  jns     short loc_180005CE3
0x180005cad  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005cb4  jz      short loc_180005CE3
0x180005cb6  lea     rcx, aCouldNotCancel_0; "Could not cancel shutdown protocol term"...
0x180005cbd  mov     r8d, 0E26h
0x180005cc3  lea     r9, aWebAdminServic_12; "WEB_ADMIN_SERVICE::CancelShutdownProtoc"...
0x180005cca  mov     [rsp+58h+var_30], rcx
0x180005ccf  mov     rdx, r14
0x180005cd2  mov     rcx, cs:g_pDebug
0x180005cd9  mov     [rsp+58h+var_38], eax
0x180005cdd  call    cs:__imp_PuDbgPrintError
0x180005ce3  add     rsp, 38h
0x180005ce7  pop     r14
0x180005ce9  pop     rdi
0x180005cea  pop     rsi
0x180005ceb  pop     rbx
0x180005cec  retn
```
