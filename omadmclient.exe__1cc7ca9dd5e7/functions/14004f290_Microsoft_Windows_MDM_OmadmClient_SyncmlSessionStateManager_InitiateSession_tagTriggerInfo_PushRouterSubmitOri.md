# Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager::InitiateSession(tagTriggerInfo *,PushRouterSubmitOrigin &,Microsoft::Windows::MDM::OmadmClient::SyncmlSession *,Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,void (*)(void *,uchar),void (*)(void *,uchar),long (*)(void *,int))

- ea: `0x14004f290`
- end: `0x140051b85`
- name: `?InitiateSession@SyncmlSessionStateManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEAUtagTriggerInfo@@AEAW4PushRouterSubmitOrigin@@PEAVSyncmlSession@2345@AEAVSyncmlSessionState@2345@P6AXPEAXE@Z5P6AJ4H@Z@Z`
- size: `10485`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager *__hidden this, struct tagTriggerInfo *, enum PushRouterSubmitOrigin *, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSession *, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, void (*)(void *, unsigned __int8), void (*)(void *, unsigned __int8), int (*)(void *, int))`
- caller_count: `0`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000bf50`
- `0x14000d71c`
- `0x14000d778`
- `0x14000e3e4`
- `0x14000e610`
- `0x14000eb54`
- `0x14000ff64`
- `0x140010f18`
- `0x140013404`
- `0x1400134a4`
- `0x14001391c`
- `0x140015970`
- `0x1400197a4`
- `0x14002c024`
- `0x14004e9b0`
- `0x14004ef28`
- `0x14004efcc`
- `0x14004f290`
- `0x140051ca0`
- `0x1400552f8`
- `0x1400556e8`
- `0x140055948`
- `0x14005599c`
- `0x140055a68`
- `0x140055ba8`
- `0x140055cdc`
- `0x140065ed4`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051436`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400507d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050de3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400515a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400515f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400507d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050de3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400515a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400515f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004f9b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400507fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005087b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140050d7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140050e02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140050e6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005106d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140051156`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400515cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005161a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004f9b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400507fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005087b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140050d7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140050e02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140050e6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005106d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140051156`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400515cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005161a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f9a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400507ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005086d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050d0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050d6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050df4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050e5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050f45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005105f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140051148`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400515bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005160c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005187a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f9a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400507ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005086d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050d0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050d6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050df4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050e5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140050f45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005105f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140051148`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400515bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005160c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005187a`
- `coredpus!__imp_GetAuthType` at `0x1400501a8`
- `coredpus!__imp_GetAuthType` at `0x1400501a8`
- `DMCmnUtils!CopyString` at `0x140050829`
- `DMCmnUtils!CopyString` at `0x140050d9d`
- `DMCmnUtils!CopyString` at `0x140050e1e`
- `DMCmnUtils!CopyString` at `0x140050e88`
- `DMCmnUtils!CopyString` at `0x140051094`
- `DMCmnUtils!CopyString` at `0x140051641`
- `DMCmnUtils!CopyString` at `0x1400518db`
- `DMCmnUtils!CopyString` at `0x140051914`
- `DMCmnUtils!CopyString` at `0x140050829`
- `DMCmnUtils!CopyString` at `0x140050d9d`
- `DMCmnUtils!CopyString` at `0x140050e1e`
- `DMCmnUtils!CopyString` at `0x140050e88`
- `DMCmnUtils!CopyString` at `0x140051094`
- `DMCmnUtils!CopyString` at `0x140051641`
- `DMCmnUtils!CopyString` at `0x1400518db`
- `DMCmnUtils!CopyString` at `0x140051914`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400513f0`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400513f0`
- `DMCmnUtils!InvStrCmpIW` at `0x14005009e`
- `DMCmnUtils!InvStrCmpIW` at `0x1400504a5`
- `DMCmnUtils!InvStrCmpIW` at `0x140050535`
- `DMCmnUtils!InvStrCmpIW` at `0x14005009e`
- `DMCmnUtils!InvStrCmpIW` at `0x1400504a5`
- `DMCmnUtils!InvStrCmpIW` at `0x140050535`
- `DMCmnUtils!InvStrCmpW` at `0x14004facc`
- `DMCmnUtils!InvStrCmpW` at `0x14004facc`
- `omadmapi!__imp_OmaDmFindAppAuthIndex` at `0x14004ffc6`
- `omadmapi!__imp_OmaDmFindAppAuthIndex` at `0x14005002d`
- `omadmapi!__imp_OmaDmFindAppAuthIndex` at `0x14004ffc6`
- `omadmapi!__imp_OmaDmFindAppAuthIndex` at `0x14005002d`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x14004fd64`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x1400500cf`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x1400502a7`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x1400505bf`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x1400517fb`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x1400519cc`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x140051a19`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x14004fd64`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x1400500cf`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x1400502a7`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x1400505bf`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x1400517fb`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x1400519cc`
- `omadmapi!__imp_OmaDmIsNodePresent` at `0x140051a19`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x14004fd84`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x1400502c7`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x14005038d`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x1400505df`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x1400519e9`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x14004fd84`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x1400502c7`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x14005038d`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x1400505df`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x1400519e9`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140050104`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x1400502fc`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x14005042c`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140050614`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x14005069c`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140050ff5`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x1400510eb`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x1400512d6`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x14005182d`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140051954`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140050104`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x1400502fc`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x14005042c`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140050614`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x14005069c`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140050ff5`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x1400510eb`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x1400512d6`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x14005182d`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140051954`
- `omadmapi!__imp_OmaDmSetNodeValuePresence` at `0x14004f90a`
- `omadmapi!__imp_OmaDmSetNodeValuePresence` at `0x14004f90a`

## string_xrefs

- `0x140050943`: `OMADM::TargetedUserSID`
- `0x140050a5f`: `OMADM::TargetedUserSID`
- `0x140050a7c`: `OMADM::TargetedUserSID`
- `0x14005190d`: `application/vnd.syncml.dm+xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager::InitiateSession(
        Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager *this,
        struct tagTriggerInfo *a2,
        enum PushRouterSubmitOrigin *a3,
        struct Microsoft::Windows::MDM::OmadmClient::SyncmlSession *a4,
        struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *a5,
        void (*a6)(void *, unsigned __int8),
        void (*a7)(void *, unsigned __int8),
        int (*a8)(void *, int))
{
  struct COmaDmLogger *Logger; // rax
  struct COmaDmLogger *v9; // rax
  struct tagTriggerInfo *v10; // rax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rax
  int *v24; // rcx
  struct COmaDmLogger *v25; // rax
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  int v29; // ecx
  int v30; // eax
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // eax
  __int64 v36; // r8
  __int64 v37; // rcx
  int v38; // eax
  __int64 v39; // rcx
  int v40; // eax
  __int64 v41; // rcx
  _QWORD *v42; // rcx
  DWORD LastError; // edi
  int v44; // eax
  __int64 v45; // rcx
  int v46; // eax
  __int64 v47; // rcx
  int v48; // eax
  __int64 v49; // rcx
  __int64 v50; // rax
  struct COmaDmLogger *v51; // rax
  __int64 v52; // rcx
  __int64 v53; // rax
  int v54; // eax
  __int64 v55; // rcx
  int v56; // eax
  __int64 v57; // r8
  __int64 v58; // rcx
  int v59; // eax
  __int64 v60; // rcx
  int v61; // eax
  __int64 v62; // rcx
  int v63; // eax
  __int64 v64; // rcx
  int AppAuthIndex; // eax
  __int64 v66; // rcx
  int v67; // eax
  const unsigned __int16 *v68; // rcx
  __int64 v69; // rcx
  unsigned int *v70; // rax
  int ValueFromStruct; // eax
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // r9
  int AuthType; // eax
  __int64 v76; // rcx
  __int64 v77; // r8
  int v78; // eax
  __int64 v79; // rcx
  int v80; // eax
  __int64 v81; // rcx
  int v82; // eax
  __int64 v83; // rcx
  int v84; // eax
  __int64 v85; // rcx
  int v86; // eax
  __int64 v87; // rcx
  int v88; // eax
  __int64 v89; // rcx
  int v90; // eax
  __int64 v91; // rcx
  int v92; // eax
  __int64 v93; // rcx
  unsigned __int16 **v94; // rcx
  DWORD v95; // edi
  unsigned int TargetUserSid; // eax
  Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager *v97; // rcx
  DWORD v98; // edi
  int v99; // ecx
  const wchar_t *v100; // rax
  char *v101; // rcx
  __int64 v102; // r8
  __int64 v103; // rdx
  __int64 v104; // rax
  __int64 v105; // rdx
  __int64 v106; // rax
  _WORD *v107; // rax
  COmaDmLogger *v108; // rax
  __int64 v109; // rcx
  __int64 v110; // rax
  char *v111; // rdi
  int v112; // r9d
  __int64 v113; // rdx
  COmaDmLogger *v114; // rax
  __int64 v115; // r12
  __int64 (__fastcall *v116)(__int64, char *, _QWORD, _QWORD); // r14
  struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *v117; // r15
  int v118; // eax
  int v119; // edi
  __int64 v120; // rcx
  void *v121; // r14
  DWORD v122; // edi
  __int64 v123; // rdx
  void *v124; // r14
  DWORD v125; // edi
  void *v126; // r14
  DWORD v127; // edi
  __int64 v128; // r10
  const unsigned __int16 **v129; // rcx
  unsigned __int16 **v130; // rax
  DWORD v131; // edi
  __int64 v132; // rdx
  _QWORD *v133; // rdx
  _QWORD *v134; // rcx
  DWORD v135; // edi
  __int64 v136; // rax
  __int64 v137; // r9
  __int64 v138; // r8
  unsigned __int64 v139; // rdx
  _QWORD *v140; // r8
  int v141; // eax
  HKEY v142; // r9
  unsigned __int64 v143; // rcx
  struct COmaDmLogger *v144; // rax
  int *v145; // r8
  FirstSync **v146; // rdi
  _BOOL8 v147; // rcx
  int *v148; // r9
  int *v149; // r8
  int *v150; // r9
  int FirstSyncKey; // eax
  HKEY v152; // rdi
  int *v153; // r8
  unsigned int v154; // r8d
  unsigned __int16 **v155; // rax
  HKEY v156; // rcx
  const unsigned __int16 **v157; // r9
  DWORD v158; // edi
  unsigned int v159; // edx
  const unsigned __int16 *v160; // rcx
  DWORD v161; // edi
  int v162; // ecx
  __int64 v163; // rax
  char *v164; // rdi
  int v165; // edx
  __int64 v166; // rax
  int v167; // edx
  __int64 v168; // rax
  int v169; // edi
  unsigned __int16 **v170; // rax
  unsigned __int16 **v171; // rax
  __int64 v172; // rcx
  __int64 v173; // rax
  __int64 v174; // rcx
  __int64 v175; // rcx
  __int64 v176; // rcx
  __int64 v177; // rcx
  unsigned __int16 *v178; // [rsp+20h] [rbp-178h]
  unsigned __int16 *v179; // [rsp+20h] [rbp-178h]
  int v180; // [rsp+20h] [rbp-178h]
  unsigned int ManagementServerAddressList; // [rsp+50h] [rbp-148h] BYREF
  char v182; // [rsp+54h] [rbp-144h]
  unsigned __int16 v183[4]; // [rsp+58h] [rbp-140h] BYREF
  _QWORD v184[3]; // [rsp+60h] [rbp-138h] BYREF
  int v185; // [rsp+78h] [rbp-120h]
  unsigned int *v186; // [rsp+80h] [rbp-118h]
  HLOCAL v187; // [rsp+88h] [rbp-110h] BYREF
  unsigned __int16 v188[4]; // [rsp+90h] [rbp-108h] BYREF
  unsigned __int16 v189[4]; // [rsp+98h] [rbp-100h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp-F8h] BYREF
  enum PushRouterSubmitOrigin *v191; // [rsp+A8h] [rbp-F0h]
  void (*v192)(void *, unsigned __int8); // [rsp+B0h] [rbp-E8h] BYREF
  char *v193; // [rsp+B8h] [rbp-E0h]
  unsigned __int16 v194[4]; // [rsp+C0h] [rbp-D8h] BYREF
  unsigned __int16 v195[4]; // [rsp+C8h] [rbp-D0h] BYREF
  HLOCAL v196; // [rsp+D0h] [rbp-C8h] BYREF
  const unsigned __int16 **v197; // [rsp+D8h] [rbp-C0h]
  struct tagTriggerInfo *v198; // [rsp+E0h] [rbp-B8h]
  HLOCAL hMem; // [rsp+E8h] [rbp-B0h]
  struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *v200; // [rsp+F0h] [rbp-A8h]
  int v201; // [rsp+F8h] [rbp-A0h] BYREF
  const unsigned __int16 **v202; // [rsp+100h] [rbp-98h] BYREF
  _QWORD *v203; // [rsp+108h] [rbp-90h] BYREF
  const unsigned __int16 **v204; // [rsp+110h] [rbp-88h] BYREF
  __int64 v205; // [rsp+118h] [rbp-80h] BYREF
  _QWORD *v206; // [rsp+120h] [rbp-78h] BYREF
  unsigned int *v207; // [rsp+128h] [rbp-70h]
  unsigned int *v208; // [rsp+130h] [rbp-68h] BYREF
  char v209; // [rsp+138h] [rbp-60h]
  unsigned __int16 *v210; // [rsp+140h] [rbp-58h]
  __int64 v211; // [rsp+148h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  *(_QWORD *)v195 = a4;
  *(_QWORD *)v194 = a3;
  v198 = a2;
  v191 = a3;
  hMem = a4;
  v200 = a5;
  v192 = a7;
  hKey = (HKEY)a8;
  ManagementServerAddressList = 0;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    *(_DWORD *)v183 = 3;
    v210 = v183;
    v211 = 4;
    v178 = (unsigned __int16 *)&v208;
    McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, OmaDmClientFunctionEntryPointEvent, a3, 2);
  }
  v208 = &ManagementServerAddressList;
  v182 = 1;
  v209 = 1;
  Logger = COmaDmLogger::GetLogger();
  Microsoft::Windows::TelemetryLogger::LogFunctionEntryMeasure(Logger, 1, "InitiateSession", 0, v178);
  v9 = COmaDmLogger::GetLogger();
  v184[0] = 0;
  v184[1] = "InitiateSession";
  v184[2] = v9;
  v185 = 1;
  v186 = &ManagementServerAddressList;
  v10 = v198;
  if ( !v198 )
  {
    v11 = -805306129;
LABEL_5:
    ManagementServerAddressList = v11;
LABEL_6:
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v12, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
    return v11;
  }
  v197 = (const unsigned __int16 **)((char *)v198 + 40);
  if ( *((_QWORD *)v198 + 5) )
  {
    v14 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 96LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
    if ( !(*(unsigned int (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v14 + 24LL))(v14, *v197) )
    {
      LODWORD(v184[0]) = 9811;
      v11 = -2102788084;
LABEL_12:
      HIDWORD(v184[0]) = v11;
      goto LABEL_6;
    }
    v10 = v198;
  }
  if ( !*(_QWORD *)v195 )
  {
    v11 = -805306127;
    goto LABEL_5;
  }
  if ( !a6 )
  {
    v11 = -805306125;
    goto LABEL_5;
  }
  if ( !hKey )
  {
    v11 = -805306124;
    goto LABEL_5;
  }
  if ( !v192 )
  {
    v11 = -805306123;
    goto LABEL_5;
  }
  v193 = (char *)a5 + 40;
  *((_QWORD *)a5 + 5) = v10;
  *((_DWORD *)a5 + 399) = *((_DWORD *)v10 + 1);
  v15 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 88LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
  v198 = (struct tagTriggerInfo *)v15;
  if ( !*((_QWORD *)a5 + 85) )
  {
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, char *))(*(_QWORD *)v15 + 8LL))(
            v15,
            0,
            0,
            0,
            0,
            (char *)a5 + 680);
    *(_DWORD *)v183 = v16;
    ManagementServerAddressList = v16;
    if ( v16 < 0 )
    {
      LODWORD(v184[0]) = 9017;
      HIDWORD(v184[0]) = v16;
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v17, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
      return *(unsigned int *)v183;
    }
  }
  *(_QWORD *)v189 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 152LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
  v18 = (*(__int64 (__fastcall **)(_QWORD, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *))(**(_QWORD **)v189 + 8LL))(
          *(_QWORD *)v189,
          a5);
  *(_DWORD *)v183 = v18;
  ManagementServerAddressList = v18;
  if ( v18 < 0 )
  {
    LODWORD(v184[0]) = 9060;
    HIDWORD(v184[0]) = v18;
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v19, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
    return *(unsigned int *)v183;
  }
  v20 = **(_QWORD **)v189;
  if ( *(_BYTE *)(*(_QWORD *)v193 + 9LL) )
  {
    v27 = (*(__int64 (__fastcall **)(_QWORD, char *))(v20 + 40))(*(_QWORD *)v189, (char *)a5 + 848);
    *(_DWORD *)v183 = v27;
    ManagementServerAddressList = v27;
    if ( v27 < 0 )
    {
      LODWORD(v184[0]) = 9037;
      HIDWORD(v184[0]) = v27;
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v28, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
      return *(unsigned int *)v183;
    }
    v24 = *(int **)v194;
  }
  else
  {
    v21 = (*(__int64 (__fastcall **)(_QWORD, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *))(v20 + 16))(
            *(_QWORD *)v189,
            a5);
    *(_DWORD *)v183 = v21;
    ManagementServerAddressList = v21;
    if ( v21 < 0 )
    {
      LODWORD(v184[0]) = 9039;
      HIDWORD(v184[0]) = v21;
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v22, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
      return *(unsigned int *)v183;
    }
    v23 = *((_QWORD *)a5 + 118);
    if ( !v23 )
    {
      v25 = COmaDmLogger::GetLogger();
      Microsoft::Windows::TelemetryLogger::LogMeasure(v25, 0, 3009, 0);
      ManagementServerAddressList = 1;
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v26, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
      return 1;
    }
    v24 = *(int **)v194;
    **(_DWORD **)v194 = *(_DWORD *)(v23 + 40);
  }
  v29 = *v24;
  if ( v29 <= 35 )
  {
    if ( v29 == 35 )
    {
LABEL_54:
      v30 = 5;
      goto LABEL_67;
    }
    if ( v29 != 3 )
    {
      switch ( v29 )
      {
        case 7:
          v30 = 3;
          goto LABEL_67;
        case 9:
          v30 = 6;
          goto LABEL_67;
        case 11:
          v30 = 8;
          goto LABEL_67;
      }
      if ( v29 != 20 )
      {
        if ( v29 == 24 )
          goto LABEL_54;
        goto LABEL_63;
      }
      goto LABEL_66;
    }
LABEL_64:
    v30 = 2;
    goto LABEL_67;
  }
  v31 = v29 - 36;
  if ( v31 )
  {
    v32 = v31 - 1;
    if ( v32 )
    {
      v33 = v32 - 5;
      if ( !v33 || (v34 = v33 - 1) == 0 )
      {
        v30 = 4;
        goto LABEL_67;
      }
      if ( (unsigned int)(v34 - 8) >= 2 )
      {
LABEL_63:
        v30 = 7;
        goto LABEL_67;
      }
      goto LABEL_64;
    }
  }
