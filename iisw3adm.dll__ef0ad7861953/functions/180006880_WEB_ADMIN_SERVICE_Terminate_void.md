# WEB_ADMIN_SERVICE::Terminate(void)

- ea: `0x180006880`
- end: `0x180006b80`
- name: `?Terminate@WEB_ADMIN_SERVICE@@AEAAXXZ`
- size: `768`
- prototype: `void __fastcall(WEB_ADMIN_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006b88`

## callees

- `0x180001274`
- `0x180003e24`
- `0x180004290`
- `0x180006880`
- `0x180007890`
- `0x180012ac4`
- `0x18002cdc0`
- `0x18005617c`
- `0x1800567b0`
- `0x180056e04`
- `0x18005f448`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006903`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006903`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006910`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006938`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006910`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006938`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006b69`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006b69`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x180006b5b`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x180006b5b`
- `iisutil!PuDbgPrint` at `0x1800068cc`
- `iisutil!PuDbgPrint` at `0x1800068cc`
- `iisutil!PuDbgPrintError` at `0x180006ad1`
- `iisutil!PuDbgPrintError` at `0x180006ad1`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180006b26`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180006b26`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180006b3d`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180006b3d`
- `iisutil!TerminateIISUtil` at `0x180006b51`
- `iisutil!TerminateIISUtil` at `0x180006b51`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180006ae6`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180006ae6`
- `nativerd!TerminateNativeConfiguration` at `0x180006b4b`
- `nativerd!TerminateNativeConfiguration` at `0x180006b4b`
- `CRYPTSP!CryptReleaseContext` at `0x180006a14`
- `CRYPTSP!CryptReleaseContext` at `0x180006a14`

## string_xrefs

- `0x1800068c5`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180006ac6`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x1800068ac`: `Initiating web admin service termination\n`
- `0x1800068b3`: `WEB_ADMIN_SERVICE::Terminate`
- `0x180006ab8`: `WEB_ADMIN_SERVICE::Terminate`
- `0x180006aa6`: `Could not cancel pending service status timer\n`

## pseudocode

