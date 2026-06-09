# winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x180010e04`
- end: `0x180011028`
- name: `?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z`
- size: `548`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD)`
- caller_count: `33`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ed80`
- `0x18000f900`
- `0x180012178`
- `0x18001392c`
- `0x180015b38`
- `0x180015bec`
- `0x180018d08`
- `0x180018e1c`
- `0x180019c04`
- `0x180019d04`
- `0x18001a180`
- `0x18001a224`
- `0x18001a3a0`
- `0x18001a704`
- `0x18001cd3c`
- `0x18001d6d0`
- `0x18001e190`
- `0x18001e218`
- `0x18001e920`
- `0x18001eda4`
- `0x18002400c`
- `0x18002433c`
- `0x180025a00`
- `0x180026bb4`
- `0x180028528`
- `0x1800288d4`
- `0x1800294d0`
- `0x1800296e4`
- `0x18002a2a8`
- `0x18002c9d0`
- `0x18002dd5c`
- `0x18002de70`
- `0x18002e2c8`

## callees

- `0x18000395a`
- `0x180008004`
- `0x18000e678`
- `0x18000e6a0`
- `0x18000e6c8`
- `0x18000e6f0`
- `0x18000e718`
- `0x18000e740`
- `0x18000e988`
- `0x18000e9b0`
- `0x18000e9d8`
- `0x18000ea00`
- `0x18000ea28`
- `0x18000ea50`
- `0x18000ea78`
- `0x18000eaa0`
- `0x180010e04`
- `0x180033010`

## pseudocode

```c
void __fastcall __noreturn winrt::throw_hresult(unsigned int a1, unsigned int *a2, __int64 a3)
{
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-20h] BYREF
  void *retaddr; // [rsp+58h] [rbp+8h]

  if ( winrt_throw_hresult_handler )
    winrt_throw_hresult_handler(*a2, *((_QWORD *)a2 + 1), *((_QWORD *)a2 + 2), retaddr, a1);
  switch ( a1 )
  {
    case 0x8007000E:
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    case 0x80070005:
      winrt::hresult_access_denied::hresult_access_denied((__int64)pExceptionObject, (__int64)a2, (__int64)a2);
      throw (winrt::hresult_access_denied *)pExceptionObject;
    case 0x8001010E:
      winrt::hresult_wrong_thread::hresult_wrong_thread((__int64)pExceptionObject, (__int64)a2, (__int64)a2);
      throw (winrt::hresult_wrong_thread *)pExceptionObject;
    case 0x80004001:
      winrt::hresult_not_implemented::hresult_not_implemented(pExceptionObject, a2, a2);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    case 0x80070057:
      winrt::hresult_invalid_argument::hresult_invalid_argument(pExceptionObject, a2, a2);
      throw (winrt::hresult_invalid_argument *)pExceptionObject;
    case 0x8000000B:
      winrt::hresult_out_of_bounds::hresult_out_of_bounds(pExceptionObject, a2, a2);
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    case 0x80004002:
      winrt::hresult_no_interface::hresult_no_interface(pExceptionObject, a2, a2);
      throw (winrt::hresult_no_interface *)pExceptionObject;
    case 0x80040111:
      winrt::hresult_class_not_available::hresult_class_not_available(pExceptionObject, a2, a2);
      throw (winrt::hresult_class_not_available *)pExceptionObject;
    case 0x80040154:
      winrt::hresult_class_not_registered::hresult_class_not_registered(pExceptionObject, a2, a2);
      throw (winrt::hresult_class_not_registered *)pExceptionObject;
    case 0x8000000C:
      winrt::hresult_changed_state::hresult_changed_state(pExceptionObject, a2, a2);
      throw (winrt::hresult_changed_state *)pExceptionObject;
    case 0x8000000E:
      winrt::hresult_illegal_method_call::hresult_illegal_method_call(pExceptionObject, a2, a2);
      throw (winrt::hresult_illegal_method_call *)pExceptionObject;
    case 0x8000000D:
      winrt::hresult_illegal_state_change::hresult_illegal_state_change(pExceptionObject, a2, a2);
      throw (winrt::hresult_illegal_state_change *)pExceptionObject;
    case 0x80000018:
      winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(pExceptionObject, a2, a2);
      throw (winrt::hresult_illegal_delegate_assignment *)pExceptionObject;
    case 0x800704C7:
      winrt::hresult_canceled::hresult_canceled(pExceptionObject, a2, a2);
      throw (winrt::hresult_canceled *)pExceptionObject;
  }
  winrt::hresult_error::hresult_error((__int64)pExceptionObject, a1, a3, (__int64)a2);
  throw (winrt::hresult_error *)pExceptionObject;
}

```

