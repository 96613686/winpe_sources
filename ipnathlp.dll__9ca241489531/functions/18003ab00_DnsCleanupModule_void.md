# DnsCleanupModule(void)

- ea: `0x18003ab00`
- end: `0x18003ad7b`
- name: `?DnsCleanupModule@@YAXXZ`
- size: `635`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033a64`

## callees

- `0x180008300`
- `0x18000c110`
- `0x18000c750`
- `0x180010b00`
- `0x180010d90`
- `0x180011740`
- `0x1800384d4`
- `0x18003ab00`
- `0x18003ad84`
- `0x18003afa0`
- `0x18004b0d0`
- `0x18004ba34`
- `0x18004bf70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ab4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ab4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ad06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ad06`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003ad24`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003ad31`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003ad24`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003ad31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003ac2f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003ac2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ac51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ac51`
- `IPHLPAPI!CancelIPChangeNotify` at `0x18003ac1b`
- `IPHLPAPI!CancelIPChangeNotify` at `0x18003ac1b`
- `NSI!NsiCancelChangeNotification` at `0x18003abcf`
- `NSI!NsiCancelChangeNotification` at `0x18003abcf`
- `ntdll!RtlDeregisterWait` at `0x18003ab5e`
- `ntdll!RtlDeregisterWait` at `0x18003abb2`
- `ntdll!RtlDeregisterWait` at `0x18003abfe`
- `ntdll!RtlDeregisterWait` at `0x18003ac9f`
- `ntdll!RtlDeregisterWait` at `0x18003ab5e`
- `ntdll!RtlDeregisterWait` at `0x18003abb2`
- `ntdll!RtlDeregisterWait` at `0x18003abfe`
- `ntdll!RtlDeregisterWait` at `0x18003ac9f`
- `ntdll!NtClose` at `0x18003ab77`
- `ntdll!NtClose` at `0x18003ab99`
- `ntdll!NtClose` at `0x18003abdc`
- `ntdll!NtClose` at `0x18003ac7d`
- `ntdll!NtClose` at `0x18003acb8`
- `ntdll!NtClose` at `0x18003acda`
- `ntdll!NtClose` at `0x18003ab77`
- `ntdll!NtClose` at `0x18003ab99`
- `ntdll!NtClose` at `0x18003abdc`
- `ntdll!NtClose` at `0x18003ac7d`
- `ntdll!NtClose` at `0x18003acb8`
- `ntdll!NtClose` at `0x18003acda`

## pseudocode

```c
void DnsCleanupModule(void)
{
  unsigned int v0; // edx
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids);
  }
  DnsEmptyTables();
  EnterCriticalSection(&DnsGlobalInfoLock);
  if ( DnsNotifyChangeKeyWaitHandle )
  {
    RtlDeregisterWait(DnsNotifyChangeKeyWaitHandle);
    DnsNotifyChangeKeyWaitHandle = 0;
  }
  if ( DnsNotifyChangeKeyEvent )
  {
    NtClose(DnsNotifyChangeKeyEvent);
    DnsNotifyChangeKeyEvent = 0;
    DnsNotifyChangeKeyCallbackRoutine(0, 0);
  }
  if ( DnsTcpipInterfacesKey )
  {
    NtClose(DnsTcpipInterfacesKey);
    DnsTcpipInterfacesKey = 0;
  }
  if ( v6DnsNotifyChangeAddressWaitHandle )
  {
    RtlDeregisterWait(v6DnsNotifyChangeAddressWaitHandle);
    v6DnsNotifyChangeAddressWaitHandle = 0;
  }
  if ( v6DnsNotifyChangeAddressEvent )
  {
    NsiCancelChangeNotification(&Dnsv6NotifyChangeAddressOverlapped);
    NtClose(v6DnsNotifyChangeAddressEvent);
    v6DnsNotifyChangeAddressEvent = 0;
    Dnsv6NotifyChangeAddressCallbackRoutine(0, 0);
  }
  if ( DnsNotifyChangeAddressWaitHandle )
  {
    RtlDeregisterWait(DnsNotifyChangeAddressWaitHandle);
    DnsNotifyChangeAddressWaitHandle = 0;
  }
  if ( DnsNotifyChangeAddressEvent )
  {
    if ( CancelIPChangeNotify(&DnsNotifyChangeAddressOverlapped)
      && WaitForSingleObject(DnsNotifyChangeAddressEvent, 0xFFFFFFFF)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids, LastError);
    }
    NtClose(DnsNotifyChangeAddressEvent);
    DnsNotifyChangeAddressEvent = 0;
    DnsNotifyChangeAddressCallbackRoutine(0, 0);
  }
  if ( DnsNotifyChangeKeyICSDomainWaitHandle )
  {
    RtlDeregisterWait(DnsNotifyChangeKeyICSDomainWaitHandle);
    DnsNotifyChangeKeyICSDomainWaitHandle = 0;
  }
  if ( DnsNotifyChangeKeyICSDomainEvent )
  {
    NtClose(DnsNotifyChangeKeyICSDomainEvent);
    DnsNotifyChangeKeyICSDomainEvent = 0;
    DnsNotifyChangeKeyICSDomainCallbackRoutine(0, 0);
  }
  if ( DnsTcpipParametersKey )
  {
    NtClose(DnsTcpipParametersKey);
    DnsTcpipParametersKey = 0;
  }
  if ( g_pDnsInterfaceMonitor )
  {
    CInterfaceMonitor::`scalar deleting destructor'(g_pDnsInterfaceMonitor, v0);
    g_pDnsInterfaceMonitor = 0;
  }
  LeaveCriticalSection(&DnsGlobalInfoLock);
  DnsShutdownInterfaceManagement(1u);
  DnsShutdownTableManagement();
  DnsShutdownFileManagement();
  DeleteCriticalSection(&DnsGlobalInfoLock);
  DeleteCriticalSection(&g_csDnsServerListLock);
  DeleteComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids);
  }
}

```

## disassembly

```asm
0x18003ab00  mov     [rsp+arg_0], rbx
0x18003ab05  push    rsi
0x18003ab06  sub     rsp, 20h
0x18003ab0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ab11  lea     rsi, WPP_GLOBAL_Control
0x18003ab18  cmp     rcx, rsi
0x18003ab1b  jz      short loc_18003AB3E
0x18003ab1d  test    byte ptr [rcx+1Ch], 10h
0x18003ab21  jz      short loc_18003AB3E
0x18003ab23  cmp     byte ptr [rcx+19h], 6
0x18003ab27  jb      short loc_18003AB3E
0x18003ab29  mov     rcx, [rcx+10h]
0x18003ab2d  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x18003ab34  mov     edx, 0Ah
0x18003ab39  call    WPP_SF_
0x18003ab3e  call    ?DnsEmptyTables@@YAXXZ; DnsEmptyTables(void)
0x18003ab43  lea     rcx, ?DnsGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003ab4a  call    cs:__imp_EnterCriticalSection
0x18003ab50  mov     rcx, cs:?DnsNotifyChangeKeyWaitHandle@@3PEAXEA; hWaitHandle
0x18003ab57  xor     ebx, ebx
0x18003ab59  test    rcx, rcx
0x18003ab5c  jz      short loc_18003AB6B
0x18003ab5e  call    cs:__imp_RtlDeregisterWait
0x18003ab64  mov     cs:?DnsNotifyChangeKeyWaitHandle@@3PEAXEA, rbx; void * DnsNotifyChangeKeyWaitHandle
0x18003ab6b  mov     rcx, cs:?DnsNotifyChangeKeyEvent@@3PEAXEA; Handle
0x18003ab72  test    rcx, rcx
0x18003ab75  jz      short loc_18003AB8D
0x18003ab77  call    cs:__imp_NtClose
0x18003ab7d  xor     edx, edx; BOOLEAN
0x18003ab7f  mov     cs:?DnsNotifyChangeKeyEvent@@3PEAXEA, rbx; void * DnsNotifyChangeKeyEvent
0x18003ab86  xor     ecx, ecx; PVOID
0x18003ab88  call    ?DnsNotifyChangeKeyCallbackRoutine@@YAXPEAXE@Z; DnsNotifyChangeKeyCallbackRoutine(void *,uchar)
0x18003ab8d  mov     rcx, cs:?DnsTcpipInterfacesKey@@3PEAXEA; Handle
0x18003ab94  test    rcx, rcx
0x18003ab97  jz      short loc_18003ABA6
0x18003ab99  call    cs:__imp_NtClose
0x18003ab9f  mov     cs:?DnsTcpipInterfacesKey@@3PEAXEA, rbx; void * DnsTcpipInterfacesKey
0x18003aba6  mov     rcx, cs:?v6DnsNotifyChangeAddressWaitHandle@@3PEAXEA; hWaitHandle
0x18003abad  test    rcx, rcx
0x18003abb0  jz      short loc_18003ABBF
0x18003abb2  call    cs:__imp_RtlDeregisterWait
0x18003abb8  mov     cs:?v6DnsNotifyChangeAddressWaitHandle@@3PEAXEA, rbx; void * v6DnsNotifyChangeAddressWaitHandle
0x18003abbf  cmp     cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA, rbx; void * v6DnsNotifyChangeAddressEvent
0x18003abc6  jz      short loc_18003ABF2
0x18003abc8  lea     rcx, ?Dnsv6NotifyChangeAddressOverlapped@@3U_OVERLAPPED@@A; _OVERLAPPED Dnsv6NotifyChangeAddressOverlapped
0x18003abcf  call    cs:__imp_NsiCancelChangeNotification
0x18003abd5  mov     rcx, cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA; Handle
0x18003abdc  call    cs:__imp_NtClose
0x18003abe2  xor     edx, edx; BOOLEAN
0x18003abe4  mov     cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA, rbx; void * v6DnsNotifyChangeAddressEvent
0x18003abeb  xor     ecx, ecx; PVOID
0x18003abed  call    ?Dnsv6NotifyChangeAddressCallbackRoutine@@YAXPEAXE@Z; Dnsv6NotifyChangeAddressCallbackRoutine(void *,uchar)
0x18003abf2  mov     rcx, cs:?DnsNotifyChangeAddressWaitHandle@@3PEAXEA; hWaitHandle
0x18003abf9  test    rcx, rcx
0x18003abfc  jz      short loc_18003AC0B
0x18003abfe  call    cs:__imp_RtlDeregisterWait
0x18003ac04  mov     cs:?DnsNotifyChangeAddressWaitHandle@@3PEAXEA, rbx; void * DnsNotifyChangeAddressWaitHandle
0x18003ac0b  cmp     cs:?DnsNotifyChangeAddressEvent@@3PEAXEA, rbx; void * DnsNotifyChangeAddressEvent
0x18003ac12  jz      short loc_18003AC93
0x18003ac14  lea     rcx, ?DnsNotifyChangeAddressOverlapped@@3U_OVERLAPPED@@A; notifyOverlapped
0x18003ac1b  call    cs:__imp_CancelIPChangeNotify
0x18003ac21  test    eax, eax
0x18003ac23  jz      short loc_18003AC76
0x18003ac25  mov     rcx, cs:?DnsNotifyChangeAddressEvent@@3PEAXEA; hHandle
0x18003ac2c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003ac2f  call    cs:__imp_WaitForSingleObject
0x18003ac35  test    eax, eax
0x18003ac37  jz      short loc_18003AC76
0x18003ac39  mov     rax, cs:WPP_GLOBAL_Control
0x18003ac40  cmp     rax, rsi
0x18003ac43  jz      short loc_18003AC76
0x18003ac45  test    byte ptr [rax+1Ch], 10h
0x18003ac49  jz      short loc_18003AC76
0x18003ac4b  cmp     byte ptr [rax+19h], 2
0x18003ac4f  jb      short loc_18003AC76
0x18003ac51  call    cs:__imp_GetLastError
0x18003ac57  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac5e  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x18003ac65  mov     edx, 0Bh
0x18003ac6a  mov     r9d, eax
0x18003ac6d  mov     rcx, [rcx+10h]
0x18003ac71  call    WPP_SF_d
0x18003ac76  mov     rcx, cs:?DnsNotifyChangeAddressEvent@@3PEAXEA; Handle
0x18003ac7d  call    cs:__imp_NtClose
0x18003ac83  xor     edx, edx; BOOLEAN
0x18003ac85  mov     cs:?DnsNotifyChangeAddressEvent@@3PEAXEA, rbx; void * DnsNotifyChangeAddressEvent
0x18003ac8c  xor     ecx, ecx; PVOID
0x18003ac8e  call    ?DnsNotifyChangeAddressCallbackRoutine@@YAXPEAXE@Z; DnsNotifyChangeAddressCallbackRoutine(void *,uchar)
0x18003ac93  mov     rcx, cs:?DnsNotifyChangeKeyICSDomainWaitHandle@@3PEAXEA; hWaitHandle
0x18003ac9a  test    rcx, rcx
0x18003ac9d  jz      short loc_18003ACAC
0x18003ac9f  call    cs:__imp_RtlDeregisterWait
0x18003aca5  mov     cs:?DnsNotifyChangeKeyICSDomainWaitHandle@@3PEAXEA, rbx; void * DnsNotifyChangeKeyICSDomainWaitHandle
0x18003acac  mov     rcx, cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA; Handle
0x18003acb3  test    rcx, rcx
0x18003acb6  jz      short loc_18003ACCE
0x18003acb8  call    cs:__imp_NtClose
0x18003acbe  xor     edx, edx; BOOLEAN
0x18003acc0  mov     cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA, rbx; void * DnsNotifyChangeKeyICSDomainEvent
0x18003acc7  xor     ecx, ecx; PVOID
0x18003acc9  call    ?DnsNotifyChangeKeyICSDomainCallbackRoutine@@YAXPEAXE@Z; DnsNotifyChangeKeyICSDomainCallbackRoutine(void *,uchar)
0x18003acce  mov     rcx, cs:?DnsTcpipParametersKey@@3PEAXEA; Handle
0x18003acd5  test    rcx, rcx
0x18003acd8  jz      short loc_18003ACE7
0x18003acda  call    cs:__imp_NtClose
0x18003ace0  mov     cs:?DnsTcpipParametersKey@@3PEAXEA, rbx; void * DnsTcpipParametersKey
0x18003ace7  mov     rcx, cs:?g_pDnsInterfaceMonitor@@3PEAVCInterfaceMonitor@@EA; this
0x18003acee  test    rcx, rcx
0x18003acf1  jz      short loc_18003ACFF
0x18003acf3  call    ??_GCInterfaceMonitor@@QEAAPEAXI@Z; CInterfaceMonitor::`scalar deleting destructor'(uint)
0x18003acf8  mov     cs:?g_pDnsInterfaceMonitor@@3PEAVCInterfaceMonitor@@EA, rbx; CInterfaceMonitor * g_pDnsInterfaceMonitor
0x18003acff  lea     rcx, ?DnsGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003ad06  call    cs:__imp_LeaveCriticalSection
0x18003ad0c  mov     cl, 1; unsigned __int8
0x18003ad0e  call    ?DnsShutdownInterfaceManagement@@YAXE@Z; DnsShutdownInterfaceManagement(uchar)
0x18003ad13  call    ?DnsShutdownTableManagement@@YAXXZ; DnsShutdownTableManagement(void)
0x18003ad18  call    ?DnsShutdownFileManagement@@YAXXZ; DnsShutdownFileManagement(void)
0x18003ad1d  lea     rcx, ?DnsGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003ad24  call    cs:__imp_DeleteCriticalSection
0x18003ad2a  lea     rcx, ?g_csDnsServerListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003ad31  call    cs:__imp_DeleteCriticalSection
0x18003ad37  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x18003ad3e  call    ?DeleteComponentReference@@YAXPEAU_COMPONENT_REFERENCE@@@Z; DeleteComponentReference(_COMPONENT_REFERENCE *)
0x18003ad43  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ad4a  cmp     rcx, rsi
0x18003ad4d  jz      short loc_18003AD70
0x18003ad4f  test    byte ptr [rcx+1Ch], 10h
0x18003ad53  jz      short loc_18003AD70
0x18003ad55  cmp     byte ptr [rcx+19h], 6
0x18003ad59  jb      short loc_18003AD70
0x18003ad5b  mov     rcx, [rcx+10h]
0x18003ad5f  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x18003ad66  mov     edx, 0Ch
0x18003ad6b  call    WPP_SF_
0x18003ad70  mov     rbx, [rsp+28h+arg_0]
0x18003ad75  add     rsp, 20h
0x18003ad79  pop     rsi
0x18003ad7a  retn
```
