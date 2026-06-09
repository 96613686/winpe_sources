# CheckEncryptionPadding

- ea: `0x18005a4d0`
- end: `0x18005a6d5`
- name: `CheckEncryptionPadding`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180007b60`

## callees

- `0x180003c70`
- `0x18000743c`
- `0x1800402cc`
- `0x18005a4d0`
- `0x1800633b4`
- `0x180067990`
- `0x180067a38`
- `0x180068500`

## string_xrefs

- `0x18005a504`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005a5a9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005a6a5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall CheckEncryptionPadding(
        char a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        _DWORD *a8)
{
  BCRYPT_HANDLE v8; // rdi
  __int64 v12; // r9
  unsigned int v13; // ebx
  unsigned int v14; // eax
  int v15; // eax
  NTSTATUS Property; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-18h] BYREF
  UCHAR v21[4]; // [rsp+54h] [rbp-14h] BYREF
  BCRYPT_HANDLE hObject[2]; // [rsp+58h] [rbp-10h] BYREF
  ULONG pcbResult; // [rsp+B8h] [rbp+50h] BYREF

  v8 = 0;
  hObject[0] = 0;
  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v21 = 0;
  pcbResult = 0;
  if ( a5 < a4 )
  {
    v12 = 3783;
LABEL_3:
    v13 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v12);
    return v13;
  }
  if ( (a1 & 2) != 0 )
  {
    hObject[0] = 0;
    v14 = SymCryptRsaPkcs1RemoveEncryptionPadding(a3, a4, a5, a6, a7, (__int64)hObject);
    v13 = SymCryptMapUint32(v14, 3221225485LL, &symmErrorsMap);
    *a8 = hObject[0];
    return v13;
  }
  if ( (a1 & 4) != 0 )
  {
    if ( !a2 || !*(_QWORD *)a2 )
    {
      v12 = 3813;
      goto LABEL_3;
    }
    v15 = CachedOpenAlgorithmProvider(hObject);
    v13 = v15;
    if ( v15 < 0 )
    {
      DebugTraceError((unsigned int)v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 3824);
      v8 = hObject[0];
      goto LABEL_21;
    }
    v8 = hObject[0];
    Property = BCryptGetProperty(hObject[0], L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    v13 = Property;
    if ( Property >= 0 )
    {
      Property = BCryptGetProperty(v8, L"HashDigestLength", v21, 4u, &pcbResult, 0);
      v13 = Property;
      if ( Property >= 0 )
      {
        Property = CheckOAEPPadding(
                     v8,
                     *(unsigned int *)v21,
                     *(unsigned int *)pbOutput,
                     *(_QWORD *)(a2 + 8),
                     *(_DWORD *)(a2 + 16),
                     a3,
                     a4,
                     a6,
                     a7,
                     a8);
        v13 = Property;
        if ( Property >= 0 )
          goto LABEL_21;
        v17 = 3864;
      }
      else
      {
        v17 = 3848;
      }
    }
    else
    {
      v17 = 3836;
    }
    v18 = (unsigned int)Property;
  }
  else
  {
    v13 = -1073741811;
    v17 = 3871;
    v18 = 3221225485LL;
  }
  DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v17);
LABEL_21:
  if ( v8 )
    CachedCloseAlgorithmProvider(v8);
  return v13;
}

```

## disassembly

