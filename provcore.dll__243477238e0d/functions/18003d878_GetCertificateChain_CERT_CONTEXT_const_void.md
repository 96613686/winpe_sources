# GetCertificateChain(_CERT_CONTEXT const *,void *)

- ea: `0x18003d878`
- end: `0x18003dab2`
- name: `?GetCertificateChain@@YA?AV?$shared_ptr@$$CBU_CERT_CHAIN_CONTEXT@@@std@@PEBU_CERT_CONTEXT@@PEAX@Z`
- size: `570`
- prototype: `std::shared_ptr<_CERT_CHAIN_CONTEXT const > *__fastcall(std::shared_ptr<_CERT_CHAIN_CONTEXT const > *result, const _CERT_CONTEXT *pCert, void *hCertStore)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18003dffc`
- `0x18003e2ec`

## callees

- `0x180002790`
- `0x1800032dc`
- `0x1800032f4`
- `0x180012748`
- `0x180012770`
- `0x180012bc8`
- `0x180013bdc`
- `0x18003ced8`
- `0x18003d878`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d927`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003da13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d927`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003da13`
- `CRYPT32!CertFreeCertificateChain` at `0x18003da76`
- `CRYPT32!CertGetCertificateChain` at `0x18003da09`
- `CRYPT32!CertGetCertificateChain` at `0x18003da09`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18003d988`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18003d91d`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18003d91d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
std::shared_ptr<_CERT_CHAIN_CONTEXT const > *__fastcall GetCertificateChain(
        std::shared_ptr<_CERT_CHAIN_CONTEXT const > *result,
        const _CERT_CONTEXT *pCert,
        void *hCertStore)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  void *v7; // r10
  signed int v8; // eax
  unsigned int v9; // ebx
  HrException pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  HrException v12; // [rsp+68h] [rbp-98h] BYREF
  void *hChainEngine; // [rsp+88h] [rbp-78h] BYREF
  const _CERT_CHAIN_CONTEXT *pCertChain; // [rsp+90h] [rbp-70h] BYREF
  void *v15; // [rsp+98h] [rbp-68h] BYREF
  _CERT_CHAIN_PARA ChainPara; // [rsp+A0h] [rbp-60h] BYREF
  _CERT_CHAIN_ENGINE_CONFIG ChainConfig; // [rsp+C0h] [rbp-40h] BYREF

  v15 = hCertStore;
  memset_0(&ChainConfig, 0, sizeof(ChainConfig));
  ChainConfig.cbSize = 88;
  memset(&ChainConfig.hRestrictedRoot, 0, 24);
  ChainConfig.cAdditionalStore = 1;
  ChainConfig.rghAdditionalStore = &v15;
  *(_QWORD *)&ChainConfig.dwFlags = 1;
  *(_QWORD *)&ChainConfig.MaximumCachedCertificates = 0;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xFu, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids);
  }
  hChainEngine = 0;
  if ( !CertCreateCertificateChainEngine(&ChainConfig, &hChainEngine) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x10u, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids, v6);
    }
    HrException::HrException(&pExceptionObject, v6);
    throw &pExceptionObject;
  }
  v7 = hChainEngine;
  LOBYTE(pExceptionObject.__vftable) = 0;
  pExceptionObject._Data._What = (const char *)CertFreeCertificateChainEngine;
  *(_QWORD *)&pExceptionObject._Data._DoFree = hChainEngine;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x11u, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids);
    v7 = hChainEngine;
  }
  *(_QWORD *)&ChainPara.cbSize = 32;
  memset(&ChainPara.RequestedUsage, 0, sizeof(ChainPara.RequestedUsage));
  pCertChain = 0;
  if ( !CertGetCertificateChain(v7, pCert, 0, 0, &ChainPara, 0, 0, &pCertChain) )
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x12u, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids, v9);
    }
    HrException::HrException(&v12, v9);
    throw &v12;
  }
  *result = 0;
  std::shared_ptr<_CERT_CHAIN_CONTEXT const>::shared_ptr<_CERT_CHAIN_CONTEXT const>(
    result,
    pCertChain,
    (void (__fastcall *)(const _CERT_CHAIN_CONTEXT *))CertFreeCertificateChain);
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>((ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> *)&pExceptionObject);
  return result;
}

```

## disassembly

