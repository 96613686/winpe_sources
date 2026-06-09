# IsatapInitialize

- ea: `0x180032e60`
- end: `0x1800331a9`
- name: `IsatapInitialize`
- size: `841`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004f50`
- `0x180009000`
- `0x18000ce90`
- `0x18000d7b0`
- `0x180014098`
- `0x1800159f0`
- `0x180029d08`
- `0x180032e60`
- `0x1800336f4`
- `0x180039220`
- `0x180039c68`
- `0x18003bc8c`
- `0x18003e154`
- `0x180041020`
- `0x180059318`
- `0x180059c98`
- `0x180059e58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180032fbd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180032fbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800330a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800330a0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003314a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003314a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032f9e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032f9e`

## string_xrefs

- `0x180032eb6`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`
- `0x1800330b0`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`
- `0x180033188`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`

## pseudocode

```c
void __fastcall IsatapInitialize(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  unsigned int v2; // edi
  __int64 v3; // r9
  __int64 v4; // rcx
  const char *v5; // r8
  __int64 v6; // rdx
  WCHAR *v7; // rax
  WCHAR *v8; // rcx
  HANDLE EventW; // rax
  int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rbx
  HANDLE v14; // rbx
  __int64 v15; // [rsp+28h] [rbp-30h]
  __int64 v16; // [rsp+30h] [rbp-28h]

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
    SetStopServiceEvent(v2);
    goto LABEL_35;
  }
  InitializeGlobalState(&g_ProtocolStateIsatap);
  dword_1800CA120 = 3;
  qword_1800CA118 = (__int64)off_1800C82E0;
  v4 = 2147483646;
  v5 = L"isatap";
  v6 = 1025;
  v7 = &Str;
  do
  {
    if ( !v4 )
      break;
    v3 = *(unsigned __int16 *)v5;
    if ( !(_WORD)v3 )
      break;
    *v7 = v3;
    v5 += 2;
    ++v7;
    --v4;
    --v6;
  }
  while ( v6 );
  g_IsatapReusableAdapterCleanupTimer = 0;
  v8 = v7 - 1;
  if ( v6 )
    v8 = v7;
  *v8 = 0;
  word_1800CA932 = 0;
  dword_1800CA124 = 2;
  dword_1800CA128 = 60;
  dword_1800CA12C = 2;
  HIDWORD(qword_1800CA960) = (unsigned __int8)IsOSServerSku(v8, v6, v5, v3) != 0;
  dword_1800CA968 = 2;
  EventW = CreateEventW(0, 1, 1, 0);
  qword_1800CA970 = EventW;
  if ( EventW )
  {
    ResetEvent(EventW);
    do
    {
      v10 = dword_1800CA968;
      if ( (dword_1800CA968 & 1) != 0 )
      {
        EventWrite0(0x2000000, L"IsatapReferenceGlobalForInterface FAILED");
        goto LABEL_27;
      }
    }
    while ( v10 != _InterlockedCompareExchange(&dword_1800CA968, dword_1800CA968 + 2, dword_1800CA968) );
    v11 = IsatapInitializeTimer();
    v2 = v11;
    if ( v11 )
    {
      EventWrite0(0x2000000, L"IsatapInitializeTimer FAILED. Error:%d", v11);
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
      v12 = qword_1800CA958;
      if ( qword_1800CA958 )
      {
        do
        {
          v13 = *(_QWORD *)v12;
          if ( !*(_DWORD *)(v12 + 2676) && !*(_DWORD *)(v12 + 8) )
            DisableIsatapInterface();
          v12 = v13;
        }
        while ( v13 );
      }
    }
  }
LABEL_27:
  v14 = g_IsatapLock;
  LODWORD(v16) = ReleaseMutex(g_IsatapLock);
  LODWORD(v15) = 3275;
  EventWrite0(
    0x800000,
    L"Lock (%p) released at %S : %S : %u. Return %d",
    v14,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\isatap.c",
    "IsatapInitialize",
    v15,
    v16);
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
0x180032e60  mov     [rsp+arg_0], rbx
0x180032e65  mov     [rsp+arg_8], rbp
0x180032e6a  push    rsi
0x180032e6b  push    rdi
0x180032e6c  push    r13
0x180032e6e  sub     rsp, 40h
0x180032e72  xor     esi, esi
0x180032e74  mov     edi, 426h
0x180032e79  cmp     cs:IpHlpSvcEtwEnabled, sil
0x180032e80  jz      short loc_180032EA5
0x180032e82  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, sil
0x180032e89  jge     short loc_180032EA5
0x180032e8b  lea     r8, aEnteredIsatapi_0; "Entered: IsatapInitialize"
0x180032e92  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180032e99  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180032ea0  call    McTemplateU0z_EventWriteTransfer
0x180032ea5  mov     r9, cs:g_IsatapLock
0x180032eac  lea     r13, aIsatapinitiali; "IsatapInitialize"
0x180032eb3  mov     rdx, r13
0x180032eb6  lea     rcx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180032ebd  mov     r8d, 0C68h
0x180032ec3  call    GetAndTraceLock
0x180032ec8  test    eax, eax
0x180032eca  jnz     short loc_180032EE2
0x180032ecc  lea     rdx, aGetLockFailed; "GET_LOCK FAILED"
0x180032ed3  mov     ecx, 2000000h
0x180032ed8  call    EventWrite0
0x180032edd  jmp     loc_18003313C
0x180032ee2  lea     rcx, g_ProtocolStateIsatap
0x180032ee9  call    InitializeGlobalState
0x180032eee  lea     rax, off_1800C82E0
0x180032ef5  mov     cs:dword_1800CA120, 3
0x180032eff  mov     ebx, 2
0x180032f04  mov     cs:qword_1800CA118, rax
0x180032f0b  mov     ecx, 7FFFFFFEh
0x180032f10  lea     r8, aIsatap_0; "isatap"
0x180032f17  mov     edx, 401h
0x180032f1c  lea     rax, Str
0x180032f23  lea     ebp, [rbx-1]
0x180032f26  test    rcx, rcx
0x180032f29  jz      short loc_180032F47
0x180032f2b  movzx   r9d, word ptr [r8]
0x180032f2f  test    r9w, r9w
0x180032f33  jz      short loc_180032F47
0x180032f35  mov     [rax], r9w
0x180032f39  add     r8, rbx
0x180032f3c  add     rax, rbx
0x180032f3f  sub     rcx, rbp
0x180032f42  sub     rdx, rbp
0x180032f45  jnz     short loc_180032F26
0x180032f47  test    rdx, rdx
0x180032f4a  mov     cs:g_IsatapReusableAdapterCleanupTimer, rsi
0x180032f51  lea     rcx, [rax-2]
0x180032f55  cmovnz  rcx, rax
0x180032f59  mov     [rcx], si
0x180032f5c  mov     cs:word_1800CA932, si
0x180032f63  mov     cs:dword_1800CA124, ebx
0x180032f69  mov     cs:dword_1800CA128, 3Ch ; '<'
0x180032f73  mov     cs:dword_1800CA12C, ebx
0x180032f79  mov     dword ptr cs:qword_1800CA960+4, esi
0x180032f7f  call    IsOSServerSku
0x180032f84  test    al, al
0x180032f86  jz      short loc_180032F8E
0x180032f88  mov     dword ptr cs:qword_1800CA960+4, ebp
0x180032f8e  xor     r9d, r9d; lpName
0x180032f91  mov     cs:dword_1800CA968, ebx
0x180032f97  mov     r8d, ebp; bInitialState
0x180032f9a  mov     edx, ebp; bManualReset
0x180032f9c  xor     ecx, ecx; lpEventAttributes
0x180032f9e  call    cs:__imp_CreateEventW
0x180032fa5  nop     dword ptr [rax+rax+00h]
0x180032faa  mov     cs:qword_1800CA970, rax
0x180032fb1  test    rax, rax
0x180032fb4  jz      loc_180033096
0x180032fba  mov     rcx, rax; hEvent
0x180032fbd  call    cs:__imp_ResetEvent
0x180032fc4  nop     dword ptr [rax+rax+00h]
0x180032fc9  mov     eax, cs:dword_1800CA968
0x180032fcf  test    bpl, al
0x180032fd2  jnz     loc_180033085
0x180032fd8  lea     ecx, [rax+2]
0x180032fdb  lock cmpxchg cs:dword_1800CA968, ecx
0x180032fe3  jnz     short loc_180032FC9
0x180032fe5  call    IsatapInitializeTimer
0x180032fea  mov     edi, eax
0x180032fec  test    eax, eax
0x180032fee  jz      short loc_18003300E
0x180032ff0  mov     r8d, eax
0x180032ff3  lea     rdx, aIsatapinitiali_0; "IsatapInitializeTimer FAILED. Error:%d"
0x180032ffa  mov     ecx, 2000000h
0x180032fff  call    EventWrite0
0x180033004  call    IsatapDereferenceGlobalForInterface
0x180033009  jmp     loc_180033096
0x18003300e  mov     dword ptr [rsp+58h+var_28], 5265C00h
0x180033016  lea     r8, CleanupIsatapReusableAdaptersCallback
0x18003301d  mov     dword ptr [rsp+58h+var_30], 5265C00h
0x180033025  lea     rdx, aIsatapReusable; "Isatap Reusable Adapter Cleanup Timer"
0x18003302c  xor     r9d, r9d
0x18003302f  mov     dword ptr [rsp+58h+var_38], ebp
0x180033033  lea     rcx, g_IsatapReusableAdapterCleanupTimer
0x18003303a  call    TpclCreateTimer
0x18003303f  test    eax, eax
0x180033041  jnz     short loc_18003304A
0x180033043  mov     cs:g_IsatapReusableAdapterCleanupTimer, rsi
0x18003304a  mov     dword ptr cs:qword_1800CA960, ebp
0x180033050  call    IsatapDeleteOrphanedInterfaceKeys
0x180033055  call    IsatapConfigurationChangeNotificationUnderLock
0x18003305a  mov     rcx, cs:qword_1800CA958
0x180033061  test    rcx, rcx
0x180033064  jz      short loc_180033096
0x180033066  mov     rbx, [rcx]
0x180033069  cmp     [rcx+0A74h], esi
0x18003306f  jnz     short loc_18003307B
0x180033071  cmp     [rcx+8], esi
0x180033074  jnz     short loc_18003307B
0x180033076  call    DisableIsatapInterface
0x18003307b  mov     rcx, rbx
0x18003307e  test    rbx, rbx
0x180033081  jnz     short loc_180033066
0x180033083  jmp     short loc_180033096
0x180033085  lea     rdx, aIsatapreferenc_0; "IsatapReferenceGlobalForInterface FAILE"...
0x18003308c  mov     ecx, 2000000h
0x180033091  call    EventWrite0
0x180033096  mov     rbx, cs:g_IsatapLock
0x18003309d  mov     rcx, rbx; hMutex
0x1800330a0  call    cs:__imp_ReleaseMutex
0x1800330a7  nop     dword ptr [rax+rax+00h]
0x1800330ac  mov     dword ptr [rsp+58h+var_28], eax
0x1800330b0  lea     r9, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800330b7  mov     dword ptr [rsp+58h+var_30], 0CCBh
0x1800330bf  mov     r8, rbx
0x1800330c2  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x1800330c9  mov     [rsp+58h+var_38], r13
0x1800330ce  mov     ecx, 800000h
0x1800330d3  call    EventWrite0
0x1800330d8  mov     rdx, cs:g_IsatapReusableAdapterCleanupTimer
0x1800330df  test    edi, edi
0x1800330e1  jnz     short loc_18003311E
0x1800330e3  test    rdx, rdx
0x1800330e6  jz      short loc_1800330FD
0x1800330e8  mov     r9d, 5265C00h
0x1800330ee  lea     rcx, aIsatapReusable; "Isatap Reusable Adapter Cleanup Timer"
0x1800330f5  mov     r8d, r9d
0x1800330f8  call    TpclSetTimer
0x1800330fd  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 4
0x180033104  jz      short loc_180033143
0x180033106  mov     r8d, ebp
0x180033109  lea     rdx, EVENT_IPHLPSVC_ETW_PROTOCOL_INITIALIZED
0x180033110  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180033117  call    McTemplateU0q_EventWriteTransfer
0x18003311c  jmp     short loc_180033143
0x18003311e  test    rdx, rdx
0x180033121  jz      short loc_18003313C
0x180033123  xor     r9d, r9d
0x180033126  lea     rcx, aIsatapReusable; "Isatap Reusable Adapter Cleanup Timer"
0x18003312d  xor     r8d, r8d
0x180033130  call    TpclDestroyTimer
0x180033135  mov     cs:g_IsatapReusableAdapterCleanupTimer, rsi
0x18003313c  mov     ecx, edi
0x18003313e  call    SetStopServiceEvent
0x180033143  mov     rcx, cs:g_IsatapStartCompleteEvent; hEvent
0x18003314a  call    cs:__imp_SetEvent
0x180033151  nop     dword ptr [rax+rax+00h]
0x180033156  cmp     cs:IpHlpSvcEtwEnabled, sil
0x18003315d  jz      short loc_180033182
0x18003315f  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, sil
0x180033166  jge     short loc_180033182
0x180033168  lea     r8, aLeavingIsatapi; "Leaving: IsatapInitialize"
0x18003316f  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180033176  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18003317d  call    McTemplateU0z_EventWriteTransfer
0x180033182  mov     r8d, 0CF5h
0x180033188  lea     rdx, aOnecoreuapNetN_39; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003318f  mov     rcx, r13
0x180033192  mov     rbx, [rsp+58h+arg_0]
0x180033197  mov     rbp, [rsp+58h+arg_8]
0x18003319c  add     rsp, 40h
0x1800331a0  pop     r13
0x1800331a2  pop     rdi
0x1800331a3  pop     rsi
0x1800331a4  jmp     DereferenceServiceEx
```
