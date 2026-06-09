# SockSanCreateSocket

- ea: `0x18004cb1c`
- end: `0x18004cd87`
- name: `SockSanCreateSocket`
- size: `619`
- prototype: `__int64 __usercall@<rax>(PVOID CompletionContext@<rcx>, char)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044bc8`
- `0x18004e9dc`
- `0x18004eda0`

## callees

- `0x180008250`
- `0x180042b50`
- `0x18004cb1c`
- `0x18004cf28`
- `0x18004e718`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004cb4c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004cb4c`
- `ntdll!RtlFreeHeap` at `0x18004cd46`
- `ntdll!RtlFreeHeap` at `0x18004cd5e`
- `ntdll!RtlFreeHeap` at `0x18004cd46`
- `ntdll!RtlFreeHeap` at `0x18004cd5e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ccfa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ccfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ccea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ccea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cc84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cc84`

## pseudocode

```c
__int64 __fastcall SockSanCreateSocket(
        volatile signed __int32 *CompletionContext,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        char a5)
{
  __int64 *v9; // rsi
  _QWORD *Value; // r14
  __int64 result; // rax
  __int64 SwitchSocket; // rbx
  __int64 v13; // r13
  __int64 *v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  __int64 v20; // r8
  _QWORD *v21; // rdx
  unsigned int v22; // [rsp+40h] [rbp-58h] BYREF
  int v23[21]; // [rsp+44h] [rbp-54h] BYREF

  v22 = 0;
  v23[0] = 0;
  v9 = (__int64 *)(a2 + 264);
  Value = TlsGetValue(MSAFD_SockTlsSlot);
  if ( !a5 && *v9 )
    return 0;
  SwitchSocket = SockSanCreateSwitchSocket();
  if ( !SwitchSocket )
    return 8;
  if ( (*(_BYTE *)(a2 + 72) & 1) != 0 )
    *(_DWORD *)(SwitchSocket + 32) = 1;
  _InterlockedAdd((volatile signed __int32 *)a2, 1u);
  _InterlockedAdd((volatile signed __int32 *)a2, 1u);
  *(_QWORD *)SwitchSocket = a2;
  *(_QWORD *)(SwitchSocket + 8) = a2;
  *(_QWORD *)(SwitchSocket + 16) = CompletionContext;
  v13 = *v9;
  *v9 = SwitchSocket;
  _InterlockedAdd(CompletionContext + 4, 1u);
  Value[3] = SwitchSocket;
  v14 = SockTcpProviderInfo;
  v15 = *(unsigned int *)(a2 + 28);
  if ( (_DWORD)v15 != 2 )
    v14 = SockTcp6ProviderInfo;
  v16 = (*((__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *, _DWORD, unsigned int, unsigned int *))CompletionContext
         + 36))(
          v15,
          *(unsigned int *)(a2 + 32),
          *(unsigned int *)(a2 + 36),
          v14,
          *(_DWORD *)(a2 + 88),
          *(_DWORD *)(a2 + 72) | 1u,
          &v22);
  *(_QWORD *)(SwitchSocket + 104) = v16;
  if ( v16 != -1 )
  {
    if ( (*((unsigned int (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))CompletionContext + 11))(
           v16,
           a3,
           a4,
           &v22) != -1
      && !(unsigned int)SockSanSetSockOpts(a2) )
    {
      Value[3] = -1;
      return 0;
    }
    (*((void (__fastcall **)(_QWORD, int *))CompletionContext + 14))(*(_QWORD *)(SwitchSocket + 104), v23);
  }
  Value[3] = -1;
  *v9 = v13;
  if ( _InterlockedExchangeAdd(CompletionContext + 4, 0xFFFFFFFF) == 1 )
    SockSanFreeProvider((PVOID)CompletionContext);
  EnterCriticalSection(&SockSanListCritSec);
  v17 = *(_QWORD *)(SwitchSocket + 88);
  if ( *(_QWORD *)(v17 + 8) != SwitchSocket + 88
    || (v18 = *(_QWORD **)(SwitchSocket + 96), *v18 != SwitchSocket + 88)
    || (--NumOpenSanSocks,
        *v18 = v17,
        *(_QWORD *)(v17 + 8) = v18,
        v19 = *(_QWORD **)(SwitchSocket + 216),
        v20 = *v19,
        *(_QWORD **)(*v19 + 8LL) != v19)
    || (v21 = (_QWORD *)v19[1], (_QWORD *)*v21 != v19) )
  {
    __fastfail(3u);
  }
  *v21 = v20;
  *(_QWORD *)(v20 + 8) = v21;
  LeaveCriticalSection(&SockSanListCritSec);
  DeleteCriticalSection((LPCRITICAL_SECTION)(SwitchSocket + 48));
  if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)SwitchSocket, 0xFFFFFFFF) == 1 )
    SockDestroySocket(*(_QWORD *)SwitchSocket);
  if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)(SwitchSocket + 8), 0xFFFFFFFF) == 1 )
    SockDestroySocket(*(_QWORD *)(SwitchSocket + 8));
  RtlFreeHeap(SockPrivateHeap, 0, *(PVOID *)(SwitchSocket + 216));
  RtlFreeHeap(SockPrivateHeap, 0, (PVOID)SwitchSocket);
  result = v22;
  if ( !v22 )
    return 10107;
  return result;
}

