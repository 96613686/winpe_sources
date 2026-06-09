# MinCrypK_VerifySignedDataKModeEx

- ea: `0x18008f458`
- end: `0x18008fbee`
- name: `MinCrypK_VerifySignedDataKModeEx`
- size: `1942`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, void *, __int64, __int64)`
- caller_count: `9`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007e894`
- `0x180081154`
- `0x18008e394`
- `0x18008e918`
- `0x18008edec`
- `0x18008f384`
- `0x180092bf4`
- `0x180093a64`
- `0x1800e4384`

## callees

- `0x18000ce08`
- `0x180012c26`
- `0x18002bed6`
- `0x18002c380`
- `0x18005aa9c`
- `0x18005c050`
- `0x18005c0e4`
- `0x1800776fc`
- `0x180077754`
- `0x18008e2f4`
- `0x18008ed10`
- `0x18008f458`
- `0x18008fbf4`
- `0x180091fb8`
- `0x180092220`
- `0x1800924e8`
- `0x180092848`
- `0x180093f78`
- `0x1800946b0`
- `0x18009860c`
- `0x1800a74a8`
- `0x1800ab2cc`
- `0x1800ae0a4`
- `0x1800e2f6c`
- `0x1800e425c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18008f507`
- `ntoskrnl!ExAllocatePool2` at `0x18008f8a0`
- `ntoskrnl!ExAllocatePool2` at `0x18008f507`
- `ntoskrnl!ExAllocatePool2` at `0x18008f8a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008fbc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008fbdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e97e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e97fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008fbc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008fbdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e97e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e97fb`

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
    if ( *(_DWORD *)(v16 + 32) != 9 || RtlCompareMemory_0(&qword_1800F5808, *(const void **)(v16 + 40), 9u) != 9 )
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
                  local_unwind_0(v59, &loc_18008FADC);
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
0x18008f458  mov     r11, rsp
0x18008f45b  mov     [r11+8], rbx
0x18008f45f  mov     [r11+10h], rsi
0x18008f463  mov     [r11+20h], r9d
0x18008f467  mov     [r11+18h], r8
0x18008f46b  push    rdi
0x18008f46c  push    r12
0x18008f46e  push    r13
0x18008f470  push    r14
0x18008f472  push    r15
0x18008f474  sub     rsp, 0D0h
0x18008f47b  mov     [rsp+0F8h+var_30], rsp
0x18008f483  mov     r13d, r9d
0x18008f486  mov     r15d, edx
0x18008f489  mov     r12, rcx
0x18008f48c  mov     rsi, [r11+30h]
0x18008f490  mov     [rsp+0F8h+var_C8], 0C0000428h
0x18008f498  xor     eax, eax
0x18008f49a  mov     [rsp+0F8h+var_C0], rax
0x18008f49f  mov     [rsp+0F8h+var_B4], eax
0x18008f4a3  mov     [r11-60h], rax
0x18008f4a7  mov     edi, eax
0x18008f4a9  mov     [rsp+0F8h+var_C4], eax
0x18008f4ad  xorps   xmm0, xmm0
0x18008f4b0  movups  xmmword ptr [r11-58h], xmm0
0x18008f4b5  mov     [rsp+0F8h+var_AC], eax
0x18008f4b9  mov     [rsp+0F8h+var_B8], eax
0x18008f4bd  mov     [rsp+0F8h+var_A8], rax
0x18008f4c2  movups  [rsp+0F8h+var_98], xmm0
0x18008f4c7  movups  [rsp+0F8h+var_88], xmm0
0x18008f4cc  movups  xmmword ptr [r11-78h], xmm0
0x18008f4d1  mov     [rsp+0F8h+var_9C], eax
0x18008f4d5  mov     [rsp+0F8h+var_B0], eax
0x18008f4d9  mov     [rsp+0F8h+var_A0], 0Ah
0x18008f4e1  xor     edx, edx; Val
0x18008f4e3  lea     r8d, [rax+50h]; Size
0x18008f4e7  mov     rbx, [rsp+0F8h+arg_30]
0x18008f4ef  mov     rcx, rbx; void *
0x18008f4f2  call    memset
0x18008f4f7  mov     edx, 0AD0h
0x18008f4fc  mov     ecx, 102h
0x18008f501  mov     r8d, 72634943h
0x18008f507  call    cs:__imp_ExAllocatePool2
0x18008f50e  nop     dword ptr [rax+rax+00h]
0x18008f513  mov     r14, rax
0x18008f516  mov     [rsp+0F8h+var_C0], rax
0x18008f51b  test    rax, rax
0x18008f51e  jnz     short loc_18008F52E
0x18008f520  mov     ebx, 0C0000017h
0x18008f525  mov     [rsp+0F8h+var_C8], ebx
0x18008f529  jmp     loc_18008FB77
0x18008f52e  add     r14, 960h
0x18008f535  mov     r8, r14
0x18008f538  mov     edx, r15d
0x18008f53b  mov     rcx, r12
0x18008f53e  call    MinAsn1ParseSignedData
0x18008f543  test    eax, eax
0x18008f545  jns     short loc_18008F551
0x18008f547  mov     edi, 50000h
0x18008f54c  jmp     loc_18008FB65
0x18008f551  cmp     dword ptr [r14+20h], 9
0x18008f556  jnz     loc_18008FB60
0x18008f55c  mov     r8d, 9; Length
0x18008f562  mov     rdx, [r14+28h]; Source2
0x18008f566  lea     rcx, qword_1800F5808; Source1
0x18008f56d  call    RtlCompareMemory_0
0x18008f572  cmp     rax, 9
0x18008f576  jnz     loc_18008FB60
0x18008f57c  test    r13d, r13d
0x18008f57f  jz      short loc_18008F5AE
0x18008f581  mov     rax, [rsp+0F8h+arg_10]
0x18008f589  test    rax, rax
0x18008f58c  jz      short loc_18008F5AE
0x18008f58e  cmp     dword ptr [r14+50h], 0
0x18008f593  jz      short loc_18008F59E
0x18008f595  movups  xmm0, xmmword ptr [r14+50h]
0x18008f59a  movdqu  xmmword ptr [rbx], xmm0
0x18008f59e  mov     [rbx+18h], rax
0x18008f5a2  mov     [rbx+10h], r13d
0x18008f5a6  mov     r12d, 1
0x18008f5ac  jmp     short loc_18008F5F3
0x18008f5ae  cmp     dword ptr [r14+50h], 0
0x18008f5b3  jz      short loc_18008F547
0x18008f5b5  cmp     dword ptr [r14+60h], 0
0x18008f5ba  jz      short loc_18008F547
0x18008f5bc  movups  xmm0, xmmword ptr [r14+50h]
0x18008f5c1  movdqu  xmmword ptr [rbx], xmm0
0x18008f5c5  lea     rdx, [rbx+10h]
0x18008f5c9  mov     rcx, r14
0x18008f5cc  call    MinAsn1SignedDataGetContent
0x18008f5d1  test    eax, eax
0x18008f5d3  jg      short loc_18008F5E8
0x18008f5d5  mov     ebx, 0C0000428h
0x18008f5da  mov     [rsp+0F8h+var_C8], ebx
0x18008f5de  mov     edi, 40000h
0x18008f5e3  jmp     loc_18008FB6E
0x18008f5e8  mov     r12d, 1
0x18008f5ee  mov     [rsp+0F8h+var_AC], r12d
0x18008f5f3  cmp     dword ptr [r14+0A0h], 0
0x18008f5fb  jz      loc_18008F547
0x18008f601  lea     rcx, [r14+70h]
0x18008f605  mov     r13, [rsp+0F8h+var_C0]
0x18008f60a  mov     r8, r13
0x18008f60d  lea     rdx, [rsp+0F8h+var_A0]
0x18008f612  call    MinAsn1ParseSignedDataCertificatesEx
0x18008f617  test    eax, eax
0x18008f619  js      short loc_18008F649
0x18008f61b  mov     eax, [rsp+0F8h+var_A0]
0x18008f61f  test    eax, eax
0x18008f621  jz      short loc_18008F649
0x18008f623  lea     rdx, [r14+0D0h]
0x18008f62a  lea     rcx, [r14+0C0h]
0x18008f631  mov     r9, r13
0x18008f634  mov     r8d, eax
0x18008f637  call    I_MinCryptFindSignerCertificateByIssuerAndSerialNumber
0x18008f63c  mov     [rsp+0F8h+var_38], rax
0x18008f644  test    rax, rax
0x18008f647  jnz     short loc_18008F653
0x18008f649  mov     edi, 60000h
0x18008f64e  jmp     loc_18008FB65
0x18008f653  movups  xmm0, xmmword ptr [rax+10h]
0x18008f657  movdqu  xmmword ptr [rbx+20h], xmm0
0x18008f65c  lea     r15, [r14+0F0h]
0x18008f663  movups  xmm0, xmmword ptr [r15]
0x18008f667  movdqu  xmmword ptr [rbx+30h], xmm0
0x18008f66c  movups  xmm1, xmmword ptr [r14+120h]
0x18008f674  movdqu  xmmword ptr [rbx+40h], xmm1
0x18008f679  mov     [rsp+0F8h+var_D0], r15
0x18008f67e  mov     [rsp+0F8h+var_D8], rsi
0x18008f683  mov     r9, [rsp+0F8h+arg_20]
0x18008f68b  mov     r8, r13
0x18008f68e  mov     edx, [rsp+0F8h+var_A0]
0x18008f692  mov     rcx, rax
0x18008f695  call    MinCryptVerifyCertificateWithPolicy2
0x18008f69a  mov     ebx, eax
0x18008f69c  mov     [rsp+0F8h+var_C8], eax
0x18008f6a0  test    eax, eax
0x18008f6a2  jns     short loc_18008F6BC
0x18008f6a4  cmp     eax, 0C0000603h
0x18008f6a9  jnz     loc_18008FB72
0x18008f6af  mov     [rsp+0F8h+var_C8], 0
0x18008f6b7  mov     [rsp+0F8h+var_B8], r12d
0x18008f6bc  cmp     dword ptr [r15], 0
0x18008f6c0  jz      short loc_18008F6DB
0x18008f6c2  mov     rdx, rsi
0x18008f6c5  mov     rcx, r15
0x18008f6c8  call    I_MinCryptGetPlatformManifestBinaryIDAttribute
0x18008f6cd  mov     ebx, eax
0x18008f6cf  mov     [rsp+0F8h+var_C8], eax
0x18008f6d3  test    eax, eax
0x18008f6d5  js      loc_18008FB72
0x18008f6db  mov     rax, [rsp+0F8h+arg_20]
0x18008f6e3  test    rax, rax
0x18008f6e6  jz      short loc_18008F6EF
0x18008f6e8  mov     eax, [rax+4]
0x18008f6eb  test    al, 10h
0x18008f6ed  jnz     short loc_18008F767
0x18008f6ef  cmp     qword ptr [rsi+10h], 0
0x18008f6f4  jz      short loc_18008F754
0x18008f6f6  xor     ebx, ebx
0x18008f6f8  mov     [rsp+0F8h+var_68], ebx
0x18008f6ff  mov     rdx, [rsi+10h]
0x18008f703  cmp     ebx, [rdx+30h]
0x18008f706  jnb     short loc_18008F74D
0x18008f708  mov     eax, ebx
0x18008f70a  imul    r15, rax, 78h ; 'x'
0x18008f70e  mov     rdx, [rdx+28h]
0x18008f712  xor     r8d, r8d
0x18008f715  mov     edx, [rdx+r15]
0x18008f719  mov     ecx, 400000h
0x18008f71e  call    I_MinCryptIsHashAlgPossiblyWeak
0x18008f723  test    al, al
0x18008f725  jz      loc_18008F7BB
0x18008f72b  mov     rax, [rsi+10h]
0x18008f72f  mov     rcx, [rax+28h]
0x18008f733  add     rcx, r15
0x18008f736  call    MincryptIsWeakCertHashAllowed
0x18008f73b  test    al, al
0x18008f73d  jnz     short loc_18008F7BB
0x18008f73f  mov     eax, r12d
0x18008f742  mov     [rsp+0F8h+var_9C], eax
0x18008f746  mov     [rsp+0F8h+var_40], eax
0x18008f74d  lea     r15, [r14+0F0h]
0x18008f754  call    I_MinCryptIsWeakTimestampPolicySet
0x18008f759  mov     ecx, [rsp+0F8h+var_B0]
0x18008f75d  test    al, al
0x18008f75f  cmovnz  ecx, r12d
0x18008f763  mov     [rsp+0F8h+var_B0], ecx
0x18008f767  lea     rcx, [r14+0E0h]
0x18008f76e  call    MinCryptDecodeHashAlgorithmIdentifier
0x18008f773  mov     r13d, eax
0x18008f776  test    eax, eax
0x18008f778  jz      loc_18008F5D5
0x18008f77e  lea     rcx, [r14+100h]
0x18008f785  call    MinCryptDecodeHashAlgorithmIdentifier
0x18008f78a  mov     r12d, eax
0x18008f78d  cmp     [rsp+0F8h+var_AC], 0
0x18008f792  jz      short loc_18008F7C3
0x18008f794  lea     r9, [rsp+0F8h+var_50]
0x18008f79c  lea     r8, [rsp+0F8h+var_58]
0x18008f7a4  mov     edx, [r14+60h]
0x18008f7a8  mov     rcx, [r14+68h]
0x18008f7ac  call    MinAsn1ExtractContent
0x18008f7b1  test    eax, eax
0x18008f7b3  js      loc_18008F5D5
0x18008f7b9  jmp     short loc_18008F7E1
0x18008f7bb  add     ebx, r12d
0x18008f7be  jmp     loc_18008F6F8
0x18008f7c3  mov     eax, [rsp+0F8h+arg_18]
0x18008f7ca  mov     [rsp+0F8h+var_58], eax
0x18008f7d1  mov     rax, [rsp+0F8h+arg_10]
0x18008f7d9  mov     [rsp+0F8h+var_50], rax
0x18008f7e1  mov     r15d, [r15]
0x18008f7e4  mov     [rsp+0F8h+var_AC], r15d
0x18008f7e9  cmp     r12d, 8000h
0x18008f7f0  jnz     short loc_18008F814
0x18008f7f2  test    r15d, r15d
0x18008f7f5  jnz     short loc_18008F814
0x18008f7f7  mov     rcx, [rsp+0F8h+var_50]
0x18008f7ff  mov     [rsp+0F8h+var_48], rcx
0x18008f807  mov     r8d, [rsp+0F8h+var_58]
0x18008f80f  jmp     loc_18008F912
0x18008f814  lea     rax, [rsp+0F8h+var_B4]
0x18008f819  mov     [rsp+0F8h+var_D8], rax
0x18008f81e  lea     r9, [r14+130h]
0x18008f825  lea     r8, [rsp+0F8h+var_58]
0x18008f82d  mov     edx, 1
0x18008f832  mov     ecx, r13d
0x18008f835  call    MinCryptHashMemory
0x18008f83a  mov     ebx, eax
0x18008f83c  mov     [rsp+0F8h+var_C8], eax
0x18008f840  test    eax, eax
0x18008f842  js      loc_18008F5DE
0x18008f848  lea     rcx, [r14+130h]
0x18008f84f  mov     [rsp+0F8h+var_48], rcx
0x18008f857  test    r15d, r15d
0x18008f85a  jz      loc_18008F90D
0x18008f860  cmp     r12d, 8000h
0x18008f867  jz      short loc_18008F892
0x18008f869  lea     r9, [r14+0F0h]
0x18008f870  lea     r8, [rsp+0F8h+var_B4]
0x18008f875  mov     rdx, rcx
0x18008f878  mov     ecx, r13d
0x18008f87b  call    I_MinCryptVerifySignerAuthenticatedAttributes
0x18008f880  mov     [rsp+0F8h+var_C8], eax
0x18008f884  mov     r8d, [rsp+0F8h+var_B4]
0x18008f889  lea     rcx, [r14+130h]
0x18008f890  jmp     short loc_18008F902
0x18008f892  mov     rdx, r15
0x18008f895  mov     ecx, 102h
0x18008f89a  mov     r8d, 72634943h
0x18008f8a0  call    cs:__imp_ExAllocatePool2
0x18008f8a7  nop     dword ptr [rax+rax+00h]
0x18008f8ac  mov     r15, rax
0x18008f8af  mov     [rsp+0F8h+P], rax
0x18008f8b7  test    rax, rax
0x18008f8ba  jnz     short loc_18008F8CA
0x18008f8bc  mov     ebx, 0C0000017h
0x18008f8c1  mov     [rsp+0F8h+var_C8], ebx
0x18008f8c5  jmp     loc_18008FB72
0x18008f8ca  lea     rax, [r14+0F0h]
0x18008f8d1  mov     [rsp+0F8h+var_D8], rax
0x18008f8d6  lea     r9, [rsp+0F8h+var_AC]
0x18008f8db  mov     r8, r15
0x18008f8de  mov     edx, [rsp+0F8h+var_B4]
0x18008f8e2  lea     rcx, [r14+130h]
0x18008f8e9  call    I_MinCryptVerifyReturnSignerAuthenticatedAttributes
0x18008f8ee  mov     [rsp+0F8h+var_C8], eax
0x18008f8f2  mov     rcx, r15
0x18008f8f5  mov     [rsp+0F8h+var_48], rcx
0x18008f8fd  mov     r8d, [rsp+0F8h+var_AC]
0x18008f902  mov     ebx, eax
0x18008f904  test    eax, eax
0x18008f906  jns     short loc_18008F912
0x18008f908  jmp     loc_18008F5DE
0x18008f90d  mov     r8d, [rsp+0F8h+var_B4]
0x18008f912  mov     rax, [rsp+0F8h+var_38]
0x18008f91a  add     rax, 0B0h
0x18008f920  lea     r9, [r14+110h]
0x18008f927  mov     [rsp+0F8h+var_D0], 0
0x18008f930  mov     [rsp+0F8h+var_D8], rax
0x18008f935  mov     rdx, rcx
0x18008f938  mov     ecx, r13d
0x18008f93b  call    MinCryptVerifySignedHash2
0x18008f940  mov     ebx, eax
0x18008f942  mov     [rsp+0F8h+var_C8], eax
0x18008f946  test    eax, eax
0x18008f948  js      loc_18008F5DE
0x18008f94e  mov     r12d, [rsp+0F8h+var_B8]
0x18008f953  mov     r13d, [rsp+0F8h+var_9C]
0x18008f958  mov     r15d, [rsp+0F8h+var_B0]
0x18008f95d  test    r12d, r12d
0x18008f960  jnz     short loc_18008F97B
0x18008f962  test    r13d, r13d
0x18008f965  jnz     short loc_18008F97B
0x18008f967  test    r15d, r15d
0x18008f96a  jnz     short loc_18008F97B
0x18008f96c  cmp     [rsp+0F8h+arg_38], 0
0x18008f975  jz      loc_18008FB72
0x18008f97b  mov     [rsp+0F8h+var_B8], 0
  ... truncated ...
```
