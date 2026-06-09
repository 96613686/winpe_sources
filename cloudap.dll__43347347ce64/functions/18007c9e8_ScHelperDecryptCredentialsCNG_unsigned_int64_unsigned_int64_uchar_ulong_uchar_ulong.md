# ScHelperDecryptCredentialsCNG(unsigned __int64,unsigned __int64,uchar *,ulong,uchar *,ulong *)

- ea: `0x18007c9e8`
- end: `0x18007cf80`
- name: `?ScHelperDecryptCredentialsCNG@@YAJ_K0PEAEK1PEAK@Z`
- size: `1432`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned __int64@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18007db08`

## callees

- `0x18000a810`
- `0x180042410`
- `0x18004317c`
- `0x180067c9c`
- `0x18007c884`
- `0x18007c9e8`
- `0x18007d1a8`
- `0x18007e624`
- `0x18007f3f8`
- `0x18007f990`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18007cf06`
- `bcrypt!BCryptDestroyHash` at `0x18007cf06`
- `bcrypt!BCryptFinishHash` at `0x18007cc20`
- `bcrypt!BCryptFinishHash` at `0x18007cc20`
- `bcrypt!BCryptCreateHash` at `0x18007cbdc`
- `bcrypt!BCryptCreateHash` at `0x18007cbdc`
- `bcrypt!BCryptHashData` at `0x18007cbfe`
- `bcrypt!BCryptHashData` at `0x18007cbfe`
- `CRYPT32!CertCreateCertificateContext` at `0x18007caec`
- `CRYPT32!CertCreateCertificateContext` at `0x18007caec`
- `CRYPT32!CertFreeCertificateContext` at `0x18007cef7`
- `CRYPT32!CertFreeCertificateContext` at `0x18007cef7`
- `ncrypt!NCryptFreeObject` at `0x18007cf4f`
- `ncrypt!NCryptFreeObject` at `0x18007cf4f`
- `ncrypt!NCryptSignHash` at `0x18007cc98`
- `ncrypt!NCryptSignHash` at `0x18007cd6f`
- `ncrypt!NCryptSignHash` at `0x18007cc98`
- `ncrypt!NCryptSignHash` at `0x18007cd6f`
- `ncrypt!NCryptOpenKey` at `0x18007ce8f`
- `ncrypt!NCryptOpenKey` at `0x18007ce8f`

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
  unsigned __int64 v10; // rcx
  NTSTATUS IsNcryptRsaKey; // ebx
  unsigned int v12; // r14d
  unsigned int v13; // r15d
  BYTE *v14; // rdi
  UCHAR *p_pcbResult; // rsi
  unsigned __int8 *v16; // r12
  void *HelperSha256AlgHandle; // r14
  unsigned __int64 v18; // rbx
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  UCHAR *v23; // rax
  DWORD v24; // r14d
  const WCHAR **p_pPaddingInfo; // r13
  unsigned __int64 v26; // rbx
  __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  void *v29; // rsp
  void *v30; // rsp
  BYTE *v31; // rax
  unsigned int v32; // r15d
  __int64 v33; // rdx
  unsigned int v34; // eax
  BYTE *v35; // r8
  __int64 v36; // r14
  unsigned int v37; // r15d
  unsigned int v38; // eax
  BYTE *v39; // r12
  unsigned int v40; // r15d
  _BYTE v42[32]; // [rsp+0h] [rbp-60h] BYREF
  PUCHAR pbSecret; // [rsp+20h] [rbp-40h]
  ULONG dwFlags[2]; // [rsp+30h] [rbp-30h]
  DWORD pcbResult; // [rsp+60h] [rbp+0h] BYREF
  unsigned int v46; // [rsp+64h] [rbp+4h]
  int v47; // [rsp+68h] [rbp+8h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+70h] [rbp+10h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+78h] [rbp+18h] BYREF
  const WCHAR *pPaddingInfo; // [rsp+80h] [rbp+20h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+88h] [rbp+28h]
  NCRYPT_PROV_HANDLE hProvider; // [rsp+90h] [rbp+30h]
  PCCERT_CONTEXT pCertContext; // [rsp+98h] [rbp+38h]
  unsigned __int8 *v54; // [rsp+A0h] [rbp+40h]
  unsigned int *v55; // [rsp+A8h] [rbp+48h]
  struct _CRYPTOAPI_BLOB v56; // [rsp+B8h] [rbp+58h] BYREF
  unsigned __int8 v57[16]; // [rsp+D0h] [rbp+70h] BYREF
  __int128 v58; // [rsp+E0h] [rbp+80h]
  unsigned __int8 v59[16]; // [rsp+F0h] [rbp+90h] BYREF
  __int128 v60; // [rsp+100h] [rbp+A0h]
  UCHAR pbOutput[32]; // [rsp+110h] [rbp+B0h] BYREF
  UCHAR pbInput[64]; // [rsp+130h] [rbp+D0h] BYREF
  WCHAR pszKeyName[264]; // [rsp+170h] [rbp+110h] BYREF

  v54 = a5;
  hProvider = a2;
  hKey = (NCRYPT_KEY_HANDLE)a1;
  v55 = a6;
  *(&v56.cbData + 1) = 0;
  memset_0(pszKeyName, 0, 0x20Au);
  pPaddingInfo = 0;
  v47 = 0;
  pcbResult = 0;
  phHash = 0;
  memset_0(v57, 0, 0x40u);
  phKey = 0;
  if ( !a2 )
    return (unsigned int)-1073741023;
  if ( a4 < 4 )
    return (unsigned int)-1073741715;
  if ( *(_DWORD *)a3 )
    return (unsigned int)-1073741715;
  if ( a4 - 4 < 4 )
    return (unsigned int)-1073741715;
  v12 = *((_DWORD *)a3 + 1);
  v13 = a4 - 8;
  v46 = v12;
  if ( a4 - 8 < v12 )
    return (unsigned int)-1073741715;
  v14 = 0;
  p_pcbResult = 0;
  if ( KerberosCryptoPolicy::GenerateRandom(v10, pbInput) )
  {
    v16 = a3 + 8;
    pCertContext = CertCreateCertificateContext(0x10001u, a3 + 8, v12);
    if ( !pCertContext )
    {
      IsNcryptRsaKey = -1073741715;
      goto LABEL_61;
    }
    HelperSha256AlgHandle = I_ScHelperGetHelperSha256AlgHandle();
    if ( HelperSha256AlgHandle )
    {
      v18 = g_cbSha256HashObjectLength;
      if ( !g_cbSha256HashObjectLength
        || g_cbSha256HashObjectLength > (unsigned __int64)g_ulMaxStackAllocSize
        || (unsigned __int64)g_cbSha256HashObjectLength + g_ulAdditionalProbeSize + 8 < g_cbSha256HashObjectLength
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_74;
      }
      v19 = v18 + 23;
      if ( v18 + 23 <= v18 + 8 )
        v19 = 0xFFFFFFFFFFFFFF0LL;
      v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
      v21 = alloca(v20);
      v22 = alloca(v20);
      p_pcbResult = (UCHAR *)&pcbResult;
      if ( v42 == (_BYTE *)-96LL || (pcbResult = 1801679955, (p_pcbResult = (UCHAR *)&v47) == 0) )
      {
LABEL_74:
        if ( v18 + 8 >= v18 )
        {
          v23 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
          p_pcbResult = v23;
          if ( v23 )
          {
            *(_DWORD *)v23 = 1885431112;
            p_pcbResult = v23 + 8;
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
        IsNcryptRsaKey = ScHelperIsNcryptRsaKey(1, a1, &v47);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_60;
        if ( v47 )
        {
          v24 = 2;
          pPaddingInfo = L"SHA1";
          p_pPaddingInfo = &pPaddingInfo;
        }
        else
        {
          p_pPaddingInfo = 0;
          v24 = 0;
        }
        IsNcryptRsaKey = NCryptSignHash(hKey, p_pPaddingInfo, pbOutput, 0x20u, 0, 0, &pcbResult, v24);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_60;
        v26 = pcbResult;
        if ( !pcbResult
          || pcbResult > (unsigned __int64)g_ulMaxStackAllocSize
          || (unsigned __int64)pcbResult + g_ulAdditionalProbeSize + 8 < pcbResult
          || !(unsigned int)VerifyStackAvailable() )
        {
          goto LABEL_75;
        }
        v27 = v26 + 23;
        if ( v26 + 23 <= v26 + 8 )
          v27 = 0xFFFFFFFFFFFFFF0LL;
        v28 = v27 & 0xFFFFFFFFFFFFFFF0uLL;
        v29 = alloca(v28);
        v30 = alloca(v28);
        v14 = (BYTE *)&pcbResult;
        if ( v42 == (_BYTE *)-96LL || (pcbResult = 1801679955, (v14 = (BYTE *)&v47) == 0) )
        {
LABEL_75:
          if ( v26 + 8 >= v26 )
          {
            v31 = (BYTE *)((__int64 (*)(void))g_pfnAllocate)();
            v14 = v31;
            if ( v31 )
            {
              *(_DWORD *)v31 = 1885431112;
              v14 = v31 + 8;
            }
          }
        }
        if ( v14 )
        {
          IsNcryptRsaKey = NCryptSignHash(hKey, p_pPaddingInfo, pbOutput, 0x20u, v14, pcbResult, &pcbResult, v24);
          if ( IsNcryptRsaKey < 0 )
            goto LABEL_60;
          IsNcryptRsaKey = ScHelperVerifyMessage(pCertContext, L"SHA256", pbInput, 64, v14, pcbResult);
          if ( IsNcryptRsaKey < 0 )
            goto LABEL_60;
          v32 = v13 - v46;
          if ( v32 >= 0x40 )
          {
            *(_OWORD *)v57 = *(_OWORD *)&v16[v46];
            v58 = *(_OWORD *)&v16[v46 + 16];
            *(_OWORD *)v59 = *(_OWORD *)&v16[v46 + 32];
            v60 = *(_OWORD *)&v16[v46 + 48];
            if ( v32 - 64 >= 4 && v32 - 68 >= 4 )
            {
              v33 = *(unsigned int *)&v16[v46 + 68];
              v56.cbData = v33;
              if ( v32 - 72 >= (unsigned int)v33 )
              {
                v34 = v32 - 72 - v33;
                v35 = &v16[v46 + 72];
                v56.pbData = v35;
                if ( v34 >= 4 )
                {
                  v36 = *(unsigned int *)&v35[v33];
                  v37 = v34 - 4;
                  if ( v34 - 4 >= (unsigned int)v36 && (unsigned int)v36 <= 0x208 )
                  {
                    v38 = *(_DWORD *)&v16[v46 + 64];
                    v39 = &v35[v33 + 4];
                    v46 = v38;
                    memcpy_0(pszKeyName, v39, (unsigned int)v36);
                    IsNcryptRsaKey = NCryptOpenKey(hProvider, &phKey, pszKeyName, 0, 0x40u);
                    if ( IsNcryptRsaKey < 0 )
                      goto LABEL_60;
                    v40 = v37 - v36;
                    if ( v40 )
                    {
                      IsNcryptRsaKey = KerbDecryptCreds(
                                         hProvider,
                                         phKey,
                                         &v56,
                                         v46,
                                         (unsigned int)pbSecret,
                                         v57,
                                         dwFlags[0],
                                         v59,
                                         v40,
                                         &v39[v36],
                                         v55,
                                         v54);
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
  if ( v14 && *((_DWORD *)v14 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( phKey )
    NCryptFreeObject(phKey);
  return (unsigned int)IsNcryptRsaKey;
}

```

## disassembly

```asm
0x18007c9e8  push    rbp
0x18007c9ea  push    rsi
0x18007c9eb  push    rdi
0x18007c9ec  push    r12
0x18007c9ee  push    r13
0x18007c9f0  push    r14
0x18007c9f2  push    r15
0x18007c9f4  sub     rsp, 390h
0x18007c9fb  lea     rbp, [rsp+60h]
0x18007ca00  mov     [rbp+360h+arg_18], rbx
0x18007ca07  mov     rax, cs:__security_cookie
0x18007ca0e  xor     rax, rbp
0x18007ca11  mov     [rbp+360h+var_40], rax
0x18007ca18  mov     rax, [rbp+360h+arg_20]
0x18007ca1f  mov     rbx, r8
0x18007ca22  mov     [rbp+360h+var_320], rax
0x18007ca26  mov     rsi, rdx
0x18007ca29  mov     rax, [rbp+360h+arg_28]
0x18007ca30  mov     r13, rcx
0x18007ca33  mov     [rbp+360h+hProvider], rdx
0x18007ca37  xor     r12d, r12d
0x18007ca3a  mov     [rbp+360h+hKey], rcx
0x18007ca3e  xor     edx, edx; Val
0x18007ca40  mov     r8d, 20Ah; Size
0x18007ca46  mov     [rbp+360h+var_318], rax
0x18007ca4a  lea     rcx, [rbp+360h+pszKeyName]; void *
0x18007ca51  mov     dword ptr [rbp+360h+var_308+4], r12d
0x18007ca55  mov     edi, r9d
0x18007ca58  call    memset_0
0x18007ca5d  xor     edx, edx; Val
0x18007ca5f  mov     [rbp+360h+pPaddingInfo], r12
0x18007ca63  lea     r8d, [r12+40h]; Size
0x18007ca68  mov     [rbp+360h+var_358], r12d
0x18007ca6c  lea     rcx, [rbp+360h+var_2F0]; void *
0x18007ca70  mov     [rbp+360h+pcbResult], r12d
0x18007ca74  mov     [rbp+360h+phHash], r12
0x18007ca78  call    memset_0
0x18007ca7d  mov     [rbp+360h+phKey], r12
0x18007ca81  test    rsi, rsi
0x18007ca84  jnz     short loc_18007CA90
0x18007ca86  mov     ebx, 0C0000321h
0x18007ca8b  jmp     loc_18007CF55
0x18007ca90  cmp     edi, 4
0x18007ca93  jnb     short loc_18007CA9F
0x18007ca95  mov     ebx, 0C000006Dh
0x18007ca9a  jmp     loc_18007CF55
0x18007ca9f  cmp     [rbx], r12d
0x18007caa2  jnz     short loc_18007CA95
0x18007caa4  lea     eax, [rdi-4]
0x18007caa7  cmp     eax, 4
0x18007caaa  jb      short loc_18007CA95
0x18007caac  mov     r14d, [rbx+4]
0x18007cab0  lea     r15d, [rax-4]
0x18007cab4  mov     [rbp+360h+var_35C], r14d
0x18007cab8  cmp     r15d, r14d
0x18007cabb  jb      short loc_18007CA95
0x18007cabd  lea     rdx, [rbp+360h+pbInput]; void *
0x18007cac4  mov     rdi, r12
0x18007cac7  mov     rsi, r12
0x18007caca  call    ?GenerateRandom@KerberosCryptoPolicy@@SA_N_KPEAX@Z; KerberosCryptoPolicy::GenerateRandom(unsigned __int64,void *)
0x18007cacf  test    al, al
0x18007cad1  jnz     short loc_18007CADD
0x18007cad3  mov     ebx, 0C000009Ah
0x18007cad8  jmp     loc_18007CEFD
0x18007cadd  lea     r12, [rbx+8]
0x18007cae1  mov     r8d, r14d; cbCertEncoded
0x18007cae4  mov     rdx, r12; pbCertEncoded
0x18007cae7  mov     ecx, 10001h; dwCertEncodingType
0x18007caec  call    cs:__imp_CertCreateCertificateContext
0x18007caf2  mov     [rbp+360h+pCertContext], rax
0x18007caf6  test    rax, rax
0x18007caf9  jnz     short loc_18007CB05
0x18007cafb  mov     ebx, 0C000006Dh
0x18007cb00  jmp     loc_18007CEFD
0x18007cb05  call    ?I_ScHelperGetHelperSha256AlgHandle@@YAPEAXXZ; I_ScHelperGetHelperSha256AlgHandle(void)
0x18007cb0a  mov     r14, rax
0x18007cb0d  test    rax, rax
0x18007cb10  jnz     short loc_18007CB1C
0x18007cb12  mov     ebx, 0C000009Ah
0x18007cb17  jmp     loc_18007CEF3
0x18007cb1c  mov     ebx, cs:?g_cbSha256HashObjectLength@@3KA; ulong g_cbSha256HashObjectLength
0x18007cb22  test    rbx, rbx
0x18007cb25  jz      short loc_18007CB88
0x18007cb27  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18007cb2e  ja      short loc_18007CB88
0x18007cb30  mov     rcx, cs:g_ulAdditionalProbeSize
0x18007cb37  add     rcx, 8
0x18007cb3b  add     rcx, rbx
0x18007cb3e  cmp     rcx, rbx
0x18007cb41  jb      short loc_18007CB88
0x18007cb43  call    VerifyStackAvailable
0x18007cb48  test    eax, eax
0x18007cb4a  jz      short loc_18007CB88
0x18007cb4c  lea     rax, [rbx+8]
0x18007cb50  lea     rcx, [rax+0Fh]
0x18007cb54  cmp     rcx, rax
0x18007cb57  ja      short loc_18007CB63
0x18007cb59  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18007cb63  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18007cb67  mov     rax, rcx
0x18007cb6a  call    _alloca_probe
0x18007cb6f  sub     rsp, rcx
0x18007cb72  lea     rsi, [rsp+3C0h+pcbResult]
0x18007cb77  test    rsi, rsi
0x18007cb7a  jz      short loc_18007CB88
0x18007cb7c  mov     dword ptr [rsi], 6B637453h
0x18007cb82  add     rsi, 8
0x18007cb86  jnz     short loc_18007CBAF
0x18007cb88  lea     rcx, [rbx+8]
0x18007cb8c  cmp     rcx, rbx
0x18007cb8f  jb      short loc_18007CBAF
0x18007cb91  mov     rax, cs:g_pfnAllocate
0x18007cb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb9d  mov     rsi, rax
0x18007cba0  test    rax, rax
0x18007cba3  jz      short loc_18007CBAF
0x18007cba5  mov     dword ptr [rax], 70616548h
0x18007cbab  add     rsi, 8
0x18007cbaf  test    rsi, rsi
0x18007cbb2  jnz     short loc_18007CBBE
0x18007cbb4  mov     ebx, 0C0000017h
0x18007cbb9  jmp     loc_18007CEF3
0x18007cbbe  mov     r9d, cs:?g_cbSha256HashObjectLength@@3KA; cbHashObject
0x18007cbc5  lea     rdx, [rbp+360h+phHash]; phHash
0x18007cbc9  mov     [rsp+3C0h+dwFlags], edi; dwFlags
0x18007cbcd  mov     r8, rsi; pbHashObject
0x18007cbd0  mov     [rsp+3C0h+cbSecret], edi; cbSecret
0x18007cbd4  mov     rcx, r14; hAlgorithm
0x18007cbd7  mov     [rsp+3C0h+pbSecret], rdi; pbSecret
0x18007cbdc  call    cs:__imp_BCryptCreateHash
0x18007cbe2  mov     ebx, eax
0x18007cbe4  test    eax, eax
0x18007cbe6  js      loc_18007CEF3
0x18007cbec  mov     rcx, [rbp+360h+phHash]; hHash
0x18007cbf0  lea     rdx, [rbp+360h+pbInput]; pbInput
0x18007cbf7  xor     r9d, r9d; dwFlags
0x18007cbfa  lea     r8d, [r9+40h]; cbInput
0x18007cbfe  call    cs:__imp_BCryptHashData
0x18007cc04  mov     ebx, eax
0x18007cc06  test    eax, eax
0x18007cc08  js      loc_18007CEF3
0x18007cc0e  mov     rcx, [rbp+360h+phHash]; hHash
0x18007cc12  lea     rdx, [rbp+360h+pbOutput]; pbOutput
0x18007cc19  xor     r9d, r9d; dwFlags
0x18007cc1c  lea     r8d, [r9+20h]; cbOutput
0x18007cc20  call    cs:__imp_BCryptFinishHash
0x18007cc26  mov     ebx, eax
0x18007cc28  test    eax, eax
0x18007cc2a  js      loc_18007CEF3
0x18007cc30  lea     r8, [rbp+360h+var_358]; int *
0x18007cc34  mov     rdx, r13; void *
0x18007cc37  mov     ecx, 1; int
0x18007cc3c  call    ?ScHelperIsNcryptRsaKey@@YAJHPEAXPEAH@Z; ScHelperIsNcryptRsaKey(int,void *,int *)
0x18007cc41  mov     ebx, eax
0x18007cc43  test    eax, eax
0x18007cc45  js      loc_18007CEF3
0x18007cc4b  cmp     [rbp+360h+var_358], edi
0x18007cc4e  jz      short loc_18007CC67
0x18007cc50  lea     rax, aSha1; "SHA1"
0x18007cc57  mov     r14d, 2
0x18007cc5d  mov     [rbp+360h+pPaddingInfo], rax
0x18007cc61  lea     r13, [rbp+360h+pPaddingInfo]
0x18007cc65  jmp     short loc_18007CC6D
0x18007cc67  xor     r13d, r13d
0x18007cc6a  xor     r14d, r14d
0x18007cc6d  mov     rcx, [rbp+360h+hKey]; hKey
0x18007cc71  lea     rax, [rbp+360h+pcbResult]
0x18007cc75  mov     [rsp+3C0h+var_388], r14d; dwFlags
0x18007cc7a  lea     r8, [rbp+360h+pbOutput]; pbHashValue
0x18007cc81  mov     qword ptr [rsp+3C0h+dwFlags], rax; pcbResult
0x18007cc86  mov     r9d, 20h ; ' '; cbHashValue
0x18007cc8c  mov     [rsp+3C0h+cbSecret], edi; cbSignature
0x18007cc90  mov     rdx, r13; pPaddingInfo
0x18007cc93  mov     [rsp+3C0h+pbSecret], rdi; pbSignature
0x18007cc98  call    cs:__imp_NCryptSignHash
0x18007cc9e  mov     ebx, eax
0x18007cca0  test    eax, eax
0x18007cca2  js      loc_18007CEF3
0x18007cca8  mov     ebx, [rbp+360h+pcbResult]
0x18007ccab  test    rbx, rbx
0x18007ccae  jz      short loc_18007CD11
0x18007ccb0  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18007ccb7  ja      short loc_18007CD11
0x18007ccb9  mov     rcx, cs:g_ulAdditionalProbeSize
0x18007ccc0  add     rcx, 8
0x18007ccc4  add     rcx, rbx
0x18007ccc7  cmp     rcx, rbx
0x18007ccca  jb      short loc_18007CD11
0x18007cccc  call    VerifyStackAvailable
0x18007ccd1  test    eax, eax
0x18007ccd3  jz      short loc_18007CD11
0x18007ccd5  lea     rax, [rbx+8]
0x18007ccd9  lea     rcx, [rax+0Fh]
0x18007ccdd  cmp     rcx, rax
0x18007cce0  ja      short loc_18007CCEC
0x18007cce2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18007ccec  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18007ccf0  mov     rax, rcx
0x18007ccf3  call    _alloca_probe
0x18007ccf8  sub     rsp, rcx
0x18007ccfb  lea     rdi, [rsp+3C0h+pcbResult]
0x18007cd00  test    rdi, rdi
0x18007cd03  jz      short loc_18007CD11
0x18007cd05  mov     dword ptr [rdi], 6B637453h
0x18007cd0b  add     rdi, 8
0x18007cd0f  jnz     short loc_18007CD38
0x18007cd11  lea     rcx, [rbx+8]
0x18007cd15  cmp     rcx, rbx
0x18007cd18  jb      short loc_18007CD38
0x18007cd1a  mov     rax, cs:g_pfnAllocate
0x18007cd21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cd26  mov     rdi, rax
0x18007cd29  test    rax, rax
0x18007cd2c  jz      short loc_18007CD38
0x18007cd2e  mov     dword ptr [rax], 70616548h
0x18007cd34  add     rdi, 8
0x18007cd38  test    rdi, rdi
0x18007cd3b  jz      loc_18007CBB4
0x18007cd41  mov     rcx, [rbp+360h+hKey]; hKey
0x18007cd45  lea     rax, [rbp+360h+pcbResult]
0x18007cd49  mov     [rsp+3C0h+var_388], r14d; dwFlags
0x18007cd4e  lea     r8, [rbp+360h+pbOutput]; pbHashValue
0x18007cd55  mov     qword ptr [rsp+3C0h+dwFlags], rax; unsigned int
0x18007cd5a  mov     r9d, 20h ; ' '; cbHashValue
0x18007cd60  mov     eax, [rbp+360h+pcbResult]
0x18007cd63  mov     rdx, r13; pPaddingInfo
0x18007cd66  mov     [rsp+3C0h+cbSecret], eax; cbSignature
0x18007cd6a  mov     [rsp+3C0h+pbSecret], rdi; pbSignature
0x18007cd6f  call    cs:__imp_NCryptSignHash
0x18007cd75  mov     ebx, eax
0x18007cd77  test    eax, eax
0x18007cd79  js      loc_18007CEF3
0x18007cd7f  mov     eax, [rbp+360h+pcbResult]
0x18007cd82  lea     r8, [rbp+360h+pbInput]
0x18007cd89  mov     rcx, [rbp+360h+pCertContext]
0x18007cd8d  lea     rdx, pszAlgId; "SHA256"
0x18007cd94  mov     [rsp+3C0h+cbSecret], eax
0x18007cd98  mov     r9d, 40h ; '@'
0x18007cd9e  mov     [rsp+3C0h+pbSecret], rdi
0x18007cda3  call    ScHelperVerifyMessage
0x18007cda8  mov     ebx, eax
0x18007cdaa  test    eax, eax
0x18007cdac  js      loc_18007CEF3
0x18007cdb2  mov     eax, [rbp+360h+var_35C]
0x18007cdb5  sub     r15d, eax
0x18007cdb8  cmp     r15d, 40h ; '@'
0x18007cdbc  jb      loc_18007CEEE
0x18007cdc2  movups  xmm0, xmmword ptr [rax+r12]
0x18007cdc7  mov     ecx, eax
0x18007cdc9  movaps  xmmword ptr [rbp+360h+var_2F0], xmm0
0x18007cdcd  movups  xmm1, xmmword ptr [rax+r12+10h]
0x18007cdd3  movaps  [rbp+360h+var_2E0], xmm1
0x18007cdda  movups  xmm0, xmmword ptr [rax+r12+20h]
0x18007cde0  movaps  xmmword ptr [rbp+360h+var_2D0], xmm0
0x18007cde7  movups  xmm1, xmmword ptr [rax+r12+30h]
0x18007cded  lea     eax, [r15-40h]
0x18007cdf1  movaps  [rbp+360h+var_2C0], xmm1
0x18007cdf8  cmp     eax, 4
0x18007cdfb  jb      loc_18007CEEE
0x18007ce01  add     eax, 0FFFFFFFCh
0x18007ce04  cmp     eax, 4
0x18007ce07  jb      loc_18007CEEE
0x18007ce0d  mov     edx, [rcx+r12+44h]
0x18007ce12  add     eax, 0FFFFFFFCh
0x18007ce15  mov     [rbp+360h+var_308.cbData], edx
0x18007ce18  cmp     eax, edx
0x18007ce1a  jb      loc_18007CEEE
0x18007ce20  lea     r8, [rcx+48h]
0x18007ce24  sub     eax, edx
0x18007ce26  add     r8, r12
0x18007ce29  mov     [rbp+360h+var_308.pbData], r8
0x18007ce2d  cmp     eax, 4
0x18007ce30  jb      loc_18007CEEE
0x18007ce36  mov     r14d, [rdx+r8]
0x18007ce3a  lea     r15d, [rax-4]
0x18007ce3e  cmp     r15d, r14d
0x18007ce41  jb      loc_18007CEEE
0x18007ce47  cmp     r14d, 208h
0x18007ce4e  ja      loc_18007CEEE
0x18007ce54  mov     eax, [rcx+r12+40h]
0x18007ce59  lea     r12, [r8+4]
0x18007ce5d  add     r12, rdx
0x18007ce60  mov     [rbp+360h+var_35C], eax
0x18007ce63  mov     rdx, r12; Src
0x18007ce66  lea     rcx, [rbp+360h+pszKeyName]; void *
0x18007ce6d  mov     r8d, r14d; Size
0x18007ce70  call    memcpy_0
0x18007ce75  mov     rcx, [rbp+360h+hProvider]; hProvider
0x18007ce79  lea     r8, [rbp+360h+pszKeyName]; pszKeyName
0x18007ce80  xor     r9d, r9d; dwLegacyKeySpec
0x18007ce83  mov     dword ptr [rsp+3C0h+pbSecret], 40h ; '@'; unsigned int
0x18007ce8b  lea     rdx, [rbp+360h+phKey]; phKey
0x18007ce8f  call    cs:__imp_NCryptOpenKey
0x18007ce95  mov     ebx, eax
0x18007ce97  test    eax, eax
0x18007ce99  js      short loc_18007CEF3
0x18007ce9b  sub     r15d, r14d
0x18007ce9e  jz      short loc_18007CEEE
0x18007cea0  mov     rcx, [rbp+360h+var_320]
0x18007cea4  lea     rax, [r12+r14]
  ... truncated ...
```
