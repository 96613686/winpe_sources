# FindCertificateContext

- ea: `0x1800cf194`
- end: `0x1800cf32c`
- name: `FindCertificateContext`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800cf334`

## callees

- `0x180008618`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800cf194`
- `0x1800f82f0`

## import_xrefs

- `CRYPT32!CertFindChainInStore` at `0x1800cf29c`
- `CRYPT32!CertFindChainInStore` at `0x1800cf29c`
- `CRYPT32!CertFreeCertificateChain` at `0x1800cf2f8`
- `CRYPT32!CertFreeCertificateChain` at `0x1800cf2f8`
- `CRYPT32!CertOpenStore` at `0x1800cf1e2`
- `CRYPT32!CertOpenStore` at `0x1800cf1e2`
- `CRYPT32!CertCloseStore` at `0x1800cf303`
- `CRYPT32!CertCloseStore` at `0x1800cf303`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800cf2c3`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800cf2c3`

## string_xrefs

- `0x1800cf1f8`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`
- `0x1800cf2de`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`

## pseudocode

```c
__int64 __fastcall FindCertificateContext(__int64 a1, __int64 a2, int a3, unsigned __int64 a4, PCCERT_CONTEXT *a5)
{
  HCERTSTORE v7; // rsi
  const char *v8; // r9
  unsigned int LastError; // ebx
  PCCERT_CHAIN_CONTEXT ChainInStore; // rax
  const char *v11; // r9
  const CERT_CHAIN_CONTEXT *v12; // rdi
  __int64 v13; // rdx
  PCCERT_CONTEXT v14; // rax
  __int128 pvFindPara; // [rsp+38h] [rbp-60h] BYREF
  __int128 v17; // [rsp+48h] [rbp-50h]
  __int128 v18; // [rsp+58h] [rbp-40h]
  __int64 v19; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  *a5 = 0;
  v7 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x1C000u, L"MY");
  if ( v7 )
  {
    if ( !a3 )
    {
      LogMessage(2u, "FindCertificateContext", 0x536u, "TelemetryAssert (%s): %s", "cIssuers > 0", "Failed");
      DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
    }
    v19 = 0;
    pvFindPara = 0;
    v17 = 0;
    LODWORD(pvFindPara) = 56;
    DWORD2(v17) = a3;
    v18 = a4;
    ChainInStore = CertFindChainInStore(v7, 1u, 0x8004u, 1u, &pvFindPara, 0);
    v12 = ChainInStore;
    if ( ChainInStore )
    {
      v14 = CertDuplicateCertificateContext((*(*ChainInStore->rgpChain)->rgpElement)->pCertContext);
      *a5 = v14;
      if ( v14 )
      {
        LastError = 0;
        goto LABEL_12;
      }
      v13 = 1348;
    }
    else
    {
      v13 = 1346;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v13,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
                  v11);
    if ( !v12 )
    {
LABEL_13:
      CertCloseStore(v7, 0);
      return LastError;
    }
LABEL_12:
    CertFreeCertificateChain(v12);
    goto LABEL_13;
  }
  return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                         retaddr,
                         (void *)0x534,
                         (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
                         v8);
}

```

## disassembly

