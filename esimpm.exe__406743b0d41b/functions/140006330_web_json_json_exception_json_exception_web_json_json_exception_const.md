# web::json::json_exception::json_exception(web::json::json_exception const &)

- ea: `0x140006330`
- end: `0x140006468`
- name: `??0json_exception@json@web@@QEAA@AEBV012@@Z`
- size: `312`
- prototype: `web::json::json_exception *__fastcall(web::json::json_exception *this, const struct web::json::json_exception *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140002f84`
- `0x1400039ae`
- `0x140003b10`
- `0x140006330`
- `0x140013dd0`
- `0x140013e64`

## pseudocode

```c
web::json::json_exception *__fastcall web::json::json_exception::json_exception(
        web::json::json_exception *this,
        const struct web::json::json_exception *a2)
{
  _OWORD *v4; // rbp
  unsigned __int64 v5; // rsi
  __int64 v6; // rbx
  size_t v7; // rax
  void *v8; // rax
  void *v9; // rcx
  size_t v10; // rcx
  _QWORD *v11; // rax

  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  o___std_exception_copy_0((char *)a2 + 8);
  *(_QWORD *)this = &web::json::json_exception::`vftable';
  *(_OWORD *)((char *)this + 24) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  if ( *((_QWORD *)a2 + 6) <= 0xFu )
    v4 = (_OWORD *)((char *)a2 + 24);
  else
    v4 = (_OWORD *)*((_QWORD *)a2 + 3);
  v5 = *((_QWORD *)a2 + 5);
  v6 = 0x7FFFFFFFFFFFFFFFLL;
  if ( v5 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlen_string();
  if ( v5 > 0xF )
  {
    if ( (v5 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
    {
      v7 = 0x8000000000000027uLL;
LABEL_9:
      v8 = operator new(v7);
      v9 = v8;
      if ( !v8 )
        __fastfail(5u);
      v11 = (_QWORD *)(((unsigned __int64)v8 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v11 - 1) = v9;
      goto LABEL_20;
    }
    v6 = v5 | 0xF;
    if ( (v5 | 0xF) < 0x16 )
      v6 = 22;
    v10 = v6 + 1;
    if ( v6 == -1 )
    {
      v11 = 0;
    }
    else
    {
      if ( v10 >= 0x1000 )
      {
        v7 = v6 + 40;
        if ( v6 + 40 < (unsigned __int64)(v6 + 1) )
          __scrt_throw_std_bad_array_new_length();
        goto LABEL_9;
      }
      v11 = operator new(v10);
    }
LABEL_20:
    *((_QWORD *)this + 3) = v11;
    *((_QWORD *)this + 5) = v5;
    *((_QWORD *)this + 6) = v6;
    memcpy_0(v11, v4, v5 + 1);
    return this;
  }
  *((_QWORD *)this + 5) = v5;
  *((_QWORD *)this + 6) = 15;
  *(_OWORD *)((char *)this + 24) = *v4;
  return this;
}

```

## disassembly

```asm
0x140006330  mov     [rsp+arg_0], rcx
0x140006335  push    rbx
0x140006336  push    rbp
0x140006337  push    rsi
0x140006338  push    rdi
0x140006339  sub     rsp, 28h
0x14000633d  mov     rbx, rdx
0x140006340  mov     rdi, rcx
0x140006343  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x14000634a  mov     [rcx], rax
0x14000634d  lea     rdx, [rcx+8]
0x140006351  xorps   xmm0, xmm0
0x140006354  movups  xmmword ptr [rdx], xmm0
0x140006357  lea     rcx, [rbx+8]
0x14000635b  call    _o___std_exception_copy_0
0x140006360  nop
0x140006361  lea     rax, ??_7json_exception@json@web@@6B@; const web::json::json_exception::`vftable'
0x140006368  mov     [rdi], rax
0x14000636b  xorps   xmm0, xmm0
0x14000636e  movups  xmmword ptr [rdi+18h], xmm0
0x140006372  xor     edx, edx
0x140006374  mov     [rdi+28h], rdx
0x140006378  mov     [rdi+30h], rdx
0x14000637c  cmp     qword ptr [rbx+30h], 0Fh
0x140006381  jbe     short loc_140006389
0x140006383  mov     rbp, [rbx+18h]
0x140006387  jmp     short loc_14000638D
0x140006389  lea     rbp, [rbx+18h]
0x14000638d  mov     rsi, [rbx+28h]
0x140006391  mov     rbx, 7FFFFFFFFFFFFFFFh
0x14000639b  cmp     rsi, rbx
0x14000639e  ja      loc_14000645C
0x1400063a4  cmp     rsi, 0Fh
0x1400063a8  ja      short loc_1400063C3
0x1400063aa  mov     [rdi+28h], rsi
0x1400063ae  mov     qword ptr [rdi+30h], 0Fh
0x1400063b6  movups  xmm0, xmmword ptr [rbp+0]
0x1400063ba  movups  xmmword ptr [rdi+18h], xmm0
0x1400063be  jmp     loc_140006450
0x1400063c3  mov     rax, rsi
0x1400063c6  or      rax, 0Fh
0x1400063ca  cmp     rax, rbx
0x1400063cd  jbe     short loc_1400063F0
0x1400063cf  mov     rax, 8000000000000027h
0x1400063d9  mov     rcx, rax; Size
0x1400063dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400063e1  mov     rcx, rax
0x1400063e4  test    rax, rax
0x1400063e7  jnz     short loc_140006421
0x1400063e9  mov     ecx, 5
0x1400063ee  int     29h; Win8: RtlFailFast(ecx)
0x1400063f0  mov     rbx, rax
0x1400063f3  mov     ecx, 16h
0x1400063f8  cmp     rax, rcx
0x1400063fb  cmovb   rbx, rcx
0x1400063ff  lea     rcx, [rbx+1]; Size
0x140006403  test    rcx, rcx
0x140006406  jnz     short loc_14000640D
0x140006408  mov     rax, rdx
0x14000640b  jmp     short loc_140006434
0x14000640d  cmp     rcx, 1000h
0x140006414  jb      short loc_14000642F
0x140006416  lea     rax, [rcx+27h]
0x14000641a  cmp     rax, rcx
0x14000641d  jbe     short loc_140006462
0x14000641f  jmp     short loc_1400063D9
0x140006421  add     rax, 27h ; '''
0x140006425  and     rax, 0FFFFFFFFFFFFFFE0h
0x140006429  mov     [rax-8], rcx
0x14000642d  jmp     short loc_140006434
0x14000642f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140006434  mov     [rdi+18h], rax
0x140006438  mov     [rdi+28h], rsi
0x14000643c  mov     [rdi+30h], rbx
0x140006440  lea     r8, [rsi+1]; Size
0x140006444  mov     rdx, rbp; Src
0x140006447  mov     rcx, rax; void *
0x14000644a  call    memcpy_0
0x14000644f  nop
0x140006450  mov     rax, rdi
0x140006453  add     rsp, 28h
0x140006457  pop     rdi
0x140006458  pop     rsi
0x140006459  pop     rbp
0x14000645a  pop     rbx
0x14000645b  retn
0x14000645c  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x140006462  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
