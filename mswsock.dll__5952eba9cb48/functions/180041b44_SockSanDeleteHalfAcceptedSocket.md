# SockSanDeleteHalfAcceptedSocket

- ea: `0x180041b44`
- end: `0x180041d47`
- name: `SockSanDeleteHalfAcceptedSocket`
- size: `515`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `7`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18003b760`
- `0x18003d540`
- `0x1800497d4`
- `0x18004abd0`
- `0x1800514d0`
- `0x180051a68`
- `0x180051f1c`

## callees

- `0x180008250`
- `0x180038118`
- `0x180041b44`
- `0x180041d50`
- `0x180042128`
- `0x180042b50`
- `0x1800507fc`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180041cee`
- `ntdll!RtlFreeHeap` at `0x180041d06`
- `ntdll!RtlFreeHeap` at `0x180041cee`
- `ntdll!RtlFreeHeap` at `0x180041d06`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041b66`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041cd2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041b66`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041cd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041bc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041c73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041bc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041c73`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041b86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041c0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041b86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041c0d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180041cac`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180041cac`

## pseudocode

```c
void __fastcall SockSanDeleteHalfAcceptedSocket(char *P)
{
  _QWORD *v2; // rsi
  __int64 v3; // rdi
  _QWORD *v4; // rax
  __int64 v5; // rdx
  char **v6; // rdx
  PVOID *v7; // rcx
  _QWORD *v8; // rax
  __int64 v9; // r8
  _QWORD *v10; // rdx
  int i; // edi

  if ( !*(_QWORD *)P || *((_QWORD *)P + 1) )
  {
    v2 = (_QWORD *)*((_QWORD *)P + 85);
    v3 = v2[2];
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
    v4 = (_QWORD *)(v3 + 680);
    v2[3] = 0;
    v5 = *(_QWORD *)(v3 + 680);
    if ( *(_QWORD *)(v5 + 8) != v3 + 680 )
      goto LABEL_24;
    *v2 = v5;
    v2[1] = v4;
    *(_QWORD *)(v5 + 8) = v2;
    *v4 = v2;
    --*(_DWORD *)(v3 + 676);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
    if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)(v3 + 8), 0xFFFFFFFF) == 1 )
      SockDestroySocket(*(_QWORD *)(v3 + 8));
    *((_DWORD *)P + 42) = 0;
    AbortSanConnection(P);
    SockSanCleanupFlowControl(P);
    EnterCriticalSection(&SockSanListCritSec);
    v6 = (char **)*((_QWORD *)P + 11);
    if ( v6[1] != P + 88
      || (v7 = (PVOID *)*((_QWORD *)P + 12), *v7 != P + 88)
      || (--NumOpenSanSocks,
          *v7 = v6,
          v6[1] = (char *)v7,
          v8 = (_QWORD *)*((_QWORD *)P + 27),
          v9 = *v8,
          *(_QWORD **)(*v8 + 8LL) != v8)
      || (v10 = (_QWORD *)v8[1], (_QWORD *)*v10 != v8) )
    {
LABEL_24:
      __fastfail(3u);
    }
    *v10 = v9;
    *(_QWORD *)(v9 + 8) = v10;
    LeaveCriticalSection(&SockSanListCritSec);
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)P + 2) + 16LL)) )
      SockSanFreeProvider(*((PVOID *)P + 2));
    for ( i = 0; i < 20; ++i )
    {
      if ( *((_DWORD *)P + 42) == 3 )
        goto LABEL_19;
      Sleep(1u);
    }
    if ( i != 20 )
      return;
    if ( _InterlockedExchange((volatile __int32 *)P + 42, 4) == 3 )
    {
LABEL_19:
      DeleteCriticalSection((LPCRITICAL_SECTION)(P + 48));
      RtlFreeHeap(SockPrivateHeap, 0, *((PVOID *)P + 27));
      goto LABEL_20;
    }
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_q(1025, 34, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids, P);
  }
  else
  {
    SockSanDeallocateFCMemory(P);
    DeleteCriticalSection((LPCRITICAL_SECTION)(P + 48));
LABEL_20:
    RtlFreeHeap(SockPrivateHeap, 0, P);
  }
}

