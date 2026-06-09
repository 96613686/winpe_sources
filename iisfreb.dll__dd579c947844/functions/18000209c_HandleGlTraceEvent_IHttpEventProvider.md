# HandleGlTraceEvent(IHttpEventProvider *)

- ea: `0x18000209c`
- end: `0x1800023c4`
- name: `?HandleGlTraceEvent@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIHttpEventProvider@@@Z`
- size: `808`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002ba0`

## callees

- `0x18000209c`
- `0x180002798`
- `0x180003654`
- `0x180003d0c`
- `0x180004604`
- `0x180005588`
- `0x18000a6a8`
- `0x18000b010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000214a`
- `iisutil!PuDbgPrint` at `0x18000214a`

## string_xrefs

- `0x180002143`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_module.cxx`

## pseudocode

```c
__int64 __fastcall HandleGlTraceEvent(__int64 *a1)
{
  __int64 v1; // rax
  int v3; // eax
  FREB_LOG_NT_EVENT_TABLE *v4; // rcx
  int v5; // ebx
  int v6; // edi
  LPCGUID pAreaGuid; // rcx
  __int64 v8; // rax
  struct IHttpContext *v9; // r14
  struct IHttpModuleContextContainer *v10; // rsi
  struct FREB_REQUEST_CONTEXT *v11; // rbx
  struct HTTP_TRACE_EVENT *v12; // rcx
  __int64 v13; // rax
  DWORD dwVerbosity; // eax
  _QWORD *p_Data1; // rdx
  const unsigned __int16 *v16; // rdx
  struct FREB_REQUEST_CONTEXT *v18; // [rsp+70h] [rbp+40h] BYREF
  struct HTTP_TRACE_EVENT *v19; // [rsp+78h] [rbp+48h] BYREF
  struct IHttpContext *v20; // [rsp+80h] [rbp+50h] BYREF
  _WORD *v21; // [rsp+88h] [rbp+58h] BYREF

  v1 = *a1;
  v20 = 0;
  v19 = 0;
  if ( !(*(unsigned int (__fastcall **)(__int64 *, void *))(v1 + 16))(a1, g_pModuleContext)
    || (*(int (__fastcall **)(__int64 *, struct IHttpContext **))(*a1 + 24))(a1, &v20) < 0 )
  {
    return 0;
  }
  v3 = (*(__int64 (__fastcall **)(__int64 *, struct HTTP_TRACE_EVENT **))(*a1 + 8))(a1, &v19);
  v5 = v3;
  if ( v3 < 0 )
  {
    FREB_LOG_NT_EVENT_TABLE::LogEventFrebRuntimeError(v4, v3);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_module.cxx",
        580,
        "HandleGlTraceEvent",
        "Failed to retrieve trace event hr=0x%x",
        v5);
    return 0;
  }
  v6 = 0;
  pAreaGuid = v19->pAreaGuid;
  if ( pAreaGuid )
  {
    v8 = *(_QWORD *)&pAreaGuid->Data1 - *(_QWORD *)&`IISGeneralEvents::GetAreaGuid'::`2'::AreaGuid.Data1;
    if ( *(_QWORD *)&pAreaGuid->Data1 == *(_QWORD *)&`IISGeneralEvents::GetAreaGuid'::`2'::AreaGuid.Data1 )
      v8 = *(_QWORD *)pAreaGuid->Data4 - *(_QWORD *)`IISGeneralEvents::GetAreaGuid'::`2'::AreaGuid.Data4;
    if ( !v8 )
      v6 = 1;
  }
  v9 = (struct IHttpContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v20 + 240LL))(v20);
  v10 = (struct IHttpModuleContextContainer *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v9 + 56LL))(v9);
  v18 = (struct FREB_REQUEST_CONTEXT *)(**(__int64 (__fastcall ***)(struct IHttpModuleContextContainer *, void *))v10)(
                                         v10,
                                         g_pModuleContext);
  v11 = v18;
  if ( v6 && v19->dwEvent == 1 )
  {
    if ( (int)HandleWWWServerGeneralRequestStart(v20, v10, &v18) < 0 )
      return 0;
    v11 = v18;
  }
  if ( !v11 )
    return 0;
  FREB_REQUEST_CONTEXT::BufferTraceEventInMemory(v11, v9, v19);
  if ( v6 )
  {
    v12 = v19;
    if ( v19->dwEvent != 2 )
      goto LABEL_25;
    if ( !(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v20 + 232LL))(v20)
      && !*((_DWORD *)v11 + 58)
      && !*((_QWORD *)v11 + 7) )
    {
      v13 = *((_QWORD *)v11 + 9);
      if ( v13 )
      {
        if ( *(_DWORD *)(v13 + 12) && TryReadRequestConfig(v20, v11) < 0 )
          return 0;
      }
    }
  }
  v12 = v19;
