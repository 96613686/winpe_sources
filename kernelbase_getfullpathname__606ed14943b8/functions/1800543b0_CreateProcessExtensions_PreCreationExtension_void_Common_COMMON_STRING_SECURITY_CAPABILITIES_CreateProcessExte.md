# CreateProcessExtensions::PreCreationExtension(void *,Common::COMMON_STRING *,_SECURITY_CAPABILITIES *,CreateProcessExtensions::ErrorContext *,_APPX_PROCESS_CONTEXT * *)

- ea: `0x1800543b0`
- end: `0x180056daf`
- name: `?PreCreationExtension@CreateProcessExtensions@@SAJPEAXPEAUCOMMON_STRING@Common@@PEAU_SECURITY_CAPABILITIES@@PEAVErrorContext@1@PEAPEAU_APPX_PROCESS_CONTEXT@@@Z`
- size: `10751`
- prototype: `__int64 __usercall@<rax>(HANDLE TokenHandle@<rcx>, struct Common::COMMON_STRING *@<rdx>, struct _SECURITY_CAPABILITIES *@<r8>, struct CreateProcessExtensions::ErrorContext *@<r9>, struct _APPX_PROCESS_CONTEXT **)`
- caller_count: `1`
- callee_count: `45`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800110d0`

## callees

- `0x1800090b0`
- `0x18000a9c4`
- `0x18000b5e4`
- `0x18000bf5c`
- `0x18000cda0`
- `0x18000ce08`
- `0x18000d0fc`
- `0x1800129d0`
- `0x180014b30`
- `0x180015764`
- `0x1800183d4`
- `0x18002d7e0`
- `0x1800391f0`
- `0x18004b9d0`
- `0x180053c30`
- `0x1800540e0`
- `0x180054164`
- `0x1800543b0`
- `0x180056dc0`
- `0x180056de8`
- `0x180056eb8`
- `0x180056ef0`
- `0x180056f24`
- `0x180056f4c`
- `0x180056f80`
- `0x18005757c`
- `0x180057738`
- `0x180057758`
- `0x18005aa70`
- `0x18005b2c4`
- `0x18005ca00`
- `0x18005e040`
- `0x18005e320`
- `0x18006bdd0`
- `0x18006befc`
- `0x1800a2d84`
- `0x1800b8e10`
- `0x1800bdc18`
- `0x1800ec430`
- `0x1800f4550`
- `0x18010dfdc`
- `0x180110f7c`
- `0x180115bf4`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180054b13`
- `ntdll!RtlInitUnicodeString` at `0x180054b13`
- `ntdll!RtlEqualSid` at `0x180055d5b`
- `ntdll!RtlEqualSid` at `0x180055d5b`
- `ntdll!RtlSetLastWin32Error` at `0x180054a33`
- `ntdll!RtlSetLastWin32Error` at `0x180054a33`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180054ade`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180054ade`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180054be7`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180054be7`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180054b3a`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180054bc8`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180054b3a`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180054bc8`
- `ntdll!NtQueryInformationToken` at `0x180054601`
- `ntdll!NtQueryInformationToken` at `0x180055852`
- `ntdll!NtQueryInformationToken` at `0x180054601`
- `ntdll!NtQueryInformationToken` at `0x180055852`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180055572`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180055572`
- `ntdll!RtlFreeSid` at `0x180054780`
- `ntdll!RtlFreeSid` at `0x180054cbf`
- `ntdll!RtlFreeSid` at `0x180054e15`
- `ntdll!RtlFreeSid` at `0x1800552ba`
- `ntdll!RtlFreeSid` at `0x180055453`
- `ntdll!RtlFreeSid` at `0x180055622`
- `ntdll!RtlFreeSid` at `0x1800556f0`
- `ntdll!RtlFreeSid` at `0x1800557e3`
- `ntdll!RtlFreeSid` at `0x180055981`
- `ntdll!RtlFreeSid` at `0x180055a71`
- `ntdll!RtlFreeSid` at `0x180055b1d`
- `ntdll!RtlFreeSid` at `0x180055bf9`
- `ntdll!RtlFreeSid` at `0x180055cf0`
- `ntdll!RtlFreeSid` at `0x180055db7`
- `ntdll!RtlFreeSid` at `0x180055e82`
- `ntdll!RtlFreeSid` at `0x180055f41`
- `ntdll!RtlFreeSid` at `0x18005609a`
- `ntdll!RtlFreeSid` at `0x180056291`
- `ntdll!RtlFreeSid` at `0x1800563d8`
- `ntdll!RtlFreeSid` at `0x1800564c0`
- `ntdll!RtlFreeSid` at `0x1800565aa`
- `ntdll!RtlFreeSid` at `0x180056637`
- `ntdll!RtlFreeSid` at `0x18005682c`
- `ntdll!RtlFreeSid` at `0x1800568d6`
- `ntdll!RtlFreeSid` at `0x180056980`
- `ntdll!RtlFreeSid` at `0x180056a2a`
- `ntdll!RtlFreeSid` at `0x180056acf`
- `ntdll!RtlFreeSid` at `0x180056b6f`
- `ntdll!RtlFreeSid` at `0x180056c0f`
- `ntdll!RtlFreeSid` at `0x180056cb4`
- `ntdll!RtlFreeSid` at `0x180056d2c`
- `ntdll!RtlFreeSid` at `0x180054780`
- `ntdll!RtlFreeSid` at `0x180054cbf`
- `ntdll!RtlFreeSid` at `0x180054e15`
- `ntdll!RtlFreeSid` at `0x1800552ba`
- `ntdll!RtlFreeSid` at `0x180055453`
- `ntdll!RtlFreeSid` at `0x180055622`
- `ntdll!RtlFreeSid` at `0x1800556f0`
- `ntdll!RtlFreeSid` at `0x1800557e3`
- `ntdll!RtlFreeSid` at `0x180055981`
- `ntdll!RtlFreeSid` at `0x180055a71`
- `ntdll!RtlFreeSid` at `0x180055b1d`
- `ntdll!RtlFreeSid` at `0x180055bf9`
- `ntdll!RtlFreeSid` at `0x180055cf0`
- `ntdll!RtlFreeSid` at `0x180055db7`
- `ntdll!RtlFreeSid` at `0x180055e82`
- `ntdll!RtlFreeSid` at `0x180055f41`
- `ntdll!RtlFreeSid` at `0x18005609a`
- `ntdll!RtlFreeSid` at `0x180056291`
- `ntdll!RtlFreeSid` at `0x1800563d8`
- `ntdll!RtlFreeSid` at `0x1800564c0`
- `ntdll!RtlFreeSid` at `0x1800565aa`
- `ntdll!RtlFreeSid` at `0x180056637`
- `ntdll!RtlFreeSid` at `0x18005682c`
- `ntdll!RtlFreeSid` at `0x1800568d6`
- `ntdll!RtlFreeSid` at `0x180056980`
- `ntdll!RtlFreeSid` at `0x180056a2a`
- `ntdll!RtlFreeSid` at `0x180056acf`
- `ntdll!RtlFreeSid` at `0x180056b6f`
- `ntdll!RtlFreeSid` at `0x180056c0f`
- `ntdll!RtlFreeSid` at `0x180056cb4`
- `ntdll!RtlFreeSid` at `0x180056d2c`
- `ntdll!RtlLengthSid` at `0x180054642`
- `ntdll!RtlLengthSid` at `0x180054a42`
- `ntdll!RtlLengthSid` at `0x1800558ca`
- `ntdll!RtlLengthSid` at `0x180054642`
- `ntdll!RtlLengthSid` at `0x180054a42`
- `ntdll!RtlLengthSid` at `0x1800558ca`
- `ntdll!RtlGetAppContainerSidType` at `0x180055874`
- `ntdll!RtlGetAppContainerSidType` at `0x180055874`
- `ntdll!RtlCopySid` at `0x18005462b`
- `ntdll!RtlCopySid` at `0x180054a9c`
- `ntdll!RtlCopySid` at `0x180055920`
- `ntdll!RtlCopySid` at `0x18005462b`
- `ntdll!RtlCopySid` at `0x180054a9c`
- `ntdll!RtlCopySid` at `0x180055920`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x18005589f`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x18005589f`
- `ntdll!RtlFreeHeap` at `0x180055479`
- `ntdll!RtlFreeHeap` at `0x180055496`
- `ntdll!RtlFreeHeap` at `0x180055479`
- `ntdll!RtlFreeHeap` at `0x180055496`
- `ntdll!NtOpenProcessToken` at `0x1800559ec`
- `ntdll!NtOpenProcessToken` at `0x1800559ec`
- `ntdll!RtlAllocateHeap` at `0x180054538`
- `ntdll!RtlAllocateHeap` at `0x18005458c`
- `ntdll!RtlAllocateHeap` at `0x180054a75`
- `ntdll!RtlAllocateHeap` at `0x180054538`
- `ntdll!RtlAllocateHeap` at `0x18005458c`
- `ntdll!RtlAllocateHeap` at `0x180054a75`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x180055028`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x180055028`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800546b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800546b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005493b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800551f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005679e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005493b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800551f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005679e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800546e7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18005540a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800546e7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18005540a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005533d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005535c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005537b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005539a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800553b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800553d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800553f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005533d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005535c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005537b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18005539a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800553b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800553d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800553f1`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRGetPackageStatusForUserSid` at `0x18005465c`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRGetPackageStatusForUserSid` at `0x18005465c`

## string_xrefs

- `0x18005471d`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180054c0d`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180054c4c`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180054d38`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180054da9`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180054e9f`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180055314`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x1800555c3`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180055695`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180055767`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180055a15`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180055b8a`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180055c76`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180055e24`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180055eef`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180055fae`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18005601f`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180056107`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180056219`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x1800562ac`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x1800562d1`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18005633e`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180056445`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18005652f`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x1800565dd`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180056d7a`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180054d93`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180054e84`: `onecore\base\appmodel\common\registrykey.cpp`
- `0x180054d64`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800551ce`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800567b6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180054af7`: `%windir%\system32`
- `0x180054702`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-manager.hpp`

## pseudocode

```c
__int64 __fastcall CreateProcessExtensions::PreCreationExtension(
        HANDLE TokenHandle,
        struct Common::COMMON_STRING *a2,
        struct _SECURITY_CAPABILITIES *a3,
        struct CreateProcessExtensions::ErrorContext *a4,
        struct _APPX_PROCESS_CONTEXT **a5)
{
  int v5; // r12d
  HANDLE v7; // rsi
  wil::TraceLoggingProvider *v8; // rax
  __int64 v9; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v10; // rcx
  int EffectivePackageMoniker; // eax
  unsigned __int64 v12; // rdx
  unsigned int HResultFromLastError; // ebx
  PVOID ProcessHeap; // rcx
  struct _APPX_PROCESS_CONTEXT *Heap; // rax
  struct _APPX_PROCESS_CONTEXT *v16; // r13
  PVOID v17; // rcx
  _QWORD *v18; // rax
  _DWORD *v19; // rbx
  ARI::Internal *v20; // r14
  __int64 v21; // rcx
  int v22; // eax
  PSID v23; // rdi
  void *v24; // r15
  unsigned int v25; // edi
  __int64 v26; // r8
  unsigned __int64 v27; // rdx
  unsigned __int8 v28; // cl
  __int64 v29; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v30; // rcx
  bool v31; // di
  signed int PackagePath_Internal; // esi
  __int64 v33; // rsi
  int v34; // eax
  bool v35; // r15
  int v36; // eax
  __int64 v37; // rcx
  int v38; // eax
  WCHAR *v39; // rsi
  int v40; // eax
  HKEY v41; // rcx
  PSID v42; // r15
  ULONG v43; // eax
  PVOID v44; // rcx
  ULONG v45; // esi
  PVOID v46; // rdi
  NTSTATUS v47; // eax
  __int64 v48; // rcx
  bool v49; // zf
  unsigned int Status; // r15d
  WCHAR *v51; // rsi
  NTSTATUS v52; // eax
  SIZE_T v53; // rax
  NTSTATUS v54; // eax
  const unsigned __int16 *v55; // rdx
  int v56; // r9d
  HKEY v57; // rcx
  __int64 v58; // rdx
  unsigned __int64 v59; // rdx
  unsigned __int8 v60; // cl
  __int64 v61; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v62; // rcx
  __int64 v64; // rdx
  void *v65; // rcx
  unsigned __int64 v66; // rdx
  unsigned __int8 v67; // cl
  __int64 v68; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v69; // rcx
  HANDLE v70; // rcx
  SIZE_T v71; // rax
  __int64 v72; // rcx
  void *v73; // rax
  LPWCH v74; // rsi
  unsigned int v75; // eax
  LPWCH v76; // rsi
  int v77; // eax
  unsigned int *v78; // r8
  int v79; // r13d
  int v80; // eax
  char v81; // dl
  int v82; // ecx
  unsigned int v83; // r8d
  int v84; // r9d
  unsigned int v85; // r8d
  int v86; // r9d
  unsigned int v87; // r8d
  int v88; // r9d
  struct CreateProcessExtensions::ErrorContext *v89; // r13
  struct _APPX_PROCESS_CONTEXT *v90; // r13
  int v91; // eax
  char v92; // al
  __int64 v93; // rcx
  struct CreateProcessExtensions::ErrorContext *v94; // rax
  PVOID v95; // r15
  const unsigned __int16 *v96; // r8
  PVOID v97; // rdx
  ARI::CreateProcessExtensions *v98; // rcx
  int ContextForChildProcess; // eax
  unsigned int v100; // r12d
  _QWORD **v101; // rax
  _QWORD *v102; // rax
  unsigned __int64 v103; // rdx
  unsigned __int8 v104; // cl
  void *v105; // rdx
  __int64 v106; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v107; // rcx
  const char *v108; // r9
  signed int LastError; // eax
  __int64 v110; // rcx
  __int64 v111; // rcx
  __int64 v112; // rcx
  __int64 v113; // rcx
  __int64 v114; // rcx
  __int64 v115; // rcx
  __int64 v116; // rcx
  __int64 v117; // rcx
  unsigned __int64 v118; // rdx
  unsigned __int8 v119; // cl
  __int64 v120; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v121; // rcx
  unsigned int v122; // r12d
  unsigned int i; // r15d
  unsigned int v124; // r15d
  unsigned __int64 v125; // rdx
  unsigned __int8 v126; // cl
  __int64 v127; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v128; // rcx
  unsigned __int64 v129; // rdx
  unsigned __int8 v130; // cl
  void *v131; // rdx
  __int64 v132; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v133; // rcx
  signed int v134; // eax
  NTSTATUS v135; // eax
  int AppContainerSidType; // eax
  void *v137; // rcx
  ULONG v138; // eax
  ULONG v139; // esi
  LPWCH v140; // rcx
  void *v141; // r15
  NTSTATUS v142; // eax
  unsigned int v143; // esi
  unsigned __int64 v144; // rdx
  unsigned __int8 v145; // cl
  void *v146; // rdx
  __int64 v147; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v148; // rcx
  NTSTATUS v149; // eax
  LPWCH v150; // rcx
  unsigned __int64 v151; // rdx
  unsigned __int8 v152; // cl
  __int64 v153; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v154; // rcx
  unsigned __int64 v155; // rdx
  unsigned __int8 v156; // cl
  __int64 v157; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v158; // rcx
  HANDLE v159; // rcx
  unsigned __int64 v160; // rdx
  unsigned __int8 v161; // cl
  __int64 v162; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v163; // rcx
  HANDLE v164; // rcx
  bool v165; // sf
  unsigned __int64 v166; // rdx
  unsigned __int8 v167; // cl
  __int64 v168; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v169; // rcx
  unsigned __int64 v170; // rdx
  unsigned __int8 v171; // cl
  __int64 v172; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v173; // rcx
  void *v174; // rcx
  void *v175; // rcx
  ARI::Internal *v176; // rcx
  unsigned __int64 v177; // rdx
  __int64 v178; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v179; // rcx
  HANDLE v180; // rcx
  unsigned __int64 v181; // rdx
  unsigned __int8 v182; // cl
  __int64 v183; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v184; // rcx
  void *v185; // rcx
  unsigned __int64 v186; // rdx
  unsigned __int8 v187; // cl
  __int64 v188; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v189; // rcx
  HANDLE v190; // rcx
  unsigned __int64 v191; // rdx
  unsigned __int8 v192; // cl
  __int64 v193; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v194; // rcx
  Common *v195; // rcx
  unsigned __int64 v196; // rdx
  unsigned __int8 v197; // cl
  __int64 v198; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v199; // rcx
  PVOID v200; // rcx
  unsigned __int8 v201; // cl
  __int64 v202; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v203; // rcx
  __int64 v204; // rdx
  unsigned __int64 v205; // rdx
  unsigned __int8 v206; // cl
  __int64 v207; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v208; // rcx
  unsigned __int64 v209; // rdx
  unsigned __int8 v210; // cl
  __int64 v211; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v212; // rcx
  LSTATUS v213; // eax
  __int64 v214; // rcx
  __int64 v215; // rcx
  unsigned __int64 v216; // rdx
  unsigned __int8 v217; // cl
  __int64 v218; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v219; // rcx
  unsigned __int64 v220; // rdx
  unsigned __int8 v221; // cl
  __int64 v222; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v223; // rcx
  unsigned __int64 v224; // rdx
  unsigned __int8 v225; // cl
  __int64 v226; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v227; // rcx
  unsigned __int64 v228; // rdx
  unsigned __int8 v229; // cl
  __int64 v230; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v231; // rcx
  unsigned __int64 v232; // rdx
  unsigned __int8 v233; // cl
  __int64 v234; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v235; // rcx
  unsigned __int64 v236; // rdx
  unsigned __int8 v237; // cl
  __int64 v238; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v239; // rcx
  unsigned __int64 v240; // rdx
  unsigned __int8 v241; // cl
  __int64 v242; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v243; // rcx
  bool *ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengthf; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  int ReturnLengthb; // [rsp+20h] [rbp-E0h]
  int ReturnLengthg; // [rsp+20h] [rbp-E0h]
  int ReturnLengthh; // [rsp+20h] [rbp-E0h]
  unsigned int ReturnLengthc; // [rsp+20h] [rbp-E0h]
  void **ReturnLengthd; // [rsp+20h] [rbp-E0h]
  int ReturnLengthe; // [rsp+20h] [rbp-E0h]
  void **v253; // [rsp+30h] [rbp-D0h]
  unsigned int v254; // [rsp+38h] [rbp-C8h]
  bool v255; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL v257; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-88h]
  HLOCAL v259; // [rsp+80h] [rbp-80h] BYREF
  PSID Sid; // [rsp+88h] [rbp-78h]
  __int16 v261; // [rsp+90h] [rbp-70h] BYREF
  char v262; // [rsp+92h] [rbp-6Eh] BYREF
  __int16 v263; // [rsp+93h] [rbp-6Dh] BYREF
  char v264; // [rsp+95h] [rbp-6Bh] BYREF
  __int64 v265; // [rsp+98h] [rbp-68h] BYREF
  void *v266; // [rsp+A0h] [rbp-60h]
  struct _APPX_PROCESS_CONTEXT *v267; // [rsp+A8h] [rbp-58h]
  LPWCH penv; // [rsp+B0h] [rbp-50h] BYREF
  PVOID P[2]; // [rsp+B8h] [rbp-48h] BYREF
  int v270; // [rsp+C8h] [rbp-38h]
  int v271; // [rsp+D0h] [rbp-30h]
  WCHAR *v272; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v273; // [rsp+E0h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+E8h] [rbp-18h] BYREF
  ULONG Length; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v276; // [rsp+F4h] [rbp-Ch] BYREF
  void **v277; // [rsp+F8h] [rbp-8h] BYREF
  void **v278; // [rsp+100h] [rbp+0h] BYREF
  PVOID v279[2]; // [rsp+108h] [rbp+8h] BYREF
  int v280; // [rsp+118h] [rbp+18h]
  BYTE Data[4]; // [rsp+120h] [rbp+20h] BYREF
  int v282; // [rsp+124h] [rbp+24h] BYREF
  unsigned __int16 v283[2]; // [rsp+128h] [rbp+28h] BYREF
  int v284; // [rsp+12Ch] [rbp+2Ch] BYREF
  bool v285[4]; // [rsp+130h] [rbp+30h] BYREF
  int v286; // [rsp+134h] [rbp+34h] BYREF
  DWORD cbData; // [rsp+138h] [rbp+38h] BYREF
  ULONG v288; // [rsp+13Ch] [rbp+3Ch] BYREF
  ULONG v289; // [rsp+140h] [rbp+40h] BYREF
  HANDLE TokenHandlea; // [rsp+148h] [rbp+48h]
  struct _UNICODE_STRING Destination; // [rsp+150h] [rbp+50h] BYREF
  __int128 v292; // [rsp+160h] [rbp+60h] BYREF
  __int64 v293; // [rsp+170h] [rbp+70h]
  __int64 v294; // [rsp+178h] [rbp+78h]
  __int64 v295; // [rsp+180h] [rbp+80h]
  __int64 v296; // [rsp+188h] [rbp+88h]
  __int64 v297; // [rsp+190h] [rbp+90h]
  __int64 v298; // [rsp+198h] [rbp+98h]
  __int128 v299; // [rsp+1A0h] [rbp+A0h]
  int v300; // [rsp+1B0h] [rbp+B0h]
  __int64 v301; // [rsp+1B8h] [rbp+B8h]
  __int64 v302; // [rsp+1C0h] [rbp+C0h]
  __int64 v303; // [rsp+1D0h] [rbp+D0h] BYREF
  struct CreateProcessExtensions::ErrorContext *v304; // [rsp+1D8h] [rbp+D8h]
  _QWORD v305[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 *v306; // [rsp+1F0h] [rbp+F0h]
  __int64 v307; // [rsp+1F8h] [rbp+F8h] BYREF
  char v308; // [rsp+200h] [rbp+100h]
  struct _APPX_PROCESS_CONTEXT **v309; // [rsp+208h] [rbp+108h]
  struct _UNICODE_STRING DestinationString; // [rsp+210h] [rbp+110h] BYREF
  __int128 v311; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v312[72]; // [rsp+230h] [rbp+130h] BYREF
  PSID SourceSid; // [rsp+278h] [rbp+178h]
  __int64 v314; // [rsp+280h] [rbp+180h]
  _BYTE pSid2[80]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v316[80]; // [rsp+2E0h] [rbp+1E0h] BYREF
  PSID Sid2[10]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE DestinationSid[80]; // [rsp+380h] [rbp+280h] BYREF
  PSID TokenInformation[12]; // [rsp+3D0h] [rbp+2D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+378h]

  v5 = 0;
  v309 = a5;
  hObject = 0;
  v304 = a4;
  TokenHandlea = TokenHandle;
  v7 = TokenHandle;
  v8 = (wil::TraceLoggingProvider *)wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
                                      TokenHandle,
                                      _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
  if ( wil::TraceLoggingProvider::IsEnabled_(v8, 0, 0) )
  {
    wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
      v9,
      _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
    AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Start_(v10);
  }
  *((_DWORD *)a4 + 1) = 200;
  if ( !v7 )
  {
    v149 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xBu, &hObject);
    if ( v149 < 0 )
    {
      BaseSetLastNTError((unsigned int)v149);
      HResultFromLastError = Common::GetHResultFromLastError(v195);
      if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v197, v196) )
      {
        wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
          v198,
          _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
        AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v199);
      }
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      return HResultFromLastError;
    }
    v7 = hObject;
    TokenHandlea = hObject;
  }
  v280 = 0;
  v264 = 0;
  v263 = 0;
  v261 = 0;
  v262 = 0;
  *(_OWORD *)v279 = 0;
  v270 = 0;
  *(_OWORD *)P = 0;
  EffectivePackageMoniker = VerifyParametersAndGetEffectivePackageMoniker(
                              v7,
                              (__int64)P,
                              (__int64)&v263 + 1,
                              (__int64)&v261 + 1,
                              (__int64)&v264,
                              (__int64)&v263,
                              (__int64)&v261,
                              (__int64)&v262);
  HResultFromLastError = EffectivePackageMoniker;
  if ( EffectivePackageMoniker < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E9,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)(unsigned int)EffectivePackageMoniker,
      (int)ReturnLength);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    v192 = (unsigned __int8)v279[1];
    if ( v279[1] )
      Common::GlobalHeap::Free(v279[1]);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v192, v191) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v193,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v194);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      return HResultFromLastError;
    }
    return HResultFromLastError;
  }
  if ( !LODWORD(v279[0]) )
  {
    v200 = P[1];
    *a5 = 0;
    if ( v200 )
      Common::GlobalHeap::Free(v200);
    v201 = (unsigned __int8)v279[1];
    if ( v279[1] )
      Common::GlobalHeap::Free(v279[1]);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v201, v12) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v202,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v203);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 0;
  }
  ProcessHeap = ReservedForLocalUse::g_heap;
  Sid = 0;
  v266 = 0;
  v272 = 0;
  v284 = 0;
  *(_DWORD *)v283 = 0;
  v257 = 0;
  v277 = 0;
  v259 = 0;
  hMem = 0;
  LODWORD(v278) = 0;
  *(_DWORD *)v285 = 0;
  if ( !ReservedForLocalUse::g_heap )
  {
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
    ReservedForLocalUse::g_heap = ProcessHeap;
  }
  Heap = (struct _APPX_PROCESS_CONTEXT *)RtlAllocateHeap(ProcessHeap, 0, 0x60u);
  v267 = Heap;
  v16 = Heap;
  if ( !Heap )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x306,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)0x8007000ELL,
      (int)ReturnLength);
    Common::GlobalHeap::Free(0);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(0);
    if ( Sid )
      RtlFreeSid(Sid);
    Common::GlobalHeap::Free(0);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    v182 = (unsigned __int8)v279[1];
    if ( v279[1] )
      Common::GlobalHeap::Free(v279[1]);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v182, v181) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v183,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v184);
    }
    v180 = hObject;
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return 2147942414LL;
LABEL_299:
    CloseHandle(v180);
    return 2147942414LL;
  }
  memset_0(Heap, 0, 0x60u);
  v17 = ReservedForLocalUse::g_heap;
  if ( !ReservedForLocalUse::g_heap )
  {
    v17 = NtCurrentPeb()->ProcessHeap;
    ReservedForLocalUse::g_heap = v17;
  }
  v18 = RtlAllocateHeap(v17, 0, 0x18u);
  v19 = v18;
  if ( !v18 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30B,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)0x8007000ELL,
      (int)ReturnLength);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(v16);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(0);
    if ( Sid )
      RtlFreeSid(Sid);
    Common::GlobalHeap::Free(0);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    v176 = (ARI::Internal *)v279[1];
    if ( !v279[1] )
    {
LABEL_296:
      if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled((unsigned __int8)v176, v177) )
      {
        wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
          v178,
          _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
        AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v179);
      }
      v180 = hObject;
      if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
        return 2147942414LL;
      goto LABEL_299;
    }
