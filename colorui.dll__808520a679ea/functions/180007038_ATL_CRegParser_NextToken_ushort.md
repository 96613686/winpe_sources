# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180007038`
- end: `0x1800071cf`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004314`
- `0x180008a7c`
- `0x180008dd0`
- `0x180009e1c`

## callees

- `0x180007038`

## import_xrefs

- `USER32!CharNextW` at `0x18000706d`
- `USER32!CharNextW` at `0x18000709b`
- `USER32!CharNextW` at `0x1800070bb`
- `USER32!CharNextW` at `0x1800070d3`
- `USER32!CharNextW` at `0x1800070e2`
- `USER32!CharNextW` at `0x18000714d`
- `USER32!CharNextW` at `0x180007172`
- `USER32!CharNextW` at `0x18000706d`
- `USER32!CharNextW` at `0x18000709b`
- `USER32!CharNextW` at `0x1800070bb`
- `USER32!CharNextW` at `0x1800070d3`
- `USER32!CharNextW` at `0x1800070e2`
- `USER32!CharNextW` at `0x18000714d`
- `USER32!CharNextW` at `0x180007172`

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
0x180007038  push    rbx
0x18000703a  push    rbp
0x18000703b  push    rsi
0x18000703c  push    rdi
0x18000703d  push    r14
0x18000703f  sub     rsp, 20h
0x180007043  mov     rbx, rdx
0x180007046  mov     rdi, rcx
0x180007049  mov     rsi, [rdi]
0x18000704c  movzx   ecx, word ptr [rsi]
0x18000704f  mov     r8d, ecx
0x180007052  sub     r8d, 9
0x180007056  jz      short loc_18000706A
0x180007058  sub     r8d, 1
0x18000705c  jz      short loc_18000706A
0x18000705e  sub     r8d, 3
0x180007062  jz      short loc_18000706A
0x180007064  cmp     r8d, 13h
0x180007068  jnz     short loc_180007078
0x18000706a  mov     rcx, rsi; lpsz
0x18000706d  call    cs:__imp_CharNextW
0x180007073  mov     [rdi], rax
0x180007076  jmp     short loc_180007049
0x180007078  xor     eax, eax
0x18000707a  cmp     ax, cx
0x18000707d  jz      loc_180007128
0x180007083  lea     r14d, [rax+27h]
0x180007087  lea     rbp, [rbx+2000h]
0x18000708e  cmp     r14w, cx
0x180007092  jnz     loc_180007158
0x180007098  mov     rcx, rsi; lpsz
0x18000709b  call    cs:__imp_CharNextW
0x1800070a1  mov     [rdi], rax
0x1800070a4  mov     rcx, rax; lpsz
0x1800070a7  movzx   edx, word ptr [rax]
0x1800070aa  xor     eax, eax
0x1800070ac  cmp     ax, dx
0x1800070af  jz      loc_180007138
0x1800070b5  cmp     r14w, dx
0x1800070b9  jnz     short loc_1800070C7
0x1800070bb  call    cs:__imp_CharNextW
0x1800070c1  cmp     r14w, [rax]
0x1800070c5  jnz     short loc_180007138
0x1800070c7  mov     rsi, [rdi]
0x1800070ca  cmp     r14w, [rsi]
0x1800070ce  jnz     short loc_1800070DF
0x1800070d0  mov     rcx, rsi; lpsz
0x1800070d3  call    cs:__imp_CharNextW
0x1800070d9  mov     rsi, rax
0x1800070dc  mov     [rdi], rax
0x1800070df  mov     rcx, rsi; lpsz
0x1800070e2  call    cs:__imp_CharNextW
0x1800070e8  mov     rdx, rax
0x1800070eb  mov     [rdi], rax
0x1800070ee  sub     rdx, rsi
0x1800070f1  sar     rdx, 1
0x1800070f4  lea     rcx, [rdx+1]
0x1800070f8  lea     rcx, [rbx+rcx*2]
0x1800070fc  cmp     rcx, rbp
0x1800070ff  jnb     short loc_180007128
0x180007101  xor     ecx, ecx
0x180007103  test    edx, edx
0x180007105  jle     short loc_18000711B
0x180007107  movzx   eax, word ptr [rsi]
0x18000710a  inc     ecx
0x18000710c  mov     [rbx], ax
0x18000710f  lea     rsi, [rsi+2]
0x180007113  add     rbx, 2
0x180007117  cmp     ecx, edx
0x180007119  jl      short loc_180007107
0x18000711b  mov     rcx, [rdi]
0x18000711e  xor     eax, eax
0x180007120  movzx   edx, word ptr [rcx]
0x180007123  cmp     ax, dx
0x180007126  jnz     short loc_1800070B5
0x180007128  mov     eax, 80020009h
0x18000712d  add     rsp, 20h
0x180007131  pop     r14
0x180007133  pop     rdi
0x180007134  pop     rsi
0x180007135  pop     rbp
0x180007136  pop     rbx
0x180007137  retn
0x180007138  mov     rcx, [rdi]
0x18000713b  xor     eax, eax
0x18000713d  cmp     ax, [rcx]
0x180007140  jz      short loc_180007128
0x180007142  cmp     rbx, rbp
0x180007145  jnb     short loc_180007128
0x180007147  mov     [rbx], ax
0x18000714a  mov     rcx, [rdi]; lpsz
0x18000714d  call    cs:__imp_CharNextW
0x180007153  mov     [rdi], rax
0x180007156  jmp     short loc_1800071C8
0x180007158  movzx   ecx, cx
0x18000715b  sub     ecx, 9
0x18000715e  jz      short loc_1800071BA
0x180007160  sub     ecx, 1
0x180007163  jz      short loc_1800071BA
0x180007165  sub     ecx, 3
0x180007168  jz      short loc_1800071BA
0x18000716a  cmp     ecx, 13h
0x18000716d  jz      short loc_1800071BA
0x18000716f  mov     rcx, rsi; lpsz
0x180007172  call    cs:__imp_CharNextW
0x180007178  mov     rdx, rax
0x18000717b  mov     [rdi], rax
0x18000717e  sub     rdx, rsi
0x180007181  sar     rdx, 1
0x180007184  lea     rcx, [rdx+1]
0x180007188  lea     rcx, [rbx+rcx*2]
0x18000718c  cmp     rcx, rbp
0x18000718f  jnb     short loc_180007128
0x180007191  xor     ecx, ecx
0x180007193  test    edx, edx
0x180007195  jle     short loc_1800071AB
0x180007197  movzx   eax, word ptr [rsi]
0x18000719a  inc     ecx
0x18000719c  mov     [rbx], ax
0x18000719f  lea     rsi, [rsi+2]
0x1800071a3  add     rbx, 2
0x1800071a7  cmp     ecx, edx
0x1800071a9  jl      short loc_180007197
0x1800071ab  mov     rsi, [rdi]
0x1800071ae  xor     eax, eax
0x1800071b0  cmp     ax, [rsi]
0x1800071b3  jz      short loc_1800071BA
0x1800071b5  movzx   ecx, word ptr [rsi]
0x1800071b8  jmp     short loc_180007158
0x1800071ba  cmp     rbx, rbp
0x1800071bd  jnb     loc_180007128
0x1800071c3  xor     eax, eax
0x1800071c5  mov     [rbx], ax
0x1800071c8  xor     eax, eax
0x1800071ca  jmp     loc_18000712D
```
