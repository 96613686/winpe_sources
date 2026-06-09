# CStorageHelper::_InitPersistentStorage(CStorageQuotaHelper *)

- ea: `0x1807785c4`
- end: `0x180778ab6`
- name: `?_InitPersistentStorage@CStorageHelper@@AEAAJPEAVCStorageQuotaHelper@@@Z`
- size: `1266`
- prototype: `__int64 __fastcall(CStorageHelper *__hidden this, struct CStorageQuotaHelper *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180a24ee4`

## callees

- `0x1801bf344`
- `0x1801c0b08`
- `0x1801cd614`
- `0x18028ecdc`
- `0x18068059c`
- `0x180748d70`
- `0x18074a174`
- `0x18074c1a0`
- `0x18075af04`
- `0x180771b58`
- `0x1807785c4`
- `0x18078f2c0`
- `0x180a24694`
- `0x180a24ab0`
- `0x180a25e24`
- `0x1810c2cb6`
- `0x1810c2d60`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180778669`
- `KERNEL32!QueryPerformanceCounter` at `0x18077872c`
- `KERNEL32!QueryPerformanceCounter` at `0x180778669`
- `KERNEL32!QueryPerformanceCounter` at `0x18077872c`
- `KERNEL32!QueryPerformanceFrequency` at `0x18077865e`
- `KERNEL32!QueryPerformanceFrequency` at `0x18077865e`
- `KERNEL32!CreateMutexW` at `0x1807786d2`
- `KERNEL32!CreateMutexW` at `0x1807786d2`
- `KERNEL32!ReleaseMutex` at `0x180778aab`
- `KERNEL32!ReleaseMutex` at `0x1810ce52a`
- `KERNEL32!ReleaseMutex` at `0x180778aab`
- `KERNEL32!ReleaseMutex` at `0x1810ce52a`
- `KERNEL32!GetLastError` at `0x1807786e8`
- `KERNEL32!GetLastError` at `0x180778871`
- `KERNEL32!GetLastError` at `0x1807788fc`
- `KERNEL32!GetLastError` at `0x180778a04`
- `KERNEL32!GetLastError` at `0x180778a8b`
- `KERNEL32!GetLastError` at `0x1807786e8`
- `KERNEL32!GetLastError` at `0x180778871`
- `KERNEL32!GetLastError` at `0x1807788fc`
- `KERNEL32!GetLastError` at `0x180778a04`
- `KERNEL32!GetLastError` at `0x180778a8b`
- `KERNEL32!WaitForSingleObject` at `0x180778846`
- `KERNEL32!WaitForSingleObject` at `0x180778846`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x1807788e9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x1807788e9`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180778690`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180778690`
- `WININET!GetUrlCacheEntryInfoW` at `0x180778863`
- `WININET!GetUrlCacheEntryInfoW` at `0x1807788c5`
- `WININET!GetUrlCacheEntryInfoW` at `0x180778863`
- `WININET!GetUrlCacheEntryInfoW` at `0x1807788c5`
- `WININET!CreateUrlCacheEntryW` at `0x1807789c5`
- `WININET!CreateUrlCacheEntryW` at `0x1807789c5`
- `WININET!CommitUrlCacheEntryW` at `0x180778a85`
- `WININET!CommitUrlCacheEntryW` at `0x180778a85`

## pseudocode