LABEL_295:
    Common::GlobalHeap::Free(v176);
    goto LABEL_296;
  }
  *v18 = 0;
  v20 = (ARI::Internal *)v279[1];
  v18[2] = 0;
  v18[1] = 0;
  if ( !(_BYTE)v261 )
  {
    if ( v20 && *(_WORD *)v20 )
    {
      v288 = 0;
      v21 = -6;
      if ( v7 )
        v21 = (__int64)v7;
      v22 = NtQueryInformationToken((HANDLE)v21, TokenUser, TokenInformation, 0x54u, &v288);
      if ( v22 < 0 || (v23 = TokenInformation[0], v22 = RtlCopySid(0x44u, DestinationSid, TokenInformation[0]), v22 < 0) )
      {
        v24 = (void *)RtlNtStatusToDosErrorNoTeb(v22);
        ARI::Internal::EtwGetPackageStatusForUserError(v20, v55, v24, v56);
      }
      else
      {
        RtlLengthSid(v23);
        LODWORD(v24) = SRGetPackageStatusForUserSid(DestinationSid, v20, &v284);
        if ( ((unsigned int)v24 & 0x1FFF0000) == 0x70000 )
          LODWORD(v24) = (unsigned __int16)v24;
        Common::GlobalHeap::Free(0);
      }
      if ( !(_DWORD)v24 )
      {
        v308 = 1;
        v265 = 0;
        v306 = &v265;
        v307 = 0;
        v25 = SRCacheManager_Open(0, &v307);
        if ( v308 )
        {
          v26 = *v306;
          *v306 = v307;
          if ( v26 )
            SRCacheManager_Close(v26);
        }
        if ( (v25 & 0x80000000) != 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA5,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-manager.hpp",
            (const char *)v25,
            (int)ReturnLength);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x314,
            (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
            (const char *)v25,
            ReturnLengthf);
          wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v265, 0);
LABEL_28:
          Common::GlobalHeap::Free(v19);
          Common::GlobalHeap::Free(v16);
          LocalFree(hMem);
          LocalFree(v259);
          LocalFree(v257);
          Common::GlobalHeap::Free(0);
          Common::GlobalHeap::Free(0);
          if ( Sid )
            RtlFreeSid(Sid);
          Common::GlobalHeap::Free(0);
          v28 = (unsigned __int8)P[1];
          if ( P[1] )
            Common::GlobalHeap::Free(P[1]);
          if ( v20 )
            Common::GlobalHeap::Free(v20);
          if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v28, v27) )
          {
            wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
              v29,
              _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
            AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v30);
          }
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          return v25;
        }
        v293 = 0;
        v31 = 0;
        v292 = 0;
        v299 = 0;
        v255 = 0;
        v294 = 0;
        v295 = 0;
        v296 = 0;
        v297 = 0;
        v298 = 0;
        v300 = 0;
        v301 = 0;
        v302 = 0;
        v303 = 0;
        PackagePath_Internal = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
                                 (struct StateRepository::Cache::Manager_NoThrow *)&v265,
                                 (const unsigned __int16 *)v20,
                                 &v303);
        if ( PackagePath_Internal < 0 )
        {
          v64 = 1165;
        }
        else
        {
          if ( !v303 )
            goto LABEL_42;
          ReturnLength = &v255;
          PackagePath_Internal = StateRepository::Cache::Entity::Package_NoThrow::Get(&v265, v303, 2058, &v292);
          if ( PackagePath_Internal >= 0 )
          {
            v31 = v255;
LABEL_42:
            if ( !v31 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x31C,
                (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                (const char *)0x80070002LL,
                (int)ReturnLength);
              StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v292);
              wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v265, 0);
              Common::GlobalHeap::Free(v19);
              Common::GlobalHeap::Free(v16);
              LocalFree(hMem);
              LocalFree(v259);
              LocalFree(v257);
              Common::GlobalHeap::Free(0);
              Common::GlobalHeap::Free(0);
              if ( Sid )
                RtlFreeSid(Sid);
              Common::GlobalHeap::Free(0);
              if ( P[1] )
                Common::GlobalHeap::Free(P[1]);
              Common::GlobalHeap::Free(v20);
              if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v161, v160) )
              {
                wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
                  v162,
                  _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
                AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v163);
              }
              v164 = hObject;
              if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
                return 2147942402LL;
              goto LABEL_369;
            }
            v255 = 0;
            v311 = 0;
            memset_0(v312, 0, 0x44u);
            v33 = v293;
            SourceSid = 0;
            v314 = 0;
            if ( v293 )
            {
              v273 = 0;
              v34 = StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(
                      (struct StateRepository::Cache::Manager_NoThrow *)&v265,
                      v293,
                      (struct StateRepository::Cache::Context_NoThrow *)&v273,
                      &v255);
              v25 = v34;
              if ( v34 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xAF,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
                  (const char *)(unsigned int)v34,
                  (int)ReturnLength);
                v93 = v273;
                v273 = 0;
                if ( v93 )
LABEL_146:
                  SRCacheContext_Close();
              }
              else
              {
                v35 = v255;
                if ( !v255 )
                {
                  v214 = v273;
                  v273 = 0;
                  if ( v214 )
                    SRCacheContext_Close();
LABEL_361:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x321,
                    (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                    (const char *)0x80070002LL,
                    (int)ReturnLength);
                  StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)&v311);
                  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v292);
                  wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v265, 0);
                  Common::GlobalHeap::Free(v19);
                  Common::GlobalHeap::Free(v16);
                  LocalFree(hMem);
                  LocalFree(v259);
                  LocalFree(v257);
                  Common::GlobalHeap::Free(0);
                  Common::GlobalHeap::Free(0);
                  if ( Sid )
                    RtlFreeSid(Sid);
                  Common::GlobalHeap::Free(0);
                  if ( P[1] )
                    Common::GlobalHeap::Free(P[1]);
                  Common::GlobalHeap::Free(v20);
                  if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v210, v209) )
                  {
                    wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
                      v211,
                      _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
                    AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v212);
                  }
                  if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
                    return 2147942402LL;
                  v164 = hObject;
