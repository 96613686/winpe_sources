# CCertChainEngine::GetAuthRootAutoUpdateCtl(CChainCallContext *,_CTL_CONTEXT const * *,_CERT_CONTEXT const *,int)

- ea: `0x18001c684`
- end: `0x18001cb76`
- name: `?GetAuthRootAutoUpdateCtl@CCertChainEngine@@QEAAHPEAVCChainCallContext@@PEAPEBU_CTL_CONTEXT@@PEBU_CERT_CONTEXT@@H@Z`
- size: `1266`
- prototype: `int(CCertChainEngine *__hidden this, struct CChainCallContext *, const struct _CTL_CONTEXT **, const struct _CERT_CONTEXT *, int)`
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001beb8`
- `0x18001bf60`
- `0x18009e0ac`

## callees

- `0x180013f5c`
- `0x18001bb3c`
- `0x18001c684`
- `0x18001cb7c`
- `0x18001ce90`
- `0x18001cedc`
- `0x18002c860`
- `0x180034270`
- `0x18003523c`
- `0x1800353c8`
- `0x180035404`
- `0x180037114`
- `0x18003a800`
- `0x18003adac`
- `0x1800450c0`
- `0x180055610`
- `0x180056d30`
- `0x1800dfa8c`
- `0x1800f3b10`
- `0x1801150c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cad1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c9da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ca20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c9da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ca20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ca36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cab6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ca36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cab6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c9a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180115ff6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c9a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180115ff6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c7a2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c7c1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c921`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c94d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001cb11`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c7a2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c7c1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c921`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c94d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001cb11`
- `ntdll!ShipAssert` at `0x18001cae0`
- `ntdll!ShipAssert` at `0x18001cae0`

## pseudocode

