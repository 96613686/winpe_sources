# MinCrypK_VerifySignedDataKModeEx

- ea: `0x18008de28`
- end: `0x18008e5be`
- name: `MinCrypK_VerifySignedDataKModeEx`
- size: `1942`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, void *, __int64, __int64)`
- caller_count: `9`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007d278`
- `0x18007fb28`
- `0x18008cd64`
- `0x18008d2e8`
- `0x18008d7bc`
- `0x18008dd54`
- `0x1800915c4`
- `0x180092434`
- `0x1800e4394`

## callees

- `0x18000ce08`
- `0x180012d3e`
- `0x18002bea6`
- `0x18002c340`
- `0x180059d84`
- `0x18005b340`
- `0x18005b3d4`
- `0x18007614c`
- `0x1800761a4`
- `0x18008ccc4`
- `0x18008d6e0`
- `0x18008de28`
- `0x18008e5c4`
- `0x180090988`
- `0x180090bf0`
- `0x180090eb8`
- `0x180091218`
- `0x180092948`
- `0x180093080`
- `0x180096fdc`
- `0x1800a62d8`
- `0x1800a9e4c`
- `0x1800acc24`
- `0x1800e1f7c`
- `0x1800e426c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18008ded7`
- `ntoskrnl!ExAllocatePool2` at `0x18008e270`
- `ntoskrnl!ExAllocatePool2` at `0x18008ded7`
- `ntoskrnl!ExAllocatePool2` at `0x18008e270`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008e592`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008e5ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e8040`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e805b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008e592`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008e5ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e8040`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e805b`

## pseudocode

```c
__int64 __fastcall MinCrypK_VerifySignedDataKModeEx(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        char *a7,
        __int64 *a8,
        _OWORD *a9)
{
  unsigned int v12; // edi
  __int64 Pool2; // rax
  void *v14; // r14
  int PlatformManifestBinaryIDAttribute; // ebx
  __int64 v16; // r14
  void *v17; // r13
  __int64 SignerCertificateByIssuerAndSerialNumber; // rax
  _DWORD *v19; // r15
  int v20; // eax
  unsigned int i; // ebx
  __int64 v22; // rdx
  __int64 v23; // r15
  char IsWeakTimestampPolicySet; // al
  int v25; // ecx
  unsigned int v26; // r13d
  int v27; // r12d
  __int64 v28; // r15
  int v29; // ecx
  int v30; // r8d
  int v31; // eax
  void *v32; // r15
  unsigned int v33; // r12d
  int v34; // r13d
  int v35; // r15d
  __int64 v36; // r9
  int v37; // eax
  __int64 v39; // [rsp+0h] [rbp-F8h] BYREF
  int SigningTime; // [rsp+30h] [rbp-C8h]
  unsigned int v41; // [rsp+34h] [rbp-C4h]
  void *v42; // [rsp+38h] [rbp-C0h]
  unsigned int v43; // [rsp+40h] [rbp-B8h] BYREF
  int v44; // [rsp+44h] [rbp-B4h] BYREF
  int v45; // [rsp+48h] [rbp-B0h]
  int v46; // [rsp+4Ch] [rbp-ACh] BYREF
  __int64 v47; // [rsp+50h] [rbp-A8h] BYREF
  unsigned int v48; // [rsp+58h] [rbp-A0h] BYREF
  int v49; // [rsp+5Ch] [rbp-9Ch]
  __int128 v50; // [rsp+60h] [rbp-98h] BYREF
  __int128 v51; // [rsp+70h] [rbp-88h]
  __int128 v52; // [rsp+80h] [rbp-78h]
  unsigned int v53; // [rsp+90h] [rbp-68h]
  PVOID P; // [rsp+98h] [rbp-60h]
  __int128 v55; // [rsp+A0h] [rbp-58h] BYREF
  void *v56; // [rsp+B0h] [rbp-48h]
  int v57; // [rsp+B8h] [rbp-40h]
  __int64 v58; // [rsp+C0h] [rbp-38h]
  __int64 *v59; // [rsp+C8h] [rbp-30h]

  v59 = &v39;
  SigningTime = -1073740760;
  v42 = 0;
  v44 = 0;
  P = 0;
  v12 = 0;
  v41 = 0;
  v55 = 0;
  v46 = 0;
  v43 = 0;
  v47 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v49 = 0;
  v45 = 0;
  v48 = 10;
  memset(a7, 0, 0x50u);
  Pool2 = ExAllocatePool2(258, 2768, 1919109443);
  v14 = (void *)Pool2;
  v42 = (void *)Pool2;
  if ( Pool2 )
  {
    v16 = Pool2 + 2400;
    if ( (int)MinAsn1ParseSignedData(a1, a2, Pool2 + 2400) < 0 )
    {
LABEL_4:
      v12 = 327680;
LABEL_91:
      PlatformManifestBinaryIDAttribute = -1073740760;
      SigningTime = -1073740760;
      goto LABEL_92;
    }
    if ( *(_DWORD *)(v16 + 32) != 9 || RtlCompareMemory_0(&qword_1800F4808, *(const void **)(v16 + 40), 9u) != 9 )
    {
      v12 = 0x40000;
      goto LABEL_91;
    }
    if ( a4 && a3 )
    {
      if ( *(_DWORD *)(v16 + 80) )
        *(_OWORD *)a7 = *(_OWORD *)(v16 + 80);
      *((_QWORD *)a7 + 3) = a3;
      *((_DWORD *)a7 + 4) = a4;
    }
    else
    {
      if ( !*(_DWORD *)(v16 + 80) || !*(_DWORD *)(v16 + 96) )
        goto LABEL_4;
      *(_OWORD *)a7 = *(_OWORD *)(v16 + 80);
      if ( (int)MinAsn1SignedDataGetContent(v16, a7 + 16) <= 0 )
        goto LABEL_15;
      v46 = 1;
    }
    if ( !*(_DWORD *)(v16 + 160) )
      goto LABEL_4;
    v17 = v42;
    if ( (int)MinAsn1ParseSignedDataCertificatesEx(v16 + 112, &v48, v42) < 0
      || !v48
      || (SignerCertificateByIssuerAndSerialNumber = I_MinCryptFindSignerCertificateByIssuerAndSerialNumber(
                                                       v16 + 192,
                                                       v16 + 208,
                                                       v48,
                                                       v17),
          (v58 = SignerCertificateByIssuerAndSerialNumber) == 0) )
    {
      v12 = 393216;
      goto LABEL_91;
    }
    *((_OWORD *)a7 + 2) = *(_OWORD *)(SignerCertificateByIssuerAndSerialNumber + 16);
    v19 = (_DWORD *)(v16 + 240);
    *((_OWORD *)a7 + 3) = *(_OWORD *)(v16 + 240);
    *((_OWORD *)a7 + 4) = *(_OWORD *)(v16 + 288);
    v20 = MinCryptVerifyCertificateWithPolicy2(
            SignerCertificateByIssuerAndSerialNumber,
            v48,
            (_DWORD)v17,
            a5,
            a6,
            v16 + 240);
    PlatformManifestBinaryIDAttribute = v20;
    SigningTime = v20;
    if ( v20 < 0 )
    {
      if ( v20 != -1073740285 )
        goto LABEL_93;
      SigningTime = 0;
      v43 = 1;
    }
    if ( *v19 )
    {
      PlatformManifestBinaryIDAttribute = I_MinCryptGetPlatformManifestBinaryIDAttribute(v16 + 240, a6);
      SigningTime = PlatformManifestBinaryIDAttribute;
      if ( PlatformManifestBinaryIDAttribute < 0 )
        goto LABEL_93;
    }
    if ( !a5 || (*(_DWORD *)(a5 + 4) & 0x10) == 0 )
    {
      if ( *(_QWORD *)(a6 + 16) )
      {
        for ( i = 0; ; ++i )
        {
          v53 = i;
          v22 = *(_QWORD *)(a6 + 16);
          if ( i >= *(_DWORD *)(v22 + 48) )
            break;
          v23 = 120LL * i;
          if ( (unsigned __int8)I_MinCryptIsHashAlgPossiblyWeak(
                                  0x400000,
                                  *(unsigned int *)(*(_QWORD *)(v22 + 40) + v23),
                                  0)
            && !(unsigned __int8)MincryptIsWeakCertHashAllowed(v23 + *(_QWORD *)(*(_QWORD *)(a6 + 16) + 40LL)) )
          {
            v49 = 1;
            v57 = 1;
            break;
          }
        }
        v19 = (_DWORD *)(v16 + 240);
      }
      IsWeakTimestampPolicySet = I_MinCryptIsWeakTimestampPolicySet();
      v25 = v45;
      if ( IsWeakTimestampPolicySet )
        v25 = 1;
      v45 = v25;
    }
    v26 = MinCryptDecodeHashAlgorithmIdentifier(v16 + 224);
    if ( v26 )
    {
      v27 = MinCryptDecodeHashAlgorithmIdentifier(v16 + 256);
      if ( !v46 )
      {
        LODWORD(v55) = a4;
        *((_QWORD *)&v55 + 1) = a3;
        goto LABEL_46;
      }
      if ( (int)MinAsn1ExtractContent(*(_QWORD *)(v16 + 104), *(unsigned int *)(v16 + 96), &v55, (char *)&v55 + 8) >= 0 )
      {
LABEL_46:
        v28 = (unsigned int)*v19;
        v46 = v28;
        if ( v27 == 0x8000 && !(_DWORD)v28 )
        {
          v29 = DWORD2(v55);
          v56 = (void *)*((_QWORD *)&v55 + 1);
          v30 = v55;
          goto LABEL_59;
        }
        PlatformManifestBinaryIDAttribute = MinCryptHashMemory(
                                              v26,
                                              1,
                                              (unsigned int)&v55,
                                              (int)v16 + 304,
                                              (__int64)&v44);
        SigningTime = PlatformManifestBinaryIDAttribute;
        if ( PlatformManifestBinaryIDAttribute < 0 )
          goto LABEL_16;
        v29 = v16 + 304;
        v56 = (void *)(v16 + 304);
        if ( !(_DWORD)v28 )
        {
          v30 = v44;
LABEL_59:
          PlatformManifestBinaryIDAttribute = MinCryptVerifySignedHash2(v26, v29, v30, (int)v16 + 272, v58 + 176, 0);
          SigningTime = PlatformManifestBinaryIDAttribute;
          if ( PlatformManifestBinaryIDAttribute >= 0 )
          {
            v33 = v43;
            v34 = v49;
            v35 = v45;
            if ( !v43 && !v49 && !v45 && !a8 )
              goto LABEL_93;
            v43 = 0;
            v47 = 0;
            SigningTime = I_MinCryptGetSigningTime(
                            v16,
                            v48,
                            (_DWORD)v42,
                            (unsigned int)&v50,
                            (__int64)&v47,
                            (__int64)&v43);
            if ( SigningTime < 0
              || v47 > 0
              && (v47 < (__int64)v52
               || v47 > *((__int64 *)&v52 + 1)
               || v47 < *(_QWORD *)(a6 + 32)
               || v47 > *(_QWORD *)(a6 + 40)) )
            {
              v47 = 0;
            }
            if ( v33 )
            {
              if ( !v47 )
                *(_DWORD *)(a6 + 8) |= 0x4000000u;
              PlatformManifestBinaryIDAttribute = MincryptIsTimestampBeforeRevocation(a6, &v47, &v50);
              SigningTime = PlatformManifestBinaryIDAttribute;
              if ( PlatformManifestBinaryIDAttribute < 0 )
                goto LABEL_93;
              *(_DWORD *)(a6 + 8) &= ~0x200000u;
            }
            if ( !a5 || (*(_DWORD *)(a5 + 4) & 0x10) == 0 )
            {
              if ( v34 )
              {
                PlatformManifestBinaryIDAttribute = I_MinCryptCheckCertHashWeakCrypto(0x400000, a6, &v47, 0);
                SigningTime = PlatformManifestBinaryIDAttribute;
                if ( PlatformManifestBinaryIDAttribute < 0 )
                  goto LABEL_93;
              }
              if ( v35 && (_QWORD)v51 )
              {
                LOBYTE(v36) = 1;
                PlatformManifestBinaryIDAttribute = I_MinCryptCheckCertHashWeakCrypto(0x4000000, &v50, &v47, v36);
                SigningTime = PlatformManifestBinaryIDAttribute;
                if ( PlatformManifestBinaryIDAttribute < 0 )
                {
                  *(_DWORD *)(a6 + 8) |= 0x40000u;
                  goto LABEL_93;
                }
                v37 = I_MinCryptCheckTimestampHashWeakCrypto(v43, &v47);
                SigningTime = v37;
                if ( v37 < 0 )
                {
                  *(_DWORD *)(a6 + 8) |= 0x40000u;
                  v43 = v37;
                  local_unwind_0(v59, &loc_18008E4AC);
                  return v43;
                }
              }
            }
            PlatformManifestBinaryIDAttribute = 0;
            SigningTime = 0;
            if ( a8 )
              *a8 = v47;
            if ( a9 )
            {
              *a9 = v50;
              a9[1] = v51;
              a9[2] = v52;
              v50 = 0;
              v52 = 0;
              v51 = 0;
            }
            goto LABEL_93;
          }
LABEL_16:
          v12 = 0x40000;
LABEL_92:
          v41 = v12;
          goto LABEL_93;
        }
        if ( v27 != 0x8000 )
        {
          v31 = I_MinCryptVerifySignerAuthenticatedAttributes(v26, v16 + 304, &v44, v16 + 240);
          SigningTime = v31;
          v30 = v44;
          v29 = v16 + 304;
          goto LABEL_56;
        }
        v32 = (void *)ExAllocatePool2(258, v28, 1919109443);
        P = v32;
        if ( v32 )
        {
          v31 = I_MinCryptVerifyReturnSignerAuthenticatedAttributes(
                  (int)v16 + 304,
                  v44,
                  (_DWORD)v32,
                  (unsigned int)&v46,
                  v16 + 240);
          SigningTime = v31;
          v29 = (int)v32;
          v56 = v32;
          v30 = v46;
LABEL_56:
          PlatformManifestBinaryIDAttribute = v31;
          if ( v31 < 0 )
            goto LABEL_16;
          goto LABEL_59;
        }
        PlatformManifestBinaryIDAttribute = -1073741801;
        SigningTime = -1073741801;
LABEL_93:
        v14 = v42;
        goto LABEL_94;
      }
    }
LABEL_15:
    PlatformManifestBinaryIDAttribute = -1073740760;
    SigningTime = -1073740760;
    goto LABEL_16;
  }
  PlatformManifestBinaryIDAttribute = -1073741801;
  SigningTime = -1073741801;
LABEL_94:
  if ( PlatformManifestBinaryIDAttribute < 0 )
    PlatformManifestBinaryIDAttribute = I_MinCryptBuildErrorPolicy(
                                          (unsigned int)PlatformManifestBinaryIDAttribute,
                                          a6,
                                          v12);
  if ( (_DWORD)v50 )
  {
    I_MincryptFreeChainInfo(v51);
    v50 = 0;
    v51 = 0;
    v52 = 0;
  }
  if ( P )
    ExFreePoolWithTag(P, 0x72634943u);
  if ( v14 )
    ExFreePoolWithTag(v14, 0x72634943u);
  return (unsigned int)PlatformManifestBinaryIDAttribute;
}

