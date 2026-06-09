# _dynamic_atexit_destructor_for__g_GuestNetworkServiceCallbacks__

- ea: `0x18000e410`
- end: `0x18000e41c`
- name: `_dynamic_atexit_destructor_for__g_GuestNetworkServiceCallbacks__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004108`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_GuestNetworkServiceCallbacks__()
{
  std::_Tree<std::_Tmap_traits<void *,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,0>>::~_Tree<std::_Tmap_traits<void *,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,0>>((void **)qword_1800184E8);
}

```

## disassembly

```asm
0x18000e410  lea     rcx, qword_1800184E8
0x18000e417  jmp     ??1?$_Tree@V?$_Tmap_traits@PEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@U?$less@PEAX@2@V?$allocator@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<void *,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,0>>::~_Tree<std::_Tmap_traits<void *,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,0>>(void)
```