```c
__int64 __fastcall CCertChainEngine::GetAuthRootAutoUpdateCtl(
        CCertChainEngine *this,
        struct CChainCallContext *a2,
        const struct _CTL_CONTEXT **a3,
        const struct _CERT_CONTEXT *a4,
        int a5)
{
  struct _CRYPT_BLOB_ARRAY *v5; // r14
  struct _AUTH_ROOT_AUTO_UPDATE_INFO *v8; // rdi
  struct _AUTH_ROOT_AUTO_UPDATE_INFO *AuthRootAutoUpdateInfo; // rax
  FILETIME v11; // rax
  const CERT_CONTEXT *v12; // rsi
  unsigned int v13; // r12d
  unsigned int i; // ebx
  int updated; // eax
  const CTL_CONTEXT *v16; // rcx
  int v17; // ecx
  HKEY v18; // rax
  HKEY v19; // rbx
  struct _RTL_CRITICAL_SECTION *v20; // r12
  FILETIME *v21; // rbx
  __int64 v22; // rcx
  const CERT_CONTEXT *v23; // rcx
  const struct _CTL_CONTEXT *AutoUpdateCtlFromCab; // rax
  DWORD LastError; // eax
  DWORD cbCertEncoded; // eax
  DWORD v27; // ebx
  FILETIME v28; // rdx
  __int64 v29; // rax
  const struct _CTL_CONTEXT *AuthRootAutoUpdateCtlFromResource; // rax
  int v31; // [rsp+48h] [rbp-41h]
  unsigned int v32; // [rsp+4Ch] [rbp-3Dh]
  FILETIME FileTime1; // [rsp+50h] [rbp-39h] BYREF
  DWORD cbEncoded; // [rsp+58h] [rbp-31h]
  FILETIME FileTime2; // [rsp+60h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-21h] BYREF
  BYTE *pbEncoded; // [rsp+70h] [rbp-19h]
  FILETIME *lpFileTime2; // [rsp+78h] [rbp-11h]
  struct _CERT_CREATE_CONTEXT_PARA pCreatePara; // [rsp+80h] [rbp-9h] BYREF

  v5 = 0;
  pv = 0;
  FileTime2 = 0;
  FileTime1 = 0;
  *a3 = 0;
  if ( a5 )
  {
    if ( !*(_DWORD *)(*((_QWORD *)a2 + 1) + 64LL) )
      return 1;
  }
  else
  {
    v17 = *((_DWORD *)a2 + 35);
    if ( (v17 & 0x8000) == 0
      && (((*(_DWORD *)(*((_QWORD *)a2 + 1) + 172LL) | v17) & 0x100) != 0
       || (unsigned int)IPR_IsAuthRootAutoUpdateDisabled()) )
    {
      return 1;
    }
  }
  v8 = (struct _AUTH_ROOT_AUTO_UPDATE_INFO *)*((_QWORD *)this + 30);
  if ( !v8 )
  {
    AuthRootAutoUpdateInfo = CreateAuthRootAutoUpdateInfo();
    v8 = AuthRootAutoUpdateInfo;
    if ( !AuthRootAutoUpdateInfo )
      return 1;
    *((_QWORD *)this + 30) = AuthRootAutoUpdateInfo;
  }
  v11 = (FILETIME)*((_QWORD *)a2 + 3);
  v12 = 0;
  v31 = 1;
  FileTime1 = 0;
  v13 = 1;
  FileTime2 = v11;
  lpFileTime2 = CChainCallContext::CacheResyncFiletime(a2);
  for ( i = 0; ; ++i )
  {
    v32 = i;
    if ( i > 1 )
      break;
    if ( v12 )
    {
      CertFreeCertificateContext(v12);
      v12 = 0;
    }
    if ( *((_QWORD *)v8 + 5) && CompareFileTime((const FILETIME *)v8 + 4, &FileTime2) > 0 )
    {
      if ( lpFileTime2 && CompareFileTime((const FILETIME *)v8 + 3, lpFileTime2) < 0 )
      {
        v13 = v31;
      }
      else
      {
        v13 = v31;
        if ( CompareFileTime((const FILETIME *)v8 + 3, &FileTime2) > 0 )
        {
          v28 = FileTime2;
          v29 = *(unsigned int *)v8;
          *((FILETIME *)v8 + 3) = FileTime2;
          *((_QWORD *)v8 + 4) = *(_QWORD *)&v28 + 10000000 * v29;
        }
      }
      break;
    }
    if ( i )
    {
      updated = CCertChainEngine::WireRetrieveAutoUpdateCab(
                  this,
                  a2,
                  5u,
                  (struct _CRYPT_BLOB_ARRAY **)&pv,
                  &FileTime1,
                  a4);
      v13 = updated;
      v31 = updated;
      if ( !a5 && !updated )
      {
        v5 = (struct _CRYPT_BLOB_ARRAY *)pv;
        goto LABEL_23;
      }
      v5 = (struct _CRYPT_BLOB_ARRAY *)pv;
      if ( !pv )
        continue;
      v20 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      AutoUpdateCtlFromCab = ExtractAutoUpdateCtlFromCab(5, v5);
      v12 = (const CERT_CONTEXT *)AutoUpdateCtlFromCab;
      if ( AutoUpdateCtlFromCab )
      {
        I_CertProtectFunction(
          9,
          0,
          0,
          (__int64)AutoUpdateCtlFromCab->pbCtlEncoded,
          AutoUpdateCtlFromCab->cbCtlEncoded,
          0,
          0);
      }
      else
      {
        LastError = GetLastError();
        IPR_LogCrypt32Error(0x100Bu, *((const unsigned __int16 **)v8 + 2), LastError);
      }
      ICM_Free(v5);
      v5 = 0;
      pv = 0;
      EnterCriticalSection(v20);
      if ( !a5 && *((_DWORD *)a2 + 37) != *(_DWORD *)(*((_QWORD *)a2 + 1) + 200LL) )
      {
        v13 = 0;
        SetLastError(0x3EBu);
        goto LABEL_25;
      }
    }
    else
    {
      v12 = 0;
      pbEncoded = 0;
      cbEncoded = 0;
      memset(&pCreatePara, 0, sizeof(pCreatePara));
      I_CertGetAutoUpdateLastSyncTime(5, &FileTime1);
      v18 = (HKEY)OpenAutoUpdateKey(-2147483646);
      v19 = v18;
      if ( !v18
        || !(unsigned int)I_CertReadBINARYValueFromRegistry(v18, L"EncodedCtl")
        || (pCreatePara.pfnFree = (PFN_CRYPT_FREE)PkiDefaultCryptFree,
            pCreatePara.cbSize = 40,
            (v12 = (const CERT_CONTEXT *)CertCreateContext(3u, 0x10001u, pbEncoded, cbEncoded, 1u, &pCreatePara)) == 0) )
      {
        FileTime1 = 0;
      }
      CloseRegistryKey(v19);
      i = v32;
      v20 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
    }
    if ( v12 )
    {
      v21 = (FILETIME *)((char *)v8 + 24);
      if ( CompareFileTime(&FileTime1, (const FILETIME *)v8 + 3) > 0 )
      {
        v22 = *((_QWORD *)v8 + 5);
        if ( v22
          && (cbCertEncoded = v12->cbCertEncoded, *(_DWORD *)(v22 + 16) == cbCertEncoded)
          && !memcmp_0(*(const void **)(v22 + 8), v12->pbCertEncoded, cbCertEncoded) )
        {
          *v21 = FileTime1;
          *((_QWORD *)v8 + 4) = *(_QWORD *)&FileTime1 + 10000000LL * *(unsigned int *)v8;
        }
        else
        {
          if ( !v32 )
            goto LABEL_40;
          LeaveCriticalSection(v20);
          cbEncoded = IRL_VerifyAuthRootAutoUpdateCtl((const struct _CTL_CONTEXT *)v12, 0);
          if ( !cbEncoded )
          {
            v27 = GetLastError();
            ShipAssert(71681, v27);
            IPR_LogCrypt32Error(0x100Bu, *((const unsigned __int16 **)v8 + 2), v27);
            v21 = (FILETIME *)((char *)v8 + 24);
          }
          EnterCriticalSection(v20);
          if ( cbEncoded )
          {
LABEL_40:
            if ( CompareFileTime(&FileTime1, v21) > 0 )
            {
              *v21 = FileTime1;
              *((_QWORD *)v8 + 4) = *(_QWORD *)&FileTime1 + 10000000LL * *(unsigned int *)v8;
              FreeAuthRootAutoUpdateMatchCaches((void **const)v8 + 6);
              v23 = (const CERT_CONTEXT *)*((_QWORD *)v8 + 5);
              if ( v23 )
                CertFreeCertificateContext(v23);
              *((_QWORD *)v8 + 5) = v12;
              v12 = 0;
            }
          }
          if ( !a5 && *((_DWORD *)a2 + 37) != *(_DWORD *)(*((_QWORD *)a2 + 1) + 200LL) )
          {
            v13 = 0;
            SetLastError(0x3EBu);
            goto LABEL_23;
          }
        }
      }
      i = v32;
    }
    v13 = v31;
  }
  if ( !*((_QWORD *)v8 + 5) )
  {
    AuthRootAutoUpdateCtlFromResource = GetAuthRootAutoUpdateCtlFromResource();
    if ( AuthRootAutoUpdateCtlFromResource )
      *((_QWORD *)v8 + 5) = AuthRootAutoUpdateCtlFromResource;
  }
  v16 = (const CTL_CONTEXT *)*((_QWORD *)v8 + 5);
  if ( v16 )
    *a3 = CertDuplicateCTLContext(v16);
LABEL_23:
  if ( v5 )
    ICM_Free(v5);
LABEL_25:
  if ( v12 )
    CertFreeCertificateContext(v12);
  return v13;
}

```

