# CBackgroundCopyJobExt::SetClientCertificateByID(BG_CERT_STORE_LOCATION,wchar_t const *,uchar *)

- ea: `0x180013450`
- end: `0x1800136aa`
- name: `?SetClientCertificateByID@CBackgroundCopyJobExt@@UEAAJW4BG_CERT_STORE_LOCATION@@PEB_WPEAE@Z`
- size: `602`
- prototype: `__int64 __fastcall(CBackgroundCopyJobExt *this, enum BG_CERT_STORE_LOCATION, const wchar_t *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008618`
- `0x18000933c`
- `0x18000cea4`
- `0x180013450`
- `0x18008ce48`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001362c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180013662`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001362c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180013662`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180013521`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180013521`
- `CRYPT32!CertFreeCertificateContext` at `0x180013621`
- `CRYPT32!CertFreeCertificateContext` at `0x180013621`
- `CRYPT32!CertOpenStore` at `0x180013561`
- `CRYPT32!CertOpenStore` at `0x180013561`
- `CRYPT32!CertFindCertificateInStore` at `0x1800135c2`
- `CRYPT32!CertFindCertificateInStore` at `0x1800135c2`
- `CRYPT32!CertCloseStore` at `0x1800135f0`
- `CRYPT32!CertCloseStore` at `0x18001363b`
- `CRYPT32!CertCloseStore` at `0x1800135f0`
- `CRYPT32!CertCloseStore` at `0x18001363b`

## string_xrefs

- `0x180013697`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180013499`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x1800134c7`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x1800134f4`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x180013577`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x1800135d8`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x180013608`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CBackgroundCopyJobExt::SetClientCertificateByID(
        CBackgroundCopyJobExt *this,
        enum BG_CERT_STORE_LOCATION a2,
        const wchar_t *a3,
        unsigned __int8 *a4)
{
  PCCERT_CONTEXT CertificateInStore; // rdi
  char v8; // bl
  char v9; // r14
  char v10; // r13
  char v11; // r12
  HRESULT v12; // eax
  const char *v13; // r9
  HCERTSTORE v14; // r15
  int LastError; // esi
  const char *v16; // r9
  int pvPara; // [rsp+20h] [rbp-78h]
  int pvParaa; // [rsp+20h] [rbp-78h]
  _QWORD pvFindPara[2]; // [rsp+48h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  CertificateInStore = 0;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33C,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
      (const char *)0x80004003LL,
      pvPara);
    return 2147500035LL;
  }
  if ( !*a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33D,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
      (const char *)0x80070057LL,
      pvPara);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33E,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
      (const char *)0x80004003LL,
      pvPara);
    return 2147500035LL;
  }
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  if ( a2 == BG_CERT_STORE_LOCATION_CURRENT_USER )
  {
    v12 = CoImpersonateClient();
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1262,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v12,
        pvPara);
    v8 = 1;
    v9 = 1;
    v10 = 1;
    v11 = 1;
  }
  v14 = CertOpenStore((LPCSTR)0xA, 0, 0, ((a2 << 16) + 0x10000) | 0xC000u, a3);
  if ( v14 )
  {
    pvFindPara[0] = 20;
    pvFindPara[1] = a4;
    CertificateInStore = CertFindCertificateInStore(v14, 0x10001u, 0, 0x10000u, pvFindPara, 0);
    if ( CertificateInStore )
    {
      CertCloseStore(v14, 0);
      v9 = v11;
      goto LABEL_19;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x334,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
                  v16);
    CertCloseStore(v14, 0);
    v9 = v10;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x32F,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
                  v13);
  }
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x348,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
      (const char *)(unsigned int)LastError,
      pvParaa);
    if ( v8 )
      CoRevertToSelf();
    return (unsigned int)LastError;
  }
