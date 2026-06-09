# ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)

- ea: `0x18001036c`
- end: `0x1800105eb`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z`
- size: `639`
- prototype: `int(ATL::CRegParser *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010c3c`

## callees

- `0x18001036c`
- `0x180012b40`

## import_xrefs

- `USER32!CharNextW` at `0x180010404`
- `USER32!CharNextW` at `0x180010434`
- `USER32!CharNextW` at `0x18001050c`
- `USER32!CharNextW` at `0x18001054e`
- `USER32!CharNextW` at `0x180010404`
- `USER32!CharNextW` at `0x180010434`
- `USER32!CharNextW` at `0x18001050c`
- `USER32!CharNextW` at `0x18001054e`
- `KERNEL32!lstrcmpiW` at `0x180010494`
- `KERNEL32!lstrcmpiW` at `0x180010494`
- `KERNEL32!lstrcpynW` at `0x18001046d`
- `KERNEL32!lstrcpynW` at `0x18001046d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800103d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800103d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800105b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800105b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800104db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180010530`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001057e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800104db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180010530`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001057e`

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
0x18001036c  mov     [rsp+arg_8], rbx
0x180010371  push    rbp
0x180010372  push    rsi
0x180010373  push    rdi
0x180010374  push    r12
0x180010376  push    r13
0x180010378  push    r14
0x18001037a  push    r15
0x18001037c  sub     rsp, 80h
0x180010383  mov     rax, cs:__security_cookie
0x18001038a  xor     rax, rsp
0x18001038d  mov     [rsp+0B8h+var_48], rax
0x180010392  xor     r13d, r13d
0x180010395  mov     [rsp+0B8h+var_98], r8
0x18001039a  mov     r14, r8
0x18001039d  mov     rbx, rdx
0x1800103a0  mov     r15, rcx
0x1800103a3  test    rdx, rdx
0x1800103a6  jz      loc_1800105BE
0x1800103ac  test    r8, r8
0x1800103af  jz      loc_1800105BE
0x1800103b5  mov     [r8], r13
0x1800103b8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800103bc  inc     rsi
0x1800103bf  cmp     [rdx+rsi*2], r13w
0x1800103c4  jnz     short loc_1800103BC
0x1800103c6  lea     esi, ds:2[rsi*2]
0x1800103cd  movsxd  rcx, esi
0x1800103d0  add     rcx, rcx; cb
0x1800103d3  call    cs:__imp_CoTaskMemAlloc
0x1800103d9  mov     rdi, rax
0x1800103dc  test    rax, rax
0x1800103df  jz      loc_180010589
0x1800103e5  mov     [r15], rbx
0x1800103e8  mov     ebp, r13d
0x1800103eb  movzx   eax, word ptr [rbx]
0x1800103ee  test    ax, ax
0x1800103f1  jz      loc_18001056B
0x1800103f7  cmp     ax, 25h ; '%'
0x1800103fb  jnz     loc_18001051C
0x180010401  mov     rcx, rbx; lpsz
0x180010404  call    cs:__imp_CharNextW
0x18001040a  mov     rbx, rax
0x18001040d  mov     [r15], rax
0x180010410  movzx   eax, word ptr [rax]
0x180010413  cmp     ax, 25h ; '%'
0x180010417  jz      loc_18001051C
0x18001041d  test    rbx, rbx
0x180010420  jz      loc_1800104A7
0x180010426  mov     r14, r13
0x180010429  jmp     short loc_180010440
0x18001042b  cmp     ax, 25h ; '%'
0x18001042f  jz      short loc_180010447
0x180010431  mov     rcx, rbx; lpsz
0x180010434  call    cs:__imp_CharNextW
0x18001043a  mov     rbx, rax
0x18001043d  movzx   eax, word ptr [rax]
0x180010440  test    ax, ax
0x180010443  jnz     short loc_18001042B
0x180010445  jmp     short loc_18001044A
0x180010447  mov     r14, rbx
0x18001044a  test    r14, r14
0x18001044d  jz      short loc_1800104A7
0x18001044f  mov     r8, r14
0x180010452  sub     r8, [r15]
0x180010455  sar     r8, 1
0x180010458  cmp     r8d, 1Fh
0x18001045c  jg      loc_18001059B
0x180010462  mov     rdx, [r15]; lpString2
0x180010465  lea     rcx, [rsp+0B8h+String1]; lpString1
0x18001046a  inc     r8d; iMaxLength
0x18001046d  call    cs:__imp_lstrcpynW
0x180010473  mov     r12, [r15+8]
0x180010477  mov     ebx, r13d
0x18001047a  cmp     [r12+8], r13d
0x18001047f  jle     short loc_1800104A7
0x180010481  mov     rax, [r12]
0x180010485  lea     rdx, [rsp+0B8h+String1]; lpString2
0x18001048a  movsxd  r13, ebx
0x18001048d  mov     rcx, [rax+r13*8]
0x180010491  mov     rcx, [rcx]; lpString1
0x180010494  call    cs:__imp_lstrcmpiW
0x18001049a  test    eax, eax
0x18001049c  jz      short loc_1800104B1
0x18001049e  inc     ebx
0x1800104a0  cmp     ebx, [r12+8]
0x1800104a5  jl      short loc_180010481
0x1800104a7  mov     ebx, 80020009h
0x1800104ac  jmp     loc_18001058E
0x1800104b1  mov     rax, [r12]
0x1800104b5  mov     rcx, [rax+r13*8]
0x1800104b9  xor     r13d, r13d
0x1800104bc  mov     rbx, [rcx+8]
0x1800104c0  test    rbx, rbx
0x1800104c3  jz      short loc_1800104A7
0x1800104c5  jmp     short loc_1800104FE
0x1800104c7  lea     r12d, [rbp+1]
0x1800104cb  cmp     r12d, esi
0x1800104ce  jle     short loc_1800104ED
0x1800104d0  add     esi, esi
0x1800104d2  mov     rcx, rdi; pv
0x1800104d5  movsxd  rdx, esi
0x1800104d8  add     rdx, rdx; cb
0x1800104db  call    cs:__imp_CoTaskMemRealloc
0x1800104e1  test    rax, rax
0x1800104e4  jz      loc_180010589
0x1800104ea  mov     rdi, rax
0x1800104ed  movzx   eax, word ptr [rbx]
0x1800104f0  add     rbx, 2
0x1800104f4  movsxd  rcx, ebp
0x1800104f7  mov     ebp, r12d
0x1800104fa  mov     [rdi+rcx*2], ax
0x1800104fe  cmp     [rbx], r13w
0x180010502  jnz     short loc_1800104C7
0x180010504  mov     rax, [r15]
0x180010507  jmp     short loc_180010515
0x180010509  mov     rcx, rax; lpsz
0x18001050c  call    cs:__imp_CharNextW
0x180010512  mov     [r15], rax
0x180010515  cmp     rax, r14
0x180010518  jnz     short loc_180010509
0x18001051a  jmp     short loc_18001054B
0x18001051c  lea     r14d, [rbp+1]
0x180010520  cmp     r14d, esi
0x180010523  jle     short loc_18001053E
0x180010525  add     esi, esi
0x180010527  mov     rcx, rdi; pv
0x18001052a  movsxd  rdx, esi
0x18001052d  add     rdx, rdx; cb
0x180010530  call    cs:__imp_CoTaskMemRealloc
0x180010536  test    rax, rax
0x180010539  jz      short loc_180010589
0x18001053b  mov     rdi, rax
0x18001053e  movzx   eax, word ptr [rbx]
0x180010541  movsxd  rcx, ebp
0x180010544  mov     ebp, r14d
0x180010547  mov     [rdi+rcx*2], ax
0x18001054b  mov     rcx, [r15]; lpsz
0x18001054e  call    cs:__imp_CharNextW
0x180010554  mov     rbx, rax
0x180010557  mov     [r15], rax
0x18001055a  movzx   eax, word ptr [rax]
0x18001055d  test    ax, ax
0x180010560  jnz     loc_1800103F7
0x180010566  mov     r14, [rsp+0B8h+var_98]
0x18001056b  lea     eax, [rbp+1]
0x18001056e  cmp     eax, esi
0x180010570  jle     short loc_1800105A5
0x180010572  lea     eax, [rsi+rsi]
0x180010575  mov     rcx, rdi; pv
0x180010578  movsxd  rdx, eax
0x18001057b  add     rdx, rdx; cb
0x18001057e  call    cs:__imp_CoTaskMemRealloc
0x180010584  test    rax, rax
0x180010587  jnz     short loc_1800105A2
0x180010589  mov     ebx, 8007000Eh
0x18001058e  mov     rcx, rdi; pv
0x180010591  call    cs:__imp_CoTaskMemFree
0x180010597  mov     eax, ebx
0x180010599  jmp     short loc_1800105C3
0x18001059b  mov     ebx, 80004005h
0x1800105a0  jmp     short loc_18001058E
0x1800105a2  mov     rdi, rax
0x1800105a5  movzx   eax, word ptr [rbx]
0x1800105a8  movsxd  rcx, ebp
0x1800105ab  mov     [rdi+rcx*2], ax
0x1800105af  xor     ecx, ecx; pv
0x1800105b1  mov     [r14], rdi
0x1800105b4  call    cs:__imp_CoTaskMemFree
0x1800105ba  xor     eax, eax
0x1800105bc  jmp     short loc_1800105C3
0x1800105be  mov     eax, 80004003h
0x1800105c3  mov     rcx, [rsp+0B8h+var_48]
0x1800105c8  xor     rcx, rsp; StackCookie
0x1800105cb  call    __security_check_cookie
0x1800105d0  mov     rbx, [rsp+0B8h+arg_8]
0x1800105d8  add     rsp, 80h
0x1800105df  pop     r15
0x1800105e1  pop     r14
0x1800105e3  pop     r13
0x1800105e5  pop     r12
0x1800105e7  pop     rdi
0x1800105e8  pop     rsi
0x1800105e9  pop     rbp
0x1800105ea  retn
```
