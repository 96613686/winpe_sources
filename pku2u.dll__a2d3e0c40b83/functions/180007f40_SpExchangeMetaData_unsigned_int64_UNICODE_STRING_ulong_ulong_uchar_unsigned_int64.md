# SpExchangeMetaData(unsigned __int64,_UNICODE_STRING *,ulong,ulong,uchar *,unsigned __int64 *)

- ea: `0x180007f40`
- end: `0x180009065`
- name: `?SpExchangeMetaData@@YAJ_KPEAU_UNICODE_STRING@@KKPEAEPEA_K@Z`
- size: `4389`
- prototype: `__int64 __fastcall(struct _PKU2U_SECONDARY_CREDENTIAL *, struct _UNICODE_STRING *, unsigned int, int, unsigned __int8 *, struct _CERT_CONTEXT **)`
- caller_count: `0`
- callee_count: `31`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003700`
- `0x180004d60`
- `0x1800052d0`
- `0x1800057f0`
- `0x180007dc8`
- `0x180007f40`
- `0x18000a340`
- `0x18000a6c0`
- `0x18000af80`
- `0x18000afc0`
- `0x18000b6c0`
- `0x180012820`
- `0x1800139e0`
- `0x180016f00`
- `0x180017820`
- `0x180017880`
- `0x1800178d0`
- `0x18001a1d0`
- `0x18001e368`
- `0x180020238`
- `0x1800210f0`
- `0x180021a54`
- `0x180023cb8`
- `0x180023ce0`
- `0x180023e70`
- `0x18002b158`
- `0x18002b4f8`
- `0x18002dc44`
- `0x18002dec4`
- `0x18002e234`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007ff3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800084a5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800085b5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008807`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007ff3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800084a5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800085b5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008807`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008799`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008feb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008feb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008de1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008de1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800081e9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800081e9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180008206`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180008206`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180008e2a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180008e2a`
- `MSASN1!ASN1_CreateDecoder` at `0x18000808e`
- `MSASN1!ASN1_CreateDecoder` at `0x18000808e`
- `MSASN1!ASN1_CloseDecoder` at `0x1800080d9`
- `MSASN1!ASN1_CloseDecoder` at `0x1800080d9`
- `MSASN1!ASN1_CreateModule` at `0x18000894a`
- `MSASN1!ASN1_CreateModule` at `0x18000894a`
- `MSASN1!ASN1_Decode` at `0x1800080c0`
- `MSASN1!ASN1_Decode` at `0x1800080c0`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180008679`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180008679`
- `ntdll!RtlAcquireResourceShared` at `0x18000861d`
- `ntdll!RtlAcquireResourceShared` at `0x18000861d`
- `ntdll!RtlFreeUnicodeString` at `0x1800083ef`
- `ntdll!RtlFreeUnicodeString` at `0x1800083ef`
- `ntdll!RtlEqualUnicodeString` at `0x180008585`
- `ntdll!RtlEqualUnicodeString` at `0x18000859e`
- `ntdll!RtlEqualUnicodeString` at `0x180008f29`
- `ntdll!RtlEqualUnicodeString` at `0x180008585`
- `ntdll!RtlEqualUnicodeString` at `0x18000859e`
- `ntdll!RtlEqualUnicodeString` at `0x180008f29`
- `ntdll!RtlLeaveCriticalSection` at `0x1800086e1`
- `ntdll!RtlLeaveCriticalSection` at `0x18000874a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800086e1`
- `ntdll!RtlLeaveCriticalSection` at `0x18000874a`
- `ntdll!RtlEnterCriticalSection` at `0x1800086c3`
- `ntdll!RtlEnterCriticalSection` at `0x1800086f4`
- `ntdll!RtlEnterCriticalSection` at `0x1800086c3`
- `ntdll!RtlEnterCriticalSection` at `0x1800086f4`
- `ntdll!NtSetInformationThread` at `0x18000828c`
- `ntdll!NtSetInformationThread` at `0x18000828c`
- `ntdll!NtOpenThreadToken` at `0x180008254`
- `ntdll!NtOpenThreadToken` at `0x180008254`
- `ntdll!RtlReleaseResource` at `0x18000868f`
- `ntdll!RtlReleaseResource` at `0x18000868f`
- `CRYPT32!CertFreeCertificateChain` at `0x180008728`
- `CRYPT32!CertFreeCertificateChain` at `0x180009017`
- `CRYPT32!CertFreeCertificateChain` at `0x180008728`
- `CRYPT32!CertFreeCertificateChain` at `0x180009017`
- `CRYPT32!CertFreeCertificateContext` at `0x180008413`
- `CRYPT32!CertFreeCertificateContext` at `0x180008f53`
- `CRYPT32!CertFreeCertificateContext` at `0x180008413`
- `CRYPT32!CertFreeCertificateContext` at `0x180008f53`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800082fb`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180008cac`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800082fb`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180008cac`
- `ext-ms-win-security-certpoleng-l1-1-0!PstGetCertificateChain` at `0x180008d24`
- `ext-ms-win-security-certpoleng-l1-1-0!PstGetCertificateChain` at `0x180008d24`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstGetCertificate` at `0x1800082c4`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstGetCertificate` at `0x1800082c4`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstGetNameIdentifierForCertificate` at `0x1800086a5`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstGetNameIdentifierForCertificate` at `0x1800086a5`

## pseudocode

```c
__int64 __fastcall SpExchangeMetaData(
        struct _PKU2U_SECONDARY_CREDENTIAL *a1,
        struct _UNICODE_STRING *a2,
        unsigned int a3,
        int a4,
        unsigned __int8 *a5,
        struct _CERT_CONTEXT **a6)
{
  struct _PKU2U_SECONDARY_CREDENTIAL *pCertInfo; // r13
  struct _CERT_CONTEXT *v7; // rdi
  int v11; // r12d
  __int64 v12; // rax
  _QWORD *hCertStore; // rax
  __int64 Module; // rax
  unsigned int v15; // eax
  int v16; // ebx
  int v17; // eax
  unsigned int v18; // esi
  DWORD v19; // ecx
  __int64 *v20; // r14
  _QWORD *i; // rax
  size_t v22; // rbx
  struct _CRYPTOAPI_BLOB *aIssuers; // rsi
  unsigned int v24; // r8d
  __int64 v25; // rax
  void *v26; // rsi
  void *v27; // r14
  int Context; // ebx
  bool v29; // sf
  NTSTATUS v30; // eax
  struct _UNICODE_STRING *p_pbCertEncoded; // rdx
  struct _CERT_CONTEXT *v32; // r14
  int v33; // eax
  struct _CERT_CONTEXT **v34; // r15
  struct _PKU2U_SECONDARY_CREDENTIAL *v35; // rsi
  HANDLE v36; // r15
  void (*v37)(void); // rax
  struct _CERT_CONTEXT *v39; // r9
  char v40; // r8
  BOOL v41; // ecx
  __int64 v42; // rdx
  struct _PKU2U_ASSOCIATED_CREDENTIAL *v43; // rcx
  __int64 v44; // rbx
  __int64 v45; // rax
  struct _PKU2U_LOGON_SESSION *v46; // rsi
  struct _PKU2U_LOGON_SESSION **v47; // rax
  struct _PKU2U_ASSOCIATED_CREDENTIAL *v48; // r12
  struct _RTL_CRITICAL_SECTION *v49; // r15
  char *v50; // r13
  char *v51; // r14
  struct _RTL_CRITICAL_SECTION *v52; // rsi
  char *v53; // rbx
  const CERT_CONTEXT *v54; // rcx
  const CERT_CHAIN_CONTEXT *v55; // rcx
  _QWORD *v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // r9
  PVOID *v59; // rcx
  PVOID *v60; // rcx
  struct _CRYPTOAPI_BLOB *v61; // rax
  __int64 v62; // rdx
  int CertFromCred; // eax
  CERT_CONTEXT *v64; // rax
  DWORD v65; // eax
  __int64 v66; // rdx
  NTSTATUS CertificateChain; // eax
  DWORD LastError; // eax
  int v69; // eax
  struct _CERT_CONTEXT *v70; // [rsp+68h] [rbp-98h]
  int v71; // [rsp+70h] [rbp-90h]
  WINBOOL IsMember; // [rsp+74h] [rbp-8Ch] BYREF
  PCCERT_CHAIN_CONTEXT ppCertChainContext; // [rsp+78h] [rbp-88h] BYREF
  struct _PKU2U_SECONDARY_CREDENTIAL *v74; // [rsp+80h] [rbp-80h]
  struct _CERT_CONTEXT *v75; // [rsp+88h] [rbp-78h] BYREF
  void *v76; // [rsp+90h] [rbp-70h] BYREF
  LARGE_INTEGER v77; // [rsp+98h] [rbp-68h] BYREF
  HANDLE hObject; // [rsp+A0h] [rbp-60h]
  void *TokenHandle; // [rsp+A8h] [rbp-58h] BYREF
  struct _PKU2U_ASSOCIATED_CREDENTIAL *v80; // [rsp+B0h] [rbp-50h] BYREF
  struct _PKU2U_LOGON_SESSION *v81; // [rsp+B8h] [rbp-48h]
  _SecPkgContext_IssuerListInfoEx pTrustedIssuers; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v83; // [rsp+D0h] [rbp-30h] BYREF
  PSID SidToCheck; // [rsp+D8h] [rbp-28h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING v86; // [rsp+E8h] [rbp-18h] BYREF
  UNICODE_STRING String1; // [rsp+F8h] [rbp-8h] BYREF
  UNICODE_STRING v88; // [rsp+108h] [rbp+8h] BYREF
  struct _UNICODE_STRING v89; // [rsp+118h] [rbp+18h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+128h] [rbp+28h] BYREF
  void *ThreadInformation; // [rsp+138h] [rbp+38h] BYREF
  __int64 *Buffer; // [rsp+140h] [rbp+40h] BYREF
  __int64 v93; // [rsp+150h] [rbp+50h] BYREF
  int v94; // [rsp+158h] [rbp+58h]
  _BYTE v95[20]; // [rsp+15Ch] [rbp+5Ch]
  __int128 v96; // [rsp+170h] [rbp+70h]
  __int128 v97; // [rsp+180h] [rbp+80h]
  __int128 v98; // [rsp+190h] [rbp+90h]
  __int64 v99; // [rsp+1A0h] [rbp+A0h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+1B0h] [rbp+B0h] BYREF

