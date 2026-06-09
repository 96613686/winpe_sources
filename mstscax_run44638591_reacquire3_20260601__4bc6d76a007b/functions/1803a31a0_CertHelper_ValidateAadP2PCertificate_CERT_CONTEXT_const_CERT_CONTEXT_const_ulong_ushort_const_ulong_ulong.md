# CertHelper::ValidateAadP2PCertificate(_CERT_CONTEXT const *,_CERT_CONTEXT const * *,ulong,ushort const *,ulong &,ulong &)

- ea: `0x1803a31a0`
- end: `0x1803a3972`
- name: `?ValidateAadP2PCertificate@CertHelper@@YAJPEBU_CERT_CONTEXT@@PEAPEBU2@KPEBGAEAK3@Z`
- size: `2002`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCertContext@<rcx>, const struct _CERT_CONTEXT *@<rdx>, const struct _CERT_CONTEXT **@<r8>, unsigned int@<r9d>, const unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180395f3c`

## callees

- `0x1800054f4`
- `0x1803a2f18`
- `0x1803a31a0`
- `0x180688f3e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1803a334b`
- `KERNEL32!GetLastError` at `0x1803a3455`
- `KERNEL32!GetLastError` at `0x1803a34fc`
- `KERNEL32!GetLastError` at `0x1803a3605`
- `KERNEL32!GetLastError` at `0x1803a334b`
- `KERNEL32!GetLastError` at `0x1803a3455`
- `KERNEL32!GetLastError` at `0x1803a34fc`
- `KERNEL32!GetLastError` at `0x1803a3605`
- `CRYPT32!CertOpenStore` at `0x1803a3339`
- `CRYPT32!CertOpenStore` at `0x1803a3339`
- `CRYPT32!CertCloseStore` at `0x1803a3947`
- `CRYPT32!CertCloseStore` at `0x1803a3947`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1803a37de`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1803a37de`
- `CRYPT32!CertFreeCertificateChain` at `0x1803a3956`
- `CRYPT32!CertFreeCertificateChain` at `0x1803a3956`
- `CRYPT32!CertGetCertificateChain` at `0x1803a35f7`
- `CRYPT32!CertGetCertificateChain` at `0x1803a35f7`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1803a3409`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1803a3409`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x1803a3447`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x1803a3447`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1803a3937`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1803a3937`

## string_xrefs

- `0x1803a3222`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x1803a32c0`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x1803a339c`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x1803a34a6`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x1803a354d`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x1803a3656`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x1803a371e`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x1803a382c`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x1803a38d0`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x1803a336f`: `CertOpenStore failed`
- `0x1803a3479`: `CertCreateCertificateChainEngine failed`

## pseudocode

