# ComputeService::Client::NotificationCallbacks::StartCallback(ComputeService::Client::NotificationCallbacks::NotificationContext *)

- ea: `0x18002df6c`
- end: `0x18002dfe3`
- name: `?StartCallback@NotificationCallbacks@Client@ComputeService@@AEAA_NPEAUNotificationContext@123@@Z`
- size: `119`
- prototype: `bool __fastcall(ComputeService::Client::NotificationCallbacks *__hidden this, struct ComputeService::Client::NotificationCallbacks::NotificationContext *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d768`
- `0x18002e0c0`

## callees

- `0x18002df6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002dfca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002dfca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002df85`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002df85`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002dfa4`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002dfa4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002dfb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002dfb6`

## pseudocode

```c
char __fastcall ComputeService::Client::NotificationCallbacks::StartCallback(
        ComputeService::Client::NotificationCallbacks *this,
        struct ComputeService::Client::NotificationCallbacks::NotificationContext *a2)
{
  RTL_SRWLOCK *v2; // rbx
  char v4; // si

  v2 = (RTL_SRWLOCK *)((char *)a2 + 72);
  AcquireSRWLockExclusive((PSRWLOCK)a2 + 9);
  v4 = 0;
  while ( *((_DWORD *)a2 + 16) )
  {
    if ( *((_BYTE *)a2 + 68) )
      goto LABEL_7;
    SleepConditionVariableSRW((PCONDITION_VARIABLE)a2 + 10, v2, 0xFFFFFFFF, 0);
  }
  if ( !*((_BYTE *)a2 + 68) )
  {
    *((_DWORD *)a2 + 16) = GetCurrentThreadId();
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
0x18002df6c  mov     [rsp+arg_0], rbx
0x18002df71  mov     [rsp+arg_10], rsi
0x18002df76  push    rdi
0x18002df77  sub     rsp, 20h
0x18002df7b  lea     rbx, [rdx+48h]
0x18002df7f  mov     rdi, rdx
0x18002df82  mov     rcx, rbx; SRWLock
0x18002df85  call    cs:__imp_AcquireSRWLockExclusive
0x18002df8b  xor     sil, sil
0x18002df8e  jmp     short loc_18002DFAA
0x18002df90  cmp     [rdi+44h], sil
0x18002df94  jnz     short loc_18002DFC2
0x18002df96  lea     rcx, [rdi+50h]; ConditionVariable
0x18002df9a  xor     r9d, r9d; Flags
0x18002df9d  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18002dfa1  mov     rdx, rbx; SRWLock
0x18002dfa4  call    cs:__imp_SleepConditionVariableSRW
0x18002dfaa  cmp     dword ptr [rdi+40h], 0
0x18002dfae  jnz     short loc_18002DF90
0x18002dfb0  cmp     [rdi+44h], sil
0x18002dfb4  jnz     short loc_18002DFC2
0x18002dfb6  call    cs:__imp_GetCurrentThreadId
0x18002dfbc  mov     [rdi+40h], eax
0x18002dfbf  mov     sil, 1
0x18002dfc2  test    rbx, rbx
0x18002dfc5  jz      short loc_18002DFD0
0x18002dfc7  mov     rcx, rbx; SRWLock
0x18002dfca  call    cs:__imp_ReleaseSRWLockExclusive
0x18002dfd0  mov     rbx, [rsp+28h+arg_0]
0x18002dfd5  mov     al, sil
0x18002dfd8  mov     rsi, [rsp+28h+arg_10]
0x18002dfdd  add     rsp, 20h
0x18002dfe1  pop     rdi
0x18002dfe2  retn
```
