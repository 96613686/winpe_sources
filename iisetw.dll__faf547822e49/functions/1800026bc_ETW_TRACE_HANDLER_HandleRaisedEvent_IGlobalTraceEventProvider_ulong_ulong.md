# ETW_TRACE_HANDLER::HandleRaisedEvent(IGlobalTraceEventProvider *,ulong *,ulong *)

- ea: `0x1800026bc`
- end: `0x180002c17`
- name: `?HandleRaisedEvent@ETW_TRACE_HANDLER@@SAJPEAVIGlobalTraceEventProvider@@PEAK1@Z`
- size: `1371`
- prototype: `__int64 __fastcall(struct IGlobalTraceEventProvider *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000265c`

## callees

- `0x1800019a4`
- `0x1800026bc`
- `0x180003020`
- `0x180003406`
- `0x180003430`
- `0x180004010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800028f8`
- `msvcrt!_wcsicmp` at `0x18000291a`
- `msvcrt!_wcsicmp` at `0x18000293c`
- `msvcrt!_wcsicmp` at `0x180002a1a`
- `msvcrt!_wcsicmp` at `0x1800028f8`
- `msvcrt!_wcsicmp` at `0x18000291a`
- `msvcrt!_wcsicmp` at `0x18000293c`
- `msvcrt!_wcsicmp` at `0x180002a1a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180002b19`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180002b39`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180002bdc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180002b19`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180002b39`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180002bdc`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180002bc0`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180002bc0`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_ETW_TRACE_EVENT@@@Z` at `0x180002b4c`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_ETW_TRACE_EVENT@@@Z` at `0x180002b4c`
- `iisutil!PuDbgPrint` at `0x180002797`
- `iisutil!PuDbgPrint` at `0x180002797`

## string_xrefs

- `0x18000277e`: `servercommon\inetsrv\iis\iisrearc\iis70\etw\etw_trace_handler.cxx`

## pseudocode

