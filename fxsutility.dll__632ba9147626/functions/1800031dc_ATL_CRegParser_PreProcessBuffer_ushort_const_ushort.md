# ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)

- ea: `0x1800031dc`
- end: `0x18000345b`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z`
- size: `639`
- prototype: `int(ATL::CRegParser *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800035fc`

## callees

- `0x1800031dc`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180003304`
- `KERNEL32!lstrcmpiW` at `0x180003304`
- `KERNEL32!lstrcpynW` at `0x1800032dd`
- `KERNEL32!lstrcpynW` at `0x1800032dd`
- `ole32!CoTaskMemRealloc` at `0x18000334b`
- `ole32!CoTaskMemRealloc` at `0x1800033a0`
- `ole32!CoTaskMemRealloc` at `0x1800033ee`
- `ole32!CoTaskMemRealloc` at `0x18000334b`
- `ole32!CoTaskMemRealloc` at `0x1800033a0`
- `ole32!CoTaskMemRealloc` at `0x1800033ee`
- `ole32!CoTaskMemFree` at `0x180003401`
- `ole32!CoTaskMemFree` at `0x180003424`
- `ole32!CoTaskMemFree` at `0x180003401`
- `ole32!CoTaskMemFree` at `0x180003424`
- `ole32!CoTaskMemAlloc` at `0x180003243`
- `ole32!CoTaskMemAlloc` at `0x180003243`
- `USER32!CharNextW` at `0x180003274`
- `USER32!CharNextW` at `0x1800032a4`
- `USER32!CharNextW` at `0x18000337c`
- `USER32!CharNextW` at `0x1800033be`
- `USER32!CharNextW` at `0x180003274`
- `USER32!CharNextW` at `0x1800032a4`
- `USER32!CharNextW` at `0x18000337c`
- `USER32!CharNextW` at `0x1800033be`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, WCHAR *a2, unsigned __int16 **a3)
{
  unsigned __int16 **v3; // r14
  LPWSTR v4; // rbx
  __int64 v6; // rsi
  int v7; // esi
  void *v8; // rdi
  int v9; // ebp
  WCHAR v10; // ax
  WCHAR v11; // ax
  const WCHAR *v12; // r14
  __int64 v13; // r8
  LPCWSTR v14; // r12
  int v15; // ebx
  unsigned int v16; // ebx
  __int16 *v17; // rbx
  LPVOID v18; // rax
  __int16 v19; // ax
  __int64 v20; // rcx
  const WCHAR *i; // rax
  LPVOID v22; // rax
  __int64 v23; // rcx
  LPVOID v24; // rax
  WCHAR String1[32]; // [rsp+30h] [rbp-88h] BYREF

  v3 = a3;
  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6 + 2;
  v8 = CoTaskMemAlloc(2LL * v7);
  if ( !v8 )
  {
LABEL_41:
    v16 = -2147024882;
    goto LABEL_42;
  }
  *this = v4;
  v9 = 0;
  v10 = *v4;
  if ( !*v4 )
  {
LABEL_39:
    if ( v9 + 1 > v7 )
    {
      v24 = CoTaskMemRealloc(v8, 4LL * v7);
      if ( !v24 )
        goto LABEL_41;
      v8 = v24;
    }
    *((_WORD *)v8 + v9) = *v4;
    *v3 = (unsigned __int16 *)v8;
    CoTaskMemFree(0);
    return 0;
  }
  while ( 1 )
  {
    if ( v10 == 37 )
    {
      v4 = CharNextW(v4);
      *this = v4;
      v11 = *v4;
      if ( *v4 != 37 )
        break;
    }
    if ( v9 + 1 > v7 )
    {
      v7 *= 2;
      v22 = CoTaskMemRealloc(v8, 2LL * v7);
      if ( !v22 )
        goto LABEL_41;
      v8 = v22;
    }
    v23 = v9++;
    *((_WORD *)v8 + v23) = *v4;
LABEL_37:
    v4 = CharNextW(*this);
    *this = v4;
    v10 = *v4;
    if ( !*v4 )
    {
      v3 = a3;
      goto LABEL_39;
    }
  }
  if ( !v4 )
    goto LABEL_21;
  v12 = 0;
  while ( v11 )
  {
    if ( v11 == 37 )
    {
      v12 = v4;
      break;
    }
    v4 = CharNextW(v4);
    v11 = *v4;
  }
  if ( !v12 )
  {
LABEL_21:
    v16 = -2147352567;
    goto LABEL_42;
  }
  v13 = v12 - *this;
  if ( (int)v13 <= 31 )
  {
    lstrcpynW(String1, *this, v13 + 1);
    v14 = this[1];
    v15 = 0;
    if ( *((int *)v14 + 2) <= 0 )
      goto LABEL_21;
    while ( lstrcmpiW(**(LPCWSTR **)(*(_QWORD *)v14 + 8LL * v15), String1) )
    {
      if ( ++v15 >= *((_DWORD *)v14 + 2) )
        goto LABEL_21;
    }
    v17 = *(__int16 **)(*(_QWORD *)(*(_QWORD *)v14 + 8LL * v15) + 8LL);
    if ( !v17 )
      goto LABEL_21;
    while ( *v17 )
    {
      if ( v9 + 1 > v7 )
      {
        v7 *= 2;
        v18 = CoTaskMemRealloc(v8, 2LL * v7);
        if ( !v18 )
          goto LABEL_41;
        v8 = v18;
      }
      v19 = *v17++;
      v20 = v9++;
      *((_WORD *)v8 + v20) = v19;
    }
    for ( i = *this; i != v12; *this = i )
      i = CharNextW(i);
    goto LABEL_37;
  }
  v16 = -2147467259;
LABEL_42:
  CoTaskMemFree(v8);
  return v16;
}

