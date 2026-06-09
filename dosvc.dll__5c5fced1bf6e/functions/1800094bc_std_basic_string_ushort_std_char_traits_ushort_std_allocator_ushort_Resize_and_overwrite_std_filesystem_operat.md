# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Resize_and_overwrite<`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_>(unsigned __int64,`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_)

- ea: `0x1800094bc`
- end: `0x18000954d`
- name: `??$_Resize_and_overwrite@V_lambda_1_@?4???Kfilesystem@std@@YA?AVpath@23@AEBV423@0@Z@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KV_lambda_1_@?4???Kfilesystem@1@YA?AVpath@31@AEBV431@1@Z@@Z`
- size: `145`
- prototype: `__int64 __fastcall(char **, char *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003700`

## callees

- `0x1800093fc`
- `0x1800094bc`
- `0x18000a6d4`

## pseudocode

```c
__int64 __fastcall ____Resize_and_overwrite_V_lambda_1___4___Kfilesystem_std__YA_AVpath_23_AEBV423_0_Z____basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAX_KV_lambda_1___4___Kfilesystem_1_YA_AVpath_31_AEBV431_1_Z__Z(
        char **a1,
        char *a2,
        __int64 a3)
{
  char **v5; // rdi
  char *v6; // rbp
  size_t v7; // rbx
  char *v8; // rcx
  __int64 result; // rax

  v5 = a1;
  if ( a1[3] >= a2 )
    a1[2] = a2;
  else
    ____Reallocate_grow_by_V_lambda_1___4_____Resize_and_overwrite_V_lambda_1___4___Kfilesystem_std__YA_AVpath_23_AEBV423_0_Z____basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAX_KV1_4___Kfilesystem_3_YA_AVpath_43_AEBV543_1_Z__Z___V___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___4_____Resize_and_overwrite_V_lambda_1___4___Kfilesystem_std__YA_AVpath_23_AEBV423_0_Z__01_QEAAX0V2_4___Kfilesystem_1_YA_AVpath_31_AEBV431_1_Z__Z__Z(
      a1,
      a2 - a1[2]);
  if ( (unsigned __int64)v5[3] <= 7 )
    v6 = (char *)v5;
  else
    v6 = *v5;
  v7 = 2LL * *(_QWORD *)(a3 + 8);
  memcpy_0(v6, *(const void **)a3, v7);
  v8 = &v6[v7];
  if ( *(_BYTE *)(a3 + 16) )
  {
    *(_WORD *)v8 = 92;
    v8 += 2;
  }
  memcpy_0(v8, *(const void **)(a3 + 24), 2LL * *(_QWORD *)(a3 + 32));
  v5[2] = a2;
  if ( (unsigned __int64)v5[3] > 7 )
    v5 = (char **)*v5;
  result = 0;
  *((_WORD *)v5 + (_QWORD)a2) = 0;
  return result;
}

```

## disassembly

```asm
0x1800094bc  push    rbx
0x1800094be  push    rbp
0x1800094bf  push    rsi
0x1800094c0  push    rdi
0x1800094c1  push    r14
0x1800094c3  sub     rsp, 20h
0x1800094c7  mov     r14, r8
0x1800094ca  mov     rsi, rdx
0x1800094cd  mov     rdi, rcx
0x1800094d0  cmp     [rcx+18h], rdx
0x1800094d4  jnb     short loc_1800094E1
0x1800094d6  sub     rdx, [rcx+10h]
0x1800094da  call    ??$_Reallocate_grow_by@V_lambda_1_@?4???$_Resize_and_overwrite@V_lambda_1_@?4???Kfilesystem@std@@YA?AVpath@23@AEBV423@0@Z@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KV1?4???Kfilesystem@3@YA?AVpath@43@AEBV543@1@Z@@Z@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?4???$_Resize_and_overwrite@V_lambda_1_@?4???Kfilesystem@std@@YA?AVpath@23@AEBV423@0@Z@@01@QEAAX0V2?4???Kfilesystem@1@YA?AVpath@31@AEBV431@1@Z@@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Resize_and_overwrite<`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_>(unsigned __int64,`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_)'::`5'::_lambda_1_,>(unsigned __int64,`std::wstring::_Resize_and_overwrite<`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_>(unsigned __int64,`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_)'::`5'::_lambda_1_)
0x1800094df  jmp     short loc_1800094E5
0x1800094e1  mov     [rcx+10h], rsi
0x1800094e5  cmp     qword ptr [rdi+18h], 7
0x1800094ea  jbe     short loc_1800094F1
0x1800094ec  mov     rbp, [rdi]
0x1800094ef  jmp     short loc_1800094F4
0x1800094f1  mov     rbp, rdi
0x1800094f4  mov     rax, [r14+8]
0x1800094f8  mov     rcx, rbp; void *
0x1800094fb  mov     rdx, [r14]; Src
0x1800094fe  lea     rbx, [rax+rax]
0x180009502  mov     r8, rbx; Size
0x180009505  call    memcpy_0
0x18000950a  cmp     byte ptr [r14+10h], 0
0x18000950f  lea     rcx, [rbx+rbp]
0x180009513  jz      short loc_18000951E
0x180009515  mov     word ptr [rcx], 5Ch ; '\'
0x18000951a  add     rcx, 2; void *
0x18000951e  mov     r8, [r14+20h]
0x180009522  mov     rdx, [r14+18h]; Src
0x180009526  add     r8, r8; Size
0x180009529  call    memcpy_0
0x18000952e  mov     [rdi+10h], rsi
0x180009532  cmp     qword ptr [rdi+18h], 7
0x180009537  jbe     short loc_18000953C
0x180009539  mov     rdi, [rdi]
0x18000953c  xor     eax, eax
0x18000953e  mov     [rdi+rsi*2], ax
0x180009542  add     rsp, 20h
0x180009546  pop     r14
0x180009548  pop     rdi
0x180009549  pop     rsi
0x18000954a  pop     rbp
0x18000954b  pop     rbx
0x18000954c  retn
```
