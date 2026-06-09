# TlsGenerateSecretAgreementMasterKey

- ea: `0x180007990`
- end: `0x180007dde`
- name: `TlsGenerateSecretAgreementMasterKey`
- size: `1102`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180006070`

## callees

- `0x180003ef0`
- `0x180005cb0`
- `0x180007940`
- `0x180007990`
- `0x1800081a8`
- `0x18000b594`
- `0x18000b654`
- `0x180020248`

## import_xrefs

- `ncrypt!NCryptDeriveKey` at `0x180007a6d`
- `ncrypt!NCryptDeriveKey` at `0x180007acb`
- `ncrypt!NCryptDeriveKey` at `0x180007a6d`
- `ncrypt!NCryptDeriveKey` at `0x180007acb`
- `ncrypt!NCryptSecretAgreement` at `0x180007a39`
- `ncrypt!NCryptSecretAgreement` at `0x180007a39`
- `ncrypt!NCryptFreeObject` at `0x180007b90`
- `ncrypt!NCryptFreeObject` at `0x180007b90`

## string_xrefs

- `0x180007bda`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180007c2a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180007cf8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180007d3f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180007d66`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsGenerateSecretAgreementMasterKey(
        int a1,
        _DWORD *a2,
        NCRYPT_KEY_HANDLE a3,
        NCRYPT_KEY_HANDLE a4,
        __int64 a5,
        DWORD pcbResult,
        int a7)
{
  __int64 v10; // rdx
  _DWORD *v12; // rdi
  __int64 v13; // rdx
  int v14; // ebx
  SECURITY_STATUS v15; // eax
  __int64 v16; // rax
  int v17; // edx
  unsigned __int64 v18; // r14
  DWORD v19; // ecx
  _BYTE *v20; // rax
  DWORD v21; // r8d
  _BYTE *v22; // rdx
  _QWORD *v24; // rcx
  __int64 v25; // r9
  int cbDerivedKey; // [rsp+20h] [rbp-71h]
  char dwFlags; // [rsp+30h] [rbp-61h]
  int v28; // [rsp+60h] [rbp-31h] BYREF
  int v29; // [rsp+64h] [rbp-2Dh] BYREF
  NCRYPT_SECRET_HANDLE phAgreedSecret; // [rsp+68h] [rbp-29h] BYREF
  __int64 v31; // [rsp+70h] [rbp-21h] BYREF
  __int64 v32; // [rsp+78h] [rbp-19h] BYREF
  __int64 v33[10]; // [rsp+80h] [rbp-11h] BYREF
  int v34; // [rsp+E8h] [rbp+57h] BYREF

  v32 = 0;
  v10 = (unsigned int)a2[2];
  v12 = 0;
  v28 = 0;
  v31 = 0;
  v34 = 0;
  v33[0] = 0;
  v29 = 0;
  phAgreedSecret = 0;
  pcbResult = 0;
  v14 = TlsParseParameterList(a5, v10, &v32, &v28, &v31, &v34, v33, &v29, 0, 0, 0);
  if ( v14 >= 0 )
  {
    v14 = NCryptSecretAgreement(a3, a4, &phAgreedSecret, 0);
    if ( v14 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        dwFlags = 12;
        goto LABEL_23;
      }
      goto LABEL_15;
    }
    v15 = NCryptDeriveKey(phAgreedSecret, L"TRUNCATE", 0, 0, 0, &pcbResult, 0);
    v14 = v15;
    if ( v15 < 0 )
    {
      v25 = 1309;
      goto LABEL_43;
    }
    v16 = SafeAllocaAllocateFromHeap(pcbResult + 12);
    v12 = (_DWORD *)v16;
    if ( !v16 )
    {
      v14 = -2146893810;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v17,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          (unsigned int)"Status",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          38);
      goto LABEL_15;
    }
    *(_DWORD *)(v16 + 4) = 1936944183;
    v18 = v16 + 12;
    *(_DWORD *)(v16 + 8) = a2[2];
    v14 = NCryptDeriveKey(phAgreedSecret, L"TRUNCATE", 0, (PBYTE)(v16 + 12), pcbResult, &pcbResult, 0);
    if ( v14 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        dwFlags = 55;
        goto LABEL_23;
      }
      goto LABEL_15;
    }
    v19 = pcbResult;
    if ( a7 == 196610 )
    {
      if ( !pcbResult )
        goto LABEL_36;
      do
      {
        v13 = v19 - 1;
        if ( *(_BYTE *)(v13 + v18) )
          break;
        pcbResult = --v19;
      }
      while ( (_DWORD)v13 );
    }
    if ( v19 )
    {
      *v12 = v19 + 12;
      v20 = v12 + 3;
      v21 = pcbResult;
      v22 = (_BYTE *)(v18 + pcbResult - 1LL);
      if ( v18 < (unsigned __int64)v22 )
      {
        do
        {
          *v20 ^= *v22;
          *v22 ^= *v20;
          v19 = (unsigned __int8)*v22--;
          *v20++ ^= v19;
        }
        while ( v20 < v22 );
        v21 = pcbResult;
      }
      if ( *a2 < 0x50u )
      {
        v14 = -2146893779;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v22,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            (unsigned int)"Status",
            45,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            100);
        goto LABEL_15;
      }
      if ( a2[2] >= 0x301u )
      {
        v14 = Tls1ComputeMasterKey(v19, (_DWORD)a2, (_DWORD)v12, v32, v28, v31, v34, v33[0], v29);
        if ( v14 >= 0 )
        {
LABEL_14:
          v14 = 0;
          goto LABEL_15;
        }
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          dwFlags = 117;
          goto LABEL_23;
        }
        goto LABEL_15;
      }
      v15 = Ssl3ComputeMasterKey(a1, (int)v12 + 12, v21, (int)a2 + 28, cbDerivedKey, v32, v28, v31, v34);
      v14 = v15;
      if ( v15 >= 0 )
        goto LABEL_14;
      v25 = 1415;
