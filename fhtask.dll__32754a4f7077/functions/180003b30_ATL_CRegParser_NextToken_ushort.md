# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180003b30`
- end: `0x180003cc7`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000296c`
- `0x180004298`
- `0x18000460c`
- `0x180004f84`

## callees

- `0x180003b30`

## import_xrefs

- `USER32!CharNextW` at `0x180003b65`
- `USER32!CharNextW` at `0x180003b93`
- `USER32!CharNextW` at `0x180003bb3`
- `USER32!CharNextW` at `0x180003bcb`
- `USER32!CharNextW` at `0x180003bda`
- `USER32!CharNextW` at `0x180003c45`
- `USER32!CharNextW` at `0x180003c6a`
- `USER32!CharNextW` at `0x180003b65`
- `USER32!CharNextW` at `0x180003b93`
- `USER32!CharNextW` at `0x180003bb3`
- `USER32!CharNextW` at `0x180003bcb`
- `USER32!CharNextW` at `0x180003bda`
- `USER32!CharNextW` at `0x180003c45`
- `USER32!CharNextW` at `0x180003c6a`

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
0x180003b30  push    rbx
0x180003b32  push    rbp
0x180003b33  push    rsi
0x180003b34  push    rdi
0x180003b35  push    r14
0x180003b37  sub     rsp, 20h
0x180003b3b  mov     rbx, rdx
0x180003b3e  mov     rdi, rcx
0x180003b41  mov     rsi, [rdi]
0x180003b44  movzx   ecx, word ptr [rsi]
0x180003b47  mov     r8d, ecx
0x180003b4a  sub     r8d, 9
0x180003b4e  jz      short loc_180003B62
0x180003b50  sub     r8d, 1
0x180003b54  jz      short loc_180003B62
0x180003b56  sub     r8d, 3
0x180003b5a  jz      short loc_180003B62
0x180003b5c  cmp     r8d, 13h
0x180003b60  jnz     short loc_180003B70
0x180003b62  mov     rcx, rsi; lpsz
0x180003b65  call    cs:__imp_CharNextW
0x180003b6b  mov     [rdi], rax
0x180003b6e  jmp     short loc_180003B41
0x180003b70  xor     eax, eax
0x180003b72  cmp     ax, cx
0x180003b75  jz      loc_180003C20
0x180003b7b  lea     r14d, [rax+27h]
0x180003b7f  lea     rbp, [rbx+2000h]
0x180003b86  cmp     r14w, cx
0x180003b8a  jnz     loc_180003C50
0x180003b90  mov     rcx, rsi; lpsz
0x180003b93  call    cs:__imp_CharNextW
0x180003b99  mov     [rdi], rax
0x180003b9c  mov     rcx, rax; lpsz
0x180003b9f  movzx   edx, word ptr [rax]
0x180003ba2  xor     eax, eax
0x180003ba4  cmp     ax, dx
0x180003ba7  jz      loc_180003C30
0x180003bad  cmp     r14w, dx
0x180003bb1  jnz     short loc_180003BBF
0x180003bb3  call    cs:__imp_CharNextW
0x180003bb9  cmp     r14w, [rax]
0x180003bbd  jnz     short loc_180003C30
0x180003bbf  mov     rsi, [rdi]
0x180003bc2  cmp     r14w, [rsi]
0x180003bc6  jnz     short loc_180003BD7
0x180003bc8  mov     rcx, rsi; lpsz
0x180003bcb  call    cs:__imp_CharNextW
0x180003bd1  mov     rsi, rax
0x180003bd4  mov     [rdi], rax
0x180003bd7  mov     rcx, rsi; lpsz
0x180003bda  call    cs:__imp_CharNextW
0x180003be0  mov     rdx, rax
0x180003be3  mov     [rdi], rax
0x180003be6  sub     rdx, rsi
0x180003be9  sar     rdx, 1
0x180003bec  lea     rcx, [rdx+1]
0x180003bf0  lea     rcx, [rbx+rcx*2]
0x180003bf4  cmp     rcx, rbp
0x180003bf7  jnb     short loc_180003C20
0x180003bf9  xor     ecx, ecx
0x180003bfb  test    edx, edx
0x180003bfd  jle     short loc_180003C13
0x180003bff  movzx   eax, word ptr [rsi]
0x180003c02  inc     ecx
0x180003c04  mov     [rbx], ax
0x180003c07  lea     rsi, [rsi+2]
0x180003c0b  add     rbx, 2
0x180003c0f  cmp     ecx, edx
0x180003c11  jl      short loc_180003BFF
0x180003c13  mov     rcx, [rdi]
0x180003c16  xor     eax, eax
0x180003c18  movzx   edx, word ptr [rcx]
0x180003c1b  cmp     ax, dx
0x180003c1e  jnz     short loc_180003BAD
0x180003c20  mov     eax, 80020009h
0x180003c25  add     rsp, 20h
0x180003c29  pop     r14
0x180003c2b  pop     rdi
0x180003c2c  pop     rsi
0x180003c2d  pop     rbp
0x180003c2e  pop     rbx
0x180003c2f  retn
0x180003c30  mov     rcx, [rdi]
0x180003c33  xor     eax, eax
0x180003c35  cmp     ax, [rcx]
0x180003c38  jz      short loc_180003C20
0x180003c3a  cmp     rbx, rbp
0x180003c3d  jnb     short loc_180003C20
0x180003c3f  mov     [rbx], ax
0x180003c42  mov     rcx, [rdi]; lpsz
0x180003c45  call    cs:__imp_CharNextW
0x180003c4b  mov     [rdi], rax
0x180003c4e  jmp     short loc_180003CC0
0x180003c50  movzx   ecx, cx
0x180003c53  sub     ecx, 9
0x180003c56  jz      short loc_180003CB2
0x180003c58  sub     ecx, 1
0x180003c5b  jz      short loc_180003CB2
0x180003c5d  sub     ecx, 3
0x180003c60  jz      short loc_180003CB2
0x180003c62  cmp     ecx, 13h
0x180003c65  jz      short loc_180003CB2
0x180003c67  mov     rcx, rsi; lpsz
0x180003c6a  call    cs:__imp_CharNextW
0x180003c70  mov     rdx, rax
0x180003c73  mov     [rdi], rax
0x180003c76  sub     rdx, rsi
0x180003c79  sar     rdx, 1
0x180003c7c  lea     rcx, [rdx+1]
0x180003c80  lea     rcx, [rbx+rcx*2]
0x180003c84  cmp     rcx, rbp
0x180003c87  jnb     short loc_180003C20
0x180003c89  xor     ecx, ecx
0x180003c8b  test    edx, edx
0x180003c8d  jle     short loc_180003CA3
0x180003c8f  movzx   eax, word ptr [rsi]
0x180003c92  inc     ecx
0x180003c94  mov     [rbx], ax
0x180003c97  lea     rsi, [rsi+2]
0x180003c9b  add     rbx, 2
0x180003c9f  cmp     ecx, edx
0x180003ca1  jl      short loc_180003C8F
0x180003ca3  mov     rsi, [rdi]
0x180003ca6  xor     eax, eax
0x180003ca8  cmp     ax, [rsi]
0x180003cab  jz      short loc_180003CB2
0x180003cad  movzx   ecx, word ptr [rsi]
0x180003cb0  jmp     short loc_180003C50
0x180003cb2  cmp     rbx, rbp
0x180003cb5  jnb     loc_180003C20
0x180003cbb  xor     eax, eax
0x180003cbd  mov     [rbx], ax
0x180003cc0  xor     eax, eax
0x180003cc2  jmp     loc_180003C25
```
