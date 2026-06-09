# Hns::Client::Notifications::NotificationCallbacks::CompleteCallback(Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)

- ea: `0x18000a2f8`
- end: `0x18000a351`
- name: `?CompleteCallback@NotificationCallbacks@Notifications@Client@Hns@@AEAA_NPEAUNotificationContext@1234@@Z`
- size: `89`
- prototype: `bool __fastcall(Hns::Client::Notifications::NotificationCallbacks *__hidden this, struct Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a40c`
- `0x18000ade0`

## callees

- `0x18000a2f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a311`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a311`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a32e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a32e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000a338`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000a338`

## pseudocode

```c
bool __fastcall Hns::Client::Notifications::NotificationCallbacks::CompleteCallback(
        Hns::Client::Notifications::NotificationCallbacks *this,
        struct Hns::Client::Notifications::NotificationCallbacks::NotificationContext *a2)
{
  RTL_SRWLOCK *v2; // rdi
  bool v4; // zf
  bool v5; // si

  v2 = (RTL_SRWLOCK *)((char *)a2 + 64);
  AcquireSRWLockExclusive((PSRWLOCK)a2 + 8);
  v4 = *((_BYTE *)a2 + 60) == 0;
  *((_DWORD *)a2 + 14) = 0;
  v5 = v4;
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  WakeAllConditionVariable((PCONDITION_VARIABLE)a2 + 9);
  return v5;
}

```

## disassembly

```asm
0x18000a2f8  mov     [rsp+arg_0], rbx
0x18000a2fd  mov     [rsp+arg_8], rsi
0x18000a302  push    rdi
0x18000a303  sub     rsp, 20h
0x18000a307  lea     rdi, [rdx+40h]
0x18000a30b  mov     rbx, rdx
0x18000a30e  mov     rcx, rdi; SRWLock
0x18000a311  call    cs:__imp_AcquireSRWLockExclusive
0x18000a317  cmp     byte ptr [rbx+3Ch], 0
0x18000a31b  mov     dword ptr [rbx+38h], 0
0x18000a322  setz    sil
0x18000a326  test    rdi, rdi
0x18000a329  jz      short loc_18000A334
0x18000a32b  mov     rcx, rdi; SRWLock
0x18000a32e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a334  lea     rcx, [rbx+48h]; ConditionVariable
0x18000a338  call    cs:__imp_WakeAllConditionVariable
0x18000a33e  mov     rbx, [rsp+28h+arg_0]
0x18000a343  mov     al, sil
0x18000a346  mov     rsi, [rsp+28h+arg_8]
0x18000a34b  add     rsp, 20h
0x18000a34f  pop     rdi
0x18000a350  retn
```
