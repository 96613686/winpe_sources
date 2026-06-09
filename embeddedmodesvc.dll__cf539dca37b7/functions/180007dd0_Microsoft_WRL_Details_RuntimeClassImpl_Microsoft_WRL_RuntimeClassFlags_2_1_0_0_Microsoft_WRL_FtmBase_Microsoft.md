# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(void)

- ea: `0x180007dd0`
- end: `0x180007e1f`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `14`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007b0c`
- `0x180007cec`
- `0x180008018`
- `0x1800081c4`
- `0x180008778`
- `0x180009690`
- `0x180009b28`
- `0x18000b9cc`
- `0x18000ba64`
- `0x18000be30`
- `0x18000f440`
- `0x18000f4dc`
- `0x18001029c`
- `0x180019f90`

## callees

- `0x180007dd0`
- `0x180007e28`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r10

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 44), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 72LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x180007dd0  push    rbx
0x180007dd2  sub     rsp, 20h
0x180007dd6  mov     r10, rcx
0x180007dd9  add     rcx, 2Ch ; ','; this
0x180007ddd  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180007de2  mov     ebx, eax
0x180007de4  test    eax, eax
0x180007de6  jnz     short loc_180007E17
0x180007de8  test    r10, r10
0x180007deb  jz      short loc_180007DFF
0x180007ded  mov     rdx, [r10]
0x180007df0  mov     rcx, r10
0x180007df3  mov     rax, [rdx+48h]
0x180007df7  lea     edx, [rbx+1]
0x180007dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dff  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007e06  test    rcx, rcx
0x180007e09  jz      short loc_180007E17
0x180007e0b  mov     rax, [rcx]
0x180007e0e  mov     rax, [rax+10h]
0x180007e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e17  mov     eax, ebx
0x180007e19  add     rsp, 20h
0x180007e1d  pop     rbx
0x180007e1e  retn
```
