# NcbPolicyInitialize

- ea: `0x18002293c`
- end: `0x180022b7a`
- name: `NcbPolicyInitialize`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015dc0`

## callees

- `0x18000723c`
- `0x1800075c4`
- `0x18000a0a0`
- `0x180013ab0`
- `0x180017d00`
- `0x180020a90`
- `0x180020ddc`
- `0x18002290c`
- `0x18002293c`
- `0x180022c54`
- `0x180022d28`
- `0x180022ddc`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x180022a94`
- `ntdll!RtlDeleteHashTable` at `0x180022a94`
- `ntdll!RtlCreateHashTable` at `0x1800229bb`
- `ntdll!RtlCreateHashTable` at `0x1800229bb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022973`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022973`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022aa6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022aa6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022a5d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022a5d`
- `IPHLPAPI!InternalGetRtcSlotInformation` at `0x1800229df`
- `IPHLPAPI!InternalGetRtcSlotInformation` at `0x1800229df`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180022b07`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180022b07`

## pseudocode

```c
__int64 __fastcall NcbPolicyInitialize(__int64 a1, __int64 a2)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  unsigned int v5; // ebx
  unsigned int RtcSlotInformation; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  DWORD v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // r8d
  _QWORD Recipient[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 *v25; // [rsp+50h] [rbp+8h] BYREF

  v25 = 0;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(a1, a2, L"NcbPolicy: Starting initialization of NCB policy module - ", 0);
  InitializeCriticalSection(&g_NcbPolicyLock);
  v2 = NcbCCResetInitialize();
  v5 = v2;
  if ( v2 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v4, v3, L"Failed to initialize NCB CCR module", v2);
    goto LABEL_24;
  }
  v25 = g_NcbPolicies;
  if ( !(unsigned __int8)RtlCreateHashTable(&v25, 0, 0) )
  {
    v5 = 8;
LABEL_23:
    NcbCCResetUninitialize();
LABEL_24:
    DeleteCriticalSection(&g_NcbPolicyLock);
    goto LABEL_30;
  }
  RtcSlotInformation = InternalGetRtcSlotInformation(
                         0,
                         &g_NcbPolicyMaxHardwareSlotsAllowed,
                         &g_NcbPolicyMaxSoftwareSlotsAllowed);
  v5 = RtcSlotInformation;
  if ( RtcSlotInformation )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v8,
        v7,
        L"NcbPolicy: Failed to query RTC Slot information with status - ",
        RtcSlotInformation);
    goto LABEL_22;
  }
  v9 = NcbPolicySubscribeToWnfEvents();
  v5 = v9;
  if ( v9 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v11, v10, L"NcbPolicy: Subscription to WNF events failed with status - ", v9);
    goto LABEL_21;
  }
  v12 = NcbPolicyPopulatePolicies();
  v5 = v12;
  if ( v12 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v14, v13, L"NcbPolicy: Initialization of policy set failed with status - ", v12);
LABEL_20:
    NcbPolicyUnsubscribeFromWnfEvents();
LABEL_21:
    NcbPolicyCleanupPolicies();
LABEL_22:
    RtlDeleteHashTable(g_NcbPolicies);
    goto LABEL_23;
  }
  g_NcbPolicyReferenceEvent = CreateEventW(0, 1, 0, 0);
  if ( !g_NcbPolicyReferenceEvent )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v16,
        v15,
        L"NcbPolicy: Creation of synchronization event failed with status - ",
        0);
    goto LABEL_20;
  }
  g_NcbPolicyChangeCallback = (__int64)NcbRegistrarPolicyChangeCallback;
  g_NcbPolicyReference = 2;
  NcbPolicyPolicyChangeCallback(0);
  NcbPolicySessionChangeHandlerHelper(0, 0, 0);
  Recipient[1] = 0;
  Recipient[0] = &NcbPolicyPowerStateChangeCallback;
  v19 = PowerSettingRegisterNotification(&GUID_LOW_POWER_EPOCH, 2u, Recipient, &g_NcbPolicyCsNotification);
  v5 = v19;
  if ( v19 )
  {
    g_NcbPolicyCsNotification = 0;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v21, v20, L"NcbPolicy: Subscription to CS events failed with status - ", v19);
    NcbPolicyUninitialize();
  }
  else
  {
    NcbCCResetSignal(0, 0, v22, 0, 1, 1);
    v5 = 0;
  }
LABEL_30:
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      v18,
      v17,
      L"NcbPolicy: Finished initialization of NCB policy module with status - ",
      v5);
  return v5;
}

```

