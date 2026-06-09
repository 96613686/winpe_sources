# VerifyAndGetLicenseKeyPack(unsigned __int64,_License_KeyPack_ *,ulong,uchar *,ulong,uchar *,ulong,uchar *)

- ea: `0x1800617a0`
- end: `0x180061e7f`
- name: `?VerifyAndGetLicenseKeyPack@@YAK_KPEAU_License_KeyPack_@@KPEAEK2K2@Z`
- size: `1759`
- prototype: `__int64 __fastcall(unsigned __int64, struct _License_KeyPack_ *, unsigned int, unsigned __int8 *, DWORD cbCertEncoded, BYTE *pbCertEncoded, unsigned int, BYTE *pbData)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18005e850`
- `0x18005e9f8`

## callees

- `0x180002d26`
- `0x18000ead0`
- `0x18001ae3c`
- `0x18001aea4`
- `0x18005f1ec`
- `0x18005f58c`
- `0x180060028`
- `0x1800617a0`
- `0x180061e88`

## import_xrefs

- `CRYPT32!CryptImportPublicKeyInfoEx` at `0x180061d85`
- `CRYPT32!CryptImportPublicKeyInfoEx` at `0x180061d85`
- `CRYPT32!CertFreeCertificateContext` at `0x180061c19`
- `CRYPT32!CertFreeCertificateContext` at `0x180061c19`
- `CRYPT32!CertCloseStore` at `0x180061c35`
- `CRYPT32!CertCloseStore` at `0x180061c35`
- `ADVAPI32!CryptVerifySignatureW` at `0x180061df1`
- `ADVAPI32!CryptVerifySignatureW` at `0x180061df1`
- `ADVAPI32!CryptCreateHash` at `0x180061cbb`
- `ADVAPI32!CryptCreateHash` at `0x180061cbb`
- `ADVAPI32!CryptHashData` at `0x180061d1e`
- `ADVAPI32!CryptHashData` at `0x180061d1e`
- `ADVAPI32!CryptDestroyHash` at `0x180061bcf`
- `ADVAPI32!CryptDestroyHash` at `0x180061bcf`
- `ADVAPI32!CryptDestroyKey` at `0x180061be4`
- `ADVAPI32!CryptDestroyKey` at `0x180061be4`
- `KERNEL32!GetLastError` at `0x180061bb8`
- `KERNEL32!GetLastError` at `0x180061e05`
- `KERNEL32!GetLastError` at `0x180061bb8`
- `KERNEL32!GetLastError` at `0x180061e05`
- `KERNEL32!LocalAlloc` at `0x180061960`
- `KERNEL32!LocalAlloc` at `0x1800619ce`
- `KERNEL32!LocalAlloc` at `0x180061a34`
- `KERNEL32!LocalAlloc` at `0x180061a90`
- `KERNEL32!LocalAlloc` at `0x180061b0f`
- `KERNEL32!LocalAlloc` at `0x180061b63`
- `KERNEL32!LocalAlloc` at `0x180061960`
- `KERNEL32!LocalAlloc` at `0x1800619ce`
- `KERNEL32!LocalAlloc` at `0x180061a34`
- `KERNEL32!LocalAlloc` at `0x180061a90`
- `KERNEL32!LocalAlloc` at `0x180061b0f`
- `KERNEL32!LocalAlloc` at `0x180061b63`
- `KERNEL32!SetLastError` at `0x180061819`
- `KERNEL32!SetLastError` at `0x180061895`
- `KERNEL32!SetLastError` at `0x1800618c7`
- `KERNEL32!SetLastError` at `0x180061ba1`
- `KERNEL32!SetLastError` at `0x180061e64`
- `KERNEL32!SetLastError` at `0x180061819`
- `KERNEL32!SetLastError` at `0x180061895`
- `KERNEL32!SetLastError` at `0x1800618c7`
- `KERNEL32!SetLastError` at `0x180061ba1`
- `KERNEL32!SetLastError` at `0x180061e64`

## pseudocode

