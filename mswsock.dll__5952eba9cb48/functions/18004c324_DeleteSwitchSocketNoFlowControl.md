# DeleteSwitchSocketNoFlowControl

- ea: `0x18004c324`
- end: `0x18004c4af`
- name: `DeleteSwitchSocketNoFlowControl`
- size: `395`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18004d164`
- `0x18004eda0`

## callees

- `0x180008250`
- `0x1800248a0`
- `0x180042b50`
- `0x18004c324`
- `0x18004c94c`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004c476`
- `ntdll!RtlFreeHeap` at `0x18004c48e`
- `ntdll!RtlFreeHeap` at `0x18004c476`
- `ntdll!RtlFreeHeap` at `0x18004c48e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c45a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c45a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c3ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c3ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c383`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c383`

## pseudocode

```c
__int64 __fastcall DeleteSwitchSocketNoFlowControl(char *P)
{
  __int64 v1; // rax
  char **v3; // rdx
  PVOID *v4; // rcx
  _QWORD *v5; // rax
  __int64 v6; // r8
  _QWORD *v7; // rdx
  bool v8; // bp
  volatile signed __int32 *v9; // rdi
  volatile signed __int32 *v10; // rsi
  unsigned int v12; // [rsp+50h] [rbp+8h] BYREF

  v1 = *((_QWORD *)P + 2);
  v12 = 0;
  if ( (*(unsigned int (__fastcall **)(_QWORD, unsigned int *))(v1 + 112))(*((_QWORD *)P + 13), &v12) == -1 && !v12 )
    v12 = 10107;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)P + 2) + 16LL), 0xFFFFFFFF) == 1 )
    SockSanFreeProvider(*((PVOID *)P + 2));
  EnterCriticalSection(&SockSanListCritSec);
  v3 = (char **)*((_QWORD *)P + 11);
  if ( v3[1] != P + 88
    || (v4 = (PVOID *)*((_QWORD *)P + 12), *v4 != P + 88)
    || (--NumOpenSanSocks,
        *v4 = v3,
        v3[1] = (char *)v4,
        v5 = (_QWORD *)*((_QWORD *)P + 27),
        v6 = *v5,
        *(_QWORD **)(*v5 + 8LL) != v5)
    || (v7 = (_QWORD *)v5[1], (_QWORD *)*v7 != v5) )
  {
    __fastfail(3u);
  }
  *v7 = v6;
  *(_QWORD *)(v6 + 8) = v7;
  v8 = 0;
  LeaveCriticalSection(&SockSanListCritSec);
  SockSanCleanupListeningContext(P);
  v9 = (volatile signed __int32 *)*((_QWORD *)P + 1);
  v10 = *(volatile signed __int32 **)P;
  if ( _InterlockedIncrement((volatile signed __int32 *)P + 208) == 2 )
    v8 = (unsigned __int8)SockSanCheckForConnectListReference(P) == 0;
  if ( _InterlockedExchangeAdd(v10, 0xFFFFFFFF) == 1 )
    SockDestroySocket(v10);
  if ( _InterlockedExchangeAdd(v9, 0xFFFFFFFF) == 1 )
    SockDestroySocket(v9);
  if ( v8 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(P + 48));
    RtlFreeHeap(SockPrivateHeap, 0, *((PVOID *)P + 27));
    RtlFreeHeap(SockPrivateHeap, 0, P);
  }
  return v12;
}

