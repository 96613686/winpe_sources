# IsatapInitialize

- ea: `0x180032e70`
- end: `0x1800331b9`
- name: `IsatapInitialize`
- size: `841`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004f60`
- `0x180009010`
- `0x18000cea0`
- `0x18000d7c0`
- `0x1800140a8`
- `0x180015a00`
- `0x180029d18`
- `0x180032e70`
- `0x180033704`
- `0x180039230`
- `0x180039c78`
- `0x18003bc9c`
- `0x18003e110`
- `0x180040fe0`
- `0x180059338`
- `0x180059cb8`
- `0x180059e78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180032fcd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180032fcd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800330b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800330b0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003315a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003315a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032fae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032fae`

## string_xrefs

- `0x180032ec6`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`
- `0x1800330c0`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`
- `0x180033198`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`

## pseudocode

```c
void __fastcall IsatapInitialize(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  unsigned int v2; // edi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // r9
  __int64 v7; // rcx
  const char *v8; // r8
  __int64 v9; // rdx
  WCHAR *v10; // rax
  WCHAR *v11; // rcx
  HANDLE EventW; // rax
  int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rbx
  HANDLE v17; // rbx
  __int64 v18; // [rsp+28h] [rbp-30h]
  __int64 v19; // [rsp+30h] [rbp-28h]

  v2 = 1062;
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
      L"Entered: IsatapInitialize");
  if ( !(unsigned int)GetAndTraceLock(
                        "onecoreuap\\net\\netio\\iphlpsvc\\service\\isatap.c",
                        "IsatapInitialize",
                        3176,
                        g_IsatapLock) )
  {
    EventWrite0(0x2000000, L"GET_LOCK FAILED");
LABEL_34:
    SetStopServiceEvent(v2, v3, v4, v5);
    goto LABEL_35;
  }
  InitializeGlobalState(&g_ProtocolStateIsatap);
  dword_1800CA120 = 3;
  qword_1800CA118 = (__int64)off_1800C82E0;
  v7 = 2147483646;
  v8 = L"isatap";
  v9 = 1025;
  v10 = &Str;
  do
  {
    if ( !v7 )
      break;
    v6 = *(unsigned __int16 *)v8;
    if ( !(_WORD)v6 )
      break;
    *v10 = v6;
    v8 += 2;
    ++v10;
    --v7;
    --v9;
  }
  while ( v9 );
  g_IsatapReusableAdapterCleanupTimer = 0;
  v11 = v10 - 1;
  if ( v9 )
    v11 = v10;
  *v11 = 0;
  word_1800CA932 = 0;
  dword_1800CA124 = 2;
  dword_1800CA128 = 60;
  dword_1800CA12C = 2;
  HIDWORD(qword_1800CA960) = (unsigned __int8)IsOSServerSku(v11, v9, v8, v6) != 0;
  dword_1800CA968 = 2;
  EventW = CreateEventW(0, 1, 1, 0);
  qword_1800CA970 = EventW;
  if ( EventW )
  {
    ResetEvent(EventW);
    do
    {
      v13 = dword_1800CA968;
      if ( (dword_1800CA968 & 1) != 0 )
      {
        EventWrite0(0x2000000, L"IsatapReferenceGlobalForInterface FAILED");
        goto LABEL_27;
      }
    }
    while ( v13 != _InterlockedCompareExchange(&dword_1800CA968, dword_1800CA968 + 2, dword_1800CA968) );
    v14 = IsatapInitializeTimer();
    v2 = v14;
    if ( v14 )
    {
      EventWrite0(0x2000000, L"IsatapInitializeTimer FAILED. Error:%d", v14);
      IsatapDereferenceGlobalForInterface();
    }
    else
    {
      if ( !(unsigned int)TpclCreateTimer(
                            &g_IsatapReusableAdapterCleanupTimer,
                            L"Isatap Reusable Adapter Cleanup Timer",
                            CleanupIsatapReusableAdaptersCallback,
                            0,
                            1,
                            86400000,
                            86400000) )
        g_IsatapReusableAdapterCleanupTimer = 0;
      LODWORD(qword_1800CA960) = 1;
      IsatapDeleteOrphanedInterfaceKeys();
      IsatapConfigurationChangeNotificationUnderLock();
      v15 = qword_1800CA958;
      if ( qword_1800CA958 )
      {
        do
        {
          v16 = *(_QWORD *)v15;
          if ( !*(_DWORD *)(v15 + 2676) && !*(_DWORD *)(v15 + 8) )
            DisableIsatapInterface();
          v15 = v16;
        }
        while ( v16 );
      }
    }
  }
LABEL_27:
  v17 = g_IsatapLock;
  LODWORD(v19) = ReleaseMutex(g_IsatapLock);
  LODWORD(v18) = 3275;
  EventWrite0(
    0x800000,
    L"Lock (%p) released at %S : %S : %u. Return %d",
    v17,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\isatap.c",
    "IsatapInitialize",
    v18,
    v19);
  v3 = g_IsatapReusableAdapterCleanupTimer;
  if ( v2 )
  {
    if ( g_IsatapReusableAdapterCleanupTimer )
    {
      TpclDestroyTimer(L"Isatap Reusable Adapter Cleanup Timer", g_IsatapReusableAdapterCleanupTimer, 0, 0);
      g_IsatapReusableAdapterCleanupTimer = 0;
    }
    goto LABEL_34;
  }
  if ( g_IsatapReusableAdapterCleanupTimer )
    TpclSetTimer(L"Isatap Reusable Adapter Cleanup Timer", g_IsatapReusableAdapterCleanupTimer, 86400000, 86400000);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 4) != 0 )
    McTemplateU0q_EventWriteTransfer(MS_IPHLPSVC_ETW_PROVIDER_ID_Context, EVENT_IPHLPSVC_ETW_PROTOCOL_INITIALIZED, 1);
LABEL_35:
  SetEvent(g_IsatapStartCompleteEvent);
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
      L"Leaving: IsatapInitialize");
  DereferenceServiceEx("IsatapInitialize", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\isatap.c", 3317);
}

```

