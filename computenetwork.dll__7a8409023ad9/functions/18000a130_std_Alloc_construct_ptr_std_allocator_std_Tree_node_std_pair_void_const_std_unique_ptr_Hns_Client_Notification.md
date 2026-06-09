# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>,void *>>>(void)

- ea: `0x18000a130`
- end: `0x18000a14c`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000e267`

## callees

- `0x1800019d0`
- `0x18000a130`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000a130  sub     rsp, 28h
0x18000a134  mov     rcx, [rcx+8]; void *
0x18000a138  test    rcx, rcx
0x18000a13b  jz      short loc_18000A147
0x18000a13d  mov     edx, 30h ; '0'; unsigned __int64
0x18000a142  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a147  add     rsp, 28h
0x18000a14b  retn
```