```asm
0x18003d878  push    rbp
0x18003d87a  push    rbx
0x18003d87b  push    rdi
0x18003d87c  push    r12
0x18003d87e  push    r14
0x18003d880  lea     rbp, [rsp-30h]
0x18003d885  sub     rsp, 130h
0x18003d88c  mov     rax, cs:__security_cookie
0x18003d893  xor     rax, rsp
0x18003d896  mov     [rbp+50h+var_30], rax
0x18003d89a  mov     rdi, pCert
0x18003d89d  mov     rbx, rcx
0x18003d8a0  mov     [rbp+50h+var_B8], rcx
0x18003d8a4  mov     [rbp+50h+var_B8], hCertStore
0x18003d8a8  xor     r14d, r14d
0x18003d8ab  xor     edx, edx; Val
0x18003d8ad  lea     r8d, [r14+58h]; Size
0x18003d8b1  lea     rcx, [rbp+50h+ChainConfig]; void *
0x18003d8b5  call    memset_0
0x18003d8ba  mov     [rbp+50h+ChainConfig.cbSize], 58h ; 'X'
0x18003d8c1  mov     [rbp+50h+ChainConfig.hRestrictedRoot], r14
0x18003d8c5  xorps   xmm0, xmm0
0x18003d8c8  movdqa  xmmword ptr [rbp+50h+ChainConfig.hRestrictedTrust], xmm0
0x18003d8cd  lea     ecx, [r14+1]
0x18003d8d1  mov     [rbp+50h+ChainConfig.cAdditionalStore], ecx
0x18003d8d4  lea     rax, [rbp+50h+var_B8]
0x18003d8d8  mov     [rbp+50h+ChainConfig.rghAdditionalStore], rax
0x18003d8dc  mov     qword ptr [rbp+50h+ChainConfig.dwFlags], rcx
0x18003d8e0  mov     qword ptr [rbp+50h+ChainConfig.MaximumCachedCertificates], r14
0x18003d8e4  lea     r12, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003d8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d8f2  cmp     rcx, r12
0x18003d8f5  jz      short loc_18003D911
0x18003d8f7  test    byte ptr [rcx+1Ch], 10h
0x18003d8fb  jz      short loc_18003D911
0x18003d8fd  lea     edx, [r14+0Fh]; id
0x18003d901  lea     hCertStore, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids; TraceGuid
0x18003d908  mov     rcx, [rcx+10h]; Logger
0x18003d90c  call    WPP_SF_
0x18003d911  mov     [rbp+50h+hChainEngine], r14
0x18003d915  lea     pCert, [rbp+50h+hChainEngine]; phChainEngine
0x18003d919  lea     rcx, [rbp+50h+ChainConfig]; pConfig
0x18003d91d  call    cs:__imp_CertCreateCertificateChainEngine
0x18003d923  test    eax, eax
0x18003d925  jnz     short loc_18003D984
0x18003d927  call    cs:__imp_GetLastError
0x18003d92d  mov     ebx, eax
0x18003d92f  test    eax, eax
0x18003d931  jle     short loc_18003D93C
0x18003d933  movzx   ebx, ax
0x18003d936  or      ebx, 80070000h
0x18003d93c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003d943  cmp     rcx, r12
0x18003d946  jz      short loc_18003D966
0x18003d948  test    byte ptr [rcx+1Ch], 10h
0x18003d94c  jz      short loc_18003D966
0x18003d94e  mov     edx, 10h; id
0x18003d953  mov     r9d, ebx; _a1
0x18003d956  lea     hCertStore, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids; TraceGuid
0x18003d95d  mov     rcx, [rcx+10h]; Logger
0x18003d961  call    WPP_SF_d
0x18003d966  mov     edx, ebx; ErrorCode
0x18003d968  lea     rcx, [rsp+150h+pExceptionObject]; this
0x18003d96d  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x18003d972  lea     pCert, _TI2?AVHrException@@; pThrowInfo
0x18003d979  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x18003d97e  call    _CxxThrowException_0
0x18003d984  mov     r10, [rbp+50h+hChainEngine]
0x18003d988  mov     rax, cs:__imp_CertFreeCertificateChainEngine
0x18003d98f  mov     byte ptr [rsp+150h+pExceptionObject.__vftable], r14b
0x18003d994  mov     [rsp+150h+pExceptionObject._Data._What], rax
0x18003d999  mov     qword ptr [rsp+150h+pExceptionObject._Data._DoFree], r10
0x18003d99e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003d9a5  cmp     rcx, r12
0x18003d9a8  jz      short loc_18003D9C9
0x18003d9aa  test    byte ptr [rcx+1Ch], 10h
0x18003d9ae  jz      short loc_18003D9C9
0x18003d9b0  mov     edx, 11h; id
0x18003d9b5  lea     hCertStore, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids; TraceGuid
0x18003d9bc  mov     rcx, [rcx+10h]; Logger
0x18003d9c0  call    WPP_SF_
0x18003d9c5  mov     r10, [rbp+50h+hChainEngine]
0x18003d9c9  mov     qword ptr [rbp+50h+ChainPara.cbSize], 20h ; ' '
0x18003d9d1  mov     qword ptr [rbp+50h+ChainPara.RequestedUsage.dwType], r14
0x18003d9d5  mov     qword ptr [rbp+50h+ChainPara.RequestedUsage.Usage.cUsageIdentifier], r14
0x18003d9d9  mov     [rbp+50h+ChainPara.RequestedUsage.Usage.rgpszUsageIdentifier], r14
0x18003d9dd  mov     [rbp+50h+pCertChain], r14
0x18003d9e1  lea     rax, [rbp+50h+pCertChain]
0x18003d9e5  mov     [rsp+150h+ppChainContext], rax; ppChainContext
0x18003d9ea  mov     [rsp+150h+pvReserved], r14; pvReserved
0x18003d9ef  mov     [rsp+150h+dwFlags], r14d; dwFlags
0x18003d9f4  lea     rax, [rbp+50h+ChainPara]
0x18003d9f8  mov     [rsp+150h+pChainPara], rax; pChainPara
0x18003d9fd  xor     r9d, r9d; hAdditionalStore
0x18003da00  xor     r8d, r8d; pTime
0x18003da03  mov     pCert, rdi; pCertContext
0x18003da06  mov     rcx, r10; hChainEngine
0x18003da09  call    cs:__imp_CertGetCertificateChain
0x18003da0f  test    eax, eax
0x18003da11  jnz     short loc_18003DA70
0x18003da13  call    cs:__imp_GetLastError
0x18003da19  mov     ebx, eax
0x18003da1b  test    eax, eax
0x18003da1d  jle     short loc_18003DA28
0x18003da1f  movzx   ebx, ax
0x18003da22  or      ebx, 80070000h
0x18003da28  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003da2f  cmp     rcx, r12
0x18003da32  jz      short loc_18003DA52
0x18003da34  test    byte ptr [rcx+1Ch], 10h
0x18003da38  jz      short loc_18003DA52
0x18003da3a  mov     edx, 12h; id
0x18003da3f  mov     r9d, ebx; _a1
0x18003da42  lea     hCertStore, WPP_a7555a15cfb1330f6bfbdf6c75b610f5_Traceguids; TraceGuid
0x18003da49  mov     rcx, [rcx+10h]; Logger
0x18003da4d  call    WPP_SF_d
0x18003da52  mov     edx, ebx; ErrorCode
0x18003da54  lea     rcx, [rsp+150h+var_E8]; this
0x18003da59  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x18003da5e  lea     pCert, _TI2?AVHrException@@; pThrowInfo
0x18003da65  lea     rcx, [rsp+150h+var_E8]; pExceptionObject
0x18003da6a  call    _CxxThrowException_0
0x18003da70  xorps   xmm0, xmm0
0x18003da73  movups  xmmword ptr [rbx], xmm0
0x18003da76  mov     hCertStore, cs:__imp_CertFreeCertificateChain; _Dt
0x18003da7d  mov     pCert, [rbp+50h+pCertChain]; _Px
0x18003da81  mov     rcx, rbx; this
0x18003da84  call    ??$?0$$CBU_CERT_CHAIN_CONTEXT@@P6AXPEBU0@@Z$0A@@?$shared_ptr@$$CBU_CERT_CHAIN_CONTEXT@@@std@@QEAA@PEBU_CERT_CHAIN_CONTEXT@@P6AX0@Z@Z; std::shared_ptr<_CERT_CHAIN_CONTEXT const>::shared_ptr<_CERT_CHAIN_CONTEXT const>(_CERT_CHAIN_CONTEXT const *,void (*)(_CERT_CHAIN_CONTEXT const *))
0x18003da89  nop
0x18003da8a  lea     rcx, [rsp+150h+pExceptionObject]; j
0x18003da8f  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x18003da94  mov     rax, rbx
0x18003da97  mov     rcx, [rbp+50h+var_30]
0x18003da9b  xor     rcx, rsp; StackCookie
0x18003da9e  call    __security_check_cookie
0x18003daa3  add     rsp, 130h
0x18003daaa  pop     r14
0x18003daac  pop     r12
0x18003daae  pop     rdi
0x18003daaf  pop     rbx
0x18003dab0  pop     rbp
0x18003dab1  retn
```
