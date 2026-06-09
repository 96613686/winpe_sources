# ATL::CRegParser::NextToken(ushort *)

- ea: `0x18000a570`
- end: `0x18000a6c7`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000919c`
- `0x18000ab0c`
- `0x18000ae30`
- `0x18000b524`

## callees

- `0x18000a570`
- `0x18000b5b8`

## import_xrefs

- `USER32!CharNextW` at `0x18000a5a9`
- `USER32!CharNextW` at `0x18000a5c2`
- `USER32!CharNextW` at `0x18000a5da`
- `USER32!CharNextW` at `0x18000a5e9`
- `USER32!CharNextW` at `0x18000a641`
- `USER32!CharNextW` at `0x18000a670`
- `USER32!CharNextW` at `0x18000a5a9`
- `USER32!CharNextW` at `0x18000a5c2`
- `USER32!CharNextW` at `0x18000a5da`
- `USER32!CharNextW` at `0x18000a5e9`
- `USER32!CharNextW` at `0x18000a641`
- `USER32!CharNextW` at `0x18000a670`

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
0x18000a570  push    rbx
0x18000a572  push    rbp
0x18000a573  push    rsi
0x18000a574  push    rdi
0x18000a575  push    r14
0x18000a577  sub     rsp, 20h
0x18000a57b  mov     rbx, rdx
0x18000a57e  mov     rdi, rcx
0x18000a581  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000a586  mov     rcx, [rdi]; lpsz
0x18000a589  xor     eax, eax
0x18000a58b  cmp     ax, [rcx]
0x18000a58e  jz      loc_18000A6B7
0x18000a594  lea     r14d, [rax+27h]
0x18000a598  lea     rbp, [rbx+2000h]
0x18000a59f  cmp     r14w, [rcx]
0x18000a5a3  jnz     loc_18000A64C
0x18000a5a9  call    cs:__imp_CharNextW
0x18000a5af  mov     [rdi], rax
0x18000a5b2  mov     rcx, [rdi]; lpsz
0x18000a5b5  xor     eax, eax
0x18000a5b7  cmp     ax, [rcx]
0x18000a5ba  jz      short loc_18000A628
0x18000a5bc  cmp     r14w, [rcx]
0x18000a5c0  jnz     short loc_18000A5CE
0x18000a5c2  call    cs:__imp_CharNextW
0x18000a5c8  cmp     r14w, [rax]
0x18000a5cc  jnz     short loc_18000A628
0x18000a5ce  mov     rsi, [rdi]
0x18000a5d1  cmp     r14w, [rsi]
0x18000a5d5  jnz     short loc_18000A5E6
0x18000a5d7  mov     rcx, rsi; lpsz
0x18000a5da  call    cs:__imp_CharNextW
0x18000a5e0  mov     rsi, rax
0x18000a5e3  mov     [rdi], rax
0x18000a5e6  mov     rcx, rsi; lpsz
0x18000a5e9  call    cs:__imp_CharNextW
0x18000a5ef  mov     rdx, rax
0x18000a5f2  mov     [rdi], rax
0x18000a5f5  sub     rdx, rsi
0x18000a5f8  sar     rdx, 1
0x18000a5fb  lea     rcx, [rdx+1]
0x18000a5ff  lea     rcx, [rbx+rcx*2]
0x18000a603  cmp     rcx, rbp
0x18000a606  jnb     loc_18000A6B7
0x18000a60c  xor     ecx, ecx
0x18000a60e  test    edx, edx
0x18000a610  jle     short loc_18000A5B2
0x18000a612  movzx   eax, word ptr [rsi]
0x18000a615  inc     ecx
0x18000a617  mov     [rbx], ax
0x18000a61a  lea     rsi, [rsi+2]
0x18000a61e  add     rbx, 2
0x18000a622  cmp     ecx, edx
0x18000a624  jl      short loc_18000A612
0x18000a626  jmp     short loc_18000A5B2
0x18000a628  mov     rcx, [rdi]
0x18000a62b  xor     eax, eax
0x18000a62d  cmp     ax, [rcx]
0x18000a630  jz      loc_18000A6B7
0x18000a636  cmp     rbx, rbp
0x18000a639  jnb     short loc_18000A6B7
0x18000a63b  mov     [rbx], ax
0x18000a63e  mov     rcx, [rdi]; lpsz
0x18000a641  call    cs:__imp_CharNextW
0x18000a647  mov     [rdi], rax
0x18000a64a  jmp     short loc_18000A6B3
0x18000a64c  mov     rsi, [rdi]
0x18000a64f  xor     eax, eax
0x18000a651  cmp     ax, [rsi]
0x18000a654  jz      short loc_18000A6AB
0x18000a656  movzx   ecx, word ptr [rsi]
0x18000a659  sub     ecx, 9
0x18000a65c  jz      short loc_18000A6AB
0x18000a65e  sub     ecx, 1
0x18000a661  jz      short loc_18000A6AB
0x18000a663  sub     ecx, 3
0x18000a666  jz      short loc_18000A6AB
0x18000a668  cmp     ecx, 13h
0x18000a66b  jz      short loc_18000A6AB
0x18000a66d  mov     rcx, rsi; lpsz
0x18000a670  call    cs:__imp_CharNextW
0x18000a676  mov     rdx, rax
0x18000a679  mov     [rdi], rax
0x18000a67c  sub     rdx, rsi
0x18000a67f  sar     rdx, 1
0x18000a682  lea     rcx, [rdx+1]
0x18000a686  lea     rcx, [rbx+rcx*2]
0x18000a68a  cmp     rcx, rbp
0x18000a68d  jnb     short loc_18000A6B7
0x18000a68f  xor     ecx, ecx
0x18000a691  test    edx, edx
0x18000a693  jle     short loc_18000A64C
0x18000a695  movzx   eax, word ptr [rsi]
0x18000a698  inc     ecx
0x18000a69a  mov     [rbx], ax
0x18000a69d  lea     rsi, [rsi+2]
0x18000a6a1  add     rbx, 2
0x18000a6a5  cmp     ecx, edx
0x18000a6a7  jl      short loc_18000A695
0x18000a6a9  jmp     short loc_18000A64C
0x18000a6ab  cmp     rbx, rbp
0x18000a6ae  jnb     short loc_18000A6B7
0x18000a6b0  mov     [rbx], ax
0x18000a6b3  xor     eax, eax
0x18000a6b5  jmp     short loc_18000A6BC
0x18000a6b7  mov     eax, 80020009h
0x18000a6bc  add     rsp, 20h
0x18000a6c0  pop     r14
0x18000a6c2  pop     rdi
0x18000a6c3  pop     rsi
0x18000a6c4  pop     rbp
0x18000a6c5  pop     rbx
0x18000a6c6  retn
```
