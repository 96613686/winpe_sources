# RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,INFO_KIND,_CERT_CONTEXT const * * *,ulong *)

- ea: `0x1800264a8`
- end: `0x180026a1b`
- name: `?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22W4INFO_KIND@@PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1395`
- prototype: `static int __high(enum _CERTFICATE_LOCATION, const char *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum INFO_KIND, const struct _CERT_CONTEXT ***, unsigned int *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b3d0`
- `0x1800262f8`
- `0x180094198`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x18000bac0`
- `0x18000c550`
- `0x180017fd0`
- `0x18001b510`
- `0x18001b560`
- `0x1800264a8`
- `0x180026a24`
- `0x1800307c4`
- `0x180043ef8`
- `0x180044300`
- `0x1800945a8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002680c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180026850`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002680c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180026850`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800268dd`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800268dd`
- `CRYPT32!CertFreeCertificateContext` at `0x180026760`
- `CRYPT32!CertFreeCertificateContext` at `0x18002681b`
- `CRYPT32!CertFreeCertificateContext` at `0x18002686c`
- `CRYPT32!CertFreeCertificateContext` at `0x180026894`
- `CRYPT32!CertFreeCertificateContext` at `0x1800269be`
- `CRYPT32!CertFreeCertificateContext` at `0x180026760`
- `CRYPT32!CertFreeCertificateContext` at `0x18002681b`
- `CRYPT32!CertFreeCertificateContext` at `0x18002686c`
- `CRYPT32!CertFreeCertificateContext` at `0x180026894`
- `CRYPT32!CertFreeCertificateContext` at `0x1800269be`

## string_xrefs

- `0x18002677e`: `StringCompare`

## pseudocode

