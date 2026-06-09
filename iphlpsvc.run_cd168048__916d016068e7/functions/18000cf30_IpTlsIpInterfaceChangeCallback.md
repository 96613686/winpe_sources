# IpTlsIpInterfaceChangeCallback

- ea: `0x18000cf30`
- end: `0x18000d5b4`
- name: `IpTlsIpInterfaceChangeCallback`
- size: `1668`
- prototype: `void __stdcall(PVOID CallerContext, PMIB_IPINTERFACE_ROW Row, MIB_NOTIFICATION_TYPE NotificationType)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003ce4`
- `0x18000cf30`
- `0x18000d7b0`
- `0x18003587c`
- `0x180041020`
- `0x180041934`
- `0x180041e04`
- `0x18004b630`
- `0x18004c1c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d16e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d252`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d16e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d252`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000cfb3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d18f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000cfb3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d18f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d1fc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d1fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d1e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d23f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d1e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d23f`
- `NSI!NsiFreeTable` at `0x18000d0f3`
- `NSI!NsiFreeTable` at `0x18000d10e`
- `NSI!NsiFreeTable` at `0x18000d0f3`
- `NSI!NsiFreeTable` at `0x18000d10e`
- `NSI!NsiGetAllParameters` at `0x18000d020`
- `NSI!NsiGetAllParameters` at `0x18000d020`
- `NSI!NsiAllocateAndGetTable` at `0x18000d31c`
- `NSI!NsiAllocateAndGetTable` at `0x18000d382`
- `NSI!NsiAllocateAndGetTable` at `0x18000d31c`
- `NSI!NsiAllocateAndGetTable` at `0x18000d382`

## string_xrefs

- `0x18000d11d`: `GetInsideOutsideStatus: inside = %d`
- `0x18000d135`: `IpTlsCheckOutsideEnabledInterfaces:old state = %d; new state = %d; already configured = %d`
- `0x18000d4d4`: `IpTlsCheckOutsideEnabledInterfaces:Inside outside state changed - outside = %d`
- `0x18000d4fb`: `IpTlsCheckOutsideEnabledInterfaces:Adding outside interfaces`
- `0x18000d545`: `IpTlsCheckOutsideEnabledInterfaces:Finished adding outside interfaces`
- `0x18000d56f`: `IpTlsCheckOutsideEnabledInterfaces:removing outside interfaces`

## pseudocode

