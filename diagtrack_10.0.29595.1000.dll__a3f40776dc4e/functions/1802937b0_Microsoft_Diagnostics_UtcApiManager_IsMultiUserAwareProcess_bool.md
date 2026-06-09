# Microsoft::Diagnostics::UtcApiManager::IsMultiUserAwareProcess(bool &)

- ea: `0x1802937b0`
- end: `0x180293a7d`
- name: `?IsMultiUserAwareProcess@UtcApiManager@Diagnostics@Microsoft@@AEAAJAEA_N@Z`
- size: `717`
- prototype: `int(Microsoft::Diagnostics::UtcApiManager *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801e5828`

## callees

- `0x1800202a4`
- `0x180024558`
- `0x18002b9c0`
- `0x18002df00`
- `0x180049bec`
- `0x180064e6c`
- `0x180064e8c`
- `0x18013a510`
- `0x1801ce3c4`
- `0x18020aac0`
- `0x18020d2d0`
- `0x18028608c`
- `0x180291dc8`
- `0x1802937b0`
- `0x1802f2490`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18029382c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180293886`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18029382c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180293886`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802938e5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802938e5`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x180293940`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x180293940`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1802939b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1802939b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180293a06`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180293a48`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180293a06`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180293a48`

## string_xrefs

- `0x1802937ea`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1802938fb`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180293953`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1802939e5`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1802939cc`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x18029387f`: `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2.dll`
- `0x180293825`: `api-ms-win-appmodel-runtime-internal-l1-1-2.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Diagnostics::UtcApiManager::IsMultiUserAwareProcess(
        Microsoft::Diagnostics::UtcApiManager *this,
        bool *a2)
{
  __int64 v3; // rdx
  unsigned int RpcCallerPid; // ebx
  HMODULE Library; // rax
  HMODULE v6; // rax
  Microsoft::Diagnostics::ApiServer *v7; // rcx
  HANDLE v8; // rbx
  const char *v9; // r9
  WCHAR *v10; // r8
  LONG v11; // eax
  PWSTR *v12; // rax
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rcx
  const wchar_t *v16; // rdx
  int IsEffectiveSupportedUsersMultiple; // eax
  __int64 v18; // rcx
  __int64 v20; // [rsp+20h] [rbp-29h] BYREF
  UINT32 packageFullNameLength; // [rsp+28h] [rbp-21h] BYREF
  DWORD dwProcessId[4]; // [rsp+30h] [rbp-19h] BYREF
  __int64 *v23; // [rsp+40h] [rbp-9h] BYREF
  __int64 v24; // [rsp+48h] [rbp-1h] BYREF
  char v25; // [rsp+50h] [rbp+7h]
  PWSTR packageFullName[2]; // [rsp+58h] [rbp+Fh] BYREF
  UINT32 v27; // [rsp+68h] [rbp+1Fh]
  unsigned __int64 v28; // [rsp+70h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *a2 = 0;
  if ( (unsigned __int8)IsGetPackageFullNamePresent(this) )
  {
    std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(dwProcessId, qword_180462BF8);
    if ( !byte_180462BF0 )
    {
      Library = LoadLibraryExW(L"api-ms-win-appmodel-runtime-internal-l1-1-2.dll", 0, 0x800u);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
        &qword_180462D88,
        Library);
      byte_180462BF0 = 1;
    }
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(dwProcessId);
    if ( !qword_180462D88 )
    {
      v3 = 6400;
      goto LABEL_3;
    }
    std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(dwProcessId, qword_180462C48);
    if ( !byte_180462BF1 )
    {
      v6 = LoadLibraryExW(L"ext-ms-onecore-appmodel-staterepository-cache-l1-1-2.dll", 0, 0x800u);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
        &qword_180462D90,
        v6);
      byte_180462BF1 = 1;
    }
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(dwProcessId);
    if ( !qword_180462D90 )
    {
      v3 = 6401;
      goto LABEL_3;
    }
    dwProcessId[0] = 0;
    RpcCallerPid = Microsoft::Diagnostics::ApiServer::GetRpcCallerPid(v7, dwProcessId);
    if ( (RpcCallerPid & 0x80000000) != 0 )
    {
      v3 = 6404;
      goto LABEL_4;
    }
    v8 = OpenProcess(0x1000u, 0, dwProcessId[0]);
    *(_QWORD *)dwProcessId = v8;
    if ( !v8 )
    {
      RpcCallerPid = wil::details::in1diag3::Return_GetLastError(
                       retaddr,
                       (void *)0x1907,
                       (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
                       v9);
LABEL_36:
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(dwProcessId);
      return RpcCallerPid;
    }
    std::wstring::wstring(packageFullName, 128, 0);
    packageFullNameLength = v27;
    v10 = (WCHAR *)packageFullName;
    if ( v28 > 7 )
      v10 = packageFullName[0];
    v11 = GetPackageFullName(v8, &packageFullNameLength, v10);
    RpcCallerPid = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x190C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)v11,
        v20);
LABEL_21:
      std::wstring::_Tidy_deallocate(packageFullName);
      goto LABEL_36;
    }
    v12 = packageFullName;
    if ( v28 > 7 )
      v12 = (PWSTR *)packageFullName[0];
    if ( *(_WORD *)v12 )
    {
      std::wstring::resize(packageFullName, packageFullNameLength);
      v20 = 0;
      v23 = &v20;
      v24 = 0;
      v25 = 1;
      RpcCallerPid = SRCacheManager_Open(0, &v24);
      wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v23);
      if ( (RpcCallerPid & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA5,
          (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
          (const char *)RpcCallerPid,
          v20);
        v13 = RpcCallerPid;
        v14 = 6419;
        goto LABEL_27;
      }
      v16 = (const wchar_t *)packageFullName;
      if ( v28 > 7 )
        v16 = packageFullName[0];
      IsEffectiveSupportedUsersMultiple = StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(
                                            (struct StateRepository::Cache::Manager_NoThrow *)&v20,
                                            v16,
                                            a2);
      RpcCallerPid = IsEffectiveSupportedUsersMultiple;
      if ( IsEffectiveSupportedUsersMultiple < 0 )
      {
        v13 = (unsigned int)IsEffectiveSupportedUsersMultiple;
        v14 = 6424;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)v13,
          v20);
        v15 = v20;
        v20 = 0;
        if ( v15 )
          SRCacheManager_Close(v15);
        goto LABEL_21;
      }
      v18 = v20;
      v20 = 0;
      if ( v18 )
        SRCacheManager_Close(v18);
    }
    std::wstring::_Tidy_deallocate(packageFullName);
    RpcCallerPid = 0;
    goto LABEL_36;
  }
  v3 = 6399;
LABEL_3:
  RpcCallerPid = -2147024846;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
    (const char *)RpcCallerPid,
    v20);
  return RpcCallerPid;
}

```

