# IkeFindLocalCertChain

- ea: `0x18008f628`
- end: `0x18008fe90`
- name: `IkeFindLocalCertChain`
- size: `2152`
- prototype: ``
- caller_count: `6`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e3378`
- `0x1800e3d54`
- `0x1800e4224`
- `0x1800e5478`
- `0x1800e638c`
- `0x1800e66d8`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x1800061ec`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004a868`
- `0x18004aa3c`
- `0x18004d2a8`
- `0x180050850`
- `0x1800510ee`
- `0x18005bc40`
- `0x180088aac`
- `0x180089f48`
- `0x18008a210`
- `0x18008b6e0`
- `0x18008c8cc`
- `0x18008d148`
- `0x18008f628`
- `0x1800900cc`
- `0x180090584`
- `0x180090700`
- `0x180090874`
- `0x180091058`
- `0x180091270`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f714`
- `CRYPT32!CertFreeCertificateContext` at `0x18008f92c`
- `CRYPT32!CertFreeCertificateContext` at `0x18008f92c`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18008fe74`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18008fe74`
- `CRYPT32!CertOpenStore` at `0x18008f701`
- `CRYPT32!CertOpenStore` at `0x18008f701`
- `CRYPT32!CertFreeCertificateChain` at `0x18008f90e`
- `CRYPT32!CertFreeCertificateChain` at `0x18008f90e`
- `CRYPT32!CertCloseStore` at `0x18008f91e`
- `CRYPT32!CertCloseStore` at `0x18008f91e`
- `ncrypt!NCryptFreeObject` at `0x18008f95c`
- `ncrypt!NCryptFreeObject` at `0x18008f95c`

## string_xrefs

- `0x18008f71d`: `CertOpenStore`

## pseudocode

