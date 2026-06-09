# ServiceManager_IsAnyOperationPending(bool *)

- ea: `0x18000a6a4`
- end: `0x18000aa1b`
- name: `?ServiceManager_IsAnyOperationPending@@YAJPEA_N@Z`
- size: `887`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, service_task, installer_update`

## callers

- `0x18000af38`

## callees

- `0x180001d00`
- `0x180002722`
- `0x18000a348`
- `0x18000a6a4`
- `0x18000bef4`
- `0x18000bf98`
- `0x18000c028`
- `0x18000c088`
- `0x18000c440`
- `0x18000c4ec`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000a94e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000a9b7`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000a94e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000a9b7`
- `MosStorage!MosStorageGetDataDirectory` at `0x18000a92c`
- `MosStorage!MosStorageGetDataDirectory` at `0x18000a993`
- `MosStorage!MosStorageGetDataDirectory` at `0x18000a92c`
- `MosStorage!MosStorageGetDataDirectory` at `0x18000a993`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a712`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a73c`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a75a`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a7bd`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a839`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a8bb`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a712`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a73c`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a75a`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a7bd`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a839`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a8bb`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18000a807`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18000a807`

## string_xrefs

- `0x18000a751`: `ServiceManager_IsAnyOperationPending`
- `0x18000a8b2`: `ServiceManager_IsAnyOperationPending`
- `0x18000a93f`: `diskcache`
- `0x18000a9a8`: `mapscache`
- `0x18000a7f4`: `InstallUpdateStarted`
- `0x18000a830`: `RegUtils::DeleteMapsPersistedRegValue`

## pseudocode

```c
__int64 __fastcall ServiceManager_IsAnyOperationPending(bool *a1)
{
  unsigned int v2; // ebx
  bool v3; // di
  __int64 v4; // rcx
  int PersistedRegistryLocation; // eax
  const unsigned __int16 *v6; // rdx
  bool v7; // r8
  HRESULT MapsPersistedRegDword; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  int RegBoolean; // eax
  int v12; // r8d
  __int64 v13; // rcx
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  int v16; // r8d
  __int64 v17; // rcx
  int v18; // eax
  int v19; // r8d
  bool v20; // sf
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  int MapsPersistedRegString; // eax
  __int64 v25; // rcx
  __int64 v26; // r8
  bool v28[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v29; // [rsp+24h] [rbp-DCh] BYREF
  __int128 v30; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h]
  __int64 v32; // [rsp+40h] [rbp-C0h]
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
  v29 = 0;
  v3 = 0;
  v28[0] = 0;
  memset_0(SubKey, 0, 0x208u);
  PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(v4, SubKey);
  if ( PersistedRegistryLocation >= 0 )
  {
    RegBoolean = RegUtils::GetRegBoolean(SubKey, v6, v7, v28);
    if ( RegBoolean >= 0 )
    {
      v3 = v28[0];
LABEL_9:
      if ( !v3 )
      {
        MapsPersistedRegDword = RegUtils::GetMapsPersistedRegDword(v9, L"CurrentOperation", v10, &v29);
        if ( MapsPersistedRegDword < 0 )
        {
          v12 = 116;
          return (unsigned int)ZTraceReportPropagationNoThis(
                                 MapsPersistedRegDword,
                                 "ServiceManager_IsAnyOperationPending",
                                 v12);
        }
        v3 = v29 != 0;
        if ( !v29 )
        {
          v30 = 0;
          v31 = 0;
          v32 = 7;
          LOWORD(v30) = 0;
          MapsPersistedRegString = RegUtils::GetMapsPersistedRegString(v22, v21, v23, &v30);
          if ( MapsPersistedRegString < 0 )
          {
            v2 = ZTraceReportPropagationNoThis(MapsPersistedRegString, "ServiceManager_IsAnyOperationPending", 126);
            std::wstring::~wstring(&v30);
            return v2;
          }
          v3 = v31 != 0;
          v28[0] = v31 != 0;
          std::wstring::~wstring(&v30);
          if ( !v3 )
          {
            MapsPersistedRegDword = RegUtils::GetMapsPersistedRegDword(v25, L"UpgradeCheck", v26, &v29);
            if ( MapsPersistedRegDword < 0 )
            {
              v12 = 134;
              return (unsigned int)ZTraceReportPropagationNoThis(
                                     MapsPersistedRegDword,
                                     "ServiceManager_IsAnyOperationPending",
                                     v12);
            }
            if ( v29 != 5 )
            {
              MapsPersistedRegDword = MosStorageGetDataDirectory(SubKey, 0x104u);
              if ( MapsPersistedRegDword < 0 )
              {
                v12 = 141;
                return (unsigned int)ZTraceReportPropagationNoThis(
                                       MapsPersistedRegDword,
                                       "ServiceManager_IsAnyOperationPending",
                                       v12);
              }
              MapsPersistedRegDword = PathCchAppend(SubKey, 0x104u, L"diskcache");
              if ( MapsPersistedRegDword < 0 )
              {
                v12 = 142;
                return (unsigned int)ZTraceReportPropagationNoThis(
                                       MapsPersistedRegDword,
                                       "ServiceManager_IsAnyOperationPending",
                                       v12);
              }
              MapsPersistedRegDword = FolderExists(SubKey, v28);
              if ( MapsPersistedRegDword < 0 )
              {
                v12 = 143;
                return (unsigned int)ZTraceReportPropagationNoThis(
                                       MapsPersistedRegDword,
                                       "ServiceManager_IsAnyOperationPending",
                                       v12);
              }
              v3 = v28[0];
              if ( !v28[0] )
              {
                MapsPersistedRegDword = MosStorageGetDataDirectory(SubKey, 0x104u);
                if ( MapsPersistedRegDword < 0 )
                {
                  v12 = 148;
                  return (unsigned int)ZTraceReportPropagationNoThis(
                                         MapsPersistedRegDword,
                                         "ServiceManager_IsAnyOperationPending",
                                         v12);
                }
                MapsPersistedRegDword = PathCchAppend(SubKey, 0x104u, L"mapscache");
                if ( MapsPersistedRegDword < 0 )
                {
                  v12 = 149;
                  return (unsigned int)ZTraceReportPropagationNoThis(
                                         MapsPersistedRegDword,
                                         "ServiceManager_IsAnyOperationPending",
                                         v12);
                }
                MapsPersistedRegDword = FolderExists(SubKey, v28);
                if ( MapsPersistedRegDword < 0 )
                {
                  v12 = 150;
                  return (unsigned int)ZTraceReportPropagationNoThis(
                                         MapsPersistedRegDword,
                                         "ServiceManager_IsAnyOperationPending",
                                         v12);
                }
                v3 = v28[0];
              }
            }
          }
        }
        goto LABEL_48;
      }
      memset_0(SubKey, 0, 0x208u);
      v14 = RegUtils::GetPersistedRegistryLocation(v13, SubKey);
      if ( v14 >= 0 )
      {
        v14 = RegUtils::SetRegDword(SubKey, v15, 3u);
        if ( v14 >= 0 )
        {
LABEL_16:
          memset_0(SubKey, 0, 0x208u);
          v18 = RegUtils::GetPersistedRegistryLocation(v17, SubKey);
          if ( v18 >= 0 )
          {
            v18 = RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, SubKey, L"InstallUpdateStarted");
            if ( v18 == 2 )
              goto LABEL_48;
            v20 = v18 < 0;
            if ( v18 > 0 )
            {
              v18 = (unsigned __int16)v18 | 0x80070000;
              v20 = v18 < 0;
            }
            if ( !v20 )
              goto LABEL_48;
            v19 = 756;
          }
          else
          {
            v19 = 752;
          }
          MapsPersistedRegDword = ZTraceReportPropagationNoThis(v18, "RegUtils::DeleteMapsPersistedRegValue", v19);
          if ( MapsPersistedRegDword < 0 )
          {
            v12 = 109;
            return (unsigned int)ZTraceReportPropagationNoThis(
                                   MapsPersistedRegDword,
                                   "ServiceManager_IsAnyOperationPending",
                                   v12);
          }
LABEL_48:
          *a1 = v3;
          return v2;
        }
        v16 = 505;
      }
      else
      {
        v16 = 500;
      }
      MapsPersistedRegDword = ZTraceReportPropagationNoThis(v14, "RegUtils::SetMapsPersistedRegDword", v16);
      if ( MapsPersistedRegDword < 0 )
      {
        v12 = 106;
        return (unsigned int)ZTraceReportPropagationNoThis(
                               MapsPersistedRegDword,
                               "ServiceManager_IsAnyOperationPending",
                               v12);
      }
      goto LABEL_16;
    }
    MapsPersistedRegDword = ZTraceReportPropagationNoThis(RegBoolean, "RegUtils::GetMapsPersistedRegBoolean", 545);
    v3 = v28[0];
  }
  else
  {
    MapsPersistedRegDword = ZTraceReportPropagationNoThis(
                              PersistedRegistryLocation,
                              "RegUtils::GetMapsPersistedRegBoolean",
                              539);
  }
  if ( MapsPersistedRegDword >= 0 )
    goto LABEL_9;
  v12 = 100;
  return (unsigned int)ZTraceReportPropagationNoThis(MapsPersistedRegDword, "ServiceManager_IsAnyOperationPending", v12);
}