  pCertInfo = a1;
  v74 = a1;
  v7 = *a6;
  v75 = *a6;
  v76 = 0;
  pTrustedIssuers = 0;
  IsMember = 0;
  v11 = 0;
  v89 = 0;
  UnicodeString = 0;
  v81 = 0;
  hObject = 0;
  v71 = 0;
  ppCertChainContext = 0;
  v86 = 0;
  PerformanceCount.QuadPart = 0;
  v77.QuadPart = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids);
  QueryPerformanceCounter(&PerformanceCount);
  if ( v7 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&v7->pbCertEncoded);
    pCertInfo = *(struct _PKU2U_SECONDARY_CREDENTIAL **)&v7->cbCertEncoded;
    v74 = pCertInfo;
    Pku2uReferenceSecondaryCredential(pCertInfo);
  }
  else
  {
    if ( !pCertInfo )
    {
      v35 = 0;
      Context = -1073741816;
      QueryPerformanceCounter(&v77);
      v32 = 0;
      v39 = *a6;
      goto LABEL_84;
    }
    Pku2uReferenceSecondaryCredential(pCertInfo);
    v41 = a2 && a2->Length;
    Context = Pku2uAllocateContext(v41, pCertInfo, a2, a3, (struct _PKU2U_CONTEXT **)&v75);
    if ( Context < 0 )
    {
      v7 = v75;
      goto LABEL_80;
    }
    v7 = v75;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_qDDZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v75->cbCertEncoded + 24LL) + 28LL),
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v75->cbCertEncoded + 24LL) + 24LL),
        (__int64)&v75[2].pbCertEncoded);
    v42 = *(_QWORD *)&v7[2].dwCertEncodingType;
    String1.Buffer = L"HTTP";
    v88.Buffer = L"HTTPS";
    *(_QWORD *)&String1.Length = 655368;
    *(_QWORD *)&v88.Length = 786442;
    if ( v42
      && *(_WORD *)(v42 + 2) == 2
      && (unsigned __int16)(*(_WORD *)v42 - 1) <= 2u
      && (RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)(v42 + 8), 1u)
       || RtlEqualUnicodeString(&v88, (PCUNICODE_STRING)(*(_QWORD *)&v7[2].dwCertEncodingType + 8LL), 1u)) )
    {
      Context = -2146893053;
      QueryPerformanceCounter(&v77);
      v32 = 0;
      v39 = *a6;
      goto LABEL_97;
    }
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)&v7[8]) > 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        156,
        &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
        v7,
        v7[8].dwCertEncodingType);
    Context = -2146893054;
    goto LABEL_80;
  }
  v12 = *(_QWORD *)&v7->cbCertEncoded;
  if ( *(_DWORD *)(v12 + 32) )
  {
    hCertStore = v7->hCertStore;
    if ( hCertStore && hCertStore[20] )
    {
LABEL_135:
      v32 = 0;
      goto LABEL_46;
    }
  }
  else if ( v12 && *(_QWORD *)(v12 + 160) )
  {
    goto LABEL_135;
  }
  v83 = 0;
  if ( !a4 || !a5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids);
    v16 = 60;
    goto LABEL_122;
  }
  if ( fKRB5ModuleStarted )
  {
    Module = PKU2UMSG_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               49,
               off_180047350,
               off_1800471C0,
               off_180047030,
               qword_180049F80,
               846556016);
    PKU2UMSG_Module = Module;
  }
  v15 = ASN1_CreateDecoder(Module, &v83, 0, 0, 0);
  if ( v15 )
  {
    v59 = (PVOID *)WPP_GLOBAL_Control;
    v16 = 60;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v15);
        v59 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v59 != &WPP_GLOBAL_Control && (*((_BYTE *)v59 + 28) & 1) != 0 )
        WPP_SF_d(v59[2], 80, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, 60);
    }
    goto LABEL_122;
  }
  v16 = 0;
  v76 = 0;
  v17 = ASN1_Decode(v83, &v76, 30, 8, a5, a4);
  v18 = v17;
  if ( v17 < 0 )
  {
    v60 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        (unsigned int)v17);
      v60 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v18 == -1009 || v18 == -1002 )
    {
      if ( v60 != &WPP_GLOBAL_Control && (*((_BYTE *)v60 + 28) & 4) != 0 )
        WPP_SF_d(v60[2], 82, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, 30);
      v16 = -2147483647;
    }
    else
    {
      if ( v18 != -1011 && v60 != &WPP_GLOBAL_Control && (*((_BYTE *)v60 + 28) & 1) != 0 )
        WPP_SF_d(v60[2], 83, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v18);
      v16 = 60;
    }
    v76 = 0;
  }
  if ( v83 )
    ASN1_CloseDecoder();
  if ( v16 )
    goto LABEL_122;
  v19 = 0;
  v20 = (__int64 *)*((_QWORD *)v76 + 1);
  for ( i = v20; i; ++v19 )
    i = (_QWORD *)*i;
  v22 = 16LL * v19;
  pTrustedIssuers.cIssuers = v19;
  if ( v22 > 0xFFFFFFFF )
  {
    pTrustedIssuers.aIssuers = 0;
    goto LABEL_79;
  }
  if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
  {
    aIssuers = (struct _CRYPTOAPI_BLOB *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))((unsigned int)v22);
    goto LABEL_21;
  }
  v61 = (struct _CRYPTOAPI_BLOB *)(**((__int64 (__fastcall ***)(_QWORD))Pku2uGlobalBaseSSP + 31))((unsigned int)v22);
  aIssuers = v61;
  if ( !v61 )
  {
LABEL_21:
    pTrustedIssuers.aIssuers = aIssuers;
    if ( aIssuers )
      goto LABEL_22;
LABEL_79:
    Context = -1073741801;
    goto LABEL_80;
  }
  memset_0(v61, 0, v22);
  pTrustedIssuers.aIssuers = aIssuers;