```c
__int64 __fastcall IkeFindLocalCertChain(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        unsigned int *a4,
        _BYTE *a5,
        NCRYPT_HANDLE *a6,
        __int64 a7,
        PCCERT_CONTEXT *a8)
{
  __int64 v9; // r12
  unsigned int v10; // edi
  const CERT_CONTEXT *v11; // r15
  void *v12; // r14
  DWORD LastError; // eax
  __int64 v14; // rcx
  __int64 SigKeyProv; // rbx
  int *v16; // rbx
  unsigned int AuthType; // r14d
  __int64 v18; // rcx
  __int64 v19; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v21; // rcx
  int TlsMmLuid; // eax
  __int64 v23; // rcx
  const WCHAR *v24; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 CertInfo; // r13
  __int64 v28; // r15
  __int64 OptionalLocalCertHashFromAcquire; // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  const CERT_CONTEXT *v32; // rbx
  __int64 v34; // rdi
  __int64 v35; // rbx
  __int64 v36; // rcx
  int v37; // eax
  __int64 v38; // rcx
  const WCHAR *v39; // rax
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rcx
  __int64 v43; // rdi
  __int64 v44; // rbx
  __int64 v45; // rcx
  int v46; // eax
  __int64 v47; // rcx
  const WCHAR *v48; // rax
  __int64 v49; // r8
  __int64 v50; // rdi
  __int64 v51; // rbx
  __int64 v52; // rcx
  int v53; // eax
  __int64 v54; // rcx
  const WCHAR *v55; // rax
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 v58; // rdi
  __int64 v59; // rbx
  __int64 v60; // rcx
  int v61; // eax
  __int64 v62; // rcx
  const WCHAR *v63; // rax
  __int64 v64; // r8
  __int64 v65; // r9
  const CERT_CONTEXT *v66; // rdi
  unsigned int *v67; // rcx
  PCCERT_CONTEXT v68; // rax
  unsigned int v69; // [rsp+28h] [rbp-D8h]
  unsigned int v70; // [rsp+28h] [rbp-D8h]
  char v71[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v72; // [rsp+54h] [rbp-ACh] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+58h] [rbp-A8h] BYREF
  HCERTSTORE v74; // [rsp+60h] [rbp-A0h]
  __int64 v75; // [rsp+68h] [rbp-98h] BYREF
  __int64 v76; // [rsp+70h] [rbp-90h] BYREF
  __int64 v77; // [rsp+78h] [rbp-88h]
  __int64 v78; // [rsp+80h] [rbp-80h]
  _QWORD *v79; // [rsp+88h] [rbp-78h]
  unsigned int *v80; // [rsp+90h] [rbp-70h]
  _BYTE *v81; // [rsp+98h] [rbp-68h]
  NCRYPT_HANDLE *v82; // [rsp+A0h] [rbp-60h]
  PCCERT_CONTEXT *v83; // [rsp+A8h] [rbp-58h]
  _DWORD v84[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v85; // [rsp+B8h] [rbp-48h]
  PCCERT_CHAIN_CONTEXT pChainContext[2]; // [rsp+C0h] [rbp-40h] BYREF
  char v87[8]; // [rsp+D0h] [rbp-30h] BYREF
  int v88; // [rsp+D8h] [rbp-28h]
  __int128 v89; // [rsp+F0h] [rbp-10h] BYREF
  const void *v90; // [rsp+108h] [rbp+8h] BYREF
  __int64 v91; // [rsp+120h] [rbp+20h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+128h] [rbp+28h]
  __int128 v93; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v94[32]; // [rsp+140h] [rbp+40h] BYREF
  __int64 *v95; // [rsp+160h] [rbp+60h]
  __int64 v96; // [rsp+168h] [rbp+68h]
  _BYTE v97[16]; // [rsp+170h] [rbp+70h] BYREF
  const char *v98; // [rsp+180h] [rbp+80h]
  __int64 v99; // [rsp+188h] [rbp+88h]

  v81 = a5;
  v82 = a6;
  v9 = 0;
  v10 = 0;
  v78 = a7;
  v79 = a3;
  v77 = a2;
  v83 = a8;
  v80 = a4;
  v76 = 0;
  pChainContext[0] = 0;
  v75 = 0;
  v72 = 0;
  v71[0] = 0;
  hObject = 0;
  memset_0(v87, 0, 0x50u);
  pCertContext = 0;
  v84[1] = 0;
  v93 = 0;
  v11 = 0;
  TraceLogHelper("IkeFindLocalCertChain", 1);
  v74 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x20001u, L"My");
  v12 = v74;
  if ( !v74 )
  {
    LastError = GetLastError();
    SigKeyProv = WfpReportSysErrorAsWinError(v14, "CertOpenStore", LastError, 1);
    goto LABEL_23;
  }
  v16 = (int *)(a1 + 584);
  if ( *(_DWORD *)(a1 + 584) == 2 )
    AuthType = *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 500LL);
  else
    AuthType = IkeGetAuthType(*(_QWORD *)(a1 + 744));
  IkeGetCertAuthFromPolicy(*(_QWORD *)(a1 + 736), AuthType, &v76);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v19 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v18);
    TlsMmLuid = IkeGetTlsMmLuid(v21);
    WPP_SF_iS(v19, 115, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, TlsMmLuid, TlsPeerAddr);
    v16 = (int *)(a1 + 584);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v91 = IkeGetTlsMmLuid(v18);
    v95 = &v91;
    v96 = 8;
    v24 = (const WCHAR *)IkeGetTlsPeerAddr(v23);
    tlgCreate1Sz_wchar_t((__int64)v97, v24);
    v99 = 30;
    v98 = "Constructing local cert chain";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_180173278,
      (unsigned __int8 *)byte_180156BAB,
      v25,
      v26,
      5,
      (__int64)v94);
  }
  CertInfo = IkeGetCertInfo(a1);
  v28 = v76;
  v88 = *v16;
  if ( v88 == 2 && *(_DWORD *)(v76 + 56) && (*(_DWORD *)(a1 + 592) & 0x80000) != 0 )
    OptionalLocalCertHashFromAcquire = IkeDownloadCertInfoFromUrl(
                                         (unsigned int *)(v76 + 56),
                                         *(_DWORD *)(v76 + 48) & 0x20,
                                         &v93,
                                         &v89,
                                         0,
                                         0,
                                         0,
                                         0);
  else
    OptionalLocalCertHashFromAcquire = IkeGetOptionalLocalCertHashFromAcquire(a1, 0, &v89);
  SigKeyProv = OptionalLocalCertHashFromAcquire;
  if ( OptionalLocalCertHashFromAcquire )
    goto LABEL_21;
  if ( !(_DWORD)v89 )
  {
    if ( *(_QWORD *)(CertInfo + 8) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v50 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v51 = IkeGetTlsPeerAddr(v30);
        v53 = IkeGetTlsMmLuid(v52);
        WPP_SF_iS(v50, 118, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v53, v51);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v91 = IkeGetTlsMmLuid(v30);
        v95 = &v91;
        v96 = 8;
        v55 = (const WCHAR *)IkeGetTlsPeerAddr(v54);
        tlgCreate1Sz_wchar_t((__int64)v97, v55);
        v99 = 25;
        v98 = "Taking into account CRPs";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_180156AE2,
          v56,
          v57,
          5,
          (__int64)v94);
      }
      SigKeyProv = IkeChainSelect(
                     (_DWORD)v74,
                     0,
                     *(_QWORD *)(CertInfo + 8),
                     *(_DWORD *)(CertInfo + 16),
                     v28,
                     AuthType,
                     (__int64)v87,
                     0,
                     (__int64)pChainContext);
    }
    if ( !SigKeyProv && *(_QWORD *)(CertInfo + 8) )
    {
      v12 = v74;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v58 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v59 = IkeGetTlsPeerAddr(v30);
        v61 = IkeGetTlsMmLuid(v60);
        WPP_SF_iS(v58, 119, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v61, v59);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v91 = IkeGetTlsMmLuid(v30);
        v95 = &v91;
        v96 = 8;
        v63 = (const WCHAR *)IkeGetTlsPeerAddr(v62);
        tlgCreate1Sz_wchar_t((__int64)v97, v63);
        v99 = 40;
        v98 = "Trying WITHOUT taking into account CRPs";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)&dword_180156AA4,
          v64,
          v65,
          5,
          (__int64)v94);
      }
      v70 = AuthType;
      v12 = v74;
      SigKeyProv = IkeChainSelect((_DWORD)v74, 0, 0, 0, v28, v70, (__int64)v87, v77, (__int64)pChainContext);
      if ( SigKeyProv )
        goto LABEL_22;
    }
LABEL_65:
    SigKeyProv = IkeCopyRootPolicyToSA(&v90, CertInfo + 64);
    if ( !SigKeyProv )
    {
      SigKeyProv = IkeEncodeCertChain(
                     (int)a1 + 584,
                     v28,
                     pChainContext[0],
                     (unsigned int)&v93,
                     (__int64)&v75,
                     (__int64)&v72,
                     (__int64)v71);
      if ( SigKeyProv
        || (v66 = (*(*pChainContext[0]->rgpChain)->rgpElement)->pCertContext, (SigKeyProv = IkeGetSigKeyProv(v66)) != 0)
        || (SigKeyProv = IkeAdjustMMLifetimeFromCert(a1, v66)) != 0
        || (SigKeyProv = IkeGetIDPayloadFromCert(v66, v78)) != 0 )
      {
        v9 = v75;
      }
      else
      {
        v67 = v80;
        v9 = v75;
        *v79 = v75;
        *v67 = v72;
        *v81 = v71[0];
        *v82 = hObject;
        v68 = CertDuplicateCertificateContext(v66);
        *v83 = v68;
      }
    }
    goto LABEL_22;
  }
  v84[0] = v89;
  v85 = *((_QWORD *)&v89 + 1);
  IkeCertFindByHash(v74, v84, &pCertContext);
  v32 = pCertContext;
  if ( pCertContext )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v34 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v35 = IkeGetTlsPeerAddr(v31);
      v37 = IkeGetTlsMmLuid(v36);
      WPP_SF_iS(v34, 116, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v37, v35);
      v32 = pCertContext;
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v91 = IkeGetTlsMmLuid(v31);
      v95 = &v91;
      v96 = 8;
      v39 = (const WCHAR *)IkeGetTlsPeerAddr(v38);
      tlgCreate1Sz_wchar_t((__int64)v97, v39);
      v99 = 47;
      v98 = "Found cert using certificate hash from acquire";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)&word_180156A66,
        v40,
        v41,
        5,
        (__int64)v94);
    }
    IkeDumpCert(v32);
    v69 = AuthType;
    v12 = v74;
    SigKeyProv = IkeChainSelect((_DWORD)v74, (_DWORD)v32, 0, 0, v28, v69, (__int64)v87, v77, (__int64)pChainContext);
    if ( SigKeyProv )
      goto LABEL_22;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v43 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v44 = IkeGetTlsPeerAddr(v42);
      v46 = IkeGetTlsMmLuid(v45);
      WPP_SF_iS(v43, 117, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v46, v44);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v91 = IkeGetTlsMmLuid(v42);
      v95 = &v91;
      v96 = 8;
      v48 = (const WCHAR *)IkeGetTlsPeerAddr(v47);
      tlgCreate1Sz_wchar_t((__int64)v97, v48);
      v99 = 53;
      v98 = "Found cert chain using certificate hash from acquire";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)qword_180156A28,
        v49,
        (__int64)"Found cert chain using certificate hash from acquire",
        5,
        (__int64)v94);
    }
    goto LABEL_65;
  }
  SigKeyProv = WfpReportSysErrorAsWinError(v31, "IkeFindLocalCertChain", 13806, 1);
LABEL_21:
  v12 = v74;
LABEL_22:
  v11 = pCertContext;
  v10 = v72;
LABEL_23:
  if ( pChainContext[0] )
    CertFreeCertificateChain(pChainContext[0]);
  if ( v12 )
    CertCloseStore(v12, 0);
  if ( v11 )
    CertFreeCertificateContext(v11);
  WfpMemFree((LPCVOID *)&v89 + 1);
  WfpMemFree((LPCVOID *)&v93 + 1);
  if ( SigKeyProv )
  {
    IkeFreeEncodedCertArray(v9, v10);
    if ( hObject )
      NCryptFreeObject(hObject);
  }
  TraceLogHelper("IkeFindLocalCertChain", 0);
  return IkeReturnError(SigKeyProv, "IkeFindLocalCertChain");
}

```

