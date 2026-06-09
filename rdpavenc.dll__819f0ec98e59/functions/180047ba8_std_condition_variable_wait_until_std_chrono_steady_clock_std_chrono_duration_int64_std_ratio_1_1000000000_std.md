# std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::unique_lock<std::mutex> &,std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)

- ea: `0x180047ba8`
- end: `0x180047c77`
- name: `??$wait_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@condition_variable@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vmutex@std@@@1@AEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z`
- size: `207`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800495c4`
- `0x180049af8`
- `0x1800602ac`
- `0x180060520`

## callees

- `0x18002700c`
- `0x180047ba8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047c47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047c47`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180047c3f`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180047c3f`

## pseudocode

```c
__int64 __fastcall std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
        RTL_CONDITION_VARIABLE *a1,
        __int64 *a2,
        _QWORD *a3)
{
  __int64 v6; // r9
  __int64 v7; // r8
  __int64 v8; // rdi
  BOOL v9; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v12; // [rsp+50h] [rbp+18h] BYREF

  while ( 1 )
  {
    std::chrono::steady_clock::now(&v12);
    if ( *a3 == v12 || *a3 < v12 )
      break;
    v6 = *a3 - v12;
    if ( v6 < 0x4E94914F0001LL )
    {
      v7 = v6 / 1000000;
      if ( 1000000 * (v6 / 1000000) < v6 )
        LODWORD(v7) = v7 + 1;
    }
    else
    {
      LODWORD(v7) = 86400000;
    }
    v8 = *a2;
    --*(_DWORD *)(v8 + 76);
    *(_DWORD *)(v8 + 72) = -1;
    v9 = SleepConditionVariableSRW(a1 + 1, (PSRWLOCK)(v8 + 16), v7, 0);
    CurrentThreadId = GetCurrentThreadId();
    ++*(_DWORD *)(v8 + 76);
    *(_DWORD *)(v8 + 72) = CurrentThreadId;
    if ( v9 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180047ba8  mov     [rsp+arg_0], rbx
0x180047bad  mov     [rsp+arg_8], rbp
0x180047bb2  push    rsi
0x180047bb3  push    rdi
0x180047bb4  push    r14
0x180047bb6  sub     rsp, 20h
0x180047bba  mov     rsi, r8
0x180047bbd  mov     r14, rdx
0x180047bc0  mov     rbp, rcx
0x180047bc3  lea     rcx, [rsp+38h+arg_10]
0x180047bc8  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180047bcd  mov     rax, [rsp+38h+arg_10]
0x180047bd2  mov     r9, [rsi]
0x180047bd5  cmp     r9, rax
0x180047bd8  jz      loc_180047C5F
0x180047bde  jl      short loc_180047C5F
0x180047be0  sub     r9, rax
0x180047be3  mov     rax, 4E94914F0001h
0x180047bed  cmp     r9, rax
0x180047bf0  jl      short loc_180047BFA
0x180047bf2  mov     r8d, 5265C00h
0x180047bf8  jmp     short loc_180047C27
0x180047bfa  mov     rax, 431BDE82D7B634DBh
0x180047c04  imul    r9
0x180047c07  mov     r8, rdx
0x180047c0a  sar     r8, 12h
0x180047c0e  mov     rax, r8
0x180047c11  shr     rax, 3Fh
0x180047c15  add     r8, rax
0x180047c18  imul    rax, r8, 0F4240h
0x180047c1f  cmp     rax, r9
0x180047c22  jge     short loc_180047C27
0x180047c24  inc     r8; dwMilliseconds
0x180047c27  mov     rdi, [r14]
0x180047c2a  lea     rcx, [rbp+8]; ConditionVariable
0x180047c2e  xor     r9d, r9d; Flags
0x180047c31  dec     dword ptr [rdi+4Ch]
0x180047c34  lea     rdx, [rdi+10h]; SRWLock
0x180047c38  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x180047c3f  call    cs:__imp_SleepConditionVariableSRW
0x180047c45  mov     ebx, eax
0x180047c47  call    cs:__imp_GetCurrentThreadId
0x180047c4d  inc     dword ptr [rdi+4Ch]
0x180047c50  mov     [rdi+48h], eax
0x180047c53  test    ebx, ebx
0x180047c55  jz      loc_180047BC3
0x180047c5b  xor     eax, eax
0x180047c5d  jmp     short loc_180047C64
0x180047c5f  mov     eax, 1
0x180047c64  mov     rbx, [rsp+38h+arg_0]
0x180047c69  mov     rbp, [rsp+38h+arg_8]
0x180047c6e  add     rsp, 20h
0x180047c72  pop     r14
0x180047c74  pop     rdi
0x180047c75  pop     rsi
0x180047c76  retn
```