```c
__int64 __fastcall CStorageHelper::_InitPersistentStorage(CStorageHelper *this, struct CStorageQuotaHelper *a2)
{
  int v4; // esi
  const unsigned __int16 **v5; // r14
  CStorageHelper *v6; // rcx
  unsigned int DomainStringWithPrefix; // ebx
  unsigned int v8; // r13d
  void *v9; // r8
  char Bool; // al
  const unsigned __int16 *v11; // r8
  HANDLE MutexW; // rax
  signed int v13; // eax
  __int64 v14; // r8
  int v16; // r15d
  signed int LastError; // eax
  struct _INTERNET_CACHE_ENTRY_INFOW *v18; // rax
  signed int v19; // eax
  signed int v20; // eax
  LPCWSTR lpszUrlName; // [rsp+58h] [rbp-4F0h] BYREF
  DWORD cbCacheEntryInfo; // [rsp+60h] [rbp-4E8h] BYREF
  int v23; // [rsp+64h] [rbp-4E4h]
  CStorageHelper *v24; // [rsp+68h] [rbp-4E0h] BYREF
  LARGE_INTEGER v25; // [rsp+70h] [rbp-4D8h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+78h] [rbp-4D0h] BYREF
  LARGE_INTEGER Frequency; // [rsp+80h] [rbp-4C8h] BYREF
  _QWORD v28[3]; // [rsp+88h] [rbp-4C0h] BYREF
  _BYTE v29[32]; // [rsp+A0h] [rbp-4A8h] BYREF
  LPCWSTR *p_lpszUrlName; // [rsp+C0h] [rbp-488h]
  __int64 v31; // [rsp+C8h] [rbp-480h]
  CStorageHelper **v32; // [rsp+D0h] [rbp-478h]
  __int64 v33; // [rsp+D8h] [rbp-470h]
  _QWORD *v34; // [rsp+E0h] [rbp-468h]
  __int64 v35; // [rsp+E8h] [rbp-460h]
  WCHAR szFileName[264]; // [rsp+F0h] [rbp-458h] BYREF
  WCHAR Name[264]; // [rsp+300h] [rbp-248h] BYREF

  v24 = this;
  memset_0(szFileName, 0, 0x208u);
  v4 = 0;
  v5 = 0;
  cbCacheEntryInfo = 0;
  lpszUrlName = 0;
  memset_0(Name, 0, 0x208u);
  PerformanceCount.QuadPart = 0;
  v25.QuadPart = 0;
  Frequency.QuadPart = 0;
  CStorageQuotaHelper::CleanupEdpStateMachine(a2);
  DomainStringWithPrefix = CStorageHelper::_EnsureCacheContainer(v6);
  v8 = DomainStringWithPrefix;
  QueryPerformanceFrequency(&Frequency);
  QueryPerformanceCounter(&PerformanceCount);
  if ( !DomainStringWithPrefix )
  {
    DomainStringWithPrefix = CStorageUtils::GetDomainStringWithPrefix(
                               *((const unsigned __int16 **)this + 7),
                               (unsigned __int16 **)&lpszUrlName);
    if ( !DomainStringWithPrefix )
    {
      Bool = IEConfiguration_GetBool(536870916);
      v11 = L"Local\\Low%s";
      if ( !Bool )
        v11 = L"Local\\%s";
      DomainStringWithPrefix = StringCchPrintfW(Name, 0x104u, v11, *((_QWORD *)this + 7));
      if ( !DomainStringWithPrefix )
      {
        MutexW = CreateMutexW(0, 0, Name);
        *((_QWORD *)this + 23) = MutexW;
        if ( MutexW )
        {
          v16 = 0;
          if ( (WaitForSingleObject(MutexW, 0xFFFFFFFF) & 0xFFFFFF7F) == 0 )
          {
            if ( GetUrlCacheEntryInfoW(lpszUrlName, 0, &cbCacheEntryInfo) )
            {
LABEL_51:
              ReleaseMutex(*((HANDLE *)this + 23));
              goto LABEL_9;
            }
            LastError = GetLastError();
            if ( LastError == 2 )
            {
              v4 = 1;
              v23 = 1;
              v16 = 1;
              goto LABEL_28;
            }
            if ( LastError == 122 )
            {
              v18 = (struct _INTERNET_CACHE_ENTRY_INFOW *)MemoryProtection::HeapAlloc<1>(
                                                            g_hProcessHeap,
                                                            cbCacheEntryInfo);
              v5 = (const unsigned __int16 **)v18;
              v28[1] = v18;
              if ( !v18 )
              {
                DomainStringWithPrefix = -2147024882;
                goto LABEL_28;
              }
              if ( GetUrlCacheEntryInfoW(lpszUrlName, v18, &cbCacheEntryInfo) )
              {
                DomainStringWithPrefix = CStr::Set((CStorageHelper *)((char *)this + 192), v5[2]);
                if ( !PathFileExistsW(v5[2]) )
                {
                  v4 = 1;
                  v23 = 1;
                }
                goto LABEL_28;
              }
              LastError = GetLastError();
              DomainStringWithPrefix = LastError;
              if ( LastError <= 0 )
              {
LABEL_28:
                if ( v4 )
                  goto LABEL_34;
                if ( !DomainStringWithPrefix )
                {
                  DomainStringWithPrefix = CStorageUtils::GetFileTimeFromName(
                                             *((const unsigned __int16 **)this + 24),
                                             (struct _FILETIME *)this + 25);
                  if ( !DomainStringWithPrefix )
                  {
                    DomainStringWithPrefix = CStorageHelper::_ReadKeyValuesFromFile(
                                               this,
                                               *((struct CAryKeyValues **)this + 19),
                                               *((struct CStringTable **)this + 20));
                    if ( DomainStringWithPrefix )
                    {
                      EmptyArray(*((struct CAryKeyValues **)this + 19), *((struct CStringTable **)this + 20));
                      DomainStringWithPrefix = 0;
                      v4 = 1;
                      v23 = 1;
                    }
                  }
                }
                if ( v4 )
                {
LABEL_34:
                  if ( !DomainStringWithPrefix )
                  {
                    if ( v16 )
                    {
                      DomainStringWithPrefix = CStorageQuotaHelper::CheckAndUpdateSubdomainLimit(
                                                 a2,
                                                 *((unsigned __int16 **)this + 9));
                      if ( !DomainStringWithPrefix )
                      {
                        if ( CreateUrlCacheEntryW(lpszUrlName, 0, L"xml", szFileName, 0) )
                        {
                          DomainStringWithPrefix = CStr::Set((CStorageHelper *)((char *)this + 192), szFileName);
                        }
                        else
                        {
                          v19 = GetLastError();
                          DomainStringWithPrefix = v19;
                          if ( v19 > 0 )
                            DomainStringWithPrefix = (unsigned __int16)v19 | 0x80070000;
                        }
                      }
                    }
                    if ( !DomainStringWithPrefix )
                    {
                      DomainStringWithPrefix = CStorageHelper::_WriteKeyValuesToFile(this, 1);
                      if ( !DomainStringWithPrefix )
                        DomainStringWithPrefix = CStorageUtils::GetFileTimeFromName(
                                                   *((const unsigned __int16 **)this + 24),
                                                   (struct _FILETIME *)this + 25);
                    }
                    if ( v16 )
                    {
                      if ( !DomainStringWithPrefix )
                      {
                        CommitUrlCacheEntryW(lpszUrlName, szFileName, 0, 0, 1u, 0, 0, 0, 0);
                        v20 = GetLastError();
                        DomainStringWithPrefix = v20;
                        if ( v20 > 0 )
                          DomainStringWithPrefix = (unsigned __int16)v20 | 0x80070000;
                      }
                    }
                  }
                }
                goto LABEL_51;
              }
            }
            else if ( LastError <= 0 )
            {
              DomainStringWithPrefix = LastError;
              goto LABEL_28;
            }
            DomainStringWithPrefix = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_28;
          }
        }
        v13 = GetLastError();
        DomainStringWithPrefix = v13;
        if ( v13 > 0 )
          DomainStringWithPrefix = (unsigned __int16)v13 | 0x80070000;
      }
    }
  }
LABEL_9:
  if ( lpszUrlName )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, (void *)lpszUrlName, v9);
  if ( v5 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v5, v9);
  QueryPerformanceCounter(&v25);
  if ( (unsigned int)dword_181559C88 > 5 && (unsigned __int8)tlgKeywordOn(&dword_181559C88, 0x400000800000LL) )
  {
    v28[0] = v14;
    LODWORD(v24) = v8;
    LODWORD(lpszUrlName) = DomainStringWithPrefix;
    v34 = v28;
    v35 = 8;
    v32 = &v24;
    v33 = 4;
    p_lpszUrlName = &lpszUrlName;
    v31 = 4;
    tlgWriteTransfer_BrowserWriteTransfer(&dword_181559C88, byte_181519B43, &xmmword_18158F768, 0, 5, v29);
  }
  return DomainStringWithPrefix;
}

```

