# CCertChainEngine::GetTimeValidDisallowedCertAutoUpdateCtl(CChainCallContext *,_CERT_CONTEXT const *)

- ea: `0x18008dfa0`
- end: `0x18008e369`
- name: `?GetTimeValidDisallowedCertAutoUpdateCtl@CCertChainEngine@@QEAAXPEAVCChainCallContext@@PEBU_CERT_CONTEXT@@@Z`
- size: `969`
- prototype: `void __fastcall(CCertChainEngine *__hidden this, struct CChainCallContext *, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b9604`

## callees

- `0x1800198a0`
- `0x18001cb7c`
- `0x18002c860`
- `0x180034270`
- `0x18003523c`
- `0x1800352b8`
- `0x1800353c8`
- `0x180035404`
- `0x180036dfc`
- `0x180037114`
- `0x1800450c0`
- `0x180056de0`
- `0x18008dfa0`
- `0x18008e370`
- `0x18008e3f8`
- `0x1801150c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e004`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e186`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e004`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e186`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008dfeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008e1c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008dfeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008e1c3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008e048`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008e06f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008e09a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008e138`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008e299`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008e048`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008e06f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008e09a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008e138`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008e299`

## pseudocode

```c
void __fastcall CCertChainEngine::GetTimeValidDisallowedCertAutoUpdateCtl(
        FILETIME *this,
        FILETIME *a2,
        struct _CERT_CONTEXT *a3)
{
  int dwHighDateTime; // r12d
  BYTE *v6; // r13
  const CERT_CONTEXT *AutoUpdateCtl; // rdi
  DWORD dwLowDateTime; // r15d
  FILETIME *v9; // r14
  unsigned __int64 v10; // rdx
  struct _FILETIME *v11; // rdx
  HKEY updated; // rax
  HKEY v13; // r15
  const CERT_CONTEXT *v14; // r15
  int v15; // ecx
  FILETIME FileTime2; // [rsp+40h] [rbp-39h] BYREF
  FILETIME FileTime1; // [rsp+48h] [rbp-31h] BYREF
  BYTE *pbEncoded; // [rsp+50h] [rbp-29h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-21h]
  struct _CERT_CREATE_CONTEXT_PARA pCreatePara; // [rsp+60h] [rbp-19h] BYREF
  FILETIME cbEncoded; // [rsp+E0h] [rbp+67h] BYREF
  int v22; // [rsp+E8h] [rbp+6Fh]
  struct _CERT_CONTEXT *v23; // [rsp+F0h] [rbp+77h]
  FILETIME v24; // [rsp+F8h] [rbp+7Fh] BYREF

