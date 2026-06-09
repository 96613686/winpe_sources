# _dynamic_initializer_for__g_GuestNetworkServiceCallbacks__

- ea: `0x180001010`
- end: `0x180001045`
- name: `_dynamic_initializer_for__g_GuestNetworkServiceCallbacks__`
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
int dynamic_initializer_for__g_GuestNetworkServiceCallbacks__()
{
  Hns::Client::Notifications::NotificationCallbacks::NotificationCallbacks(
    (Hns::Client::Notifications::NotificationCallbacks *)qword_1800184D0,
    HnsRpc_RegisterGuestNetworkServiceNotifications,
    HnsRpc_UnregisterGuestNetworkServiceNotifications,
    HnsRpc_QueryGuestNetworkServiceNotification);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_GuestNetworkServiceCallbacks__);
}

```

## disassembly

```asm
0x180001010  sub     rsp, 28h
0x180001014  lea     r9, HnsRpc_QueryGuestNetworkServiceNotification; int (*)(void *, unsigned int *, int *, unsigned __int16 **)
0x18000101b  lea     r8, HnsRpc_UnregisterGuestNetworkServiceNotifications; int (*)(void *)
0x180001022  lea     rdx, HnsRpc_RegisterGuestNetworkServiceNotifications; int (*)(void *, void **, void **)
0x180001029  lea     rcx, qword_1800184D0; this
0x180001030  call    ??0NotificationCallbacks@Notifications@Client@Hns@@QEAA@P6AJPEAXPEAPEAX1@ZP6AJ0@ZP6AJ0PEAKPEAJPEAPEAG@Z@Z; Hns::Client::Notifications::NotificationCallbacks::NotificationCallbacks(long (*)(void *,void * *,void * *),long (*)(void *),long (*)(void *,ulong *,long *,ushort * *))
0x180001035  lea     rcx, _dynamic_atexit_destructor_for__g_GuestNetworkServiceCallbacks__
0x18000103c  add     rsp, 28h
0x180001040  jmp     atexit
```