LABEL_22:
  v24 = 0;
  if ( v20 )
  {
    while ( 1 )
    {
      v62 = v24++;
      v62 *= 2;
      *(&aIssuers->cbData + 2 * v62) = *((_DWORD *)v20 + 2);
      *((_QWORD *)&pTrustedIssuers.aIssuers->pbData + v62) = v20[2];
      v20 = (__int64 *)*v20;
      if ( !v20 )
        break;
      aIssuers = pTrustedIssuers.aIssuers;
    }
  }
  if ( *((_DWORD *)pCertInfo + 8) == 1 )
  {
    CertFromCred = Pku2uPopulateContextWithCredmanCreds((struct _PKU2U_CONTEXT *)v7);
    Context = CertFromCred;
    if ( CertFromCred < 0 )
    {
      v56 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_80;
      v57 = 157;
LABEL_169:
      v58 = (unsigned int)CertFromCred;
      goto LABEL_171;
    }
    if ( v7->pCertInfo )
    {
      Pku2uDereferenceSecondaryCredential(pCertInfo);
      pCertInfo = (struct _PKU2U_SECONDARY_CREDENTIAL *)v7->pCertInfo;
      v74 = pCertInfo;
      Pku2uReferenceSecondaryCredential(pCertInfo);
    }
  }
  if ( *((_DWORD *)pCertInfo + 8) )
  {
    if ( *(char *)v76 >= 0
      || (v16 = KerbConvertPrincipalNameToString(
                  &v89,
                  (unsigned int *)&IsMember,
                  (struct KERB_PRINCIPAL_NAME *)((char *)v76 + 24))) == 0 )
    {
      v25 = *((_QWORD *)pCertInfo + 3);
      v71 = 0;
      hObject = 0;
      SidToCheck = 0;
      v26 = *(void **)(v25 + 32);
      v27 = 0;
      *(_DWORD *)pIdentifierAuthority.Value = 0;
      *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
      IsMember = 0;
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
      {
        Context = 0;
        if ( !CheckTokenMembership(v26, SidToCheck, &IsMember) )
        {
          Context = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_145765ada38d35d83bd68130d412160b_Traceguids,
              (unsigned int)Context);
        }
      }
      else
      {
        Context = GetLastError();
      }
      if ( SidToCheck )
        FreeSid(SidToCheck);
      v29 = Context < 0;
      if ( Context > 0 )
      {
        Context = (unsigned __int16)Context | 0xC0070000;
        v29 = Context < 0;
      }
      if ( !v29 )
      {
        if ( IsMember )
        {
LABEL_37:
          p_pbCertEncoded = &v89;
          if ( *(_QWORD *)&v7[2].cbCertEncoded )
            p_pbCertEncoded = (struct _UNICODE_STRING *)&v7[2].pbCertEncoded;
          Context = IntPstGetCertificate(v7[1].cbCertEncoded, p_pbCertEncoded, &pTrustedIssuers, &ppCertChainContext);
          if ( Context >= 0 )
          {
            if ( v11 )
            {
              if ( !SetThreadToken(0, v27) )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  LastError = GetLastError();
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    11,
                    WPP_145765ada38d35d83bd68130d412160b_Traceguids,
                    LastError);
                }
                RevertToSelf();
              }
              v11 = 0;
              v71 = 0;
            }
            v70 = (struct _CERT_CONTEXT *)CertDuplicateCertificateContext((*(*ppCertChainContext->rgpChain)->rgpElement)->pCertContext);
            v32 = v70;
            v75 = v70;
            if ( v70 )
              goto LABEL_42;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
LABEL_202:
              Context = -1073741670;
              goto LABEL_81;
            }
            v65 = GetLastError();
            v66 = 165;
