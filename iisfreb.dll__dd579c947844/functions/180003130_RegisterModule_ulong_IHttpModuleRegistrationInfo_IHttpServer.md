# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180003130`
- end: `0x180003437`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `775`
- prototype: `__int64 __fastcall(__int64, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task`

## callees

- `0x180001008`
- `0x180001d74`
- `0x180001f1c`
- `0x180003130`
- `0x180004274`
- `0x180008424`
- `0x1800097c4`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000316c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000316c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033ac`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800033a2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800033a2`
- `iisutil!PuCreateDebugPrintsObject` at `0x180003153`
- `iisutil!PuCreateDebugPrintsObject` at `0x180003153`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x18000319e`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x18000319e`
- `iisutil!IISGetPlatformType` at `0x1800031aa`
- `iisutil!IISGetPlatformType` at `0x1800031aa`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x1800032da`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x1800032da`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18000335e`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18000335e`

## string_xrefs

- `0x180003165`: `Unable to Create Debug Print Object \n`
- `0x180003197`: `System\CurrentControlSet\Services\W3SVC\Parameters\iisfreb`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  __int64 DebugPrintsObject; // rax
  _QWORD *v6; // rax
  signed int v7; // ebx
  _QWORD *v8; // rax
  struct IHttpTraceContext *v9; // rax
  EVENT_LOG *v10; // rbx
  int v11; // eax
  const unsigned __int16 *v12; // rdx
  void **v13; // rax
  void **v14; // rbx
  signed int LastError; // eax

  DebugPrintsObject = PuCreateDebugPrintsObject("iisfreb", 1);
  g_pDebug = DebugPrintsObject;
  if ( !DebugPrintsObject
    && (OutputDebugStringA("Unable to Create Debug Print Object \n"), (DebugPrintsObject = g_pDebug) == 0)
    || !*(_DWORD *)(DebugPrintsObject + 640) )
  {
    v7 = -2147467259;
    goto LABEL_27;
  }
  g_StartupState = 1;
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\iisfreb", 0);
  IISGetPlatformType();
  g_pModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  g_pGlobalInfo = a3;
  v6 = operator new(0x10u);
  if ( !v6 )
    goto LABEL_23;
  *v6 = &CIISModuleFactory::`vftable';
  v6[1] = &CIISHttpModule::`vftable';
  v7 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
         a2,
         v6,
         1,
         0);
  if ( v7 < 0 )
  {
LABEL_27:
    CleanupGlobals();
    return (unsigned int)v7;
  }
  v8 = operator new(8u);
  if ( !v8 )
  {
LABEL_23:
    v7 = -2147024888;
    goto LABEL_27;
  }
  *v8 = &CIISGlobalModule::`vftable';
  v7 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 24LL))(
         a2,
         v8,
         8448);
  if ( v7 < 0 )
    goto LABEL_27;
  v9 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 184LL))(g_pGlobalInfo);
  v7 = EnableWWWServerProvider(v9, 1);
  if ( v7 < 0 )
    goto LABEL_27;
  v7 = FREB_REQUEST_CONTEXT::Initialize();
  if ( v7 < 0 )
    goto LABEL_27;
  g_StartupState = 2;
  v10 = (EVENT_LOG *)operator new(4u);
  if ( !v10 )
  {
    FREB_LOG_NT_EVENT::sm_pEventLog = 0;
LABEL_25:
    v7 = -2147024882;
    goto LABEL_27;
  }
  v11 = (**(__int64 (__fastcall ***)(struct IHttpServer *))g_pGlobalInfo)(g_pGlobalInfo);
  v12 = L"HostableWebCore";
  if ( !v11 )
    v12 = L"W3SVC-WP";
  FREB_LOG_NT_EVENT::sm_pEventLog = EVENT_LOG::EVENT_LOG(v10, v12);
  if ( !FREB_LOG_NT_EVENT::sm_pEventLog )
    goto LABEL_25;
  g_StartupState = 3;
  v13 = (void **)operator new(0x58u);
  v14 = v13;
  if ( !v13 )
  {
    g_pFrebLogNtEventTable = 0;
    goto LABEL_23;
  }
  CLKRHashTable::CLKRHashTable(
    (CLKRHashTable *)(v13 + 1),
    "FREB_LOG_NT_EVENT_TABLE",
    (unsigned __int64 (*)(const void *))CTypedHashTable<FREB_LOG_NT_EVENT_TABLE,FREB_LOG_NT_EVENT,unsigned short const *,CLKRHashTable>::_ExtractKey,
    (unsigned int (*)(unsigned __int64))CTypedHashTable<FREB_LOG_NT_EVENT_TABLE,FREB_LOG_NT_EVENT,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<FREB_LOG_NT_EVENT_TABLE,FREB_LOG_NT_EVENT,unsigned short const *,CLKRHashTable>::_EqualKeys,
    (void (*)(const void *, int))CTypedHashTable<FREB_LOG_NT_EVENT_TABLE,FREB_LOG_NT_EVENT,unsigned short const *,CLKRHashTable>::_AddRefRecord,
    4.0,
    1u,
    0,
    0);
  *v14 = &FREB_LOG_NT_EVENT_TABLE::`vftable';
  v14[10] = 0;
  g_pFrebLogNtEventTable = (struct FREB_LOG_NT_EVENT_TABLE *)v14;
  if ( !CreateTimerQueueTimer(v14 + 10, 0, FREB_LOG_NT_EVENT_TABLE::ScavengerCallback, v14, 0x493E0u, 0x493E0u, 0x10u) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_27;
  }
  g_StartupState = 4;
  v7 = FREB_LOG_FILE_MANAGER::Initialize();
  if ( v7 < 0 )
    goto LABEL_27;
  g_StartupState = 5;
  v7 = FREB_XML_SERIALIZER::Initialize();
  if ( v7 < 0 )
    goto LABEL_27;
  g_StartupState = 6;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003130  mov     [rsp+arg_0], rbx
