# HNS::Service::Core::StorageManager::Start(void)

- ea: `0x1800b3950`
- end: `0x1800b3ad5`
- name: `?Start@StorageManager@Core@Service@HNS@@UEAAXXZ`
- size: `389`
- prototype: `void __fastcall(HNS::Service::Core::StorageManager *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800663fc`
- `0x18006ea40`
- `0x18007046c`
- `0x1800759d8`
- `0x180075aac`
- `0x1800b368c`
- `0x1800b3950`
- `0x1800b3c50`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b3a99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b3a99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b39c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b39c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3997`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800b39a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800b39a7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800b39b5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800b39b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800b39be`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800b39be`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800b3982`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800b3982`

## string_xrefs

- `0x1800b3abd`: `onecore\vm\dv\net\hns\service\core\storagemanager.cpp`
- `0x1800b3961`: `HNS::Service::Core::StorageManager::Start`
- `0x1800b3aa4`: `HNS::Service::Core::StorageManager::Start`

## pseudocode

```c
void __fastcall HNS::Service::Core::StorageManager::Start(struct _TP_WAIT **this)
{
  PTP_WAIT ThreadpoolWait; // rax
  const char *v3; // r9
  struct _TP_WAIT *v4; // rbp
  PTP_WAIT v5; // rsi
  DWORD LastError; // ebx
  struct _TP_WAIT *v7; // rdx
  signed __int32 v8; // eax
  signed __int32 v9; // ett
  volatile signed __int32 *v10; // rbx
  RTL_SRWLOCK *v11; // rcx
  struct _TP_WAIT *v12; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v13; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  PSRWLOCK SRWLock; // [rsp+60h] [rbp+8h] BYREF

  HNSTraceProvider::TraceEnter("HNS::Service::Core::StorageManager::Start", 0x66u);
  HNS::Service::Core::StorageManager::InitializeDatabase((HNS::Service::Core::StorageManager *)this);
  ThreadpoolWait = CreateThreadpoolWait(lambda_b420158cfb0edf86b9f5d921eb1aa8f7_::_lambda_invoker_cdecl_, this, 0);
  v4 = this[702];
  v5 = ThreadpoolWait;
  if ( v4 )
  {
    LastError = GetLastError();
    SetThreadpoolWait(v4, 0, 0);
    WaitForThreadpoolWaitCallbacks(v4, 1);
    CloseThreadpoolWait(v4);
    SetLastError(LastError);
  }
  this[702] = v5;
  if ( !v5 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\storagemanager.cpp",
      v3);
  v7 = this[9];
  if ( !v7 )
LABEL_17:
    std::_Throw_bad_weak_ptr();
  v8 = *((_DWORD *)v7 + 2);
  do
  {
    if ( !v8 )
      goto LABEL_17;
    v9 = v8;
    v8 = _InterlockedCompareExchange((volatile signed __int32 *)v7 + 2, v8 + 1, v8);
  }
  while ( v9 != v8 );
  v12 = this[8];
  v13 = (volatile signed __int32 *)this[9];
  std::shared_ptr<HNS::Service::Core::NamespaceEntityManager>::operator=(
    &HNS::Service::Core::StorageManager::m_instance,
    &v12);
  v10 = v13;
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  *((_DWORD *)this + 8) = 0;
  HNS::Service::Interface::IManager::AddRef((HNS::Service::Interface::IManager *)this);
  (*((void (__fastcall **)(struct _TP_WAIT **, PSRWLOCK *))*this + 1))(this, &SRWLock);
  v11 = SRWLock;
  *((_DWORD *)this + 20) = 2;
  if ( v11 )
    ReleaseSRWLockExclusive(v11);
  HNSTraceProvider::TraceSuccess("HNS::Service::Core::StorageManager::Start", 0x77u);
}

