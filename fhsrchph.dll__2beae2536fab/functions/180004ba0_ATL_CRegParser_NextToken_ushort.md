# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180004ba0`
- end: `0x180004d37`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800037ac`
- `0x1800052f8`
- `0x18000566c`
- `0x180006074`

## callees

- `0x180004ba0`

## import_xrefs

- `USER32!CharNextW` at `0x180004bd5`
- `USER32!CharNextW` at `0x180004c03`
- `USER32!CharNextW` at `0x180004c23`
- `USER32!CharNextW` at `0x180004c3b`
- `USER32!CharNextW` at `0x180004c4a`
- `USER32!CharNextW` at `0x180004cb5`
- `USER32!CharNextW` at `0x180004cda`
- `USER32!CharNextW` at `0x180004bd5`
- `USER32!CharNextW` at `0x180004c03`
- `USER32!CharNextW` at `0x180004c23`
- `USER32!CharNextW` at `0x180004c3b`
- `USER32!CharNextW` at `0x180004c4a`
- `USER32!CharNextW` at `0x180004cb5`
- `USER32!CharNextW` at `0x180004cda`

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
0x180004ba0  push    rbx
0x180004ba2  push    rbp
0x180004ba3  push    rsi
0x180004ba4  push    rdi
0x180004ba5  push    r14
0x180004ba7  sub     rsp, 20h
0x180004bab  mov     rbx, rdx
0x180004bae  mov     rdi, rcx
0x180004bb1  mov     rsi, [rdi]
0x180004bb4  movzx   ecx, word ptr [rsi]
0x180004bb7  mov     r8d, ecx
0x180004bba  sub     r8d, 9
0x180004bbe  jz      short loc_180004BD2
0x180004bc0  sub     r8d, 1
0x180004bc4  jz      short loc_180004BD2
0x180004bc6  sub     r8d, 3
0x180004bca  jz      short loc_180004BD2
0x180004bcc  cmp     r8d, 13h
0x180004bd0  jnz     short loc_180004BE0
0x180004bd2  mov     rcx, rsi; lpsz
0x180004bd5  call    cs:__imp_CharNextW
0x180004bdb  mov     [rdi], rax
0x180004bde  jmp     short loc_180004BB1
0x180004be0  xor     eax, eax
0x180004be2  cmp     ax, cx
0x180004be5  jz      loc_180004C90
0x180004beb  lea     r14d, [rax+27h]
0x180004bef  lea     rbp, [rbx+2000h]
0x180004bf6  cmp     r14w, cx
0x180004bfa  jnz     loc_180004CC0
0x180004c00  mov     rcx, rsi; lpsz
0x180004c03  call    cs:__imp_CharNextW
0x180004c09  mov     [rdi], rax
0x180004c0c  mov     rcx, rax; lpsz
0x180004c0f  movzx   edx, word ptr [rax]
0x180004c12  xor     eax, eax
0x180004c14  cmp     ax, dx
0x180004c17  jz      loc_180004CA0
0x180004c1d  cmp     r14w, dx
0x180004c21  jnz     short loc_180004C2F
0x180004c23  call    cs:__imp_CharNextW
0x180004c29  cmp     r14w, [rax]
0x180004c2d  jnz     short loc_180004CA0
0x180004c2f  mov     rsi, [rdi]
0x180004c32  cmp     r14w, [rsi]
0x180004c36  jnz     short loc_180004C47
0x180004c38  mov     rcx, rsi; lpsz
0x180004c3b  call    cs:__imp_CharNextW
0x180004c41  mov     rsi, rax
0x180004c44  mov     [rdi], rax
0x180004c47  mov     rcx, rsi; lpsz
0x180004c4a  call    cs:__imp_CharNextW
0x180004c50  mov     rdx, rax
0x180004c53  mov     [rdi], rax
0x180004c56  sub     rdx, rsi
0x180004c59  sar     rdx, 1
0x180004c5c  lea     rcx, [rdx+1]
0x180004c60  lea     rcx, [rbx+rcx*2]
0x180004c64  cmp     rcx, rbp
0x180004c67  jnb     short loc_180004C90
0x180004c69  xor     ecx, ecx
0x180004c6b  test    edx, edx
0x180004c6d  jle     short loc_180004C83
0x180004c6f  movzx   eax, word ptr [rsi]
0x180004c72  inc     ecx
0x180004c74  mov     [rbx], ax
0x180004c77  lea     rsi, [rsi+2]
0x180004c7b  add     rbx, 2
0x180004c7f  cmp     ecx, edx
0x180004c81  jl      short loc_180004C6F
0x180004c83  mov     rcx, [rdi]
0x180004c86  xor     eax, eax
0x180004c88  movzx   edx, word ptr [rcx]
0x180004c8b  cmp     ax, dx
0x180004c8e  jnz     short loc_180004C1D
0x180004c90  mov     eax, 80020009h
0x180004c95  add     rsp, 20h
0x180004c99  pop     r14
0x180004c9b  pop     rdi
0x180004c9c  pop     rsi
0x180004c9d  pop     rbp
0x180004c9e  pop     rbx
0x180004c9f  retn
0x180004ca0  mov     rcx, [rdi]
0x180004ca3  xor     eax, eax
0x180004ca5  cmp     ax, [rcx]
0x180004ca8  jz      short loc_180004C90
0x180004caa  cmp     rbx, rbp
0x180004cad  jnb     short loc_180004C90
0x180004caf  mov     [rbx], ax
0x180004cb2  mov     rcx, [rdi]; lpsz
0x180004cb5  call    cs:__imp_CharNextW
0x180004cbb  mov     [rdi], rax
0x180004cbe  jmp     short loc_180004D30
0x180004cc0  movzx   ecx, cx
0x180004cc3  sub     ecx, 9
0x180004cc6  jz      short loc_180004D22
0x180004cc8  sub     ecx, 1
0x180004ccb  jz      short loc_180004D22
0x180004ccd  sub     ecx, 3
0x180004cd0  jz      short loc_180004D22
0x180004cd2  cmp     ecx, 13h
0x180004cd5  jz      short loc_180004D22
0x180004cd7  mov     rcx, rsi; lpsz
0x180004cda  call    cs:__imp_CharNextW
0x180004ce0  mov     rdx, rax
0x180004ce3  mov     [rdi], rax
0x180004ce6  sub     rdx, rsi
0x180004ce9  sar     rdx, 1
0x180004cec  lea     rcx, [rdx+1]
0x180004cf0  lea     rcx, [rbx+rcx*2]
0x180004cf4  cmp     rcx, rbp
0x180004cf7  jnb     short loc_180004C90
0x180004cf9  xor     ecx, ecx
0x180004cfb  test    edx, edx
0x180004cfd  jle     short loc_180004D13
0x180004cff  movzx   eax, word ptr [rsi]
0x180004d02  inc     ecx
0x180004d04  mov     [rbx], ax
0x180004d07  lea     rsi, [rsi+2]
0x180004d0b  add     rbx, 2
0x180004d0f  cmp     ecx, edx
0x180004d11  jl      short loc_180004CFF
0x180004d13  mov     rsi, [rdi]
0x180004d16  xor     eax, eax
0x180004d18  cmp     ax, [rsi]
0x180004d1b  jz      short loc_180004D22
0x180004d1d  movzx   ecx, word ptr [rsi]
0x180004d20  jmp     short loc_180004CC0
0x180004d22  cmp     rbx, rbp
0x180004d25  jnb     loc_180004C90
0x180004d2b  xor     eax, eax
0x180004d2d  mov     [rbx], ax
0x180004d30  xor     eax, eax
0x180004d32  jmp     loc_180004C95
```
