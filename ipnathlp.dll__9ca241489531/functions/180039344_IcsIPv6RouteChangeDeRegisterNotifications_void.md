# IcsIPv6RouteChangeDeRegisterNotifications(void)

- ea: `0x180039344`
- end: `0x18003945d`
- name: `?IcsIPv6RouteChangeDeRegisterNotifications@@YAKXZ`
- size: `281`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180038be4`
- `0x180071ac4`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180039344`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003938b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003938b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003941a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003941a`
- `WINNSI!NsiDisconnectFromServer` at `0x180039402`
- `WINNSI!NsiDisconnectFromServer` at `0x180039402`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x1800393af`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x1800393af`

## pseudocode

```c
__int64 IcsIPv6RouteChangeDeRegisterNotifications(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_c678c027e5b43e0680680faed04d78a8_Traceguids);
  }
  v0 = 0;
  EnterCriticalSection(&IPv6RouteChangeNotifyLock);
  if ( g_ICSRouteChangeNotificationHandle )
  {
    v1 = NsiRpcDeregisterChangeNotification(
           g_ICSRouteChangeRpcHandle,
           &NPI_MS_IPV6_MODULEID,
           16,
           g_ICSRouteChangeNotificationHandle);
    v0 = v1;
    if ( v1
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_c678c027e5b43e0680680faed04d78a8_Traceguids, v1);
    }
    g_ICSRouteChangeNotificationHandle = 0;
  }
  if ( g_ICSRouteChangeRpcHandle )
  {
    NsiDisconnectFromServer(g_ICSRouteChangeRpcHandle);
    g_ICSRouteChangeRpcHandle = 0;
  }
  LeaveCriticalSection(&IPv6RouteChangeNotifyLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_c678c027e5b43e0680680faed04d78a8_Traceguids, v0);
  }
  return v0;
}

```

## disassembly

```asm
0x180039344  mov     [rsp+arg_0], rbx
0x180039349  push    rsi
0x18003934a  sub     rsp, 20h
0x18003934e  mov     rcx, cs:WPP_GLOBAL_Control
0x180039355  lea     rsi, WPP_GLOBAL_Control
0x18003935c  cmp     rcx, rsi
0x18003935f  jz      short loc_180039382
0x180039361  test    byte ptr [rcx+1Ch], 80h
0x180039365  jz      short loc_180039382
0x180039367  cmp     byte ptr [rcx+19h], 6
0x18003936b  jb      short loc_180039382
0x18003936d  mov     rcx, [rcx+10h]
0x180039371  lea     r8, WPP_c678c027e5b43e0680680faed04d78a8_Traceguids
0x180039378  mov     edx, 19h
0x18003937d  call    WPP_SF_
0x180039382  lea     rcx, ?IPv6RouteChangeNotifyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180039389  xor     ebx, ebx
0x18003938b  call    cs:__imp_EnterCriticalSection
0x180039391  mov     r9, cs:?g_ICSRouteChangeNotificationHandle@@3PEAXEA; void * g_ICSRouteChangeNotificationHandle
0x180039398  test    r9, r9
0x18003939b  jz      short loc_1800393F6
0x18003939d  mov     rcx, cs:?g_ICSRouteChangeRpcHandle@@3PEAXEA; void * g_ICSRouteChangeRpcHandle
0x1800393a4  lea     r8d, [rbx+10h]
0x1800393a8  lea     rdx, NPI_MS_IPV6_MODULEID
0x1800393af  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x1800393b5  mov     ebx, eax
0x1800393b7  test    eax, eax
0x1800393b9  jz      short loc_1800393EB
0x1800393bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800393c2  cmp     rcx, rsi
0x1800393c5  jz      short loc_1800393EB
0x1800393c7  test    byte ptr [rcx+1Ch], 80h
0x1800393cb  jz      short loc_1800393EB
0x1800393cd  cmp     byte ptr [rcx+19h], 2
0x1800393d1  jb      short loc_1800393EB
0x1800393d3  mov     rcx, [rcx+10h]
0x1800393d7  lea     r8, WPP_c678c027e5b43e0680680faed04d78a8_Traceguids
0x1800393de  mov     edx, 1Ah
0x1800393e3  mov     r9d, eax
0x1800393e6  call    WPP_SF_d
0x1800393eb  mov     cs:?g_ICSRouteChangeNotificationHandle@@3PEAXEA, 0; void * g_ICSRouteChangeNotificationHandle
0x1800393f6  mov     rcx, cs:?g_ICSRouteChangeRpcHandle@@3PEAXEA; void * g_ICSRouteChangeRpcHandle
0x1800393fd  test    rcx, rcx
0x180039400  jz      short loc_180039413
0x180039402  call    cs:__imp_NsiDisconnectFromServer
0x180039408  mov     cs:?g_ICSRouteChangeRpcHandle@@3PEAXEA, 0; void * g_ICSRouteChangeRpcHandle
0x180039413  lea     rcx, ?IPv6RouteChangeNotifyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003941a  call    cs:__imp_LeaveCriticalSection
0x180039420  mov     rcx, cs:WPP_GLOBAL_Control
0x180039427  cmp     rcx, rsi
0x18003942a  jz      short loc_180039450
0x18003942c  test    byte ptr [rcx+1Ch], 80h
0x180039430  jz      short loc_180039450
0x180039432  cmp     byte ptr [rcx+19h], 6
0x180039436  jb      short loc_180039450
0x180039438  mov     rcx, [rcx+10h]
0x18003943c  lea     r8, WPP_c678c027e5b43e0680680faed04d78a8_Traceguids
0x180039443  mov     edx, 1Bh
0x180039448  mov     r9d, ebx
0x18003944b  call    WPP_SF_d
0x180039450  mov     eax, ebx
0x180039452  mov     rbx, [rsp+28h+arg_0]
0x180039457  add     rsp, 20h
0x18003945b  pop     rsi
0x18003945c  retn
```