## disassembly

```asm
0x180010e04  mov     [rsp-8+arg_0], rbx
0x180010e09  mov     [rsp-8+arg_8], rdi
0x180010e0e  push    rbp
0x180010e0f  mov     rbp, rsp
0x180010e12  sub     rsp, 50h
0x180010e16  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x180010e1d  mov     rdi, rdx
0x180010e20  mov     ebx, ecx
0x180010e22  test    rax, rax
0x180010e25  jz      short loc_180010E3E
0x180010e27  mov     r8, [rdx+10h]
0x180010e2b  mov     rdx, [rdx+8]
0x180010e2f  mov     r9, [rbp+8]
0x180010e33  mov     [rsp+50h+var_30], ecx
0x180010e37  mov     ecx, [rdi]
0x180010e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e3e  lea     rcx, [rbp+pExceptionObject]; this
0x180010e42  cmp     ebx, 8007000Eh
0x180010e48  jnz     short loc_180010E60
0x180010e4a  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180010e4f  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180010e56  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010e5a  call    _CxxThrowException_0
0x180010e60  cmp     ebx, 80070005h
0x180010e66  jnz     short loc_180010E81
0x180010e68  mov     r8, rdi
0x180010e6b  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180010e70  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x180010e77  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010e7b  call    _CxxThrowException_0
0x180010e81  cmp     ebx, 8001010Eh
0x180010e87  jnz     short loc_180010EA2
0x180010e89  mov     r8, rdi
0x180010e8c  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180010e91  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x180010e98  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010e9c  call    _CxxThrowException_0
0x180010ea2  cmp     ebx, 80004001h
0x180010ea8  jnz     short loc_180010EC3
0x180010eaa  mov     r8, rdi
0x180010ead  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180010eb2  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180010eb9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010ebd  call    _CxxThrowException_0
0x180010ec3  cmp     ebx, 80070057h
0x180010ec9  jnz     short loc_180010EE4
0x180010ecb  mov     r8, rdi
0x180010ece  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180010ed3  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180010eda  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010ede  call    _CxxThrowException_0
0x180010ee4  cmp     ebx, 8000000Bh
0x180010eea  jnz     short loc_180010F05
0x180010eec  mov     r8, rdi
0x180010eef  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180010ef4  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180010efb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010eff  call    _CxxThrowException_0
0x180010f05  cmp     ebx, 80004002h
0x180010f0b  jnz     short loc_180010F26
0x180010f0d  mov     r8, rdi
0x180010f10  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180010f15  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x180010f1c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010f20  call    _CxxThrowException_0
0x180010f26  cmp     ebx, 80040111h
0x180010f2c  jnz     short loc_180010F47
0x180010f2e  mov     r8, rdi
0x180010f31  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180010f36  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x180010f3d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010f41  call    _CxxThrowException_0
0x180010f47  cmp     ebx, 80040154h
0x180010f4d  jnz     short loc_180010F68
0x180010f4f  mov     r8, rdi
0x180010f52  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180010f57  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x180010f5e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010f62  call    _CxxThrowException_0
0x180010f68  cmp     ebx, 8000000Ch
0x180010f6e  jnz     short loc_180010F89
0x180010f70  mov     r8, rdi
0x180010f73  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180010f78  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180010f7f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010f83  call    _CxxThrowException_0
0x180010f89  cmp     ebx, 8000000Eh
0x180010f8f  jnz     short loc_180010FAA
0x180010f91  mov     r8, rdi
0x180010f94  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180010f99  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x180010fa0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010fa4  call    _CxxThrowException_0
0x180010faa  cmp     ebx, 8000000Dh
0x180010fb0  jnz     short loc_180010FCB
0x180010fb2  mov     r8, rdi
0x180010fb5  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180010fba  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x180010fc1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010fc5  call    _CxxThrowException_0
0x180010fcb  cmp     ebx, 80000018h
0x180010fd1  jnz     short loc_180010FEC
0x180010fd3  mov     r8, rdi
0x180010fd6  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180010fdb  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x180010fe2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010fe6  call    _CxxThrowException_0
0x180010fec  cmp     ebx, 800704C7h
0x180010ff2  jnz     short loc_18001100D
0x180010ff4  mov     r8, rdi
0x180010ff7  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180010ffc  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180011003  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011007  call    _CxxThrowException_0
0x18001100d  mov     r9, rdi
0x180011010  mov     edx, ebx
0x180011012  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011017  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18001101e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011022  call    _CxxThrowException_0
```