0x180003135  mov     [rsp+arg_8], rbp
0x18000313a  push    rdi
0x18000313b  sub     rsp, 50h
0x18000313f  mov     rdi, rdx
0x180003142  lea     rcx, aIisfreb; "iisfreb"
0x180003149  mov     ebp, 1
0x18000314e  mov     rbx, r8
0x180003151  mov     edx, ebp
0x180003153  call    cs:__imp_PuCreateDebugPrintsObject
0x180003159  mov     cs:g_pDebug, rax
0x180003160  test    rax, rax
0x180003163  jnz     short loc_180003182
0x180003165  lea     rcx, aUnableToCreate; "Unable to Create Debug Print Object \n"
0x18000316c  call    cs:__imp_OutputDebugStringA
0x180003172  mov     rax, cs:g_pDebug
0x180003179  test    rax, rax
0x18000317c  jz      loc_18000341B
0x180003182  cmp     dword ptr [rax+280h], 0
0x180003189  jz      loc_18000341B
0x18000318f  xor     edx, edx
0x180003191  mov     cs:?g_StartupState@@3W4FrebStartup@@A, ebp; FrebStartup g_StartupState
0x180003197  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x18000319e  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x1800031a4  mov     cs:g_dwDebugFlags, eax
0x1800031aa  call    cs:__imp_IISGetPlatformType
0x1800031b0  mov     rax, [rdi]
0x1800031b3  mov     rcx, rdi
0x1800031b6  mov     rax, [rax+8]
0x1800031ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031bf  mov     ecx, 10h; Size
0x1800031c4  mov     cs:?g_pModuleContext@@3PEAXEA, rax; void * g_pModuleContext
0x1800031cb  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * g_pGlobalInfo
0x1800031d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800031d7  mov     rdx, rax
0x1800031da  test    rax, rax
0x1800031dd  jz      loc_180003402
0x1800031e3  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x1800031ea  xor     r9d, r9d
0x1800031ed  mov     [rdx], rax
0x1800031f0  mov     r8d, ebp
0x1800031f3  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x1800031fa  mov     [rdx+8], rax
0x1800031fe  mov     rcx, [rdi]
0x180003201  mov     rax, [rcx+10h]
0x180003205  mov     rcx, rdi
0x180003208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000320d  mov     ebx, eax
0x18000320f  test    eax, eax
0x180003211  js      loc_180003420
0x180003217  mov     ecx, 8; Size
0x18000321c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003221  mov     rdx, rax
0x180003224  test    rax, rax
0x180003227  jz      loc_180003402
0x18000322d  lea     rax, ??_7CIISGlobalModule@@6B@; const CIISGlobalModule::`vftable'
0x180003234  mov     r8d, 2100h
0x18000323a  mov     [rdx], rax
0x18000323d  mov     rcx, [rdi]
0x180003240  mov     rax, [rcx+18h]
0x180003244  mov     rcx, rdi
0x180003247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000324c  mov     ebx, eax
0x18000324e  test    eax, eax
0x180003250  js      loc_180003420
0x180003256  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000325d  mov     rax, [rcx]
0x180003260  mov     rax, [rax+0B8h]
0x180003267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000326c  mov     rcx, rax; struct IHttpTraceContext *
0x18000326f  mov     edx, ebp; int
0x180003271  call    ?EnableWWWServerProvider@@YAJPEAVIHttpTraceContext@@H@Z; EnableWWWServerProvider(IHttpTraceContext *,int)
0x180003276  mov     ebx, eax
0x180003278  test    eax, eax
0x18000327a  js      loc_180003420
0x180003280  call    ?Initialize@FREB_REQUEST_CONTEXT@@SAJXZ; FREB_REQUEST_CONTEXT::Initialize(void)
0x180003285  mov     ebx, eax
0x180003287  test    eax, eax
0x180003289  js      loc_180003420
0x18000328f  mov     edi, 4
0x180003294  mov     cs:?g_StartupState@@3W4FrebStartup@@A, 2; FrebStartup g_StartupState
0x18000329e  mov     ecx, edi; Size
0x1800032a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800032a5  mov     rbx, rax
0x1800032a8  test    rax, rax
0x1800032ab  jz      loc_180003409
0x1800032b1  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800032b8  mov     rdx, [rcx]
0x1800032bb  mov     rax, [rdx]
0x1800032be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032c3  test    eax, eax
0x1800032c5  lea     rcx, aW3svcWp; "W3SVC-WP"
0x1800032cc  lea     rdx, aHostablewebcor; "HostableWebCore"
0x1800032d3  cmovz   rdx, rcx
0x1800032d7  mov     rcx, rbx
0x1800032da  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x1800032e0  mov     cs:?sm_pEventLog@FREB_LOG_NT_EVENT@@0PEAVEVENT_LOG@@EA, rax; EVENT_LOG * FREB_LOG_NT_EVENT::sm_pEventLog
0x1800032e7  test    rax, rax
0x1800032ea  jz      loc_180003414
0x1800032f0  lea     ecx, [rdi+54h]; Size
0x1800032f3  mov     cs:?g_StartupState@@3W4FrebStartup@@A, 3; FrebStartup g_StartupState
0x1800032fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003302  mov     rbx, rax
0x180003305  test    rax, rax
0x180003308  jz      loc_1800033F7
0x18000330e  movsd   xmm0, cs:__real@4010000000000000
0x180003316  lea     rcx, [rax+8]
0x18000331a  mov     [rsp+58h+var_10], 0
0x18000331f  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VFREB_LOG_NT_EVENT_TABLE@@VFREB_LOG_NT_EVENT@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<FREB_LOG_NT_EVENT_TABLE,FREB_LOG_NT_EVENT,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x180003326  mov     [rsp+58h+var_18], 0
0x18000332e  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VFREB_LOG_NT_EVENT_TABLE@@VFREB_LOG_NT_EVENT@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<FREB_LOG_NT_EVENT_TABLE,FREB_LOG_NT_EVENT,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180003335  mov     [rsp+58h+var_20], ebp
0x180003339  lea     r8, ?_ExtractKey@?$CTypedHashTable@VFREB_LOG_NT_EVENT_TABLE@@VFREB_LOG_NT_EVENT@@PEBGVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<FREB_LOG_NT_EVENT_TABLE,FREB_LOG_NT_EVENT,ushort const *,CLKRHashTable>::_ExtractKey(void const *)
0x180003340  movsd   qword ptr [rsp+58h+Flags], xmm0
0x180003346  lea     rdx, aFrebLogNtEvent; "FREB_LOG_NT_EVENT_TABLE"
0x18000334d  mov     qword ptr [rsp+58h+Period], rax
0x180003352  lea     rax, ?_EqualKeys@?$CTypedHashTable@VFREB_LOG_NT_EVENT_TABLE@@VFREB_LOG_NT_EVENT@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<FREB_LOG_NT_EVENT_TABLE,FREB_LOG_NT_EVENT,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180003359  mov     qword ptr [rsp+58h+DueTime], rax
0x18000335e  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x180003364  lea     rax, ??_7FREB_LOG_NT_EVENT_TABLE@@6B@; const FREB_LOG_NT_EVENT_TABLE::`vftable'
0x18000336b  mov     [rsp+58h+Flags], 10h; Flags
0x180003373  mov     [rbx], rax
0x180003376  lea     rcx, [rbx+50h]; phNewTimer
0x18000337a  mov     eax, 493E0h
0x18000337f  mov     qword ptr [rbx+50h], 0
0x180003387  mov     [rsp+58h+Period], eax; Period
0x18000338b  lea     r8, ?ScavengerCallback@FREB_LOG_NT_EVENT_TABLE@@CAXPEAXE@Z; Callback
0x180003392  mov     r9, rbx; Parameter
0x180003395  mov     [rsp+58h+DueTime], eax; DueTime
0x180003399  xor     edx, edx; TimerQueue
0x18000339b  mov     cs:?g_pFrebLogNtEventTable@@3PEAVFREB_LOG_NT_EVENT_TABLE@@EA, rbx; FREB_LOG_NT_EVENT_TABLE * g_pFrebLogNtEventTable
0x1800033a2  call    cs:__imp_CreateTimerQueueTimer
0x1800033a8  test    eax, eax
0x1800033aa  jnz     short loc_1800033C5
0x1800033ac  call    cs:__imp_GetLastError
0x1800033b2  mov     ebx, eax
0x1800033b4  test    eax, eax
0x1800033b6  jle     short loc_1800033C1
0x1800033b8  movzx   ebx, ax
0x1800033bb  or      ebx, 80070000h
0x1800033c1  test    ebx, ebx
0x1800033c3  js      short loc_180003420
0x1800033c5  mov     cs:?g_StartupState@@3W4FrebStartup@@A, edi; FrebStartup g_StartupState
0x1800033cb  call    ?Initialize@FREB_LOG_FILE_MANAGER@@SAJXZ; FREB_LOG_FILE_MANAGER::Initialize(void)
0x1800033d0  mov     ebx, eax
0x1800033d2  test    eax, eax
0x1800033d4  js      short loc_180003420
0x1800033d6  mov     cs:?g_StartupState@@3W4FrebStartup@@A, 5; FrebStartup g_StartupState
0x1800033e0  call    ?Initialize@FREB_XML_SERIALIZER@@SAJXZ; FREB_XML_SERIALIZER::Initialize(void)
0x1800033e5  mov     ebx, eax
0x1800033e7  test    eax, eax
0x1800033e9  js      short loc_180003420
0x1800033eb  mov     cs:?g_StartupState@@3W4FrebStartup@@A, 6; FrebStartup g_StartupState
0x1800033f5  jmp     short loc_180003425
0x1800033f7  mov     cs:?g_pFrebLogNtEventTable@@3PEAVFREB_LOG_NT_EVENT_TABLE@@EA, 0; FREB_LOG_NT_EVENT_TABLE * g_pFrebLogNtEventTable
0x180003402  mov     ebx, 80070008h
0x180003407  jmp     short loc_180003420
0x180003409  mov     cs:?sm_pEventLog@FREB_LOG_NT_EVENT@@0PEAVEVENT_LOG@@EA, 0; EVENT_LOG * FREB_LOG_NT_EVENT::sm_pEventLog
0x180003414  mov     ebx, 8007000Eh
0x180003419  jmp     short loc_180003420
0x18000341b  mov     ebx, 80004005h
0x180003420  call    ?CleanupGlobals@@YAXXZ; CleanupGlobals(void)
0x180003425  mov     rbp, [rsp+58h+arg_8]
0x18000342a  mov     eax, ebx
0x18000342c  mov     rbx, [rsp+58h+arg_0]
0x180003431  add     rsp, 50h
0x180003435  pop     rdi
0x180003436  retn
```