```

## disassembly

```asm
0x1800b3950  push    rbx
0x1800b3952  push    rbp
0x1800b3953  push    rsi
0x1800b3954  push    rdi
0x1800b3955  sub     rsp, 38h
0x1800b3959  mov     rdi, rcx
0x1800b395c  mov     edx, 66h ; 'f'; unsigned int
0x1800b3961  lea     rcx, aHnsServiceCore_14; "HNS::Service::Core::StorageManager::Sta"...
0x1800b3968  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1800b396d  mov     rcx, rdi; this
0x1800b3970  call    ?InitializeDatabase@StorageManager@Core@Service@HNS@@AEAAXXZ; HNS::Service::Core::StorageManager::InitializeDatabase(void)
0x1800b3975  xor     r8d, r8d; pcbe
0x1800b3978  lea     rcx, _lambda_b420158cfb0edf86b9f5d921eb1aa8f7____lambda_invoker_cdecl_; pfnwa
0x1800b397f  mov     rdx, rdi; pv
0x1800b3982  call    cs:__imp_CreateThreadpoolWait
0x1800b3988  mov     rbp, [rdi+15F0h]
0x1800b398f  mov     rsi, rax
0x1800b3992  test    rbp, rbp
0x1800b3995  jz      short loc_1800B39CC
0x1800b3997  call    cs:__imp_GetLastError
0x1800b399d  xor     r8d, r8d; pftTimeout
0x1800b39a0  xor     edx, edx; h
0x1800b39a2  mov     rcx, rbp; pwa
0x1800b39a5  mov     ebx, eax
0x1800b39a7  call    cs:__imp_SetThreadpoolWait
0x1800b39ad  mov     edx, 1; fCancelPendingCallbacks
0x1800b39b2  mov     rcx, rbp; pwa
0x1800b39b5  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800b39bb  mov     rcx, rbp; pwa
0x1800b39be  call    cs:__imp_CloseThreadpoolWait
0x1800b39c4  mov     ecx, ebx; dwErrCode
0x1800b39c6  call    cs:__imp_SetLastError
0x1800b39cc  mov     [rdi+15F0h], rsi
0x1800b39d3  test    rsi, rsi
0x1800b39d6  jz      loc_1800B3AB8
0x1800b39dc  mov     rdx, [rdi+48h]
0x1800b39e0  test    rdx, rdx
0x1800b39e3  jz      loc_1800B3ACF
0x1800b39e9  mov     eax, [rdx+8]
0x1800b39ec  jmp     short loc_1800B39F8
0x1800b39ee  lea     ecx, [rax+1]
0x1800b39f1  lock cmpxchg [rdx+8], ecx
0x1800b39f6  jz      short loc_1800B3A02
0x1800b39f8  test    eax, eax
0x1800b39fa  jz      loc_1800B3ACF
0x1800b3a00  jmp     short loc_1800B39EE
0x1800b3a02  mov     rax, [rdi+40h]
0x1800b3a06  lea     rdx, [rsp+58h+var_38]
0x1800b3a0b  mov     [rsp+58h+var_38], rax
0x1800b3a10  lea     rcx, ?m_instance@StorageManager@Core@Service@HNS@@0V?$shared_ptr@VStorageManager@Core@Service@HNS@@@std@@A; std::shared_ptr<HNS::Service::Core::StorageManager> HNS::Service::Core::StorageManager::m_instance
0x1800b3a17  mov     rax, [rdi+48h]
0x1800b3a1b  mov     [rsp+58h+var_30], rax
0x1800b3a20  call    ??4?$shared_ptr@VNamespaceEntityManager@Core@Service@HNS@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<HNS::Service::Core::NamespaceEntityManager>::operator=(std::shared_ptr<HNS::Service::Core::NamespaceEntityManager> &&)
0x1800b3a25  mov     rbx, [rsp+58h+var_30]
0x1800b3a2a  test    rbx, rbx
0x1800b3a2d  jz      short loc_1800B3A65
0x1800b3a2f  or      esi, 0FFFFFFFFh
0x1800b3a32  mov     eax, esi
0x1800b3a34  lock xadd [rbx+8], eax
0x1800b3a39  add     eax, esi
0x1800b3a3b  jnz     short loc_1800B3A65
0x1800b3a3d  mov     rax, [rbx]
0x1800b3a40  mov     rcx, rbx
0x1800b3a43  mov     rax, [rax]
0x1800b3a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3a4b  mov     eax, esi
0x1800b3a4d  lock xadd [rbx+0Ch], eax
0x1800b3a52  add     eax, esi
0x1800b3a54  jnz     short loc_1800B3A65
0x1800b3a56  mov     rax, [rbx]
0x1800b3a59  mov     rcx, rbx
0x1800b3a5c  mov     rax, [rax+8]
0x1800b3a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3a65  mov     rcx, rdi; this
0x1800b3a68  mov     dword ptr [rdi+20h], 0
0x1800b3a6f  call    ?AddRef@IManager@Interface@Service@HNS@@QEAAKXZ; HNS::Service::Interface::IManager::AddRef(void)
0x1800b3a74  mov     rax, [rdi]
0x1800b3a77  lea     rdx, [rsp+58h+SRWLock]
0x1800b3a7c  mov     rcx, rdi
0x1800b3a7f  mov     rax, [rax+8]
0x1800b3a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3a88  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x1800b3a8d  mov     dword ptr [rdi+50h], 2
0x1800b3a94  test    rcx, rcx
0x1800b3a97  jz      short loc_1800B3A9F
0x1800b3a99  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b3a9f  mov     edx, 77h ; 'w'; unsigned int
0x1800b3aa4  lea     rcx, aHnsServiceCore_14; "HNS::Service::Core::StorageManager::Sta"...
0x1800b3aab  add     rsp, 38h
0x1800b3aaf  pop     rdi
0x1800b3ab0  pop     rsi
0x1800b3ab1  pop     rbp
0x1800b3ab2  pop     rbx
0x1800b3ab3  jmp     ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x1800b3ab8  mov     rcx, [rsp+58h]; this
0x1800b3abd  lea     r8, aOnecoreVmDvNet_66; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800b3ac4  mov     edx, 74h ; 't'; void *
0x1800b3ac9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b3acf  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
```
