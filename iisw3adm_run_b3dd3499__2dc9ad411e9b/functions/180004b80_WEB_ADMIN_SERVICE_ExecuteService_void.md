# WEB_ADMIN_SERVICE::ExecuteService(void)

- ea: `0x180004b80`
- end: `0x180004cdd`
- name: `?ExecuteService@WEB_ADMIN_SERVICE@@QEAAXXZ`
- size: `349`
- prototype: `void __fastcall(WEB_ADMIN_SERVICE *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180003460`
- `0x180003770`

## callees

- `0x180004b80`
- `0x180005950`
- `0x180006b88`
- `0x1800073fc`
- `0x180007600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004cbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004cbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004ca6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004ca6`
- `iisutil!PuDbgPrintError` at `0x180004c11`
- `iisutil!PuDbgPrintError` at `0x180004c4f`
- `iisutil!PuDbgPrintError` at `0x180004c99`
- `iisutil!PuDbgPrintError` at `0x180004c11`
- `iisutil!PuDbgPrintError` at `0x180004c4f`
- `iisutil!PuDbgPrintError` at `0x180004c99`

## string_xrefs

- `0x180004c06`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180004c48`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180004c92`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180004c37`: `WEB_ADMIN_SERVICE::ExecuteService`
- `0x180004c81`: `WEB_ADMIN_SERVICE::ExecuteService`
- `0x180004bfa`: `WEB_ADMIN_SERVICE::StartWorkQueue`
- `0x180004be6`: `Couldn't queue start service work item\n`

## pseudocode

```c
void __fastcall WEB_ADMIN_SERVICE::ExecuteService(WEB_ADMIN_SERVICE *this)
{
  WEB_ADMIN_SERVICE *v1; // rdi
  int v2; // ebx
  int v3; // ebx

  v1 = g_pWebAdminService;
  v2 = WORK_QUEUE::Initialize((WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 16));
  if ( v2 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      return;
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
      1101,
      "WEB_ADMIN_SERVICE::StartWorkQueue",
      v2,
      "Couldn't initialize work queue\n");
LABEL_7:
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        595,
        "WEB_ADMIN_SERVICE::ExecuteService",
        v2,
        "Could not start work queue\n");
    return;
  }
  v2 = WORK_QUEUE::GetAndQueueWorkItem((WEB_ADMIN_SERVICE *)((char *)v1 + 16), v1, 1u);
  if ( v2 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      return;
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
      1119,
      "WEB_ADMIN_SERVICE::StartWorkQueue",
      v2,
      "Couldn't queue start service work item\n");
    goto LABEL_7;
  }
  v3 = WEB_ADMIN_SERVICE::MainWorkerThread(v1);
  if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
      617,
      "WEB_ADMIN_SERVICE::ExecuteService",
      v3,
      "Main work loop function returned an error\n");
  EnterCriticalSection(&g_critsecWebAdminService);
  g_fWASStoppingInProgress = 1;
  LeaveCriticalSection(&g_critsecWebAdminService);
  WEB_ADMIN_SERVICE::TerminateServiceAndReportFinalStatus((struct _RTL_CRITICAL_SECTION *)v1, v3);
}

```

## disassembly

