# ScHelperDecryptCredentialsCNG(unsigned __int64,unsigned __int64,uchar *,ulong,uchar *,ulong *)

- ea: `0x1800d6780`
- end: `0x1800d6d1d`
- name: `?ScHelperDecryptCredentialsCNG@@YAJ_K0PEAEK1PEAK@Z`
- size: `1437`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned __int64@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800d71e8`

## callees

- `0x180007e80`
- `0x18002d328`
- `0x180034f04`
- `0x18006882c`
- `0x180068b20`
- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x1800d62c4`
- `0x1800d6780`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1800d6979`
- `bcrypt!BCryptCreateHash` at `0x1800d6979`
- `bcrypt!BCryptHashData` at `0x1800d699b`
- `bcrypt!BCryptHashData` at `0x1800d699b`
- `bcrypt!BCryptDestroyHash` at `0x1800d6ca3`
- `bcrypt!BCryptDestroyHash` at `0x1800d6ca3`
- `bcrypt!BCryptFinishHash` at `0x1800d69bd`
- `bcrypt!BCryptFinishHash` at `0x1800d69bd`
- `CRYPT32!CertCreateCertificateContext` at `0x1800d6889`
- `CRYPT32!CertCreateCertificateContext` at `0x1800d6889`
- `CRYPT32!CertFreeCertificateContext` at `0x1800d6c94`
- `CRYPT32!CertFreeCertificateContext` at `0x1800d6c94`
- `ncrypt!NCryptOpenKey` at `0x1800d6c2c`
- `ncrypt!NCryptOpenKey` at `0x1800d6c2c`
- `ncrypt!NCryptSignHash` at `0x1800d6a35`
- `ncrypt!NCryptSignHash` at `0x1800d6b0c`
- `ncrypt!NCryptSignHash` at `0x1800d6a35`
- `ncrypt!NCryptSignHash` at `0x1800d6b0c`
- `ncrypt!NCryptFreeObject` at `0x1800d6cec`
- `ncrypt!NCryptFreeObject` at `0x1800d6cec`

## pseudocode

```c
__int64 __fastcall ScHelperDecryptCredentialsCNG(
        void *a1,
        NCRYPT_PROV_HANDLE a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int *a6)
{
  int IsNcryptRsaKey; // ebx
  unsigned int v11; // r14d
  unsigned int v12; // r15d
  BYTE *v13; // rdi
  UCHAR *p_pcbResult; // rsi
  unsigned __int8 *v15; // r12
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  void *HelperSha256AlgHandle; // r14
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // rcx
  __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  void *v24; // rsp
  void *v25; // rsp
  UCHAR *v26; // rax
  DWORD v27; // r14d
  const WCHAR **p_pPaddingInfo; // r13
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  unsigned __int64 v32; // rbx
  unsigned __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned __int64 v35; // rcx
  void *v36; // rsp
  void *v37; // rsp
  BYTE *v38; // rax
  unsigned int v39; // r15d
  __int64 v40; // rdx
  unsigned int v41; // eax
  BYTE *v42; // r8
  __int64 v43; // r14
  unsigned int v44; // r15d
  unsigned int v45; // eax
  BYTE *v46; // r12
  unsigned int v47; // r15d
  _BYTE v49[32]; // [rsp+0h] [rbp-60h] BYREF
  PUCHAR pbSecret; // [rsp+20h] [rbp-40h]
  ULONG dwFlags[2]; // [rsp+30h] [rbp-30h]
  DWORD pcbResult; // [rsp+60h] [rbp+0h] BYREF
  unsigned int v53; // [rsp+64h] [rbp+4h]
  int v54; // [rsp+68h] [rbp+8h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+70h] [rbp+10h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+78h] [rbp+18h] BYREF
  const WCHAR *pPaddingInfo; // [rsp+80h] [rbp+20h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+88h] [rbp+28h]
  NCRYPT_PROV_HANDLE hProvider; // [rsp+90h] [rbp+30h]
  PCCERT_CONTEXT pCertContext; // [rsp+98h] [rbp+38h]
  unsigned __int8 *v61; // [rsp+A0h] [rbp+40h]
  unsigned int *v62; // [rsp+A8h] [rbp+48h]
  struct _CRYPTOAPI_BLOB v63; // [rsp+B8h] [rbp+58h] BYREF
  unsigned __int8 v64[16]; // [rsp+D0h] [rbp+70h] BYREF
  __int128 v65; // [rsp+E0h] [rbp+80h]
  unsigned __int8 v66[16]; // [rsp+F0h] [rbp+90h] BYREF
  __int128 v67; // [rsp+100h] [rbp+A0h]
  UCHAR pbOutput[32]; // [rsp+110h] [rbp+B0h] BYREF
  UCHAR pbInput[64]; // [rsp+130h] [rbp+D0h] BYREF
  WCHAR pszKeyName[264]; // [rsp+170h] [rbp+110h] BYREF

  v61 = a5;
  hProvider = a2;
  hKey = (NCRYPT_KEY_HANDLE)a1;
  v62 = a6;
  *(&v63.cbData + 1) = 0;
  memset_0(pszKeyName, 0, 0x20Au);
  pPaddingInfo = 0;
  v54 = 0;
  pcbResult = 0;
  phHash = 0;
  memset_0(v64, 0, 0x40u);
  phKey = 0;
  if ( !a2 )
    return (unsigned int)-1073741023;
  if ( a4 < 4 )
    return (unsigned int)-1073741715;
  if ( *(_DWORD *)a3 )
    return (unsigned int)-1073741715;
  if ( a4 - 4 < 4 )
    return (unsigned int)-1073741715;
  v11 = *((_DWORD *)a3 + 1);
  v12 = a4 - 8;
  v53 = v11;
  if ( a4 - 8 < v11 )
    return (unsigned int)-1073741715;
  v13 = 0;
  p_pcbResult = 0;
  if ( KerberosCryptoPolicy::GenerateRandom(0x40u, pbInput) )
  {
    v15 = a3 + 8;
    pCertContext = CertCreateCertificateContext(0x10001u, a3 + 8, v11);
    if ( !pCertContext )
    {
      IsNcryptRsaKey = -1073741715;
      goto LABEL_61;
    }
    HelperSha256AlgHandle = I_ScHelperGetHelperSha256AlgHandle();
    if ( HelperSha256AlgHandle )
    {
      v20 = g_cbSha256HashObjectLength;
      if ( !g_cbSha256HashObjectLength )
        goto LABEL_74;
      if ( g_cbSha256HashObjectLength > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_74;
      v21 = g_cbSha256HashObjectLength + g_ulAdditionalProbeSize + 8;
      if ( v21 < g_cbSha256HashObjectLength || !(unsigned int)VerifyStackAvailable(v21, v16, v17, v18) )
        goto LABEL_74;
      v22 = v20 + 23;
      if ( v20 + 23 <= v20 + 8 )
        v22 = 0xFFFFFFFFFFFFFF0LL;
      v23 = v22 & 0xFFFFFFFFFFFFFFF0uLL;
      v24 = alloca(v23);
      v25 = alloca(v23);
      p_pcbResult = (UCHAR *)&pcbResult;
      if ( v49 == (_BYTE *)-96LL || (pcbResult = 1801679955, (p_pcbResult = (UCHAR *)&v54) == 0) )
      {
LABEL_74:
        if ( v20 + 8 >= v20 )
        {
          v26 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
          p_pcbResult = v26;
          if ( v26 )
          {
            *(_DWORD *)v26 = 1885431112;
            p_pcbResult = v26 + 8;
          }
        }
      }
      if ( p_pcbResult )
      {
        IsNcryptRsaKey = BCryptCreateHash(
                           HelperSha256AlgHandle,
                           &phHash,
                           p_pcbResult,
                           g_cbSha256HashObjectLength,
                           0,
                           0,
                           0);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_60;
        IsNcryptRsaKey = BCryptHashData(phHash, pbInput, 0x40u, 0);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_60;
        IsNcryptRsaKey = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_60;
        IsNcryptRsaKey = ScHelperIsNcryptRsaKey(1, a1, &v54);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_60;
        if ( v54 )
        {
          v27 = 2;
          pPaddingInfo = L"SHA1";
          p_pPaddingInfo = &pPaddingInfo;
        }
        else
        {
          p_pPaddingInfo = 0;
          v27 = 0;
        }
        IsNcryptRsaKey = NCryptSignHash(hKey, p_pPaddingInfo, pbOutput, 0x20u, 0, 0, &pcbResult, v27);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_60;
        v32 = pcbResult;
        if ( !pcbResult )
          goto LABEL_75;
        if ( pcbResult > (unsigned __int64)g_ulMaxStackAllocSize )
          goto LABEL_75;
        v33 = pcbResult + g_ulAdditionalProbeSize + 8;
        if ( v33 < pcbResult || !(unsigned int)VerifyStackAvailable(v33, v29, v30, v31) )
          goto LABEL_75;
        v34 = v32 + 23;
        if ( v32 + 23 <= v32 + 8 )
          v34 = 0xFFFFFFFFFFFFFF0LL;
        v35 = v34 & 0xFFFFFFFFFFFFFFF0uLL;
        v36 = alloca(v35);
        v37 = alloca(v35);
        v13 = (BYTE *)&pcbResult;
        if ( v49 == (_BYTE *)-96LL || (pcbResult = 1801679955, (v13 = (BYTE *)&v54) == 0) )
        {
LABEL_75:
          if ( v32 + 8 >= v32 )
          {
            v38 = (BYTE *)((__int64 (*)(void))g_pfnAllocate)();
            v13 = v38;
            if ( v38 )
            {
              *(_DWORD *)v38 = 1885431112;
              v13 = v38 + 8;
            }
          }
        }
        if ( v13 )
        {
          IsNcryptRsaKey = NCryptSignHash(hKey, p_pPaddingInfo, pbOutput, 0x20u, v13, pcbResult, &pcbResult, v27);
          if ( IsNcryptRsaKey < 0 )
            goto LABEL_60;
          IsNcryptRsaKey = ScHelperVerifyMessage(
                             (__int64)pCertContext,
                             (__int64)L"SHA256",
                             pbInput,
                             0x40u,
                             v13,
                             pcbResult);
          if ( IsNcryptRsaKey < 0 )
            goto LABEL_60;
          v39 = v12 - v53;
          if ( v39 >= 0x40 )
          {
            *(_OWORD *)v64 = *(_OWORD *)&v15[v53];
            v65 = *(_OWORD *)&v15[v53 + 16];
            *(_OWORD *)v66 = *(_OWORD *)&v15[v53 + 32];
            v67 = *(_OWORD *)&v15[v53 + 48];
            if ( v39 - 64 >= 4 && v39 - 68 >= 4 )
            {
              v40 = *(unsigned int *)&v15[v53 + 68];
              v63.cbData = v40;
              if ( v39 - 72 >= (unsigned int)v40 )
              {
                v41 = v39 - 72 - v40;
                v42 = &v15[v53 + 72];
                v63.pbData = v42;
                if ( v41 >= 4 )
                {
                  v43 = *(unsigned int *)&v42[v40];
                  v44 = v41 - 4;
                  if ( v41 - 4 >= (unsigned int)v43 && (unsigned int)v43 <= 0x208 )
                  {
                    v45 = *(_DWORD *)&v15[v53 + 64];
                    v46 = &v42[v40 + 4];
                    v53 = v45;
                    memcpy_0(pszKeyName, v46, (unsigned int)v43);
                    IsNcryptRsaKey = NCryptOpenKey(hProvider, &phKey, pszKeyName, 0, 0x40u);
                    if ( IsNcryptRsaKey < 0 )
                      goto LABEL_60;
                    v47 = v44 - v43;
                    if ( v47 )
                    {
                      IsNcryptRsaKey = KerbDecryptCreds(
                                         hProvider,
                                         phKey,
                                         &v63,
                                         v53,
                                         (unsigned int)pbSecret,
                                         v64,
                                         dwFlags[0],
                                         v66,
                                         v47,
                                         &v46[v43],
                                         v62,
                                         v61);
                      goto LABEL_60;
                    }
                  }
                }
              }
            }
          }
          IsNcryptRsaKey = -1073741715;
          goto LABEL_60;
        }
      }
      IsNcryptRsaKey = -1073741801;
    }
    else
    {
      IsNcryptRsaKey = -1073741670;
    }
LABEL_60:
    CertFreeCertificateContext(pCertContext);
    goto LABEL_61;
  }
  IsNcryptRsaKey = -1073741670;
LABEL_61:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( p_pcbResult && *((_DWORD *)p_pcbResult - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v13 && *((_DWORD *)v13 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( phKey )
    NCryptFreeObject(phKey);
  return (unsigned int)IsNcryptRsaKey;
}

```

## disassembly

```asm
0x1800d6780  push    rbp
0x1800d6782  push    rsi
0x1800d6783  push    rdi
0x1800d6784  push    r12
0x1800d6786  push    r13
0x1800d6788  push    r14
0x1800d678a  push    r15
0x1800d678c  sub     rsp, 390h
0x1800d6793  lea     rbp, [rsp+60h]
0x1800d6798  mov     [rbp+360h+arg_18], rbx
0x1800d679f  mov     rax, cs:__security_cookie
0x1800d67a6  xor     rax, rbp
0x1800d67a9  mov     [rbp+360h+var_40], rax
0x1800d67b0  mov     rax, [rbp+360h+arg_20]
0x1800d67b7  mov     rbx, r8
0x1800d67ba  mov     [rbp+360h+var_320], rax
0x1800d67be  mov     rsi, rdx
0x1800d67c1  mov     rax, [rbp+360h+arg_28]
0x1800d67c8  mov     r13, rcx
0x1800d67cb  mov     [rbp+360h+hProvider], rdx
0x1800d67cf  xor     r12d, r12d
0x1800d67d2  mov     [rbp+360h+hKey], rcx
0x1800d67d6  xor     edx, edx; Val
0x1800d67d8  mov     r8d, 20Ah; Size
0x1800d67de  mov     [rbp+360h+var_318], rax
0x1800d67e2  lea     rcx, [rbp+360h+pszKeyName]; void *
0x1800d67e9  mov     dword ptr [rbp+360h+var_308+4], r12d
0x1800d67ed  mov     edi, r9d
0x1800d67f0  call    memset_0
0x1800d67f5  xor     edx, edx; Val
0x1800d67f7  mov     [rbp+360h+pPaddingInfo], r12
0x1800d67fb  lea     r8d, [r12+40h]; Size
0x1800d6800  mov     [rbp+360h+var_358], r12d
0x1800d6804  lea     rcx, [rbp+360h+var_2F0]; void *
0x1800d6808  mov     [rbp+360h+pcbResult], r12d
0x1800d680c  mov     [rbp+360h+phHash], r12
0x1800d6810  call    memset_0
0x1800d6815  mov     [rbp+360h+phKey], r12
0x1800d6819  test    rsi, rsi
0x1800d681c  jnz     short loc_1800D6828
0x1800d681e  mov     ebx, 0C0000321h
0x1800d6823  jmp     loc_1800D6CF2
0x1800d6828  cmp     edi, 4
0x1800d682b  jnb     short loc_1800D6837
0x1800d682d  mov     ebx, 0C000006Dh
0x1800d6832  jmp     loc_1800D6CF2
0x1800d6837  cmp     [rbx], r12d
0x1800d683a  jnz     short loc_1800D682D
0x1800d683c  lea     eax, [rdi-4]
0x1800d683f  cmp     eax, 4
0x1800d6842  jb      short loc_1800D682D
0x1800d6844  mov     r14d, [rbx+4]
0x1800d6848  lea     r15d, [rax-4]
0x1800d684c  mov     [rbp+360h+var_35C], r14d
0x1800d6850  cmp     r15d, r14d
0x1800d6853  jb      short loc_1800D682D
0x1800d6855  lea     rdx, [rbp+360h+pbInput]; void *
0x1800d685c  mov     ecx, 40h ; '@'; cbBuffer
0x1800d6861  mov     rdi, r12
0x1800d6864  mov     rsi, r12
0x1800d6867  call    ?GenerateRandom@KerberosCryptoPolicy@@SA_N_KPEAX@Z; KerberosCryptoPolicy::GenerateRandom(unsigned __int64,void *)
0x1800d686c  test    al, al
0x1800d686e  jnz     short loc_1800D687A
0x1800d6870  mov     ebx, 0C000009Ah
0x1800d6875  jmp     loc_1800D6C9A
0x1800d687a  lea     r12, [rbx+8]
0x1800d687e  mov     r8d, r14d; cbCertEncoded
0x1800d6881  mov     rdx, r12; pbCertEncoded
0x1800d6884  mov     ecx, 10001h; dwCertEncodingType
0x1800d6889  call    cs:__imp_CertCreateCertificateContext
0x1800d688f  mov     [rbp+360h+pCertContext], rax
0x1800d6893  test    rax, rax
0x1800d6896  jnz     short loc_1800D68A2
0x1800d6898  mov     ebx, 0C000006Dh
0x1800d689d  jmp     loc_1800D6C9A
0x1800d68a2  call    ?I_ScHelperGetHelperSha256AlgHandle@@YAPEAXXZ; I_ScHelperGetHelperSha256AlgHandle(void)
0x1800d68a7  mov     r14, rax
0x1800d68aa  test    rax, rax
0x1800d68ad  jnz     short loc_1800D68B9
0x1800d68af  mov     ebx, 0C000009Ah
0x1800d68b4  jmp     loc_1800D6C90
0x1800d68b9  mov     ebx, cs:?g_cbSha256HashObjectLength@@3KA; ulong g_cbSha256HashObjectLength
0x1800d68bf  test    rbx, rbx
0x1800d68c2  jz      short loc_1800D6925
0x1800d68c4  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800d68cb  ja      short loc_1800D6925
0x1800d68cd  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800d68d4  add     rcx, 8
0x1800d68d8  add     rcx, rbx
0x1800d68db  cmp     rcx, rbx
0x1800d68de  jb      short loc_1800D6925
0x1800d68e0  call    VerifyStackAvailable
0x1800d68e5  test    eax, eax
0x1800d68e7  jz      short loc_1800D6925
0x1800d68e9  lea     rax, [rbx+8]
0x1800d68ed  lea     rcx, [rax+0Fh]
0x1800d68f1  cmp     rcx, rax
0x1800d68f4  ja      short loc_1800D6900
0x1800d68f6  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800d6900  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800d6904  mov     rax, rcx
0x1800d6907  call    _alloca_probe
0x1800d690c  sub     rsp, rcx
0x1800d690f  lea     rsi, [rsp+3C0h+pcbResult]
0x1800d6914  test    rsi, rsi
0x1800d6917  jz      short loc_1800D6925
0x1800d6919  mov     dword ptr [rsi], 6B637453h
0x1800d691f  add     rsi, 8
0x1800d6923  jnz     short loc_1800D694C
0x1800d6925  lea     rcx, [rbx+8]
0x1800d6929  cmp     rcx, rbx
0x1800d692c  jb      short loc_1800D694C
0x1800d692e  mov     rax, cs:g_pfnAllocate
0x1800d6935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d693a  mov     rsi, rax
0x1800d693d  test    rax, rax
0x1800d6940  jz      short loc_1800D694C
0x1800d6942  mov     dword ptr [rax], 70616548h
0x1800d6948  add     rsi, 8
0x1800d694c  test    rsi, rsi
0x1800d694f  jnz     short loc_1800D695B
0x1800d6951  mov     ebx, 0C0000017h
0x1800d6956  jmp     loc_1800D6C90
0x1800d695b  mov     r9d, cs:?g_cbSha256HashObjectLength@@3KA; cbHashObject
0x1800d6962  lea     rdx, [rbp+360h+phHash]; phHash
0x1800d6966  mov     [rsp+3C0h+dwFlags], edi; dwFlags
0x1800d696a  mov     r8, rsi; pbHashObject
0x1800d696d  mov     [rsp+3C0h+cbSecret], edi; cbSecret
0x1800d6971  mov     rcx, r14; hAlgorithm
0x1800d6974  mov     [rsp+3C0h+pbSecret], rdi; pbSecret
0x1800d6979  call    cs:__imp_BCryptCreateHash
0x1800d697f  mov     ebx, eax
0x1800d6981  test    eax, eax
0x1800d6983  js      loc_1800D6C90
0x1800d6989  mov     rcx, [rbp+360h+phHash]; hHash
0x1800d698d  lea     rdx, [rbp+360h+pbInput]; pbInput
0x1800d6994  xor     r9d, r9d; dwFlags
0x1800d6997  lea     r8d, [r9+40h]; cbInput
0x1800d699b  call    cs:__imp_BCryptHashData
0x1800d69a1  mov     ebx, eax
0x1800d69a3  test    eax, eax
0x1800d69a5  js      loc_1800D6C90
0x1800d69ab  mov     rcx, [rbp+360h+phHash]; hHash
0x1800d69af  lea     rdx, [rbp+360h+pbOutput]; pbOutput
0x1800d69b6  xor     r9d, r9d; dwFlags
0x1800d69b9  lea     r8d, [r9+20h]; cbOutput
0x1800d69bd  call    cs:__imp_BCryptFinishHash
0x1800d69c3  mov     ebx, eax
0x1800d69c5  test    eax, eax
0x1800d69c7  js      loc_1800D6C90
0x1800d69cd  lea     r8, [rbp+360h+var_358]; int *
0x1800d69d1  mov     rdx, r13; void *
0x1800d69d4  mov     ecx, 1; int
0x1800d69d9  call    ?ScHelperIsNcryptRsaKey@@YAJHPEAXPEAH@Z; ScHelperIsNcryptRsaKey(int,void *,int *)
0x1800d69de  mov     ebx, eax
0x1800d69e0  test    eax, eax
0x1800d69e2  js      loc_1800D6C90
0x1800d69e8  cmp     [rbp+360h+var_358], edi
0x1800d69eb  jz      short loc_1800D6A04
0x1800d69ed  lea     rax, pszAlgId; "SHA1"
0x1800d69f4  mov     r14d, 2
0x1800d69fa  mov     [rbp+360h+pPaddingInfo], rax
0x1800d69fe  lea     r13, [rbp+360h+pPaddingInfo]
0x1800d6a02  jmp     short loc_1800D6A0A
0x1800d6a04  xor     r13d, r13d
0x1800d6a07  xor     r14d, r14d
0x1800d6a0a  mov     rcx, [rbp+360h+hKey]; hKey
0x1800d6a0e  lea     rax, [rbp+360h+pcbResult]
0x1800d6a12  mov     [rsp+3C0h+var_388], r14d; dwFlags
0x1800d6a17  lea     r8, [rbp+360h+pbOutput]; pbHashValue
0x1800d6a1e  mov     qword ptr [rsp+3C0h+dwFlags], rax; pcbResult
0x1800d6a23  mov     r9d, 20h ; ' '; cbHashValue
0x1800d6a29  mov     [rsp+3C0h+cbSecret], edi; cbSignature
0x1800d6a2d  mov     rdx, r13; pPaddingInfo
0x1800d6a30  mov     [rsp+3C0h+pbSecret], rdi; pbSignature
0x1800d6a35  call    cs:__imp_NCryptSignHash
0x1800d6a3b  mov     ebx, eax
0x1800d6a3d  test    eax, eax
0x1800d6a3f  js      loc_1800D6C90
0x1800d6a45  mov     ebx, [rbp+360h+pcbResult]
0x1800d6a48  test    rbx, rbx
0x1800d6a4b  jz      short loc_1800D6AAE
0x1800d6a4d  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800d6a54  ja      short loc_1800D6AAE
0x1800d6a56  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800d6a5d  add     rcx, 8
0x1800d6a61  add     rcx, rbx
0x1800d6a64  cmp     rcx, rbx
0x1800d6a67  jb      short loc_1800D6AAE
0x1800d6a69  call    VerifyStackAvailable
0x1800d6a6e  test    eax, eax
0x1800d6a70  jz      short loc_1800D6AAE
0x1800d6a72  lea     rax, [rbx+8]
0x1800d6a76  lea     rcx, [rax+0Fh]
0x1800d6a7a  cmp     rcx, rax
0x1800d6a7d  ja      short loc_1800D6A89
0x1800d6a7f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800d6a89  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800d6a8d  mov     rax, rcx
0x1800d6a90  call    _alloca_probe
0x1800d6a95  sub     rsp, rcx
0x1800d6a98  lea     rdi, [rsp+3C0h+pcbResult]
0x1800d6a9d  test    rdi, rdi
0x1800d6aa0  jz      short loc_1800D6AAE
0x1800d6aa2  mov     dword ptr [rdi], 6B637453h
0x1800d6aa8  add     rdi, 8
0x1800d6aac  jnz     short loc_1800D6AD5
0x1800d6aae  lea     rcx, [rbx+8]
0x1800d6ab2  cmp     rcx, rbx
0x1800d6ab5  jb      short loc_1800D6AD5
0x1800d6ab7  mov     rax, cs:g_pfnAllocate
0x1800d6abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6ac3  mov     rdi, rax
0x1800d6ac6  test    rax, rax
0x1800d6ac9  jz      short loc_1800D6AD5
0x1800d6acb  mov     dword ptr [rax], 70616548h
0x1800d6ad1  add     rdi, 8
0x1800d6ad5  test    rdi, rdi
0x1800d6ad8  jz      loc_1800D6951
0x1800d6ade  mov     rcx, [rbp+360h+hKey]; hKey
0x1800d6ae2  lea     rax, [rbp+360h+pcbResult]
0x1800d6ae6  mov     [rsp+3C0h+var_388], r14d; dwFlags
0x1800d6aeb  lea     r8, [rbp+360h+pbOutput]; pbHashValue
0x1800d6af2  mov     qword ptr [rsp+3C0h+dwFlags], rax; unsigned int
0x1800d6af7  mov     r9d, 20h ; ' '; cbHashValue
0x1800d6afd  mov     eax, [rbp+360h+pcbResult]
0x1800d6b00  mov     rdx, r13; pPaddingInfo
0x1800d6b03  mov     [rsp+3C0h+cbSecret], eax; cbSignature
0x1800d6b07  mov     [rsp+3C0h+pbSecret], rdi; pbSignature
0x1800d6b0c  call    cs:__imp_NCryptSignHash
0x1800d6b12  mov     ebx, eax
0x1800d6b14  test    eax, eax
0x1800d6b16  js      loc_1800D6C90
0x1800d6b1c  mov     eax, [rbp+360h+pcbResult]
0x1800d6b1f  lea     r8, [rbp+360h+pbInput]
0x1800d6b26  mov     rcx, [rbp+360h+pCertContext]
0x1800d6b2a  lea     rdx, aSha256; "SHA256"
0x1800d6b31  mov     [rsp+3C0h+cbSecret], eax
0x1800d6b35  mov     r9d, 40h ; '@'
0x1800d6b3b  mov     [rsp+3C0h+pbSecret], rdi
0x1800d6b40  call    ScHelperVerifyMessage
0x1800d6b45  mov     ebx, eax
0x1800d6b47  test    eax, eax
0x1800d6b49  js      loc_1800D6C90
0x1800d6b4f  mov     eax, [rbp+360h+var_35C]
0x1800d6b52  sub     r15d, eax
0x1800d6b55  cmp     r15d, 40h ; '@'
0x1800d6b59  jb      loc_1800D6C8B
0x1800d6b5f  movups  xmm0, xmmword ptr [rax+r12]
0x1800d6b64  mov     ecx, eax
0x1800d6b66  movaps  xmmword ptr [rbp+360h+var_2F0], xmm0
0x1800d6b6a  movups  xmm1, xmmword ptr [rax+r12+10h]
0x1800d6b70  movaps  [rbp+360h+var_2E0], xmm1
0x1800d6b77  movups  xmm0, xmmword ptr [rax+r12+20h]
0x1800d6b7d  movaps  xmmword ptr [rbp+360h+var_2D0], xmm0
0x1800d6b84  movups  xmm1, xmmword ptr [rax+r12+30h]
0x1800d6b8a  lea     eax, [r15-40h]
0x1800d6b8e  movaps  [rbp+360h+var_2C0], xmm1
0x1800d6b95  cmp     eax, 4
0x1800d6b98  jb      loc_1800D6C8B
0x1800d6b9e  add     eax, 0FFFFFFFCh
0x1800d6ba1  cmp     eax, 4
0x1800d6ba4  jb      loc_1800D6C8B
0x1800d6baa  mov     edx, [rcx+r12+44h]
0x1800d6baf  add     eax, 0FFFFFFFCh
0x1800d6bb2  mov     [rbp+360h+var_308.cbData], edx
0x1800d6bb5  cmp     eax, edx
0x1800d6bb7  jb      loc_1800D6C8B
0x1800d6bbd  lea     r8, [rcx+48h]
0x1800d6bc1  sub     eax, edx
0x1800d6bc3  add     r8, r12
0x1800d6bc6  mov     [rbp+360h+var_308.pbData], r8
0x1800d6bca  cmp     eax, 4
0x1800d6bcd  jb      loc_1800D6C8B
0x1800d6bd3  mov     r14d, [rdx+r8]
0x1800d6bd7  lea     r15d, [rax-4]
0x1800d6bdb  cmp     r15d, r14d
0x1800d6bde  jb      loc_1800D6C8B
0x1800d6be4  cmp     r14d, 208h
0x1800d6beb  ja      loc_1800D6C8B
0x1800d6bf1  mov     eax, [rcx+r12+40h]
0x1800d6bf6  lea     r12, [r8+4]
0x1800d6bfa  add     r12, rdx
0x1800d6bfd  mov     [rbp+360h+var_35C], eax
0x1800d6c00  mov     rdx, r12; Src
0x1800d6c03  lea     rcx, [rbp+360h+pszKeyName]; void *
0x1800d6c0a  mov     r8d, r14d; Size
0x1800d6c0d  call    memcpy_0
0x1800d6c12  mov     rcx, [rbp+360h+hProvider]; hProvider
0x1800d6c16  lea     r8, [rbp+360h+pszKeyName]; pszKeyName
0x1800d6c1d  xor     r9d, r9d; dwLegacyKeySpec
0x1800d6c20  mov     dword ptr [rsp+3C0h+pbSecret], 40h ; '@'; unsigned int
0x1800d6c28  lea     rdx, [rbp+360h+phKey]; phKey
0x1800d6c2c  call    cs:__imp_NCryptOpenKey
0x1800d6c32  mov     ebx, eax
0x1800d6c34  test    eax, eax
0x1800d6c36  js      short loc_1800D6C90
0x1800d6c38  sub     r15d, r14d
0x1800d6c3b  jz      short loc_1800D6C8B
0x1800d6c3d  mov     rcx, [rbp+360h+var_320]
  ... truncated ...
```
