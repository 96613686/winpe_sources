# RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,INFO_KIND,_CERT_CONTEXT const * * *,ulong *)

- ea: `0x1800461d8`
- end: `0x180046722`
- name: `?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22W4INFO_KIND@@PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1354`
- prototype: `static int __high(enum _CERTFICATE_LOCATION, const char *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum INFO_KIND, const struct _CERT_CONTEXT ***, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006980`

## callees

- `0x1800073c0`
- `0x18000c190`
- `0x180010a60`
- `0x180016dc0`
- `0x18001a530`
- `0x180027278`
- `0x180027448`
- `0x18002aee4`
- `0x18002e664`
- `0x180044870`
- `0x180045e7c`
- `0x1800461d8`
- `0x180046728`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800465fe`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800465fe`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004652d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180046571`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004652d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180046571`
- `CRYPT32!CertFreeCertificateContext` at `0x180046481`
- `CRYPT32!CertFreeCertificateContext` at `0x18004653c`
- `CRYPT32!CertFreeCertificateContext` at `0x18004658d`
- `CRYPT32!CertFreeCertificateContext` at `0x1800465b5`
- `CRYPT32!CertFreeCertificateContext` at `0x180046481`
- `CRYPT32!CertFreeCertificateContext` at `0x18004653c`
- `CRYPT32!CertFreeCertificateContext` at `0x18004658d`
- `CRYPT32!CertFreeCertificateContext` at `0x1800465b5`

## string_xrefs

