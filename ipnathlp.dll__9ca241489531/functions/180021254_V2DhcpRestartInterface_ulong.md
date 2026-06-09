# V2DhcpRestartInterface(ulong)

- ea: `0x180021254`
- end: `0x1800214f8`
- name: `?V2DhcpRestartInterface@@YAKK@Z`
- size: `676`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180020fc8`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18000f328`
- `0x180021254`
- `0x18002173c`
- `0x18004b990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021287`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800212ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021287`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800212ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800212d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021337`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800212d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021337`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002137a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002137a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800212e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800212e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002146a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002146a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002131f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002131f`

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
0x180021254  push    rbx
0x180021256  push    rsi
0x180021257  push    rdi
0x180021258  push    r14
0x18002125a  push    r15
0x18002125c  sub     rsp, 20h
0x180021260  mov     esi, ecx
0x180021262  mov     rcx, cs:WPP_GLOBAL_Control
0x180021269  lea     r14, WPP_GLOBAL_Control
0x180021270  lea     r15, WPP_cc76035b73e233bb5bf3894a25dab4d2_Traceguids
0x180021277  cmp     rcx, r14
0x18002127a  jnz     loc_1800213C9
0x180021280  lea     rcx, ?V2DhcpInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180021287  call    cs:__imp_EnterCriticalSection
0x18002128d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021294  cmp     rcx, r14
0x180021297  jz      short loc_1800212A3
0x180021299  test    byte ptr [rcx+1Ch], 2
0x18002129d  jnz     loc_1800213F6
0x1800212a3  mov     rdi, cs:?V2DhcpInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY V2DhcpInterfaceList
0x1800212aa  lea     rax, ?V2DhcpInterfaceList@@3U_LIST_ENTRY@@A; _LIST_ENTRY V2DhcpInterfaceList
0x1800212b1  cmp     rdi, rax
0x1800212b4  jnz     loc_18002141D
0x1800212ba  cmp     rcx, r14
0x1800212bd  jnz     loc_1800214A3
0x1800212c3  mov     ebx, 389h
0x1800212c8  jmp     short loc_180021330
0x1800212ca  lea     rcx, ?V2DhcpInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800212d1  call    cs:__imp_LeaveCriticalSection
0x1800212d7  mov     rcx, [rdi+88h]; hHandle
0x1800212de  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800212e1  call    cs:__imp_WaitForSingleObject
0x1800212e7  lea     rcx, ?V2DhcpInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800212ee  call    cs:__imp_EnterCriticalSection
0x1800212f4  xor     edx, edx; struct _LIST_ENTRY **
0x1800212f6  mov     ecx, esi; unsigned int
0x1800212f8  call    ?V2DhcpLookupInterface@@YAPEAU_V2_DHCP_INTERFACE@@KPEAPEAU_LIST_ENTRY@@@Z; V2DhcpLookupInterface(ulong,_LIST_ENTRY * *)
0x1800212fd  mov     rdi, rax
0x180021300  test    rax, rax
0x180021303  jz      loc_180021475
0x180021309  mov     rcx, rax; struct _V2_DHCP_INTERFACE *
0x18002130c  call    ?V2DhcpRefreshInterface@@YAKPEAU_V2_DHCP_INTERFACE@@@Z; V2DhcpRefreshInterface(_V2_DHCP_INTERFACE *)
0x180021311  mov     ebx, eax
0x180021313  mov     rcx, [rdi+88h]; hObject
0x18002131a  test    rcx, rcx
0x18002131d  jz      short loc_180021330
0x18002131f  call    cs:__imp_CloseHandle
0x180021325  mov     qword ptr [rdi+88h], 0
0x180021330  lea     rcx, ?V2DhcpInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180021337  call    cs:__imp_LeaveCriticalSection
0x18002133d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021344  cmp     rcx, r14
0x180021347  jz      short loc_180021359
0x180021349  test    byte ptr [rcx+1Ch], 2
0x18002134d  jz      short loc_180021359
0x18002134f  cmp     byte ptr [rcx+19h], 6
0x180021353  jnb     loc_1800214DF
0x180021359  mov     eax, ebx
0x18002135b  add     rsp, 20h
0x18002135f  pop     r15
0x180021361  pop     r14
0x180021363  pop     rdi
0x180021364  pop     rsi
0x180021365  pop     rbx
0x180021366  retn
0x180021367  test    rdi, rdi
0x18002136a  jz      loc_1800214C7
0x180021370  xor     r9d, r9d; lpName
0x180021373  xor     r8d, r8d; bInitialState
0x180021376  xor     edx, edx; bManualReset
0x180021378  xor     ecx, ecx; lpEventAttributes
0x18002137a  call    cs:__imp_CreateEventW
0x180021380  mov     [rdi+88h], rax
0x180021387  test    rax, rax
0x18002138a  jz      loc_18002146A
0x180021390  mov     ecx, esi; unsigned int
0x180021392  call    ?V2DhcpDeleteInterface@@YAKK@Z; V2DhcpDeleteInterface(ulong)
0x180021397  mov     ebx, eax
0x180021399  test    eax, eax
0x18002139b  jnz     loc_180021313
0x1800213a1  jmp     loc_1800212CA
0x1800213a6  cmp     byte ptr [rcx+19h], 2
0x1800213aa  jb      loc_1800212C3
0x1800213b0  mov     edx, 49h ; 'I'
0x1800213b5  mov     rcx, [rcx+10h]
0x1800213b9  mov     r9d, esi
0x1800213bc  mov     r8, r15
0x1800213bf  call    WPP_SF_d
0x1800213c4  jmp     loc_1800212C3
0x1800213c9  test    byte ptr [rcx+1Ch], 2
0x1800213cd  jz      loc_180021280
0x1800213d3  cmp     byte ptr [rcx+19h], 6
0x1800213d7  jb      loc_180021280
0x1800213dd  mov     rcx, [rcx+10h]
0x1800213e1  mov     edx, 48h ; 'H'
0x1800213e6  mov     r9d, esi
0x1800213e9  mov     r8, r15
0x1800213ec  call    WPP_SF_d
0x1800213f1  jmp     loc_180021280
0x1800213f6  cmp     byte ptr [rcx+19h], 6
0x1800213fa  jb      loc_1800212A3
0x180021400  mov     rcx, [rcx+10h]
0x180021404  mov     edx, 6Bh ; 'k'
0x180021409  mov     r8, r15
0x18002140c  call    WPP_SF_
0x180021411  mov     rcx, cs:WPP_GLOBAL_Control
0x180021418  jmp     loc_1800212A3
0x18002141d  cmp     esi, [rdi+3Ch]
0x180021420  jbe     short loc_18002142A
0x180021422  mov     rdi, [rdi]
0x180021425  jmp     loc_1800212AA
0x18002142a  jb      loc_1800212BA
0x180021430  cmp     rcx, r14
0x180021433  jz      loc_180021367
0x180021439  test    byte ptr [rcx+1Ch], 2
0x18002143d  jz      loc_180021367
0x180021443  cmp     byte ptr [rcx+19h], 6
0x180021447  jb      loc_180021367
0x18002144d  mov     rcx, [rcx+10h]
0x180021451  mov     edx, 6Ch ; 'l'
0x180021456  mov     r8, r15
0x180021459  call    WPP_SF_
0x18002145e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021465  jmp     loc_180021367
0x18002146a  call    cs:__imp_GetLastError
0x180021470  jmp     loc_180021311
0x180021475  mov     rcx, cs:WPP_GLOBAL_Control
0x18002147c  cmp     rcx, r14
0x18002147f  jz      loc_1800212C3
0x180021485  test    byte ptr [rcx+1Ch], 2
0x180021489  jz      loc_1800212C3
0x18002148f  cmp     byte ptr [rcx+19h], 2
0x180021493  jb      loc_1800212C3
0x180021499  mov     edx, 4Ah ; 'J'
0x18002149e  jmp     loc_1800213B5
0x1800214a3  test    byte ptr [rcx+1Ch], 2
0x1800214a7  jz      short loc_1800214C7
0x1800214a9  cmp     byte ptr [rcx+19h], 6
0x1800214ad  jb      short loc_1800214C7
0x1800214af  mov     rcx, [rcx+10h]
0x1800214b3  mov     edx, 6Dh ; 'm'
0x1800214b8  mov     r8, r15
0x1800214bb  call    WPP_SF_
0x1800214c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214c7  cmp     rcx, r14
0x1800214ca  jz      loc_1800212C3
0x1800214d0  test    byte ptr [rcx+1Ch], 2
0x1800214d4  jz      loc_1800212C3
0x1800214da  jmp     loc_1800213A6
0x1800214df  mov     rcx, [rcx+10h]
0x1800214e3  mov     edx, 4Bh ; 'K'
0x1800214e8  mov     r9d, ebx
0x1800214eb  mov     r8, r15
0x1800214ee  call    WPP_SF_d
0x1800214f3  jmp     loc_180021359
```
