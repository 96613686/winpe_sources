# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_grow_by<`std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Resize_and_overwrite<`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_>(unsigned __int64,`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_)'::`5'::_lambda_1_,>(unsigned __int64,`std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Resize_and_overwrite<`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_>(unsigned __int64,`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_)'::`5'::_lambda_1_)

- ea: `0x180007ff8`
- end: `0x1800080f5`
- name: `??$_Reallocate_grow_by@V_lambda_1_@?4???$_Resize_and_overwrite@V_lambda_1_@?4???Kfilesystem@std@@YA?AVpath@23@AEBV423@0@Z@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KV1?4???Kfilesystem@3@YA?AVpath@43@AEBV543@1@Z@@Z@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?4???$_Resize_and_overwrite@V_lambda_1_@?4???Kfilesystem@std@@YA?AVpath@23@AEBV423@0@Z@@01@QEAAX0V2?4???Kfilesystem@1@YA?AVpath@31@AEBV431@1@Z@@Z@@Z`
- size: `253`
- prototype: `void **__fastcall(void **Src, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180008f94`

## callees

- `0x180001f70`
- `0x18000739c`
- `0x180007ff8`
- `0x18000aa3c`
- `0x18000d5b4`

## pseudocode

```c
void **__fastcall ____Reallocate_grow_by_V_lambda_1___4_____Resize_and_overwrite_V_lambda_1___4___Kfilesystem_std__YA_AVpath_23_AEBV423_0_Z____basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAX_KV1_4___Kfilesystem_3_YA_AVpath_43_AEBV543_1_Z__Z___V___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___4_____Resize_and_overwrite_V_lambda_1___4___Kfilesystem_std__YA_AVpath_23_AEBV423_0_Z__01_QEAAX0V2_4___Kfilesystem_1_YA_AVpath_31_AEBV431_1_Z__Z__Z(
        void **Src,
        unsigned __int64 a2)
{
  void *v2; // rbx
  __int64 v4; // rcx
  unsigned __int64 v5; // r14
  char *v6; // rbp
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r8
  _QWORD *v9; // rsi
  size_t v10; // r8
  _BYTE *v11; // rbx
  unsigned __int64 v12; // rdx
  _BYTE *v13; // rcx
  void **result; // rax
  __int64 v15; // [rsp+40h] [rbp+8h] BYREF

  v2 = Src[2];
  v4 = 0x7FFFFFFFFFFFFFFELL;
  if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v2 < a2 )
    std::_Xlen_string();
  v5 = (unsigned __int64)Src[3];
  v6 = (char *)v2 + a2;
  v7 = ((unsigned __int64)v2 + a2) | 7;
  if ( v7 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v8 = v5 >> 1;
    if ( v5 <= 0x7FFFFFFFFFFFFFFELL - (v5 >> 1) )
    {
      v4 = v5 + v8;
      if ( v7 >= v5 + v8 )
        v4 = v7;
    }
  }
  v15 = v4;
  v9 = std::wstring::_Allocate_for_capacity<0>(v4, &v15);
  Src[3] = (void *)v15;
  Src[2] = v6;
  v10 = 2LL * (_QWORD)v2 + 2;
  if ( v5 <= 7 )
  {
    memcpy_0(v9, Src, v10);
  }
  else
  {
    v11 = *Src;
    memcpy_0(v9, *Src, v10);
    v12 = 2 * v5 + 2;
    if ( v12 < 0x1000 )
    {
      v13 = v11;
    }
    else
    {
      v13 = (_BYTE *)*((_QWORD *)v11 - 1);
      if ( (unsigned __int64)(v11 - v13 - 8) > 0x1F )
        __fastfail(5u);
      v12 = 2 * v5 + 41;
    }
    operator delete(v13, v12);
  }
  result = Src;
  *Src = v9;
  return result;
}

```

## disassembly

```asm
0x180007ff8  mov     [rsp+arg_8], rbx
0x180007ffd  mov     [rsp+arg_10], rbp
0x180008002  push    rsi
0x180008003  push    rdi
0x180008004  push    r14
0x180008006  sub     rsp, 20h
0x18000800a  mov     rbx, [rcx+10h]
0x18000800e  mov     rdi, rcx
0x180008011  mov     rcx, 7FFFFFFFFFFFFFFEh
0x18000801b  mov     rax, rcx
0x18000801e  sub     rax, rbx
0x180008021  cmp     rax, rdx
0x180008024  jb      loc_1800080EF
0x18000802a  mov     r14, [rdi+18h]
0x18000802e  lea     rbp, [rbx+rdx]
0x180008032  mov     rdx, rbp
0x180008035  or      rdx, 7
0x180008039  cmp     rdx, rcx
0x18000803c  ja      short loc_18000805A
0x18000803e  mov     r8, r14
0x180008041  mov     rax, rcx
0x180008044  shr     r8, 1
0x180008047  sub     rax, r8
0x18000804a  cmp     r14, rax
0x18000804d  ja      short loc_18000805A
0x18000804f  lea     rcx, [r14+r8]
0x180008053  cmp     rdx, rcx
0x180008056  cmovnb  rcx, rdx
0x18000805a  lea     rdx, [rsp+38h+arg_0]
0x18000805f  mov     [rsp+38h+arg_0], rcx
0x180008064  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180008069  mov     rcx, [rsp+38h+arg_0]
0x18000806e  mov     rsi, rax
0x180008071  mov     [rdi+18h], rcx
0x180008075  mov     rcx, rax; void *
0x180008078  mov     [rdi+10h], rbp
0x18000807c  lea     r8, ds:2[rbx*2]; Size
0x180008084  cmp     r14, 7
0x180008088  jbe     short loc_1800080CE
0x18000808a  mov     rbx, [rdi]
0x18000808d  mov     rdx, rbx; Src
0x180008090  call    memcpy_0
0x180008095  lea     rdx, ds:2[r14*2]; unsigned __int64
0x18000809d  cmp     rdx, 1000h
0x1800080a4  jb      short loc_1800080C4
0x1800080a6  mov     rcx, [rbx-8]
0x1800080aa  sub     rbx, rcx
0x1800080ad  sub     rbx, 8
0x1800080b1  cmp     rbx, 1Fh
0x1800080b5  ja      short loc_1800080BD
0x1800080b7  add     rdx, 27h ; '''
0x1800080bb  jmp     short loc_1800080C7
0x1800080bd  mov     ecx, 5
0x1800080c2  int     29h; Win8: RtlFailFast(ecx)
0x1800080c4  mov     rcx, rbx; void *
0x1800080c7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800080cc  jmp     short loc_1800080D6
0x1800080ce  mov     rdx, rdi; Src
0x1800080d1  call    memcpy_0
0x1800080d6  mov     rax, rdi
0x1800080d9  mov     [rax], rsi
0x1800080dc  mov     rbx, [rsp+38h+arg_8]
0x1800080e1  mov     rbp, [rsp+38h+arg_10]
0x1800080e6  add     rsp, 20h
0x1800080ea  pop     r14
0x1800080ec  pop     rdi
0x1800080ed  pop     rsi
0x1800080ee  retn
0x1800080ef  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