```c
void __fastcall WEB_ADMIN_SERVICE::Terminate(WEB_ADMIN_SERVICE *this)
{
  void *v2; // rcx
  __int64 v3; // rsi
  void *v4; // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  void (__fastcall ***v7)(_QWORD, __int64); // rcx
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  __int64 v10; // rcx
  void (__fastcall ***v11)(_QWORD, __int64); // rcx
  WEB_ADMIN_SERVICE *v12; // rcx
  struct _TP_TIMER **v13; // rbx
  WAS_SQM_WRITER *v14; // rcx
  void (__fastcall ***v15)(_QWORD, __int64); // rcx
  WEB_ADMIN_SERVICE *v16; // rcx
  int v17; // eax
  void *v18; // rbx
  volatile signed __int32 *v19; // rbx

  if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
      3322,
      "WEB_ADMIN_SERVICE::Terminate",
      "Initiating web admin service termination\n");
  CONFIG_AND_CONTROL_MANAGER::StopChangeProcessing((WEB_ADMIN_SERVICE *)((char *)this + 688));
  UL_AND_WORKER_MANAGER::Terminate((WEB_ADMIN_SERVICE *)((char *)this + 112));
  CONFIG_AND_CONTROL_MANAGER::StopChangeProcessing((WEB_ADMIN_SERVICE *)((char *)this + 688));
  v2 = (void *)*((_QWORD *)this + 122);
  if ( v2 )
  {
    WaitForSingleObject(v2, 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 122));
    *((_QWORD *)this + 122) = 0;
    *((_DWORD *)this + 242) = 0;
  }
  v3 = *((_QWORD *)this + 120);
  if ( v3 )
  {
    v4 = *(void **)(v3 + 120);
    if ( v4 )
    {
      CloseHandle(v4);
      *(_QWORD *)(v3 + 120) = 0;
    }
    *(_DWORD *)(v3 + 16) = 5;
  }
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 91);
  if ( v5 )
  {
    (**v5)(v5, 1);
    *((_QWORD *)this + 91) = 0;
  }
  v6 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 92);
  if ( v6 )
  {
    (**v6)(v6, 1);
    *((_QWORD *)this + 92) = 0;
  }
  v7 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 93);
  if ( v7 )
  {
    (**v7)(v7, 1);
    *((_QWORD *)this + 93) = 0;
  }
  v8 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 94);
  if ( v8 )
  {
    (**v8)(v8, 1);
    *((_QWORD *)this + 94) = 0;
  }
  v9 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 95);
  if ( v9 )
  {
    (**v9)(v9, 1);
    *((_QWORD *)this + 95) = 0;
  }
  v10 = *((_QWORD *)this + 90);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v11 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 90);
    if ( v11 )
      (**v11)(v11, 1);
    *((_QWORD *)this + 90) = 0;
  }
  v12 = (WEB_ADMIN_SERVICE *)*((_QWORD *)this + 128);
  if ( v12 )
  {
    CryptReleaseContext((HCRYPTPROV)v12, 0);
    *((_QWORD *)this + 128) = 0;
  }
  v13 = (struct _TP_TIMER **)*((_QWORD *)this + 231);
  if ( v13 )
  {
    if ( v13[1] )
    {
      WEB_ADMIN_SERVICE::CancelTimer(v12, v13 + 1);
      v13[1] = 0;
    }
    WAS_SQM_WRITER::PopulateRuntimeData((WAS_SQM_WRITER *)v13);
    WAS_SQM_WRITER::WriteSQMRuntimeData(v14);
    WAS_SQM_WRITER::WriteTraceLoggingRuntimeData((WAS_SQM_WRITER *)v13);
    v15 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 231);
    if ( v15 )
      (**v15)(v15, 1);
    *((_QWORD *)this + 231) = 0;
  }
  WORK_QUEUE::Terminate((WEB_ADMIN_SERVICE *)((char *)this + 16));
  if ( *((_QWORD *)this + 145) )
  {
    v17 = WEB_ADMIN_SERVICE::CancelTimer(v16, (struct _TP_TIMER **)this + 145);
    if ( v17 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
          3386,
          "WEB_ADMIN_SERVICE::Terminate",
          v17,
          "Could not cancel pending service status timer\n");
    }
    else
    {
      *((_QWORD *)this + 145) = 0;
    }
  }
  v18 = MULTI_WORK_ITEM::sm_pAllocCacheHandler;
  if ( MULTI_WORK_ITEM::sm_pAllocCacheHandler )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)MULTI_WORK_ITEM::sm_pAllocCacheHandler);
    operator delete(v18);
    MULTI_WORK_ITEM::sm_pAllocCacheHandler = 0;
  }
  v19 = (volatile signed __int32 *)*((_QWORD *)this + 174);
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd(v19 + 5, 0xFFFFFFFF) == 1 )
    {
      TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY((TOKEN_CACHE_ENTRY *)v19);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, (void *)v19);
    }
    *((_QWORD *)this + 174) = 0;
  }
  CLKRHashTable::Clear((WEB_ADMIN_SERVICE *)((char *)this + 1240));
  TOKEN_CACHE::Terminate((WEB_ADMIN_SERVICE *)((char *)this + 1240));
  TerminateNativeConfiguration();
  TerminateIISUtil();
  CoFreeUnusedLibrariesEx(0, 0);
  if ( *((_DWORD *)this + 461) )
  {
    CoUninitialize();
    *((_DWORD *)this + 461) = 0;
  }
}

```

## disassembly

