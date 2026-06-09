# CheckEncryptionPadding

- ea: `0x18005adc0`
- end: `0x18005afc5`
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
- `0x180040e5c`
- `0x18005adc0`
- `0x180063d34`
- `0x180068390`
- `0x180068438`
- `0x180068f00`

## string_xrefs

- `0x18005adf4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005ae99`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005af95`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x18005adc0  push    rbp
0x18005adc2  push    rbx
0x18005adc3  push    rsi
0x18005adc4  push    rdi
0x18005adc5  push    r14
0x18005adc7  push    r15
0x18005adc9  mov     rbp, rsp
0x18005adcc  sub     rsp, 68h
0x18005add0  xor     edi, edi
0x18005add2  mov     r14d, r9d
0x18005add5  mov     r15, r8
0x18005add8  mov     rsi, rdx
0x18005addb  mov     [rbp+hObject], rdi
0x18005addf  mov     dword ptr [rbp+pbOutput], edi
0x18005ade2  mov     dword ptr [rbp+var_14], edi
0x18005ade5  mov     [rbp+arg_18], edi
0x18005ade8  cmp     [rbp+arg_20], r9d
0x18005adec  jnb     short loc_18005AE16
0x18005adee  mov     r9d, 0EC7h
0x18005adf4  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005adfb  mov     ecx, 0C000000Dh
0x18005ae00  lea     rdx, aStatus; "Status"
0x18005ae07  mov     ebx, 0C000000Dh
0x18005ae0c  call    DebugTraceError
0x18005ae11  jmp     loc_18005AFB5
0x18005ae16  test    cl, 2
0x18005ae19  jz      short loc_18005AE66
0x18005ae1b  mov     eax, [rbp+arg_30]
0x18005ae1e  lea     rcx, [rbp+hObject]
0x18005ae22  mov     r8d, [rbp+arg_20]
0x18005ae26  mov     rdx, r14
0x18005ae29  mov     r9, [rbp+arg_28]
0x18005ae2d  mov     qword ptr [rsp+68h+dwFlags], rcx
0x18005ae32  mov     rcx, r15
0x18005ae35  mov     [rbp+hObject], rdi
0x18005ae39  mov     [rsp+68h+pcbResult], rax
0x18005ae3e  call    SymCryptRsaPkcs1RemoveEncryptionPadding
0x18005ae43  lea     r8, symmErrorsMap
0x18005ae4a  mov     edx, 0C000000Dh
0x18005ae4f  mov     ecx, eax
0x18005ae51  call    SymCryptMapUint32
0x18005ae56  mov     rdx, [rbp+arg_38]
0x18005ae5a  mov     ebx, eax
0x18005ae5c  mov     ecx, dword ptr [rbp+hObject]
0x18005ae5f  mov     [rdx], ecx
0x18005ae61  jmp     loc_18005AFB5
0x18005ae66  test    cl, 4
0x18005ae69  jz      loc_18005AF85
0x18005ae6f  test    rsi, rsi
0x18005ae72  jz      loc_18005AF7A
0x18005ae78  mov     rdx, [rdx]
0x18005ae7b  test    rdx, rdx
0x18005ae7e  jz      loc_18005AF7A
0x18005ae84  lea     rcx, [rbp+hObject]
0x18005ae88  call    CachedOpenAlgorithmProvider
0x18005ae8d  mov     ebx, eax
0x18005ae8f  test    eax, eax
0x18005ae91  jns     short loc_18005AEB7
0x18005ae93  mov     r9d, 0EF0h
0x18005ae99  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005aea0  lea     rdx, aStatus; "Status"
0x18005aea7  mov     ecx, eax
0x18005aea9  call    DebugTraceError
0x18005aeae  mov     rdi, [rbp+hObject]
0x18005aeb2  jmp     loc_18005AFA8
0x18005aeb7  mov     [rsp+68h+dwFlags], edi; dwFlags
0x18005aebb  lea     rax, [rbp+arg_18]
0x18005aebf  mov     rdi, [rbp+hObject]
0x18005aec3  lea     r8, [rbp+pbOutput]; pbOutput
0x18005aec7  mov     rcx, rdi; hObject
0x18005aeca  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18005aecf  mov     r9d, 4; cbOutput
0x18005aed5  lea     rdx, aObjectlength; "ObjectLength"
0x18005aedc  call    BCryptGetProperty
0x18005aee1  mov     ebx, eax
0x18005aee3  test    eax, eax
0x18005aee5  jns     short loc_18005AEF4
0x18005aee7  mov     r9d, 0EFCh
0x18005aeed  mov     ecx, eax
0x18005aeef  jmp     loc_18005AF95
0x18005aef4  lea     rax, [rbp+arg_18]
0x18005aef8  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18005af00  mov     r9d, 4; cbOutput
0x18005af06  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18005af0b  lea     r8, [rbp+var_14]; pbOutput
0x18005af0f  mov     rcx, rdi; hObject
0x18005af12  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18005af19  call    BCryptGetProperty
0x18005af1e  mov     ebx, eax
0x18005af20  test    eax, eax
0x18005af22  jns     short loc_18005AF2C
0x18005af24  mov     r9d, 0F08h
0x18005af2a  jmp     short loc_18005AEED
0x18005af2c  mov     rax, [rbp+arg_38]
0x18005af30  mov     rcx, rdi
0x18005af33  mov     r9, [rsi+8]
0x18005af37  mov     r8d, dword ptr [rbp+pbOutput]
0x18005af3b  mov     edx, dword ptr [rbp+var_14]
0x18005af3e  mov     [rsp+68h+var_20], rax
0x18005af43  mov     eax, [rbp+arg_30]
0x18005af46  mov     [rsp+68h+var_28], eax
0x18005af4a  mov     rax, [rbp+arg_28]
0x18005af4e  mov     [rsp+68h+var_30], rax
0x18005af53  mov     eax, [rsi+10h]
0x18005af56  mov     [rsp+68h+var_38], r14d
0x18005af5b  mov     qword ptr [rsp+68h+dwFlags], r15
0x18005af60  mov     dword ptr [rsp+68h+pcbResult], eax
0x18005af64  call    CheckOAEPPadding
0x18005af69  mov     ebx, eax
0x18005af6b  test    eax, eax
0x18005af6d  jns     short loc_18005AFA8
0x18005af6f  mov     r9d, 0F18h
0x18005af75  jmp     loc_18005AEED
0x18005af7a  mov     r9d, 0EE5h
0x18005af80  jmp     loc_18005ADF4
0x18005af85  mov     ebx, 0C000000Dh
0x18005af8a  mov     r9d, 0F1Fh
0x18005af90  mov     ecx, 0C000000Dh
0x18005af95  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005af9c  lea     rdx, aStatus; "Status"
0x18005afa3  call    DebugTraceError
0x18005afa8  test    rdi, rdi
0x18005afab  jz      short loc_18005AFB5
0x18005afad  mov     rcx, rdi; hAlgorithm
0x18005afb0  call    CachedCloseAlgorithmProvider
0x18005afb5  mov     eax, ebx
0x18005afb7  add     rsp, 68h
0x18005afbb  pop     r15
0x18005afbd  pop     r14
0x18005afbf  pop     rdi
0x18005afc0  pop     rsi
0x18005afc1  pop     rbx
0x18005afc2  pop     rbp
0x18005afc3  retn
```
