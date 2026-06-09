# NatServiceShutdown(void)

- ea: `0x180042360`
- end: `0x180042696`
- name: `?NatServiceShutdown@@YAXXZ`
- size: `822`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800422e0`
- `0x180074960`
- `0x180077690`

## callees

- `0x18000ca20`
- `0x180021cf0`
- `0x180021fb8`
- `0x180027b54`
- `0x18003d24c`
- `0x18003e124`
- `0x180040774`
- `0x180040bb0`
- `0x180042360`
- `0x18004269c`
- `0x18005dfc8`
- `0x180065194`
- `0x18006dca8`
- `0x180074adc`
- `0x180074c04`
- `0x180077550`
- `0x18008c5f0`
- `0x18008e63c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042434`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800424b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004256d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042434`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800424b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004256d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004244e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800424d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004259b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004244e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800424d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004259b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800423f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800423f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800425f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042618`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004263b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800425f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042618`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004263b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004250c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180042540`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004250c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180042540`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004251f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180042553`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004251f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180042553`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800423e5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800423e5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800423c6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800423c6`

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
    if ( xmmword_1800AE3F0 )
    {
      if ( !UnregisterWait(xmmword_1800AE3F0) )
        GetLastError();
      xmmword_1800AE3F0 = 0;
    }
    DnsDisableSuffixQuery();
    V2NatStopHostedNetworkManagementAllInterfaces();
    V2NatStopDnsServerAllInterfaces();
    if ( (_BYTE)word_1800AE400 || byte_1800AE402 )
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
          v2 = off_180099640[v1];
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
  if ( *(&xmmword_1800AE3F0 + 1) )
  {
    CloseHandle(*(&xmmword_1800AE3F0 + 1));
    *(&xmmword_1800AE3F0 + 1) = 0;
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
0x180042360  push    rbx
0x180042362  push    rbp
0x180042363  push    rdi
0x180042364  push    r15
0x180042366  sub     rsp, 38h
0x18004236a  mov     rcx, cs:WPP_GLOBAL_Control
0x180042371  lea     r15, WPP_GLOBAL_Control
0x180042378  cmp     rcx, r15
0x18004237b  jz      short loc_1800423A1
0x18004237d  test    dword ptr [rcx+1Ch], 200h
0x180042384  jz      short loc_1800423A1
0x180042386  cmp     byte ptr [rcx+19h], 6
0x18004238a  jb      short loc_1800423A1
0x18004238c  mov     rcx, [rcx+10h]
0x180042390  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180042397  mov     edx, 104h
0x18004239c  call    WPP_SF_
0x1800423a1  xor     edi, edi
0x1800423a3  mov     [rsp+58h+arg_0], edi
0x1800423a7  lea     ebp, [rdi+1]
0x1800423aa  cmp     cs:ServiceStatus.dwCurrentState, ebp
0x1800423b0  jz      loc_1800425DB
0x1800423b6  mov     rcx, qword ptr cs:WaitHandle; WaitHandle
0x1800423bd  test    rcx, rcx
0x1800423c0  jz      short loc_1800423D9
0x1800423c2  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800423c6  call    cs:__imp_UnregisterWaitEx
0x1800423cd  nop     dword ptr [rax+rax+00h]
0x1800423d2  mov     qword ptr cs:WaitHandle, rdi
0x1800423d9  mov     rcx, qword ptr cs:xmmword_1800AE3F0; WaitHandle
0x1800423e0  test    rcx, rcx
0x1800423e3  jz      short loc_180042408
0x1800423e5  call    cs:__imp_UnregisterWait
0x1800423ec  nop     dword ptr [rax+rax+00h]
0x1800423f1  test    eax, eax
0x1800423f3  jnz     short loc_180042401
0x1800423f5  call    cs:__imp_GetLastError
0x1800423fc  nop     dword ptr [rax+rax+00h]
0x180042401  mov     qword ptr cs:xmmword_1800AE3F0, rdi
0x180042408  call    ?DnsDisableSuffixQuery@@YAKXZ; DnsDisableSuffixQuery(void)
0x18004240d  call    ?V2NatStopHostedNetworkManagementAllInterfaces@@YAXXZ; V2NatStopHostedNetworkManagementAllInterfaces(void)
0x180042412  call    ?V2NatStopDnsServerAllInterfaces@@YAKXZ; V2NatStopDnsServerAllInterfaces(void)
0x180042417  cmp     byte ptr cs:word_1800AE400, dil
0x18004241e  jnz     short loc_18004242D
0x180042420  cmp     cs:byte_1800AE402, dil
0x180042427  jz      loc_1800424E5
0x18004242d  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180042434  call    cs:__imp_EnterCriticalSection
0x18004243b  nop     dword ptr [rax+rax+00h]
0x180042440  movsxd  rbx, cs:?NhComponentMode@@3W4NH_COMPONENT_MODE@@A; NH_COMPONENT_MODE NhComponentMode
0x180042447  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004244e  call    cs:__imp_LeaveCriticalSection
0x180042455  nop     dword ptr [rax+rax+00h]
0x18004245a  mov     rcx, cs:WPP_GLOBAL_Control
0x180042461  cmp     rcx, r15
0x180042464  jz      short loc_1800424AB
0x180042466  test    dword ptr [rcx+1Ch], 200h
0x18004246d  jz      short loc_1800424AB
0x18004246f  cmp     byte ptr [rcx+19h], 4
0x180042473  jb      short loc_1800424AB
0x180042475  cmp     ebx, 4
0x180042478  ja      short loc_180042487
0x18004247a  lea     r8, off_180099640; "NhUninitializedMode"
0x180042481  mov     r8, [r8+rbx*8]
0x180042485  jmp     short loc_18004248E
0x180042487  lea     r8, aUnknown; "UNKNOWN"
0x18004248e  mov     rcx, [rcx+10h]
0x180042492  mov     edx, 105h
0x180042497  mov     [rsp+58h+var_38], r8
0x18004249c  mov     r9d, ebx
0x18004249f  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x1800424a6  call    WPP_SF_Ds
0x1800424ab  lea     rcx, ?g_csOperationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800424b2  call    cs:__imp_EnterCriticalSection
0x1800424b9  nop     dword ptr [rax+rax+00h]
0x1800424be  cmp     ebx, 3
0x1800424c1  jnz     short loc_1800424CA
0x1800424c3  call    ?NatHostedNetworkShutdown@@YAXXZ; NatHostedNetworkShutdown(void)
0x1800424c8  jmp     short loc_1800424D2
0x1800424ca  mov     cl, bpl; bool
0x1800424cd  call    ?NatShutdown@@YAX_N@Z; NatShutdown(bool)
0x1800424d2  lea     rcx, ?g_csOperationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800424d9  call    cs:__imp_LeaveCriticalSection
0x1800424e0  nop     dword ptr [rax+rax+00h]
0x1800424e5  call    ?UnRegisterAllNsiNotification@@YAXXZ; UnRegisterAllNsiNotification(void)
0x1800424ea  call    ?ICSRpcServerUninitialize@@YAKXZ; ICSRpcServerUninitialize(void)
0x1800424ef  cmp     cs:?gV2DnsGlobalsRefed@@3HA, ebp; int gV2DnsGlobalsRefed
0x1800424f5  jnz     short loc_1800424FE
0x1800424f7  mov     ecx, ebp; int
0x1800424f9  call    ?ClearDefaultDomainSuffix@@YAXH@Z; ClearDefaultDomainSuffix(int)
0x1800424fe  mov     rcx, cs:?g_FirewallExceptionBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x180042505  test    rcx, rcx
0x180042508  jz      short loc_180042532
0x18004250a  mov     edx, ebp; fCancelPendingCallbacks
0x18004250c  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180042513  nop     dword ptr [rax+rax+00h]
0x180042518  mov     rcx, cs:?g_FirewallExceptionBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18004251f  call    cs:__imp_CloseThreadpoolWork
0x180042526  nop     dword ptr [rax+rax+00h]
0x18004252b  mov     cs:?g_FirewallExceptionBackgroundWork@@3PEAU_TP_WORK@@EA, rdi; _TP_WORK * g_FirewallExceptionBackgroundWork
0x180042532  mov     rcx, cs:?g_FirewallCleanupBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x180042539  test    rcx, rcx
0x18004253c  jz      short loc_180042566
0x18004253e  mov     edx, ebp; fCancelPendingCallbacks
0x180042540  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180042547  nop     dword ptr [rax+rax+00h]
0x18004254c  mov     rcx, cs:?g_FirewallCleanupBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x180042553  call    cs:__imp_CloseThreadpoolWork
0x18004255a  nop     dword ptr [rax+rax+00h]
0x18004255f  mov     cs:?g_FirewallCleanupBackgroundWork@@3PEAU_TP_WORK@@EA, rdi; _TP_WORK * g_FirewallCleanupBackgroundWork
0x180042566  lea     rcx, ?gNatMain@@3UNAT_MAIN_COMPONENT_@@A; lpCriticalSection
0x18004256d  call    cs:__imp_EnterCriticalSection
0x180042574  nop     dword ptr [rax+rax+00h]
0x180042579  jmp     short loc_180042586
0x18004257b  cmp     [rsp+58h+arg_0], 81h
0x180042583  cmovz   edi, ebp
0x180042586  lea     rcx, [rsp+58h+arg_0]; unsigned int *
0x18004258b  call    ?NatServiceControlQueuePopFront@@YAHPEAK@Z; NatServiceControlQueuePopFront(ulong *)
0x180042590  test    eax, eax
0x180042592  jnz     short loc_18004257B
0x180042594  lea     rcx, ?gNatMain@@3UNAT_MAIN_COMPONENT_@@A; lpCriticalSection
0x18004259b  call    cs:__imp_LeaveCriticalSection
0x1800425a2  nop     dword ptr [rax+rax+00h]
0x1800425a7  test    edi, edi
0x1800425a9  jnz     short loc_1800425D4
0x1800425ab  xor     ecx, ecx; unsigned __int8
0x1800425ad  call    ?DhcpShutdownInterfaceManagement@@YAXE@Z; DhcpShutdownInterfaceManagement(uchar)
0x1800425b2  xor     ecx, ecx; unsigned __int8
0x1800425b4  call    ?DnsShutdownInterfaceManagement@@YAXE@Z; DnsShutdownInterfaceManagement(uchar)
0x1800425b9  xor     ecx, ecx; unsigned __int8
0x1800425bb  call    ?V2DhcpShutdownInterfaceManagement@@YAXE@Z; V2DhcpShutdownInterfaceManagement(uchar)
0x1800425c0  xor     edx, edx; bool
0x1800425c2  mov     ecx, ebp; unsigned int
0x1800425c4  call    ?NatServiceChangeState@@YAJK_N@Z; NatServiceChangeState(ulong,bool)
0x1800425c9  mov     cs:hServiceStatus, 0
0x1800425d4  xor     ecx, ecx; int
0x1800425d6  call    ?NatSetInitializationState@@YAHH@Z; NatSetInitializationState(int)
0x1800425db  lea     rcx, [rsp+58h+arg_0]; unsigned int *
0x1800425e0  call    ?NatServiceControlQueuePopFront@@YAHPEAK@Z; NatServiceControlQueuePopFront(ulong *)
0x1800425e5  test    eax, eax
0x1800425e7  jnz     short loc_1800425DB
0x1800425e9  mov     rcx, cs:hObject; hObject
0x1800425f0  test    rcx, rcx
0x1800425f3  jz      short loc_18004260C
0x1800425f5  call    cs:__imp_CloseHandle
0x1800425fc  nop     dword ptr [rax+rax+00h]
0x180042601  mov     cs:hObject, 0
0x18004260c  mov     rcx, qword ptr cs:WaitHandle+8; hObject
0x180042613  test    rcx, rcx
0x180042616  jz      short loc_18004262F
0x180042618  call    cs:__imp_CloseHandle
0x18004261f  nop     dword ptr [rax+rax+00h]
0x180042624  mov     qword ptr cs:WaitHandle+8, 0
0x18004262f  mov     rcx, qword ptr cs:xmmword_1800AE3F0+8; hObject
0x180042636  test    rcx, rcx
0x180042639  jz      short loc_180042652
0x18004263b  call    cs:__imp_CloseHandle
0x180042642  nop     dword ptr [rax+rax+00h]
0x180042647  mov     qword ptr cs:xmmword_1800AE3F0+8, 0
0x180042652  test    edi, edi
0x180042654  jz      short loc_18004265B
0x180042656  call    ?NatServiceReInitialize@@YAXXZ; NatServiceReInitialize(void)
0x18004265b  mov     rcx, cs:WPP_GLOBAL_Control
0x180042662  cmp     rcx, r15
0x180042665  jz      short loc_18004268B
0x180042667  test    dword ptr [rcx+1Ch], 200h
0x18004266e  jz      short loc_18004268B
0x180042670  cmp     byte ptr [rcx+19h], 6
0x180042674  jb      short loc_18004268B
0x180042676  mov     rcx, [rcx+10h]
0x18004267a  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180042681  mov     edx, 106h
0x180042686  call    WPP_SF_
0x18004268b  add     rsp, 38h
0x18004268f  pop     r15
0x180042691  pop     rdi
0x180042692  pop     rbp
0x180042693  pop     rbx
0x180042694  retn
```
