# UpdateW3SVCPendingServiceStatusCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800543d0`
- end: `0x18005452f`
- name: `?UpdateW3SVCPendingServiceStatusCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `351`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180054190`
- `0x1800543d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800544e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800544e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800543e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800543e8`
- `iisutil!PuDbgPrint` at `0x180054445`
- `iisutil!PuDbgPrint` at `0x1800544d7`
- `iisutil!PuDbgPrint` at `0x180054445`
- `iisutil!PuDbgPrint` at `0x1800544d7`
- `iisutil!PuDbgPrintError` at `0x180054491`
- `iisutil!PuDbgPrintError` at `0x18005451e`
- `iisutil!PuDbgPrintError` at `0x180054491`
- `iisutil!PuDbgPrintError` at `0x18005451e`

## string_xrefs

- `0x18005441e`: `Updating the service state checkpoint to: %lu\n`
- `0x18005446d`: `Could not report service status\n`
- `0x1800544b0`: `Ignoring pending service status timer, not in pending state. State: %lu\n`
- `0x18005443e`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_service.cxx`
- `0x18005448a`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_service.cxx`
- `0x1800544d0`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_service.cxx`
- `0x180054517`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_service.cxx`
- `0x18005442c`: `HTTP_SERVICE::UpdatePendingServiceStatus`
- `0x180054479`: `HTTP_SERVICE::UpdatePendingServiceStatus`
- `0x1800544be`: `HTTP_SERVICE::UpdatePendingServiceStatus`
- `0x1800544fa`: `Updating W3SVC pending service status failed\n`
- `0x180054506`: `UpdateW3SVCPendingServiceStatusCallback`

## pseudocode

```c
void __fastcall UpdateW3SVCPendingServiceStatusCallback(
        struct _TP_CALLBACK_INSTANCE *a1,
        void *a2,
        struct _TP_TIMER *a3)
{
  HTTP_SERVICE *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  int v5; // ecx
  int v6; // eax
  int v7; // ebx

  v3 = g_pHttpService;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)g_pHttpService + 72);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pHttpService + 72));
  v5 = *((_DWORD *)v3 + 3);
  v6 = g_dwDebugFlags;
  if ( (unsigned int)(v5 - 2) > 1 )
  {
    v7 = 0;
    if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_service.cxx",
        1297,
        "HTTP_SERVICE::UpdatePendingServiceStatus",
        "Ignoring pending service status timer, not in pending state. State: %lu\n",
        v5);
  }
  else
  {
    ++*((_DWORD *)v3 + 7);
    if ( (v6 & 0x30000) != 0 && (v6 & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_service.cxx",
        1272,
        "HTTP_SERVICE::UpdatePendingServiceStatus",
        "Updating the service state checkpoint to: %lu\n",
        *((_DWORD *)v3 + 7));
    v7 = HTTP_SERVICE::ReportServiceStatus(v3);
    if ( v7 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_service.cxx",
        1284,
        "HTTP_SERVICE::UpdatePendingServiceStatus",
        v7,
        "Could not report service status\n");
  }
  LeaveCriticalSection(v4);
  if ( v7 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_service.cxx",
      1389,
      "UpdateW3SVCPendingServiceStatusCallback",
      v7,
      "Updating W3SVC pending service status failed\n");
}

```

## disassembly

