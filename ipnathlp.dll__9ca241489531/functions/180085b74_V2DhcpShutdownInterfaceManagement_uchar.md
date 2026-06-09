# V2DhcpShutdownInterfaceManagement(uchar)

- ea: `0x180085b74`
- end: `0x180085cdd`
- name: `?V2DhcpShutdownInterfaceManagement@@YAXE@Z`
- size: `361`
- prototype: `void __fastcall(unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18003eee0`
- `0x1800843a4`

## callees

- `0x18000c110`
- `0x18003ebc0`
- `0x180084c54`
- `0x180085b74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085bc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085c77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085bc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085c77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085c2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085c63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085c89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085c2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085c63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085c89`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180085c97`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180085c97`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180085c6e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180085c6e`

## pseudocode

```c
void __fastcall V2DhcpShutdownInterfaceManagement(char a1)
{
  struct _V2_DHCP_INTERFACE *v2; // rbx
  __int64 v3; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids);
  }
  EnterCriticalSection(&V2DhcpInterfaceLock);
  while ( 1 )
  {
    v2 = V2DhcpInterfaceList;
    if ( V2DhcpInterfaceList == (struct _V2_DHCP_INTERFACE *)&V2DhcpInterfaceList )
      break;
    if ( *((struct _V2_DHCP_INTERFACE ***)V2DhcpInterfaceList + 1) != &V2DhcpInterfaceList
      || (v3 = *(_QWORD *)V2DhcpInterfaceList,
          *(struct _V2_DHCP_INTERFACE **)(*(_QWORD *)V2DhcpInterfaceList + 8LL) != V2DhcpInterfaceList) )
    {
      __fastfail(3u);
    }
    V2DhcpInterfaceList = *(struct _V2_DHCP_INTERFACE **)V2DhcpInterfaceList;
    *(_QWORD *)(v3 + 8) = &V2DhcpInterfaceList;
    if ( (*((_DWORD *)v2 + 31) & 0x60000000) == 0x60000000 )
      V2DhcpDeactivateInterface(v2);
    if ( (*((_DWORD *)v2 + 14))-- == 1 )
      V2DhcpCleanupInterface(v2);
  }
  LeaveCriticalSection(&V2DhcpInterfaceLock);
  while ( 1 )
  {
    EnterCriticalSection(&V2DhcpInterfaceLock);
    if ( V2DhcpInterfaceCount <= 0 )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids);
    }
    LeaveCriticalSection(&V2DhcpInterfaceLock);
    Sleep(0x1F4u);
  }
  LeaveCriticalSection(&V2DhcpInterfaceLock);
  if ( a1 )
    DeleteCriticalSection(&V2DhcpInterfaceLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids);
  }
}