LABEL_43:
      DebugTraceError((unsigned int)v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v25);
      goto LABEL_15;
    }
LABEL_36:
    v14 = -2146893779;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        (unsigned int)"Status",
        45,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        70);
    goto LABEL_15;
  }
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    dwFlags = -3;
LABEL_23:
    WPP_SF_sDsd(
      v24[2],
      v13,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      (unsigned int)"Status",
      v14,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      dwFlags);
  }
LABEL_15:
  if ( phAgreedSecret )
    NCryptFreeObject(phAgreedSecret);
  if ( v12 )
    MSCryptFree(v12);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180007990  push    rbp
0x180007992  push    rbx
0x180007993  push    rsi
0x180007994  push    rdi
0x180007995  push    r12
0x180007997  push    r13
0x180007999  push    r14
0x18000799b  push    r15
0x18000799d  lea     rbp, [rsp-7]
0x1800079a2  sub     rsp, 98h
0x1800079a9  xor     r13d, r13d
0x1800079ac  lea     rax, [rbp+3Fh+var_6C]
0x1800079b0  mov     [rsp+0D0h+var_80], r13
0x1800079b5  mov     r14, r9
0x1800079b8  mov     [rsp+0D0h+var_88], r13
0x1800079bd  lea     r9, [rbp+3Fh+var_70]
0x1800079c1  mov     [rsp+0D0h+var_90], r13
0x1800079c6  mov     r15, r8
0x1800079c9  mov     [rsp+0D0h+var_98], rax
0x1800079ce  lea     r8, [rbp+3Fh+var_58]
0x1800079d2  lea     rax, [rbp+3Fh+var_50]
0x1800079d6  mov     [rbp+3Fh+var_58], r13
0x1800079da  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800079df  mov     rsi, rdx
0x1800079e2  mov     edx, [rdx+8]
0x1800079e5  lea     rax, [rbp+3Fh+arg_8]
0x1800079e9  mov     [rsp+0D0h+pcbResult], rax
0x1800079ee  mov     r12, rcx
0x1800079f1  mov     rcx, [rbp+3Fh+arg_20]
0x1800079f5  lea     rax, [rbp+3Fh+var_60]
0x1800079f9  mov     qword ptr [rsp+0D0h+cbDerivedKey], rax
0x1800079fe  mov     edi, r13d
0x180007a01  mov     [rbp+3Fh+var_70], r13d
0x180007a05  mov     [rbp+3Fh+var_60], r13
0x180007a09  mov     [rbp+3Fh+arg_8], r13d
0x180007a0d  mov     [rbp+3Fh+var_50], r13
0x180007a11  mov     [rbp+3Fh+var_6C], r13d
0x180007a15  mov     [rbp+3Fh+phAgreedSecret], r13
0x180007a19  mov     [rbp+3Fh+arg_28], r13d
0x180007a1d  call    TlsParseParameterList
0x180007a22  mov     ebx, eax
0x180007a24  test    eax, eax
0x180007a26  js      loc_180007BB9
0x180007a2c  xor     r9d, r9d; dwFlags
0x180007a2f  lea     r8, [rbp+3Fh+phAgreedSecret]; phAgreedSecret
0x180007a33  mov     rdx, r14; hPubKey
0x180007a36  mov     rcx, r15; hPrivKey
0x180007a39  call    cs:__imp_NCryptSecretAgreement
0x180007a3f  mov     ebx, eax
0x180007a41  test    eax, eax
0x180007a43  js      loc_180007C9C
0x180007a49  mov     rcx, [rbp+3Fh+phAgreedSecret]; hSharedSecret
0x180007a4d  lea     rax, [rbp+3Fh+arg_28]
0x180007a51  mov     [rsp+0D0h+dwFlags], r13d; dwFlags
0x180007a56  lea     rdx, pwszKDF; "TRUNCATE"
0x180007a5d  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180007a62  xor     r9d, r9d; pbDerivedKey
0x180007a65  xor     r8d, r8d; pParameterList
0x180007a68  mov     [rsp+0D0h+cbDerivedKey], r13d; cbDerivedKey
0x180007a6d  call    cs:__imp_NCryptDeriveKey
0x180007a73  mov     ebx, eax
0x180007a75  test    eax, eax
0x180007a77  js      loc_180007D58
0x180007a7d  mov     ecx, [rbp+3Fh+arg_28]
0x180007a80  add     ecx, 0Ch
0x180007a83  call    SafeAllocaAllocateFromHeap
0x180007a88  mov     rdi, rax
0x180007a8b  test    rax, rax
0x180007a8e  jz      loc_180007BFC
0x180007a94  mov     dword ptr [rax+4], 73736C37h
0x180007a9b  lea     r14, [rdi+0Ch]
0x180007a9f  mov     eax, [rsi+8]
0x180007aa2  lea     rdx, pwszKDF; "TRUNCATE"
0x180007aa9  mov     [rdi+8], eax
0x180007aac  mov     r9, r14; pbDerivedKey
0x180007aaf  mov     rcx, [rbp+3Fh+phAgreedSecret]; hSharedSecret
0x180007ab3  lea     rax, [rbp+3Fh+arg_28]
0x180007ab7  mov     [rsp+0D0h+dwFlags], r13d; dwFlags
0x180007abc  xor     r8d, r8d; pParameterList
0x180007abf  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180007ac4  mov     eax, [rbp+3Fh+arg_28]
0x180007ac7  mov     [rsp+0D0h+cbDerivedKey], eax; cbDerivedKey
0x180007acb  call    cs:__imp_NCryptDeriveKey
0x180007ad1  mov     ebx, eax
0x180007ad3  test    eax, eax
0x180007ad5  js      loc_180007C6E
0x180007adb  cmp     [rbp+3Fh+arg_30], 30002h
0x180007ae2  mov     ecx, [rbp+3Fh+arg_28]
0x180007ae5  jz      loc_180007D80
0x180007aeb  test    ecx, ecx
0x180007aed  jz      loc_180007CCA
0x180007af3  lea     eax, [rcx+0Ch]
0x180007af6  mov     [rdi], eax
0x180007af8  mov     rax, r14
0x180007afb  mov     r8d, [rbp+3Fh+arg_28]
0x180007aff  lea     rdx, [r8-1]
0x180007b03  add     rdx, r14
0x180007b06  cmp     r14, rdx
0x180007b09  jnb     short loc_180007B2E
0x180007b0b  nop     dword ptr [rax+rax+00h]
0x180007b10  movzx   ecx, byte ptr [rdx]
0x180007b13  xor     [rax], cl
0x180007b15  movzx   ecx, byte ptr [rax]
0x180007b18  xor     [rdx], cl
0x180007b1a  movzx   ecx, byte ptr [rdx]
0x180007b1d  dec     rdx
0x180007b20  xor     [rax], cl
0x180007b22  inc     rax
0x180007b25  cmp     rax, rdx
0x180007b28  jb      short loc_180007B10
0x180007b2a  mov     r8d, [rbp+3Fh+arg_28]
0x180007b2e  cmp     dword ptr [rsi], 50h ; 'P'
0x180007b31  jb      loc_180007D11
0x180007b37  cmp     dword ptr [rsi+8], 301h
0x180007b3e  jb      loc_180007DA3
0x180007b44  mov     eax, [rbp+3Fh+var_6C]
0x180007b47  mov     r8, rdi
0x180007b4a  mov     r9, [rbp+3Fh+var_58]
0x180007b4e  mov     rdx, rsi
0x180007b51  mov     dword ptr [rsp+0D0h+var_90], eax
0x180007b55  mov     rax, [rbp+3Fh+var_50]
0x180007b59  mov     [rsp+0D0h+var_98], rax
0x180007b5e  mov     eax, [rbp+3Fh+arg_8]
0x180007b61  mov     [rsp+0D0h+dwFlags], eax
0x180007b65  mov     rax, [rbp+3Fh+var_60]
0x180007b69  mov     [rsp+0D0h+pcbResult], rax
0x180007b6e  mov     eax, [rbp+3Fh+var_70]
0x180007b71  mov     [rsp+0D0h+cbDerivedKey], eax
0x180007b75  call    Tls1ComputeMasterKey
0x180007b7a  mov     ebx, eax
0x180007b7c  test    eax, eax
0x180007b7e  js      loc_180007C40
0x180007b84  mov     ebx, r13d
0x180007b87  mov     rcx, [rbp+3Fh+phAgreedSecret]; hObject
0x180007b8b  test    rcx, rcx
0x180007b8e  jz      short loc_180007B96
0x180007b90  call    cs:__imp_NCryptFreeObject
0x180007b96  test    rdi, rdi
0x180007b99  jz      short loc_180007BA3
0x180007b9b  mov     rcx, rdi
0x180007b9e  call    MSCryptFree
0x180007ba3  mov     eax, ebx
0x180007ba5  add     rsp, 98h
0x180007bac  pop     r15
0x180007bae  pop     r14
0x180007bb0  pop     r13
0x180007bb2  pop     r12
0x180007bb4  pop     rdi
0x180007bb5  pop     rsi
0x180007bb6  pop     rbx
0x180007bb7  pop     rbp
0x180007bb8  retn
0x180007bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bc0  lea     rax, WPP_GLOBAL_Control
0x180007bc7  cmp     rcx, rax
0x180007bca  jz      short loc_180007B87
0x180007bcc  test    byte ptr [rcx+1Ch], 1
0x180007bd0  jz      short loc_180007B87
0x180007bd2  mov     [rsp+0D0h+dwFlags], 4FDh
0x180007bda  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007be1  mov     [rsp+0D0h+pcbResult], r8
0x180007be6  mov     [rsp+0D0h+cbDerivedKey], ebx
0x180007bea  mov     rcx, [rcx+10h]
0x180007bee  lea     r9, aStatus; "Status"
0x180007bf5  call    WPP_SF_sDsd
0x180007bfa  jmp     short loc_180007B87
0x180007bfc  mov     ebx, 8009000Eh
0x180007c01  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c08  lea     rax, WPP_GLOBAL_Control
0x180007c0f  cmp     rcx, rax
0x180007c12  jz      loc_180007B87
0x180007c18  test    byte ptr [rcx+1Ch], 1
0x180007c1c  jz      loc_180007B87
0x180007c22  mov     [rsp+0D0h+dwFlags], 526h
0x180007c2a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007c31  mov     [rsp+0D0h+pcbResult], r8
0x180007c36  mov     [rsp+0D0h+cbDerivedKey], 8009000Eh
0x180007c3e  jmp     short loc_180007BEA
0x180007c40  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c47  lea     rax, WPP_GLOBAL_Control
0x180007c4e  cmp     rcx, rax
0x180007c51  jz      loc_180007B87
0x180007c57  test    byte ptr [rcx+1Ch], 1
0x180007c5b  jz      loc_180007B87
0x180007c61  mov     [rsp+0D0h+dwFlags], 575h
0x180007c69  jmp     loc_180007BDA
0x180007c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c75  lea     rax, WPP_GLOBAL_Control
0x180007c7c  cmp     rcx, rax
0x180007c7f  jz      loc_180007B87
0x180007c85  test    byte ptr [rcx+1Ch], 1
0x180007c89  jz      loc_180007B87
0x180007c8f  mov     [rsp+0D0h+dwFlags], 537h
0x180007c97  jmp     loc_180007BDA
0x180007c9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ca3  lea     rax, WPP_GLOBAL_Control
0x180007caa  cmp     rcx, rax
0x180007cad  jz      loc_180007B87
0x180007cb3  test    byte ptr [rcx+1Ch], 1
0x180007cb7  jz      loc_180007B87
0x180007cbd  mov     [rsp+0D0h+dwFlags], 50Ch
0x180007cc5  jmp     loc_180007BDA
0x180007cca  mov     ebx, 8009002Dh
0x180007ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cd6  lea     rax, WPP_GLOBAL_Control
0x180007cdd  cmp     rcx, rax
0x180007ce0  jz      loc_180007B87
0x180007ce6  test    byte ptr [rcx+1Ch], 1
0x180007cea  jz      loc_180007B87
0x180007cf0  mov     [rsp+0D0h+dwFlags], 546h
0x180007cf8  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007cff  mov     [rsp+0D0h+pcbResult], r8
0x180007d04  mov     [rsp+0D0h+cbDerivedKey], 8009002Dh
0x180007d0c  jmp     loc_180007BEA
0x180007d11  mov     ebx, 8009002Dh
0x180007d16  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d1d  lea     rax, WPP_GLOBAL_Control
0x180007d24  cmp     rcx, rax
0x180007d27  jz      loc_180007B87
0x180007d2d  test    byte ptr [rcx+1Ch], 1
0x180007d31  jz      loc_180007B87
0x180007d37  mov     [rsp+0D0h+dwFlags], 564h
0x180007d3f  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007d46  mov     [rsp+0D0h+pcbResult], r8
0x180007d4b  mov     [rsp+0D0h+cbDerivedKey], 8009002Dh
0x180007d53  jmp     loc_180007BEA
0x180007d58  mov     r9d, 51Dh
0x180007d5e  jmp     short loc_180007D66
0x180007d60  mov     r9d, 587h
0x180007d66  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007d6d  mov     ecx, eax
0x180007d6f  lea     rdx, aStatus; "Status"
0x180007d76  call    DebugTraceError
0x180007d7b  jmp     loc_180007B87
0x180007d80  test    ecx, ecx
0x180007d82  jz      loc_180007CCA
0x180007d88  lea     edx, [rcx-1]
0x180007d8b  cmp     [rdx+r14], r13b
0x180007d8f  jnz     loc_180007AEB
0x180007d95  mov     [rbp+3Fh+arg_28], edx
0x180007d98  mov     ecx, edx
0x180007d9a  test    edx, edx
0x180007d9c  jnz     short loc_180007D88
0x180007d9e  jmp     loc_180007AEB
0x180007da3  mov     eax, [rbp+3Fh+arg_8]
0x180007da6  lea     r9, [rsi+1Ch]
0x180007daa  mov     dword ptr [rsp+0D0h+var_90], eax
0x180007dae  mov     rdx, r14
0x180007db1  mov     rax, [rbp+3Fh+var_60]
0x180007db5  mov     rcx, r12
0x180007db8  mov     [rsp+0D0h+var_98], rax
0x180007dbd  mov     eax, [rbp+3Fh+var_70]
0x180007dc0  mov     [rsp+0D0h+dwFlags], eax
0x180007dc4  mov     rax, [rbp+3Fh+var_58]
0x180007dc8  mov     [rsp+0D0h+pcbResult], rax
0x180007dcd  call    Ssl3ComputeMasterKey
0x180007dd2  mov     ebx, eax
0x180007dd4  test    eax, eax
0x180007dd6  jns     loc_180007B84
0x180007ddc  jmp     short loc_180007D60
```
