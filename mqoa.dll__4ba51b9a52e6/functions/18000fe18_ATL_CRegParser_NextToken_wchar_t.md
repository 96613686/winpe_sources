# ATL::CRegParser::NextToken(wchar_t *)

- ea: `0x18000fe18`
- end: `0x18000ff73`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z`
- size: `347`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000be24`
- `0x180011168`
- `0x180011504`
- `0x180012470`

## callees

- `0x18000fe18`
- `0x1800124f8`

## import_xrefs

- `USER32!CharNextW` at `0x18000fe4f`
- `USER32!CharNextW` at `0x18000fe6b`
- `USER32!CharNextW` at `0x18000fe83`
- `USER32!CharNextW` at `0x18000fe92`
- `USER32!CharNextW` at `0x18000feef`
- `USER32!CharNextW` at `0x18000ff1b`
- `USER32!CharNextW` at `0x18000fe4f`
- `USER32!CharNextW` at `0x18000fe6b`
- `USER32!CharNextW` at `0x18000fe83`
- `USER32!CharNextW` at `0x18000fe92`
- `USER32!CharNextW` at `0x18000feef`
- `USER32!CharNextW` at `0x18000ff1b`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, wchar_t *a2)
{
  const WCHAR *v4; // rbx
  WCHAR v5; // cx
  wchar_t *v6; // rbp
  LPWSTR v7; // rdx
  const WCHAR *v8; // rbx
  wchar_t v10; // ax
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  LPWSTR v14; // rax
  const WCHAR *v15; // rcx
  wchar_t v16; // ax

  ATL::CRegParser::SkipWhiteSpace(this);
  v4 = *(const WCHAR **)this;
  v5 = **(_WORD **)this;
  if ( !v5 )
    return 2147614729LL;
  v6 = a2;
  if ( v5 != 39 )
  {
    while ( v5 )
    {
      v11 = v5 - 9;
      if ( !v11 )
        break;
      v12 = v11 - 1;
      if ( !v12 )
        break;
      v13 = v12 - 3;
      if ( !v13 || v13 == 19 )
        break;
      v14 = CharNextW(v4);
      *(_QWORD *)this = v14;
      if ( &a2[v14 - v4] >= v6 + 4096 )
        return 2147614729LL;
      v15 = v4;
      if ( v4 >= v14 )
      {
        v4 = v14;
      }
      else
      {
        do
        {
          v16 = *v15++;
          *a2++ = v16;
          v4 = *(const WCHAR **)this;
        }
        while ( (unsigned __int64)v15 < *(_QWORD *)this );
      }
      v5 = *v4;
    }
    *a2 = 0;
    return 0;
  }
  v7 = CharNextW(*(LPCWSTR *)this);
  *(_QWORD *)this = v7;
  while ( *v7 && (*v7 != 39 || *CharNextW(v7) == 39) )
  {
    v8 = *(const WCHAR **)this;
    if ( **(_WORD **)this == 39 )
    {
      v8 = CharNextW(*(LPCWSTR *)this);
      *(_QWORD *)this = v8;
    }
    v7 = CharNextW(v8);
    *(_QWORD *)this = v7;
    if ( &a2[v7 - v8] >= v6 + 4096 )
      return 2147614729LL;
    while ( v8 < v7 )
    {
      v10 = *v8++;
      *a2++ = v10;
      v7 = *(LPWSTR *)this;
    }
  }
  if ( !**(_WORD **)this )
    return 2147614729LL;
  *a2 = 0;
  *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
  return 0;
}

