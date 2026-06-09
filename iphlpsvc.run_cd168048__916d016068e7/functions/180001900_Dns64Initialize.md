# Dns64Initialize

- ea: `0x180001900`
- end: `0x180001ac9`
- name: `Dns64Initialize`
- size: `457`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001900`
- `0x180001e74`
- `0x180004f50`
- `0x18000d7b0`
- `0x180013aa0`
- `0x180042fe8`
- `0x180043320`
- `0x180043398`
- `0x18006997c`

## import_xrefs

- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180001a20`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180001a20`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001a9e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001a9e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001962`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001962`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000192b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000192b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001988`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001988`

## string_xrefs

- `0x180001975`: `onecoreuap\net\netio\iphlpsvc\service\dns64.c`
- `0x1800019af`: `Dns64ConfigurationChangeNotification`
- `0x1800019b9`: `ReferenceService: ++%u (%hs) @ %ls:%u`

## pseudocode

```c
void __fastcall Dns64Initialize(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  char v2; // bl
  int v3; // ecx
  int v4; // eax
  NTSTATUS v5; // eax

  v2 = 31;
  qword_1800CBD40 = (__int64)&g_Dns64DomainInterfaceListHead;
  g_Dns64DomainInterfaceListHead = (__int64)&g_Dns64DomainInterfaceListHead;
  InitializeCriticalSection(&g_Dns64ConfigChangeLock);
  g_Dns64IpInterfaceChangeNotification = 0;
  g_Dns64NLMNetworkChangeNotification = 0;
  g_Dns64Translator = 0;
  g_Dns64GlobalReferenceObjectEvent = CreateEventW(0, 0, 0, 0);
  if ( g_Dns64GlobalReferenceObjectEvent )
  {
    g_Dns64GlobalReferenceObject = 2;
    Dns64InitializeGlobalPerformanceCounters();
    EventWrite0(
      0x40000,
      L"ReferenceService: ++%u (%hs) @ %ls:%u",
      ((unsigned int)g_Reference >> 1) & 0x3FFFFFFF,
      "Dns64ConfigurationChangeNotification",
      L"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64.c",
      173);
    do
    {
      v4 = g_Reference;
      if ( (g_Reference & 1) != 0 )
        goto LABEL_10;
    }
    while ( v4 != _InterlockedCompareExchange(&g_Reference, g_Reference + 2, g_Reference) );
    Dns64ConfigurationChangeNotification(0, 0);
    v5 = NotifyIpInterfaceChange(0x17u, Dns64IpInterfaceChangeCallback, 0, 0, &g_Dns64IpInterfaceChangeNotification);
    v2 = v5;
    if ( v5 )
    {
LABEL_10:
      Dns64Uninitialize();
      goto LABEL_11;
    }
    RegisterForNetworkChangeNotification(
      &g_Dns64NLMNetworkChangeNotification,
      0,
      0,
      Dns64DomainNetworkChangeNotification,
      0);
    if ( g_Dns64NLMNetworkChangeNotification )
      Dns64DomainNetworkChangeNotification(0, (enum NLM_NETWORK_PROPERTY_CHANGE)0);
    else
      Dns64Uninitialize();
  }
  else
  {
    DeleteCriticalSection(&g_Dns64ConfigChangeLock);
LABEL_11:
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x8000) != 0 )
      McTemplateU0pzq_EventWriteTransfer(
        v3,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_MODULE_INIT_FAILED,
        0,
        (unsigned int)&word_180087660,
        v2);
  }
  SetEvent(g_Dns64StartCompleteEvent);
  DereferenceServiceEx("InitializeDns64", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64.c", 217);
}

