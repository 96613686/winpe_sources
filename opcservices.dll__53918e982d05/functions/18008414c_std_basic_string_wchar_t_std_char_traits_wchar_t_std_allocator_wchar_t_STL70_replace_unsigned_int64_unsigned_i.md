# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>::replace(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)

- ea: `0x18008414c`
- end: `0x18008439b`
- name: `?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_K0PEB_W0@Z`
- size: `591`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180041e88`
- `0x180062d30`
- `0x18008407c`

## callees

- `0x1800190e0`
- `0x18008414c`
- `0x1800cded0`
- `0x1800cdf2c`
- `0x1800dea78`

## import_xrefs

- `msvcrt!memmove_s` at `0x18008425a`
- `msvcrt!memmove_s` at `0x180084361`
- `msvcrt!memmove_s` at `0x18008425a`
- `msvcrt!memmove_s` at `0x180084361`
- `msvcrt!memcpy_s` at `0x18008427e`
- `msvcrt!memcpy_s` at `0x18008427e`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        char *a4,
        unsigned __int64 a5)
{
  char *v5; // rbx
  unsigned __int64 v7; // rsi
  char *v10; // rax
  _QWORD *v11; // rcx
  unsigned __int64 v12; // r13
  unsigned __int64 v13; // rbp
  unsigned __int64 v14; // rdx
  _QWORD *v15; // rcx
  _QWORD *v16; // r8
  unsigned __int64 v17; // rdx
  _QWORD *v18; // rax
  unsigned __int64 v20; // rdx
  _QWORD *v21; // rcx
  _QWORD *v22; // r8

  v5 = (char *)(a1 + 1);
  v7 = a3;
  if ( a1[4] < 8u )
    v10 = (char *)(a1 + 1);
  else
    v10 = *(char **)v5;
  if ( a4 < v10 || (a1[4] < 8u ? (v11 = a1 + 1) : (v11 = *(_QWORD **)v5), (char *)v11 + 2 * a1[3] <= a4) )
  {
    if ( a1[3] < a2 )
      std::_String_base::_Xran();
    if ( a1[3] - a2 < a3 )
      v7 = a1[3] - a2;
    if ( ~a5 <= a1[3] - v7 )
      std::_String_base::_Xlen();
    v12 = a1[3] - a2 - v7;
    if ( a5 < v7 )
    {
      v20 = a1[4];
      if ( v20 < 8 )
      {
        v21 = v5;
        v22 = v5;
      }
      else
      {
        v21 = *(_QWORD **)v5;
        v22 = *(_QWORD **)v5;
      }
      memmove_s((char *)v21 + 2 * a2 + 2 * a5, 2 * (v20 - a2 - a5), (char *)v22 + 2 * a2 + 2 * v7, 2 * v12);
    }
    if ( !a5 && !v7 )
      return a1;
    v13 = a5 + a1[3] - v7;
    if ( v13 > 0x7FFFFFFFFFFFFFFELL )
      std::_String_base::_Xlen();
    if ( a1[4] < v13 )
    {
      std::wstring::_Copy(a1, a5 + a1[3] - v7, a1[3]);
      if ( !v13 )
        return a1;
    }
    else if ( !v13 )
    {
      if ( a1[4] >= 8u )
        v5 = *(char **)v5;
      a1[3] = 0;
      *(_WORD *)v5 = 0;
      return a1;
    }
    if ( v7 < a5 )
    {
      v14 = a1[4];
      if ( v14 < 8 )
      {
        v15 = v5;
        v16 = v5;
      }
      else
      {
        v15 = *(_QWORD **)v5;
        v16 = *(_QWORD **)v5;
      }
      memmove_s((char *)v15 + 2 * a2 + 2 * a5, 2 * (v14 - a2 - a5), (char *)v16 + 2 * a2 + 2 * v7, 2 * v12);
    }
    v17 = a1[4];
    if ( v17 < 8 )
      v18 = v5;
    else
      v18 = *(_QWORD **)v5;
    memcpy_s((char *)v18 + 2 * a2, 2 * (v17 - a2), a4, 2 * a5);
    if ( a1[4] >= 8u )
      v5 = *(char **)v5;
    a1[3] = v13;
    *(_WORD *)&v5[2 * v13] = 0;
    return a1;
  }
  if ( a1[4] >= 8u )
    v5 = *(char **)v5;
  return std::wstring::replace(a1, a2, a3, a1, (a4 - v5) >> 1, a5);
}

```

