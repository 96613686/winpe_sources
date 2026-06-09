# Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____lambda_645992aee5a6b4af0977e82444ecfa7d___

- ea: `0x18000f3a8`
- end: `0x18000f438`
- name: `Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____lambda_645992aee5a6b4af0977e82444ecfa7d___`
- size: `144`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010db8`

## callees

- `0x180002f60`
- `0x18000a604`
- `0x18000a9d8`
- `0x18000f3a8`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____lambda_645992aee5a6b4af0977e82444ecfa7d___(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  _QWORD *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  v7 = v4;
  if ( v4 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>(v4);
    *v5 = &off_18001C588;
    v5[2] = *a2;
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v5;
    v7 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____::_MakeAllocator_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____(&v7);
  return a1;
}

```

## disassembly

```asm
0x18000f3a8  mov     [rsp+arg_8], rbx
0x18000f3ad  mov     [rsp+arg_10], rsi
0x18000f3b2  push    rdi
0x18000f3b3  sub     rsp, 20h
0x18000f3b7  mov     rsi, rdx
0x18000f3ba  mov     rdi, rcx
0x18000f3bd  mov     qword ptr [rcx], 0
0x18000f3c4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f3cb  mov     ecx, 18h; unsigned __int64
0x18000f3d0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f3d5  mov     rbx, rax
0x18000f3d8  mov     [rsp+28h+arg_0], rax
0x18000f3dd  test    rax, rax
0x18000f3e0  jz      short loc_18000F41B
0x18000f3e2  mov     rcx, rax
0x18000f3e5  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMTAThreadPoolWorkCallback@Utility@IoT@3@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>(void)
0x18000f3ea  lea     rax, off_18001C588
0x18000f3f1  mov     [rbx], rax
0x18000f3f4  mov     rcx, [rsi]
0x18000f3f7  mov     [rbx+10h], rcx
0x18000f3fb  mov     rcx, [rdi]
0x18000f3fe  test    rcx, rcx
0x18000f401  jz      short loc_18000F40F
0x18000f403  mov     rax, [rcx]
0x18000f406  mov     rax, [rax+10h]
0x18000f40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f40f  mov     [rdi], rbx
0x18000f412  mov     [rsp+28h+arg_0], 0
0x18000f41b  lea     rcx, [rsp+28h+arg_0]
0x18000f420  call    Microsoft__WRL__Details__MakeAllocator_Microsoft__IoT__Utility__MTAThreadPool__LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d________MakeAllocator_Microsoft__IoT__Utility__MTAThreadPool__LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____
0x18000f425  mov     rax, rdi
0x18000f428  mov     rbx, [rsp+28h+arg_8]
0x18000f42d  mov     rsi, [rsp+28h+arg_10]
0x18000f432  add     rsp, 20h
0x18000f436  pop     rdi
0x18000f437  retn
```
