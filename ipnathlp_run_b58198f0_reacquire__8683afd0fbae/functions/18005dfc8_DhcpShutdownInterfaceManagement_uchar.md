# DhcpShutdownInterfaceManagement(uchar)

- ea: `0x18005dfc8`
- end: `0x18005e15c`
- name: `?DhcpShutdownInterfaceManagement@@YAXE@Z`
- size: `404`
- prototype: `void __fastcall(unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180042360`
- `0x18005c074`

## callees

- `0x18000ca20`
- `0x18001085c`
- `0x180031260`
- `0x18005dfc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e01b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e0e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e01b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e0e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e085`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e0c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e0fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e085`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e0c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e0fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005e10f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005e10f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005e0d4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005e0d4`

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
0x18005dfc8  mov     [rsp+arg_0], rbx
0x18005dfcd  mov     [rsp+arg_10], rbp
0x18005dfd2  push    rsi
0x18005dfd3  push    rdi
0x18005dfd4  push    r14
0x18005dfd6  sub     rsp, 20h
0x18005dfda  mov     dil, cl
0x18005dfdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005dfe4  lea     r14, WPP_GLOBAL_Control
0x18005dfeb  cmp     rcx, r14
0x18005dfee  jz      short loc_18005E011
0x18005dff0  test    byte ptr [rcx+1Ch], 2
0x18005dff4  jz      short loc_18005E011
0x18005dff6  cmp     byte ptr [rcx+19h], 6
0x18005dffa  jb      short loc_18005E011
0x18005dffc  mov     rcx, [rcx+10h]
0x18005e000  lea     r8, WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids
0x18005e007  mov     edx, 7Dh ; '}'
0x18005e00c  call    WPP_SF_
0x18005e011  lea     rsi, ?DhcpInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION DhcpInterfaceLock
0x18005e018  mov     rcx, rsi; lpCriticalSection
0x18005e01b  call    cs:__imp_EnterCriticalSection
0x18005e022  nop     dword ptr [rax+rax+00h]
0x18005e027  lea     rbp, ?DhcpInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DhcpInterfaceList
0x18005e02e  mov     rbx, cs:?DhcpInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DhcpInterfaceList
0x18005e035  cmp     rbx, rbp
0x18005e038  jz      short loc_18005E082
0x18005e03a  cmp     [rbx+8], rbp
0x18005e03e  jnz     short loc_18005E07B
0x18005e040  mov     rax, [rbx]
0x18005e043  cmp     [rax+8], rbx
0x18005e047  jnz     short loc_18005E07B
0x18005e049  mov     cs:?DhcpInterfaceList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY DhcpInterfaceList
0x18005e050  mov     [rax+8], rbp
0x18005e054  mov     eax, [rbx+4Ch]
0x18005e057  and     eax, 60000000h
0x18005e05c  cmp     eax, 60000000h
0x18005e061  jnz     short loc_18005E06B
0x18005e063  mov     rcx, rbx; struct _DHCP_INTERFACE *
0x18005e066  call    ?DhcpDeactivateInterface@@YAXPEAU_DHCP_INTERFACE@@@Z; DhcpDeactivateInterface(_DHCP_INTERFACE *)
0x18005e06b  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x18005e06f  jnz     short loc_18005E02E
0x18005e071  mov     rcx, rbx; lpMem
0x18005e074  call    ?DhcpCleanupInterface@@YAXPEAU_DHCP_INTERFACE@@@Z; DhcpCleanupInterface(_DHCP_INTERFACE *)
0x18005e079  jmp     short loc_18005E02E
0x18005e07b  mov     ecx, 3
0x18005e080  int     29h; Win8: RtlFailFast(ecx)
0x18005e082  mov     rcx, rsi; lpCriticalSection
0x18005e085  call    cs:__imp_LeaveCriticalSection
0x18005e08c  nop     dword ptr [rax+rax+00h]
0x18005e091  jmp     short loc_18005E0E0
0x18005e093  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e09a  cmp     rcx, r14
0x18005e09d  jz      short loc_18005E0C0
0x18005e09f  test    byte ptr [rcx+1Ch], 10h
0x18005e0a3  jz      short loc_18005E0C0
0x18005e0a5  cmp     byte ptr [rcx+19h], 5
0x18005e0a9  jb      short loc_18005E0C0
0x18005e0ab  mov     rcx, [rcx+10h]
0x18005e0af  lea     r8, WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids
0x18005e0b6  mov     edx, 7Eh ; '~'
0x18005e0bb  call    WPP_SF_
0x18005e0c0  mov     rcx, rsi; lpCriticalSection
0x18005e0c3  call    cs:__imp_LeaveCriticalSection
0x18005e0ca  nop     dword ptr [rax+rax+00h]
0x18005e0cf  mov     ecx, 1F4h; dwMilliseconds
0x18005e0d4  call    cs:__imp_Sleep
0x18005e0db  nop     dword ptr [rax+rax+00h]
0x18005e0e0  mov     rcx, rsi; lpCriticalSection
0x18005e0e3  call    cs:__imp_EnterCriticalSection
0x18005e0ea  nop     dword ptr [rax+rax+00h]
0x18005e0ef  cmp     cs:?DhcpInterfaceCount@@3JA, 0; long DhcpInterfaceCount
0x18005e0f6  jg      short loc_18005E093
0x18005e0f8  mov     rcx, rsi; lpCriticalSection
0x18005e0fb  call    cs:__imp_LeaveCriticalSection
0x18005e102  nop     dword ptr [rax+rax+00h]
0x18005e107  test    dil, dil
0x18005e10a  jz      short loc_18005E11B
0x18005e10c  mov     rcx, rsi; lpCriticalSection
0x18005e10f  call    cs:__imp_DeleteCriticalSection
0x18005e116  nop     dword ptr [rax+rax+00h]
0x18005e11b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e122  cmp     rcx, r14
0x18005e125  jz      short loc_18005E148
0x18005e127  test    byte ptr [rcx+1Ch], 2
0x18005e12b  jz      short loc_18005E148
0x18005e12d  cmp     byte ptr [rcx+19h], 6
0x18005e131  jb      short loc_18005E148
0x18005e133  mov     rcx, [rcx+10h]
0x18005e137  lea     r8, WPP_ee6aa21a272e3a6a6df4f3c8e21775a3_Traceguids
0x18005e13e  mov     edx, 7Fh
0x18005e143  call    WPP_SF_
0x18005e148  mov     rbx, [rsp+38h+arg_0]
0x18005e14d  mov     rbp, [rsp+38h+arg_10]
0x18005e152  add     rsp, 20h
0x18005e156  pop     r14
0x18005e158  pop     rdi
0x18005e159  pop     rsi
0x18005e15a  retn
```
