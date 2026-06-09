# Microsoft::IoT::Utility::MTAThreadPool::QueueDelayedLambda__lambda_c03daee19112fcf77f71079884cb6bd0___

- ea: `0x18000f58c`
- end: `0x18000f64a`
- name: `Microsoft::IoT::Utility::MTAThreadPool::QueueDelayedLambda__lambda_c03daee19112fcf77f71079884cb6bd0___`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012f10`

## callees

- `0x18000a730`
- `0x18000aa70`
- `0x18000c668`
- `0x18000c9f4`
- `0x18000cd7c`
- `0x18000d6d8`
- `0x18000d82c`
- `0x18000f304`
- `0x18000f58c`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::IoT::Utility::MTAThreadPool::QueueDelayedLambda__lambda_c03daee19112fcf77f71079884cb6bd0___(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  struct Microsoft::IoT::Utility::MTAThreadPool *v5; // rbx
  unsigned int v6; // edi
  _QWORD v8[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v9; // [rsp+30h] [rbp-20h] BYREF
  __int64 v10; // [rsp+38h] [rbp-18h]
  __int64 v11; // [rsp+40h] [rbp-10h]
  struct Microsoft::IoT::Utility::MTAThreadPool *v12; // [rsp+78h] [rbp+28h] BYREF

  Microsoft::IoT::Utility::MTAThreadPool::GetDelayTimer(v8, a2);
  Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaEventCallback__lambda_c03daee19112fcf77f71079884cb6bd0_____lambda_c03daee19112fcf77f71079884cb6bd0___(
    &v12,
    a3);
  v5 = v12;
  if ( v12 )
  {
    std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(&v9);
    if ( v10 == v11 )
    {
      std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::_Emplace_reallocate<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>> const &>(
        &v9,
        v10,
        v8);
    }
    else
    {
      std::_Construct_in_place<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>> const &>(
        v10,
        v8);
      v10 += 16;
    }
    v6 = Microsoft::IoT::Utility::MTAThreadPool::QueueMultiEventItem(a1, &v9, v5);
    std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::_Tidy(&v9);
  }
  else
  {
    v6 = -2147024882;
  }
  if ( v5 )
    (*(void (__fastcall **)(struct Microsoft::IoT::Utility::MTAThreadPool *))(*(_QWORD *)v5 + 16LL))(v5);
  std::shared_ptr<Microsoft::IoT::Utility::MTAThread>::~shared_ptr<Microsoft::IoT::Utility::MTAThread>((__int64)v8);
  return v6;
}

```

## disassembly

```asm
0x18000f58c  mov     [rsp-8+arg_0], rbx
0x18000f591  mov     [rsp-8+arg_8], rdi
0x18000f596  push    rbp
0x18000f597  mov     rbp, rsp
0x18000f59a  sub     rsp, 50h
0x18000f59e  mov     rbx, r8
0x18000f5a1  mov     rdi, rcx
0x18000f5a4  lea     rcx, [rbp+var_30]
0x18000f5a8  call    ?GetDelayTimer@MTAThreadPool@Utility@IoT@Microsoft@@CA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@_K@Z; Microsoft::IoT::Utility::MTAThreadPool::GetDelayTimer(unsigned __int64)
0x18000f5ad  nop
0x18000f5ae  mov     rdx, rbx
0x18000f5b1  lea     rcx, [rbp+arg_18]
0x18000f5b5  call    Microsoft__WRL__Details__Make_Microsoft__IoT__Utility__MTAThreadPool__LambdaEventCallback__lambda_c03daee19112fcf77f71079884cb6bd0_____lambda_c03daee19112fcf77f71079884cb6bd0___
0x18000f5ba  nop
0x18000f5bb  mov     rbx, [rbp+arg_18]
0x18000f5bf  test    rbx, rbx
0x18000f5c2  jnz     short loc_18000F5CB
0x18000f5c4  mov     edi, 8007000Eh
0x18000f5c9  jmp     short loc_18000F61A
0x18000f5cb  lea     rcx, [rbp+var_20]
0x18000f5cf  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x18000f5d4  nop
0x18000f5d5  mov     rcx, [rbp+var_18]
0x18000f5d9  cmp     rcx, [rbp+var_10]
0x18000f5dd  jz      short loc_18000F5EF
0x18000f5df  lea     rdx, [rbp+var_30]
0x18000f5e3  call    ??$_Construct_in_place@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV12@@std@@YAXAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV12@@Z; std::_Construct_in_place<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &>(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &)
0x18000f5e8  add     [rbp+var_18], 10h
0x18000f5ed  jmp     short loc_18000F5FF
0x18000f5ef  lea     r8, [rbp+var_30]
0x18000f5f3  mov     rdx, rcx
0x18000f5f6  lea     rcx, [rbp+var_20]
0x18000f5fa  call    ??$_Emplace_reallocate@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAV23@AEBV23@@Z; std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::_Emplace_reallocate<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &>(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> * const,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &)
0x18000f5ff  mov     r8, rbx
0x18000f602  lea     rdx, [rbp+var_20]
0x18000f606  mov     rcx, rdi
0x18000f609  call    ?QueueMultiEventItem@MTAThreadPool@Utility@IoT@Microsoft@@QEAAJAEBV?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@PEAUIMTAThreadPoolEventCallback@234@@Z; Microsoft::IoT::Utility::MTAThreadPool::QueueMultiEventItem(std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>> const &,Microsoft::IoT::Utility::IMTAThreadPoolEventCallback *)
0x18000f60e  mov     edi, eax
0x18000f610  lea     rcx, [rbp+var_20]
0x18000f614  call    ?_Tidy@?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::_Tidy(void)
0x18000f619  nop
0x18000f61a  test    rbx, rbx
0x18000f61d  jz      short loc_18000F62F
0x18000f61f  mov     rdx, [rbx]
0x18000f622  mov     rcx, rbx
0x18000f625  mov     rax, [rdx+10h]
0x18000f629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f62e  nop
0x18000f62f  lea     rcx, [rbp+var_30]
0x18000f633  call    ??1?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::IoT::Utility::MTAThread>::~shared_ptr<Microsoft::IoT::Utility::MTAThread>(void)
0x18000f638  mov     eax, edi
0x18000f63a  mov     rbx, [rsp+50h+arg_0]
0x18000f63f  mov     rdi, [rsp+50h+arg_8]
0x18000f644  add     rsp, 50h
0x18000f648  pop     rbp
0x18000f649  retn
```