LABEL_25:
  if ( *((_QWORD *)v11 + 10) )
  {
    dwVerbosity = v12->dwVerbosity;
    if ( dwVerbosity && dwVerbosity <= *((_DWORD *)v11 + 22) )
    {
      *((_DWORD *)v11 + 51) = 1;
      *((_DWORD *)v11 + 57) = 1;
      v12 = v19;
    }
    if ( v6 && v12->dwEvent == 2 )
    {
      FREB_REQUEST_CONTEXT::MatchFailureDefinitionsStatusCode(v11, v20);
      v21 = 0;
      LODWORD(v18) = 0;
      if ( (*(int (__fastcall **)(struct IHttpContext *, const char *, _WORD **, struct FREB_REQUEST_CONTEXT **))(*(_QWORD *)v20 + 128LL))(
             v20,
             "IIS_EnableFailedRequestLog",
             &v21,
             &v18) >= 0
        && *v21 == 49 )
      {
        *((_DWORD *)v11 + 51) = 1;
        *((_DWORD *)v11 + 52) = 1;
      }
      v12 = v19;
    }
    if ( v12->dwEvent - 16 <= 1 )
    {
      p_Data1 = &v12->pAreaGuid->Data1;
      if ( p_Data1 )
      {
        if ( *p_Data1 == *(_QWORD *)&`IISRequestNotificationEvents::GetAreaGuid'::`2'::AreaGuid.Data1
          && p_Data1[1] == *(_QWORD *)`IISRequestNotificationEvents::GetAreaGuid'::`2'::AreaGuid.Data4 )
        {
          FREB_REQUEST_CONTEXT::MatchFailureDefinitionsStatusCode(v11, v20);
          v12 = v19;
        }
      }
    }
    if ( v6
      && v12->dwEvent == 2
      && !(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v20 + 232LL))(v20)
      && *((_DWORD *)v11 + 51) )
    {
      if ( *((_DWORD *)v11 + 53) )
      {
        v16 = L"STATUS_CODE";
      }
      else if ( *((_DWORD *)v11 + 52) )
      {
        v16 = L"SERVER_VARIABLE";
      }
      else if ( *((_DWORD *)v11 + 57) )
      {
        v16 = L"EVENT_VERBOSITY_LEVEL";
      }
      else
      {
        v16 = L"TIME_TAKEN";
        if ( !*((_DWORD *)v11 + 54) )
          v16 = L"UNKNOWN";
      }
      FREB_REQUEST_CONTEXT::WriteTraceEventsToFile(v11, v16);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000209c  push    rbp
0x18000209e  push    rbx
0x18000209f  push    rsi
0x1800020a0  push    rdi
0x1800020a1  push    r12
0x1800020a3  push    r14
0x1800020a5  push    r15
0x1800020a7  mov     rbp, rsp
0x1800020aa  sub     rsp, 30h
0x1800020ae  mov     rax, [rcx]
0x1800020b1  xor     r15d, r15d
0x1800020b4  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x1800020bb  mov     rbx, rcx
0x1800020be  mov     [rbp+arg_10], r15
0x1800020c2  mov     [rbp+arg_8], r15
0x1800020c6  mov     rax, [rax+10h]
0x1800020ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020cf  test    eax, eax
0x1800020d1  jz      loc_1800023B3
0x1800020d7  mov     rax, [rbx]
0x1800020da  lea     rdx, [rbp+arg_10]
0x1800020de  mov     rcx, rbx
0x1800020e1  mov     rax, [rax+18h]
0x1800020e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ea  test    eax, eax
0x1800020ec  js      loc_1800023B3
0x1800020f2  mov     rax, [rbx]
0x1800020f5  lea     rdx, [rbp+arg_8]
0x1800020f9  mov     rcx, rbx
0x1800020fc  mov     rax, [rax+8]
0x180002100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002105  mov     ebx, eax
0x180002107  test    eax, eax
0x180002109  jns     short loc_180002155
0x18000210b  mov     edx, eax; int
0x18000210d  call    ?LogEventFrebRuntimeError@FREB_LOG_NT_EVENT_TABLE@@QEAAXJ@Z; FREB_LOG_NT_EVENT_TABLE::LogEventFrebRuntimeError(long)
0x180002112  test    byte ptr cs:g_dwDebugFlags, 3
0x180002119  jz      loc_1800023B3
0x18000211f  mov     rcx, cs:g_pDebug
0x180002126  lea     rax, aFailedToRetrie; "Failed to retrieve trace event hr=0x%x"
0x18000212d  mov     [rsp+30h+var_8], ebx
0x180002131  lea     r9, aHandlegltracee; "HandleGlTraceEvent"
0x180002138  mov     r8d, 244h
0x18000213e  mov     [rsp+30h+var_10], rax
0x180002143  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000214a  call    cs:__imp_PuDbgPrint
0x180002150  jmp     loc_1800023B3
0x180002155  mov     rax, [rbp+arg_8]
0x180002159  mov     edi, r15d
0x18000215c  mov     r12d, 1
0x180002162  mov     rcx, [rax+10h]
0x180002166  test    rcx, rcx
0x180002169  jz      short loc_180002189
0x18000216b  mov     rax, [rcx]
0x18000216e  sub     rax, qword ptr cs:?AreaGuid@?1??GetAreaGuid@IISGeneralEvents@@SAPEBU_GUID@@XZ@4U3@B.Data1; _GUID const `IISGeneralEvents::GetAreaGuid(void)'::`2'::AreaGuid ...
0x180002175  jnz     short loc_180002182
0x180002177  mov     rax, [rcx+8]
0x18000217b  sub     rax, qword ptr cs:?AreaGuid@?1??GetAreaGuid@IISGeneralEvents@@SAPEBU_GUID@@XZ@4U3@B.Data4; _GUID const `IISGeneralEvents::GetAreaGuid(void)'::`2'::AreaGuid ...
0x180002182  test    rax, rax
0x180002185  cmovz   edi, r12d
0x180002189  mov     rcx, [rbp+arg_10]
0x18000218d  mov     rax, [rcx]
0x180002190  mov     rax, [rax+0F0h]
0x180002197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000219c  mov     r14, rax
0x18000219f  mov     rcx, [rax]
0x1800021a2  mov     rax, [rcx+38h]
0x1800021a6  mov     rcx, r14
0x1800021a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021ae  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x1800021b5  mov     rsi, rax
0x1800021b8  mov     rcx, [rax]
0x1800021bb  mov     rax, [rcx]
0x1800021be  mov     rcx, rsi
0x1800021c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021c6  mov     [rbp+arg_0], rax
0x1800021ca  mov     rbx, rax
0x1800021cd  test    edi, edi
0x1800021cf  jz      short loc_1800021F7
0x1800021d1  mov     rcx, [rbp+arg_8]
0x1800021d5  cmp     [rcx+18h], r12d
0x1800021d9  jnz     short loc_1800021F7
0x1800021db  mov     rcx, [rbp+arg_10]; struct IHttpContext *
0x1800021df  lea     r8, [rbp+arg_0]; struct FREB_REQUEST_CONTEXT **
0x1800021e3  mov     rdx, rsi; struct IHttpModuleContextContainer *
0x1800021e6  call    ?HandleWWWServerGeneralRequestStart@@YAJPEAVIHttpContext@@PEAVIHttpModuleContextContainer@@PEAPEAVFREB_REQUEST_CONTEXT@@@Z; HandleWWWServerGeneralRequestStart(IHttpContext *,IHttpModuleContextContainer *,FREB_REQUEST_CONTEXT * *)
0x1800021eb  test    eax, eax
0x1800021ed  js      loc_1800023B3
0x1800021f3  mov     rbx, [rbp+arg_0]
0x1800021f7  test    rbx, rbx
0x1800021fa  jz      loc_1800023B3
0x180002200  mov     r8, [rbp+arg_8]; struct HTTP_TRACE_EVENT *
0x180002204  mov     rdx, r14; struct IHttpContext *
0x180002207  mov     rcx, rbx; this
0x18000220a  call    ?BufferTraceEventInMemory@FREB_REQUEST_CONTEXT@@QEAAXPEAVIHttpContext@@PEBUHTTP_TRACE_EVENT@@@Z; FREB_REQUEST_CONTEXT::BufferTraceEventInMemory(IHttpContext *,HTTP_TRACE_EVENT const *)
0x18000220f  test    edi, edi
0x180002211  jz      short loc_180002267
0x180002213  mov     rcx, [rbp+arg_8]
0x180002217  cmp     dword ptr [rcx+18h], 2
0x18000221b  jnz     short loc_18000226B
0x18000221d  mov     rcx, [rbp+arg_10]
0x180002221  mov     rax, [rcx]
0x180002224  mov     rax, [rax+0E8h]
0x18000222b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002230  test    rax, rax
0x180002233  jnz     short loc_180002267
0x180002235  cmp     [rbx+0E8h], r15d
0x18000223c  jnz     short loc_180002267
0x18000223e  cmp     [rbx+38h], r15
0x180002242  jnz     short loc_180002267
0x180002244  mov     rax, [rbx+48h]
0x180002248  test    rax, rax
0x18000224b  jz      short loc_180002267
0x18000224d  cmp     [rax+0Ch], r15d
0x180002251  jz      short loc_180002267
0x180002253  mov     rcx, [rbp+arg_10]; struct IHttpContext *
0x180002257  mov     rdx, rbx; struct FREB_REQUEST_CONTEXT *
0x18000225a  call    ?TryReadRequestConfig@@YAJPEAVIHttpContext@@PEAVFREB_REQUEST_CONTEXT@@@Z; TryReadRequestConfig(IHttpContext *,FREB_REQUEST_CONTEXT *)
0x18000225f  test    eax, eax
0x180002261  js      loc_1800023B3
0x180002267  mov     rcx, [rbp+arg_8]
0x18000226b  cmp     [rbx+50h], r15
0x18000226f  jz      loc_1800023B3
0x180002275  mov     eax, [rcx+2Ch]
0x180002278  cmp     eax, r12d
0x18000227b  jb      short loc_180002294
0x18000227d  cmp     eax, [rbx+58h]
0x180002280  ja      short loc_180002294
0x180002282  mov     [rbx+0CCh], r12d
0x180002289  mov     [rbx+0E4h], r12d
0x180002290  mov     rcx, [rbp+arg_8]
0x180002294  test    edi, edi
0x180002296  jz      short loc_1800022F4
0x180002298  cmp     dword ptr [rcx+18h], 2
0x18000229c  jnz     short loc_1800022F4
0x18000229e  mov     rdx, [rbp+arg_10]; struct IHttpContext *
0x1800022a2  mov     rcx, rbx; this
0x1800022a5  call    ?MatchFailureDefinitionsStatusCode@FREB_REQUEST_CONTEXT@@QEAAXPEAVIHttpContext@@@Z; FREB_REQUEST_CONTEXT::MatchFailureDefinitionsStatusCode(IHttpContext *)
0x1800022aa  mov     rcx, [rbp+arg_10]
0x1800022ae  lea     r9, [rbp+arg_0]
0x1800022b2  lea     r8, [rbp+arg_18]
0x1800022b6  mov     [rbp+arg_18], r15
0x1800022ba  lea     rdx, aIisEnablefaile; "IIS_EnableFailedRequestLog"
0x1800022c1  mov     dword ptr [rbp+arg_0], r15d
0x1800022c5  mov     rax, [rcx]
0x1800022c8  mov     rax, [rax+80h]
0x1800022cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022d4  test    eax, eax
0x1800022d6  js      short loc_1800022F0
0x1800022d8  mov     rax, [rbp+arg_18]
0x1800022dc  cmp     word ptr [rax], 31h ; '1'
0x1800022e0  jnz     short loc_1800022F0
0x1800022e2  mov     [rbx+0CCh], r12d
0x1800022e9  mov     [rbx+0D0h], r12d
0x1800022f0  mov     rcx, [rbp+arg_8]
0x1800022f4  mov     eax, [rcx+18h]
0x1800022f7  sub     eax, 10h
0x1800022fa  cmp     eax, r12d
0x1800022fd  ja      short loc_180002331
0x1800022ff  mov     rdx, [rcx+10h]
0x180002303  test    rdx, rdx
0x180002306  jz      short loc_180002331
0x180002308  mov     rax, [rdx]
0x18000230b  cmp     rax, qword ptr cs:?AreaGuid@?1??GetAreaGuid@IISRequestNotificationEvents@@SAPEBU_GUID@@XZ@4U3@B.Data1; _GUID const `IISRequestNotificationEvents::GetAreaGuid(void)'::`2'::AreaGuid ...
0x180002312  jnz     short loc_180002331
0x180002314  mov     rax, [rdx+8]
0x180002318  cmp     rax, qword ptr cs:?AreaGuid@?1??GetAreaGuid@IISRequestNotificationEvents@@SAPEBU_GUID@@XZ@4U3@B.Data4; _GUID const `IISRequestNotificationEvents::GetAreaGuid(void)'::`2'::AreaGuid ...
0x18000231f  jnz     short loc_180002331
0x180002321  mov     rdx, [rbp+arg_10]; struct IHttpContext *
0x180002325  mov     rcx, rbx; this
0x180002328  call    ?MatchFailureDefinitionsStatusCode@FREB_REQUEST_CONTEXT@@QEAAXPEAVIHttpContext@@@Z; FREB_REQUEST_CONTEXT::MatchFailureDefinitionsStatusCode(IHttpContext *)
0x18000232d  mov     rcx, [rbp+arg_8]
0x180002331  test    edi, edi
0x180002333  jz      short loc_1800023B3
0x180002335  cmp     dword ptr [rcx+18h], 2
0x180002339  jnz     short loc_1800023B3
0x18000233b  mov     rcx, [rbp+arg_10]
0x18000233f  mov     rax, [rcx]
0x180002342  mov     rax, [rax+0E8h]
0x180002349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000234e  test    rax, rax
0x180002351  jnz     short loc_1800023B3
0x180002353  cmp     [rbx+0CCh], r15d
0x18000235a  jz      short loc_1800023B3
0x18000235c  cmp     [rbx+0D4h], r15d
0x180002363  jz      short loc_18000236E
0x180002365  lea     rdx, aStatusCode; "STATUS_CODE"
0x18000236c  jmp     short loc_1800023AB
0x18000236e  cmp     [rbx+0D0h], r15d
0x180002375  jz      short loc_180002380
0x180002377  lea     rdx, aServerVariable; "SERVER_VARIABLE"
0x18000237e  jmp     short loc_1800023AB
0x180002380  cmp     [rbx+0E4h], r15d
0x180002387  jz      short loc_180002392
0x180002389  lea     rdx, aEventVerbosity; "EVENT_VERBOSITY_LEVEL"
0x180002390  jmp     short loc_1800023AB
0x180002392  cmp     [rbx+0D8h], r15d
0x180002399  lea     rdx, aTimeTaken; "TIME_TAKEN"
0x1800023a0  lea     rax, aUnknown; "UNKNOWN"
0x1800023a7  cmovz   rdx, rax; unsigned __int16 *
0x1800023ab  mov     rcx, rbx; this
0x1800023ae  call    ?WriteTraceEventsToFile@FREB_REQUEST_CONTEXT@@QEAAJPEBG@Z; FREB_REQUEST_CONTEXT::WriteTraceEventsToFile(ushort const *)
0x1800023b3  xor     eax, eax
0x1800023b5  add     rsp, 30h
0x1800023b9  pop     r15
0x1800023bb  pop     r14
0x1800023bd  pop     r12
0x1800023bf  pop     rdi
0x1800023c0  pop     rsi
0x1800023c1  pop     rbx
0x1800023c2  pop     rbp
0x1800023c3  retn
```
