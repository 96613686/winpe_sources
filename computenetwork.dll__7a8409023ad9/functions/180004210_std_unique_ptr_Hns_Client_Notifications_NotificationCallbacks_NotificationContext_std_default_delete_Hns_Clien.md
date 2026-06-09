# std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>::~unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext,std::default_delete<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>(void)

- ea: `0x180004210`
- end: `0x180004239`
- name: `??1?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000e21f`
- `0x18000e279`

## callees

- `0x1800019d0`
- `0x180004210`
- `0x180004240`

## pseudocode

```c
void __fastcall std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>::~unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>(
        Hns::Client::Notifications::NotificationCallbacks::NotificationContext **a1)
{
  Hns::Client::Notifications::NotificationCallbacks::NotificationContext *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    Hns::Client::Notifications::NotificationCallbacks::NotificationContext::~NotificationContext(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x180004210  push    rbx
0x180004212  sub     rsp, 20h
0x180004216  mov     rbx, [rcx]
0x180004219  test    rbx, rbx
0x18000421c  jz      short loc_180004233
0x18000421e  mov     rcx, rbx; this
0x180004221  call    ??1NotificationContext@NotificationCallbacks@Notifications@Client@Hns@@QEAA@XZ; Hns::Client::Notifications::NotificationCallbacks::NotificationContext::~NotificationContext(void)
0x180004226  mov     edx, 60h ; '`'; unsigned __int64
0x18000422b  mov     rcx, rbx; void *
0x18000422e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004233  add     rsp, 20h
0x180004237  pop     rbx
0x180004238  retn
```
