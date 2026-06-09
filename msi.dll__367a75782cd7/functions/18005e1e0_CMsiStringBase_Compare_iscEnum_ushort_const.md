# CMsiStringBase::Compare(iscEnum,ushort const *)

- ea: `0x18005e1e0`
- end: `0x18005e540`
- name: `?Compare@CMsiStringBase@@UEBAHW4iscEnum@@PEBG@Z`
- size: `864`
- prototype: `int __high(enum iscEnum, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180025560`
- `0x18005e1e0`
- `0x180061334`
- `0x1800620e4`
- `0x18025ab06`
- `0x18025c010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18005e30e`
- `msvcrt!wcsstr` at `0x18005e4be`
- `msvcrt!wcsstr` at `0x18005e30e`
- `msvcrt!wcsstr` at `0x18005e4be`
- `KERNEL32!lstrlenW` at `0x18005e2fc`
- `KERNEL32!lstrlenW` at `0x18005e32e`
- `KERNEL32!lstrlenW` at `0x18005e398`
- `KERNEL32!lstrlenW` at `0x18005e413`
- `KERNEL32!lstrlenW` at `0x18005e426`
- `KERNEL32!lstrlenW` at `0x18005e2fc`
- `KERNEL32!lstrlenW` at `0x18005e32e`
- `KERNEL32!lstrlenW` at `0x18005e398`
- `KERNEL32!lstrlenW` at `0x18005e413`
- `KERNEL32!lstrlenW` at `0x18005e426`
- `KERNEL32!CompareStringW` at `0x18005e3c3`
- `KERNEL32!CompareStringW` at `0x18005e535`
- `KERNEL32!CompareStringW` at `0x18005e3c3`
- `KERNEL32!CompareStringW` at `0x18005e535`
- `KERNEL32!lstrcmpiW` at `0x18005e25b`
- `KERNEL32!lstrcmpiW` at `0x18005e373`
- `KERNEL32!lstrcmpiW` at `0x18005e25b`
- `KERNEL32!lstrcmpiW` at `0x18005e373`
- `USER32!CharLowerW` at `0x18005e4a9`
- `USER32!CharLowerW` at `0x18005e4b2`
- `USER32!CharLowerW` at `0x18005e4a9`
- `USER32!CharLowerW` at `0x18005e4b2`

## pseudocode

