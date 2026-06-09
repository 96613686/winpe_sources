# V2DhcpRestartInterface(ulong)

- ea: `0x18002d618`
- end: `0x18002d8ed`
- name: `?V2DhcpRestartInterface@@YAKK@Z`
- size: `725`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002d37c`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18000fec0`
- `0x18002d618`
- `0x18002db50`
- `0x18004f694`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d64b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d6c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d64b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d6c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d69b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d719`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d69b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d719`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d763`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d763`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d6b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d6b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d859`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d6fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d6fb`

## pseudocode

```c
__int64 __fastcall V2DhcpRestartInterface(unsigned int a1)
{
  PVOID *v2; // rcx
  struct _V2_DHCP_INTERFACE *i; // rdi
  unsigned int v4; // ebx
  struct _V2_DHCP_INTERFACE *v5; // rax
  DWORD LastError; // eax
  void *v7; // rcx
  HANDLE EventW; // rax
  __int64 v10; // rdx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids, a1);
  }
  EnterCriticalSection(&V2DhcpInterfaceLock);
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  for ( i = V2DhcpInterfaceList; ; i = *(struct _V2_DHCP_INTERFACE **)i )
  {
    if ( i == (struct _V2_DHCP_INTERFACE *)&V2DhcpInterfaceList )
      goto LABEL_6;
    if ( a1 <= *((_DWORD *)i + 15) )
      break;
  }
  if ( a1 < *((_DWORD *)i + 15) )
  {
LABEL_6:
    if ( v2 == &WPP_GLOBAL_Control )
      goto LABEL_7;
    if ( (*((_BYTE *)v2 + 28) & 2) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    {
      WPP_SF_(v2[2], 109, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_45:
    if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 2) == 0 || *((_BYTE *)v2 + 25) < 2u )
      goto LABEL_7;
    v10 = 73;
    goto LABEL_24;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 && *((_BYTE *)v2 + 25) >= 6u )
  {
    WPP_SF_(v2[2], 108, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !i )
    goto LABEL_45;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)i + 17) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    goto LABEL_10;
  }
  v4 = V2DhcpDeleteInterface(a1);
  if ( !v4 )
  {
    LeaveCriticalSection(&V2DhcpInterfaceLock);
    WaitForSingleObject(*((HANDLE *)i + 17), 0xFFFFFFFF);
    EnterCriticalSection(&V2DhcpInterfaceLock);
    v5 = V2DhcpLookupInterface(a1, 0);
    i = v5;
    if ( v5 )
    {
      LastError = V2DhcpRefreshInterface(v5);
LABEL_10:
      v4 = LastError;
      goto LABEL_11;
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 74;
LABEL_24:
      WPP_SF_d(v2[2], v10, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids, a1);
    }
LABEL_7:
    v4 = 905;
    goto LABEL_13;
  }
LABEL_11:
  v7 = (void *)*((_QWORD *)i + 17);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)i + 17) = 0;
  }
LABEL_13:
  LeaveCriticalSection(&V2DhcpInterfaceLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18002d618  push    rbx
0x18002d61a  push    rsi
0x18002d61b  push    rdi
0x18002d61c  push    r14
0x18002d61e  push    r15
0x18002d620  sub     rsp, 20h
0x18002d624  mov     esi, ecx
0x18002d626  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d62d  lea     r14, WPP_GLOBAL_Control
0x18002d634  lea     r15, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids
0x18002d63b  cmp     rcx, r14
0x18002d63e  jnz     loc_18002D7B8
0x18002d644  lea     rcx, ?V2DhcpInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002d64b  call    cs:__imp_EnterCriticalSection
0x18002d652  nop     dword ptr [rax+rax+00h]
0x18002d657  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d65e  cmp     rcx, r14
0x18002d661  jz      short loc_18002D66D
0x18002d663  test    byte ptr [rcx+1Ch], 2
0x18002d667  jnz     loc_18002D7E5
0x18002d66d  mov     rdi, cs:?V2DhcpInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY V2DhcpInterfaceList
0x18002d674  lea     rax, ?V2DhcpInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY V2DhcpInterfaceList
0x18002d67b  cmp     rdi, rax
0x18002d67e  jnz     loc_18002D80C
0x18002d684  cmp     rcx, r14
0x18002d687  jnz     loc_18002D898
0x18002d68d  mov     ebx, 389h
0x18002d692  jmp     short loc_18002D712
0x18002d694  lea     rcx, ?V2DhcpInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002d69b  call    cs:__imp_LeaveCriticalSection
0x18002d6a2  nop     dword ptr [rax+rax+00h]
0x18002d6a7  mov     rcx, [rdi+88h]; hHandle
0x18002d6ae  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002d6b1  call    cs:__imp_WaitForSingleObject
0x18002d6b8  nop     dword ptr [rax+rax+00h]
0x18002d6bd  lea     rcx, ?V2DhcpInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002d6c4  call    cs:__imp_EnterCriticalSection
0x18002d6cb  nop     dword ptr [rax+rax+00h]
0x18002d6d0  xor     edx, edx; struct _LIST_ENTRY **
0x18002d6d2  mov     ecx, esi; unsigned int
0x18002d6d4  call    ?V2DhcpLookupInterface@@YAPEAU_V2_DHCP_INTERFACE@@KPEAPEAU_LIST_ENTRY@@@Z; V2DhcpLookupInterface(ulong,_LIST_ENTRY * *)
0x18002d6d9  mov     rdi, rax
0x18002d6dc  test    rax, rax
0x18002d6df  jz      loc_18002D86A
0x18002d6e5  mov     rcx, rax; struct _V2_DHCP_INTERFACE *
0x18002d6e8  call    ?V2DhcpRefreshInterface@@YAKPEAU_V2_DHCP_INTERFACE@@@Z; V2DhcpRefreshInterface(_V2_DHCP_INTERFACE *)
0x18002d6ed  mov     ebx, eax
0x18002d6ef  mov     rcx, [rdi+88h]; hObject
0x18002d6f6  test    rcx, rcx
0x18002d6f9  jz      short loc_18002D712
0x18002d6fb  call    cs:__imp_CloseHandle
0x18002d702  nop     dword ptr [rax+rax+00h]
0x18002d707  mov     qword ptr [rdi+88h], 0
0x18002d712  lea     rcx, ?V2DhcpInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002d719  call    cs:__imp_LeaveCriticalSection
0x18002d720  nop     dword ptr [rax+rax+00h]
0x18002d725  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d72c  cmp     rcx, r14
0x18002d72f  jz      short loc_18002D741
0x18002d731  test    byte ptr [rcx+1Ch], 2
0x18002d735  jz      short loc_18002D741
0x18002d737  cmp     byte ptr [rcx+19h], 6
0x18002d73b  jnb     loc_18002D8D4
0x18002d741  mov     eax, ebx
0x18002d743  add     rsp, 20h
0x18002d747  pop     r15
0x18002d749  pop     r14
0x18002d74b  pop     rdi
0x18002d74c  pop     rsi
0x18002d74d  pop     rbx
0x18002d74e  retn
0x18002d750  test    rdi, rdi
0x18002d753  jz      loc_18002D8BC
0x18002d759  xor     r9d, r9d; lpName
0x18002d75c  xor     r8d, r8d; bInitialState
0x18002d75f  xor     edx, edx; bManualReset
0x18002d761  xor     ecx, ecx; lpEventAttributes
0x18002d763  call    cs:__imp_CreateEventW
0x18002d76a  nop     dword ptr [rax+rax+00h]
0x18002d76f  mov     [rdi+88h], rax
0x18002d776  test    rax, rax
0x18002d779  jz      loc_18002D859
0x18002d77f  mov     ecx, esi; unsigned int
0x18002d781  call    ?V2DhcpDeleteInterface@@YAKK@Z; V2DhcpDeleteInterface(ulong)
0x18002d786  mov     ebx, eax
0x18002d788  test    eax, eax
0x18002d78a  jnz     loc_18002D6EF
0x18002d790  jmp     loc_18002D694
0x18002d795  cmp     byte ptr [rcx+19h], 2
0x18002d799  jb      loc_18002D68D
0x18002d79f  mov     edx, 49h ; 'I'
0x18002d7a4  mov     rcx, [rcx+10h]
0x18002d7a8  mov     r9d, esi
0x18002d7ab  mov     r8, r15
0x18002d7ae  call    WPP_SF_d
0x18002d7b3  jmp     loc_18002D68D
0x18002d7b8  test    byte ptr [rcx+1Ch], 2
0x18002d7bc  jz      loc_18002D644
0x18002d7c2  cmp     byte ptr [rcx+19h], 6
0x18002d7c6  jb      loc_18002D644
0x18002d7cc  mov     rcx, [rcx+10h]
0x18002d7d0  mov     edx, 48h ; 'H'
0x18002d7d5  mov     r9d, esi
0x18002d7d8  mov     r8, r15
0x18002d7db  call    WPP_SF_d
0x18002d7e0  jmp     loc_18002D644
0x18002d7e5  cmp     byte ptr [rcx+19h], 6
0x18002d7e9  jb      loc_18002D66D
0x18002d7ef  mov     rcx, [rcx+10h]
0x18002d7f3  mov     edx, 6Bh ; 'k'
0x18002d7f8  mov     r8, r15
0x18002d7fb  call    WPP_SF_
0x18002d800  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d807  jmp     loc_18002D66D
0x18002d80c  cmp     esi, [rdi+3Ch]
0x18002d80f  jbe     short loc_18002D819
0x18002d811  mov     rdi, [rdi]
0x18002d814  jmp     loc_18002D674
0x18002d819  jb      loc_18002D684
0x18002d81f  cmp     rcx, r14
0x18002d822  jz      loc_18002D750
0x18002d828  test    byte ptr [rcx+1Ch], 2
0x18002d82c  jz      loc_18002D750
0x18002d832  cmp     byte ptr [rcx+19h], 6
0x18002d836  jb      loc_18002D750
0x18002d83c  mov     rcx, [rcx+10h]
0x18002d840  mov     edx, 6Ch ; 'l'
0x18002d845  mov     r8, r15
0x18002d848  call    WPP_SF_
0x18002d84d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d854  jmp     loc_18002D750
0x18002d859  call    cs:__imp_GetLastError
0x18002d860  nop     dword ptr [rax+rax+00h]
0x18002d865  jmp     loc_18002D6ED
0x18002d86a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d871  cmp     rcx, r14
0x18002d874  jz      loc_18002D68D
0x18002d87a  test    byte ptr [rcx+1Ch], 2
0x18002d87e  jz      loc_18002D68D
0x18002d884  cmp     byte ptr [rcx+19h], 2
0x18002d888  jb      loc_18002D68D
0x18002d88e  mov     edx, 4Ah ; 'J'
0x18002d893  jmp     loc_18002D7A4
0x18002d898  test    byte ptr [rcx+1Ch], 2
0x18002d89c  jz      short loc_18002D8BC
0x18002d89e  cmp     byte ptr [rcx+19h], 6
0x18002d8a2  jb      short loc_18002D8BC
0x18002d8a4  mov     rcx, [rcx+10h]
0x18002d8a8  mov     edx, 6Dh ; 'm'
0x18002d8ad  mov     r8, r15
0x18002d8b0  call    WPP_SF_
0x18002d8b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d8bc  cmp     rcx, r14
0x18002d8bf  jz      loc_18002D68D
0x18002d8c5  test    byte ptr [rcx+1Ch], 2
0x18002d8c9  jz      loc_18002D68D
0x18002d8cf  jmp     loc_18002D795
0x18002d8d4  mov     rcx, [rcx+10h]
0x18002d8d8  mov     edx, 4Bh ; 'K'
0x18002d8dd  mov     r9d, ebx
0x18002d8e0  mov     r8, r15
0x18002d8e3  call    WPP_SF_d
0x18002d8e8  jmp     loc_18002D741
```
