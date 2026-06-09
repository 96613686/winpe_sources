# Dns64Initialize

- ea: `0x180001910`
- end: `0x180001ad9`
- name: `Dns64Initialize`
- size: `457`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001910`
- `0x180001e84`
- `0x180004f60`
- `0x18000d7c0`
- `0x180013ab0`
- `0x180042fa8`
- `0x1800432e0`
- `0x180043358`
- `0x18006999c`

## import_xrefs

- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180001a30`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180001a30`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001aae`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001aae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001972`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001972`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000193b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000193b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001998`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001998`

## string_xrefs

- `0x180001985`: `onecoreuap\net\netio\iphlpsvc\service\dns64.c`
- `0x1800019bf`: `Dns64ConfigurationChangeNotification`
- `0x1800019c9`: `ReferenceService: ++%u (%hs) @ %ls:%u`

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
0x180001910  mov     [rsp+arg_0], rbx
0x180001915  push    rsi
0x180001916  sub     rsp, 30h
0x18000191a  lea     rax, g_Dns64DomainInterfaceListHead
0x180001921  mov     ebx, 1Fh
0x180001926  lea     rcx, g_Dns64ConfigChangeLock; lpCriticalSection
0x18000192d  mov     cs:qword_1800CBD40, rax
0x180001934  mov     cs:g_Dns64DomainInterfaceListHead, rax
0x18000193b  call    cs:__imp_InitializeCriticalSection
0x180001942  nop     dword ptr [rax+rax+00h]
0x180001947  xor     r9d, r9d; lpName
0x18000194a  mov     cs:g_Dns64IpInterfaceChangeNotification, 0
0x180001955  xor     r8d, r8d; bInitialState
0x180001958  mov     cs:g_Dns64NLMNetworkChangeNotification, 0
0x180001963  xor     edx, edx; bManualReset
0x180001965  mov     cs:g_Dns64Translator, 0
0x180001970  xor     ecx, ecx; lpEventAttributes
0x180001972  call    cs:__imp_CreateEventW
0x180001979  nop     dword ptr [rax+rax+00h]
0x18000197e  mov     cs:g_Dns64GlobalReferenceObjectEvent, rax
0x180001985  lea     rsi, aOnecoreuapNetN_13; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18000198c  test    rax, rax
0x18000198f  jnz     short loc_1800019A9
0x180001991  lea     rcx, g_Dns64ConfigChangeLock; lpCriticalSection
0x180001998  call    cs:__imp_DeleteCriticalSection
0x18000199f  nop     dword ptr [rax+rax+00h]
0x1800019a4  jmp     loc_180001A84
0x1800019a9  mov     cs:g_Dns64GlobalReferenceObject, 2
0x1800019b3  call    Dns64InitializeGlobalPerformanceCounters
0x1800019b8  mov     r8d, cs:g_Reference
0x1800019bf  lea     r9, aDns64configura; "Dns64ConfigurationChangeNotification"
0x1800019c6  shr     r8d, 1
0x1800019c9  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x1800019d0  and     r8d, 3FFFFFFFh
0x1800019d7  mov     [rsp+38h+var_10], 0ADh
0x1800019df  mov     ecx, 40000h
0x1800019e4  mov     [rsp+38h+NotificationHandle], rsi
0x1800019e9  call    EventWrite0
0x1800019ee  mov     eax, cs:g_Reference
0x1800019f4  test    al, 1
0x1800019f6  jnz     loc_180001A7F
0x1800019fc  lea     ecx, [rax+2]
0x1800019ff  lock cmpxchg cs:g_Reference, ecx
0x180001a07  jnz     short loc_1800019EE
0x180001a09  xor     edx, edx; Context
0x180001a0b  xor     ecx, ecx; Instance
0x180001a0d  call    Dns64ConfigurationChangeNotification
0x180001a12  lea     rax, g_Dns64IpInterfaceChangeNotification
0x180001a19  mov     ecx, 17h; Family
0x180001a1e  xor     r9d, r9d; InitialNotification
0x180001a21  mov     [rsp+38h+NotificationHandle], rax; NotificationHandle
0x180001a26  xor     r8d, r8d; CallerContext
0x180001a29  lea     rdx, Dns64IpInterfaceChangeCallback; Callback
0x180001a30  call    cs:__imp_NotifyIpInterfaceChange
0x180001a37  nop     dword ptr [rax+rax+00h]
0x180001a3c  mov     ebx, eax
0x180001a3e  test    eax, eax
0x180001a40  jnz     short loc_180001A7F
0x180001a42  lea     r9, Dns64DomainNetworkChangeNotification; void (*)(struct _GUID *, enum NLM_NETWORK_PROPERTY_CHANGE)
0x180001a49  mov     [rsp+38h+NotificationHandle], 0; void (*)(struct _GUID *)
0x180001a52  xor     r8d, r8d; void (*)(struct _GUID *, enum NLM_CONNECTIVITY)
0x180001a55  lea     rcx, g_Dns64NLMNetworkChangeNotification; struct CNlmEventSink **
0x180001a5c  xor     edx, edx; void (*)(struct _GUID *)
0x180001a5e  call    RegisterForNetworkChangeNotification
0x180001a63  cmp     cs:g_Dns64NLMNetworkChangeNotification, 0
0x180001a6b  jnz     short loc_180001A74
0x180001a6d  call    Dns64Uninitialize
0x180001a72  jmp     short loc_180001AA7
0x180001a74  xor     edx, edx; enum NLM_NETWORK_PROPERTY_CHANGE
0x180001a76  xor     ecx, ecx; struct _GUID *
0x180001a78  call    Dns64DomainNetworkChangeNotification
0x180001a7d  jmp     short loc_180001AA7
0x180001a7f  call    Dns64Uninitialize
0x180001a84  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 0
0x180001a8b  jge     short loc_180001AA7
0x180001a8d  lea     r9, word_180087660
0x180001a94  mov     dword ptr [rsp+38h+NotificationHandle], ebx
0x180001a98  xor     r8d, r8d
0x180001a9b  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_MODULE_INIT_FAILED
0x180001aa2  call    McTemplateU0pzq_EventWriteTransfer
0x180001aa7  mov     rcx, cs:g_Dns64StartCompleteEvent; hEvent
0x180001aae  call    cs:__imp_SetEvent
0x180001ab5  nop     dword ptr [rax+rax+00h]
0x180001aba  mov     r8d, 0D9h
0x180001ac0  lea     rcx, aInitializedns6; "InitializeDns64"
0x180001ac7  mov     rdx, rsi
0x180001aca  mov     rbx, [rsp+38h+arg_0]
0x180001acf  add     rsp, 30h
0x180001ad3  pop     rsi
0x180001ad4  jmp     DereferenceServiceEx
```
