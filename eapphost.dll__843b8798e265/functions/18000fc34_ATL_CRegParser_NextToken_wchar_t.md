# ATL::CRegParser::NextToken(wchar_t *)

- ea: `0x18000fc34`
- end: `0x18000fdbb`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z`
- size: `391`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ee98`
- `0x18001024c`
- `0x1800105a0`
- `0x180010c0c`

## callees

- `0x18000fc34`
- `0x180010ca0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fc6d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fc90`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fcae`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fcc3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fd28`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fd5d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fc6d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fc90`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fcae`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fcc3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fd28`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fd5d`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, wchar_t *a2)
{
  const WCHAR *v4; // rcx
  wchar_t *v5; // rbp
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rsi
  LPWSTR v8; // rax
  __int64 v9; // rdx
  int i; // ecx
  wchar_t *v11; // rsi
  LPWSTR v12; // rax
  __int64 v13; // rdx
  int j; // ecx

  ATL::CRegParser::SkipWhiteSpace(this);
  v4 = *(const WCHAR **)this;
  if ( **(_WORD **)this )
  {
    v5 = a2 + 4096;
    if ( *v4 == 39 )
    {
      *(_QWORD *)this = CharNextW(v4);
      while ( 1 )
      {
        v6 = *(const WCHAR **)this;
        if ( !**(_WORD **)this || *v6 == 39 && *CharNextW(v6) != 39 )
          break;
        v7 = *(const WCHAR **)this;
        if ( **(_WORD **)this == 39 )
        {
          v7 = CharNextW(*(LPCWSTR *)this);
          *(_QWORD *)this = v7;
        }
        v8 = CharNextW(v7);
        *(_QWORD *)this = v8;
        v9 = v8 - v7;
        if ( &a2[v9 + 1] >= v5 )
          return 2147614729LL;
        for ( i = 0; i < (int)v9; ++a2 )
        {
          ++i;
          *a2 = *v7++;
        }
      }
      if ( **(_WORD **)this && a2 < v5 )
      {
        *a2 = 0;
        *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
        return 0;
      }
    }
    else
    {
      while ( 1 )
      {
        v11 = *(wchar_t **)this;
        if ( !**(_WORD **)this || *v11 == 9 || *v11 == 10 || *v11 == 13 || *v11 == 32 )
          break;
        v12 = CharNextW(*(LPCWSTR *)this);
        *(_QWORD *)this = v12;
        v13 = v12 - v11;
        if ( &a2[v13 + 1] >= v5 )
          return 2147614729LL;
        for ( j = 0; j < (int)v13; ++a2 )
        {
          ++j;
          *a2 = *v11++;
        }
      }
      if ( a2 < v5 )
      {
        *a2 = 0;
        return 0;
      }
    }
  }
  return 2147614729LL;
}