```c
__int64 __fastcall VerifyAndGetLicenseKeyPack(
        unsigned __int64 a1,
        struct _License_KeyPack_ *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        DWORD cbCertEncoded,
        BYTE *pbCertEncoded,
        unsigned int a7,
        BYTE *pbData)
{
  unsigned __int64 v11; // r12
  unsigned int v12; // ebx
  DWORD Certificate; // eax
  const CERT_CONTEXT *v15; // rsi
  DWORD v16; // eax
  unsigned int v17; // esi
  const BYTE *v18; // r13
  BYTE *v19; // r14
  unsigned int v20; // ecx
  HLOCAL v21; // rax
  __int64 v22; // rax
  unsigned int *v23; // r14
  unsigned __int64 v24; // rax
  unsigned int *v25; // rax
  unsigned int *v26; // rsi
  unsigned int v27; // r12d
  unsigned int v28; // eax
  unsigned int *v29; // r14
  unsigned int v30; // ecx
  HLOCAL v31; // rax
  unsigned int v32; // eax
  unsigned int v33; // ecx
  HLOCAL v34; // rax
  unsigned int v35; // ebx
  unsigned int v36; // eax
  unsigned int *v37; // rsi
  unsigned int v38; // ecx
  HLOCAL v39; // rax
  unsigned int v40; // eax
  DWORD *v41; // rsi
  unsigned int v42; // edx
  HLOCAL v43; // rax
  DWORD v44; // r14d
  DWORD v45; // ecx
  DWORD v46; // ebx
  const BYTE *v47; // rbx
  _QWORD *v48; // rcx
  __int64 v49; // rdx
  DWORD LastError; // ebx
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-30h] BYREF
  HCRYPTHASH hHash; // [rsp+48h] [rbp-28h] BYREF
  HCERTSTORE hCertStore; // [rsp+50h] [rbp-20h] BYREF
  HCRYPTKEY hKey; // [rsp+58h] [rbp-18h] BYREF
  struct _EVENT_DESCRIPTOR v55; // [rsp+60h] [rbp-10h] BYREF

  pCertContext = 0;
  hCertStore = 0;
  hHash = 0;
  v11 = a1;
  hKey = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids,
      L"VerifyAndGetLicenseKeyPack");
  SetLastError(0);
  v12 = 80;
  if ( a7 < 0x50 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids,
        (unsigned int)L"VerifyAndGetLicenseKeyPack",
        87);
    return 87;
  }
  Certificate = GetCertificate(a3, a4, v11, &pCertContext, &hCertStore);
  if ( Certificate )
  {
    SetLastError(Certificate);
    goto LABEL_11;
  }
  v16 = VerifyCertificateChain(hCertStore, pCertContext, cbCertEncoded, pbCertEncoded);
  v17 = v16;
  if ( v16 )
  {
    SetLastError(v16);
    v55 = (struct _EVENT_DESCRIPTOR)TLS_E_CERTIFICATE_VERIFICATION_FAILED;
    KeypackLib_LogErrorEvent(&v55, v17);
    goto LABEL_11;
  }
  v18 = pbData;
  v19 = pbData + 64;
  *(_DWORD *)a2 = *(_DWORD *)pbData;
  *((_DWORD *)a2 + 1) = *((_DWORD *)pbData + 1);
  *((_DWORD *)a2 + 2) = *((_DWORD *)pbData + 2);
  *(_OWORD *)((char *)a2 + 12) = *(_OWORD *)(pbData + 12);
  *(_QWORD *)((char *)a2 + 28) = *(_QWORD *)(pbData + 28);
  *(_QWORD *)((char *)a2 + 36) = *(_QWORD *)(pbData + 36);
  *(_QWORD *)((char *)a2 + 44) = *(_QWORD *)(pbData + 44);
  *((_DWORD *)a2 + 13) = *((_DWORD *)pbData + 13);
  *((_DWORD *)a2 + 14) = *((_DWORD *)pbData + 14);
  v20 = *((_DWORD *)pbData + 15);
  *((_DWORD *)a2 + 15) = v20;
  if ( v20 )
  {
    if ( v20 + 80 < 0x50 )
      goto LABEL_49;
    v12 = v20 + 80;
    if ( a7 < v20 + 80 )
      goto LABEL_87;
    v21 = LocalAlloc(0x40u, v20);
    *((_QWORD *)a2 + 8) = v21;
    if ( !v21 )
      goto LABEL_51;
    memcpy_0(v21, v19, *((unsigned int *)a2 + 15));
    v19 += *((unsigned int *)a2 + 15);
  }
  *((_DWORD *)a2 + 18) = *(_DWORD *)v19;
  *((_DWORD *)a2 + 19) = *((_DWORD *)v19 + 1);
  *((_DWORD *)a2 + 20) = *((_DWORD *)v19 + 2);
  v22 = *((unsigned int *)v19 + 3);
  v23 = (unsigned int *)(v19 + 16);
  *((_DWORD *)a2 + 21) = v22;
  if ( (_DWORD)v22 )
  {
    v24 = 32 * v22;
    if ( v24 > 0xFFFFFFFF )
      goto LABEL_87;
    v25 = (unsigned int *)LocalAlloc(0x40u, (unsigned int)v24);
    *((_QWORD *)a2 + 11) = v25;
    v26 = v25;
    if ( !v25 )
      goto LABEL_51;
    v27 = 0;
    if ( *((_DWORD *)a2 + 21) )
    {
      while ( 1 )
      {
        v12 += 12;
        if ( a7 < v12 )
          goto LABEL_87;
        *v26 = *v23;
        v28 = v23[1];
        v29 = v23 + 2;
        v26[1] = v28;
        if ( v28 )
        {
          v30 = v28 + v12;
          if ( v12 > v28 + v12 )
            goto LABEL_49;
          v12 += v28;
          if ( a7 < v30 )
            goto LABEL_87;
          v31 = LocalAlloc(0x40u, v28);
          *((_QWORD *)v26 + 1) = v31;
          if ( !v31 )
            goto LABEL_51;
          memcpy_0(v31, v29, v26[1]);
          v29 = (unsigned int *)((char *)v29 + v26[1]);
        }
        v32 = *v29;
        v23 = v29 + 1;
        v26[4] = v32;
        if ( v32 )
        {
          v33 = v32 + v12;
          if ( v12 > v32 + v12 )
            goto LABEL_49;
          v12 += v32;
          if ( a7 < v33 )
            goto LABEL_87;
          v34 = LocalAlloc(0x40u, v32);
          *((_QWORD *)v26 + 3) = v34;
          if ( !v34 )
            goto LABEL_51;
          memcpy_0(v34, v23, v26[4]);
          v23 = (unsigned int *)((char *)v23 + v26[4]);
        }
        ++v27;
        v26 += 8;
        if ( v27 >= *((_DWORD *)a2 + 21) )
        {
          v18 = pbData;
          break;
        }
      }
    }
    v11 = a1;
  }
  v35 = v12 + 12;
  if ( a7 < v35 )
    goto LABEL_87;
  v36 = *v23;
  v37 = v23 + 1;
  *((_DWORD *)a2 + 24) = *v23;
  if ( v36 )
  {
    v38 = v36 + v35;
    if ( v35 > v36 + v35 )
      goto LABEL_49;
    v35 += v36;
    if ( a7 < v38 )
      goto LABEL_87;
    v39 = LocalAlloc(0x40u, v36);
    *((_QWORD *)a2 + 13) = v39;
    if ( v39 )
    {
      memcpy_0(v39, v23 + 1, *((unsigned int *)a2 + 24));
      v37 = (unsigned int *)((char *)v37 + *((unsigned int *)a2 + 24));
      goto LABEL_43;
    }
LABEL_51:
    v15 = pCertContext;
    goto LABEL_52;
  }
LABEL_43:
  v40 = *v37;
  v41 = v37 + 1;
  *((_DWORD *)a2 + 28) = v40;
  if ( !v40 )
    goto LABEL_48;
  v42 = v40 + v35;
  if ( v35 > v40 + v35 )
  {
LABEL_49:
    v45 = 534;
LABEL_50:
    SetLastError(v45);
    goto LABEL_51;
  }
  v35 += v40;
  if ( a7 < v42 )
    goto LABEL_87;
  v43 = LocalAlloc(0x40u, v40);
  *((_QWORD *)a2 + 15) = v43;
  if ( !v43 )
    goto LABEL_51;
  memcpy_0(v43, v41, *((unsigned int *)a2 + 28));
  v41 = (DWORD *)((char *)v41 + *((unsigned int *)a2 + 28));
LABEL_48:
  v44 = *v41;
  if ( v35 > v35 + *v41 )
    goto LABEL_49;
  if ( a7 < v35 + *v41 )
  {
LABEL_87:
    v45 = 87;
    goto LABEL_50;
  }
  v47 = (const BYTE *)(v41 + 1);
  if ( CryptCreateHash(v11, 0x800Eu, 0, 0, &hHash) )
  {
    if ( CryptHashData(hHash, v18, (_DWORD)v41 - (_DWORD)v18, 0) )
    {
      v15 = pCertContext;
      if ( CryptImportPublicKeyInfoEx(v11, 1u, &pCertContext->pCertInfo->SubjectPublicKeyInfo, 0x2400u, 0, 0, &hKey) )
      {
        if ( !CryptVerifySignatureW(hHash, v47, v44, hKey, 0, 0) )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              46,
              WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids,
              L"VerifyAndGetLicenseKeyPack");
          v55 = (struct _EVENT_DESCRIPTOR)TLS_E_KEYPACK_INVALID_HASH;
          KeypackLib_LogErrorEvent(&v55, LastError);
          SetLastError(LastError);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids,
          L"VerifyAndGetLicenseKeyPack");
      }
      goto LABEL_52;
    }
    v48 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_11;
    v49 = 44;
  }
  else
  {
    v48 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_11;
    v49 = 43;
  }
  WPP_SF_S(v48[2], v49, WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids, L"VerifyAndGetLicenseKeyPack");
LABEL_11:
  v15 = pCertContext;
LABEL_52:
  v46 = GetLastError();
  if ( hHash )
    CryptDestroyHash(hHash);
  if ( hKey )
    CryptDestroyKey(hKey);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88573>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MSRC88573>::GetImpl'::`2'::impl)
    && v46
    && a2 )
  {
    FreeLicenseKeyPack(a2);
  }
  if ( v15 )
    CertFreeCertificateContext(v15);
  if ( hCertStore )
    CertCloseStore(hCertStore, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      (unsigned int)WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids,
      (unsigned int)L"VerifyAndGetLicenseKeyPack",
      v46);
  return v46;
}

