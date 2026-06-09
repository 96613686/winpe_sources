# TLSGenerateClientCertificate

- ea: `0x18003a76c`
- end: `0x18003b240`
- name: `TLSGenerateClientCertificate`
- size: `2772`
- prototype: `__int64 __fastcall(HCRYPTPROV_LEGACY hCryptProv, unsigned int, char *, __int16, ULONGLONG *, _DWORD *, int, void *Src, _QWORD *)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180018510`
- `0x180027fb0`
- `0x18002c4e8`

## callees

- `0x180002d26`
- `0x18001ad48`
- `0x18001ad74`
- `0x18001ae3c`
- `0x18001b42c`
- `0x180022910`
- `0x1800397b8`
- `0x180039d70`
- `0x180039dac`
- `0x18003a76c`
- `0x180044bb0`

## import_xrefs

- `CRYPT32!CertSaveStore` at `0x18003af10`
- `CRYPT32!CertSaveStore` at `0x18003b186`
- `CRYPT32!CertSaveStore` at `0x18003af10`
- `CRYPT32!CertSaveStore` at `0x18003b186`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18003aa89`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18003ad20`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18003ae87`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18003aa89`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18003ad20`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18003ae87`
- `CRYPT32!CertOpenStore` at `0x18003a836`
- `CRYPT32!CertOpenStore` at `0x18003a87d`
- `CRYPT32!CertOpenStore` at `0x18003a836`
- `CRYPT32!CertOpenStore` at `0x18003a87d`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18003aa2f`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18003aa2f`
- `CRYPT32!CertCreateCertificateContext` at `0x18003accd`
- `CRYPT32!CertCreateCertificateContext` at `0x18003accd`
- `CRYPT32!CertFreeCertificateContext` at `0x18003a975`
- `CRYPT32!CertFreeCertificateContext` at `0x18003b1d2`
- `CRYPT32!CertFreeCertificateContext` at `0x18003b1eb`
- `CRYPT32!CertFreeCertificateContext` at `0x18003a975`
- `CRYPT32!CertFreeCertificateContext` at `0x18003b1d2`
- `CRYPT32!CertFreeCertificateContext` at `0x18003b1eb`
- `CRYPT32!CertCloseStore` at `0x18003b1ff`
- `CRYPT32!CertCloseStore` at `0x18003b21d`
- `CRYPT32!CertCloseStore` at `0x18003b1ff`
- `CRYPT32!CertCloseStore` at `0x18003b21d`
- `KERNEL32!GetLastError` at `0x18003a84c`
- `KERNEL32!GetLastError` at `0x18003a891`
- `KERNEL32!GetLastError` at `0x18003aae5`
- `KERNEL32!GetLastError` at `0x18003adef`
- `KERNEL32!GetLastError` at `0x18003af24`
- `KERNEL32!GetLastError` at `0x18003af3d`
- `KERNEL32!GetLastError` at `0x18003af9d`
- `KERNEL32!GetLastError` at `0x18003b0dd`
- `KERNEL32!GetLastError` at `0x18003a84c`
- `KERNEL32!GetLastError` at `0x18003a891`
- `KERNEL32!GetLastError` at `0x18003aae5`
- `KERNEL32!GetLastError` at `0x18003adef`
- `KERNEL32!GetLastError` at `0x18003af24`
- `KERNEL32!GetLastError` at `0x18003af3d`
- `KERNEL32!GetLastError` at `0x18003af9d`
- `KERNEL32!GetLastError` at `0x18003b0dd`
- `KERNEL32!LocalAlloc` at `0x18003b14e`
- `KERNEL32!LocalAlloc` at `0x18003b14e`
- `KERNEL32!LocalFree` at `0x18003ad3c`
- `KERNEL32!LocalFree` at `0x18003b1be`
- `KERNEL32!LocalFree` at `0x18003ad3c`
- `KERNEL32!LocalFree` at `0x18003b1be`
- `KERNEL32!ReleaseMutex` at `0x18003ac82`
- `KERNEL32!ReleaseMutex` at `0x18003ae60`
- `KERNEL32!ReleaseMutex` at `0x18003aeb7`
- `KERNEL32!ReleaseMutex` at `0x18003b025`
- `KERNEL32!ReleaseMutex` at `0x18003b073`
- `KERNEL32!ReleaseMutex` at `0x18003ac82`
- `KERNEL32!ReleaseMutex` at `0x18003ae60`
- `KERNEL32!ReleaseMutex` at `0x18003aeb7`
- `KERNEL32!ReleaseMutex` at `0x18003b025`
- `KERNEL32!ReleaseMutex` at `0x18003b073`

## pseudocode

