# CHttpRangesRateLimiter::_ThreadProc(void)

- ea: `0x180051e04`
- end: `0x1800520b8`
- name: `?_ThreadProc@CHttpRangesRateLimiter@@AEAAXXZ`
- size: `692`
- prototype: `void __fastcall(CHttpRangesRateLimiter *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180052410`

## callees

- `0x1800199b4`
- `0x180019c5c`
- `0x18001eeac`
- `0x180047e28`
- `0x180051e04`
- `0x180052268`
- `0x18006ff8c`
- `0x1800bff90`
- `0x1800f8134`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180051ebe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180051f19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180051ebe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180051f19`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005203b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052075`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005203b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052075`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180051eb0`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180051f0b`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180051eb0`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180051f0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CHttpRangesRateLimiter::_ThreadProc(CHttpRangesRateLimiter *this)
{
  char *v2; // rdi
  __int64 v3; // rbx
  __int64 *v4; // rax
  unsigned int v5; // r15d
  unsigned int v6; // r11d
  unsigned __int64 v7; // r10
  CHttpRangesDownload *v8; // rcx
  unsigned __int64 v9; // rax
  __int64 v10; // r8
  unsigned __int64 v11; // rbx
  _QWORD *v12; // rax
  bool v13; // zf
  CHttpRangesDownload *v14; // [rsp+20h] [rbp-30h] BYREF
  __int64 v15; // [rsp+28h] [rbp-28h] BYREF
  __int128 v16; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v17[8]; // [rsp+40h] [rbp-10h] BYREF
  _BYTE v18[8]; // [rsp+48h] [rbp-8h] BYREF

  std::chrono::steady_clock::now(&v15);
  v2 = (char *)this + 152;
  v16 = (unsigned __int64)this + 152;
  if ( (unsigned int)mtx_do_lock((char *)this + 152) )
LABEL_40:
    std::_Throw_Cpp_error(5);
  v3 = v15;
  while ( 1 )
  {
    if ( *((_DWORD *)this + 57) == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 57) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    BYTE8(v16) = 1;
    if ( !*((_BYTE *)this + 320) )
      break;
    if ( *((_QWORD *)this + 9) )
    {
      if ( *((_QWORD *)this + 4) < (unsigned __int64)*((unsigned int *)this + 22) )
      {
        v4 = (__int64 *)std::chrono::steady_clock::now(v17);
        if ( v3 == *v4 || v3 < *v4 )
        {
          v5 = 0;
          while ( 1 )
          {
            v10 = *((_QWORD *)this + 9);
            if ( !v10 )
              break;
            v6 = *((_DWORD *)this + 21);
            if ( v5 >= v6 || *((_QWORD *)this + 4) >= (unsigned __int64)*((unsigned int *)this + 22) )
              break;
            v7 = *((_QWORD *)this + 8);
            v8 = *(CHttpRangesDownload **)(*(_QWORD *)(*((_QWORD *)this + 6)
                                                     + 8 * ((*((_QWORD *)this + 7) - 1LL) & (v7 >> 1)))
                                         + 8 * (v7 & 1));
            v14 = v8;
            v9 = v10 - 1;
            *((_QWORD *)this + 9) = v10 - 1;
            if ( v10 != 1 )
              v9 = v7 + 1;
            *((_QWORD *)this + 8) = v9;
            v5 += CHttpRangesDownload::SendNextRequestCallback(v8, v6);
            std::deque<CHttpRangesDownload *>::push_back(this, &v14);
          }
          CRateTracker::AddDataCount((CHttpRangesRateLimiter *)((char *)this + 96), v5);
          if ( *((_DWORD *)this + 20) && v5 )
          {
            v11 = 1000 * (unsigned __int64)v5 / *((unsigned int *)this + 20);
            v12 = (_QWORD *)std::chrono::steady_clock::now(v18);
            if ( v11 < 0xA )
              v11 = 10;
            v3 = *v12 + 1000000 * v11;
            v15 = v3;
          }
        }
        else
        {
          while ( *((_BYTE *)this + 320)
               && (unsigned int)std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
                                  (char *)this + 232,
                                  &v16,
                                  &v15) != 1 )
            ;
        }
      }
      else
      {
        while ( *((_BYTE *)this + 320) && *((_QWORD *)this + 4) >= (unsigned __int64)*((unsigned int *)this + 22) )
        {
          *((_DWORD *)v2 + 18) = -1;
          --*((_DWORD *)v2 + 19);
          if ( !SleepConditionVariableSRW((PCONDITION_VARIABLE)this + 30, (PSRWLOCK)v2 + 2, 0xFFFFFFFF, 0) )
LABEL_39:
            abort();
          *((_DWORD *)v2 + 18) = GetCurrentThreadId();
          ++*((_DWORD *)v2 + 19);
        }
      }
    }
    else
    {
      while ( *((_BYTE *)this + 320) && !*((_QWORD *)this + 9) )
      {
        *((_DWORD *)v2 + 18) = -1;
        --*((_DWORD *)v2 + 19);
        if ( !SleepConditionVariableSRW((PCONDITION_VARIABLE)this + 30, (PSRWLOCK)v2 + 2, 0xFFFFFFFF, 0) )
          goto LABEL_39;
        *((_DWORD *)v2 + 18) = GetCurrentThreadId();
        ++*((_DWORD *)v2 + 19);
      }
    }
    v13 = (*((_DWORD *)v2 + 19))-- == 1;
    if ( v13 )
    {
      *((_DWORD *)v2 + 18) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)v2 + 2);
    }
    v2 = (char *)this + 152;
    v16 = (unsigned __int64)this + 152;
    if ( (unsigned int)mtx_do_lock((char *)this + 152) )
      goto LABEL_40;
  }
  v13 = (*((_DWORD *)v2 + 19))-- == 1;
  if ( v13 )
  {
    *((_DWORD *)v2 + 18) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)v2 + 2);
  }
}

