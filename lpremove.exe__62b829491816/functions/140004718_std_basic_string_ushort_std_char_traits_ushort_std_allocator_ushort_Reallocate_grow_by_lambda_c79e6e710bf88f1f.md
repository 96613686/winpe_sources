# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)

- ea: `0x140004718`
- end: `0x14000484f`
- name: `??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z`
- size: `311`
- prototype: `void **__fastcall(void **Src, unsigned __int64, __int64, const void *, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1400081a8`
- `0x14000c36c`
- `0x14000cef4`
- `0x14000f530`

## callees

- `0x1400021b4`
- `0x140003211`
- `0x14000422c`
- `0x140004718`
- `0x14000cea0`

## pseudocode

```c
void **__fastcall std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
        void **Src,
        unsigned __int64 a2,
        __int64 a3,
        const void *a4,
        __int64 a5)
{
  void *v5; // rbx
  __int64 v6; // r8
  unsigned __int64 v9; // r14
  char *v10; // rbp
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  _QWORD *v13; // rax
  __int64 v14; // rdx
  size_t v15; // r8
  void *v16; // rcx
  _QWORD *v17; // rsi
  char *v18; // r15
  size_t v19; // rbp
  __int64 v20; // r12
  _BYTE *v21; // rbx
  _BYTE *v22; // rcx
  void **result; // rax
  __int64 v24; // [rsp+70h] [rbp+8h] BYREF

  v5 = Src[2];
  v6 = 0x7FFFFFFFFFFFFFFELL;
  if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v5 < a2 )
    std::_Xlen_string();
  v9 = (unsigned __int64)Src[3];
  v10 = (char *)v5 + a2;
  v11 = ((unsigned __int64)v5 + a2) | 7;
  if ( v11 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v12 = v9 >> 1;
    if ( v9 <= 0x7FFFFFFFFFFFFFFELL - (v9 >> 1) )
    {
      v6 = v9 + v12;
      if ( v11 >= v9 + v12 )
        v6 = v11;
    }
  }
  v24 = v6;
  v13 = std::wstring::_Allocate_for_capacity<0>(v11, &v24);
  v14 = a5;
  v15 = 2LL * (_QWORD)v5;
  v16 = (void *)v24;
  v17 = v13;
  Src[2] = v10;
  Src[3] = v16;
  v18 = (char *)v13 + 2 * (_QWORD)v5;
  v19 = 2 * v14;
  v20 = (__int64)v5 + v14;
  if ( v9 <= 7 )
  {
    memcpy_0(v13, Src, v15);
    memcpy_0(v18, a4, v19);
    *((_WORD *)v17 + v20) = 0;
  }
  else
  {
    v21 = *Src;
    memcpy_0(v13, *Src, v15);
    memcpy_0(v18, a4, v19);
    *((_WORD *)v17 + v20) = 0;
    if ( 2 * v9 + 2 < 0x1000 )
    {
      v22 = v21;
    }
    else
    {
      v22 = (_BYTE *)*((_QWORD *)v21 - 1);
      if ( (unsigned __int64)(v21 - v22 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v22);
  }
  result = Src;
  *Src = v17;
  return result;
}

```

## disassembly

```asm
0x140004718  push    rbx
0x14000471a  push    rbp
0x14000471b  push    rsi
0x14000471c  push    rdi
0x14000471d  push    r12
0x14000471f  push    r13
0x140004721  push    r14
0x140004723  push    r15
0x140004725  sub     rsp, 28h
0x140004729  mov     rbx, [rcx+10h]
0x14000472d  mov     r8, 7FFFFFFFFFFFFFFEh
0x140004737  mov     rax, r8
0x14000473a  mov     r13, r9
0x14000473d  sub     rax, rbx
0x140004740  mov     rdi, rcx
0x140004743  cmp     rax, rdx
0x140004746  jb      loc_140004849
0x14000474c  mov     r14, [rcx+18h]
0x140004750  lea     rbp, [rbx+rdx]
0x140004754  mov     rcx, rbp
0x140004757  or      rcx, 7
0x14000475b  cmp     rcx, r8
0x14000475e  ja      short loc_14000477C
0x140004760  mov     rdx, r14
0x140004763  mov     rax, r8
0x140004766  shr     rdx, 1
0x140004769  sub     rax, rdx
0x14000476c  cmp     r14, rax
0x14000476f  ja      short loc_14000477C
0x140004771  lea     r8, [r14+rdx]
0x140004775  cmp     rcx, r8
0x140004778  cmovnb  r8, rcx
0x14000477c  lea     rdx, [rsp+68h+arg_0]
0x140004781  mov     [rsp+68h+arg_0], r8
0x140004786  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x14000478b  mov     rdx, [rsp+68h+arg_20]
0x140004793  lea     r8, [rbx+rbx]; Size
0x140004797  mov     rcx, [rsp+68h+arg_0]
0x14000479c  mov     rsi, rax
0x14000479f  mov     [rdi+10h], rbp
0x1400047a3  mov     [rdi+18h], rcx
0x1400047a7  lea     r15, [r8+rax]
0x1400047ab  lea     rbp, [rdx+rdx]
0x1400047af  mov     rcx, rax; void *
0x1400047b2  lea     r12, [rbx+rdx]
0x1400047b6  cmp     r14, 7
0x1400047ba  jbe     short loc_140004815
0x1400047bc  mov     rbx, [rdi]
0x1400047bf  mov     rdx, rbx; Src
0x1400047c2  call    memcpy_0
0x1400047c7  mov     r8, rbp; Size
0x1400047ca  mov     rdx, r13; Src
0x1400047cd  mov     rcx, r15; void *
0x1400047d0  call    memcpy_0
0x1400047d5  xor     eax, eax
0x1400047d7  lea     rdx, ds:2[r14*2]
0x1400047df  mov     [rsi+r12*2], ax
0x1400047e4  cmp     rdx, 1000h
0x1400047eb  jb      short loc_14000480B
0x1400047ed  mov     rcx, [rbx-8]
0x1400047f1  sub     rbx, rcx
0x1400047f4  sub     rbx, 8
0x1400047f8  cmp     rbx, 1Fh
0x1400047fc  ja      short loc_140004804
0x1400047fe  add     rdx, 27h ; '''
0x140004802  jmp     short loc_14000480E
0x140004804  mov     ecx, 5
0x140004809  int     29h; Win8: RtlFailFast(ecx)
0x14000480b  mov     rcx, rbx; Block
0x14000480e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004813  jmp     short loc_140004832
0x140004815  mov     rdx, rdi; Src
0x140004818  call    memcpy_0
0x14000481d  mov     r8, rbp; Size
0x140004820  mov     rdx, r13; Src
0x140004823  mov     rcx, r15; void *
0x140004826  call    memcpy_0
0x14000482b  xor     eax, eax
0x14000482d  mov     [rsi+r12*2], ax
0x140004832  mov     rax, rdi
0x140004835  mov     [rax], rsi
0x140004838  add     rsp, 28h
0x14000483c  pop     r15
0x14000483e  pop     r14
0x140004840  pop     r13
0x140004842  pop     r12
0x140004844  pop     rdi
0x140004845  pop     rsi
0x140004846  pop     rbp
0x140004847  pop     rbx
0x140004848  retn
0x140004849  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
