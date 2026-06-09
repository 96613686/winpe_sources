# BCryptDeriveKeyCapi

- ea: `0x180058960`
- end: `0x180058d58`
- name: `BCryptDeriveKeyCapi`
- size: `1016`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash, BCRYPT_ALG_HANDLE hTargetAlg, PUCHAR pbDerivedKey, ULONG cbDerivedKey, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180001930`
- `0x1800034b0`
- `0x180003c70`
- `0x180003f70`
- `0x180006470`
- `0x1800064e0`
- `0x18000743c`
- `0x1800080f0`
- `0x180058960`
- `0x18005c3c0`
- `0x18009f616`
- `0x18009f650`
- `0x18009f780`
- `0x18009fa80`

## string_xrefs

- `0x180058a9a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180058b0b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180058d04`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDeriveKeyCapi(
        BCRYPT_HASH_HANDLE hHash,
        BCRYPT_ALG_HANDLE hTargetAlg,
        PUCHAR pbDerivedKey,
        ULONG cbDerivedKey,
        ULONG dwFlags)
{
  size_t v5; // rsi
  NTSTATUS Property; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  NTSTATUS v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rcx
  UCHAR *v17; // rax
  UCHAR *v18; // rdi
  NTSTATUS v19; // eax
  __int64 v20; // r9
  unsigned int v21; // r14d
  BOOL v22; // ebx
  NTSTATUS v23; // eax
  __int64 i; // r8
  UCHAR v25; // al
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-BCh] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-B8h] BYREF
  BCRYPT_HASH_HANDLE hHasha; // [rsp+50h] [rbp-B0h] BYREF
  UCHAR v31[8]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v32; // [rsp+68h] [rbp-98h] BYREF
  UCHAR pbInput[64]; // [rsp+70h] [rbp-90h] BYREF
  UCHAR v34[64]; // [rsp+B0h] [rbp-50h] BYREF

  v5 = cbDerivedKey;
  *(_DWORD *)pbOutput = 0;
  *(_QWORD *)v31 = 0;
  phHash = 0;
  hHasha = 0;
  pcbResult = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      41,
      pbDerivedKey,
      hHash,
      hTargetAlg,
      pbDerivedKey,
      cbDerivedKey,
      dwFlags);
  if ( dwFlags || !pbDerivedKey || !(_DWORD)v5 )
  {
    v14 = 7138;
    goto LABEL_45;
  }
  Property = BCryptGetProperty(hHash, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  v13 = Property;
  if ( Property >= 0 )
  {
    v16 = (unsigned int)(2 * *(_DWORD *)pbOutput);
    if ( (unsigned int)v16 >= (unsigned int)v5 && *(_DWORD *)pbOutput <= 0x40u )
    {
      v17 = (UCHAR *)MSCryptAlloc(v16, v10, v11, v12);
      v18 = v17;
      if ( !v17 )
      {
        v13 = -1073741801;
        v14 = 7183;
        v15 = 3221225495LL;
        goto LABEL_46;
      }
      v19 = BCryptFinishHash(hHash, v17, *(ULONG *)pbOutput, 0);
      v13 = v19;
      if ( v19 < 0 )
      {
        v20 = 7193;
LABEL_15:
        DebugTraceError((unsigned int)v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v20);
LABEL_42:
        MSCryptFree(v18);
        goto LABEL_47;
      }
      v21 = *(_DWORD *)pbOutput;
      v22 = *(_DWORD *)pbOutput < (unsigned int)v5;
      if ( hTargetAlg && (_DWORD)v5 == 16 && *(_DWORD *)pbOutput < 0x20u )
      {
        v23 = BCryptGetProperty(hTargetAlg, L"AlgorithmName", (PUCHAR)&v32, 8u, &pcbResult, 0);
        if ( v23 >= 0 )
        {
          if ( !wcscmp_0(&v32, L"AES") )
            v22 = 1;
        }
        else
        {
          DebugTraceError((unsigned int)v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 7221);
        }
        v21 = *(_DWORD *)pbOutput;
      }
      if ( v22 )
      {
        memset(pbInput, 54, sizeof(pbInput));
        memset(v34, 92, sizeof(v34));
        for ( i = 0; (unsigned int)i < v21; i = (unsigned int)(i + 1) )
        {
          v25 = v18[i];
          pbInput[i] ^= v25;
          v34[i] ^= v25;
        }
        v19 = BCryptGetProperty(hHash, L"ProviderHandle", v31, 8u, &pcbResult, 0);
        v13 = v19;
        if ( v19 < 0 )
        {
          v20 = 7260;
          goto LABEL_15;
        }
        v19 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)v31, &phHash, 0, 0, 0, 0, 0);
        v13 = v19;
        if ( v19 < 0 )
        {
          v20 = 7273;
          goto LABEL_15;
        }
        v19 = BCryptHashData(phHash, pbInput, 0x40u, 0);
        v13 = v19;
        if ( v19 < 0 )
        {
          v20 = 7283;
          goto LABEL_15;
        }
        v19 = BCryptFinishHash(phHash, v18, *(ULONG *)pbOutput, 0);
        v13 = v19;
        if ( v19 < 0 )
        {
          v20 = 7293;
          goto LABEL_15;
        }
        v19 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)v31, &hHasha, 0, 0, 0, 0, 0);
        v13 = v19;
        if ( v19 < 0 )
        {
          v20 = 7306;
          goto LABEL_15;
        }
        v19 = BCryptHashData(hHasha, v34, 0x40u, 0);
        v13 = v19;
        if ( v19 < 0 )
        {
          v20 = 7316;
          goto LABEL_15;
        }
        v19 = BCryptFinishHash(hHasha, &v18[*(unsigned int *)pbOutput], *(ULONG *)pbOutput, 0);
        v13 = v19;
        if ( v19 < 0 )
        {
          v20 = 7326;
          goto LABEL_15;
        }
      }
      memmove(pbDerivedKey, v18, v5);
      v13 = 0;
      goto LABEL_42;
    }
    v14 = 7167;
LABEL_45:
    v15 = 3221225485LL;
    v13 = -1073741811;
    goto LABEL_46;
  }
  v14 = 7160;
  v15 = (unsigned int)Property;
LABEL_46:
  DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v14);
LABEL_47:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( hHasha )
    BCryptDestroyHash(hHasha);
  return v13;
}

```

