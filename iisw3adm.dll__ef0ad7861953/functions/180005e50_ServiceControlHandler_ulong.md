# ServiceControlHandler(ulong)

- ea: `0x180005e50`
- end: `0x1800060af`
- name: `?ServiceControlHandler@@YAXK@Z`
- size: `607`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800040bc`
- `0x180005694`
- `0x180005d0c`
- `0x180005e50`
- `0x1800073fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005ee1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005ee1`
- `iisutil!PuDbgPrint` at `0x180005ec5`
- `iisutil!PuDbgPrint` at `0x180005ec5`
- `iisutil!PuDbgPrintError` at `0x180005f25`
- `iisutil!PuDbgPrintError` at `0x180006032`
- `iisutil!PuDbgPrintError` at `0x18000608c`
- `iisutil!PuDbgPrintError` at `0x180005f25`
- `iisutil!PuDbgPrintError` at `0x180006032`
- `iisutil!PuDbgPrintError` at `0x18000608c`

## string_xrefs

- `0x180005e61`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180005f05`: `Couldn't report the service status\n`
- `0x180005f11`: `WEB_ADMIN_SERVICE::InterrogateService`
- `0x180005fdb`: `couldn't transition to service pause pending\n`
- `0x180006018`: `WEB_ADMIN_SERVICE::InitiatePauseService`
- `0x18000600b`: `Couldn't queue pause service work item\n`
- `0x180005f60`: `couldn't transition to service continue pending\n`
- `0x180005f6d`: `WEB_ADMIN_SERVICE::InitiateContinueService`
- `0x180005faf`: `WEB_ADMIN_SERVICE::InitiateContinueService`
- `0x180005fa2`: `Couldn't queue continue service work item\n`
- `0x180005ea2`: `Service control ignored, OpCode: %lu\n`
- `0x180005eb0`: `ServiceControlHandler`
- `0x180006078`: `ServiceControlHandler`
- `0x18000606c`: `Service control operation failed\n`

## pseudocode

```c
void __fastcall ServiceControlHandler(DWORD dwControl)
{
  WEB_ADMIN_SERVICE *v1; // rbx
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  int v3; // ebx
  WEB_ADMIN_SERVICE *v4; // rdi
  WEB_ADMIN_SERVICE *v5; // rdi
  const char *v6; // rax
  __int64 v7; // r8

  if ( dwControl == 1 )
  {
LABEL_26:
    v3 = WEB_ADMIN_SERVICE::InitiateStopService(g_pWebAdminService);
    goto LABEL_27;
  }
  if ( dwControl != 2 )
  {
    if ( dwControl == 3 )
    {
      v4 = g_pWebAdminService;
      v3 = WEB_ADMIN_SERVICE::BeginStateTransition(g_pWebAdminService, 5u);
      if ( v3 >= 0 )
      {
        v3 = WORK_QUEUE::GetAndQueueWorkItem((WEB_ADMIN_SERVICE *)((char *)v4 + 16), v4, 4u);
        if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
            937,
            "WEB_ADMIN_SERVICE::InitiateContinueService",
            v3,
            "Couldn't queue continue service work item\n");
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
          919,
          "WEB_ADMIN_SERVICE::InitiateContinueService",
          v3,
          "couldn't transition to service continue pending\n");
      }
      goto LABEL_27;
    }
    if ( dwControl == 4 )
    {
      v1 = g_pWebAdminService;
      v2 = (struct _RTL_CRITICAL_SECTION *)((char *)g_pWebAdminService + 1080);
      EnterCriticalSection((LPCRITICAL_SECTION)g_pWebAdminService + 27);
      v3 = WEB_ADMIN_SERVICE::ReportServiceStatus(v1);
      if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
          735,
          "WEB_ADMIN_SERVICE::InterrogateService",
          v3,
          "Couldn't report the service status\n");
      LeaveCriticalSection(v2);
      goto LABEL_27;
    }
    if ( dwControl != 5 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
          3982,
          "ServiceControlHandler",
          "Service control ignored, OpCode: %lu\n",
          dwControl);
      return;
    }
    goto LABEL_26;
  }
  v5 = g_pWebAdminService;
  v3 = WEB_ADMIN_SERVICE::BeginStateTransition(g_pWebAdminService, 6u);
  if ( v3 >= 0 )
  {
    v3 = WORK_QUEUE::GetAndQueueWorkItem((WEB_ADMIN_SERVICE *)((char *)v5 + 16), v5, 3u);
    if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    {
      v6 = "Couldn't queue pause service work item\n";
      v7 = 871;
      goto LABEL_24;
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v6 = "couldn't transition to service pause pending\n";
    v7 = 853;
LABEL_24:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
      v7,
      "WEB_ADMIN_SERVICE::InitiatePauseService",
      v3,
      v6);
  }
LABEL_27:
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -2147023835 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        4000,
        "ServiceControlHandler",
        v3,
        "Service control operation failed\n");
    *((_DWORD *)g_pWebAdminService + 294) = v3;
  }
}

```

