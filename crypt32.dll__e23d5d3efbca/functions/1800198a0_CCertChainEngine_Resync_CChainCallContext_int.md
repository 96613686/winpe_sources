# CCertChainEngine::Resync(CChainCallContext *,int)

- ea: `0x1800198a0`
- end: `0x180019df3`
- name: `?Resync@CCertChainEngine@@QEAAHPEAVCChainCallContext@@H@Z`
- size: `1363`
- prototype: `__int64 __fastcall(CCertChainEngine *this, struct CChainCallContext *, int)`
- caller_count: `4`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180019764`
- `0x180062198`
- `0x18008dfa0`
- `0x1800f12c0`

## callees

- `0x180010610`
- `0x1800198a0`
- `0x180019dfc`
- `0x180019fa0`
- `0x18001a018`
- `0x18001a0d0`
- `0x18001a234`
- `0x18001a534`
- `0x18001a570`
- `0x18001ab2c`
- `0x180028d60`
- `0x18002c860`
- `0x18003523c`
- `0x1800352b8`
- `0x1800353c8`
- `0x180035404`
- `0x180037114`
- `0x1800450c0`
- `0x180055610`
- `0x180055ae4`
- `0x18005e720`
- `0x1800614e0`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019db3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019db3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800198d7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800198d7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019a62`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019ca4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019d70`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019d93`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019a62`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019ca4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019d70`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019d93`

## pseudocode

```c
__int64 __fastcall CCertChainEngine::Resync(CCertChainEngine *this, struct CChainCallContext *a2, int a3)
{
  HANDLE *v3; // rbx
  void *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rcx
  void (__fastcall *v9)(_QWORD, __int64, __int64, HANDLE *); // rax
  __int64 v10; // rbx
  unsigned int *v11; // rbx
  const void *v12; // r14
  HKEY v13; // rax
  HKEY v14; // r15
  const CERT_CONTEXT *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rbx
  void *v19; // rdx
  __int64 v20; // rcx
  const void *v22; // rbx
  HKEY updated; // rax
  HKEY v24; // r14
  const CERT_CONTEXT *v25; // rcx
  BYTE *pbEncoded; // [rsp+40h] [rbp-30h] BYREF
  struct _CERT_CREATE_CONTEXT_PARA pCreatePara; // [rsp+48h] [rbp-28h] BYREF
  FILETIME FileTime1; // [rsp+C8h] [rbp+58h] BYREF

  v3 = (HANDLE *)((char *)this + 144);
  if ( !a3 && WaitForSingleObject(*v3, 0) )
    goto LABEL_48;
  v6 = (void *)*((_QWORD *)this + 98);
  if ( v6 )
  {
    PkiDefaultCryptFree(v6);
    *((_QWORD *)this + 98) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 41);
  if ( v7 )
  {
    PkiDefaultCryptFree(v7);
    *((_QWORD *)this + 41) = 0;
  }
  ChainFreeConfigSha256Allow((char *)this + 248);
  ChainRegConfigReadParameters(
    *((HKEY *)this + 100),
    (CCertChainEngine *)((char *)this + 248),
    (unsigned int *)(((unsigned __int64)this + 176) & -(__int64)(*((_DWORD *)this + 45) != 0)));
  v8 = *((_QWORD *)this + 17);
  if ( *(_DWORD *)v8 == 3 )
  {
    ControlCollectionStore((struct _CERT_STORE *)v8, 1u, 1u, v3);
  }
  else if ( *(_DWORD *)(v8 + 156) > 0xDu
         && (v9 = *(void (__fastcall **)(_QWORD, __int64, __int64, HANDLE *))(*(_QWORD *)(v8 + 160) + 104LL)) != 0 )
  {
    v9(*(_QWORD *)(v8 + 168), 1, 1, v3);
  }
  else
  {
    SetLastError(0x78u);
  }
  CCertObjectCache::FlushObjects(*((CCertObjectCache **)this + 23), a2);
  I_CryptFlushLruCache(*(_QWORD *)(*((_QWORD *)this + 23) + 48LL), 0, a2);
  v10 = *((_QWORD *)this + 23);
  I_CryptFlushLruCache(*(_QWORD *)(v10 + 56), 0, a2);
  I_CryptFlushLruCache(*(_QWORD *)(v10 + 64), 0, a2);
  if ( *((_DWORD *)this + 16) )
  {
    FileTime1 = 0;
    if ( (unsigned int)GetAutoUpdateLastSyncTime(-2147483646, 6, &FileTime1) )
    {
      pbEncoded = 0;
      if ( (unsigned int)GetAutoUpdateLastSyncTime(-2147483647, 6, &pbEncoded) )
      {
        if ( CompareFileTime((const FILETIME *)&pbEncoded, &FileTime1) > 0 )
          FileTime1 = (FILETIME)pbEncoded;
      }
    }
    if ( !*((_QWORD *)this + 105) || CompareFileTime(&FileTime1, (const FILETIME *)this + 104) )
    {
      pbEncoded = 0;
      memset(&pCreatePara.pvFree, 0, 24);
      v22 = 0;
      *(&pCreatePara.cbSize + 1) = 0;
      updated = (HKEY)OpenAutoUpdateKey(-2147483646);
      v24 = updated;
      if ( updated && (unsigned int)I_CertReadBINARYValueFromRegistry(updated, L"DisallowedCertEncodedCtl") )
      {
        pCreatePara.cbSize = 40;
        pCreatePara.pfnFree = (PFN_CRYPT_FREE)PkiDefaultCryptFree;
        v22 = CertCreateContext(3u, 0x10001u, pbEncoded, 0, 1u, &pCreatePara);
      }
      CloseRegistryKey(v24);
      if ( v22 )
      {
        v25 = (const CERT_CONTEXT *)*((_QWORD *)this + 105);
        if ( v25 )
          CertFreeCertificateContext(v25);
        *((FILETIME *)this + 104) = FileTime1;
        *((_QWORD *)this + 105) = v22;
      }
    }
  }
  v11 = (unsigned int *)*((_QWORD *)this + 30);
  if ( v11 )
  {
    FileTime1 = 0;
    if ( (unsigned int)GetAutoUpdateLastSyncTime(-2147483646, 5, &FileTime1) )
    {
      pbEncoded = 0;
      if ( (unsigned int)GetAutoUpdateLastSyncTime(-2147483647, 5, &pbEncoded) )
      {
        if ( CompareFileTime((const FILETIME *)&pbEncoded, &FileTime1) > 0 )
          FileTime1 = (FILETIME)pbEncoded;
      }
    }
    if ( !*((_QWORD *)v11 + 5) || CompareFileTime(&FileTime1, (const FILETIME *)v11 + 3) )
    {
      pbEncoded = 0;
      *(&pCreatePara.cbSize + 1) = 0;
      memset(&pCreatePara.pvFree, 0, 24);
      v12 = 0;
      I_CertGetAutoUpdateLastSyncTime(5, &FileTime1);
      v13 = (HKEY)OpenAutoUpdateKey(-2147483646);
      v14 = v13;
      if ( !v13
        || !(unsigned int)I_CertReadBINARYValueFromRegistry(v13, L"EncodedCtl")
        || (pCreatePara.pfnFree = (PFN_CRYPT_FREE)PkiDefaultCryptFree,
            pCreatePara.cbSize = 40,
            (v12 = CertCreateContext(3u, 0x10001u, pbEncoded, 0, 1u, &pCreatePara)) == 0) )
      {
        FileTime1 = 0;
      }
      CloseRegistryKey(v14);
      if ( v12 )
      {
        v15 = (const CERT_CONTEXT *)*((_QWORD *)v11 + 5);
        if ( v15 )
          CertFreeCertificateContext(v15);
        v16 = 10000000LL * *v11;
        *((_QWORD *)v11 + 5) = v12;
        v17 = *(_QWORD *)&FileTime1 + v16;
        *((FILETIME *)v11 + 3) = FileTime1;
        *((_QWORD *)v11 + 4) = v17;
        FreeAuthRootAutoUpdateMatchCaches((void **const)v11 + 6);
      }
    }
  }
  CCertObjectCache::AddKnownStores(
    *((CCertObjectCache **)this + 23),
    *((HCERTSTORE *)this + 14),
    *((void **)this + 10),
    *((void **)this + 9),
    *((HCERTSTORE *)this + 15),
    *((const struct _CTL_CONTEXT **)this + 105),
    *((_DWORD *)this + 12),
    *((_DWORD *)this + 13));
  CertRemoveStoreFromCollection(*((HCERTSTORE *)this + 12), *((HCERTSTORE *)this + 28));
  CCertObjectCache::AddOcspCACerts(*((CCertObjectCache **)this + 23), *((struct _CERT_STORE **)this + 17));
  v18 = *((_QWORD *)this + 24);
  I_CryptFlushLruCache(*(_QWORD *)v18, 0, 0);
  *(_QWORD *)(v18 + 8) = 0;
  *(_DWORD *)(v18 + 16) = 0;
  SSCtlPopulateCacheFromCertStore(this, v19);
  LODWORD(v18) = CCertChainEngine::GetCrossCertDistPointsForStore(
                   this,
                   *((struct _CERT_STORE **)this + 17),
                   1,
                   (struct _XCERT_DP_LINK **)this + 27);
  CertAddStoreToCollection(*((HCERTSTORE *)this + 12), *((HCERTSTORE *)this + 28), 0, 0);
  v20 = *((_QWORD *)a2 + 1);
  *((_DWORD *)a2 + 37) = ++*(_DWORD *)(v20 + 200);
  if ( (_DWORD)v18 )
  {
LABEL_48:
    do
    {
      *((_DWORD *)a2 + 37) = *(_DWORD *)(*((_QWORD *)a2 + 1) + 200LL);
      CCertChainEngine::UpdateCrossCerts(this, a2);
    }
    while ( *((_DWORD *)a2 + 37) != *(_DWORD *)(*((_QWORD *)a2 + 1) + 200LL) );
  }
  return 1;
}

