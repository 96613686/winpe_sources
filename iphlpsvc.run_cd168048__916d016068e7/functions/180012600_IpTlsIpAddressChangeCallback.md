# IpTlsIpAddressChangeCallback

- ea: `0x180012600`
- end: `0x18001298f`
- name: `IpTlsIpAddressChangeCallback`
- size: `911`
- prototype: `void __stdcall(PVOID CallerContext, PMIB_UNICASTIPADDRESS_ROW Row, MIB_NOTIFICATION_TYPE NotificationType)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000d7b0`
- `0x180011a60`
- `0x180012600`
- `0x18003587c`
- `0x180041020`
- `0x18004b630`
- `0x1800662cc`

## import_xrefs

- `IPHLPAPI!GetUnicastIpAddressEntry` at `0x180012884`
- `IPHLPAPI!GetUnicastIpAddressEntry` at `0x180012884`
- `IPHLPAPI!FreeMibTable` at `0x180012932`
- `IPHLPAPI!FreeMibTable` at `0x180012932`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x1800128e5`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x1800128e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800126a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012715`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001274e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012831`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800126a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012715`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001274e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012831`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012660`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012678`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001276e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012660`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012678`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001276e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800127db`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800127db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800127c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001281e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800127c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001281e`

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
0x180012600  mov     [rsp+arg_0], rbx
0x180012605  mov     [rsp+arg_10], rbp
0x18001260a  push    rsi
0x18001260b  push    rdi
0x18001260c  push    r14
0x18001260e  sub     rsp, 90h
0x180012615  mov     rax, cs:__security_cookie
0x18001261c  xor     rax, rsp
0x18001261f  mov     [rsp+0A8h+var_28], rax
0x180012627  mov     rcx, cs:g_IpTlsConfigChangeLock; hHandle
0x18001262e  xorps   xmm0, xmm0
0x180012631  mov     rbp, rdx
0x180012634  mov     [rsp+0A8h+Table], 0
0x18001263d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180012642  mov     edi, r8d
0x180012645  movups  xmmword ptr [rsp+0A8h+Row.Address], xmm0
0x18001264a  xor     bl, bl
0x18001264c  movups  xmmword ptr [rsp+0A8h+Row.Address+10h], xmm0
0x180012651  movups  xmmword ptr [rsp+0A8h+Row.InterfaceLuid], xmm0
0x180012656  movups  xmmword ptr [rsp+0A8h+Row.SuffixOrigin], xmm0
0x18001265b  movups  xmmword ptr [rsp+0A8h+Row.DadState], xmm0
0x180012660  call    cs:__imp_WaitForSingleObject
0x180012667  nop     dword ptr [rax+rax+00h]
0x18001266c  mov     rcx, cs:g_IpTlsInterfaceListLock; hHandle
0x180012673  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180012678  call    cs:__imp_WaitForSingleObject
0x18001267f  nop     dword ptr [rax+rax+00h]
0x180012684  mov     rsi, cs:g_IpTlsInterfaceListHead
0x18001268b  lea     r14, g_IpTlsInterfaceListHead
0x180012692  cmp     rsi, r14
0x180012695  jnz     loc_1800128C0
0x18001269b  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x1800126a2  call    cs:__imp_ReleaseMutex
0x1800126a9  nop     dword ptr [rax+rax+00h]
0x1800126ae  cmp     cs:g_IpTlsGlobalV6AddressCount, 0
0x1800126b5  mov     eax, edi
0x1800126b7  setz    sil
0x1800126bb  sub     eax, 1
0x1800126be  jz      loc_180012866
0x1800126c4  sub     eax, 1
0x1800126c7  jz      loc_1800128AC
0x1800126cd  cmp     eax, 1
0x1800126d0  jz      loc_1800128DB
0x1800126d6  cmp     cs:g_IpTlsGlobalV6AddressCount, 0
0x1800126dd  jz      loc_180012943
0x1800126e3  test    sil, sil
0x1800126e6  jz      short loc_180012747
0x1800126e8  cmp     cs:g_IpTlsConfiguredForCorpConnectivity, 0
0x1800126ef  jnz     short loc_180012747
0x1800126f1  cmp     edi, 3
0x1800126f4  jz      short loc_180012747
0x1800126f6  lea     rdx, aIptlsipaddress; "IpTlsIpAddressChangeCallback:Removing a"...
0x1800126fd  mov     ecx, 10000000h
0x180012702  call    EventWrite0
0x180012707  xor     ecx, ecx
0x180012709  call    IpTlsRemoveEligibleInterfaces
0x18001270e  mov     rcx, cs:g_IpTlsConfigChangeLock; hMutex
0x180012715  call    cs:__imp_ReleaseMutex
0x18001271c  nop     dword ptr [rax+rax+00h]
0x180012721  jmp     short loc_180012762
0x180012723  cmp     cs:g_IpTlsConfiguredForCorpConnectivity, bl
0x180012729  jnz     short loc_180012747
0x18001272b  lea     rdx, aIptlsipaddress_0; "IpTlsIpAddressChangeCallbackNo global v"...
0x180012732  mov     ecx, 10000000h
0x180012737  call    EventWrite0
0x18001273c  cmp     cs:g_IpTlsGlobalV6AddressCount, 0
0x180012743  mov     bl, 1
0x180012745  jnz     short loc_1800126E3
0x180012747  mov     rcx, cs:g_IpTlsConfigChangeLock; hMutex
0x18001274e  call    cs:__imp_ReleaseMutex
0x180012755  nop     dword ptr [rax+rax+00h]
0x18001275a  test    bl, bl
0x18001275c  jz      loc_18001283D
0x180012762  mov     rcx, cs:g_IpTlsNLMNotificationLock; hHandle
0x180012769  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18001276e  call    cs:__imp_WaitForSingleObject
0x180012775  nop     dword ptr [rax+rax+00h]
0x18001277a  mov     rax, cs:g_IpTlsCorpConnectivityTimeout
0x180012781  neg     rax
0x180012784  mov     rcx, rax
0x180012787  mov     [rsp+0A8h+pftDueTime.dwLowDateTime], eax
0x18001278b  shr     rcx, 20h
0x18001278f  cmp     cs:g_IpTlsCorpConnectivityTimerArmed, 0
0x180012796  mov     [rsp+0A8h+pftDueTime.dwHighDateTime], ecx
0x18001279a  jz      short loc_1800127E7
0x18001279c  lea     rdx, aIptlsrestartco_0; "IpTlsRestartCorpConnectivityTimer: Canc"...
0x1800127a3  mov     cs:g_IpTlsCorpConnectivityTimerArmed, 0
0x1800127aa  mov     ecx, 10000000h
0x1800127af  call    EventWrite0
0x1800127b4  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x1800127bb  xor     r9d, r9d; msWindowLength
0x1800127be  xor     r8d, r8d; msPeriod
0x1800127c1  xor     edx, edx; pftDueTime
0x1800127c3  call    cs:__imp_SetThreadpoolTimer
0x1800127ca  nop     dword ptr [rax+rax+00h]
0x1800127cf  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x1800127d6  mov     edx, 1; fCancelPendingCallbacks
0x1800127db  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800127e2  nop     dword ptr [rax+rax+00h]
0x1800127e7  lea     rdx, aIptlsrestartco; "IpTlsRestartCorpConnectivityTimer:Start"...
0x1800127ee  mov     ecx, 10000000h
0x1800127f3  call    EventWrite0
0x1800127f8  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800127ff  jnz     loc_180012971
0x180012805  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x18001280c  lea     rdx, [rsp+0A8h+pftDueTime]; pftDueTime
0x180012811  xor     r9d, r9d; msWindowLength
0x180012814  mov     cs:g_IpTlsCorpConnectivityTimerArmed, 1
0x18001281b  xor     r8d, r8d; msPeriod
0x18001281e  call    cs:__imp_SetThreadpoolTimer
0x180012825  nop     dword ptr [rax+rax+00h]
0x18001282a  mov     rcx, cs:g_IpTlsNLMNotificationLock; hMutex
0x180012831  call    cs:__imp_ReleaseMutex
0x180012838  nop     dword ptr [rax+rax+00h]
0x18001283d  mov     rcx, [rsp+0A8h+var_28]
0x180012845  xor     rcx, rsp; StackCookie
0x180012848  call    __security_check_cookie
0x18001284d  lea     r11, [rsp+0A8h+var_18]
0x180012855  mov     rbx, [r11+20h]
0x180012859  mov     rbp, [r11+30h]
0x18001285d  mov     rsp, r11
0x180012860  pop     r14
0x180012862  pop     rdi
0x180012863  pop     rsi
0x180012864  retn
0x180012866  movups  xmm0, xmmword ptr [rbp+0]
0x18001286a  mov     eax, [rbp+28h]
0x18001286d  lea     rcx, [rsp+0A8h+Row]; Row
0x180012872  movups  xmm1, xmmword ptr [rbp+0Ch]
0x180012876  mov     [rsp+0A8h+Row.InterfaceIndex], eax
0x18001287a  movaps  xmmword ptr [rsp+0A8h+Row.Address], xmm0
0x18001287f  movups  xmmword ptr [rsp+0A8h+Row.Address+0Ch], xmm1
0x180012884  call    cs:__imp_GetUnicastIpAddressEntry
0x18001288b  nop     dword ptr [rax+rax+00h]
0x180012890  test    eax, eax
0x180012892  jnz     loc_1800126D6
0x180012898  mov     edx, 1
0x18001289d  lea     rcx, [rsp+0A8h+Row]
0x1800128a2  call    IpTlsUpdateGlobalUsableIpv6AddressCount
0x1800128a7  jmp     loc_1800126D6
0x1800128ac  mov     edx, 2
0x1800128b1  mov     rcx, rbp
0x1800128b4  call    IpTlsUpdateGlobalUsableIpv6AddressCount
0x1800128b9  jmp     loc_1800126D6
0x1800128c0  cmp     dword ptr [rsi+3F4h], 0
0x1800128c7  jnz     loc_18001295A
0x1800128cd  mov     rsi, [rsi]
0x1800128d0  cmp     rsi, r14
0x1800128d3  jz      loc_18001269B
0x1800128d9  jmp     short loc_1800128C0
0x1800128db  mov     ecx, 17h; Family
0x1800128e0  lea     rdx, [rsp+0A8h+Table]; Table
0x1800128e5  call    cs:__imp_GetUnicastIpAddressTable
0x1800128ec  nop     dword ptr [rax+rax+00h]
0x1800128f1  test    eax, eax
0x1800128f3  jnz     loc_1800126D6
0x1800128f9  mov     rdx, [rsp+0A8h+Table]
0x1800128fe  xor     ebp, ebp
0x180012900  cmp     [rdx], ebp
0x180012902  jbe     short loc_18001292F
0x180012904  lea     rcx, ds:0[rbp*4]
0x18001290c  add     rcx, rbp
0x18001290f  shl     rcx, 4
0x180012913  add     rcx, 8
0x180012917  add     rcx, rdx
0x18001291a  mov     edx, 1
0x18001291f  call    IpTlsUpdateGlobalUsableIpv6AddressCount
0x180012924  mov     rdx, [rsp+0A8h+Table]
0x180012929  inc     ebp
0x18001292b  cmp     ebp, [rdx]
0x18001292d  jb      short loc_180012904
0x18001292f  mov     rcx, rdx; Memory
0x180012932  call    cs:__imp_FreeMibTable
0x180012939  nop     dword ptr [rax+rax+00h]
0x18001293e  jmp     loc_1800126D6
0x180012943  test    sil, sil
0x180012946  jz      loc_180012723
0x18001294c  cmp     edi, 3
0x18001294f  jnz     loc_180012747
0x180012955  jmp     loc_180012723
0x18001295a  mov     rcx, [rsi+450h]
0x180012961  mov     r8d, edi
0x180012964  mov     rdx, rbp
0x180012967  call    IpTlsServerIpChangeCallback
0x18001296c  jmp     loc_1800128CD
0x180012971  mov     r8d, 5F5E100h
0x180012977  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CORP_CONNECTIVITY_TIMER_STARTED
0x18001297e  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180012985  call    McTemplateU0q_EventWriteTransfer
0x18001298a  jmp     loc_180012805
```
