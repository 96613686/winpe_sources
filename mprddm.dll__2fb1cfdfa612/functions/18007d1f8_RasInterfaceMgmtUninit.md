# RasInterfaceMgmtUninit

- ea: `0x18007d1f8`
- end: `0x18007d2e5`
- name: `RasInterfaceMgmtUninit`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001f8e0`
- `0x18007d140`

## callees

- `0x18007cd94`
- `0x18007d1f8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18007d235`
- `KERNEL32!DeleteCriticalSection` at `0x18007d235`
- `KERNEL32!GetProcessHeap` at `0x18007d24f`
- `KERNEL32!GetProcessHeap` at `0x18007d278`
- `KERNEL32!GetProcessHeap` at `0x18007d2a1`
- `KERNEL32!GetProcessHeap` at `0x18007d24f`
- `KERNEL32!GetProcessHeap` at `0x18007d278`
- `KERNEL32!GetProcessHeap` at `0x18007d2a1`
- `KERNEL32!HeapFree` at `0x18007d25d`
- `KERNEL32!HeapFree` at `0x18007d28a`
- `KERNEL32!HeapFree` at `0x18007d2b3`
- `KERNEL32!HeapFree` at `0x18007d25d`
- `KERNEL32!HeapFree` at `0x18007d28a`
- `KERNEL32!HeapFree` at `0x18007d2b3`
- `WINNSI!NsiDisconnectFromServer` at `0x18007d214`
- `WINNSI!NsiDisconnectFromServer` at `0x18007d214`

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
0x18007d1f8  push    rbx
0x18007d1fa  sub     rsp, 20h
0x18007d1fe  call    DeregisterInterfaceChangeNotifications
0x18007d203  call    DeregisterInterfaceChangeNotifications
0x18007d208  mov     rcx, cs:g_hNsiRPCHandle
0x18007d20f  test    rcx, rcx
0x18007d212  jz      short loc_18007D225
0x18007d214  call    cs:__imp_NsiDisconnectFromServer
0x18007d21a  mov     cs:g_hNsiRPCHandle, 0
0x18007d225  cmp     cs:g_fcsInterfaceCacheInitialized, 0
0x18007d22c  jz      short loc_18007D263
0x18007d22e  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x18007d235  call    cs:__imp_DeleteCriticalSection
0x18007d23b  mov     cs:g_fcsInterfaceCacheInitialized, 0
0x18007d242  jmp     short loc_18007D263
0x18007d244  mov     rax, [rbx+10h]
0x18007d248  mov     cs:g_RasVpnLuids, rax
0x18007d24f  call    cs:__imp_GetProcessHeap
0x18007d255  mov     r8, rbx; lpMem
0x18007d258  xor     edx, edx; dwFlags
0x18007d25a  mov     rcx, rax; hHeap
0x18007d25d  call    cs:__imp_HeapFree
0x18007d263  mov     rbx, cs:g_RasVpnLuids
0x18007d26a  test    rbx, rbx
0x18007d26d  jnz     short loc_18007D244
0x18007d26f  cmp     cs:g_IpV4InterfaceTable, rbx
0x18007d276  jz      short loc_18007D297
0x18007d278  call    cs:__imp_GetProcessHeap
0x18007d27e  mov     r8, cs:g_IpV4InterfaceTable; lpMem
0x18007d285  xor     edx, edx; dwFlags
0x18007d287  mov     rcx, rax; hHeap
0x18007d28a  call    cs:__imp_HeapFree
0x18007d290  mov     cs:g_IpV4InterfaceTable, rbx
0x18007d297  cmp     cs:g_IpV6InterfaceTable, 0
0x18007d29f  jz      short loc_18007D2C4
0x18007d2a1  call    cs:__imp_GetProcessHeap
0x18007d2a7  mov     r8, cs:g_IpV6InterfaceTable; lpMem
0x18007d2ae  xor     edx, edx; dwFlags
0x18007d2b0  mov     rcx, rax; hHeap
0x18007d2b3  call    cs:__imp_HeapFree
0x18007d2b9  mov     cs:g_IpV6InterfaceTable, 0
0x18007d2c4  mov     cs:g_NumVpnIpv4RouteTableChanges, 0
0x18007d2ce  mov     cs:g_NumVpnIpv6RouteTableChanges, 0
0x18007d2d8  mov     cs:g_Initialized, 0
0x18007d2df  add     rsp, 20h
0x18007d2e3  pop     rbx
0x18007d2e4  retn
```