```asm
0x180004b80  mov     [rsp+arg_0], rbx
0x180004b85  mov     [rsp+arg_8], rsi
0x180004b8a  push    rdi
0x180004b8b  sub     rsp, 30h
0x180004b8f  mov     rdi, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180004b96  lea     rcx, [rdi+10h]; this
0x180004b9a  call    ?Initialize@WORK_QUEUE@@QEAAJXZ; WORK_QUEUE::Initialize(void)
0x180004b9f  mov     ebx, eax
0x180004ba1  test    eax, eax
0x180004ba3  jns     short loc_180004BC1
0x180004ba5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004bac  jz      loc_180004CCD
0x180004bb2  lea     rax, aCouldnTInitial_2; "Couldn't initialize work queue\n"
0x180004bb9  mov     r8d, 44Dh
0x180004bbf  jmp     short loc_180004BF3
0x180004bc1  mov     r8d, 1; unsigned __int64
0x180004bc7  lea     rcx, [rdi+10h]; this
0x180004bcb  mov     rdx, rdi; struct WORK_DISPATCH *
0x180004bce  call    ?GetAndQueueWorkItem@WORK_QUEUE@@QEAAJPEAVWORK_DISPATCH@@_K@Z; WORK_QUEUE::GetAndQueueWorkItem(WORK_DISPATCH *,unsigned __int64)
0x180004bd3  mov     ebx, eax
0x180004bd5  test    eax, eax
0x180004bd7  jns     short loc_180004C57
0x180004bd9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004be0  jz      loc_180004CCD
0x180004be6  lea     rax, aCouldnTQueueSt_0; "Couldn't queue start service work item"...
0x180004bed  mov     r8d, 45Fh
0x180004bf3  mov     rcx, cs:g_pDebug
0x180004bfa  lea     r9, aWebAdminServic_15; "WEB_ADMIN_SERVICE::StartWorkQueue"
0x180004c01  mov     [rsp+38h+var_10], rax
0x180004c06  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180004c0d  mov     [rsp+38h+var_18], ebx
0x180004c11  call    cs:__imp_PuDbgPrintError
0x180004c17  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004c1e  jz      loc_180004CCD
0x180004c24  mov     rcx, cs:g_pDebug
0x180004c2b  lea     rax, aCouldNotStartW; "Could not start work queue\n"
0x180004c32  mov     [rsp+38h+var_10], rax
0x180004c37  lea     r9, aWebAdminServic_7; "WEB_ADMIN_SERVICE::ExecuteService"
0x180004c3e  mov     r8d, 253h
0x180004c44  mov     [rsp+38h+var_18], ebx
0x180004c48  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180004c4f  call    cs:__imp_PuDbgPrintError
0x180004c55  jmp     short loc_180004CCD
0x180004c57  mov     rcx, rdi; this
0x180004c5a  call    ?MainWorkerThread@WEB_ADMIN_SERVICE@@AEAAJXZ; WEB_ADMIN_SERVICE::MainWorkerThread(void)
0x180004c5f  mov     ebx, eax
0x180004c61  test    eax, eax
0x180004c63  jns     short loc_180004C9F
0x180004c65  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004c6c  jz      short loc_180004C9F
0x180004c6e  mov     rcx, cs:g_pDebug
0x180004c75  lea     rax, aMainWorkLoopFu; "Main work loop function returned an err"...
0x180004c7c  mov     [rsp+38h+var_10], rax
0x180004c81  lea     r9, aWebAdminServic_7; "WEB_ADMIN_SERVICE::ExecuteService"
0x180004c88  mov     r8d, 269h
0x180004c8e  mov     [rsp+38h+var_18], ebx
0x180004c92  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180004c99  call    cs:__imp_PuDbgPrintError
0x180004c9f  lea     rcx, ?g_critsecWebAdminService@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004ca6  call    cs:__imp_EnterCriticalSection
0x180004cac  lea     rcx, ?g_critsecWebAdminService@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004cb3  mov     cs:?g_fWASStoppingInProgress@@3HA, 1; int g_fWASStoppingInProgress
0x180004cbd  call    cs:__imp_LeaveCriticalSection
0x180004cc3  mov     edx, ebx; unsigned int
0x180004cc5  mov     rcx, rdi; this
0x180004cc8  call    ?TerminateServiceAndReportFinalStatus@WEB_ADMIN_SERVICE@@AEAAXJ@Z; WEB_ADMIN_SERVICE::TerminateServiceAndReportFinalStatus(long)
0x180004ccd  mov     rbx, [rsp+38h+arg_0]
0x180004cd2  mov     rsi, [rsp+38h+arg_8]
0x180004cd7  add     rsp, 30h
0x180004cdb  pop     rdi
0x180004cdc  retn
```
