# MinCryptVerifySignedDataWithPolicy

- ea: `0x18006af48`
- end: `0x18006b3e8`
- name: `MinCryptVerifySignedDataWithPolicy`
- size: `1184`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006c170`

## callees

- `0x18006af48`
- `0x18006b69c`
- `0x18006b804`
- `0x18006bb38`
- `0x18006bc0c`
- `0x18006bf80`
- `0x18006c7bc`
- `0x18006cbe8`
- `0x18006cfbc`
- `0x1800afb9c`
- `0x1801200d0`
- `0x180120ecc`
- `0x180191ea8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18006b2a3`
- `ntdll!RtlNtStatusToDosError` at `0x18006b2a3`
- `bcrypt!BCryptFinishHash` at `0x18006b280`
- `bcrypt!BCryptFinishHash` at `0x18006b280`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006b1bd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006b1bd`
- `bcrypt!BCryptGetProperty` at `0x18006b23c`
- `bcrypt!BCryptGetProperty` at `0x18006b23c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006b29b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006b29b`
- `bcrypt!BCryptCreateHash` at `0x18006b204`
- `bcrypt!BCryptCreateHash` at `0x18006b204`
- `bcrypt!BCryptHashData` at `0x18006b264`
- `bcrypt!BCryptHashData` at `0x18006b264`
- `bcrypt!BCryptDestroyHash` at `0x18006b28b`
- `bcrypt!BCryptDestroyHash` at `0x18006b35f`
- `bcrypt!BCryptDestroyHash` at `0x18006b28b`
- `bcrypt!BCryptDestroyHash` at `0x18006b35f`

## pseudocode

