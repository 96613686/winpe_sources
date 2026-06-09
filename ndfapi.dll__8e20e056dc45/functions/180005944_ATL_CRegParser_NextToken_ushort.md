# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180005944`
- end: `0x180005adb`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800046ec`
- `0x180005f38`
- `0x1800062ac`
- `0x180006a5c`

## callees

- `0x180005944`

## import_xrefs

- `USER32!CharNextW` at `0x180005979`
- `USER32!CharNextW` at `0x1800059a7`
- `USER32!CharNextW` at `0x1800059c7`
- `USER32!CharNextW` at `0x1800059df`
- `USER32!CharNextW` at `0x1800059ee`
- `USER32!CharNextW` at `0x180005a59`
- `USER32!CharNextW` at `0x180005a7e`
- `USER32!CharNextW` at `0x180005979`
- `USER32!CharNextW` at `0x1800059a7`
- `USER32!CharNextW` at `0x1800059c7`
- `USER32!CharNextW` at `0x1800059df`
- `USER32!CharNextW` at `0x1800059ee`
- `USER32!CharNextW` at `0x180005a59`
- `USER32!CharNextW` at `0x180005a7e`

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
0x180005944  push    rbx
0x180005946  push    rbp
0x180005947  push    rsi
0x180005948  push    rdi
0x180005949  push    r14
0x18000594b  sub     rsp, 20h
0x18000594f  mov     rbx, rdx
0x180005952  mov     rdi, rcx
0x180005955  mov     rsi, [rdi]
0x180005958  movzx   ecx, word ptr [rsi]
0x18000595b  mov     r8d, ecx
0x18000595e  sub     r8d, 9
0x180005962  jz      short loc_180005976
0x180005964  sub     r8d, 1
0x180005968  jz      short loc_180005976
0x18000596a  sub     r8d, 3
0x18000596e  jz      short loc_180005976
0x180005970  cmp     r8d, 13h
0x180005974  jnz     short loc_180005984
0x180005976  mov     rcx, rsi; lpsz
0x180005979  call    cs:__imp_CharNextW
0x18000597f  mov     [rdi], rax
0x180005982  jmp     short loc_180005955
0x180005984  xor     eax, eax
0x180005986  cmp     ax, cx
0x180005989  jz      loc_180005A34
0x18000598f  lea     r14d, [rax+27h]
0x180005993  lea     rbp, [rbx+2000h]
0x18000599a  cmp     r14w, cx
0x18000599e  jnz     loc_180005A64
0x1800059a4  mov     rcx, rsi; lpsz
0x1800059a7  call    cs:__imp_CharNextW
0x1800059ad  mov     [rdi], rax
0x1800059b0  mov     rcx, rax; lpsz
0x1800059b3  movzx   edx, word ptr [rax]
0x1800059b6  xor     eax, eax
0x1800059b8  cmp     ax, dx
0x1800059bb  jz      loc_180005A44
0x1800059c1  cmp     r14w, dx
0x1800059c5  jnz     short loc_1800059D3
0x1800059c7  call    cs:__imp_CharNextW
0x1800059cd  cmp     r14w, [rax]
0x1800059d1  jnz     short loc_180005A44
0x1800059d3  mov     rsi, [rdi]
0x1800059d6  cmp     r14w, [rsi]
0x1800059da  jnz     short loc_1800059EB
0x1800059dc  mov     rcx, rsi; lpsz
0x1800059df  call    cs:__imp_CharNextW
0x1800059e5  mov     rsi, rax
0x1800059e8  mov     [rdi], rax
0x1800059eb  mov     rcx, rsi; lpsz
0x1800059ee  call    cs:__imp_CharNextW
0x1800059f4  mov     rdx, rax
0x1800059f7  mov     [rdi], rax
0x1800059fa  sub     rdx, rsi
0x1800059fd  sar     rdx, 1
0x180005a00  lea     rcx, [rdx+1]
0x180005a04  lea     rcx, [rbx+rcx*2]
0x180005a08  cmp     rcx, rbp
0x180005a0b  jnb     short loc_180005A34
0x180005a0d  xor     ecx, ecx
0x180005a0f  test    edx, edx
0x180005a11  jle     short loc_180005A27
0x180005a13  movzx   eax, word ptr [rsi]
0x180005a16  inc     ecx
0x180005a18  mov     [rbx], ax
0x180005a1b  lea     rsi, [rsi+2]
0x180005a1f  add     rbx, 2
0x180005a23  cmp     ecx, edx
0x180005a25  jl      short loc_180005A13
0x180005a27  mov     rcx, [rdi]
0x180005a2a  xor     eax, eax
0x180005a2c  movzx   edx, word ptr [rcx]
0x180005a2f  cmp     ax, dx
0x180005a32  jnz     short loc_1800059C1
0x180005a34  mov     eax, 80020009h
0x180005a39  add     rsp, 20h
0x180005a3d  pop     r14
0x180005a3f  pop     rdi
0x180005a40  pop     rsi
0x180005a41  pop     rbp
0x180005a42  pop     rbx
0x180005a43  retn
0x180005a44  mov     rcx, [rdi]
0x180005a47  xor     eax, eax
0x180005a49  cmp     ax, [rcx]
0x180005a4c  jz      short loc_180005A34
0x180005a4e  cmp     rbx, rbp
0x180005a51  jnb     short loc_180005A34
0x180005a53  mov     [rbx], ax
0x180005a56  mov     rcx, [rdi]; lpsz
0x180005a59  call    cs:__imp_CharNextW
0x180005a5f  mov     [rdi], rax
0x180005a62  jmp     short loc_180005AD4
0x180005a64  movzx   ecx, cx
0x180005a67  sub     ecx, 9
0x180005a6a  jz      short loc_180005AC6
0x180005a6c  sub     ecx, 1
0x180005a6f  jz      short loc_180005AC6
0x180005a71  sub     ecx, 3
0x180005a74  jz      short loc_180005AC6
0x180005a76  cmp     ecx, 13h
0x180005a79  jz      short loc_180005AC6
0x180005a7b  mov     rcx, rsi; lpsz
0x180005a7e  call    cs:__imp_CharNextW
0x180005a84  mov     rdx, rax
0x180005a87  mov     [rdi], rax
0x180005a8a  sub     rdx, rsi
0x180005a8d  sar     rdx, 1
0x180005a90  lea     rcx, [rdx+1]
0x180005a94  lea     rcx, [rbx+rcx*2]
0x180005a98  cmp     rcx, rbp
0x180005a9b  jnb     short loc_180005A34
0x180005a9d  xor     ecx, ecx
0x180005a9f  test    edx, edx
0x180005aa1  jle     short loc_180005AB7
0x180005aa3  movzx   eax, word ptr [rsi]
0x180005aa6  inc     ecx
0x180005aa8  mov     [rbx], ax
0x180005aab  lea     rsi, [rsi+2]
0x180005aaf  add     rbx, 2
0x180005ab3  cmp     ecx, edx
0x180005ab5  jl      short loc_180005AA3
0x180005ab7  mov     rsi, [rdi]
0x180005aba  xor     eax, eax
0x180005abc  cmp     ax, [rsi]
0x180005abf  jz      short loc_180005AC6
0x180005ac1  movzx   ecx, word ptr [rsi]
0x180005ac4  jmp     short loc_180005A64
0x180005ac6  cmp     rbx, rbp
0x180005ac9  jnb     loc_180005A34
0x180005acf  xor     eax, eax
0x180005ad1  mov     [rbx], ax
0x180005ad4  xor     eax, eax
0x180005ad6  jmp     loc_180005A39
```
