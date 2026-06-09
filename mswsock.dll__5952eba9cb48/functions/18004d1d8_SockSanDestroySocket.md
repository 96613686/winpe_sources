# SockSanDestroySocket

- ea: `0x18004d1d8`
- end: `0x18004d447`
- name: `SockSanDestroySocket`
- size: `623`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008250`

## callees

- `0x180041d50`
- `0x180042b50`
- `0x18004c94c`
- `0x18004d1d8`
- `0x1800507fc`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004d201`
- `ntdll!RtlFreeHeap` at `0x18004d283`
- `ntdll!RtlFreeHeap` at `0x18004d3b1`
- `ntdll!RtlFreeHeap` at `0x18004d3c9`
- `ntdll!RtlFreeHeap` at `0x18004d201`
- `ntdll!RtlFreeHeap` at `0x18004d283`
- `ntdll!RtlFreeHeap` at `0x18004d3b1`
- `ntdll!RtlFreeHeap` at `0x18004d3c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d395`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d3e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d401`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d395`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d3e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d401`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004d427`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004d427`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d267`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d294`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d2e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d35f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d267`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d294`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d2e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d35f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d22c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d2ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d2fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d22c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d2ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d2fc`

## pseudocode

```c
char __fastcall SockSanDestroySocket(char *P)
{
  void *v2; // r8
  __int64 v3; // rcx
  char *v4; // rdi
  _QWORD *v5; // rax
  __int64 v6; // rdx
  _QWORD *v7; // rcx
  char **v8; // rdx
  PVOID *v9; // rcx
  char *v10; // rsi
  signed __int32 v11; // eax

  SockSanCleanupFlowControl();
  v2 = (void *)*((_QWORD *)P + 88);
  if ( v2 )
    RtlFreeHeap(SockPrivateHeap, 0, v2);
  SockSanDeallocateFCMemory(P);
  if ( *((_QWORD *)P + 64) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(P + 48));
    v3 = *((_QWORD *)P + 64);
    if ( v3 && !P[520] && (P[520] = 1, _InterlockedIncrement((volatile signed __int32 *)(v3 + 48)) == 2) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(P + 48));
      RtlFreeHeap(SockPrivateHeap, 0, *((PVOID *)P + 64));
    }
    else
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(P + 48));
    }
  }
  v4 = P;
  do
  {
    EnterCriticalSection(&SockSanListCritSec);
    v5 = (_QWORD *)*((_QWORD *)v4 + 27);
    v6 = *v5;
    if ( *(_QWORD **)(*v5 + 8LL) != v5 )
      goto LABEL_28;
    v7 = (_QWORD *)v5[1];
    if ( (_QWORD *)*v7 != v5 )
      goto LABEL_28;
    *v7 = v6;
    *(_QWORD *)(v6 + 8) = v7;
    LeaveCriticalSection(&SockSanListCritSec);
    v4 = (char *)*((_QWORD *)v4 + 3);
  }
  while ( v4 );
  EnterCriticalSection(&SockSanListCritSec);
  v8 = (char **)*((_QWORD *)P + 11);
  if ( v8[1] != P + 88 || (v9 = (PVOID *)*((_QWORD *)P + 12), *v9 != P + 88) )
LABEL_28:
    __fastfail(3u);
  *v9 = v8;
  v8[1] = (char *)v9;
  if ( (__int64 *)SockSanOpenList == &SockSanOpenList && (__int64 *)SockSanClosingList == &SockSanClosingList )
    LOBYTE(v4) = SockSanDeleteListCritSec != 0;
  LeaveCriticalSection(&SockSanListCritSec);
  do
  {
    v10 = (char *)*((_QWORD *)P + 3);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)P + 2) + 16LL), 0xFFFFFFFF) == 1 )
      SockSanFreeProvider(*((PVOID *)P + 2));
    SockSanCleanupListeningContext(P);
    DeleteCriticalSection((LPCRITICAL_SECTION)(P + 48));
    RtlFreeHeap(SockPrivateHeap, 0, *((PVOID *)P + 27));
    LOBYTE(v11) = RtlFreeHeap(SockPrivateHeap, 0, P);
    P = v10;
  }
  while ( v10 );
  if ( (_BYTE)v4 )
  {
    DeleteCriticalSection(&SockSanListCritSec);
    if ( !SockSanCacheCallbackRegistered )
      DeleteCriticalSection(&SockSanProvListCritSec);
    v11 = _InterlockedIncrement(&SockSanCleanUpCompleteCount);
    if ( v11 == 2 )
      LOBYTE(v11) = SetEvent(SockSanCleanUpCompleteEvent);
  }
  return v11;
}

```

