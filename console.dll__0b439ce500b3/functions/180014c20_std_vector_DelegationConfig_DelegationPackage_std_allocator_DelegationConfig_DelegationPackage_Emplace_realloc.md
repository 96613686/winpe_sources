# std::vector<DelegationConfig::DelegationPackage,std::allocator<DelegationConfig::DelegationPackage>>::_Emplace_reallocate<DelegationConfig::DelegationPackage>(DelegationConfig::DelegationPackage * const,DelegationConfig::DelegationPackage &&)

- ea: `0x180014c20`
- end: `0x180014d81`
- name: `??$_Emplace_reallocate@UDelegationPackage@DelegationConfig@@@?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@AEAAPEAUDelegationPackage@DelegationConfig@@QEAU23@$$QEAU23@@Z`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180016c14`

## callees

- `0x18000d7c8`
- `0x18000eaf0`
- `0x180014c20`
- `0x180014e20`
- `0x180014eac`
- `0x1800151e8`
- `0x180015778`
- `0x180015860`

## pseudocode

```c
__int64 __fastcall std::vector<DelegationConfig::DelegationPackage>::_Emplace_reallocate<DelegationConfig::DelegationPackage>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r14
  __int64 v4; // rbx
  __int64 v7; // rax
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // r14
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rcx
  _QWORD v19[3]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v20; // [rsp+38h] [rbp-50h]
  __int64 v21; // [rsp+40h] [rbp-48h]

  v3 = g_availablePackages;
  v4 = 0x1745D1745D1745DLL;
  v7 = 0x2E8BA2E8BA2E8BA3LL * (((__int64)xmmword_180023990 - g_availablePackages) >> 4);
  if ( v7 == 0x1745D1745D1745DLL )
    std::vector<DelegationConfig::DelegationBase>::_Xlength();
  v8 = v7 + 1;
  v9 = 0x2E8BA2E8BA2E8BA3LL * ((*((_QWORD *)&xmmword_180023990 + 1) - g_availablePackages) >> 4);
  if ( v9 <= 0x1745D1745D1745DLL - (v9 >> 1) )
  {
    v10 = (v9 >> 1) + v9;
    v11 = v8;
    if ( v10 >= v8 )
      v11 = v10;
    if ( v11 > 0x1745D1745D1745DLL )
      std::_Throw_bad_array_new_length();
    v4 = v11;
  }
  v12 = std::_Allocate<16,std::_Default_allocate_traits>(176 * v4);
  v19[2] = v4;
  v19[0] = &g_availablePackages;
  v13 = v12 + 176 * ((a2 - v3) / 176);
  v21 = v13 + 176;
  std::construct_at<DelegationConfig::DelegationPackage,DelegationConfig::DelegationPackage>(v13, a3);
  v14 = xmmword_180023990;
  v15 = v12;
  v16 = g_availablePackages;
  v20 = v13;
  if ( a2 != (_QWORD)xmmword_180023990 )
  {
    std::_Uninitialized_move<DelegationConfig::DelegationPackage *>(g_availablePackages, a2, v12);
    v14 = xmmword_180023990;
    v15 = v13 + 176;
    v16 = a2;
    v20 = v12;
  }
  std::_Uninitialized_move<DelegationConfig::DelegationPackage *>(v16, v14, v15);
  v19[1] = 0;
  std::vector<DelegationConfig::DelegationPackage>::_Change_array(v17, v12, v8, v4);
  std::vector<DelegationConfig::DelegationPackage>::_Reallocation_guard::~_Reallocation_guard(v19);
  return v13;
}

