# DnsShutdownInterfaceManagement(uchar)

- ea: `0x18003afa0`
- end: `0x18003b109`
- name: `?DnsShutdownInterfaceManagement@@YAXE@Z`
- size: `361`
- prototype: `void __fastcall(unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18003ab00`
- `0x18003eee0`

## callees

- `0x18000c110`
- `0x180010458`
- `0x180010744`
- `0x18003afa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aff3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b0a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aff3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b0a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b057`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b08f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b0b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b057`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b08f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b0b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b0c3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b0c3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003b09a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003b09a`

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
0x18003afa0  mov     [rsp+arg_0], rbx
0x18003afa5  mov     [rsp+arg_10], rbp
0x18003afaa  push    rsi
0x18003afab  push    rdi
0x18003afac  push    r15
0x18003afae  sub     rsp, 20h
0x18003afb2  mov     dil, cl
0x18003afb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003afbc  lea     r15, WPP_GLOBAL_Control
0x18003afc3  cmp     rcx, r15
0x18003afc6  jz      short loc_18003AFE9
0x18003afc8  test    byte ptr [rcx+1Ch], 10h
0x18003afcc  jz      short loc_18003AFE9
0x18003afce  cmp     byte ptr [rcx+19h], 6
0x18003afd2  jb      short loc_18003AFE9
0x18003afd4  mov     rcx, [rcx+10h]
0x18003afd8  lea     r8, WPP_56b6188218e633e268d52c8066432fe3_Traceguids
0x18003afdf  mov     edx, 0B2h
0x18003afe4  call    WPP_SF_
0x18003afe9  lea     rsi, ?DnsInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION DnsInterfaceLock
0x18003aff0  mov     rcx, rsi; lpCriticalSection
0x18003aff3  call    cs:__imp_EnterCriticalSection
0x18003aff9  lea     rbp, ?DnsInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DnsInterfaceList
0x18003b000  mov     rbx, cs:?DnsInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DnsInterfaceList
0x18003b007  cmp     rbx, rbp
0x18003b00a  jz      short loc_18003B054
0x18003b00c  cmp     [rbx+8], rbp
0x18003b010  jnz     short loc_18003B04D
0x18003b012  mov     rax, [rbx]
0x18003b015  cmp     [rax+8], rbx
0x18003b019  jnz     short loc_18003B04D
0x18003b01b  mov     cs:?DnsInterfaceList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY DnsInterfaceList
0x18003b022  mov     [rax+8], rbp
0x18003b026  mov     eax, [rbx+50h]
0x18003b029  and     eax, 60000000h
0x18003b02e  cmp     eax, 60000000h
0x18003b033  jnz     short loc_18003B03D
0x18003b035  mov     rcx, rbx; struct _DNS_INTERFACE *
0x18003b038  call    ?DnsDeactivateInterface@@YAXPEAU_DNS_INTERFACE@@@Z; DnsDeactivateInterface(_DNS_INTERFACE *)
0x18003b03d  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x18003b041  jnz     short loc_18003B000
0x18003b043  mov     rcx, rbx; lpMem
0x18003b046  call    ?DnsCleanupInterface@@YAXPEAU_DNS_INTERFACE@@@Z; DnsCleanupInterface(_DNS_INTERFACE *)
0x18003b04b  jmp     short loc_18003B000
0x18003b04d  mov     ecx, 3
0x18003b052  int     29h; Win8: RtlFailFast(ecx)
0x18003b054  mov     rcx, rsi; lpCriticalSection
0x18003b057  call    cs:__imp_LeaveCriticalSection
0x18003b05d  jmp     short loc_18003B0A0
0x18003b05f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b066  cmp     rcx, r15
0x18003b069  jz      short loc_18003B08C
0x18003b06b  test    byte ptr [rcx+1Ch], 10h
0x18003b06f  jz      short loc_18003B08C
0x18003b071  cmp     byte ptr [rcx+19h], 5
0x18003b075  jb      short loc_18003B08C
0x18003b077  mov     rcx, [rcx+10h]
0x18003b07b  lea     r8, WPP_56b6188218e633e268d52c8066432fe3_Traceguids
0x18003b082  mov     edx, 0B3h
0x18003b087  call    WPP_SF_
0x18003b08c  mov     rcx, rsi; lpCriticalSection
0x18003b08f  call    cs:__imp_LeaveCriticalSection
0x18003b095  mov     ecx, 1F4h; dwMilliseconds
0x18003b09a  call    cs:__imp_Sleep
0x18003b0a0  mov     rcx, rsi; lpCriticalSection
0x18003b0a3  call    cs:__imp_EnterCriticalSection
0x18003b0a9  cmp     cs:?DnsInterfaceCount@@3JA, 0; long DnsInterfaceCount
0x18003b0b0  jg      short loc_18003B05F
0x18003b0b2  mov     rcx, rsi; lpCriticalSection
0x18003b0b5  call    cs:__imp_LeaveCriticalSection
0x18003b0bb  test    dil, dil
0x18003b0be  jz      short loc_18003B0C9
0x18003b0c0  mov     rcx, rsi; lpCriticalSection
0x18003b0c3  call    cs:__imp_DeleteCriticalSection
0x18003b0c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b0d0  cmp     rcx, r15
0x18003b0d3  jz      short loc_18003B0F6
0x18003b0d5  test    byte ptr [rcx+1Ch], 10h
0x18003b0d9  jz      short loc_18003B0F6
0x18003b0db  cmp     byte ptr [rcx+19h], 6
0x18003b0df  jb      short loc_18003B0F6
0x18003b0e1  mov     rcx, [rcx+10h]
0x18003b0e5  lea     r8, WPP_56b6188218e633e268d52c8066432fe3_Traceguids
0x18003b0ec  mov     edx, 0B4h
0x18003b0f1  call    WPP_SF_
0x18003b0f6  mov     rbx, [rsp+38h+arg_0]
0x18003b0fb  mov     rbp, [rsp+38h+arg_10]
0x18003b100  add     rsp, 20h
0x18003b104  pop     r15
0x18003b106  pop     rdi
0x18003b107  pop     rsi
0x18003b108  retn
```
