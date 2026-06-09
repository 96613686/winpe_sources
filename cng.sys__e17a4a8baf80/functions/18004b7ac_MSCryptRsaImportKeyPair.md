# MSCryptRsaImportKeyPair

- ea: `0x18004b7ac`
- end: `0x18004bc3d`
- name: `MSCryptRsaImportKeyPair`
- size: `1169`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18004b770`
- `0x18007e59c`
- `0x180082200`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x180029b7c`
- `0x1800499a8`
- `0x180049c48`
- `0x18004a524`
- `0x18004b314`
- `0x18004b628`
- `0x18004b7ac`
- `0x18004bddc`
- `0x180051dd0`
- `0x1800521a4`
- `0x180088308`
- `0x1800a40b4`
- `0x1800a4232`

## string_xrefs

- `0x18004b8fc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004b9c4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004ba35`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004ba89`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004bc13`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptRsaImportKeyPair(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        _QWORD *a4,
        _DWORD *a5,
        unsigned int a6,
        unsigned int a7,
        int a8)
{
  unsigned int v8; // r13d
  __int64 v12; // r9
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rdx
  _DWORD *v16; // rax
  _DWORD *v17; // r14
  unsigned int v18; // edi
  _DWORD *v19; // rsi
  __int64 v20; // r9
  __int64 v21; // rcx
  unsigned int v22; // eax
  int v23; // r12d
  unsigned int v24; // ecx
  unsigned int v25; // r9d
  int v26; // eax
  _QWORD *v27; // rdi
  int SymcryptRsakey; // eax
  __int64 v29; // r9
  __int64 v30; // rbx
  unsigned int v31; // eax
  int v32; // eax
  int v33; // r11d
  int v34; // r8d
  unsigned int v35; // eax
  __int64 v36; // rcx
  _BYTE *v37; // rax
  unsigned int v39; // [rsp+60h] [rbp-41h] BYREF
  PVOID P; // [rsp+68h] [rbp-39h] BYREF
  __int64 v41; // [rsp+70h] [rbp-31h] BYREF
  __int64 v42; // [rsp+78h] [rbp-29h]
  __int128 v43; // [rsp+80h] [rbp-21h] BYREF
  __int128 v44; // [rsp+90h] [rbp-11h] BYREF
  unsigned int v46; // [rsp+110h] [rbp+6Fh]
  unsigned int v47; // [rsp+118h] [rbp+77h]

  v8 = 0;
  v41 = 0;
  P = 0;
  v39 = 0;
  *a4 = 0;
  v44 = 0;
  v43 = 0;
  if ( (a7 & 0xFFFFFFF7) != 0 )
  {
    v12 = 1427;
LABEL_64:
    v13 = -1073741811;
    v14 = 3221225485LL;
    goto LABEL_65;
  }
  if ( ((a8 - 1) & 0xFFFFFFFC) != 0 || a8 == 3 )
  {
    v12 = 1436;
    goto LABEL_64;
  }
  v42 = validateMSCryptRsaAlgorithm();
  if ( !v42 )
  {
    v13 = -1073741816;
    v12 = 1444;
    v14 = 3221225480LL;
LABEL_65:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v12);
    return v13;
  }
  if ( !a3 || wcscmp_0(a3, L"PKCS11RsaAesWrapBlob") )
  {
    if ( a2 )
    {
      v13 = -1073741637;
      v12 = 1497;
      v14 = 3221225659LL;
      goto LABEL_65;
    }
    v18 = a6;
    v17 = 0;
    v19 = a5;
LABEL_21:
    if ( !wcscmp_0(a3, L"RSAPUBLICBLOB") || !wcscmp_0(a3, L"PUBLICBLOB") )
    {
      v22 = VerifyRsaPublicBlob(v19, v18);
      v23 = 0;
      v13 = v22;
      if ( v22 )
      {
        v20 = 1511;
        goto LABEL_29;
      }
    }
    else
    {
      if ( wcscmp_0(a3, L"RSAPRIVATEBLOB") && wcscmp_0(a3, L"PRIVATEBLOB") )
      {
        v13 = -1073741637;
        v20 = 1529;
        v21 = 3221225659LL;
LABEL_26:
        DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v20);
        goto LABEL_59;
      }
      v22 = VerifyRsaPrivateBlob(v19, v18);
      v13 = v22;
      if ( v22 )
      {
        v20 = 1522;
LABEL_29:
        v21 = v22;
        goto LABEL_26;
      }
      v23 = 1;
    }
    v24 = v19[3];
    v47 = v19[2];
    v25 = 8 * v24;
    if ( (unsigned int)(v19[1] + 7) >> 3 >= v24 )
      v25 = v19[1];
    v46 = v25;
    v26 = CreateAndInitializeNewKey(v42, v25, &P);
    v13 = v26;
    if ( v26 < 0 )
    {
      DebugTraceError((unsigned int)v26, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 1555);
      v27 = P;
      goto LABEL_55;
    }
    v27 = P;
    SymcryptRsakey = AllocateSymcryptRsakey(P);
    v13 = SymcryptRsakey;
    if ( SymcryptRsakey >= 0 )
    {
      v30 = (__int64)v19 + v47 + 24;
      if ( v23 )
      {
        *(_QWORD *)&v44 = v30 + (unsigned int)v19[3];
        *(_QWORD *)&v43 = (unsigned int)v19[4];
        *((_QWORD *)&v44 + 1) = v44 + (unsigned int)v19[4];
        *((_QWORD *)&v43 + 1) = (unsigned int)v19[5];
      }
      v31 = SymCryptLoadMsbFirstUint64(v19 + 6, (unsigned int)v19[2], &v41);
      if ( v31 )
      {
        SymcryptRsakey = SymcryptErrorCodeToNtStatus(v31);
        v13 = SymcryptRsakey;
        v29 = 1581;
      }
      else
      {
        v32 = BCryptFlagsToSymCryptKeyValidationFlags(a7);
        switch ( a8 )
        {
          case 4:
            v32 |= 0x3100u;
            break;
          case 1:
            v32 |= 0x1000u;
            break;
          case 2:
            v32 |= 0x2000u;
            break;
        }
        v34 = v32 | 0x100;
        if ( v46 >= 0x400 )
          v34 = v32;
        v35 = SymCryptRsakeySetValueInternal(
                v30,
                v19[3],
                (unsigned int)&v41,
                1,
                0,
                0,
                (__int64)&v44,
                (__int64)&v43,
                v33,
                2,
                v34,
                v27[4]);
        if ( !v35 )
        {
          *((_DWORD *)v27 + 4) = 1;
          *a4 = v27;
          v27 = 0;
          v13 = 0;
LABEL_55:
          if ( v27 )
          {
            if ( v27[4] )
            {
              SymCryptRsakeyFree();
              v27[4] = 0;
            }
            MSCryptFree(v27);
          }
LABEL_59:
          if ( !v17 )
            return v13;
          goto LABEL_60;
        }
        SymcryptRsakey = SymcryptErrorCodeToNtStatus(v35);
        v13 = SymcryptRsakey;
        v29 = 1623;
      }
    }
    else
    {
      v29 = 1562;
    }
    DebugTraceError(
      (unsigned int)SymcryptRsakey,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
      v29);
    goto LABEL_55;
  }
  if ( !a2 )
  {
    v12 = 1454;
    goto LABEL_64;
  }
  if ( (int)Pkcs11ConvertToKeyBlob(a1, a2, 0, &v39, a5, a6) < 0 )
  {
    v12 = 1467;
    goto LABEL_64;
  }
  v16 = (_DWORD *)MSCryptAlloc(v39, v15);
  v17 = v16;
  if ( !v16 )
  {
    v13 = -1073741801;
    v12 = 1474;
    v14 = 3221225495LL;
    goto LABEL_65;
  }
  if ( (int)Pkcs11ConvertToKeyBlob(a1, a2, v16, &v39, a5, a6) >= 0 )
  {
    v8 = v39;
    a3 = L"RSAPRIVATEBLOB";
    v18 = v39;
    v19 = v17;
    goto LABEL_21;
  }
  v13 = -1073741811;
  DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 1487);
  v8 = v39;
