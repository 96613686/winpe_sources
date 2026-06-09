# OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)

- ea: `0x180011280`
- end: `0x180013863`
- name: `?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z`
- size: `9699`
- prototype: `unsigned int __high(enum iaaAppAssignment, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CRegHandle *, bool)`
- caller_count: `24`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000f930`
- `0x180010b58`
- `0x180039bc4`
- `0x18003a560`
- `0x18003ae54`
- `0x18003c1d0`
- `0x18003e4c0`
- `0x18003ecd4`
- `0x18003f930`
- `0x1800424b4`
- `0x1800434d0`
- `0x180045c60`
- `0x18004660c`
- `0x180048294`
- `0x1800493f0`
- `0x18004bb30`
- `0x18004c158`
- `0x18004c8f0`
- `0x18005de50`
- `0x18005e764`
- `0x1800b3608`
- `0x18011b27c`
- `0x18019971c`
- `0x1801dc920`

## callees

- `0x18000c4bc`
- `0x180011280`
- `0x18001386c`
- `0x180014160`
- `0x1800141e0`
- `0x180014288`
- `0x180014328`
- `0x180014f18`
- `0x1800399d0`
- `0x18003c030`
- `0x180045ba4`
- `0x18006cb7c`
- `0x180087b7c`
- `0x18015cbac`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180011b28`
- `msvcrt!_wcsicmp` at `0x180011b28`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180011a25`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180011e8e`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180012a6e`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180011a25`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180011e8e`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180012a6e`
- `ADVAPI32!SetThreadToken` at `0x180011982`
- `ADVAPI32!SetThreadToken` at `0x180011d15`
- `ADVAPI32!SetThreadToken` at `0x18001208d`
- `ADVAPI32!SetThreadToken` at `0x180012848`
- `ADVAPI32!SetThreadToken` at `0x180012c19`
- `ADVAPI32!SetThreadToken` at `0x1800130a1`
- `ADVAPI32!SetThreadToken` at `0x180013118`
- `ADVAPI32!SetThreadToken` at `0x180013407`
- `ADVAPI32!SetThreadToken` at `0x1800135b5`
- `ADVAPI32!SetThreadToken` at `0x180013633`
- `ADVAPI32!SetThreadToken` at `0x180013703`
- `ADVAPI32!SetThreadToken` at `0x180013781`
- `ADVAPI32!SetThreadToken` at `0x180011982`
- `ADVAPI32!SetThreadToken` at `0x180011d15`
- `ADVAPI32!SetThreadToken` at `0x18001208d`
- `ADVAPI32!SetThreadToken` at `0x180012848`
- `ADVAPI32!SetThreadToken` at `0x180012c19`
- `ADVAPI32!SetThreadToken` at `0x1800130a1`
- `ADVAPI32!SetThreadToken` at `0x180013118`
- `ADVAPI32!SetThreadToken` at `0x180013407`
- `ADVAPI32!SetThreadToken` at `0x1800135b5`
- `ADVAPI32!SetThreadToken` at `0x180013633`
- `ADVAPI32!SetThreadToken` at `0x180013703`
- `ADVAPI32!SetThreadToken` at `0x180013781`
- `ADVAPI32!OpenThreadToken` at `0x18001232d`
- `ADVAPI32!OpenThreadToken` at `0x180012f10`
- `ADVAPI32!OpenThreadToken` at `0x18001232d`
- `ADVAPI32!OpenThreadToken` at `0x180012f10`
- `ADVAPI32!OpenProcessToken` at `0x180012368`
- `ADVAPI32!OpenProcessToken` at `0x180012f4b`
- `ADVAPI32!OpenProcessToken` at `0x180012368`
- `ADVAPI32!OpenProcessToken` at `0x180012f4b`
- `ADVAPI32!RegCloseKey` at `0x180011d66`
- `ADVAPI32!RegCloseKey` at `0x180012563`
- `ADVAPI32!RegCloseKey` at `0x180012666`
- `ADVAPI32!RegCloseKey` at `0x180011d66`
- `ADVAPI32!RegCloseKey` at `0x180012563`
- `ADVAPI32!RegCloseKey` at `0x180012666`
- `KERNEL32!InitializeCriticalSection` at `0x18001253e`
- `KERNEL32!InitializeCriticalSection` at `0x180012641`
- `KERNEL32!InitializeCriticalSection` at `0x18001253e`
- `KERNEL32!InitializeCriticalSection` at `0x180012641`
- `KERNEL32!CloseHandle` at `0x18001282f`
- `KERNEL32!CloseHandle` at `0x180012862`
- `KERNEL32!CloseHandle` at `0x1800130ff`
- `KERNEL32!CloseHandle` at `0x180013132`
- `KERNEL32!CloseHandle` at `0x18001282f`
- `KERNEL32!CloseHandle` at `0x180012862`
- `KERNEL32!CloseHandle` at `0x1800130ff`
- `KERNEL32!CloseHandle` at `0x180013132`
- `KERNEL32!LeaveCriticalSection` at `0x1800116fd`
- `KERNEL32!LeaveCriticalSection` at `0x18001173a`
- `KERNEL32!LeaveCriticalSection` at `0x1800118c6`
- `KERNEL32!LeaveCriticalSection` at `0x180011b99`
- `KERNEL32!LeaveCriticalSection` at `0x180011bd6`
- `KERNEL32!LeaveCriticalSection` at `0x180011c54`
- `KERNEL32!LeaveCriticalSection` at `0x180011d83`
- `KERNEL32!LeaveCriticalSection` at `0x18001201b`
- `KERNEL32!LeaveCriticalSection` at `0x1800123c6`
- `KERNEL32!LeaveCriticalSection` at `0x18001257f`
- `KERNEL32!LeaveCriticalSection` at `0x180012682`
- `KERNEL32!LeaveCriticalSection` at `0x180012799`
- `KERNEL32!LeaveCriticalSection` at `0x18001280c`
- `KERNEL32!LeaveCriticalSection` at `0x180012ba3`
- `KERNEL32!LeaveCriticalSection` at `0x180012e70`
- `KERNEL32!LeaveCriticalSection` at `0x180012fa9`
- `KERNEL32!LeaveCriticalSection` at `0x180013399`
- `KERNEL32!LeaveCriticalSection` at `0x180013579`
- `KERNEL32!LeaveCriticalSection` at `0x1800136c7`
- `KERNEL32!LeaveCriticalSection` at `0x1800116fd`
- `KERNEL32!LeaveCriticalSection` at `0x18001173a`
- `KERNEL32!LeaveCriticalSection` at `0x1800118c6`
- `KERNEL32!LeaveCriticalSection` at `0x180011b99`
- `KERNEL32!LeaveCriticalSection` at `0x180011bd6`
- `KERNEL32!LeaveCriticalSection` at `0x180011c54`
- `KERNEL32!LeaveCriticalSection` at `0x180011d83`
- `KERNEL32!LeaveCriticalSection` at `0x18001201b`
- `KERNEL32!LeaveCriticalSection` at `0x1800123c6`
- `KERNEL32!LeaveCriticalSection` at `0x18001257f`
- `KERNEL32!LeaveCriticalSection` at `0x180012682`
- `KERNEL32!LeaveCriticalSection` at `0x180012799`
- `KERNEL32!LeaveCriticalSection` at `0x18001280c`
- `KERNEL32!LeaveCriticalSection` at `0x180012ba3`
- `KERNEL32!LeaveCriticalSection` at `0x180012e70`
- `KERNEL32!LeaveCriticalSection` at `0x180012fa9`
- `KERNEL32!LeaveCriticalSection` at `0x180013399`
- `KERNEL32!LeaveCriticalSection` at `0x180013579`
- `KERNEL32!LeaveCriticalSection` at `0x1800136c7`
- `KERNEL32!EnterCriticalSection` at `0x1800116c1`
- `KERNEL32!EnterCriticalSection` at `0x1800116d4`
- `KERNEL32!EnterCriticalSection` at `0x1800118a4`
- `KERNEL32!EnterCriticalSection` at `0x180011b5f`
- `KERNEL32!EnterCriticalSection` at `0x180011b72`
- `KERNEL32!EnterCriticalSection` at `0x180011c32`
- `KERNEL32!EnterCriticalSection` at `0x180011d51`
- `KERNEL32!EnterCriticalSection` at `0x180012002`
- `KERNEL32!EnterCriticalSection` at `0x18001254e`
- `KERNEL32!EnterCriticalSection` at `0x180012651`
- `KERNEL32!EnterCriticalSection` at `0x180012b8a`
- `KERNEL32!EnterCriticalSection` at `0x180012e57`
- `KERNEL32!EnterCriticalSection` at `0x180013380`
- `KERNEL32!EnterCriticalSection` at `0x1800116c1`
- `KERNEL32!EnterCriticalSection` at `0x1800116d4`
- `KERNEL32!EnterCriticalSection` at `0x1800118a4`
- `KERNEL32!EnterCriticalSection` at `0x180011b5f`
- `KERNEL32!EnterCriticalSection` at `0x180011b72`
- `KERNEL32!EnterCriticalSection` at `0x180011c32`
- `KERNEL32!EnterCriticalSection` at `0x180011d51`
- `KERNEL32!EnterCriticalSection` at `0x180012002`
- `KERNEL32!EnterCriticalSection` at `0x18001254e`
- `KERNEL32!EnterCriticalSection` at `0x180012651`
- `KERNEL32!EnterCriticalSection` at `0x180012b8a`
- `KERNEL32!EnterCriticalSection` at `0x180012e57`
- `KERNEL32!EnterCriticalSection` at `0x180013380`
- `KERNEL32!GlobalAlloc` at `0x180012247`
- `KERNEL32!GlobalAlloc` at `0x1800123f6`
- `KERNEL32!GlobalAlloc` at `0x180013438`
- `KERNEL32!GlobalAlloc` at `0x180012247`
- `KERNEL32!GlobalAlloc` at `0x1800123f6`
- `KERNEL32!GlobalAlloc` at `0x180013438`
- `KERNEL32!GetCurrentThread` at `0x18001230e`
- `KERNEL32!GetCurrentThread` at `0x180012ef1`
- `KERNEL32!GetCurrentThread` at `0x18001230e`
- `KERNEL32!GetCurrentThread` at `0x180012ef1`
- `KERNEL32!GetCurrentProcess` at `0x18001234f`
- `KERNEL32!GetCurrentProcess` at `0x180012f32`
- `KERNEL32!GetCurrentProcess` at `0x18001234f`
- `KERNEL32!GetCurrentProcess` at `0x180012f32`
- `KERNEL32!lstrlenW` at `0x1800114b6`
- `KERNEL32!lstrlenW` at `0x1800114cb`
- `KERNEL32!lstrlenW` at `0x18001218b`
- `KERNEL32!lstrlenW` at `0x1800121a8`
- `KERNEL32!lstrlenW` at `0x1800114b6`
- `KERNEL32!lstrlenW` at `0x1800114cb`
- `KERNEL32!lstrlenW` at `0x18001218b`
- `KERNEL32!lstrlenW` at `0x1800121a8`
- `KERNEL32!GlobalFree` at `0x180011380`
- `KERNEL32!GlobalFree` at `0x180011648`
- `KERNEL32!GlobalFree` at `0x180011676`
- `KERNEL32!GlobalFree` at `0x180011b4c`
- `KERNEL32!GlobalFree` at `0x180011dd1`
- `KERNEL32!GlobalFree` at `0x180011dff`
- `KERNEL32!GlobalFree` at `0x1800120ff`
- `KERNEL32!GlobalFree` at `0x180012115`
- `KERNEL32!GlobalFree` at `0x1800121fc`
- `KERNEL32!GlobalFree` at `0x18001222a`
- `KERNEL32!GlobalFree` at `0x180012741`
- `KERNEL32!GlobalFree` at `0x18001276f`
- `KERNEL32!GlobalFree` at `0x1800127b4`
- `KERNEL32!GlobalFree` at `0x1800127e2`
- `KERNEL32!GlobalFree` at `0x180012fdf`
- `KERNEL32!GlobalFree` at `0x1800131b6`
- `KERNEL32!GlobalFree` at `0x1800131e4`
- `KERNEL32!GlobalFree` at `0x18001345a`
- `KERNEL32!GlobalFree` at `0x180013488`
- `KERNEL32!GlobalFree` at `0x180013561`
- `KERNEL32!GlobalFree` at `0x1800135a0`
- `KERNEL32!GlobalFree` at `0x1800136a6`
- `KERNEL32!GlobalFree` at `0x1800136ee`
- `KERNEL32!GlobalFree` at `0x1800137fa`
- `KERNEL32!GlobalFree` at `0x180013852`
- `KERNEL32!GlobalFree` at `0x180011380`
- `KERNEL32!GlobalFree` at `0x180011648`
- `KERNEL32!GlobalFree` at `0x180011676`
- `KERNEL32!GlobalFree` at `0x180011b4c`
- `KERNEL32!GlobalFree` at `0x180011dd1`
- `KERNEL32!GlobalFree` at `0x180011dff`
- `KERNEL32!GlobalFree` at `0x1800120ff`
- `KERNEL32!GlobalFree` at `0x180012115`
- `KERNEL32!GlobalFree` at `0x1800121fc`
- `KERNEL32!GlobalFree` at `0x18001222a`
- `KERNEL32!GlobalFree` at `0x180012741`
- `KERNEL32!GlobalFree` at `0x18001276f`
- `KERNEL32!GlobalFree` at `0x1800127b4`
- `KERNEL32!GlobalFree` at `0x1800127e2`
- `KERNEL32!GlobalFree` at `0x180012fdf`
- `KERNEL32!GlobalFree` at `0x1800131b6`
- `KERNEL32!GlobalFree` at `0x1800131e4`
- `KERNEL32!GlobalFree` at `0x18001345a`
- `KERNEL32!GlobalFree` at `0x180013488`
- `KERNEL32!GlobalFree` at `0x180013561`
- `KERNEL32!GlobalFree` at `0x1800135a0`
- `KERNEL32!GlobalFree` at `0x1800136a6`
- `KERNEL32!GlobalFree` at `0x1800136ee`
- `KERNEL32!GlobalFree` at `0x1800137fa`
- `KERNEL32!GlobalFree` at `0x180013852`
- `KERNEL32!LocalFree` at `0x180011af6`
- `KERNEL32!LocalFree` at `0x180011f5b`
- `KERNEL32!LocalFree` at `0x1800120c7`
- `KERNEL32!LocalFree` at `0x18001214d`
- `KERNEL32!LocalFree` at `0x180012b3b`
- `KERNEL32!LocalFree` at `0x180012e1d`

