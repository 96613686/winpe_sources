# Hns::Client::Notifications::NotificationCallbacks::StartCallback(Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)

- ea: `0x18000ac88`
- end: `0x18000acff`
- name: `?StartCallback@NotificationCallbacks@Notifications@Client@Hns@@AEAA_NPEAUNotificationContext@1234@@Z`
- size: `119`
- prototype: `bool __fastcall(Hns::Client::Notifications::NotificationCallbacks *__hidden this, struct Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a40c`
- `0x18000ade0`

## callees

- `0x18000ac88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aca1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aca1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ace6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ace6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000acd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000acd2`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000acc0`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000acc0`

## pseudocode

```c
char __fastcall Hns::Client::Notifications::NotificationCallbacks::StartCallback(
        Hns::Client::Notifications::NotificationCallbacks *this,
        struct Hns::Client::Notifications::NotificationCallbacks::NotificationContext *a2)
{
  RTL_SRWLOCK *v2; // rbx
  char v4; // si

  v2 = (RTL_SRWLOCK *)((char *)a2 + 64);
  AcquireSRWLockExclusive((PSRWLOCK)a2 + 8);
  v4 = 0;
  while ( *((_DWORD *)a2 + 14) )
  {
    if ( *((_BYTE *)a2 + 60) )
      goto LABEL_7;
    SleepConditionVariableSRW((PCONDITION_VARIABLE)a2 + 9, v2, 0xFFFFFFFF, 0);
  }
  if ( !*((_BYTE *)a2 + 60) )
  {
    *((_DWORD *)a2 + 14) = GetCurrentThreadId();
    v4 = 1;
  }
LABEL_7:
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  return v4;
}

```

## disassembly

```asm
0x18000ac88  mov     [rsp+arg_0], rbx
0x18000ac8d  mov     [rsp+arg_8], rsi
0x18000ac92  push    rdi
0x18000ac93  sub     rsp, 20h
0x18000ac97  lea     rbx, [rdx+40h]
0x18000ac9b  mov     rdi, rdx
0x18000ac9e  mov     rcx, rbx; SRWLock
0x18000aca1  call    cs:__imp_AcquireSRWLockExclusive
0x18000aca7  xor     sil, sil
0x18000acaa  jmp     short loc_18000ACC6
0x18000acac  cmp     [rdi+3Ch], sil
0x18000acb0  jnz     short loc_18000ACDE
0x18000acb2  lea     rcx, [rdi+48h]; ConditionVariable
0x18000acb6  xor     r9d, r9d; Flags
0x18000acb9  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18000acbd  mov     rdx, rbx; SRWLock
0x18000acc0  call    cs:__imp_SleepConditionVariableSRW
0x18000acc6  cmp     dword ptr [rdi+38h], 0
0x18000acca  jnz     short loc_18000ACAC
0x18000accc  cmp     [rdi+3Ch], sil
0x18000acd0  jnz     short loc_18000ACDE
0x18000acd2  call    cs:__imp_GetCurrentThreadId
0x18000acd8  mov     [rdi+38h], eax
0x18000acdb  mov     sil, 1
0x18000acde  test    rbx, rbx
0x18000ace1  jz      short loc_18000ACEC
0x18000ace3  mov     rcx, rbx; SRWLock
0x18000ace6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000acec  mov     rbx, [rsp+28h+arg_0]
0x18000acf1  mov     al, sil
0x18000acf4  mov     rsi, [rsp+28h+arg_8]
0x18000acf9  add     rsp, 20h
0x18000acfd  pop     rdi
0x18000acfe  retn
```
