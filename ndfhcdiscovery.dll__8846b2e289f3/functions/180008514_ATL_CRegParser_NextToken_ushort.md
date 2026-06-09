# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180008514`
- end: `0x1800086de`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `458`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000615c`
- `0x180008d5c`
- `0x180009108`
- `0x180009ba0`

## callees

- `0x180008514`

## import_xrefs

- `USER32!CharNextW` at `0x180008549`
- `USER32!CharNextW` at `0x18000857d`
- `USER32!CharNextW` at `0x1800085a3`
- `USER32!CharNextW` at `0x1800085c5`
- `USER32!CharNextW` at `0x1800085da`
- `USER32!CharNextW` at `0x180008650`
- `USER32!CharNextW` at `0x18000867b`
- `USER32!CharNextW` at `0x180008549`
- `USER32!CharNextW` at `0x18000857d`
- `USER32!CharNextW` at `0x1800085a3`
- `USER32!CharNextW` at `0x1800085c5`
- `USER32!CharNextW` at `0x1800085da`
- `USER32!CharNextW` at `0x180008650`
- `USER32!CharNextW` at `0x18000867b`

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
0x180008514  push    rbx
0x180008516  push    rbp
0x180008517  push    rsi
0x180008518  push    rdi
0x180008519  push    r14
0x18000851b  sub     rsp, 20h
0x18000851f  mov     rbx, rdx
0x180008522  mov     rdi, rcx
0x180008525  mov     rsi, [rdi]
0x180008528  movzx   ecx, word ptr [rsi]
0x18000852b  mov     r8d, ecx
0x18000852e  sub     r8d, 9
0x180008532  jz      short loc_180008546
0x180008534  sub     r8d, 1
0x180008538  jz      short loc_180008546
0x18000853a  sub     r8d, 3
0x18000853e  jz      short loc_180008546
0x180008540  cmp     r8d, 13h
0x180008544  jnz     short loc_18000855A
0x180008546  mov     rcx, rsi; lpsz
0x180008549  call    cs:__imp_CharNextW
0x180008550  nop     dword ptr [rax+rax+00h]
0x180008555  mov     [rdi], rax
0x180008558  jmp     short loc_180008525
0x18000855a  xor     eax, eax
0x18000855c  cmp     ax, cx
0x18000855f  jz      loc_18000862A
0x180008565  lea     r14d, [rax+27h]
0x180008569  lea     rbp, [rbx+2000h]
0x180008570  cmp     r14w, cx
0x180008574  jnz     loc_180008661
0x18000857a  mov     rcx, rsi; lpsz
0x18000857d  call    cs:__imp_CharNextW
0x180008584  nop     dword ptr [rax+rax+00h]
0x180008589  mov     [rdi], rax
0x18000858c  mov     rcx, rax; lpsz
0x18000858f  movzx   edx, word ptr [rax]
0x180008592  xor     eax, eax
0x180008594  cmp     ax, dx
0x180008597  jz      loc_18000863B
0x18000859d  cmp     r14w, dx
0x1800085a1  jnz     short loc_1800085B9
0x1800085a3  call    cs:__imp_CharNextW
0x1800085aa  nop     dword ptr [rax+rax+00h]
0x1800085af  cmp     r14w, [rax]
0x1800085b3  jnz     loc_18000863B
0x1800085b9  mov     rsi, [rdi]
0x1800085bc  cmp     r14w, [rsi]
0x1800085c0  jnz     short loc_1800085D7
0x1800085c2  mov     rcx, rsi; lpsz
0x1800085c5  call    cs:__imp_CharNextW
0x1800085cc  nop     dword ptr [rax+rax+00h]
0x1800085d1  mov     rsi, rax
0x1800085d4  mov     [rdi], rax
0x1800085d7  mov     rcx, rsi; lpsz
0x1800085da  call    cs:__imp_CharNextW
0x1800085e1  nop     dword ptr [rax+rax+00h]
0x1800085e6  mov     rdx, rax
0x1800085e9  mov     [rdi], rax
0x1800085ec  sub     rdx, rsi
0x1800085ef  sar     rdx, 1
0x1800085f2  lea     rcx, [rdx+1]
0x1800085f6  lea     rcx, [rbx+rcx*2]
0x1800085fa  cmp     rcx, rbp
0x1800085fd  jnb     short loc_18000862A
0x1800085ff  xor     ecx, ecx
0x180008601  test    edx, edx
0x180008603  jle     short loc_180008619
0x180008605  movzx   eax, word ptr [rsi]
0x180008608  inc     ecx
0x18000860a  mov     [rbx], ax
0x18000860d  lea     rsi, [rsi+2]
0x180008611  add     rbx, 2
0x180008615  cmp     ecx, edx
0x180008617  jl      short loc_180008605
0x180008619  mov     rcx, [rdi]
0x18000861c  xor     eax, eax
0x18000861e  movzx   edx, word ptr [rcx]
0x180008621  cmp     ax, dx
0x180008624  jnz     loc_18000859D
0x18000862a  mov     eax, 80020009h
0x18000862f  add     rsp, 20h
0x180008633  pop     r14
0x180008635  pop     rdi
0x180008636  pop     rsi
0x180008637  pop     rbp
0x180008638  pop     rbx
0x180008639  retn
0x18000863b  mov     rcx, [rdi]
0x18000863e  xor     eax, eax
0x180008640  cmp     ax, [rcx]
0x180008643  jz      short loc_18000862A
0x180008645  cmp     rbx, rbp
0x180008648  jnb     short loc_18000862A
0x18000864a  mov     [rbx], ax
0x18000864d  mov     rcx, [rdi]; lpsz
0x180008650  call    cs:__imp_CharNextW
0x180008657  nop     dword ptr [rax+rax+00h]
0x18000865c  mov     [rdi], rax
0x18000865f  jmp     short loc_1800086D7
0x180008661  movzx   ecx, cx
0x180008664  sub     ecx, 9
0x180008667  jz      short loc_1800086C9
0x180008669  sub     ecx, 1
0x18000866c  jz      short loc_1800086C9
0x18000866e  sub     ecx, 3
0x180008671  jz      short loc_1800086C9
0x180008673  cmp     ecx, 13h
0x180008676  jz      short loc_1800086C9
0x180008678  mov     rcx, rsi; lpsz
0x18000867b  call    cs:__imp_CharNextW
0x180008682  nop     dword ptr [rax+rax+00h]
0x180008687  mov     rdx, rax
0x18000868a  mov     [rdi], rax
0x18000868d  sub     rdx, rsi
0x180008690  sar     rdx, 1
0x180008693  lea     rcx, [rdx+1]
0x180008697  lea     rcx, [rbx+rcx*2]
0x18000869b  cmp     rcx, rbp
0x18000869e  jnb     short loc_18000862A
0x1800086a0  xor     ecx, ecx
0x1800086a2  test    edx, edx
0x1800086a4  jle     short loc_1800086BA
0x1800086a6  movzx   eax, word ptr [rsi]
0x1800086a9  inc     ecx
0x1800086ab  mov     [rbx], ax
0x1800086ae  lea     rsi, [rsi+2]
0x1800086b2  add     rbx, 2
0x1800086b6  cmp     ecx, edx
0x1800086b8  jl      short loc_1800086A6
0x1800086ba  mov     rsi, [rdi]
0x1800086bd  xor     eax, eax
0x1800086bf  cmp     ax, [rsi]
0x1800086c2  jz      short loc_1800086C9
0x1800086c4  movzx   ecx, word ptr [rsi]
0x1800086c7  jmp     short loc_180008661
0x1800086c9  cmp     rbx, rbp
0x1800086cc  jnb     loc_18000862A
0x1800086d2  xor     eax, eax
0x1800086d4  mov     [rbx], ax
0x1800086d7  xor     eax, eax
0x1800086d9  jmp     loc_18000862F
```
