# ATL::CRegParser::NextToken(wchar_t *)

- ea: `0x18000e33c`
- end: `0x18000e4d3`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, wchar_t *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bd2c`
- `0x18000ec38`
- `0x18000efac`
- `0x18000ff04`

## callees

- `0x18000e33c`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e371`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e39f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e3bf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e3d7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e3e6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e451`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e476`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e371`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e39f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e3bf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e3d7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e3e6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e451`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e476`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCWSTR *this, wchar_t *a2)
{
  const WCHAR *v4; // rsi
  WCHAR v5; // cx
  wchar_t *v6; // rbp
  LPWSTR v7; // rax
  const WCHAR *v8; // rcx
  __int16 v9; // dx
  const WCHAR *v10; // rsi
  LPWSTR v11; // rax
  __int64 v12; // rdx
  int j; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  LPWSTR v18; // rax
  __int64 v19; // rdx
  int i; // ecx

  while ( 1 )
  {
    v4 = *this;
    v5 = **this;
    if ( v5 != 9 && **this != 10 && **this != 13 && **this != 32 )
      break;
    *this = CharNextW(*this);
  }
  if ( !v5 )
    return 2147614729LL;
  v6 = a2 + 4096;
  if ( v5 != 39 )
  {
    while ( 1 )
    {
      v15 = v5 - 9;
      if ( !v15 )
        break;
      v16 = v15 - 1;
      if ( !v16 )
        break;
      v17 = v16 - 3;
      if ( !v17 || v17 == 19 )
        break;
      v18 = CharNextW(v4);
      *this = v18;
      v19 = v18 - v4;
      if ( &a2[v19 + 1] >= v6 )
        return 2147614729LL;
      for ( i = 0; i < (int)v19; ++a2 )
      {
        ++i;
        *a2 = *v4++;
      }
      v4 = *this;
      if ( !**this )
        break;
      v5 = *v4;
    }
    if ( a2 < v6 )
    {
      *a2 = 0;
      return 0;
    }
    return 2147614729LL;
  }
  v7 = CharNextW(*this);
  *this = v7;
  v8 = v7;
  v9 = *v7;
  if ( *v7 )
  {
    while ( v9 != 39 || *CharNextW(v8) == 39 )
    {
      v10 = *this;
      if ( **this == 39 )
      {
        v10 = CharNextW(*this);
        *this = v10;
      }
      v11 = CharNextW(v10);
      *this = v11;
      v12 = v11 - v10;
      if ( &a2[v12 + 1] < v6 )
      {
        for ( j = 0; j < (int)v12; ++a2 )
        {
          ++j;
          *a2 = *v10++;
        }
        v8 = *this;
        v9 = **this;
        if ( v9 )
          continue;
      }
      return 2147614729LL;
    }
  }
  if ( !**this || a2 >= v6 )
    return 2147614729LL;
  *a2 = 0;
  *this = CharNextW(*this);
  return 0;
}

```

## disassembly

