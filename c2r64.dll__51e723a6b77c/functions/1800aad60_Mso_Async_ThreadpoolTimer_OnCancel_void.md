# Mso::Async::ThreadpoolTimer::OnCancel(void)

- ea: `0x1800aad60`
- end: `0x1800aae27`
- name: `?OnCancel@ThreadpoolTimer@Async@Mso@@UEAAXXZ`
- size: `199`
- prototype: `void __fastcall(Mso::Async::ThreadpoolTimer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180012bf8`
- `0x180031e80`
- `0x1800a3c34`
- `0x1800aad60`
- `0x1800aaf98`
- `0x180146090`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x1800aae0e`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800aae0e`
- `KERNEL32!SetThreadpoolTimer` at `0x1800aadf5`
- `KERNEL32!SetThreadpoolTimer` at `0x1800aadf5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800aae04`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800aae04`

## pseudocode

```c
void __fastcall Mso::Async::ThreadpoolTimer::OnCancel(Mso::Async::ThreadpoolTimer *this)
{
  Mso::Async::ThreadPool *v2; // rax
  __int64 v3; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 4, 2, 0) )
  {
    v2 = (Mso::Async::ThreadPool *)Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->((char *)this + 24);
    Mso::Async::ThreadPool::RemoveTask(v2, this);
    v4 = *((_QWORD *)this + 4);
    v3 = Mso::Details::QueryCastConverter<Mso::Async::ICancellationListener *>::QueryCast<Mso::IFunctor<void,> *>(&v4);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3);
    v4 = 0;
    Mso::TCntPtr<Mso::Async::IDispatchQueue>::operator=((char *)this + 32, &v4);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 5), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 5), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 5));
    *((_QWORD *)this + 5) = 0;
  }
}

```

## disassembly

```asm
0x1800aad60  mov     [rsp+arg_8], rbx
0x1800aad65  push    rdi
0x1800aad66  sub     rsp, 20h
0x1800aad6a  mov     rbx, rcx
0x1800aad6d  mov     ecx, 2
0x1800aad72  xor     eax, eax
0x1800aad74  lock cmpxchg [rbx+10h], ecx
0x1800aad79  jnz     loc_1800AAE1C
0x1800aad7f  lea     rcx, [rbx+18h]
0x1800aad83  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x1800aad88  mov     rdx, rbx; struct Mso::Async::ICancellationListener *
0x1800aad8b  mov     rcx, rax; this
0x1800aad8e  call    ?RemoveTask@ThreadPool@Async@Mso@@AEAAXPEAUICancellationListener@23@@Z; Mso::Async::ThreadPool::RemoveTask(Mso::Async::ICancellationListener *)
0x1800aad93  mov     rax, [rbx+20h]
0x1800aad97  mov     [rsp+28h+arg_0], rax
0x1800aad9c  lea     rcx, [rsp+28h+arg_0]
0x1800aada1  call    ??$QueryCast@PEAU?$IFunctor@X$$V@Mso@@@?$QueryCastConverter@PEAUICancellationListener@Async@Mso@@@Details@Mso@@SAPEAUICancellationListener@Async@2@AEBQEAU?$IFunctor@X$$V@2@@Z; Mso::Details::QueryCastConverter<Mso::Async::ICancellationListener *>::QueryCast<Mso::IFunctor<void,> *>(Mso::IFunctor<void,> * const &)
0x1800aada6  test    rax, rax
0x1800aada9  jz      short loc_1800AADBB
0x1800aadab  mov     rdx, [rax]
0x1800aadae  mov     rcx, rax
0x1800aadb1  mov     rax, [rdx+18h]
0x1800aadb5  call    cs:__guard_dispatch_icall_fptr
0x1800aadbb  mov     [rsp+28h+arg_0], 0
0x1800aadc4  lea     rdx, [rsp+28h+arg_0]
0x1800aadc9  lea     rcx, [rbx+20h]
0x1800aadcd  call    ??4?$TCntPtr@VIDispatchQueue@Async@Mso@@@Mso@@QEAAAEAV01@$$QEAV01@@Z; Mso::TCntPtr<Mso::Async::IDispatchQueue>::operator=(Mso::TCntPtr<Mso::Async::IDispatchQueue> &&)
0x1800aadd2  mov     rcx, [rsp+28h+arg_0]
0x1800aadd7  test    rcx, rcx
0x1800aadda  jz      short loc_1800AADE9
0x1800aaddc  mov     rax, [rcx]
0x1800aaddf  mov     rax, [rax+10h]
0x1800aade3  call    cs:__guard_dispatch_icall_fptr
0x1800aade9  xor     r9d, r9d; msWindowLength
0x1800aadec  xor     r8d, r8d; msPeriod
0x1800aadef  xor     edx, edx; pftDueTime
0x1800aadf1  mov     rcx, [rbx+28h]; pti
0x1800aadf5  call    cs:__imp_SetThreadpoolTimer
0x1800aadfb  mov     edx, 1; fCancelPendingCallbacks
0x1800aae00  mov     rcx, [rbx+28h]; pti
0x1800aae04  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800aae0a  mov     rcx, [rbx+28h]; pti
0x1800aae0e  call    cs:__imp_CloseThreadpoolTimer
0x1800aae14  mov     qword ptr [rbx+28h], 0
0x1800aae1c  mov     rbx, [rsp+28h+arg_8]
0x1800aae21  add     rsp, 20h
0x1800aae25  pop     rdi
0x1800aae26  retn
```
