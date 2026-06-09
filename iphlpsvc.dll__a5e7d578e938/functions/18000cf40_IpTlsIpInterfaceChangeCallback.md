# IpTlsIpInterfaceChangeCallback

- ea: `0x18000cf40`
- end: `0x18000d5c4`
- name: `IpTlsIpInterfaceChangeCallback`
- size: `1668`
- prototype: `void __stdcall(PVOID CallerContext, PMIB_IPINTERFACE_ROW Row, MIB_NOTIFICATION_TYPE NotificationType)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003cf4`
- `0x18000cf40`
- `0x18000d7c0`
- `0x18003588c`
- `0x180040fe0`
- `0x1800418f4`
- `0x180041dc4`
- `0x18004b5f0`
- `0x18004c188`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d17e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d262`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d17e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d262`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000cfc3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d19f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000cfc3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d19f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d20c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d20c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d1f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d24f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d1f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d24f`
- `NSI!NsiFreeTable` at `0x18000d103`
- `NSI!NsiFreeTable` at `0x18000d11e`
- `NSI!NsiFreeTable` at `0x18000d103`
- `NSI!NsiFreeTable` at `0x18000d11e`
- `NSI!NsiGetAllParameters` at `0x18000d030`
- `NSI!NsiGetAllParameters` at `0x18000d030`
- `NSI!NsiAllocateAndGetTable` at `0x18000d32c`
- `NSI!NsiAllocateAndGetTable` at `0x18000d392`
- `NSI!NsiAllocateAndGetTable` at `0x18000d32c`
- `NSI!NsiAllocateAndGetTable` at `0x18000d392`

## string_xrefs

- `0x18000d12d`: `GetInsideOutsideStatus: inside = %d`
- `0x18000d145`: `IpTlsCheckOutsideEnabledInterfaces:old state = %d; new state = %d; already configured = %d`
- `0x18000d4e4`: `IpTlsCheckOutsideEnabledInterfaces:Inside outside state changed - outside = %d`
- `0x18000d50b`: `IpTlsCheckOutsideEnabledInterfaces:Adding outside interfaces`
- `0x18000d555`: `IpTlsCheckOutsideEnabledInterfaces:Finished adding outside interfaces`
- `0x18000d57f`: `IpTlsCheckOutsideEnabledInterfaces:removing outside interfaces`

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
  int v21; // [rsp+20h] [rbp-E0h]
  __int64 v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+60h] [rbp-A0h]
  unsigned int v24; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v25; // [rsp+74h] [rbp-8Ch] BYREF
  struct _FILETIME pftDueTime; // [rsp+78h] [rbp-88h] BYREF
  __int64 v27; // [rsp+80h] [rbp-80h] BYREF
  NET_LUID v28; // [rsp+88h] [rbp-78h] BYREF
  __int64 v29; // [rsp+90h] [rbp-70h] BYREF
  __int64 v30; // [rsp+98h] [rbp-68h] BYREF
  __int128 v31; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v32; // [rsp+B0h] [rbp-50h]
  __int128 v33; // [rsp+C0h] [rbp-40h]
  __int128 v34; // [rsp+D0h] [rbp-30h]
  __int128 v35; // [rsp+E0h] [rbp-20h]
  __int64 v36; // [rsp+F0h] [rbp-10h]
  _OWORD v37[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v38[161]; // [rsp+120h] [rbp+20h] BYREF
  char v39; // [rsp+1C1h] [rbp+C1h]

  v28.Value = 0;
  memset_0(v38, 0, 0xF0u);
  v36 = 0;
  memset(v37, 0, sizeof(v37));
  v5 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  WaitForSingleObject(g_IpTlsConfigChangeLock, 0xFFFFFFFF);
  if ( NotificationType )
  {
    v7 = g_IpTlsGlobalV6AddressCount;
  }
  else
  {
    v28.Value = (ULONG64)Row->InterfaceLuid;
    if ( (unsigned int)NsiGetAllParameters(1, &NPI_MS_IPV6_MODULEID, 7, &v28, 8, v38, 240, &v31, 88, v37, 32) )
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
        v21,
        v39);
    v7 = g_IpTlsGlobalV6AddressCount;
    v8 = (LPVOID *)g_IpTlsGlobalV6AddressList;
    v5 = g_IpTlsGlobalV6AddressCount == 0;
    if ( g_IpTlsGlobalV6AddressList != &g_IpTlsGlobalV6AddressList )
    {
      do
      {
        if ( v8[4] != (LPVOID)v28.Value )
          goto LABEL_9;
        v9 = *((unsigned __int8 *)v8 + 40);
        if ( (_BYTE)v9 == v39 )
        {
          v6 = v32 == 0;
          if ( *((unsigned __int8 *)v8 + 41) == v6 )
            goto LABEL_9;
        }
        LOBYTE(v6) = (_BYTE)v9 == 1 || *((_BYTE *)v8 + 41) == 1;
        *((_BYTE *)v8 + 40) = v39;
        v18 = (_DWORD)v32 == 0;
        *((_BYTE *)v8 + 41) = (_DWORD)v32 == 0;
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
  v30 = 0;
  v27 = 0;
  pftDueTime = 0;
  v29 = 0;
  v24 = 0;
  v25 = 0;
  if ( (unsigned int)NsiAllocateAndGetTable(1, &NPI_MS_IPV6_MODULEID, 7, &pftDueTime, 8, &v29, 240, 0, 0, 0, 0, &v25, 0) )
  {
    v15 = v27;
    v12 = 1;
  }
  else
  {
    LOBYTE(v23) = 0;
    Table = NsiAllocateAndGetTable(1, &NPI_MS_IPV4_MODULEID, 7, &v30, 8, &v27, 240, 0, 0, 0, 0, &v24, v23);
    v15 = v27;
    if ( Table )
    {
LABEL_39:
      v12 = 1;
    }
    else
    {
      for ( i = 0; i < v24; ++i )
      {
        if ( *(_DWORD *)(240LL * i + v27 + 168) == 1 )
          goto LABEL_39;
      }
      for ( j = 0; j < v25; ++j )
      {
        if ( *(_DWORD *)(240LL * j + v29 + 168) == 1 )
          goto LABEL_39;
      }
      v12 = 0;
    }
  }
  NsiFreeTable(v30, v15, 0, 0);
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))NsiFreeTable)(pftDueTime, v29, 0, 0);
  EventWrite0(0x800000, L"GetInsideOutsideStatus: inside = %d", v12);
  v13 = v12 ^ 1;
  LODWORD(v22) = (unsigned __int8)g_IpTlsConfiguredForOutside;
  EventWrite0(
    0x10000000,
    L"IpTlsCheckOutsideEnabledInterfaces:old state = %d; new state = %d; already configured = %d",
    (unsigned __int8)g_IpTlsIsOutside,
    v13,
    v22);
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
0x18000cf40  mov     [rsp-8+arg_0], rbx
0x18000cf45  mov     [rsp-8+arg_10], rsi
0x18000cf4a  push    rbp
0x18000cf4b  push    rdi
0x18000cf4c  push    r14
0x18000cf4e  lea     rbp, [rsp-120h]
0x18000cf56  sub     rsp, 220h
0x18000cf5d  mov     rax, cs:__security_cookie
0x18000cf64  xor     rax, rsp
0x18000cf67  mov     [rbp+130h+var_20], rax
0x18000cf6e  mov     ebx, r8d
0x18000cf71  lea     rcx, [rbp+130h+var_110]; void *
0x18000cf75  mov     rsi, rdx
0x18000cf78  xor     r14d, r14d
0x18000cf7b  xor     edx, edx; Val
0x18000cf7d  mov     [rbp+130h+var_1A8], r14
0x18000cf81  mov     r8d, 0F0h; Size
0x18000cf87  call    memset_0
0x18000cf8c  mov     rcx, cs:g_IpTlsConfigChangeLock; hHandle
0x18000cf93  xorps   xmm1, xmm1
0x18000cf96  xorps   xmm0, xmm0
0x18000cf99  xor     eax, eax
0x18000cf9b  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000cfa0  mov     [rbp+130h+var_140], rax
0x18000cfa4  movups  [rbp+130h+var_130], xmm0
0x18000cfa8  xor     dil, dil
0x18000cfab  movups  [rbp+130h+var_120], xmm0
0x18000cfaf  movups  [rbp+130h+var_190], xmm1
0x18000cfb3  movups  [rbp+130h+var_180], xmm1
0x18000cfb7  movups  [rbp+130h+var_170], xmm1
0x18000cfbb  movups  [rbp+130h+var_160], xmm1
0x18000cfbf  movups  [rbp+130h+var_150], xmm1
0x18000cfc3  call    cs:__imp_WaitForSingleObject
0x18000cfca  nop     dword ptr [rax+rax+00h]
0x18000cfcf  test    ebx, ebx
0x18000cfd1  jnz     loc_18000D296
0x18000cfd7  mov     rax, [rsi+8]
0x18000cfdb  lea     r9, [rbp+130h+var_1A8]
0x18000cfdf  mov     [rsp+230h+var_1E0], 20h ; ' '
0x18000cfe7  lea     rdx, NPI_MS_IPV6_MODULEID
0x18000cfee  mov     [rbp+130h+var_1A8], rax
0x18000cff2  mov     r8d, 7
0x18000cff8  lea     rax, [rbp+130h+var_130]
0x18000cffc  mov     ecx, 1
0x18000d001  mov     [rsp+230h+var_1E8], rax
0x18000d006  lea     rax, [rbp+130h+var_190]
0x18000d00a  mov     [rsp+230h+var_1F0], 58h ; 'X'
0x18000d012  mov     [rsp+230h+var_1F8], rax
0x18000d017  lea     rax, [rbp+130h+var_110]
0x18000d01b  mov     [rsp+230h+var_200], 0F0h
0x18000d023  mov     [rsp+230h+var_208], rax
0x18000d028  mov     dword ptr [rsp+230h+var_210], 8
0x18000d030  call    cs:__imp_NsiGetAllParameters
0x18000d037  nop     dword ptr [rax+rax+00h]
0x18000d03c  test    eax, eax
0x18000d03e  jnz     loc_18000D0E7
0x18000d044  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18000d04b  jnz     loc_18000D481
0x18000d051  mov     edx, cs:g_IpTlsGlobalV6AddressCount
0x18000d057  lea     rsi, g_IpTlsGlobalV6AddressList
0x18000d05e  mov     rbx, cs:g_IpTlsGlobalV6AddressList
0x18000d065  test    edx, edx
0x18000d067  setz    dil
0x18000d06b  cmp     rbx, rsi
0x18000d06e  jz      short loc_18000D0A9
0x18000d070  mov     rax, [rbp+130h+var_1A8]
0x18000d074  cmp     [rbx+20h], rax
0x18000d078  jnz     short loc_18000D0A1
0x18000d07a  movzx   r8d, byte ptr [rbx+28h]
0x18000d07f  cmp     r8b, [rbp+130h+var_6F]
0x18000d086  jnz     loc_18000D40B
0x18000d08c  movzx   eax, byte ptr [rbx+29h]
0x18000d090  mov     ecx, r14d
0x18000d093  cmp     dword ptr [rbp+130h+var_180], ecx
0x18000d096  setz    cl
0x18000d099  cmp     eax, ecx
0x18000d09b  jnz     loc_18000D40B
0x18000d0a1  mov     rbx, [rbx]
0x18000d0a4  cmp     rbx, rsi
0x18000d0a7  jnz     short loc_18000D070
0x18000d0a9  xor     sil, sil
0x18000d0ac  test    edx, edx
0x18000d0ae  jz      loc_18000D4A8
0x18000d0b4  test    dil, dil
0x18000d0b7  jz      loc_18000D2BE
0x18000d0bd  cmp     cs:g_IpTlsConfiguredForCorpConnectivity, sil
0x18000d0c4  jnz     loc_18000D2BE
0x18000d0ca  lea     rdx, aIptlsipinterfa_0; "IpTlsIpInterfaceChangeCallback:Removing"...
0x18000d0d1  mov     ecx, 10000000h
0x18000d0d6  call    EventWrite0
0x18000d0db  xor     ecx, ecx
0x18000d0dd  call    IpTlsRemoveEligibleInterfaces
0x18000d0e2  jmp     loc_18000D2BB
0x18000d0e7  mov     rcx, cs:g_IpTlsConfigChangeLock
0x18000d0ee  jmp     loc_18000D262
0x18000d0f3  mov     ebx, r14d
0x18000d0f6  mov     rcx, [rbp+130h+var_198]
0x18000d0fa  xor     r9d, r9d
0x18000d0fd  xor     r8d, r8d
0x18000d100  mov     rdx, r10
0x18000d103  call    cs:__imp_NsiFreeTable
0x18000d10a  nop     dword ptr [rax+rax+00h]
0x18000d10f  mov     rdx, [rbp+130h+var_1A0]
0x18000d113  xor     r9d, r9d
0x18000d116  mov     rcx, qword ptr [rsp+230h+pftDueTime.dwLowDateTime]
0x18000d11b  xor     r8d, r8d
0x18000d11e  call    cs:__imp_NsiFreeTable
0x18000d125  nop     dword ptr [rax+rax+00h]
0x18000d12a  mov     r8d, ebx
0x18000d12d  lea     rdx, aGetinsideoutsi; "GetInsideOutsideStatus: inside = %d"
0x18000d134  mov     ecx, 800000h
0x18000d139  call    EventWrite0
0x18000d13e  movzx   eax, cs:g_IpTlsConfiguredForOutside
0x18000d145  lea     rdx, aIptlscheckouts_2; "IpTlsCheckOutsideEnabledInterfaces:old "...
0x18000d14c  movzx   r8d, cs:g_IpTlsIsOutside
0x18000d154  xor     bl, 1
0x18000d157  movzx   ebx, bl
0x18000d15a  mov     ecx, 10000000h
0x18000d15f  mov     r9d, ebx
0x18000d162  mov     dword ptr [rsp+230h+var_210], eax
0x18000d166  call    EventWrite0
0x18000d16b  cmp     cs:g_IpTlsIsOutside, bl
0x18000d171  jnz     loc_18000D4DB
0x18000d177  mov     rcx, cs:g_IpTlsConfigChangeLock; hMutex
0x18000d17e  call    cs:__imp_ReleaseMutex
0x18000d185  nop     dword ptr [rax+rax+00h]
0x18000d18a  test    sil, sil
0x18000d18d  jz      loc_18000D26E
0x18000d193  mov     rcx, cs:g_IpTlsNLMNotificationLock; hHandle
0x18000d19a  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000d19f  call    cs:__imp_WaitForSingleObject
0x18000d1a6  nop     dword ptr [rax+rax+00h]
0x18000d1ab  mov     rax, cs:g_IpTlsCorpConnectivityTimeout
0x18000d1b2  neg     rax
0x18000d1b5  mov     rcx, rax
0x18000d1b8  mov     [rsp+230h+pftDueTime.dwLowDateTime], eax
0x18000d1bc  shr     rcx, 20h
0x18000d1c0  cmp     cs:g_IpTlsCorpConnectivityTimerArmed, r14b
0x18000d1c7  mov     [rsp+230h+pftDueTime.dwHighDateTime], ecx
0x18000d1cb  jz      short loc_18000D218
0x18000d1cd  lea     rdx, aIptlsrestartco_0; "IpTlsRestartCorpConnectivityTimer: Canc"...
0x18000d1d4  mov     cs:g_IpTlsCorpConnectivityTimerArmed, r14b
0x18000d1db  mov     ecx, 10000000h
0x18000d1e0  call    EventWrite0
0x18000d1e5  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x18000d1ec  xor     r9d, r9d; msWindowLength
0x18000d1ef  xor     r8d, r8d; msPeriod
0x18000d1f2  xor     edx, edx; pftDueTime
0x18000d1f4  call    cs:__imp_SetThreadpoolTimer
0x18000d1fb  nop     dword ptr [rax+rax+00h]
0x18000d200  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x18000d207  mov     edx, 1; fCancelPendingCallbacks
0x18000d20c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d213  nop     dword ptr [rax+rax+00h]
0x18000d218  lea     rdx, aIptlsrestartco; "IpTlsRestartCorpConnectivityTimer:Start"...
0x18000d21f  mov     ecx, 10000000h
0x18000d224  call    EventWrite0
0x18000d229  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18000d230  jnz     loc_18000D5A6
0x18000d236  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x18000d23d  lea     rdx, [rsp+230h+pftDueTime]; pftDueTime
0x18000d242  xor     r9d, r9d; msWindowLength
0x18000d245  mov     cs:g_IpTlsCorpConnectivityTimerArmed, 1
0x18000d24c  xor     r8d, r8d; msPeriod
0x18000d24f  call    cs:__imp_SetThreadpoolTimer
0x18000d256  nop     dword ptr [rax+rax+00h]
0x18000d25b  mov     rcx, cs:g_IpTlsNLMNotificationLock; hMutex
0x18000d262  call    cs:__imp_ReleaseMutex
0x18000d269  nop     dword ptr [rax+rax+00h]
0x18000d26e  mov     rcx, [rbp+130h+var_20]
0x18000d275  xor     rcx, rsp; StackCookie
0x18000d278  call    __security_check_cookie
0x18000d27d  lea     r11, [rsp+230h+var_10]
0x18000d285  mov     rbx, [r11+20h]
0x18000d289  mov     rsi, [r11+30h]
0x18000d28d  mov     rsp, r11
0x18000d290  pop     r14
0x18000d292  pop     rdi
0x18000d293  pop     rbp
0x18000d294  retn
0x18000d296  mov     edx, cs:g_IpTlsGlobalV6AddressCount
0x18000d29c  jmp     loc_18000D0A9
0x18000d2a1  cmp     cs:g_IpTlsConfiguredForCorpConnectivity, sil
0x18000d2a8  jnz     short loc_18000D2BE
0x18000d2aa  lea     rdx, aIptlsipinterfa; "IpTlsIpInterfaceChangeCallbackNo global"...
0x18000d2b1  mov     ecx, 10000000h
0x18000d2b6  call    EventWrite0
0x18000d2bb  mov     sil, 1
0x18000d2be  mov     byte ptr [rsp+230h+var_1D0], r14b
0x18000d2c3  lea     rax, [rsp+230h+var_1BC]
0x18000d2c8  mov     [rsp+230h+var_1D8], rax
0x18000d2cd  lea     r9, [rsp+230h+pftDueTime]
0x18000d2d2  mov     [rsp+230h+var_1E0], r14d
0x18000d2d7  lea     rax, [rbp+130h+var_1A0]
0x18000d2db  mov     [rsp+230h+var_1E8], r14
0x18000d2e0  lea     rdx, NPI_MS_IPV6_MODULEID
0x18000d2e7  mov     [rsp+230h+var_1F0], r14d
0x18000d2ec  mov     r8d, 7
0x18000d2f2  mov     [rsp+230h+var_1F8], r14
0x18000d2f7  mov     ecx, 1
0x18000d2fc  mov     [rsp+230h+var_200], 0F0h
0x18000d304  mov     [rsp+230h+var_208], rax
0x18000d309  mov     dword ptr [rsp+230h+var_210], 8
0x18000d311  mov     [rbp+130h+var_198], r14
0x18000d315  mov     [rbp+130h+var_1B0], r14
0x18000d319  mov     qword ptr [rsp+230h+pftDueTime.dwLowDateTime], r14
0x18000d31e  mov     [rbp+130h+var_1A0], r14
0x18000d322  mov     [rsp+230h+var_1C0], r14d
0x18000d327  mov     [rsp+230h+var_1BC], r14d
0x18000d32c  call    cs:__imp_NsiAllocateAndGetTable
0x18000d333  nop     dword ptr [rax+rax+00h]
0x18000d338  test    eax, eax
0x18000d33a  jnz     loc_18000D4CD
0x18000d340  mov     byte ptr [rsp+230h+var_1D0], r14b
0x18000d345  lea     rax, [rsp+230h+var_1C0]
0x18000d34a  mov     [rsp+230h+var_1D8], rax
0x18000d34f  lea     r9, [rbp+130h+var_198]
0x18000d353  mov     [rsp+230h+var_1E0], r14d
0x18000d358  lea     rax, [rbp+130h+var_1B0]
0x18000d35c  mov     [rsp+230h+var_1E8], r14
0x18000d361  lea     rdx, NPI_MS_IPV4_MODULEID
0x18000d368  mov     [rsp+230h+var_1F0], r14d
0x18000d36d  mov     r8d, 7
0x18000d373  mov     [rsp+230h+var_1F8], r14
0x18000d378  mov     ecx, 1
0x18000d37d  mov     [rsp+230h+var_200], 0F0h
0x18000d385  mov     [rsp+230h+var_208], rax
0x18000d38a  mov     dword ptr [rsp+230h+var_210], 8
0x18000d392  call    cs:__imp_NsiAllocateAndGetTable
0x18000d399  nop     dword ptr [rax+rax+00h]
0x18000d39e  mov     r10, [rbp+130h+var_1B0]
0x18000d3a2  test    eax, eax
0x18000d3a4  jnz     short loc_18000D401
0x18000d3a6  mov     r8d, [rsp+230h+var_1C0]
0x18000d3ab  mov     eax, r14d
0x18000d3ae  xchg    ax, ax
0x18000d3b0  cmp     eax, r8d
0x18000d3b3  jnb     short loc_18000D3CD
0x18000d3b5  mov     ecx, eax
0x18000d3b7  imul    rdx, rcx, 0F0h
0x18000d3be  cmp     dword ptr [rdx+r10+0A8h], 1
0x18000d3c7  jz      short loc_18000D401
0x18000d3c9  inc     eax
0x18000d3cb  jmp     short loc_18000D3B0
0x18000d3cd  mov     r9, [rbp+130h+var_1A0]
0x18000d3d1  mov     edx, r14d
0x18000d3d4  mov     r8d, [rsp+230h+var_1BC]
0x18000d3d9  nop     dword ptr [rax+00000000h]
0x18000d3e0  cmp     edx, r8d
0x18000d3e3  jnb     loc_18000D0F3
0x18000d3e9  mov     eax, edx
0x18000d3eb  imul    rcx, rax, 0F0h
0x18000d3f2  cmp     dword ptr [rcx+r9+0A8h], 1
0x18000d3fb  jz      short loc_18000D401
0x18000d3fd  inc     edx
0x18000d3ff  jmp     short loc_18000D3E0
0x18000d401  mov     ebx, 1
0x18000d406  jmp     loc_18000D0F6
0x18000d40b  cmp     r8b, 1
0x18000d40f  jnz     short loc_18000D477
0x18000d411  mov     cl, 1
0x18000d413  movzx   eax, [rbp+130h+var_6F]
0x18000d41a  mov     [rbx+28h], al
0x18000d41d  cmp     dword ptr [rbp+130h+var_180], r14d
0x18000d421  setz    al
0x18000d424  mov     [rbx+29h], al
0x18000d427  cmp     [rbx+28h], r14b
0x18000d42b  jnz     short loc_18000D435
0x18000d42d  test    al, al
0x18000d42f  jz      loc_18000D4B6
0x18000d435  test    cl, cl
0x18000d437  jnz     loc_18000D0A1
0x18000d43d  dec     edx
0x18000d43f  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18000d446  mov     cs:g_IpTlsGlobalV6AddressCount, edx
0x18000d44c  jz      loc_18000D0A1
0x18000d452  movzx   r9d, cs:g_IpTlsInternetConnectivityPresent
0x18000d45a  mov     dword ptr [rsp+230h+var_208], 1
0x18000d462  mov     dword ptr [rsp+230h+var_210], r9d
0x18000d467  call    McTemplateU0qttt_EventWriteTransfer
0x18000d46c  mov     edx, cs:g_IpTlsGlobalV6AddressCount
0x18000d472  jmp     loc_18000D0A1
0x18000d477  cmp     byte ptr [rbx+29h], 1
0x18000d47b  jz      short loc_18000D411
0x18000d47d  xor     cl, cl
0x18000d47f  jmp     short loc_18000D413
0x18000d481  movzx   eax, [rbp+130h+var_6F]
0x18000d488  lea     r9, word_180087660
0x18000d48f  mov     r8d, [rsi+10h]
0x18000d493  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_CHANGE_CALLBACK
0x18000d49a  mov     dword ptr [rsp+230h+var_208], eax
0x18000d49e  call    McTemplateU0qztt_EventWriteTransfer
0x18000d4a3  jmp     loc_18000D051
0x18000d4a8  test    dil, dil
0x18000d4ab  jnz     loc_18000D2BE
0x18000d4b1  jmp     loc_18000D2A1
0x18000d4b6  inc     edx
0x18000d4b8  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18000d4bf  mov     cs:g_IpTlsGlobalV6AddressCount, edx
0x18000d4c5  jz      loc_18000D0A1
  ... truncated ...
```
