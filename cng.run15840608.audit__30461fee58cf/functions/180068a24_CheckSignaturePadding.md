# CheckSignaturePadding

- ea: `0x180068a24`
- end: `0x180068d91`
- name: `CheckSignaturePadding`
- size: `877`
- prototype: `__int64 __fastcall(char, __int64, void *, unsigned int, void *Buf2, size_t Size)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18005a160`

## callees

- `0x180003c70`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180067990`
- `0x180067a38`
- `0x1800687b8`
- `0x180068a24`
- `0x180068fe8`

## string_xrefs

- `0x180068a7c`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180068aae`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180068bab`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180068d55`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall CheckSignaturePadding(char a1, __int64 a2, void *a3, unsigned int a4, void *Buf2, size_t Size)
{
  BCRYPT_HANDLE v6; // rsi
  __int64 v7; // rdi
  __int64 v11; // r9
  unsigned int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // r9
  int Property; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  NTSTATUS v19; // eax
  __int64 v20; // r9
  __int64 v21; // rcx
  int v22; // eax
  size_t dwFlags; // [rsp+28h] [rbp-28h]
  size_t dwFlagsa; // [rsp+28h] [rbp-28h]
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-10h] BYREF
  UCHAR v27[4]; // [rsp+44h] [rbp-Ch] BYREF
  BCRYPT_HANDLE hObject; // [rsp+48h] [rbp-8h] BYREF
  ULONG cbOutput; // [rsp+80h] [rbp+30h] BYREF

  v6 = 0;
  v7 = 0;
  hObject = 0;
  *(_DWORD *)v27 = 0;
  *(_DWORD *)pbOutput = 0;
  cbOutput = 0;
  if ( (a1 & 2) == 0 )
  {
    if ( (a1 & 8) == 0 )
    {
      v17 = 1721;
      goto LABEL_44;
    }
    if ( !a2 || !*(_QWORD *)a2 )
    {
      v11 = 1665;
      goto LABEL_4;
    }
    v14 = CachedOpenAlgorithmProvider(&hObject);
    v12 = v14;
    if ( v14 < 0 )
    {
      v15 = 1676;
      goto LABEL_9;
    }
    v6 = hObject;
    Property = BCryptGetProperty(hObject, L"ObjectLength", v27, 4u, &cbOutput, 0);
    v12 = Property;
    if ( Property < 0 )
    {
      v17 = 1688;
      goto LABEL_12;
    }
    Property = BCryptGetProperty(v6, L"HashDigestLength", pbOutput, 4u, &cbOutput, 0);
    v12 = Property;
    if ( Property < 0 )
    {
      v17 = 1700;
      goto LABEL_12;
    }
    Property = CheckPSSPadding(
                 v6,
                 *(unsigned int *)pbOutput,
                 *(unsigned int *)v27,
                 *(_DWORD *)(a2 + 8),
                 a3,
                 a4,
                 (PUCHAR)Buf2,
                 Size);
    v12 = Property;
    if ( Property < 0 )
    {
      v17 = 1714;
      goto LABEL_12;
    }
    goto LABEL_40;
  }
  if ( !a2 )
  {
    v11 = 1549;
LABEL_4:
    v12 = -1073741811;
    v13 = 3221225485LL;
LABEL_5:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v11);
    return v12;
  }
  if ( !*(_QWORD *)a2 )
  {
    LODWORD(dwFlags) = Size;
    v22 = VerifyPKCS1SigningFormat(0, 0, (int)a3, a4, Buf2, dwFlags, 0);
    v12 = v22;
    if ( v22 < 0 )
    {
      v11 = 1653;
      v13 = (unsigned int)v22;
      goto LABEL_5;
    }
    goto LABEL_40;
  }
  v14 = CachedOpenAlgorithmProvider(&hObject);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 1562;