LABEL_201:
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v66, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, v65);
            goto LABEL_202;
          }
          v56 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v57 = 164;
            v58 = (unsigned int)Context;
LABEL_171:
            WPP_SF_d(v56[2], v57, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, v58);
          }
LABEL_80:
          v32 = 0;
          goto LABEL_81;
        }
        ThreadInformation = v26;
        TokenHandle = 0;
        Context = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
        if ( (int)(Context + 0x80000000) < 0 || Context == -1073741700 )
        {
          v11 = 1;
          v71 = 1;
          v30 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
          v27 = TokenHandle;
          Context = v30;
          hObject = TokenHandle;
          TokenHandle = 0;
        }
        else
        {
          v71 = 0;
          hObject = 0;
          if ( TokenHandle )
            CloseHandle(TokenHandle);
        }
      }
      if ( Context < 0 )
        goto LABEL_80;
      goto LABEL_37;
    }
LABEL_122:
    v32 = 0;
    Context = KerbMapKerbError(v16);
    if ( Context >= 0 )
    {
LABEL_49:
      v35 = v74;
      goto LABEL_50;
    }
    goto LABEL_81;
  }
  if ( (unsigned __int16)Pku2uMapCredsToProviderHResult(pCertInfo) )
    Context = (unsigned __int16)Pku2uMapCredsToProviderHResult(pCertInfo) | 0xC0070000;
  else
    Context = (unsigned __int16)Pku2uMapCredsToProviderHResult(pCertInfo);
  if ( Context < 0 )
  {
    v56 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_80;
    v57 = 158;
    goto LABEL_170;
  }
  if ( (unsigned __int16)GetUserNameWithDomainPrefixHResult(pCertInfo, &v86) )
    Context = (unsigned __int16)GetUserNameWithDomainPrefixHResult(pCertInfo, &v86) | 0xC0070000;
  else
    Context = (unsigned __int16)GetUserNameWithDomainPrefixHResult(pCertInfo, &v86);
  if ( Context < 0 )
  {
    v56 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_80;
    v57 = 159;
LABEL_170:
    v58 = (unsigned int)Context;
    goto LABEL_171;
  }
  if ( v86.Length )
  {
    KerbFreeString((struct _UNICODE_STRING *)&v7[4].pCertInfo);
    CertFromCred = KerbDuplicateStringEx((struct _UNICODE_STRING *)&v7[4].pCertInfo, &v86, 1u, 0);
    Context = CertFromCred;
    if ( CertFromCred < 0 )
    {
      v56 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_80;
      v57 = 160;
      goto LABEL_169;
    }
  }
  CertFromCred = Pku2uGetCertFromCred(pCertInfo, 0, 0);
  Context = CertFromCred;
  if ( CertFromCred < 0 )
  {
    v56 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_80;
    v57 = 161;
    goto LABEL_169;
  }
  v64 = (CERT_CONTEXT *)CertDuplicateCertificateContext(*((PCCERT_CONTEXT *)pCertInfo + 20));
  v70 = v64;
  v32 = v64;
  v75 = v64;
  if ( !v64 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_202;
    v65 = GetLastError();
    v66 = 162;
    goto LABEL_201;
  }
  CertificateChain = PstGetCertificateChain(v64, &pTrustedIssuers, &ppCertChainContext);
  if ( CertificateChain < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        163,
        &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
        (unsigned int)CertificateChain);
    Context = -2146893042;
    goto LABEL_81;
  }
