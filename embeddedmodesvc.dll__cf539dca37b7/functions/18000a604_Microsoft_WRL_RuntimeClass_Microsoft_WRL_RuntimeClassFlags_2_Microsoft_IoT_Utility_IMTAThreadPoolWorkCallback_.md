# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>(void)

- ea: `0x18000a604`
- end: `0x18000a63d`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMTAThreadPoolWorkCallback@Utility@IoT@3@@WRL@Microsoft@@QEAA@XZ`
- size: `57`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009a90`
- `0x18000c888`
- `0x18000f3a8`

## callees

- `0x18000a604`
- `0x18000a644`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>(
        _QWORD *a1)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>();
  *a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x18000a604  push    rbx
0x18000a606  sub     rsp, 20h
0x18000a60a  mov     rbx, rcx
0x18000a60d  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMTAThreadPoolEventCallback@Utility@IoT@3@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>(void)
0x18000a612  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMTAThreadPoolWorkCallback@Utility@IoT@3@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::`vftable'
0x18000a619  mov     [rbx], rcx
0x18000a61c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a623  test    rcx, rcx
0x18000a626  jz      short loc_18000A634
0x18000a628  mov     rax, [rcx]
0x18000a62b  mov     rax, [rax+8]
0x18000a62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a634  mov     rax, rbx
0x18000a637  add     rsp, 20h
0x18000a63b  pop     rbx
0x18000a63c  retn
```
