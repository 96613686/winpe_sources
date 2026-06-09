# MSCryptRsaImportKeyPair

- ea: `0x18004235c`
- end: `0x1800427ed`
- name: `MSCryptRsaImportKeyPair`
- size: `1169`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180042320`
- `0x180074dfc`
- `0x180078a70`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x18001cafc`
- `0x180040578`
- `0x180040818`
- `0x1800410d8`
- `0x180041ec4`
- `0x1800421d8`
- `0x18004235c`
- `0x18004288c`
- `0x180048770`
- `0x180048b44`
- `0x18007f0f8`
- `0x18009f480`
- `0x18009f616`

## string_xrefs

- `0x1800424ac`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180042574`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x1800425e5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180042639`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x1800427c3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

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
  __int64 v16; // r8
  __int64 v17; // r9
  _DWORD *v18; // rax
  _DWORD *v19; // r14
  unsigned int v20; // edi
  _DWORD *v21; // rsi
  __int64 v22; // r9
  __int64 v23; // rcx
  unsigned int v24; // eax
  int v25; // r12d
  unsigned int v26; // ecx
  unsigned int v27; // r9d
  int v28; // eax
  _QWORD *v29; // rdi
  int SymcryptRsakey; // eax
  __int64 v31; // r9
  __int64 v32; // rbx
  unsigned int v33; // eax
  int v34; // eax
  int v35; // r11d
  int v36; // r8d
  unsigned int v37; // eax
  __int64 v38; // rcx
  _BYTE *v39; // rax
  unsigned int v41; // [rsp+60h] [rbp-41h] BYREF
  PVOID P; // [rsp+68h] [rbp-39h] BYREF
  __int64 v43; // [rsp+70h] [rbp-31h] BYREF
  __int64 v44; // [rsp+78h] [rbp-29h]
  __int128 v45; // [rsp+80h] [rbp-21h] BYREF
  __int128 v46; // [rsp+90h] [rbp-11h] BYREF
  unsigned int v48; // [rsp+110h] [rbp+6Fh]
  unsigned int v49; // [rsp+118h] [rbp+77h]

  v8 = 0;
  v43 = 0;
  P = 0;
  v41 = 0;
  *a4 = 0;
  v46 = 0;
  v45 = 0;
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
  v44 = validateMSCryptRsaAlgorithm();
  if ( !v44 )
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
    v20 = a6;
    v19 = 0;
    v21 = a5;
