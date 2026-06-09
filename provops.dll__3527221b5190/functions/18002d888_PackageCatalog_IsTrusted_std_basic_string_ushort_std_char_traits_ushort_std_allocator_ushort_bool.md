# PackageCatalog::IsTrusted(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,bool *)

- ea: `0x18002d888`
- end: `0x18002dc19`
- name: `?IsTrusted@PackageCatalog@@QEAA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_N@Z`
- size: `913`
- prototype: `char __fastcall(PackageCatalog *this, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180023558`

## callees

- `0x180001b4c`
- `0x18001b3a8`
- `0x180020710`
- `0x18002d368`
- `0x18002d450`
- `0x18002d888`
- `0x180033e9a`
- `0x180033ed0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002da2a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002db8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002da2a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002db8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002da19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002db7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002da19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002db7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d8f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d8f0`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18002d967`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18002d967`
- `CRYPT32!CertGetCertificateChain` at `0x18002da78`
- `CRYPT32!CertGetCertificateChain` at `0x18002da78`
- `CRYPT32!CertFreeCertificateChain` at `0x18002daf2`
- `CRYPT32!CertFreeCertificateChain` at `0x18002db32`
- `CRYPT32!CertFreeCertificateChain` at `0x18002daf2`
- `CRYPT32!CertFreeCertificateChain` at `0x18002db32`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18002d9fc`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18002db61`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18002d9fc`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18002db61`
- `CRYPT32!CertFreeCertificateContext` at `0x18002d9ed`
- `CRYPT32!CertFreeCertificateContext` at `0x18002db52`
- `CRYPT32!CertFreeCertificateContext` at `0x18002d9ed`
- `CRYPT32!CertFreeCertificateContext` at `0x18002db52`
- `CRYPT32!CertOpenStore` at `0x18002d91e`
- `CRYPT32!CertOpenStore` at `0x18002d91e`
- `CRYPT32!CertCloseStore` at `0x18002d9dc`
- `CRYPT32!CertCloseStore` at `0x18002da08`
- `CRYPT32!CertCloseStore` at `0x18002db03`
- `CRYPT32!CertCloseStore` at `0x18002db43`
- `CRYPT32!CertCloseStore` at `0x18002db6d`
- `CRYPT32!CertCloseStore` at `0x18002d9dc`
- `CRYPT32!CertCloseStore` at `0x18002da08`
- `CRYPT32!CertCloseStore` at `0x18002db03`
- `CRYPT32!CertCloseStore` at `0x18002db43`
- `CRYPT32!CertCloseStore` at `0x18002db6d`

## pseudocode

