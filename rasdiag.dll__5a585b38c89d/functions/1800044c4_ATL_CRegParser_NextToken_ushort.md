# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800044c4`
- end: `0x18000468e`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `458`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030ec`
- `0x180004b4c`
- `0x180004ef8`
- `0x18000574c`

## callees

- `0x1800044c4`

## import_xrefs

- `USER32!CharNextW` at `0x1800044f9`
- `USER32!CharNextW` at `0x18000452d`
- `USER32!CharNextW` at `0x180004553`
- `USER32!CharNextW` at `0x180004575`
- `USER32!CharNextW` at `0x18000458a`
- `USER32!CharNextW` at `0x180004600`
- `USER32!CharNextW` at `0x18000462b`
- `USER32!CharNextW` at `0x1800044f9`
- `USER32!CharNextW` at `0x18000452d`
- `USER32!CharNextW` at `0x180004553`
- `USER32!CharNextW` at `0x180004575`
- `USER32!CharNextW` at `0x18000458a`
- `USER32!CharNextW` at `0x180004600`
- `USER32!CharNextW` at `0x18000462b`

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
0x1800044c4  push    rbx
0x1800044c6  push    rbp
0x1800044c7  push    rsi
0x1800044c8  push    rdi
0x1800044c9  push    r14
0x1800044cb  sub     rsp, 20h
0x1800044cf  mov     rbx, rdx
0x1800044d2  mov     rdi, rcx
0x1800044d5  mov     rsi, [rdi]
0x1800044d8  movzx   ecx, word ptr [rsi]
0x1800044db  mov     r8d, ecx
0x1800044de  sub     r8d, 9
0x1800044e2  jz      short loc_1800044F6
0x1800044e4  sub     r8d, 1
0x1800044e8  jz      short loc_1800044F6
0x1800044ea  sub     r8d, 3
0x1800044ee  jz      short loc_1800044F6
0x1800044f0  cmp     r8d, 13h
0x1800044f4  jnz     short loc_18000450A
0x1800044f6  mov     rcx, rsi; lpsz
0x1800044f9  call    cs:__imp_CharNextW
0x180004500  nop     dword ptr [rax+rax+00h]
0x180004505  mov     [rdi], rax
0x180004508  jmp     short loc_1800044D5
0x18000450a  xor     eax, eax
0x18000450c  cmp     ax, cx
0x18000450f  jz      loc_1800045DA
0x180004515  lea     r14d, [rax+27h]
0x180004519  lea     rbp, [rbx+2000h]
0x180004520  cmp     r14w, cx
0x180004524  jnz     loc_180004611
0x18000452a  mov     rcx, rsi; lpsz
0x18000452d  call    cs:__imp_CharNextW
0x180004534  nop     dword ptr [rax+rax+00h]
0x180004539  mov     [rdi], rax
0x18000453c  mov     rcx, rax; lpsz
0x18000453f  movzx   edx, word ptr [rax]
0x180004542  xor     eax, eax
0x180004544  cmp     ax, dx
0x180004547  jz      loc_1800045EB
0x18000454d  cmp     r14w, dx
0x180004551  jnz     short loc_180004569
0x180004553  call    cs:__imp_CharNextW
0x18000455a  nop     dword ptr [rax+rax+00h]
0x18000455f  cmp     r14w, [rax]
0x180004563  jnz     loc_1800045EB
0x180004569  mov     rsi, [rdi]
0x18000456c  cmp     r14w, [rsi]
0x180004570  jnz     short loc_180004587
0x180004572  mov     rcx, rsi; lpsz
0x180004575  call    cs:__imp_CharNextW
0x18000457c  nop     dword ptr [rax+rax+00h]
0x180004581  mov     rsi, rax
0x180004584  mov     [rdi], rax
0x180004587  mov     rcx, rsi; lpsz
0x18000458a  call    cs:__imp_CharNextW
0x180004591  nop     dword ptr [rax+rax+00h]
0x180004596  mov     rdx, rax
0x180004599  mov     [rdi], rax
0x18000459c  sub     rdx, rsi
0x18000459f  sar     rdx, 1
0x1800045a2  lea     rcx, [rdx+1]
0x1800045a6  lea     rcx, [rbx+rcx*2]
0x1800045aa  cmp     rcx, rbp
0x1800045ad  jnb     short loc_1800045DA
0x1800045af  xor     ecx, ecx
0x1800045b1  test    edx, edx
0x1800045b3  jle     short loc_1800045C9
0x1800045b5  movzx   eax, word ptr [rsi]
0x1800045b8  inc     ecx
0x1800045ba  mov     [rbx], ax
0x1800045bd  lea     rsi, [rsi+2]
0x1800045c1  add     rbx, 2
0x1800045c5  cmp     ecx, edx
0x1800045c7  jl      short loc_1800045B5
0x1800045c9  mov     rcx, [rdi]
0x1800045cc  xor     eax, eax
0x1800045ce  movzx   edx, word ptr [rcx]
0x1800045d1  cmp     ax, dx
0x1800045d4  jnz     loc_18000454D
0x1800045da  mov     eax, 80020009h
0x1800045df  add     rsp, 20h
0x1800045e3  pop     r14
0x1800045e5  pop     rdi
0x1800045e6  pop     rsi
0x1800045e7  pop     rbp
0x1800045e8  pop     rbx
0x1800045e9  retn
0x1800045eb  mov     rcx, [rdi]
0x1800045ee  xor     eax, eax
0x1800045f0  cmp     ax, [rcx]
0x1800045f3  jz      short loc_1800045DA
0x1800045f5  cmp     rbx, rbp
0x1800045f8  jnb     short loc_1800045DA
0x1800045fa  mov     [rbx], ax
0x1800045fd  mov     rcx, [rdi]; lpsz
0x180004600  call    cs:__imp_CharNextW
0x180004607  nop     dword ptr [rax+rax+00h]
0x18000460c  mov     [rdi], rax
0x18000460f  jmp     short loc_180004687
0x180004611  movzx   ecx, cx
0x180004614  sub     ecx, 9
0x180004617  jz      short loc_180004679
0x180004619  sub     ecx, 1
0x18000461c  jz      short loc_180004679
0x18000461e  sub     ecx, 3
0x180004621  jz      short loc_180004679
0x180004623  cmp     ecx, 13h
0x180004626  jz      short loc_180004679
0x180004628  mov     rcx, rsi; lpsz
0x18000462b  call    cs:__imp_CharNextW
0x180004632  nop     dword ptr [rax+rax+00h]
0x180004637  mov     rdx, rax
0x18000463a  mov     [rdi], rax
0x18000463d  sub     rdx, rsi
0x180004640  sar     rdx, 1
0x180004643  lea     rcx, [rdx+1]
0x180004647  lea     rcx, [rbx+rcx*2]
0x18000464b  cmp     rcx, rbp
0x18000464e  jnb     short loc_1800045DA
0x180004650  xor     ecx, ecx
0x180004652  test    edx, edx
0x180004654  jle     short loc_18000466A
0x180004656  movzx   eax, word ptr [rsi]
0x180004659  inc     ecx
0x18000465b  mov     [rbx], ax
0x18000465e  lea     rsi, [rsi+2]
0x180004662  add     rbx, 2
0x180004666  cmp     ecx, edx
0x180004668  jl      short loc_180004656
0x18000466a  mov     rsi, [rdi]
0x18000466d  xor     eax, eax
0x18000466f  cmp     ax, [rsi]
0x180004672  jz      short loc_180004679
0x180004674  movzx   ecx, word ptr [rsi]
0x180004677  jmp     short loc_180004611
0x180004679  cmp     rbx, rbp
0x18000467c  jnb     loc_1800045DA
0x180004682  xor     eax, eax
0x180004684  mov     [rbx], ax
0x180004687  xor     eax, eax
0x180004689  jmp     loc_1800045DF
```
