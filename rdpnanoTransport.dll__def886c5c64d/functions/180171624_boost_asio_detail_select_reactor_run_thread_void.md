# boost::asio::detail::select_reactor::run_thread(void)

- ea: `0x180171624`
- end: `0x180171830`
- name: `?run_thread@select_reactor@detail@asio@boost@@AEAAXXZ`
- size: `524`
- prototype: `void __fastcall(boost::asio::detail::select_reactor *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180171120`

## callees

- `0x18017113c`
- `0x180171624`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## import_xrefs

- `KERNEL32!PostQueuedCompletionStatus` at `0x1801716ec`
- `KERNEL32!PostQueuedCompletionStatus` at `0x1801716ec`
- `KERNEL32!EnterCriticalSection` at `0x180171668`
- `KERNEL32!EnterCriticalSection` at `0x1801716fa`
- `KERNEL32!EnterCriticalSection` at `0x180171789`
- `KERNEL32!EnterCriticalSection` at `0x180171668`
- `KERNEL32!EnterCriticalSection` at `0x1801716fa`
- `KERNEL32!EnterCriticalSection` at `0x180171789`
- `KERNEL32!LeaveCriticalSection` at `0x180171685`
- `KERNEL32!LeaveCriticalSection` at `0x180171762`
- `KERNEL32!LeaveCriticalSection` at `0x180171800`
- `KERNEL32!LeaveCriticalSection` at `0x180171685`
- `KERNEL32!LeaveCriticalSection` at `0x180171762`
- `KERNEL32!LeaveCriticalSection` at `0x180171800`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall boost::asio::detail::select_reactor::run_thread(boost::asio::detail::select_reactor *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  __int64 v3; // rsi
  LPOVERLAPPED v4; // rbx
  LPOVERLAPPED v5; // rcx
  LPOVERLAPPED v6; // r15
  __int64 v7; // rax
  LPOVERLAPPED v8; // r10
  LPOVERLAPPED v9; // rcx
  LPOVERLAPPED v10; // rax
  __int128 v11; // [rsp+40h] [rbp-30h] BYREF
  __int64 v12; // [rsp+50h] [rbp-20h]
  LPOVERLAPPED lpOverlapped[2]; // [rsp+58h] [rbp-18h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  while ( !*((_BYTE *)this + 416) )
  {
    LeaveCriticalSection(v2);
    *(_OWORD *)lpOverlapped = 0;
    boost::asio::detail::select_reactor::run(this, 0xFFFFFFFFLL, lpOverlapped);
    v3 = *((_QWORD *)this + 6);
    v4 = lpOverlapped[0];
    if ( lpOverlapped[0] )
    {
      v5 = lpOverlapped[0];
      v6 = lpOverlapped[0];
      do
      {
        lpOverlapped[0] = (LPOVERLAPPED)v6[1].Internal;
        lpOverlapped[1] = (LPOVERLAPPED)((unsigned __int64)lpOverlapped[1] & -(__int64)(lpOverlapped[0] != 0));
        v5[1].Internal = 0;
        v4[1].Offset = 1;
        if ( !PostQueuedCompletionStatus(*(HANDLE *)(v3 + 48), 0, 0, v4) )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 104));
          v4[1].Internal = 0;
          v7 = *(_QWORD *)(v3 + 160);
          if ( v7 )
            *(_QWORD *)(v7 + 32) = v4;
          else
            *(_QWORD *)(v3 + 152) = v4;
          *(_QWORD *)(v3 + 160) = v6;
          if ( lpOverlapped[0] )
          {
            if ( v6 )
              v6[1].Internal = (ULONG_PTR)lpOverlapped[0];
            else
              *(LPOVERLAPPED *)(v3 + 152) = lpOverlapped[0];
            *(LPOVERLAPPED *)(v3 + 160) = lpOverlapped[1];
            *(_OWORD *)lpOverlapped = 0;
          }
          _InterlockedExchange((volatile __int32 *)(v3 + 96), 1);
          LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 104));
        }
        v4 = lpOverlapped[0];
        v6 = lpOverlapped[0];
        v5 = lpOverlapped[0];
      }
      while ( lpOverlapped[0] );
    }
    EnterCriticalSection(v2);
    v8 = lpOverlapped[0];
    if ( lpOverlapped[0] )
    {
      v9 = lpOverlapped[0];
      v10 = lpOverlapped[0];
      do
      {
        lpOverlapped[0] = (LPOVERLAPPED)v10[1].Internal;
        lpOverlapped[1] = (LPOVERLAPPED)((unsigned __int64)lpOverlapped[1] & -(__int64)(lpOverlapped[0] != 0));
        v9[1].Internal = 0;
        v11 = 0;
        v12 = 0;
        ((void (__fastcall *)(_QWORD, LPOVERLAPPED, __int128 *, _QWORD))v8[1].InternalHigh)(0, v8, &v11, 0);
        v8 = lpOverlapped[0];
        v10 = lpOverlapped[0];
        v9 = lpOverlapped[0];
      }
      while ( lpOverlapped[0] );
    }
  }
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180171624  mov     [rsp-28h+arg_8], rbx
0x180171629  mov     [rsp-28h+arg_10], rsi
0x18017162e  mov     [rsp-28h+arg_18], rdi
0x180171633  push    rbp
0x180171634  push    r12
0x180171636  push    r13
0x180171638  push    r14
0x18017163a  push    r15
0x18017163c  mov     rbp, rsp
0x18017163f  mov     eax, 70h
0x180171644  call    _alloca_probe
0x180171649  sub     rsp, rax
0x18017164c  mov     rax, cs:__security_cookie
0x180171653  xor     rax, rsp
0x180171656  mov     [rbp+var_8], rax
0x18017165a  mov     r13, rcx
0x18017165d  lea     r14, [rcx+38h]
0x180171661  mov     [rbp+var_40], r14
0x180171665  mov     rcx, r14; lpCriticalSection
0x180171668  call    cs:__imp_EnterCriticalSection
0x18017166e  mov     dil, 1
0x180171671  mov     [rbp+var_38], dil
0x180171675  xor     r12d, r12d
0x180171678  jmp     loc_1801717EB
0x18017167d  test    dil, dil
0x180171680  jz      short loc_180171692
0x180171682  mov     rcx, r14; lpCriticalSection
0x180171685  call    cs:__imp_LeaveCriticalSection
0x18017168b  mov     dil, r12b
0x18017168e  mov     [rbp+var_38], r12b
0x180171692  xorps   xmm1, xmm1
0x180171695  movdqu  xmmword ptr [rbp+lpOverlapped], xmm1
0x18017169a  lea     r8, [rbp+lpOverlapped]
0x18017169e  or      edx, 0FFFFFFFFh
0x1801716a1  mov     rcx, r13
0x1801716a4  call    ?run@select_reactor@detail@asio@boost@@QEAAXJAEAV?$op_queue@Vwin_iocp_operation@detail@asio@boost@@@234@@Z; boost::asio::detail::select_reactor::run(long,boost::asio::detail::op_queue<boost::asio::detail::win_iocp_operation> &)
0x1801716a9  mov     rsi, [r13+30h]
0x1801716ad  mov     r10, [rbp+lpOverlapped]
0x1801716b1  mov     rbx, r10
0x1801716b4  test    r10, r10
0x1801716b7  jz      loc_180171781
0x1801716bd  mov     rcx, rbx
0x1801716c0  mov     r15, rbx
0x1801716c3  mov     rax, [r15+20h]
0x1801716c7  mov     [rbp+lpOverlapped], rax
0x1801716cb  neg     rax
0x1801716ce  sbb     rax, rax
0x1801716d1  and     [rbp+lpOverlapped+8], rax
0x1801716d5  mov     [rcx+20h], r12
0x1801716d9  mov     dword ptr [rbx+30h], 1
0x1801716e0  mov     r9, rbx; lpOverlapped
0x1801716e3  xor     r8d, r8d; dwCompletionKey
0x1801716e6  xor     edx, edx; dwNumberOfBytesTransferred
0x1801716e8  mov     rcx, [rsi+30h]; CompletionPort
0x1801716ec  call    cs:__imp_PostQueuedCompletionStatus
0x1801716f2  test    eax, eax
0x1801716f4  jnz     short loc_18017176B
0x1801716f6  lea     rcx, [rsi+68h]; lpCriticalSection
0x1801716fa  call    cs:__imp_EnterCriticalSection
0x180171700  mov     qword ptr [rbx+20h], 0
0x180171708  mov     rax, [rsi+0A0h]
0x18017170f  test    rax, rax
0x180171712  jz      short loc_18017171A
0x180171714  mov     [rax+20h], rbx
0x180171718  jmp     short loc_180171721
0x18017171a  mov     [rsi+98h], rbx
0x180171721  mov     [rsi+0A0h], r15
0x180171728  mov     rax, [rbp+lpOverlapped]
0x18017172c  test    rax, rax
0x18017172f  jz      short loc_180171756
0x180171731  test    r15, r15
0x180171734  jz      short loc_18017173C
0x180171736  mov     [r15+20h], rax
0x18017173a  jmp     short loc_180171743
0x18017173c  mov     [rsi+98h], rax
0x180171743  mov     rax, [rbp+lpOverlapped+8]
0x180171747  mov     [rsi+0A0h], rax
0x18017174e  xorps   xmm0, xmm0
0x180171751  movdqu  xmmword ptr [rbp+lpOverlapped], xmm0
0x180171756  mov     eax, 1
0x18017175b  xchg    eax, [rsi+60h]
0x18017175e  lea     rcx, [rsi+68h]; lpCriticalSection
0x180171762  call    cs:__imp_LeaveCriticalSection
0x180171768  xor     r12d, r12d
0x18017176b  mov     r10, [rbp+lpOverlapped]
0x18017176f  mov     rbx, r10
0x180171772  mov     r15, r10
0x180171775  mov     rcx, r10
0x180171778  test    r10, r10
0x18017177b  jnz     loc_1801716C3
0x180171781  test    dil, dil
0x180171784  jnz     short loc_18017179A
0x180171786  mov     rcx, r14; lpCriticalSection
0x180171789  call    cs:__imp_EnterCriticalSection
0x18017178f  mov     dil, 1
0x180171792  mov     [rbp+var_38], dil
0x180171796  mov     r10, [rbp+lpOverlapped]
0x18017179a  test    r10, r10
0x18017179d  jz      short loc_1801717EB
0x18017179f  mov     rcx, r10
0x1801717a2  mov     rax, r10
0x1801717a5  mov     rax, [rax+20h]
0x1801717a9  mov     [rbp+lpOverlapped], rax
0x1801717ad  neg     rax
0x1801717b0  sbb     rax, rax
0x1801717b3  and     [rbp+lpOverlapped+8], rax
0x1801717b7  mov     [rcx+20h], r12
0x1801717bb  xorps   xmm0, xmm0
0x1801717be  movups  [rbp+var_30], xmm0
0x1801717c2  mov     [rbp+var_20], r12
0x1801717c6  xor     r9d, r9d
0x1801717c9  lea     r8, [rbp+var_30]
0x1801717cd  mov     rdx, r10
0x1801717d0  xor     ecx, ecx
0x1801717d2  mov     rax, [r10+28h]
0x1801717d6  call    cs:__guard_dispatch_icall_fptr
0x1801717dc  mov     r10, [rbp+lpOverlapped]
0x1801717e0  mov     rax, r10
0x1801717e3  mov     rcx, r10
0x1801717e6  test    r10, r10
0x1801717e9  jnz     short loc_1801717A5
0x1801717eb  cmp     [r13+1A0h], r12b
0x1801717f2  jz      loc_18017167D
0x1801717f8  test    dil, dil
0x1801717fb  jz      short loc_180171806
0x1801717fd  mov     rcx, r14; lpCriticalSection
0x180171800  call    cs:__imp_LeaveCriticalSection
0x180171806  mov     rcx, [rbp+var_8]
0x18017180a  xor     rcx, rsp; StackCookie
0x18017180d  call    __security_check_cookie
0x180171812  lea     r11, [rsp+70h+var_s0]
0x180171817  mov     rbx, [r11+38h]
0x18017181b  mov     rsi, [r11+40h]
0x18017181f  mov     rdi, [r11+48h]
0x180171823  mov     rsp, r11
0x180171826  pop     r15
0x180171828  pop     r14
0x18017182a  pop     r13
0x18017182c  pop     r12
0x18017182e  pop     rbp
0x18017182f  retn
```