```c
char __fastcall PackageCatalog::IsTrusted(PackageCatalog *this, __int64 a2, _BYTE *a3)
{
  unsigned int v6; // eax
  const char *v7; // r9
  HCERTSTORE v8; // r14
  const char *v9; // r9
  HCERTCHAINENGINE v10; // rbx
  const CERT_CONTEXT *v11; // rcx
  char result; // al
  HCERTSTORE v13; // rsi
  const CERT_CONTEXT *v14; // rdi
  const char *v15; // rdx
  const char *v16; // r9
  const CERT_CHAIN_CONTEXT *v17; // rcx
  bool v18; // al
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  HCERTCHAINENGINE phChainEngine; // [rsp+40h] [rbp-C0h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HCERTSTORE hCertStore; // [rsp+58h] [rbp-A8h] BYREF
  _CERT_CHAIN_PARA pChainPara; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[24]; // [rsp+80h] [rbp-80h] BYREF
  HCERTSTORE v26; // [rsp+98h] [rbp-68h]
  HCERTCHAINENGINE v27; // [rsp+A0h] [rbp-60h]
  _CERT_CHAIN_ENGINE_CONFIG pConfig; // [rsp+B0h] [rbp-50h] BYREF
  int v29; // [rsp+100h] [rbp+0h]
  __int64 v30; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v30 = a2;
  if ( a3 )
    *a3 = 0;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Provisioning\\TrustedProvisioners", 0, 0x20019u, &hKey);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecatalog.cpp",
      (const char *)v6,
      phkResult);
  v8 = CertOpenStore((LPCSTR)4, 0x10001u, 0, 0x4000u, hKey);
  v26 = v8;
  if ( !v8 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecatalog.cpp",
      v7);
  phChainEngine = 0;
  memset_0(&pConfig, 0, 0x58u);
  pConfig.cbSize = 88;
  pConfig.hExclusiveRoot = v8;
  v29 = 1;
  if ( !CertCreateCertificateChainEngine(&pConfig, &phChainEngine) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecatalog.cpp",
      v9);
  v10 = phChainEngine;
  v27 = phChainEngine;
  memset(v25, 0, sizeof(v25));
  *(_QWORD *)&pChainPara.cbSize = 32;
  pChainPara.RequestedUsage.dwType = 0;
  *(_OWORD *)(&pChainPara.RequestedUsage.dwType + 1) = *(_OWORD *)&v25[4];
  HIDWORD(pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier) = 0;
  hCertStore = 0;
  phChainEngine = 0;
  if ( !(unsigned __int8)GetCertsOnFile(this, a2, &phChainEngine, &hCertStore) )
  {
    if ( hCertStore )
      CertCloseStore(hCertStore, 0);
    v11 = (const CERT_CONTEXT *)phChainEngine;
    if ( !phChainEngine )
      goto LABEL_11;
    goto LABEL_10;
  }
  if ( a3 )
    *a3 = 1;
  pChainContext = 0;
  v13 = hCertStore;
  v14 = (const CERT_CONTEXT *)phChainEngine;
  if ( !CertGetCertificateChain(v10, (PCCERT_CONTEXT)phChainEngine, 0, hCertStore, &pChainPara, 0, 0, &pChainContext) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecatalog.cpp",
      v16);
  if ( pChainContext->TrustStatus.dwErrorStatus )
  {
    if ( *(_DWORD *)g_hProvTraceProvider > 2u )
    {
      if ( *((_QWORD *)this + 3) >= 8u )
        this = *(PackageCatalog **)this;
      phChainEngine = this;
      LODWORD(hCertStore) = pChainContext->TrustStatus.dwErrorStatus;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        g_hProvTraceProvider,
        (__int64)byte_1800419D3,
        0,
        (__int64)v16,
        (__int64)&hCertStore,
        &phChainEngine);
    }
    v17 = pChainContext;
    goto LABEL_27;
  }
  v18 = PackageCatalog::CheckPolicy(this, v15, pChainContext);
  v17 = pChainContext;
  if ( !v18 )
  {
LABEL_27:
    if ( v17 )
      CertFreeCertificateChain(v17);
    if ( v13 )
      CertCloseStore(v13, 0);
    if ( !v14 )
      goto LABEL_11;
    v11 = v14;
LABEL_10:
    CertFreeCertificateContext(v11);
LABEL_11:
    if ( v10 )
      CertFreeCertificateChainEngine(v10);
    CertCloseStore(v8, 0);
    if ( hKey )
      RegCloseKey(hKey);
    if ( *(_QWORD *)(a2 + 24) >= 8u )
      operator delete(*(void **)a2);
    result = 0;
    goto LABEL_47;
  }
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  if ( v13 )
    CertCloseStore(v13, 0);
  if ( v14 )
    CertFreeCertificateContext(v14);
  if ( v10 )
    CertFreeCertificateChainEngine(v10);
  CertCloseStore(v8, 0);
  if ( hKey )
    RegCloseKey(hKey);
  if ( *(_QWORD *)(a2 + 24) >= 8u )
    operator delete(*(void **)a2);
  result = 1;
LABEL_47:
  *(_QWORD *)(a2 + 24) = 7;
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)a2 = 0;
  return result;
}

```

## disassembly