LABEL_21:
    if ( !wcscmp_0(a3, L"RSAPUBLICBLOB") || !wcscmp_0(a3, L"PUBLICBLOB") )
    {
      v24 = VerifyRsaPublicBlob(v21, v20);
      v25 = 0;
      v13 = v24;
      if ( v24 )
      {
        v22 = 1511;
        goto LABEL_29;
      }
    }
    else
    {
      if ( wcscmp_0(a3, L"RSAPRIVATEBLOB") && wcscmp_0(a3, L"PRIVATEBLOB") )
      {
        v13 = -1073741637;
        v22 = 1529;
        v23 = 3221225659LL;
LABEL_26:
        DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v22);
        goto LABEL_59;
      }
      v24 = VerifyRsaPrivateBlob(v21, v20);
      v13 = v24;
      if ( v24 )
      {
        v22 = 1522;
LABEL_29:
        v23 = v24;
        goto LABEL_26;
      }
      v25 = 1;
    }
    v26 = v21[3];
    v49 = v21[2];
    v27 = 8 * v26;
    if ( (unsigned int)(v21[1] + 7) >> 3 >= v26 )
      v27 = v21[1];
    v48 = v27;
    v28 = CreateAndInitializeNewKey(v44, v27, &P);
    v13 = v28;
    if ( v28 < 0 )
    {
      DebugTraceError((unsigned int)v28, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 1555);
      v29 = P;
      goto LABEL_55;
    }
    v29 = P;
    SymcryptRsakey = AllocateSymcryptRsakey(P);
    v13 = SymcryptRsakey;
    if ( SymcryptRsakey >= 0 )
    {
      v32 = (__int64)v21 + v49 + 24;
      if ( v25 )
      {
        *(_QWORD *)&v46 = v32 + (unsigned int)v21[3];
        *(_QWORD *)&v45 = (unsigned int)v21[4];
        *((_QWORD *)&v46 + 1) = v46 + (unsigned int)v21[4];
        *((_QWORD *)&v45 + 1) = (unsigned int)v21[5];
      }
      v33 = SymCryptLoadMsbFirstUint64(v21 + 6, (unsigned int)v21[2], &v43);
      if ( v33 )
      {
        SymcryptRsakey = SymcryptErrorCodeToNtStatus(v33);
        v13 = SymcryptRsakey;
        v31 = 1581;
      }
      else
      {
        v34 = BCryptFlagsToSymCryptKeyValidationFlags(a7);
        switch ( a8 )
        {
          case 4:
            v34 |= 0x3100u;
            break;
          case 1:
            v34 |= 0x1000u;
            break;
          case 2:
            v34 |= 0x2000u;
            break;
        }
        v36 = v34 | 0x100;
        if ( v48 >= 0x400 )
          v36 = v34;
        v37 = SymCryptRsakeySetValueInternal(
                v32,
                v21[3],
                (unsigned int)&v43,
                1,
                0,
                0,
                (__int64)&v46,
                (__int64)&v45,
                v35,
                2,
                v36,
                v29[4]);
        if ( !v37 )
        {
          *((_DWORD *)v29 + 4) = 1;
          *a4 = v29;
          v29 = 0;
          v13 = 0;
LABEL_55:
          if ( v29 )
          {
            if ( v29[4] )
            {
              SymCryptRsakeyFree();
              v29[4] = 0;
            }
            MSCryptFree(v29);
          }
LABEL_59:
          if ( !v19 )
            return v13;
          goto LABEL_60;
        }
        SymcryptRsakey = SymcryptErrorCodeToNtStatus(v37);
        v13 = SymcryptRsakey;
        v31 = 1623;
      }
    }
    else
    {
      v31 = 1562;
    }
    DebugTraceError(
      (unsigned int)SymcryptRsakey,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
      v31);
    goto LABEL_55;
  }
  if ( !a2 )
  {
    v12 = 1454;
    goto LABEL_64;
  }
  if ( (int)Pkcs11ConvertToKeyBlob(a1, a2, 0, &v41, a5, a6) < 0 )
  {
    v12 = 1467;
    goto LABEL_64;
  }
  v18 = (_DWORD *)MSCryptAlloc(v41, v15, v16, v17);
  v19 = v18;
  if ( !v18 )
  {
    v13 = -1073741801;
    v12 = 1474;
    v14 = 3221225495LL;
    goto LABEL_65;
  }
  if ( (int)Pkcs11ConvertToKeyBlob(a1, a2, v18, &v41, a5, a6) >= 0 )
  {
    v8 = v41;
    a3 = L"RSAPRIVATEBLOB";
    v20 = v41;
    v21 = v19;
    goto LABEL_21;
  }
  v13 = -1073741811;
  DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 1487);
  v8 = v41;
LABEL_60:
  v38 = v8;
  v39 = v19;
  if ( v8 )
  {
    do
    {
      *v39++ = 0;
      --v38;
    }
    while ( v38 );
  }
  MSCryptFree(v19);
  return v13;
}

