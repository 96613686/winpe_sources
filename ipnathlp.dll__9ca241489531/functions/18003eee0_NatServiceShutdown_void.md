# NatServiceShutdown(void)

- ea: `0x18003eee0`
- end: `0x18003f1b5`
- name: `?NatServiceShutdown@@YAXXZ`
- size: `725`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003ee60`
- `0x18006f0cc`
- `0x180071bf0`

## callees

- `0x18000c110`
- `0x1800231bc`
- `0x18002ee44`
- `0x18002f0f8`
- `0x18003a268`
- `0x18003afa0`
- `0x18003d4bc`
- `0x18003d854`
- `0x18003eee0`
- `0x18003f1bc`
- `0x1800598f4`
- `0x180060688`
- `0x180068a74`
- `0x18006f22c`
- `0x18006f33c`
- `0x180071ac4`
- `0x180085b74`
- `0x180087a78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003efa2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f014`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f0ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003efa2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f014`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f0ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003efb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f035`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f0d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003efb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f035`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f0d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f144`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f161`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f144`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f161`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18003f062`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18003f08a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18003f062`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18003f08a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003f06f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003f097`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003f06f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003f097`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18003ef5f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18003ef5f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18003ef46`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18003ef46`

## pseudocode

```c
void NatServiceShutdown(void)
{
  int v0; // edi
  __int64 v1; // rbx
  const char *v2; // r8
  unsigned int v3; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 260, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  v0 = 0;
  v3 = 0;
  if ( ServiceStatus.dwCurrentState != 1 )
  {
    if ( WaitHandle )
    {
      UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      WaitHandle = 0;
    }
    if ( xmmword_1800A7330 )
    {
      if ( !UnregisterWait(xmmword_1800A7330) )
        GetLastError();
      xmmword_1800A7330 = 0;
    }
    DnsDisableSuffixQuery();
    V2NatStopHostedNetworkManagementAllInterfaces();
    V2NatStopDnsServerAllInterfaces();
    if ( (_BYTE)word_1800A7340 || byte_1800A7342 )
    {
      EnterCriticalSection(&NhLock);
      v1 = NhComponentMode;
      LeaveCriticalSection(&NhLock);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        if ( (unsigned int)v1 > 4 )
          v2 = "UNKNOWN";
        else
          v2 = off_180092640[v1];
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          261,
          (unsigned int)&WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
          v1,
          (__int64)v2);
      }
      EnterCriticalSection(&g_csOperationLock);
      if ( (_DWORD)v1 == 3 )
        NatHostedNetworkShutdown();
      else
        NatShutdown(1);
      LeaveCriticalSection(&g_csOperationLock);
    }
    UnRegisterAllNsiNotification();
    ICSRpcServerUninitialize();
    if ( gV2DnsGlobalsRefed == 1 )
      ClearDefaultDomainSuffix(1);
    if ( g_FirewallExceptionBackgroundWork )
    {
      WaitForThreadpoolWorkCallbacks(g_FirewallExceptionBackgroundWork, 1);
      CloseThreadpoolWork(g_FirewallExceptionBackgroundWork);
      g_FirewallExceptionBackgroundWork = 0;
    }
    if ( g_FirewallCleanupBackgroundWork )
    {
      WaitForThreadpoolWorkCallbacks(g_FirewallCleanupBackgroundWork, 1);
      CloseThreadpoolWork(g_FirewallCleanupBackgroundWork);
      g_FirewallCleanupBackgroundWork = 0;
    }
    EnterCriticalSection(&gNatMain);
    while ( (unsigned int)NatServiceControlQueuePopFront(&v3) )
    {
      if ( v3 == 129 )
        v0 = 1;
    }
    LeaveCriticalSection(&gNatMain);
    if ( !v0 )
    {
      DhcpShutdownInterfaceManagement(0);
      DnsShutdownInterfaceManagement(0);
      V2DhcpShutdownInterfaceManagement(0);
      NatServiceChangeState(1u, 0);
      hServiceStatus = 0;
    }
    NatSetInitializationState(0);
  }
  while ( (unsigned int)NatServiceControlQueuePopFront(&v3) )
    ;
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( *(&WaitHandle + 1) )
  {
    CloseHandle(*(&WaitHandle + 1));
    *(&WaitHandle + 1) = 0;
  }
  if ( *(&xmmword_1800A7330 + 1) )
  {
    CloseHandle(*(&xmmword_1800A7330 + 1));
    *(&xmmword_1800A7330 + 1) = 0;
  }
  if ( v0 )
    NatServiceReInitialize();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 262, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
}

```