LABEL_9:
    DebugTraceError((unsigned int)v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v15);
    v6 = hObject;
    goto LABEL_46;
  }
  v6 = hObject;
  Property = BCryptGetProperty(hObject, L"HashDigestLength", pbOutput, 4u, &cbOutput, 0);
  v12 = Property;
  if ( Property >= 0 )
  {
    if ( *(_DWORD *)pbOutput != a4 )
    {
      v17 = 1580;
LABEL_44:
      v18 = 3221225485LL;
      v12 = -1073741811;
      goto LABEL_45;
    }
    Property = BCryptGetProperty(v6, L"HashOIDList", 0, 0, &cbOutput, 0);
    v12 = Property;
    if ( Property < 0 )
    {
      v17 = 1592;
      goto LABEL_12;
    }
    v7 = MSCryptAlloc(cbOutput);
    if ( !v7 )
    {
      v12 = -1073741801;
      v17 = 1602;
      v18 = 3221225495LL;
      goto LABEL_45;
    }
    v19 = BCryptGetProperty(v6, L"HashOIDList", (PUCHAR)v7, cbOutput, &cbOutput, 0);
    v12 = v19;
    if ( v19 < 0 )
    {
      v20 = 1614;
LABEL_21:
      v21 = (unsigned int)v19;
LABEL_22:
      DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v20);
LABEL_41:
      MSCryptFree((PVOID)v7);
      goto LABEL_46;
    }
    if ( !*(_DWORD *)v7 )
    {
      v12 = -1073741595;
      v20 = 1623;
      v21 = 3221225701LL;
      goto LABEL_22;
    }
    LODWORD(dwFlagsa) = Size;
    v19 = VerifyPKCS1SigningFormat(*(_DWORD *)v7, *(_QWORD *)(v7 + 8), (int)a3, a4, Buf2, dwFlagsa, 1);
    v12 = v19;
    if ( v19 < 0 )
    {
      v20 = 1637;
      goto LABEL_21;
    }
LABEL_40:
    v12 = 0;
    if ( !v7 )
      goto LABEL_46;
    goto LABEL_41;
  }
  v17 = 1574;
LABEL_12:
  v18 = (unsigned int)Property;
LABEL_45:
  DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v17);
LABEL_46:
  if ( v6 )
    CachedCloseAlgorithmProvider(v6);
  return v12;
}

