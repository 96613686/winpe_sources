# FCheckSCardCertAndCanOpenSilentContext(_CERT_CONTEXT const *,int,int,int *)

- ea: `0x18001489c`
- end: `0x180014df2`
- name: `?FCheckSCardCertAndCanOpenSilentContext@@YAHPEBU_CERT_CONTEXT@@HHPEAH@Z`
- size: `1366`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, int, int, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800136f0`
- `0x180020624`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18001489c`
- `0x18002d58c`
- `0x180069510`
- `0x18006d9ec`
- `0x1800791f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d49`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014b19`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014b19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800149dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800149dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a45`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180014ad2`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180014b4b`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180014ad2`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180014b4b`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180014d3f`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180014d3f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x180014c0a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x180014c0a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180014bb3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180014bb3`
- `ncrypt!NCryptOpenStorageProvider` at `0x180014c68`
- `ncrypt!NCryptOpenStorageProvider` at `0x180014c68`
- `ncrypt!NCryptGetProperty` at `0x180014cd6`
- `ncrypt!NCryptGetProperty` at `0x180014cd6`
- `ncrypt!NCryptFreeObject` at `0x180014a6c`
- `ncrypt!NCryptFreeObject` at `0x180014dd1`
- `ncrypt!NCryptFreeObject` at `0x180014a6c`
- `ncrypt!NCryptFreeObject` at `0x180014dd1`
- `CRYPTSP!CryptReleaseContext` at `0x180014dc2`
- `CRYPTSP!CryptReleaseContext` at `0x180014dc2`

## pseudocode

