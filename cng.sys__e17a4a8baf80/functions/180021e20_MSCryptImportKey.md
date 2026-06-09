# MSCryptImportKey

- ea: `0x180021e20`
- end: `0x1800221fe`
- name: `MSCryptImportKey`
- size: `990`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, wchar_t *Str1@<r8>, int, int, void *, size_t, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180020c70`

## callees

- `0x18000e090`
- `0x180010530`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x1800210a0`
- `0x180021e20`
- `0x180022204`
- `0x180023a50`
- `0x180023f00`
- `0x180088308`
- `0x1800a4232`

## string_xrefs

- `0x180021fa8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002201b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180022071`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800220be`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002211a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800a689a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800a691e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

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
  _DWORD *v33; // rax
  int v34; // eax
  char Src; // [rsp+20h] [rbp-38h]
  size_t Size; // [rsp+28h] [rbp-30h]
  size_t v37; // [rsp+30h] [rbp-28h]
  char v38; // [rsp+30h] [rbp-28h]
  unsigned int v39; // [rsp+40h] [rbp-18h] BYREF
  int v40[2]; // [rsp+48h] [rbp-10h] BYREF

  *(_QWORD *)v40 = 0;
  v39 = 0;
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
        v25 = 1436;
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
              v31 = Pkcs11ConvertToKeyBlob(a1, a2, 0, &v39, a7, a8);
              v20 = v31;
              if ( v31 >= 0 )
              {
                v33 = (_DWORD *)MSCryptAlloc(v39, v32);
                v15 = (unsigned __int64)v33;
                if ( v33 )
                {
                  v34 = Pkcs11ConvertToKeyBlob(a1, a2, v33, &v39, a7, a8);
                  v20 = v34;
                  if ( v34 < 0 )
                  {
                    DebugTraceError(
                      (unsigned int)v34,
                      "Status",
                      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                      1498);
LABEL_40:
                    v26 = v39;
                    v27 = (_BYTE *)v15;
                    if ( v39 )
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
                  v17 = v39;
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
                    v25 = 1521;
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
                            6);
                        }
LABEL_17:
                        if ( !v15 )
                          return v20;
                        goto LABEL_40;
                      }
                      LODWORD(Size) = v16[2];
                      SymmetricKey = MSCryptGenerateSymmetricKey(a1, (int)v40, a5, a6, v16 + 3, Size, 128);
                      v20 = SymmetricKey;
                      if ( SymmetricKey >= 0 )
                      {
LABEL_16:
                        *a4 = *(_QWORD *)v40;
                        goto LABEL_17;
                      }
                      v24 = (unsigned int)SymmetricKey;
                      v25 = 1555;
LABEL_29:
                      DebugTraceError(
                        v24,
                        "Status",
                        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                        v25);
                      if ( *(_QWORD *)v40 )
                        MSCryptDestroyKey(*(_QWORD *)v40);
                      goto LABEL_17;
                    }
                    v20 = -1073741789;
                    v22 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
                    {
                      goto LABEL_17;
                    }
                    v38 = -4;
                    Src = 35;
                  }
                  else
                  {
                    if ( !wcscmp_0(Str1, L"Rfc3565KeyWrapBlob") )
                    {
                      LODWORD(v37) = v17;
                      v23 = MSCryptAesKeyUnwrap(a1, a2, (int)v40, a5, a6, v16, v37);
                      v20 = v23;
                      if ( v23 >= 0 )
                        goto LABEL_16;
                      v24 = (unsigned int)v23;
                      v25 = 1572;
                      goto LABEL_29;
                    }
                    v20 = -1073741637;
                    v22 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
                    {
                      goto LABEL_17;
                    }
                    v38 = 43;
                    Src = -69;
                  }
                  WPP_SF_sDsd(
                    v22[3],
                    v18,
                    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                    (unsigned int)"Status",
                    Src,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                    v38);
                  goto LABEL_17;
                }
                v20 = -1073741801;
                v28 = 1486;
                v29 = 3221225495LL;
              }
              else
              {
                v28 = 1479;
                v29 = (unsigned int)v31;
              }
            }
            else
            {
              v20 = -1073741637;
              v28 = 1467;
              v29 = 3221225659LL;
            }
LABEL_57:
            DebugTraceError(v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v28);
            return v20;
          }
          v28 = 1460;
LABEL_55:
          v20 = -1073741816;
          v29 = 3221225480LL;
          goto LABEL_57;
        }
        v28 = 1450;
      }
      else
      {
        v28 = 1443;
      }
      v20 = -1073741811;
      v29 = 3221225485LL;
      goto LABEL_57;
    }
    v28 = 1429;
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
      140);
  return v20;
}

```

## disassembly