```

## disassembly

```asm
0x180068a24  mov     [rsp-28h+arg_8], rbx
0x180068a29  mov     [rsp-28h+arg_10], rsi
0x180068a2e  push    rbp
0x180068a2f  push    rdi
0x180068a30  push    r12
0x180068a32  push    r14
0x180068a34  push    r15
0x180068a36  mov     rbp, rsp
0x180068a39  sub     rsp, 50h
0x180068a3d  xor     esi, esi
0x180068a3f  xor     edi, edi
0x180068a41  mov     [rbp+hObject], rsi
0x180068a45  mov     r15d, r9d
0x180068a48  mov     dword ptr [rbp+var_C], esi
0x180068a4b  mov     r12, r8
0x180068a4e  mov     dword ptr [rbp+pbOutput], esi
0x180068a51  mov     r14, rdx
0x180068a54  mov     [rbp+cbOutput], esi
0x180068a57  test    cl, 2
0x180068a5a  jz      loc_180068C41
0x180068a60  test    rdx, rdx
0x180068a63  jnz     short loc_180068A8D
0x180068a65  mov     r9d, 60Dh
0x180068a6b  mov     ebx, 0C000000Dh
0x180068a70  mov     ecx, 0C000000Dh
0x180068a75  lea     rdx, aStatus; "Status"
0x180068a7c  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068a83  call    DebugTraceError
0x180068a88  jmp     loc_180068D75
0x180068a8d  mov     rdx, [rdx]
0x180068a90  test    rdx, rdx
0x180068a93  jz      loc_180068C0D
0x180068a99  lea     rcx, [rbp+hObject]
0x180068a9d  call    CachedOpenAlgorithmProvider
0x180068aa2  mov     ebx, eax
0x180068aa4  test    eax, eax
0x180068aa6  jns     short loc_180068ACC
0x180068aa8  mov     r9d, 61Ah
0x180068aae  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068ab5  mov     ecx, eax
0x180068ab7  lea     rdx, aStatus; "Status"
0x180068abe  call    DebugTraceError
0x180068ac3  mov     rsi, [rbp+hObject]
0x180068ac7  jmp     loc_180068D68
0x180068acc  mov     dword ptr [rsp+50h+dwFlags], esi; dwFlags
0x180068ad0  lea     rax, [rbp+cbOutput]
0x180068ad4  mov     rsi, [rbp+hObject]
0x180068ad8  lea     r8, [rbp+pbOutput]; pbOutput
0x180068adc  mov     rcx, rsi; hObject
0x180068adf  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180068ae4  mov     r9d, 4; cbOutput
0x180068aea  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180068af1  call    BCryptGetProperty
0x180068af6  mov     ebx, eax
0x180068af8  test    eax, eax
0x180068afa  jns     short loc_180068B09
0x180068afc  mov     r9d, 626h
0x180068b02  mov     ecx, eax
0x180068b04  jmp     loc_180068D55
0x180068b09  cmp     dword ptr [rbp+pbOutput], r15d
0x180068b0d  jz      short loc_180068B1A
0x180068b0f  mov     r9d, 62Ch
0x180068b15  jmp     loc_180068D4B
0x180068b1a  lea     rax, [rbp+cbOutput]
0x180068b1e  mov     dword ptr [rsp+50h+dwFlags], edi; dwFlags
0x180068b22  xor     r9d, r9d; cbOutput
0x180068b25  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180068b2a  xor     r8d, r8d; pbOutput
0x180068b2d  lea     rdx, aHashoidlist; "HashOIDList"
0x180068b34  mov     rcx, rsi; hObject
0x180068b37  call    BCryptGetProperty
0x180068b3c  mov     ebx, eax
0x180068b3e  test    eax, eax
0x180068b40  jns     short loc_180068B4A
0x180068b42  mov     r9d, 638h
0x180068b48  jmp     short loc_180068B02
0x180068b4a  mov     ecx, [rbp+cbOutput]
0x180068b4d  call    MSCryptAlloc
0x180068b52  mov     rdi, rax
0x180068b55  test    rax, rax
0x180068b58  jnz     short loc_180068B6F
0x180068b5a  mov     ebx, 0C0000017h
0x180068b5f  mov     r9d, 642h
0x180068b65  mov     ecx, 0C0000017h
0x180068b6a  jmp     loc_180068D55
0x180068b6f  mov     r9d, [rbp+cbOutput]; cbOutput
0x180068b73  lea     rax, [rbp+cbOutput]
0x180068b77  mov     dword ptr [rsp+50h+dwFlags], 0; dwFlags
0x180068b7f  lea     rdx, aHashoidlist; "HashOIDList"
0x180068b86  mov     r8, rdi; pbOutput
0x180068b89  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180068b8e  mov     rcx, rsi; hObject
0x180068b91  call    BCryptGetProperty
0x180068b96  mov     ebx, eax
0x180068b98  test    eax, eax
0x180068b9a  jns     short loc_180068BBC
0x180068b9c  mov     r9d, 64Eh
0x180068ba2  mov     ecx, eax
0x180068ba4  lea     rdx, aStatus; "Status"
0x180068bab  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068bb2  call    DebugTraceError
0x180068bb7  jmp     loc_180068D30
0x180068bbc  mov     ecx, [rdi]; int
0x180068bbe  test    ecx, ecx
0x180068bc0  jnz     short loc_180068BD4
0x180068bc2  mov     ebx, 0C00000E5h
0x180068bc7  mov     r9d, 657h
0x180068bcd  mov     ecx, 0C00000E5h
0x180068bd2  jmp     short loc_180068BA4
0x180068bd4  mov     eax, dword ptr [rbp+Size]
0x180068bd7  mov     r9d, r15d; int
0x180068bda  mov     rdx, [rdi+8]; int
0x180068bde  mov     r8, r12; int
0x180068be1  mov     [rsp+50h+var_20], 1; int
0x180068be9  mov     dword ptr [rsp+50h+dwFlags], eax; Size
0x180068bed  mov     rax, [rbp+Buf2]
0x180068bf1  mov     [rsp+50h+pcbResult], rax; Buf2
0x180068bf6  call    VerifyPKCS1SigningFormat
0x180068bfb  mov     ebx, eax
0x180068bfd  test    eax, eax
0x180068bff  jns     loc_180068D29
0x180068c05  mov     r9d, 665h; int
0x180068c0b  jmp     short loc_180068BA2
0x180068c0d  mov     eax, dword ptr [rbp+Size]
0x180068c10  xor     edx, edx; int
0x180068c12  mov     [rsp+50h+var_20], esi; int
0x180068c16  xor     ecx, ecx; int
0x180068c18  mov     dword ptr [rsp+50h+dwFlags], eax; Size
0x180068c1c  mov     rax, [rbp+Buf2]
0x180068c20  mov     [rsp+50h+pcbResult], rax; Buf2
0x180068c25  call    VerifyPKCS1SigningFormat
0x180068c2a  mov     ebx, eax
0x180068c2c  test    eax, eax
0x180068c2e  jns     loc_180068D29
0x180068c34  mov     r9d, 675h
0x180068c3a  mov     ecx, eax
0x180068c3c  jmp     loc_180068A75
0x180068c41  test    cl, 8
0x180068c44  jz      loc_180068D45
0x180068c4a  test    r14, r14
0x180068c4d  jz      loc_180068D3A
0x180068c53  mov     rdx, [rdx]
0x180068c56  test    rdx, rdx
0x180068c59  jz      loc_180068D3A
0x180068c5f  lea     rcx, [rbp+hObject]
0x180068c63  call    CachedOpenAlgorithmProvider
0x180068c68  mov     ebx, eax
0x180068c6a  test    eax, eax
0x180068c6c  jns     short loc_180068C79
0x180068c6e  mov     r9d, 68Ch
0x180068c74  jmp     loc_180068AAE
0x180068c79  mov     dword ptr [rsp+50h+dwFlags], esi; dwFlags
0x180068c7d  lea     rax, [rbp+cbOutput]
0x180068c81  mov     rsi, [rbp+hObject]
0x180068c85  lea     r8, [rbp+var_C]; pbOutput
0x180068c89  mov     rcx, rsi; hObject
0x180068c8c  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180068c91  mov     r9d, 4; cbOutput
0x180068c97  lea     rdx, aObjectlength; "ObjectLength"
0x180068c9e  call    BCryptGetProperty
0x180068ca3  mov     ebx, eax
0x180068ca5  test    eax, eax
0x180068ca7  jns     short loc_180068CB4
0x180068ca9  mov     r9d, 698h
0x180068caf  jmp     loc_180068B02
0x180068cb4  lea     rax, [rbp+cbOutput]
0x180068cb8  mov     dword ptr [rsp+50h+dwFlags], edi; dwFlags
0x180068cbc  mov     r9d, 4; cbOutput
0x180068cc2  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180068cc7  lea     r8, [rbp+pbOutput]; pbOutput
0x180068ccb  mov     rcx, rsi; hObject
0x180068cce  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180068cd5  call    BCryptGetProperty
0x180068cda  mov     ebx, eax
0x180068cdc  test    eax, eax
0x180068cde  jns     short loc_180068CEB
0x180068ce0  mov     r9d, 6A4h
0x180068ce6  jmp     loc_180068B02
0x180068ceb  mov     eax, dword ptr [rbp+Size]
0x180068cee  mov     rcx, rsi
0x180068cf1  mov     r9d, [r14+8]
0x180068cf5  mov     r8d, dword ptr [rbp+var_C]
0x180068cf9  mov     edx, dword ptr [rbp+pbOutput]
0x180068cfc  mov     [rsp+50h+var_18], eax
0x180068d00  mov     rax, [rbp+Buf2]
0x180068d04  mov     qword ptr [rsp+50h+var_20], rax
0x180068d09  mov     dword ptr [rsp+50h+dwFlags], r15d
0x180068d0e  mov     [rsp+50h+pcbResult], r12
0x180068d13  call    CheckPSSPadding
0x180068d18  mov     ebx, eax
0x180068d1a  test    eax, eax
0x180068d1c  jns     short loc_180068D29
0x180068d1e  mov     r9d, 6B2h
0x180068d24  jmp     loc_180068B02
0x180068d29  xor     ebx, ebx
0x180068d2b  test    rdi, rdi
0x180068d2e  jz      short loc_180068D68
0x180068d30  mov     rcx, rdi; P
0x180068d33  call    MSCryptFree
0x180068d38  jmp     short loc_180068D68
0x180068d3a  mov     r9d, 681h
0x180068d40  jmp     loc_180068A6B
0x180068d45  mov     r9d, 6B9h
0x180068d4b  mov     ecx, 0C000000Dh
0x180068d50  mov     ebx, 0C000000Dh
0x180068d55  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068d5c  lea     rdx, aStatus; "Status"
0x180068d63  call    DebugTraceError
0x180068d68  test    rsi, rsi
0x180068d6b  jz      short loc_180068D75
0x180068d6d  mov     rcx, rsi; hAlgorithm
0x180068d70  call    CachedCloseAlgorithmProvider
0x180068d75  lea     r11, [rsp+50h+var_s0]
0x180068d7a  mov     eax, ebx
0x180068d7c  mov     rbx, [r11+38h]
0x180068d80  mov     rsi, [r11+40h]
0x180068d84  mov     rsp, r11
0x180068d87  pop     r15
0x180068d89  pop     r14
0x180068d8b  pop     r12
0x180068d8d  pop     rdi
0x180068d8e  pop     rbp
0x180068d8f  retn
```
