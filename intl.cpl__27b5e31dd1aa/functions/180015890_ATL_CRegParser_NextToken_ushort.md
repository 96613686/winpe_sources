# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180015890`
- end: `0x180015a01`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `369`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001399c`
- `0x18001614c`
- `0x18001646c`
- `0x180016c70`

## callees

- `0x180015890`
- `0x180016d04`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800158cf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800158ef`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015907`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015916`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015981`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800159a6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800158cf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800158ef`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015907`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015916`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015981`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800159a6`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rsi
  unsigned __int16 v5; // cx
  unsigned __int16 *v6; // rbp
  LPWSTR v7; // rax
  const WCHAR *v8; // rcx
  WCHAR v9; // dx
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

  ATL::CRegParser::SkipWhiteSpace(this);
  v4 = *(const WCHAR **)this;
  v5 = **(_WORD **)this;
  if ( !v5 )
    return 2147614729LL;
  v6 = a2 + 4096;
  if ( v5 != 39 )
  {
    do
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
      *(_QWORD *)this = v18;
      v19 = v18 - v4;
      if ( &a2[v19 + 1] >= v6 )
        return 2147614729LL;
      for ( i = 0; i < (int)v19; ++a2 )
      {
        ++i;
        *a2 = *v4++;
      }
      v4 = *(const WCHAR **)this;
      v5 = **(_WORD **)this;
    }
    while ( v5 );
    if ( a2 < v6 )
    {
      *a2 = 0;
      return 0;
    }
    return 2147614729LL;
  }
  v7 = CharNextW(*(LPCWSTR *)this);
  *(_QWORD *)this = v7;
  v8 = v7;
  v9 = *v7;
  if ( *v7 )
  {
    while ( v9 != 39 || *CharNextW(v8) == 39 )
    {
      v10 = *(const WCHAR **)this;
      if ( **(_WORD **)this == 39 )
      {
        v10 = CharNextW(*(LPCWSTR *)this);
        *(_QWORD *)this = v10;
      }
      v11 = CharNextW(v10);
      *(_QWORD *)this = v11;
      v12 = v11 - v10;
      if ( &a2[v12 + 1] < v6 )
      {
        for ( j = 0; j < (int)v12; ++a2 )
        {
          ++j;
          *a2 = *v10++;
        }
        v8 = *(const WCHAR **)this;
        v9 = **(_WORD **)this;
        if ( v9 )
          continue;
      }
      return 2147614729LL;
    }
  }
  if ( !**(_WORD **)this || a2 >= v6 )
    return 2147614729LL;
  *a2 = 0;
  *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
  return 0;
}

