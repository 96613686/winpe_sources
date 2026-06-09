# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800044c0`
- end: `0x180004657`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800028fc`
- `0x180004b88`
- `0x180004efc`
- `0x180005928`

## callees

- `0x1800044c0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800044f5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004523`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004543`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000455b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000456a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800045d5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800045fa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800044f5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004523`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004543`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000455b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000456a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800045d5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800045fa`

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
0x1800044c0  push    rbx
0x1800044c2  push    rbp
0x1800044c3  push    rsi
0x1800044c4  push    rdi
0x1800044c5  push    r14
0x1800044c7  sub     rsp, 20h
0x1800044cb  mov     rbx, rdx
0x1800044ce  mov     rdi, rcx
0x1800044d1  mov     rsi, [rdi]
0x1800044d4  movzx   ecx, word ptr [rsi]
0x1800044d7  mov     r8d, ecx
0x1800044da  sub     r8d, 9
0x1800044de  jz      short loc_1800044F2
0x1800044e0  sub     r8d, 1
0x1800044e4  jz      short loc_1800044F2
0x1800044e6  sub     r8d, 3
0x1800044ea  jz      short loc_1800044F2
0x1800044ec  cmp     r8d, 13h
0x1800044f0  jnz     short loc_180004500
0x1800044f2  mov     rcx, rsi; lpsz
0x1800044f5  call    cs:__imp_CharNextW
0x1800044fb  mov     [rdi], rax
0x1800044fe  jmp     short loc_1800044D1
0x180004500  xor     eax, eax
0x180004502  cmp     ax, cx
0x180004505  jz      loc_1800045B0
0x18000450b  lea     r14d, [rax+27h]
0x18000450f  lea     rbp, [rbx+2000h]
0x180004516  cmp     r14w, cx
0x18000451a  jnz     loc_1800045E0
0x180004520  mov     rcx, rsi; lpsz
0x180004523  call    cs:__imp_CharNextW
0x180004529  mov     [rdi], rax
0x18000452c  mov     rcx, rax; lpsz
0x18000452f  movzx   edx, word ptr [rax]
0x180004532  xor     eax, eax
0x180004534  cmp     ax, dx
0x180004537  jz      loc_1800045C0
0x18000453d  cmp     r14w, dx
0x180004541  jnz     short loc_18000454F
0x180004543  call    cs:__imp_CharNextW
0x180004549  cmp     r14w, [rax]
0x18000454d  jnz     short loc_1800045C0
0x18000454f  mov     rsi, [rdi]
0x180004552  cmp     r14w, [rsi]
0x180004556  jnz     short loc_180004567
0x180004558  mov     rcx, rsi; lpsz
0x18000455b  call    cs:__imp_CharNextW
0x180004561  mov     rsi, rax
0x180004564  mov     [rdi], rax
0x180004567  mov     rcx, rsi; lpsz
0x18000456a  call    cs:__imp_CharNextW
0x180004570  mov     rdx, rax
0x180004573  mov     [rdi], rax
0x180004576  sub     rdx, rsi
0x180004579  sar     rdx, 1
0x18000457c  lea     rcx, [rdx+1]
0x180004580  lea     rcx, [rbx+rcx*2]
0x180004584  cmp     rcx, rbp
0x180004587  jnb     short loc_1800045B0
0x180004589  xor     ecx, ecx
0x18000458b  test    edx, edx
0x18000458d  jle     short loc_1800045A3
0x18000458f  movzx   eax, word ptr [rsi]
0x180004592  inc     ecx
0x180004594  mov     [rbx], ax
0x180004597  lea     rsi, [rsi+2]
0x18000459b  add     rbx, 2
0x18000459f  cmp     ecx, edx
0x1800045a1  jl      short loc_18000458F
0x1800045a3  mov     rcx, [rdi]
0x1800045a6  xor     eax, eax
0x1800045a8  movzx   edx, word ptr [rcx]
0x1800045ab  cmp     ax, dx
0x1800045ae  jnz     short loc_18000453D
0x1800045b0  mov     eax, 80020009h
0x1800045b5  add     rsp, 20h
0x1800045b9  pop     r14
0x1800045bb  pop     rdi
0x1800045bc  pop     rsi
0x1800045bd  pop     rbp
0x1800045be  pop     rbx
0x1800045bf  retn
0x1800045c0  mov     rcx, [rdi]
0x1800045c3  xor     eax, eax
0x1800045c5  cmp     ax, [rcx]
0x1800045c8  jz      short loc_1800045B0
0x1800045ca  cmp     rbx, rbp
0x1800045cd  jnb     short loc_1800045B0
0x1800045cf  mov     [rbx], ax
0x1800045d2  mov     rcx, [rdi]; lpsz
0x1800045d5  call    cs:__imp_CharNextW
0x1800045db  mov     [rdi], rax
0x1800045de  jmp     short loc_180004650
0x1800045e0  movzx   ecx, cx
0x1800045e3  sub     ecx, 9
0x1800045e6  jz      short loc_180004642
0x1800045e8  sub     ecx, 1
0x1800045eb  jz      short loc_180004642
0x1800045ed  sub     ecx, 3
0x1800045f0  jz      short loc_180004642
0x1800045f2  cmp     ecx, 13h
0x1800045f5  jz      short loc_180004642
0x1800045f7  mov     rcx, rsi; lpsz
0x1800045fa  call    cs:__imp_CharNextW
0x180004600  mov     rdx, rax
0x180004603  mov     [rdi], rax
0x180004606  sub     rdx, rsi
0x180004609  sar     rdx, 1
0x18000460c  lea     rcx, [rdx+1]
0x180004610  lea     rcx, [rbx+rcx*2]
0x180004614  cmp     rcx, rbp
0x180004617  jnb     short loc_1800045B0
0x180004619  xor     ecx, ecx
0x18000461b  test    edx, edx
0x18000461d  jle     short loc_180004633
0x18000461f  movzx   eax, word ptr [rsi]
0x180004622  inc     ecx
0x180004624  mov     [rbx], ax
0x180004627  lea     rsi, [rsi+2]
0x18000462b  add     rbx, 2
0x18000462f  cmp     ecx, edx
0x180004631  jl      short loc_18000461F
0x180004633  mov     rsi, [rdi]
0x180004636  xor     eax, eax
0x180004638  cmp     ax, [rsi]
0x18000463b  jz      short loc_180004642
0x18000463d  movzx   ecx, word ptr [rsi]
0x180004640  jmp     short loc_1800045E0
0x180004642  cmp     rbx, rbp
0x180004645  jnb     loc_1800045B0
0x18000464b  xor     eax, eax
0x18000464d  mov     [rbx], ax
0x180004650  xor     eax, eax
0x180004652  jmp     loc_1800045B5
```