```c
__int64 __fastcall TLSGenerateClientCertificate(
        HCRYPTPROV_LEGACY hCryptProv,
        unsigned int a2,
        char *a3,
        __int16 a4,
        ULONGLONG *a5,
        _DWORD *a6,
        int a7,
        void *Src,
        _QWORD *a9)
{
  struct _DbLicensedProduct *LastError; // rbx
  void *v10; // rdi
  const CERT_CONTEXT *CertificateContext; // r14
  struct _CRYPTOAPI_BLOB *p_Subject; // rsi
  unsigned int v14; // r13d
  HCERTSTORE v16; // r12
  PCCERT_CONTEXT v17; // rax
  unsigned int v18; // r15d
  _QWORD *v19; // r13
  PVOID *v20; // rcx
  unsigned __int16 *v21; // rax
  int v22; // edx
  int v23; // r8d
  const CERT_CONTEXT *IssuerCertContext; // rax
  const CERT_CONTEXT *v25; // rax
  PVOID v26; // rcx
  struct _CERT_PUBLIC_KEY_INFO *v27; // r9
  PCERT_INFO pCertInfo; // rdx
  PCERT_INFO v29; // rax
  HCERTSTORE v30; // rdx
  PVOID v31; // rcx
  const CERT_CONTEXT *v32; // rdx
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  DWORD v35; // eax
  unsigned int v36; // edx
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  struct _EVENT_DESCRIPTOR pbCertEncoded_8; // [rsp+48h] [rbp-C0h] BYREF
  DWORD cbCertEncoded[2]; // [rsp+58h] [rbp-B0h] BYREF
  HCERTSTORE pCertContext; // [rsp+60h] [rbp-A8h]
  struct _EVENT_DESCRIPTOR pCertContext_8; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v44; // [rsp+78h] [rbp-90h] BYREF
  __int128 v45; // [rsp+88h] [rbp-80h]
  _DWORD pvPara[2]; // [rsp+98h] [rbp-70h] BYREF
  void *v47; // [rsp+A0h] [rbp-68h]
  _BYTE v48[2736]; // [rsp+A8h] [rbp-60h] BYREF
  char *Srca; // [rsp+BA0h] [rbp+A98h]

  LODWORD(LastError) = 0;
  v10 = 0;
  pCertContext = 0;
  cbCertEncoded[0] = 0;
  *(_QWORD *)&pbCertEncoded_8.Id = 0;
  CertificateContext = 0;
  *(_QWORD *)&pCertContext_8.Id = 0;
  p_Subject = 0;
  v14 = a2;
  v44 = 0;
  v45 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids);
  pvPara[0] = a7;
  pvPara[1] = 0;
  v47 = Src;
  if ( Src )
  {
    pCertContext = CertOpenStore("PKCS7", 0x10001u, hCryptProv, 1u, pvPara);
    if ( !pCertContext )
    {
      LODWORD(LastError) = GetLastError();
      return (unsigned int)LastError;
    }
    v14 = a2;
  }
  v16 = CertOpenStore((LPCSTR)2, 0x10001u, hCryptProv, 1u, 0);
  if ( !v16 )
  {
    LastError = (struct _DbLicensedProduct *)GetLastError();
    pCertContext_8 = (struct _EVENT_DESCRIPTOR)TLS_E_GENERATECLIENTELICENSE;
    TLSLogEvent(&pCertContext_8, 0xC011000F, LastError);
    goto LABEL_144;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_2533973305>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_2533973305>::GetImpl'::`2'::impl) )
  {
    v17 = g_SelfSignCertContext;
    if ( !g_SelfSignCertContext )
    {
      LODWORD(LastError) = 4096;
      goto LABEL_143;
    }
    if ( RdlsSecretsCache::g_bHasHydraCert && g_hCaStore && a4 == 3 )
      v17 = RdlsSecretsCache::g_pLicenseCertContext;
    p_Subject = &v17->pCertInfo->Subject;
  }
  v18 = 0;
  if ( !v14 )
  {
LABEL_97:
    pbCertEncoded_8 = 0;
    if ( CertSaveStore(v16, 0x10001u, 2u, 2u, &pbCertEncoded_8, 0)
      || (LODWORD(LastError) = GetLastError(), (_DWORD)LastError == 234) )
    {
      pbCertEncoded_8.Keyword = (ULONGLONG)LocalAlloc(0x40u, *(unsigned int *)&pbCertEncoded_8.Id);
      if ( !pbCertEncoded_8.Keyword )
      {
        LODWORD(LastError) = 4117;
        goto LABEL_137;
      }
      if ( CertSaveStore(v16, 0x10001u, 2u, 2u, &pbCertEncoded_8, 0) )
      {
        *a5 = pbCertEncoded_8.Keyword;
        *a6 = *(_DWORD *)&pbCertEncoded_8.Id;
        goto LABEL_137;
      }
    }
    LastError = (struct _DbLicensedProduct *)GetLastError();
    v44 = TLS_E_GENERATECLIENTELICENSE;
    TLSLogEvent((struct _EVENT_DESCRIPTOR *)&v44, 0xC0110011, LastError);
LABEL_137:
    if ( v10 )
      LocalFree(v10);
    goto LABEL_139;
  }
  v19 = a9;
  Srca = a3;
  while ( 1 )
  {
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids, v18);
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( CertificateContext )
    {
      CertFreeCertificateContext(CertificateContext);
      v20 = (PVOID *)WPP_GLOBAL_Control;
      CertificateContext = 0;
    }
    if ( !a9 || !*v19 )
      break;
    v21 = (unsigned __int16 *)*v19;
    do
    {
      v22 = *(unsigned __int16 *)((char *)&g_szComputerName + (_QWORD)v21 - *v19);
      v23 = *v21 - v22;
      if ( v23 )
        break;
      ++v21;
    }
    while ( v22 );
    if ( !v23 )
      break;
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 0x20) != 0 )
      WPP_SF_S(v20[2], 14, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids, *v19);
    memcpy_0(v48, Srca, 0xA70u);
    IssuerCertContext = (const CERT_CONTEXT *)findIssuerCertContext(pCertContext, v48);
    CertificateContext = IssuerCertContext;
    if ( !IssuerCertContext )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        v38 = 15;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    v25 = CertDuplicateCertificateContext(IssuerCertContext);
    *(_QWORD *)&pCertContext_8.Id = v25;
    if ( !v25 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids);
      goto LABEL_97;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids);
      v25 = *(const CERT_CONTEXT **)&pCertContext_8.Id;
    }
    if ( !CertAddCertificateContextToStore(v16, v25, 4u, 0) )
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        v34 = 18;
        goto LABEL_103;
      }
      goto LABEL_104;
    }
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids);
    if ( !(unsigned int)TLSChainIssuerCertificate(v26, pCertContext, v16, *(_QWORD *)&pCertContext_8.Id) )
    {
      LastError = (struct _DbLicensedProduct *)GetLastError();
      pbCertEncoded_8 = (struct _EVENT_DESCRIPTOR)TLS_E_GENERATECLIENTELICENSE;
      TLSLogEvent(&pbCertEncoded_8, 0xC0110010, LastError);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids);
      goto LABEL_140;
    }
