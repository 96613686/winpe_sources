# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180008410`
- end: `0x180008567`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006dfc`
- `0x180008aac`
- `0x180008e68`
- `0x1800096cc`

## callees

- `0x180008410`
- `0x180009760`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008449`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008462`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000847a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008489`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800084e1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008510`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008449`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008462`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000847a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008489`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800084e1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008510`

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
0x180008410  push    rbx
0x180008412  push    rbp
0x180008413  push    rsi
0x180008414  push    rdi
0x180008415  push    r14
0x180008417  sub     rsp, 20h
0x18000841b  mov     rbx, rdx
0x18000841e  mov     rdi, rcx
0x180008421  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180008426  mov     rcx, [rdi]; lpsz
0x180008429  xor     eax, eax
0x18000842b  cmp     ax, [rcx]
0x18000842e  jz      loc_180008557
0x180008434  lea     r14d, [rax+27h]
0x180008438  lea     rbp, [rbx+2000h]
0x18000843f  cmp     r14w, [rcx]
0x180008443  jnz     loc_1800084EC
0x180008449  call    cs:__imp_CharNextW
0x18000844f  mov     [rdi], rax
0x180008452  mov     rcx, [rdi]; lpsz
0x180008455  xor     eax, eax
0x180008457  cmp     ax, [rcx]
0x18000845a  jz      short loc_1800084C8
0x18000845c  cmp     r14w, [rcx]
0x180008460  jnz     short loc_18000846E
0x180008462  call    cs:__imp_CharNextW
0x180008468  cmp     r14w, [rax]
0x18000846c  jnz     short loc_1800084C8
0x18000846e  mov     rsi, [rdi]
0x180008471  cmp     r14w, [rsi]
0x180008475  jnz     short loc_180008486
0x180008477  mov     rcx, rsi; lpsz
0x18000847a  call    cs:__imp_CharNextW
0x180008480  mov     rsi, rax
0x180008483  mov     [rdi], rax
0x180008486  mov     rcx, rsi; lpsz
0x180008489  call    cs:__imp_CharNextW
0x18000848f  mov     rdx, rax
0x180008492  mov     [rdi], rax
0x180008495  sub     rdx, rsi
0x180008498  sar     rdx, 1
0x18000849b  lea     rcx, [rdx+1]
0x18000849f  lea     rcx, [rbx+rcx*2]
0x1800084a3  cmp     rcx, rbp
0x1800084a6  jnb     loc_180008557
0x1800084ac  xor     ecx, ecx
0x1800084ae  test    edx, edx
0x1800084b0  jle     short loc_180008452
0x1800084b2  movzx   eax, word ptr [rsi]
0x1800084b5  inc     ecx
0x1800084b7  mov     [rbx], ax
0x1800084ba  lea     rsi, [rsi+2]
0x1800084be  add     rbx, 2
0x1800084c2  cmp     ecx, edx
0x1800084c4  jl      short loc_1800084B2
0x1800084c6  jmp     short loc_180008452
0x1800084c8  mov     rcx, [rdi]
0x1800084cb  xor     eax, eax
0x1800084cd  cmp     ax, [rcx]
0x1800084d0  jz      loc_180008557
0x1800084d6  cmp     rbx, rbp
0x1800084d9  jnb     short loc_180008557
0x1800084db  mov     [rbx], ax
0x1800084de  mov     rcx, [rdi]; lpsz
0x1800084e1  call    cs:__imp_CharNextW
0x1800084e7  mov     [rdi], rax
0x1800084ea  jmp     short loc_180008553
0x1800084ec  mov     rsi, [rdi]
0x1800084ef  xor     eax, eax
0x1800084f1  cmp     ax, [rsi]
0x1800084f4  jz      short loc_18000854B
0x1800084f6  movzx   ecx, word ptr [rsi]
0x1800084f9  sub     ecx, 9
0x1800084fc  jz      short loc_18000854B
0x1800084fe  sub     ecx, 1
0x180008501  jz      short loc_18000854B
0x180008503  sub     ecx, 3
0x180008506  jz      short loc_18000854B
0x180008508  cmp     ecx, 13h
0x18000850b  jz      short loc_18000854B
0x18000850d  mov     rcx, rsi; lpsz
0x180008510  call    cs:__imp_CharNextW
0x180008516  mov     rdx, rax
0x180008519  mov     [rdi], rax
0x18000851c  sub     rdx, rsi
0x18000851f  sar     rdx, 1
0x180008522  lea     rcx, [rdx+1]
0x180008526  lea     rcx, [rbx+rcx*2]
0x18000852a  cmp     rcx, rbp
0x18000852d  jnb     short loc_180008557
0x18000852f  xor     ecx, ecx
0x180008531  test    edx, edx
0x180008533  jle     short loc_1800084EC
0x180008535  movzx   eax, word ptr [rsi]
0x180008538  inc     ecx
0x18000853a  mov     [rbx], ax
0x18000853d  lea     rsi, [rsi+2]
0x180008541  add     rbx, 2
0x180008545  cmp     ecx, edx
0x180008547  jl      short loc_180008535
0x180008549  jmp     short loc_1800084EC
0x18000854b  cmp     rbx, rbp
0x18000854e  jnb     short loc_180008557
0x180008550  mov     [rbx], ax
0x180008553  xor     eax, eax
0x180008555  jmp     short loc_18000855C
0x180008557  mov     eax, 80020009h
0x18000855c  add     rsp, 20h
0x180008560  pop     r14
0x180008562  pop     rdi
0x180008563  pop     rsi
0x180008564  pop     rbp
0x180008565  pop     rbx
0x180008566  retn
```
