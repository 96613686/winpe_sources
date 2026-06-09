# std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> const &>(Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> * const,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> const &)

- ea: `0x18000a098`
- end: `0x18000a1d8`
- name: `??$_Emplace_reallocate@AEBV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@QEAV234@AEBV234@@Z`
- size: `320`
- prototype: `_QWORD *__fastcall(__int64 *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000bb44`

## callees

- `0x180009ebc`
- `0x180009f7c`
- `0x180009fb0`
- `0x18000a098`
- `0x18000a1e0`
- `0x18000a248`
- `0x18000ae94`
- `0x18000bea0`
- `0x18000c6b8`

## pseudocode

```c
_QWORD *__fastcall std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> const &>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rax
  unsigned __int64 v8; // r15
  __int64 v9; // r14
  unsigned __int64 v10; // rcx
  __int64 v11; // r14
  unsigned __int64 v12; // rdx
  size_t size_of; // rax
  _QWORD *v14; // rax
  volatile int *v15; // rdx
  __int64 v16; // rcx
  _QWORD *v17; // rsi
  _QWORD *v18; // r14
  __int64 v19; // rdx
  _QWORD *v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rcx
  _QWORD v24[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v25; // [rsp+38h] [rbp-60h]
  _QWORD *v26; // [rsp+40h] [rbp-58h]

  v3 = 0x1FFFFFFFFFFFFFFFLL;
  v5 = (a1[1] - *a1) >> 3;
  if ( v5 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::_Xlength();
  v8 = v5 + 1;
  v9 = a2 - *a1;
  v10 = (a1[2] - *a1) >> 3;
  v11 = v9 >> 3;
  v12 = v10 >> 1;
  if ( v10 <= 0x1FFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v12 + v10;
    if ( v12 + v10 < v8 )
      v3 = v5 + 1;
  }
  size_of = std::_Get_size_of_n<8>(v3);
  v14 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v16 = *a3;
  v17 = v14;
  v24[0] = a1;
  v24[2] = v3;
  v18 = &v14[v11];
  *v18 = v16;
  v26 = v18 + 1;
  if ( v16 )
    Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v16 + 44), v15);
  v19 = a1[1];
  v20 = v17;
  v21 = *a1;
  v25 = v18;
  if ( a2 != v19 )
  {
    std::_Uninitialized_move<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> *,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>(
      v21,
      a2,
      v17);
    v19 = a1[1];
    v20 = v18 + 1;
    v21 = a2;
    v25 = v17;
  }
  std::_Uninitialized_move<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> *,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>(
    v21,
    v19,
    v20);
  v22 = *a1;
  v24[1] = 0;
  if ( v22 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>(
      v22,
      a1[1]);
    std::_Deallocate<16>((_QWORD *)*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = (__int64)v17;
  a1[1] = (__int64)&v17[v8];
  a1[2] = (__int64)&v17[v3];
  std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::_Reallocation_guard::~_Reallocation_guard(v24);
  return v18;
}

```

## disassembly