## string_xrefs

- `0x180011306`: `Software\Classes\Installer`
- `0x18001177b`: `Software\Microsoft\Windows\CurrentVersion\Installer\Managed`
- `0x180012dbc`: `Installer`
- `0x180013313`: `Software\Microsoft\Installer`

## pseudocode

```c
__int64 __fastcall OpenSpecificUsersAdvertisedSubKeyPacked(
        int a1,
        const wchar_t *a2,
        WCHAR *a3,
        const WCHAR *a4,
        struct _RTL_CRITICAL_SECTION *a5,
        char a6)
{
  const WCHAR *v6; // r12
  const wchar_t *v8; // r15
  const unsigned __int16 *v9; // r13
  __int64 v10; // r14
  const wchar_t *v11; // rdx
  __int64 v12; // rcx
  _WORD *v13; // r9
  __int64 v14; // r8
  _WORD *v15; // rax
  int v16; // esi
  __int64 v17; // r15
  __int64 v18; // rcx
  LPCWSTR v19; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rax
  WCHAR *v23; // rdx
  const unsigned __int16 *kk; // r8
  WCHAR *v25; // rax
  __int64 v26; // rcx
  LPCWSTR v27; // rax
  __int64 v28; // r9
  WCHAR *v29; // rcx
  __int64 v30; // rax
  __int64 mm; // r8
  WCHAR *v32; // rax
  int v33; // ebx
  int v34; // edi
  unsigned __int64 v35; // rbx
  const WCHAR *v36; // rsi
  WCHAR *v37; // rdx
  unsigned __int64 v38; // rax
  unsigned __int64 v39; // rcx
  const WCHAR *v40; // rax
  unsigned __int64 v41; // rdx
  WCHAR *v42; // rcx
  __int64 v43; // rax
  unsigned __int64 nn; // rbx
  WCHAR *v45; // rax
  __int64 v46; // rcx
  LPCWSTR v47; // rax
  __int64 v48; // r8
  WCHAR *v49; // rcx
  __int64 i1; // rdx
  WCHAR *v51; // rax
  _DWORD *v53; // rbx
  int v54; // eax
  unsigned int v55; // esi
  WCHAR *v56; // r9
  __int64 v57; // rcx
  const unsigned __int16 *v58; // r8
  __int64 v59; // rdx
  WCHAR *v60; // rax
  __int64 v61; // rcx
  LPCWSTR v62; // rax
  __int64 v63; // rax
  WCHAR *v64; // r8
  __int64 v65; // rcx
  const unsigned __int16 *v66; // rdx
  __int64 k; // r9
  WCHAR *v68; // rax
  int v69; // eax
  int v70; // ebx
  DWORD v71; // esi
  unsigned int v72; // eax
  unsigned int v73; // r14d
  unsigned int v74; // ecx
  int v75; // r15d
  unsigned int v76; // r8d
  unsigned int v77; // ecx
  struct IUnknownVtbl *v78; // rdx
  char v79; // bl
  int v80; // r12d
  int CurrentUserSID; // ebx
  LPWSTR v82; // r9
  __int64 v83; // rcx
  LPWSTR v84; // rax
  __int64 v85; // rdx
  int v86; // r10d
  wchar_t *v87; // r8
  __int64 v88; // rdx
  __int64 v89; // rcx
  wchar_t *v90; // rax
  _DWORD *v91; // rbx
  int v92; // eax
  unsigned int v93; // esi
  int v94; // eax
  char v95; // r14
  int v96; // ebx
  DWORD v97; // esi
  unsigned int v98; // eax
  unsigned int v99; // r14d
  unsigned int v100; // ecx
  int v101; // r15d
  unsigned int v102; // r8d
  unsigned int v103; // ecx
  struct IUnknownVtbl *lpVtbl; // rdx
  struct _RTL_CRITICAL_SECTION *v105; // r12
  const WCHAR *v106; // rdi
  __int64 v107; // r9
  unsigned int v108; // ebx
  int v109; // ebx
  LPWSTR v110; // r9
  __int64 v111; // rcx
  LPWSTR v112; // rax
  __int64 v113; // rdx
  int v114; // r10d
  _WORD *v115; // r8
  __int64 v116; // rdx
  __int64 v117; // rcx
  _WORD *v118; // rax
  WCHAR *v119; // r9
  __int64 v120; // rcx
  WCHAR *v121; // r8
  __int64 v122; // rdx
  WCHAR *v123; // rax
  DWORD v124; // edi
  unsigned int v125; // ecx
  void *v126; // rsi
  int v127; // ebx
  unsigned __int64 v128; // rbx
  __int64 v129; // rdx
  _OWORD *v130; // rcx
  wchar_t **v131; // rax
  __int64 v132; // rdx
  __int128 v133; // xmm0
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  _OWORD *v136; // rcx
  wchar_t **v137; // rax
  __int64 v138; // rdx
  __int128 v139; // xmm0
  BOOL v140; // ebx
  char *v141; // rdx
  unsigned int v142; // eax
  int v143; // ecx
  const WCHAR *v144; // rdx
  const WCHAR *v145; // rdx
  int v146; // ebx
  unsigned int v147; // r13d
  LPWSTR v148; // r9
  __int64 v149; // rcx
  LPWSTR v150; // rax
  int v151; // r12d
  __int64 v152; // rdx
  int v153; // r10d
  _WORD *v154; // r8
  __int64 v155; // rdx
  __int64 v156; // rcx
  _WORD *v157; // rax
  unsigned int v158; // ecx
  int v159; // ebx
  __int64 v160; // rcx
  LPCWSTR v161; // rax
  __int64 v162; // rax
  WCHAR *v163; // rdx
  __int64 v164; // rcx
  WCHAR *v165; // r8
  __int64 n; // r9
  WCHAR *v167; // rax
  __int64 v168; // rdx
  LPCWSTR v169; // rax
  __int64 v170; // r8
  WCHAR *v171; // rdx
  __int64 v172; // rax
  const unsigned __int16 *v173; // r9
  __int64 ii; // rcx
  WCHAR *v175; // rax
  __int64 v176; // rdx
  LPCWSTR v177; // rax
  __int64 v178; // rcx
  const unsigned __int16 *v179; // r9
  WCHAR *v180; // r8
  __int64 jj; // rax
  WCHAR *v182; // rax
  DWORD v183; // esi
  unsigned int v184; // ecx
  void *v185; // r14
  int v186; // ebx
  HANDLE v187; // rax
  HANDLE v188; // rax
  __int64 v189; // rdx
  LPCWSTR v190; // rax
  __int64 v191; // r9
  WCHAR *v192; // rdx
  __int64 v193; // rax
  __int64 m; // rcx
  WCHAR *v195; // rax
  BOOL v196; // ebx
  char *v197; // rdx
  unsigned int v198; // eax
  int v199; // ecx
  __int64 v200; // rcx
  LPCWSTR v201; // rax
  __int64 v202; // rdx
  __int64 v203; // rax
  __int64 v204; // rcx
  WCHAR *v205; // r8
  const unsigned __int16 *v206; // rdx
  __int64 i; // r9
  WCHAR *v208; // rax
  __int64 v209; // rdx
  LPCWSTR v210; // rax
  __int64 v211; // r8
  const wchar_t *v212; // r9
  WCHAR *v213; // rdx
  __int64 v214; // rax
  __int64 j; // rcx
  WCHAR *v216; // rax
  DWORD v217; // esi
  unsigned int Value; // ecx
  void *v219; // r14
  int v220; // ebx
  int v221; // ecx
  int v222; // ecx
  int v223; // r8d
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  int v225; // [rsp+68h] [rbp-98h] BYREF
  char v226; // [rsp+6Ch] [rbp-94h]
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  const WCHAR *v228; // [rsp+78h] [rbp-88h]
  struct _RTL_CRITICAL_SECTION *v229; // [rsp+80h] [rbp-80h]
  HGLOBAL hMem; // [rsp+90h] [rbp-70h] BYREF
  int v231; // [rsp+98h] [rbp-68h]
  int v232; // [rsp+9Ch] [rbp-64h]
  _BYTE v233[128]; // [rsp+A0h] [rbp-60h] BYREF
  PSID Sid[2]; // [rsp+120h] [rbp+20h] BYREF
  __int16 *v235; // [rsp+130h] [rbp+30h] BYREF
  int v236; // [rsp+138h] [rbp+38h]
  __int16 v237; // [rsp+140h] [rbp+40h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+148h] [rbp+48h] BYREF
  wchar_t *String2; // [rsp+180h] [rbp+80h] BYREF
  int v240; // [rsp+188h] [rbp+88h]
  int v241; // [rsp+18Ch] [rbp+8Ch]
  _BYTE v242[128]; // [rsp+190h] [rbp+90h] BYREF
  LPCWSTR lpString; // [rsp+210h] [rbp+110h]
  int v244; // [rsp+218h] [rbp+118h]
  _BYTE v245[528]; // [rsp+220h] [rbp+120h] BYREF

  v6 = a4;
  v229 = a5;
  lpString = (LPCWSTR)v245;
  hMem = v233;
  v228 = a4;
  v8 = a2;
  v244 = 260;
  v9 = L"\\";
  v231 = 64;
  if ( a1 == 2 )
  {
    v10 = 2147483646;
    v11 = L"Software\\Classes\\Installer";
    v12 = 2147483646;
    v13 = v245;
    v14 = 260;
    do
    {
      if ( !v12 )
        break;
      if ( !*v11 )
        break;
      *v13++ = *v11++;
      --v12;
      --v14;
    }
    while ( v14 );
    v15 = v13 - 1;
    if ( v14 )
      v15 = v13;
    v16 = 0;
    *v15 = 0;
    if ( v14 )
    {
      v17 = -2147483646;
      goto LABEL_10;
    }
LABEL_75:
    if ( v231 > 64 )
      GlobalFree(hMem);
    hMem = v233;
LABEL_78:
    v231 = 64;
    if ( v244 <= 260 )
      return 1627;
LABEL_79:
    GlobalFree((HGLOBAL)lpString);
    return 1627;
  }
  if ( a1 )
  {
    if ( a1 != 1 )
      return 2;
    v16 = 0;
    LOWORD(v80) = 14;
    if ( !a2 )
      goto LABEL_158;
    v240 = 64;
    String2 = (wchar_t *)v242;
    v241 = 64;
    Sid[0] = &v235;
    Sid[1] = (PSID)0x4800000048LL;
    CurrentUserSID = GetCurrentUserSID(Sid);
    if ( CurrentUserSID )
    {
LABEL_152:
      if ( SLODWORD(Sid[1]) > 72 )
        GlobalFree(Sid[0]);
      if ( CurrentUserSID || _wcsicmp(v8, String2) )
      {
        if ( v240 > 64 )
          GlobalFree(String2);
        if ( v231 > 64 )
LABEL_244:
          GlobalFree(hMem);
LABEL_245:
        hMem = v233;
        v231 = 64;
        if ( v244 > 260 )
LABEL_314:
          GlobalFree((HGLOBAL)lpString);
        return 2;
      }
      if ( v240 > 64 )
        GlobalFree(String2);
LABEL_158:
      EnterCriticalSection(&g_csPolicyTableLock);
      EnterCriticalSection(&g_csPolicyTableLock);
      if ( !g_pPolicyTable )
      {
        g_pPolicyTable = GlobalAlloc(0x40u, 0x4D8u);
        v136 = g_pPolicyTable;
        if ( !g_pPolicyTable )
        {
          LeaveCriticalSection(&g_csPolicyTableLock);
          goto LABEL_317;
        }
        v137 = &off_180267530;
        v138 = 9;
        do
        {
          v136 += 8;
          v139 = *(_OWORD *)v137;
          v137 += 16;
          *(v136 - 8) = v139;
          *(v136 - 7) = *((_OWORD *)v137 - 7);
          *(v136 - 6) = *((_OWORD *)v137 - 6);
          *(v136 - 5) = *((_OWORD *)v137 - 5);
          *(v136 - 4) = *((_OWORD *)v137 - 4);
          *(v136 - 3) = *((_OWORD *)v137 - 3);
          *(v136 - 2) = *((_OWORD *)v137 - 2);
          *(v136 - 1) = *((_OWORD *)v137 - 1);
          --v138;
        }
        while ( v138 );
        *v136 = *(_OWORD *)v137;
        v136[1] = *((_OWORD *)v137 + 1);
        v136[2] = *((_OWORD *)v137 + 2);
        v136[3] = *((_OWORD *)v137 + 3);
        v136[4] = *((_OWORD *)v137 + 4);
        *((_QWORD *)v136 + 10) = v137[10];
      }
      LeaveCriticalSection(&g_csPolicyTableLock);
      v91 = g_pPolicyTable;
      if ( *(_QWORD *)g_pPolicyTable )
      {
        v92 = *((_DWORD *)g_pPolicyTable + 6);
        if ( v92 != -1 )
        {
          if ( *((_QWORD *)g_pPolicyTable + 1) == 1 )
          {
            v93 = *((_DWORD *)g_pPolicyTable + 4);
            goto LABEL_163;
          }
          if ( v92 != -2 || PopulateDefaultValuesInPolicyTable() )
          {
            v93 = v91[6];
            v235 = &v237;
            *(_OWORD *)Sid = 0;
            v237 = 0;
            v236 = 1;
            InitializeCriticalSection(&CriticalSection);
            EnterCriticalSection(&CriticalSection);
            if ( Sid[0] )
            {
              RegCloseKey((HKEY)Sid[0]);
              Sid[0] = 0;
              *v235 = 0;
            }
            LeaveCriticalSection(&CriticalSection);
            if ( !OpenPolicyKey((HKEY *)Sid, 1) )
            {
              v145 = *(const WCHAR **)v91;
              String2 = (wchar_t *)v242;
              v240 = 40;
              v241 = 40;
              if ( !(unsigned int)MsiRegQueryValueExW((HKEY)Sid[0], v145, (__int64)&String2, 0)
                && *(_DWORD *)String2 >= v91[7]
                && *(_DWORD *)String2 <= v91[8] )
              {
                v93 = *(_DWORD *)String2;
              }
              if ( v240 > 40 )
                GlobalFree(String2);
              v240 = 40;
              String2 = (wchar_t *)v242;
            }
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                L"%s policy value '%s' is %u",
                L"Machine",
                *(const unsigned __int16 **)v91,
                (const unsigned __int16 *)v93,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            *((_QWORD *)v91 + 2) = v93;
            *((_QWORD *)v91 + 1) = 1;
            CRegHandle::~CRegHandle((CRegHandle *)Sid);
LABEL_163:
            LeaveCriticalSection(&g_csPolicyTableLock);
            if ( !v93 )
            {
              v16 = 0;
              goto LABEL_165;
            }
            if ( v231 > 64 )
              goto LABEL_244;
            goto LABEL_245;
          }
        }
      }
LABEL_317:
      LeaveCriticalSection(&g_csPolicyTableLock);
LABEL_165:
      v94 = dword_180310D00;
      v225 = 0;
      if ( dword_180310D00 == -1 )
      {
        StringSid = (LPWSTR)-1LL;
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 4u, 1, (PHANDLE)&StringSid) )
        {
          if ( !SetThreadToken(0, 0) )
            ExitProcessIfNotClient();
        }
        else
        {
          StringSid = (LPWSTR)-1LL;
        }
        TokenHandle = 0;
        CurrentProcess = GetCurrentProcess();
        if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
        {
          v140 = IsLocalSystemToken(TokenHandle);
          CloseHandle(TokenHandle);
          dword_180310D00 = v140;
        }
        else if ( g_dmDiagnosticMode )
        {
          DebugString(
            9,
            0,
            0,
            L"Could not determine if the process is running as local system or not.",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        if ( StringSid != (LPWSTR)-1LL )
        {
          if ( !SetThreadToken(0, StringSid) )
            ExitProcessIfNotClient();
          CloseHandle(StringSid);
        }
        v94 = dword_180310D00;
      }
      if ( g_scServerContext != 2 && !v94 )
      {
        v95 = 0;
        v226 = 0;
LABEL_198:
        v232 = 64;
        Sid[0] = &v235;
        Sid[1] = (PSID)0x4800000048LL;
        v108 = GetCurrentUserSID(Sid);
        if ( v108 )
          goto LABEL_218;
        StringSid = 0;
        if ( !ConvertSidToStringSidW(Sid[0], &StringSid) )
        {
          v108 = 1627;
LABEL_218:
          if ( SLODWORD(Sid[1]) > 72 )
            GlobalFree(Sid[0]);
          if ( v108 )
          {
            CImpersonate::~CImpersonate((CImpersonate *)&v225);
            if ( v231 <= 64 )
              goto LABEL_189;
            goto LABEL_188;
          }
          v119 = (WCHAR *)lpString;
          v120 = v244;
          if ( v244 )
          {
            if ( (unsigned __int64)v244 > 0x7FFFFFFF )
            {
              *lpString = 0;
            }
            else
            {
              v121 = (WCHAR *)hMem;
              v122 = 2147483646;
              do
              {
                if ( !v122 )
                  break;
                if ( !*v121 )
                  break;
                *v119++ = *v121++;
                --v122;
                --v120;
              }
              while ( v120 );
              v123 = v119 - 1;
              if ( v120 )
                v123 = v119;
              *v123 = 0;
              if ( v120 && v244 && (unsigned __int64)v244 <= 0x7FFFFFFF )
              {
                v200 = v244;
                v201 = lpString;
                do
                {
                  if ( !*v201 )
                    break;
                  ++v201;
                  --v200;
                }
                while ( v200 );
                v202 = v244 - v200;
                if ( v200 )
                {
                  v203 = v244 - v200;
                  v9 = L"\\";
                  v204 = 2147483646;
                  v205 = (WCHAR *)&lpString[v202];
                  v206 = L"\\";
                  for ( i = v244 - v203; i; --i )
                  {
                    if ( !v204 )
                      break;
                    if ( !*v206 )
                      break;
                    *v205++ = *v206++;
                    --v204;
                  }
                  v208 = v205 - 1;
                  if ( i )
                    v208 = v205;
                  *v208 = 0;
                  if ( i )
                  {
                    if ( !v95 )
                    {
LABEL_493:
                      if ( v244 && (unsigned __int64)v244 <= 0x7FFFFFFF )
                      {
                        v209 = v244;
                        v210 = lpString;
                        do
                        {
                          if ( !*v210 )
                            break;
                          ++v210;
                          --v209;
                        }
                        while ( v209 );
                        if ( v209 )
                        {
                          v211 = v244 - v209;
                          v212 = L"Software\\Microsoft\\Installer";
                          v10 = 2147483646;
                          v213 = (WCHAR *)&lpString[v211];
                          v214 = 2147483646;
                          for ( j = v244 - v211; j; --j )
                          {
                            if ( !v214 )
                              break;
                            if ( !*v212 )
                              break;
                            *v213++ = *v212++;
                            --v214;
                          }
                          v216 = v213 - 1;
                          if ( j )
                            v216 = v213;
                          *v216 = 0;
                          if ( j )
                          {
                            v6 = v228;
                            v17 = -2147483645;
                            goto LABEL_10;
                          }
                        }
                      }
                      if ( v231 > 64 )
LABEL_440:
                        GlobalFree(hMem);
LABEL_441:
                      hMem = v233;
                      v231 = 64;
                      if ( v244 <= 260 )
                        return 1627;
                      goto LABEL_79;
                    }
                    EnterCriticalSection(&g_csImpersonationLock);
                    v217 = g_dwImpersonationSlot;
                    LeaveCriticalSection(&g_csImpersonationLock);
                    if ( v217 != -1 )
                    {
                      Value = (unsigned int)TlsGetValue(g_dwImpersonationSlot);
                      if ( (Value & 0xE0000000) != 0x80000000 )
                      {
                        v219 = (void *)Value;
                        v220 = Value & 0x1FFFFFFF;
                        if ( TlsSetValue(
                               v217,
                               (LPVOID)(Value & 0xE0000000 | (unsigned __int64)(((Value & 0x1FFFFFFF) - 1) & 0x1FFFFFFF))) )
                        {
                          if ( v220 != 1 || SetThreadToken(0, 0) )
                            goto LABEL_513;
                          TlsSetValue(v217, v219);
                        }
                        ExitProcessIfNotClient();
                      }
                    }
LABEL_513:
                    v16 = 0;
                    goto LABEL_493;
                  }
                }
              }
            }
          }
          if ( !v95 )
            goto LABEL_75;
          EnterCriticalSection(&g_csImpersonationLock);
          v124 = g_dwImpersonationSlot;
          LeaveCriticalSection(&g_csImpersonationLock);
          if ( v124 == -1 )
            goto LABEL_75;
          v125 = (unsigned int)TlsGetValue(g_dwImpersonationSlot);
          if ( (v125 & 0xE0000000) == 0x80000000 )
            goto LABEL_75;
          v126 = (void *)v125;
          v127 = v125 & 0x1FFFFFFF;
          if ( !TlsSetValue(
                  v124,
                  (LPVOID)(v125 & 0xE0000000 | (unsigned __int64)(((v125 & 0x1FFFFFFF) - 1) & 0x1FFFFFFF))) )
            goto LABEL_238;
          if ( v127 != 1 || SetThreadToken(0, 0) )
            goto LABEL_75;
LABEL_237:
          TlsSetValue(v124, v126);
LABEL_238:
          ExitProcessIfNotClient();
          goto LABEL_75;
        }
        v110 = StringSid;
        if ( !StringSid )
          goto LABEL_239;
        v111 = 0x7FFFFFFF;
        v112 = StringSid;
        do
        {
          if ( !*v112 )
            break;
          ++v112;
          --v111;
        }
        while ( v111 );
        v113 = 0x7FFFFFFF - v111;
        if ( v111 )
        {
          v114 = v231;
          if ( v231 >= (unsigned __int64)(v113 + 1) )
            goto LABEL_206;
          if ( (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(&hMem, (unsigned int)(v113 + 1), 0) )
          {
            v114 = v231;
            v110 = StringSid;
LABEL_206:
            v115 = hMem;
            v116 = v114;
            if ( v114 )
            {
              if ( (unsigned __int64)v114 > 0x7FFFFFFF )
              {
                v80 = -2147024809;
                *(_WORD *)hMem = 0;
              }
              else
              {
                v117 = 2147483646;
                do
                {
                  if ( !v117 )
                    break;
                  if ( !*v110 )
                    break;
                  *v115++ = *v110++;
                  --v117;
                  --v116;
                }
                while ( v116 );
                v118 = v115 - 1;
                v80 = -2147024774;
                if ( v116 )
                {
                  v118 = v115;
                  v80 = 0;
                }
                *v118 = 0;
              }
              v110 = StringSid;
            }
            else
            {
              v80 = -2147024809;
            }
            LocalFree(v110);
            if ( v80 >= 0 )
            {
              v108 = 0;
              goto LABEL_218;
            }
            goto LABEL_240;
          }
          LocalFree(StringSid);
        }
        else
        {
LABEL_239:
          LOWORD(v80) = 87;
          LocalFree(StringSid);
        }
LABEL_240:
        v108 = (unsigned __int16)v80;
        goto LABEL_218;
      }
      v95 = 0;
      v226 = 0;
      v96 = (g_scServerContext == 3) + 2;
      EnterCriticalSection(&g_csImpersonationLock);
      v97 = g_dwImpersonationSlot;
      if ( g_dwImpersonationSlot == -1 )
      {
        g_dwImpersonationSlot = TlsAlloc();
        v97 = g_dwImpersonationSlot;
        if ( g_dwImpersonationSlot == -1 )
        {
          LeaveCriticalSection(&g_csImpersonationLock);
          ExitProcessIfNotClient();
          goto LABEL_197;
        }
      }
      LeaveCriticalSection(&g_csImpersonationLock);
      v98 = (unsigned int)TlsGetValue(v97);
      v99 = v98;
      v100 = v98 >> 29;
      if ( v98 >> 29 == 4 )
        goto LABEL_196;
      v101 = v98 & 0x1FFFFFFF;
      if ( g_scServerContext == 3 && v96 == 2 )
        v96 = 3;
      v102 = v98;
      if ( v100 )
      {
        v103 = v100 - 1;
        if ( v103 )
        {
          if ( v103 == 2 )
            v96 = 3;
        }
        else
        {
          v96 = 1;
        }
      }
      else
      {
        v102 = v96 << 29;
        v101 = 0;
      }
      if ( !TlsSetValue(v97, (LPVOID)(v102 & 0xE0000000 | (unsigned __int64)((v101 + 1) & 0x1FFFFFFF))) )
        goto LABEL_195;
      if ( v96 == 2 )
      {
        lpVtbl = (struct IUnknownVtbl *)Token;
        if ( Token )
          goto LABEL_180;
        if ( g_scServerContext == 2 )
        {
          if ( !CMsiTransaction::m_pMsiTransaction )
            goto LABEL_194;
          lpVtbl = CMsiTransaction::m_pMsiTransaction[5].lpVtbl;
        }
        if ( lpVtbl )
        {
LABEL_180:
          if ( SetThreadToken(0, lpVtbl) )
          {
LABEL_181:
            v95 = 1;
            v226 = 1;
LABEL_182:
            v225 = v101;
LABEL_197:
            v16 = 0;
            goto LABEL_198;
          }
          goto LABEL_194;
        }
        if ( g_scServerContext != 2 )
        {
          v95 = 0;
          goto LABEL_182;
        }
LABEL_194:
        TlsSetValue(v97, (LPVOID)v99);
LABEL_195:
        ExitProcessIfNotClient();
LABEL_196:
        v95 = 0;
        goto LABEL_197;
      }
      v109 = v96 - 1;
      if ( !v109 )
      {
        if ( !(unsigned int)OLE32::CoImpersonateClient() )
          goto LABEL_181;
        goto LABEL_194;
      }
      if ( v109 != 2 )
        goto LABEL_194;
      v141 = (char *)*((_QWORD *)g_pCustomActionContext + 15);
      if ( (unsigned __int64)(v141 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        if ( SetThreadToken(0, v141) )
          goto LABEL_181;
        goto LABEL_194;
      }
      v142 = *((_DWORD *)g_pCustomActionContext + 25);
      if ( g_fWoW )
      {
        if ( v142 <= 9 )
        {
          v143 = 642;
          if ( _bittest(&v143, v142) )
            goto LABEL_327;
        }
      }
      else if ( v142 <= 8 )
      {
        v222 = 321;
        if ( _bittest(&v222, v142) )
          goto LABEL_327;
      }
      ExitProcessIfNotClient();
LABEL_327:
      TlsSetValue(v97, (LPVOID)v99);
      goto LABEL_196;
    }
    StringSid = 0;
    if ( !ConvertSidToStringSidW(Sid[0], &StringSid) )
    {
      CurrentUserSID = 1627;
      goto LABEL_152;
    }
    v82 = StringSid;
    if ( StringSid )
    {
      v83 = 0x7FFFFFFF;
      v84 = StringSid;
      do
      {
        if ( !*v84 )
          break;
        ++v84;
        --v83;
      }
      while ( v83 );
      LOWORD(CurrentUserSID) = 87;
      v85 = 0x7FFFFFFF - v83;
      if ( v83 )
      {
        v86 = v240;
        if ( v240 < (unsigned __int64)(v85 + 1) )
        {
          if ( !(unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(&String2, (unsigned int)(v85 + 1), 0) )
          {
            LOWORD(CurrentUserSID) = 14;
            LocalFree(StringSid);
            goto LABEL_249;
          }
          v86 = v240;
          v82 = StringSid;
        }
        v87 = String2;
        v88 = v86;
        if ( v86 )
        {
          if ( (unsigned __int64)v86 > 0x7FFFFFFF )
          {
            CurrentUserSID = -2147024809;
            *String2 = 0;
          }
          else
          {
            v89 = 2147483646;
            do
            {
              if ( !v89 )
                break;
              if ( !*v82 )
                break;
              *v87++ = *v82++;
              --v89;
              --v88;
            }
            while ( v88 );
            v90 = v87 - 1;
            CurrentUserSID = -2147024774;
            if ( v88 )
            {
              v90 = v87;
              CurrentUserSID = 0;
            }
            *v90 = 0;
          }
          v82 = StringSid;
        }
        else
        {
          CurrentUserSID = -2147024809;
        }
        LocalFree(v82);
        if ( CurrentUserSID >= 0 )
        {
          CurrentUserSID = 0;
          goto LABEL_152;
        }
LABEL_249:
        CurrentUserSID = (unsigned __int16)CurrentUserSID;
        goto LABEL_152;
      }
    }
    else
    {
      LOWORD(CurrentUserSID) = 87;
    }
    LocalFree(StringSid);
    goto LABEL_249;
  }
  EnterCriticalSection(&g_csPolicyTableLock);
  EnterCriticalSection(&g_csPolicyTableLock);
  v16 = 0;
  if ( !g_pPolicyTable )
  {
    g_pPolicyTable = GlobalAlloc(0x40u, 0x4D8u);
    v130 = g_pPolicyTable;
    if ( !g_pPolicyTable )
    {
      LeaveCriticalSection(&g_csPolicyTableLock);
      goto LABEL_310;
    }
    v131 = &off_180267530;
    v132 = 9;
    do
    {
      v130 += 8;
      v133 = *(_OWORD *)v131;
      v131 += 16;
      *(v130 - 8) = v133;
      *(v130 - 7) = *((_OWORD *)v131 - 7);
      *(v130 - 6) = *((_OWORD *)v131 - 6);
      *(v130 - 5) = *((_OWORD *)v131 - 5);
      *(v130 - 4) = *((_OWORD *)v131 - 4);
      *(v130 - 3) = *((_OWORD *)v131 - 3);
      *(v130 - 2) = *((_OWORD *)v131 - 2);
      *(v130 - 1) = *((_OWORD *)v131 - 1);
      --v132;
    }
    while ( v132 );
    *v130 = *(_OWORD *)v131;
    v130[1] = *((_OWORD *)v131 + 1);
    v130[2] = *((_OWORD *)v131 + 2);
    v130[3] = *((_OWORD *)v131 + 3);
    v130[4] = *((_OWORD *)v131 + 4);
    *((_QWORD *)v130 + 10) = v131[10];
  }
  LeaveCriticalSection(&g_csPolicyTableLock);
  v53 = g_pPolicyTable;
  if ( *(_QWORD *)g_pPolicyTable )
  {
    v54 = *((_DWORD *)g_pPolicyTable + 6);
    if ( v54 != -1 )
    {
      if ( *((_QWORD *)g_pPolicyTable + 1) == 1 )
      {
        v55 = *((_DWORD *)g_pPolicyTable + 4);
        goto LABEL_87;
      }
      if ( v54 != -2 || PopulateDefaultValuesInPolicyTable() )
      {
        v55 = v53[6];
        v235 = &v237;
        *(_OWORD *)Sid = 0;
        v237 = 0;
        v236 = 1;
        InitializeCriticalSection(&CriticalSection);
        EnterCriticalSection(&CriticalSection);
        if ( Sid[0] )
        {
          RegCloseKey((HKEY)Sid[0]);
          Sid[0] = 0;
          *v235 = 0;
        }
        LeaveCriticalSection(&CriticalSection);
        if ( !OpenPolicyKey((HKEY *)Sid, 1) )
        {
          v144 = *(const WCHAR **)v53;
          String2 = (wchar_t *)v242;
          v240 = 40;
          v241 = 40;
          if ( !(unsigned int)MsiRegQueryValueExW((HKEY)Sid[0], v144, (__int64)&String2, 0)
            && *(_DWORD *)String2 >= v53[7]
            && *(_DWORD *)String2 <= v53[8] )
          {
            v55 = *(_DWORD *)String2;
          }
          if ( v240 > 40 )
            GlobalFree(String2);
          v240 = 40;
          String2 = (wchar_t *)v242;
        }
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"%s policy value '%s' is %u",
            L"Machine",
            *(const unsigned __int16 **)v53,
            (const unsigned __int16 *)v55,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        *((_QWORD *)v53 + 2) = v55;
        *((_QWORD *)v53 + 1) = 1;
        CRegHandle::~CRegHandle((CRegHandle *)Sid);
LABEL_87:
        LeaveCriticalSection(&g_csPolicyTableLock);
        if ( !v55 )
        {
          v16 = 0;
          goto LABEL_89;
        }
        if ( v231 > 64 )
          GlobalFree(hMem);
        hMem = v233;
        v231 = 64;
        if ( v244 > 260 )
          goto LABEL_314;
        return 2;
      }
    }
  }
LABEL_310:
  LeaveCriticalSection(&g_csPolicyTableLock);
LABEL_89:
  v56 = (WCHAR *)lpString;
  v57 = v244;
  if ( !v244 )
    goto LABEL_75;
  if ( (unsigned __int64)v244 > 0x7FFFFFFF )
  {
    *lpString = 0;
    goto LABEL_75;
  }
  v10 = 2147483646;
  v58 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\Managed";
  v59 = 2147483646;
  do
  {
    if ( !v59 )
      break;
    if ( !*v58 )
      break;
    *v56++ = *v58++;
    --v59;
    --v57;
  }
  while ( v57 );
  v60 = v56 - 1;
  if ( v57 )
    v60 = v56;
  *v60 = 0;
  if ( !v57 || !v244 || (unsigned __int64)v244 > 0x7FFFFFFF )
    goto LABEL_75;
  v61 = v244;
  v62 = lpString;
  do
  {
    if ( !*v62 )
      break;
    ++v62;
    --v61;
  }
  while ( v61 );
  if ( !v61 )
    goto LABEL_75;
  v63 = v244 - v61;
  v64 = (WCHAR *)&lpString[v63];
  v65 = 2147483646;
  v66 = L"\\";
  for ( k = v244 - v63; k; --k )
  {
    if ( !v65 )
      break;
    if ( !*v66 )
      break;
    *v64++ = *v66++;
    --v65;
  }
  v68 = v64 - 1;
  if ( k )
    v68 = v64;
  *v68 = 0;
  if ( !k )
    goto LABEL_75;
  if ( v8 )
  {
    if ( v244 && (unsigned __int64)v244 <= 0x7FFFFFFF )
    {
      v189 = v244;
      v190 = lpString;
      do
      {
        if ( !*v190 )
          break;
        ++v190;
        --v189;
      }
      while ( v189 );
      v191 = v244 - v189;
      if ( v189 )
      {
        v192 = (WCHAR *)&lpString[v191];
        v193 = 2147483646;
        for ( m = v244 - v191; m; --m )
        {
          if ( !v193 )
            break;
          if ( !*v8 )
            break;
          *v192++ = *v8++;
          --v193;
        }
        v195 = v192 - 1;
        if ( m )
          v195 = v192;
        *v195 = 0;
        if ( m )
          goto LABEL_392;
      }
    }
    if ( v231 > 64 )
      goto LABEL_440;
    goto LABEL_441;
  }
  v69 = dword_180310D00;
  v225 = 0;
  if ( dword_180310D00 == -1 )
  {
    StringSid = (LPWSTR)-1LL;
    v187 = GetCurrentThread();
    if ( OpenThreadToken(v187, 4u, 1, (PHANDLE)&StringSid) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      StringSid = (LPWSTR)-1LL;
    }
    TokenHandle = 0;
    v188 = GetCurrentProcess();
    if ( OpenProcessToken(v188, 8u, &TokenHandle) )
    {
      v196 = IsLocalSystemToken(TokenHandle);
      CloseHandle(TokenHandle);
      dword_180310D00 = v196;
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"Could not determine if the process is running as local system or not.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( StringSid != (LPWSTR)-1LL )
    {
      if ( !SetThreadToken(0, StringSid) )
        ExitProcessIfNotClient();
      CloseHandle(StringSid);
    }
    v69 = dword_180310D00;
  }
  if ( g_scServerContext == 2 || v69 )
  {
    v226 = 0;
    v70 = (g_scServerContext == 3) + 2;
    EnterCriticalSection(&g_csImpersonationLock);
    v71 = g_dwImpersonationSlot;
    if ( g_dwImpersonationSlot == -1 )
    {
      g_dwImpersonationSlot = TlsAlloc();
      v71 = g_dwImpersonationSlot;
      if ( g_dwImpersonationSlot == -1 )
      {
        LeaveCriticalSection(&g_csImpersonationLock);
        ExitProcessIfNotClient();
        goto LABEL_345;
      }
    }
    LeaveCriticalSection(&g_csImpersonationLock);
    v72 = (unsigned int)TlsGetValue(v71);
    v73 = v72;
    v74 = v72 >> 29;
    if ( v72 >> 29 == 4 )
    {
LABEL_344:
      v10 = 2147483646;
LABEL_345:
      v79 = 0;
      goto LABEL_346;
    }
    v75 = v72 & 0x1FFFFFFF;
    if ( g_scServerContext == 3 && v70 == 2 )
      v70 = 3;
    v76 = v72;
    if ( v74 )
    {
      v77 = v74 - 1;
      if ( v77 )
      {
        if ( v77 == 2 )
          v70 = 3;
      }
      else
      {
        v70 = 1;
      }
    }
    else
    {
      v76 = v70 << 29;
      v75 = 0;
    }
    if ( !TlsSetValue(v71, (LPVOID)(v76 & 0xE0000000 | (unsigned __int64)((v75 + 1) & 0x1FFFFFFF))) )
    {
LABEL_343:
      ExitProcessIfNotClient();
      goto LABEL_344;
    }
    if ( v70 == 2 )
    {
      v78 = (struct IUnknownVtbl *)Token;
      if ( Token )
        goto LABEL_127;
      if ( g_scServerContext == 2 )
      {
        if ( !CMsiTransaction::m_pMsiTransaction )
          goto LABEL_342;
        v78 = CMsiTransaction::m_pMsiTransaction[5].lpVtbl;
      }
      if ( v78 )
      {
LABEL_127:
        if ( SetThreadToken(0, v78) )
        {
LABEL_128:
          v79 = 1;
          v226 = 1;
LABEL_129:
          v225 = v75;
          v10 = 2147483646;
LABEL_346:
          v16 = 0;
          goto LABEL_347;
        }
        goto LABEL_342;
      }
      if ( g_scServerContext != 2 )
      {
        v79 = 0;
        goto LABEL_129;
      }
LABEL_342:
      TlsSetValue(v71, (LPVOID)v73);
      goto LABEL_343;
    }
    v146 = v70 - 1;
    if ( !v146 )
    {
      if ( !(unsigned int)OLE32::CoImpersonateClient() )
        goto LABEL_128;
      goto LABEL_342;
    }
    if ( v146 != 2 )
      goto LABEL_342;
    v197 = (char *)*((_QWORD *)g_pCustomActionContext + 15);
    if ( (unsigned __int64)(v197 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( SetThreadToken(0, v197) )
        goto LABEL_128;
      goto LABEL_342;
    }
    v198 = *((_DWORD *)g_pCustomActionContext + 25);
    if ( g_fWoW )
    {
      if ( v198 <= 9 )
      {
        v199 = 642;
        if ( _bittest(&v199, v198) )
          goto LABEL_470;
      }
    }
    else if ( v198 <= 8 )
    {
      v221 = 321;
      if ( _bittest(&v221, v198) )
        goto LABEL_470;
    }
    ExitProcessIfNotClient();
LABEL_470:
    TlsSetValue(v71, (LPVOID)v73);
    goto LABEL_344;
  }
  v79 = 0;
  v226 = 0;
LABEL_347:
  v232 = 64;
  Sid[0] = &v235;
  Sid[1] = (PSID)0x4800000048LL;
  v147 = GetCurrentUserSID(Sid);
  if ( v147 )
    goto LABEL_367;
  StringSid = 0;
  if ( ConvertSidToStringSidW(Sid[0], &StringSid) )
  {
    v148 = StringSid;
    if ( StringSid )
    {
      v149 = 0x7FFFFFFF;
      v150 = StringSid;
      do
      {
        if ( !*v150 )
          break;
        ++v150;
        --v149;
      }
      while ( v149 );
      LOWORD(v151) = 87;
      v152 = 0x7FFFFFFF - v149;
      if ( v149 )
      {
        v153 = v231;
        if ( v231 >= (unsigned __int64)(v152 + 1) )
          goto LABEL_355;
        if ( (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(&hMem, (unsigned int)(v152 + 1), 0) )
        {
          v153 = v231;
          v148 = StringSid;
LABEL_355:
          v154 = hMem;
          v155 = v153;
          if ( v153 )
          {
            if ( (unsigned __int64)v153 > 0x7FFFFFFF )
            {
              v151 = -2147024809;
              *(_WORD *)hMem = 0;
            }
            else
            {
              v156 = 2147483646;
              do
              {
                if ( !v156 )
                  break;
                if ( !*v148 )
                  break;
                *v154++ = *v148++;
                --v156;
                --v155;
              }
              while ( v155 );
              v157 = v154 - 1;
              v151 = -2147024774;
              if ( v155 )
              {
                v157 = v154;
                v151 = 0;
              }
              *v157 = 0;
            }
            v148 = StringSid;
          }
          else
          {
            v151 = -2147024809;
          }
          LocalFree(v148);
          if ( v151 >= 0 )
          {
            v147 = 0;
            goto LABEL_367;
          }
          goto LABEL_421;
        }
        LOWORD(v151) = 14;
        LocalFree(StringSid);
LABEL_421:
        v147 = (unsigned __int16)v151;
        goto LABEL_367;
      }
    }
    else
    {
      LOWORD(v151) = 87;
    }
    LocalFree(StringSid);
    goto LABEL_421;
  }
  v147 = 1627;
LABEL_367:
  if ( SLODWORD(Sid[1]) > 72 )
    GlobalFree(Sid[0]);
  if ( v147 )
  {
    CImpersonate::~CImpersonate((CImpersonate *)&v225);
    if ( v231 > 64 )
      GlobalFree(hMem);
    hMem = v233;
    v231 = 64;
    if ( v244 > 260 )
      GlobalFree((HGLOBAL)lpString);
    return v147;
  }
  if ( !v244 || (unsigned __int64)v244 > 0x7FFFFFFF )
    goto LABEL_584;
  v160 = v244;
  v161 = lpString;
  do
  {
    if ( !*v161 )
      break;
    ++v161;
    --v160;
  }
  while ( v160 );
  if ( !v160 )
    goto LABEL_584;
  v162 = v244 - v160;
  v163 = (WCHAR *)hMem;
  v164 = 2147483646;
  v165 = (WCHAR *)&lpString[v162];
  for ( n = v244 - v162; n; --n )
  {
    if ( !v164 )
      break;
    if ( !*v163 )
      break;
    *v165++ = *v163++;
    --v164;
  }
  v167 = v165 - 1;
  if ( n )
    v167 = v165;
  *v167 = 0;
  if ( !n )
  {
LABEL_584:
    if ( !v79 )
      goto LABEL_75;
    EnterCriticalSection(&g_csImpersonationLock);
    v124 = g_dwImpersonationSlot;
    LeaveCriticalSection(&g_csImpersonationLock);
    if ( v124 == -1 )
      goto LABEL_75;
    v158 = (unsigned int)TlsGetValue(g_dwImpersonationSlot);
    if ( (v158 & 0xE0000000) == 0x80000000 )
      goto LABEL_75;
    v126 = (void *)v158;
    v159 = v158 & 0x1FFFFFFF;
    if ( !TlsSetValue(v124, (LPVOID)(v158 & 0xE0000000 | (unsigned __int64)(((v158 & 0x1FFFFFFF) - 1) & 0x1FFFFFFF))) )
      goto LABEL_238;
    if ( v159 != 1 || SetThreadToken(0, 0) )
      goto LABEL_75;
    goto LABEL_237;
  }
  if ( v79 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    v183 = g_dwImpersonationSlot;
    LeaveCriticalSection(&g_csImpersonationLock);
    if ( v183 == -1 )
      goto LABEL_428;
    v184 = (unsigned int)TlsGetValue(g_dwImpersonationSlot);
    if ( (v184 & 0xE0000000) == 0x80000000 )
      goto LABEL_428;
    v185 = (void *)v184;
    v186 = v184 & 0x1FFFFFFF;
    if ( TlsSetValue(v183, (LPVOID)(v184 & 0xE0000000 | (unsigned __int64)(((v184 & 0x1FFFFFFF) - 1) & 0x1FFFFFFF))) )
    {
      if ( v186 != 1 || SetThreadToken(0, 0) )
        goto LABEL_427;
      TlsSetValue(v183, v185);
    }
    ExitProcessIfNotClient();
LABEL_427:
    v10 = 2147483646;
LABEL_428:
    v16 = 0;
  }
  v9 = L"\\";
LABEL_392:
  if ( !v244 || (unsigned __int64)v244 > 0x7FFFFFFF )
    goto LABEL_75;
  v168 = v244;
  v169 = lpString;
  do
  {
    if ( !*v169 )
      break;
    ++v169;
    --v168;
  }
  while ( v168 );
  if ( !v168 )
    goto LABEL_75;
  v170 = v244 - v168;
  v171 = (WCHAR *)&lpString[v170];
  v172 = 2147483646;
  v173 = L"\\";
  for ( ii = v244 - v170; ii; --ii )
  {
    if ( !v172 )
      break;
    if ( !*v173 )
      break;
    *v171++ = *v173++;
    --v172;
  }
  v175 = v171 - 1;
  if ( ii )
    v175 = v171;
  *v175 = 0;
  if ( !ii || !v244 || (unsigned __int64)v244 > 0x7FFFFFFF )
    goto LABEL_75;
  v176 = v244;
  v177 = lpString;
  do
  {
    if ( !*v177 )
      break;
    ++v177;
    --v176;
  }
  while ( v176 );
  if ( !v176 )
    goto LABEL_75;
  v178 = v244 - (v244 - v176);
  v179 = L"Installer";
  v180 = (WCHAR *)&lpString[v244 - v176];
  v17 = -2147483646;
  for ( jj = 2147483646; v178; --v178 )
  {
    if ( !jj )
      break;
    if ( !*v179 )
      break;
    *v180++ = *v179++;
    --jj;
  }
  v182 = v180 - 1;
  if ( v178 )
    v182 = v180;
  *v182 = 0;
  if ( !v178 )
    goto LABEL_75;
  v6 = v228;
LABEL_10:
  if ( a3 )
  {
    if ( !v244 || (unsigned __int64)v244 > 0x7FFFFFFF )
      goto LABEL_12;
    v18 = v244;
    v19 = lpString;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v18;
    }
    while ( v18 );
    v20 = v244 - v18;
    if ( !v18 )
      goto LABEL_12;
    v21 = v244 - v20;
    v22 = 2147483646;
    v23 = (WCHAR *)&lpString[v20];
    for ( kk = L"\\"; v21; --v21 )
    {
      if ( !v22 )
        break;
      if ( !*kk )
        break;
      *v23++ = *kk++;
      --v22;
    }
    v25 = v23 - 1;
    if ( v21 )
      v25 = v23;
    *v25 = 0;
    if ( !v21 || !v244 || (unsigned __int64)v244 > 0x7FFFFFFF )
      goto LABEL_12;
    v26 = v244;
    v27 = lpString;
    do
    {
      if ( !*v27 )
        break;
      ++v27;
      --v26;
    }
    while ( v26 );
    v28 = v244 - v26;
    if ( !v26 )
      goto LABEL_12;
    v29 = (WCHAR *)&lpString[v28];
    v30 = 2147483646;
    for ( mm = v244 - v28; mm; --mm )
    {
      if ( !v30 )
        break;
      if ( !*a3 )
        break;
      *v29++ = *a3++;
      --v30;
    }
    v32 = v29 - 1;
    if ( mm )
      v32 = v29;
    *v32 = 0;
    if ( !mm )
    {
LABEL_12:
      if ( v231 > 64 )
        GlobalFree(hMem);
      hMem = v233;
      goto LABEL_78;
    }
    if ( v6 )
    {
      v33 = lstrlenW(v6);
      v34 = v33 + lstrlenW(lpString) + 2;
      v35 = v34;
      if ( v34 > 260 )
      {
        v36 = (const WCHAR *)GlobalAlloc(0x40u, 2LL * v34);
        if ( !v36 )
        {
          if ( v231 > 64 )
            GlobalFree(hMem);
          hMem = v233;
          v231 = 64;
          if ( v244 > 260 )
            GlobalFree((HGLOBAL)lpString);
          return 14;
        }
      }
      else
      {
        v36 = (const WCHAR *)v245;
      }
      v37 = (WCHAR *)lpString;
      if ( lpString == v36 )
        goto LABEL_44;
      v223 = v244;
      if ( v34 < v244 )
        v223 = v34;
      if ( !v223 )
      {
LABEL_44:
        v38 = v34;
      }
      else
      {
        do
        {
          --v223;
          v36[v223] = v37[v223];
          v37 = (WCHAR *)lpString;
        }
        while ( v223 );
        v38 = v34;
      }
      if ( v37 == (WCHAR *)v245 )
        v35 = v38;
      else
        GlobalFree(v37);
      lpString = v36;
      v244 = v34;
      if ( !v34 || v35 > 0x7FFFFFFF )
        goto LABEL_75;
      v39 = v35;
      v40 = v36;
      if ( v35 )
      {
        while ( *v40 )
        {
          ++v40;
          if ( !--v39 )
            goto LABEL_52;
        }
        v41 = v35 - v39;
      }
      else
      {
LABEL_52:
        v41 = 0;
      }
      if ( !v39 )
        goto LABEL_75;
      v42 = (WCHAR *)&v36[v41];
      v43 = 2147483646;
      for ( nn = v35 - v41; nn; --nn )
      {
        if ( !v43 )
          break;
        if ( !*v9 )
          break;
        *v42++ = *v9++;
        --v43;
      }
      v45 = v42 - 1;
      if ( nn )
        v45 = v42;
      v16 = 0;
      *v45 = 0;
      if ( !nn || !v244 || (unsigned __int64)v244 > 0x7FFFFFFF )
        goto LABEL_75;
      v46 = v244;
      v47 = lpString;
      do
      {
        if ( !*v47 )
          break;
        ++v47;
        --v46;
      }
      while ( v46 );
      v48 = v244 - v46;
      if ( !v46 )
        goto LABEL_75;
      v49 = (WCHAR *)&lpString[v48];
      for ( i1 = v244 - v48; i1; --i1 )
      {
        if ( !v10 )
          break;
        if ( !*v6 )
          break;
        *v49++ = *v6++;
        --v10;
      }
      v51 = v49 - 1;
      if ( i1 )
        v51 = v49;
      *v51 = 0;
      if ( !i1 )
        goto LABEL_75;
    }
    v105 = v229;
    v106 = lpString;
    EnterCriticalSection(v229 + 1);
    if ( v105->DebugInfo )
    {
      RegCloseKey((HKEY)v105->DebugInfo);
      v105->DebugInfo = 0;
      *(_WORD *)v105->OwningThread = 0;
    }
    LeaveCriticalSection(v105 + 1);
    v107 = g_samRead;
    if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
      LODWORD(v107) = g_samRead | 0x100;
    v108 = ((__int64 (__fastcall *)(__int64, const WCHAR *, _QWORD, __int64, struct _RTL_CRITICAL_SECTION *))RegOpenKeyAPI)(
             v17,
             v106,
             0,
             v107,
             v105);
    if ( v108 )
    {
      if ( v231 <= 64 )
      {
LABEL_189:
        hMem = v233;
        v231 = 64;
        if ( v244 > 260 )
          GlobalFree((HGLOBAL)lpString);
        return v108;
      }
LABEL_188:
      GlobalFree(hMem);
      goto LABEL_189;
    }
    if ( a6 )
    {
      v128 = v17 & 0xFFFFFFFF7FFFFFFFuLL;
      if ( v106 )
        v16 = lstrlenW(v106);
      v129 = (unsigned int)(v16 + lstrlenW(off_180267A08[v128]) + 1);
      if ( (SLODWORD(v105->LockSemaphore) >= (unsigned __int64)(int)v129
         || (unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v105->OwningThread, v129, 0))
        && (int)StringCchCopyW(
                  (unsigned __int16 *)v105->OwningThread,
                  SLODWORD(v105->LockSemaphore),
                  off_180267A08[v128]) >= 0
        && (!v106 || (int)StringCchCatW((unsigned __int16 *)v105->OwningThread, SLODWORD(v105->LockSemaphore), v106) >= 0) )
      {
        *(_QWORD *)&v105->LockCount = v17;
      }
      else
      {
        *(_WORD *)v105->OwningThread = 0;
      }
    }
    if ( v231 > 64 )
      GlobalFree(hMem);
    hMem = v233;
    v231 = 64;
    if ( v244 > 260 )
      GlobalFree((HGLOBAL)lpString);
    return 0;
  }
  else
  {
    if ( v231 > 64 )
      GlobalFree(hMem);
    hMem = v233;
    v231 = 64;
    if ( v244 > 260 )
      GlobalFree((HGLOBAL)lpString);
    return 87;
  }
}

```

