# FreeGlobals

- ea: `0x180013794`
- end: `0x180013862`
- name: `FreeGlobals`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014e08`

## callees

- `0x180013794`
- `0x1800210f4`

## import_xrefs

- `msvcrt!free` at `0x18001383c`
- `msvcrt!free` at `0x180013855`
- `msvcrt!free` at `0x18001383c`
- `msvcrt!free` at `0x180013855`
- `ADVAPI32!CryptReleaseContext` at `0x1800137a8`
- `ADVAPI32!CryptReleaseContext` at `0x1800137c7`
- `ADVAPI32!CryptReleaseContext` at `0x1800137a8`
- `ADVAPI32!CryptReleaseContext` at `0x1800137c7`
- `KERNEL32!TlsFree` at `0x1800137e5`
- `KERNEL32!TlsFree` at `0x1800137f5`
- `KERNEL32!TlsFree` at `0x18001381e`
- `KERNEL32!TlsFree` at `0x1800137e5`
- `KERNEL32!TlsFree` at `0x1800137f5`
- `KERNEL32!TlsFree` at `0x18001381e`
- `mqsec!mqrpcUnbindQMService` at `0x18001380e`
- `mqsec!mqrpcUnbindQMService` at `0x18001380e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void FreeGlobals()
{
  CMSMQTrace *v0; // rbx

  if ( RTSecurityContextBase::s_hInternalCertCryptoProvider )
  {
    CryptReleaseContext(RTSecurityContextBase::s_hInternalCertCryptoProvider, 0);
    RTSecurityContextBase::s_hInternalCertCryptoProvider = 0;
  }
  if ( RTSecurityContextBase::s_hInternalCertLocalSystemCryptoProvider )
  {
    CryptReleaseContext(RTSecurityContextBase::s_hInternalCertLocalSystemCryptoProvider, 0);
    RTSecurityContextBase::s_hInternalCertLocalSystemCryptoProvider = 0;
  }
  if ( g_hBindIndex != -1 )
    TlsFree(g_hBindIndex);
  if ( g_dwThreadEventIndex != -1 )
    TlsFree(g_dwThreadEventIndex);
  if ( g_pszStringBinding )
    mqrpcUnbindQMService(0, &g_pszStringBinding);
  if ( g_hThreadIndex != -1 )
    TlsFree(g_hThreadIndex);
  v0 = g_pMSMQErrorLoggingTrace;
  if ( g_pMSMQErrorLoggingTrace )
  {
    CMSMQTrace::~CMSMQTrace(g_pMSMQErrorLoggingTrace);
    free(v0);
    g_pMSMQErrorLoggingTrace = 0;
  }
  free(g_lpwcsComputerName);
}

```

## disassembly

```asm
0x180013794  push    rbx
0x180013796  sub     rsp, 20h
0x18001379a  mov     rcx, cs:?s_hInternalCertCryptoProvider@RTSecurityContextBase@@0_KA; hProv
0x1800137a1  test    rcx, rcx
0x1800137a4  jz      short loc_1800137B9
0x1800137a6  xor     edx, edx; dwFlags
0x1800137a8  call    cs:__imp_CryptReleaseContext
0x1800137ae  mov     cs:?s_hInternalCertCryptoProvider@RTSecurityContextBase@@0_KA, 0; unsigned __int64 RTSecurityContextBase::s_hInternalCertCryptoProvider
0x1800137b9  mov     rcx, cs:?s_hInternalCertLocalSystemCryptoProvider@RTSecurityContextBase@@0_KA; hProv
0x1800137c0  test    rcx, rcx
0x1800137c3  jz      short loc_1800137D8
0x1800137c5  xor     edx, edx; dwFlags
0x1800137c7  call    cs:__imp_CryptReleaseContext
0x1800137cd  mov     cs:?s_hInternalCertLocalSystemCryptoProvider@RTSecurityContextBase@@0_KA, 0; unsigned __int64 RTSecurityContextBase::s_hInternalCertLocalSystemCryptoProvider
0x1800137d8  mov     ecx, cs:?g_hBindIndex@@3KA; dwTlsIndex
0x1800137de  or      ebx, 0FFFFFFFFh
0x1800137e1  cmp     ecx, ebx
0x1800137e3  jz      short loc_1800137EB
0x1800137e5  call    cs:__imp_TlsFree
0x1800137eb  mov     ecx, cs:?g_dwThreadEventIndex@@3KA; dwTlsIndex
0x1800137f1  cmp     ecx, ebx
0x1800137f3  jz      short loc_1800137FB
0x1800137f5  call    cs:__imp_TlsFree
0x1800137fb  cmp     cs:?g_pszStringBinding@@3PEA_WEA, 0; wchar_t * g_pszStringBinding
0x180013803  jz      short loc_180013814
0x180013805  lea     rdx, ?g_pszStringBinding@@3PEA_WEA; wchar_t * g_pszStringBinding
0x18001380c  xor     ecx, ecx
0x18001380e  call    cs:__imp_?mqrpcUnbindQMService@@YAJPEAPEAXPEAPEA_W@Z; mqrpcUnbindQMService(void * *,wchar_t * *)
0x180013814  mov     ecx, cs:?g_hThreadIndex@@3KA; dwTlsIndex
0x18001381a  cmp     ecx, ebx
0x18001381c  jz      short loc_180013824
0x18001381e  call    cs:__imp_TlsFree
0x180013824  mov     rbx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001382b  test    rbx, rbx
0x18001382e  jz      short loc_18001384E
0x180013830  mov     rcx, rbx; this
0x180013833  call    ??1CMSMQTrace@@QEAA@XZ; CMSMQTrace::~CMSMQTrace(void)
0x180013838  nop
0x180013839  mov     rcx, rbx; Block
0x18001383c  call    cs:__imp_free
0x180013842  nop
0x180013843  mov     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001384e  mov     rcx, cs:?g_lpwcsComputerName@@3PEA_WEA; Block
0x180013855  call    cs:__imp_free
0x18001385b  nop
0x18001385c  add     rsp, 20h
0x180013860  pop     rbx
0x180013861  retn
```
