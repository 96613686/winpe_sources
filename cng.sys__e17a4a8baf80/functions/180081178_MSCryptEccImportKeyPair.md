# MSCryptEccImportKeyPair

- ea: `0x180081178`
- end: `0x18008154e`
- name: `MSCryptEccImportKeyPair`
- size: `982`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18007fc80`
- `0x180080090`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x18004a91c`
- `0x18004f89c`
- `0x18007f580`
- `0x18008052c`
- `0x180081178`
- `0x180088308`
- `0x1800a4232`

## string_xrefs

- `0x1800811c8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800812d6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800814bd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800814f0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

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
  int v21; // eax
  unsigned int v22; // r15d
  BOOL v23; // ecx
  int v24; // eax
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // r9
  __int64 v28; // rax
  __int64 v29; // rcx
  int *v30; // rax
  unsigned int v32; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v33; // [rsp+44h] [rbp-24h] BYREF
  __int64 v34; // [rsp+48h] [rbp-20h] BYREF
  __int64 v35[3]; // [rsp+50h] [rbp-18h] BYREF

  v9 = 0;
  v35[0] = 0;
  v33 = 0;
  v13 = 0;
  v34 = 0;
  v32 = 0;
  if ( (a7 & 0xFFFFFFC7) != 0 )
  {
    v14 = -1073741811;
    v15 = 3014;
    v16 = 3221225485LL;
LABEL_3:
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v15);
    return v14;
  }
  v17 = ValidateEccAlgorithm(a1, 0, a8, (unsigned int)&v33, (__int64)v35);
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
    v22 = v32;
    v14 = -1073741811;
    v26 = 3221225485LL;
    v27 = 3029;
LABEL_52:
    DebugTraceError(v26, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v27);
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
    v22 = v32;
LABEL_23:
    if ( !wcscmp_0(a3, L"PUBLICBLOB") )
    {
      *a9 = 0;
      v23 = *v18 == 1346650949 || *v18 == 1347109701;
      v24 = 0;
    }
    else
    {
      if ( wcscmp_0(a3, L"PRIVATEBLOB") )
      {
        if ( !wcscmp_0(a3, L"ECCPUBLICBLOB") )
        {
          *a9 = 0;
          v24 = 0;
        }
        else
        {
          if ( wcscmp_0(a3, L"ECCPRIVATEBLOB") )
          {
            if ( !wcscmp_0(a3, L"ECCFULLPUBLICBLOB") )
            {
              *a9 = 0;
              v24 = 0;
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
              v24 = 1;
            }
            goto LABEL_46;
          }
          *a9 = 1;
          v24 = 1;
        }
LABEL_41:
        v25 = ImportEccKeyBlobWithoutParameters(v35[0], v18, v19, v33, a8, v24, a7, &v34);
LABEL_47:
        v14 = v25;
        if ( v25 >= 0 )
        {
          v28 = v34;
          *(_DWORD *)(v34 + 32) |= 2u;
          v14 = 0;
          *a4 = v28;
          goto LABEL_54;
        }
        v13 = v34;
        v26 = (unsigned int)v25;
        v27 = 3163;
        goto LABEL_52;
      }
      *a9 = 1;
      v23 = *v18 == 1447314245 || *v18 == 1447772997;
      v24 = 1;
    }
    if ( v23 )
    {
LABEL_46:
      v25 = ImportEccKeyBlobWithParameters(v35[0], (_DWORD)v18, v19, a8, v24, a7, (__int64)&v34);
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
  v17 = Pkcs11ConvertToKeyBlob(a1, a2, 0, &v32, a5, a6);
  v14 = v17;
  if ( v17 < 0 )
  {
    v15 = 3051;
    goto LABEL_6;
  }
  v9 = (int *)MSCryptAlloc(v32, v20);
  if ( !v9 )
  {
    v14 = -1073741801;
    v15 = 3058;
    v16 = 3221225495LL;
    goto LABEL_3;
  }
  v21 = Pkcs11ConvertToKeyBlob(a1, a2, v9, &v32, a5, a6);
  v14 = v21;
  if ( v21 >= 0 )
  {
    v22 = v32;
    a3 = L"ECCPRIVATEBLOB";
    v19 = v32;
    v18 = v9;
    goto LABEL_23;
  }
  DebugTraceError((unsigned int)v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 3070);
  v22 = v32;
LABEL_55:
  v29 = v22;
  v30 = v9;
  if ( v22 )
  {
    do
    {
      *(_BYTE *)v30 = 0;
      v30 = (int *)((char *)v30 + 1);
      --v29;
    }
    while ( v29 );
  }
  MSCryptFree(v9);
  return v14;
}

```