```asm
0x18000a098  push    rbx
0x18000a09a  push    rbp
0x18000a09b  push    rsi
0x18000a09c  push    rdi
0x18000a09d  push    r12
0x18000a09f  push    r13
0x18000a0a1  push    r14
0x18000a0a3  push    r15
0x18000a0a5  sub     rsp, 58h
0x18000a0a9  mov     rax, [rcx+8]
0x18000a0ad  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18000a0b7  sub     rax, [rcx]
0x18000a0ba  mov     r13, r8
0x18000a0bd  sar     rax, 3
0x18000a0c1  mov     rbp, rdx
0x18000a0c4  mov     rbx, rcx
0x18000a0c7  cmp     rax, rdi
0x18000a0ca  jz      loc_18000A1D2
0x18000a0d0  mov     r14, rdx
0x18000a0d3  lea     r15, [rax+1]
0x18000a0d7  sub     r14, [rcx]
0x18000a0da  mov     rax, rdi
0x18000a0dd  mov     rcx, [rcx+10h]
0x18000a0e1  sub     rcx, [rbx]
0x18000a0e4  sar     rcx, 3
0x18000a0e8  mov     rdx, rcx
0x18000a0eb  sar     r14, 3
0x18000a0ef  shr     rdx, 1
0x18000a0f2  sub     rax, rdx
0x18000a0f5  cmp     rcx, rax
0x18000a0f8  ja      short loc_18000A105
0x18000a0fa  lea     rdi, [rdx+rcx]
0x18000a0fe  cmp     rdi, r15
0x18000a101  cmovb   rdi, r15
0x18000a105  mov     rcx, rdi
0x18000a108  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18000a10d  mov     rcx, rax
0x18000a110  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000a115  mov     rcx, [r13+0]
0x18000a119  mov     rsi, rax
0x18000a11c  mov     [rsp+98h+var_78], rbx
0x18000a121  mov     [rsp+98h+var_68], rdi
0x18000a126  lea     r14, [rax+r14*8]
0x18000a12a  mov     [r14], rcx
0x18000a12d  lea     r12, [r14+8]
0x18000a131  mov     [rsp+98h+var_58], r12
0x18000a136  test    rcx, rcx
0x18000a139  jz      short loc_18000A144
0x18000a13b  add     rcx, 2Ch ; ','; this
0x18000a13f  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18000a144  mov     rdx, [rbx+8]
0x18000a148  mov     r8, rsi
0x18000a14b  mov     rcx, [rbx]
0x18000a14e  mov     [rsp+98h+var_60], r14
0x18000a153  cmp     rbp, rdx
0x18000a156  jz      short loc_18000A16F
0x18000a158  mov     rdx, rbp
0x18000a15b  call    ??$_Uninitialized_move@PEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@YAPEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@QEAV123@0PEAV123@AEAV?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@0@@Z; std::_Uninitialized_move<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> *,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>(Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> * const,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> * const,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> *,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>> &)
0x18000a160  mov     rdx, [rbx+8]
0x18000a164  mov     r8, r12
0x18000a167  mov     rcx, rbp
0x18000a16a  mov     [rsp+98h+var_60], rsi
0x18000a16f  call    ??$_Uninitialized_move@PEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@YAPEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@QEAV123@0PEAV123@AEAV?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@0@@Z; std::_Uninitialized_move<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> *,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>(Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> * const,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> * const,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> *,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>> &)
0x18000a174  mov     rcx, [rbx]
0x18000a177  mov     [rsp+98h+var_70], 0
0x18000a180  test    rcx, rcx
0x18000a183  jz      short loc_18000A1A1
0x18000a185  mov     rdx, [rbx+8]
0x18000a189  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>(Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> *,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> * const,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>> &)
0x18000a18e  mov     rdx, [rbx+10h]
0x18000a192  sub     rdx, [rbx]
0x18000a195  mov     rcx, [rbx]
0x18000a198  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000a19c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a1a1  mov     [rbx], rsi
0x18000a1a4  lea     rcx, [rsi+r15*8]
0x18000a1a8  mov     [rbx+8], rcx
0x18000a1ac  lea     rcx, [rsi+rdi*8]
0x18000a1b0  mov     [rbx+10h], rcx
0x18000a1b4  lea     rcx, [rsp+98h+var_78]
0x18000a1b9  call    ??1_Reallocation_guard@?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000a1be  mov     rax, r14
0x18000a1c1  add     rsp, 58h
0x18000a1c5  pop     r15
0x18000a1c7  pop     r14
0x18000a1c9  pop     r13
0x18000a1cb  pop     r12
0x18000a1cd  pop     rdi
0x18000a1ce  pop     rsi
0x18000a1cf  pop     rbp
0x18000a1d0  pop     rbx
0x18000a1d1  retn
0x18000a1d2  call    ?_Xlength@?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@CAXXZ; std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::_Xlength(void)
```
