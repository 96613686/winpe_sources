# RegistrationCertStatus::GetCertificate(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,INFO_KIND,_CERT_CONTEXT const * *)

- ea: `0x18002572c`
- end: `0x180025943`
- name: `?GetCertificate@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22W4INFO_KIND@@PEAPEBU_CERT_CONTEXT@@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180025bd4`

## callees

- `0x18000febc`
- `0x180010218`
- `0x18001029c`
- `0x180013b20`
- `0x180013bd0`
- `0x180024e68`
- `0x180024ea8`
- `0x18002572c`
- `0x18002594c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180025834`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180025834`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800258e5`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800258e5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002585c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002585c`

## pseudocode

```c
__int64 __fastcall RegistrationCertStatus::GetCertificate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        PCCERT_CONTEXT *a7)
{
  const struct _CERT_CONTEXT **v7; // r15
  unsigned int v8; // r12d
  unsigned int v9; // r13d
  int Certificates; // eax
  __int64 v11; // rbx
  const struct _CERT_CONTEXT *v12; // rax
  const struct _CERT_CONTEXT *v13; // rcx
  const wchar_t *v14; // rdi
  const struct _CERT_CONTEXT ***v16; // [rsp+28h] [rbp-58h]
  void **p_Block; // [rsp+30h] [rbp-50h]
  void *Block; // [rsp+50h] [rbp-30h] BYREF
  const struct _CERT_CONTEXT **v19; // [rsp+58h] [rbp-28h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-20h] BYREF

  v7 = 0;
  v8 = 0;
  v19 = 0;
  LODWORD(Block) = 0;
  SystemTime = 0;
  if ( !a7 )
  {
    v9 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationCertStatus::GetCertificate", L"ppCertContext");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationCertStatus::GetCertificate", L"ppCertContext");
    goto LABEL_18;
  }
  *a7 = 0;
  p_Block = &Block;
  v16 = &v19;
  Certificates = RegistrationCertStatus::GetCertificates();
  v9 = Certificates;
  if ( Certificates < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationCertStatus::GetCertificate",
      L"RegistrationCertStatus::GetCertificates",
      (unsigned int)Certificates);
    v7 = v19;
    v8 = (unsigned int)Block;
    goto LABEL_18;
  }
  v8 = (unsigned int)Block;
  v7 = v19;
  if ( (_DWORD)Block != 1 )
  {
    v11 = 0;
    if ( !(_DWORD)Block )
      goto LABEL_13;
    while ( 1 )
    {
      v12 = v7[v11];
      if ( !*a7 )
        goto LABEL_11;
      if ( CompareFileTime(&v12->pCertInfo->NotBefore, &(*a7)->pCertInfo->NotBefore) == -1 )
        break;
LABEL_12:
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= v8 )
        goto LABEL_13;
    }
    v12 = v7[v11];
LABEL_11:
    *a7 = v12;
    goto LABEL_12;
  }
  v9 = 0;
  *a7 = *v19;
LABEL_13:
  if ( FileTimeToSystemTime(&(*a7)->pCertInfo->NotBefore, &SystemTime) )
  {
    v13 = *a7;
    Block = 0;
    CertificateUtil::GetCertificateThumbprint(v13, (unsigned __int16 **)&Block);
    v14 = L"N/A";
    if ( Block )
      v14 = (const wchar_t *)Block;
    LODWORD(p_Block) = SystemTime.wMinute;
    LODWORD(v16) = SystemTime.wHour;
    Logger::TraceVerbose(
      L"%s: Returning certificate with UTC timestamp (YYYY-MM-DD HH:MM:SS.sss) %04u-%02u-%02u %02u:%02u:%02u.%03u and thumbprint %s",
      L"RegistrationCertStatus::GetCertificate",
      SystemTime.wYear,
      SystemTime.wMonth,
      SystemTime.wDay,
      v16,
      p_Block,
      SystemTime.wSecond,
      SystemTime.wMilliseconds,
      v14);
    operator delete(Block);
  }
  *a7 = CertDuplicateCertificateContext(*a7);
LABEL_18:
  CertificateUtil::FreeCertificates(v7, v8);
  operator delete(v7);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetCertificate", v9);
  return v9;
}

