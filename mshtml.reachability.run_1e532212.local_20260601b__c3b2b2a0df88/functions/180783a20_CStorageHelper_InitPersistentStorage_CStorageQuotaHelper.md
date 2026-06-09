# CStorageHelper::_InitPersistentStorage(CStorageQuotaHelper *)

- ea: `0x180783a20`
- end: `0x180783f7d`
- name: `?_InitPersistentStorage@CStorageHelper@@AEAAJPEAVCStorageQuotaHelper@@@Z`
- size: `1373`
- prototype: `__int64 __fastcall(CStorageHelper *__hidden this, struct CStorageQuotaHelper *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180a37b58`

## callees

- `0x18005ce98`
- `0x18005e684`
- `0x18006b354`
- `0x1804e4c1c`
- `0x18067f6c4`
- `0x180751424`
- `0x180752abc`
- `0x1807555dc`
- `0x180763d28`
- `0x18077c370`
- `0x180783a20`
- `0x18079a2a4`
- `0x180a372c8`
- `0x180a37718`
- `0x180a38b24`
- `0x1810f6516`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180783acb`
- `KERNEL32!QueryPerformanceCounter` at `0x180783baa`
- `KERNEL32!QueryPerformanceCounter` at `0x180783acb`
- `KERNEL32!QueryPerformanceCounter` at `0x180783baa`
- `KERNEL32!QueryPerformanceFrequency` at `0x180783aba`
- `KERNEL32!QueryPerformanceFrequency` at `0x180783aba`
- `KERNEL32!CreateMutexW` at `0x180783b44`
- `KERNEL32!CreateMutexW` at `0x180783b44`
- `KERNEL32!ReleaseMutex` at `0x180783f6c`
- `KERNEL32!ReleaseMutex` at `0x181101da0`
- `KERNEL32!ReleaseMutex` at `0x180783f6c`
- `KERNEL32!ReleaseMutex` at `0x181101da0`
- `KERNEL32!GetLastError` at `0x180783b60`
- `KERNEL32!GetLastError` at `0x180783d02`
- `KERNEL32!GetLastError` at `0x180783d9f`
- `KERNEL32!GetLastError` at `0x180783eb3`
- `KERNEL32!GetLastError` at `0x180783f46`
- `KERNEL32!GetLastError` at `0x180783b60`
- `KERNEL32!GetLastError` at `0x180783d02`
- `KERNEL32!GetLastError` at `0x180783d9f`
- `KERNEL32!GetLastError` at `0x180783eb3`
- `KERNEL32!GetLastError` at `0x180783f46`
- `KERNEL32!WaitForSingleObject` at `0x180783ccb`
- `KERNEL32!WaitForSingleObject` at `0x180783ccb`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x180783d86`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x180783d86`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180783afc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180783afc`
- `WININET!GetUrlCacheEntryInfoW` at `0x180783cee`
- `WININET!GetUrlCacheEntryInfoW` at `0x180783d5c`
- `WININET!GetUrlCacheEntryInfoW` at `0x180783cee`
- `WININET!GetUrlCacheEntryInfoW` at `0x180783d5c`
- `WININET!CreateUrlCacheEntryW` at `0x180783e6e`
- `WININET!CreateUrlCacheEntryW` at `0x180783e6e`
- `WININET!CommitUrlCacheEntryW` at `0x180783f3a`
- `WININET!CommitUrlCacheEntryW` at `0x180783f3a`

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
  __int64 v10; // rdx
  __int64 v11; // r9
  char Bool; // al
  const unsigned __int16 *v13; // r8
  HANDLE MutexW; // rax
  signed int v15; // eax
  __int64 v16; // r8
  int v18; // r15d
  signed int LastError; // eax
  struct _INTERNET_CACHE_ENTRY_INFOW *v20; // rax
  signed int v21; // eax
  signed int v22; // eax
  LPCWSTR lpszUrlName; // [rsp+58h] [rbp-4F0h] BYREF
  DWORD cbCacheEntryInfo; // [rsp+60h] [rbp-4E8h] BYREF
  int v25; // [rsp+64h] [rbp-4E4h]
  CStorageHelper *v26; // [rsp+68h] [rbp-4E0h] BYREF
  LARGE_INTEGER v27; // [rsp+70h] [rbp-4D8h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+78h] [rbp-4D0h] BYREF
  LARGE_INTEGER Frequency; // [rsp+80h] [rbp-4C8h] BYREF
  _QWORD v30[3]; // [rsp+88h] [rbp-4C0h] BYREF
  _BYTE v31[32]; // [rsp+A0h] [rbp-4A8h] BYREF
  LPCWSTR *p_lpszUrlName; // [rsp+C0h] [rbp-488h]
  __int64 v33; // [rsp+C8h] [rbp-480h]
  CStorageHelper **v34; // [rsp+D0h] [rbp-478h]
  __int64 v35; // [rsp+D8h] [rbp-470h]
  _QWORD *v36; // [rsp+E0h] [rbp-468h]
  __int64 v37; // [rsp+E8h] [rbp-460h]
  WCHAR szFileName[264]; // [rsp+F0h] [rbp-458h] BYREF
  WCHAR Name[264]; // [rsp+300h] [rbp-248h] BYREF

  v26 = this;
  memset_0(szFileName, 0, 0x208u);
  v4 = 0;
  v5 = 0;
  cbCacheEntryInfo = 0;
  lpszUrlName = 0;
  memset_0(Name, 0, 0x208u);
  PerformanceCount.QuadPart = 0;
  v27.QuadPart = 0;
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
      Bool = IEConfiguration_GetBool(536870916, v10, v9, v11);
      v13 = L"Local\\Low%s";
      if ( !Bool )
        v13 = L"Local\\%s";
      DomainStringWithPrefix = StringCchPrintfW(Name, 0x104u, v13, *((_QWORD *)this + 7));
      if ( !DomainStringWithPrefix )
      {
        MutexW = CreateMutexW(0, 0, Name);
        *((_QWORD *)this + 23) = MutexW;
        if ( MutexW )
        {
          v18 = 0;
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
              v25 = 1;
              v18 = 1;
              goto LABEL_28;
            }
            if ( LastError == 122 )
            {
              v20 = (struct _INTERNET_CACHE_ENTRY_INFOW *)MemoryProtection::HeapAlloc<1>(
                                                            g_hProcessHeap,
                                                            cbCacheEntryInfo);
              v5 = (const unsigned __int16 **)v20;
              v30[1] = v20;
              if ( !v20 )
              {
                DomainStringWithPrefix = -2147024882;
                goto LABEL_28;
              }
              if ( GetUrlCacheEntryInfoW(lpszUrlName, v20, &cbCacheEntryInfo) )
              {
                DomainStringWithPrefix = CStr::Set((CStorageHelper *)((char *)this + 192), v5[2]);
                if ( !PathFileExistsW(v5[2]) )
                {
                  v4 = 1;
                  v25 = 1;
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
                      v25 = 1;
                    }
                  }
                }
                if ( v4 )
                {
LABEL_34:
                  if ( !DomainStringWithPrefix )
                  {
                    if ( v18 )
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
                          v21 = GetLastError();
                          DomainStringWithPrefix = v21;
                          if ( v21 > 0 )
                            DomainStringWithPrefix = (unsigned __int16)v21 | 0x80070000;
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
                    if ( v18 )
                    {
                      if ( !DomainStringWithPrefix )
                      {
                        CommitUrlCacheEntryW(lpszUrlName, szFileName, 0, 0, 1u, 0, 0, 0, 0);
                        v22 = GetLastError();
                        DomainStringWithPrefix = v22;
                        if ( v22 > 0 )
                          DomainStringWithPrefix = (unsigned __int16)v22 | 0x80070000;
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
        v15 = GetLastError();
        DomainStringWithPrefix = v15;
        if ( v15 > 0 )
          DomainStringWithPrefix = (unsigned __int16)v15 | 0x80070000;
      }
    }
  }
LABEL_9:
  if ( lpszUrlName )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, (void *)lpszUrlName, v9);
  if ( v5 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v5, v9);
  QueryPerformanceCounter(&v27);
  if ( (unsigned int)dword_18158CCA8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18158CCA8, 0x400000800000LL) )
  {
    v30[0] = v16;
    LODWORD(v26) = v8;
    LODWORD(lpszUrlName) = DomainStringWithPrefix;
    v36 = v30;
    v37 = 8;
    v34 = &v26;
    v35 = 4;
    p_lpszUrlName = &lpszUrlName;
    v33 = 4;
    tlgWriteTransfer_BrowserWriteTransfer(&dword_18158CCA8, byte_18154CBA3, &xmmword_1815C2868, 0, 5, v31);
  }
  return DomainStringWithPrefix;
}

