# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::replace(unsigned __int64,unsigned __int64,char const *,unsigned __int64)

- ea: `0x1800bcdac`
- end: `0x1800bcf41`
- name: `?replace@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0PEBD0@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800bcd14`

## callees

- `0x18001d2c0`
- `0x18001edc4`
- `0x180083f38`
- `0x1800bcdac`
- `0x1800cded0`
- `0x1800cdf2c`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800bce87`
- `msvcrt!memmove_s` at `0x1800bceef`
- `msvcrt!memmove_s` at `0x1800bce87`
- `msvcrt!memmove_s` at `0x1800bceef`
- `msvcrt!memcpy_s` at `0x1800bcf14`
- `msvcrt!memcpy_s` at `0x1800bcf14`

## pseudocode

```c
_QWORD *__fastcall std::string::replace(_QWORD *a1, unsigned __int64 a2, rsize_t a3, _BYTE *a4, rsize_t SourceSize)
{
  _QWORD *v9; // rax
  _QWORD *v11; // rdi
  rsize_t v12; // r15
  unsigned __int64 v13; // rdx
  _QWORD *v14; // rax
  _QWORD *v15; // rcx
  rsize_t v16; // r13
  unsigned __int64 v17; // rdx
  _QWORD *v18; // rax
  _QWORD *v19; // rcx
  unsigned __int64 v20; // rdx
  _QWORD *v21; // rax

  if ( (unsigned __int8)std::string::_Inside(a1, a4) )
  {
    v9 = a1 + 1;
    if ( a1[4] >= 0x10u )
      v9 = (_QWORD *)*v9;
    return std::string::replace(a1, a2, a3, a1, a4 - (_BYTE *)v9, SourceSize);
  }
  else
  {
    if ( a1[3] < a2 )
      std::_String_base::_Xran();
    if ( a1[3] - a2 < a3 )
      a3 = a1[3] - a2;
    if ( ~SourceSize <= a1[3] - a3 )
      std::_String_base::_Xlen();
    v11 = a1 + 1;
    v12 = a1[3] - a2 - a3;
    if ( SourceSize < a3 )
    {
      v13 = a1[4];
      if ( v13 < 0x10 )
      {
        v14 = a1 + 1;
        v15 = a1 + 1;
      }
      else
      {
        v14 = (_QWORD *)*v11;
        v15 = (_QWORD *)*v11;
      }
      memmove_s((char *)v14 + a2 + SourceSize, v13 - a2 - SourceSize, (char *)v15 + a2 + a3, a1[3] - a2 - a3);
    }
    if ( SourceSize || a3 )
    {
      v16 = SourceSize + a1[3] - a3;
      if ( (unsigned __int8)std::string::_Grow(a1, v16, 0) )
      {
        if ( a3 < SourceSize )
        {
          v17 = a1[4];
          v11 = a1 + 1;
          if ( v17 < 0x10 )
          {
            v18 = a1 + 1;
            v19 = a1 + 1;
          }
          else
          {
            v18 = (_QWORD *)*v11;
            v19 = (_QWORD *)*v11;
          }
          memmove_s((char *)v18 + a2 + SourceSize, v17 - a2 - SourceSize, (char *)v19 + a2 + a3, v12);
        }
        v20 = a1[4];
        if ( v20 < 0x10 )
          v21 = v11;
        else
          v21 = (_QWORD *)*v11;
        memcpy_s((char *)v21 + a2, v20 - a2, a4, SourceSize);
        if ( a1[4] >= 0x10u )
          v11 = (_QWORD *)*v11;
        a1[3] = v16;
        *((_BYTE *)v11 + v16) = 0;
      }
    }
    return a1;
  }
}