```

## disassembly

```asm
0x18004235c  mov     [rsp-8+arg_18], r9
0x180042361  push    rbp
0x180042362  push    rbx
0x180042363  push    rsi
0x180042364  push    rdi
0x180042365  push    r12
0x180042367  push    r13
0x180042369  push    r14
0x18004236b  push    r15
0x18004236d  lea     rbp, [rsp-7]
0x180042372  sub     rsp, 0A8h
0x180042379  xor     r13d, r13d
0x18004237c  mov     [rbp+3Fh+var_70], 0
0x180042384  test    [rbp+3Fh+arg_30], 0FFFFFFF7h
0x18004238b  xorps   xmm0, xmm0
0x18004238e  xorps   xmm1, xmm1
0x180042391  mov     [rbp+3Fh+P], 0
0x180042399  mov     rbx, r8
0x18004239c  mov     [rbp+3Fh+var_80], r13d
0x1800423a0  mov     rdi, rdx
0x1800423a3  mov     [r9], r13
0x1800423a6  mov     rsi, rcx
0x1800423a9  movups  [rbp+3Fh+var_50], xmm0
0x1800423ad  movups  [rbp+3Fh+var_60], xmm1
0x1800423b1  jz      short loc_1800423BE
0x1800423b3  mov     r9d, 593h
0x1800423b9  jmp     loc_1800427B9
0x1800423be  mov     r15d, [rbp+3Fh+arg_38]
0x1800423c5  lea     eax, [r15-1]
0x1800423c9  test    eax, 0FFFFFFFCh
0x1800423ce  jnz     loc_1800427B3
0x1800423d4  cmp     r15d, 3
0x1800423d8  jz      loc_1800427B3
0x1800423de  call    validateMSCryptRsaAlgorithm
0x1800423e3  mov     [rbp+3Fh+var_68], rax
0x1800423e7  test    rax, rax
0x1800423ea  jnz     short loc_180042401
0x1800423ec  mov     ebx, 0C0000008h
0x1800423f1  mov     r9d, 5A4h
0x1800423f7  mov     ecx, 0C0000008h
0x1800423fc  jmp     loc_1800427C3
0x180042401  test    rbx, rbx
0x180042404  jz      loc_1800424E5
0x18004240a  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x180042411  mov     rcx, rbx; Str1
0x180042414  call    wcscmp_0
0x180042419  test    eax, eax
0x18004241b  jnz     loc_1800424E5
0x180042421  test    rdi, rdi
0x180042424  jnz     short loc_180042431
0x180042426  mov     r9d, 5AEh
0x18004242c  jmp     loc_1800427B9
0x180042431  mov     ebx, [rbp+3Fh+arg_28]
0x180042434  lea     r9, [rbp+3Fh+var_80]
0x180042438  mov     r12, [rbp+3Fh+arg_20]
0x18004243c  xor     r8d, r8d
0x18004243f  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x180042443  mov     rdx, rdi
0x180042446  mov     rcx, rsi
0x180042449  mov     [rsp+0E0h+var_C0], r12
0x18004244e  call    Pkcs11ConvertToKeyBlob
0x180042453  test    eax, eax
0x180042455  jns     short loc_180042462
0x180042457  mov     r9d, 5BBh
0x18004245d  jmp     loc_1800427B9
0x180042462  mov     ecx, [rbp+3Fh+var_80]
0x180042465  call    MSCryptAlloc
0x18004246a  mov     r14, rax
0x18004246d  test    rax, rax
0x180042470  jnz     short loc_180042487
0x180042472  mov     ebx, 0C0000017h
0x180042477  mov     r9d, 5C2h
0x18004247d  mov     ecx, 0C0000017h
0x180042482  jmp     loc_1800427C3
0x180042487  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x18004248b  lea     r9, [rbp+3Fh+var_80]
0x18004248f  mov     r8, r14
0x180042492  mov     [rsp+0E0h+var_C0], r12
0x180042497  mov     rdx, rdi
0x18004249a  mov     rcx, rsi
0x18004249d  call    Pkcs11ConvertToKeyBlob
0x1800424a2  test    eax, eax
0x1800424a4  jns     short loc_1800424D2
0x1800424a6  mov     r9d, 5CFh
0x1800424ac  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800424b3  lea     rdx, aStatus; "Status"
0x1800424ba  mov     ecx, 0C000000Dh
0x1800424bf  mov     ebx, 0C000000Dh
0x1800424c4  call    DebugTraceError
0x1800424c9  mov     r13d, [rbp+3Fh+var_80]
0x1800424cd  jmp     loc_180042792
0x1800424d2  mov     r13d, [rbp+3Fh+var_80]
0x1800424d6  lea     rbx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x1800424dd  mov     edi, r13d
0x1800424e0  mov     rsi, r14
0x1800424e3  jmp     short loc_180042509
0x1800424e5  test    rdi, rdi
0x1800424e8  jz      short loc_1800424FF
0x1800424ea  mov     ebx, 0C00000BBh
0x1800424ef  mov     r9d, 5D9h
0x1800424f5  mov     ecx, 0C00000BBh
0x1800424fa  jmp     loc_1800427C3
0x1800424ff  mov     edi, [rbp+3Fh+arg_28]
0x180042502  xor     r14d, r14d
0x180042505  mov     rsi, [rbp+3Fh+arg_20]
0x180042509  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x180042510  mov     rcx, rbx; Str1
0x180042513  call    wcscmp_0
0x180042518  test    eax, eax
0x18004251a  jz      loc_180042603
0x180042520  lea     rdx, aPublicblob; "PUBLICBLOB"
0x180042527  mov     rcx, rbx; Str1
0x18004252a  call    wcscmp_0
0x18004252f  test    eax, eax
0x180042531  jz      loc_180042603
0x180042537  lea     rdx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18004253e  mov     rcx, rbx; Str1
0x180042541  call    wcscmp_0
0x180042546  test    eax, eax
0x180042548  jz      short loc_180042585
0x18004254a  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x180042551  mov     rcx, rbx; Str1
0x180042554  call    wcscmp_0
0x180042559  test    eax, eax
0x18004255b  jz      short loc_180042585
0x18004255d  mov     ebx, 0C00000BBh
0x180042562  mov     r9d, 5F9h
0x180042568  mov     ecx, 0C00000BBh
0x18004256d  lea     rdx, aStatus; "Status"
0x180042574  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004257b  call    DebugTraceError
0x180042580  jmp     loc_18004278D
0x180042585  mov     edx, edi
0x180042587  mov     rcx, rsi
0x18004258a  call    VerifyRsaPrivateBlob
0x18004258f  mov     ebx, eax
0x180042591  test    eax, eax
0x180042593  jz      short loc_18004259F
0x180042595  mov     r9d, 5F2h
0x18004259b  mov     ecx, eax
0x18004259d  jmp     short loc_18004256D
0x18004259f  mov     r12d, 1
0x1800425a5  mov     edx, [rsi+4]
0x1800425a8  lea     r8, [rbp+3Fh+P]
0x1800425ac  mov     ecx, [rsi+0Ch]
0x1800425af  mov     eax, [rsi+8]
0x1800425b2  mov     [rbp+3Fh+arg_28], eax
0x1800425b5  lea     eax, [rdx+7]
0x1800425b8  lea     r9d, ds:0[rcx*8]
0x1800425c0  shr     eax, 3
0x1800425c3  cmp     eax, ecx
0x1800425c5  mov     rcx, [rbp+3Fh+var_68]
0x1800425c9  cmovnb  r9d, edx
0x1800425cd  mov     edx, r9d
0x1800425d0  mov     dword ptr [rbp+3Fh+arg_20], r9d
0x1800425d4  call    CreateAndInitializeNewKey
0x1800425d9  mov     ebx, eax
0x1800425db  test    eax, eax
0x1800425dd  jns     short loc_180042621
0x1800425df  mov     r9d, 613h
0x1800425e5  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800425ec  lea     rdx, aStatus; "Status"
0x1800425f3  mov     ecx, eax
0x1800425f5  call    DebugTraceError
0x1800425fa  mov     rdi, [rbp+3Fh+P]
0x1800425fe  jmp     loc_18004276A
0x180042603  mov     edx, edi
0x180042605  mov     rcx, rsi
0x180042608  call    VerifyRsaPublicBlob
0x18004260d  xor     r12d, r12d
0x180042610  mov     ebx, eax
0x180042612  test    eax, eax
0x180042614  jz      short loc_1800425A5
0x180042616  mov     r9d, 5E7h
0x18004261c  jmp     loc_18004259B
0x180042621  mov     rdi, [rbp+3Fh+P]
0x180042625  mov     rcx, rdi
0x180042628  call    AllocateSymcryptRsakey
0x18004262d  mov     ebx, eax
0x18004262f  test    eax, eax
0x180042631  jns     short loc_180042653
0x180042633  mov     r9d, 61Ah
0x180042639  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180042640  mov     ecx, eax
0x180042642  lea     rdx, aStatus; "Status"
0x180042649  call    DebugTraceError
0x18004264e  jmp     loc_18004276A
0x180042653  mov     ebx, [rbp+3Fh+arg_28]
0x180042656  lea     rcx, [rsi+18h]
0x18004265a  add     rbx, rcx
0x18004265d  xor     r11d, r11d
0x180042660  test    r12d, r12d
0x180042663  jz      short loc_18004268D
0x180042665  mov     edx, [rsi+0Ch]
0x180042668  mov     r11d, 2
0x18004266e  add     rdx, rbx
0x180042671  mov     qword ptr [rbp+3Fh+var_50], rdx
0x180042675  mov     eax, [rsi+10h]
0x180042678  mov     qword ptr [rbp+3Fh+var_60], rax
0x18004267c  mov     eax, [rsi+10h]
0x18004267f  add     rax, rdx
0x180042682  mov     qword ptr [rbp+3Fh+var_50+8], rax
0x180042686  mov     eax, [rsi+14h]
0x180042689  mov     qword ptr [rbp+3Fh+var_60+8], rax
0x18004268d  mov     edx, [rsi+8]
0x180042690  lea     r8, [rbp+3Fh+var_70]
0x180042694  call    SymCryptLoadMsbFirstUint64
0x180042699  test    eax, eax
0x18004269b  jz      short loc_1800426AE
0x18004269d  mov     ecx, eax
0x18004269f  call    SymcryptErrorCodeToNtStatus
0x1800426a4  mov     ebx, eax
0x1800426a6  mov     r9d, 62Dh
0x1800426ac  jmp     short loc_180042639
0x1800426ae  mov     ecx, [rbp+3Fh+arg_30]
0x1800426b1  call    BCryptFlagsToSymCryptKeyValidationFlags
0x1800426b6  cmp     r15d, 4
0x1800426ba  jnz     short loc_1800426C3
0x1800426bc  or      eax, 3100h
0x1800426c1  jmp     short loc_1800426D9
0x1800426c3  cmp     r15d, 1
0x1800426c7  jnz     short loc_1800426CF
0x1800426c9  bts     eax, 0Ch
0x1800426cd  jmp     short loc_1800426D9
0x1800426cf  cmp     r15d, 2
0x1800426d3  jnz     short loc_1800426D9
0x1800426d5  bts     eax, 0Dh
0x1800426d9  mov     edx, [rsi+0Ch]
0x1800426dc  mov     r8d, eax
0x1800426df  bts     r8d, 8
0x1800426e4  mov     r9d, 1
0x1800426ea  cmp     dword ptr [rbp+3Fh+arg_20], 400h
0x1800426f1  mov     rcx, rbx
0x1800426f4  cmovnb  r8d, eax
0x1800426f8  mov     rax, [rdi+20h]
0x1800426fc  mov     [rsp+0E0h+var_88], rax
0x180042701  lea     rax, [rbp+3Fh+var_60]
0x180042705  mov     [rsp+0E0h+var_90], r8d
0x18004270a  lea     r8, [rbp+3Fh+var_70]
0x18004270e  mov     [rsp+0E0h+var_98], 2
0x180042716  mov     [rsp+0E0h+var_A0], r11d
0x18004271b  mov     [rsp+0E0h+var_A8], rax
0x180042720  lea     rax, [rbp+3Fh+var_50]
0x180042724  mov     [rsp+0E0h+var_B0], rax
0x180042729  mov     [rsp+0E0h+var_B8], 0
0x180042732  mov     [rsp+0E0h+var_C0], 0
0x18004273b  call    SymCryptRsakeySetValueInternal
0x180042740  test    eax, eax
0x180042742  jz      short loc_180042758
0x180042744  mov     ecx, eax
0x180042746  call    SymcryptErrorCodeToNtStatus
0x18004274b  mov     ebx, eax
0x18004274d  mov     r9d, 657h
0x180042753  jmp     loc_180042639
0x180042758  mov     rax, [rbp+3Fh+arg_18]
0x18004275c  mov     dword ptr [rdi+10h], 1
0x180042763  mov     [rax], rdi
0x180042766  xor     edi, edi
0x180042768  xor     ebx, ebx
0x18004276a  test    rdi, rdi
0x18004276d  jz      short loc_18004278D
0x18004276f  mov     rcx, [rdi+20h]
0x180042773  test    rcx, rcx
0x180042776  jz      short loc_180042785
0x180042778  call    SymCryptRsakeyFree
0x18004277d  mov     qword ptr [rdi+20h], 0
0x180042785  mov     rcx, rdi; P
0x180042788  call    MSCryptFree
0x18004278d  test    r14, r14
0x180042790  jz      short loc_1800427D6
0x180042792  mov     ecx, r13d
0x180042795  mov     rax, r14
0x180042798  test    r13d, r13d
0x18004279b  jz      short loc_1800427A9
0x18004279d  mov     byte ptr [rax], 0
0x1800427a0  inc     rax
0x1800427a3  sub     rcx, 1
0x1800427a7  jnz     short loc_18004279D
0x1800427a9  mov     rcx, r14; P
0x1800427ac  call    MSCryptFree
0x1800427b1  jmp     short loc_1800427D6
0x1800427b3  mov     r9d, 59Ch
0x1800427b9  mov     ebx, 0C000000Dh
0x1800427be  mov     ecx, 0C000000Dh
0x1800427c3  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800427ca  lea     rdx, aStatus; "Status"
0x1800427d1  call    DebugTraceError
0x1800427d6  mov     eax, ebx
0x1800427d8  add     rsp, 0A8h
0x1800427df  pop     r15
0x1800427e1  pop     r14
0x1800427e3  pop     r13
0x1800427e5  pop     r12
0x1800427e7  pop     rdi
0x1800427e8  pop     rsi
0x1800427e9  pop     rbx
0x1800427ea  pop     rbp
0x1800427eb  retn
```
