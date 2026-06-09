# RegistrationCertStatus::GetCertificate(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,INFO_KIND,_CERT_CONTEXT const * *)

- ea: `0x180078a9c`
- end: `0x180078cb3`
- name: `?GetCertificate@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22W4INFO_KIND@@PEAPEBU_CERT_CONTEXT@@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180078f44`

## callees

- `0x18002c90c`
- `0x18002cb48`
- `0x18002ce0c`
- `0x180035664`
- `0x180035680`
- `0x18007824c`
- `0x18007828c`
- `0x180078a9c`
- `0x180078cbc`

## import_xrefs

- `CRYPT32!CertDuplicateCertificateContext` at `0x180078c55`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180078c55`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180078ba4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180078ba4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180078bcc`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180078bcc`

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
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-20h] BYREF

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
0x180078a9c  mov     [rsp-28h+arg_8], rbx
0x180078aa1  mov     [rsp-28h+arg_18], rdi
0x180078aa6  push    rbp
0x180078aa7  push    r12
0x180078aa9  push    r13
0x180078aab  push    r14
0x180078aad  push    r15
0x180078aaf  mov     rbp, rsp
0x180078ab2  sub     rsp, 80h
0x180078ab9  mov     rax, cs:__security_cookie
0x180078ac0  xor     rax, rsp
0x180078ac3  mov     [rbp+var_10], rax
0x180078ac7  mov     r14, [rbp+arg_30]
0x180078acb  xor     r15d, r15d
0x180078ace  xor     r12d, r12d
0x180078ad1  mov     [rbp+var_28], r15
0x180078ad5  mov     dword ptr [rbp+Block], r12d
0x180078ad9  xorps   xmm0, xmm0
0x180078adc  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180078ae0  test    r14, r14
0x180078ae3  jnz     short loc_180078B1D
0x180078ae5  lea     r8, aPpcertcontext; "ppCertContext"
0x180078aec  mov     r13d, 80070057h
0x180078af2  lea     rdx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x180078af9  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180078b00  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180078b05  lea     rdx, aPpcertcontext; "ppCertContext"
0x180078b0c  lea     rcx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x180078b13  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180078b18  jmp     loc_180078C5E
0x180078b1d  lea     rax, [rbp+Block]
0x180078b21  mov     [r14], r12
0x180078b24  mov     [rsp+80h+var_50], rax
0x180078b29  lea     rax, [rbp+var_28]
0x180078b2d  mov     [rsp+80h+var_58], rax
0x180078b32  call    ?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z; RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,_CERT_CONTEXT const * * *,ulong *)
0x180078b37  mov     r13d, eax
0x180078b3a  test    eax, eax
0x180078b3c  jns     short loc_180078B68
0x180078b3e  mov     r9d, eax
0x180078b41  lea     r8, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x180078b48  lea     rdx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x180078b4f  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x180078b56  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180078b5b  mov     r15, [rbp+var_28]
0x180078b5f  mov     r12d, dword ptr [rbp+Block]
0x180078b63  jmp     loc_180078C5E
0x180078b68  mov     r12d, dword ptr [rbp+Block]
0x180078b6c  mov     r15, [rbp+var_28]
0x180078b70  cmp     r12d, 1
0x180078b74  jnz     short loc_180078B81
0x180078b76  mov     rax, [r15]
0x180078b79  xor     r13d, r13d
0x180078b7c  mov     [r14], rax
0x180078b7f  jmp     short loc_180078BBD
0x180078b81  xor     ebx, ebx
0x180078b83  test    r12d, r12d
0x180078b86  jz      short loc_180078BBD
0x180078b88  mov     rdx, [r14]
0x180078b8b  mov     rax, [r15+rbx*8]
0x180078b8f  test    rdx, rdx
0x180078b92  jz      short loc_180078BB3
0x180078b94  mov     rdx, [rdx+18h]
0x180078b98  mov     rcx, [rax+18h]
0x180078b9c  add     rdx, 40h ; '@'; lpFileTime2
0x180078ba0  add     rcx, 40h ; '@'; lpFileTime1
0x180078ba4  call    cs:__imp_CompareFileTime
0x180078baa  cmp     eax, 0FFFFFFFFh
0x180078bad  jnz     short loc_180078BB6
0x180078baf  mov     rax, [r15+rbx*8]
0x180078bb3  mov     [r14], rax
0x180078bb6  inc     ebx
0x180078bb8  cmp     ebx, r12d
0x180078bbb  jb      short loc_180078B88
0x180078bbd  mov     rax, [r14]
0x180078bc0  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180078bc4  mov     rcx, [rax+18h]
0x180078bc8  add     rcx, 40h ; '@'; lpFileTime
0x180078bcc  call    cs:__imp_FileTimeToSystemTime
0x180078bd2  test    eax, eax
0x180078bd4  jz      short loc_180078C52
0x180078bd6  mov     rcx, [r14]; struct _CERT_CONTEXT *
0x180078bd9  lea     rdx, [rbp+Block]; unsigned __int16 **
0x180078bdd  mov     [rbp+Block], 0
0x180078be5  call    ?GetCertificateThumbprint@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::GetCertificateThumbprint(_CERT_CONTEXT const *,ushort * *)
0x180078bea  movzx   edx, [rbp+SystemTime.wSecond]
0x180078bee  lea     rdi, aNA; "N/A"
0x180078bf5  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x180078bf9  lea     rcx, aSReturningCert; "%s: Returning certificate with UTC time"...
0x180078c00  movzx   r10d, [rbp+SystemTime.wMinute]
0x180078c05  movzx   r11d, [rbp+SystemTime.wHour]
0x180078c0a  movzx   ebx, [rbp+SystemTime.wDay]
0x180078c0e  cmp     [rbp+Block], 0
0x180078c13  movzx   r9d, [rbp+SystemTime.wMonth]
0x180078c18  cmovnz  rdi, [rbp+Block]
0x180078c1d  movzx   r8d, [rbp+SystemTime.wYear]
0x180078c22  mov     [rsp+80h+var_38], rdi
0x180078c27  mov     [rsp+80h+var_40], eax
0x180078c2b  mov     [rsp+80h+var_48], edx
0x180078c2f  lea     rdx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x180078c36  mov     dword ptr [rsp+80h+var_50], r10d
0x180078c3b  mov     dword ptr [rsp+80h+var_58], r11d
0x180078c40  mov     [rsp+80h+var_60], ebx
0x180078c44  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180078c49  mov     rcx, [rbp+Block]; Block
0x180078c4d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078c52  mov     rcx, [r14]; pCertContext
0x180078c55  call    cs:__imp_CertDuplicateCertificateContext
0x180078c5b  mov     [r14], rax
0x180078c5e  mov     edx, r12d; unsigned int
0x180078c61  mov     rcx, r15; struct _CERT_CONTEXT **
0x180078c64  call    ?FreeCertificates@CertificateUtil@@SAXQEAPEBU_CERT_CONTEXT@@K@Z; CertificateUtil::FreeCertificates(_CERT_CONTEXT const * * const,ulong)
0x180078c69  mov     rcx, r15; Block
0x180078c6c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078c71  mov     r8d, r13d
0x180078c74  lea     rdx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x180078c7b  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180078c82  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180078c87  mov     eax, r13d
0x180078c8a  mov     rcx, [rbp+var_10]
0x180078c8e  xor     rcx, rsp; StackCookie
0x180078c91  call    __security_check_cookie
0x180078c96  lea     r11, [rsp+80h+var_s0]
0x180078c9e  mov     rbx, [r11+38h]
0x180078ca2  mov     rdi, [r11+48h]
0x180078ca6  mov     rsp, r11
0x180078ca9  pop     r15
0x180078cab  pop     r14
0x180078cad  pop     r13
0x180078caf  pop     r12
0x180078cb1  pop     rbp
0x180078cb2  retn
```