```

## disassembly

```asm
0x1800198a0  mov     [rsp-38h+arg_0], rbx
0x1800198a5  push    rbp
0x1800198a6  push    rsi
0x1800198a7  push    rdi
0x1800198a8  push    r12
0x1800198aa  push    r13
0x1800198ac  push    r14
0x1800198ae  push    r15
0x1800198b0  mov     rbp, rsp
0x1800198b3  sub     rsp, 70h
0x1800198b7  xor     r12d, r12d
0x1800198ba  lea     rbx, [rcx+90h]
0x1800198c1  mov     rsi, rdx
0x1800198c4  mov     rdi, rcx
0x1800198c7  mov     r13d, 1
0x1800198cd  test    r8d, r8d
0x1800198d0  jnz     short loc_180019913
0x1800198d2  mov     rcx, [rbx]; hHandle
0x1800198d5  xor     edx, edx; dwMilliseconds
0x1800198d7  call    cs:__imp_WaitForSingleObject
0x1800198dd  test    eax, eax
0x1800198df  jz      short loc_180019913
0x1800198e1  mov     rcx, [rsi+8]
0x1800198e5  mov     edx, [rcx+0C8h]
0x1800198eb  mov     rcx, rdi; this
0x1800198ee  mov     [rsi+94h], edx
0x1800198f4  mov     rdx, rsi; struct CChainCallContext *
0x1800198f7  call    ?UpdateCrossCerts@CCertChainEngine@@QEAAHPEAVCChainCallContext@@@Z; CCertChainEngine::UpdateCrossCerts(CChainCallContext *)
0x1800198fc  mov     rcx, [rsi+8]
0x180019900  mov     edx, [rcx+0C8h]
0x180019906  cmp     [rsi+94h], edx
0x18001990c  jnz     short loc_1800198E1
0x18001990e  jmp     loc_180019C25
0x180019913  lea     r14, [rdi+0F8h]
0x18001991a  mov     rcx, [r14+218h]; hMem
0x180019921  test    rcx, rcx
0x180019924  jnz     loc_180019DC7
0x18001992a  mov     rcx, [rdi+148h]; hMem
0x180019931  test    rcx, rcx
0x180019934  jnz     loc_180019DD8
0x18001993a  mov     rcx, r14
0x18001993d  call    ChainFreeConfigSha256Allow
0x180019942  mov     eax, [rdi+0B4h]
0x180019948  lea     rcx, [rdi+0B0h]
0x18001994f  neg     eax
0x180019951  mov     rdx, r14; struct _CHAIN_CONFIG *
0x180019954  sbb     r8, r8
0x180019957  and     r8, rcx; unsigned int *
0x18001995a  mov     rcx, [rdi+320h]; hKey
0x180019961  call    ?ChainRegConfigReadParameters@@YAXPEAUHKEY__@@PEAU_CHAIN_CONFIG@@PEAK@Z; ChainRegConfigReadParameters(HKEY__ *,_CHAIN_CONFIG *,ulong *)
0x180019966  mov     rcx, [rdi+88h]; struct _CERT_STORE *
0x18001996d  cmp     dword ptr [rcx], 3
0x180019970  jz      loc_180019C40
0x180019976  cmp     dword ptr [rcx+9Ch], 0Dh
0x18001997d  jbe     loc_180019DAE
0x180019983  mov     rax, [rcx+0A0h]
0x18001998a  mov     rax, [rax+68h]
0x18001998e  test    rax, rax
0x180019991  jz      loc_180019DAE
0x180019997  mov     rcx, [rcx+0A8h]
0x18001999e  mov     r9, rbx
0x1800199a1  mov     r8d, r13d
0x1800199a4  mov     edx, r13d
0x1800199a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199ac  mov     rcx, [rdi+0B8h]; this
0x1800199b3  mov     rdx, rsi; struct CChainCallContext *
0x1800199b6  call    ?FlushObjects@CCertObjectCache@@QEAAXPEAVCChainCallContext@@@Z; CCertObjectCache::FlushObjects(CChainCallContext *)
0x1800199bb  mov     rcx, [rdi+0B8h]
0x1800199c2  mov     r8, rsi
0x1800199c5  xor     edx, edx
0x1800199c7  mov     rcx, [rcx+30h]
0x1800199cb  call    I_CryptFlushLruCache
0x1800199d0  mov     rbx, [rdi+0B8h]
0x1800199d7  mov     r8, rsi
0x1800199da  xor     edx, edx
0x1800199dc  mov     rcx, [rbx+38h]
0x1800199e0  call    I_CryptFlushLruCache
0x1800199e5  mov     rcx, [rbx+40h]
0x1800199e9  mov     r8, rsi
0x1800199ec  xor     edx, edx
0x1800199ee  call    I_CryptFlushLruCache
0x1800199f3  lea     r15, PkiDefaultCryptFree
0x1800199fa  cmp     [rdi+40h], r12d
0x1800199fe  jnz     loc_180019C53
0x180019a04  mov     rbx, [rdi+0F0h]
0x180019a0b  test    rbx, rbx
0x180019a0e  jz      loc_180019B53
0x180019a14  mov     r15d, 5
0x180019a1a  mov     qword ptr [rbp+FileTime1.dwLowDateTime], r12
0x180019a1e  mov     edx, r15d
0x180019a21  lea     r8, [rbp+FileTime1]
0x180019a25  mov     rcx, 0FFFFFFFF80000002h
0x180019a2c  call    _GetAutoUpdateLastSyncTime
0x180019a31  test    eax, eax
0x180019a33  jz      short loc_180019A54
0x180019a35  lea     r8, [rbp+pbEncoded]
0x180019a39  mov     [rbp+pbEncoded], r12
0x180019a3d  mov     edx, r15d
0x180019a40  mov     rcx, 0FFFFFFFF80000001h
0x180019a47  call    _GetAutoUpdateLastSyncTime
0x180019a4c  test    eax, eax
0x180019a4e  jnz     loc_180019D8B
0x180019a54  cmp     [rbx+28h], r12
0x180019a58  jz      short loc_180019A70
0x180019a5a  lea     rdx, [rbx+18h]; lpFileTime2
0x180019a5e  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180019a62  call    cs:__imp_CompareFileTime
0x180019a68  test    eax, eax
0x180019a6a  jz      loc_180019B53
0x180019a70  xorps   xmm0, xmm0
0x180019a73  mov     [rbp+pbEncoded], r12
0x180019a77  xor     r8d, r8d
0x180019a7a  mov     [rbp+cbEncoded], r12d
0x180019a7e  lea     rdx, [rbp+FileTime1]
0x180019a82  mov     dword ptr [rbp+var_28+4], r12d
0x180019a86  mov     ecx, r15d
0x180019a89  mov     [rbp+var_28.pvSort], r12
0x180019a8d  movdqu  xmmword ptr [rbp+var_28.pvFree], xmm0
0x180019a92  mov     r14, r12
0x180019a95  call    I_CertGetAutoUpdateLastSyncTime
0x180019a9a  mov     rcx, 0FFFFFFFF80000002h
0x180019aa1  call    _OpenAutoUpdateKey
0x180019aa6  mov     r15, rax
0x180019aa9  test    rax, rax
0x180019aac  jz      loc_180019DBE
0x180019ab2  lea     r9, [rbp+cbEncoded]
0x180019ab6  mov     rcx, rax; hKey
0x180019ab9  lea     r8, [rbp+pbEncoded]
0x180019abd  lea     rdx, aEncodedctl; "EncodedCtl"
0x180019ac4  call    I_CertReadBINARYValueFromRegistry
0x180019ac9  test    eax, eax
0x180019acb  jz      loc_180019DBE
0x180019ad1  mov     r9d, [rbp+cbEncoded]; cbEncoded
0x180019ad5  lea     rax, PkiDefaultCryptFree
0x180019adc  mov     r8, [rbp+pbEncoded]; pbEncoded
0x180019ae0  mov     edx, 10001h; dwEncodingType
0x180019ae5  mov     [rbp+var_28.pfnFree], rax
0x180019ae9  mov     ecx, 3; dwContextType
0x180019aee  lea     rax, [rbp+var_28]
0x180019af2  mov     [rbp+var_28.cbSize], 28h ; '('
0x180019af9  mov     [rsp+70h+pCreatePara], rax; pCreatePara
0x180019afe  mov     [rsp+70h+dwFlags], r13d; dwFlags
0x180019b03  call    CertCreateContext
0x180019b08  mov     r14, rax
0x180019b0b  test    rax, rax
0x180019b0e  jz      loc_180019DBE
0x180019b14  mov     rcx, r15; hKey
0x180019b17  call    _CloseRegistryKey
0x180019b1c  test    r14, r14
0x180019b1f  jz      short loc_180019B53
0x180019b21  mov     rcx, [rbx+28h]; pCertContext
0x180019b25  test    rcx, rcx
0x180019b28  jnz     loc_180019DE9
0x180019b2e  mov     ecx, [rbx]
0x180019b30  imul    rdx, rcx, 989680h
0x180019b37  mov     [rbx+28h], r14
0x180019b3b  lea     rcx, [rbx+30h]; void **
0x180019b3f  mov     rax, qword ptr [rbp+FileTime1.dwLowDateTime]
0x180019b43  add     rdx, rax
0x180019b46  mov     [rbx+18h], rax
0x180019b4a  mov     [rbx+20h], rdx
0x180019b4e  call    ?FreeAuthRootAutoUpdateMatchCaches@@YAXQEAPEAX@Z; FreeAuthRootAutoUpdateMatchCaches(void * * const)
0x180019b53  mov     eax, [rdi+34h]
0x180019b56  mov     r9, [rdi+48h]; void *
0x180019b5a  mov     r8, [rdi+50h]; void *
0x180019b5e  mov     rdx, [rdi+70h]; hCertStore
0x180019b62  mov     rcx, [rdi+0B8h]; this
0x180019b69  mov     [rsp+70h+var_38], eax; int
0x180019b6d  mov     eax, [rdi+30h]
0x180019b70  mov     [rsp+70h+var_40], eax; int
0x180019b74  mov     rax, [rdi+348h]
0x180019b7b  mov     [rsp+70h+pCreatePara], rax; struct _CTL_CONTEXT *
0x180019b80  mov     rax, [rdi+78h]
0x180019b84  mov     qword ptr [rsp+70h+dwFlags], rax; HCERTSTORE
0x180019b89  call    ?AddKnownStores@CCertObjectCache@@QEAAHPEAX000PEBU_CTL_CONTEXT@@HH@Z; CCertObjectCache::AddKnownStores(void *,void *,void *,void *,_CTL_CONTEXT const *,int,int)
0x180019b8e  mov     rdx, [rdi+0E0h]; hSiblingStore
0x180019b95  mov     rcx, [rdi+60h]; hCollectionStore
0x180019b99  call    CertRemoveStoreFromCollection
0x180019b9e  mov     rdx, [rdi+88h]; struct _CERT_STORE *
0x180019ba5  mov     rcx, [rdi+0B8h]; this
0x180019bac  call    ?AddOcspCACerts@CCertObjectCache@@QEAAHPEAX@Z; CCertObjectCache::AddOcspCACerts(void *)
0x180019bb1  mov     rbx, [rdi+0C0h]
0x180019bb8  xor     r8d, r8d
0x180019bbb  xor     edx, edx
0x180019bbd  mov     rcx, [rbx]
0x180019bc0  call    I_CryptFlushLruCache
0x180019bc5  mov     [rbx+8], r12
0x180019bc9  mov     rcx, rdi; struct CCertChainEngine *
0x180019bcc  mov     [rbx+10h], r12d
0x180019bd0  call    ?SSCtlPopulateCacheFromCertStore@@YAHPEAVCCertChainEngine@@PEAX@Z; SSCtlPopulateCacheFromCertStore(CCertChainEngine *,void *)
0x180019bd5  mov     rdx, [rdi+88h]; struct _CERT_STORE *
0x180019bdc  lea     r9, [rdi+0D8h]; struct _XCERT_DP_LINK **
0x180019be3  mov     r8d, r13d; int
0x180019be6  mov     rcx, rdi; this
0x180019be9  call    ?GetCrossCertDistPointsForStore@CCertChainEngine@@QEAAHPEAXHPEAPEAU_XCERT_DP_LINK@@@Z; CCertChainEngine::GetCrossCertDistPointsForStore(void *,int,_XCERT_DP_LINK * *)
0x180019bee  mov     rdx, [rdi+0E0h]; hSiblingStore
0x180019bf5  xor     r9d, r9d; dwPriority
0x180019bf8  mov     rcx, [rdi+60h]; hCollectionStore
0x180019bfc  xor     r8d, r8d; dwUpdateFlags
0x180019bff  mov     ebx, eax
0x180019c01  call    CertAddStoreToCollection
0x180019c06  mov     rcx, [rsi+8]
0x180019c0a  add     [rcx+0C8h], r13d
0x180019c11  mov     ecx, [rcx+0C8h]
0x180019c17  mov     [rsi+94h], ecx
0x180019c1d  test    ebx, ebx
0x180019c1f  jnz     loc_1800198E1
0x180019c25  mov     rbx, [rsp+70h+arg_0]
0x180019c2d  mov     eax, r13d
0x180019c30  add     rsp, 70h
0x180019c34  pop     r15
0x180019c36  pop     r14
0x180019c38  pop     r13
0x180019c3a  pop     r12
0x180019c3c  pop     rdi
0x180019c3d  pop     rsi
0x180019c3e  pop     rbp
0x180019c3f  retn
0x180019c40  mov     r9, rbx; void *
0x180019c43  mov     r8d, r13d; unsigned int
0x180019c46  mov     edx, r13d; unsigned int
0x180019c49  call    ?ControlCollectionStore@@YAHPEAU_CERT_STORE@@KKPEBX@Z; ControlCollectionStore(_CERT_STORE *,ulong,ulong,void const *)
0x180019c4e  jmp     loc_1800199AC
0x180019c53  mov     ebx, 6
0x180019c58  mov     qword ptr [rbp+FileTime1.dwLowDateTime], r12
0x180019c5c  mov     edx, ebx
0x180019c5e  lea     r8, [rbp+FileTime1]
0x180019c62  mov     rcx, 0FFFFFFFF80000002h
0x180019c69  call    _GetAutoUpdateLastSyncTime
0x180019c6e  test    eax, eax
0x180019c70  jz      short loc_180019C90
0x180019c72  lea     r8, [rbp+pbEncoded]
0x180019c76  mov     [rbp+pbEncoded], r12
0x180019c7a  mov     edx, ebx
0x180019c7c  mov     rcx, 0FFFFFFFF80000001h
0x180019c83  call    _GetAutoUpdateLastSyncTime
0x180019c88  test    eax, eax
0x180019c8a  jnz     loc_180019D68
0x180019c90  cmp     [rdi+348h], r12
0x180019c97  jz      short loc_180019CB2
0x180019c99  lea     rdx, [rdi+340h]; lpFileTime2
0x180019ca0  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180019ca4  call    cs:__imp_CompareFileTime
0x180019caa  test    eax, eax
0x180019cac  jz      loc_180019A04
0x180019cb2  xorps   xmm0, xmm0
0x180019cb5  mov     [rbp+pbEncoded], r12
0x180019cb9  mov     rcx, 0FFFFFFFF80000002h
0x180019cc0  mov     [rbp+cbEncoded], r12d
0x180019cc4  movdqu  xmmword ptr [rbp+var_28.pvFree], xmm0
0x180019cc9  mov     rbx, r12
0x180019ccc  mov     dword ptr [rbp+var_28+4], r12d
0x180019cd0  mov     [rbp+var_28.pvSort], r12
0x180019cd4  call    _OpenAutoUpdateKey
0x180019cd9  mov     r14, rax
0x180019cdc  test    rax, rax
0x180019cdf  jz      short loc_180019D2F
0x180019ce1  lea     r9, [rbp+cbEncoded]
0x180019ce5  mov     rcx, rax; hKey
0x180019ce8  lea     r8, [rbp+pbEncoded]
0x180019cec  lea     rdx, aDisallowedcert_0; "DisallowedCertEncodedCtl"
0x180019cf3  call    I_CertReadBINARYValueFromRegistry
0x180019cf8  test    eax, eax
0x180019cfa  jz      short loc_180019D2F
0x180019cfc  mov     r9d, [rbp+cbEncoded]; cbEncoded
0x180019d00  lea     rax, [rbp+var_28]
0x180019d04  mov     r8, [rbp+pbEncoded]; pbEncoded
0x180019d08  mov     edx, 10001h; dwEncodingType
0x180019d0d  mov     [rsp+70h+pCreatePara], rax; pCreatePara
0x180019d12  mov     ecx, 3; dwContextType
0x180019d17  mov     [rsp+70h+dwFlags], r13d; dwFlags
0x180019d1c  mov     [rbp+var_28.cbSize], 28h ; '('
0x180019d23  mov     [rbp+var_28.pfnFree], r15
0x180019d27  call    CertCreateContext
0x180019d2c  mov     rbx, rax
0x180019d2f  mov     rcx, r14; hKey
0x180019d32  call    _CloseRegistryKey
0x180019d37  test    rbx, rbx
0x180019d3a  jz      loc_180019A04
0x180019d40  mov     rcx, [rdi+348h]; pCertContext
0x180019d47  test    rcx, rcx
0x180019d4a  jz      short loc_180019D51
0x180019d4c  call    CertFreeCertificateContext
0x180019d51  mov     rax, qword ptr [rbp+FileTime1.dwLowDateTime]
0x180019d55  mov     [rdi+340h], rax
0x180019d5c  mov     [rdi+348h], rbx
0x180019d63  jmp     loc_180019A04
0x180019d68  lea     rdx, [rbp+FileTime1]; lpFileTime2
0x180019d6c  lea     rcx, [rbp+pbEncoded]; lpFileTime1
0x180019d70  call    cs:__imp_CompareFileTime
0x180019d76  test    eax, eax
0x180019d78  jle     loc_180019C90
0x180019d7e  mov     rax, [rbp+pbEncoded]
0x180019d82  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x180019d86  jmp     loc_180019C90
0x180019d8b  lea     rdx, [rbp+FileTime1]; lpFileTime2
0x180019d8f  lea     rcx, [rbp+pbEncoded]; lpFileTime1
0x180019d93  call    cs:__imp_CompareFileTime
0x180019d99  test    eax, eax
0x180019d9b  jle     loc_180019A54
  ... truncated ...
```
