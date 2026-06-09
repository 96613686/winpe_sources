# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180012760`
- end: `0x1800128b7`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180011508`
- `0x180012e28`
- `0x180013134`
- `0x1800138ec`

## callees

- `0x180012760`
- `0x180013980`

## import_xrefs

- `USER32!CharNextW` at `0x180012799`
- `USER32!CharNextW` at `0x1800127b2`
- `USER32!CharNextW` at `0x1800127ca`
- `USER32!CharNextW` at `0x1800127d9`
- `USER32!CharNextW` at `0x180012831`
- `USER32!CharNextW` at `0x180012860`
- `USER32!CharNextW` at `0x180012799`
- `USER32!CharNextW` at `0x1800127b2`
- `USER32!CharNextW` at `0x1800127ca`
- `USER32!CharNextW` at `0x1800127d9`
- `USER32!CharNextW` at `0x180012831`
- `USER32!CharNextW` at `0x180012860`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rcx
  unsigned __int16 *v5; // rbp
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rsi
  LPWSTR v8; // rax
  __int64 v9; // rdx
  int i; // ecx
  unsigned __int16 *v11; // rsi
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
        v11 = *(unsigned __int16 **)this;
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
0x180012760  push    rbx
0x180012762  push    rbp
0x180012763  push    rsi
0x180012764  push    rdi
0x180012765  push    r14
0x180012767  sub     rsp, 20h
0x18001276b  mov     rbx, rdx
0x18001276e  mov     rdi, rcx
0x180012771  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180012776  mov     rcx, [rdi]; lpsz
0x180012779  xor     eax, eax
0x18001277b  cmp     ax, [rcx]
0x18001277e  jz      loc_1800128A7
0x180012784  lea     r14d, [rax+27h]
0x180012788  lea     rbp, [rbx+2000h]
0x18001278f  cmp     r14w, [rcx]
0x180012793  jnz     loc_18001283C
0x180012799  call    cs:__imp_CharNextW
0x18001279f  mov     [rdi], rax
0x1800127a2  mov     rcx, [rdi]; lpsz
0x1800127a5  xor     eax, eax
0x1800127a7  cmp     ax, [rcx]
0x1800127aa  jz      short loc_180012818
0x1800127ac  cmp     r14w, [rcx]
0x1800127b0  jnz     short loc_1800127BE
0x1800127b2  call    cs:__imp_CharNextW
0x1800127b8  cmp     r14w, [rax]
0x1800127bc  jnz     short loc_180012818
0x1800127be  mov     rsi, [rdi]
0x1800127c1  cmp     r14w, [rsi]
0x1800127c5  jnz     short loc_1800127D6
0x1800127c7  mov     rcx, rsi; lpsz
0x1800127ca  call    cs:__imp_CharNextW
0x1800127d0  mov     rsi, rax
0x1800127d3  mov     [rdi], rax
0x1800127d6  mov     rcx, rsi; lpsz
0x1800127d9  call    cs:__imp_CharNextW
0x1800127df  mov     rdx, rax
0x1800127e2  mov     [rdi], rax
0x1800127e5  sub     rdx, rsi
0x1800127e8  sar     rdx, 1
0x1800127eb  lea     rcx, [rdx+1]
0x1800127ef  lea     rcx, [rbx+rcx*2]
0x1800127f3  cmp     rcx, rbp
0x1800127f6  jnb     loc_1800128A7
0x1800127fc  xor     ecx, ecx
0x1800127fe  test    edx, edx
0x180012800  jle     short loc_1800127A2
0x180012802  movzx   eax, word ptr [rsi]
0x180012805  inc     ecx
0x180012807  mov     [rbx], ax
0x18001280a  lea     rsi, [rsi+2]
0x18001280e  add     rbx, 2
0x180012812  cmp     ecx, edx
0x180012814  jl      short loc_180012802
0x180012816  jmp     short loc_1800127A2
0x180012818  mov     rcx, [rdi]
0x18001281b  xor     eax, eax
0x18001281d  cmp     ax, [rcx]
0x180012820  jz      loc_1800128A7
0x180012826  cmp     rbx, rbp
0x180012829  jnb     short loc_1800128A7
0x18001282b  mov     [rbx], ax
0x18001282e  mov     rcx, [rdi]; lpsz
0x180012831  call    cs:__imp_CharNextW
0x180012837  mov     [rdi], rax
0x18001283a  jmp     short loc_1800128A3
0x18001283c  mov     rsi, [rdi]
0x18001283f  xor     eax, eax
0x180012841  cmp     ax, [rsi]
0x180012844  jz      short loc_18001289B
0x180012846  movzx   ecx, word ptr [rsi]
0x180012849  sub     ecx, 9
0x18001284c  jz      short loc_18001289B
0x18001284e  sub     ecx, 1
0x180012851  jz      short loc_18001289B
0x180012853  sub     ecx, 3
0x180012856  jz      short loc_18001289B
0x180012858  cmp     ecx, 13h
0x18001285b  jz      short loc_18001289B
0x18001285d  mov     rcx, rsi; lpsz
0x180012860  call    cs:__imp_CharNextW
0x180012866  mov     rdx, rax
0x180012869  mov     [rdi], rax
0x18001286c  sub     rdx, rsi
0x18001286f  sar     rdx, 1
0x180012872  lea     rcx, [rdx+1]
0x180012876  lea     rcx, [rbx+rcx*2]
0x18001287a  cmp     rcx, rbp
0x18001287d  jnb     short loc_1800128A7
0x18001287f  xor     ecx, ecx
0x180012881  test    edx, edx
0x180012883  jle     short loc_18001283C
0x180012885  movzx   eax, word ptr [rsi]
0x180012888  inc     ecx
0x18001288a  mov     [rbx], ax
0x18001288d  lea     rsi, [rsi+2]
0x180012891  add     rbx, 2
0x180012895  cmp     ecx, edx
0x180012897  jl      short loc_180012885
0x180012899  jmp     short loc_18001283C
0x18001289b  cmp     rbx, rbp
0x18001289e  jnb     short loc_1800128A7
0x1800128a0  mov     [rbx], ax
0x1800128a3  xor     eax, eax
0x1800128a5  jmp     short loc_1800128AC
0x1800128a7  mov     eax, 80020009h
0x1800128ac  add     rsp, 20h
0x1800128b0  pop     r14
0x1800128b2  pop     rdi
0x1800128b3  pop     rsi
0x1800128b4  pop     rbp
0x1800128b5  pop     rbx
0x1800128b6  retn
```
