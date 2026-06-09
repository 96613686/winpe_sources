# DhcpShutdownInterfaceManagement(uchar)

- ea: `0x1800598f4`
- end: `0x180059a5d`
- name: `?DhcpShutdownInterfaceManagement@@YAXE@Z`
- size: `361`
- prototype: `void __fastcall(char)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18003eee0`
- `0x180057b10`

## callees

- `0x18000c110`
- `0x18000fc04`
- `0x18002c9e4`
- `0x1800598f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059947`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800599f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059947`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800599f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800599ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800599e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059a09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800599ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800599e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059a09`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180059a17`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180059a17`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800599ee`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800599ee`

## pseudocode

```c
void __fastcall DhcpShutdownInterfaceManagement(char a1)
{
  struct _DHCP_INTERFACE *v2; // rbx
  __int64 v3; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids);
  }
  EnterCriticalSection(&DhcpInterfaceLock);
  while ( 1 )
  {
    v2 = DhcpInterfaceList;
    if ( DhcpInterfaceList == (struct _DHCP_INTERFACE *)&DhcpInterfaceList )
      break;
    if ( *((struct _DHCP_INTERFACE ***)DhcpInterfaceList + 1) != &DhcpInterfaceList
      || (v3 = *(_QWORD *)DhcpInterfaceList,
          *(struct _DHCP_INTERFACE **)(*(_QWORD *)DhcpInterfaceList + 8LL) != DhcpInterfaceList) )
    {
      __fastfail(3u);
    }
    DhcpInterfaceList = *(struct _DHCP_INTERFACE **)DhcpInterfaceList;
    *(_QWORD *)(v3 + 8) = &DhcpInterfaceList;
    if ( (*((_DWORD *)v2 + 19) & 0x60000000) == 0x60000000 )
      DhcpDeactivateInterface(v2);
    if ( (*((_DWORD *)v2 + 14))-- == 1 )
      DhcpCleanupInterface(v2);
  }
  LeaveCriticalSection(&DhcpInterfaceLock);
  while ( 1 )
  {
    EnterCriticalSection(&DhcpInterfaceLock);
    if ( DhcpInterfaceCount <= 0 )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids);
    }
    LeaveCriticalSection(&DhcpInterfaceLock);
    Sleep(0x1F4u);
  }
  LeaveCriticalSection(&DhcpInterfaceLock);
  if ( a1 )
    DeleteCriticalSection(&DhcpInterfaceLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids);
  }
}

```

## disassembly

