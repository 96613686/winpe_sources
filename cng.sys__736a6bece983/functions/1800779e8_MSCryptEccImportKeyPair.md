# MSCryptEccImportKeyPair

- ea: `0x1800779e8`
- end: `0x180077dbe`
- name: `MSCryptEccImportKeyPair`
- size: `982`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800764f0`
- `0x180076900`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x1800414cc`
- `0x18004623c`
- `0x180075df0`
- `0x180076d9c`
- `0x1800779e8`
- `0x18007f0f8`
- `0x18009f616`

## string_xrefs

- `0x180077a38`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180077b46`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180077d2d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180077d60`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccImportKeyPair(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        _QWORD *a4,
        int *a5,
        unsigned int a6,
        int a7,
        unsigned int a8,
        _DWORD *a9)
{
  int *v9; // r14
  __int64 v13; // rsi
  unsigned int v14; // ebx
  __int64 v15; // r9
  __int64 v16; // rcx
  int v17; // eax
  int *v18; // r12
  unsigned int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  int v23; // eax
  unsigned int v24; // r15d
  BOOL v25; // ecx
  int v26; // eax
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // r9
  __int64 v30; // rax
  __int64 v31; // rcx
  int *v32; // rax
  unsigned int v34; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v35; // [rsp+44h] [rbp-24h] BYREF
  __int64 v36; // [rsp+48h] [rbp-20h] BYREF
  __int64 v37[3]; // [rsp+50h] [rbp-18h] BYREF

  v9 = 0;
  v37[0] = 0;
  v35 = 0;
  v13 = 0;
  v36 = 0;
  v34 = 0;
  if ( (a7 & 0xFFFFFFC7) != 0 )
  {
    v14 = -1073741811;
    v15 = 3014;
    v16 = 3221225485LL;
LABEL_3:
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v15);
    return v14;
  }
  v17 = ValidateEccAlgorithm(a1, 0, a8, (unsigned int)&v35, (__int64)v37);
  v14 = v17;
  if ( v17 < 0 )
  {
    v15 = 3021;
LABEL_6:
    v16 = (unsigned int)v17;
    goto LABEL_3;
  }
  v18 = a5;
  if ( !a5 || (v19 = a6, a6 < 4) )
  {
    v24 = v34;
    v14 = -1073741811;
    v28 = 3221225485LL;
    v29 = 3029;
LABEL_52:
    DebugTraceError(v28, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v29);
    if ( v13 )
      MSCryptEccDestroyKeyPair(v13, a8);
LABEL_54:
    if ( !v9 )
      return v14;
    goto LABEL_55;
  }
  if ( !a3 || wcscmp_0(a3, L"PKCS11RsaAesWrapBlob") )
  {
    if ( a2 )
    {
      v14 = -1073741637;
      v15 = 3080;
      v16 = 3221225659LL;
      goto LABEL_3;
    }
    v24 = v34;
LABEL_23:
    if ( !wcscmp_0(a3, L"PUBLICBLOB") )
    {
      *a9 = 0;
      v25 = *v18 == 1346650949 || *v18 == 1347109701;
      v26 = 0;
    }
    else
    {
      if ( wcscmp_0(a3, L"PRIVATEBLOB") )
      {
        if ( !wcscmp_0(a3, L"ECCPUBLICBLOB") )
        {
          *a9 = 0;
          v26 = 0;
        }
        else
        {
          if ( wcscmp_0(a3, L"ECCPRIVATEBLOB") )
          {
            if ( !wcscmp_0(a3, L"ECCFULLPUBLICBLOB") )
            {
              *a9 = 0;
              v26 = 0;
            }
            else
            {
              if ( wcscmp_0(a3, L"ECCFULLPRIVATEBLOB") )
              {
                v14 = -1073741637;
                DebugTraceError(
                  3221225659LL,
                  "Status",
                  "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                  3134);
                goto LABEL_54;
              }
              *a9 = 1;
              v26 = 1;
            }
            goto LABEL_46;
          }
          *a9 = 1;
          v26 = 1;
        }
LABEL_41:
        v27 = ImportEccKeyBlobWithoutParameters(v37[0], v18, v19, v35, a8, v26, a7, &v36);
LABEL_47:
        v14 = v27;
        if ( v27 >= 0 )
        {
          v30 = v36;
          *(_DWORD *)(v36 + 32) |= 2u;
          v14 = 0;
          *a4 = v30;
          goto LABEL_54;
        }
        v13 = v36;
        v28 = (unsigned int)v27;
        v29 = 3163;
        goto LABEL_52;
      }
      *a9 = 1;
      v25 = *v18 == 1447314245 || *v18 == 1447772997;
      v26 = 1;
    }
    if ( v25 )
    {
LABEL_46:
      v27 = ImportEccKeyBlobWithParameters(v37[0], (_DWORD)v18, v19, a8, v26, a7, (__int64)&v36);
      goto LABEL_47;
    }
    goto LABEL_41;
  }
  if ( !a2 )
  {
    v14 = -1073741816;
    v15 = 3039;
    v16 = 3221225480LL;
    goto LABEL_3;
  }
  v17 = Pkcs11ConvertToKeyBlob(a1, a2, 0, &v34, a5, a6);
  v14 = v17;
  if ( v17 < 0 )
  {
    v15 = 3051;
    goto LABEL_6;
  }
  v9 = (int *)MSCryptAlloc(v34, v20, v21, v22);
  if ( !v9 )
  {
    v14 = -1073741801;
    v15 = 3058;
    v16 = 3221225495LL;
    goto LABEL_3;
  }
  v23 = Pkcs11ConvertToKeyBlob(a1, a2, v9, &v34, a5, a6);
  v14 = v23;
  if ( v23 >= 0 )
  {
    v24 = v34;
    a3 = L"ECCPRIVATEBLOB";
    v19 = v34;
    v18 = v9;
    goto LABEL_23;
  }
  DebugTraceError((unsigned int)v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 3070);
  v24 = v34;
LABEL_55:
  v31 = v24;
  v32 = v9;
  if ( v24 )
  {
    do
    {
      *(_BYTE *)v32 = 0;
      v32 = (int *)((char *)v32 + 1);
      --v31;
    }
    while ( v31 );
  }
  MSCryptFree(v9);
  return v14;
}

