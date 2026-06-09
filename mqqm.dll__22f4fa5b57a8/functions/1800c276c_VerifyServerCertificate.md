# VerifyServerCertificate

- ea: `0x1800c276c`
- end: `0x1800c2b76`
- name: `VerifyServerCertificate`
- size: `1034`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c1638`

## callees

- `0x180004d91`
- `0x18000d1f0`
- `0x18000f35c`
- `0x18009aa2c`
- `0x1800bec44`
- `0x1800bec68`
- `0x1800c1398`
- `0x1800c276c`
- `0x1800d00c0`
- `0x1800d01a4`

## import_xrefs

- `msvcrt!??0exception@@QEAA@XZ` at `0x1800c2800`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800c287d`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800c2981`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800c29ee`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800c2ab3`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800c2b2a`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800c2800`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800c287d`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800c2981`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800c29ee`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800c2ab3`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800c2b2a`
- `KERNEL32!GetLastError` at `0x1800c2926`
- `KERNEL32!GetLastError` at `0x1800c2958`
- `KERNEL32!GetLastError` at `0x1800c2a58`
- `KERNEL32!GetLastError` at `0x1800c2a8a`
- `KERNEL32!GetLastError` at `0x1800c2926`
- `KERNEL32!GetLastError` at `0x1800c2958`
- `KERNEL32!GetLastError` at `0x1800c2a58`
- `KERNEL32!GetLastError` at `0x1800c2a8a`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800c2a4e`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800c2a4e`
- `CRYPT32!CertGetCertificateChain` at `0x1800c291c`
- `CRYPT32!CertGetCertificateChain` at `0x1800c291c`
- `CRYPT32!CertOpenSystemStoreW` at `0x1800c27b9`
- `CRYPT32!CertOpenSystemStoreW` at `0x1800c27b9`
- `CRYPT32!CertFindCertificateInStore` at `0x1800c2832`
- `CRYPT32!CertFindCertificateInStore` at `0x1800c2832`

## string_xrefs

