# SerialChainEngineIsDisallowedCertificate(_CRYPTOAPI_BLOB *)

- ea: `0x1800a1e50`
- end: `0x1800a2005`
- name: `?SerialChainEngineIsDisallowedCertificate@@YAHPEAU_CRYPTOAPI_BLOB@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(PCRYPT_DATA_BLOB pSubjectIdentifier)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180018f10`

## callees

- `0x1800161d0`
- `0x18001663c`
- `0x18001ce90`
- `0x18001dd40`
- `0x18002c860`
- `0x1800353c8`
- `0x180035404`
- `0x180037114`
- `0x1800450c0`
- `0x1800a1e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a1fcd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a1fcd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a1fa2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a1fa2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a1f01`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a1f01`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a1ea6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a1ea6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a1e99`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a1e99`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800a1ec1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800a1ee8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800a1ec1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800a1ee8`

## pseudocode

```c
__int64 __fastcall SerialChainEngineIsDisallowedCertificate(PCRYPT_DATA_BLOB pSubjectIdentifier)
{
  unsigned int SubjectInSortedCTL; // r15d
  __int64 Engine; // rbx
  const CTL_CONTEXT *v5; // rdi
  struct _FILETIME *v6; // r14
  HKEY updated; // rax
  HKEY v8; // r14
  const CERT_CONTEXT *v9; // rcx
  struct _CERT_CREATE_CONTEXT_PARA pCreatePara; // [rsp+38h] [rbp-28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp+50h] BYREF
  FILETIME FileTime1; // [rsp+B8h] [rbp+58h] BYREF

  SubjectInSortedCTL = 0;
  SystemTimeAsFileTime = 0;
  Engine = SerialChainGetEngine();
  if ( !Engine )
    goto LABEL_2;
  v5 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  AcquireSRWLockShared((PSRWLOCK)(Engine + 32));
  if ( *(_QWORD *)(Engine + 72) )
  {
    v6 = (struct _FILETIME *)(Engine + 80);
    FileTime1 = 0;
    if ( CompareFileTime((const FILETIME *)(Engine + 80), &SystemTimeAsFileTime) > 0 )
      *v6 = SystemTimeAsFileTime;
    FileTime1 = (FILETIME)(*(_QWORD *)v6 + 10000000LL * *(unsigned int *)(Engine + 96));
    if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) > 0 )
      v5 = CertDuplicateCTLContext(*(PCCTL_CONTEXT *)(Engine + 72));
  }
  ReleaseSRWLockShared((PSRWLOCK)(Engine + 32));
  if ( v5 )
  {
LABEL_16:
    SubjectInSortedCTL = CertFindSubjectInSortedCTL(pSubjectIdentifier, v5, 0, 0, 0);
    CertFreeCertificateContext((PCCERT_CONTEXT)v5);
    goto LABEL_2;
  }
  memset(&pCreatePara.pvFree, 0, 24);
  *(&pCreatePara.cbSize + 1) = 0;
  updated = OpenAutoUpdateKey(HKEY_LOCAL_MACHINE);
  v8 = updated;
  if ( updated && (unsigned int)I_CertReadBINARYValueFromRegistry(updated, L"DisallowedCertEncodedCtl") )
  {
    pCreatePara.pfnFree = (PFN_CRYPT_FREE)PkiDefaultCryptFree;
    pCreatePara.cbSize = 40;
    v5 = (const CTL_CONTEXT *)CertCreateContext(3u, 0x10001u, 0, 0, 3u, &pCreatePara);
  }
  CloseRegistryKey(v8);
  if ( v5 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)(Engine + 32));
    v9 = *(const CERT_CONTEXT **)(Engine + 72);
    if ( v9 )
      CertFreeCertificateContext(v9);
    *(_QWORD *)(Engine + 72) = CertDuplicateCTLContext(v5);
    *(struct _FILETIME *)(Engine + 80) = SystemTimeAsFileTime;
    ReleaseSRWLockExclusive((PSRWLOCK)(Engine + 32));
    goto LABEL_16;
  }
LABEL_2:
  _SerialChainReleaseEngine((struct _CERT_SERIAL_CHAIN_ENGINE *)Engine);
  return SubjectInSortedCTL;
}

```

## disassembly