```

## disassembly

```asm
0x1800779e8  mov     [rsp-40h+arg_18], r9
0x1800779ed  push    rbp
0x1800779ee  push    rbx
0x1800779ef  push    rsi
0x1800779f0  push    rdi
0x1800779f1  push    r12
0x1800779f3  push    r13
0x1800779f5  push    r14
0x1800779f7  push    r15
0x1800779f9  mov     rbp, rsp
0x1800779fc  sub     rsp, 68h
0x180077a00  xor     r14d, r14d
0x180077a03  mov     rdi, r8
0x180077a06  test    [rbp+arg_30], 0FFFFFFC7h
0x180077a0d  mov     r15, rdx
0x180077a10  mov     r13, rcx
0x180077a13  mov     [rbp+var_18], r14
0x180077a17  mov     [rbp+var_24], r14d
0x180077a1b  mov     esi, r14d
0x180077a1e  mov     [rbp+var_20], r14
0x180077a22  mov     [rbp+var_28], r14d
0x180077a26  jz      short loc_180077A50
0x180077a28  mov     ebx, 0C000000Dh
0x180077a2d  mov     r9d, 0BC6h
0x180077a33  mov     ecx, 0C000000Dh
0x180077a38  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180077a3f  lea     rdx, aStatus; "Status"
0x180077a46  call    DebugTraceError
0x180077a4b  jmp     loc_180077DAA
0x180077a50  mov     r8d, [rbp+arg_38]
0x180077a57  lea     rax, [rbp+var_18]
0x180077a5b  lea     r9, [rbp+var_24]
0x180077a5f  mov     [rsp+68h+var_48], rax
0x180077a64  xor     edx, edx
0x180077a66  call    ValidateEccAlgorithm
0x180077a6b  mov     ebx, eax
0x180077a6d  test    eax, eax
0x180077a6f  jns     short loc_180077A7B
0x180077a71  mov     r9d, 0BCDh
0x180077a77  mov     ecx, eax
0x180077a79  jmp     short loc_180077A38
0x180077a7b  mov     r12, [rbp+arg_20]
0x180077a7f  test    r12, r12
0x180077a82  jz      loc_180077D4C
0x180077a88  mov     ebx, [rbp+arg_28]
0x180077a8b  cmp     ebx, 4
0x180077a8e  jb      loc_180077D4C
0x180077a94  test    rdi, rdi
0x180077a97  jz      loc_180077B77
0x180077a9d  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x180077aa4  mov     rcx, rdi; Str1
0x180077aa7  call    wcscmp_0
0x180077aac  test    eax, eax
0x180077aae  jnz     loc_180077B77
0x180077ab4  test    r15, r15
0x180077ab7  jnz     short loc_180077ACE
0x180077ab9  mov     ebx, 0C0000008h
0x180077abe  mov     r9d, 0BDFh
0x180077ac4  mov     ecx, 0C0000008h
0x180077ac9  jmp     loc_180077A38
0x180077ace  mov     [rsp+68h+var_40], ebx
0x180077ad2  lea     r9, [rbp+var_28]
0x180077ad6  xor     r8d, r8d
0x180077ad9  mov     [rsp+68h+var_48], r12
0x180077ade  mov     rdx, r15
0x180077ae1  mov     rcx, r13
0x180077ae4  call    Pkcs11ConvertToKeyBlob
0x180077ae9  mov     ebx, eax
0x180077aeb  test    eax, eax
0x180077aed  jns     short loc_180077AF7
0x180077aef  mov     r9d, 0BEBh
0x180077af5  jmp     short loc_180077A77
0x180077af7  mov     ecx, [rbp+var_28]
0x180077afa  call    MSCryptAlloc
0x180077aff  mov     r14, rax
0x180077b02  test    rax, rax
0x180077b05  jnz     short loc_180077B1C
0x180077b07  mov     ebx, 0C0000017h
0x180077b0c  mov     r9d, 0BF2h
0x180077b12  mov     ecx, 0C0000017h
0x180077b17  jmp     loc_180077A38
0x180077b1c  mov     eax, [rbp+arg_28]
0x180077b1f  lea     r9, [rbp+var_28]
0x180077b23  mov     [rsp+68h+var_40], eax
0x180077b27  mov     r8, r14
0x180077b2a  mov     rdx, r15
0x180077b2d  mov     [rsp+68h+var_48], r12
0x180077b32  mov     rcx, r13
0x180077b35  call    Pkcs11ConvertToKeyBlob
0x180077b3a  mov     ebx, eax
0x180077b3c  test    eax, eax
0x180077b3e  jns     short loc_180077B64
0x180077b40  mov     r9d, 0BFEh
0x180077b46  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180077b4d  lea     rdx, aStatus; "Status"
0x180077b54  mov     ecx, eax
0x180077b56  call    DebugTraceError
0x180077b5b  mov     r15d, [rbp+var_28]
0x180077b5f  jmp     loc_180077D8B
0x180077b64  mov     r15d, [rbp+var_28]
0x180077b68  lea     rdi, aEccprivateblob; "ECCPRIVATEBLOB"
0x180077b6f  mov     ebx, r15d
0x180077b72  mov     r12, r14
0x180077b75  jmp     short loc_180077B95
0x180077b77  test    r15, r15
0x180077b7a  jz      short loc_180077B91
0x180077b7c  mov     ebx, 0C00000BBh
0x180077b81  mov     r9d, 0C08h
0x180077b87  mov     ecx, 0C00000BBh
0x180077b8c  jmp     loc_180077A38
0x180077b91  mov     r15d, [rbp+var_28]
0x180077b95  lea     rdx, aPublicblob; "PUBLICBLOB"
0x180077b9c  mov     rcx, rdi; Str1
0x180077b9f  call    wcscmp_0
0x180077ba4  test    eax, eax
0x180077ba6  jnz     short loc_180077BD0
0x180077ba8  mov     rax, [rbp+arg_40]
0x180077baf  mov     [rax], esi
0x180077bb1  mov     eax, [r12]
0x180077bb5  cmp     eax, 50444345h
0x180077bba  jz      short loc_180077BC7
0x180077bbc  cmp     eax, 504B4345h
0x180077bc1  jz      short loc_180077BC7
0x180077bc3  xor     ecx, ecx
0x180077bc5  jmp     short loc_180077BCC
0x180077bc7  mov     ecx, 1
0x180077bcc  xor     eax, eax
0x180077bce  jmp     short loc_180077C10
0x180077bd0  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x180077bd7  mov     rcx, rdi; Str1
0x180077bda  call    wcscmp_0
0x180077bdf  test    eax, eax
0x180077be1  jnz     short loc_180077C19
0x180077be3  mov     rax, [rbp+arg_40]
0x180077bea  mov     dword ptr [rax], 1
0x180077bf0  mov     eax, [r12]
0x180077bf4  cmp     eax, 56444345h
0x180077bf9  jz      short loc_180077C06
0x180077bfb  cmp     eax, 564B4345h
0x180077c00  jz      short loc_180077C06
0x180077c02  xor     ecx, ecx
0x180077c04  jmp     short loc_180077C0B
0x180077c06  mov     ecx, 1
0x180077c0b  mov     eax, 1
0x180077c10  test    ecx, ecx
0x180077c12  jz      short loc_180077C5E
0x180077c14  jmp     loc_180077CD6
0x180077c19  lea     rdx, aEccpublicblob; "ECCPUBLICBLOB"
0x180077c20  mov     rcx, rdi; Str1
0x180077c23  call    wcscmp_0
0x180077c28  test    eax, eax
0x180077c2a  jnz     short loc_180077C39
0x180077c2c  mov     rax, [rbp+arg_40]
0x180077c33  mov     [rax], esi
0x180077c35  xor     eax, eax
0x180077c37  jmp     short loc_180077C5E
0x180077c39  lea     rdx, aEccprivateblob; "ECCPRIVATEBLOB"
0x180077c40  mov     rcx, rdi; Str1
0x180077c43  call    wcscmp_0
0x180077c48  test    eax, eax
0x180077c4a  jnz     short loc_180077C91
0x180077c4c  mov     rax, [rbp+arg_40]
0x180077c53  mov     dword ptr [rax], 1
0x180077c59  mov     eax, 1
0x180077c5e  mov     r9d, [rbp+var_24]
0x180077c62  lea     rcx, [rbp+var_20]
0x180077c66  mov     [rsp+68h+var_30], rcx
0x180077c6b  mov     r8d, ebx
0x180077c6e  mov     ecx, [rbp+arg_30]
0x180077c71  mov     rdx, r12
0x180077c74  mov     dword ptr [rsp+68h+var_38], ecx
0x180077c78  mov     rcx, [rbp+var_18]
0x180077c7c  mov     [rsp+68h+var_40], eax
0x180077c80  mov     eax, [rbp+arg_38]
0x180077c86  mov     dword ptr [rsp+68h+var_48], eax
0x180077c8a  call    ImportEccKeyBlobWithoutParameters
0x180077c8f  jmp     short loc_180077D00
0x180077c91  lea     rdx, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x180077c98  mov     rcx, rdi; Str1
0x180077c9b  call    wcscmp_0
0x180077ca0  test    eax, eax
0x180077ca2  jnz     short loc_180077CB1
0x180077ca4  mov     rax, [rbp+arg_40]
0x180077cab  mov     [rax], esi
0x180077cad  xor     eax, eax
0x180077caf  jmp     short loc_180077CD6
0x180077cb1  lea     rdx, aEccfullprivate; "ECCFULLPRIVATEBLOB"
0x180077cb8  mov     rcx, rdi; Str1
0x180077cbb  call    wcscmp_0
0x180077cc0  test    eax, eax
0x180077cc2  jnz     short loc_180077D27
0x180077cc4  mov     rax, [rbp+arg_40]
0x180077ccb  mov     dword ptr [rax], 1
0x180077cd1  mov     eax, 1
0x180077cd6  mov     r9d, [rbp+arg_38]
0x180077cdd  lea     rcx, [rbp+var_20]
0x180077ce1  mov     [rsp+68h+var_38], rcx
0x180077ce6  mov     r8d, ebx
0x180077ce9  mov     ecx, [rbp+arg_30]
0x180077cec  mov     rdx, r12
0x180077cef  mov     [rsp+68h+var_40], ecx
0x180077cf3  mov     rcx, [rbp+var_18]
0x180077cf7  mov     dword ptr [rsp+68h+var_48], eax
0x180077cfb  call    ImportEccKeyBlobWithParameters
0x180077d00  mov     ebx, eax
0x180077d02  test    eax, eax
0x180077d04  jns     short loc_180077D14
0x180077d06  mov     rsi, [rbp+var_20]
0x180077d0a  mov     ecx, eax
0x180077d0c  mov     r9d, 0C5Bh
0x180077d12  jmp     short loc_180077D60
0x180077d14  mov     rax, [rbp+var_20]
0x180077d18  mov     rcx, [rbp+arg_18]
0x180077d1c  or      dword ptr [rax+20h], 2
0x180077d20  xor     ebx, ebx
0x180077d22  mov     [rcx], rax
0x180077d25  jmp     short loc_180077D86
0x180077d27  mov     r9d, 0C3Eh
0x180077d2d  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180077d34  lea     rdx, aStatus; "Status"
0x180077d3b  mov     ecx, 0C00000BBh
0x180077d40  mov     ebx, 0C00000BBh
0x180077d45  call    DebugTraceError
0x180077d4a  jmp     short loc_180077D86
0x180077d4c  mov     r15d, [rbp+var_28]
0x180077d50  mov     ebx, 0C000000Dh
0x180077d55  mov     ecx, 0C000000Dh
0x180077d5a  mov     r9d, 0BD5h
0x180077d60  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180077d67  lea     rdx, aStatus; "Status"
0x180077d6e  call    DebugTraceError
0x180077d73  test    rsi, rsi
0x180077d76  jz      short loc_180077D86
0x180077d78  mov     edx, [rbp+arg_38]
0x180077d7e  mov     rcx, rsi
0x180077d81  call    MSCryptEccDestroyKeyPair
0x180077d86  test    r14, r14
0x180077d89  jz      short loc_180077DAA
0x180077d8b  mov     ecx, r15d
0x180077d8e  mov     rax, r14
0x180077d91  test    r15d, r15d
0x180077d94  jz      short loc_180077DA2
0x180077d96  mov     byte ptr [rax], 0
0x180077d99  inc     rax
0x180077d9c  sub     rcx, 1
0x180077da0  jnz     short loc_180077D96
0x180077da2  mov     rcx, r14; P
0x180077da5  call    MSCryptFree
0x180077daa  mov     eax, ebx
0x180077dac  add     rsp, 68h
0x180077db0  pop     r15
0x180077db2  pop     r14
0x180077db4  pop     r13
0x180077db6  pop     r12
0x180077db8  pop     rdi
0x180077db9  pop     rsi
0x180077dba  pop     rbx
0x180077dbb  pop     rbp
0x180077dbc  retn
```
