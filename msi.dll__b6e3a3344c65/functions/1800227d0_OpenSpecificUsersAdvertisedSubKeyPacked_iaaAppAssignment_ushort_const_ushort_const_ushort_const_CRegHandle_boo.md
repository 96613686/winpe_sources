# OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)

- ea: `0x1800227d0`
- end: `0x180024f96`
- name: `?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z`
- size: `10182`
- prototype: `unsigned int __high(enum iaaAppAssignment, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CRegHandle *, bool)`
- caller_count: `24`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180013264`
- `0x18001354c`
- `0x180013fe4`
- `0x180014848`
- `0x180015ac0`
- `0x180017b28`
- `0x180018210`
- `0x180018d10`
- `0x18001bb30`
- `0x180021030`
- `0x1800221b0`
- `0x18002e3ec`
- `0x18004aff0`
- `0x18004d38c`
- `0x18004e3b0`
- `0x18004ed4c`
- `0x18004fa38`
- `0x180050710`
- `0x18005d670`
- `0x18005de7c`
- `0x1800af898`
- `0x1801140e4`
- `0x180192bd4`
- `0x1801d3bac`

## callees

- `0x180015950`
- `0x1800227d0`
- `0x180024f9c`
- `0x1800252a8`
- `0x180025560`
- `0x1800255e0`
- `0x180025688`
- `0x18002571c`
- `0x180025a18`
- `0x180050cf0`
- `0x180064f18`
- `0x180071fdc`
- `0x180083434`
- `0x180090ca4`
- `0x1800a9d48`
- `0x1800b7800`
- `0x180146568`
- `0x180157094`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800232f2`
- `msvcrt!_wcsicmp` at `0x1800232f2`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180022fdf`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800231f8`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800236e4`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180022fdf`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800231f8`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800236e4`
- `ADVAPI32!CopySid` at `0x180022fa7`
- `ADVAPI32!CopySid` at `0x1800236ac`
- `ADVAPI32!CopySid` at `0x180022fa7`
- `ADVAPI32!CopySid` at `0x1800236ac`
- `ADVAPI32!GetTokenInformation` at `0x180022f8a`
- `ADVAPI32!GetTokenInformation` at `0x18002368f`
- `ADVAPI32!GetTokenInformation` at `0x180022f8a`
- `ADVAPI32!GetTokenInformation` at `0x18002368f`
- `ADVAPI32!SetThreadToken` at `0x180022e88`
- `ADVAPI32!SetThreadToken` at `0x18002315c`
- `ADVAPI32!SetThreadToken` at `0x18002349d`
- `ADVAPI32!SetThreadToken` at `0x1800238cf`
- `ADVAPI32!SetThreadToken` at `0x1800240a3`
- `ADVAPI32!SetThreadToken` at `0x1800247c1`
- `ADVAPI32!SetThreadToken` at `0x180024830`
- `ADVAPI32!SetThreadToken` at `0x180024a8e`
- `ADVAPI32!SetThreadToken` at `0x180024c06`
- `ADVAPI32!SetThreadToken` at `0x180024c7e`
- `ADVAPI32!SetThreadToken` at `0x180024dc2`
- `ADVAPI32!SetThreadToken` at `0x180024e3a`
- `ADVAPI32!SetThreadToken` at `0x180022e88`
- `ADVAPI32!SetThreadToken` at `0x18002315c`
- `ADVAPI32!SetThreadToken` at `0x18002349d`
- `ADVAPI32!SetThreadToken` at `0x1800238cf`
- `ADVAPI32!SetThreadToken` at `0x1800240a3`
- `ADVAPI32!SetThreadToken` at `0x1800247c1`
- `ADVAPI32!SetThreadToken` at `0x180024830`
- `ADVAPI32!SetThreadToken` at `0x180024a8e`
- `ADVAPI32!SetThreadToken` at `0x180024c06`
- `ADVAPI32!SetThreadToken` at `0x180024c7e`
- `ADVAPI32!SetThreadToken` at `0x180024dc2`
- `ADVAPI32!SetThreadToken` at `0x180024e3a`
- `ADVAPI32!OpenThreadToken` at `0x180023914`
- `ADVAPI32!OpenThreadToken` at `0x180023ba9`
- `ADVAPI32!OpenThreadToken` at `0x180024464`
- `ADVAPI32!OpenThreadToken` at `0x180024586`
- `ADVAPI32!OpenThreadToken` at `0x180023914`
- `ADVAPI32!OpenThreadToken` at `0x180023ba9`
- `ADVAPI32!OpenThreadToken` at `0x180024464`
- `ADVAPI32!OpenThreadToken` at `0x180024586`
- `ADVAPI32!OpenProcessToken` at `0x180023942`
- `ADVAPI32!OpenProcessToken` at `0x180023bd8`
- `ADVAPI32!OpenProcessToken` at `0x180024492`
- `ADVAPI32!OpenProcessToken` at `0x1800245b5`
- `ADVAPI32!OpenProcessToken` at `0x180023942`
- `ADVAPI32!OpenProcessToken` at `0x180023bd8`
- `ADVAPI32!OpenProcessToken` at `0x180024492`
- `ADVAPI32!OpenProcessToken` at `0x1800245b5`
- `ADVAPI32!RegCloseKey` at `0x1800234e3`
- `ADVAPI32!RegCloseKey` at `0x180023df0`
- `ADVAPI32!RegCloseKey` at `0x180023eec`
- `ADVAPI32!RegCloseKey` at `0x1800234e3`
- `ADVAPI32!RegCloseKey` at `0x180023df0`
- `ADVAPI32!RegCloseKey` at `0x180023eec`
- `KERNEL32!InitializeCriticalSection` at `0x180023dd7`
- `KERNEL32!InitializeCriticalSection` at `0x180023ed3`
- `KERNEL32!InitializeCriticalSection` at `0x180023dd7`
- `KERNEL32!InitializeCriticalSection` at `0x180023ed3`
- `KERNEL32!CloseHandle` at `0x180022fc1`
- `KERNEL32!CloseHandle` at `0x1800236c6`
- `KERNEL32!CloseHandle` at `0x180024090`
- `KERNEL32!CloseHandle` at `0x1800240b7`
- `KERNEL32!CloseHandle` at `0x18002481d`
- `KERNEL32!CloseHandle` at `0x180024844`
- `KERNEL32!CloseHandle` at `0x180022fc1`
- `KERNEL32!CloseHandle` at `0x1800236c6`
- `KERNEL32!CloseHandle` at `0x180024090`
- `KERNEL32!CloseHandle` at `0x1800240b7`
- `KERNEL32!CloseHandle` at `0x18002481d`
- `KERNEL32!CloseHandle` at `0x180024844`
- `KERNEL32!LeaveCriticalSection` at `0x180022c25`
- `KERNEL32!LeaveCriticalSection` at `0x180022c5c`
- `KERNEL32!LeaveCriticalSection` at `0x180022dd9`
- `KERNEL32!LeaveCriticalSection` at `0x180022f1a`
- `KERNEL32!LeaveCriticalSection` at `0x1800230fc`
- `KERNEL32!LeaveCriticalSection` at `0x18002334b`
- `KERNEL32!LeaveCriticalSection` at `0x180023382`
- `KERNEL32!LeaveCriticalSection` at `0x1800233ee`
- `KERNEL32!LeaveCriticalSection` at `0x1800234fa`
- `KERNEL32!LeaveCriticalSection` at `0x18002361f`
- `KERNEL32!LeaveCriticalSection` at `0x180023865`
- `KERNEL32!LeaveCriticalSection` at `0x180023c2a`
- `KERNEL32!LeaveCriticalSection` at `0x180023e06`
- `KERNEL32!LeaveCriticalSection` at `0x180023e92`
- `KERNEL32!LeaveCriticalSection` at `0x180023f02`
- `KERNEL32!LeaveCriticalSection` at `0x180024005`
- `KERNEL32!LeaveCriticalSection` at `0x180024066`
- `KERNEL32!LeaveCriticalSection` at `0x180024504`
- `KERNEL32!LeaveCriticalSection` at `0x180024607`
- `KERNEL32!LeaveCriticalSection` at `0x180024a2c`
- `KERNEL32!LeaveCriticalSection` at `0x180024bd6`
- `KERNEL32!LeaveCriticalSection` at `0x180024d92`
- `KERNEL32!LeaveCriticalSection` at `0x180022c25`
- `KERNEL32!LeaveCriticalSection` at `0x180022c5c`
- `KERNEL32!LeaveCriticalSection` at `0x180022dd9`
- `KERNEL32!LeaveCriticalSection` at `0x180022f1a`
- `KERNEL32!LeaveCriticalSection` at `0x1800230fc`
- `KERNEL32!LeaveCriticalSection` at `0x18002334b`
- `KERNEL32!LeaveCriticalSection` at `0x180023382`
- `KERNEL32!LeaveCriticalSection` at `0x1800233ee`
- `KERNEL32!LeaveCriticalSection` at `0x1800234fa`
- `KERNEL32!LeaveCriticalSection` at `0x18002361f`
- `KERNEL32!LeaveCriticalSection` at `0x180023865`
- `KERNEL32!LeaveCriticalSection` at `0x180023c2a`
- `KERNEL32!LeaveCriticalSection` at `0x180023e06`
- `KERNEL32!LeaveCriticalSection` at `0x180023e92`
- `KERNEL32!LeaveCriticalSection` at `0x180023f02`
- `KERNEL32!LeaveCriticalSection` at `0x180024005`
- `KERNEL32!LeaveCriticalSection` at `0x180024066`
- `KERNEL32!LeaveCriticalSection` at `0x180024504`
- `KERNEL32!LeaveCriticalSection` at `0x180024607`
- `KERNEL32!LeaveCriticalSection` at `0x180024a2c`
- `KERNEL32!LeaveCriticalSection` at `0x180024bd6`
- `KERNEL32!LeaveCriticalSection` at `0x180024d92`
- `KERNEL32!GetLastError` at `0x18002391e`
- `KERNEL32!GetLastError` at `0x180024071`
- `KERNEL32!GetLastError` at `0x18002446e`
- `KERNEL32!GetLastError` at `0x1800247fe`
- `KERNEL32!GetLastError` at `0x180024cb3`
- `KERNEL32!GetLastError` at `0x180024d0c`
- `KERNEL32!GetLastError` at `0x180024e6f`
- `KERNEL32!GetLastError` at `0x180024ec8`
- `KERNEL32!GetLastError` at `0x18002391e`
- `KERNEL32!GetLastError` at `0x180024071`
- `KERNEL32!GetLastError` at `0x18002446e`
- `KERNEL32!GetLastError` at `0x1800247fe`
- `KERNEL32!GetLastError` at `0x180024cb3`
- `KERNEL32!GetLastError` at `0x180024d0c`
- `KERNEL32!GetLastError` at `0x180024e6f`
- `KERNEL32!GetLastError` at `0x180024ec8`
- `KERNEL32!EnterCriticalSection` at `0x180022bf5`
- `KERNEL32!EnterCriticalSection` at `0x180022c02`
- `KERNEL32!EnterCriticalSection` at `0x180022dbd`
- `KERNEL32!EnterCriticalSection` at `0x180022ef6`
- `KERNEL32!EnterCriticalSection` at `0x1800230e9`
- `KERNEL32!EnterCriticalSection` at `0x18002331d`
- `KERNEL32!EnterCriticalSection` at `0x18002332a`
- `KERNEL32!EnterCriticalSection` at `0x1800233d2`
- `KERNEL32!EnterCriticalSection` at `0x1800234d4`
- `KERNEL32!EnterCriticalSection` at `0x1800235fb`
- `KERNEL32!EnterCriticalSection` at `0x180023852`
- `KERNEL32!EnterCriticalSection` at `0x180023de1`
- `KERNEL32!EnterCriticalSection` at `0x180023edd`
- `KERNEL32!EnterCriticalSection` at `0x1800244f1`
- `KERNEL32!EnterCriticalSection` at `0x180024a19`
- `KERNEL32!EnterCriticalSection` at `0x180022bf5`
- `KERNEL32!EnterCriticalSection` at `0x180022c02`
- `KERNEL32!EnterCriticalSection` at `0x180022dbd`
- `KERNEL32!EnterCriticalSection` at `0x180022ef6`
- `KERNEL32!EnterCriticalSection` at `0x1800230e9`
- `KERNEL32!EnterCriticalSection` at `0x18002331d`
- `KERNEL32!EnterCriticalSection` at `0x18002332a`
- `KERNEL32!EnterCriticalSection` at `0x1800233d2`
- `KERNEL32!EnterCriticalSection` at `0x1800234d4`
- `KERNEL32!EnterCriticalSection` at `0x1800235fb`
- `KERNEL32!EnterCriticalSection` at `0x180023852`
- `KERNEL32!EnterCriticalSection` at `0x180023de1`
- `KERNEL32!EnterCriticalSection` at `0x180023edd`
- `KERNEL32!EnterCriticalSection` at `0x1800244f1`
- `KERNEL32!EnterCriticalSection` at `0x180024a19`
- `KERNEL32!GlobalAlloc` at `0x180023acf`
- `KERNEL32!GlobalAlloc` at `0x180023c60`
- `KERNEL32!GlobalAlloc` at `0x180024ab3`
- `KERNEL32!GlobalAlloc` at `0x180023acf`
- `KERNEL32!GlobalAlloc` at `0x180023c60`
- `KERNEL32!GlobalAlloc` at `0x180024ab3`
- `KERNEL32!GetCurrentThread` at `0x1800238fb`
- `KERNEL32!GetCurrentThread` at `0x180023b90`
- `KERNEL32!GetCurrentThread` at `0x18002444b`
- `KERNEL32!GetCurrentThread` at `0x18002456d`
- `KERNEL32!GetCurrentThread` at `0x1800238fb`
- `KERNEL32!GetCurrentThread` at `0x180023b90`
- `KERNEL32!GetCurrentThread` at `0x18002444b`
- `KERNEL32!GetCurrentThread` at `0x18002456d`
- `KERNEL32!GetCurrentProcess` at `0x18002392f`
- `KERNEL32!GetCurrentProcess` at `0x180023bc5`
- `KERNEL32!GetCurrentProcess` at `0x18002447f`
- `KERNEL32!GetCurrentProcess` at `0x1800245a2`
- `KERNEL32!GetCurrentProcess` at `0x18002392f`
- `KERNEL32!GetCurrentProcess` at `0x180023bc5`
- `KERNEL32!GetCurrentProcess` at `0x18002447f`
- `KERNEL32!GetCurrentProcess` at `0x1800245a2`
- `KERNEL32!lstrlenW` at `0x180022a08`
- `KERNEL32!lstrlenW` at `0x180022a13`
- `KERNEL32!lstrlenW` at `0x180023a2b`
- `KERNEL32!lstrlenW` at `0x180023a42`
- `KERNEL32!lstrlenW` at `0x180022a08`
- `KERNEL32!lstrlenW` at `0x180022a13`
- `KERNEL32!lstrlenW` at `0x180023a2b`
- `KERNEL32!lstrlenW` at `0x180023a42`
- `KERNEL32!GlobalFree` at `0x1800228d0`
- `KERNEL32!GlobalFree` at `0x180022b89`

