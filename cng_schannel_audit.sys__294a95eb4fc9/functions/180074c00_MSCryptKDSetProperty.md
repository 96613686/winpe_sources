# MSCryptKDSetProperty

- ea: `0x180074c00`
- end: `0x180074f21`
- name: `MSCryptKDSetProperty`
- size: `801`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180003f70`
- `0x180005e10`
- `0x180006470`
- `0x18000743c`
- `0x180039f20`
- `0x18003c820`
- `0x1800646f8`
- `0x180074c00`
- `0x18009d746`
- `0x18009d820`
- `0x18009da40`
- `0x18009dd40`

## string_xrefs

- `0x180074df3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180074ee4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDSetProperty(__int64 a1, const wchar_t *a2, wchar_t *a3, unsigned int a4, int a5)
{
  size_t v5; // rsi
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  int v12; // eax
  int v13; // r12d
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 SymCryptMacAlgorithm; // rax
  __int64 v17; // rdx
  void *v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rcx
  unsigned __int64 v21; // r14
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rdx
  __int64 v27; // [rsp+40h] [rbp-41h] BYREF
  _QWORD Src[8]; // [rsp+50h] [rbp-31h] BYREF

  v5 = a4;
  v27 = 0;
  memset(Src, 0, sizeof(Src));
  if ( !a1 )
  {
    v9 = -1073741816;
    v10 = 1122;
    v11 = 3221225480LL;
LABEL_45:
    DebugTraceError(
      v11,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v10);
    return v9;
  }
  if ( a5 || !a2 )
  {
    v10 = 1130;
    goto LABEL_44;
  }
  v12 = ValidateKeyDerivationKey(a1, &v27);
  v9 = v12;
  if ( v12 < 0 )
  {
    v10 = 1138;
    v11 = (unsigned int)v12;
    goto LABEL_45;
  }
  v13 = 0;
  if ( !wcscmp_0(a2, L"HkdfHashAlgorithm") )
  {
    v14 = v27;
    if ( *(_DWORD *)(v27 + 48) == 1 )
    {
      v10 = 1150;
LABEL_44:
      v9 = -1073741811;
      v11 = 3221225485LL;
      goto LABEL_45;
    }
    if ( (unsigned int)v5 < 2 )
    {
LABEL_14:
      v10 = 1159;
      goto LABEL_44;
    }
    LODWORD(v15) = (unsigned int)v5 >> 1;
    while ( 1 )
    {
      v15 = (unsigned int)(v15 - 1);
      if ( !a3[v15] )
        break;
      if ( !(_DWORD)v15 )
        goto LABEL_14;
    }
    SymCryptMacAlgorithm = GetSymCryptMacAlgorithm(a3);
    *(_QWORD *)(v14 + 72) = SymCryptMacAlgorithm;
    if ( !SymCryptMacAlgorithm )
    {
      v10 = 1171;
LABEL_17:
      v9 = -1073741637;
      v11 = 3221225659LL;
      goto LABEL_45;
    }
    v18 = (void *)MSCryptAlloc(v5, v17);
    *(_QWORD *)(v14 + 56) = v18;
    if ( !v18 )
    {
      v9 = -1073741801;
      v10 = 1179;
      v11 = 3221225495LL;
      goto LABEL_45;
    }
    memmove(v18, a3, v5);
    *(_DWORD *)(v14 + 64) = v5;
  }
  else if ( !wcscmp_0(a2, L"HkdfSaltAndFinalize") )
  {
    v19 = v27;
    if ( *(_DWORD *)(v27 + 48) == 1 || (v20 = *(_QWORD *)(v27 + 72)) == 0 )
    {
      v10 = 1205;
      goto LABEL_44;
    }
    v21 = *(_QWORD *)(v20 + 48);
    if ( (unsigned int)SymCryptHkdfExtractPrk(
                         v20,
                         *(_QWORD *)(v27 + 24),
                         *(_DWORD *)(v27 + 16),
                         (_DWORD)a3,
                         v5,
                         (__int64)Src,
                         v21) )
      return v9;
    v13 = 1;
    if ( !(unsigned int)SymCryptHkdfPrkExpandKey(v19 + 80, *(_QWORD *)(v19 + 72), Src, v21) )
    {
      if ( *(unsigned int *)(v19 + 16) < v21 )
      {
        MSCryptFree(*(PVOID *)(v19 + 24));
        v23 = MSCryptAlloc(v21, v22);
        *(_QWORD *)(v19 + 24) = v23;
        if ( !v23 )
        {
          v9 = -1073741801;
          DebugTraceError(
            3221225495LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
            1241);
LABEL_40:
          memset(Src, 0, sizeof(Src));
          return v9;
        }
      }
      memmove(*(void **)(v19 + 24), Src, v21);
      *(_DWORD *)(v19 + 16) = v21;
      *(_DWORD *)(v19 + 48) = 1;
    }
  }
  else
  {
    if ( wcscmp_0(a2, L"HkdfPrkAndFinalize") )
    {
      v10 = 1302;
      goto LABEL_17;
    }
    v24 = v27;
    if ( *(_DWORD *)(v27 + 48) == 1 || (v25 = *(_QWORD *)(v27 + 72)) == 0 || a3 || (_DWORD)v5 )
    {
      v10 = 1275;
      goto LABEL_44;
    }
    if ( (unsigned int)SymCryptHkdfPrkExpandKey(v27 + 80, v25, *(_QWORD *)(v27 + 24), *(unsigned int *)(v27 + 16)) )
    {
      v9 = -1073741823;
      v10 = 1290;
      v11 = 3221225473LL;
      goto LABEL_45;
    }
    *(_DWORD *)(v24 + 48) = 1;
  }
  v9 = 0;
  if ( v13 )
    goto LABEL_40;
  return v9;
}