```

## disassembly

```asm
0x180783a20  mov     [rsp+arg_10], rbx
0x180783a25  mov     [rsp+arg_18], rsi
0x180783a2a  push    rdi
0x180783a2b  push    r12
0x180783a2d  push    r13
0x180783a2f  push    r14
0x180783a31  push    r15
0x180783a33  sub     rsp, 520h
0x180783a3a  mov     rax, cs:__security_cookie
0x180783a41  xor     rax, rsp
0x180783a44  mov     [rsp+548h+var_38], rax
0x180783a4c  mov     r12, rdx
0x180783a4f  mov     rdi, rcx
0x180783a52  mov     [rsp+548h+var_4E0], rcx
0x180783a57  mov     ebx, 208h
0x180783a5c  mov     r8d, ebx; Size
0x180783a5f  xor     edx, edx; Val
0x180783a61  lea     rcx, [rsp+548h+szFileName]; void *
0x180783a69  call    memset_0
0x180783a6e  xor     esi, esi
0x180783a70  mov     r14d, esi
0x180783a73  mov     [rsp+548h+cbCacheEntryInfo], esi
0x180783a77  mov     [rsp+548h+lpszUrlName], rsi
0x180783a7c  mov     r8d, ebx; Size
0x180783a7f  xor     edx, edx; Val
0x180783a81  lea     rcx, [rsp+548h+Name]; void *
0x180783a89  call    memset_0
0x180783a8e  mov     qword ptr [rsp+548h+PerformanceCount], rsi
0x180783a93  mov     qword ptr [rsp+548h+var_4D8], rsi
0x180783a98  mov     qword ptr [rsp+548h+Frequency], rsi
0x180783aa0  mov     rcx, r12; this
0x180783aa3  call    ?CleanupEdpStateMachine@CStorageQuotaHelper@@QEAAXXZ; CStorageQuotaHelper::CleanupEdpStateMachine(void)
0x180783aa8  call    ?_EnsureCacheContainer@CStorageHelper@@AEAAJXZ; CStorageHelper::_EnsureCacheContainer(void)
0x180783aad  mov     ebx, eax
0x180783aaf  mov     r13d, eax
0x180783ab2  lea     rcx, [rsp+548h+Frequency]; lpFrequency
0x180783aba  call    cs:__imp_QueryPerformanceFrequency
0x180783ac1  nop     dword ptr [rax+rax+00h]
0x180783ac6  lea     rcx, [rsp+548h+PerformanceCount]; lpPerformanceCount
0x180783acb  call    cs:__imp_QueryPerformanceCounter
0x180783ad2  nop     dword ptr [rax+rax+00h]
0x180783ad7  test    ebx, ebx
0x180783ad9  jnz     loc_180783B7B
0x180783adf  lea     rdx, [rsp+548h+lpszUrlName]; unsigned __int16 **
0x180783ae4  mov     rcx, [rdi+38h]; unsigned __int16 *
0x180783ae8  call    ?GetDomainStringWithPrefix@CStorageUtils@@SAJPEBGPEAPEAG@Z; CStorageUtils::GetDomainStringWithPrefix(ushort const *,ushort * *)
0x180783aed  mov     ebx, eax
0x180783aef  test    eax, eax
0x180783af1  jnz     loc_180783B7B
0x180783af7  mov     ecx, 20000004h
0x180783afc  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180783b03  nop     dword ptr [rax+rax+00h]
0x180783b08  lea     rcx, aLocalS; "Local\\%s"
0x180783b0f  lea     r8, aLocalLowS; "Local\\Low%s"
0x180783b16  test    al, al
0x180783b18  cmovz   r8, rcx; unsigned __int16 *
0x180783b1c  mov     r9, [rdi+38h]
0x180783b20  mov     edx, 104h; unsigned __int64
0x180783b25  lea     rcx, [rsp+548h+Name]; unsigned __int16 *
0x180783b2d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180783b32  mov     ebx, eax
0x180783b34  test    eax, eax
0x180783b36  jnz     short loc_180783B7B
0x180783b38  lea     r8, [rsp+548h+Name]; lpName
0x180783b40  xor     edx, edx; bInitialOwner
0x180783b42  xor     ecx, ecx; lpMutexAttributes
0x180783b44  call    cs:__imp_CreateMutexW
0x180783b4b  nop     dword ptr [rax+rax+00h]
0x180783b50  mov     [rdi+0B8h], rax
0x180783b57  test    rax, rax
0x180783b5a  jnz     loc_180783CC2
0x180783b60  call    cs:__imp_GetLastError
0x180783b67  nop     dword ptr [rax+rax+00h]
0x180783b6c  mov     ebx, eax
0x180783b6e  test    eax, eax
0x180783b70  jle     short loc_180783B7B
0x180783b72  movzx   ebx, ax
0x180783b75  or      ebx, 80070000h
0x180783b7b  mov     rdx, [rsp+548h+lpszUrlName]; void *
0x180783b80  test    rdx, rdx
0x180783b83  jz      short loc_180783B91
0x180783b85  mov     rcx, cs:g_hProcessHeap; this
0x180783b8c  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180783b91  test    r14, r14
0x180783b94  jz      short loc_180783BA5
0x180783b96  mov     rdx, r14; void *
0x180783b99  mov     rcx, cs:g_hProcessHeap; this
0x180783ba0  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180783ba5  lea     rcx, [rsp+548h+var_4D8]; lpPerformanceCount
0x180783baa  call    cs:__imp_QueryPerformanceCounter
0x180783bb1  nop     dword ptr [rax+rax+00h]
0x180783bb6  mov     rax, qword ptr [rsp+548h+var_4D8]
0x180783bbb  sub     rax, qword ptr [rsp+548h+PerformanceCount]
0x180783bc0  imul    rax, 0F4240h
0x180783bc7  cqo
0x180783bc9  idiv    qword ptr [rsp+548h+Frequency]
0x180783bd1  mov     r8, rax
0x180783bd4  mov     ecx, cs:dword_18158CCA8
0x180783bda  cmp     ecx, 5
0x180783bdd  jbe     loc_180783C92
0x180783be3  mov     rdx, 400000800000h
0x180783bed  lea     rcx, dword_18158CCA8
0x180783bf4  call    _tlgKeywordOn
0x180783bf9  test    al, al
0x180783bfb  jz      loc_180783C92
0x180783c01  mov     [rsp+548h+var_4C0], r8
0x180783c09  mov     dword ptr [rsp+548h+var_4E0], r13d
0x180783c0e  mov     dword ptr [rsp+548h+lpszUrlName], ebx
0x180783c12  lea     rax, [rsp+548h+var_4C0]
0x180783c1a  mov     [rsp+548h+var_468], rax
0x180783c22  mov     [rsp+548h+var_460], 8
0x180783c2e  lea     rax, [rsp+548h+var_4E0]
0x180783c33  mov     [rsp+548h+var_478], rax
0x180783c3b  mov     [rsp+548h+var_470], 4
0x180783c47  lea     rax, [rsp+548h+lpszUrlName]
0x180783c4c  mov     [rsp+548h+var_488], rax
0x180783c54  mov     [rsp+548h+var_480], 4
0x180783c60  lea     rax, [rsp+548h+var_4A8]
0x180783c68  mov     [rsp+548h+lpszHeaderInfo], rax
0x180783c6d  mov     [rsp+548h+dwReserved], 5
0x180783c75  xor     r9d, r9d
0x180783c78  lea     r8, xmmword_1815C2868
0x180783c7f  lea     rdx, byte_18154CBA3
0x180783c86  lea     rcx, dword_18158CCA8
0x180783c8d  call    _tlgWriteTransfer_BrowserWriteTransfer
0x180783c92  mov     eax, ebx
0x180783c94  mov     rcx, [rsp+548h+var_38]
0x180783c9c  xor     rcx, rsp; StackCookie
0x180783c9f  call    __security_check_cookie
0x180783ca4  lea     r11, [rsp+548h+var_28]
0x180783cac  mov     rbx, [r11+40h]
0x180783cb0  mov     rsi, [r11+48h]
0x180783cb4  mov     rsp, r11
0x180783cb7  pop     r15
0x180783cb9  pop     r14
0x180783cbb  pop     r13
0x180783cbd  pop     r12
0x180783cbf  pop     rdi
0x180783cc0  retn
0x180783cc2  xor     r15d, r15d
0x180783cc5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180783cc8  mov     rcx, rax; hHandle
0x180783ccb  call    cs:__imp_WaitForSingleObject
0x180783cd2  nop     dword ptr [rax+rax+00h]
0x180783cd7  test    eax, 0FFFFFF7Fh
0x180783cdc  jnz     loc_180783B60
0x180783ce2  lea     r8, [rsp+548h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180783ce7  xor     edx, edx; lpCacheEntryInfo
0x180783ce9  mov     rcx, [rsp+548h+lpszUrlName]; lpszUrlName
0x180783cee  call    cs:__imp_GetUrlCacheEntryInfoW
0x180783cf5  nop     dword ptr [rax+rax+00h]
0x180783cfa  test    eax, eax
0x180783cfc  jnz     loc_180783F65
0x180783d02  call    cs:__imp_GetLastError
0x180783d09  nop     dword ptr [rax+rax+00h]
0x180783d0e  cmp     eax, 2
0x180783d11  jnz     short loc_180783D22
0x180783d13  lea     esi, [rax-1]
0x180783d16  mov     [rsp+548h+var_4E4], esi
0x180783d1a  mov     r15d, esi
0x180783d1d  jmp     loc_180783DBE
0x180783d22  cmp     eax, 7Ah ; 'z'
0x180783d25  jnz     loc_180783EA4
0x180783d2b  mov     edx, [rsp+548h+cbCacheEntryInfo]
0x180783d2f  mov     rcx, cs:g_hProcessHeap
0x180783d36  call    ??$HeapAlloc@$00@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<1>(void *,unsigned __int64)
0x180783d3b  mov     r14, rax
0x180783d3e  mov     [rsp+548h+var_4B8], rax
0x180783d46  test    rax, rax
0x180783d49  jz      loc_180783E9A
0x180783d4f  lea     r8, [rsp+548h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180783d54  mov     rdx, rax; lpCacheEntryInfo
0x180783d57  mov     rcx, [rsp+548h+lpszUrlName]; lpszUrlName
0x180783d5c  call    cs:__imp_GetUrlCacheEntryInfoW
0x180783d63  nop     dword ptr [rax+rax+00h]
0x180783d68  test    eax, eax
0x180783d6a  jz      short loc_180783D9F
0x180783d6c  lea     rcx, [rdi+0C0h]; this
0x180783d73  mov     rdx, [r14+10h]; unsigned __int16 *
0x180783d77  call    ?Set@CStr@@QEAAJPEBG@Z; CStr::Set(ushort const *)
0x180783d7c  mov     ebx, eax
0x180783d7e  mov     [rsp+548h+var_4F8], eax
0x180783d82  mov     rcx, [r14+10h]; pszPath
0x180783d86  call    cs:__imp_PathFileExistsW
0x180783d8d  nop     dword ptr [rax+rax+00h]
0x180783d92  test    eax, eax
0x180783d94  jnz     short loc_180783DBE
0x180783d96  lea     esi, [rax+1]
0x180783d99  mov     [rsp+548h+var_4E4], esi
0x180783d9d  jmp     short loc_180783DBE
0x180783d9f  call    cs:__imp_GetLastError
0x180783da6  nop     dword ptr [rax+rax+00h]
0x180783dab  mov     ebx, eax
0x180783dad  test    eax, eax
0x180783daf  jle     short loc_180783DBA
0x180783db1  movzx   ebx, ax
0x180783db4  or      ebx, 80070000h
0x180783dba  mov     [rsp+548h+var_4F8], ebx
0x180783dbe  test    esi, esi
0x180783dc0  jnz     short loc_180783E2B
0x180783dc2  test    ebx, ebx
0x180783dc4  jnz     short loc_180783E23
0x180783dc6  lea     rdx, [rdi+0C8h]; struct _FILETIME *
0x180783dcd  mov     rcx, [rdi+0C0h]; unsigned __int16 *
0x180783dd4  call    ?GetFileTimeFromName@CStorageUtils@@SAJPEBGPEAU_FILETIME@@@Z; CStorageUtils::GetFileTimeFromName(ushort const *,_FILETIME *)
0x180783dd9  mov     ebx, eax
0x180783ddb  mov     [rsp+548h+var_4F8], eax
0x180783ddf  test    eax, eax
0x180783de1  jnz     short loc_180783E23
0x180783de3  mov     r8, [rdi+0A0h]; struct CStringTable *
0x180783dea  mov     rdx, [rdi+98h]; struct CAryKeyValues *
0x180783df1  mov     rcx, rdi; this
0x180783df4  call    ?_ReadKeyValuesFromFile@CStorageHelper@@AEAAJPEAVCAryKeyValues@@PEAVCStringTable@@@Z; CStorageHelper::_ReadKeyValuesFromFile(CAryKeyValues *,CStringTable *)
0x180783df9  mov     ebx, eax
0x180783dfb  mov     [rsp+548h+var_4F8], eax
0x180783dff  test    eax, eax
0x180783e01  jz      short loc_180783E23
0x180783e03  mov     rdx, [rdi+0A0h]; struct CStringTable *
0x180783e0a  mov     rcx, [rdi+98h]; this
0x180783e11  call    ?EmptyArray@@YAXPEAVCAryKeyValues@@PEAVCStringTable@@@Z; EmptyArray(CAryKeyValues *,CStringTable *)
0x180783e16  xor     ebx, ebx
0x180783e18  mov     [rsp+548h+var_4F8], ebx
0x180783e1c  lea     esi, [rbx+1]
0x180783e1f  mov     [rsp+548h+var_4E4], esi
0x180783e23  test    esi, esi
0x180783e25  jz      loc_180783F65
0x180783e2b  xor     esi, esi
0x180783e2d  test    ebx, ebx
0x180783e2f  jnz     loc_180783F65
0x180783e35  test    r15d, r15d
0x180783e38  jz      loc_180783ED2
0x180783e3e  mov     rdx, [rdi+48h]; unsigned __int16 *
0x180783e42  mov     rcx, r12; this
0x180783e45  call    ?CheckAndUpdateSubdomainLimit@CStorageQuotaHelper@@QEAAJPEAG@Z; CStorageQuotaHelper::CheckAndUpdateSubdomainLimit(ushort *)
0x180783e4a  mov     ebx, eax
0x180783e4c  mov     [rsp+548h+var_4F8], eax
0x180783e50  test    eax, eax
0x180783e52  jnz     short loc_180783ED2
0x180783e54  mov     [rsp+548h+dwReserved], esi; dwReserved
0x180783e58  lea     r9, [rsp+548h+szFileName]; lpszFileName
0x180783e60  lea     r8, szFileExtension; "xml"
0x180783e67  xor     edx, edx; dwExpectedFileSize
0x180783e69  mov     rcx, [rsp+548h+lpszUrlName]; lpszUrlName
0x180783e6e  call    cs:__imp_CreateUrlCacheEntryW
0x180783e75  nop     dword ptr [rax+rax+00h]
0x180783e7a  test    eax, eax
0x180783e7c  jz      short loc_180783EB3
0x180783e7e  lea     rcx, [rdi+0C0h]; this
0x180783e85  lea     rdx, [rsp+548h+szFileName]; unsigned __int16 *
0x180783e8d  call    ?Set@CStr@@QEAAJPEBG@Z; CStr::Set(ushort const *)
0x180783e92  mov     ebx, eax
0x180783e94  mov     [rsp+548h+var_4F8], eax
0x180783e98  jmp     short loc_180783ED2
0x180783e9a  mov     ebx, 8007000Eh
0x180783e9f  jmp     loc_180783DBA
0x180783ea4  test    eax, eax
0x180783ea6  jg      loc_180783DB1
0x180783eac  mov     ebx, eax
0x180783eae  jmp     loc_180783DBA
0x180783eb3  call    cs:__imp_GetLastError
0x180783eba  nop     dword ptr [rax+rax+00h]
0x180783ebf  mov     ebx, eax
0x180783ec1  test    eax, eax
0x180783ec3  jle     short loc_180783ECE
0x180783ec5  movzx   ebx, ax
0x180783ec8  or      ebx, 80070000h
0x180783ece  mov     [rsp+548h+var_4F8], ebx
0x180783ed2  test    ebx, ebx
0x180783ed4  jnz     short loc_180783F03
0x180783ed6  mov     dl, 1; bool
0x180783ed8  mov     rcx, rdi; this
0x180783edb  call    ?_WriteKeyValuesToFile@CStorageHelper@@AEAAJ_N@Z; CStorageHelper::_WriteKeyValuesToFile(bool)
0x180783ee0  mov     ebx, eax
0x180783ee2  mov     [rsp+548h+var_4F8], eax
0x180783ee6  test    eax, eax
0x180783ee8  jnz     short loc_180783F03
0x180783eea  lea     rdx, [rdi+0C8h]; struct _FILETIME *
0x180783ef1  mov     rcx, [rdi+0C0h]; unsigned __int16 *
0x180783ef8  call    ?GetFileTimeFromName@CStorageUtils@@SAJPEBGPEAU_FILETIME@@@Z; CStorageUtils::GetFileTimeFromName(ushort const *,_FILETIME *)
0x180783efd  mov     ebx, eax
0x180783eff  mov     [rsp+548h+var_4F8], eax
0x180783f03  test    r15d, r15d
0x180783f06  jz      short loc_180783F65
0x180783f08  test    ebx, ebx
0x180783f0a  jnz     short loc_180783F65
0x180783f0c  mov     r8, rsi; ExpireTime
0x180783f0f  mov     [rsp+548h+lpszOriginalUrl], rsi; lpszOriginalUrl
0x180783f14  mov     [rsp+548h+lpszFileExtension], rsi; lpszFileExtension
0x180783f19  mov     [rsp+548h+cchHeaderInfo], esi; cchHeaderInfo
0x180783f1d  mov     [rsp+548h+lpszHeaderInfo], rsi; lpszHeaderInfo
0x180783f22  mov     [rsp+548h+dwReserved], 1; CacheEntryType
0x180783f2a  mov     r9, rsi; LastModifiedTime
0x180783f2d  lea     rdx, [rsp+548h+szFileName]; lpszLocalFileName
0x180783f35  mov     rcx, [rsp+548h+lpszUrlName]; lpszUrlName
0x180783f3a  call    cs:__imp_CommitUrlCacheEntryW
0x180783f41  nop     dword ptr [rax+rax+00h]
0x180783f46  call    cs:__imp_GetLastError
0x180783f4d  nop     dword ptr [rax+rax+00h]
0x180783f52  test    eax, eax
0x180783f54  mov     ebx, eax
  ... truncated ...
```