## string_xrefs

- `0x180022856`: `Software\Classes\Installer`
- `0x180022c97`: `Software\Microsoft\Windows\CurrentVersion\Installer\Managed`
- `0x1800243d3`: `Installer`
- `0x1800249af`: `Software\Microsoft\Installer`
- `0x180024cca`: `GetTokenInformation failed with error %d`
- `0x180024e86`: `GetTokenInformation failed with error %d`

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
  const unsigned __int16 *v9; // r14
  __int64 v10; // r13
  const wchar_t *v11; // rdx
  __int64 v12; // rcx
  _WORD *v13; // r9
  __int64 v14; // r8
  _WORD *v15; // rax
  int v16; // esi
  __int64 v17; // r15
  __int64 v18; // rcx
  LPCWSTR v19; // rax
  __int64 v20; // rdx
  WCHAR *v21; // rcx
  __int64 v22; // rax
  const unsigned __int16 *v23; // r8
  __int64 kk; // r9
  WCHAR *v25; // rax
  __int64 v26; // rcx
  LPCWSTR v27; // rax
  __int64 v28; // r9
  WCHAR *v29; // rcx
  __int64 v30; // rax
  __int64 mm; // r8
  WCHAR *v32; // rax
  int v33; // edi
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
  WCHAR *v56; // r8
  __int64 v57; // rcx
  const unsigned __int16 *v58; // r9
  __int64 v59; // rdx
  WCHAR *v60; // rax
  __int64 v61; // rcx
  LPCWSTR v62; // rax
  __int64 v63; // rax
  WCHAR *v64; // rdx
  __int64 v65; // rcx
  const unsigned __int16 *v66; // r8
  __int64 k; // r9
  WCHAR *v68; // rax
  int v69; // eax
  char v70; // r14
  int v71; // ebx
  DWORD v72; // esi
  unsigned int v73; // eax
  unsigned int v74; // r14d
  unsigned int v75; // ecx
  int v76; // r15d
  unsigned int v77; // r8d
  unsigned int v78; // ecx
  struct IUnknownVtbl *v79; // rdx
  bool v80; // dl
  int v81; // ecx
  int v82; // eax
  unsigned int v83; // ebx
  struct IUnknownVtbl *v84; // rcx
  bool v85; // si
  DWORD v86; // ebx
  PSID v87; // rbx
  _WORD *v88; // r9
  __int64 v89; // rcx
  _WORD *v90; // rax
  int v91; // r12d
  __int64 v92; // rdx
  int v93; // r10d
  _WORD *v94; // r8
  __int64 v95; // rdx
  __int64 v96; // rcx
  _WORD *v97; // rax
  unsigned int v98; // r13d
  DWORD v99; // edi
  unsigned int v100; // ecx
  void *v101; // rsi
  int v102; // ebx
  int v103; // r12d
  int CurrentUserSID; // ebx
  wchar_t *v105; // r8
  __int64 v106; // rcx
  _WORD *v107; // rax
  __int64 v108; // rdx
  int v109; // r10d
  wchar_t *v110; // r9
  __int64 v111; // rdx
  __int64 v112; // rcx
  wchar_t *v113; // rax
  _DWORD *v114; // rbx
  int v115; // eax
  unsigned int v116; // esi
  int v117; // eax
  char v118; // r14
  int v119; // ebx
  DWORD v120; // esi
  unsigned int v121; // eax
  unsigned int v122; // r14d
  unsigned int v123; // ecx
  int v124; // r15d
  unsigned int v125; // r8d
  unsigned int v126; // ecx
  struct IUnknownVtbl *v127; // rdx
  struct _RTL_CRITICAL_SECTION *v128; // r12
  const WCHAR *v129; // rdi
  __int64 v130; // r9
  unsigned int v131; // ebx
  int v132; // ebx
  bool v133; // dl
  int v134; // ecx
  int v135; // eax
  unsigned int v136; // ebx
  struct IUnknownVtbl *lpVtbl; // rcx
  bool v138; // si
  DWORD LastError; // ebx
  PSID v140; // rbx
  _WORD *v141; // r9
  __int64 v142; // rcx
  _WORD *v143; // rax
  __int64 v144; // rdx
  int v145; // r10d
  _WORD *v146; // r8
  __int64 v147; // rdx
  __int64 v148; // rcx
  _WORD *v149; // rax
  WCHAR *v150; // r9
  __int64 v151; // rcx
  WCHAR *v152; // r8
  __int64 v153; // rdx
  WCHAR *v154; // rax
  unsigned int v155; // ecx
  int v156; // ebx
  HANDLE v157; // rax
  HANDLE v158; // rax
  unsigned __int64 v159; // rbx
  __int64 v160; // rdx
  _OWORD *v161; // rcx
  wchar_t **v162; // rax
  __int64 v163; // rdx
  __int128 v164; // xmm0
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  _OWORD *v167; // rcx
  wchar_t **v168; // rax
  __int64 v169; // rdx
  __int128 v170; // xmm0
  bool *v171; // rdx
  BOOL v172; // ebx
  char *v173; // rdx
  unsigned int v174; // eax
  int v175; // ecx
  const WCHAR *v176; // rdx
  const WCHAR *v177; // rdx
  __int64 v178; // rcx
  LPCWSTR v179; // rax
  __int64 v180; // rax
  WCHAR *v181; // rdx
  WCHAR *v182; // r8
  __int64 v183; // rcx
  __int64 n; // r9
  WCHAR *v185; // rax
  __int64 v186; // rdx
  LPCWSTR v187; // rax
  __int64 v188; // r8
  WCHAR *v189; // rdx
  __int64 v190; // rax
  const unsigned __int16 *v191; // r9
  __int64 ii; // rcx
  WCHAR *v193; // rax
  __int64 v194; // rdx
  LPCWSTR v195; // rax
  __int64 v196; // r8
  const unsigned __int16 *v197; // r9
  WCHAR *v198; // rdx
  __int64 v199; // rax
  __int64 jj; // rcx
  WCHAR *v201; // rax
  HANDLE v202; // rax
  HANDLE v203; // rax
  DWORD v204; // esi
  unsigned int v205; // ecx
  void *v206; // r14
  int v207; // ebx
  HANDLE v208; // rax
  HANDLE v209; // rax
  char *v210; // rdx
  unsigned int v211; // eax
  int v212; // ecx
  int v213; // ebx
  bool *v214; // rdx
  __int64 v215; // rdx
  LPCWSTR v216; // rax
  __int64 v217; // r9
  WCHAR *v218; // rdx
  __int64 v219; // rax
  __int64 m; // rcx
  WCHAR *v221; // rax
  BOOL v222; // ebx
  __int64 v223; // rcx
  LPCWSTR v224; // rax
  __int64 v225; // rax
  const unsigned __int16 *v226; // r8
  __int64 v227; // rcx
  WCHAR *v228; // r9
  __int64 i; // rdx
  WCHAR *v230; // rax
  __int64 v231; // rdx
  LPCWSTR v232; // rax
  __int64 v233; // r8
  const wchar_t *v234; // r9
  __int64 v235; // rax
  WCHAR *v236; // rdx
  __int64 j; // rcx
  WCHAR *v238; // rax
  DWORD v239; // esi
  unsigned int Value; // ecx
  void *v241; // r14
  int v242; // ebx
  int v243; // ecx
  int v244; // ecx
  DWORD v245; // eax
  DWORD v246; // eax
  int v247; // r8d
  HANDLE TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  DWORD ReturnLength[2]; // [rsp+68h] [rbp-98h] BYREF
  int v250; // [rsp+70h] [rbp-90h] BYREF
  char v251; // [rsp+74h] [rbp-8Ch]
  const WCHAR *v252; // [rsp+78h] [rbp-88h]
  struct _RTL_CRITICAL_SECTION *v253; // [rsp+80h] [rbp-80h]
  HGLOBAL hMem; // [rsp+90h] [rbp-70h] BYREF
  int v255; // [rsp+98h] [rbp-68h]
  int v256; // [rsp+9Ch] [rbp-64h]
  _BYTE v257[128]; // [rsp+A0h] [rbp-60h] BYREF
  PSID pDestinationSid[2]; // [rsp+120h] [rbp+20h] BYREF
  __int16 *v259; // [rsp+130h] [rbp+30h] BYREF
  int v260; // [rsp+138h] [rbp+38h]
  __int16 v261; // [rsp+140h] [rbp+40h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+148h] [rbp+48h] BYREF
  wchar_t *TokenInformation; // [rsp+180h] [rbp+80h] BYREF
  int v264; // [rsp+188h] [rbp+88h]
  int v265; // [rsp+18Ch] [rbp+8Ch]
  _BYTE v266[128]; // [rsp+190h] [rbp+90h] BYREF
  LPCWSTR lpString; // [rsp+210h] [rbp+110h]
  int v268; // [rsp+218h] [rbp+118h]
  _BYTE v269[528]; // [rsp+220h] [rbp+120h] BYREF

  v6 = a4;
  v253 = a5;
  lpString = (LPCWSTR)v269;
  hMem = v257;
  v252 = a4;
  v8 = a2;
  v268 = 260;
  v9 = L"\\";
  v255 = 64;
  if ( a1 == 2 )
  {
    v10 = 2147483646;
    v11 = L"Software\\Classes\\Installer";
    v12 = 2147483646;
    v13 = v269;
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
    if ( v255 > 64 )
      GlobalFree(hMem);
    hMem = v257;
LABEL_78:
    v255 = 64;
    if ( v268 <= 260 )
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
    LOWORD(v103) = 14;
    if ( !a2 )
      goto LABEL_207;
    v264 = 64;
    TokenInformation = (wchar_t *)v266;
    v265 = 64;
    pDestinationSid[0] = &v259;
    pDestinationSid[1] = (PSID)0x4800000048LL;
    CurrentUserSID = GetCurrentUserSID(pDestinationSid);
    if ( CurrentUserSID )
    {
LABEL_201:
      if ( SLODWORD(pDestinationSid[1]) > 72 )
        GlobalFree(pDestinationSid[0]);
      if ( CurrentUserSID || _wcsicmp(v8, TokenInformation) )
      {
        if ( v264 > 64 )
          GlobalFree(TokenInformation);
        if ( v255 > 64 )
LABEL_316:
          GlobalFree(hMem);
LABEL_317:
        hMem = v257;
        v255 = 64;
        if ( v268 > 260 )
        {
          GlobalFree((HGLOBAL)lpString);
          return 2;
        }
        return 2;
      }
      if ( v264 > 64 )
        GlobalFree(TokenInformation);
LABEL_207:
      EnterCriticalSection(&g_csPolicyTableLock);
      EnterCriticalSection(&g_csPolicyTableLock);
      if ( !g_pPolicyTable )
      {
        g_pPolicyTable = GlobalAlloc(0x40u, 0x4D8u);
        v167 = g_pPolicyTable;
        if ( !g_pPolicyTable )
        {
          LeaveCriticalSection(&g_csPolicyTableLock);
          goto LABEL_394;
        }
        v168 = &off_18025D9D0;
        v169 = 9;
        do
        {
          v167 += 8;
          v170 = *(_OWORD *)v168;
          v168 += 16;
          *(v167 - 8) = v170;
          *(v167 - 7) = *((_OWORD *)v168 - 7);
          *(v167 - 6) = *((_OWORD *)v168 - 6);
          *(v167 - 5) = *((_OWORD *)v168 - 5);
          *(v167 - 4) = *((_OWORD *)v168 - 4);
          *(v167 - 3) = *((_OWORD *)v168 - 3);
          *(v167 - 2) = *((_OWORD *)v168 - 2);
          *(v167 - 1) = *((_OWORD *)v168 - 1);
          --v169;
        }
        while ( v169 );
        *v167 = *(_OWORD *)v168;
        v167[1] = *((_OWORD *)v168 + 1);
        v167[2] = *((_OWORD *)v168 + 2);
        v167[3] = *((_OWORD *)v168 + 3);
        v167[4] = *((_OWORD *)v168 + 4);
        *((_QWORD *)v167 + 10) = v168[10];
      }
      LeaveCriticalSection(&g_csPolicyTableLock);
      v114 = g_pPolicyTable;
      if ( *(_QWORD *)g_pPolicyTable )
      {
        v115 = *((_DWORD *)g_pPolicyTable + 6);
        if ( v115 != -1 )
        {
          if ( *((_QWORD *)g_pPolicyTable + 1) == 1 )
          {
            v116 = *((_DWORD *)g_pPolicyTable + 4);
            goto LABEL_212;
          }
          if ( v115 != -2 || PopulateDefaultValuesInPolicyTable() )
          {
            v116 = v114[6];
            v259 = &v261;
            *(_OWORD *)pDestinationSid = 0;
            v261 = 0;
            v260 = 1;
            InitializeCriticalSection(&CriticalSection);
            EnterCriticalSection(&CriticalSection);
            if ( pDestinationSid[0] )
            {
              RegCloseKey((HKEY)pDestinationSid[0]);
              pDestinationSid[0] = 0;
              *v259 = 0;
            }
            LeaveCriticalSection(&CriticalSection);
            if ( !OpenPolicyKey((HKEY *)pDestinationSid, 1) )
            {
              v177 = *(const WCHAR **)v114;
              TokenInformation = (wchar_t *)v266;
              v264 = 40;
              v265 = 40;
              if ( !(unsigned int)MsiRegQueryValueExW((HKEY)pDestinationSid[0], v177, (__int64)&TokenInformation, 0)
                && *(_DWORD *)TokenInformation >= v114[7]
                && *(_DWORD *)TokenInformation <= v114[8] )
              {
                v116 = *(_DWORD *)TokenInformation;
              }
              if ( v264 > 40 )
                GlobalFree(TokenInformation);
              v264 = 40;
              TokenInformation = (wchar_t *)v266;
            }
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                L"%s policy value '%s' is %u",
                L"Machine",
                *(const unsigned __int16 **)v114,
                (const unsigned __int16 *)v116,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            *((_QWORD *)v114 + 2) = v116;
            *((_QWORD *)v114 + 1) = 1;
            CRegHandle::~CRegHandle((CRegHandle *)pDestinationSid);
LABEL_212:
            LeaveCriticalSection(&g_csPolicyTableLock);
            if ( !v116 )
            {
              v16 = 0;
              goto LABEL_214;
            }
            if ( v255 > 64 )
              goto LABEL_316;
            goto LABEL_317;
          }
        }
      }
LABEL_394:
      LeaveCriticalSection(&g_csPolicyTableLock);
LABEL_214:
      v117 = dword_180306D40;
      v250 = 0;
      if ( dword_180306D40 == -1 )
      {
        TokenHandle = (HANDLE)-1LL;
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
        {
          if ( !SetThreadToken(0, 0) )
            ExitProcessIfNotClient();
        }
        else
        {
          TokenHandle = (HANDLE)-1LL;
        }
        *(_QWORD *)ReturnLength = 0;
        CurrentProcess = GetCurrentProcess();
        if ( OpenProcessToken(CurrentProcess, 8u, (PHANDLE)ReturnLength) )
        {
          v172 = IsLocalSystemToken(*(void **)ReturnLength);
          CloseHandle(*(HANDLE *)ReturnLength);
          dword_180306D40 = v172;
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
        if ( TokenHandle != (HANDLE)-1LL )
        {
          if ( !SetThreadToken(0, TokenHandle) )
            ExitProcessIfNotClient();
          CloseHandle(TokenHandle);
        }
        v117 = dword_180306D40;
      }
      if ( g_scServerContext != 2 && !v117 )
      {
        v118 = 0;
        v251 = 0;
LABEL_247:
        v256 = 64;
        pDestinationSid[0] = &v259;
        pDestinationSid[1] = (PSID)0x4800000048LL;
        TokenHandle = 0;
        v134 = RunningAsLocalSystem();
        if ( v134 == -1 )
        {
          LastError = 5;
          goto LABEL_618;
        }
        v135 = g_scServerContext;
        v136 = 0;
        if ( g_scServerContext == 2 || v134 == 1 )
        {
          EnterCriticalSection(&g_csImpersonationLock);
          if ( g_dwImpersonationSlot != -1 )
            v136 = (unsigned int)TlsGetValue(g_dwImpersonationSlot) >> 29;
          LeaveCriticalSection(&g_csImpersonationLock);
          v135 = g_scServerContext;
        }
        if ( v135 == 2 && v136 == 1 )
        {
          CCoImpersonate::CCoImpersonate((CCoImpersonate *)ReturnLength, v133);
          LastError = OpenUserToken(&TokenHandle, v171);
          v138 = LastError == 0;
          if ( LOBYTE(ReturnLength[1]) )
            StopImpersonateCore(1);
          goto LABEL_257;
        }
        lpVtbl = (struct IUnknownVtbl *)Token;
        v138 = 0;
        if ( !Token && v135 == 2 )
        {
          if ( !CMsiTransaction::m_pMsiTransaction )
          {
            TokenHandle = 0;
LABEL_305:
            LastError = 0;
            v157 = GetCurrentThread();
            if ( !OpenThreadToken(v157, 0xCu, 1, &TokenHandle) )
            {
              LastError = GetLastError();
              if ( LastError == 1008 )
              {
                LastError = 0;
                v158 = GetCurrentProcess();
                if ( !OpenProcessToken(v158, 0xCu, &TokenHandle) )
                  LastError = GetLastError();
              }
            }
            if ( !LastError )
            {
              v138 = 1;
LABEL_258:
              v140 = pDestinationSid[0];
              ReturnLength[0] = 0;
              if ( GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x58u, ReturnLength) )
              {
                if ( CopySid(0x48u, v140, TokenInformation) )
                  LastError = 0;
                else
                  LastError = GetLastError();
              }
              else
              {
                v245 = GetLastError();
                LastError = v245;
                if ( g_dmDiagnosticMode )
                  DebugString(
                    9,
                    0,
                    0,
                    L"GetTokenInformation failed with error %d",
                    (const unsigned __int16 *)v245,
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    0,
                    0);
              }
              if ( v138 )
                CloseHandle(TokenHandle);
              v16 = 0;
              if ( !LastError )
              {
                TokenHandle = 0;
                if ( ConvertSidToStringSidW(pDestinationSid[0], (LPWSTR *)&TokenHandle) )
                {
                  v141 = TokenHandle;
                  if ( !TokenHandle )
                    goto LABEL_311;
                  v142 = 0x7FFFFFFF;
                  v143 = TokenHandle;
                  do
                  {
                    if ( !*v143 )
                      break;
                    ++v143;
                    --v142;
                  }
                  while ( v142 );
                  v144 = 0x7FFFFFFF - v142;
                  if ( v142 )
                  {
                    v145 = v255;
                    if ( v255 >= (unsigned __int64)(v144 + 1) )
                      goto LABEL_271;
                    if ( (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(&hMem, (unsigned int)(v144 + 1), 0) )
                    {
                      v145 = v255;
                      v141 = TokenHandle;
LABEL_271:
                      v146 = hMem;
                      v147 = v145;
                      if ( v145 )
                      {
                        if ( (unsigned __int64)v145 > 0x7FFFFFFF )
                        {
                          v103 = -2147024809;
                          *(_WORD *)hMem = 0;
                        }
                        else
                        {
                          v148 = 2147483646;
                          do
                          {
                            if ( !v148 )
                              break;
                            if ( !*v141 )
                              break;
                            *v146++ = *v141++;
                            --v148;
                            --v147;
                          }
                          while ( v147 );
                          v149 = v146 - 1;
                          v103 = -2147024774;
                          if ( v147 )
                          {
                            v149 = v146;
                            v103 = 0;
                          }
                          *v149 = 0;
                        }
                        v141 = TokenHandle;
                      }
                      else
                      {
                        v103 = -2147024809;
                      }
                      LocalFree(v141);
                      if ( v103 >= 0 )
                      {
                        v98 = 0;
                        goto LABEL_283;
                      }
                      goto LABEL_312;
                    }
                    LocalFree(TokenHandle);
                  }
                  else
                  {
LABEL_311:
                    LOWORD(v103) = 87;
                    LocalFree(TokenHandle);
                  }
LABEL_312:
                  v98 = (unsigned __int16)v103;
                  goto LABEL_283;
                }
                v98 = 1627;
LABEL_283:
                if ( SLODWORD(pDestinationSid[1]) > 72 )
                  GlobalFree(pDestinationSid[0]);
                if ( v98 )
                {
                  CImpersonate::~CImpersonate((CImpersonate *)&v250);
                  if ( v255 <= 64 )
                    goto LABEL_529;
                  goto LABEL_528;
                }
                v150 = (WCHAR *)lpString;
                v151 = v268;
                if ( v268 )
                {
                  if ( (unsigned __int64)v268 > 0x7FFFFFFF )
                  {
                    *lpString = 0;
                  }
                  else
                  {
                    v152 = (WCHAR *)hMem;
                    v10 = 2147483646;
                    v153 = 2147483646;
                    do
                    {
                      if ( !v153 )
                        break;
                      if ( !*v152 )
                        break;
                      *v150++ = *v152++;
                      --v153;
                      --v151;
                    }
                    while ( v151 );
                    v154 = v150 - 1;
                    if ( v151 )
                      v154 = v150;
                    *v154 = 0;
                    if ( v151 && v268 && (unsigned __int64)v268 <= 0x7FFFFFFF )
                    {
                      v223 = v268;
                      v224 = lpString;
                      do
                      {
                        if ( !*v224 )
                          break;
                        ++v224;
                        --v223;
                      }
                      while ( v223 );
                      if ( v223 )
                      {
                        v225 = v268 - v223;
                        v226 = L"\\";
                        v227 = 2147483646;
                        v228 = (WCHAR *)&lpString[v225];
                        for ( i = v268 - v225; i; --i )
                        {
                          if ( !v227 )
                            break;
                          if ( !*v226 )
                            break;
                          *v228++ = *v226++;
                          --v227;
                        }
                        v230 = v228 - 1;
                        if ( i )
                          v230 = v228;
                        *v230 = 0;
                        if ( i )
                        {
                          if ( !v118 )
                          {
LABEL_549:
                            if ( v268 && (unsigned __int64)v268 <= 0x7FFFFFFF )
                            {
                              v231 = v268;
                              v232 = lpString;
                              do
                              {
                                if ( !*v232 )
                                  break;
                                ++v232;
                                --v231;
                              }
                              while ( v231 );
                              if ( v231 )
                              {
                                v233 = v268 - v231;
                                v234 = L"Software\\Microsoft\\Installer";
                                v235 = 2147483646;
                                v236 = (WCHAR *)&lpString[v233];
                                for ( j = v268 - v233; j; --j )
                                {
                                  if ( !v235 )
                                    break;
                                  if ( !*v234 )
                                    break;
                                  *v236++ = *v234++;
                                  --v235;
                                }
                                v238 = v236 - 1;
                                if ( j )
                                  v238 = v236;
                                *v238 = 0;
                                if ( j )
                                {
                                  v6 = v252;
                                  v9 = L"\\";
                                  v17 = -2147483645;
                                  goto LABEL_10;
                                }
                              }
                            }
                            if ( v255 > 64 )
LABEL_498:
                              GlobalFree(hMem);
LABEL_499:
                            hMem = v257;
                            v255 = 64;
                            if ( v268 <= 260 )
                              return 1627;
                            goto LABEL_79;
                          }
                          EnterCriticalSection(&g_csImpersonationLock);
                          v239 = g_dwImpersonationSlot;
                          LeaveCriticalSection(&g_csImpersonationLock);
                          if ( v239 != -1 )
                          {
                            Value = (unsigned int)TlsGetValue(g_dwImpersonationSlot);
                            if ( (Value & 0xE0000000) != 0x80000000 )
                            {
                              v241 = (void *)Value;
                              v242 = Value & 0x1FFFFFFF;
                              if ( TlsSetValue(
                                     v239,
                                     (LPVOID)(Value & 0xE0000000
                                            | (unsigned __int64)(((Value & 0x1FFFFFFF) - 1) & 0x1FFFFFFF))) )
                              {
                                if ( v242 != 1 || SetThreadToken(0, 0) )
                                  goto LABEL_569;
                                TlsSetValue(v239, v241);
                              }
                              ExitProcessIfNotClient();
                            }
                          }
LABEL_569:
                          v16 = 0;
                          goto LABEL_549;
                        }
                      }
                    }
                  }
                }
                if ( !v118 )
                  goto LABEL_75;
                EnterCriticalSection(&g_csImpersonationLock);
                v99 = g_dwImpersonationSlot;
                LeaveCriticalSection(&g_csImpersonationLock);
                if ( v99 == -1 )
                  goto LABEL_75;
                v155 = (unsigned int)TlsGetValue(g_dwImpersonationSlot);
                if ( (v155 & 0xE0000000) == 0x80000000 )
                  goto LABEL_75;
                v101 = (void *)v155;
                v156 = v155 & 0x1FFFFFFF;
                if ( !TlsSetValue(
                        v99,
                        (LPVOID)(v155 & 0xE0000000 | (unsigned __int64)(((v155 & 0x1FFFFFFF) - 1) & 0x1FFFFFFF))) )
                  goto LABEL_178;
                if ( v156 != 1 || SetThreadToken(0, 0) )
                  goto LABEL_75;
LABEL_177:
                TlsSetValue(v99, v101);
LABEL_178:
                ExitProcessIfNotClient();
                goto LABEL_75;
              }
LABEL_618:
              v98 = LastError;
              goto LABEL_283;
            }
LABEL_257:
            if ( LastError )
            {
              v16 = 0;
              goto LABEL_618;
            }
            goto LABEL_258;
          }
          lpVtbl = CMsiTransaction::m_pMsiTransaction[5].lpVtbl;
        }
        TokenHandle = lpVtbl;
        LastError = 0;
        if ( lpVtbl )
          goto LABEL_257;
        goto LABEL_305;
      }
      v118 = 0;
      v251 = 0;
      v119 = (g_scServerContext == 3) + 2;
      EnterCriticalSection(&g_csImpersonationLock);
      v120 = g_dwImpersonationSlot;
      if ( g_dwImpersonationSlot == -1 )
      {
        g_dwImpersonationSlot = TlsAlloc();
        v120 = g_dwImpersonationSlot;
        if ( g_dwImpersonationSlot == -1 )
        {
          LeaveCriticalSection(&g_csImpersonationLock);
          if ( (unsigned int)(g_scServerContext - 2) <= 1 )
            goto LABEL_348;
          goto LABEL_246;
        }
      }
      LeaveCriticalSection(&g_csImpersonationLock);
      v121 = (unsigned int)TlsGetValue(v120);
      v122 = v121;
      v123 = v121 >> 29;
      if ( v121 >> 29 == 4 )
        goto LABEL_245;
      v124 = v121 & 0x1FFFFFFF;
      if ( g_scServerContext == 3 && v119 == 2 )
        v119 = 3;
      v125 = v121;
      if ( v123 )
      {
        v126 = v123 - 1;
        if ( v126 )
        {
          if ( v126 == 2 )
            v119 = 3;
        }
        else
        {
          v119 = 1;
        }
      }
      else
      {
        v125 = v119 << 29;
        v124 = 0;
      }
      if ( !TlsSetValue(v120, (LPVOID)(v125 & 0xE0000000 | (unsigned __int64)((v124 + 1) & 0x1FFFFFFF))) )
        goto LABEL_244;
      if ( v119 == 2 )
      {
        v127 = (struct IUnknownVtbl *)Token;
        if ( Token )
          goto LABEL_229;
        if ( g_scServerContext == 2 )
        {
          if ( !CMsiTransaction::m_pMsiTransaction )
            goto LABEL_243;
          v127 = CMsiTransaction::m_pMsiTransaction[5].lpVtbl;
        }
        if ( v127 )
        {
LABEL_229:
          if ( SetThreadToken(0, v127) )
          {
LABEL_230:
            v118 = 1;
            v251 = 1;
LABEL_231:
            v250 = v124;
LABEL_246:
            v16 = 0;
            goto LABEL_247;
          }
          goto LABEL_243;
        }
        if ( g_scServerContext != 2 )
        {
          v118 = 0;
          goto LABEL_231;
        }
LABEL_243:
        TlsSetValue(v120, (LPVOID)v122);
LABEL_244:
        ExitProcessIfNotClient();
LABEL_245:
        v118 = 0;
        goto LABEL_246;
      }
      v132 = v119 - 1;
      if ( !v132 )
      {
        if ( !(unsigned int)OLE32::CoImpersonateClient() )
          goto LABEL_230;
        goto LABEL_243;
      }
      if ( v132 != 2 )
        goto LABEL_243;
      v173 = (char *)*((_QWORD *)g_pCustomActionContext + 15);
      if ( (unsigned __int64)(v173 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        if ( SetThreadToken(0, v173) )
          goto LABEL_230;
        goto LABEL_243;
      }
      v174 = *((_DWORD *)g_pCustomActionContext + 25);
      if ( g_fWoW )
      {
        if ( v174 <= 9 )
        {
          v175 = 642;
          if ( _bittest(&v175, v174) )
            goto LABEL_404;
        }
      }
      else if ( v174 <= 8 )
      {
        v244 = 321;
        if ( _bittest(&v244, v174) )
          goto LABEL_404;
      }
      ExitProcessIfNotClient();
LABEL_404:
      TlsSetValue(v120, (LPVOID)v122);
      goto LABEL_245;
    }
    TokenHandle = 0;
    if ( !ConvertSidToStringSidW(pDestinationSid[0], (LPWSTR *)&TokenHandle) )
    {
      CurrentUserSID = 1627;
      goto LABEL_201;
    }
    v105 = (wchar_t *)TokenHandle;
    if ( TokenHandle )
    {
      v106 = 0x7FFFFFFF;
      v107 = TokenHandle;
      do
      {
        if ( !*v107 )
          break;
        ++v107;
        --v106;
      }
      while ( v106 );
      LOWORD(CurrentUserSID) = 87;
      v108 = 0x7FFFFFFF - v106;
      if ( v106 )
      {
        v109 = v264;
        if ( v264 < (unsigned __int64)(v108 + 1) )
        {
          if ( !(unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(
                                   &TokenInformation,
                                   (unsigned int)(v108 + 1),
                                   0) )
          {
            LOWORD(CurrentUserSID) = 14;
            LocalFree(TokenHandle);
            goto LABEL_321;
          }
          v109 = v264;
          v105 = (wchar_t *)TokenHandle;
        }
        v110 = TokenInformation;
        v111 = v109;
        if ( v109 )
        {
          if ( (unsigned __int64)v109 > 0x7FFFFFFF )
          {
            CurrentUserSID = -2147024809;
            *TokenInformation = 0;
          }
          else
          {
            v112 = 2147483646;
            do
            {
              if ( !v112 )
                break;
              if ( !*v105 )
                break;
              *v110++ = *v105++;
              --v112;
              --v111;
            }
            while ( v111 );
            v113 = v110 - 1;
            CurrentUserSID = -2147024774;
            if ( v111 )
            {
              v113 = v110;
              CurrentUserSID = 0;
            }
            *v113 = 0;
          }
          v105 = (wchar_t *)TokenHandle;
        }
        else
        {
          CurrentUserSID = -2147024809;
        }
        LocalFree(v105);
        if ( CurrentUserSID >= 0 )
        {
          CurrentUserSID = 0;
          goto LABEL_201;
        }
LABEL_321:
        CurrentUserSID = (unsigned __int16)CurrentUserSID;
        goto LABEL_201;
      }
    }
    else
    {
      LOWORD(CurrentUserSID) = 87;
    }
    LocalFree(TokenHandle);
    goto LABEL_321;
  }
  EnterCriticalSection(&g_csPolicyTableLock);
  EnterCriticalSection(&g_csPolicyTableLock);
  v16 = 0;
  if ( !g_pPolicyTable )
  {
    g_pPolicyTable = GlobalAlloc(0x40u, 0x4D8u);
    v161 = g_pPolicyTable;
    if ( !g_pPolicyTable )
    {
      LeaveCriticalSection(&g_csPolicyTableLock);
      goto LABEL_387;
    }
    v162 = &off_18025D9D0;
    v163 = 9;
    do
    {
      v161 += 8;
      v164 = *(_OWORD *)v162;
      v162 += 16;
      *(v161 - 8) = v164;
      *(v161 - 7) = *((_OWORD *)v162 - 7);
      *(v161 - 6) = *((_OWORD *)v162 - 6);
      *(v161 - 5) = *((_OWORD *)v162 - 5);
      *(v161 - 4) = *((_OWORD *)v162 - 4);
      *(v161 - 3) = *((_OWORD *)v162 - 3);
      *(v161 - 2) = *((_OWORD *)v162 - 2);
      *(v161 - 1) = *((_OWORD *)v162 - 1);
      --v163;
    }
    while ( v163 );
    *v161 = *(_OWORD *)v162;
    v161[1] = *((_OWORD *)v162 + 1);
    v161[2] = *((_OWORD *)v162 + 2);
    v161[3] = *((_OWORD *)v162 + 3);
    v161[4] = *((_OWORD *)v162 + 4);
    *((_QWORD *)v161 + 10) = v162[10];
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
        LeaveCriticalSection(&g_csPolicyTableLock);
LABEL_87:
        if ( !v55 )
        {
          v16 = 0;
          goto LABEL_89;
        }
        if ( v255 > 64 )
          GlobalFree(hMem);
        hMem = v257;
        v255 = 64;
        if ( v268 > 260 )
          GlobalFree((HGLOBAL)lpString);
        return 2;
      }
      if ( v54 != -2 || PopulateDefaultValuesInPolicyTable() )
      {
        v55 = v53[6];
        v259 = &v261;
        *(_OWORD *)pDestinationSid = 0;
        v261 = 0;
        v260 = 1;
        InitializeCriticalSection(&CriticalSection);
        EnterCriticalSection(&CriticalSection);
        if ( pDestinationSid[0] )
        {
          RegCloseKey((HKEY)pDestinationSid[0]);
          pDestinationSid[0] = 0;
          *v259 = 0;
        }
        LeaveCriticalSection(&CriticalSection);
        if ( !OpenPolicyKey((HKEY *)pDestinationSid, 1) )
        {
          v176 = *(const WCHAR **)v53;
          TokenInformation = (wchar_t *)v266;
          v264 = 40;
          v265 = 40;
          if ( !(unsigned int)MsiRegQueryValueExW((HKEY)pDestinationSid[0], v176, (__int64)&TokenInformation, 0)
            && *(_DWORD *)TokenInformation >= v53[7]
            && *(_DWORD *)TokenInformation <= v53[8] )
          {
            v55 = *(_DWORD *)TokenInformation;
          }
          if ( v264 > 40 )
            GlobalFree(TokenInformation);
          v264 = 40;
          TokenInformation = (wchar_t *)v266;
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
        CRegHandle::~CRegHandle((CRegHandle *)pDestinationSid);
        LeaveCriticalSection(&g_csPolicyTableLock);
        v9 = L"\\";
        goto LABEL_87;
      }
    }
  }
LABEL_387:
  LeaveCriticalSection(&g_csPolicyTableLock);
LABEL_89:
  v56 = (WCHAR *)lpString;
  v57 = v268;
  if ( !v268 )
    goto LABEL_75;
  if ( (unsigned __int64)v268 > 0x7FFFFFFF )
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
  if ( !v57 || !v268 || (unsigned __int64)v268 > 0x7FFFFFFF )
    goto LABEL_75;
  v61 = v268;
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
  v63 = v268 - v61;
  v64 = (WCHAR *)&lpString[v63];
  v65 = 2147483646;
  v66 = L"\\";
  for ( k = v268 - v63; k; --k )
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
    if ( v268 && (unsigned __int64)v268 <= 0x7FFFFFFF )
    {
      v215 = v268;
      v216 = lpString;
      do
      {
        if ( !*v216 )
          break;
        ++v216;
        --v215;
      }
      while ( v215 );
      v217 = v268 - v215;
      if ( v215 )
      {
        v218 = (WCHAR *)&lpString[v217];
        v219 = 2147483646;
        for ( m = v268 - v217; m; --m )
        {
          if ( !v219 )
            break;
          if ( !*v8 )
            break;
          *v218++ = *v8++;
          --v219;
        }
        v221 = v218 - 1;
        if ( m )
          v221 = v218;
        *v221 = 0;
        if ( m )
          goto LABEL_431;
      }
    }
    if ( v255 > 64 )
      goto LABEL_498;
    goto LABEL_499;
  }
  v69 = dword_180306D40;
  v250 = 0;
  if ( dword_180306D40 == -1 )
  {
    TokenHandle = (HANDLE)-1LL;
    v208 = GetCurrentThread();
    if ( OpenThreadToken(v208, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (HANDLE)-1LL;
    }
    *(_QWORD *)ReturnLength = 0;
    v209 = GetCurrentProcess();
    if ( OpenProcessToken(v209, 8u, (PHANDLE)ReturnLength) )
    {
      v222 = IsLocalSystemToken(*(void **)ReturnLength);
      CloseHandle(*(HANDLE *)ReturnLength);
      dword_180306D40 = v222;
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
    if ( TokenHandle != (HANDLE)-1LL )
    {
      if ( !SetThreadToken(0, TokenHandle) )
        ExitProcessIfNotClient();
      CloseHandle(TokenHandle);
    }
    v69 = dword_180306D40;
  }
  if ( g_scServerContext == 2 || v69 )
  {
    v70 = 0;
    v251 = 0;
    v71 = (g_scServerContext == 3) + 2;
    EnterCriticalSection(&g_csImpersonationLock);
    v72 = g_dwImpersonationSlot;
    if ( g_dwImpersonationSlot == -1 )
    {
      g_dwImpersonationSlot = TlsAlloc();
      v72 = g_dwImpersonationSlot;
      if ( g_dwImpersonationSlot == -1 )
      {
        LeaveCriticalSection(&g_csImpersonationLock);
        if ( (unsigned int)(g_scServerContext - 2) <= 1 )
LABEL_348:
          ExitProcess(0xFFFFFFFF);
        goto LABEL_130;
      }
    }
    LeaveCriticalSection(&g_csImpersonationLock);
    v73 = (unsigned int)TlsGetValue(v72);
    v74 = v73;
    v75 = v73 >> 29;
    if ( v73 >> 29 == 4 )
      goto LABEL_491;
    v76 = v73 & 0x1FFFFFFF;
    if ( g_scServerContext == 3 && v71 == 2 )
      v71 = 3;
    v77 = v73;
    if ( v75 )
    {
      v78 = v75 - 1;
      if ( v78 )
      {
        if ( v78 == 2 )
          v71 = 3;
      }
      else
      {
        v71 = 1;
      }
    }
    else
    {
      v77 = v71 << 29;
      v76 = 0;
    }
    if ( !TlsSetValue(v72, (LPVOID)(v77 & 0xE0000000 | (unsigned __int64)((v76 + 1) & 0x1FFFFFFF))) )
      goto LABEL_495;
    if ( v71 == 2 )
    {
      v79 = (struct IUnknownVtbl *)Token;
      if ( Token )
        goto LABEL_127;
      if ( g_scServerContext == 2 )
      {
        if ( !CMsiTransaction::m_pMsiTransaction )
          goto LABEL_494;
        v79 = CMsiTransaction::m_pMsiTransaction[5].lpVtbl;
      }
      if ( v79 )
      {
LABEL_127:
        if ( SetThreadToken(0, v79) )
        {
LABEL_128:
          v70 = 1;
          v251 = 1;
LABEL_129:
          v250 = v76;
LABEL_130:
          v16 = 0;
          goto LABEL_131;
        }
        goto LABEL_494;
      }
      if ( g_scServerContext != 2 )
      {
        v70 = 0;
        goto LABEL_129;
      }
LABEL_494:
      TlsSetValue(v72, (LPVOID)v74);
LABEL_495:
      ExitProcessIfNotClient();
      v70 = 0;
      goto LABEL_130;
    }
    v213 = v71 - 1;
    if ( !v213 )
    {
      if ( !(unsigned int)OLE32::CoImpersonateClient() )
        goto LABEL_128;
      goto LABEL_494;
    }
    if ( v213 != 2 )
      goto LABEL_494;
    v210 = (char *)*((_QWORD *)g_pCustomActionContext + 15);
    if ( (unsigned __int64)(v210 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( SetThreadToken(0, v210) )
        goto LABEL_128;
      goto LABEL_494;
    }
    v211 = *((_DWORD *)g_pCustomActionContext + 25);
    if ( g_fWoW )
    {
      if ( v211 <= 9 )
      {
        v212 = 642;
        if ( _bittest(&v212, v211) )
          goto LABEL_490;
      }
    }
    else if ( v211 <= 8 )
    {
      v243 = 321;
      if ( _bittest(&v243, v211) )
        goto LABEL_490;
    }
    ExitProcessIfNotClient();
LABEL_490:
    TlsSetValue(v72, (LPVOID)v74);
LABEL_491:
    v70 = 0;
    goto LABEL_130;
  }
  v70 = 0;
  v251 = 0;
LABEL_131:
  v256 = 64;
  pDestinationSid[0] = &v259;
  pDestinationSid[1] = (PSID)0x4800000048LL;
  TokenHandle = 0;
  v81 = RunningAsLocalSystem();
  if ( v81 == -1 )
  {
    v86 = 5;
    goto LABEL_644;
  }
  v82 = g_scServerContext;
  v83 = 0;
  if ( g_scServerContext == 2 || v81 == 1 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    if ( g_dwImpersonationSlot != -1 )
      v83 = (unsigned int)TlsGetValue(g_dwImpersonationSlot) >> 29;
    LeaveCriticalSection(&g_csImpersonationLock);
    v82 = g_scServerContext;
  }
  if ( v82 == 2 && v83 == 1 )
  {
    CCoImpersonate::CCoImpersonate((CCoImpersonate *)ReturnLength, v80);
    v86 = OpenUserToken(&TokenHandle, v214);
    v85 = v86 == 0;
    if ( LOBYTE(ReturnLength[1]) )
      StopImpersonateCore(1);
    goto LABEL_141;
  }
  v84 = (struct IUnknownVtbl *)Token;
  v85 = 0;
  if ( !Token && v82 == 2 )
  {
    if ( !CMsiTransaction::m_pMsiTransaction )
    {
      TokenHandle = 0;
      goto LABEL_460;
    }
    v84 = CMsiTransaction::m_pMsiTransaction[5].lpVtbl;
  }
  TokenHandle = v84;
  v86 = 0;
  if ( v84 )
  {
LABEL_141:
    if ( !v86 )
      goto LABEL_142;
    v16 = 0;
LABEL_644:
    v98 = v86;
    goto LABEL_167;
  }
LABEL_460:
  v86 = 0;
  v202 = GetCurrentThread();
  if ( !OpenThreadToken(v202, 0xCu, 1, &TokenHandle) )
  {
    v86 = GetLastError();
    if ( v86 == 1008 )
    {
      v86 = 0;
      v203 = GetCurrentProcess();
      if ( !OpenProcessToken(v203, 0xCu, &TokenHandle) )
        v86 = GetLastError();
    }
  }
  if ( v86 )
    goto LABEL_141;
  v85 = 1;
LABEL_142:
  v87 = pDestinationSid[0];
  ReturnLength[0] = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x58u, ReturnLength) )
  {
    if ( CopySid(0x48u, v87, TokenInformation) )
      v86 = 0;
    else
      v86 = GetLastError();
  }
  else
  {
    v246 = GetLastError();
    v86 = v246;
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"GetTokenInformation failed with error %d",
        (const unsigned __int16 *)v246,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
  }
  if ( v85 )
    CloseHandle(TokenHandle);
  v16 = 0;
  if ( v86 )
    goto LABEL_644;
  TokenHandle = 0;
  if ( ConvertSidToStringSidW(pDestinationSid[0], (LPWSTR *)&TokenHandle) )
  {
    v88 = TokenHandle;
    if ( TokenHandle )
    {
      v89 = 0x7FFFFFFF;
      v90 = TokenHandle;
      do
      {
        if ( !*v90 )
          break;
        ++v90;
        --v89;
      }
      while ( v89 );
      LOWORD(v91) = 87;
      v92 = 0x7FFFFFFF - v89;
      if ( v89 )
      {
        v93 = v255;
        if ( v255 >= (unsigned __int64)(v92 + 1) )
          goto LABEL_155;
        if ( (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(&hMem, (unsigned int)(v92 + 1), 0) )
        {
          v93 = v255;
          v88 = TokenHandle;
LABEL_155:
          v94 = hMem;
          v95 = v93;
          if ( v93 )
          {
            if ( (unsigned __int64)v93 > 0x7FFFFFFF )
            {
              v91 = -2147024809;
              *(_WORD *)hMem = 0;
            }
            else
            {
              v96 = 2147483646;
              do
              {
                if ( !v96 )
                  break;
                if ( !*v88 )
                  break;
                *v94++ = *v88++;
                --v96;
                --v95;
              }
              while ( v95 );
              v97 = v94 - 1;
              v91 = -2147024774;
              if ( v95 )
              {
                v97 = v94;
                v91 = 0;
              }
              *v97 = 0;
            }
            v88 = TokenHandle;
          }
          else
          {
            v91 = -2147024809;
          }
          LocalFree(v88);
          if ( v91 >= 0 )
          {
            v98 = 0;
            goto LABEL_167;
          }
          goto LABEL_468;
        }
        LOWORD(v91) = 14;
        LocalFree(TokenHandle);
LABEL_468:
        v98 = (unsigned __int16)v91;
        goto LABEL_167;
      }
    }
    else
    {
      LOWORD(v91) = 87;
    }
    LocalFree(TokenHandle);
    goto LABEL_468;
  }
  v98 = 1627;
LABEL_167:
  if ( SLODWORD(pDestinationSid[1]) > 72 )
    GlobalFree(pDestinationSid[0]);
  if ( v98 )
  {
    CImpersonate::~CImpersonate((CImpersonate *)&v250);
    if ( v255 <= 64 )
    {
LABEL_529:
      hMem = v257;
      v255 = 64;
      if ( v268 > 260 )
        GlobalFree((HGLOBAL)lpString);
      return v98;
    }
LABEL_528:
    GlobalFree(hMem);
    goto LABEL_529;
  }
  if ( !v268 || (unsigned __int64)v268 > 0x7FFFFFFF )
    goto LABEL_654;
  v178 = v268;
  v179 = lpString;
  do
  {
    if ( !*v179 )
      break;
    ++v179;
    --v178;
  }
  while ( v178 );
  if ( !v178 )
    goto LABEL_654;
  v180 = v268 - v178;
  v181 = (WCHAR *)hMem;
  v10 = 2147483646;
  v182 = (WCHAR *)&lpString[v180];
  v183 = 2147483646;
  for ( n = v268 - v180; n; --n )
  {
    if ( !v183 )
      break;
    if ( !*v181 )
      break;
    *v182++ = *v181++;
    --v183;
  }
  v185 = v182 - 1;
  if ( n )
    v185 = v182;
  *v185 = 0;
  if ( !n )
  {
LABEL_654:
    if ( !v70 )
      goto LABEL_75;
    EnterCriticalSection(&g_csImpersonationLock);
    v99 = g_dwImpersonationSlot;
    LeaveCriticalSection(&g_csImpersonationLock);
    if ( v99 == -1 )
      goto LABEL_75;
    v100 = (unsigned int)TlsGetValue(g_dwImpersonationSlot);
    if ( (v100 & 0xE0000000) == 0x80000000 )
      goto LABEL_75;
    v101 = (void *)v100;
    v102 = v100 & 0x1FFFFFFF;
    if ( !TlsSetValue(v99, (LPVOID)(v100 & 0xE0000000 | (unsigned __int64)(((v100 & 0x1FFFFFFF) - 1) & 0x1FFFFFFF))) )
      goto LABEL_178;
    if ( v102 != 1 || SetThreadToken(0, 0) )
      goto LABEL_75;
    goto LABEL_177;
  }
  if ( v70 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    v204 = g_dwImpersonationSlot;
    LeaveCriticalSection(&g_csImpersonationLock);
    if ( v204 == -1 )
      goto LABEL_474;
    v205 = (unsigned int)TlsGetValue(g_dwImpersonationSlot);
    if ( (v205 & 0xE0000000) == 0x80000000 )
      goto LABEL_474;
    v206 = (void *)v205;
    v207 = v205 & 0x1FFFFFFF;
    if ( TlsSetValue(v204, (LPVOID)(v205 & 0xE0000000 | (unsigned __int64)(((v205 & 0x1FFFFFFF) - 1) & 0x1FFFFFFF))) )
    {
      if ( v207 != 1 || SetThreadToken(0, 0) )
        goto LABEL_474;
      TlsSetValue(v204, v206);
    }
    ExitProcessIfNotClient();
LABEL_474:
    v16 = 0;
  }
  v9 = L"\\";
LABEL_431:
  if ( !v268 || (unsigned __int64)v268 > 0x7FFFFFFF )
    goto LABEL_75;
  v186 = v268;
  v187 = lpString;
  do
  {
    if ( !*v187 )
      break;
    ++v187;
    --v186;
  }
  while ( v186 );
  if ( !v186 )
    goto LABEL_75;
  v188 = v268 - v186;
  v189 = (WCHAR *)&lpString[v188];
  v190 = 2147483646;
  v191 = L"\\";
  for ( ii = v268 - v188; ii; --ii )
  {
    if ( !v190 )
      break;
    if ( !*v191 )
      break;
    *v189++ = *v191++;
    --v190;
  }
  v193 = v189 - 1;
  if ( ii )
    v193 = v189;
  *v193 = 0;
  if ( !ii || !v268 || (unsigned __int64)v268 > 0x7FFFFFFF )
    goto LABEL_75;
  v194 = v268;
  v195 = lpString;
  do
  {
    if ( !*v195 )
      break;
    ++v195;
    --v194;
  }
  while ( v194 );
  if ( !v194 )
    goto LABEL_75;
  v196 = v268 - v194;
  v197 = L"Installer";
  v17 = -2147483646;
  v198 = (WCHAR *)&lpString[v196];
  v199 = 2147483646;
  for ( jj = v268 - v196; jj; --jj )
  {
    if ( !v199 )
      break;
    if ( !*v197 )
      break;
    *v198++ = *v197++;
    --v199;
  }
  v201 = v198 - 1;
  if ( jj )
    v201 = v198;
  *v201 = 0;
  if ( !jj )
    goto LABEL_75;
  v6 = v252;
LABEL_10:
  if ( a3 )
  {
    if ( !v268 || (unsigned __int64)v268 > 0x7FFFFFFF )
      goto LABEL_12;
    v18 = v268;
    v19 = lpString;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v18;
    }
    while ( v18 );
    if ( !v18 )
      goto LABEL_12;
    v20 = v268 - v18;
    v21 = (WCHAR *)&lpString[v20];
    v22 = 2147483646;
    v23 = L"\\";
    for ( kk = v268 - v20; kk; --kk )
    {
      if ( !v22 )
        break;
      if ( !*v23 )
        break;
      *v21++ = *v23++;
      --v22;
    }
    v25 = v21 - 1;
    if ( kk )
      v25 = v21;
    *v25 = 0;
    if ( !kk || !v268 || (unsigned __int64)v268 > 0x7FFFFFFF )
      goto LABEL_12;
    v26 = v268;
    v27 = lpString;
    do
    {
      if ( !*v27 )
        break;
      ++v27;
      --v26;
    }
    while ( v26 );
    v28 = v268 - v26;
    if ( !v26 )
      goto LABEL_12;
    v29 = (WCHAR *)&lpString[v28];
    v30 = 2147483646;
    for ( mm = v268 - v28; mm; --mm )
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
      if ( v255 > 64 )
        GlobalFree(hMem);
      hMem = v257;
      goto LABEL_78;
    }
    if ( !v6 )
    {
LABEL_232:
      v128 = v253;
      v129 = lpString;
      EnterCriticalSection(v253 + 1);
      if ( v128->DebugInfo )
      {
        RegCloseKey((HKEY)v128->DebugInfo);
        v128->DebugInfo = 0;
        *(_WORD *)v128->OwningThread = 0;
      }
      LeaveCriticalSection(v128 + 1);
      v130 = g_samRead;
      if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
        LODWORD(v130) = g_samRead | 0x100;
      v131 = ((__int64 (__fastcall *)(__int64, const WCHAR *, _QWORD, __int64, struct _RTL_CRITICAL_SECTION *))RegOpenKeyAPI)(
               v17,
               v129,
               0,
               v130,
               v128);
      if ( v131 )
      {
        if ( v255 > 64 )
          GlobalFree(hMem);
        hMem = v257;
        v255 = 64;
        if ( v268 > 260 )
          GlobalFree((HGLOBAL)lpString);
        return v131;
      }
      else
      {
        if ( a6 )
        {
          v159 = v17 & 0xFFFFFFFF7FFFFFFFuLL;
          if ( v129 )
            v16 = lstrlenW(v129);
          v160 = (unsigned int)(v16 + lstrlenW(off_18025DEA8[v159]) + 1);
          if ( (SLODWORD(v128->LockSemaphore) >= (unsigned __int64)(int)v160
             || (unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v128->OwningThread, v160, 0))
            && (int)StringCchCopyW(
                      (unsigned __int16 *)v128->OwningThread,
                      SLODWORD(v128->LockSemaphore),
                      off_18025DEA8[v159]) >= 0
            && (!v129
             || (int)StringCchCatW((unsigned __int16 *)v128->OwningThread, SLODWORD(v128->LockSemaphore), v129) >= 0) )
          {
            *(_QWORD *)&v128->LockCount = v17;
          }
          else
          {
            *(_WORD *)v128->OwningThread = 0;
          }
        }
        if ( v255 > 64 )
          GlobalFree(hMem);
        hMem = v257;
        v255 = 64;
        if ( v268 > 260 )
          GlobalFree((HGLOBAL)lpString);
        return 0;
      }
    }
    v33 = lstrlenW(lpString);
    v34 = lstrlenW(v6) + v33 + 2;
    v35 = v34;
    if ( v34 <= 260 )
    {
      v36 = (const WCHAR *)v269;
      goto LABEL_43;
    }
    v36 = (const WCHAR *)GlobalAlloc(0x40u, 2LL * v34);
    if ( v36 )
    {
LABEL_43:
      v37 = (WCHAR *)lpString;
      if ( lpString == v36 )
        goto LABEL_44;
      v247 = v268;
      if ( v34 < v268 )
        v247 = v34;
      if ( !v247 )
      {
LABEL_44:
        v38 = v34;
      }
      else
      {
        do
        {
          --v247;
          v36[v247] = v37[v247];
          v37 = (WCHAR *)lpString;
        }
        while ( v247 );
        v38 = v34;
      }
      if ( v37 == (WCHAR *)v269 )
        v35 = v38;
      else
        GlobalFree(v37);
      lpString = v36;
      v268 = v34;
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
      if ( !nn || !v268 || (unsigned __int64)v268 > 0x7FFFFFFF )
        goto LABEL_75;
      v46 = v268;
      v47 = lpString;
      do
      {
        if ( !*v47 )
          break;
        ++v47;
        --v46;
      }
      while ( v46 );
      v48 = v268 - v46;
      if ( !v46 )
        goto LABEL_75;
      v49 = (WCHAR *)&lpString[v48];
      for ( i1 = v268 - v48; i1; --i1 )
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
      goto LABEL_232;
    }
    if ( v255 > 64 )
      GlobalFree(hMem);
    hMem = v257;
    v255 = 64;
    if ( v268 > 260 )
      GlobalFree((HGLOBAL)lpString);
    return 14;
  }
  else
  {
    if ( v255 > 64 )
      GlobalFree(hMem);
    hMem = v257;
    v255 = 64;
    if ( v268 > 260 )
      GlobalFree((HGLOBAL)lpString);
    return 87;
  }
}

