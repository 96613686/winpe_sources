# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)

- ea: `0x18001ce50`
- end: `0x18001cea0`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `80`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800078ac`
- `0x180042a8c`
- `0x180042fb0`
- `0x180043768`
- `0x1800438b8`
- `0x180043c70`
- `0x180043e30`

## callees

- `0x1800121f8`
- `0x18001ce50`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r10

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 12), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 32LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      Microsoft::WRL::Details::ModuleBase::module_->DecrementObjectCount(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x18001ce50  push    rbx
0x18001ce52  sub     rsp, 20h
0x18001ce56  mov     r10, rcx
0x18001ce59  add     rcx, 0Ch; this
0x18001ce5d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x18001ce62  mov     ebx, eax
0x18001ce64  test    eax, eax
0x18001ce66  jnz     short loc_18001CE97
0x18001ce68  test    r10, r10
0x18001ce6b  jz      short loc_18001CE7F
0x18001ce6d  mov     rdx, [r10]
0x18001ce70  mov     rcx, r10
0x18001ce73  mov     rax, [rdx+20h]
0x18001ce77  lea     edx, [rbx+1]
0x18001ce7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce7f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001ce86  test    rcx, rcx
0x18001ce89  jz      short loc_18001CE97
0x18001ce8b  mov     rax, [rcx]
0x18001ce8e  mov     rax, [rax+10h]
0x18001ce92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce97  mov     eax, ebx
0x18001ce99  add     rsp, 20h
0x18001ce9d  pop     rbx
0x18001ce9e  retn
```