```asm
0x1800cf194  mov     [rsp+arg_0], rbx
0x1800cf199  push    rsi
0x1800cf19a  push    rdi
0x1800cf19b  push    r14
0x1800cf19d  sub     rsp, 80h
0x1800cf1a4  mov     rax, cs:__security_cookie
0x1800cf1ab  xor     rax, rsp
0x1800cf1ae  mov     [rsp+98h+var_28], rax
0x1800cf1b3  mov     r14, [rsp+98h+arg_20]
0x1800cf1bb  lea     rax, aMy; "MY"
0x1800cf1c2  xor     edx, edx; dwEncodingType
0x1800cf1c4  mov     [rsp+98h+pvPara], rax; pvPara
0x1800cf1c9  mov     rdi, r9
0x1800cf1cc  mov     ebx, r8d
0x1800cf1cf  mov     r9d, 1C000h; dwFlags
0x1800cf1d5  xor     r8d, r8d; hCryptProv
0x1800cf1d8  mov     qword ptr [r14], 0
0x1800cf1df  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800cf1e2  call    cs:__imp_CertOpenStore
0x1800cf1e8  mov     rsi, rax
0x1800cf1eb  test    rax, rax
0x1800cf1ee  jnz     short loc_1800CF210
0x1800cf1f0  mov     rcx, [rsp+98h]; this
0x1800cf1f8  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cf1ff  mov     edx, 534h; void *
0x1800cf204  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cf209  mov     ebx, eax
0x1800cf20b  jmp     loc_1800CF309
0x1800cf210  test    ebx, ebx
0x1800cf212  jnz     short loc_1800CF252
0x1800cf214  lea     rax, aFailed; "Failed"
0x1800cf21b  mov     r8d, 536h; unsigned int
0x1800cf221  mov     [rsp+98h+pPrevChainContext], rax
0x1800cf226  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x1800cf22d  lea     rax, aCissuers0; "cIssuers > 0"
0x1800cf234  lea     rdx, aFindcertificat; "FindCertificateContext"
0x1800cf23b  mov     [rsp+98h+pvPara], rax
0x1800cf240  lea     ecx, [rbx+2]; unsigned __int8
0x1800cf243  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800cf248  or      ecx, 0FFFFFFFFh; unsigned int
0x1800cf24b  mov     edx, ecx; unsigned int
0x1800cf24d  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x1800cf252  xor     eax, eax
0x1800cf254  xorps   xmm0, xmm0
0x1800cf257  mov     [rsp+98h+pPrevChainContext], rax; pPrevChainContext
0x1800cf25c  mov     edx, 1; dwCertEncodingType
0x1800cf261  mov     [rsp+98h+var_30], rax
0x1800cf266  mov     r9d, edx; dwFindType
0x1800cf269  lea     rax, [rsp+98h+pvFindPara]
0x1800cf26e  mov     r8d, 8004h; dwFindFlags
0x1800cf274  movups  [rsp+98h+pvFindPara], xmm0
0x1800cf279  mov     rcx, rsi; hCertStore
0x1800cf27c  mov     [rsp+98h+pvPara], rax; pvFindPara
0x1800cf281  movups  [rsp+98h+var_50], xmm0
0x1800cf286  mov     dword ptr [rsp+98h+pvFindPara], 38h ; '8'
0x1800cf28e  movups  [rsp+98h+var_40], xmm0
0x1800cf293  mov     dword ptr [rsp+98h+var_50+8], ebx
0x1800cf297  mov     qword ptr [rsp+98h+var_40], rdi
0x1800cf29c  call    cs:__imp_CertFindChainInStore
0x1800cf2a2  mov     rdi, rax
0x1800cf2a5  test    rax, rax
0x1800cf2a8  jnz     short loc_1800CF2B1
0x1800cf2aa  mov     edx, 542h
0x1800cf2af  jmp     short loc_1800CF2D6
0x1800cf2b1  mov     rax, [rax+10h]
0x1800cf2b5  mov     rcx, [rax]
0x1800cf2b8  mov     rax, [rcx+10h]
0x1800cf2bc  mov     rcx, [rax]
0x1800cf2bf  mov     rcx, [rcx+8]; pCertContext
0x1800cf2c3  call    cs:__imp_CertDuplicateCertificateContext
0x1800cf2c9  mov     [r14], rax
0x1800cf2cc  test    rax, rax
0x1800cf2cf  jnz     short loc_1800CF2F3
0x1800cf2d1  mov     edx, 544h; void *
0x1800cf2d6  mov     rcx, [rsp+98h]; this
0x1800cf2de  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cf2e5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cf2ea  mov     ebx, eax
0x1800cf2ec  test    rdi, rdi
0x1800cf2ef  jz      short loc_1800CF2FE
0x1800cf2f1  jmp     short loc_1800CF2F5
0x1800cf2f3  xor     ebx, ebx
0x1800cf2f5  mov     rcx, rdi; pChainContext
0x1800cf2f8  call    cs:__imp_CertFreeCertificateChain
0x1800cf2fe  xor     edx, edx; dwFlags
0x1800cf300  mov     rcx, rsi; hCertStore
0x1800cf303  call    cs:__imp_CertCloseStore
0x1800cf309  mov     eax, ebx
0x1800cf30b  mov     rcx, [rsp+98h+var_28]
0x1800cf310  xor     rcx, rsp; StackCookie
0x1800cf313  call    __security_check_cookie
0x1800cf318  mov     rbx, [rsp+98h+arg_0]
0x1800cf320  add     rsp, 80h
0x1800cf327  pop     r14
0x1800cf329  pop     rdi
0x1800cf32a  pop     rsi
0x1800cf32b  retn
```
