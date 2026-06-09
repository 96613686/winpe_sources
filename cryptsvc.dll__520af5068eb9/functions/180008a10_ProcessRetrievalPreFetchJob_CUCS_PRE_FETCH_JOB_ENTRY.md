# ProcessRetrievalPreFetchJob(_CUCS_PRE_FETCH_JOB_ENTRY *)

- ea: `0x180008a10`
- end: `0x180008db8`
- name: `?ProcessRetrievalPreFetchJob@@YAXPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@@Z`
- size: `936`
- prototype: `void __fastcall(struct _CUCS_PRE_FETCH_JOB_ENTRY *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000f950`

## callees

- `0x180002220`
- `0x180004180`
- `0x180007980`
- `0x180008a10`
- `0x180009388`
- `0x180009790`
- `0x1800097e0`
- `0x18000ec40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d3d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008a86`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008a86`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008aaa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008aaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008a6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008a6e`
- `CRYPT32!CryptMemFree` at `0x180008c62`
- `CRYPT32!CryptMemFree` at `0x180008cdf`
- `CRYPT32!CryptMemFree` at `0x180008d9f`
- `CRYPT32!CryptMemFree` at `0x180008dad`
- `CRYPT32!CryptMemFree` at `0x180008c62`
- `CRYPT32!CryptMemFree` at `0x180008cdf`
- `CRYPT32!CryptMemFree` at `0x180008d9f`
- `CRYPT32!CryptMemFree` at `0x180008dad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008b62`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008b62`
- `CRYPTNET!CryptRetrieveObjectByUrlW` at `0x180008bc8`
- `CRYPTNET!CryptRetrieveObjectByUrlW` at `0x180008bc8`

## pseudocode

```c
void __fastcall ProcessRetrievalPreFetchJob(struct _CUCS_PRE_FETCH_JOB_ENTRY *a1)
{
  int v2; // r15d
  void **v3; // rax
  void *v4; // rdi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *v7; // r14
  int v8; // edi
  int v9; // eax
  DWORD v10; // esi
  LPWSTR *ppwszErrorResponseHeaders; // rax
  unsigned int v12; // edi
  _QWORD *v13; // rdi
  void *v14; // rcx
  DWORD v15; // esi
  DWORD v16; // ecx
  void *v17; // rcx
  int v18; // eax
  unsigned int v19; // r12d
  __int64 v20; // rdi
  int v21; // eax
  __int64 v22; // [rsp+58h] [rbp-59h] BYREF
  _CRYPT_RETRIEVE_AUX_INFO pAuxInfo; // [rsp+68h] [rbp-49h] BYREF
  void *TokenHandle; // [rsp+118h] [rbp+67h] BYREF
  LPVOID pv; // [rsp+120h] [rbp+6Fh] BYREF
  LPVOID v26; // [rsp+128h] [rbp+77h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+130h] [rbp+7Fh] BYREF

  v2 = 0;
  memset_0(&pAuxInfo, 0, sizeof(pAuxInfo));
  v3 = (void **)*((_QWORD *)a1 + 16);
  v22 = 0;
  pv = 0;
  v26 = 0;
  if ( !v3 )
  {
    v7 = 0;
    v16 = 1008;
LABEL_21:
    SetLastError(v16);
    goto LABEL_33;
  }
  v4 = *v3;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    TokenHandle = 0;
    if ( LastError != 1008 )
      goto LABEL_47;
  }
  if ( !SetThreadToken(0, v4) )
  {
    LastError = GetLastError();
LABEL_47:
    SetLastError(LastError);
    v7 = TokenHandle;
    if ( TokenHandle )
    {
      I_UrlCacheCloseHandle(TokenHandle);
      v7 = 0;
      TokenHandle = 0;
    }
    goto LABEL_33;
  }
  v7 = TokenHandle;
  v8 = 0;
  v9 = *((_DWORD *)a1 + 35);
  v10 = 6291469;
  v2 = 1;
  if ( v9 == 3 )
  {
    if ( (unsigned int)IsPostOcspUrl(*((const unsigned __int16 **)a1 + 9)) )
      v10 = 7340045;
  }
  else if ( v9 == 7 || (unsigned int)(v9 - 5) <= 1 )
  {
    v8 = 1;
    if ( (I_CertGetAutoUpdateFlags() & 4) == 0 )
      v10 = 207618061;
  }
  memset_0(&pAuxInfo, 0, sizeof(pAuxInfo));
  pAuxInfo.pwszCacheFileNamePrefix = (LPWSTR)*((_QWORD *)a1 + 10);
  pAuxInfo.cbSize = 88;
  pAuxInfo.ppResponseInfo = (PCRYPTNET_URL_CACHE_RESPONSE_INFO *)&pv;
  pAuxInfo.dwMaxUrlRetrievalByteCount = dword_180020278;
  *((_QWORD *)a1 + 29) = 0;
  pAuxInfo.pLastSyncTime = (FILETIME *)((char *)a1 + 232);
  ppwszErrorResponseHeaders = (LPWSTR *)&v26;
  if ( !v8 )
    ppwszErrorResponseHeaders = pAuxInfo.ppwszErrorResponseHeaders;
  pAuxInfo.ppwszErrorResponseHeaders = ppwszErrorResponseHeaders;
  if ( *((_DWORD *)a1 + 44) )
  {
    v12 = *((_DWORD *)a1 + 45);
LABEL_13:
    if ( v12 )
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v22 = *(_QWORD *)&SystemTimeAsFileTime - 10000000LL * v12;
      pAuxInfo.pftCacheResync = (LPFILETIME)&v22;
    }
    goto LABEL_15;
  }
  if ( v8 )
  {
    v18 = *((_DWORD *)a1 + 35);
    if ( v18 == 7 )
    {
LABEL_39:
      v19 = 14400;
      goto LABEL_40;
    }
    v21 = v18 - 5;
    if ( v21 )
    {
      if ( v21 == 1 )
        goto LABEL_39;
      v19 = 3600;
    }
    else
    {
      v19 = 86400;
    }
LABEL_40:
    v12 = (unsigned int)I_CryptSubtractFileTimes((char *)a1 + 160, (char *)a1 + 152) >> 1;
    if ( v12 > v19 )
      v12 = v19;
    goto LABEL_13;
  }