```c
__int64 __fastcall CMsiStringBase::Compare(unsigned int *a1, int a2, const WCHAR *a3)
{
  const WCHAR *lpString2; // rsi
  const WCHAR *v6; // rax
  const WCHAR *v7; // rbx
  signed __int64 v8; // rsi
  int v9; // eax
  int v10; // ecx
  __int64 v12; // rdi
  __int64 v13; // rbp
  char *v14; // rax
  signed __int64 v15; // rsi
  int v16; // ecx
  int v17; // edx
  int v18; // ebp
  int v19; // ebp
  int v20; // ebp
  int v21; // ebp
  wchar_t *v22; // rax
  int v24; // eax
  unsigned int cchCount2; // eax
  int v26; // edi
  int v27; // eax
  int v28; // edi
  unsigned int v29; // eax
  void *v30; // r15
  unsigned int v31; // eax
  __int64 v32; // rax
  void *v33; // rbp
  wchar_t *v34; // rdi

  lpString2 = &Default;
  if ( a3 )
    lpString2 = a3;
  v6 = (const WCHAR *)(*(__int64 (__fastcall **)(unsigned int *))(*(_QWORD *)a1 + 80LL))(a1);
  v7 = v6;
  if ( !a2 )
  {
    v8 = (char *)lpString2 - (char *)v6;
    do
    {
      v9 = *(const WCHAR *)((char *)v7 + v8);
      v10 = *v7 - v9;
      if ( v10 )
        break;
      ++v7;
    }
    while ( v9 );
    return v10 == 0;
  }
  if ( a2 == 1 )
    return lstrcmpiW(v6, lpString2) == 0;
  v12 = a1[3];
  if ( !(_DWORD)v12 )
    return 0;
  if ( a2 == 4 )
  {
    v13 = -1;
    do
      ++v13;
    while ( lpString2[v13] );
    if ( (unsigned int)v13 > (unsigned int)v12 )
      return 0;
    v14 = (char *)&v6[v12 - (int)v13];
    v15 = (char *)lpString2 - v14;
    do
    {
      v16 = *(unsigned __int16 *)&v14[v15];
      v17 = *(unsigned __int16 *)v14 - v16;
      if ( v17 )
        break;
      v14 += 2;
    }
    while ( v16 );
    if ( v17 )
      return 0;
    return (unsigned int)(v12 - v13 + 1);
  }
  v18 = a2 - 2;
  if ( !v18 )
  {
    v24 = lstrlenW(lpString2);
    if ( v24 <= a1[3] )
      return memcmp_0(v7, lpString2, 2LL * v24) == 0;
    return 0;
  }
  v19 = v18 - 1;
  if ( v19 )
  {
    v20 = v19 - 2;
    if ( !v20 )
    {
      v13 = -1;
      do
        ++v13;
      while ( lpString2[v13] );
      if ( (unsigned int)v13 > (unsigned int)v12 )
        return 0;
      if ( lstrcmpiW(&v6[v12 - (int)v13], lpString2) )
        return 0;
      LODWORD(v12) = a1[3];
      return (unsigned int)(v12 - v13 + 1);
    }
    v21 = v20 - 1;
    if ( !v21 )
    {
      if ( lstrlenW(lpString2) <= a1[3] )
      {
        v22 = wcsstr(v7, lpString2);
        if ( v22 )
          return (unsigned int)(v22 - v7 + 1);
        else
          return 0;
      }
      return 0;
    }
    if ( v21 != 1 || lstrlenW(lpString2) > a1[3] )
      return 0;
    v28 = lstrlenW(lpString2) + 1;
    v29 = 2 * (a1[3] + 1);
    if ( !is_mul_ok(a1[3] + 1, 2u) )
      v29 = -1;
    v30 = (void *)operator new(v29);
    v31 = 2 * v28;
    if ( !is_mul_ok(v28, 2u) )
      v31 = -1;
    v32 = operator new(v31);
    v33 = (void *)v32;
    if ( !v30 || !v32 )
      return 0;
    if ( (int)StringCchCopyW((unsigned __int16 *)v30, a1[3] + 1, v7) < 0
      || (int)StringCchCopyW((unsigned __int16 *)v33, v28, lpString2) < 0 )
    {
      operator delete(v30);
      operator delete(v33);
      return 0;
    }
    else
    {
      CharLowerW((LPWSTR)v30);
      CharLowerW((LPWSTR)v33);
      v34 = wcsstr((const wchar_t *)v30, (const wchar_t *)v33);
      operator delete(v30);
      operator delete(v33);
      if ( v34 )
        LODWORD(v34) = (((char *)v34 - (_BYTE *)v30) >> 1) + 1;
      return (unsigned int)v34;
    }
  }
  else
  {
    cchCount2 = lstrlenW(lpString2);
    v26 = cchCount2;
    if ( cchCount2 > a1[3] )
      return 0;
    v27 = CompareStringW(0x400u, 1u, v7, cchCount2, lpString2, cchCount2);
    if ( !v27 )
      v27 = CompareStringW(0x400u, 1u, v7, v26, lpString2, v26);
    return v27 == 2;
  }
}

```

## disassembly