## disassembly

```asm
0x18008414c  push    rbx
0x18008414e  push    rbp
0x18008414f  push    rsi
0x180084150  push    rdi
0x180084151  push    r12
0x180084153  push    r13
0x180084155  push    r14
0x180084157  push    r15
0x180084159  sub     rsp, 38h
0x18008415d  cmp     qword ptr [rcx+20h], 8
0x180084162  lea     rbx, [rcx+8]
0x180084166  mov     r12, r9
0x180084169  mov     rsi, r8
0x18008416c  mov     r15, rdx
0x18008416f  mov     rdi, rcx
0x180084172  jb      loc_1800842C5
0x180084178  mov     rax, [rbx]
0x18008417b  cmp     r12, rax
0x18008417e  jb      short loc_18008419F
0x180084180  cmp     qword ptr [rcx+20h], 8
0x180084185  jb      loc_1800842CD
0x18008418b  mov     rcx, [rbx]
0x18008418e  mov     rax, [rdi+18h]
0x180084192  lea     rcx, [rcx+rax*2]
0x180084196  cmp     rcx, r12
0x180084199  ja      loc_1800842FE
0x18008419f  cmp     [rdi+18h], r15
0x1800841a3  jb      loc_180084374
0x1800841a9  mov     rcx, [rdi+18h]
0x1800841ad  mov     r14, [rsp+78h+arg_20]
0x1800841b5  mov     rax, rcx
0x1800841b8  sub     rax, r15
0x1800841bb  cmp     rax, rsi
0x1800841be  cmovb   rsi, rax
0x1800841c2  mov     rax, r14
0x1800841c5  not     rax
0x1800841c8  sub     rcx, rsi
0x1800841cb  cmp     rax, rcx
0x1800841ce  jbe     loc_18008437E
0x1800841d4  mov     r13, [rdi+18h]
0x1800841d8  sub     r13, r15
0x1800841db  sub     r13, rsi
0x1800841de  cmp     r14, rsi
0x1800841e1  jb      loc_180084330
0x1800841e7  test    r14, r14
0x1800841ea  jz      loc_180084388
0x1800841f0  mov     rbp, [rdi+18h]
0x1800841f4  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800841fe  sub     rbp, rsi
0x180084201  add     rbp, r14
0x180084204  cmp     rbp, rax
0x180084207  ja      loc_180084396
0x18008420d  cmp     [rdi+20h], rbp
0x180084211  jb      loc_1800842AC
0x180084217  test    rbp, rbp
0x18008421a  jz      loc_1800842E5
0x180084220  cmp     rsi, r14
0x180084223  jnb     short loc_180084260
0x180084225  mov     rdx, [rdi+20h]
0x180084229  cmp     rdx, 8
0x18008422d  jb      loc_1800842DA
0x180084233  mov     rcx, [rbx]
0x180084236  mov     r8, rcx
0x180084239  sub     rdx, r15
0x18008423c  lea     rax, [r15+rsi]
0x180084240  lea     r8, [r8+rax*2]; Source
0x180084244  sub     rdx, r14
0x180084247  lea     rax, [r15+r14]
0x18008424b  add     rdx, rdx; DestinationSize
0x18008424e  lea     rcx, [rcx+rax*2]; Destination
0x180084252  lea     r9, ds:0[r13*2]; SourceSize
0x18008425a  call    cs:__imp_memmove_s
0x180084260  mov     rdx, [rdi+20h]
0x180084264  cmp     rdx, 8
0x180084268  jb      short loc_1800842D5
0x18008426a  mov     rax, [rbx]
0x18008426d  sub     rdx, r15
0x180084270  lea     r9, [r14+r14]; SourceSize
0x180084274  add     rdx, rdx; DestinationSize
0x180084277  lea     rcx, [rax+r15*2]; Destination
0x18008427b  mov     r8, r12; Source
0x18008427e  call    cs:__imp_memcpy_s
0x180084284  cmp     qword ptr [rdi+20h], 8
0x180084289  jb      short loc_18008428E
0x18008428b  mov     rbx, [rbx]
0x18008428e  xor     eax, eax
0x180084290  mov     [rdi+18h], rbp
0x180084294  mov     [rbx+rbp*2], ax
0x180084298  mov     rax, rdi
0x18008429b  add     rsp, 38h
0x18008429f  pop     r15
0x1800842a1  pop     r14
0x1800842a3  pop     r13
0x1800842a5  pop     r12
0x1800842a7  pop     rdi
0x1800842a8  pop     rsi
0x1800842a9  pop     rbp
0x1800842aa  pop     rbx
0x1800842ab  retn
0x1800842ac  mov     r8, [rdi+18h]
0x1800842b0  mov     rdx, rbp
0x1800842b3  mov     rcx, rdi
0x1800842b6  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x1800842bb  test    rbp, rbp
0x1800842be  jz      short loc_180084298
0x1800842c0  jmp     loc_180084220
0x1800842c5  mov     rax, rbx
0x1800842c8  jmp     loc_18008417B
0x1800842cd  mov     rcx, rbx
0x1800842d0  jmp     loc_18008418E
0x1800842d5  mov     rax, rbx
0x1800842d8  jmp     short loc_18008426D
0x1800842da  mov     rcx, rbx
0x1800842dd  mov     r8, rbx
0x1800842e0  jmp     loc_180084239
0x1800842e5  cmp     qword ptr [rdi+20h], 8
0x1800842ea  jb      short loc_1800842EF
0x1800842ec  mov     rbx, [rbx]
0x1800842ef  xor     eax, eax
0x1800842f1  mov     qword ptr [rdi+18h], 0
0x1800842f9  mov     [rbx], ax
0x1800842fc  jmp     short loc_180084298
0x1800842fe  cmp     qword ptr [rdi+20h], 8
0x180084303  jb      short loc_180084308
0x180084305  mov     rbx, [rbx]
0x180084308  mov     rax, [rsp+78h+arg_20]
0x180084310  sub     r12, rbx
0x180084313  sar     r12, 1
0x180084316  mov     r9, rdi
0x180084319  mov     [rsp+78h+var_50], rax
0x18008431e  mov     rcx, rdi
0x180084321  mov     [rsp+78h+var_58], r12
0x180084326  call    ?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_K0AEBV12@00@Z; std::wstring::replace(unsigned __int64,unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x18008432b  jmp     loc_18008429B
0x180084330  mov     rdx, [rdi+20h]
0x180084334  cmp     rdx, 8
0x180084338  jb      short loc_18008436C
0x18008433a  mov     rcx, [rbx]
0x18008433d  mov     r8, rcx
0x180084340  sub     rdx, r15
0x180084343  lea     rax, [r15+rsi]
0x180084347  lea     r8, [r8+rax*2]; Source
0x18008434b  sub     rdx, r14
0x18008434e  lea     rax, [r15+r14]
0x180084352  add     rdx, rdx; DestinationSize
0x180084355  lea     rcx, [rcx+rax*2]; Destination
0x180084359  lea     r9, ds:0[r13*2]; SourceSize
0x180084361  call    cs:__imp_memmove_s
0x180084367  jmp     loc_1800841E7
0x18008436c  mov     rcx, rbx
0x18008436f  mov     r8, rbx
0x180084372  jmp     short loc_180084340
0x180084374  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x180084379  jmp     loc_1800841A9
0x18008437e  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x180084383  jmp     loc_1800841D4
0x180084388  test    rsi, rsi
0x18008438b  jz      loc_180084298
0x180084391  jmp     loc_1800841F0
0x180084396  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
```
