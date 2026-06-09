# DnsCleanupModule(void)

- ea: `0x18003dbc4`
- end: `0x18003deb0`
- name: `?DnsCleanupModule@@YAXXZ`
- size: `748`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180036364`

## callees

- `0x1800087c0`
- `0x18000ca20`
- `0x18000d090`
- `0x180011860`
- `0x180011b20`
- `0x180012580`
- `0x18003b2e8`
- `0x18003dbc4`
- `0x18003deb8`
- `0x18003e124`
- `0x18004ed18`
- `0x18004fa34`
- `0x18004fc6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003dc0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003dc0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003de28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003de28`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003de4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003de5f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003de4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003de5f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003dd2d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003dd2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dd55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dd55`
- `IPHLPAPI!CancelIPChangeNotify` at `0x18003dd13`
- `IPHLPAPI!CancelIPChangeNotify` at `0x18003dd13`
- `NSI!NsiCancelChangeNotification` at `0x18003dcb1`
- `NSI!NsiCancelChangeNotification` at `0x18003dcb1`
- `ntdll!RtlDeregisterWait` at `0x18003dc28`
- `ntdll!RtlDeregisterWait` at `0x18003dc8e`
- `ntdll!RtlDeregisterWait` at `0x18003dcec`
- `ntdll!RtlDeregisterWait` at `0x18003ddaf`
- `ntdll!RtlDeregisterWait` at `0x18003dc28`
- `ntdll!RtlDeregisterWait` at `0x18003dc8e`
- `ntdll!RtlDeregisterWait` at `0x18003dcec`
- `ntdll!RtlDeregisterWait` at `0x18003ddaf`
- `ntdll!NtClose` at `0x18003dc47`
- `ntdll!NtClose` at `0x18003dc6f`
- `ntdll!NtClose` at `0x18003dcc4`
- `ntdll!NtClose` at `0x18003dd87`
- `ntdll!NtClose` at `0x18003ddce`
- `ntdll!NtClose` at `0x18003ddf6`
- `ntdll!NtClose` at `0x18003dc47`
- `ntdll!NtClose` at `0x18003dc6f`
- `ntdll!NtClose` at `0x18003dcc4`
- `ntdll!NtClose` at `0x18003dd87`
- `ntdll!NtClose` at `0x18003ddce`
- `ntdll!NtClose` at `0x18003ddf6`

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
0x18003dbc4  mov     [rsp+arg_0], rbx
0x18003dbc9  push    rsi
0x18003dbca  sub     rsp, 20h
0x18003dbce  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dbd5  lea     rsi, WPP_GLOBAL_Control
0x18003dbdc  cmp     rcx, rsi
0x18003dbdf  jz      short loc_18003DC02
0x18003dbe1  test    byte ptr [rcx+1Ch], 10h
0x18003dbe5  jz      short loc_18003DC02
0x18003dbe7  cmp     byte ptr [rcx+19h], 6
0x18003dbeb  jb      short loc_18003DC02
0x18003dbed  mov     rcx, [rcx+10h]
0x18003dbf1  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x18003dbf8  mov     edx, 0Ah
0x18003dbfd  call    WPP_SF_
0x18003dc02  call    ?DnsEmptyTables@@YAXXZ; DnsEmptyTables(void)
0x18003dc07  lea     rcx, ?DnsGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003dc0e  call    cs:__imp_EnterCriticalSection
0x18003dc15  nop     dword ptr [rax+rax+00h]
0x18003dc1a  mov     rcx, cs:?DnsNotifyChangeKeyWaitHandle@@3PEAXEA; hWaitHandle
0x18003dc21  xor     ebx, ebx
0x18003dc23  test    rcx, rcx
0x18003dc26  jz      short loc_18003DC3B
0x18003dc28  call    cs:__imp_RtlDeregisterWait
0x18003dc2f  nop     dword ptr [rax+rax+00h]
0x18003dc34  mov     cs:?DnsNotifyChangeKeyWaitHandle@@3PEAXEA, rbx; void * DnsNotifyChangeKeyWaitHandle
0x18003dc3b  mov     rcx, cs:?DnsNotifyChangeKeyEvent@@3PEAXEA; Handle
0x18003dc42  test    rcx, rcx
0x18003dc45  jz      short loc_18003DC63
0x18003dc47  call    cs:__imp_NtClose
0x18003dc4e  nop     dword ptr [rax+rax+00h]
0x18003dc53  xor     edx, edx; BOOLEAN
0x18003dc55  mov     cs:?DnsNotifyChangeKeyEvent@@3PEAXEA, rbx; void * DnsNotifyChangeKeyEvent
0x18003dc5c  xor     ecx, ecx; PVOID
0x18003dc5e  call    ?DnsNotifyChangeKeyCallbackRoutine@@YAXPEAXE@Z; DnsNotifyChangeKeyCallbackRoutine(void *,uchar)
0x18003dc63  mov     rcx, cs:?DnsTcpipInterfacesKey@@3PEAXEA; Handle
0x18003dc6a  test    rcx, rcx
0x18003dc6d  jz      short loc_18003DC82
0x18003dc6f  call    cs:__imp_NtClose
0x18003dc76  nop     dword ptr [rax+rax+00h]
0x18003dc7b  mov     cs:?DnsTcpipInterfacesKey@@3PEAXEA, rbx; void * DnsTcpipInterfacesKey
0x18003dc82  mov     rcx, cs:?v6DnsNotifyChangeAddressWaitHandle@@3PEAXEA; hWaitHandle
0x18003dc89  test    rcx, rcx
0x18003dc8c  jz      short loc_18003DCA1
0x18003dc8e  call    cs:__imp_RtlDeregisterWait
0x18003dc95  nop     dword ptr [rax+rax+00h]
0x18003dc9a  mov     cs:?v6DnsNotifyChangeAddressWaitHandle@@3PEAXEA, rbx; void * v6DnsNotifyChangeAddressWaitHandle
0x18003dca1  cmp     cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA, rbx; void * v6DnsNotifyChangeAddressEvent
0x18003dca8  jz      short loc_18003DCE0
0x18003dcaa  lea     rcx, ?Dnsv6NotifyChangeAddressOverlapped@@3U_OVERLAPPED@@A; _OVERLAPPED Dnsv6NotifyChangeAddressOverlapped
0x18003dcb1  call    cs:__imp_NsiCancelChangeNotification
0x18003dcb8  nop     dword ptr [rax+rax+00h]
0x18003dcbd  mov     rcx, cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA; Handle
0x18003dcc4  call    cs:__imp_NtClose
0x18003dccb  nop     dword ptr [rax+rax+00h]
0x18003dcd0  xor     edx, edx; BOOLEAN
0x18003dcd2  mov     cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA, rbx; void * v6DnsNotifyChangeAddressEvent
0x18003dcd9  xor     ecx, ecx; PVOID
0x18003dcdb  call    ?Dnsv6NotifyChangeAddressCallbackRoutine@@YAXPEAXE@Z; Dnsv6NotifyChangeAddressCallbackRoutine(void *,uchar)
0x18003dce0  mov     rcx, cs:?DnsNotifyChangeAddressWaitHandle@@3PEAXEA; hWaitHandle
0x18003dce7  test    rcx, rcx
0x18003dcea  jz      short loc_18003DCFF
0x18003dcec  call    cs:__imp_RtlDeregisterWait
0x18003dcf3  nop     dword ptr [rax+rax+00h]
0x18003dcf8  mov     cs:?DnsNotifyChangeAddressWaitHandle@@3PEAXEA, rbx; void * DnsNotifyChangeAddressWaitHandle
0x18003dcff  cmp     cs:?DnsNotifyChangeAddressEvent@@3PEAXEA, rbx; void * DnsNotifyChangeAddressEvent
0x18003dd06  jz      loc_18003DDA3
0x18003dd0c  lea     rcx, ?DnsNotifyChangeAddressOverlapped@@3U_OVERLAPPED@@A; notifyOverlapped
0x18003dd13  call    cs:__imp_CancelIPChangeNotify
0x18003dd1a  nop     dword ptr [rax+rax+00h]
0x18003dd1f  test    eax, eax
0x18003dd21  jz      short loc_18003DD80
0x18003dd23  mov     rcx, cs:?DnsNotifyChangeAddressEvent@@3PEAXEA; hHandle
0x18003dd2a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003dd2d  call    cs:__imp_WaitForSingleObject
0x18003dd34  nop     dword ptr [rax+rax+00h]
0x18003dd39  test    eax, eax
0x18003dd3b  jz      short loc_18003DD80
0x18003dd3d  mov     rax, cs:WPP_GLOBAL_Control
0x18003dd44  cmp     rax, rsi
0x18003dd47  jz      short loc_18003DD80
0x18003dd49  test    byte ptr [rax+1Ch], 10h
0x18003dd4d  jz      short loc_18003DD80
0x18003dd4f  cmp     byte ptr [rax+19h], 2
0x18003dd53  jb      short loc_18003DD80
0x18003dd55  call    cs:__imp_GetLastError
0x18003dd5c  nop     dword ptr [rax+rax+00h]
0x18003dd61  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dd68  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x18003dd6f  mov     edx, 0Bh
0x18003dd74  mov     r9d, eax
0x18003dd77  mov     rcx, [rcx+10h]
0x18003dd7b  call    WPP_SF_d
0x18003dd80  mov     rcx, cs:?DnsNotifyChangeAddressEvent@@3PEAXEA; Handle
0x18003dd87  call    cs:__imp_NtClose
0x18003dd8e  nop     dword ptr [rax+rax+00h]
0x18003dd93  xor     edx, edx; BOOLEAN
0x18003dd95  mov     cs:?DnsNotifyChangeAddressEvent@@3PEAXEA, rbx; void * DnsNotifyChangeAddressEvent
0x18003dd9c  xor     ecx, ecx; PVOID
0x18003dd9e  call    ?DnsNotifyChangeAddressCallbackRoutine@@YAXPEAXE@Z; DnsNotifyChangeAddressCallbackRoutine(void *,uchar)
0x18003dda3  mov     rcx, cs:?DnsNotifyChangeKeyICSDomainWaitHandle@@3PEAXEA; hWaitHandle
0x18003ddaa  test    rcx, rcx
0x18003ddad  jz      short loc_18003DDC2
0x18003ddaf  call    cs:__imp_RtlDeregisterWait
0x18003ddb6  nop     dword ptr [rax+rax+00h]
0x18003ddbb  mov     cs:?DnsNotifyChangeKeyICSDomainWaitHandle@@3PEAXEA, rbx; void * DnsNotifyChangeKeyICSDomainWaitHandle
0x18003ddc2  mov     rcx, cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA; Handle
0x18003ddc9  test    rcx, rcx
0x18003ddcc  jz      short loc_18003DDEA
0x18003ddce  call    cs:__imp_NtClose
0x18003ddd5  nop     dword ptr [rax+rax+00h]
0x18003ddda  xor     edx, edx; BOOLEAN
0x18003dddc  mov     cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA, rbx; void * DnsNotifyChangeKeyICSDomainEvent
0x18003dde3  xor     ecx, ecx; PVOID
0x18003dde5  call    ?DnsNotifyChangeKeyICSDomainCallbackRoutine@@YAXPEAXE@Z; DnsNotifyChangeKeyICSDomainCallbackRoutine(void *,uchar)
0x18003ddea  mov     rcx, cs:?DnsTcpipParametersKey@@3PEAXEA; Handle
0x18003ddf1  test    rcx, rcx
0x18003ddf4  jz      short loc_18003DE09
0x18003ddf6  call    cs:__imp_NtClose
0x18003ddfd  nop     dword ptr [rax+rax+00h]
0x18003de02  mov     cs:?DnsTcpipParametersKey@@3PEAXEA, rbx; void * DnsTcpipParametersKey
0x18003de09  mov     rcx, cs:?g_pDnsInterfaceMonitor@@3PEAVCInterfaceMonitor@@EA; this
0x18003de10  test    rcx, rcx
0x18003de13  jz      short loc_18003DE21
0x18003de15  call    ??_GCInterfaceMonitor@@QEAAPEAXI@Z; CInterfaceMonitor::`scalar deleting destructor'(uint)
0x18003de1a  mov     cs:?g_pDnsInterfaceMonitor@@3PEAVCInterfaceMonitor@@EA, rbx; CInterfaceMonitor * g_pDnsInterfaceMonitor
0x18003de21  lea     rcx, ?DnsGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003de28  call    cs:__imp_LeaveCriticalSection
0x18003de2f  nop     dword ptr [rax+rax+00h]
0x18003de34  mov     cl, 1; unsigned __int8
0x18003de36  call    ?DnsShutdownInterfaceManagement@@YAXE@Z; DnsShutdownInterfaceManagement(uchar)
0x18003de3b  call    ?DnsShutdownTableManagement@@YAXXZ; DnsShutdownTableManagement(void)
0x18003de40  call    ?DnsShutdownFileManagement@@YAXXZ; DnsShutdownFileManagement(void)
0x18003de45  lea     rcx, ?DnsGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003de4c  call    cs:__imp_DeleteCriticalSection
0x18003de53  nop     dword ptr [rax+rax+00h]
0x18003de58  lea     rcx, ?g_csDnsServerListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003de5f  call    cs:__imp_DeleteCriticalSection
0x18003de66  nop     dword ptr [rax+rax+00h]
0x18003de6b  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x18003de72  call    ?DeleteComponentReference@@YAXPEAU_COMPONENT_REFERENCE@@@Z; DeleteComponentReference(_COMPONENT_REFERENCE *)
0x18003de77  mov     rcx, cs:WPP_GLOBAL_Control
0x18003de7e  cmp     rcx, rsi
0x18003de81  jz      short loc_18003DEA4
0x18003de83  test    byte ptr [rcx+1Ch], 10h
0x18003de87  jz      short loc_18003DEA4
0x18003de89  cmp     byte ptr [rcx+19h], 6
0x18003de8d  jb      short loc_18003DEA4
0x18003de8f  mov     rcx, [rcx+10h]
0x18003de93  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x18003de9a  mov     edx, 0Ch
0x18003de9f  call    WPP_SF_
0x18003dea4  mov     rbx, [rsp+28h+arg_0]
0x18003dea9  add     rsp, 20h
0x18003dead  pop     rsi
0x18003deae  retn
```
