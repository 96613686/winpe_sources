# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)

- ea: `0x1400052b0`
- end: `0x14000543c`
- name: `??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z`
- size: `396`
- prototype: `void **__fastcall(void **Src, unsigned __int64, __int64, const void *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140006c30`
- `0x14000b7dc`

## callees

- `0x140001c74`
- `0x140001cb8`
- `0x1400027ba`
- `0x140003580`
- `0x1400035a8`
- `0x1400052b0`

## pseudocode

```c
void **__fastcall std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
        void **Src,
        unsigned __int64 a2,
        __int64 a3,
        const void *a4,
        __int64 a5)
{
  void *v5; // r14
  __int64 v6; // rbx
  unsigned __int64 v9; // r15
  char *v10; // rbp
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  size_t v13; // rcx
  void *v14; // rax
  _QWORD *v15; // rdi
  size_t v16; // r8
  __int64 v17; // r14
  char *v18; // r12
  size_t v19; // rbp
  _BYTE *v20; // rbx
  const struct std::nothrow_t *v21; // rdx
  _BYTE *v22; // rcx
  void **result; // rax

  v5 = Src[2];
  v6 = 0x7FFFFFFFFFFFFFFELL;
  if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v5 < a2 )
    std::_Xlen_string();
  v9 = (unsigned __int64)Src[3];
  v10 = (char *)v5 + a2;
  v11 = ((unsigned __int64)v5 + a2) | 7;
  if ( v11 <= 0x7FFFFFFFFFFFFFFELL && (v12 = v9 >> 1, v9 <= 0x7FFFFFFFFFFFFFFELL - (v9 >> 1)) )
  {
    v6 = v11;
    if ( v11 < v9 + v12 )
      v6 = v9 + v12;
    if ( (unsigned __int64)(v6 + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_25;
    v13 = 2 * (v6 + 1);
    if ( !v13 )
    {
      v15 = 0;
      goto LABEL_15;
    }
  }
  else
  {
    v13 = -2;
  }
  if ( v13 < 0x1000 )
  {
    v15 = operator new(v13);
    goto LABEL_15;
  }
  if ( v13 + 39 < v13 )
LABEL_25:
    __scrt_throw_std_bad_array_new_length();
  v14 = operator new(v13 + 39);
  if ( !v14 )
    goto LABEL_19;
  v15 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v15 - 1) = v14;
LABEL_15:
  v16 = 2LL * (_QWORD)v5;
  v17 = (__int64)v5 + a5;
  Src[2] = v10;
  Src[3] = (void *)v6;
  v18 = (char *)v15 + v16;
  v19 = 2 * a5;
  if ( v9 <= 7 )
  {
    memcpy_0(v15, Src, v16);
    memcpy_0(v18, a4, v19);
    *((_WORD *)v15 + v17) = 0;
    goto LABEL_23;
  }
  v20 = *Src;
  memcpy_0(v15, *Src, v16);
  memcpy_0(v18, a4, v19);
  v21 = (const struct std::nothrow_t *)(2 * v9 + 2);
  *((_WORD *)v15 + v17) = 0;
  if ( (unsigned __int64)v21 < 0x1000 )
  {
    v22 = v20;
    goto LABEL_21;
  }
  v22 = (_BYTE *)*((_QWORD *)v20 - 1);
  if ( (unsigned __int64)(v20 - v22 - 8) > 0x1F )
LABEL_19:
    __fastfail(5u);
  v21 = (const struct std::nothrow_t *)(2 * v9 + 41);
LABEL_21:
  operator delete(v22, v21);
LABEL_23:
  result = Src;
  *Src = v15;
  return result;
}

```

## disassembly

