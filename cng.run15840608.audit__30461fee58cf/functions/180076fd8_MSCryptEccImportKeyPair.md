# MSCryptEccImportKeyPair

- ea: `0x180076fd8`
- end: `0x1800773ae`
- name: `MSCryptEccImportKeyPair`
- size: `982`
- prototype: `__int64 __fastcall(__int64, __int64, const wchar_t *, _QWORD *, _DWORD *, unsigned int, int, unsigned int, _DWORD *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180075ae0`
- `0x180075ef0`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x18004093c`
- `0x1800457ac`
- `0x1800753e0`
- `0x18007638c`
- `0x180076fd8`
- `0x18007e108`
- `0x18009d746`

## string_xrefs

- `0x180077028`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180077136`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18007731d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180077350`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccImportKeyPair(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        _QWORD *a4,
        _DWORD *a5,
        unsigned int a6,
        int a7,
        unsigned int a8,
        _DWORD *a9)
{
  _DWORD *v9; // r14
  __int64 v13; // rsi
  unsigned int v14; // ebx
  __int64 v15; // r9
  __int64 v16; // rcx
  int v17; // eax
  _DWORD *v18; // r12
  unsigned int v19; // ebx
  int v20; // eax
  unsigned int v21; // r15d
  BOOL v22; // ecx
  int v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // r9
  __int64 v27; // rax
  __int64 v28; // rcx
  _BYTE *v29; // rax
  unsigned int v31; // [rsp+40h] [rbp-28h] BYREF
  int v32; // [rsp+44h] [rbp-24h] BYREF
  __int64 v33; // [rsp+48h] [rbp-20h] BYREF
  __int64 v34[3]; // [rsp+50h] [rbp-18h] BYREF

  v9 = 0;
  v34[0] = 0;
  v32 = 0;
  v13 = 0;
  v33 = 0;
  v31 = 0;
  if ( (a7 & 0xFFFFFFC7) != 0 )
  {
    v14 = -1073741811;
    v15 = 3014;
    v16 = 3221225485LL;
LABEL_3:
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v15);
    return v14;
  }
  v17 = ValidateEccAlgorithm(a1, 0, a8, (unsigned int)&v32, (__int64)v34);
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
    v21 = v31;
    v14 = -1073741811;
    v25 = 3221225485LL;
    v26 = 3029;
LABEL_52:
    DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v26);
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
    v21 = v31;
LABEL_23:
    if ( !wcscmp_0(a3, L"PUBLICBLOB") )
    {
      *a9 = 0;
      v22 = *v18 == 1346650949 || *v18 == 1347109701;
      v23 = 0;
    }
    else
    {
      if ( wcscmp_0(a3, L"PRIVATEBLOB") )
      {
        if ( !wcscmp_0(a3, L"ECCPUBLICBLOB") )
        {
          *a9 = 0;
          v23 = 0;
        }
        else
        {
          if ( wcscmp_0(a3, L"ECCPRIVATEBLOB") )
          {
            if ( !wcscmp_0(a3, L"ECCFULLPUBLICBLOB") )
            {
              *a9 = 0;
              v23 = 0;
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
              v23 = 1;
            }
            goto LABEL_46;
          }
          *a9 = 1;
          v23 = 1;
        }
LABEL_41:
        v24 = ImportEccKeyBlobWithoutParameters(v34[0], (_DWORD)v18, v19, v32, a8, v23, a7, (__int64)&v33);
LABEL_47:
        v14 = v24;
        if ( v24 >= 0 )
        {
          v27 = v33;
          *(_DWORD *)(v33 + 32) |= 2u;
          v14 = 0;
          *a4 = v27;
          goto LABEL_54;
        }
        v13 = v33;
        v25 = (unsigned int)v24;
        v26 = 3163;
        goto LABEL_52;
      }
      *a9 = 1;
      v22 = *v18 == 1447314245 || *v18 == 1447772997;
      v23 = 1;
    }
    if ( v22 )
    {
LABEL_46:
      v24 = ImportEccKeyBlobWithParameters(v34[0], (_DWORD)v18, v19, a8, v23, a7, (__int64)&v33);
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
  v17 = Pkcs11ConvertToKeyBlob(a1, a2, 0, &v31, a5, a6);
  v14 = v17;
  if ( v17 < 0 )
  {
    v15 = 3051;
    goto LABEL_6;
  }
  v9 = (_DWORD *)MSCryptAlloc(v31);
  if ( !v9 )
  {
    v14 = -1073741801;
    v15 = 3058;
    v16 = 3221225495LL;
    goto LABEL_3;
  }
  v20 = Pkcs11ConvertToKeyBlob(a1, a2, v9, &v31, a5, a6);
  v14 = v20;
  if ( v20 >= 0 )
  {
    v21 = v31;
    a3 = L"ECCPRIVATEBLOB";
    v19 = v31;
    v18 = v9;
    goto LABEL_23;
  }
  DebugTraceError((unsigned int)v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 3070);
  v21 = v31;
LABEL_55:
  v28 = v21;
  v29 = v9;
  if ( v21 )
  {
    do
    {
      *v29++ = 0;
      --v28;
    }
    while ( v28 );
  }
  MSCryptFree(v9);
  return v14;
}

```

