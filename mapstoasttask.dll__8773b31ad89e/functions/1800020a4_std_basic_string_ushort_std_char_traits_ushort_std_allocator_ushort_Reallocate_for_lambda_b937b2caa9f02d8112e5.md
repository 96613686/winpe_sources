# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)

- ea: `0x1800020a4`
- end: `0x1800021dc`
- name: `??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z`
- size: `312`
- prototype: `char **__fastcall(char **, unsigned __int64, __int64, const void *)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000374c`
- `0x1800038e4`
- `0x1800040f0`
- `0x180005e60`
- `0x180007450`

## callees

- `0x1800015d4`
- `0x180001624`
- `0x1800020a4`
- `0x1800063b4`
- `0x1800063dc`
- `0x180009540`

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
  char *v15; // rcx
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
      goto LABEL_23;
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
LABEL_23:
    __scrt_throw_std_bad_array_new_length();
  v12 = operator new(v11 + 39);
  if ( !v12 )
    goto LABEL_18;
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
    if ( 2 * v8 + 2 < 0x1000 )
    {
      v15 = *a1;
    }
    else
    {
      v15 = (char *)*((_QWORD *)v14 - 1);
      if ( (unsigned __int64)(v14 - v15 - 8) > 0x1F )
LABEL_18:
        __fastfail(5u);
    }
    operator delete(v15);
  }
  result = a1;
  *a1 = (char *)v13;
  return result;
}

```

## disassembly

```asm
0x1800020a4  push    rbx
0x1800020a6  push    rbp
0x1800020a7  push    rsi
0x1800020a8  push    rdi
0x1800020a9  push    r14
0x1800020ab  push    r15
0x1800020ad  sub     rsp, 28h
0x1800020b1  mov     rbx, 7FFFFFFFFFFFFFFEh
0x1800020bb  mov     r15, r9
0x1800020be  mov     r14, rdx
0x1800020c1  mov     rdi, rcx
0x1800020c4  cmp     rdx, rbx
0x1800020c7  ja      loc_1800021D0
0x1800020cd  mov     rbp, [rcx+18h]
0x1800020d1  mov     rcx, rdx
0x1800020d4  or      rcx, 7
0x1800020d8  cmp     rcx, rbx
0x1800020db  ja      short loc_1800020EE
0x1800020dd  mov     rdx, rbp
0x1800020e0  mov     rax, rbx
0x1800020e3  shr     rdx, 1
0x1800020e6  sub     rax, rdx
0x1800020e9  cmp     rbp, rax
0x1800020ec  jbe     short loc_18000212A
0x1800020ee  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x1800020f5  cmp     rcx, 1000h
0x1800020fc  jb      short loc_180002155
0x1800020fe  lea     rax, [rcx+27h]
0x180002102  cmp     rax, rcx
0x180002105  jbe     loc_1800021D6
0x18000210b  mov     rcx, rax; Size
0x18000210e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002113  test    rax, rax
0x180002116  jz      loc_1800021AE
0x18000211c  lea     rsi, [rax+27h]
0x180002120  and     rsi, 0FFFFFFFFFFFFFFE0h
0x180002124  mov     [rsi-8], rax
0x180002128  jmp     short loc_18000215D
0x18000212a  lea     rbx, [rdx+rbp]
0x18000212e  mov     rax, 7FFFFFFFFFFFFFFFh
0x180002138  cmp     rcx, rbx
0x18000213b  cmovnb  rbx, rcx
0x18000213f  lea     rcx, [rbx+1]
0x180002143  cmp     rcx, rax
0x180002146  ja      loc_1800021D6
0x18000214c  add     rcx, rcx
0x18000214f  jnz     short loc_1800020F5
0x180002151  xor     esi, esi
0x180002153  jmp     short loc_18000215D
0x180002155  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000215a  mov     rsi, rax
0x18000215d  mov     [rdi+18h], rbx
0x180002161  mov     rdx, r15; Src
0x180002164  lea     rbx, [r14+r14]
0x180002168  mov     [rdi+10h], r14
0x18000216c  mov     r8, rbx; Size
0x18000216f  mov     rcx, rsi; void *
0x180002172  call    memcpy_0
0x180002177  xor     ecx, ecx
0x180002179  mov     [rbx+rsi], cx
0x18000217d  cmp     rbp, 7
0x180002181  jbe     short loc_1800021BD
0x180002183  mov     rax, [rdi]
0x180002186  lea     rdx, ds:2[rbp*2]
0x18000218e  cmp     rdx, 1000h
0x180002195  jb      short loc_1800021B5
0x180002197  mov     rcx, [rax-8]
0x18000219b  sub     rax, rcx
0x18000219e  sub     rax, 8
0x1800021a2  cmp     rax, 1Fh
0x1800021a6  ja      short loc_1800021AE
0x1800021a8  add     rdx, 27h ; '''
0x1800021ac  jmp     short loc_1800021B8
0x1800021ae  mov     ecx, 5
0x1800021b3  int     29h; Win8: RtlFailFast(ecx)
0x1800021b5  mov     rcx, rax; Block
0x1800021b8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800021bd  mov     rax, rdi
0x1800021c0  mov     [rax], rsi
0x1800021c3  add     rsp, 28h
0x1800021c7  pop     r15
0x1800021c9  pop     r14
0x1800021cb  pop     rdi
0x1800021cc  pop     rsi
0x1800021cd  pop     rbp
0x1800021ce  pop     rbx
0x1800021cf  retn
0x1800021d0  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1800021d6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