```c
__int64 __fastcall CertHelper::ValidateAadP2PCertificate(
        PCCERT_CONTEXT pCertContext,
        const struct _CERT_CONTEXT *a2,
        const struct _CERT_CONTEXT **a3,
        wchar_t *a4,
        unsigned __int16 *a5,
        unsigned int *a6)
{
  unsigned int v7; // esi
  HCERTSTORE v10; // r15
  signed int matched; // ebx
  __int16 *v12; // rdx
  const char **v13; // rax
  signed int v14; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  unsigned int v18; // ebx
  signed int v19; // eax
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  signed int LastError; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  bool *v27; // r9
  signed int v28; // eax
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // r8d
  int v33; // r9d
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  void *pvPara; // [rsp+20h] [rbp-E0h]
  const char **pvReserved; // [rsp+30h] [rbp-D0h]
  const char **v40; // [rsp+40h] [rbp-C0h]
  const char **p_pPolicyPara; // [rsp+48h] [rbp-B8h]
  int v42; // [rsp+50h] [rbp-B0h] BYREF
  const char *v43; // [rsp+58h] [rbp-A8h] BYREF
  const char *v44; // [rsp+60h] [rbp-A0h] BYREF
  const char *v45; // [rsp+68h] [rbp-98h] BYREF
  struct _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+70h] [rbp-90h] BYREF
  const char *v47; // [rsp+80h] [rbp-80h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+88h] [rbp-78h] BYREF
  HCERTCHAINENGINE phChainEngine; // [rsp+90h] [rbp-70h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v51[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-40h]
  __int64 v53; // [rsp+C8h] [rbp-38h]
  _CERT_CHAIN_ENGINE_CONFIG pConfig; // [rsp+D0h] [rbp-30h] BYREF
  int v55; // [rsp+180h] [rbp+80h] BYREF

  phChainEngine = 0;
  v7 = (unsigned int)a3;
  pChainContext = 0;
  LOBYTE(v55) = 0;
  v10 = 0;
  if ( !pCertContext )
  {
    matched = -2147024809;
    if ( (unsigned int)dword_1808B5850 <= 2 )
      goto LABEL_43;
    v55 = 371;
    *(_QWORD *)&pPolicyPara.cbSize = "pDeviceCert is not specified";
    v12 = (__int16 *)byte_180875273;
    v43 = "ValidateAadP2PCertificate";
    v44 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
    v45 = "Error condition failed";
    p_pPolicyPara = (const char **)&pPolicyPara;
    v40 = &v43;
    pvReserved = &v44;
    v13 = &v45;
LABEL_42:
    v42 = -2147024809;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      -2147024809,
      (_DWORD)v12,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)v13,
      (__int64)&v42,
      (__int64)pvReserved,
      (__int64)&v55,
      (__int64)v40,
      (__int64)p_pPolicyPara);
    goto LABEL_43;
  }
  if ( !a2 )
  {
    matched = -2147024809;
    if ( (unsigned int)dword_1808B5850 <= 2 )
      goto LABEL_43;
    v55 = 372;
    v45 = "ppP2PRootCerts is not specified";
    v12 = &word_1808752BE;
    v44 = "ValidateAadP2PCertificate";
    v43 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
    *(_QWORD *)&pPolicyPara.cbSize = "Error condition failed";
    p_pPolicyPara = &v45;
    v40 = &v44;
    pvReserved = &v43;
    v13 = (const char **)&pPolicyPara;
    goto LABEL_42;
  }
  if ( !a4 || !*a4 )
  {
    matched = -2147024809;
    if ( (unsigned int)dword_1808B5850 <= 2 )
      goto LABEL_43;
    v55 = 373;
    v47 = "pwszExpectedDeviceId is not specified";
    v12 = (__int16 *)&dword_180875354;
    v45 = "ValidateAadP2PCertificate";
    v44 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
    v43 = "Error condition failed";
    p_pPolicyPara = &v47;
    v40 = &v45;
    pvReserved = &v44;
    v13 = &v43;
    goto LABEL_42;
  }
  v10 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
  if ( v10 )
  {
    v18 = 0;
    if ( v7 )
    {
      while ( CertAddCertificateContextToStore(v10, *((PCCERT_CONTEXT *)&a2->dwCertEncodingType + v18), 1u, 0) )
      {
        if ( ++v18 >= v7 )
          goto LABEL_17;
      }
      LastError = GetLastError();
      matched = LastError;
      if ( LastError > 0 )
        matched = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_1808B5850 > 2 )
      {
        v55 = 387;
        v45 = "CertAddCertificateContextToStore failed";
        v42 = matched;
        v44 = "ValidateAadP2PCertificate";
        v43 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
        *(_QWORD *)&pPolicyPara.cbSize = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v24,
          (unsigned int)byte_180875309,
          v25,
          v26,
          (__int64)&pPolicyPara,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v55,
          (__int64)&v44,
          (__int64)&v45);
      }
    }
    else
    {
LABEL_17:
      memset_0(&pConfig, 0, 0x58u);
      pConfig.cbSize = 88;
      pConfig.hExclusiveRoot = v10;
      pConfig.dwFlags = 1;
      if ( CertCreateCertificateChainEngine(&pConfig, &phChainEngine) )
      {
        v45 = "1.3.6.1.5.5.7.3.1";
        *(_QWORD *)(&pChainPara.cbSize + 1) = 0;
        pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier = (LPSTR *)&v45;
        *(&pChainPara.RequestedUsage.dwType + 1) = 0;
        *(_QWORD *)&pChainPara.RequestedUsage.Usage.cUsageIdentifier = 1;
        pChainPara.cbSize = 32;
        if ( CertGetCertificateChain(phChainEngine, pCertContext, 0, 0, &pChainPara, 0x40000000u, 0, &pChainContext) )
        {
          *(_DWORD *)a5 = (*pChainContext->rgpChain)->TrustStatus.dwErrorStatus & 0xFEFFFFBF;
          matched = CertHelper::MatchAgainstSubjectName(
                      pCertContext,
                      a4,
                      (const unsigned __int16 *)&v55,
                      v27,
                      (unsigned __int64)pvPara);
          if ( matched >= 0 )
          {
            if ( (_BYTE)v55 )
            {
              v52 = 0;
              memset(&pChainPara, 0, 24);
              pPolicyPara.cbSize = 16;
              pPolicyPara.dwFlags = 3840;
              pChainPara.cbSize = 24;
              v51[0] = 24;
              pPolicyPara.pvExtraPolicyPara = v51;
              v51[1] = 2;
              v53 = 0;
              if ( CertVerifyCertificateChainPolicy(
                     (LPCSTR)4,
                     pChainContext,
                     &pPolicyPara,
                     (PCERT_CHAIN_POLICY_STATUS)&pChainPara) )
              {
                *a6 = *(&pChainPara.cbSize + 1);
              }
              else
              {
                matched = -2147467259;
                if ( (unsigned int)dword_1808B5850 > 2 )
                {
                  v55 = 491;
                  v47 = "CertVerifyCertificateChainPolicy failed";
                  v42 = -2147467259;
                  v45 = "ValidateAadP2PCertificate";
                  v44 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
                  v43 = "Error condition failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v34,
                    (unsigned int)qword_180875228,
                    v35,
                    v36,
                    (__int64)&v43,
                    (__int64)&v42,
                    (__int64)&v44,
                    (__int64)&v55,
                    (__int64)&v45,
                    (__int64)&v47);
                }
              }
            }
            else
            {
              *a6 = -2146762481;
            }
          }
          else if ( (unsigned int)dword_1808B5850 > 2 )
          {
            v55 = 452;
            v47 = "MatchAgainstSubjectName failed";
            v42 = matched;
            v45 = "ValidateAadP2PCertificate";
            v44 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
            v43 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              dword_1808B5850,
              (unsigned int)&dword_1808750FC,
              v32,
              v33,
              (__int64)&v43,
              (__int64)&v42,
              (__int64)&v44,
              (__int64)&v55,
              (__int64)&v45,
              (__int64)&v47);
          }
        }
        else
        {
          v28 = GetLastError();
          matched = v28;
          if ( v28 > 0 )
            matched = (unsigned __int16)v28 | 0x80070000;
          if ( (unsigned int)dword_1808B5850 > 2 )
          {
            v55 = 435;
            v44 = "CertGetCertificateChain failed";
            v42 = matched;
            v43 = "ValidateAadP2PCertificate";
            *(_QWORD *)&pPolicyPara.cbSize = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
            v47 = "Error condition failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v29,
              (unsigned int)byte_1808750B1,
              v30,
              v31,
              (__int64)&v47,
              (__int64)&v42,
              (__int64)&pPolicyPara,
              (__int64)&v55,
              (__int64)&v43,
              (__int64)&v44);
          }
        }
      }
      else
      {
        v19 = GetLastError();
        matched = v19;
        if ( v19 > 0 )
          matched = (unsigned __int16)v19 | 0x80070000;
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          v55 = 402;
          v45 = "CertCreateCertificateChainEngine failed";
          v42 = matched;
          v44 = "ValidateAadP2PCertificate";
          v43 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
          *(_QWORD *)&pPolicyPara.cbSize = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v20,
            (unsigned int)&byte_180875147,
            v21,
            v22,
            (__int64)&pPolicyPara,
            (__int64)&v42,
            (__int64)&v43,
            (__int64)&v55,
            (__int64)&v44,
            (__int64)&v45);
        }
      }
    }
  }
  else
  {
    v14 = GetLastError();
    matched = v14;
    if ( v14 > 0 )
      matched = (unsigned __int16)v14 | 0x80070000;
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      v55 = 379;
      v45 = "CertOpenStore failed";
      v42 = matched;
      v44 = "ValidateAadP2PCertificate";
      v43 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
      *(_QWORD *)&pPolicyPara.cbSize = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v15,
        (unsigned int)&byte_18087539F,
        v16,
        v17,
        (__int64)&pPolicyPara,
        (__int64)&v42,
        (__int64)&v43,
        (__int64)&v55,
        (__int64)&v44,
        (__int64)&v45);
    }
  }
LABEL_43:
  if ( phChainEngine )
    CertFreeCertificateChainEngine(phChainEngine);
  if ( v10 )
    CertCloseStore(v10, 0);
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  return (unsigned int)matched;
}

```

