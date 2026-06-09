# GetRsaProperty

- ea: `0x18004036c`
- end: `0x18004056f`
- name: `GetRsaProperty`
- size: `515`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180040340`
- `0x180078350`
- `0x18007f0f8`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18004036c`
- `0x180040578`
- `0x1800407f8`
- `0x1800780e4`
- `0x18009f616`

## import_xrefs

- `ntoskrnl!wcscpy_s` at `0x1800a3a1e`
- `ntoskrnl!wcscpy_s` at `0x1800a3a1e`

## string_xrefs

- `0x180040469`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x1800a3a48`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

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
0x18004036c  push    rbx
0x18004036e  push    rbp
0x18004036f  push    rsi
0x180040370  push    rdi
0x180040371  push    r14
0x180040373  sub     rsp, 40h
0x180040377  cmp     [rsp+68h+arg_28], 0
0x18004037f  mov     rdi, r8
0x180040382  mov     esi, r9d
0x180040385  mov     rbx, rdx
0x180040388  mov     r14, rcx
0x18004038b  jnz     loc_180040446
0x180040391  test    rdx, rdx
0x180040394  jz      loc_180040493
0x18004039a  test    rcx, rcx
0x18004039d  jz      loc_1800404B3
0x1800403a3  mov     eax, [rcx+4]
0x1800403a6  cmp     eax, 4D535241h
0x1800403ab  jnz     loc_1800404A8
0x1800403b1  lea     rdx, aAlgorithmname; "AlgorithmName"
0x1800403b8  mov     rcx, rbx; Str1
0x1800403bb  call    wcscmp_0
0x1800403c0  test    eax, eax
0x1800403c2  jz      loc_1800404C8
0x1800403c8  mov     rcx, r14
0x1800403cb  call    validateMSCryptRsaAlgorithm
0x1800403d0  test    rax, rax
0x1800403d3  jz      short loc_18004042B
0x1800403d5  lea     rdx, aPaddingschemes; "PaddingSchemes"
0x1800403dc  mov     rcx, rbx; Str1
0x1800403df  call    wcscmp_0
0x1800403e4  test    eax, eax
0x1800403e6  jnz     loc_180040523
0x1800403ec  mov     rax, [rsp+68h+arg_20]
0x1800403f4  mov     dword ptr [rax], 4
0x1800403fa  test    rdi, rdi
0x1800403fd  jz      short loc_18004041B
0x1800403ff  cmp     esi, 4
0x180040402  jb      loc_180040519
0x180040408  mov     al, [rsp+68h+arg_30]
0x18004040f  neg     al
0x180040411  sbb     ecx, ecx
0x180040413  and     ecx, 0FFFFFFF6h
0x180040416  add     ecx, 1Eh
0x180040419  mov     [rdi], ecx
0x18004041b  xor     ebx, ebx
0x18004041d  mov     eax, ebx
0x18004041f  add     rsp, 40h
0x180040423  pop     r14
0x180040425  pop     rdi
0x180040426  pop     rsi
0x180040427  pop     rbp
0x180040428  pop     rbx
0x180040429  retn
0x18004042b  mov     rcx, r14
0x18004042e  call    validateMSCryptRsaKey
0x180040433  mov     rbp, rax
0x180040436  test    rax, rax
0x180040439  jnz     loc_1800A3A61
0x18004043f  mov     eax, 0C0000008h
0x180040444  jmp     short loc_18004041F
0x180040446  mov     ebx, 0C000000Dh
0x18004044b  mov     rcx, cs:WPP_GLOBAL_Control
0x180040452  lea     rax, WPP_GLOBAL_Control
0x180040459  cmp     rcx, rax
0x18004045c  jz      short loc_18004041D
0x18004045e  mov     eax, [rcx+2Ch]
0x180040461  test    al, 1
0x180040463  jz      short loc_18004041D
0x180040465  mov     rcx, [rcx+18h]
0x180040469  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180040470  mov     [rsp+68h+var_38], 24Eh
0x180040478  lea     r9, aStatus; "Status"
0x18004047f  mov     [rsp+68h+var_40], r8
0x180040484  mov     [rsp+68h+var_48], 0C000000Dh
0x18004048c  call    WPP_SF_sDsd
0x180040491  jmp     short loc_18004041D
0x180040493  mov     ebx, 0C000000Dh
0x180040498  mov     r9d, 255h
0x18004049e  mov     ecx, 0C000000Dh
0x1800404a3  jmp     loc_1800A3A48
0x1800404a8  cmp     eax, 4D53524Bh
0x1800404ad  jz      loc_1800403B1
0x1800404b3  mov     ebx, 0C0000008h
0x1800404b8  mov     r9d, 25Dh
0x1800404be  mov     ecx, 0C0000008h
0x1800404c3  jmp     loc_1800A3A48
0x1800404c8  mov     r8b, [rsp+68h+arg_30]
0x1800404d0  mov     al, r8b
0x1800404d3  neg     al
0x1800404d5  mov     rax, [rsp+68h+arg_20]
0x1800404dd  sbb     ecx, ecx
0x1800404df  and     ecx, 0Ah
0x1800404e2  add     ecx, 8
0x1800404e5  mov     [rax], ecx
0x1800404e7  test    rdi, rdi
0x1800404ea  jz      loc_18004041B
0x1800404f0  cmp     esi, ecx
0x1800404f2  jb      short loc_180040519
0x1800404f4  mov     rdx, rsi
0x1800404f7  mov     rcx, rdi; Dst
0x1800404fa  shr     rdx, 1; SizeInWords
0x1800404fd  test    r8b, r8b
0x180040500  lea     r8, aRsaSign; "RSA_SIGN"
0x180040507  jnz     loc_1800A3A1E
0x18004050d  lea     r8, aRsa; "RSA"
0x180040514  jmp     loc_1800A3A1E
0x180040519  mov     ebx, 0C0000023h
0x18004051e  jmp     loc_18004041D
0x180040523  lea     rdx, aKeylengths; "KeyLengths"
0x18004052a  mov     rcx, rbx; Str1
0x18004052d  call    wcscmp_0
0x180040532  test    eax, eax
0x180040534  jnz     loc_1800A3A30
0x18004053a  mov     rax, [rsp+68h+arg_20]
0x180040542  mov     dword ptr [rax], 0Ch
0x180040548  test    rdi, rdi
0x18004054b  jz      loc_18004041B
0x180040551  cmp     esi, 0Ch
0x180040554  jb      short loc_180040519
0x180040556  mov     dword ptr [rdi], 200h
0x18004055c  mov     dword ptr [rdi+4], 4000h
0x180040563  mov     dword ptr [rdi+8], 8
0x18004056a  jmp     loc_18004041B
0x1800a3a1e  call    cs:__imp_wcscpy_s
0x1800a3a25  nop     dword ptr [rax+rax+00h]
0x1800a3a2a  nop
0x1800a3a2b  jmp     loc_18004041B
0x1800a3a30  mov     r9d, 2C3h
0x1800a3a36  jmp     short loc_1800A3A3E
0x1800a3a38  mov     r9d, 30Dh
0x1800a3a3e  mov     ebx, 0C00000BBh
0x1800a3a43  mov     ecx, 0C00000BBh
0x1800a3a48  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a3a4f  lea     rdx, aStatus; "Status"
0x1800a3a56  call    DebugTraceError
0x1800a3a5b  nop
0x1800a3a5c  jmp     loc_18004041D
0x1800a3a61  lea     rdx, aKeystrength; "KeyStrength"
0x1800a3a68  mov     rcx, rbx; Str1
0x1800a3a6b  call    wcscmp_0
0x1800a3a70  test    eax, eax
0x1800a3a72  jz      loc_1800A3B66
0x1800a3a78  lea     rdx, aKeylength; "KeyLength"
0x1800a3a7f  mov     rcx, rbx; Str1
0x1800a3a82  call    wcscmp_0
0x1800a3a87  test    eax, eax
0x1800a3a89  jz      loc_1800A3B66
0x1800a3a8f  lea     rdx, aPublickeylengt; "PublicKeyLength"
0x1800a3a96  mov     rcx, rbx; Str1
0x1800a3a99  call    wcscmp_0
0x1800a3a9e  test    eax, eax
0x1800a3aa0  jz      loc_1800A3B66
0x1800a3aa6  lea     rdx, aBlocklength; "BlockLength"
0x1800a3aad  mov     rcx, rbx; Str1
0x1800a3ab0  call    wcscmp_0
0x1800a3ab5  test    eax, eax
0x1800a3ab7  jz      short loc_1800A3B2D
0x1800a3ab9  lea     rdx, aSignaturelengt; "SignatureLength"
0x1800a3ac0  mov     rcx, rbx; Str1
0x1800a3ac3  call    wcscmp_0
0x1800a3ac8  test    eax, eax
0x1800a3aca  jz      short loc_1800A3B2D
0x1800a3acc  lea     rdx, aIsifxtpmweakke; "IsIfxTpmWeakKey"
0x1800a3ad3  mov     rcx, rbx; Str1
0x1800a3ad6  call    wcscmp_0
0x1800a3adb  test    eax, eax
0x1800a3add  jnz     loc_1800A3A38
0x1800a3ae3  mov     [rsp+68h+arg_28], eax
0x1800a3aea  mov     rax, [rsp+68h+arg_20]
0x1800a3af2  mov     dword ptr [rax], 4
0x1800a3af8  test    rdi, rdi
0x1800a3afb  jz      loc_18004041B
0x1800a3b01  cmp     esi, 4
0x1800a3b04  jb      loc_180040519
0x1800a3b0a  lea     rdx, [rsp+68h+arg_28]
0x1800a3b12  mov     rcx, r14
0x1800a3b15  call    IsIfxTpmWeakKeyProperty
0x1800a3b1a  mov     ebx, eax
0x1800a3b1c  test    eax, eax
0x1800a3b1e  js      loc_18004041D
0x1800a3b24  mov     eax, [rsp+68h+arg_28]
0x1800a3b2b  jmp     short loc_1800A3B89
0x1800a3b2d  mov     rax, [rsp+68h+arg_20]
0x1800a3b35  mov     dword ptr [rax], 4
0x1800a3b3b  test    rdi, rdi
0x1800a3b3e  jz      loc_18004041B
0x1800a3b44  cmp     esi, 4
0x1800a3b47  jb      loc_180040519
0x1800a3b4d  mov     rax, [rbp+20h]
0x1800a3b51  test    rax, rax
0x1800a3b54  jz      short loc_1800A3B5B
0x1800a3b56  mov     eax, [rax+10h]
0x1800a3b59  jmp     short loc_1800A3B5E
0x1800a3b5b  mov     eax, [rbp+0Ch]
0x1800a3b5e  add     eax, 7
0x1800a3b61  shr     eax, 3
0x1800a3b64  jmp     short loc_1800A3B89
0x1800a3b66  mov     rax, [rsp+68h+arg_20]
0x1800a3b6e  mov     dword ptr [rax], 4
0x1800a3b74  test    rdi, rdi
0x1800a3b77  jz      loc_18004041B
0x1800a3b7d  cmp     esi, 4
0x1800a3b80  jb      loc_180040519
0x1800a3b86  mov     eax, [rbp+0Ch]
0x1800a3b89  mov     [rdi], eax
0x1800a3b8b  jmp     loc_18004041B
```
