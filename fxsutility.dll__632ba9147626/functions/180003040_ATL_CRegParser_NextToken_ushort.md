# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180003040`
- end: `0x1800031c8`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `392`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002274`
- `0x1800035fc`
- `0x1800039f4`
- `0x18000445c`

## callees

- `0x180003040`

## import_xrefs

- `USER32!CharNextW` at `0x180003075`
- `USER32!CharNextW` at `0x18000309b`
- `USER32!CharNextW` at `0x1800030b5`
- `USER32!CharNextW` at `0x1800030cd`
- `USER32!CharNextW` at `0x1800030dc`
- `USER32!CharNextW` at `0x180003142`
- `USER32!CharNextW` at `0x180003167`
- `USER32!CharNextW` at `0x180003075`
- `USER32!CharNextW` at `0x18000309b`
- `USER32!CharNextW` at `0x1800030b5`
- `USER32!CharNextW` at `0x1800030cd`
- `USER32!CharNextW` at `0x1800030dc`
- `USER32!CharNextW` at `0x180003142`
- `USER32!CharNextW` at `0x180003167`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCWSTR *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rbx
  WCHAR v5; // cx
  unsigned __int16 *v6; // rbp
  LPWSTR v7; // rax
  LPWSTR v8; // rdx
  WCHAR i; // cx
  const WCHAR *v10; // rbx
  unsigned __int16 v12; // ax
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  LPWSTR v16; // rax
  const WCHAR *v17; // rcx
  unsigned __int16 v18; // ax

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
  v6 = a2;
  if ( v5 != 39 )
  {
    while ( 1 )
    {
      v13 = v5 - 9;
      if ( !v13 )
        break;
      v14 = v13 - 1;
      if ( !v14 )
        break;
      v15 = v14 - 3;
      if ( !v15 || v15 == 19 )
        break;
      v16 = CharNextW(v4);
      *this = v16;
      if ( &a2[v16 - v4] >= v6 + 4096 )
        return 2147614729LL;
      v17 = v4;
      if ( v4 >= v16 )
      {
        v4 = v16;
      }
      else
      {
        do
        {
          v18 = *v17++;
          *a2++ = v18;
          v4 = *this;
        }
        while ( v17 < *this );
      }
      if ( !*v4 )
        break;
      v5 = *v4;
    }
    *a2 = 0;
    return 0;
  }
  v7 = CharNextW(*this);
  *this = v7;
  v8 = v7;
  for ( i = *v7; i && (i != 39 || *CharNextW(v8) == 39); i = *v8 )
  {
    v10 = *this;
    if ( **this == 39 )
    {
      v10 = CharNextW(*this);
      *this = v10;
    }
    v8 = CharNextW(v10);
    *this = v8;
    if ( &a2[v8 - v10] >= v6 + 4096 )
      return 2147614729LL;
    while ( v10 < v8 )
    {
      v12 = *v10++;
      *a2++ = v12;
      v8 = (LPWSTR)*this;
    }
  }
  if ( !**this )
    return 2147614729LL;
  *a2 = 0;
  *this = CharNextW(*this);
  return 0;
}

```

## disassembly