## disassembly

```asm
0x180032e70  mov     [rsp+arg_0], rbx
0x180032e75  mov     [rsp+arg_8], rbp
0x180032e7a  push    rsi
0x180032e7b  push    rdi
0x180032e7c  push    r13
0x180032e7e  sub     rsp, 40h
0x180032e82  xor     esi, esi
0x180032e84  mov     edi, 426h
0x180032e89  cmp     cs:IpHlpSvcEtwEnabled, sil
0x180032e90  jz      short loc_180032EB5
0x180032e92  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, sil
0x180032e99  jge     short loc_180032EB5
0x180032e9b  lea     r8, aEnteredIsatapi_0; "Entered: IsatapInitialize"
0x180032ea2  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180032ea9  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180032eb0  call    McTemplateU0z_EventWriteTransfer
0x180032eb5  mov     r9, cs:g_IsatapLock
0x180032ebc  lea     r13, aIsatapinitiali; "IsatapInitialize"
0x180032ec3  mov     rdx, r13
0x180032ec6  lea     rcx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180032ecd  mov     r8d, 0C68h
0x180032ed3  call    GetAndTraceLock
0x180032ed8  test    eax, eax
0x180032eda  jnz     short loc_180032EF2
0x180032edc  lea     rdx, aGetLockFailed; "GET_LOCK FAILED"
0x180032ee3  mov     ecx, 2000000h
0x180032ee8  call    EventWrite0
0x180032eed  jmp     loc_18003314C
0x180032ef2  lea     rcx, g_ProtocolStateIsatap
0x180032ef9  call    InitializeGlobalState
0x180032efe  lea     rax, off_1800C82E0
0x180032f05  mov     cs:dword_1800CA120, 3
0x180032f0f  mov     ebx, 2
0x180032f14  mov     cs:qword_1800CA118, rax
0x180032f1b  mov     ecx, 7FFFFFFEh
0x180032f20  lea     r8, aIsatap_0; "isatap"
0x180032f27  mov     edx, 401h
0x180032f2c  lea     rax, Str
0x180032f33  lea     ebp, [rbx-1]
0x180032f36  test    rcx, rcx
0x180032f39  jz      short loc_180032F57
0x180032f3b  movzx   r9d, word ptr [r8]
0x180032f3f  test    r9w, r9w
0x180032f43  jz      short loc_180032F57
0x180032f45  mov     [rax], r9w
0x180032f49  add     r8, rbx
0x180032f4c  add     rax, rbx
0x180032f4f  sub     rcx, rbp
0x180032f52  sub     rdx, rbp
0x180032f55  jnz     short loc_180032F36
0x180032f57  test    rdx, rdx
0x180032f5a  mov     cs:g_IsatapReusableAdapterCleanupTimer, rsi
0x180032f61  lea     rcx, [rax-2]
0x180032f65  cmovnz  rcx, rax
0x180032f69  mov     [rcx], si
0x180032f6c  mov     cs:word_1800CA932, si
0x180032f73  mov     cs:dword_1800CA124, ebx
0x180032f79  mov     cs:dword_1800CA128, 3Ch ; '<'
0x180032f83  mov     cs:dword_1800CA12C, ebx
0x180032f89  mov     dword ptr cs:qword_1800CA960+4, esi
0x180032f8f  call    IsOSServerSku
0x180032f94  test    al, al
0x180032f96  jz      short loc_180032F9E
0x180032f98  mov     dword ptr cs:qword_1800CA960+4, ebp
0x180032f9e  xor     r9d, r9d; lpName
0x180032fa1  mov     cs:dword_1800CA968, ebx
0x180032fa7  mov     r8d, ebp; bInitialState
0x180032faa  mov     edx, ebp; bManualReset
0x180032fac  xor     ecx, ecx; lpEventAttributes
0x180032fae  call    cs:__imp_CreateEventW
0x180032fb5  nop     dword ptr [rax+rax+00h]
0x180032fba  mov     cs:qword_1800CA970, rax
0x180032fc1  test    rax, rax
0x180032fc4  jz      loc_1800330A6
0x180032fca  mov     rcx, rax; hEvent
0x180032fcd  call    cs:__imp_ResetEvent
0x180032fd4  nop     dword ptr [rax+rax+00h]
0x180032fd9  mov     eax, cs:dword_1800CA968
0x180032fdf  test    bpl, al
0x180032fe2  jnz     loc_180033095
0x180032fe8  lea     ecx, [rax+2]
0x180032feb  lock cmpxchg cs:dword_1800CA968, ecx
0x180032ff3  jnz     short loc_180032FD9
0x180032ff5  call    IsatapInitializeTimer
0x180032ffa  mov     edi, eax
0x180032ffc  test    eax, eax
0x180032ffe  jz      short loc_18003301E
0x180033000  mov     r8d, eax
0x180033003  lea     rdx, aIsatapinitiali_0; "IsatapInitializeTimer FAILED. Error:%d"
0x18003300a  mov     ecx, 2000000h
0x18003300f  call    EventWrite0
0x180033014  call    IsatapDereferenceGlobalForInterface
0x180033019  jmp     loc_1800330A6
0x18003301e  mov     dword ptr [rsp+58h+var_28], 5265C00h
0x180033026  lea     r8, CleanupIsatapReusableAdaptersCallback
0x18003302d  mov     dword ptr [rsp+58h+var_30], 5265C00h
0x180033035  lea     rdx, aIsatapReusable; "Isatap Reusable Adapter Cleanup Timer"
0x18003303c  xor     r9d, r9d
0x18003303f  mov     dword ptr [rsp+58h+var_38], ebp
0x180033043  lea     rcx, g_IsatapReusableAdapterCleanupTimer
0x18003304a  call    TpclCreateTimer
0x18003304f  test    eax, eax
0x180033051  jnz     short loc_18003305A
0x180033053  mov     cs:g_IsatapReusableAdapterCleanupTimer, rsi
0x18003305a  mov     dword ptr cs:qword_1800CA960, ebp
0x180033060  call    IsatapDeleteOrphanedInterfaceKeys
0x180033065  call    IsatapConfigurationChangeNotificationUnderLock
0x18003306a  mov     rcx, cs:qword_1800CA958
0x180033071  test    rcx, rcx
0x180033074  jz      short loc_1800330A6
0x180033076  mov     rbx, [rcx]
0x180033079  cmp     [rcx+0A74h], esi
0x18003307f  jnz     short loc_18003308B
0x180033081  cmp     [rcx+8], esi
0x180033084  jnz     short loc_18003308B
0x180033086  call    DisableIsatapInterface
0x18003308b  mov     rcx, rbx
0x18003308e  test    rbx, rbx
0x180033091  jnz     short loc_180033076
0x180033093  jmp     short loc_1800330A6
0x180033095  lea     rdx, aIsatapreferenc_0; "IsatapReferenceGlobalForInterface FAILE"...
0x18003309c  mov     ecx, 2000000h
0x1800330a1  call    EventWrite0
0x1800330a6  mov     rbx, cs:g_IsatapLock
0x1800330ad  mov     rcx, rbx; hMutex
0x1800330b0  call    cs:__imp_ReleaseMutex
0x1800330b7  nop     dword ptr [rax+rax+00h]
0x1800330bc  mov     dword ptr [rsp+58h+var_28], eax
0x1800330c0  lea     r9, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800330c7  mov     dword ptr [rsp+58h+var_30], 0CCBh
0x1800330cf  mov     r8, rbx
0x1800330d2  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x1800330d9  mov     [rsp+58h+var_38], r13
0x1800330de  mov     ecx, 800000h
0x1800330e3  call    EventWrite0
0x1800330e8  mov     rdx, cs:g_IsatapReusableAdapterCleanupTimer
0x1800330ef  test    edi, edi
0x1800330f1  jnz     short loc_18003312E
0x1800330f3  test    rdx, rdx
0x1800330f6  jz      short loc_18003310D
0x1800330f8  mov     r9d, 5265C00h
0x1800330fe  lea     rcx, aIsatapReusable; "Isatap Reusable Adapter Cleanup Timer"
0x180033105  mov     r8d, r9d
0x180033108  call    TpclSetTimer
0x18003310d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 4
0x180033114  jz      short loc_180033153
0x180033116  mov     r8d, ebp
0x180033119  lea     rdx, EVENT_IPHLPSVC_ETW_PROTOCOL_INITIALIZED
0x180033120  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180033127  call    McTemplateU0q_EventWriteTransfer
0x18003312c  jmp     short loc_180033153
0x18003312e  test    rdx, rdx
0x180033131  jz      short loc_18003314C
0x180033133  xor     r9d, r9d
0x180033136  lea     rcx, aIsatapReusable; "Isatap Reusable Adapter Cleanup Timer"
0x18003313d  xor     r8d, r8d
0x180033140  call    TpclDestroyTimer
0x180033145  mov     cs:g_IsatapReusableAdapterCleanupTimer, rsi
0x18003314c  mov     ecx, edi
0x18003314e  call    SetStopServiceEvent
0x180033153  mov     rcx, cs:g_IsatapStartCompleteEvent; hEvent
0x18003315a  call    cs:__imp_SetEvent
0x180033161  nop     dword ptr [rax+rax+00h]
0x180033166  cmp     cs:IpHlpSvcEtwEnabled, sil
0x18003316d  jz      short loc_180033192
0x18003316f  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, sil
0x180033176  jge     short loc_180033192
0x180033178  lea     r8, aLeavingIsatapi; "Leaving: IsatapInitialize"
0x18003317f  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180033186  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18003318d  call    McTemplateU0z_EventWriteTransfer
0x180033192  mov     r8d, 0CF5h
0x180033198  lea     rdx, aOnecoreuapNetN_39; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003319f  mov     rcx, r13
0x1800331a2  mov     rbx, [rsp+58h+arg_0]
0x1800331a7  mov     rbp, [rsp+58h+arg_8]
0x1800331ac  add     rsp, 40h
0x1800331b0  pop     r13
0x1800331b2  pop     rdi
0x1800331b3  pop     rsi
0x1800331b4  jmp     DereferenceServiceEx
```
