# CConnectivityManager::Initialize(int,int,IGPEventSubSystem *)

- ea: `0x1800384b0`
- end: `0x1800388b5`
- name: `?Initialize@CConnectivityManager@@AEAAKHHPEAVIGPEventSubSystem@@@Z`
- size: `1029`
- prototype: `unsigned int __fastcall(CConnectivityManager *__hidden this, int, int, struct IGPEventSubSystem *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180036340`

## callees

- `0x1800384b0`
- `0x180039148`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038624`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038624`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038711`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800387e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038711`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800387e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038701`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003872c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003872c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038801`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x180038653`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x180038653`

## string_xrefs

- `0x18003874d`: `Connectivity manager class initialize: failed to create the policy apply success event %d.`
- `0x18003877e`: `Connectivity manager class initialize: failed to create the policy apply success event %d.`
- `0x1800387aa`: `Connectivity manager class initialize: Created the policy apply success event %p.`
- `0x1800387cd`: `Connectivity manager class initialize: Created the policy apply success event %p.`
- `0x180038822`: `Connectivity manager class initialize: failed to create the policy apply failure event %d.`
- `0x180038840`: `Connectivity manager class initialize: failed to create the policy apply failure event %d.`
- `0x180038861`: `Connectivity manager class initialize: Created the policy apply failure event %p.`
- `0x180038884`: `Connectivity manager class initialize: Created the policy apply failure event %p.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CConnectivityManager::Initialize(
        CConnectivityManager *this,
        int a2,
        int a3,
        struct IGPEventSubSystem *a4)
{
  CConnectivityManager *v6; // rsi
  DWORD LastError; // edi
  void (*v8)(unsigned int, const unsigned __int16 *, ...); // r9
  const wchar_t *v9; // r8
  const wchar_t *v10; // r8
  const wchar_t *v11; // r8
  const wchar_t *v12; // r8
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  HANDLE EventW; // rax
  void (*v15)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v16; // rdx
  HANDLE v17; // rax
  _QWORD v19[4]; // [rsp+20h] [rbp-48h] BYREF

  v6 = CConnectivityManager::s_pInstance;
  if ( *((_DWORD *)CConnectivityManager::s_pInstance + 4) )
    return 1247;
  if ( !*((_QWORD *)CConnectivityManager::s_pInstance + 10) )
    return 14;
  LastError = 0;
  *((_QWORD *)CConnectivityManager::s_pInstance + 1) = a4;
  *((_DWORD *)v6 + 9) = a3;
  *((_DWORD *)v6 + 8) = 1;
  v8 = g_lpDebugMsg;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      v9 = L"Disabled";
      if ( !a3 )
        v9 = L"Enabled";
      g_lpDebugMsg(4u, L"Register for connectivity notification is %ws.", v9);
LABEL_15:
      v8 = g_lpDebugMsg;
      goto LABEL_16;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v10 = L"Disabled";
      if ( !a3 )
        v10 = L"Enabled";
      RedirectDebugMsg(4u, L"Register for connectivity notification is %ws.", v10, 0);
      goto LABEL_15;
    }
  }
LABEL_16:
  *((_DWORD *)v6 + 5) = a2 != 0 ? 3 : 1;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( v8 )
    {
      v11 = L"IntranetAuth";
      if ( !a2 )
        v11 = L"Internet";
      v8(4u, L"Connectivity manager class initialized for %ws connectivity", v11);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v12 = L"IntranetAuth";
      if ( !a2 )
        v12 = L"Internet";
      RedirectDebugMsg(4u, L"Connectivity manager class initialized for %ws connectivity", v12);
    }
  }
  if ( !*((_QWORD *)v6 + 11) )
  {
    v13 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v6 + 10);
    if ( v13 )
      EnterCriticalSection(v13);
    v19[0] = 1;
    v19[1] = &CConnectivityManager::PdcClientActivatorCallback;
    v19[2] = v6;
    LastError = ((__int64 (__fastcall *)(__int64, _QWORD *, char *, void (*)(unsigned int, const unsigned __int16 *, ...)))Pdcv2ActivationClientRegister)(
                  12,
                  v19,
                  (char *)v6 + 88,
                  v8);
    if ( LastError )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"Connectivity manager class failed to initialize AOAC return %d.", LastError);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"Connectivity manager class failed to initialize AOAC return %d.", LastError);
        }
      }
      LastError = 0;
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"Connectivity manager class initialize AOAC.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"Connectivity manager class initialize AOAC.");
      }
    }
    if ( v13 )
      LeaveCriticalSection(v13);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  XHandle::operator=((void **)v6 + 13, EventW);
  if ( *((_QWORD *)v6 + 13) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"Connectivity manager class initialize: Created the policy apply success event %p.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"Connectivity manager class initialize: Created the policy apply success event %p.");
      }
    }
    v17 = CreateEventW(0, 0, 0, 0);
    XHandle::operator=((void **)v6 + 14, v17);
    if ( *((_QWORD *)v6 + 14) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"Connectivity manager class initialize: Created the policy apply failure event %p.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"Connectivity manager class initialize: Created the policy apply failure event %p.");
        }
      }
      *((_DWORD *)v6 + 4) = 1;
    }
    else
    {
      LastError = GetLastError();
      if ( !*(_DWORD *)&g_dwDebugLevel )
        return LastError;
      v15 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v16 = L"Connectivity manager class initialize: failed to create the policy apply failure event %d.";
        goto LABEL_49;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(
          2u,
          L"Connectivity manager class initialize: failed to create the policy apply failure event %d.",
          LastError);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( !*(_DWORD *)&g_dwDebugLevel )
      return LastError;
    v15 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v16 = L"Connectivity manager class initialize: failed to create the policy apply success event %d.";
LABEL_49:
      v15(2u, v16, LastError);
      return LastError;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      RedirectDebugMsg(
        2u,
        L"Connectivity manager class initialize: failed to create the policy apply success event %d.",
        LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800384b0  mov     [rsp+arg_8], rbx
0x1800384b5  mov     [rsp+arg_10], rbp
0x1800384ba  mov     [rsp+arg_0], rcx
0x1800384bf  push    rsi
0x1800384c0  push    rdi
0x1800384c1  push    r12
0x1800384c3  push    r14
0x1800384c5  push    r15
0x1800384c7  sub     rsp, 40h
0x1800384cb  mov     eax, r8d
0x1800384ce  mov     ebx, edx
0x1800384d0  mov     rsi, cs:?s_pInstance@CConnectivityManager@@0PEAV1@EA; CConnectivityManager * CConnectivityManager::s_pInstance
0x1800384d7  xor     r14d, r14d
0x1800384da  cmp     [rsi+10h], r14d
0x1800384de  jz      short loc_1800384EA
0x1800384e0  mov     edi, 4DFh
0x1800384e5  jmp     loc_18003889A
0x1800384ea  cmp     [rsi+50h], r14
0x1800384ee  jnz     short loc_1800384FA
0x1800384f0  mov     edi, 0Eh
0x1800384f5  jmp     loc_18003889A
0x1800384fa  mov     edi, r14d
0x1800384fd  mov     [rsi+8], r9
0x180038501  mov     [rsi+24h], eax
0x180038504  mov     dword ptr [rsi+20h], 1
0x18003850b  mov     r12d, 4
0x180038511  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180038518  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18003851f  jz      short loc_18003858A
0x180038521  test    r9, r9
0x180038524  jz      short loc_18003854E
0x180038526  lea     rcx, aEnabled; "Enabled"
0x18003852d  lea     r8, aDisabled; "Disabled"
0x180038534  test    eax, eax
0x180038536  cmovz   r8, rcx
0x18003853a  lea     rdx, aRegisterForCon; "Register for connectivity notification "...
0x180038541  mov     ecx, r12d
0x180038544  mov     rax, r9
0x180038547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003854c  jmp     short loc_180038583
0x18003854e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180038555  jz      short loc_18003858A
0x180038557  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003855e  jz      short loc_18003858A
0x180038560  lea     rcx, aEnabled; "Enabled"
0x180038567  lea     r8, aDisabled; "Disabled"
0x18003856e  test    eax, eax
0x180038570  cmovz   r8, rcx
0x180038574  lea     rdx, aRegisterForCon; "Register for connectivity notification "...
0x18003857b  mov     ecx, r12d; unsigned int
0x18003857e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180038583  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003858a  mov     eax, ebx
0x18003858c  neg     eax
0x18003858e  sbb     ecx, ecx
0x180038590  mov     r15d, 2
0x180038596  and     ecx, r15d
0x180038599  inc     ecx
0x18003859b  mov     [rsi+14h], ecx
0x18003859e  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800385a5  jz      short loc_180038609
0x1800385a7  test    r9, r9
0x1800385aa  jz      short loc_1800385D4
0x1800385ac  lea     rax, aInternet; "Internet"
0x1800385b3  lea     r8, aIntranetauth; "IntranetAuth"
0x1800385ba  test    ebx, ebx
0x1800385bc  cmovz   r8, rax
0x1800385c0  lea     rdx, aConnectivityMa_5; "Connectivity manager class initialized "...
0x1800385c7  mov     ecx, r12d
0x1800385ca  mov     rax, r9
0x1800385cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385d2  jmp     short loc_180038609
0x1800385d4  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800385db  jz      short loc_180038609
0x1800385dd  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800385e4  jz      short loc_180038609
0x1800385e6  lea     rax, aInternet; "Internet"
0x1800385ed  lea     r8, aIntranetauth; "IntranetAuth"
0x1800385f4  test    ebx, ebx
0x1800385f6  cmovz   r8, rax
0x1800385fa  lea     rdx, aConnectivityMa_5; "Connectivity manager class initialized "...
0x180038601  mov     ecx, r12d; unsigned int
0x180038604  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180038609  cmp     [rsi+58h], r14
0x18003860d  jnz     loc_180038707
0x180038613  mov     rbx, [rsi+50h]
0x180038617  mov     [rsp+68h+arg_0], rbx
0x18003861c  test    rbx, rbx
0x18003861f  jz      short loc_18003862B
0x180038621  mov     rcx, rbx; lpCriticalSection
0x180038624  call    cs:__imp_EnterCriticalSection
0x18003862a  nop
0x18003862b  mov     [rsp+68h+var_48], 1
0x180038634  lea     rax, ?PdcClientActivatorCallback@CConnectivityManager@@CAXPEAXW4_PDC_ACTIVATOR_ERROR_DETAIL@@00@Z; CConnectivityManager::PdcClientActivatorCallback(void *,_PDC_ACTIVATOR_ERROR_DETAIL,void *,void *)
0x18003863b  mov     [rsp+68h+var_40], rax
0x180038640  mov     [rsp+68h+var_38], rsi
0x180038645  lea     r8, [rsi+58h]
0x180038649  lea     rdx, [rsp+68h+var_48]
0x18003864e  mov     ecx, 0Ch
0x180038653  call    cs:__imp_Pdcv2ActivationClientRegister
0x180038659  mov     edi, eax
0x18003865b  test    eax, eax
0x18003865d  jz      short loc_1800386B1
0x18003865f  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180038666  jz      short loc_1800386AC
0x180038668  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003866f  test    rax, rax
0x180038672  jz      short loc_180038688
0x180038674  mov     r8d, edi
0x180038677  lea     rdx, aConnectivityMa_0; "Connectivity manager class failed to in"...
0x18003867e  mov     ecx, r15d
0x180038681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038686  jmp     short loc_1800386AC
0x180038688  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18003868f  jz      short loc_1800386AC
0x180038691  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180038698  jz      short loc_1800386AC
0x18003869a  mov     r8d, edi
0x18003869d  lea     rdx, aConnectivityMa_0; "Connectivity manager class failed to in"...
0x1800386a4  mov     ecx, r15d; unsigned int
0x1800386a7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800386ac  mov     edi, r14d
0x1800386af  jmp     short loc_1800386F9
0x1800386b1  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800386b8  jz      short loc_1800386F9
0x1800386ba  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800386c1  test    rax, rax
0x1800386c4  jz      short loc_1800386D7
0x1800386c6  lea     rdx, aConnectivityMa; "Connectivity manager class initialize A"...
0x1800386cd  mov     ecx, r12d
0x1800386d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386d5  jmp     short loc_1800386F9
0x1800386d7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800386de  jz      short loc_1800386F9
0x1800386e0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800386e7  jz      short loc_1800386F9
0x1800386e9  lea     rdx, aConnectivityMa; "Connectivity manager class initialize A"...
0x1800386f0  mov     ecx, r12d; unsigned int
0x1800386f3  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800386f8  nop
0x1800386f9  test    rbx, rbx
0x1800386fc  jz      short loc_180038707
0x1800386fe  mov     rcx, rbx; lpCriticalSection
0x180038701  call    cs:__imp_LeaveCriticalSection
0x180038707  xor     r9d, r9d; lpName
0x18003870a  xor     r8d, r8d; bInitialState
0x18003870d  xor     edx, edx; bManualReset
0x18003870f  xor     ecx, ecx; lpEventAttributes
0x180038711  call    cs:__imp_CreateEventW
0x180038717  mov     rdx, rax
0x18003871a  lea     rcx, [rsi+68h]
0x18003871e  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x180038723  mov     r8, [rsi+68h]
0x180038727  test    r8, r8
0x18003872a  jnz     short loc_180038795
0x18003872c  call    cs:__imp_GetLastError
0x180038732  mov     edi, eax
0x180038734  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18003873b  jz      loc_18003889A
0x180038741  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180038748  test    rax, rax
0x18003874b  jz      short loc_180038764
0x18003874d  lea     rdx, aConnectivityMa_4; "Connectivity manager class initialize: "...
0x180038754  mov     r8d, edi
0x180038757  mov     ecx, r15d
0x18003875a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003875f  jmp     loc_18003889A
0x180038764  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18003876b  jz      loc_18003889A
0x180038771  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180038778  jz      loc_18003889A
0x18003877e  lea     rdx, aConnectivityMa_4; "Connectivity manager class initialize: "...
0x180038785  mov     r8d, edi
0x180038788  mov     ecx, r15d; unsigned int
0x18003878b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180038790  jmp     loc_18003889A
0x180038795  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18003879c  jz      short loc_1800387DC
0x18003879e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800387a5  test    rax, rax
0x1800387a8  jz      short loc_1800387BB
0x1800387aa  lea     rdx, aConnectivityMa_1; "Connectivity manager class initialize: "...
0x1800387b1  mov     ecx, r12d
0x1800387b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387b9  jmp     short loc_1800387DC
0x1800387bb  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800387c2  jz      short loc_1800387DC
0x1800387c4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800387cb  jz      short loc_1800387DC
0x1800387cd  lea     rdx, aConnectivityMa_1; "Connectivity manager class initialize: "...
0x1800387d4  mov     ecx, r12d; unsigned int
0x1800387d7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800387dc  xor     r9d, r9d; lpName
0x1800387df  xor     r8d, r8d; bInitialState
0x1800387e2  xor     edx, edx; bManualReset
0x1800387e4  xor     ecx, ecx; lpEventAttributes
0x1800387e6  call    cs:__imp_CreateEventW
0x1800387ec  mov     rdx, rax
0x1800387ef  lea     rcx, [rsi+70h]
0x1800387f3  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x1800387f8  mov     r8, [rsi+70h]
0x1800387fc  test    r8, r8
0x1800387ff  jnz     short loc_18003884C
0x180038801  call    cs:__imp_GetLastError
0x180038807  mov     edi, eax
0x180038809  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180038810  jz      loc_18003889A
0x180038816  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003881d  test    rax, rax
0x180038820  jz      short loc_18003882E
0x180038822  lea     rdx, aConnectivityMa_3; "Connectivity manager class initialize: "...
0x180038829  jmp     loc_180038754
0x18003882e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180038835  jz      short loc_18003889A
0x180038837  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003883e  jz      short loc_18003889A
0x180038840  lea     rdx, aConnectivityMa_3; "Connectivity manager class initialize: "...
0x180038847  jmp     loc_180038785
0x18003884c  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180038853  jz      short loc_180038893
0x180038855  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003885c  test    rax, rax
0x18003885f  jz      short loc_180038872
0x180038861  lea     rdx, aConnectivityMa_2; "Connectivity manager class initialize: "...
0x180038868  mov     ecx, r12d
0x18003886b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038870  jmp     short loc_180038893
0x180038872  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180038879  jz      short loc_180038893
0x18003887b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180038882  jz      short loc_180038893
0x180038884  lea     rdx, aConnectivityMa_2; "Connectivity manager class initialize: "...
0x18003888b  mov     ecx, r12d; unsigned int
0x18003888e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180038893  mov     dword ptr [rsi+10h], 1
0x18003889a  mov     eax, edi
0x18003889c  lea     r11, [rsp+68h+var_28]
0x1800388a1  mov     rbx, [r11+38h]
0x1800388a5  mov     rbp, [r11+40h]
0x1800388a9  mov     rsp, r11
0x1800388ac  pop     r15
0x1800388ae  pop     r14
0x1800388b0  pop     r12
0x1800388b2  pop     rdi
0x1800388b3  pop     rsi
0x1800388b4  retn
```