```c
__int64 __fastcall ETW_TRACE_HANDLER::HandleRaisedEvent(
        struct IGlobalTraceEventProvider *a1,
        unsigned int *a2,
        unsigned int *a3)
{
  __int64 v4; // rax
  int v5; // eax
  int v6; // esi
  void **v7; // rcx
  struct HTTP_TRACE_EVENT *v8; // r14
  int v9; // edi
  __int64 v10; // rbx
  LPCGUID pProviderGuid; // rdx
  void **v12; // r11
  LPCGUID v13; // r13
  const struct _GUID *IISProviderGUID; // rax
  __int64 v15; // r11
  CEtwTracer *v16; // r13
  __int64 v18; // rax
  int (__fastcall *v19)(struct IGlobalTraceEventProvider *, __int64 *); // rax
  GUID *v20; // r14
  struct HTTP_TRACE_EVENT *v21; // rdx
  GUID *v22; // rax
  GUID *v23; // rax
  GUID *pRelatedActivityGuid; // rax
  GUID *v25; // rax
  unsigned int v26; // edi
  GUID *pActivityGuid; // rax
  GUID *v28; // rax
  HTTP_TRACE_EVENT_ITEM *pEventItems; // r10
  GUID *pbData; // rax
  GUID *v31; // r10
  __int64 v32; // r8
  ULONG cbData; // ecx
  unsigned int v34; // edi
  int v35; // [rsp+30h] [rbp-D0h] BYREF
  struct HTTP_TRACE_EVENT *v36; // [rsp+38h] [rbp-C8h] BYREF
  CEtwTracer *v37; // [rsp+40h] [rbp-C0h]
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  GUID ActivityId; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v41; // [rsp+70h] [rbp-90h] BYREF
  __int128 v42; // [rsp+80h] [rbp-80h]
  __int128 v43; // [rsp+90h] [rbp-70h]
  GUID *v44; // [rsp+A0h] [rbp-60h]
  _DWORD v45[2]; // [rsp+A8h] [rbp-58h]
  GUID *v46; // [rsp+B0h] [rbp-50h]
  int v47; // [rsp+B8h] [rbp-48h]
  DWORD *p_dwTimeStamp; // [rsp+C0h] [rbp-40h]
  int v49; // [rsp+C8h] [rbp-38h]
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v51[30]; // [rsp+1B0h] [rbp+B0h] BYREF

  v36 = 0;
  memset_0(&v41, 0, 0x130u);
  v38 = 0;
  EventDescriptor = 0;
  UserData = 0;
  memset_0(v51, 0, sizeof(v51));
  v4 = *(_QWORD *)a1;
  ActivityId = 0;
  v5 = (*(__int64 (__fastcall **)(struct IGlobalTraceEventProvider *, struct HTTP_TRACE_EVENT **))(v4 + 8))(a1, &v36);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\etw\\etw_trace_handler.cxx",
        536,
        "ETW_TRACE_HANDLER::HandleRaisedEvent",
        "Failed to retrieve trace event hr=0x%x",
        v5);
    return (unsigned int)v6;
  }
  v7 = (void **)ETW_TRACE_HANDLER::sm_EtwProviderListHead;
  v8 = v36;
  v9 = 0;
  v37 = 0;
  v10 = 0;
  if ( ETW_TRACE_HANDLER::sm_EtwProviderListHead != &ETW_TRACE_HANDLER::sm_EtwProviderListHead )
  {
    pProviderGuid = v36->pProviderGuid;
    while ( v7[8] != *(void **)&pProviderGuid->Data1 || v7[9] != *(void **)pProviderGuid->Data4 )
    {
      v7 = (void **)*v7;
      if ( v7 == &ETW_TRACE_HANDLER::sm_EtwProviderListHead )
        goto LABEL_11;
    }
    v9 = *((_DWORD *)v7 + 20);
    v37 = (CEtwTracer *)(v7 + 2);
  }
LABEL_11:
  v12 = (void **)ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead;
  if ( ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead != &ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead )
  {
    v13 = v36->pProviderGuid;
    while ( 1 )
    {
      IISProviderGUID = CCustomEtwTracerV2::QueryIISProviderGUID((CCustomEtwTracerV2 *)(v12 + 2));
      if ( *(_QWORD *)&IISProviderGUID->Data1 == *(_QWORD *)&v13->Data1
        && *(_QWORD *)IISProviderGUID->Data4 == *(_QWORD *)v13->Data4 )
      {
        break;
      }
      v12 = *(void ***)v15;
      if ( v12 == &ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead )
        goto LABEL_18;
    }
    v9 = *(_DWORD *)(v15 + 96);
    v10 = v15 + 16;
  }
LABEL_18:
  v16 = v37;
  if ( !v37 && !v10 )
    return 0;
  if ( !v9 || (v9 & *((_DWORD *)v37 + 10)) == 0 && (v9 & *(_DWORD *)(v10 + 20)) == 0 )
    goto LABEL_27;
  v35 = 0;
  v6 = ETW_TRACE_HANDLER::ApplyUrlFilter(v8, a1, &v35);
  if ( v6 >= 0 )
  {
    if ( !v35 )
      return 0;
LABEL_27:
    v18 = *(_QWORD *)a1;
    LODWORD(v37) = 0;
    v35 = 0;
    v41 = 0;
    v19 = *(int (__fastcall **)(struct IGlobalTraceEventProvider *, __int64 *))(v18 + 24);
    v42 = 0;
    v43 = 0;
    v20 = &GUID_NULL_FOR_ETW_TRACE_HANDLER;
    if ( v19(a1, &v38) < 0
      || v36->cEventItems < 3
      || _wcsicmp(v36->pEventItems->pszName, L"ActivityGuid")
      || _wcsicmp(v36->pEventItems[1].pszName, L"RelatedActivityGuid")
      || _wcsicmp(v36->pEventItems[2].pszName, L"Timestamp") )
    {
      v26 = 0;
      if ( (*(int (__fastcall **)(struct IGlobalTraceEventProvider *, __int64 *))(*(_QWORD *)a1 + 24LL))(a1, &v38) < 0
        || _wcsicmp(v36->pEventItems->pszName, L"ContextId") )
      {
        v21 = v36;
      }
      else
      {
        v21 = v36;
        pActivityGuid = &GUID_NULL_FOR_ETW_TRACE_HANDLER;
        if ( v36->pActivityGuid )
          pActivityGuid = (GUID *)v36->pActivityGuid;
        v44 = pActivityGuid;
        v45[0] = 16;
        if ( v10 )
        {
          v28 = &GUID_NULL_FOR_ETW_TRACE_HANDLER;
          if ( v36->pActivityGuid )
            v28 = (GUID *)v36->pActivityGuid;
          UserData.Ptr = (ULONGLONG)v28;
          *(_QWORD *)&UserData.Size = 16;
        }
        v26 = 1;
      }
    }
    else
    {
      v21 = v36;
      v22 = &GUID_NULL_FOR_ETW_TRACE_HANDLER;
      if ( v36->pActivityGuid )
        v22 = (GUID *)v36->pActivityGuid;
      v44 = v22;
      v45[0] = 16;
      if ( v10 )
      {
        v23 = &GUID_NULL_FOR_ETW_TRACE_HANDLER;
        if ( v36->pActivityGuid )
          v23 = (GUID *)v36->pActivityGuid;
        UserData.Ptr = (ULONGLONG)v23;
        *(_QWORD *)&UserData.Size = 16;
      }
      pRelatedActivityGuid = &GUID_NULL_FOR_ETW_TRACE_HANDLER;
      if ( v36->pRelatedActivityGuid )
        pRelatedActivityGuid = (GUID *)v36->pRelatedActivityGuid;
      v46 = pRelatedActivityGuid;
      v47 = 16;
      if ( v10 )
      {
        v25 = &GUID_NULL_FOR_ETW_TRACE_HANDLER;
        if ( v36->pRelatedActivityGuid )
          v25 = (GUID *)v36->pRelatedActivityGuid;
        v51[0] = v25;
        v51[1] = 16;
      }
      p_dwTimeStamp = &v36->dwTimeStamp;
      v49 = 4;
      if ( v10 )
      {
        v51[2] = v36->dwTimeStamp;
        v51[3] = 4;
      }
      v26 = 3;
    }
    do
    {
      if ( v26 >= v21->cEventItems )
        break;
      pEventItems = v21->pEventItems;
      if ( pEventItems[v26].dwDataType == HTTP_TRACE_TYPE_LPCGUID )
      {
        pbData = (GUID *)pEventItems[v26].pbData;
        v31 = &GUID_NULL_FOR_ETW_TRACE_HANDLER;
        if ( pbData )
          v31 = pbData;
      }
      else
      {
        v31 = (GUID *)pEventItems[v26].pbData;
      }
      v32 = 2LL * v26;
      *(_QWORD *)&v45[2 * v32 - 2] = v31;
      v45[2 * v32] = v21->pEventItems[v26].cbData;
      if ( v10 )
      {
        cbData = v21->pEventItems[v26].cbData;
        *(&UserData.Ptr + 2 * v26) = (ULONGLONG)v31;
        *(&UserData.Size + 4 * v26) = cbData;
        *(&UserData.Reserved + 4 * v26) = 0;
      }
      ++v26;
    }
    while ( v26 < 0x10 );
    HIDWORD(v43) = 1703936;
    LOWORD(v41) = 16 * (v26 + 3);
    BYTE4(v41) = v21->dwEvent;
    *((_QWORD *)&v42 + 1) = v21->pAreaGuid;
    WORD3(v41) = v21->dwEventVersion;
    EventActivityIdControl(1u, &ActivityId);
    if ( v36->pActivityGuid )
      v20 = (GUID *)v36->pActivityGuid;
    EventActivityIdControl(2u, v20);
    if ( v16 )
      v34 = CEtwTracer::EtwTraceEvent(v16, (struct _ETW_TRACE_EVENT *)&v41);
    else
      v34 = (unsigned int)v37;
    if ( v10 )
    {
      EventDescriptor.Id = v36->dwEvent;
      EventDescriptor.Version = v36->dwEventVersion;
      EventDescriptor.Channel = 16;
      EventDescriptor.Level = v36->dwVerbosity;
      EventDescriptor.Opcode = v36->dwEvent;
      EventDescriptor.Task = 0;
      EventDescriptor.Keyword = v36->dwArea;
      if ( *(_DWORD *)(v10 + 16) && *(_DWORD *)(v10 + 12) && *(_DWORD *)(v10 + 8) )
        v35 = EventWrite(*(_QWORD *)(v10 + 48), &EventDescriptor, v36->cEventItems, &UserData);
      else
        v35 = 50;
    }
    EventActivityIdControl(2u, &ActivityId);
    if ( v34 || v35 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800026bc  push    rbp
0x1800026be  push    rbx
0x1800026bf  push    rsi
0x1800026c0  push    rdi
0x1800026c1  push    r12
0x1800026c3  push    r13
0x1800026c5  push    r14
0x1800026c7  push    r15
0x1800026c9  lea     rbp, [rsp-1B8h]
0x1800026d1  sub     rsp, 2B8h
0x1800026d8  mov     rax, cs:__security_cookie
0x1800026df  xor     rax, rsp
0x1800026e2  mov     [rbp+1F0h+var_50], rax
0x1800026e9  mov     r12, rcx
0x1800026ec  mov     [rsp+2F0h+var_2B8], 0
0x1800026f5  lea     rcx, [rsp+2F0h+var_280]; void *
0x1800026fa  xor     edx, edx; Val
0x1800026fc  mov     r8d, 130h; Size
0x180002702  call    memset_0
0x180002707  xorps   xmm0, xmm0
0x18000270a  mov     [rsp+2F0h+var_2A8], 0
0x180002713  xorps   xmm1, xmm1
0x180002716  lea     rcx, [rbp+1F0h+var_140]; void *
0x18000271d  xor     edx, edx; Val
0x18000271f  mov     r8d, 0F0h; Size
0x180002725  movups  xmmword ptr [rsp+2F0h+EventDescriptor.Id], xmm0
0x18000272a  movups  xmmword ptr [rbp+1F0h+UserData.Ptr], xmm1
0x180002731  call    memset_0
0x180002736  mov     rax, [r12]
0x18000273a  lea     rdx, [rsp+2F0h+var_2B8]
0x18000273f  xorps   xmm0, xmm0
0x180002742  mov     rcx, r12
0x180002745  movups  xmmword ptr [rsp+2F0h+ActivityId.Data1], xmm0
0x18000274a  mov     rax, [rax+8]
0x18000274e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002753  mov     esi, eax
0x180002755  test    eax, eax
0x180002757  jns     short loc_1800027A2
0x180002759  mov     r15d, 3
0x18000275f  test    cs:g_dwDebugFlags, r15b
0x180002766  jz      loc_180002BF2
0x18000276c  mov     rcx, cs:g_pDebug
0x180002773  lea     r9, aEtwTraceHandle; "ETW_TRACE_HANDLER::HandleRaisedEvent"
0x18000277a  mov     [rsp+2F0h+var_2C8], eax
0x18000277e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002785  lea     rax, aFailedToRetrie; "Failed to retrieve trace event hr=0x%x"
0x18000278c  mov     r8d, 218h
0x180002792  mov     [rsp+2F0h+var_2D0], rax
0x180002797  call    cs:__imp_PuDbgPrint
0x18000279d  jmp     loc_180002BF2
0x1800027a2  mov     rcx, cs:?sm_EtwProviderListHead@ETW_TRACE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ETW_TRACE_HANDLER::sm_EtwProviderListHead
0x1800027a9  lea     r8, ?sm_EtwProviderListHead@ETW_TRACE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ETW_TRACE_HANDLER::sm_EtwProviderListHead
0x1800027b0  mov     r14, [rsp+2F0h+var_2B8]
0x1800027b5  xor     eax, eax
0x1800027b7  xor     edi, edi
0x1800027b9  mov     [rsp+2F0h+var_2B0], rax
0x1800027be  xor     ebx, ebx
0x1800027c0  cmp     rcx, r8
0x1800027c3  jz      short loc_1800027F1
0x1800027c5  mov     rdx, [r14]
0x1800027c8  mov     rax, [rcx+40h]
0x1800027cc  cmp     rax, [rdx]
0x1800027cf  jnz     short loc_1800027DB
0x1800027d1  mov     rax, [rcx+48h]
0x1800027d5  cmp     rax, [rdx+8]
0x1800027d9  jz      short loc_1800027E5
0x1800027db  mov     rcx, [rcx]
0x1800027de  cmp     rcx, r8
0x1800027e1  jnz     short loc_1800027C8
0x1800027e3  jmp     short loc_1800027F1
0x1800027e5  mov     edi, [rcx+50h]
0x1800027e8  lea     rax, [rcx+10h]
0x1800027ec  mov     [rsp+2F0h+var_2B0], rax
0x1800027f1  mov     r11, cs:?sm_EtwV2ProviderListHead@ETW_TRACE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead
0x1800027f8  lea     rax, ?sm_EtwV2ProviderListHead@ETW_TRACE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead
0x1800027ff  cmp     r11, rax
0x180002802  jz      short loc_18000283C
0x180002804  mov     r13, [r14]
0x180002807  lea     rcx, [r11+10h]; this
0x18000280b  call    ?QueryIISProviderGUID@CCustomEtwTracerV2@@QEAAPEBU_GUID@@XZ; CCustomEtwTracerV2::QueryIISProviderGUID(void)
0x180002810  mov     rcx, [rax]
0x180002813  cmp     rcx, [r13+0]
0x180002817  jnz     short loc_180002823
0x180002819  mov     rax, [rax+8]
0x18000281d  cmp     rax, [r13+8]
0x180002821  jz      short loc_180002834
0x180002823  mov     r11, [r11]
0x180002826  lea     rax, ?sm_EtwV2ProviderListHead@ETW_TRACE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead
0x18000282d  cmp     r11, rax
0x180002830  jnz     short loc_180002807
0x180002832  jmp     short loc_18000283C
0x180002834  mov     edi, [r11+60h]
0x180002838  lea     rbx, [r11+10h]
0x18000283c  mov     r13, [rsp+2F0h+var_2B0]
0x180002841  test    r13, r13
0x180002844  jnz     short loc_180002852
0x180002846  test    rbx, rbx
0x180002849  jnz     short loc_180002852
0x18000284b  xor     eax, eax
0x18000284d  jmp     loc_180002BF4
0x180002852  test    edi, edi
0x180002854  jz      short loc_180002891
0x180002856  test    [r13+28h], edi
0x18000285a  jnz     short loc_180002861
0x18000285c  test    [rbx+14h], edi
0x18000285f  jz      short loc_180002891
0x180002861  lea     r8, [rsp+2F0h+var_2C0]; int *
0x180002866  mov     [rsp+2F0h+var_2C0], 0
0x18000286e  mov     rdx, r12; struct IGlobalTraceEventProvider *
0x180002871  mov     rcx, r14; struct HTTP_TRACE_EVENT *
0x180002874  call    ?ApplyUrlFilter@ETW_TRACE_HANDLER@@SAJPEAUHTTP_TRACE_EVENT@@PEAVIGlobalTraceEventProvider@@PEAH@Z; ETW_TRACE_HANDLER::ApplyUrlFilter(HTTP_TRACE_EVENT *,IGlobalTraceEventProvider *,int *)
0x180002879  mov     esi, eax
0x18000287b  test    eax, eax
0x18000287d  js      loc_180002BF2
0x180002883  cmp     [rsp+2F0h+var_2C0], 0
0x180002888  jnz     short loc_180002891
0x18000288a  xor     esi, esi
0x18000288c  jmp     loc_180002BF2
0x180002891  mov     rax, [r12]
0x180002895  lea     rdx, [rsp+2F0h+var_2A8]
0x18000289a  xorps   xmm0, xmm0
0x18000289d  mov     dword ptr [rsp+2F0h+var_2B0], 0
0x1800028a5  mov     rcx, r12
0x1800028a8  mov     [rsp+2F0h+var_2C0], 0
0x1800028b0  movups  [rsp+2F0h+var_280], xmm0
0x1800028b5  mov     rax, [rax+18h]
0x1800028b9  movups  [rbp+1F0h+var_270], xmm0
0x1800028bd  movups  [rbp+1F0h+var_260], xmm0
0x1800028c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028c6  lea     r14, GUID_NULL_FOR_ETW_TRACE_HANDLER
0x1800028cd  mov     r15d, 3
0x1800028d3  test    eax, eax
0x1800028d5  js      loc_1800029E9
0x1800028db  mov     rcx, [rsp+2F0h+var_2B8]
0x1800028e0  cmp     [rcx+48h], r15d
0x1800028e4  jb      loc_1800029E9
0x1800028ea  mov     rcx, [rcx+50h]
0x1800028ee  lea     rdx, aActivityguid; "ActivityGuid"
0x1800028f5  mov     rcx, [rcx]; String1
0x1800028f8  call    cs:__imp__wcsicmp
0x1800028fe  test    eax, eax
0x180002900  jnz     loc_1800029E9
0x180002906  mov     rax, [rsp+2F0h+var_2B8]
0x18000290b  lea     rdx, aRelatedactivit; "RelatedActivityGuid"
0x180002912  mov     rcx, [rax+50h]
0x180002916  mov     rcx, [rcx+28h]; String1
0x18000291a  call    cs:__imp__wcsicmp
0x180002920  test    eax, eax
0x180002922  jnz     loc_1800029E9
0x180002928  mov     rax, [rsp+2F0h+var_2B8]
0x18000292d  lea     rdx, aTimestamp; "Timestamp"
0x180002934  mov     rcx, [rax+50h]
0x180002938  mov     rcx, [rcx+50h]; String1
0x18000293c  call    cs:__imp__wcsicmp
0x180002942  test    eax, eax
0x180002944  jnz     loc_1800029E9
0x18000294a  mov     rdx, [rsp+2F0h+var_2B8]
0x18000294f  lea     r11d, [r15+0Dh]
0x180002953  xor     r12d, r12d
0x180002956  mov     rax, r14
0x180002959  cmp     [rdx+30h], r12
0x18000295d  cmovnz  rax, [rdx+30h]
0x180002962  mov     [rbp+1F0h+var_250], rax
0x180002966  mov     [rbp+1F0h+var_248], r11d
0x18000296a  test    rbx, rbx
0x18000296d  jz      short loc_180002989
0x18000296f  cmp     [rdx+30h], r12
0x180002973  mov     rax, r14
0x180002976  cmovnz  rax, [rdx+30h]
0x18000297b  mov     [rbp+1F0h+UserData.Ptr], rax
0x180002982  mov     qword ptr [rbp+1F0h+UserData.Size], r11
0x180002989  cmp     [rdx+38h], r12
0x18000298d  mov     rax, r14
0x180002990  cmovnz  rax, [rdx+38h]
0x180002995  mov     [rbp+1F0h+var_240], rax
0x180002999  mov     [rbp+1F0h+var_238], r11d
0x18000299d  test    rbx, rbx
0x1800029a0  jz      short loc_1800029BC
0x1800029a2  cmp     [rdx+38h], r12
0x1800029a6  mov     rax, r14
0x1800029a9  cmovnz  rax, [rdx+38h]
0x1800029ae  mov     [rbp+1F0h+var_140], rax
0x1800029b5  mov     [rbp+1F0h+var_138], r11
0x1800029bc  lea     rax, [rdx+40h]
0x1800029c0  mov     ecx, 4
0x1800029c5  mov     [rbp+1F0h+var_230], rax
0x1800029c9  mov     [rbp+1F0h+var_228], ecx
0x1800029cc  test    rbx, rbx
0x1800029cf  jz      short loc_1800029E1
0x1800029d1  mov     eax, [rax]
0x1800029d3  mov     [rbp+1F0h+var_130], rax
0x1800029da  mov     [rbp+1F0h+var_128], rcx
0x1800029e1  mov     edi, r15d
0x1800029e4  jmp     loc_180002A72
0x1800029e9  mov     rax, [r12]
0x1800029ed  lea     rdx, [rsp+2F0h+var_2A8]
0x1800029f2  mov     rcx, r12
0x1800029f5  xor     edi, edi
0x1800029f7  mov     rax, [rax+18h]
0x1800029fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a00  xor     r12d, r12d
0x180002a03  test    eax, eax
0x180002a05  js      short loc_180002A67
0x180002a07  mov     rax, [rsp+2F0h+var_2B8]
0x180002a0c  lea     rdx, aContextid; "ContextId"
0x180002a13  mov     rcx, [rax+50h]
0x180002a17  mov     rcx, [rcx]; String1
0x180002a1a  call    cs:__imp__wcsicmp
0x180002a20  test    eax, eax
0x180002a22  jnz     short loc_180002A67
0x180002a24  mov     rdx, [rsp+2F0h+var_2B8]
0x180002a29  lea     r11d, [rdi+10h]
0x180002a2d  mov     rax, r14
0x180002a30  cmp     [rdx+30h], r12
0x180002a34  cmovnz  rax, [rdx+30h]
0x180002a39  mov     [rbp+1F0h+var_250], rax
0x180002a3d  mov     [rbp+1F0h+var_248], r11d
0x180002a41  test    rbx, rbx
0x180002a44  jz      short loc_180002A60
0x180002a46  cmp     [rdx+30h], r12
0x180002a4a  mov     rax, r14
0x180002a4d  cmovnz  rax, [rdx+30h]
0x180002a52  mov     [rbp+1F0h+UserData.Ptr], rax
0x180002a59  mov     qword ptr [rbp+1F0h+UserData.Size], r11
0x180002a60  mov     edi, 1
0x180002a65  jmp     short loc_180002A72
0x180002a67  mov     rdx, [rsp+2F0h+var_2B8]
0x180002a6c  mov     r11d, 10h
0x180002a72  cmp     edi, [rdx+48h]
0x180002a75  jnb     short loc_180002AE3
0x180002a77  mov     r10, [rdx+50h]
0x180002a7b  mov     r8d, edi
0x180002a7e  lea     r9, [r8+r8*4]
0x180002a82  cmp     dword ptr [r10+r9*8+8], 48h ; 'H'
0x180002a88  jnz     short loc_180002A9B
0x180002a8a  mov     rax, [r10+r9*8+10h]
0x180002a8f  mov     r10, r14
0x180002a92  test    rax, rax
0x180002a95  cmovnz  r10, rax
0x180002a99  jmp     short loc_180002AA0
0x180002a9b  mov     r10, [r10+r9*8+10h]
0x180002aa0  add     r8, r8
0x180002aa3  mov     [rbp+r8*8+1F0h+var_250], r10
0x180002aa8  mov     rax, [rdx+50h]
0x180002aac  mov     ecx, [rax+r9*8+18h]
0x180002ab1  mov     [rbp+r8*8+1F0h+var_248], ecx
0x180002ab6  test    rbx, rbx
0x180002ab9  jz      short loc_180002ADC
0x180002abb  mov     rax, [rdx+50h]
0x180002abf  mov     ecx, [rax+r9*8+18h]
0x180002ac4  mov     [rbp+r8*8+1F0h+UserData.Ptr], r10
0x180002acc  mov     [rbp+r8*8+1F0h+UserData.Size], ecx
0x180002ad4  mov     dword ptr [rbp+r8*8+1F0h+UserData.0Ch], r12d
0x180002adc  inc     edi
0x180002ade  cmp     edi, r11d
0x180002ae1  jb      short loc_180002A72
0x180002ae3  mov     dword ptr [rbp+1F0h+var_260+0Ch], 1A0000h
0x180002aea  add     di, r15w
0x180002aee  shl     di, 4
0x180002af2  mov     ecx, 1; ControlCode
0x180002af7  mov     word ptr [rsp+2F0h+var_280], di
0x180002afc  mov     al, [rdx+18h]
0x180002aff  mov     byte ptr [rsp+2F0h+var_280+4], al
0x180002b03  mov     rax, [rdx+10h]
0x180002b07  mov     qword ptr [rbp+1F0h+var_270+8], rax
0x180002b0b  movzx   eax, word ptr [rdx+28h]
0x180002b0f  lea     rdx, [rsp+2F0h+ActivityId]; ActivityId
0x180002b14  mov     word ptr [rsp+2F0h+var_280+6], ax
0x180002b19  call    cs:__imp_EventActivityIdControl
0x180002b1f  mov     rax, [rsp+2F0h+var_2B8]
0x180002b24  cmp     [rax+30h], r12
0x180002b28  cmovnz  r14, [rax+30h]
0x180002b2d  mov     rdx, r14; ActivityId
0x180002b30  mov     r14d, 2
0x180002b36  mov     ecx, r14d; ControlCode
0x180002b39  call    cs:__imp_EventActivityIdControl
0x180002b3f  test    r13, r13
0x180002b42  jz      short loc_180002B56
0x180002b44  lea     rdx, [rsp+2F0h+var_280]
0x180002b49  mov     rcx, r13
0x180002b4c  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_ETW_TRACE_EVENT@@@Z; CEtwTracer::EtwTraceEvent(_ETW_TRACE_EVENT *)
0x180002b52  mov     edi, eax
0x180002b54  jmp     short loc_180002B5A
0x180002b56  mov     edi, dword ptr [rsp+2F0h+var_2B0]
0x180002b5a  test    rbx, rbx
0x180002b5d  jz      short loc_180002BD4
0x180002b5f  mov     r8, [rsp+2F0h+var_2B8]
0x180002b64  movzx   ecx, word ptr [r8+18h]
0x180002b69  mov     [rsp+2F0h+EventDescriptor.Id], cx
0x180002b6e  mov     cl, [r8+28h]
0x180002b72  mov     [rsp+2F0h+EventDescriptor.Version], cl
0x180002b76  mov     [rsp+2F0h+EventDescriptor.Channel], 10h
0x180002b7b  mov     cl, [r8+2Ch]
0x180002b7f  mov     [rsp+2F0h+EventDescriptor.Level], cl
0x180002b83  mov     al, [r8+18h]
0x180002b87  mov     [rsp+2F0h+EventDescriptor.Opcode], al
0x180002b8b  mov     [rsp+2F0h+EventDescriptor.Task], r12w
0x180002b91  mov     eax, [r8+8]
0x180002b95  mov     [rsp+2F0h+EventDescriptor.Keyword], rax
0x180002b9a  cmp     [rbx+10h], r12d
  ... truncated ...
```