LABEL_19:
  pvFindPara[0] = CertificateInStore;
  CBackgroundCopyJob::SetClientCertificate(*((_QWORD *)this + 4), pvFindPara);
  if ( v9 )
    CoRevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x180013450  push    rbx
0x180013452  push    rsi
0x180013453  push    rdi
0x180013454  push    r12
0x180013456  push    r13
0x180013458  push    r14
0x18001345a  push    r15
0x18001345c  sub     rsp, 60h
0x180013460  mov     rax, cs:__security_cookie
0x180013467  xor     rax, rsp
0x18001346a  mov     [rsp+98h+var_40], rax
0x18001346f  mov     rax, r9
0x180013472  mov     [rsp+98h+var_60], rax
0x180013477  mov     rsi, r8
0x18001347a  mov     r15d, edx
0x18001347d  mov     [rsp+98h+var_58], rcx
0x180013482  xor     edi, edi
0x180013484  test    r8, r8
0x180013487  jnz     short loc_1800134B1
0x180013489  mov     rcx, [rsp+98h]; this
0x180013491  mov     ebx, 80004003h
0x180013496  mov     r9d, ebx; char *
0x180013499  lea     r8, aCW1SSrcDeliver_81; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800134a0  mov     edx, 33Ch; void *
0x1800134a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800134aa  mov     eax, ebx
0x1800134ac  jmp     loc_180013677
0x1800134b1  cmp     [r8], di
0x1800134b5  jnz     short loc_1800134DF
0x1800134b7  mov     rcx, [rsp+98h]; this
0x1800134bf  mov     ebx, 80070057h
0x1800134c4  mov     r9d, ebx; char *
0x1800134c7  lea     r8, aCW1SSrcDeliver_81; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800134ce  mov     edx, 33Dh; void *
0x1800134d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800134d8  mov     eax, ebx
0x1800134da  jmp     loc_180013677
0x1800134df  test    rax, rax
0x1800134e2  jnz     short loc_18001350C
0x1800134e4  mov     rcx, [rsp+98h]; this
0x1800134ec  mov     ebx, 80004003h
0x1800134f1  mov     r9d, ebx; char *
0x1800134f4  lea     r8, aCW1SSrcDeliver_81; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800134fb  mov     edx, 33Eh; void *
0x180013500  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013505  mov     eax, ebx
0x180013507  jmp     loc_180013677
0x18001350c  mov     bl, dil
0x18001350f  mov     [rsp+98h+var_68], bl
0x180013513  mov     r14b, dil
0x180013516  mov     r13b, dil
0x180013519  mov     r12b, dil
0x18001351c  test    r15d, r15d
0x18001351f  jnz     short loc_180013542
0x180013521  call    cs:__imp_CoImpersonateClient
0x180013527  mov     rcx, [rsp+98h]; this
0x18001352f  test    eax, eax
0x180013531  js      loc_180013694
0x180013537  mov     bl, 1
0x180013539  mov     r14b, bl
0x18001353c  mov     r13b, bl
0x18001353f  mov     r12b, bl
0x180013542  shl     r15d, 10h
0x180013546  lea     r9d, [r15+10000h]
0x18001354d  or      r9d, 0C000h; dwFlags
0x180013554  mov     [rsp+98h+pvPara], rsi; pvPara
0x180013559  xor     r8d, r8d; hCryptProv
0x18001355c  xor     edx, edx; dwEncodingType
0x18001355e  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180013561  call    cs:__imp_CertOpenStore
0x180013567  mov     r15, rax
0x18001356a  test    rax, rax
0x18001356d  jnz     short loc_18001358C
0x18001356f  mov     rcx, [rsp+98h]; this
0x180013577  lea     r8, aCW1SSrcDeliver_81; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18001357e  mov     edx, 32Fh; void *
0x180013583  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013588  mov     esi, eax
0x18001358a  jmp     short loc_1800135F9
0x18001358c  mov     [rsp+98h+pvFindPara], 14h
0x180013595  mov     rax, [rsp+98h+var_60]
0x18001359a  mov     [rsp+98h+var_48], rax
0x18001359f  mov     [rsp+98h+pPrevCertContext], 0; pPrevCertContext
0x1800135a8  lea     rax, [rsp+98h+pvFindPara]
0x1800135ad  mov     [rsp+98h+pvPara], rax; int
0x1800135b2  mov     r9d, 10000h; dwFindType
0x1800135b8  xor     r8d, r8d; dwFindFlags
0x1800135bb  lea     edx, [r9+1]; dwCertEncodingType
0x1800135bf  mov     rcx, r15; hCertStore
0x1800135c2  call    cs:__imp_CertFindCertificateInStore
0x1800135c8  mov     rdi, rax
0x1800135cb  test    rax, rax
0x1800135ce  jnz     short loc_180013636
0x1800135d0  mov     rcx, [rsp+98h]; this
0x1800135d8  lea     r8, aCW1SSrcDeliver_81; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800135df  mov     edx, 334h; void *
0x1800135e4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800135e9  mov     esi, eax
0x1800135eb  xor     edx, edx; dwFlags
0x1800135ed  mov     rcx, r15; hCertStore
0x1800135f0  call    cs:__imp_CertCloseStore
0x1800135f6  mov     r14b, r13b
0x1800135f9  test    esi, esi
0x1800135fb  jns     short loc_180013644
0x1800135fd  mov     rcx, [rsp+98h]; this
0x180013605  mov     r9d, esi; char *
0x180013608  lea     r8, aCW1SSrcDeliver_81; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18001360f  mov     edx, 348h; void *
0x180013614  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013619  test    rdi, rdi
0x18001361c  jz      short loc_180013628
0x18001361e  mov     rcx, rdi; pCertContext
0x180013621  call    cs:__imp_CertFreeCertificateContext
0x180013627  nop
0x180013628  test    bl, bl
0x18001362a  jz      short loc_180013632
0x18001362c  call    cs:__imp_CoRevertToSelf
0x180013632  mov     eax, esi
0x180013634  jmp     short loc_180013677
0x180013636  xor     edx, edx; dwFlags
0x180013638  mov     rcx, r15; hCertStore
0x18001363b  call    cs:__imp_CertCloseStore
0x180013641  mov     r14b, r12b
0x180013644  mov     [rsp+98h+pvFindPara], rdi
0x180013649  lea     rdx, [rsp+98h+pvFindPara]
0x18001364e  mov     rcx, [rsp+98h+var_58]
0x180013653  mov     rcx, [rcx+20h]
0x180013657  call    ?SetClientCertificate@CBackgroundCopyJob@@QEAAXV?$unique_any_t@Ucert_context_t@wil@@@wil@@@Z; CBackgroundCopyJob::SetClientCertificate(wil::unique_any_t<wil::cert_context_t>)
0x18001365c  nop
0x18001365d  test    r14b, r14b
0x180013660  jz      short loc_180013668
0x180013662  call    cs:__imp_CoRevertToSelf
0x180013668  xor     eax, eax
0x18001366a  jmp     short loc_180013677
0x18001366c  mov     eax, dword ptr [rsp+98h+pvFindPara]
0x180013670  jmp     short loc_180013677
0x180013672  mov     eax, 8007000Eh
0x180013677  mov     rcx, [rsp+98h+var_40]
0x18001367c  xor     rcx, rsp; StackCookie
0x18001367f  call    __security_check_cookie
0x180013684  add     rsp, 60h
0x180013688  pop     r15
0x18001368a  pop     r14
0x18001368c  pop     r13
0x18001368e  pop     r12
0x180013690  pop     rdi
0x180013691  pop     rsi
0x180013692  pop     rbx
0x180013693  retn
0x180013694  mov     r9d, eax; char *
0x180013697  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18001369e  mov     edx, 1262h; void *
0x1800136a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
