# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800107e0`
- end: `0x180010977`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e0bc`
- `0x180010f18`
- `0x180011384`
- `0x180011eb0`

## callees

- `0x1800107e0`

## import_xrefs

- `USER32!CharNextW` at `0x180010815`
- `USER32!CharNextW` at `0x180010843`
- `USER32!CharNextW` at `0x180010863`
- `USER32!CharNextW` at `0x18001087b`
- `USER32!CharNextW` at `0x18001088a`
- `USER32!CharNextW` at `0x1800108f5`
- `USER32!CharNextW` at `0x18001091a`
- `USER32!CharNextW` at `0x180010815`
- `USER32!CharNextW` at `0x180010843`
- `USER32!CharNextW` at `0x180010863`
- `USER32!CharNextW` at `0x18001087b`
- `USER32!CharNextW` at `0x18001088a`
- `USER32!CharNextW` at `0x1800108f5`
- `USER32!CharNextW` at `0x18001091a`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCWSTR *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rsi
  WCHAR v5; // cx
  unsigned __int16 *v6; // rbp
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
0x1800107e0  push    rbx
0x1800107e2  push    rbp
0x1800107e3  push    rsi
0x1800107e4  push    rdi
0x1800107e5  push    r14
0x1800107e7  sub     rsp, 20h
0x1800107eb  mov     rbx, rdx
0x1800107ee  mov     rdi, rcx
0x1800107f1  mov     rsi, [rdi]
0x1800107f4  movzx   ecx, word ptr [rsi]
0x1800107f7  mov     r8d, ecx
0x1800107fa  sub     r8d, 9
0x1800107fe  jz      short loc_180010812
0x180010800  sub     r8d, 1
0x180010804  jz      short loc_180010812
0x180010806  sub     r8d, 3
0x18001080a  jz      short loc_180010812
0x18001080c  cmp     r8d, 13h
0x180010810  jnz     short loc_180010820
0x180010812  mov     rcx, rsi; lpsz
0x180010815  call    cs:__imp_CharNextW
0x18001081b  mov     [rdi], rax
0x18001081e  jmp     short loc_1800107F1
0x180010820  xor     eax, eax
0x180010822  cmp     ax, cx
0x180010825  jz      loc_1800108D0
0x18001082b  lea     r14d, [rax+27h]
0x18001082f  lea     rbp, [rbx+2000h]
0x180010836  cmp     r14w, cx
0x18001083a  jnz     loc_180010900
0x180010840  mov     rcx, rsi; lpsz
0x180010843  call    cs:__imp_CharNextW
0x180010849  mov     [rdi], rax
0x18001084c  mov     rcx, rax; lpsz
0x18001084f  movzx   edx, word ptr [rax]
0x180010852  xor     eax, eax
0x180010854  cmp     ax, dx
0x180010857  jz      loc_1800108E0
0x18001085d  cmp     r14w, dx
0x180010861  jnz     short loc_18001086F
0x180010863  call    cs:__imp_CharNextW
0x180010869  cmp     r14w, [rax]
0x18001086d  jnz     short loc_1800108E0
0x18001086f  mov     rsi, [rdi]
0x180010872  cmp     r14w, [rsi]
0x180010876  jnz     short loc_180010887
0x180010878  mov     rcx, rsi; lpsz
0x18001087b  call    cs:__imp_CharNextW
0x180010881  mov     rsi, rax
0x180010884  mov     [rdi], rax
0x180010887  mov     rcx, rsi; lpsz
0x18001088a  call    cs:__imp_CharNextW
0x180010890  mov     rdx, rax
0x180010893  mov     [rdi], rax
0x180010896  sub     rdx, rsi
0x180010899  sar     rdx, 1
0x18001089c  lea     rcx, [rdx+1]
0x1800108a0  lea     rcx, [rbx+rcx*2]
0x1800108a4  cmp     rcx, rbp
0x1800108a7  jnb     short loc_1800108D0
0x1800108a9  xor     ecx, ecx
0x1800108ab  test    edx, edx
0x1800108ad  jle     short loc_1800108C3
0x1800108af  movzx   eax, word ptr [rsi]
0x1800108b2  inc     ecx
0x1800108b4  mov     [rbx], ax
0x1800108b7  lea     rsi, [rsi+2]
0x1800108bb  add     rbx, 2
0x1800108bf  cmp     ecx, edx
0x1800108c1  jl      short loc_1800108AF
0x1800108c3  mov     rcx, [rdi]
0x1800108c6  xor     eax, eax
0x1800108c8  movzx   edx, word ptr [rcx]
0x1800108cb  cmp     ax, dx
0x1800108ce  jnz     short loc_18001085D
0x1800108d0  mov     eax, 80020009h
0x1800108d5  add     rsp, 20h
0x1800108d9  pop     r14
0x1800108db  pop     rdi
0x1800108dc  pop     rsi
0x1800108dd  pop     rbp
0x1800108de  pop     rbx
0x1800108df  retn
0x1800108e0  mov     rcx, [rdi]
0x1800108e3  xor     eax, eax
0x1800108e5  cmp     ax, [rcx]
0x1800108e8  jz      short loc_1800108D0
0x1800108ea  cmp     rbx, rbp
0x1800108ed  jnb     short loc_1800108D0
0x1800108ef  mov     [rbx], ax
0x1800108f2  mov     rcx, [rdi]; lpsz
0x1800108f5  call    cs:__imp_CharNextW
0x1800108fb  mov     [rdi], rax
0x1800108fe  jmp     short loc_180010970
0x180010900  movzx   ecx, cx
0x180010903  sub     ecx, 9
0x180010906  jz      short loc_180010962
0x180010908  sub     ecx, 1
0x18001090b  jz      short loc_180010962
0x18001090d  sub     ecx, 3
0x180010910  jz      short loc_180010962
0x180010912  cmp     ecx, 13h
0x180010915  jz      short loc_180010962
0x180010917  mov     rcx, rsi; lpsz
0x18001091a  call    cs:__imp_CharNextW
0x180010920  mov     rdx, rax
0x180010923  mov     [rdi], rax
0x180010926  sub     rdx, rsi
0x180010929  sar     rdx, 1
0x18001092c  lea     rcx, [rdx+1]
0x180010930  lea     rcx, [rbx+rcx*2]
0x180010934  cmp     rcx, rbp
0x180010937  jnb     short loc_1800108D0
0x180010939  xor     ecx, ecx
0x18001093b  test    edx, edx
0x18001093d  jle     short loc_180010953
0x18001093f  movzx   eax, word ptr [rsi]
0x180010942  inc     ecx
0x180010944  mov     [rbx], ax
0x180010947  lea     rsi, [rsi+2]
0x18001094b  add     rbx, 2
0x18001094f  cmp     ecx, edx
0x180010951  jl      short loc_18001093F
0x180010953  mov     rsi, [rdi]
0x180010956  xor     eax, eax
0x180010958  cmp     ax, [rsi]
0x18001095b  jz      short loc_180010962
0x18001095d  movzx   ecx, word ptr [rsi]
0x180010960  jmp     short loc_180010900
0x180010962  cmp     rbx, rbp
0x180010965  jnb     loc_1800108D0
0x18001096b  xor     eax, eax
0x18001096d  mov     [rbx], ax
0x180010970  xor     eax, eax
0x180010972  jmp     loc_1800108D5
```
