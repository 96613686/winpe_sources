# CPersistUserData::EnsureCacheContainer(void)

- ea: `0x180a5e08c`
- end: `0x180a5e349`
- name: `?EnsureCacheContainer@CPersistUserData@@AEAAJXZ`
- size: `701`
- prototype: `__int64 __fastcall(CPersistUserData *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180a5ed64`
- `0x180a5f478`

## callees

- `0x180a5e08c`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceW` at `0x180a5e2bd`
- `KERNEL32!GetDiskFreeSpaceW` at `0x180a5e2bd`
- `KERNEL32!GetLastError` at `0x180a5e165`
- `KERNEL32!GetLastError` at `0x180a5e176`
- `KERNEL32!GetLastError` at `0x180a5e1fe`
- `KERNEL32!GetLastError` at `0x180a5e2e8`
- `KERNEL32!GetLastError` at `0x180a5e165`
- `KERNEL32!GetLastError` at `0x180a5e176`
- `KERNEL32!GetLastError` at `0x180a5e1fe`
- `KERNEL32!GetLastError` at `0x180a5e2e8`
- `KERNEL32!LeaveCriticalSection` at `0x180a5e31a`
- `KERNEL32!LeaveCriticalSection` at `0x180a5e31a`
- `KERNEL32!EnterCriticalSection` at `0x180a5e0b9`
- `KERNEL32!EnterCriticalSection` at `0x180a5e0b9`
- `iertutil!__imp_?IEOpStateGetData@@YAJK_NPEA_K@Z` at `0x180a5e12f`
- `iertutil!__imp_?IEOpStateGetData@@YAJK_NPEA_K@Z` at `0x180a5e12f`
- `iertutil!__imp_?IEOpStateSetData@@YAJK_K0@Z` at `0x180a5e19d`
- `iertutil!__imp_?IEOpStateSetData@@YAJK_K0@Z` at `0x180a5e19d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180a5e108`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180a5e256`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180a5e108`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180a5e256`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x180a5e0ed`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x180a5e0ed`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180a5e245`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180a5e245`
- `WININET!CreateUrlCacheContainerW` at `0x180a5e1ee`
- `WININET!CreateUrlCacheContainerW` at `0x180a5e1ee`
- `WININET!DeleteUrlCacheContainerW` at `0x180a5e155`
- `WININET!DeleteUrlCacheContainerW` at `0x180a5e155`

## pseudocode

