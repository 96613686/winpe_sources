# wil::details::threadpool_timer_context::RequestRelease(wil::details::threadpool_timer_context *)

- ea: `0x180021454`
- end: `0x180021516`
- name: `?RequestRelease@threadpool_timer_context@details@wil@@SAXPEAU123@@Z`
- size: `194`
- prototype: `void __fastcall(struct wil::details::threadpool_timer_context *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180020350`
- `0x180020938`

## callees

- `0x180001b94`
- `0x18001fdb4`
- `0x180021454`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021491`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021491`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021470`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021470`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800214c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800214c0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800214ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800214ab`

## pseudocode

```c
void __fastcall wil::details::threadpool_timer_context::RequestRelease(
        struct wil::details::threadpool_timer_context *this)
{
  RTL_SRWLOCK *v1; // rdi
  char v3; // si
  __int64 v4; // rdx
  struct _TP_TIMER *v5; // rcx
  __int64 v6; // rcx

  v1 = (RTL_SRWLOCK *)((char *)this + 88);
  v3 = 1;
  AcquireSRWLockExclusive((PSRWLOCK)this + 11);
  if ( *((_DWORD *)this + 24) )
  {
    *((_BYTE *)this + 100) = 1;
    v3 = 0;
  }
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  if ( v3 )
  {
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 10), 1);
    v5 = (struct _TP_TIMER *)*((_QWORD *)this + 10);
    if ( v5 )
      CloseThreadpoolTimer(v5);
    v6 = *((_QWORD *)this + 9);
    if ( v6 )
    {
      LOBYTE(v4) = v6 != (_QWORD)this + 16;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 32LL))(v6, v4);
      *((_QWORD *)this + 9) = 0;
    }
    wil::details::threadpool_object_context::~threadpool_object_context(this);
    operator delete(this, (const struct std::nothrow_t *)0x68);
  }
}

```

## disassembly

```asm
0x180021454  mov     [rsp+arg_0], rbx
0x180021459  mov     [rsp+arg_8], rsi
0x18002145e  push    rdi
0x18002145f  sub     rsp, 20h
0x180021463  lea     rdi, [rcx+58h]
0x180021467  mov     rbx, rcx
0x18002146a  mov     rcx, rdi; SRWLock
0x18002146d  mov     sil, 1
0x180021470  call    cs:__imp_AcquireSRWLockExclusive
0x180021477  nop     dword ptr [rax+rax+00h]
0x18002147c  cmp     dword ptr [rbx+60h], 0
0x180021480  jz      short loc_180021489
0x180021482  mov     [rbx+64h], sil
0x180021486  xor     sil, sil
0x180021489  test    rdi, rdi
0x18002148c  jz      short loc_18002149D
0x18002148e  mov     rcx, rdi; SRWLock
0x180021491  call    cs:__imp_ReleaseSRWLockExclusive
0x180021498  nop     dword ptr [rax+rax+00h]
0x18002149d  test    sil, sil
0x1800214a0  jz      short loc_180021505
0x1800214a2  mov     rcx, [rbx+50h]; pti
0x1800214a6  mov     edx, 1; fCancelPendingCallbacks
0x1800214ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800214b2  nop     dword ptr [rax+rax+00h]
0x1800214b7  mov     rcx, [rbx+50h]; pti
0x1800214bb  test    rcx, rcx
0x1800214be  jz      short loc_1800214CC
0x1800214c0  call    cs:__imp_CloseThreadpoolTimer
0x1800214c7  nop     dword ptr [rax+rax+00h]
0x1800214cc  lea     rdi, [rbx+10h]
0x1800214d0  mov     rcx, [rdi+38h]
0x1800214d4  test    rcx, rcx
0x1800214d7  jz      short loc_1800214F0
0x1800214d9  mov     rax, [rcx]
0x1800214dc  cmp     rcx, rdi
0x1800214df  setnz   dl
0x1800214e2  mov     rax, [rax+20h]
0x1800214e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214eb  and     qword ptr [rdi+38h], 0
0x1800214f0  mov     rcx, rbx; this
0x1800214f3  call    ??1threadpool_object_context@details@wil@@QEAA@XZ; wil::details::threadpool_object_context::~threadpool_object_context(void)
0x1800214f8  mov     edx, 68h ; 'h'; struct std::nothrow_t *
0x1800214fd  mov     rcx, rbx; void *
0x180021500  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180021505  mov     rbx, [rsp+28h+arg_0]
0x18002150a  mov     rsi, [rsp+28h+arg_8]
0x18002150f  add     rsp, 20h
0x180021513  pop     rdi
0x180021514  retn
```
