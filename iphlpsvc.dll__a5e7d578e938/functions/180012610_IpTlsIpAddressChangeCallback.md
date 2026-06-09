# IpTlsIpAddressChangeCallback

- ea: `0x180012610`
- end: `0x18001299f`
- name: `IpTlsIpAddressChangeCallback`
- size: `911`
- prototype: `void __stdcall(PVOID CallerContext, PMIB_UNICASTIPADDRESS_ROW Row, MIB_NOTIFICATION_TYPE NotificationType)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000d7c0`
- `0x180011a70`
- `0x180012610`
- `0x18003588c`
- `0x180040fe0`
- `0x18004b5f0`
- `0x1800662ec`

## import_xrefs

- `IPHLPAPI!GetUnicastIpAddressEntry` at `0x180012894`
- `IPHLPAPI!GetUnicastIpAddressEntry` at `0x180012894`
- `IPHLPAPI!FreeMibTable` at `0x180012942`
- `IPHLPAPI!FreeMibTable` at `0x180012942`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x1800128f5`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x1800128f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800126b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012725`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001275e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012841`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800126b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012725`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001275e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012841`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012670`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012688`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001277e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012670`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012688`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001277e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800127eb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800127eb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800127d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001282e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800127d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001282e`

## pseudocode

```c
void __fastcall IpTlsIpAddressChangeCallback(
        PVOID CallerContext,
        PMIB_UNICASTIPADDRESS_ROW Row,
        unsigned int NotificationType)
{
  char v5; // bl
  __int64 i; // rsi
  bool v7; // si
  SOCKADDR_IN Ipv4; // xmm0
  __int128 v9; // xmm1
  PMIB_UNICASTIPADDRESS_TABLE v10; // rdx
  __int64 j; // rbp
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+20h] [rbp-88h] BYREF
  struct _FILETIME pftDueTime; // [rsp+28h] [rbp-80h] BYREF
  _MIB_UNICASTIPADDRESS_ROW Rowa; // [rsp+30h] [rbp-78h] BYREF

  Table = 0;
  memset(&Rowa, 0, sizeof(Rowa));
  v5 = 0;
  WaitForSingleObject(g_IpTlsConfigChangeLock, 0xFFFFFFFF);
  WaitForSingleObject(g_IpTlsInterfaceListLock, 0xFFFFFFFF);
  for ( i = g_IpTlsInterfaceListHead; (__int64 *)i != &g_IpTlsInterfaceListHead; i = *(_QWORD *)i )
  {
    if ( *(_DWORD *)(i + 1012) )
      IpTlsServerIpChangeCallback(*(_QWORD *)(i + 1104), Row, NotificationType);
  }
  ReleaseMutex(g_IpTlsInterfaceListLock);
  v7 = g_IpTlsGlobalV6AddressCount == 0;
  if ( NotificationType == 1 )
  {
    Ipv4 = Row->Address.Ipv4;
    v9 = *(_OWORD *)(&Row->Address.si_family + 6);
    Rowa.InterfaceIndex = Row->InterfaceIndex;
    Rowa.Address.Ipv4 = Ipv4;
    *(_OWORD *)(&Rowa.Address.si_family + 6) = v9;
    if ( !GetUnicastIpAddressEntry(&Rowa) )
      IpTlsUpdateGlobalUsableIpv6AddressCount(&Rowa, 1);
  }
  else if ( NotificationType == 2 )
  {
    IpTlsUpdateGlobalUsableIpv6AddressCount(Row, 2);
  }
  else if ( NotificationType == 3 && !GetUnicastIpAddressTable(0x17u, &Table) )
  {
    v10 = Table;
    for ( j = 0; (unsigned int)j < Table->NumEntries; j = (unsigned int)(j + 1) )
    {
      IpTlsUpdateGlobalUsableIpv6AddressCount(&v10->Table[j], 1);
      v10 = Table;
    }
    FreeMibTable(v10);
  }
  if ( !g_IpTlsGlobalV6AddressCount
    && (v7 && NotificationType != 3
     || g_IpTlsConfiguredForCorpConnectivity
     || (EventWrite0(0x10000000, L"IpTlsIpAddressChangeCallbackNo global v6 addresses. Starting automatic inerfaces"),
         v5 = 1,
         !g_IpTlsGlobalV6AddressCount))
    || !v7
    || g_IpTlsConfiguredForCorpConnectivity
    || NotificationType == 3 )
  {
    ReleaseMutex(g_IpTlsConfigChangeLock);
    if ( !v5 )
      return;
  }
  else
  {
    EventWrite0(0x10000000, L"IpTlsIpAddressChangeCallback:Removing automatic interfaces");
    IpTlsRemoveEligibleInterfaces(0);
    ReleaseMutex(g_IpTlsConfigChangeLock);
  }
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
  ReleaseMutex(g_IpTlsNLMNotificationLock);
}

```

