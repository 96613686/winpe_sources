# winrt::impl::signal_awaiter::create_threadpool_wait(void)

- ea: `0x18001a6ec`
- end: `0x18001a796`
- name: `?create_threadpool_wait@signal_awaiter@impl@winrt@@AEAAXXZ`
- size: `170`
- prototype: `void __fastcall(winrt::impl::signal_awaiter *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016160`

## callees

- `0x1800024f8`
- `0x180002510`
- `0x180015e80`
- `0x18001a6c0`
- `0x18001a6ec`
- `0x18001aa44`

## pseudocode

```c
void __fastcall winrt::impl::signal_awaiter::create_threadpool_wait(winrt::impl::signal_awaiter *this)
{
  const struct winrt::impl::slim_source_location *v2; // rdx
  struct _TP_WAIT *ThreadpoolWait; // rsi
  void *v4; // rdx
  int v5; // [rsp+20h] [rbp-28h] BYREF
  __int128 v6; // [rsp+28h] [rbp-20h]
  __int64 v7; // [rsp+58h] [rbp+10h] BYREF

  v5 = 0;
  v6 = 0;
  ThreadpoolWait = WINRT_IMPL_CreateThreadpoolWait(winrt::impl::signal_awaiter::callback, this, 0);
  if ( !ThreadpoolWait )
    winrt::throw_last_error((winrt *)&v5, v2);
  winrt::handle_type<winrt::impl::signal_awaiter::wait_traits>::close((char *)this + 8);
  winrt::handle_type<winrt::impl::signal_awaiter::wait_traits>::close((char *)this + 8);
  *((_QWORD *)this + 1) = ThreadpoolWait;
  v4 = (void *)*((_QWORD *)this + 3);
  v7 = -*((_QWORD *)this + 2);
  SetThreadpoolWait_0(ThreadpoolWait, v4, (PFILETIME)((unsigned __int64)&v7 & -(__int64)(v7 != 0)));
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 12, 1, 0) )
    winrt::impl::signal_awaiter::fire_immediately(this);
}

```

## disassembly

```asm
0x18001a6ec  mov     rax, rsp
0x18001a6ef  mov     [rax+18h], rbx
0x18001a6f3  mov     [rax+20h], rsi
0x18001a6f7  push    rdi
0x18001a6f8  sub     rsp, 40h
0x18001a6fc  mov     rdi, rcx
0x18001a6ff  mov     dword ptr [rax-28h], 0
0x18001a706  xorps   xmm0, xmm0
0x18001a709  mov     rdx, rcx; pv
0x18001a70c  lea     rcx, ?callback@signal_awaiter@impl@winrt@@CAXPEAX00I@Z; pfnwa
0x18001a713  xor     r8d, r8d; pcbe
0x18001a716  movdqu  xmmword ptr [rax-20h], xmm0
0x18001a71b  call    WINRT_IMPL_CreateThreadpoolWait
0x18001a720  mov     rsi, rax
0x18001a723  test    rax, rax
0x18001a726  jz      short loc_18001A78B
0x18001a728  lea     rbx, [rdi+8]
0x18001a72c  mov     rcx, rbx
0x18001a72f  call    ?close@?$handle_type@Uwait_traits@signal_awaiter@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::signal_awaiter::wait_traits>::close(void)
0x18001a734  mov     rcx, rbx
0x18001a737  call    ?close@?$handle_type@Uwait_traits@signal_awaiter@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::signal_awaiter::wait_traits>::close(void)
0x18001a73c  mov     [rbx], rsi
0x18001a73f  mov     rcx, rsi; pwa
0x18001a742  mov     rax, [rdi+10h]
0x18001a746  mov     rdx, [rdi+18h]; h
0x18001a74a  neg     rax
0x18001a74d  mov     [rsp+48h+arg_8], rax
0x18001a752  neg     rax
0x18001a755  lea     rax, [rsp+48h+arg_8]
0x18001a75a  sbb     r8, r8
0x18001a75d  and     r8, rax; pftTimeout
0x18001a760  call    SetThreadpoolWait_0
0x18001a765  mov     ecx, 1
0x18001a76a  xor     eax, eax
0x18001a76c  lock cmpxchg [rdi+30h], ecx
0x18001a771  jz      short loc_18001A77B
0x18001a773  mov     rcx, rdi; this
0x18001a776  call    ?fire_immediately@signal_awaiter@impl@winrt@@AEAAXXZ; winrt::impl::signal_awaiter::fire_immediately(void)
0x18001a77b  mov     rbx, [rsp+48h+arg_10]
0x18001a780  mov     rsi, [rsp+48h+arg_18]
0x18001a785  add     rsp, 40h
0x18001a789  pop     rdi
0x18001a78a  retn
0x18001a78b  lea     rcx, [rsp+48h+var_28]; this
0x18001a790  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