```

## disassembly

```asm
0x180015890  push    rbx
0x180015892  push    rbp
0x180015893  push    rsi
0x180015894  push    rdi
0x180015895  push    r14
0x180015897  sub     rsp, 20h
0x18001589b  mov     rbx, rdx
0x18001589e  mov     rdi, rcx
0x1800158a1  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800158a6  mov     rsi, [rdi]
0x1800158a9  xor     eax, eax
0x1800158ab  movzx   ecx, word ptr [rsi]
0x1800158ae  cmp     ax, cx
0x1800158b1  jz      loc_18001595C
0x1800158b7  lea     r14d, [rax+27h]
0x1800158bb  lea     rbp, [rbx+2000h]
0x1800158c2  cmp     r14w, cx
0x1800158c6  jnz     loc_18001598C
0x1800158cc  mov     rcx, rsi; lpsz
0x1800158cf  call    cs:__imp_CharNextW
0x1800158d5  mov     [rdi], rax
0x1800158d8  mov     rcx, rax; lpsz
0x1800158db  movzx   edx, word ptr [rax]
0x1800158de  xor     eax, eax
0x1800158e0  cmp     ax, dx
0x1800158e3  jz      loc_18001596C
0x1800158e9  cmp     r14w, dx
0x1800158ed  jnz     short loc_1800158FB
0x1800158ef  call    cs:__imp_CharNextW
0x1800158f5  cmp     r14w, [rax]
0x1800158f9  jnz     short loc_18001596C
0x1800158fb  mov     rsi, [rdi]
0x1800158fe  cmp     r14w, [rsi]
0x180015902  jnz     short loc_180015913
0x180015904  mov     rcx, rsi; lpsz
0x180015907  call    cs:__imp_CharNextW
0x18001590d  mov     rsi, rax
0x180015910  mov     [rdi], rax
0x180015913  mov     rcx, rsi; lpsz
0x180015916  call    cs:__imp_CharNextW
0x18001591c  mov     rdx, rax
0x18001591f  mov     [rdi], rax
0x180015922  sub     rdx, rsi
0x180015925  sar     rdx, 1
0x180015928  lea     rcx, [rdx+1]
0x18001592c  lea     rcx, [rbx+rcx*2]
0x180015930  cmp     rcx, rbp
0x180015933  jnb     short loc_18001595C
0x180015935  xor     ecx, ecx
0x180015937  test    edx, edx
0x180015939  jle     short loc_18001594F
0x18001593b  movzx   eax, word ptr [rsi]
0x18001593e  inc     ecx
0x180015940  mov     [rbx], ax
0x180015943  lea     rsi, [rsi+2]
0x180015947  add     rbx, 2
0x18001594b  cmp     ecx, edx
0x18001594d  jl      short loc_18001593B
0x18001594f  mov     rcx, [rdi]
0x180015952  xor     eax, eax
0x180015954  movzx   edx, word ptr [rcx]
0x180015957  cmp     ax, dx
0x18001595a  jnz     short loc_1800158E9
0x18001595c  mov     eax, 80020009h
0x180015961  add     rsp, 20h
0x180015965  pop     r14
0x180015967  pop     rdi
0x180015968  pop     rsi
0x180015969  pop     rbp
0x18001596a  pop     rbx
0x18001596b  retn
0x18001596c  mov     rcx, [rdi]
0x18001596f  xor     eax, eax
0x180015971  cmp     ax, [rcx]
0x180015974  jz      short loc_18001595C
0x180015976  cmp     rbx, rbp
0x180015979  jnb     short loc_18001595C
0x18001597b  mov     [rbx], ax
0x18001597e  mov     rcx, [rdi]; lpsz
0x180015981  call    cs:__imp_CharNextW
0x180015987  mov     [rdi], rax
0x18001598a  jmp     short loc_1800159FA
0x18001598c  movzx   ecx, cx
0x18001598f  sub     ecx, 9
0x180015992  jz      short loc_1800159EC
0x180015994  sub     ecx, 1
0x180015997  jz      short loc_1800159EC
0x180015999  sub     ecx, 3
0x18001599c  jz      short loc_1800159EC
0x18001599e  cmp     ecx, 13h
0x1800159a1  jz      short loc_1800159EC
0x1800159a3  mov     rcx, rsi; lpsz
0x1800159a6  call    cs:__imp_CharNextW
0x1800159ac  mov     rdx, rax
0x1800159af  mov     [rdi], rax
0x1800159b2  sub     rdx, rsi
0x1800159b5  sar     rdx, 1
0x1800159b8  lea     rcx, [rdx+1]
0x1800159bc  lea     rcx, [rbx+rcx*2]
0x1800159c0  cmp     rcx, rbp
0x1800159c3  jnb     short loc_18001595C
0x1800159c5  xor     ecx, ecx
0x1800159c7  test    edx, edx
0x1800159c9  jle     short loc_1800159DF
0x1800159cb  movzx   eax, word ptr [rsi]
0x1800159ce  inc     ecx
0x1800159d0  mov     [rbx], ax
0x1800159d3  lea     rsi, [rsi+2]
0x1800159d7  add     rbx, 2
0x1800159db  cmp     ecx, edx
0x1800159dd  jl      short loc_1800159CB
0x1800159df  mov     rsi, [rdi]
0x1800159e2  xor     eax, eax
0x1800159e4  movzx   ecx, word ptr [rsi]
0x1800159e7  cmp     ax, cx
0x1800159ea  jnz     short loc_18001598C
0x1800159ec  cmp     rbx, rbp
0x1800159ef  jnb     loc_18001595C
0x1800159f5  xor     eax, eax
0x1800159f7  mov     [rbx], ax
0x1800159fa  xor     eax, eax
0x1800159fc  jmp     loc_180015961
```
