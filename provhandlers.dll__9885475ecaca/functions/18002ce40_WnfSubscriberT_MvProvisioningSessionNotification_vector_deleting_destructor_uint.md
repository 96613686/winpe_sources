# WnfSubscriberT<MvProvisioningSessionNotification>::`vector deleting destructor'(uint)

- ea: `0x18002ce40`
- end: `0x18002cebc`
- name: `??_E?$WnfSubscriberT@UMvProvisioningSessionNotification@@@@UEAAPEAXI@Z`
- size: `124`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18002cb64`
- `0x18002ce40`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002cea8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002cea8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce99`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18002ce62`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18002ce62`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall WnfSubscriberT<MvProvisioningSessionNotification>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  void *v4; // rcx
  void *v5; // rcx

  *a1 = &WnfSubscriberT<MvProvisioningSessionNotification>::`vftable';
  if ( a1[2] )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    a1[2] = 0;
  }
  v4 = (void *)a1[3];
  if ( v4 )
  {
    CloseHandle(v4);
    a1[3] = 0;
  }
  std::_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>,std::less<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,std::allocator<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,0>>::~_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>,std::less<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,std::allocator<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,0>>(a1 + 8);
  v5 = (void *)a1[3];
  if ( v5 )
    CloseHandle(v5);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18002ce40  mov     [rsp+arg_0], rbx
0x18002ce45  push    rdi
0x18002ce46  sub     rsp, 20h
0x18002ce4a  lea     rax, ??_7?$WnfSubscriberT@UMvProvisioningSessionNotification@@@@6B@; const WnfSubscriberT<MvProvisioningSessionNotification>::`vftable'
0x18002ce51  mov     rbx, rcx
0x18002ce54  mov     [rcx], rax
0x18002ce57  mov     edi, edx
0x18002ce59  mov     rcx, [rcx+10h]
0x18002ce5d  test    rcx, rcx
0x18002ce60  jz      short loc_18002CE70
0x18002ce62  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18002ce68  mov     qword ptr [rbx+10h], 0
0x18002ce70  mov     rcx, [rbx+18h]; hObject
0x18002ce74  test    rcx, rcx
0x18002ce77  jz      short loc_18002CE87
0x18002ce79  call    cs:__imp_CloseHandle
0x18002ce7f  mov     qword ptr [rbx+18h], 0
0x18002ce87  lea     rcx, [rbx+40h]
0x18002ce8b  call    ??1?$_Tree@V?$_Tset_traits@V?$shared_ptr@V?$function@$$A6AXAEBUMvProvisioningSessionNotification@@@Z@std@@@std@@U?$less@V?$shared_ptr@V?$function@$$A6AXAEBUMvProvisioningSessionNotification@@@Z@std@@@std@@@2@V?$allocator@V?$shared_ptr@V?$function@$$A6AXAEBUMvProvisioningSessionNotification@@@Z@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>,std::less<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,std::allocator<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,0>>::~_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>,std::less<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,std::allocator<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,0>>(void)
0x18002ce90  mov     rcx, [rbx+18h]; hObject
0x18002ce94  test    rcx, rcx
0x18002ce97  jz      short loc_18002CE9F
0x18002ce99  call    cs:__imp_CloseHandle
0x18002ce9f  test    dil, 1
0x18002cea3  jz      short loc_18002CEAE
0x18002cea5  mov     rcx, rbx
0x18002cea8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002ceae  mov     rax, rbx
0x18002ceb1  mov     rbx, [rsp+28h+arg_0]
0x18002ceb6  add     rsp, 20h
0x18002ceba  pop     rdi
0x18002cebb  retn
```