LABEL_66:
  v30 = 1;
LABEL_67:
  *((_DWORD *)a5 + 532) = v30;
  v35 = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::Close((struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *)((char *)a5 + 1496));
  *(_DWORD *)v188 = v35;
  ManagementServerAddressList = v35;
  v36 = *(_QWORD *)v195;
  if ( v35 < 0 )
  {
    LODWORD(v184[0]) = 9054;
    HIDWORD(v184[0]) = v35;
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v37, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
    return *(unsigned int *)v188;
  }
  *((_QWORD *)a5 + 114) = a6;
  *((_QWORD *)a5 + 115) = v36;
  v38 = (*(__int64 (__fastcall **)(_QWORD, char *, char *))(**(_QWORD **)v189 + 48LL))(
          *(_QWORD *)v189,
          (char *)a5 + 848,
          (char *)a5 + 976);
  *(_DWORD *)v183 = v38;
  ManagementServerAddressList = v38;
  if ( v38 < 0 )
  {
    LODWORD(v184[0]) = 9074;
    HIDWORD(v184[0]) = v38;
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v39, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
    return *(unsigned int *)v183;
  }
  *(_QWORD *)v189 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 144LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
  *((_DWORD *)a5 + 12) = 512;
  v40 = OmaDmSetNodeValuePresence(34, (char *)a5 + 48);
  *(_DWORD *)v183 = v40;
  ManagementServerAddressList = v40;
  if ( v40 < 0 )
  {
    LODWORD(v184[0]) = 9052;
    HIDWORD(v184[0]) = v40;
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v41, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
    return *(unsigned int *)v183;
  }
  *(_QWORD *)v183 = *(_QWORD *)(**(_QWORD **)v189 + 32LL);
  v42 = (_QWORD *)((char *)a5 + 560);
  v196 = (char *)a5 + 560;
  hMem = (HLOCAL)*((_QWORD *)a5 + 70);
  if ( hMem )
  {
    LastError = GetLastError();
    LocalFree(hMem);
    SetLastError(LastError);
    v42 = (_QWORD *)((char *)a5 + 560);
  }
  *v42 = 0;
  v44 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD *))v183)(
          *(_QWORD *)v189,
          *(_QWORD *)(*(_QWORD *)v193 + 16LL),
          *(unsigned int *)(*(_QWORD *)v193 + 24LL),
          v42);
  *(_DWORD *)v183 = v44;
  ManagementServerAddressList = v44;
  if ( v44 < 0 )
  {
    LODWORD(v184[0]) = 9051;
    HIDWORD(v184[0]) = v44;
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v45, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
    return *(unsigned int *)v183;
  }
  v46 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *))(**(_QWORD **)v189 + 40LL))(
          *(_QWORD *)v189,
          *(_QWORD *)(*(_QWORD *)v193 + 16LL),
          *(unsigned int *)(*(_QWORD *)v193 + 24LL),
          (char *)a5 + 48);
  *(_DWORD *)v183 = v46;
  ManagementServerAddressList = v46;
  if ( v46 < 0 )
  {
    LODWORD(v184[0]) = 9048;
    HIDWORD(v184[0]) = v46;
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v47, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
    return *(unsigned int *)v183;
  }
  if ( !*((_QWORD *)a5 + 9) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *((_DWORD *)a5 + 148) = InvStrCmpW(*((const unsigned __int16 **)a5 + 9), L"sprint") == 0;
  (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *, const unsigned __int16 *, char *))(**(_QWORD **)v189 + 72LL))(
    *(_QWORD *)v189,
    -2147483646,
    L"Software\\Microsoft\\Provisioning\\CSPs",
    L"revision_number",
    (char *)a5 + 2120);
  *(_QWORD *)v189 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 208LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
  (*(void (__fastcall **)(_QWORD, _QWORD, char *))(**(_QWORD **)v189 + 408LL))(
    *(_QWORD *)v189,
    *((_QWORD *)a5 + 70),
    (char *)a5 + 2124);
  v207 = (unsigned int *)((char *)a5 + 764);
  v48 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, char *))(**(_QWORD **)v189 + 24LL))(
          *(_QWORD *)v189,
          *((_QWORD *)a5 + 70),
          1,
          (char *)a5 + 764);
  *(_DWORD *)v183 = v48;
  ManagementServerAddressList = v48;
  if ( v48 < 0 )
  {
    LODWORD(v184[0]) = 9027;
    HIDWORD(v184[0]) = v48;
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v49, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
    return *(unsigned int *)v183;
  }
  if ( **(_DWORD **)v194 == 3 || (unsigned int)(**(_DWORD **)v194 - 51) <= 1 )
  {
    v50 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 168LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
    ManagementServerAddressList = (*(__int64 (__fastcall **)(__int64, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *))(*(_QWORD *)v50 + 8LL))(
                                    v50,
                                    a5);
    if ( *((_BYTE *)a5 + 2088) )
    {
      v51 = COmaDmLogger::GetLogger();
      Microsoft::Windows::TelemetryLogger::LogMeasure(v51, 1, 3, 0);
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v52, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
      return 0;
    }
  }
  v201 = 0;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int *))(**(_QWORD **)v189 + 344LL))(
         *(_QWORD *)v189,
         *((_QWORD *)a5 + 70),
         *((unsigned int *)a5 + 112),
         *((_QWORD *)a5 + 53),
         &v201) >= 0
    && v201 == 1 )
  {
    v11 = -2147022965;
    ManagementServerAddressList = -2147022965;
    LODWORD(v184[0]) = 9079;
    goto LABEL_12;
  }
  v53 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 136LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
  v54 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v53 + 32LL))(
          v53,
          *(_QWORD *)(*(_QWORD *)v193 + 16LL),
          *(unsigned int *)(*(_QWORD *)v193 + 24LL));
  *(_DWORD *)v183 = v54;
  ManagementServerAddressList = v54;
  if ( v54 < 0 )
  {
    LODWORD(v184[0]) = 9073;
    HIDWORD(v184[0]) = v54;
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v55, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
    return *(unsigned int *)v183;
  }
  if ( (unsigned int)OmaDmIsNodePresent(34, (char *)a5 + 48)
    && (unsigned int)OmaDmIsNodeValuePresent(34, (char *)a5 + 48) )
  {
    *(_DWORD *)v188 = 0;
    v56 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)v189 + 16LL))(*(_QWORD *)v189, v188);
    *(_DWORD *)v183 = v56;
    ManagementServerAddressList = v56;
    if ( v56 < 0 )
    {
      LODWORD(v184[0]) = 9038;
      HIDWORD(v184[0]) = v56;
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v58, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
      return *(unsigned int *)v183;
    }
    if ( *(_DWORD *)v188 )
    {
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, SessionAbortedOnRoamingEvent, v57, 1);
      v11 = -2102657020;
      goto LABEL_5;
    }
    v59 = (*(__int64 (__fastcall **)(struct tagTriggerInfo *, _QWORD, _QWORD, _QWORD, _QWORD, char *))(*(_QWORD *)v198 + 8LL))(
            v198,
            0,
            0,
            0,
            0,
            (char *)a5 + 696);
    *(_DWORD *)v183 = v59;
    ManagementServerAddressList = v59;
    if ( v59 < 0 )
    {
      LODWORD(v184[0]) = 9019;
      HIDWORD(v184[0]) = v59;
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v60, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
      return *(unsigned int *)v183;
    }
    v61 = (*(__int64 (__fastcall **)(struct tagTriggerInfo *, char *, _QWORD, void (*)(void *, unsigned __int8), _QWORD, int))(*(_QWORD *)v198 + 72LL))(
            v198,
            (char *)a5 + 688,
            *((_QWORD *)a5 + 87),
            v192,
            *(_QWORD *)v195,
            -1);
    *(_DWORD *)v183 = v61;
    ManagementServerAddressList = v61;
    if ( v61 < 0 )
    {
      LODWORD(v184[0]) = 9059;
      HIDWORD(v184[0]) = v61;
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v62, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
      return *(unsigned int *)v183;
    }
    v63 = (*(__int64 (__fastcall **)(struct tagTriggerInfo *, _QWORD, char *))(*(_QWORD *)v198 + 80LL))(
            v198,
            *((_QWORD *)a5 + 87),
            (char *)a5 + 704);
    *(_DWORD *)v183 = v63;
    ManagementServerAddressList = v63;
    if ( v63 < 0 )
    {
      LODWORD(v184[0]) = 9058;
      HIDWORD(v184[0]) = v63;
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v64, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
      return *(unsigned int *)v183;
    }
  }
  AppAuthIndex = OmaDmFindAppAuthIndex(L"CLCRED", (char *)a5 + 48, (char *)a5 + 624);
  *(_DWORD *)v183 = AppAuthIndex;
  ManagementServerAddressList = AppAuthIndex;
  if ( AppAuthIndex < 0 )
  {
    LODWORD(v184[0]) = 9006;
    HIDWORD(v184[0]) = AppAuthIndex;
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v66, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
    return *(unsigned int *)v183;
  }
  v67 = OmaDmFindAppAuthIndex(L"SRVCRED", (char *)a5 + 48, (char *)a5 + 628);
  *(_DWORD *)v183 = v67;
  ManagementServerAddressList = v67;
  if ( v67 < 0 )
  {
    LODWORD(v184[0]) = 9062;
    HIDWORD(v184[0]) = v67;
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v69, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
    return *(unsigned int *)v183;
  }
  if ( (*((_BYTE *)a5 + 140) & 0x20) != 0 )
  {
    v68 = (const unsigned __int16 *)*((_QWORD *)a5 + 65);
    if ( !v68 || !InvStrCmpIW(v68, L"1.0") )
      *((_DWORD *)a5 + 158) = 3;
  }
  v70 = (unsigned int *)((char *)a5 + 632);
  if ( *((_DWORD *)a5 + 158) != 3 )
  {
    if ( (unsigned int)OmaDmIsNodePresent(6, (char *)a5 + 48) )
    {
      v192 = 0;
      ValueFromStruct = OmaDmGetValueFromStruct(6, (char *)a5 + 48, 0xFFFFFFFFLL, &v192, 0);
      *(_DWORD *)v183 = ValueFromStruct;
      ManagementServerAddressList = ValueFromStruct;
      if ( ValueFromStruct < 0 )
      {
        LODWORD(v184[0]) = 6015;
        HIDWORD(v184[0]) = ValueFromStruct;
        Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
        if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
          McTemplateU0qq_EventWriteTransfer(v72, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
        return *(unsigned int *)v183;
      }
      if ( !*(_QWORD *)v192 )
      {
        LODWORD(v184[0]) = 6002;
LABEL_150:
        HIDWORD(v184[0]) = -2147418113;
        Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
        if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) == 0 )
          return 2147549183LL;
        v74 = ManagementServerAddressList;
LABEL_401:
        McTemplateU0qq_EventWriteTransfer(v73, OmaDmClientFunctionReturnValueEvent, 3, v74);
        return 2147549183LL;
      }
      AuthType = GetAuthType(*(_QWORD *)v192, 0xFFFFFFFFLL, (char *)a5 + 632);
      *(_DWORD *)v183 = AuthType;
      ManagementServerAddressList = AuthType;
      if ( AuthType < 0 )
      {
        LODWORD(v184[0]) = 9004;
        HIDWORD(v184[0]) = AuthType;
        Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
        if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
          McTemplateU0qq_EventWriteTransfer(v76, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
        return *(unsigned int *)v183;
      }
    }
    v70 = (unsigned int *)((char *)a5 + 632);
  }
  v77 = *v70;
  if ( (_DWORD)v77 != 3 )
  {
    if ( *((_DWORD *)a5 + 157) == -1 )
    {
      LODWORD(v184[0]) = 9061;
      goto LABEL_150;
    }
    if ( *((_DWORD *)a5 + 156) == -1 )
    {
      LODWORD(v184[0]) = 9005;
      goto LABEL_150;
    }
  }
  v78 = Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager::ValidateAcctParameters(
          v68,
          (char *)a5 + 48,
          v77,
          *((unsigned int *)a5 + 157),
          *((_DWORD *)a5 + 156));
  *(_DWORD *)v183 = v78;
  ManagementServerAddressList = v78;
  if ( v78 < 0 )
  {
    LODWORD(v184[0]) = 9076;
    HIDWORD(v184[0]) = v78;
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v79, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
    return *(unsigned int *)v183;
  }
  if ( (unsigned int)OmaDmIsNodePresent(38, (char *)a5 + 48)
    && (unsigned int)OmaDmIsNodeValuePresent(38, (char *)a5 + 48) )
  {
    v192 = 0;
    v80 = OmaDmGetValueFromStruct(38, (char *)a5 + 48, 0xFFFFFFFFLL, &v192, 0);
    *(_DWORD *)v183 = v80;
    ManagementServerAddressList = v80;
    if ( v80 < 0 )
    {
      LODWORD(v184[0]) = 6019;
      HIDWORD(v184[0]) = v80;
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v81, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
      return *(unsigned int *)v183;
    }
    *((_WORD *)a5 + 372) = *(_WORD *)v192;
  }
  v192 = (void (*)(void *, unsigned __int8))(*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 184LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
  if ( !(unsigned int)OmaDmIsNodeValuePresent(21, (char *)a5 + 48) )
  {
    v82 = (*(__int64 (__fastcall **)(void (*)(void *, unsigned __int8), struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, const wchar_t *))(*(_QWORD *)v192 + 32LL))(
            v192,
            a5,
            L"1.2");
    *(_DWORD *)v183 = v82;
    ManagementServerAddressList = v82;
    if ( v82 < 0 )
    {
      LODWORD(v184[0]) = 9069;
      HIDWORD(v184[0]) = v82;
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v83, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
      return *(unsigned int *)v183;
    }
LABEL_194:
    if ( (unsigned int)OmaDmIsNodePresent(27, (char *)a5 + 48)
      && (unsigned int)OmaDmIsNodeValuePresent(27, (char *)a5 + 48) )
    {
      *(_QWORD *)v188 = 0;
      v90 = OmaDmGetValueFromStruct(27, (char *)a5 + 48, 0xFFFFFFFFLL, v188, 0);
      *(_DWORD *)v183 = v90;
      ManagementServerAddressList = v90;
      if ( v90 < 0 )
      {
        LODWORD(v184[0]) = 6021;
        HIDWORD(v184[0]) = v90;
        Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
        if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
          McTemplateU0qq_EventWriteTransfer(v91, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
        return *(unsigned int *)v183;
      }
      *((_WORD *)a5 + 373) = **(_WORD **)v188;
    }
    v205 = 0;
    v92 = OmaDmGetValueFromStruct(20, (char *)a5 + 48, 0xFFFFFFFFLL, &v205, 0);
    *(_DWORD *)v183 = v92;
    ManagementServerAddressList = v92;
    if ( v92 < 0 )
    {
      LODWORD(v184[0]) = 6013;
      HIDWORD(v184[0]) = v92;
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v93, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
      return *(unsigned int *)v183;
    }
    if ( !v205 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState::ResetState(a5);
    if ( !*((_QWORD *)a5 + 70) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    ManagementServerAddressList = StringCchPrintfW(
                                    (unsigned __int16 *)a5 + 670,
                                    0xBu,
                                    L"%d",
                                    *((unsigned int *)a5 + 191));
    if ( (ManagementServerAddressList & 0x80000000) != 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    *((_QWORD *)a5 + 152) = (char *)a5 + 1340;
    *((_QWORD *)a5 + 151) = L"OMADM::AccountTypeString";
    *((_QWORD *)a5 + 153) = L"OMADM::AccountID";
    *((_QWORD *)a5 + 154) = *((_QWORD *)a5 + 70);
    LODWORD(v191) = 2;
    *((_DWORD *)a5 + 149) = 3;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v189 + 440LL))(
           *(_QWORD *)v189,
           *((_QWORD *)a5 + 65)) )
    {
      if ( !*v197 )
      {
        *((_DWORD *)a5 + 149) = 1;
        goto LABEL_221;
      }
      *((_DWORD *)a5 + 149) = 2;
      v94 = (unsigned __int16 **)((char *)a5 + 600);
      hMem = (HLOCAL)*((_QWORD *)a5 + 75);
      if ( hMem )
      {
        v95 = GetLastError();
        LocalFree(hMem);
        SetLastError(v95);
        v94 = (unsigned __int16 **)((char *)a5 + 600);
      }
      *v94 = 0;
      TargetUserSid = CopyString(*v197, 0xFFFFFFFF, v94);
    }
    else
    {
      v97 = (struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *)((char *)a5 + 600);
      hMem = (HLOCAL)*((_QWORD *)a5 + 75);
      if ( hMem )
      {
        v98 = GetLastError();
        LocalFree(hMem);
        SetLastError(v98);
        v97 = (struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *)((char *)a5 + 600);
      }
      *(_QWORD *)v97 = 0;
      TargetUserSid = Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager::GetTargetUserSid(
                        v97,
                        *((const unsigned __int16 **)a5 + 70),
                        (unsigned __int16 **)v97);
    }
    ManagementServerAddressList = TargetUserSid;
LABEL_221:
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v189 + 440LL))(
           *(_QWORD *)v189,
           *((_QWORD *)a5 + 65)) )
    {
      v99 = *((_DWORD *)a5 + 149);
      if ( v99 == 1 )
      {
        v100 = L"DEVICE";
      }
      else
      {
        v100 = L"USER";
        if ( v99 != 2 )
          v100 = L"MIXED";
      }
      v101 = (char *)a5 + 1208;
      *((_QWORD *)a5 + 156) = v100;
      *((_QWORD *)a5 + 155) = L"OMADM::SyncType";
      v102 = 3;
      LODWORD(v191) = 3;
    }
    else
    {
      v101 = (char *)a5 + 1208;
      v102 = (unsigned int)v191;
    }
    if ( (ManagementServerAddressList & 0x80000000) == 0 )
    {
      v103 = *((_QWORD *)a5 + 75);
      if ( v103 )
      {
        v104 = 2LL * (unsigned int)v102;
        *(_QWORD *)&v101[8 * v104 + 8] = v103;
        *(_QWORD *)&v101[8 * v104] = L"OMADM::TargetedUserSID";
        v102 = (unsigned int)(v102 + 1);
        LODWORD(v191) = v102;
      }
    }
    v105 = (unsigned int)**(_DWORD **)v194;
    if ( (int)v105 > 32 )
    {
      if ( (_DWORD)v105 == 33
        || (_DWORD)v105 == 34
        || (_DWORD)v105 == 35
        || (_DWORD)v105 == 36
        || (_DWORD)v105 == 40
        || (_DWORD)v105 == 42
        || (unsigned int)(v105 - 43) < 2 )
      {
        goto LABEL_253;
      }
    }
    else if ( (_DWORD)v105 == 32
           || (_DWORD)v105 == 5
           || (_DWORD)v105 == 13
           || (_DWORD)v105 == 14
           || (_DWORD)v105 == 15
           || (_DWORD)v105 == 16
           || (_DWORD)v105 == 18
           || (_DWORD)v105 == 19
           || (_DWORD)v105 == 20
           || (_DWORD)v105 == 31 )
    {
      goto LABEL_253;
    }
    v105 = (unsigned int)(v105 - 20);
    if ( (_DWORD)v105 )
    {
      v105 = (unsigned int)(v105 - 16);
      if ( (_DWORD)v105 )
      {
        *(_DWORD *)v188 = 0;
        if ( (_DWORD)v105 != 1 )
        {
LABEL_254:
          v106 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *, __int64, __int64))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 8LL))(
                   Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory,
                   v105,
                   v102);
          ManagementServerAddressList = (*(__int64 (__fastcall **)(__int64, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, _QWORD))(*(_QWORD *)v106 + 8LL))(
                                          v106,
                                          a5,
                                          *(unsigned int *)v188);
          if ( ManagementServerAddressList == 1
            && *((_QWORD *)a5 + 75)
            && ((1LL << *((_DWORD *)a5 + 191)) & 0x4000040) != 0 )
          {
            *(_DWORD *)v183 = (_DWORD)v191 - 1;
            *(_QWORD *)v188 = 16LL * (unsigned int)((_DWORD)v191 - 1);
            if ( wcscmp_0(*(const wchar_t **)((char *)a5 + *(_QWORD *)v188 + 1208), L"OMADM::TargetedUserSID") )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            if ( !wcscmp_0(*(const wchar_t **)((char *)a5 + *(_QWORD *)v188 + 1208), L"OMADM::TargetedUserSID") )
            {
              LODWORD(v191) = *(_DWORD *)v183;
              v107 = *(_WORD **)v188;
              *(_QWORD *)((char *)a5 + *(_QWORD *)v188 + 1216) = 0;
              *(_QWORD *)((char *)a5 + (_QWORD)v107 + 1208) = 0;
            }
            *((_DWORD *)a5 + 149) = 1;
            if ( *v197
              && (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v189 + 440LL))(
                   *(_QWORD *)v189,
                   *((_QWORD *)a5 + 65)) )
            {
              ManagementServerAddressList = -2102788083;
            }
          }
          v108 = COmaDmLogger::GetLogger();
          COmaDmLogger::LogOmaDmSessionUser(
            v108,
            *((const unsigned __int16 **)a5 + 75),
            *((_DWORD *)a5 + 178),
            *((const unsigned __int16 **)a5 + 76),
            *((const unsigned __int16 **)a5 + 77),
            *((_DWORD *)a5 + 191),
            *((_DWORD *)a5 + 149));
          *(_DWORD *)v183 = ManagementServerAddressList;
          if ( (ManagementServerAddressList & 0x80000000) != 0 )
          {
            LODWORD(v184[0]) = 9070;
            HIDWORD(v184[0]) = ManagementServerAddressList;
            Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
            if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
              McTemplateU0qq_EventWriteTransfer(
                v109,
                OmaDmClientFunctionReturnValueEvent,
                3,
                ManagementServerAddressList);
            return *(unsigned int *)v183;
          }
          v187 = 0;
          v110 = **(_QWORD **)v189;
          v187 = 0;
          if ( (*(int (__fastcall **)(_QWORD, HLOCAL *))(v110 + 48))(*(_QWORD *)v189, &v187) >= 0 )
            *((_DWORD *)a5 + 181) = 1;
          v111 = v193;
          if ( !*(_QWORD *)(*(_QWORD *)v193 + 32LL) && *((_DWORD *)a5 + 191) != 4 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( *(_QWORD *)(*(_QWORD *)v111 + 32LL) )
          {
            v112 = (int)v191;
            v113 = 2LL * (unsigned int)v191;
            *((_QWORD *)a5 + v113 + 151) = L"OMADM::SessionID";
            *((_QWORD *)a5 + v113 + 152) = *(_QWORD *)(*(_QWORD *)v111 + 32LL);
            LODWORD(v191) = v112 + 1;
          }
          else if ( *((_DWORD *)a5 + 179) )
          {
            v114 = COmaDmLogger::GetLogger();
            COmaDmLogger::LogOmaDmContainerWarningNoSessionId(v114, *((_DWORD *)a5 + 191));
          }
          v115 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 72LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
          v116 = *(__int64 (__fastcall **)(__int64, char *, _QWORD, _QWORD))(*(_QWORD *)v115 + 8LL);
          StringCchPrintfW(&qword_140085290, 0x40u, L"%d", *v207);
          v117 = v200;
          v118 = v116(v115, (char *)v200 + 1624, *((_QWORD *)v200 + 9), *(_QWORD *)v196);
          v119 = v118;
          ManagementServerAddressList = v118;
          if ( v118 < 0 )
          {
            LODWORD(v184[0]) = 9025;
            HIDWORD(v184[0]) = v118;
            goto LABEL_279;
          }
          v121 = (void *)*((_QWORD *)v117 + 80);
          if ( v121 )
          {
            v122 = GetLastError();
            LocalFree(v121);
            SetLastError(v122);
          }
          *((_QWORD *)v117 + 80) = 0;
          v119 = CopyString(*((const unsigned __int16 **)v117 + 203), 0xFFFFFFFF, (unsigned __int16 **)v117 + 80);
          ManagementServerAddressList = v119;
          if ( v119 < 0 )
          {
            v123 = 597;
LABEL_289:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v123,
              (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\syncmlsessionstatemanager.cpp",
              (const char *)(unsigned int)v119,
              (int)&qword_140085290);
LABEL_279:
            if ( v187 )
              LocalFree(v187);
            Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
            if ( !v182 || (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) == 0 )
              return (unsigned int)v119;
            goto LABEL_283;
          }
          v124 = (void *)*((_QWORD *)v117 + 81);
          if ( v124 )
          {
            v125 = GetLastError();
            LocalFree(v124);
            SetLastError(v125);
          }
          *((_QWORD *)v117 + 81) = 0;
          v119 = CopyString(*((const unsigned __int16 **)v117 + 204), 0xFFFFFFFF, (unsigned __int16 **)v117 + 81);
          ManagementServerAddressList = v119;
          if ( v119 < 0 )
          {
            v123 = 601;
            goto LABEL_289;
          }
          v126 = (void *)*((_QWORD *)v117 + 82);
          if ( v126 )
          {
            v127 = GetLastError();
            LocalFree(v126);
            SetLastError(v127);
          }
          *((_QWORD *)v117 + 82) = 0;
          v119 = CopyString(*((const unsigned __int16 **)v117 + 212), 0xFFFFFFFF, (unsigned __int16 **)v117 + 82);
          ManagementServerAddressList = v119;
          if ( v119 < 0 )
          {
            v123 = 605;
            goto LABEL_289;
          }
          if ( ((1LL << *((_DWORD *)v117 + 191)) & 0xD402061) == 0 )
          {
            v128 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 200LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
            if ( *(_BYTE *)(*(_QWORD *)v193 + 8LL) == 3 )
            {
              v119 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, HKEY))(*(_QWORD *)v128 + 16LL))(
                       v128,
                       *((unsigned int *)v117 + 148),
                       (__int64)v117 + 48,
                       *(_QWORD *)v195,
                       hKey);
              ManagementServerAddressList = v119;
              if ( v119 < 0 )
              {
                LODWORD(v184[0]) = 9034;
                goto LABEL_303;
              }
            }
            else
            {
              if ( *(_BYTE *)(*(_QWORD *)v193 + 8LL) != 4 )
                goto LABEL_312;
              v119 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v128 + 8LL))(
                       v128,
                       *((unsigned int *)v117 + 148),
                       (__int64)v117 + 48);
              ManagementServerAddressList = v119;
              if ( v119 < 0 )
              {
                LODWORD(v184[0]) = 9033;
LABEL_303:
                HIDWORD(v184[0]) = v119;
                goto LABEL_304;
              }
            }
            *((_DWORD *)v117 + 396) = 1;
          }
