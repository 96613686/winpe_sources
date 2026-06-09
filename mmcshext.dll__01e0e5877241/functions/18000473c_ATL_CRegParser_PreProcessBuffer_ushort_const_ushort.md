# ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)

- ea: `0x18000473c`
- end: `0x1800049bb`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z`
- size: `639`
- prototype: `int(ATL::CRegParser *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004d3c`

## callees

- `0x18000473c`
- `0x18000a5b0`

## import_xrefs

- `USER32!CharNextW` at `0x1800047d4`
- `USER32!CharNextW` at `0x180004804`
- `USER32!CharNextW` at `0x1800048dc`
- `USER32!CharNextW` at `0x18000491e`
- `USER32!CharNextW` at `0x1800047d4`
- `USER32!CharNextW` at `0x180004804`
- `USER32!CharNextW` at `0x1800048dc`
- `USER32!CharNextW` at `0x18000491e`
- `KERNEL32!lstrcpynW` at `0x18000483d`
- `KERNEL32!lstrcpynW` at `0x18000483d`
- `KERNEL32!lstrcmpiW` at `0x180004864`
- `KERNEL32!lstrcmpiW` at `0x180004864`
- `ole32!CoTaskMemAlloc` at `0x1800047a3`
- `ole32!CoTaskMemAlloc` at `0x1800047a3`
- `ole32!CoTaskMemRealloc` at `0x1800048ab`
- `ole32!CoTaskMemRealloc` at `0x180004900`
- `ole32!CoTaskMemRealloc` at `0x18000494e`
- `ole32!CoTaskMemRealloc` at `0x1800048ab`
- `ole32!CoTaskMemRealloc` at `0x180004900`
- `ole32!CoTaskMemRealloc` at `0x18000494e`
- `ole32!CoTaskMemFree` at `0x180004961`
- `ole32!CoTaskMemFree` at `0x180004984`
- `ole32!CoTaskMemFree` at `0x180004961`
- `ole32!CoTaskMemFree` at `0x180004984`

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
0x18000473c  mov     [rsp+arg_8], rbx
0x180004741  push    rbp
0x180004742  push    rsi
0x180004743  push    rdi
0x180004744  push    r12
0x180004746  push    r13
0x180004748  push    r14
0x18000474a  push    r15
0x18000474c  sub     rsp, 80h
0x180004753  mov     rax, cs:__security_cookie
0x18000475a  xor     rax, rsp
0x18000475d  mov     [rsp+0B8h+var_48], rax
0x180004762  xor     r13d, r13d
0x180004765  mov     [rsp+0B8h+var_98], r8
0x18000476a  mov     r14, r8
0x18000476d  mov     rbx, rdx
0x180004770  mov     r15, rcx
0x180004773  test    rdx, rdx
0x180004776  jz      loc_18000498E
0x18000477c  test    r8, r8
0x18000477f  jz      loc_18000498E
0x180004785  mov     [r8], r13
0x180004788  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000478c  inc     rsi
0x18000478f  cmp     [rdx+rsi*2], r13w
0x180004794  jnz     short loc_18000478C
0x180004796  lea     esi, ds:2[rsi*2]
0x18000479d  movsxd  rcx, esi
0x1800047a0  add     rcx, rcx; cb
0x1800047a3  call    cs:__imp_CoTaskMemAlloc
0x1800047a9  mov     rdi, rax
0x1800047ac  test    rax, rax
0x1800047af  jz      loc_180004959
0x1800047b5  mov     [r15], rbx
0x1800047b8  mov     ebp, r13d
0x1800047bb  movzx   eax, word ptr [rbx]
0x1800047be  test    ax, ax
0x1800047c1  jz      loc_18000493B
0x1800047c7  cmp     ax, 25h ; '%'
0x1800047cb  jnz     loc_1800048EC
0x1800047d1  mov     rcx, rbx; lpsz
0x1800047d4  call    cs:__imp_CharNextW
0x1800047da  mov     rbx, rax
0x1800047dd  mov     [r15], rax
0x1800047e0  movzx   eax, word ptr [rax]
0x1800047e3  cmp     ax, 25h ; '%'
0x1800047e7  jz      loc_1800048EC
0x1800047ed  test    rbx, rbx
0x1800047f0  jz      loc_180004877
0x1800047f6  mov     r14, r13
0x1800047f9  jmp     short loc_180004810
0x1800047fb  cmp     ax, 25h ; '%'
0x1800047ff  jz      short loc_180004817
0x180004801  mov     rcx, rbx; lpsz
0x180004804  call    cs:__imp_CharNextW
0x18000480a  mov     rbx, rax
0x18000480d  movzx   eax, word ptr [rax]
0x180004810  test    ax, ax
0x180004813  jnz     short loc_1800047FB
0x180004815  jmp     short loc_18000481A
0x180004817  mov     r14, rbx
0x18000481a  test    r14, r14
0x18000481d  jz      short loc_180004877
0x18000481f  mov     r8, r14
0x180004822  sub     r8, [r15]
0x180004825  sar     r8, 1
0x180004828  cmp     r8d, 1Fh
0x18000482c  jg      loc_18000496B
0x180004832  mov     rdx, [r15]; lpString2
0x180004835  lea     rcx, [rsp+0B8h+String1]; lpString1
0x18000483a  inc     r8d; iMaxLength
0x18000483d  call    cs:__imp_lstrcpynW
0x180004843  mov     r12, [r15+8]
0x180004847  mov     ebx, r13d
0x18000484a  cmp     [r12+8], r13d
0x18000484f  jle     short loc_180004877
0x180004851  mov     rax, [r12]
0x180004855  lea     rdx, [rsp+0B8h+String1]; lpString2
0x18000485a  movsxd  r13, ebx
0x18000485d  mov     rcx, [rax+r13*8]
0x180004861  mov     rcx, [rcx]; lpString1
0x180004864  call    cs:__imp_lstrcmpiW
0x18000486a  test    eax, eax
0x18000486c  jz      short loc_180004881
0x18000486e  inc     ebx
0x180004870  cmp     ebx, [r12+8]
0x180004875  jl      short loc_180004851
0x180004877  mov     ebx, 80020009h
0x18000487c  jmp     loc_18000495E
0x180004881  mov     rax, [r12]
0x180004885  mov     rcx, [rax+r13*8]
0x180004889  xor     r13d, r13d
0x18000488c  mov     rbx, [rcx+8]
0x180004890  test    rbx, rbx
0x180004893  jz      short loc_180004877
0x180004895  jmp     short loc_1800048CE
0x180004897  lea     r12d, [rbp+1]
0x18000489b  cmp     r12d, esi
0x18000489e  jle     short loc_1800048BD
0x1800048a0  add     esi, esi
0x1800048a2  mov     rcx, rdi; pv
0x1800048a5  movsxd  rdx, esi
0x1800048a8  add     rdx, rdx; cb
0x1800048ab  call    cs:__imp_CoTaskMemRealloc
0x1800048b1  test    rax, rax
0x1800048b4  jz      loc_180004959
0x1800048ba  mov     rdi, rax
0x1800048bd  movzx   eax, word ptr [rbx]
0x1800048c0  add     rbx, 2
0x1800048c4  movsxd  rcx, ebp
0x1800048c7  mov     ebp, r12d
0x1800048ca  mov     [rdi+rcx*2], ax
0x1800048ce  cmp     [rbx], r13w
0x1800048d2  jnz     short loc_180004897
0x1800048d4  mov     rax, [r15]
0x1800048d7  jmp     short loc_1800048E5
0x1800048d9  mov     rcx, rax; lpsz
0x1800048dc  call    cs:__imp_CharNextW
0x1800048e2  mov     [r15], rax
0x1800048e5  cmp     rax, r14
0x1800048e8  jnz     short loc_1800048D9
0x1800048ea  jmp     short loc_18000491B
0x1800048ec  lea     r14d, [rbp+1]
0x1800048f0  cmp     r14d, esi
0x1800048f3  jle     short loc_18000490E
0x1800048f5  add     esi, esi
0x1800048f7  mov     rcx, rdi; pv
0x1800048fa  movsxd  rdx, esi
0x1800048fd  add     rdx, rdx; cb
0x180004900  call    cs:__imp_CoTaskMemRealloc
0x180004906  test    rax, rax
0x180004909  jz      short loc_180004959
0x18000490b  mov     rdi, rax
0x18000490e  movzx   eax, word ptr [rbx]
0x180004911  movsxd  rcx, ebp
0x180004914  mov     ebp, r14d
0x180004917  mov     [rdi+rcx*2], ax
0x18000491b  mov     rcx, [r15]; lpsz
0x18000491e  call    cs:__imp_CharNextW
0x180004924  mov     rbx, rax
0x180004927  mov     [r15], rax
0x18000492a  movzx   eax, word ptr [rax]
0x18000492d  test    ax, ax
0x180004930  jnz     loc_1800047C7
0x180004936  mov     r14, [rsp+0B8h+var_98]
0x18000493b  lea     eax, [rbp+1]
0x18000493e  cmp     eax, esi
0x180004940  jle     short loc_180004975
0x180004942  lea     eax, [rsi+rsi]
0x180004945  mov     rcx, rdi; pv
0x180004948  movsxd  rdx, eax
0x18000494b  add     rdx, rdx; cb
0x18000494e  call    cs:__imp_CoTaskMemRealloc
0x180004954  test    rax, rax
0x180004957  jnz     short loc_180004972
0x180004959  mov     ebx, 8007000Eh
0x18000495e  mov     rcx, rdi; pv
0x180004961  call    cs:__imp_CoTaskMemFree
0x180004967  mov     eax, ebx
0x180004969  jmp     short loc_180004993
0x18000496b  mov     ebx, 80004005h
0x180004970  jmp     short loc_18000495E
0x180004972  mov     rdi, rax
0x180004975  movzx   eax, word ptr [rbx]
0x180004978  movsxd  rcx, ebp
0x18000497b  mov     [rdi+rcx*2], ax
0x18000497f  xor     ecx, ecx; pv
0x180004981  mov     [r14], rdi
0x180004984  call    cs:__imp_CoTaskMemFree
0x18000498a  xor     eax, eax
0x18000498c  jmp     short loc_180004993
0x18000498e  mov     eax, 80004003h
0x180004993  mov     rcx, [rsp+0B8h+var_48]
0x180004998  xor     rcx, rsp; StackCookie
0x18000499b  call    __security_check_cookie
0x1800049a0  mov     rbx, [rsp+0B8h+arg_8]
0x1800049a8  add     rsp, 80h
0x1800049af  pop     r15
0x1800049b1  pop     r14
0x1800049b3  pop     r13
0x1800049b5  pop     r12
0x1800049b7  pop     rdi
0x1800049b8  pop     rsi
0x1800049b9  pop     rbp
0x1800049ba  retn
```
