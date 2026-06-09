# DeleteInstalledCert(ushort const *,int)

- ea: `0x180044958`
- end: `0x180044ae9`
- name: `?DeleteInstalledCert@@YAJPEBGH@Z`
- size: `401`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800439fc`

## callees

- `0x1800140d0`
- `0x18001ab40`
- `0x180044958`
- `0x180044af0`
- `0x18006fdd8`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044a46`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044a46`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800449fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800449fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044a15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044a15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044a2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044a93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044a2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044a93`
- `CRYPT32!CertCloseStore` at `0x180044ac1`
- `CRYPT32!CertCloseStore` at `0x180044ac1`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180044a87`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180044a87`
- `CRYPT32!CertFreeCertificateContext` at `0x180044ab0`
- `CRYPT32!CertFreeCertificateContext` at `0x180044ab0`

## string_xrefs

- `0x1800449f6`: `SecRuntime.dll`
- `0x180044a0b`: `DeleteCertificateChain`
- `0x180044987`: `DeleteInstalledCert`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeleteInstalledCert(const unsigned __int16 *a1, int a2)
{
  __int64 v4; // rdx
  PCCERT_CONTEXT v5; // rbx
  DWORD cbCertEncoded; // edi
  BYTE *pbCertEncoded; // r15
  HMODULE Library; // rax
  HMODULE v9; // rsi
  FARPROC ProcAddress; // rax
  unsigned int v11; // edi
  signed int LastError; // eax
  int v13; // eax
  BOOL v14; // eax
  signed int v15; // eax
  unsigned int v16; // ebx
  HCERTSTORE hCertStore; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v19[3]; // [rsp+38h] [rbp-18h] BYREF
  int InstalledCert; // [rsp+90h] [rbp+40h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+98h] [rbp+48h] BYREF

  InstalledCert = 0;
  hCertStore = 0;
  pCertContext = 0;
  v19[0] = "DeleteInstalledCert";
  v19[1] = &InstalledCert;
  InstalledCert = GetInstalledCert(a1, &hCertStore, &pCertContext, a2, 0);
  v5 = pCertContext;
  if ( InstalledCert >= 0 )
  {
    if ( !pCertContext )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !v5->pbCertEncoded )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !v5->cbCertEncoded )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( a2 )
    {
      cbCertEncoded = v5->cbCertEncoded;
      pbCertEncoded = v5->pbCertEncoded;
      Library = LoadLibraryExW(L"SecRuntime.dll", 0, 0x800u);
      v9 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "DeleteCertificateChain");
        if ( ProcAddress )
        {
          v11 = ((__int64 (__fastcall *)(BYTE *, _QWORD))ProcAddress)(pbCertEncoded, cbCertEncoded);
        }
        else
        {
          LastError = GetLastError();
          v11 = LastError;
          if ( LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
        }
        FreeLibrary(v9);
        InstalledCert = v11;
        if ( v11 != -2147467263 )
          goto LABEL_24;
      }
      else
      {
        InstalledCert = -2147467263;
      }
    }
    v13 = DeleteSubjectCertificateFromEnrollmentNeededAccountStores(a1, v4);
    InstalledCert = v13;
    if ( v13 >= 0 || v13 == -2146885628 || v13 == -2147467263 )
    {
      InstalledCert = 0;
      v14 = CertDeleteCertificateFromStore(v5);
      v5 = 0;
      if ( v14 )
        goto LABEL_26;
      v15 = GetLastError();
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      InstalledCert = v15;
    }
  }
LABEL_24:
  if ( v5 )
    CertFreeCertificateContext(v5);
LABEL_26:
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  v16 = InstalledCert;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v19, v4);
  return v16;
}

