# RegistrationCertStatus::GetCertificate(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,INFO_KIND,_CERT_CONTEXT const * *)

- ea: `0x18007df58`
- end: `0x18007e182`
- name: `?GetCertificate@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22W4INFO_KIND@@PEAPEBU_CERT_CONTEXT@@@Z`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007e410`

## callees

- `0x18002ee04`
- `0x18002f048`
- `0x18002f324`
- `0x180038254`
- `0x180038270`
- `0x18007d6d4`
- `0x18007d71c`
- `0x18007df58`
- `0x18007e188`

## import_xrefs

- `CRYPT32!CertDuplicateCertificateContext` at `0x18007e11d`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18007e11d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007e060`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007e060`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18007e08e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18007e08e`

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
0x18007df58  mov     [rsp-28h+arg_8], rbx
0x18007df5d  mov     [rsp-28h+arg_18], rdi
0x18007df62  push    rbp
0x18007df63  push    r12
0x18007df65  push    r13
0x18007df67  push    r14
0x18007df69  push    r15
0x18007df6b  mov     rbp, rsp
0x18007df6e  sub     rsp, 80h
0x18007df75  mov     rax, cs:__security_cookie
0x18007df7c  xor     rax, rsp
0x18007df7f  mov     [rbp+var_10], rax
0x18007df83  mov     r14, [rbp+arg_30]
0x18007df87  xor     r15d, r15d
0x18007df8a  xor     r12d, r12d
0x18007df8d  mov     [rbp+var_28], r15
0x18007df91  mov     dword ptr [rbp+Block], r12d
0x18007df95  xorps   xmm0, xmm0
0x18007df98  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18007df9c  test    r14, r14
0x18007df9f  jnz     short loc_18007DFD9
0x18007dfa1  lea     r8, aPpcertcontext; "ppCertContext"
0x18007dfa8  mov     r13d, 80070057h
0x18007dfae  lea     rdx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x18007dfb5  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007dfbc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007dfc1  lea     rdx, aPpcertcontext; "ppCertContext"
0x18007dfc8  lea     rcx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x18007dfcf  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007dfd4  jmp     loc_18007E12C
0x18007dfd9  lea     rax, [rbp+Block]
0x18007dfdd  mov     [r14], r12
0x18007dfe0  mov     [rsp+80h+var_50], rax
0x18007dfe5  lea     rax, [rbp+var_28]
0x18007dfe9  mov     [rsp+80h+var_58], rax
0x18007dfee  call    ?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z; RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,_CERT_CONTEXT const * * *,ulong *)
0x18007dff3  mov     r13d, eax
0x18007dff6  test    eax, eax
0x18007dff8  jns     short loc_18007E024
0x18007dffa  mov     r9d, eax
0x18007dffd  lea     r8, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x18007e004  lea     rdx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x18007e00b  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18007e012  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e017  mov     r15, [rbp+var_28]
0x18007e01b  mov     r12d, dword ptr [rbp+Block]
0x18007e01f  jmp     loc_18007E12C
0x18007e024  mov     r12d, dword ptr [rbp+Block]
0x18007e028  mov     r15, [rbp+var_28]
0x18007e02c  cmp     r12d, 1
0x18007e030  jnz     short loc_18007E03D
0x18007e032  mov     rax, [r15]
0x18007e035  xor     r13d, r13d
0x18007e038  mov     [r14], rax
0x18007e03b  jmp     short loc_18007E07F
0x18007e03d  xor     ebx, ebx
0x18007e03f  test    r12d, r12d
0x18007e042  jz      short loc_18007E07F
0x18007e044  mov     rdx, [r14]
0x18007e047  mov     rax, [r15+rbx*8]
0x18007e04b  test    rdx, rdx
0x18007e04e  jz      short loc_18007E075
0x18007e050  mov     rdx, [rdx+18h]
0x18007e054  mov     rcx, [rax+18h]
0x18007e058  add     rdx, 40h ; '@'; lpFileTime2
0x18007e05c  add     rcx, 40h ; '@'; lpFileTime1
0x18007e060  call    cs:__imp_CompareFileTime
0x18007e067  nop     dword ptr [rax+rax+00h]
0x18007e06c  cmp     eax, 0FFFFFFFFh
0x18007e06f  jnz     short loc_18007E078
0x18007e071  mov     rax, [r15+rbx*8]
0x18007e075  mov     [r14], rax
0x18007e078  inc     ebx
0x18007e07a  cmp     ebx, r12d
0x18007e07d  jb      short loc_18007E044
0x18007e07f  mov     rax, [r14]
0x18007e082  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18007e086  mov     rcx, [rax+18h]
0x18007e08a  add     rcx, 40h ; '@'; lpFileTime
0x18007e08e  call    cs:__imp_FileTimeToSystemTime
0x18007e095  nop     dword ptr [rax+rax+00h]
0x18007e09a  test    eax, eax
0x18007e09c  jz      short loc_18007E11A
0x18007e09e  mov     rcx, [r14]; struct _CERT_CONTEXT *
0x18007e0a1  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18007e0a5  mov     [rbp+Block], 0
0x18007e0ad  call    ?GetCertificateThumbprint@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::GetCertificateThumbprint(_CERT_CONTEXT const *,ushort * *)
0x18007e0b2  movzx   edx, [rbp+SystemTime.wSecond]
0x18007e0b6  lea     rdi, aNA; "N/A"
0x18007e0bd  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x18007e0c1  lea     rcx, aSReturningCert; "%s: Returning certificate with UTC time"...
0x18007e0c8  movzx   r10d, [rbp+SystemTime.wMinute]
0x18007e0cd  movzx   r11d, [rbp+SystemTime.wHour]
0x18007e0d2  movzx   ebx, [rbp+SystemTime.wDay]
0x18007e0d6  cmp     [rbp+Block], 0
0x18007e0db  movzx   r9d, [rbp+SystemTime.wMonth]
0x18007e0e0  cmovnz  rdi, [rbp+Block]
0x18007e0e5  movzx   r8d, [rbp+SystemTime.wYear]
0x18007e0ea  mov     [rsp+80h+var_38], rdi
0x18007e0ef  mov     [rsp+80h+var_40], eax
0x18007e0f3  mov     [rsp+80h+var_48], edx
0x18007e0f7  lea     rdx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x18007e0fe  mov     dword ptr [rsp+80h+var_50], r10d
0x18007e103  mov     dword ptr [rsp+80h+var_58], r11d
0x18007e108  mov     [rsp+80h+var_60], ebx
0x18007e10c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007e111  mov     rcx, [rbp+Block]; Block
0x18007e115  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007e11a  mov     rcx, [r14]; pCertContext
0x18007e11d  call    cs:__imp_CertDuplicateCertificateContext
0x18007e124  nop     dword ptr [rax+rax+00h]
0x18007e129  mov     [r14], rax
0x18007e12c  mov     edx, r12d; unsigned int
0x18007e12f  mov     rcx, r15; struct _CERT_CONTEXT **
0x18007e132  call    ?FreeCertificates@CertificateUtil@@SAXQEAPEBU_CERT_CONTEXT@@K@Z; CertificateUtil::FreeCertificates(_CERT_CONTEXT const * * const,ulong)
0x18007e137  mov     rcx, r15; Block
0x18007e13a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007e13f  mov     r8d, r13d
0x18007e142  lea     rdx, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x18007e149  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18007e150  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007e155  mov     eax, r13d
0x18007e158  mov     rcx, [rbp+var_10]
0x18007e15c  xor     rcx, rsp; StackCookie
0x18007e15f  call    __security_check_cookie
0x18007e164  lea     r11, [rsp+80h+var_s0]
0x18007e16c  mov     rbx, [r11+38h]
0x18007e170  mov     rdi, [r11+48h]
0x18007e174  mov     rsp, r11
0x18007e177  pop     r15
0x18007e179  pop     r14
0x18007e17b  pop     r13
0x18007e17d  pop     r12
0x18007e17f  pop     rbp
0x18007e180  retn
```