```c
__int64 __fastcall MinCryptVerifySignedDataWithPolicy(
        int a1,
        int a2,
        UCHAR *a3,
        ULONG a4,
        __int64 a5,
        void *a6,
        _DWORD *a7)
{
  __int64 v11; // rcx
  char v12; // r12
  __int64 v13; // xmm0_8
  int v14; // eax
  ULONG v15; // edi
  struct _CRYPTOAPI_BLOB *SignerCertificateByIssuerAndSerialNumber; // rax
  int v17; // r9d
  struct _CRYPTOAPI_BLOB *v18; // r13
  struct _CRYPTOAPI_BLOB v19; // xmm0
  unsigned __int8 *pbData; // rax
  unsigned int v21; // ebx
  BCRYPT_ALG_HANDLE v22; // rsi
  __int64 result; // rax
  unsigned int v24; // edi
  const WCHAR *v25; // rax
  NTSTATUS v26; // eax
  NTSTATUS Property; // ebx
  NTSTATUS v28; // ecx
  unsigned int v29; // ecx
  __int64 v30; // xmm0_8
  int v31; // eax
  ULONG pcbResult; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-B8h] BYREF
  ULONG cbHash; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v35; // [rsp+58h] [rbp-A8h] BYREF
  BCRYPT_ALG_HANDLE v36; // [rsp+70h] [rbp-90h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+78h] [rbp-88h] BYREF
  UCHAR pbHashObject[512]; // [rsp+80h] [rbp-80h] BYREF
  UCHAR pbOutput[4]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v40[16]; // [rsp+290h] [rbp+190h] BYREF
  int v41; // [rsp+2A0h] [rbp+1A0h]
  int v42; // [rsp+2B0h] [rbp+1B0h]
  __int64 v43; // [rsp+2B8h] [rbp+1B8h]
  int v44; // [rsp+2E0h] [rbp+1E0h]
  __int64 v45; // [rsp+2E4h] [rbp+1E4h]
  int v46; // [rsp+2ECh] [rbp+1ECh]
  unsigned int v47; // [rsp+2F0h] [rbp+1F0h]
  int v48; // [rsp+2F4h] [rbp+1F4h]
  __int64 v49; // [rsp+2F8h] [rbp+1F8h]
  _BYTE v50[48]; // [rsp+300h] [rbp+200h] BYREF
  int v51; // [rsp+330h] [rbp+230h]
  struct _CRYPTOAPI_BLOB v52; // [rsp+350h] [rbp+250h] BYREF
  struct _CRYPTOAPI_BLOB v53; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v54[16]; // [rsp+370h] [rbp+270h] BYREF
  struct _CRYPTOAPI_BLOB v55; // [rsp+380h] [rbp+280h] BYREF
  __int128 v56; // [rsp+3B0h] [rbp+2B0h]
  struct _CRYPTOAPI_BLOB v57[15]; // [rsp+3C0h] [rbp+2C0h] BYREF
  UCHAR pbHash[64]; // [rsp+D20h] [rbp+C20h] BYREF

  phAlgorithm = a6;
  cbHash = 0;
  v35 = 0;
  memset_0(a7, 0, 0x50u);
  pcbResult = 24;
  if ( (int)MinAsn1ExtractValues(a1, a2, (unsigned int)&pcbResult, (unsigned int)&qword_1801B7420, 19, (__int64)v40) <= 0
    || v41 <= 0 )
  {
    v21 = 327680;
LABEL_19:
    v22 = phAlgorithm;
    goto LABEL_20;
  }
  if ( v42 != 9 )
    goto LABEL_23;
  v11 = 0x7010DF78648862ALL - *(_QWORD *)v43;
  if ( *(_QWORD *)v43 == 0x7010DF78648862ALL )
    v11 = 2LL - *(unsigned __int8 *)(v43 + 8);
  if ( v11 )
  {
LABEL_23:
    v21 = 0x40000;
    goto LABEL_19;
  }
  if ( a4 && a3 )
  {
    v12 = 0;
    if ( v44 )
    {
      v13 = v45;
      *a7 = v44;
      v14 = v46;
      *(_QWORD *)(a7 + 1) = v13;
      a7[3] = v14;
    }
    *((_QWORD *)a7 + 3) = a3;
    a7[4] = a4;
  }
  else
  {
    if ( !v44 || (v29 = v47) == 0 )
    {
      v21 = 327680;
      LODWORD(result) = 232;
      goto LABEL_50;
    }
    v30 = v45;
    v12 = 1;
    *a7 = v44;
    v31 = v46;
    *(_QWORD *)(a7 + 1) = v30;
    a7[3] = v31;
    a7[5] = v48;
    *((_QWORD *)a7 + 3) = v49;
    a7[4] = v29;
  }
  if ( !v51 )
  {
    v21 = 327680;
LABEL_48:
    LODWORD(result) = -2146885618;
LABEL_50:
    v22 = phAlgorithm;
    return I_MinCryptBuildErrorPolicy((unsigned int)result, v22, v21);
  }
  pcbResult = 10;
  if ( (int)MinAsn1ParseSignedDataCertificatesEx(v50, &pcbResult, v57) <= 0
    || (v15 = pcbResult) == 0
    || (SignerCertificateByIssuerAndSerialNumber = I_MinCryptFindSignerCertificateByIssuerAndSerialNumber(
                                                     &v52,
                                                     &v53,
                                                     pcbResult,
                                                     (struct _CRYPTOAPI_BLOB (*const)[15])v57),
        (v18 = SignerCertificateByIssuerAndSerialNumber) == 0) )
  {
    v21 = 393216;
    goto LABEL_48;
  }
  v19 = SignerCertificateByIssuerAndSerialNumber[1];
  *((_QWORD *)a7 + 6) = *(_QWORD *)&v55.cbData;
  pbData = v55.pbData;
  *((struct _CRYPTOAPI_BLOB *)a7 + 2) = v19;
  v21 = 0;
  *((_QWORD *)a7 + 7) = pbData;
  *((_OWORD *)a7 + 4) = v56;
  v22 = phAlgorithm;
  LODWORD(result) = MinCryptVerifyCertificateWithPolicy((_DWORD)v18, v15, (unsigned int)v57, v17, (__int64)phAlgorithm);
  if ( (_DWORD)result )
    return I_MinCryptBuildErrorPolicy((unsigned int)result, v22, v21);
  v24 = MinCryptDecodeHashAlgorithmIdentifier(v54);
  if ( !v24 )
  {
    v21 = 0x40000;
    LODWORD(result) = -2146889726;
    return I_MinCryptBuildErrorPolicy((unsigned int)result, v22, v21);
  }
  if ( v12 )
  {
    if ( (int)MinAsn1ExtractContent(v49, v47, &v35, (char *)&v35 + 8) > 0 )
    {
      a3 = (UCHAR *)*((_QWORD *)&v35 + 1);
      a4 = v35;
      goto LABEL_25;
    }
    v21 = 0x40000;
LABEL_20:
    LODWORD(result) = -2146885619;
    return I_MinCryptBuildErrorPolicy((unsigned int)result, v22, v21);
  }
LABEL_25:
  v25 = CapiAlgIdToCngAlgId(v24);
  if ( !v25 )
  {
    LODWORD(result) = -2146893816;
LABEL_32:
    v21 = 0x40000;
    return I_MinCryptBuildErrorPolicy((unsigned int)result, v22, v21);
  }
  phAlgorithm = 0;
  v26 = BCryptOpenAlgorithmProvider(&phAlgorithm, v25, L"Microsoft Primitive Provider", 0);
  if ( v26 < 0 )
  {
    v28 = v26;
  }
  else
  {
    v36 = phAlgorithm;
    phHash = 0;
    *(_DWORD *)pbOutput = 0;
    pcbResult = 0;
    Property = BCryptCreateHash(phAlgorithm, &phHash, pbHashObject, 0x200u, 0, 0, 0);
    if ( Property >= 0 )
    {
      Property = BCryptGetProperty(phHash, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
      if ( Property < 0 )
      {
        BCryptDestroyHash(phHash);
      }
      else
      {
        cbHash = *(_DWORD *)pbOutput;
        BCryptHashData(phHash, a3, a4, 0);
        BCryptFinishHash(phHash, pbHash, *(ULONG *)pbOutput, 0);
        BCryptDestroyHash(phHash);
        Property = 0;
      }
    }
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    v28 = Property;
  }
  LODWORD(result) = RtlNtStatusToDosError(v28);
  if ( (_DWORD)result )
    goto LABEL_32;
  if ( v55.cbData )
  {
    LODWORD(result) = I_MinCryptVerifySignerAuthenticatedAttributes(v24, pbHash, &cbHash, &v55);
    if ( (_DWORD)result )
      goto LABEL_32;
  }
  result = MinCryptVerifySignedHash(v24, pbHash, cbHash, (__int64)&v18[11]);
  if ( (_DWORD)result )
    goto LABEL_32;
  return result;
}

```

