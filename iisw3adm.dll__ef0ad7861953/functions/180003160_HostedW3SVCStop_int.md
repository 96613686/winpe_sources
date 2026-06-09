# HostedW3SVCStop(int)

- ea: `0x180003160`
- end: `0x1800033d8`
- name: `?HostedW3SVCStop@@YAJH@Z`
- size: `632`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002c90`

## callees

- `0x180003160`
- `0x180005694`
- `0x180053c34`
- `0x1800540bc`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800031eb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800032bb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800031eb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800032bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003307`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18000322d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800032fd`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18000322d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800032fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003362`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000338e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003362`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000338e`
- `iisutil!PuDbgPrintError` at `0x180003280`
- `iisutil!PuDbgPrintError` at `0x180003350`
- `iisutil!PuDbgPrintError` at `0x180003280`
- `iisutil!PuDbgPrintError` at `0x180003350`

## string_xrefs

- `0x180003275`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\main.cxx`
- `0x180003345`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\main.cxx`
- `0x180003255`: `Main thread for hosted W3SVC failed\n`
- `0x180003325`: `Main thread for hosted W3SVC failed\n`

## pseudocode

```c
__int64 __fastcall HostedW3SVCStop(int a1)
{
  unsigned int v2; // ebx
  int v3; // edx
  int LastError; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  DWORD ExitCode; // [rsp+48h] [rbp+10h] BYREF

  ExitCode = 0;
  if ( !g_pWebAdminService && !g_pHttpService )
    return 1062;
  v2 = 0;
  if ( g_pHttpService && (unsigned int)(*((_DWORD *)g_pHttpService + 3) - 2) <= 2 )
  {
    v3 = 0;
    if ( !a1 )
      v3 = -2147467259;
    HTTP_SERVICE::InitiateStopService(g_pHttpService, v3, a1);
    if ( g_hHostedW3SVCMainThread )
    {
      if ( WaitForSingleObject(g_hHostedW3SVCMainThread, 0xFFFFFFFF) == -1 )
      {
        LastError = GetLastError();
        ExitCode = LastError;
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
            1453,
            "HostedW3SVCStop",
            v2,
            "WaitForSingleObject() failed\n");
      }
      else if ( !GetExitCodeThread(g_hHostedW3SVCMainThread, &ExitCode) )
      {
        v5 = GetLastError();
        ExitCode = v5;
        v2 = v5;
        if ( v5 > 0 )
          v2 = (unsigned __int16)v5 | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
            1469,
            "HostedW3SVCStop",
            v2,
            "Main thread for hosted W3SVC failed\n");
      }
    }
  }
  if ( g_pWebAdminService && (unsigned int)(*((_DWORD *)g_pWebAdminService + 283) - 2) <= 4 )
    WEB_ADMIN_SERVICE::InitiateStopService(g_pWebAdminService);
  if ( g_hHostedWASMainThread )
  {
    if ( WaitForSingleObject(g_hHostedWASMainThread, 0xFFFFFFFF) == -1 )
    {
      v6 = GetLastError();
      ExitCode = v6;
      v2 = v6;
      if ( v6 > 0 )
        v2 = (unsigned __int16)v6 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
          1514,
          "HostedW3SVCStop",
          v2,
          "WaitForSingleObject() failed\n");
    }
    else if ( !GetExitCodeThread(g_hHostedWASMainThread, &ExitCode) )
    {
      v7 = GetLastError();
      ExitCode = v7;
      v2 = v7;
      if ( v7 > 0 )
        v2 = (unsigned __int16)v7 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\main.cxx",
          1530,
          "HostedW3SVCStop",
          v2,
          "Main thread for hosted W3SVC failed\n");
    }
  }
  if ( g_hHostedW3SVCMainThread )
  {
    CloseHandle(g_hHostedW3SVCMainThread);
    g_hHostedW3SVCMainThread = 0;
  }
  if ( g_pHttpService )
    HTTP_SERVICE::DestroyHttpService();
  if ( g_hHostedWASMainThread )
  {
    CloseHandle(g_hHostedWASMainThread);
    g_hHostedWASMainThread = 0;
  }
  if ( g_pWebAdminService )
  {
    (*(void (__fastcall **)(WEB_ADMIN_SERVICE *))(*(_QWORD *)g_pWebAdminService + 8LL))(g_pWebAdminService);
    g_pWebAdminService = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180003160  mov     [rsp+arg_0], rbx
0x180003165  mov     [rsp+arg_10], rbp
0x18000316a  push    r13
0x18000316c  sub     rsp, 30h
0x180003170  cmp     cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA, 0; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180003178  mov     r8d, ecx; int
0x18000317b  mov     [rsp+38h+ExitCode], 0
0x180003183  jnz     short loc_180003199
0x180003185  cmp     cs:?g_pHttpService@@3PEAVHTTP_SERVICE@@EA, 0; HTTP_SERVICE * g_pHttpService
0x18000318d  jnz     short loc_180003199
0x18000318f  mov     eax, 426h
0x180003194  jmp     loc_1800033C7
0x180003199  mov     rcx, cs:?g_pHttpService@@3PEAVHTTP_SERVICE@@EA; this
0x1800031a0  lea     r13, aWaitforsingleo; "WaitForSingleObject() failed\n"
0x1800031a7  xor     ebx, ebx
0x1800031a9  mov     ebp, 80070000h
0x1800031ae  test    rcx, rcx
0x1800031b1  jz      loc_180003286
0x1800031b7  mov     eax, [rcx+0Ch]
0x1800031ba  sub     eax, 2
0x1800031bd  cmp     eax, 2
0x1800031c0  ja      loc_180003286
0x1800031c6  xor     edx, edx
0x1800031c8  mov     eax, 80004005h
0x1800031cd  test    r8d, r8d
0x1800031d0  cmovz   edx, eax; int
0x1800031d3  call    ?InitiateStopService@HTTP_SERVICE@@QEAAJJH@Z; HTTP_SERVICE::InitiateStopService(long,int)
0x1800031d8  mov     rcx, cs:?g_hHostedW3SVCMainThread@@3PEAXEA; hHandle
0x1800031df  test    rcx, rcx
0x1800031e2  jz      loc_180003286
0x1800031e8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800031eb  call    cs:__imp_WaitForSingleObject
0x1800031f1  cmp     eax, 0FFFFFFFFh
0x1800031f4  jnz     short loc_180003221
0x1800031f6  call    cs:__imp_GetLastError
0x1800031fc  mov     [rsp+38h+ExitCode], eax
0x180003200  mov     ebx, eax
0x180003202  test    eax, eax
0x180003204  jle     short loc_18000320B
0x180003206  movzx   ebx, ax
0x180003209  or      ebx, ebp
0x18000320b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003212  jz      short loc_180003286
0x180003214  mov     [rsp+38h+var_10], r13
0x180003219  mov     r8d, 5ADh
0x18000321f  jmp     short loc_180003267
0x180003221  mov     rcx, cs:?g_hHostedW3SVCMainThread@@3PEAXEA; hThread
0x180003228  lea     rdx, [rsp+38h+ExitCode]; lpExitCode
0x18000322d  call    cs:__imp_GetExitCodeThread
0x180003233  test    eax, eax
0x180003235  jnz     short loc_180003286
0x180003237  call    cs:__imp_GetLastError
0x18000323d  mov     [rsp+38h+ExitCode], eax
0x180003241  mov     ebx, eax
0x180003243  test    eax, eax
0x180003245  jle     short loc_18000324C
0x180003247  movzx   ebx, ax
0x18000324a  or      ebx, ebp
0x18000324c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003253  jz      short loc_180003286
0x180003255  lea     rax, aMainThreadForH; "Main thread for hosted W3SVC failed\n"
0x18000325c  mov     r8d, 5BDh
0x180003262  mov     [rsp+38h+var_10], rax
0x180003267  mov     rcx, cs:g_pDebug
0x18000326e  lea     r9, aHostedw3svcsto_0; "HostedW3SVCStop"
0x180003275  lea     rdx, aServercommonIn_39; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000327c  mov     [rsp+38h+var_18], ebx
0x180003280  call    cs:__imp_PuDbgPrintError
0x180003286  mov     rdx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18000328d  test    rdx, rdx
0x180003290  jz      short loc_1800032A8
0x180003292  mov     eax, [rdx+46Ch]
0x180003298  sub     eax, 2
0x18000329b  cmp     eax, 4
0x18000329e  ja      short loc_1800032A8
0x1800032a0  mov     rcx, rdx; this
0x1800032a3  call    ?InitiateStopService@WEB_ADMIN_SERVICE@@QEAAJXZ; WEB_ADMIN_SERVICE::InitiateStopService(void)
0x1800032a8  mov     rcx, cs:?g_hHostedWASMainThread@@3PEAXEA; hHandle
0x1800032af  test    rcx, rcx
0x1800032b2  jz      loc_180003356
0x1800032b8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800032bb  call    cs:__imp_WaitForSingleObject
0x1800032c1  cmp     eax, 0FFFFFFFFh
0x1800032c4  jnz     short loc_1800032F1
0x1800032c6  call    cs:__imp_GetLastError
0x1800032cc  mov     [rsp+38h+ExitCode], eax
0x1800032d0  mov     ebx, eax
0x1800032d2  test    eax, eax
0x1800032d4  jle     short loc_1800032DB
0x1800032d6  movzx   ebx, ax
0x1800032d9  or      ebx, ebp
0x1800032db  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800032e2  jz      short loc_180003356
0x1800032e4  mov     [rsp+38h+var_10], r13
0x1800032e9  mov     r8d, 5EAh
0x1800032ef  jmp     short loc_180003337
0x1800032f1  mov     rcx, cs:?g_hHostedWASMainThread@@3PEAXEA; hThread
0x1800032f8  lea     rdx, [rsp+38h+ExitCode]; lpExitCode
0x1800032fd  call    cs:__imp_GetExitCodeThread
0x180003303  test    eax, eax
0x180003305  jnz     short loc_180003356
0x180003307  call    cs:__imp_GetLastError
0x18000330d  mov     [rsp+38h+ExitCode], eax
0x180003311  mov     ebx, eax
0x180003313  test    eax, eax
0x180003315  jle     short loc_18000331C
0x180003317  movzx   ebx, ax
0x18000331a  or      ebx, ebp
0x18000331c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003323  jz      short loc_180003356
0x180003325  lea     rax, aMainThreadForH; "Main thread for hosted W3SVC failed\n"
0x18000332c  mov     r8d, 5FAh
0x180003332  mov     [rsp+38h+var_10], rax
0x180003337  mov     rcx, cs:g_pDebug
0x18000333e  lea     r9, aHostedw3svcsto_0; "HostedW3SVCStop"
0x180003345  lea     rdx, aServercommonIn_39; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000334c  mov     [rsp+38h+var_18], ebx
0x180003350  call    cs:__imp_PuDbgPrintError
0x180003356  mov     rcx, cs:?g_hHostedW3SVCMainThread@@3PEAXEA; hObject
0x18000335d  test    rcx, rcx
0x180003360  jz      short loc_180003373
0x180003362  call    cs:__imp_CloseHandle
0x180003368  mov     cs:?g_hHostedW3SVCMainThread@@3PEAXEA, 0; void * g_hHostedW3SVCMainThread
0x180003373  cmp     cs:?g_pHttpService@@3PEAVHTTP_SERVICE@@EA, 0; HTTP_SERVICE * g_pHttpService
0x18000337b  jz      short loc_180003382
0x18000337d  call    ?DestroyHttpService@HTTP_SERVICE@@SAXXZ; HTTP_SERVICE::DestroyHttpService(void)
0x180003382  mov     rcx, cs:?g_hHostedWASMainThread@@3PEAXEA; hObject
0x180003389  test    rcx, rcx
0x18000338c  jz      short loc_18000339F
0x18000338e  call    cs:__imp_CloseHandle
0x180003394  mov     cs:?g_hHostedWASMainThread@@3PEAXEA, 0; void * g_hHostedWASMainThread
0x18000339f  mov     rdx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x1800033a6  test    rdx, rdx
0x1800033a9  jz      short loc_1800033C5
0x1800033ab  mov     rcx, [rdx]
0x1800033ae  mov     rax, [rcx+8]
0x1800033b2  mov     rcx, rdx
0x1800033b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ba  mov     cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA, 0; WEB_ADMIN_SERVICE * g_pWebAdminService
0x1800033c5  mov     eax, ebx
0x1800033c7  mov     rbx, [rsp+38h+arg_0]
0x1800033cc  mov     rbp, [rsp+38h+arg_10]
0x1800033d1  add     rsp, 30h
0x1800033d5  pop     r13
0x1800033d7  retn
```
