# std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>::_Emplace_reallocate<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> &&)

- ea: `0x180009bc0`
- end: `0x180009cc1`
- name: `??$_Emplace_reallocate@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV23@$$QEAV23@@Z`
- size: `257`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c0f0`
- `0x180019894`

## callees

- `0x180004958`
- `0x180008be0`
- `0x180009bc0`
- `0x180009d6c`
- `0x180009dc4`
- `0x18000aa58`
- `0x18000d218`
- `0x18000d2a8`

## pseudocode

```c
__int64 __fastcall std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>(
        _QWORD *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rbp
  __int64 v6; // rax
  __int64 v8; // r13
  __int64 v9; // r15
  __int64 size_of; // rax
  __int64 v11; // rdi
  _QWORD *v12; // r8
  _QWORD *v13; // r14
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  _QWORD *v18; // [rsp+20h] [rbp-78h] BYREF
  __int64 v19; // [rsp+30h] [rbp-68h]
  _QWORD *v20; // [rsp+38h] [rbp-60h]
  _QWORD *v21; // [rsp+40h] [rbp-58h]

  v3 = *a1;
  v6 = (__int64)(a1[1] - *a1) >> 3;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v8 = v6 + 1;
  v9 = std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Calculate_growth(a1, v6 + 1);
  size_of = std::_Get_size_of_n<8>(v9);
  v18 = a1;
  v19 = v9;
  v11 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v12 = (_QWORD *)v11;
  v13 = (_QWORD *)(v11 + 8 * ((a2 - v3) >> 3));
  v14 = *a3;
  *a3 = 0;
  *v13 = v14;
  v15 = a1[1];
  v16 = *a1;
  v21 = v13 + 1;
  v20 = v13;
  if ( a2 != v15 )
  {
    std::_Uninitialized_move<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(
      v16,
      a2,
      v11);
    v15 = a1[1];
    v12 = v13 + 1;
    v16 = a2;
    v20 = (_QWORD *)v11;
  }
  std::_Uninitialized_move<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(
    v16,
    v15,
    v12);
  std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Change_array(
    a1,
    v11,
    v8,
    v9,
    v18,
    0,
    v19,
    v20,
    v21);
  std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Reallocation_guard::~_Reallocation_guard(&v18);
  return v11 + 8 * ((a2 - v3) >> 3);
}

```

## disassembly

```asm
0x180009bc0  push    rbx
0x180009bc2  push    rbp
0x180009bc3  push    rsi
0x180009bc4  push    rdi
0x180009bc5  push    r12
0x180009bc7  push    r13
0x180009bc9  push    r14
0x180009bcb  push    r15
0x180009bcd  sub     rsp, 58h
0x180009bd1  mov     rbp, [rcx]
0x180009bd4  mov     rbx, rcx
0x180009bd7  mov     rax, [rcx+8]
0x180009bdb  mov     r12, r8
0x180009bde  sub     rax, rbp
0x180009be1  mov     rcx, 1FFFFFFFFFFFFFFFh
0x180009beb  sar     rax, 3
0x180009bef  mov     rsi, rdx
0x180009bf2  cmp     rax, rcx
0x180009bf5  jnz     short loc_180009C04
0x180009bf7  lea     rcx, aVectorTooLong; "vector too long"
0x180009bfe  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180009c04  lea     r13, [rax+1]
0x180009c08  mov     rcx, rbx
0x180009c0b  mov     rdx, r13
0x180009c0e  call    ?_Calculate_growth@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEBA_K_K@Z; std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Calculate_growth(unsigned __int64)
0x180009c13  mov     rcx, rax
0x180009c16  mov     r15, rax
0x180009c19  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x180009c1e  mov     rcx, rax
0x180009c21  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180009c26  mov     rcx, rsi
0x180009c29  mov     [rsp+98h+var_78], rbx
0x180009c2e  sub     rcx, rbp
0x180009c31  mov     [rsp+98h+var_68], r15
0x180009c36  sar     rcx, 3
0x180009c3a  mov     rdi, rax
0x180009c3d  mov     r8, rax
0x180009c40  lea     r14, [rax+rcx*8]
0x180009c44  mov     rcx, [r12]
0x180009c48  mov     qword ptr [r12], 0
0x180009c50  lea     rbp, [r14+8]
0x180009c54  mov     [r14], rcx
0x180009c57  mov     rdx, [rbx+8]
0x180009c5b  mov     rcx, [rbx]
0x180009c5e  mov     [rsp+98h+var_58], rbp
0x180009c63  mov     [rsp+98h+var_60], r14
0x180009c68  cmp     rsi, rdx
0x180009c6b  jz      short loc_180009C84
0x180009c6d  mov     rdx, rsi
0x180009c70  call    ??$_Uninitialized_move@PEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV12@0PEAV12@AEAV?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@0@@Z; std::_Uninitialized_move<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> &)
0x180009c75  mov     rdx, [rbx+8]
0x180009c79  mov     r8, rbp
0x180009c7c  mov     rcx, rsi
0x180009c7f  mov     [rsp+98h+var_60], rdi
0x180009c84  call    ??$_Uninitialized_move@PEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV12@0PEAV12@AEAV?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@0@@Z; std::_Uninitialized_move<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> &)
0x180009c89  mov     r9, r15
0x180009c8c  mov     [rsp+98h+var_70], 0
0x180009c95  mov     r8, r13
0x180009c98  mov     rdx, rdi
0x180009c9b  mov     rcx, rbx
0x180009c9e  call    ?_Change_array@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAXQEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@_K1@Z; std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Change_array(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,unsigned __int64,unsigned __int64)
0x180009ca3  lea     rcx, [rsp+98h+var_78]
0x180009ca8  call    ??1_Reallocation_guard@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180009cad  mov     rax, r14
0x180009cb0  add     rsp, 58h
0x180009cb4  pop     r15
0x180009cb6  pop     r14
0x180009cb8  pop     r13
0x180009cba  pop     r12
0x180009cbc  pop     rdi
0x180009cbd  pop     rsi
0x180009cbe  pop     rbp
0x180009cbf  pop     rbx
0x180009cc0  retn
```
