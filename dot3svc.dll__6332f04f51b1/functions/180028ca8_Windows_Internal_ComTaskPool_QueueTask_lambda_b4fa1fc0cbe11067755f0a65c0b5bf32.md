# Windows::Internal::ComTaskPool::QueueTask__lambda_b4fa1fc0cbe11067755f0a65c0b5bf32___

- ea: `0x180028ca8`
- end: `0x180028d3e`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_b4fa1fc0cbe11067755f0a65c0b5bf32___`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b88c`

## callees

- `0x180002a10`
- `0x180028ca8`
- `0x18002aaf0`
- `0x18002b468`
- `0x180040010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180028d16`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180028d16`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::Internal::ComTaskPool::QueueTask__lambda_b4fa1fc0cbe11067755f0a65c0b5bf32___(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        ...)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  _QWORD *v7; // rbx
  unsigned int v8; // edi
  _QWORD *v10; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v10 = va_arg(va1, _QWORD *);
  v5 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v6 = v5;
  v10 = v5;
  v7 = 0;
  if ( v5 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v5);
    *v6 = &off_1800414A8;
    v10 = 0;
    v7 = v6;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_f832dff8963ad3d707781d512be5e0ff_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_f832dff8963ad3d707781d512be5e0ff_____((_QWORD **)va);
  v8 = SHTaskPoolQueueTask(0, a2, a3);
  if ( v7 )
    (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
  return v8;
}

```

## disassembly

```asm
0x180028ca8  mov     [rsp+arg_18], r9
0x180028cad  push    rbx
0x180028cae  push    rbp
0x180028caf  push    rsi
0x180028cb0  push    rdi
0x180028cb1  sub     rsp, 38h
0x180028cb5  mov     esi, r8d
0x180028cb8  mov     ebp, edx
0x180028cba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028cc1  mov     ecx, 18h; unsigned __int64
0x180028cc6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180028ccb  mov     rdi, rax
0x180028cce  mov     [rsp+58h+arg_18], rax
0x180028cd3  xor     ebx, ebx
0x180028cd5  test    rax, rax
0x180028cd8  jz      short loc_180028CF4
0x180028cda  mov     rcx, rax
0x180028cdd  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x180028ce2  lea     rax, off_1800414A8
0x180028ce9  mov     [rdi], rax
0x180028cec  mov     [rsp+58h+arg_18], rbx
0x180028cf1  mov     rbx, rdi
0x180028cf4  lea     rcx, [rsp+58h+arg_18]
0x180028cf9  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_f832dff8963ad3d707781d512be5e0ff________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_f832dff8963ad3d707781d512be5e0ff_____
0x180028cfe  mov     [rsp+58h+var_30], 0
0x180028d07  mov     [rsp+58h+var_38], rbx
0x180028d0c  xor     r9d, r9d
0x180028d0f  mov     r8d, esi
0x180028d12  mov     edx, ebp
0x180028d14  xor     ecx, ecx
0x180028d16  call    cs:__imp_SHTaskPoolQueueTask
0x180028d1c  mov     edi, eax
0x180028d1e  test    rbx, rbx
0x180028d21  jz      short loc_180028D33
0x180028d23  mov     rdx, [rbx]
0x180028d26  mov     rcx, rbx
0x180028d29  mov     rax, [rdx+10h]
0x180028d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d32  nop
0x180028d33  mov     eax, edi
0x180028d35  add     rsp, 38h
0x180028d39  pop     rdi
0x180028d3a  pop     rsi
0x180028d3b  pop     rbp
0x180028d3c  pop     rbx
0x180028d3d  retn
```
