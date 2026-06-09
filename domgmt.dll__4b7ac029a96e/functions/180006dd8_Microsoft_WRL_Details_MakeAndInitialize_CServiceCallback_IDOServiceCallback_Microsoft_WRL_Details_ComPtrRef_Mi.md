# Microsoft::WRL::Details::MakeAndInitialize<CServiceCallback,IDOServiceCallback,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDOServiceCallback>>)

- ea: `0x180006dd8`
- end: `0x180006eaa`
- name: `??$MakeAndInitialize@VCServiceCallback@@UIDOServiceCallback@@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIDOServiceCallback@@@WRL@Microsoft@@@012@@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ae80`

## callees

- `0x1800022cc`
- `0x180006dd8`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CServiceCallback,IDOServiceCallback,>(__int64 *a1)
{
  __int64 v2; // rcx
  _QWORD *v3; // rax
  _QWORD *v4; // rdi
  unsigned int v5; // ebx

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  *a1 = 0;
  v3 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 5) = 1;
    *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDOServiceCallback,IDOServiceCallback2>::`vftable'{for `IDOServiceCallback'};
    v3[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDOServiceCallback,IDOServiceCallback2>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDOServiceCallback2>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v4 = &CServiceCallback::`vftable'{for `IDOServiceCallback'};
    v4[1] = &CServiceCallback::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDOServiceCallback2>'};
    v5 = ((__int64 (__fastcall *)(_QWORD *, GUID *, __int64 *))CServiceCallback::`vftable'{for `IDOServiceCallback'})(
           v4,
           &GUID_a92e7211_62cc_4a07_8e5c_2972f0bfe476,
           a1);
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v5;
}

```

## disassembly

```asm
0x180006dd8  mov     [rsp+arg_0], rbx
0x180006ddd  push    rdi
0x180006dde  sub     rsp, 20h
0x180006de2  mov     rbx, rcx
0x180006de5  mov     rcx, [rcx]
0x180006de8  test    rcx, rcx
0x180006deb  jz      short loc_180006E01
0x180006ded  mov     qword ptr [rbx], 0
0x180006df4  mov     rax, [rcx]
0x180006df7  mov     rax, [rax+10h]
0x180006dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e00  nop
0x180006e01  mov     qword ptr [rbx], 0
0x180006e08  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006e0f  mov     ecx, 18h; unsigned __int64
0x180006e14  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006e19  mov     rdi, rax
0x180006e1c  test    rax, rax
0x180006e1f  jnz     short loc_180006E28
0x180006e21  mov     ebx, 8007000Eh
0x180006e26  jmp     short loc_180006E9D
0x180006e28  mov     dword ptr [rax+14h], 1
0x180006e2f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDOServiceCallback@@UIDOServiceCallback2@@@WRL@Microsoft@@6BIDOServiceCallback@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDOServiceCallback,IDOServiceCallback2>::`vftable'{for `IDOServiceCallback'}
0x180006e36  mov     [rdi], rax
0x180006e39  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDOServiceCallback@@UIDOServiceCallback2@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIDOServiceCallback2@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDOServiceCallback,IDOServiceCallback2>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDOServiceCallback2>'}
0x180006e40  mov     [rdi+8], rax
0x180006e44  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180006e4b  test    rcx, rcx
0x180006e4e  jz      short loc_180006E5D
0x180006e50  mov     rax, [rcx]
0x180006e53  mov     rax, [rax+8]
0x180006e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e5c  nop
0x180006e5d  lea     rax, ??_7CServiceCallback@@6BIDOServiceCallback@@@; const CServiceCallback::`vftable'{for `IDOServiceCallback'}
0x180006e64  mov     [rdi], rax
0x180006e67  lea     rax, ??_7CServiceCallback@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIDOServiceCallback2@@@Details@WRL@Microsoft@@@; const CServiceCallback::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDOServiceCallback2>'}
0x180006e6e  mov     [rdi+8], rax
0x180006e72  mov     r8, rbx
0x180006e75  lea     rdx, _GUID_a92e7211_62cc_4a07_8e5c_2972f0bfe476
0x180006e7c  mov     rcx, rdi
0x180006e7f  mov     rax, cs:??_7CServiceCallback@@6BIDOServiceCallback@@@; const CServiceCallback::`vftable'{for `IDOServiceCallback'}
0x180006e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e8b  mov     ebx, eax
0x180006e8d  mov     rcx, [rdi]
0x180006e90  mov     rax, [rcx+10h]
0x180006e94  mov     rcx, rdi
0x180006e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e9c  nop
0x180006e9d  mov     eax, ebx
0x180006e9f  mov     rbx, [rsp+28h+arg_0]
0x180006ea4  add     rsp, 20h
0x180006ea8  pop     rdi
0x180006ea9  retn
```
