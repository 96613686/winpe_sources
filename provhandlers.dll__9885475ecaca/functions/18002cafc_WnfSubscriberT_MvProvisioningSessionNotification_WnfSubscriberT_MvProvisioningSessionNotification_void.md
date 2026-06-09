# WnfSubscriberT<MvProvisioningSessionNotification>::~WnfSubscriberT<MvProvisioningSessionNotification>(void)

- ea: `0x18002cafc`
- end: `0x18002cb5b`
- name: `??1?$WnfSubscriberT@UMvProvisioningSessionNotification@@@@UEAA@XZ`
- size: `95`
- prototype: `int __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d4a0`

## callees

- `0x18002cafc`
- `0x18002cb64`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cb2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cb4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cb2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cb4f`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18002cb18`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18002cb18`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall WnfSubscriberT<MvProvisioningSessionNotification>::~WnfSubscriberT<MvProvisioningSessionNotification>(
        _QWORD *a1)
{
  void *v2; // rcx
  int result; // eax
  void *v4; // rcx

  *a1 = &WnfSubscriberT<MvProvisioningSessionNotification>::`vftable';
  if ( a1[2] )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    a1[2] = 0;
  }
  v2 = (void *)a1[3];
  if ( v2 )
  {
    CloseHandle(v2);
    a1[3] = 0;
  }
  result = std::_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>,std::less<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,std::allocator<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,0>>::~_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>,std::less<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,std::allocator<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,0>>(a1 + 8);
  v4 = (void *)a1[3];
  if ( v4 )
    return CloseHandle(v4);
  return result;
}

```

## disassembly

```asm
0x18002cafc  push    rbx
0x18002cafe  sub     rsp, 20h
0x18002cb02  lea     rax, ??_7?$WnfSubscriberT@UMvProvisioningSessionNotification@@@@6B@; const WnfSubscriberT<MvProvisioningSessionNotification>::`vftable'
0x18002cb09  mov     rbx, rcx
0x18002cb0c  mov     [rcx], rax
0x18002cb0f  mov     rcx, [rcx+10h]
0x18002cb13  test    rcx, rcx
0x18002cb16  jz      short loc_18002CB26
0x18002cb18  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18002cb1e  mov     qword ptr [rbx+10h], 0
0x18002cb26  mov     rcx, [rbx+18h]; hObject
0x18002cb2a  test    rcx, rcx
0x18002cb2d  jz      short loc_18002CB3D
0x18002cb2f  call    cs:__imp_CloseHandle
0x18002cb35  mov     qword ptr [rbx+18h], 0
0x18002cb3d  lea     rcx, [rbx+40h]
0x18002cb41  call    ??1?$_Tree@V?$_Tset_traits@V?$shared_ptr@V?$function@$$A6AXAEBUMvProvisioningSessionNotification@@@Z@std@@@std@@U?$less@V?$shared_ptr@V?$function@$$A6AXAEBUMvProvisioningSessionNotification@@@Z@std@@@std@@@2@V?$allocator@V?$shared_ptr@V?$function@$$A6AXAEBUMvProvisioningSessionNotification@@@Z@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>,std::less<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,std::allocator<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,0>>::~_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>,std::less<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,std::allocator<std::shared_ptr<std::function<void (MvProvisioningSessionNotification const &)>>>,0>>(void)
0x18002cb46  mov     rcx, [rbx+18h]; hObject
0x18002cb4a  test    rcx, rcx
0x18002cb4d  jz      short loc_18002CB55
0x18002cb4f  call    cs:__imp_CloseHandle
0x18002cb55  add     rsp, 20h
0x18002cb59  pop     rbx
0x18002cb5a  retn
```
