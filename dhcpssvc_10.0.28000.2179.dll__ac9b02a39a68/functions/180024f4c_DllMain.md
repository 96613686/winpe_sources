# DllMain

- ea: `0x180024f4c`
- end: `0x180025091`
- name: `DllMain`
- size: `325`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001424`

## callees

- `0x18000282c`
- `0x180024f4c`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x180024fc8`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180024fc8`
- `KERNEL32!GetProcessHeap` at `0x180024f5e`
- `KERNEL32!GetProcessHeap` at `0x180024f5e`
- `KERNEL32!DeleteCriticalSection` at `0x180025056`
- `KERNEL32!DeleteCriticalSection` at `0x180025069`
- `KERNEL32!DeleteCriticalSection` at `0x18002507c`
- `KERNEL32!DeleteCriticalSection` at `0x180025056`
- `KERNEL32!DeleteCriticalSection` at `0x180025069`
- `KERNEL32!DeleteCriticalSection` at `0x18002507c`
- `KERNEL32!InitializeCriticalSection` at `0x180024fdb`
- `KERNEL32!InitializeCriticalSection` at `0x180024fee`
- `KERNEL32!InitializeCriticalSection` at `0x180025001`
- `KERNEL32!InitializeCriticalSection` at `0x180024fdb`
- `KERNEL32!InitializeCriticalSection` at `0x180024fee`
- `KERNEL32!InitializeCriticalSection` at `0x180025001`
- `KERNEL32!GetLastError` at `0x180024f76`
- `KERNEL32!GetLastError` at `0x180024f76`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL result; // eax

  if ( fdwReason == 1 )
  {
    gDhcpHeap = GetProcessHeap();
    if ( !gDhcpHeap )
    {
      result = GetLastError();
      if ( result )
      {
        LOBYTE(result) = 0;
        return result;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        108,
        &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids,
        (unsigned int)DhcpGlobalDataRefCount);
    DisableThreadLibraryCalls(hinstDLL);
    InitializeCriticalSection(&DhcpV6GlobalEndPointCS);
    InitializeCriticalSection(&DhcpGlobalEndPointCS);
    InitializeCriticalSection(&DhcpGlobalDebugFileCritSect);
  }
  else if ( !fdwReason && !lpvReserved )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        109,
        &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids,
        (unsigned int)DhcpGlobalDataRefCount);
    DeleteCriticalSection(&DhcpV6GlobalEndPointCS);
    DeleteCriticalSection(&DhcpGlobalEndPointCS);
    DeleteCriticalSection(&DhcpGlobalDebugFileCritSect);
  }
  LOBYTE(result) = 1;
  return result;
}

```

## disassembly

```asm
0x180024f4c  push    rbx
0x180024f4e  sub     rsp, 20h
0x180024f52  mov     rbx, rcx
0x180024f55  cmp     edx, 1
0x180024f58  jnz     loc_18002500F
0x180024f5e  call    cs:__imp_GetProcessHeap
0x180024f65  nop     dword ptr [rax+rax+00h]
0x180024f6a  mov     cs:gDhcpHeap, rax
0x180024f71  test    rax, rax
0x180024f74  jnz     short loc_180024F8D
0x180024f76  call    cs:__imp_GetLastError
0x180024f7d  nop     dword ptr [rax+rax+00h]
0x180024f82  test    eax, eax
0x180024f84  jz      short loc_180024F8D
0x180024f86  xor     al, al
0x180024f88  jmp     loc_18002508A
0x180024f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f94  lea     rax, WPP_GLOBAL_Control
0x180024f9b  cmp     rcx, rax
0x180024f9e  jz      short loc_180024FC5
0x180024fa0  test    dword ptr [rcx+1Ch], 8000h
0x180024fa7  jz      short loc_180024FC5
0x180024fa9  mov     r9d, cs:DhcpGlobalDataRefCount
0x180024fb0  lea     r8, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x180024fb7  mov     rcx, [rcx+10h]
0x180024fbb  mov     edx, 6Ch ; 'l'
0x180024fc0  call    WPP_SF_D
0x180024fc5  mov     rcx, rbx; hLibModule
0x180024fc8  call    cs:__imp_DisableThreadLibraryCalls
0x180024fcf  nop     dword ptr [rax+rax+00h]
0x180024fd4  lea     rcx, DhcpV6GlobalEndPointCS; lpCriticalSection
0x180024fdb  call    cs:__imp_InitializeCriticalSection
0x180024fe2  nop     dword ptr [rax+rax+00h]
0x180024fe7  lea     rcx, DhcpGlobalEndPointCS; lpCriticalSection
0x180024fee  call    cs:__imp_InitializeCriticalSection
0x180024ff5  nop     dword ptr [rax+rax+00h]
0x180024ffa  lea     rcx, DhcpGlobalDebugFileCritSect; lpCriticalSection
0x180025001  call    cs:__imp_InitializeCriticalSection
0x180025008  nop     dword ptr [rax+rax+00h]
0x18002500d  jmp     short loc_180025088
0x18002500f  test    edx, edx
0x180025011  jnz     short loc_180025088
0x180025013  test    r8, r8
0x180025016  jnz     short loc_180025088
0x180025018  mov     rcx, cs:WPP_GLOBAL_Control
0x18002501f  lea     rax, WPP_GLOBAL_Control
0x180025026  cmp     rcx, rax
0x180025029  jz      short loc_18002504F
0x18002502b  test    dword ptr [rcx+1Ch], 8000h
0x180025032  jz      short loc_18002504F
0x180025034  mov     r9d, cs:DhcpGlobalDataRefCount
0x18002503b  lea     edx, [r8+6Dh]
0x18002503f  mov     rcx, [rcx+10h]
0x180025043  lea     r8, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x18002504a  call    WPP_SF_D
0x18002504f  lea     rcx, DhcpV6GlobalEndPointCS; lpCriticalSection
0x180025056  call    cs:__imp_DeleteCriticalSection
0x18002505d  nop     dword ptr [rax+rax+00h]
0x180025062  lea     rcx, DhcpGlobalEndPointCS; lpCriticalSection
0x180025069  call    cs:__imp_DeleteCriticalSection
0x180025070  nop     dword ptr [rax+rax+00h]
0x180025075  lea     rcx, DhcpGlobalDebugFileCritSect; lpCriticalSection
0x18002507c  call    cs:__imp_DeleteCriticalSection
0x180025083  nop     dword ptr [rax+rax+00h]
0x180025088  mov     al, 1
0x18002508a  add     rsp, 20h
0x18002508e  pop     rbx
0x18002508f  retn
```
