# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)

- ea: `0x140002d90`
- end: `0x140002ec8`
- name: `??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z`
- size: `312`
- prototype: `char **__fastcall(char **, unsigned __int64, __int64, const void *)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140003154`
- `0x140006c30`
- `0x140008590`
- `0x14000b144`

## callees

- `0x140001c74`
- `0x140001cb8`
- `0x1400027ba`
- `0x140002d90`
- `0x140003580`
- `0x1400035a8`

## pseudocode

```c
char **__fastcall std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        char **a1,
        unsigned __int64 a2,
        __int64 a3,
        const void *a4)
{
  __int64 v4; // rbx
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  size_t v11; // rcx
  void *v12; // rax
  _QWORD *v13; // rsi
  char *v14; // rax
  const struct std::nothrow_t *v15; // rdx
  char *v16; // rcx
  char **result; // rax

  v4 = 0x7FFFFFFFFFFFFFFELL;
  if ( a2 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  v8 = (unsigned __int64)a1[3];
  v9 = a2 | 7;
  if ( (a2 | 7) <= 0x7FFFFFFFFFFFFFFELL && (v10 = v8 >> 1, v8 <= 0x7FFFFFFFFFFFFFFELL - (v8 >> 1)) )
  {
    v4 = v10 + v8;
    if ( v9 >= v10 + v8 )
      v4 = v9;
    if ( (unsigned __int64)(v4 + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_24;
    v11 = 2 * (v4 + 1);
    if ( !v11 )
    {
      v13 = 0;
      goto LABEL_15;
    }
  }
  else
  {
    v11 = -2;
  }
  if ( v11 < 0x1000 )
  {
    v13 = operator new(v11);
    goto LABEL_15;
  }
  if ( v11 + 39 < v11 )
LABEL_24:
    __scrt_throw_std_bad_array_new_length();
  v12 = operator new(v11 + 39);
  if ( !v12 )
    goto LABEL_19;
  v13 = (_QWORD *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v12;
LABEL_15:
  a1[3] = (char *)v4;
  a1[2] = (char *)a2;
  memcpy_0(v13, a4, 2 * a2);
  *((_WORD *)v13 + a2) = 0;
  if ( v8 > 7 )
  {
    v14 = *a1;
    v15 = (const struct std::nothrow_t *)(2 * v8 + 2);
    if ( (unsigned __int64)v15 < 0x1000 )
    {
      v16 = *a1;
      goto LABEL_21;
    }
    v16 = (char *)*((_QWORD *)v14 - 1);
    if ( (unsigned __int64)(v14 - v16 - 8) <= 0x1F )
    {
      v15 = (const struct std::nothrow_t *)(2 * v8 + 41);
LABEL_21:
      operator delete(v16, v15);
      goto LABEL_22;
    }
LABEL_19:
    __fastfail(5u);
  }
LABEL_22:
  result = a1;
  *a1 = (char *)v13;
  return result;
}

```

## disassembly

```asm
0x140002d90  push    rbx
0x140002d92  push    rbp
0x140002d93  push    rsi
0x140002d94  push    rdi
0x140002d95  push    r14
0x140002d97  push    r15
0x140002d99  sub     rsp, 28h
0x140002d9d  mov     rbx, 7FFFFFFFFFFFFFFEh
0x140002da7  mov     r15, r9
0x140002daa  mov     r14, rdx
0x140002dad  mov     rdi, rcx
0x140002db0  cmp     rdx, rbx
0x140002db3  ja      loc_140002EBC
0x140002db9  mov     rbp, [rcx+18h]
0x140002dbd  mov     rcx, rdx
0x140002dc0  or      rcx, 7
0x140002dc4  cmp     rcx, rbx
0x140002dc7  ja      short loc_140002DDA
0x140002dc9  mov     rdx, rbp
0x140002dcc  mov     rax, rbx
0x140002dcf  shr     rdx, 1
0x140002dd2  sub     rax, rdx
0x140002dd5  cmp     rbp, rax
0x140002dd8  jbe     short loc_140002E16
0x140002dda  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x140002de1  cmp     rcx, 1000h
0x140002de8  jb      short loc_140002E41
0x140002dea  lea     rax, [rcx+27h]
0x140002dee  cmp     rax, rcx
0x140002df1  jbe     loc_140002EC2
0x140002df7  mov     rcx, rax; Size
0x140002dfa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002dff  test    rax, rax
0x140002e02  jz      loc_140002E9A
0x140002e08  lea     rsi, [rax+27h]
0x140002e0c  and     rsi, 0FFFFFFFFFFFFFFE0h
0x140002e10  mov     [rsi-8], rax
0x140002e14  jmp     short loc_140002E49
0x140002e16  lea     rbx, [rdx+rbp]
0x140002e1a  mov     rax, 7FFFFFFFFFFFFFFFh
0x140002e24  cmp     rcx, rbx
0x140002e27  cmovnb  rbx, rcx
0x140002e2b  lea     rcx, [rbx+1]
0x140002e2f  cmp     rcx, rax
0x140002e32  ja      loc_140002EC2
0x140002e38  add     rcx, rcx
0x140002e3b  jnz     short loc_140002DE1
0x140002e3d  xor     esi, esi
0x140002e3f  jmp     short loc_140002E49
0x140002e41  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002e46  mov     rsi, rax
0x140002e49  mov     [rdi+18h], rbx
0x140002e4d  mov     rdx, r15; Src
0x140002e50  lea     rbx, [r14+r14]
0x140002e54  mov     [rdi+10h], r14
0x140002e58  mov     r8, rbx; Size
0x140002e5b  mov     rcx, rsi; void *
0x140002e5e  call    memcpy_0
0x140002e63  xor     ecx, ecx
0x140002e65  mov     [rbx+rsi], cx
0x140002e69  cmp     rbp, 7
0x140002e6d  jbe     short loc_140002EA9
0x140002e6f  mov     rax, [rdi]
0x140002e72  lea     rdx, ds:2[rbp*2]; struct std::nothrow_t *
0x140002e7a  cmp     rdx, 1000h
0x140002e81  jb      short loc_140002EA1
0x140002e83  mov     rcx, [rax-8]
0x140002e87  sub     rax, rcx
0x140002e8a  sub     rax, 8
0x140002e8e  cmp     rax, 1Fh
0x140002e92  ja      short loc_140002E9A
0x140002e94  add     rdx, 27h ; '''
0x140002e98  jmp     short loc_140002EA4
0x140002e9a  mov     ecx, 5
0x140002e9f  int     29h; Win8: RtlFailFast(ecx)
0x140002ea1  mov     rcx, rax; void *
0x140002ea4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140002ea9  mov     rax, rdi
0x140002eac  mov     [rax], rsi
0x140002eaf  add     rsp, 28h
0x140002eb3  pop     r15
0x140002eb5  pop     r14
0x140002eb7  pop     rdi
0x140002eb8  pop     rsi
0x140002eb9  pop     rbp
0x140002eba  pop     rbx
0x140002ebb  retn
0x140002ebc  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x140002ec2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
