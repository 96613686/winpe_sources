# Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::NotificationDeliveryThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180005d10`
- end: `0x180005ea7`
- name: `?NotificationDeliveryThread@?$InProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `407`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800048a0`
- `0x180005d10`
- `0x180006f7c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d9f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e3c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d9f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d80`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180005e15`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180005e15`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180005db9`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180005db9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d39`

## string_xrefs

- `0x180005e94`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::NotificationDeliveryThread(
        PTP_CALLBACK_INSTANCE Instance,
        _QWORD *Context,
        PTP_WORK Work)
{
  __int64 v3; // rsi
  volatile signed __int32 *v4; // r14
  RTL_SRWLOCK *v5; // rbx
  DWORD LastError; // edi
  const char *v7; // r9
  char v8; // al
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+68h] [rbp+20h]

  v3 = Context[1];
  v4 = (volatile signed __int32 *)Context[2];
  if ( v4 )
    _InterlockedIncrement(v4 + 2);
  *(_DWORD *)(v3 + 100) = GetCurrentThreadId();
  v5 = (RTL_SRWLOCK *)(v3 + 16);
  AcquireSRWLockExclusive((PSRWLOCK)(v3 + 16));
  while ( *(_QWORD *)(v3 + 72) && !*(_BYTE *)(v3 + 104) )
  {
    if ( v5 )
    {
      LastError = GetLastError();
      ReleaseSRWLockExclusive(v5);
      SetLastError(LastError);
    }
    v12 = 0;
    v11 = 0;
    AcquireSRWLockExclusive((PSRWLOCK)(v3 + 40));
    while ( !*(_QWORD *)(v3 + 72) )
    {
      if ( SleepConditionVariableSRW((PCONDITION_VARIABLE)(v3 + 24), (PSRWLOCK)(v3 + 40), 0, 0) )
      {
        v8 = 0;
      }
      else
      {
        if ( GetLastError() != 1460 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xF46,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v7);
        v8 = 1;
      }
      if ( v8 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB0,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslBuffer.h",
          v7);
    }
    v11 = *(_QWORD *)(v3 + 8LL * *(_QWORD *)(v3 + 56) + 48);
    *(_QWORD *)(v3 + 56) = 0;
    --*(_QWORD *)(v3 + 72);
    if ( v3 != -40 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v3 + 40));
    WakeConditionVariable((PCONDITION_VARIABLE)(v3 + 32));
    try
    {
      (*(void (__fastcall **)(__int64 *, _QWORD))v3)(&v11, *(_QWORD *)(v3 + 8));
    }
    catch ( ... )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x148,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
        v9);
    }
    if ( *(_BYTE *)(v3 + 105) )
      goto LABEL_23;
    v5 = (RTL_SRWLOCK *)(v3 + 16);
    AcquireSRWLockExclusive((PSRWLOCK)(v3 + 16));
  }
  *(_DWORD *)(v3 + 100) = -1;
  *(_BYTE *)(v3 + 96) = 0;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
LABEL_23:
  if ( v4 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v4);
}