```c
__int64 __fastcall FCheckSCardCertAndCanOpenSilentContext(PCCERT_CONTEXT pCertContext, int a2, int a3, int *a4)
{
  HLOCAL v5; // rsi
  unsigned int v9; // r15d
  struct _EAPTLS_CONTROL_BLOCK *v10; // rcx
  int v11; // r14d
  unsigned int EKUUsage; // eax
  HLOCAL v13; // rdi
  int v14; // ebx
  struct _CTL_USAGE *v15; // r13
  __int64 i; // rbx
  struct _EAPTLS_CONTROL_BLOCK *v17; // rcx
  __int64 v18; // rdx
  DWORD LastError; // eax
  __int64 v20; // rdx
  struct _EAPTLS_CONTROL_BLOCK *v21; // rcx
  __int64 v22; // r9
  HLOCAL v23; // rax
  int v24; // edx
  int v25; // r8d
  DWORD Property; // eax
  DWORD pcbData; // [rsp+30h] [rbp-30h] BYREF
  BYTE pbData[4]; // [rsp+34h] [rbp-2Ch] BYREF
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+38h] [rbp-28h] BYREF
  DWORD pdwKeySpec; // [rsp+3Ch] [rbp-24h] BYREF
  DWORD pcbResult; // [rsp+40h] [rbp-20h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+48h] [rbp-18h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+50h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-8h] BYREF

  v5 = 0;
  hObject = 0;
  pdwKeySpec = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  *(_DWORD *)pbData = 0;
  pcbData = 0;
  v9 = 1;
  pcbResult = 0;
  phProvider = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  if ( a4 )
  {
    *a4 = 1;
    v10 = WPP_GLOBAL_Control;
  }
  hMem = 0;
  if ( v10 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)v10 + 2), 37, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
  v11 = g_eapTlsUseAllPurposeCert;
  if ( a2 )
    v11 = g_peapUseAllPurposeCert;
  EKUUsage = GetEKUUsage(pCertContext, (struct _CTL_USAGE **)&hMem);
  v13 = hMem;
  v14 = EKUUsage;
  if ( !EKUUsage )
    goto LABEL_19;
  v15 = 0;
  if ( EKUUsage != -2146762480 )
    goto LABEL_20;
  if ( a3 || !v11 || hMem && *(_DWORD *)hMem )
  {
    v14 = 0;
LABEL_19:
    v15 = (struct _CTL_USAGE *)hMem;
    v13 = 0;
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, 2148204816LL);
  v14 = -2143158015;
LABEL_20:
  LocalFree(v13);
  if ( v14 )
    goto LABEL_25;
  if ( !a3 && !(unsigned int)FCheckUsage(pCertContext, v15, 0, 0, a2) )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
LABEL_25:
    if ( !v15 )
      goto LABEL_28;
    goto LABEL_26;
  }
  for ( i = 0; (unsigned int)i < v15->cUsageIdentifier; i = (unsigned int)(i + 1) )
  {
    if ( !strcmp_0(v15->rgpszUsageIdentifier[i], "1.3.6.1.4.1.311.20.2.2") )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_26;
      v18 = 41;
      goto LABEL_38;
    }
  }
  if ( !CertGetCertificateContextProperty(pCertContext, 2u, 0, &pcbData) )
  {
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_26;
    LastError = GetLastError();
    v20 = 42;
    goto LABEL_42;
  }
  v23 = LocalAlloc(0x40u, pcbData);
  v5 = v23;
  if ( !v23 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      LastError = GetLastError();
      v20 = 43;
LABEL_42:
      v21 = WPP_GLOBAL_Control;
LABEL_43:
      v22 = LastError;
LABEL_44:
      WPP_SF_d(*((_QWORD *)v21 + 2), v20, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v22);
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  if ( CertGetCertificateContextProperty(pCertContext, 2u, v23, &pcbData) )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, v25, *(_QWORD *)v5, *((_QWORD *)v5 + 1), *((_DWORD *)v5 + 4));
    if ( CryptAcquireContextW(
           &hObject,
           *(LPCWSTR *)v5,
           *((LPCWSTR *)v5 + 1),
           *((_DWORD *)v5 + 4),
           *((_DWORD *)v5 + 5) & 0xFFFFFFBE | 0x40) )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      pdwKeySpec = 1;
      pfCallerFreeProvOrNCryptKey = 1;
      pcbData = 4;
      if ( !CryptGetProvParam(hObject, 3u, pbData, &pcbData, 0) )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          LastError = GetLastError();
          v20 = 47;
          goto LABEL_42;
        }
        goto LABEL_26;
      }
      v22 = *(unsigned int *)pbData;
      if ( (pbData[0] & 0xB) == 0xB )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v20 = 48;
          goto LABEL_44;
        }
        goto LABEL_26;
      }
LABEL_79:
      v9 = 0;
      goto LABEL_26;
    }
    LastError = NCryptOpenStorageProvider(&phProvider, *((LPCWSTR *)v5 + 1), 0);
    if ( LastError )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v20 = 49;
        goto LABEL_43;
      }
      goto LABEL_26;
    }
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
    Property = NCryptGetProperty(phProvider, L"Impl Type", pbData, 4u, &pcbResult, 0);
    if ( Property )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_26;
      v20 = 51;
    }
    else
    {
      v22 = *(unsigned int *)pbData;
      if ( (pbData[0] & 3) == 3 || (pbData[0] & 8) != 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v20 = 52;
          goto LABEL_44;
        }
        goto LABEL_26;
      }
      if ( CryptAcquireCertificatePrivateKey(
             pCertContext,
             0x40048u,
             0,
             &hObject,
             &pdwKeySpec,
             &pfCallerFreeProvOrNCryptKey) )
      {
        goto LABEL_79;
      }
      Property = GetLastError();
      if ( a4 && Property == -2146893790 )
      {
        *a4 = 0;
        v9 = 0;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v18 = 53;
LABEL_38:
          WPP_SF_(*((_QWORD *)v17 + 2), v18, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
          goto LABEL_26;
        }
        goto LABEL_26;
      }
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_26;
      v20 = 54;
    }
    v22 = Property;
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    LastError = GetLastError();
    v20 = 44;
    goto LABEL_42;
  }
LABEL_26:
  LocalFree(v15);
  if ( v5 )
    LocalFree(v5);
LABEL_28:
  if ( hObject && pfCallerFreeProvOrNCryptKey )
  {
    if ( pdwKeySpec == -1 )
      NCryptFreeObject(hObject);
    else
      CryptReleaseContext(hObject, 0);
  }
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return v9;
}

```

## disassembly