```

## disassembly

```asm
0x1800617a0  mov     rax, rsp
0x1800617a3  mov     [rax+10h], rbx
0x1800617a7  mov     [rax+18h], rsi
0x1800617ab  mov     [rax+20h], rdi
0x1800617af  mov     [rax+8], rcx
0x1800617b3  push    rbp
0x1800617b4  push    r12
0x1800617b6  push    r13
0x1800617b8  push    r14
0x1800617ba  push    r15
0x1800617bc  mov     rbp, rsp
0x1800617bf  sub     rsp, 70h
0x1800617c3  xor     eax, eax
0x1800617c5  mov     rsi, r9
0x1800617c8  mov     [rbp+pCertContext], rax
0x1800617cc  mov     r14d, r8d
0x1800617cf  mov     [rbp+hCertStore], rax
0x1800617d3  mov     rdi, rdx
0x1800617d6  mov     [rbp+hHash], rax
0x1800617da  mov     r12, rcx
0x1800617dd  mov     [rbp+hKey], rax
0x1800617e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800617e8  lea     r13, WPP_GLOBAL_Control
0x1800617ef  cmp     rcx, r13
0x1800617f2  jz      short loc_180061817
0x1800617f4  test    dword ptr [rcx+1Ch], 1000h
0x1800617fb  jz      short loc_180061817
0x1800617fd  mov     rcx, [rcx+10h]
0x180061801  lea     edx, [rax+29h]
0x180061804  lea     r9, aVerifyandgetli; "VerifyAndGetLicenseKeyPack"
0x18006180b  lea     r8, WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids
0x180061812  call    WPP_SF_S
0x180061817  xor     ecx, ecx; dwErrCode
0x180061819  call    cs:__imp_SetLastError
0x180061820  nop     dword ptr [rax+rax+00h]
0x180061825  mov     r15d, [rbp+arg_30]
0x180061829  mov     ebx, 50h ; 'P'
0x18006182e  cmp     r15d, ebx
0x180061831  jnb     short loc_180061874
0x180061833  mov     rcx, cs:WPP_GLOBAL_Control
0x18006183a  cmp     rcx, r13
0x18006183d  jz      short loc_18006186A
0x18006183f  test    dword ptr [rcx+1Ch], 1000h
0x180061846  jz      short loc_18006186A
0x180061848  mov     rcx, [rcx+10h]
0x18006184c  lea     edx, [rbx-26h]
0x18006184f  lea     r9, aVerifyandgetli; "VerifyAndGetLicenseKeyPack"
0x180061856  mov     dword ptr [rsp+70h+phHash], 57h ; 'W'
0x18006185e  lea     r8, WPP_7f1a9c88674431a40e0472a6bde2fdc6_Traceguids
0x180061865  call    WPP_SF_SD
0x18006186a  mov     eax, 57h ; 'W'
0x18006186f  jmp     loc_180061C78
0x180061874  lea     rax, [rbp+hCertStore]
0x180061878  mov     r8, r12; unsigned __int64
0x18006187b  lea     r9, [rbp+pCertContext]; struct _CERT_CONTEXT **
0x18006187f  mov     [rsp+70h+phHash], rax; void **
0x180061884  mov     rdx, rsi; unsigned __int8 *
0x180061887  mov     ecx, r14d; unsigned int
0x18006188a  call    ?GetCertificate@@YAKKPEAE_KPEAPEBU_CERT_CONTEXT@@PEAPEAX@Z; GetCertificate(ulong,uchar *,unsigned __int64,_CERT_CONTEXT const * *,void * *)
0x18006188f  test    eax, eax
0x180061891  jz      short loc_1800618AA
0x180061893  mov     ecx, eax; dwErrCode
0x180061895  call    cs:__imp_SetLastError
0x18006189c  nop     dword ptr [rax+rax+00h]
0x1800618a1  mov     rsi, [rbp+pCertContext]
0x1800618a5  jmp     loc_180061BB8
0x1800618aa  mov     r9, [rbp+pbCertEncoded]; pbCertEncoded
0x1800618ae  mov     r8d, [rbp+cbCertEncoded]; cbCertEncoded
0x1800618b2  mov     rdx, [rbp+pCertContext]; pCertContext
0x1800618b6  mov     rcx, [rbp+hCertStore]; hCertStore
0x1800618ba  call    ?VerifyCertificateChain@@YAKPEAXPEBU_CERT_CONTEXT@@KPEAE@Z; VerifyCertificateChain(void *,_CERT_CONTEXT const *,ulong,uchar *)
0x1800618bf  mov     esi, eax
0x1800618c1  test    eax, eax
0x1800618c3  jz      short loc_1800618EC
0x1800618c5  mov     ecx, eax; dwErrCode
0x1800618c7  call    cs:__imp_SetLastError
0x1800618ce  nop     dword ptr [rax+rax+00h]
0x1800618d3  movups  xmm0, cs:TLS_E_CERTIFICATE_VERIFICATION_FAILED
0x1800618da  mov     edx, esi; unsigned int
0x1800618dc  lea     rcx, [rbp+var_10]; struct _EVENT_DESCRIPTOR
0x1800618e0  movdqu  xmmword ptr [rbp+var_10.Id], xmm0
0x1800618e5  call    ?KeypackLib_LogErrorEvent@@YAXU_EVENT_DESCRIPTOR@@K@Z; KeypackLib_LogErrorEvent(_EVENT_DESCRIPTOR,ulong)
0x1800618ea  jmp     short loc_1800618A1
0x1800618ec  mov     r13, [rbp+pbData]
0x1800618f0  mov     eax, [r13+0]
0x1800618f4  lea     r14, [r13+40h]
0x1800618f8  mov     [rdi], eax
0x1800618fa  mov     eax, [r13+4]
0x1800618fe  mov     [rdi+4], eax
0x180061901  mov     eax, [r13+8]
0x180061905  mov     [rdi+8], eax
0x180061908  movups  xmm0, xmmword ptr [r13+0Ch]
0x18006190d  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x180061912  mov     rax, [r13+1Ch]
0x180061916  mov     [rdi+1Ch], rax
0x18006191a  mov     rax, [r13+24h]
0x18006191e  mov     [rdi+24h], rax
0x180061922  mov     rax, [r13+2Ch]
0x180061926  mov     [rdi+2Ch], rax
0x18006192a  mov     eax, [r13+34h]
0x18006192e  mov     [rdi+34h], eax
0x180061931  mov     eax, [r13+38h]
0x180061935  mov     [rdi+38h], eax
0x180061938  mov     ecx, [r13+3Ch]
0x18006193c  mov     [rdi+3Ch], ecx
0x18006193f  test    ecx, ecx
0x180061941  jz      short loc_18006198E
0x180061943  lea     eax, [rcx+50h]
0x180061946  cmp     eax, ebx
0x180061948  jb      loc_180061B9C
0x18006194e  mov     ebx, eax
0x180061950  cmp     r15d, eax
0x180061953  jb      loc_180061E75
0x180061959  mov     edx, ecx; uBytes
0x18006195b  mov     ecx, 40h ; '@'; uFlags
0x180061960  call    cs:__imp_LocalAlloc
0x180061967  nop     dword ptr [rax+rax+00h]
0x18006196c  mov     [rdi+40h], rax
0x180061970  test    rax, rax
0x180061973  jz      loc_180061BAD
0x180061979  mov     r8d, [rdi+3Ch]; Size
0x18006197d  mov     rdx, r14; Src
0x180061980  mov     rcx, rax; void *
0x180061983  call    memcpy_0
0x180061988  mov     eax, [rdi+3Ch]
0x18006198b  add     r14, rax
0x18006198e  mov     eax, [r14]
0x180061991  mov     [rdi+48h], eax
0x180061994  mov     eax, [r14+4]
0x180061998  mov     [rdi+4Ch], eax
0x18006199b  mov     eax, [r14+8]
0x18006199f  mov     [rdi+50h], eax
0x1800619a2  mov     eax, [r14+0Ch]
0x1800619a6  add     r14, 10h
0x1800619aa  mov     [rdi+54h], eax
0x1800619ad  test    eax, eax
0x1800619af  jz      loc_180061AD8
0x1800619b5  shl     rax, 5
0x1800619b9  mov     ecx, 0FFFFFFFFh
0x1800619be  cmp     rax, rcx
0x1800619c1  ja      loc_180061E75
0x1800619c7  mov     edx, eax; uBytes
0x1800619c9  mov     ecx, 40h ; '@'; uFlags
0x1800619ce  call    cs:__imp_LocalAlloc
0x1800619d5  nop     dword ptr [rax+rax+00h]
0x1800619da  mov     [rdi+58h], rax
0x1800619de  mov     rsi, rax
0x1800619e1  test    rax, rax
0x1800619e4  jz      loc_180061BAD
0x1800619ea  xor     r12d, r12d
0x1800619ed  cmp     [rdi+54h], r12d
0x1800619f1  jbe     loc_180061AD4
0x1800619f7  add     ebx, 0Ch
0x1800619fa  cmp     r15d, ebx
0x1800619fd  jb      loc_180061E75
0x180061a03  mov     eax, [r14]
0x180061a06  mov     [rsi], eax
0x180061a08  mov     eax, [r14+4]
0x180061a0c  add     r14, 8
0x180061a10  mov     [rsi+4], eax
0x180061a13  test    eax, eax
0x180061a15  jz      short loc_180061A62
0x180061a17  lea     ecx, [rax+rbx]
0x180061a1a  cmp     ebx, ecx
0x180061a1c  ja      loc_180061B9C
0x180061a22  mov     ebx, ecx
0x180061a24  cmp     r15d, ecx
0x180061a27  jb      loc_180061E75
0x180061a2d  mov     edx, eax; uBytes
0x180061a2f  mov     ecx, 40h ; '@'; uFlags
0x180061a34  call    cs:__imp_LocalAlloc
0x180061a3b  nop     dword ptr [rax+rax+00h]
0x180061a40  mov     [rsi+8], rax
0x180061a44  test    rax, rax
0x180061a47  jz      loc_180061BAD
0x180061a4d  mov     r8d, [rsi+4]; Size
0x180061a51  mov     rdx, r14; Src
0x180061a54  mov     rcx, rax; void *
0x180061a57  call    memcpy_0
0x180061a5c  mov     eax, [rsi+4]
0x180061a5f  add     r14, rax
0x180061a62  mov     eax, [r14]
0x180061a65  add     r14, 4
0x180061a69  mov     [rsi+10h], eax
0x180061a6c  mov     r13, r14
0x180061a6f  test    eax, eax
0x180061a71  jz      short loc_180061ABF
0x180061a73  lea     ecx, [rax+rbx]
0x180061a76  cmp     ebx, ecx
0x180061a78  ja      loc_180061B9C
0x180061a7e  mov     ebx, ecx
0x180061a80  cmp     r15d, ecx
0x180061a83  jb      loc_180061E75
0x180061a89  mov     edx, eax; uBytes
0x180061a8b  mov     ecx, 40h ; '@'; uFlags
0x180061a90  call    cs:__imp_LocalAlloc
0x180061a97  nop     dword ptr [rax+rax+00h]
0x180061a9c  mov     [rsi+18h], rax
0x180061aa0  test    rax, rax
0x180061aa3  jz      loc_180061BAD
0x180061aa9  mov     r8d, [rsi+10h]; Size
0x180061aad  mov     rdx, r14; Src
0x180061ab0  mov     rcx, rax; void *
0x180061ab3  call    memcpy_0
0x180061ab8  mov     r14d, [rsi+10h]
0x180061abc  add     r14, r13
0x180061abf  inc     r12d
0x180061ac2  add     rsi, 20h ; ' '
0x180061ac6  cmp     r12d, [rdi+54h]
0x180061aca  jb      loc_1800619F7
0x180061ad0  mov     r13, [rbp+pbData]
0x180061ad4  mov     r12, [rbp+arg_0]
0x180061ad8  add     ebx, 0Ch
0x180061adb  cmp     r15d, ebx
0x180061ade  jb      loc_180061E75
0x180061ae4  mov     eax, [r14]
0x180061ae7  lea     rsi, [r14+4]
0x180061aeb  mov     [rdi+60h], eax
0x180061aee  test    eax, eax
0x180061af0  jz      short loc_180061B3D
0x180061af2  lea     ecx, [rax+rbx]
0x180061af5  cmp     ebx, ecx
0x180061af7  ja      loc_180061B9C
0x180061afd  mov     ebx, ecx
0x180061aff  cmp     r15d, ecx
0x180061b02  jb      loc_180061E75
0x180061b08  mov     edx, eax; uBytes
0x180061b0a  mov     ecx, 40h ; '@'; uFlags
0x180061b0f  call    cs:__imp_LocalAlloc
0x180061b16  nop     dword ptr [rax+rax+00h]
0x180061b1b  mov     [rdi+68h], rax
0x180061b1f  test    rax, rax
0x180061b22  jz      loc_180061BAD
0x180061b28  mov     r8d, [rdi+60h]; Size
0x180061b2c  mov     rdx, rsi; Src
0x180061b2f  mov     rcx, rax; void *
0x180061b32  call    memcpy_0
0x180061b37  mov     eax, [rdi+60h]
0x180061b3a  add     rsi, rax
0x180061b3d  mov     eax, [rsi]
0x180061b3f  add     rsi, 4
0x180061b43  mov     [rdi+70h], eax
0x180061b46  test    eax, eax
0x180061b48  jz      short loc_180061B8D
0x180061b4a  lea     edx, [rax+rbx]
0x180061b4d  cmp     ebx, edx
0x180061b4f  ja      short loc_180061B9C
0x180061b51  mov     ebx, edx
0x180061b53  cmp     r15d, edx
0x180061b56  jb      loc_180061E75
0x180061b5c  mov     edx, eax; uBytes
0x180061b5e  mov     ecx, 40h ; '@'; uFlags
0x180061b63  call    cs:__imp_LocalAlloc
0x180061b6a  nop     dword ptr [rax+rax+00h]
0x180061b6f  mov     [rdi+78h], rax
0x180061b73  test    rax, rax
0x180061b76  jz      short loc_180061BAD
0x180061b78  mov     r8d, [rdi+70h]; Size
0x180061b7c  mov     rdx, rsi; Src
0x180061b7f  mov     rcx, rax; void *
0x180061b82  call    memcpy_0
0x180061b87  mov     eax, [rdi+70h]
0x180061b8a  add     rsi, rax
0x180061b8d  mov     r14d, [rsi]
0x180061b90  lea     eax, [rbx+r14]
0x180061b94  cmp     ebx, eax
0x180061b96  jbe     loc_180061C97
0x180061b9c  mov     ecx, 216h; dwErrCode
0x180061ba1  call    cs:__imp_SetLastError
0x180061ba8  nop     dword ptr [rax+rax+00h]
0x180061bad  mov     rsi, [rbp+pCertContext]
0x180061bb1  lea     r13, WPP_GLOBAL_Control
0x180061bb8  call    cs:__imp_GetLastError
0x180061bbf  nop     dword ptr [rax+rax+00h]
0x180061bc4  mov     rcx, [rbp+hHash]; hHash
0x180061bc8  mov     ebx, eax
0x180061bca  test    rcx, rcx
0x180061bcd  jz      short loc_180061BDB
0x180061bcf  call    cs:__imp_CryptDestroyHash
0x180061bd6  nop     dword ptr [rax+rax+00h]
0x180061bdb  mov     rcx, [rbp+hKey]; hKey
0x180061bdf  test    rcx, rcx
0x180061be2  jz      short loc_180061BF0
0x180061be4  call    cs:__imp_CryptDestroyKey
0x180061beb  nop     dword ptr [rax+rax+00h]
0x180061bf0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MSRC88573@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MSRC88573@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88573> `wil::Feature<__WilFeatureTraits_Feature_MSRC88573>::GetImpl(void)'::`2'::impl
0x180061bf7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MSRC88573@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC88573>::__private_IsEnabled(void)
0x180061bfc  test    al, al
0x180061bfe  jz      short loc_180061C11
0x180061c00  test    ebx, ebx
0x180061c02  jz      short loc_180061C11
0x180061c04  test    rdi, rdi
0x180061c07  jz      short loc_180061C11
0x180061c09  mov     rcx, rdi; struct _License_KeyPack_ *
0x180061c0c  call    ?FreeLicenseKeyPack@@YAXPEAU_License_KeyPack_@@@Z; FreeLicenseKeyPack(_License_KeyPack_ *)
0x180061c11  test    rsi, rsi
0x180061c14  jz      short loc_180061C25
0x180061c16  mov     rcx, rsi; pCertContext
0x180061c19  call    cs:__imp_CertFreeCertificateContext
0x180061c20  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
