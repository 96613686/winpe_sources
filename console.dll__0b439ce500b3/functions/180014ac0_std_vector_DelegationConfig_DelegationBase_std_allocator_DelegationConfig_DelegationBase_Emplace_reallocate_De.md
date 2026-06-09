# std::vector<DelegationConfig::DelegationBase,std::allocator<DelegationConfig::DelegationBase>>::_Emplace_reallocate<DelegationConfig::DelegationBase>(DelegationConfig::DelegationBase * const,DelegationConfig::DelegationBase &&)

- ea: `0x180014ac0`
- end: `0x180014c17`
- name: `??$_Emplace_reallocate@UDelegationBase@DelegationConfig@@@?$vector@UDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@AEAAPEAUDelegationBase@DelegationConfig@@QEAU23@$$QEAU23@@Z`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180015880`

## callees

- `0x18000d7c8`
- `0x18000eaf0`
- `0x180014ac0`
- `0x180014dc0`
- `0x180014e80`
- `0x1800151ac`
- `0x1800156f8`
- `0x180015860`

## pseudocode

```c
__int64 __fastcall std::vector<DelegationConfig::DelegationBase>::_Emplace_reallocate<DelegationConfig::DelegationBase>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r15
  __int64 v5; // rbx
  unsigned __int64 v7; // rax
  unsigned __int64 v9; // rbp
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  __int64 v13; // rsi
  __int64 v14; // r15
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  _QWORD v19[3]; // [rsp+20h] [rbp-78h] BYREF
  __int64 v20; // [rsp+38h] [rbp-60h]
  __int64 v21; // [rsp+40h] [rbp-58h]

  v3 = *a1;
  v5 = 0x1AF286BCA1AF286LL;
  v7 = 0x86BCA1AF286BCA1BuLL * ((a1[1] - *a1) >> 3);
  if ( v7 == 0x1AF286BCA1AF286LL )
    std::vector<DelegationConfig::DelegationBase>::_Xlength();
  v9 = v7 + 1;
  v10 = 0x86BCA1AF286BCA1BuLL * ((a1[2] - v3) >> 3);
  if ( v10 <= 0x1AF286BCA1AF286LL - (v10 >> 1) )
  {
    v11 = (v10 >> 1) + v10;
    v12 = v9;
    if ( v11 >= v9 )
      v12 = v11;
    if ( v12 > 0x1AF286BCA1AF286LL )
      std::_Throw_bad_array_new_length();
    v5 = v12;
  }
  v13 = std::_Allocate<16,std::_Default_allocate_traits>(152 * v5);
  v19[0] = a1;
  v19[2] = v5;
  v14 = v13 + 152 * ((a2 - v3) / 152);
  v21 = v14 + 152;
  std::construct_at<DelegationConfig::DelegationBase,DelegationConfig::DelegationBase>(v14, a3);
  v15 = a1[1];
  v16 = v13;
  v17 = *a1;
  v20 = v14;
  if ( a2 != v15 )
  {
    std::_Uninitialized_move<DelegationConfig::DelegationBase *>(v17, a2, v13);
    v15 = a1[1];
    v16 = v14 + 152;
    v17 = a2;
    v20 = v13;
  }
  std::_Uninitialized_move<DelegationConfig::DelegationBase *>(v17, v15, v16);
  v19[1] = 0;
  std::vector<DelegationConfig::DelegationBase>::_Change_array(a1, v13, v9, v5);
  std::vector<DelegationConfig::DelegationBase>::_Reallocation_guard::~_Reallocation_guard(v19);
  return v14;
}