## disassembly

```asm
0x18004d1d8  push    rbx
0x18004d1da  push    rsi
0x18004d1db  push    rdi
0x18004d1dc  push    r14
0x18004d1de  push    r15
0x18004d1e0  sub     rsp, 20h
0x18004d1e4  mov     rbx, rcx
0x18004d1e7  call    SockSanCleanupFlowControl
0x18004d1ec  mov     r8, [rbx+2C0h]; P
0x18004d1f3  test    r8, r8
0x18004d1f6  jz      short loc_18004D20D
0x18004d1f8  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004d1ff  xor     edx, edx; Flags
0x18004d201  call    cs:__imp_RtlFreeHeap
0x18004d208  nop     dword ptr [rax+rax+00h]
0x18004d20d  mov     rcx, rbx
0x18004d210  call    SockSanDeallocateFCMemory
0x18004d215  cmp     qword ptr [rbx+200h], 0
0x18004d21d  mov     r14d, 1
0x18004d223  jz      short loc_18004D2A0
0x18004d225  lea     rdi, [rbx+30h]
0x18004d229  mov     rcx, rdi; lpCriticalSection
0x18004d22c  call    cs:__imp_EnterCriticalSection
0x18004d233  nop     dword ptr [rax+rax+00h]
0x18004d238  mov     rcx, [rbx+200h]
0x18004d23f  test    rcx, rcx
0x18004d242  jz      short loc_18004D291
0x18004d244  cmp     byte ptr [rbx+208h], 0
0x18004d24b  jnz     short loc_18004D291
0x18004d24d  mov     [rbx+208h], r14b
0x18004d254  mov     eax, r14d
0x18004d257  lock xadd [rcx+30h], eax
0x18004d25c  add     eax, r14d
0x18004d25f  cmp     eax, 2
0x18004d262  jnz     short loc_18004D291
0x18004d264  mov     rcx, rdi; lpCriticalSection
0x18004d267  call    cs:__imp_LeaveCriticalSection
0x18004d26e  nop     dword ptr [rax+rax+00h]
0x18004d273  mov     r8, [rbx+200h]; P
0x18004d27a  xor     edx, edx; Flags
0x18004d27c  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004d283  call    cs:__imp_RtlFreeHeap
0x18004d28a  nop     dword ptr [rax+rax+00h]
0x18004d28f  jmp     short loc_18004D2A0
0x18004d291  mov     rcx, rdi; lpCriticalSection
0x18004d294  call    cs:__imp_LeaveCriticalSection
0x18004d29b  nop     dword ptr [rax+rax+00h]
0x18004d2a0  mov     rdi, rbx
0x18004d2a3  lea     r15, SockSanListCritSec
0x18004d2aa  mov     rcx, r15; lpCriticalSection
0x18004d2ad  call    cs:__imp_EnterCriticalSection
0x18004d2b4  nop     dword ptr [rax+rax+00h]
0x18004d2b9  mov     rax, [rdi+0D8h]
0x18004d2c0  mov     rdx, [rax]
0x18004d2c3  cmp     [rdx+8], rax
0x18004d2c7  jnz     loc_18004D440
0x18004d2cd  mov     rcx, [rax+8]
0x18004d2d1  cmp     [rcx], rax
0x18004d2d4  jnz     loc_18004D440
0x18004d2da  mov     [rcx], rdx
0x18004d2dd  mov     [rdx+8], rcx
0x18004d2e1  mov     rcx, r15; lpCriticalSection
0x18004d2e4  call    cs:__imp_LeaveCriticalSection
0x18004d2eb  nop     dword ptr [rax+rax+00h]
0x18004d2f0  mov     rdi, [rdi+18h]
0x18004d2f4  test    rdi, rdi
0x18004d2f7  jnz     short loc_18004D2AA
0x18004d2f9  mov     rcx, r15; lpCriticalSection
0x18004d2fc  call    cs:__imp_EnterCriticalSection
0x18004d303  nop     dword ptr [rax+rax+00h]
0x18004d308  lea     rax, [rbx+58h]
0x18004d30c  mov     rdx, [rax]
0x18004d30f  cmp     [rdx+8], rax
0x18004d313  jnz     loc_18004D440
0x18004d319  mov     rcx, [rax+8]
0x18004d31d  cmp     [rcx], rax
0x18004d320  jnz     loc_18004D440
0x18004d326  mov     [rcx], rdx
0x18004d329  lea     rax, SockSanOpenList
0x18004d330  mov     [rdx+8], rcx
0x18004d334  cmp     cs:SockSanOpenList, rax
0x18004d33b  jnz     short loc_18004D35C
0x18004d33d  lea     rax, SockSanClosingList
0x18004d344  cmp     cs:SockSanClosingList, rax
0x18004d34b  jnz     short loc_18004D35C
0x18004d34d  cmp     cs:SockSanDeleteListCritSec, 0
0x18004d354  movzx   edi, dil
0x18004d358  cmovnz  edi, r14d
0x18004d35c  mov     rcx, r15; lpCriticalSection
0x18004d35f  call    cs:__imp_LeaveCriticalSection
0x18004d366  nop     dword ptr [rax+rax+00h]
0x18004d36b  mov     rsi, [rbx+18h]
0x18004d36f  or      eax, 0FFFFFFFFh
0x18004d372  mov     rcx, [rbx+10h]
0x18004d376  lock xadd [rcx+10h], eax
0x18004d37b  cmp     eax, r14d
0x18004d37e  jnz     short loc_18004D389
0x18004d380  mov     rcx, [rbx+10h]; CompletionContext
0x18004d384  call    SockSanFreeProvider
0x18004d389  mov     rcx, rbx
0x18004d38c  call    SockSanCleanupListeningContext
0x18004d391  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004d395  call    cs:__imp_DeleteCriticalSection
0x18004d39c  nop     dword ptr [rax+rax+00h]
0x18004d3a1  mov     r8, [rbx+0D8h]; P
0x18004d3a8  xor     edx, edx; Flags
0x18004d3aa  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004d3b1  call    cs:__imp_RtlFreeHeap
0x18004d3b8  nop     dword ptr [rax+rax+00h]
0x18004d3bd  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004d3c4  mov     r8, rbx; P
0x18004d3c7  xor     edx, edx; Flags
0x18004d3c9  call    cs:__imp_RtlFreeHeap
0x18004d3d0  nop     dword ptr [rax+rax+00h]
0x18004d3d5  mov     rbx, rsi
0x18004d3d8  test    rsi, rsi
0x18004d3db  jnz     short loc_18004D36B
0x18004d3dd  test    dil, dil
0x18004d3e0  jz      short loc_18004D433
0x18004d3e2  mov     rcx, r15; lpCriticalSection
0x18004d3e5  call    cs:__imp_DeleteCriticalSection
0x18004d3ec  nop     dword ptr [rax+rax+00h]
0x18004d3f1  cmp     cs:SockSanCacheCallbackRegistered, sil
0x18004d3f8  jnz     short loc_18004D40D
0x18004d3fa  lea     rcx, SockSanProvListCritSec; lpCriticalSection
0x18004d401  call    cs:__imp_DeleteCriticalSection
0x18004d408  nop     dword ptr [rax+rax+00h]
0x18004d40d  mov     eax, r14d
0x18004d410  lock xadd cs:SockSanCleanUpCompleteCount, eax
0x18004d418  add     eax, r14d
0x18004d41b  cmp     eax, 2
0x18004d41e  jnz     short loc_18004D433
0x18004d420  mov     rcx, cs:SockSanCleanUpCompleteEvent; hEvent
0x18004d427  call    cs:__imp_SetEvent
0x18004d42e  nop     dword ptr [rax+rax+00h]
0x18004d433  add     rsp, 20h
0x18004d437  pop     r15
0x18004d439  pop     r14
0x18004d43b  pop     rdi
0x18004d43c  pop     rsi
0x18004d43d  pop     rbx
0x18004d43e  retn
0x18004d440  mov     ecx, 3
0x18004d445  int     29h; Win8: RtlFailFast(ecx)
```
