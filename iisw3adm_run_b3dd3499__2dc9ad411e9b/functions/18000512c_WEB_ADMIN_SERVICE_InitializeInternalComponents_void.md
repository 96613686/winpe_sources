# WEB_ADMIN_SERVICE::InitializeInternalComponents(void)

- ea: `0x18000512c`
- end: `0x180005381`
- name: `?InitializeInternalComponents@WEB_ADMIN_SERVICE@@AEAAJXZ`
- size: `597`
- prototype: `__int64 __fastcall(WEB_ADMIN_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006490`

## callees

- `0x18000479c`
- `0x1800049a4`
- `0x18000512c`
- `0x1800607f0`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x1800051ed`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x1800051ed`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800051bc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800051bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052d5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000514e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000514e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000513e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000513e`
- `iisutil!PuDbgPrintError` at `0x1800051a5`
- `iisutil!PuDbgPrintError` at `0x1800051a5`
- `iisutil!InitializeIISUtil` at `0x1800052cb`
- `iisutil!InitializeIISUtil` at `0x1800052cb`
- `nativerd!InitializeNativeConfiguration` at `0x180005305`
- `nativerd!InitializeNativeConfiguration` at `0x180005305`

## string_xrefs

- `0x18000519a`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x18000517a`: `Setting thread priority failed\n`
- `0x18000518e`: `WEB_ADMIN_SERVICE::InitializeInternalComponents`
- `0x180005221`: `Couldn't register service control handler\n`
- `0x18000528c`: `Determining current directory failed\n`
- `0x1800052b9`: `Creating cached worker process tokens failed\n`
- `0x18000531a`: `Could not initialize native config reader\n`
- `0x180005340`: `Could not initialize multi work item reader\n`

## pseudocode

```c
__int64 __fastcall WEB_ADMIN_SERVICE::InitializeInternalComponents(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int CachedWorkerProcessTokens; // ebx
  bool v5; // zf
  SERVICE_STATUS_HANDLE v6; // rax
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax

  CurrentThread = GetCurrentThread();
  if ( !SetThreadPriority(CurrentThread, 1) )
  {
    LastError = GetLastError();
    CachedWorkerProcessTokens = LastError;
    if ( LastError > 0 )
      CachedWorkerProcessTokens = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        2296,
        "WEB_ADMIN_SERVICE::InitializeInternalComponents",
        CachedWorkerProcessTokens,
        "Setting thread priority failed\n");
    return (unsigned int)CachedWorkerProcessTokens;
  }
  if ( InitializeCriticalSectionAndSpinCount(this + 27, 0x800003E8) )
  {
    HIDWORD(this[26].SpinCount) = 1;
  }
  else
  {
    v8 = GetLastError();
    CachedWorkerProcessTokens = v8;
    if ( v8 > 0 )
      CachedWorkerProcessTokens = (unsigned __int16)v8 | 0x80070000;
    if ( CachedWorkerProcessTokens < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
          2314,
          "WEB_ADMIN_SERVICE::InitializeInternalComponents",
          CachedWorkerProcessTokens,
          "Lock initialization failed\n");
      return (unsigned int)CachedWorkerProcessTokens;
    }
  }
  v5 = this[41].LockCount == 0;
  this[40].RecursionCount = 1;
  if ( v5 )
  {
    v6 = RegisterServiceCtrlHandlerW(L"was", ServiceControlHandler);
    this[28].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v6;
    if ( !v6 )
    {
      v7 = GetLastError();
      CachedWorkerProcessTokens = v7;
      if ( v7 > 0 )
        CachedWorkerProcessTokens = (unsigned __int16)v7 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
          2344,
          "WEB_ADMIN_SERVICE::InitializeInternalComponents",
          CachedWorkerProcessTokens,
          "Couldn't register service control handler\n");
      return (unsigned int)CachedWorkerProcessTokens;
    }
    g_RegisterServiceCalled = 1;
  }
  CachedWorkerProcessTokens = WEB_ADMIN_SERVICE::DetermineCurrentDirectory((WEB_ADMIN_SERVICE *)this);
  if ( CachedWorkerProcessTokens >= 0 )
  {
    CachedWorkerProcessTokens = WEB_ADMIN_SERVICE::CreateCachedWorkerProcessTokens((WEB_ADMIN_SERVICE *)this);
    if ( CachedWorkerProcessTokens >= 0 )
    {
      if ( (unsigned int)InitializeIISUtil() )
      {
        CachedWorkerProcessTokens = InitializeNativeConfiguration();
        if ( CachedWorkerProcessTokens >= 0 )
        {
          CachedWorkerProcessTokens = MULTI_WORK_ITEM::InitializeLookAsideList();
          if ( CachedWorkerProcessTokens >= 0 )
          {
            CachedWorkerProcessTokens = 0;
            qword_180089200 = (__int64)&WORKER_PROCESS::s_WorkerProcessListHead;
            WORKER_PROCESS::s_WorkerProcessListHead.Flink = &WORKER_PROCESS::s_WorkerProcessListHead;
            this[40].LockCount = 1;
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
              2433,
              "WEB_ADMIN_SERVICE::InitializeInternalComponents",
              CachedWorkerProcessTokens,
              "Could not initialize multi work item reader\n");
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
            2417,
            "WEB_ADMIN_SERVICE::InitializeInternalComponents",
            CachedWorkerProcessTokens,
            "Could not initialize native config reader\n");
        }
      }
      else
      {
        v9 = GetLastError();
        CachedWorkerProcessTokens = v9;
        if ( v9 > 0 )
          CachedWorkerProcessTokens = (unsigned __int16)v9 | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
            2401,
            "WEB_ADMIN_SERVICE::InitializeInternalComponents",
            CachedWorkerProcessTokens,
            "Could not initialize iisutil\n");
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        2383,
        "WEB_ADMIN_SERVICE::InitializeInternalComponents",
        CachedWorkerProcessTokens,
        "Creating cached worker process tokens failed\n");
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
      2364,
      "WEB_ADMIN_SERVICE::InitializeInternalComponents",
      CachedWorkerProcessTokens,
      "Determining current directory failed\n");
  }
  return (unsigned int)CachedWorkerProcessTokens;
}

```