LABEL_42:
  if ( *(_DWORD *)(*(_QWORD *)&v7->cbCertEncoded + 32LL) )
  {
    if ( v7[1].cbCertEncoded )
    {
      if ( Pku2uGlobalAlwaysPrompt )
      {
        v7[9].dwCertEncodingType = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2));
      }
    }
    if ( v7[9].dwCertEncodingType )
    {
      v7[9].pbCertEncoded = (BYTE *)ppCertChainContext;
      ppCertChainContext = 0;
      goto LABEL_46;
    }
    v43 = (struct _PKU2U_ASSOCIATED_CREDENTIAL *)v7->hCertStore;
    if ( v43 )
    {
      Pku2uDereferenceAssociatedCredential(v43);
      v7->hCertStore = 0;
    }
    v44 = *(_QWORD *)&v7->cbCertEncoded;
    RtlAcquireResourceShared(&Pku2uGlobalLogonSessionTableLock, 1u);
    v81 = 0;
    v99 = 0;
    v45 = *(_QWORD *)(v44 + 40);
    v46 = 0;
    v94 = 0;
    *(_OWORD *)&v95[4] = 0;
    *(_QWORD *)v95 = v45;
    Buffer = &v93;
    v93 = 0x5353455355554B50LL;
    v96 = 0;
    v97 = 0;
    v98 = 0;
    v47 = (struct _PKU2U_LOGON_SESSION **)RtlLookupElementGenericTableAvl(&Pku2uGlobalLogonSessionTable, &Buffer);
    if ( v47 )
    {
      v46 = *v47;
      v81 = *v47;
      Pku2uReferenceLogonSession(v81);
    }
    RtlReleaseResource(&Pku2uGlobalLogonSessionTableLock);
    if ( v46 )
    {
      Context = IntPstGetNameIdentifierForCertificate(v32, &UnicodeString);
      if ( Context < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            167,
            &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
            (unsigned int)Context);
      }
      else
      {
        v48 = 0;
        v80 = 0;
        v49 = (struct _RTL_CRITICAL_SECTION *)((char *)v46 + 40);
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v46 + 1);
        v50 = (char *)*((_QWORD *)v46 + 3);
        v51 = (char *)v46 + 24;
        while ( 1 )
        {
          v52 = 0;
          v53 = 0;
          if ( v50 == v51 )
            break;
          v80 = (struct _PKU2U_ASSOCIATED_CREDENTIAL *)v50;
          v53 = v50;
          v48 = (struct _PKU2U_ASSOCIATED_CREDENTIAL *)v50;
          if ( RtlEqualUnicodeString(&UnicodeString, (PCUNICODE_STRING)(v50 + 88), 1u) )
          {
            Pku2uReferenceAssociatedCredential((struct _PKU2U_ASSOCIATED_CREDENTIAL *)v50);
            v52 = (struct _RTL_CRITICAL_SECTION *)v50;
            break;
          }
          v50 = *(char **)v50;
          v48 = 0;
          v80 = 0;
        }
        RtlLeaveCriticalSection(v49);
        if ( v52 )
        {
          RtlEnterCriticalSection(v52 + 1);
          v54 = (const CERT_CONTEXT *)*((_QWORD *)v53 + 20);
          if ( v54 )
            CertFreeCertificateContext(v54);
          *((_QWORD *)v53 + 20) = v70;
          v32 = 0;
          v55 = (const CERT_CHAIN_CONTEXT *)*((_QWORD *)v53 + 21);
          if ( v55 )
          {
            CertFreeCertificateChain(v55);
            *((_QWORD *)v53 + 21) = 0;
          }
          *((_QWORD *)v53 + 21) = ppCertChainContext;
          ppCertChainContext = 0;
          RtlLeaveCriticalSection(v52 + 1);
          goto LABEL_115;
        }
        v69 = Pku2uAllocateAssociatedCredential(
                v81,
                &UnicodeString,
                (const struct _CERT_CONTEXT **)&v75,
                &ppCertChainContext,
                &v80);
        v32 = v75;
        Context = v69;
        if ( v69 >= 0 )
        {
          v48 = v80;
LABEL_115:
          v7->hCertStore = v48;
          goto LABEL_46;
        }
        pCertInfo = v74;
        v11 = v71;
      }
    }
    else
    {
      Context = -1073741729;
    }
LABEL_81:
    v34 = a6;
    goto LABEL_82;
  }
LABEL_46:
  v33 = 0;
  v34 = a6;
  if ( !*a6 )
  {
    *a6 = v7;
    v33 = 1;
    _InterlockedDecrement((volatile signed __int32 *)&v7[8]);
    v7 = 0;
  }
  v11 = v71;
  Context = 0;
  if ( !v33 )
    goto LABEL_49;
  pCertInfo = v74;
LABEL_82:
  QueryPerformanceCounter(&v77);
  v39 = *v34;
  if ( pCertInfo )
  {
LABEL_97:
    v40 = *((_BYTE *)pCertInfo + 32);
    v35 = v74;
    goto LABEL_85;
  }
  v35 = v74;
LABEL_84:
  v40 = -1;
LABEL_85:
  Pku2uLogProvider::LogExchangeMetadata(PerformanceCount, v77, v40, (struct _PKU2U_CONTEXT *)v39, Context);
LABEL_50:
  v36 = hObject;
  if ( v11 )
    Pku2uRevertImpersonation(hObject);
  if ( v36 )
    CloseHandle(v36);
  if ( v81 )
    Pku2uDereferenceLogonSession(v81);
  if ( v7 )
  {
    LODWORD(v7[1].hCertStore) = Context;
    _InterlockedDecrement((volatile signed __int32 *)&v7[8]);
    Pku2uDereferenceContext((struct _PKU2U_CONTEXT *)v7);
  }
  if ( pTrustedIssuers.aIssuers )
    Pku2uFree(pTrustedIssuers.aIssuers);
  if ( ppCertChainContext )
    CertFreeCertificateChain(ppCertChainContext);
  if ( v89.Buffer )
  {
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      v37 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL);
    else
      v37 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL);
    v37();
    v89 = 0;
  }
  RtlFreeUnicodeString(&UnicodeString);
  if ( v35 )
    Pku2uDereferenceSecondaryCredential(v35);
  if ( v76 )
    KerbFreeData(0x1Eu, v76);
  if ( v32 )
    CertFreeCertificateContext(v32);
  if ( v86.Buffer )
    basessp::BaseSSP::WSTFree(Pku2uGlobalBaseSSP, v86.Buffer);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      168,
      &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
      (unsigned int)Context);
  return (unsigned int)Context;
}

