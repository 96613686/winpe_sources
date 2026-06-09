# CloseClientOperationHandle(HCS_OPERATION__ *)

- ea: `0x1800146d4`
- end: `0x1800147e4`
- name: `?CloseClientOperationHandle@@YAXPEAUHCS_OPERATION__@@@Z`
- size: `272`
- prototype: `void __fastcall(struct HCS_OPERATION__ *)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015da0`
- `0x180045158`
- `0x1800453bc`
- `0x1800455c0`
- `0x180045980`
- `0x1800467a8`

## callees

- `0x1800067c0`
- `0x180012edc`
- `0x1800146d4`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001474f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014786`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001474f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014786`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014725`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001475d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014725`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001475d`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180014741`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180014741`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180014777`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180014777`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001472f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001472f`

## pseudocode

```c
void __fastcall CloseClientOperationHandle(struct HCS_OPERATION__ *a1)
{
  RTL_SRWLOCK *v2; // rax
  volatile signed __int32 *v3; // rdi
  RTL_SRWLOCK *v4; // rbx
  char v5; // si
  struct HCS_OPERATION__ *v6; // [rsp+20h] [rbp-18h] BYREF

  v6 = a1;
  ComputeLib::Diagnostics::TraceProvider::HcsOperation_Close<HCS_OPERATION__ * &>(&v6);
  v2 = *(RTL_SRWLOCK **)a1;
  v3 = (volatile signed __int32 *)*((_QWORD *)a1 + 1);
  *(_QWORD *)a1 = 0;
  *((_QWORD *)a1 + 1) = 0;
  if ( v2 )
  {
    v4 = v2 + 6;
    AcquireSRWLockExclusive(v2 + 6);
    LOBYTE(v4[3].Ptr) = 1;
    if ( LODWORD(v4[2].Ptr) == GetCurrentThreadId() )
    {
      v5 = 1;
      WakeAllConditionVariable((PCONDITION_VARIABLE)&v4[1]);
    }
    else
    {
      v5 = 0;
    }
    ReleaseSRWLockExclusive(v4);
    if ( !v5 )
    {
      AcquireSRWLockExclusive(v4);
      LOBYTE(v4[3].Ptr) = 1;
      while ( LODWORD(v4[2].Ptr) )
        SleepConditionVariableSRW((PCONDITION_VARIABLE)&v4[1], v4, 0xFFFFFFFF, 0);
      ReleaseSRWLockExclusive(v4);
    }
  }
  if ( v3 && _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
    if ( !_InterlockedDecrement(v3 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
  }
}

```

## disassembly

```asm
0x1800146d4  mov     r11, rsp
0x1800146d7  mov     [r11+10h], rbx
0x1800146db  mov     [r11+18h], rsi
0x1800146df  push    rdi
0x1800146e0  sub     rsp, 30h
0x1800146e4  mov     rax, cs:__security_cookie
0x1800146eb  xor     rax, rsp
0x1800146ee  mov     [rsp+38h+var_10], rax
0x1800146f3  mov     rbx, rcx
0x1800146f6  mov     [r11-18h], rcx
0x1800146fa  lea     rcx, [r11-18h]
0x1800146fe  call    ??$HcsOperation_Close@AEAPEAUHCS_OPERATION__@@@TraceProvider@Diagnostics@ComputeLib@@SAXAEAPEAUHCS_OPERATION__@@@Z; ComputeLib::Diagnostics::TraceProvider::HcsOperation_Close<HCS_OPERATION__ * &>(HCS_OPERATION__ * &)
0x180014703  mov     rax, [rbx]
0x180014706  mov     rdi, [rbx+8]
0x18001470a  mov     qword ptr [rbx], 0
0x180014711  mov     qword ptr [rbx+8], 0
0x180014719  test    rax, rax
0x18001471c  jz      short loc_18001478C
0x18001471e  lea     rbx, [rax+30h]
0x180014722  mov     rcx, rbx; SRWLock
0x180014725  call    cs:__imp_AcquireSRWLockExclusive
0x18001472b  mov     byte ptr [rbx+18h], 1
0x18001472f  call    cs:__imp_GetCurrentThreadId
0x180014735  cmp     [rbx+10h], eax
0x180014738  jnz     short loc_180014749
0x18001473a  lea     rcx, [rbx+8]; ConditionVariable
0x18001473e  mov     sil, 1
0x180014741  call    cs:__imp_WakeAllConditionVariable
0x180014747  jmp     short loc_18001474C
0x180014749  xor     sil, sil
0x18001474c  mov     rcx, rbx; SRWLock
0x18001474f  call    cs:__imp_ReleaseSRWLockExclusive
0x180014755  test    sil, sil
0x180014758  jnz     short loc_18001478C
0x18001475a  mov     rcx, rbx; SRWLock
0x18001475d  call    cs:__imp_AcquireSRWLockExclusive
0x180014763  mov     byte ptr [rbx+18h], 1
0x180014767  jmp     short loc_18001477D
0x180014769  xor     r9d, r9d; Flags
0x18001476c  lea     rcx, [rbx+8]; ConditionVariable
0x180014770  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180014774  mov     rdx, rbx; SRWLock
0x180014777  call    cs:__imp_SleepConditionVariableSRW
0x18001477d  cmp     dword ptr [rbx+10h], 0
0x180014781  jnz     short loc_180014769
0x180014783  mov     rcx, rbx; SRWLock
0x180014786  call    cs:__imp_ReleaseSRWLockExclusive
0x18001478c  test    rdi, rdi
0x18001478f  jz      short loc_1800147C7
0x180014791  or      ebx, 0FFFFFFFFh
0x180014794  mov     eax, ebx
0x180014796  lock xadd [rdi+8], eax
0x18001479b  add     eax, ebx
0x18001479d  jnz     short loc_1800147C7
0x18001479f  mov     rax, [rdi]
0x1800147a2  mov     rcx, rdi
0x1800147a5  mov     rax, [rax]
0x1800147a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147ad  mov     eax, ebx
0x1800147af  lock xadd [rdi+0Ch], eax
0x1800147b4  add     eax, ebx
0x1800147b6  jnz     short loc_1800147C7
0x1800147b8  mov     rax, [rdi]
0x1800147bb  mov     rcx, rdi
0x1800147be  mov     rax, [rax+8]
0x1800147c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147c7  mov     rcx, [rsp+38h+var_10]
0x1800147cc  xor     rcx, rsp; StackCookie
0x1800147cf  call    __security_check_cookie
0x1800147d4  mov     rbx, [rsp+38h+arg_8]
0x1800147d9  mov     rsi, [rsp+38h+arg_10]
0x1800147de  add     rsp, 30h
0x1800147e2  pop     rdi
0x1800147e3  retn
```