```

## disassembly

```asm
0x1800bcdac  push    rbx
0x1800bcdae  push    rbp
0x1800bcdaf  push    rsi
0x1800bcdb0  push    rdi
0x1800bcdb1  push    r12
0x1800bcdb3  push    r13
0x1800bcdb5  push    r14
0x1800bcdb7  push    r15
0x1800bcdb9  sub     rsp, 38h
0x1800bcdbd  mov     rbp, rdx
0x1800bcdc0  mov     r12, r9
0x1800bcdc3  mov     rdx, r9
0x1800bcdc6  mov     rsi, r8
0x1800bcdc9  mov     rbx, rcx
0x1800bcdcc  call    ?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAA_NPEBD@Z; std::string::_Inside(char const *)
0x1800bcdd1  test    al, al
0x1800bcdd3  jz      short loc_1800BCE0E
0x1800bcdd5  cmp     qword ptr [rbx+20h], 10h
0x1800bcdda  lea     rax, [rbx+8]
0x1800bcdde  jb      short loc_1800BCDE3
0x1800bcde0  mov     rax, [rax]
0x1800bcde3  sub     r12, rax
0x1800bcde6  mov     r9, rbx
0x1800bcde9  mov     rax, [rsp+78h+SourceSize]
0x1800bcdf1  mov     r8, rsi
0x1800bcdf4  mov     [rsp+78h+var_50], rax
0x1800bcdf9  mov     rdx, rbp
0x1800bcdfc  mov     rcx, rbx
0x1800bcdff  mov     [rsp+78h+var_58], r12
0x1800bce04  call    ?replace@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0AEBV12@00@Z; std::string::replace(unsigned __int64,unsigned __int64,std::string const &,unsigned __int64,unsigned __int64)
0x1800bce09  jmp     loc_1800BCF30
0x1800bce0e  cmp     [rbx+18h], rbp
0x1800bce12  jnb     short loc_1800BCE19
0x1800bce14  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x1800bce19  mov     rcx, [rbx+18h]
0x1800bce1d  mov     r14, [rsp+78h+SourceSize]
0x1800bce25  mov     rax, rcx
0x1800bce28  sub     rax, rbp
0x1800bce2b  cmp     rax, rsi
0x1800bce2e  cmovb   rsi, rax
0x1800bce32  mov     rax, r14
0x1800bce35  not     rax
0x1800bce38  sub     rcx, rsi
0x1800bce3b  cmp     rax, rcx
0x1800bce3e  ja      short loc_1800BCE45
0x1800bce40  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x1800bce45  mov     r15, [rbx+18h]
0x1800bce49  lea     rdi, [rbx+8]
0x1800bce4d  sub     r15, rbp
0x1800bce50  sub     r15, rsi
0x1800bce53  cmp     r14, rsi
0x1800bce56  jnb     short loc_1800BCE8D
0x1800bce58  mov     rdx, [rbx+20h]
0x1800bce5c  cmp     rdx, 10h
0x1800bce60  jb      short loc_1800BCE6A
0x1800bce62  mov     rax, [rdi]
0x1800bce65  mov     rcx, rax
0x1800bce68  jmp     short loc_1800BCE70
0x1800bce6a  mov     rax, rdi
0x1800bce6d  mov     rcx, rdi
0x1800bce70  lea     r8, [rcx+rbp]
0x1800bce74  sub     rdx, rbp
0x1800bce77  lea     rcx, [rax+rbp]
0x1800bce7b  add     r8, rsi; Source
0x1800bce7e  add     rcx, r14; Destination
0x1800bce81  sub     rdx, r14; DestinationSize
0x1800bce84  mov     r9, r15; SourceSize
0x1800bce87  call    cs:__imp_memmove_s
0x1800bce8d  test    r14, r14
0x1800bce90  jnz     short loc_1800BCE9B
0x1800bce92  test    rsi, rsi
0x1800bce95  jz      loc_1800BCF2D
0x1800bce9b  mov     r13, [rbx+18h]
0x1800bce9f  xor     r8d, r8d
0x1800bcea2  sub     r13, rsi
0x1800bcea5  mov     rcx, rbx
0x1800bcea8  add     r13, r14
0x1800bceab  mov     rdx, r13
0x1800bceae  call    ?_Grow@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAA_N_K_N@Z; std::string::_Grow(unsigned __int64,bool)
0x1800bceb3  test    al, al
0x1800bceb5  jz      short loc_1800BCF2D
0x1800bceb7  cmp     rsi, r14
0x1800bceba  jnb     short loc_1800BCEF5
0x1800bcebc  mov     rdx, [rbx+20h]
0x1800bcec0  lea     rdi, [rbx+8]
0x1800bcec4  cmp     rdx, 10h
0x1800bcec8  jb      short loc_1800BCED2
0x1800bceca  mov     rax, [rdi]
0x1800bcecd  mov     rcx, rax
0x1800bced0  jmp     short loc_1800BCED8
0x1800bced2  mov     rax, rdi
0x1800bced5  mov     rcx, rdi
0x1800bced8  lea     r8, [rcx+rbp]
0x1800bcedc  sub     rdx, rbp
0x1800bcedf  lea     rcx, [rax+rbp]
0x1800bcee3  add     r8, rsi; Source
0x1800bcee6  add     rcx, r14; Destination
0x1800bcee9  sub     rdx, r14; DestinationSize
0x1800bceec  mov     r9, r15; SourceSize
0x1800bceef  call    cs:__imp_memmove_s
0x1800bcef5  mov     rdx, [rbx+20h]
0x1800bcef9  cmp     rdx, 10h
0x1800bcefd  jb      short loc_1800BCF04
0x1800bceff  mov     rax, [rdi]
0x1800bcf02  jmp     short loc_1800BCF07
0x1800bcf04  mov     rax, rdi
0x1800bcf07  sub     rdx, rbp; DestinationSize
0x1800bcf0a  lea     rcx, [rax+rbp]; Destination
0x1800bcf0e  mov     r9, r14; SourceSize
0x1800bcf11  mov     r8, r12; Source
0x1800bcf14  call    cs:__imp_memcpy_s
0x1800bcf1a  cmp     qword ptr [rbx+20h], 10h
0x1800bcf1f  jb      short loc_1800BCF24
0x1800bcf21  mov     rdi, [rdi]
0x1800bcf24  mov     [rbx+18h], r13
0x1800bcf28  mov     byte ptr [rdi+r13], 0
0x1800bcf2d  mov     rax, rbx
0x1800bcf30  add     rsp, 38h
0x1800bcf34  pop     r15
0x1800bcf36  pop     r14
0x1800bcf38  pop     r13
0x1800bcf3a  pop     r12
0x1800bcf3c  pop     rdi
0x1800bcf3d  pop     rsi
0x1800bcf3e  pop     rbp
0x1800bcf3f  pop     rbx
0x1800bcf40  retn
```