LABEL_312:
          v202 = 0;
          v119 = OmaDmGetValueFromStruct(12, (char *)v117 + 48, 0xFFFFFFFFLL, &v202, 0);
          ManagementServerAddressList = v119;
          if ( v119 < 0 )
          {
            LODWORD(v184[0]) = 6014;
            goto LABEL_303;
          }
          v129 = v202;
          if ( !*v202 )
          {
            LODWORD(v184[0]) = 6001;
LABEL_396:
            HIDWORD(v184[0]) = -2147418113;
            if ( v187 )
              LocalFree(v187);
            Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
            if ( !v182 || (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) == 0 )
              return 2147549183LL;
            v74 = ManagementServerAddressList;
            goto LABEL_401;
          }
          v130 = (unsigned __int16 **)((char *)v117 + 1416);
          v196 = (HLOCAL)*((_QWORD *)v117 + 177);
          if ( v196 )
          {
            v131 = GetLastError();
            LocalFree(v196);
            SetLastError(v131);
            v129 = v202;
            v130 = (unsigned __int16 **)((char *)v117 + 1416);
          }
          *v130 = 0;
          v119 = CopyString(*v129, 0xFFFFFFFF, v130);
          ManagementServerAddressList = v119;
          if ( v119 < 0 )
          {
            v132 = 666;
            goto LABEL_320;
          }
          v203 = 0;
          v119 = OmaDmGetValueFromStruct(56, (char *)v117 + 48, 0xFFFFFFFFLL, &v203, 0);
          ManagementServerAddressList = v119;
          if ( v119 < 0 )
          {
            LODWORD(v184[0]) = 6022;
            goto LABEL_303;
          }
          v133 = v203;
          if ( *v203 )
          {
            v134 = (_QWORD *)((char *)v117 + 2056);
            v196 = (HLOCAL)*((_QWORD *)v117 + 257);
            if ( v196 )
            {
              v135 = GetLastError();
              LocalFree(v196);
              SetLastError(v135);
              v133 = v203;
              v134 = (_QWORD *)((char *)v117 + 2056);
            }
            *v134 = 0;
            ManagementServerAddressList = Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager::GetManagementServerAddressList(
                                            (_DWORD)v134,
                                            *v133,
                                            (_DWORD)v134,
                                            (int)v117 + 2048,
                                            (__int64)v117 + 2064);
          }
          v136 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 112LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
          v137 = v136;
          v200 = (struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *)v136;
          v138 = *((_QWORD *)v117 + 258);
          if ( *((_QWORD *)v117 + 259) == v138 )
          {
            v119 = (*(__int64 (__fastcall **)(__int64, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, const unsigned __int16 *))(*(_QWORD *)v136 + 8LL))(
                     v136,
                     v117,
                     *v202);
            ManagementServerAddressList = v119;
            if ( v119 < 0 )
            {
              LODWORD(v184[0]) = 9056;
              goto LABEL_303;
            }
          }
          else
          {
            *((_BYTE *)v117 + 2044) = 1;
            v139 = *((_QWORD *)v117 + 256);
            hKey = 0;
            while ( 1 )
            {
              v140 = (_QWORD *)(32 * v139 + v138);
              if ( v140[3] > 7u )
                v140 = (_QWORD *)*v140;
              v141 = (*(__int64 (__fastcall **)(__int64, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, _QWORD *))(*(_QWORD *)v137 + 8LL))(
                       v137,
                       v117,
                       v140);
              v119 = v141;
              ManagementServerAddressList = v141;
              if ( v141 >= 0 )
                break;
              v142 = (HKEY)((char *)hKey + 1);
              hKey = v142;
              v138 = *((_QWORD *)v117 + 258);
              v143 = (*((_QWORD *)v117 + 259) - v138) >> 5;
              if ( v142 == (HKEY)v143 || v141 != -2147012891 )
                goto LABEL_336;
              v139 = ((unsigned __int64)v142 + *((_QWORD *)v117 + 256)) % v143;
              v137 = (__int64)v200;
            }
            v144 = COmaDmLogger::GetLogger();
            Microsoft::Windows::TelemetryLogger::LogMeasure(v144, 1, 2, 0);
            v119 = ManagementServerAddressList;
LABEL_336:
            if ( v119 < 0 )
            {
              LODWORD(v184[0]) = 3008;
              goto LABEL_303;
            }
          }
          v204 = 0;
          v119 = OmaDmGetValueFromStruct(3, (char *)v117 + 48, 0xFFFFFFFFLL, &v204, 0);
          ManagementServerAddressList = v119;
          if ( v119 < 0 )
          {
            LODWORD(v184[0]) = 6012;
            goto LABEL_303;
          }
          *(_DWORD *)v188 = 0;
          v146 = (FirstSync **)((char *)v117 + 560);
          if ( FirstSync::GetIsFirstSyncKeyPresent(*((FirstSync **)v117 + 70), v188, v145) >= 0 && *(_DWORD *)v188 )
          {
            *(_DWORD *)v195 = 0;
            *(_DWORD *)v194 = 0;
            *(_DWORD *)v189 = 0;
            *(_DWORD *)v183 = 0;
            if ( FirstSync::GetIsSyncDone(*v146, 0, v195, v148) < 0
              || (int)FirstSync::HasAnyUserPageBeenDisplayed(*v146, v194, v149) < 0 )
            {
LABEL_362:
              if ( FirstSync::GetIsSyncDone(*v146, *((const unsigned __int16 **)v117 + 75), v189, v150) >= 0
                && FirstSync::GetSkipUserStatusPage(*v146, v183, v153) >= 0
                && !*(_DWORD *)v189
                && !*(_DWORD *)v183 )
              {
                *((_DWORD *)v117 + 167) = 2;
              }
              goto LABEL_367;
            }
            if ( !*v146 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x27A,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
                (const char *)0x80070057LL,
                v180);
              goto LABEL_362;
            }
            LODWORD(v193) = 1;
            hKey = 0;
            FirstSyncKey = FirstSync::GetFirstSyncKey(
                             (PCWSTR)*v146,
                             0,
                             (const unsigned __int16 *)&hKey,
                             (HKEY *)v150,
                             v180);
            *(_DWORD *)v188 = 0;
            v152 = hKey;
            if ( FirstSyncKey < 0
              || (FirstSyncKey = OmaDmRegistryGetDWORD(hKey, 0, L"SkipDeviceStatusPage", (unsigned int *)v188),
                  LODWORD(v197) = FirstSyncKey,
                  FirstSyncKey < 0) )
            {
              if ( FirstSyncKey == -2147024894 )
                FirstSyncKey = 0;
              LODWORD(v197) = FirstSyncKey;
            }
            else
            {
              v147 = *(_DWORD *)v188 != 0;
              LODWORD(v193) = *(_DWORD *)v188 != 0;
            }
            if ( v152 )
            {
              RegCloseKey(v152);
              FirstSyncKey = (int)v197;
            }
            if ( FirstSyncKey < 0 || *(_DWORD *)v195 || (_DWORD)v193 || *(_DWORD *)v194 )
            {
              v146 = (FirstSync **)((char *)v117 + 560);
              goto LABEL_362;
            }
            *((_DWORD *)v117 + 167) = 1;
          }
