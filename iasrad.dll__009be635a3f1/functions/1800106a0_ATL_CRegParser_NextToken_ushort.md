# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800106a0`
- end: `0x180010811`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `369`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ea4c`
- `0x180010ccc`
- `0x1800110f4`
- `0x180011990`

## callees

- `0x1800106a0`
- `0x180011a24`

## import_xrefs

- `USER32!CharNextW` at `0x1800106df`
- `USER32!CharNextW` at `0x1800106ff`
- `USER32!CharNextW` at `0x180010717`
- `USER32!CharNextW` at `0x180010726`
- `USER32!CharNextW` at `0x180010791`
- `USER32!CharNextW` at `0x1800107b6`
- `USER32!CharNextW` at `0x1800106df`
- `USER32!CharNextW` at `0x1800106ff`
- `USER32!CharNextW` at `0x180010717`
- `USER32!CharNextW` at `0x180010726`
- `USER32!CharNextW` at `0x180010791`
- `USER32!CharNextW` at `0x1800107b6`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rsi
  unsigned __int16 v5; // cx
  unsigned __int16 *v6; // rbp
  LPWSTR v7; // rax
  const WCHAR *v8; // rcx
  WCHAR v9; // dx
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

  ATL::CRegParser::SkipWhiteSpace(this);
  v4 = *(const WCHAR **)this;
  v5 = **(_WORD **)this;
  if ( !v5 )
    return 2147614729LL;
  v6 = a2 + 4096;
  if ( v5 != 39 )
  {
    do
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
      *(_QWORD *)this = v18;
      v19 = v18 - v4;
      if ( &a2[v19 + 1] >= v6 )
        return 2147614729LL;
      for ( i = 0; i < (int)v19; ++a2 )
      {
        ++i;
        *a2 = *v4++;
      }
      v4 = *(const WCHAR **)this;
      v5 = **(_WORD **)this;
    }
    while ( v5 );
    if ( a2 < v6 )
    {
      *a2 = 0;
      return 0;
    }
    return 2147614729LL;
  }
  v7 = CharNextW(*(LPCWSTR *)this);
  *(_QWORD *)this = v7;
  v8 = v7;
  v9 = *v7;
  if ( *v7 )
  {
    while ( v9 != 39 || *CharNextW(v8) == 39 )
    {
      v10 = *(const WCHAR **)this;
      if ( **(_WORD **)this == 39 )
      {
        v10 = CharNextW(*(LPCWSTR *)this);
        *(_QWORD *)this = v10;
      }
      v11 = CharNextW(v10);
      *(_QWORD *)this = v11;
      v12 = v11 - v10;
      if ( &a2[v12 + 1] < v6 )
      {
        for ( j = 0; j < (int)v12; ++a2 )
        {
          ++j;
          *a2 = *v10++;
        }
        v8 = *(const WCHAR **)this;
        v9 = **(_WORD **)this;
        if ( v9 )
          continue;
      }
      return 2147614729LL;
    }
  }
  if ( !**(_WORD **)this || a2 >= v6 )
    return 2147614729LL;
  *a2 = 0;
  *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
  return 0;
}

```

## disassembly

