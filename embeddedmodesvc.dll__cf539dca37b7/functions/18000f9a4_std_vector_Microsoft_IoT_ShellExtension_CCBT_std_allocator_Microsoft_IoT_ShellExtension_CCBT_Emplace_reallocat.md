# std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::_Emplace_reallocate<Microsoft::IoT::ShellExtension::CCBT const &>(Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT const &)

- ea: `0x18000f9a4`
- end: `0x18000fad9`
- name: `??$_Emplace_reallocate@AEBVCCBT@ShellExtension@IoT@Microsoft@@@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV2345@AEBV2345@@Z`
- size: `309`
- prototype: `Microsoft::IoT::ShellExtension::CCBT *__fastcall(_QWORD *, __int64, const struct Microsoft::IoT::ShellExtension::CCBT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000fddc`

## callees

- `0x180009ebc`
- `0x18000c548`
- `0x18000c6b8`
- `0x18000f9a4`
- `0x18000fc68`
- `0x18000fcd4`
- `0x180010100`
- `0x180010948`
- `0x180014e8c`
- `0x180014ed4`

## pseudocode

```c
Microsoft::IoT::ShellExtension::CCBT *__fastcall std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Emplace_reallocate<Microsoft::IoT::ShellExtension::CCBT const &>(
        _QWORD *a1,
        __int64 a2,
        const struct Microsoft::IoT::ShellExtension::CCBT *a3)
{
  __int64 v6; // r15
  __int64 v7; // rax
  __int64 v8; // r14
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // r10
  _QWORD *v12; // rdi
  Microsoft::IoT::ShellExtension::CCBT *v13; // r15
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *v17; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v18; // [rsp+28h] [rbp-70h]
  unsigned __int64 v19; // [rsp+30h] [rbp-68h]
  Microsoft::IoT::ShellExtension::CCBT *v20; // [rsp+38h] [rbp-60h]
  char *v21; // [rsp+40h] [rbp-58h]

  v6 = *a1;
  v7 = 0x2E8BA2E8BA2E8BA3LL * ((__int64)(a1[1] - *a1) >> 3);
  if ( v7 == 0x2E8BA2E8BA2E8BALL )
    std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::_Xlength();
  v8 = v7 + 1;
  v9 = std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Calculate_growth(a1, v7 + 1);
  v10 = v9;
  if ( v9 > v11 )
    std::_Throw_bad_array_new_length();
  v12 = std::_Allocate<16,std::_Default_allocate_traits>(88 * v9);
  v13 = (Microsoft::IoT::ShellExtension::CCBT *)&v12[11 * ((a2 - v6) / 88)];
  v17 = a1;
  v18 = v12;
  v19 = v10;
  v21 = (char *)v13 + 88;
  Microsoft::IoT::ShellExtension::CCBT::CCBT(v13, a3);
  v20 = v13;
  v14 = a1[1];
  v15 = *a1;
  if ( a2 == v14 )
  {
    std::_Uninitialized_copy<Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(
      v15,
      v14,
      v12,
      a1,
      v17,
      v18,
      v19,
      v20,
      v21);
  }
  else
  {
    std::_Uninitialized_move<Microsoft::IoT::ShellExtension::CCBT *>(v15, a2, v12);
    v20 = (Microsoft::IoT::ShellExtension::CCBT *)v12;
    std::_Uninitialized_move<Microsoft::IoT::ShellExtension::CCBT *>(a2, a1[1], (char *)v13 + 88);
  }
  v18 = 0;
  std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Change_array(a1, v12, v8, v10);
  std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Reallocation_guard::~_Reallocation_guard(&v17);
  return v13;
}

```

## disassembly

