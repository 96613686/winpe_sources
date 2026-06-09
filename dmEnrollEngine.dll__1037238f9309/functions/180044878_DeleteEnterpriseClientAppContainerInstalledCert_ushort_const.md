# DeleteEnterpriseClientAppContainerInstalledCert(ushort const *)

- ea: `0x180044878`
- end: `0x180044950`
- name: `?DeleteEnterpriseClientAppContainerInstalledCert@@YAJPEBG@Z`
- size: `216`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004f260`

## callees

- `0x1800140d0`
- `0x18001ab40`
- `0x180044878`
- `0x18006fdd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044903`
- `CRYPT32!CertCloseStore` at `0x180044931`
- `CRYPT32!CertCloseStore` at `0x180044931`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x1800448f7`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x1800448f7`
- `CRYPT32!CertFreeCertificateContext` at `0x180044920`
- `CRYPT32!CertFreeCertificateContext` at `0x180044920`

## string_xrefs

- `0x18004489c`: `DeleteEnterpriseClientAppContainerInstalledCert`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeleteEnterpriseClientAppContainerInstalledCert(const unsigned __int16 *a1)
{
  __int64 v1; // rdx
  PCCERT_CONTEXT v2; // rbx
  BOOL v3; // eax
  signed int LastError; // eax
  unsigned int v5; // ebx
  _QWORD v7[2]; // [rsp+30h] [rbp-10h] BYREF
  int InstalledCert; // [rsp+58h] [rbp+18h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+60h] [rbp+20h] BYREF
  HCERTSTORE hCertStore; // [rsp+68h] [rbp+28h] BYREF

  InstalledCert = 0;
  hCertStore = 0;
  pCertContext = 0;
  v7[0] = "DeleteEnterpriseClientAppContainerInstalledCert";
  v7[1] = &InstalledCert;
  InstalledCert = GetInstalledCert(a1, &hCertStore, &pCertContext, 0, 0);
  v2 = pCertContext;
  if ( InstalledCert < 0 )
  {
LABEL_12:
    if ( v2 )
      CertFreeCertificateContext(v2);
    goto LABEL_14;
  }
  if ( !pCertContext )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !v2->pbCertEncoded )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !v2->cbCertEncoded )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v3 = CertDeleteCertificateFromStore(v2);
  v2 = 0;
  if ( !v3 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    InstalledCert = LastError;
    goto LABEL_12;
  }
LABEL_14:
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  v5 = InstalledCert;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v7, v1);
  return v5;
}

```

## disassembly

```asm
0x180044878  mov     [rsp-8+arg_0], rbx
0x18004487d  push    rbp
0x18004487e  mov     rbp, rsp
0x180044881  sub     rsp, 40h
0x180044885  mov     [rbp+arg_8], 0
0x18004488c  mov     [rbp+hCertStore], 0
0x180044894  mov     [rbp+pCertContext], 0
0x18004489c  lea     rax, aDeleteenterpri; "DeleteEnterpriseClientAppContainerInsta"...
0x1800448a3  mov     [rbp+var_10], rax
0x1800448a7  lea     rax, [rbp+arg_8]
0x1800448ab  mov     [rbp+var_8], rax
0x1800448af  mov     [rsp+40h+var_20], 0; unsigned int *
0x1800448b8  xor     r9d, r9d; int
0x1800448bb  lea     r8, [rbp+pCertContext]; struct _CERT_CONTEXT **
0x1800448bf  lea     rdx, [rbp+hCertStore]; void **
0x1800448c3  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x1800448c8  mov     [rbp+arg_8], eax
0x1800448cb  mov     rbx, [rbp+pCertContext]
0x1800448cf  test    eax, eax
0x1800448d1  js      short loc_180044918
0x1800448d3  test    rbx, rbx
0x1800448d6  jnz     short loc_1800448DD
0x1800448d8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "NULL != pCtx")
0x1800448dd  cmp     qword ptr [rbx+8], 0
0x1800448e2  jnz     short loc_1800448E9
0x1800448e4  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "NULL != pCtx->pbCertEncoded")
0x1800448e9  cmp     dword ptr [rbx+10h], 0
0x1800448ed  ja      short loc_1800448F4
0x1800448ef  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pCtx->cbCertEncoded > 0")
0x1800448f4  mov     rcx, rbx; pCertContext
0x1800448f7  call    cs:__imp_CertDeleteCertificateFromStore
0x1800448fd  xor     ebx, ebx
0x1800448ff  test    eax, eax
0x180044901  jnz     short loc_180044926
0x180044903  call    cs:__imp_GetLastError
0x180044909  test    eax, eax
0x18004490b  jle     short loc_180044915
0x18004490d  movzx   eax, ax
0x180044910  or      eax, 80070000h
0x180044915  mov     [rbp+arg_8], eax
0x180044918  test    rbx, rbx
0x18004491b  jz      short loc_180044926
0x18004491d  mov     rcx, rbx; pCertContext
0x180044920  call    cs:__imp_CertFreeCertificateContext
0x180044926  mov     rcx, [rbp+hCertStore]; hCertStore
0x18004492a  test    rcx, rcx
0x18004492d  jz      short loc_180044937
0x18004492f  xor     edx, edx; dwFlags
0x180044931  call    cs:__imp_CertCloseStore
0x180044937  mov     ebx, [rbp+arg_8]
0x18004493a  lea     rcx, [rbp+var_10]; this
0x18004493e  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180044943  mov     eax, ebx
0x180044945  mov     rbx, [rsp+40h+arg_0]
0x18004494a  add     rsp, 40h
0x18004494e  pop     rbp
0x18004494f  retn
```
