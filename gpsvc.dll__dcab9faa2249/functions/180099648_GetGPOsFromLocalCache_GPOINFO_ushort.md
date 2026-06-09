# GetGPOsFromLocalCache(_GPOINFO *,ushort *)

- ea: `0x180099648`
- end: `0x180099a8c`
- name: `?GetGPOsFromLocalCache@@YAHPEAU_GPOINFO@@PEAG@Z`
- size: `1092`
- prototype: `__int64 __fastcall(struct _GPOINFO *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180058f20`

## callees

- `0x180016640`
- `0x1800183d4`
- `0x18001ae40`
- `0x18002ba60`
- `0x180070458`
- `0x180075ec0`
- `0x180075fb8`
- `0x180099648`
- `0x18009dd2c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180099a6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180099a6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099770`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180099670`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180099764`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800999ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180099670`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180099764`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800999ea`

## string_xrefs

- `0x1800996ab`: `GetGPOsFromLocalCache(%s):++.`
- `0x1800996ce`: `GetGPOsFromLocalCache(%s):++.`
- `0x180099748`: `GetGPOsFromLocalCache(%s): Failed to Read DNName from registry.`
- `0x180099827`: `GetGPOsFromLocalCache(%s): Failed to Read DNName from registry.`
- `0x180099875`: `GetGPOsFromLocalCache(%s): Failed to read SiteName.`
- `0x18009989b`: `GetGPOsFromLocalCache(%s): Failed to read SiteName.`
- `0x1800998d9`: `GetGPOsFromLocalCache(%s): Failed to read DCName.`
- `0x1800998ff`: `GetGPOsFromLocalCache(%s): Failed to read DCName.`
- `0x180099936`: `GetGPOsFromLocalCache(%s): Failed to load gpoList.`
- `0x18009995c`: `GetGPOsFromLocalCache(%s): Failed to load gpoList.`
- `0x18009998c`: `GetGPOsFromLocalCache(%s): Get %ld GPOs to process.`
- `0x1800999b4`: `GetGPOsFromLocalCache(%s): Get %ld GPOs to process.`
- `0x1800997f7`: `GetGPOsFromLocalCache(%s):-- (Status:%s).`
- `0x180099a58`: `GetGPOsFromLocalCache(%s):-- (Status:%s).`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetGPOsFromLocalCache(struct _GPOINFO *a1, unsigned __int16 *a2)
{
  DWORD LastError; // ebx
  DWORD TickCount; // r12d
  unsigned int CachedString; // esi
  void (*v7)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v8; // rdx
  const wchar_t *v9; // r9
  __int64 GPOCount; // r9
  const wchar_t *v11; // r9
  unsigned int v13; // [rsp+30h] [rbp-20h] BYREF
  void *v14; // [rsp+38h] [rbp-18h] BYREF
  __int64 v15; // [rsp+40h] [rbp-10h]
  unsigned int v16; // [rsp+90h] [rbp+40h] BYREF
  int v17; // [rsp+A0h] [rbp+50h]
  unsigned int v18; // [rsp+A8h] [rbp+58h] BYREF

  LastError = GetLastError();
  v17 = LastError;
  TickCount = GetTickCount();
  if ( a1 && a2 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"GetGPOsFromLocalCache(%s):++.", a2);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"GetGPOsFromLocalCache(%s):++.", a2);
      }
    }
    v14 = 0;
    v15 = 0;
    v16 = *(_DWORD *)a1 & 1;
    COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v14, &v16);
    COperationalBaseEvent::ReportOperationalEvent((COperationalBaseEvent *)&v14, &gpEvent_GP_LOAD_FROM_CACHE_START);
    CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(&v14);
    CachedString = GetCachedString(a1, L"DNName", (unsigned __int16 **)a1 + 3);
    if ( !CachedString )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
      {
LABEL_14:
        v14 = 0;
        v15 = 0;
        v13 = GetTickCount() - TickCount;
        v18 = GetLastError();
        v16 = *(_DWORD *)a1 & 1;
        COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v14, &v16);
        COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v14, &v18);
        COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v14, &v13);
        COperationalBaseEvent::ReportOperationalEvent(
          (COperationalBaseEvent *)&v14,
          &gpEvent_GP_LOAD_FROM_CACHE_END_ERROR);
        goto LABEL_15;
      }
      v7 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"GetGPOsFromLocalCache(%s): Failed to Read DNName from registry.", a2);
        goto LABEL_14;
      }
      v8 = L"GetGPOsFromLocalCache(%s): Failed to Read DNName from registry.";
LABEL_13:
      v7(2u, v8, a2);
      goto LABEL_14;
    }
    CachedString = GetCachedString(a1, L"SiteName", (unsigned __int16 **)a1 + 28);
    if ( !CachedString )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_14;
      v7 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"GetGPOsFromLocalCache(%s): Failed to read SiteName.", a2);
        goto LABEL_14;
      }
      v8 = L"GetGPOsFromLocalCache(%s): Failed to read SiteName.";
      goto LABEL_13;
    }
    CachedString = GetCachedString(a1, L"DCName", (unsigned __int16 **)a1 + 33);
    if ( !CachedString )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_14;
      v7 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"GetGPOsFromLocalCache(%s): Failed to read DCName.", a2);
        goto LABEL_14;
      }
      v8 = L"GetGPOsFromLocalCache(%s): Failed to read DCName.";
      goto LABEL_13;
    }
    CachedString = ReadGPOListFromDataStore(a1, (struct _GROUP_POLICY_OBJECTW **)a1 + 8);
    if ( !CachedString )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_14;
      v7 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"GetGPOsFromLocalCache(%s): Failed to load gpoList.", a2);
        goto LABEL_14;
      }
      v8 = L"GetGPOsFromLocalCache(%s): Failed to load gpoList.";
      goto LABEL_13;
    }
    GPOCount = GetGPOCount(*((struct _GROUP_POLICY_OBJECTW **)a1 + 8));
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"GetGPOsFromLocalCache(%s): Get %ld GPOs to process.", a2, GPOCount);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"GetGPOsFromLocalCache(%s): Get %ld GPOs to process.", a2, GPOCount);
      }
    }
    DebugPrintGPOList2(a1);
  }
  else
  {
    LastError = 87;
    v17 = 87;
    CachedString = 0;
  }
  if ( !CachedString )
    goto LABEL_14;
  v14 = 0;
  v15 = 0;
  v18 = GetTickCount() - TickCount;
  v16 = *(_DWORD *)a1 & 1;
  COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v14, &v16);
  COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v14, &v18);
  COperationalBaseEvent::ReportOperationalEvent((COperationalBaseEvent *)&v14, &gpEvent_GP_LOAD_FROM_CACHE_END);
LABEL_15:
  CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(&v14);
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      v9 = L"TRUE";
      if ( !CachedString )
        v9 = L"FALSE";
      g_lpDebugMsg(4u, L"GetGPOsFromLocalCache(%s):-- (Status:%s).", a2, v9);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v11 = L"TRUE";
      if ( !CachedString )
        v11 = L"FALSE";
      RedirectDebugMsg(4u, L"GetGPOsFromLocalCache(%s):-- (Status:%s).", a2, v11);
    }
  }
  SetLastError(LastError);
  return CachedString;
}

```