```asm
0x1400052b0  push    rbx
0x1400052b2  push    rbp
0x1400052b3  push    rsi
0x1400052b4  push    rdi
0x1400052b5  push    r12
0x1400052b7  push    r13
0x1400052b9  push    r14
0x1400052bb  push    r15
0x1400052bd  sub     rsp, 28h
0x1400052c1  mov     r14, [rcx+10h]
0x1400052c5  mov     rbx, 7FFFFFFFFFFFFFFEh
0x1400052cf  mov     rax, rbx
0x1400052d2  mov     r13, r9
0x1400052d5  sub     rax, r14
0x1400052d8  mov     rsi, rcx
0x1400052db  cmp     rax, rdx
0x1400052de  jb      loc_140005430
0x1400052e4  mov     r15, [rcx+18h]
0x1400052e8  lea     rbp, [r14+rdx]
0x1400052ec  mov     rcx, rbp
0x1400052ef  or      rcx, 7
0x1400052f3  cmp     rcx, rbx
0x1400052f6  ja      short loc_140005309
0x1400052f8  mov     rdx, r15
0x1400052fb  mov     rax, rbx
0x1400052fe  shr     rdx, 1
0x140005301  sub     rax, rdx
0x140005304  cmp     r15, rax
0x140005307  jbe     short loc_140005345
0x140005309  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x140005310  cmp     rcx, 1000h
0x140005317  jb      short loc_140005373
0x140005319  lea     rax, [rcx+27h]
0x14000531d  cmp     rax, rcx
0x140005320  jbe     loc_140005436
0x140005326  mov     rcx, rax; Size
0x140005329  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000532e  test    rax, rax
0x140005331  jz      loc_1400053EB
0x140005337  lea     rdi, [rax+27h]
0x14000533b  and     rdi, 0FFFFFFFFFFFFFFE0h
0x14000533f  mov     [rdi-8], rax
0x140005343  jmp     short loc_14000537B
0x140005345  lea     rax, [r15+rdx]
0x140005349  mov     rbx, rcx
0x14000534c  cmp     rcx, rax
0x14000534f  cmovb   rbx, rax
0x140005353  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000535d  lea     rcx, [rbx+1]
0x140005361  cmp     rcx, rax
0x140005364  ja      loc_140005436
0x14000536a  add     rcx, rcx
0x14000536d  jnz     short loc_140005310
0x14000536f  xor     edi, edi
0x140005371  jmp     short loc_14000537B
0x140005373  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005378  mov     rdi, rax
0x14000537b  mov     rdx, [rsp+68h+arg_20]
0x140005383  lea     r8, [r14+r14]; Size
0x140005387  add     r14, rdx
0x14000538a  mov     [rsi+10h], rbp
0x14000538e  mov     [rsi+18h], rbx
0x140005392  lea     r12, [r8+rdi]
0x140005396  mov     rcx, rdi; void *
0x140005399  lea     rbp, [rdx+rdx]
0x14000539d  cmp     r15, 7
0x1400053a1  jbe     short loc_1400053FC
0x1400053a3  mov     rbx, [rsi]
0x1400053a6  mov     rdx, rbx; Src
0x1400053a9  call    memcpy_0
0x1400053ae  mov     r8, rbp; Size
0x1400053b1  mov     rdx, r13; Src
0x1400053b4  mov     rcx, r12; void *
0x1400053b7  call    memcpy_0
0x1400053bc  xor     eax, eax
0x1400053be  lea     rdx, ds:2[r15*2]; struct std::nothrow_t *
0x1400053c6  mov     [rdi+r14*2], ax
0x1400053cb  cmp     rdx, 1000h
0x1400053d2  jb      short loc_1400053F2
0x1400053d4  mov     rcx, [rbx-8]
0x1400053d8  sub     rbx, rcx
0x1400053db  sub     rbx, 8
0x1400053df  cmp     rbx, 1Fh
0x1400053e3  ja      short loc_1400053EB
0x1400053e5  add     rdx, 27h ; '''
0x1400053e9  jmp     short loc_1400053F5
0x1400053eb  mov     ecx, 5
0x1400053f0  int     29h; Win8: RtlFailFast(ecx)
0x1400053f2  mov     rcx, rbx; void *
0x1400053f5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400053fa  jmp     short loc_140005419
0x1400053fc  mov     rdx, rsi; Src
0x1400053ff  call    memcpy_0
0x140005404  mov     r8, rbp; Size
0x140005407  mov     rdx, r13; Src
0x14000540a  mov     rcx, r12; void *
0x14000540d  call    memcpy_0
0x140005412  xor     eax, eax
0x140005414  mov     [rdi+r14*2], ax
0x140005419  mov     rax, rsi
0x14000541c  mov     [rax], rdi
0x14000541f  add     rsp, 28h
0x140005423  pop     r15
0x140005425  pop     r14
0x140005427  pop     r13
0x140005429  pop     r12
0x14000542b  pop     rdi
0x14000542c  pop     rsi
0x14000542d  pop     rbp
0x14000542e  pop     rbx
0x14000542f  retn
0x140005430  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x140005436  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