```asm
0x180006880  push    rbx
0x180006882  push    rbp
0x180006883  push    rsi
0x180006884  push    rdi
0x180006885  push    r14
0x180006887  sub     rsp, 30h
0x18000688b  mov     eax, cs:g_dwDebugFlags
0x180006891  mov     rdi, rcx
0x180006894  test    eax, 30000h
0x180006899  setnz   dl
0x18000689c  test    al, 3
0x18000689e  setnz   al
0x1800068a1  test    al, dl
0x1800068a3  jz      short loc_1800068D2
0x1800068a5  mov     rcx, cs:g_pDebug
0x1800068ac  lea     rax, aInitiatingWebA; "Initiating web admin service terminatio"...
0x1800068b3  lea     r9, aWebAdminServic_22; "WEB_ADMIN_SERVICE::Terminate"
0x1800068ba  mov     [rsp+58h+var_38], rax
0x1800068bf  mov     r8d, 0CFAh
0x1800068c5  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800068cc  call    cs:__imp_PuDbgPrint
0x1800068d2  lea     rbx, [rdi+2B0h]
0x1800068d9  mov     rcx, rbx; this
0x1800068dc  call    ?StopChangeProcessing@CONFIG_AND_CONTROL_MANAGER@@QEAAXXZ; CONFIG_AND_CONTROL_MANAGER::StopChangeProcessing(void)
0x1800068e1  lea     rcx, [rdi+70h]; this
0x1800068e5  call    ?Terminate@UL_AND_WORKER_MANAGER@@QEAAXXZ; UL_AND_WORKER_MANAGER::Terminate(void)
0x1800068ea  mov     rcx, rbx; this
0x1800068ed  call    ?StopChangeProcessing@CONFIG_AND_CONTROL_MANAGER@@QEAAXXZ; CONFIG_AND_CONTROL_MANAGER::StopChangeProcessing(void)
0x1800068f2  mov     rcx, [rbx+120h]; hHandle
0x1800068f9  xor     ebp, ebp
0x1800068fb  test    rcx, rcx
0x1800068fe  jz      short loc_180006923
0x180006900  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006903  call    cs:__imp_WaitForSingleObject
0x180006909  mov     rcx, [rbx+120h]; hObject
0x180006910  call    cs:__imp_CloseHandle
0x180006916  mov     [rbx+120h], rbp
0x18000691d  mov     [rbx+118h], ebp
0x180006923  mov     rsi, [rbx+110h]
0x18000692a  test    rsi, rsi
0x18000692d  jz      short loc_180006949
0x18000692f  mov     rcx, [rsi+78h]; hObject
0x180006933  test    rcx, rcx
0x180006936  jz      short loc_180006942
0x180006938  call    cs:__imp_CloseHandle
0x18000693e  mov     [rsi+78h], rbp
0x180006942  mov     dword ptr [rsi+10h], 5
0x180006949  mov     rcx, [rbx+28h]
0x18000694d  mov     r14d, 1
0x180006953  test    rcx, rcx
0x180006956  jz      short loc_18000696A
0x180006958  mov     rax, [rcx]
0x18000695b  mov     edx, r14d
0x18000695e  mov     rax, [rax]
0x180006961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006966  mov     [rbx+28h], rbp
0x18000696a  mov     rcx, [rbx+30h]
0x18000696e  test    rcx, rcx
0x180006971  jz      short loc_180006985
0x180006973  mov     rax, [rcx]
0x180006976  mov     edx, r14d
0x180006979  mov     rax, [rax]
0x18000697c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006981  mov     [rbx+30h], rbp
0x180006985  mov     rcx, [rbx+38h]
0x180006989  test    rcx, rcx
0x18000698c  jz      short loc_1800069A0
0x18000698e  mov     rax, [rcx]
0x180006991  mov     edx, r14d
0x180006994  mov     rax, [rax]
0x180006997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000699c  mov     [rbx+38h], rbp
0x1800069a0  mov     rcx, [rbx+40h]
0x1800069a4  test    rcx, rcx
0x1800069a7  jz      short loc_1800069BB
0x1800069a9  mov     rax, [rcx]
0x1800069ac  mov     edx, r14d
0x1800069af  mov     rax, [rax]
0x1800069b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069b7  mov     [rbx+40h], rbp
0x1800069bb  mov     rcx, [rbx+48h]
0x1800069bf  test    rcx, rcx
0x1800069c2  jz      short loc_1800069D6
0x1800069c4  mov     rax, [rcx]
0x1800069c7  mov     edx, r14d
0x1800069ca  mov     rax, [rax]
0x1800069cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069d2  mov     [rbx+48h], rbp
0x1800069d6  mov     rcx, [rbx+20h]
0x1800069da  test    rcx, rcx
0x1800069dd  jz      short loc_180006A06
0x1800069df  mov     rax, [rcx]
0x1800069e2  mov     rax, [rax+10h]
0x1800069e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069eb  mov     rcx, [rbx+20h]
0x1800069ef  test    rcx, rcx
0x1800069f2  jz      short loc_180006A02
0x1800069f4  mov     rax, [rcx]
0x1800069f7  mov     edx, r14d
0x1800069fa  mov     rax, [rax]
0x1800069fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a02  mov     [rbx+20h], rbp
0x180006a06  mov     rcx, [rbx+150h]; hProv
0x180006a0d  test    rcx, rcx
0x180006a10  jz      short loc_180006A21
0x180006a12  xor     edx, edx; dwFlags
0x180006a14  call    cs:__imp_CryptReleaseContext
0x180006a1a  mov     [rbx+150h], rbp
0x180006a21  mov     rbx, [rdi+738h]
0x180006a28  test    rbx, rbx
0x180006a2b  jz      short loc_180006A77
0x180006a2d  lea     rsi, [rbx+8]
0x180006a31  cmp     [rsi], rbp
0x180006a34  jz      short loc_180006A41
0x180006a36  mov     rdx, rsi; struct _TP_TIMER **
0x180006a39  call    ?CancelTimer@WEB_ADMIN_SERVICE@@QEAAJPEAPEAU_TP_TIMER@@@Z; WEB_ADMIN_SERVICE::CancelTimer(_TP_TIMER * *)
0x180006a3e  mov     [rsi], rbp
0x180006a41  mov     rcx, rbx; this
0x180006a44  call    ?PopulateRuntimeData@WAS_SQM_WRITER@@AEAAXXZ; WAS_SQM_WRITER::PopulateRuntimeData(void)
0x180006a49  call    ?WriteSQMRuntimeData@WAS_SQM_WRITER@@QEAAXXZ; WAS_SQM_WRITER::WriteSQMRuntimeData(void)
0x180006a4e  mov     rcx, rbx; this
0x180006a51  call    ?WriteTraceLoggingRuntimeData@WAS_SQM_WRITER@@AEAAXXZ; WAS_SQM_WRITER::WriteTraceLoggingRuntimeData(void)
0x180006a56  mov     rcx, [rdi+738h]
0x180006a5d  test    rcx, rcx
0x180006a60  jz      short loc_180006A70
0x180006a62  mov     rax, [rcx]
0x180006a65  mov     edx, r14d
0x180006a68  mov     rax, [rax]
0x180006a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a70  mov     [rdi+738h], rbp
0x180006a77  lea     rcx, [rdi+10h]; this
0x180006a7b  call    ?Terminate@WORK_QUEUE@@QEAAXXZ; WORK_QUEUE::Terminate(void)
0x180006a80  lea     rbx, [rdi+488h]
0x180006a87  cmp     [rbx], rbp
0x180006a8a  jz      short loc_180006AD7
0x180006a8c  mov     rdx, rbx; struct _TP_TIMER **
0x180006a8f  call    ?CancelTimer@WEB_ADMIN_SERVICE@@QEAAJPEAPEAU_TP_TIMER@@@Z; WEB_ADMIN_SERVICE::CancelTimer(_TP_TIMER * *)
0x180006a94  test    eax, eax
0x180006a96  js      short loc_180006A9D
0x180006a98  mov     [rbx], rbp
0x180006a9b  jmp     short loc_180006AD7
0x180006a9d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006aa4  jz      short loc_180006AD7
0x180006aa6  lea     rcx, aCouldNotCancel_2; "Could not cancel pending service status"...
0x180006aad  mov     r8d, 0D3Ah
0x180006ab3  mov     [rsp+58h+var_30], rcx
0x180006ab8  lea     r9, aWebAdminServic_22; "WEB_ADMIN_SERVICE::Terminate"
0x180006abf  mov     rcx, cs:g_pDebug
0x180006ac6  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006acd  mov     dword ptr [rsp+58h+var_38], eax
0x180006ad1  call    cs:__imp_PuDbgPrintError
0x180006ad7  mov     rbx, cs:?sm_pAllocCacheHandler@MULTI_WORK_ITEM@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * MULTI_WORK_ITEM::sm_pAllocCacheHandler
0x180006ade  test    rbx, rbx
0x180006ae1  jz      short loc_180006AFB
0x180006ae3  mov     rcx, rbx
0x180006ae6  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180006aec  mov     rcx, rbx; Block
0x180006aef  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006af4  mov     cs:?sm_pAllocCacheHandler@MULTI_WORK_ITEM@@0PEAVALLOC_CACHE_HANDLER@@EA, rbp; ALLOC_CACHE_HANDLER * MULTI_WORK_ITEM::sm_pAllocCacheHandler
0x180006afb  mov     rbx, [rdi+570h]
0x180006b02  test    rbx, rbx
0x180006b05  jz      short loc_180006B33
0x180006b07  or      eax, 0FFFFFFFFh
0x180006b0a  lock xadd [rbx+14h], eax
0x180006b0f  cmp     eax, r14d
0x180006b12  jnz     short loc_180006B2C
0x180006b14  mov     rcx, rbx; this
0x180006b17  call    ??1TOKEN_CACHE_ENTRY@@AEAA@XZ; TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(void)
0x180006b1c  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x180006b23  mov     rdx, rbx
0x180006b26  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180006b2c  mov     [rdi+570h], rbp
0x180006b33  lea     rbx, [rdi+4D8h]
0x180006b3a  mov     rcx, rbx
0x180006b3d  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x180006b43  mov     rcx, rbx; this
0x180006b46  call    ?Terminate@TOKEN_CACHE@@QEAAXXZ; TOKEN_CACHE::Terminate(void)
0x180006b4b  call    cs:__imp_?TerminateNativeConfiguration@@YAXXZ; TerminateNativeConfiguration(void)
0x180006b51  call    cs:__imp_TerminateIISUtil
0x180006b57  xor     edx, edx; dwReserved
0x180006b59  xor     ecx, ecx; dwUnloadDelay
0x180006b5b  call    cs:__imp_CoFreeUnusedLibrariesEx
0x180006b61  cmp     [rdi+734h], ebp
0x180006b67  jz      short loc_180006B75
0x180006b69  call    cs:__imp_CoUninitialize
0x180006b6f  mov     [rdi+734h], ebp
0x180006b75  add     rsp, 30h
0x180006b79  pop     r14
0x180006b7b  pop     rdi
0x180006b7c  pop     rsi
0x180006b7d  pop     rbp
0x180006b7e  pop     rbx
0x180006b7f  retn
```
