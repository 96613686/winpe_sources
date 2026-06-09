# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180016350`
- end: `0x1800164ab`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `347`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008670`
- `0x1800154e4`
- `0x18001684c`
- `0x180016a0c`

## callees

- `0x180016350`
- `0x180016a94`

## import_xrefs

- `USER32!CharNextW` at `0x180016387`
- `USER32!CharNextW` at `0x1800163a3`
- `USER32!CharNextW` at `0x1800163bb`
- `USER32!CharNextW` at `0x1800163ca`
- `USER32!CharNextW` at `0x180016427`
- `USER32!CharNextW` at `0x180016453`
- `USER32!CharNextW` at `0x180016387`
- `USER32!CharNextW` at `0x1800163a3`
- `USER32!CharNextW` at `0x1800163bb`
- `USER32!CharNextW` at `0x1800163ca`
- `USER32!CharNextW` at `0x180016427`
- `USER32!CharNextW` at `0x180016453`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rbx
  WCHAR v5; // cx
  unsigned __int16 *v6; // rbp
  LPWSTR v7; // rdx
  const WCHAR *v8; // rbx
  unsigned __int16 v10; // ax
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  LPWSTR v14; // rax
  const WCHAR *v15; // rcx
  unsigned __int16 v16; // ax

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
0x180016350  push    rbx
0x180016352  push    rbp
0x180016353  push    rsi
0x180016354  push    rdi
0x180016355  push    r14
0x180016357  sub     rsp, 20h
0x18001635b  mov     rsi, rdx
0x18001635e  mov     rdi, rcx
0x180016361  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180016366  mov     rbx, [rdi]
0x180016369  xor     eax, eax
0x18001636b  movzx   ecx, word ptr [rbx]
0x18001636e  cmp     ax, cx
0x180016371  jz      short loc_1800163EC
0x180016373  lea     r14d, [rax+27h]
0x180016377  mov     rbp, rsi
0x18001637a  cmp     r14w, cx
0x18001637e  jnz     loc_180016432
0x180016384  mov     rcx, rbx; lpsz
0x180016387  call    cs:__imp_CharNextW
0x18001638d  mov     rdx, rax
0x180016390  mov     [rdi], rax
0x180016393  xor     eax, eax
0x180016395  cmp     ax, [rdx]
0x180016398  jz      short loc_180016417
0x18001639a  cmp     r14w, [rdx]
0x18001639e  jnz     short loc_1800163AF
0x1800163a0  mov     rcx, rdx; lpsz
0x1800163a3  call    cs:__imp_CharNextW
0x1800163a9  cmp     r14w, [rax]
0x1800163ad  jnz     short loc_180016417
0x1800163af  mov     rbx, [rdi]
0x1800163b2  cmp     r14w, [rbx]
0x1800163b6  jnz     short loc_1800163C7
0x1800163b8  mov     rcx, rbx; lpsz
0x1800163bb  call    cs:__imp_CharNextW
0x1800163c1  mov     rbx, rax
0x1800163c4  mov     [rdi], rax
0x1800163c7  mov     rcx, rbx; lpsz
0x1800163ca  call    cs:__imp_CharNextW
0x1800163d0  mov     rdx, rax
0x1800163d3  mov     [rdi], rax
0x1800163d6  sub     rax, rbx
0x1800163d9  sar     rax, 1
0x1800163dc  lea     rcx, [rsi+rax*2]
0x1800163e0  lea     rax, [rbp+2000h]
0x1800163e7  cmp     rcx, rax
0x1800163ea  jb      short loc_18001640D
0x1800163ec  mov     eax, 80020009h
0x1800163f1  add     rsp, 20h
0x1800163f5  pop     r14
0x1800163f7  pop     rdi
0x1800163f8  pop     rsi
0x1800163f9  pop     rbp
0x1800163fa  pop     rbx
0x1800163fb  retn
0x1800163fc  movzx   eax, word ptr [rbx]
0x1800163ff  add     rbx, 2
0x180016403  mov     [rsi], ax
0x180016406  add     rsi, 2
0x18001640a  mov     rdx, [rdi]
0x18001640d  cmp     rbx, rdx
0x180016410  jb      short loc_1800163FC
0x180016412  jmp     loc_180016393
0x180016417  mov     rcx, [rdi]
0x18001641a  xor     eax, eax
0x18001641c  cmp     ax, [rcx]
0x18001641f  jz      short loc_1800163EC
0x180016421  mov     [rsi], ax
0x180016424  mov     rcx, [rdi]; lpsz
0x180016427  call    cs:__imp_CharNextW
0x18001642d  mov     [rdi], rax
0x180016430  jmp     short loc_1800164A4
0x180016432  xor     eax, eax
0x180016434  cmp     ax, cx
0x180016437  jz      short loc_1800164A1
0x180016439  movzx   ecx, cx
0x18001643c  sub     ecx, 9
0x18001643f  jz      short loc_1800164A1
0x180016441  sub     ecx, 1
0x180016444  jz      short loc_1800164A1
0x180016446  sub     ecx, 3
0x180016449  jz      short loc_1800164A1
0x18001644b  cmp     ecx, 13h
0x18001644e  jz      short loc_1800164A1
0x180016450  mov     rcx, rbx; lpsz
0x180016453  call    cs:__imp_CharNextW
0x180016459  mov     rcx, rax
0x18001645c  mov     [rdi], rax
0x18001645f  sub     rcx, rbx
0x180016462  sar     rcx, 1
0x180016465  lea     rdx, [rsi+rcx*2]
0x180016469  lea     rcx, [rbp+2000h]
0x180016470  cmp     rdx, rcx
0x180016473  jnb     loc_1800163EC
0x180016479  mov     rcx, rbx
0x18001647c  cmp     rbx, rax
0x18001647f  jnb     short loc_180016499
0x180016481  movzx   eax, word ptr [rcx]
0x180016484  add     rcx, 2
0x180016488  mov     [rsi], ax
0x18001648b  add     rsi, 2
0x18001648f  mov     rbx, [rdi]
0x180016492  cmp     rcx, rbx
0x180016495  jb      short loc_180016481
0x180016497  jmp     short loc_18001649C
0x180016499  mov     rbx, rax
0x18001649c  movzx   ecx, word ptr [rbx]
0x18001649f  jmp     short loc_180016432
0x1800164a1  mov     [rsi], ax
0x1800164a4  xor     eax, eax
0x1800164a6  jmp     loc_1800163F1
```