```

## disassembly

```asm
0x18000fe18  push    rbx
0x18000fe1a  push    rbp
0x18000fe1b  push    rsi
0x18000fe1c  push    rdi
0x18000fe1d  push    r14
0x18000fe1f  sub     rsp, 20h
0x18000fe23  mov     rsi, rdx
0x18000fe26  mov     rdi, rcx
0x18000fe29  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000fe2e  mov     rbx, [rdi]
0x18000fe31  xor     eax, eax
0x18000fe33  movzx   ecx, word ptr [rbx]
0x18000fe36  cmp     ax, cx
0x18000fe39  jz      short loc_18000FEB4
0x18000fe3b  lea     r14d, [rax+27h]
0x18000fe3f  mov     rbp, rsi
0x18000fe42  cmp     r14w, cx
0x18000fe46  jnz     loc_18000FEFA
0x18000fe4c  mov     rcx, rbx; lpsz
0x18000fe4f  call    cs:__imp_CharNextW
0x18000fe55  mov     rdx, rax
0x18000fe58  mov     [rdi], rax
0x18000fe5b  xor     eax, eax
0x18000fe5d  cmp     ax, [rdx]
0x18000fe60  jz      short loc_18000FEDF
0x18000fe62  cmp     r14w, [rdx]
0x18000fe66  jnz     short loc_18000FE77
0x18000fe68  mov     rcx, rdx; lpsz
0x18000fe6b  call    cs:__imp_CharNextW
0x18000fe71  cmp     r14w, [rax]
0x18000fe75  jnz     short loc_18000FEDF
0x18000fe77  mov     rbx, [rdi]
0x18000fe7a  cmp     r14w, [rbx]
0x18000fe7e  jnz     short loc_18000FE8F
0x18000fe80  mov     rcx, rbx; lpsz
0x18000fe83  call    cs:__imp_CharNextW
0x18000fe89  mov     rbx, rax
0x18000fe8c  mov     [rdi], rax
0x18000fe8f  mov     rcx, rbx; lpsz
0x18000fe92  call    cs:__imp_CharNextW
0x18000fe98  mov     rdx, rax
0x18000fe9b  mov     [rdi], rax
0x18000fe9e  sub     rax, rbx
0x18000fea1  sar     rax, 1
0x18000fea4  lea     rcx, [rsi+rax*2]
0x18000fea8  lea     rax, [rbp+2000h]
0x18000feaf  cmp     rcx, rax
0x18000feb2  jb      short loc_18000FED5
0x18000feb4  mov     eax, 80020009h
0x18000feb9  add     rsp, 20h
0x18000febd  pop     r14
0x18000febf  pop     rdi
0x18000fec0  pop     rsi
0x18000fec1  pop     rbp
0x18000fec2  pop     rbx
0x18000fec3  retn
0x18000fec4  movzx   eax, word ptr [rbx]
0x18000fec7  add     rbx, 2
0x18000fecb  mov     [rsi], ax
0x18000fece  add     rsi, 2
0x18000fed2  mov     rdx, [rdi]
0x18000fed5  cmp     rbx, rdx
0x18000fed8  jb      short loc_18000FEC4
0x18000feda  jmp     loc_18000FE5B
0x18000fedf  mov     rcx, [rdi]
0x18000fee2  xor     eax, eax
0x18000fee4  cmp     ax, [rcx]
0x18000fee7  jz      short loc_18000FEB4
0x18000fee9  mov     [rsi], ax
0x18000feec  mov     rcx, [rdi]; lpsz
0x18000feef  call    cs:__imp_CharNextW
0x18000fef5  mov     [rdi], rax
0x18000fef8  jmp     short loc_18000FF6C
0x18000fefa  xor     eax, eax
0x18000fefc  cmp     ax, cx
0x18000feff  jz      short loc_18000FF69
0x18000ff01  movzx   ecx, cx
0x18000ff04  sub     ecx, 9
0x18000ff07  jz      short loc_18000FF69
0x18000ff09  sub     ecx, 1
0x18000ff0c  jz      short loc_18000FF69
0x18000ff0e  sub     ecx, 3
0x18000ff11  jz      short loc_18000FF69
0x18000ff13  cmp     ecx, 13h
0x18000ff16  jz      short loc_18000FF69
0x18000ff18  mov     rcx, rbx; lpsz
0x18000ff1b  call    cs:__imp_CharNextW
0x18000ff21  mov     rcx, rax
0x18000ff24  mov     [rdi], rax
0x18000ff27  sub     rcx, rbx
0x18000ff2a  sar     rcx, 1
0x18000ff2d  lea     rdx, [rsi+rcx*2]
0x18000ff31  lea     rcx, [rbp+2000h]
0x18000ff38  cmp     rdx, rcx
0x18000ff3b  jnb     loc_18000FEB4
0x18000ff41  mov     rcx, rbx
0x18000ff44  cmp     rbx, rax
0x18000ff47  jnb     short loc_18000FF61
0x18000ff49  movzx   eax, word ptr [rcx]
0x18000ff4c  add     rcx, 2
0x18000ff50  mov     [rsi], ax
0x18000ff53  add     rsi, 2
0x18000ff57  mov     rbx, [rdi]
0x18000ff5a  cmp     rcx, rbx
0x18000ff5d  jb      short loc_18000FF49
0x18000ff5f  jmp     short loc_18000FF64
0x18000ff61  mov     rbx, rax
0x18000ff64  movzx   ecx, word ptr [rbx]
0x18000ff67  jmp     short loc_18000FEFA
0x18000ff69  mov     [rsi], ax
0x18000ff6c  xor     eax, eax
0x18000ff6e  jmp     loc_18000FEB9
```