```c
void __fastcall IpTlsIpInterfaceChangeCallback(
        PVOID CallerContext,
        PMIB_IPINTERFACE_ROW Row,
        MIB_NOTIFICATION_TYPE NotificationType)
{
  bool v5; // di
  int v6; // ecx
  int v7; // edx
  LPVOID *v8; // rbx
  int v9; // r8d
  char v10; // si
  HANDLE v11; // rcx
  unsigned int v12; // ebx
  unsigned __int8 v13; // bl
  int Table; // eax
  __int64 v15; // r10
  unsigned int i; // eax
  unsigned int j; // edx
  bool v18; // al
  char v19; // bl
  unsigned __int8 v20; // di
  __int64 v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+60h] [rbp-A0h]
  unsigned int v23; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v24; // [rsp+74h] [rbp-8Ch] BYREF
  struct _FILETIME pftDueTime; // [rsp+78h] [rbp-88h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h] BYREF
  NET_LUID v27; // [rsp+88h] [rbp-78h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+98h] [rbp-68h] BYREF
  __int128 v30; // [rsp+A0h] [rbp-60h]
  __int128 v31; // [rsp+B0h] [rbp-50h]
  __int128 v32; // [rsp+C0h] [rbp-40h]
  __int128 v33; // [rsp+D0h] [rbp-30h]
  __int128 v34; // [rsp+E0h] [rbp-20h]
  __int64 v35; // [rsp+F0h] [rbp-10h]
  __int128 v36; // [rsp+100h] [rbp+0h]
  __int128 v37; // [rsp+110h] [rbp+10h]
  _BYTE v38[161]; // [rsp+120h] [rbp+20h] BYREF
  char v39; // [rsp+1C1h] [rbp+C1h]

  v27.Value = 0;
  memset_0(v38, 0, 0xF0u);
  v35 = 0;
  v36 = 0;
  v5 = 0;
  v37 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  WaitForSingleObject(g_IpTlsConfigChangeLock, 0xFFFFFFFF);
  if ( NotificationType )
  {
    v7 = g_IpTlsGlobalV6AddressCount;
  }
  else
  {
    v27.Value = (ULONG64)Row->InterfaceLuid;
    if ( (unsigned int)NsiGetAllParameters(1, &NPI_MS_IPV6_MODULEID, 7, &v27) )
    {
      v11 = g_IpTlsConfigChangeLock;
LABEL_23:
      ReleaseMutex(v11);
      return;
    }
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
      McTemplateU0qztt_EventWriteTransfer(
        v6,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_CHANGE_CALLBACK,
        Row->InterfaceIndex,
        (unsigned int)&word_180087660,
        8,
        v39);
    v7 = g_IpTlsGlobalV6AddressCount;
    v8 = (LPVOID *)g_IpTlsGlobalV6AddressList;
    v5 = g_IpTlsGlobalV6AddressCount == 0;
    if ( g_IpTlsGlobalV6AddressList != &g_IpTlsGlobalV6AddressList )
    {
      do
      {
        if ( v8[4] != (LPVOID)v27.Value )
          goto LABEL_9;
        v9 = *((unsigned __int8 *)v8 + 40);
        if ( (_BYTE)v9 == v39 )
        {
          v6 = v31 == 0;
          if ( *((unsigned __int8 *)v8 + 41) == v6 )
            goto LABEL_9;
        }
        LOBYTE(v6) = (_BYTE)v9 == 1 || *((_BYTE *)v8 + 41) == 1;
        *((_BYTE *)v8 + 40) = v39;
        v18 = (_DWORD)v31 == 0;
        *((_BYTE *)v8 + 41) = (_DWORD)v31 == 0;
        if ( *((_BYTE *)v8 + 40) || v18 )
        {
          if ( (_BYTE)v6 )
            goto LABEL_9;
          g_IpTlsGlobalV6AddressCount = --v7;
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) == 0 )
            goto LABEL_9;
        }
        else
        {
          g_IpTlsGlobalV6AddressCount = ++v7;
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) == 0 )
            goto LABEL_9;
        }
        McTemplateU0qttt_EventWriteTransfer(
          v6,
          v7,
          v9,
          (unsigned __int8)g_IpTlsInternetConnectivityPresent,
          g_IpTlsInternetConnectivityPresent,
          1);
        v7 = g_IpTlsGlobalV6AddressCount;
LABEL_9:
        v8 = (LPVOID *)*v8;
      }
      while ( v8 != &g_IpTlsGlobalV6AddressList );
    }
  }
  v10 = 0;
  if ( v7 )
  {
    if ( v5 && !g_IpTlsConfiguredForCorpConnectivity )
    {
      EventWrite0(0x10000000, L"IpTlsIpInterfaceChangeCallback:Removing automatic interfaces");
      IpTlsRemoveEligibleInterfaces(0);
LABEL_28:
      v10 = 1;
    }
  }
  else if ( !v5 && !g_IpTlsConfiguredForCorpConnectivity )
  {
    EventWrite0(0x10000000, L"IpTlsIpInterfaceChangeCallbackNo global v6 addresses. Starting automatic inerfaces");
    goto LABEL_28;
  }
  v29 = 0;
  v26 = 0;
  pftDueTime = 0;
  v28 = 0;
  v23 = 0;
  v24 = 0;
  if ( (unsigned int)NsiAllocateAndGetTable(1, &NPI_MS_IPV6_MODULEID, 7, &pftDueTime, 8, &v28, 240, 0, 0, 0, 0, &v24, 0) )
  {
    v15 = v26;
    v12 = 1;
  }
  else
  {
    LOBYTE(v22) = 0;
    Table = NsiAllocateAndGetTable(1, &NPI_MS_IPV4_MODULEID, 7, &v29, 8, &v26, 240, 0, 0, 0, 0, &v23, v22);
    v15 = v26;
    if ( Table )
    {
LABEL_39:
      v12 = 1;
    }
    else
    {
      for ( i = 0; i < v23; ++i )
      {
        if ( *(_DWORD *)(240LL * i + v26 + 168) == 1 )
          goto LABEL_39;
      }
      for ( j = 0; j < v24; ++j )
      {
        if ( *(_DWORD *)(240LL * j + v28 + 168) == 1 )
          goto LABEL_39;
      }
      v12 = 0;
    }
  }
  NsiFreeTable(v29, v15, 0, 0);
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))NsiFreeTable)(pftDueTime, v28, 0, 0);
  EventWrite0(0x800000, L"GetInsideOutsideStatus: inside = %d", v12);
  v13 = v12 ^ 1;
  LODWORD(v21) = (unsigned __int8)g_IpTlsConfiguredForOutside;
  EventWrite0(
    0x10000000,
    L"IpTlsCheckOutsideEnabledInterfaces:old state = %d; new state = %d; already configured = %d",
    (unsigned __int8)g_IpTlsIsOutside,
    v13,
    v21);
  if ( g_IpTlsIsOutside != v13 )
  {
    g_IpTlsIsOutside = v13;
    EventWrite0(0x10000000, L"IpTlsCheckOutsideEnabledInterfaces:Inside outside state changed - outside = %d", v13);
    if ( g_IpTlsIsOutside )
    {
      if ( !g_IpTlsConfiguredForOutside )
      {
        EventWrite0(0x10000000, L"IpTlsCheckOutsideEnabledInterfaces:Adding outside interfaces");
        v19 = IpTlsAddEligibleInterfaces(1, 2);
        v20 = v19 | IpTlsAddEligibleInterfaces(1, 1);
        if ( v20 | (unsigned __int8)IpTlsAddEligibleInterfaces(1, 0) )
        {
          EventWrite0(0x10000000, L"IpTlsCheckOutsideEnabledInterfaces:Finished adding outside interfaces");
          g_IpTlsConfiguredForOutside = 1;
        }
      }
    }
    else if ( g_IpTlsConfiguredForOutside )
    {
      EventWrite0(0x10000000, L"IpTlsCheckOutsideEnabledInterfaces:removing outside interfaces");
      IpTlsRemoveEligibleInterfaces(1);
      g_IpTlsConfiguredForOutside = 0;
    }
  }
  ReleaseMutex(g_IpTlsConfigChangeLock);
  if ( v10 )
  {
    WaitForSingleObject(g_IpTlsNLMNotificationLock, 0xFFFFFFFF);
    pftDueTime = (struct _FILETIME)-g_IpTlsCorpConnectivityTimeout;
    if ( g_IpTlsCorpConnectivityTimerArmed )
    {
      g_IpTlsCorpConnectivityTimerArmed = 0;
      EventWrite0(0x10000000, L"IpTlsRestartCorpConnectivityTimer: Cancelling");
      SetThreadpoolTimer(g_IpTlsCorpConnectivityTimer, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(g_IpTlsCorpConnectivityTimer, 1);
    }
    EventWrite0(0x10000000, L"IpTlsRestartCorpConnectivityTimer:Starting Corp Timer");
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
      McTemplateU0q_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_IPHTTPS_CORP_CONNECTIVITY_TIMER_STARTED,
        100000000);
    g_IpTlsCorpConnectivityTimerArmed = 1;
    SetThreadpoolTimer(g_IpTlsCorpConnectivityTimer, &pftDueTime, 0, 0);
    v11 = g_IpTlsNLMNotificationLock;
    goto LABEL_23;
  }
}

```

