# ProcessToBeRunTriggerJob

- ea: `0x180005700`
- end: `0x180005bca`
- name: `ProcessToBeRunTriggerJob`
- size: `1226`
- prototype: `void __fastcall(HANDLE **hMem)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180005460`

## callees

- `0x180004318`
- `0x180004364`
- `0x180004498`
- `0x180004998`
- `0x180005700`
- `0x180005bd0`
- `0x180006760`
- `0x1800068b0`
- `0x1800068f0`
- `0x180006d00`
- `0x180006db0`
- `0x180007980`
- `0x18000cab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ad0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ac6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005bbf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ac6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005aed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005bbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005aad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005aad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b75`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005788`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005913`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005788`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005913`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005abe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005adb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005abe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005adb`
- `CRYPT32!I_CertSrvProtectFunction` at `0x180005950`
- `CRYPT32!I_CertSrvProtectFunction` at `0x1800059c1`
- `CRYPT32!I_CertSrvProtectFunction` at `0x180005950`
- `CRYPT32!I_CertSrvProtectFunction` at `0x1800059c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005a1c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005a1c`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x180005807`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x180005807`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180005760`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800058c3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180005760`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800058c3`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180005836`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180005836`

## string_xrefs

- `0x1800057c7`: `\Microsoft\CryptnetUrlCache\`

## pseudocode

```c
void __fastcall ProcessToBeRunTriggerJob(HANDLE **hMem)
{
  struct _CUCS_TOKEN_ID *TokenId; // rdi
  struct _CUCS_URL_CACHE_DIR_ENTRY *v3; // rbx
  struct _CUCS_URL_CACHE_DIR_ENTRY *v4; // rax
  WCHAR *v5; // rsi
  int v6; // ebp
  const unsigned __int16 *LowIntegrityUserPath; // rax
  const WCHAR *MetaDataDirectory; // rax
  HANDLE v9; // rax
  __int64 v10; // rax
  struct _CUCS_URL_CACHE_DIR_ENTRY *v11; // rax
  PSID *v12; // rcx
  PSID *v13; // rdx
  _QWORD *v14; // rcx
  __int64 i; // rdx
  __int64 v16; // rax
  volatile signed __int32 *v17; // rsi
  _QWORD *v18; // rbp
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 *v23; // r8
  __int64 v24; // rbx
  DWORD LastError; // ebx
  HANDLE *v26; // rcx
  HANDLE *v27; // rdi
  DWORD v28; // ebx
  DWORD v29; // ebx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp+8h] BYREF
  __int64 v31; // [rsp+88h] [rbp+10h] BYREF

  TokenId = GetTokenId(*hMem[4]);
  if ( !TokenId )
    goto LABEL_37;
  v3 = pUrlCacheDirHead;
  if ( !pUrlCacheDirHead )
  {
LABEL_5:
    SystemTimeAsFileTime = 0;
    v4 = (struct _CUCS_URL_CACHE_DIR_ENTRY *)LocalAlloc(0x40u, 0x78u);
    v3 = v4;
    if ( !v4 )
    {
      SetLastError(0x8007000E);
      PkiFree(0);
      goto LABEL_35;
    }
    v5 = 0;
    v6 = 0;
    *((_QWORD *)v4 + 3) = TokenId;
    TokenId = 0;
    if ( (unsigned int)ImpersonateToken(*hMem[4], (void **)&SystemTimeAsFileTime) )
    {
      v6 = 1;
      LowIntegrityUserPath = (const unsigned __int16 *)I_CryptGetLowIntegrityUserPath(
                                                         (__int64)*hMem[4],
                                                         L"\\Microsoft\\CryptnetUrlCache\\");
      *((_QWORD *)v3 + 4) = LowIntegrityUserPath;
      if ( LowIntegrityUserPath )
      {
        MetaDataDirectory = GetMetaDataDirectory(LowIntegrityUserPath);
        v5 = (WCHAR *)MetaDataDirectory;
        if ( MetaDataDirectory )
        {
          v9 = FindFirstChangeNotificationW(MetaDataDirectory, 1, 0x1Bu);
          *((_QWORD *)v3 + 7) = v9;
          if ( v9 == (HANDLE)-1LL )
          {
            *((_QWORD *)v3 + 7) = 0;
          }
          else
          {
            v10 = RegisterWaitForSingleObjectEx(v9, DirChangeCallback, v3, 0xFFFFFFFFLL, 4);
            *((_QWORD *)v3 + 8) = v10;
            if ( v10 )
            {
              *((_DWORD *)v3 + 18) = 1;
              if ( (unsigned int)CreateSessionProcessEntryAndAddToDir(
                                   v3,
                                   *((unsigned int *)hMem + 10),
                                   *((unsigned int *)hMem + 11),
                                   hMem + 6) )
              {
                if ( (unsigned int)CreateCacheFileLruCache(v3) )
                {
                  v11 = pUrlCacheDirHead;
                  if ( pUrlCacheDirHead )
                  {
                    *(_QWORD *)v3 = pUrlCacheDirHead;
                    *((_QWORD *)v11 + 1) = v3;
                  }
                  else
                  {
                    *(_QWORD *)v3 = 0;
                  }
                  *((_QWORD *)v3 + 1) = 0;
                  pUrlCacheDirHead = v3;
LABEL_52:
                  RestoreToken(*(HANDLE *)&SystemTimeAsFileTime);
LABEL_53:
                  PkiFree(v5);
                  if ( !v3 )
                    goto LABEL_35;
                  goto LABEL_22;
                }
              }
            }
          }
        }
      }
    }
    FreeUrlCacheDir(v3);
    v3 = 0;
    if ( !v6 )
      goto LABEL_53;
    goto LABEL_52;
  }
  while ( 1 )
  {
    if ( !EqualSid(**(PSID **)TokenId, ***((PSID ***)v3 + 3)) )
      goto LABEL_4;
    v12 = (PSID *)*((_QWORD *)TokenId + 1);
    v13 = *(PSID **)(*((_QWORD *)v3 + 3) + 8LL);
    if ( v12 )
      break;
    if ( !v13 )
      goto LABEL_19;
LABEL_4:
    v3 = *(struct _CUCS_URL_CACHE_DIR_ENTRY **)v3;
    if ( !v3 )
      goto LABEL_5;
  }
  if ( !v13 || !EqualSid(*v12, *v13) )
    goto LABEL_4;
LABEL_19:
  v14 = (_QWORD *)*((_QWORD *)v3 + 2);
  for ( i = *((unsigned int *)hMem + 10); v14; v14 = (_QWORD *)*v14 )
  {
    v16 = v14[5];
    if ( (_DWORD)i )
    {
      if ( (_DWORD)i == *(_DWORD *)(v16 + 40) )
        goto LABEL_22;
    }
    else if ( *((_DWORD *)hMem + 11) == *(_DWORD *)(v16 + 44) )
    {
      goto LABEL_22;
    }
  }
  if ( (unsigned int)CreateSessionProcessEntryAndAddToDir(v3, i, *((unsigned int *)hMem + 11), hMem + 6) )
  {
LABEL_22:
    if ( !*((_QWORD *)v3 + 10) )
    {
      v17 = (volatile signed __int32 *)hMem[4];
      v18 = LocalAlloc(0x40u, 0x30u);
      if ( v18 )
      {
        if ( !(unsigned int)I_CertSrvProtectFunction(0)
          || (unsigned int)IsDisallowedCertAutoUpdateEnabled(v20, v19, v21, v22, 0, 0) )
        {
          if ( (unsigned int)SetAutoUpdatePreFetchInfo(5, *(_QWORD *)v17, *((_QWORD *)v3 + 4)) )
            *((_DWORD *)v3 + 18) = 1;
          if ( (unsigned int)SetAutoUpdatePreFetchInfo(6, *(_QWORD *)v17, *((_QWORD *)v3 + 4)) )
            *((_DWORD *)v3 + 18) = 1;
          if ( !(unsigned int)I_CertSrvProtectFunction(0)
            && (unsigned int)SetAutoUpdatePreFetchInfo(7, *(_QWORD *)v17, *((_QWORD *)v3 + 4)) )
          {
            *((_DWORD *)v3 + 18) = 1;
          }
        }
        v18[4] = v3;
        _InterlockedIncrement(v17 + 2);
        v18[5] = v17;
        v23 = 0;
        *((_QWORD *)v3 + 10) = v18;
        v24 = (unsigned int)dword_1800202A4;
        v31 = 0;
        if ( dword_1800202A4 )
        {
          SystemTimeAsFileTime = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          v23 = &v31;
          v31 = *(_QWORD *)&SystemTimeAsFileTime + 10000000 * v24;
        }
        AddToBeRunJobEx((FILETIME)v18, 2, v23, 0);
      }
      else
      {
        SetLastError(0x8007000E);
      }
    }
  }
LABEL_35:
  if ( TokenId )
  {
    LastError = GetLastError();
    LocalFree(TokenId);
    SetLastError(LastError);
  }
LABEL_37:
  v26 = hMem[6];
  if ( v26 )
    CloseHandle(v26);
  v27 = hMem[4];
  if ( v27 )
  {
    if ( *v27 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27 + 2, 0xFFFFFFFF) == 1 )
      {
        CloseHandle(*v27);
        v28 = GetLastError();
        LocalFree(v27);
        SetLastError(v28);
      }
    }
    else
    {
      PkiFree(hMem[4]);
    }
    hMem[4] = 0;
  }
  v29 = GetLastError();
  LocalFree(hMem);
  SetLastError(v29);
}