LABEL_369:
                  CloseHandle(v164);
                  return 2147942402LL;
                }
                v36 = StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(&v273, &v311, 0, v33);
                v25 = v36;
                if ( v36 >= 0 )
                {
                  v37 = v273;
                  v273 = 0;
                  if ( v37 )
                    SRCacheContext_Close();
                  if ( v35 )
                  {
                    hKey = 0;
                    penv = 0;
                    v38 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                            &penv,
                            L"%s\\%s",
                            L"Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\R"
                             "epository\\Packages",
                            v20);
                    v25 = v38;
                    if ( v38 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x286,
                        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                        (const char *)(unsigned int)v38,
                        (int)ReturnLength);
                      if ( penv )
                        FreeEnvironmentStringsW(penv);
                      v57 = hKey;
                      if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
                        goto LABEL_79;
                    }
                    else
                    {
                      v39 = penv;
                      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                        RegCloseKey(hKey);
                      hKey = 0;
                      v40 = RegOpenKeyExInternalW(HKEY_LOCAL_MACHINE, v39, (PHANDLE)&hKey, 0);
                      v25 = v40;
                      if ( v40 > 0 )
                        v25 = (unsigned __int16)v40 | 0x80070000;
                      if ( (int)v25 > -2147024895 && v25 + 2147024892 > 0x7FF8FFFB )
                      {
                        v41 = hKey;
                        v271 = 0;
                        if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
                        {
                          if ( v39 )
                          {
                            FreeEnvironmentStringsW(v39);
                            v41 = hKey;
                          }
                          if ( (unsigned __int64)v41 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
                            goto LABEL_61;
                          goto LABEL_395;
                        }
                        *(_DWORD *)Data = 0;
                        cbData = 4;
                        v213 = RegQueryValueExW(hKey, L"FullTrust", 0, 0, Data, &cbData);
                        v25 = v213;
                        if ( v213 > 0 )
                          v25 = (unsigned __int16)v213 | 0x80070000;
                        if ( (int)v25 > -2147024895 && v25 + 2147024892 > 0x7FF8FFFB )
                        {
                          if ( (v25 & 0x80000000) == 0 )
                          {
                            if ( *(_DWORD *)Data == 1 )
                              v271 = 1;
                            if ( v39 )
                              FreeEnvironmentStringsW(v39);
                            v41 = hKey;
                            if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
                              goto LABEL_61;
                          }
                          else
                          {
                            if ( v39 )
                              FreeEnvironmentStringsW(v39);
                            v41 = hKey;
                            if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
                              goto LABEL_61;
                          }
LABEL_395:
                          RegCloseKey(v41);
LABEL_61:
                          v42 = SourceSid;
                          v5 = BYTE4(v294) & 1;
                          RtlSetLastWin32Error(0);
                          v43 = RtlLengthSid(v42);
                          v44 = ReservedForLocalUse::g_heap;
                          v45 = v43;
                          if ( !ReservedForLocalUse::g_heap )
                          {
                            v44 = NtCurrentPeb()->ProcessHeap;
                            ReservedForLocalUse::g_heap = v44;
                          }
                          v46 = RtlAllocateHeap(v44, 0, v43);
                          if ( !v46 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x32A,
                              (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                              (const char *)0x8007000ELL,
                              ReturnLengtha);
                            StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)&v311);
                            StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v292);
                            wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(
                              &v265,
                              0);
                            Common::GlobalHeap::Free(v19);
                            Common::GlobalHeap::Free(v16);
                            LocalFree(hMem);
                            LocalFree(v259);
                            LocalFree(v257);
                            Common::GlobalHeap::Free(0);
                            Common::GlobalHeap::Free(0);
                            if ( Sid )
                              RtlFreeSid(Sid);
                            v175 = 0;
                            goto LABEL_292;
                          }
                          Common::GlobalHeap::Free(0);
                          v47 = RtlCopySid(v45, v46, v42);
                          if ( v47 < 0 )
                          {
                            BaseSetLastNTError((unsigned int)v47);
                            LastError = wil::details::in1diag3::Return_GetLastError(
                                          retaddr,
                                          (void *)0x32B,
                                          (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                                          v108);
                            v110 = v314;
                            v314 = 0;
                            PackagePath_Internal = LastError;
                            if ( v110 )
                              SRCache_Free();
                            v111 = *((_QWORD *)&v311 + 1);
                            *((_QWORD *)&v311 + 1) = 0;
                            if ( v111 )
                              SRCache_Free();
                            v112 = v301;
                            v301 = 0;
                            if ( v112 )
                              SRCache_Free();
                            v113 = *((_QWORD *)&v299 + 1);
                            *((_QWORD *)&v299 + 1) = 0;
                            if ( v113 )
                              SRCache_Free();
                            v114 = v299;
                            *(_QWORD *)&v299 = 0;
                            if ( v114 )
                              SRCache_Free();
                            v115 = v298;
                            v298 = 0;
                            if ( v115 )
                              SRCache_Free();
                            v116 = *((_QWORD *)&v292 + 1);
                            *((_QWORD *)&v292 + 1) = 0;
                            if ( v116 )
                              SRCache_Free();
                            v117 = v265;
                            v265 = 0;
                            if ( v117 )
                              SRCacheManager_Close(v117);
                            Common::GlobalHeap::Free(v19);
                            Common::GlobalHeap::Free(v16);
                            LocalFree(hMem);
                            LocalFree(v259);
                            LocalFree(v257);
                            Common::GlobalHeap::Free(0);
                            if ( Sid )
                              RtlFreeSid(Sid);
                            Common::GlobalHeap::Free(v46);
                            if ( P[1] )
                              RtlFreeHeap(ReservedForLocalUse::g_heap, 0, P[1]);
                            RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v20);
LABEL_181:
                            if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(
                                   v119,
                                   v118) )
                            {
                              wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
                                v120,
                                _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
                              AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v121);
                            }
                            v70 = hObject;
                            if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
                              return (unsigned int)PackagePath_Internal;
                            goto LABEL_102;
                          }
                          v49 = HIBYTE(v261) == 0;
                          Status = 87;
                          *(_QWORD *)v19 = v46;
                          if ( v49 )
                            goto LABEL_118;
                          if ( v300 != 12 )
                          {
                            LODWORD(v51) = (_DWORD)v266;
                            goto LABEL_108;
                          }
                          LODWORD(v51) = 0;
                          v286 = 0;
                          RtlGetDeviceFamilyInfoEnum(0, &v286, 0);
                          if ( v286 != 5 )
                            goto LABEL_108;
                          DestinationString = 0;
                          Destination = 0;
                          RtlInitUnicodeString(&DestinationString, L"%windir%\\system32");
                          Length = 0;
                          Destination = 0;
                          v52 = RtlExpandEnvironmentStrings_U(0, &DestinationString, &Destination, &Length);
                          PackagePath_Internal = v52;
                          if ( !v52 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x33F,
                              (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                              (const char *)0x8000FFFFLL,
                              ReturnLengtha);
                            StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)&v311);
                            StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v292);
                            wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(
                              &v265,
                              0);
                            Common::GlobalHeap::Free(v19);
                            Common::GlobalHeap::Free(v16);
                            LocalFree(hMem);
                            LocalFree(v259);
                            LocalFree(v257);
                            v185 = 0;
                            goto LABEL_312;
                          }
                          if ( v52 == -1073741789 )
                          {
                            v53 = 2LL * Length;
                            penv = 0;
                            if ( !is_mul_ok(Length, 2u) )
                              v53 = -1;
                            Common::GlobalHeap::Alloc(v53, (void **)&penv);
                            v51 = penv;
                            v266 = penv;
                            if ( !penv )
                            {
                              v204 = 835;
                              goto LABEL_351;
                            }
                            Common::GlobalHeap::Free(0);
                            v272 = v51;
                            *(_QWORD *)&Destination.Length = 0;
                            Destination.Buffer = v51;
                            *(_DWORD *)&Destination.MaximumLength = (unsigned __int16)(2 * Length);
                            v54 = RtlExpandEnvironmentStrings_U(0, &DestinationString, &Destination, &Length);
                            if ( v54 < 0 )
                            {
                              v134 = wil::details::in1diag3::Return_NtStatus(
                                       retaddr,
                                       (void *)0x345,
                                       (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                                       (const char *)(unsigned int)v54,
                                       ReturnLengtha);
LABEL_213:
                              PackagePath_Internal = v134;
                              StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)&v311);
                              StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v292);
                              wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(
                                &v265,
                                0);
                              Common::GlobalHeap::Free(v19);
                              Common::GlobalHeap::Free(v16);
                              LocalFree(hMem);
                              LocalFree(v259);
                              LocalFree(v257);
                              Common::GlobalHeap::Free(v266);
                              Common::GlobalHeap::Free(0);
                              if ( Sid )
                                RtlFreeSid(Sid);
                              Common::GlobalHeap::Free(v46);
                              if ( P[1] )
                                Common::GlobalHeap::Free(P[1]);
                              Common::GlobalHeap::Free(v20);
                              goto LABEL_181;
                            }
                            *((_QWORD *)v16 + 2) = v51;