## disassembly

```asm
0x18000cf30  mov     [rsp-8+arg_0], rbx
0x18000cf35  mov     [rsp-8+arg_10], rsi
0x18000cf3a  push    rbp
0x18000cf3b  push    rdi
0x18000cf3c  push    r14
0x18000cf3e  lea     rbp, [rsp-120h]
0x18000cf46  sub     rsp, 220h
0x18000cf4d  mov     rax, cs:__security_cookie
0x18000cf54  xor     rax, rsp
0x18000cf57  mov     [rbp+130h+var_20], rax
0x18000cf5e  mov     ebx, r8d
0x18000cf61  lea     rcx, [rbp+130h+var_110]; void *
0x18000cf65  mov     rsi, rdx
0x18000cf68  xor     r14d, r14d
0x18000cf6b  xor     edx, edx; Val
0x18000cf6d  mov     [rbp+130h+var_1A8], r14
0x18000cf71  mov     r8d, 0F0h; Size
0x18000cf77  call    memset_0
0x18000cf7c  mov     rcx, cs:g_IpTlsConfigChangeLock; hHandle
0x18000cf83  xorps   xmm1, xmm1
0x18000cf86  xorps   xmm0, xmm0
0x18000cf89  xor     eax, eax
0x18000cf8b  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000cf90  mov     [rbp+130h+var_140], rax
0x18000cf94  movups  [rbp+130h+var_130], xmm0
0x18000cf98  xor     dil, dil
0x18000cf9b  movups  [rbp+130h+var_120], xmm0
0x18000cf9f  movups  [rbp+130h+var_190], xmm1
0x18000cfa3  movups  [rbp+130h+var_180], xmm1
0x18000cfa7  movups  [rbp+130h+var_170], xmm1
0x18000cfab  movups  [rbp+130h+var_160], xmm1
0x18000cfaf  movups  [rbp+130h+var_150], xmm1
0x18000cfb3  call    cs:__imp_WaitForSingleObject
0x18000cfba  nop     dword ptr [rax+rax+00h]
0x18000cfbf  test    ebx, ebx
0x18000cfc1  jnz     loc_18000D286
0x18000cfc7  mov     rax, [rsi+8]
0x18000cfcb  lea     r9, [rbp+130h+var_1A8]
0x18000cfcf  mov     [rsp+230h+var_1E0], 20h ; ' '
0x18000cfd7  lea     rdx, NPI_MS_IPV6_MODULEID
0x18000cfde  mov     [rbp+130h+var_1A8], rax
0x18000cfe2  mov     r8d, 7
0x18000cfe8  lea     rax, [rbp+130h+var_130]
0x18000cfec  mov     ecx, 1
0x18000cff1  mov     [rsp+230h+var_1E8], rax
0x18000cff6  lea     rax, [rbp+130h+var_190]
0x18000cffa  mov     [rsp+230h+var_1F0], 58h ; 'X'
0x18000d002  mov     [rsp+230h+var_1F8], rax
0x18000d007  lea     rax, [rbp+130h+var_110]
0x18000d00b  mov     [rsp+230h+var_200], 0F0h
0x18000d013  mov     [rsp+230h+var_208], rax
0x18000d018  mov     dword ptr [rsp+230h+var_210], 8
0x18000d020  call    cs:__imp_NsiGetAllParameters
0x18000d027  nop     dword ptr [rax+rax+00h]
0x18000d02c  test    eax, eax
0x18000d02e  jnz     loc_18000D0D7
0x18000d034  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18000d03b  jnz     loc_18000D471
0x18000d041  mov     edx, cs:g_IpTlsGlobalV6AddressCount
0x18000d047  lea     rsi, g_IpTlsGlobalV6AddressList
0x18000d04e  mov     rbx, cs:g_IpTlsGlobalV6AddressList
0x18000d055  test    edx, edx
0x18000d057  setz    dil
0x18000d05b  cmp     rbx, rsi
0x18000d05e  jz      short loc_18000D099
0x18000d060  mov     rax, [rbp+130h+var_1A8]
0x18000d064  cmp     [rbx+20h], rax
0x18000d068  jnz     short loc_18000D091
0x18000d06a  movzx   r8d, byte ptr [rbx+28h]
0x18000d06f  cmp     r8b, [rbp+130h+var_6F]
0x18000d076  jnz     loc_18000D3FB
0x18000d07c  movzx   eax, byte ptr [rbx+29h]
0x18000d080  mov     ecx, r14d
0x18000d083  cmp     dword ptr [rbp+130h+var_180], ecx
0x18000d086  setz    cl
0x18000d089  cmp     eax, ecx
0x18000d08b  jnz     loc_18000D3FB
0x18000d091  mov     rbx, [rbx]
0x18000d094  cmp     rbx, rsi
0x18000d097  jnz     short loc_18000D060
0x18000d099  xor     sil, sil
0x18000d09c  test    edx, edx
0x18000d09e  jz      loc_18000D498
0x18000d0a4  test    dil, dil
0x18000d0a7  jz      loc_18000D2AE
0x18000d0ad  cmp     cs:g_IpTlsConfiguredForCorpConnectivity, sil
0x18000d0b4  jnz     loc_18000D2AE
0x18000d0ba  lea     rdx, aIptlsipinterfa_0; "IpTlsIpInterfaceChangeCallback:Removing"...
0x18000d0c1  mov     ecx, 10000000h
0x18000d0c6  call    EventWrite0
0x18000d0cb  xor     ecx, ecx
0x18000d0cd  call    IpTlsRemoveEligibleInterfaces
0x18000d0d2  jmp     loc_18000D2AB
0x18000d0d7  mov     rcx, cs:g_IpTlsConfigChangeLock
0x18000d0de  jmp     loc_18000D252
0x18000d0e3  mov     ebx, r14d
0x18000d0e6  mov     rcx, [rbp+130h+var_198]
0x18000d0ea  xor     r9d, r9d
0x18000d0ed  xor     r8d, r8d
0x18000d0f0  mov     rdx, r10
0x18000d0f3  call    cs:__imp_NsiFreeTable
0x18000d0fa  nop     dword ptr [rax+rax+00h]
0x18000d0ff  mov     rdx, [rbp+130h+var_1A0]
0x18000d103  xor     r9d, r9d
0x18000d106  mov     rcx, qword ptr [rsp+230h+pftDueTime.dwLowDateTime]
0x18000d10b  xor     r8d, r8d
0x18000d10e  call    cs:__imp_NsiFreeTable
0x18000d115  nop     dword ptr [rax+rax+00h]
0x18000d11a  mov     r8d, ebx
0x18000d11d  lea     rdx, aGetinsideoutsi; "GetInsideOutsideStatus: inside = %d"
0x18000d124  mov     ecx, 800000h
0x18000d129  call    EventWrite0
0x18000d12e  movzx   eax, cs:g_IpTlsConfiguredForOutside
0x18000d135  lea     rdx, aIptlscheckouts_2; "IpTlsCheckOutsideEnabledInterfaces:old "...
0x18000d13c  movzx   r8d, cs:g_IpTlsIsOutside
0x18000d144  xor     bl, 1
0x18000d147  movzx   ebx, bl
0x18000d14a  mov     ecx, 10000000h
0x18000d14f  mov     r9d, ebx
0x18000d152  mov     dword ptr [rsp+230h+var_210], eax
0x18000d156  call    EventWrite0
0x18000d15b  cmp     cs:g_IpTlsIsOutside, bl
0x18000d161  jnz     loc_18000D4CB
0x18000d167  mov     rcx, cs:g_IpTlsConfigChangeLock; hMutex
0x18000d16e  call    cs:__imp_ReleaseMutex
0x18000d175  nop     dword ptr [rax+rax+00h]
0x18000d17a  test    sil, sil
0x18000d17d  jz      loc_18000D25E
0x18000d183  mov     rcx, cs:g_IpTlsNLMNotificationLock; hHandle
0x18000d18a  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000d18f  call    cs:__imp_WaitForSingleObject
0x18000d196  nop     dword ptr [rax+rax+00h]
0x18000d19b  mov     rax, cs:g_IpTlsCorpConnectivityTimeout
0x18000d1a2  neg     rax
0x18000d1a5  mov     rcx, rax
0x18000d1a8  mov     [rsp+230h+pftDueTime.dwLowDateTime], eax
0x18000d1ac  shr     rcx, 20h
0x18000d1b0  cmp     cs:g_IpTlsCorpConnectivityTimerArmed, r14b
0x18000d1b7  mov     [rsp+230h+pftDueTime.dwHighDateTime], ecx
0x18000d1bb  jz      short loc_18000D208
0x18000d1bd  lea     rdx, aIptlsrestartco_0; "IpTlsRestartCorpConnectivityTimer: Canc"...
0x18000d1c4  mov     cs:g_IpTlsCorpConnectivityTimerArmed, r14b
0x18000d1cb  mov     ecx, 10000000h
0x18000d1d0  call    EventWrite0
0x18000d1d5  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x18000d1dc  xor     r9d, r9d; msWindowLength
0x18000d1df  xor     r8d, r8d; msPeriod
0x18000d1e2  xor     edx, edx; pftDueTime
0x18000d1e4  call    cs:__imp_SetThreadpoolTimer
0x18000d1eb  nop     dword ptr [rax+rax+00h]
0x18000d1f0  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x18000d1f7  mov     edx, 1; fCancelPendingCallbacks
0x18000d1fc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d203  nop     dword ptr [rax+rax+00h]
0x18000d208  lea     rdx, aIptlsrestartco; "IpTlsRestartCorpConnectivityTimer:Start"...
0x18000d20f  mov     ecx, 10000000h
0x18000d214  call    EventWrite0
0x18000d219  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18000d220  jnz     loc_18000D596
0x18000d226  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x18000d22d  lea     rdx, [rsp+230h+pftDueTime]; pftDueTime
0x18000d232  xor     r9d, r9d; msWindowLength
0x18000d235  mov     cs:g_IpTlsCorpConnectivityTimerArmed, 1
0x18000d23c  xor     r8d, r8d; msPeriod
0x18000d23f  call    cs:__imp_SetThreadpoolTimer
0x18000d246  nop     dword ptr [rax+rax+00h]
0x18000d24b  mov     rcx, cs:g_IpTlsNLMNotificationLock; hMutex
0x18000d252  call    cs:__imp_ReleaseMutex
0x18000d259  nop     dword ptr [rax+rax+00h]
0x18000d25e  mov     rcx, [rbp+130h+var_20]
0x18000d265  xor     rcx, rsp; StackCookie
0x18000d268  call    __security_check_cookie
0x18000d26d  lea     r11, [rsp+230h+var_10]
0x18000d275  mov     rbx, [r11+20h]
0x18000d279  mov     rsi, [r11+30h]
0x18000d27d  mov     rsp, r11
0x18000d280  pop     r14
0x18000d282  pop     rdi
0x18000d283  pop     rbp
0x18000d284  retn
0x18000d286  mov     edx, cs:g_IpTlsGlobalV6AddressCount
0x18000d28c  jmp     loc_18000D099
0x18000d291  cmp     cs:g_IpTlsConfiguredForCorpConnectivity, sil
0x18000d298  jnz     short loc_18000D2AE
0x18000d29a  lea     rdx, aIptlsipinterfa; "IpTlsIpInterfaceChangeCallbackNo global"...
0x18000d2a1  mov     ecx, 10000000h
0x18000d2a6  call    EventWrite0
0x18000d2ab  mov     sil, 1
0x18000d2ae  mov     byte ptr [rsp+230h+var_1D0], r14b
0x18000d2b3  lea     rax, [rsp+230h+var_1BC]
0x18000d2b8  mov     [rsp+230h+var_1D8], rax
0x18000d2bd  lea     r9, [rsp+230h+pftDueTime]
0x18000d2c2  mov     [rsp+230h+var_1E0], r14d
0x18000d2c7  lea     rax, [rbp+130h+var_1A0]
0x18000d2cb  mov     [rsp+230h+var_1E8], r14
0x18000d2d0  lea     rdx, NPI_MS_IPV6_MODULEID
0x18000d2d7  mov     [rsp+230h+var_1F0], r14d
0x18000d2dc  mov     r8d, 7
0x18000d2e2  mov     [rsp+230h+var_1F8], r14
0x18000d2e7  mov     ecx, 1
0x18000d2ec  mov     [rsp+230h+var_200], 0F0h
0x18000d2f4  mov     [rsp+230h+var_208], rax
0x18000d2f9  mov     dword ptr [rsp+230h+var_210], 8
0x18000d301  mov     [rbp+130h+var_198], r14
0x18000d305  mov     [rbp+130h+var_1B0], r14
0x18000d309  mov     qword ptr [rsp+230h+pftDueTime.dwLowDateTime], r14
0x18000d30e  mov     [rbp+130h+var_1A0], r14
0x18000d312  mov     [rsp+230h+var_1C0], r14d
0x18000d317  mov     [rsp+230h+var_1BC], r14d
0x18000d31c  call    cs:__imp_NsiAllocateAndGetTable
0x18000d323  nop     dword ptr [rax+rax+00h]
0x18000d328  test    eax, eax
0x18000d32a  jnz     loc_18000D4BD
0x18000d330  mov     byte ptr [rsp+230h+var_1D0], r14b
0x18000d335  lea     rax, [rsp+230h+var_1C0]
0x18000d33a  mov     [rsp+230h+var_1D8], rax
0x18000d33f  lea     r9, [rbp+130h+var_198]
0x18000d343  mov     [rsp+230h+var_1E0], r14d
0x18000d348  lea     rax, [rbp+130h+var_1B0]
0x18000d34c  mov     [rsp+230h+var_1E8], r14
0x18000d351  lea     rdx, NPI_MS_IPV4_MODULEID
0x18000d358  mov     [rsp+230h+var_1F0], r14d
0x18000d35d  mov     r8d, 7
0x18000d363  mov     [rsp+230h+var_1F8], r14
0x18000d368  mov     ecx, 1
0x18000d36d  mov     [rsp+230h+var_200], 0F0h
0x18000d375  mov     [rsp+230h+var_208], rax
0x18000d37a  mov     dword ptr [rsp+230h+var_210], 8
0x18000d382  call    cs:__imp_NsiAllocateAndGetTable
0x18000d389  nop     dword ptr [rax+rax+00h]
0x18000d38e  mov     r10, [rbp+130h+var_1B0]
0x18000d392  test    eax, eax
0x18000d394  jnz     short loc_18000D3F1
0x18000d396  mov     r8d, [rsp+230h+var_1C0]
0x18000d39b  mov     eax, r14d
0x18000d39e  xchg    ax, ax
0x18000d3a0  cmp     eax, r8d
0x18000d3a3  jnb     short loc_18000D3BD
0x18000d3a5  mov     ecx, eax
0x18000d3a7  imul    rdx, rcx, 0F0h
0x18000d3ae  cmp     dword ptr [rdx+r10+0A8h], 1
0x18000d3b7  jz      short loc_18000D3F1
0x18000d3b9  inc     eax
0x18000d3bb  jmp     short loc_18000D3A0
0x18000d3bd  mov     r9, [rbp+130h+var_1A0]
0x18000d3c1  mov     edx, r14d
0x18000d3c4  mov     r8d, [rsp+230h+var_1BC]
0x18000d3c9  nop     dword ptr [rax+00000000h]
0x18000d3d0  cmp     edx, r8d
0x18000d3d3  jnb     loc_18000D0E3
0x18000d3d9  mov     eax, edx
0x18000d3db  imul    rcx, rax, 0F0h
0x18000d3e2  cmp     dword ptr [rcx+r9+0A8h], 1
0x18000d3eb  jz      short loc_18000D3F1
0x18000d3ed  inc     edx
0x18000d3ef  jmp     short loc_18000D3D0
0x18000d3f1  mov     ebx, 1
0x18000d3f6  jmp     loc_18000D0E6
0x18000d3fb  cmp     r8b, 1
0x18000d3ff  jnz     short loc_18000D467
0x18000d401  mov     cl, 1
0x18000d403  movzx   eax, [rbp+130h+var_6F]
0x18000d40a  mov     [rbx+28h], al
0x18000d40d  cmp     dword ptr [rbp+130h+var_180], r14d
0x18000d411  setz    al
0x18000d414  mov     [rbx+29h], al
0x18000d417  cmp     [rbx+28h], r14b
0x18000d41b  jnz     short loc_18000D425
0x18000d41d  test    al, al
0x18000d41f  jz      loc_18000D4A6
0x18000d425  test    cl, cl
0x18000d427  jnz     loc_18000D091
0x18000d42d  dec     edx
0x18000d42f  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18000d436  mov     cs:g_IpTlsGlobalV6AddressCount, edx
0x18000d43c  jz      loc_18000D091
0x18000d442  movzx   r9d, cs:g_IpTlsInternetConnectivityPresent
0x18000d44a  mov     dword ptr [rsp+230h+var_208], 1
0x18000d452  mov     dword ptr [rsp+230h+var_210], r9d
0x18000d457  call    McTemplateU0qttt_EventWriteTransfer
0x18000d45c  mov     edx, cs:g_IpTlsGlobalV6AddressCount
0x18000d462  jmp     loc_18000D091
0x18000d467  cmp     byte ptr [rbx+29h], 1
0x18000d46b  jz      short loc_18000D401
0x18000d46d  xor     cl, cl
0x18000d46f  jmp     short loc_18000D403
0x18000d471  movzx   eax, [rbp+130h+var_6F]
0x18000d478  lea     r9, word_180087660
0x18000d47f  mov     r8d, [rsi+10h]
0x18000d483  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_CHANGE_CALLBACK
0x18000d48a  mov     dword ptr [rsp+230h+var_208], eax
0x18000d48e  call    McTemplateU0qztt_EventWriteTransfer
0x18000d493  jmp     loc_18000D041
0x18000d498  test    dil, dil
0x18000d49b  jnz     loc_18000D2AE
0x18000d4a1  jmp     loc_18000D291
0x18000d4a6  inc     edx
0x18000d4a8  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18000d4af  mov     cs:g_IpTlsGlobalV6AddressCount, edx
0x18000d4b5  jz      loc_18000D091
  ... truncated ...
```
