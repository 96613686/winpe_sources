# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800072f0`
- end: `0x180007461`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `369`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003dbc`
- `0x1800079dc`
- `0x180007e04`
- `0x180008730`

## callees

- `0x1800072f0`
- `0x1800087c4`

## import_xrefs

- `USER32!CharNextW` at `0x18000732f`
- `USER32!CharNextW` at `0x18000734f`
- `USER32!CharNextW` at `0x180007367`
- `USER32!CharNextW` at `0x180007376`
- `USER32!CharNextW` at `0x1800073e1`
- `USER32!CharNextW` at `0x180007406`
- `USER32!CharNextW` at `0x18000732f`
- `USER32!CharNextW` at `0x18000734f`
- `USER32!CharNextW` at `0x180007367`
- `USER32!CharNextW` at `0x180007376`
- `USER32!CharNextW` at `0x1800073e1`
- `USER32!CharNextW` at `0x180007406`

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
0x1800072f0  push    rbx
0x1800072f2  push    rbp
0x1800072f3  push    rsi
0x1800072f4  push    rdi
0x1800072f5  push    r14
0x1800072f7  sub     rsp, 20h
0x1800072fb  mov     rbx, rdx
0x1800072fe  mov     rdi, rcx
0x180007301  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180007306  mov     rsi, [rdi]
0x180007309  xor     eax, eax
0x18000730b  movzx   ecx, word ptr [rsi]
0x18000730e  cmp     ax, cx
0x180007311  jz      loc_1800073BC
0x180007317  lea     r14d, [rax+27h]
0x18000731b  lea     rbp, [rbx+2000h]
0x180007322  cmp     r14w, cx
0x180007326  jnz     loc_1800073EC
0x18000732c  mov     rcx, rsi; lpsz
0x18000732f  call    cs:__imp_CharNextW
0x180007335  mov     [rdi], rax
0x180007338  mov     rcx, rax; lpsz
0x18000733b  movzx   edx, word ptr [rax]
0x18000733e  xor     eax, eax
0x180007340  cmp     ax, dx
0x180007343  jz      loc_1800073CC
0x180007349  cmp     r14w, dx
0x18000734d  jnz     short loc_18000735B
0x18000734f  call    cs:__imp_CharNextW
0x180007355  cmp     r14w, [rax]
0x180007359  jnz     short loc_1800073CC
0x18000735b  mov     rsi, [rdi]
0x18000735e  cmp     r14w, [rsi]
0x180007362  jnz     short loc_180007373
0x180007364  mov     rcx, rsi; lpsz
0x180007367  call    cs:__imp_CharNextW
0x18000736d  mov     rsi, rax
0x180007370  mov     [rdi], rax
0x180007373  mov     rcx, rsi; lpsz
0x180007376  call    cs:__imp_CharNextW
0x18000737c  mov     rdx, rax
0x18000737f  mov     [rdi], rax
0x180007382  sub     rdx, rsi
0x180007385  sar     rdx, 1
0x180007388  lea     rcx, [rdx+1]
0x18000738c  lea     rcx, [rbx+rcx*2]
0x180007390  cmp     rcx, rbp
0x180007393  jnb     short loc_1800073BC
0x180007395  xor     ecx, ecx
0x180007397  test    edx, edx
0x180007399  jle     short loc_1800073AF
0x18000739b  movzx   eax, word ptr [rsi]
0x18000739e  inc     ecx
0x1800073a0  mov     [rbx], ax
0x1800073a3  lea     rsi, [rsi+2]
0x1800073a7  add     rbx, 2
0x1800073ab  cmp     ecx, edx
0x1800073ad  jl      short loc_18000739B
0x1800073af  mov     rcx, [rdi]
0x1800073b2  xor     eax, eax
0x1800073b4  movzx   edx, word ptr [rcx]
0x1800073b7  cmp     ax, dx
0x1800073ba  jnz     short loc_180007349
0x1800073bc  mov     eax, 80020009h
0x1800073c1  add     rsp, 20h
0x1800073c5  pop     r14
0x1800073c7  pop     rdi
0x1800073c8  pop     rsi
0x1800073c9  pop     rbp
0x1800073ca  pop     rbx
0x1800073cb  retn
0x1800073cc  mov     rcx, [rdi]
0x1800073cf  xor     eax, eax
0x1800073d1  cmp     ax, [rcx]
0x1800073d4  jz      short loc_1800073BC
0x1800073d6  cmp     rbx, rbp
0x1800073d9  jnb     short loc_1800073BC
0x1800073db  mov     [rbx], ax
0x1800073de  mov     rcx, [rdi]; lpsz
0x1800073e1  call    cs:__imp_CharNextW
0x1800073e7  mov     [rdi], rax
0x1800073ea  jmp     short loc_18000745A
0x1800073ec  movzx   ecx, cx
0x1800073ef  sub     ecx, 9
0x1800073f2  jz      short loc_18000744C
0x1800073f4  sub     ecx, 1
0x1800073f7  jz      short loc_18000744C
0x1800073f9  sub     ecx, 3
0x1800073fc  jz      short loc_18000744C
0x1800073fe  cmp     ecx, 13h
0x180007401  jz      short loc_18000744C
0x180007403  mov     rcx, rsi; lpsz
0x180007406  call    cs:__imp_CharNextW
0x18000740c  mov     rdx, rax
0x18000740f  mov     [rdi], rax
0x180007412  sub     rdx, rsi
0x180007415  sar     rdx, 1
0x180007418  lea     rcx, [rdx+1]
0x18000741c  lea     rcx, [rbx+rcx*2]
0x180007420  cmp     rcx, rbp
0x180007423  jnb     short loc_1800073BC
0x180007425  xor     ecx, ecx
0x180007427  test    edx, edx
0x180007429  jle     short loc_18000743F
0x18000742b  movzx   eax, word ptr [rsi]
0x18000742e  inc     ecx
0x180007430  mov     [rbx], ax
0x180007433  lea     rsi, [rsi+2]
0x180007437  add     rbx, 2
0x18000743b  cmp     ecx, edx
0x18000743d  jl      short loc_18000742B
0x18000743f  mov     rsi, [rdi]
0x180007442  xor     eax, eax
0x180007444  movzx   ecx, word ptr [rsi]
0x180007447  cmp     ax, cx
0x18000744a  jnz     short loc_1800073EC
0x18000744c  cmp     rbx, rbp
0x18000744f  jnb     loc_1800073BC
0x180007455  xor     eax, eax
0x180007457  mov     [rbx], ax
0x18000745a  xor     eax, eax
0x18000745c  jmp     loc_1800073C1
```