```asm
0x1800598f4  mov     [rsp+arg_0], rbx
0x1800598f9  mov     [rsp+arg_10], rbp
0x1800598fe  push    rsi
0x1800598ff  push    rdi
0x180059900  push    r14
0x180059902  sub     rsp, 20h
0x180059906  mov     dil, cl
0x180059909  mov     rcx, cs:WPP_GLOBAL_Control
0x180059910  lea     r14, WPP_GLOBAL_Control
0x180059917  cmp     rcx, r14
0x18005991a  jz      short loc_18005993D
0x18005991c  test    byte ptr [rcx+1Ch], 2
0x180059920  jz      short loc_18005993D
0x180059922  cmp     byte ptr [rcx+19h], 6
0x180059926  jb      short loc_18005993D
0x180059928  mov     rcx, [rcx+10h]
0x18005992c  lea     r8, WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids
0x180059933  mov     edx, 7Dh ; '}'
0x180059938  call    WPP_SF_
0x18005993d  lea     rsi, ?DhcpInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION DhcpInterfaceLock
0x180059944  mov     rcx, rsi; lpCriticalSection
0x180059947  call    cs:__imp_EnterCriticalSection
0x18005994d  lea     rbp, ?DhcpInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DhcpInterfaceList
0x180059954  mov     rbx, cs:?DhcpInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DhcpInterfaceList
0x18005995b  cmp     rbx, rbp
0x18005995e  jz      short loc_1800599A8
0x180059960  cmp     [rbx+8], rbp
0x180059964  jnz     short loc_1800599A1
0x180059966  mov     rax, [rbx]
0x180059969  cmp     [rax+8], rbx
0x18005996d  jnz     short loc_1800599A1
0x18005996f  mov     cs:?DhcpInterfaceList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY DhcpInterfaceList
0x180059976  mov     [rax+8], rbp
0x18005997a  mov     eax, [rbx+4Ch]
0x18005997d  and     eax, 60000000h
0x180059982  cmp     eax, 60000000h
0x180059987  jnz     short loc_180059991
0x180059989  mov     rcx, rbx; struct _DHCP_INTERFACE *
0x18005998c  call    ?DhcpDeactivateInterface@@YAXPEAU_DHCP_INTERFACE@@@Z; DhcpDeactivateInterface(_DHCP_INTERFACE *)
0x180059991  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x180059995  jnz     short loc_180059954
0x180059997  mov     rcx, rbx; lpMem
0x18005999a  call    ?DhcpCleanupInterface@@YAXPEAU_DHCP_INTERFACE@@@Z; DhcpCleanupInterface(_DHCP_INTERFACE *)
0x18005999f  jmp     short loc_180059954
0x1800599a1  mov     ecx, 3
0x1800599a6  int     29h; Win8: RtlFailFast(ecx)
0x1800599a8  mov     rcx, rsi; lpCriticalSection
0x1800599ab  call    cs:__imp_LeaveCriticalSection
0x1800599b1  jmp     short loc_1800599F4
0x1800599b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800599ba  cmp     rcx, r14
0x1800599bd  jz      short loc_1800599E0
0x1800599bf  test    byte ptr [rcx+1Ch], 10h
0x1800599c3  jz      short loc_1800599E0
0x1800599c5  cmp     byte ptr [rcx+19h], 5
0x1800599c9  jb      short loc_1800599E0
0x1800599cb  mov     rcx, [rcx+10h]
0x1800599cf  lea     r8, WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids
0x1800599d6  mov     edx, 7Eh ; '~'
0x1800599db  call    WPP_SF_
0x1800599e0  mov     rcx, rsi; lpCriticalSection
0x1800599e3  call    cs:__imp_LeaveCriticalSection
0x1800599e9  mov     ecx, 1F4h; dwMilliseconds
0x1800599ee  call    cs:__imp_Sleep
0x1800599f4  mov     rcx, rsi; lpCriticalSection
0x1800599f7  call    cs:__imp_EnterCriticalSection
0x1800599fd  cmp     cs:?DhcpInterfaceCount@@3JA, 0; long DhcpInterfaceCount
0x180059a04  jg      short loc_1800599B3
0x180059a06  mov     rcx, rsi; lpCriticalSection
0x180059a09  call    cs:__imp_LeaveCriticalSection
0x180059a0f  test    dil, dil
0x180059a12  jz      short loc_180059A1D
0x180059a14  mov     rcx, rsi; lpCriticalSection
0x180059a17  call    cs:__imp_DeleteCriticalSection
0x180059a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180059a24  cmp     rcx, r14
0x180059a27  jz      short loc_180059A4A
0x180059a29  test    byte ptr [rcx+1Ch], 2
0x180059a2d  jz      short loc_180059A4A
0x180059a2f  cmp     byte ptr [rcx+19h], 6
0x180059a33  jb      short loc_180059A4A
0x180059a35  mov     rcx, [rcx+10h]
0x180059a39  lea     r8, WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids
0x180059a40  mov     edx, 7Fh
0x180059a45  call    WPP_SF_
0x180059a4a  mov     rbx, [rsp+38h+arg_0]
0x180059a4f  mov     rbp, [rsp+38h+arg_10]
0x180059a54  add     rsp, 20h
0x180059a58  pop     r14
0x180059a5a  pop     rdi
0x180059a5b  pop     rsi
0x180059a5c  retn
```
