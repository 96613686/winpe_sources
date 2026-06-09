# AsyncClientCallRetryContext::CancelRetry(IAsyncClientTransport *,ulong)

- ea: `0x180064800`
- end: `0x1800649a5`
- name: `?CancelRetry@AsyncClientCallRetryContext@@QEAAJPEAUIAsyncClientTransport@@K@Z`
- size: `421`
- prototype: `HRESULT __fastcall(AsyncClientCallRetryContext *this, IAsyncClientTransport *pAsyncClientTransport, unsigned int ulSeconds)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180064770`
- `0x18015f6fc`

## callees

- `0x180022e18`
- `0x180064800`
- `0x1800649b0`
- `0x180084480`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180064848`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180064884`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180064848`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180064884`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180064828`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006486f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180064828`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006486f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006493f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006493f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800648bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180064981`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800648bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180064981`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800648ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800648ac`

## pseudocode

```c
__int64 __fastcall AsyncClientCallRetryContext::CancelRetry(
        AsyncClientCallRetryContext *this,
        IAsyncClientTransport *pAsyncClientTransport,
        unsigned int ulSeconds)
{
  Microsoft::WRL::Wrappers::SRWLock *p_lockRetryContext; // rsi
  unsigned int v7; // ebx
  AsyncClientCallRetryContext::CancellationState cancellationState; // r14d
  unsigned int v9; // r15d
  unsigned int v11; // eax
  unsigned int dwTimeout; // ecx
  _TP_TIMER *pTimer; // rcx
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive lock; // [rsp+50h] [rbp+8h] BYREF
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive result; // [rsp+68h] [rbp+20h] BYREF

  p_lockRetryContext = &this->_lockRetryContext;
  v7 = 0;
  AcquireSRWLockExclusive(&this->_lockRetryContext.SRWLock_);
  cancellationState = this->_cancellationState;
  this->_isCancellationRequested = 1;
  if ( cancellationState == TimerInProgress )
  {
    v11 = GetTickCount64() - LODWORD(this->_retryDelayTimer._initialCount);
    dwTimeout = this->_retryDelayTimer._dwTimeout;
    if ( dwTimeout >= v11 )
      v7 = (dwTimeout - v11) / 0x3E8;
    if ( ulSeconds > v7 )
      this->_allowFinalRetryAttempt = 1;
  }
  if ( p_lockRetryContext )
    ReleaseSRWLockExclusive(&p_lockRetryContext->SRWLock_);
  if ( cancellationState == CallInProgress )
    goto LABEL_5;
  v9 = 0;
  if ( cancellationState == TimerInProgress )
  {
    pTimer = this->_pTimer;
    if ( ulSeconds > v7 )
    {
      WaitForThreadpoolTimerCallbacks(pTimer, 0);
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&lock, &p_lockRetryContext->SRWLock_);
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(&lock);
      ulSeconds -= v7;
LABEL_5:
      v9 = pAsyncClientTransport->CancelTransportCall(pAsyncClientTransport, ulSeconds);
      goto LABEL_6;
    }
    SetThreadpoolTimer(pTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(this->_pTimer, 1);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&result, &p_lockRetryContext->SRWLock_);
    this->_spAsyncClientTransport.ptr_->OnRetryCanceled(this->_spAsyncClientTransport.ptr_);
    lock.sync_ = 0;
    Microsoft::WRL::ComPtr<OutParameterMarshalingClient>::operator=(
      (ObjectLibrary::ReferencedPtr<WinrtAsyncChannelMessage> *)&this->_spAsyncClientTransport,
      (ObjectLibrary::ReferencedPtr<WinrtAsyncChannelMessage> *)&lock);
    if ( lock.sync_ )
      (*((void (__fastcall **)(_RTL_SRWLOCK *))lock.sync_->Ptr + 2))(lock.sync_);
    lock.sync_ = 0;
    Microsoft::WRL::ComPtr<OutParameterMarshalingClient>::operator=(
      (ObjectLibrary::ReferencedPtr<WinrtAsyncChannelMessage> *)&this->_spKeepRetryContextAlive,
      (ObjectLibrary::ReferencedPtr<WinrtAsyncChannelMessage> *)&lock);
    if ( lock.sync_ )
      (*((void (__fastcall **)(_RTL_SRWLOCK *))lock.sync_->Ptr + 2))(lock.sync_);
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(&result);
  }
LABEL_6:
  AcquireSRWLockExclusive(&p_lockRetryContext->SRWLock_);
  this->_cancellationState = NothingToCancel;
  if ( p_lockRetryContext )
    ReleaseSRWLockExclusive(&p_lockRetryContext->SRWLock_);
  return v9;
}