```

## disassembly

```asm
0x180005700  push    rbx
0x180005702  push    rdi
0x180005703  push    r14
0x180005705  push    r15
0x180005707  sub     rsp, 58h
0x18000570b  mov     r14, rcx
0x18000570e  mov     rcx, [rcx+20h]
0x180005712  mov     rcx, [rcx]; TokenHandle
0x180005715  call    ?GetTokenId@@YAPEAU_CUCS_TOKEN_ID@@PEAX@Z; GetTokenId(void *)
0x18000571a  xor     r15d, r15d
0x18000571d  mov     rdi, rax
0x180005720  test    rax, rax
0x180005723  jz      loc_180005A7C
0x180005729  mov     [rsp+78h+arg_10], rbp
0x180005731  mov     [rsp+78h+var_28], rsi
0x180005736  mov     rbx, cs:?pUrlCacheDirHead@@3PEAU_CUCS_URL_CACHE_DIR_ENTRY@@EA; _CUCS_URL_CACHE_DIR_ENTRY * pUrlCacheDirHead
0x18000573d  test    rbx, rbx
0x180005740  jz      short loc_180005776
0x180005742  nop     dword ptr [rax+00h]
0x180005746  nop     word ptr [rax+rax+00000000h]
0x180005750  mov     rax, [rbx+18h]
0x180005754  mov     rcx, [rdi]
0x180005757  mov     rdx, [rax]
0x18000575a  mov     rcx, [rcx]; pSid1
0x18000575d  mov     rdx, [rdx]; pSid2
0x180005760  call    cs:__imp_EqualSid
0x180005766  test    eax, eax
0x180005768  jnz     loc_18000589F
0x18000576e  mov     rbx, [rbx]
0x180005771  test    rbx, rbx
0x180005774  jnz     short loc_180005750
0x180005776  mov     edx, 78h ; 'x'; uBytes
0x18000577b  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180005783  mov     ecx, 40h ; '@'; uFlags
0x180005788  call    cs:__imp_LocalAlloc
0x18000578e  mov     rbx, rax
0x180005791  test    rax, rax
0x180005794  jz      loc_180005B9A
0x18000579a  mov     rsi, r15
0x18000579d  mov     ebp, r15d
0x1800057a0  mov     [rax+18h], rdi
0x1800057a4  lea     rdx, [rsp+78h+SystemTimeAsFileTime]; void **
0x1800057ac  mov     rcx, [r14+20h]
0x1800057b0  mov     rdi, r15
0x1800057b3  mov     rcx, [rcx]; Token
0x1800057b6  call    ?ImpersonateToken@@YAHPEAXPEAPEAX@Z; ImpersonateToken(void *,void * *)
0x1800057bb  test    eax, eax
0x1800057bd  jz      loc_180005B34
0x1800057c3  mov     rcx, [r14+20h]
0x1800057c7  lea     rdx, aMicrosoftCrypt_0; "\\Microsoft\\CryptnetUrlCache\\"
0x1800057ce  mov     ebp, 1
0x1800057d3  mov     rcx, [rcx]
0x1800057d6  call    I_CryptGetLowIntegrityUserPath
0x1800057db  mov     [rbx+20h], rax
0x1800057df  test    rax, rax
0x1800057e2  jz      loc_180005B34
0x1800057e8  mov     rcx, rax; Src
0x1800057eb  call    ?GetMetaDataDirectory@@YAPEAGPEBG@Z; GetMetaDataDirectory(ushort const *)
0x1800057f0  mov     rsi, rax
0x1800057f3  test    rax, rax
0x1800057f6  jz      loc_180005B34
0x1800057fc  mov     edx, ebp; bWatchSubtree
0x1800057fe  mov     r8d, 1Bh; dwNotifyFilter
0x180005804  mov     rcx, rax; lpPathName
0x180005807  call    cs:__imp_FindFirstChangeNotificationW
0x18000580d  mov     [rbx+38h], rax
0x180005811  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005815  jz      loc_180005BB1
0x18000581b  mov     r9d, 0FFFFFFFFh
0x180005821  mov     dword ptr [rsp+78h+var_58], 4
0x180005829  mov     r8, rbx
0x18000582c  lea     rdx, ?DirChangeCallback@@YAXPEAXE@Z; DirChangeCallback(void *,uchar)
0x180005833  mov     rcx, rax
0x180005836  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18000583c  mov     [rbx+40h], rax
0x180005840  test    rax, rax
0x180005843  jz      loc_180005B34
0x180005849  mov     [rbx+48h], ebp
0x18000584c  lea     r9, [r14+30h]
0x180005850  mov     r8d, [r14+2Ch]
0x180005854  mov     rcx, rbx
0x180005857  mov     edx, [r14+28h]
0x18000585b  call    CreateSessionProcessEntryAndAddToDir
0x180005860  test    eax, eax
0x180005862  jz      loc_180005B34
0x180005868  mov     rcx, rbx
0x18000586b  call    _CreateCacheFileLruCache
0x180005870  test    eax, eax
0x180005872  jz      loc_180005B34
0x180005878  mov     rax, cs:?pUrlCacheDirHead@@3PEAU_CUCS_URL_CACHE_DIR_ENTRY@@EA; _CUCS_URL_CACHE_DIR_ENTRY * pUrlCacheDirHead
0x18000587f  test    rax, rax
0x180005882  jz      loc_180005B92
0x180005888  mov     [rbx], rax
0x18000588b  mov     [rax+8], rbx
0x18000588f  mov     [rbx+8], r15
0x180005893  mov     cs:?pUrlCacheDirHead@@3PEAU_CUCS_URL_CACHE_DIR_ENTRY@@EA, rbx; _CUCS_URL_CACHE_DIR_ENTRY * pUrlCacheDirHead
0x18000589a  jmp     loc_180005B45
0x18000589f  mov     rax, [rbx+18h]
0x1800058a3  mov     rcx, [rdi+8]
0x1800058a7  mov     rdx, [rax+8]
0x1800058ab  test    rcx, rcx
0x1800058ae  jz      loc_180005B26
0x1800058b4  test    rdx, rdx
0x1800058b7  jz      loc_18000576E
0x1800058bd  mov     rdx, [rdx]; pSid2
0x1800058c0  mov     rcx, [rcx]; pSid1
0x1800058c3  call    cs:__imp_EqualSid
0x1800058c9  test    eax, eax
0x1800058cb  jz      loc_18000576E
0x1800058d1  mov     rcx, [rbx+10h]
0x1800058d5  mov     edx, [r14+28h]
0x1800058d9  test    rcx, rcx
0x1800058dc  jz      loc_180005B09
0x1800058e2  mov     rax, [rcx+28h]
0x1800058e6  test    edx, edx
0x1800058e8  jnz     loc_180005AF4
0x1800058ee  mov     eax, [rax+2Ch]
0x1800058f1  cmp     [r14+2Ch], eax
0x1800058f5  jnz     loc_180005AFD
0x1800058fb  cmp     [rbx+50h], r15
0x1800058ff  jnz     loc_180005A51
0x180005905  mov     rsi, [r14+20h]
0x180005909  mov     edx, 30h ; '0'; uBytes
0x18000590e  mov     ecx, 40h ; '@'; uFlags
0x180005913  call    cs:__imp_LocalAlloc
0x180005919  mov     rbp, rax
0x18000591c  test    rax, rax
0x18000591f  jz      loc_180005BBA
0x180005925  mov     [rsp+78h+var_30], r15
0x18000592a  xor     r9d, r9d
0x18000592d  mov     [rsp+78h+var_38], r15
0x180005932  xor     r8d, r8d
0x180005935  mov     [rsp+78h+var_40], r15
0x18000593a  mov     edx, 0Ch
0x18000593f  mov     [rsp+78h+var_48], r15
0x180005944  xor     ecx, ecx
0x180005946  mov     [rsp+78h+var_50], r15d
0x18000594b  mov     [rsp+78h+var_58], r15
0x180005950  call    cs:__imp_I_CertSrvProtectFunction
0x180005956  test    eax, eax
0x180005958  jnz     loc_180005B80
0x18000595e  mov     r8, [rbx+20h]
0x180005962  mov     ecx, 5
0x180005967  mov     rdx, [rsi]
0x18000596a  call    SetAutoUpdatePreFetchInfo
0x18000596f  test    eax, eax
0x180005971  jz      short loc_18000597A
0x180005973  mov     dword ptr [rbx+48h], 1
0x18000597a  mov     r8, [rbx+20h]
0x18000597e  mov     ecx, 6
0x180005983  mov     rdx, [rsi]
0x180005986  call    SetAutoUpdatePreFetchInfo
0x18000598b  test    eax, eax
0x18000598d  jz      short loc_180005996
0x18000598f  mov     dword ptr [rbx+48h], 1
0x180005996  mov     [rsp+78h+var_30], r15
0x18000599b  xor     r9d, r9d
0x18000599e  mov     [rsp+78h+var_38], r15
0x1800059a3  xor     r8d, r8d
0x1800059a6  mov     [rsp+78h+var_40], r15
0x1800059ab  mov     edx, 0Fh
0x1800059b0  mov     [rsp+78h+var_48], r15
0x1800059b5  xor     ecx, ecx
0x1800059b7  mov     [rsp+78h+var_50], r15d
0x1800059bc  mov     [rsp+78h+var_58], r15
0x1800059c1  call    cs:__imp_I_CertSrvProtectFunction
0x1800059c7  test    eax, eax
0x1800059c9  jnz     short loc_1800059E7
0x1800059cb  mov     r8, [rbx+20h]
0x1800059cf  mov     ecx, 7
0x1800059d4  mov     rdx, [rsi]
0x1800059d7  call    SetAutoUpdatePreFetchInfo
0x1800059dc  test    eax, eax
0x1800059de  jz      short loc_1800059E7
0x1800059e0  mov     dword ptr [rbx+48h], 1
0x1800059e7  mov     [rbp+20h], rbx
0x1800059eb  lock inc dword ptr [rsi+8]
0x1800059ef  mov     [rbp+28h], rsi
0x1800059f3  mov     r8, r15
0x1800059f6  mov     [rbx+50h], rbp
0x1800059fa  mov     ebx, cs:dword_1800202A4
0x180005a00  mov     [rsp+78h+arg_8], r15
0x180005a08  test    ebx, ebx
0x180005a0a  jz      short loc_180005A41
0x180005a0c  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005a14  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180005a1c  call    cs:__imp_GetSystemTimeAsFileTime
0x180005a22  imul    rcx, rbx, 989680h
0x180005a29  lea     r8, [rsp+78h+arg_8]
0x180005a31  add     rcx, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x180005a39  mov     [rsp+78h+arg_8], rcx
0x180005a41  xor     r9d, r9d
0x180005a44  mov     edx, 2
0x180005a49  mov     rcx, rbp
0x180005a4c  call    AddToBeRunJobEx
0x180005a51  mov     rsi, [rsp+78h+var_28]
0x180005a56  mov     rbp, [rsp+78h+arg_10]
0x180005a5e  test    rdi, rdi
0x180005a61  jz      short loc_180005A7C
0x180005a63  call    cs:__imp_GetLastError
0x180005a69  mov     rcx, rdi; hMem
0x180005a6c  mov     ebx, eax
0x180005a6e  call    cs:__imp_LocalFree
0x180005a74  mov     ecx, ebx; dwErrCode
0x180005a76  call    cs:__imp_SetLastError
0x180005a7c  mov     rcx, [r14+30h]; hObject
0x180005a80  test    rcx, rcx
0x180005a83  jnz     loc_180005B75
0x180005a89  mov     rdi, [r14+20h]
0x180005a8d  test    rdi, rdi
0x180005a90  jz      short loc_180005AD0
0x180005a92  cmp     [rdi], r15
0x180005a95  jz      loc_180005B68
0x180005a9b  mov     eax, 0FFFFFFFFh
0x180005aa0  lock xadd [rdi+8], eax
0x180005aa5  cmp     eax, 1
0x180005aa8  jnz     short loc_180005ACC
0x180005aaa  mov     rcx, [rdi]; hObject
0x180005aad  call    cs:__imp_CloseHandle
0x180005ab3  call    cs:__imp_GetLastError
0x180005ab9  mov     rcx, rdi; hMem
0x180005abc  mov     ebx, eax
0x180005abe  call    cs:__imp_LocalFree
0x180005ac4  mov     ecx, ebx; dwErrCode
0x180005ac6  call    cs:__imp_SetLastError
0x180005acc  mov     [r14+20h], r15
0x180005ad0  call    cs:__imp_GetLastError
0x180005ad6  mov     rcx, r14; hMem
0x180005ad9  mov     ebx, eax
0x180005adb  call    cs:__imp_LocalFree
0x180005ae1  mov     ecx, ebx
0x180005ae3  add     rsp, 58h
0x180005ae7  pop     r15
0x180005ae9  pop     r14
0x180005aeb  pop     rdi
0x180005aec  pop     rbx
0x180005aed  jmp     cs:__imp_SetLastError
0x180005af4  cmp     edx, [rax+28h]
0x180005af7  jz      loc_1800058FB
0x180005afd  mov     rcx, [rcx]
0x180005b00  test    rcx, rcx
0x180005b03  jnz     loc_1800058E2
0x180005b09  mov     r8d, [r14+2Ch]
0x180005b0d  lea     r9, [r14+30h]
0x180005b11  mov     rcx, rbx
0x180005b14  call    CreateSessionProcessEntryAndAddToDir
0x180005b19  test    eax, eax
0x180005b1b  jnz     loc_1800058FB
0x180005b21  jmp     loc_180005A51
0x180005b26  test    rdx, rdx
0x180005b29  jnz     loc_18000576E
0x180005b2f  jmp     loc_1800058D1
0x180005b34  xor     edx, edx
0x180005b36  mov     rcx, rbx; hMem
0x180005b39  call    FreeUrlCacheDir
0x180005b3e  mov     rbx, r15
0x180005b41  test    ebp, ebp
0x180005b43  jz      short loc_180005B52
0x180005b45  mov     rcx, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]; hObject
0x180005b4d  call    ?RestoreToken@@YAXPEAX@Z; RestoreToken(void *)
0x180005b52  mov     rcx, rsi; hMem
0x180005b55  call    PkiFree
0x180005b5a  test    rbx, rbx
0x180005b5d  jz      loc_180005A51
0x180005b63  jmp     loc_1800058FB
0x180005b68  mov     rcx, rdi; hMem
0x180005b6b  call    PkiFree
0x180005b70  jmp     loc_180005ACC
0x180005b75  call    cs:__imp_CloseHandle
0x180005b7b  jmp     loc_180005A89
0x180005b80  call    IsDisallowedCertAutoUpdateEnabled
0x180005b85  test    eax, eax
0x180005b87  jz      loc_1800059E7
0x180005b8d  jmp     loc_18000595E
0x180005b92  mov     [rbx], r15
0x180005b95  jmp     loc_18000588F
0x180005b9a  mov     ecx, 8007000Eh; dwErrCode
0x180005b9f  call    cs:__imp_SetLastError
0x180005ba5  xor     ecx, ecx; hMem
0x180005ba7  call    PkiFree
0x180005bac  jmp     loc_180005A51
0x180005bb1  mov     [rbx+38h], r15
0x180005bb5  jmp     loc_180005B34
0x180005bba  mov     ecx, 8007000Eh; dwErrCode
0x180005bbf  call    cs:__imp_SetLastError
0x180005bc5  jmp     loc_180005A51
```