```asm
0x18002d888  mov     [rsp-8+arg_18], rbx
0x18002d88d  push    rbp
0x18002d88e  push    rsi
0x18002d88f  push    rdi
0x18002d890  push    r12
0x18002d892  push    r13
0x18002d894  push    r14
0x18002d896  push    r15
0x18002d898  lea     rbp, [rsp-20h]
0x18002d89d  sub     rsp, 120h
0x18002d8a4  mov     rax, cs:__security_cookie
0x18002d8ab  xor     rax, rsp
0x18002d8ae  mov     [rbp+50h+var_38], rax
0x18002d8b2  mov     rdi, r8
0x18002d8b5  mov     r15, rdx
0x18002d8b8  mov     r12, rcx
0x18002d8bb  mov     [rbp+50h+var_40], rdx
0x18002d8bf  xor     r13d, r13d
0x18002d8c2  test    r8, r8
0x18002d8c5  jz      short loc_18002D8CA
0x18002d8c7  mov     [r8], r13b
0x18002d8ca  mov     [rsp+150h+hKey], r13
0x18002d8cf  lea     rax, [rsp+150h+hKey]
0x18002d8d4  mov     [rsp+150h+phkResult], rax; unsigned int
0x18002d8d9  mov     r9d, 20019h; samDesired
0x18002d8df  xor     r8d, r8d; ulOptions
0x18002d8e2  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Provisioning\\Trus"...
0x18002d8e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d8f0  call    cs:__imp_RegOpenKeyExW
0x18002d8f6  mov     rcx, [rbp+58h]; this
0x18002d8fa  test    eax, eax
0x18002d8fc  jnz     loc_18002DBE0
0x18002d902  mov     rax, [rsp+150h+hKey]
0x18002d907  mov     [rsp+150h+phkResult], rax; pvPara
0x18002d90c  mov     r9d, 4000h; dwFlags
0x18002d912  xor     r8d, r8d; hCryptProv
0x18002d915  mov     edx, 10001h; dwEncodingType
0x18002d91a  lea     ecx, [r8+4]; lpszStoreProvider
0x18002d91e  call    cs:__imp_CertOpenStore
0x18002d924  mov     r14, rax
0x18002d927  mov     [rbp+50h+var_B8], rax
0x18002d92b  mov     rcx, [rbp+58h]; this
0x18002d92f  test    rax, rax
0x18002d932  jz      loc_18002DBF5
0x18002d938  mov     [rsp+150h+phChainEngine], r13
0x18002d93d  mov     ebx, 58h ; 'X'
0x18002d942  mov     r8d, ebx; Size
0x18002d945  xor     edx, edx; Val
0x18002d947  lea     rcx, [rbp+50h+pConfig]; void *
0x18002d94b  call    memset_0
0x18002d950  mov     [rbp+50h+pConfig.cbSize], ebx
0x18002d953  mov     [rbp+50h+pConfig.hExclusiveRoot], r14
0x18002d957  mov     [rbp+50h+var_50], 1
0x18002d95e  lea     rdx, [rsp+150h+phChainEngine]; phChainEngine
0x18002d963  lea     rcx, [rbp+50h+pConfig]; pConfig
0x18002d967  call    cs:__imp_CertCreateCertificateChainEngine
0x18002d96d  mov     rcx, [rbp+58h]; this
0x18002d971  test    eax, eax
0x18002d973  jz      loc_18002DC07
0x18002d979  mov     rbx, [rsp+150h+phChainEngine]
0x18002d97e  mov     [rbp+50h+var_B0], rbx
0x18002d982  xorps   xmm0, xmm0
0x18002d985  xor     eax, eax
0x18002d987  movups  [rbp+50h+var_D0], xmm0
0x18002d98b  mov     [rbp+50h+var_C0], rax
0x18002d98f  mov     qword ptr [rsp+150h+pChainPara.cbSize], 20h ; ' '
0x18002d998  mov     [rsp+150h+pChainPara.RequestedUsage.dwType], r13d
0x18002d99d  movups  xmm0, [rbp+50h+var_D0+4]
0x18002d9a1  movups  xmmword ptr [rsp+150h+pChainPara.RequestedUsage+4], xmm0
0x18002d9a6  mov     eax, dword ptr [rbp+50h+var_C0+4]
0x18002d9a9  mov     dword ptr [rsp+150h+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier+4], eax
0x18002d9ad  mov     [rsp+150h+hCertStore], r13
0x18002d9b2  mov     [rsp+150h+phChainEngine], r13
0x18002d9b7  lea     r9, [rsp+150h+hCertStore]
0x18002d9bc  lea     r8, [rsp+150h+phChainEngine]
0x18002d9c1  mov     rdx, r15
0x18002d9c4  mov     rcx, r12
0x18002d9c7  call    GetCertsOnFile
0x18002d9cc  test    al, al
0x18002d9ce  jnz     short loc_18002DA37
0x18002d9d0  mov     rcx, [rsp+150h+hCertStore]; hCertStore
0x18002d9d5  test    rcx, rcx
0x18002d9d8  jz      short loc_18002D9E3
0x18002d9da  xor     edx, edx; dwFlags
0x18002d9dc  call    cs:__imp_CertCloseStore
0x18002d9e2  nop
0x18002d9e3  mov     rcx, [rsp+150h+phChainEngine]; pCertContext
0x18002d9e8  test    rcx, rcx
0x18002d9eb  jz      short loc_18002D9F4
0x18002d9ed  call    cs:__imp_CertFreeCertificateContext
0x18002d9f3  nop
0x18002d9f4  test    rbx, rbx
0x18002d9f7  jz      short loc_18002DA03
0x18002d9f9  mov     rcx, rbx; hChainEngine
0x18002d9fc  call    cs:__imp_CertFreeCertificateChainEngine
0x18002da02  nop
0x18002da03  xor     edx, edx; dwFlags
0x18002da05  mov     rcx, r14; hCertStore
0x18002da08  call    cs:__imp_CertCloseStore
0x18002da0e  nop
0x18002da0f  mov     rcx, [rsp+150h+hKey]; hKey
0x18002da14  test    rcx, rcx
0x18002da17  jz      short loc_18002DA20
0x18002da19  call    cs:__imp_RegCloseKey
0x18002da1f  nop
0x18002da20  cmp     qword ptr [r15+18h], 8
0x18002da25  jb      short loc_18002DA30
0x18002da27  mov     rcx, [r15]
0x18002da2a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002da30  xor     al, al
0x18002da32  jmp     loc_18002DB97
0x18002da37  test    rdi, rdi
0x18002da3a  jz      short loc_18002DA3F
0x18002da3c  mov     byte ptr [rdi], 1
0x18002da3f  mov     [rsp+150h+pChainContext], r13
0x18002da44  lea     rax, [rsp+150h+pChainContext]
0x18002da49  mov     [rsp+150h+ppChainContext], rax; ppChainContext
0x18002da4e  mov     [rsp+150h+pvReserved], r13; pvReserved
0x18002da53  mov     [rsp+150h+dwFlags], r13d; dwFlags
0x18002da58  lea     rax, [rsp+150h+pChainPara]
0x18002da5d  mov     [rsp+150h+phkResult], rax; pChainPara
0x18002da62  mov     rsi, [rsp+150h+hCertStore]
0x18002da67  mov     r9, rsi; hAdditionalStore
0x18002da6a  xor     r8d, r8d; pTime
0x18002da6d  mov     rdi, [rsp+150h+phChainEngine]
0x18002da72  mov     rdx, rdi; pCertContext
0x18002da75  mov     rcx, rbx; hChainEngine
0x18002da78  call    cs:__imp_CertGetCertificateChain
0x18002da7e  mov     rcx, [rbp+58h]; this
0x18002da82  test    eax, eax
0x18002da84  jz      loc_18002DBCE
0x18002da8a  mov     r8, [rsp+150h+pChainContext]; struct _CERT_CHAIN_CONTEXT *
0x18002da8f  cmp     [r8+4], r13d
0x18002da93  jz      loc_18002DB1B
0x18002da99  mov     rcx, cs:g_hProvTraceProvider
0x18002daa0  mov     eax, [rcx]
0x18002daa2  cmp     eax, 2
0x18002daa5  jbe     short loc_18002DAE8
0x18002daa7  cmp     qword ptr [r12+18h], 8
0x18002daad  jb      short loc_18002DAB3
0x18002daaf  mov     r12, [r12]
0x18002dab3  mov     [rsp+150h+phChainEngine], r12
0x18002dab8  mov     rax, [rsp+150h+pChainContext]
0x18002dabd  mov     edx, [rax+4]
0x18002dac0  mov     dword ptr [rsp+150h+hCertStore], edx
0x18002dac4  lea     rax, [rsp+150h+phChainEngine]
0x18002dac9  mov     qword ptr [rsp+150h+dwFlags], rax
0x18002dace  lea     rax, [rsp+150h+hCertStore]
0x18002dad3  mov     [rsp+150h+phkResult], rax
0x18002dad8  xor     r8d, r8d
0x18002dadb  lea     rdx, byte_1800419D3
0x18002dae2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18002dae7  nop
0x18002dae8  mov     rcx, [rsp+150h+pChainContext]; pChainContext
0x18002daed  test    rcx, rcx
0x18002daf0  jz      short loc_18002DAF9
0x18002daf2  call    cs:__imp_CertFreeCertificateChain
0x18002daf8  nop
0x18002daf9  test    rsi, rsi
0x18002dafc  jz      short loc_18002DB0A
0x18002dafe  xor     edx, edx; dwFlags
0x18002db00  mov     rcx, rsi; hCertStore
0x18002db03  call    cs:__imp_CertCloseStore
0x18002db09  nop
0x18002db0a  test    rdi, rdi
0x18002db0d  jz      loc_18002D9F4
0x18002db13  mov     rcx, rdi
0x18002db16  jmp     loc_18002D9ED
0x18002db1b  mov     rcx, r12; this
0x18002db1e  call    ?CheckPolicy@PackageCatalog@@AEAA_NPEBDPEBU_CERT_CHAIN_CONTEXT@@@Z; PackageCatalog::CheckPolicy(char const *,_CERT_CHAIN_CONTEXT const *)
0x18002db23  nop
0x18002db24  mov     rcx, [rsp+150h+pChainContext]; pChainContext
0x18002db29  test    al, al
0x18002db2b  jz      short loc_18002DAED
0x18002db2d  test    rcx, rcx
0x18002db30  jz      short loc_18002DB39
0x18002db32  call    cs:__imp_CertFreeCertificateChain
0x18002db38  nop
0x18002db39  test    rsi, rsi
0x18002db3c  jz      short loc_18002DB4A
0x18002db3e  xor     edx, edx; dwFlags
0x18002db40  mov     rcx, rsi; hCertStore
0x18002db43  call    cs:__imp_CertCloseStore
0x18002db49  nop
0x18002db4a  test    rdi, rdi
0x18002db4d  jz      short loc_18002DB59
0x18002db4f  mov     rcx, rdi; pCertContext
0x18002db52  call    cs:__imp_CertFreeCertificateContext
0x18002db58  nop
0x18002db59  test    rbx, rbx
0x18002db5c  jz      short loc_18002DB68
0x18002db5e  mov     rcx, rbx; hChainEngine
0x18002db61  call    cs:__imp_CertFreeCertificateChainEngine
0x18002db67  nop
0x18002db68  xor     edx, edx; dwFlags
0x18002db6a  mov     rcx, r14; hCertStore
0x18002db6d  call    cs:__imp_CertCloseStore
0x18002db73  nop
0x18002db74  mov     rcx, [rsp+150h+hKey]; hKey
0x18002db79  test    rcx, rcx
0x18002db7c  jz      short loc_18002DB85
0x18002db7e  call    cs:__imp_RegCloseKey
0x18002db84  nop
0x18002db85  cmp     qword ptr [r15+18h], 8
0x18002db8a  jb      short loc_18002DB95
0x18002db8c  mov     rcx, [r15]
0x18002db8f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002db95  mov     al, 1
0x18002db97  mov     qword ptr [r15+18h], 7
0x18002db9f  mov     [r15+10h], r13
0x18002dba3  mov     [r15], r13w
0x18002dba7  mov     rcx, [rbp+50h+var_38]
0x18002dbab  xor     rcx, rsp; StackCookie
0x18002dbae  call    __security_check_cookie
0x18002dbb3  mov     rbx, [rsp+150h+arg_18]
0x18002dbbb  add     rsp, 120h
0x18002dbc2  pop     r15
0x18002dbc4  pop     r14
0x18002dbc6  pop     r13
0x18002dbc8  pop     r12
0x18002dbca  pop     rdi
0x18002dbcb  pop     rsi
0x18002dbcc  pop     rbp
0x18002dbcd  retn
0x18002dbce  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\packageca"...
0x18002dbd5  mov     edx, 0D7h; void *
0x18002dbda  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002dbe0  mov     r9d, eax; char *
0x18002dbe3  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\packageca"...
0x18002dbea  mov     edx, 0B4h; void *
0x18002dbef  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002dbf5  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\packageca"...
0x18002dbfc  mov     edx, 0B9h; void *
0x18002dc01  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002dc07  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\packageca"...
0x18002dc0e  mov     edx, 1Fh; void *
0x18002dc13  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