LABEL_96:
    Srca += 2672;
    ++v18;
    ++v19;
    if ( v18 >= a2 )
      goto LABEL_97;
  }
  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 0x20) != 0 )
    WPP_SF_(v20[2], 21, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids);
  LODWORD(v44) = 3;
  LastError = (struct _DbLicensedProduct *)&a3[2672 * v18];
  *((_QWORD *)&v44 + 1) = (char *)LastError + 1612;
  *(_QWORD *)&v45 = (char *)LastError + 2124;
  *((_QWORD *)&v45 + 1) = (char *)LastError + 32;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_2533973305>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_2533973305>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned int)WaitForMyTurnOrShutdown(g_AdminLock, 0xFFFFFFFFLL) )
    {
      if ( g_SelfSignCertContext )
      {
        if ( RdlsSecretsCache::g_pLicenseCertContext )
        {
          pCertInfo = g_SelfSignCertContext->pCertInfo;
          if ( pCertInfo )
          {
            v29 = RdlsSecretsCache::g_pLicenseCertContext->pCertInfo;
            if ( v29 )
            {
              if ( !RdlsSecretsCache::g_bHasHydraCert || !g_hCaStore || (p_Subject = &v29->Subject, a4 != 3) )
                p_Subject = &pCertInfo->Subject;
              goto LABEL_60;
            }
          }
        }
      }
      if ( g_AdminLock )
        ReleaseMutex(g_AdminLock);
      LODWORD(LastError) = 4096;
    }
    else
    {
      LODWORD(LastError) = -1073676261;
    }
LABEL_139:
    if ( CertificateContext )
      goto LABEL_140;
    goto LABEL_141;
  }
LABEL_60:
  LODWORD(LastError) = TLSGenerateSingleCertificate(
                         hCryptProv,
                         p_Subject,
                         (struct __LSClientCertRDN *)&v44,
                         v27,
                         LastError,
                         (unsigned __int8 **)&pbCertEncoded_8,
                         cbCertEncoded);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_2533973305>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_2533973305>::GetImpl'::`2'::impl)
    && g_AdminLock )
  {
    ReleaseMutex(g_AdminLock);
  }
  if ( (_DWORD)LastError )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids);
    v10 = *(void **)&pbCertEncoded_8.Id;
    goto LABEL_137;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids);
  v10 = *(void **)&pbCertEncoded_8.Id;
  CertificateContext = CertCreateCertificateContext(1u, *(const BYTE **)&pbCertEncoded_8.Id, cbCertEncoded[0]);
  if ( !CertificateContext )
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v38 = 24;
LABEL_125:
      WPP_SF_(v37[2], v38, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids);
    }
