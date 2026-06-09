# Microsoft::WRL::Details::MakeAndInitialize<CHiveUploadTaskHandler,CHiveUploadTaskHandler,>(CHiveUploadTaskHandler * *)

- ea: `0x180017fe4`
- end: `0x180018096`
- name: `??$MakeAndInitialize@VCHiveUploadTaskHandler@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCHiveUploadTaskHandler@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800194d0`

## callees

- `0x180005aa0`
- `0x18000bb54`
- `0x180017fe4`
- `0x1800187f4`
- `0x180018934`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CHiveUploadTaskHandler,CHiveUploadTaskHandler,>(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  unsigned int v4; // ebx
  _QWORD *v6; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v7; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v6 = v2;
  if ( v2 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler>(v2);
    *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskHandler>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v3 = &CHiveUploadTaskHandler::`vftable';
    v7 = v3;
    v6 = 0;
    ((void (__fastcall *)(_QWORD *))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler>::AddRef)(v3);
    *a1 = v3;
    Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v7);
    v4 = 0;
  }
  else
  {
    v4 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<CHiveUploadTaskHandler>::~MakeAllocator<CHiveUploadTaskHandler>(&v6);
  return v4;
}

```

## disassembly

```asm
0x180017fe4  mov     [rsp+arg_10], rbx
0x180017fe9  push    rdi
0x180017fea  sub     rsp, 20h
0x180017fee  mov     rdi, rcx
0x180017ff1  mov     qword ptr [rcx], 0
0x180017ff8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017fff  mov     ecx, 10h; unsigned __int64
0x180018004  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018009  mov     rbx, rax
0x18001800c  mov     [rsp+28h+arg_0], rax
0x180018011  test    rax, rax
0x180018014  jnz     short loc_18001801D
0x180018016  mov     ebx, 8007000Eh
0x18001801b  jmp     short loc_18001807F
0x18001801d  mov     rcx, rbx
0x180018020  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UITaskHandler@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler>(void)
0x180018025  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITaskHandler@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskHandler>::`vftable'
0x18001802c  mov     [rbx], rcx
0x18001802f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180018036  test    rcx, rcx
0x180018039  jz      short loc_180018048
0x18001803b  mov     rax, [rcx]
0x18001803e  mov     rax, [rax+8]
0x180018042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018047  nop
0x180018048  lea     rax, ??_7CHiveUploadTaskHandler@@6B@; const CHiveUploadTaskHandler::`vftable'
0x18001804f  mov     [rbx], rax
0x180018052  mov     [rsp+28h+arg_8], rbx
0x180018057  mov     [rsp+28h+arg_0], 0
0x180018060  mov     rcx, rbx
0x180018063  mov     rax, cs:off_1800211C8
0x18001806a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001806f  nop
0x180018070  mov     [rdi], rbx
0x180018073  lea     rcx, [rsp+28h+arg_8]
0x180018078  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x18001807d  xor     ebx, ebx
0x18001807f  lea     rcx, [rsp+28h+arg_0]
0x180018084  call    ??1?$MakeAllocator@VCHiveUploadTaskHandler@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CHiveUploadTaskHandler>::~MakeAllocator<CHiveUploadTaskHandler>(void)
0x180018089  mov     eax, ebx
0x18001808b  mov     rbx, [rsp+28h+arg_10]
0x180018090  add     rsp, 20h
0x180018094  pop     rdi
0x180018095  retn
```
