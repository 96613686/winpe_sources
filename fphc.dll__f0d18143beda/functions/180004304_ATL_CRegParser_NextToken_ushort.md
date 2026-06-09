# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180004304`
- end: `0x18000449b`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030ac`
- `0x1800048f8`
- `0x180004c68`
- `0x18000541c`

## callees

- `0x180004304`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004339`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004367`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004387`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000439f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800043ae`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004419`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000443e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004339`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004367`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004387`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000439f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800043ae`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004419`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000443e`

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
0x180004304  push    rbx
0x180004306  push    rbp
0x180004307  push    rsi
0x180004308  push    rdi
0x180004309  push    r14
0x18000430b  sub     rsp, 20h
0x18000430f  mov     rbx, rdx
0x180004312  mov     rdi, rcx
0x180004315  mov     rsi, [rdi]
0x180004318  movzx   ecx, word ptr [rsi]
0x18000431b  mov     r8d, ecx
0x18000431e  sub     r8d, 9
0x180004322  jz      short loc_180004336
0x180004324  sub     r8d, 1
0x180004328  jz      short loc_180004336
0x18000432a  sub     r8d, 3
0x18000432e  jz      short loc_180004336
0x180004330  cmp     r8d, 13h
0x180004334  jnz     short loc_180004344
0x180004336  mov     rcx, rsi; lpsz
0x180004339  call    cs:__imp_CharNextW
0x18000433f  mov     [rdi], rax
0x180004342  jmp     short loc_180004315
0x180004344  xor     eax, eax
0x180004346  cmp     ax, cx
0x180004349  jz      loc_1800043F4
0x18000434f  lea     r14d, [rax+27h]
0x180004353  lea     rbp, [rbx+2000h]
0x18000435a  cmp     r14w, cx
0x18000435e  jnz     loc_180004424
0x180004364  mov     rcx, rsi; lpsz
0x180004367  call    cs:__imp_CharNextW
0x18000436d  mov     [rdi], rax
0x180004370  mov     rcx, rax; lpsz
0x180004373  movzx   edx, word ptr [rax]
0x180004376  xor     eax, eax
0x180004378  cmp     ax, dx
0x18000437b  jz      loc_180004404
0x180004381  cmp     r14w, dx
0x180004385  jnz     short loc_180004393
0x180004387  call    cs:__imp_CharNextW
0x18000438d  cmp     r14w, [rax]
0x180004391  jnz     short loc_180004404
0x180004393  mov     rsi, [rdi]
0x180004396  cmp     r14w, [rsi]
0x18000439a  jnz     short loc_1800043AB
0x18000439c  mov     rcx, rsi; lpsz
0x18000439f  call    cs:__imp_CharNextW
0x1800043a5  mov     rsi, rax
0x1800043a8  mov     [rdi], rax
0x1800043ab  mov     rcx, rsi; lpsz
0x1800043ae  call    cs:__imp_CharNextW
0x1800043b4  mov     rdx, rax
0x1800043b7  mov     [rdi], rax
0x1800043ba  sub     rdx, rsi
0x1800043bd  sar     rdx, 1
0x1800043c0  lea     rcx, [rdx+1]
0x1800043c4  lea     rcx, [rbx+rcx*2]
0x1800043c8  cmp     rcx, rbp
0x1800043cb  jnb     short loc_1800043F4
0x1800043cd  xor     ecx, ecx
0x1800043cf  test    edx, edx
0x1800043d1  jle     short loc_1800043E7
0x1800043d3  movzx   eax, word ptr [rsi]
0x1800043d6  inc     ecx
0x1800043d8  mov     [rbx], ax
0x1800043db  lea     rsi, [rsi+2]
0x1800043df  add     rbx, 2
0x1800043e3  cmp     ecx, edx
0x1800043e5  jl      short loc_1800043D3
0x1800043e7  mov     rcx, [rdi]
0x1800043ea  xor     eax, eax
0x1800043ec  movzx   edx, word ptr [rcx]
0x1800043ef  cmp     ax, dx
0x1800043f2  jnz     short loc_180004381
0x1800043f4  mov     eax, 80020009h
0x1800043f9  add     rsp, 20h
0x1800043fd  pop     r14
0x1800043ff  pop     rdi
0x180004400  pop     rsi
0x180004401  pop     rbp
0x180004402  pop     rbx
0x180004403  retn
0x180004404  mov     rcx, [rdi]
0x180004407  xor     eax, eax
0x180004409  cmp     ax, [rcx]
0x18000440c  jz      short loc_1800043F4
0x18000440e  cmp     rbx, rbp
0x180004411  jnb     short loc_1800043F4
0x180004413  mov     [rbx], ax
0x180004416  mov     rcx, [rdi]; lpsz
0x180004419  call    cs:__imp_CharNextW
0x18000441f  mov     [rdi], rax
0x180004422  jmp     short loc_180004494
0x180004424  movzx   ecx, cx
0x180004427  sub     ecx, 9
0x18000442a  jz      short loc_180004486
0x18000442c  sub     ecx, 1
0x18000442f  jz      short loc_180004486
0x180004431  sub     ecx, 3
0x180004434  jz      short loc_180004486
0x180004436  cmp     ecx, 13h
0x180004439  jz      short loc_180004486
0x18000443b  mov     rcx, rsi; lpsz
0x18000443e  call    cs:__imp_CharNextW
0x180004444  mov     rdx, rax
0x180004447  mov     [rdi], rax
0x18000444a  sub     rdx, rsi
0x18000444d  sar     rdx, 1
0x180004450  lea     rcx, [rdx+1]
0x180004454  lea     rcx, [rbx+rcx*2]
0x180004458  cmp     rcx, rbp
0x18000445b  jnb     short loc_1800043F4
0x18000445d  xor     ecx, ecx
0x18000445f  test    edx, edx
0x180004461  jle     short loc_180004477
0x180004463  movzx   eax, word ptr [rsi]
0x180004466  inc     ecx
0x180004468  mov     [rbx], ax
0x18000446b  lea     rsi, [rsi+2]
0x18000446f  add     rbx, 2
0x180004473  cmp     ecx, edx
0x180004475  jl      short loc_180004463
0x180004477  mov     rsi, [rdi]
0x18000447a  xor     eax, eax
0x18000447c  cmp     ax, [rsi]
0x18000447f  jz      short loc_180004486
0x180004481  movzx   ecx, word ptr [rsi]
0x180004484  jmp     short loc_180004424
0x180004486  cmp     rbx, rbp
0x180004489  jnb     loc_1800043F4
0x18000448f  xor     eax, eax
0x180004491  mov     [rbx], ax
0x180004494  xor     eax, eax
0x180004496  jmp     loc_1800043F9
```