LABEL_126:
    v35 = GetLastError();
    v36 = -1072627708;
    goto LABEL_127;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids);
  if ( !CertAddCertificateContextToStore(v16, CertificateContext, 4u, 0) )
  {
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v34 = 26;
LABEL_103:
      WPP_SF_(v33[2], v34, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids);
    }
LABEL_104:
    v35 = GetLastError();
    v36 = -1072627696;
LABEL_127:
    LODWORD(LastError) = v35;
    pbCertEncoded_8 = (struct _EVENT_DESCRIPTOR)TLS_E_GENERATECLIENTELICENSE;
    TLSLogEvent(&pbCertEncoded_8, v36, v35);
    if ( (_DWORD)LastError )
      goto LABEL_137;
    goto LABEL_97;
  }
  if ( v10 )
    LocalFree(v10);
  v10 = 0;
  *(_QWORD *)&pbCertEncoded_8.Id = 0;
  if ( RdlsSecretsCache::g_bHasHydraCert )
  {
    v30 = g_hCaStore;
    if ( g_hCaStore )
    {
      if ( a4 == 3 )
      {
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids);
          v30 = g_hCaStore;
        }
        if ( (unsigned int)TLSChainIssuerCertificate(v31, v30, v16, CertificateContext) )
          goto LABEL_96;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids);
LABEL_84:
        LastError = (struct _DbLicensedProduct *)GetLastError();
        pbCertEncoded_8 = (struct _EVENT_DESCRIPTOR)TLS_E_GENERATECLIENTELICENSE;
        TLSLogEvent(&pbCertEncoded_8, 0xC0110010, LastError);
        goto LABEL_140;
      }
    }
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_2533973305>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_2533973305>::GetImpl'::`2'::impl) )
  {
    v32 = g_SelfSignCertContext;
LABEL_92:
    if ( CertAddCertificateContextToStore(v16, v32, 4u, 0) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_2533973305>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_2533973305>::GetImpl'::`2'::impl)
        && g_AdminLock )
      {
        ReleaseMutex(g_AdminLock);
      }
      goto LABEL_96;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_2533973305>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_2533973305>::GetImpl'::`2'::impl)
      && g_AdminLock )
    {
      ReleaseMutex(g_AdminLock);
    }
    goto LABEL_84;
  }
  if ( !(unsigned int)WaitForMyTurnOrShutdown(g_AdminLock, 0xFFFFFFFFLL) )
  {
    LODWORD(LastError) = -1073676261;
    goto LABEL_140;
  }
  v32 = g_SelfSignCertContext;
  if ( g_SelfSignCertContext )
    goto LABEL_92;
  if ( g_AdminLock )
    ReleaseMutex(g_AdminLock);
  LODWORD(LastError) = 4096;
LABEL_140:
  CertFreeCertificateContext(CertificateContext);
LABEL_141:
  if ( *(_QWORD *)&pCertContext_8.Id )
    CertFreeCertificateContext(*(PCCERT_CONTEXT *)&pCertContext_8.Id);
LABEL_143:
  CertCloseStore(v16, 1u);
LABEL_144:
  if ( pCertContext )
    CertCloseStore(pCertContext, 1u);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18003a76c  mov     rax, rsp