```

## disassembly

```asm
0x18000fc34  push    rbx
0x18000fc36  push    rbp
0x18000fc37  push    rsi
0x18000fc38  push    rdi
0x18000fc39  push    r14
0x18000fc3b  sub     rsp, 20h
0x18000fc3f  mov     rbx, rdx
0x18000fc42  mov     rdi, rcx
0x18000fc45  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000fc4a  mov     rcx, [rdi]; lpsz
0x18000fc4d  xor     eax, eax
0x18000fc4f  cmp     ax, [rcx]
0x18000fc52  jz      loc_18000FDAA
0x18000fc58  lea     r14d, [rax+27h]
0x18000fc5c  lea     rbp, [rbx+2000h]
0x18000fc63  cmp     r14w, [rcx]
0x18000fc67  jnz     loc_18000FD39
0x18000fc6d  call    cs:__imp_CharNextW
0x18000fc74  nop     dword ptr [rax+rax+00h]
0x18000fc79  mov     [rdi], rax
0x18000fc7c  mov     rcx, [rdi]; lpsz
0x18000fc7f  xor     eax, eax
0x18000fc81  cmp     ax, [rcx]
0x18000fc84  jz      loc_18000FD0B
0x18000fc8a  cmp     r14w, [rcx]
0x18000fc8e  jnz     short loc_18000FCA2
0x18000fc90  call    cs:__imp_CharNextW
0x18000fc97  nop     dword ptr [rax+rax+00h]
0x18000fc9c  cmp     r14w, [rax]
0x18000fca0  jnz     short loc_18000FD0B
0x18000fca2  mov     rsi, [rdi]
0x18000fca5  cmp     r14w, [rsi]
0x18000fca9  jnz     short loc_18000FCC0
0x18000fcab  mov     rcx, rsi; lpsz
0x18000fcae  call    cs:__imp_CharNextW
0x18000fcb5  nop     dword ptr [rax+rax+00h]
0x18000fcba  mov     rsi, rax
0x18000fcbd  mov     [rdi], rax
0x18000fcc0  mov     rcx, rsi; lpsz
0x18000fcc3  call    cs:__imp_CharNextW
0x18000fcca  nop     dword ptr [rax+rax+00h]
0x18000fccf  mov     rdx, rax
0x18000fcd2  mov     [rdi], rax
0x18000fcd5  sub     rdx, rsi
0x18000fcd8  sar     rdx, 1
0x18000fcdb  lea     rcx, [rdx+1]
0x18000fcdf  lea     rcx, [rbx+rcx*2]
0x18000fce3  cmp     rcx, rbp
0x18000fce6  jnb     loc_18000FDAA
0x18000fcec  xor     ecx, ecx
0x18000fcee  test    edx, edx
0x18000fcf0  jle     short loc_18000FC7C
0x18000fcf2  movzx   eax, word ptr [rsi]
0x18000fcf5  inc     ecx
0x18000fcf7  mov     [rbx], ax
0x18000fcfa  lea     rsi, [rsi+2]
0x18000fcfe  add     rbx, 2
0x18000fd02  cmp     ecx, edx
0x18000fd04  jl      short loc_18000FCF2
0x18000fd06  jmp     loc_18000FC7C
0x18000fd0b  mov     rcx, [rdi]
0x18000fd0e  xor     eax, eax
0x18000fd10  cmp     ax, [rcx]
0x18000fd13  jz      loc_18000FDAA
0x18000fd19  cmp     rbx, rbp
0x18000fd1c  jnb     loc_18000FDAA
0x18000fd22  mov     [rbx], ax
0x18000fd25  mov     rcx, [rdi]; lpsz
0x18000fd28  call    cs:__imp_CharNextW
0x18000fd2f  nop     dword ptr [rax+rax+00h]
0x18000fd34  mov     [rdi], rax
0x18000fd37  jmp     short loc_18000FDA6
0x18000fd39  mov     rsi, [rdi]
0x18000fd3c  xor     eax, eax
0x18000fd3e  cmp     ax, [rsi]
0x18000fd41  jz      short loc_18000FD9E
0x18000fd43  movzx   ecx, word ptr [rsi]
0x18000fd46  sub     ecx, 9
0x18000fd49  jz      short loc_18000FD9E
0x18000fd4b  sub     ecx, 1
0x18000fd4e  jz      short loc_18000FD9E
0x18000fd50  sub     ecx, 3
0x18000fd53  jz      short loc_18000FD9E
0x18000fd55  cmp     ecx, 13h
0x18000fd58  jz      short loc_18000FD9E
0x18000fd5a  mov     rcx, rsi; lpsz
0x18000fd5d  call    cs:__imp_CharNextW
0x18000fd64  nop     dword ptr [rax+rax+00h]
0x18000fd69  mov     rdx, rax
0x18000fd6c  mov     [rdi], rax
0x18000fd6f  sub     rdx, rsi
0x18000fd72  sar     rdx, 1
0x18000fd75  lea     rcx, [rdx+1]
0x18000fd79  lea     rcx, [rbx+rcx*2]
0x18000fd7d  cmp     rcx, rbp
0x18000fd80  jnb     short loc_18000FDAA
0x18000fd82  xor     ecx, ecx
0x18000fd84  test    edx, edx
0x18000fd86  jle     short loc_18000FD39
0x18000fd88  movzx   eax, word ptr [rsi]
0x18000fd8b  inc     ecx
0x18000fd8d  mov     [rbx], ax
0x18000fd90  lea     rsi, [rsi+2]
0x18000fd94  add     rbx, 2
0x18000fd98  cmp     ecx, edx
0x18000fd9a  jl      short loc_18000FD88
0x18000fd9c  jmp     short loc_18000FD39
0x18000fd9e  cmp     rbx, rbp
0x18000fda1  jnb     short loc_18000FDAA
0x18000fda3  mov     [rbx], ax
0x18000fda6  xor     eax, eax
0x18000fda8  jmp     short loc_18000FDAF
0x18000fdaa  mov     eax, 80020009h
0x18000fdaf  add     rsp, 20h
0x18000fdb3  pop     r14
0x18000fdb5  pop     rdi
0x18000fdb6  pop     rsi
0x18000fdb7  pop     rbp
0x18000fdb8  pop     rbx
0x18000fdb9  retn
```