## disassembly

```asm
0x18002293c  mov     [rsp+arg_8], rbx
0x180022941  mov     [rsp+arg_0], rcx
0x180022946  push    rbp
0x180022947  sub     rsp, 40h
0x18002294b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180022952  mov     [rsp+48h+arg_0], 0
0x18002295b  jz      short loc_18002296C
0x18002295d  xor     r9d, r9d
0x180022960  lea     r8, aNcbpolicyStart; "NcbPolicy: Starting initialization of N"...
0x180022967  call    McTemplateU0zq_EventWriteTransfer
0x18002296c  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180022973  call    cs:__imp_InitializeCriticalSection
0x180022979  call    NcbCCResetInitialize
0x18002297e  mov     ebx, eax
0x180022980  test    eax, eax
0x180022982  jz      short loc_1800229A5
0x180022984  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18002298b  jz      loc_180022A9F
0x180022991  mov     r9d, eax
0x180022994  lea     r8, aFailedToInitia; "Failed to initialize NCB CCR module"
0x18002299b  call    McTemplateU0zq_EventWriteTransfer
0x1800229a0  jmp     loc_180022A9F
0x1800229a5  lea     rbp, g_NcbPolicies
0x1800229ac  xor     r8d, r8d
0x1800229af  xor     edx, edx
0x1800229b1  mov     [rsp+48h+arg_0], rbp
0x1800229b6  lea     rcx, [rsp+48h+arg_0]
0x1800229bb  call    cs:__imp_RtlCreateHashTable
0x1800229c1  test    al, al
0x1800229c3  jnz     short loc_1800229CF
0x1800229c5  mov     ebx, 8
0x1800229ca  jmp     loc_180022A9A
0x1800229cf  lea     r8, g_NcbPolicyMaxSoftwareSlotsAllowed
0x1800229d6  xor     ecx, ecx
0x1800229d8  lea     rdx, g_NcbPolicyMaxHardwareSlotsAllowed
0x1800229df  call    cs:__imp_InternalGetRtcSlotInformation
0x1800229e5  mov     ebx, eax
0x1800229e7  test    eax, eax
0x1800229e9  jz      short loc_180022A0C
0x1800229eb  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800229f2  jz      loc_180022A91
0x1800229f8  mov     r9d, eax
0x1800229fb  lea     r8, aNcbpolicyFaile; "NcbPolicy: Failed to query RTC Slot inf"...
0x180022a02  call    McTemplateU0zq_EventWriteTransfer
0x180022a07  jmp     loc_180022A91
0x180022a0c  call    NcbPolicySubscribeToWnfEvents
0x180022a11  mov     ebx, eax
0x180022a13  test    eax, eax
0x180022a15  jz      short loc_180022A31
0x180022a17  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180022a1e  jz      short loc_180022A8C
0x180022a20  mov     r9d, eax
0x180022a23  lea     r8, aNcbpolicySubsc_1; "NcbPolicy: Subscription to WNF events f"...
0x180022a2a  call    McTemplateU0zq_EventWriteTransfer
0x180022a2f  jmp     short loc_180022A8C
0x180022a31  call    NcbPolicyPopulatePolicies
0x180022a36  mov     ebx, eax
0x180022a38  test    eax, eax
0x180022a3a  jz      short loc_180022A51
0x180022a3c  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180022a43  jz      short loc_180022A87
0x180022a45  mov     r9d, eax
0x180022a48  lea     r8, aNcbpolicyIniti; "NcbPolicy: Initialization of policy set"...
0x180022a4f  jmp     short loc_180022A82
0x180022a51  xor     r9d, r9d; lpName
0x180022a54  xor     r8d, r8d; bInitialState
0x180022a57  xor     ecx, ecx; lpEventAttributes
0x180022a59  lea     edx, [r9+1]; bManualReset
0x180022a5d  call    cs:__imp_CreateEventW
0x180022a63  mov     cs:g_NcbPolicyReferenceEvent, rax
0x180022a6a  test    rax, rax
0x180022a6d  jnz     short loc_180022AB1
0x180022a6f  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180022a76  jz      short loc_180022A87
0x180022a78  xor     r9d, r9d
0x180022a7b  lea     r8, aNcbpolicyCreat; "NcbPolicy: Creation of synchronization "...
0x180022a82  call    McTemplateU0zq_EventWriteTransfer
0x180022a87  call    NcbPolicyUnsubscribeFromWnfEvents
0x180022a8c  call    NcbPolicyCleanupPolicies
0x180022a91  mov     rcx, rbp
0x180022a94  call    cs:__imp_RtlDeleteHashTable
0x180022a9a  call    NcbCCResetUninitialize
0x180022a9f  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180022aa6  call    cs:__imp_DeleteCriticalSection
0x180022aac  jmp     loc_180022B55
0x180022ab1  lea     rax, NcbRegistrarPolicyChangeCallback
0x180022ab8  mov     ebx, 2
0x180022abd  xor     ecx, ecx
0x180022abf  mov     cs:g_NcbPolicyChangeCallback, rax
0x180022ac6  mov     cs:g_NcbPolicyReference, ebx
0x180022acc  call    NcbPolicyPolicyChangeCallback
0x180022ad1  xor     r8d, r8d
0x180022ad4  xor     edx, edx
0x180022ad6  xor     ecx, ecx
0x180022ad8  call    NcbPolicySessionChangeHandlerHelper
0x180022add  lea     rax, NcbPolicyPowerStateChangeCallback
0x180022ae4  mov     [rsp+48h+var_10], 0
0x180022aed  lea     r9, g_NcbPolicyCsNotification; RegistrationHandle
0x180022af4  mov     [rsp+48h+Recipient], rax
0x180022af9  lea     r8, [rsp+48h+Recipient]; Recipient
0x180022afe  mov     edx, ebx; Flags
0x180022b00  lea     rcx, GUID_LOW_POWER_EPOCH; SettingGuid
0x180022b07  call    cs:__imp_PowerSettingRegisterNotification
0x180022b0d  mov     ebx, eax
0x180022b0f  test    eax, eax
0x180022b11  jz      short loc_180022B3D
0x180022b13  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180022b1a  mov     cs:g_NcbPolicyCsNotification, 0
0x180022b25  jz      short loc_180022B36
0x180022b27  mov     r9d, eax
0x180022b2a  lea     r8, aNcbpolicySubsc; "NcbPolicy: Subscription to CS events fa"...
0x180022b31  call    McTemplateU0zq_EventWriteTransfer
0x180022b36  call    NcbPolicyUninitialize
0x180022b3b  jmp     short loc_180022B55
0x180022b3d  mov     [rsp+48h+var_20], 1
0x180022b42  xor     r9d, r9d
0x180022b45  xor     edx, edx
0x180022b47  mov     [rsp+48h+var_28], 1
0x180022b4c  xor     ecx, ecx
0x180022b4e  call    NcbCCResetSignal
0x180022b53  xor     ebx, ebx
0x180022b55  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180022b5c  jz      short loc_180022B6D
0x180022b5e  mov     r9d, ebx
0x180022b61  lea     r8, aNcbpolicyFinis; "NcbPolicy: Finished initialization of N"...
0x180022b68  call    McTemplateU0zq_EventWriteTransfer
0x180022b6d  mov     eax, ebx
0x180022b6f  mov     rbx, [rsp+48h+arg_8]
0x180022b74  add     rsp, 40h
0x180022b78  pop     rbp
0x180022b79  retn
```
