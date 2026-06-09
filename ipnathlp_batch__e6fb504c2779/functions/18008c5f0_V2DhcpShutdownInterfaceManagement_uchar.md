# V2DhcpShutdownInterfaceManagement(uchar)

- ea: `0x18008c5f0`
- end: `0x18008c784`
- name: `?V2DhcpShutdownInterfaceManagement@@YAXE@Z`
- size: `404`
- prototype: `void __fastcall(unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180042360`
- `0x18008ac74`

## callees

- `0x18000ca20`
- `0x180042024`
- `0x18008b578`
- `0x18008c5f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c643`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c70b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c643`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c70b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c6ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c6eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c723`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c6ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c6eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c723`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008c737`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008c737`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008c6fc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008c6fc`

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
0x18008c5f0  mov     [rsp+arg_0], rbx
0x18008c5f5  mov     [rsp+arg_10], rbp
0x18008c5fa  push    rsi
0x18008c5fb  push    rdi
0x18008c5fc  push    r14
0x18008c5fe  sub     rsp, 20h
0x18008c602  mov     dil, cl
0x18008c605  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c60c  lea     r14, WPP_GLOBAL_Control
0x18008c613  cmp     rcx, r14
0x18008c616  jz      short loc_18008C639
0x18008c618  test    byte ptr [rcx+1Ch], 2
0x18008c61c  jz      short loc_18008C639
0x18008c61e  cmp     byte ptr [rcx+19h], 6
0x18008c622  jb      short loc_18008C639
0x18008c624  mov     rcx, [rcx+10h]
0x18008c628  lea     r8, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids
0x18008c62f  mov     edx, 7Eh ; '~'
0x18008c634  call    WPP_SF_
0x18008c639  lea     rsi, ?V2DhcpInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION V2DhcpInterfaceLock
0x18008c640  mov     rcx, rsi; lpCriticalSection
0x18008c643  call    cs:__imp_EnterCriticalSection
0x18008c64a  nop     dword ptr [rax+rax+00h]
0x18008c64f  lea     rbp, ?V2DhcpInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY V2DhcpInterfaceList
0x18008c656  mov     rbx, cs:?V2DhcpInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY V2DhcpInterfaceList
0x18008c65d  cmp     rbx, rbp
0x18008c660  jz      short loc_18008C6AA
0x18008c662  cmp     [rbx+8], rbp
0x18008c666  jnz     short loc_18008C6A3
0x18008c668  mov     rax, [rbx]
0x18008c66b  cmp     [rax+8], rbx
0x18008c66f  jnz     short loc_18008C6A3
0x18008c671  mov     cs:?V2DhcpInterfaceList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY V2DhcpInterfaceList
0x18008c678  mov     [rax+8], rbp
0x18008c67c  mov     eax, [rbx+7Ch]
0x18008c67f  and     eax, 60000000h
0x18008c684  cmp     eax, 60000000h
0x18008c689  jnz     short loc_18008C693
0x18008c68b  mov     rcx, rbx; struct _V2_DHCP_INTERFACE *
0x18008c68e  call    ?V2DhcpDeactivateInterface@@YAXPEAU_V2_DHCP_INTERFACE@@@Z; V2DhcpDeactivateInterface(_V2_DHCP_INTERFACE *)
0x18008c693  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x18008c697  jnz     short loc_18008C656
0x18008c699  mov     rcx, rbx; lpMem
0x18008c69c  call    ?V2DhcpCleanupInterface@@YAXPEAU_V2_DHCP_INTERFACE@@@Z; V2DhcpCleanupInterface(_V2_DHCP_INTERFACE *)
0x18008c6a1  jmp     short loc_18008C656
0x18008c6a3  mov     ecx, 3
0x18008c6a8  int     29h; Win8: RtlFailFast(ecx)
0x18008c6aa  mov     rcx, rsi; lpCriticalSection
0x18008c6ad  call    cs:__imp_LeaveCriticalSection
0x18008c6b4  nop     dword ptr [rax+rax+00h]
0x18008c6b9  jmp     short loc_18008C708
0x18008c6bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c6c2  cmp     rcx, r14
0x18008c6c5  jz      short loc_18008C6E8
0x18008c6c7  test    byte ptr [rcx+1Ch], 10h
0x18008c6cb  jz      short loc_18008C6E8
0x18008c6cd  cmp     byte ptr [rcx+19h], 5
0x18008c6d1  jb      short loc_18008C6E8
0x18008c6d3  mov     rcx, [rcx+10h]
0x18008c6d7  lea     r8, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids
0x18008c6de  mov     edx, 7Fh
0x18008c6e3  call    WPP_SF_
0x18008c6e8  mov     rcx, rsi; lpCriticalSection
0x18008c6eb  call    cs:__imp_LeaveCriticalSection
0x18008c6f2  nop     dword ptr [rax+rax+00h]
0x18008c6f7  mov     ecx, 1F4h; dwMilliseconds
0x18008c6fc  call    cs:__imp_Sleep
0x18008c703  nop     dword ptr [rax+rax+00h]
0x18008c708  mov     rcx, rsi; lpCriticalSection
0x18008c70b  call    cs:__imp_EnterCriticalSection
0x18008c712  nop     dword ptr [rax+rax+00h]
0x18008c717  cmp     cs:?V2DhcpInterfaceCount@@3JA, 0; long V2DhcpInterfaceCount
0x18008c71e  jg      short loc_18008C6BB
0x18008c720  mov     rcx, rsi; lpCriticalSection
0x18008c723  call    cs:__imp_LeaveCriticalSection
0x18008c72a  nop     dword ptr [rax+rax+00h]
0x18008c72f  test    dil, dil
0x18008c732  jz      short loc_18008C743
0x18008c734  mov     rcx, rsi; lpCriticalSection
0x18008c737  call    cs:__imp_DeleteCriticalSection
0x18008c73e  nop     dword ptr [rax+rax+00h]
0x18008c743  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c74a  cmp     rcx, r14
0x18008c74d  jz      short loc_18008C770
0x18008c74f  test    byte ptr [rcx+1Ch], 2
0x18008c753  jz      short loc_18008C770
0x18008c755  cmp     byte ptr [rcx+19h], 6
0x18008c759  jb      short loc_18008C770
0x18008c75b  mov     rcx, [rcx+10h]
0x18008c75f  lea     r8, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids
0x18008c766  mov     edx, 80h
0x18008c76b  call    WPP_SF_
0x18008c770  mov     rbx, [rsp+38h+arg_0]
0x18008c775  mov     rbp, [rsp+38h+arg_10]
0x18008c77a  add     rsp, 20h
0x18008c77e  pop     r14
0x18008c780  pop     rdi
0x18008c781  pop     rsi
0x18008c782  retn
```
