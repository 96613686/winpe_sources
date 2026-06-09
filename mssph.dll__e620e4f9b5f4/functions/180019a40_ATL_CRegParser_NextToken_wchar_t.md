# ATL::CRegParser::NextToken(wchar_t *)

- ea: `0x180019a40`
- end: `0x180019b97`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180016dfc`
- `0x18001a418`
- `0x18001a7d4`
- `0x18001b8cc`

## callees

- `0x180019a40`
- `0x18001b960`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019a79`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019a92`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019aaa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019ab9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019b11`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019b40`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019a79`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019a92`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019aaa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019ab9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019b11`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019b40`

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
0x180019a40  push    rbx
0x180019a42  push    rbp
0x180019a43  push    rsi
0x180019a44  push    rdi
0x180019a45  push    r14
0x180019a47  sub     rsp, 20h
0x180019a4b  mov     rbx, rdx
0x180019a4e  mov     rdi, rcx
0x180019a51  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180019a56  mov     rcx, [rdi]; lpsz
0x180019a59  xor     eax, eax
0x180019a5b  cmp     ax, [rcx]
0x180019a5e  jz      loc_180019B87
0x180019a64  lea     r14d, [rax+27h]
0x180019a68  lea     rbp, [rbx+2000h]
0x180019a6f  cmp     r14w, [rcx]
0x180019a73  jnz     loc_180019B1C
0x180019a79  call    cs:__imp_CharNextW
0x180019a7f  mov     [rdi], rax
0x180019a82  mov     rcx, [rdi]; lpsz
0x180019a85  xor     eax, eax
0x180019a87  cmp     ax, [rcx]
0x180019a8a  jz      short loc_180019AF8
0x180019a8c  cmp     r14w, [rcx]
0x180019a90  jnz     short loc_180019A9E
0x180019a92  call    cs:__imp_CharNextW
0x180019a98  cmp     r14w, [rax]
0x180019a9c  jnz     short loc_180019AF8
0x180019a9e  mov     rsi, [rdi]
0x180019aa1  cmp     r14w, [rsi]
0x180019aa5  jnz     short loc_180019AB6
0x180019aa7  mov     rcx, rsi; lpsz
0x180019aaa  call    cs:__imp_CharNextW
0x180019ab0  mov     rsi, rax
0x180019ab3  mov     [rdi], rax
0x180019ab6  mov     rcx, rsi; lpsz
0x180019ab9  call    cs:__imp_CharNextW
0x180019abf  mov     rdx, rax
0x180019ac2  mov     [rdi], rax
0x180019ac5  sub     rdx, rsi
0x180019ac8  sar     rdx, 1
0x180019acb  lea     rcx, [rdx+1]
0x180019acf  lea     rcx, [rbx+rcx*2]
0x180019ad3  cmp     rcx, rbp
0x180019ad6  jnb     loc_180019B87
0x180019adc  xor     ecx, ecx
0x180019ade  test    edx, edx
0x180019ae0  jle     short loc_180019A82
0x180019ae2  movzx   eax, word ptr [rsi]
0x180019ae5  inc     ecx
0x180019ae7  mov     [rbx], ax
0x180019aea  lea     rsi, [rsi+2]
0x180019aee  add     rbx, 2
0x180019af2  cmp     ecx, edx
0x180019af4  jl      short loc_180019AE2
0x180019af6  jmp     short loc_180019A82
0x180019af8  mov     rcx, [rdi]
0x180019afb  xor     eax, eax
0x180019afd  cmp     ax, [rcx]
0x180019b00  jz      loc_180019B87
0x180019b06  cmp     rbx, rbp
0x180019b09  jnb     short loc_180019B87
0x180019b0b  mov     [rbx], ax
0x180019b0e  mov     rcx, [rdi]; lpsz
0x180019b11  call    cs:__imp_CharNextW
0x180019b17  mov     [rdi], rax
0x180019b1a  jmp     short loc_180019B83
0x180019b1c  mov     rsi, [rdi]
0x180019b1f  xor     eax, eax
0x180019b21  cmp     ax, [rsi]
0x180019b24  jz      short loc_180019B7B
0x180019b26  movzx   ecx, word ptr [rsi]
0x180019b29  sub     ecx, 9
0x180019b2c  jz      short loc_180019B7B
0x180019b2e  sub     ecx, 1
0x180019b31  jz      short loc_180019B7B
0x180019b33  sub     ecx, 3
0x180019b36  jz      short loc_180019B7B
0x180019b38  cmp     ecx, 13h
0x180019b3b  jz      short loc_180019B7B
0x180019b3d  mov     rcx, rsi; lpsz
0x180019b40  call    cs:__imp_CharNextW
0x180019b46  mov     rdx, rax
0x180019b49  mov     [rdi], rax
0x180019b4c  sub     rdx, rsi
0x180019b4f  sar     rdx, 1
0x180019b52  lea     rcx, [rdx+1]
0x180019b56  lea     rcx, [rbx+rcx*2]
0x180019b5a  cmp     rcx, rbp
0x180019b5d  jnb     short loc_180019B87
0x180019b5f  xor     ecx, ecx
0x180019b61  test    edx, edx
0x180019b63  jle     short loc_180019B1C
0x180019b65  movzx   eax, word ptr [rsi]
0x180019b68  inc     ecx
0x180019b6a  mov     [rbx], ax
0x180019b6d  lea     rsi, [rsi+2]
0x180019b71  add     rbx, 2
0x180019b75  cmp     ecx, edx
0x180019b77  jl      short loc_180019B65
0x180019b79  jmp     short loc_180019B1C
0x180019b7b  cmp     rbx, rbp
0x180019b7e  jnb     short loc_180019B87
0x180019b80  mov     [rbx], ax
0x180019b83  xor     eax, eax
0x180019b85  jmp     short loc_180019B8C
0x180019b87  mov     eax, 80020009h
0x180019b8c  add     rsp, 20h
0x180019b90  pop     r14
0x180019b92  pop     rdi
0x180019b93  pop     rsi
0x180019b94  pop     rbp
0x180019b95  pop     rbx
0x180019b96  retn
```
