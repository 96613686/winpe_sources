# RasInterfaceMgmtUninit

- ea: `0x1800990cc`
- end: `0x1800991b9`
- name: `RasInterfaceMgmtUninit`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000aa60`
- `0x180099010`

## callees

- `0x180098c64`
- `0x1800990cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180099109`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180099109`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099131`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009915e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099187`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099131`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009915e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099187`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099123`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009914c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099175`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099123`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009914c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099175`
- `WINNSI!NsiDisconnectFromServer` at `0x1800990e8`
- `WINNSI!NsiDisconnectFromServer` at `0x1800990e8`

## pseudocode

```c
void RasInterfaceMgmtUninit()
{
  HANDLE ProcessHeap; // rax
  void *v1; // rbx
  HANDLE v2; // rax
  HANDLE v3; // rax

  DeregisterInterfaceChangeNotifications();
  DeregisterInterfaceChangeNotifications();
  if ( g_hNsiRPCHandle )
  {
    NsiDisconnectFromServer();
    g_hNsiRPCHandle = 0;
  }
  if ( g_fcsInterfaceCacheInitialized )
  {
    DeleteCriticalSection(&g_csInterfaceCache);
    g_fcsInterfaceCacheInitialized = 0;
  }
  while ( 1 )
  {
    v1 = g_RasVpnLuids;
    if ( !g_RasVpnLuids )
      break;
    g_RasVpnLuids = (LPVOID)*((_QWORD *)g_RasVpnLuids + 2);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
  if ( g_IpV4InterfaceTable )
  {
    v2 = GetProcessHeap();
    HeapFree(v2, 0, g_IpV4InterfaceTable);
    g_IpV4InterfaceTable = 0;
  }
  if ( g_IpV6InterfaceTable )
  {
    v3 = GetProcessHeap();
    HeapFree(v3, 0, g_IpV6InterfaceTable);
    g_IpV6InterfaceTable = 0;
  }
  g_NumVpnIpv4RouteTableChanges = 0;
  g_NumVpnIpv6RouteTableChanges = 0;
  g_Initialized = 0;
}

```

## disassembly

```asm
0x1800990cc  push    rbx
0x1800990ce  sub     rsp, 20h
0x1800990d2  call    DeregisterInterfaceChangeNotifications
0x1800990d7  call    DeregisterInterfaceChangeNotifications
0x1800990dc  mov     rcx, cs:g_hNsiRPCHandle
0x1800990e3  test    rcx, rcx
0x1800990e6  jz      short loc_1800990F9
0x1800990e8  call    cs:__imp_NsiDisconnectFromServer
0x1800990ee  mov     cs:g_hNsiRPCHandle, 0
0x1800990f9  cmp     cs:g_fcsInterfaceCacheInitialized, 0
0x180099100  jz      short loc_180099137
0x180099102  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x180099109  call    cs:__imp_DeleteCriticalSection
0x18009910f  mov     cs:g_fcsInterfaceCacheInitialized, 0
0x180099116  jmp     short loc_180099137
0x180099118  mov     rax, [rbx+10h]
0x18009911c  mov     cs:g_RasVpnLuids, rax
0x180099123  call    cs:__imp_GetProcessHeap
0x180099129  mov     r8, rbx; lpMem
0x18009912c  xor     edx, edx; dwFlags
0x18009912e  mov     rcx, rax; hHeap
0x180099131  call    cs:__imp_HeapFree
0x180099137  mov     rbx, cs:g_RasVpnLuids
0x18009913e  test    rbx, rbx
0x180099141  jnz     short loc_180099118
0x180099143  cmp     cs:g_IpV4InterfaceTable, rbx
0x18009914a  jz      short loc_18009916B
0x18009914c  call    cs:__imp_GetProcessHeap
0x180099152  mov     r8, cs:g_IpV4InterfaceTable; lpMem
0x180099159  xor     edx, edx; dwFlags
0x18009915b  mov     rcx, rax; hHeap
0x18009915e  call    cs:__imp_HeapFree
0x180099164  mov     cs:g_IpV4InterfaceTable, rbx
0x18009916b  cmp     cs:g_IpV6InterfaceTable, 0
0x180099173  jz      short loc_180099198
0x180099175  call    cs:__imp_GetProcessHeap
0x18009917b  mov     r8, cs:g_IpV6InterfaceTable; lpMem
0x180099182  xor     edx, edx; dwFlags
0x180099184  mov     rcx, rax; hHeap
0x180099187  call    cs:__imp_HeapFree
0x18009918d  mov     cs:g_IpV6InterfaceTable, 0
0x180099198  mov     cs:g_NumVpnIpv4RouteTableChanges, 0
0x1800991a2  mov     cs:g_NumVpnIpv6RouteTableChanges, 0
0x1800991ac  mov     cs:g_Initialized, 0
0x1800991b3  add     rsp, 20h
0x1800991b7  pop     rbx
0x1800991b8  retn
```
