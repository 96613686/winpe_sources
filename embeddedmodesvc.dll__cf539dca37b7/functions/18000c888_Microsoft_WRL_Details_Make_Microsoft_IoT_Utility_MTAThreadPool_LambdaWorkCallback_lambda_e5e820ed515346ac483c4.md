# Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_e5e820ed515346ac483c45f56bfacfa7_____lambda_e5e820ed515346ac483c45f56bfacfa7___

- ea: `0x18000c888`
- end: `0x18000c925`
- name: `Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_e5e820ed515346ac483c45f56bfacfa7_____lambda_e5e820ed515346ac483c45f56bfacfa7___`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000de50`

## callees

- `0x180002f60`
- `0x18000a604`
- `0x18000a9d8`
- `0x18000c888`
- `0x18000d1a8`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_e5e820ed515346ac483c45f56bfacfa7_____lambda_e5e820ed515346ac483c45f56bfacfa7___(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  _QWORD *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  v7 = v4;
  if ( v4 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>(v4);
    *v5 = &off_18001C498;
    Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>(
      v5 + 2,
      a2);
    v5[3] = a2[1];
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
0x18000c888  mov     [rsp+arg_8], rbx
0x18000c88d  mov     [rsp+arg_10], rsi
0x18000c892  push    rdi
0x18000c893  sub     rsp, 20h
0x18000c897  mov     rsi, rdx
0x18000c89a  mov     rdi, rcx
0x18000c89d  mov     qword ptr [rcx], 0
0x18000c8a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c8ab  mov     ecx, 20h ; ' '; unsigned __int64
0x18000c8b0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c8b5  mov     rbx, rax
0x18000c8b8  mov     [rsp+28h+arg_0], rax
0x18000c8bd  test    rax, rax
0x18000c8c0  jz      short loc_18000C908
0x18000c8c2  mov     rcx, rax
0x18000c8c5  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMTAThreadPoolWorkCallback@Utility@IoT@3@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>(void)
0x18000c8ca  lea     rax, off_18001C498
0x18000c8d1  mov     [rbx], rax
0x18000c8d4  mov     rdx, rsi
0x18000c8d7  lea     rcx, [rbx+10h]
0x18000c8db  call    ??0?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>(Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> &&)
0x18000c8e0  mov     rcx, [rsi+8]
0x18000c8e4  mov     [rbx+18h], rcx
0x18000c8e8  mov     rcx, [rdi]
0x18000c8eb  test    rcx, rcx
0x18000c8ee  jz      short loc_18000C8FC
0x18000c8f0  mov     rax, [rcx]
0x18000c8f3  mov     rax, [rax+10h]
0x18000c8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8fc  mov     [rdi], rbx
0x18000c8ff  mov     [rsp+28h+arg_0], 0
0x18000c908  lea     rcx, [rsp+28h+arg_0]
0x18000c90d  call    Microsoft__WRL__Details__MakeAllocator_Microsoft__IoT__Utility__MTAThreadPool__LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d________MakeAllocator_Microsoft__IoT__Utility__MTAThreadPool__LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____
0x18000c912  mov     rax, rdi
0x18000c915  mov     rbx, [rsp+28h+arg_8]
0x18000c91a  mov     rsi, [rsp+28h+arg_10]
0x18000c91f  add     rsp, 20h
0x18000c923  pop     rdi
0x18000c924  retn
```
