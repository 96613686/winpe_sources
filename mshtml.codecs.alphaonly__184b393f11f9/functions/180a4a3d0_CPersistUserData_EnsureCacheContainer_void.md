# CPersistUserData::EnsureCacheContainer(void)

- ea: `0x180a4a3d0`
- end: `0x180a4a62b`
- name: `?EnsureCacheContainer@CPersistUserData@@AEAAJXZ`
- size: `603`
- prototype: `__int64 __fastcall(CPersistUserData *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180a4afc4`
- `0x180a4b640`

## callees

- `0x180a4a3d0`
- `0x1810c2d60`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceW` at `0x180a4a5b2`
- `KERNEL32!GetDiskFreeSpaceW` at `0x180a4a5b2`
- `KERNEL32!GetLastError` at `0x180a4a487`
- `KERNEL32!GetLastError` at `0x180a4a492`
- `KERNEL32!GetLastError` at `0x180a4a508`
- `KERNEL32!GetLastError` at `0x180a4a5d7`
- `KERNEL32!GetLastError` at `0x180a4a487`
- `KERNEL32!GetLastError` at `0x180a4a492`
- `KERNEL32!GetLastError` at `0x180a4a508`
- `KERNEL32!GetLastError` at `0x180a4a5d7`
- `KERNEL32!LeaveCriticalSection` at `0x180a4a603`
- `KERNEL32!LeaveCriticalSection` at `0x180a4a603`
- `KERNEL32!EnterCriticalSection` at `0x180a4a3fd`
- `KERNEL32!EnterCriticalSection` at `0x180a4a3fd`
- `iertutil!__imp_?IEOpStateGetData@@YAJK_NPEA_K@Z` at `0x180a4a45d`
- `iertutil!__imp_?IEOpStateGetData@@YAJK_NPEA_K@Z` at `0x180a4a45d`
- `iertutil!__imp_?IEOpStateSetData@@YAJK_K0@Z` at `0x180a4a4b3`
- `iertutil!__imp_?IEOpStateSetData@@YAJK_K0@Z` at `0x180a4a4b3`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180a4a440`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180a4a554`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180a4a440`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180a4a554`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x180a4a42b`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x180a4a42b`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180a4a549`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180a4a549`
- `WININET!CreateUrlCacheContainerW` at `0x180a4a4fe`
- `WININET!CreateUrlCacheContainerW` at `0x180a4a4fe`
- `WININET!DeleteUrlCacheContainerW` at `0x180a4a47d`
- `WININET!DeleteUrlCacheContainerW` at `0x180a4a47d`

## pseudocode

```c
__int64 __fastcall CPersistUserData::EnsureCacheContainer(CPersistUserData *this)
{
  signed int BrowserProfileDataFilePath; // ebx
  signed int LastError; // eax
  signed int v3; // eax
  signed int v4; // eax
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
      if ( !(unsigned __int8)IEConfiguration_GetBool(536870915) )
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
            v3 = GetLastError();
            if ( v3 != 183 )
            {
              if ( v3 > 0 )
                BrowserProfileDataFilePath = (unsigned __int16)v3 | 0x80070000;
              else
                BrowserProfileDataFilePath = v3;
            }
          }
          if ( szCachePath[0] == 47 || szCachePath[0] == 92 )
            PathCchAddBackslash(szCachePath, 0x104u);
          else
            szCachePath[3] = 0;
          if ( (unsigned __int8)IEConfiguration_GetBool(536870915) )
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
              v4 = GetLastError();
              BrowserProfileDataFilePath = v4;
              if ( v4 > 0 )
                BrowserProfileDataFilePath = (unsigned __int16)v4 | 0x80070000;
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
0x180a4a3d0  mov     [rsp-8+arg_0], rbx
0x180a4a3d5  push    rbp
0x180a4a3d6  lea     rbp, [rsp-180h]
0x180a4a3de  sub     rsp, 280h
0x180a4a3e5  mov     rax, cs:__security_cookie
0x180a4a3ec  xor     rax, rsp
0x180a4a3ef  mov     [rbp+180h+var_10], rax
0x180a4a3f6  lea     rcx, ?s_csCacheContainer@CPersistUserData@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180a4a3fd  call    cs:__imp_EnterCriticalSection
0x180a4a403  cmp     cs:?s_bCheckedCacheContainer@CPersistUserData@@0HA, 0; int CPersistUserData::s_bCheckedCacheContainer
0x180a4a40a  jz      short loc_180A4A417
0x180a4a40c  mov     ebx, cs:?s_hrCacheContainer@CPersistUserData@@0JA; long CPersistUserData::s_hrCacheContainer
0x180a4a412  jmp     loc_180A4A5EC
0x180a4a417  mov     rcx, cs:?BROWSERPROFILEDATA_FILEPATH_UserData@FilePathStore@@3UBROWSERPROFILEDATA_FILEPATHID@1@B; FilePathStore::BROWSERPROFILEDATA_FILEPATHID const FilePathStore::BROWSERPROFILEDATA_FILEPATH_UserData
0x180a4a41e  lea     r8, [rsp+280h+szCachePath]
0x180a4a423  mov     r9d, 104h
0x180a4a429  xor     edx, edx
0x180a4a42b  call    cs:__imp_GetBrowserProfileDataFilePath
0x180a4a431  mov     ebx, eax
0x180a4a433  test    eax, eax
0x180a4a435  js      loc_180A4A5EC
0x180a4a43b  mov     ecx, 20000003h
0x180a4a440  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180a4a446  test    al, al
0x180a4a448  jz      short loc_180A4A4C3
0x180a4a44a  xor     edx, edx
0x180a4a44c  mov     qword ptr [rsp+280h+NumberOfFreeClusters], 0
0x180a4a455  lea     r8, [rsp+280h+NumberOfFreeClusters]
0x180a4a45a  lea     ecx, [rdx+1]
0x180a4a45d  call    cs:__imp_?IEOpStateGetData@@YAJK_NPEA_K@Z; IEOpStateGetData(ulong,bool,unsigned __int64 *)
0x180a4a463  mov     ebx, eax
0x180a4a465  test    eax, eax
0x180a4a467  js      loc_180A4A5EC
0x180a4a46d  test    byte ptr [rsp+280h+NumberOfFreeClusters], 2
0x180a4a472  jnz     short loc_180A4A4C3
0x180a4a474  xor     edx, edx; dwOptions
0x180a4a476  lea     rcx, CachePrefix; "UserData"
0x180a4a47d  call    cs:__imp_DeleteUrlCacheContainerW
0x180a4a483  test    eax, eax
0x180a4a485  jnz     short loc_180A4A4A9
0x180a4a487  call    cs:__imp_GetLastError
0x180a4a48d  cmp     eax, 2
0x180a4a490  jz      short loc_180A4A4A9
0x180a4a492  call    cs:__imp_GetLastError
0x180a4a498  mov     ebx, eax
0x180a4a49a  test    eax, eax
0x180a4a49c  jle     short loc_180A4A4BB
0x180a4a49e  movzx   ebx, ax
0x180a4a4a1  or      ebx, 80070000h
0x180a4a4a7  jmp     short loc_180A4A4BB
0x180a4a4a9  xor     r8d, r8d
0x180a4a4ac  lea     edx, [r8+2]
0x180a4a4b0  lea     ecx, [rdx-1]
0x180a4a4b3  call    cs:__imp_?IEOpStateSetData@@YAJK_K0@Z; IEOpStateSetData(ulong,unsigned __int64,unsigned __int64)
0x180a4a4b9  mov     ebx, eax
0x180a4a4bb  test    ebx, ebx
0x180a4a4bd  js      loc_180A4A5EC
0x180a4a4c3  mov     [rsp+280h+cbBuffer], 0; cbBuffer
0x180a4a4cc  lea     r8, [rsp+280h+szCachePath]; lpszCachePath
0x180a4a4d1  mov     [rsp+280h+pvBuffer], 0; pvBuffer
0x180a4a4da  lea     rdx, CachePrefix; "UserData"
0x180a4a4e1  mov     [rsp+280h+dwOptions], 8; dwOptions
0x180a4a4e9  lea     rcx, CachePrefix; "UserData"
0x180a4a4f0  mov     r9d, 3E8h; KBCacheLimit
0x180a4a4f6  mov     [rsp+280h+dwContainerType], 0; dwContainerType
0x180a4a4fe  call    cs:__imp_CreateUrlCacheContainerW
0x180a4a504  test    eax, eax
0x180a4a506  jnz     short loc_180A4A526
0x180a4a508  call    cs:__imp_GetLastError
0x180a4a50e  cmp     eax, 0B7h
0x180a4a513  jz      short loc_180A4A526
0x180a4a515  test    eax, eax
0x180a4a517  jg      short loc_180A4A51D
0x180a4a519  mov     ebx, eax
0x180a4a51b  jmp     short loc_180A4A526
0x180a4a51d  movzx   ebx, ax
0x180a4a520  or      ebx, 80070000h
0x180a4a526  cmp     [rsp+280h+szCachePath], 2Fh ; '/'
0x180a4a52c  jz      short loc_180A4A53F
0x180a4a52e  cmp     [rsp+280h+szCachePath], 5Ch ; '\'
0x180a4a534  jz      short loc_180A4A53F
0x180a4a536  xor     eax, eax
0x180a4a538  mov     [rsp+280h+var_21A], ax
0x180a4a53d  jmp     short loc_180A4A54F
0x180a4a53f  mov     edx, 104h; cchPath
0x180a4a544  lea     rcx, [rsp+280h+szCachePath]; pszPath
0x180a4a549  call    cs:__imp_PathCchAddBackslash
0x180a4a54f  mov     ecx, 20000003h
0x180a4a554  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180a4a55a  test    al, al
0x180a4a55c  jz      short loc_180A4A574
0x180a4a55e  mov     cs:?s_dwClusterSizeMinusOne@CPersistUserData@@0KA, 3FFh; ulong CPersistUserData::s_dwClusterSizeMinusOne
0x180a4a568  mov     cs:?s_dwClusterSizeMask@CPersistUserData@@0KA, 0FFFFFC00h; ulong CPersistUserData::s_dwClusterSizeMask
0x180a4a572  jmp     short loc_180A4A5EC
0x180a4a574  lea     rax, [rsp+280h+TotalNumberOfClusters]
0x180a4a579  mov     [rsp+280h+SectorsPerCluster], 0
0x180a4a581  lea     r9, [rsp+280h+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x180a4a586  mov     qword ptr [rsp+280h+dwContainerType], rax; lpTotalNumberOfClusters
0x180a4a58b  lea     r8, [rsp+280h+BytesPerSector]; lpBytesPerSector
0x180a4a590  mov     [rsp+280h+BytesPerSector], 0
0x180a4a598  lea     rdx, [rsp+280h+SectorsPerCluster]; lpSectorsPerCluster
0x180a4a59d  mov     [rsp+280h+NumberOfFreeClusters], 0
0x180a4a5a5  lea     rcx, [rsp+280h+szCachePath]; lpRootPathName
0x180a4a5aa  mov     [rsp+280h+TotalNumberOfClusters], 0
0x180a4a5b2  call    cs:__imp_GetDiskFreeSpaceW
0x180a4a5b8  test    eax, eax
0x180a4a5ba  jz      short loc_180A4A5D7
0x180a4a5bc  mov     eax, [rsp+280h+BytesPerSector]
0x180a4a5c0  imul    eax, [rsp+280h+SectorsPerCluster]
0x180a4a5c5  dec     eax
0x180a4a5c7  mov     cs:?s_dwClusterSizeMinusOne@CPersistUserData@@0KA, eax; ulong CPersistUserData::s_dwClusterSizeMinusOne
0x180a4a5cd  not     eax
0x180a4a5cf  mov     cs:?s_dwClusterSizeMask@CPersistUserData@@0KA, eax; ulong CPersistUserData::s_dwClusterSizeMask
0x180a4a5d5  jmp     short loc_180A4A5EC
0x180a4a5d7  call    cs:__imp_GetLastError
0x180a4a5dd  mov     ebx, eax
0x180a4a5df  test    eax, eax
0x180a4a5e1  jle     short loc_180A4A5EC
0x180a4a5e3  movzx   ebx, ax
0x180a4a5e6  or      ebx, 80070000h
0x180a4a5ec  lea     rcx, ?s_csCacheContainer@CPersistUserData@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180a4a5f3  mov     cs:?s_bCheckedCacheContainer@CPersistUserData@@0HA, 1; int CPersistUserData::s_bCheckedCacheContainer
0x180a4a5fd  mov     cs:?s_hrCacheContainer@CPersistUserData@@0JA, ebx; long CPersistUserData::s_hrCacheContainer
0x180a4a603  call    cs:__imp_LeaveCriticalSection
0x180a4a609  mov     eax, ebx
0x180a4a60b  mov     rcx, [rbp+180h+var_10]
0x180a4a612  xor     rcx, rsp; StackCookie
0x180a4a615  call    __security_check_cookie
0x180a4a61a  mov     rbx, [rsp+280h+arg_0]
0x180a4a622  add     rsp, 280h
0x180a4a629  pop     rbp
0x180a4a62a  retn
```
