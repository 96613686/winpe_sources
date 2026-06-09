# Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_1bb57df98d7ba98072f104d9e64aece0_____lambda_1bb57df98d7ba98072f104d9e64aece0___

- ea: `0x180009a90`
- end: `0x180009b20`
- name: `Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_1bb57df98d7ba98072f104d9e64aece0_____lambda_1bb57df98d7ba98072f104d9e64aece0___`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b0a0`

## callees

- `0x180002f60`
- `0x180009a90`
- `0x18000a604`
- `0x18000a9d8`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_1bb57df98d7ba98072f104d9e64aece0_____lambda_1bb57df98d7ba98072f104d9e64aece0___(
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
    *v5 = &off_18001C390;
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
0x180009a90  mov     [rsp+arg_8], rbx
0x180009a95  mov     [rsp+arg_10], rsi
0x180009a9a  push    rdi
0x180009a9b  sub     rsp, 20h
0x180009a9f  mov     rsi, rdx
0x180009aa2  mov     rdi, rcx
0x180009aa5  mov     qword ptr [rcx], 0
0x180009aac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009ab3  mov     ecx, 18h; unsigned __int64
0x180009ab8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009abd  mov     rbx, rax
0x180009ac0  mov     [rsp+28h+arg_0], rax
0x180009ac5  test    rax, rax
0x180009ac8  jz      short loc_180009B03
0x180009aca  mov     rcx, rax
0x180009acd  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMTAThreadPoolWorkCallback@Utility@IoT@3@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>(void)
0x180009ad2  lea     rax, off_18001C390
0x180009ad9  mov     [rbx], rax
0x180009adc  mov     rcx, [rsi]
0x180009adf  mov     [rbx+10h], rcx
0x180009ae3  mov     rcx, [rdi]
0x180009ae6  test    rcx, rcx
0x180009ae9  jz      short loc_180009AF7
0x180009aeb  mov     rax, [rcx]
0x180009aee  mov     rax, [rax+10h]
0x180009af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009af7  mov     [rdi], rbx
0x180009afa  mov     [rsp+28h+arg_0], 0
0x180009b03  lea     rcx, [rsp+28h+arg_0]
0x180009b08  call    Microsoft__WRL__Details__MakeAllocator_Microsoft__IoT__Utility__MTAThreadPool__LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d________MakeAllocator_Microsoft__IoT__Utility__MTAThreadPool__LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____
0x180009b0d  mov     rax, rdi
0x180009b10  mov     rbx, [rsp+28h+arg_8]
0x180009b15  mov     rsi, [rsp+28h+arg_10]
0x180009b1a  add     rsp, 20h
0x180009b1e  pop     rdi
0x180009b1f  retn
```
