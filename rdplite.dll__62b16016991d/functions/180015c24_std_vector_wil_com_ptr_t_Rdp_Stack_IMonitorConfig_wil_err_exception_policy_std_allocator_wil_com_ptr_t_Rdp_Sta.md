# std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>::_Emplace_reallocate<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> const &>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> const &)

- ea: `0x180015c24`
- end: `0x180015d22`
- name: `??$_Emplace_reallocate@AEBV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV23@AEBV23@@Z`
- size: `254`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016304`

## callees

- `0x180004958`
- `0x180008be0`
- `0x180009d6c`
- `0x180009dc4`
- `0x18000a0e4`
- `0x18000aa58`
- `0x18000d218`
- `0x18000d2a8`
- `0x180015c24`

## pseudocode

```c
_QWORD *__fastcall std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> const &>(
        _QWORD *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rbp
  __int64 v6; // rax
  __int64 v8; // r15
  __int64 v9; // r14
  __int64 size_of; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdi
  _QWORD *v14; // rbp
  __int64 v15; // rdx
  _QWORD *v16; // r8
  __int64 v17; // rcx
  _QWORD *v19; // [rsp+20h] [rbp-78h] BYREF
  __int64 v20; // [rsp+30h] [rbp-68h]
  _QWORD *v21; // [rsp+38h] [rbp-60h]
  _QWORD *v22; // [rsp+40h] [rbp-58h]

  v3 = *a1;
  v6 = (__int64)(a1[1] - *a1) >> 3;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v8 = v6 + 1;
  v9 = std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Calculate_growth(a1, v6 + 1);
  size_of = std::_Get_size_of_n<8>(v9);
  v11 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v12 = *a3;
  v19 = a1;
  v13 = v11;
  v20 = v9;
  v14 = (_QWORD *)(v11 + 8 * ((a2 - v3) >> 3));
  v22 = v14 + 1;
  wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
    v14,
    v12);
  v15 = a1[1];
  v16 = (_QWORD *)v13;
  v17 = *a1;
  v21 = v14;
  if ( a2 != v15 )
  {
    std::_Uninitialized_move<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(
      v17,
      a2,
      v13);
    v15 = a1[1];
    v16 = v14 + 1;
    v17 = a2;
    v21 = (_QWORD *)v13;
  }
  std::_Uninitialized_move<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(
    v17,
    v15,
    v16);
  std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Change_array(
    a1,
    v13,
    v8,
    v9,
    v19,
    0,
    v20,
    v21,
    v22);
  std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Reallocation_guard::~_Reallocation_guard(&v19);
  return v14;
}

```

## disassembly

```asm
0x180015c24  push    rbx
0x180015c26  push    rbp
0x180015c27  push    rsi
0x180015c28  push    rdi
0x180015c29  push    r12
0x180015c2b  push    r13
0x180015c2d  push    r14
0x180015c2f  push    r15
0x180015c31  sub     rsp, 58h
0x180015c35  mov     rbp, [rcx]
0x180015c38  mov     rbx, rcx
0x180015c3b  mov     rax, [rcx+8]
0x180015c3f  mov     r13, r8
0x180015c42  sub     rax, rbp
0x180015c45  mov     rcx, 1FFFFFFFFFFFFFFFh
0x180015c4f  sar     rax, 3
0x180015c53  mov     rsi, rdx
0x180015c56  cmp     rax, rcx
0x180015c59  jnz     short loc_180015C68
0x180015c5b  lea     rcx, aVectorTooLong; "vector too long"
0x180015c62  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180015c68  lea     r15, [rax+1]
0x180015c6c  mov     rcx, rbx
0x180015c6f  mov     rdx, r15
0x180015c72  call    ?_Calculate_growth@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEBA_K_K@Z; std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Calculate_growth(unsigned __int64)
0x180015c77  mov     rcx, rax
0x180015c7a  mov     r14, rax
0x180015c7d  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x180015c82  mov     rcx, rax
0x180015c85  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180015c8a  mov     rdx, [r13+0]
0x180015c8e  mov     rcx, rsi
0x180015c91  sub     rcx, rbp
0x180015c94  mov     [rsp+98h+var_78], rbx
0x180015c99  sar     rcx, 3
0x180015c9d  mov     rdi, rax
0x180015ca0  mov     [rsp+98h+var_68], r14
0x180015ca5  lea     rbp, [rax+rcx*8]
0x180015ca9  lea     r12, [rbp+8]
0x180015cad  mov     rcx, rbp
0x180015cb0  mov     [rsp+98h+var_58], r12
0x180015cb5  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180015cba  mov     rdx, [rbx+8]
0x180015cbe  mov     r8, rdi
0x180015cc1  mov     rcx, [rbx]
0x180015cc4  mov     [rsp+98h+var_60], rbp
0x180015cc9  cmp     rsi, rdx
0x180015ccc  jz      short loc_180015CE5
0x180015cce  mov     rdx, rsi
0x180015cd1  call    ??$_Uninitialized_move@PEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV12@0PEAV12@AEAV?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@0@@Z; std::_Uninitialized_move<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> &)
0x180015cd6  mov     rdx, [rbx+8]
0x180015cda  mov     r8, r12
0x180015cdd  mov     rcx, rsi
0x180015ce0  mov     [rsp+98h+var_60], rdi
0x180015ce5  call    ??$_Uninitialized_move@PEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV12@0PEAV12@AEAV?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@0@@Z; std::_Uninitialized_move<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> &)
0x180015cea  mov     r9, r14
0x180015ced  mov     [rsp+98h+var_70], 0
0x180015cf6  mov     r8, r15
0x180015cf9  mov     rdx, rdi
0x180015cfc  mov     rcx, rbx
0x180015cff  call    ?_Change_array@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAXQEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@_K1@Z; std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Change_array(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,unsigned __int64,unsigned __int64)
0x180015d04  lea     rcx, [rsp+98h+var_78]
0x180015d09  call    ??1_Reallocation_guard@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180015d0e  mov     rax, rbp
0x180015d11  add     rsp, 58h
0x180015d15  pop     r15
0x180015d17  pop     r14
0x180015d19  pop     r13
0x180015d1b  pop     r12
0x180015d1d  pop     rdi
0x180015d1e  pop     rsi
0x180015d1f  pop     rbp
0x180015d20  pop     rbx
0x180015d21  retn
```