  v23 = a3;
  dwHighDateTime = a2[17].dwHighDateTime;
  lpCriticalSection = (LPCRITICAL_SECTION)&this[1];
  FileTime2 = 0;
  FileTime1 = 0;
  v24 = 0;
  v6 = 0;
  pbEncoded = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)&this[1]);
  if ( !this[8].dwLowDateTime || (dwHighDateTime & 0x70000000) == 0 )
    goto LABEL_3;
  AutoUpdateCtl = 0;
  dwLowDateTime = this[99].dwLowDateTime;
  if ( a2[12].dwHighDateTime && a2[13].dwLowDateTime < dwLowDateTime )
    dwLowDateTime = a2[13].dwLowDateTime;
  v9 = this + 104;
  FileTime2 = a2[3];
  if ( CompareFileTime(this + 104, &FileTime2) > 0 )
    *v9 = FileTime2;
  FileTime1 = (FILETIME)(*(_QWORD *)v9 + 10000000LL * dwLowDateTime);
  if ( CompareFileTime(&FileTime1, &FileTime2) > 0 )
    goto LABEL_8;
  if ( dwHighDateTime < 0 || (int)GetOfflineUrlTimeStatus((struct _OFFLINE_URL_TIME_INFO *)&this[106]) < 0 )
    goto LABEL_9;
  if ( (unsigned int)GetAutoUpdateLastSyncTime(-2147483646, 6, &v24) )
  {
    cbEncoded = 0;
    if ( (unsigned int)GetAutoUpdateLastSyncTime(-2147483647, 6, &cbEncoded) )
    {
      if ( CompareFileTime(&cbEncoded, &v24) > 0 )
        v24 = cbEncoded;
    }
  }
  if ( CompareFileTime(&v24, this + 104) > 0 )
  {
    v22 = 1;
    AutoUpdateCtl = (const CERT_CONTEXT *)I_CertGetAutoUpdateCtl(6, &v24);
    if ( AutoUpdateCtl )
      goto LABEL_33;
  }
  CCertChainEngine::WireRetrieveAutoUpdateCab(
    (CCertChainEngine *)this,
    (struct CChainCallContext *)a2,
    6u,
    (struct _CRYPT_BLOB_ARRAY **)&pbEncoded,
    &v24,
    v23);
  v6 = pbEncoded;
  if ( pbEncoded )
  {
    if ( *(_DWORD *)pbEncoded )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)&this[1]);
      v22 = I_CertCltProtectFunction(13, 6, 0, *(_QWORD *)(*((_QWORD *)v6 + 1) + 8LL), **((_DWORD **)v6 + 1), 0, 0);
      EnterCriticalSection((LPCRITICAL_SECTION)&this[1]);
      AutoUpdateCtl = 0;
      pbEncoded = 0;
      cbEncoded.dwLowDateTime = 0;
      *(&pCreatePara.cbSize + 1) = 0;
      memset(&pCreatePara.pvFree, 0, 24);
      I_CertGetAutoUpdateLastSyncTime(6, &v24);
      updated = (HKEY)OpenAutoUpdateKey(-2147483646);
      v13 = updated;
      if ( !updated
        || !(unsigned int)I_CertReadBINARYValueFromRegistry(updated, L"DisallowedCertEncodedCtl")
        || (pCreatePara.pfnFree = (PFN_CRYPT_FREE)PkiDefaultCryptFree,
            pCreatePara.cbSize = 40,
            (AutoUpdateCtl = (const CERT_CONTEXT *)CertCreateContext(
                                                     3u,
                                                     0x10001u,
                                                     pbEncoded,
                                                     cbEncoded.dwLowDateTime,
                                                     1u,
                                                     &pCreatePara)) == 0) )
      {
        v24 = 0;
      }
      CloseRegistryKey(v13);
      if ( AutoUpdateCtl )
      {
LABEL_33:
        v14 = (const CERT_CONTEXT *)this[105];
        if ( v14
          && AutoUpdateCtl->cbCertEncoded == v14->cbCertEncoded
          && !memcmp_0(AutoUpdateCtl->pbCertEncoded, v14->pbCertEncoded, AutoUpdateCtl->cbCertEncoded) )
        {
          v15 = 0;
          if ( !v22 )
            goto LABEL_26;
        }
        else
        {
          v15 = 1;
        }
        *v9 = v24;
        this[106].dwLowDateTime = 0;
        if ( v15 )
        {
          if ( v14 )
            CertFreeCertificateContext(v14);
          this[105] = (FILETIME)AutoUpdateCtl;
          AutoUpdateCtl = 0;
          CCertChainEngine::Resync((CCertChainEngine *)this, (struct CChainCallContext *)a2, 1);
        }
LABEL_8:
        a2[18].dwLowDateTime |= 0x1000u;
        goto LABEL_9;
      }
    }
  }
LABEL_26:
  SetOfflineUrlTime((struct _OFFLINE_URL_TIME_INFO *)&this[106], v11);
LABEL_9:
  if ( v9->dwLowDateTime || this[104].dwHighDateTime )
  {
    a2[18].dwLowDateTime |= 0x2000u;
    if ( CompareFileTime(a2 + 3, this + 104) <= 0 )
      LODWORD(v10) = 0;
    else
      v10 = (*(_QWORD *)&a2[3] - *(_QWORD *)v9) / 0x989680uLL;
    a2[25].dwLowDateTime = v10;
  }
  if ( v6 )
    ICM_Free(v6);
  if ( AutoUpdateCtl )
    CertFreeCertificateContext(AutoUpdateCtl);
