# OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)

- ea: `0x1800227d0`
- end: `0x180024f96`
- name: `?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z`
- size: `10182`
- prototype: `__int64 __fastcall(int, const wchar_t *, WCHAR *, const WCHAR *, struct _RTL_CRITICAL_SECTION *, char)`
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
  int v80; // ecx
  int v81; // eax
  unsigned int v82; // ebx
  struct IUnknownVtbl *v83; // rcx
  bool v84; // si
  DWORD v85; // ebx
  PSID v86; // rbx
  _WORD *v87; // r9
  __int64 v88; // rcx
  _WORD *v89; // rax
  int v90; // r12d
  __int64 v91; // rdx
  int v92; // r10d
  _WORD *v93; // r8
  __int64 v94; // rdx
  __int64 v95; // rcx
  _WORD *v96; // rax
  unsigned int v97; // r13d
  DWORD v98; // edi
  unsigned int v99; // ecx
  void *v100; // rsi
  int v101; // ebx
  int v102; // r12d
  int CurrentUserSID; // ebx
  wchar_t *v104; // r8
  __int64 v105; // rcx
  _WORD *v106; // rax
  __int64 v107; // rdx
  int v108; // r10d
  wchar_t *v109; // r9
  __int64 v110; // rdx
  __int64 v111; // rcx
  wchar_t *v112; // rax
  _DWORD *v113; // rbx
  int v114; // eax
  unsigned int v115; // esi
  int v116; // eax
  char v117; // r14
  int v118; // ebx
  DWORD v119; // esi
  unsigned int v120; // eax
  unsigned int v121; // r14d
  unsigned int v122; // ecx
  int v123; // r15d
  unsigned int v124; // r8d
  unsigned int v125; // ecx
  struct IUnknownVtbl *v126; // rdx
  struct _RTL_CRITICAL_SECTION *v127; // r12
  const WCHAR *v128; // rdi
  __int64 v129; // r9
  unsigned int v130; // ebx
  int v131; // ebx
  int v132; // ecx
  int v133; // eax
  unsigned int v134; // ebx
  struct IUnknownVtbl *lpVtbl; // rcx
  bool v136; // si
  DWORD LastError; // ebx
  PSID v138; // rbx
  _WORD *v139; // r9
  __int64 v140; // rcx
  _WORD *v141; // rax
  __int64 v142; // rdx
  int v143; // r10d
  _WORD *v144; // r8
  __int64 v145; // rdx
  __int64 v146; // rcx
  _WORD *v147; // rax
  WCHAR *v148; // r9
  __int64 v149; // rcx
  WCHAR *v150; // r8
  __int64 v151; // rdx
  WCHAR *v152; // rax
  unsigned int v153; // ecx
  int v154; // ebx
  HANDLE v155; // rax
  HANDLE v156; // rax
  unsigned __int64 v157; // rbx
  __int64 v158; // rdx
  _OWORD *v159; // rcx
  wchar_t **v160; // rax
  __int64 v161; // rdx
  __int128 v162; // xmm0
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  _OWORD *v165; // rcx
  wchar_t **v166; // rax
  __int64 v167; // rdx
  __int128 v168; // xmm0
  bool *v169; // rdx
  BOOL v170; // ebx
  char *v171; // rdx
  unsigned int v172; // eax
  int v173; // ecx
  const WCHAR *v174; // rdx
  const WCHAR *v175; // rdx
  __int64 v176; // rcx
  LPCWSTR v177; // rax
  __int64 v178; // rax
  WCHAR *v179; // rdx
  WCHAR *v180; // r8
  __int64 v181; // rcx
  __int64 n; // r9
  WCHAR *v183; // rax
  __int64 v184; // rdx
  LPCWSTR v185; // rax
  __int64 v186; // r8
  WCHAR *v187; // rdx
  __int64 v188; // rax
  const unsigned __int16 *v189; // r9
  __int64 ii; // rcx
  WCHAR *v191; // rax
  __int64 v192; // rdx
  LPCWSTR v193; // rax
  __int64 v194; // r8
  const unsigned __int16 *v195; // r9
  WCHAR *v196; // rdx
  __int64 v197; // rax
  __int64 jj; // rcx
  WCHAR *v199; // rax
  HANDLE v200; // rax
  HANDLE v201; // rax
  DWORD v202; // esi
  unsigned int v203; // ecx
  void *v204; // r14
  int v205; // ebx
  HANDLE v206; // rax
  HANDLE v207; // rax
  char *v208; // rdx
  unsigned int v209; // eax
  int v210; // ecx
  int v211; // ebx
  bool *v212; // rdx
  __int64 v213; // rdx
  LPCWSTR v214; // rax
  __int64 v215; // r9
  WCHAR *v216; // rdx
  __int64 v217; // rax
  __int64 m; // rcx
  WCHAR *v219; // rax
  BOOL v220; // ebx
  __int64 v221; // rcx
  LPCWSTR v222; // rax
  __int64 v223; // rax
  const unsigned __int16 *v224; // r8
  __int64 v225; // rcx
  WCHAR *v226; // r9
  __int64 i; // rdx
  WCHAR *v228; // rax
  __int64 v229; // rdx
  LPCWSTR v230; // rax
  __int64 v231; // r8
  const wchar_t *v232; // r9
  __int64 v233; // rax
  WCHAR *v234; // rdx
  __int64 j; // rcx
  WCHAR *v236; // rax
  DWORD v237; // esi
  unsigned int Value; // ecx
  void *v239; // r14
  int v240; // ebx
  int v241; // ecx
  int v242; // ecx
  DWORD v243; // eax
  DWORD v244; // eax
  int v245; // r8d
  HANDLE TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  DWORD ReturnLength[2]; // [rsp+68h] [rbp-98h] BYREF
  int v248; // [rsp+70h] [rbp-90h] BYREF
  char v249; // [rsp+74h] [rbp-8Ch]
  const WCHAR *v250; // [rsp+78h] [rbp-88h]
  struct _RTL_CRITICAL_SECTION *v251; // [rsp+80h] [rbp-80h]
  HGLOBAL hMem; // [rsp+90h] [rbp-70h] BYREF
  int v253; // [rsp+98h] [rbp-68h]
  int v254; // [rsp+9Ch] [rbp-64h]
  _BYTE v255[128]; // [rsp+A0h] [rbp-60h] BYREF
  PSID pDestinationSid[2]; // [rsp+120h] [rbp+20h] BYREF
  __int16 *v257; // [rsp+130h] [rbp+30h] BYREF
  int v258; // [rsp+138h] [rbp+38h]
  __int16 v259; // [rsp+140h] [rbp+40h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+148h] [rbp+48h] BYREF
  wchar_t *TokenInformation; // [rsp+180h] [rbp+80h] BYREF
  int v262; // [rsp+188h] [rbp+88h]
  int v263; // [rsp+18Ch] [rbp+8Ch]
  _BYTE v264[128]; // [rsp+190h] [rbp+90h] BYREF
  LPCWSTR lpString; // [rsp+210h] [rbp+110h]
  int v266; // [rsp+218h] [rbp+118h]
  _BYTE v267[528]; // [rsp+220h] [rbp+120h] BYREF

  v6 = a4;
  v251 = a5;
  lpString = (LPCWSTR)v267;
  hMem = v255;
  v250 = a4;
  v8 = a2;
  v266 = 260;
  v9 = L"\\";
  v253 = 64;
  if ( a1 == 2 )
  {
    v10 = 2147483646;
    v11 = L"Software\\Classes\\Installer";
    v12 = 2147483646;
    v13 = v267;
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
    if ( v253 > 64 )
      GlobalFree(hMem);
    hMem = v255;
LABEL_78:
    v253 = 64;
    if ( v266 <= 260 )
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
    LOWORD(v102) = 14;
    if ( !a2 )
      goto LABEL_207;
    v262 = 64;
    TokenInformation = (wchar_t *)v264;
    v263 = 64;
    pDestinationSid[0] = &v257;
    pDestinationSid[1] = (PSID)0x4800000048LL;
    CurrentUserSID = GetCurrentUserSID(pDestinationSid);
    if ( CurrentUserSID )
    {
LABEL_201:
      if ( SLODWORD(pDestinationSid[1]) > 72 )
        GlobalFree(pDestinationSid[0]);
      if ( CurrentUserSID || _wcsicmp(v8, TokenInformation) )
      {
        if ( v262 > 64 )
          GlobalFree(TokenInformation);
        if ( v253 > 64 )
LABEL_316:
          GlobalFree(hMem);
LABEL_317:
        hMem = v255;
        v253 = 64;
        if ( v266 > 260 )
        {
          GlobalFree((HGLOBAL)lpString);
          return 2;
        }
        return 2;
      }
      if ( v262 > 64 )
        GlobalFree(TokenInformation);
LABEL_207:
      EnterCriticalSection(&g_csPolicyTableLock);
      EnterCriticalSection(&g_csPolicyTableLock);
      if ( !g_pPolicyTable )
      {
        g_pPolicyTable = GlobalAlloc(0x40u, 0x4D8u);
        v165 = g_pPolicyTable;
        if ( !g_pPolicyTable )
        {
          LeaveCriticalSection(&g_csPolicyTableLock);
          goto LABEL_394;
        }
        v166 = &off_18025D9D0;
        v167 = 9;
        do
        {
          v165 += 8;
          v168 = *(_OWORD *)v166;
          v166 += 16;
          *(v165 - 8) = v168;
          *(v165 - 7) = *((_OWORD *)v166 - 7);
          *(v165 - 6) = *((_OWORD *)v166 - 6);
          *(v165 - 5) = *((_OWORD *)v166 - 5);
          *(v165 - 4) = *((_OWORD *)v166 - 4);
          *(v165 - 3) = *((_OWORD *)v166 - 3);
          *(v165 - 2) = *((_OWORD *)v166 - 2);
          *(v165 - 1) = *((_OWORD *)v166 - 1);
          --v167;
        }
        while ( v167 );
        *v165 = *(_OWORD *)v166;
        v165[1] = *((_OWORD *)v166 + 1);
        v165[2] = *((_OWORD *)v166 + 2);
        v165[3] = *((_OWORD *)v166 + 3);
        v165[4] = *((_OWORD *)v166 + 4);
        *((_QWORD *)v165 + 10) = v166[10];
      }
      LeaveCriticalSection(&g_csPolicyTableLock);
      v113 = g_pPolicyTable;
      if ( *(_QWORD *)g_pPolicyTable )
      {
        v114 = *((_DWORD *)g_pPolicyTable + 6);
        if ( v114 != -1 )
        {
          if ( *((_QWORD *)g_pPolicyTable + 1) == 1 )
          {
            v115 = *((_DWORD *)g_pPolicyTable + 4);
            goto LABEL_212;
          }
          if ( v114 != -2 || PopulateDefaultValuesInPolicyTable() )
          {
            v115 = v113[6];
            v257 = &v259;
            *(_OWORD *)pDestinationSid = 0;
            v259 = 0;
            v258 = 1;
            InitializeCriticalSection(&CriticalSection);
            EnterCriticalSection(&CriticalSection);
            if ( pDestinationSid[0] )
            {
              RegCloseKey((HKEY)pDestinationSid[0]);
              pDestinationSid[0] = 0;
              *v257 = 0;
            }
            LeaveCriticalSection(&CriticalSection);
            if ( !OpenPolicyKey((HKEY *)pDestinationSid, 1) )
            {
              v175 = *(const WCHAR **)v113;
              TokenInformation = (wchar_t *)v264;
              v262 = 40;
              v263 = 40;
              if ( !(unsigned int)MsiRegQueryValueExW((HKEY)pDestinationSid[0], v175, (__int64)&TokenInformation, 0)
                && *(_DWORD *)TokenInformation >= v113[7]
                && *(_DWORD *)TokenInformation <= v113[8] )
              {
                v115 = *(_DWORD *)TokenInformation;
              }
              if ( v262 > 40 )
                GlobalFree(TokenInformation);
              v262 = 40;
              TokenInformation = (wchar_t *)v264;
            }
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                L"%s policy value '%s' is %u",
                L"Machine",
                *(const unsigned __int16 **)v113,
                (const unsigned __int16 *)v115,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            *((_QWORD *)v113 + 2) = v115;
            *((_QWORD *)v113 + 1) = 1;
            CRegHandle::~CRegHandle((CRegHandle *)pDestinationSid);
LABEL_212:
            LeaveCriticalSection(&g_csPolicyTableLock);
            if ( !v115 )
            {
              v16 = 0;
              goto LABEL_214;
            }
            if ( v253 > 64 )
              goto LABEL_316;
            goto LABEL_317;
          }
        }
      }
LABEL_394:
      LeaveCriticalSection(&g_csPolicyTableLock);
LABEL_214:
      v116 = dword_180306D40;
      v248 = 0;
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
          v170 = IsLocalSystemToken(*(void **)ReturnLength);
          CloseHandle(*(HANDLE *)ReturnLength);
          dword_180306D40 = v170;
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
        v116 = dword_180306D40;
      }
      if ( g_scServerContext != 2 && !v116 )
      {
        v117 = 0;
        v249 = 0;
LABEL_247:
        v254 = 64;
        pDestinationSid[0] = &v257;
        pDestinationSid[1] = (PSID)0x4800000048LL;
        TokenHandle = 0;
        v132 = RunningAsLocalSystem();
        if ( v132 == -1 )
        {
          LastError = 5;
          goto LABEL_618;
        }
        v133 = g_scServerContext;
        v134 = 0;
        if ( g_scServerContext == 2 || v132 == 1 )
        {
          EnterCriticalSection(&g_csImpersonationLock);
          if ( g_dwImpersonationSlot != -1 )
            v134 = (unsigned int)TlsGetValue(g_dwImpersonationSlot) >> 29;
          LeaveCriticalSection(&g_csImpersonationLock);
          v133 = g_scServerContext;
        }
        if ( v133 == 2 && v134 == 1 )
        {
          CCoImpersonate::CCoImpersonate((CCoImpersonate *)ReturnLength);
          LastError = OpenUserToken(&TokenHandle, v169);
          v136 = LastError == 0;
          if ( LOBYTE(ReturnLength[1]) )
            StopImpersonateCore(1);
          goto LABEL_257;
        }
        lpVtbl = (struct IUnknownVtbl *)Token;
        v136 = 0;
        if ( !Token && v133 == 2 )
        {
          if ( !CMsiTransaction::m_pMsiTransaction )
          {
            TokenHandle = 0;
LABEL_305:
            LastError = 0;
            v155 = GetCurrentThread();
            if ( !OpenThreadToken(v155, 0xCu, 1, &TokenHandle) )
            {
              LastError = GetLastError();
              if ( LastError == 1008 )
              {
                LastError = 0;
                v156 = GetCurrentProcess();
                if ( !OpenProcessToken(v156, 0xCu, &TokenHandle) )
                  LastError = GetLastError();
              }
            }
            if ( !LastError )
            {
              v136 = 1;
LABEL_258:
              v138 = pDestinationSid[0];
              ReturnLength[0] = 0;
              if ( GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x58u, ReturnLength) )
              {
                if ( CopySid(0x48u, v138, TokenInformation) )
                  LastError = 0;
                else
                  LastError = GetLastError();
              }
              else
              {
                v243 = GetLastError();
                LastError = v243;
                if ( g_dmDiagnosticMode )
                  DebugString(
                    9,
                    0,
                    0,
                    L"GetTokenInformation failed with error %d",
                    (const unsigned __int16 *)v243,
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    0,
                    0);
              }
              if ( v136 )
                CloseHandle(TokenHandle);
              v16 = 0;
              if ( !LastError )
              {
                TokenHandle = 0;
                if ( ConvertSidToStringSidW(pDestinationSid[0], (LPWSTR *)&TokenHandle) )
                {
                  v139 = TokenHandle;
                  if ( !TokenHandle )
                    goto LABEL_311;
                  v140 = 0x7FFFFFFF;
                  v141 = TokenHandle;
                  do
                  {
                    if ( !*v141 )
                      break;
                    ++v141;
                    --v140;
                  }
                  while ( v140 );
                  v142 = 0x7FFFFFFF - v140;
                  if ( v140 )
                  {
                    v143 = v253;
                    if ( v253 >= (unsigned __int64)(v142 + 1) )
                      goto LABEL_271;
                    if ( (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(&hMem, (unsigned int)(v142 + 1), 0) )
                    {
                      v143 = v253;
                      v139 = TokenHandle;
LABEL_271:
                      v144 = hMem;
                      v145 = v143;
                      if ( v143 )
                      {
                        if ( (unsigned __int64)v143 > 0x7FFFFFFF )
                        {
                          v102 = -2147024809;
                          *(_WORD *)hMem = 0;
                        }
                        else
                        {
                          v146 = 2147483646;
                          do
                          {
                            if ( !v146 )
                              break;
                            if ( !*v139 )
                              break;
                            *v144++ = *v139++;
                            --v146;
                            --v145;
                          }
                          while ( v145 );
                          v147 = v144 - 1;
                          v102 = -2147024774;
                          if ( v145 )
                          {
                            v147 = v144;
                            v102 = 0;
                          }
                          *v147 = 0;
                        }
                        v139 = TokenHandle;
                      }
                      else
                      {
                        v102 = -2147024809;
                      }
                      LocalFree(v139);
                      if ( v102 >= 0 )
                      {
                        v97 = 0;
                        goto LABEL_283;
                      }
                      goto LABEL_312;
                    }
                    LocalFree(TokenHandle);
                  }
                  else
                  {
LABEL_311:
                    LOWORD(v102) = 87;
                    LocalFree(TokenHandle);
                  }
LABEL_312:
                  v97 = (unsigned __int16)v102;
                  goto LABEL_283;
                }
                v97 = 1627;
LABEL_283:
                if ( SLODWORD(pDestinationSid[1]) > 72 )
                  GlobalFree(pDestinationSid[0]);
                if ( v97 )
                {
                  CImpersonate::~CImpersonate((CImpersonate *)&v248);
                  if ( v253 <= 64 )
                    goto LABEL_529;
                  goto LABEL_528;
                }
                v148 = (WCHAR *)lpString;
                v149 = v266;
                if ( v266 )
                {
                  if ( (unsigned __int64)v266 > 0x7FFFFFFF )
                  {
                    *lpString = 0;
                  }
                  else
                  {
                    v150 = (WCHAR *)hMem;
                    v10 = 2147483646;
                    v151 = 2147483646;
                    do
                    {
                      if ( !v151 )
                        break;
                      if ( !*v150 )
                        break;
                      *v148++ = *v150++;
                      --v151;
                      --v149;
                    }
                    while ( v149 );
                    v152 = v148 - 1;
                    if ( v149 )
                      v152 = v148;
                    *v152 = 0;
                    if ( v149 && v266 && (unsigned __int64)v266 <= 0x7FFFFFFF )
                    {
                      v221 = v266;
                      v222 = lpString;
                      do
                      {
                        if ( !*v222 )
                          break;
                        ++v222;
                        --v221;
                      }
                      while ( v221 );
                      if ( v221 )
                      {
                        v223 = v266 - v221;
                        v224 = L"\\";
                        v225 = 2147483646;
                        v226 = (WCHAR *)&lpString[v223];
                        for ( i = v266 - v223; i; --i )
                        {
                          if ( !v225 )
                            break;
                          if ( !*v224 )
                            break;
                          *v226++ = *v224++;
                          --v225;
                        }
                        v228 = v226 - 1;
                        if ( i )
                          v228 = v226;
                        *v228 = 0;
                        if ( i )
                        {
                          if ( !v117 )
                          {
LABEL_549:
                            if ( v266 && (unsigned __int64)v266 <= 0x7FFFFFFF )
                            {
                              v229 = v266;
                              v230 = lpString;
                              do
                              {
                                if ( !*v230 )
                                  break;
                                ++v230;
                                --v229;
                              }
                              while ( v229 );
                              if ( v229 )
                              {
                                v231 = v266 - v229;
                                v232 = L"Software\\Microsoft\\Installer";
                                v233 = 2147483646;
                                v234 = (WCHAR *)&lpString[v231];
                                for ( j = v266 - v231; j; --j )
                                {
                                  if ( !v233 )
                                    break;
                                  if ( !*v232 )
                                    break;
                                  *v234++ = *v232++;
                                  --v233;
                                }
                                v236 = v234 - 1;
                                if ( j )
                                  v236 = v234;
                                *v236 = 0;
                                if ( j )
                                {
                                  v6 = v250;
                                  v9 = L"\\";
                                  v17 = -2147483645;
                                  goto LABEL_10;
                                }
                              }
                            }
                            if ( v253 > 64 )
LABEL_498:
                              GlobalFree(hMem);
LABEL_499:
                            hMem = v255;
                            v253 = 64;
                            if ( v266 <= 260 )
                              return 1627;
                            goto LABEL_79;
                          }
                          EnterCriticalSection(&g_csImpersonationLock);
                          v237 = g_dwImpersonationSlot;
                          LeaveCriticalSection(&g_csImpersonationLock);
                          if ( v237 != -1 )
                          {
                            Value = (unsigned int)TlsGetValue(g_dwImpersonationSlot);
                            if ( (Value & 0xE0000000) != 0x80000000 )
                            {
                              v239 = (void *)Value;
                              v240 = Value & 0x1FFFFFFF;
                              if ( TlsSetValue(
                                     v237,
                                     (LPVOID)(Value & 0xE0000000
                                            | (unsigned __int64)(((Value & 0x1FFFFFFF) - 1) & 0x1FFFFFFF))) )
                              {
                                if ( v240 != 1 || SetThreadToken(0, 0) )
                                  goto LABEL_569;
                                TlsSetValue(v237, v239);
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
                if ( !v117 )
                  goto LABEL_75;
                EnterCriticalSection(&g_csImpersonationLock);
                v98 = g_dwImpersonationSlot;
                LeaveCriticalSection(&g_csImpersonationLock);
                if ( v98 == -1 )
                  goto LABEL_75;
                v153 = (unsigned int)TlsGetValue(g_dwImpersonationSlot);
                if ( (v153 & 0xE0000000) == 0x80000000 )
                  goto LABEL_75;
                v100 = (void *)v153;
                v154 = v153 & 0x1FFFFFFF;
                if ( !TlsSetValue(
                        v98,
                        (LPVOID)(v153 & 0xE0000000 | (unsigned __int64)(((v153 & 0x1FFFFFFF) - 1) & 0x1FFFFFFF))) )
                  goto LABEL_178;
                if ( v154 != 1 || SetThreadToken(0, 0) )
                  goto LABEL_75;
LABEL_177:
                TlsSetValue(v98, v100);
LABEL_178:
                ExitProcessIfNotClient();
                goto LABEL_75;
              }
LABEL_618:
              v97 = LastError;
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
      v117 = 0;
      v249 = 0;
      v118 = (g_scServerContext == 3) + 2;
      EnterCriticalSection(&g_csImpersonationLock);
      v119 = g_dwImpersonationSlot;
      if ( g_dwImpersonationSlot == -1 )
      {
        g_dwImpersonationSlot = TlsAlloc();
        v119 = g_dwImpersonationSlot;
        if ( g_dwImpersonationSlot == -1 )
        {
          LeaveCriticalSection(&g_csImpersonationLock);
          if ( (unsigned int)(g_scServerContext - 2) <= 1 )
            goto LABEL_348;
          goto LABEL_246;
        }
      }
      LeaveCriticalSection(&g_csImpersonationLock);
      v120 = (unsigned int)TlsGetValue(v119);
      v121 = v120;
      v122 = v120 >> 29;
      if ( v120 >> 29 == 4 )
        goto LABEL_245;
      v123 = v120 & 0x1FFFFFFF;
      if ( g_scServerContext == 3 && v118 == 2 )
        v118 = 3;
      v124 = v120;
      if ( v122 )
      {
        v125 = v122 - 1;
        if ( v125 )
        {
          if ( v125 == 2 )
            v118 = 3;
        }
        else
        {
          v118 = 1;
        }
      }
      else
      {
        v124 = v118 << 29;
        v123 = 0;
      }
      if ( !TlsSetValue(v119, (LPVOID)(v124 & 0xE0000000 | (unsigned __int64)((v123 + 1) & 0x1FFFFFFF))) )
        goto LABEL_244;
      if ( v118 == 2 )
      {
        v126 = (struct IUnknownVtbl *)Token;
        if ( Token )
          goto LABEL_229;
        if ( g_scServerContext == 2 )
        {
          if ( !CMsiTransaction::m_pMsiTransaction )
            goto LABEL_243;
          v126 = CMsiTransaction::m_pMsiTransaction[5].lpVtbl;
        }
        if ( v126 )
        {
LABEL_229:
          if ( SetThreadToken(0, v126) )
          {
LABEL_230:
            v117 = 1;
            v249 = 1;
LABEL_231:
            v248 = v123;
LABEL_246:
            v16 = 0;
            goto LABEL_247;
          }
          goto LABEL_243;
        }
        if ( g_scServerContext != 2 )
        {
          v117 = 0;
          goto LABEL_231;
        }
LABEL_243:
        TlsSetValue(v119, (LPVOID)v121);
LABEL_244:
        ExitProcessIfNotClient();
LABEL_245:
        v117 = 0;
        goto LABEL_246;
      }
      v131 = v118 - 1;
      if ( !v131 )
      {
        if ( !(unsigned int)OLE32::CoImpersonateClient() )
          goto LABEL_230;
        goto LABEL_243;
      }
      if ( v131 != 2 )
        goto LABEL_243;
      v171 = (char *)*((_QWORD *)g_pCustomActionContext + 15);
      if ( (unsigned __int64)(v171 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        if ( SetThreadToken(0, v171) )
          goto LABEL_230;
        goto LABEL_243;
      }
      v172 = *((_DWORD *)g_pCustomActionContext + 25);
      if ( g_fWoW )
      {
        if ( v172 <= 9 )
        {
          v173 = 642;
          if ( _bittest(&v173, v172) )
            goto LABEL_404;
        }
      }
      else if ( v172 <= 8 )
      {
        v242 = 321;
        if ( _bittest(&v242, v172) )
          goto LABEL_404;
      }
      ExitProcessIfNotClient();
LABEL_404:
      TlsSetValue(v119, (LPVOID)v121);
      goto LABEL_245;
    }
    TokenHandle = 0;
    if ( !ConvertSidToStringSidW(pDestinationSid[0], (LPWSTR *)&TokenHandle) )
    {
      CurrentUserSID = 1627;
      goto LABEL_201;
    }
    v104 = (wchar_t *)TokenHandle;
    if ( TokenHandle )
    {
      v105 = 0x7FFFFFFF;
      v106 = TokenHandle;
      do
      {
        if ( !*v106 )
          break;
        ++v106;
        --v105;
      }
      while ( v105 );
      LOWORD(CurrentUserSID) = 87;
      v107 = 0x7FFFFFFF - v105;
      if ( v105 )
      {
        v108 = v262;
        if ( v262 < (unsigned __int64)(v107 + 1) )
        {
          if ( !(unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(
                                   &TokenInformation,
                                   (unsigned int)(v107 + 1),
                                   0) )
          {
            LOWORD(CurrentUserSID) = 14;
            LocalFree(TokenHandle);
            goto LABEL_321;
          }
          v108 = v262;
          v104 = (wchar_t *)TokenHandle;
        }
        v109 = TokenInformation;
        v110 = v108;
        if ( v108 )
        {
          if ( (unsigned __int64)v108 > 0x7FFFFFFF )
          {
            CurrentUserSID = -2147024809;
            *TokenInformation = 0;
          }
          else
          {
            v111 = 2147483646;
            do
            {
              if ( !v111 )
                break;
              if ( !*v104 )
                break;
              *v109++ = *v104++;
              --v111;
              --v110;
            }
            while ( v110 );
            v112 = v109 - 1;
            CurrentUserSID = -2147024774;
            if ( v110 )
            {
              v112 = v109;
              CurrentUserSID = 0;
            }
            *v112 = 0;
          }
          v104 = (wchar_t *)TokenHandle;
        }
        else
        {
          CurrentUserSID = -2147024809;
        }
        LocalFree(v104);
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
    v159 = g_pPolicyTable;
    if ( !g_pPolicyTable )
    {
      LeaveCriticalSection(&g_csPolicyTableLock);
      goto LABEL_387;
    }
    v160 = &off_18025D9D0;
    v161 = 9;
    do
    {
      v159 += 8;
      v162 = *(_OWORD *)v160;
      v160 += 16;
      *(v159 - 8) = v162;
      *(v159 - 7) = *((_OWORD *)v160 - 7);
      *(v159 - 6) = *((_OWORD *)v160 - 6);
      *(v159 - 5) = *((_OWORD *)v160 - 5);
      *(v159 - 4) = *((_OWORD *)v160 - 4);
      *(v159 - 3) = *((_OWORD *)v160 - 3);
      *(v159 - 2) = *((_OWORD *)v160 - 2);
      *(v159 - 1) = *((_OWORD *)v160 - 1);
      --v161;
    }
    while ( v161 );
    *v159 = *(_OWORD *)v160;
    v159[1] = *((_OWORD *)v160 + 1);
    v159[2] = *((_OWORD *)v160 + 2);
    v159[3] = *((_OWORD *)v160 + 3);
    v159[4] = *((_OWORD *)v160 + 4);
    *((_QWORD *)v159 + 10) = v160[10];
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
        if ( v253 > 64 )
          GlobalFree(hMem);
        hMem = v255;
        v253 = 64;
        if ( v266 > 260 )
          GlobalFree((HGLOBAL)lpString);
        return 2;
      }
      if ( v54 != -2 || PopulateDefaultValuesInPolicyTable() )
      {
        v55 = v53[6];
        v257 = &v259;
        *(_OWORD *)pDestinationSid = 0;
        v259 = 0;
        v258 = 1;
        InitializeCriticalSection(&CriticalSection);
        EnterCriticalSection(&CriticalSection);
        if ( pDestinationSid[0] )
        {
          RegCloseKey((HKEY)pDestinationSid[0]);
          pDestinationSid[0] = 0;
          *v257 = 0;
        }
        LeaveCriticalSection(&CriticalSection);
        if ( !OpenPolicyKey((HKEY *)pDestinationSid, 1) )
        {
          v174 = *(const WCHAR **)v53;
          TokenInformation = (wchar_t *)v264;
          v262 = 40;
          v263 = 40;
          if ( !(unsigned int)MsiRegQueryValueExW((HKEY)pDestinationSid[0], v174, (__int64)&TokenInformation, 0)
            && *(_DWORD *)TokenInformation >= v53[7]
            && *(_DWORD *)TokenInformation <= v53[8] )
          {
            v55 = *(_DWORD *)TokenInformation;
          }
          if ( v262 > 40 )
            GlobalFree(TokenInformation);
          v262 = 40;
          TokenInformation = (wchar_t *)v264;
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
  v57 = v266;
  if ( !v266 )
    goto LABEL_75;
  if ( (unsigned __int64)v266 > 0x7FFFFFFF )
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
  if ( !v57 || !v266 || (unsigned __int64)v266 > 0x7FFFFFFF )
    goto LABEL_75;
  v61 = v266;
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
  v63 = v266 - v61;
  v64 = (WCHAR *)&lpString[v63];
  v65 = 2147483646;
  v66 = L"\\";
  for ( k = v266 - v63; k; --k )
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
    if ( v266 && (unsigned __int64)v266 <= 0x7FFFFFFF )
    {
      v213 = v266;
      v214 = lpString;
      do
      {
        if ( !*v214 )
          break;
        ++v214;
        --v213;
      }
      while ( v213 );
      v215 = v266 - v213;
      if ( v213 )
      {
        v216 = (WCHAR *)&lpString[v215];
        v217 = 2147483646;
        for ( m = v266 - v215; m; --m )
        {
          if ( !v217 )
            break;
          if ( !*v8 )
            break;
          *v216++ = *v8++;
          --v217;
        }
        v219 = v216 - 1;
        if ( m )
          v219 = v216;
        *v219 = 0;
        if ( m )
          goto LABEL_431;
      }
    }
    if ( v253 > 64 )
      goto LABEL_498;
    goto LABEL_499;
  }
  v69 = dword_180306D40;
  v248 = 0;
  if ( dword_180306D40 == -1 )
  {
    TokenHandle = (HANDLE)-1LL;
    v206 = GetCurrentThread();
    if ( OpenThreadToken(v206, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (HANDLE)-1LL;
    }
    *(_QWORD *)ReturnLength = 0;
    v207 = GetCurrentProcess();
    if ( OpenProcessToken(v207, 8u, (PHANDLE)ReturnLength) )
    {
      v220 = IsLocalSystemToken(*(void **)ReturnLength);
      CloseHandle(*(HANDLE *)ReturnLength);
      dword_180306D40 = v220;
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
    v249 = 0;
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
          v249 = 1;
LABEL_129:
          v248 = v76;
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
    v211 = v71 - 1;
    if ( !v211 )
    {
      if ( !(unsigned int)OLE32::CoImpersonateClient() )
        goto LABEL_128;
      goto LABEL_494;
    }
    if ( v211 != 2 )
      goto LABEL_494;
    v208 = (char *)*((_QWORD *)g_pCustomActionContext + 15);
    if ( (unsigned __int64)(v208 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( SetThreadToken(0, v208) )
        goto LABEL_128;
      goto LABEL_494;
    }
    v209 = *((_DWORD *)g_pCustomActionContext + 25);
    if ( g_fWoW )
    {
      if ( v209 <= 9 )
      {
        v210 = 642;
        if ( _bittest(&v210, v209) )
          goto LABEL_490;
      }
    }
    else if ( v209 <= 8 )
    {
      v241 = 321;
      if ( _bittest(&v241, v209) )
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
  v249 = 0;
LABEL_131:
  v254 = 64;
  pDestinationSid[0] = &v257;
  pDestinationSid[1] = (PSID)0x4800000048LL;
  TokenHandle = 0;
  v80 = RunningAsLocalSystem();
  if ( v80 == -1 )
  {
    v85 = 5;
    goto LABEL_644;
  }
  v81 = g_scServerContext;
  v82 = 0;
  if ( g_scServerContext == 2 || v80 == 1 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    if ( g_dwImpersonationSlot != -1 )
      v82 = (unsigned int)TlsGetValue(g_dwImpersonationSlot) >> 29;
    LeaveCriticalSection(&g_csImpersonationLock);
    v81 = g_scServerContext;
  }
  if ( v81 == 2 && v82 == 1 )
  {
    CCoImpersonate::CCoImpersonate((CCoImpersonate *)ReturnLength);
    v85 = OpenUserToken(&TokenHandle, v212);
    v84 = v85 == 0;
    if ( LOBYTE(ReturnLength[1]) )
      StopImpersonateCore(1);
    goto LABEL_141;
  }
  v83 = (struct IUnknownVtbl *)Token;
  v84 = 0;
  if ( !Token && v81 == 2 )
  {
    if ( !CMsiTransaction::m_pMsiTransaction )
    {
      TokenHandle = 0;
      goto LABEL_460;
    }
    v83 = CMsiTransaction::m_pMsiTransaction[5].lpVtbl;
  }
  TokenHandle = v83;
  v85 = 0;
  if ( v83 )
  {
LABEL_141:
    if ( !v85 )
      goto LABEL_142;
    v16 = 0;
LABEL_644:
    v97 = v85;
    goto LABEL_167;
  }
LABEL_460:
  v85 = 0;
  v200 = GetCurrentThread();
  if ( !OpenThreadToken(v200, 0xCu, 1, &TokenHandle) )
  {
    v85 = GetLastError();
    if ( v85 == 1008 )
    {
      v85 = 0;
      v201 = GetCurrentProcess();
      if ( !OpenProcessToken(v201, 0xCu, &TokenHandle) )
        v85 = GetLastError();
    }
  }
  if ( v85 )
    goto LABEL_141;
  v84 = 1;
LABEL_142:
  v86 = pDestinationSid[0];
  ReturnLength[0] = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x58u, ReturnLength) )
  {
    if ( CopySid(0x48u, v86, TokenInformation) )
      v85 = 0;
    else
      v85 = GetLastError();
  }
  else
  {
    v244 = GetLastError();
    v85 = v244;
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"GetTokenInformation failed with error %d",
        (const unsigned __int16 *)v244,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
  }
  if ( v84 )
    CloseHandle(TokenHandle);
  v16 = 0;
  if ( v85 )
    goto LABEL_644;
  TokenHandle = 0;
  if ( ConvertSidToStringSidW(pDestinationSid[0], (LPWSTR *)&TokenHandle) )
  {
    v87 = TokenHandle;
    if ( TokenHandle )
    {
      v88 = 0x7FFFFFFF;
      v89 = TokenHandle;
      do
      {
        if ( !*v89 )
          break;
        ++v89;
        --v88;
      }
      while ( v88 );
      LOWORD(v90) = 87;
      v91 = 0x7FFFFFFF - v88;
      if ( v88 )
      {
        v92 = v253;
        if ( v253 >= (unsigned __int64)(v91 + 1) )
          goto LABEL_155;
        if ( (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(&hMem, (unsigned int)(v91 + 1), 0) )
        {
          v92 = v253;
          v87 = TokenHandle;
LABEL_155:
          v93 = hMem;
          v94 = v92;
          if ( v92 )
          {
            if ( (unsigned __int64)v92 > 0x7FFFFFFF )
            {
              v90 = -2147024809;
              *(_WORD *)hMem = 0;
            }
            else
            {
              v95 = 2147483646;
              do
              {
                if ( !v95 )
                  break;
                if ( !*v87 )
                  break;
                *v93++ = *v87++;
                --v95;
                --v94;
              }
              while ( v94 );
              v96 = v93 - 1;
              v90 = -2147024774;
              if ( v94 )
              {
                v96 = v93;
                v90 = 0;
              }
              *v96 = 0;
            }
            v87 = TokenHandle;
          }
          else
          {
            v90 = -2147024809;
          }
          LocalFree(v87);
          if ( v90 >= 0 )
          {
            v97 = 0;
            goto LABEL_167;
          }
          goto LABEL_468;
        }
        LOWORD(v90) = 14;
        LocalFree(TokenHandle);
LABEL_468:
        v97 = (unsigned __int16)v90;
        goto LABEL_167;
      }
    }
    else
    {
      LOWORD(v90) = 87;
    }
    LocalFree(TokenHandle);
    goto LABEL_468;
  }
  v97 = 1627;
LABEL_167:
  if ( SLODWORD(pDestinationSid[1]) > 72 )
    GlobalFree(pDestinationSid[0]);
  if ( v97 )
  {
    CImpersonate::~CImpersonate((CImpersonate *)&v248);
    if ( v253 <= 64 )
    {
LABEL_529:
      hMem = v255;
      v253 = 64;
      if ( v266 > 260 )
        GlobalFree((HGLOBAL)lpString);
      return v97;
    }
LABEL_528:
    GlobalFree(hMem);
    goto LABEL_529;
  }
  if ( !v266 || (unsigned __int64)v266 > 0x7FFFFFFF )
    goto LABEL_654;
  v176 = v266;
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
    goto LABEL_654;
  v178 = v266 - v176;
  v179 = (WCHAR *)hMem;
  v10 = 2147483646;
  v180 = (WCHAR *)&lpString[v178];
  v181 = 2147483646;
  for ( n = v266 - v178; n; --n )
  {
    if ( !v181 )
      break;
    if ( !*v179 )
      break;
    *v180++ = *v179++;
    --v181;
  }
  v183 = v180 - 1;
  if ( n )
    v183 = v180;
  *v183 = 0;
  if ( !n )
  {
LABEL_654:
    if ( !v70 )
      goto LABEL_75;
    EnterCriticalSection(&g_csImpersonationLock);
    v98 = g_dwImpersonationSlot;
    LeaveCriticalSection(&g_csImpersonationLock);
    if ( v98 == -1 )
      goto LABEL_75;
    v99 = (unsigned int)TlsGetValue(g_dwImpersonationSlot);
    if ( (v99 & 0xE0000000) == 0x80000000 )
      goto LABEL_75;
    v100 = (void *)v99;
    v101 = v99 & 0x1FFFFFFF;
    if ( !TlsSetValue(v98, (LPVOID)(v99 & 0xE0000000 | (unsigned __int64)(((v99 & 0x1FFFFFFF) - 1) & 0x1FFFFFFF))) )
      goto LABEL_178;
    if ( v101 != 1 || SetThreadToken(0, 0) )
      goto LABEL_75;
    goto LABEL_177;
  }
  if ( v70 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    v202 = g_dwImpersonationSlot;
    LeaveCriticalSection(&g_csImpersonationLock);
    if ( v202 == -1 )
      goto LABEL_474;
    v203 = (unsigned int)TlsGetValue(g_dwImpersonationSlot);
    if ( (v203 & 0xE0000000) == 0x80000000 )
      goto LABEL_474;
    v204 = (void *)v203;
    v205 = v203 & 0x1FFFFFFF;
    if ( TlsSetValue(v202, (LPVOID)(v203 & 0xE0000000 | (unsigned __int64)(((v203 & 0x1FFFFFFF) - 1) & 0x1FFFFFFF))) )
    {
      if ( v205 != 1 || SetThreadToken(0, 0) )
        goto LABEL_474;
      TlsSetValue(v202, v204);
    }
    ExitProcessIfNotClient();
LABEL_474:
    v16 = 0;
  }
  v9 = L"\\";
LABEL_431:
  if ( !v266 || (unsigned __int64)v266 > 0x7FFFFFFF )
    goto LABEL_75;
  v184 = v266;
  v185 = lpString;
  do
  {
    if ( !*v185 )
      break;
    ++v185;
    --v184;
  }
  while ( v184 );
  if ( !v184 )
    goto LABEL_75;
  v186 = v266 - v184;
  v187 = (WCHAR *)&lpString[v186];
  v188 = 2147483646;
  v189 = L"\\";
  for ( ii = v266 - v186; ii; --ii )
  {
    if ( !v188 )
      break;
    if ( !*v189 )
      break;
    *v187++ = *v189++;
    --v188;
  }
  v191 = v187 - 1;
  if ( ii )
    v191 = v187;
  *v191 = 0;
  if ( !ii || !v266 || (unsigned __int64)v266 > 0x7FFFFFFF )
    goto LABEL_75;
  v192 = v266;
  v193 = lpString;
  do
  {
    if ( !*v193 )
      break;
    ++v193;
    --v192;
  }
  while ( v192 );
  if ( !v192 )
    goto LABEL_75;
  v194 = v266 - v192;
  v195 = L"Installer";
  v17 = -2147483646;
  v196 = (WCHAR *)&lpString[v194];
  v197 = 2147483646;
  for ( jj = v266 - v194; jj; --jj )
  {
    if ( !v197 )
      break;
    if ( !*v195 )
      break;
    *v196++ = *v195++;
    --v197;
  }
  v199 = v196 - 1;
  if ( jj )
    v199 = v196;
  *v199 = 0;
  if ( !jj )
    goto LABEL_75;
  v6 = v250;
LABEL_10:
  if ( a3 )
  {
    if ( !v266 || (unsigned __int64)v266 > 0x7FFFFFFF )
      goto LABEL_12;
    v18 = v266;
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
    v20 = v266 - v18;
    v21 = (WCHAR *)&lpString[v20];
    v22 = 2147483646;
    v23 = L"\\";
    for ( kk = v266 - v20; kk; --kk )
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
    if ( !kk || !v266 || (unsigned __int64)v266 > 0x7FFFFFFF )
      goto LABEL_12;
    v26 = v266;
    v27 = lpString;
    do
    {
      if ( !*v27 )
        break;
      ++v27;
      --v26;
    }
    while ( v26 );
    v28 = v266 - v26;
    if ( !v26 )
      goto LABEL_12;
    v29 = (WCHAR *)&lpString[v28];
    v30 = 2147483646;
    for ( mm = v266 - v28; mm; --mm )
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
      if ( v253 > 64 )
        GlobalFree(hMem);
      hMem = v255;
      goto LABEL_78;
    }
    if ( !v6 )
    {
LABEL_232:
      v127 = v251;
      v128 = lpString;
      EnterCriticalSection(v251 + 1);
      if ( v127->DebugInfo )
      {
        RegCloseKey((HKEY)v127->DebugInfo);
        v127->DebugInfo = 0;
        *(_WORD *)v127->OwningThread = 0;
      }
      LeaveCriticalSection(v127 + 1);
      v129 = g_samRead;
      if ( !g_fWoW && g_fWinNT64 && (g_samRead & 0x100) == 0 )
        LODWORD(v129) = g_samRead | 0x100;
      v130 = ((__int64 (__fastcall *)(__int64, const WCHAR *, _QWORD, __int64, struct _RTL_CRITICAL_SECTION *))RegOpenKeyAPI)(
               v17,
               v128,
               0,
               v129,
               v127);
      if ( v130 )
      {
        if ( v253 > 64 )
          GlobalFree(hMem);
        hMem = v255;
        v253 = 64;
        if ( v266 > 260 )
          GlobalFree((HGLOBAL)lpString);
        return v130;
      }
      else
      {
        if ( a6 )
        {
          v157 = v17 & 0xFFFFFFFF7FFFFFFFuLL;
          if ( v128 )
            v16 = lstrlenW(v128);
          v158 = (unsigned int)(v16 + lstrlenW(off_18025DEA8[v157]) + 1);
          if ( (SLODWORD(v127->LockSemaphore) >= (unsigned __int64)(int)v158
             || (unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v127->OwningThread, v158, 0))
            && (int)StringCchCopyW(
                      (unsigned __int16 *)v127->OwningThread,
                      SLODWORD(v127->LockSemaphore),
                      off_18025DEA8[v157]) >= 0
            && (!v128
             || (int)StringCchCatW((unsigned __int16 *)v127->OwningThread, SLODWORD(v127->LockSemaphore), v128) >= 0) )
          {
            *(_QWORD *)&v127->LockCount = v17;
          }
          else
          {
            *(_WORD *)v127->OwningThread = 0;
          }
        }
        if ( v253 > 64 )
          GlobalFree(hMem);
        hMem = v255;
        v253 = 64;
        if ( v266 > 260 )
          GlobalFree((HGLOBAL)lpString);
        return 0;
      }
    }
    v33 = lstrlenW(lpString);
    v34 = lstrlenW(v6) + v33 + 2;
    v35 = v34;
    if ( v34 <= 260 )
    {
      v36 = (const WCHAR *)v267;
      goto LABEL_43;
    }
    v36 = (const WCHAR *)GlobalAlloc(0x40u, 2LL * v34);
    if ( v36 )
    {
LABEL_43:
      v37 = (WCHAR *)lpString;
      if ( lpString == v36 )
        goto LABEL_44;
      v245 = v266;
      if ( v34 < v266 )
        v245 = v34;
      if ( !v245 )
      {
LABEL_44:
        v38 = v34;
      }
      else
      {
        do
        {
          --v245;
          v36[v245] = v37[v245];
          v37 = (WCHAR *)lpString;
        }
        while ( v245 );
        v38 = v34;
      }
      if ( v37 == (WCHAR *)v267 )
        v35 = v38;
      else
        GlobalFree(v37);
      lpString = v36;
      v266 = v34;
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
      if ( !nn || !v266 || (unsigned __int64)v266 > 0x7FFFFFFF )
        goto LABEL_75;
      v46 = v266;
      v47 = lpString;
      do
      {
        if ( !*v47 )
          break;
        ++v47;
        --v46;
      }
      while ( v46 );
      v48 = v266 - v46;
      if ( !v46 )
        goto LABEL_75;
      v49 = (WCHAR *)&lpString[v48];
      for ( i1 = v266 - v48; i1; --i1 )
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
    if ( v253 > 64 )
      GlobalFree(hMem);
    hMem = v255;
    v253 = 64;
    if ( v266 > 260 )
      GlobalFree((HGLOBAL)lpString);
    return 14;
  }
  else
  {
    if ( v253 > 64 )
      GlobalFree(hMem);
    hMem = v255;
    v253 = 64;
    if ( v266 > 260 )
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