- `0x1800c28b3`: `security`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall VerifyServerCertificate(PCCERT_CONTEXT pCertContext, __int64 a2)
{
  HCERTSTORE v4; // rax
  unsigned int v5; // ecx
  signed int LastError; // eax
  unsigned int v7; // ecx
  DWORD v8; // eax
  signed int dwErrorStatus; // eax
  unsigned int v10; // ecx
  signed int v11; // eax
  unsigned int v12; // ecx
  DWORD v13; // eax
  DWORD dwError; // edx
  int pExceptionObject; // [rsp+40h] [rbp-59h] BYREF
  const wchar_t *v16; // [rsp+48h] [rbp-51h]
  const wchar_t *v17; // [rsp+50h] [rbp-49h]
  int v18; // [rsp+58h] [rbp-41h]
  __int64 v19; // [rsp+60h] [rbp-39h]
  __int128 v20; // [rsp+68h] [rbp-31h] BYREF
  __int64 v21; // [rsp+78h] [rbp-21h]
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+80h] [rbp-19h] BYREF
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+98h] [rbp-1h] BYREF
  PCCERT_CONTEXT CertificateInStore; // [rsp+A8h] [rbp+Fh] BYREF
  HCERTSTORE v25; // [rsp+B0h] [rbp+17h] BYREF
  int v26; // [rsp+B8h] [rbp+1Fh]
  _CERT_CHAIN_PARA pChainPara; // [rsp+C0h] [rbp+27h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+118h] [rbp+7Fh] BYREF

  v20 = 0;
  v21 = 0;
  pPolicyPara = 0;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  memset(&pChainPara, 0, sizeof(pChainPara));
  v4 = CertOpenSystemStoreW(0, L"Disallowed");
  v25 = v4;
  v26 = 0;
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, WPP_141b597a36f53d015b025654940084c8_Traceguids);
    exception::exception((exception *)&pExceptionObject);
    throw (exception *)&pExceptionObject;
  }
  CertificateInStore = CertFindCertificateInStore(v4, 0x10001u, 0, 0xD0000u, pCertContext, 0);
  if ( CertificateInStore )
  {
    EvReportWithFrequency(0x8000088F);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, WPP_141b597a36f53d015b025654940084c8_Traceguids);
    exception::exception((exception *)&pExceptionObject);
    throw (exception *)&pExceptionObject;
  }
  memset(&pChainPara, 0, sizeof(pChainPara));
  pChainPara.cbSize = 32;
  pChainContext = 0;
  pExceptionObject = 0;
  v16 = L"security";
  v17 = L"SkipRevocationCheck";
  v18 = 0;
  v19 = 0;
  QueryValueInternal((struct RegEntry *)&pExceptionObject);
  if ( !CertGetCertificateChain(
          (HCERTCHAINENGINE)1,
          pCertContext,
          0,
          pCertContext->hCertStore,
          &pChainPara,
          0x20000000u,
          0,
          &pChainContext) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    EvReportWithErrorAndFrequency(v7, LastError);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v8 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 13, WPP_141b597a36f53d015b025654940084c8_Traceguids, v8);
    }
    exception::exception((exception *)&pExceptionObject);
    throw (exception *)&pExceptionObject;
  }
  dwErrorStatus = pChainContext->TrustStatus.dwErrorStatus;
  if ( dwErrorStatus )
  {
    if ( dwErrorStatus > 0 )
      dwErrorStatus = (unsigned __int16)dwErrorStatus | 0x80070000;
    EvReportWithErrorAndFrequency(v5, dwErrorStatus);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        14,
        WPP_141b597a36f53d015b025654940084c8_Traceguids,
        pChainContext->TrustStatus.dwErrorStatus);
    exception::exception((exception *)&pExceptionObject);
    throw (exception *)&pExceptionObject;
  }
  v20 = 0x200000018uLL;
  v21 = a2;
  *(_QWORD *)&pPolicyPara.cbSize = 16;
  pPolicyPara.pvExtraPolicyPara = &v20;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  pPolicyStatus.cbSize = 24;
  if ( !CertVerifyCertificateChainPolicy((LPCSTR)4, pChainContext, &pPolicyPara, &pPolicyStatus) )
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    EvReportWithErrorAndFrequency(v12, v11);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v13 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, WPP_141b597a36f53d015b025654940084c8_Traceguids, v13);
    }
    exception::exception((exception *)&pExceptionObject);
    throw (exception *)&pExceptionObject;
  }
  dwError = pPolicyStatus.dwError;
  if ( pPolicyStatus.dwError )
  {
    if ( pPolicyStatus.dwError == -2146762481 )
    {
      EvReportWithFrequency(0x80000891);
    }
    else
    {
      if ( (int)pPolicyStatus.dwError > 0 )
        dwError = LOWORD(pPolicyStatus.dwError) | 0x80070000;
      EvReportWithErrorAndFrequency(v10, dwError);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        16,
        WPP_141b597a36f53d015b025654940084c8_Traceguids,
        pPolicyStatus.dwError);
    exception::exception((exception *)&pExceptionObject);
    throw (exception *)&pExceptionObject;
  }
  CCertificateChain::~CCertificateChain((CCertificateChain *)&pChainContext);
  CCertificateContext::~CCertificateContext((CCertificateContext *)&CertificateInStore);
  CCertOpenStore::~CCertOpenStore((CCertOpenStore *)&v25);
}