```

## disassembly

```asm
0x180044958  mov     [rsp-28h+arg_0], rbx
0x18004495d  push    rbp
0x18004495e  push    rsi
0x18004495f  push    rdi
0x180044960  push    r14
0x180044962  push    r15
0x180044964  mov     rbp, rsp
0x180044967  sub     rsp, 50h
0x18004496b  mov     edi, edx
0x18004496d  mov     r14, rcx
0x180044970  mov     [rbp+arg_10], 0
0x180044977  mov     [rbp+hCertStore], 0
0x18004497f  mov     [rbp+pCertContext], 0
0x180044987  lea     rax, aDeleteinstalle; "DeleteInstalledCert"
0x18004498e  mov     [rbp+var_18], rax
0x180044992  lea     rax, [rbp+arg_10]
0x180044996  mov     [rbp+var_10], rax
0x18004499a  mov     [rsp+50h+var_30], 0; unsigned int *
0x1800449a3  mov     r9d, edx; int
0x1800449a6  lea     r8, [rbp+pCertContext]; struct _CERT_CONTEXT **
0x1800449aa  lea     rdx, [rbp+hCertStore]; void **
0x1800449ae  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x1800449b3  mov     [rbp+arg_10], eax
0x1800449b6  mov     rbx, [rbp+pCertContext]
0x1800449ba  test    eax, eax
0x1800449bc  js      loc_180044AA8
0x1800449c2  test    rbx, rbx
0x1800449c5  jnz     short loc_1800449CC
0x1800449c7  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "NULL != pCtx")
0x1800449cc  cmp     qword ptr [rbx+8], 0
0x1800449d1  jnz     short loc_1800449D8
0x1800449d3  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "NULL != pCtx->pbCertEncoded")
0x1800449d8  cmp     dword ptr [rbx+10h], 0
0x1800449dc  ja      short loc_1800449E3
0x1800449de  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pCtx->cbCertEncoded > 0")
0x1800449e3  test    edi, edi
0x1800449e5  jz      short loc_180044A60
0x1800449e7  mov     edi, [rbx+10h]
0x1800449ea  mov     r15, [rbx+8]
0x1800449ee  xor     edx, edx; hFile
0x1800449f0  mov     r8d, 800h; dwFlags
0x1800449f6  lea     rcx, LibFileName; "SecRuntime.dll"
0x1800449fd  call    cs:__imp_LoadLibraryExW
0x180044a03  mov     rsi, rax
0x180044a06  test    rax, rax
0x180044a09  jz      short loc_180044A59
0x180044a0b  lea     rdx, aDeletecertific; "DeleteCertificateChain"
0x180044a12  mov     rcx, rax; hModule
0x180044a15  call    cs:__imp_GetProcAddress
0x180044a1b  test    rax, rax
0x180044a1e  jz      short loc_180044A2E
0x180044a20  mov     edx, edi
0x180044a22  mov     rcx, r15
0x180044a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a2a  mov     edi, eax
0x180044a2c  jmp     short loc_180044A43
0x180044a2e  call    cs:__imp_GetLastError
0x180044a34  mov     edi, eax
0x180044a36  test    eax, eax
0x180044a38  jle     short loc_180044A43
0x180044a3a  movzx   edi, ax
0x180044a3d  or      edi, 80070000h
0x180044a43  mov     rcx, rsi; hLibModule
0x180044a46  call    cs:__imp_FreeLibrary
0x180044a4c  mov     [rbp+arg_10], edi
0x180044a4f  cmp     edi, 80004001h
0x180044a55  jnz     short loc_180044AA8
0x180044a57  jmp     short loc_180044A60
0x180044a59  mov     [rbp+arg_10], 80004001h
0x180044a60  mov     rcx, r14; unsigned __int16 *
0x180044a63  call    ?DeleteSubjectCertificateFromEnrollmentNeededAccountStores@@YAJPEBGK@Z; DeleteSubjectCertificateFromEnrollmentNeededAccountStores(ushort const *,ulong)
0x180044a68  mov     [rbp+arg_10], eax
0x180044a6b  test    eax, eax
0x180044a6d  jns     short loc_180044A7D
0x180044a6f  cmp     eax, 80092004h
0x180044a74  jz      short loc_180044A7D
0x180044a76  cmp     eax, 80004001h
0x180044a7b  jnz     short loc_180044AA8
0x180044a7d  mov     [rbp+arg_10], 0
0x180044a84  mov     rcx, rbx; pCertContext
0x180044a87  call    cs:__imp_CertDeleteCertificateFromStore
0x180044a8d  xor     ebx, ebx
0x180044a8f  test    eax, eax
0x180044a91  jnz     short loc_180044AB6
0x180044a93  call    cs:__imp_GetLastError
0x180044a99  test    eax, eax
0x180044a9b  jle     short loc_180044AA5
0x180044a9d  movzx   eax, ax
0x180044aa0  or      eax, 80070000h
0x180044aa5  mov     [rbp+arg_10], eax
0x180044aa8  test    rbx, rbx
0x180044aab  jz      short loc_180044AB6
0x180044aad  mov     rcx, rbx; pCertContext
0x180044ab0  call    cs:__imp_CertFreeCertificateContext
0x180044ab6  mov     rcx, [rbp+hCertStore]; hCertStore
0x180044aba  test    rcx, rcx
0x180044abd  jz      short loc_180044AC7
0x180044abf  xor     edx, edx; dwFlags
0x180044ac1  call    cs:__imp_CertCloseStore
0x180044ac7  mov     ebx, [rbp+arg_10]
0x180044aca  lea     rcx, [rbp+var_18]; this
0x180044ace  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180044ad3  mov     eax, ebx
0x180044ad5  mov     rbx, [rsp+50h+arg_0]
0x180044add  add     rsp, 50h
0x180044ae1  pop     r15
0x180044ae3  pop     r14
0x180044ae5  pop     rdi
0x180044ae6  pop     rsi
0x180044ae7  pop     rbp
0x180044ae8  retn
```
