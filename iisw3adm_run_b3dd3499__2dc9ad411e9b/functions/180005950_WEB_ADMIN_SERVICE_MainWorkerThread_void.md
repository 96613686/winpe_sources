# WEB_ADMIN_SERVICE::MainWorkerThread(void)

- ea: `0x180005950`
- end: `0x180005aa3`
- name: `?MainWorkerThread@WEB_ADMIN_SERVICE@@AEAAJXZ`
- size: `339`
- prototype: `__int64 __fastcall(WEB_ADMIN_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180004b80`

## callees

- `0x180005950`
- `0x1800076e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005964`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005964`
- `iisutil!PuDbgPrint` at `0x180005a8b`
- `iisutil!PuDbgPrint` at `0x180005a8b`
- `iisutil!PuDbgPrintError` at `0x1800059bf`
- `iisutil!PuDbgPrintError` at `0x180005a3a`
- `iisutil!PuDbgPrintError` at `0x1800059bf`
- `iisutil!PuDbgPrintError` at `0x180005a3a`

## string_xrefs

- `0x1800059b8`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180005a33`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180005a84`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x1800059a7`: `WEB_ADMIN_SERVICE::MainWorkerThread`
- `0x180005a2c`: `WEB_ADMIN_SERVICE::MainWorkerThread`
- `0x180005a72`: `WEB_ADMIN_SERVICE::MainWorkerThread`
- `0x1800059d8`: `Exiting main work loop due to error on main worker thread\n`
- `0x180005a0f`: `Exiting main work loop due to error on secondary thread\n`
- `0x180005a6b`: `Main worker thread has exited it's work loop\n`

## pseudocode

```c
__int64 __fastcall WEB_ADMIN_SERVICE::MainWorkerThread(WEB_ADMIN_SERVICE *this)
{
  int v2; // edi
  bool v3; // zf
  int v4; // eax

  v2 = 0;
  *((_DWORD *)this + 293) = GetCurrentThreadId();
  while ( !*((_DWORD *)this + 292) )
  {
    v2 = WORK_QUEUE::ProcessWorkItem((WEB_ADMIN_SERVICE *)((char *)this + 16));
    if ( v2 >= 0 )
    {
      v4 = *((_DWORD *)this + 294);
      if ( v4 < 0 )
      {
        v3 = (g_dwDebugFlags & 0xF) == 0;
        v2 = *((_DWORD *)this + 294);
        *((_DWORD *)this + 292) = 1;
        if ( !v3 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
            1221,
            "WEB_ADMIN_SERVICE::MainWorkerThread",
            v4,
            "Exiting main work loop due to error on secondary thread\n");
      }
    }
    else
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
          1173,
          "WEB_ADMIN_SERVICE::MainWorkerThread",
          v2,
          "Processing work item failed\n");
      v3 = (g_dwDebugFlags & 0xF) == 0;
      *((_DWORD *)this + 292) = 1;
      if ( !v3 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
          1186,
          "WEB_ADMIN_SERVICE::MainWorkerThread",
          v2,
          "Exiting main work loop due to error on main worker thread\n");
    }
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x30000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
      1232,
      "WEB_ADMIN_SERVICE::MainWorkerThread",
      "Main worker thread has exited it's work loop\n");
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180005950  mov     [rsp+arg_0], rbx
0x180005955  mov     [rsp+arg_8], rsi
0x18000595a  push    rdi
0x18000595b  sub     rsp, 30h
0x18000595f  mov     rbx, rcx
0x180005962  xor     edi, edi
0x180005964  call    cs:__imp_GetCurrentThreadId
0x18000596a  mov     [rbx+494h], eax
0x180005970  cmp     [rbx+490h], edi
0x180005976  jnz     loc_180005A4D
0x18000597c  lea     rcx, [rbx+10h]; this
0x180005980  call    ?ProcessWorkItem@WORK_QUEUE@@QEAAJXZ; WORK_QUEUE::ProcessWorkItem(void)
0x180005985  mov     edi, eax
0x180005987  test    eax, eax
0x180005989  jns     short loc_1800059F0
0x18000598b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005992  jz      short loc_1800059C5
0x180005994  mov     rcx, cs:g_pDebug
0x18000599b  lea     rax, aProcessingWork; "Processing work item failed\n"
0x1800059a2  mov     [rsp+38h+var_10], rax
0x1800059a7  lea     r9, aWebAdminServic_26; "WEB_ADMIN_SERVICE::MainWorkerThread"
0x1800059ae  mov     r8d, 495h
0x1800059b4  mov     dword ptr [rsp+38h+var_18], edi
0x1800059b8  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800059bf  call    cs:__imp_PuDbgPrintError
0x1800059c5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800059cc  mov     dword ptr [rbx+490h], 1
0x1800059d6  jz      short loc_180005A40
0x1800059d8  lea     rax, aExitingMainWor_0; "Exiting main work loop due to error on "...
0x1800059df  mov     r8d, 4A2h
0x1800059e5  mov     [rsp+38h+var_10], rax
0x1800059ea  mov     dword ptr [rsp+38h+var_18], edi
0x1800059ee  jmp     short loc_180005A25
0x1800059f0  mov     eax, [rbx+498h]
0x1800059f6  test    eax, eax
0x1800059f8  jns     short loc_180005A40
0x1800059fa  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005a01  mov     edi, eax
0x180005a03  mov     dword ptr [rbx+490h], 1
0x180005a0d  jz      short loc_180005A40
0x180005a0f  lea     rcx, aExitingMainWor; "Exiting main work loop due to error on "...
0x180005a16  mov     r8d, 4C5h
0x180005a1c  mov     [rsp+38h+var_10], rcx
0x180005a21  mov     dword ptr [rsp+38h+var_18], eax
0x180005a25  mov     rcx, cs:g_pDebug
0x180005a2c  lea     r9, aWebAdminServic_26; "WEB_ADMIN_SERVICE::MainWorkerThread"
0x180005a33  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005a3a  call    cs:__imp_PuDbgPrintError
0x180005a40  cmp     dword ptr [rbx+490h], 0
0x180005a47  jz      loc_18000597C
0x180005a4d  mov     eax, cs:g_dwDebugFlags
0x180005a53  test    al, 3
0x180005a55  setnz   cl
0x180005a58  test    eax, 30000h
0x180005a5d  setnz   al
0x180005a60  test    al, cl
0x180005a62  jz      short loc_180005A91
0x180005a64  mov     rcx, cs:g_pDebug
0x180005a6b  lea     rax, aMainWorkerThre; "Main worker thread has exited it's work"...
0x180005a72  lea     r9, aWebAdminServic_26; "WEB_ADMIN_SERVICE::MainWorkerThread"
0x180005a79  mov     [rsp+38h+var_18], rax
0x180005a7e  mov     r8d, 4D0h
0x180005a84  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005a8b  call    cs:__imp_PuDbgPrint
0x180005a91  mov     rbx, [rsp+38h+arg_0]
0x180005a96  mov     eax, edi
0x180005a98  mov     rsi, [rsp+38h+arg_8]
0x180005a9d  add     rsp, 30h
0x180005aa1  pop     rdi
0x180005aa2  retn
```