```asm
0x180003040  push    rbx
0x180003042  push    rbp
0x180003043  push    rsi
0x180003044  push    rdi
0x180003045  push    r14
0x180003047  sub     rsp, 20h
0x18000304b  mov     rsi, rdx
0x18000304e  mov     rdi, rcx
0x180003051  mov     rbx, [rdi]
0x180003054  movzx   ecx, word ptr [rbx]
0x180003057  mov     r8d, ecx
0x18000305a  sub     r8d, 9
0x18000305e  jz      short loc_180003072
0x180003060  sub     r8d, 1
0x180003064  jz      short loc_180003072
0x180003066  sub     r8d, 3
0x18000306a  jz      short loc_180003072
0x18000306c  cmp     r8d, 13h
0x180003070  jnz     short loc_180003080
0x180003072  mov     rcx, rbx; lpsz
0x180003075  call    cs:__imp_CharNextW
0x18000307b  mov     [rdi], rax
0x18000307e  jmp     short loc_180003051
0x180003080  xor     eax, eax
0x180003082  cmp     ax, cx
0x180003085  jz      short loc_1800030FE
0x180003087  lea     r14d, [rax+27h]
0x18000308b  mov     rbp, rsi
0x18000308e  cmp     r14w, cx
0x180003092  jnz     loc_18000314D
0x180003098  mov     rcx, rbx; lpsz
0x18000309b  call    cs:__imp_CharNextW
0x1800030a1  mov     [rdi], rax
0x1800030a4  mov     rdx, rax
0x1800030a7  movzx   ecx, word ptr [rax]
0x1800030aa  jmp     short loc_180003127
0x1800030ac  cmp     r14w, cx
0x1800030b0  jnz     short loc_1800030C1
0x1800030b2  mov     rcx, rdx; lpsz
0x1800030b5  call    cs:__imp_CharNextW
0x1800030bb  cmp     r14w, [rax]
0x1800030bf  jnz     short loc_180003132
0x1800030c1  mov     rbx, [rdi]
0x1800030c4  cmp     r14w, [rbx]
0x1800030c8  jnz     short loc_1800030D9
0x1800030ca  mov     rcx, rbx; lpsz
0x1800030cd  call    cs:__imp_CharNextW
0x1800030d3  mov     rbx, rax
0x1800030d6  mov     [rdi], rax
0x1800030d9  mov     rcx, rbx; lpsz
0x1800030dc  call    cs:__imp_CharNextW
0x1800030e2  mov     rdx, rax
0x1800030e5  mov     [rdi], rax
0x1800030e8  sub     rax, rbx
0x1800030eb  sar     rax, 1
0x1800030ee  lea     rcx, [rsi+rax*2]
0x1800030f2  lea     rax, [rbp+2000h]
0x1800030f9  cmp     rcx, rax
0x1800030fc  jb      short loc_18000311F
0x1800030fe  mov     eax, 80020009h
0x180003103  add     rsp, 20h
0x180003107  pop     r14
0x180003109  pop     rdi
0x18000310a  pop     rsi
0x18000310b  pop     rbp
0x18000310c  pop     rbx
0x18000310d  retn
0x18000310e  movzx   eax, word ptr [rbx]
0x180003111  add     rbx, 2
0x180003115  mov     [rsi], ax
0x180003118  add     rsi, 2
0x18000311c  mov     rdx, [rdi]
0x18000311f  cmp     rbx, rdx
0x180003122  jb      short loc_18000310E
0x180003124  movzx   ecx, word ptr [rdx]
0x180003127  xor     eax, eax
0x180003129  cmp     ax, cx
0x18000312c  jnz     loc_1800030AC
0x180003132  mov     rcx, [rdi]
0x180003135  xor     eax, eax
0x180003137  cmp     ax, [rcx]
0x18000313a  jz      short loc_1800030FE
0x18000313c  mov     [rsi], ax
0x18000313f  mov     rcx, [rdi]; lpsz
0x180003142  call    cs:__imp_CharNextW
0x180003148  mov     [rdi], rax
0x18000314b  jmp     short loc_1800031C1
0x18000314d  movzx   ecx, cx
0x180003150  sub     ecx, 9
0x180003153  jz      short loc_1800031BC
0x180003155  sub     ecx, 1
0x180003158  jz      short loc_1800031BC
0x18000315a  sub     ecx, 3
0x18000315d  jz      short loc_1800031BC
0x18000315f  cmp     ecx, 13h
0x180003162  jz      short loc_1800031BC
0x180003164  mov     rcx, rbx; lpsz
0x180003167  call    cs:__imp_CharNextW
0x18000316d  mov     rcx, rax
0x180003170  mov     [rdi], rax
0x180003173  sub     rcx, rbx
0x180003176  sar     rcx, 1
0x180003179  lea     rdx, [rsi+rcx*2]
0x18000317d  lea     rcx, [rbp+2000h]
0x180003184  cmp     rdx, rcx
0x180003187  jnb     loc_1800030FE
0x18000318d  mov     rcx, rbx
0x180003190  cmp     rbx, rax
0x180003193  jnb     short loc_1800031AD
0x180003195  movzx   eax, word ptr [rcx]
0x180003198  add     rcx, 2
0x18000319c  mov     [rsi], ax
0x18000319f  add     rsi, 2
0x1800031a3  mov     rbx, [rdi]
0x1800031a6  cmp     rcx, rbx
0x1800031a9  jb      short loc_180003195
0x1800031ab  jmp     short loc_1800031B0
0x1800031ad  mov     rbx, rax
0x1800031b0  xor     eax, eax
0x1800031b2  cmp     ax, [rbx]
0x1800031b5  jz      short loc_1800031BC
0x1800031b7  movzx   ecx, word ptr [rbx]
0x1800031ba  jmp     short loc_18000314D
0x1800031bc  xor     eax, eax
0x1800031be  mov     [rsi], ax
0x1800031c1  xor     eax, eax
0x1800031c3  jmp     loc_180003103
```