```

## disassembly

```asm
0x18004c324  push    rbx
0x18004c326  push    rbp
0x18004c327  push    rsi
0x18004c328  push    rdi
0x18004c329  sub     rsp, 28h
0x18004c32d  mov     rax, [rcx+10h]
0x18004c331  lea     rdx, [rsp+48h+arg_0]
0x18004c336  mov     rbx, rcx
0x18004c339  mov     [rsp+48h+arg_0], 0
0x18004c341  mov     rcx, [rcx+68h]
0x18004c345  mov     rax, [rax+70h]
0x18004c349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c34e  cmp     eax, 0FFFFFFFFh
0x18004c351  jnz     short loc_18004C362
0x18004c353  cmp     [rsp+48h+arg_0], 0
0x18004c358  jnz     short loc_18004C362
0x18004c35a  mov     [rsp+48h+arg_0], 277Bh
0x18004c362  mov     rcx, [rbx+10h]
0x18004c366  or      eax, 0FFFFFFFFh
0x18004c369  lock xadd [rcx+10h], eax
0x18004c36e  cmp     eax, 1
0x18004c371  jnz     short loc_18004C37C
0x18004c373  mov     rcx, [rbx+10h]; CompletionContext
0x18004c377  call    SockSanFreeProvider
0x18004c37c  lea     rcx, SockSanListCritSec; lpCriticalSection
0x18004c383  call    cs:__imp_EnterCriticalSection
0x18004c38a  nop     dword ptr [rax+rax+00h]
0x18004c38f  lea     rax, [rbx+58h]
0x18004c393  mov     rdx, [rax]
0x18004c396  cmp     [rdx+8], rax
0x18004c39a  jnz     loc_18004C4A8
0x18004c3a0  mov     rcx, [rax+8]
0x18004c3a4  cmp     [rcx], rax
0x18004c3a7  jnz     loc_18004C4A8
0x18004c3ad  dec     cs:NumOpenSanSocks
0x18004c3b3  mov     [rcx], rdx
0x18004c3b6  mov     [rdx+8], rcx
0x18004c3ba  mov     rax, [rbx+0D8h]
0x18004c3c1  mov     r8, [rax]
0x18004c3c4  cmp     [r8+8], rax
0x18004c3c8  jnz     loc_18004C4A8
0x18004c3ce  mov     rdx, [rax+8]
0x18004c3d2  cmp     [rdx], rax
0x18004c3d5  jnz     loc_18004C4A8
0x18004c3db  mov     [rdx], r8
0x18004c3de  lea     rcx, SockSanListCritSec; lpCriticalSection
0x18004c3e5  mov     [r8+8], rdx
0x18004c3e9  xor     bpl, bpl
0x18004c3ec  call    cs:__imp_LeaveCriticalSection
0x18004c3f3  nop     dword ptr [rax+rax+00h]
0x18004c3f8  mov     rcx, rbx
0x18004c3fb  call    SockSanCleanupListeningContext
0x18004c400  mov     rdi, [rbx+8]
0x18004c404  mov     eax, 1
0x18004c409  mov     rsi, [rbx]
0x18004c40c  lock xadd [rbx+340h], eax
0x18004c414  inc     eax
0x18004c416  cmp     eax, 2
0x18004c419  jnz     short loc_18004C429
0x18004c41b  mov     rcx, rbx
0x18004c41e  call    SockSanCheckForConnectListReference
0x18004c423  test    al, al
0x18004c425  setz    bpl
0x18004c429  or      eax, 0FFFFFFFFh
0x18004c42c  lock xadd [rsi], eax
0x18004c430  cmp     eax, 1
0x18004c433  jnz     short loc_18004C43D
0x18004c435  mov     rcx, rsi
0x18004c438  call    SockDestroySocket
0x18004c43d  or      eax, 0FFFFFFFFh
0x18004c440  lock xadd [rdi], eax
0x18004c444  cmp     eax, 1
0x18004c447  jnz     short loc_18004C451
0x18004c449  mov     rcx, rdi
0x18004c44c  call    SockDestroySocket
0x18004c451  test    bpl, bpl
0x18004c454  jz      short loc_18004C49A
0x18004c456  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004c45a  call    cs:__imp_DeleteCriticalSection
0x18004c461  nop     dword ptr [rax+rax+00h]
0x18004c466  mov     r8, [rbx+0D8h]; P
0x18004c46d  xor     edx, edx; Flags
0x18004c46f  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004c476  call    cs:__imp_RtlFreeHeap
0x18004c47d  nop     dword ptr [rax+rax+00h]
0x18004c482  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004c489  mov     r8, rbx; P
0x18004c48c  xor     edx, edx; Flags
0x18004c48e  call    cs:__imp_RtlFreeHeap
0x18004c495  nop     dword ptr [rax+rax+00h]
0x18004c49a  mov     eax, [rsp+48h+arg_0]
0x18004c49e  add     rsp, 28h
0x18004c4a2  pop     rdi
0x18004c4a3  pop     rsi
0x18004c4a4  pop     rbp
0x18004c4a5  pop     rbx
0x18004c4a6  retn
0x18004c4a8  mov     ecx, 3
0x18004c4ad  int     29h; Win8: RtlFailFast(ecx)
```