```

## disassembly

```asm
0x1800227d0  mov     [rsp-8+arg_0], rbx
0x1800227d5  push    rbp
0x1800227d6  push    rsi
0x1800227d7  push    rdi
0x1800227d8  push    r12
0x1800227da  push    r13
0x1800227dc  push    r14
0x1800227de  push    r15
0x1800227e0  lea     rbp, [rsp-340h]
0x1800227e8  sub     rsp, 440h
0x1800227ef  mov     rax, cs:__security_cookie
0x1800227f6  xor     rax, rsp
0x1800227f9  mov     [rbp+370h+var_40], rax
0x180022800  mov     rax, [rbp+370h+arg_20]
0x180022807  mov     r12, r9
0x18002280a  mov     [rbp+370h+var_3F0], rax
0x18002280e  lea     rax, [rbp+370h+var_250]
0x180022815  mov     [rbp+370h+lpString], rax
0x18002281c  lea     rax, [rbp+370h+var_3D0]
0x180022820  mov     [rbp+370h+hMem], rax
0x180022824  mov     rdi, r8
0x180022827  mov     [rsp+470h+var_3F8], r9
0x18002282c  mov     r15, rdx
0x18002282f  mov     [rbp+370h+var_258], 104h
0x180022839  lea     r14, asc_18026F7A4; "\\"
0x180022840  mov     [rbp+370h+var_3D8], 40h ; '@'
0x180022847  cmp     ecx, 2
0x18002284a  jnz     loc_180022BE6
0x180022850  mov     r13d, 7FFFFFFEh
0x180022856  lea     rdx, aSoftwareClasse_0; "Software\\Classes\\Installer"
0x18002285d  mov     ecx, r13d
0x180022860  lea     r9, [rbp+370h+var_250]
0x180022867  mov     r8d, 104h
0x18002286d  nop     dword ptr [rax]
0x180022870  test    rcx, rcx
0x180022873  jz      short loc_180022892
0x180022875  movzx   eax, word ptr [rdx]
0x180022878  test    ax, ax
0x18002287b  jz      short loc_180022892
0x18002287d  mov     [r9], ax
0x180022881  add     rdx, 2
0x180022885  add     r9, 2
0x180022889  dec     rcx
0x18002288c  sub     r8, 1
0x180022890  jnz     short loc_180022870
0x180022892  test    r8, r8
0x180022895  lea     rax, [r9-2]
0x180022899  cmovnz  rax, r9
0x18002289d  xor     esi, esi
0x18002289f  mov     [rax], si
0x1800228a2  test    r8, r8
0x1800228a5  jz      loc_180022B7F
0x1800228ab  mov     r15, 0FFFFFFFF80000002h
0x1800228b2  test    rdi, rdi
0x1800228b5  jz      loc_180023FAF
0x1800228bb  movsxd  rax, [rbp+370h+var_258]
0x1800228c2  test    eax, eax
0x1800228c4  jnz     short loc_1800228E3
0x1800228c6  cmp     [rbp+370h+var_3D8], 40h ; '@'
0x1800228ca  jle     short loc_1800228D6
0x1800228cc  mov     rcx, [rbp+370h+hMem]; hMem
0x1800228d0  call    cs:__imp_GlobalFree
0x1800228d6  lea     rcx, [rbp+370h+var_3D0]
0x1800228da  mov     [rbp+370h+hMem], rcx
0x1800228de  jmp     loc_180022B97
0x1800228e3  mov     r9, rax
0x1800228e6  cmp     rax, 7FFFFFFFh
0x1800228ec  ja      short loc_1800228C6
0x1800228ee  mov     r10, [rbp+370h+lpString]
0x1800228f5  mov     rcx, rax
0x1800228f8  mov     rax, r10
0x1800228fb  mov     r8, rcx
0x1800228fe  xchg    ax, ax
0x180022900  cmp     word ptr [rax], 0
0x180022904  jz      short loc_180022910
0x180022906  add     rax, 2
0x18002290a  sub     rcx, 1
0x18002290e  jnz     short loc_180022900
0x180022910  sub     r8, rcx
0x180022913  mov     rdx, rsi
0x180022916  test    rcx, rcx
0x180022919  cmovnz  rdx, r8
0x18002291d  jz      short loc_1800228C6
0x18002291f  lea     rcx, [r10+rdx*2]
0x180022923  mov     rax, r13
0x180022926  mov     r8, r14
0x180022929  sub     r9, rdx
0x18002292c  jz      short loc_180022952
0x18002292e  xchg    ax, ax
0x180022930  test    rax, rax
0x180022933  jz      short loc_180022952
0x180022935  movzx   edx, word ptr [r8]
0x180022939  test    dx, dx
0x18002293c  jz      short loc_180022952
0x18002293e  mov     [rcx], dx
0x180022941  add     r8, 2
0x180022945  add     rcx, 2
0x180022949  dec     rax
0x18002294c  sub     r9, 1
0x180022950  jnz     short loc_180022930
0x180022952  test    r9, r9
0x180022955  lea     rax, [rcx-2]
0x180022959  cmovnz  rax, rcx
0x18002295d  mov     [rax], si
0x180022960  jz      loc_1800228C6
0x180022966  movsxd  rax, [rbp+370h+var_258]
0x18002296d  test    eax, eax
0x18002296f  jz      loc_1800228C6
0x180022975  mov     r8, rax
0x180022978  cmp     rax, 7FFFFFFFh
0x18002297e  ja      loc_1800228C6
0x180022984  mov     r10, [rbp+370h+lpString]
0x18002298b  mov     rcx, rax
0x18002298e  mov     rax, r10
0x180022991  mov     r9, rcx
0x180022994  cmp     word ptr [rax], 0
0x180022998  jz      short loc_1800229A4
0x18002299a  add     rax, 2
0x18002299e  sub     rcx, 1
0x1800229a2  jnz     short loc_180022994
0x1800229a4  sub     r9, rcx
0x1800229a7  mov     rdx, rsi
0x1800229aa  test    rcx, rcx
0x1800229ad  cmovnz  rdx, r9
0x1800229b1  jz      loc_1800228C6
0x1800229b7  lea     rcx, [r10+rdx*2]
0x1800229bb  mov     rax, r13
0x1800229be  sub     r8, rdx
0x1800229c1  jz      short loc_1800229E4
0x1800229c3  test    rax, rax
0x1800229c6  jz      short loc_1800229E4
0x1800229c8  movzx   edx, word ptr [rdi]
0x1800229cb  test    dx, dx
0x1800229ce  jz      short loc_1800229E4
0x1800229d0  mov     [rcx], dx
0x1800229d3  add     rdi, 2
0x1800229d7  add     rcx, 2
0x1800229db  dec     rax
0x1800229de  sub     r8, 1
0x1800229e2  jnz     short loc_1800229C3
0x1800229e4  test    r8, r8
0x1800229e7  lea     rax, [rcx-2]
0x1800229eb  cmovnz  rax, rcx
0x1800229ef  mov     [rax], si
0x1800229f2  jz      loc_1800228C6
0x1800229f8  test    r12, r12
0x1800229fb  jz      loc_1800234C4
0x180022a01  mov     rcx, [rbp+370h+lpString]; lpString
0x180022a08  call    cs:__imp_lstrlenW
0x180022a0e  mov     rcx, r12; lpString
0x180022a11  mov     edi, eax
0x180022a13  call    cs:__imp_lstrlenW
0x180022a19  add     edi, 2
0x180022a1c  add     edi, eax
0x180022a1e  movsxd  rbx, edi
0x180022a21  cmp     edi, 104h
0x180022a27  jg      loc_180024AAA
0x180022a2d  lea     rsi, [rbp+370h+var_250]
0x180022a34  mov     rdx, [rbp+370h+lpString]
0x180022a3b  cmp     rdx, rsi
0x180022a3e  jnz     loc_180024F4D
0x180022a44  mov     rax, rbx
0x180022a47  lea     rcx, [rbp+370h+var_250]
0x180022a4e  cmp     rdx, rcx
0x180022a51  jnz     loc_180024F88
0x180022a57  mov     rbx, rax
0x180022a5a  mov     [rbp+370h+lpString], rsi
0x180022a61  mov     [rbp+370h+var_258], edi
0x180022a67  test    edi, edi
0x180022a69  jz      loc_180022B7F
0x180022a6f  cmp     rbx, 7FFFFFFFh
0x180022a76  ja      loc_180022B7F
0x180022a7c  mov     rcx, rbx
0x180022a7f  mov     rax, rsi
0x180022a82  mov     rdx, rbx
0x180022a85  test    rbx, rbx
0x180022a88  jz      short loc_180022AA0
0x180022a8a  nop     word ptr [rax+rax+00h]
0x180022a90  cmp     word ptr [rax], 0
0x180022a94  jz      short loc_180022AA4
0x180022a96  add     rax, 2
0x180022a9a  sub     rcx, 1
0x180022a9e  jnz     short loc_180022A90
0x180022aa0  xor     edx, edx
0x180022aa2  jmp     short loc_180022AA7
0x180022aa4  sub     rdx, rcx
0x180022aa7  test    rcx, rcx
0x180022aaa  jz      loc_180022B7F
0x180022ab0  lea     rcx, [rsi+rdx*2]
0x180022ab4  mov     rax, r13
0x180022ab7  sub     rbx, rdx
0x180022aba  jz      short loc_180022AE2
0x180022abc  nop     dword ptr [rax+00h]
0x180022ac0  test    rax, rax
0x180022ac3  jz      short loc_180022AE2
0x180022ac5  movzx   edx, word ptr [r14]
0x180022ac9  test    dx, dx
0x180022acc  jz      short loc_180022AE2
0x180022ace  mov     [rcx], dx
0x180022ad1  add     r14, 2
0x180022ad5  add     rcx, 2
0x180022ad9  dec     rax
0x180022adc  sub     rbx, 1
0x180022ae0  jnz     short loc_180022AC0
0x180022ae2  test    rbx, rbx
0x180022ae5  lea     rax, [rcx-2]
0x180022ae9  cmovnz  rax, rcx
0x180022aed  xor     esi, esi
0x180022aef  mov     [rax], si
0x180022af2  test    rbx, rbx
0x180022af5  jz      loc_180022B7F
0x180022afb  movsxd  rax, [rbp+370h+var_258]
0x180022b02  test    eax, eax
0x180022b04  jz      short loc_180022B7F
0x180022b06  mov     rdx, rax
0x180022b09  cmp     rax, 7FFFFFFFh
0x180022b0f  ja      short loc_180022B7F
0x180022b11  mov     r9, [rbp+370h+lpString]
0x180022b18  mov     rcx, rax
0x180022b1b  mov     rax, r9
0x180022b1e  mov     r8, rcx
0x180022b21  cmp     [rax], si
0x180022b24  jz      short loc_180022B30
0x180022b26  add     rax, 2
0x180022b2a  sub     rcx, 1
0x180022b2e  jnz     short loc_180022B21
0x180022b30  sub     r8, rcx
0x180022b33  mov     rax, rsi
0x180022b36  test    rcx, rcx
0x180022b39  cmovnz  rax, r8
0x180022b3d  jz      short loc_180022B7F
0x180022b3f  lea     rcx, [r9+rax*2]
0x180022b43  sub     rdx, rax
0x180022b46  jz      short loc_180022B6B
0x180022b48  test    r13, r13
0x180022b4b  jz      short loc_180022B6B
0x180022b4d  movzx   eax, word ptr [r12]
0x180022b52  test    ax, ax
0x180022b55  jz      short loc_180022B6B
0x180022b57  mov     [rcx], ax
0x180022b5a  add     r12, 2
0x180022b5e  add     rcx, 2
0x180022b62  dec     r13
0x180022b65  sub     rdx, 1
0x180022b69  jnz     short loc_180022B48
0x180022b6b  test    rdx, rdx
0x180022b6e  lea     rax, [rcx-2]
0x180022b72  cmovnz  rax, rcx
0x180022b76  mov     [rax], si
0x180022b79  jnz     loc_1800234C4
0x180022b7f  cmp     [rbp+370h+var_3D8], 40h ; '@'
0x180022b83  jle     short loc_180022B8F
0x180022b85  mov     rcx, [rbp+370h+hMem]; hMem
0x180022b89  call    cs:__imp_GlobalFree
0x180022b8f  lea     rax, [rbp+370h+var_3D0]
0x180022b93  mov     [rbp+370h+hMem], rax
0x180022b97  cmp     [rbp+370h+var_258], 104h
0x180022ba1  mov     [rbp+370h+var_3D8], 40h ; '@'
0x180022ba8  jle     short loc_180022BB7
0x180022baa  mov     rcx, [rbp+370h+lpString]; hMem
0x180022bb1  call    cs:__imp_GlobalFree
0x180022bb7  mov     eax, 65Bh
0x180022bbc  mov     rcx, [rbp+370h+var_40]
0x180022bc3  xor     rcx, rsp; StackCookie
0x180022bc6  call    __security_check_cookie
0x180022bcb  mov     rbx, [rsp+470h+arg_0]
0x180022bd3  add     rsp, 440h
0x180022bda  pop     r15
0x180022bdc  pop     r14
0x180022bde  pop     r13
0x180022be0  pop     r12
0x180022be2  pop     rdi
0x180022be3  pop     rsi
0x180022be4  pop     rbp
0x180022be5  retn
0x180022be6  test    ecx, ecx
0x180022be8  jnz     loc_18002317F
0x180022bee  lea     rcx, ?g_csPolicyTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180022bf5  call    cs:__imp_EnterCriticalSection
0x180022bfb  lea     rcx, ?g_csPolicyTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180022c02  call    cs:__imp_EnterCriticalSection
0x180022c08  xor     esi, esi
0x180022c0a  lea     r12, aNull; "(NULL)"
0x180022c11  cmp     cs:?g_pPolicyTable@@3PEAUPolicyEntry@@EA, rsi; PolicyEntry * g_pPolicyTable
0x180022c18  jz      loc_180023AC5
0x180022c1e  lea     rcx, ?g_csPolicyTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180022c25  call    cs:__imp_LeaveCriticalSection
0x180022c2b  mov     rbx, cs:?g_pPolicyTable@@3PEAUPolicyEntry@@EA; PolicyEntry * g_pPolicyTable
0x180022c32  cmp     [rbx], rsi
0x180022c35  jz      loc_180023FFE
0x180022c3b  mov     eax, [rbx+18h]
0x180022c3e  cmp     eax, 0FFFFFFFFh
0x180022c41  jz      loc_180023FFE
0x180022c47  cmp     qword ptr [rbx+8], 1
0x180022c4c  jnz     loc_180023DA8
0x180022c52  mov     esi, [rbx+10h]
0x180022c55  lea     rcx, ?g_csPolicyTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180022c5c  call    cs:__imp_LeaveCriticalSection
0x180022c62  test    esi, esi
0x180022c64  jnz     loc_180024010
  ... truncated ...
```