## disassembly

```asm
0x180011280  mov     [rsp-8+arg_0], rbx
0x180011285  push    rbp
0x180011286  push    rsi
0x180011287  push    rdi
0x180011288  push    r12
0x18001128a  push    r13
0x18001128c  push    r14
0x18001128e  push    r15
0x180011290  lea     rbp, [rsp-340h]
0x180011298  sub     rsp, 440h
0x18001129f  mov     rax, cs:__security_cookie
0x1800112a6  xor     rax, rsp
0x1800112a9  mov     [rbp+370h+var_40], rax
0x1800112b0  mov     rax, [rbp+370h+arg_20]
0x1800112b7  mov     r12, r9
0x1800112ba  mov     [rbp+370h+var_3F0], rax
0x1800112be  lea     rax, [rbp+370h+var_250]
0x1800112c5  mov     [rbp+370h+lpString], rax
0x1800112cc  lea     rax, [rbp+370h+var_3D0]
0x1800112d0  mov     [rbp+370h+hMem], rax
0x1800112d4  mov     rdi, r8
0x1800112d7  mov     [rsp+470h+var_3F8], r9
0x1800112dc  mov     r15, rdx
0x1800112df  mov     [rbp+370h+var_258], 104h
0x1800112e9  lea     r13, asc_18027979C; "\\"
0x1800112f0  mov     [rbp+370h+var_3D8], 40h ; '@'
0x1800112f7  cmp     ecx, 2
0x1800112fa  jnz     loc_1800116B2
0x180011300  mov     r14d, 7FFFFFFEh
0x180011306  lea     rdx, aSoftwareClasse_0; "Software\\Classes\\Installer"
0x18001130d  mov     ecx, r14d
0x180011310  lea     r9, [rbp+370h+var_250]
0x180011317  mov     r8d, 104h
0x18001131d  nop     dword ptr [rax]
0x180011320  test    rcx, rcx
0x180011323  jz      short loc_180011342
0x180011325  movzx   eax, word ptr [rdx]
0x180011328  test    ax, ax
0x18001132b  jz      short loc_180011342
0x18001132d  mov     [r9], ax
0x180011331  add     rdx, 2
0x180011335  add     r9, 2
0x180011339  dec     rcx
0x18001133c  sub     r8, 1
0x180011340  jnz     short loc_180011320
0x180011342  test    r8, r8
0x180011345  lea     rax, [r9-2]
0x180011349  cmovnz  rax, r9
0x18001134d  xor     esi, esi
0x18001134f  mov     [rax], si
0x180011352  test    r8, r8
0x180011355  jz      loc_18001163E
0x18001135b  mov     r15, 0FFFFFFFF80000002h
0x180011362  test    rdi, rdi
0x180011365  jz      loc_180012737
0x18001136b  movsxd  rax, [rbp+370h+var_258]
0x180011372  test    eax, eax
0x180011374  jnz     short loc_180011399
0x180011376  cmp     [rbp+370h+var_3D8], 40h ; '@'
0x18001137a  jle     short loc_18001138C
0x18001137c  mov     rcx, [rbp+370h+hMem]; hMem
0x180011380  call    cs:__imp_GlobalFree
0x180011387  nop     dword ptr [rax+rax+00h]
0x18001138c  lea     rcx, [rbp+370h+var_3D0]
0x180011390  mov     [rbp+370h+hMem], rcx
0x180011394  jmp     loc_18001165C
0x180011399  mov     r9, rax
0x18001139c  cmp     rax, 7FFFFFFFh
0x1800113a2  ja      short loc_180011376
0x1800113a4  mov     r10, [rbp+370h+lpString]
0x1800113ab  mov     rcx, rax
0x1800113ae  mov     rax, r10
0x1800113b1  mov     r8, rcx
0x1800113b4  cmp     word ptr [rax], 0
0x1800113b8  jz      short loc_1800113C4
0x1800113ba  add     rax, 2
0x1800113be  sub     rcx, 1
0x1800113c2  jnz     short loc_1800113B4
0x1800113c4  sub     r8, rcx
0x1800113c7  mov     rdx, rsi
0x1800113ca  test    rcx, rcx
0x1800113cd  cmovnz  rdx, r8
0x1800113d1  jz      short loc_180011376
0x1800113d3  sub     r9, rdx
0x1800113d6  mov     rax, r14
0x1800113d9  lea     rdx, [r10+rdx*2]
0x1800113dd  mov     r8, r13
0x1800113e0  jz      short loc_180011404
0x1800113e2  test    rax, rax
0x1800113e5  jz      short loc_180011404
0x1800113e7  movzx   ecx, word ptr [r8]
0x1800113eb  test    cx, cx
0x1800113ee  jz      short loc_180011404
0x1800113f0  mov     [rdx], cx
0x1800113f3  add     r8, 2
0x1800113f7  add     rdx, 2
0x1800113fb  dec     rax
0x1800113fe  sub     r9, 1
0x180011402  jnz     short loc_1800113E2
0x180011404  test    r9, r9
0x180011407  lea     rax, [rdx-2]
0x18001140b  cmovnz  rax, rdx
0x18001140f  mov     [rax], si
0x180011412  jz      loc_180011376
0x180011418  movsxd  rax, [rbp+370h+var_258]
0x18001141f  test    eax, eax
0x180011421  jz      loc_180011376
0x180011427  mov     r8, rax
0x18001142a  cmp     rax, 7FFFFFFFh
0x180011430  ja      loc_180011376
0x180011436  mov     r10, [rbp+370h+lpString]
0x18001143d  mov     rcx, rax
0x180011440  mov     rax, r10
0x180011443  mov     r9, rcx
0x180011446  cmp     word ptr [rax], 0
0x18001144a  jz      short loc_180011456
0x18001144c  add     rax, 2
0x180011450  sub     rcx, 1
0x180011454  jnz     short loc_180011446
0x180011456  sub     r9, rcx
0x180011459  mov     rdx, rsi
0x18001145c  test    rcx, rcx
0x18001145f  cmovnz  rdx, r9
0x180011463  jz      loc_180011376
0x180011469  lea     rcx, [r10+rdx*2]
0x18001146d  mov     rax, r14
0x180011470  sub     r8, rdx
0x180011473  jz      short loc_180011496
0x180011475  test    rax, rax
0x180011478  jz      short loc_180011496
0x18001147a  movzx   edx, word ptr [rdi]
0x18001147d  test    dx, dx
0x180011480  jz      short loc_180011496
0x180011482  mov     [rcx], dx
0x180011485  add     rdi, 2
0x180011489  add     rcx, 2
0x18001148d  dec     rax
0x180011490  sub     r8, 1
0x180011494  jnz     short loc_180011475
0x180011496  test    r8, r8
0x180011499  lea     rax, [rcx-2]
0x18001149d  cmovnz  rax, rcx
0x1800114a1  mov     [rax], si
0x1800114a4  jz      loc_180011376
0x1800114aa  test    r12, r12
0x1800114ad  jz      loc_180011D41
0x1800114b3  mov     rcx, r12; lpString
0x1800114b6  call    cs:__imp_lstrlenW
0x1800114bd  nop     dword ptr [rax+rax+00h]
0x1800114c2  mov     rcx, [rbp+370h+lpString]; lpString
0x1800114c9  mov     ebx, eax
0x1800114cb  call    cs:__imp_lstrlenW
0x1800114d2  nop     dword ptr [rax+rax+00h]
0x1800114d7  lea     edi, [rax+2]
0x1800114da  add     edi, ebx
0x1800114dc  movsxd  rbx, edi
0x1800114df  cmp     edi, 104h
0x1800114e5  jg      loc_18001342F
0x1800114eb  lea     rsi, [rbp+370h+var_250]
0x1800114f2  mov     rdx, [rbp+370h+lpString]
0x1800114f9  cmp     rdx, rsi
0x1800114fc  jnz     loc_180013814
0x180011502  mov     rax, rbx
0x180011505  lea     rcx, [rbp+370h+var_250]
0x18001150c  cmp     rdx, rcx
0x18001150f  jnz     loc_18001384F
0x180011515  mov     rbx, rax
0x180011518  mov     [rbp+370h+lpString], rsi
0x18001151f  mov     [rbp+370h+var_258], edi
0x180011525  test    edi, edi
0x180011527  jz      loc_18001163E
0x18001152d  cmp     rbx, 7FFFFFFFh
0x180011534  ja      loc_18001163E
0x18001153a  mov     rcx, rbx
0x18001153d  mov     rax, rsi
0x180011540  mov     rdx, rbx
0x180011543  test    rbx, rbx
0x180011546  jz      short loc_180011558
0x180011548  cmp     word ptr [rax], 0
0x18001154c  jz      short loc_180011560
0x18001154e  add     rax, 2
0x180011552  sub     rcx, 1
0x180011556  jnz     short loc_180011548
0x180011558  xor     r9d, r9d
0x18001155b  mov     edx, r9d
0x18001155e  jmp     short loc_180011563
0x180011560  sub     rdx, rcx
0x180011563  test    rcx, rcx
0x180011566  jz      loc_18001163E
0x18001156c  lea     rcx, [rsi+rdx*2]
0x180011570  mov     rax, r14
0x180011573  sub     rbx, rdx
0x180011576  jz      short loc_18001159B
0x180011578  test    rax, rax
0x18001157b  jz      short loc_18001159B
0x18001157d  movzx   edx, word ptr [r13+0]
0x180011582  test    dx, dx
0x180011585  jz      short loc_18001159B
0x180011587  mov     [rcx], dx
0x18001158a  add     r13, 2
0x18001158e  add     rcx, 2
0x180011592  dec     rax
0x180011595  sub     rbx, 1
0x180011599  jnz     short loc_180011578
0x18001159b  test    rbx, rbx
0x18001159e  lea     rax, [rcx-2]
0x1800115a2  cmovnz  rax, rcx
0x1800115a6  xor     esi, esi
0x1800115a8  mov     [rax], si
0x1800115ab  test    rbx, rbx
0x1800115ae  jz      loc_18001163E
0x1800115b4  movsxd  rax, [rbp+370h+var_258]
0x1800115bb  test    eax, eax
0x1800115bd  jz      loc_18001163E
0x1800115c3  mov     rdx, rax
0x1800115c6  cmp     rax, 7FFFFFFFh
0x1800115cc  ja      short loc_18001163E
0x1800115ce  mov     r9, [rbp+370h+lpString]
0x1800115d5  mov     rcx, rax
0x1800115d8  mov     rax, r9
0x1800115db  mov     r8, rcx
0x1800115de  xchg    ax, ax
0x1800115e0  cmp     [rax], si
0x1800115e3  jz      short loc_1800115EF
0x1800115e5  add     rax, 2
0x1800115e9  sub     rcx, 1
0x1800115ed  jnz     short loc_1800115E0
0x1800115ef  sub     r8, rcx
0x1800115f2  mov     rax, rsi
0x1800115f5  test    rcx, rcx
0x1800115f8  cmovnz  rax, r8
0x1800115fc  jz      short loc_18001163E
0x1800115fe  lea     rcx, [r9+rax*2]
0x180011602  sub     rdx, rax
0x180011605  jz      short loc_18001162A
0x180011607  test    r14, r14
0x18001160a  jz      short loc_18001162A
0x18001160c  movzx   eax, word ptr [r12]
0x180011611  test    ax, ax
0x180011614  jz      short loc_18001162A
0x180011616  mov     [rcx], ax
0x180011619  add     r12, 2
0x18001161d  add     rcx, 2
0x180011621  dec     r14
0x180011624  sub     rdx, 1
0x180011628  jnz     short loc_180011607
0x18001162a  test    rdx, rdx
0x18001162d  lea     rax, [rcx-2]
0x180011631  cmovnz  rax, rcx
0x180011635  mov     [rax], si
0x180011638  jnz     loc_180011D41
0x18001163e  cmp     [rbp+370h+var_3D8], 40h ; '@'
0x180011642  jle     short loc_180011654
0x180011644  mov     rcx, [rbp+370h+hMem]; hMem
0x180011648  call    cs:__imp_GlobalFree
0x18001164f  nop     dword ptr [rax+rax+00h]
0x180011654  lea     rax, [rbp+370h+var_3D0]
0x180011658  mov     [rbp+370h+hMem], rax
0x18001165c  cmp     [rbp+370h+var_258], 104h
0x180011666  mov     [rbp+370h+var_3D8], 40h ; '@'
0x18001166d  jle     short loc_180011682
0x18001166f  mov     rcx, [rbp+370h+lpString]; hMem
0x180011676  call    cs:__imp_GlobalFree
0x18001167d  nop     dword ptr [rax+rax+00h]
0x180011682  mov     eax, 65Bh
0x180011687  mov     rcx, [rbp+370h+var_40]
0x18001168e  xor     rcx, rsp; StackCookie
0x180011691  call    __security_check_cookie
0x180011696  mov     rbx, [rsp+470h+arg_0]
0x18001169e  add     rsp, 440h
0x1800116a5  pop     r15
0x1800116a7  pop     r14
0x1800116a9  pop     r13
0x1800116ab  pop     r12
0x1800116ad  pop     rdi
0x1800116ae  pop     rsi
0x1800116af  pop     rbp
0x1800116b0  retn
0x1800116b2  test    ecx, ecx
0x1800116b4  jnz     loc_1800119AC
0x1800116ba  lea     rcx, ?g_csPolicyTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800116c1  call    cs:__imp_EnterCriticalSection
0x1800116c8  nop     dword ptr [rax+rax+00h]
0x1800116cd  lea     rcx, ?g_csPolicyTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800116d4  call    cs:__imp_EnterCriticalSection
0x1800116db  nop     dword ptr [rax+rax+00h]
0x1800116e0  xor     esi, esi
0x1800116e2  lea     r12, aNull; "(NULL)"
0x1800116e9  cmp     cs:?g_pPolicyTable@@3PEAUPolicyEntry@@EA, rsi; PolicyEntry * g_pPolicyTable
0x1800116f0  jz      loc_18001223D
0x1800116f6  lea     rcx, ?g_csPolicyTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800116fd  call    cs:__imp_LeaveCriticalSection
0x180011704  nop     dword ptr [rax+rax+00h]
0x180011709  mov     rbx, cs:?g_pPolicyTable@@3PEAUPolicyEntry@@EA; PolicyEntry * g_pPolicyTable
0x180011710  cmp     [rbx], rsi
0x180011713  jz      loc_180012792
0x180011719  mov     eax, [rbx+18h]
0x18001171c  cmp     eax, 0FFFFFFFFh
0x18001171f  jz      loc_180012792
0x180011725  cmp     qword ptr [rbx+8], 1
  ... truncated ...
```
