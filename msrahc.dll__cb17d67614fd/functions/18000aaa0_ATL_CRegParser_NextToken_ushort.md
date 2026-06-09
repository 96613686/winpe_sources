# ATL::CRegParser::NextToken(ushort *)

- ea: `0x18000aaa0`
- end: `0x18000abf7`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008efc`
- `0x18000b05c`
- `0x18000b44c`
- `0x18000bbbc`

## callees

- `0x18000aaa0`
- `0x18000bc50`

## import_xrefs

- `USER32!CharNextW` at `0x18000aad9`
- `USER32!CharNextW` at `0x18000aaf2`
- `USER32!CharNextW` at `0x18000ab0a`
- `USER32!CharNextW` at `0x18000ab19`
- `USER32!CharNextW` at `0x18000ab71`
- `USER32!CharNextW` at `0x18000aba0`
- `USER32!CharNextW` at `0x18000aad9`
- `USER32!CharNextW` at `0x18000aaf2`
- `USER32!CharNextW` at `0x18000ab0a`
- `USER32!CharNextW` at `0x18000ab19`
- `USER32!CharNextW` at `0x18000ab71`
- `USER32!CharNextW` at `0x18000aba0`

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
0x18000aaa0  push    rbx
0x18000aaa2  push    rbp
0x18000aaa3  push    rsi
0x18000aaa4  push    rdi
0x18000aaa5  push    r14
0x18000aaa7  sub     rsp, 20h
0x18000aaab  mov     rbx, rdx
0x18000aaae  mov     rdi, rcx
0x18000aab1  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000aab6  mov     rcx, [rdi]; lpsz
0x18000aab9  xor     eax, eax
0x18000aabb  cmp     ax, [rcx]
0x18000aabe  jz      loc_18000ABE7
0x18000aac4  lea     r14d, [rax+27h]
0x18000aac8  lea     rbp, [rbx+2000h]
0x18000aacf  cmp     r14w, [rcx]
0x18000aad3  jnz     loc_18000AB7C
0x18000aad9  call    cs:__imp_CharNextW
0x18000aadf  mov     [rdi], rax
0x18000aae2  mov     rcx, [rdi]; lpsz
0x18000aae5  xor     eax, eax
0x18000aae7  cmp     ax, [rcx]
0x18000aaea  jz      short loc_18000AB58
0x18000aaec  cmp     r14w, [rcx]
0x18000aaf0  jnz     short loc_18000AAFE
0x18000aaf2  call    cs:__imp_CharNextW
0x18000aaf8  cmp     r14w, [rax]
0x18000aafc  jnz     short loc_18000AB58
0x18000aafe  mov     rsi, [rdi]
0x18000ab01  cmp     r14w, [rsi]
0x18000ab05  jnz     short loc_18000AB16
0x18000ab07  mov     rcx, rsi; lpsz
0x18000ab0a  call    cs:__imp_CharNextW
0x18000ab10  mov     rsi, rax
0x18000ab13  mov     [rdi], rax
0x18000ab16  mov     rcx, rsi; lpsz
0x18000ab19  call    cs:__imp_CharNextW
0x18000ab1f  mov     rdx, rax
0x18000ab22  mov     [rdi], rax
0x18000ab25  sub     rdx, rsi
0x18000ab28  sar     rdx, 1
0x18000ab2b  lea     rcx, [rdx+1]
0x18000ab2f  lea     rcx, [rbx+rcx*2]
0x18000ab33  cmp     rcx, rbp
0x18000ab36  jnb     loc_18000ABE7
0x18000ab3c  xor     ecx, ecx
0x18000ab3e  test    edx, edx
0x18000ab40  jle     short loc_18000AAE2
0x18000ab42  movzx   eax, word ptr [rsi]
0x18000ab45  inc     ecx
0x18000ab47  mov     [rbx], ax
0x18000ab4a  lea     rsi, [rsi+2]
0x18000ab4e  add     rbx, 2
0x18000ab52  cmp     ecx, edx
0x18000ab54  jl      short loc_18000AB42
0x18000ab56  jmp     short loc_18000AAE2
0x18000ab58  mov     rcx, [rdi]
0x18000ab5b  xor     eax, eax
0x18000ab5d  cmp     ax, [rcx]
0x18000ab60  jz      loc_18000ABE7
0x18000ab66  cmp     rbx, rbp
0x18000ab69  jnb     short loc_18000ABE7
0x18000ab6b  mov     [rbx], ax
0x18000ab6e  mov     rcx, [rdi]; lpsz
0x18000ab71  call    cs:__imp_CharNextW
0x18000ab77  mov     [rdi], rax
0x18000ab7a  jmp     short loc_18000ABE3
0x18000ab7c  mov     rsi, [rdi]
0x18000ab7f  xor     eax, eax
0x18000ab81  cmp     ax, [rsi]
0x18000ab84  jz      short loc_18000ABDB
0x18000ab86  movzx   ecx, word ptr [rsi]
0x18000ab89  sub     ecx, 9
0x18000ab8c  jz      short loc_18000ABDB
0x18000ab8e  sub     ecx, 1
0x18000ab91  jz      short loc_18000ABDB
0x18000ab93  sub     ecx, 3
0x18000ab96  jz      short loc_18000ABDB
0x18000ab98  cmp     ecx, 13h
0x18000ab9b  jz      short loc_18000ABDB
0x18000ab9d  mov     rcx, rsi; lpsz
0x18000aba0  call    cs:__imp_CharNextW
0x18000aba6  mov     rdx, rax
0x18000aba9  mov     [rdi], rax
0x18000abac  sub     rdx, rsi
0x18000abaf  sar     rdx, 1
0x18000abb2  lea     rcx, [rdx+1]
0x18000abb6  lea     rcx, [rbx+rcx*2]
0x18000abba  cmp     rcx, rbp
0x18000abbd  jnb     short loc_18000ABE7
0x18000abbf  xor     ecx, ecx
0x18000abc1  test    edx, edx
0x18000abc3  jle     short loc_18000AB7C
0x18000abc5  movzx   eax, word ptr [rsi]
0x18000abc8  inc     ecx
0x18000abca  mov     [rbx], ax
0x18000abcd  lea     rsi, [rsi+2]
0x18000abd1  add     rbx, 2
0x18000abd5  cmp     ecx, edx
0x18000abd7  jl      short loc_18000ABC5
0x18000abd9  jmp     short loc_18000AB7C
0x18000abdb  cmp     rbx, rbp
0x18000abde  jnb     short loc_18000ABE7
0x18000abe0  mov     [rbx], ax
0x18000abe3  xor     eax, eax
0x18000abe5  jmp     short loc_18000ABEC
0x18000abe7  mov     eax, 80020009h
0x18000abec  add     rsp, 20h
0x18000abf0  pop     r14
0x18000abf2  pop     rdi
0x18000abf3  pop     rsi
0x18000abf4  pop     rbp
0x18000abf5  pop     rbx
0x18000abf6  retn
```