```

## disassembly

```asm
0x180041b44  push    rbx
0x180041b46  push    rbp
0x180041b47  push    rsi
0x180041b48  push    rdi
0x180041b49  sub     rsp, 28h
0x180041b4d  cmp     qword ptr [rcx], 0
0x180041b51  mov     rbx, rcx
0x180041b54  jz      short loc_180041B77
0x180041b56  cmp     qword ptr [rcx+8], 0
0x180041b5b  jnz     short loc_180041B77
0x180041b5d  call    SockSanDeallocateFCMemory
0x180041b62  lea     rcx, [rbx+30h]; lpCriticalSection
0x180041b66  call    cs:__imp_DeleteCriticalSection
0x180041b6d  nop     dword ptr [rax+rax+00h]
0x180041b72  jmp     loc_180041CFA
0x180041b77  mov     rsi, [rcx+2A8h]
0x180041b7e  mov     rdi, [rsi+10h]
0x180041b82  lea     rcx, [rdi+30h]; lpCriticalSection
0x180041b86  call    cs:__imp_EnterCriticalSection
0x180041b8d  nop     dword ptr [rax+rax+00h]
0x180041b92  lea     rax, [rdi+2A8h]
0x180041b99  mov     qword ptr [rsi+18h], 0
0x180041ba1  mov     rdx, [rax]
0x180041ba4  cmp     [rdx+8], rax
0x180041ba8  jnz     loc_180041D40
0x180041bae  mov     [rsi], rdx
0x180041bb1  lea     rcx, [rdi+30h]; lpCriticalSection
0x180041bb5  mov     [rsi+8], rax
0x180041bb9  mov     [rdx+8], rsi
0x180041bbd  mov     [rax], rsi
0x180041bc0  or      esi, 0FFFFFFFFh
0x180041bc3  add     [rdi+2A4h], esi
0x180041bc9  call    cs:__imp_LeaveCriticalSection
0x180041bd0  nop     dword ptr [rax+rax+00h]
0x180041bd5  mov     rax, [rdi+8]
0x180041bd9  mov     ecx, esi
0x180041bdb  lock xadd [rax], ecx
0x180041bdf  add     ecx, esi
0x180041be1  jnz     short loc_180041BEC
0x180041be3  mov     rcx, [rdi+8]
0x180041be7  call    SockDestroySocket
0x180041bec  mov     rcx, rbx
0x180041bef  mov     dword ptr [rbx+0A8h], 0
0x180041bf9  call    AbortSanConnection
0x180041bfe  mov     rcx, rbx
0x180041c01  call    SockSanCleanupFlowControl
0x180041c06  lea     rcx, SockSanListCritSec; lpCriticalSection
0x180041c0d  call    cs:__imp_EnterCriticalSection
0x180041c14  nop     dword ptr [rax+rax+00h]
0x180041c19  lea     rax, [rbx+58h]
0x180041c1d  mov     rdx, [rax]
0x180041c20  cmp     [rdx+8], rax
0x180041c24  jnz     loc_180041D40
0x180041c2a  mov     rcx, [rax+8]
0x180041c2e  cmp     [rcx], rax
0x180041c31  jnz     loc_180041D40
0x180041c37  dec     cs:NumOpenSanSocks
0x180041c3d  mov     [rcx], rdx
0x180041c40  mov     [rdx+8], rcx
0x180041c44  mov     rax, [rbx+0D8h]
0x180041c4b  mov     r8, [rax]
0x180041c4e  cmp     [r8+8], rax
0x180041c52  jnz     loc_180041D40
0x180041c58  mov     rdx, [rax+8]
0x180041c5c  cmp     [rdx], rax
0x180041c5f  jnz     loc_180041D40
0x180041c65  mov     [rdx], r8
0x180041c68  lea     rcx, SockSanListCritSec; lpCriticalSection
0x180041c6f  mov     [r8+8], rdx
0x180041c73  call    cs:__imp_LeaveCriticalSection
0x180041c7a  nop     dword ptr [rax+rax+00h]
0x180041c7f  mov     rcx, [rbx+10h]
0x180041c83  mov     eax, esi
0x180041c85  lock xadd [rcx+10h], eax
0x180041c8a  add     eax, esi
0x180041c8c  jnz     short loc_180041C97
0x180041c8e  mov     rcx, [rbx+10h]; CompletionContext
0x180041c92  call    SockSanFreeProvider
0x180041c97  xor     edi, edi
0x180041c99  cmp     edi, 14h
0x180041c9c  jge     short loc_180041CBC
0x180041c9e  cmp     dword ptr [rbx+0A8h], 3
0x180041ca5  jz      short loc_180041CCE
0x180041ca7  mov     ecx, 1; dwMilliseconds
0x180041cac  call    cs:__imp_Sleep
0x180041cb3  nop     dword ptr [rax+rax+00h]
0x180041cb8  inc     edi
0x180041cba  jmp     short loc_180041C99
0x180041cbc  jnz     short loc_180041D12
0x180041cbe  mov     eax, 4
0x180041cc3  xchg    eax, [rbx+0A8h]
0x180041cc9  cmp     eax, 3
0x180041ccc  jnz     short loc_180041D1C
0x180041cce  lea     rcx, [rbx+30h]; lpCriticalSection
0x180041cd2  call    cs:__imp_DeleteCriticalSection
0x180041cd9  nop     dword ptr [rax+rax+00h]
0x180041cde  mov     r8, [rbx+0D8h]; P
0x180041ce5  xor     edx, edx; Flags
0x180041ce7  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180041cee  call    cs:__imp_RtlFreeHeap
0x180041cf5  nop     dword ptr [rax+rax+00h]
0x180041cfa  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180041d01  mov     r8, rbx; P
0x180041d04  xor     edx, edx; Flags
0x180041d06  call    cs:__imp_RtlFreeHeap
0x180041d0d  nop     dword ptr [rax+rax+00h]
0x180041d12  add     rsp, 28h
0x180041d16  pop     rdi
0x180041d17  pop     rsi
0x180041d18  pop     rbp
0x180041d19  pop     rbx
0x180041d1a  retn
0x180041d1c  test    byte ptr cs:xmmword_180063D60, 2
0x180041d23  jz      short loc_180041D12
0x180041d25  mov     edx, 22h ; '"'
0x180041d2a  lea     r8, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids
0x180041d31  mov     ecx, 401h
0x180041d36  mov     r9, rbx
0x180041d39  call    WPP_SF_q
0x180041d3e  jmp     short loc_180041D12
0x180041d40  mov     ecx, 3
0x180041d45  int     29h; Win8: RtlFailFast(ecx)
```