```asm
0x1800543d0  mov     [rsp+arg_0], rbx
0x1800543d5  push    rdi
0x1800543d6  sub     rsp, 30h
0x1800543da  mov     rbx, cs:?g_pHttpService@@3PEAVHTTP_SERVICE@@EA; HTTP_SERVICE * g_pHttpService
0x1800543e1  lea     rdi, [rbx+48h]
0x1800543e5  mov     rcx, rdi; lpCriticalSection
0x1800543e8  call    cs:__imp_EnterCriticalSection
0x1800543ee  mov     ecx, [rbx+0Ch]
0x1800543f1  lea     eax, [rcx-2]
0x1800543f4  cmp     eax, 1
0x1800543f7  mov     eax, cs:g_dwDebugFlags
0x1800543fd  ja      loc_180054499
0x180054403  inc     dword ptr [rbx+1Ch]
0x180054406  mov     ecx, [rbx+1Ch]
0x180054409  test    eax, 30000h
0x18005440e  setnz   dl
0x180054411  test    al, 3
0x180054413  setnz   al
0x180054416  test    al, dl
0x180054418  jz      short loc_18005444B
0x18005441a  mov     dword ptr [rsp+38h+var_10], ecx
0x18005441e  lea     rax, aUpdatingTheSer; "Updating the service state checkpoint t"...
0x180054425  mov     rcx, cs:g_pDebug
0x18005442c  lea     r9, aHttpServiceUpd; "HTTP_SERVICE::UpdatePendingServiceStatu"...
0x180054433  mov     r8d, 4F8h
0x180054439  mov     [rsp+38h+var_18], rax
0x18005443e  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180054445  call    cs:__imp_PuDbgPrint
0x18005444b  mov     rcx, rbx; this
0x18005444e  call    ?ReportServiceStatus@HTTP_SERVICE@@AEAAJXZ; HTTP_SERVICE::ReportServiceStatus(void)
0x180054453  mov     ebx, eax
0x180054455  test    eax, eax
0x180054457  jns     loc_1800544DD
0x18005445d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180054464  jz      short loc_1800544DD
0x180054466  mov     rcx, cs:g_pDebug
0x18005446d  lea     rax, aCouldNotReport; "Could not report service status\n"
0x180054474  mov     [rsp+38h+var_10], rax
0x180054479  lea     r9, aHttpServiceUpd; "HTTP_SERVICE::UpdatePendingServiceStatu"...
0x180054480  mov     r8d, 504h
0x180054486  mov     dword ptr [rsp+38h+var_18], ebx
0x18005448a  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180054491  call    cs:__imp_PuDbgPrintError
0x180054497  jmp     short loc_1800544DD
0x180054499  xor     ebx, ebx
0x18005449b  test    eax, 30000h
0x1800544a0  setnz   dl
0x1800544a3  test    al, 3
0x1800544a5  setnz   al
0x1800544a8  test    al, dl
0x1800544aa  jz      short loc_1800544DD
0x1800544ac  mov     dword ptr [rsp+38h+var_10], ecx
0x1800544b0  lea     rax, aIgnoringPendin; "Ignoring pending service status timer, "...
0x1800544b7  mov     rcx, cs:g_pDebug
0x1800544be  lea     r9, aHttpServiceUpd; "HTTP_SERVICE::UpdatePendingServiceStatu"...
0x1800544c5  mov     r8d, 511h
0x1800544cb  mov     [rsp+38h+var_18], rax
0x1800544d0  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800544d7  call    cs:__imp_PuDbgPrint
0x1800544dd  mov     rcx, rdi; lpCriticalSection
0x1800544e0  call    cs:__imp_LeaveCriticalSection
0x1800544e6  test    ebx, ebx
0x1800544e8  jns     short loc_180054524
0x1800544ea  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800544f1  jz      short loc_180054524
0x1800544f3  mov     rcx, cs:g_pDebug
0x1800544fa  lea     rax, aUpdatingW3svcP; "Updating W3SVC pending service status f"...
0x180054501  mov     [rsp+38h+var_10], rax
0x180054506  lea     r9, aUpdatew3svcpen; "UpdateW3SVCPendingServiceStatusCallback"
0x18005450d  mov     r8d, 56Dh
0x180054513  mov     dword ptr [rsp+38h+var_18], ebx
0x180054517  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005451e  call    cs:__imp_PuDbgPrintError
0x180054524  mov     rbx, [rsp+38h+arg_0]
0x180054529  add     rsp, 30h
0x18005452d  pop     rdi
0x18005452e  retn
```
