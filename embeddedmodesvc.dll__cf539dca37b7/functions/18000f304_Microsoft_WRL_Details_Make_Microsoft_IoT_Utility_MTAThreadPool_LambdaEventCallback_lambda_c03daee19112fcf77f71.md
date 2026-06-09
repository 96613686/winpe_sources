# Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaEventCallback__lambda_c03daee19112fcf77f71079884cb6bd0_____lambda_c03daee19112fcf77f71079884cb6bd0___

- ea: `0x18000f304`
- end: `0x18000f3a2`
- name: `Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaEventCallback__lambda_c03daee19112fcf77f71079884cb6bd0_____lambda_c03daee19112fcf77f71079884cb6bd0___`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f58c`

## callees

- `0x180002f60`
- `0x18000a9d8`
- `0x18000f304`
- `0x18000ff20`
- `0x180010070`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaEventCallback__lambda_c03daee19112fcf77f71079884cb6bd0_____lambda_c03daee19112fcf77f71079884cb6bd0___(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  _QWORD *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  v7 = v4;
  if ( v4 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>(v4);
    *v5 = &off_18001C5B0;
    v5[2] = *a2;
    Microsoft::IoT::ShellExtension::CCBT::CCBT(v5 + 3, a2 + 1);
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
0x18000f304  mov     [rsp+arg_8], rbx
0x18000f309  mov     [rsp+arg_10], rsi
0x18000f30e  push    rdi
0x18000f30f  sub     rsp, 20h
0x18000f313  mov     rsi, rdx
0x18000f316  mov     rdi, rcx
0x18000f319  mov     qword ptr [rcx], 0
0x18000f320  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f327  mov     ecx, 70h ; 'p'; unsigned __int64
0x18000f32c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f331  mov     rbx, rax
0x18000f334  mov     [rsp+28h+arg_0], rax
0x18000f339  test    rax, rax
0x18000f33c  jz      short loc_18000F385
0x18000f33e  mov     rcx, rax
0x18000f341  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMTAThreadPoolEventCallback@Utility@IoT@3@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>(void)
0x18000f346  lea     rax, off_18001C5B0
0x18000f34d  mov     [rbx], rax
0x18000f350  mov     rcx, [rsi]
0x18000f353  mov     [rbx+10h], rcx
0x18000f357  lea     rdx, [rsi+8]
0x18000f35b  lea     rcx, [rbx+18h]
0x18000f35f  call    ??0CCBT@ShellExtension@IoT@Microsoft@@QEAA@$$QEAV0123@@Z; Microsoft::IoT::ShellExtension::CCBT::CCBT(Microsoft::IoT::ShellExtension::CCBT &&)
0x18000f364  nop
0x18000f365  mov     rcx, [rdi]
0x18000f368  test    rcx, rcx
0x18000f36b  jz      short loc_18000F379
0x18000f36d  mov     rax, [rcx]
0x18000f370  mov     rax, [rax+10h]
0x18000f374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f379  mov     [rdi], rbx
0x18000f37c  mov     [rsp+28h+arg_0], 0
0x18000f385  lea     rcx, [rsp+28h+arg_0]
0x18000f38a  call    Microsoft__WRL__Details__MakeAllocator_Microsoft__IoT__Utility__MTAThreadPool__LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d________MakeAllocator_Microsoft__IoT__Utility__MTAThreadPool__LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____
0x18000f38f  mov     rax, rdi
0x18000f392  mov     rbx, [rsp+28h+arg_8]
0x18000f397  mov     rsi, [rsp+28h+arg_10]
0x18000f39c  add     rsp, 20h
0x18000f3a0  pop     rdi
0x18000f3a1  retn
```
