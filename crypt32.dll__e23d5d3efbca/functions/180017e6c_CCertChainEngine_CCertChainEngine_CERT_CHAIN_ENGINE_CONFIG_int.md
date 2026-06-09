# CCertChainEngine::CCertChainEngine(_CERT_CHAIN_ENGINE_CONFIG *,int &)

- ea: `0x180017e6c`
- end: `0x180018741`
- name: `??0CCertChainEngine@@QEAA@PEAU_CERT_CHAIN_ENGINE_CONFIG@@AEAH@Z`
- size: `2261`
- prototype: `CCertChainEngine *__fastcall(CCertChainEngine *__hidden this, struct _CERT_CHAIN_ENGINE_CONFIG *, int *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180054a4c`

## callees

- `0x180017e6c`
- `0x180018750`
- `0x1800189b0`
- `0x180018cc4`
- `0x180019dfc`
- `0x18001a018`
- `0x18001a0d0`
- `0x18001a570`
- `0x18001bb3c`
- `0x180036dfc`
- `0x18003ad34`
- `0x1800466a0`
- `0x180047f10`
- `0x1800557b0`
- `0x180057a8c`
- `0x180058084`
- `0x18005d484`
- `0x18005e720`
- `0x1800614e0`
- `0x180088810`
- `0x18009c1b8`
- `0x1800f26a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800185c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800185c2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001832d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001832d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180018008`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180018008`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180018357`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180018357`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018655`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018655`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017fc9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017fc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018721`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018721`

## string_xrefs

- `0x180017f85`: `Software\Microsoft\Cryptography\OID\EncodingType 0\CertDllCreateCertificateChainEngine\Config`
- `0x18001862b`: `Software\Microsoft\Cryptography\OID\EncodingType 0\CertDllCreateCertificateChainEngine\Config`

## pseudocode

```c
CCertChainEngine *__fastcall CCertChainEngine::CCertChainEngine(
        CCertChainEngine *this,
        struct _CERT_CHAIN_ENGINE_CONFIG *a2,
        int *a3)
{
  unsigned int v3; // ebp
  void **v4; // r13
  HCERTSTORE v8; // r12
  int IsAuthRootAutoUpdateDisabled; // eax
  int IsDisallowedCertAutoUpdateEnabled; // eax
  DWORD dwUrlRetrievalTimeout; // eax
  DWORD *v12; // r15
  int v13; // eax
  HKEY *v14; // r14
  LSTATUS v15; // eax
  int v16; // r9d
  DWORD v17; // r9d
  HCERTSTORE v18; // rax
  HCERTSTORE v19; // rax
  HCERTSTORE v20; // rax
  HCERTSTORE v21; // rax
  HCERTSTORE v22; // rax
  HCERTSTORE hRestrictedRoot; // rdx
  void *v24; // rcx
  HCERTSTORE v25; // rax
  void *v26; // rcx
  HCERTSTORE *p_hRestrictedTrust; // r14
  int v28; // eax
  HCERTSTORE *v29; // r15
  HCERTSTORE v30; // rcx
  HCERTSTORE hRestrictedOther; // rdx
  void *v32; // rcx
  BOOL v33; // eax
  int EngineStore; // eax
  int CertificateObjectCache; // eax
  int v36; // eax
  int v37; // eax
  int ObjectCache; // eax
  void *v39; // rdx
  int v40; // eax
  HANDLE EventA; // rax
  unsigned int v42; // r9d
  void *v43; // rax
  HCERTSTORE v44; // rax
  int CrossCertDistPointsForStore; // eax
  DWORD LastError; // esi
  HCERTSTORE hExclusiveTrustedPeople; // rcx
  HCERTSTORE hExclusiveRoot; // rcx
  BOOL v50; // eax
  void *v51; // rdx
  HCERTSTORE v52; // rax
  void *v53; // r9
  void *v54; // r8
  void *v55; // rcx
  int v56; // eax
  BOOL v57; // eax
  HCERTSTORE v58; // rdx
  HCERTSTORE v59; // rax
  void *v60; // rcx
  BOOL v61; // eax
  void *v62; // rdx
  BOOL v63; // eax
  HCERTSTORE v64; // rax
  BOOL v65; // eax
  BOOL v66; // eax
  DWORD dwDisposition; // [rsp+90h] [rbp+8h] BYREF
  DWORD dwErrCode; // [rsp+98h] [rbp+10h]
  HCERTSTORE hCertStore; // [rsp+A0h] [rbp+18h] BYREF

  v3 = 0;
  v4 = (void **)((char *)this + 136);
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *(_DWORD *)this = 1;
  v8 = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  hCertStore = 0;
  *((_QWORD *)this + 17) = 0;
  *((_DWORD *)this + 38) = a2->cAdditionalStore;
  *((_QWORD *)this + 20) = a2->rghAdditionalStore;
  *((_DWORD *)this + 42) = 0x10000;
  *((_DWORD *)this + 43) = a2->dwFlags;
  *((_QWORD *)this + 6) = 0;
  dwErrCode = 0;
  *a3 = 0;
  *((_DWORD *)this + 14) = I_CryptIsAppContainerToken(0);
  IsAuthRootAutoUpdateDisabled = IPR_IsAuthRootAutoUpdateDisabled();
  *((_DWORD *)this + 15) = IsAuthRootAutoUpdateDisabled;
  if ( IsAuthRootAutoUpdateDisabled )
    IsDisallowedCertAutoUpdateEnabled = IPR_IsDisallowedCertAutoUpdateEnabled();
  else
    IsDisallowedCertAutoUpdateEnabled = 1;
  *((_DWORD *)this + 16) = IsDisallowedCertAutoUpdateEnabled;
  *((_QWORD *)this + 105) = 0;
  *((_QWORD *)this + 104) = 0;
  *((_DWORD *)this + 212) = 0;
  if ( *((_DWORD *)this + 14)
    && (unsigned int)ILS_HasAppContainerExclusiveTrust()
    && (unsigned int)I_CryptHasAppContainerPackageCertificates() )
  {
    *((_DWORD *)this + 43) |= 0x100u;
    *((_DWORD *)this + 15) = 1;
  }
  dwUrlRetrievalTimeout = a2->dwUrlRetrievalTimeout;
  v12 = (DWORD *)((char *)this + 176);
  if ( dwUrlRetrievalTimeout )
  {
    *v12 = dwUrlRetrievalTimeout;
    v13 = 0;
  }
  else
  {
    v13 = 1;
  }
  *((_DWORD *)this + 45) = v13;
  v14 = (HKEY *)((char *)this + 800);
  *((_QWORD *)this + 100) = 0;
  *((_DWORD *)this + 50) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 58) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 101) = 0;
  *((_QWORD *)this + 102) = 0;
  v15 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Cryptography\\OID\\EncodingType 0\\CertDllCreateCertificateChainEngine\\Config",
          0,
          0x20119u,
          (PHKEY)this + 100);
  if ( v15 == 2 )
  {
    dwDisposition = 0;
    v15 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Cryptography\\OID\\EncodingType 0\\CertDllCreateCertificateChainEngine\\Config",
            0,
            0,
            0,
            0x2011Fu,
            0,
            (PHKEY)this + 100,
            &dwDisposition);
  }
  if ( v15 )
    *v14 = 0;
  ChainRegConfigReadParameters(
    *v14,
    (CCertChainEngine *)((char *)this + 248),
    (unsigned int *)((unsigned __int64)v12 & -(__int64)(*((_DWORD *)this + 45) != 0)));
  *((_QWORD *)this + 103) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( (a2->dwFlags & 8) != 0 )
  {
    v16 = 0x20000;
    *((_DWORD *)this + 42) = 0x20000;
  }
  else
  {
    v16 = *((_DWORD *)this + 42);
  }
  if ( (a2->dwFlags & 0x20) != 0 )
    v16 |= 0x40u;
  v17 = v16 | 0x1080;
  *((_DWORD *)this + 42) = v17;
  if ( a2->hRestrictedOther )
  {
    v64 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, v17, L"My");
    *((_QWORD *)this + 16) = v64;
    if ( !v64 )
      goto LABEL_66;
  }
  v18 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, *((_DWORD *)this + 42), L"CA");
  *((_QWORD *)this + 13) = v18;
  if ( !v18 )
    goto LABEL_66;
  v19 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, *((_DWORD *)this + 42), L"Disallowed");
  *((_QWORD *)this + 14) = v19;
  if ( !v19 )
    goto LABEL_66;
  v20 = CertOpenStore((LPCSTR)0xB, 0x10001u, 0, 4u, 0);
  *((_QWORD *)this + 12) = v20;
  if ( !v20 )
    goto LABEL_66;
  if ( a2->cbSize < 0x50 || !a2->hExclusiveRoot && !a2->hExclusiveTrustedPeople )
  {
    v21 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, *((_DWORD *)this + 42), L"Root");
    *((_QWORD *)this + 9) = v21;
    if ( !v21 )
      goto LABEL_66;
    v22 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, *((_DWORD *)this + 42), L"TrustedPeople");
    *((_QWORD *)this + 15) = v22;
    if ( !v22 )
      goto LABEL_66;
    hRestrictedRoot = a2->hRestrictedRoot;
    v24 = (void *)*((_QWORD *)this + 9);
    if ( hRestrictedRoot )
    {
      if ( !(unsigned int)ChainIsProperRestrictedRoot(v24, hRestrictedRoot) )
      {
        v26 = (void *)*((_QWORD *)this + 10);
LABEL_24:
        if ( !v26 )
          goto LABEL_66;
        p_hRestrictedTrust = &a2->hRestrictedTrust;
        if ( a2->hRestrictedTrust && a2->hRestrictedOther )
        {
          v29 = &a2->hRestrictedTrust;
        }
        else
        {
          v28 = ChainCreateWorldStore(
                  v26,
                  *((HCERTSTORE *)this + 13),
                  *((HCERTSTORE *)this + 16),
                  a2->cAdditionalStore,
                  a2->rghAdditionalStore,
                  *((_DWORD *)this + 42),
                  &hCertStore);
          v8 = hCertStore;
          *a3 = v28;
          if ( !v28 )
            goto LABEL_48;
          v29 = &a2->hRestrictedTrust;
        }
        v30 = *p_hRestrictedTrust;
        if ( !*p_hRestrictedTrust )
          v30 = v8;
        *((_QWORD *)this + 11) = CertDuplicateStore(v30);
        hRestrictedOther = a2->hRestrictedOther;
        v32 = (void *)*((_QWORD *)this + 12);
        if ( hRestrictedOther )
        {
          v33 = CertAddStoreToCollection(v32, hRestrictedOther, 0, 0);
          *a3 = v33;
          if ( !v33 )
          {
LABEL_32:
            EngineStore = ChainCreateEngineStore(
                            *((HCERTSTORE *)this + 9),
                            *((HCERTSTORE *)this + 11),
                            *((HCERTSTORE *)this + 12),
                            *((HCERTSTORE *)this + 14),
                            *((HCERTSTORE *)this + 15),
                            *((HCERTSTORE *)this + 16),
                            a2->dwFlags,
                            (void **)this + 17,
                            (void **)this + 18);
            *a3 = EngineStore;
            if ( !EngineStore )
              goto LABEL_48;
            goto LABEL_33;
          }
          v58 = (HCERTSTORE)*((_QWORD *)this + 10);
        }
        else
        {
          v57 = CertAddStoreToCollection(v32, v8, 0, 0);
          *a3 = v57;
          if ( !v57 )
            goto LABEL_48;
          v58 = *v29;
          if ( !*v29 )
            goto LABEL_32;
        }
        v66 = CertAddStoreToCollection(*((HCERTSTORE *)this + 12), v58, 0, 0);
        *a3 = v66;
        if ( !v66 )
          goto LABEL_48;
        goto LABEL_32;
      }
      v25 = CertDuplicateStore(a2->hRestrictedRoot);
      *((_DWORD *)this + 43) |= 0x100u;
    }
    else
    {
      v25 = CertDuplicateStore(v24);
    }
    *((_QWORD *)this + 10) = v25;
    v26 = v25;
    goto LABEL_24;
  }
  *((_DWORD *)this + 43) |= 0x100u;
  *((_DWORD *)this + 12) = 1;
  if ( a2->cbSize >= 0x54 && (a2[1].cbSize & 1) != 0 )
    *((_DWORD *)this + 13) = 1;
  hExclusiveTrustedPeople = a2->hExclusiveTrustedPeople;
  if ( hExclusiveTrustedPeople )
    *((_QWORD *)this + 15) = CertDuplicateStore(hExclusiveTrustedPeople);
  hExclusiveRoot = a2->hExclusiveRoot;
  if ( !hExclusiveRoot
    || (v59 = CertDuplicateStore(hExclusiveRoot),
        v60 = (void *)*((_QWORD *)this + 12),
        *((_QWORD *)this + 10) = v59,
        v61 = CertAddStoreToCollection(v60, v59, 0, 0),
        (*a3 = v61) != 0) )
  {
    v50 = CertAddStoreToCollection(*((HCERTSTORE *)this + 12), *((HCERTSTORE *)this + 13), 0, 0);
    *a3 = v50;
    if ( v50 )
    {
      v51 = (void *)*((_QWORD *)this + 16);
      if ( !v51 || (v65 = CertAddStoreToCollection(*((HCERTSTORE *)this + 12), v51, 0, 0), (*a3 = v65) != 0) )
      {
        while ( v3 < *((_DWORD *)this + 38) )
        {
          v62 = *(void **)(*((_QWORD *)this + 20) + 8LL * v3);
          if ( v62 )
          {
            v63 = CertAddStoreToCollection(*((HCERTSTORE *)this + 12), v62, 0, 0);
            *a3 = v63;
            if ( !v63 )
              goto LABEL_48;
          }
          ++v3;
        }
        v52 = CertDuplicateStore(*((HCERTSTORE *)this + 12));
        v53 = (void *)*((_QWORD *)this + 14);
        v54 = (void *)*((_QWORD *)this + 12);
        v55 = (void *)*((_QWORD *)this + 10);
        *((_QWORD *)this + 11) = v52;
        v56 = ChainCreateEngineStore(
                v55,
                0,
                v54,
                v53,
                *((HCERTSTORE *)this + 15),
                0,
                a2->dwFlags,
                v4,
                (void **)this + 18);
        *a3 = v56;
        if ( v56 )
        {
LABEL_33:
          CertificateObjectCache = ChainCreateCertificateObjectCache(
                                     a2->MaximumCachedCertificates,
                                     (struct CCertObjectCache **)this + 23);
          *a3 = CertificateObjectCache;
          if ( !CertificateObjectCache )
            goto LABEL_48;
          if ( *((_DWORD *)this + 16) )
            *((_QWORD *)this + 105) = I_CertGetAutoUpdateCtl(6, (char *)this + 832);
          v36 = CCertObjectCache::AddKnownStores(
                  *((CCertObjectCache **)this + 23),
                  *((HCERTSTORE *)this + 14),
                  *((void **)this + 10),
                  *((void **)this + 9),
                  *((HCERTSTORE *)this + 15),
                  *((const struct _CTL_CONTEXT **)this + 105),
                  *((_DWORD *)this + 12),
                  *((_DWORD *)this + 13));
          *a3 = v36;
          if ( !v36 )
            goto LABEL_48;
          v37 = CCertObjectCache::AddOcspCACerts(*((CCertObjectCache **)this + 23), *((struct _CERT_STORE **)this + 17));
          *a3 = v37;
          if ( !v37 )
            goto LABEL_48;
          ObjectCache = SSCtlCreateObjectCache((struct CSSCtlObjectCache **)this + 24);
          *a3 = ObjectCache;
          if ( !ObjectCache )
            goto LABEL_48;
          v40 = SSCtlPopulateCacheFromCertStore(this, v39);
          *a3 = v40;
          if ( !v40 )
            goto LABEL_48;
          if ( *((_QWORD *)this + 100) )
          {
            if ( *((_QWORD *)this + 18) )
            {
              EventA = CreateEventA(0, 0, 0, 0);
              *((_QWORD *)this + 101) = EventA;
              if ( EventA )
              {
                if ( RegNotifyChangeKeyValue(*((HKEY *)this + 100), 1, 0x10000005u, EventA, 1)
                  || (v43 = I_RegisterWaitForSingleObjectEx(
                              *((void **)this + 101),
                              (void (*)(void *, unsigned __int8))ChainRegConfigChangeCallback,
                              this,
                              v42,
                              0x80u),
                      (*((_QWORD *)this + 102) = v43) == 0) )
                {
                  CloseHandle(*((HANDLE *)this + 101));
                  *((_QWORD *)this + 101) = 0;
                  *((_QWORD *)this + 102) = 0;
                }
              }
            }
          }
          v44 = CertOpenStore((LPCSTR)0xB, 0x10001u, 0, 4u, 0);
          *((_QWORD *)this + 28) = v44;
          if ( v44 )
          {
            CrossCertDistPointsForStore = CCertChainEngine::GetCrossCertDistPointsForStore(
                                            this,
                                            *((struct _CERT_STORE **)this + 17),
                                            1,
                                            (struct _XCERT_DP_LINK **)this + 27);
            *a3 = CrossCertDistPointsForStore;
            if ( CrossCertDistPointsForStore )
              *a3 = CertAddStoreToCollection(*((HCERTSTORE *)this + 12), *((HCERTSTORE *)this + 28), 0, 0);
            goto LABEL_48;
          }
LABEL_66:
          *a3 = 0;
        }
      }
    }
  }
