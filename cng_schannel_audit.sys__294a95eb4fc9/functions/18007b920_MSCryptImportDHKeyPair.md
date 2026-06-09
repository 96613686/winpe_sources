# MSCryptImportDHKeyPair

- ea: `0x18007b920`
- end: `0x18007bce5`
- name: `MSCryptImportDHKeyPair`
- size: `965`
- prototype: `__int64 __fastcall(__int64, __int64, const wchar_t *, __int64 *, _DWORD *, int, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180041648`
- `0x180047ce0`
- `0x180048d28`
- `0x18007b920`
- `0x18007c250`
- `0x18008f24c`
- `0x18008f308`
- `0x18008fb34`
- `0x18008fffc`
- `0x180090360`
- `0x1800917f8`
- `0x18009d746`

## string_xrefs

- `0x18007b9d0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`
- `0x18007bc91`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

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
0x18007b920  push    rbx
0x18007b922  push    rbp
0x18007b923  push    rsi
0x18007b924  push    rdi
0x18007b925  push    r12
0x18007b927  push    r13
0x18007b929  push    r14
0x18007b92b  push    r15
0x18007b92d  sub     rsp, 88h
0x18007b934  xor     r13d, r13d
0x18007b937  mov     r12, r9
0x18007b93a  test    [rsp+0C8h+arg_30], 0FFFFFFC7h
0x18007b945  mov     rdi, r8
0x18007b948  mov     [rsp+0C8h+var_58], r13d
0x18007b94d  mov     [rsp+0C8h+var_50], r13
0x18007b952  jz      short loc_18007B95E
0x18007b954  mov     eax, 0C000000Dh
0x18007b959  jmp     loc_18007BCD0
0x18007b95e  test    rdx, rdx
0x18007b961  jz      short loc_18007B96D
0x18007b963  mov     eax, 0C00000BBh
0x18007b968  jmp     loc_18007BCD0
0x18007b96d  test    rcx, rcx
0x18007b970  jz      loc_18007BC77
0x18007b976  test    rdi, rdi
0x18007b979  jz      loc_18007BC77
0x18007b97f  test    r12, r12
0x18007b982  jz      loc_18007BC77
0x18007b988  mov     rsi, [rsp+0C8h+arg_20]
0x18007b990  test    rsi, rsi
0x18007b993  jz      loc_18007BC77
0x18007b999  mov     r14d, [rsp+0C8h+arg_28]
0x18007b9a1  test    r14d, r14d
0x18007b9a4  jz      loc_18007BC77
0x18007b9aa  lea     r9, [rsp+0C8h+var_50]
0x18007b9af  xor     edx, edx
0x18007b9b1  lea     r8, [rsp+0C8h+var_58]
0x18007b9b6  call    ValidateDHAlgorithm
0x18007b9bb  mov     ebx, eax
0x18007b9bd  test    eax, eax
0x18007b9bf  jns     short loc_18007B9E1
0x18007b9c1  mov     r9d, 592h
0x18007b9c7  mov     ecx, eax
0x18007b9c9  lea     rdx, aStatus; "Status"
0x18007b9d0  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007b9d7  call    DebugTraceError
0x18007b9dc  jmp     loc_18007BCCE
0x18007b9e1  lea     rdx, aDhpublicblob; "DHPUBLICBLOB"
0x18007b9e8  mov     rcx, rdi; Str1
0x18007b9eb  call    wcscmp_0
0x18007b9f0  test    eax, eax
0x18007b9f2  jz      short loc_18007BA5A
0x18007b9f4  lea     rdx, aPublicblob; "PUBLICBLOB"
0x18007b9fb  mov     rcx, rdi; Str1
0x18007b9fe  call    wcscmp_0
0x18007ba03  test    eax, eax
0x18007ba05  jz      short loc_18007BA5A
0x18007ba07  lea     rdx, aDhprivateblob; "DHPRIVATEBLOB"
0x18007ba0e  mov     rcx, rdi; Str1
0x18007ba11  call    wcscmp_0
0x18007ba16  test    eax, eax
0x18007ba18  jz      short loc_18007BA3F
0x18007ba1a  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x18007ba21  mov     rcx, rdi; Str1
0x18007ba24  call    wcscmp_0
0x18007ba29  test    eax, eax
0x18007ba2b  jz      short loc_18007BA3F
0x18007ba2d  mov     r9d, 5B7h
0x18007ba33  mov     ebx, 0C000000Dh
0x18007ba38  mov     ecx, 0C000000Dh
0x18007ba3d  jmp     short loc_18007B9C9
0x18007ba3f  cmp     dword ptr [rsi], 56504844h
0x18007ba45  jz      short loc_18007BA4F
0x18007ba47  mov     r9d, 5AEh
0x18007ba4d  jmp     short loc_18007BA33
0x18007ba4f  mov     ecx, 4
0x18007ba54  lea     r15d, [rcx-3]
0x18007ba58  jmp     short loc_18007BA72
0x18007ba5a  cmp     dword ptr [rsi], 42504844h
0x18007ba60  jz      short loc_18007BA6A
0x18007ba62  mov     r9d, 5A2h
0x18007ba68  jmp     short loc_18007BA33
0x18007ba6a  mov     ecx, 3
0x18007ba6f  mov     r15d, r13d
0x18007ba72  mov     ebp, [rsi+4]
0x18007ba75  imul    ecx, ebp
0x18007ba78  add     rcx, 8
0x18007ba7c  cmp     r14, rcx
0x18007ba7f  jnz     loc_18007BC6C
0x18007ba85  lea     eax, [rbp-40h]
0x18007ba88  cmp     eax, 1C0h
0x18007ba8d  ja      loc_18007BC6C
0x18007ba93  mov     r14d, 28h ; '('
0x18007ba99  mov     ecx, r14d
0x18007ba9c  call    MSCryptAlloc
0x18007baa1  mov     rdi, rax
0x18007baa4  test    rax, rax
0x18007baa7  jnz     short loc_18007BABE
0x18007baa9  mov     ebx, 0C0000017h
0x18007baae  mov     ecx, 0C0000017h
0x18007bab3  mov     r9d, 5D1h
0x18007bab9  jmp     loc_18007BC8A
0x18007babe  mov     [rax+8], r13
0x18007bac2  xor     edx, edx
0x18007bac4  mov     [rax+10h], r13
0x18007bac8  mov     [rax+18h], r13
0x18007bacc  mov     [rax+20h], r13
0x18007bad0  mov     [rax], r14d
0x18007bad3  mov     dword ptr [rax+4], 4D534B59h
0x18007bada  mov     rax, [rsp+0C8h+var_50]
0x18007badf  mov     ecx, [rax+8]
0x18007bae2  mov     [rdi+8], ecx
0x18007bae5  lea     ecx, ds:0[rbp*8]
0x18007baec  mov     [rdi+0Ch], ebp
0x18007baef  call    SymCryptDlgroupAllocate
0x18007baf4  mov     [rdi+18h], rax
0x18007baf8  test    rax, rax
0x18007bafb  jnz     short loc_18007BB12
0x18007bafd  mov     ebx, 0C0000017h
0x18007bb02  mov     ecx, 0C0000017h
0x18007bb07  mov     r9d, 5E4h
0x18007bb0d  jmp     loc_18007BC8A
0x18007bb12  mov     edx, [rdi+0Ch]; int
0x18007bb15  lea     rcx, [rsi+8]; int
0x18007bb19  mov     [rsp+0C8h+var_68], rax; __int64
0x18007bb1e  xor     r9d, r9d; int
0x18007bb21  mov     [rsp+0C8h+var_70], r13d; int
0x18007bb26  xor     r8d, r8d; int
0x18007bb29  mov     [rsp+0C8h+var_78], r13d; int
0x18007bb2e  mov     [rsp+0C8h+Size], r13; Size
0x18007bb33  lea     r14, [rdx+rcx]
0x18007bb37  mov     [rsp+0C8h+var_88], r13; __int64
0x18007bb3c  mov     [rsp+0C8h+var_90], r13; __int64
0x18007bb41  mov     [rsp+0C8h+var_98], 2; int
0x18007bb49  mov     qword ptr [rsp+0C8h+var_A0], rdx; int
0x18007bb4e  mov     qword ptr [rsp+0C8h+var_A8], r14; int
0x18007bb53  call    SymCryptDlgroupSetValue
0x18007bb58  test    eax, eax
0x18007bb5a  jz      short loc_18007BB72
0x18007bb5c  mov     ecx, eax
0x18007bb5e  call    SymcryptErrorCodeToNtStatus
0x18007bb63  mov     ebx, eax
0x18007bb65  mov     ecx, eax
0x18007bb67  mov     r9d, 5FCh
0x18007bb6d  jmp     loc_18007BC8A
0x18007bb72  mov     edx, [rdi+0Ch]
0x18007bb75  lea     rcx, [rsi+8]
0x18007bb79  or      dword ptr [rdi+10h], 2
0x18007bb7d  mov     rbp, r13
0x18007bb80  lea     r10d, [rdx+rdx]
0x18007bb84  add     rcx, r10
0x18007bb87  call    IsAllZeros
0x18007bb8c  test    eax, eax
0x18007bb8e  jnz     short loc_18007BB94
0x18007bb90  lea     rbp, [r14+rdx]
0x18007bb94  xor     ecx, ecx
0x18007bb96  mov     r13d, edx
0x18007bb99  test    eax, eax
0x18007bb9b  mov     eax, r15d
0x18007bb9e  cmovnz  r13d, ecx
0x18007bba2  neg     eax
0x18007bba4  sbb     eax, eax
0x18007bba6  and     eax, edx
0x18007bba8  neg     r15d
0x18007bbab  mov     [rsp+0C8h+arg_28], eax
0x18007bbb2  lea     rax, [r10+r14]
0x18007bbb6  sbb     r14, r14
0x18007bbb9  and     r14, rax
0x18007bbbc  test    byte ptr [rsp+0C8h+arg_30], 20h
0x18007bbc4  jz      short loc_18007BBDE
0x18007bbc6  test    r14, r14
0x18007bbc9  jz      short loc_18007BBD0
0x18007bbcb  test    rbp, rbp
0x18007bbce  jnz     short loc_18007BBDE
0x18007bbd0  mov     r9d, 617h
0x18007bbd6  xor     r13d, r13d
0x18007bbd9  jmp     loc_18007BC80
0x18007bbde  mov     ecx, [rsp+0C8h+arg_30]
0x18007bbe5  call    BCryptFlagsToSymCryptKeyValidationFlags
0x18007bbea  mov     rcx, [rdi+18h]
0x18007bbee  mov     r15d, eax
0x18007bbf1  mov     dl, [rcx+28h]
0x18007bbf4  neg     dl
0x18007bbf6  sbb     esi, esi
0x18007bbf8  and     esi, 0FFFFFF00h
0x18007bbfe  add     esi, 2100h
0x18007bc04  call    SymCryptDlkeyAllocate
0x18007bc09  mov     [rdi+20h], rax
0x18007bc0d  test    rax, rax
0x18007bc10  jnz     short loc_18007BC27
0x18007bc12  mov     ebx, 0C0000017h
0x18007bc17  mov     ecx, 0C0000017h
0x18007bc1c  mov     r9d, 62Ah
0x18007bc22  xor     r13d, r13d
0x18007bc25  jmp     short loc_18007BC8A
0x18007bc27  mov     edx, [rsp+0C8h+arg_28]
0x18007bc2e  or      esi, r15d
0x18007bc31  mov     qword ptr [rsp+0C8h+var_98], rax
0x18007bc36  mov     r8, rbp
0x18007bc39  mov     r9d, r13d
0x18007bc3c  mov     rcx, r14
0x18007bc3f  mov     [rsp+0C8h+var_A0], esi
0x18007bc43  call    SymCryptDlkeySetValue
0x18007bc48  xor     r13d, r13d
0x18007bc4b  test    eax, eax
0x18007bc4d  jz      short loc_18007BC62
0x18007bc4f  mov     ecx, eax
0x18007bc51  call    SymcryptErrorCodeToNtStatus
0x18007bc56  mov     ebx, eax
0x18007bc58  mov     ecx, eax
0x18007bc5a  mov     r9d, 639h
0x18007bc60  jmp     short loc_18007BC8A
0x18007bc62  or      dword ptr [rdi+10h], 1
0x18007bc66  mov     [r12], rdi
0x18007bc6a  jmp     short loc_18007BCCE
0x18007bc6c  mov     r9d, 5C4h
0x18007bc72  jmp     loc_18007BA33
0x18007bc77  mov     rdi, r13
0x18007bc7a  mov     r9d, 58Bh
0x18007bc80  mov     ecx, 0C000000Dh
0x18007bc85  mov     ebx, 0C000000Dh
0x18007bc8a  lea     rdx, aStatus; "Status"
0x18007bc91  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007bc98  call    DebugTraceError
0x18007bc9d  test    rdi, rdi
0x18007bca0  jz      short loc_18007BCCE
0x18007bca2  mov     rcx, [rdi+20h]
0x18007bca6  test    rcx, rcx
0x18007bca9  jz      short loc_18007BCB4
0x18007bcab  call    SymCryptDlkeyFree
0x18007bcb0  mov     [rdi+20h], r13
0x18007bcb4  mov     rcx, [rdi+18h]
0x18007bcb8  test    rcx, rcx
0x18007bcbb  jz      short loc_18007BCC6
0x18007bcbd  call    SymCryptMlDsaTemporariesFree
0x18007bcc2  mov     [rdi+18h], r13
0x18007bcc6  mov     rcx, rdi; P
0x18007bcc9  call    MSCryptFree
0x18007bcce  mov     eax, ebx
0x18007bcd0  add     rsp, 88h
0x18007bcd7  pop     r15
0x18007bcd9  pop     r14
0x18007bcdb  pop     r13
0x18007bcdd  pop     r12
0x18007bcdf  pop     rdi
0x18007bce0  pop     rsi
0x18007bce1  pop     rbp
0x18007bce2  pop     rbx
0x18007bce3  retn
```