```

## disassembly

```asm
0x180001900  mov     [rsp+arg_0], rbx
0x180001905  push    rsi
0x180001906  sub     rsp, 30h
0x18000190a  lea     rax, g_Dns64DomainInterfaceListHead
0x180001911  mov     ebx, 1Fh
0x180001916  lea     rcx, g_Dns64ConfigChangeLock; lpCriticalSection
0x18000191d  mov     cs:qword_1800CBD40, rax
0x180001924  mov     cs:g_Dns64DomainInterfaceListHead, rax
0x18000192b  call    cs:__imp_InitializeCriticalSection
0x180001932  nop     dword ptr [rax+rax+00h]
0x180001937  xor     r9d, r9d; lpName
0x18000193a  mov     cs:g_Dns64IpInterfaceChangeNotification, 0
0x180001945  xor     r8d, r8d; bInitialState
0x180001948  mov     cs:g_Dns64NLMNetworkChangeNotification, 0
0x180001953  xor     edx, edx; bManualReset
0x180001955  mov     cs:g_Dns64Translator, 0
0x180001960  xor     ecx, ecx; lpEventAttributes
0x180001962  call    cs:__imp_CreateEventW
0x180001969  nop     dword ptr [rax+rax+00h]
0x18000196e  mov     cs:g_Dns64GlobalReferenceObjectEvent, rax
0x180001975  lea     rsi, aOnecoreuapNetN_13; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18000197c  test    rax, rax
0x18000197f  jnz     short loc_180001999
0x180001981  lea     rcx, g_Dns64ConfigChangeLock; lpCriticalSection
0x180001988  call    cs:__imp_DeleteCriticalSection
0x18000198f  nop     dword ptr [rax+rax+00h]
0x180001994  jmp     loc_180001A74
0x180001999  mov     cs:g_Dns64GlobalReferenceObject, 2
0x1800019a3  call    Dns64InitializeGlobalPerformanceCounters
0x1800019a8  mov     r8d, cs:g_Reference
0x1800019af  lea     r9, aDns64configura; "Dns64ConfigurationChangeNotification"
0x1800019b6  shr     r8d, 1
0x1800019b9  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x1800019c0  and     r8d, 3FFFFFFFh
0x1800019c7  mov     [rsp+38h+var_10], 0ADh
0x1800019cf  mov     ecx, 40000h
0x1800019d4  mov     [rsp+38h+NotificationHandle], rsi
0x1800019d9  call    EventWrite0
0x1800019de  mov     eax, cs:g_Reference
0x1800019e4  test    al, 1
0x1800019e6  jnz     loc_180001A6F
0x1800019ec  lea     ecx, [rax+2]
0x1800019ef  lock cmpxchg cs:g_Reference, ecx
0x1800019f7  jnz     short loc_1800019DE
0x1800019f9  xor     edx, edx; Context
0x1800019fb  xor     ecx, ecx; Instance
0x1800019fd  call    Dns64ConfigurationChangeNotification
0x180001a02  lea     rax, g_Dns64IpInterfaceChangeNotification
0x180001a09  mov     ecx, 17h; Family
0x180001a0e  xor     r9d, r9d; InitialNotification
0x180001a11  mov     [rsp+38h+NotificationHandle], rax; NotificationHandle
0x180001a16  xor     r8d, r8d; CallerContext
0x180001a19  lea     rdx, Dns64IpInterfaceChangeCallback; Callback
0x180001a20  call    cs:__imp_NotifyIpInterfaceChange
0x180001a27  nop     dword ptr [rax+rax+00h]
0x180001a2c  mov     ebx, eax
0x180001a2e  test    eax, eax
0x180001a30  jnz     short loc_180001A6F
0x180001a32  lea     r9, Dns64DomainNetworkChangeNotification; void (*)(struct _GUID *, enum NLM_NETWORK_PROPERTY_CHANGE)
0x180001a39  mov     [rsp+38h+NotificationHandle], 0; void (*)(struct _GUID *)
0x180001a42  xor     r8d, r8d; void (*)(struct _GUID *, enum NLM_CONNECTIVITY)
0x180001a45  lea     rcx, g_Dns64NLMNetworkChangeNotification; struct CNlmEventSink **
0x180001a4c  xor     edx, edx; void (*)(struct _GUID *)
0x180001a4e  call    RegisterForNetworkChangeNotification
0x180001a53  cmp     cs:g_Dns64NLMNetworkChangeNotification, 0
0x180001a5b  jnz     short loc_180001A64
0x180001a5d  call    Dns64Uninitialize
0x180001a62  jmp     short loc_180001A97
0x180001a64  xor     edx, edx; enum NLM_NETWORK_PROPERTY_CHANGE
0x180001a66  xor     ecx, ecx; struct _GUID *
0x180001a68  call    Dns64DomainNetworkChangeNotification
0x180001a6d  jmp     short loc_180001A97
0x180001a6f  call    Dns64Uninitialize
0x180001a74  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 0
0x180001a7b  jge     short loc_180001A97
0x180001a7d  lea     r9, word_180087660
0x180001a84  mov     dword ptr [rsp+38h+NotificationHandle], ebx
0x180001a88  xor     r8d, r8d
0x180001a8b  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_MODULE_INIT_FAILED
0x180001a92  call    McTemplateU0pzq_EventWriteTransfer
0x180001a97  mov     rcx, cs:g_Dns64StartCompleteEvent; hEvent
0x180001a9e  call    cs:__imp_SetEvent
0x180001aa5  nop     dword ptr [rax+rax+00h]
0x180001aaa  mov     r8d, 0D9h
0x180001ab0  lea     rcx, aInitializedns6; "InitializeDns64"
0x180001ab7  mov     rdx, rsi
0x180001aba  mov     rbx, [rsp+38h+arg_0]
0x180001abf  add     rsp, 30h
0x180001ac3  pop     rsi
0x180001ac4  jmp     DereferenceServiceEx
```