## disassembly

```asm
0x180058960  push    rbp
0x180058962  push    rbx
0x180058963  push    rsi
0x180058964  push    rdi
0x180058965  push    r12
0x180058967  push    r13
0x180058969  push    r14
0x18005896b  push    r15
0x18005896d  lea     rbp, [rsp-8]
0x180058972  sub     rsp, 108h
0x180058979  mov     rax, cs:__security_cookie
0x180058980  xor     rax, rsp
0x180058983  mov     [rbp+40h+var_50], rax
0x180058987  xor     r14d, r14d
0x18005898a  mov     esi, r9d
0x18005898d  mov     dword ptr [rsp+140h+pbOutput], r14d
0x180058992  mov     r13, r8
0x180058995  mov     qword ptr [rsp+140h+var_E8], r14
0x18005899a  mov     r12, rdx
0x18005899d  mov     [rsp+140h+phHash], r14
0x1800589a2  mov     r15, rcx
0x1800589a5  mov     [rsp+140h+hHash], r14
0x1800589aa  mov     [rsp+140h+var_FC], r14d
0x1800589af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800589b6  lea     rax, WPP_GLOBAL_Control
0x1800589bd  mov     ebx, [rbp+40h+dwFlags]
0x1800589c0  cmp     rcx, rax
0x1800589c3  jz      short loc_1800589EE
0x1800589c5  mov     eax, [rcx+2Ch]
0x1800589c8  test    al, 4
0x1800589ca  jz      short loc_1800589EE
0x1800589cc  mov     rcx, [rcx+18h]
0x1800589d0  lea     edx, [r14+29h]
0x1800589d4  mov     [rsp+140h+var_108], ebx
0x1800589d8  mov     r9, r15
0x1800589db  mov     [rsp+140h+var_110], esi
0x1800589df  mov     qword ptr [rsp+140h+cbSecret], r8
0x1800589e4  mov     [rsp+140h+pcbResult], r12
0x1800589e9  call    WPP_SF_qqqdD
0x1800589ee  test    ebx, ebx
0x1800589f0  jnz     loc_180058CF4
0x1800589f6  test    r13, r13
0x1800589f9  jz      loc_180058CF4
0x1800589ff  test    esi, esi
0x180058a01  jz      loc_180058CF4
0x180058a07  lea     rax, [rsp+140h+var_FC]
0x180058a0c  mov     [rsp+140h+cbSecret], r14d; dwFlags
0x180058a11  lea     r9d, [rbx+4]; cbOutput
0x180058a15  mov     [rsp+140h+pcbResult], rax; pcbResult
0x180058a1a  lea     r8, [rsp+140h+pbOutput]; pbOutput
0x180058a1f  mov     rcx, r15; hObject
0x180058a22  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180058a29  call    BCryptGetProperty
0x180058a2e  mov     ebx, eax
0x180058a30  test    eax, eax
0x180058a32  jns     short loc_180058A41
0x180058a34  mov     r9d, 1BF8h
0x180058a3a  mov     ecx, eax
0x180058a3c  jmp     loc_180058D04
0x180058a41  mov     eax, dword ptr [rsp+140h+pbOutput]
0x180058a45  lea     ecx, [rax+rax]
0x180058a48  cmp     ecx, esi
0x180058a4a  jb      loc_180058CEC
0x180058a50  cmp     eax, 40h ; '@'
0x180058a53  ja      loc_180058CEC
0x180058a59  call    MSCryptAlloc
0x180058a5e  mov     rdi, rax
0x180058a61  test    rax, rax
0x180058a64  jnz     short loc_180058A7B
0x180058a66  mov     ebx, 0C0000017h
0x180058a6b  mov     r9d, 1C0Fh
0x180058a71  mov     ecx, 0C0000017h
0x180058a76  jmp     loc_180058D04
0x180058a7b  mov     r8d, dword ptr [rsp+140h+pbOutput]; cbOutput
0x180058a80  xor     r9d, r9d; dwFlags
0x180058a83  mov     rdx, rdi; pbOutput
0x180058a86  mov     rcx, r15; hHash
0x180058a89  call    BCryptFinishHash
0x180058a8e  mov     ebx, eax
0x180058a90  test    eax, eax
0x180058a92  jns     short loc_180058AB4
0x180058a94  mov     r9d, 1C19h
0x180058a9a  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058aa1  mov     ecx, eax
0x180058aa3  lea     rdx, aStatus; "Status"
0x180058aaa  call    DebugTraceError
0x180058aaf  jmp     loc_180058CE2
0x180058ab4  mov     ebx, r14d
0x180058ab7  mov     eax, 1
0x180058abc  mov     r14d, dword ptr [rsp+140h+pbOutput]
0x180058ac1  cmp     r14d, esi
0x180058ac4  cmovb   ebx, eax
0x180058ac7  test    r12, r12
0x180058aca  jz      short loc_180058B42
0x180058acc  cmp     esi, 10h
0x180058acf  jnz     short loc_180058B42
0x180058ad1  cmp     r14d, 20h ; ' '
0x180058ad5  jnb     short loc_180058B42
0x180058ad7  lea     rax, [rsp+140h+var_FC]
0x180058adc  mov     [rsp+140h+cbSecret], 0; dwFlags
0x180058ae4  lea     r9d, [rsi-8]; cbOutput
0x180058ae8  mov     [rsp+140h+pcbResult], rax; pcbResult
0x180058aed  lea     r8, [rsp+140h+var_D8]; pbOutput
0x180058af2  mov     rcx, r12; hObject
0x180058af5  lea     rdx, aAlgorithmname; "AlgorithmName"
0x180058afc  call    BCryptGetProperty
0x180058b01  test    eax, eax
0x180058b03  jns     short loc_180058B22
0x180058b05  mov     r9d, 1C35h
0x180058b0b  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058b12  lea     rdx, aStatus; "Status"
0x180058b19  mov     ecx, eax
0x180058b1b  call    DebugTraceError
0x180058b20  jmp     short loc_180058B3D
0x180058b22  lea     rdx, aAes; "AES"
0x180058b29  lea     rcx, [rsp+140h+var_D8]; Str1
0x180058b2e  call    wcscmp_0
0x180058b33  test    eax, eax
0x180058b35  mov     eax, 1
0x180058b3a  cmovz   ebx, eax
0x180058b3d  mov     r14d, dword ptr [rsp+140h+pbOutput]
0x180058b42  test    ebx, ebx
0x180058b44  jz      loc_180058CCE
0x180058b4a  mov     r12d, 40h ; '@'
0x180058b50  lea     rcx, [rsp+140h+pbInput]; void *
0x180058b55  mov     r8d, r12d; Size
0x180058b58  lea     edx, [r12-0Ah]; Val
0x180058b5d  call    memset
0x180058b62  mov     r8d, r12d; Size
0x180058b65  lea     edx, [r12+1Ch]; Val
0x180058b6a  lea     rcx, [rbp+40h+var_90]; void *
0x180058b6e  call    memset
0x180058b73  xor     r8d, r8d
0x180058b76  test    r14d, r14d
0x180058b79  jz      short loc_180058B91
0x180058b7b  mov     al, [r8+rdi]
0x180058b7f  xor     [rsp+r8+140h+pbInput], al
0x180058b84  xor     [rbp+r8+40h+var_90], al
0x180058b89  inc     r8d
0x180058b8c  cmp     r8d, r14d
0x180058b8f  jb      short loc_180058B7B
0x180058b91  xor     r14d, r14d
0x180058b94  lea     rax, [rsp+140h+var_FC]
0x180058b99  mov     [rsp+140h+cbSecret], r14d; dwFlags
0x180058b9e  lea     r8, [rsp+140h+var_E8]; pbOutput
0x180058ba3  lea     rdx, aProviderhandle; "ProviderHandle"
0x180058baa  mov     [rsp+140h+pcbResult], rax; pcbResult
0x180058baf  mov     rcx, r15; hObject
0x180058bb2  lea     r9d, [r14+8]; cbOutput
0x180058bb6  call    BCryptGetProperty
0x180058bbb  mov     ebx, eax
0x180058bbd  test    eax, eax
0x180058bbf  jns     short loc_180058BCC
0x180058bc1  mov     r9d, 1C5Ch
0x180058bc7  jmp     loc_180058A9A
0x180058bcc  mov     rcx, qword ptr [rsp+140h+var_E8]; hAlgorithm
0x180058bd1  lea     rdx, [rsp+140h+phHash]; phHash
0x180058bd6  mov     [rsp+140h+var_110], r14d; dwFlags
0x180058bdb  xor     r9d, r9d; cbHashObject
0x180058bde  mov     [rsp+140h+cbSecret], r14d; cbSecret
0x180058be3  xor     r8d, r8d; pbHashObject
0x180058be6  mov     [rsp+140h+pcbResult], r14; pbSecret
0x180058beb  call    BCryptCreateHash
0x180058bf0  mov     ebx, eax
0x180058bf2  test    eax, eax
0x180058bf4  jns     short loc_180058C01
0x180058bf6  mov     r9d, 1C69h
0x180058bfc  jmp     loc_180058A9A
0x180058c01  mov     rcx, [rsp+140h+phHash]; hHash
0x180058c06  lea     rdx, [rsp+140h+pbInput]; pbInput
0x180058c0b  xor     r9d, r9d; dwFlags
0x180058c0e  mov     r8d, r12d; cbInput
0x180058c11  call    BCryptHashData
0x180058c16  mov     ebx, eax
0x180058c18  test    eax, eax
0x180058c1a  jns     short loc_180058C27
0x180058c1c  mov     r9d, 1C73h
0x180058c22  jmp     loc_180058A9A
0x180058c27  mov     r8d, dword ptr [rsp+140h+pbOutput]; cbOutput
0x180058c2c  xor     r9d, r9d; dwFlags
0x180058c2f  mov     rcx, [rsp+140h+phHash]; hHash
0x180058c34  mov     rdx, rdi; pbOutput
0x180058c37  call    BCryptFinishHash
0x180058c3c  mov     ebx, eax
0x180058c3e  test    eax, eax
0x180058c40  jns     short loc_180058C4D
0x180058c42  mov     r9d, 1C7Dh
0x180058c48  jmp     loc_180058A9A
0x180058c4d  mov     rcx, qword ptr [rsp+140h+var_E8]; hAlgorithm
0x180058c52  lea     rdx, [rsp+140h+hHash]; phHash
0x180058c57  mov     [rsp+140h+var_110], r14d; dwFlags
0x180058c5c  xor     r9d, r9d; cbHashObject
0x180058c5f  mov     [rsp+140h+cbSecret], r14d; cbSecret
0x180058c64  xor     r8d, r8d; pbHashObject
0x180058c67  mov     [rsp+140h+pcbResult], r14; pbSecret
0x180058c6c  call    BCryptCreateHash
0x180058c71  mov     ebx, eax
0x180058c73  test    eax, eax
0x180058c75  jns     short loc_180058C82
0x180058c77  mov     r9d, 1C8Ah
0x180058c7d  jmp     loc_180058A9A
0x180058c82  mov     rcx, [rsp+140h+hHash]; hHash
0x180058c87  lea     rdx, [rbp+40h+var_90]; pbInput
0x180058c8b  xor     r9d, r9d; dwFlags
0x180058c8e  mov     r8d, r12d; cbInput
0x180058c91  call    BCryptHashData
0x180058c96  mov     ebx, eax
0x180058c98  test    eax, eax
0x180058c9a  jns     short loc_180058CA7
0x180058c9c  mov     r9d, 1C94h
0x180058ca2  jmp     loc_180058A9A
0x180058ca7  mov     r8d, dword ptr [rsp+140h+pbOutput]; cbOutput
0x180058cac  xor     r9d, r9d; dwFlags
0x180058caf  mov     rcx, [rsp+140h+hHash]; hHash
0x180058cb4  lea     rdx, [rdi+r8]; pbOutput
0x180058cb8  call    BCryptFinishHash
0x180058cbd  mov     ebx, eax
0x180058cbf  test    eax, eax
0x180058cc1  jns     short loc_180058CD1
0x180058cc3  mov     r9d, 1C9Eh
0x180058cc9  jmp     loc_180058A9A
0x180058cce  xor     r14d, r14d
0x180058cd1  mov     r8, rsi; Size
0x180058cd4  mov     rdx, rdi; Src
0x180058cd7  mov     rcx, r13; void *
0x180058cda  call    memmove
0x180058cdf  mov     ebx, r14d
0x180058ce2  mov     rcx, rdi; P
0x180058ce5  call    MSCryptFree
0x180058cea  jmp     short loc_180058D17
0x180058cec  mov     r9d, 1BFFh
0x180058cf2  jmp     short loc_180058CFA
0x180058cf4  mov     r9d, 1BE2h
0x180058cfa  mov     ecx, 0C000000Dh
0x180058cff  mov     ebx, 0C000000Dh
0x180058d04  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058d0b  lea     rdx, aStatus; "Status"
0x180058d12  call    DebugTraceError
0x180058d17  mov     rcx, [rsp+140h+phHash]; hHash
0x180058d1c  test    rcx, rcx
0x180058d1f  jz      short loc_180058D26
0x180058d21  call    BCryptDestroyHash
0x180058d26  mov     rcx, [rsp+140h+hHash]; hHash
0x180058d2b  test    rcx, rcx
0x180058d2e  jz      short loc_180058D35
0x180058d30  call    BCryptDestroyHash
0x180058d35  mov     eax, ebx
0x180058d37  mov     rcx, [rbp+40h+var_50]
0x180058d3b  xor     rcx, rsp; StackCookie
0x180058d3e  call    __security_check_cookie
0x180058d43  add     rsp, 108h
0x180058d4a  pop     r15
0x180058d4c  pop     r14
0x180058d4e  pop     r13
0x180058d50  pop     r12
0x180058d52  pop     rdi
0x180058d53  pop     rsi
0x180058d54  pop     rbx
0x180058d55  pop     rbp
0x180058d56  retn
```
