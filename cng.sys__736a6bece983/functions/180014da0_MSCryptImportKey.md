# MSCryptImportKey

- ea: `0x180014da0`
- end: `0x18001517e`
- name: `MSCryptImportKey`
- size: `990`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, wchar_t *Str1@<r8>, int, int, void *, size_t, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180013c40`

## callees

- `0x180003f70`
- `0x180006410`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x180014070`
- `0x180014da0`
- `0x180015184`
- `0x1800169d0`
- `0x180016e80`
- `0x18007f0f8`
- `0x18009f616`

## string_xrefs

- `0x180014f28`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180014f9b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180014ff1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18001503e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18001509a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800a16b2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800a1736`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptImportKey(
        __int64 a1,
        __int64 a2,
        wchar_t *Str1,
        _QWORD *a4,
        __int64 a5,
        unsigned int a6,
        _DWORD *a7,
        size_t a8,
        int a9)
{
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // r15
  unsigned __int64 v15; // rsi
  _DWORD *v16; // rdi
  unsigned int v17; // r14d
  int v18; // edx
  int SymmetricKey; // eax
  unsigned int v20; // ebx
  _QWORD *v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // r9
  __int64 v26; // rcx
  _BYTE *v27; // rax
  __int64 v28; // r9
  __int64 v29; // rcx
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  _DWORD *v35; // rax
  int v36; // eax
  char Src; // [rsp+20h] [rbp-38h]
  size_t Size; // [rsp+28h] [rbp-30h]
  size_t v39; // [rsp+30h] [rbp-28h]
  char v40; // [rsp+30h] [rbp-28h]
  unsigned int v41; // [rsp+40h] [rbp-18h] BYREF
  int v42[2]; // [rsp+48h] [rbp-10h] BYREF

  *(_QWORD *)v42 = 0;
  v41 = 0;
  if ( !a9 )
  {
    v14 = validateMSCryptSymmAlgorithm();
    if ( v14 )
    {
      v15 = (unsigned int)v12;
      if ( a5 == v12 || (v16 = a7) == 0 )
      {
        v20 = -1073741811;
        v24 = 3221225485LL;
        v25 = 1435;
        goto LABEL_29;
      }
      if ( Str1 )
      {
        if ( v13 )
        {
          if ( wcscmp_0(Str1, L"PKCS11RsaAesWrapBlob") )
          {
            v17 = a8;
            goto LABEL_9;
          }
          if ( a2 )
          {
            if ( *(_DWORD *)(v14 + 8) == 65538 )
            {
              v31 = Pkcs11ConvertToKeyBlob(a1, a2, 0, &v41, a7, a8);
              v20 = v31;
              if ( v31 >= 0 )
              {
                v35 = (_DWORD *)MSCryptAlloc(v41, v32, v33, v34);
                v15 = (unsigned __int64)v35;
                if ( v35 )
                {
                  v36 = Pkcs11ConvertToKeyBlob(a1, a2, v35, &v41, a7, a8);
                  v20 = v36;
                  if ( v36 < 0 )
                  {
                    DebugTraceError(
                      (unsigned int)v36,
                      "Status",
                      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                      1497);
LABEL_40:
                    v26 = v41;
                    v27 = (_BYTE *)v15;
                    if ( v41 )
                    {
                      do
                      {
                        *v27++ = 0;
                        --v26;
                      }
                      while ( v26 );
                    }
                    MSCryptFree((PVOID)v15);
                    return v20;
                  }
                  v17 = v41;
                  Str1 = (wchar_t *)L"KeyDataBlob";
                  v16 = (_DWORD *)v15;
LABEL_9:
                  if ( !wcscmp_0(Str1, L"OpaqueKeyBlob") )
                  {
                    if ( a6 < *(_DWORD *)(v14 + 28) )
                    {
                      v20 = -1073741789;
                      goto LABEL_17;
                    }
                    v30 = MSCryptImportKeyOpaque(v14, v16, v17);
                    v20 = v30;
                    if ( v30 >= 0 )
                      goto LABEL_16;
                    v24 = (unsigned int)v30;
                    v25 = 1520;
                    goto LABEL_29;
                  }
                  if ( !wcscmp_0(Str1, L"KeyDataBlob") )
                  {
                    if ( v17 >= 0xC )
                    {
                      if ( *v16 != 1296188491 || v16[1] != 1 || (unsigned __int64)v17 - 12 < (unsigned int)v16[2] )
                      {
                        v20 = -1073741811;
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                        {
                          WPP_SF_sDsd(
                            *((_QWORD *)WPP_GLOBAL_Control + 3),
                            v18,
                            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                            (unsigned int)"Status",
                            13,
                            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                            5);
                        }
LABEL_17:
                        if ( !v15 )
                          return v20;
                        goto LABEL_40;
                      }
                      LODWORD(Size) = v16[2];
                      SymmetricKey = MSCryptGenerateSymmetricKey(a1, (int)v42, a5, a6, v16 + 3, Size, 128);
                      v20 = SymmetricKey;
                      if ( SymmetricKey >= 0 )
                      {
LABEL_16:
                        *a4 = *(_QWORD *)v42;
                        goto LABEL_17;
                      }
                      v24 = (unsigned int)SymmetricKey;
                      v25 = 1554;
LABEL_29:
                      DebugTraceError(
                        v24,
                        "Status",
                        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                        v25);
                      if ( *(_QWORD *)v42 )
                        MSCryptDestroyKey(*(_QWORD *)v42);
                      goto LABEL_17;
                    }
                    v20 = -1073741789;
                    v22 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
                    {
                      goto LABEL_17;
                    }
                    v40 = -5;
                    Src = 35;
                  }
                  else
                  {
                    if ( !wcscmp_0(Str1, L"Rfc3565KeyWrapBlob") )
                    {
                      LODWORD(v39) = v17;
                      v23 = MSCryptAesKeyUnwrap(a1, a2, (int)v42, a5, a6, v16, v39);
                      v20 = v23;
                      if ( v23 >= 0 )
                        goto LABEL_16;
                      v24 = (unsigned int)v23;
                      v25 = 1571;
                      goto LABEL_29;
                    }
                    v20 = -1073741637;
                    v22 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
                    {
                      goto LABEL_17;
                    }
                    v40 = 42;
                    Src = -69;
                  }
                  WPP_SF_sDsd(
                    v22[3],
                    v18,
                    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                    (unsigned int)"Status",
                    Src,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                    v40);
                  goto LABEL_17;
                }
                v20 = -1073741801;
                v28 = 1485;
                v29 = 3221225495LL;
              }
              else
              {
                v28 = 1478;
                v29 = (unsigned int)v31;
              }
            }
            else
            {
              v20 = -1073741637;
              v28 = 1466;
              v29 = 3221225659LL;
            }
LABEL_57:
            DebugTraceError(v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v28);
            return v20;
          }
          v28 = 1459;
LABEL_55:
          v20 = -1073741816;
          v29 = 3221225480LL;
          goto LABEL_57;
        }
        v28 = 1449;
      }
      else
      {
        v28 = 1442;
      }
      v20 = -1073741811;
      v29 = 3221225485LL;
      goto LABEL_57;
    }
    v28 = 1428;
    goto LABEL_55;
  }
  v20 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      0,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
      139);
  return v20;
}

```