## disassembly

```asm
0x18003eee0  push    rbx
0x18003eee2  push    rbp
0x18003eee3  push    rdi
0x18003eee4  push    r15
0x18003eee6  sub     rsp, 38h
0x18003eeea  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eef1  lea     r15, WPP_GLOBAL_Control
0x18003eef8  cmp     rcx, r15
0x18003eefb  jz      short loc_18003EF21
0x18003eefd  test    dword ptr [rcx+1Ch], 200h
0x18003ef04  jz      short loc_18003EF21
0x18003ef06  cmp     byte ptr [rcx+19h], 6
0x18003ef0a  jb      short loc_18003EF21
0x18003ef0c  mov     rcx, [rcx+10h]
0x18003ef10  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003ef17  mov     edx, 104h
0x18003ef1c  call    WPP_SF_
0x18003ef21  xor     edi, edi
0x18003ef23  mov     [rsp+58h+arg_0], edi
0x18003ef27  lea     ebp, [rdi+1]
0x18003ef2a  cmp     cs:ServiceStatus.dwCurrentState, ebp
0x18003ef30  jz      loc_18003F10D
0x18003ef36  mov     rcx, qword ptr cs:WaitHandle; WaitHandle
0x18003ef3d  test    rcx, rcx
0x18003ef40  jz      short loc_18003EF53
0x18003ef42  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18003ef46  call    cs:__imp_UnregisterWaitEx
0x18003ef4c  mov     qword ptr cs:WaitHandle, rdi
0x18003ef53  mov     rcx, qword ptr cs:xmmword_1800A7330; WaitHandle
0x18003ef5a  test    rcx, rcx
0x18003ef5d  jz      short loc_18003EF76
0x18003ef5f  call    cs:__imp_UnregisterWait
0x18003ef65  test    eax, eax
0x18003ef67  jnz     short loc_18003EF6F
0x18003ef69  call    cs:__imp_GetLastError
0x18003ef6f  mov     qword ptr cs:xmmword_1800A7330, rdi
0x18003ef76  call    ?DnsDisableSuffixQuery@@YAKXZ; DnsDisableSuffixQuery(void)
0x18003ef7b  call    ?V2NatStopHostedNetworkManagementAllInterfaces@@YAXXZ; V2NatStopHostedNetworkManagementAllInterfaces(void)
0x18003ef80  call    ?V2NatStopDnsServerAllInterfaces@@YAKXZ; V2NatStopDnsServerAllInterfaces(void)
0x18003ef85  cmp     byte ptr cs:word_1800A7340, dil
0x18003ef8c  jnz     short loc_18003EF9B
0x18003ef8e  cmp     cs:byte_1800A7342, dil
0x18003ef95  jz      loc_18003F03B
0x18003ef9b  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003efa2  call    cs:__imp_EnterCriticalSection
0x18003efa8  movsxd  rbx, cs:?NhComponentMode@@3W4NH_COMPONENT_MODE@@A; NH_COMPONENT_MODE NhComponentMode
0x18003efaf  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003efb6  call    cs:__imp_LeaveCriticalSection
0x18003efbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003efc3  cmp     rcx, r15
0x18003efc6  jz      short loc_18003F00D
0x18003efc8  test    dword ptr [rcx+1Ch], 200h
0x18003efcf  jz      short loc_18003F00D
0x18003efd1  cmp     byte ptr [rcx+19h], 4
0x18003efd5  jb      short loc_18003F00D
0x18003efd7  cmp     ebx, 4
0x18003efda  ja      short loc_18003EFE9
0x18003efdc  lea     r8, off_180092640; "NhUninitializedMode"
0x18003efe3  mov     r8, [r8+rbx*8]
0x18003efe7  jmp     short loc_18003EFF0
0x18003efe9  lea     r8, aUnknown; "UNKNOWN"
0x18003eff0  mov     rcx, [rcx+10h]
0x18003eff4  mov     edx, 105h
0x18003eff9  mov     [rsp+58h+var_38], r8
0x18003effe  mov     r9d, ebx
0x18003f001  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003f008  call    WPP_SF_Ds
0x18003f00d  lea     rcx, ?g_csOperationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003f014  call    cs:__imp_EnterCriticalSection
0x18003f01a  cmp     ebx, 3
0x18003f01d  jnz     short loc_18003F026
0x18003f01f  call    ?NatHostedNetworkShutdown@@YAXXZ; NatHostedNetworkShutdown(void)
0x18003f024  jmp     short loc_18003F02E
0x18003f026  mov     cl, bpl; bool
0x18003f029  call    ?NatShutdown@@YAX_N@Z; NatShutdown(bool)
0x18003f02e  lea     rcx, ?g_csOperationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003f035  call    cs:__imp_LeaveCriticalSection
0x18003f03b  call    ?UnRegisterAllNsiNotification@@YAXXZ; UnRegisterAllNsiNotification(void)
0x18003f040  call    ?ICSRpcServerUninitialize@@YAKXZ; ICSRpcServerUninitialize(void)
0x18003f045  cmp     cs:?gV2DnsGlobalsRefed@@3HA, ebp; int gV2DnsGlobalsRefed
0x18003f04b  jnz     short loc_18003F054
0x18003f04d  mov     ecx, ebp; int
0x18003f04f  call    ?ClearDefaultDomainSuffix@@YAXH@Z; ClearDefaultDomainSuffix(int)
0x18003f054  mov     rcx, cs:?g_FirewallExceptionBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18003f05b  test    rcx, rcx
0x18003f05e  jz      short loc_18003F07C
0x18003f060  mov     edx, ebp; fCancelPendingCallbacks
0x18003f062  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18003f068  mov     rcx, cs:?g_FirewallExceptionBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18003f06f  call    cs:__imp_CloseThreadpoolWork
0x18003f075  mov     cs:?g_FirewallExceptionBackgroundWork@@3PEAU_TP_WORK@@EA, rdi; _TP_WORK * g_FirewallExceptionBackgroundWork
0x18003f07c  mov     rcx, cs:?g_FirewallCleanupBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18003f083  test    rcx, rcx
0x18003f086  jz      short loc_18003F0A4
0x18003f088  mov     edx, ebp; fCancelPendingCallbacks
0x18003f08a  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18003f090  mov     rcx, cs:?g_FirewallCleanupBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18003f097  call    cs:__imp_CloseThreadpoolWork
0x18003f09d  mov     cs:?g_FirewallCleanupBackgroundWork@@3PEAU_TP_WORK@@EA, rdi; _TP_WORK * g_FirewallCleanupBackgroundWork
0x18003f0a4  lea     rcx, ?gNatMain@@3UNAT_MAIN_COMPONENT_@@A; lpCriticalSection
0x18003f0ab  call    cs:__imp_EnterCriticalSection
0x18003f0b1  jmp     short loc_18003F0BE
0x18003f0b3  cmp     [rsp+58h+arg_0], 81h
0x18003f0bb  cmovz   edi, ebp
0x18003f0be  lea     rcx, [rsp+58h+arg_0]; unsigned int *
0x18003f0c3  call    ?NatServiceControlQueuePopFront@@YAHPEAK@Z; NatServiceControlQueuePopFront(ulong *)
0x18003f0c8  test    eax, eax
0x18003f0ca  jnz     short loc_18003F0B3
0x18003f0cc  lea     rcx, ?gNatMain@@3UNAT_MAIN_COMPONENT_@@A; lpCriticalSection
0x18003f0d3  call    cs:__imp_LeaveCriticalSection
0x18003f0d9  test    edi, edi
0x18003f0db  jnz     short loc_18003F106
0x18003f0dd  xor     ecx, ecx; unsigned __int8
0x18003f0df  call    ?DhcpShutdownInterfaceManagement@@YAXE@Z; DhcpShutdownInterfaceManagement(uchar)
0x18003f0e4  xor     ecx, ecx; unsigned __int8
0x18003f0e6  call    ?DnsShutdownInterfaceManagement@@YAXE@Z; DnsShutdownInterfaceManagement(uchar)
0x18003f0eb  xor     ecx, ecx; unsigned __int8
0x18003f0ed  call    ?V2DhcpShutdownInterfaceManagement@@YAXE@Z; V2DhcpShutdownInterfaceManagement(uchar)
0x18003f0f2  xor     edx, edx; bool
0x18003f0f4  mov     ecx, ebp; unsigned int
0x18003f0f6  call    ?NatServiceChangeState@@YAJK_N@Z; NatServiceChangeState(ulong,bool)
0x18003f0fb  mov     cs:hServiceStatus, 0
0x18003f106  xor     ecx, ecx; int
0x18003f108  call    ?NatSetInitializationState@@YAHH@Z; NatSetInitializationState(int)
0x18003f10d  lea     rcx, [rsp+58h+arg_0]; unsigned int *
0x18003f112  call    ?NatServiceControlQueuePopFront@@YAHPEAK@Z; NatServiceControlQueuePopFront(ulong *)
0x18003f117  test    eax, eax
0x18003f119  jnz     short loc_18003F10D
0x18003f11b  mov     rcx, cs:hObject; hObject
0x18003f122  test    rcx, rcx
0x18003f125  jz      short loc_18003F138
0x18003f127  call    cs:__imp_CloseHandle
0x18003f12d  mov     cs:hObject, 0
0x18003f138  mov     rcx, qword ptr cs:WaitHandle+8; hObject
0x18003f13f  test    rcx, rcx
0x18003f142  jz      short loc_18003F155
0x18003f144  call    cs:__imp_CloseHandle
0x18003f14a  mov     qword ptr cs:WaitHandle+8, 0
0x18003f155  mov     rcx, qword ptr cs:xmmword_1800A7330+8; hObject
0x18003f15c  test    rcx, rcx
0x18003f15f  jz      short loc_18003F172
0x18003f161  call    cs:__imp_CloseHandle
0x18003f167  mov     qword ptr cs:xmmword_1800A7330+8, 0
0x18003f172  test    edi, edi
0x18003f174  jz      short loc_18003F17B
0x18003f176  call    ?NatServiceReInitialize@@YAXXZ; NatServiceReInitialize(void)
0x18003f17b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f182  cmp     rcx, r15
0x18003f185  jz      short loc_18003F1AB
0x18003f187  test    dword ptr [rcx+1Ch], 200h
0x18003f18e  jz      short loc_18003F1AB
0x18003f190  cmp     byte ptr [rcx+19h], 6
0x18003f194  jb      short loc_18003F1AB
0x18003f196  mov     rcx, [rcx+10h]
0x18003f19a  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003f1a1  mov     edx, 106h
0x18003f1a6  call    WPP_SF_
0x18003f1ab  add     rsp, 38h
0x18003f1af  pop     r15
0x18003f1b1  pop     rdi
0x18003f1b2  pop     rbp
0x18003f1b3  pop     rbx
0x18003f1b4  retn
```