```

## disassembly

```asm
0x1800031dc  mov     [rsp+arg_8], rbx
0x1800031e1  push    rbp
0x1800031e2  push    rsi
0x1800031e3  push    rdi
0x1800031e4  push    r12
0x1800031e6  push    r13
0x1800031e8  push    r14
0x1800031ea  push    r15
0x1800031ec  sub     rsp, 80h
0x1800031f3  mov     rax, cs:__security_cookie
0x1800031fa  xor     rax, rsp
0x1800031fd  mov     [rsp+0B8h+var_48], rax
0x180003202  xor     r13d, r13d
0x180003205  mov     [rsp+0B8h+var_98], r8
0x18000320a  mov     r14, r8
0x18000320d  mov     rbx, rdx
0x180003210  mov     r15, rcx
0x180003213  test    rdx, rdx
0x180003216  jz      loc_18000342E
0x18000321c  test    r8, r8
0x18000321f  jz      loc_18000342E
0x180003225  mov     [r8], r13
0x180003228  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000322c  inc     rsi
0x18000322f  cmp     [rdx+rsi*2], r13w
0x180003234  jnz     short loc_18000322C
0x180003236  lea     esi, ds:2[rsi*2]
0x18000323d  movsxd  rcx, esi
0x180003240  add     rcx, rcx; cb
0x180003243  call    cs:__imp_CoTaskMemAlloc
0x180003249  mov     rdi, rax
0x18000324c  test    rax, rax
0x18000324f  jz      loc_1800033F9
0x180003255  mov     [r15], rbx
0x180003258  mov     ebp, r13d
0x18000325b  movzx   eax, word ptr [rbx]
0x18000325e  test    ax, ax
0x180003261  jz      loc_1800033DB
0x180003267  cmp     ax, 25h ; '%'
0x18000326b  jnz     loc_18000338C
0x180003271  mov     rcx, rbx; lpsz
0x180003274  call    cs:__imp_CharNextW
0x18000327a  mov     rbx, rax
0x18000327d  mov     [r15], rax
0x180003280  movzx   eax, word ptr [rax]
0x180003283  cmp     ax, 25h ; '%'
0x180003287  jz      loc_18000338C
0x18000328d  test    rbx, rbx
0x180003290  jz      loc_180003317
0x180003296  mov     r14, r13
0x180003299  jmp     short loc_1800032B0
0x18000329b  cmp     ax, 25h ; '%'
0x18000329f  jz      short loc_1800032B7
0x1800032a1  mov     rcx, rbx; lpsz
0x1800032a4  call    cs:__imp_CharNextW
0x1800032aa  mov     rbx, rax
0x1800032ad  movzx   eax, word ptr [rax]
0x1800032b0  test    ax, ax
0x1800032b3  jnz     short loc_18000329B
0x1800032b5  jmp     short loc_1800032BA
0x1800032b7  mov     r14, rbx
0x1800032ba  test    r14, r14
0x1800032bd  jz      short loc_180003317
0x1800032bf  mov     r8, r14
0x1800032c2  sub     r8, [r15]
0x1800032c5  sar     r8, 1
0x1800032c8  cmp     r8d, 1Fh
0x1800032cc  jg      loc_18000340B
0x1800032d2  mov     rdx, [r15]; lpString2
0x1800032d5  lea     rcx, [rsp+0B8h+String1]; lpString1
0x1800032da  inc     r8d; iMaxLength
0x1800032dd  call    cs:__imp_lstrcpynW
0x1800032e3  mov     r12, [r15+8]
0x1800032e7  mov     ebx, r13d
0x1800032ea  cmp     [r12+8], r13d
0x1800032ef  jle     short loc_180003317
0x1800032f1  mov     rax, [r12]
0x1800032f5  lea     rdx, [rsp+0B8h+String1]; lpString2
0x1800032fa  movsxd  r13, ebx
0x1800032fd  mov     rcx, [rax+r13*8]
0x180003301  mov     rcx, [rcx]; lpString1
0x180003304  call    cs:__imp_lstrcmpiW
0x18000330a  test    eax, eax
0x18000330c  jz      short loc_180003321
0x18000330e  inc     ebx
0x180003310  cmp     ebx, [r12+8]
0x180003315  jl      short loc_1800032F1
0x180003317  mov     ebx, 80020009h
0x18000331c  jmp     loc_1800033FE
0x180003321  mov     rax, [r12]
0x180003325  mov     rcx, [rax+r13*8]
0x180003329  xor     r13d, r13d
0x18000332c  mov     rbx, [rcx+8]
0x180003330  test    rbx, rbx
0x180003333  jz      short loc_180003317
0x180003335  jmp     short loc_18000336E
0x180003337  lea     r12d, [rbp+1]
0x18000333b  cmp     r12d, esi
0x18000333e  jle     short loc_18000335D
0x180003340  add     esi, esi
0x180003342  mov     rcx, rdi; pv
0x180003345  movsxd  rdx, esi
0x180003348  add     rdx, rdx; cb
0x18000334b  call    cs:__imp_CoTaskMemRealloc
0x180003351  test    rax, rax
0x180003354  jz      loc_1800033F9
0x18000335a  mov     rdi, rax
0x18000335d  movzx   eax, word ptr [rbx]
0x180003360  add     rbx, 2
0x180003364  movsxd  rcx, ebp
0x180003367  mov     ebp, r12d
0x18000336a  mov     [rdi+rcx*2], ax
0x18000336e  cmp     [rbx], r13w
0x180003372  jnz     short loc_180003337
0x180003374  mov     rax, [r15]
0x180003377  jmp     short loc_180003385
0x180003379  mov     rcx, rax; lpsz
0x18000337c  call    cs:__imp_CharNextW
0x180003382  mov     [r15], rax
0x180003385  cmp     rax, r14
0x180003388  jnz     short loc_180003379
0x18000338a  jmp     short loc_1800033BB
0x18000338c  lea     r14d, [rbp+1]
0x180003390  cmp     r14d, esi
0x180003393  jle     short loc_1800033AE
0x180003395  add     esi, esi
0x180003397  mov     rcx, rdi; pv
0x18000339a  movsxd  rdx, esi
0x18000339d  add     rdx, rdx; cb
0x1800033a0  call    cs:__imp_CoTaskMemRealloc
0x1800033a6  test    rax, rax
0x1800033a9  jz      short loc_1800033F9
0x1800033ab  mov     rdi, rax
0x1800033ae  movzx   eax, word ptr [rbx]
0x1800033b1  movsxd  rcx, ebp
0x1800033b4  mov     ebp, r14d
0x1800033b7  mov     [rdi+rcx*2], ax
0x1800033bb  mov     rcx, [r15]; lpsz
0x1800033be  call    cs:__imp_CharNextW
0x1800033c4  mov     rbx, rax
0x1800033c7  mov     [r15], rax
0x1800033ca  movzx   eax, word ptr [rax]
0x1800033cd  test    ax, ax
0x1800033d0  jnz     loc_180003267
0x1800033d6  mov     r14, [rsp+0B8h+var_98]
0x1800033db  lea     eax, [rbp+1]
0x1800033de  cmp     eax, esi
0x1800033e0  jle     short loc_180003415
0x1800033e2  lea     eax, [rsi+rsi]
0x1800033e5  mov     rcx, rdi; pv
0x1800033e8  movsxd  rdx, eax
0x1800033eb  add     rdx, rdx; cb
0x1800033ee  call    cs:__imp_CoTaskMemRealloc
0x1800033f4  test    rax, rax
0x1800033f7  jnz     short loc_180003412
0x1800033f9  mov     ebx, 8007000Eh
0x1800033fe  mov     rcx, rdi; pv
0x180003401  call    cs:__imp_CoTaskMemFree
0x180003407  mov     eax, ebx
0x180003409  jmp     short loc_180003433
0x18000340b  mov     ebx, 80004005h
0x180003410  jmp     short loc_1800033FE
0x180003412  mov     rdi, rax
0x180003415  movzx   eax, word ptr [rbx]
0x180003418  movsxd  rcx, ebp
0x18000341b  mov     [rdi+rcx*2], ax
0x18000341f  xor     ecx, ecx; pv
0x180003421  mov     [r14], rdi
0x180003424  call    cs:__imp_CoTaskMemFree
0x18000342a  xor     eax, eax
0x18000342c  jmp     short loc_180003433
0x18000342e  mov     eax, 80004003h
0x180003433  mov     rcx, [rsp+0B8h+var_48]
0x180003438  xor     rcx, rsp; StackCookie
0x18000343b  call    __security_check_cookie
0x180003440  mov     rbx, [rsp+0B8h+arg_8]
0x180003448  add     rsp, 80h
0x18000344f  pop     r15
0x180003451  pop     r14
0x180003453  pop     r13
0x180003455  pop     r12
0x180003457  pop     rdi
0x180003458  pop     rsi
0x180003459  pop     rbp
0x18000345a  retn
```