```

## disassembly

```asm
0x180007f40  push    rbp
0x180007f42  push    rbx
0x180007f43  push    rsi
0x180007f44  push    rdi
0x180007f45  push    r12
0x180007f47  push    r13
0x180007f49  push    r14
0x180007f4b  push    r15
0x180007f4d  lea     rbp, [rsp-0C8h]
0x180007f55  sub     rsp, 1C8h
0x180007f5c  mov     rax, cs:__security_cookie
0x180007f63  xor     rax, rsp
0x180007f66  mov     [rbp+100h+var_48], rax
0x180007f6d  mov     rax, [rbp+100h+arg_28]
0x180007f74  xorps   xmm0, xmm0
0x180007f77  mov     r14, [rbp+100h+arg_20]
0x180007f7e  mov     r13, rcx
0x180007f81  mov     [rbp+100h+var_180], rcx
0x180007f85  xorps   xmm1, xmm1
0x180007f88  xor     ecx, ecx
0x180007f8a  mov     [rsp+200h+var_1A0], rax
0x180007f8f  mov     rdi, [rax]
0x180007f92  mov     esi, r9d
0x180007f95  mov     [rbp+100h+var_178], rdi
0x180007f99  mov     r15d, r8d
0x180007f9c  mov     rbx, rdx
0x180007f9f  mov     [rbp+100h+var_170], rcx
0x180007fa3  movups  xmmword ptr [rbp+100h+pTrustedIssuers.aIssuers], xmm0
0x180007fa7  mov     [rsp+200h+IsMember], ecx
0x180007fab  mov     r12d, ecx
0x180007fae  movups  xmmword ptr [rbp+100h+var_E8.Length], xmm0
0x180007fb2  mov     [rsp+200h+var_198], rcx
0x180007fb7  movups  xmmword ptr [rbp+100h+UnicodeString.Length], xmm1
0x180007fbb  mov     [rbp+100h+var_148], rcx
0x180007fbf  mov     [rbp+100h+hObject], rcx
0x180007fc3  mov     [rsp+200h+var_190], ecx
0x180007fc7  mov     [rsp+200h+ppCertChainContext], rcx
0x180007fcc  movups  xmmword ptr [rbp+100h+var_118.Length], xmm0
0x180007fd0  mov     qword ptr [rbp+100h+PerformanceCount], rcx
0x180007fd4  mov     qword ptr [rbp+100h+var_168], rcx
0x180007fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fdf  lea     rax, WPP_GLOBAL_Control
0x180007fe6  cmp     rcx, rax
0x180007fe9  jnz     loc_18000846A
0x180007fef  lea     rcx, [rbp+100h+PerformanceCount]; lpPerformanceCount
0x180007ff3  call    cs:__imp_QueryPerformanceCounter
0x180007ff9  test    rdi, rdi
0x180007ffc  jz      loc_1800084D4
0x180008002  lock inc dword ptr [rdi+8]
0x180008006  mov     r13, [rdi+10h]
0x18000800a  mov     rcx, r13; struct _PKU2U_SECONDARY_CREDENTIAL *
0x18000800d  mov     [rbp+100h+var_180], r13
0x180008011  call    ?Pku2uReferenceSecondaryCredential@@YAXPEAU_PKU2U_SECONDARY_CREDENTIAL@@@Z; Pku2uReferenceSecondaryCredential(_PKU2U_SECONDARY_CREDENTIAL *)
0x180008016  lea     r9, WPP_GLOBAL_Control
0x18000801d  mov     eax, 1
0x180008022  lock xadd [rdi+140h], eax
0x18000802a  inc     eax
0x18000802c  cmp     eax, 1
0x18000802f  jg      loc_180008883
0x180008035  mov     rax, [rdi+10h]
0x180008039  cmp     [rax+20h], r12d
0x18000803d  jz      loc_1800088DB
0x180008043  mov     rax, [rdi+20h]
0x180008047  test    rax, rax
0x18000804a  jnz     loc_1800088C1
0x180008050  xor     r15d, r15d
0x180008053  mov     [rbp+100h+var_130], r15
0x180008057  test    esi, esi
0x180008059  jz      loc_180008FAA
0x18000805f  test    r14, r14
0x180008062  jz      loc_180008FAA
0x180008068  cmp     cs:?fKRB5ModuleStarted@@3HA, r12d; int fKRB5ModuleStarted
0x18000806f  jz      loc_1800088F2
0x180008075  mov     rax, cs:PKU2UMSG_Module
0x18000807c  xor     r9d, r9d
0x18000807f  mov     qword ptr [rsp+200h+nSubAuthority2], r15
0x180008084  xor     r8d, r8d
0x180008087  lea     rdx, [rbp+100h+var_130]
0x18000808b  mov     rcx, rax
0x18000808e  call    cs:__imp_ASN1_CreateDecoder
0x180008094  test    eax, eax
0x180008096  jnz     loc_18000895C
0x18000809c  mov     rcx, [rbp+100h+var_130]
0x1800080a0  lea     rdx, [rbp+100h+var_170]
0x1800080a4  mov     [rsp+200h+nSubAuthority3], esi
0x1800080a8  mov     r9d, 8
0x1800080ae  mov     r8d, 1Eh
0x1800080b4  mov     qword ptr [rsp+200h+nSubAuthority2], r14
0x1800080b9  mov     ebx, r15d
0x1800080bc  mov     [rbp+100h+var_170], r15
0x1800080c0  call    cs:__imp_ASN1_Decode
0x1800080c6  mov     esi, eax
0x1800080c8  test    eax, eax
0x1800080ca  js      loc_1800089CD
0x1800080d0  mov     rcx, [rbp+100h+var_130]
0x1800080d4  test    rcx, rcx
0x1800080d7  jz      short loc_1800080DF
0x1800080d9  call    cs:__imp_ASN1_CloseDecoder
0x1800080df  test    ebx, ebx
0x1800080e1  jnz     loc_1800087E1
0x1800080e7  mov     rax, [rbp+100h+var_170]
0x1800080eb  mov     ecx, r15d
0x1800080ee  mov     r14, [rax+8]
0x1800080f2  mov     rax, r14
0x1800080f5  test    r14, r14
0x1800080f8  jz      short loc_180008104
0x1800080fa  mov     rax, [rax]
0x1800080fd  inc     ecx
0x1800080ff  test    rax, rax
0x180008102  jnz     short loc_1800080FA
0x180008104  mov     ebx, ecx
0x180008106  shl     rbx, 4
0x18000810a  mov     [rbp+100h+pTrustedIssuers.cIssuers], ecx
0x18000810d  mov     eax, 0FFFFFFFFh
0x180008112  cmp     rbx, rax
0x180008115  ja      loc_18000848E
0x18000811b  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x180008122  cmp     dword ptr [rax+0D0h], 1
0x180008129  jnz     loc_180008A7B
0x18000812f  mov     rax, [rax+0F0h]
0x180008136  mov     ecx, ebx
0x180008138  mov     rax, [rax+180h]
0x18000813f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008144  mov     rsi, rax
0x180008147  mov     [rbp+100h+pTrustedIssuers.aIssuers], rsi
0x18000814b  test    rsi, rsi
0x18000814e  jz      loc_180008492
0x180008154  mov     r8d, r15d
0x180008157  test    r14, r14
0x18000815a  jnz     loc_180008AAE
0x180008160  cmp     dword ptr [r13+20h], 1
0x180008165  jz      loc_180008ADD
0x18000816b  cmp     [r13+20h], r12d
0x18000816f  jz      loc_180008B61
0x180008175  mov     r8, [rbp+100h+var_170]
0x180008179  test    byte ptr [r8], 80h
0x18000817d  jnz     loc_180008D6D
0x180008183  mov     rax, [r13+18h]
0x180008187  lea     rcx, [rbp+100h+pIdentifierAuthority]; pIdentifierAuthority
0x18000818e  xor     r9d, r9d; nSubAuthority1
0x180008191  mov     [rsp+200h+var_190], r15d
0x180008196  mov     r8d, 14h; nSubAuthority0
0x18000819c  mov     [rbp+100h+hObject], r15
0x1800081a0  mov     dl, 1; nSubAuthorityCount
0x1800081a2  mov     [rbp+100h+SidToCheck], r15
0x1800081a6  mov     rsi, [rax+20h]
0x1800081aa  mov     r14, r15
0x1800081ad  lea     rax, [rbp+100h+SidToCheck]
0x1800081b1  mov     dword ptr [rbp+100h+pIdentifierAuthority.Value], r12d
0x1800081b8  mov     [rsp+200h+pSid], rax; pSid
0x1800081bd  mov     [rsp+200h+nSubAuthority7], r15d; nSubAuthority7
0x1800081c2  mov     [rsp+200h+nSubAuthority6], r15d; nSubAuthority6
0x1800081c7  mov     [rsp+200h+nSubAuthority5], r15d; nSubAuthority5
0x1800081cc  mov     [rsp+200h+nSubAuthority4], r15d; nSubAuthority4
0x1800081d1  mov     [rsp+200h+nSubAuthority3], r15d; nSubAuthority3
0x1800081d6  mov     [rsp+200h+nSubAuthority2], r15d; nSubAuthority2
0x1800081db  mov     word ptr [rbp+100h+pIdentifierAuthority.Value+4], 500h
0x1800081e4  mov     [rsp+200h+IsMember], r15d
0x1800081e9  call    cs:__imp_AllocateAndInitializeSid
0x1800081ef  test    eax, eax
0x1800081f1  jz      loc_180008D8E
0x1800081f7  mov     rdx, [rbp+100h+SidToCheck]; SidToCheck
0x1800081fb  lea     r8, [rsp+200h+IsMember]; IsMember
0x180008200  mov     rcx, rsi; TokenHandle
0x180008203  mov     ebx, r15d
0x180008206  call    cs:__imp_CheckTokenMembership
0x18000820c  test    eax, eax
0x18000820e  jz      loc_180008D9B
0x180008214  mov     rcx, [rbp+100h+SidToCheck]; pSid
0x180008218  test    rcx, rcx
0x18000821b  jnz     loc_180008DE1
0x180008221  test    ebx, ebx
0x180008223  jle     short loc_180008230
0x180008225  movzx   ebx, bx
0x180008228  or      ebx, 0C0070000h
0x18000822e  test    ebx, ebx
0x180008230  js      short loc_1800082A0
0x180008232  cmp     [rsp+200h+IsMember], r12d
0x180008237  jnz     short loc_1800082A8
0x180008239  lea     r9, [rbp+100h+TokenHandle]; TokenHandle
0x18000823d  mov     [rbp+100h+ThreadInformation], rsi
0x180008241  mov     r8b, 1; OpenAsSelf
0x180008244  mov     [rbp+100h+TokenHandle], r15
0x180008248  mov     edx, 0Ch; DesiredAccess
0x18000824d  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180008254  call    cs:__imp_NtOpenThreadToken
0x18000825a  mov     ecx, 80000000h
0x18000825f  mov     ebx, eax
0x180008261  add     eax, ecx
0x180008263  test    ecx, eax
0x180008265  jz      loc_1800085D6
0x18000826b  mov     r12d, 1
0x180008271  lea     r8, [rbp+100h+ThreadInformation]; ThreadInformation
0x180008275  mov     r9d, 8; ThreadInformationLength
0x18000827b  mov     [rsp+200h+var_190], r12d
0x180008280  mov     edx, 5; ThreadInformationClass
0x180008285  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000828c  call    cs:__imp_NtSetInformationThread
0x180008292  mov     r14, [rbp+100h+TokenHandle]
0x180008296  mov     ebx, eax
0x180008298  mov     [rbp+100h+hObject], r14
0x18000829c  mov     [rbp+100h+TokenHandle], r15
0x1800082a0  test    ebx, ebx
0x1800082a2  js      loc_180008497
0x1800082a8  cmp     [rdi+60h], r15
0x1800082ac  lea     rax, [rdi+58h]
0x1800082b0  mov     ecx, [rdi+38h]
0x1800082b3  lea     rdx, [rbp+100h+var_E8]
0x1800082b7  cmovnz  rdx, rax
0x1800082bb  lea     r9, [rsp+200h+ppCertChainContext]
0x1800082c0  lea     r8, [rbp+100h+pTrustedIssuers]
0x1800082c4  call    cs:__imp_IntPstGetCertificate
0x1800082ca  mov     ebx, eax
0x1800082cc  test    eax, eax
0x1800082ce  js      loc_180008759
0x1800082d4  test    r12d, r12d
0x1800082d7  jnz     loc_180008794
0x1800082dd  lea     rsi, WPP_GLOBAL_Control
0x1800082e4  mov     rax, [rsp+200h+ppCertChainContext]
0x1800082e9  mov     rcx, [rax+10h]
0x1800082ed  mov     rax, [rcx]
0x1800082f0  mov     rcx, [rax+10h]
0x1800082f4  mov     rcx, [rcx]
0x1800082f7  mov     rcx, [rcx+8]; pCertContext
0x1800082fb  call    cs:__imp_CertDuplicateCertificateContext
0x180008301  mov     [rsp+200h+var_198], rax
0x180008306  mov     r14, rax
0x180008309  mov     [rbp+100h+var_178], rax
0x18000830d  test    rax, rax
0x180008310  jz      loc_180008E35
0x180008316  mov     rax, [rdi+10h]
0x18000831a  cmp     [rax+20h], r15d
0x18000831e  jz      short loc_180008348
0x180008320  cmp     [rdi+38h], r15d
0x180008324  jnz     loc_180008E54
0x18000832a  cmp     [rdi+168h], r15d
0x180008331  jz      loc_180008603
0x180008337  mov     rax, [rsp+200h+ppCertChainContext]
0x18000833c  mov     [rdi+170h], rax
0x180008343  mov     [rsp+200h+ppCertChainContext], r15
0x180008348  mov     eax, r15d
0x18000834b  mov     r15, [rsp+200h+var_1A0]
0x180008350  cmp     qword ptr [r15], 0
0x180008354  jz      loc_1800087BB
0x18000835a  mov     r12d, [rsp+200h+var_190]
0x18000835f  xor     ebx, ebx
0x180008361  test    eax, eax
0x180008363  jnz     loc_180008FA1
0x180008369  mov     rsi, [rbp+100h+var_180]
0x18000836d  mov     r15, [rbp+100h+hObject]
0x180008371  test    r12d, r12d
0x180008374  jnz     loc_180008FDB
0x18000837a  test    r15, r15
0x18000837d  jnz     loc_180008FE8
0x180008383  mov     rax, [rbp+100h+var_148]
0x180008387  test    rax, rax
0x18000838a  jnz     loc_180008787
0x180008390  test    rdi, rdi
0x180008393  jnz     loc_180008FF6
0x180008399  mov     rcx, [rbp+100h+pTrustedIssuers.aIssuers]; void *
0x18000839d  test    rcx, rcx
0x1800083a0  jnz     loc_18000900D
0x1800083a6  mov     rcx, [rsp+200h+ppCertChainContext]; pChainContext
0x1800083ab  test    rcx, rcx
0x1800083ae  jnz     loc_180009017
0x1800083b4  mov     rcx, [rbp+100h+var_E8.Buffer]
0x1800083b8  test    rcx, rcx
0x1800083bb  jz      short loc_1800083EB
0x1800083bd  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x1800083c4  cmp     dword ptr [rax+0D0h], 1
0x1800083cb  jnz     loc_1800087D1
0x1800083d1  mov     rax, [rax+0F0h]
0x1800083d8  mov     rax, [rax+188h]
0x1800083df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083e4  xorps   xmm0, xmm0
0x1800083e7  movups  xmmword ptr [rbp+100h+var_E8.Length], xmm0
0x1800083eb  lea     rcx, [rbp+100h+UnicodeString]; UnicodeString
0x1800083ef  call    cs:__imp_RtlFreeUnicodeString
0x1800083f5  test    rsi, rsi
0x1800083f8  jnz     loc_180009022
0x1800083fe  mov     rdx, [rbp+100h+var_170]; void *
0x180008402  test    rdx, rdx
0x180008405  jnz     loc_18000902F
0x18000840b  test    r14, r14
0x18000840e  jz      short loc_180008419
0x180008410  mov     rcx, r14; pCertContext
0x180008413  call    cs:__imp_CertFreeCertificateContext
0x180008419  mov     rdx, [rbp+100h+var_118.Buffer]; void *
0x18000841d  test    rdx, rdx
0x180008420  jz      short loc_18000842E
0x180008422  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180008429  call    ?WSTFree@BaseSSP@basessp@@QEAAXPEAX@Z; basessp::BaseSSP::WSTFree(void *)
0x18000842e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008435  lea     rax, WPP_GLOBAL_Control
0x18000843c  cmp     rcx, rax
0x18000843f  jnz     loc_18000903E
0x180008445  mov     eax, ebx
0x180008447  mov     rcx, [rbp+100h+var_48]
0x18000844e  xor     rcx, rsp; StackCookie
0x180008451  call    __security_check_cookie
  ... truncated ...
```