```

## disassembly

```asm
0x18004cb1c  push    rbx
0x18004cb1e  push    rbp
0x18004cb1f  push    rsi
0x18004cb20  push    rdi
0x18004cb21  push    r12
0x18004cb23  push    r13
0x18004cb25  push    r14
0x18004cb27  push    r15
0x18004cb29  sub     rsp, 58h
0x18004cb2d  mov     rdi, rcx
0x18004cb30  xor     r13d, r13d
0x18004cb33  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18004cb39  mov     r15d, r9d
0x18004cb3c  mov     [rsp+98h+var_58], r13d
0x18004cb41  mov     r12, r8
0x18004cb44  mov     [rsp+98h+var_54], r13d
0x18004cb49  mov     rbp, rdx
0x18004cb4c  call    cs:__imp_TlsGetValue
0x18004cb53  nop     dword ptr [rax+rax+00h]
0x18004cb58  lea     rsi, [rbp+108h]
0x18004cb5f  mov     r14, rax
0x18004cb62  cmp     [rsp+98h+arg_20], r13b
0x18004cb6a  jnz     short loc_18004CB85
0x18004cb6c  cmp     [rsi], r13
0x18004cb6f  jz      short loc_18004CB85
0x18004cb71  xor     eax, eax
0x18004cb73  add     rsp, 58h
0x18004cb77  pop     r15
0x18004cb79  pop     r14
0x18004cb7b  pop     r13
0x18004cb7d  pop     r12
0x18004cb7f  pop     rdi
0x18004cb80  pop     rsi
0x18004cb81  pop     rbp
0x18004cb82  pop     rbx
0x18004cb83  retn
0x18004cb85  call    SockSanCreateSwitchSocket
0x18004cb8a  mov     rbx, rax
0x18004cb8d  test    rax, rax
0x18004cb90  jnz     short loc_18004CB97
0x18004cb92  lea     eax, [rbx+8]
0x18004cb95  jmp     short loc_18004CB73
0x18004cb97  mov     eax, 1
0x18004cb9c  test    [rbp+48h], al
0x18004cb9f  jz      short loc_18004CBA4
0x18004cba1  mov     [rbx+20h], eax
0x18004cba4  lock add [rbp+0], eax
0x18004cba8  lock add [rbp+0], eax
0x18004cbac  mov     [rbx], rbp
0x18004cbaf  mov     [rbx+8], rbp
0x18004cbb3  mov     [rbx+10h], rdi
0x18004cbb7  mov     r13, [rsi]
0x18004cbba  mov     [rsi], rbx
0x18004cbbd  lock add [rdi+10h], eax
0x18004cbc1  mov     [r14+18h], rbx
0x18004cbc5  lea     r9, SockTcpProviderInfo
0x18004cbcc  mov     edx, [rbp+48h]
0x18004cbcf  mov     ecx, [rbp+1Ch]
0x18004cbd2  or      edx, eax
0x18004cbd4  mov     r8d, [rbp+24h]
0x18004cbd8  lea     rax, SockTcp6ProviderInfo
0x18004cbdf  cmp     ecx, 2
0x18004cbe2  cmovnz  r9, rax
0x18004cbe6  lea     rax, [rsp+98h+var_58]
0x18004cbeb  mov     [rsp+98h+var_68], rax
0x18004cbf0  mov     rax, [rdi+120h]
0x18004cbf7  mov     [rsp+98h+var_70], edx
0x18004cbfb  mov     edx, [rbp+58h]
0x18004cbfe  mov     [rsp+98h+var_78], edx
0x18004cc02  mov     edx, [rbp+20h]
0x18004cc05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc0a  mov     [rbx+68h], rax
0x18004cc0e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004cc12  jz      short loc_18004CC5D
0x18004cc14  mov     rcx, rax
0x18004cc17  lea     r9, [rsp+98h+var_58]
0x18004cc1c  mov     rax, [rdi+58h]
0x18004cc20  mov     r8d, r15d
0x18004cc23  mov     rdx, r12
0x18004cc26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc2b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004cc2f  cmp     eax, r15d
0x18004cc32  jz      short loc_18004CC49
0x18004cc34  mov     rcx, rbp
0x18004cc37  call    SockSanSetSockOpts
0x18004cc3c  test    eax, eax
0x18004cc3e  jnz     short loc_18004CC49
0x18004cc40  mov     [r14+18h], r15
0x18004cc44  jmp     loc_18004CB71
0x18004cc49  mov     rcx, [rbx+68h]
0x18004cc4d  lea     rdx, [rsp+98h+var_54]
0x18004cc52  mov     rax, [rdi+70h]
0x18004cc56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc5b  jmp     short loc_18004CC61
0x18004cc5d  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004cc61  mov     [r14+18h], r15
0x18004cc65  mov     eax, r15d
0x18004cc68  mov     [rsi], r13
0x18004cc6b  lock xadd [rdi+10h], eax
0x18004cc70  add     eax, r15d
0x18004cc73  jnz     short loc_18004CC7D
0x18004cc75  mov     rcx, rdi; CompletionContext
0x18004cc78  call    SockSanFreeProvider
0x18004cc7d  lea     rcx, SockSanListCritSec; lpCriticalSection
0x18004cc84  call    cs:__imp_EnterCriticalSection
0x18004cc8b  nop     dword ptr [rax+rax+00h]
0x18004cc90  lea     rax, [rbx+58h]
0x18004cc94  mov     rdx, [rax]
0x18004cc97  cmp     [rdx+8], rax
0x18004cc9b  jnz     loc_18004CD80
0x18004cca1  mov     rcx, [rax+8]
0x18004cca5  cmp     [rcx], rax
0x18004cca8  jnz     loc_18004CD80
0x18004ccae  dec     cs:NumOpenSanSocks
0x18004ccb4  mov     [rcx], rdx
0x18004ccb7  mov     [rdx+8], rcx
0x18004ccbb  mov     rax, [rbx+0D8h]
0x18004ccc2  mov     r8, [rax]
0x18004ccc5  cmp     [r8+8], rax
0x18004ccc9  jnz     loc_18004CD80
0x18004cccf  mov     rdx, [rax+8]
0x18004ccd3  cmp     [rdx], rax
0x18004ccd6  jnz     loc_18004CD80
0x18004ccdc  mov     [rdx], r8
0x18004ccdf  lea     rcx, SockSanListCritSec; lpCriticalSection
0x18004cce6  mov     [r8+8], rdx
0x18004ccea  call    cs:__imp_LeaveCriticalSection
0x18004ccf1  nop     dword ptr [rax+rax+00h]
0x18004ccf6  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004ccfa  call    cs:__imp_DeleteCriticalSection
0x18004cd01  nop     dword ptr [rax+rax+00h]
0x18004cd06  mov     rax, [rbx]
0x18004cd09  mov     ecx, r15d
0x18004cd0c  lock xadd [rax], ecx
0x18004cd10  add     ecx, r15d
0x18004cd13  jnz     short loc_18004CD1D
0x18004cd15  mov     rcx, [rbx]
0x18004cd18  call    SockDestroySocket
0x18004cd1d  mov     rax, [rbx+8]
0x18004cd21  mov     ecx, r15d
0x18004cd24  lock xadd [rax], ecx
0x18004cd28  add     ecx, r15d
0x18004cd2b  jnz     short loc_18004CD36
0x18004cd2d  mov     rcx, [rbx+8]
0x18004cd31  call    SockDestroySocket
0x18004cd36  mov     r8, [rbx+0D8h]; P
0x18004cd3d  xor     edx, edx; Flags
0x18004cd3f  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004cd46  call    cs:__imp_RtlFreeHeap
0x18004cd4d  nop     dword ptr [rax+rax+00h]
0x18004cd52  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004cd59  mov     r8, rbx; P
0x18004cd5c  xor     edx, edx; Flags
0x18004cd5e  call    cs:__imp_RtlFreeHeap
0x18004cd65  nop     dword ptr [rax+rax+00h]
0x18004cd6a  mov     eax, [rsp+98h+var_58]
0x18004cd6e  test    eax, eax
0x18004cd70  jnz     loc_18004CB73
0x18004cd76  mov     eax, 277Bh
0x18004cd7b  jmp     loc_18004CB73
0x18004cd80  mov     ecx, 3
0x18004cd85  int     29h; Win8: RtlFailFast(ecx)
```
