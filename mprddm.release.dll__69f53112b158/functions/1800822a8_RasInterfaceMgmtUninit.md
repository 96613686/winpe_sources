# RasInterfaceMgmtUninit

- ea: `0x1800822a8`
- end: `0x1800823ba`
- name: `RasInterfaceMgmtUninit`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800205b0`
- `0x1800821e0`

## callees

- `0x180081e24`
- `0x1800822a8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800822e8`
- `KERNEL32!DeleteCriticalSection` at `0x1800822e8`
- `KERNEL32!GetProcessHeap` at `0x180082308`
- `KERNEL32!GetProcessHeap` at `0x18008233d`
- `KERNEL32!GetProcessHeap` at `0x180082372`
- `KERNEL32!GetProcessHeap` at `0x180082308`
- `KERNEL32!GetProcessHeap` at `0x18008233d`
- `KERNEL32!GetProcessHeap` at `0x180082372`
- `KERNEL32!HeapFree` at `0x18008231c`
- `KERNEL32!HeapFree` at `0x180082355`
- `KERNEL32!HeapFree` at `0x18008238a`
- `KERNEL32!HeapFree` at `0x18008231c`
- `KERNEL32!HeapFree` at `0x180082355`
- `KERNEL32!HeapFree` at `0x18008238a`
- `WINNSI!NsiDisconnectFromServer` at `0x1800822c4`
- `WINNSI!NsiDisconnectFromServer` at `0x1800822c4`

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
0x1800822a8  push    rbx
0x1800822aa  sub     rsp, 20h
0x1800822ae  call    DeregisterInterfaceChangeNotifications
0x1800822b3  call    DeregisterInterfaceChangeNotifications
0x1800822b8  mov     rcx, cs:g_hNsiRPCHandle
0x1800822bf  test    rcx, rcx
0x1800822c2  jz      short loc_1800822D8
0x1800822c4  call    cs:__imp_NsiDisconnectFromServer
0x1800822cb  nop     dword ptr [rax+rax+00h]
0x1800822d0  and     cs:g_hNsiRPCHandle, 0
0x1800822d8  cmp     cs:g_fcsInterfaceCacheInitialized, 0
0x1800822df  jz      short loc_180082328
0x1800822e1  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x1800822e8  call    cs:__imp_DeleteCriticalSection
0x1800822ef  nop     dword ptr [rax+rax+00h]
0x1800822f4  mov     cs:g_fcsInterfaceCacheInitialized, 0
0x1800822fb  jmp     short loc_180082328
0x1800822fd  mov     rax, [rbx+10h]
0x180082301  mov     cs:g_RasVpnLuids, rax
0x180082308  call    cs:__imp_GetProcessHeap
0x18008230f  nop     dword ptr [rax+rax+00h]
0x180082314  mov     r8, rbx; lpMem
0x180082317  xor     edx, edx; dwFlags
0x180082319  mov     rcx, rax; hHeap
0x18008231c  call    cs:__imp_HeapFree
0x180082323  nop     dword ptr [rax+rax+00h]
0x180082328  mov     rbx, cs:g_RasVpnLuids
0x18008232f  test    rbx, rbx
0x180082332  jnz     short loc_1800822FD
0x180082334  cmp     cs:g_IpV4InterfaceTable, rbx
0x18008233b  jz      short loc_180082368
0x18008233d  call    cs:__imp_GetProcessHeap
0x180082344  nop     dword ptr [rax+rax+00h]
0x180082349  mov     r8, cs:g_IpV4InterfaceTable; lpMem
0x180082350  xor     edx, edx; dwFlags
0x180082352  mov     rcx, rax; hHeap
0x180082355  call    cs:__imp_HeapFree
0x18008235c  nop     dword ptr [rax+rax+00h]
0x180082361  and     cs:g_IpV4InterfaceTable, rbx
0x180082368  cmp     cs:g_IpV6InterfaceTable, 0
0x180082370  jz      short loc_18008239E
0x180082372  call    cs:__imp_GetProcessHeap
0x180082379  nop     dword ptr [rax+rax+00h]
0x18008237e  mov     r8, cs:g_IpV6InterfaceTable; lpMem
0x180082385  xor     edx, edx; dwFlags
0x180082387  mov     rcx, rax; hHeap
0x18008238a  call    cs:__imp_HeapFree
0x180082391  nop     dword ptr [rax+rax+00h]
0x180082396  and     cs:g_IpV6InterfaceTable, 0
0x18008239e  and     cs:g_NumVpnIpv4RouteTableChanges, 0
0x1800823a5  and     cs:g_NumVpnIpv6RouteTableChanges, 0
0x1800823ac  mov     cs:g_Initialized, 0
0x1800823b3  add     rsp, 20h
0x1800823b7  pop     rbx
0x1800823b8  retn
```