## disassembly

```asm
0x1803a31a0  push    rbp
0x1803a31a2  push    rbx
0x1803a31a3  push    rsi
0x1803a31a4  push    rdi
0x1803a31a5  push    r12
0x1803a31a7  push    r13
0x1803a31a9  push    r14
0x1803a31ab  push    r15
0x1803a31ad  lea     rbp, [rsp-38h]
0x1803a31b2  sub     rsp, 138h
0x1803a31b9  xor     r13d, r13d
0x1803a31bc  mov     rdi, r9
0x1803a31bf  mov     [rbp+70h+phChainEngine], r13
0x1803a31c3  mov     esi, r8d
0x1803a31c6  mov     [rbp+70h+pChainContext], r13
0x1803a31ca  mov     r14, rdx
0x1803a31cd  mov     byte ptr [rbp+70h+arg_0], r13b
0x1803a31d4  mov     r12, rcx
0x1803a31d7  mov     r15d, r13d
0x1803a31da  test    rcx, rcx
0x1803a31dd  jnz     loc_1803A3278
0x1803a31e3  mov     eax, cs:dword_1808B5850
0x1803a31e9  mov     ecx, 80070057h
0x1803a31ee  mov     ebx, ecx
0x1803a31f0  cmp     eax, 2
0x1803a31f3  jbe     loc_1803A392E
0x1803a31f9  lea     rax, aPdevicecertIsN; "pDeviceCert is not specified"
0x1803a3200  mov     [rbp+70h+arg_0], 173h
0x1803a320a  mov     qword ptr [rsp+170h+pPolicyPara.cbSize], rax
0x1803a320f  lea     rdx, byte_180875273
0x1803a3216  lea     rax, aValidateaadp2p; "ValidateAadP2PCertificate"
0x1803a321d  mov     [rsp+170h+var_118], rax
0x1803a3222  lea     rax, aOnecoreTermsrv_48; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1803a3229  mov     [rsp+170h+var_110], rax
0x1803a322e  lea     rax, aErrorCondition; "Error condition failed"
0x1803a3235  mov     [rsp+170h+var_108], rax
0x1803a323a  lea     rax, [rsp+170h+pPolicyPara]
0x1803a323f  mov     [rsp+170h+var_128], rax
0x1803a3244  lea     rax, [rsp+170h+var_118]
0x1803a3249  mov     [rsp+170h+var_130], rax
0x1803a324e  lea     rax, [rbp+70h+arg_0]
0x1803a3255  mov     [rsp+170h+ppChainContext], rax
0x1803a325a  lea     rax, [rsp+170h+var_110]
0x1803a325f  mov     [rsp+170h+pvReserved], rax
0x1803a3264  lea     rax, [rsp+170h+var_120]
0x1803a3269  mov     qword ptr [rsp+170h+dwFlags], rax
0x1803a326e  lea     rax, [rsp+170h+var_108]
0x1803a3273  jmp     loc_1803A3920
0x1803a3278  test    r14, r14
0x1803a327b  jnz     loc_1803A3316
0x1803a3281  mov     eax, cs:dword_1808B5850
0x1803a3287  mov     ecx, 80070057h
0x1803a328c  mov     ebx, ecx
0x1803a328e  cmp     eax, 2
0x1803a3291  jbe     loc_1803A392E
0x1803a3297  lea     rax, aPpp2prootcerts; "ppP2PRootCerts is not specified"
0x1803a329e  mov     [rbp+70h+arg_0], 174h
0x1803a32a8  mov     [rsp+170h+var_108], rax
0x1803a32ad  lea     rdx, word_1808752BE
0x1803a32b4  lea     rax, aValidateaadp2p; "ValidateAadP2PCertificate"
0x1803a32bb  mov     [rsp+170h+var_110], rax
0x1803a32c0  lea     rax, aOnecoreTermsrv_48; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1803a32c7  mov     [rsp+170h+var_118], rax
0x1803a32cc  lea     rax, aErrorCondition; "Error condition failed"
0x1803a32d3  mov     qword ptr [rsp+170h+pPolicyPara.cbSize], rax
0x1803a32d8  lea     rax, [rsp+170h+var_108]
0x1803a32dd  mov     [rsp+170h+var_128], rax
0x1803a32e2  lea     rax, [rsp+170h+var_110]
0x1803a32e7  mov     [rsp+170h+var_130], rax
0x1803a32ec  lea     rax, [rbp+70h+arg_0]
0x1803a32f3  mov     [rsp+170h+ppChainContext], rax
0x1803a32f8  lea     rax, [rsp+170h+var_118]
0x1803a32fd  mov     [rsp+170h+pvReserved], rax
0x1803a3302  lea     rax, [rsp+170h+var_120]
0x1803a3307  mov     qword ptr [rsp+170h+dwFlags], rax
0x1803a330c  lea     rax, [rsp+170h+pPolicyPara]
0x1803a3311  jmp     loc_1803A3920
0x1803a3316  test    rdi, rdi
0x1803a3319  jz      loc_1803A3892
0x1803a331f  cmp     [r9], r13w
0x1803a3323  jz      loc_1803A3892
0x1803a3329  xor     edx, edx; dwEncodingType
0x1803a332b  mov     [rsp+170h+pvPara], r13; pvPara
0x1803a3330  xor     r9d, r9d; dwFlags
0x1803a3333  xor     r8d, r8d; hCryptProv
0x1803a3336  lea     ecx, [rdx+2]; lpszStoreProvider
0x1803a3339  call    cs:__imp_CertOpenStore
0x1803a333f  mov     r15, rax
0x1803a3342  test    rax, rax
0x1803a3345  jnz     loc_1803A33F2
0x1803a334b  call    cs:__imp_GetLastError
0x1803a3351  mov     ebx, eax
0x1803a3353  test    eax, eax
0x1803a3355  jle     short loc_1803A3360
0x1803a3357  movzx   ebx, ax
0x1803a335a  or      ebx, 80070000h
0x1803a3360  mov     eax, cs:dword_1808B5850
0x1803a3366  cmp     eax, 2
0x1803a3369  jbe     loc_1803A392E
0x1803a336f  lea     rax, aCertopenstoreF; "CertOpenStore failed"
0x1803a3376  mov     [rbp+70h+arg_0], 17Bh
0x1803a3380  mov     [rsp+170h+var_108], rax
0x1803a3385  lea     rdx, byte_18087539F
0x1803a338c  lea     rax, aValidateaadp2p; "ValidateAadP2PCertificate"
0x1803a3393  mov     [rsp+170h+var_120], ebx
0x1803a3397  mov     [rsp+170h+var_110], rax
0x1803a339c  lea     rax, aOnecoreTermsrv_48; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1803a33a3  mov     [rsp+170h+var_118], rax
0x1803a33a8  lea     rax, aErrorCondition; "Error condition failed"
0x1803a33af  mov     qword ptr [rsp+170h+pPolicyPara.cbSize], rax
0x1803a33b4  lea     rax, [rsp+170h+var_108]
0x1803a33b9  mov     [rsp+170h+var_128], rax
0x1803a33be  lea     rax, [rsp+170h+var_110]
0x1803a33c3  mov     [rsp+170h+var_130], rax
0x1803a33c8  lea     rax, [rbp+70h+arg_0]
0x1803a33cf  mov     [rsp+170h+ppChainContext], rax
0x1803a33d4  lea     rax, [rsp+170h+var_118]
0x1803a33d9  mov     [rsp+170h+pvReserved], rax
0x1803a33de  lea     rax, [rsp+170h+var_120]
0x1803a33e3  mov     qword ptr [rsp+170h+dwFlags], rax
0x1803a33e8  lea     rax, [rsp+170h+pPolicyPara]
0x1803a33ed  jmp     loc_1803A3924
0x1803a33f2  mov     ebx, r13d
0x1803a33f5  test    esi, esi
0x1803a33f7  jz      short loc_1803A341D
0x1803a33f9  xor     r9d, r9d; ppStoreContext
0x1803a33fc  mov     edx, ebx
0x1803a33fe  mov     rcx, r15; hCertStore
0x1803a3401  mov     rdx, [r14+rdx*8]; pCertContext
0x1803a3405  lea     r8d, [r9+1]; dwAddDisposition
0x1803a3409  call    cs:__imp_CertAddCertificateContextToStore
0x1803a340f  test    eax, eax
0x1803a3411  jz      loc_1803A34FC
0x1803a3417  inc     ebx
0x1803a3419  cmp     ebx, esi
0x1803a341b  jb      short loc_1803A33F9
0x1803a341d  mov     ebx, 58h ; 'X'
0x1803a3422  lea     rcx, [rbp+70h+pConfig]; void *
0x1803a3426  mov     r8d, ebx; Size
0x1803a3429  xor     edx, edx; Val
0x1803a342b  call    memset_0
0x1803a3430  mov     [rbp+70h+pConfig.cbSize], ebx
0x1803a3433  lea     rdx, [rbp+70h+phChainEngine]; phChainEngine
0x1803a3437  mov     ebx, 1
0x1803a343c  mov     [rbp+70h+pConfig.hExclusiveRoot], r15
0x1803a3440  lea     rcx, [rbp+70h+pConfig]; pConfig
0x1803a3444  mov     [rbp+70h+pConfig.dwFlags], ebx
0x1803a3447  call    cs:__imp_CertCreateCertificateChainEngine
0x1803a344d  test    eax, eax
0x1803a344f  jnz     loc_1803A35A3
0x1803a3455  call    cs:__imp_GetLastError
0x1803a345b  mov     ebx, eax
0x1803a345d  test    eax, eax
0x1803a345f  jle     short loc_1803A346A
0x1803a3461  movzx   ebx, ax
0x1803a3464  or      ebx, 80070000h
0x1803a346a  mov     eax, cs:dword_1808B5850
0x1803a3470  cmp     eax, 2
0x1803a3473  jbe     loc_1803A392E
0x1803a3479  lea     rax, aCertcreatecert_1; "CertCreateCertificateChainEngine failed"
0x1803a3480  mov     [rbp+70h+arg_0], 192h
0x1803a348a  mov     [rsp+170h+var_108], rax
0x1803a348f  lea     rdx, byte_180875147
0x1803a3496  lea     rax, aValidateaadp2p; "ValidateAadP2PCertificate"
0x1803a349d  mov     [rsp+170h+var_120], ebx
0x1803a34a1  mov     [rsp+170h+var_110], rax
0x1803a34a6  lea     rax, aOnecoreTermsrv_48; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1803a34ad  mov     [rsp+170h+var_118], rax
0x1803a34b2  lea     rax, aErrorCondition; "Error condition failed"
0x1803a34b9  mov     qword ptr [rsp+170h+pPolicyPara.cbSize], rax
0x1803a34be  lea     rax, [rsp+170h+var_108]
0x1803a34c3  mov     [rsp+170h+var_128], rax
0x1803a34c8  lea     rax, [rsp+170h+var_110]
0x1803a34cd  mov     [rsp+170h+var_130], rax
0x1803a34d2  lea     rax, [rbp+70h+arg_0]
0x1803a34d9  mov     [rsp+170h+ppChainContext], rax
0x1803a34de  lea     rax, [rsp+170h+var_118]
0x1803a34e3  mov     [rsp+170h+pvReserved], rax
0x1803a34e8  lea     rax, [rsp+170h+var_120]
0x1803a34ed  mov     qword ptr [rsp+170h+dwFlags], rax
0x1803a34f2  lea     rax, [rsp+170h+pPolicyPara]
0x1803a34f7  jmp     loc_1803A3924
0x1803a34fc  call    cs:__imp_GetLastError
0x1803a3502  mov     ebx, eax
0x1803a3504  test    eax, eax
0x1803a3506  jle     short loc_1803A3511
0x1803a3508  movzx   ebx, ax
0x1803a350b  or      ebx, 80070000h
0x1803a3511  mov     eax, cs:dword_1808B5850
0x1803a3517  cmp     eax, 2
0x1803a351a  jbe     loc_1803A392E
0x1803a3520  lea     rax, aCertaddcertifi_0; "CertAddCertificateContextToStore failed"
0x1803a3527  mov     [rbp+70h+arg_0], 183h
0x1803a3531  mov     [rsp+170h+var_108], rax
0x1803a3536  lea     rdx, byte_180875309
0x1803a353d  lea     rax, aValidateaadp2p; "ValidateAadP2PCertificate"
0x1803a3544  mov     [rsp+170h+var_120], ebx
0x1803a3548  mov     [rsp+170h+var_110], rax
0x1803a354d  lea     rax, aOnecoreTermsrv_48; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1803a3554  mov     [rsp+170h+var_118], rax
0x1803a3559  lea     rax, aErrorCondition; "Error condition failed"
0x1803a3560  mov     qword ptr [rsp+170h+pPolicyPara.cbSize], rax
0x1803a3565  lea     rax, [rsp+170h+var_108]
0x1803a356a  mov     [rsp+170h+var_128], rax
0x1803a356f  lea     rax, [rsp+170h+var_110]
0x1803a3574  mov     [rsp+170h+var_130], rax
0x1803a3579  lea     rax, [rbp+70h+arg_0]
0x1803a3580  mov     [rsp+170h+ppChainContext], rax
0x1803a3585  lea     rax, [rsp+170h+var_118]
0x1803a358a  mov     [rsp+170h+pvReserved], rax
0x1803a358f  lea     rax, [rsp+170h+var_120]
0x1803a3594  mov     qword ptr [rsp+170h+dwFlags], rax
0x1803a3599  lea     rax, [rsp+170h+pPolicyPara]
0x1803a359e  jmp     loc_1803A3924
0x1803a35a3  mov     rcx, [rbp+70h+phChainEngine]; hChainEngine
0x1803a35a7  lea     rax, a136155731; "1.3.6.1.5.5.7.3.1"
0x1803a35ae  mov     [rsp+170h+var_108], rax
0x1803a35b3  xor     r9d, r9d; hAdditionalStore
0x1803a35b6  lea     rax, [rsp+170h+var_108]
0x1803a35bb  mov     qword ptr [rbp+70h+pChainPara+4], r13
0x1803a35bf  mov     [rbp+70h+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x1803a35c3  xor     r8d, r8d; pTime
0x1803a35c6  lea     rax, [rbp+70h+pChainContext]
0x1803a35ca  mov     dword ptr [rbp+70h+pChainPara.RequestedUsage+4], r13d
0x1803a35ce  mov     [rsp+170h+ppChainContext], rax; ppChainContext
0x1803a35d3  mov     rdx, r12; pCertContext
0x1803a35d6  mov     [rsp+170h+pvReserved], r13; pvReserved
0x1803a35db  lea     rax, [rbp+70h+pChainPara]
0x1803a35df  mov     [rsp+170h+dwFlags], 40000000h; dwFlags
0x1803a35e7  mov     [rsp+170h+pvPara], rax; unsigned __int64
0x1803a35ec  mov     qword ptr [rbp+70h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], rbx
0x1803a35f0  mov     [rbp+70h+pChainPara.cbSize], 20h ; ' '
0x1803a35f7  call    cs:__imp_CertGetCertificateChain
0x1803a35fd  test    eax, eax
0x1803a35ff  jnz     loc_1803A36AA
0x1803a3605  call    cs:__imp_GetLastError
0x1803a360b  mov     ebx, eax
0x1803a360d  test    eax, eax
0x1803a360f  jle     short loc_1803A361A
0x1803a3611  movzx   ebx, ax
0x1803a3614  or      ebx, 80070000h
0x1803a361a  mov     eax, cs:dword_1808B5850
0x1803a3620  cmp     eax, 2
0x1803a3623  jbe     loc_1803A392E
0x1803a3629  lea     rax, aCertgetcertifi_2; "CertGetCertificateChain failed"
0x1803a3630  mov     [rbp+70h+arg_0], 1B3h
0x1803a363a  mov     [rsp+170h+var_110], rax
0x1803a363f  lea     rdx, byte_1808750B1
0x1803a3646  lea     rax, aValidateaadp2p; "ValidateAadP2PCertificate"
0x1803a364d  mov     [rsp+170h+var_120], ebx
0x1803a3651  mov     [rsp+170h+var_118], rax
0x1803a3656  lea     rax, aOnecoreTermsrv_48; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1803a365d  mov     qword ptr [rsp+170h+pPolicyPara.cbSize], rax
0x1803a3662  lea     rax, aErrorCondition; "Error condition failed"
0x1803a3669  mov     [rbp+70h+var_F0], rax
0x1803a366d  lea     rax, [rsp+170h+var_110]
0x1803a3672  mov     [rsp+170h+var_128], rax
0x1803a3677  lea     rax, [rsp+170h+var_118]
0x1803a367c  mov     [rsp+170h+var_130], rax
0x1803a3681  lea     rax, [rbp+70h+arg_0]
0x1803a3688  mov     [rsp+170h+ppChainContext], rax
0x1803a368d  lea     rax, [rsp+170h+pPolicyPara]
0x1803a3692  mov     [rsp+170h+pvReserved], rax
0x1803a3697  lea     rax, [rsp+170h+var_120]
0x1803a369c  mov     qword ptr [rsp+170h+dwFlags], rax
0x1803a36a1  lea     rax, [rbp+70h+var_F0]
0x1803a36a5  jmp     loc_1803A3924
0x1803a36aa  mov     rax, [rbp+70h+pChainContext]
0x1803a36ae  lea     r8, [rbp+70h+arg_0]; unsigned __int16 *
0x1803a36b5  mov     rdx, rdi; String1
0x1803a36b8  mov     rcx, [rax+10h]
0x1803a36bc  mov     rax, [rcx]
0x1803a36bf  mov     ecx, [rax+4]
0x1803a36c2  mov     rax, [rbp+70h+arg_20]
0x1803a36c9  and     ecx, 0FEFFFFBFh
0x1803a36cf  mov     [rax], ecx
0x1803a36d1  mov     rcx, r12; pCertContext
0x1803a36d4  call    ?MatchAgainstSubjectName@CertHelper@@YAJPEBU_CERT_CONTEXT@@PEBGAEA_N_K@Z; CertHelper::MatchAgainstSubjectName(_CERT_CONTEXT const *,ushort const *,bool &,unsigned __int64)
0x1803a36d9  mov     ebx, eax
0x1803a36db  test    eax, eax
0x1803a36dd  jns     loc_1803A3773
0x1803a36e3  mov     ecx, cs:dword_1808B5850
0x1803a36e9  cmp     ecx, 2
0x1803a36ec  jbe     loc_1803A392E
0x1803a36f2  lea     rax, aMatchagainstsu; "MatchAgainstSubjectName failed"
0x1803a36f9  mov     [rbp+70h+arg_0], 1C4h
0x1803a3703  mov     [rbp+70h+var_F0], rax
0x1803a3707  lea     rdx, dword_1808750FC
0x1803a370e  lea     rax, aValidateaadp2p; "ValidateAadP2PCertificate"
0x1803a3715  mov     [rsp+170h+var_120], ebx
0x1803a3719  mov     [rsp+170h+var_108], rax
0x1803a371e  lea     rax, aOnecoreTermsrv_48; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1803a3725  mov     [rsp+170h+var_110], rax
0x1803a372a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1803a3731  mov     [rsp+170h+var_118], rax
0x1803a3736  lea     rax, [rbp+70h+var_F0]
0x1803a373a  mov     [rsp+170h+var_128], rax
0x1803a373f  lea     rax, [rsp+170h+var_108]
0x1803a3744  mov     [rsp+170h+var_130], rax
0x1803a3749  lea     rax, [rbp+70h+arg_0]
  ... truncated ...
```
