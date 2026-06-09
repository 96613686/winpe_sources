# std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>::reserve(unsigned __int64)

- ea: `0x18000dabc`
- end: `0x18000db5b`
- name: `?reserve@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAAX_K@Z`
- size: `159`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c0f0`

## callees

- `0x180004958`
- `0x180008be0`
- `0x180009d6c`
- `0x180009dc4`
- `0x18000aa94`
- `0x18000d2a8`
- `0x18000dabc`

## pseudocode

```c
unsigned __int64 __fastcall std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::reserve(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 result; // rax
  __int64 v5; // rdi
  __int64 size_of; // rax
  __int64 v7; // rbx
  _QWORD v8[9]; // [rsp+20h] [rbp-48h] BYREF

  result = (__int64)(a1[2] - *a1) >> 3;
  if ( a2 > result )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector too long");
    v5 = (__int64)(a1[1] - *a1) >> 3;
    size_of = std::_Get_size_of_n<8>(a2);
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    std::_Uninitialized_move<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(
      *a1,
      a1[1],
      v7);
    std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Change_array(
      a1,
      v7,
      v5,
      a2,
      a1,
      0,
      a2,
      v8[3],
      v8[4]);
    return std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Simple_reallocation_guard::~_Simple_reallocation_guard(v8);
  }
  return result;
}

```

## disassembly

```asm
0x18000dabc  push    rbx
0x18000dabe  push    rbp
0x18000dabf  push    rsi
0x18000dac0  push    rdi
0x18000dac1  sub     rsp, 48h
0x18000dac5  mov     rax, [rcx+10h]
0x18000dac9  mov     rbp, rdx
0x18000dacc  sub     rax, [rcx]
0x18000dacf  mov     rsi, rcx
0x18000dad2  sar     rax, 3
0x18000dad6  cmp     rdx, rax
0x18000dad9  jbe     short loc_18000DB52
0x18000dadb  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000dae5  cmp     rdx, rax
0x18000dae8  jbe     short loc_18000DAF7
0x18000daea  lea     rcx, aVectorTooLong; "vector too long"
0x18000daf1  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000daf7  mov     rdi, [rcx+8]
0x18000dafb  sub     rdi, [rcx]
0x18000dafe  mov     rcx, rbp
0x18000db01  sar     rdi, 3
0x18000db05  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18000db0a  mov     rcx, rax
0x18000db0d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000db12  mov     rdx, [rsi+8]
0x18000db16  mov     r8, rax
0x18000db19  mov     rcx, [rsi]
0x18000db1c  mov     rbx, rax
0x18000db1f  mov     [rsp+68h+var_48], rsi
0x18000db24  mov     [rsp+68h+var_38], rbp
0x18000db29  call    ??$_Uninitialized_move@PEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV12@0PEAV12@AEAV?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@0@@Z; std::_Uninitialized_move<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> &)
0x18000db2e  mov     r9, rbp
0x18000db31  mov     [rsp+68h+var_40], 0
0x18000db3a  mov     r8, rdi
0x18000db3d  mov     rdx, rbx
0x18000db40  mov     rcx, rsi
0x18000db43  call    ?_Change_array@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAXQEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@_K1@Z; std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Change_array(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,unsigned __int64,unsigned __int64)
0x18000db48  lea     rcx, [rsp+68h+var_48]
0x18000db4d  call    ??1_Simple_reallocation_guard@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Simple_reallocation_guard::~_Simple_reallocation_guard(void)
0x18000db52  add     rsp, 48h
0x18000db56  pop     rdi
0x18000db57  pop     rsi
0x18000db58  pop     rbp
0x18000db59  pop     rbx
0x18000db5a  retn
```
