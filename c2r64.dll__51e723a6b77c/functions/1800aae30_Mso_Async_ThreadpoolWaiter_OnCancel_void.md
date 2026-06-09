# Mso::Async::ThreadpoolWaiter::OnCancel(void)

- ea: `0x1800aae30`
- end: `0x1800aaedb`
- name: `?OnCancel@ThreadpoolWaiter@Async@Mso@@UEAAXXZ`
- size: `171`
- prototype: `void __fastcall(Mso::Async::ThreadpoolWaiter *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012bf8`
- `0x1800a3c34`
- `0x1800aae30`
- `0x1800aaf98`
- `0x180146090`

## import_xrefs

- `KERNEL32!CloseThreadpoolWait` at `0x1800aaec7`
- `KERNEL32!CloseThreadpoolWait` at `0x1800aaec7`
- `KERNEL32!SetThreadpoolWait` at `0x1800aaeb1`
- `KERNEL32!SetThreadpoolWait` at `0x1800aaeb1`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x1800aaebd`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x1800aaebd`

## pseudocode

```c
void __fastcall Mso::Async::ThreadpoolWaiter::OnCancel(Mso::Async::ThreadpoolWaiter *this)
{
  Mso::Async::ThreadPool *v2; // rax
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 4, 2, 0) )
  {
    v2 = (Mso::Async::ThreadPool *)Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->((char *)this + 24);
    Mso::Async::ThreadPool::RemoveTask(v2, this);
    v6 = *((_QWORD *)this + 4);
    v3 = Mso::Details::QueryCastConverter<Mso::Async::ICancellationListener *>::QueryCast<Mso::IFunctor<void,> *>(&v6);
    v4 = v3;
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3);
    v5 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = 0;
    if ( v5 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 16LL))(v5, v4);
    SetThreadpoolWait(*((PTP_WAIT *)this + 5), 0, 0);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 5), 0);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 5));
    *((_QWORD *)this + 5) = 0;
  }
}

```

## disassembly

```asm
0x1800aae30  push    rbx
0x1800aae32  sub     rsp, 20h
0x1800aae36  mov     rbx, rcx
0x1800aae39  mov     ecx, 2
0x1800aae3e  xor     eax, eax
0x1800aae40  lock cmpxchg [rbx+10h], ecx
0x1800aae45  jnz     loc_1800AAED5
0x1800aae4b  lea     rcx, [rbx+18h]
0x1800aae4f  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x1800aae54  mov     rdx, rbx; struct Mso::Async::ICancellationListener *
0x1800aae57  mov     rcx, rax; this
0x1800aae5a  call    ?RemoveTask@ThreadPool@Async@Mso@@AEAAXPEAUICancellationListener@23@@Z; Mso::Async::ThreadPool::RemoveTask(Mso::Async::ICancellationListener *)
0x1800aae5f  mov     rax, [rbx+20h]
0x1800aae63  mov     [rsp+28h+arg_0], rax
0x1800aae68  lea     rcx, [rsp+28h+arg_0]
0x1800aae6d  call    ??$QueryCast@PEAU?$IFunctor@X$$V@Mso@@@?$QueryCastConverter@PEAUICancellationListener@Async@Mso@@@Details@Mso@@SAPEAUICancellationListener@Async@2@AEBQEAU?$IFunctor@X$$V@2@@Z; Mso::Details::QueryCastConverter<Mso::Async::ICancellationListener *>::QueryCast<Mso::IFunctor<void,> *>(Mso::IFunctor<void,> * const &)
0x1800aae72  mov     rdx, rax
0x1800aae75  test    rax, rax
0x1800aae78  jz      short loc_1800AAE8A
0x1800aae7a  mov     rcx, [rax]
0x1800aae7d  mov     rax, [rcx+18h]
0x1800aae81  mov     rcx, rdx
0x1800aae84  call    cs:__guard_dispatch_icall_fptr
0x1800aae8a  mov     rcx, [rbx+20h]
0x1800aae8e  mov     qword ptr [rbx+20h], 0
0x1800aae96  test    rcx, rcx
0x1800aae99  jz      short loc_1800AAEA8
0x1800aae9b  mov     rax, [rcx]
0x1800aae9e  mov     rax, [rax+10h]
0x1800aaea2  call    cs:__guard_dispatch_icall_fptr
0x1800aaea8  xor     r8d, r8d; pftTimeout
0x1800aaeab  xor     edx, edx; h
0x1800aaead  mov     rcx, [rbx+28h]; pwa
0x1800aaeb1  call    cs:__imp_SetThreadpoolWait
0x1800aaeb7  xor     edx, edx; fCancelPendingCallbacks
0x1800aaeb9  mov     rcx, [rbx+28h]; pwa
0x1800aaebd  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800aaec3  mov     rcx, [rbx+28h]; pwa
0x1800aaec7  call    cs:__imp_CloseThreadpoolWait
0x1800aaecd  mov     qword ptr [rbx+28h], 0
0x1800aaed5  add     rsp, 20h
0x1800aaed9  pop     rbx
0x1800aaeda  retn
```