```

## disassembly

```asm
0x180074c00  mov     [rsp-8+arg_0], rbx
0x180074c05  push    rbp
0x180074c06  push    rsi
0x180074c07  push    rdi
0x180074c08  push    r12
0x180074c0a  push    r13
0x180074c0c  push    r14
0x180074c0e  push    r15
0x180074c10  lea     rbp, [rsp-1Fh]
0x180074c15  sub     rsp, 0A0h
0x180074c1c  mov     rax, cs:__security_cookie
0x180074c23  xor     rax, rsp
0x180074c26  mov     [rbp+4Fh+var_40], rax
0x180074c2a  xor     r13d, r13d
0x180074c2d  mov     esi, r9d
0x180074c30  mov     r15, r8
0x180074c33  mov     [rbp+4Fh+var_90], r13
0x180074c37  mov     rdi, rdx
0x180074c3a  mov     rbx, rcx
0x180074c3d  xor     edx, edx; Val
0x180074c3f  lea     rcx, [rbp+4Fh+Src]; void *
0x180074c43  lea     r8d, [r13+40h]; Size
0x180074c47  call    memset
0x180074c4c  test    rbx, rbx
0x180074c4f  jnz     short loc_180074C66
0x180074c51  mov     ebx, 0C0000008h
0x180074c56  mov     r9d, 462h
0x180074c5c  mov     ecx, 0C0000008h
0x180074c61  jmp     loc_180074EE4
0x180074c66  cmp     [rbp+4Fh+arg_20], r13d
0x180074c6a  jnz     loc_180074ED4
0x180074c70  test    rdi, rdi
0x180074c73  jz      loc_180074ED4
0x180074c79  lea     rdx, [rbp+4Fh+var_90]
0x180074c7d  mov     rcx, rbx
0x180074c80  call    ValidateKeyDerivationKey
0x180074c85  mov     ebx, eax
0x180074c87  test    eax, eax
0x180074c89  jns     short loc_180074C98
0x180074c8b  mov     r9d, 472h
0x180074c91  mov     ecx, eax
0x180074c93  jmp     loc_180074EE4
0x180074c98  lea     rdx, aHkdfhashalgori; "HkdfHashAlgorithm"
0x180074c9f  mov     rcx, rdi; Str1
0x180074ca2  mov     r12d, r13d
0x180074ca5  call    wcscmp_0
0x180074caa  test    eax, eax
0x180074cac  jnz     loc_180074D4A
0x180074cb2  mov     rbx, [rbp+4Fh+var_90]
0x180074cb6  cmp     dword ptr [rbx+30h], 1
0x180074cba  jnz     short loc_180074CC7
0x180074cbc  mov     r9d, 47Eh
0x180074cc2  jmp     loc_180074EDA
0x180074cc7  cmp     esi, 2
0x180074cca  jb      short loc_180074CDD
0x180074ccc  mov     ecx, esi
0x180074cce  shr     ecx, 1
0x180074cd0  dec     ecx
0x180074cd2  cmp     [r15+rcx*2], r13w
0x180074cd7  jz      short loc_180074CE8
0x180074cd9  test    ecx, ecx
0x180074cdb  jnz     short loc_180074CD0
0x180074cdd  mov     r9d, 487h
0x180074ce3  jmp     loc_180074EDA
0x180074ce8  mov     rcx, r15; Str1
0x180074ceb  call    GetSymCryptMacAlgorithm
0x180074cf0  mov     [rbx+48h], rax
0x180074cf4  test    rax, rax
0x180074cf7  jnz     short loc_180074D0E
0x180074cf9  mov     r9d, 493h
0x180074cff  mov     ebx, 0C00000BBh
0x180074d04  mov     ecx, 0C00000BBh
0x180074d09  jmp     loc_180074EE4
0x180074d0e  mov     rcx, rsi
0x180074d11  call    MSCryptAlloc
0x180074d16  mov     [rbx+38h], rax
0x180074d1a  test    rax, rax
0x180074d1d  jnz     short loc_180074D34
0x180074d1f  mov     ebx, 0C0000017h
0x180074d24  mov     r9d, 49Bh
0x180074d2a  mov     ecx, 0C0000017h
0x180074d2f  jmp     loc_180074EE4
0x180074d34  mov     r8, rsi; Size
0x180074d37  mov     rdx, r15; Src
0x180074d3a  mov     rcx, rax; void *
0x180074d3d  call    memmove
0x180074d42  mov     [rbx+40h], esi
0x180074d45  jmp     loc_180074E97
0x180074d4a  lea     rdx, aHkdfsaltandfin; "HkdfSaltAndFinalize"
0x180074d51  mov     rcx, rdi; Str1
0x180074d54  call    wcscmp_0
0x180074d59  test    eax, eax
0x180074d5b  jnz     loc_180074E3A
0x180074d61  mov     rdi, [rbp+4Fh+var_90]
0x180074d65  cmp     dword ptr [rdi+30h], 1
0x180074d69  jz      loc_180074E2F
0x180074d6f  mov     rcx, [rdi+48h]
0x180074d73  test    rcx, rcx
0x180074d76  jz      loc_180074E2F
0x180074d7c  mov     r14, [rcx+30h]
0x180074d80  lea     rdx, [rbp+4Fh+Src]
0x180074d84  mov     r8d, [rdi+10h]
0x180074d88  mov     r9, r15
0x180074d8b  mov     [rsp+0D0h+var_A0], r14
0x180074d90  mov     [rsp+0D0h+var_A8], rdx
0x180074d95  mov     rdx, [rdi+18h]
0x180074d99  mov     [rsp+0D0h+var_B0], rsi
0x180074d9e  call    SymCryptHkdfExtractPrk
0x180074da3  test    eax, eax
0x180074da5  jnz     loc_180074EF7
0x180074dab  mov     rdx, [rdi+48h]
0x180074daf  lea     rcx, [rdi+50h]
0x180074db3  mov     r9, r14
0x180074db6  lea     r8, [rbp+4Fh+Src]
0x180074dba  lea     r12d, [rax+1]
0x180074dbe  call    SymCryptHkdfPrkExpandKey
0x180074dc3  test    eax, eax
0x180074dc5  jnz     loc_180074E97
0x180074dcb  mov     eax, [rdi+10h]
0x180074dce  cmp     rax, r14
0x180074dd1  jnb     short loc_180074E15
0x180074dd3  mov     rcx, [rdi+18h]; P
0x180074dd7  call    MSCryptFree
0x180074ddc  mov     rcx, r14
0x180074ddf  call    MSCryptAlloc
0x180074de4  mov     [rdi+18h], rax
0x180074de8  test    rax, rax
0x180074deb  jnz     short loc_180074E15
0x180074ded  mov     r9d, 4D9h
0x180074df3  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180074dfa  lea     rdx, aStatus; "Status"
0x180074e01  mov     ecx, 0C0000017h
0x180074e06  mov     ebx, 0C0000017h
0x180074e0b  call    DebugTraceError
0x180074e10  jmp     loc_180074E9F
0x180074e15  mov     rcx, [rdi+18h]; void *
0x180074e19  lea     rdx, [rbp+4Fh+Src]; Src
0x180074e1d  mov     r8, r14; Size
0x180074e20  call    memmove
0x180074e25  mov     [rdi+10h], r14d
0x180074e29  mov     [rdi+30h], r12d
0x180074e2d  jmp     short loc_180074E97
0x180074e2f  mov     r9d, 4B5h
0x180074e35  jmp     loc_180074EDA
0x180074e3a  lea     rdx, aHkdfprkandfina; "HkdfPrkAndFinalize"
0x180074e41  mov     rcx, rdi; Str1
0x180074e44  call    wcscmp_0
0x180074e49  test    eax, eax
0x180074e4b  jnz     short loc_180074EC9
0x180074e4d  mov     rbx, [rbp+4Fh+var_90]
0x180074e51  cmp     dword ptr [rbx+30h], 1
0x180074e55  jz      short loc_180074EC1
0x180074e57  mov     rdx, [rbx+48h]
0x180074e5b  test    rdx, rdx
0x180074e5e  jz      short loc_180074EC1
0x180074e60  test    r15, r15
0x180074e63  jnz     short loc_180074EC1
0x180074e65  test    esi, esi
0x180074e67  jnz     short loc_180074EC1
0x180074e69  mov     r9d, [rbx+10h]
0x180074e6d  lea     rcx, [rbx+50h]
0x180074e71  mov     r8, [rbx+18h]
0x180074e75  call    SymCryptHkdfPrkExpandKey
0x180074e7a  test    eax, eax
0x180074e7c  jz      short loc_180074E90
0x180074e7e  mov     ebx, 0C0000001h
0x180074e83  mov     r9d, 50Ah
0x180074e89  mov     ecx, 0C0000001h
0x180074e8e  jmp     short loc_180074EE4
0x180074e90  mov     dword ptr [rbx+30h], 1
0x180074e97  mov     ebx, r13d
0x180074e9a  test    r12d, r12d
0x180074e9d  jz      short loc_180074EF7
0x180074e9f  mov     [rbp+4Fh+Src], r13
0x180074ea3  mov     [rbp+4Fh+var_78], r13
0x180074ea7  mov     [rbp+4Fh+var_70], r13
0x180074eab  mov     [rbp+4Fh+var_68], r13
0x180074eaf  mov     [rbp+4Fh+var_60], r13
0x180074eb3  mov     [rbp+4Fh+var_58], r13
0x180074eb7  mov     [rbp+4Fh+var_50], r13
0x180074ebb  mov     [rbp+4Fh+var_48], r13
0x180074ebf  jmp     short loc_180074EF7
0x180074ec1  mov     r9d, 4FBh
0x180074ec7  jmp     short loc_180074EDA
0x180074ec9  mov     r9d, 516h
0x180074ecf  jmp     loc_180074CFF
0x180074ed4  mov     r9d, 46Ah
0x180074eda  mov     ebx, 0C000000Dh
0x180074edf  mov     ecx, 0C000000Dh
0x180074ee4  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180074eeb  lea     rdx, aStatus; "Status"
0x180074ef2  call    DebugTraceError
0x180074ef7  mov     eax, ebx
0x180074ef9  mov     rcx, [rbp+4Fh+var_40]
0x180074efd  xor     rcx, rsp; StackCookie
0x180074f00  call    __security_check_cookie
0x180074f05  mov     rbx, [rsp+0D0h+arg_0]
0x180074f0d  add     rsp, 0A0h
0x180074f14  pop     r15
0x180074f16  pop     r14
0x180074f18  pop     r13
0x180074f1a  pop     r12
0x180074f1c  pop     rdi
0x180074f1d  pop     rsi
0x180074f1e  pop     rbp
0x180074f1f  retn
```