```asm
0x180021e20  mov     [rsp-40h+arg_18], r9
0x180021e25  push    rbp
0x180021e26  push    rbx
0x180021e27  push    rsi
0x180021e28  push    rdi
0x180021e29  push    r12
0x180021e2b  push    r13
0x180021e2d  push    r14
0x180021e2f  push    r15
0x180021e31  mov     rbp, rsp
0x180021e34  sub     rsp, 58h
0x180021e38  mov     r12, rdx
0x180021e3b  mov     rbx, r8
0x180021e3e  xor     edx, edx
0x180021e40  mov     r13, rcx
0x180021e43  mov     qword ptr [rbp+var_10], rdx
0x180021e47  mov     [rbp+var_18], edx
0x180021e4a  cmp     [rbp+arg_40], edx
0x180021e50  jnz     loc_180022092
0x180021e56  call    validateMSCryptSymmAlgorithm
0x180021e5b  mov     r15, rax
0x180021e5e  test    rax, rax
0x180021e61  jz      loc_180022157
0x180021e67  mov     esi, edx
0x180021e69  cmp     [rbp+arg_20], rdx
0x180021e6d  jz      loc_1800221E9
0x180021e73  mov     rdi, [rbp+arg_30]
0x180021e77  test    rdi, rdi
0x180021e7a  jz      loc_1800221E9
0x180021e80  test    rbx, rbx
0x180021e83  jz      loc_180022162
0x180021e89  test    r9, r9
0x180021e8c  jz      loc_18002216A
0x180021e92  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x180021e99  mov     rcx, rbx; Str1
0x180021e9c  call    wcscmp_0
0x180021ea1  test    eax, eax
0x180021ea3  jz      loc_18002217F
0x180021ea9  mov     r14d, dword ptr [rbp+arg_38]
0x180021eb0  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x180021eb7  mov     rcx, rbx; Str1
0x180021eba  call    wcscmp_0
0x180021ebf  test    eax, eax
0x180021ec1  jz      loc_180021F6C
0x180021ec7  lea     rdx, aKeydatablob; "KeyDataBlob"
0x180021ece  mov     rcx, rbx; Str1
0x180021ed1  call    wcscmp_0
0x180021ed6  test    eax, eax
0x180021ed8  jnz     loc_180021FCE
0x180021ede  cmp     r14d, 0Ch
0x180021ee2  jb      loc_180021F81
0x180021ee8  cmp     dword ptr [rdi], 4D42444Bh
0x180021eee  jnz     loc_180022045
0x180021ef4  cmp     dword ptr [rdi+4], 1
0x180021ef8  jnz     loc_180022045
0x180021efe  mov     ecx, [rdi+8]
0x180021f01  mov     eax, r14d
0x180021f04  sub     rax, 0Ch
0x180021f08  cmp     rax, rcx
0x180021f0b  jb      loc_180022045
0x180021f11  mov     r9d, [rbp+arg_28]; int
0x180021f15  lea     rax, [rdi+0Ch]
0x180021f19  mov     r8, [rbp+arg_20]; int
0x180021f1d  lea     rdx, [rbp+var_10]; int
0x180021f21  mov     dword ptr [rsp+58h+var_28], 80h; int
0x180021f29  mov     dword ptr [rsp+58h+Size], ecx; Size
0x180021f2d  mov     rcx, r13; int
0x180021f30  mov     [rsp+58h+Src], rax; Src
0x180021f35  call    MSCryptGenerateSymmetricKey
0x180021f3a  mov     ebx, eax
0x180021f3c  test    eax, eax
0x180021f3e  js      loc_1800221DC
0x180021f44  mov     rcx, [rbp+arg_18]
0x180021f48  mov     rax, qword ptr [rbp+var_10]
0x180021f4c  mov     [rcx], rax
0x180021f4f  test    rsi, rsi
0x180021f52  jnz     loc_180022133
0x180021f58  mov     eax, ebx
0x180021f5a  add     rsp, 58h
0x180021f5e  pop     r15
0x180021f60  pop     r14
0x180021f62  pop     r13
0x180021f64  pop     r12
0x180021f66  pop     rdi
0x180021f67  pop     rsi
0x180021f68  pop     rbx
0x180021f69  pop     rbp
0x180021f6a  retn
0x180021f6c  mov     r9d, [rbp+arg_28]
0x180021f70  cmp     r9d, [r15+1Ch]
0x180021f74  jnb     loc_1800221AB
0x180021f7a  mov     ebx, 0C0000023h
0x180021f7f  jmp     short loc_180021F4F
0x180021f81  mov     ebx, 0C0000023h
0x180021f86  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f8d  lea     rax, WPP_GLOBAL_Control
0x180021f94  cmp     rcx, rax
0x180021f97  jz      short loc_180021F4F
0x180021f99  mov     eax, [rcx+2Ch]
0x180021f9c  test    al, 1
0x180021f9e  jz      short loc_180021F4F
0x180021fa0  mov     dword ptr [rsp+58h+var_28], 5FCh
0x180021fa8  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021faf  mov     [rsp+58h+Size], r8
0x180021fb4  mov     dword ptr [rsp+58h+Src], 0C0000023h
0x180021fbc  mov     rcx, [rcx+18h]
0x180021fc0  lea     r9, aStatus; "Status"
0x180021fc7  call    WPP_SF_sDsd
0x180021fcc  jmp     short loc_180021F4F
0x180021fce  lea     rdx, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x180021fd5  mov     rcx, rbx; Str1
0x180021fd8  call    wcscmp_0
0x180021fdd  test    eax, eax
0x180021fdf  jnz     loc_1800220EB
0x180021fe5  mov     eax, [rbp+arg_28]
0x180021fe8  lea     r8, [rbp+var_10]; int
0x180021fec  mov     r9, [rbp+arg_20]; int
0x180021ff0  mov     rdx, r12; int
0x180021ff3  mov     dword ptr [rsp+58h+var_28], r14d; Size
0x180021ff8  mov     rcx, r13; int
0x180021ffb  mov     [rsp+58h+Size], rdi; Src
0x180022000  mov     dword ptr [rsp+58h+Src], eax; int
0x180022004  call    MSCryptAesKeyUnwrap
0x180022009  mov     ebx, eax
0x18002200b  test    eax, eax
0x18002200d  jns     loc_180021F44
0x180022013  mov     ecx, eax
0x180022015  mov     r9d, 624h
0x18002201b  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022022  lea     rdx, aStatus; "Status"
0x180022029  call    DebugTraceError
0x18002202e  mov     rcx, qword ptr [rbp+var_10]
0x180022032  test    rcx, rcx
0x180022035  jz      loc_180021F4F
0x18002203b  call    MSCryptDestroyKey
0x180022040  jmp     loc_180021F4F
0x180022045  mov     ebx, 0C000000Dh
0x18002204a  mov     r10, cs:WPP_GLOBAL_Control
0x180022051  lea     rax, WPP_GLOBAL_Control
0x180022058  cmp     r10, rax
0x18002205b  jz      loc_180021F4F
0x180022061  mov     eax, [r10+2Ch]
0x180022065  test    al, 1
0x180022067  jz      loc_180021F4F
0x18002206d  mov     rcx, [r10+18h]
0x180022071  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022078  mov     dword ptr [rsp+58h+var_28], 606h
0x180022080  mov     [rsp+58h+Size], r8
0x180022085  mov     dword ptr [rsp+58h+Src], 0C000000Dh
0x18002208d  jmp     loc_180021FC0
0x180022092  mov     ebx, 0C000000Dh
0x180022097  mov     r10, cs:WPP_GLOBAL_Control
0x18002209e  lea     rax, WPP_GLOBAL_Control
0x1800220a5  cmp     r10, rax
0x1800220a8  jz      loc_180021F58
0x1800220ae  mov     eax, [r10+2Ch]
0x1800220b2  test    al, 1
0x1800220b4  jz      loc_180021F58
0x1800220ba  mov     rcx, [r10+18h]
0x1800220be  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800220c5  mov     dword ptr [rsp+58h+var_28], 58Ch
0x1800220cd  lea     r9, aStatus; "Status"
0x1800220d4  mov     [rsp+58h+Size], r8
0x1800220d9  mov     dword ptr [rsp+58h+Src], 0C000000Dh
0x1800220e1  call    WPP_SF_sDsd
0x1800220e6  jmp     loc_180021F58
0x1800220eb  mov     ebx, 0C00000BBh
0x1800220f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220f7  lea     rax, WPP_GLOBAL_Control
0x1800220fe  cmp     rcx, rax
0x180022101  jz      loc_180021F4F
0x180022107  mov     eax, [rcx+2Ch]
0x18002210a  test    al, 1
0x18002210c  jz      loc_180021F4F
0x180022112  mov     dword ptr [rsp+58h+var_28], 62Bh
0x18002211a  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022121  mov     [rsp+58h+Size], r8
0x180022126  mov     dword ptr [rsp+58h+Src], 0C00000BBh
0x18002212e  jmp     loc_180021FBC
0x180022133  mov     ecx, [rbp+var_18]
0x180022136  mov     rax, rsi
0x180022139  test    rcx, rcx
0x18002213c  jz      short loc_18002214A
0x18002213e  mov     byte ptr [rax], 0
0x180022141  inc     rax
0x180022144  sub     rcx, 1
0x180022148  jnz     short loc_18002213E
0x18002214a  mov     rcx, rsi; P
0x18002214d  call    MSCryptFree
0x180022152  jmp     loc_180021F58
0x180022157  mov     r9d, 595h
0x18002215d  jmp     loc_1800A687E
0x180022162  mov     r9d, 5A3h
0x180022168  jmp     short loc_180022170
0x18002216a  mov     r9d, 5AAh
0x180022170  mov     ebx, 0C000000Dh
0x180022175  mov     ecx, 0C000000Dh
0x18002217a  jmp     loc_1800A689A
0x18002217f  test    r12, r12
0x180022182  jz      loc_1800A6878
0x180022188  cmp     dword ptr [r15+8], 10002h
0x180022190  jz      loc_1800A68B3
0x180022196  mov     ebx, 0C00000BBh
0x18002219b  mov     r9d, 5BBh
0x1800221a1  mov     ecx, 0C00000BBh
0x1800221a6  jmp     loc_1800A689A
0x1800221ab  mov     r8, [rbp+arg_20]
0x1800221af  lea     rdx, [rbp+var_10]
0x1800221b3  mov     dword ptr [rsp+58h+Size], r14d; int
0x1800221b8  mov     rcx, r15; int
0x1800221bb  mov     [rsp+58h+Src], rdi; Src
0x1800221c0  call    MSCryptImportKeyOpaque
0x1800221c5  mov     ebx, eax
0x1800221c7  test    eax, eax
0x1800221c9  jns     loc_180021F44
0x1800221cf  mov     ecx, eax
0x1800221d1  mov     r9d, 5F1h
0x1800221d7  jmp     loc_18002201B
0x1800221dc  mov     ecx, eax
0x1800221de  mov     r9d, 613h
0x1800221e4  jmp     loc_18002201B
0x1800221e9  mov     ebx, 0C000000Dh
0x1800221ee  mov     ecx, 0C000000Dh
0x1800221f3  mov     r9d, 59Ch
0x1800221f9  jmp     loc_18002201B
0x1800a6878  mov     r9d, 5B4h
0x1800a687e  mov     ebx, 0C0000008h
0x1800a6883  mov     ecx, 0C0000008h
0x1800a6888  jmp     short loc_1800A689A
0x1800a688a  mov     ebx, 0C0000017h
0x1800a688f  mov     r9d, 5CEh
0x1800a6895  mov     ecx, 0C0000017h
0x1800a689a  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a68a1  lea     rdx, aStatus; "Status"
0x1800a68a8  call    DebugTraceError
0x1800a68ad  nop
0x1800a68ae  jmp     loc_180021F58
0x1800a68b3  mov     r14d, dword ptr [rbp+arg_38]
0x1800a68ba  lea     r9, [rbp+var_18]
0x1800a68be  mov     dword ptr [rsp+58h+Size], r14d
0x1800a68c3  xor     r8d, r8d
0x1800a68c6  mov     rdx, r12
0x1800a68c9  mov     [rsp+58h+Src], rdi
0x1800a68ce  mov     rcx, r13
0x1800a68d1  call    Pkcs11ConvertToKeyBlob
0x1800a68d6  mov     ebx, eax
0x1800a68d8  test    eax, eax
0x1800a68da  jns     short loc_1800A68E6
0x1800a68dc  mov     r9d, 5C7h
0x1800a68e2  mov     ecx, eax
0x1800a68e4  jmp     short loc_1800A689A
0x1800a68e6  mov     ecx, [rbp+var_18]
0x1800a68e9  call    MSCryptAlloc
0x1800a68ee  mov     rsi, rax
0x1800a68f1  test    rax, rax
0x1800a68f4  jz      short loc_1800A688A
0x1800a68f6  mov     dword ptr [rsp+58h+Size], r14d
0x1800a68fb  lea     r9, [rbp+var_18]
0x1800a68ff  mov     r8, rax
0x1800a6902  mov     [rsp+58h+Src], rdi
0x1800a6907  mov     rdx, r12
0x1800a690a  mov     rcx, r13
0x1800a690d  call    Pkcs11ConvertToKeyBlob
0x1800a6912  mov     ebx, eax
0x1800a6914  test    eax, eax
0x1800a6916  jns     short loc_1800A6939
0x1800a6918  mov     r9d, 5DAh
0x1800a691e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a6925  lea     rdx, aStatus; "Status"
0x1800a692c  mov     ecx, eax
0x1800a692e  call    DebugTraceError
0x1800a6933  nop
0x1800a6934  jmp     loc_180022133
0x1800a6939  mov     r14d, [rbp+var_18]
0x1800a693d  lea     rbx, aKeydatablob; "KeyDataBlob"
0x1800a6944  mov     rdi, rsi
0x1800a6947  jmp     loc_180021EB0
```