## disassembly

```asm
0x180076fd8  mov     [rsp-40h+arg_18], r9
0x180076fdd  push    rbp
0x180076fde  push    rbx
0x180076fdf  push    rsi
0x180076fe0  push    rdi
0x180076fe1  push    r12
0x180076fe3  push    r13
0x180076fe5  push    r14
0x180076fe7  push    r15
0x180076fe9  mov     rbp, rsp
0x180076fec  sub     rsp, 68h
0x180076ff0  xor     r14d, r14d
0x180076ff3  mov     rdi, r8
0x180076ff6  test    [rbp+arg_30], 0FFFFFFC7h
0x180076ffd  mov     r15, rdx
0x180077000  mov     r13, rcx
0x180077003  mov     [rbp+var_18], r14
0x180077007  mov     [rbp+var_24], r14d
0x18007700b  mov     esi, r14d
0x18007700e  mov     [rbp+var_20], r14
0x180077012  mov     [rbp+var_28], r14d
0x180077016  jz      short loc_180077040
0x180077018  mov     ebx, 0C000000Dh
0x18007701d  mov     r9d, 0BC6h
0x180077023  mov     ecx, 0C000000Dh
0x180077028  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007702f  lea     rdx, aStatus; "Status"
0x180077036  call    DebugTraceError
0x18007703b  jmp     loc_18007739A
0x180077040  mov     r8d, [rbp+arg_38]
0x180077047  lea     rax, [rbp+var_18]
0x18007704b  lea     r9, [rbp+var_24]
0x18007704f  mov     [rsp+68h+var_48], rax
0x180077054  xor     edx, edx
0x180077056  call    ValidateEccAlgorithm
0x18007705b  mov     ebx, eax
0x18007705d  test    eax, eax
0x18007705f  jns     short loc_18007706B
0x180077061  mov     r9d, 0BCDh
0x180077067  mov     ecx, eax
0x180077069  jmp     short loc_180077028
0x18007706b  mov     r12, [rbp+arg_20]
0x18007706f  test    r12, r12
0x180077072  jz      loc_18007733C
0x180077078  mov     ebx, [rbp+arg_28]
0x18007707b  cmp     ebx, 4
0x18007707e  jb      loc_18007733C
0x180077084  test    rdi, rdi
0x180077087  jz      loc_180077167
0x18007708d  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x180077094  mov     rcx, rdi; Str1
0x180077097  call    wcscmp_0
0x18007709c  test    eax, eax
0x18007709e  jnz     loc_180077167
0x1800770a4  test    r15, r15
0x1800770a7  jnz     short loc_1800770BE
0x1800770a9  mov     ebx, 0C0000008h
0x1800770ae  mov     r9d, 0BDFh
0x1800770b4  mov     ecx, 0C0000008h
0x1800770b9  jmp     loc_180077028
0x1800770be  mov     [rsp+68h+var_40], ebx
0x1800770c2  lea     r9, [rbp+var_28]
0x1800770c6  xor     r8d, r8d
0x1800770c9  mov     [rsp+68h+var_48], r12
0x1800770ce  mov     rdx, r15
0x1800770d1  mov     rcx, r13
0x1800770d4  call    Pkcs11ConvertToKeyBlob
0x1800770d9  mov     ebx, eax
0x1800770db  test    eax, eax
0x1800770dd  jns     short loc_1800770E7
0x1800770df  mov     r9d, 0BEBh
0x1800770e5  jmp     short loc_180077067
0x1800770e7  mov     ecx, [rbp+var_28]
0x1800770ea  call    MSCryptAlloc
0x1800770ef  mov     r14, rax
0x1800770f2  test    rax, rax
0x1800770f5  jnz     short loc_18007710C
0x1800770f7  mov     ebx, 0C0000017h
0x1800770fc  mov     r9d, 0BF2h
0x180077102  mov     ecx, 0C0000017h
0x180077107  jmp     loc_180077028
0x18007710c  mov     eax, [rbp+arg_28]
0x18007710f  lea     r9, [rbp+var_28]
0x180077113  mov     [rsp+68h+var_40], eax
0x180077117  mov     r8, r14
0x18007711a  mov     rdx, r15
0x18007711d  mov     [rsp+68h+var_48], r12
0x180077122  mov     rcx, r13
0x180077125  call    Pkcs11ConvertToKeyBlob
0x18007712a  mov     ebx, eax
0x18007712c  test    eax, eax
0x18007712e  jns     short loc_180077154
0x180077130  mov     r9d, 0BFEh
0x180077136  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007713d  lea     rdx, aStatus; "Status"
0x180077144  mov     ecx, eax
0x180077146  call    DebugTraceError
0x18007714b  mov     r15d, [rbp+var_28]
0x18007714f  jmp     loc_18007737B
0x180077154  mov     r15d, [rbp+var_28]
0x180077158  lea     rdi, aEccprivateblob; "ECCPRIVATEBLOB"
0x18007715f  mov     ebx, r15d
0x180077162  mov     r12, r14
0x180077165  jmp     short loc_180077185
0x180077167  test    r15, r15
0x18007716a  jz      short loc_180077181
0x18007716c  mov     ebx, 0C00000BBh
0x180077171  mov     r9d, 0C08h
0x180077177  mov     ecx, 0C00000BBh
0x18007717c  jmp     loc_180077028
0x180077181  mov     r15d, [rbp+var_28]
0x180077185  lea     rdx, aPublicblob; "PUBLICBLOB"
0x18007718c  mov     rcx, rdi; Str1
0x18007718f  call    wcscmp_0
0x180077194  test    eax, eax
0x180077196  jnz     short loc_1800771C0
0x180077198  mov     rax, [rbp+arg_40]
0x18007719f  mov     [rax], esi
0x1800771a1  mov     eax, [r12]
0x1800771a5  cmp     eax, 50444345h
0x1800771aa  jz      short loc_1800771B7
0x1800771ac  cmp     eax, 504B4345h
0x1800771b1  jz      short loc_1800771B7
0x1800771b3  xor     ecx, ecx
0x1800771b5  jmp     short loc_1800771BC
0x1800771b7  mov     ecx, 1
0x1800771bc  xor     eax, eax
0x1800771be  jmp     short loc_180077200
0x1800771c0  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x1800771c7  mov     rcx, rdi; Str1
0x1800771ca  call    wcscmp_0
0x1800771cf  test    eax, eax
0x1800771d1  jnz     short loc_180077209
0x1800771d3  mov     rax, [rbp+arg_40]
0x1800771da  mov     dword ptr [rax], 1
0x1800771e0  mov     eax, [r12]
0x1800771e4  cmp     eax, 56444345h
0x1800771e9  jz      short loc_1800771F6
0x1800771eb  cmp     eax, 564B4345h
0x1800771f0  jz      short loc_1800771F6
0x1800771f2  xor     ecx, ecx
0x1800771f4  jmp     short loc_1800771FB
0x1800771f6  mov     ecx, 1
0x1800771fb  mov     eax, 1
0x180077200  test    ecx, ecx
0x180077202  jz      short loc_18007724E
0x180077204  jmp     loc_1800772C6
0x180077209  lea     rdx, aEccpublicblob; "ECCPUBLICBLOB"
0x180077210  mov     rcx, rdi; Str1
0x180077213  call    wcscmp_0
0x180077218  test    eax, eax
0x18007721a  jnz     short loc_180077229
0x18007721c  mov     rax, [rbp+arg_40]
0x180077223  mov     [rax], esi
0x180077225  xor     eax, eax
0x180077227  jmp     short loc_18007724E
0x180077229  lea     rdx, aEccprivateblob; "ECCPRIVATEBLOB"
0x180077230  mov     rcx, rdi; Str1
0x180077233  call    wcscmp_0
0x180077238  test    eax, eax
0x18007723a  jnz     short loc_180077281
0x18007723c  mov     rax, [rbp+arg_40]
0x180077243  mov     dword ptr [rax], 1
0x180077249  mov     eax, 1
0x18007724e  mov     r9d, [rbp+var_24]
0x180077252  lea     rcx, [rbp+var_20]
0x180077256  mov     [rsp+68h+var_30], rcx
0x18007725b  mov     r8d, ebx
0x18007725e  mov     ecx, [rbp+arg_30]
0x180077261  mov     rdx, r12
0x180077264  mov     dword ptr [rsp+68h+var_38], ecx
0x180077268  mov     rcx, [rbp+var_18]
0x18007726c  mov     [rsp+68h+var_40], eax
0x180077270  mov     eax, [rbp+arg_38]
0x180077276  mov     dword ptr [rsp+68h+var_48], eax
0x18007727a  call    ImportEccKeyBlobWithoutParameters
0x18007727f  jmp     short loc_1800772F0
0x180077281  lea     rdx, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x180077288  mov     rcx, rdi; Str1
0x18007728b  call    wcscmp_0
0x180077290  test    eax, eax
0x180077292  jnz     short loc_1800772A1
0x180077294  mov     rax, [rbp+arg_40]
0x18007729b  mov     [rax], esi
0x18007729d  xor     eax, eax
0x18007729f  jmp     short loc_1800772C6
0x1800772a1  lea     rdx, aEccfullprivate; "ECCFULLPRIVATEBLOB"
0x1800772a8  mov     rcx, rdi; Str1
0x1800772ab  call    wcscmp_0
0x1800772b0  test    eax, eax
0x1800772b2  jnz     short loc_180077317
0x1800772b4  mov     rax, [rbp+arg_40]
0x1800772bb  mov     dword ptr [rax], 1
0x1800772c1  mov     eax, 1
0x1800772c6  mov     r9d, [rbp+arg_38]
0x1800772cd  lea     rcx, [rbp+var_20]
0x1800772d1  mov     [rsp+68h+var_38], rcx
0x1800772d6  mov     r8d, ebx
0x1800772d9  mov     ecx, [rbp+arg_30]
0x1800772dc  mov     rdx, r12
0x1800772df  mov     [rsp+68h+var_40], ecx
0x1800772e3  mov     rcx, [rbp+var_18]
0x1800772e7  mov     dword ptr [rsp+68h+var_48], eax
0x1800772eb  call    ImportEccKeyBlobWithParameters
0x1800772f0  mov     ebx, eax
0x1800772f2  test    eax, eax
0x1800772f4  jns     short loc_180077304
0x1800772f6  mov     rsi, [rbp+var_20]
0x1800772fa  mov     ecx, eax
0x1800772fc  mov     r9d, 0C5Bh
0x180077302  jmp     short loc_180077350
0x180077304  mov     rax, [rbp+var_20]
0x180077308  mov     rcx, [rbp+arg_18]
0x18007730c  or      dword ptr [rax+20h], 2
0x180077310  xor     ebx, ebx
0x180077312  mov     [rcx], rax
0x180077315  jmp     short loc_180077376
0x180077317  mov     r9d, 0C3Eh
0x18007731d  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180077324  lea     rdx, aStatus; "Status"
0x18007732b  mov     ecx, 0C00000BBh
0x180077330  mov     ebx, 0C00000BBh
0x180077335  call    DebugTraceError
0x18007733a  jmp     short loc_180077376
0x18007733c  mov     r15d, [rbp+var_28]
0x180077340  mov     ebx, 0C000000Dh
0x180077345  mov     ecx, 0C000000Dh
0x18007734a  mov     r9d, 0BD5h
0x180077350  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180077357  lea     rdx, aStatus; "Status"
0x18007735e  call    DebugTraceError
0x180077363  test    rsi, rsi
0x180077366  jz      short loc_180077376
0x180077368  mov     edx, [rbp+arg_38]
0x18007736e  mov     rcx, rsi
0x180077371  call    MSCryptEccDestroyKeyPair
0x180077376  test    r14, r14
0x180077379  jz      short loc_18007739A
0x18007737b  mov     ecx, r15d
0x18007737e  mov     rax, r14
0x180077381  test    r15d, r15d
0x180077384  jz      short loc_180077392
0x180077386  mov     byte ptr [rax], 0
0x180077389  inc     rax
0x18007738c  sub     rcx, 1
0x180077390  jnz     short loc_180077386
0x180077392  mov     rcx, r14; P
0x180077395  call    MSCryptFree
0x18007739a  mov     eax, ebx
0x18007739c  add     rsp, 68h
0x1800773a0  pop     r15
0x1800773a2  pop     r14
0x1800773a4  pop     r13
0x1800773a6  pop     r12
0x1800773a8  pop     rdi
0x1800773a9  pop     rsi
0x1800773aa  pop     rbx
0x1800773ab  pop     rbp
0x1800773ac  retn
```