## disassembly

```asm
0x180099648  mov     [rsp-38h+arg_8], rbx
0x18009964d  push    rbp
0x18009964e  push    rsi
0x18009964f  push    rdi
0x180099650  push    r12
0x180099652  push    r13
0x180099654  push    r14
0x180099656  push    r15
0x180099658  mov     rbp, rsp
0x18009965b  sub     rsp, 50h
0x18009965f  mov     rdi, rdx
0x180099662  mov     r14, rcx
0x180099665  call    cs:__imp_GetLastError
0x18009966b  mov     ebx, eax
0x18009966d  mov     [rbp+arg_10], eax
0x180099670  call    cs:__imp_GetTickCount
0x180099676  mov     r12d, eax
0x180099679  mov     ecx, 4; unsigned int
0x18009967e  xor     r13d, r13d
0x180099681  test    r14, r14
0x180099684  jz      loc_1800999CF
0x18009968a  test    rdi, rdi
0x18009968d  jz      loc_1800999CF
0x180099693  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18009969a  jz      short loc_1800996DA
0x18009969c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800996a3  test    rax, rax
0x1800996a6  jz      short loc_1800996B9
0x1800996a8  mov     r8, rdi
0x1800996ab  lea     rdx, aGetgposfromloc_5; "GetGPOsFromLocalCache(%s):++."
0x1800996b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800996b7  jmp     short loc_1800996DA
0x1800996b9  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800996c0  jz      short loc_1800996DA
0x1800996c2  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800996c9  jz      short loc_1800996DA
0x1800996cb  mov     r8, rdi
0x1800996ce  lea     rdx, aGetgposfromloc_5; "GetGPOsFromLocalCache(%s):++."
0x1800996d5  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800996da  mov     [rbp+var_18], r13
0x1800996de  mov     [rbp+var_10], r13
0x1800996e2  mov     eax, [r14]
0x1800996e5  and     eax, 1
0x1800996e8  mov     [rbp+arg_0], eax
0x1800996eb  lea     rdx, [rbp+arg_0]; unsigned int *
0x1800996ef  lea     rcx, [rbp+var_18]; this
0x1800996f3  call    ?AddArg@COperationalBaseEvent@@IEAAKAEAK@Z; COperationalBaseEvent::AddArg(ulong &)
0x1800996f8  lea     rdx, gpEvent_GP_LOAD_FROM_CACHE_START; struct _EVENT_DESCRIPTOR *
0x1800996ff  lea     rcx, [rbp+var_18]; this
0x180099703  call    ?ReportOperationalEvent@COperationalBaseEvent@@IEAAKPEBU_EVENT_DESCRIPTOR@@@Z; COperationalBaseEvent::ReportOperationalEvent(_EVENT_DESCRIPTOR const *)
0x180099708  nop
0x180099709  lea     rcx, [rbp+var_18]; this
0x18009970d  call    ??1CServiceConfigurationChangeOperationalEvent@@QEAA@XZ; CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(void)
0x180099712  lea     r8, [r14+18h]; unsigned __int16 **
0x180099716  lea     rdx, aDnname; "DNName"
0x18009971d  mov     rcx, r14; struct _GPOINFO *
0x180099720  call    ?GetCachedString@@YAHPEAU_GPOINFO@@PEBGPEAPEAG@Z; GetCachedString(_GPOINFO *,ushort const *,ushort * *)
0x180099725  mov     esi, eax
0x180099727  test    eax, eax
0x180099729  jnz     loc_180099840
0x18009972f  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180099736  jz      short loc_18009975C
0x180099738  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009973f  test    rax, rax
0x180099742  jz      loc_18009980D
0x180099748  lea     rdx, aGetgposfromloc_0; "GetGPOsFromLocalCache(%s): Failed to Re"...
0x18009974f  mov     r8, rdi
0x180099752  mov     ecx, 2
0x180099757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009975c  mov     [rbp+var_18], r13
0x180099760  mov     [rbp+var_10], r13
0x180099764  call    cs:__imp_GetTickCount
0x18009976a  sub     eax, r12d
0x18009976d  mov     [rbp+var_20], eax
0x180099770  call    cs:__imp_GetLastError
0x180099776  mov     [rbp+arg_18], eax
0x180099779  mov     eax, [r14]
0x18009977c  and     eax, 1
0x18009977f  mov     [rbp+arg_0], eax
0x180099782  lea     rdx, [rbp+arg_0]; unsigned int *
0x180099786  lea     rcx, [rbp+var_18]; this
0x18009978a  call    ?AddArg@COperationalBaseEvent@@IEAAKAEAK@Z; COperationalBaseEvent::AddArg(ulong &)
0x18009978f  lea     rdx, [rbp+arg_18]; unsigned int *
0x180099793  lea     rcx, [rbp+var_18]; this
0x180099797  call    ?AddArg@COperationalBaseEvent@@IEAAKAEAK@Z; COperationalBaseEvent::AddArg(ulong &)
0x18009979c  lea     rdx, [rbp+var_20]; unsigned int *
0x1800997a0  lea     rcx, [rbp+var_18]; this
0x1800997a4  call    ?AddArg@COperationalBaseEvent@@IEAAKAEAK@Z; COperationalBaseEvent::AddArg(ulong &)
0x1800997a9  lea     rdx, gpEvent_GP_LOAD_FROM_CACHE_END_ERROR; struct _EVENT_DESCRIPTOR *
0x1800997b0  lea     rcx, [rbp+var_18]; this
0x1800997b4  call    ?ReportOperationalEvent@COperationalBaseEvent@@IEAAKPEBU_EVENT_DESCRIPTOR@@@Z; COperationalBaseEvent::ReportOperationalEvent(_EVENT_DESCRIPTOR const *)
0x1800997b9  nop
0x1800997ba  lea     rcx, [rbp+var_18]; this
0x1800997be  call    ??1CServiceConfigurationChangeOperationalEvent@@QEAA@XZ; CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(void)
0x1800997c3  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800997ca  jz      loc_180099A6A
0x1800997d0  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800997d7  test    rax, rax
0x1800997da  jz      loc_180099A2F
0x1800997e0  lea     rdx, aFalse_0; "FALSE"
0x1800997e7  lea     r9, aTrue_1; "TRUE"
0x1800997ee  test    esi, esi
0x1800997f0  cmovz   r9, rdx
0x1800997f4  mov     r8, rdi
0x1800997f7  lea     rdx, aGetgposfromloc_4; "GetGPOsFromLocalCache(%s):-- (Status:%s"...
0x1800997fe  mov     ecx, 4
0x180099803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099808  jmp     loc_180099A6A
0x18009980d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180099814  jz      loc_18009975C
0x18009981a  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180099821  jz      loc_18009975C
0x180099827  lea     rdx, aGetgposfromloc_0; "GetGPOsFromLocalCache(%s): Failed to Re"...
0x18009982e  mov     r8, rdi
0x180099831  mov     ecx, 2; unsigned int
0x180099836  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009983b  jmp     loc_18009975C
0x180099840  lea     r8, [r14+0E0h]; unsigned __int16 **
0x180099847  lea     rdx, aSitename; "SiteName"
0x18009984e  mov     rcx, r14; struct _GPOINFO *
0x180099851  call    ?GetCachedString@@YAHPEAU_GPOINFO@@PEBGPEAPEAG@Z; GetCachedString(_GPOINFO *,ushort const *,ushort * *)
0x180099856  mov     esi, eax
0x180099858  test    eax, eax
0x18009985a  jnz     short loc_1800998A4
0x18009985c  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180099863  jz      loc_18009975C
0x180099869  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180099870  test    rax, rax
0x180099873  jz      short loc_180099881
0x180099875  lea     rdx, aGetgposfromloc_1; "GetGPOsFromLocalCache(%s): Failed to re"...
0x18009987c  jmp     loc_18009974F
0x180099881  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180099888  jz      loc_18009975C
0x18009988e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180099895  jz      loc_18009975C
0x18009989b  lea     rdx, aGetgposfromloc_1; "GetGPOsFromLocalCache(%s): Failed to re"...
0x1800998a2  jmp     short loc_18009982E
0x1800998a4  lea     r8, [r14+108h]; unsigned __int16 **
0x1800998ab  lea     rdx, aDcname; "DCName"
0x1800998b2  mov     rcx, r14; struct _GPOINFO *
0x1800998b5  call    ?GetCachedString@@YAHPEAU_GPOINFO@@PEBGPEAPEAG@Z; GetCachedString(_GPOINFO *,ushort const *,ushort * *)
0x1800998ba  mov     esi, eax
0x1800998bc  test    eax, eax
0x1800998be  jnz     short loc_18009990B
0x1800998c0  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800998c7  jz      loc_18009975C
0x1800998cd  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800998d4  test    rax, rax
0x1800998d7  jz      short loc_1800998E5
0x1800998d9  lea     rdx, aGetgposfromloc_3; "GetGPOsFromLocalCache(%s): Failed to re"...
0x1800998e0  jmp     loc_18009974F
0x1800998e5  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800998ec  jz      loc_18009975C
0x1800998f2  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800998f9  jz      loc_18009975C
0x1800998ff  lea     rdx, aGetgposfromloc_3; "GetGPOsFromLocalCache(%s): Failed to re"...
0x180099906  jmp     loc_18009982E
0x18009990b  lea     rdx, [r14+40h]; struct _GROUP_POLICY_OBJECTW **
0x18009990f  mov     rcx, r14; struct _GPOINFO *
0x180099912  call    ?ReadGPOListFromDataStore@@YAHPEAU_GPOINFO@@PEAPEAU_GROUP_POLICY_OBJECTW@@@Z; ReadGPOListFromDataStore(_GPOINFO *,_GROUP_POLICY_OBJECTW * *)
0x180099917  mov     esi, eax
0x180099919  test    eax, eax
0x18009991b  jnz     short loc_180099968
0x18009991d  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180099924  jz      loc_18009975C
0x18009992a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180099931  test    rax, rax
0x180099934  jz      short loc_180099942
0x180099936  lea     rdx, aGetgposfromloc; "GetGPOsFromLocalCache(%s): Failed to lo"...
0x18009993d  jmp     loc_18009974F
0x180099942  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180099949  jz      loc_18009975C
0x18009994f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180099956  jz      loc_18009975C
0x18009995c  lea     rdx, aGetgposfromloc; "GetGPOsFromLocalCache(%s): Failed to lo"...
0x180099963  jmp     loc_18009982E
0x180099968  mov     rcx, [r14+40h]; struct _GROUP_POLICY_OBJECTW *
0x18009996c  call    ?GetGPOCount@@YAKPEAU_GROUP_POLICY_OBJECTW@@@Z; GetGPOCount(_GROUP_POLICY_OBJECTW *)
0x180099971  mov     r9d, eax
0x180099974  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18009997b  jz      short loc_1800999C5
0x18009997d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180099984  test    rax, rax
0x180099987  jz      short loc_18009999F
0x180099989  mov     r8, rdi
0x18009998c  lea     rdx, aGetgposfromloc_2; "GetGPOsFromLocalCache(%s): Get %ld GPOs"...
0x180099993  mov     ecx, 4
0x180099998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009999d  jmp     short loc_1800999C5
0x18009999f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800999a6  jz      short loc_1800999C5
0x1800999a8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800999af  jz      short loc_1800999C5
0x1800999b1  mov     r8, rdi
0x1800999b4  lea     rdx, aGetgposfromloc_2; "GetGPOsFromLocalCache(%s): Get %ld GPOs"...
0x1800999bb  mov     ecx, 4; unsigned int
0x1800999c0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800999c5  mov     rcx, r14; struct _GPOINFO *
0x1800999c8  call    ?DebugPrintGPOList2@@YAXPEAU_GPOINFO@@@Z; DebugPrintGPOList2(_GPOINFO *)
0x1800999cd  jmp     short loc_1800999DA
0x1800999cf  mov     ebx, 57h ; 'W'
0x1800999d4  mov     [rbp+arg_10], ebx
0x1800999d7  mov     esi, r13d
0x1800999da  test    esi, esi
0x1800999dc  jz      loc_18009975C
0x1800999e2  mov     [rbp+var_18], r13
0x1800999e6  mov     [rbp+var_10], r13
0x1800999ea  call    cs:__imp_GetTickCount
0x1800999f0  sub     eax, r12d
0x1800999f3  mov     [rbp+arg_18], eax
0x1800999f6  mov     eax, [r14]
0x1800999f9  and     eax, 1
0x1800999fc  mov     [rbp+arg_0], eax
0x1800999ff  lea     rdx, [rbp+arg_0]; unsigned int *
0x180099a03  lea     rcx, [rbp+var_18]; this
0x180099a07  call    ?AddArg@COperationalBaseEvent@@IEAAKAEAK@Z; COperationalBaseEvent::AddArg(ulong &)
0x180099a0c  lea     rdx, [rbp+arg_18]; unsigned int *
0x180099a10  lea     rcx, [rbp+var_18]; this
0x180099a14  call    ?AddArg@COperationalBaseEvent@@IEAAKAEAK@Z; COperationalBaseEvent::AddArg(ulong &)
0x180099a19  lea     rdx, gpEvent_GP_LOAD_FROM_CACHE_END; struct _EVENT_DESCRIPTOR *
0x180099a20  lea     rcx, [rbp+var_18]; this
0x180099a24  call    ?ReportOperationalEvent@COperationalBaseEvent@@IEAAKPEBU_EVENT_DESCRIPTOR@@@Z; COperationalBaseEvent::ReportOperationalEvent(_EVENT_DESCRIPTOR const *)
0x180099a29  nop
0x180099a2a  jmp     loc_1800997BA
0x180099a2f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180099a36  jz      short loc_180099A6A
0x180099a38  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180099a3f  jz      short loc_180099A6A
0x180099a41  lea     rdx, aFalse_0; "FALSE"
0x180099a48  lea     r9, aTrue_1; "TRUE"
0x180099a4f  test    esi, esi
0x180099a51  cmovz   r9, rdx
0x180099a55  mov     r8, rdi
0x180099a58  lea     rdx, aGetgposfromloc_4; "GetGPOsFromLocalCache(%s):-- (Status:%s"...
0x180099a5f  mov     ecx, 4; unsigned int
0x180099a64  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180099a69  nop
0x180099a6a  mov     ecx, ebx; dwErrCode
0x180099a6c  call    cs:__imp_SetLastError
0x180099a72  mov     eax, esi
0x180099a74  mov     rbx, [rsp+50h+arg_8]
0x180099a7c  add     rsp, 50h
0x180099a80  pop     r15
0x180099a82  pop     r14
0x180099a84  pop     r13
0x180099a86  pop     r12
0x180099a88  pop     rdi
0x180099a89  pop     rsi
0x180099a8a  pop     rbp
0x180099a8b  retn
```
