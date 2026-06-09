# HcsClient::NotificationWorker::Worker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18004c990`
- end: `0x18004cb1d`
- name: `?Worker@NotificationWorker@HcsClient@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `397`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800067c0`
- `0x18002a03c`
- `0x18002a610`
- `0x18004ac68`
- `0x18004c990`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ca6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004cabe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ca6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004cabe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ca26`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ca89`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ca26`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ca89`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004ca44`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004caa7`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004ca44`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004caa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c9fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c9fe`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18004ca0a`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18004ca0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall HcsClient::NotificationWorker::Worker(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  __int64 v5; // rdx
  signed __int32 v6; // eax
  signed __int32 v7; // ett
  __int128 v8; // kr00_16
  _BYTE v9[16]; // [rsp+30h] [rbp-38h] BYREF

  v5 = *((_QWORD *)Context + 9);
  if ( v5 )
  {
    v6 = *(_DWORD *)(v5 + 8);
    while ( v6 )
    {
      v7 = v6;
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 8), v6 + 1, v6);
      if ( v7 == v6 )
      {
        v8 = *((_OWORD *)Context + 4);
        goto LABEL_6;
      }
    }
  }
  v8 = 0;
LABEL_6:
  if ( (_QWORD)v8 )
  {
    CallbackManager::Enter((PSRWLOCK)Context, (__int64)v9);
    if ( v9[8] )
    {
      *((_DWORD *)Context + 15) = GetCurrentThreadId();
      CallbackMayRunLong(Instance);
      HcsClient::OperationTracker::QueueWorker((HcsClient::OperationTracker *)v8);
      *((_DWORD *)Context + 15) = 0;
    }
    AcquireSRWLockExclusive((PSRWLOCK)Context + 5);
    if ( *((_DWORD *)Context + 14) == 1 )
    {
      *((_DWORD *)Context + 14) = 0;
    }
    else if ( *((_DWORD *)Context + 14) == 2 )
    {
      *((_DWORD *)Context + 14) = 3;
      WakeAllConditionVariable((PCONDITION_VARIABLE)Context + 6);
    }
    if ( Context != (PVOID)-40LL )
      ReleaseSRWLockExclusive((PSRWLOCK)Context + 5);
    std::_Optional_destruct_base<CallbackReference,0>::~_Optional_destruct_base<CallbackReference,0>(v9);
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)Context + 5);
    if ( *((_DWORD *)Context + 14) == 1 )
    {
      *((_DWORD *)Context + 14) = 0;
    }
    else if ( *((_DWORD *)Context + 14) == 2 )
    {
      *((_DWORD *)Context + 14) = 3;
      WakeAllConditionVariable((PCONDITION_VARIABLE)Context + 6);
    }
    if ( Context != (PVOID)-40LL )
      ReleaseSRWLockExclusive((PSRWLOCK)Context + 5);
  }
  if ( *((_QWORD *)&v8 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v8 + 1) + 8LL), 0xFFFFFFFF) == 1 )
  {
    (***((void (__fastcall ****)(_QWORD))&v8 + 1))(*((_QWORD *)&v8 + 1));
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v8 + 1) + 12LL)) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v8 + 1) + 8LL))(*((_QWORD *)&v8 + 1));
  }
}

```

## disassembly

