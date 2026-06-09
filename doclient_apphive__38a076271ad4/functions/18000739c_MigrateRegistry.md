# MigrateRegistry

- ea: `0x18000739c`
- end: `0x180007823`
- name: `MigrateRegistry`
- size: `1159`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180004ef0`
- `0x18000516c`

## callees

- `0x18000739c`
- `0x1800084f0`
- `0x1800089f8`
- `0x1800095a0`
- `0x18009b290`
- `0x18009b538`
- `0x1800a1ea4`
- `0x1800a49c4`
- `0x1800a4e18`
- `0x1800a5c88`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyA` at `0x180007486`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyA` at `0x1800076ac`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyA` at `0x180007486`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyA` at `0x1800076ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800074c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007561`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007601`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800076e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800076f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007770`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007781`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800077a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800077e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800074c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007561`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007601`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800076e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800076f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007770`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007781`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800077a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800077e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800075c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800075c6`
- `api-ms-win-shcore-registry-l1-1-0!SHCopyKeyA` at `0x180007510`
- `api-ms-win-shcore-registry-l1-1-0!SHCopyKeyA` at `0x18000771f`
- `api-ms-win-shcore-registry-l1-1-0!SHCopyKeyA` at `0x180007510`
- `api-ms-win-shcore-registry-l1-1-0!SHCopyKeyA` at `0x18000771f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsA` at `0x18000766e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsA` at `0x18000766e`

## string_xrefs

- `0x180007413`: `C:\__w\1\s\src\DeliveryOptimization\dll\dosvc.cpp`
- `0x1800074a4`: `C:\__w\1\s\src\DeliveryOptimization\dll\dosvc.cpp`
- `0x180007544`: `C:\__w\1\s\src\DeliveryOptimization\dll\dosvc.cpp`
- `0x1800075e4`: `C:\__w\1\s\src\DeliveryOptimization\dll\dosvc.cpp`
- `0x1800076ca`: `C:\__w\1\s\src\DeliveryOptimization\dll\dosvc.cpp`
- `0x180007753`: `C:\__w\1\s\src\DeliveryOptimization\dll\dosvc.cpp`
- `0x180007404`: `Failed to get DO state path`
- `0x180007535`: `Failed to migrate DO registry into %hs`
- `0x1800075d5`: `Failed to open DO root reg key`
- `0x180007744`: `Failed to migrate DO registry from %hs`
- `0x1800077be`: `DO registry migration file not found: %s`
- `0x1800077cb`: `MigrateRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall MigrateRegistry(char a1)
{
  int StatePath; // ebx
  const char *v4; // rcx
  const CHAR *v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  HKEY v8; // rdi
  struct CPersistenceLocation *v9; // rax
  const CHAR *v10; // rbx
  struct CPersistenceLocation *v11; // rax
  unsigned int v12; // eax
  const char *v13; // rdx
  struct CPersistenceLocation *v14; // rax
  const CHAR *v15; // rbx
  struct CPersistenceLocation *v16; // rax
  unsigned int v17; // eax
  const CHAR *v18; // rcx
  const CHAR *v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // eax
  const char *v22; // rdx
  const char *v23; // rax
  char *v24; // [rsp+28h] [rbp-50h]
  HKEY phkResult; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v26; // [rsp+38h] [rbp-40h] BYREF
  LPCSTR lpFile[2]; // [rsp+40h] [rbp-38h] BYREF
  __m128i si128; // [rsp+50h] [rbp-28h]
  HKEY hKey; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( *((_BYTE *)CPersistenceLocation::Instance() + 160) )
    return 0;
  *(_OWORD *)lpFile = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(lpFile[0]) = 0;
  StatePath = CPersistenceLocation::GetStatePath("migration.dat", lpFile);
  if ( StatePath < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2EB,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
      (const char *)(unsigned int)StatePath,
      (int)"Failed to get DO state path",
      v24);
    std::string::~string(lpFile);
    return (unsigned int)StatePath;
  }
  if ( a1 )
  {
    v4 = (const char *)lpFile;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v4 = lpFile[0];
    CFile::Delete(v4);
    phkResult = 0;
    v5 = (const CHAR *)lpFile;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v5 = lpFile[0];
    v6 = RegLoadAppKeyA(v5, &phkResult, 0xF003Fu, 0, 0);
    if ( v6 )
    {
      v7 = wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x2F3,
             (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
             (const char *)v6,
             (unsigned int)"Error with RegLoadAppKey",
             v24);
      if ( phkResult )
        RegCloseKey(phkResult);
LABEL_47:
      std::string::~string(lpFile);
      return v7;
    }
    v8 = phkResult;
    v9 = CPersistenceLocation::Instance();
    v10 = (const CHAR *)v9;
    if ( *((_QWORD *)v9 + 3) > 0xFu )
      v10 = *(const CHAR **)v9;
    v11 = CPersistenceLocation::Instance();
    v12 = SHCopyKeyA((HKEY)(-(__int64)(*((_BYTE *)v11 + 160) != 0) - 2147483645), v10, v8, 0);
    if ( v12 )
    {
      v13 = (const char *)lpFile;
      if ( si128.m128i_i64[1] > 0xFuLL )
        v13 = lpFile[0];
      v7 = wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x2F9,
             (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
             (const char *)v12,
             (unsigned int)"Failed to migrate DO registry into %hs",
             v13);
      if ( phkResult )
        RegCloseKey(phkResult);
      goto LABEL_47;
    }
  }
  else
  {
    phkResult = 0;
    v14 = CPersistenceLocation::Instance();
    v15 = (const CHAR *)v14;
    if ( *((_QWORD *)v14 + 3) > 0xFu )
      v15 = *(const CHAR **)v14;
    v16 = CPersistenceLocation::Instance();
    v17 = RegOpenKeyExA((HKEY)(-(__int64)(*((_BYTE *)v16 + 160) != 0) - 2147483645), v15, 0, 0x2001Fu, &phkResult);
    if ( v17 )
    {
      v7 = wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x2FF,
             (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
             (const char *)v17,
             (unsigned int)"Failed to open DO root reg key",
             v24);
      if ( phkResult )
        RegCloseKey(phkResult);
      goto LABEL_47;
    }
    v26 = 0;
    RegQueryDwordValue(phkResult, 0, "Migrated", &v26);
    if ( !v26 )
    {
      RegSetDwordValue(phkResult, 0, "Migrated", 1u);
      v18 = (const CHAR *)lpFile;
      if ( si128.m128i_i64[1] > 0xFuLL )
        v18 = lpFile[0];
      if ( PathFileExistsA(v18) )
      {
        hKey = 0;
        v19 = (const CHAR *)lpFile;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v19 = lpFile[0];
        v20 = RegLoadAppKeyA(v19, &hKey, 0xF003Fu, 0, 0);
        if ( v20 )
        {
          v7 = wil::details::in1diag3::Return_Win32Msg(
                 retaddr,
                 (void *)0x30A,
                 (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
                 (const char *)v20,
                 (unsigned int)"RegLoadAppKey failed",
                 v24);
          if ( hKey )
            RegCloseKey(hKey);
          if ( phkResult )
            RegCloseKey(phkResult);
          goto LABEL_47;
        }
        v21 = SHCopyKeyA(hKey, 0, phkResult, 0);
        if ( v21 )
        {
          v22 = (const char *)lpFile;
          if ( si128.m128i_i64[1] > 0xFuLL )
            v22 = lpFile[0];
          v7 = wil::details::in1diag3::Return_Win32Msg(
                 retaddr,
                 (void *)0x30F,
                 (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
                 (const char *)v21,
                 (unsigned int)"Failed to migrate DO registry from %hs",
                 v22);
          if ( hKey )
            RegCloseKey(hKey);
          if ( phkResult )
            RegCloseKey(phkResult);
          goto LABEL_47;
        }
        if ( hKey )
          RegCloseKey(hKey);
      }
      else
      {
        v23 = (const char *)lpFile;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v23 = lpFile[0];
        LogMessage(4u, "MigrateRegistry", 0x313u, "DO registry migration file not found: %s", v23);
      }
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  std::string::~string(lpFile);
  return 0;
}

```

## disassembly

```asm
0x18000739c  mov     [rsp+arg_0], rbx
0x1800073a1  push    rdi
0x1800073a2  sub     rsp, 70h
0x1800073a6  mov     rax, cs:__security_cookie
0x1800073ad  xor     rax, rsp
0x1800073b0  mov     [rsp+78h+var_10], rax
0x1800073b5  mov     dil, cl
0x1800073b8  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800073bd  cmp     byte ptr [rax+0A0h], 0
0x1800073c4  jz      short loc_1800073CD
0x1800073c6  xor     eax, eax
0x1800073c8  jmp     loc_180007807
0x1800073cd  xorps   xmm0, xmm0
0x1800073d0  movups  xmmword ptr [rsp+78h+lpFile], xmm0
0x1800073d5  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800073dd  movdqu  [rsp+78h+var_28], xmm1
0x1800073e3  mov     byte ptr [rsp+78h+lpFile], 0
0x1800073e8  lea     rdx, [rsp+78h+lpFile]
0x1800073ed  lea     rcx, aMigrationDat; "migration.dat"
0x1800073f4  call    ?GetStatePath@CPersistenceLocation@@SAJPEBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CPersistenceLocation::GetStatePath(char const *,std::string &)
0x1800073f9  mov     ebx, eax
0x1800073fb  test    eax, eax
0x1800073fd  jns     short loc_180007436
0x1800073ff  mov     rcx, [rsp+78h]; this
0x180007404  lea     rax, aFailedToGetDoS; "Failed to get DO state path"
0x18000740b  mov     qword ptr [rsp+78h+Reserved], rax; int
0x180007410  mov     r9d, ebx; char *
0x180007413  lea     r8, aCW1SSrcDeliver_56; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000741a  mov     edx, 2EBh; void *
0x18000741f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180007424  nop
0x180007425  lea     rcx, [rsp+78h+lpFile]; void *
0x18000742a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000742f  mov     eax, ebx
0x180007431  jmp     loc_180007807
0x180007436  test    dil, dil
0x180007439  jz      loc_18000757E
0x18000743f  lea     rcx, [rsp+78h+lpFile]
0x180007444  cmp     qword ptr [rsp+78h+var_28+8], 0Fh
0x18000744a  cmova   rcx, [rsp+78h+lpFile]; char *
0x180007450  call    ?Delete@CFile@@SAJPEBD@Z; CFile::Delete(char const *)
0x180007455  nop
0x180007456  mov     [rsp+78h+phkResult], 0
0x18000745f  lea     rcx, [rsp+78h+lpFile]
0x180007464  cmp     qword ptr [rsp+78h+var_28+8], 0Fh
0x18000746a  cmova   rcx, [rsp+78h+lpFile]; lpFile
0x180007470  mov     [rsp+78h+Reserved], 0; Reserved
0x180007478  xor     r9d, r9d; dwOptions
0x18000747b  mov     r8d, 0F003Fh; samDesired
0x180007481  lea     rdx, [rsp+78h+phkResult]; phkResult
0x180007486  call    cs:__imp_RegLoadAppKeyA
0x18000748c  test    eax, eax
0x18000748e  jz      short loc_1800074D9
0x180007490  mov     rcx, [rsp+78h]; this
0x180007495  lea     rdx, aErrorWithReglo; "Error with RegLoadAppKey"
0x18000749c  mov     qword ptr [rsp+78h+Reserved], rdx; unsigned int
0x1800074a1  mov     r9d, eax; char *
0x1800074a4  lea     r8, aCW1SSrcDeliver_56; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800074ab  mov     edx, 2F3h; void *
0x1800074b0  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800074b5  mov     ebx, eax
0x1800074b7  mov     rcx, [rsp+78h+phkResult]; hKey
0x1800074bc  test    rcx, rcx
0x1800074bf  jz      short loc_1800074C8
0x1800074c1  call    cs:__imp_RegCloseKey
0x1800074c7  nop
0x1800074c8  lea     rcx, [rsp+78h+lpFile]; void *
0x1800074cd  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800074d2  mov     eax, ebx
0x1800074d4  jmp     loc_180007807
0x1800074d9  mov     rdi, [rsp+78h+phkResult]
0x1800074de  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800074e3  mov     rbx, rax
0x1800074e6  cmp     qword ptr [rax+18h], 0Fh
0x1800074eb  jbe     short loc_1800074F0
0x1800074ed  mov     rbx, [rax]
0x1800074f0  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800074f5  mov     al, [rax+0A0h]
0x1800074fb  neg     al
0x1800074fd  sbb     rcx, rcx
0x180007500  add     rcx, 0FFFFFFFF80000003h; hkeySrc
0x180007507  xor     r9d, r9d; fReserved
0x18000750a  mov     r8, rdi; hkeyDest
0x18000750d  mov     rdx, rbx; pszSrcSubKey
0x180007510  call    cs:__imp_SHCopyKeyA
0x180007516  test    eax, eax
0x180007518  jz      short loc_180007579
0x18000751a  lea     rdx, [rsp+78h+lpFile]
0x18000751f  cmp     qword ptr [rsp+78h+var_28+8], 0Fh
0x180007525  cmova   rdx, [rsp+78h+lpFile]
0x18000752b  mov     rcx, [rsp+78h]; this
0x180007530  mov     [rsp+78h+var_50], rdx; char *
0x180007535  lea     rdx, aFailedToMigrat; "Failed to migrate DO registry into %hs"
0x18000753c  mov     qword ptr [rsp+78h+Reserved], rdx; unsigned int
0x180007541  mov     r9d, eax; char *
0x180007544  lea     r8, aCW1SSrcDeliver_56; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000754b  mov     edx, 2F9h; void *
0x180007550  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180007555  mov     ebx, eax
0x180007557  mov     rcx, [rsp+78h+phkResult]; hKey
0x18000755c  test    rcx, rcx
0x18000755f  jz      short loc_180007568
0x180007561  call    cs:__imp_RegCloseKey
0x180007567  nop
0x180007568  lea     rcx, [rsp+78h+lpFile]; void *
0x18000756d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180007572  mov     eax, ebx
0x180007574  jmp     loc_180007807
0x180007579  jmp     loc_1800077DD
0x18000757e  mov     [rsp+78h+phkResult], 0
0x180007587  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18000758c  mov     rbx, rax
0x18000758f  cmp     qword ptr [rax+18h], 0Fh
0x180007594  jbe     short loc_180007599
0x180007596  mov     rbx, [rax]
0x180007599  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18000759e  mov     al, [rax+0A0h]
0x1800075a4  neg     al
0x1800075a6  sbb     rcx, rcx
0x1800075a9  add     rcx, 0FFFFFFFF80000003h; hKey
0x1800075b0  lea     rax, [rsp+78h+phkResult]
0x1800075b5  mov     qword ptr [rsp+78h+Reserved], rax; phkResult
0x1800075ba  mov     r9d, 2001Fh; samDesired
0x1800075c0  xor     r8d, r8d; ulOptions
0x1800075c3  mov     rdx, rbx; lpSubKey
0x1800075c6  call    cs:__imp_RegOpenKeyExA
0x1800075cc  test    eax, eax
0x1800075ce  jz      short loc_180007619
0x1800075d0  mov     rcx, [rsp+78h]; this
0x1800075d5  lea     rdx, aFailedToOpenDo_0; "Failed to open DO root reg key"
0x1800075dc  mov     qword ptr [rsp+78h+Reserved], rdx; unsigned int
0x1800075e1  mov     r9d, eax; char *
0x1800075e4  lea     r8, aCW1SSrcDeliver_56; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800075eb  mov     edx, 2FFh; void *
0x1800075f0  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800075f5  mov     ebx, eax
0x1800075f7  mov     rcx, [rsp+78h+phkResult]; hKey
0x1800075fc  test    rcx, rcx
0x1800075ff  jz      short loc_180007608
0x180007601  call    cs:__imp_RegCloseKey
0x180007607  nop
0x180007608  lea     rcx, [rsp+78h+lpFile]; void *
0x18000760d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180007612  mov     eax, ebx
0x180007614  jmp     loc_180007807
0x180007619  mov     [rsp+78h+var_40], 0
0x180007621  lea     r9, [rsp+78h+var_40]; unsigned int *
0x180007626  lea     r8, ValueName; "Migrated"
0x18000762d  xor     edx, edx; char *
0x18000762f  mov     rcx, [rsp+78h+phkResult]; HKEY
0x180007634  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEBD1PEAI@Z; RegQueryDwordValue(HKEY__ *,char const *,char const *,uint *)
0x180007639  cmp     [rsp+78h+var_40], 0
0x18000763e  jnz     loc_1800077DD
0x180007644  mov     r9d, 1; unsigned int
0x18000764a  lea     r8, ValueName; "Migrated"
0x180007651  xor     edx, edx; char *
0x180007653  mov     rcx, [rsp+78h+phkResult]; HKEY
0x180007658  call    ?RegSetDwordValue@@YAJPEAUHKEY__@@PEBD1I@Z; RegSetDwordValue(HKEY__ *,char const *,char const *,uint)
0x18000765d  lea     rcx, [rsp+78h+lpFile]
0x180007662  cmp     qword ptr [rsp+78h+var_28+8], 0Fh
0x180007668  cmova   rcx, [rsp+78h+lpFile]; pszPath
0x18000766e  call    cs:__imp_PathFileExistsA
0x180007674  test    eax, eax
0x180007676  jz      loc_1800077A8
0x18000767c  mov     [rsp+78h+hKey], 0
0x180007685  lea     rcx, [rsp+78h+lpFile]
0x18000768a  cmp     qword ptr [rsp+78h+var_28+8], 0Fh
0x180007690  cmova   rcx, [rsp+78h+lpFile]; lpFile
0x180007696  mov     [rsp+78h+Reserved], 0; Reserved
0x18000769e  xor     r9d, r9d; dwOptions
0x1800076a1  mov     r8d, 0F003Fh; samDesired
0x1800076a7  lea     rdx, [rsp+78h+hKey]; phkResult
0x1800076ac  call    cs:__imp_RegLoadAppKeyA
0x1800076b2  test    eax, eax
0x1800076b4  jz      short loc_180007710
0x1800076b6  mov     rcx, [rsp+78h]; this
0x1800076bb  lea     rdx, aRegloadappkeyF; "RegLoadAppKey failed"
0x1800076c2  mov     qword ptr [rsp+78h+Reserved], rdx; unsigned int
0x1800076c7  mov     r9d, eax; char *
0x1800076ca  lea     r8, aCW1SSrcDeliver_56; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800076d1  mov     edx, 30Ah; void *
0x1800076d6  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800076db  mov     ebx, eax
0x1800076dd  mov     rcx, [rsp+78h+hKey]; hKey
0x1800076e2  test    rcx, rcx
0x1800076e5  jz      short loc_1800076EE
0x1800076e7  call    cs:__imp_RegCloseKey
0x1800076ed  nop
0x1800076ee  mov     rcx, [rsp+78h+phkResult]; hKey
0x1800076f3  test    rcx, rcx
0x1800076f6  jz      short loc_1800076FF
0x1800076f8  call    cs:__imp_RegCloseKey
0x1800076fe  nop
0x1800076ff  lea     rcx, [rsp+78h+lpFile]; void *
0x180007704  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180007709  mov     eax, ebx
0x18000770b  jmp     loc_180007807
0x180007710  xor     r9d, r9d; fReserved
0x180007713  mov     r8, [rsp+78h+phkResult]; hkeyDest
0x180007718  xor     edx, edx; pszSrcSubKey
0x18000771a  mov     rcx, [rsp+78h+hKey]; hkeySrc
0x18000771f  call    cs:__imp_SHCopyKeyA
0x180007725  test    eax, eax
0x180007727  jz      short loc_180007796
0x180007729  lea     rdx, [rsp+78h+lpFile]
0x18000772e  cmp     qword ptr [rsp+78h+var_28+8], 0Fh
0x180007734  cmova   rdx, [rsp+78h+lpFile]
0x18000773a  mov     rcx, [rsp+78h]; this
0x18000773f  mov     [rsp+78h+var_50], rdx; char *
0x180007744  lea     rdx, aFailedToMigrat_0; "Failed to migrate DO registry from %hs"
0x18000774b  mov     qword ptr [rsp+78h+Reserved], rdx; unsigned int
0x180007750  mov     r9d, eax; char *
0x180007753  lea     r8, aCW1SSrcDeliver_56; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000775a  mov     edx, 30Fh; void *
0x18000775f  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180007764  mov     ebx, eax
0x180007766  mov     rcx, [rsp+78h+hKey]; hKey
0x18000776b  test    rcx, rcx
0x18000776e  jz      short loc_180007777
0x180007770  call    cs:__imp_RegCloseKey
0x180007776  nop
0x180007777  mov     rcx, [rsp+78h+phkResult]; hKey
0x18000777c  test    rcx, rcx
0x18000777f  jz      short loc_180007788
0x180007781  call    cs:__imp_RegCloseKey
0x180007787  nop
0x180007788  lea     rcx, [rsp+78h+lpFile]; void *
0x18000778d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180007792  mov     eax, ebx
0x180007794  jmp     short loc_180007807
0x180007796  mov     rcx, [rsp+78h+hKey]; hKey
0x18000779b  test    rcx, rcx
0x18000779e  jz      short loc_1800077DD
0x1800077a0  call    cs:__imp_RegCloseKey
0x1800077a6  jmp     short loc_1800077DD
0x1800077a8  lea     rax, [rsp+78h+lpFile]
0x1800077ad  cmp     qword ptr [rsp+78h+var_28+8], 0Fh
0x1800077b3  cmova   rax, [rsp+78h+lpFile]
0x1800077b9  mov     qword ptr [rsp+78h+Reserved], rax
0x1800077be  lea     r9, aDoRegistryMigr; "DO registry migration file not found: %"...
0x1800077c5  mov     r8d, 313h; unsigned int
0x1800077cb  lea     rdx, aMigrateregistr_1; "MigrateRegistry"
0x1800077d2  mov     ecx, 4; unsigned __int8
0x1800077d7  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800077dc  nop
0x1800077dd  mov     rcx, [rsp+78h+phkResult]; hKey
0x1800077e2  test    rcx, rcx
0x1800077e5  jz      short loc_1800077EE
0x1800077e7  call    cs:__imp_RegCloseKey
0x1800077ed  nop
0x1800077ee  lea     rcx, [rsp+78h+lpFile]; void *
0x1800077f3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800077f8  xor     eax, eax
0x1800077fa  jmp     short loc_180007807
0x1800077fc  mov     eax, 8007000Eh
0x180007801  jmp     short loc_180007807
0x180007803  mov     eax, [rsp+78h+var_40]
0x180007807  mov     rcx, [rsp+78h+var_10]
0x18000780c  xor     rcx, rsp; StackCookie
0x18000780f  call    __security_check_cookie
0x180007814  mov     rbx, [rsp+78h+arg_0]
0x18000781c  add     rsp, 70h
0x180007820  pop     rdi
0x180007821  retn
```