```

## disassembly

```asm
0x18008de28  mov     r11, rsp
0x18008de2b  mov     [r11+8], rbx
0x18008de2f  mov     [r11+10h], rsi
0x18008de33  mov     [r11+20h], r9d
0x18008de37  mov     [r11+18h], r8
0x18008de3b  push    rdi
0x18008de3c  push    r12
0x18008de3e  push    r13
0x18008de40  push    r14
0x18008de42  push    r15
0x18008de44  sub     rsp, 0D0h
0x18008de4b  mov     [rsp+0F8h+var_30], rsp
0x18008de53  mov     r13d, r9d
0x18008de56  mov     r15d, edx
0x18008de59  mov     r12, rcx
0x18008de5c  mov     rsi, [r11+30h]
0x18008de60  mov     [rsp+0F8h+var_C8], 0C0000428h
0x18008de68  xor     eax, eax
0x18008de6a  mov     [rsp+0F8h+var_C0], rax
0x18008de6f  mov     [rsp+0F8h+var_B4], eax
0x18008de73  mov     [r11-60h], rax
0x18008de77  mov     edi, eax
0x18008de79  mov     [rsp+0F8h+var_C4], eax
0x18008de7d  xorps   xmm0, xmm0
0x18008de80  movups  xmmword ptr [r11-58h], xmm0
0x18008de85  mov     [rsp+0F8h+var_AC], eax
0x18008de89  mov     [rsp+0F8h+var_B8], eax
0x18008de8d  mov     [rsp+0F8h+var_A8], rax
0x18008de92  movups  [rsp+0F8h+var_98], xmm0
0x18008de97  movups  [rsp+0F8h+var_88], xmm0
0x18008de9c  movups  xmmword ptr [r11-78h], xmm0
0x18008dea1  mov     [rsp+0F8h+var_9C], eax
0x18008dea5  mov     [rsp+0F8h+var_B0], eax
0x18008dea9  mov     [rsp+0F8h+var_A0], 0Ah
0x18008deb1  xor     edx, edx; Val
0x18008deb3  lea     r8d, [rax+50h]; Size
0x18008deb7  mov     rbx, [rsp+0F8h+arg_30]
0x18008debf  mov     rcx, rbx; void *
0x18008dec2  call    memset
0x18008dec7  mov     edx, 0AD0h
0x18008decc  mov     ecx, 102h
0x18008ded1  mov     r8d, 72634943h
0x18008ded7  call    cs:__imp_ExAllocatePool2
0x18008dede  nop     dword ptr [rax+rax+00h]
0x18008dee3  mov     r14, rax
0x18008dee6  mov     [rsp+0F8h+var_C0], rax
0x18008deeb  test    rax, rax
0x18008deee  jnz     short loc_18008DEFE
0x18008def0  mov     ebx, 0C0000017h
0x18008def5  mov     [rsp+0F8h+var_C8], ebx
0x18008def9  jmp     loc_18008E547
0x18008defe  add     r14, 960h
0x18008df05  mov     r8, r14
0x18008df08  mov     edx, r15d
0x18008df0b  mov     rcx, r12
0x18008df0e  call    MinAsn1ParseSignedData
0x18008df13  test    eax, eax
0x18008df15  jns     short loc_18008DF21
0x18008df17  mov     edi, 50000h
0x18008df1c  jmp     loc_18008E535
0x18008df21  cmp     dword ptr [r14+20h], 9
0x18008df26  jnz     loc_18008E530
0x18008df2c  mov     r8d, 9; Length
0x18008df32  mov     rdx, [r14+28h]; Source2
0x18008df36  lea     rcx, qword_1800F4808; Source1
0x18008df3d  call    RtlCompareMemory_0
0x18008df42  cmp     rax, 9
0x18008df46  jnz     loc_18008E530
0x18008df4c  test    r13d, r13d
0x18008df4f  jz      short loc_18008DF7E
0x18008df51  mov     rax, [rsp+0F8h+arg_10]
0x18008df59  test    rax, rax
0x18008df5c  jz      short loc_18008DF7E
0x18008df5e  cmp     dword ptr [r14+50h], 0
0x18008df63  jz      short loc_18008DF6E
0x18008df65  movups  xmm0, xmmword ptr [r14+50h]
0x18008df6a  movdqu  xmmword ptr [rbx], xmm0
0x18008df6e  mov     [rbx+18h], rax
0x18008df72  mov     [rbx+10h], r13d
0x18008df76  mov     r12d, 1
0x18008df7c  jmp     short loc_18008DFC3
0x18008df7e  cmp     dword ptr [r14+50h], 0
0x18008df83  jz      short loc_18008DF17
0x18008df85  cmp     dword ptr [r14+60h], 0
0x18008df8a  jz      short loc_18008DF17
0x18008df8c  movups  xmm0, xmmword ptr [r14+50h]
0x18008df91  movdqu  xmmword ptr [rbx], xmm0
0x18008df95  lea     rdx, [rbx+10h]
0x18008df99  mov     rcx, r14
0x18008df9c  call    MinAsn1SignedDataGetContent
0x18008dfa1  test    eax, eax
0x18008dfa3  jg      short loc_18008DFB8
0x18008dfa5  mov     ebx, 0C0000428h
0x18008dfaa  mov     [rsp+0F8h+var_C8], ebx
0x18008dfae  mov     edi, 40000h
0x18008dfb3  jmp     loc_18008E53E
0x18008dfb8  mov     r12d, 1
0x18008dfbe  mov     [rsp+0F8h+var_AC], r12d
0x18008dfc3  cmp     dword ptr [r14+0A0h], 0
0x18008dfcb  jz      loc_18008DF17
0x18008dfd1  lea     rcx, [r14+70h]
0x18008dfd5  mov     r13, [rsp+0F8h+var_C0]
0x18008dfda  mov     r8, r13
0x18008dfdd  lea     rdx, [rsp+0F8h+var_A0]
0x18008dfe2  call    MinAsn1ParseSignedDataCertificatesEx
0x18008dfe7  test    eax, eax
0x18008dfe9  js      short loc_18008E019
0x18008dfeb  mov     eax, [rsp+0F8h+var_A0]
0x18008dfef  test    eax, eax
0x18008dff1  jz      short loc_18008E019
0x18008dff3  lea     rdx, [r14+0D0h]
0x18008dffa  lea     rcx, [r14+0C0h]
0x18008e001  mov     r9, r13
0x18008e004  mov     r8d, eax
0x18008e007  call    I_MinCryptFindSignerCertificateByIssuerAndSerialNumber
0x18008e00c  mov     [rsp+0F8h+var_38], rax
0x18008e014  test    rax, rax
0x18008e017  jnz     short loc_18008E023
0x18008e019  mov     edi, 60000h
0x18008e01e  jmp     loc_18008E535
0x18008e023  movups  xmm0, xmmword ptr [rax+10h]
0x18008e027  movdqu  xmmword ptr [rbx+20h], xmm0
0x18008e02c  lea     r15, [r14+0F0h]
0x18008e033  movups  xmm0, xmmword ptr [r15]
0x18008e037  movdqu  xmmword ptr [rbx+30h], xmm0
0x18008e03c  movups  xmm1, xmmword ptr [r14+120h]
0x18008e044  movdqu  xmmword ptr [rbx+40h], xmm1
0x18008e049  mov     [rsp+0F8h+var_D0], r15
0x18008e04e  mov     [rsp+0F8h+var_D8], rsi
0x18008e053  mov     r9, [rsp+0F8h+arg_20]
0x18008e05b  mov     r8, r13
0x18008e05e  mov     edx, [rsp+0F8h+var_A0]
0x18008e062  mov     rcx, rax
0x18008e065  call    MinCryptVerifyCertificateWithPolicy2
0x18008e06a  mov     ebx, eax
0x18008e06c  mov     [rsp+0F8h+var_C8], eax
0x18008e070  test    eax, eax
0x18008e072  jns     short loc_18008E08C
0x18008e074  cmp     eax, 0C0000603h
0x18008e079  jnz     loc_18008E542
0x18008e07f  mov     [rsp+0F8h+var_C8], 0
0x18008e087  mov     [rsp+0F8h+var_B8], r12d
0x18008e08c  cmp     dword ptr [r15], 0
0x18008e090  jz      short loc_18008E0AB
0x18008e092  mov     rdx, rsi
0x18008e095  mov     rcx, r15
0x18008e098  call    I_MinCryptGetPlatformManifestBinaryIDAttribute
0x18008e09d  mov     ebx, eax
0x18008e09f  mov     [rsp+0F8h+var_C8], eax
0x18008e0a3  test    eax, eax
0x18008e0a5  js      loc_18008E542
0x18008e0ab  mov     rax, [rsp+0F8h+arg_20]
0x18008e0b3  test    rax, rax
0x18008e0b6  jz      short loc_18008E0BF
0x18008e0b8  mov     eax, [rax+4]
0x18008e0bb  test    al, 10h
0x18008e0bd  jnz     short loc_18008E137
0x18008e0bf  cmp     qword ptr [rsi+10h], 0
0x18008e0c4  jz      short loc_18008E124
0x18008e0c6  xor     ebx, ebx
0x18008e0c8  mov     [rsp+0F8h+var_68], ebx
0x18008e0cf  mov     rdx, [rsi+10h]
0x18008e0d3  cmp     ebx, [rdx+30h]
0x18008e0d6  jnb     short loc_18008E11D
0x18008e0d8  mov     eax, ebx
0x18008e0da  imul    r15, rax, 78h ; 'x'
0x18008e0de  mov     rdx, [rdx+28h]
0x18008e0e2  xor     r8d, r8d
0x18008e0e5  mov     edx, [rdx+r15]
0x18008e0e9  mov     ecx, 400000h
0x18008e0ee  call    I_MinCryptIsHashAlgPossiblyWeak
0x18008e0f3  test    al, al
0x18008e0f5  jz      loc_18008E18B
0x18008e0fb  mov     rax, [rsi+10h]
0x18008e0ff  mov     rcx, [rax+28h]
0x18008e103  add     rcx, r15
0x18008e106  call    MincryptIsWeakCertHashAllowed
0x18008e10b  test    al, al
0x18008e10d  jnz     short loc_18008E18B
0x18008e10f  mov     eax, r12d
0x18008e112  mov     [rsp+0F8h+var_9C], eax
0x18008e116  mov     [rsp+0F8h+var_40], eax
0x18008e11d  lea     r15, [r14+0F0h]
0x18008e124  call    I_MinCryptIsWeakTimestampPolicySet
0x18008e129  mov     ecx, [rsp+0F8h+var_B0]
0x18008e12d  test    al, al
0x18008e12f  cmovnz  ecx, r12d
0x18008e133  mov     [rsp+0F8h+var_B0], ecx
0x18008e137  lea     rcx, [r14+0E0h]
0x18008e13e  call    MinCryptDecodeHashAlgorithmIdentifier
0x18008e143  mov     r13d, eax
0x18008e146  test    eax, eax
0x18008e148  jz      loc_18008DFA5
0x18008e14e  lea     rcx, [r14+100h]
0x18008e155  call    MinCryptDecodeHashAlgorithmIdentifier
0x18008e15a  mov     r12d, eax
0x18008e15d  cmp     [rsp+0F8h+var_AC], 0
0x18008e162  jz      short loc_18008E193
0x18008e164  lea     r9, [rsp+0F8h+var_50]
0x18008e16c  lea     r8, [rsp+0F8h+var_58]
0x18008e174  mov     edx, [r14+60h]
0x18008e178  mov     rcx, [r14+68h]
0x18008e17c  call    MinAsn1ExtractContent
0x18008e181  test    eax, eax
0x18008e183  js      loc_18008DFA5
0x18008e189  jmp     short loc_18008E1B1
0x18008e18b  add     ebx, r12d
0x18008e18e  jmp     loc_18008E0C8
0x18008e193  mov     eax, [rsp+0F8h+arg_18]
0x18008e19a  mov     [rsp+0F8h+var_58], eax
0x18008e1a1  mov     rax, [rsp+0F8h+arg_10]
0x18008e1a9  mov     [rsp+0F8h+var_50], rax
0x18008e1b1  mov     r15d, [r15]
0x18008e1b4  mov     [rsp+0F8h+var_AC], r15d
0x18008e1b9  cmp     r12d, 8000h
0x18008e1c0  jnz     short loc_18008E1E4
0x18008e1c2  test    r15d, r15d
0x18008e1c5  jnz     short loc_18008E1E4
0x18008e1c7  mov     rcx, [rsp+0F8h+var_50]
0x18008e1cf  mov     [rsp+0F8h+var_48], rcx
0x18008e1d7  mov     r8d, [rsp+0F8h+var_58]
0x18008e1df  jmp     loc_18008E2E2
0x18008e1e4  lea     rax, [rsp+0F8h+var_B4]
0x18008e1e9  mov     [rsp+0F8h+var_D8], rax
0x18008e1ee  lea     r9, [r14+130h]
0x18008e1f5  lea     r8, [rsp+0F8h+var_58]
0x18008e1fd  mov     edx, 1
0x18008e202  mov     ecx, r13d
0x18008e205  call    MinCryptHashMemory
0x18008e20a  mov     ebx, eax
0x18008e20c  mov     [rsp+0F8h+var_C8], eax
0x18008e210  test    eax, eax
0x18008e212  js      loc_18008DFAE
0x18008e218  lea     rcx, [r14+130h]
0x18008e21f  mov     [rsp+0F8h+var_48], rcx
0x18008e227  test    r15d, r15d
0x18008e22a  jz      loc_18008E2DD
0x18008e230  cmp     r12d, 8000h
0x18008e237  jz      short loc_18008E262
0x18008e239  lea     r9, [r14+0F0h]
0x18008e240  lea     r8, [rsp+0F8h+var_B4]
0x18008e245  mov     rdx, rcx
0x18008e248  mov     ecx, r13d
0x18008e24b  call    I_MinCryptVerifySignerAuthenticatedAttributes
0x18008e250  mov     [rsp+0F8h+var_C8], eax
0x18008e254  mov     r8d, [rsp+0F8h+var_B4]
0x18008e259  lea     rcx, [r14+130h]
0x18008e260  jmp     short loc_18008E2D2
0x18008e262  mov     rdx, r15
0x18008e265  mov     ecx, 102h
0x18008e26a  mov     r8d, 72634943h
0x18008e270  call    cs:__imp_ExAllocatePool2
0x18008e277  nop     dword ptr [rax+rax+00h]
0x18008e27c  mov     r15, rax
0x18008e27f  mov     [rsp+0F8h+P], rax
0x18008e287  test    rax, rax
0x18008e28a  jnz     short loc_18008E29A
0x18008e28c  mov     ebx, 0C0000017h
0x18008e291  mov     [rsp+0F8h+var_C8], ebx
0x18008e295  jmp     loc_18008E542
0x18008e29a  lea     rax, [r14+0F0h]
0x18008e2a1  mov     [rsp+0F8h+var_D8], rax
0x18008e2a6  lea     r9, [rsp+0F8h+var_AC]
0x18008e2ab  mov     r8, r15
0x18008e2ae  mov     edx, [rsp+0F8h+var_B4]
0x18008e2b2  lea     rcx, [r14+130h]
0x18008e2b9  call    I_MinCryptVerifyReturnSignerAuthenticatedAttributes
0x18008e2be  mov     [rsp+0F8h+var_C8], eax
0x18008e2c2  mov     rcx, r15
0x18008e2c5  mov     [rsp+0F8h+var_48], rcx
0x18008e2cd  mov     r8d, [rsp+0F8h+var_AC]
0x18008e2d2  mov     ebx, eax
0x18008e2d4  test    eax, eax
0x18008e2d6  jns     short loc_18008E2E2
0x18008e2d8  jmp     loc_18008DFAE
0x18008e2dd  mov     r8d, [rsp+0F8h+var_B4]
0x18008e2e2  mov     rax, [rsp+0F8h+var_38]
0x18008e2ea  add     rax, 0B0h
0x18008e2f0  lea     r9, [r14+110h]
0x18008e2f7  mov     [rsp+0F8h+var_D0], 0
0x18008e300  mov     [rsp+0F8h+var_D8], rax
0x18008e305  mov     rdx, rcx
0x18008e308  mov     ecx, r13d
0x18008e30b  call    MinCryptVerifySignedHash2
0x18008e310  mov     ebx, eax
0x18008e312  mov     [rsp+0F8h+var_C8], eax
0x18008e316  test    eax, eax
0x18008e318  js      loc_18008DFAE
0x18008e31e  mov     r12d, [rsp+0F8h+var_B8]
0x18008e323  mov     r13d, [rsp+0F8h+var_9C]
0x18008e328  mov     r15d, [rsp+0F8h+var_B0]
0x18008e32d  test    r12d, r12d
0x18008e330  jnz     short loc_18008E34B
0x18008e332  test    r13d, r13d
0x18008e335  jnz     short loc_18008E34B
0x18008e337  test    r15d, r15d
0x18008e33a  jnz     short loc_18008E34B
0x18008e33c  cmp     [rsp+0F8h+arg_38], 0
0x18008e345  jz      loc_18008E542
0x18008e34b  mov     [rsp+0F8h+var_B8], 0
  ... truncated ...
```
