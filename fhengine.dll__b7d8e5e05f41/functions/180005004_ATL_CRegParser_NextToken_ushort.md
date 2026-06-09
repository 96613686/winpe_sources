# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180005004`
- end: `0x18000515b`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003aec`
- `0x18000576c`
- `0x180005a90`
- `0x1800064f0`

## callees

- `0x180005004`
- `0x180006584`

## import_xrefs

- `USER32!CharNextW` at `0x18000503d`
- `USER32!CharNextW` at `0x180005056`
- `USER32!CharNextW` at `0x18000506e`
- `USER32!CharNextW` at `0x18000507d`
- `USER32!CharNextW` at `0x1800050d5`
- `USER32!CharNextW` at `0x180005104`
- `USER32!CharNextW` at `0x18000503d`
- `USER32!CharNextW` at `0x180005056`
- `USER32!CharNextW` at `0x18000506e`
- `USER32!CharNextW` at `0x18000507d`
- `USER32!CharNextW` at `0x1800050d5`
- `USER32!CharNextW` at `0x180005104`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rcx
  unsigned __int16 *v5; // rbp
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rsi
  LPWSTR v8; // rax
  __int64 v9; // rdx
  int i; // ecx
  unsigned __int16 *v11; // rsi
  LPWSTR v12; // rax
  __int64 v13; // rdx
  int j; // ecx

  ATL::CRegParser::SkipWhiteSpace(this);
  v4 = *(const WCHAR **)this;
  if ( **(_WORD **)this )
  {
    v5 = a2 + 4096;
    if ( *v4 == 39 )
    {
      *(_QWORD *)this = CharNextW(v4);
      while ( 1 )
      {
        v6 = *(const WCHAR **)this;
        if ( !**(_WORD **)this || *v6 == 39 && *CharNextW(v6) != 39 )
          break;
        v7 = *(const WCHAR **)this;
        if ( **(_WORD **)this == 39 )
        {
          v7 = CharNextW(*(LPCWSTR *)this);
          *(_QWORD *)this = v7;
        }
        v8 = CharNextW(v7);
        *(_QWORD *)this = v8;
        v9 = v8 - v7;
        if ( &a2[v9 + 1] >= v5 )
          return 2147614729LL;
        for ( i = 0; i < (int)v9; ++a2 )
        {
          ++i;
          *a2 = *v7++;
        }
      }
      if ( **(_WORD **)this && a2 < v5 )
      {
        *a2 = 0;
        *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
        return 0;
      }
    }
    else
    {
      while ( 1 )
      {
        v11 = *(unsigned __int16 **)this;
        if ( !**(_WORD **)this || *v11 == 9 || *v11 == 10 || *v11 == 13 || *v11 == 32 )
          break;
        v12 = CharNextW(*(LPCWSTR *)this);
        *(_QWORD *)this = v12;
        v13 = v12 - v11;
        if ( &a2[v13 + 1] >= v5 )
          return 2147614729LL;
        for ( j = 0; j < (int)v13; ++a2 )
        {
          ++j;
          *a2 = *v11++;
        }
      }
      if ( a2 < v5 )
      {
        *a2 = 0;
        return 0;
      }
    }
  }
  return 2147614729LL;
}

```

## disassembly

