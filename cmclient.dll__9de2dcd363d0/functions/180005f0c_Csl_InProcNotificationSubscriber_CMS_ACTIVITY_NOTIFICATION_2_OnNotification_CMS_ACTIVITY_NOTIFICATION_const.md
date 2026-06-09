# Csl::InProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::OnNotification(_CMS_ACTIVITY_NOTIFICATION const &)

- ea: `0x180005f0c`
- end: `0x180006063`
- name: `?OnNotification@?$InProcNotificationSubscriber@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAAXAEBU_CMS_ACTIVITY_NOTIFICATION@@@Z`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006210`

## callees

- `0x1800048a0`
- `0x180005f0c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180006015`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180006015`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005f31`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005ff8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005f31`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005ff8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f62`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005fdc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006023`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f62`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005fdc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f92`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180005fe6`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180005fe6`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180005f84`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180005f84`

## string_xrefs

- `0x18000603f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Csl::InProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::OnNotification(
        __int64 a1,
        __int64 *a2)
{
  __int64 v3; // rbx
  unsigned __int8 (__fastcall *v4)(__int64 *, __int64, _QWORD); // rax
  const char *v5; // r9
  char v6; // al
  RTL_SRWLOCK *v7; // rbx
  __int64 v8; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 8);
  v10 = *a2;
  AcquireSRWLockExclusive((PSRWLOCK)(v3 + 40));
  v4 = *(unsigned __int8 (__fastcall **)(__int64 *, __int64, _QWORD))(v3 + 88);
  if ( !v4 || v4(&v10, v3 + 24, *(_QWORD *)(v3 + 96)) )
  {
    while ( *(_QWORD *)(v3 + 80) == 2 )
    {
      if ( SleepConditionVariableSRW((PCONDITION_VARIABLE)(v3 + 32), (PSRWLOCK)(v3 + 40), 0x3A98u, 0) )
      {
        v6 = 0;
      }
      else
      {
        if ( GetLastError() != 1460 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xF46,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v5);
        v6 = 1;
      }
      if ( v6 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x86,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslBuffer.h",
          v5);
    }
    *(_QWORD *)(v3 + 8LL * *(_QWORD *)(v3 + 72) + 48) = v10;
    *(_QWORD *)(v3 + 72) = ((unsigned __int8)*(_QWORD *)(v3 + 72) - 1) & 1;
    ++*(_QWORD *)(v3 + 80);
    if ( v3 != -40 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v3 + 40));
    WakeConditionVariable((PCONDITION_VARIABLE)(v3 + 24));
  }
  else if ( v3 != -40 )
  {
    ReleaseSRWLockExclusive((PSRWLOCK)(v3 + 40));
  }
  v7 = (RTL_SRWLOCK *)(*(_QWORD *)(a1 + 8) + 16LL);
  AcquireSRWLockExclusive(v7);
  v8 = *(_QWORD *)(a1 + 8);
  if ( !*(_BYTE *)(v8 + 112) && !*(_BYTE *)(v8 + 104) )
  {
    *(_BYTE *)(v8 + 104) = 1;
    SubmitThreadpoolWork(*(PTP_WORK *)a1);
  }
  if ( v7 )
    ReleaseSRWLockExclusive(v7);
}

```

## disassembly

