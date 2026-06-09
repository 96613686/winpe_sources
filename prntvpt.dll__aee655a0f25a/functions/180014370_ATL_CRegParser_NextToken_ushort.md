# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180014370`
- end: `0x1800144c7`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800119c8`
- `0x1800152f0`
- `0x1800155fc`
- `0x1800163c0`

## callees

- `0x180014370`
- `0x180016514`

## import_xrefs

- `USER32!CharNextW` at `0x1800143a9`
- `USER32!CharNextW` at `0x1800143c2`
- `USER32!CharNextW` at `0x1800143da`
- `USER32!CharNextW` at `0x1800143e9`
- `USER32!CharNextW` at `0x180014441`
- `USER32!CharNextW` at `0x180014470`
- `USER32!CharNextW` at `0x1800143a9`
- `USER32!CharNextW` at `0x1800143c2`
- `USER32!CharNextW` at `0x1800143da`
- `USER32!CharNextW` at `0x1800143e9`
- `USER32!CharNextW` at `0x180014441`
- `USER32!CharNextW` at `0x180014470`

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
0x180014370  push    rbx
0x180014372  push    rbp
0x180014373  push    rsi
0x180014374  push    rdi
0x180014375  push    r14
0x180014377  sub     rsp, 20h
0x18001437b  mov     rbx, rdx
0x18001437e  mov     rdi, rcx
0x180014381  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180014386  mov     rcx, [rdi]; lpsz
0x180014389  xor     eax, eax
0x18001438b  cmp     ax, [rcx]
0x18001438e  jz      loc_1800144B7
0x180014394  lea     r14d, [rax+27h]
0x180014398  lea     rbp, [rbx+2000h]
0x18001439f  cmp     r14w, [rcx]
0x1800143a3  jnz     loc_18001444C
0x1800143a9  call    cs:__imp_CharNextW
0x1800143af  mov     [rdi], rax
0x1800143b2  mov     rcx, [rdi]; lpsz
0x1800143b5  xor     eax, eax
0x1800143b7  cmp     ax, [rcx]
0x1800143ba  jz      short loc_180014428
0x1800143bc  cmp     r14w, [rcx]
0x1800143c0  jnz     short loc_1800143CE
0x1800143c2  call    cs:__imp_CharNextW
0x1800143c8  cmp     r14w, [rax]
0x1800143cc  jnz     short loc_180014428
0x1800143ce  mov     rsi, [rdi]
0x1800143d1  cmp     r14w, [rsi]
0x1800143d5  jnz     short loc_1800143E6
0x1800143d7  mov     rcx, rsi; lpsz
0x1800143da  call    cs:__imp_CharNextW
0x1800143e0  mov     rsi, rax
0x1800143e3  mov     [rdi], rax
0x1800143e6  mov     rcx, rsi; lpsz
0x1800143e9  call    cs:__imp_CharNextW
0x1800143ef  mov     rdx, rax
0x1800143f2  mov     [rdi], rax
0x1800143f5  sub     rdx, rsi
0x1800143f8  sar     rdx, 1
0x1800143fb  lea     rcx, [rdx+1]
0x1800143ff  lea     rcx, [rbx+rcx*2]
0x180014403  cmp     rcx, rbp
0x180014406  jnb     loc_1800144B7
0x18001440c  xor     ecx, ecx
0x18001440e  test    edx, edx
0x180014410  jle     short loc_1800143B2
0x180014412  movzx   eax, word ptr [rsi]
0x180014415  inc     ecx
0x180014417  mov     [rbx], ax
0x18001441a  lea     rsi, [rsi+2]
0x18001441e  add     rbx, 2
0x180014422  cmp     ecx, edx
0x180014424  jl      short loc_180014412
0x180014426  jmp     short loc_1800143B2
0x180014428  mov     rcx, [rdi]
0x18001442b  xor     eax, eax
0x18001442d  cmp     ax, [rcx]
0x180014430  jz      loc_1800144B7
0x180014436  cmp     rbx, rbp
0x180014439  jnb     short loc_1800144B7
0x18001443b  mov     [rbx], ax
0x18001443e  mov     rcx, [rdi]; lpsz
0x180014441  call    cs:__imp_CharNextW
0x180014447  mov     [rdi], rax
0x18001444a  jmp     short loc_1800144B3
0x18001444c  mov     rsi, [rdi]
0x18001444f  xor     eax, eax
0x180014451  cmp     ax, [rsi]
0x180014454  jz      short loc_1800144AB
0x180014456  movzx   ecx, word ptr [rsi]
0x180014459  sub     ecx, 9
0x18001445c  jz      short loc_1800144AB
0x18001445e  sub     ecx, 1
0x180014461  jz      short loc_1800144AB
0x180014463  sub     ecx, 3
0x180014466  jz      short loc_1800144AB
0x180014468  cmp     ecx, 13h
0x18001446b  jz      short loc_1800144AB
0x18001446d  mov     rcx, rsi; lpsz
0x180014470  call    cs:__imp_CharNextW
0x180014476  mov     rdx, rax
0x180014479  mov     [rdi], rax
0x18001447c  sub     rdx, rsi
0x18001447f  sar     rdx, 1
0x180014482  lea     rcx, [rdx+1]
0x180014486  lea     rcx, [rbx+rcx*2]
0x18001448a  cmp     rcx, rbp
0x18001448d  jnb     short loc_1800144B7
0x18001448f  xor     ecx, ecx
0x180014491  test    edx, edx
0x180014493  jle     short loc_18001444C
0x180014495  movzx   eax, word ptr [rsi]
0x180014498  inc     ecx
0x18001449a  mov     [rbx], ax
0x18001449d  lea     rsi, [rsi+2]
0x1800144a1  add     rbx, 2
0x1800144a5  cmp     ecx, edx
0x1800144a7  jl      short loc_180014495
0x1800144a9  jmp     short loc_18001444C
0x1800144ab  cmp     rbx, rbp
0x1800144ae  jnb     short loc_1800144B7
0x1800144b0  mov     [rbx], ax
0x1800144b3  xor     eax, eax
0x1800144b5  jmp     short loc_1800144BC
0x1800144b7  mov     eax, 80020009h
0x1800144bc  add     rsp, 20h
0x1800144c0  pop     r14
0x1800144c2  pop     rdi
0x1800144c3  pop     rsi
0x1800144c4  pop     rbp
0x1800144c5  pop     rbx
0x1800144c6  retn
```