```c
__int64 __fastcall CPersistUserData::EnsureCacheContainer(CPersistUserData *this)
{
  signed int BrowserProfileDataFilePath; // ebx
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  signed int LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  signed int v9; // eax
  signed int v10; // eax
  DWORD BytesPerSector; // [rsp+40h] [rbp-C0h] BYREF
  DWORD SectorsPerCluster; // [rsp+44h] [rbp-BCh] BYREF
  DWORD NumberOfFreeClusters[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD TotalNumberOfClusters[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR szCachePath[264]; // [rsp+60h] [rbp-A0h] BYREF

  EnterCriticalSection(&CPersistUserData::s_csCacheContainer);
  if ( CPersistUserData::s_bCheckedCacheContainer )
  {
    BrowserProfileDataFilePath = CPersistUserData::s_hrCacheContainer;
  }
  else
  {
    BrowserProfileDataFilePath = GetBrowserProfileDataFilePath(
                                   FilePathStore::BROWSERPROFILEDATA_FILEPATH_UserData,
                                   0,
                                   szCachePath,
                                   260);
    if ( BrowserProfileDataFilePath >= 0 )
    {
      if ( !(unsigned __int8)IEConfiguration_GetBool(536870915, v2, v3, v4) )
        goto LABEL_31;
      *(_QWORD *)NumberOfFreeClusters = 0;
      BrowserProfileDataFilePath = IEOpStateGetData(1u, 0, (unsigned __int64 *)NumberOfFreeClusters);
      if ( BrowserProfileDataFilePath >= 0 )
      {
        if ( (NumberOfFreeClusters[0] & 2) != 0 )
          goto LABEL_31;
        if ( DeleteUrlCacheContainerW(L"UserData", 0) || GetLastError() == 2 )
        {
          BrowserProfileDataFilePath = IEOpStateSetData(1u, 2u, 0);
        }
        else
        {
          LastError = GetLastError();
          BrowserProfileDataFilePath = LastError;
          if ( LastError > 0 )
            BrowserProfileDataFilePath = (unsigned __int16)LastError | 0x80070000;
        }
        if ( BrowserProfileDataFilePath >= 0 )
        {
LABEL_31:
          if ( !CreateUrlCacheContainerW(L"UserData", L"UserData", szCachePath, 0x3E8u, 0, 8u, 0, 0) )
          {
            v9 = GetLastError();
            if ( v9 != 183 )
            {
              if ( v9 > 0 )
                BrowserProfileDataFilePath = (unsigned __int16)v9 | 0x80070000;
              else
                BrowserProfileDataFilePath = v9;
            }
          }
          if ( szCachePath[0] == 47 || szCachePath[0] == 92 )
            PathCchAddBackslash(szCachePath, 0x104u);
          else
            szCachePath[3] = 0;
          if ( (unsigned __int8)IEConfiguration_GetBool(536870915, v6, v7, v8) )
          {
            CPersistUserData::s_dwClusterSizeMinusOne = 1023;
            CPersistUserData::s_dwClusterSizeMask = -1024;
          }
          else
          {
            SectorsPerCluster = 0;
            BytesPerSector = 0;
            NumberOfFreeClusters[0] = 0;
            TotalNumberOfClusters[0] = 0;
            if ( GetDiskFreeSpaceW(
                   szCachePath,
                   &SectorsPerCluster,
                   &BytesPerSector,
                   NumberOfFreeClusters,
                   TotalNumberOfClusters) )
            {
              CPersistUserData::s_dwClusterSizeMinusOne = SectorsPerCluster * BytesPerSector - 1;
              CPersistUserData::s_dwClusterSizeMask = ~CPersistUserData::s_dwClusterSizeMinusOne;
            }
            else
            {
              v10 = GetLastError();
              BrowserProfileDataFilePath = v10;
              if ( v10 > 0 )
                BrowserProfileDataFilePath = (unsigned __int16)v10 | 0x80070000;
            }
          }
        }
      }
    }
  }
  CPersistUserData::s_bCheckedCacheContainer = 1;
  CPersistUserData::s_hrCacheContainer = BrowserProfileDataFilePath;
  LeaveCriticalSection(&CPersistUserData::s_csCacheContainer);
  return (unsigned int)BrowserProfileDataFilePath;
}

```

## disassembly

