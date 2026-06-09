# NlmHandlerShutdown

- ea: `0x1800c4200`
- end: `0x1800c4428`
- name: `NlmHandlerShutdown`
- size: `552`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c3d24`
- `0x1800e1f2c`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x1800b99d4`
- `0x1800c4200`
- `0x1800e3da0`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800c428b`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800c428b`
- `ntdll!RtlNtStatusToDosError` at `0x1800c4299`
- `ntdll!RtlNtStatusToDosError` at `0x1800c4299`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c433b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c435e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c43bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c433b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c435e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c43bc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c4312`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c4312`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c4328`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c4328`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800c4386`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800c4386`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800c4399`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800c4399`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c4238`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c4238`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c43e4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c43e4`

## pseudocode

```c
void NlmHandlerShutdown()
{
  HRESULT v0; // eax
  struct _LIST_ENTRY *v1; // rcx
  NTSTATUS v2; // eax
  signed int v3; // eax
  bool v4; // sf
  struct _LIST_ENTRY *v5; // rcx

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 199, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
  v0 = CoInitializeEx(0, 0);
  if ( v0 >= 0 )
  {
    if ( !g_WnfSubscription )
      goto LABEL_15;
    v2 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    v3 = RtlNtStatusToDosError(v2);
    v4 = v3 < 0;
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3 | 0x80070000;
      v4 = v3 < 0;
    }
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 201, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, (unsigned int)v3);
      }
    }
    else
    {
LABEL_15:
      g_WnfSubscription = 0;
      g_CostedNetworkSettingsInitialized = 0;
      if ( g_hNotifySinkThread )
      {
        SetEvent(g_hNotifyThreadStopEvent);
        WaitForSingleObject(g_hNotifySinkThread, 0xFFFFFFFF);
        CloseHandle(g_hNotifySinkThread);
        g_hNotifySinkThread = 0;
      }
      if ( g_hNotifyThreadStopEvent )
      {
        CloseHandle(g_hNotifyThreadStopEvent);
        g_hNotifyThreadStopEvent = 0;
      }
      if ( g_tpNetworkChangeWait )
      {
        WaitForThreadpoolWaitCallbacks(g_tpNetworkChangeWait, 1);
        CloseThreadpoolWait(g_tpNetworkChangeWait);
        g_tpNetworkChangeWait = 0;
      }
      v5 = (struct _LIST_ENTRY *)g_NetworkChangeEvent;
      if ( g_NetworkChangeEvent )
      {
        CloseHandle(g_NetworkChangeEvent);
        g_NetworkChangeEvent = 0;
      }
      NlmNetworkListFree(v5);
      VpnCriticalSectionDestroy(&g_CsNlmNetwork);
    }
    CoUninitialize();
    goto LABEL_25;
  }
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 200, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, (unsigned int)v0);
LABEL_25:
    v1 = WPP_GLOBAL_Control;
  }
  g_NlmHandlerInitialized = 0;
  if ( v1 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v1[1].Blink) & 8) != 0 )
    WPP_SF_(v1[1].Flink, 202, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
}