```

## disassembly

```asm
0x180085b74  mov     [rsp+arg_0], rbx
0x180085b79  mov     [rsp+arg_10], rbp
0x180085b7e  push    rsi
0x180085b7f  push    rdi
0x180085b80  push    r14
0x180085b82  sub     rsp, 20h
0x180085b86  mov     dil, cl
0x180085b89  mov     rcx, cs:WPP_GLOBAL_Control
0x180085b90  lea     r14, WPP_GLOBAL_Control
0x180085b97  cmp     rcx, r14
0x180085b9a  jz      short loc_180085BBD
0x180085b9c  test    byte ptr [rcx+1Ch], 2
0x180085ba0  jz      short loc_180085BBD
0x180085ba2  cmp     byte ptr [rcx+19h], 6
0x180085ba6  jb      short loc_180085BBD
0x180085ba8  mov     rcx, [rcx+10h]
0x180085bac  lea     r8, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids
0x180085bb3  mov     edx, 7Eh ; '~'
0x180085bb8  call    WPP_SF_
0x180085bbd  lea     rsi, ?V2DhcpInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION V2DhcpInterfaceLock
0x180085bc4  mov     rcx, rsi; lpCriticalSection
0x180085bc7  call    cs:__imp_EnterCriticalSection
0x180085bcd  lea     rbp, ?V2DhcpInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY V2DhcpInterfaceList
0x180085bd4  mov     rbx, cs:?V2DhcpInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY V2DhcpInterfaceList
0x180085bdb  cmp     rbx, rbp
0x180085bde  jz      short loc_180085C28
0x180085be0  cmp     [rbx+8], rbp
0x180085be4  jnz     short loc_180085C21
0x180085be6  mov     rax, [rbx]
0x180085be9  cmp     [rax+8], rbx
0x180085bed  jnz     short loc_180085C21
0x180085bef  mov     cs:?V2DhcpInterfaceList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY V2DhcpInterfaceList
0x180085bf6  mov     [rax+8], rbp
0x180085bfa  mov     eax, [rbx+7Ch]
0x180085bfd  and     eax, 60000000h
0x180085c02  cmp     eax, 60000000h
0x180085c07  jnz     short loc_180085C11
0x180085c09  mov     rcx, rbx; struct _V2_DHCP_INTERFACE *
0x180085c0c  call    ?V2DhcpDeactivateInterface@@YAXPEAU_V2_DHCP_INTERFACE@@@Z; V2DhcpDeactivateInterface(_V2_DHCP_INTERFACE *)
0x180085c11  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x180085c15  jnz     short loc_180085BD4
0x180085c17  mov     rcx, rbx; lpMem
0x180085c1a  call    ?V2DhcpCleanupInterface@@YAXPEAU_V2_DHCP_INTERFACE@@@Z; V2DhcpCleanupInterface(_V2_DHCP_INTERFACE *)
0x180085c1f  jmp     short loc_180085BD4
0x180085c21  mov     ecx, 3
0x180085c26  int     29h; Win8: RtlFailFast(ecx)
0x180085c28  mov     rcx, rsi; lpCriticalSection
0x180085c2b  call    cs:__imp_LeaveCriticalSection
0x180085c31  jmp     short loc_180085C74
0x180085c33  mov     rcx, cs:WPP_GLOBAL_Control
0x180085c3a  cmp     rcx, r14
0x180085c3d  jz      short loc_180085C60
0x180085c3f  test    byte ptr [rcx+1Ch], 10h
0x180085c43  jz      short loc_180085C60
0x180085c45  cmp     byte ptr [rcx+19h], 5
0x180085c49  jb      short loc_180085C60
0x180085c4b  mov     rcx, [rcx+10h]
0x180085c4f  lea     r8, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids
0x180085c56  mov     edx, 7Fh
0x180085c5b  call    WPP_SF_
0x180085c60  mov     rcx, rsi; lpCriticalSection
0x180085c63  call    cs:__imp_LeaveCriticalSection
0x180085c69  mov     ecx, 1F4h; dwMilliseconds
0x180085c6e  call    cs:__imp_Sleep
0x180085c74  mov     rcx, rsi; lpCriticalSection
0x180085c77  call    cs:__imp_EnterCriticalSection
0x180085c7d  cmp     cs:?V2DhcpInterfaceCount@@3JA, 0; long V2DhcpInterfaceCount
0x180085c84  jg      short loc_180085C33
0x180085c86  mov     rcx, rsi; lpCriticalSection
0x180085c89  call    cs:__imp_LeaveCriticalSection
0x180085c8f  test    dil, dil
0x180085c92  jz      short loc_180085C9D
0x180085c94  mov     rcx, rsi; lpCriticalSection
0x180085c97  call    cs:__imp_DeleteCriticalSection
0x180085c9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180085ca4  cmp     rcx, r14
0x180085ca7  jz      short loc_180085CCA
0x180085ca9  test    byte ptr [rcx+1Ch], 2
0x180085cad  jz      short loc_180085CCA
0x180085caf  cmp     byte ptr [rcx+19h], 6
0x180085cb3  jb      short loc_180085CCA
0x180085cb5  mov     rcx, [rcx+10h]
0x180085cb9  lea     r8, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids
0x180085cc0  mov     edx, 80h
0x180085cc5  call    WPP_SF_
0x180085cca  mov     rbx, [rsp+38h+arg_0]
0x180085ccf  mov     rbp, [rsp+38h+arg_10]
0x180085cd4  add     rsp, 20h
0x180085cd8  pop     r14
0x180085cda  pop     rdi
0x180085cdb  pop     rsi
0x180085cdc  retn
```