```

## disassembly

```asm
0x180014ac0  push    rbx
0x180014ac2  push    rbp
0x180014ac3  push    rsi
0x180014ac4  push    rdi
0x180014ac5  push    r12
0x180014ac7  push    r13
0x180014ac9  push    r14
0x180014acb  push    r15
0x180014acd  sub     rsp, 58h
0x180014ad1  mov     r15, [rcx]
0x180014ad4  mov     r14, rdx
0x180014ad7  mov     rax, [rcx+8]
0x180014adb  mov     rdx, 86BCA1AF286BCA1Bh
0x180014ae5  sub     rax, r15
0x180014ae8  mov     rbx, 1AF286BCA1AF286h
0x180014af2  sar     rax, 3
0x180014af6  mov     r13, r8
0x180014af9  imul    rax, rdx
0x180014afd  mov     rdi, rcx
0x180014b00  cmp     rax, rbx
0x180014b03  jz      loc_180014C11
0x180014b09  mov     rcx, [rcx+10h]
0x180014b0d  lea     rbp, [rax+1]
0x180014b11  sub     rcx, r15
0x180014b14  mov     rax, rbx
0x180014b17  sar     rcx, 3
0x180014b1b  imul    rcx, rdx
0x180014b1f  mov     rdx, rcx
0x180014b22  shr     rdx, 1
0x180014b25  sub     rax, rdx
0x180014b28  cmp     rcx, rax
0x180014b2b  ja      short loc_180014B47
0x180014b2d  lea     rax, [rdx+rcx]
0x180014b31  mov     rcx, rbp
0x180014b34  cmp     rax, rbp
0x180014b37  cmovnb  rcx, rax
0x180014b3b  cmp     rcx, rbx
0x180014b3e  ja      loc_180014C0B
0x180014b44  mov     rbx, rcx
0x180014b47  imul    rcx, rbx, 98h
0x180014b4e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180014b53  mov     rsi, rax
0x180014b56  mov     [rsp+98h+var_78], rdi
0x180014b5b  mov     rcx, r14
0x180014b5e  mov     [rsp+98h+var_68], rbx
0x180014b63  sub     rcx, r15
0x180014b66  mov     rax, 6BCA1AF286BCA1Bh
0x180014b70  imul    rcx
0x180014b73  sar     rdx, 2
0x180014b77  mov     rcx, rdx
0x180014b7a  shr     rcx, 3Fh
0x180014b7e  add     rdx, rcx
0x180014b81  imul    r15, rdx, 98h
0x180014b88  mov     rdx, r13
0x180014b8b  add     r15, rsi
0x180014b8e  mov     rcx, r15
0x180014b91  lea     r12, [r15+98h]
0x180014b98  mov     [rsp+98h+var_58], r12
0x180014b9d  call    ??$construct_at@UDelegationBase@DelegationConfig@@U12@@std@@YAPEAUDelegationBase@DelegationConfig@@QEAU12@$$QEAU12@@Z; std::construct_at<DelegationConfig::DelegationBase,DelegationConfig::DelegationBase>(DelegationConfig::DelegationBase * const,DelegationConfig::DelegationBase &&)
0x180014ba2  mov     rdx, [rdi+8]
0x180014ba6  mov     r8, rsi
0x180014ba9  mov     rcx, [rdi]
0x180014bac  mov     [rsp+98h+var_60], r15
0x180014bb1  cmp     r14, rdx
0x180014bb4  jz      short loc_180014BCD
0x180014bb6  mov     rdx, r14
0x180014bb9  call    ??$_Uninitialized_move@PEAUDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@YAPEAUDelegationBase@DelegationConfig@@QEAU12@0PEAU12@AEAV?$allocator@UDelegationBase@DelegationConfig@@@0@@Z; std::_Uninitialized_move<DelegationConfig::DelegationBase *>(DelegationConfig::DelegationBase * const,DelegationConfig::DelegationBase * const,DelegationConfig::DelegationBase *,std::allocator<DelegationConfig::DelegationBase> &)
0x180014bbe  mov     rdx, [rdi+8]
0x180014bc2  mov     r8, r12
0x180014bc5  mov     rcx, r14
0x180014bc8  mov     [rsp+98h+var_60], rsi
0x180014bcd  call    ??$_Uninitialized_move@PEAUDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@YAPEAUDelegationBase@DelegationConfig@@QEAU12@0PEAU12@AEAV?$allocator@UDelegationBase@DelegationConfig@@@0@@Z; std::_Uninitialized_move<DelegationConfig::DelegationBase *>(DelegationConfig::DelegationBase * const,DelegationConfig::DelegationBase * const,DelegationConfig::DelegationBase *,std::allocator<DelegationConfig::DelegationBase> &)
0x180014bd2  mov     r9, rbx
0x180014bd5  mov     [rsp+98h+var_70], 0
0x180014bde  mov     r8, rbp
0x180014be1  mov     rdx, rsi
0x180014be4  mov     rcx, rdi
0x180014be7  call    ?_Change_array@?$vector@UDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@AEAAXQEAUDelegationBase@DelegationConfig@@_K1@Z; std::vector<DelegationConfig::DelegationBase>::_Change_array(DelegationConfig::DelegationBase * const,unsigned __int64,unsigned __int64)
0x180014bec  lea     rcx, [rsp+98h+var_78]
0x180014bf1  call    ??1_Reallocation_guard@?$vector@UDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@QEAA@XZ; std::vector<DelegationConfig::DelegationBase>::_Reallocation_guard::~_Reallocation_guard(void)
0x180014bf6  mov     rax, r15
0x180014bf9  add     rsp, 58h
0x180014bfd  pop     r15
0x180014bff  pop     r14
0x180014c01  pop     r13
0x180014c03  pop     r12
0x180014c05  pop     rdi
0x180014c06  pop     rsi
0x180014c07  pop     rbp
0x180014c08  pop     rbx
0x180014c09  retn
0x180014c0b  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180014c11  call    ?_Xlength@?$vector@UDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@CAXXZ; std::vector<DelegationConfig::DelegationBase>::_Xlength(void)
```