LABEL_60:
  v36 = v8;
  v37 = v17;
  if ( v8 )
  {
    do
    {
      *v37++ = 0;
      --v36;
    }
    while ( v36 );
  }
  MSCryptFree(v17);
  return v13;
}

```

## disassembly

```asm
0x18004b7ac  mov     [rsp-8+arg_18], r9
0x18004b7b1  push    rbp
0x18004b7b2  push    rbx
0x18004b7b3  push    rsi
0x18004b7b4  push    rdi
0x18004b7b5  push    r12
0x18004b7b7  push    r13
0x18004b7b9  push    r14
0x18004b7bb  push    r15
0x18004b7bd  lea     rbp, [rsp-7]
0x18004b7c2  sub     rsp, 0A8h
0x18004b7c9  xor     r13d, r13d
0x18004b7cc  mov     [rbp+3Fh+var_70], 0
0x18004b7d4  test    [rbp+3Fh+arg_30], 0FFFFFFF7h
0x18004b7db  xorps   xmm0, xmm0
0x18004b7de  xorps   xmm1, xmm1
0x18004b7e1  mov     [rbp+3Fh+P], 0
0x18004b7e9  mov     rbx, r8
0x18004b7ec  mov     [rbp+3Fh+var_80], r13d
0x18004b7f0  mov     rdi, rdx
0x18004b7f3  mov     [r9], r13
0x18004b7f6  mov     rsi, rcx
0x18004b7f9  movups  [rbp+3Fh+var_50], xmm0
0x18004b7fd  movups  [rbp+3Fh+var_60], xmm1
0x18004b801  jz      short loc_18004B80E
0x18004b803  mov     r9d, 593h
0x18004b809  jmp     loc_18004BC09
0x18004b80e  mov     r15d, [rbp+3Fh+arg_38]
0x18004b815  lea     eax, [r15-1]
0x18004b819  test    eax, 0FFFFFFFCh
0x18004b81e  jnz     loc_18004BC03
0x18004b824  cmp     r15d, 3
0x18004b828  jz      loc_18004BC03
0x18004b82e  call    validateMSCryptRsaAlgorithm
0x18004b833  mov     [rbp+3Fh+var_68], rax
0x18004b837  test    rax, rax
0x18004b83a  jnz     short loc_18004B851
0x18004b83c  mov     ebx, 0C0000008h
0x18004b841  mov     r9d, 5A4h
0x18004b847  mov     ecx, 0C0000008h
0x18004b84c  jmp     loc_18004BC13
0x18004b851  test    rbx, rbx
0x18004b854  jz      loc_18004B935
0x18004b85a  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x18004b861  mov     rcx, rbx; Str1
0x18004b864  call    wcscmp_0
0x18004b869  test    eax, eax
0x18004b86b  jnz     loc_18004B935
0x18004b871  test    rdi, rdi
0x18004b874  jnz     short loc_18004B881
0x18004b876  mov     r9d, 5AEh
0x18004b87c  jmp     loc_18004BC09
0x18004b881  mov     ebx, [rbp+3Fh+arg_28]
0x18004b884  lea     r9, [rbp+3Fh+var_80]
0x18004b888  mov     r12, [rbp+3Fh+arg_20]
0x18004b88c  xor     r8d, r8d
0x18004b88f  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x18004b893  mov     rdx, rdi
0x18004b896  mov     rcx, rsi
0x18004b899  mov     [rsp+0E0h+var_C0], r12
0x18004b89e  call    Pkcs11ConvertToKeyBlob
0x18004b8a3  test    eax, eax
0x18004b8a5  jns     short loc_18004B8B2
0x18004b8a7  mov     r9d, 5BBh
0x18004b8ad  jmp     loc_18004BC09
0x18004b8b2  mov     ecx, [rbp+3Fh+var_80]
0x18004b8b5  call    MSCryptAlloc
0x18004b8ba  mov     r14, rax
0x18004b8bd  test    rax, rax
0x18004b8c0  jnz     short loc_18004B8D7
0x18004b8c2  mov     ebx, 0C0000017h
0x18004b8c7  mov     r9d, 5C2h
0x18004b8cd  mov     ecx, 0C0000017h
0x18004b8d2  jmp     loc_18004BC13
0x18004b8d7  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x18004b8db  lea     r9, [rbp+3Fh+var_80]
0x18004b8df  mov     r8, r14
0x18004b8e2  mov     [rsp+0E0h+var_C0], r12
0x18004b8e7  mov     rdx, rdi
0x18004b8ea  mov     rcx, rsi
0x18004b8ed  call    Pkcs11ConvertToKeyBlob
0x18004b8f2  test    eax, eax
0x18004b8f4  jns     short loc_18004B922
0x18004b8f6  mov     r9d, 5CFh
0x18004b8fc  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004b903  lea     rdx, aStatus; "Status"
0x18004b90a  mov     ecx, 0C000000Dh
0x18004b90f  mov     ebx, 0C000000Dh
0x18004b914  call    DebugTraceError
0x18004b919  mov     r13d, [rbp+3Fh+var_80]
0x18004b91d  jmp     loc_18004BBE2
0x18004b922  mov     r13d, [rbp+3Fh+var_80]
0x18004b926  lea     rbx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18004b92d  mov     edi, r13d
0x18004b930  mov     rsi, r14
0x18004b933  jmp     short loc_18004B959
0x18004b935  test    rdi, rdi
0x18004b938  jz      short loc_18004B94F
0x18004b93a  mov     ebx, 0C00000BBh
0x18004b93f  mov     r9d, 5D9h
0x18004b945  mov     ecx, 0C00000BBh
0x18004b94a  jmp     loc_18004BC13
0x18004b94f  mov     edi, [rbp+3Fh+arg_28]
0x18004b952  xor     r14d, r14d
0x18004b955  mov     rsi, [rbp+3Fh+arg_20]
0x18004b959  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x18004b960  mov     rcx, rbx; Str1
0x18004b963  call    wcscmp_0
0x18004b968  test    eax, eax
0x18004b96a  jz      loc_18004BA53
0x18004b970  lea     rdx, aPublicblob; "PUBLICBLOB"
0x18004b977  mov     rcx, rbx; Str1
0x18004b97a  call    wcscmp_0
0x18004b97f  test    eax, eax
0x18004b981  jz      loc_18004BA53
0x18004b987  lea     rdx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18004b98e  mov     rcx, rbx; Str1
0x18004b991  call    wcscmp_0
0x18004b996  test    eax, eax
0x18004b998  jz      short loc_18004B9D5
0x18004b99a  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x18004b9a1  mov     rcx, rbx; Str1
0x18004b9a4  call    wcscmp_0
0x18004b9a9  test    eax, eax
0x18004b9ab  jz      short loc_18004B9D5
0x18004b9ad  mov     ebx, 0C00000BBh
0x18004b9b2  mov     r9d, 5F9h
0x18004b9b8  mov     ecx, 0C00000BBh
0x18004b9bd  lea     rdx, aStatus; "Status"
0x18004b9c4  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004b9cb  call    DebugTraceError
0x18004b9d0  jmp     loc_18004BBDD
0x18004b9d5  mov     edx, edi
0x18004b9d7  mov     rcx, rsi
0x18004b9da  call    VerifyRsaPrivateBlob
0x18004b9df  mov     ebx, eax
0x18004b9e1  test    eax, eax
0x18004b9e3  jz      short loc_18004B9EF
0x18004b9e5  mov     r9d, 5F2h
0x18004b9eb  mov     ecx, eax
0x18004b9ed  jmp     short loc_18004B9BD
0x18004b9ef  mov     r12d, 1
0x18004b9f5  mov     edx, [rsi+4]
0x18004b9f8  lea     r8, [rbp+3Fh+P]
0x18004b9fc  mov     ecx, [rsi+0Ch]
0x18004b9ff  mov     eax, [rsi+8]
0x18004ba02  mov     [rbp+3Fh+arg_28], eax
0x18004ba05  lea     eax, [rdx+7]
0x18004ba08  lea     r9d, ds:0[rcx*8]
0x18004ba10  shr     eax, 3
0x18004ba13  cmp     eax, ecx
0x18004ba15  mov     rcx, [rbp+3Fh+var_68]
0x18004ba19  cmovnb  r9d, edx
0x18004ba1d  mov     edx, r9d
0x18004ba20  mov     dword ptr [rbp+3Fh+arg_20], r9d
0x18004ba24  call    CreateAndInitializeNewKey
0x18004ba29  mov     ebx, eax
0x18004ba2b  test    eax, eax
0x18004ba2d  jns     short loc_18004BA71
0x18004ba2f  mov     r9d, 613h
0x18004ba35  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004ba3c  lea     rdx, aStatus; "Status"
0x18004ba43  mov     ecx, eax
0x18004ba45  call    DebugTraceError
0x18004ba4a  mov     rdi, [rbp+3Fh+P]
0x18004ba4e  jmp     loc_18004BBBA
0x18004ba53  mov     edx, edi
0x18004ba55  mov     rcx, rsi
0x18004ba58  call    VerifyRsaPublicBlob
0x18004ba5d  xor     r12d, r12d
0x18004ba60  mov     ebx, eax
0x18004ba62  test    eax, eax
0x18004ba64  jz      short loc_18004B9F5
0x18004ba66  mov     r9d, 5E7h
0x18004ba6c  jmp     loc_18004B9EB
0x18004ba71  mov     rdi, [rbp+3Fh+P]
0x18004ba75  mov     rcx, rdi
0x18004ba78  call    AllocateSymcryptRsakey
0x18004ba7d  mov     ebx, eax
0x18004ba7f  test    eax, eax
0x18004ba81  jns     short loc_18004BAA3
0x18004ba83  mov     r9d, 61Ah
0x18004ba89  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004ba90  mov     ecx, eax
0x18004ba92  lea     rdx, aStatus; "Status"
0x18004ba99  call    DebugTraceError
0x18004ba9e  jmp     loc_18004BBBA
0x18004baa3  mov     ebx, [rbp+3Fh+arg_28]
0x18004baa6  lea     rcx, [rsi+18h]
0x18004baaa  add     rbx, rcx
0x18004baad  xor     r11d, r11d
0x18004bab0  test    r12d, r12d
0x18004bab3  jz      short loc_18004BADD
0x18004bab5  mov     edx, [rsi+0Ch]
0x18004bab8  mov     r11d, 2
0x18004babe  add     rdx, rbx
0x18004bac1  mov     qword ptr [rbp+3Fh+var_50], rdx
0x18004bac5  mov     eax, [rsi+10h]
0x18004bac8  mov     qword ptr [rbp+3Fh+var_60], rax
0x18004bacc  mov     eax, [rsi+10h]
0x18004bacf  add     rax, rdx
0x18004bad2  mov     qword ptr [rbp+3Fh+var_50+8], rax
0x18004bad6  mov     eax, [rsi+14h]
0x18004bad9  mov     qword ptr [rbp+3Fh+var_60+8], rax
0x18004badd  mov     edx, [rsi+8]
0x18004bae0  lea     r8, [rbp+3Fh+var_70]
0x18004bae4  call    SymCryptLoadMsbFirstUint64
0x18004bae9  test    eax, eax
0x18004baeb  jz      short loc_18004BAFE
0x18004baed  mov     ecx, eax
0x18004baef  call    SymcryptErrorCodeToNtStatus
0x18004baf4  mov     ebx, eax
0x18004baf6  mov     r9d, 62Dh
0x18004bafc  jmp     short loc_18004BA89
0x18004bafe  mov     ecx, [rbp+3Fh+arg_30]
0x18004bb01  call    BCryptFlagsToSymCryptKeyValidationFlags
0x18004bb06  cmp     r15d, 4
0x18004bb0a  jnz     short loc_18004BB13
0x18004bb0c  or      eax, 3100h
0x18004bb11  jmp     short loc_18004BB29
0x18004bb13  cmp     r15d, 1
0x18004bb17  jnz     short loc_18004BB1F
0x18004bb19  bts     eax, 0Ch
0x18004bb1d  jmp     short loc_18004BB29
0x18004bb1f  cmp     r15d, 2
0x18004bb23  jnz     short loc_18004BB29
0x18004bb25  bts     eax, 0Dh
0x18004bb29  mov     edx, [rsi+0Ch]
0x18004bb2c  mov     r8d, eax
0x18004bb2f  bts     r8d, 8
0x18004bb34  mov     r9d, 1
0x18004bb3a  cmp     dword ptr [rbp+3Fh+arg_20], 400h
0x18004bb41  mov     rcx, rbx
0x18004bb44  cmovnb  r8d, eax
0x18004bb48  mov     rax, [rdi+20h]
0x18004bb4c  mov     [rsp+0E0h+var_88], rax
0x18004bb51  lea     rax, [rbp+3Fh+var_60]
0x18004bb55  mov     [rsp+0E0h+var_90], r8d
0x18004bb5a  lea     r8, [rbp+3Fh+var_70]
0x18004bb5e  mov     [rsp+0E0h+var_98], 2
0x18004bb66  mov     [rsp+0E0h+var_A0], r11d
0x18004bb6b  mov     [rsp+0E0h+var_A8], rax
0x18004bb70  lea     rax, [rbp+3Fh+var_50]
0x18004bb74  mov     [rsp+0E0h+var_B0], rax
0x18004bb79  mov     [rsp+0E0h+var_B8], 0
0x18004bb82  mov     [rsp+0E0h+var_C0], 0
0x18004bb8b  call    SymCryptRsakeySetValueInternal
0x18004bb90  test    eax, eax
0x18004bb92  jz      short loc_18004BBA8
0x18004bb94  mov     ecx, eax
0x18004bb96  call    SymcryptErrorCodeToNtStatus
0x18004bb9b  mov     ebx, eax
0x18004bb9d  mov     r9d, 657h
0x18004bba3  jmp     loc_18004BA89
0x18004bba8  mov     rax, [rbp+3Fh+arg_18]
0x18004bbac  mov     dword ptr [rdi+10h], 1
0x18004bbb3  mov     [rax], rdi
0x18004bbb6  xor     edi, edi
0x18004bbb8  xor     ebx, ebx
0x18004bbba  test    rdi, rdi
0x18004bbbd  jz      short loc_18004BBDD
0x18004bbbf  mov     rcx, [rdi+20h]
0x18004bbc3  test    rcx, rcx
0x18004bbc6  jz      short loc_18004BBD5
0x18004bbc8  call    SymCryptRsakeyFree
0x18004bbcd  mov     qword ptr [rdi+20h], 0
0x18004bbd5  mov     rcx, rdi; P
0x18004bbd8  call    MSCryptFree
0x18004bbdd  test    r14, r14
0x18004bbe0  jz      short loc_18004BC26
0x18004bbe2  mov     ecx, r13d
0x18004bbe5  mov     rax, r14
0x18004bbe8  test    r13d, r13d
0x18004bbeb  jz      short loc_18004BBF9
0x18004bbed  mov     byte ptr [rax], 0
0x18004bbf0  inc     rax
0x18004bbf3  sub     rcx, 1
0x18004bbf7  jnz     short loc_18004BBED
0x18004bbf9  mov     rcx, r14; P
0x18004bbfc  call    MSCryptFree
0x18004bc01  jmp     short loc_18004BC26
0x18004bc03  mov     r9d, 59Ch
0x18004bc09  mov     ebx, 0C000000Dh
0x18004bc0e  mov     ecx, 0C000000Dh
0x18004bc13  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004bc1a  lea     rdx, aStatus; "Status"
0x18004bc21  call    DebugTraceError
0x18004bc26  mov     eax, ebx
0x18004bc28  add     rsp, 0A8h
0x18004bc2f  pop     r15
0x18004bc31  pop     r14
0x18004bc33  pop     r13
0x18004bc35  pop     r12
0x18004bc37  pop     rdi
0x18004bc38  pop     rsi
0x18004bc39  pop     rbx
0x18004bc3a  pop     rbp
0x18004bc3b  retn
```
