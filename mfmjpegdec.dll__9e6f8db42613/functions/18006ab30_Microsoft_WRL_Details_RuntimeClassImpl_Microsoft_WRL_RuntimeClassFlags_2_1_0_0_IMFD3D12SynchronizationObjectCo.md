# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x18006ab30`
- end: `0x18006ab7f`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMFD3D12SynchronizationObjectCommands@@UIMFD3D12SynchronizationObject@@UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800696c8`
- `0x18006ab90`
- `0x18006aba0`
- `0x18006abb0`
- `0x18006abc0`
- `0x18006abd0`

## callees

- `0x1800428bc`
- `0x18006ab30`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r10

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 68), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 56LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x18006ab30  push    rbx
0x18006ab32  sub     rsp, 20h
0x18006ab36  mov     r10, rcx
0x18006ab39  add     rcx, 44h ; 'D'; this
0x18006ab3d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x18006ab42  mov     ebx, eax
0x18006ab44  test    eax, eax
0x18006ab46  jnz     short loc_18006AB77
0x18006ab48  test    r10, r10
0x18006ab4b  jz      short loc_18006AB5F
0x18006ab4d  mov     rdx, [r10]
0x18006ab50  mov     rcx, r10
0x18006ab53  mov     rax, [rdx+38h]
0x18006ab57  lea     edx, [rbx+1]
0x18006ab5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab5f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18006ab66  test    rcx, rcx
0x18006ab69  jz      short loc_18006AB77
0x18006ab6b  mov     rax, [rcx]
0x18006ab6e  mov     rax, [rax+10h]
0x18006ab72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab77  mov     eax, ebx
0x18006ab79  add     rsp, 20h
0x18006ab7d  pop     rbx
0x18006ab7e  retn
```
