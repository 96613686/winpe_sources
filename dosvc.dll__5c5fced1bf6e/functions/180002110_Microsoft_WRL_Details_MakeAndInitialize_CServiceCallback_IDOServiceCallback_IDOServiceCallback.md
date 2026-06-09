# Microsoft::WRL::Details::MakeAndInitialize<CServiceCallback,IDOServiceCallback,>(IDOServiceCallback * *)

- ea: `0x180002110`
- end: `0x1800021c7`
- name: `??$MakeAndInitialize@VCServiceCallback@@UIDOServiceCallback@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIDOServiceCallback@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001f60`

## callees

- `0x180002110`
- `0x18000401c`
- `0x18000547c`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CServiceCallback,IDOServiceCallback,>(_QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  unsigned int v5; // edi

  *a1 = 0;
  v2 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>(v2);
  *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDOServiceCallback,IDOServiceCallback2>::`vftable'{for `IDOServiceCallback'};
  v3[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDOServiceCallback,IDOServiceCallback2>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDOServiceCallback2>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *v3 = &CServiceCallback::`vftable'{for `IDOServiceCallback'};
  v3[1] = &CServiceCallback::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDOServiceCallback2>'};
  v5 = ((__int64 (__fastcall *)(_QWORD *, GUID *, _QWORD *))CServiceCallback::`vftable'{for `IDOServiceCallback'})(
         v3,
         &GUID_a92e7211_62cc_4a07_8e5c_2972f0bfe476,
         a1);
  (*(void (__fastcall **)(_QWORD *))(*v3 + 16LL))(v3);
  return v5;
}

```

## disassembly

```asm
0x180002110  mov     [rsp+arg_0], rbx
0x180002115  push    rdi
0x180002116  sub     rsp, 20h
0x18000211a  mov     rdi, rcx
0x18000211d  mov     qword ptr [rcx], 0
0x180002124  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000212b  mov     ecx, 18h; unsigned __int64
0x180002130  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002135  mov     rbx, rax
0x180002138  test    rax, rax
0x18000213b  jnz     short loc_180002144
0x18000213d  mov     eax, 8007000Eh
0x180002142  jmp     short loc_1800021BC
0x180002144  mov     rcx, rbx
0x180002147  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDOServiceCallback@@UIDOServiceCallback2@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>(void)
0x18000214c  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDOServiceCallback@@UIDOServiceCallback2@@@WRL@Microsoft@@6BIDOServiceCallback@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDOServiceCallback,IDOServiceCallback2>::`vftable'{for `IDOServiceCallback'}
0x180002153  mov     [rbx], rcx
0x180002156  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDOServiceCallback@@UIDOServiceCallback2@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIDOServiceCallback2@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDOServiceCallback,IDOServiceCallback2>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDOServiceCallback2>'}
0x18000215d  mov     [rbx+8], rax
0x180002161  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002168  test    rcx, rcx
0x18000216b  jz      short loc_18000217A
0x18000216d  mov     rax, [rcx]
0x180002170  mov     rax, [rax+8]
0x180002174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002179  nop
0x18000217a  lea     rax, ??_7CServiceCallback@@6BIDOServiceCallback@@@; const CServiceCallback::`vftable'{for `IDOServiceCallback'}
0x180002181  mov     [rbx], rax
0x180002184  lea     rax, ??_7CServiceCallback@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIDOServiceCallback2@@@Details@WRL@Microsoft@@@; const CServiceCallback::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IDOServiceCallback2>'}
0x18000218b  mov     [rbx+8], rax
0x18000218f  mov     r8, rdi
0x180002192  lea     rdx, _GUID_a92e7211_62cc_4a07_8e5c_2972f0bfe476
0x180002199  mov     rcx, rbx
0x18000219c  mov     rax, cs:??_7CServiceCallback@@6BIDOServiceCallback@@@; const CServiceCallback::`vftable'{for `IDOServiceCallback'}
0x1800021a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021a8  mov     edi, eax
0x1800021aa  mov     rcx, [rbx]
0x1800021ad  mov     rax, [rcx+10h]
0x1800021b1  mov     rcx, rbx
0x1800021b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021b9  nop
0x1800021ba  mov     eax, edi
0x1800021bc  mov     rbx, [rsp+28h+arg_0]
0x1800021c1  add     rsp, 20h
0x1800021c5  pop     rdi
0x1800021c6  retn
```
