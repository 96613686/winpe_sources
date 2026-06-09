# MSCryptImportDHKeyPair

- ea: `0x180085b20`
- end: `0x180085ee5`
- name: `MSCryptImportDHKeyPair`
- size: `965`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x18004b628`
- `0x180051dd0`
- `0x180052e18`
- `0x180085b20`
- `0x180086450`
- `0x180097824`
- `0x1800978e0`
- `0x18009810c`
- `0x1800985d4`
- `0x180098938`
- `0x180099dd0`
- `0x1800a4232`

## string_xrefs

- `0x180085bd0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`
- `0x180085e91`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall MSCryptImportDHKeyPair(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        __int64 *a4,
        _DWORD *a5,
        int a6,
        unsigned int a7)
{
  int v10; // eax
  __int64 v11; // rbx
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // r15d
  int v17; // ebp
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rax
  __int64 v23; // rdx
  char *v24; // r14
  unsigned int v25; // eax
  __int64 v26; // rdx
  char *v27; // rbp
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r10
  int v31; // r13d
  __int64 v32; // r14
  int v33; // eax
  __int64 v34; // rcx
  int v35; // r15d
  __int64 v36; // rdx
  int v37; // esi
  __int64 v38; // rax
  unsigned int v39; // eax
  int v40; // [rsp+20h] [rbp-A8h]
  int v41; // [rsp+70h] [rbp-58h] BYREF
  __int64 v42[10]; // [rsp+78h] [rbp-50h] BYREF
  int v43; // [rsp+F8h] [rbp+30h]

  v41 = 0;
  v42[0] = 0;
  if ( (a7 & 0xFFFFFFC7) != 0 )
    return 3221225485LL;
  if ( a2 )
    return 3221225659LL;
  if ( !a1 || !a3 || !a4 || !a5 || !a6 )
  {
    v19 = 0;
    v21 = 1419;
    goto LABEL_48;
  }
  v10 = ValidateDHAlgorithm(a1, 0, &v41, v42);
  LODWORD(v11) = v10;
  if ( v10 >= 0 )
  {
    if ( !wcscmp_0(a3, L"DHPUBLICBLOB") || !wcscmp_0(a3, L"PUBLICBLOB") )
    {
      if ( *a5 != 1112557636 )
      {
        v12 = 1442;
        goto LABEL_18;
      }
      v15 = 3;
      v16 = 0;
    }
    else
    {
      if ( wcscmp_0(a3, L"DHPRIVATEBLOB") && wcscmp_0(a3, L"PRIVATEBLOB") )
      {
        v12 = 1463;
LABEL_18:
        LODWORD(v11) = -1073741811;
        v13 = 3221225485LL;
        goto LABEL_12;
      }
      if ( *a5 != 1448101956 )
      {
        v12 = 1454;
        goto LABEL_18;
      }
      v15 = 4;
      v16 = 1;
    }
    v17 = a5[1];
    if ( a6 != (unsigned int)(v17 * v15) + 8LL || (unsigned int)(v17 - 64) > 0x1C0 )
    {
      v12 = 1476;
      goto LABEL_18;
    }
    v18 = MSCryptAlloc(40, v14);
    v19 = v18;
    if ( !v18 )
    {
      LODWORD(v11) = -1073741801;
      v20 = 3221225495LL;
      v21 = 1489;
      goto LABEL_49;
    }
    *(_QWORD *)(v18 + 8) = 0;
    *(_QWORD *)(v18 + 16) = 0;
    *(_QWORD *)(v18 + 24) = 0;
    *(_QWORD *)(v18 + 32) = 0;
    *(_DWORD *)v18 = 40;
    *(_DWORD *)(v18 + 4) = 1297304409;
    *(_DWORD *)(v18 + 8) = *(_DWORD *)(v42[0] + 8);
    *(_DWORD *)(v18 + 12) = v17;
    v22 = SymCryptDlgroupAllocate((unsigned int)(8 * v17), 0);
    *(_QWORD *)(v19 + 24) = v22;
    if ( !v22 )
    {
      LODWORD(v11) = -1073741801;
      v20 = 3221225495LL;
      v21 = 1508;
      goto LABEL_49;
    }
    v23 = *(unsigned int *)(v19 + 12);
    v24 = (char *)a5 + v23 + 8;
    v25 = SymCryptDlgroupSetValue(
            (int)a5 + 8,
            v23,
            0,
            0,
            (int)v23 + (int)a5 + 8,
            *(_DWORD *)(v19 + 12),
            2,
            0,
            0,
            0,
            0,
            0,
            v22);
    if ( v25 )
    {
      v11 = (unsigned int)SymcryptErrorCodeToNtStatus(v25);
      v20 = v11;
      v21 = 1532;
      goto LABEL_49;
    }
    v26 = *(unsigned int *)(v19 + 12);
    *(_DWORD *)(v19 + 16) |= 2u;
    v27 = 0;
    v28 = IsAllZeros((char *)a5 + (unsigned int)(2 * v26) + 8, v26);
    if ( !v28 )
      v27 = &v24[v29];
    v31 = v29;
    if ( v28 )
      v31 = 0;
    v43 = v16 != 0 ? v29 : 0;
    v32 = (unsigned __int64)&v24[v30] & -(__int64)(v16 != 0);
    if ( (a7 & 0x20) == 0 || v32 && v27 )
    {
      v33 = BCryptFlagsToSymCryptKeyValidationFlags(a7);
      v34 = *(_QWORD *)(v19 + 24);
      v35 = v33;
      LOBYTE(v36) = -*(_BYTE *)(v34 + 40);
      v37 = *(_BYTE *)(v34 + 40) != 0 ? 0x2000 : 8448;
      v38 = SymCryptDlkeyAllocate(v34, v36);
      *(_QWORD *)(v19 + 32) = v38;
      if ( v38 )
      {
        v39 = SymCryptDlkeySetValue(v32, v43, (_DWORD)v27, v31, v40, v35 | (unsigned int)v37, v38);
        if ( !v39 )
        {
          *(_DWORD *)(v19 + 16) |= 1u;
          *a4 = v19;
          return (unsigned int)v11;
        }
        v11 = (unsigned int)SymcryptErrorCodeToNtStatus(v39);
        v20 = v11;
        v21 = 1593;
      }
      else
      {
        LODWORD(v11) = -1073741801;
        v20 = 3221225495LL;
        v21 = 1578;
      }
LABEL_49:
      DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v21);
      if ( v19 )
      {
        if ( *(_QWORD *)(v19 + 32) )
        {
          SymCryptDlkeyFree();
          *(_QWORD *)(v19 + 32) = 0;
        }
        if ( *(_QWORD *)(v19 + 24) )
        {
          SymCryptMlDsaTemporariesFree();
          *(_QWORD *)(v19 + 24) = 0;
        }
        MSCryptFree((PVOID)v19);
      }
      return (unsigned int)v11;
    }
    v21 = 1559;
LABEL_48:
    v20 = 3221225485LL;
    LODWORD(v11) = -1073741811;
    goto LABEL_49;
  }
  v12 = 1426;
  v13 = (unsigned int)v10;
LABEL_12:
  DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v12);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180085b20  push    rbx
0x180085b22  push    rbp
0x180085b23  push    rsi
0x180085b24  push    rdi
0x180085b25  push    r12
0x180085b27  push    r13
0x180085b29  push    r14
0x180085b2b  push    r15
0x180085b2d  sub     rsp, 88h
0x180085b34  xor     r13d, r13d
0x180085b37  mov     r12, r9
0x180085b3a  test    [rsp+0C8h+arg_30], 0FFFFFFC7h
0x180085b45  mov     rdi, r8
0x180085b48  mov     [rsp+0C8h+var_58], r13d
0x180085b4d  mov     [rsp+0C8h+var_50], r13
0x180085b52  jz      short loc_180085B5E
0x180085b54  mov     eax, 0C000000Dh
0x180085b59  jmp     loc_180085ED0
0x180085b5e  test    rdx, rdx
0x180085b61  jz      short loc_180085B6D
0x180085b63  mov     eax, 0C00000BBh
0x180085b68  jmp     loc_180085ED0
0x180085b6d  test    rcx, rcx
0x180085b70  jz      loc_180085E77
0x180085b76  test    rdi, rdi
0x180085b79  jz      loc_180085E77
0x180085b7f  test    r12, r12
0x180085b82  jz      loc_180085E77
0x180085b88  mov     rsi, [rsp+0C8h+arg_20]
0x180085b90  test    rsi, rsi
0x180085b93  jz      loc_180085E77
0x180085b99  mov     r14d, [rsp+0C8h+arg_28]
0x180085ba1  test    r14d, r14d
0x180085ba4  jz      loc_180085E77
0x180085baa  lea     r9, [rsp+0C8h+var_50]
0x180085baf  xor     edx, edx
0x180085bb1  lea     r8, [rsp+0C8h+var_58]
0x180085bb6  call    ValidateDHAlgorithm
0x180085bbb  mov     ebx, eax
0x180085bbd  test    eax, eax
0x180085bbf  jns     short loc_180085BE1
0x180085bc1  mov     r9d, 592h
0x180085bc7  mov     ecx, eax
0x180085bc9  lea     rdx, aStatus; "Status"
0x180085bd0  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180085bd7  call    DebugTraceError
0x180085bdc  jmp     loc_180085ECE
0x180085be1  lea     rdx, aDhpublicblob; "DHPUBLICBLOB"
0x180085be8  mov     rcx, rdi; Str1
0x180085beb  call    wcscmp_0
0x180085bf0  test    eax, eax
0x180085bf2  jz      short loc_180085C5A
0x180085bf4  lea     rdx, aPublicblob; "PUBLICBLOB"
0x180085bfb  mov     rcx, rdi; Str1
0x180085bfe  call    wcscmp_0
0x180085c03  test    eax, eax
0x180085c05  jz      short loc_180085C5A
0x180085c07  lea     rdx, aDhprivateblob; "DHPRIVATEBLOB"
0x180085c0e  mov     rcx, rdi; Str1
0x180085c11  call    wcscmp_0
0x180085c16  test    eax, eax
0x180085c18  jz      short loc_180085C3F
0x180085c1a  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x180085c21  mov     rcx, rdi; Str1
0x180085c24  call    wcscmp_0
0x180085c29  test    eax, eax
0x180085c2b  jz      short loc_180085C3F
0x180085c2d  mov     r9d, 5B7h
0x180085c33  mov     ebx, 0C000000Dh
0x180085c38  mov     ecx, 0C000000Dh
0x180085c3d  jmp     short loc_180085BC9
0x180085c3f  cmp     dword ptr [rsi], 56504844h
0x180085c45  jz      short loc_180085C4F
0x180085c47  mov     r9d, 5AEh
0x180085c4d  jmp     short loc_180085C33
0x180085c4f  mov     ecx, 4
0x180085c54  lea     r15d, [rcx-3]
0x180085c58  jmp     short loc_180085C72
0x180085c5a  cmp     dword ptr [rsi], 42504844h
0x180085c60  jz      short loc_180085C6A
0x180085c62  mov     r9d, 5A2h
0x180085c68  jmp     short loc_180085C33
0x180085c6a  mov     ecx, 3
0x180085c6f  mov     r15d, r13d
0x180085c72  mov     ebp, [rsi+4]
0x180085c75  imul    ecx, ebp
0x180085c78  add     rcx, 8
0x180085c7c  cmp     r14, rcx
0x180085c7f  jnz     loc_180085E6C
0x180085c85  lea     eax, [rbp-40h]
0x180085c88  cmp     eax, 1C0h
0x180085c8d  ja      loc_180085E6C
0x180085c93  mov     r14d, 28h ; '('
0x180085c99  mov     ecx, r14d
0x180085c9c  call    MSCryptAlloc
0x180085ca1  mov     rdi, rax
0x180085ca4  test    rax, rax
0x180085ca7  jnz     short loc_180085CBE
0x180085ca9  mov     ebx, 0C0000017h
0x180085cae  mov     ecx, 0C0000017h
0x180085cb3  mov     r9d, 5D1h
0x180085cb9  jmp     loc_180085E8A
0x180085cbe  mov     [rax+8], r13
0x180085cc2  xor     edx, edx
0x180085cc4  mov     [rax+10h], r13
0x180085cc8  mov     [rax+18h], r13
0x180085ccc  mov     [rax+20h], r13
0x180085cd0  mov     [rax], r14d
0x180085cd3  mov     dword ptr [rax+4], 4D534B59h
0x180085cda  mov     rax, [rsp+0C8h+var_50]
0x180085cdf  mov     ecx, [rax+8]
0x180085ce2  mov     [rdi+8], ecx
0x180085ce5  lea     ecx, ds:0[rbp*8]
0x180085cec  mov     [rdi+0Ch], ebp
0x180085cef  call    SymCryptDlgroupAllocate
0x180085cf4  mov     [rdi+18h], rax
0x180085cf8  test    rax, rax
0x180085cfb  jnz     short loc_180085D12
0x180085cfd  mov     ebx, 0C0000017h
0x180085d02  mov     ecx, 0C0000017h
0x180085d07  mov     r9d, 5E4h
0x180085d0d  jmp     loc_180085E8A
0x180085d12  mov     edx, [rdi+0Ch]; int
0x180085d15  lea     rcx, [rsi+8]; int
0x180085d19  mov     [rsp+0C8h+var_68], rax; __int64
0x180085d1e  xor     r9d, r9d; int
0x180085d21  mov     [rsp+0C8h+var_70], r13d; int
0x180085d26  xor     r8d, r8d; int
0x180085d29  mov     [rsp+0C8h+var_78], r13d; int
0x180085d2e  mov     [rsp+0C8h+Size], r13; Size
0x180085d33  lea     r14, [rdx+rcx]
0x180085d37  mov     [rsp+0C8h+var_88], r13; __int64
0x180085d3c  mov     [rsp+0C8h+var_90], r13; __int64
0x180085d41  mov     [rsp+0C8h+var_98], 2; int
0x180085d49  mov     qword ptr [rsp+0C8h+var_A0], rdx; int
0x180085d4e  mov     qword ptr [rsp+0C8h+var_A8], r14; int
0x180085d53  call    SymCryptDlgroupSetValue
0x180085d58  test    eax, eax
0x180085d5a  jz      short loc_180085D72
0x180085d5c  mov     ecx, eax
0x180085d5e  call    SymcryptErrorCodeToNtStatus
0x180085d63  mov     ebx, eax
0x180085d65  mov     ecx, eax
0x180085d67  mov     r9d, 5FCh
0x180085d6d  jmp     loc_180085E8A
0x180085d72  mov     edx, [rdi+0Ch]
0x180085d75  lea     rcx, [rsi+8]
0x180085d79  or      dword ptr [rdi+10h], 2
0x180085d7d  mov     rbp, r13
0x180085d80  lea     r10d, [rdx+rdx]
0x180085d84  add     rcx, r10
0x180085d87  call    IsAllZeros
0x180085d8c  test    eax, eax
0x180085d8e  jnz     short loc_180085D94
0x180085d90  lea     rbp, [r14+rdx]
0x180085d94  xor     ecx, ecx
0x180085d96  mov     r13d, edx
0x180085d99  test    eax, eax
0x180085d9b  mov     eax, r15d
0x180085d9e  cmovnz  r13d, ecx
0x180085da2  neg     eax
0x180085da4  sbb     eax, eax
0x180085da6  and     eax, edx
0x180085da8  neg     r15d
0x180085dab  mov     [rsp+0C8h+arg_28], eax
0x180085db2  lea     rax, [r10+r14]
0x180085db6  sbb     r14, r14
0x180085db9  and     r14, rax
0x180085dbc  test    byte ptr [rsp+0C8h+arg_30], 20h
0x180085dc4  jz      short loc_180085DDE
0x180085dc6  test    r14, r14
0x180085dc9  jz      short loc_180085DD0
0x180085dcb  test    rbp, rbp
0x180085dce  jnz     short loc_180085DDE
0x180085dd0  mov     r9d, 617h
0x180085dd6  xor     r13d, r13d
0x180085dd9  jmp     loc_180085E80
0x180085dde  mov     ecx, [rsp+0C8h+arg_30]
0x180085de5  call    BCryptFlagsToSymCryptKeyValidationFlags
0x180085dea  mov     rcx, [rdi+18h]
0x180085dee  mov     r15d, eax
0x180085df1  mov     dl, [rcx+28h]
0x180085df4  neg     dl
0x180085df6  sbb     esi, esi
0x180085df8  and     esi, 0FFFFFF00h
0x180085dfe  add     esi, 2100h
0x180085e04  call    SymCryptDlkeyAllocate
0x180085e09  mov     [rdi+20h], rax
0x180085e0d  test    rax, rax
0x180085e10  jnz     short loc_180085E27
0x180085e12  mov     ebx, 0C0000017h
0x180085e17  mov     ecx, 0C0000017h
0x180085e1c  mov     r9d, 62Ah
0x180085e22  xor     r13d, r13d
0x180085e25  jmp     short loc_180085E8A
0x180085e27  mov     edx, [rsp+0C8h+arg_28]
0x180085e2e  or      esi, r15d
0x180085e31  mov     qword ptr [rsp+0C8h+var_98], rax
0x180085e36  mov     r8, rbp
0x180085e39  mov     r9d, r13d
0x180085e3c  mov     rcx, r14
0x180085e3f  mov     [rsp+0C8h+var_A0], esi
0x180085e43  call    SymCryptDlkeySetValue
0x180085e48  xor     r13d, r13d
0x180085e4b  test    eax, eax
0x180085e4d  jz      short loc_180085E62
0x180085e4f  mov     ecx, eax
0x180085e51  call    SymcryptErrorCodeToNtStatus
0x180085e56  mov     ebx, eax
0x180085e58  mov     ecx, eax
0x180085e5a  mov     r9d, 639h
0x180085e60  jmp     short loc_180085E8A
0x180085e62  or      dword ptr [rdi+10h], 1
0x180085e66  mov     [r12], rdi
0x180085e6a  jmp     short loc_180085ECE
0x180085e6c  mov     r9d, 5C4h
0x180085e72  jmp     loc_180085C33
0x180085e77  mov     rdi, r13
0x180085e7a  mov     r9d, 58Bh
0x180085e80  mov     ecx, 0C000000Dh
0x180085e85  mov     ebx, 0C000000Dh
0x180085e8a  lea     rdx, aStatus; "Status"
0x180085e91  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180085e98  call    DebugTraceError
0x180085e9d  test    rdi, rdi
0x180085ea0  jz      short loc_180085ECE
0x180085ea2  mov     rcx, [rdi+20h]
0x180085ea6  test    rcx, rcx
0x180085ea9  jz      short loc_180085EB4
0x180085eab  call    SymCryptDlkeyFree
0x180085eb0  mov     [rdi+20h], r13
0x180085eb4  mov     rcx, [rdi+18h]
0x180085eb8  test    rcx, rcx
0x180085ebb  jz      short loc_180085EC6
0x180085ebd  call    SymCryptMlDsaTemporariesFree
0x180085ec2  mov     [rdi+18h], r13
0x180085ec6  mov     rcx, rdi; P
0x180085ec9  call    MSCryptFree
0x180085ece  mov     eax, ebx
0x180085ed0  add     rsp, 88h
0x180085ed7  pop     r15
0x180085ed9  pop     r14
0x180085edb  pop     r13
0x180085edd  pop     r12
0x180085edf  pop     rdi
0x180085ee0  pop     rsi
0x180085ee1  pop     rbp
0x180085ee2  pop     rbx
0x180085ee3  retn
```