0x18003a76f  mov     [rax+20h], r9w
0x18003a774  mov     [rax+18h], r8
0x18003a778  mov     [rax+10h], edx
0x18003a77b  mov     [rax+8], rcx
0x18003a77f  push    rbp
0x18003a780  push    rbx
0x18003a781  push    rsi
0x18003a782  push    rdi
0x18003a783  push    r12
0x18003a785  push    r13
0x18003a787  push    r14
0x18003a789  push    r15
0x18003a78b  lea     rbp, [rax-0A58h]
0x18003a792  sub     rsp, 0B18h
0x18003a799  xor     ebx, ebx
0x18003a79b  xor     edi, edi
0x18003a79d  and     [rsp+0B50h+pCertContext], rbx
0x18003a7a2  xorps   xmm0, xmm0
0x18003a7a5  and     [rsp+0B50h+cbCertEncoded], ebx
0x18003a7a9  movzx   r15d, r9w
0x18003a7ad  xor     r9d, r9d
0x18003a7b0  mov     [rsp+0B50h+pbCertEncoded+8], rdi
0x18003a7b5  xor     r14d, r14d
0x18003a7b8  mov     [rsp+0B50h+pCertContext+8], r9
0x18003a7bd  xor     esi, esi
0x18003a7bf  mov     r13d, edx
0x18003a7c2  mov     r12, rcx
0x18003a7c5  movups  xmmword ptr [rsp+0B50h+var_AE8+8], xmm0
0x18003a7ca  movups  [rbp+0A50h+var_AD0], xmm0
0x18003a7ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a7d5  lea     rax, WPP_GLOBAL_Control
0x18003a7dc  cmp     rcx, rax
0x18003a7df  jz      short loc_18003A7FA
0x18003a7e1  test    byte ptr [rcx+1Ch], 20h
0x18003a7e5  jz      short loc_18003A7FA
0x18003a7e7  mov     rcx, [rcx+10h]
0x18003a7eb  lea     edx, [rbx+0Ch]
0x18003a7ee  lea     r8, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids
0x18003a7f5  call    WPP_SF_
0x18003a7fa  mov     eax, [rbp+0A50h+arg_30]
0x18003a800  mov     [rbp+0A50h+var_AC0], eax
0x18003a803  xor     eax, eax
0x18003a805  mov     [rbp+0A50h+var_ABC], eax
0x18003a808  mov     rax, [rbp+0A50h+Src]
0x18003a80f  mov     [rbp+0A50h+var_AB8], rax
0x18003a813  test    rax, rax
0x18003a816  jz      short loc_18003A866
0x18003a818  lea     rax, [rbp+0A50h+var_AC0]
0x18003a81c  mov     r9d, 1; dwFlags
0x18003a822  mov     r8, r12; hCryptProv
0x18003a825  mov     [rsp+0B50h+pvPara], rax; pvPara
0x18003a82a  mov     edx, 10001h; dwEncodingType
0x18003a82f  lea     rcx, szStoreProvider; "PKCS7"
0x18003a836  call    cs:__imp_CertOpenStore
0x18003a83d  nop     dword ptr [rax+rax+00h]
0x18003a842  mov     [rsp+0B50h+pCertContext], rax
0x18003a847  test    rax, rax
0x18003a84a  jnz     short loc_18003A85F
0x18003a84c  call    cs:__imp_GetLastError
0x18003a853  nop     dword ptr [rax+rax+00h]
0x18003a858  mov     ebx, eax
0x18003a85a  jmp     loc_18003B229
0x18003a85f  mov     r13d, [rbp+0A50h+arg_8]
0x18003a866  and     [rsp+0B50h+pvPara], rbx
0x18003a86b  mov     r9d, 1; dwFlags
0x18003a871  mov     r8, r12; hCryptProv
0x18003a874  mov     edx, 10001h; dwEncodingType
0x18003a879  lea     ecx, [r9+1]; lpszStoreProvider
0x18003a87d  call    cs:__imp_CertOpenStore
0x18003a884  nop     dword ptr [rax+rax+00h]
0x18003a889  mov     r12, rax
0x18003a88c  test    rax, rax
0x18003a88f  jnz     short loc_18003A8C3
0x18003a891  call    cs:__imp_GetLastError
0x18003a898  nop     dword ptr [rax+rax+00h]
0x18003a89d  movups  xmm0, cs:TLS_E_GENERATECLIENTELICENSE
0x18003a8a4  mov     r8d, eax
0x18003a8a7  lea     rcx, [rsp+0B50h+pCertContext+8]; struct _EVENT_DESCRIPTOR
0x18003a8ac  mov     edx, 0C011000Fh; unsigned int
0x18003a8b1  mov     ebx, eax
0x18003a8b3  movdqu  xmmword ptr [rsp+0B50h+pCertContext+8], xmm0
0x18003a8b9  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x18003a8be  jmp     loc_18003B20B
0x18003a8c3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_2533973305@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_2533973305@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2533973305> `wil::Feature<__WilFeatureTraits_Feature_2533973305>::GetImpl(void)'::`2'::impl
0x18003a8ca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_2533973305@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2533973305>::__private_IsEnabled(void)
0x18003a8cf  mov     ecx, 3
0x18003a8d4  test    al, al
0x18003a8d6  jnz     short loc_18003A914
0x18003a8d8  mov     rax, cs:?g_SelfSignCertContext@@3PEBU_CERT_CONTEXT@@EB; _CERT_CONTEXT const * const g_SelfSignCertContext
0x18003a8df  test    rax, rax
0x18003a8e2  jnz     short loc_18003A8EE
0x18003a8e4  mov     ebx, 1000h
0x18003a8e9  jmp     loc_18003B1F7
0x18003a8ee  cmp     cs:?g_bHasHydraCert@RdlsSecretsCache@@2HA, ebx; int RdlsSecretsCache::g_bHasHydraCert
0x18003a8f4  jz      short loc_18003A90C
0x18003a8f6  cmp     cs:?g_hCaStore@@3PEAXEA, rbx; void * g_hCaStore
0x18003a8fd  jz      short loc_18003A90C
0x18003a8ff  cmp     r15w, cx
0x18003a903  jnz     short loc_18003A90C
0x18003a905  mov     rax, cs:?g_pLicenseCertContext@RdlsSecretsCache@@2PEBU_CERT_CONTEXT@@EB; _CERT_CONTEXT const * const RdlsSecretsCache::g_pLicenseCertContext
0x18003a90c  mov     rsi, [rax+18h]
0x18003a910  add     rsi, 50h ; 'P'
0x18003a914  xor     r15d, r15d
0x18003a917  test    r13d, r13d
0x18003a91a  jz      loc_18003AEE2
0x18003a920  mov     rax, [rbp+0A50h+arg_10]
0x18003a927  mov     r13, [rbp+0A50h+arg_40]
0x18003a92e  mov     [rbp+0A50h+Src], rax
0x18003a935  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a93c  lea     rdx, WPP_GLOBAL_Control
0x18003a943  cmp     rcx, rdx
0x18003a946  jz      short loc_18003A96D
0x18003a948  test    byte ptr [rcx+1Ch], 20h
0x18003a94c  jz      short loc_18003A96D
0x18003a94e  mov     rcx, [rcx+10h]
0x18003a952  lea     r8, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids
0x18003a959  mov     edx, 0Dh
0x18003a95e  mov     r9d, r15d
0x18003a961  call    WPP_SF_D
0x18003a966  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a96d  test    r14, r14
0x18003a970  jz      short loc_18003A98B
0x18003a972  mov     rcx, r14; pCertContext
0x18003a975  call    cs:__imp_CertFreeCertificateContext
0x18003a97c  nop     dword ptr [rax+rax+00h]
0x18003a981  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a988  xor     r14d, r14d
0x18003a98b  cmp     [rbp+0A50h+arg_40], 0
0x18003a993  jz      loc_18003AB4D
0x18003a999  cmp     qword ptr [r13+0], 0
0x18003a99e  jz      loc_18003AB4D
0x18003a9a4  mov     rax, [r13+0]
0x18003a9a8  lea     r9, ?g_szComputerName@@3PAGA; ushort near * g_szComputerName
0x18003a9af  sub     r9, rax
0x18003a9b2  movzx   r8d, word ptr [rax]
0x18003a9b6  movzx   edx, word ptr [rax+r9]
0x18003a9bb  sub     r8d, edx
0x18003a9be  jnz     short loc_18003A9C8
0x18003a9c0  add     rax, 2
0x18003a9c4  test    edx, edx
0x18003a9c6  jnz     short loc_18003A9B2
0x18003a9c8  test    r8d, r8d
0x18003a9cb  jz      loc_18003AB4D
0x18003a9d1  lea     rax, WPP_GLOBAL_Control
0x18003a9d8  cmp     rcx, rax
0x18003a9db  jz      short loc_18003A9FC
0x18003a9dd  test    byte ptr [rcx+1Ch], 20h
0x18003a9e1  jz      short loc_18003A9FC
0x18003a9e3  mov     r9, [r13+0]
0x18003a9e7  lea     r8, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids
0x18003a9ee  mov     rcx, [rcx+10h]
0x18003a9f2  mov     edx, 0Eh
0x18003a9f7  call    WPP_SF_S
0x18003a9fc  mov     rdx, [rbp+0A50h+Src]; Src
0x18003aa03  lea     rcx, [rbp+0A50h+var_AB0]; void *
0x18003aa07  mov     r8d, 0A70h; Size
0x18003aa0d  call    memcpy_0
0x18003aa12  mov     rcx, [rsp+0B50h+pCertContext]
0x18003aa17  lea     rdx, [rbp+0A50h+var_AB0]
0x18003aa1b  call    ?findIssuerCertContext@@YAPEBU_CERT_CONTEXT@@PEAXU_DbLicensedProduct@@@Z; findIssuerCertContext(void *,_DbLicensedProduct)
0x18003aa20  mov     r14, rax
0x18003aa23  test    rax, rax
0x18003aa26  jz      loc_18003AFEE
0x18003aa2c  mov     rcx, rax; pCertContext
0x18003aa2f  call    cs:__imp_CertDuplicateCertificateContext
0x18003aa36  nop     dword ptr [rax+rax+00h]
0x18003aa3b  mov     [rsp+0B50h+pCertContext+8], rax
0x18003aa40  test    rax, rax
0x18003aa43  jz      loc_18003AFB3
0x18003aa49  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aa50  lea     rdx, WPP_GLOBAL_Control
0x18003aa57  cmp     rcx, rdx
0x18003aa5a  jz      short loc_18003AA7C
0x18003aa5c  test    byte ptr [rcx+1Ch], 20h
0x18003aa60  jz      short loc_18003AA7C
0x18003aa62  mov     rcx, [rcx+10h]
0x18003aa66  lea     r8, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids
0x18003aa6d  mov     edx, 11h
0x18003aa72  call    WPP_SF_
0x18003aa77  mov     rax, [rsp+0B50h+pCertContext+8]
0x18003aa7c  xor     r9d, r9d; ppStoreContext
0x18003aa7f  mov     rdx, rax; pCertContext
0x18003aa82  mov     rcx, r12; hCertStore
0x18003aa85  lea     r8d, [r9+4]; dwAddDisposition
0x18003aa89  call    cs:__imp_CertAddCertificateContextToStore
0x18003aa90  nop     dword ptr [rax+rax+00h]
0x18003aa95  test    eax, eax
0x18003aa97  jz      loc_18003AF6F
0x18003aa9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aaa4  lea     rax, WPP_GLOBAL_Control
0x18003aaab  cmp     rcx, rax
0x18003aaae  jz      short loc_18003AACB
0x18003aab0  test    byte ptr [rcx+1Ch], 20h
0x18003aab4  jz      short loc_18003AACB
0x18003aab6  mov     rcx, [rcx+10h]
0x18003aaba  lea     r8, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids
0x18003aac1  mov     edx, 13h
0x18003aac6  call    WPP_SF_
0x18003aacb  mov     r9, [rsp+0B50h+pCertContext+8]
0x18003aad0  mov     r8, r12
0x18003aad3  mov     rdx, [rsp+0B50h+pCertContext]
0x18003aad8  call    TLSChainIssuerCertificate
0x18003aadd  test    eax, eax
0x18003aadf  jnz     loc_18003AEC3
0x18003aae5  call    cs:__imp_GetLastError
0x18003aaec  nop     dword ptr [rax+rax+00h]
0x18003aaf1  movups  xmm0, cs:TLS_E_GENERATECLIENTELICENSE
0x18003aaf8  mov     r8d, eax
0x18003aafb  lea     rcx, [rsp+0B50h+pbCertEncoded+8]; struct _EVENT_DESCRIPTOR
0x18003ab00  mov     edx, 0C0110010h; unsigned int
0x18003ab05  mov     ebx, eax
0x18003ab07  movdqu  xmmword ptr [rsp+0B50h+pbCertEncoded+8], xmm0
0x18003ab0d  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x18003ab12  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ab19  lea     rax, WPP_GLOBAL_Control
0x18003ab20  cmp     rcx, rax
0x18003ab23  jz      loc_18003B1CF
0x18003ab29  test    byte ptr [rcx+1Ch], 20h
0x18003ab2d  jz      loc_18003B1CF
0x18003ab33  mov     rcx, [rcx+10h]
0x18003ab37  lea     r8, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids
0x18003ab3e  mov     edx, 14h
0x18003ab43  call    WPP_SF_
0x18003ab48  jmp     loc_18003B1CF
0x18003ab4d  lea     rdi, WPP_GLOBAL_Control
0x18003ab54  cmp     rcx, rdi
0x18003ab57  jz      short loc_18003AB74
0x18003ab59  test    byte ptr [rcx+1Ch], 20h
0x18003ab5d  jz      short loc_18003AB74
0x18003ab5f  mov     rcx, [rcx+10h]
0x18003ab63  lea     r8, WPP_b011ab09783b3dc2f509b7b29d9a715c_Traceguids
0x18003ab6a  mov     edx, 15h
0x18003ab6f  call    WPP_SF_
0x18003ab74  mov     eax, 3
0x18003ab79  mov     dword ptr [rsp+0B50h+var_AE8+8], eax
0x18003ab7d  mov     eax, r15d
0x18003ab80  imul    rbx, rax, 0A70h
0x18003ab87  add     rbx, [rbp+0A50h+arg_10]
0x18003ab8e  lea     rax, [rbx+64Ch]
0x18003ab95  mov     qword ptr [rsp+0B50h+var_AE8+10h], rax
0x18003ab9a  lea     rax, [rbx+84Ch]
0x18003aba1  mov     qword ptr [rbp+0A50h+var_AD0], rax
0x18003aba5  lea     rax, [rbx+20h]
0x18003aba9  mov     qword ptr [rbp+0A50h+var_AD0+8], rax
0x18003abad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_2533973305@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_2533973305@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2533973305> `wil::Feature<__WilFeatureTraits_Feature_2533973305>::GetImpl(void)'::`2'::impl
0x18003abb4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_2533973305@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2533973305>::__private_IsEnabled(void)
0x18003abb9  test    al, al
0x18003abbb  jz      short loc_18003AC37
0x18003abbd  mov     rcx, cs:?g_AdminLock@@3VCCMutex@@A; CCMutex g_AdminLock
0x18003abc4  or      edx, 0FFFFFFFFh
0x18003abc7  call    WaitForMyTurnOrShutdown
0x18003abcc  test    eax, eax
0x18003abce  jz      loc_18003B03B
0x18003abd4  mov     rax, cs:?g_SelfSignCertContext@@3PEBU_CERT_CONTEXT@@EB; _CERT_CONTEXT const * const g_SelfSignCertContext
0x18003abdb  test    rax, rax
0x18003abde  jz      loc_18003B019
0x18003abe4  mov     rcx, cs:?g_pLicenseCertContext@RdlsSecretsCache@@2PEBU_CERT_CONTEXT@@EB; _CERT_CONTEXT const * const RdlsSecretsCache::g_pLicenseCertContext
0x18003abeb  test    rcx, rcx
0x18003abee  jz      loc_18003B019
0x18003abf4  mov     rdx, [rax+18h]
0x18003abf8  test    rdx, rdx
0x18003abfb  jz      loc_18003B019
0x18003ac01  mov     rax, [rcx+18h]
0x18003ac05  test    rax, rax
0x18003ac08  jz      loc_18003B019
0x18003ac0e  cmp     cs:?g_bHasHydraCert@RdlsSecretsCache@@2HA, 0; int RdlsSecretsCache::g_bHasHydraCert
0x18003ac15  jz      short loc_18003AC33
0x18003ac17  cmp     cs:?g_hCaStore@@3PEAXEA, 0; void * g_hCaStore
0x18003ac1f  jz      short loc_18003AC33
0x18003ac21  mov     ecx, 3
0x18003ac26  lea     rsi, [rax+50h]
0x18003ac2a  cmp     [rbp+0A50h+arg_18], cx
0x18003ac31  jz      short loc_18003AC37
0x18003ac33  lea     rsi, [rdx+50h]
0x18003ac37  mov     rcx, [rbp+0A50h+arg_0]; unsigned __int64
0x18003ac3e  lea     rax, [rsp+0B50h+cbCertEncoded]
0x18003ac43  mov     [rsp+30h], rax; unsigned int *
0x18003ac48  lea     r8, [rsp+0B50h+var_AE8+8]; struct __LSClientCertRDN *
0x18003ac4d  lea     rax, [rsp+0B50h+pbCertEncoded+8]
0x18003ac52  mov     rdx, rsi; struct _CRYPTOAPI_BLOB *
0x18003ac55  mov     qword ptr [rsp+0B50h+dwFlags], rax; unsigned __int8 **
0x18003ac5a  mov     [rsp+0B50h+pvPara], rbx; struct _DbLicensedProduct *
0x18003ac5f  call    ?TLSGenerateSingleCertificate@@YAK_KPEAU_CRYPTOAPI_BLOB@@PEAU__LSClientCertRDN@@PEAU_CERT_PUBLIC_KEY_INFO@@PEAU_DbLicensedProduct@@PEAPEAEPEAK@Z; TLSGenerateSingleCertificate(unsigned __int64,_CRYPTOAPI_BLOB *,__LSClientCertRDN *,_CERT_PUBLIC_KEY_INFO *,_DbLicensedProduct *,uchar * *,ulong *)
0x18003ac64  mov     ebx, eax
0x18003ac66  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_2533973305@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_2533973305@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2533973305> `wil::Feature<__WilFeatureTraits_Feature_2533973305>::GetImpl(void)'::`2'::impl
0x18003ac6d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_2533973305@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2533973305>::__private_IsEnabled(void)
0x18003ac72  test    al, al
0x18003ac74  jz      short loc_18003AC8E
0x18003ac76  mov     rcx, cs:?g_AdminLock@@3VCCMutex@@A; hMutex
0x18003ac7d  test    rcx, rcx
0x18003ac80  jz      short loc_18003AC8E
0x18003ac82  call    cs:__imp_ReleaseMutex
0x18003ac89  nop     dword ptr [rax+rax+00h]
0x18003ac8e  test    ebx, ebx
0x18003ac90  jnz     loc_18003B117
0x18003ac96  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac9d  cmp     rcx, rdi
0x18003aca0  jz      short loc_18003ACBB
0x18003aca2  test    byte ptr [rcx+1Ch], 20h
  ... truncated ...
```
