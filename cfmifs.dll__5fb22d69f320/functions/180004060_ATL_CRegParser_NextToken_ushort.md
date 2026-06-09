# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180004060`
- end: `0x1800041f7`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d44`
- `0x180004688`
- `0x1800049dc`
- `0x1800052b4`

## callees

- `0x180004060`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004095`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800040c3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800040e3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800040fb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000410a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004175`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000419a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004095`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800040c3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800040e3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800040fb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000410a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004175`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000419a`

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
0x180004060  push    rbx
0x180004062  push    rbp
0x180004063  push    rsi
0x180004064  push    rdi
0x180004065  push    r14
0x180004067  sub     rsp, 20h
0x18000406b  mov     rbx, rdx
0x18000406e  mov     rdi, rcx
0x180004071  mov     rsi, [rdi]
0x180004074  movzx   ecx, word ptr [rsi]
0x180004077  mov     r8d, ecx
0x18000407a  sub     r8d, 9
0x18000407e  jz      short loc_180004092
0x180004080  sub     r8d, 1
0x180004084  jz      short loc_180004092
0x180004086  sub     r8d, 3
0x18000408a  jz      short loc_180004092
0x18000408c  cmp     r8d, 13h
0x180004090  jnz     short loc_1800040A0
0x180004092  mov     rcx, rsi; lpsz
0x180004095  call    cs:__imp_CharNextW
0x18000409b  mov     [rdi], rax
0x18000409e  jmp     short loc_180004071
0x1800040a0  xor     eax, eax
0x1800040a2  cmp     ax, cx
0x1800040a5  jz      loc_180004150
0x1800040ab  lea     r14d, [rax+27h]
0x1800040af  lea     rbp, [rbx+2000h]
0x1800040b6  cmp     r14w, cx
0x1800040ba  jnz     loc_180004180
0x1800040c0  mov     rcx, rsi; lpsz
0x1800040c3  call    cs:__imp_CharNextW
0x1800040c9  mov     [rdi], rax
0x1800040cc  mov     rcx, rax; lpsz
0x1800040cf  movzx   edx, word ptr [rax]
0x1800040d2  xor     eax, eax
0x1800040d4  cmp     ax, dx
0x1800040d7  jz      loc_180004160
0x1800040dd  cmp     r14w, dx
0x1800040e1  jnz     short loc_1800040EF
0x1800040e3  call    cs:__imp_CharNextW
0x1800040e9  cmp     r14w, [rax]
0x1800040ed  jnz     short loc_180004160
0x1800040ef  mov     rsi, [rdi]
0x1800040f2  cmp     r14w, [rsi]
0x1800040f6  jnz     short loc_180004107
0x1800040f8  mov     rcx, rsi; lpsz
0x1800040fb  call    cs:__imp_CharNextW
0x180004101  mov     rsi, rax
0x180004104  mov     [rdi], rax
0x180004107  mov     rcx, rsi; lpsz
0x18000410a  call    cs:__imp_CharNextW
0x180004110  mov     rdx, rax
0x180004113  mov     [rdi], rax
0x180004116  sub     rdx, rsi
0x180004119  sar     rdx, 1
0x18000411c  lea     rcx, [rdx+1]
0x180004120  lea     rcx, [rbx+rcx*2]
0x180004124  cmp     rcx, rbp
0x180004127  jnb     short loc_180004150
0x180004129  xor     ecx, ecx
0x18000412b  test    edx, edx
0x18000412d  jle     short loc_180004143
0x18000412f  movzx   eax, word ptr [rsi]
0x180004132  inc     ecx
0x180004134  mov     [rbx], ax
0x180004137  lea     rsi, [rsi+2]
0x18000413b  add     rbx, 2
0x18000413f  cmp     ecx, edx
0x180004141  jl      short loc_18000412F
0x180004143  mov     rcx, [rdi]
0x180004146  xor     eax, eax
0x180004148  movzx   edx, word ptr [rcx]
0x18000414b  cmp     ax, dx
0x18000414e  jnz     short loc_1800040DD
0x180004150  mov     eax, 80020009h
0x180004155  add     rsp, 20h
0x180004159  pop     r14
0x18000415b  pop     rdi
0x18000415c  pop     rsi
0x18000415d  pop     rbp
0x18000415e  pop     rbx
0x18000415f  retn
0x180004160  mov     rcx, [rdi]
0x180004163  xor     eax, eax
0x180004165  cmp     ax, [rcx]
0x180004168  jz      short loc_180004150
0x18000416a  cmp     rbx, rbp
0x18000416d  jnb     short loc_180004150
0x18000416f  mov     [rbx], ax
0x180004172  mov     rcx, [rdi]; lpsz
0x180004175  call    cs:__imp_CharNextW
0x18000417b  mov     [rdi], rax
0x18000417e  jmp     short loc_1800041F0
0x180004180  movzx   ecx, cx
0x180004183  sub     ecx, 9
0x180004186  jz      short loc_1800041E2
0x180004188  sub     ecx, 1
0x18000418b  jz      short loc_1800041E2
0x18000418d  sub     ecx, 3
0x180004190  jz      short loc_1800041E2
0x180004192  cmp     ecx, 13h
0x180004195  jz      short loc_1800041E2
0x180004197  mov     rcx, rsi; lpsz
0x18000419a  call    cs:__imp_CharNextW
0x1800041a0  mov     rdx, rax
0x1800041a3  mov     [rdi], rax
0x1800041a6  sub     rdx, rsi
0x1800041a9  sar     rdx, 1
0x1800041ac  lea     rcx, [rdx+1]
0x1800041b0  lea     rcx, [rbx+rcx*2]
0x1800041b4  cmp     rcx, rbp
0x1800041b7  jnb     short loc_180004150
0x1800041b9  xor     ecx, ecx
0x1800041bb  test    edx, edx
0x1800041bd  jle     short loc_1800041D3
0x1800041bf  movzx   eax, word ptr [rsi]
0x1800041c2  inc     ecx
0x1800041c4  mov     [rbx], ax
0x1800041c7  lea     rsi, [rsi+2]
0x1800041cb  add     rbx, 2
0x1800041cf  cmp     ecx, edx
0x1800041d1  jl      short loc_1800041BF
0x1800041d3  mov     rsi, [rdi]
0x1800041d6  xor     eax, eax
0x1800041d8  cmp     ax, [rsi]
0x1800041db  jz      short loc_1800041E2
0x1800041dd  movzx   ecx, word ptr [rsi]
0x1800041e0  jmp     short loc_180004180
0x1800041e2  cmp     rbx, rbp
0x1800041e5  jnb     loc_180004150
0x1800041eb  xor     eax, eax
0x1800041ed  mov     [rbx], ax
0x1800041f0  xor     eax, eax
0x1800041f2  jmp     loc_180004155
```
