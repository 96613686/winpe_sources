# UpdatePendingServiceStatusCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180006ce0`
- end: `0x180006e65`
- name: `?UpdatePendingServiceStatusCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `389`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005d0c`
- `0x180006ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006cfb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006cfb`
- `iisutil!PuDbgPrint` at `0x180006d5f`
- `iisutil!PuDbgPrint` at `0x180006db8`
- `iisutil!PuDbgPrint` at `0x180006d5f`
- `iisutil!PuDbgPrint` at `0x180006db8`
- `iisutil!PuDbgPrintError` at `0x180006e00`
- `iisutil!PuDbgPrintError` at `0x180006e47`
- `iisutil!PuDbgPrintError` at `0x180006e00`
- `iisutil!PuDbgPrintError` at `0x180006e47`

## string_xrefs

- `0x180006d4d`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180006db1`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180006df9`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180006e40`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180006d91`: `Updating the service state checkpoint to: %lu\n`
- `0x180006d46`: `WEB_ADMIN_SERVICE::UpdatePendingServiceStatus`
- `0x180006d9f`: `WEB_ADMIN_SERVICE::UpdatePendingServiceStatus`
- `0x180006de8`: `WEB_ADMIN_SERVICE::UpdatePendingServiceStatus`
- `0x180006ddc`: `Could not report service status\n`
- `0x180006d3b`: `Ignoring pending service status timer, not in pending state. State: %lu\n`
- `0x180006e23`: `Updating pending service status failed\n`
- `0x180006e2f`: `UpdatePendingServiceStatusCallback`

## pseudocode

```c
void __fastcall UpdatePendingServiceStatusCallback(struct _TP_CALLBACK_INSTANCE *a1, void *a2, struct _TP_TIMER *a3)
{
  WEB_ADMIN_SERVICE *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  int v5; // edx
  int v6; // ebx

  v3 = g_pWebAdminService;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)g_pWebAdminService + 1080);
  EnterCriticalSection((LPCRITICAL_SECTION)g_pWebAdminService + 27);
  v5 = *((_DWORD *)v3 + 283);
  if ( (unsigned int)(v5 - 2) <= 1 || (unsigned int)(v5 - 5) <= 1 )
  {
    ++*((_DWORD *)v3 + 287);
    if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        1000,
        "WEB_ADMIN_SERVICE::UpdatePendingServiceStatus",
        "Updating the service state checkpoint to: %lu\n",
        *((_DWORD *)v3 + 287));
    v6 = WEB_ADMIN_SERVICE::ReportServiceStatus(v3);
    if ( v6 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        1012,
        "WEB_ADMIN_SERVICE::UpdatePendingServiceStatus",
        v6,
        "Could not report service status\n");
  }
  else
  {
    v6 = 0;
    if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        1025,
        "WEB_ADMIN_SERVICE::UpdatePendingServiceStatus",
        "Ignoring pending service status timer, not in pending state. State: %lu\n",
        v5);
  }
  LeaveCriticalSection(v4);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        4054,
        "UpdatePendingServiceStatusCallback",
        v6,
        "Updating pending service status failed\n");
    *((_DWORD *)g_pWebAdminService + 294) = v6;
  }
}

```

## disassembly