## disassembly

```asm
0x1807785c4  mov     [rsp+arg_10], rbx
0x1807785c9  mov     [rsp+arg_18], rsi
0x1807785ce  push    rdi
0x1807785cf  push    r12
0x1807785d1  push    r13
0x1807785d3  push    r14
0x1807785d5  push    r15
0x1807785d7  sub     rsp, 520h
0x1807785de  mov     rax, cs:__security_cookie
0x1807785e5  xor     rax, rsp
0x1807785e8  mov     [rsp+548h+var_38], rax
0x1807785f0  mov     r12, rdx
0x1807785f3  mov     rdi, rcx
0x1807785f6  mov     [rsp+548h+var_4E0], rcx
0x1807785fb  mov     ebx, 208h
0x180778600  mov     r8d, ebx; Size
0x180778603  xor     edx, edx; Val
0x180778605  lea     rcx, [rsp+548h+szFileName]; void *
0x18077860d  call    memset_0
0x180778612  xor     esi, esi
0x180778614  mov     r14d, esi
0x180778617  mov     [rsp+548h+cbCacheEntryInfo], esi
0x18077861b  mov     [rsp+548h+lpszUrlName], rsi
0x180778620  mov     r8d, ebx; Size
0x180778623  xor     edx, edx; Val
0x180778625  lea     rcx, [rsp+548h+Name]; void *
0x18077862d  call    memset_0
0x180778632  mov     qword ptr [rsp+548h+PerformanceCount], rsi
0x180778637  mov     qword ptr [rsp+548h+var_4D8], rsi
0x18077863c  mov     qword ptr [rsp+548h+Frequency], rsi
0x180778644  mov     rcx, r12; this
0x180778647  call    ?CleanupEdpStateMachine@CStorageQuotaHelper@@QEAAXXZ; CStorageQuotaHelper::CleanupEdpStateMachine(void)
0x18077864c  call    ?_EnsureCacheContainer@CStorageHelper@@AEAAJXZ; CStorageHelper::_EnsureCacheContainer(void)
0x180778651  mov     ebx, eax
0x180778653  mov     r13d, eax
0x180778656  lea     rcx, [rsp+548h+Frequency]; lpFrequency
0x18077865e  call    cs:__imp_QueryPerformanceFrequency
0x180778664  lea     rcx, [rsp+548h+PerformanceCount]; lpPerformanceCount
0x180778669  call    cs:__imp_QueryPerformanceCounter
0x18077866f  test    ebx, ebx
0x180778671  jnz     loc_1807786FD
0x180778677  lea     rdx, [rsp+548h+lpszUrlName]; unsigned __int16 **
0x18077867c  mov     rcx, [rdi+38h]; unsigned __int16 *
0x180778680  call    ?GetDomainStringWithPrefix@CStorageUtils@@SAJPEBGPEAPEAG@Z; CStorageUtils::GetDomainStringWithPrefix(ushort const *,ushort * *)
0x180778685  mov     ebx, eax
0x180778687  test    eax, eax
0x180778689  jnz     short loc_1807786FD
0x18077868b  mov     ecx, 20000004h
0x180778690  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180778696  lea     rcx, aLocalS; "Local\\%s"
0x18077869d  lea     r8, aLocalLowS; "Local\\Low%s"
0x1807786a4  test    al, al
0x1807786a6  cmovz   r8, rcx; unsigned __int16 *
0x1807786aa  mov     r9, [rdi+38h]
0x1807786ae  mov     edx, 104h; unsigned __int64
0x1807786b3  lea     rcx, [rsp+548h+Name]; unsigned __int16 *
0x1807786bb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1807786c0  mov     ebx, eax
0x1807786c2  test    eax, eax
0x1807786c4  jnz     short loc_1807786FD
0x1807786c6  lea     r8, [rsp+548h+Name]; lpName
0x1807786ce  xor     edx, edx; bInitialOwner
0x1807786d0  xor     ecx, ecx; lpMutexAttributes
0x1807786d2  call    cs:__imp_CreateMutexW
0x1807786d8  mov     [rdi+0B8h], rax
0x1807786df  test    rax, rax
0x1807786e2  jnz     loc_18077883D
0x1807786e8  call    cs:__imp_GetLastError
0x1807786ee  mov     ebx, eax
0x1807786f0  test    eax, eax
0x1807786f2  jle     short loc_1807786FD
0x1807786f4  movzx   ebx, ax
0x1807786f7  or      ebx, 80070000h
0x1807786fd  mov     rdx, [rsp+548h+lpszUrlName]; void *
0x180778702  test    rdx, rdx
0x180778705  jz      short loc_180778713
0x180778707  mov     rcx, cs:g_hProcessHeap; this
0x18077870e  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180778713  test    r14, r14
0x180778716  jz      short loc_180778727
0x180778718  mov     rdx, r14; void *
0x18077871b  mov     rcx, cs:g_hProcessHeap; this
0x180778722  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180778727  lea     rcx, [rsp+548h+var_4D8]; lpPerformanceCount
0x18077872c  call    cs:__imp_QueryPerformanceCounter
0x180778732  mov     rax, qword ptr [rsp+548h+var_4D8]
0x180778737  sub     rax, qword ptr [rsp+548h+PerformanceCount]
0x18077873c  imul    rax, 0F4240h
0x180778743  cqo
0x180778745  idiv    qword ptr [rsp+548h+Frequency]
0x18077874d  mov     r8, rax
0x180778750  mov     ecx, cs:dword_181559C88
0x180778756  cmp     ecx, 5
0x180778759  jbe     loc_18077880E
0x18077875f  mov     rdx, 400000800000h
0x180778769  lea     rcx, dword_181559C88
0x180778770  call    _tlgKeywordOn
0x180778775  test    al, al
0x180778777  jz      loc_18077880E
0x18077877d  mov     [rsp+548h+var_4C0], r8
0x180778785  mov     dword ptr [rsp+548h+var_4E0], r13d
0x18077878a  mov     dword ptr [rsp+548h+lpszUrlName], ebx
0x18077878e  lea     rax, [rsp+548h+var_4C0]
0x180778796  mov     [rsp+548h+var_468], rax
0x18077879e  mov     [rsp+548h+var_460], 8
0x1807787aa  lea     rax, [rsp+548h+var_4E0]
0x1807787af  mov     [rsp+548h+var_478], rax
0x1807787b7  mov     [rsp+548h+var_470], 4
0x1807787c3  lea     rax, [rsp+548h+lpszUrlName]
0x1807787c8  mov     [rsp+548h+var_488], rax
0x1807787d0  mov     [rsp+548h+var_480], 4
0x1807787dc  lea     rax, [rsp+548h+var_4A8]
0x1807787e4  mov     [rsp+548h+lpszHeaderInfo], rax
0x1807787e9  mov     [rsp+548h+dwReserved], 5
0x1807787f1  xor     r9d, r9d
0x1807787f4  lea     r8, xmmword_18158F768
0x1807787fb  lea     rdx, byte_181519B43
0x180778802  lea     rcx, dword_181559C88
0x180778809  call    _tlgWriteTransfer_BrowserWriteTransfer
0x18077880e  mov     eax, ebx
0x180778810  mov     rcx, [rsp+548h+var_38]
0x180778818  xor     rcx, rsp; StackCookie
0x18077881b  call    __security_check_cookie
0x180778820  lea     r11, [rsp+548h+var_28]
0x180778828  mov     rbx, [r11+40h]
0x18077882c  mov     rsi, [r11+48h]
0x180778830  mov     rsp, r11
0x180778833  pop     r15
0x180778835  pop     r14
0x180778837  pop     r13
0x180778839  pop     r12
0x18077883b  pop     rdi
0x18077883c  retn
0x18077883d  xor     r15d, r15d
0x180778840  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180778843  mov     rcx, rax; hHandle
0x180778846  call    cs:__imp_WaitForSingleObject
0x18077884c  test    eax, 0FFFFFF7Fh
0x180778851  jnz     loc_1807786E8
0x180778857  lea     r8, [rsp+548h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x18077885c  xor     edx, edx; lpCacheEntryInfo
0x18077885e  mov     rcx, [rsp+548h+lpszUrlName]; lpszUrlName
0x180778863  call    cs:__imp_GetUrlCacheEntryInfoW
0x180778869  test    eax, eax
0x18077886b  jnz     loc_180778AA4
0x180778871  call    cs:__imp_GetLastError
0x180778877  cmp     eax, 2
0x18077887a  jnz     short loc_18077888B
0x18077887c  lea     esi, [rax-1]
0x18077887f  mov     [rsp+548h+var_4E4], esi
0x180778883  mov     r15d, esi
0x180778886  jmp     loc_180778915
0x18077888b  cmp     eax, 7Ah ; 'z'
0x18077888e  jnz     loc_1807789F5
0x180778894  mov     edx, [rsp+548h+cbCacheEntryInfo]
0x180778898  mov     rcx, cs:g_hProcessHeap
0x18077889f  call    ??$HeapAlloc@$00@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<1>(void *,unsigned __int64)
0x1807788a4  mov     r14, rax
0x1807788a7  mov     [rsp+548h+var_4B8], rax
0x1807788af  test    rax, rax
0x1807788b2  jz      loc_1807789EB
0x1807788b8  lea     r8, [rsp+548h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x1807788bd  mov     rdx, rax; lpCacheEntryInfo
0x1807788c0  mov     rcx, [rsp+548h+lpszUrlName]; lpszUrlName
0x1807788c5  call    cs:__imp_GetUrlCacheEntryInfoW
0x1807788cb  test    eax, eax
0x1807788cd  jz      short loc_1807788FC
0x1807788cf  lea     rcx, [rdi+0C0h]; this
0x1807788d6  mov     rdx, [r14+10h]; unsigned __int16 *
0x1807788da  call    ?Set@CStr@@QEAAJPEBG@Z; CStr::Set(ushort const *)
0x1807788df  mov     ebx, eax
0x1807788e1  mov     [rsp+548h+var_4F8], eax
0x1807788e5  mov     rcx, [r14+10h]; pszPath
0x1807788e9  call    cs:__imp_PathFileExistsW
0x1807788ef  test    eax, eax
0x1807788f1  jnz     short loc_180778915
0x1807788f3  lea     esi, [rax+1]
0x1807788f6  mov     [rsp+548h+var_4E4], esi
0x1807788fa  jmp     short loc_180778915
0x1807788fc  call    cs:__imp_GetLastError
0x180778902  mov     ebx, eax
0x180778904  test    eax, eax
0x180778906  jle     short loc_180778911
0x180778908  movzx   ebx, ax
0x18077890b  or      ebx, 80070000h
0x180778911  mov     [rsp+548h+var_4F8], ebx
0x180778915  test    esi, esi
0x180778917  jnz     short loc_180778982
0x180778919  test    ebx, ebx
0x18077891b  jnz     short loc_18077897A
0x18077891d  lea     rdx, [rdi+0C8h]; struct _FILETIME *
0x180778924  mov     rcx, [rdi+0C0h]; unsigned __int16 *
0x18077892b  call    ?GetFileTimeFromName@CStorageUtils@@SAJPEBGPEAU_FILETIME@@@Z; CStorageUtils::GetFileTimeFromName(ushort const *,_FILETIME *)
0x180778930  mov     ebx, eax
0x180778932  mov     [rsp+548h+var_4F8], eax
0x180778936  test    eax, eax
0x180778938  jnz     short loc_18077897A
0x18077893a  mov     r8, [rdi+0A0h]; struct CStringTable *
0x180778941  mov     rdx, [rdi+98h]; struct CAryKeyValues *
0x180778948  mov     rcx, rdi; this
0x18077894b  call    ?_ReadKeyValuesFromFile@CStorageHelper@@AEAAJPEAVCAryKeyValues@@PEAVCStringTable@@@Z; CStorageHelper::_ReadKeyValuesFromFile(CAryKeyValues *,CStringTable *)
0x180778950  mov     ebx, eax
0x180778952  mov     [rsp+548h+var_4F8], eax
0x180778956  test    eax, eax
0x180778958  jz      short loc_18077897A
0x18077895a  mov     rdx, [rdi+0A0h]; struct CStringTable *
0x180778961  mov     rcx, [rdi+98h]; this
0x180778968  call    ?EmptyArray@@YAXPEAVCAryKeyValues@@PEAVCStringTable@@@Z; EmptyArray(CAryKeyValues *,CStringTable *)
0x18077896d  xor     ebx, ebx
0x18077896f  mov     [rsp+548h+var_4F8], ebx
0x180778973  lea     esi, [rbx+1]
0x180778976  mov     [rsp+548h+var_4E4], esi
0x18077897a  test    esi, esi
0x18077897c  jz      loc_180778AA4
0x180778982  xor     esi, esi
0x180778984  test    ebx, ebx
0x180778986  jnz     loc_180778AA4
0x18077898c  test    r15d, r15d
0x18077898f  jz      loc_180778A1D
0x180778995  mov     rdx, [rdi+48h]; unsigned __int16 *
0x180778999  mov     rcx, r12; this
0x18077899c  call    ?CheckAndUpdateSubdomainLimit@CStorageQuotaHelper@@QEAAJPEAG@Z; CStorageQuotaHelper::CheckAndUpdateSubdomainLimit(ushort *)
0x1807789a1  mov     ebx, eax
0x1807789a3  mov     [rsp+548h+var_4F8], eax
0x1807789a7  test    eax, eax
0x1807789a9  jnz     short loc_180778A1D
0x1807789ab  mov     [rsp+548h+dwReserved], esi; dwReserved
0x1807789af  lea     r9, [rsp+548h+szFileName]; lpszFileName
0x1807789b7  lea     r8, szFileExtension; "xml"
0x1807789be  xor     edx, edx; dwExpectedFileSize
0x1807789c0  mov     rcx, [rsp+548h+lpszUrlName]; lpszUrlName
0x1807789c5  call    cs:__imp_CreateUrlCacheEntryW
0x1807789cb  test    eax, eax
0x1807789cd  jz      short loc_180778A04
0x1807789cf  lea     rcx, [rdi+0C0h]; this
0x1807789d6  lea     rdx, [rsp+548h+szFileName]; unsigned __int16 *
0x1807789de  call    ?Set@CStr@@QEAAJPEBG@Z; CStr::Set(ushort const *)
0x1807789e3  mov     ebx, eax
0x1807789e5  mov     [rsp+548h+var_4F8], eax
0x1807789e9  jmp     short loc_180778A1D
0x1807789eb  mov     ebx, 8007000Eh
0x1807789f0  jmp     loc_180778911
0x1807789f5  test    eax, eax
0x1807789f7  jg      loc_180778908
0x1807789fd  mov     ebx, eax
0x1807789ff  jmp     loc_180778911
0x180778a04  call    cs:__imp_GetLastError
0x180778a0a  mov     ebx, eax
0x180778a0c  test    eax, eax
0x180778a0e  jle     short loc_180778A19
0x180778a10  movzx   ebx, ax
0x180778a13  or      ebx, 80070000h
0x180778a19  mov     [rsp+548h+var_4F8], ebx
0x180778a1d  test    ebx, ebx
0x180778a1f  jnz     short loc_180778A4E
0x180778a21  mov     dl, 1; bool
0x180778a23  mov     rcx, rdi; this
0x180778a26  call    ?_WriteKeyValuesToFile@CStorageHelper@@AEAAJ_N@Z; CStorageHelper::_WriteKeyValuesToFile(bool)
0x180778a2b  mov     ebx, eax
0x180778a2d  mov     [rsp+548h+var_4F8], eax
0x180778a31  test    eax, eax
0x180778a33  jnz     short loc_180778A4E
0x180778a35  lea     rdx, [rdi+0C8h]; struct _FILETIME *
0x180778a3c  mov     rcx, [rdi+0C0h]; unsigned __int16 *
0x180778a43  call    ?GetFileTimeFromName@CStorageUtils@@SAJPEBGPEAU_FILETIME@@@Z; CStorageUtils::GetFileTimeFromName(ushort const *,_FILETIME *)
0x180778a48  mov     ebx, eax
0x180778a4a  mov     [rsp+548h+var_4F8], eax
0x180778a4e  test    r15d, r15d
0x180778a51  jz      short loc_180778AA4
0x180778a53  test    ebx, ebx
0x180778a55  jnz     short loc_180778AA4
0x180778a57  mov     r8, rsi; ExpireTime
0x180778a5a  mov     [rsp+548h+lpszOriginalUrl], rsi; lpszOriginalUrl
0x180778a5f  mov     [rsp+548h+lpszFileExtension], rsi; lpszFileExtension
0x180778a64  mov     [rsp+548h+cchHeaderInfo], esi; cchHeaderInfo
0x180778a68  mov     [rsp+548h+lpszHeaderInfo], rsi; lpszHeaderInfo
0x180778a6d  mov     [rsp+548h+dwReserved], 1; CacheEntryType
0x180778a75  mov     r9, rsi; LastModifiedTime
0x180778a78  lea     rdx, [rsp+548h+szFileName]; lpszLocalFileName
0x180778a80  mov     rcx, [rsp+548h+lpszUrlName]; lpszUrlName
0x180778a85  call    cs:__imp_CommitUrlCacheEntryW
0x180778a8b  call    cs:__imp_GetLastError
0x180778a91  test    eax, eax
0x180778a93  mov     ebx, eax
0x180778a95  jle     short loc_180778AA0
0x180778a97  movzx   ebx, ax
0x180778a9a  or      ebx, 80070000h
0x180778aa0  mov     [rsp+548h+var_4F8], ebx
0x180778aa4  mov     rcx, [rdi+0B8h]; hMutex
0x180778aab  call    cs:__imp_ReleaseMutex
0x180778ab1  jmp     loc_1807786FD
0x1810ce516  push    rbp
0x1810ce518  sub     rsp, 50h
0x1810ce51c  mov     rbp, rdx
0x1810ce51f  mov     rcx, [rbp+68h]
0x1810ce523  mov     rcx, [rcx+0B8h]; hMutex
0x1810ce52a  call    cs:__imp_ReleaseMutex
0x1810ce530  nop
0x1810ce531  add     rsp, 50h
0x1810ce535  pop     rbp
  ... truncated ...
```
