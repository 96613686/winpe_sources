# _dynamic_initializer_for__g_ServiceCallbacks__

- ea: `0x180001090`
- end: `0x1800010c5`
- name: `_dynamic_initializer_for__g_ServiceCallbacks__`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800019b0`
- `0x18000a010`

## pseudocode

```c
int dynamic_initializer_for__g_ServiceCallbacks__()
{
  Hns::Client::Notifications::NotificationCallbacks::NotificationCallbacks(
    (Hns::Client::Notifications::NotificationCallbacks *)qword_180018470,
    HnsRpc_RegisterServiceNotifications,
    HnsRpc_UnregisterServiceNotifications,
    HnsRpc_QueryServiceNotification);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_ServiceCallbacks__);
}

```

## disassembly

```asm
0x180001090  sub     rsp, 28h
0x180001094  lea     r9, HnsRpc_QueryServiceNotification; int (*)(void *, unsigned int *, int *, unsigned __int16 **)
0x18000109b  lea     r8, HnsRpc_UnregisterServiceNotifications; int (*)(void *)
0x1800010a2  lea     rdx, HnsRpc_RegisterServiceNotifications; int (*)(void *, void **, void **)
0x1800010a9  lea     rcx, qword_180018470; this
0x1800010b0  call    ??0NotificationCallbacks@Notifications@Client@Hns@@QEAA@P6AJPEAXPEAPEAX1@ZP6AJ0@ZP6AJ0PEAKPEAJPEAPEAG@Z@Z; Hns::Client::Notifications::NotificationCallbacks::NotificationCallbacks(long (*)(void *,void * *,void * *),long (*)(void *),long (*)(void *,ulong *,long *,ushort * *))
0x1800010b5  lea     rcx, _dynamic_atexit_destructor_for__g_ServiceCallbacks__
0x1800010bc  add     rsp, 28h
0x1800010c0  jmp     atexit
```
