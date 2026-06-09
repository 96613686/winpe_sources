# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800047e0`
- end: `0x180004977`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000366c`
- `0x180004ea8`
- `0x18000521c`
- `0x180005b98`

## callees

- `0x1800047e0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004815`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004843`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004863`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000487b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000488a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800048f5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000491a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004815`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004843`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004863`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000487b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000488a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800048f5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000491a`

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
0x1800047e0  push    rbx
0x1800047e2  push    rbp
0x1800047e3  push    rsi
0x1800047e4  push    rdi
0x1800047e5  push    r14
0x1800047e7  sub     rsp, 20h
0x1800047eb  mov     rbx, rdx
0x1800047ee  mov     rdi, rcx
0x1800047f1  mov     rsi, [rdi]
0x1800047f4  movzx   ecx, word ptr [rsi]
0x1800047f7  mov     r8d, ecx
0x1800047fa  sub     r8d, 9
0x1800047fe  jz      short loc_180004812
0x180004800  sub     r8d, 1
0x180004804  jz      short loc_180004812
0x180004806  sub     r8d, 3
0x18000480a  jz      short loc_180004812
0x18000480c  cmp     r8d, 13h
0x180004810  jnz     short loc_180004820
0x180004812  mov     rcx, rsi; lpsz
0x180004815  call    cs:__imp_CharNextW
0x18000481b  mov     [rdi], rax
0x18000481e  jmp     short loc_1800047F1
0x180004820  xor     eax, eax
0x180004822  cmp     ax, cx
0x180004825  jz      loc_1800048D0
0x18000482b  lea     r14d, [rax+27h]
0x18000482f  lea     rbp, [rbx+2000h]
0x180004836  cmp     r14w, cx
0x18000483a  jnz     loc_180004900
0x180004840  mov     rcx, rsi; lpsz
0x180004843  call    cs:__imp_CharNextW
0x180004849  mov     [rdi], rax
0x18000484c  mov     rcx, rax; lpsz
0x18000484f  movzx   edx, word ptr [rax]
0x180004852  xor     eax, eax
0x180004854  cmp     ax, dx
0x180004857  jz      loc_1800048E0
0x18000485d  cmp     r14w, dx
0x180004861  jnz     short loc_18000486F
0x180004863  call    cs:__imp_CharNextW
0x180004869  cmp     r14w, [rax]
0x18000486d  jnz     short loc_1800048E0
0x18000486f  mov     rsi, [rdi]
0x180004872  cmp     r14w, [rsi]
0x180004876  jnz     short loc_180004887
0x180004878  mov     rcx, rsi; lpsz
0x18000487b  call    cs:__imp_CharNextW
0x180004881  mov     rsi, rax
0x180004884  mov     [rdi], rax
0x180004887  mov     rcx, rsi; lpsz
0x18000488a  call    cs:__imp_CharNextW
0x180004890  mov     rdx, rax
0x180004893  mov     [rdi], rax
0x180004896  sub     rdx, rsi
0x180004899  sar     rdx, 1
0x18000489c  lea     rcx, [rdx+1]
0x1800048a0  lea     rcx, [rbx+rcx*2]
0x1800048a4  cmp     rcx, rbp
0x1800048a7  jnb     short loc_1800048D0
0x1800048a9  xor     ecx, ecx
0x1800048ab  test    edx, edx
0x1800048ad  jle     short loc_1800048C3
0x1800048af  movzx   eax, word ptr [rsi]
0x1800048b2  inc     ecx
0x1800048b4  mov     [rbx], ax
0x1800048b7  lea     rsi, [rsi+2]
0x1800048bb  add     rbx, 2
0x1800048bf  cmp     ecx, edx
0x1800048c1  jl      short loc_1800048AF
0x1800048c3  mov     rcx, [rdi]
0x1800048c6  xor     eax, eax
0x1800048c8  movzx   edx, word ptr [rcx]
0x1800048cb  cmp     ax, dx
0x1800048ce  jnz     short loc_18000485D
0x1800048d0  mov     eax, 80020009h
0x1800048d5  add     rsp, 20h
0x1800048d9  pop     r14
0x1800048db  pop     rdi
0x1800048dc  pop     rsi
0x1800048dd  pop     rbp
0x1800048de  pop     rbx
0x1800048df  retn
0x1800048e0  mov     rcx, [rdi]
0x1800048e3  xor     eax, eax
0x1800048e5  cmp     ax, [rcx]
0x1800048e8  jz      short loc_1800048D0
0x1800048ea  cmp     rbx, rbp
0x1800048ed  jnb     short loc_1800048D0
0x1800048ef  mov     [rbx], ax
0x1800048f2  mov     rcx, [rdi]; lpsz
0x1800048f5  call    cs:__imp_CharNextW
0x1800048fb  mov     [rdi], rax
0x1800048fe  jmp     short loc_180004970
0x180004900  movzx   ecx, cx
0x180004903  sub     ecx, 9
0x180004906  jz      short loc_180004962
0x180004908  sub     ecx, 1
0x18000490b  jz      short loc_180004962
0x18000490d  sub     ecx, 3
0x180004910  jz      short loc_180004962
0x180004912  cmp     ecx, 13h
0x180004915  jz      short loc_180004962
0x180004917  mov     rcx, rsi; lpsz
0x18000491a  call    cs:__imp_CharNextW
0x180004920  mov     rdx, rax
0x180004923  mov     [rdi], rax
0x180004926  sub     rdx, rsi
0x180004929  sar     rdx, 1
0x18000492c  lea     rcx, [rdx+1]
0x180004930  lea     rcx, [rbx+rcx*2]
0x180004934  cmp     rcx, rbp
0x180004937  jnb     short loc_1800048D0
0x180004939  xor     ecx, ecx
0x18000493b  test    edx, edx
0x18000493d  jle     short loc_180004953
0x18000493f  movzx   eax, word ptr [rsi]
0x180004942  inc     ecx
0x180004944  mov     [rbx], ax
0x180004947  lea     rsi, [rsi+2]
0x18000494b  add     rbx, 2
0x18000494f  cmp     ecx, edx
0x180004951  jl      short loc_18000493F
0x180004953  mov     rsi, [rdi]
0x180004956  xor     eax, eax
0x180004958  cmp     ax, [rsi]
0x18000495b  jz      short loc_180004962
0x18000495d  movzx   ecx, word ptr [rsi]
0x180004960  jmp     short loc_180004900
0x180004962  cmp     rbx, rbp
0x180004965  jnb     loc_1800048D0
0x18000496b  xor     eax, eax
0x18000496d  mov     [rbx], ax
0x180004970  xor     eax, eax
0x180004972  jmp     loc_1800048D5
```