## disassembly

```asm
0x18008f628  push    rbp
0x18008f62a  push    rbx
0x18008f62b  push    rsi
0x18008f62c  push    rdi
0x18008f62d  push    r12
0x18008f62f  push    r13
0x18008f631  push    r14
0x18008f633  push    r15
0x18008f635  lea     rbp, [rsp-0A8h]
0x18008f63d  sub     rsp, 1A8h
0x18008f644  mov     rax, cs:__security_cookie
0x18008f64b  xor     rax, rsp
0x18008f64e  mov     [rbp+0E0h+var_50], rax
0x18008f655  mov     rax, [rbp+0E0h+arg_20]
0x18008f65c  xor     ebx, ebx
0x18008f65e  mov     [rbp+0E0h+var_148], rax
0x18008f662  mov     rsi, rcx
0x18008f665  mov     rax, [rbp+0E0h+arg_28]
0x18008f66c  lea     rcx, [rbp+0E0h+var_110]; void *
0x18008f670  mov     [rbp+0E0h+var_140], rax
0x18008f674  mov     r12d, ebx
0x18008f677  mov     rax, [rbp+0E0h+arg_30]
0x18008f67e  mov     edi, ebx
0x18008f680  mov     [rbp+0E0h+var_160], rax
0x18008f684  mov     rax, [rbp+0E0h+arg_38]
0x18008f68b  mov     [rbp+0E0h+var_158], r8
0x18008f68f  lea     r8d, [rbx+50h]; Size
0x18008f693  mov     [rsp+1E0h+var_168], rdx
0x18008f698  xor     edx, edx; Val
0x18008f69a  mov     [rbp+0E0h+var_138], rax
0x18008f69e  mov     [rbp+0E0h+var_150], r9
0x18008f6a2  mov     [rsp+1E0h+var_170], rbx
0x18008f6a7  mov     [rbp+0E0h+pChainContext], rbx
0x18008f6ab  mov     [rsp+1E0h+var_178], rbx
0x18008f6b0  mov     [rsp+1E0h+var_18C], ebx
0x18008f6b4  mov     [rsp+1E0h+var_190], bl
0x18008f6b8  mov     [rbp+0E0h+hObject], rbx
0x18008f6bc  call    memset_0
0x18008f6c1  xorps   xmm0, xmm0
0x18008f6c4  mov     [rsp+1E0h+pCertContext], rbx
0x18008f6c9  lea     r13d, [rbx+1]
0x18008f6cd  mov     [rbp+0E0h+var_12C], ebx
0x18008f6d0  mov     edx, r13d
0x18008f6d3  lea     rcx, aIkefindlocalce; "IkeFindLocalCertChain"
0x18008f6da  movups  [rbp+0E0h+var_B0], xmm0
0x18008f6de  mov     r15d, ebx
0x18008f6e1  call    TraceLogHelper
0x18008f6e6  lea     rax, aMy; "My"
0x18008f6ed  mov     r9d, 20001h; dwFlags
0x18008f6f3  xor     r8d, r8d; hCryptProv
0x18008f6f6  mov     [rsp+1E0h+pvPara], rax; pvPara
0x18008f6fb  mov     edx, r13d; dwEncodingType
0x18008f6fe  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x18008f701  call    cs:__imp_CertOpenStore
0x18008f707  mov     [rsp+1E0h+var_180], rax
0x18008f70c  mov     r14, rax
0x18008f70f  test    rax, rax
0x18008f712  jnz     short loc_18008F734
0x18008f714  call    cs:__imp_GetLastError
0x18008f71a  mov     r9d, r13d
0x18008f71d  lea     rdx, aCertopenstore_0; "CertOpenStore"
0x18008f724  mov     r8d, eax
0x18008f727  call    WfpReportSysErrorAsWinError
0x18008f72c  mov     rbx, rax
0x18008f72f  jmp     loc_18008F905
0x18008f734  lea     rbx, [rsi+248h]
0x18008f73b  cmp     dword ptr [rbx], 2
0x18008f73e  jnz     short loc_18008F750
0x18008f740  mov     rax, [rsi+450h]
0x18008f747  mov     r14d, [rax+1F4h]
0x18008f74e  jmp     short loc_18008F75F
0x18008f750  mov     rcx, [rsi+2E8h]
0x18008f757  call    IkeGetAuthType
0x18008f75c  mov     r14d, eax
0x18008f75f  mov     rcx, [rsi+2E0h]
0x18008f766  lea     r8, [rsp+1E0h+var_170]
0x18008f76b  mov     edx, r14d
0x18008f76e  call    IkeGetCertAuthFromPolicy
0x18008f773  mov     rdi, cs:WPP_GLOBAL_Control
0x18008f77a  lea     rax, WPP_GLOBAL_Control
0x18008f781  cmp     rdi, rax
0x18008f784  jz      short loc_18008F7C6
0x18008f786  cmp     byte ptr [rdi+19h], 4
0x18008f78a  jb      short loc_18008F7C6
0x18008f78c  test    byte ptr [rdi+1Ch], 10h
0x18008f790  jz      short loc_18008F7C6
0x18008f792  mov     rdi, [rdi+10h]
0x18008f796  call    IkeGetTlsPeerAddr
0x18008f79b  mov     rbx, rax
0x18008f79e  call    IkeGetTlsMmLuid
0x18008f7a3  mov     r9, rax
0x18008f7a6  mov     [rsp+1E0h+pvPara], rbx
0x18008f7ab  mov     edx, 73h ; 's'
0x18008f7b0  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x18008f7b7  mov     rcx, rdi
0x18008f7ba  call    WPP_SF_iS
0x18008f7bf  lea     rbx, [rsi+248h]
0x18008f7c6  mov     eax, cs:dword_180173278
0x18008f7cc  cmp     eax, 4
0x18008f7cf  jbe     short loc_18008F838
0x18008f7d1  call    IkeGetTlsMmLuid
0x18008f7d6  mov     [rbp+0E0h+var_C0], rax
0x18008f7da  lea     rax, [rbp+0E0h+var_C0]
0x18008f7de  mov     [rbp+0E0h+var_80], rax
0x18008f7e2  mov     [rbp+0E0h+var_78], 8
0x18008f7ea  call    IkeGetTlsPeerAddr
0x18008f7ef  mov     rdx, rax
0x18008f7f2  lea     rcx, [rbp+0E0h+var_70]
0x18008f7f6  call    _tlgCreate1Sz_wchar_t
0x18008f7fb  lea     rcx, aConstructingLo; "Constructing local cert chain"
0x18008f802  mov     [rbp+0E0h+var_58], 1Eh
0x18008f80d  lea     rax, [rbp+0E0h+var_A0]
0x18008f811  mov     [rbp+0E0h+var_60], rcx
0x18008f818  mov     [rsp+1E0h+var_1B8], rax
0x18008f81d  lea     rcx, dword_180173278
0x18008f824  lea     rdx, byte_180156BAB
0x18008f82b  mov     dword ptr [rsp+1E0h+pvPara], 5
0x18008f833  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18008f838  mov     rcx, rsi
0x18008f83b  call    IkeGetCertInfo
0x18008f840  mov     ecx, [rbx]
0x18008f842  mov     r13, rax
0x18008f845  mov     r15, [rsp+1E0h+var_170]
0x18008f84a  mov     [rbp+0E0h+var_108], ecx
0x18008f84d  cmp     ecx, 2
0x18008f850  jnz     short loc_18008F891
0x18008f852  lea     rcx, [r15+38h]
0x18008f856  cmp     [rcx], r12d
0x18008f859  jbe     short loc_18008F891
0x18008f85b  test    dword ptr [rsi+250h], 80000h
0x18008f865  jz      short loc_18008F891
0x18008f867  mov     edx, [r15+30h]
0x18008f86b  lea     r9, [rbp+0E0h+var_F0]
0x18008f86f  mov     [rsp+1E0h+var_1A8], r12
0x18008f874  lea     r8, [rbp+0E0h+var_B0]
0x18008f878  mov     [rsp+1E0h+var_1B0], r12
0x18008f87d  and     edx, 20h
0x18008f880  mov     [rsp+1E0h+var_1B8], r12
0x18008f885  mov     [rsp+1E0h+pvPara], r12
0x18008f88a  call    IkeDownloadCertInfoFromUrl
0x18008f88f  jmp     short loc_18008F89F
0x18008f891  lea     r8, [rbp+0E0h+var_F0]
0x18008f895  xor     edx, edx
0x18008f897  mov     rcx, rsi
0x18008f89a  call    IkeGetOptionalLocalCertHashFromAcquire
0x18008f89f  mov     rbx, rax
0x18008f8a2  test    rax, rax
0x18008f8a5  jnz     short loc_18008F8F7
0x18008f8a7  mov     eax, [rbp+0E0h+var_F0]
0x18008f8aa  test    eax, eax
0x18008f8ac  jz      loc_18008FB7C
0x18008f8b2  mov     rcx, [rsp+1E0h+var_180]
0x18008f8b7  lea     r8, [rsp+1E0h+pCertContext]
0x18008f8bc  mov     [rbp+0E0h+var_130], eax
0x18008f8bf  lea     rdx, [rbp+0E0h+var_130]
0x18008f8c3  mov     rax, [rbp+0E0h+var_E8]
0x18008f8c7  mov     [rbp+0E0h+var_128], rax
0x18008f8cb  call    IkeCertFindByHash
0x18008f8d0  mov     rbx, [rsp+1E0h+pCertContext]
0x18008f8d5  test    rbx, rbx
0x18008f8d8  jnz     loc_18008F9A2
0x18008f8de  lea     r9d, [rbx+1]
0x18008f8e2  mov     r8d, 35EEh
0x18008f8e8  lea     rdx, aIkefindlocalce; "IkeFindLocalCertChain"
0x18008f8ef  call    WfpReportSysErrorAsWinError
0x18008f8f4  mov     rbx, rax
0x18008f8f7  mov     r14, [rsp+1E0h+var_180]
0x18008f8fc  mov     r15, [rsp+1E0h+pCertContext]
0x18008f901  mov     edi, [rsp+1E0h+var_18C]
0x18008f905  mov     rcx, [rbp+0E0h+pChainContext]; pChainContext
0x18008f909  test    rcx, rcx
0x18008f90c  jz      short loc_18008F914
0x18008f90e  call    cs:__imp_CertFreeCertificateChain
0x18008f914  test    r14, r14
0x18008f917  jz      short loc_18008F924
0x18008f919  xor     edx, edx; dwFlags
0x18008f91b  mov     rcx, r14; hCertStore
0x18008f91e  call    cs:__imp_CertCloseStore
0x18008f924  test    r15, r15
0x18008f927  jz      short loc_18008F932
0x18008f929  mov     rcx, r15; pCertContext
0x18008f92c  call    cs:__imp_CertFreeCertificateContext
0x18008f932  lea     rcx, [rbp+0E0h+var_E8]
0x18008f936  call    WfpMemFree
0x18008f93b  lea     rcx, [rbp+0E0h+var_B0+8]
0x18008f93f  call    WfpMemFree
0x18008f944  test    rbx, rbx
0x18008f947  jz      short loc_18008F962
0x18008f949  mov     edx, edi
0x18008f94b  mov     rcx, r12
0x18008f94e  call    IkeFreeEncodedCertArray
0x18008f953  mov     rcx, [rbp+0E0h+hObject]; hObject
0x18008f957  test    rcx, rcx
0x18008f95a  jz      short loc_18008F962
0x18008f95c  call    cs:__imp_NCryptFreeObject
0x18008f962  xor     edx, edx
0x18008f964  lea     rcx, aIkefindlocalce; "IkeFindLocalCertChain"
0x18008f96b  call    TraceLogHelper
0x18008f970  lea     rdx, aIkefindlocalce; "IkeFindLocalCertChain"
0x18008f977  mov     rcx, rbx
0x18008f97a  call    IkeReturnError
0x18008f97f  mov     rcx, [rbp+0E0h+var_50]
0x18008f986  xor     rcx, rsp; StackCookie
0x18008f989  call    __security_check_cookie
0x18008f98e  add     rsp, 1A8h
0x18008f995  pop     r15
0x18008f997  pop     r14
0x18008f999  pop     r13
0x18008f99b  pop     r12
0x18008f99d  pop     rdi
0x18008f99e  pop     rsi
0x18008f99f  pop     rbx
0x18008f9a0  pop     rbp
0x18008f9a1  retn
0x18008f9a2  mov     rdi, cs:WPP_GLOBAL_Control
0x18008f9a9  lea     rax, WPP_GLOBAL_Control
0x18008f9b0  cmp     rdi, rax
0x18008f9b3  jz      short loc_18008F9F3
0x18008f9b5  cmp     byte ptr [rdi+19h], 4
0x18008f9b9  jb      short loc_18008F9F3
0x18008f9bb  test    byte ptr [rdi+1Ch], 10h
0x18008f9bf  jz      short loc_18008F9F3
0x18008f9c1  mov     rdi, [rdi+10h]
0x18008f9c5  call    IkeGetTlsPeerAddr
0x18008f9ca  mov     rbx, rax
0x18008f9cd  call    IkeGetTlsMmLuid
0x18008f9d2  mov     r9, rax
0x18008f9d5  mov     [rsp+1E0h+pvPara], rbx
0x18008f9da  mov     edx, 74h ; 't'
0x18008f9df  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x18008f9e6  mov     rcx, rdi
0x18008f9e9  call    WPP_SF_iS
0x18008f9ee  mov     rbx, [rsp+1E0h+pCertContext]
0x18008f9f3  mov     eax, cs:dword_180173278
0x18008f9f9  cmp     eax, 4
0x18008f9fc  jbe     short loc_18008FA65
0x18008f9fe  call    IkeGetTlsMmLuid
0x18008fa03  mov     [rbp+0E0h+var_C0], rax
0x18008fa07  lea     rax, [rbp+0E0h+var_C0]
0x18008fa0b  mov     [rbp+0E0h+var_80], rax
0x18008fa0f  mov     [rbp+0E0h+var_78], 8
0x18008fa17  call    IkeGetTlsPeerAddr
0x18008fa1c  mov     rdx, rax
0x18008fa1f  lea     rcx, [rbp+0E0h+var_70]
0x18008fa23  call    _tlgCreate1Sz_wchar_t
0x18008fa28  lea     rcx, aFoundCertUsing; "Found cert using certificate hash from "...
0x18008fa2f  mov     [rbp+0E0h+var_58], 2Fh ; '/'
0x18008fa3a  lea     rax, [rbp+0E0h+var_A0]
0x18008fa3e  mov     [rbp+0E0h+var_60], rcx
0x18008fa45  mov     [rsp+1E0h+var_1B8], rax
0x18008fa4a  lea     rcx, dword_180173278
0x18008fa51  lea     rdx, word_180156A66
0x18008fa58  mov     dword ptr [rsp+1E0h+pvPara], 5
0x18008fa60  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18008fa65  mov     rcx, rbx; pCertContext
0x18008fa68  call    IkeDumpCert
0x18008fa6d  lea     rax, [rbp+0E0h+pChainContext]
0x18008fa71  xor     r9d, r9d
0x18008fa74  mov     [rsp+1E0h+var_1A0], rax
0x18008fa79  xor     r8d, r8d
0x18008fa7c  mov     rax, [rsp+1E0h+var_168]
0x18008fa81  mov     rdx, rbx
0x18008fa84  mov     [rsp+1E0h+var_1A8], rax
0x18008fa89  lea     rax, [rbp+0E0h+var_110]
0x18008fa8d  mov     [rsp+1E0h+var_1B0], rax
0x18008fa92  mov     dword ptr [rsp+1E0h+var_1B8], r14d
0x18008fa97  mov     r14, [rsp+1E0h+var_180]
0x18008fa9c  mov     rcx, r14
0x18008fa9f  mov     [rsp+1E0h+pvPara], r15
0x18008faa4  call    IkeChainSelect
0x18008faa9  mov     rbx, rax
0x18008faac  test    rax, rax
0x18008faaf  jnz     loc_18008F8FC
0x18008fab5  mov     rdi, cs:WPP_GLOBAL_Control
0x18008fabc  lea     rax, WPP_GLOBAL_Control
0x18008fac3  cmp     rdi, rax
0x18008fac6  jz      short loc_18008FB01
0x18008fac8  cmp     byte ptr [rdi+19h], 4
0x18008facc  jb      short loc_18008FB01
0x18008face  test    byte ptr [rdi+1Ch], 10h
0x18008fad2  jz      short loc_18008FB01
0x18008fad4  mov     rdi, [rdi+10h]
0x18008fad8  call    IkeGetTlsPeerAddr
0x18008fadd  mov     rbx, rax
0x18008fae0  call    IkeGetTlsMmLuid
0x18008fae5  mov     r9, rax
0x18008fae8  mov     [rsp+1E0h+pvPara], rbx
0x18008faed  mov     edx, 75h ; 'u'
0x18008faf2  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x18008faf9  mov     rcx, rdi
0x18008fafc  call    WPP_SF_iS
0x18008fb01  mov     eax, cs:dword_180173278
0x18008fb07  cmp     eax, 4
0x18008fb0a  jbe     loc_18008FD97
0x18008fb10  call    IkeGetTlsMmLuid
0x18008fb15  mov     [rbp+0E0h+var_C0], rax
0x18008fb19  lea     rax, [rbp+0E0h+var_C0]
0x18008fb1d  mov     [rbp+0E0h+var_80], rax
0x18008fb21  mov     [rbp+0E0h+var_78], 8
0x18008fb29  call    IkeGetTlsPeerAddr
  ... truncated ...
```