LABEL_15:
  v13 = (_QWORD *)((char *)a1 + 216);
  v14 = (void *)*((_QWORD *)a1 + 27);
  if ( v14 )
  {
    CryptMemFree(v14);
    *v13 = 0;
  }
  if ( CryptRetrieveObjectByUrlW(
         *((LPCWSTR *)a1 + 9),
         0,
         v10,
         1000 * dword_1800202AC,
         (LPVOID *)a1 + 27,
         0,
         0,
         0,
         &pAuxInfo) )
  {
    v15 = 0;
    if ( *v13 )
    {
      v17 = (void *)*((_QWORD *)a1 + 28);
      if ( v17 )
        CryptMemFree(v17);
      *((_QWORD *)a1 + 28) = pv;
      pv = 0;
      goto LABEL_25;
    }
    if ( pAuxInfo.dwHttpStatusCode == 304 )
    {
LABEL_25:
      RestoreToken(v7);
      goto LABEL_26;
    }
    v16 = -2147418113;
    goto LABEL_21;
  }
  if ( *((_DWORD *)a1 + 35) == 7 )
  {
    v20 = GetLastError();
    SetPinRulesLastError(v20, v26, 0);
    SetLastError(v20);
  }
LABEL_33:
  v15 = GetLastError();
  if ( !v15 )
    v15 = -2147418113;
  if ( v2 )
    goto LABEL_25;
LABEL_26:
  if ( pv )
    CryptMemFree(pv);
  if ( v26 )
    CryptMemFree(v26);
  *((_DWORD *)a1 + 30) = v15;
}