## disassembly

```asm
0x1802937b0  push    rbp
0x1802937b2  push    rbx
0x1802937b3  push    rsi
0x1802937b4  push    rdi
0x1802937b5  lea     rbp, [rsp-3Fh]
0x1802937ba  sub     rsp, 88h
0x1802937c1  mov     rax, cs:__security_cookie
0x1802937c8  xor     rax, rsp
0x1802937cb  mov     [rbp+57h+var_28], rax
0x1802937cf  mov     rdi, rdx
0x1802937d2  xor     esi, esi
0x1802937d4  mov     [rdx], sil
0x1802937d7  call    IsGetPackageFullNamePresent
0x1802937dc  test    al, al
0x1802937de  jnz     short loc_180293802
0x1802937e0  mov     edx, 18FFh; void *
0x1802937e5  mov     ebx, 80070032h
0x1802937ea  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1802937f1  mov     r9d, ebx; char *
0x1802937f4  mov     rcx, [rbp+5Fh]; this
0x1802937f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802937fd  jmp     loc_180293A63
0x180293802  lea     rdx, qword_180462BF8
0x180293809  lea     rcx, [rbp+57h+dwProcessId]
0x18029380d  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x180293812  mov     ebx, 800h
0x180293817  cmp     cs:byte_180462BF0, sil
0x18029381e  jnz     short loc_180293848
0x180293820  mov     r8d, ebx; dwFlags
0x180293823  xor     edx, edx; hFile
0x180293825  lea     rcx, aApiMsWinAppmod_0; "api-ms-win-appmodel-runtime-internal-l1"...
0x18029382c  call    cs:__imp_LoadLibraryExW
0x180293832  mov     rdx, rax
0x180293835  lea     rcx, qword_180462D88
0x18029383c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180293841  mov     cs:byte_180462BF0, 1
0x180293848  lea     rcx, [rbp+57h+dwProcessId]
0x18029384c  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180293851  cmp     cs:qword_180462D88, rsi
0x180293858  jnz     short loc_180293861
0x18029385a  mov     edx, 1900h
0x18029385f  jmp     short loc_1802937E5
0x180293861  lea     rdx, qword_180462C48
0x180293868  lea     rcx, [rbp+57h+dwProcessId]
0x18029386c  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x180293871  cmp     cs:byte_180462BF1, sil
0x180293878  jnz     short loc_1802938A2
0x18029387a  mov     r8d, ebx; dwFlags
0x18029387d  xor     edx, edx; hFile
0x18029387f  lea     rcx, aExtMsOnecoreAp_1; "ext-ms-onecore-appmodel-staterepository"...
0x180293886  call    cs:__imp_LoadLibraryExW
0x18029388c  mov     rdx, rax
0x18029388f  lea     rcx, qword_180462D90
0x180293896  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18029389b  mov     cs:byte_180462BF1, 1
0x1802938a2  lea     rcx, [rbp+57h+dwProcessId]
0x1802938a6  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1802938ab  cmp     cs:qword_180462D90, rsi
0x1802938b2  jnz     short loc_1802938BE
0x1802938b4  mov     edx, 1901h
0x1802938b9  jmp     loc_1802937E5
0x1802938be  mov     [rbp+57h+dwProcessId], esi
0x1802938c1  lea     rdx, [rbp+57h+dwProcessId]; unsigned int *
0x1802938c5  call    ?GetRpcCallerPid@ApiServer@Diagnostics@Microsoft@@IEAAJAEAK@Z; Microsoft::Diagnostics::ApiServer::GetRpcCallerPid(ulong &)
0x1802938ca  mov     ebx, eax
0x1802938cc  test    eax, eax
0x1802938ce  jns     short loc_1802938DA
0x1802938d0  mov     edx, 1904h
0x1802938d5  jmp     loc_1802937EA
0x1802938da  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x1802938de  xor     edx, edx; bInheritHandle
0x1802938e0  mov     ecx, 1000h; dwDesiredAccess
0x1802938e5  call    cs:__imp_OpenProcess
0x1802938eb  mov     rbx, rax
0x1802938ee  mov     qword ptr [rbp+57h+dwProcessId], rax
0x1802938f2  test    rax, rax
0x1802938f5  jnz     short loc_180293913
0x1802938f7  mov     rcx, [rbp+5Fh]; this
0x1802938fb  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180293902  mov     edx, 1907h; void *
0x180293907  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18029390c  mov     ebx, eax
0x18029390e  jmp     loc_180293A5A
0x180293913  xor     r8d, r8d
0x180293916  mov     edx, 80h
0x18029391b  lea     rcx, [rbp+57h+packageFullName]
0x18029391f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x180293924  nop
0x180293925  mov     eax, [rbp+57h+var_38]
0x180293928  mov     [rbp+57h+packageFullNameLength], eax
0x18029392b  lea     r8, [rbp+57h+packageFullName]
0x18029392f  cmp     [rbp+57h+var_30], 7
0x180293934  cmova   r8, [rbp+57h+packageFullName]; packageFullName
0x180293939  lea     rdx, [rbp+57h+packageFullNameLength]; packageFullNameLength
0x18029393d  mov     rcx, rbx; hProcess
0x180293940  call    cs:__imp_GetPackageFullName
0x180293946  mov     ebx, eax
0x180293948  test    eax, eax
0x18029394a  jns     short loc_180293973
0x18029394c  mov     rcx, [rbp+5Fh]; this
0x180293950  mov     r9d, eax; char *
0x180293953  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x18029395a  mov     edx, 190Ch; void *
0x18029395f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180293964  nop
0x180293965  lea     rcx, [rbp+57h+packageFullName]
0x180293969  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029396e  jmp     loc_180293A5A
0x180293973  lea     rax, [rbp+57h+packageFullName]
0x180293977  cmp     [rbp+57h+var_30], 7
0x18029397c  cmova   rax, [rbp+57h+packageFullName]
0x180293981  cmp     [rax], si
0x180293984  jz      loc_180293A4F
0x18029398a  mov     edx, [rbp+57h+packageFullNameLength]
0x18029398d  lea     rcx, [rbp+57h+packageFullName]
0x180293991  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180293996  mov     [rbp+57h+var_80], rsi
0x18029399a  lea     rax, [rbp+57h+var_80]
0x18029399e  mov     [rbp+57h+var_60], rax
0x1802939a2  mov     [rbp+57h+var_58], rsi
0x1802939a6  mov     [rbp+57h+var_50], 1
0x1802939aa  lea     rdx, [rbp+57h+var_58]
0x1802939ae  xor     ecx, ecx
0x1802939b0  call    cs:__imp_SRCacheManager_Open
0x1802939b6  mov     ebx, eax
0x1802939b8  lea     rcx, [rbp+57h+var_60]
0x1802939bc  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x1802939c1  test    ebx, ebx
0x1802939c3  jns     short loc_180293A11
0x1802939c5  mov     rcx, [rbp+5Fh]; this
0x1802939c9  mov     r9d, ebx; char *
0x1802939cc  lea     r8, aOnecorePrivate; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x1802939d3  mov     edx, 0A5h; void *
0x1802939d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802939dd  mov     r9d, ebx; char *
0x1802939e0  mov     edx, 1913h; void *
0x1802939e5  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1802939ec  mov     rcx, [rbp+5Fh]; this
0x1802939f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802939f5  mov     rcx, [rbp+57h+var_80]
0x1802939f9  mov     [rbp+57h+var_80], rsi
0x1802939fd  test    rcx, rcx
0x180293a00  jz      loc_180293965
0x180293a06  call    cs:__imp_SRCacheManager_Close
0x180293a0c  jmp     loc_180293965
0x180293a11  lea     rdx, [rbp+57h+packageFullName]
0x180293a15  cmp     [rbp+57h+var_30], 7
0x180293a1a  cmova   rdx, [rbp+57h+packageFullName]; wchar_t *
0x180293a1f  mov     r8, rdi; bool *
0x180293a22  lea     rcx, [rbp+57h+var_80]; struct StateRepository::Cache::Manager_NoThrow *
0x180293a26  call    ?GetIsEffectiveSupportedUsersMultiple@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEB_WAEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(StateRepository::Cache::Manager_NoThrow &,wchar_t const *,bool &)
0x180293a2b  mov     ebx, eax
0x180293a2d  test    eax, eax
0x180293a2f  jns     short loc_180293A3B
0x180293a31  mov     r9d, eax
0x180293a34  mov     edx, 1918h
0x180293a39  jmp     short loc_1802939E5
0x180293a3b  mov     rcx, [rbp+57h+var_80]
0x180293a3f  mov     [rbp+57h+var_80], rsi
0x180293a43  test    rcx, rcx
0x180293a46  jz      short loc_180293A4F
0x180293a48  call    cs:__imp_SRCacheManager_Close
0x180293a4e  nop
0x180293a4f  lea     rcx, [rbp+57h+packageFullName]
0x180293a53  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180293a58  mov     ebx, esi
0x180293a5a  lea     rcx, [rbp+57h+dwProcessId]
0x180293a5e  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180293a63  mov     eax, ebx
0x180293a65  mov     rcx, [rbp+57h+var_28]
0x180293a69  xor     rcx, rsp; StackCookie
0x180293a6c  call    __security_check_cookie
0x180293a71  add     rsp, 88h
0x180293a78  pop     rdi
0x180293a79  pop     rsi
0x180293a7a  pop     rbx
0x180293a7b  pop     rbp
0x180293a7c  retn
```
