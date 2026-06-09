# NlmHandlerInitialize

- ea: `0x1800c3d24`
- end: `0x1800c41f8`
- name: `NlmHandlerInitialize`
- size: `1236`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800e0e34`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x1800c3d24`
- `0x1800c4200`
- `0x1800e3cfc`
- `0x1800e3fac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800c3e77`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800c3e77`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800c4141`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800c4141`
- `ntdll!RtlNtStatusToDosError` at `0x1800c414f`
- `ntdll!RtlNtStatusToDosError` at `0x1800c414f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3e07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3fd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c404c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c40af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3e07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3fd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c404c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c40af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c3def`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c3f57`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c4034`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c3def`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c3f57`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c4034`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800c3fba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800c4097`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800c3fba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800c4097`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c401e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c40fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c401e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c40fb`

## string_xrefs

- `0x1800c3f3c`: `VpnCriticalSectionCreate`

## pseudocode

```c
__int64 NlmHandlerInitialize()
{
  struct _LIST_ENTRY *v0; // rcx
  signed int LastError; // eax
  unsigned int v3; // ebx
  struct _LIST_ENTRY *v4; // rcx
  __int64 v5; // rdx
  signed int v6; // eax
  int v7; // eax
  int v8; // eax
  unsigned int v9; // ecx
  __int64 v10; // r8
  signed int v11; // eax
  struct _TP_WAIT *ThreadpoolWait; // rax
  signed int v13; // eax
  signed int v14; // eax
  struct _TP_WAIT *v15; // rax
  signed int v16; // eax
  NTSTATUS v17; // eax
  signed int v18; // eax

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 188, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( g_NlmHandlerInitialized != 1 )
  {
    g_NlmNetwork.Blink = &g_NlmNetwork;
    g_NlmNetwork.Flink = &g_NlmNetwork;
    g_lpfnConnChangeHandlerCB = (void (*)(enum NLM_CONNECTIVITY))int_NLMConnNotificationHandler;
    g_lpfnCostChangeHandlerCB = (void (*)(unsigned int))int_NLMCostNotificationHandler;
    g_lpfnNetworkChangeHandler = (int (*)(struct _LIST_ENTRY *))int_NetworkChangeHandlerCallback;
    g_lpfnNetworkConnectivityChangeHandler = int_NetworkConnectivityChangeHandlerCallback;
    g_hNotifyThreadStopEvent = CreateEventW(0, 0, 0, 0);
    if ( !g_hNotifyThreadStopEvent )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v5 = 190;
LABEL_15:
        WPP_SF_d(v4[1].Flink, v5, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, v3);
        goto LABEL_65;
      }
      goto LABEL_65;
    }
    g_hNotifySinkThread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)ComThreadProc, 0, 0, &g_NotifySinkThreadId);
    if ( !g_hNotifySinkThread )
    {
      v6 = GetLastError();
      v3 = v6;
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v5 = 191;
        goto LABEL_15;
      }
LABEL_65:
      if ( (v3 & 0x80000000) == 0 )
        return 0;
LABEL_66:
      NlmHandlerShutdown();
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 198, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, v3);
      }
      if ( (v3 & 0x1FFF0000) == 0x70000 )
        return (unsigned __int16)v3;
      return v3;
    }
    v7 = VpnCriticalSectionCreate(&g_CsNlmNetwork);
    v3 = v7;
    if ( v7 >= 0
      || WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      if ( v7 >= 0 )
        goto LABEL_34;
    }
    else
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 192, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, (unsigned int)v7);
      v7 = v3;
    }
    v8 = (v7 >> 16) & 0x1FFF;
    if ( v8 == 7 )
      v9 = (unsigned __int16)v3;
    else
      v9 = v3;
    if ( v9 )
    {
      v10 = v3;
      if ( v8 == 7 )
        v10 = (unsigned __int16)v3;
      VpnReportError("NlmHandlerInitialize", "VpnCriticalSectionCreate", v10);
      goto LABEL_66;
    }