```asm
0x18004c990  mov     [rsp+arg_10], rbx
0x18004c995  push    rbp
0x18004c996  push    rsi
0x18004c997  push    rdi
0x18004c998  sub     rsp, 50h
0x18004c99c  mov     rax, cs:__security_cookie
0x18004c9a3  xor     rax, rsp
0x18004c9a6  mov     [rsp+68h+var_28], rax
0x18004c9ab  mov     rdi, rdx
0x18004c9ae  mov     rbp, rcx
0x18004c9b1  xorps   xmm1, xmm1
0x18004c9b4  movdqu  xmmword ptr [rsp+68h+var_48], xmm1
0x18004c9ba  mov     rdx, [rdx+48h]
0x18004c9be  test    rdx, rdx
0x18004c9c1  jz      short loc_18004C9D6
0x18004c9c3  mov     eax, [rdx+8]
0x18004c9c6  jmp     short loc_18004C9D2
0x18004c9c8  lea     ecx, [rax+1]
0x18004c9cb  lock cmpxchg [rdx+8], ecx
0x18004c9d0  jz      short loc_18004CA4C
0x18004c9d2  test    eax, eax
0x18004c9d4  jnz     short loc_18004C9C8
0x18004c9d6  mov     rsi, [rsp+68h+var_48]
0x18004c9db  mov     rbx, [rsp+68h+var_48+8]
0x18004c9e0  test    rsi, rsi
0x18004c9e3  jz      loc_18004CA82
0x18004c9e9  lea     rdx, [rsp+68h+var_38]
0x18004c9ee  mov     rcx, rdi; SRWLock
0x18004c9f1  call    ?Enter@CallbackManager@@QEAA?AV?$optional@VCallbackReference@@@std@@XZ; CallbackManager::Enter(void)
0x18004c9f6  nop
0x18004c9f7  cmp     [rsp+68h+var_30], 0
0x18004c9fc  jz      short loc_18004CA1F
0x18004c9fe  call    cs:__imp_GetCurrentThreadId
0x18004ca04  mov     [rdi+3Ch], eax
0x18004ca07  mov     rcx, rbp; pci
0x18004ca0a  call    cs:__imp_CallbackMayRunLong
0x18004ca10  mov     rcx, rsi; this
0x18004ca13  call    ?QueueWorker@OperationTracker@HcsClient@@AEAAXXZ; HcsClient::OperationTracker::QueueWorker(void)
0x18004ca18  mov     dword ptr [rdi+3Ch], 0
0x18004ca1f  lea     rsi, [rdi+28h]
0x18004ca23  mov     rcx, rsi; SRWLock
0x18004ca26  call    cs:__imp_AcquireSRWLockExclusive
0x18004ca2c  mov     ecx, [rdi+38h]
0x18004ca2f  sub     ecx, 1
0x18004ca32  jz      short loc_18004CA60
0x18004ca34  cmp     ecx, 1
0x18004ca37  jnz     short loc_18004CA67
0x18004ca39  mov     dword ptr [rdi+38h], 3
0x18004ca40  lea     rcx, [rdi+30h]; ConditionVariable
0x18004ca44  call    cs:__imp_WakeAllConditionVariable
0x18004ca4a  jmp     short loc_18004CA67
0x18004ca4c  mov     rsi, [rdi+40h]
0x18004ca50  mov     [rsp+68h+var_48], rsi
0x18004ca55  mov     rbx, [rdi+48h]
0x18004ca59  mov     [rsp+68h+var_48+8], rbx
0x18004ca5e  jmp     short loc_18004C9E0
0x18004ca60  mov     dword ptr [rdi+38h], 0
0x18004ca67  test    rsi, rsi
0x18004ca6a  jz      short loc_18004CA76
0x18004ca6c  mov     rcx, rsi; SRWLock
0x18004ca6f  call    cs:__imp_ReleaseSRWLockExclusive
0x18004ca75  nop
0x18004ca76  lea     rcx, [rsp+68h+var_38]
0x18004ca7b  call    ??1?$_Optional_destruct_base@VCallbackReference@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<CallbackReference,0>::~_Optional_destruct_base<CallbackReference,0>(void)
0x18004ca80  jmp     short loc_18004CAC5
0x18004ca82  lea     rsi, [rdi+28h]
0x18004ca86  mov     rcx, rsi; SRWLock
0x18004ca89  call    cs:__imp_AcquireSRWLockExclusive
0x18004ca8f  mov     ecx, [rdi+38h]
0x18004ca92  sub     ecx, 1
0x18004ca95  jz      short loc_18004CAAF
0x18004ca97  cmp     ecx, 1
0x18004ca9a  jnz     short loc_18004CAB6
0x18004ca9c  mov     dword ptr [rdi+38h], 3
0x18004caa3  lea     rcx, [rdi+30h]; ConditionVariable
0x18004caa7  call    cs:__imp_WakeAllConditionVariable
0x18004caad  jmp     short loc_18004CAB6
0x18004caaf  mov     dword ptr [rdi+38h], 0
0x18004cab6  test    rsi, rsi
0x18004cab9  jz      short loc_18004CAC5
0x18004cabb  mov     rcx, rsi; SRWLock
0x18004cabe  call    cs:__imp_ReleaseSRWLockExclusive
0x18004cac4  nop
0x18004cac5  test    rbx, rbx
0x18004cac8  jz      short loc_18004CB00
0x18004caca  or      edi, 0FFFFFFFFh
0x18004cacd  mov     eax, edi
0x18004cacf  lock xadd [rbx+8], eax
0x18004cad4  add     eax, edi
0x18004cad6  jnz     short loc_18004CB00
0x18004cad8  mov     rax, [rbx]
0x18004cadb  mov     rcx, rbx
0x18004cade  mov     rax, [rax]
0x18004cae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cae6  mov     eax, edi
0x18004cae8  lock xadd [rbx+0Ch], eax
0x18004caed  add     eax, edi
0x18004caef  jnz     short loc_18004CB00
0x18004caf1  mov     rax, [rbx]
0x18004caf4  mov     rcx, rbx
0x18004caf7  mov     rax, [rax+8]
0x18004cafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb00  mov     rcx, [rsp+68h+var_28]
0x18004cb05  xor     rcx, rsp; StackCookie
0x18004cb08  call    __security_check_cookie
0x18004cb0d  mov     rbx, [rsp+68h+arg_10]
0x18004cb15  add     rsp, 50h
0x18004cb19  pop     rdi
0x18004cb1a  pop     rsi
0x18004cb1b  pop     rbp
0x18004cb1c  retn
```