```c
__int64 __fastcall RegistrationCertStatus::GetCertificates(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4,
        __int64 a5,
        unsigned int a6,
        struct _CERT_CONTEXT ***a7,
        unsigned int *a8)
{
  unsigned int v8; // edi
  struct _CERT_CONTEXT **v10; // r14
  unsigned int v11; // r13d
  unsigned int v12; // r15d
  const unsigned __int16 *v13; // rdx
  int Certificates; // eax
  __int64 v15; // r12
  int v16; // eax
  unsigned int v17; // edx
  int TenantId; // eax
  const unsigned __int16 *v19; // r8
  BOOL v20; // esi
  __int64 j; // rbx
  const WCHAR *v22; // rsi
  int v23; // edi
  __int64 k; // rcx
  struct _CERT_CONTEXT *v25; // r8
  unsigned int v26; // ebx
  unsigned int v27; // ecx
  unsigned int v28; // edi
  int v29; // r15d
  unsigned int i; // esi
  LONG v31; // eax
  unsigned int v32; // ecx
  const CERT_CONTEXT *v33; // rcx
  unsigned __int16 *v34; // rdi
  unsigned __int16 *v35; // rsi
  __int64 InfoKindName; // rax
  __int64 m; // rdi
  __int64 v39; // [rsp+20h] [rbp-89h]
  struct _CERT_CONTEXT ***v40; // [rsp+28h] [rbp-81h]
  unsigned int *v41; // [rsp+30h] [rbp-79h]
  unsigned int v42; // [rsp+50h] [rbp-59h] BYREF
  struct _CERT_CONTEXT **v43; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v44; // [rsp+60h] [rbp-49h]
  unsigned __int16 *v45; // [rsp+68h] [rbp-41h] BYREF
  void *Block; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int16 *v47; // [rsp+78h] [rbp-31h] BYREF
  struct _CERT_CONTEXT ***v48; // [rsp+80h] [rbp-29h]
  unsigned int *v49; // [rsp+88h] [rbp-21h]
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-19h] BYREF

  v8 = a6;
  v10 = 0;
  v44 = a6;
  v11 = 0;
  v48 = a7;
  v49 = a8;
  v43 = 0;
  v42 = 0;
  Block = 0;
  v45 = 0;
  SystemTime = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( !a7 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertStatus::GetCertificates",
      L"pppCertContexts");
    v13 = L"pppCertContexts";
LABEL_7:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationCertStatus::GetCertificates", v13);
    goto LABEL_81;
  }
  if ( !a8 )
  {
    v12 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationCertStatus::GetCertificates", L"pdwCount");
    v13 = L"pdwCount";
    goto LABEL_7;
  }
  v41 = &v42;
  v40 = &v43;
  HIDWORD(v39) = HIDWORD(a5);
  Certificates = RegistrationCertStatus::GetCertificates(a1, &v43, a3);
  LODWORD(v47) = Certificates;
  v12 = Certificates;
  if ( Certificates < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationCertStatus::GetCertificates",
      L"RegistrationCertStatus::GetCertificates",
      (unsigned int)Certificates);
    v10 = v43;
    v11 = v42;
    goto LABEL_81;
  }
  v11 = v42;
  if ( a6 == 4 )
  {
    *a7 = v43;
    *a8 = v11;
LABEL_14:
    v12 = 0;
    goto LABEL_81;
  }
  if ( v42 == 1 )
  {
    if ( a6 && a6 != 3 )
    {
      Logger::TraceVerbose(
        (wchar_t *)L"%s: CertificateUtil::FindAllCertificatesByOidValue found just one certificate and recovery certificat"
                    "e is requested so returning CRYPT_E_NOT_FOUND.",
        L"RegistrationCertStatus::GetCertificates");
      v10 = v43;
      v12 = -2146885628;
      goto LABEL_81;
    }
    *a7 = v43;
    *a8 = 1;
    goto LABEL_14;
  }
  v15 = 0;
  v16 = IsEmptyString(a4);
  v10 = v43;
  if ( !v16 || a6 == 3 )
  {
    v26 = 0;
    LODWORD(v43) = v17;
    if ( a6 )
    {
      if ( a6 == v17 )
      {
LABEL_60:
        v28 = v17;
        if ( v11 > v17 )
        {
          v29 = (int)v43;
          do
          {
            if ( CompareFileTime(&v10[v28]->pCertInfo->NotBefore, &v10[v26]->pCertInfo->NotBefore) == v29 )
            {
              CertFreeCertificateContext(v10[v26]);
              v10[v26] = 0;
              v26 = v28;
            }
            else
            {
              CertFreeCertificateContext(v10[v28]);
              v10[v28] = 0;
            }
            v17 = 1;
            ++v28;
          }
          while ( v28 < v11 );
          v12 = (unsigned int)v47;
          if ( v26 )
          {
            *v10 = v10[v26];
            v10[v26] = 0;
          }
        }
        LODWORD(v15) = v17;
        if ( FileTimeToSystemTime(&(*v10)->pCertInfo->NotBefore, &SystemTime) )
        {
          v33 = *v10;
          v47 = 0;
          CertificateUtil::GetCertificateThumbprint(v33, &v47);
          v34 = L"N/A";
          v35 = v47;
          if ( v47 )
            v34 = v47;
          LODWORD(v41) = SystemTime.wMinute;
          LODWORD(v40) = SystemTime.wHour;
          LODWORD(v39) = SystemTime.wDay;
          Logger::TraceVerbose(
            (wchar_t *)L"%s: Returning certificate with UTC timestamp (YYYY-MM-DD HH:MM:SS.sss) %04u-%02u-%02u %02u:%02u:%"
                        "02u.%03u and thumbprint %s",
            L"RegistrationCertStatus::GetCertificates",
            SystemTime.wYear,
            SystemTime.wMonth,
            v39,
            v40,
            v41,
            SystemTime.wSecond,
            SystemTime.wMilliseconds,
            v34);
          operator delete(v35);
        }
LABEL_79:
        v8 = v44;
        goto LABEL_80;
      }
      v27 = a6 - v17 - v17;
      if ( v27 )
      {
        if ( v27 == v17 )
          goto LABEL_59;
      }
      else
      {
        for ( i = v17; i < v11; v26 = v32 )
        {
          v31 = CompareFileTime(&v10[i]->pCertInfo->NotBefore, &v10[v26]->pCertInfo->NotBefore);
          v32 = i;
          if ( v31 >= 0 )
            v32 = v26;
          ++i;
        }
        CertFreeCertificateContext(v10[v26]);
        v15 = v11 - 1;
        if ( v26 != (_DWORD)v15 )
          v10[v26] = v10[v15];
        v10[v15] = 0;
      }
LABEL_80:
      InfoKindName = GetInfoKindName(v8);
      Logger::TraceVerbose(
        (wchar_t *)L"%s: Returning %lu certificate(s) (found total of %lu certificate(s)). Requested infoKind is %s",
        L"RegistrationCertStatus::GetCertificates",
        (unsigned int)v15,
        v11,
        InfoKindName);
      *v48 = v10;
      v10 = 0;
      *v49 = v15;
      goto LABEL_81;
    }
LABEL_59:
    LODWORD(v43) = -1;
    goto LABEL_60;
  }
  TenantId = SortCertificatesInPlace((const struct _CERT_CONTEXT **const)v43, v11);
  v12 = TenantId;
  if ( TenantId >= 0 )
  {
    v20 = 0;
    for ( j = 0; ; j = v42 )
    {
      if ( (unsigned int)j >= v11 )
      {
        for ( k = 0; (unsigned int)k < v11; k = (unsigned int)(k + 1) )
        {
          v25 = v10[k];
          if ( v25 )
          {
            if ( (_DWORD)k != (_DWORD)v15 )
            {
              v10[v15] = v25;
              v10[k] = 0;
            }
            v15 = (unsigned int)(v15 + 1);
          }
        }
        goto LABEL_79;
      }
      if ( (_DWORD)j )
      {
        v23 = v20;
        operator delete(Block);
        v22 = v45;
        Block = v45;
        v45 = 0;
      }
      else
      {
        TenantId = RegistrationCertStatus::GetTenantId(*v10, (unsigned __int16 **)&Block, 0);
        v12 = TenantId;
        if ( TenantId < 0 )
          goto LABEL_46;
        v22 = (const WCHAR *)Block;
        v23 = 1;
      }
      v42 = j + 1;
      if ( (_DWORD)j == v11 - 1 )
      {
        v20 = 1;
        v45 = 0;
      }
      else
      {
        TenantId = RegistrationCertStatus::GetTenantId(v10[(unsigned int)(j + 1)], &v45, 0);
        v12 = TenantId;
        if ( TenantId < 0 )
        {
LABEL_46:
          v19 = L"RegistrationCertStatus::GetTenantId";
          goto LABEL_24;
        }
        LODWORD(v43) = 0;
        TenantId = StringCompare(v22, v45, 1u, (int *)&v43);
        v12 = TenantId;
        if ( TenantId < 0 )
        {
          v19 = L"StringCompare";
          goto LABEL_24;
        }
        v20 = (_DWORD)v43 == 0;
      }
      switch ( v44 )
      {
        case 0u:
          if ( v23 )
            continue;
LABEL_44:
          CertFreeCertificateContext(v10[j]);
          v10[j] = 0;
          continue;
        case 1u:
          v23 = !v20;
          break;
        case 2u:
          break;
        default:
          continue;
      }
      if ( v23 )
        goto LABEL_44;
    }
  }
  v19 = L"SortCertificatesInPlace";
LABEL_24:
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"RegistrationCertStatus::GetCertificates",
    v19,
    (unsigned int)TenantId);
LABEL_81:
  operator delete(v45);
  operator delete(Block);
  if ( v10 )
  {
    for ( m = 0; (unsigned int)m < v11; m = (unsigned int)(m + 1) )
    {
      CertFreeCertificateContext(v10[m]);
      v10[m] = 0;
    }
  }
  operator delete(v10);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetCertificates", v12);
  return v12;
}

```