LABEL_367:
          *(_DWORD *)v183 = 0;
          v154 = *(_DWORD *)Feature_AutopilotDevicePreparation__descriptor;
          if ( (*(_DWORD *)Feature_AutopilotDevicePreparation__descriptor & 4) == 0 )
          {
            v196 = *(HLOCAL *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDevicePreparation>::GetCachedFeatureEnabledState(
                                v147,
                                &v196);
            v154 = (unsigned int)v196;
          }
          *(_DWORD *)v189 = 0;
          v189[2] = 3;
          v179 = v189;
          wil::details::ReportUsageToService(&qword_1400851C8, 41603559, (v154 >> 10) & 1, (v154 >> 11) & 1);
          if ( (int)Microsoft::Windows::Autopilot::AutopilotDevicePreparationHelpers::GetAndEnforceAutopilotDevicePrepHintIsInOobe((enum AUTOPILOT_DEVICE_PREP_HINT *)v183) >= 0 )
            *((_DWORD *)v117 + 166) = *(_DWORD *)v183;
          v119 = (*(__int64 (__fastcall **)(void (*)(void *, unsigned __int8), struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *))(*(_QWORD *)v192 + 8LL))(
                   v192,
                   v117);
          ManagementServerAddressList = v119;
          if ( v119 < 0 )
          {
            LODWORD(v184[0]) = 9020;
            goto LABEL_303;
          }
          v155 = (unsigned __int16 **)((char *)v117 + 1408);
          v156 = (HKEY)*((_QWORD *)v117 + 176);
          hKey = v156;
          v157 = v204;
          if ( *v204 )
          {
            if ( v156 )
            {
              v161 = GetLastError();
              LocalFree(hKey);
              SetLastError(v161);
              v157 = v204;
              v155 = (unsigned __int16 **)((char *)v117 + 1408);
            }
            *v155 = 0;
            v159 = -1;
            v160 = *v157;
          }
          else
          {
            if ( v156 )
            {
              v158 = GetLastError();
              LocalFree(hKey);
              SetLastError(v158);
              v155 = (unsigned __int16 **)((char *)v117 + 1408);
            }
            *v155 = 0;
            v159 = *((_DWORD *)v117 + 454);
            v160 = (const unsigned __int16 *)*((_QWORD *)v117 + 226);
          }
          v119 = CopyString(v160, v159, v155);
          ManagementServerAddressList = v119;
          if ( v119 >= 0 )
          {
            *((_QWORD *)v117 + 148) = *((_QWORD *)v117 + 176);
            v162 = (int)v191;
            v163 = 2LL * (unsigned int)v191;
            v164 = (char *)v117 + 1208;
            *(_QWORD *)&v164[8 * v163 + 8] = L"INPROC";
            *(_QWORD *)&v164[8 * v163] = L"OMADM::DpuRunningMode";
            LODWORD(v191) = v162 + 1;
            ManagementServerAddressList = StringCchPrintfW((unsigned __int16 *)v117 + 681, 0xBu, L"%d");
            if ( (ManagementServerAddressList & 0x80000000) != 0 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            v165 = (int)v191;
            v166 = 2LL * (unsigned int)v191;
            *(_QWORD *)&v164[8 * v166 + 8] = (char *)v117 + 1362;
            *(_QWORD *)&v164[8 * v166] = L"pdcprocessactivationid";
            LODWORD(v191) = v165 + 1;
            ManagementServerAddressList = StringCchPrintfW((unsigned __int16 *)v117 + 692, 0xBu, L"%d", 1800);
            if ( (ManagementServerAddressList & 0x80000000) != 0 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            v167 = (int)v191;
            v168 = 2LL * (unsigned int)v191;
            *(_QWORD *)&v164[8 * v168 + 8] = (char *)v117 + 1384;
            *(_QWORD *)&v164[8 * v168] = L"pdctotalexpectedduration";
            v169 = v167 + 1;
            if ( (unsigned int)(v167 + 1) > 8 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            *((_DWORD *)v117 + 334) = v169;
            *((_QWORD *)v117 + 150) = (char *)v117 + 1208;
            *((_DWORD *)v117 + 299) = v169;
            *((_QWORD *)v117 + 147) = *((_QWORD *)v117 + 9);
            *((_DWORD *)v117 + 292) = 1;
            *((_DWORD *)v117 + 293) = *((_DWORD *)v117 + 35);
            *((_DWORD *)v117 + 298) = 0;
            if ( *((_DWORD *)v117 + 133) )
            {
              *((_DWORD *)v117 + 371) = 1;
              LODWORD(v179) = 0;
              v119 = (*(__int64 (__fastcall **)(struct tagTriggerInfo *, _QWORD, __int64, _QWORD))(*(_QWORD *)v198 + 8LL))(
                       v198,
                       0,
                       1,
                       0);
              ManagementServerAddressList = v119;
              if ( v119 < 0 )
              {
                LODWORD(v184[0]) = 9018;
                goto LABEL_303;
              }
            }
            if ( (unsigned int)OmaDmIsNodePresent(22, (char *)v117 + 48) )
            {
              hKey = 0;
              v119 = OmaDmGetValueFromStruct(22, (char *)v117 + 48, 0xFFFFFFFFLL, &hKey, 0);
              ManagementServerAddressList = v119;
              if ( v119 < 0 )
              {
                LODWORD(v184[0]) = 6020;
                goto LABEL_303;
              }
              if ( !*(_QWORD *)hKey )
              {
                LODWORD(v184[0]) = 6006;
                goto LABEL_396;
              }
              v170 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&((char *)v117 + 752);
              v119 = CopyString(*(const unsigned __int16 **)hKey, 0xFFFFFFFF, v170);
              ManagementServerAddressList = v119;
              if ( v119 < 0 )
              {
                v132 = 852;
                goto LABEL_320;
              }
            }
            else
            {
              v171 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&((char *)v117 + 752);
              v119 = CopyString(L"application/vnd.syncml.dm+xml", 0xFFFFFFFF, v171);
              ManagementServerAddressList = v119;
              if ( v119 < 0 )
              {
                v132 = 858;
                goto LABEL_320;
              }
            }
            v206 = 0;
            v119 = OmaDmGetValueFromStruct(4, (char *)v117 + 48, 0xFFFFFFFFLL, &v206, 0);
            ManagementServerAddressList = v119;
            if ( v119 < 0 )
            {
              LODWORD(v184[0]) = 6048;
              goto LABEL_303;
            }
            if ( *v206 )
            {
              v119 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, _QWORD, __int64, __int64))(*(_QWORD *)v200 + 32LL))(
                       v200,
                       *v206,
                       (__int64)v117 + 2092,
                       (__int64)v117 + 2096);
              ManagementServerAddressList = v119;
              if ( v119 < 0 )
              {
                LODWORD(v184[0]) = 6049;
                goto LABEL_303;
              }
            }
            if ( (unsigned int)OmaDmIsNodePresent(59, (char *)v117 + 48)
              && (unsigned int)OmaDmIsNodeValuePresent(59, (char *)v117 + 48) )
            {
              if ( (unsigned int)(*((_DWORD *)v117 + 113) - 1) > 2 )
              {
                *((_DWORD *)v117 + 113) = 0;
              }
              else
              {
                if ( !(unsigned int)OmaDmIsNodePresent(60, (char *)v117 + 48) )
                  *((_DWORD *)v117 + 114) = 1;
                if ( !*((_QWORD *)v117 + 58) && !*((_QWORD *)v117 + 59) )
                {
                  v119 = -2102656509;
                  ManagementServerAddressList = -2102656509;
                  v132 = 907;
                  goto LABEL_320;
                }
                v173 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 32LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
                v119 = (*(__int64 (__fastcall **)(__int64, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *))(*(_QWORD *)v173 + 80LL))(
                         v173,
                         v117);
                ManagementServerAddressList = v119;
                if ( v119 < 0 )
                {
                  v132 = 902;
                  goto LABEL_320;
                }
              }
            }
            Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager::GetSettingFromAcct(
              v172,
              (char *)v117 + 48,
              30,
              *((unsigned int *)v117 + 192));
            Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager::GetSettingFromAcct(
              v174,
              (char *)v117 + 48,
              31,
              *((unsigned int *)v117 + 198));
            Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager::GetSettingFromAcct(
              v175,
              (char *)v117 + 48,
              32,
              *((unsigned int *)v117 + 197));
            *(_DWORD *)v183 = 0;
            Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager::GetSettingFromAcct(
              v176,
              (char *)v117 + 48,
              33,
              0);
            if ( *(_DWORD *)v183 )
              *((_DWORD *)v117 + 195) = 0;
            v119 = ManagementServerAddressList;
LABEL_304:
            if ( v187 )
              LocalFree(v187);
            Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
            if ( !v182 || (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) == 0 )
              return (unsigned int)v119;
LABEL_283:
            McTemplateU0qq_EventWriteTransfer(v120, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
            return (unsigned int)v119;
          }
          v132 = 786;
LABEL_320:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v132,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\syncmlsessionstatemanager.cpp",
            (const char *)(unsigned int)v119,
            (int)v179);
          goto LABEL_304;
        }
      }
    }