## disassembly

```asm
0x18000512c  mov     [rsp+arg_0], rbx
0x180005131  mov     [rsp+arg_8], rbp
0x180005136  push    rdi
0x180005137  sub     rsp, 30h
0x18000513b  mov     rdi, rcx
0x18000513e  call    cs:__imp_GetCurrentThread
0x180005144  mov     ebp, 1
0x180005149  mov     rcx, rax; hThread
0x18000514c  mov     edx, ebp; nPriority
0x18000514e  call    cs:__imp_SetThreadPriority
0x180005154  test    eax, eax
0x180005156  jnz     short loc_1800051B0
0x180005158  call    cs:__imp_GetLastError
0x18000515e  mov     ebx, eax
0x180005160  test    eax, eax
0x180005162  jle     short loc_18000516D
0x180005164  movzx   ebx, ax
0x180005167  or      ebx, 80070000h
0x18000516d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005174  jz      loc_18000536F
0x18000517a  lea     rax, aSettingThreadP; "Setting thread priority failed\n"
0x180005181  mov     r8d, 8F8h
0x180005187  mov     rcx, cs:g_pDebug
0x18000518e  lea     r9, aWebAdminServic_31; "WEB_ADMIN_SERVICE::InitializeInternalCo"...
0x180005195  mov     [rsp+38h+var_10], rax
0x18000519a  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800051a1  mov     [rsp+38h+var_18], ebx
0x1800051a5  call    cs:__imp_PuDbgPrintError
0x1800051ab  jmp     loc_18000536F
0x1800051b0  lea     rcx, [rdi+438h]; lpCriticalSection
0x1800051b7  mov     edx, 800003E8h; dwSpinCount
0x1800051bc  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800051c2  test    eax, eax
0x1800051c4  jz      short loc_180005233
0x1800051c6  mov     [rdi+434h], ebp
0x1800051cc  cmp     dword ptr [rdi+670h], 0
0x1800051d3  mov     [rdi+64Ch], ebp
0x1800051d9  jnz     loc_180005271
0x1800051df  lea     rdx, ?ServiceControlHandler@@YAXK@Z; lpHandlerProc
0x1800051e6  lea     rcx, ServiceName; "was"
0x1800051ed  call    cs:__imp_RegisterServiceCtrlHandlerW
0x1800051f3  mov     [rdi+460h], rax
0x1800051fa  test    rax, rax
0x1800051fd  jnz     short loc_18000526B
0x1800051ff  call    cs:__imp_GetLastError
0x180005205  mov     ebx, eax
0x180005207  test    eax, eax
0x180005209  jle     short loc_180005214
0x18000520b  movzx   ebx, ax
0x18000520e  or      ebx, 80070000h
0x180005214  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000521b  jz      loc_18000536F
0x180005221  lea     rax, aCouldnTRegiste; "Couldn't register service control handl"...
0x180005228  mov     r8d, 928h
0x18000522e  jmp     loc_180005187
0x180005233  call    cs:__imp_GetLastError
0x180005239  mov     ebx, eax
0x18000523b  test    eax, eax
0x18000523d  jle     short loc_180005248
0x18000523f  movzx   ebx, ax
0x180005242  or      ebx, 80070000h
0x180005248  test    ebx, ebx
0x18000524a  jns     short loc_1800051CC
0x18000524c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005253  jz      loc_18000536F
0x180005259  lea     rax, aLockInitializa; "Lock initialization failed\n"
0x180005260  mov     r8d, 90Ah
0x180005266  jmp     loc_180005187
0x18000526b  mov     cs:?g_RegisterServiceCalled@@3HA, ebp; int g_RegisterServiceCalled
0x180005271  mov     rcx, rdi; this
0x180005274  call    ?DetermineCurrentDirectory@WEB_ADMIN_SERVICE@@AEAAJXZ; WEB_ADMIN_SERVICE::DetermineCurrentDirectory(void)
0x180005279  mov     ebx, eax
0x18000527b  test    eax, eax
0x18000527d  jns     short loc_18000529E
0x18000527f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005286  jz      loc_18000536F
0x18000528c  lea     rax, aDeterminingCur; "Determining current directory failed\n"
0x180005293  mov     r8d, 93Ch
0x180005299  jmp     loc_180005187
0x18000529e  mov     rcx, rdi; this
0x1800052a1  call    ?CreateCachedWorkerProcessTokens@WEB_ADMIN_SERVICE@@AEAAJXZ; WEB_ADMIN_SERVICE::CreateCachedWorkerProcessTokens(void)
0x1800052a6  mov     ebx, eax
0x1800052a8  test    eax, eax
0x1800052aa  jns     short loc_1800052CB
0x1800052ac  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800052b3  jz      loc_18000536F
0x1800052b9  lea     rax, aCreatingCached; "Creating cached worker process tokens f"...
0x1800052c0  mov     r8d, 94Fh
0x1800052c6  jmp     loc_180005187
0x1800052cb  call    cs:__imp_InitializeIISUtil
0x1800052d1  test    eax, eax
0x1800052d3  jnz     short loc_180005305
0x1800052d5  call    cs:__imp_GetLastError
0x1800052db  mov     ebx, eax
0x1800052dd  test    eax, eax
0x1800052df  jle     short loc_1800052EA
0x1800052e1  movzx   ebx, ax
0x1800052e4  or      ebx, 80070000h
0x1800052ea  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800052f1  jz      short loc_18000536F
0x1800052f3  lea     rax, aCouldNotInitia_0; "Could not initialize iisutil\n"
0x1800052fa  mov     r8d, 961h
0x180005300  jmp     loc_180005187
0x180005305  call    cs:__imp_?InitializeNativeConfiguration@@YAJXZ; InitializeNativeConfiguration(void)
0x18000530b  mov     ebx, eax
0x18000530d  test    eax, eax
0x18000530f  jns     short loc_18000532C
0x180005311  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005318  jz      short loc_18000536F
0x18000531a  lea     rax, aCouldNotInitia; "Could not initialize native config read"...
0x180005321  mov     r8d, 971h
0x180005327  jmp     loc_180005187
0x18000532c  call    ?InitializeLookAsideList@MULTI_WORK_ITEM@@SAJXZ; MULTI_WORK_ITEM::InitializeLookAsideList(void)
0x180005331  mov     ebx, eax
0x180005333  test    eax, eax
0x180005335  jns     short loc_180005352
0x180005337  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000533e  jz      short loc_18000536F
0x180005340  lea     rax, aCouldNotInitia_2; "Could not initialize multi work item re"...
0x180005347  mov     r8d, 981h
0x18000534d  jmp     loc_180005187
0x180005352  lea     rax, ?s_WorkerProcessListHead@WORKER_PROCESS@@0U_LIST_ENTRY@@A; _LIST_ENTRY WORKER_PROCESS::s_WorkerProcessListHead
0x180005359  xor     ebx, ebx
0x18000535b  mov     cs:qword_180089200, rax
0x180005362  mov     cs:?s_WorkerProcessListHead@WORKER_PROCESS@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY WORKER_PROCESS::s_WorkerProcessListHead
0x180005369  mov     [rdi+648h], ebp
0x18000536f  mov     rbp, [rsp+38h+arg_8]
0x180005374  mov     eax, ebx
0x180005376  mov     rbx, [rsp+38h+arg_0]
0x18000537b  add     rsp, 30h
0x18000537f  pop     rdi
0x180005380  retn
```