LABEL_34:
    g_NetworkChangeEvent = CreateEventW(0, 0, 0, 0);
    if ( g_NetworkChangeEvent )
    {
      ThreadpoolWait = CreateThreadpoolWait(int_NlmNetworkChangeHandler, 0, 0);
      g_tpNetworkChangeWait = ThreadpoolWait;
      if ( ThreadpoolWait )
      {
        SetThreadpoolWait(ThreadpoolWait, g_NetworkChangeEvent, 0);
        g_NetworkConnectivityChangeEvent = CreateEventW(0, 0, 0, 0);
        if ( g_NetworkConnectivityChangeEvent )
        {
          v15 = CreateThreadpoolWait(int_NlmNetworkConnectivityChangeHandler, 0, 0);
          g_tpNetworkConnectivityChangeWait = v15;
          if ( v15 )
          {
            SetThreadpoolWait(v15, g_NetworkConnectivityChangeEvent, 0);
            v17 = RtlSubscribeWnfStateChangeNotification(
                    &g_WnfSubscription,
                    WNF_ENTR_CONNECTIVITY_POLICY_VALUE_CHANGED,
                    0,
                    NlmHandlerCostPolicyUpdate,
                    0,
                    0,
                    0,
                    0);
            v18 = RtlNtStatusToDosError(v17);
            v3 = v18;
            if ( v18 > 0 )
              v3 = (unsigned __int16)v18 | 0x80070000;
            if ( (v3 & 0x80000000) != 0 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 197, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, v3);
              }
              goto LABEL_66;
            }
            g_CostedNetworkSettingsInitialized = 0;
            goto LABEL_65;
          }
          v16 = GetLastError();
          v3 = v16;
          if ( v16 > 0 )
            v3 = (unsigned __int16)v16 | 0x80070000;
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            v5 = 196;
            goto LABEL_15;
          }
        }
        else
        {
          v14 = GetLastError();
          v3 = v14;
          if ( v14 > 0 )
            v3 = (unsigned __int16)v14 | 0x80070000;
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            v5 = 195;
            goto LABEL_15;
          }
        }
      }
      else
      {
        v13 = GetLastError();
        v3 = v13;
        if ( v13 > 0 )
          v3 = (unsigned __int16)v13 | 0x80070000;
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          v5 = 194;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v11 = GetLastError();
      v3 = v11;
      if ( v11 > 0 )
        v3 = (unsigned __int16)v11 | 0x80070000;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v5 = 193;
        goto LABEL_15;
      }
    }
    goto LABEL_65;
  }
  if ( v0 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v0[1].Blink) & 8) != 0 )
    WPP_SF_(v0[1].Flink, 189, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1800c3d24  mov     [rsp+arg_0], rbx
0x1800c3d29  mov     [rsp+arg_8], rsi
0x1800c3d2e  push    r14
0x1800c3d30  sub     rsp, 40h
0x1800c3d34  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3d3b  lea     rsi, WPP_GLOBAL_Control
0x1800c3d42  lea     r14, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800c3d49  cmp     rcx, rsi
0x1800c3d4c  jz      short loc_1800C3D6C
0x1800c3d4e  test    byte ptr [rcx+1Ch], 8
0x1800c3d52  jz      short loc_1800C3D6C
0x1800c3d54  mov     rcx, [rcx+10h]
0x1800c3d58  mov     edx, 0BCh
0x1800c3d5d  mov     r8, r14
0x1800c3d60  call    WPP_SF_
0x1800c3d65  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3d6c  cmp     cs:?g_NlmHandlerInitialized@@3HA, 1; int g_NlmHandlerInitialized
0x1800c3d73  jnz     short loc_1800C3D98
0x1800c3d75  cmp     rcx, rsi
0x1800c3d78  jz      short loc_1800C3D91
0x1800c3d7a  test    byte ptr [rcx+1Ch], 8
0x1800c3d7e  jz      short loc_1800C3D91
0x1800c3d80  mov     rcx, [rcx+10h]
0x1800c3d84  mov     edx, 0BDh
0x1800c3d89  mov     r8, r14
0x1800c3d8c  call    WPP_SF_
0x1800c3d91  xor     eax, eax
0x1800c3d93  jmp     loc_1800C41E6
0x1800c3d98  lea     rax, ?g_NlmNetwork@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_NlmNetwork
0x1800c3d9f  xor     r9d, r9d; lpName
0x1800c3da2  mov     cs:?g_NlmNetwork@@3U_LIST_ENTRY@@A.Blink, rax; _LIST_ENTRY g_NlmNetwork ...
0x1800c3da9  xor     r8d, r8d; bInitialState
0x1800c3dac  mov     cs:?g_NlmNetwork@@3U_LIST_ENTRY@@A.Flink, rax; _LIST_ENTRY g_NlmNetwork ...
0x1800c3db3  xor     edx, edx; bManualReset
0x1800c3db5  lea     rax, ?int_NLMConnNotificationHandler@@YAXW4NLM_CONNECTIVITY@@@Z; int_NLMConnNotificationHandler(NLM_CONNECTIVITY)
0x1800c3dbc  xor     ecx, ecx; lpEventAttributes
0x1800c3dbe  mov     cs:?g_lpfnConnChangeHandlerCB@@3P6AXW4NLM_CONNECTIVITY@@@ZEA, rax; void (*g_lpfnConnChangeHandlerCB)(NLM_CONNECTIVITY)
0x1800c3dc5  lea     rax, ?int_NLMCostNotificationHandler@@YAXK@Z; int_NLMCostNotificationHandler(ulong)
0x1800c3dcc  mov     cs:?g_lpfnCostChangeHandlerCB@@3P6AXK@ZEA, rax; void (*g_lpfnCostChangeHandlerCB)(ulong)
0x1800c3dd3  lea     rax, ?int_NetworkChangeHandlerCallback@@YAHPEAU_LIST_ENTRY@@@Z; int_NetworkChangeHandlerCallback(_LIST_ENTRY *)
0x1800c3dda  mov     cs:?g_lpfnNetworkChangeHandler@@3P6AHPEAU_LIST_ENTRY@@@ZEA, rax; int (*g_lpfnNetworkChangeHandler)(_LIST_ENTRY *)
0x1800c3de1  lea     rax, ?int_NetworkConnectivityChangeHandlerCallback@@YAXXZ; int_NetworkConnectivityChangeHandlerCallback(void)
0x1800c3de8  mov     cs:?g_lpfnNetworkConnectivityChangeHandler@@3P6AXXZEA, rax; void (*g_lpfnNetworkConnectivityChangeHandler)(void)
0x1800c3def  call    cs:__imp_CreateEventW
0x1800c3df6  nop     dword ptr [rax+rax+00h]
0x1800c3dfb  mov     cs:?g_hNotifyThreadStopEvent@@3PEAXEA, rax; void * g_hNotifyThreadStopEvent
0x1800c3e02  test    rax, rax
0x1800c3e05  jnz     short loc_1800C3E55
0x1800c3e07  call    cs:__imp_GetLastError
0x1800c3e0e  nop     dword ptr [rax+rax+00h]
0x1800c3e13  mov     ebx, eax
0x1800c3e15  test    eax, eax
0x1800c3e17  jle     short loc_1800C3E22
0x1800c3e19  movzx   ebx, ax
0x1800c3e1c  or      ebx, 80070000h
0x1800c3e22  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3e29  cmp     rcx, rsi
0x1800c3e2c  jz      loc_1800C41A0
0x1800c3e32  test    byte ptr [rcx+1Ch], 1
0x1800c3e36  jz      loc_1800C41A0
0x1800c3e3c  mov     edx, 0BEh
0x1800c3e41  mov     rcx, [rcx+10h]
0x1800c3e45  mov     r9d, ebx
0x1800c3e48  mov     r8, r14
0x1800c3e4b  call    WPP_SF_d
0x1800c3e50  jmp     loc_1800C41A0
0x1800c3e55  lea     rax, ?g_NotifySinkThreadId@@3KA; ulong g_NotifySinkThreadId
0x1800c3e5c  xor     r9d, r9d; lpParameter
0x1800c3e5f  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800c3e64  lea     r8, ?ComThreadProc@@YAKPEAX@Z; lpStartAddress
0x1800c3e6b  xor     edx, edx; dwStackSize
0x1800c3e6d  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800c3e75  xor     ecx, ecx; lpThreadAttributes
0x1800c3e77  call    cs:__imp_CreateThread
0x1800c3e7e  nop     dword ptr [rax+rax+00h]
0x1800c3e83  mov     cs:?g_hNotifySinkThread@@3PEAXEA, rax; void * g_hNotifySinkThread
0x1800c3e8a  test    rax, rax
0x1800c3e8d  jnz     short loc_1800C3ECE
0x1800c3e8f  call    cs:__imp_GetLastError
0x1800c3e96  nop     dword ptr [rax+rax+00h]
0x1800c3e9b  mov     ebx, eax
0x1800c3e9d  test    eax, eax
0x1800c3e9f  jle     short loc_1800C3EAA
0x1800c3ea1  movzx   ebx, ax
0x1800c3ea4  or      ebx, 80070000h
0x1800c3eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3eb1  cmp     rcx, rsi
0x1800c3eb4  jz      loc_1800C41A0
0x1800c3eba  test    byte ptr [rcx+1Ch], 1
0x1800c3ebe  jz      loc_1800C41A0
0x1800c3ec4  mov     edx, 0BFh
0x1800c3ec9  jmp     loc_1800C3E41
0x1800c3ece  lea     rcx, ?g_CsNlmNetwork@@3UVPN_CRITICAL_SECTION_@@A; lpCriticalSection
0x1800c3ed5  call    VpnCriticalSectionCreate
0x1800c3eda  mov     ebx, eax
0x1800c3edc  test    eax, eax
0x1800c3ede  jns     short loc_1800C3F0A
0x1800c3ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3ee7  cmp     rcx, rsi
0x1800c3eea  jz      short loc_1800C3F0A
0x1800c3eec  test    byte ptr [rcx+1Ch], 1
0x1800c3ef0  jz      short loc_1800C3F0A
0x1800c3ef2  mov     rcx, [rcx+10h]
0x1800c3ef6  mov     edx, 0C0h
0x1800c3efb  mov     r9d, eax
0x1800c3efe  mov     r8, r14
0x1800c3f01  call    WPP_SF_d
0x1800c3f06  mov     eax, ebx
0x1800c3f08  jmp     short loc_1800C3F0E
0x1800c3f0a  test    ebx, ebx
0x1800c3f0c  jns     short loc_1800C3F4D
0x1800c3f0e  sar     eax, 10h
0x1800c3f11  and     eax, 1FFFh
0x1800c3f16  cmp     eax, 7
0x1800c3f19  jnz     short loc_1800C3F22
0x1800c3f1b  movzx   ecx, bx
0x1800c3f1e  mov     edx, ecx
0x1800c3f20  jmp     short loc_1800C3F27
0x1800c3f22  mov     ecx, ebx
0x1800c3f24  movzx   edx, bx
0x1800c3f27  test    ecx, ecx
0x1800c3f29  jz      short loc_1800C3F4D
0x1800c3f2b  cmp     eax, 7
0x1800c3f2e  lea     rcx, aNlmhandlerinit; "NlmHandlerInitialize"
0x1800c3f35  mov     r8d, ebx
0x1800c3f38  cmovz   r8d, edx
0x1800c3f3c  lea     rdx, aVpncriticalsec_4; "VpnCriticalSectionCreate"
0x1800c3f43  call    VpnReportError
0x1800c3f48  jmp     loc_1800C41A4
0x1800c3f4d  xor     r9d, r9d; lpName
0x1800c3f50  xor     r8d, r8d; bInitialState
0x1800c3f53  xor     edx, edx; bManualReset
0x1800c3f55  xor     ecx, ecx; lpEventAttributes
0x1800c3f57  call    cs:__imp_CreateEventW
0x1800c3f5e  nop     dword ptr [rax+rax+00h]
0x1800c3f63  mov     cs:?g_NetworkChangeEvent@@3PEAXEA, rax; void * g_NetworkChangeEvent
0x1800c3f6a  test    rax, rax
0x1800c3f6d  jnz     short loc_1800C3FAE
0x1800c3f6f  call    cs:__imp_GetLastError
0x1800c3f76  nop     dword ptr [rax+rax+00h]
0x1800c3f7b  mov     ebx, eax
0x1800c3f7d  test    eax, eax
0x1800c3f7f  jle     short loc_1800C3F8A
0x1800c3f81  movzx   ebx, ax
0x1800c3f84  or      ebx, 80070000h
0x1800c3f8a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3f91  cmp     rcx, rsi
0x1800c3f94  jz      loc_1800C41A0
0x1800c3f9a  test    byte ptr [rcx+1Ch], 1
0x1800c3f9e  jz      loc_1800C41A0
0x1800c3fa4  mov     edx, 0C1h
0x1800c3fa9  jmp     loc_1800C3E41
0x1800c3fae  xor     r8d, r8d; pcbe
0x1800c3fb1  lea     rcx, ?int_NlmNetworkChangeHandler@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800c3fb8  xor     edx, edx; pv
0x1800c3fba  call    cs:__imp_CreateThreadpoolWait
0x1800c3fc1  nop     dword ptr [rax+rax+00h]
0x1800c3fc6  mov     cs:?g_tpNetworkChangeWait@@3PEAU_TP_WAIT@@EA, rax; _TP_WAIT * g_tpNetworkChangeWait
0x1800c3fcd  test    rax, rax
0x1800c3fd0  jnz     short loc_1800C4011
0x1800c3fd2  call    cs:__imp_GetLastError
0x1800c3fd9  nop     dword ptr [rax+rax+00h]
0x1800c3fde  mov     ebx, eax
0x1800c3fe0  test    eax, eax
0x1800c3fe2  jle     short loc_1800C3FED
0x1800c3fe4  movzx   ebx, ax
0x1800c3fe7  or      ebx, 80070000h
0x1800c3fed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3ff4  cmp     rcx, rsi
0x1800c3ff7  jz      loc_1800C41A0
0x1800c3ffd  test    byte ptr [rcx+1Ch], 1
0x1800c4001  jz      loc_1800C41A0
0x1800c4007  mov     edx, 0C2h
0x1800c400c  jmp     loc_1800C3E41
0x1800c4011  mov     rdx, cs:?g_NetworkChangeEvent@@3PEAXEA; h
0x1800c4018  xor     r8d, r8d; pftTimeout
0x1800c401b  mov     rcx, rax; pwa
0x1800c401e  call    cs:__imp_SetThreadpoolWait
0x1800c4025  nop     dword ptr [rax+rax+00h]
0x1800c402a  xor     r9d, r9d; lpName
0x1800c402d  xor     r8d, r8d; bInitialState
0x1800c4030  xor     edx, edx; bManualReset
0x1800c4032  xor     ecx, ecx; lpEventAttributes
0x1800c4034  call    cs:__imp_CreateEventW
0x1800c403b  nop     dword ptr [rax+rax+00h]
0x1800c4040  mov     cs:?g_NetworkConnectivityChangeEvent@@3PEAXEA, rax; void * g_NetworkConnectivityChangeEvent
0x1800c4047  test    rax, rax
0x1800c404a  jnz     short loc_1800C408B
0x1800c404c  call    cs:__imp_GetLastError
0x1800c4053  nop     dword ptr [rax+rax+00h]
0x1800c4058  mov     ebx, eax
0x1800c405a  test    eax, eax
0x1800c405c  jle     short loc_1800C4067
0x1800c405e  movzx   ebx, ax
0x1800c4061  or      ebx, 80070000h
0x1800c4067  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c406e  cmp     rcx, rsi
0x1800c4071  jz      loc_1800C41A0
0x1800c4077  test    byte ptr [rcx+1Ch], 1
0x1800c407b  jz      loc_1800C41A0
0x1800c4081  mov     edx, 0C3h
0x1800c4086  jmp     loc_1800C3E41
0x1800c408b  xor     r8d, r8d; pcbe
0x1800c408e  lea     rcx, ?int_NlmNetworkConnectivityChangeHandler@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800c4095  xor     edx, edx; pv
0x1800c4097  call    cs:__imp_CreateThreadpoolWait
0x1800c409e  nop     dword ptr [rax+rax+00h]
0x1800c40a3  mov     cs:?g_tpNetworkConnectivityChangeWait@@3PEAU_TP_WAIT@@EA, rax; _TP_WAIT * g_tpNetworkConnectivityChangeWait
0x1800c40aa  test    rax, rax
0x1800c40ad  jnz     short loc_1800C40EE
0x1800c40af  call    cs:__imp_GetLastError
0x1800c40b6  nop     dword ptr [rax+rax+00h]
0x1800c40bb  mov     ebx, eax
0x1800c40bd  test    eax, eax
0x1800c40bf  jle     short loc_1800C40CA
0x1800c40c1  movzx   ebx, ax
0x1800c40c4  or      ebx, 80070000h
0x1800c40ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c40d1  cmp     rcx, rsi
0x1800c40d4  jz      loc_1800C41A0
0x1800c40da  test    byte ptr [rcx+1Ch], 1
0x1800c40de  jz      loc_1800C41A0
0x1800c40e4  mov     edx, 0C4h
0x1800c40e9  jmp     loc_1800C3E41
0x1800c40ee  mov     rdx, cs:?g_NetworkConnectivityChangeEvent@@3PEAXEA; h
0x1800c40f5  xor     r8d, r8d; pftTimeout
0x1800c40f8  mov     rcx, rax; pwa
0x1800c40fb  call    cs:__imp_SetThreadpoolWait
0x1800c4102  nop     dword ptr [rax+rax+00h]
0x1800c4107  mov     rdx, cs:WNF_ENTR_CONNECTIVITY_POLICY_VALUE_CHANGED
0x1800c410e  lea     r9, NlmHandlerCostPolicyUpdate
0x1800c4115  mov     [rsp+48h+var_10], 0
0x1800c411d  lea     rcx, ?g_WnfSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_WnfSubscription
0x1800c4124  mov     [rsp+48h+var_18], 0
0x1800c412c  xor     r8d, r8d
0x1800c412f  mov     [rsp+48h+lpThreadId], 0
0x1800c4138  mov     qword ptr [rsp+48h+dwCreationFlags], 0
0x1800c4141  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800c4148  nop     dword ptr [rax+rax+00h]
0x1800c414d  mov     ecx, eax; Status
0x1800c414f  call    cs:__imp_RtlNtStatusToDosError
0x1800c4156  nop     dword ptr [rax+rax+00h]
0x1800c415b  mov     ebx, eax
0x1800c415d  test    eax, eax
0x1800c415f  jle     short loc_1800C416A
0x1800c4161  movzx   ebx, ax
0x1800c4164  or      ebx, 80070000h
0x1800c416a  test    ebx, ebx
0x1800c416c  jns     short loc_1800C4196
0x1800c416e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4175  cmp     rcx, rsi
0x1800c4178  jz      short loc_1800C41A4
0x1800c417a  test    byte ptr [rcx+1Ch], 1
0x1800c417e  jz      short loc_1800C41A4
0x1800c4180  mov     rcx, [rcx+10h]
0x1800c4184  mov     edx, 0C5h
0x1800c4189  mov     r9d, ebx
0x1800c418c  mov     r8, r14
0x1800c418f  call    WPP_SF_d
0x1800c4194  jmp     short loc_1800C41A4
0x1800c4196  mov     cs:?g_CostedNetworkSettingsInitialized@@3HA, 0; int g_CostedNetworkSettingsInitialized
0x1800c41a0  test    ebx, ebx
0x1800c41a2  jns     short loc_1800C41E2
0x1800c41a4  call    NlmHandlerShutdown
0x1800c41a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c41b0  cmp     rcx, rsi
0x1800c41b3  jz      short loc_1800C41CF
0x1800c41b5  test    byte ptr [rcx+1Ch], 8
0x1800c41b9  jz      short loc_1800C41CF
0x1800c41bb  mov     rcx, [rcx+10h]
0x1800c41bf  mov     edx, 0C6h
0x1800c41c4  mov     r9d, ebx
0x1800c41c7  mov     r8, r14
0x1800c41ca  call    WPP_SF_d
0x1800c41cf  mov     eax, ebx
0x1800c41d1  and     eax, 1FFF0000h
0x1800c41d6  cmp     eax, 70000h
0x1800c41db  jnz     short loc_1800C41E4
0x1800c41dd  movzx   ebx, bx
0x1800c41e0  jmp     short loc_1800C41E4
0x1800c41e2  xor     ebx, ebx
0x1800c41e4  mov     eax, ebx
0x1800c41e6  mov     rbx, [rsp+48h+arg_0]
0x1800c41eb  mov     rsi, [rsp+48h+arg_8]
0x1800c41f0  add     rsp, 40h
0x1800c41f4  pop     r14
0x1800c41f6  retn
```