LABEL_253:
    *(_DWORD *)v188 = 1;
    goto LABEL_254;
  }
  *(_QWORD *)v188 = 0;
  v84 = OmaDmGetValueFromStruct(21, (char *)a5 + 48, 0xFFFFFFFFLL, v188, 0);
  *(_DWORD *)v183 = v84;
  ManagementServerAddressList = v84;
  if ( v84 >= 0 )
  {
    if ( !**(_QWORD **)v188 )
    {
      LODWORD(v184[0]) = 6037;
      goto LABEL_150;
    }
    if ( InvStrCmpIW(**(const unsigned __int16 ***)v188, L"1.2") )
    {
      if ( InvStrCmpIW(**(const unsigned __int16 ***)v188, L"1.1") )
      {
        v184[0] = 0x8007005700002361uLL;
        Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
        if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
          McTemplateU0qq_EventWriteTransfer(v177, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
        return 2147942487LL;
      }
      else
      {
        v88 = (*(__int64 (__fastcall **)(void (*)(void *, unsigned __int8), struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, const wchar_t *))(*(_QWORD *)v192 + 32LL))(
                v192,
                a5,
                L"1.1");
        *(_DWORD *)v183 = v88;
        ManagementServerAddressList = v88;
        if ( v88 >= 0 )
          goto LABEL_194;
        LODWORD(v184[0]) = 9067;
        HIDWORD(v184[0]) = v88;
        Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
        if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
          McTemplateU0qq_EventWriteTransfer(v89, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
        return *(unsigned int *)v183;
      }
    }
    else
    {
      v86 = (*(__int64 (__fastcall **)(void (*)(void *, unsigned __int8), struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, const wchar_t *))(*(_QWORD *)v192 + 32LL))(
              v192,
              a5,
              L"1.2");
      *(_DWORD *)v183 = v86;
      ManagementServerAddressList = v86;
      if ( v86 >= 0 )
        goto LABEL_194;
      LODWORD(v184[0]) = 9068;
      HIDWORD(v184[0]) = v86;
      Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v87, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
      return *(unsigned int *)v183;
    }
  }
  else
  {
    LODWORD(v184[0]) = 6024;
    HIDWORD(v184[0]) = v84;
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v184);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v85, OmaDmClientFunctionReturnValueEvent, 3, ManagementServerAddressList);
    return *(unsigned int *)v183;
  }
}