```asm
0x1800a1e50  push    rbp
0x1800a1e52  push    rbx
0x1800a1e53  push    rsi
0x1800a1e54  push    rdi
0x1800a1e55  push    r12
0x1800a1e57  push    r14
0x1800a1e59  push    r15
0x1800a1e5b  mov     rbp, rsp
0x1800a1e5e  sub     rsp, 60h
0x1800a1e62  xor     r15d, r15d
0x1800a1e65  mov     r12, rcx
0x1800a1e68  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r15
0x1800a1e6c  call    _SerialChainGetEngine
0x1800a1e71  mov     rbx, rax
0x1800a1e74  test    rax, rax
0x1800a1e77  jnz     short loc_1800A1E93
0x1800a1e79  mov     rcx, rbx; struct _CERT_SERIAL_CHAIN_ENGINE *
0x1800a1e7c  call    ?_SerialChainReleaseEngine@@YAXPEAU_CERT_SERIAL_CHAIN_ENGINE@@@Z; _SerialChainReleaseEngine(_CERT_SERIAL_CHAIN_ENGINE *)
0x1800a1e81  mov     eax, r15d
0x1800a1e84  add     rsp, 60h
0x1800a1e88  pop     r15
0x1800a1e8a  pop     r14
0x1800a1e8c  pop     r12
0x1800a1e8e  pop     rdi
0x1800a1e8f  pop     rsi
0x1800a1e90  pop     rbx
0x1800a1e91  pop     rbp
0x1800a1e92  retn
0x1800a1e93  xor     edi, edi
0x1800a1e95  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a1e99  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a1e9f  lea     rsi, [rbx+20h]
0x1800a1ea3  mov     rcx, rsi; SRWLock
0x1800a1ea6  call    cs:__imp_AcquireSRWLockShared
0x1800a1eac  cmp     [rbx+48h], rdi
0x1800a1eb0  jz      short loc_1800A1EFE
0x1800a1eb2  lea     r14, [rbx+50h]
0x1800a1eb6  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rdi
0x1800a1eba  mov     rcx, r14; lpFileTime1
0x1800a1ebd  lea     rdx, [rbp+SystemTimeAsFileTime]; lpFileTime2
0x1800a1ec1  call    cs:__imp_CompareFileTime
0x1800a1ec7  test    eax, eax
0x1800a1ec9  jg      loc_1800A1FF9
0x1800a1ecf  mov     eax, [rbx+60h]
0x1800a1ed2  lea     rdx, [rbp+SystemTimeAsFileTime]; lpFileTime2
0x1800a1ed6  imul    rcx, rax, 989680h
0x1800a1edd  add     rcx, [r14]
0x1800a1ee0  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rcx
0x1800a1ee4  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800a1ee8  call    cs:__imp_CompareFileTime
0x1800a1eee  test    eax, eax
0x1800a1ef0  jle     short loc_1800A1EFE
0x1800a1ef2  mov     rcx, [rbx+48h]; pCtlContext
0x1800a1ef6  call    CertDuplicateCTLContext
0x1800a1efb  mov     rdi, rax
0x1800a1efe  mov     rcx, rsi; SRWLock
0x1800a1f01  call    cs:__imp_ReleaseSRWLockShared
0x1800a1f07  test    rdi, rdi
0x1800a1f0a  jnz     loc_1800A1FD3
0x1800a1f10  xorps   xmm0, xmm0
0x1800a1f13  mov     [rbp+pbEncoded], rdi
0x1800a1f17  mov     rcx, 0FFFFFFFF80000002h
0x1800a1f1e  mov     [rbp+cbEncoded], edi
0x1800a1f21  movdqu  xmmword ptr [rbp+var_28.pvFree], xmm0
0x1800a1f26  mov     dword ptr [rbp+var_28+4], edi
0x1800a1f29  mov     [rbp+var_28.pvSort], rdi
0x1800a1f2d  call    _OpenAutoUpdateKey
0x1800a1f32  mov     r14, rax
0x1800a1f35  test    rax, rax
0x1800a1f38  jz      short loc_1800A1F8E
0x1800a1f3a  lea     r9, [rbp+cbEncoded]
0x1800a1f3e  mov     rcx, rax; hKey
0x1800a1f41  lea     r8, [rbp+pbEncoded]
0x1800a1f45  lea     rdx, aDisallowedcert_0; "DisallowedCertEncodedCtl"
0x1800a1f4c  call    I_CertReadBINARYValueFromRegistry
0x1800a1f51  test    eax, eax
0x1800a1f53  jz      short loc_1800A1F8E
0x1800a1f55  mov     r9d, [rbp+cbEncoded]; cbEncoded
0x1800a1f59  lea     rax, PkiDefaultCryptFree
0x1800a1f60  mov     r8, [rbp+pbEncoded]; pbEncoded
0x1800a1f64  mov     ecx, 3; dwContextType
0x1800a1f69  mov     [rbp+var_28.pfnFree], rax
0x1800a1f6d  mov     edx, 10001h; dwEncodingType
0x1800a1f72  lea     rax, [rbp+var_28]
0x1800a1f76  mov     [rbp+var_28.cbSize], 28h ; '('
0x1800a1f7d  mov     [rsp+60h+pCreatePara], rax; pCreatePara
0x1800a1f82  mov     [rsp+60h+dwFlags], ecx; dwFlags
0x1800a1f86  call    CertCreateContext
0x1800a1f8b  mov     rdi, rax
0x1800a1f8e  mov     rcx, r14; hKey
0x1800a1f91  call    _CloseRegistryKey
0x1800a1f96  test    rdi, rdi
0x1800a1f99  jz      loc_1800A1E79
0x1800a1f9f  mov     rcx, rsi; SRWLock
0x1800a1fa2  call    cs:__imp_AcquireSRWLockExclusive
0x1800a1fa8  mov     rcx, [rbx+48h]; pCertContext
0x1800a1fac  test    rcx, rcx
0x1800a1faf  jz      short loc_1800A1FB6
0x1800a1fb1  call    CertFreeCertificateContext
0x1800a1fb6  mov     rcx, rdi; pCtlContext
0x1800a1fb9  call    CertDuplicateCTLContext
0x1800a1fbe  mov     [rbx+48h], rax
0x1800a1fc2  mov     rcx, rsi; SRWLock
0x1800a1fc5  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800a1fc9  mov     [rbx+50h], rax
0x1800a1fcd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a1fd3  xor     r9d, r9d; pvReserved
0x1800a1fd6  mov     qword ptr [rsp+60h+dwFlags], r15; pEncodedAttributes
0x1800a1fdb  xor     r8d, r8d; dwFlags
0x1800a1fde  mov     rdx, rdi; pCtlContext
0x1800a1fe1  mov     rcx, r12; pSubjectIdentifier
0x1800a1fe4  call    CertFindSubjectInSortedCTL
0x1800a1fe9  mov     r15d, eax
0x1800a1fec  mov     rcx, rdi; pCertContext
0x1800a1fef  call    CertFreeCertificateContext
0x1800a1ff4  jmp     loc_1800A1E79
0x1800a1ff9  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800a1ffd  mov     [r14], rax
0x1800a2000  jmp     loc_1800A1ECF
```