```

## disassembly

```asm
0x180051e04  mov     [rsp-28h+arg_8], rbx
0x180051e09  mov     [rsp-28h+arg_10], rsi
0x180051e0e  push    rbp
0x180051e0f  push    rdi
0x180051e10  push    r12
0x180051e12  push    r14
0x180051e14  push    r15
0x180051e16  mov     rbp, rsp
0x180051e19  sub     rsp, 50h
0x180051e1d  mov     rsi, rcx
0x180051e20  lea     rcx, [rbp+var_28]
0x180051e24  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180051e29  xorps   xmm0, xmm0
0x180051e2c  movups  [rbp+var_20], xmm0
0x180051e30  lea     r14, [rsi+98h]
0x180051e37  mov     rdi, r14
0x180051e3a  mov     qword ptr [rbp+var_20], r14
0x180051e3e  mov     byte ptr [rbp+var_20+8], 0
0x180051e42  mov     rcx, r14
0x180051e45  call    mtx_do_lock
0x180051e4a  test    eax, eax
0x180051e4c  jnz     loc_18005209A
0x180051e52  mov     rbx, [rbp+var_28]
0x180051e56  cmp     dword ptr [r14+4Ch], 7FFFFFFFh
0x180051e5e  jz      loc_1800520A5
0x180051e64  mov     byte ptr [rbp+var_20+8], 1
0x180051e68  cmp     byte ptr [rsi+140h], 0
0x180051e6f  jz      loc_180052064
0x180051e75  cmp     qword ptr [rsi+48h], 0
0x180051e7a  jnz     short loc_180051ECC
0x180051e7c  cmp     byte ptr [rsi+140h], 0
0x180051e83  jz      loc_18005202A
0x180051e89  cmp     qword ptr [rsi+48h], 0
0x180051e8e  jnz     loc_18005202A
0x180051e94  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x180051e9b  dec     dword ptr [rdi+4Ch]
0x180051e9e  lea     rdx, [rdi+10h]; SRWLock
0x180051ea2  lea     rcx, [rsi+0F0h]; ConditionVariable
0x180051ea9  xor     r9d, r9d; Flags
0x180051eac  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180051eb0  call    cs:__imp_SleepConditionVariableSRW
0x180051eb6  test    eax, eax
0x180051eb8  jz      loc_180052094
0x180051ebe  call    cs:__imp_GetCurrentThreadId
0x180051ec4  mov     [rdi+48h], eax
0x180051ec7  inc     dword ptr [rdi+4Ch]
0x180051eca  jmp     short loc_180051E7C
0x180051ecc  mov     eax, [rsi+58h]
0x180051ecf  cmp     [rsi+20h], rax
0x180051ed3  jb      short loc_180051F27
0x180051ed5  cmp     byte ptr [rsi+140h], 0
0x180051edc  jz      loc_18005202A
0x180051ee2  mov     eax, [rsi+58h]
0x180051ee5  cmp     [rsi+20h], rax
0x180051ee9  jb      loc_18005202A
0x180051eef  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x180051ef6  dec     dword ptr [rdi+4Ch]
0x180051ef9  lea     rdx, [rdi+10h]; SRWLock
0x180051efd  lea     rcx, [rsi+0F0h]; ConditionVariable
0x180051f04  xor     r9d, r9d; Flags
0x180051f07  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180051f0b  call    cs:__imp_SleepConditionVariableSRW
0x180051f11  test    eax, eax
0x180051f13  jz      loc_180052094
0x180051f19  call    cs:__imp_GetCurrentThreadId
0x180051f1f  mov     [rdi+48h], eax
0x180051f22  inc     dword ptr [rdi+4Ch]
0x180051f25  jmp     short loc_180051ED5
0x180051f27  lea     rcx, [rbp+var_10]
0x180051f2b  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180051f30  cmp     rbx, [rax]
0x180051f33  jz      short loc_180051F37
0x180051f35  jge     short loc_180051F5C
0x180051f37  xor     r15d, r15d
0x180051f3a  jmp     loc_180051FD2
0x180051f3f  lea     r8, [rbp+var_28]
0x180051f43  lea     rdx, [rbp+var_20]
0x180051f47  lea     rcx, [rsi+0E8h]
0x180051f4e  call    ??$wait_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@condition_variable@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vmutex@std@@@1@AEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z; std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::unique_lock<std::mutex> &,std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)
0x180051f53  cmp     eax, 1
0x180051f56  jz      loc_18005202A
0x180051f5c  cmp     byte ptr [rsi+140h], 0
0x180051f63  jnz     short loc_180051F3F
0x180051f65  jmp     loc_18005202A
0x180051f6a  mov     r11d, [rsi+54h]
0x180051f6e  cmp     r15d, r11d
0x180051f71  jnb     short loc_180051FDB
0x180051f73  mov     eax, [rsi+58h]
0x180051f76  cmp     [rsi+20h], rax
0x180051f7a  jnb     short loc_180051FDB
0x180051f7c  mov     r10, [rsi+40h]
0x180051f80  mov     rdx, r10
0x180051f83  shr     rdx, 1
0x180051f86  mov     rax, [rsi+38h]
0x180051f8a  dec     rax
0x180051f8d  and     rdx, rax
0x180051f90  mov     rax, [rsi+30h]
0x180051f94  mov     rcx, r10
0x180051f97  and     ecx, 1
0x180051f9a  mov     rax, [rax+rdx*8]
0x180051f9e  mov     rcx, [rax+rcx*8]; this
0x180051fa2  mov     [rbp+var_30], rcx
0x180051fa6  lea     rax, [r8-1]
0x180051faa  mov     [rsi+48h], rax
0x180051fae  test    rax, rax
0x180051fb1  jz      short loc_180051FB7
0x180051fb3  lea     rax, [r10+1]
0x180051fb7  mov     [rsi+40h], rax
0x180051fbb  mov     edx, r11d; unsigned int
0x180051fbe  call    ?SendNextRequestCallback@CHttpRangesDownload@@QEAAII@Z; CHttpRangesDownload::SendNextRequestCallback(uint)
0x180051fc3  add     r15d, eax
0x180051fc6  lea     rdx, [rbp+var_30]
0x180051fca  mov     rcx, rsi
0x180051fcd  call    ?push_back@?$deque@PEAVCHttpRangesDownload@@V?$allocator@PEAVCHttpRangesDownload@@@std@@@std@@QEAAXAEBQEAVCHttpRangesDownload@@@Z; std::deque<CHttpRangesDownload *>::push_back(CHttpRangesDownload * const &)
0x180051fd2  mov     r8, [rsi+48h]
0x180051fd6  test    r8, r8
0x180051fd9  jnz     short loc_180051F6A
0x180051fdb  mov     r12d, r15d
0x180051fde  lea     rcx, [rsi+60h]; this
0x180051fe2  mov     edx, r15d; unsigned __int64
0x180051fe5  call    ?AddDataCount@CRateTracker@@QEAAX_K@Z; CRateTracker::AddDataCount(unsigned __int64)
0x180051fea  cmp     dword ptr [rsi+50h], 0
0x180051fee  jz      short loc_18005202A
0x180051ff0  test    r15d, r15d
0x180051ff3  jz      short loc_18005202A
0x180051ff5  imul    rax, r12, 3E8h
0x180051ffc  mov     ecx, [rsi+50h]
0x180051fff  xor     edx, edx
0x180052001  div     rcx
0x180052004  mov     rbx, rax
0x180052007  lea     rcx, [rbp+var_8]
0x18005200b  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180052010  mov     edx, 0Ah
0x180052015  cmp     rbx, rdx
0x180052018  cmovb   rbx, rdx
0x18005201c  imul    rbx, 0F4240h
0x180052023  add     rbx, [rax]
0x180052026  mov     [rbp+var_28], rbx
0x18005202a  sub     dword ptr [rdi+4Ch], 1
0x18005202e  jnz     short loc_180052041
0x180052030  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x180052037  lea     rcx, [rdi+10h]; SRWLock
0x18005203b  call    cs:__imp_ReleaseSRWLockExclusive
0x180052041  xorps   xmm0, xmm0
0x180052044  movups  [rbp+var_20], xmm0
0x180052048  mov     rdi, r14
0x18005204b  mov     qword ptr [rbp+var_20], r14
0x18005204f  mov     byte ptr [rbp+var_20+8], 0
0x180052053  mov     rcx, r14
0x180052056  call    mtx_do_lock
0x18005205b  test    eax, eax
0x18005205d  jnz     short loc_18005209A
0x18005205f  jmp     loc_180051E56
0x180052064  sub     dword ptr [rdi+4Ch], 1
0x180052068  jnz     short loc_18005207B
0x18005206a  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x180052071  lea     rcx, [rdi+10h]; SRWLock
0x180052075  call    cs:__imp_ReleaseSRWLockExclusive
0x18005207b  lea     r11, [rsp+50h+var_s0]
0x180052080  mov     rbx, [r11+38h]
0x180052084  mov     rsi, [r11+40h]
0x180052088  mov     rsp, r11
0x18005208b  pop     r15
0x18005208d  pop     r14
0x18005208f  pop     r12
0x180052091  pop     rdi
0x180052092  pop     rbp
0x180052093  retn
0x180052094  call    abort
0x18005209a  mov     ecx, 5; int
0x18005209f  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800520a5  mov     dword ptr [r14+4Ch], 7FFFFFFEh
0x1800520ad  mov     ecx, 6; int
0x1800520b2  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
