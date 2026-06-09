# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180003b24`
- end: `0x180003cbb`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b3c`
- `0x180004118`
- `0x18000448c`
- `0x180004c3c`

## callees

- `0x180003b24`

## import_xrefs

- `USER32!CharNextW` at `0x180003b59`
- `USER32!CharNextW` at `0x180003b87`
- `USER32!CharNextW` at `0x180003ba7`
- `USER32!CharNextW` at `0x180003bbf`
- `USER32!CharNextW` at `0x180003bce`
- `USER32!CharNextW` at `0x180003c39`
- `USER32!CharNextW` at `0x180003c5e`
- `USER32!CharNextW` at `0x180003b59`
- `USER32!CharNextW` at `0x180003b87`
- `USER32!CharNextW` at `0x180003ba7`
- `USER32!CharNextW` at `0x180003bbf`
- `USER32!CharNextW` at `0x180003bce`
- `USER32!CharNextW` at `0x180003c39`
- `USER32!CharNextW` at `0x180003c5e`

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
0x180003b24  push    rbx
0x180003b26  push    rbp
0x180003b27  push    rsi
0x180003b28  push    rdi
0x180003b29  push    r14
0x180003b2b  sub     rsp, 20h
0x180003b2f  mov     rbx, rdx
0x180003b32  mov     rdi, rcx
0x180003b35  mov     rsi, [rdi]
0x180003b38  movzx   ecx, word ptr [rsi]
0x180003b3b  mov     r8d, ecx
0x180003b3e  sub     r8d, 9
0x180003b42  jz      short loc_180003B56
0x180003b44  sub     r8d, 1
0x180003b48  jz      short loc_180003B56
0x180003b4a  sub     r8d, 3
0x180003b4e  jz      short loc_180003B56
0x180003b50  cmp     r8d, 13h
0x180003b54  jnz     short loc_180003B64
0x180003b56  mov     rcx, rsi; lpsz
0x180003b59  call    cs:__imp_CharNextW
0x180003b5f  mov     [rdi], rax
0x180003b62  jmp     short loc_180003B35
0x180003b64  xor     eax, eax
0x180003b66  cmp     ax, cx
0x180003b69  jz      loc_180003C14
0x180003b6f  lea     r14d, [rax+27h]
0x180003b73  lea     rbp, [rbx+2000h]
0x180003b7a  cmp     r14w, cx
0x180003b7e  jnz     loc_180003C44
0x180003b84  mov     rcx, rsi; lpsz
0x180003b87  call    cs:__imp_CharNextW
0x180003b8d  mov     [rdi], rax
0x180003b90  mov     rcx, rax; lpsz
0x180003b93  movzx   edx, word ptr [rax]
0x180003b96  xor     eax, eax
0x180003b98  cmp     ax, dx
0x180003b9b  jz      loc_180003C24
0x180003ba1  cmp     r14w, dx
0x180003ba5  jnz     short loc_180003BB3
0x180003ba7  call    cs:__imp_CharNextW
0x180003bad  cmp     r14w, [rax]
0x180003bb1  jnz     short loc_180003C24
0x180003bb3  mov     rsi, [rdi]
0x180003bb6  cmp     r14w, [rsi]
0x180003bba  jnz     short loc_180003BCB
0x180003bbc  mov     rcx, rsi; lpsz
0x180003bbf  call    cs:__imp_CharNextW
0x180003bc5  mov     rsi, rax
0x180003bc8  mov     [rdi], rax
0x180003bcb  mov     rcx, rsi; lpsz
0x180003bce  call    cs:__imp_CharNextW
0x180003bd4  mov     rdx, rax
0x180003bd7  mov     [rdi], rax
0x180003bda  sub     rdx, rsi
0x180003bdd  sar     rdx, 1
0x180003be0  lea     rcx, [rdx+1]
0x180003be4  lea     rcx, [rbx+rcx*2]
0x180003be8  cmp     rcx, rbp
0x180003beb  jnb     short loc_180003C14
0x180003bed  xor     ecx, ecx
0x180003bef  test    edx, edx
0x180003bf1  jle     short loc_180003C07
0x180003bf3  movzx   eax, word ptr [rsi]
0x180003bf6  inc     ecx
0x180003bf8  mov     [rbx], ax
0x180003bfb  lea     rsi, [rsi+2]
0x180003bff  add     rbx, 2
0x180003c03  cmp     ecx, edx
0x180003c05  jl      short loc_180003BF3
0x180003c07  mov     rcx, [rdi]
0x180003c0a  xor     eax, eax
0x180003c0c  movzx   edx, word ptr [rcx]
0x180003c0f  cmp     ax, dx
0x180003c12  jnz     short loc_180003BA1
0x180003c14  mov     eax, 80020009h
0x180003c19  add     rsp, 20h
0x180003c1d  pop     r14
0x180003c1f  pop     rdi
0x180003c20  pop     rsi
0x180003c21  pop     rbp
0x180003c22  pop     rbx
0x180003c23  retn
0x180003c24  mov     rcx, [rdi]
0x180003c27  xor     eax, eax
0x180003c29  cmp     ax, [rcx]
0x180003c2c  jz      short loc_180003C14
0x180003c2e  cmp     rbx, rbp
0x180003c31  jnb     short loc_180003C14
0x180003c33  mov     [rbx], ax
0x180003c36  mov     rcx, [rdi]; lpsz
0x180003c39  call    cs:__imp_CharNextW
0x180003c3f  mov     [rdi], rax
0x180003c42  jmp     short loc_180003CB4
0x180003c44  movzx   ecx, cx
0x180003c47  sub     ecx, 9
0x180003c4a  jz      short loc_180003CA6
0x180003c4c  sub     ecx, 1
0x180003c4f  jz      short loc_180003CA6
0x180003c51  sub     ecx, 3
0x180003c54  jz      short loc_180003CA6
0x180003c56  cmp     ecx, 13h
0x180003c59  jz      short loc_180003CA6
0x180003c5b  mov     rcx, rsi; lpsz
0x180003c5e  call    cs:__imp_CharNextW
0x180003c64  mov     rdx, rax
0x180003c67  mov     [rdi], rax
0x180003c6a  sub     rdx, rsi
0x180003c6d  sar     rdx, 1
0x180003c70  lea     rcx, [rdx+1]
0x180003c74  lea     rcx, [rbx+rcx*2]
0x180003c78  cmp     rcx, rbp
0x180003c7b  jnb     short loc_180003C14
0x180003c7d  xor     ecx, ecx
0x180003c7f  test    edx, edx
0x180003c81  jle     short loc_180003C97
0x180003c83  movzx   eax, word ptr [rsi]
0x180003c86  inc     ecx
0x180003c88  mov     [rbx], ax
0x180003c8b  lea     rsi, [rsi+2]
0x180003c8f  add     rbx, 2
0x180003c93  cmp     ecx, edx
0x180003c95  jl      short loc_180003C83
0x180003c97  mov     rsi, [rdi]
0x180003c9a  xor     eax, eax
0x180003c9c  cmp     ax, [rsi]
0x180003c9f  jz      short loc_180003CA6
0x180003ca1  movzx   ecx, word ptr [rsi]
0x180003ca4  jmp     short loc_180003C44
0x180003ca6  cmp     rbx, rbp
0x180003ca9  jnb     loc_180003C14
0x180003caf  xor     eax, eax
0x180003cb1  mov     [rbx], ax
0x180003cb4  xor     eax, eax
0x180003cb6  jmp     loc_180003C19
```
