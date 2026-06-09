# CheckSignaturePadding

- ea: `0x180072bc4`
- end: `0x180072f31`
- name: `CheckSignaturePadding`
- size: `877`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180064330`

## callees

- `0x18000dd90`
- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x180071b30`
- `0x180071bd8`
- `0x180072958`
- `0x180072bc4`
- `0x180073188`

## string_xrefs

- `0x180072c1c`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180072c4e`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180072d4b`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180072ef5`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall CheckSignaturePadding(char a1, __int64 a2, __int64 a3, int a4, void *Buf2, size_t Size)
{
  BCRYPT_HANDLE v6; // rsi
  __int64 v7; // rdi
  __int64 v11; // r9
  unsigned int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // r9
  NTSTATUS Property; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rdx
  NTSTATUS v20; // eax
  __int64 v21; // r9
  __int64 v22; // rcx
  int v23; // eax
  size_t dwFlags; // [rsp+28h] [rbp-28h]
  size_t dwFlagsa; // [rsp+28h] [rbp-28h]
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-10h] BYREF
  UCHAR v28[4]; // [rsp+44h] [rbp-Ch] BYREF
  BCRYPT_HANDLE hObject; // [rsp+48h] [rbp-8h] BYREF
  ULONG cbOutput; // [rsp+80h] [rbp+30h] BYREF

  v6 = 0;
  v7 = 0;
  hObject = 0;
  *(_DWORD *)v28 = 0;
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
    Property = BCryptGetProperty(hObject, L"ObjectLength", v28, 4u, &cbOutput, 0);
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
                 *(unsigned int *)v28,
                 *(unsigned int *)(a2 + 8),
                 a3,
                 a4,
                 Buf2,
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
    v23 = VerifyPKCS1SigningFormat(0, 0, a3, a4, Buf2, dwFlags, 0);
    v12 = v23;
    if ( v23 < 0 )
    {
      v11 = 1653;
      v13 = (unsigned int)v23;
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
    v7 = MSCryptAlloc(cbOutput, v19);
    if ( !v7 )
    {
      v12 = -1073741801;
      v17 = 1602;
      v18 = 3221225495LL;
      goto LABEL_45;
    }
    v20 = BCryptGetProperty(v6, L"HashOIDList", (PUCHAR)v7, cbOutput, &cbOutput, 0);
    v12 = v20;
    if ( v20 < 0 )
    {
      v21 = 1614;
LABEL_21:
      v22 = (unsigned int)v20;
LABEL_22:
      DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v21);
LABEL_41:
      MSCryptFree((PVOID)v7);
      goto LABEL_46;
    }
    if ( !*(_DWORD *)v7 )
    {
      v12 = -1073741595;
      v21 = 1623;
      v22 = 3221225701LL;
      goto LABEL_22;
    }
    LODWORD(dwFlagsa) = Size;
    v20 = VerifyPKCS1SigningFormat(*(_DWORD *)v7, *(_QWORD *)(v7 + 8), a3, a4, Buf2, dwFlagsa, 1);
    v12 = v20;
    if ( v20 < 0 )
    {
      v21 = 1637;
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
0x180072bc4  mov     [rsp-28h+arg_8], rbx
0x180072bc9  mov     [rsp-28h+arg_10], rsi
0x180072bce  push    rbp
0x180072bcf  push    rdi
0x180072bd0  push    r12
0x180072bd2  push    r14
0x180072bd4  push    r15
0x180072bd6  mov     rbp, rsp
0x180072bd9  sub     rsp, 50h
0x180072bdd  xor     esi, esi
0x180072bdf  xor     edi, edi
0x180072be1  mov     [rbp+hObject], rsi
0x180072be5  mov     r15d, r9d
0x180072be8  mov     dword ptr [rbp+var_C], esi
0x180072beb  mov     r12, r8
0x180072bee  mov     dword ptr [rbp+pbOutput], esi
0x180072bf1  mov     r14, rdx
0x180072bf4  mov     [rbp+cbOutput], esi
0x180072bf7  test    cl, 2
0x180072bfa  jz      loc_180072DE1
0x180072c00  test    rdx, rdx
0x180072c03  jnz     short loc_180072C2D
0x180072c05  mov     r9d, 60Dh
0x180072c0b  mov     ebx, 0C000000Dh
0x180072c10  mov     ecx, 0C000000Dh
0x180072c15  lea     rdx, aStatus; "Status"
0x180072c1c  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180072c23  call    DebugTraceError
0x180072c28  jmp     loc_180072F15
0x180072c2d  mov     rdx, [rdx]
0x180072c30  test    rdx, rdx
0x180072c33  jz      loc_180072DAD
0x180072c39  lea     rcx, [rbp+hObject]
0x180072c3d  call    CachedOpenAlgorithmProvider
0x180072c42  mov     ebx, eax
0x180072c44  test    eax, eax
0x180072c46  jns     short loc_180072C6C
0x180072c48  mov     r9d, 61Ah
0x180072c4e  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180072c55  mov     ecx, eax
0x180072c57  lea     rdx, aStatus; "Status"
0x180072c5e  call    DebugTraceError
0x180072c63  mov     rsi, [rbp+hObject]
0x180072c67  jmp     loc_180072F08
0x180072c6c  mov     dword ptr [rsp+50h+dwFlags], esi; dwFlags
0x180072c70  lea     rax, [rbp+cbOutput]
0x180072c74  mov     rsi, [rbp+hObject]
0x180072c78  lea     r8, [rbp+pbOutput]; pbOutput
0x180072c7c  mov     rcx, rsi; hObject
0x180072c7f  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180072c84  mov     r9d, 4; cbOutput
0x180072c8a  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180072c91  call    BCryptGetProperty
0x180072c96  mov     ebx, eax
0x180072c98  test    eax, eax
0x180072c9a  jns     short loc_180072CA9
0x180072c9c  mov     r9d, 626h
0x180072ca2  mov     ecx, eax
0x180072ca4  jmp     loc_180072EF5
0x180072ca9  cmp     dword ptr [rbp+pbOutput], r15d
0x180072cad  jz      short loc_180072CBA
0x180072caf  mov     r9d, 62Ch
0x180072cb5  jmp     loc_180072EEB
0x180072cba  lea     rax, [rbp+cbOutput]
0x180072cbe  mov     dword ptr [rsp+50h+dwFlags], edi; dwFlags
0x180072cc2  xor     r9d, r9d; cbOutput
0x180072cc5  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180072cca  xor     r8d, r8d; pbOutput
0x180072ccd  lea     rdx, aHashoidlist; "HashOIDList"
0x180072cd4  mov     rcx, rsi; hObject
0x180072cd7  call    BCryptGetProperty
0x180072cdc  mov     ebx, eax
0x180072cde  test    eax, eax
0x180072ce0  jns     short loc_180072CEA
0x180072ce2  mov     r9d, 638h
0x180072ce8  jmp     short loc_180072CA2
0x180072cea  mov     ecx, [rbp+cbOutput]
0x180072ced  call    MSCryptAlloc
0x180072cf2  mov     rdi, rax
0x180072cf5  test    rax, rax
0x180072cf8  jnz     short loc_180072D0F
0x180072cfa  mov     ebx, 0C0000017h
0x180072cff  mov     r9d, 642h
0x180072d05  mov     ecx, 0C0000017h
0x180072d0a  jmp     loc_180072EF5
0x180072d0f  mov     r9d, [rbp+cbOutput]; cbOutput
0x180072d13  lea     rax, [rbp+cbOutput]
0x180072d17  mov     dword ptr [rsp+50h+dwFlags], 0; dwFlags
0x180072d1f  lea     rdx, aHashoidlist; "HashOIDList"
0x180072d26  mov     r8, rdi; pbOutput
0x180072d29  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180072d2e  mov     rcx, rsi; hObject
0x180072d31  call    BCryptGetProperty
0x180072d36  mov     ebx, eax
0x180072d38  test    eax, eax
0x180072d3a  jns     short loc_180072D5C
0x180072d3c  mov     r9d, 64Eh
0x180072d42  mov     ecx, eax
0x180072d44  lea     rdx, aStatus; "Status"
0x180072d4b  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180072d52  call    DebugTraceError
0x180072d57  jmp     loc_180072ED0
0x180072d5c  mov     ecx, [rdi]; int
0x180072d5e  test    ecx, ecx
0x180072d60  jnz     short loc_180072D74
0x180072d62  mov     ebx, 0C00000E5h
0x180072d67  mov     r9d, 657h
0x180072d6d  mov     ecx, 0C00000E5h
0x180072d72  jmp     short loc_180072D44
0x180072d74  mov     eax, dword ptr [rbp+Size]
0x180072d77  mov     r9d, r15d; int
0x180072d7a  mov     rdx, [rdi+8]; int
0x180072d7e  mov     r8, r12; int
0x180072d81  mov     [rsp+50h+var_20], 1; int
0x180072d89  mov     dword ptr [rsp+50h+dwFlags], eax; Size
0x180072d8d  mov     rax, [rbp+Buf2]
0x180072d91  mov     [rsp+50h+pcbResult], rax; Buf2
0x180072d96  call    VerifyPKCS1SigningFormat
0x180072d9b  mov     ebx, eax
0x180072d9d  test    eax, eax
0x180072d9f  jns     loc_180072EC9
0x180072da5  mov     r9d, 665h; int
0x180072dab  jmp     short loc_180072D42
0x180072dad  mov     eax, dword ptr [rbp+Size]
0x180072db0  xor     edx, edx; int
0x180072db2  mov     [rsp+50h+var_20], esi; int
0x180072db6  xor     ecx, ecx; int
0x180072db8  mov     dword ptr [rsp+50h+dwFlags], eax; Size
0x180072dbc  mov     rax, [rbp+Buf2]
0x180072dc0  mov     [rsp+50h+pcbResult], rax; Buf2
0x180072dc5  call    VerifyPKCS1SigningFormat
0x180072dca  mov     ebx, eax
0x180072dcc  test    eax, eax
0x180072dce  jns     loc_180072EC9
0x180072dd4  mov     r9d, 675h
0x180072dda  mov     ecx, eax
0x180072ddc  jmp     loc_180072C15
0x180072de1  test    cl, 8
0x180072de4  jz      loc_180072EE5
0x180072dea  test    r14, r14
0x180072ded  jz      loc_180072EDA
0x180072df3  mov     rdx, [rdx]
0x180072df6  test    rdx, rdx
0x180072df9  jz      loc_180072EDA
0x180072dff  lea     rcx, [rbp+hObject]
0x180072e03  call    CachedOpenAlgorithmProvider
0x180072e08  mov     ebx, eax
0x180072e0a  test    eax, eax
0x180072e0c  jns     short loc_180072E19
0x180072e0e  mov     r9d, 68Ch
0x180072e14  jmp     loc_180072C4E
0x180072e19  mov     dword ptr [rsp+50h+dwFlags], esi; dwFlags
0x180072e1d  lea     rax, [rbp+cbOutput]
0x180072e21  mov     rsi, [rbp+hObject]
0x180072e25  lea     r8, [rbp+var_C]; pbOutput
0x180072e29  mov     rcx, rsi; hObject
0x180072e2c  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180072e31  mov     r9d, 4; cbOutput
0x180072e37  lea     rdx, aObjectlength; "ObjectLength"
0x180072e3e  call    BCryptGetProperty
0x180072e43  mov     ebx, eax
0x180072e45  test    eax, eax
0x180072e47  jns     short loc_180072E54
0x180072e49  mov     r9d, 698h
0x180072e4f  jmp     loc_180072CA2
0x180072e54  lea     rax, [rbp+cbOutput]
0x180072e58  mov     dword ptr [rsp+50h+dwFlags], edi; dwFlags
0x180072e5c  mov     r9d, 4; cbOutput
0x180072e62  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180072e67  lea     r8, [rbp+pbOutput]; pbOutput
0x180072e6b  mov     rcx, rsi; hObject
0x180072e6e  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180072e75  call    BCryptGetProperty
0x180072e7a  mov     ebx, eax
0x180072e7c  test    eax, eax
0x180072e7e  jns     short loc_180072E8B
0x180072e80  mov     r9d, 6A4h
0x180072e86  jmp     loc_180072CA2
0x180072e8b  mov     eax, dword ptr [rbp+Size]
0x180072e8e  mov     rcx, rsi
0x180072e91  mov     r9d, [r14+8]
0x180072e95  mov     r8d, dword ptr [rbp+var_C]
0x180072e99  mov     edx, dword ptr [rbp+pbOutput]
0x180072e9c  mov     [rsp+50h+var_18], eax
0x180072ea0  mov     rax, [rbp+Buf2]
0x180072ea4  mov     qword ptr [rsp+50h+var_20], rax
0x180072ea9  mov     dword ptr [rsp+50h+dwFlags], r15d
0x180072eae  mov     [rsp+50h+pcbResult], r12
0x180072eb3  call    CheckPSSPadding
0x180072eb8  mov     ebx, eax
0x180072eba  test    eax, eax
0x180072ebc  jns     short loc_180072EC9
0x180072ebe  mov     r9d, 6B2h
0x180072ec4  jmp     loc_180072CA2
0x180072ec9  xor     ebx, ebx
0x180072ecb  test    rdi, rdi
0x180072ece  jz      short loc_180072F08
0x180072ed0  mov     rcx, rdi; P
0x180072ed3  call    MSCryptFree
0x180072ed8  jmp     short loc_180072F08
0x180072eda  mov     r9d, 681h
0x180072ee0  jmp     loc_180072C0B
0x180072ee5  mov     r9d, 6B9h
0x180072eeb  mov     ecx, 0C000000Dh
0x180072ef0  mov     ebx, 0C000000Dh
0x180072ef5  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180072efc  lea     rdx, aStatus; "Status"
0x180072f03  call    DebugTraceError
0x180072f08  test    rsi, rsi
0x180072f0b  jz      short loc_180072F15
0x180072f0d  mov     rcx, rsi; hAlgorithm
0x180072f10  call    CachedCloseAlgorithmProvider
0x180072f15  lea     r11, [rsp+50h+var_s0]
0x180072f1a  mov     eax, ebx
0x180072f1c  mov     rbx, [r11+38h]
0x180072f20  mov     rsi, [r11+40h]
0x180072f24  mov     rsp, r11
0x180072f27  pop     r15
0x180072f29  pop     r14
0x180072f2b  pop     r12
0x180072f2d  pop     rdi
0x180072f2e  pop     rbp
0x180072f2f  retn
```