```

## disassembly

```asm
0x180014c20  push    rbx
0x180014c22  push    rbp
0x180014c23  push    rsi
0x180014c24  push    rdi
0x180014c25  push    r12
0x180014c27  push    r14
0x180014c29  push    r15
0x180014c2b  sub     rsp, 50h
0x180014c2f  mov     r14, cs:?g_availablePackages@@3V?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@A; std::vector<DelegationConfig::DelegationPackage> g_availablePackages
0x180014c36  mov     r15, 2E8BA2E8BA2E8BA3h
0x180014c40  mov     rax, qword ptr cs:xmmword_180023990
0x180014c47  mov     rbx, 1745D1745D1745Dh
0x180014c51  sub     rax, r14
0x180014c54  mov     r12, r8
0x180014c57  sar     rax, 4
0x180014c5b  mov     rbp, rdx
0x180014c5e  imul    rax, r15
0x180014c62  cmp     rax, rbx
0x180014c65  jz      loc_180014D7B
0x180014c6b  mov     rcx, qword ptr cs:xmmword_180023990+8
0x180014c72  lea     rsi, [rax+1]
0x180014c76  sub     rcx, r14
0x180014c79  mov     rax, rbx
0x180014c7c  sar     rcx, 4
0x180014c80  imul    rcx, r15
0x180014c84  mov     rdx, rcx
0x180014c87  shr     rdx, 1
0x180014c8a  sub     rax, rdx
0x180014c8d  cmp     rcx, rax
0x180014c90  ja      short loc_180014CAC
0x180014c92  lea     rax, [rdx+rcx]
0x180014c96  mov     rcx, rsi
0x180014c99  cmp     rax, rsi
0x180014c9c  cmovnb  rcx, rax
0x180014ca0  cmp     rcx, rbx
0x180014ca3  ja      loc_180014D75
0x180014ca9  mov     rbx, rcx
0x180014cac  imul    rcx, rbx, 0B0h
0x180014cb3  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180014cb8  mov     rdi, rax
0x180014cbb  mov     [rsp+88h+var_58], rbx
0x180014cc0  mov     rax, r15
0x180014cc3  mov     rcx, rbp
0x180014cc6  sub     rcx, r14
0x180014cc9  imul    rcx
0x180014ccc  lea     rax, ?g_availablePackages@@3V?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@A; std::vector<DelegationConfig::DelegationPackage> g_availablePackages
0x180014cd3  sar     rdx, 5
0x180014cd7  mov     rcx, rdx
0x180014cda  mov     [rsp+88h+var_68], rax
0x180014cdf  shr     rcx, 3Fh
0x180014ce3  add     rdx, rcx
0x180014ce6  imul    r14, rdx, 0B0h
0x180014ced  mov     rdx, r12
0x180014cf0  add     r14, rdi
0x180014cf3  mov     rcx, r14
0x180014cf6  lea     r15, [r14+0B0h]
0x180014cfd  mov     [rsp+88h+var_48], r15
0x180014d02  call    ??$construct_at@UDelegationPackage@DelegationConfig@@U12@@std@@YAPEAUDelegationPackage@DelegationConfig@@QEAU12@$$QEAU12@@Z; std::construct_at<DelegationConfig::DelegationPackage,DelegationConfig::DelegationPackage>(DelegationConfig::DelegationPackage * const,DelegationConfig::DelegationPackage &&)
0x180014d07  mov     rdx, qword ptr cs:xmmword_180023990
0x180014d0e  mov     r8, rdi
0x180014d11  mov     rcx, cs:?g_availablePackages@@3V?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@A; std::vector<DelegationConfig::DelegationPackage> g_availablePackages
0x180014d18  mov     [rsp+88h+var_50], r14
0x180014d1d  cmp     rbp, rdx
0x180014d20  jz      short loc_180014D3C
0x180014d22  mov     rdx, rbp
0x180014d25  call    ??$_Uninitialized_move@PEAUDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@YAPEAUDelegationPackage@DelegationConfig@@QEAU12@0PEAU12@AEAV?$allocator@UDelegationPackage@DelegationConfig@@@0@@Z; std::_Uninitialized_move<DelegationConfig::DelegationPackage *>(DelegationConfig::DelegationPackage * const,DelegationConfig::DelegationPackage * const,DelegationConfig::DelegationPackage *,std::allocator<DelegationConfig::DelegationPackage> &)
0x180014d2a  mov     rdx, qword ptr cs:xmmword_180023990
0x180014d31  mov     r8, r15
0x180014d34  mov     rcx, rbp
0x180014d37  mov     [rsp+88h+var_50], rdi
0x180014d3c  call    ??$_Uninitialized_move@PEAUDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@YAPEAUDelegationPackage@DelegationConfig@@QEAU12@0PEAU12@AEAV?$allocator@UDelegationPackage@DelegationConfig@@@0@@Z; std::_Uninitialized_move<DelegationConfig::DelegationPackage *>(DelegationConfig::DelegationPackage * const,DelegationConfig::DelegationPackage * const,DelegationConfig::DelegationPackage *,std::allocator<DelegationConfig::DelegationPackage> &)
0x180014d41  mov     r9, rbx
0x180014d44  mov     [rsp+88h+var_60], 0
0x180014d4d  mov     r8, rsi
0x180014d50  mov     rdx, rdi
0x180014d53  call    ?_Change_array@?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@AEAAXQEAUDelegationPackage@DelegationConfig@@_K1@Z; std::vector<DelegationConfig::DelegationPackage>::_Change_array(DelegationConfig::DelegationPackage * const,unsigned __int64,unsigned __int64)
0x180014d58  lea     rcx, [rsp+88h+var_68]
0x180014d5d  call    ??1_Reallocation_guard@?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@QEAA@XZ; std::vector<DelegationConfig::DelegationPackage>::_Reallocation_guard::~_Reallocation_guard(void)
0x180014d62  mov     rax, r14
0x180014d65  add     rsp, 50h
0x180014d69  pop     r15
0x180014d6b  pop     r14
0x180014d6d  pop     r12
0x180014d6f  pop     rdi
0x180014d70  pop     rsi
0x180014d71  pop     rbp
0x180014d72  pop     rbx
0x180014d73  retn
0x180014d75  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180014d7b  call    ?_Xlength@?$vector@UDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@CAXXZ; std::vector<DelegationConfig::DelegationBase>::_Xlength(void)
```
