# RasInterfaceMgmtUninit

- ea: `0x18009e18c`
- end: `0x18009e2aa`
- name: `RasInterfaceMgmtUninit`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000acb4`
- `0x18009e0c0`

## callees

- `0x18009dcfc`
- `0x18009e18c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009e1cf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009e1cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e203`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e23c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e271`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e203`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e23c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e271`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e1ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e224`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e259`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e1ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e224`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e259`
- `WINNSI!NsiDisconnectFromServer` at `0x18009e1a8`
- `WINNSI!NsiDisconnectFromServer` at `0x18009e1a8`

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
0x18009e18c  push    rbx
0x18009e18e  sub     rsp, 20h
0x18009e192  call    DeregisterInterfaceChangeNotifications
0x18009e197  call    DeregisterInterfaceChangeNotifications
0x18009e19c  mov     rcx, cs:g_hNsiRPCHandle
0x18009e1a3  test    rcx, rcx
0x18009e1a6  jz      short loc_18009E1BF
0x18009e1a8  call    cs:__imp_NsiDisconnectFromServer
0x18009e1af  nop     dword ptr [rax+rax+00h]
0x18009e1b4  mov     cs:g_hNsiRPCHandle, 0
0x18009e1bf  cmp     cs:g_fcsInterfaceCacheInitialized, 0
0x18009e1c6  jz      short loc_18009E20F
0x18009e1c8  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x18009e1cf  call    cs:__imp_DeleteCriticalSection
0x18009e1d6  nop     dword ptr [rax+rax+00h]
0x18009e1db  mov     cs:g_fcsInterfaceCacheInitialized, 0
0x18009e1e2  jmp     short loc_18009E20F
0x18009e1e4  mov     rax, [rbx+10h]
0x18009e1e8  mov     cs:g_RasVpnLuids, rax
0x18009e1ef  call    cs:__imp_GetProcessHeap
0x18009e1f6  nop     dword ptr [rax+rax+00h]
0x18009e1fb  mov     r8, rbx; lpMem
0x18009e1fe  xor     edx, edx; dwFlags
0x18009e200  mov     rcx, rax; hHeap
0x18009e203  call    cs:__imp_HeapFree
0x18009e20a  nop     dword ptr [rax+rax+00h]
0x18009e20f  mov     rbx, cs:g_RasVpnLuids
0x18009e216  test    rbx, rbx
0x18009e219  jnz     short loc_18009E1E4
0x18009e21b  cmp     cs:g_IpV4InterfaceTable, rbx
0x18009e222  jz      short loc_18009E24F
0x18009e224  call    cs:__imp_GetProcessHeap
0x18009e22b  nop     dword ptr [rax+rax+00h]
0x18009e230  mov     r8, cs:g_IpV4InterfaceTable; lpMem
0x18009e237  xor     edx, edx; dwFlags
0x18009e239  mov     rcx, rax; hHeap
0x18009e23c  call    cs:__imp_HeapFree
0x18009e243  nop     dword ptr [rax+rax+00h]
0x18009e248  mov     cs:g_IpV4InterfaceTable, rbx
0x18009e24f  cmp     cs:g_IpV6InterfaceTable, 0
0x18009e257  jz      short loc_18009E288
0x18009e259  call    cs:__imp_GetProcessHeap
0x18009e260  nop     dword ptr [rax+rax+00h]
0x18009e265  mov     r8, cs:g_IpV6InterfaceTable; lpMem
0x18009e26c  xor     edx, edx; dwFlags
0x18009e26e  mov     rcx, rax; hHeap
0x18009e271  call    cs:__imp_HeapFree
0x18009e278  nop     dword ptr [rax+rax+00h]
0x18009e27d  mov     cs:g_IpV6InterfaceTable, 0
0x18009e288  mov     cs:g_NumVpnIpv4RouteTableChanges, 0
0x18009e292  mov     cs:g_NumVpnIpv6RouteTableChanges, 0
0x18009e29c  mov     cs:g_Initialized, 0
0x18009e2a3  add     rsp, 20h
0x18009e2a7  pop     rbx
0x18009e2a8  retn
```