```asm
0x180006ce0  mov     [rsp+arg_0], rbx
0x180006ce5  push    rdi
0x180006ce6  sub     rsp, 30h
0x180006cea  mov     rbx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180006cf1  lea     rdi, [rbx+438h]
0x180006cf8  mov     rcx, rdi; lpCriticalSection
0x180006cfb  call    cs:__imp_EnterCriticalSection
0x180006d01  mov     edx, [rbx+46Ch]
0x180006d07  lea     eax, [rdx-2]
0x180006d0a  cmp     eax, 1
0x180006d0d  jbe     short loc_180006D6A
0x180006d0f  lea     eax, [rdx-5]
0x180006d12  cmp     eax, 1
0x180006d15  jbe     short loc_180006D6A
0x180006d17  mov     eax, cs:g_dwDebugFlags
0x180006d1d  xor     ebx, ebx
0x180006d1f  test    eax, 30000h
0x180006d24  setnz   cl
0x180006d27  test    al, 3
0x180006d29  setnz   al
0x180006d2c  test    al, cl
0x180006d2e  jz      loc_180006E06
0x180006d34  mov     rcx, cs:g_pDebug
0x180006d3b  lea     rax, aIgnoringPendin; "Ignoring pending service status timer, "...
0x180006d42  mov     dword ptr [rsp+38h+var_10], edx
0x180006d46  lea     r9, aWebAdminServic_16; "WEB_ADMIN_SERVICE::UpdatePendingService"...
0x180006d4d  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006d54  mov     [rsp+38h+var_18], rax
0x180006d59  mov     r8d, 401h
0x180006d5f  call    cs:__imp_PuDbgPrint
0x180006d65  jmp     loc_180006E06
0x180006d6a  inc     dword ptr [rbx+47Ch]
0x180006d70  mov     eax, cs:g_dwDebugFlags
0x180006d76  test    eax, 30000h
0x180006d7b  mov     ecx, [rbx+47Ch]
0x180006d81  setnz   dl
0x180006d84  test    al, 3
0x180006d86  setnz   al
0x180006d89  test    al, dl
0x180006d8b  jz      short loc_180006DBE
0x180006d8d  mov     dword ptr [rsp+38h+var_10], ecx
0x180006d91  lea     rax, aUpdatingTheSer; "Updating the service state checkpoint t"...
0x180006d98  mov     rcx, cs:g_pDebug
0x180006d9f  lea     r9, aWebAdminServic_16; "WEB_ADMIN_SERVICE::UpdatePendingService"...
0x180006da6  mov     r8d, 3E8h
0x180006dac  mov     [rsp+38h+var_18], rax
0x180006db1  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006db8  call    cs:__imp_PuDbgPrint
0x180006dbe  mov     rcx, rbx; this
0x180006dc1  call    ?ReportServiceStatus@WEB_ADMIN_SERVICE@@AEAAJXZ; WEB_ADMIN_SERVICE::ReportServiceStatus(void)
0x180006dc6  mov     ebx, eax
0x180006dc8  test    eax, eax
0x180006dca  jns     short loc_180006E06
0x180006dcc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006dd3  jz      short loc_180006E06
0x180006dd5  mov     rcx, cs:g_pDebug
0x180006ddc  lea     rax, aCouldNotReport; "Could not report service status\n"
0x180006de3  mov     [rsp+38h+var_10], rax
0x180006de8  lea     r9, aWebAdminServic_16; "WEB_ADMIN_SERVICE::UpdatePendingService"...
0x180006def  mov     r8d, 3F4h
0x180006df5  mov     dword ptr [rsp+38h+var_18], ebx
0x180006df9  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006e00  call    cs:__imp_PuDbgPrintError
0x180006e06  mov     rcx, rdi; lpCriticalSection
0x180006e09  call    cs:__imp_LeaveCriticalSection
0x180006e0f  test    ebx, ebx
0x180006e11  jns     short loc_180006E5A
0x180006e13  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006e1a  jz      short loc_180006E4D
0x180006e1c  mov     rcx, cs:g_pDebug
0x180006e23  lea     rax, aUpdatingPendin; "Updating pending service status failed"...
0x180006e2a  mov     [rsp+38h+var_10], rax
0x180006e2f  lea     r9, aUpdatependings; "UpdatePendingServiceStatusCallback"
0x180006e36  mov     r8d, 0FD6h
0x180006e3c  mov     dword ptr [rsp+38h+var_18], ebx
0x180006e40  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006e47  call    cs:__imp_PuDbgPrintError
0x180006e4d  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180006e54  mov     [rax+498h], ebx
0x180006e5a  mov     rbx, [rsp+38h+arg_0]
0x180006e5f  add     rsp, 30h
0x180006e63  pop     rdi
0x180006e64  retn
```
