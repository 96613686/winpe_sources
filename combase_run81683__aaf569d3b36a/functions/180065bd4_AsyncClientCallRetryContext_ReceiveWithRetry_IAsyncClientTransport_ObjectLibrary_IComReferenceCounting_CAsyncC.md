# AsyncClientCallRetryContext::ReceiveWithRetry(IAsyncClientTransport *,ObjectLibrary::IComReferenceCounting *,CAsyncCall *,_GUID const &,CStdIdentity *)

- ea: `0x180065bd4`
- end: `0x180065dcc`
- name: `?ReceiveWithRetry@AsyncClientCallRetryContext@@QEAAJPEAUIAsyncClientTransport@@PEAUIComReferenceCounting@ObjectLibrary@@PEAVCAsyncCall@@AEBU_GUID@@PEAVCStdIdentity@@@Z`
- size: `504`
- prototype: `HRESULT __fastcall(AsyncClientCallRetryContext *this, IAsyncClientTransport *pAsyncClientTransport, ObjectLibrary::IComReferenceCounting *pKeepRetryContextAlive, CAsyncCall *pAsyncCall, const _GUID *moid, CStdIdentity *pStdId)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180065970`
- `0x180124d20`

## callees

- `0x1800188a0`
- `0x180022e18`
- `0x18003a8bc`
- `0x180065bd4`
- `0x180084480`
- `0x18018bb5c`
- `0x1801b68bc`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180065c58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180065ca9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180065c58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180065ca9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180065c36`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180065c36`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180065d8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180065d8c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180065db5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180065db5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180065cf0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180065cf0`

## string_xrefs

- `0x180065c83`: `onecore\com\combase\dcomrem\callctrl.cxx`

## pseudocode

```c
__int64 __fastcall AsyncClientCallRetryContext::ReceiveWithRetry(
        AsyncClientCallRetryContext *this,
        IAsyncClientTransport *pAsyncClientTransport,
        WinrtAsyncChannelMessage *pKeepRetryContextAlive,
        CAsyncCall *pAsyncCall,
        const _GUID *moid,
        CStdIdentity *pStdId)
{
  IAsyncClientTransport_vtbl *v10; // rax
  signed int v11; // r15d
  HRESULT v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // ebx
  _TP_TIMER *ThreadpoolTimer; // rax
  signed int LastError; // eax
  IAsyncClientTransport_vtbl *v18; // rax
  _TP_TIMER *pTimer; // rcx
  unsigned int AutoRetry; // eax
  __int64 v21; // rdi
  HRESULT v22; // eax
  unsigned int retryStatus; // [rsp+30h] [rbp-20h] BYREF
  ObjectLibrary::ReferencedPtr<WinrtAsyncChannelMessage> other; // [rsp+38h] [rbp-18h] BYREF
  _FILETIME relativeDueTime; // [rsp+40h] [rbp-10h] BYREF
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive lock; // [rsp+48h] [rbp-8h] BYREF
  void *retaddr; // [rsp+88h] [rbp+38h]

  relativeDueTime = (_FILETIME)NtCurrentTeb()->ReservedForOle;
  if ( *(_QWORD *)&relativeDueTime || (v13 = COleTls::TLSAllocData((COleTls *)&relativeDueTime), v14 = v13, v13 >= 0) )
  {
    v10 = pAsyncClientTransport->__vftable;
    retryStatus = 0;
    v11 = v10->TransportReceive(pAsyncClientTransport, &retryStatus);
    if ( v11 >= 0 )
      v11 = retryStatus;
    AcquireSRWLockExclusive(&this->_lockRetryContext.SRWLock_);
    lock.sync_ = &this->_lockRetryContext.SRWLock_;
    this->_cancellationState = NothingToCancel;
    if ( v11 == -2147352577 )
    {
      if ( this->_isCancellationRequested )
      {
        if ( this != (AsyncClientCallRetryContext *)-16LL )
          ReleaseSRWLockExclusive(&this->_lockRetryContext.SRWLock_);
        return 2147549186LL;
      }
      else
      {
        if ( pAsyncCall->_destObj._dwDestCtx == 5 || pAsyncCall->_destObj._dwDestCtx == 2 )
        {
          v15 = -2147417846;
        }
        else if ( this->_pTimer
               || (ThreadpoolTimer = CreateThreadpoolTimer(
                                       AsyncClientCallRetryContext::RetrySendOnTimerExpiration,
                                       this,
                                       0),
                   (this->_pTimer = ThreadpoolTimer) != 0) )
        {
          AutoRetry = ClientCallRetryContext::NextAutoRetry(this);
          v21 = AutoRetry;
          if ( AutoRetry == -1 )
          {
            v15 = -2147352578;
          }
          else
          {
            v22 = AsyncClientCallRetryContext::CopyRequestMessageFromAutoRetryResponse(
                    this,
                    pAsyncClientTransport,
                    pAsyncCall,
                    moid,
                    pStdId);
            if ( v22 == -2147417846 )
            {
              v18 = pAsyncClientTransport->__vftable;
              other.ptr_ = (WinrtAsyncChannelMessage *)pAsyncClientTransport;
              v18->AddRef(pAsyncClientTransport);
              Microsoft::WRL::ComPtr<OutParameterMarshalingClient>::operator=(
                (ObjectLibrary::ReferencedPtr<WinrtAsyncChannelMessage> *)&this->_spAsyncClientTransport,
                &other);
              if ( other.ptr_ )
                other.ptr_->Release(other.ptr_);
              other.ptr_ = pKeepRetryContextAlive;
              if ( pKeepRetryContextAlive )
                pKeepRetryContextAlive->AddRef(pKeepRetryContextAlive);
              Microsoft::WRL::ComPtr<OutParameterMarshalingClient>::operator=(
                (ObjectLibrary::ReferencedPtr<WinrtAsyncChannelMessage> *)&this->_spKeepRetryContextAlive,
                &other);
              if ( other.ptr_ )
                other.ptr_->Release(other.ptr_);
              this->_retryDelayTimer._dwTimeout = v21;
              this->_retryDelayTimer._initialCount = GetTickCount64();
              pTimer = this->_pTimer;
              relativeDueTime = (_FILETIME)(-10000 * v21);
              SetThreadpoolTimer(pTimer, &relativeDueTime, 0, 0);
              this->_cancellationState = TimerInProgress;
              v15 = -2147352577;
            }
            else
            {
              v15 = v22;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v15 = LastError;
          if ( LastError > 0 )
            v15 = (unsigned __int16)LastError | 0x80070000;
        }
        Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(&lock);
        return v15;
      }
    }
    else
    {
      if ( this != (AsyncClientCallRetryContext *)-16LL )
        ReleaseSRWLockExclusive(&this->_lockRetryContext.SRWLock_);
      return (unsigned int)v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x458u, "onecore\\com\\combase\\dcomrem\\callctrl.cxx", v13);
    return v14;
  }
}

```

## disassembly

```asm
0x180065bd4  push    rbp
0x180065bd6  push    rbx
0x180065bd7  push    rsi
0x180065bd8  push    rdi
0x180065bd9  push    r12
0x180065bdb  push    r14
0x180065bdd  push    r15
0x180065bdf  mov     rbp, rsp
0x180065be2  sub     rsp, 50h
0x180065be6  mov     rax, gs:30h
0x180065bef  mov     r12, pAsyncCall
0x180065bf2  mov     rsi, pKeepRetryContextAlive
0x180065bf5  mov     r14, pAsyncClientTransport
0x180065bf8  mov     rbx, this
0x180065bfb  mov     r10, [rax+1758h]
0x180065c02  mov     qword ptr [rbp+relativeDueTime.dwLowDateTime], r10
0x180065c06  test    r10, r10
0x180065c09  jz      short loc_180065C70
0x180065c0b  mov     rax, [r14]
0x180065c0e  lea     pAsyncClientTransport, [rbp+retryStatus]
0x180065c12  mov     this, r14
0x180065c15  mov     [rbp+retryStatus], 0
0x180065c1c  mov     rax, [rax+28h]
0x180065c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c25  test    eax, eax
0x180065c27  lea     rdi, [rbx+10h]
0x180065c2b  mov     r15d, eax
0x180065c2e  mov     this, rdi; SRWLock
0x180065c31  cmovns  r15d, [rbp+retryStatus]
0x180065c36  call    cs:__imp_AcquireSRWLockExclusive
0x180065c3c  mov     [rbp+lock.sync_], rdi
0x180065c40  mov     dword ptr [rbx+30h], 2
0x180065c47  cmp     r15d, 8001FFFFh
0x180065c4e  jz      short loc_180065C9B
0x180065c50  test    rdi, rdi
0x180065c53  jz      short loc_180065C5E
0x180065c55  mov     this, rdi; SRWLock
0x180065c58  call    cs:__imp_ReleaseSRWLockExclusive
0x180065c5e  mov     eax, r15d
0x180065c61  add     rsp, 50h
0x180065c65  pop     r15
0x180065c67  pop     r14
0x180065c69  pop     r12
0x180065c6b  pop     rdi
0x180065c6c  pop     rsi
0x180065c6d  pop     rbx
0x180065c6e  pop     rbp
0x180065c6f  retn
0x180065c70  lea     this, [rbp+relativeDueTime]; this
0x180065c74  call    ?TLSAllocData@COleTls@@QEAAJXZ; COleTls::TLSAllocData(void)
0x180065c79  mov     edi, eax
0x180065c7b  test    eax, eax
0x180065c7d  jns     short loc_180065C0B
0x180065c7f  mov     this, [rbp+38h]; callerReturnAddress
0x180065c83  lea     pKeepRetryContextAlive, aOnecoreComComb_7; "onecore\\com\\combase\\dcomrem\\callctr"...
0x180065c8a  mov     r9d, eax; hr
0x180065c8d  mov     edx, 458h; lineNumber
0x180065c92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065c97  mov     eax, edi
0x180065c99  jmp     short loc_180065C61
0x180065c9b  cmp     byte ptr [rbx+34h], 0
0x180065c9f  jz      short loc_180065CC8
0x180065ca1  test    rdi, rdi
0x180065ca4  jz      short loc_180065CAF
0x180065ca6  mov     this, rdi; SRWLock
0x180065ca9  call    cs:__imp_ReleaseSRWLockExclusive
0x180065caf  mov     eax, 80010002h
0x180065cb4  jmp     short loc_180065C61
0x180065cb6  mov     ebx, 8001010Ah
0x180065cbb  lea     this, [rbp+lock]; this
0x180065cbf  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x180065cc4  mov     eax, ebx
0x180065cc6  jmp     short loc_180065C61
0x180065cc8  cmp     dword ptr [r12+40h], 5
0x180065cce  jz      short loc_180065CB6
0x180065cd0  cmp     dword ptr [r12+40h], 2
0x180065cd6  jz      short loc_180065CB6
0x180065cd8  cmp     qword ptr [rbx+18h], 0
0x180065cdd  jnz     loc_180247CE0
0x180065ce3  xor     r8d, r8d; pcbe
0x180065ce6  lea     this, ?RetrySendOnTimerExpiration@AsyncClientCallRetryContext@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180065ced  mov     pAsyncClientTransport, rbx; pv
0x180065cf0  call    cs:__imp_CreateThreadpoolTimer
0x180065cf6  mov     [rbx+18h], rax
0x180065cfa  test    rax, rax
0x180065cfd  jnz     loc_180247CE0
0x180065d03  call    cs:__imp_GetLastError
0x180065d09  mov     ebx, eax
0x180065d0b  test    eax, eax
0x180065d0d  jle     short loc_180065CBB
0x180065d0f  movzx   ebx, ax
0x180065d12  or      ebx, 80070000h
0x180065d18  jmp     short loc_180065CBB
0x180065d1a  mov     rax, [r14]
0x180065d1d  mov     this, r14
0x180065d20  mov     [rbp+other.ptr_], r14
0x180065d24  mov     rax, [rax+8]
0x180065d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d2d  lea     this, [rbx+20h]; this
0x180065d31  lea     pAsyncClientTransport, [rbp+other]; other
0x180065d35  call    ??4?$ComPtr@VOutParameterMarshalingClient@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<OutParameterMarshalingClient>::operator=(Microsoft::WRL::ComPtr<OutParameterMarshalingClient> &&)
0x180065d3a  mov     this, [rbp+other.ptr_]
0x180065d3e  test    this, this
0x180065d41  jz      short loc_180065D4F
0x180065d43  mov     rax, [this]
0x180065d46  mov     rax, [rax+10h]
0x180065d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d4f  mov     [rbp+other.ptr_], rsi
0x180065d53  test    rsi, rsi
0x180065d56  jz      short loc_180065D67
0x180065d58  mov     rax, [rsi]
0x180065d5b  mov     this, rsi
0x180065d5e  mov     rax, [rax+8]
0x180065d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d67  lea     this, [rbx+28h]; this
0x180065d6b  lea     pAsyncClientTransport, [rbp+other]; other
0x180065d6f  call    ??4?$ComPtr@VOutParameterMarshalingClient@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<OutParameterMarshalingClient>::operator=(Microsoft::WRL::ComPtr<OutParameterMarshalingClient> &&)
0x180065d74  mov     this, [rbp+other.ptr_]
0x180065d78  test    this, this
0x180065d7b  jz      short loc_180065D89
0x180065d7d  mov     rax, [this]
0x180065d80  mov     rax, [rax+10h]
0x180065d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d89  mov     [rbx+38h], edi
0x180065d8c  call    cs:__imp_GetTickCount64
0x180065d92  mov     [rbx+40h], rax
0x180065d96  xor     r9d, r9d; msWindowLength
0x180065d99  mov     this, [rbx+18h]; pti
0x180065d9d  lea     pAsyncClientTransport, [rbp+relativeDueTime]; pftDueTime
0x180065da1  imul    rax, rdi, 0FFFFFFFFFFFFD8F0h
0x180065da8  xor     r8d, r8d; msPeriod
0x180065dab  mov     [rbp+relativeDueTime.dwLowDateTime], eax
0x180065dae  shr     rax, 20h
0x180065db2  mov     [rbp+relativeDueTime.dwHighDateTime], eax
0x180065db5  call    cs:__imp_SetThreadpoolTimer
0x180065dbb  mov     dword ptr [rbx+30h], 1
0x180065dc2  mov     ebx, 8001FFFFh
0x180065dc7  jmp     loc_180065CBB
0x180247ce0  mov     rcx, rbx; this
0x180247ce3  call    ?NextAutoRetry@ClientCallRetryContext@@IEAAKXZ; ClientCallRetryContext::NextAutoRetry(void)
0x180247ce8  mov     edi, eax
0x180247cea  cmp     eax, 0FFFFFFFFh
0x180247ced  jnz     short loc_180247CF9
0x180247cef  mov     ebx, 8001FFFEh
0x180247cf4  jmp     loc_180065CBB
0x180247cf9  mov     rax, [rbp+arg_28]
0x180247cfd  mov     r8, r12; completedTransportCall
0x180247d00  mov     r9, [rbp+oid]; oid
0x180247d04  mov     rdx, r14; asyncClientTransport
0x180247d07  mov     rcx, rbx; this
0x180247d0a  mov     [rsp+50h+stdIdentity], rax; stdIdentity
0x180247d0f  call    ?CopyRequestMessageFromAutoRetryResponse@AsyncClientCallRetryContext@@AEAAJPEAUIAsyncClientTransport@@PEAVCAsyncCall@@AEBU_GUID@@PEAVCStdIdentity@@@Z; AsyncClientCallRetryContext::CopyRequestMessageFromAutoRetryResponse(IAsyncClientTransport *,CAsyncCall *,_GUID const &,CStdIdentity *)
0x180247d14  cmp     eax, 8001010Ah
0x180247d19  jz      loc_180065D1A
0x180247d1f  mov     ebx, eax
0x180247d21  jmp     loc_180065CBB
```
