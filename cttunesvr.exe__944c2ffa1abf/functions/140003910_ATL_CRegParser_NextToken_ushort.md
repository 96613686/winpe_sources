# ATL::CRegParser::NextToken(ushort *)

- ea: `0x140003910`
- end: `0x140003aa7`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400025a4`
- `0x140003f98`
- `0x1400042ec`
- `0x140004e78`

## callees

- `0x140003910`

## import_xrefs

- `USER32!CharNextW` at `0x140003945`
- `USER32!CharNextW` at `0x140003973`
- `USER32!CharNextW` at `0x140003993`
- `USER32!CharNextW` at `0x1400039ab`
- `USER32!CharNextW` at `0x1400039ba`
- `USER32!CharNextW` at `0x140003a25`
- `USER32!CharNextW` at `0x140003a4a`
- `USER32!CharNextW` at `0x140003945`
- `USER32!CharNextW` at `0x140003973`
- `USER32!CharNextW` at `0x140003993`
- `USER32!CharNextW` at `0x1400039ab`
- `USER32!CharNextW` at `0x1400039ba`
- `USER32!CharNextW` at `0x140003a25`
- `USER32!CharNextW` at `0x140003a4a`

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
0x140003910  push    rbx
0x140003912  push    rbp
0x140003913  push    rsi
0x140003914  push    rdi
0x140003915  push    r14
0x140003917  sub     rsp, 20h
0x14000391b  mov     rbx, rdx
0x14000391e  mov     rdi, rcx
0x140003921  mov     rsi, [rdi]
0x140003924  movzx   ecx, word ptr [rsi]
0x140003927  mov     r8d, ecx
0x14000392a  sub     r8d, 9
0x14000392e  jz      short loc_140003942
0x140003930  sub     r8d, 1
0x140003934  jz      short loc_140003942
0x140003936  sub     r8d, 3
0x14000393a  jz      short loc_140003942
0x14000393c  cmp     r8d, 13h
0x140003940  jnz     short loc_140003950
0x140003942  mov     rcx, rsi; lpsz
0x140003945  call    cs:__imp_CharNextW
0x14000394b  mov     [rdi], rax
0x14000394e  jmp     short loc_140003921
0x140003950  xor     eax, eax
0x140003952  cmp     ax, cx
0x140003955  jz      loc_140003A00
0x14000395b  lea     r14d, [rax+27h]
0x14000395f  lea     rbp, [rbx+2000h]
0x140003966  cmp     r14w, cx
0x14000396a  jnz     loc_140003A30
0x140003970  mov     rcx, rsi; lpsz
0x140003973  call    cs:__imp_CharNextW
0x140003979  mov     [rdi], rax
0x14000397c  mov     rcx, rax; lpsz
0x14000397f  movzx   edx, word ptr [rax]
0x140003982  xor     eax, eax
0x140003984  cmp     ax, dx
0x140003987  jz      loc_140003A10
0x14000398d  cmp     r14w, dx
0x140003991  jnz     short loc_14000399F
0x140003993  call    cs:__imp_CharNextW
0x140003999  cmp     r14w, [rax]
0x14000399d  jnz     short loc_140003A10
0x14000399f  mov     rsi, [rdi]
0x1400039a2  cmp     r14w, [rsi]
0x1400039a6  jnz     short loc_1400039B7
0x1400039a8  mov     rcx, rsi; lpsz
0x1400039ab  call    cs:__imp_CharNextW
0x1400039b1  mov     rsi, rax
0x1400039b4  mov     [rdi], rax
0x1400039b7  mov     rcx, rsi; lpsz
0x1400039ba  call    cs:__imp_CharNextW
0x1400039c0  mov     rdx, rax
0x1400039c3  mov     [rdi], rax
0x1400039c6  sub     rdx, rsi
0x1400039c9  sar     rdx, 1
0x1400039cc  lea     rcx, [rdx+1]
0x1400039d0  lea     rcx, [rbx+rcx*2]
0x1400039d4  cmp     rcx, rbp
0x1400039d7  jnb     short loc_140003A00
0x1400039d9  xor     ecx, ecx
0x1400039db  test    edx, edx
0x1400039dd  jle     short loc_1400039F3
0x1400039df  movzx   eax, word ptr [rsi]
0x1400039e2  inc     ecx
0x1400039e4  mov     [rbx], ax
0x1400039e7  lea     rsi, [rsi+2]
0x1400039eb  add     rbx, 2
0x1400039ef  cmp     ecx, edx
0x1400039f1  jl      short loc_1400039DF
0x1400039f3  mov     rcx, [rdi]
0x1400039f6  xor     eax, eax
0x1400039f8  movzx   edx, word ptr [rcx]
0x1400039fb  cmp     ax, dx
0x1400039fe  jnz     short loc_14000398D
0x140003a00  mov     eax, 80020009h
0x140003a05  add     rsp, 20h
0x140003a09  pop     r14
0x140003a0b  pop     rdi
0x140003a0c  pop     rsi
0x140003a0d  pop     rbp
0x140003a0e  pop     rbx
0x140003a0f  retn
0x140003a10  mov     rcx, [rdi]
0x140003a13  xor     eax, eax
0x140003a15  cmp     ax, [rcx]
0x140003a18  jz      short loc_140003A00
0x140003a1a  cmp     rbx, rbp
0x140003a1d  jnb     short loc_140003A00
0x140003a1f  mov     [rbx], ax
0x140003a22  mov     rcx, [rdi]; lpsz
0x140003a25  call    cs:__imp_CharNextW
0x140003a2b  mov     [rdi], rax
0x140003a2e  jmp     short loc_140003AA0
0x140003a30  movzx   ecx, cx
0x140003a33  sub     ecx, 9
0x140003a36  jz      short loc_140003A92
0x140003a38  sub     ecx, 1
0x140003a3b  jz      short loc_140003A92
0x140003a3d  sub     ecx, 3
0x140003a40  jz      short loc_140003A92
0x140003a42  cmp     ecx, 13h
0x140003a45  jz      short loc_140003A92
0x140003a47  mov     rcx, rsi; lpsz
0x140003a4a  call    cs:__imp_CharNextW
0x140003a50  mov     rdx, rax
0x140003a53  mov     [rdi], rax
0x140003a56  sub     rdx, rsi
0x140003a59  sar     rdx, 1
0x140003a5c  lea     rcx, [rdx+1]
0x140003a60  lea     rcx, [rbx+rcx*2]
0x140003a64  cmp     rcx, rbp
0x140003a67  jnb     short loc_140003A00
0x140003a69  xor     ecx, ecx
0x140003a6b  test    edx, edx
0x140003a6d  jle     short loc_140003A83
0x140003a6f  movzx   eax, word ptr [rsi]
0x140003a72  inc     ecx
0x140003a74  mov     [rbx], ax
0x140003a77  lea     rsi, [rsi+2]
0x140003a7b  add     rbx, 2
0x140003a7f  cmp     ecx, edx
0x140003a81  jl      short loc_140003A6F
0x140003a83  mov     rsi, [rdi]
0x140003a86  xor     eax, eax
0x140003a88  cmp     ax, [rsi]
0x140003a8b  jz      short loc_140003A92
0x140003a8d  movzx   ecx, word ptr [rsi]
0x140003a90  jmp     short loc_140003A30
0x140003a92  cmp     rbx, rbp
0x140003a95  jnb     loc_140003A00
0x140003a9b  xor     eax, eax
0x140003a9d  mov     [rbx], ax
0x140003aa0  xor     eax, eax
0x140003aa2  jmp     loc_140003A05
```