```asm
0x18000e33c  push    rbx
0x18000e33e  push    rbp
0x18000e33f  push    rsi
0x18000e340  push    rdi
0x18000e341  push    r14
0x18000e343  sub     rsp, 20h
0x18000e347  mov     rbx, rdx
0x18000e34a  mov     rdi, rcx
0x18000e34d  mov     rsi, [rdi]
0x18000e350  movzx   ecx, word ptr [rsi]
0x18000e353  mov     r8d, ecx
0x18000e356  sub     r8d, 9
0x18000e35a  jz      short loc_18000E36E
0x18000e35c  sub     r8d, 1
0x18000e360  jz      short loc_18000E36E
0x18000e362  sub     r8d, 3
0x18000e366  jz      short loc_18000E36E
0x18000e368  cmp     r8d, 13h
0x18000e36c  jnz     short loc_18000E37C
0x18000e36e  mov     rcx, rsi; lpsz
0x18000e371  call    cs:__imp_CharNextW
0x18000e377  mov     [rdi], rax
0x18000e37a  jmp     short loc_18000E34D
0x18000e37c  xor     eax, eax
0x18000e37e  cmp     ax, cx
0x18000e381  jz      loc_18000E42C
0x18000e387  lea     r14d, [rax+27h]
0x18000e38b  lea     rbp, [rbx+2000h]
0x18000e392  cmp     r14w, cx
0x18000e396  jnz     loc_18000E45C
0x18000e39c  mov     rcx, rsi; lpsz
0x18000e39f  call    cs:__imp_CharNextW
0x18000e3a5  mov     [rdi], rax
0x18000e3a8  mov     rcx, rax; lpsz
0x18000e3ab  movzx   edx, word ptr [rax]
0x18000e3ae  xor     eax, eax
0x18000e3b0  cmp     ax, dx
0x18000e3b3  jz      loc_18000E43C
0x18000e3b9  cmp     r14w, dx
0x18000e3bd  jnz     short loc_18000E3CB
0x18000e3bf  call    cs:__imp_CharNextW
0x18000e3c5  cmp     r14w, [rax]
0x18000e3c9  jnz     short loc_18000E43C
0x18000e3cb  mov     rsi, [rdi]
0x18000e3ce  cmp     r14w, [rsi]
0x18000e3d2  jnz     short loc_18000E3E3
0x18000e3d4  mov     rcx, rsi; lpsz
0x18000e3d7  call    cs:__imp_CharNextW
0x18000e3dd  mov     rsi, rax
0x18000e3e0  mov     [rdi], rax
0x18000e3e3  mov     rcx, rsi; lpsz
0x18000e3e6  call    cs:__imp_CharNextW
0x18000e3ec  mov     rdx, rax
0x18000e3ef  mov     [rdi], rax
0x18000e3f2  sub     rdx, rsi
0x18000e3f5  sar     rdx, 1
0x18000e3f8  lea     rcx, [rdx+1]
0x18000e3fc  lea     rcx, [rbx+rcx*2]
0x18000e400  cmp     rcx, rbp
0x18000e403  jnb     short loc_18000E42C
0x18000e405  xor     ecx, ecx
0x18000e407  test    edx, edx
0x18000e409  jle     short loc_18000E41F
0x18000e40b  movzx   eax, word ptr [rsi]
0x18000e40e  inc     ecx
0x18000e410  mov     [rbx], ax
0x18000e413  lea     rsi, [rsi+2]
0x18000e417  add     rbx, 2
0x18000e41b  cmp     ecx, edx
0x18000e41d  jl      short loc_18000E40B
0x18000e41f  mov     rcx, [rdi]
0x18000e422  xor     eax, eax
0x18000e424  movzx   edx, word ptr [rcx]
0x18000e427  cmp     ax, dx
0x18000e42a  jnz     short loc_18000E3B9
0x18000e42c  mov     eax, 80020009h
0x18000e431  add     rsp, 20h
0x18000e435  pop     r14
0x18000e437  pop     rdi
0x18000e438  pop     rsi
0x18000e439  pop     rbp
0x18000e43a  pop     rbx
0x18000e43b  retn
0x18000e43c  mov     rcx, [rdi]
0x18000e43f  xor     eax, eax
0x18000e441  cmp     ax, [rcx]
0x18000e444  jz      short loc_18000E42C
0x18000e446  cmp     rbx, rbp
0x18000e449  jnb     short loc_18000E42C
0x18000e44b  mov     [rbx], ax
0x18000e44e  mov     rcx, [rdi]; lpsz
0x18000e451  call    cs:__imp_CharNextW
0x18000e457  mov     [rdi], rax
0x18000e45a  jmp     short loc_18000E4CC
0x18000e45c  movzx   ecx, cx
0x18000e45f  sub     ecx, 9
0x18000e462  jz      short loc_18000E4BE
0x18000e464  sub     ecx, 1
0x18000e467  jz      short loc_18000E4BE
0x18000e469  sub     ecx, 3
0x18000e46c  jz      short loc_18000E4BE
0x18000e46e  cmp     ecx, 13h
0x18000e471  jz      short loc_18000E4BE
0x18000e473  mov     rcx, rsi; lpsz
0x18000e476  call    cs:__imp_CharNextW
0x18000e47c  mov     rdx, rax
0x18000e47f  mov     [rdi], rax
0x18000e482  sub     rdx, rsi
0x18000e485  sar     rdx, 1
0x18000e488  lea     rcx, [rdx+1]
0x18000e48c  lea     rcx, [rbx+rcx*2]
0x18000e490  cmp     rcx, rbp
0x18000e493  jnb     short loc_18000E42C
0x18000e495  xor     ecx, ecx
0x18000e497  test    edx, edx
0x18000e499  jle     short loc_18000E4AF
0x18000e49b  movzx   eax, word ptr [rsi]
0x18000e49e  inc     ecx
0x18000e4a0  mov     [rbx], ax
0x18000e4a3  lea     rsi, [rsi+2]
0x18000e4a7  add     rbx, 2
0x18000e4ab  cmp     ecx, edx
0x18000e4ad  jl      short loc_18000E49B
0x18000e4af  mov     rsi, [rdi]
0x18000e4b2  xor     eax, eax
0x18000e4b4  cmp     ax, [rsi]
0x18000e4b7  jz      short loc_18000E4BE
0x18000e4b9  movzx   ecx, word ptr [rsi]
0x18000e4bc  jmp     short loc_18000E45C
0x18000e4be  cmp     rbx, rbp
0x18000e4c1  jnb     loc_18000E42C
0x18000e4c7  xor     eax, eax
0x18000e4c9  mov     [rbx], ax
0x18000e4cc  xor     eax, eax
0x18000e4ce  jmp     loc_18000E431
```