LABEL_108:
                            if ( !*((_QWORD *)v16 + 2) )
                            {
                              v276 = 0;
                              ReturnLengtha = (int)v51;
                              LOBYTE(v48) = 1;
                              PackagePath_Internal = ARI::GetPackagePath_Internal(v48, v20, 2, &v276);
                              if ( PackagePath_Internal )
                              {
                                if ( PackagePath_Internal != 122 )
                                {
                                  v165 = PackagePath_Internal < 0;
                                  if ( PackagePath_Internal > 0 )
                                  {
                                    PackagePath_Internal = (unsigned __int16)PackagePath_Internal | 0x80070000;
                                    v165 = PackagePath_Internal < 0;
                                  }
                                  if ( v165 )
                                    wil::details::in1diag3::Return_Hr(
                                      retaddr,
                                      (void *)0x350,
                                      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                                      (const char *)(unsigned int)PackagePath_Internal,
                                      ReturnLengtha);
                                  StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)&v311);
                                  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v292);
                                  wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(
                                    &v265,
                                    0);
                                  Common::GlobalHeap::Free(v19);
                                  Common::GlobalHeap::Free(v16);
                                  LocalFree(hMem);
                                  LocalFree(v259);
                                  LocalFree(v257);
                                  Common::GlobalHeap::Free(v266);
                                  Common::GlobalHeap::Free(0);
                                  if ( Sid )
                                    RtlFreeSid(Sid);
                                  Common::GlobalHeap::Free(v46);
                                  if ( P[1] )
                                    Common::GlobalHeap::Free(P[1]);
                                  Common::GlobalHeap::Free(v20);
                                  if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(
                                         v167,
                                         v166) )
                                  {
                                    wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
                                      v168,
                                      _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
                                    AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v169);
                                  }
                                  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                                  {
                                    CloseHandle(hObject);
                                    return (unsigned int)PackagePath_Internal;
                                  }
                                  return (unsigned int)PackagePath_Internal;
                                }
                                v71 = 2LL * v276;
                                penv = 0;
                                if ( !is_mul_ok(v276, 2u) )
                                  v71 = -1;
                                Common::GlobalHeap::Alloc(v71, (void **)&penv);
                                v73 = v266;
                                v74 = penv;
                                if ( v266 != penv )
                                {
                                  Common::GlobalHeap::Free(v266);
                                  v73 = v74;
                                  v266 = v74;
                                  v272 = v74;
                                }
                                if ( v73 )
                                {
                                  ReturnLengthc = (unsigned int)v73;
                                  LOBYTE(v72) = 1;
                                  v75 = ARI::GetPackagePath_Internal(v72, v20, 2, &v276);
                                  if ( !v75 )
                                  {
                                    *((_QWORD *)v16 + 2) = v266;
                                    goto LABEL_118;
                                  }
                                  v134 = wil::details::in1diag3::Return_Win32(
                                           retaddr,
                                           (void *)0x354,
                                           (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                                           (const char *)v75,
                                           ReturnLengthc);
                                  goto LABEL_213;
                                }
                                v204 = 851;
LABEL_351:
                                wil::details::in1diag3::Return_Hr(
                                  retaddr,
                                  (void *)v204,
                                  (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                                  (const char *)0x8007000ELL,
                                  ReturnLengtha);
                                StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)&v311);
                                StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v292);
                                wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(
                                  &v265,
                                  0);
                                Common::GlobalHeap::Free(v19);
                                Common::GlobalHeap::Free(v16);
                                LocalFree(hMem);
                                LocalFree(v259);
                                LocalFree(v257);
                                v174 = 0;