```

## disassembly

```asm
0x1800c276c  mov     [rsp-8+arg_0], rbx
0x1800c2771  mov     [rsp-8+arg_8], rsi
0x1800c2776  push    rbp
0x1800c2777  push    rdi
0x1800c2778  push    r14
0x1800c277a  lea     rbp, [rsp-47h]
0x1800c277f  sub     rsp, 0E0h
0x1800c2786  mov     rsi, rdx
0x1800c2789  mov     rdi, rcx
0x1800c278c  xorps   xmm0, xmm0
0x1800c278f  xor     eax, eax
0x1800c2791  movups  [rbp+57h+var_88], xmm0
0x1800c2795  mov     [rbp+57h+var_78], rax
0x1800c2799  movups  xmmword ptr [rbp+57h+pPolicyPara.cbSize], xmm0
0x1800c279d  xorps   xmm1, xmm1
0x1800c27a0  movups  xmmword ptr [rbp+57h+pPolicyStatus.cbSize], xmm1
0x1800c27a4  mov     [rbp+57h+pPolicyStatus.pvExtraPolicyStatus], rax
0x1800c27a8  movups  xmmword ptr [rbp+57h+pChainPara.cbSize], xmm0
0x1800c27ac  movups  xmmword ptr [rbp+57h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x1800c27b0  lea     rdx, szSubsystemProtocol; "Disallowed"
0x1800c27b7  xor     ecx, ecx; hProv
0x1800c27b9  call    cs:__imp_CertOpenSystemStoreW
0x1800c27bf  mov     [rbp+57h+var_40], rax
0x1800c27c3  xor     r14d, r14d
0x1800c27c6  mov     [rbp+57h+var_38], r14d
0x1800c27ca  test    rax, rax
0x1800c27cd  jnz     short loc_1800C2817
0x1800c27cf  lea     rax, WPP_GLOBAL_Control
0x1800c27d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c27dd  cmp     rcx, rax
0x1800c27e0  jz      short loc_1800C27FC
0x1800c27e2  test    byte ptr [rcx+6Ch], 1
0x1800c27e6  jz      short loc_1800C27FC
0x1800c27e8  lea     edx, [r14+0Bh]
0x1800c27ec  lea     r8, WPP_141b597a36f53d015b025654940084c8_Traceguids
0x1800c27f3  mov     rcx, [rcx+60h]
0x1800c27f7  call    WPP_SF_
0x1800c27fc  lea     rcx, [rbp+57h+pExceptionObject]
0x1800c2800  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x1800c2806  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x1800c280d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800c2811  call    _CxxThrowException_0
0x1800c2817  mov     [rsp+0F0h+pPrevCertContext], r14; pPrevCertContext
0x1800c281c  mov     [rsp+0F0h+pvFindPara], rdi; pvFindPara
0x1800c2821  mov     r9d, 0D0000h; dwFindType
0x1800c2827  xor     r8d, r8d; dwFindFlags
0x1800c282a  mov     edx, 10001h; dwCertEncodingType
0x1800c282f  mov     rcx, rax; hCertStore
0x1800c2832  call    cs:__imp_CertFindCertificateInStore
0x1800c2838  mov     [rbp+57h+var_48], rax
0x1800c283c  test    rax, rax
0x1800c283f  jz      short loc_1800C2894
0x1800c2841  mov     ecx, 8000088Fh; unsigned int
0x1800c2846  call    ?EvReportWithFrequency@@YAXK@Z; EvReportWithFrequency(ulong)
0x1800c284b  lea     rax, WPP_GLOBAL_Control
0x1800c2852  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2859  cmp     rcx, rax
0x1800c285c  jz      short loc_1800C2879
0x1800c285e  test    byte ptr [rcx+6Ch], 1
0x1800c2862  jz      short loc_1800C2879
0x1800c2864  mov     edx, 0Ch
0x1800c2869  lea     r8, WPP_141b597a36f53d015b025654940084c8_Traceguids
0x1800c2870  mov     rcx, [rcx+60h]
0x1800c2874  call    WPP_SF_
0x1800c2879  lea     rcx, [rbp+57h+pExceptionObject]
0x1800c287d  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x1800c2883  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x1800c288a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800c288e  call    _CxxThrowException_0
0x1800c2894  xorps   xmm0, xmm0
0x1800c2897  movups  xmmword ptr [rbp+57h+pChainPara.cbSize], xmm0
0x1800c289b  movups  xmmword ptr [rbp+57h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x1800c289f  mov     [rbp+57h+pChainPara.cbSize], 20h ; ' '
0x1800c28a6  mov     [rbp+57h+pChainContext], r14
0x1800c28aa  mov     ebx, 20000000h
0x1800c28af  mov     [rbp+57h+pExceptionObject], r14d
0x1800c28b3  lea     rax, aSecurity_0; "security"
0x1800c28ba  mov     [rbp+57h+var_A8], rax
0x1800c28be  lea     rax, aSkiprevocation; "SkipRevocationCheck"
0x1800c28c5  mov     [rbp+57h+var_A0], rax
0x1800c28c9  mov     [rbp+57h+var_98], r14d
0x1800c28cd  mov     [rbp+57h+var_90], r14
0x1800c28d1  mov     [rbp+57h+arg_10], r14d
0x1800c28d5  mov     r9d, 4
0x1800c28db  lea     r8, [rbp+57h+arg_10]
0x1800c28df  mov     edx, r9d
0x1800c28e2  lea     rcx, [rbp+57h+pExceptionObject]; struct RegEntry *
0x1800c28e6  call    QueryValueInternal
0x1800c28eb  cmp     [rbp+57h+arg_10], r14d
0x1800c28ef  cmovnz  ebx, r14d
0x1800c28f3  lea     rax, [rbp+57h+pChainContext]
0x1800c28f7  mov     [rsp+0F0h+ppChainContext], rax; ppChainContext
0x1800c28fc  mov     [rsp+0F0h+pvReserved], r14; pvReserved
0x1800c2901  mov     dword ptr [rsp+0F0h+pPrevCertContext], ebx; dwFlags
0x1800c2905  lea     rax, [rbp+57h+pChainPara]
0x1800c2909  mov     [rsp+0F0h+pvFindPara], rax; pChainPara
0x1800c290e  mov     r9, [rdi+20h]; hAdditionalStore
0x1800c2912  xor     r8d, r8d; pTime
0x1800c2915  mov     rdx, rdi; pCertContext
0x1800c2918  lea     ecx, [r8+1]; hChainEngine
0x1800c291c  call    cs:__imp_CertGetCertificateChain
0x1800c2922  test    eax, eax
0x1800c2924  jnz     short loc_1800C2998
0x1800c2926  call    cs:__imp_GetLastError
0x1800c292c  test    eax, eax
0x1800c292e  jle     short loc_1800C2938
0x1800c2930  movzx   eax, ax
0x1800c2933  or      eax, 80070000h
0x1800c2938  mov     edx, eax; int
0x1800c293a  call    ?EvReportWithErrorAndFrequency@@YAXKJ@Z; EvReportWithErrorAndFrequency(ulong,long)
0x1800c293f  lea     rax, WPP_GLOBAL_Control
0x1800c2946  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c294d  cmp     rcx, rax
0x1800c2950  jz      short loc_1800C297D
0x1800c2952  test    byte ptr [rcx+6Ch], 1
0x1800c2956  jz      short loc_1800C297D
0x1800c2958  call    cs:__imp_GetLastError
0x1800c295e  mov     edx, 0Dh
0x1800c2963  mov     r9d, eax
0x1800c2966  lea     r8, WPP_141b597a36f53d015b025654940084c8_Traceguids
0x1800c296d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2974  mov     rcx, [rcx+60h]
0x1800c2978  call    WPP_SF_d
0x1800c297d  lea     rcx, [rbp+57h+pExceptionObject]
0x1800c2981  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x1800c2987  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x1800c298e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800c2992  call    _CxxThrowException_0
0x1800c2998  mov     rdx, [rbp+57h+pChainContext]; pChainContext
0x1800c299c  mov     eax, [rdx+4]
0x1800c299f  test    eax, eax
0x1800c29a1  jz      short loc_1800C2A05
0x1800c29a3  jle     short loc_1800C29AD
0x1800c29a5  movzx   eax, ax
0x1800c29a8  or      eax, 80070000h
0x1800c29ad  mov     edx, eax; int
0x1800c29af  call    ?EvReportWithErrorAndFrequency@@YAXKJ@Z; EvReportWithErrorAndFrequency(ulong,long)
0x1800c29b4  lea     rax, WPP_GLOBAL_Control
0x1800c29bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c29c2  cmp     rcx, rax
0x1800c29c5  jz      short loc_1800C29EA
0x1800c29c7  test    byte ptr [rcx+6Ch], 1
0x1800c29cb  jz      short loc_1800C29EA
0x1800c29cd  mov     edx, 0Eh
0x1800c29d2  mov     r9, [rbp+57h+pChainContext]
0x1800c29d6  mov     r9d, [r9+4]
0x1800c29da  lea     r8, WPP_141b597a36f53d015b025654940084c8_Traceguids
0x1800c29e1  mov     rcx, [rcx+60h]
0x1800c29e5  call    WPP_SF_d
0x1800c29ea  lea     rcx, [rbp+57h+pExceptionObject]
0x1800c29ee  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x1800c29f4  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x1800c29fb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800c29ff  call    _CxxThrowException_0
0x1800c2a05  mov     qword ptr [rbp+57h+var_88+8], r14
0x1800c2a09  mov     r8d, 18h
0x1800c2a0f  mov     dword ptr [rbp+57h+var_88], r8d
0x1800c2a13  mov     dword ptr [rbp+57h+var_88+4], 2
0x1800c2a1a  mov     [rbp+57h+var_78], rsi
0x1800c2a1e  mov     qword ptr [rbp+57h+pPolicyPara.cbSize], 10h
0x1800c2a26  lea     ebx, [r8-8]
0x1800c2a2a  lea     rax, [rbp+57h+var_88]
0x1800c2a2e  mov     [rbp+57h+pPolicyPara.pvExtraPolicyPara], rax
0x1800c2a32  xorps   xmm0, xmm0
0x1800c2a35  xor     eax, eax
0x1800c2a37  movups  xmmword ptr [rbp+57h+pPolicyStatus.cbSize], xmm0
0x1800c2a3b  mov     [rbp+57h+pPolicyStatus.pvExtraPolicyStatus], rax
0x1800c2a3f  mov     [rbp+57h+pPolicyStatus.cbSize], r8d
0x1800c2a43  lea     r9, [rbp+57h+pPolicyStatus]; pPolicyStatus
0x1800c2a47  lea     r8, [rbp+57h+pPolicyPara]; pPolicyPara
0x1800c2a4b  lea     ecx, [rbx-0Ch]; pszPolicyOID
0x1800c2a4e  call    cs:__imp_CertVerifyCertificateChainPolicy
0x1800c2a54  test    eax, eax
0x1800c2a56  jnz     short loc_1800C2ACA
0x1800c2a58  call    cs:__imp_GetLastError
0x1800c2a5e  test    eax, eax
0x1800c2a60  jle     short loc_1800C2A6A
0x1800c2a62  movzx   eax, ax
0x1800c2a65  or      eax, 80070000h
0x1800c2a6a  mov     edx, eax; int
0x1800c2a6c  call    ?EvReportWithErrorAndFrequency@@YAXKJ@Z; EvReportWithErrorAndFrequency(ulong,long)
0x1800c2a71  lea     rax, WPP_GLOBAL_Control
0x1800c2a78  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2a7f  cmp     rcx, rax
0x1800c2a82  jz      short loc_1800C2AAF
0x1800c2a84  test    byte ptr [rcx+6Ch], 1
0x1800c2a88  jz      short loc_1800C2AAF
0x1800c2a8a  call    cs:__imp_GetLastError
0x1800c2a90  mov     edx, 0Fh
0x1800c2a95  mov     r9d, eax
0x1800c2a98  lea     r8, WPP_141b597a36f53d015b025654940084c8_Traceguids
0x1800c2a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2aa6  mov     rcx, [rcx+60h]
0x1800c2aaa  call    WPP_SF_d
0x1800c2aaf  lea     rcx, [rbp+57h+pExceptionObject]
0x1800c2ab3  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x1800c2ab9  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x1800c2ac0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800c2ac4  call    _CxxThrowException_0
0x1800c2aca  mov     edx, [rbp+57h+pPolicyStatus.dwError]
0x1800c2acd  test    edx, edx
0x1800c2acf  jz      short loc_1800C2B41
0x1800c2ad1  cmp     edx, 800B010Fh
0x1800c2ad7  jnz     short loc_1800C2AE5
0x1800c2ad9  mov     ecx, 80000891h; unsigned int
0x1800c2ade  call    ?EvReportWithFrequency@@YAXK@Z; EvReportWithFrequency(ulong)
0x1800c2ae3  jmp     short loc_1800C2AF7
0x1800c2ae5  test    edx, edx
0x1800c2ae7  jle     short loc_1800C2AF2
0x1800c2ae9  movzx   edx, dx
0x1800c2aec  or      edx, 80070000h; int
0x1800c2af2  call    ?EvReportWithErrorAndFrequency@@YAXKJ@Z; EvReportWithErrorAndFrequency(ulong,long)
0x1800c2af7  lea     rax, WPP_GLOBAL_Control
0x1800c2afe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2b05  cmp     rcx, rax
0x1800c2b08  jz      short loc_1800C2B26
0x1800c2b0a  test    byte ptr [rcx+6Ch], 1
0x1800c2b0e  jz      short loc_1800C2B26
0x1800c2b10  mov     edx, ebx
0x1800c2b12  mov     r9d, [rbp+57h+pPolicyStatus.dwError]
0x1800c2b16  lea     r8, WPP_141b597a36f53d015b025654940084c8_Traceguids
0x1800c2b1d  mov     rcx, [rcx+60h]
0x1800c2b21  call    WPP_SF_d
0x1800c2b26  lea     rcx, [rbp+57h+pExceptionObject]
0x1800c2b2a  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x1800c2b30  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x1800c2b37  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800c2b3b  call    _CxxThrowException_0
0x1800c2b41  lea     rcx, [rbp+57h+pChainContext]; this
0x1800c2b45  call    ??1CCertificateChain@@QEAA@XZ; CCertificateChain::~CCertificateChain(void)
0x1800c2b4a  nop
0x1800c2b4b  lea     rcx, [rbp+57h+var_48]; this
0x1800c2b4f  call    ??1CCertificateContext@@QEAA@XZ; CCertificateContext::~CCertificateContext(void)
0x1800c2b54  nop
0x1800c2b55  lea     rcx, [rbp+57h+var_40]; this
0x1800c2b59  call    ??1CCertOpenStore@@QEAA@XZ; CCertOpenStore::~CCertOpenStore(void)
0x1800c2b5e  lea     r11, [rsp+0F0h+var_10]
0x1800c2b66  mov     rbx, [r11+20h]
0x1800c2b6a  mov     rsi, [r11+28h]
0x1800c2b6e  mov     rsp, r11
0x1800c2b71  pop     r14
0x1800c2b73  pop     rdi
0x1800c2b74  pop     rbp
0x1800c2b75  retn
```