## disassembly

```asm
0x180012610  mov     [rsp+arg_0], rbx
0x180012615  mov     [rsp+arg_10], rbp
0x18001261a  push    rsi
0x18001261b  push    rdi
0x18001261c  push    r14
0x18001261e  sub     rsp, 90h
0x180012625  mov     rax, cs:__security_cookie
0x18001262c  xor     rax, rsp
0x18001262f  mov     [rsp+0A8h+var_28], rax
0x180012637  mov     rcx, cs:g_IpTlsConfigChangeLock; hHandle
0x18001263e  xorps   xmm0, xmm0
0x180012641  mov     rbp, rdx
0x180012644  mov     [rsp+0A8h+Table], 0
0x18001264d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180012652  mov     edi, r8d
0x180012655  movups  xmmword ptr [rsp+0A8h+Row.Address], xmm0
0x18001265a  xor     bl, bl
0x18001265c  movups  xmmword ptr [rsp+0A8h+Row.Address+10h], xmm0
0x180012661  movups  xmmword ptr [rsp+0A8h+Row.InterfaceLuid], xmm0
0x180012666  movups  xmmword ptr [rsp+0A8h+Row.SuffixOrigin], xmm0
0x18001266b  movups  xmmword ptr [rsp+0A8h+Row.DadState], xmm0
0x180012670  call    cs:__imp_WaitForSingleObject
0x180012677  nop     dword ptr [rax+rax+00h]
0x18001267c  mov     rcx, cs:g_IpTlsInterfaceListLock; hHandle
0x180012683  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180012688  call    cs:__imp_WaitForSingleObject
0x18001268f  nop     dword ptr [rax+rax+00h]
0x180012694  mov     rsi, cs:g_IpTlsInterfaceListHead
0x18001269b  lea     r14, g_IpTlsInterfaceListHead
0x1800126a2  cmp     rsi, r14
0x1800126a5  jnz     loc_1800128D0
0x1800126ab  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x1800126b2  call    cs:__imp_ReleaseMutex
0x1800126b9  nop     dword ptr [rax+rax+00h]
0x1800126be  cmp     cs:g_IpTlsGlobalV6AddressCount, 0
0x1800126c5  mov     eax, edi
0x1800126c7  setz    sil
0x1800126cb  sub     eax, 1
0x1800126ce  jz      loc_180012876
0x1800126d4  sub     eax, 1
0x1800126d7  jz      loc_1800128BC
0x1800126dd  cmp     eax, 1
0x1800126e0  jz      loc_1800128EB
0x1800126e6  cmp     cs:g_IpTlsGlobalV6AddressCount, 0
0x1800126ed  jz      loc_180012953
0x1800126f3  test    sil, sil
0x1800126f6  jz      short loc_180012757
0x1800126f8  cmp     cs:g_IpTlsConfiguredForCorpConnectivity, 0
0x1800126ff  jnz     short loc_180012757
0x180012701  cmp     edi, 3
0x180012704  jz      short loc_180012757
0x180012706  lea     rdx, aIptlsipaddress; "IpTlsIpAddressChangeCallback:Removing a"...
0x18001270d  mov     ecx, 10000000h
0x180012712  call    EventWrite0
0x180012717  xor     ecx, ecx
0x180012719  call    IpTlsRemoveEligibleInterfaces
0x18001271e  mov     rcx, cs:g_IpTlsConfigChangeLock; hMutex
0x180012725  call    cs:__imp_ReleaseMutex
0x18001272c  nop     dword ptr [rax+rax+00h]
0x180012731  jmp     short loc_180012772
0x180012733  cmp     cs:g_IpTlsConfiguredForCorpConnectivity, bl
0x180012739  jnz     short loc_180012757
0x18001273b  lea     rdx, aIptlsipaddress_0; "IpTlsIpAddressChangeCallbackNo global v"...
0x180012742  mov     ecx, 10000000h
0x180012747  call    EventWrite0
0x18001274c  cmp     cs:g_IpTlsGlobalV6AddressCount, 0
0x180012753  mov     bl, 1
0x180012755  jnz     short loc_1800126F3
0x180012757  mov     rcx, cs:g_IpTlsConfigChangeLock; hMutex
0x18001275e  call    cs:__imp_ReleaseMutex
0x180012765  nop     dword ptr [rax+rax+00h]
0x18001276a  test    bl, bl
0x18001276c  jz      loc_18001284D
0x180012772  mov     rcx, cs:g_IpTlsNLMNotificationLock; hHandle
0x180012779  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18001277e  call    cs:__imp_WaitForSingleObject
0x180012785  nop     dword ptr [rax+rax+00h]
0x18001278a  mov     rax, cs:g_IpTlsCorpConnectivityTimeout
0x180012791  neg     rax
0x180012794  mov     rcx, rax
0x180012797  mov     [rsp+0A8h+pftDueTime.dwLowDateTime], eax
0x18001279b  shr     rcx, 20h
0x18001279f  cmp     cs:g_IpTlsCorpConnectivityTimerArmed, 0
0x1800127a6  mov     [rsp+0A8h+pftDueTime.dwHighDateTime], ecx
0x1800127aa  jz      short loc_1800127F7
0x1800127ac  lea     rdx, aIptlsrestartco_0; "IpTlsRestartCorpConnectivityTimer: Canc"...
0x1800127b3  mov     cs:g_IpTlsCorpConnectivityTimerArmed, 0
0x1800127ba  mov     ecx, 10000000h
0x1800127bf  call    EventWrite0
0x1800127c4  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x1800127cb  xor     r9d, r9d; msWindowLength
0x1800127ce  xor     r8d, r8d; msPeriod
0x1800127d1  xor     edx, edx; pftDueTime
0x1800127d3  call    cs:__imp_SetThreadpoolTimer
0x1800127da  nop     dword ptr [rax+rax+00h]
0x1800127df  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x1800127e6  mov     edx, 1; fCancelPendingCallbacks
0x1800127eb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800127f2  nop     dword ptr [rax+rax+00h]
0x1800127f7  lea     rdx, aIptlsrestartco; "IpTlsRestartCorpConnectivityTimer:Start"...
0x1800127fe  mov     ecx, 10000000h
0x180012803  call    EventWrite0
0x180012808  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18001280f  jnz     loc_180012981
0x180012815  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x18001281c  lea     rdx, [rsp+0A8h+pftDueTime]; pftDueTime
0x180012821  xor     r9d, r9d; msWindowLength
0x180012824  mov     cs:g_IpTlsCorpConnectivityTimerArmed, 1
0x18001282b  xor     r8d, r8d; msPeriod
0x18001282e  call    cs:__imp_SetThreadpoolTimer
0x180012835  nop     dword ptr [rax+rax+00h]
0x18001283a  mov     rcx, cs:g_IpTlsNLMNotificationLock; hMutex
0x180012841  call    cs:__imp_ReleaseMutex
0x180012848  nop     dword ptr [rax+rax+00h]
0x18001284d  mov     rcx, [rsp+0A8h+var_28]
0x180012855  xor     rcx, rsp; StackCookie
0x180012858  call    __security_check_cookie
0x18001285d  lea     r11, [rsp+0A8h+var_18]
0x180012865  mov     rbx, [r11+20h]
0x180012869  mov     rbp, [r11+30h]
0x18001286d  mov     rsp, r11
0x180012870  pop     r14
0x180012872  pop     rdi
0x180012873  pop     rsi
0x180012874  retn
0x180012876  movups  xmm0, xmmword ptr [rbp+0]
0x18001287a  mov     eax, [rbp+28h]
0x18001287d  lea     rcx, [rsp+0A8h+Row]; Row
0x180012882  movups  xmm1, xmmword ptr [rbp+0Ch]
0x180012886  mov     [rsp+0A8h+Row.InterfaceIndex], eax
0x18001288a  movaps  xmmword ptr [rsp+0A8h+Row.Address], xmm0
0x18001288f  movups  xmmword ptr [rsp+0A8h+Row.Address+0Ch], xmm1
0x180012894  call    cs:__imp_GetUnicastIpAddressEntry
0x18001289b  nop     dword ptr [rax+rax+00h]
0x1800128a0  test    eax, eax
0x1800128a2  jnz     loc_1800126E6
0x1800128a8  mov     edx, 1
0x1800128ad  lea     rcx, [rsp+0A8h+Row]
0x1800128b2  call    IpTlsUpdateGlobalUsableIpv6AddressCount
0x1800128b7  jmp     loc_1800126E6
0x1800128bc  mov     edx, 2
0x1800128c1  mov     rcx, rbp
0x1800128c4  call    IpTlsUpdateGlobalUsableIpv6AddressCount
0x1800128c9  jmp     loc_1800126E6
0x1800128d0  cmp     dword ptr [rsi+3F4h], 0
0x1800128d7  jnz     loc_18001296A
0x1800128dd  mov     rsi, [rsi]
0x1800128e0  cmp     rsi, r14
0x1800128e3  jz      loc_1800126AB
0x1800128e9  jmp     short loc_1800128D0
0x1800128eb  mov     ecx, 17h; Family
0x1800128f0  lea     rdx, [rsp+0A8h+Table]; Table
0x1800128f5  call    cs:__imp_GetUnicastIpAddressTable
0x1800128fc  nop     dword ptr [rax+rax+00h]
0x180012901  test    eax, eax
0x180012903  jnz     loc_1800126E6
0x180012909  mov     rdx, [rsp+0A8h+Table]
0x18001290e  xor     ebp, ebp
0x180012910  cmp     [rdx], ebp
0x180012912  jbe     short loc_18001293F
0x180012914  lea     rcx, ds:0[rbp*4]
0x18001291c  add     rcx, rbp
0x18001291f  shl     rcx, 4
0x180012923  add     rcx, 8
0x180012927  add     rcx, rdx
0x18001292a  mov     edx, 1
0x18001292f  call    IpTlsUpdateGlobalUsableIpv6AddressCount
0x180012934  mov     rdx, [rsp+0A8h+Table]
0x180012939  inc     ebp
0x18001293b  cmp     ebp, [rdx]
0x18001293d  jb      short loc_180012914
0x18001293f  mov     rcx, rdx; Memory
0x180012942  call    cs:__imp_FreeMibTable
0x180012949  nop     dword ptr [rax+rax+00h]
0x18001294e  jmp     loc_1800126E6
0x180012953  test    sil, sil
0x180012956  jz      loc_180012733
0x18001295c  cmp     edi, 3
0x18001295f  jnz     loc_180012757
0x180012965  jmp     loc_180012733
0x18001296a  mov     rcx, [rsi+450h]
0x180012971  mov     r8d, edi
0x180012974  mov     rdx, rbp
0x180012977  call    IpTlsServerIpChangeCallback
0x18001297c  jmp     loc_1800128DD
0x180012981  mov     r8d, 5F5E100h
0x180012987  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CORP_CONNECTIVITY_TIMER_STARTED
0x18001298e  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180012995  call    McTemplateU0q_EventWriteTransfer
0x18001299a  jmp     loc_180012815
```