```asm
0x18005a4d0  push    rbp
0x18005a4d2  push    rbx
0x18005a4d3  push    rsi
0x18005a4d4  push    rdi
0x18005a4d5  push    r14
0x18005a4d7  push    r15
0x18005a4d9  mov     rbp, rsp
0x18005a4dc  sub     rsp, 68h
0x18005a4e0  xor     edi, edi
0x18005a4e2  mov     r14d, r9d
0x18005a4e5  mov     r15, r8
0x18005a4e8  mov     rsi, rdx
0x18005a4eb  mov     [rbp+hObject], rdi
0x18005a4ef  mov     dword ptr [rbp+pbOutput], edi
0x18005a4f2  mov     dword ptr [rbp+var_14], edi
0x18005a4f5  mov     [rbp+arg_18], edi
0x18005a4f8  cmp     [rbp+arg_20], r9d
0x18005a4fc  jnb     short loc_18005A526
0x18005a4fe  mov     r9d, 0EC7h
0x18005a504  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005a50b  mov     ecx, 0C000000Dh
0x18005a510  lea     rdx, aStatus; "Status"
0x18005a517  mov     ebx, 0C000000Dh
0x18005a51c  call    DebugTraceError
0x18005a521  jmp     loc_18005A6C5
0x18005a526  test    cl, 2
0x18005a529  jz      short loc_18005A576
0x18005a52b  mov     eax, [rbp+arg_30]
0x18005a52e  lea     rcx, [rbp+hObject]
0x18005a532  mov     r8d, [rbp+arg_20]
0x18005a536  mov     rdx, r14
0x18005a539  mov     r9, [rbp+arg_28]
0x18005a53d  mov     qword ptr [rsp+68h+dwFlags], rcx
0x18005a542  mov     rcx, r15
0x18005a545  mov     [rbp+hObject], rdi
0x18005a549  mov     [rsp+68h+pcbResult], rax
0x18005a54e  call    SymCryptRsaPkcs1RemoveEncryptionPadding
0x18005a553  lea     r8, symmErrorsMap
0x18005a55a  mov     edx, 0C000000Dh
0x18005a55f  mov     ecx, eax
0x18005a561  call    SymCryptMapUint32
0x18005a566  mov     rdx, [rbp+arg_38]
0x18005a56a  mov     ebx, eax
0x18005a56c  mov     ecx, dword ptr [rbp+hObject]
0x18005a56f  mov     [rdx], ecx
0x18005a571  jmp     loc_18005A6C5
0x18005a576  test    cl, 4
0x18005a579  jz      loc_18005A695
0x18005a57f  test    rsi, rsi
0x18005a582  jz      loc_18005A68A
0x18005a588  mov     rdx, [rdx]
0x18005a58b  test    rdx, rdx
0x18005a58e  jz      loc_18005A68A
0x18005a594  lea     rcx, [rbp+hObject]
0x18005a598  call    CachedOpenAlgorithmProvider
0x18005a59d  mov     ebx, eax
0x18005a59f  test    eax, eax
0x18005a5a1  jns     short loc_18005A5C7
0x18005a5a3  mov     r9d, 0EF0h
0x18005a5a9  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005a5b0  lea     rdx, aStatus; "Status"
0x18005a5b7  mov     ecx, eax
0x18005a5b9  call    DebugTraceError
0x18005a5be  mov     rdi, [rbp+hObject]
0x18005a5c2  jmp     loc_18005A6B8
0x18005a5c7  mov     [rsp+68h+dwFlags], edi; dwFlags
0x18005a5cb  lea     rax, [rbp+arg_18]
0x18005a5cf  mov     rdi, [rbp+hObject]
0x18005a5d3  lea     r8, [rbp+pbOutput]; pbOutput
0x18005a5d7  mov     rcx, rdi; hObject
0x18005a5da  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18005a5df  mov     r9d, 4; cbOutput
0x18005a5e5  lea     rdx, aObjectlength; "ObjectLength"
0x18005a5ec  call    BCryptGetProperty
0x18005a5f1  mov     ebx, eax
0x18005a5f3  test    eax, eax
0x18005a5f5  jns     short loc_18005A604
0x18005a5f7  mov     r9d, 0EFCh
0x18005a5fd  mov     ecx, eax
0x18005a5ff  jmp     loc_18005A6A5
0x18005a604  lea     rax, [rbp+arg_18]
0x18005a608  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18005a610  mov     r9d, 4; cbOutput
0x18005a616  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18005a61b  lea     r8, [rbp+var_14]; pbOutput
0x18005a61f  mov     rcx, rdi; hObject
0x18005a622  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18005a629  call    BCryptGetProperty
0x18005a62e  mov     ebx, eax
0x18005a630  test    eax, eax
0x18005a632  jns     short loc_18005A63C
0x18005a634  mov     r9d, 0F08h
0x18005a63a  jmp     short loc_18005A5FD
0x18005a63c  mov     rax, [rbp+arg_38]
0x18005a640  mov     rcx, rdi
0x18005a643  mov     r9, [rsi+8]
0x18005a647  mov     r8d, dword ptr [rbp+pbOutput]
0x18005a64b  mov     edx, dword ptr [rbp+var_14]
0x18005a64e  mov     [rsp+68h+var_20], rax
0x18005a653  mov     eax, [rbp+arg_30]
0x18005a656  mov     [rsp+68h+var_28], eax
0x18005a65a  mov     rax, [rbp+arg_28]
0x18005a65e  mov     [rsp+68h+var_30], rax
0x18005a663  mov     eax, [rsi+10h]
0x18005a666  mov     [rsp+68h+var_38], r14d
0x18005a66b  mov     qword ptr [rsp+68h+dwFlags], r15
0x18005a670  mov     dword ptr [rsp+68h+pcbResult], eax
0x18005a674  call    CheckOAEPPadding
0x18005a679  mov     ebx, eax
0x18005a67b  test    eax, eax
0x18005a67d  jns     short loc_18005A6B8
0x18005a67f  mov     r9d, 0F18h
0x18005a685  jmp     loc_18005A5FD
0x18005a68a  mov     r9d, 0EE5h
0x18005a690  jmp     loc_18005A504
0x18005a695  mov     ebx, 0C000000Dh
0x18005a69a  mov     r9d, 0F1Fh
0x18005a6a0  mov     ecx, 0C000000Dh
0x18005a6a5  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005a6ac  lea     rdx, aStatus; "Status"
0x18005a6b3  call    DebugTraceError
0x18005a6b8  test    rdi, rdi
0x18005a6bb  jz      short loc_18005A6C5
0x18005a6bd  mov     rcx, rdi; hAlgorithm
0x18005a6c0  call    CachedCloseAlgorithmProvider
0x18005a6c5  mov     eax, ebx
0x18005a6c7  add     rsp, 68h
0x18005a6cb  pop     r15
0x18005a6cd  pop     r14
0x18005a6cf  pop     rdi
0x18005a6d0  pop     rsi
0x18005a6d1  pop     rbx
0x18005a6d2  pop     rbp
0x18005a6d3  retn
```