```

## disassembly

```asm
0x18002572c  mov     [rsp-28h+arg_8], rbx
0x180025731  mov     [rsp-28h+arg_18], rdi
0x180025736  push    rbp
0x180025737  push    r12
0x180025739  push    r13
0x18002573b  push    r14
0x18002573d  push    r15
0x18002573f  mov     rbp, rsp
0x180025742  sub     rsp, 80h
0x180025749  mov     rax, cs:__security_cookie
0x180025750  xor     rax, rsp
0x180025753  mov     [rbp+var_10], rax
0x180025757  mov     r14, [rbp+arg_30]
0x18002575b  xor     r15d, r15d
0x18002575e  xor     r12d, r12d
0x180025761  mov     [rbp+var_28], r15
0x180025765  mov     dword ptr [rbp+Block], r12d
0x180025769  xorps   xmm0, xmm0
0x18002576c  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180025770  test    r14, r14
0x180025773  jnz     short loc_1800257AD
0x180025775  lea     r8, aPpcertcontext; "ppCertContext"
0x18002577c  mov     r13d, 80070057h
0x180025782  lea     rdx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x180025789  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180025790  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180025795  lea     rdx, aPpcertcontext; "ppCertContext"
0x18002579c  lea     rcx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x1800257a3  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800257a8  jmp     loc_1800258EE
0x1800257ad  lea     rax, [rbp+Block]
0x1800257b1  mov     [r14], r12
0x1800257b4  mov     [rsp+80h+var_50], rax
0x1800257b9  lea     rax, [rbp+var_28]
0x1800257bd  mov     [rsp+80h+var_58], rax
0x1800257c2  call    ?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z; RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,_CERT_CONTEXT const * * *,ulong *)
0x1800257c7  mov     r13d, eax
0x1800257ca  test    eax, eax
0x1800257cc  jns     short loc_1800257F8
0x1800257ce  mov     r9d, eax
0x1800257d1  lea     r8, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x1800257d8  lea     rdx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x1800257df  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x1800257e6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800257eb  mov     r15, [rbp+var_28]
0x1800257ef  mov     r12d, dword ptr [rbp+Block]
0x1800257f3  jmp     loc_1800258EE
0x1800257f8  mov     r12d, dword ptr [rbp+Block]
0x1800257fc  mov     r15, [rbp+var_28]
0x180025800  cmp     r12d, 1
0x180025804  jnz     short loc_180025811
0x180025806  mov     rax, [r15]
0x180025809  xor     r13d, r13d
0x18002580c  mov     [r14], rax
0x18002580f  jmp     short loc_18002584D
0x180025811  xor     ebx, ebx
0x180025813  test    r12d, r12d
0x180025816  jz      short loc_18002584D
0x180025818  mov     rdx, [r14]
0x18002581b  mov     rax, [r15+rbx*8]
0x18002581f  test    rdx, rdx
0x180025822  jz      short loc_180025843
0x180025824  mov     rdx, [rdx+18h]
0x180025828  mov     rcx, [rax+18h]
0x18002582c  add     rdx, 40h ; '@'; lpFileTime2
0x180025830  add     rcx, 40h ; '@'; lpFileTime1
0x180025834  call    cs:__imp_CompareFileTime
0x18002583a  cmp     eax, 0FFFFFFFFh
0x18002583d  jnz     short loc_180025846
0x18002583f  mov     rax, [r15+rbx*8]
0x180025843  mov     [r14], rax
0x180025846  inc     ebx
0x180025848  cmp     ebx, r12d
0x18002584b  jb      short loc_180025818
0x18002584d  mov     rax, [r14]
0x180025850  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180025854  mov     rcx, [rax+18h]
0x180025858  add     rcx, 40h ; '@'; lpFileTime
0x18002585c  call    cs:__imp_FileTimeToSystemTime
0x180025862  test    eax, eax
0x180025864  jz      short loc_1800258E2
0x180025866  mov     rcx, [r14]; struct _CERT_CONTEXT *
0x180025869  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18002586d  mov     [rbp+Block], 0
0x180025875  call    ?GetCertificateThumbprint@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::GetCertificateThumbprint(_CERT_CONTEXT const *,ushort * *)
0x18002587a  movzx   edx, [rbp+SystemTime.wSecond]
0x18002587e  lea     rdi, aNA; "N/A"
0x180025885  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x180025889  lea     rcx, aSReturningCert; "%s: Returning certificate with UTC time"...
0x180025890  movzx   r10d, [rbp+SystemTime.wMinute]
0x180025895  movzx   r11d, [rbp+SystemTime.wHour]
0x18002589a  movzx   ebx, [rbp+SystemTime.wDay]
0x18002589e  cmp     [rbp+Block], 0
0x1800258a3  movzx   r9d, [rbp+SystemTime.wMonth]
0x1800258a8  cmovnz  rdi, [rbp+Block]
0x1800258ad  movzx   r8d, [rbp+SystemTime.wYear]
0x1800258b2  mov     [rsp+80h+var_38], rdi
0x1800258b7  mov     [rsp+80h+var_40], eax
0x1800258bb  mov     [rsp+80h+var_48], edx
0x1800258bf  lea     rdx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x1800258c6  mov     dword ptr [rsp+80h+var_50], r10d
0x1800258cb  mov     dword ptr [rsp+80h+var_58], r11d
0x1800258d0  mov     [rsp+80h+var_60], ebx
0x1800258d4  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800258d9  mov     rcx, [rbp+Block]; Block
0x1800258dd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800258e2  mov     rcx, [r14]; pCertContext
0x1800258e5  call    cs:__imp_CertDuplicateCertificateContext
0x1800258eb  mov     [r14], rax
0x1800258ee  mov     edx, r12d; unsigned int
0x1800258f1  mov     rcx, r15; struct _CERT_CONTEXT **
0x1800258f4  call    ?FreeCertificates@CertificateUtil@@SAXQEAPEBU_CERT_CONTEXT@@K@Z; CertificateUtil::FreeCertificates(_CERT_CONTEXT const * * const,ulong)
0x1800258f9  mov     rcx, r15; Block
0x1800258fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025901  mov     r8d, r13d
0x180025904  lea     rdx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x18002590b  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180025912  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180025917  mov     eax, r13d
0x18002591a  mov     rcx, [rbp+var_10]
0x18002591e  xor     rcx, rsp; StackCookie
0x180025921  call    __security_check_cookie
0x180025926  lea     r11, [rsp+80h+var_s0]
0x18002592e  mov     rbx, [r11+38h]
0x180025932  mov     rdi, [r11+48h]
0x180025936  mov     rsp, r11
0x180025939  pop     r15
0x18002593b  pop     r14
0x18002593d  pop     r13
0x18002593f  pop     r12
0x180025941  pop     rbp
0x180025942  retn
```