```

## disassembly

```asm
0x18000a6a4  mov     [rsp-8+arg_8], rbx
0x18000a6a9  mov     [rsp-8+arg_10], rsi
0x18000a6ae  push    rbp
0x18000a6af  push    rdi
0x18000a6b0  push    r14
0x18000a6b2  lea     rbp, [rsp-170h]
0x18000a6ba  sub     rsp, 270h
0x18000a6c1  mov     rax, cs:__security_cookie
0x18000a6c8  xor     rax, rsp
0x18000a6cb  mov     [rbp+180h+var_20], rax
0x18000a6d2  mov     rsi, rcx
0x18000a6d5  xor     ebx, ebx
0x18000a6d7  mov     [rsp+280h+var_25C], ebx
0x18000a6db  mov     dil, bl
0x18000a6de  mov     [rsp+280h+var_260], bl
0x18000a6e2  mov     r14d, 208h
0x18000a6e8  mov     r8d, r14d; Size
0x18000a6eb  xor     edx, edx; Val
0x18000a6ed  lea     rcx, [rsp+280h+SubKey]; void *
0x18000a6f2  call    memset_0
0x18000a6f7  lea     rdx, [rsp+280h+SubKey]
0x18000a6fc  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x18000a701  test    eax, eax
0x18000a703  jns     short loc_18000A71A
0x18000a705  lea     r8d, [r14+13h]
0x18000a709  lea     rdx, aRegutilsGetmap_1; "RegUtils::GetMapsPersistedRegBoolean"
0x18000a710  mov     ecx, eax
0x18000a712  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000a718  jmp     short loc_18000A747
0x18000a71a  lea     r9, [rsp+280h+var_260]; bool *
0x18000a71f  lea     rcx, [rsp+280h+SubKey]; lpSubKey
0x18000a724  call    ?GetRegBoolean@RegUtils@@SAJPEBG0_NPEA_N@Z; RegUtils::GetRegBoolean(ushort const *,ushort const *,bool,bool *)
0x18000a729  test    eax, eax
0x18000a72b  jns     short loc_18000A767
0x18000a72d  mov     r8d, 221h
0x18000a733  lea     rdx, aRegutilsGetmap_1; "RegUtils::GetMapsPersistedRegBoolean"
0x18000a73a  mov     ecx, eax
0x18000a73c  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000a742  mov     dil, [rsp+280h+var_260]
0x18000a747  test    eax, eax
0x18000a749  jns     short loc_18000A76C
0x18000a74b  mov     r8d, 64h ; 'd'
0x18000a751  lea     rdx, aServicemanager; "ServiceManager_IsAnyOperationPending"
0x18000a758  mov     ecx, eax
0x18000a75a  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000a760  mov     ebx, eax
0x18000a762  jmp     loc_18000A9F2
0x18000a767  mov     dil, [rsp+280h+var_260]
0x18000a76c  test    dil, dil
0x18000a76f  jz      loc_18000A852
0x18000a775  mov     r8, r14; Size
0x18000a778  xor     edx, edx; Val
0x18000a77a  lea     rcx, [rsp+280h+SubKey]; void *
0x18000a77f  call    memset_0
0x18000a784  lea     rdx, [rsp+280h+SubKey]
0x18000a789  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x18000a78e  test    eax, eax
0x18000a790  jns     short loc_18000A79A
0x18000a792  mov     r8d, 1F4h
0x18000a798  jmp     short loc_18000A7B4
0x18000a79a  mov     r8d, 3; unsigned int
0x18000a7a0  lea     rcx, [rsp+280h+SubKey]; lpSubKey
0x18000a7a5  call    ?SetRegDword@RegUtils@@SAJPEBG0K@Z; RegUtils::SetRegDword(ushort const *,ushort const *,ulong)
0x18000a7aa  test    eax, eax
0x18000a7ac  jns     short loc_18000A7CF
0x18000a7ae  mov     r8d, 1F9h
0x18000a7b4  lea     rdx, aRegutilsSetmap; "RegUtils::SetMapsPersistedRegDword"
0x18000a7bb  mov     ecx, eax
0x18000a7bd  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000a7c3  test    eax, eax
0x18000a7c5  jns     short loc_18000A7CF
0x18000a7c7  mov     r8d, 6Ah ; 'j'
0x18000a7cd  jmp     short loc_18000A751
0x18000a7cf  mov     r8, r14; Size
0x18000a7d2  xor     edx, edx; Val
0x18000a7d4  lea     rcx, [rsp+280h+SubKey]; void *
0x18000a7d9  call    memset_0
0x18000a7de  lea     rdx, [rsp+280h+SubKey]
0x18000a7e3  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x18000a7e8  test    eax, eax
0x18000a7ea  jns     short loc_18000A7F4
0x18000a7ec  mov     r8d, 2F0h
0x18000a7f2  jmp     short loc_18000A830
0x18000a7f4  lea     r8, Value; "InstallUpdateStarted"
0x18000a7fb  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x18000a800  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a807  call    cs:__imp_RegDeleteKeyValueW
0x18000a80d  cmp     eax, 2
0x18000a810  jz      loc_18000A9EF
0x18000a816  test    eax, eax
0x18000a818  jle     short loc_18000A824
0x18000a81a  movzx   eax, ax
0x18000a81d  or      eax, 80070000h
0x18000a822  test    eax, eax
0x18000a824  jns     loc_18000A9EF
0x18000a82a  mov     r8d, 2F4h
0x18000a830  lea     rdx, aRegutilsDelete; "RegUtils::DeleteMapsPersistedRegValue"
0x18000a837  mov     ecx, eax
0x18000a839  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000a83f  test    eax, eax
0x18000a841  jns     loc_18000A9EF
0x18000a847  mov     r8d, 6Dh ; 'm'
0x18000a84d  jmp     loc_18000A751
0x18000a852  lea     r9, [rsp+280h+var_25C]
0x18000a857  lea     rdx, ValueName; "CurrentOperation"
0x18000a85e  call    ?GetMapsPersistedRegDword@RegUtils@@SAJW4MapsRegKeys@@PEBGKPEAK@Z; RegUtils::GetMapsPersistedRegDword(MapsRegKeys,ushort const *,ulong,ulong *)
0x18000a863  test    eax, eax
0x18000a865  jns     short loc_18000A872
0x18000a867  mov     r8d, 74h ; 't'
0x18000a86d  jmp     loc_18000A751
0x18000a872  cmp     [rsp+280h+var_25C], ebx
0x18000a876  setnz   dil
0x18000a87a  test    dil, dil
0x18000a87d  jnz     loc_18000A9EF
0x18000a883  xorps   xmm0, xmm0
0x18000a886  movups  [rsp+280h+var_258], xmm0
0x18000a88b  mov     [rsp+280h+var_248], rbx
0x18000a890  mov     [rsp+280h+var_240], 7
0x18000a899  mov     word ptr [rsp+280h+var_258], bx
0x18000a89e  lea     r9, [rsp+280h+var_258]
0x18000a8a3  call    ?GetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBG1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetMapsPersistedRegString(MapsRegKeys,ushort const *,ushort const *,std::wstring *)
0x18000a8a8  test    eax, eax
0x18000a8aa  jns     short loc_18000A8D2
0x18000a8ac  mov     r8d, 7Eh ; '~'
0x18000a8b2  lea     rdx, aServicemanager; "ServiceManager_IsAnyOperationPending"
0x18000a8b9  mov     ecx, eax
0x18000a8bb  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000a8c1  mov     ebx, eax
0x18000a8c3  lea     rcx, [rsp+280h+var_258]
0x18000a8c8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a8cd  jmp     loc_18000A9F2
0x18000a8d2  cmp     [rsp+280h+var_248], rbx
0x18000a8d7  setnz   dil
0x18000a8db  mov     [rsp+280h+var_260], dil
0x18000a8e0  lea     rcx, [rsp+280h+var_258]
0x18000a8e5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a8ea  test    dil, dil
0x18000a8ed  jnz     loc_18000A9EF
0x18000a8f3  lea     r9, [rsp+280h+var_25C]
0x18000a8f8  lea     rdx, aUpgradecheck; "UpgradeCheck"
0x18000a8ff  call    ?GetMapsPersistedRegDword@RegUtils@@SAJW4MapsRegKeys@@PEBGKPEAK@Z; RegUtils::GetMapsPersistedRegDword(MapsRegKeys,ushort const *,ulong,ulong *)
0x18000a904  test    eax, eax
0x18000a906  jns     short loc_18000A913
0x18000a908  mov     r8d, 86h
0x18000a90e  jmp     loc_18000A751
0x18000a913  cmp     [rsp+280h+var_25C], 5
0x18000a918  jz      loc_18000A9EF
0x18000a91e  mov     r14d, 104h
0x18000a924  mov     edx, r14d
0x18000a927  lea     rcx, [rsp+280h+SubKey]
0x18000a92c  call    cs:__imp_?MosStorageGetDataDirectory@@YAJPEAGK@Z; MosStorageGetDataDirectory(ushort *,ulong)
0x18000a932  test    eax, eax
0x18000a934  jns     short loc_18000A93F
0x18000a936  lea     r8d, [r14-77h]
0x18000a93a  jmp     loc_18000A751
0x18000a93f  lea     r8, pszMore; "diskcache"
0x18000a946  mov     rdx, r14; cchPath
0x18000a949  lea     rcx, [rsp+280h+SubKey]; pszPath
0x18000a94e  call    cs:__imp_PathCchAppend
0x18000a954  test    eax, eax
0x18000a956  jns     short loc_18000A963
0x18000a958  mov     r8d, 8Eh
0x18000a95e  jmp     loc_18000A751
0x18000a963  lea     rdx, [rsp+280h+var_260]; bool *
0x18000a968  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x18000a96d  call    ?FolderExists@@YAJPEBGPEA_N@Z; FolderExists(ushort const *,bool *)
0x18000a972  test    eax, eax
0x18000a974  jns     short loc_18000A981
0x18000a976  mov     r8d, 8Fh
0x18000a97c  jmp     loc_18000A751
0x18000a981  mov     dil, [rsp+280h+var_260]
0x18000a986  test    dil, dil
0x18000a989  jnz     short loc_18000A9EF
0x18000a98b  mov     edx, r14d
0x18000a98e  lea     rcx, [rsp+280h+SubKey]
0x18000a993  call    cs:__imp_?MosStorageGetDataDirectory@@YAJPEAGK@Z; MosStorageGetDataDirectory(ushort *,ulong)
0x18000a999  test    eax, eax
0x18000a99b  jns     short loc_18000A9A8
0x18000a99d  mov     r8d, 94h
0x18000a9a3  jmp     loc_18000A751
0x18000a9a8  lea     r8, aMapscache; "mapscache"
0x18000a9af  mov     rdx, r14; cchPath
0x18000a9b2  lea     rcx, [rsp+280h+SubKey]; pszPath
0x18000a9b7  call    cs:__imp_PathCchAppend
0x18000a9bd  test    eax, eax
0x18000a9bf  jns     short loc_18000A9CC
0x18000a9c1  mov     r8d, 95h
0x18000a9c7  jmp     loc_18000A751
0x18000a9cc  lea     rdx, [rsp+280h+var_260]; bool *
0x18000a9d1  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x18000a9d6  call    ?FolderExists@@YAJPEBGPEA_N@Z; FolderExists(ushort const *,bool *)
0x18000a9db  test    eax, eax
0x18000a9dd  jns     short loc_18000A9EA
0x18000a9df  mov     r8d, 96h
0x18000a9e5  jmp     loc_18000A751
0x18000a9ea  mov     dil, [rsp+280h+var_260]
0x18000a9ef  mov     [rsi], dil
0x18000a9f2  mov     eax, ebx
0x18000a9f4  mov     rcx, [rbp+180h+var_20]
0x18000a9fb  xor     rcx, rsp; StackCookie
0x18000a9fe  call    __security_check_cookie
0x18000aa03  lea     r11, [rsp+280h+var_10]
0x18000aa0b  mov     rbx, [r11+28h]
0x18000aa0f  mov     rsi, [r11+30h]
0x18000aa13  mov     rsp, r11
0x18000aa16  pop     r14
0x18000aa18  pop     rdi
0x18000aa19  pop     rbp
0x18000aa1a  retn
```