LABEL_289:
                                Common::GlobalHeap::Free(v174);
                                Common::GlobalHeap::Free(0);
                                if ( Sid )
                                  RtlFreeSid(Sid);
                                v175 = v46;
LABEL_292:
                                Common::GlobalHeap::Free(v175);
                                if ( P[1] )
                                  Common::GlobalHeap::Free(P[1]);
                                v176 = v20;
                                goto LABEL_295;
                              }
                              wil::details::in1diag3::Return_Hr(
                                retaddr,
                                (void *)0x34F,
                                (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                                (const char *)0x8000FFFFLL,
                                ReturnLengtha);
                              StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)&v311);
                              StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v292);
                              wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(
                                &v265,
                                0);
                              Common::GlobalHeap::Free(v19);
                              Common::GlobalHeap::Free(v16);
                              LocalFree(hMem);
                              LocalFree(v259);
                              LocalFree(v257);
                              v185 = v266;
LABEL_312:
                              Common::GlobalHeap::Free(v185);
                              Common::GlobalHeap::Free(0);
                              if ( Sid )
                                RtlFreeSid(Sid);
                              Common::GlobalHeap::Free(v46);
                              if ( P[1] )
                                Common::GlobalHeap::Free(P[1]);
                              Common::GlobalHeap::Free(v20);
                              if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(
                                     v187,
                                     v186) )
                              {
                                wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
                                  v188,
                                  _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
                                AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v189);
                              }
                              v190 = hObject;
                              if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
                                return 2147549183LL;
                              goto LABEL_360;
                            }
LABEL_118:
                            StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)&v311);
                            StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v292);
                            wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(
                              &v265,
                              0);
                            goto LABEL_119;
                          }
                          if ( v52 > 0 )
                            PackagePath_Internal = (unsigned __int16)v52 | 0x80070000;
                          if ( PackagePath_Internal < 0 )
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x340,
                              (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                              (const char *)(unsigned int)PackagePath_Internal,
                              ReturnLengtha);
                          StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)&v311);
                          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v292);
                          wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(
                            &v265,
                            0);
                          Common::GlobalHeap::Free(v19);
                          Common::GlobalHeap::Free(v16);
                          LocalFree(hMem);
                          LocalFree(v259);
                          LocalFree(v257);
                          Common::GlobalHeap::Free(0);
                          Common::GlobalHeap::Free(0);
                          if ( Sid )
                            RtlFreeSid(Sid);
                          v65 = v46;
LABEL_96:
                          Common::GlobalHeap::Free(v65);
                          if ( P[1] )
                            Common::GlobalHeap::Free(P[1]);
                          Common::GlobalHeap::Free(v20);
                          if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v67, v66) )
                          {
                            wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
                              v68,
                              _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
                            AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v69);
                          }
                          if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
                            return (unsigned int)PackagePath_Internal;
                          v70 = hObject;
LABEL_102:
                          CloseHandle(v70);
                          return (unsigned int)PackagePath_Internal;
                        }
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x290,
                          (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                          (const char *)v25,
                          ReturnLengtha);
                        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&penv);
                        Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
                        goto LABEL_79;
                      }
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x5A,
                        (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
                        (const char *)v25,
                        ReturnLengtha);
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x288,
                        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                        (const char *)v25,
                        ReturnLengthh);
                      if ( v39 )
                        FreeEnvironmentStringsW(v39);
                      v57 = hKey;
                      if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
                      {
LABEL_79:
                        v58 = 803;
LABEL_80:
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)v58,
                          (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                          (const char *)v25,
                          ReturnLengthb);
                        StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)&v311);
                        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v292);
                        wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(
                          &v265,
                          0);
                        Common::GlobalHeap::Free(v19);
                        Common::GlobalHeap::Free(v16);
                        LocalFree(hMem);
                        LocalFree(v259);
                        LocalFree(v257);
                        Common::GlobalHeap::Free(0);
                        Common::GlobalHeap::Free(0);
                        if ( Sid )
                          RtlFreeSid(Sid);
                        Common::GlobalHeap::Free(0);
                        if ( P[1] )
                          Common::GlobalHeap::Free(P[1]);
                        Common::GlobalHeap::Free(v20);
                        if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v60, v59) )
                        {
                          wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
                            v61,
                            _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
                          AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v62);
                        }
                        if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
                          return v25;
                        CloseHandle(hObject);
                        return v25;
                      }
                    }
                    RegCloseKey(v57);
                    goto LABEL_79;
                  }
                  goto LABEL_361;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xB4,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
                  (const char *)(unsigned int)v36,
                  (int)ReturnLength);
                v215 = v273;
                v273 = 0;
                if ( v215 )
                  goto LABEL_146;
              }
            }
            else
            {
              v25 = -2147024809;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xAC,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
                (const char *)0x80070057LL,
                (int)ReturnLength);
            }
            v58 = 800;
            goto LABEL_80;
          }
          v64 = 1168;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v64,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
          (const char *)(unsigned int)PackagePath_Internal,
          (int)ReturnLength);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x31B,
          (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
          (const char *)(unsigned int)PackagePath_Internal,
          ReturnLengthg);
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v292);
        wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v265, 0);
        Common::GlobalHeap::Free(v19);
        Common::GlobalHeap::Free(v16);
        LocalFree(hMem);
        LocalFree(v259);
        LocalFree(v257);
        Common::GlobalHeap::Free(0);
        Common::GlobalHeap::Free(0);
        if ( Sid )
          RtlFreeSid(Sid);
        v65 = 0;
        goto LABEL_96;
      }
    }
    else
    {
      LODWORD(v24) = 87;
    }
    v25 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x311,
            (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
            (const char *)(unsigned int)v24,
            (unsigned int)ReturnLength);
    goto LABEL_28;
  }
  v46 = 0;
  v271 = 0;
  Status = 87;
