# MSCryptRsaImportKeyPair

- ea: `0x1800417cc`
- end: `0x180041c5d`
- name: `MSCryptRsaImportKeyPair`
- size: `1169`
- prototype: `__int64 __fastcall(int, __int64, const wchar_t *, _QWORD *, __int64, unsigned int, unsigned int, int)`
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180041790`
- `0x1800743fc`
- `0x180078060`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x18001fa4c`
- `0x18003f9e8`
- `0x18003fc88`
- `0x180040548`
- `0x180041334`
- `0x180041648`
- `0x1800417cc`
- `0x180041dfc`
- `0x180047ce0`
- `0x1800480b4`
- `0x18007e108`
- `0x18009d5b4`
- `0x18009d746`

## string_xrefs

- `0x18004191c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x1800419e4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180041a55`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180041aa9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180041c33`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptRsaImportKeyPair(
        int a1,
        __int64 a2,
        const wchar_t *a3,
        _QWORD *a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7,
        int a8)
{
  unsigned int v8; // r13d
  __int64 v12; // r9
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
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
    v19 = (_DWORD *)a5;
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
  if ( (int)Pkcs11ConvertToKeyBlob(a1, a2, 0, (unsigned int)&v39, a5, a6) < 0 )
  {
    v12 = 1467;
    goto LABEL_64;
  }
  v16 = MSCryptAlloc(v39, v15);
  v17 = (_DWORD *)v16;
  if ( !v16 )
  {
    v13 = -1073741801;
    v12 = 1474;
    v14 = 3221225495LL;
    goto LABEL_65;
  }
  if ( (int)Pkcs11ConvertToKeyBlob(a1, a2, v16, (unsigned int)&v39, a5, a6) >= 0 )
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
0x1800417cc  mov     [rsp-8+arg_18], r9
0x1800417d1  push    rbp
0x1800417d2  push    rbx
0x1800417d3  push    rsi
0x1800417d4  push    rdi
0x1800417d5  push    r12
0x1800417d7  push    r13
0x1800417d9  push    r14
0x1800417db  push    r15
0x1800417dd  lea     rbp, [rsp-7]
0x1800417e2  sub     rsp, 0A8h
0x1800417e9  xor     r13d, r13d
0x1800417ec  mov     [rbp+3Fh+var_70], 0
0x1800417f4  test    [rbp+3Fh+arg_30], 0FFFFFFF7h
0x1800417fb  xorps   xmm0, xmm0
0x1800417fe  xorps   xmm1, xmm1
0x180041801  mov     [rbp+3Fh+P], 0
0x180041809  mov     rbx, r8
0x18004180c  mov     [rbp+3Fh+var_80], r13d
0x180041810  mov     rdi, rdx
0x180041813  mov     [r9], r13
0x180041816  mov     rsi, rcx
0x180041819  movups  [rbp+3Fh+var_50], xmm0
0x18004181d  movups  [rbp+3Fh+var_60], xmm1
0x180041821  jz      short loc_18004182E
0x180041823  mov     r9d, 593h
0x180041829  jmp     loc_180041C29
0x18004182e  mov     r15d, [rbp+3Fh+arg_38]
0x180041835  lea     eax, [r15-1]
0x180041839  test    eax, 0FFFFFFFCh
0x18004183e  jnz     loc_180041C23
0x180041844  cmp     r15d, 3
0x180041848  jz      loc_180041C23
0x18004184e  call    validateMSCryptRsaAlgorithm
0x180041853  mov     [rbp+3Fh+var_68], rax
0x180041857  test    rax, rax
0x18004185a  jnz     short loc_180041871
0x18004185c  mov     ebx, 0C0000008h
0x180041861  mov     r9d, 5A4h
0x180041867  mov     ecx, 0C0000008h
0x18004186c  jmp     loc_180041C33
0x180041871  test    rbx, rbx
0x180041874  jz      loc_180041955
0x18004187a  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x180041881  mov     rcx, rbx; Str1
0x180041884  call    wcscmp_0
0x180041889  test    eax, eax
0x18004188b  jnz     loc_180041955
0x180041891  test    rdi, rdi
0x180041894  jnz     short loc_1800418A1
0x180041896  mov     r9d, 5AEh
0x18004189c  jmp     loc_180041C29
0x1800418a1  mov     ebx, [rbp+3Fh+arg_28]
0x1800418a4  lea     r9, [rbp+3Fh+var_80]
0x1800418a8  mov     r12, [rbp+3Fh+arg_20]
0x1800418ac  xor     r8d, r8d
0x1800418af  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x1800418b3  mov     rdx, rdi
0x1800418b6  mov     rcx, rsi
0x1800418b9  mov     [rsp+0E0h+var_C0], r12
0x1800418be  call    Pkcs11ConvertToKeyBlob
0x1800418c3  test    eax, eax
0x1800418c5  jns     short loc_1800418D2
0x1800418c7  mov     r9d, 5BBh
0x1800418cd  jmp     loc_180041C29
0x1800418d2  mov     ecx, [rbp+3Fh+var_80]
0x1800418d5  call    MSCryptAlloc
0x1800418da  mov     r14, rax
0x1800418dd  test    rax, rax
0x1800418e0  jnz     short loc_1800418F7
0x1800418e2  mov     ebx, 0C0000017h
0x1800418e7  mov     r9d, 5C2h
0x1800418ed  mov     ecx, 0C0000017h
0x1800418f2  jmp     loc_180041C33
0x1800418f7  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x1800418fb  lea     r9, [rbp+3Fh+var_80]
0x1800418ff  mov     r8, r14
0x180041902  mov     [rsp+0E0h+var_C0], r12
0x180041907  mov     rdx, rdi
0x18004190a  mov     rcx, rsi
0x18004190d  call    Pkcs11ConvertToKeyBlob
0x180041912  test    eax, eax
0x180041914  jns     short loc_180041942
0x180041916  mov     r9d, 5CFh
0x18004191c  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180041923  lea     rdx, aStatus; "Status"
0x18004192a  mov     ecx, 0C000000Dh
0x18004192f  mov     ebx, 0C000000Dh
0x180041934  call    DebugTraceError
0x180041939  mov     r13d, [rbp+3Fh+var_80]
0x18004193d  jmp     loc_180041C02
0x180041942  mov     r13d, [rbp+3Fh+var_80]
0x180041946  lea     rbx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18004194d  mov     edi, r13d
0x180041950  mov     rsi, r14
0x180041953  jmp     short loc_180041979
0x180041955  test    rdi, rdi
0x180041958  jz      short loc_18004196F
0x18004195a  mov     ebx, 0C00000BBh
0x18004195f  mov     r9d, 5D9h
0x180041965  mov     ecx, 0C00000BBh
0x18004196a  jmp     loc_180041C33
0x18004196f  mov     edi, [rbp+3Fh+arg_28]
0x180041972  xor     r14d, r14d
0x180041975  mov     rsi, [rbp+3Fh+arg_20]
0x180041979  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x180041980  mov     rcx, rbx; Str1
0x180041983  call    wcscmp_0
0x180041988  test    eax, eax
0x18004198a  jz      loc_180041A73
0x180041990  lea     rdx, aPublicblob; "PUBLICBLOB"
0x180041997  mov     rcx, rbx; Str1
0x18004199a  call    wcscmp_0
0x18004199f  test    eax, eax
0x1800419a1  jz      loc_180041A73
0x1800419a7  lea     rdx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x1800419ae  mov     rcx, rbx; Str1
0x1800419b1  call    wcscmp_0
0x1800419b6  test    eax, eax
0x1800419b8  jz      short loc_1800419F5
0x1800419ba  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x1800419c1  mov     rcx, rbx; Str1
0x1800419c4  call    wcscmp_0
0x1800419c9  test    eax, eax
0x1800419cb  jz      short loc_1800419F5
0x1800419cd  mov     ebx, 0C00000BBh
0x1800419d2  mov     r9d, 5F9h
0x1800419d8  mov     ecx, 0C00000BBh
0x1800419dd  lea     rdx, aStatus; "Status"
0x1800419e4  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800419eb  call    DebugTraceError
0x1800419f0  jmp     loc_180041BFD
0x1800419f5  mov     edx, edi
0x1800419f7  mov     rcx, rsi
0x1800419fa  call    VerifyRsaPrivateBlob
0x1800419ff  mov     ebx, eax
0x180041a01  test    eax, eax
0x180041a03  jz      short loc_180041A0F
0x180041a05  mov     r9d, 5F2h
0x180041a0b  mov     ecx, eax
0x180041a0d  jmp     short loc_1800419DD
0x180041a0f  mov     r12d, 1
0x180041a15  mov     edx, [rsi+4]
0x180041a18  lea     r8, [rbp+3Fh+P]
0x180041a1c  mov     ecx, [rsi+0Ch]
0x180041a1f  mov     eax, [rsi+8]
0x180041a22  mov     [rbp+3Fh+arg_28], eax
0x180041a25  lea     eax, [rdx+7]
0x180041a28  lea     r9d, ds:0[rcx*8]
0x180041a30  shr     eax, 3
0x180041a33  cmp     eax, ecx
0x180041a35  mov     rcx, [rbp+3Fh+var_68]
0x180041a39  cmovnb  r9d, edx
0x180041a3d  mov     edx, r9d
0x180041a40  mov     dword ptr [rbp+3Fh+arg_20], r9d
0x180041a44  call    CreateAndInitializeNewKey
0x180041a49  mov     ebx, eax
0x180041a4b  test    eax, eax
0x180041a4d  jns     short loc_180041A91
0x180041a4f  mov     r9d, 613h
0x180041a55  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180041a5c  lea     rdx, aStatus; "Status"
0x180041a63  mov     ecx, eax
0x180041a65  call    DebugTraceError
0x180041a6a  mov     rdi, [rbp+3Fh+P]
0x180041a6e  jmp     loc_180041BDA
0x180041a73  mov     edx, edi
0x180041a75  mov     rcx, rsi
0x180041a78  call    VerifyRsaPublicBlob
0x180041a7d  xor     r12d, r12d
0x180041a80  mov     ebx, eax
0x180041a82  test    eax, eax
0x180041a84  jz      short loc_180041A15
0x180041a86  mov     r9d, 5E7h
0x180041a8c  jmp     loc_180041A0B
0x180041a91  mov     rdi, [rbp+3Fh+P]
0x180041a95  mov     rcx, rdi
0x180041a98  call    AllocateSymcryptRsakey
0x180041a9d  mov     ebx, eax
0x180041a9f  test    eax, eax
0x180041aa1  jns     short loc_180041AC3
0x180041aa3  mov     r9d, 61Ah
0x180041aa9  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180041ab0  mov     ecx, eax
0x180041ab2  lea     rdx, aStatus; "Status"
0x180041ab9  call    DebugTraceError
0x180041abe  jmp     loc_180041BDA
0x180041ac3  mov     ebx, [rbp+3Fh+arg_28]
0x180041ac6  lea     rcx, [rsi+18h]
0x180041aca  add     rbx, rcx
0x180041acd  xor     r11d, r11d
0x180041ad0  test    r12d, r12d
0x180041ad3  jz      short loc_180041AFD
0x180041ad5  mov     edx, [rsi+0Ch]
0x180041ad8  mov     r11d, 2
0x180041ade  add     rdx, rbx
0x180041ae1  mov     qword ptr [rbp+3Fh+var_50], rdx
0x180041ae5  mov     eax, [rsi+10h]
0x180041ae8  mov     qword ptr [rbp+3Fh+var_60], rax
0x180041aec  mov     eax, [rsi+10h]
0x180041aef  add     rax, rdx
0x180041af2  mov     qword ptr [rbp+3Fh+var_50+8], rax
0x180041af6  mov     eax, [rsi+14h]
0x180041af9  mov     qword ptr [rbp+3Fh+var_60+8], rax
0x180041afd  mov     edx, [rsi+8]
0x180041b00  lea     r8, [rbp+3Fh+var_70]
0x180041b04  call    SymCryptLoadMsbFirstUint64
0x180041b09  test    eax, eax
0x180041b0b  jz      short loc_180041B1E
0x180041b0d  mov     ecx, eax
0x180041b0f  call    SymcryptErrorCodeToNtStatus
0x180041b14  mov     ebx, eax
0x180041b16  mov     r9d, 62Dh
0x180041b1c  jmp     short loc_180041AA9
0x180041b1e  mov     ecx, [rbp+3Fh+arg_30]
0x180041b21  call    BCryptFlagsToSymCryptKeyValidationFlags
0x180041b26  cmp     r15d, 4
0x180041b2a  jnz     short loc_180041B33
0x180041b2c  or      eax, 3100h
0x180041b31  jmp     short loc_180041B49
0x180041b33  cmp     r15d, 1
0x180041b37  jnz     short loc_180041B3F
0x180041b39  bts     eax, 0Ch
0x180041b3d  jmp     short loc_180041B49
0x180041b3f  cmp     r15d, 2
0x180041b43  jnz     short loc_180041B49
0x180041b45  bts     eax, 0Dh
0x180041b49  mov     edx, [rsi+0Ch]
0x180041b4c  mov     r8d, eax
0x180041b4f  bts     r8d, 8
0x180041b54  mov     r9d, 1
0x180041b5a  cmp     dword ptr [rbp+3Fh+arg_20], 400h
0x180041b61  mov     rcx, rbx
0x180041b64  cmovnb  r8d, eax
0x180041b68  mov     rax, [rdi+20h]
0x180041b6c  mov     [rsp+0E0h+var_88], rax
0x180041b71  lea     rax, [rbp+3Fh+var_60]
0x180041b75  mov     [rsp+0E0h+var_90], r8d
0x180041b7a  lea     r8, [rbp+3Fh+var_70]
0x180041b7e  mov     [rsp+0E0h+var_98], 2
0x180041b86  mov     [rsp+0E0h+var_A0], r11d
0x180041b8b  mov     [rsp+0E0h+var_A8], rax
0x180041b90  lea     rax, [rbp+3Fh+var_50]
0x180041b94  mov     [rsp+0E0h+var_B0], rax
0x180041b99  mov     [rsp+0E0h+var_B8], 0
0x180041ba2  mov     [rsp+0E0h+var_C0], 0
0x180041bab  call    SymCryptRsakeySetValueInternal
0x180041bb0  test    eax, eax
0x180041bb2  jz      short loc_180041BC8
0x180041bb4  mov     ecx, eax
0x180041bb6  call    SymcryptErrorCodeToNtStatus
0x180041bbb  mov     ebx, eax
0x180041bbd  mov     r9d, 657h
0x180041bc3  jmp     loc_180041AA9
0x180041bc8  mov     rax, [rbp+3Fh+arg_18]
0x180041bcc  mov     dword ptr [rdi+10h], 1
0x180041bd3  mov     [rax], rdi
0x180041bd6  xor     edi, edi
0x180041bd8  xor     ebx, ebx
0x180041bda  test    rdi, rdi
0x180041bdd  jz      short loc_180041BFD
0x180041bdf  mov     rcx, [rdi+20h]
0x180041be3  test    rcx, rcx
0x180041be6  jz      short loc_180041BF5
0x180041be8  call    SymCryptRsakeyFree
0x180041bed  mov     qword ptr [rdi+20h], 0
0x180041bf5  mov     rcx, rdi; P
0x180041bf8  call    MSCryptFree
0x180041bfd  test    r14, r14
0x180041c00  jz      short loc_180041C46
0x180041c02  mov     ecx, r13d
0x180041c05  mov     rax, r14
0x180041c08  test    r13d, r13d
0x180041c0b  jz      short loc_180041C19
0x180041c0d  mov     byte ptr [rax], 0
0x180041c10  inc     rax
0x180041c13  sub     rcx, 1
0x180041c17  jnz     short loc_180041C0D
0x180041c19  mov     rcx, r14; P
0x180041c1c  call    MSCryptFree
0x180041c21  jmp     short loc_180041C46
0x180041c23  mov     r9d, 59Ch
0x180041c29  mov     ebx, 0C000000Dh
0x180041c2e  mov     ecx, 0C000000Dh
0x180041c33  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180041c3a  lea     rdx, aStatus; "Status"
0x180041c41  call    DebugTraceError
0x180041c46  mov     eax, ebx
0x180041c48  add     rsp, 0A8h
0x180041c4f  pop     r15
0x180041c51  pop     r14
0x180041c53  pop     r13
0x180041c55  pop     r12
0x180041c57  pop     rdi
0x180041c58  pop     rsi
0x180041c59  pop     rbx
0x180041c5a  pop     rbp
0x180041c5b  retn
```