```asm
0x1800106a0  push    rbx
0x1800106a2  push    rbp
0x1800106a3  push    rsi
0x1800106a4  push    rdi
0x1800106a5  push    r14
0x1800106a7  sub     rsp, 20h
0x1800106ab  mov     rbx, rdx
0x1800106ae  mov     rdi, rcx
0x1800106b1  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800106b6  mov     rsi, [rdi]
0x1800106b9  xor     eax, eax
0x1800106bb  movzx   ecx, word ptr [rsi]
0x1800106be  cmp     ax, cx
0x1800106c1  jz      loc_18001076C
0x1800106c7  lea     r14d, [rax+27h]
0x1800106cb  lea     rbp, [rbx+2000h]
0x1800106d2  cmp     r14w, cx
0x1800106d6  jnz     loc_18001079C
0x1800106dc  mov     rcx, rsi; lpsz
0x1800106df  call    cs:__imp_CharNextW
0x1800106e5  mov     [rdi], rax
0x1800106e8  mov     rcx, rax; lpsz
0x1800106eb  movzx   edx, word ptr [rax]
0x1800106ee  xor     eax, eax
0x1800106f0  cmp     ax, dx
0x1800106f3  jz      loc_18001077C
0x1800106f9  cmp     r14w, dx
0x1800106fd  jnz     short loc_18001070B
0x1800106ff  call    cs:__imp_CharNextW
0x180010705  cmp     r14w, [rax]
0x180010709  jnz     short loc_18001077C
0x18001070b  mov     rsi, [rdi]
0x18001070e  cmp     r14w, [rsi]
0x180010712  jnz     short loc_180010723
0x180010714  mov     rcx, rsi; lpsz
0x180010717  call    cs:__imp_CharNextW
0x18001071d  mov     rsi, rax
0x180010720  mov     [rdi], rax
0x180010723  mov     rcx, rsi; lpsz
0x180010726  call    cs:__imp_CharNextW
0x18001072c  mov     rdx, rax
0x18001072f  mov     [rdi], rax
0x180010732  sub     rdx, rsi
0x180010735  sar     rdx, 1
0x180010738  lea     rcx, [rdx+1]
0x18001073c  lea     rcx, [rbx+rcx*2]
0x180010740  cmp     rcx, rbp
0x180010743  jnb     short loc_18001076C
0x180010745  xor     ecx, ecx
0x180010747  test    edx, edx
0x180010749  jle     short loc_18001075F
0x18001074b  movzx   eax, word ptr [rsi]
0x18001074e  inc     ecx
0x180010750  mov     [rbx], ax
0x180010753  lea     rsi, [rsi+2]
0x180010757  add     rbx, 2
0x18001075b  cmp     ecx, edx
0x18001075d  jl      short loc_18001074B
0x18001075f  mov     rcx, [rdi]
0x180010762  xor     eax, eax
0x180010764  movzx   edx, word ptr [rcx]
0x180010767  cmp     ax, dx
0x18001076a  jnz     short loc_1800106F9
0x18001076c  mov     eax, 80020009h
0x180010771  add     rsp, 20h
0x180010775  pop     r14
0x180010777  pop     rdi
0x180010778  pop     rsi
0x180010779  pop     rbp
0x18001077a  pop     rbx
0x18001077b  retn
0x18001077c  mov     rcx, [rdi]
0x18001077f  xor     eax, eax
0x180010781  cmp     ax, [rcx]
0x180010784  jz      short loc_18001076C
0x180010786  cmp     rbx, rbp
0x180010789  jnb     short loc_18001076C
0x18001078b  mov     [rbx], ax
0x18001078e  mov     rcx, [rdi]; lpsz
0x180010791  call    cs:__imp_CharNextW
0x180010797  mov     [rdi], rax
0x18001079a  jmp     short loc_18001080A
0x18001079c  movzx   ecx, cx
0x18001079f  sub     ecx, 9
0x1800107a2  jz      short loc_1800107FC
0x1800107a4  sub     ecx, 1
0x1800107a7  jz      short loc_1800107FC
0x1800107a9  sub     ecx, 3
0x1800107ac  jz      short loc_1800107FC
0x1800107ae  cmp     ecx, 13h
0x1800107b1  jz      short loc_1800107FC
0x1800107b3  mov     rcx, rsi; lpsz
0x1800107b6  call    cs:__imp_CharNextW
0x1800107bc  mov     rdx, rax
0x1800107bf  mov     [rdi], rax
0x1800107c2  sub     rdx, rsi
0x1800107c5  sar     rdx, 1
0x1800107c8  lea     rcx, [rdx+1]
0x1800107cc  lea     rcx, [rbx+rcx*2]
0x1800107d0  cmp     rcx, rbp
0x1800107d3  jnb     short loc_18001076C
0x1800107d5  xor     ecx, ecx
0x1800107d7  test    edx, edx
0x1800107d9  jle     short loc_1800107EF
0x1800107db  movzx   eax, word ptr [rsi]
0x1800107de  inc     ecx
0x1800107e0  mov     [rbx], ax
0x1800107e3  lea     rsi, [rsi+2]
0x1800107e7  add     rbx, 2
0x1800107eb  cmp     ecx, edx
0x1800107ed  jl      short loc_1800107DB
0x1800107ef  mov     rsi, [rdi]
0x1800107f2  xor     eax, eax
0x1800107f4  movzx   ecx, word ptr [rsi]
0x1800107f7  cmp     ax, cx
0x1800107fa  jnz     short loc_18001079C
0x1800107fc  cmp     rbx, rbp
0x1800107ff  jnb     loc_18001076C
0x180010805  xor     eax, eax
0x180010807  mov     [rbx], ax
0x18001080a  xor     eax, eax
0x18001080c  jmp     loc_180010771
```
