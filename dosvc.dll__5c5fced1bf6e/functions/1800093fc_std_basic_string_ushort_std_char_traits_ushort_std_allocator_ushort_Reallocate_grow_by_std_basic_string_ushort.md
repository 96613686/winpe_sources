# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_grow_by<`std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Resize_and_overwrite<`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_>(unsigned __int64,`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_)'::`5'::_lambda_1_,>(unsigned __int64,`std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Resize_and_overwrite<`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_>(unsigned __int64,`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_)'::`5'::_lambda_1_)

- ea: `0x1800093fc`
- end: `0x1800094b3`
- name: `??$_Reallocate_grow_by@V_lambda_1_@?4???$_Resize_and_overwrite@V_lambda_1_@?4???Kfilesystem@std@@YA?AVpath@23@AEBV423@0@Z@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KV1?4???Kfilesystem@3@YA?AVpath@43@AEBV543@1@Z@@Z@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?4???$_Resize_and_overwrite@V_lambda_1_@?4???Kfilesystem@std@@YA?AVpath@23@AEBV423@0@Z@@01@QEAAX0V2?4???Kfilesystem@1@YA?AVpath@31@AEBV431@1@Z@@Z@@Z`
- size: `183`
- prototype: `_QWORD *__fastcall(_QWORD *Src, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800094bc`

## callees

- `0x180002340`
- `0x180003e14`
- `0x180004270`
- `0x1800093fc`
- `0x18000a6d4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000942e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000942e`

## pseudocode

```c
_QWORD *__fastcall ____Reallocate_grow_by_V_lambda_1___4_____Resize_and_overwrite_V_lambda_1___4___Kfilesystem_std__YA_AVpath_23_AEBV423_0_Z____basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAX_KV1_4___Kfilesystem_3_YA_AVpath_43_AEBV543_1_Z__Z___V___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___4_____Resize_and_overwrite_V_lambda_1___4___Kfilesystem_std__YA_AVpath_23_AEBV423_0_Z__01_QEAAX0V2_4___Kfilesystem_1_YA_AVpath_31_AEBV431_1_Z__Z__Z(
        _QWORD *Src,
        unsigned __int64 a2)
{
  __int64 v2; // r14
  unsigned __int64 v4; // rbp
  __int64 v5; // rbx
  __int64 v6; // rcx
  void *v7; // rsi
  size_t v8; // r8
  _QWORD *v9; // rbx
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF

  v2 = Src[2];
  if ( 0x7FFFFFFFFFFFFFFELL - v2 < a2 )
    std::_Xlength_error("string too long");
  v4 = Src[3];
  v5 = v2 + a2;
  v11 = std::wstring::_Calculate_growth(Src, v2 + a2);
  v7 = (void *)std::wstring::_Allocate_for_capacity<0>(v6, &v11);
  Src[3] = v11;
  Src[2] = v5;
  v8 = 2 * v2 + 2;
  if ( v4 <= 7 )
  {
    memcpy_0(v7, Src, v8);
  }
  else
  {
    v9 = (_QWORD *)*Src;
    memcpy_0(v7, (const void *)*Src, v8);
    std::_Deallocate<16>(v9, 2 * v4 + 2);
  }
  *Src = v7;
  return Src;
}

```

## disassembly

```asm
0x1800093fc  mov     [rsp+arg_8], rbx
0x180009401  mov     [rsp+arg_10], rbp
0x180009406  push    rsi
0x180009407  push    rdi
0x180009408  push    r14
0x18000940a  sub     rsp, 20h
0x18000940e  mov     r14, [rcx+10h]
0x180009412  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000941c  sub     rax, r14
0x18000941f  mov     rdi, rcx
0x180009422  cmp     rax, rdx
0x180009425  jnb     short loc_180009435
0x180009427  lea     rcx, aStringTooLong; "string too long"
0x18000942e  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180009435  mov     rbp, [rcx+18h]
0x180009439  lea     rbx, [r14+rdx]
0x18000943d  mov     rdx, rbx
0x180009440  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBA_K_K@Z; std::wstring::_Calculate_growth(unsigned __int64)
0x180009445  lea     rdx, [rsp+38h+arg_0]
0x18000944a  mov     [rsp+38h+arg_0], rax
0x18000944f  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180009454  mov     rcx, [rsp+38h+arg_0]
0x180009459  mov     rsi, rax
0x18000945c  mov     [rdi+18h], rcx
0x180009460  mov     rcx, rax; void *
0x180009463  mov     [rdi+10h], rbx
0x180009467  lea     r8, ds:2[r14*2]; Size
0x18000946f  cmp     rbp, 7
0x180009473  jbe     short loc_180009492
0x180009475  mov     rbx, [rdi]
0x180009478  mov     rdx, rbx; Src
0x18000947b  call    memcpy_0
0x180009480  lea     rdx, ds:2[rbp*2]
0x180009488  mov     rcx, rbx
0x18000948b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009490  jmp     short loc_18000949A
0x180009492  mov     rdx, rdi; Src
0x180009495  call    memcpy_0
0x18000949a  mov     [rdi], rsi
0x18000949d  mov     rax, rdi
0x1800094a0  mov     rbx, [rsp+38h+arg_8]
0x1800094a5  mov     rbp, [rsp+38h+arg_10]
0x1800094aa  add     rsp, 20h
0x1800094ae  pop     r14
0x1800094b0  pop     rdi
0x1800094b1  pop     rsi
0x1800094b2  retn
```