```

## disassembly

```asm
0x1800c4200  push    rdi
0x1800c4202  sub     rsp, 20h
0x1800c4206  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c420d  lea     rdi, WPP_GLOBAL_Control
0x1800c4214  cmp     rcx, rdi
0x1800c4217  jz      short loc_1800C4234
0x1800c4219  test    byte ptr [rcx+1Ch], 8
0x1800c421d  jz      short loc_1800C4234
0x1800c421f  mov     rcx, [rcx+10h]
0x1800c4223  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800c422a  mov     edx, 0C7h
0x1800c422f  call    WPP_SF_
0x1800c4234  xor     edx, edx; dwCoInit
0x1800c4236  xor     ecx, ecx; pvReserved
0x1800c4238  call    cs:__imp_CoInitializeEx
0x1800c423f  nop     dword ptr [rax+rax+00h]
0x1800c4244  test    eax, eax
0x1800c4246  jns     short loc_1800C427F
0x1800c4248  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c424f  cmp     rcx, rdi
0x1800c4252  jz      loc_1800C43F7
0x1800c4258  test    byte ptr [rcx+1Ch], 1
0x1800c425c  jz      loc_1800C43F7
0x1800c4262  mov     rcx, [rcx+10h]
0x1800c4266  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800c426d  mov     edx, 0C8h
0x1800c4272  mov     r9d, eax
0x1800c4275  call    WPP_SF_d
0x1800c427a  jmp     loc_1800C43F0
0x1800c427f  mov     rcx, cs:?g_WnfSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_WnfSubscription
0x1800c4286  test    rcx, rcx
0x1800c4289  jz      short loc_1800C42EC
0x1800c428b  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800c4292  nop     dword ptr [rax+rax+00h]
0x1800c4297  mov     ecx, eax; Status
0x1800c4299  call    cs:__imp_RtlNtStatusToDosError
0x1800c42a0  nop     dword ptr [rax+rax+00h]
0x1800c42a5  test    eax, eax
0x1800c42a7  jle     short loc_1800C42B3
0x1800c42a9  movzx   eax, ax
0x1800c42ac  or      eax, 80070000h
0x1800c42b1  test    eax, eax
0x1800c42b3  jns     short loc_1800C42EC
0x1800c42b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c42bc  cmp     rcx, rdi
0x1800c42bf  jz      loc_1800C43E4
0x1800c42c5  test    byte ptr [rcx+1Ch], 1
0x1800c42c9  jz      loc_1800C43E4
0x1800c42cf  mov     rcx, [rcx+10h]
0x1800c42d3  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800c42da  mov     edx, 0C9h
0x1800c42df  mov     r9d, eax
0x1800c42e2  call    WPP_SF_d
0x1800c42e7  jmp     loc_1800C43E4
0x1800c42ec  cmp     cs:?g_hNotifySinkThread@@3PEAXEA, 0; void * g_hNotifySinkThread
0x1800c42f4  mov     cs:?g_WnfSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, 0; _WNF_USER_SUBSCRIPTION * g_WnfSubscription
0x1800c42ff  mov     cs:?g_CostedNetworkSettingsInitialized@@3HA, 0; int g_CostedNetworkSettingsInitialized
0x1800c4309  jz      short loc_1800C4352
0x1800c430b  mov     rcx, cs:?g_hNotifyThreadStopEvent@@3PEAXEA; hEvent
0x1800c4312  call    cs:__imp_SetEvent
0x1800c4319  nop     dword ptr [rax+rax+00h]
0x1800c431e  mov     rcx, cs:?g_hNotifySinkThread@@3PEAXEA; hHandle
0x1800c4325  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800c4328  call    cs:__imp_WaitForSingleObject
0x1800c432f  nop     dword ptr [rax+rax+00h]
0x1800c4334  mov     rcx, cs:?g_hNotifySinkThread@@3PEAXEA; hObject
0x1800c433b  call    cs:__imp_CloseHandle
0x1800c4342  nop     dword ptr [rax+rax+00h]
0x1800c4347  mov     cs:?g_hNotifySinkThread@@3PEAXEA, 0; void * g_hNotifySinkThread
0x1800c4352  mov     rcx, cs:?g_hNotifyThreadStopEvent@@3PEAXEA; hObject
0x1800c4359  test    rcx, rcx
0x1800c435c  jz      short loc_1800C4375
0x1800c435e  call    cs:__imp_CloseHandle
0x1800c4365  nop     dword ptr [rax+rax+00h]
0x1800c436a  mov     cs:?g_hNotifyThreadStopEvent@@3PEAXEA, 0; void * g_hNotifyThreadStopEvent
0x1800c4375  mov     rcx, cs:?g_tpNetworkChangeWait@@3PEAU_TP_WAIT@@EA; pwa
0x1800c437c  test    rcx, rcx
0x1800c437f  jz      short loc_1800C43B0
0x1800c4381  mov     edx, 1; fCancelPendingCallbacks
0x1800c4386  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800c438d  nop     dword ptr [rax+rax+00h]
0x1800c4392  mov     rcx, cs:?g_tpNetworkChangeWait@@3PEAU_TP_WAIT@@EA; pwa
0x1800c4399  call    cs:__imp_CloseThreadpoolWait
0x1800c43a0  nop     dword ptr [rax+rax+00h]
0x1800c43a5  mov     cs:?g_tpNetworkChangeWait@@3PEAU_TP_WAIT@@EA, 0; _TP_WAIT * g_tpNetworkChangeWait
0x1800c43b0  mov     rcx, cs:?g_NetworkChangeEvent@@3PEAXEA; hObject
0x1800c43b7  test    rcx, rcx
0x1800c43ba  jz      short loc_1800C43D3
0x1800c43bc  call    cs:__imp_CloseHandle
0x1800c43c3  nop     dword ptr [rax+rax+00h]
0x1800c43c8  mov     cs:?g_NetworkChangeEvent@@3PEAXEA, 0; void * g_NetworkChangeEvent
0x1800c43d3  call    ?NlmNetworkListFree@@YAXPEAU_LIST_ENTRY@@@Z; NlmNetworkListFree(_LIST_ENTRY *)
0x1800c43d8  lea     rcx, ?g_CsNlmNetwork@@3UVPN_CRITICAL_SECTION_@@A; lpCriticalSection
0x1800c43df  call    VpnCriticalSectionDestroy
0x1800c43e4  call    cs:__imp_CoUninitialize
0x1800c43eb  nop     dword ptr [rax+rax+00h]
0x1800c43f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c43f7  mov     cs:?g_NlmHandlerInitialized@@3HA, 0; int g_NlmHandlerInitialized
0x1800c4401  cmp     rcx, rdi
0x1800c4404  jz      short loc_1800C4421
0x1800c4406  test    byte ptr [rcx+1Ch], 8
0x1800c440a  jz      short loc_1800C4421
0x1800c440c  mov     rcx, [rcx+10h]
0x1800c4410  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800c4417  mov     edx, 0CAh
0x1800c441c  call    WPP_SF_
0x1800c4421  add     rsp, 20h
0x1800c4425  pop     rdi
0x1800c4426  retn
```
