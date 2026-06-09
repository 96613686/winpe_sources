# WwanController::`vector deleting destructor'(uint)

- ea: `0x18000a530`
- end: `0x18000a595`
- name: `??_EWwanController@@EEAAPEAXI@Z`
- size: `101`
- prototype: `WwanController *__fastcall(WwanController *this, char)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18000a350`
- `0x18000a3d0`
- `0x18000a46c`
- `0x18000a530`
- `0x18000e418`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a581`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a581`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a552`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a552`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WwanController *__fastcall WwanController::`vector deleting destructor'(WwanController *this, char a2)
{
  *(_QWORD *)this = &WwanController::`vftable';
  WwanController::clearExecIntfList(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  std::_Tree<std::_Tmap_traits<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>::~_Tree<std::_Tmap_traits<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>((void **)this + 19);
  std::_Tree<std::_Tmap_traits<_GUID,WwanController::WwanModemInformation,WwanController::GuidLessThan,std::allocator<std::pair<_GUID const,WwanController::WwanModemInformation>>,0>>::~_Tree<std::_Tmap_traits<_GUID,WwanController::WwanModemInformation,WwanController::GuidLessThan,std::allocator<std::pair<_GUID const,WwanController::WwanModemInformation>>,0>>((char *)this + 136);
  std::deque<_L2_NOTIFICATION_DATA *>::~deque<_L2_NOTIFICATION_DATA *>((char *)this + 88);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000a530  mov     [rsp+arg_0], rbx
0x18000a535  push    rdi
0x18000a536  sub     rsp, 20h
0x18000a53a  lea     rax, ??_7WwanController@@6B@; const WwanController::`vftable'
0x18000a541  mov     ebx, edx
0x18000a543  mov     [rcx], rax
0x18000a546  mov     rdi, rcx
0x18000a549  call    ?clearExecIntfList@WwanController@@AEAAXXZ; WwanController::clearExecIntfList(void)
0x18000a54e  lea     rcx, [rdi+10h]; lpCriticalSection
0x18000a552  call    cs:__imp_DeleteCriticalSection
0x18000a558  lea     rcx, [rdi+98h]
0x18000a55f  call    ??1?$_Tree@V?$_Tmap_traits@W4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@JU?$less@W4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@@std@@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<__MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<__MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>::~_Tree<std::_Tmap_traits<__MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<__MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>(void)
0x18000a564  lea     rcx, [rdi+88h]
0x18000a56b  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@UWwanModemInformation@WwanController@@UGuidLessThan@3@V?$allocator@U?$pair@$$CBU_GUID@@UWwanModemInformation@WwanController@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,WwanController::WwanModemInformation,WwanController::GuidLessThan,std::allocator<std::pair<_GUID const,WwanController::WwanModemInformation>>,0>>::~_Tree<std::_Tmap_traits<_GUID,WwanController::WwanModemInformation,WwanController::GuidLessThan,std::allocator<std::pair<_GUID const,WwanController::WwanModemInformation>>,0>>(void)
0x18000a570  lea     rcx, [rdi+58h]
0x18000a574  call    ??1?$deque@PEAU_L2_NOTIFICATION_DATA@@V?$allocator@PEAU_L2_NOTIFICATION_DATA@@@std@@@std@@QEAA@XZ; std::deque<_L2_NOTIFICATION_DATA *>::~deque<_L2_NOTIFICATION_DATA *>(void)
0x18000a579  test    bl, 1
0x18000a57c  jz      short loc_18000A587
0x18000a57e  mov     rcx, rdi
0x18000a581  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a587  mov     rbx, [rsp+28h+arg_0]
0x18000a58c  mov     rax, rdi
0x18000a58f  add     rsp, 20h
0x18000a593  pop     rdi
0x18000a594  retn
```