```

## disassembly

```asm
0x180064800  mov     [rsp+arg_8], rbx
0x180064805  mov     [rsp+arg_10], rbp
0x18006480a  push    rsi
0x18006480b  push    rdi
0x18006480c  push    r12
0x18006480e  push    r14
0x180064810  push    r15
0x180064812  sub     rsp, 20h
0x180064816  lea     rsi, [this+10h]
0x18006481a  mov     rdi, this
0x18006481d  mov     this, rsi; SRWLock
0x180064820  mov     ebp, ulSeconds
0x180064823  mov     r12, pAsyncClientTransport
0x180064826  xor     ebx, ebx
0x180064828  call    cs:__imp_AcquireSRWLockExclusive
0x18006482e  mov     r14d, [rdi+30h]
0x180064832  mov     byte ptr [rdi+34h], 1
0x180064836  cmp     r14d, 1
0x18006483a  jz      loc_18006493F
0x180064840  test    rsi, rsi
0x180064843  jz      short loc_18006484E
0x180064845  mov     this, rsi; SRWLock
0x180064848  call    cs:__imp_ReleaseSRWLockExclusive
0x18006484e  test    r14d, r14d
0x180064851  jnz     loc_180064966
0x180064857  mov     rax, [r12]
0x18006485b  mov     edx, ebp
0x18006485d  mov     this, r12
0x180064860  mov     rax, [rax+30h]
0x180064864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064869  mov     r15d, eax
0x18006486c  mov     this, rsi; SRWLock
0x18006486f  call    cs:__imp_AcquireSRWLockExclusive
0x180064875  mov     dword ptr [rdi+30h], 2
0x18006487c  test    rsi, rsi
0x18006487f  jz      short loc_18006488A
0x180064881  mov     this, rsi; SRWLock
0x180064884  call    cs:__imp_ReleaseSRWLockExclusive
0x18006488a  mov     rbx, [rsp+48h+arg_8]
0x18006488f  mov     eax, r15d
0x180064892  mov     rbp, [rsp+48h+arg_10]
0x180064897  add     rsp, 20h
0x18006489b  pop     r15
0x18006489d  pop     r14
0x18006489f  pop     r12
0x1800648a1  pop     rdi
0x1800648a2  pop     rsi
0x1800648a3  retn
0x1800648a4  xor     r9d, r9d; msWindowLength
0x1800648a7  xor     ulSeconds, ulSeconds; msPeriod
0x1800648aa  xor     edx, edx; pftDueTime
0x1800648ac  call    cs:__imp_SetThreadpoolTimer
0x1800648b2  mov     this, [rdi+18h]; pti
0x1800648b6  mov     edx, 1; fCancelPendingCallbacks
0x1800648bb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800648c1  mov     pAsyncClientTransport, rsi; lock
0x1800648c4  lea     this, [rsp+48h+result]; result
0x1800648c9  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800648ce  mov     this, [rdi+20h]
0x1800648d2  mov     rax, [this]
0x1800648d5  mov     rax, [rax+38h]
0x1800648d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800648de  lea     pAsyncClientTransport, [rsp+48h+lock]; other
0x1800648e3  mov     [rsp+48h+lock.sync_], r15
0x1800648e8  lea     this, [rdi+20h]; this
0x1800648ec  call    ??4?$ComPtr@VOutParameterMarshalingClient@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<OutParameterMarshalingClient>::operator=(Microsoft::WRL::ComPtr<OutParameterMarshalingClient> &&)
0x1800648f1  mov     this, [rsp+48h+lock.sync_]
0x1800648f6  test    this, this
0x1800648f9  jz      short loc_180064907
0x1800648fb  mov     rax, [this]
0x1800648fe  mov     rax, [rax+10h]
0x180064902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064907  lea     this, [rdi+28h]; this
0x18006490b  mov     [rsp+48h+lock.sync_], r15
0x180064910  lea     pAsyncClientTransport, [rsp+48h+lock]; other
0x180064915  call    ??4?$ComPtr@VOutParameterMarshalingClient@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<OutParameterMarshalingClient>::operator=(Microsoft::WRL::ComPtr<OutParameterMarshalingClient> &&)
0x18006491a  mov     this, [rsp+48h+lock.sync_]
0x18006491f  test    this, this
0x180064922  jz      short loc_180064930
0x180064924  mov     rax, [this]
0x180064927  mov     rax, [rax+10h]
0x18006492b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064930  lea     this, [rsp+48h+result]; this
0x180064935  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18006493a  jmp     loc_18006486C
0x18006493f  call    cs:__imp_GetTickCount64
0x180064945  sub     eax, [rdi+40h]
0x180064948  mov     ecx, [rdi+38h]
0x18006494b  cmp     ecx, eax
0x18006494d  jb      loc_180247C30
0x180064953  sub     ecx, eax
0x180064955  mov     eax, 10624DD3h
0x18006495a  mul     ecx
0x18006495c  mov     ebx, edx
0x18006495e  shr     ebx, 6
0x180064961  jmp     loc_180247C30
0x180064966  xor     r15d, r15d
0x180064969  cmp     r14d, 1
0x18006496d  jnz     loc_18006486C
0x180064973  mov     this, [rdi+18h]; pti
0x180064977  cmp     ebp, ebx
0x180064979  jbe     loc_1800648A4
0x18006497f  xor     edx, edx; fCancelPendingCallbacks
0x180064981  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180064987  mov     pAsyncClientTransport, rsi; lock
0x18006498a  lea     this, [rsp+48h+lock]; result
0x18006498f  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180064994  lea     this, [rsp+48h+lock]; this
0x180064999  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18006499e  sub     ebp, ebx
0x1800649a0  jmp     loc_180064857
0x180247c30  cmp     ebp, ebx
0x180247c32  jbe     loc_180064840
0x180247c38  mov     byte ptr [rdi+35h], 1
0x180247c3c  jmp     loc_180064840
```
