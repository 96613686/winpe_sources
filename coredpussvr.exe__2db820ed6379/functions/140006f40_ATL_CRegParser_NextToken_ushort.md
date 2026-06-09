# ATL::CRegParser::NextToken(ushort *)

- ea: `0x140006f40`
- end: `0x14000710a`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `458`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400061bc`
- `0x1400076dc`
- `0x140007a88`
- `0x14000836c`

## callees

- `0x140006f40`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140006f75`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140006fa9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140006fcf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140006ff1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140007006`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000707c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400070a7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140006f75`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140006fa9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140006fcf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140006ff1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140007006`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000707c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400070a7`

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
0x140006f40  push    rbx
0x140006f42  push    rbp
0x140006f43  push    rsi
0x140006f44  push    rdi
0x140006f45  push    r14
0x140006f47  sub     rsp, 20h
0x140006f4b  mov     rbx, rdx
0x140006f4e  mov     rdi, rcx
0x140006f51  mov     rsi, [rdi]
0x140006f54  movzx   ecx, word ptr [rsi]
0x140006f57  mov     r8d, ecx
0x140006f5a  sub     r8d, 9
0x140006f5e  jz      short loc_140006F72
0x140006f60  sub     r8d, 1
0x140006f64  jz      short loc_140006F72
0x140006f66  sub     r8d, 3
0x140006f6a  jz      short loc_140006F72
0x140006f6c  cmp     r8d, 13h
0x140006f70  jnz     short loc_140006F86
0x140006f72  mov     rcx, rsi; lpsz
0x140006f75  call    cs:__imp_CharNextW
0x140006f7c  nop     dword ptr [rax+rax+00h]
0x140006f81  mov     [rdi], rax
0x140006f84  jmp     short loc_140006F51
0x140006f86  xor     eax, eax
0x140006f88  cmp     ax, cx
0x140006f8b  jz      loc_140007056
0x140006f91  lea     r14d, [rax+27h]
0x140006f95  lea     rbp, [rbx+2000h]
0x140006f9c  cmp     r14w, cx
0x140006fa0  jnz     loc_14000708D
0x140006fa6  mov     rcx, rsi; lpsz
0x140006fa9  call    cs:__imp_CharNextW
0x140006fb0  nop     dword ptr [rax+rax+00h]
0x140006fb5  mov     [rdi], rax
0x140006fb8  mov     rcx, rax; lpsz
0x140006fbb  movzx   edx, word ptr [rax]
0x140006fbe  xor     eax, eax
0x140006fc0  cmp     ax, dx
0x140006fc3  jz      loc_140007067
0x140006fc9  cmp     r14w, dx
0x140006fcd  jnz     short loc_140006FE5
0x140006fcf  call    cs:__imp_CharNextW
0x140006fd6  nop     dword ptr [rax+rax+00h]
0x140006fdb  cmp     r14w, [rax]
0x140006fdf  jnz     loc_140007067
0x140006fe5  mov     rsi, [rdi]
0x140006fe8  cmp     r14w, [rsi]
0x140006fec  jnz     short loc_140007003
0x140006fee  mov     rcx, rsi; lpsz
0x140006ff1  call    cs:__imp_CharNextW
0x140006ff8  nop     dword ptr [rax+rax+00h]
0x140006ffd  mov     rsi, rax
0x140007000  mov     [rdi], rax
0x140007003  mov     rcx, rsi; lpsz
0x140007006  call    cs:__imp_CharNextW
0x14000700d  nop     dword ptr [rax+rax+00h]
0x140007012  mov     rdx, rax
0x140007015  mov     [rdi], rax
0x140007018  sub     rdx, rsi
0x14000701b  sar     rdx, 1
0x14000701e  lea     rcx, [rdx+1]
0x140007022  lea     rcx, [rbx+rcx*2]
0x140007026  cmp     rcx, rbp
0x140007029  jnb     short loc_140007056
0x14000702b  xor     ecx, ecx
0x14000702d  test    edx, edx
0x14000702f  jle     short loc_140007045
0x140007031  movzx   eax, word ptr [rsi]
0x140007034  inc     ecx
0x140007036  mov     [rbx], ax
0x140007039  lea     rsi, [rsi+2]
0x14000703d  add     rbx, 2
0x140007041  cmp     ecx, edx
0x140007043  jl      short loc_140007031
0x140007045  mov     rcx, [rdi]
0x140007048  xor     eax, eax
0x14000704a  movzx   edx, word ptr [rcx]
0x14000704d  cmp     ax, dx
0x140007050  jnz     loc_140006FC9
0x140007056  mov     eax, 80020009h
0x14000705b  add     rsp, 20h
0x14000705f  pop     r14
0x140007061  pop     rdi
0x140007062  pop     rsi
0x140007063  pop     rbp
0x140007064  pop     rbx
0x140007065  retn
0x140007067  mov     rcx, [rdi]
0x14000706a  xor     eax, eax
0x14000706c  cmp     ax, [rcx]
0x14000706f  jz      short loc_140007056
0x140007071  cmp     rbx, rbp
0x140007074  jnb     short loc_140007056
0x140007076  mov     [rbx], ax
0x140007079  mov     rcx, [rdi]; lpsz
0x14000707c  call    cs:__imp_CharNextW
0x140007083  nop     dword ptr [rax+rax+00h]
0x140007088  mov     [rdi], rax
0x14000708b  jmp     short loc_140007103
0x14000708d  movzx   ecx, cx
0x140007090  sub     ecx, 9
0x140007093  jz      short loc_1400070F5
0x140007095  sub     ecx, 1
0x140007098  jz      short loc_1400070F5
0x14000709a  sub     ecx, 3
0x14000709d  jz      short loc_1400070F5
0x14000709f  cmp     ecx, 13h
0x1400070a2  jz      short loc_1400070F5
0x1400070a4  mov     rcx, rsi; lpsz
0x1400070a7  call    cs:__imp_CharNextW
0x1400070ae  nop     dword ptr [rax+rax+00h]
0x1400070b3  mov     rdx, rax
0x1400070b6  mov     [rdi], rax
0x1400070b9  sub     rdx, rsi
0x1400070bc  sar     rdx, 1
0x1400070bf  lea     rcx, [rdx+1]
0x1400070c3  lea     rcx, [rbx+rcx*2]
0x1400070c7  cmp     rcx, rbp
0x1400070ca  jnb     short loc_140007056
0x1400070cc  xor     ecx, ecx
0x1400070ce  test    edx, edx
0x1400070d0  jle     short loc_1400070E6
0x1400070d2  movzx   eax, word ptr [rsi]
0x1400070d5  inc     ecx
0x1400070d7  mov     [rbx], ax
0x1400070da  lea     rsi, [rsi+2]
0x1400070de  add     rbx, 2
0x1400070e2  cmp     ecx, edx
0x1400070e4  jl      short loc_1400070D2
0x1400070e6  mov     rsi, [rdi]
0x1400070e9  xor     eax, eax
0x1400070eb  cmp     ax, [rsi]
0x1400070ee  jz      short loc_1400070F5
0x1400070f0  movzx   ecx, word ptr [rsi]
0x1400070f3  jmp     short loc_14000708D
0x1400070f5  cmp     rbx, rbp
0x1400070f8  jnb     loc_140007056
0x1400070fe  xor     eax, eax
0x140007100  mov     [rbx], ax
0x140007103  xor     eax, eax
0x140007105  jmp     loc_14000705B
```