```

## disassembly

```asm
0x14004f290  mov     r11, rsp
0x14004f293  push    rbx
0x14004f294  push    rsi
0x14004f295  push    rdi
0x14004f296  push    r12
0x14004f298  push    r13
0x14004f29a  push    r14
0x14004f29c  push    r15
0x14004f29e  sub     rsp, 160h
0x14004f2a5  mov     rax, cs:__security_cookie
0x14004f2ac  xor     rax, rsp
0x14004f2af  mov     [rsp+198h+var_48], rax
0x14004f2b7  mov     qword ptr [rsp+198h+var_D0], r9
0x14004f2bf  mov     rax, r8
0x14004f2c2  mov     qword ptr [rsp+198h+var_D8], rax
0x14004f2ca  mov     [rsp+198h+var_B8], rdx
0x14004f2d2  mov     [rsp+198h+var_F0], rax
0x14004f2da  mov     [rsp+198h+hMem], r9
0x14004f2e2  mov     rsi, [rsp+198h+arg_20]
0x14004f2ea  mov     [rsp+198h+var_A8], rsi
0x14004f2f2  mov     rax, [rsp+198h+arg_30]
0x14004f2fa  mov     [rsp+198h+var_E8], rax
0x14004f302  mov     rax, [rsp+198h+arg_38]
0x14004f30a  mov     [rsp+198h+hKey], rax
0x14004f312  xor     r13d, r13d
0x14004f315  mov     [rsp+198h+var_148], r13d
0x14004f31a  lea     r14d, [r13+8]
0x14004f31e  lea     edi, [r13+3]
0x14004f322  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, r14b
0x14004f329  jz      short loc_14004F360
0x14004f32b  mov     dword ptr [rsp+198h+var_140], edi
0x14004f32f  lea     rax, [rsp+198h+var_140]
0x14004f334  mov     [r11-58h], rax
0x14004f338  mov     qword ptr [r11-50h], 4
0x14004f340  lea     rax, [r11-68h]
0x14004f344  mov     [rsp+198h+var_178], rax
0x14004f349  lea     r9d, [r13+2]
0x14004f34d  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x14004f354  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14004f35b  call    McGenEventWrite_EventWriteTransfer
0x14004f360  lea     rbx, [rsp+198h+var_148]
0x14004f365  mov     [rsp+198h+var_68], rbx
0x14004f36d  mov     r15d, 1
0x14004f373  mov     r12b, r15b
0x14004f376  mov     [rsp+198h+var_144], r15b
0x14004f37b  mov     [rsp+198h+var_60], r15b
0x14004f383  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004f388  xor     r9d, r9d
0x14004f38b  lea     r8, aInitiatesessio; "InitiateSession"
0x14004f392  mov     edx, r15d
0x14004f395  mov     rcx, rax
0x14004f398  call    ?LogFunctionEntryMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@PEBDPEBGZZ; Microsoft::Windows::TelemetryLogger::LogFunctionEntryMeasure(Microsoft::Windows::TracingLevel,char const *,ushort const *,...)
0x14004f39d  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004f3a2  mov     [rsp+198h+var_138], r13
0x14004f3a7  lea     rcx, aInitiatesessio; "InitiateSession"
0x14004f3ae  mov     [rsp+198h+var_130], rcx
0x14004f3b3  mov     [rsp+198h+var_128], rax
0x14004f3b8  mov     [rsp+198h+var_120], r15d
0x14004f3bd  lea     rax, [rsp+198h+var_148]
0x14004f3c2  mov     [rsp+198h+var_118], rax
0x14004f3ca  mov     rax, [rsp+198h+var_B8]
0x14004f3d2  test    rax, rax
0x14004f3d5  jnz     short loc_14004F40F
0x14004f3d7  mov     ebx, 0D00000EFh
0x14004f3dc  mov     [rsp+198h+var_148], ebx
0x14004f3e0  lea     rcx, [rsp+198h+var_138]; this
0x14004f3e5  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004f3ea  nop
0x14004f3eb  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, r14b
0x14004f3f2  jz      short loc_14004F408
0x14004f3f4  mov     r9d, [rsp+198h+var_148]
0x14004f3f9  mov     r8d, edi
0x14004f3fc  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x14004f403  call    McTemplateU0qq_EventWriteTransfer
0x14004f408  mov     eax, ebx
0x14004f40a  jmp     loc_140051B61
0x14004f40f  lea     rcx, [rax+28h]
0x14004f413  mov     [rsp+198h+var_C0], rcx
0x14004f41b  cmp     [rcx], r13
0x14004f41e  jz      short loc_14004F46F
0x14004f420  mov     rcx, cs:?g_pIAbstractFactory@OmadmClient@MDM@Windows@Microsoft@@3PEAVIAbstractFactory@1234@EA; Microsoft::Windows::MDM::OmadmClient::IAbstractFactory * Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory
0x14004f427  mov     rax, [rcx]
0x14004f42a  mov     rax, [rax+60h]
0x14004f42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f433  mov     rcx, rax
0x14004f436  mov     rax, [rax]
0x14004f439  mov     rdx, [rsp+198h+var_C0]
0x14004f441  mov     rdx, [rdx]
0x14004f444  mov     rax, [rax+18h]
0x14004f448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f44d  test    eax, eax
0x14004f44f  jnz     short loc_14004F467
0x14004f451  mov     dword ptr [rsp+198h+var_138], 2653h
0x14004f459  mov     ebx, 82AA000Ch
0x14004f45e  mov     dword ptr [rsp+198h+var_138+4], ebx
0x14004f462  jmp     loc_14004F3E0
0x14004f467  mov     rax, [rsp+198h+var_B8]
0x14004f46f  cmp     qword ptr [rsp+198h+var_D0], 0
0x14004f478  jnz     short loc_14004F484
0x14004f47a  mov     ebx, 0D00000F1h
0x14004f47f  jmp     loc_14004F3DC
0x14004f484  cmp     [rsp+198h+arg_28], r13
0x14004f48c  jnz     short loc_14004F498
0x14004f48e  mov     ebx, 0D00000F3h
0x14004f493  jmp     loc_14004F3DC
0x14004f498  cmp     [rsp+198h+hKey], r13
0x14004f4a0  jnz     short loc_14004F4AC
0x14004f4a2  mov     ebx, 0D00000F4h
0x14004f4a7  jmp     loc_14004F3DC
0x14004f4ac  cmp     [rsp+198h+var_E8], r13
0x14004f4b4  jnz     short loc_14004F4C0
0x14004f4b6  mov     ebx, 0D00000F5h
0x14004f4bb  jmp     loc_14004F3DC
0x14004f4c0  lea     rcx, [rsi+28h]
0x14004f4c4  mov     [rsp+198h+var_E0], rcx
0x14004f4cc  mov     [rcx], rax
0x14004f4cf  mov     eax, [rax+4]
0x14004f4d2  mov     [rsi+63Ch], eax
0x14004f4d8  mov     rcx, cs:?g_pIAbstractFactory@OmadmClient@MDM@Windows@Microsoft@@3PEAVIAbstractFactory@1234@EA; Microsoft::Windows::MDM::OmadmClient::IAbstractFactory * Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory
0x14004f4df  mov     rax, [rcx]
0x14004f4e2  mov     rax, [rax+58h]
0x14004f4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f4eb  mov     r10, rax
0x14004f4ee  mov     [rsp+198h+var_B8], rax
0x14004f4f6  lea     rcx, [rsi+2A8h]
0x14004f4fd  cmp     [rcx], r13
0x14004f500  jnz     short loc_14004F56C
0x14004f502  mov     rax, [rax]
0x14004f505  mov     qword ptr [rsp+198h+var_170], rcx
0x14004f50a  mov     [rsp+198h+var_178], r13
0x14004f50f  xor     r9d, r9d
0x14004f512  xor     r8d, r8d
0x14004f515  xor     edx, edx
0x14004f517  mov     rcx, r10
0x14004f51a  mov     rax, [rax+8]
0x14004f51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f523  mov     dword ptr [rsp+198h+var_140], eax
0x14004f527  mov     [rsp+198h+var_148], eax
0x14004f52b  test    eax, eax
0x14004f52d  jns     short loc_14004F56C
0x14004f52f  mov     dword ptr [rsp+198h+var_138], 2339h
0x14004f537  mov     dword ptr [rsp+198h+var_138+4], eax
0x14004f53b  lea     rcx, [rsp+198h+var_138]; this
0x14004f540  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004f545  nop
0x14004f546  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, r14b
0x14004f54d  jz      short loc_14004F563
0x14004f54f  mov     r9d, [rsp+198h+var_148]
0x14004f554  mov     r8d, edi
0x14004f557  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x14004f55e  call    McTemplateU0qq_EventWriteTransfer
0x14004f563  mov     eax, dword ptr [rsp+198h+var_140]
0x14004f567  jmp     loc_140051B61
0x14004f56c  mov     rcx, cs:?g_pIAbstractFactory@OmadmClient@MDM@Windows@Microsoft@@3PEAVIAbstractFactory@1234@EA; Microsoft::Windows::MDM::OmadmClient::IAbstractFactory * Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory
0x14004f573  mov     rax, [rcx]
0x14004f576  mov     rax, [rax+98h]
0x14004f57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f582  mov     rcx, rax
0x14004f585  mov     qword ptr [rsp+198h+var_100], rax
0x14004f58d  mov     rax, [rax]
0x14004f590  mov     rdx, rsi
0x14004f593  mov     rax, [rax+8]
0x14004f597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f59c  mov     dword ptr [rsp+198h+var_140], eax
0x14004f5a0  mov     [rsp+198h+var_148], eax
0x14004f5a4  test    eax, eax
0x14004f5a6  jns     short loc_14004F5E5
0x14004f5a8  mov     dword ptr [rsp+198h+var_138], 2364h
0x14004f5b0  mov     dword ptr [rsp+198h+var_138+4], eax
0x14004f5b4  lea     rcx, [rsp+198h+var_138]; this
0x14004f5b9  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004f5be  nop
0x14004f5bf  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, r14b
0x14004f5c6  jz      short loc_14004F5DC
0x14004f5c8  mov     r9d, [rsp+198h+var_148]
0x14004f5cd  mov     r8d, edi
0x14004f5d0  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x14004f5d7  call    McTemplateU0qq_EventWriteTransfer
0x14004f5dc  mov     eax, dword ptr [rsp+198h+var_140]
0x14004f5e0  jmp     loc_140051B61
0x14004f5e5  mov     rcx, qword ptr [rsp+198h+var_100]
0x14004f5ed  mov     r8, [rcx]
0x14004f5f0  mov     rax, [rsp+198h+var_E0]
0x14004f5f8  mov     rax, [rax]
0x14004f5fb  cmp     [rax+9], r13b
0x14004f5ff  jnz     loc_14004F6C5
0x14004f605  mov     rdx, rsi
0x14004f608  mov     rax, [r8+10h]
0x14004f60c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f611  mov     dword ptr [rsp+198h+var_140], eax
0x14004f615  mov     [rsp+198h+var_148], eax
0x14004f619  test    eax, eax
0x14004f61b  jns     short loc_14004F65A
0x14004f61d  mov     dword ptr [rsp+198h+var_138], 234Fh
0x14004f625  mov     dword ptr [rsp+198h+var_138+4], eax
0x14004f629  lea     rcx, [rsp+198h+var_138]; this
0x14004f62e  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004f633  nop
0x14004f634  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, r14b
0x14004f63b  jz      short loc_14004F651
0x14004f63d  mov     r9d, [rsp+198h+var_148]
0x14004f642  mov     r8d, edi
0x14004f645  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x14004f64c  call    McTemplateU0qq_EventWriteTransfer
0x14004f651  mov     eax, dword ptr [rsp+198h+var_140]
0x14004f655  jmp     loc_140051B61
0x14004f65a  mov     rax, [rsi+3B0h]
0x14004f661  test    rax, rax
0x14004f664  jz      short loc_14004F678
0x14004f666  mov     eax, [rax+28h]
0x14004f669  mov     rcx, qword ptr [rsp+198h+var_D8]
0x14004f671  mov     [rcx], eax
0x14004f673  jmp     loc_14004F726
0x14004f678  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004f67d  xor     r9d, r9d
0x14004f680  xor     edx, edx
0x14004f682  mov     r8d, 0BC1h
0x14004f688  mov     rcx, rax
0x14004f68b  call    ?LogMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@KPEBGZZ; Microsoft::Windows::TelemetryLogger::LogMeasure(Microsoft::Windows::TracingLevel,ulong,ushort const *,...)
0x14004f690  mov     [rsp+198h+var_148], r15d
0x14004f695  lea     rcx, [rsp+198h+var_138]; this
0x14004f69a  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004f69f  nop
0x14004f6a0  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, r14b
0x14004f6a7  jz      short loc_14004F6BD
0x14004f6a9  mov     r9d, [rsp+198h+var_148]
0x14004f6ae  mov     r8d, edi
0x14004f6b1  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x14004f6b8  call    McTemplateU0qq_EventWriteTransfer
0x14004f6bd  mov     eax, r15d
0x14004f6c0  jmp     loc_140051B61
0x14004f6c5  lea     rdx, [rsi+350h]
0x14004f6cc  mov     rax, [r8+28h]
0x14004f6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f6d5  mov     dword ptr [rsp+198h+var_140], eax
0x14004f6d9  mov     [rsp+198h+var_148], eax
0x14004f6dd  test    eax, eax
0x14004f6df  jns     short loc_14004F71E
0x14004f6e1  mov     dword ptr [rsp+198h+var_138], 234Dh
0x14004f6e9  mov     dword ptr [rsp+198h+var_138+4], eax
0x14004f6ed  lea     rcx, [rsp+198h+var_138]; this
0x14004f6f2  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004f6f7  nop
0x14004f6f8  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, r14b
0x14004f6ff  jz      short loc_14004F715
0x14004f701  mov     r9d, [rsp+198h+var_148]
0x14004f706  mov     r8d, edi
0x14004f709  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x14004f710  call    McTemplateU0qq_EventWriteTransfer
0x14004f715  mov     eax, dword ptr [rsp+198h+var_140]
0x14004f719  jmp     loc_140051B61
0x14004f71e  mov     rcx, qword ptr [rsp+198h+var_D8]
0x14004f726  mov     ecx, [rcx]
0x14004f728  cmp     ecx, 23h ; '#'
0x14004f72b  jg      short loc_14004F763
0x14004f72d  jz      short loc_14004F74C
0x14004f72f  cmp     ecx, edi
0x14004f731  jz      short loc_14004F788
0x14004f733  cmp     ecx, 7
0x14004f736  jz      short loc_14004F75F
0x14004f738  cmp     ecx, 9
0x14004f73b  jz      short loc_14004F758
0x14004f73d  cmp     ecx, 0Bh
0x14004f740  jz      short loc_14004F753
0x14004f742  cmp     ecx, 14h
0x14004f745  jz      short loc_14004F796
0x14004f747  cmp     ecx, 18h
0x14004f74a  jnz     short loc_14004F781
0x14004f74c  mov     eax, 5
0x14004f751  jmp     short loc_14004F799
0x14004f753  mov     eax, r14d
0x14004f756  jmp     short loc_14004F799
0x14004f758  mov     eax, 6
0x14004f75d  jmp     short loc_14004F799
0x14004f75f  mov     eax, edi
0x14004f761  jmp     short loc_14004F799
0x14004f763  sub     ecx, 24h ; '$'
0x14004f766  jz      short loc_14004F796
0x14004f768  sub     ecx, 1
0x14004f76b  jz      short loc_14004F796
0x14004f76d  sub     ecx, 5
0x14004f770  jz      short loc_14004F78F
0x14004f772  sub     ecx, 1
0x14004f775  jz      short loc_14004F78F
0x14004f777  sub     ecx, r14d
0x14004f77a  jz      short loc_14004F788
0x14004f77c  cmp     ecx, 1
0x14004f77f  jz      short loc_14004F788
0x14004f781  mov     eax, 7
0x14004f786  jmp     short loc_14004F799
0x14004f788  mov     eax, 2
0x14004f78d  jmp     short loc_14004F799
0x14004f78f  mov     eax, 4
0x14004f794  jmp     short loc_14004F799
0x14004f796  mov     eax, r15d
0x14004f799  mov     [rsi+850h], eax
0x14004f79f  lea     rcx, [rsi+5D8h]; this
0x14004f7a6  call    ?Close@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@QEAAJXZ; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::Close(void)
0x14004f7ab  mov     dword ptr [rsp+198h+var_108], eax
0x14004f7b2  mov     [rsp+198h+var_148], eax
  ... truncated ...
```
