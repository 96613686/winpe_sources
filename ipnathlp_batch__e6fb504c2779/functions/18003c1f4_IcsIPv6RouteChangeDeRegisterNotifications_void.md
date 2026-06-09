# IcsIPv6RouteChangeDeRegisterNotifications(void)

- ea: `0x18003c1f4`
- end: `0x18003c326`
- name: `?IcsIPv6RouteChangeDeRegisterNotifications@@YAKXZ`
- size: `306`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18003ba60`
- `0x180077550`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18003c1f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c23b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c23b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c2dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c2dc`
- `WINNSI!NsiDisconnectFromServer` at `0x18003c2be`
- `WINNSI!NsiDisconnectFromServer` at `0x18003c2be`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18003c265`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18003c265`

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
0x18003c1f4  mov     [rsp+arg_0], rbx
0x18003c1f9  push    rsi
0x18003c1fa  sub     rsp, 20h
0x18003c1fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c205  lea     rsi, WPP_GLOBAL_Control
0x18003c20c  cmp     rcx, rsi
0x18003c20f  jz      short loc_18003C232
0x18003c211  test    byte ptr [rcx+1Ch], 80h
0x18003c215  jz      short loc_18003C232
0x18003c217  cmp     byte ptr [rcx+19h], 6
0x18003c21b  jb      short loc_18003C232
0x18003c21d  mov     rcx, [rcx+10h]
0x18003c221  lea     r8, WPP_c678c027e5b43e0680680faed04d78a8_Traceguids
0x18003c228  mov     edx, 19h
0x18003c22d  call    WPP_SF_
0x18003c232  lea     rcx, ?IPv6RouteChangeNotifyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003c239  xor     ebx, ebx
0x18003c23b  call    cs:__imp_EnterCriticalSection
0x18003c242  nop     dword ptr [rax+rax+00h]
0x18003c247  mov     r9, cs:?g_ICSRouteChangeNotificationHandle@@3PEAXEA; void * g_ICSRouteChangeNotificationHandle
0x18003c24e  test    r9, r9
0x18003c251  jz      short loc_18003C2B2
0x18003c253  mov     rcx, cs:?g_ICSRouteChangeRpcHandle@@3PEAXEA; void * g_ICSRouteChangeRpcHandle
0x18003c25a  lea     r8d, [rbx+10h]
0x18003c25e  lea     rdx, NPI_MS_IPV6_MODULEID
0x18003c265  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18003c26c  nop     dword ptr [rax+rax+00h]
0x18003c271  mov     ebx, eax
0x18003c273  test    eax, eax
0x18003c275  jz      short loc_18003C2A7
0x18003c277  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c27e  cmp     rcx, rsi
0x18003c281  jz      short loc_18003C2A7
0x18003c283  test    byte ptr [rcx+1Ch], 80h
0x18003c287  jz      short loc_18003C2A7
0x18003c289  cmp     byte ptr [rcx+19h], 2
0x18003c28d  jb      short loc_18003C2A7
0x18003c28f  mov     rcx, [rcx+10h]
0x18003c293  lea     r8, WPP_c678c027e5b43e0680680faed04d78a8_Traceguids
0x18003c29a  mov     edx, 1Ah
0x18003c29f  mov     r9d, eax
0x18003c2a2  call    WPP_SF_d
0x18003c2a7  mov     cs:?g_ICSRouteChangeNotificationHandle@@3PEAXEA, 0; void * g_ICSRouteChangeNotificationHandle
0x18003c2b2  mov     rcx, cs:?g_ICSRouteChangeRpcHandle@@3PEAXEA; void * g_ICSRouteChangeRpcHandle
0x18003c2b9  test    rcx, rcx
0x18003c2bc  jz      short loc_18003C2D5
0x18003c2be  call    cs:__imp_NsiDisconnectFromServer
0x18003c2c5  nop     dword ptr [rax+rax+00h]
0x18003c2ca  mov     cs:?g_ICSRouteChangeRpcHandle@@3PEAXEA, 0; void * g_ICSRouteChangeRpcHandle
0x18003c2d5  lea     rcx, ?IPv6RouteChangeNotifyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003c2dc  call    cs:__imp_LeaveCriticalSection
0x18003c2e3  nop     dword ptr [rax+rax+00h]
0x18003c2e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c2ef  cmp     rcx, rsi
0x18003c2f2  jz      short loc_18003C318
0x18003c2f4  test    byte ptr [rcx+1Ch], 80h
0x18003c2f8  jz      short loc_18003C318
0x18003c2fa  cmp     byte ptr [rcx+19h], 6
0x18003c2fe  jb      short loc_18003C318
0x18003c300  mov     rcx, [rcx+10h]
0x18003c304  lea     r8, WPP_c678c027e5b43e0680680faed04d78a8_Traceguids
0x18003c30b  mov     edx, 1Bh
0x18003c310  mov     r9d, ebx
0x18003c313  call    WPP_SF_d
0x18003c318  mov     eax, ebx
0x18003c31a  mov     rbx, [rsp+28h+arg_0]
0x18003c31f  add     rsp, 20h
0x18003c323  pop     rsi
0x18003c324  retn
```
