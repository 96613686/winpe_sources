# std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x180008f94`
- end: `0x180009135`
- name: `??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z`
- size: `417`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *Src, struct std::filesystem::path *, std::filesystem *this)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000993c`
- `0x180009d90`
- `0x180009ec0`
- `0x180009f54`

## callees

- `0x180007ff8`
- `0x180008a68`
- `0x180008f94`
- `0x1800091d8`
- `0x18000d5b4`

## pseudocode

```c
std::filesystem::path *__fastcall std::filesystem::operator/(
        std::filesystem::path *Src,
        struct std::filesystem::path *a2,
        std::filesystem *this)
{
  __int64 v6; // rdx
  std::filesystem *v7; // r15
  size_t v8; // r13
  __int64 v9; // rcx
  unsigned __int8 v10; // r12
  size_t v11; // r14
  unsigned __int64 v12; // rdi
  std::filesystem::path *v13; // rbp
  _WORD *v14; // rcx
  std::filesystem::path *v15; // rcx

  v6 = *((_QWORD *)this + 2);
  if ( *((_QWORD *)this + 3) <= 7u )
    v7 = this;
  else
    v7 = *(std::filesystem **)this;
  if ( !v6
    || (v8 = 2 * v6, 2 * v6 >= 4) && (*(_DWORD *)v7 & 0xFFFFFFDF) - 3801153 < 0x1A
    || *(_WORD *)v7 == 92
    || *(_WORD *)v7 == 47 )
  {
    std::filesystem::path::path(Src, a2);
    std::filesystem::path::operator/=(Src, this);
    return Src;
  }
  v9 = *((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(struct std::filesystem::path **)a2;
  if ( v9 == 2 )
  {
    if ( (*(_DWORD *)a2 & 0xFFFFFFDF) - 3801153 < 0x1A )
      goto LABEL_13;
  }
  else if ( !v9 )
  {
    goto LABEL_13;
  }
  v11 = 2 * v9;
  if ( *((_WORD *)a2 + v9 - 1) != 92 && *(_WORD *)((char *)a2 + v11 - 2) != 47 )
  {
    v10 = 1;
    goto LABEL_14;
  }
LABEL_13:
  v10 = 0;
  v11 = 2 * v9;
LABEL_14:
  v12 = v6 + v9 + v10;
  *(_OWORD *)Src = 0;
  *((_QWORD *)Src + 2) = 0;
  *((_QWORD *)Src + 3) = 7;
  *(_WORD *)Src = 0;
  if ( v12 <= 7 )
    *((_QWORD *)Src + 2) = v12;
  else
    ____Reallocate_grow_by_V_lambda_1___4_____Resize_and_overwrite_V_lambda_1___4___Kfilesystem_std__YA_AVpath_23_AEBV423_0_Z____basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAX_KV1_4___Kfilesystem_3_YA_AVpath_43_AEBV543_1_Z__Z___V___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___4_____Resize_and_overwrite_V_lambda_1___4___Kfilesystem_std__YA_AVpath_23_AEBV423_0_Z__01_QEAAX0V2_4___Kfilesystem_1_YA_AVpath_31_AEBV431_1_Z__Z__Z(
      (void **)Src,
      v6 + v9 + v10);
  if ( *((_QWORD *)Src + 3) <= 7u )
    v13 = Src;
  else
    v13 = *(std::filesystem::path **)Src;
  memcpy_0(v13, a2, v11);
  v14 = (_WORD *)((char *)v13 + v11);
  if ( v10 )
    *v14++ = 92;
  memcpy_0(v14, v7, v8);
  *((_QWORD *)Src + 2) = v12;
  if ( *((_QWORD *)Src + 3) <= 7u )
    v15 = Src;
  else
    v15 = *(std::filesystem::path **)Src;
  *((_WORD *)v15 + v12) = 0;
  return Src;
}

```

## disassembly

```asm
0x180008f94  mov     [rsp+arg_8], rbx
0x180008f99  mov     [rsp+arg_0], rcx
0x180008f9e  push    rbp
0x180008f9f  push    rsi
0x180008fa0  push    rdi
0x180008fa1  push    r12
0x180008fa3  push    r13
0x180008fa5  push    r14
0x180008fa7  push    r15
0x180008fa9  sub     rsp, 20h
0x180008fad  mov     rdi, r8
0x180008fb0  mov     rsi, rdx
0x180008fb3  mov     rbx, rcx
0x180008fb6  mov     r8d, 1
0x180008fbc  mov     [rsp+58h+arg_10], r8d
0x180008fc1  mov     rdx, [rdi+10h]
0x180008fc5  lea     ebp, [r8+6]
0x180008fc9  cmp     [rdi+18h], rbp
0x180008fcd  jbe     short loc_180008FD4
0x180008fcf  mov     r15, [rdi]
0x180008fd2  jmp     short loc_180008FD7
0x180008fd4  mov     r15, rdi
0x180008fd7  test    rdx, rdx
0x180008fda  jz      loc_180009100
0x180008fe0  lea     r13, [rdx+rdx]
0x180008fe4  mov     rax, r13
0x180008fe7  and     rax, 0FFFFFFFFFFFFFFFEh
0x180008feb  mov     r9d, 0FFFFFFDFh
0x180008ff1  mov     r10d, 3A0041h
0x180008ff7  cmp     rax, 4
0x180008ffb  jl      short loc_18000900F
0x180008ffd  mov     eax, [r15]
0x180009000  and     eax, r9d
0x180009003  sub     eax, r10d
0x180009006  cmp     eax, 1Ah
0x180009009  jb      loc_180009100
0x18000900f  mov     r11d, 5Ch ; '\'
0x180009015  cmp     [r15], r11w
0x180009019  jz      loc_180009100
0x18000901f  cmp     word ptr [r15], 2Fh ; '/'
0x180009024  jz      loc_180009100
0x18000902a  mov     rcx, [rsi+10h]
0x18000902e  cmp     [rsi+18h], rbp
0x180009032  jbe     short loc_180009037
0x180009034  mov     rsi, [rsi]
0x180009037  cmp     rcx, 2
0x18000903b  jnz     short loc_180009089
0x18000903d  mov     eax, [rsi]
0x18000903f  and     eax, r9d
0x180009042  sub     eax, r10d
0x180009045  cmp     eax, 1Ah
0x180009048  jnb     short loc_18000908E
0x18000904a  xor     r12b, r12b
0x18000904d  lea     r14, [rcx+rcx]
0x180009051  movzx   edi, r12b
0x180009055  add     rdi, rcx
0x180009058  add     rdi, rdx
0x18000905b  xorps   xmm0, xmm0
0x18000905e  movups  xmmword ptr [rbx], xmm0
0x180009061  mov     qword ptr [rbx+10h], 0
0x180009069  mov     [rbx+18h], rbp
0x18000906d  xor     eax, eax
0x18000906f  mov     [rbx], ax
0x180009072  mov     [rsp+58h+arg_10], r8d
0x180009077  cmp     rdi, rbp
0x18000907a  jbe     short loc_1800090A8
0x18000907c  mov     rdx, rdi
0x18000907f  mov     rcx, rbx; Src
0x180009082  call    ??$_Reallocate_grow_by@V_lambda_1_@?4???$_Resize_and_overwrite@V_lambda_1_@?4???Kfilesystem@std@@YA?AVpath@23@AEBV423@0@Z@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KV1?4???Kfilesystem@3@YA?AVpath@43@AEBV543@1@Z@@Z@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?4???$_Resize_and_overwrite@V_lambda_1_@?4???Kfilesystem@std@@YA?AVpath@23@AEBV423@0@Z@@01@QEAAX0V2?4???Kfilesystem@1@YA?AVpath@31@AEBV431@1@Z@@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Resize_and_overwrite<`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_>(unsigned __int64,`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_)'::`5'::_lambda_1_,>(unsigned __int64,`std::wstring::_Resize_and_overwrite<`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_>(unsigned __int64,`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_)'::`5'::_lambda_1_)
0x180009087  jmp     short loc_1800090AC
0x180009089  test    rcx, rcx
0x18000908c  jz      short loc_18000904A
0x18000908e  lea     r14, [rcx+rcx]
0x180009092  cmp     [r14+rsi-2], r11w
0x180009098  jz      short loc_18000904A
0x18000909a  cmp     word ptr [r14+rsi-2], 2Fh ; '/'
0x1800090a1  jz      short loc_18000904A
0x1800090a3  mov     r12b, r8b
0x1800090a6  jmp     short loc_180009051
0x1800090a8  mov     [rbx+10h], rdi
0x1800090ac  cmp     [rbx+18h], rbp
0x1800090b0  jbe     short loc_1800090B7
0x1800090b2  mov     rbp, [rbx]
0x1800090b5  jmp     short loc_1800090BA
0x1800090b7  mov     rbp, rbx
0x1800090ba  mov     r8, r14; Size
0x1800090bd  mov     rdx, rsi; Src
0x1800090c0  mov     rcx, rbp; void *
0x1800090c3  call    memcpy_0
0x1800090c8  lea     rcx, [r14+rbp]
0x1800090cc  test    r12b, r12b
0x1800090cf  jz      short loc_1800090DA
0x1800090d1  mov     word ptr [rcx], 5Ch ; '\'
0x1800090d6  add     rcx, 2; void *
0x1800090da  mov     r8, r13; Size
0x1800090dd  mov     rdx, r15; Src
0x1800090e0  call    memcpy_0
0x1800090e5  mov     [rbx+10h], rdi
0x1800090e9  cmp     qword ptr [rbx+18h], 7
0x1800090ee  jbe     short loc_1800090F5
0x1800090f0  mov     rcx, [rbx]
0x1800090f3  jmp     short loc_1800090F8
0x1800090f5  mov     rcx, rbx; this
0x1800090f8  xor     eax, eax
0x1800090fa  mov     [rcx+rdi*2], ax
0x1800090fe  jmp     short loc_18000911D
0x180009100  mov     rdx, rsi; struct std::filesystem::path *
0x180009103  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x180009108  nop
0x180009109  mov     [rsp+58h+arg_10], 3
0x180009111  mov     rdx, rdi; this
0x180009114  mov     rcx, rbx; Src
0x180009117  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x18000911c  nop
0x18000911d  mov     rax, rbx
0x180009120  mov     rbx, [rsp+58h+arg_8]
0x180009125  add     rsp, 20h
0x180009129  pop     r15
0x18000912b  pop     r14
0x18000912d  pop     r13
0x18000912f  pop     r12
0x180009131  pop     rdi
0x180009132  pop     rsi
0x180009133  pop     rbp
0x180009134  retn
```