## disassembly

```asm
0x1800264a8  mov     [rsp-8+arg_8], rbx
0x1800264ad  push    rbp
0x1800264ae  push    rsi
0x1800264af  push    rdi
0x1800264b0  push    r12
0x1800264b2  push    r13
0x1800264b4  push    r14
0x1800264b6  push    r15
0x1800264b8  lea     rbp, [rsp-7]
0x1800264bd  sub     rsp, 0B0h
0x1800264c4  mov     rax, cs:__security_cookie
0x1800264cb  xor     rax, rsp
0x1800264ce  mov     [rbp+37h+var_40], rax
0x1800264d2  mov     r12, [rbp+37h+arg_30]
0x1800264d6  xor     edx, edx
0x1800264d8  mov     rsi, [rbp+37h+arg_38]
0x1800264dc  xorps   xmm0, xmm0
0x1800264df  mov     edi, [rbp+37h+arg_28]
0x1800264e2  mov     rbx, r9
0x1800264e5  mov     rax, [rbp+37h+arg_20]
0x1800264e9  mov     r14d, edx
0x1800264ec  mov     [rbp+37h+var_80], edi
0x1800264ef  mov     r13d, edx
0x1800264f2  mov     [rbp+37h+var_60], r12
0x1800264f6  mov     [rbp+37h+var_58], rsi
0x1800264fa  mov     [rbp+37h+var_88], rdx
0x1800264fe  mov     [rbp+37h+var_90], edx
0x180026501  mov     [rbp+37h+Block], rdx
0x180026505  mov     [rbp+37h+var_78], rdx
0x180026509  movups  xmmword ptr [rbp+37h+SystemTime.wYear], xmm0
0x18002650d  test    r12, r12
0x180026510  jz      short loc_180026516
0x180026512  mov     [r12], rdx
0x180026516  test    rsi, rsi
0x180026519  jz      short loc_18002651D
0x18002651b  mov     [rsi], edx
0x18002651d  test    r12, r12
0x180026520  jnz     short loc_18002655A
0x180026522  lea     r8, aPppcertcontext; "pppCertContexts"
0x180026529  mov     r15d, 80070057h
0x18002652f  lea     rdx, aRegistrationce_19; "RegistrationCertStatus::GetCertificates"
0x180026536  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18002653d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180026542  lea     rdx, aPppcertcontext; "pppCertContexts"
0x180026549  lea     rcx, aRegistrationce_19; "RegistrationCertStatus::GetCertificates"
0x180026550  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180026555  jmp     loc_18002699C
0x18002655a  test    rsi, rsi
0x18002655d  jnz     short loc_180026588
0x18002655f  lea     r8, aPdwcount; "pdwCount"
0x180026566  mov     r15d, 80070057h
0x18002656c  lea     rdx, aRegistrationce_19; "RegistrationCertStatus::GetCertificates"
0x180026573  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18002657a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002657f  lea     rdx, aPdwcount; "pdwCount"
0x180026586  jmp     short loc_180026549
0x180026588  lea     rdx, [rbp+37h+var_90]
0x18002658c  mov     [rsp+0E0h+var_B0], rdx
0x180026591  lea     rdx, [rbp+37h+var_88]
0x180026595  mov     [rsp+0E0h+var_B8], rdx
0x18002659a  mov     [rsp+0E0h+var_C0], rax
0x18002659f  call    ?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z; RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,_CERT_CONTEXT const * * *,ulong *)
0x1800265a4  mov     dword ptr [rbp+37h+var_68], eax
0x1800265a7  mov     r15d, eax
0x1800265aa  test    eax, eax
0x1800265ac  jns     short loc_1800265D8
0x1800265ae  mov     r9d, eax
0x1800265b1  lea     r8, aRegistrationce_19; "RegistrationCertStatus::GetCertificates"
0x1800265b8  lea     rdx, aRegistrationce_19; "RegistrationCertStatus::GetCertificates"
0x1800265bf  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800265c6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800265cb  mov     r14, [rbp+37h+var_88]
0x1800265cf  mov     r13d, [rbp+37h+var_90]
0x1800265d3  jmp     loc_18002699C
0x1800265d8  mov     r13d, [rbp+37h+var_90]
0x1800265dc  cmp     edi, 4
0x1800265df  jnz     short loc_1800265F4
0x1800265e1  mov     rax, [rbp+37h+var_88]
0x1800265e5  mov     [r12], rax
0x1800265e9  mov     [rsi], r13d
0x1800265ec  xor     r15d, r15d
0x1800265ef  jmp     loc_18002699C
0x1800265f4  mov     edx, 1
0x1800265f9  cmp     r13d, edx
0x1800265fc  jnz     short loc_180026635
0x1800265fe  test    edi, edi
0x180026600  jz      short loc_180026629
0x180026602  cmp     edi, 3
0x180026605  jz      short loc_180026629
0x180026607  lea     rdx, aRegistrationce_19; "RegistrationCertStatus::GetCertificates"
0x18002660e  lea     rcx, aSCertificateut; "%s: CertificateUtil::FindAllCertificate"...
0x180026615  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18002661a  mov     r14, [rbp+37h+var_88]
0x18002661e  mov     r15d, 80092004h
0x180026624  jmp     loc_18002699C
0x180026629  mov     rax, [rbp+37h+var_88]
0x18002662d  mov     [r12], rax
0x180026631  mov     [rsi], edx
0x180026633  jmp     short loc_1800265EC
0x180026635  mov     rcx, rbx; unsigned __int16 *
0x180026638  xor     r12d, r12d
0x18002663b  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180026640  mov     r14, [rbp+37h+var_88]
0x180026644  test    eax, eax
0x180026646  jz      loc_1800267BE
0x18002664c  cmp     edi, 3
0x18002664f  jz      loc_1800267BE
0x180026655  mov     edx, r13d; unsigned int
0x180026658  mov     rcx, r14; struct _CERT_CONTEXT **
0x18002665b  call    ?SortCertificatesInPlace@@YAJQEAPEBU_CERT_CONTEXT@@K@Z; SortCertificatesInPlace(_CERT_CONTEXT const * * const,ulong)
0x180026660  mov     r15d, eax
0x180026663  test    eax, eax
0x180026665  jns     short loc_180026689
0x180026667  lea     r8, aSortcertificat; "SortCertificatesInPlace"
0x18002666e  mov     r9d, eax
0x180026671  lea     rdx, aRegistrationce_19; "RegistrationCertStatus::GetCertificates"
0x180026678  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18002667f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180026684  jmp     loc_18002699C
0x180026689  xor     esi, esi
0x18002668b  xor     ebx, ebx
0x18002668d  cmp     ebx, r13d
0x180026690  jnb     loc_18002678A
0x180026696  test    ebx, ebx
0x180026698  jnz     short loc_1800266BD
0x18002669a  mov     rcx, [r14]; struct _CERT_CONTEXT *
0x18002669d  lea     rdx, [rbp+37h+Block]; unsigned __int16 **
0x1800266a1  xor     r8d, r8d; int *
0x1800266a4  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x1800266a9  mov     r15d, eax
0x1800266ac  test    eax, eax
0x1800266ae  js      loc_180026772
0x1800266b4  mov     rsi, [rbp+37h+Block]
0x1800266b8  lea     edi, [rbx+1]
0x1800266bb  jmp     short loc_1800266D4
0x1800266bd  mov     rcx, [rbp+37h+Block]; Block
0x1800266c1  mov     edi, esi
0x1800266c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800266c8  mov     rsi, [rbp+37h+var_78]
0x1800266cc  mov     [rbp+37h+Block], rsi
0x1800266d0  mov     [rbp+37h+var_78], r12
0x1800266d4  lea     eax, [r13-1]
0x1800266d8  cmp     ebx, eax
0x1800266da  lea     eax, [rbx+1]
0x1800266dd  mov     [rbp+37h+var_90], eax
0x1800266e0  jnz     short loc_1800266ED
0x1800266e2  mov     esi, 1
0x1800266e7  mov     [rbp+37h+var_78], r12
0x1800266eb  jmp     short loc_18002673A
0x1800266ed  mov     rcx, [r14+rax*8]; struct _CERT_CONTEXT *
0x1800266f1  lea     rdx, [rbp+37h+var_78]; unsigned __int16 **
0x1800266f5  xor     r8d, r8d; int *
0x1800266f8  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x1800266fd  mov     r15d, eax
0x180026700  test    eax, eax
0x180026702  js      short loc_180026772
0x180026704  mov     rdx, [rbp+37h+var_78]; unsigned __int16 *
0x180026708  lea     r9, [rbp+37h+var_88]; int *
0x18002670c  mov     r8d, 1; unsigned int
0x180026712  mov     dword ptr [rbp+37h+var_88], r12d
0x180026716  mov     rcx, rsi; lpString1
0x180026719  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x18002671e  mov     r15d, eax
0x180026721  test    eax, eax
0x180026723  js      short loc_18002677E
0x180026725  cmp     dword ptr [rbp+37h+var_88], r12d
0x180026729  jnz     short loc_180026732
0x18002672b  mov     esi, 1
0x180026730  jmp     short loc_18002673A
0x180026732  mov     edx, [rbp+37h+var_90]
0x180026735  xor     esi, esi
0x180026737  mov     [rbp+37h+var_90], edx
0x18002673a  mov     ecx, [rbp+37h+var_80]
0x18002673d  test    ecx, ecx
0x18002673f  jz      short loc_180026758
0x180026741  sub     ecx, 1
0x180026744  jz      short loc_18002674D
0x180026746  cmp     ecx, 1
0x180026749  jz      short loc_180026752
0x18002674b  jmp     short loc_18002676A
0x18002674d  mov     edi, esi
0x18002674f  xor     edi, 1
0x180026752  test    edi, edi
0x180026754  jnz     short loc_18002675C
0x180026756  jmp     short loc_18002676A
0x180026758  test    edi, edi
0x18002675a  jnz     short loc_18002676A
0x18002675c  mov     rcx, [r14+rbx*8]; pCertContext
0x180026760  call    cs:__imp_CertFreeCertificateContext
0x180026766  mov     [r14+rbx*8], r12
0x18002676a  mov     ebx, [rbp+37h+var_90]
0x18002676d  jmp     loc_18002668D
0x180026772  lea     r8, aRegistrationce_21; "RegistrationCertStatus::GetTenantId"
0x180026779  jmp     loc_18002666E
0x18002677e  lea     r8, aStringcompare; "StringCompare"
0x180026785  jmp     loc_18002666E
0x18002678a  xor     ecx, ecx
0x18002678c  test    r13d, r13d
0x18002678f  jz      loc_180026963
0x180026795  mov     r8, [r14+rcx*8]
0x180026799  test    r8, r8
0x18002679c  jz      short loc_1800267B2
0x18002679e  cmp     ecx, r12d
0x1800267a1  jz      short loc_1800267AF
0x1800267a3  mov     [r14+r12*8], r8
0x1800267a7  mov     qword ptr [r14+rcx*8], 0
0x1800267af  inc     r12d
0x1800267b2  inc     ecx
0x1800267b4  cmp     ecx, r13d
0x1800267b7  jb      short loc_180026795
0x1800267b9  jmp     loc_180026963
0x1800267be  xor     ebx, ebx
0x1800267c0  mov     dword ptr [rbp+37h+var_88], edx
0x1800267c3  mov     ecx, edi
0x1800267c5  test    edi, edi
0x1800267c7  jz      short loc_1800267D9
0x1800267c9  sub     ecx, edx
0x1800267cb  jz      short loc_1800267E0
0x1800267cd  sub     ecx, edx
0x1800267cf  jz      short loc_18002682D
0x1800267d1  cmp     ecx, edx
0x1800267d3  jnz     loc_180026966
0x1800267d9  mov     dword ptr [rbp+37h+var_88], 0FFFFFFFFh
0x1800267e0  mov     edi, edx
0x1800267e2  cmp     r13d, edx
0x1800267e5  jbe     loc_1800268CB
0x1800267eb  mov     r15d, dword ptr [rbp+37h+var_88]
0x1800267ef  mov     esi, ebx
0x1800267f1  mov     r12d, edi
0x1800267f4  mov     rax, [r14+rsi*8]
0x1800267f8  mov     rdx, [rax+18h]
0x1800267fc  mov     rax, [r14+r12*8]
0x180026800  add     rdx, 40h ; '@'; lpFileTime2
0x180026804  mov     rcx, [rax+18h]
0x180026808  add     rcx, 40h ; '@'; lpFileTime1
0x18002680c  call    cs:__imp_CompareFileTime
0x180026812  cmp     eax, r15d
0x180026815  jnz     short loc_180026890
0x180026817  mov     rcx, [r14+rsi*8]; pCertContext
0x18002681b  call    cs:__imp_CertFreeCertificateContext
0x180026821  mov     qword ptr [r14+rsi*8], 0
0x180026829  mov     ebx, edi
0x18002682b  jmp     short loc_1800268A2
0x18002682d  mov     esi, edx
0x18002682f  cmp     r13d, edx
0x180026832  jbe     short loc_180026866
0x180026834  mov     eax, ebx
0x180026836  mov     rcx, [r14+rax*8]
0x18002683a  mov     eax, esi
0x18002683c  mov     rdx, [rcx+18h]
0x180026840  mov     rcx, [r14+rax*8]
0x180026844  add     rdx, 40h ; '@'; lpFileTime2
0x180026848  mov     rcx, [rcx+18h]
0x18002684c  add     rcx, 40h ; '@'; lpFileTime1
0x180026850  call    cs:__imp_CompareFileTime
0x180026856  test    eax, eax
0x180026858  mov     ecx, esi
0x18002685a  cmovns  ecx, ebx
0x18002685d  inc     esi
0x18002685f  mov     ebx, ecx
0x180026861  cmp     esi, r13d
0x180026864  jb      short loc_180026834
0x180026866  mov     esi, ebx
0x180026868  mov     rcx, [r14+rsi*8]; pCertContext
0x18002686c  call    cs:__imp_CertFreeCertificateContext
0x180026872  lea     r12d, [r13-1]
0x180026876  cmp     ebx, r12d
0x180026879  jz      short loc_180026883
0x18002687b  mov     rax, [r14+r12*8]
0x18002687f  mov     [r14+rsi*8], rax
0x180026883  mov     qword ptr [r14+r12*8], 0
0x18002688b  jmp     loc_180026966
0x180026890  mov     rcx, [r14+r12*8]; pCertContext
0x180026894  call    cs:__imp_CertFreeCertificateContext
0x18002689a  mov     qword ptr [r14+r12*8], 0
0x1800268a2  mov     edx, 1
0x1800268a7  add     edi, edx
0x1800268a9  cmp     edi, r13d
0x1800268ac  jb      loc_1800267EF
0x1800268b2  mov     r15d, dword ptr [rbp+37h+var_68]
0x1800268b6  test    ebx, ebx
0x1800268b8  jz      short loc_1800268CB
0x1800268ba  mov     ecx, ebx
0x1800268bc  mov     rax, [r14+rcx*8]
0x1800268c0  mov     [r14], rax
0x1800268c3  mov     qword ptr [r14+rcx*8], 0
0x1800268cb  mov     rax, [r14]
0x1800268ce  mov     r12d, edx
0x1800268d1  lea     rdx, [rbp+37h+SystemTime]; lpSystemTime
0x1800268d5  mov     rcx, [rax+18h]
0x1800268d9  add     rcx, 40h ; '@'; lpFileTime
0x1800268dd  call    cs:__imp_FileTimeToSystemTime
0x1800268e3  test    eax, eax
0x1800268e5  jz      short loc_180026963
0x1800268e7  mov     rcx, [r14]; pCertContext
0x1800268ea  lea     rdx, [rbp+37h+var_68]; unsigned __int16 **
0x1800268ee  mov     [rbp+37h+var_68], 0
0x1800268f6  call    ?GetCertificateThumbprint@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::GetCertificateThumbprint(_CERT_CONTEXT const *,ushort * *)
0x1800268fb  movzx   edx, [rbp+37h+SystemTime.wSecond]
0x1800268ff  lea     rdi, aNA; "N/A"
  ... truncated ...
```
