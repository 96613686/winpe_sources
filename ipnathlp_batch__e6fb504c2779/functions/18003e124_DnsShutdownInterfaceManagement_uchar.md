# DnsShutdownInterfaceManagement(uchar)

- ea: `0x18003e124`
- end: `0x18003e2b8`
- name: `?DnsShutdownInterfaceManagement@@YAXE@Z`
- size: `404`
- prototype: `void __fastcall(unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18003dbc4`
- `0x180042360`

## callees

- `0x18000ca20`
- `0x180011108`
- `0x180011428`
- `0x18003e124`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e177`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e23f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e177`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e23f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e1e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e21f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e257`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e1e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e21f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e257`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003e26b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003e26b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003e230`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003e230`

## pseudocode

```c
void __fastcall DnsShutdownInterfaceManagement(char a1)
{
  struct _DNS_INTERFACE *v2; // rbx
  __int64 v3; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, &WPP_56b6188218e633e268d52c8066432fe3_Traceguids);
  }
  EnterCriticalSection(&DnsInterfaceLock);
  while ( 1 )
  {
    v2 = DnsInterfaceList;
    if ( DnsInterfaceList == (struct _DNS_INTERFACE *)&DnsInterfaceList )
      break;
    if ( *((struct _DNS_INTERFACE ***)DnsInterfaceList + 1) != &DnsInterfaceList
      || (v3 = *(_QWORD *)DnsInterfaceList,
          *(struct _DNS_INTERFACE **)(*(_QWORD *)DnsInterfaceList + 8LL) != DnsInterfaceList) )
    {
      __fastfail(3u);
    }
    DnsInterfaceList = *(struct _DNS_INTERFACE **)DnsInterfaceList;
    *(_QWORD *)(v3 + 8) = &DnsInterfaceList;
    if ( (*((_DWORD *)v2 + 20) & 0x60000000) == 0x60000000 )
      DnsDeactivateInterface(v2);
    if ( (*((_DWORD *)v2 + 14))-- == 1 )
      DnsCleanupInterface(v2);
  }
  LeaveCriticalSection(&DnsInterfaceLock);
  while ( 1 )
  {
    EnterCriticalSection(&DnsInterfaceLock);
    if ( DnsInterfaceCount <= 0 )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, &WPP_56b6188218e633e268d52c8066432fe3_Traceguids);
    }
    LeaveCriticalSection(&DnsInterfaceLock);
    Sleep(0x1F4u);
  }
  LeaveCriticalSection(&DnsInterfaceLock);
  if ( a1 )
    DeleteCriticalSection(&DnsInterfaceLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, &WPP_56b6188218e633e268d52c8066432fe3_Traceguids);
  }
}

```

## disassembly