```asm
0x18005e1e0  mov     [rsp+arg_8], rbx
0x18005e1e5  mov     [rsp+arg_10], rbp
0x18005e1ea  push    rsi
0x18005e1eb  push    rdi
0x18005e1ec  push    r14
0x18005e1ee  sub     rsp, 30h
0x18005e1f2  mov     rax, [rcx]
0x18005e1f5  lea     rsi, Default
0x18005e1fc  test    r8, r8
0x18005e1ff  mov     ebp, edx
0x18005e201  mov     r14, rcx
0x18005e204  cmovnz  rsi, r8
0x18005e208  mov     rax, [rax+50h]
0x18005e20c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e211  mov     rbx, rax
0x18005e214  test    ebp, ebp
0x18005e216  jnz     short loc_18005E250
0x18005e218  sub     rsi, rax
0x18005e21b  nop     dword ptr [rax+rax+00h]
0x18005e220  movzx   ecx, word ptr [rbx]
0x18005e223  movzx   eax, word ptr [rbx+rsi]
0x18005e227  sub     ecx, eax
0x18005e229  jnz     short loc_18005E233
0x18005e22b  add     rbx, 2
0x18005e22f  test    eax, eax
0x18005e231  jnz     short loc_18005E220
0x18005e233  xor     edi, edi
0x18005e235  test    ecx, ecx
0x18005e237  setz    dil
0x18005e23b  mov     eax, edi
0x18005e23d  mov     rbx, [rsp+48h+arg_8]
0x18005e242  mov     rbp, [rsp+48h+arg_10]
0x18005e247  add     rsp, 30h
0x18005e24b  pop     r14
0x18005e24d  pop     rdi
0x18005e24e  pop     rsi
0x18005e24f  retn
0x18005e250  cmp     ebp, 1
0x18005e253  jnz     short loc_18005E26D
0x18005e255  mov     rdx, rsi; lpString2
0x18005e258  mov     rcx, rbx; lpString1
0x18005e25b  call    cs:__imp_lstrcmpiW
0x18005e261  xor     edi, edi
0x18005e263  test    eax, eax
0x18005e265  setz    dil
0x18005e269  mov     eax, edi
0x18005e26b  jmp     short loc_18005E23D
0x18005e26d  mov     edi, [r14+0Ch]
0x18005e271  mov     [rsp+48h+arg_0], r15
0x18005e276  test    edi, edi
0x18005e278  jz      short loc_18005E294
0x18005e27a  cmp     ebp, 4
0x18005e27d  jnz     short loc_18005E2D9
0x18005e27f  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18005e286  inc     rbp
0x18005e289  cmp     word ptr [rsi+rbp*2], 0
0x18005e28e  jnz     short loc_18005E286
0x18005e290  cmp     ebp, edi
0x18005e292  jbe     short loc_18005E29D
0x18005e294  mov     r15, [rsp+48h+arg_0]
0x18005e299  xor     eax, eax
0x18005e29b  jmp     short loc_18005E23D
0x18005e29d  movsxd  rax, ebp
0x18005e2a0  mov     rcx, rdi
0x18005e2a3  sub     rcx, rax
0x18005e2a6  lea     rax, [rbx+rcx*2]
0x18005e2aa  sub     rsi, rax
0x18005e2ad  nop     dword ptr [rax]
0x18005e2b0  movzx   edx, word ptr [rax]
0x18005e2b3  movzx   ecx, word ptr [rax+rsi]
0x18005e2b7  sub     edx, ecx
0x18005e2b9  jnz     short loc_18005E2C3
0x18005e2bb  add     rax, 2
0x18005e2bf  test    ecx, ecx
0x18005e2c1  jnz     short loc_18005E2B0
0x18005e2c3  test    edx, edx
0x18005e2c5  jz      loc_18005E385
0x18005e2cb  mov     r15, [rsp+48h+arg_0]
0x18005e2d0  xor     edi, edi
0x18005e2d2  mov     eax, edi
0x18005e2d4  jmp     loc_18005E23D
0x18005e2d9  sub     ebp, 2
0x18005e2dc  jz      short loc_18005E32B
0x18005e2de  sub     ebp, 1
0x18005e2e1  jz      loc_18005E395
0x18005e2e7  sub     ebp, 2
0x18005e2ea  jz      loc_18005E3E6
0x18005e2f0  sub     ebp, 1
0x18005e2f3  jnz     loc_18005E407
0x18005e2f9  mov     rcx, rsi; lpString
0x18005e2fc  call    cs:__imp_lstrlenW
0x18005e302  cmp     eax, [r14+0Ch]
0x18005e306  ja      short loc_18005E294
0x18005e308  mov     rdx, rsi; SubStr
0x18005e30b  mov     rcx, rbx; Str
0x18005e30e  call    cs:__imp_wcsstr
0x18005e314  test    rax, rax
0x18005e317  jnz     loc_18005E4E8
0x18005e31d  xor     edi, edi
0x18005e31f  mov     r15, [rsp+48h+arg_0]
0x18005e324  mov     eax, edi
0x18005e326  jmp     loc_18005E23D
0x18005e32b  mov     rcx, rsi; lpString
0x18005e32e  call    cs:__imp_lstrlenW
0x18005e334  cmp     eax, [r14+0Ch]
0x18005e338  ja      loc_18005E294
0x18005e33e  movsxd  r8, eax
0x18005e341  mov     rdx, rsi; Buf2
0x18005e344  add     r8, r8; Size
0x18005e347  mov     rcx, rbx; Buf1
0x18005e34a  call    memcmp_0
0x18005e34f  mov     r15, [rsp+48h+arg_0]
0x18005e354  xor     edi, edi
0x18005e356  test    eax, eax
0x18005e358  setz    dil
0x18005e35c  mov     eax, edi
0x18005e35e  jmp     loc_18005E23D
0x18005e363  movsxd  rax, ebp
0x18005e366  mov     rcx, rdi
0x18005e369  sub     rcx, rax
0x18005e36c  mov     rdx, rsi; lpString2
0x18005e36f  lea     rcx, [rbx+rcx*2]; lpString1
0x18005e373  call    cs:__imp_lstrcmpiW
0x18005e379  test    eax, eax
0x18005e37b  jnz     loc_18005E2CB
0x18005e381  mov     edi, [r14+0Ch]
0x18005e385  mov     r15, [rsp+48h+arg_0]
0x18005e38a  sub     edi, ebp
0x18005e38c  inc     edi
0x18005e38e  mov     eax, edi
0x18005e390  jmp     loc_18005E23D
0x18005e395  mov     rcx, rsi; lpString
0x18005e398  call    cs:__imp_lstrlenW
0x18005e39e  mov     edi, eax
0x18005e3a0  cmp     eax, [r14+0Ch]
0x18005e3a4  ja      loc_18005E294
0x18005e3aa  mov     [rsp+48h+cchCount2], eax; cchCount2
0x18005e3ae  mov     r9d, eax; cchCount1
0x18005e3b1  mov     r8, rbx; lpString1
0x18005e3b4  mov     [rsp+48h+lpString2], rsi; lpString2
0x18005e3b9  mov     edx, 1; dwCmpFlags
0x18005e3be  mov     ecx, 400h; Locale
0x18005e3c3  call    cs:__imp_CompareStringW
0x18005e3c9  test    eax, eax
0x18005e3cb  jz      loc_18005E51C
0x18005e3d1  mov     r15, [rsp+48h+arg_0]
0x18005e3d6  xor     edi, edi
0x18005e3d8  cmp     eax, 2
0x18005e3db  setz    dil
0x18005e3df  mov     eax, edi
0x18005e3e1  jmp     loc_18005E23D
0x18005e3e6  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18005e3ed  nop     dword ptr [rax]
0x18005e3f0  inc     rbp
0x18005e3f3  cmp     word ptr [rsi+rbp*2], 0
0x18005e3f8  jnz     short loc_18005E3F0
0x18005e3fa  cmp     ebp, edi
0x18005e3fc  ja      loc_18005E294
0x18005e402  jmp     loc_18005E363
0x18005e407  cmp     ebp, 1
0x18005e40a  jnz     loc_18005E294
0x18005e410  mov     rcx, rsi; lpString
0x18005e413  call    cs:__imp_lstrlenW
0x18005e419  cmp     eax, [r14+0Ch]
0x18005e41d  ja      loc_18005E294
0x18005e423  mov     rcx, rsi; lpString
0x18005e426  call    cs:__imp_lstrlenW
0x18005e42c  mov     ecx, [r14+0Ch]
0x18005e430  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18005e437  inc     ecx
0x18005e439  lea     edi, [rax+1]
0x18005e43c  mov     eax, 2
0x18005e441  mul     rcx
0x18005e444  cmovb   rax, rbp
0x18005e448  mov     rcx, rax; unsigned __int64
0x18005e44b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005e450  mov     r15, rax
0x18005e453  movsxd  rdi, edi
0x18005e456  mov     eax, 2
0x18005e45b  mul     rdi
0x18005e45e  cmovb   rax, rbp
0x18005e462  mov     rcx, rax; unsigned __int64
0x18005e465  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005e46a  mov     rbp, rax
0x18005e46d  test    r15, r15
0x18005e470  jz      loc_18005E294
0x18005e476  test    rax, rax
0x18005e479  jz      loc_18005E294
0x18005e47f  mov     edx, [r14+0Ch]
0x18005e483  mov     r8, rbx; unsigned __int16 *
0x18005e486  inc     edx; unsigned __int64
0x18005e488  mov     rcx, r15; unsigned __int16 *
0x18005e48b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005e490  test    eax, eax
0x18005e492  js      short loc_18005E500
0x18005e494  mov     r8, rsi; unsigned __int16 *
0x18005e497  mov     rdx, rdi; unsigned __int64
0x18005e49a  mov     rcx, rbp; unsigned __int16 *
0x18005e49d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005e4a2  test    eax, eax
0x18005e4a4  js      short loc_18005E500
0x18005e4a6  mov     rcx, r15; lpsz
0x18005e4a9  call    cs:__imp_CharLowerW
0x18005e4af  mov     rcx, rbp; lpsz
0x18005e4b2  call    cs:__imp_CharLowerW
0x18005e4b8  mov     rdx, rbp; SubStr
0x18005e4bb  mov     rcx, r15; Str
0x18005e4be  call    cs:__imp_wcsstr
0x18005e4c4  mov     rcx, r15; void *
0x18005e4c7  mov     rdi, rax
0x18005e4ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005e4cf  mov     rcx, rbp; void *
0x18005e4d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005e4d7  test    rdi, rdi
0x18005e4da  jnz     short loc_18005E4F6
0x18005e4dc  mov     r15, [rsp+48h+arg_0]
0x18005e4e1  mov     eax, edi
0x18005e4e3  jmp     loc_18005E23D
0x18005e4e8  sub     rax, rbx
0x18005e4eb  sar     rax, 1
0x18005e4ee  lea     edi, [rax+1]
0x18005e4f1  jmp     loc_18005E31F
0x18005e4f6  sub     rdi, r15
0x18005e4f9  sar     rdi, 1
0x18005e4fc  inc     edi
0x18005e4fe  jmp     short loc_18005E4DC
0x18005e500  mov     rcx, r15; void *
0x18005e503  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005e508  mov     rcx, rbp; void *
0x18005e50b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005e510  mov     r15, [rsp+48h+arg_0]
0x18005e515  xor     eax, eax
0x18005e517  jmp     loc_18005E23D
0x18005e51c  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18005e520  mov     r9d, edi; cchCount1
0x18005e523  mov     r8, rbx; lpString1
0x18005e526  mov     [rsp+48h+lpString2], rsi; lpString2
0x18005e52b  mov     edx, 1; dwCmpFlags
0x18005e530  mov     ecx, 400h; Locale
0x18005e535  call    cs:__imp_CompareStringW
0x18005e53b  jmp     loc_18005E3D1
```