LABEL_3:
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18008dfa0  mov     [rsp-8+arg_10], r8
0x18008dfa5  push    rbp
0x18008dfa6  push    rbx
0x18008dfa7  push    rsi
0x18008dfa8  push    rdi
0x18008dfa9  push    r12
0x18008dfab  push    r13
0x18008dfad  push    r14
0x18008dfaf  push    r15
0x18008dfb1  lea     rbp, [rsp-1Fh]
0x18008dfb6  sub     rsp, 98h
0x18008dfbd  mov     r12d, [rdx+8Ch]
0x18008dfc4  lea     rax, [rcx+8]
0x18008dfc8  xor     r14d, r14d
0x18008dfcb  mov     [rbp+57h+lpCriticalSection], rax
0x18008dfcf  mov     rsi, rcx
0x18008dfd2  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], r14
0x18008dfd6  mov     rcx, rax; lpCriticalSection
0x18008dfd9  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], r14
0x18008dfdd  mov     rbx, rdx
0x18008dfe0  mov     qword ptr [rbp+57h+arg_18.dwLowDateTime], r14
0x18008dfe4  mov     r13d, r14d
0x18008dfe7  mov     [rbp+57h+pbEncoded], r14
0x18008dfeb  call    cs:__imp_EnterCriticalSection
0x18008dff1  cmp     [rsi+40h], r14d
0x18008dff5  jz      short loc_18008E000
0x18008dff7  test    r12d, 70000000h
0x18008dffe  jnz     short loc_18008E01E
0x18008e000  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18008e004  call    cs:__imp_LeaveCriticalSection
0x18008e00a  add     rsp, 98h
0x18008e011  pop     r15
0x18008e013  pop     r14
0x18008e015  pop     r13
0x18008e017  pop     r12
0x18008e019  pop     rdi
0x18008e01a  pop     rsi
0x18008e01b  pop     rbx
0x18008e01c  pop     rbp
0x18008e01d  retn
0x18008e01e  mov     rdi, r14
0x18008e021  mov     r15d, [rsi+318h]
0x18008e028  cmp     [rbx+64h], r14d
0x18008e02c  jnz     loc_18008E33E
0x18008e032  mov     rax, [rbx+18h]
0x18008e036  lea     r14, [rsi+340h]
0x18008e03d  mov     rcx, r14; lpFileTime1
0x18008e040  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], rax
0x18008e044  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x18008e048  call    cs:__imp_CompareFileTime
0x18008e04e  test    eax, eax
0x18008e050  jg      loc_18008E2B4
0x18008e056  mov     eax, r15d
0x18008e059  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x18008e05d  imul    rcx, rax, 989680h
0x18008e064  add     rcx, [r14]
0x18008e067  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], rcx
0x18008e06b  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x18008e06f  call    cs:__imp_CompareFileTime
0x18008e075  test    eax, eax
0x18008e077  jle     short loc_18008E0DD
0x18008e079  bts     dword ptr [rbx+90h], 0Ch
0x18008e081  cmp     dword ptr [r14], 0
0x18008e085  jz      loc_18008E281
0x18008e08b  bts     dword ptr [rbx+90h], 0Dh
0x18008e093  lea     rcx, [rbx+18h]; lpFileTime1
0x18008e097  mov     rdx, r14; lpFileTime2
0x18008e09a  call    cs:__imp_CompareFileTime
0x18008e0a0  test    eax, eax
0x18008e0a2  jle     loc_18008E362
0x18008e0a8  mov     rdx, [rbx+18h]
0x18008e0ac  mov     rax, 0D6BF94D5E57A42BDh
0x18008e0b6  sub     rdx, [r14]
0x18008e0b9  mul     rdx
0x18008e0bc  shr     rdx, 17h
0x18008e0c0  mov     [rbx+0C8h], edx
0x18008e0c6  test    r13, r13
0x18008e0c9  jz      loc_18011BFEA
0x18008e0cf  mov     rcx, r13; pv
0x18008e0d2  call    ?ICM_Free@@YAXPEAX@Z; ICM_Free(void *)
0x18008e0d7  nop
0x18008e0d8  jmp     loc_18011BFEA
0x18008e0dd  test    r12d, r12d
0x18008e0e0  js      short loc_18008E081
0x18008e0e2  lea     r12, [rsi+350h]
0x18008e0e9  mov     rcx, r12; struct _OFFLINE_URL_TIME_INFO *
0x18008e0ec  call    ?GetOfflineUrlTimeStatus@@YAJPEAU_OFFLINE_URL_TIME_INFO@@@Z; GetOfflineUrlTimeStatus(_OFFLINE_URL_TIME_INFO *)
0x18008e0f1  test    eax, eax
0x18008e0f3  js      short loc_18008E081
0x18008e0f5  mov     r15d, 6
0x18008e0fb  lea     r8, [rbp+57h+arg_18]
0x18008e0ff  mov     edx, r15d
0x18008e102  mov     rcx, 0FFFFFFFF80000002h
0x18008e109  call    _GetAutoUpdateLastSyncTime
0x18008e10e  test    eax, eax
0x18008e110  jz      short loc_18008E131
0x18008e112  lea     r8, [rbp+57h+cbEncoded]
0x18008e116  mov     [rbp+57h+cbEncoded], rdi
0x18008e11a  mov     edx, r15d
0x18008e11d  mov     rcx, 0FFFFFFFF80000001h
0x18008e124  call    _GetAutoUpdateLastSyncTime
0x18008e129  test    eax, eax
0x18008e12b  jnz     loc_18008E291
0x18008e131  mov     rdx, r14; lpFileTime2
0x18008e134  lea     rcx, [rbp+57h+arg_18]; lpFileTime1
0x18008e138  call    cs:__imp_CompareFileTime
0x18008e13e  test    eax, eax
0x18008e140  jg      loc_18008E2CA
0x18008e146  mov     rax, [rbp+57h+arg_10]
0x18008e14a  lea     r9, [rbp+57h+pbEncoded]; struct _CRYPT_BLOB_ARRAY **
0x18008e14e  mov     [rsp+0D0h+pCreatePara], rax; struct _CERT_CONTEXT *
0x18008e153  mov     r8d, r15d; unsigned int
0x18008e156  lea     rax, [rbp+57h+arg_18]
0x18008e15a  mov     rdx, rbx; struct CChainCallContext *
0x18008e15d  mov     rcx, rsi; this
0x18008e160  mov     qword ptr [rsp+0D0h+dwFlags], rax; struct _FILETIME *
0x18008e165  call    ?WireRetrieveAutoUpdateCab@CCertChainEngine@@QEAAHPEAVCChainCallContext@@KPEAPEAU_CRYPT_BLOB_ARRAY@@PEAU_FILETIME@@PEBU_CERT_CONTEXT@@@Z; CCertChainEngine::WireRetrieveAutoUpdateCab(CChainCallContext *,ulong,_CRYPT_BLOB_ARRAY * *,_FILETIME *,_CERT_CONTEXT const *)
0x18008e16a  mov     r13, [rbp+57h+pbEncoded]
0x18008e16e  test    r13, r13
0x18008e171  jz      loc_18008E274
0x18008e177  cmp     dword ptr [r13+0], 0
0x18008e17c  jz      loc_18008E274
0x18008e182  lea     rcx, [rsi+8]; lpCriticalSection
0x18008e186  call    cs:__imp_LeaveCriticalSection
0x18008e18c  mov     r9, [r13+8]
0x18008e190  xor     r8d, r8d
0x18008e193  mov     [rsp+0D0h+var_A0], 0
0x18008e19c  mov     edx, r15d
0x18008e19f  mov     [rsp+0D0h+pCreatePara], 0
0x18008e1a8  mov     eax, [r9]
0x18008e1ab  lea     ecx, [r8+0Dh]
0x18008e1af  mov     r9, [r9+8]
0x18008e1b3  mov     [rsp+0D0h+dwFlags], eax
0x18008e1b7  call    I_CertCltProtectFunction
0x18008e1bc  lea     rcx, [rsi+8]; lpCriticalSection
0x18008e1c0  mov     [rbp+57h+arg_8], eax
0x18008e1c3  call    cs:__imp_EnterCriticalSection
0x18008e1c9  xor     edi, edi
0x18008e1cb  lea     rdx, [rbp+57h+arg_18]
0x18008e1cf  xorps   xmm0, xmm0
0x18008e1d2  mov     [rbp+57h+pbEncoded], rdi
0x18008e1d6  xor     r8d, r8d
0x18008e1d9  mov     dword ptr [rbp+57h+cbEncoded], edi
0x18008e1dc  mov     ecx, r15d
0x18008e1df  mov     dword ptr [rbp+57h+var_70+4], edi
0x18008e1e2  movdqu  xmmword ptr [rbp+57h+var_70.pvFree], xmm0
0x18008e1e7  mov     [rbp+57h+var_70.pvSort], rdi
0x18008e1eb  call    I_CertGetAutoUpdateLastSyncTime
0x18008e1f0  mov     rcx, 0FFFFFFFF80000002h
0x18008e1f7  call    _OpenAutoUpdateKey
0x18008e1fc  mov     r15, rax
0x18008e1ff  test    rax, rax
0x18008e202  jz      loc_18008E2C0
0x18008e208  lea     r9, [rbp+57h+cbEncoded]
0x18008e20c  mov     rcx, rax; hKey
0x18008e20f  lea     r8, [rbp+57h+pbEncoded]
0x18008e213  lea     rdx, aDisallowedcert_0; "DisallowedCertEncodedCtl"
0x18008e21a  call    I_CertReadBINARYValueFromRegistry
0x18008e21f  test    eax, eax
0x18008e221  jz      loc_18008E2C0
0x18008e227  mov     r9d, dword ptr [rbp+57h+cbEncoded]; cbEncoded
0x18008e22b  lea     rax, PkiDefaultCryptFree
0x18008e232  mov     r8, [rbp+57h+pbEncoded]; pbEncoded
0x18008e236  lea     ecx, [rdi+3]; dwContextType
0x18008e239  mov     [rbp+57h+var_70.pfnFree], rax
0x18008e23d  mov     edx, 10001h; dwEncodingType
0x18008e242  lea     rax, [rbp+57h+var_70]
0x18008e246  mov     [rbp+57h+var_70.cbSize], 28h ; '('
0x18008e24d  mov     [rsp+0D0h+pCreatePara], rax; pCreatePara
0x18008e252  mov     [rsp+0D0h+dwFlags], 1; dwFlags
0x18008e25a  call    CertCreateContext
0x18008e25f  mov     rdi, rax
0x18008e262  test    rax, rax
0x18008e265  jz      short loc_18008E2C0
0x18008e267  mov     rcx, r15; hKey
0x18008e26a  call    _CloseRegistryKey
0x18008e26f  test    rdi, rdi
0x18008e272  jnz     short loc_18008E2E9
0x18008e274  mov     rcx, r12; struct _OFFLINE_URL_TIME_INFO *
0x18008e277  call    ?SetOfflineUrlTime@@YAXPEAU_OFFLINE_URL_TIME_INFO@@PEAU_FILETIME@@@Z; SetOfflineUrlTime(_OFFLINE_URL_TIME_INFO *,_FILETIME *)
0x18008e27c  jmp     loc_18008E081
0x18008e281  cmp     dword ptr [r14+4], 0
0x18008e286  jnz     loc_18008E08B
0x18008e28c  jmp     loc_18008E0C6
0x18008e291  lea     rdx, [rbp+57h+arg_18]; lpFileTime2
0x18008e295  lea     rcx, [rbp+57h+cbEncoded]; lpFileTime1
0x18008e299  call    cs:__imp_CompareFileTime
0x18008e29f  test    eax, eax
0x18008e2a1  jle     loc_18008E131
0x18008e2a7  mov     rax, [rbp+57h+cbEncoded]
0x18008e2ab  mov     qword ptr [rbp+57h+arg_18.dwLowDateTime], rax
0x18008e2af  jmp     loc_18008E131
0x18008e2b4  mov     rax, qword ptr [rbp+57h+FileTime2.dwLowDateTime]
0x18008e2b8  mov     [r14], rax
0x18008e2bb  jmp     loc_18008E056
0x18008e2c0  mov     qword ptr [rbp+57h+arg_18.dwLowDateTime], 0
0x18008e2c8  jmp     short loc_18008E267
0x18008e2ca  lea     rdx, [rbp+57h+arg_18]
0x18008e2ce  mov     [rbp+57h+arg_8], 1
0x18008e2d5  mov     ecx, r15d
0x18008e2d8  call    I_CertGetAutoUpdateCtl
0x18008e2dd  mov     rdi, rax
0x18008e2e0  test    rax, rax
0x18008e2e3  jz      loc_18008E146
0x18008e2e9  mov     r15, [rsi+348h]
0x18008e2f0  test    r15, r15
0x18008e2f3  jz      short loc_18008E2FE
0x18008e2f5  mov     eax, [rdi+10h]
0x18008e2f8  cmp     eax, [r15+10h]
0x18008e2fc  jz      short loc_18008E34C
0x18008e2fe  mov     ecx, 1
0x18008e303  mov     rax, qword ptr [rbp+57h+arg_18.dwLowDateTime]
0x18008e307  mov     [r14], rax
0x18008e30a  mov     dword ptr [r12], 0
0x18008e312  test    ecx, ecx
0x18008e314  jz      loc_18008E079
0x18008e31a  test    r15, r15
0x18008e31d  jz      loc_18011BFCC
0x18008e323  mov     rcx, r15; pCertContext
0x18008e326  call    CertFreeCertificateContext
0x18008e32b  nop
0x18008e32c  jmp     loc_18011BFCC
0x18008e331  xor     ecx, ecx
0x18008e333  cmp     [rbp+57h+arg_8], ecx
0x18008e336  jz      loc_18008E274
0x18008e33c  jmp     short loc_18008E303
0x18008e33e  cmp     [rbx+68h], r15d
0x18008e342  cmovb   r15d, [rbx+68h]
0x18008e347  jmp     loc_18008E032
0x18008e34c  mov     rdx, [r15+8]; Buf2
0x18008e350  mov     r8, rax; Size
0x18008e353  mov     rcx, [rdi+8]; Buf1
0x18008e357  call    memcmp_0
0x18008e35c  test    eax, eax
0x18008e35e  jnz     short loc_18008E2FE
0x18008e360  jmp     short loc_18008E331
0x18008e362  xor     edx, edx
0x18008e364  jmp     loc_18008E0C0
0x18011bfcc  mov     [rsi+348h], rdi
0x18011bfd3  mov     rdx, rbx; struct CChainCallContext *
0x18011bfd6  xor     edi, edi
0x18011bfd8  mov     rcx, rsi; this
0x18011bfdb  lea     r8d, [rdi+1]; int
0x18011bfdf  call    ?Resync@CCertChainEngine@@QEAAHPEAVCChainCallContext@@H@Z; CCertChainEngine::Resync(CChainCallContext *,int)
0x18011bfe4  nop
0x18011bfe5  jmp     loc_18008E079
0x18011bfea  test    rdi, rdi
0x18011bfed  jz      loc_18008E000
0x18011bff3  mov     rcx, rdi; pCertContext
0x18011bff6  call    CertFreeCertificateContext
0x18011bffb  nop
0x18011bffc  jmp     loc_18008E000
```