```asm
0x18001489c  mov     rax, rsp
0x18001489f  mov     [rax+18h], rbx
0x1800148a3  mov     [rax+20h], r9
0x1800148a7  mov     [rax+10h], edx
0x1800148aa  mov     [rax+8], rcx
0x1800148ae  push    rbp
0x1800148af  push    rsi
0x1800148b0  push    rdi
0x1800148b1  push    r12
0x1800148b3  push    r13
0x1800148b5  push    r14
0x1800148b7  push    r15
0x1800148b9  mov     rbp, rsp
0x1800148bc  sub     rsp, 60h
0x1800148c0  xor     r14d, r14d
0x1800148c3  mov     rbx, r9
0x1800148c6  mov     esi, r14d
0x1800148c9  mov     [rbp+hObject], r14
0x1800148cd  mov     [rbp+pdwKeySpec], r14d
0x1800148d1  mov     r12d, r8d
0x1800148d4  mov     [rbp+pfCallerFreeProvOrNCryptKey], r14d
0x1800148d8  mov     edi, edx
0x1800148da  mov     dword ptr [rbp+pbData], r14d
0x1800148de  mov     r13, rcx
0x1800148e1  mov     [rbp+pcbData], r14d
0x1800148e5  mov     r15d, 1
0x1800148eb  mov     [rbp+pcbResult], r14d
0x1800148ef  mov     [rbp+phProvider], r14
0x1800148f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800148fa  lea     rax, WPP_GLOBAL_Control
0x180014901  cmp     rcx, rax
0x180014904  jz      short loc_180014928
0x180014906  mov     rcx, [rcx+10h]
0x18001490a  lea     edx, [r15+26h]
0x18001490e  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180014915  call    WPP_SF_
0x18001491a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014921  lea     rax, WPP_GLOBAL_Control
0x180014928  test    rbx, rbx
0x18001492b  jz      short loc_180014937
0x18001492d  mov     [rbx], r15d
0x180014930  mov     rcx, cs:WPP_GLOBAL_Control
0x180014937  mov     [rbp+hMem], r14
0x18001493b  cmp     rcx, rax
0x18001493e  jz      short loc_180014955
0x180014940  mov     rcx, [rcx+10h]
0x180014944  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18001494b  mov     edx, 25h ; '%'
0x180014950  call    WPP_SF_
0x180014955  mov     r14d, cs:?g_eapTlsUseAllPurposeCert@@3HA; int g_eapTlsUseAllPurposeCert
0x18001495c  lea     rdx, [rbp+hMem]; struct _CTL_USAGE **
0x180014960  test    edi, edi
0x180014962  mov     rcx, r13; pCertContext
0x180014965  cmovnz  r14d, cs:?g_peapUseAllPurposeCert@@3HA; int g_peapUseAllPurposeCert
0x18001496d  call    ?GetEKUUsage@@YAKPEBU_CERT_CONTEXT@@PEAPEAU_CTL_USAGE@@@Z; GetEKUUsage(_CERT_CONTEXT const *,_CTL_USAGE * *)
0x180014972  mov     rdi, [rbp+hMem]
0x180014976  mov     ebx, eax
0x180014978  test    eax, eax
0x18001497a  jz      short loc_1800149CE
0x18001497c  xor     r13d, r13d
0x18001497f  mov     r9d, 800B0110h
0x180014985  cmp     eax, r9d
0x180014988  jnz     short loc_1800149D3
0x18001498a  test    r12d, r12d
0x18001498d  jnz     short loc_1800149CC
0x18001498f  test    r14d, r14d
0x180014992  jz      short loc_1800149CC
0x180014994  test    rdi, rdi
0x180014997  jz      short loc_18001499D
0x180014999  cmp     [rdi], esi
0x18001499b  jnz     short loc_1800149CC
0x18001499d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149a4  lea     r14, WPP_GLOBAL_Control
0x1800149ab  cmp     rcx, r14
0x1800149ae  jz      short loc_1800149C5
0x1800149b0  mov     rcx, [rcx+10h]
0x1800149b4  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x1800149bb  mov     edx, 26h ; '&'
0x1800149c0  call    WPP_SF_d
0x1800149c5  mov     ebx, 80420101h
0x1800149ca  jmp     short loc_1800149DA
0x1800149cc  xor     ebx, ebx
0x1800149ce  mov     r13, rdi
0x1800149d1  xor     edi, edi
0x1800149d3  lea     r14, WPP_GLOBAL_Control
0x1800149da  mov     rcx, rdi; hMem
0x1800149dd  call    cs:__imp_LocalFree
0x1800149e3  test    ebx, ebx
0x1800149e5  jnz     short loc_180014A2F
0x1800149e7  mov     rdi, [rbp+pCertContext]
0x1800149eb  test    r12d, r12d
0x1800149ee  jnz     loc_180014A77
0x1800149f4  mov     eax, [rbp+arg_8]
0x1800149f7  xor     r9d, r9d; int
0x1800149fa  xor     r8d, r8d; int
0x1800149fd  mov     [rsp+60h+dwFlags], eax; int
0x180014a01  mov     rdx, r13; struct _CTL_USAGE *
0x180014a04  mov     rcx, rdi; pCertContext
0x180014a07  call    ?FCheckUsage@@YAHPEBU_CERT_CONTEXT@@PEAU_CTL_USAGE@@HHH@Z; FCheckUsage(_CERT_CONTEXT const *,_CTL_USAGE *,int,int,int)
0x180014a0c  test    eax, eax
0x180014a0e  jnz     short loc_180014A77
0x180014a10  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a17  cmp     rcx, r14
0x180014a1a  jz      short loc_180014A2F
0x180014a1c  mov     rcx, [rcx+10h]
0x180014a20  lea     edx, [rbx+28h]
0x180014a23  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180014a2a  call    WPP_SF_
0x180014a2f  test    r13, r13
0x180014a32  jz      short loc_180014A4B
0x180014a34  mov     rcx, r13; hMem
0x180014a37  call    cs:__imp_LocalFree
0x180014a3d  test    rsi, rsi
0x180014a40  jz      short loc_180014A4B
0x180014a42  mov     rcx, rsi; hMem
0x180014a45  call    cs:__imp_LocalFree
0x180014a4b  mov     rcx, [rbp+hObject]; hProv
0x180014a4f  test    rcx, rcx
0x180014a52  jz      loc_180014DC8
0x180014a58  cmp     [rbp+pfCallerFreeProvOrNCryptKey], 0
0x180014a5c  jz      loc_180014DC8
0x180014a62  cmp     [rbp+pdwKeySpec], 0FFFFFFFFh
0x180014a66  jnz     loc_180014DC0
0x180014a6c  call    cs:__imp_NCryptFreeObject
0x180014a72  jmp     loc_180014DC8
0x180014a77  xor     ebx, ebx
0x180014a79  cmp     ebx, [r13+0]
0x180014a7d  jnb     short loc_180014AC2
0x180014a7f  mov     rcx, [r13+8]
0x180014a83  lea     rdx, Str2; "1.3.6.1.4.1.311.20.2.2"
0x180014a8a  mov     rcx, [rcx+rbx*8]; Str1
0x180014a8e  call    strcmp_0
0x180014a93  test    eax, eax
0x180014a95  jz      short loc_180014A9C
0x180014a97  add     ebx, r15d
0x180014a9a  jmp     short loc_180014A79
0x180014a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014aa3  cmp     rcx, r14
0x180014aa6  jz      short loc_180014A34
0x180014aa8  mov     edx, 29h ; ')'
0x180014aad  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180014ab4  mov     rcx, [rcx+10h]
0x180014ab8  call    WPP_SF_
0x180014abd  jmp     loc_180014A34
0x180014ac2  xor     r8d, r8d; pvData
0x180014ac5  lea     r9, [rbp+pcbData]; pcbData
0x180014ac9  mov     rcx, rdi; pCertContext
0x180014acc  lea     ebx, [r8+2]
0x180014ad0  mov     edx, ebx; dwPropId
0x180014ad2  call    cs:__imp_CertGetCertificateContextProperty
0x180014ad8  test    eax, eax
0x180014ada  jnz     short loc_180014B11
0x180014adc  cmp     cs:WPP_GLOBAL_Control, r14
0x180014ae3  jz      loc_180014A34
0x180014ae9  call    cs:__imp_GetLastError
0x180014aef  lea     edx, [rbx+28h]
0x180014af2  mov     rcx, cs:WPP_GLOBAL_Control
0x180014af9  mov     r9d, eax
0x180014afc  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180014b03  mov     rcx, [rcx+10h]
0x180014b07  call    WPP_SF_d
0x180014b0c  jmp     loc_180014A34
0x180014b11  mov     edx, [rbp+pcbData]; uBytes
0x180014b14  mov     ecx, 40h ; '@'; uFlags
0x180014b19  call    cs:__imp_LocalAlloc
0x180014b1f  mov     rsi, rax
0x180014b22  test    rax, rax
0x180014b25  jnz     short loc_180014B3F
0x180014b27  cmp     cs:WPP_GLOBAL_Control, r14
0x180014b2e  jz      loc_180014A34
0x180014b34  call    cs:__imp_GetLastError
0x180014b3a  lea     edx, [rsi+2Bh]
0x180014b3d  jmp     short loc_180014AF2
0x180014b3f  lea     r9, [rbp+pcbData]; pcbData
0x180014b43  mov     r8, rsi; pvData
0x180014b46  mov     edx, ebx; dwPropId
0x180014b48  mov     rcx, rdi; pCertContext
0x180014b4b  call    cs:__imp_CertGetCertificateContextProperty
0x180014b51  test    eax, eax
0x180014b53  jnz     short loc_180014B6F
0x180014b55  cmp     cs:WPP_GLOBAL_Control, r14
0x180014b5c  jz      loc_180014A34
0x180014b62  call    cs:__imp_GetLastError
0x180014b68  mov     edx, 2Ch ; ','
0x180014b6d  jmp     short loc_180014AF2
0x180014b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b76  cmp     rcx, r14
0x180014b79  jz      short loc_180014B97
0x180014b7b  mov     eax, [rsi+10h]
0x180014b7e  mov     r9, [rsi]
0x180014b81  mov     rcx, [rcx+10h]
0x180014b85  mov     [rsp+60h+var_38], eax
0x180014b89  mov     rax, [rsi+8]
0x180014b8d  mov     qword ptr [rsp+60h+dwFlags], rax
0x180014b92  call    WPP_SF_SSD
0x180014b97  mov     eax, [rsi+14h]
0x180014b9a  lea     rcx, [rbp+hObject]; phProv
0x180014b9e  mov     r9d, [rsi+10h]; dwProvType
0x180014ba2  and     eax, 0FFFFFFFEh
0x180014ba5  mov     r8, [rsi+8]; szProvider
0x180014ba9  or      eax, 40h
0x180014bac  mov     rdx, [rsi]; szContainer
0x180014baf  mov     [rsp+60h+dwFlags], eax; dwFlags
0x180014bb3  call    cs:__imp_CryptAcquireContextW
0x180014bb9  test    eax, eax
0x180014bbb  jz      loc_180014C5D
0x180014bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bc8  cmp     rcx, r14
0x180014bcb  jz      short loc_180014BE2
0x180014bcd  mov     rcx, [rcx+10h]
0x180014bd1  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180014bd8  mov     edx, 2Eh ; '.'
0x180014bdd  call    WPP_SF_
0x180014be2  mov     rcx, [rbp+hObject]; hProv
0x180014be6  lea     r9, [rbp+pcbData]; pdwDataLen
0x180014bea  lea     r8, [rbp+pbData]; pbData
0x180014bee  mov     [rbp+pdwKeySpec], r15d
0x180014bf2  mov     edx, 3; dwParam
0x180014bf7  mov     [rbp+pfCallerFreeProvOrNCryptKey], r15d
0x180014bfb  mov     [rbp+pcbData], 4
0x180014c02  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180014c0a  call    cs:__imp_CryptGetProvParam
0x180014c10  test    eax, eax
0x180014c12  jnz     short loc_180014C31
0x180014c14  cmp     cs:WPP_GLOBAL_Control, r14
0x180014c1b  jz      loc_180014A34
0x180014c21  call    cs:__imp_GetLastError
0x180014c27  mov     edx, 2Fh ; '/'
0x180014c2c  jmp     loc_180014AF2
0x180014c31  mov     r9d, dword ptr [rbp+pbData]
0x180014c35  mov     eax, r9d
0x180014c38  and     eax, 0Bh
0x180014c3b  cmp     al, 0Bh
0x180014c3d  jnz     loc_180014D9E
0x180014c43  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c4a  cmp     rcx, r14
0x180014c4d  jz      loc_180014A34
0x180014c53  mov     edx, 30h ; '0'
0x180014c58  jmp     loc_180014AFC
0x180014c5d  mov     rdx, [rsi+8]; pszProviderName
0x180014c61  lea     rcx, [rbp+phProvider]; phProvider
0x180014c65  xor     r8d, r8d; dwFlags
0x180014c68  call    cs:__imp_NCryptOpenStorageProvider
0x180014c6e  test    eax, eax
0x180014c70  jz      short loc_180014C8C
0x180014c72  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c79  cmp     rcx, r14
0x180014c7c  jz      loc_180014A34
0x180014c82  mov     edx, 31h ; '1'
0x180014c87  jmp     loc_180014AF9
0x180014c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c93  lea     rbx, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180014c9a  cmp     rcx, r14
0x180014c9d  jz      short loc_180014CB0
0x180014c9f  mov     rcx, [rcx+10h]
0x180014ca3  mov     edx, 32h ; '2'
0x180014ca8  mov     r8, rbx
0x180014cab  call    WPP_SF_
0x180014cb0  mov     rcx, [rbp+phProvider]; hObject
0x180014cb4  lea     rax, [rbp+pcbResult]
0x180014cb8  mov     [rsp+60h+var_38], 0; dwFlags
0x180014cc0  lea     r8, [rbp+pbData]; pbOutput
0x180014cc4  mov     r9d, 4; cbOutput
0x180014cca  mov     qword ptr [rsp+60h+dwFlags], rax; pcbResult
0x180014ccf  lea     rdx, aImplType; "Impl Type"
0x180014cd6  call    cs:__imp_NCryptGetProperty
0x180014cdc  test    eax, eax
0x180014cde  jz      short loc_180014D00
0x180014ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ce7  cmp     rcx, r14
0x180014cea  jz      loc_180014A34
0x180014cf0  mov     edx, 33h ; '3'
0x180014cf5  mov     r9d, eax
0x180014cf8  mov     r8, rbx
0x180014cfb  jmp     loc_180014B03
0x180014d00  mov     r9d, dword ptr [rbp+pbData]
0x180014d04  mov     eax, r9d
0x180014d07  and     eax, 3
0x180014d0a  cmp     al, 3
0x180014d0c  setnz   cl
0x180014d0f  test    r9b, 8
0x180014d13  setz    al
0x180014d16  test    al, cl
0x180014d18  jz      loc_180014DA6
0x180014d1e  lea     rax, [rbp+pfCallerFreeProvOrNCryptKey]
0x180014d22  xor     r8d, r8d; pvParameters
0x180014d25  mov     qword ptr [rsp+60h+var_38], rax; pfCallerFreeProvOrNCryptKey
0x180014d2a  lea     r9, [rbp+hObject]; phCryptProvOrNCryptKey
0x180014d2e  lea     rax, [rbp+pdwKeySpec]
0x180014d32  mov     edx, 40048h; dwFlags
0x180014d37  mov     rcx, rdi; pCert
0x180014d3a  mov     qword ptr [rsp+60h+dwFlags], rax; pdwKeySpec
0x180014d3f  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x180014d45  test    eax, eax
0x180014d47  jnz     short loc_180014D9E
0x180014d49  call    cs:__imp_GetLastError
0x180014d4f  mov     rcx, [rbp+arg_18]
0x180014d53  test    rcx, rcx
0x180014d56  jz      short loc_180014D84
0x180014d58  cmp     eax, 80090022h
  ... truncated ...
```