LABEL_119:
  v76 = 0;
  v254 = 0;
  v253 = (void **)&v278;
  ReturnLengthd = (void **)((char *)&v277 + 4);
  v77 = QueryApplicationCapabilitiesEx(v20, &v257, &v277, &v259);
  v79 = v77;
  if ( v77 == -2147024444 )
    goto LABEL_127;
  if ( v77 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36F,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)(unsigned int)v77,
      (int)&v277 + 4);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v267);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::GlobalHeap::Free(v266);
    v150 = 0;
    goto LABEL_237;
  }
  v80 = v271;
  v81 = v262;
  if ( *(_DWORD *)v285 == 2 )
    v80 = 1;
  v271 = v80;
  v82 = HIDWORD(v277) + (_DWORD)v278 + (v262 != 0);
  v49 = (_DWORD)v277 + v82 == 0;
  v19[4] = (_DWORD)v277 + v82;
  if ( !v49 )
  {
    LOBYTE(v254) = v81;
    LODWORD(v253) = (_DWORD)v278;
    LODWORD(ReturnLengthd) = HIDWORD(v277);
    v79 = ReservedForLocalUse::ReallocateCapabilityArray(
            (ReservedForLocalUse *)(v19 + 2),
            (struct _SID_AND_ATTRIBUTES **)v257,
            (void **)(unsigned int)v277,
            (unsigned int)v259,
            ReturnLengthd,
            (unsigned int)hMem,
            v253,
            v254,
            (bool)v285);
    penv = (LPWCH)*((_QWORD *)v19 + 1);
    if ( penv )
    {
      Common::GlobalHeap::Free(0);
      v76 = penv;
    }
    ReservedForLocalUse::FreeSidsInSidArray((ReservedForLocalUse *)v257, (void **)(unsigned int)v277, v83, v84);
    ReservedForLocalUse::FreeSidsInSidArray((ReservedForLocalUse *)v259, (void **)HIDWORD(v277), v85, v86);
    ReservedForLocalUse::FreeSidsInSidArray((ReservedForLocalUse *)hMem, (void **)(unsigned int)v278, v87, v88);
    if ( v79 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x393,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
        (const char *)(unsigned int)v79,
        (int)ReturnLengthd);
      Common::GlobalHeap::Free(v19);
      Common::GlobalHeap::Free(v267);
      LocalFree(hMem);
      LocalFree(v259);
      LocalFree(v257);
      Common::GlobalHeap::Free(v266);
      v150 = v76;
LABEL_237:
      Common::GlobalHeap::Free(v150);
      if ( Sid )
        RtlFreeSid(Sid);
      Common::GlobalHeap::Free(v46);
      v152 = (unsigned __int8)P[1];
      if ( P[1] )
        Common::GlobalHeap::Free(P[1]);
      if ( v20 )
        Common::GlobalHeap::Free(v20);
      if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v152, v151) )
      {
        wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
          v153,
          _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
        AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v154);
      }
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      return (unsigned int)v79;
    }
  }
LABEL_127:
  v89 = v304;
  *((_DWORD *)v304 + 1) = 300;
  if ( (v284 & 0x20) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v267);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::GlobalHeap::Free(v266);
    Common::GlobalHeap::Free(v76);
    if ( Sid )
      RtlFreeSid(Sid);
    Common::GlobalHeap::Free(v46);
    v156 = (unsigned __int8)P[1];
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    if ( v20 )
      Common::GlobalHeap::Free(v20);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v156, v155) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v157,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v158);
    }
    v159 = hObject;
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return 2147958016LL;
LABEL_426:
    CloseHandle(v159);
    return 2147958016LL;
  }
  if ( (v284 & 0x800) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v267);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v272);
    Common::GlobalHeap::Free(v76);
    if ( Sid )
      RtlFreeSid(Sid);
    Common::GlobalHeap::Free(v46);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v279);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v217, v216) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v218,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v219);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      return 2147958031LL;
    }
    return 2147958031LL;
  }
  if ( (v284 & 0x4000307) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v267);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v272);
    Common::GlobalHeap::Free(v76);
    if ( Sid )
      RtlFreeSid(Sid);
    Common::GlobalHeap::Free(v46);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v279);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v221, v220) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v222,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v223);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      return 2147958012LL;
    }
    return 2147958012LL;
  }
  if ( (v284 & 0x98) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v267);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v272);
    Common::GlobalHeap::Free(v76);
    if ( Sid )
      RtlFreeSid(Sid);
    Common::GlobalHeap::Free(v46);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v279);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v225, v224) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v226,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v227);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      return 2147958106LL;
    }
    return 2147958106LL;
  }
  *((_DWORD *)v89 + 1) = 400;
  if ( !v20 || !*(_WORD *)v20 || (Status = ARI::Internal::GetStatus(v20, v283, v78)) != 0 )
  {
    v124 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3B1,
             (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
             (const char *)Status,
             (unsigned int)ReturnLengthd);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v267);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::GlobalHeap::Free(v266);
    Common::GlobalHeap::Free(v76);
    if ( Sid )
      RtlFreeSid(Sid);
    Common::GlobalHeap::Free(v46);
    v126 = (unsigned __int8)P[1];
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    if ( v20 )
      Common::GlobalHeap::Free(v20);
    goto LABEL_199;
  }
  if ( (*(_DWORD *)v283 & 0x80000) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v267);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v272);
    Common::GlobalHeap::Free(v76);
    if ( Sid )
      RtlFreeSid(Sid);
    Common::GlobalHeap::Free(v46);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v279);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v229, v228) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v230,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v231);
    }
    v159 = hObject;
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return 2147958016LL;
    goto LABEL_426;
  }
  if ( (*(_DWORD *)v283 & 0x400000) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v267);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v272);
    Common::GlobalHeap::Free(v76);
    if ( Sid )
      RtlFreeSid(Sid);
    Common::GlobalHeap::Free(v46);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v279);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v233, v232) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v234,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v235);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 2147958031LL;
  }
  if ( (*(_DWORD *)v283 & 0x4000347) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v267);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v272);
    Common::GlobalHeap::Free(v76);
    if ( Sid )
      RtlFreeSid(Sid);
    Common::GlobalHeap::Free(v46);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v279);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v237, v236) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v238,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v239);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 2147958012LL;
  }
  if ( (v283[0] & 0x98) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v267);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v272);
    Common::GlobalHeap::Free(v76);
    if ( Sid )
      RtlFreeSid(Sid);
    Common::GlobalHeap::Free(v46);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v279);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v241, v240) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v242,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v243);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 2147958106LL;
  }
  *((_DWORD *)v89 + 1) = 500;
  if ( (_BYTE)v263 == (_BYTE)Status )
    goto LABEL_139;
  v282 = 0;
  v289 = 76;
  v135 = NtQueryInformationToken(TokenHandlea, TokenAppContainerSid, Sid2, 0x4Cu, &v289);
  if ( v135 < 0 )
  {
    v124 = v135 | 0x10000000;
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v267);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v272);
    Common::GlobalHeap::Free(v76);
    if ( Sid )
      RtlFreeSid(Sid);
    goto LABEL_447;
  }
  AppContainerSidType = RtlGetAppContainerSidType(Sid2[0], &v282);
  if ( AppContainerSidType < 0 )
  {
    v124 = AppContainerSidType | 0x10000000;
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v267);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v272);
    Common::GlobalHeap::Free(v76);
    if ( Sid )
      RtlFreeSid(Sid);
LABEL_447:
    Common::GlobalHeap::Free(v46);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v279);
LABEL_199:
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v126, v125) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v127,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v128);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return v124;
  }
  v137 = *(void **)v19;
  if ( v282 == 1 )
  {
    if ( (unsigned __int8)RtlIsParentOfChildAppContainer(v137, Sid2[0]) )
    {
      v19[4] = 0;
      *((_QWORD *)v19 + 1) = 0;
      Common::GlobalHeap::Free(v76);
      v138 = RtlLengthSid(Sid2[0]);
      penv = 0;
      v139 = v138;
      Common::GlobalHeap::Alloc(v138, (void **)&penv);
      v140 = penv;
      *(_QWORD *)v19 = penv;
      if ( v140 )
      {
        Common::GlobalHeap::Free(v46);
        v141 = *(void **)v19;
        v46 = 0;
        if ( *(_QWORD *)v19 )
        {
          Common::GlobalHeap::Free(0);
          v46 = v141;
        }
        v142 = RtlCopySid(v139, *(PSID *)v19, Sid2[0]);
        if ( v142 < 0 )
        {
          v143 = v142 | 0x10000000;
          Common::GlobalHeap::Free(v19);
          Common::GlobalHeap::Free(v267);
          LocalFree(hMem);
          LocalFree(v259);
          LocalFree(v257);
          Common::GlobalHeap::Free(v266);
          Common::GlobalHeap::Free(0);
          if ( Sid )
            RtlFreeSid(Sid);
          Common::GlobalHeap::Free(v46);
          if ( P[1] )
            Common::GlobalHeap::Free(P[1]);
          Common::GlobalHeap::Free(v20);
          if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v145, v144) )
          {
            wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
              v147,
              _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
            AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v148);
          }
          Common::CloseHandleHelper((Common *)hObject, v146);
          return v143;
        }
        v76 = 0;
LABEL_139:
        v90 = v267;
        v91 = v271;
        *((_BYTE *)v267 + 80) &= ~1u;
        if ( *(_QWORD *)v19 )
        {
          if ( v91 )
            goto LABEL_147;
          if ( v76 )
          {
            if ( !(unsigned int)IgnoreProtectedAppProcess(v5) )
            {
              memset_0(v316, 0, 0x44u);
              memset_0(pSid2, 0, 0x44u);
              v305[0] = 1703960;
              v305[1] = L"protectedApp";
              if ( (int)RtlDeriveCapabilitySidsFromName(v305, v316, pSid2) >= 0 )
              {
                v122 = v19[4];
                for ( i = 0; i < v122; ++i )
                {
                  if ( EqualSid(*(PSID *)&v76[8 * i], pSid2) )
                  {
                    *((_BYTE *)v90 + 80) |= 1u;
                    break;
                  }
                }
              }
            }
          }
        }
        else if ( v91 )
        {
          goto LABEL_147;
        }
        if ( HIBYTE(v263) )
          *(_QWORD *)v90 = v19;
        if ( !v264 )
        {
          v92 = 0;
          goto LABEL_148;
        }
LABEL_147:
        v92 = 4;