## disassembly

```asm
0x180014da0  mov     [rsp-40h+arg_18], r9
0x180014da5  push    rbp
0x180014da6  push    rbx
0x180014da7  push    rsi
0x180014da8  push    rdi
0x180014da9  push    r12
0x180014dab  push    r13
0x180014dad  push    r14
0x180014daf  push    r15
0x180014db1  mov     rbp, rsp
0x180014db4  sub     rsp, 58h
0x180014db8  mov     r12, rdx
0x180014dbb  mov     rbx, r8
0x180014dbe  xor     edx, edx
0x180014dc0  mov     r13, rcx
0x180014dc3  mov     qword ptr [rbp+var_10], rdx
0x180014dc7  mov     [rbp+var_18], edx
0x180014dca  cmp     [rbp+arg_40], edx
0x180014dd0  jnz     loc_180015012
0x180014dd6  call    validateMSCryptSymmAlgorithm
0x180014ddb  mov     r15, rax
0x180014dde  test    rax, rax
0x180014de1  jz      loc_1800150D7
0x180014de7  mov     esi, edx
0x180014de9  cmp     [rbp+arg_20], rdx
0x180014ded  jz      loc_180015169
0x180014df3  mov     rdi, [rbp+arg_30]
0x180014df7  test    rdi, rdi
0x180014dfa  jz      loc_180015169
0x180014e00  test    rbx, rbx
0x180014e03  jz      loc_1800150E2
0x180014e09  test    r9, r9
0x180014e0c  jz      loc_1800150EA
0x180014e12  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x180014e19  mov     rcx, rbx; Str1
0x180014e1c  call    wcscmp_0
0x180014e21  test    eax, eax
0x180014e23  jz      loc_1800150FF
0x180014e29  mov     r14d, dword ptr [rbp+arg_38]
0x180014e30  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x180014e37  mov     rcx, rbx; Str1
0x180014e3a  call    wcscmp_0
0x180014e3f  test    eax, eax
0x180014e41  jz      loc_180014EEC
0x180014e47  lea     rdx, aKeydatablob; "KeyDataBlob"
0x180014e4e  mov     rcx, rbx; Str1
0x180014e51  call    wcscmp_0
0x180014e56  test    eax, eax
0x180014e58  jnz     loc_180014F4E
0x180014e5e  cmp     r14d, 0Ch
0x180014e62  jb      loc_180014F01
0x180014e68  cmp     dword ptr [rdi], 4D42444Bh
0x180014e6e  jnz     loc_180014FC5
0x180014e74  cmp     dword ptr [rdi+4], 1
0x180014e78  jnz     loc_180014FC5
0x180014e7e  mov     ecx, [rdi+8]
0x180014e81  mov     eax, r14d
0x180014e84  sub     rax, 0Ch
0x180014e88  cmp     rax, rcx
0x180014e8b  jb      loc_180014FC5
0x180014e91  mov     r9d, [rbp+arg_28]; int
0x180014e95  lea     rax, [rdi+0Ch]
0x180014e99  mov     r8, [rbp+arg_20]; int
0x180014e9d  lea     rdx, [rbp+var_10]; int
0x180014ea1  mov     dword ptr [rsp+58h+var_28], 80h; int
0x180014ea9  mov     dword ptr [rsp+58h+Size], ecx; Size
0x180014ead  mov     rcx, r13; int
0x180014eb0  mov     [rsp+58h+Src], rax; Src
0x180014eb5  call    MSCryptGenerateSymmetricKey
0x180014eba  mov     ebx, eax
0x180014ebc  test    eax, eax
0x180014ebe  js      loc_18001515C
0x180014ec4  mov     rcx, [rbp+arg_18]
0x180014ec8  mov     rax, qword ptr [rbp+var_10]
0x180014ecc  mov     [rcx], rax
0x180014ecf  test    rsi, rsi
0x180014ed2  jnz     loc_1800150B3
0x180014ed8  mov     eax, ebx
0x180014eda  add     rsp, 58h
0x180014ede  pop     r15
0x180014ee0  pop     r14
0x180014ee2  pop     r13
0x180014ee4  pop     r12
0x180014ee6  pop     rdi
0x180014ee7  pop     rsi
0x180014ee8  pop     rbx
0x180014ee9  pop     rbp
0x180014eea  retn
0x180014eec  mov     r9d, [rbp+arg_28]
0x180014ef0  cmp     r9d, [r15+1Ch]
0x180014ef4  jnb     loc_18001512B
0x180014efa  mov     ebx, 0C0000023h
0x180014eff  jmp     short loc_180014ECF
0x180014f01  mov     ebx, 0C0000023h
0x180014f06  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f0d  lea     rax, WPP_GLOBAL_Control
0x180014f14  cmp     rcx, rax
0x180014f17  jz      short loc_180014ECF
0x180014f19  mov     eax, [rcx+2Ch]
0x180014f1c  test    al, 1
0x180014f1e  jz      short loc_180014ECF
0x180014f20  mov     dword ptr [rsp+58h+var_28], 5FBh
0x180014f28  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014f2f  mov     [rsp+58h+Size], r8
0x180014f34  mov     dword ptr [rsp+58h+Src], 0C0000023h
0x180014f3c  mov     rcx, [rcx+18h]
0x180014f40  lea     r9, aStatus; "Status"
0x180014f47  call    WPP_SF_sDsd
0x180014f4c  jmp     short loc_180014ECF
0x180014f4e  lea     rdx, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x180014f55  mov     rcx, rbx; Str1
0x180014f58  call    wcscmp_0
0x180014f5d  test    eax, eax
0x180014f5f  jnz     loc_18001506B
0x180014f65  mov     eax, [rbp+arg_28]
0x180014f68  lea     r8, [rbp+var_10]; int
0x180014f6c  mov     r9, [rbp+arg_20]; int
0x180014f70  mov     rdx, r12; int
0x180014f73  mov     dword ptr [rsp+58h+var_28], r14d; Size
0x180014f78  mov     rcx, r13; int
0x180014f7b  mov     [rsp+58h+Size], rdi; Src
0x180014f80  mov     dword ptr [rsp+58h+Src], eax; int
0x180014f84  call    MSCryptAesKeyUnwrap
0x180014f89  mov     ebx, eax
0x180014f8b  test    eax, eax
0x180014f8d  jns     loc_180014EC4
0x180014f93  mov     ecx, eax
0x180014f95  mov     r9d, 623h
0x180014f9b  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014fa2  lea     rdx, aStatus; "Status"
0x180014fa9  call    DebugTraceError
0x180014fae  mov     rcx, qword ptr [rbp+var_10]
0x180014fb2  test    rcx, rcx
0x180014fb5  jz      loc_180014ECF
0x180014fbb  call    MSCryptDestroyKey
0x180014fc0  jmp     loc_180014ECF
0x180014fc5  mov     ebx, 0C000000Dh
0x180014fca  mov     r10, cs:WPP_GLOBAL_Control
0x180014fd1  lea     rax, WPP_GLOBAL_Control
0x180014fd8  cmp     r10, rax
0x180014fdb  jz      loc_180014ECF
0x180014fe1  mov     eax, [r10+2Ch]
0x180014fe5  test    al, 1
0x180014fe7  jz      loc_180014ECF
0x180014fed  mov     rcx, [r10+18h]
0x180014ff1  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014ff8  mov     dword ptr [rsp+58h+var_28], 605h
0x180015000  mov     [rsp+58h+Size], r8
0x180015005  mov     dword ptr [rsp+58h+Src], 0C000000Dh
0x18001500d  jmp     loc_180014F40
0x180015012  mov     ebx, 0C000000Dh
0x180015017  mov     r10, cs:WPP_GLOBAL_Control
0x18001501e  lea     rax, WPP_GLOBAL_Control
0x180015025  cmp     r10, rax
0x180015028  jz      loc_180014ED8
0x18001502e  mov     eax, [r10+2Ch]
0x180015032  test    al, 1
0x180015034  jz      loc_180014ED8
0x18001503a  mov     rcx, [r10+18h]
0x18001503e  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015045  mov     dword ptr [rsp+58h+var_28], 58Bh
0x18001504d  lea     r9, aStatus; "Status"
0x180015054  mov     [rsp+58h+Size], r8
0x180015059  mov     dword ptr [rsp+58h+Src], 0C000000Dh
0x180015061  call    WPP_SF_sDsd
0x180015066  jmp     loc_180014ED8
0x18001506b  mov     ebx, 0C00000BBh
0x180015070  mov     rcx, cs:WPP_GLOBAL_Control
0x180015077  lea     rax, WPP_GLOBAL_Control
0x18001507e  cmp     rcx, rax
0x180015081  jz      loc_180014ECF
0x180015087  mov     eax, [rcx+2Ch]
0x18001508a  test    al, 1
0x18001508c  jz      loc_180014ECF
0x180015092  mov     dword ptr [rsp+58h+var_28], 62Ah
0x18001509a  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800150a1  mov     [rsp+58h+Size], r8
0x1800150a6  mov     dword ptr [rsp+58h+Src], 0C00000BBh
0x1800150ae  jmp     loc_180014F3C
0x1800150b3  mov     ecx, [rbp+var_18]
0x1800150b6  mov     rax, rsi
0x1800150b9  test    rcx, rcx
0x1800150bc  jz      short loc_1800150CA
0x1800150be  mov     byte ptr [rax], 0
0x1800150c1  inc     rax
0x1800150c4  sub     rcx, 1
0x1800150c8  jnz     short loc_1800150BE
0x1800150ca  mov     rcx, rsi; P
0x1800150cd  call    MSCryptFree
0x1800150d2  jmp     loc_180014ED8
0x1800150d7  mov     r9d, 594h
0x1800150dd  jmp     loc_1800A1696
0x1800150e2  mov     r9d, 5A2h
0x1800150e8  jmp     short loc_1800150F0
0x1800150ea  mov     r9d, 5A9h
0x1800150f0  mov     ebx, 0C000000Dh
0x1800150f5  mov     ecx, 0C000000Dh
0x1800150fa  jmp     loc_1800A16B2
0x1800150ff  test    r12, r12
0x180015102  jz      loc_1800A1690
0x180015108  cmp     dword ptr [r15+8], 10002h
0x180015110  jz      loc_1800A16CB
0x180015116  mov     ebx, 0C00000BBh
0x18001511b  mov     r9d, 5BAh
0x180015121  mov     ecx, 0C00000BBh
0x180015126  jmp     loc_1800A16B2
0x18001512b  mov     r8, [rbp+arg_20]
0x18001512f  lea     rdx, [rbp+var_10]
0x180015133  mov     dword ptr [rsp+58h+Size], r14d; int
0x180015138  mov     rcx, r15; int
0x18001513b  mov     [rsp+58h+Src], rdi; Src
0x180015140  call    MSCryptImportKeyOpaque
0x180015145  mov     ebx, eax
0x180015147  test    eax, eax
0x180015149  jns     loc_180014EC4
0x18001514f  mov     ecx, eax
0x180015151  mov     r9d, 5F0h
0x180015157  jmp     loc_180014F9B
0x18001515c  mov     ecx, eax
0x18001515e  mov     r9d, 612h
0x180015164  jmp     loc_180014F9B
0x180015169  mov     ebx, 0C000000Dh
0x18001516e  mov     ecx, 0C000000Dh
0x180015173  mov     r9d, 59Bh
0x180015179  jmp     loc_180014F9B
0x1800a1690  mov     r9d, 5B3h
0x1800a1696  mov     ebx, 0C0000008h
0x1800a169b  mov     ecx, 0C0000008h
0x1800a16a0  jmp     short loc_1800A16B2
0x1800a16a2  mov     ebx, 0C0000017h
0x1800a16a7  mov     r9d, 5CDh
0x1800a16ad  mov     ecx, 0C0000017h
0x1800a16b2  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a16b9  lea     rdx, aStatus; "Status"
0x1800a16c0  call    DebugTraceError
0x1800a16c5  nop
0x1800a16c6  jmp     loc_180014ED8
0x1800a16cb  mov     r14d, dword ptr [rbp+arg_38]
0x1800a16d2  lea     r9, [rbp+var_18]
0x1800a16d6  mov     dword ptr [rsp+58h+Size], r14d
0x1800a16db  xor     r8d, r8d
0x1800a16de  mov     rdx, r12
0x1800a16e1  mov     [rsp+58h+Src], rdi
0x1800a16e6  mov     rcx, r13
0x1800a16e9  call    Pkcs11ConvertToKeyBlob
0x1800a16ee  mov     ebx, eax
0x1800a16f0  test    eax, eax
0x1800a16f2  jns     short loc_1800A16FE
0x1800a16f4  mov     r9d, 5C6h
0x1800a16fa  mov     ecx, eax
0x1800a16fc  jmp     short loc_1800A16B2
0x1800a16fe  mov     ecx, [rbp+var_18]
0x1800a1701  call    MSCryptAlloc
0x1800a1706  mov     rsi, rax
0x1800a1709  test    rax, rax
0x1800a170c  jz      short loc_1800A16A2
0x1800a170e  mov     dword ptr [rsp+58h+Size], r14d
0x1800a1713  lea     r9, [rbp+var_18]
0x1800a1717  mov     r8, rax
0x1800a171a  mov     [rsp+58h+Src], rdi
0x1800a171f  mov     rdx, r12
0x1800a1722  mov     rcx, r13
0x1800a1725  call    Pkcs11ConvertToKeyBlob
0x1800a172a  mov     ebx, eax
0x1800a172c  test    eax, eax
0x1800a172e  jns     short loc_1800A1751
0x1800a1730  mov     r9d, 5D9h
0x1800a1736  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a173d  lea     rdx, aStatus; "Status"
0x1800a1744  mov     ecx, eax
0x1800a1746  call    DebugTraceError
0x1800a174b  nop
0x1800a174c  jmp     loc_1800150B3
0x1800a1751  mov     r14d, [rbp+var_18]
0x1800a1755  lea     rbx, aKeydatablob; "KeyDataBlob"
0x1800a175c  mov     rdi, rsi
0x1800a175f  jmp     loc_180014E30
```