```asm
0x18003e124  mov     [rsp+arg_0], rbx
0x18003e129  mov     [rsp+arg_10], rbp
0x18003e12e  push    rsi
0x18003e12f  push    rdi
0x18003e130  push    r15
0x18003e132  sub     rsp, 20h
0x18003e136  mov     dil, cl
0x18003e139  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e140  lea     r15, WPP_GLOBAL_Control
0x18003e147  cmp     rcx, r15
0x18003e14a  jz      short loc_18003E16D
0x18003e14c  test    byte ptr [rcx+1Ch], 10h
0x18003e150  jz      short loc_18003E16D
0x18003e152  cmp     byte ptr [rcx+19h], 6
0x18003e156  jb      short loc_18003E16D
0x18003e158  mov     rcx, [rcx+10h]
0x18003e15c  lea     r8, WPP_56b6188218e633e268d52c8066432fe3_Traceguids
0x18003e163  mov     edx, 0B2h
0x18003e168  call    WPP_SF_
0x18003e16d  lea     rsi, ?DnsInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION DnsInterfaceLock
0x18003e174  mov     rcx, rsi; lpCriticalSection
0x18003e177  call    cs:__imp_EnterCriticalSection
0x18003e17e  nop     dword ptr [rax+rax+00h]
0x18003e183  lea     rbp, ?DnsInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DnsInterfaceList
0x18003e18a  mov     rbx, cs:?DnsInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DnsInterfaceList
0x18003e191  cmp     rbx, rbp
0x18003e194  jz      short loc_18003E1DE
0x18003e196  cmp     [rbx+8], rbp
0x18003e19a  jnz     short loc_18003E1D7
0x18003e19c  mov     rax, [rbx]
0x18003e19f  cmp     [rax+8], rbx
0x18003e1a3  jnz     short loc_18003E1D7
0x18003e1a5  mov     cs:?DnsInterfaceList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY DnsInterfaceList
0x18003e1ac  mov     [rax+8], rbp
0x18003e1b0  mov     eax, [rbx+50h]
0x18003e1b3  and     eax, 60000000h
0x18003e1b8  cmp     eax, 60000000h
0x18003e1bd  jnz     short loc_18003E1C7
0x18003e1bf  mov     rcx, rbx; struct _DNS_INTERFACE *
0x18003e1c2  call    ?DnsDeactivateInterface@@YAXPEAU_DNS_INTERFACE@@@Z; DnsDeactivateInterface(_DNS_INTERFACE *)
0x18003e1c7  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x18003e1cb  jnz     short loc_18003E18A
0x18003e1cd  mov     rcx, rbx; lpMem
0x18003e1d0  call    ?DnsCleanupInterface@@YAXPEAU_DNS_INTERFACE@@@Z; DnsCleanupInterface(_DNS_INTERFACE *)
0x18003e1d5  jmp     short loc_18003E18A
0x18003e1d7  mov     ecx, 3
0x18003e1dc  int     29h; Win8: RtlFailFast(ecx)
0x18003e1de  mov     rcx, rsi; lpCriticalSection
0x18003e1e1  call    cs:__imp_LeaveCriticalSection
0x18003e1e8  nop     dword ptr [rax+rax+00h]
0x18003e1ed  jmp     short loc_18003E23C
0x18003e1ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e1f6  cmp     rcx, r15
0x18003e1f9  jz      short loc_18003E21C
0x18003e1fb  test    byte ptr [rcx+1Ch], 10h
0x18003e1ff  jz      short loc_18003E21C
0x18003e201  cmp     byte ptr [rcx+19h], 5
0x18003e205  jb      short loc_18003E21C
0x18003e207  mov     rcx, [rcx+10h]
0x18003e20b  lea     r8, WPP_56b6188218e633e268d52c8066432fe3_Traceguids
0x18003e212  mov     edx, 0B3h
0x18003e217  call    WPP_SF_
0x18003e21c  mov     rcx, rsi; lpCriticalSection
0x18003e21f  call    cs:__imp_LeaveCriticalSection
0x18003e226  nop     dword ptr [rax+rax+00h]
0x18003e22b  mov     ecx, 1F4h; dwMilliseconds
0x18003e230  call    cs:__imp_Sleep
0x18003e237  nop     dword ptr [rax+rax+00h]
0x18003e23c  mov     rcx, rsi; lpCriticalSection
0x18003e23f  call    cs:__imp_EnterCriticalSection
0x18003e246  nop     dword ptr [rax+rax+00h]
0x18003e24b  cmp     cs:?DnsInterfaceCount@@3JA, 0; long DnsInterfaceCount
0x18003e252  jg      short loc_18003E1EF
0x18003e254  mov     rcx, rsi; lpCriticalSection
0x18003e257  call    cs:__imp_LeaveCriticalSection
0x18003e25e  nop     dword ptr [rax+rax+00h]
0x18003e263  test    dil, dil
0x18003e266  jz      short loc_18003E277
0x18003e268  mov     rcx, rsi; lpCriticalSection
0x18003e26b  call    cs:__imp_DeleteCriticalSection
0x18003e272  nop     dword ptr [rax+rax+00h]
0x18003e277  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e27e  cmp     rcx, r15
0x18003e281  jz      short loc_18003E2A4
0x18003e283  test    byte ptr [rcx+1Ch], 10h
0x18003e287  jz      short loc_18003E2A4
0x18003e289  cmp     byte ptr [rcx+19h], 6
0x18003e28d  jb      short loc_18003E2A4
0x18003e28f  mov     rcx, [rcx+10h]
0x18003e293  lea     r8, WPP_56b6188218e633e268d52c8066432fe3_Traceguids
0x18003e29a  mov     edx, 0B4h
0x18003e29f  call    WPP_SF_
0x18003e2a4  mov     rbx, [rsp+38h+arg_0]
0x18003e2a9  mov     rbp, [rsp+38h+arg_10]
0x18003e2ae  add     rsp, 20h
0x18003e2b2  pop     r15
0x18003e2b4  pop     rdi
0x18003e2b5  pop     rsi
0x18003e2b6  retn
```
