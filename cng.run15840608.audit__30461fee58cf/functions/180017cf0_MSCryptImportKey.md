# MSCryptImportKey

- ea: `0x180017cf0`
- end: `0x1800180ce`
- name: `MSCryptImportKey`
- size: `990`
- prototype: `__int64 __fastcall(_DWORD *, __int64, wchar_t *Str1, _QWORD *, __int64, unsigned int, char *, size_t, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180016b90`

## callees

- `0x180003f70`
- `0x180006410`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x180016fc0`
- `0x180017cf0`
- `0x1800180d4`
- `0x180019920`
- `0x180019dd0`
- `0x18007e108`
- `0x18009d746`

## string_xrefs

- `0x180017e78`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180017eeb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180017f41`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180017f8e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180017fea`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18009fafc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18009fb80`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptImportKey(
        _DWORD *a1,
        __int64 a2,
        wchar_t *Str1,
        _QWORD *a4,
        __int64 a5,
        unsigned int a6,
        char *a7,
        size_t a8,
        int a9)
{
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // r15
  unsigned __int64 v15; // rsi
  char *v16; // rdi
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
  _DWORD *v32; // rax
  int v33; // eax
  char Src; // [rsp+20h] [rbp-38h]
  size_t Size; // [rsp+28h] [rbp-30h]
  size_t v36; // [rsp+30h] [rbp-28h]
  char v37; // [rsp+30h] [rbp-28h]
  unsigned int v38; // [rsp+40h] [rbp-18h] BYREF
  int v39[2]; // [rsp+48h] [rbp-10h] BYREF

  *(_QWORD *)v39 = 0;
  v38 = 0;
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
              v31 = Pkcs11ConvertToKeyBlob((__int64)a1, a2, 0, &v38, a7, a8);
              v20 = v31;
              if ( v31 >= 0 )
              {
                v32 = (_DWORD *)MSCryptAlloc(v38);
                v15 = (unsigned __int64)v32;
                if ( v32 )
                {
                  v33 = Pkcs11ConvertToKeyBlob((__int64)a1, a2, v32, &v38, a7, a8);
                  v20 = v33;
                  if ( v33 < 0 )
                  {
                    DebugTraceError(
                      (unsigned int)v33,
                      "Status",
                      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                      1497);
LABEL_40:
                    v26 = v38;
                    v27 = (_BYTE *)v15;
                    if ( v38 )
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
                  v17 = v38;
                  Str1 = (wchar_t *)L"KeyDataBlob";
                  v16 = (char *)v15;
LABEL_9:
                  if ( !wcscmp_0(Str1, L"OpaqueKeyBlob") )
                  {
                    if ( a6 < *(_DWORD *)(v14 + 28) )
                    {
                      v20 = -1073741789;
                      goto LABEL_17;
                    }
                    v30 = MSCryptImportKeyOpaque(v14, v39, a5, a6, v16, v17);
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
                      if ( *(_DWORD *)v16 != 1296188491
                        || *((_DWORD *)v16 + 1) != 1
                        || (unsigned __int64)v17 - 12 < *((unsigned int *)v16 + 2) )
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
                      LODWORD(Size) = *((_DWORD *)v16 + 2);
                      SymmetricKey = MSCryptGenerateSymmetricKey(a1, (char **)v39, a5, a6, v16 + 12, Size, 128);
                      v20 = SymmetricKey;
                      if ( SymmetricKey >= 0 )
                      {
LABEL_16:
                        *a4 = *(_QWORD *)v39;
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
                      if ( *(_QWORD *)v39 )
                        MSCryptDestroyKey(*(_QWORD *)v39);
                      goto LABEL_17;
                    }
                    v20 = -1073741789;
                    v22 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
                    {
                      goto LABEL_17;
                    }
                    v37 = -5;
                    Src = 35;
                  }
                  else
                  {
                    if ( !wcscmp_0(Str1, L"Rfc3565KeyWrapBlob") )
                    {
                      LODWORD(v36) = v17;
                      v23 = MSCryptAesKeyUnwrap((int)a1, a2, (int)v39, a5, a6, v16, v36);
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
                    v37 = 42;
                    Src = -69;
                  }
                  WPP_SF_sDsd(
                    v22[3],
                    v18,
                    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                    (unsigned int)"Status",
                    Src,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                    v37);
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
0x180017cf0  mov     [rsp-40h+arg_18], r9
0x180017cf5  push    rbp
0x180017cf6  push    rbx
0x180017cf7  push    rsi
0x180017cf8  push    rdi
0x180017cf9  push    r12
0x180017cfb  push    r13
0x180017cfd  push    r14
0x180017cff  push    r15
0x180017d01  mov     rbp, rsp
0x180017d04  sub     rsp, 58h
0x180017d08  mov     r12, rdx
0x180017d0b  mov     rbx, r8
0x180017d0e  xor     edx, edx
0x180017d10  mov     r13, rcx
0x180017d13  mov     qword ptr [rbp+var_10], rdx
0x180017d17  mov     [rbp+var_18], edx
0x180017d1a  cmp     [rbp+arg_40], edx
0x180017d20  jnz     loc_180017F62
0x180017d26  call    validateMSCryptSymmAlgorithm
0x180017d2b  mov     r15, rax
0x180017d2e  test    rax, rax
0x180017d31  jz      loc_180018027
0x180017d37  mov     esi, edx
0x180017d39  cmp     [rbp+arg_20], rdx
0x180017d3d  jz      loc_1800180B9
0x180017d43  mov     rdi, [rbp+arg_30]
0x180017d47  test    rdi, rdi
0x180017d4a  jz      loc_1800180B9
0x180017d50  test    rbx, rbx
0x180017d53  jz      loc_180018032
0x180017d59  test    r9, r9
0x180017d5c  jz      loc_18001803A
0x180017d62  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x180017d69  mov     rcx, rbx; Str1
0x180017d6c  call    wcscmp_0
0x180017d71  test    eax, eax
0x180017d73  jz      loc_18001804F
0x180017d79  mov     r14d, dword ptr [rbp+arg_38]
0x180017d80  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x180017d87  mov     rcx, rbx; Str1
0x180017d8a  call    wcscmp_0
0x180017d8f  test    eax, eax
0x180017d91  jz      loc_180017E3C
0x180017d97  lea     rdx, aKeydatablob; "KeyDataBlob"
0x180017d9e  mov     rcx, rbx; Str1
0x180017da1  call    wcscmp_0
0x180017da6  test    eax, eax
0x180017da8  jnz     loc_180017E9E
0x180017dae  cmp     r14d, 0Ch
0x180017db2  jb      loc_180017E51
0x180017db8  cmp     dword ptr [rdi], 4D42444Bh
0x180017dbe  jnz     loc_180017F15
0x180017dc4  cmp     dword ptr [rdi+4], 1
0x180017dc8  jnz     loc_180017F15
0x180017dce  mov     ecx, [rdi+8]
0x180017dd1  mov     eax, r14d
0x180017dd4  sub     rax, 0Ch
0x180017dd8  cmp     rax, rcx
0x180017ddb  jb      loc_180017F15
0x180017de1  mov     r9d, [rbp+arg_28]; int
0x180017de5  lea     rax, [rdi+0Ch]
0x180017de9  mov     r8, [rbp+arg_20]; int
0x180017ded  lea     rdx, [rbp+var_10]; int
0x180017df1  mov     dword ptr [rsp+58h+var_28], 80h; int
0x180017df9  mov     dword ptr [rsp+58h+Size], ecx; Size
0x180017dfd  mov     rcx, r13; int
0x180017e00  mov     [rsp+58h+Src], rax; Src
0x180017e05  call    MSCryptGenerateSymmetricKey
0x180017e0a  mov     ebx, eax
0x180017e0c  test    eax, eax
0x180017e0e  js      loc_1800180AC
0x180017e14  mov     rcx, [rbp+arg_18]
0x180017e18  mov     rax, qword ptr [rbp+var_10]
0x180017e1c  mov     [rcx], rax
0x180017e1f  test    rsi, rsi
0x180017e22  jnz     loc_180018003
0x180017e28  mov     eax, ebx
0x180017e2a  add     rsp, 58h
0x180017e2e  pop     r15
0x180017e30  pop     r14
0x180017e32  pop     r13
0x180017e34  pop     r12
0x180017e36  pop     rdi
0x180017e37  pop     rsi
0x180017e38  pop     rbx
0x180017e39  pop     rbp
0x180017e3a  retn
0x180017e3c  mov     r9d, [rbp+arg_28]
0x180017e40  cmp     r9d, [r15+1Ch]
0x180017e44  jnb     loc_18001807B
0x180017e4a  mov     ebx, 0C0000023h
0x180017e4f  jmp     short loc_180017E1F
0x180017e51  mov     ebx, 0C0000023h
0x180017e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e5d  lea     rax, WPP_GLOBAL_Control
0x180017e64  cmp     rcx, rax
0x180017e67  jz      short loc_180017E1F
0x180017e69  mov     eax, [rcx+2Ch]
0x180017e6c  test    al, 1
0x180017e6e  jz      short loc_180017E1F
0x180017e70  mov     dword ptr [rsp+58h+var_28], 5FBh
0x180017e78  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017e7f  mov     [rsp+58h+Size], r8
0x180017e84  mov     dword ptr [rsp+58h+Src], 0C0000023h
0x180017e8c  mov     rcx, [rcx+18h]
0x180017e90  lea     r9, aStatus; "Status"
0x180017e97  call    WPP_SF_sDsd
0x180017e9c  jmp     short loc_180017E1F
0x180017e9e  lea     rdx, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x180017ea5  mov     rcx, rbx; Str1
0x180017ea8  call    wcscmp_0
0x180017ead  test    eax, eax
0x180017eaf  jnz     loc_180017FBB
0x180017eb5  mov     eax, [rbp+arg_28]
0x180017eb8  lea     r8, [rbp+var_10]; int
0x180017ebc  mov     r9, [rbp+arg_20]; int
0x180017ec0  mov     rdx, r12; int
0x180017ec3  mov     dword ptr [rsp+58h+var_28], r14d; Size
0x180017ec8  mov     rcx, r13; int
0x180017ecb  mov     [rsp+58h+Size], rdi; Src
0x180017ed0  mov     dword ptr [rsp+58h+Src], eax; int
0x180017ed4  call    MSCryptAesKeyUnwrap
0x180017ed9  mov     ebx, eax
0x180017edb  test    eax, eax
0x180017edd  jns     loc_180017E14
0x180017ee3  mov     ecx, eax
0x180017ee5  mov     r9d, 623h
0x180017eeb  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017ef2  lea     rdx, aStatus; "Status"
0x180017ef9  call    DebugTraceError
0x180017efe  mov     rcx, qword ptr [rbp+var_10]
0x180017f02  test    rcx, rcx
0x180017f05  jz      loc_180017E1F
0x180017f0b  call    MSCryptDestroyKey
0x180017f10  jmp     loc_180017E1F
0x180017f15  mov     ebx, 0C000000Dh
0x180017f1a  mov     r10, cs:WPP_GLOBAL_Control
0x180017f21  lea     rax, WPP_GLOBAL_Control
0x180017f28  cmp     r10, rax
0x180017f2b  jz      loc_180017E1F
0x180017f31  mov     eax, [r10+2Ch]
0x180017f35  test    al, 1
0x180017f37  jz      loc_180017E1F
0x180017f3d  mov     rcx, [r10+18h]
0x180017f41  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017f48  mov     dword ptr [rsp+58h+var_28], 605h
0x180017f50  mov     [rsp+58h+Size], r8
0x180017f55  mov     dword ptr [rsp+58h+Src], 0C000000Dh
0x180017f5d  jmp     loc_180017E90
0x180017f62  mov     ebx, 0C000000Dh
0x180017f67  mov     r10, cs:WPP_GLOBAL_Control
0x180017f6e  lea     rax, WPP_GLOBAL_Control
0x180017f75  cmp     r10, rax
0x180017f78  jz      loc_180017E28
0x180017f7e  mov     eax, [r10+2Ch]
0x180017f82  test    al, 1
0x180017f84  jz      loc_180017E28
0x180017f8a  mov     rcx, [r10+18h]
0x180017f8e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017f95  mov     dword ptr [rsp+58h+var_28], 58Bh
0x180017f9d  lea     r9, aStatus; "Status"
0x180017fa4  mov     [rsp+58h+Size], r8
0x180017fa9  mov     dword ptr [rsp+58h+Src], 0C000000Dh
0x180017fb1  call    WPP_SF_sDsd
0x180017fb6  jmp     loc_180017E28
0x180017fbb  mov     ebx, 0C00000BBh
0x180017fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180017fc7  lea     rax, WPP_GLOBAL_Control
0x180017fce  cmp     rcx, rax
0x180017fd1  jz      loc_180017E1F
0x180017fd7  mov     eax, [rcx+2Ch]
0x180017fda  test    al, 1
0x180017fdc  jz      loc_180017E1F
0x180017fe2  mov     dword ptr [rsp+58h+var_28], 62Ah
0x180017fea  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017ff1  mov     [rsp+58h+Size], r8
0x180017ff6  mov     dword ptr [rsp+58h+Src], 0C00000BBh
0x180017ffe  jmp     loc_180017E8C
0x180018003  mov     ecx, [rbp+var_18]
0x180018006  mov     rax, rsi
0x180018009  test    rcx, rcx
0x18001800c  jz      short loc_18001801A
0x18001800e  mov     byte ptr [rax], 0
0x180018011  inc     rax
0x180018014  sub     rcx, 1
0x180018018  jnz     short loc_18001800E
0x18001801a  mov     rcx, rsi; P
0x18001801d  call    MSCryptFree
0x180018022  jmp     loc_180017E28
0x180018027  mov     r9d, 594h
0x18001802d  jmp     loc_18009FAE0
0x180018032  mov     r9d, 5A2h
0x180018038  jmp     short loc_180018040
0x18001803a  mov     r9d, 5A9h
0x180018040  mov     ebx, 0C000000Dh
0x180018045  mov     ecx, 0C000000Dh
0x18001804a  jmp     loc_18009FAFC
0x18001804f  test    r12, r12
0x180018052  jz      loc_18009FADA
0x180018058  cmp     dword ptr [r15+8], 10002h
0x180018060  jz      loc_18009FB15
0x180018066  mov     ebx, 0C00000BBh
0x18001806b  mov     r9d, 5BAh
0x180018071  mov     ecx, 0C00000BBh
0x180018076  jmp     loc_18009FAFC
0x18001807b  mov     r8, [rbp+arg_20]
0x18001807f  lea     rdx, [rbp+var_10]
0x180018083  mov     dword ptr [rsp+58h+Size], r14d; int
0x180018088  mov     rcx, r15; int
0x18001808b  mov     [rsp+58h+Src], rdi; Src
0x180018090  call    MSCryptImportKeyOpaque
0x180018095  mov     ebx, eax
0x180018097  test    eax, eax
0x180018099  jns     loc_180017E14
0x18001809f  mov     ecx, eax
0x1800180a1  mov     r9d, 5F0h
0x1800180a7  jmp     loc_180017EEB
0x1800180ac  mov     ecx, eax
0x1800180ae  mov     r9d, 612h
0x1800180b4  jmp     loc_180017EEB
0x1800180b9  mov     ebx, 0C000000Dh
0x1800180be  mov     ecx, 0C000000Dh
0x1800180c3  mov     r9d, 59Bh
0x1800180c9  jmp     loc_180017EEB
0x18009fada  mov     r9d, 5B3h
0x18009fae0  mov     ebx, 0C0000008h
0x18009fae5  mov     ecx, 0C0000008h
0x18009faea  jmp     short loc_18009FAFC
0x18009faec  mov     ebx, 0C0000017h
0x18009faf1  mov     r9d, 5CDh
0x18009faf7  mov     ecx, 0C0000017h
0x18009fafc  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18009fb03  lea     rdx, aStatus; "Status"
0x18009fb0a  call    DebugTraceError
0x18009fb0f  nop
0x18009fb10  jmp     loc_180017E28
0x18009fb15  mov     r14d, dword ptr [rbp+arg_38]
0x18009fb1c  lea     r9, [rbp+var_18]
0x18009fb20  mov     dword ptr [rsp+58h+Size], r14d
0x18009fb25  xor     r8d, r8d
0x18009fb28  mov     rdx, r12
0x18009fb2b  mov     [rsp+58h+Src], rdi
0x18009fb30  mov     rcx, r13
0x18009fb33  call    Pkcs11ConvertToKeyBlob
0x18009fb38  mov     ebx, eax
0x18009fb3a  test    eax, eax
0x18009fb3c  jns     short loc_18009FB48
0x18009fb3e  mov     r9d, 5C6h
0x18009fb44  mov     ecx, eax
0x18009fb46  jmp     short loc_18009FAFC
0x18009fb48  mov     ecx, [rbp+var_18]
0x18009fb4b  call    MSCryptAlloc
0x18009fb50  mov     rsi, rax
0x18009fb53  test    rax, rax
0x18009fb56  jz      short loc_18009FAEC
0x18009fb58  mov     dword ptr [rsp+58h+Size], r14d
0x18009fb5d  lea     r9, [rbp+var_18]
0x18009fb61  mov     r8, rax
0x18009fb64  mov     [rsp+58h+Src], rdi
0x18009fb69  mov     rdx, r12
0x18009fb6c  mov     rcx, r13
0x18009fb6f  call    Pkcs11ConvertToKeyBlob
0x18009fb74  mov     ebx, eax
0x18009fb76  test    eax, eax
0x18009fb78  jns     short loc_18009FB9B
0x18009fb7a  mov     r9d, 5D9h
0x18009fb80  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18009fb87  lea     rdx, aStatus; "Status"
0x18009fb8e  mov     ecx, eax
0x18009fb90  call    DebugTraceError
0x18009fb95  nop
0x18009fb96  jmp     loc_180018003
0x18009fb9b  mov     r14d, [rbp+var_18]
0x18009fb9f  lea     rbx, aKeydatablob; "KeyDataBlob"
0x18009fba6  mov     rdi, rsi
0x18009fba9  jmp     loc_180017D80
```