## disassembly

```asm
0x180005e50  mov     [rsp+arg_0], rbx
0x180005e55  mov     [rsp+arg_8], rbp
0x180005e5a  push    rdi
0x180005e5b  sub     rsp, 30h
0x180005e5f  mov     eax, ecx
0x180005e61  lea     rbp, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005e68  sub     eax, 1
0x180005e6b  jz      loc_18000603A
0x180005e71  sub     eax, 1
0x180005e74  jz      loc_180005FB8
0x180005e7a  sub     eax, 1
0x180005e7d  jz      loc_180005F39
0x180005e83  sub     eax, 1
0x180005e86  jz      short loc_180005ED0
0x180005e88  cmp     eax, 1
0x180005e8b  jz      loc_18000603A
0x180005e91  test    byte ptr cs:g_dwDebugFlags, 3
0x180005e98  jz      loc_18000609F
0x180005e9e  mov     dword ptr [rsp+38h+var_10], ecx
0x180005ea2  lea     rax, aServiceControl_0; "Service control ignored, OpCode: %lu\n"
0x180005ea9  mov     rcx, cs:g_pDebug
0x180005eb0  lea     r9, aServicecontrol; "ServiceControlHandler"
0x180005eb7  mov     r8d, 0F8Eh
0x180005ebd  mov     [rsp+38h+var_18], rax
0x180005ec2  mov     rdx, rbp
0x180005ec5  call    cs:__imp_PuDbgPrint
0x180005ecb  jmp     loc_18000609F
0x180005ed0  mov     rbx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180005ed7  lea     rdi, [rbx+438h]
0x180005ede  mov     rcx, rdi; lpCriticalSection
0x180005ee1  call    cs:__imp_EnterCriticalSection
0x180005ee7  mov     rcx, rbx; this
0x180005eea  call    ?ReportServiceStatus@WEB_ADMIN_SERVICE@@AEAAJXZ; WEB_ADMIN_SERVICE::ReportServiceStatus(void)
0x180005eef  mov     ebx, eax
0x180005ef1  test    eax, eax
0x180005ef3  jns     short loc_180005F2B
0x180005ef5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005efc  jz      short loc_180005F2B
0x180005efe  mov     rcx, cs:g_pDebug
0x180005f05  lea     rax, aCouldnTReportT; "Couldn't report the service status\n"
0x180005f0c  mov     [rsp+38h+var_10], rax
0x180005f11  lea     r9, aWebAdminServic_13; "WEB_ADMIN_SERVICE::InterrogateService"
0x180005f18  mov     r8d, 2DFh
0x180005f1e  mov     dword ptr [rsp+38h+var_18], ebx
0x180005f22  mov     rdx, rbp
0x180005f25  call    cs:__imp_PuDbgPrintError
0x180005f2b  mov     rcx, rdi; lpCriticalSection
0x180005f2e  call    cs:__imp_LeaveCriticalSection
0x180005f34  jmp     loc_180006048
0x180005f39  mov     rdi, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180005f40  mov     edx, 5; unsigned int
0x180005f45  mov     rcx, rdi; this
0x180005f48  call    ?BeginStateTransition@WEB_ADMIN_SERVICE@@AEAAJK@Z; WEB_ADMIN_SERVICE::BeginStateTransition(ulong)
0x180005f4d  mov     ebx, eax
0x180005f4f  test    eax, eax
0x180005f51  jns     short loc_180005F79
0x180005f53  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005f5a  jz      loc_180006048
0x180005f60  lea     rax, aCouldnTTransit_2; "couldn't transition to service continue"...
0x180005f67  mov     r8d, 397h
0x180005f6d  lea     r9, aWebAdminServic_2; "WEB_ADMIN_SERVICE::InitiateContinueServ"...
0x180005f74  jmp     loc_18000601F
0x180005f79  lea     rcx, [rdi+10h]; this
0x180005f7d  mov     r8d, 4; unsigned __int64
0x180005f83  mov     rdx, rdi; struct WORK_DISPATCH *
0x180005f86  call    ?GetAndQueueWorkItem@WORK_QUEUE@@QEAAJPEAVWORK_DISPATCH@@_K@Z; WORK_QUEUE::GetAndQueueWorkItem(WORK_DISPATCH *,unsigned __int64)
0x180005f8b  mov     ebx, eax
0x180005f8d  test    eax, eax
0x180005f8f  jns     loc_180006048
0x180005f95  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005f9c  jz      loc_180006048
0x180005fa2  lea     rax, aCouldnTQueueCo; "Couldn't queue continue service work it"...
0x180005fa9  mov     r8d, 3A9h
0x180005faf  lea     r9, aWebAdminServic_2; "WEB_ADMIN_SERVICE::InitiateContinueServ"...
0x180005fb6  jmp     short loc_18000601F
0x180005fb8  mov     rdi, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180005fbf  mov     edx, 6; unsigned int
0x180005fc4  mov     rcx, rdi; this
0x180005fc7  call    ?BeginStateTransition@WEB_ADMIN_SERVICE@@AEAAJK@Z; WEB_ADMIN_SERVICE::BeginStateTransition(ulong)
0x180005fcc  mov     ebx, eax
0x180005fce  test    eax, eax
0x180005fd0  jns     short loc_180005FEA
0x180005fd2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005fd9  jz      short loc_180006048
0x180005fdb  lea     rax, aCouldnTTransit; "couldn't transition to service pause pe"...
0x180005fe2  mov     r8d, 355h
0x180005fe8  jmp     short loc_180006018
0x180005fea  lea     rcx, [rdi+10h]; this
0x180005fee  mov     r8d, 3; unsigned __int64
0x180005ff4  mov     rdx, rdi; struct WORK_DISPATCH *
0x180005ff7  call    ?GetAndQueueWorkItem@WORK_QUEUE@@QEAAJPEAVWORK_DISPATCH@@_K@Z; WORK_QUEUE::GetAndQueueWorkItem(WORK_DISPATCH *,unsigned __int64)
0x180005ffc  mov     ebx, eax
0x180005ffe  test    eax, eax
0x180006000  jns     short loc_180006048
0x180006002  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006009  jz      short loc_180006048
0x18000600b  lea     rax, aCouldnTQueuePa; "Couldn't queue pause service work item"...
0x180006012  mov     r8d, 367h
0x180006018  lea     r9, aWebAdminServic_0; "WEB_ADMIN_SERVICE::InitiatePauseService"
0x18000601f  mov     rcx, cs:g_pDebug
0x180006026  mov     rdx, rbp
0x180006029  mov     [rsp+38h+var_10], rax
0x18000602e  mov     dword ptr [rsp+38h+var_18], ebx
0x180006032  call    cs:__imp_PuDbgPrintError
0x180006038  jmp     short loc_180006048
0x18000603a  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x180006041  call    ?InitiateStopService@WEB_ADMIN_SERVICE@@QEAAJXZ; WEB_ADMIN_SERVICE::InitiateStopService(void)
0x180006046  mov     ebx, eax
0x180006048  mov     eax, 80000000h
0x18000604d  lea     ecx, [rbx+rax]
0x180006050  test    eax, ecx
0x180006052  jnz     short loc_18000609F
0x180006054  cmp     ebx, 80070425h
0x18000605a  jz      short loc_18000609F
0x18000605c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006063  jz      short loc_180006092
0x180006065  mov     rcx, cs:g_pDebug
0x18000606c  lea     rax, aServiceControl; "Service control operation failed\n"
0x180006073  mov     [rsp+38h+var_10], rax
0x180006078  lea     r9, aServicecontrol; "ServiceControlHandler"
0x18000607f  mov     r8d, 0FA0h
0x180006085  mov     dword ptr [rsp+38h+var_18], ebx
0x180006089  mov     rdx, rbp
0x18000608c  call    cs:__imp_PuDbgPrintError
0x180006092  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180006099  mov     [rax+498h], ebx
0x18000609f  mov     rbx, [rsp+38h+arg_0]
0x1800060a4  mov     rbp, [rsp+38h+arg_8]
0x1800060a9  add     rsp, 30h
0x1800060ad  pop     rdi
0x1800060ae  retn
```
