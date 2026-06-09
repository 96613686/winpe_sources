# HcsClient::OperationTracker::Teardown(void)

- ea: `0x18004c8a8`
- end: `0x18004c983`
- name: `?Teardown@OperationTracker@HcsClient@@QEAAXXZ`
- size: `219`
- prototype: `void __fastcall(HcsClient::OperationTracker *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002c4b4`
- `0x180035da4`

## callees

- `0x18004c8a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c8e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c93d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c974`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c8e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c93d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c974`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c8b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c8ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c94b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c8b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c8ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c94b`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004c8d4`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004c8d4`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18004c920`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18004c965`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18004c920`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18004c965`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c8c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c8f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c8c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c8f4`

## pseudocode

```c
void __fastcall HcsClient::OperationTracker::Teardown(HcsClient::OperationTracker *this)
{
  __int64 v1; // rdi
  char v2; // si
  DWORD CurrentThreadId; // eax

  v1 = *((_QWORD *)this + 13);
  AcquireSRWLockExclusive((PSRWLOCK)v1);
  *(_BYTE *)(v1 + 24) = 1;
  if ( *(_DWORD *)(v1 + 16) == GetCurrentThreadId() )
  {
    v2 = 1;
    WakeAllConditionVariable((PCONDITION_VARIABLE)(v1 + 8));
  }
  else
  {
    v2 = 0;
  }
  ReleaseSRWLockExclusive((PSRWLOCK)v1);
  AcquireSRWLockExclusive((PSRWLOCK)(v1 + 40));
  CurrentThreadId = GetCurrentThreadId();
  if ( !*(_DWORD *)(v1 + 56) || *(_DWORD *)(v1 + 56) == 3 || *(_DWORD *)(v1 + 60) == CurrentThreadId )
  {
    *(_DWORD *)(v1 + 56) = 3;
  }
  else
  {
    *(_DWORD *)(v1 + 56) = 2;
    do
      SleepConditionVariableSRW((PCONDITION_VARIABLE)(v1 + 48), (PSRWLOCK)(v1 + 40), 0xFFFFFFFF, 0);
    while ( *(_DWORD *)(v1 + 56) != 3 );
  }
  if ( v1 != -40 )
    ReleaseSRWLockExclusive((PSRWLOCK)(v1 + 40));
  if ( !v2 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)v1);
    *(_BYTE *)(v1 + 24) = 1;
    while ( *(_DWORD *)(v1 + 16) )
      SleepConditionVariableSRW((PCONDITION_VARIABLE)(v1 + 8), (PSRWLOCK)v1, 0xFFFFFFFF, 0);
    ReleaseSRWLockExclusive((PSRWLOCK)v1);
  }
}

```

## disassembly

```asm
0x18004c8a8  push    rbx
0x18004c8aa  push    rbp
0x18004c8ab  push    rsi
0x18004c8ac  push    rdi
0x18004c8ad  sub     rsp, 28h
0x18004c8b1  mov     rdi, [rcx+68h]
0x18004c8b5  mov     rcx, rdi; SRWLock
0x18004c8b8  call    cs:__imp_AcquireSRWLockExclusive
0x18004c8be  mov     byte ptr [rdi+18h], 1
0x18004c8c2  call    cs:__imp_GetCurrentThreadId
0x18004c8c8  cmp     [rdi+10h], eax
0x18004c8cb  jnz     short loc_18004C8DC
0x18004c8cd  lea     rcx, [rdi+8]; ConditionVariable
0x18004c8d1  mov     sil, 1
0x18004c8d4  call    cs:__imp_WakeAllConditionVariable
0x18004c8da  jmp     short loc_18004C8DE
0x18004c8dc  xor     esi, esi
0x18004c8de  mov     rcx, rdi; SRWLock
0x18004c8e1  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c8e7  lea     rbx, [rdi+28h]
0x18004c8eb  mov     rcx, rbx; SRWLock
0x18004c8ee  call    cs:__imp_AcquireSRWLockExclusive
0x18004c8f4  call    cs:__imp_GetCurrentThreadId
0x18004c8fa  cmp     dword ptr [rdi+38h], 0
0x18004c8fe  jz      short loc_18004C92E
0x18004c900  cmp     dword ptr [rdi+38h], 3
0x18004c904  jz      short loc_18004C92E
0x18004c906  cmp     [rdi+3Ch], eax
0x18004c909  jz      short loc_18004C92E
0x18004c90b  mov     dword ptr [rdi+38h], 2
0x18004c912  xor     r9d, r9d; Flags
0x18004c915  lea     rcx, [rdi+30h]; ConditionVariable
0x18004c919  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18004c91d  mov     rdx, rbx; SRWLock
0x18004c920  call    cs:__imp_SleepConditionVariableSRW
0x18004c926  cmp     dword ptr [rdi+38h], 3
0x18004c92a  jnz     short loc_18004C912
0x18004c92c  jmp     short loc_18004C935
0x18004c92e  mov     dword ptr [rdi+38h], 3
0x18004c935  test    rbx, rbx
0x18004c938  jz      short loc_18004C943
0x18004c93a  mov     rcx, rbx; SRWLock
0x18004c93d  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c943  test    sil, sil
0x18004c946  jnz     short loc_18004C97A
0x18004c948  mov     rcx, rdi; SRWLock
0x18004c94b  call    cs:__imp_AcquireSRWLockExclusive
0x18004c951  mov     byte ptr [rdi+18h], 1
0x18004c955  jmp     short loc_18004C96B
0x18004c957  xor     r9d, r9d; Flags
0x18004c95a  lea     rcx, [rdi+8]; ConditionVariable
0x18004c95e  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18004c962  mov     rdx, rdi; SRWLock
0x18004c965  call    cs:__imp_SleepConditionVariableSRW
0x18004c96b  cmp     dword ptr [rdi+10h], 0
0x18004c96f  jnz     short loc_18004C957
0x18004c971  mov     rcx, rdi; SRWLock
0x18004c974  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c97a  add     rsp, 28h
0x18004c97e  pop     rdi
0x18004c97f  pop     rsi
0x18004c980  pop     rbp
0x18004c981  pop     rbx
0x18004c982  retn
```
