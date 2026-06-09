# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800070f0`
- end: `0x180007287`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b14`
- `0x1800078f8`
- `0x180007c4c`
- `0x180008714`

## callees

- `0x1800070f0`

## import_xrefs

- `USER32!CharNextW` at `0x180007125`
- `USER32!CharNextW` at `0x180007153`
- `USER32!CharNextW` at `0x180007173`
- `USER32!CharNextW` at `0x18000718b`
- `USER32!CharNextW` at `0x18000719a`
- `USER32!CharNextW` at `0x180007205`
- `USER32!CharNextW` at `0x18000722a`
- `USER32!CharNextW` at `0x180007125`
- `USER32!CharNextW` at `0x180007153`
- `USER32!CharNextW` at `0x180007173`
- `USER32!CharNextW` at `0x18000718b`
- `USER32!CharNextW` at `0x18000719a`
- `USER32!CharNextW` at `0x180007205`
- `USER32!CharNextW` at `0x18000722a`

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
0x1800070f0  push    rbx
0x1800070f2  push    rbp
0x1800070f3  push    rsi
0x1800070f4  push    rdi
0x1800070f5  push    r14
0x1800070f7  sub     rsp, 20h
0x1800070fb  mov     rbx, rdx
0x1800070fe  mov     rdi, rcx
0x180007101  mov     rsi, [rdi]
0x180007104  movzx   ecx, word ptr [rsi]
0x180007107  mov     r8d, ecx
0x18000710a  sub     r8d, 9
0x18000710e  jz      short loc_180007122
0x180007110  sub     r8d, 1
0x180007114  jz      short loc_180007122
0x180007116  sub     r8d, 3
0x18000711a  jz      short loc_180007122
0x18000711c  cmp     r8d, 13h
0x180007120  jnz     short loc_180007130
0x180007122  mov     rcx, rsi; lpsz
0x180007125  call    cs:__imp_CharNextW
0x18000712b  mov     [rdi], rax
0x18000712e  jmp     short loc_180007101
0x180007130  xor     eax, eax
0x180007132  cmp     ax, cx
0x180007135  jz      loc_1800071E0
0x18000713b  lea     r14d, [rax+27h]
0x18000713f  lea     rbp, [rbx+2000h]
0x180007146  cmp     r14w, cx
0x18000714a  jnz     loc_180007210
0x180007150  mov     rcx, rsi; lpsz
0x180007153  call    cs:__imp_CharNextW
0x180007159  mov     [rdi], rax
0x18000715c  mov     rcx, rax; lpsz
0x18000715f  movzx   edx, word ptr [rax]
0x180007162  xor     eax, eax
0x180007164  cmp     ax, dx
0x180007167  jz      loc_1800071F0
0x18000716d  cmp     r14w, dx
0x180007171  jnz     short loc_18000717F
0x180007173  call    cs:__imp_CharNextW
0x180007179  cmp     r14w, [rax]
0x18000717d  jnz     short loc_1800071F0
0x18000717f  mov     rsi, [rdi]
0x180007182  cmp     r14w, [rsi]
0x180007186  jnz     short loc_180007197
0x180007188  mov     rcx, rsi; lpsz
0x18000718b  call    cs:__imp_CharNextW
0x180007191  mov     rsi, rax
0x180007194  mov     [rdi], rax
0x180007197  mov     rcx, rsi; lpsz
0x18000719a  call    cs:__imp_CharNextW
0x1800071a0  mov     rdx, rax
0x1800071a3  mov     [rdi], rax
0x1800071a6  sub     rdx, rsi
0x1800071a9  sar     rdx, 1
0x1800071ac  lea     rcx, [rdx+1]
0x1800071b0  lea     rcx, [rbx+rcx*2]
0x1800071b4  cmp     rcx, rbp
0x1800071b7  jnb     short loc_1800071E0
0x1800071b9  xor     ecx, ecx
0x1800071bb  test    edx, edx
0x1800071bd  jle     short loc_1800071D3
0x1800071bf  movzx   eax, word ptr [rsi]
0x1800071c2  inc     ecx
0x1800071c4  mov     [rbx], ax
0x1800071c7  lea     rsi, [rsi+2]
0x1800071cb  add     rbx, 2
0x1800071cf  cmp     ecx, edx
0x1800071d1  jl      short loc_1800071BF
0x1800071d3  mov     rcx, [rdi]
0x1800071d6  xor     eax, eax
0x1800071d8  movzx   edx, word ptr [rcx]
0x1800071db  cmp     ax, dx
0x1800071de  jnz     short loc_18000716D
0x1800071e0  mov     eax, 80020009h
0x1800071e5  add     rsp, 20h
0x1800071e9  pop     r14
0x1800071eb  pop     rdi
0x1800071ec  pop     rsi
0x1800071ed  pop     rbp
0x1800071ee  pop     rbx
0x1800071ef  retn
0x1800071f0  mov     rcx, [rdi]
0x1800071f3  xor     eax, eax
0x1800071f5  cmp     ax, [rcx]
0x1800071f8  jz      short loc_1800071E0
0x1800071fa  cmp     rbx, rbp
0x1800071fd  jnb     short loc_1800071E0
0x1800071ff  mov     [rbx], ax
0x180007202  mov     rcx, [rdi]; lpsz
0x180007205  call    cs:__imp_CharNextW
0x18000720b  mov     [rdi], rax
0x18000720e  jmp     short loc_180007280
0x180007210  movzx   ecx, cx
0x180007213  sub     ecx, 9
0x180007216  jz      short loc_180007272
0x180007218  sub     ecx, 1
0x18000721b  jz      short loc_180007272
0x18000721d  sub     ecx, 3
0x180007220  jz      short loc_180007272
0x180007222  cmp     ecx, 13h
0x180007225  jz      short loc_180007272
0x180007227  mov     rcx, rsi; lpsz
0x18000722a  call    cs:__imp_CharNextW
0x180007230  mov     rdx, rax
0x180007233  mov     [rdi], rax
0x180007236  sub     rdx, rsi
0x180007239  sar     rdx, 1
0x18000723c  lea     rcx, [rdx+1]
0x180007240  lea     rcx, [rbx+rcx*2]
0x180007244  cmp     rcx, rbp
0x180007247  jnb     short loc_1800071E0
0x180007249  xor     ecx, ecx
0x18000724b  test    edx, edx
0x18000724d  jle     short loc_180007263
0x18000724f  movzx   eax, word ptr [rsi]
0x180007252  inc     ecx
0x180007254  mov     [rbx], ax
0x180007257  lea     rsi, [rsi+2]
0x18000725b  add     rbx, 2
0x18000725f  cmp     ecx, edx
0x180007261  jl      short loc_18000724F
0x180007263  mov     rsi, [rdi]
0x180007266  xor     eax, eax
0x180007268  cmp     ax, [rsi]
0x18000726b  jz      short loc_180007272
0x18000726d  movzx   ecx, word ptr [rsi]
0x180007270  jmp     short loc_180007210
0x180007272  cmp     rbx, rbp
0x180007275  jnb     loc_1800071E0
0x18000727b  xor     eax, eax
0x18000727d  mov     [rbx], ax
0x180007280  xor     eax, eax
0x180007282  jmp     loc_1800071E5
```