## disassembly

```asm
0x180081178  mov     [rsp-40h+arg_18], r9
0x18008117d  push    rbp
0x18008117e  push    rbx
0x18008117f  push    rsi
0x180081180  push    rdi
0x180081181  push    r12
0x180081183  push    r13
0x180081185  push    r14
0x180081187  push    r15
0x180081189  mov     rbp, rsp
0x18008118c  sub     rsp, 68h
0x180081190  xor     r14d, r14d
0x180081193  mov     rdi, r8
0x180081196  test    [rbp+arg_30], 0FFFFFFC7h
0x18008119d  mov     r15, rdx
0x1800811a0  mov     r13, rcx
0x1800811a3  mov     [rbp+var_18], r14
0x1800811a7  mov     [rbp+var_24], r14d
0x1800811ab  mov     esi, r14d
0x1800811ae  mov     [rbp+var_20], r14
0x1800811b2  mov     [rbp+var_28], r14d
0x1800811b6  jz      short loc_1800811E0
0x1800811b8  mov     ebx, 0C000000Dh
0x1800811bd  mov     r9d, 0BC6h
0x1800811c3  mov     ecx, 0C000000Dh
0x1800811c8  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800811cf  lea     rdx, aStatus; "Status"
0x1800811d6  call    DebugTraceError
0x1800811db  jmp     loc_18008153A
0x1800811e0  mov     r8d, [rbp+arg_38]
0x1800811e7  lea     rax, [rbp+var_18]
0x1800811eb  lea     r9, [rbp+var_24]
0x1800811ef  mov     [rsp+68h+var_48], rax
0x1800811f4  xor     edx, edx
0x1800811f6  call    ValidateEccAlgorithm
0x1800811fb  mov     ebx, eax
0x1800811fd  test    eax, eax
0x1800811ff  jns     short loc_18008120B
0x180081201  mov     r9d, 0BCDh
0x180081207  mov     ecx, eax
0x180081209  jmp     short loc_1800811C8
0x18008120b  mov     r12, [rbp+arg_20]
0x18008120f  test    r12, r12
0x180081212  jz      loc_1800814DC
0x180081218  mov     ebx, [rbp+arg_28]
0x18008121b  cmp     ebx, 4
0x18008121e  jb      loc_1800814DC
0x180081224  test    rdi, rdi
0x180081227  jz      loc_180081307
0x18008122d  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x180081234  mov     rcx, rdi; Str1
0x180081237  call    wcscmp_0
0x18008123c  test    eax, eax
0x18008123e  jnz     loc_180081307
0x180081244  test    r15, r15
0x180081247  jnz     short loc_18008125E
0x180081249  mov     ebx, 0C0000008h
0x18008124e  mov     r9d, 0BDFh
0x180081254  mov     ecx, 0C0000008h
0x180081259  jmp     loc_1800811C8
0x18008125e  mov     [rsp+68h+var_40], ebx
0x180081262  lea     r9, [rbp+var_28]
0x180081266  xor     r8d, r8d
0x180081269  mov     [rsp+68h+var_48], r12
0x18008126e  mov     rdx, r15
0x180081271  mov     rcx, r13
0x180081274  call    Pkcs11ConvertToKeyBlob
0x180081279  mov     ebx, eax
0x18008127b  test    eax, eax
0x18008127d  jns     short loc_180081287
0x18008127f  mov     r9d, 0BEBh
0x180081285  jmp     short loc_180081207
0x180081287  mov     ecx, [rbp+var_28]
0x18008128a  call    MSCryptAlloc
0x18008128f  mov     r14, rax
0x180081292  test    rax, rax
0x180081295  jnz     short loc_1800812AC
0x180081297  mov     ebx, 0C0000017h
0x18008129c  mov     r9d, 0BF2h
0x1800812a2  mov     ecx, 0C0000017h
0x1800812a7  jmp     loc_1800811C8
0x1800812ac  mov     eax, [rbp+arg_28]
0x1800812af  lea     r9, [rbp+var_28]
0x1800812b3  mov     [rsp+68h+var_40], eax
0x1800812b7  mov     r8, r14
0x1800812ba  mov     rdx, r15
0x1800812bd  mov     [rsp+68h+var_48], r12
0x1800812c2  mov     rcx, r13
0x1800812c5  call    Pkcs11ConvertToKeyBlob
0x1800812ca  mov     ebx, eax
0x1800812cc  test    eax, eax
0x1800812ce  jns     short loc_1800812F4
0x1800812d0  mov     r9d, 0BFEh
0x1800812d6  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800812dd  lea     rdx, aStatus; "Status"
0x1800812e4  mov     ecx, eax
0x1800812e6  call    DebugTraceError
0x1800812eb  mov     r15d, [rbp+var_28]
0x1800812ef  jmp     loc_18008151B
0x1800812f4  mov     r15d, [rbp+var_28]
0x1800812f8  lea     rdi, aEccprivateblob; "ECCPRIVATEBLOB"
0x1800812ff  mov     ebx, r15d
0x180081302  mov     r12, r14
0x180081305  jmp     short loc_180081325
0x180081307  test    r15, r15
0x18008130a  jz      short loc_180081321
0x18008130c  mov     ebx, 0C00000BBh
0x180081311  mov     r9d, 0C08h
0x180081317  mov     ecx, 0C00000BBh
0x18008131c  jmp     loc_1800811C8
0x180081321  mov     r15d, [rbp+var_28]
0x180081325  lea     rdx, aPublicblob; "PUBLICBLOB"
0x18008132c  mov     rcx, rdi; Str1
0x18008132f  call    wcscmp_0
0x180081334  test    eax, eax
0x180081336  jnz     short loc_180081360
0x180081338  mov     rax, [rbp+arg_40]
0x18008133f  mov     [rax], esi
0x180081341  mov     eax, [r12]
0x180081345  cmp     eax, 50444345h
0x18008134a  jz      short loc_180081357
0x18008134c  cmp     eax, 504B4345h
0x180081351  jz      short loc_180081357
0x180081353  xor     ecx, ecx
0x180081355  jmp     short loc_18008135C
0x180081357  mov     ecx, 1
0x18008135c  xor     eax, eax
0x18008135e  jmp     short loc_1800813A0
0x180081360  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x180081367  mov     rcx, rdi; Str1
0x18008136a  call    wcscmp_0
0x18008136f  test    eax, eax
0x180081371  jnz     short loc_1800813A9
0x180081373  mov     rax, [rbp+arg_40]
0x18008137a  mov     dword ptr [rax], 1
0x180081380  mov     eax, [r12]
0x180081384  cmp     eax, 56444345h
0x180081389  jz      short loc_180081396
0x18008138b  cmp     eax, 564B4345h
0x180081390  jz      short loc_180081396
0x180081392  xor     ecx, ecx
0x180081394  jmp     short loc_18008139B
0x180081396  mov     ecx, 1
0x18008139b  mov     eax, 1
0x1800813a0  test    ecx, ecx
0x1800813a2  jz      short loc_1800813EE
0x1800813a4  jmp     loc_180081466
0x1800813a9  lea     rdx, aEccpublicblob; "ECCPUBLICBLOB"
0x1800813b0  mov     rcx, rdi; Str1
0x1800813b3  call    wcscmp_0
0x1800813b8  test    eax, eax
0x1800813ba  jnz     short loc_1800813C9
0x1800813bc  mov     rax, [rbp+arg_40]
0x1800813c3  mov     [rax], esi
0x1800813c5  xor     eax, eax
0x1800813c7  jmp     short loc_1800813EE
0x1800813c9  lea     rdx, aEccprivateblob; "ECCPRIVATEBLOB"
0x1800813d0  mov     rcx, rdi; Str1
0x1800813d3  call    wcscmp_0
0x1800813d8  test    eax, eax
0x1800813da  jnz     short loc_180081421
0x1800813dc  mov     rax, [rbp+arg_40]
0x1800813e3  mov     dword ptr [rax], 1
0x1800813e9  mov     eax, 1
0x1800813ee  mov     r9d, [rbp+var_24]
0x1800813f2  lea     rcx, [rbp+var_20]
0x1800813f6  mov     [rsp+68h+var_30], rcx
0x1800813fb  mov     r8d, ebx
0x1800813fe  mov     ecx, [rbp+arg_30]
0x180081401  mov     rdx, r12
0x180081404  mov     dword ptr [rsp+68h+var_38], ecx
0x180081408  mov     rcx, [rbp+var_18]
0x18008140c  mov     [rsp+68h+var_40], eax
0x180081410  mov     eax, [rbp+arg_38]
0x180081416  mov     dword ptr [rsp+68h+var_48], eax
0x18008141a  call    ImportEccKeyBlobWithoutParameters
0x18008141f  jmp     short loc_180081490
0x180081421  lea     rdx, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x180081428  mov     rcx, rdi; Str1
0x18008142b  call    wcscmp_0
0x180081430  test    eax, eax
0x180081432  jnz     short loc_180081441
0x180081434  mov     rax, [rbp+arg_40]
0x18008143b  mov     [rax], esi
0x18008143d  xor     eax, eax
0x18008143f  jmp     short loc_180081466
0x180081441  lea     rdx, aEccfullprivate; "ECCFULLPRIVATEBLOB"
0x180081448  mov     rcx, rdi; Str1
0x18008144b  call    wcscmp_0
0x180081450  test    eax, eax
0x180081452  jnz     short loc_1800814B7
0x180081454  mov     rax, [rbp+arg_40]
0x18008145b  mov     dword ptr [rax], 1
0x180081461  mov     eax, 1
0x180081466  mov     r9d, [rbp+arg_38]
0x18008146d  lea     rcx, [rbp+var_20]
0x180081471  mov     [rsp+68h+var_38], rcx
0x180081476  mov     r8d, ebx
0x180081479  mov     ecx, [rbp+arg_30]
0x18008147c  mov     rdx, r12
0x18008147f  mov     [rsp+68h+var_40], ecx
0x180081483  mov     rcx, [rbp+var_18]
0x180081487  mov     dword ptr [rsp+68h+var_48], eax
0x18008148b  call    ImportEccKeyBlobWithParameters
0x180081490  mov     ebx, eax
0x180081492  test    eax, eax
0x180081494  jns     short loc_1800814A4
0x180081496  mov     rsi, [rbp+var_20]
0x18008149a  mov     ecx, eax
0x18008149c  mov     r9d, 0C5Bh
0x1800814a2  jmp     short loc_1800814F0
0x1800814a4  mov     rax, [rbp+var_20]
0x1800814a8  mov     rcx, [rbp+arg_18]
0x1800814ac  or      dword ptr [rax+20h], 2
0x1800814b0  xor     ebx, ebx
0x1800814b2  mov     [rcx], rax
0x1800814b5  jmp     short loc_180081516
0x1800814b7  mov     r9d, 0C3Eh
0x1800814bd  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800814c4  lea     rdx, aStatus; "Status"
0x1800814cb  mov     ecx, 0C00000BBh
0x1800814d0  mov     ebx, 0C00000BBh
0x1800814d5  call    DebugTraceError
0x1800814da  jmp     short loc_180081516
0x1800814dc  mov     r15d, [rbp+var_28]
0x1800814e0  mov     ebx, 0C000000Dh
0x1800814e5  mov     ecx, 0C000000Dh
0x1800814ea  mov     r9d, 0BD5h
0x1800814f0  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800814f7  lea     rdx, aStatus; "Status"
0x1800814fe  call    DebugTraceError
0x180081503  test    rsi, rsi
0x180081506  jz      short loc_180081516
0x180081508  mov     edx, [rbp+arg_38]
0x18008150e  mov     rcx, rsi
0x180081511  call    MSCryptEccDestroyKeyPair
0x180081516  test    r14, r14
0x180081519  jz      short loc_18008153A
0x18008151b  mov     ecx, r15d
0x18008151e  mov     rax, r14
0x180081521  test    r15d, r15d
0x180081524  jz      short loc_180081532
0x180081526  mov     byte ptr [rax], 0
0x180081529  inc     rax
0x18008152c  sub     rcx, 1
0x180081530  jnz     short loc_180081526
0x180081532  mov     rcx, r14; P
0x180081535  call    MSCryptFree
0x18008153a  mov     eax, ebx
0x18008153c  add     rsp, 68h
0x180081540  pop     r15
0x180081542  pop     r14
0x180081544  pop     r13
0x180081546  pop     r12
0x180081548  pop     rdi
0x180081549  pop     rsi
0x18008154a  pop     rbx
0x18008154b  pop     rbp
0x18008154c  retn
```
