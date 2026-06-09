# PsmpShutdownPolicy

- ea: `0x180021fac`
- end: `0x1800220ae`
- name: `PsmpShutdownPolicy`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f0a0`

## callees

- `0x180021fac`
- `0x180024968`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180022028`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18002203a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180022028`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18002203a`
- `ntdll!TpReleaseWait` at `0x180021fce`
- `ntdll!TpReleaseWait` at `0x180021fce`
- `ntdll!NtClose` at `0x180021fe0`
- `ntdll!NtClose` at `0x180021ff2`
- `ntdll!NtClose` at `0x180021fe0`
- `ntdll!NtClose` at `0x180021ff2`
- `ntdll!TpReleaseTimer` at `0x180022016`
- `ntdll!TpReleaseTimer` at `0x180022016`
- `ntdll!TpWaitForTimer` at `0x180022009`
- `ntdll!TpWaitForTimer` at `0x180022009`
- `ntdll!TpWaitForWait` at `0x180021fc1`
- `ntdll!TpWaitForWait` at `0x180021fc1`
- `ntdll!RtlRunOnceBeginInitialize` at `0x180022090`
- `ntdll!RtlRunOnceBeginInitialize` at `0x180022090`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18002204c`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18002205e`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180022070`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18002204c`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18002205e`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180022070`
- `NduProv!__imp_NduCloseHandle` at `0x18002209f`
- `NduProv!__imp_NduCloseHandle` at `0x18002209f`

## pseudocode

```c
__int64 PsmpShutdownPolicy()
{
  __int64 v1; // [rsp+30h] [rbp+8h] BYREF

  if ( qword_18003FE30 )
  {
    TpWaitForWait(qword_18003FE30, 1);
    TpReleaseWait(qword_18003FE30);
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( Event )
    NtClose(Event);
  if ( qword_18003FE28 )
  {
    TpWaitForTimer(qword_18003FE28, 1);
    TpReleaseTimer(qword_18003FE28);
  }
  if ( qword_18003FE88 )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  if ( qword_18003FE10 )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  if ( RegistrationHandle )
    PowerSettingUnregisterNotification(RegistrationHandle);
  if ( qword_18003FE40 )
    PowerSettingUnregisterNotification(qword_18003FE40);
  if ( qword_18003FE48 )
    PowerSettingUnregisterNotification(qword_18003FE48);
  v1 = 0;
  if ( (int)RtlRunOnceBeginInitialize(&PsmpNetInit, 1, &v1) >= 0 )
    NduCloseHandle(v1);
  return PsmpNotificationQueueShutdown();
}

```

## disassembly

```asm
0x180021fac  sub     rsp, 28h
0x180021fb0  mov     rcx, cs:qword_18003FE30
0x180021fb7  test    rcx, rcx
0x180021fba  jz      short loc_180021FD4
0x180021fbc  mov     edx, 1
0x180021fc1  call    cs:__imp_TpWaitForWait
0x180021fc7  mov     rcx, cs:qword_18003FE30
0x180021fce  call    cs:__imp_TpReleaseWait
0x180021fd4  mov     rcx, cs:KeyHandle; Handle
0x180021fdb  test    rcx, rcx
0x180021fde  jz      short loc_180021FE6
0x180021fe0  call    cs:__imp_NtClose
0x180021fe6  mov     rcx, cs:Event; Handle
0x180021fed  test    rcx, rcx
0x180021ff0  jz      short loc_180021FF8
0x180021ff2  call    cs:__imp_NtClose
0x180021ff8  mov     rcx, cs:qword_18003FE28
0x180021fff  test    rcx, rcx
0x180022002  jz      short loc_18002201C
0x180022004  mov     edx, 1
0x180022009  call    cs:__imp_TpWaitForTimer
0x18002200f  mov     rcx, cs:qword_18003FE28
0x180022016  call    cs:__imp_TpReleaseTimer
0x18002201c  mov     rcx, cs:qword_18003FE88
0x180022023  test    rcx, rcx
0x180022026  jz      short loc_18002202E
0x180022028  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18002202e  mov     rcx, cs:qword_18003FE10
0x180022035  test    rcx, rcx
0x180022038  jz      short loc_180022040
0x18002203a  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180022040  mov     rcx, cs:RegistrationHandle; RegistrationHandle
0x180022047  test    rcx, rcx
0x18002204a  jz      short loc_180022052
0x18002204c  call    cs:__imp_PowerSettingUnregisterNotification
0x180022052  mov     rcx, cs:qword_18003FE40; RegistrationHandle
0x180022059  test    rcx, rcx
0x18002205c  jz      short loc_180022064
0x18002205e  call    cs:__imp_PowerSettingUnregisterNotification
0x180022064  mov     rcx, cs:qword_18003FE48; RegistrationHandle
0x18002206b  test    rcx, rcx
0x18002206e  jz      short loc_180022076
0x180022070  call    cs:__imp_PowerSettingUnregisterNotification
0x180022076  lea     r8, [rsp+28h+arg_0]
0x18002207b  mov     [rsp+28h+arg_0], 0
0x180022084  mov     edx, 1
0x180022089  lea     rcx, PsmpNetInit
0x180022090  call    cs:__imp_RtlRunOnceBeginInitialize
0x180022096  test    eax, eax
0x180022098  js      short loc_1800220A5
0x18002209a  mov     rcx, [rsp+28h+arg_0]
0x18002209f  call    cs:__imp_NduCloseHandle
0x1800220a5  add     rsp, 28h
0x1800220a9  jmp     PsmpNotificationQueueShutdown
```
