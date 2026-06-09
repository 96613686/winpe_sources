# std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::_Emplace_reallocate<Microsoft::IoT::ShellExtension::CCBT>(Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT &&)

- ea: `0x18000fae0`
- end: `0x18000fc10`
- name: `??$_Emplace_reallocate@VCCBT@ShellExtension@IoT@Microsoft@@@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV2345@$$QEAV2345@@Z`
- size: `304`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f968`

## callees

- `0x180009ebc`
- `0x18000c548`
- `0x18000c6b8`
- `0x18000fae0`
- `0x18000fc68`
- `0x18000fcd4`
- `0x180010070`
- `0x180010948`
- `0x180014e8c`
- `0x180014ed4`

## pseudocode

```c
_QWORD *__fastcall std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Emplace_reallocate<Microsoft::IoT::ShellExtension::CCBT>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r15
  __int64 v7; // rax
  __int64 v8; // r14
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // r10
  _QWORD *v12; // rdi
  _QWORD *v13; // r15
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *v17; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v18; // [rsp+28h] [rbp-70h]
  unsigned __int64 v19; // [rsp+30h] [rbp-68h]
  _QWORD *v20; // [rsp+38h] [rbp-60h]
  _QWORD *v21; // [rsp+40h] [rbp-58h]

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
  v13 = &v12[11 * ((a2 - v6) / 88)];
  v17 = a1;
  v18 = v12;
  v19 = v10;
  v21 = v13 + 11;
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
    v20 = v12;
    std::_Uninitialized_move<Microsoft::IoT::ShellExtension::CCBT *>(a2, a1[1], v13 + 11);
  }
  v18 = 0;
  std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Change_array(a1, v12, v8, v10);
  std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Reallocation_guard::~_Reallocation_guard(&v17);
  return v13;
}

```

## disassembly

```asm
0x18000fae0  push    rbx
0x18000fae2  push    rbp
0x18000fae3  push    rsi
0x18000fae4  push    rdi
0x18000fae5  push    r12
0x18000fae7  push    r13
0x18000fae9  push    r14
0x18000faeb  push    r15
0x18000faed  sub     rsp, 58h
0x18000faf1  mov     r13, r8
0x18000faf4  mov     rbp, rdx
0x18000faf7  mov     rbx, rcx
0x18000fafa  mov     r15, [rcx]
0x18000fafd  mov     rax, [rcx+8]
0x18000fb01  sub     rax, r15
0x18000fb04  sar     rax, 3
0x18000fb08  mov     r12, 2E8BA2E8BA2E8BA3h
0x18000fb12  imul    rax, r12
0x18000fb16  mov     r10, 2E8BA2E8BA2E8BAh
0x18000fb20  cmp     rax, r10
0x18000fb23  jz      loc_18000FC0A
0x18000fb29  lea     r14, [rax+1]
0x18000fb2d  mov     rdx, r14
0x18000fb30  call    ?_Calculate_growth@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEBA_K_K@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Calculate_growth(unsigned __int64)
0x18000fb35  mov     rsi, rax
0x18000fb38  cmp     rax, r10
0x18000fb3b  ja      loc_18000FC04
0x18000fb41  imul    rcx, rsi, 58h ; 'X'
0x18000fb45  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000fb4a  mov     rdi, rax
0x18000fb4d  mov     rcx, rbp
0x18000fb50  sub     rcx, r15
0x18000fb53  mov     rax, r12
0x18000fb56  imul    rcx
0x18000fb59  sar     rdx, 4
0x18000fb5d  mov     rcx, rdx
0x18000fb60  shr     rcx, 3Fh
0x18000fb64  add     rdx, rcx
0x18000fb67  imul    r15, rdx, 58h ; 'X'
0x18000fb6b  add     r15, rdi
0x18000fb6e  lea     r12, [r15+58h]
0x18000fb72  mov     [rsp+98h+var_78], rbx
0x18000fb77  mov     [rsp+98h+var_70], rdi
0x18000fb7c  mov     [rsp+98h+var_68], rsi
0x18000fb81  mov     [rsp+98h+var_58], r12
0x18000fb86  mov     rdx, r13
0x18000fb89  mov     rcx, r15
0x18000fb8c  call    ??0CCBT@ShellExtension@IoT@Microsoft@@QEAA@$$QEAV0123@@Z; Microsoft::IoT::ShellExtension::CCBT::CCBT(Microsoft::IoT::ShellExtension::CCBT &&)
0x18000fb91  mov     [rsp+98h+var_60], r15
0x18000fb96  mov     rdx, [rbx+8]
0x18000fb9a  mov     r8, rdi
0x18000fb9d  mov     rcx, [rbx]
0x18000fba0  cmp     rbp, rdx
0x18000fba3  jnz     short loc_18000FBAF
0x18000fba5  mov     r9, rbx
0x18000fba8  call    ??$_Uninitialized_copy@PEAVCCBT@ShellExtension@IoT@Microsoft@@PEAV1234@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAPEAVCCBT@ShellExtension@IoT@Microsoft@@PEAV1234@00AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Uninitialized_copy<Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x18000fbad  jmp     short loc_18000FBCB
0x18000fbaf  mov     rdx, rbp
0x18000fbb2  call    ??$_Uninitialized_move@PEAVCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@0PEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Uninitialized_move<Microsoft::IoT::ShellExtension::CCBT *>(Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x18000fbb7  mov     [rsp+98h+var_60], rdi
0x18000fbbc  mov     r8, r12
0x18000fbbf  mov     rdx, [rbx+8]
0x18000fbc3  mov     rcx, rbp
0x18000fbc6  call    ??$_Uninitialized_move@PEAVCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@0PEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Uninitialized_move<Microsoft::IoT::ShellExtension::CCBT *>(Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x18000fbcb  mov     [rsp+98h+var_70], 0
0x18000fbd4  mov     r9, rsi
0x18000fbd7  mov     r8, r14
0x18000fbda  mov     rdx, rdi
0x18000fbdd  mov     rcx, rbx
0x18000fbe0  call    ?_Change_array@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAXQEAVCCBT@ShellExtension@IoT@Microsoft@@_K1@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Change_array(Microsoft::IoT::ShellExtension::CCBT * const,unsigned __int64,unsigned __int64)
0x18000fbe5  nop
0x18000fbe6  lea     rcx, [rsp+98h+var_78]
0x18000fbeb  call    ??1_Reallocation_guard@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000fbf0  mov     rax, r15
0x18000fbf3  add     rsp, 58h
0x18000fbf7  pop     r15
0x18000fbf9  pop     r14
0x18000fbfb  pop     r13
0x18000fbfd  pop     r12
0x18000fbff  pop     rdi
0x18000fc00  pop     rsi
0x18000fc01  pop     rbp
0x18000fc02  pop     rbx
0x18000fc03  retn
0x18000fc04  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18000fc0a  call    ?_Xlength@?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@CAXXZ; std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::_Xlength(void)
```