## disassembly

```asm
0x18001c684  mov     rax, rsp
0x18001c687  mov     [rax+10h], rbx
0x18001c68b  mov     [rax+20h], r9
0x18001c68f  mov     [rax+18h], r8
0x18001c693  mov     [rax+8], rcx
0x18001c697  push    rbp
0x18001c698  push    rsi
0x18001c699  push    rdi
0x18001c69a  push    r12
0x18001c69c  push    r13
0x18001c69e  push    r14
0x18001c6a0  push    r15
0x18001c6a2  lea     rbp, [rax-57h]
0x18001c6a6  sub     rsp, 0A0h
0x18001c6ad  xor     r14d, r14d
0x18001c6b0  mov     r15, rdx
0x18001c6b3  mov     rbx, rcx
0x18001c6b6  mov     [rbp+4Fh+pv], r14
0x18001c6ba  mov     qword ptr [rbp+4Fh+FileTime2.dwLowDateTime], r14
0x18001c6be  mov     qword ptr [rbp+4Fh+FileTime1.dwLowDateTime], r14
0x18001c6c2  mov     [r8], r14
0x18001c6c5  cmp     [rbp+4Fh+arg_20], r14d
0x18001c6c9  jz      loc_18001C823
0x18001c6cf  mov     rax, [rdx+8]
0x18001c6d3  cmp     [rax+40h], r14d
0x18001c6d7  jz      short loc_18001C6F2
0x18001c6d9  mov     rdi, [rbx+0F0h]
0x18001c6e0  test    rdi, rdi
0x18001c6e3  jnz     short loc_18001C703
0x18001c6e5  call    ?CreateAuthRootAutoUpdateInfo@@YAPEAU_AUTH_ROOT_AUTO_UPDATE_INFO@@XZ; CreateAuthRootAutoUpdateInfo(void)
0x18001c6ea  mov     rdi, rax
0x18001c6ed  test    rax, rax
0x18001c6f0  jnz     short loc_18001C6FC
0x18001c6f2  mov     eax, 1
0x18001c6f7  jmp     loc_18001C808
0x18001c6fc  mov     [rbx+0F0h], rax
0x18001c703  mov     rax, [r15+18h]
0x18001c707  mov     r13d, 1
0x18001c70d  xor     esi, esi
0x18001c70f  mov     [rbp+4Fh+var_90], r13d
0x18001c713  mov     rcx, r15; this
0x18001c716  mov     qword ptr [rbp+4Fh+FileTime1.dwLowDateTime], rsi
0x18001c71a  mov     r12d, r13d
0x18001c71d  mov     qword ptr [rbp+4Fh+FileTime2.dwLowDateTime], rax
0x18001c721  call    ?CacheResyncFiletime@CChainCallContext@@QEAAPEAU_FILETIME@@XZ; CChainCallContext::CacheResyncFiletime(void)
0x18001c726  mov     [rbp+4Fh+lpFileTime2], rax
0x18001c72a  xor     ebx, ebx
0x18001c72c  mov     [rbp+4Fh+var_8C], ebx
0x18001c72f  cmp     ebx, r13d
0x18001c732  ja      loc_18001C7D3
0x18001c738  test    rsi, rsi
0x18001c73b  jnz     loc_18001C9E5
0x18001c741  cmp     qword ptr [rdi+28h], 0
0x18001c746  jnz     short loc_18001C79A
0x18001c748  test    ebx, ebx
0x18001c74a  jz      loc_18001C859
0x18001c750  mov     rax, [rbp+4Fh+arg_18]
0x18001c754  lea     r9, [rbp+4Fh+pv]; struct _CRYPT_BLOB_ARRAY **
0x18001c758  mov     rcx, [rbp+4Fh+arg_0]; this
0x18001c75c  mov     r8d, 5; unsigned int
0x18001c762  mov     [rsp+0D0h+pCreatePara], rax; struct _CERT_CONTEXT *
0x18001c767  mov     rdx, r15; struct CChainCallContext *
0x18001c76a  lea     rax, [rbp+4Fh+FileTime1]
0x18001c76e  mov     qword ptr [rsp+0D0h+dwFlags], rax; struct _FILETIME *
0x18001c773  call    ?WireRetrieveAutoUpdateCab@CCertChainEngine@@QEAAHPEAVCChainCallContext@@KPEAPEAU_CRYPT_BLOB_ARRAY@@PEAU_FILETIME@@PEBU_CERT_CONTEXT@@@Z; CCertChainEngine::WireRetrieveAutoUpdateCab(CChainCallContext *,ulong,_CRYPT_BLOB_ARRAY * *,_FILETIME *,_CERT_CONTEXT const *)
0x18001c778  cmp     [rbp+4Fh+arg_20], 0
0x18001c77c  mov     r12d, eax
0x18001c77f  mov     [rbp+4Fh+var_90], eax
0x18001c782  jz      loc_18001C98D
0x18001c788  mov     r14, [rbp+4Fh+pv]
0x18001c78c  test    r14, r14
0x18001c78f  jnz     loc_18001CA2B
0x18001c795  add     ebx, r13d
0x18001c798  jmp     short loc_18001C72C
0x18001c79a  lea     rdx, [rbp+4Fh+FileTime2]; lpFileTime2
0x18001c79e  lea     rcx, [rdi+20h]; lpFileTime1
0x18001c7a2  call    cs:__imp_CompareFileTime
0x18001c7a8  test    eax, eax
0x18001c7aa  jle     short loc_18001C748
0x18001c7ac  mov     rax, [rbp+4Fh+lpFileTime2]
0x18001c7b0  test    rax, rax
0x18001c7b3  jnz     loc_18001CB0A
0x18001c7b9  lea     rdx, [rbp+4Fh+FileTime2]; lpFileTime2
0x18001c7bd  lea     rcx, [rdi+18h]; lpFileTime1
0x18001c7c1  call    cs:__imp_CompareFileTime
0x18001c7c7  mov     r12d, [rbp+4Fh+var_90]
0x18001c7cb  test    eax, eax
0x18001c7cd  jg      loc_18001CB28
0x18001c7d3  cmp     qword ptr [rdi+28h], 0
0x18001c7d8  jz      loc_18001CB45
0x18001c7de  mov     rcx, [rdi+28h]; pCtlContext
0x18001c7e2  test    rcx, rcx
0x18001c7e5  jz      short loc_18001C7F3
0x18001c7e7  call    CertDuplicateCTLContext
0x18001c7ec  mov     rcx, [rbp+4Fh+arg_10]
0x18001c7f0  mov     [rcx], rax
0x18001c7f3  test    r14, r14
0x18001c7f6  jnz     loc_18001CB5C
0x18001c7fc  test    rsi, rsi
0x18001c7ff  jnz     loc_18001CB69
0x18001c805  mov     eax, r12d
0x18001c808  mov     rbx, [rsp+0D0h+arg_8]
0x18001c810  add     rsp, 0A0h
0x18001c817  pop     r15
0x18001c819  pop     r14
0x18001c81b  pop     r13
0x18001c81d  pop     r12
0x18001c81f  pop     rdi
0x18001c820  pop     rsi
0x18001c821  pop     rbp
0x18001c822  retn
0x18001c823  mov     ecx, [rdx+8Ch]
0x18001c829  bt      ecx, 0Fh
0x18001c82d  jb      loc_18001C6D9
0x18001c833  mov     rax, [rdx+8]
0x18001c837  or      ecx, [rax+0ACh]
0x18001c83d  bt      ecx, 8
0x18001c841  jb      loc_18001C6F2
0x18001c847  call    ?IPR_IsAuthRootAutoUpdateDisabled@@YAHXZ; IPR_IsAuthRootAutoUpdateDisabled(void)
0x18001c84c  test    eax, eax
0x18001c84e  jz      loc_18001C6D9
0x18001c854  jmp     loc_18001C6F2
0x18001c859  xor     esi, esi
0x18001c85b  lea     rdx, [rbp+4Fh+FileTime1]
0x18001c85f  xorps   xmm0, xmm0
0x18001c862  mov     [rbp+4Fh+pbEncoded], rsi
0x18001c866  xor     eax, eax
0x18001c868  mov     [rbp+4Fh+cbEncoded], esi
0x18001c86b  xor     r8d, r8d
0x18001c86e  mov     [rbp+4Fh+var_58.pvSort], rax
0x18001c872  lea     ecx, [rsi+5]
0x18001c875  movups  xmmword ptr [rbp+4Fh+var_58.cbSize], xmm0
0x18001c879  movups  xmmword ptr [rbp+4Fh+var_58.pvFree], xmm0
0x18001c87d  call    I_CertGetAutoUpdateLastSyncTime
0x18001c882  mov     rcx, 0FFFFFFFF80000002h
0x18001c889  call    _OpenAutoUpdateKey
0x18001c88e  mov     rbx, rax
0x18001c891  test    rax, rax
0x18001c894  jz      loc_18001C9F4
0x18001c89a  lea     r9, [rbp+4Fh+cbEncoded]
0x18001c89e  mov     rcx, rax; hKey
0x18001c8a1  lea     r8, [rbp+4Fh+pbEncoded]
0x18001c8a5  lea     rdx, aEncodedctl; "EncodedCtl"
0x18001c8ac  call    I_CertReadBINARYValueFromRegistry
0x18001c8b1  test    eax, eax
0x18001c8b3  jz      loc_18001C9F4
0x18001c8b9  mov     r9d, [rbp+4Fh+cbEncoded]; cbEncoded
0x18001c8bd  lea     rax, PkiDefaultCryptFree
0x18001c8c4  mov     r8, [rbp+4Fh+pbEncoded]; pbEncoded
0x18001c8c8  lea     ecx, [rsi+3]; dwContextType
0x18001c8cb  mov     [rbp+4Fh+var_58.pfnFree], rax
0x18001c8cf  mov     edx, 10001h; dwEncodingType
0x18001c8d4  lea     rax, [rbp+4Fh+var_58]
0x18001c8d8  mov     [rbp+4Fh+var_58.cbSize], 28h ; '('
0x18001c8df  mov     [rsp+0D0h+pCreatePara], rax; pCreatePara
0x18001c8e4  mov     [rsp+0D0h+dwFlags], r13d; dwFlags
0x18001c8e9  call    CertCreateContext
0x18001c8ee  mov     rsi, rax
0x18001c8f1  test    rax, rax
0x18001c8f4  jz      loc_18001C9F4
0x18001c8fa  mov     rcx, rbx; hKey
0x18001c8fd  call    _CloseRegistryKey
0x18001c902  mov     r12, [rbp+4Fh+arg_0]
0x18001c906  mov     ebx, [rbp+4Fh+var_8C]
0x18001c909  add     r12, 8
0x18001c90d  test    rsi, rsi
0x18001c910  jz      loc_18001C9C9
0x18001c916  lea     rbx, [rdi+18h]
0x18001c91a  mov     rdx, rbx; lpFileTime2
0x18001c91d  lea     rcx, [rbp+4Fh+FileTime1]; lpFileTime1
0x18001c921  call    cs:__imp_CompareFileTime
0x18001c927  test    eax, eax
0x18001c929  jle     loc_18001C9C6
0x18001c92f  mov     rcx, [rdi+28h]
0x18001c933  test    rcx, rcx
0x18001c936  jnz     loc_18001CA72
0x18001c93c  cmp     [rbp+4Fh+var_8C], 0
0x18001c940  jnz     loc_18001CAB3
0x18001c946  mov     rdx, rbx; lpFileTime2
0x18001c949  lea     rcx, [rbp+4Fh+FileTime1]; lpFileTime1
0x18001c94d  call    cs:__imp_CompareFileTime
0x18001c953  test    eax, eax
0x18001c955  jle     short loc_18001C9AD
0x18001c957  mov     rax, qword ptr [rbp+4Fh+FileTime1.dwLowDateTime]
0x18001c95b  mov     [rbx], rax
0x18001c95e  mov     eax, [rdi]
0x18001c960  imul    rcx, rax, 989680h
0x18001c967  add     rcx, qword ptr [rbp+4Fh+FileTime1.dwLowDateTime]
0x18001c96b  mov     [rdi+20h], rcx
0x18001c96f  lea     rcx, [rdi+30h]; void **
0x18001c973  call    ?FreeAuthRootAutoUpdateMatchCaches@@YAXQEAPEAX@Z; FreeAuthRootAutoUpdateMatchCaches(void * * const)
0x18001c978  mov     rcx, [rdi+28h]; pCertContext
0x18001c97c  test    rcx, rcx
0x18001c97f  jnz     loc_18001CB00
0x18001c985  mov     [rdi+28h], rsi
0x18001c989  xor     esi, esi
0x18001c98b  jmp     short loc_18001C9AD
0x18001c98d  test    eax, eax
0x18001c98f  jnz     loc_18001C788
0x18001c995  mov     r14, [rbp+4Fh+pv]
0x18001c999  jmp     loc_18001C7F3
0x18001c99e  mov     rcx, r12; lpCriticalSection
0x18001c9a1  call    cs:__imp_EnterCriticalSection
0x18001c9a7  cmp     [rbp+4Fh+cbEncoded], 0
0x18001c9ab  jnz     short loc_18001C946
0x18001c9ad  cmp     [rbp+4Fh+arg_20], 0
0x18001c9b1  jnz     short loc_18001C9C6
0x18001c9b3  mov     rax, [r15+8]
0x18001c9b7  mov     ecx, [rax+0C8h]
0x18001c9bd  cmp     [r15+94h], ecx
0x18001c9c4  jnz     short loc_18001C9D2
0x18001c9c6  mov     ebx, [rbp+4Fh+var_8C]
0x18001c9c9  mov     r12d, [rbp+4Fh+var_90]
0x18001c9cd  jmp     loc_18001C795
0x18001c9d2  xor     r12d, r12d
0x18001c9d5  mov     ecx, 3EBh; dwErrCode
0x18001c9da  call    cs:__imp_SetLastError
0x18001c9e0  jmp     loc_18001C7F3
0x18001c9e5  mov     rcx, rsi; pCertContext
0x18001c9e8  call    CertFreeCertificateContext
0x18001c9ed  xor     esi, esi
0x18001c9ef  jmp     loc_18001C741
0x18001c9f4  mov     qword ptr [rbp+4Fh+FileTime1.dwLowDateTime], 0
0x18001c9fc  jmp     loc_18001C8FA
0x18001ca01  mov     rax, [r15+8]
0x18001ca05  mov     ecx, [rax+0C8h]
0x18001ca0b  cmp     [r15+94h], ecx
0x18001ca12  jz      loc_18001C90D
0x18001ca18  xor     r12d, r12d
0x18001ca1b  mov     ecx, 3EBh; dwErrCode
0x18001ca20  call    cs:__imp_SetLastError
0x18001ca26  jmp     loc_18001C7FC
0x18001ca2b  mov     r12, [rbp+4Fh+arg_0]
0x18001ca2f  add     r12, 8
0x18001ca33  mov     rcx, r12; lpCriticalSection
0x18001ca36  call    cs:__imp_LeaveCriticalSection
0x18001ca3c  mov     rdx, r14; struct _CRYPT_BLOB_ARRAY *
0x18001ca3f  mov     ecx, 5; unsigned int
0x18001ca44  call    ?ExtractAutoUpdateCtlFromCab@@YAPEBU_CTL_CONTEXT@@KPEAU_CRYPT_BLOB_ARRAY@@@Z; ExtractAutoUpdateCtlFromCab(ulong,_CRYPT_BLOB_ARRAY *)
0x18001ca49  mov     rsi, rax
0x18001ca4c  test    rax, rax
0x18001ca4f  jnz     loc_180115FBA
0x18001ca55  call    cs:__imp_GetLastError
0x18001ca5b  mov     rdx, [rdi+10h]; unsigned __int16 *
0x18001ca5f  mov     ecx, 100Bh; unsigned int
0x18001ca64  mov     r8d, eax; unsigned int
0x18001ca67  call    ?IPR_LogCrypt32Error@@YAXKPEBGK@Z; IPR_LogCrypt32Error(ulong,ushort const *,ulong)
0x18001ca6c  nop
0x18001ca6d  jmp     loc_180115FE4
0x18001ca72  mov     eax, [rsi+10h]
0x18001ca75  cmp     [rcx+10h], eax
0x18001ca78  jnz     loc_18001C93C
0x18001ca7e  mov     rdx, [rsi+8]; Buf2
0x18001ca82  mov     r8d, eax; Size
0x18001ca85  mov     rcx, [rcx+8]; Buf1
0x18001ca89  call    memcmp_0
0x18001ca8e  test    eax, eax
0x18001ca90  jnz     loc_18001C93C
0x18001ca96  mov     rax, qword ptr [rbp+4Fh+FileTime1.dwLowDateTime]
0x18001ca9a  mov     [rbx], rax
0x18001ca9d  mov     eax, [rdi]
0x18001ca9f  imul    rcx, rax, 989680h
0x18001caa6  add     rcx, qword ptr [rbp+4Fh+FileTime1.dwLowDateTime]
0x18001caaa  mov     [rdi+20h], rcx
0x18001caae  jmp     loc_18001C9C6
0x18001cab3  mov     rcx, r12; lpCriticalSection
0x18001cab6  call    cs:__imp_LeaveCriticalSection
0x18001cabc  xor     edx, edx; int
0x18001cabe  mov     rcx, rsi; struct _CTL_CONTEXT *
0x18001cac1  call    ?IRL_VerifyAuthRootAutoUpdateCtl@@YAHPEBU_CTL_CONTEXT@@H@Z; IRL_VerifyAuthRootAutoUpdateCtl(_CTL_CONTEXT const *,int)
0x18001cac6  mov     [rbp+4Fh+cbEncoded], eax
0x18001cac9  test    eax, eax
0x18001cacb  jnz     loc_18001C99E
0x18001cad1  call    cs:__imp_GetLastError
0x18001cad7  mov     edx, eax
0x18001cad9  mov     ecx, 11801h
0x18001cade  mov     ebx, eax
0x18001cae0  call    cs:__imp_ShipAssert
0x18001cae6  mov     rdx, [rdi+10h]; unsigned __int16 *
0x18001caea  mov     r8d, ebx; unsigned int
0x18001caed  mov     ecx, 100Bh; unsigned int
0x18001caf2  call    ?IPR_LogCrypt32Error@@YAXKPEBGK@Z; IPR_LogCrypt32Error(ulong,ushort const *,ulong)
0x18001caf7  lea     rbx, [rdi+18h]
0x18001cafb  jmp     loc_18001C99E
0x18001cb00  call    CertFreeCertificateContext
0x18001cb05  jmp     loc_18001C985
0x18001cb0a  lea     rcx, [rdi+18h]; lpFileTime1
0x18001cb0e  mov     rdx, rax; lpFileTime2
0x18001cb11  call    cs:__imp_CompareFileTime
0x18001cb17  test    eax, eax
0x18001cb19  jns     loc_18001C7B9
0x18001cb1f  mov     r12d, [rbp+4Fh+var_90]
0x18001cb23  jmp     loc_18001C7D3
0x18001cb28  mov     rdx, qword ptr [rbp+4Fh+FileTime2.dwLowDateTime]
0x18001cb2c  mov     eax, [rdi]
0x18001cb2e  imul    rcx, rax, 989680h
0x18001cb35  mov     [rdi+18h], rdx
0x18001cb39  add     rcx, rdx
0x18001cb3c  mov     [rdi+20h], rcx
0x18001cb40  jmp     loc_18001C7D3
  ... truncated ...
```
