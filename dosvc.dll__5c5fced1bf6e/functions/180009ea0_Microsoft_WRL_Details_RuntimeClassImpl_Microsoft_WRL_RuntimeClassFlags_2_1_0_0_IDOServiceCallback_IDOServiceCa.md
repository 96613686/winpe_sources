# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>::Release(void)

- ea: `0x180009ea0`
- end: `0x180009eef`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDOServiceCallback@@UIDOServiceCallback2@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009f00`

## callees

- `0x180002aa0`
- `0x180009ea0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r9

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 20), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 48LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x180009ea0  push    rbx
0x180009ea2  sub     rsp, 20h
0x180009ea6  mov     r9, rcx
0x180009ea9  add     rcx, 14h; this
0x180009ead  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180009eb2  mov     ebx, eax
0x180009eb4  test    eax, eax
0x180009eb6  jnz     short loc_180009EE7
0x180009eb8  test    r9, r9
0x180009ebb  jz      short loc_180009ECF
0x180009ebd  mov     rdx, [r9]
0x180009ec0  mov     rcx, r9
0x180009ec3  mov     rax, [rdx+30h]
0x180009ec7  lea     edx, [rbx+1]
0x180009eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ecf  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180009ed6  test    rcx, rcx
0x180009ed9  jz      short loc_180009EE7
0x180009edb  mov     rax, [rcx]
0x180009ede  mov     rax, [rax+10h]
0x180009ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ee7  mov     eax, ebx
0x180009ee9  add     rsp, 20h
0x180009eed  pop     rbx
0x180009eee  retn
```
