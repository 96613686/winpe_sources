# ATL::CRegParser::NextToken(wchar_t *)

- ea: `0x18000f5e4`
- end: `0x18000f73b`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e89c`
- `0x18000fb7c`
- `0x18000fea0`
- `0x1800104d4`

## callees

- `0x18000f5e4`
- `0x180010568`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f61d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f636`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f64e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f65d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f6b5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f6e4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f61d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f636`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f64e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f65d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f6b5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f6e4`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, wchar_t *a2)
{
  const WCHAR *v4; // rcx
  wchar_t *v5; // rbp
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rsi
  LPWSTR v8; // rax
  __int64 v9; // rdx
  int i; // ecx
  wchar_t *v11; // rsi
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
        v11 = *(wchar_t **)this;
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
0x18000f5e4  push    rbx
0x18000f5e6  push    rbp
0x18000f5e7  push    rsi
0x18000f5e8  push    rdi
0x18000f5e9  push    r14
0x18000f5eb  sub     rsp, 20h
0x18000f5ef  mov     rbx, rdx
0x18000f5f2  mov     rdi, rcx
0x18000f5f5  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000f5fa  mov     rcx, [rdi]; lpsz
0x18000f5fd  xor     eax, eax
0x18000f5ff  cmp     ax, [rcx]
0x18000f602  jz      loc_18000F72B
0x18000f608  lea     r14d, [rax+27h]
0x18000f60c  lea     rbp, [rbx+2000h]
0x18000f613  cmp     r14w, [rcx]
0x18000f617  jnz     loc_18000F6C0
0x18000f61d  call    cs:__imp_CharNextW
0x18000f623  mov     [rdi], rax
0x18000f626  mov     rcx, [rdi]; lpsz
0x18000f629  xor     eax, eax
0x18000f62b  cmp     ax, [rcx]
0x18000f62e  jz      short loc_18000F69C
0x18000f630  cmp     r14w, [rcx]
0x18000f634  jnz     short loc_18000F642
0x18000f636  call    cs:__imp_CharNextW
0x18000f63c  cmp     r14w, [rax]
0x18000f640  jnz     short loc_18000F69C
0x18000f642  mov     rsi, [rdi]
0x18000f645  cmp     r14w, [rsi]
0x18000f649  jnz     short loc_18000F65A
0x18000f64b  mov     rcx, rsi; lpsz
0x18000f64e  call    cs:__imp_CharNextW
0x18000f654  mov     rsi, rax
0x18000f657  mov     [rdi], rax
0x18000f65a  mov     rcx, rsi; lpsz
0x18000f65d  call    cs:__imp_CharNextW
0x18000f663  mov     rdx, rax
0x18000f666  mov     [rdi], rax
0x18000f669  sub     rdx, rsi
0x18000f66c  sar     rdx, 1
0x18000f66f  lea     rcx, [rdx+1]
0x18000f673  lea     rcx, [rbx+rcx*2]
0x18000f677  cmp     rcx, rbp
0x18000f67a  jnb     loc_18000F72B
0x18000f680  xor     ecx, ecx
0x18000f682  test    edx, edx
0x18000f684  jle     short loc_18000F626
0x18000f686  movzx   eax, word ptr [rsi]
0x18000f689  inc     ecx
0x18000f68b  mov     [rbx], ax
0x18000f68e  lea     rsi, [rsi+2]
0x18000f692  add     rbx, 2
0x18000f696  cmp     ecx, edx
0x18000f698  jl      short loc_18000F686
0x18000f69a  jmp     short loc_18000F626
0x18000f69c  mov     rcx, [rdi]
0x18000f69f  xor     eax, eax
0x18000f6a1  cmp     ax, [rcx]
0x18000f6a4  jz      loc_18000F72B
0x18000f6aa  cmp     rbx, rbp
0x18000f6ad  jnb     short loc_18000F72B
0x18000f6af  mov     [rbx], ax
0x18000f6b2  mov     rcx, [rdi]; lpsz
0x18000f6b5  call    cs:__imp_CharNextW
0x18000f6bb  mov     [rdi], rax
0x18000f6be  jmp     short loc_18000F727
0x18000f6c0  mov     rsi, [rdi]
0x18000f6c3  xor     eax, eax
0x18000f6c5  cmp     ax, [rsi]
0x18000f6c8  jz      short loc_18000F71F
0x18000f6ca  movzx   ecx, word ptr [rsi]
0x18000f6cd  sub     ecx, 9
0x18000f6d0  jz      short loc_18000F71F
0x18000f6d2  sub     ecx, 1
0x18000f6d5  jz      short loc_18000F71F
0x18000f6d7  sub     ecx, 3
0x18000f6da  jz      short loc_18000F71F
0x18000f6dc  cmp     ecx, 13h
0x18000f6df  jz      short loc_18000F71F
0x18000f6e1  mov     rcx, rsi; lpsz
0x18000f6e4  call    cs:__imp_CharNextW
0x18000f6ea  mov     rdx, rax
0x18000f6ed  mov     [rdi], rax
0x18000f6f0  sub     rdx, rsi
0x18000f6f3  sar     rdx, 1
0x18000f6f6  lea     rcx, [rdx+1]
0x18000f6fa  lea     rcx, [rbx+rcx*2]
0x18000f6fe  cmp     rcx, rbp
0x18000f701  jnb     short loc_18000F72B
0x18000f703  xor     ecx, ecx
0x18000f705  test    edx, edx
0x18000f707  jle     short loc_18000F6C0
0x18000f709  movzx   eax, word ptr [rsi]
0x18000f70c  inc     ecx
0x18000f70e  mov     [rbx], ax
0x18000f711  lea     rsi, [rsi+2]
0x18000f715  add     rbx, 2
0x18000f719  cmp     ecx, edx
0x18000f71b  jl      short loc_18000F709
0x18000f71d  jmp     short loc_18000F6C0
0x18000f71f  cmp     rbx, rbp
0x18000f722  jnb     short loc_18000F72B
0x18000f724  mov     [rbx], ax
0x18000f727  xor     eax, eax
0x18000f729  jmp     short loc_18000F730
0x18000f72b  mov     eax, 80020009h
0x18000f730  add     rsp, 20h
0x18000f734  pop     r14
0x18000f736  pop     rdi
0x18000f737  pop     rsi
0x18000f738  pop     rbp
0x18000f739  pop     rbx
0x18000f73a  retn
```