```asm
0x180005f0c  mov     [rsp+arg_8], rbx
0x180005f11  mov     [rsp+arg_10], rsi
0x180005f16  push    rdi
0x180005f17  sub     rsp, 20h
0x180005f1b  mov     rsi, rcx
0x180005f1e  mov     rbx, [rcx+8]
0x180005f22  mov     rax, [rdx]
0x180005f25  mov     [rsp+28h+arg_0], rax
0x180005f2a  lea     rdi, [rbx+28h]
0x180005f2e  mov     rcx, rdi; SRWLock
0x180005f31  call    cs:__imp_AcquireSRWLockExclusive
0x180005f37  mov     rax, [rbx+58h]
0x180005f3b  test    rax, rax
0x180005f3e  jz      short loc_180005F6D
0x180005f40  mov     r8, [rbx+60h]
0x180005f44  lea     rdx, [rbx+18h]
0x180005f48  lea     rcx, [rsp+28h+arg_0]
0x180005f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f52  test    al, al
0x180005f54  jnz     short loc_180005F6D
0x180005f56  test    rdi, rdi
0x180005f59  jz      loc_180005FED
0x180005f5f  mov     rcx, rdi; SRWLock
0x180005f62  call    cs:__imp_ReleaseSRWLockExclusive
0x180005f68  jmp     loc_180005FED
0x180005f6d  cmp     qword ptr [rbx+50h], 2
0x180005f72  jnz     short loc_180005FB4
0x180005f74  lea     rcx, [rbx+20h]; ConditionVariable
0x180005f78  xor     r9d, r9d; Flags
0x180005f7b  mov     r8d, 3A98h; dwMilliseconds
0x180005f81  mov     rdx, rdi; SRWLock
0x180005f84  call    cs:__imp_SleepConditionVariableSRW
0x180005f8a  test    eax, eax
0x180005f8c  jz      short loc_180005F92
0x180005f8e  xor     al, al
0x180005f90  jmp     short loc_180005FA5
0x180005f92  call    cs:__imp_GetLastError
0x180005f98  cmp     eax, 5B4h
0x180005f9d  jnz     loc_18000603A
0x180005fa3  mov     al, 1
0x180005fa5  mov     rcx, [rsp+28h]; this
0x180005faa  test    al, al
0x180005fac  jnz     loc_180006051
0x180005fb2  jmp     short loc_180005F6D
0x180005fb4  mov     rdx, [rbx+48h]
0x180005fb8  mov     rax, [rsp+28h+arg_0]
0x180005fbd  mov     [rbx+rdx*8+30h], rax
0x180005fc2  mov     rax, [rbx+48h]
0x180005fc6  dec     rax
0x180005fc9  and     eax, 1
0x180005fcc  mov     [rbx+48h], rax
0x180005fd0  inc     qword ptr [rbx+50h]
0x180005fd4  test    rdi, rdi
0x180005fd7  jz      short loc_180005FE2
0x180005fd9  mov     rcx, rdi; SRWLock
0x180005fdc  call    cs:__imp_ReleaseSRWLockExclusive
0x180005fe2  lea     rcx, [rbx+18h]; ConditionVariable
0x180005fe6  call    cs:__imp_WakeConditionVariable
0x180005fec  nop
0x180005fed  mov     rbx, [rsi+8]
0x180005ff1  add     rbx, 10h
0x180005ff5  mov     rcx, rbx; SRWLock
0x180005ff8  call    cs:__imp_AcquireSRWLockExclusive
0x180005ffe  mov     rax, [rsi+8]
0x180006002  cmp     byte ptr [rax+70h], 0
0x180006006  jnz     short loc_18000601B
0x180006008  cmp     byte ptr [rax+68h], 0
0x18000600c  jnz     short loc_18000601B
0x18000600e  mov     byte ptr [rax+68h], 1
0x180006012  mov     rcx, [rsi]; pwk
0x180006015  call    cs:__imp_SubmitThreadpoolWork
0x18000601b  test    rbx, rbx
0x18000601e  jz      short loc_18000602A
0x180006020  mov     rcx, rbx; SRWLock
0x180006023  call    cs:__imp_ReleaseSRWLockExclusive
0x180006029  nop
0x18000602a  mov     rbx, [rsp+28h+arg_8]
0x18000602f  mov     rsi, [rsp+28h+arg_10]
0x180006034  add     rsp, 20h
0x180006038  pop     rdi
0x180006039  retn
0x18000603a  mov     rcx, [rsp+28h]; this
0x18000603f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006046  mov     edx, 0F46h; void *
0x18000604b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006051  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180006058  mov     edx, 86h; void *
0x18000605d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
