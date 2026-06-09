# CMsiStringBase::Compare(iscEnum,ushort const *)

- ea: `0x18005eb00`
- end: `0x18005eeb5`
- name: `?Compare@CMsiStringBase@@UEBAHW4iscEnum@@PEBG@Z`
- size: `949`
- prototype: `int __high(enum iscEnum, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180014160`
- `0x180018ee0`
- `0x180019cc0`
- `0x18005eb00`
- `0x1802651c6`
- `0x180266010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18005ec44`
- `msvcrt!wcsstr` at `0x18005ee27`
- `msvcrt!wcsstr` at `0x18005ec44`
- `msvcrt!wcsstr` at `0x18005ee27`
- `KERNEL32!lstrlenW` at `0x18005ec2c`
- `KERNEL32!lstrlenW` at `0x18005ec6a`
- `KERNEL32!lstrlenW` at `0x18005ece0`
- `KERNEL32!lstrlenW` at `0x18005ed64`
- `KERNEL32!lstrlenW` at `0x18005ed7d`
- `KERNEL32!lstrlenW` at `0x18005ec2c`
- `KERNEL32!lstrlenW` at `0x18005ec6a`
- `KERNEL32!lstrlenW` at `0x18005ece0`
- `KERNEL32!lstrlenW` at `0x18005ed64`
- `KERNEL32!lstrlenW` at `0x18005ed7d`
- `KERNEL32!CompareStringW` at `0x18005ed11`
- `KERNEL32!CompareStringW` at `0x18005eea4`
- `KERNEL32!CompareStringW` at `0x18005ed11`
- `KERNEL32!CompareStringW` at `0x18005eea4`
- `KERNEL32!lstrcmpiW` at `0x18005eb7c`
- `KERNEL32!lstrcmpiW` at `0x18005ecb5`
- `KERNEL32!lstrcmpiW` at `0x18005eb7c`
- `KERNEL32!lstrcmpiW` at `0x18005ecb5`
- `USER32!CharLowerW` at `0x18005ee06`
- `USER32!CharLowerW` at `0x18005ee15`
- `USER32!CharLowerW` at `0x18005ee06`
- `USER32!CharLowerW` at `0x18005ee15`

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
  void *v29; // r15
  void *v30; // rax
  void *v31; // rbp
  wchar_t *v32; // rdi

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
    if ( v21 != 1 )
      return 0;
    if ( lstrlenW(lpString2) > a1[3] )
      return 0;
    v28 = lstrlenW(lpString2) + 1;
    v29 = operator new(saturated_mul(a1[3] + 1, 2u));
    v30 = operator new(saturated_mul(v28, 2u));
    v31 = v30;
    if ( !v29 || !v30 )
      return 0;
    if ( (int)StringCchCopyW((unsigned __int16 *)v29, a1[3] + 1, v7) < 0
      || (int)StringCchCopyW((unsigned __int16 *)v31, v28, lpString2) < 0 )
    {
      operator delete(v29);
      operator delete(v31);
      return 0;
    }
    else
    {
      CharLowerW((LPWSTR)v29);
      CharLowerW((LPWSTR)v31);
      v32 = wcsstr((const wchar_t *)v29, (const wchar_t *)v31);
      operator delete(v29);
      operator delete(v31);
      if ( v32 )
        LODWORD(v32) = (((char *)v32 - (_BYTE *)v29) >> 1) + 1;
      return (unsigned int)v32;
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
0x18005eb00  mov     [rsp+arg_8], rbx
0x18005eb05  mov     [rsp+arg_10], rbp
0x18005eb0a  push    rsi
0x18005eb0b  push    rdi
0x18005eb0c  push    r14
0x18005eb0e  sub     rsp, 30h
0x18005eb12  mov     rax, [rcx]
0x18005eb15  lea     rsi, Default
0x18005eb1c  test    r8, r8
0x18005eb1f  mov     ebp, edx
0x18005eb21  mov     r14, rcx
0x18005eb24  cmovnz  rsi, r8
0x18005eb28  mov     rax, [rax+50h]
0x18005eb2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eb31  mov     rbx, rax
0x18005eb34  test    ebp, ebp
0x18005eb36  jnz     short loc_18005EB71
0x18005eb38  sub     rsi, rax
0x18005eb3b  nop     dword ptr [rax+rax+00h]
0x18005eb40  movzx   ecx, word ptr [rbx]
0x18005eb43  movzx   eax, word ptr [rbx+rsi]
0x18005eb47  sub     ecx, eax
0x18005eb49  jnz     short loc_18005EB53
0x18005eb4b  add     rbx, 2
0x18005eb4f  test    eax, eax
0x18005eb51  jnz     short loc_18005EB40
0x18005eb53  xor     edi, edi
0x18005eb55  test    ecx, ecx
0x18005eb57  setz    dil
0x18005eb5b  mov     eax, edi
0x18005eb5d  mov     rbx, [rsp+48h+arg_8]
0x18005eb62  mov     rbp, [rsp+48h+arg_10]
0x18005eb67  add     rsp, 30h
0x18005eb6b  pop     r14
0x18005eb6d  pop     rdi
0x18005eb6e  pop     rsi
0x18005eb6f  retn
0x18005eb71  cmp     ebp, 1
0x18005eb74  jnz     short loc_18005EB94
0x18005eb76  mov     rdx, rsi; lpString2
0x18005eb79  mov     rcx, rbx; lpString1
0x18005eb7c  call    cs:__imp_lstrcmpiW
0x18005eb83  nop     dword ptr [rax+rax+00h]
0x18005eb88  xor     edi, edi
0x18005eb8a  test    eax, eax
0x18005eb8c  setz    dil
0x18005eb90  mov     eax, edi
0x18005eb92  jmp     short loc_18005EB5D
0x18005eb94  mov     edi, [r14+0Ch]
0x18005eb98  mov     [rsp+48h+arg_0], r15
0x18005eb9d  test    edi, edi
0x18005eb9f  jz      short loc_18005EBBE
0x18005eba1  cmp     ebp, 4
0x18005eba4  jnz     short loc_18005EC09
0x18005eba6  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18005ebad  nop     dword ptr [rax]
0x18005ebb0  inc     rbp
0x18005ebb3  cmp     word ptr [rsi+rbp*2], 0
0x18005ebb8  jnz     short loc_18005EBB0
0x18005ebba  cmp     ebp, edi
0x18005ebbc  jbe     short loc_18005EBC7
0x18005ebbe  mov     r15, [rsp+48h+arg_0]
0x18005ebc3  xor     eax, eax
0x18005ebc5  jmp     short loc_18005EB5D
0x18005ebc7  movsxd  rax, ebp
0x18005ebca  mov     rcx, rdi
0x18005ebcd  sub     rcx, rax
0x18005ebd0  lea     rax, [rbx+rcx*2]
0x18005ebd4  sub     rsi, rax
0x18005ebd7  nop     word ptr [rax+rax+00000000h]
0x18005ebe0  movzx   edx, word ptr [rax]
0x18005ebe3  movzx   ecx, word ptr [rax+rsi]
0x18005ebe7  sub     edx, ecx
0x18005ebe9  jnz     short loc_18005EBF3
0x18005ebeb  add     rax, 2
0x18005ebef  test    ecx, ecx
0x18005ebf1  jnz     short loc_18005EBE0
0x18005ebf3  test    edx, edx
0x18005ebf5  jz      loc_18005ECCD
0x18005ebfb  mov     r15, [rsp+48h+arg_0]
0x18005ec00  xor     edi, edi
0x18005ec02  mov     eax, edi
0x18005ec04  jmp     loc_18005EB5D
0x18005ec09  sub     ebp, 2
0x18005ec0c  jz      short loc_18005EC67
0x18005ec0e  sub     ebp, 1
0x18005ec11  jz      loc_18005ECDD
0x18005ec17  sub     ebp, 2
0x18005ec1a  jz      loc_18005ED3A
0x18005ec20  sub     ebp, 1
0x18005ec23  jnz     loc_18005ED58
0x18005ec29  mov     rcx, rsi; lpString
0x18005ec2c  call    cs:__imp_lstrlenW
0x18005ec33  nop     dword ptr [rax+rax+00h]
0x18005ec38  cmp     eax, [r14+0Ch]
0x18005ec3c  ja      short loc_18005EBBE
0x18005ec3e  mov     rdx, rsi; SubStr
0x18005ec41  mov     rcx, rbx; Str
0x18005ec44  call    cs:__imp_wcsstr
0x18005ec4b  nop     dword ptr [rax+rax+00h]
0x18005ec50  test    rax, rax
0x18005ec53  jnz     loc_18005EE57
0x18005ec59  xor     edi, edi
0x18005ec5b  mov     r15, [rsp+48h+arg_0]
0x18005ec60  mov     eax, edi
0x18005ec62  jmp     loc_18005EB5D
0x18005ec67  mov     rcx, rsi; lpString
0x18005ec6a  call    cs:__imp_lstrlenW
0x18005ec71  nop     dword ptr [rax+rax+00h]
0x18005ec76  cmp     eax, [r14+0Ch]
0x18005ec7a  ja      loc_18005EBBE
0x18005ec80  movsxd  r8, eax
0x18005ec83  mov     rdx, rsi; Buf2
0x18005ec86  add     r8, r8; Size
0x18005ec89  mov     rcx, rbx; Buf1
0x18005ec8c  call    memcmp_0
0x18005ec91  mov     r15, [rsp+48h+arg_0]
0x18005ec96  xor     edi, edi
0x18005ec98  test    eax, eax
0x18005ec9a  setz    dil
0x18005ec9e  mov     eax, edi
0x18005eca0  jmp     loc_18005EB5D
0x18005eca5  movsxd  rax, ebp
0x18005eca8  mov     rcx, rdi
0x18005ecab  sub     rcx, rax
0x18005ecae  mov     rdx, rsi; lpString2
0x18005ecb1  lea     rcx, [rbx+rcx*2]; lpString1
0x18005ecb5  call    cs:__imp_lstrcmpiW
0x18005ecbc  nop     dword ptr [rax+rax+00h]
0x18005ecc1  test    eax, eax
0x18005ecc3  jnz     loc_18005EBFB
0x18005ecc9  mov     edi, [r14+0Ch]
0x18005eccd  mov     r15, [rsp+48h+arg_0]
0x18005ecd2  sub     edi, ebp
0x18005ecd4  inc     edi
0x18005ecd6  mov     eax, edi
0x18005ecd8  jmp     loc_18005EB5D
0x18005ecdd  mov     rcx, rsi; lpString
0x18005ece0  call    cs:__imp_lstrlenW
0x18005ece7  nop     dword ptr [rax+rax+00h]
0x18005ecec  mov     edi, eax
0x18005ecee  cmp     eax, [r14+0Ch]
0x18005ecf2  ja      loc_18005EBBE
0x18005ecf8  mov     [rsp+48h+cchCount2], eax; cchCount2
0x18005ecfc  mov     r9d, eax; cchCount1
0x18005ecff  mov     r8, rbx; lpString1
0x18005ed02  mov     [rsp+48h+lpString2], rsi; lpString2
0x18005ed07  mov     edx, 1; dwCmpFlags
0x18005ed0c  mov     ecx, 400h; Locale
0x18005ed11  call    cs:__imp_CompareStringW
0x18005ed18  nop     dword ptr [rax+rax+00h]
0x18005ed1d  test    eax, eax
0x18005ed1f  jz      loc_18005EE8B
0x18005ed25  mov     r15, [rsp+48h+arg_0]
0x18005ed2a  xor     edi, edi
0x18005ed2c  cmp     eax, 2
0x18005ed2f  setz    dil
0x18005ed33  mov     eax, edi
0x18005ed35  jmp     loc_18005EB5D
0x18005ed3a  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18005ed41  inc     rbp
0x18005ed44  cmp     word ptr [rsi+rbp*2], 0
0x18005ed49  jnz     short loc_18005ED41
0x18005ed4b  cmp     ebp, edi
0x18005ed4d  ja      loc_18005EBBE
0x18005ed53  jmp     loc_18005ECA5
0x18005ed58  cmp     ebp, 1
0x18005ed5b  jnz     loc_18005EBBE
0x18005ed61  mov     rcx, rsi; lpString
0x18005ed64  call    cs:__imp_lstrlenW
0x18005ed6b  nop     dword ptr [rax+rax+00h]
0x18005ed70  cmp     eax, [r14+0Ch]
0x18005ed74  ja      loc_18005EBBE
0x18005ed7a  mov     rcx, rsi; lpString
0x18005ed7d  call    cs:__imp_lstrlenW
0x18005ed84  nop     dword ptr [rax+rax+00h]
0x18005ed89  mov     ecx, [r14+0Ch]
0x18005ed8d  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18005ed94  inc     ecx
0x18005ed96  lea     edi, [rax+1]
0x18005ed99  mov     eax, 2
0x18005ed9e  mul     rcx
0x18005eda1  cmovb   rax, rbp
0x18005eda5  mov     rcx, rax; unsigned __int64
0x18005eda8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005edad  mov     r15, rax
0x18005edb0  movsxd  rdi, edi
0x18005edb3  mov     eax, 2
0x18005edb8  mul     rdi
0x18005edbb  cmovb   rax, rbp
0x18005edbf  mov     rcx, rax; unsigned __int64
0x18005edc2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005edc7  mov     rbp, rax
0x18005edca  test    r15, r15
0x18005edcd  jz      loc_18005EBBE
0x18005edd3  test    rax, rax
0x18005edd6  jz      loc_18005EBBE
0x18005eddc  mov     edx, [r14+0Ch]
0x18005ede0  mov     r8, rbx; unsigned __int16 *
0x18005ede3  inc     edx; unsigned __int64
0x18005ede5  mov     rcx, r15; unsigned __int16 *
0x18005ede8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005eded  test    eax, eax
0x18005edef  js      short loc_18005EE6F
0x18005edf1  mov     r8, rsi; unsigned __int16 *
0x18005edf4  mov     rdx, rdi; unsigned __int64
0x18005edf7  mov     rcx, rbp; unsigned __int16 *
0x18005edfa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005edff  test    eax, eax
0x18005ee01  js      short loc_18005EE6F
0x18005ee03  mov     rcx, r15; lpsz
0x18005ee06  call    cs:__imp_CharLowerW
0x18005ee0d  nop     dword ptr [rax+rax+00h]
0x18005ee12  mov     rcx, rbp; lpsz
0x18005ee15  call    cs:__imp_CharLowerW
0x18005ee1c  nop     dword ptr [rax+rax+00h]
0x18005ee21  mov     rdx, rbp; SubStr
0x18005ee24  mov     rcx, r15; Str
0x18005ee27  call    cs:__imp_wcsstr
0x18005ee2e  nop     dword ptr [rax+rax+00h]
0x18005ee33  mov     rcx, r15; void *
0x18005ee36  mov     rdi, rax
0x18005ee39  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005ee3e  mov     rcx, rbp; void *
0x18005ee41  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005ee46  test    rdi, rdi
0x18005ee49  jnz     short loc_18005EE65
0x18005ee4b  mov     r15, [rsp+48h+arg_0]
0x18005ee50  mov     eax, edi
0x18005ee52  jmp     loc_18005EB5D
0x18005ee57  sub     rax, rbx
0x18005ee5a  sar     rax, 1
0x18005ee5d  lea     edi, [rax+1]
0x18005ee60  jmp     loc_18005EC5B
0x18005ee65  sub     rdi, r15
0x18005ee68  sar     rdi, 1
0x18005ee6b  inc     edi
0x18005ee6d  jmp     short loc_18005EE4B
0x18005ee6f  mov     rcx, r15; void *
0x18005ee72  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005ee77  mov     rcx, rbp; void *
0x18005ee7a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005ee7f  mov     r15, [rsp+48h+arg_0]
0x18005ee84  xor     eax, eax
0x18005ee86  jmp     loc_18005EB5D
0x18005ee8b  mov     [rsp+48h+cchCount2], edi; cchCount2
0x18005ee8f  mov     r9d, edi; cchCount1
0x18005ee92  mov     r8, rbx; lpString1
0x18005ee95  mov     [rsp+48h+lpString2], rsi; lpString2
0x18005ee9a  mov     edx, 1; dwCmpFlags
0x18005ee9f  mov     ecx, 400h; Locale
0x18005eea4  call    cs:__imp_CompareStringW
0x18005eeab  nop     dword ptr [rax+rax+00h]
0x18005eeb0  jmp     loc_18005ED25
```
