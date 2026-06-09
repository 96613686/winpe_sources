# _Hns::Client::Notifications::NotificationCallbacks::RemoveNotificationContext_::_1_::dtor$0

- ea: `0x18000e279`
- end: `0x18000e285`
- name: `_Hns::Client::Notifications::NotificationCallbacks::RemoveNotificationContext_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004210`

## pseudocode

```c
void __fastcall Hns::Client::Notifications::NotificationCallbacks::RemoveNotificationContext_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>::~unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>((Hns::Client::Notifications::NotificationCallbacks::NotificationContext **)(a2 + 144));
}

```

## disassembly

```asm
0x18000e279  lea     rcx, [rdx+90h]
0x18000e280  jmp     ??1?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@QEAA@XZ; std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>::~unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>(void)
```