```

## disassembly

```asm
0x180005d10  mov     [rsp+arg_0], rbx
0x180005d15  push    rsi
0x180005d16  push    rdi
0x180005d17  push    r14
0x180005d19  sub     rsp, 30h
0x180005d1d  mov     rsi, [rdx+8]
0x180005d21  mov     r14, [rdx+10h]
0x180005d25  mov     [rsp+48h+var_28], rsi
0x180005d2a  mov     [rsp+48h+var_20], r14
0x180005d2f  test    r14, r14
0x180005d32  jz      short loc_180005D39
0x180005d34  lock inc dword ptr [r14+8]
0x180005d39  call    cs:__imp_GetCurrentThreadId
0x180005d3f  mov     [rsi+64h], eax
0x180005d42  lea     rbx, [rsi+10h]
0x180005d46  mov     rcx, rbx; SRWLock
0x180005d49  call    cs:__imp_AcquireSRWLockExclusive
0x180005d4f  nop
0x180005d50  mov     rax, rbx
0x180005d53  cmp     qword ptr [rsi+48h], 0
0x180005d58  jz      loc_180005E47
0x180005d5e  cmp     byte ptr [rsi+68h], 0
0x180005d62  jnz     loc_180005E47
0x180005d68  test    rax, rax
0x180005d6b  jz      short loc_180005D86
0x180005d6d  call    cs:__imp_GetLastError
0x180005d73  mov     edi, eax
0x180005d75  mov     rcx, rbx; SRWLock
0x180005d78  call    cs:__imp_ReleaseSRWLockExclusive
0x180005d7e  mov     ecx, edi; dwErrCode
0x180005d80  call    cs:__imp_SetLastError
0x180005d86  mov     [rsp+48h+arg_18], 0
0x180005d8f  mov     [rsp+48h+arg_8], 0
0x180005d98  lea     rdi, [rsi+28h]
0x180005d9c  mov     rcx, rdi; SRWLock
0x180005d9f  call    cs:__imp_AcquireSRWLockExclusive
0x180005da5  cmp     qword ptr [rsi+48h], 0
0x180005daa  jnz     short loc_180005DE9
0x180005dac  xor     r9d, r9d; Flags
0x180005daf  xor     r8d, r8d; dwMilliseconds
0x180005db2  mov     rdx, rdi; SRWLock
0x180005db5  lea     rcx, [rsi+18h]; ConditionVariable
0x180005db9  call    cs:__imp_SleepConditionVariableSRW
0x180005dbf  test    eax, eax
0x180005dc1  jz      short loc_180005DC7
0x180005dc3  xor     al, al
0x180005dc5  jmp     short loc_180005DDA
0x180005dc7  call    cs:__imp_GetLastError
0x180005dcd  cmp     eax, 5B4h
0x180005dd2  jnz     loc_180005E8F
0x180005dd8  mov     al, 1
0x180005dda  mov     rcx, [rsp+48h]; this
0x180005ddf  test    al, al
0x180005de1  jnz     loc_180005E7D
0x180005de7  jmp     short loc_180005DA5
0x180005de9  mov     rax, [rsi+38h]
0x180005ded  mov     rdx, [rsi+rax*8+30h]
0x180005df2  mov     [rsp+48h+arg_8], rdx
0x180005df7  mov     qword ptr [rsi+38h], 0
0x180005dff  dec     qword ptr [rsi+48h]
0x180005e03  test    rdi, rdi
0x180005e06  jz      short loc_180005E11
0x180005e08  mov     rcx, rdi; SRWLock
0x180005e0b  call    cs:__imp_ReleaseSRWLockExclusive
0x180005e11  lea     rcx, [rsi+20h]; ConditionVariable
0x180005e15  call    cs:__imp_WakeConditionVariable
0x180005e1b  mov     rdx, [rsi+8]
0x180005e1f  lea     rcx, [rsp+48h+arg_8]
0x180005e24  mov     rax, [rsi]
0x180005e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e2c  nop
0x180005e2d  cmp     byte ptr [rsi+69h], 0
0x180005e31  jz      short loc_180005E35
0x180005e33  jmp     short loc_180005E61
0x180005e35  lea     rbx, [rsi+10h]
0x180005e39  mov     rcx, rbx; SRWLock
0x180005e3c  call    cs:__imp_AcquireSRWLockExclusive
0x180005e42  jmp     loc_180005D50
0x180005e47  mov     dword ptr [rsi+64h], 0FFFFFFFFh
0x180005e4e  mov     byte ptr [rsi+60h], 0
0x180005e52  test    rax, rax
0x180005e55  jz      short loc_180005E61
0x180005e57  mov     rcx, rbx; SRWLock
0x180005e5a  call    cs:__imp_ReleaseSRWLockExclusive
0x180005e60  nop
0x180005e61  test    r14, r14
0x180005e64  jz      short loc_180005E6F
0x180005e66  mov     rcx, r14; this
0x180005e69  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180005e6e  nop
0x180005e6f  mov     rbx, [rsp+48h+arg_0]
0x180005e74  add     rsp, 30h
0x180005e78  pop     r14
0x180005e7a  pop     rdi
0x180005e7b  pop     rsi
0x180005e7c  retn
0x180005e7d  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180005e84  mov     edx, 0B0h; void *
0x180005e89  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180005e8f  mov     rcx, [rsp+48h]; this
0x180005e94  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005e9b  mov     edx, 0F46h; void *
0x180005ea0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