LABEL_48:
  _InterlockedIncrement(&g_cCertChainEngines);
  if ( *a3 )
    LastError = dwErrCode;
  else
    LastError = GetLastError();
  if ( v8 )
    CertCloseStore(v8, 0);
  if ( !*a3 )
    SetLastError(LastError);
  return this;
}

```

## disassembly

```asm
0x180017e6c  mov     rax, rsp
0x180017e6f  mov     [rax+20h], rbx
0x180017e73  push    rbp
0x180017e74  push    rsi
0x180017e75  push    rdi
0x180017e76  push    r12
0x180017e78  push    r13
0x180017e7a  push    r14
0x180017e7c  push    r15
0x180017e7e  sub     rsp, 50h
0x180017e82  xor     ebp, ebp
0x180017e84  lea     r13, [rcx+88h]
0x180017e8b  mov     [rcx+50h], rbp
0x180017e8f  mov     rbx, rcx
0x180017e92  mov     [rcx+48h], rbp
0x180017e96  mov     rdi, r8
0x180017e99  mov     [rcx+58h], rbp
0x180017e9d  mov     rsi, rdx
0x180017ea0  mov     [rcx+60h], rbp
0x180017ea4  lea     r14d, [rbp+1]
0x180017ea8  mov     [rcx], r14d
0x180017eab  mov     r12d, ebp
0x180017eae  mov     [rcx+68h], rbp
0x180017eb2  mov     [rcx+70h], rbp
0x180017eb6  mov     [rcx+78h], rbp
0x180017eba  mov     [rcx+80h], rbp
0x180017ec1  mov     [rcx+90h], rbp
0x180017ec8  mov     [rcx+0B8h], rbp
0x180017ecf  mov     [rcx+0C0h], rbp
0x180017ed6  mov     [rax+18h], rbp
0x180017eda  mov     [r13+0], rbp
0x180017ede  mov     eax, [rdx+20h]
0x180017ee1  mov     [rcx+98h], eax
0x180017ee7  mov     rax, [rdx+28h]
0x180017eeb  mov     [rcx+0A0h], rax
0x180017ef2  mov     dword ptr [rcx+0A8h], 10000h
0x180017efc  mov     eax, [rdx+30h]
0x180017eff  mov     [rcx+0ACh], eax
0x180017f05  mov     [rcx+30h], rbp
0x180017f09  xor     ecx, ecx
0x180017f0b  mov     [rsp+88h+dwErrCode], ebp
0x180017f12  mov     [r8], ebp
0x180017f15  call    I_CryptIsAppContainerToken
0x180017f1a  mov     [rbx+38h], eax
0x180017f1d  call    ?IPR_IsAuthRootAutoUpdateDisabled@@YAHXZ; IPR_IsAuthRootAutoUpdateDisabled(void)
0x180017f22  mov     [rbx+3Ch], eax
0x180017f25  test    eax, eax
0x180017f27  jnz     loc_18001860D
0x180017f2d  mov     eax, r14d
0x180017f30  mov     [rbx+40h], eax
0x180017f33  mov     [rbx+348h], rbp
0x180017f3a  mov     [rbx+340h], rbp
0x180017f41  mov     [rbx+350h], ebp
0x180017f47  cmp     [rbx+38h], ebp
0x180017f4a  jnz     loc_18001854C
0x180017f50  mov     eax, [rsi+34h]
0x180017f53  lea     r15, [rbx+0B0h]
0x180017f5a  test    eax, eax
0x180017f5c  jz      loc_180018504
0x180017f62  mov     [r15], eax
0x180017f65  mov     eax, ebp
0x180017f67  mov     [rbx+0B4h], eax
0x180017f6d  lea     r14, [rbx+320h]
0x180017f74  mov     r9d, 20119h; samDesired
0x180017f7a  mov     [r14], rbp
0x180017f7d  xor     r8d, r8d; ulOptions
0x180017f80  mov     [rsp+88h+phkResult], r14; phkResult
0x180017f85  lea     rdx, SubKey; "Software\\Microsoft\\Cryptography\\OID"...
0x180017f8c  mov     [rbx+0C8h], ebp
0x180017f92  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017f99  mov     [rbx+0D0h], rbp
0x180017fa0  mov     [rbx+0D8h], rbp
0x180017fa7  mov     [rbx+0E0h], rbp
0x180017fae  mov     [rbx+0E8h], ebp
0x180017fb4  mov     [rbx+0F0h], rbp
0x180017fbb  mov     [rbx+328h], rbp
0x180017fc2  mov     [rbx+330h], rbp
0x180017fc9  call    cs:__imp_RegOpenKeyExW
0x180017fcf  cmp     eax, 2
0x180017fd2  jz      loc_180018617
0x180017fd8  test    eax, eax
0x180017fda  jnz     loc_180018660
0x180017fe0  mov     eax, [rbx+0B4h]
0x180017fe6  lea     rdx, [rbx+0F8h]; struct _CHAIN_CONFIG *
0x180017fed  mov     rcx, [r14]; hKey
0x180017ff0  neg     eax
0x180017ff2  sbb     r8, r8
0x180017ff5  and     r8, r15; unsigned int *
0x180017ff8  call    ?ChainRegConfigReadParameters@@YAXPEAUHKEY__@@PEAU_CHAIN_CONFIG@@PEAK@Z; ChainRegConfigReadParameters(HKEY__ *,_CHAIN_CONFIG *,ulong *)
0x180017ffd  lea     rcx, [rbx+8]; lpCriticalSection
0x180018001  mov     [rbx+338h], rbp
0x180018008  call    cs:__imp_InitializeCriticalSection
0x18001800e  test    byte ptr [rsi+30h], 8
0x180018012  jz      loc_1800185A1
0x180018018  mov     r9d, 20000h
0x18001801e  mov     [rbx+0A8h], r9d
0x180018025  test    byte ptr [rsi+30h], 20h
0x180018029  jz      short loc_18001802F
0x18001802b  or      r9d, 40h
0x18001802f  or      r9d, 1080h; dwFlags
0x180018036  mov     r15d, 10001h
0x18001803c  mov     [rbx+0A8h], r9d
0x180018043  mov     r14d, 0Ah
0x180018049  cmp     [rsi+18h], rbp
0x18001804d  jnz     loc_180018668
0x180018053  mov     r9d, [rbx+0A8h]; dwFlags
0x18001805a  lea     rax, aCa_0; "CA"
0x180018061  xor     r8d, r8d; hCryptProv
0x180018064  mov     [rsp+88h+phkResult], rax; pvPara
0x180018069  mov     edx, r15d; dwEncodingType
0x18001806c  mov     rcx, r14; lpszStoreProvider
0x18001806f  call    CertOpenStore
0x180018074  mov     [rbx+68h], rax
0x180018078  test    rax, rax
0x18001807b  jz      loc_1800184FD
0x180018081  mov     r9d, [rbx+0A8h]; dwFlags
0x180018088  lea     rax, aDisallowed; "Disallowed"
0x18001808f  xor     r8d, r8d; hCryptProv
0x180018092  mov     [rsp+88h+phkResult], rax; pvPara
0x180018097  mov     edx, r15d; dwEncodingType
0x18001809a  mov     rcx, r14; lpszStoreProvider
0x18001809d  call    CertOpenStore
0x1800180a2  mov     [rbx+70h], rax
0x1800180a6  test    rax, rax
0x1800180a9  jz      loc_1800184FD
0x1800180af  mov     r9d, 4; dwFlags
0x1800180b5  mov     [rsp+88h+phkResult], rbp; pvPara
0x1800180ba  xor     r8d, r8d; hCryptProv
0x1800180bd  mov     edx, r15d; dwEncodingType
0x1800180c0  lea     ecx, [r9+7]; lpszStoreProvider
0x1800180c4  call    CertOpenStore
0x1800180c9  mov     [rbx+60h], rax
0x1800180cd  test    rax, rax
0x1800180d0  jz      loc_1800184FD
0x1800180d6  cmp     dword ptr [rsi], 50h ; 'P'
0x1800180d9  jnb     loc_180018428
0x1800180df  mov     r9d, [rbx+0A8h]; dwFlags
0x1800180e6  lea     rax, aRoot_0; "Root"
0x1800180ed  xor     r8d, r8d; hCryptProv
0x1800180f0  mov     [rsp+88h+phkResult], rax; pvPara
0x1800180f5  mov     edx, r15d; dwEncodingType
0x1800180f8  mov     rcx, r14; lpszStoreProvider
0x1800180fb  call    CertOpenStore
0x180018100  mov     [rbx+48h], rax
0x180018104  test    rax, rax
0x180018107  jz      loc_1800184FD
0x18001810d  mov     r9d, [rbx+0A8h]; dwFlags
0x180018114  lea     rax, aTrustedpeople; "TrustedPeople"
0x18001811b  xor     r8d, r8d; hCryptProv
0x18001811e  mov     [rsp+88h+phkResult], rax; pvPara
0x180018123  mov     edx, r15d; dwEncodingType
0x180018126  mov     rcx, r14; lpszStoreProvider
0x180018129  call    CertOpenStore
0x18001812e  mov     [rbx+78h], rax
0x180018132  test    rax, rax
0x180018135  jz      loc_1800184FD
0x18001813b  mov     rdx, [rsi+8]; HCERTSTORE
0x18001813f  mov     rcx, [rbx+48h]; hCertStore
0x180018143  test    rdx, rdx
0x180018146  jnz     loc_1800186C3
0x18001814c  call    CertDuplicateStore
0x180018151  mov     [rbx+50h], rax
0x180018155  mov     rcx, rax; hSiblingStore
0x180018158  test    rcx, rcx
0x18001815b  jz      loc_1800184FD
0x180018161  lea     r14, [rsi+10h]
0x180018165  cmp     [r14], rbp
0x180018168  jnz     loc_1800186E6
0x18001816e  mov     r9d, [rsi+20h]; unsigned int
0x180018172  lea     rax, [rsp+88h+hCertStore]
0x18001817a  mov     r8, [rbx+80h]; HCERTSTORE
0x180018181  mov     rdx, [rbx+68h]; HCERTSTORE
0x180018185  mov     [rsp+88h+lpSecurityAttributes], rax; void **
0x18001818a  mov     eax, [rbx+0A8h]
0x180018190  mov     [rsp+88h+samDesired], eax; dwFlags
0x180018194  mov     rax, [rsi+28h]
0x180018198  mov     [rsp+88h+phkResult], rax; void **
0x18001819d  call    ?ChainCreateWorldStore@@YAHPEAX00KPEAPEAXK1@Z; ChainCreateWorldStore(void *,void *,void *,ulong,void * *,ulong,void * *)
0x1800181a2  mov     r12, [rsp+88h+hCertStore]
0x1800181aa  mov     [rdi], eax
0x1800181ac  test    eax, eax
0x1800181ae  jz      loc_1800183E0
0x1800181b4  lea     r15, [rsi+10h]
0x1800181b8  mov     rcx, [r14]
0x1800181bb  test    rcx, rcx
0x1800181be  jnz     short loc_1800181C3
0x1800181c0  mov     rcx, r12; hCertStore
0x1800181c3  call    CertDuplicateStore
0x1800181c8  mov     [rbx+58h], rax
0x1800181cc  xor     r9d, r9d; dwPriority
0x1800181cf  mov     rdx, [rsi+18h]; hSiblingStore
0x1800181d3  xor     r8d, r8d; dwUpdateFlags
0x1800181d6  mov     rcx, [rbx+60h]; hCollectionStore
0x1800181da  test    rdx, rdx
0x1800181dd  jz      loc_18001850C
0x1800181e3  call    CertAddStoreToCollection
0x1800181e8  mov     [rdi], eax
0x1800181ea  test    eax, eax
0x1800181ec  jnz     loc_1800186F8
0x1800181f2  mov     r9, [rbx+70h]; HCERTSTORE
0x1800181f6  lea     rax, [rbx+90h]
0x1800181fd  mov     r8, [rbx+60h]; HCERTSTORE
0x180018201  lea     rcx, [rbx+88h]
0x180018208  mov     rdx, [rbx+58h]; HCERTSTORE
0x18001820c  mov     [rsp+88h+lpdwDisposition], rax; void **
0x180018211  mov     eax, [rsi+30h]
0x180018214  mov     [rsp+88h+var_50], rcx; void **
0x180018219  mov     rcx, [rbx+48h]; hSiblingStore
0x18001821d  mov     dword ptr [rsp+88h+lpSecurityAttributes], eax; unsigned int
0x180018221  mov     rax, [rbx+80h]
0x180018228  mov     qword ptr [rsp+88h+samDesired], rax; HCERTSTORE
0x18001822d  mov     rax, [rbx+78h]
0x180018231  mov     [rsp+88h+phkResult], rax; HCERTSTORE
0x180018236  call    ?ChainCreateEngineStore@@YAHPEAX00000KPEAPEAX1@Z; ChainCreateEngineStore(void *,void *,void *,void *,void *,void *,ulong,void * *,void * *)
0x18001823b  mov     [rdi], eax
0x18001823d  test    eax, eax
0x18001823f  jz      loc_1800183E0
0x180018245  mov     r14d, 1
0x18001824b  mov     r15d, 10001h
0x180018251  mov     ecx, [rsi+38h]; unsigned int
0x180018254  lea     rdx, [rbx+0B8h]; struct CCertObjectCache **
0x18001825b  call    ?ChainCreateCertificateObjectCache@@YAHKPEAPEAVCCertObjectCache@@@Z; ChainCreateCertificateObjectCache(ulong,CCertObjectCache * *)
0x180018260  mov     [rdi], eax
0x180018262  test    eax, eax
0x180018264  jz      loc_1800183E0
0x18001826a  cmp     [rbx+40h], ebp
0x18001826d  jz      short loc_180018287
0x18001826f  lea     rdx, [rbx+340h]
0x180018276  mov     ecx, 6
0x18001827b  call    I_CertGetAutoUpdateCtl
0x180018280  mov     [rbx+348h], rax
0x180018287  mov     eax, [rbx+34h]
0x18001828a  mov     r9, [rbx+48h]; void *
0x18001828e  mov     r8, [rbx+50h]; void *
0x180018292  mov     rdx, [rbx+70h]; hCertStore
0x180018296  mov     rcx, [rbx+0B8h]; this
0x18001829d  mov     dword ptr [rsp+88h+var_50], eax; int
0x1800182a1  mov     eax, [rbx+30h]
0x1800182a4  mov     dword ptr [rsp+88h+lpSecurityAttributes], eax; int
0x1800182a8  mov     rax, [rbx+348h]
0x1800182af  mov     qword ptr [rsp+88h+samDesired], rax; struct _CTL_CONTEXT *
0x1800182b4  mov     rax, [rbx+78h]
0x1800182b8  mov     [rsp+88h+phkResult], rax; HCERTSTORE
0x1800182bd  call    ?AddKnownStores@CCertObjectCache@@QEAAHPEAX000PEBU_CTL_CONTEXT@@HH@Z; CCertObjectCache::AddKnownStores(void *,void *,void *,void *,_CTL_CONTEXT const *,int,int)
0x1800182c2  mov     [rdi], eax
0x1800182c4  test    eax, eax
0x1800182c6  jz      loc_1800183E0
0x1800182cc  mov     rdx, [rbx+88h]; struct _CERT_STORE *
0x1800182d3  mov     rcx, [rbx+0B8h]; this
0x1800182da  call    ?AddOcspCACerts@CCertObjectCache@@QEAAHPEAX@Z; CCertObjectCache::AddOcspCACerts(void *)
0x1800182df  mov     [rdi], eax
0x1800182e1  test    eax, eax
0x1800182e3  jz      loc_1800183E0
0x1800182e9  lea     rcx, [rbx+0C0h]; struct CSSCtlObjectCache **
0x1800182f0  call    ?SSCtlCreateObjectCache@@YAHPEAPEAVCSSCtlObjectCache@@@Z; SSCtlCreateObjectCache(CSSCtlObjectCache * *)
0x1800182f5  mov     [rdi], eax
0x1800182f7  test    eax, eax
0x1800182f9  jz      loc_1800183E0
0x1800182ff  mov     rcx, rbx; struct CCertChainEngine *
0x180018302  call    ?SSCtlPopulateCacheFromCertStore@@YAHPEAVCCertChainEngine@@PEAX@Z; SSCtlPopulateCacheFromCertStore(CCertChainEngine *,void *)
0x180018307  mov     [rdi], eax
0x180018309  test    eax, eax
0x18001830b  jz      loc_1800183E0
0x180018311  cmp     [rbx+320h], rbp
0x180018318  jz      short loc_180018393
0x18001831a  cmp     [rbx+90h], rbp
0x180018321  jz      short loc_180018393
0x180018323  xor     r9d, r9d; lpName
0x180018326  xor     r8d, r8d; bInitialState
0x180018329  xor     edx, edx; bManualReset
0x18001832b  xor     ecx, ecx; lpEventAttributes
0x18001832d  call    cs:__imp_CreateEventA
0x180018333  mov     [rbx+328h], rax
0x18001833a  test    rax, rax
0x18001833d  jz      short loc_180018393
0x18001833f  mov     rcx, [rbx+320h]; hKey
0x180018346  mov     r9, rax; hEvent
0x180018349  mov     r8d, 10000005h; dwNotifyFilter
0x18001834f  mov     dword ptr [rsp+88h+phkResult], r14d; fAsynchronous
0x180018354  mov     edx, r14d; bWatchSubtree
0x180018357  call    cs:__imp_RegNotifyChangeKeyValue
0x18001835d  test    eax, eax
0x18001835f  jnz     loc_18001871A
0x180018365  mov     rcx, [rbx+328h]; void *
0x18001836c  lea     rdx, ?ChainRegConfigChangeCallback@@YAXPEAXE@Z; void (*)(void *, unsigned __int8)
0x180018373  mov     r8, rbx; void *
0x180018376  mov     dword ptr [rsp+88h+phkResult], 80h; unsigned int
0x18001837e  call    ?I_RegisterWaitForSingleObjectEx@@YAPEAXPEAXP6AX0E@Z0KK@Z; I_RegisterWaitForSingleObjectEx(void *,void (*)(void *,uchar),void *,ulong,ulong)
0x180018383  mov     [rbx+330h], rax
0x18001838a  test    rax, rax
0x18001838d  jz      loc_18001871A
0x180018393  mov     r9d, 4; dwFlags
0x180018399  mov     [rsp+88h+phkResult], rbp; pvPara
0x18001839e  xor     r8d, r8d; hCryptProv
0x1800183a1  mov     edx, r15d; dwEncodingType
0x1800183a4  lea     ecx, [r9+7]; lpszStoreProvider
0x1800183a8  call    CertOpenStore
0x1800183ad  mov     [rbx+0E0h], rax
0x1800183b4  test    rax, rax
0x1800183b7  jz      loc_1800184FD
  ... truncated ...
```