```

## disassembly

```asm
0x180008a10  mov     rax, rsp
0x180008a13  push    rbp
0x180008a14  push    rbx
0x180008a15  push    rsi
0x180008a16  lea     rbp, [rax-5Fh]
0x180008a1a  sub     rsp, 0F0h
0x180008a21  mov     [rax-20h], rdi
0x180008a25  mov     rbx, rcx
0x180008a28  mov     [rax-30h], r13
0x180008a2c  lea     rcx, [rbp+57h+pAuxInfo]; void *
0x180008a30  mov     [rax-38h], r14
0x180008a34  xor     r13d, r13d
0x180008a37  mov     [rax-40h], r15
0x180008a3b  xor     edx, edx; Val
0x180008a3d  mov     r8d, 58h ; 'X'; Size
0x180008a43  mov     r15d, r13d
0x180008a46  call    memset_0
0x180008a4b  mov     rax, [rbx+80h]
0x180008a52  mov     [rbp+57h+var_B0], r13
0x180008a56  mov     [rbp+57h+pv], r13
0x180008a5a  mov     [rbp+57h+arg_10], r13
0x180008a5e  test    rax, rax
0x180008a61  jz      loc_180008D28
0x180008a67  mov     rdi, [rax]
0x180008a6a  mov     [rbp+57h+TokenHandle], r13
0x180008a6e  call    cs:__imp_GetCurrentThread
0x180008a74  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180008a78  mov     edx, 0Ch; DesiredAccess
0x180008a7d  mov     rcx, rax; ThreadHandle
0x180008a80  mov     r8d, 1; OpenAsSelf
0x180008a86  call    cs:__imp_OpenThreadToken
0x180008a8c  test    eax, eax
0x180008a8e  jnz     short loc_180008AA5
0x180008a90  call    cs:__imp_GetLastError
0x180008a96  mov     [rbp+57h+TokenHandle], r13
0x180008a9a  cmp     eax, 3F0h
0x180008a9f  jnz     loc_180008D3B
0x180008aa5  mov     rdx, rdi; Token
0x180008aa8  xor     ecx, ecx; Thread
0x180008aaa  call    cs:__imp_SetThreadToken
0x180008ab0  test    eax, eax
0x180008ab2  jz      loc_180008D35
0x180008ab8  mov     r14, [rbp+57h+TokenHandle]
0x180008abc  mov     edi, r13d
0x180008abf  mov     eax, [rbx+8Ch]
0x180008ac5  mov     esi, 60000Dh
0x180008aca  mov     r15d, 1
0x180008ad0  cmp     eax, 3
0x180008ad3  jz      loc_180008CEA
0x180008ad9  cmp     eax, 7
0x180008adc  jnz     loc_180008D64
0x180008ae2  mov     edi, r15d
0x180008ae5  call    I_CertGetAutoUpdateFlags
0x180008aea  test    al, 4
0x180008aec  jnz     short loc_180008AF4
0x180008aee  or      esi, 0C000000h
0x180008af4  xor     edx, edx; Val
0x180008af6  lea     rcx, [rbp+57h+pAuxInfo]; void *
0x180008afa  mov     r8d, 58h ; 'X'; Size
0x180008b00  call    memset_0
0x180008b05  mov     rax, [rbx+50h]
0x180008b09  xor     ecx, ecx
0x180008b0b  mov     [rbp+57h+pAuxInfo.pwszCacheFileNamePrefix], rax
0x180008b0f  test    edi, edi
0x180008b11  lea     rax, [rbp+57h+pv]
0x180008b15  mov     [rbp+57h+pAuxInfo.cbSize], 58h ; 'X'
0x180008b1c  mov     [rbp+57h+pAuxInfo.ppResponseInfo], rax
0x180008b20  mov     eax, cs:dword_180020278
0x180008b26  mov     [rbp+57h+pAuxInfo.dwMaxUrlRetrievalByteCount], eax
0x180008b29  lea     rax, [rbx+0E8h]
0x180008b30  mov     [rax], rcx
0x180008b33  mov     [rbp+57h+pAuxInfo.pLastSyncTime], rax
0x180008b37  lea     rax, [rbp+57h+arg_10]
0x180008b3b  cmovz   rax, [rbp+57h+pAuxInfo.ppwszErrorResponseHeaders]
0x180008b40  mov     [rbp+57h+pAuxInfo.ppwszErrorResponseHeaders], rax
0x180008b44  cmp     [rbx+0B0h], ecx
0x180008b4a  jz      loc_180008C8F
0x180008b50  mov     edi, [rbx+0B4h]
0x180008b56  test    edi, edi
0x180008b58  jz      short loc_180008B84
0x180008b5a  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180008b5e  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r13
0x180008b62  call    cs:__imp_GetSystemTimeAsFileTime
0x180008b68  mov     eax, edi
0x180008b6a  imul    rcx, rax, 989680h
0x180008b71  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180008b75  sub     rax, rcx
0x180008b78  mov     [rbp+57h+var_B0], rax
0x180008b7c  lea     rax, [rbp+57h+var_B0]
0x180008b80  mov     [rbp+57h+pAuxInfo.pftCacheResync], rax
0x180008b84  lea     rdi, [rbx+0D8h]
0x180008b8b  mov     rcx, [rdi]; pv
0x180008b8e  test    rcx, rcx
0x180008b91  jnz     loc_180008D9F
0x180008b97  imul    r9d, cs:dword_1800202AC, 3E8h; dwTimeout
0x180008ba2  lea     rax, [rbp+57h+pAuxInfo]
0x180008ba6  mov     rcx, [rbx+48h]; pszUrl
0x180008baa  mov     r8d, esi; dwRetrievalFlags
0x180008bad  mov     [rsp+40h], rax; pAuxInfo
0x180008bb2  xor     edx, edx; pszObjectOid
0x180008bb4  mov     [rsp+100h+pvVerify], r13; pvVerify
0x180008bb9  mov     [rsp+100h+pCredentials], r13; pCredentials
0x180008bbe  mov     [rsp+100h+hAsyncRetrieve], r13; hAsyncRetrieve
0x180008bc3  mov     [rsp+100h+ppvObject], rdi; ppvObject
0x180008bc8  call    cs:__imp_CryptRetrieveObjectByUrlW
0x180008bce  test    eax, eax
0x180008bd0  jz      loc_180008C6A
0x180008bd6  mov     esi, r13d
0x180008bd9  cmp     [rdi], rsi
0x180008bdc  jnz     short loc_180008BF7
0x180008bde  cmp     [rbp+57h+pAuxInfo.dwHttpStatusCode], 130h
0x180008be5  jz      short loc_180008C16
0x180008be7  mov     ecx, 8000FFFFh; dwErrCode
0x180008bec  call    cs:__imp_SetLastError
0x180008bf2  jmp     loc_180008C77
0x180008bf7  mov     rcx, [rbx+0E0h]; pv
0x180008bfe  test    rcx, rcx
0x180008c01  jnz     loc_180008CDF
0x180008c07  mov     rax, [rbp+57h+pv]
0x180008c0b  mov     [rbx+0E0h], rax
0x180008c12  mov     [rbp+57h+pv], r13
0x180008c16  mov     rcx, r14; hObject
0x180008c19  call    ?RestoreToken@@YAXPEAX@Z; RestoreToken(void *)
0x180008c1e  mov     rcx, [rbp+57h+pv]; pv
0x180008c22  mov     r15, [rsp+100h+var_38]
0x180008c2a  mov     r14, [rsp+100h+var_30]
0x180008c32  mov     r13, [rsp+100h+var_28]
0x180008c3a  mov     rdi, [rsp+0E8h]
0x180008c42  test    rcx, rcx
0x180008c45  jnz     short loc_180008C62
0x180008c47  mov     rcx, [rbp+57h+arg_10]; pv
0x180008c4b  test    rcx, rcx
0x180008c4e  jnz     loc_180008DAD
0x180008c54  mov     [rbx+78h], esi
0x180008c57  add     rsp, 0F0h
0x180008c5e  pop     rsi
0x180008c5f  pop     rbx
0x180008c60  pop     rbp
0x180008c61  retn
0x180008c62  call    cs:__imp_CryptMemFree
0x180008c68  jmp     short loc_180008C47
0x180008c6a  cmp     dword ptr [rbx+8Ch], 7
0x180008c71  jz      loc_180008D05
0x180008c77  call    cs:__imp_GetLastError
0x180008c7d  mov     esi, eax
0x180008c7f  test    eax, eax
0x180008c81  jnz     short loc_180008C88
0x180008c83  mov     esi, 8000FFFFh
0x180008c88  test    r15d, r15d
0x180008c8b  jnz     short loc_180008C16
0x180008c8d  jmp     short loc_180008C1E
0x180008c8f  test    edi, edi
0x180008c91  jz      loc_180008B84
0x180008c97  mov     eax, [rbx+8Ch]
0x180008c9d  mov     [rsp+100h+var_20], r12
0x180008ca5  cmp     eax, 7
0x180008ca8  jnz     loc_180008D7B
0x180008cae  mov     r12d, 3840h
0x180008cb4  lea     rdx, [rbx+98h]
0x180008cbb  lea     rcx, [rbx+0A0h]
0x180008cc2  call    I_CryptSubtractFileTimes
0x180008cc7  mov     edi, eax
0x180008cc9  shr     edi, 1
0x180008ccb  cmp     edi, r12d
0x180008cce  cmova   edi, r12d
0x180008cd2  mov     r12, [rsp+100h+var_20]
0x180008cda  jmp     loc_180008B56
0x180008cdf  call    cs:__imp_CryptMemFree
0x180008ce5  jmp     loc_180008C07
0x180008cea  mov     rcx, [rbx+48h]; unsigned __int16 *
0x180008cee  call    ?IsPostOcspUrl@@YAHPEBG@Z; IsPostOcspUrl(ushort const *)
0x180008cf3  test    eax, eax
0x180008cf5  jz      loc_180008AF4
0x180008cfb  mov     esi, 70000Dh
0x180008d00  jmp     loc_180008AF4
0x180008d05  call    cs:__imp_GetLastError
0x180008d0b  mov     rdx, [rbp+57h+arg_10]
0x180008d0f  xor     r8d, r8d
0x180008d12  mov     ecx, eax
0x180008d14  mov     edi, eax
0x180008d16  call    _SetPinRulesLastError
0x180008d1b  mov     ecx, edi; dwErrCode
0x180008d1d  call    cs:__imp_SetLastError
0x180008d23  jmp     loc_180008C77
0x180008d28  mov     r14, r13
0x180008d2b  mov     ecx, 3F0h
0x180008d30  jmp     loc_180008BEC
0x180008d35  call    cs:__imp_GetLastError
0x180008d3b  mov     ecx, eax; dwErrCode
0x180008d3d  call    cs:__imp_SetLastError
0x180008d43  mov     r14, [rbp+57h+TokenHandle]
0x180008d47  test    r14, r14
0x180008d4a  jz      loc_180008C77
0x180008d50  mov     rcx, r14; hObject
0x180008d53  call    I_UrlCacheCloseHandle
0x180008d58  mov     r14, r13
0x180008d5b  mov     [rbp+57h+TokenHandle], r13
0x180008d5f  jmp     loc_180008C77
0x180008d64  sub     eax, 5
0x180008d67  jz      loc_180008AE2
0x180008d6d  cmp     eax, r15d
0x180008d70  jnz     loc_180008AF4
0x180008d76  jmp     loc_180008AE2
0x180008d7b  sub     eax, 5
0x180008d7e  jz      short loc_180008D94
0x180008d80  cmp     eax, r15d
0x180008d83  jz      loc_180008CAE
0x180008d89  mov     r12d, 0E10h
0x180008d8f  jmp     loc_180008CB4
0x180008d94  mov     r12d, 15180h
0x180008d9a  jmp     loc_180008CB4
0x180008d9f  call    cs:__imp_CryptMemFree
0x180008da5  mov     [rdi], r13
0x180008da8  jmp     loc_180008B97
0x180008dad  call    cs:__imp_CryptMemFree
0x180008db3  jmp     loc_180008C54
```
