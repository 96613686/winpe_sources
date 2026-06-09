# ATL::CRegParser::NextToken(ushort *)

- ea: `0x14000cf98`
- end: `0x14000d12f`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c654`
- `0x14000d578`
- `0x14000d8cc`
- `0x14000e07c`

## callees

- `0x14000cf98`

## import_xrefs

- `USER32!CharNextW` at `0x14000cfcd`
- `USER32!CharNextW` at `0x14000cffb`
- `USER32!CharNextW` at `0x14000d01b`
- `USER32!CharNextW` at `0x14000d033`
- `USER32!CharNextW` at `0x14000d042`
- `USER32!CharNextW` at `0x14000d0ad`
- `USER32!CharNextW` at `0x14000d0d2`
- `USER32!CharNextW` at `0x14000cfcd`
- `USER32!CharNextW` at `0x14000cffb`
- `USER32!CharNextW` at `0x14000d01b`
- `USER32!CharNextW` at `0x14000d033`
- `USER32!CharNextW` at `0x14000d042`
- `USER32!CharNextW` at `0x14000d0ad`
- `USER32!CharNextW` at `0x14000d0d2`

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
0x14000cf98  push    rbx
0x14000cf9a  push    rbp
0x14000cf9b  push    rsi
0x14000cf9c  push    rdi
0x14000cf9d  push    r14
0x14000cf9f  sub     rsp, 20h
0x14000cfa3  mov     rbx, rdx
0x14000cfa6  mov     rdi, rcx
0x14000cfa9  mov     rsi, [rdi]
0x14000cfac  movzx   ecx, word ptr [rsi]
0x14000cfaf  mov     r8d, ecx
0x14000cfb2  sub     r8d, 9
0x14000cfb6  jz      short loc_14000CFCA
0x14000cfb8  sub     r8d, 1
0x14000cfbc  jz      short loc_14000CFCA
0x14000cfbe  sub     r8d, 3
0x14000cfc2  jz      short loc_14000CFCA
0x14000cfc4  cmp     r8d, 13h
0x14000cfc8  jnz     short loc_14000CFD8
0x14000cfca  mov     rcx, rsi; lpsz
0x14000cfcd  call    cs:__imp_CharNextW
0x14000cfd3  mov     [rdi], rax
0x14000cfd6  jmp     short loc_14000CFA9
0x14000cfd8  xor     eax, eax
0x14000cfda  cmp     ax, cx
0x14000cfdd  jz      loc_14000D088
0x14000cfe3  lea     r14d, [rax+27h]
0x14000cfe7  lea     rbp, [rbx+2000h]
0x14000cfee  cmp     r14w, cx
0x14000cff2  jnz     loc_14000D0B8
0x14000cff8  mov     rcx, rsi; lpsz
0x14000cffb  call    cs:__imp_CharNextW
0x14000d001  mov     [rdi], rax
0x14000d004  mov     rcx, rax; lpsz
0x14000d007  movzx   edx, word ptr [rax]
0x14000d00a  xor     eax, eax
0x14000d00c  cmp     ax, dx
0x14000d00f  jz      loc_14000D098
0x14000d015  cmp     r14w, dx
0x14000d019  jnz     short loc_14000D027
0x14000d01b  call    cs:__imp_CharNextW
0x14000d021  cmp     r14w, [rax]
0x14000d025  jnz     short loc_14000D098
0x14000d027  mov     rsi, [rdi]
0x14000d02a  cmp     r14w, [rsi]
0x14000d02e  jnz     short loc_14000D03F
0x14000d030  mov     rcx, rsi; lpsz
0x14000d033  call    cs:__imp_CharNextW
0x14000d039  mov     rsi, rax
0x14000d03c  mov     [rdi], rax
0x14000d03f  mov     rcx, rsi; lpsz
0x14000d042  call    cs:__imp_CharNextW
0x14000d048  mov     rdx, rax
0x14000d04b  mov     [rdi], rax
0x14000d04e  sub     rdx, rsi
0x14000d051  sar     rdx, 1
0x14000d054  lea     rcx, [rdx+1]
0x14000d058  lea     rcx, [rbx+rcx*2]
0x14000d05c  cmp     rcx, rbp
0x14000d05f  jnb     short loc_14000D088
0x14000d061  xor     ecx, ecx
0x14000d063  test    edx, edx
0x14000d065  jle     short loc_14000D07B
0x14000d067  movzx   eax, word ptr [rsi]
0x14000d06a  inc     ecx
0x14000d06c  mov     [rbx], ax
0x14000d06f  lea     rsi, [rsi+2]
0x14000d073  add     rbx, 2
0x14000d077  cmp     ecx, edx
0x14000d079  jl      short loc_14000D067
0x14000d07b  mov     rcx, [rdi]
0x14000d07e  xor     eax, eax
0x14000d080  movzx   edx, word ptr [rcx]
0x14000d083  cmp     ax, dx
0x14000d086  jnz     short loc_14000D015
0x14000d088  mov     eax, 80020009h
0x14000d08d  add     rsp, 20h
0x14000d091  pop     r14
0x14000d093  pop     rdi
0x14000d094  pop     rsi
0x14000d095  pop     rbp
0x14000d096  pop     rbx
0x14000d097  retn
0x14000d098  mov     rcx, [rdi]
0x14000d09b  xor     eax, eax
0x14000d09d  cmp     ax, [rcx]
0x14000d0a0  jz      short loc_14000D088
0x14000d0a2  cmp     rbx, rbp
0x14000d0a5  jnb     short loc_14000D088
0x14000d0a7  mov     [rbx], ax
0x14000d0aa  mov     rcx, [rdi]; lpsz
0x14000d0ad  call    cs:__imp_CharNextW
0x14000d0b3  mov     [rdi], rax
0x14000d0b6  jmp     short loc_14000D128
0x14000d0b8  movzx   ecx, cx
0x14000d0bb  sub     ecx, 9
0x14000d0be  jz      short loc_14000D11A
0x14000d0c0  sub     ecx, 1
0x14000d0c3  jz      short loc_14000D11A
0x14000d0c5  sub     ecx, 3
0x14000d0c8  jz      short loc_14000D11A
0x14000d0ca  cmp     ecx, 13h
0x14000d0cd  jz      short loc_14000D11A
0x14000d0cf  mov     rcx, rsi; lpsz
0x14000d0d2  call    cs:__imp_CharNextW
0x14000d0d8  mov     rdx, rax
0x14000d0db  mov     [rdi], rax
0x14000d0de  sub     rdx, rsi
0x14000d0e1  sar     rdx, 1
0x14000d0e4  lea     rcx, [rdx+1]
0x14000d0e8  lea     rcx, [rbx+rcx*2]
0x14000d0ec  cmp     rcx, rbp
0x14000d0ef  jnb     short loc_14000D088
0x14000d0f1  xor     ecx, ecx
0x14000d0f3  test    edx, edx
0x14000d0f5  jle     short loc_14000D10B
0x14000d0f7  movzx   eax, word ptr [rsi]
0x14000d0fa  inc     ecx
0x14000d0fc  mov     [rbx], ax
0x14000d0ff  lea     rsi, [rsi+2]
0x14000d103  add     rbx, 2
0x14000d107  cmp     ecx, edx
0x14000d109  jl      short loc_14000D0F7
0x14000d10b  mov     rsi, [rdi]
0x14000d10e  xor     eax, eax
0x14000d110  cmp     ax, [rsi]
0x14000d113  jz      short loc_14000D11A
0x14000d115  movzx   ecx, word ptr [rsi]
0x14000d118  jmp     short loc_14000D0B8
0x14000d11a  cmp     rbx, rbp
0x14000d11d  jnb     loc_14000D088
0x14000d123  xor     eax, eax
0x14000d125  mov     [rbx], ax
0x14000d128  xor     eax, eax
0x14000d12a  jmp     loc_14000D08D
```
