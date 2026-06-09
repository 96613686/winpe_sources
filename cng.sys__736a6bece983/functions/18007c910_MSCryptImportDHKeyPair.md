# MSCryptImportDHKeyPair

- ea: `0x18007c910`
- end: `0x18007ccd5`
- name: `MSCryptImportDHKeyPair`
- size: `965`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x1800421d8`
- `0x180048770`
- `0x1800497b8`
- `0x18007c910`
- `0x18007d240`
- `0x180090cb0`
- `0x180090d6c`
- `0x180091598`
- `0x180091a60`
- `0x180091dc4`
- `0x18009325c`
- `0x18009f616`

## string_xrefs

- `0x18007c9c0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`
- `0x18007cc81`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

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
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // ecx
  int v18; // r15d
  int v19; // ebp
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rcx
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rdx
  char *v26; // r14
  unsigned int v27; // eax
  __int64 v28; // rdx
  char *v29; // rbp
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r10
  int v33; // r13d
  __int64 v34; // r14
  int v35; // eax
  __int64 v36; // rcx
  int v37; // r15d
  __int64 v38; // rdx
  int v39; // esi
  __int64 v40; // rax
  unsigned int v41; // eax
  int v42; // [rsp+20h] [rbp-A8h]
  int v43; // [rsp+70h] [rbp-58h] BYREF
  __int64 v44[10]; // [rsp+78h] [rbp-50h] BYREF
  int v45; // [rsp+F8h] [rbp+30h]

  v43 = 0;
  v44[0] = 0;
  if ( (a7 & 0xFFFFFFC7) != 0 )
    return 3221225485LL;
  if ( a2 )
    return 3221225659LL;
  if ( !a1 || !a3 || !a4 || !a5 || !a6 )
  {
    v21 = 0;
    v23 = 1419;
    goto LABEL_48;
  }
  v10 = ValidateDHAlgorithm(a1, 0, &v43, v44);
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
      v17 = 3;
      v18 = 0;
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
      v17 = 4;
      v18 = 1;
    }
    v19 = a5[1];
    if ( a6 != (unsigned int)(v19 * v17) + 8LL || (unsigned int)(v19 - 64) > 0x1C0 )
    {
      v12 = 1476;
      goto LABEL_18;
    }
    v20 = MSCryptAlloc(40, v14, v15, v16);
    v21 = v20;
    if ( !v20 )
    {
      LODWORD(v11) = -1073741801;
      v22 = 3221225495LL;
      v23 = 1489;
      goto LABEL_49;
    }
    *(_QWORD *)(v20 + 8) = 0;
    *(_QWORD *)(v20 + 16) = 0;
    *(_QWORD *)(v20 + 24) = 0;
    *(_QWORD *)(v20 + 32) = 0;
    *(_DWORD *)v20 = 40;
    *(_DWORD *)(v20 + 4) = 1297304409;
    *(_DWORD *)(v20 + 8) = *(_DWORD *)(v44[0] + 8);
    *(_DWORD *)(v20 + 12) = v19;
    v24 = SymCryptDlgroupAllocate((unsigned int)(8 * v19), 0);
    *(_QWORD *)(v21 + 24) = v24;
    if ( !v24 )
    {
      LODWORD(v11) = -1073741801;
      v22 = 3221225495LL;
      v23 = 1508;
      goto LABEL_49;
    }
    v25 = *(unsigned int *)(v21 + 12);
    v26 = (char *)a5 + v25 + 8;
    v27 = SymCryptDlgroupSetValue(
            (int)a5 + 8,
            v25,
            0,
            0,
            (int)v25 + (int)a5 + 8,
            *(_DWORD *)(v21 + 12),
            2,
            0,
            0,
            0,
            0,
            0,
            v24);
    if ( v27 )
    {
      v11 = (unsigned int)SymcryptErrorCodeToNtStatus(v27);
      v22 = v11;
      v23 = 1532;
      goto LABEL_49;
    }
    v28 = *(unsigned int *)(v21 + 12);
    *(_DWORD *)(v21 + 16) |= 2u;
    v29 = 0;
    v30 = IsAllZeros((char *)a5 + (unsigned int)(2 * v28) + 8, v28);
    if ( !v30 )
      v29 = &v26[v31];
    v33 = v31;
    if ( v30 )
      v33 = 0;
    v45 = v18 != 0 ? v31 : 0;
    v34 = (unsigned __int64)&v26[v32] & -(__int64)(v18 != 0);
    if ( (a7 & 0x20) == 0 || v34 && v29 )
    {
      v35 = BCryptFlagsToSymCryptKeyValidationFlags(a7);
      v36 = *(_QWORD *)(v21 + 24);
      v37 = v35;
      LOBYTE(v38) = -*(_BYTE *)(v36 + 40);
      v39 = *(_BYTE *)(v36 + 40) != 0 ? 0x2000 : 8448;
      v40 = SymCryptDlkeyAllocate(v36, v38);
      *(_QWORD *)(v21 + 32) = v40;
      if ( v40 )
      {
        v41 = SymCryptDlkeySetValue(v34, v45, (_DWORD)v29, v33, v42, v37 | (unsigned int)v39, v40);
        if ( !v41 )
        {
          *(_DWORD *)(v21 + 16) |= 1u;
          *a4 = v21;
          return (unsigned int)v11;
        }
        v11 = (unsigned int)SymcryptErrorCodeToNtStatus(v41);
        v22 = v11;
        v23 = 1593;
      }
      else
      {
        LODWORD(v11) = -1073741801;
        v22 = 3221225495LL;
        v23 = 1578;
      }
LABEL_49:
      DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v23);
      if ( v21 )
      {
        if ( *(_QWORD *)(v21 + 32) )
        {
          SymCryptDlkeyFree();
          *(_QWORD *)(v21 + 32) = 0;
        }
        if ( *(_QWORD *)(v21 + 24) )
        {
          SymCryptMlDsaTemporariesFree();
          *(_QWORD *)(v21 + 24) = 0;
        }
        MSCryptFree((PVOID)v21);
      }
      return (unsigned int)v11;
    }
    v23 = 1559;
LABEL_48:
    v22 = 3221225485LL;
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
0x18007c910  push    rbx
0x18007c912  push    rbp
0x18007c913  push    rsi
0x18007c914  push    rdi
0x18007c915  push    r12
0x18007c917  push    r13
0x18007c919  push    r14
0x18007c91b  push    r15
0x18007c91d  sub     rsp, 88h
0x18007c924  xor     r13d, r13d
0x18007c927  mov     r12, r9
0x18007c92a  test    [rsp+0C8h+arg_30], 0FFFFFFC7h
0x18007c935  mov     rdi, r8
0x18007c938  mov     [rsp+0C8h+var_58], r13d
0x18007c93d  mov     [rsp+0C8h+var_50], r13
0x18007c942  jz      short loc_18007C94E
0x18007c944  mov     eax, 0C000000Dh
0x18007c949  jmp     loc_18007CCC0
0x18007c94e  test    rdx, rdx
0x18007c951  jz      short loc_18007C95D
0x18007c953  mov     eax, 0C00000BBh
0x18007c958  jmp     loc_18007CCC0
0x18007c95d  test    rcx, rcx
0x18007c960  jz      loc_18007CC67
0x18007c966  test    rdi, rdi
0x18007c969  jz      loc_18007CC67
0x18007c96f  test    r12, r12
0x18007c972  jz      loc_18007CC67
0x18007c978  mov     rsi, [rsp+0C8h+arg_20]
0x18007c980  test    rsi, rsi
0x18007c983  jz      loc_18007CC67
0x18007c989  mov     r14d, [rsp+0C8h+arg_28]
0x18007c991  test    r14d, r14d
0x18007c994  jz      loc_18007CC67
0x18007c99a  lea     r9, [rsp+0C8h+var_50]
0x18007c99f  xor     edx, edx
0x18007c9a1  lea     r8, [rsp+0C8h+var_58]
0x18007c9a6  call    ValidateDHAlgorithm
0x18007c9ab  mov     ebx, eax
0x18007c9ad  test    eax, eax
0x18007c9af  jns     short loc_18007C9D1
0x18007c9b1  mov     r9d, 592h
0x18007c9b7  mov     ecx, eax
0x18007c9b9  lea     rdx, aStatus; "Status"
0x18007c9c0  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007c9c7  call    DebugTraceError
0x18007c9cc  jmp     loc_18007CCBE
0x18007c9d1  lea     rdx, aDhpublicblob; "DHPUBLICBLOB"
0x18007c9d8  mov     rcx, rdi; Str1
0x18007c9db  call    wcscmp_0
0x18007c9e0  test    eax, eax
0x18007c9e2  jz      short loc_18007CA4A
0x18007c9e4  lea     rdx, aPublicblob; "PUBLICBLOB"
0x18007c9eb  mov     rcx, rdi; Str1
0x18007c9ee  call    wcscmp_0
0x18007c9f3  test    eax, eax
0x18007c9f5  jz      short loc_18007CA4A
0x18007c9f7  lea     rdx, aDhprivateblob; "DHPRIVATEBLOB"
0x18007c9fe  mov     rcx, rdi; Str1
0x18007ca01  call    wcscmp_0
0x18007ca06  test    eax, eax
0x18007ca08  jz      short loc_18007CA2F
0x18007ca0a  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x18007ca11  mov     rcx, rdi; Str1
0x18007ca14  call    wcscmp_0
0x18007ca19  test    eax, eax
0x18007ca1b  jz      short loc_18007CA2F
0x18007ca1d  mov     r9d, 5B7h
0x18007ca23  mov     ebx, 0C000000Dh
0x18007ca28  mov     ecx, 0C000000Dh
0x18007ca2d  jmp     short loc_18007C9B9
0x18007ca2f  cmp     dword ptr [rsi], 56504844h
0x18007ca35  jz      short loc_18007CA3F
0x18007ca37  mov     r9d, 5AEh
0x18007ca3d  jmp     short loc_18007CA23
0x18007ca3f  mov     ecx, 4
0x18007ca44  lea     r15d, [rcx-3]
0x18007ca48  jmp     short loc_18007CA62
0x18007ca4a  cmp     dword ptr [rsi], 42504844h
0x18007ca50  jz      short loc_18007CA5A
0x18007ca52  mov     r9d, 5A2h
0x18007ca58  jmp     short loc_18007CA23
0x18007ca5a  mov     ecx, 3
0x18007ca5f  mov     r15d, r13d
0x18007ca62  mov     ebp, [rsi+4]
0x18007ca65  imul    ecx, ebp
0x18007ca68  add     rcx, 8
0x18007ca6c  cmp     r14, rcx
0x18007ca6f  jnz     loc_18007CC5C
0x18007ca75  lea     eax, [rbp-40h]
0x18007ca78  cmp     eax, 1C0h
0x18007ca7d  ja      loc_18007CC5C
0x18007ca83  mov     r14d, 28h ; '('
0x18007ca89  mov     ecx, r14d
0x18007ca8c  call    MSCryptAlloc
0x18007ca91  mov     rdi, rax
0x18007ca94  test    rax, rax
0x18007ca97  jnz     short loc_18007CAAE
0x18007ca99  mov     ebx, 0C0000017h
0x18007ca9e  mov     ecx, 0C0000017h
0x18007caa3  mov     r9d, 5D1h
0x18007caa9  jmp     loc_18007CC7A
0x18007caae  mov     [rax+8], r13
0x18007cab2  xor     edx, edx
0x18007cab4  mov     [rax+10h], r13
0x18007cab8  mov     [rax+18h], r13
0x18007cabc  mov     [rax+20h], r13
0x18007cac0  mov     [rax], r14d
0x18007cac3  mov     dword ptr [rax+4], 4D534B59h
0x18007caca  mov     rax, [rsp+0C8h+var_50]
0x18007cacf  mov     ecx, [rax+8]
0x18007cad2  mov     [rdi+8], ecx
0x18007cad5  lea     ecx, ds:0[rbp*8]
0x18007cadc  mov     [rdi+0Ch], ebp
0x18007cadf  call    SymCryptDlgroupAllocate
0x18007cae4  mov     [rdi+18h], rax
0x18007cae8  test    rax, rax
0x18007caeb  jnz     short loc_18007CB02
0x18007caed  mov     ebx, 0C0000017h
0x18007caf2  mov     ecx, 0C0000017h
0x18007caf7  mov     r9d, 5E4h
0x18007cafd  jmp     loc_18007CC7A
0x18007cb02  mov     edx, [rdi+0Ch]; int
0x18007cb05  lea     rcx, [rsi+8]; int
0x18007cb09  mov     [rsp+0C8h+var_68], rax; __int64
0x18007cb0e  xor     r9d, r9d; int
0x18007cb11  mov     [rsp+0C8h+var_70], r13d; int
0x18007cb16  xor     r8d, r8d; int
0x18007cb19  mov     [rsp+0C8h+var_78], r13d; int
0x18007cb1e  mov     [rsp+0C8h+Size], r13; Size
0x18007cb23  lea     r14, [rdx+rcx]
0x18007cb27  mov     [rsp+0C8h+var_88], r13; __int64
0x18007cb2c  mov     [rsp+0C8h+var_90], r13; __int64
0x18007cb31  mov     [rsp+0C8h+var_98], 2; int
0x18007cb39  mov     qword ptr [rsp+0C8h+var_A0], rdx; int
0x18007cb3e  mov     qword ptr [rsp+0C8h+var_A8], r14; int
0x18007cb43  call    SymCryptDlgroupSetValue
0x18007cb48  test    eax, eax
0x18007cb4a  jz      short loc_18007CB62
0x18007cb4c  mov     ecx, eax
0x18007cb4e  call    SymcryptErrorCodeToNtStatus
0x18007cb53  mov     ebx, eax
0x18007cb55  mov     ecx, eax
0x18007cb57  mov     r9d, 5FCh
0x18007cb5d  jmp     loc_18007CC7A
0x18007cb62  mov     edx, [rdi+0Ch]
0x18007cb65  lea     rcx, [rsi+8]
0x18007cb69  or      dword ptr [rdi+10h], 2
0x18007cb6d  mov     rbp, r13
0x18007cb70  lea     r10d, [rdx+rdx]
0x18007cb74  add     rcx, r10
0x18007cb77  call    IsAllZeros
0x18007cb7c  test    eax, eax
0x18007cb7e  jnz     short loc_18007CB84
0x18007cb80  lea     rbp, [r14+rdx]
0x18007cb84  xor     ecx, ecx
0x18007cb86  mov     r13d, edx
0x18007cb89  test    eax, eax
0x18007cb8b  mov     eax, r15d
0x18007cb8e  cmovnz  r13d, ecx
0x18007cb92  neg     eax
0x18007cb94  sbb     eax, eax
0x18007cb96  and     eax, edx
0x18007cb98  neg     r15d
0x18007cb9b  mov     [rsp+0C8h+arg_28], eax
0x18007cba2  lea     rax, [r10+r14]
0x18007cba6  sbb     r14, r14
0x18007cba9  and     r14, rax
0x18007cbac  test    byte ptr [rsp+0C8h+arg_30], 20h
0x18007cbb4  jz      short loc_18007CBCE
0x18007cbb6  test    r14, r14
0x18007cbb9  jz      short loc_18007CBC0
0x18007cbbb  test    rbp, rbp
0x18007cbbe  jnz     short loc_18007CBCE
0x18007cbc0  mov     r9d, 617h
0x18007cbc6  xor     r13d, r13d
0x18007cbc9  jmp     loc_18007CC70
0x18007cbce  mov     ecx, [rsp+0C8h+arg_30]
0x18007cbd5  call    BCryptFlagsToSymCryptKeyValidationFlags
0x18007cbda  mov     rcx, [rdi+18h]
0x18007cbde  mov     r15d, eax
0x18007cbe1  mov     dl, [rcx+28h]
0x18007cbe4  neg     dl
0x18007cbe6  sbb     esi, esi
0x18007cbe8  and     esi, 0FFFFFF00h
0x18007cbee  add     esi, 2100h
0x18007cbf4  call    SymCryptDlkeyAllocate
0x18007cbf9  mov     [rdi+20h], rax
0x18007cbfd  test    rax, rax
0x18007cc00  jnz     short loc_18007CC17
0x18007cc02  mov     ebx, 0C0000017h
0x18007cc07  mov     ecx, 0C0000017h
0x18007cc0c  mov     r9d, 62Ah
0x18007cc12  xor     r13d, r13d
0x18007cc15  jmp     short loc_18007CC7A
0x18007cc17  mov     edx, [rsp+0C8h+arg_28]
0x18007cc1e  or      esi, r15d
0x18007cc21  mov     qword ptr [rsp+0C8h+var_98], rax
0x18007cc26  mov     r8, rbp
0x18007cc29  mov     r9d, r13d
0x18007cc2c  mov     rcx, r14
0x18007cc2f  mov     [rsp+0C8h+var_A0], esi
0x18007cc33  call    SymCryptDlkeySetValue
0x18007cc38  xor     r13d, r13d
0x18007cc3b  test    eax, eax
0x18007cc3d  jz      short loc_18007CC52
0x18007cc3f  mov     ecx, eax
0x18007cc41  call    SymcryptErrorCodeToNtStatus
0x18007cc46  mov     ebx, eax
0x18007cc48  mov     ecx, eax
0x18007cc4a  mov     r9d, 639h
0x18007cc50  jmp     short loc_18007CC7A
0x18007cc52  or      dword ptr [rdi+10h], 1
0x18007cc56  mov     [r12], rdi
0x18007cc5a  jmp     short loc_18007CCBE
0x18007cc5c  mov     r9d, 5C4h
0x18007cc62  jmp     loc_18007CA23
0x18007cc67  mov     rdi, r13
0x18007cc6a  mov     r9d, 58Bh
0x18007cc70  mov     ecx, 0C000000Dh
0x18007cc75  mov     ebx, 0C000000Dh
0x18007cc7a  lea     rdx, aStatus; "Status"
0x18007cc81  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007cc88  call    DebugTraceError
0x18007cc8d  test    rdi, rdi
0x18007cc90  jz      short loc_18007CCBE
0x18007cc92  mov     rcx, [rdi+20h]
0x18007cc96  test    rcx, rcx
0x18007cc99  jz      short loc_18007CCA4
0x18007cc9b  call    SymCryptDlkeyFree
0x18007cca0  mov     [rdi+20h], r13
0x18007cca4  mov     rcx, [rdi+18h]
0x18007cca8  test    rcx, rcx
0x18007ccab  jz      short loc_18007CCB6
0x18007ccad  call    SymCryptMlDsaTemporariesFree
0x18007ccb2  mov     [rdi+18h], r13
0x18007ccb6  mov     rcx, rdi; P
0x18007ccb9  call    MSCryptFree
0x18007ccbe  mov     eax, ebx
0x18007ccc0  add     rsp, 88h
0x18007ccc7  pop     r15
0x18007ccc9  pop     r14
0x18007cccb  pop     r13
0x18007cccd  pop     r12
0x18007cccf  pop     rdi
0x18007ccd0  pop     rsi
0x18007ccd1  pop     rbp
0x18007ccd2  pop     rbx
0x18007ccd3  retn
```