```asm
0x180a5e08c  mov     [rsp-8+arg_0], rbx
0x180a5e091  push    rbp
0x180a5e092  lea     rbp, [rsp-180h]
0x180a5e09a  sub     rsp, 280h
0x180a5e0a1  mov     rax, cs:__security_cookie
0x180a5e0a8  xor     rax, rsp
0x180a5e0ab  mov     [rbp+180h+var_10], rax
0x180a5e0b2  lea     rcx, ?s_csCacheContainer@CPersistUserData@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180a5e0b9  call    cs:__imp_EnterCriticalSection
0x180a5e0c0  nop     dword ptr [rax+rax+00h]
0x180a5e0c5  cmp     cs:?s_bCheckedCacheContainer@CPersistUserData@@0HA, 0; int CPersistUserData::s_bCheckedCacheContainer
0x180a5e0cc  jz      short loc_180A5E0D9
0x180a5e0ce  mov     ebx, cs:?s_hrCacheContainer@CPersistUserData@@0JA; long CPersistUserData::s_hrCacheContainer
0x180a5e0d4  jmp     loc_180A5E303
0x180a5e0d9  mov     rcx, cs:?BROWSERPROFILEDATA_FILEPATH_UserData@FilePathStore@@3UBROWSERPROFILEDATA_FILEPATHID@1@B; FilePathStore::BROWSERPROFILEDATA_FILEPATHID const FilePathStore::BROWSERPROFILEDATA_FILEPATH_UserData
0x180a5e0e0  lea     r8, [rsp+280h+szCachePath]
0x180a5e0e5  mov     r9d, 104h
0x180a5e0eb  xor     edx, edx
0x180a5e0ed  call    cs:__imp_GetBrowserProfileDataFilePath
0x180a5e0f4  nop     dword ptr [rax+rax+00h]
0x180a5e0f9  mov     ebx, eax
0x180a5e0fb  test    eax, eax
0x180a5e0fd  js      loc_180A5E303
0x180a5e103  mov     ecx, 20000003h
0x180a5e108  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180a5e10f  nop     dword ptr [rax+rax+00h]
0x180a5e114  test    al, al
0x180a5e116  jz      loc_180A5E1B3
0x180a5e11c  xor     edx, edx
0x180a5e11e  mov     qword ptr [rsp+280h+NumberOfFreeClusters], 0
0x180a5e127  lea     r8, [rsp+280h+NumberOfFreeClusters]
0x180a5e12c  lea     ecx, [rdx+1]
0x180a5e12f  call    cs:__imp_?IEOpStateGetData@@YAJK_NPEA_K@Z; IEOpStateGetData(ulong,bool,unsigned __int64 *)
0x180a5e136  nop     dword ptr [rax+rax+00h]
0x180a5e13b  mov     ebx, eax
0x180a5e13d  test    eax, eax
0x180a5e13f  js      loc_180A5E303
0x180a5e145  test    byte ptr [rsp+280h+NumberOfFreeClusters], 2
0x180a5e14a  jnz     short loc_180A5E1B3
0x180a5e14c  xor     edx, edx; dwOptions
0x180a5e14e  lea     rcx, CachePrefix; "UserData"
0x180a5e155  call    cs:__imp_DeleteUrlCacheContainerW
0x180a5e15c  nop     dword ptr [rax+rax+00h]
0x180a5e161  test    eax, eax
0x180a5e163  jnz     short loc_180A5E193
0x180a5e165  call    cs:__imp_GetLastError
0x180a5e16c  nop     dword ptr [rax+rax+00h]
0x180a5e171  cmp     eax, 2
0x180a5e174  jz      short loc_180A5E193
0x180a5e176  call    cs:__imp_GetLastError
0x180a5e17d  nop     dword ptr [rax+rax+00h]
0x180a5e182  mov     ebx, eax
0x180a5e184  test    eax, eax
0x180a5e186  jle     short loc_180A5E1AB
0x180a5e188  movzx   ebx, ax
0x180a5e18b  or      ebx, 80070000h
0x180a5e191  jmp     short loc_180A5E1AB
0x180a5e193  xor     r8d, r8d
0x180a5e196  lea     edx, [r8+2]
0x180a5e19a  lea     ecx, [rdx-1]
0x180a5e19d  call    cs:__imp_?IEOpStateSetData@@YAJK_K0@Z; IEOpStateSetData(ulong,unsigned __int64,unsigned __int64)
0x180a5e1a4  nop     dword ptr [rax+rax+00h]
0x180a5e1a9  mov     ebx, eax
0x180a5e1ab  test    ebx, ebx
0x180a5e1ad  js      loc_180A5E303
0x180a5e1b3  mov     [rsp+280h+cbBuffer], 0; cbBuffer
0x180a5e1bc  lea     r8, [rsp+280h+szCachePath]; lpszCachePath
0x180a5e1c1  mov     [rsp+280h+pvBuffer], 0; pvBuffer
0x180a5e1ca  lea     rdx, CachePrefix; "UserData"
0x180a5e1d1  mov     [rsp+280h+dwOptions], 8; dwOptions
0x180a5e1d9  lea     rcx, CachePrefix; "UserData"
0x180a5e1e0  mov     r9d, 3E8h; KBCacheLimit
0x180a5e1e6  mov     [rsp+280h+dwContainerType], 0; dwContainerType
0x180a5e1ee  call    cs:__imp_CreateUrlCacheContainerW
0x180a5e1f5  nop     dword ptr [rax+rax+00h]
0x180a5e1fa  test    eax, eax
0x180a5e1fc  jnz     short loc_180A5E222
0x180a5e1fe  call    cs:__imp_GetLastError
0x180a5e205  nop     dword ptr [rax+rax+00h]
0x180a5e20a  cmp     eax, 0B7h
0x180a5e20f  jz      short loc_180A5E222
0x180a5e211  test    eax, eax
0x180a5e213  jg      short loc_180A5E219
0x180a5e215  mov     ebx, eax
0x180a5e217  jmp     short loc_180A5E222
0x180a5e219  movzx   ebx, ax
0x180a5e21c  or      ebx, 80070000h
0x180a5e222  cmp     [rsp+280h+szCachePath], 2Fh ; '/'
0x180a5e228  jz      short loc_180A5E23B
0x180a5e22a  cmp     [rsp+280h+szCachePath], 5Ch ; '\'
0x180a5e230  jz      short loc_180A5E23B
0x180a5e232  xor     eax, eax
0x180a5e234  mov     [rsp+280h+var_21A], ax
0x180a5e239  jmp     short loc_180A5E251
0x180a5e23b  mov     edx, 104h; cchPath
0x180a5e240  lea     rcx, [rsp+280h+szCachePath]; pszPath
0x180a5e245  call    cs:__imp_PathCchAddBackslash
0x180a5e24c  nop     dword ptr [rax+rax+00h]
0x180a5e251  mov     ecx, 20000003h
0x180a5e256  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180a5e25d  nop     dword ptr [rax+rax+00h]
0x180a5e262  test    al, al
0x180a5e264  jz      short loc_180A5E27F
0x180a5e266  mov     cs:?s_dwClusterSizeMinusOne@CPersistUserData@@0KA, 3FFh; ulong CPersistUserData::s_dwClusterSizeMinusOne
0x180a5e270  mov     cs:?s_dwClusterSizeMask@CPersistUserData@@0KA, 0FFFFFC00h; ulong CPersistUserData::s_dwClusterSizeMask
0x180a5e27a  jmp     loc_180A5E303
0x180a5e27f  lea     rax, [rsp+280h+TotalNumberOfClusters]
0x180a5e284  mov     [rsp+280h+SectorsPerCluster], 0
0x180a5e28c  lea     r9, [rsp+280h+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x180a5e291  mov     qword ptr [rsp+280h+dwContainerType], rax; lpTotalNumberOfClusters
0x180a5e296  lea     r8, [rsp+280h+BytesPerSector]; lpBytesPerSector
0x180a5e29b  mov     [rsp+280h+BytesPerSector], 0
0x180a5e2a3  lea     rdx, [rsp+280h+SectorsPerCluster]; lpSectorsPerCluster
0x180a5e2a8  mov     [rsp+280h+NumberOfFreeClusters], 0
0x180a5e2b0  lea     rcx, [rsp+280h+szCachePath]; lpRootPathName
0x180a5e2b5  mov     [rsp+280h+TotalNumberOfClusters], 0
0x180a5e2bd  call    cs:__imp_GetDiskFreeSpaceW
0x180a5e2c4  nop     dword ptr [rax+rax+00h]
0x180a5e2c9  test    eax, eax
0x180a5e2cb  jz      short loc_180A5E2E8
0x180a5e2cd  mov     eax, [rsp+280h+BytesPerSector]
0x180a5e2d1  imul    eax, [rsp+280h+SectorsPerCluster]
0x180a5e2d6  dec     eax
0x180a5e2d8  mov     cs:?s_dwClusterSizeMinusOne@CPersistUserData@@0KA, eax; ulong CPersistUserData::s_dwClusterSizeMinusOne
0x180a5e2de  not     eax
0x180a5e2e0  mov     cs:?s_dwClusterSizeMask@CPersistUserData@@0KA, eax; ulong CPersistUserData::s_dwClusterSizeMask
0x180a5e2e6  jmp     short loc_180A5E303
0x180a5e2e8  call    cs:__imp_GetLastError
0x180a5e2ef  nop     dword ptr [rax+rax+00h]
0x180a5e2f4  mov     ebx, eax
0x180a5e2f6  test    eax, eax
0x180a5e2f8  jle     short loc_180A5E303
0x180a5e2fa  movzx   ebx, ax
0x180a5e2fd  or      ebx, 80070000h
0x180a5e303  lea     rcx, ?s_csCacheContainer@CPersistUserData@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180a5e30a  mov     cs:?s_bCheckedCacheContainer@CPersistUserData@@0HA, 1; int CPersistUserData::s_bCheckedCacheContainer
0x180a5e314  mov     cs:?s_hrCacheContainer@CPersistUserData@@0JA, ebx; long CPersistUserData::s_hrCacheContainer
0x180a5e31a  call    cs:__imp_LeaveCriticalSection
0x180a5e321  nop     dword ptr [rax+rax+00h]
0x180a5e326  mov     eax, ebx
0x180a5e328  mov     rcx, [rbp+180h+var_10]
0x180a5e32f  xor     rcx, rsp; StackCookie
0x180a5e332  call    __security_check_cookie
0x180a5e337  mov     rbx, [rsp+280h+arg_0]
0x180a5e33f  add     rsp, 280h
0x180a5e346  pop     rbp
0x180a5e347  retn
```
