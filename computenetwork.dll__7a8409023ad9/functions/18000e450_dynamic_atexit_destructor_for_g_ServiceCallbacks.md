# _dynamic_atexit_destructor_for__g_ServiceCallbacks__

- ea: `0x18000e450`
- end: `0x18000e45c`
- name: `_dynamic_atexit_destructor_for__g_ServiceCallbacks__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004108`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_ServiceCallbacks__()
{
  std::_Tree<std::_Tmap_traits<void *,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,0>>::~_Tree<std::_Tmap_traits<void *,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,0>>((void **)qword_180018488);
}

```

## disassembly

```asm
0x18000e450  lea     rcx, qword_180018488
0x18000e457  jmp     ??1?$_Tree@V?$_Tmap_traits@PEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@U?$less@PEAX@2@V?$allocator@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<void *,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,0>>::~_Tree<std::_Tmap_traits<void *,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>,std::less<void *>,std::allocator<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,0>>(void)
```