## disassembly

```asm
0x18006af48  push    rbp
0x18006af4a  push    rbx
0x18006af4b  push    rsi
0x18006af4c  push    rdi
0x18006af4d  push    r12
0x18006af4f  push    r13
0x18006af51  push    r14
0x18006af53  push    r15
0x18006af55  lea     rbp, [rsp-0C78h]
0x18006af5d  sub     rsp, 0D78h
0x18006af64  mov     rax, cs:__security_cookie
0x18006af6b  xor     rax, rsp
0x18006af6e  mov     [rbp+0CB0h+var_50], rax
0x18006af75  mov     rax, [rbp+0CB0h+arg_28]
0x18006af7c  xor     r13d, r13d
0x18006af7f  mov     rsi, [rbp+0CB0h+arg_30]
0x18006af86  mov     r14, r8
0x18006af89  mov     edi, edx
0x18006af8b  mov     [rsp+0DB0h+phAlgorithm], rax
0x18006af90  mov     rbx, rcx
0x18006af93  mov     [rsp+0DB0h+cbHash], r13d
0x18006af98  xorps   xmm0, xmm0
0x18006af9b  lea     r8d, [r13+50h]; Size
0x18006af9f  xor     edx, edx; Val
0x18006afa1  mov     rcx, rsi; void *
0x18006afa4  mov     r15d, r9d
0x18006afa7  movups  [rsp+0DB0h+var_D58], xmm0
0x18006afac  call    memset_0
0x18006afb1  lea     rax, [rbp+0CB0h+var_B20]
0x18006afb8  mov     [rsp+0DB0h+pcbResult], 18h
0x18006afc0  mov     qword ptr [rsp+0DB0h+cbSecret], rax
0x18006afc5  lea     r9, qword_1801B7420
0x18006afcc  lea     r8, [rsp+0DB0h+pcbResult]
0x18006afd1  mov     dword ptr [rsp+0DB0h+pbSecret], 13h
0x18006afd9  mov     edx, edi
0x18006afdb  mov     rcx, rbx
0x18006afde  call    MinAsn1ExtractValues
0x18006afe3  test    eax, eax
0x18006afe5  jle     loc_18006B154
0x18006afeb  cmp     [rbp+0CB0h+var_B10], r13d
0x18006aff2  jle     loc_18006B154
0x18006aff8  cmp     [rbp+0CB0h+var_B00], 9
0x18006afff  jnz     loc_18006B183
0x18006b005  mov     rax, [rbp+0CB0h+var_AF8]
0x18006b00c  mov     rcx, cs:qword_1801CAD50
0x18006b013  sub     rcx, [rax]
0x18006b016  jnz     short loc_18006B026
0x18006b018  movzx   ecx, cs:byte_1801CAD58
0x18006b01f  movzx   eax, byte ptr [rax+8]
0x18006b023  sub     rcx, rax
0x18006b026  test    rcx, rcx
0x18006b029  jnz     loc_18006B183
0x18006b02f  test    r15d, r15d
0x18006b032  jz      loc_18006B2C6
0x18006b038  test    r14, r14
0x18006b03b  jz      loc_18006B2C6
0x18006b041  mov     eax, [rbp+0CB0h+var_AD0]
0x18006b047  mov     r12b, r13b
0x18006b04a  test    eax, eax
0x18006b04c  jz      short loc_18006B066
0x18006b04e  movsd   xmm0, [rbp+0CB0h+var_ACC]
0x18006b056  mov     [rsi], eax
0x18006b058  mov     eax, [rbp+0CB0h+var_AC4]
0x18006b05e  movsd   qword ptr [rsi+4], xmm0
0x18006b063  mov     [rsi+0Ch], eax
0x18006b066  mov     [rsi+18h], r14
0x18006b06a  mov     [rsi+10h], r15d
0x18006b06e  cmp     [rbp+0CB0h+var_A80], r13d
0x18006b075  jz      loc_18006B319
0x18006b07b  lea     r8, [rbp+0CB0h+var_9F0]
0x18006b082  mov     [rsp+0DB0h+pcbResult], 0Ah
0x18006b08a  lea     rdx, [rsp+0DB0h+pcbResult]
0x18006b08f  lea     rcx, [rbp+0CB0h+var_AB0]
0x18006b096  call    MinAsn1ParseSignedDataCertificatesEx
0x18006b09b  test    eax, eax
0x18006b09d  jle     loc_18006B3C8
0x18006b0a3  mov     edi, [rsp+0DB0h+pcbResult]
0x18006b0a7  test    edi, edi
0x18006b0a9  jz      loc_18006B3C8
0x18006b0af  lea     r9, [rbp+0CB0h+var_9F0]; struct _CRYPTOAPI_BLOB (*)[15]
0x18006b0b6  mov     r8d, edi; unsigned int
0x18006b0b9  lea     rdx, [rbp+0CB0h+var_A50]; struct _CRYPTOAPI_BLOB *
0x18006b0c0  lea     rcx, [rbp+0CB0h+var_A60]; struct _CRYPTOAPI_BLOB *
0x18006b0c7  call    ?I_MinCryptFindSignerCertificateByIssuerAndSerialNumber@@YAPEAU_CRYPTOAPI_BLOB@@PEAU1@0KQEAY0P@U1@@Z; I_MinCryptFindSignerCertificateByIssuerAndSerialNumber(_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *,ulong,_CRYPTOAPI_BLOB (* const)[15])
0x18006b0cc  mov     r13, rax
0x18006b0cf  test    rax, rax
0x18006b0d2  jz      loc_18006B3C8
0x18006b0d8  movups  xmm0, xmmword ptr [rax+10h]
0x18006b0dc  mov     rax, qword ptr [rbp+0CB0h+var_A30.cbData]
0x18006b0e3  lea     r8, [rbp+0CB0h+var_9F0]
0x18006b0ea  mov     [rsi+30h], rax
0x18006b0ee  mov     edx, edi
0x18006b0f0  mov     rax, [rbp+0CB0h+var_A30.pbData]
0x18006b0f7  mov     rcx, r13
0x18006b0fa  movdqu  xmmword ptr [rsi+20h], xmm0
0x18006b0ff  xor     ebx, ebx
0x18006b101  mov     [rsi+38h], rax
0x18006b105  movaps  xmm0, [rbp+0CB0h+var_A00]
0x18006b10c  movdqu  xmmword ptr [rsi+40h], xmm0
0x18006b111  mov     rsi, [rsp+0DB0h+phAlgorithm]
0x18006b116  mov     [rsp+0DB0h+pbSecret], rsi
0x18006b11b  call    MinCryptVerifyCertificateWithPolicy
0x18006b120  test    eax, eax
0x18006b122  jz      short loc_18006B165
0x18006b124  mov     r8d, ebx
0x18006b127  mov     rdx, rsi
0x18006b12a  mov     ecx, eax
0x18006b12c  call    I_MinCryptBuildErrorPolicy
0x18006b131  mov     rcx, [rbp+0CB0h+var_50]
0x18006b138  xor     rcx, rsp; StackCookie
0x18006b13b  call    __security_check_cookie
0x18006b140  add     rsp, 0D78h
0x18006b147  pop     r15
0x18006b149  pop     r14
0x18006b14b  pop     r13
0x18006b14d  pop     r12
0x18006b14f  pop     rdi
0x18006b150  pop     rsi
0x18006b151  pop     rbx
0x18006b152  pop     rbp
0x18006b153  retn
0x18006b154  mov     ebx, 50000h
0x18006b159  mov     rsi, [rsp+0DB0h+phAlgorithm]
0x18006b15e  mov     eax, 8009200Dh
0x18006b163  jmp     short loc_18006B124
0x18006b165  lea     rcx, [rbp+0CB0h+var_A40]
0x18006b16c  call    MinCryptDecodeHashAlgorithmIdentifier
0x18006b171  mov     edi, eax
0x18006b173  test    eax, eax
0x18006b175  jnz     short loc_18006B18A
0x18006b177  mov     ebx, 40000h
0x18006b17c  mov     eax, 80091002h
0x18006b181  jmp     short loc_18006B124
0x18006b183  mov     ebx, 40000h
0x18006b188  jmp     short loc_18006B159
0x18006b18a  test    r12b, r12b
0x18006b18d  jnz     loc_18006B323
0x18006b193  xor     r12d, r12d
0x18006b196  mov     ecx, edi; unsigned int
0x18006b198  call    ?CapiAlgIdToCngAlgId@@YAPEBGI@Z; CapiAlgIdToCngAlgId(uint)
0x18006b19d  test    rax, rax
0x18006b1a0  jz      loc_18006B2BB
0x18006b1a6  xor     r9d, r9d; dwFlags
0x18006b1a9  mov     [rsp+0DB0h+phAlgorithm], r12
0x18006b1ae  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18006b1b5  mov     rdx, rax; pszAlgId
0x18006b1b8  lea     rcx, [rsp+0DB0h+phAlgorithm]; phAlgorithm
0x18006b1bd  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18006b1c3  test    eax, eax
0x18006b1c5  js      loc_18006B2C2
0x18006b1cb  mov     rcx, [rsp+0DB0h+phAlgorithm]; hAlgorithm
0x18006b1d0  lea     r8, [rbp+0CB0h+pbHashObject]; pbHashObject
0x18006b1d4  mov     [rsp+0DB0h+dwFlags], r12d; dwFlags
0x18006b1d9  lea     rdx, [rsp+0DB0h+phHash]; phHash
0x18006b1de  mov     [rsp+0DB0h+cbSecret], r12d; cbSecret
0x18006b1e3  mov     r9d, 200h; cbHashObject
0x18006b1e9  mov     [rsp+0DB0h+var_D40], rcx
0x18006b1ee  mov     [rsp+0DB0h+pbSecret], r12; pbSecret
0x18006b1f3  mov     [rsp+0DB0h+phHash], r12
0x18006b1f8  mov     dword ptr [rbp+0CB0h+pbOutput], r12d
0x18006b1ff  mov     [rsp+0DB0h+pcbResult], r12d
0x18006b204  call    cs:__imp_BCryptCreateHash
0x18006b20a  mov     ebx, eax
0x18006b20c  test    eax, eax
0x18006b20e  js      loc_18006B294
0x18006b214  mov     rcx, [rsp+0DB0h+phHash]; hObject
0x18006b219  lea     rax, [rsp+0DB0h+pcbResult]
0x18006b21e  mov     [rsp+0DB0h+cbSecret], r12d; dwFlags
0x18006b223  lea     r8, [rbp+0CB0h+pbOutput]; pbOutput
0x18006b22a  mov     r9d, 4; cbOutput
0x18006b230  mov     [rsp+0DB0h+pbSecret], rax; pcbResult
0x18006b235  lea     rdx, pszProperty; "HashDigestLength"
0x18006b23c  call    cs:__imp_BCryptGetProperty
0x18006b242  mov     rcx, [rsp+0DB0h+phHash]; hHash
0x18006b247  mov     ebx, eax
0x18006b249  test    eax, eax
0x18006b24b  js      loc_18006B35F
0x18006b251  mov     eax, dword ptr [rbp+0CB0h+pbOutput]
0x18006b257  xor     r9d, r9d; dwFlags
0x18006b25a  mov     r8d, r15d; cbInput
0x18006b25d  mov     [rsp+0DB0h+cbHash], eax
0x18006b261  mov     rdx, r14; pbInput
0x18006b264  call    cs:__imp_BCryptHashData
0x18006b26a  mov     r8d, dword ptr [rbp+0CB0h+pbOutput]; cbOutput
0x18006b271  lea     rdx, [rbp+0CB0h+pbHash]; pbOutput
0x18006b278  mov     rcx, [rsp+0DB0h+phHash]; hHash
0x18006b27d  xor     r9d, r9d; dwFlags
0x18006b280  call    cs:__imp_BCryptFinishHash
0x18006b286  mov     rcx, [rsp+0DB0h+phHash]; hHash
0x18006b28b  call    cs:__imp_BCryptDestroyHash
0x18006b291  mov     ebx, r12d
0x18006b294  mov     rcx, [rsp+0DB0h+phAlgorithm]; hAlgorithm
0x18006b299  xor     edx, edx; dwFlags
0x18006b29b  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18006b2a1  mov     ecx, ebx; Status
0x18006b2a3  call    cs:__imp_RtlNtStatusToDosError
0x18006b2a9  test    eax, eax
0x18006b2ab  jz      loc_18006B36A
0x18006b2b1  mov     ebx, 40000h
0x18006b2b6  jmp     loc_18006B124
0x18006b2bb  mov     eax, 80090008h
0x18006b2c0  jmp     short loc_18006B2B1
0x18006b2c2  mov     ecx, eax
0x18006b2c4  jmp     short loc_18006B2A3
0x18006b2c6  mov     eax, [rbp+0CB0h+var_AD0]
0x18006b2cc  test    eax, eax
0x18006b2ce  jz      loc_18006B3D4
0x18006b2d4  mov     ecx, [rbp+0CB0h+var_AC0]
0x18006b2da  test    ecx, ecx
0x18006b2dc  jz      loc_18006B3D4
0x18006b2e2  movsd   xmm0, [rbp+0CB0h+var_ACC]
0x18006b2ea  mov     r12b, 1
0x18006b2ed  mov     [rsi], eax
0x18006b2ef  mov     eax, [rbp+0CB0h+var_AC4]
0x18006b2f5  movsd   qword ptr [rsi+4], xmm0
0x18006b2fa  mov     [rsi+0Ch], eax
0x18006b2fd  mov     eax, [rbp+0CB0h+var_ABC]
0x18006b303  mov     [rsi+14h], eax
0x18006b306  mov     rax, [rbp+0CB0h+var_AB8]
0x18006b30d  mov     [rsi+18h], rax
0x18006b311  mov     [rsi+10h], ecx
0x18006b314  jmp     loc_18006B06E
0x18006b319  mov     ebx, 50000h
0x18006b31e  jmp     loc_18006B3CD
0x18006b323  mov     edx, [rbp+0CB0h+var_AC0]
0x18006b329  lea     r9, [rsp+0DB0h+var_D58+8]
0x18006b32e  mov     rcx, [rbp+0CB0h+var_AB8]
0x18006b335  lea     r8, [rsp+0DB0h+var_D58]
0x18006b33a  call    MinAsn1ExtractContent
0x18006b33f  xor     r12d, r12d
0x18006b342  test    eax, eax
0x18006b344  jg      short loc_18006B350
0x18006b346  mov     ebx, 40000h
0x18006b34b  jmp     loc_18006B15E
0x18006b350  mov     r14, qword ptr [rsp+0DB0h+var_D58+8]
0x18006b355  mov     r15d, dword ptr [rsp+0DB0h+var_D58]
0x18006b35a  jmp     loc_18006B196
0x18006b35f  call    cs:__imp_BCryptDestroyHash
0x18006b365  jmp     loc_18006B294
0x18006b36a  cmp     [rbp+0CB0h+var_A30.cbData], r12d
0x18006b371  jz      short loc_18006B395
0x18006b373  lea     r9, [rbp+0CB0h+var_A30]; struct _CRYPTOAPI_BLOB *
0x18006b37a  mov     ecx, edi; unsigned int
0x18006b37c  lea     r8, [rsp+0DB0h+cbHash]; unsigned int *
0x18006b381  lea     rdx, [rbp+0CB0h+pbHash]; unsigned __int8 *
0x18006b388  call    ?I_MinCryptVerifySignerAuthenticatedAttributes@@YAJIQEAEPEAKPEAU_CRYPTOAPI_BLOB@@@Z; I_MinCryptVerifySignerAuthenticatedAttributes(uint,uchar * const,ulong *,_CRYPTOAPI_BLOB *)
0x18006b38d  test    eax, eax
0x18006b38f  jnz     loc_18006B2B1
0x18006b395  mov     r8d, [rsp+0DB0h+cbHash]; cbHash
0x18006b39a  lea     rax, [r13+0B0h]
0x18006b3a1  lea     r9, [rbp+0CB0h+var_A10]
0x18006b3a8  mov     [rsp+0DB0h+pbSecret], rax; __int64
0x18006b3ad  lea     rdx, [rbp+0CB0h+pbHash]; pbHash
0x18006b3b4  mov     ecx, edi; unsigned int
0x18006b3b6  call    MinCryptVerifySignedHash
0x18006b3bb  test    eax, eax
0x18006b3bd  jnz     loc_18006B2B1
0x18006b3c3  jmp     loc_18006B131
0x18006b3c8  mov     ebx, 60000h
0x18006b3cd  mov     eax, 8009200Eh
0x18006b3d2  jmp     short loc_18006B3DE
0x18006b3d4  mov     ebx, 50000h
0x18006b3d9  mov     eax, 0E8h
0x18006b3de  mov     rsi, [rsp+0DB0h+phAlgorithm]
0x18006b3e3  jmp     loc_18006B124
```