```asm
0x18000f9a4  push    rbx
0x18000f9a6  push    rbp
0x18000f9a7  push    rsi
0x18000f9a8  push    rdi
0x18000f9a9  push    r12
0x18000f9ab  push    r13
0x18000f9ad  push    r14
0x18000f9af  push    r15
0x18000f9b1  sub     rsp, 58h
0x18000f9b5  mov     r13, r8
0x18000f9b8  mov     rbp, rdx
0x18000f9bb  mov     rbx, rcx
0x18000f9be  mov     r15, [rcx]
0x18000f9c1  mov     rax, [rcx+8]
0x18000f9c5  sub     rax, r15
0x18000f9c8  sar     rax, 3
0x18000f9cc  mov     r12, 2E8BA2E8BA2E8BA3h
0x18000f9d6  imul    rax, r12
0x18000f9da  mov     r10, 2E8BA2E8BA2E8BAh
0x18000f9e4  cmp     rax, r10
0x18000f9e7  jz      loc_18000FAD3
0x18000f9ed  lea     r14, [rax+1]
0x18000f9f1  mov     rdx, r14
0x18000f9f4  call    ?_Calculate_growth@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEBA_K_K@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Calculate_growth(unsigned __int64)
0x18000f9f9  mov     rsi, rax
0x18000f9fc  cmp     rax, r10
0x18000f9ff  ja      loc_18000FACD
0x18000fa05  imul    rcx, rsi, 58h ; 'X'
0x18000fa09  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000fa0e  mov     rdi, rax
0x18000fa11  mov     rcx, rbp
0x18000fa14  sub     rcx, r15
0x18000fa17  mov     rax, r12
0x18000fa1a  imul    rcx
0x18000fa1d  sar     rdx, 4
0x18000fa21  mov     rcx, rdx
0x18000fa24  shr     rcx, 3Fh
0x18000fa28  add     rdx, rcx
0x18000fa2b  imul    r15, rdx, 58h ; 'X'
0x18000fa2f  add     r15, rdi
0x18000fa32  lea     r12, [r15+58h]
0x18000fa36  mov     [rsp+98h+var_78], rbx
0x18000fa3b  mov     [rsp+98h+var_70], rdi
0x18000fa40  mov     [rsp+98h+var_68], rsi
0x18000fa45  mov     [rsp+98h+var_60], r12
0x18000fa4a  mov     [rsp+98h+var_58], r12
0x18000fa4f  mov     rdx, r13; struct Microsoft::IoT::ShellExtension::CCBT *
0x18000fa52  mov     rcx, r15; this
0x18000fa55  call    ??0CCBT@ShellExtension@IoT@Microsoft@@QEAA@AEBV0123@@Z; Microsoft::IoT::ShellExtension::CCBT::CCBT(Microsoft::IoT::ShellExtension::CCBT const &)
0x18000fa5a  mov     [rsp+98h+var_60], r15
0x18000fa5f  mov     rdx, [rbx+8]
0x18000fa63  mov     r8, rdi
0x18000fa66  mov     rcx, [rbx]
0x18000fa69  cmp     rbp, rdx
0x18000fa6c  jnz     short loc_18000FA78
0x18000fa6e  mov     r9, rbx
0x18000fa71  call    ??$_Uninitialized_copy@PEAVCCBT@ShellExtension@IoT@Microsoft@@PEAV1234@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAPEAVCCBT@ShellExtension@IoT@Microsoft@@PEAV1234@00AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Uninitialized_copy<Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x18000fa76  jmp     short loc_18000FA94
0x18000fa78  mov     rdx, rbp
0x18000fa7b  call    ??$_Uninitialized_move@PEAVCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@0PEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Uninitialized_move<Microsoft::IoT::ShellExtension::CCBT *>(Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x18000fa80  mov     [rsp+98h+var_60], rdi
0x18000fa85  mov     r8, r12
0x18000fa88  mov     rdx, [rbx+8]
0x18000fa8c  mov     rcx, rbp
0x18000fa8f  call    ??$_Uninitialized_move@PEAVCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@0PEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Uninitialized_move<Microsoft::IoT::ShellExtension::CCBT *>(Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x18000fa94  mov     [rsp+98h+var_70], 0
0x18000fa9d  mov     r9, rsi
0x18000faa0  mov     r8, r14
0x18000faa3  mov     rdx, rdi
0x18000faa6  mov     rcx, rbx
0x18000faa9  call    ?_Change_array@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAXQEAVCCBT@ShellExtension@IoT@Microsoft@@_K1@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Change_array(Microsoft::IoT::ShellExtension::CCBT * const,unsigned __int64,unsigned __int64)
0x18000faae  nop
0x18000faaf  lea     rcx, [rsp+98h+var_78]
0x18000fab4  call    ??1_Reallocation_guard@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000fab9  mov     rax, r15
0x18000fabc  add     rsp, 58h
0x18000fac0  pop     r15
0x18000fac2  pop     r14
0x18000fac4  pop     r13
0x18000fac6  pop     r12
0x18000fac8  pop     rdi
0x18000fac9  pop     rsi
0x18000faca  pop     rbp
0x18000facb  pop     rbx
0x18000facc  retn
0x18000facd  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18000fad3  call    ?_Xlength@?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@CAXXZ; std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::_Xlength(void)
```
