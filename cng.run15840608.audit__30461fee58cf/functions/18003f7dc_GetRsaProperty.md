# GetRsaProperty

- ea: `0x18003f7dc`
- end: `0x18003f9df`
- name: `GetRsaProperty`
- size: `515`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003f7b0`
- `0x180077940`
- `0x18007e108`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003f7dc`
- `0x18003f9e8`
- `0x18003fc68`
- `0x1800776d4`
- `0x18009d746`

## import_xrefs

- `ntoskrnl!wcscpy_s` at `0x1800a1bee`
- `ntoskrnl!wcscpy_s` at `0x1800a1bee`

## string_xrefs

- `0x18003f8d9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x1800a1c18`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall GetRsaProperty(
        __int64 a1,
        const wchar_t *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int a6,
        char a7)
{
  unsigned __int64 v8; // rsi
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v14; // rbp
  __int64 v15; // r9
  __int64 v16; // rcx
  char v17; // r8
  unsigned int v18; // ecx
  bool v19; // zf
  const wchar_t *v20; // r8
  unsigned int v21; // eax
  __int64 v22; // rax
  int v23; // eax

  v8 = a4;
  if ( a6 )
  {
    v12 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        78);
    return v12;
  }
  if ( !a2 )
  {
    v12 = -1073741811;
    v15 = 597;
    v16 = 3221225485LL;
LABEL_34:
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v15);
    return v12;
  }
  if ( !a1 || (v11 = *(_DWORD *)(a1 + 4), v11 != 1297306177) && v11 != 1297306187 )
  {
    v12 = -1073741816;
    v15 = 605;
    v16 = 3221225480LL;
    goto LABEL_34;
  }
  if ( !wcscmp_0(a2, L"AlgorithmName") )
  {
    v17 = a7;
    v18 = a7 != 0 ? 18 : 8;
    *a5 = v18;
    if ( !a3 )
      return 0;
    if ( (unsigned int)v8 >= v18 )
    {
      v19 = v17 == 0;
      v20 = L"RSA_SIGN";
      if ( v19 )
        v20 = L"RSA";
      wcscpy_s((wchar_t *)a3, v8 >> 1, v20);
      return 0;
    }
    return (unsigned int)-1073741789;
  }
  if ( validateMSCryptRsaAlgorithm(a1) )
  {
    if ( !wcscmp_0(a2, L"PaddingSchemes") )
    {
      *a5 = 4;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 >= 4 )
      {
        *(_DWORD *)a3 = a7 != 0 ? 20 : 30;
        return 0;
      }
      return (unsigned int)-1073741789;
    }
    if ( !wcscmp_0(a2, L"KeyLengths") )
    {
      *a5 = 12;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 >= 0xC )
      {
        *(_DWORD *)a3 = 512;
        *(_DWORD *)(a3 + 4) = 0x4000;
        *(_DWORD *)(a3 + 8) = 8;
        return 0;
      }
      return (unsigned int)-1073741789;
    }
    v15 = 707;
LABEL_33:
    v12 = -1073741637;
    v16 = 3221225659LL;
    goto LABEL_34;
  }
  v14 = validateMSCryptRsaKey(a1);
  if ( v14 )
  {
    if ( !wcscmp_0(a2, L"KeyStrength") || !wcscmp_0(a2, L"KeyLength") || !wcscmp_0(a2, L"PublicKeyLength") )
    {
      *a5 = 4;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 < 4 )
        return (unsigned int)-1073741789;
      v21 = *(_DWORD *)(v14 + 12);
    }
    else if ( !wcscmp_0(a2, L"BlockLength") || !wcscmp_0(a2, L"SignatureLength") )
    {
      *a5 = 4;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 < 4 )
        return (unsigned int)-1073741789;
      v22 = *(_QWORD *)(v14 + 32);
      if ( v22 )
        v23 = *(_DWORD *)(v22 + 16);
      else
        v23 = *(_DWORD *)(v14 + 12);
      v21 = (unsigned int)(v23 + 7) >> 3;
    }
    else
    {
      if ( wcscmp_0(a2, L"IsIfxTpmWeakKey") )
      {
        v15 = 781;
        goto LABEL_33;
      }
      a6 = 0;
      *a5 = 4;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 < 4 )
        return (unsigned int)-1073741789;
      v12 = IsIfxTpmWeakKeyProperty(a1, &a6);
      if ( (v12 & 0x80000000) != 0 )
        return v12;
      v21 = a6;
    }
    *(_DWORD *)a3 = v21;
    return 0;
  }
  return 3221225480LL;
}