LABEL_148:
        *((_BYTE *)v90 + 80) &= ~4u;
        *((_BYTE *)v90 + 80) |= v92;
        v94 = v304;
        v95 = P[1];
        v96 = (const unsigned __int16 *)(unsigned __int8)v261;
        v97 = P[1];
        v98 = (ARI::CreateProcessExtensions *)TokenHandlea;
        *((_QWORD *)v90 + 3) = v20;
        *((_DWORD *)v94 + 1) = 600;
        ContextForChildProcess = ARI::CreateProcessExtensions::LoadContextForChildProcess(
                                   v98,
                                   v97,
                                   v96,
                                   (int)v90,
                                   (struct _APPX_PROCESS_CONTEXT *)ReturnLengthd);
        v100 = ContextForChildProcess;
        if ( ContextForChildProcess < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x437,
            (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
            (const char *)(unsigned int)ContextForChildProcess,
            ReturnLengthe);
          Common::GlobalHeap::Free(v19);
          Common::GlobalHeap::Free(v90);
          LocalFree(hMem);
          LocalFree(v259);
          LocalFree(v257);
          Common::GlobalHeap::Free(v266);
          Common::GlobalHeap::Free(v76);
          if ( Sid )
            RtlFreeSid(Sid);
          Common::GlobalHeap::Free(v46);
          if ( v95 )
            Common::GlobalHeap::Free(v95);
          Common::GlobalHeap::Free(v20);
          if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v130, v129) )
          {
            wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
              v132,
              _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
            AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v133);
          }
          Common::CloseHandleHelper((Common *)hObject, v131);
          return v100;
        }
        else
        {
          *v309 = v90;
          CreateProcessExtensions::AcquireAppXContext(v90);
          v102 = *v101;
          if ( *v102 )
          {
            v46 = 0;
            v76 = 0;
            v19 = 0;
          }
          if ( v102[2] )
            v266 = 0;
          Common::GlobalHeap::Free(v19);
          Common::GlobalHeap::Free(0);
          LocalFree(hMem);
          LocalFree(v259);
          LocalFree(v257);
          Common::GlobalHeap::Free(v266);
          Common::GlobalHeap::Free(v76);
          if ( Sid )
            RtlFreeSid(Sid);
          Common::GlobalHeap::Free(v46);
          if ( v95 )
            Common::GlobalHeap::Free(v95);
          if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v104, v103) )
          {
            wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
              v106,
              _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
            AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v107);
          }
          Common::CloseHandleHelper((Common *)hObject, v105);
          return 0;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F6,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
        (const char *)0x8007000ELL,
        (int)ReturnLengthd);
      Common::GlobalHeap::Free(v19);
      Common::GlobalHeap::Free(v267);
      LocalFree(hMem);
      LocalFree(v259);
      LocalFree(v257);
      v174 = v266;
      goto LABEL_289;
    }
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v267);
    LocalFree(hMem);
    LocalFree(v259);
    LocalFree(v257);
    Common::GlobalHeap::Free(v266);
    Common::GlobalHeap::Free(v76);
    if ( Sid )
      RtlFreeSid(Sid);
    Common::GlobalHeap::Free(v46);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    Common::GlobalHeap::Free(v20);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v206, v205) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v207,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v208);
    }
    v190 = hObject;
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return 2147549183LL;
LABEL_360:
    CloseHandle(v190);
    return 2147549183LL;
  }
  if ( RtlEqualSid(v137, Sid2[0]) )
    goto LABEL_139;
  Common::GlobalHeap::Free(v19);
  Common::GlobalHeap::Free(v267);
  LocalFree(hMem);
  LocalFree(v259);
  LocalFree(v257);
  Common::GlobalHeap::Free(v266);
  Common::GlobalHeap::Free(v76);
  if ( Sid )
    RtlFreeSid(Sid);
  Common::GlobalHeap::Free(v46);
  if ( P[1] )
    Common::GlobalHeap::Free(P[1]);
  Common::GlobalHeap::Free(v20);
  if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v171, v170) )
  {
    wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
      v172,
      _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
    AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v173);
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800543b0  push    rbp
0x1800543b2  push    rbx
0x1800543b3  push    rsi
0x1800543b4  push    rdi
0x1800543b5  push    r12
0x1800543b7  push    r14
0x1800543b9  push    r15
0x1800543bb  lea     rbp, [rsp-340h]
0x1800543c3  sub     rsp, 440h
0x1800543ca  mov     rax, cs:__security_cookie
0x1800543d1  xor     rax, rsp
0x1800543d4  mov     [rbp+370h+var_40], rax
0x1800543db  mov     r15, [rbp+370h+arg_20]
0x1800543e2  mov     rdi, rdx
0x1800543e5  xor     r12d, r12d
0x1800543e8  mov     [rbp+370h+var_268], r15
0x1800543ef  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_234fc6f01c94939abb1aa6f0961130da_@@CA@XZ; _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_(void)
0x1800543f6  mov     [rsp+470h+hObject], r12
0x1800543fb  mov     r14, r9
0x1800543fe  mov     [rbp+370h+var_298], r9
0x180054405  mov     rbx, r8
0x180054408  mov     [rbp+370h+TokenHandle], rcx
0x18005440c  mov     rsi, rcx
0x18005440f  call    ?get@?$static_lazy@VAppxCreateProcessExtensionsTelemetry@AppxCreateProcessExtensions@@@details@wil@@QEAAPEAVAppxCreateProcessExtensionsTelemetry@AppxCreateProcessExtensions@@P6AXXZ@Z; wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(void (*)(void))
0x180054414  xor     r8d, r8d; unsigned __int64
0x180054417  xor     edx, edx; unsigned __int8
0x180054419  mov     rcx, rax; this
0x18005441c  call    ?IsEnabled_@TraceLoggingProvider@wil@@IEBA_NE_K@Z; wil::TraceLoggingProvider::IsEnabled_(uchar,unsigned __int64)
0x180054421  test    al, al
0x180054423  jz      short loc_180054436
0x180054425  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_234fc6f01c94939abb1aa6f0961130da_@@CA@XZ; _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_(void)
0x18005442c  call    ?get@?$static_lazy@VAppxCreateProcessExtensionsTelemetry@AppxCreateProcessExtensions@@@details@wil@@QEAAPEAVAppxCreateProcessExtensionsTelemetry@AppxCreateProcessExtensions@@P6AXXZ@Z; wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(void (*)(void))
0x180054431  call    ?PreCreationExtension_Start_@AppxCreateProcessExtensionsTelemetry@AppxCreateProcessExtensions@@QEAAXXZ; AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Start_(void)
0x180054436  mov     dword ptr [r14+4], 0C8h
0x18005443e  test    rsi, rsi
0x180054441  jz      loc_1800559DB
0x180054447  xor     eax, eax
0x180054449  mov     [rbp+370h+var_358], r12d
0x18005444d  mov     byte ptr [rbp+370h+var_3E0+4], al
0x180054450  lea     r9, [rbp+370h+var_368]
0x180054454  mov     byte ptr [rbp+370h+var_3E0+1], al
0x180054457  xorps   xmm0, xmm0
0x18005445a  mov     byte ptr [rbp+370h+var_3E0+5], al
0x18005445d  mov     r8, rbx
0x180054460  mov     byte ptr [rbp+370h+var_3E0+3], al
0x180054463  mov     rdx, rdi
0x180054466  mov     byte ptr [rbp+370h+var_3E0], al
0x180054469  mov     rcx, rsi; TokenHandle
0x18005446c  mov     byte ptr [rbp+370h+var_3E0+2], al
0x18005446f  lea     rax, [rbp+370h+var_3E0+2]
0x180054473  mov     [rsp+470h+var_420], rax; __int64
0x180054478  lea     rax, [rbp+370h+var_3E0]
0x18005447c  mov     [rsp+470h+var_428], rax; __int64
0x180054481  lea     rax, [rbp+370h+var_3E0+3]
0x180054485  mov     qword ptr [rsp+470h+var_430], rax; __int64
0x18005448a  lea     rax, [rbp+370h+var_3E0+5]
0x18005448e  mov     qword ptr [rsp+470h+var_438], rax; __int64
0x180054493  lea     rax, [rbp+370h+var_3E0+1]
0x180054497  mov     [rsp+470h+var_440], rax; __int64
0x18005449c  lea     rax, [rbp+370h+var_3E0+4]
0x1800544a0  mov     [rsp+470h+lpcbData], rax; __int64
0x1800544a5  lea     rax, [rbp+370h+P]
0x1800544a9  mov     [rsp+470h+ReturnLength], rax; int
0x1800544ae  movups  xmmword ptr [rbp+370h+var_368], xmm0
0x1800544b2  mov     [rbp+370h+var_3A8], r12d
0x1800544b6  movups  xmmword ptr [rbp+370h+P], xmm0
0x1800544ba  call    VerifyParametersAndGetEffectivePackageMoniker
0x1800544bf  mov     ebx, eax
0x1800544c1  test    eax, eax
0x1800544c3  js      loc_180056100
0x1800544c9  cmp     dword ptr [rbp+370h+var_368], r12d
0x1800544cd  jz      loc_1800561AE
0x1800544d3  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; void * ReservedForLocalUse::g_heap
0x1800544da  mov     rax, r12
0x1800544dd  mov     [rsp+470h+arg_10], r13
0x1800544e5  mov     [rbp+370h+Sid], r12
0x1800544e9  mov     [rbp+370h+var_3D0], rax
0x1800544ed  mov     [rbp+370h+var_398], rax
0x1800544f1  mov     [rbp+370h+var_344], r12d
0x1800544f5  mov     dword ptr [rbp+370h+var_348], r12d
0x1800544f9  mov     [rsp+470h+var_400], r12
0x1800544fe  mov     dword ptr [rbp+370h+var_378], r12d
0x180054502  mov     [rbp+370h+var_3F0], r12
0x180054506  mov     dword ptr [rbp+370h+var_378+4], r12d
0x18005450a  mov     [rsp+470h+hMem], r12
0x18005450f  mov     dword ptr [rbp+370h+var_370], r12d
0x180054513  mov     dword ptr [rbp+370h+var_340], r12d
0x180054517  test    rcx, rcx
0x18005451a  jnz     short loc_180054530
0x18005451c  mov     rcx, gs:60h
0x180054525  mov     rcx, [rcx+30h]; HeapHandle
0x180054529  mov     cs:?g_heap@ReservedForLocalUse@@3PEAXEA, rcx; void * ReservedForLocalUse::g_heap
0x180054530  xor     edx, edx; Flags
0x180054532  mov     r8d, 60h ; '`'; Size
0x180054538  call    cs:__imp_RtlAllocateHeap
0x18005453f  nop     dword ptr [rax+rax+00h]
0x180054544  mov     [rbp+370h+var_3C8], rax
0x180054548  mov     r13, rax
0x18005454b  test    rax, rax
0x18005454e  jz      loc_180055EE8
0x180054554  xor     edx, edx; Val
0x180054556  mov     r8d, 60h ; '`'; Size
0x18005455c  mov     rcx, rax; void *
0x18005455f  call    memset_0
0x180054564  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; void * ReservedForLocalUse::g_heap
0x18005456b  test    rcx, rcx
0x18005456e  jnz     short loc_180054584
0x180054570  mov     rcx, gs:60h
0x180054579  mov     rcx, [rcx+30h]; HeapHandle
0x18005457d  mov     cs:?g_heap@ReservedForLocalUse@@3PEAXEA, rcx; void * ReservedForLocalUse::g_heap
0x180054584  xor     edx, edx; Flags
0x180054586  mov     r8d, 18h; Size
0x18005458c  call    cs:__imp_RtlAllocateHeap
0x180054593  nop     dword ptr [rax+rax+00h]
0x180054598  mov     rbx, rax
0x18005459b  test    rax, rax
0x18005459e  jz      loc_1800565D6
0x1800545a4  mov     [rax], r12
0x1800545a7  mov     r14, [rbp+370h+var_368+8]
0x1800545ab  mov     [rax+10h], r12
0x1800545af  mov     [rax+8], r12
0x1800545b3  cmp     byte ptr [rbp+370h+var_3E0], r12b
0x1800545b7  jnz     loc_18005574A
0x1800545bd  test    r14, r14
0x1800545c0  jz      loc_180054D2B
0x1800545c6  cmp     [r14], r12w
0x1800545ca  jz      loc_180054D2B
0x1800545d0  mov     [rbp+370h+var_334], r12d
0x1800545d4  lea     rax, [rbp+370h+var_334]
0x1800545d8  test    rsi, rsi
0x1800545db  mov     [rsp+470h+ReturnLength], rax; int
0x1800545e0  mov     r12d, 1
0x1800545e6  lea     r8, [rbp+370h+TokenInformation]; TokenInformation
0x1800545ed  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x1800545f4  mov     edx, r12d; TokenInformationClass
0x1800545f7  cmovnz  rcx, rsi; TokenHandle
0x1800545fb  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180054601  call    cs:__imp_NtQueryInformationToken
0x180054608  nop     dword ptr [rax+rax+00h]
0x18005460d  test    eax, eax
0x18005460f  js      loc_180054BE5
0x180054615  mov     rdi, [rbp+370h+TokenInformation]
0x18005461c  lea     rdx, [rbp+370h+DestinationSid]; DestinationSid
0x180054623  mov     r8, rdi; SourceSid
0x180054626  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18005462b  call    cs:__imp_RtlCopySid
0x180054632  nop     dword ptr [rax+rax+00h]
0x180054637  test    eax, eax
0x180054639  js      loc_180054BE5
0x18005463f  mov     rcx, rdi; Sid
0x180054642  call    cs:__imp_RtlLengthSid
0x180054649  nop     dword ptr [rax+rax+00h]
0x18005464e  lea     r8, [rbp+370h+var_344]
0x180054652  mov     rdx, r14
0x180054655  lea     rcx, [rbp+370h+DestinationSid]
0x18005465c  call    cs:__imp_SRGetPackageStatusForUserSid
0x180054663  nop     dword ptr [rax+rax+00h]
0x180054668  mov     r15d, eax
0x18005466b  and     eax, 1FFF0000h
0x180054670  cmp     eax, 70000h
0x180054675  jz      loc_180056D57
0x18005467b  xor     ecx, ecx; void *
0x18005467d  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180054682  test    r15d, r15d
0x180054685  jnz     loc_180054D31
0x18005468b  xor     r15d, r15d
0x18005468e  mov     [rbp+370h+var_270], r12b
0x180054695  lea     rax, [rbp+370h+var_3D8]
0x180054699  mov     [rbp+370h+var_3D8], r15
0x18005469d  lea     rdx, [rbp+370h+var_278]
0x1800546a4  mov     [rbp+370h+var_280], rax
0x1800546ab  xor     ecx, ecx
0x1800546ad  mov     [rbp+370h+var_278], r15
0x1800546b4  call    cs:__imp_SRCacheManager_Open
0x1800546bb  nop     dword ptr [rax+rax+00h]
0x1800546c0  mov     edi, eax
0x1800546c2  cmp     [rbp+370h+var_270], r15b
0x1800546c9  jz      short loc_1800546F3
0x1800546cb  mov     rdx, [rbp+370h+var_280]
0x1800546d2  mov     rcx, [rbp+370h+var_278]
0x1800546d9  mov     r8, [rdx]
0x1800546dc  mov     [rdx], rcx
0x1800546df  test    r8, r8
0x1800546e2  jz      short loc_1800546F3
0x1800546e4  mov     rcx, r8
0x1800546e7  call    cs:__imp_SRCacheManager_Close
0x1800546ee  nop     dword ptr [rax+rax+00h]
0x1800546f3  test    edi, edi
0x1800546f5  jns     loc_1800547E5
0x1800546fb  mov     rcx, [rbp+378h]; this
0x180054702  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180054709  mov     r9d, edi; char *
0x18005470c  mov     edx, 0A5h; void *
0x180054711  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054716  mov     rcx, [rbp+378h]; this
0x18005471d  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\processcreatio"...
0x180054724  mov     r9d, edi; char *
0x180054727  mov     edx, 314h; void *
0x18005472c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054731  xor     edx, edx
0x180054733  lea     rcx, [rbp+370h+var_3D8]
0x180054737  call    ?reset@?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheManager@@@Z; wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(SRCacheManager *)
0x18005473c  mov     rcx, rbx; void *
0x18005473f  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180054744  mov     rcx, r13; void *
0x180054747  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18005474c  mov     rcx, [rsp+470h+hMem]; hMem
0x180054751  call    LocalFree
0x180054756  mov     rcx, [rbp+370h+var_3F0]; hMem
0x18005475a  call    LocalFree
0x18005475f  mov     rcx, [rsp+470h+var_400]; hMem
0x180054764  call    LocalFree
0x180054769  xor     ecx, ecx; void *
0x18005476b  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180054770  xor     ecx, ecx; void *
0x180054772  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180054777  mov     rcx, [rbp+370h+Sid]; Sid
0x18005477b  test    rcx, rcx
0x18005477e  jz      short loc_18005478C
0x180054780  call    cs:__imp_RtlFreeSid
0x180054787  nop     dword ptr [rax+rax+00h]
0x18005478c  xor     ecx, ecx; void *
0x18005478e  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180054793  mov     rcx, [rbp+370h+P+8]; void *
0x180054797  test    rcx, rcx
0x18005479a  jz      short loc_1800547A1
0x18005479c  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800547a1  test    r14, r14
0x1800547a4  jz      short loc_1800547AE
0x1800547a6  mov     rcx, r14; void *
0x1800547a9  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800547ae  call    ?IsEnabled@AppxCreateProcessExtensionsTelemetry@AppxCreateProcessExtensions@@SA_NE_K@Z; AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800547b3  test    al, al
0x1800547b5  jz      short loc_1800547C8
0x1800547b7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_234fc6f01c94939abb1aa6f0961130da_@@CA@XZ; _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_(void)
0x1800547be  call    ?get@?$static_lazy@VAppxCreateProcessExtensionsTelemetry@AppxCreateProcessExtensions@@@details@wil@@QEAAPEAVAppxCreateProcessExtensionsTelemetry@AppxCreateProcessExtensions@@P6AXXZ@Z; wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(void (*)(void))
0x1800547c3  call    ?PreCreationExtension_Stop_@AppxCreateProcessExtensionsTelemetry@AppxCreateProcessExtensions@@QEAAXXZ; AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(void)
0x1800547c8  mov     rcx, [rsp+470h+hObject]; hObject
0x1800547cd  lea     rax, [rcx-1]
0x1800547d1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800547d5  ja      loc_180054D1A
0x1800547db  call    CloseHandle
0x1800547e0  jmp     loc_180054D1A
0x1800547e5  xorps   xmm0, xmm0
0x1800547e8  mov     [rbp+370h+var_300], r15
0x1800547ec  xor     dil, dil
0x1800547ef  movdqa  [rbp+370h+var_310], xmm0
0x1800547f4  lea     r8, [rbp+370h+var_2A0]; __int64 *
0x1800547fb  movdqa  [rbp+370h+var_2D0], xmm0
0x180054803  mov     rdx, r14; unsigned __int16 *
0x180054806  mov     [rsp+470h+var_410], dil
0x18005480b  lea     rcx, [rbp+370h+var_3D8]; struct StateRepository::Cache::Manager_NoThrow *
0x18005480f  mov     [rbp+370h+var_2F8], r15
0x180054813  mov     [rbp+370h+var_2F0], r15
0x18005481a  mov     [rbp+370h+var_2E8], r15
0x180054821  mov     [rbp+370h+var_2E0], r15
0x180054828  mov     [rbp+370h+var_2D8], r15
0x18005482f  mov     [rbp+370h+var_2C0], r15d
0x180054836  mov     [rbp+370h+var_2B8], r15
0x18005483d  mov     [rbp+370h+var_2B0], r15
0x180054844  mov     [rbp+370h+var_2A0], r15
0x18005484b  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180054850  mov     esi, eax
0x180054852  test    eax, eax
0x180054854  js      loc_180054D87
0x18005485a  mov     rdx, [rbp+370h+var_2A0]
0x180054861  test    rdx, rdx
0x180054864  jz      short loc_180054892
0x180054866  lea     rax, [rsp+470h+var_410]
0x18005486b  mov     r8d, 80Ah
0x180054871  lea     r9, [rbp+370h+var_310]
0x180054875  mov     [rsp+470h+ReturnLength], rax; int
0x18005487a  lea     rcx, [rbp+370h+var_3D8]
0x18005487e  call    ?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180054883  mov     esi, eax
0x180054885  test    eax, eax
0x180054887  js      loc_180056D60
0x18005488d  movzx   edi, [rsp+470h+var_410]
0x180054892  test    dil, dil
0x180054895  jz      loc_180055B83
0x18005489b  xorps   xmm0, xmm0
0x18005489e  mov     [rsp+470h+var_410], r15b
0x1800548a3  xor     edx, edx; Val
0x1800548a5  movdqa  [rbp+370h+var_250], xmm0
0x1800548ad  mov     r8d, 44h ; 'D'; Size
0x1800548b3  lea     rcx, [rbp+370h+var_240]; void *
0x1800548ba  call    memset_0
0x1800548bf  mov     rsi, [rbp+370h+var_300]
0x1800548c3  mov     [rbp+370h+SourceSid], r15
0x1800548ca  mov     [rbp+370h+var_1F0], r15
0x1800548d1  test    rsi, rsi
0x1800548d4  jz      loc_180054D5D
0x1800548da  lea     r9, [rsp+470h+var_410]; bool *
0x1800548df  mov     [rbp+370h+var_390], r15
0x1800548e3  lea     r8, [rbp+370h+var_390]; struct StateRepository::Cache::Context_NoThrow *
0x1800548e7  mov     rdx, rsi; __int64
0x1800548ea  lea     rcx, [rbp+370h+var_3D8]; struct StateRepository::Cache::Manager_NoThrow *
0x1800548ee  call    ?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x1800548f3  mov     edi, eax
0x1800548f5  test    eax, eax
  ... truncated ...
```