```asm
0x180005004  push    rbx
0x180005006  push    rbp
0x180005007  push    rsi
0x180005008  push    rdi
0x180005009  push    r14
0x18000500b  sub     rsp, 20h
0x18000500f  mov     rbx, rdx
0x180005012  mov     rdi, rcx
0x180005015  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000501a  mov     rcx, [rdi]; lpsz
0x18000501d  xor     eax, eax
0x18000501f  cmp     ax, [rcx]
0x180005022  jz      loc_18000514B
0x180005028  lea     r14d, [rax+27h]
0x18000502c  lea     rbp, [rbx+2000h]
0x180005033  cmp     r14w, [rcx]
0x180005037  jnz     loc_1800050E0
0x18000503d  call    cs:__imp_CharNextW
0x180005043  mov     [rdi], rax
0x180005046  mov     rcx, [rdi]; lpsz
0x180005049  xor     eax, eax
0x18000504b  cmp     ax, [rcx]
0x18000504e  jz      short loc_1800050BC
0x180005050  cmp     r14w, [rcx]
0x180005054  jnz     short loc_180005062
0x180005056  call    cs:__imp_CharNextW
0x18000505c  cmp     r14w, [rax]
0x180005060  jnz     short loc_1800050BC
0x180005062  mov     rsi, [rdi]
0x180005065  cmp     r14w, [rsi]
0x180005069  jnz     short loc_18000507A
0x18000506b  mov     rcx, rsi; lpsz
0x18000506e  call    cs:__imp_CharNextW
0x180005074  mov     rsi, rax
0x180005077  mov     [rdi], rax
0x18000507a  mov     rcx, rsi; lpsz
0x18000507d  call    cs:__imp_CharNextW
0x180005083  mov     rdx, rax
0x180005086  mov     [rdi], rax
0x180005089  sub     rdx, rsi
0x18000508c  sar     rdx, 1
0x18000508f  lea     rcx, [rdx+1]
0x180005093  lea     rcx, [rbx+rcx*2]
0x180005097  cmp     rcx, rbp
0x18000509a  jnb     loc_18000514B
0x1800050a0  xor     ecx, ecx
0x1800050a2  test    edx, edx
0x1800050a4  jle     short loc_180005046
0x1800050a6  movzx   eax, word ptr [rsi]
0x1800050a9  inc     ecx
0x1800050ab  mov     [rbx], ax
0x1800050ae  lea     rsi, [rsi+2]
0x1800050b2  add     rbx, 2
0x1800050b6  cmp     ecx, edx
0x1800050b8  jl      short loc_1800050A6
0x1800050ba  jmp     short loc_180005046
0x1800050bc  mov     rcx, [rdi]
0x1800050bf  xor     eax, eax
0x1800050c1  cmp     ax, [rcx]
0x1800050c4  jz      loc_18000514B
0x1800050ca  cmp     rbx, rbp
0x1800050cd  jnb     short loc_18000514B
0x1800050cf  mov     [rbx], ax
0x1800050d2  mov     rcx, [rdi]; lpsz
0x1800050d5  call    cs:__imp_CharNextW
0x1800050db  mov     [rdi], rax
0x1800050de  jmp     short loc_180005147
0x1800050e0  mov     rsi, [rdi]
0x1800050e3  xor     eax, eax
0x1800050e5  cmp     ax, [rsi]
0x1800050e8  jz      short loc_18000513F
0x1800050ea  movzx   ecx, word ptr [rsi]
0x1800050ed  sub     ecx, 9
0x1800050f0  jz      short loc_18000513F
0x1800050f2  sub     ecx, 1
0x1800050f5  jz      short loc_18000513F
0x1800050f7  sub     ecx, 3
0x1800050fa  jz      short loc_18000513F
0x1800050fc  cmp     ecx, 13h
0x1800050ff  jz      short loc_18000513F
0x180005101  mov     rcx, rsi; lpsz
0x180005104  call    cs:__imp_CharNextW
0x18000510a  mov     rdx, rax
0x18000510d  mov     [rdi], rax
0x180005110  sub     rdx, rsi
0x180005113  sar     rdx, 1
0x180005116  lea     rcx, [rdx+1]
0x18000511a  lea     rcx, [rbx+rcx*2]
0x18000511e  cmp     rcx, rbp
0x180005121  jnb     short loc_18000514B
0x180005123  xor     ecx, ecx
0x180005125  test    edx, edx
0x180005127  jle     short loc_1800050E0
0x180005129  movzx   eax, word ptr [rsi]
0x18000512c  inc     ecx
0x18000512e  mov     [rbx], ax
0x180005131  lea     rsi, [rsi+2]
0x180005135  add     rbx, 2
0x180005139  cmp     ecx, edx
0x18000513b  jl      short loc_180005129
0x18000513d  jmp     short loc_1800050E0
0x18000513f  cmp     rbx, rbp
0x180005142  jnb     short loc_18000514B
0x180005144  mov     [rbx], ax
0x180005147  xor     eax, eax
0x180005149  jmp     short loc_180005150
0x18000514b  mov     eax, 80020009h
0x180005150  add     rsp, 20h
0x180005154  pop     r14
0x180005156  pop     rdi
0x180005157  pop     rsi
0x180005158  pop     rbp
0x180005159  pop     rbx
0x18000515a  retn
```