```

## disassembly

```asm
0x18003f7dc  push    rbx
0x18003f7de  push    rbp
0x18003f7df  push    rsi
0x18003f7e0  push    rdi
0x18003f7e1  push    r14
0x18003f7e3  sub     rsp, 40h
0x18003f7e7  cmp     [rsp+68h+arg_28], 0
0x18003f7ef  mov     rdi, r8
0x18003f7f2  mov     esi, r9d
0x18003f7f5  mov     rbx, rdx
0x18003f7f8  mov     r14, rcx
0x18003f7fb  jnz     loc_18003F8B6
0x18003f801  test    rdx, rdx
0x18003f804  jz      loc_18003F903
0x18003f80a  test    rcx, rcx
0x18003f80d  jz      loc_18003F923
0x18003f813  mov     eax, [rcx+4]
0x18003f816  cmp     eax, 4D535241h
0x18003f81b  jnz     loc_18003F918
0x18003f821  lea     rdx, aAlgorithmname; "AlgorithmName"
0x18003f828  mov     rcx, rbx; Str1
0x18003f82b  call    wcscmp_0
0x18003f830  test    eax, eax
0x18003f832  jz      loc_18003F938
0x18003f838  mov     rcx, r14
0x18003f83b  call    validateMSCryptRsaAlgorithm
0x18003f840  test    rax, rax
0x18003f843  jz      short loc_18003F89B
0x18003f845  lea     rdx, aPaddingschemes; "PaddingSchemes"
0x18003f84c  mov     rcx, rbx; Str1
0x18003f84f  call    wcscmp_0
0x18003f854  test    eax, eax
0x18003f856  jnz     loc_18003F993
0x18003f85c  mov     rax, [rsp+68h+arg_20]
0x18003f864  mov     dword ptr [rax], 4
0x18003f86a  test    rdi, rdi
0x18003f86d  jz      short loc_18003F88B
0x18003f86f  cmp     esi, 4
0x18003f872  jb      loc_18003F989
0x18003f878  mov     al, [rsp+68h+arg_30]
0x18003f87f  neg     al
0x18003f881  sbb     ecx, ecx
0x18003f883  and     ecx, 0FFFFFFF6h
0x18003f886  add     ecx, 1Eh
0x18003f889  mov     [rdi], ecx
0x18003f88b  xor     ebx, ebx
0x18003f88d  mov     eax, ebx
0x18003f88f  add     rsp, 40h
0x18003f893  pop     r14
0x18003f895  pop     rdi
0x18003f896  pop     rsi
0x18003f897  pop     rbp
0x18003f898  pop     rbx
0x18003f899  retn
0x18003f89b  mov     rcx, r14
0x18003f89e  call    validateMSCryptRsaKey
0x18003f8a3  mov     rbp, rax
0x18003f8a6  test    rax, rax
0x18003f8a9  jnz     loc_1800A1C31
0x18003f8af  mov     eax, 0C0000008h
0x18003f8b4  jmp     short loc_18003F88F
0x18003f8b6  mov     ebx, 0C000000Dh
0x18003f8bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f8c2  lea     rax, WPP_GLOBAL_Control
0x18003f8c9  cmp     rcx, rax
0x18003f8cc  jz      short loc_18003F88D
0x18003f8ce  mov     eax, [rcx+2Ch]
0x18003f8d1  test    al, 1
0x18003f8d3  jz      short loc_18003F88D
0x18003f8d5  mov     rcx, [rcx+18h]
0x18003f8d9  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f8e0  mov     [rsp+68h+var_38], 24Eh
0x18003f8e8  lea     r9, aStatus; "Status"
0x18003f8ef  mov     [rsp+68h+var_40], r8
0x18003f8f4  mov     [rsp+68h+var_48], 0C000000Dh
0x18003f8fc  call    WPP_SF_sDsd
0x18003f901  jmp     short loc_18003F88D
0x18003f903  mov     ebx, 0C000000Dh
0x18003f908  mov     r9d, 255h
0x18003f90e  mov     ecx, 0C000000Dh
0x18003f913  jmp     loc_1800A1C18
0x18003f918  cmp     eax, 4D53524Bh
0x18003f91d  jz      loc_18003F821
0x18003f923  mov     ebx, 0C0000008h
0x18003f928  mov     r9d, 25Dh
0x18003f92e  mov     ecx, 0C0000008h
0x18003f933  jmp     loc_1800A1C18
0x18003f938  mov     r8b, [rsp+68h+arg_30]
0x18003f940  mov     al, r8b
0x18003f943  neg     al
0x18003f945  mov     rax, [rsp+68h+arg_20]
0x18003f94d  sbb     ecx, ecx
0x18003f94f  and     ecx, 0Ah
0x18003f952  add     ecx, 8
0x18003f955  mov     [rax], ecx
0x18003f957  test    rdi, rdi
0x18003f95a  jz      loc_18003F88B
0x18003f960  cmp     esi, ecx
0x18003f962  jb      short loc_18003F989
0x18003f964  mov     rdx, rsi
0x18003f967  mov     rcx, rdi; Dst
0x18003f96a  shr     rdx, 1; SizeInWords
0x18003f96d  test    r8b, r8b
0x18003f970  lea     r8, aRsaSign; "RSA_SIGN"
0x18003f977  jnz     loc_1800A1BEE
0x18003f97d  lea     r8, aRsa; "RSA"
0x18003f984  jmp     loc_1800A1BEE
0x18003f989  mov     ebx, 0C0000023h
0x18003f98e  jmp     loc_18003F88D
0x18003f993  lea     rdx, aKeylengths; "KeyLengths"
0x18003f99a  mov     rcx, rbx; Str1
0x18003f99d  call    wcscmp_0
0x18003f9a2  test    eax, eax
0x18003f9a4  jnz     loc_1800A1C00
0x18003f9aa  mov     rax, [rsp+68h+arg_20]
0x18003f9b2  mov     dword ptr [rax], 0Ch
0x18003f9b8  test    rdi, rdi
0x18003f9bb  jz      loc_18003F88B
0x18003f9c1  cmp     esi, 0Ch
0x18003f9c4  jb      short loc_18003F989
0x18003f9c6  mov     dword ptr [rdi], 200h
0x18003f9cc  mov     dword ptr [rdi+4], 4000h
0x18003f9d3  mov     dword ptr [rdi+8], 8
0x18003f9da  jmp     loc_18003F88B
0x1800a1bee  call    cs:__imp_wcscpy_s
0x1800a1bf5  nop     dword ptr [rax+rax+00h]
0x1800a1bfa  nop
0x1800a1bfb  jmp     loc_18003F88B
0x1800a1c00  mov     r9d, 2C3h
0x1800a1c06  jmp     short loc_1800A1C0E
0x1800a1c08  mov     r9d, 30Dh
0x1800a1c0e  mov     ebx, 0C00000BBh
0x1800a1c13  mov     ecx, 0C00000BBh
0x1800a1c18  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a1c1f  lea     rdx, aStatus; "Status"
0x1800a1c26  call    DebugTraceError
0x1800a1c2b  nop
0x1800a1c2c  jmp     loc_18003F88D
0x1800a1c31  lea     rdx, aKeystrength; "KeyStrength"
0x1800a1c38  mov     rcx, rbx; Str1
0x1800a1c3b  call    wcscmp_0
0x1800a1c40  test    eax, eax
0x1800a1c42  jz      loc_1800A1D36
0x1800a1c48  lea     rdx, aKeylength; "KeyLength"
0x1800a1c4f  mov     rcx, rbx; Str1
0x1800a1c52  call    wcscmp_0
0x1800a1c57  test    eax, eax
0x1800a1c59  jz      loc_1800A1D36
0x1800a1c5f  lea     rdx, aPublickeylengt; "PublicKeyLength"
0x1800a1c66  mov     rcx, rbx; Str1
0x1800a1c69  call    wcscmp_0
0x1800a1c6e  test    eax, eax
0x1800a1c70  jz      loc_1800A1D36
0x1800a1c76  lea     rdx, aBlocklength; "BlockLength"
0x1800a1c7d  mov     rcx, rbx; Str1
0x1800a1c80  call    wcscmp_0
0x1800a1c85  test    eax, eax
0x1800a1c87  jz      short loc_1800A1CFD
0x1800a1c89  lea     rdx, aSignaturelengt; "SignatureLength"
0x1800a1c90  mov     rcx, rbx; Str1
0x1800a1c93  call    wcscmp_0
0x1800a1c98  test    eax, eax
0x1800a1c9a  jz      short loc_1800A1CFD
0x1800a1c9c  lea     rdx, aIsifxtpmweakke; "IsIfxTpmWeakKey"
0x1800a1ca3  mov     rcx, rbx; Str1
0x1800a1ca6  call    wcscmp_0
0x1800a1cab  test    eax, eax
0x1800a1cad  jnz     loc_1800A1C08
0x1800a1cb3  mov     [rsp+68h+arg_28], eax
0x1800a1cba  mov     rax, [rsp+68h+arg_20]
0x1800a1cc2  mov     dword ptr [rax], 4
0x1800a1cc8  test    rdi, rdi
0x1800a1ccb  jz      loc_18003F88B
0x1800a1cd1  cmp     esi, 4
0x1800a1cd4  jb      loc_18003F989
0x1800a1cda  lea     rdx, [rsp+68h+arg_28]
0x1800a1ce2  mov     rcx, r14
0x1800a1ce5  call    IsIfxTpmWeakKeyProperty
0x1800a1cea  mov     ebx, eax
0x1800a1cec  test    eax, eax
0x1800a1cee  js      loc_18003F88D
0x1800a1cf4  mov     eax, [rsp+68h+arg_28]
0x1800a1cfb  jmp     short loc_1800A1D59
0x1800a1cfd  mov     rax, [rsp+68h+arg_20]
0x1800a1d05  mov     dword ptr [rax], 4
0x1800a1d0b  test    rdi, rdi
0x1800a1d0e  jz      loc_18003F88B
0x1800a1d14  cmp     esi, 4
0x1800a1d17  jb      loc_18003F989
0x1800a1d1d  mov     rax, [rbp+20h]
0x1800a1d21  test    rax, rax
0x1800a1d24  jz      short loc_1800A1D2B
0x1800a1d26  mov     eax, [rax+10h]
0x1800a1d29  jmp     short loc_1800A1D2E
0x1800a1d2b  mov     eax, [rbp+0Ch]
0x1800a1d2e  add     eax, 7
0x1800a1d31  shr     eax, 3
0x1800a1d34  jmp     short loc_1800A1D59
0x1800a1d36  mov     rax, [rsp+68h+arg_20]
0x1800a1d3e  mov     dword ptr [rax], 4
0x1800a1d44  test    rdi, rdi
0x1800a1d47  jz      loc_18003F88B
0x1800a1d4d  cmp     esi, 4
0x1800a1d50  jb      loc_18003F989
0x1800a1d56  mov     eax, [rbp+0Ch]
0x1800a1d59  mov     [rdi], eax
0x1800a1d5b  jmp     loc_18003F88B
```