- `0x18004649f`: `StringCompare`

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
  const unsigned __int16 *v22; // rsi
  int v23; // edi
  unsigned int v24; // r8d
  __int64 k; // rcx
  struct _CERT_CONTEXT *v26; // r8
  unsigned int v27; // ebx
  unsigned int v28; // ecx
  unsigned int v29; // edi
  int v30; // r15d
  unsigned int i; // esi
  LONG v32; // eax
  unsigned int v33; // ecx
  const CERT_CONTEXT *v34; // rcx
  unsigned __int16 *v35; // rdi
  unsigned __int16 *v36; // rsi
  __int64 InfoKindName; // rax
  struct _CERT_CONTEXT ***v39; // [rsp+28h] [rbp-81h]
  unsigned int *v40; // [rsp+30h] [rbp-79h]
  unsigned int v41; // [rsp+50h] [rbp-59h] BYREF
  struct _CERT_CONTEXT **v42; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v43; // [rsp+60h] [rbp-49h]
  unsigned __int16 *v44; // [rsp+68h] [rbp-41h] BYREF
  void *Block; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int16 *v46; // [rsp+78h] [rbp-31h] BYREF
  struct _CERT_CONTEXT ***v47; // [rsp+80h] [rbp-29h]
  unsigned int *v48; // [rsp+88h] [rbp-21h]
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-19h] BYREF

  v8 = a6;
  v43 = a6;
  v10 = 0;
  v47 = a7;
  v11 = 0;
  v48 = a8;
  v42 = 0;
  v41 = 0;
  Block = 0;
  v44 = 0;
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
  v40 = &v41;
  v39 = &v42;
  Certificates = RegistrationCertStatus::GetCertificates();
  LODWORD(v46) = Certificates;
  v12 = Certificates;
  if ( Certificates < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationCertStatus::GetCertificates",
      L"RegistrationCertStatus::GetCertificates",
      (unsigned int)Certificates);
    v10 = v42;
    v11 = v41;
    goto LABEL_81;
  }
  v11 = v41;
  if ( a6 == 4 )
  {
    *a7 = v42;
    *a8 = v11;
LABEL_14:
    v12 = 0;
    goto LABEL_81;
  }
  if ( v41 == 1 )
  {
    if ( a6 && a6 != 3 )
    {
      Logger::TraceVerbose(
        L"%s: CertificateUtil::FindAllCertificatesByOidValue found just one certificate and recovery certificate is reques"
         "ted so returning CRYPT_E_NOT_FOUND.",
        L"RegistrationCertStatus::GetCertificates");
      v10 = v42;
      v12 = -2146885628;
      goto LABEL_81;
    }
    *a7 = v42;
    *a8 = 1;
    goto LABEL_14;
  }
  v15 = 0;
  v16 = IsEmptyString(a4);
  v10 = v42;
  if ( !v16 || a6 == 3 )
  {
    v27 = 0;
    LODWORD(v42) = v17;
    if ( a6 )
    {
      if ( a6 == v17 )
      {
LABEL_60:
        v29 = v17;
        if ( v11 > v17 )
        {
          v30 = (int)v42;
          do
          {
            if ( CompareFileTime(&v10[v29]->pCertInfo->NotBefore, &v10[v27]->pCertInfo->NotBefore) == v30 )
            {
              CertFreeCertificateContext(v10[v27]);
              v10[v27] = 0;
              v27 = v29;
            }
            else
            {
              CertFreeCertificateContext(v10[v29]);
              v10[v29] = 0;
            }
            v17 = 1;
            ++v29;
          }
          while ( v29 < v11 );
          v12 = (unsigned int)v46;
          if ( v27 )
          {
            *v10 = v10[v27];
            v10[v27] = 0;
          }
        }
        LODWORD(v15) = v17;
        if ( FileTimeToSystemTime(&(*v10)->pCertInfo->NotBefore, &SystemTime) )
        {
          v34 = *v10;
          v46 = 0;
          CertificateUtil::GetCertificateThumbprint(v34, &v46);
          v35 = L"N/A";
          v36 = v46;
          if ( v46 )
            v35 = v46;
          LODWORD(v40) = SystemTime.wMinute;
          LODWORD(v39) = SystemTime.wHour;
          Logger::TraceVerbose(
            L"%s: Returning certificate with UTC timestamp (YYYY-MM-DD HH:MM:SS.sss) %04u-%02u-%02u %02u:%02u:%02u.%03u and thumbprint %s",
            L"RegistrationCertStatus::GetCertificates",
            SystemTime.wYear,
            SystemTime.wMonth,
            SystemTime.wDay,
            v39,
            v40,
            SystemTime.wSecond,
            SystemTime.wMilliseconds,
            v35);
          operator delete(v36);
        }
LABEL_79:
        v8 = v43;
        goto LABEL_80;
      }
      v28 = a6 - v17 - v17;
      if ( v28 )
      {
        if ( v28 == v17 )
          goto LABEL_59;
      }
      else
      {
        for ( i = v17; i < v11; v27 = v33 )
        {
          v32 = CompareFileTime(&v10[i]->pCertInfo->NotBefore, &v10[v27]->pCertInfo->NotBefore);
          v33 = i;
          if ( v32 >= 0 )
            v33 = v27;
          ++i;
        }
        CertFreeCertificateContext(v10[v27]);
        v15 = v11 - 1;
        if ( v27 != (_DWORD)v15 )
          v10[v27] = v10[v15];
        v10[v15] = 0;
      }
LABEL_80:
      InfoKindName = GetInfoKindName(v8);
      Logger::TraceVerbose(
        L"%s: Returning %lu certificate(s) (found total of %lu certificate(s)). Requested infoKind is %s",
        L"RegistrationCertStatus::GetCertificates",
        (unsigned int)v15,
        v11,
        InfoKindName);
      *v47 = v10;
      v10 = 0;
      *v48 = v15;
      goto LABEL_81;
    }
LABEL_59:
    LODWORD(v42) = -1;
    goto LABEL_60;
  }
  TenantId = SortCertificatesInPlace((const struct _CERT_CONTEXT **const)v42, v11);
  v12 = TenantId;
  if ( TenantId >= 0 )
  {
    v20 = 0;
    for ( j = 0; ; j = v41 )
    {
      if ( (unsigned int)j >= v11 )
      {
        for ( k = 0; (unsigned int)k < v11; k = (unsigned int)(k + 1) )
        {
          v26 = v10[k];
          if ( v26 )
          {
            if ( (_DWORD)k != (_DWORD)v15 )
            {
              v10[v15] = v26;
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
        v22 = v44;
        Block = v44;
        v44 = 0;
      }
      else
      {
        TenantId = RegistrationCertStatus::GetTenantId(*v10, (unsigned __int16 **)&Block, 0);
        v12 = TenantId;
        if ( TenantId < 0 )
          goto LABEL_46;
        v22 = (const unsigned __int16 *)Block;
        v23 = 1;
      }
      v41 = j + 1;
      if ( (_DWORD)j == v11 - 1 )
      {
        v20 = 1;
        v44 = 0;
      }
      else
      {
        TenantId = RegistrationCertStatus::GetTenantId(v10[(unsigned int)(j + 1)], &v44, 0);
        v12 = TenantId;
        if ( TenantId < 0 )
        {
LABEL_46:
          v19 = L"RegistrationCertStatus::GetTenantId";
          goto LABEL_24;
        }
        LODWORD(v42) = 0;
        TenantId = StringCompare(v22, v44, v24, (int *)&v42);
        v12 = TenantId;
        if ( TenantId < 0 )
        {
          v19 = L"StringCompare";
          goto LABEL_24;
        }
        v20 = (_DWORD)v42 == 0;
      }
      if ( !v43 )
        break;
      if ( v43 == 1 )
      {
        v23 = !v20;
      }
      else if ( v43 != 2 )
      {
        continue;
      }
      if ( v23 )
        goto LABEL_44;
LABEL_45:
      ;
    }
    if ( v23 )
      goto LABEL_45;
LABEL_44:
    CertFreeCertificateContext(v10[j]);
    v10[j] = 0;
    goto LABEL_45;
  }
  v19 = L"SortCertificatesInPlace";
LABEL_24:
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"RegistrationCertStatus::GetCertificates",
    v19,
    (unsigned int)TenantId);
LABEL_81:
  operator delete(v44);
  operator delete(Block);
  CertificateUtil::FreeCertificates((const struct _CERT_CONTEXT **const)v10, v11);
  operator delete(v10);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetCertificates", v12);
  return v12;
}

```

## disassembly

```asm
0x1800461d8  mov     [rsp-8+arg_8], rbx
0x1800461dd  push    rbp
0x1800461de  push    rsi
0x1800461df  push    rdi
0x1800461e0  push    r12
0x1800461e2  push    r13
0x1800461e4  push    r14
0x1800461e6  push    r15
0x1800461e8  lea     rbp, [rsp-7]
0x1800461ed  sub     rsp, 0B0h
0x1800461f4  mov     rax, cs:__security_cookie
0x1800461fb  xor     rax, rsp
0x1800461fe  mov     [rbp+37h+var_40], rax
0x180046202  mov     r12, [rbp+37h+arg_30]
0x180046206  xor     eax, eax
0x180046208  mov     rsi, [rbp+37h+arg_38]
0x18004620c  xorps   xmm0, xmm0
0x18004620f  mov     edi, [rbp+37h+arg_28]
0x180046212  mov     rbx, r9
0x180046215  mov     [rbp+37h+var_80], edi
0x180046218  mov     r14d, eax
0x18004621b  mov     [rbp+37h+var_60], r12
0x18004621f  mov     r13d, eax
0x180046222  mov     [rbp+37h+var_58], rsi
0x180046226  mov     [rbp+37h+var_88], rax
0x18004622a  mov     [rbp+37h+var_90], eax
0x18004622d  mov     [rbp+37h+Block], rax
0x180046231  mov     [rbp+37h+var_78], rax
0x180046235  movups  xmmword ptr [rbp+37h+SystemTime.wYear], xmm0
0x180046239  test    r12, r12
0x18004623c  jz      short loc_180046242
0x18004623e  mov     [r12], rax
0x180046242  test    rsi, rsi
0x180046245  jz      short loc_180046249
0x180046247  mov     [rsi], eax
0x180046249  test    r12, r12
0x18004624c  jnz     short loc_180046286
0x18004624e  lea     r8, aPppcertcontext; "pppCertContexts"
0x180046255  mov     r15d, 80070057h
0x18004625b  lea     rdx, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x180046262  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180046269  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004626e  lea     rdx, aPppcertcontext; "pppCertContexts"
0x180046275  lea     rcx, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x18004627c  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180046281  jmp     loc_1800466BD
0x180046286  test    rsi, rsi
0x180046289  jnz     short loc_1800462B4
0x18004628b  lea     r8, aPdwcount; "pdwCount"
0x180046292  mov     r15d, 80070057h
0x180046298  lea     rdx, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x18004629f  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800462a6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800462ab  lea     rdx, aPdwcount; "pdwCount"
0x1800462b2  jmp     short loc_180046275
0x1800462b4  lea     rax, [rbp+37h+var_90]
0x1800462b8  mov     [rsp+0E0h+var_B0], rax
0x1800462bd  lea     rax, [rbp+37h+var_88]
0x1800462c1  mov     [rsp+0E0h+var_B8], rax
0x1800462c6  call    ?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z; RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,_CERT_CONTEXT const * * *,ulong *)
0x1800462cb  mov     dword ptr [rbp+37h+var_68], eax
0x1800462ce  mov     r15d, eax
0x1800462d1  test    eax, eax
0x1800462d3  jns     short loc_1800462FF
0x1800462d5  mov     r9d, eax
0x1800462d8  lea     r8, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x1800462df  lea     rdx, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x1800462e6  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x1800462ed  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800462f2  mov     r14, [rbp+37h+var_88]
0x1800462f6  mov     r13d, [rbp+37h+var_90]
0x1800462fa  jmp     loc_1800466BD
0x1800462ff  mov     r13d, [rbp+37h+var_90]
0x180046303  cmp     edi, 4
0x180046306  jnz     short loc_18004631B
0x180046308  mov     rax, [rbp+37h+var_88]
0x18004630c  mov     [r12], rax
0x180046310  mov     [rsi], r13d
0x180046313  xor     r15d, r15d
0x180046316  jmp     loc_1800466BD
0x18004631b  mov     edx, 1
0x180046320  cmp     r13d, edx
0x180046323  jnz     short loc_18004635C
0x180046325  test    edi, edi
0x180046327  jz      short loc_180046350
0x180046329  cmp     edi, 3
0x18004632c  jz      short loc_180046350
0x18004632e  lea     rdx, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x180046335  lea     rcx, aSCertificateut; "%s: CertificateUtil::FindAllCertificate"...
0x18004633c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180046341  mov     r14, [rbp+37h+var_88]
0x180046345  mov     r15d, 80092004h
0x18004634b  jmp     loc_1800466BD
0x180046350  mov     rax, [rbp+37h+var_88]
0x180046354  mov     [r12], rax
0x180046358  mov     [rsi], edx
0x18004635a  jmp     short loc_180046313
0x18004635c  mov     rcx, rbx; unsigned __int16 *
0x18004635f  xor     r12d, r12d
0x180046362  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180046367  mov     r14, [rbp+37h+var_88]
0x18004636b  test    eax, eax
0x18004636d  jz      loc_1800464DF
0x180046373  cmp     edi, 3
0x180046376  jz      loc_1800464DF
0x18004637c  mov     edx, r13d; unsigned int
0x18004637f  mov     rcx, r14; struct _CERT_CONTEXT **
0x180046382  call    ?SortCertificatesInPlace@@YAJQEAPEBU_CERT_CONTEXT@@K@Z; SortCertificatesInPlace(_CERT_CONTEXT const * * const,ulong)
0x180046387  mov     r15d, eax
0x18004638a  test    eax, eax
0x18004638c  jns     short loc_1800463B0
0x18004638e  lea     r8, aSortcertificat; "SortCertificatesInPlace"
0x180046395  mov     r9d, eax
0x180046398  lea     rdx, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x18004639f  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x1800463a6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800463ab  jmp     loc_1800466BD
0x1800463b0  xor     esi, esi
0x1800463b2  xor     ebx, ebx
0x1800463b4  cmp     ebx, r13d
0x1800463b7  jnb     loc_1800464AB
0x1800463bd  test    ebx, ebx
0x1800463bf  jnz     short loc_1800463E4
0x1800463c1  mov     rcx, [r14]; struct _CERT_CONTEXT *
0x1800463c4  lea     rdx, [rbp+37h+Block]; unsigned __int16 **
0x1800463c8  xor     r8d, r8d; int *
0x1800463cb  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x1800463d0  mov     r15d, eax
0x1800463d3  test    eax, eax
0x1800463d5  js      loc_180046493
0x1800463db  mov     rsi, [rbp+37h+Block]
0x1800463df  lea     edi, [rbx+1]
0x1800463e2  jmp     short loc_1800463FB
0x1800463e4  mov     rcx, [rbp+37h+Block]; Block
0x1800463e8  mov     edi, esi
0x1800463ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800463ef  mov     rsi, [rbp+37h+var_78]
0x1800463f3  mov     [rbp+37h+Block], rsi
0x1800463f7  mov     [rbp+37h+var_78], r12
0x1800463fb  lea     eax, [r13-1]
0x1800463ff  cmp     ebx, eax
0x180046401  lea     eax, [rbx+1]
0x180046404  mov     [rbp+37h+var_90], eax
0x180046407  jnz     short loc_180046414
0x180046409  mov     esi, 1
0x18004640e  mov     [rbp+37h+var_78], r12
0x180046412  jmp     short loc_18004645B
0x180046414  mov     rcx, [r14+rax*8]; struct _CERT_CONTEXT *
0x180046418  lea     rdx, [rbp+37h+var_78]; unsigned __int16 **
0x18004641c  xor     r8d, r8d; int *
0x18004641f  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x180046424  mov     r15d, eax
0x180046427  test    eax, eax
0x180046429  js      short loc_180046493
0x18004642b  mov     rdx, [rbp+37h+var_78]; unsigned __int16 *
0x18004642f  lea     r9, [rbp+37h+var_88]; int *
0x180046433  mov     rcx, rsi; unsigned __int16 *
0x180046436  mov     dword ptr [rbp+37h+var_88], r12d
0x18004643a  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x18004643f  mov     r15d, eax
0x180046442  test    eax, eax
0x180046444  js      short loc_18004649F
0x180046446  cmp     dword ptr [rbp+37h+var_88], r12d
0x18004644a  jnz     short loc_180046453
0x18004644c  mov     esi, 1
0x180046451  jmp     short loc_18004645B
0x180046453  mov     edx, [rbp+37h+var_90]
0x180046456  xor     esi, esi
0x180046458  mov     [rbp+37h+var_90], edx
0x18004645b  mov     ecx, [rbp+37h+var_80]
0x18004645e  test    ecx, ecx
0x180046460  jz      short loc_180046479
0x180046462  sub     ecx, 1
0x180046465  jz      short loc_18004646E
0x180046467  cmp     ecx, 1
0x18004646a  jnz     short loc_18004648B
0x18004646c  jmp     short loc_180046473
0x18004646e  mov     edi, esi
0x180046470  xor     edi, 1
0x180046473  test    edi, edi
0x180046475  jz      short loc_18004648B
0x180046477  jmp     short loc_18004647D
0x180046479  test    edi, edi
0x18004647b  jnz     short loc_18004648B
0x18004647d  mov     rcx, [r14+rbx*8]; pCertContext
0x180046481  call    cs:__imp_CertFreeCertificateContext
0x180046487  mov     [r14+rbx*8], r12
0x18004648b  mov     ebx, [rbp+37h+var_90]
0x18004648e  jmp     loc_1800463B4
0x180046493  lea     r8, aRegistrationce_3; "RegistrationCertStatus::GetTenantId"
0x18004649a  jmp     loc_180046395
0x18004649f  lea     r8, aStringcompare; "StringCompare"
0x1800464a6  jmp     loc_180046395
0x1800464ab  xor     ecx, ecx
0x1800464ad  test    r13d, r13d
0x1800464b0  jz      loc_180046684
0x1800464b6  mov     r8, [r14+rcx*8]
0x1800464ba  test    r8, r8
0x1800464bd  jz      short loc_1800464D3
0x1800464bf  cmp     ecx, r12d
0x1800464c2  jz      short loc_1800464D0
0x1800464c4  mov     [r14+r12*8], r8
0x1800464c8  mov     qword ptr [r14+rcx*8], 0
0x1800464d0  inc     r12d
0x1800464d3  inc     ecx
0x1800464d5  cmp     ecx, r13d
0x1800464d8  jb      short loc_1800464B6
0x1800464da  jmp     loc_180046684
0x1800464df  xor     ebx, ebx
0x1800464e1  mov     dword ptr [rbp+37h+var_88], edx
0x1800464e4  mov     ecx, edi
0x1800464e6  test    edi, edi
0x1800464e8  jz      short loc_1800464FA
0x1800464ea  sub     ecx, edx
0x1800464ec  jz      short loc_180046501
0x1800464ee  sub     ecx, edx
0x1800464f0  jz      short loc_18004654E
0x1800464f2  cmp     ecx, edx
0x1800464f4  jnz     loc_180046687
0x1800464fa  mov     dword ptr [rbp+37h+var_88], 0FFFFFFFFh
0x180046501  mov     edi, edx
0x180046503  cmp     r13d, edx
0x180046506  jbe     loc_1800465EC
0x18004650c  mov     r15d, dword ptr [rbp+37h+var_88]
0x180046510  mov     esi, ebx
0x180046512  mov     r12d, edi
0x180046515  mov     rax, [r14+rsi*8]
0x180046519  mov     rdx, [rax+18h]
0x18004651d  mov     rax, [r14+r12*8]
0x180046521  add     rdx, 40h ; '@'; lpFileTime2
0x180046525  mov     rcx, [rax+18h]
0x180046529  add     rcx, 40h ; '@'; lpFileTime1
0x18004652d  call    cs:__imp_CompareFileTime
0x180046533  cmp     eax, r15d
0x180046536  jnz     short loc_1800465B1
0x180046538  mov     rcx, [r14+rsi*8]; pCertContext
0x18004653c  call    cs:__imp_CertFreeCertificateContext
0x180046542  mov     qword ptr [r14+rsi*8], 0
0x18004654a  mov     ebx, edi
0x18004654c  jmp     short loc_1800465C3
0x18004654e  mov     esi, edx
0x180046550  cmp     r13d, edx
0x180046553  jbe     short loc_180046587
0x180046555  mov     eax, ebx
0x180046557  mov     rcx, [r14+rax*8]
0x18004655b  mov     eax, esi
0x18004655d  mov     rdx, [rcx+18h]
0x180046561  mov     rcx, [r14+rax*8]
0x180046565  add     rdx, 40h ; '@'; lpFileTime2
0x180046569  mov     rcx, [rcx+18h]
0x18004656d  add     rcx, 40h ; '@'; lpFileTime1
0x180046571  call    cs:__imp_CompareFileTime
0x180046577  test    eax, eax
0x180046579  mov     ecx, esi
0x18004657b  cmovns  ecx, ebx
0x18004657e  inc     esi
0x180046580  mov     ebx, ecx
0x180046582  cmp     esi, r13d
0x180046585  jb      short loc_180046555
0x180046587  mov     esi, ebx
0x180046589  mov     rcx, [r14+rsi*8]; pCertContext
0x18004658d  call    cs:__imp_CertFreeCertificateContext
0x180046593  lea     r12d, [r13-1]
0x180046597  cmp     ebx, r12d
0x18004659a  jz      short loc_1800465A4
0x18004659c  mov     rax, [r14+r12*8]
0x1800465a0  mov     [r14+rsi*8], rax
0x1800465a4  mov     qword ptr [r14+r12*8], 0
0x1800465ac  jmp     loc_180046687
0x1800465b1  mov     rcx, [r14+r12*8]; pCertContext
0x1800465b5  call    cs:__imp_CertFreeCertificateContext
0x1800465bb  mov     qword ptr [r14+r12*8], 0
0x1800465c3  mov     edx, 1
0x1800465c8  add     edi, edx
0x1800465ca  cmp     edi, r13d
0x1800465cd  jb      loc_180046510
0x1800465d3  mov     r15d, dword ptr [rbp+37h+var_68]
0x1800465d7  test    ebx, ebx
0x1800465d9  jz      short loc_1800465EC
0x1800465db  mov     ecx, ebx
0x1800465dd  mov     rax, [r14+rcx*8]
0x1800465e1  mov     [r14], rax
0x1800465e4  mov     qword ptr [r14+rcx*8], 0
0x1800465ec  mov     rax, [r14]
0x1800465ef  mov     r12d, edx
0x1800465f2  lea     rdx, [rbp+37h+SystemTime]; lpSystemTime
0x1800465f6  mov     rcx, [rax+18h]
0x1800465fa  add     rcx, 40h ; '@'; lpFileTime
0x1800465fe  call    cs:__imp_FileTimeToSystemTime
0x180046604  test    eax, eax
0x180046606  jz      short loc_180046684
0x180046608  mov     rcx, [r14]; pCertContext
0x18004660b  lea     rdx, [rbp+37h+var_68]; unsigned __int16 **
0x18004660f  mov     [rbp+37h+var_68], 0
0x180046617  call    ?GetCertificateThumbprint@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::GetCertificateThumbprint(_CERT_CONTEXT const *,ushort * *)
0x18004661c  movzx   edx, [rbp+37h+SystemTime.wSecond]
0x180046620  lea     rdi, aNA; "N/A"
0x180046627  mov     rsi, [rbp+37h+var_68]
0x18004662b  lea     rcx, aSReturningCert; "%s: Returning certificate with UTC time"...
0x180046632  movzx   eax, [rbp+37h+SystemTime.wMilliseconds]
  ... truncated ...
```
