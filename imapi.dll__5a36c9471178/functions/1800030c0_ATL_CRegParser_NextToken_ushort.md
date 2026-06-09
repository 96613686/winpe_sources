# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800030c0`
- end: `0x180003257`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002454`
- `0x1800036e8`
- `0x180003a3c`
- `0x180004304`

## callees

- `0x1800030c0`

## import_xrefs

- `USER32!CharNextW` at `0x1800030f5`
- `USER32!CharNextW` at `0x180003123`
- `USER32!CharNextW` at `0x180003143`
- `USER32!CharNextW` at `0x18000315b`
- `USER32!CharNextW` at `0x18000316a`
- `USER32!CharNextW` at `0x1800031d5`
- `USER32!CharNextW` at `0x1800031fa`
- `USER32!CharNextW` at `0x1800030f5`
- `USER32!CharNextW` at `0x180003123`
- `USER32!CharNextW` at `0x180003143`
- `USER32!CharNextW` at `0x18000315b`
- `USER32!CharNextW` at `0x18000316a`
- `USER32!CharNextW` at `0x1800031d5`
- `USER32!CharNextW` at `0x1800031fa`

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
0x1800030c0  push    rbx
0x1800030c2  push    rbp
0x1800030c3  push    rsi
0x1800030c4  push    rdi
0x1800030c5  push    r14
0x1800030c7  sub     rsp, 20h
0x1800030cb  mov     rbx, rdx
0x1800030ce  mov     rdi, rcx
0x1800030d1  mov     rsi, [rdi]
0x1800030d4  movzx   ecx, word ptr [rsi]
0x1800030d7  mov     r8d, ecx
0x1800030da  sub     r8d, 9
0x1800030de  jz      short loc_1800030F2
0x1800030e0  sub     r8d, 1
0x1800030e4  jz      short loc_1800030F2
0x1800030e6  sub     r8d, 3
0x1800030ea  jz      short loc_1800030F2
0x1800030ec  cmp     r8d, 13h
0x1800030f0  jnz     short loc_180003100
0x1800030f2  mov     rcx, rsi; lpsz
0x1800030f5  call    cs:__imp_CharNextW
0x1800030fb  mov     [rdi], rax
0x1800030fe  jmp     short loc_1800030D1
0x180003100  xor     eax, eax
0x180003102  cmp     ax, cx
0x180003105  jz      loc_1800031B0
0x18000310b  lea     r14d, [rax+27h]
0x18000310f  lea     rbp, [rbx+2000h]
0x180003116  cmp     r14w, cx
0x18000311a  jnz     loc_1800031E0
0x180003120  mov     rcx, rsi; lpsz
0x180003123  call    cs:__imp_CharNextW
0x180003129  mov     [rdi], rax
0x18000312c  mov     rcx, rax; lpsz
0x18000312f  movzx   edx, word ptr [rax]
0x180003132  xor     eax, eax
0x180003134  cmp     ax, dx
0x180003137  jz      loc_1800031C0
0x18000313d  cmp     r14w, dx
0x180003141  jnz     short loc_18000314F
0x180003143  call    cs:__imp_CharNextW
0x180003149  cmp     r14w, [rax]
0x18000314d  jnz     short loc_1800031C0
0x18000314f  mov     rsi, [rdi]
0x180003152  cmp     r14w, [rsi]
0x180003156  jnz     short loc_180003167
0x180003158  mov     rcx, rsi; lpsz
0x18000315b  call    cs:__imp_CharNextW
0x180003161  mov     rsi, rax
0x180003164  mov     [rdi], rax
0x180003167  mov     rcx, rsi; lpsz
0x18000316a  call    cs:__imp_CharNextW
0x180003170  mov     rdx, rax
0x180003173  mov     [rdi], rax
0x180003176  sub     rdx, rsi
0x180003179  sar     rdx, 1
0x18000317c  lea     rcx, [rdx+1]
0x180003180  lea     rcx, [rbx+rcx*2]
0x180003184  cmp     rcx, rbp
0x180003187  jnb     short loc_1800031B0
0x180003189  xor     ecx, ecx
0x18000318b  test    edx, edx
0x18000318d  jle     short loc_1800031A3
0x18000318f  movzx   eax, word ptr [rsi]
0x180003192  inc     ecx
0x180003194  mov     [rbx], ax
0x180003197  lea     rsi, [rsi+2]
0x18000319b  add     rbx, 2
0x18000319f  cmp     ecx, edx
0x1800031a1  jl      short loc_18000318F
0x1800031a3  mov     rcx, [rdi]
0x1800031a6  xor     eax, eax
0x1800031a8  movzx   edx, word ptr [rcx]
0x1800031ab  cmp     ax, dx
0x1800031ae  jnz     short loc_18000313D
0x1800031b0  mov     eax, 80020009h
0x1800031b5  add     rsp, 20h
0x1800031b9  pop     r14
0x1800031bb  pop     rdi
0x1800031bc  pop     rsi
0x1800031bd  pop     rbp
0x1800031be  pop     rbx
0x1800031bf  retn
0x1800031c0  mov     rcx, [rdi]
0x1800031c3  xor     eax, eax
0x1800031c5  cmp     ax, [rcx]
0x1800031c8  jz      short loc_1800031B0
0x1800031ca  cmp     rbx, rbp
0x1800031cd  jnb     short loc_1800031B0
0x1800031cf  mov     [rbx], ax
0x1800031d2  mov     rcx, [rdi]; lpsz
0x1800031d5  call    cs:__imp_CharNextW
0x1800031db  mov     [rdi], rax
0x1800031de  jmp     short loc_180003250
0x1800031e0  movzx   ecx, cx
0x1800031e3  sub     ecx, 9
0x1800031e6  jz      short loc_180003242
0x1800031e8  sub     ecx, 1
0x1800031eb  jz      short loc_180003242
0x1800031ed  sub     ecx, 3
0x1800031f0  jz      short loc_180003242
0x1800031f2  cmp     ecx, 13h
0x1800031f5  jz      short loc_180003242
0x1800031f7  mov     rcx, rsi; lpsz
0x1800031fa  call    cs:__imp_CharNextW
0x180003200  mov     rdx, rax
0x180003203  mov     [rdi], rax
0x180003206  sub     rdx, rsi
0x180003209  sar     rdx, 1
0x18000320c  lea     rcx, [rdx+1]
0x180003210  lea     rcx, [rbx+rcx*2]
0x180003214  cmp     rcx, rbp
0x180003217  jnb     short loc_1800031B0
0x180003219  xor     ecx, ecx
0x18000321b  test    edx, edx
0x18000321d  jle     short loc_180003233
0x18000321f  movzx   eax, word ptr [rsi]
0x180003222  inc     ecx
0x180003224  mov     [rbx], ax
0x180003227  lea     rsi, [rsi+2]
0x18000322b  add     rbx, 2
0x18000322f  cmp     ecx, edx
0x180003231  jl      short loc_18000321F
0x180003233  mov     rsi, [rdi]
0x180003236  xor     eax, eax
0x180003238  cmp     ax, [rsi]
0x18000323b  jz      short loc_180003242
0x18000323d  movzx   ecx, word ptr [rsi]
0x180003240  jmp     short loc_1800031E0
0x180003242  cmp     rbx, rbp
0x180003245  jnb     loc_1800031B0
0x18000324b  xor     eax, eax
0x18000324d  mov     [rbx], ax
0x180003250  xor     eax, eax
0x180003252  jmp     loc_1800031B5
```
