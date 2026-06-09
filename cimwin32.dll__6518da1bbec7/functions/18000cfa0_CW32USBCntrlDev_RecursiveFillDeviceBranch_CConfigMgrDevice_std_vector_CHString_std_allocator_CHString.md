# CW32USBCntrlDev::RecursiveFillDeviceBranch(CConfigMgrDevice *,std::vector<CHString *,std::allocator<CHString *>> &)

- ea: `0x18000cfa0`
- end: `0x18000f49d`
- name: `?RecursiveFillDeviceBranch@CW32USBCntrlDev@@AEAAJPEAVCConfigMgrDevice@@AEAV?$vector@PEAVCHString@@V?$allocator@PEAVCHString@@@std@@@std@@@Z`
- size: `9469`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ac20`
- `0x18000cfa0`

## callees

- `0x1800035c0`
- `0x1800058c0`
- `0x18000cd50`
- `0x18000cfa0`
- `0x18000f584`
- `0x18000f638`
- `0x18000f6ec`
- `0x180015f48`
- `0x18008aed0`
- `0x18008bb9c`
- `0x1800fc8f6`
- `0x1800fc980`
- `0x1800fca40`
- `0x180110010`

## import_xrefs

- `msvcrt!malloc` at `0x18000d431`
- `msvcrt!malloc` at `0x18000d7aa`
- `msvcrt!malloc` at `0x18000d9fe`
- `msvcrt!malloc` at `0x18000dfb8`
- `msvcrt!malloc` at `0x18000e2c7`
- `msvcrt!malloc` at `0x18000e519`
- `msvcrt!malloc` at `0x18000ea3b`
- `msvcrt!malloc` at `0x18000d431`
- `msvcrt!malloc` at `0x18000d7aa`
- `msvcrt!malloc` at `0x18000d9fe`
- `msvcrt!malloc` at `0x18000dfb8`
- `msvcrt!malloc` at `0x18000e2c7`
- `msvcrt!malloc` at `0x18000e519`
- `msvcrt!malloc` at `0x18000ea3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d34f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d91b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ddf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e1e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e4f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e724`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e916`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e928`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ec4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ed60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ed88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eea3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ef93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f027`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f132`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f15e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f17d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f1b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f1c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f1df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f1f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f20b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d34f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d91b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ddf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e1e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e4f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e724`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e916`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e928`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ec4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ed60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ed88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eea3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ef93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f027`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f132`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f15e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f17d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f1b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f1c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f1df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f1f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f20b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000dd5d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e6ad`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e89d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000ece4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000ee2a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000dd5d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e6ad`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e89d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000ece4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000ee2a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000d08d`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000d47a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000d485`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000d490`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000d4c6`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000d570`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000da4a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000da55`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000da60`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000da90`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000dffd`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000e008`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000e013`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000e047`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000e565`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000e570`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000e57b`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000e5a7`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000ea7f`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000ea8a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000ea95`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000eac9`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000d08d`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000d47a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000d485`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000d490`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000d4c6`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000d570`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000da4a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000da55`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000da60`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000da90`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000dffd`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000e008`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000e013`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000e047`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000e565`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000e570`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000e57b`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000e5a7`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000ea7f`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000ea8a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000ea95`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000eac9`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18000dd4c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18000e69c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18000e88c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18000ecd3`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18000ee19`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18000dd4c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18000e69c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18000e88c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18000ecd3`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18000ee19`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x18000d78e`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x18000e2ab`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x18000d78e`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x18000e2ab`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x18000d7c9`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x18000e2e9`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x18000d7c9`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x18000e2e9`
- `framedynos!??4CHString@@QEAAAEBV0@PEBD@Z` at `0x18000d72a`
- `framedynos!??4CHString@@QEAAAEBV0@PEBD@Z` at `0x18000e248`
- `framedynos!??4CHString@@QEAAAEBV0@PEBD@Z` at `0x18000d72a`
- `framedynos!??4CHString@@QEAAAEBV0@PEBD@Z` at `0x18000e248`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18000e9bf`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18000ef77`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18000efff`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18000f09a`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18000f114`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18000e9bf`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18000ef77`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18000efff`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18000f09a`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18000f114`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18000d123`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18000d266`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18000d522`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18000db0b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18000e0ad`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18000e949`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18000eb1d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18000d123`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18000d266`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18000d522`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18000db0b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18000e0ad`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18000e949`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18000eb1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=51
__int64 __fastcall CW32USBCntrlDev::RecursiveFillDeviceBranch(__int64 a1, __int64 a2, _QWORD *a3)
{
  _DWORD *v4; // rsi
  volatile signed __int32 *v5; // r14
  _QWORD *v6; // r15
  _QWORD *i; // rbx
  __int64 v8; // rdi
  void *v9; // rdx
  int v10; // ebx
  struct IErrorInfo *v11; // rdx
  GUID v12; // xmm6
  _QWORD *v13; // rdi
  _QWORD *jj; // rbx
  __int64 v15; // r15
  void *v16; // rdx
  struct CResource *v17; // rax
  struct CResource *v18; // r12
  _QWORD *v19; // rbx
  volatile signed __int32 *v20; // rcx
  __int64 v22; // r15
  void *v23; // rdx
  struct CResource *Resource; // rax
  struct CResource *v25; // r12
  unsigned int (__fastcall *v26)(int *, _QWORD, _QWORD); // rax
  _QWORD *v27; // rdi
  _QWORD *n; // rbx
  __int64 v29; // r15
  int v30; // ebx
  __int64 v31; // rdi
  _QWORD *ii; // rax
  bool v33; // zf
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rcx
  CResource *v37; // rax
  CResource *v38; // r13
  unsigned int (__fastcall *v39)(int *, _QWORD, _QWORD); // rax
  _DWORD *v40; // rax
  _DWORD *v41; // r15
  int v42; // ebx
  int v43; // edi
  _QWORD *v44; // r15
  _QWORD *i5; // rbx
  volatile signed __int32 *v46; // rbx
  int v47; // r12d
  _QWORD *v48; // r15
  _QWORD *i8; // rbx
  int v50; // r12d
  CResource *v51; // rdx
  _QWORD *v52; // r15
  GUID v53; // xmm6
  volatile signed __int32 *v54; // r13
  _QWORD *i10; // rbx
  __int64 v56; // rdi
  void *v57; // rdx
  _QWORD *i17; // rbx
  __int64 v59; // rdi
  __int64 v60; // rdi
  __int64 v61; // rdi
  void *v62; // rdx
  struct CResource *v63; // rax
  struct CResource *v64; // r12
  int v65; // r13d
  unsigned int (__fastcall *v66)(_QWORD, _BYTE *, __int64, _QWORD); // rax
  _QWORD *v67; // r15
  _QWORD *i11; // rbx
  __int64 v69; // rdi
  CHString *v70; // rax
  _QWORD *v71; // rdi
  unsigned __int64 v72; // rcx
  bool v73; // al
  __int64 v74; // rdx
  __int64 v75; // rcx
  unsigned __int64 v76; // rdx
  unsigned __int64 v77; // rax
  unsigned __int64 v78; // rdx
  int v79; // ebx
  __int64 v80; // r15
  _QWORD *i12; // rax
  __int64 v82; // rax
  int v83; // eax
  volatile signed __int32 *v84; // rcx
  CResource *v85; // rax
  CResource *v86; // r13
  unsigned int (__fastcall *v87)(int *, _QWORD, _QWORD); // rax
  volatile signed __int32 *v88; // rbx
  _DWORD *v89; // rax
  _DWORD *v90; // r15
  int v91; // ebx
  int v92; // edi
  _QWORD *v93; // r15
  _QWORD *i18; // rbx
  __int64 v95; // rdi
  void *v96; // rdx
  volatile signed __int32 *v97; // rbx
  _QWORD *i21; // rbx
  __int64 v99; // rdi
  int v100; // ebx
  __int64 v101; // r15
  _QWORD *i22; // rax
  __int64 v103; // rax
  int v104; // eax
  _DWORD *v105; // rdi
  _QWORD *v106; // r12
  _QWORD *i13; // rbx
  __int64 v108; // r15
  char v109; // r15
  struct CResource *v110; // rax
  struct CResource *v111; // r12
  int v112; // r13d
  _QWORD *v113; // r15
  _QWORD *i19; // rbx
  __int64 v115; // rdi
  const OLECHAR *v116; // rax
  int v117; // ebx
  __int64 v118; // r15
  _QWORD *i20; // rax
  __int64 v120; // rax
  int v121; // eax
  __int64 v122; // rcx
  int v123; // ebx
  __int64 v124; // r15
  _QWORD *i9; // rax
  __int64 v126; // rax
  int v127; // eax
  __int64 v128; // rcx
  CResource *v129; // rax
  CResource *v130; // rbx
  unsigned int (__fastcall *v131)(int *, _QWORD, _QWORD); // rax
  _DWORD *v132; // rax
  int v133; // ebx
  int v134; // r15d
  _QWORD *v135; // r12
  _QWORD *v136; // rbx
  int v137; // r13d
  _QWORD *v138; // r12
  _QWORD *i16; // rbx
  struct _RTL_CRITICAL_SECTION *v140; // r15
  int v141; // eax
  __int64 v142; // r15
  void *v143; // rdx
  int v144; // ebx
  __int64 v145; // r12
  __int64 **v146; // rax
  int v147; // r13d
  unsigned int (__fastcall *v148)(_QWORD, _BYTE *, __int64, _QWORD); // rax
  _QWORD *kk; // rbx
  __int64 v150; // r15
  CHString *v151; // rax
  _QWORD *v152; // r13
  unsigned __int64 v153; // r8
  __int64 v154; // r9
  __int64 v155; // r8
  unsigned __int64 v156; // r8
  unsigned __int64 v157; // r9
  unsigned __int64 v158; // rdx
  CHString *v159; // rax
  _DWORD *v160; // rdi
  _QWORD *v161; // r12
  _QWORD *nn; // rbx
  __int64 v163; // r15
  void *v164; // rdx
  char v165; // r15
  int v166; // ebx
  __int64 v167; // rdi
  _QWORD *mm; // rax
  __int64 v169; // rax
  int v170; // eax
  struct _RTL_CRITICAL_SECTION *v171; // rcx
  _DWORD *v172; // rax
  int v173; // ebx
  int v174; // edi
  _QWORD *v175; // r15
  _QWORD *j; // rbx
  __int64 v177; // rdi
  void *v178; // rdx
  struct CResource *v179; // rax
  CResource *v180; // r12
  int v181; // r13d
  _QWORD *v182; // r15
  _QWORD *k; // rbx
  __int64 v184; // rdi
  const OLECHAR *v185; // rax
  int v186; // ebx
  __int64 v187; // r15
  _QWORD *m; // rax
  __int64 v189; // rcx
  __int64 v190; // rcx
  struct CResource *v191; // rax
  CResource *v192; // r13
  _QWORD *v193; // r12
  _QWORD *i14; // rbx
  __int64 v195; // r15
  const OLECHAR *v196; // rax
  int v197; // ebx
  __int64 v198; // r12
  _QWORD *i15; // rax
  unsigned int (__fastcall *v200)(_QWORD, __int64, int *, _BYTE *, int *, _DWORD); // rax
  CResource *v201; // rax
  CResource *v202; // rbx
  CResource *v203; // rdx
  unsigned int (__fastcall *v204)(int *, _QWORD, _QWORD); // rax
  _DWORD *v205; // rax
  int v206; // ebx
  int v207; // r15d
  _QWORD *v208; // r12
  _QWORD *i1; // rbx
  int v210; // r13d
  _QWORD *v211; // r15
  _QWORD *i4; // rbx
  struct _RTL_CRITICAL_SECTION *v213; // r12
  int v214; // eax
  __int64 v215; // r15
  void *v216; // rdx
  int v217; // ebx
  __int64 v218; // r15
  __int64 **v219; // rax
  struct CResource *v220; // rax
  CResource *v221; // r12
  int v222; // r13d
  _QWORD *v223; // r15
  _QWORD *i6; // rbx
  __int64 v225; // rdi
  const OLECHAR *v226; // rax
  int v227; // ebx
  __int64 v228; // r15
  _QWORD *i7; // rax
  struct CResource *v230; // rax
  CResource *v231; // r13
  _QWORD *v232; // r12
  _QWORD *i2; // rbx
  __int64 v234; // r15
  const OLECHAR *v235; // rax
  int v236; // ebx
  __int64 v237; // r12
  _QWORD *i3; // rax
  __int64 v239; // rcx
  unsigned int (__fastcall *v240)(_QWORD, __int64, int *, _BYTE *, int *, _DWORD); // rax
  unsigned int (__fastcall *v241)(_QWORD, __int64, int *, _BYTE *, int *, _DWORD); // rax
  unsigned int (__fastcall *v242)(_QWORD, __int64, int *, _BYTE *, int *, _DWORD); // rax
  unsigned int (__fastcall *v243)(_QWORD, __int64, int *, _BYTE *, int *, _DWORD); // rax
  __int64 v244; // rbx
  __int64 v245; // rbx
  int v246; // [rsp+40h] [rbp-2BF8h]
  int v247; // [rsp+40h] [rbp-2BF8h]
  int v248; // [rsp+40h] [rbp-2BF8h]
  CHString *v249; // [rsp+48h] [rbp-2BF0h] BYREF
  int v250; // [rsp+50h] [rbp-2BE8h]
  volatile signed __int32 *v251; // [rsp+58h] [rbp-2BE0h]
  GUID Buf2; // [rsp+60h] [rbp-2BD8h] BYREF
  CResource *v253; // [rsp+70h] [rbp-2BC8h]
  GUID v254; // [rsp+80h] [rbp-2BB8h] BYREF
  int v255; // [rsp+90h] [rbp-2BA8h] BYREF
  int v256; // [rsp+94h] [rbp-2BA4h] BYREF
  int v257; // [rsp+98h] [rbp-2BA0h] BYREF
  int v258; // [rsp+9Ch] [rbp-2B9Ch] BYREF
  int v259; // [rsp+A0h] [rbp-2B98h] BYREF
  _QWORD *v260; // [rsp+A8h] [rbp-2B90h]
  int v261; // [rsp+B0h] [rbp-2B88h] BYREF
  int v262; // [rsp+B4h] [rbp-2B84h] BYREF
  int v263; // [rsp+B8h] [rbp-2B80h] BYREF
  int v264; // [rsp+BCh] [rbp-2B7Ch] BYREF
  int v265; // [rsp+C0h] [rbp-2B78h] BYREF
  char v266[8]; // [rsp+C8h] [rbp-2B70h] BYREF
  char v267[8]; // [rsp+D0h] [rbp-2B68h] BYREF
  int v268; // [rsp+D8h] [rbp-2B60h] BYREF
  int v269; // [rsp+DCh] [rbp-2B5Ch] BYREF
  int v270; // [rsp+E0h] [rbp-2B58h] BYREF
  int v271; // [rsp+E4h] [rbp-2B54h] BYREF
  int v272; // [rsp+E8h] [rbp-2B50h] BYREF
  int v273; // [rsp+ECh] [rbp-2B4Ch] BYREF
  int v274; // [rsp+F0h] [rbp-2B48h] BYREF
  int pExceptionObject; // [rsp+F4h] [rbp-2B44h] BYREF
  int v276; // [rsp+F8h] [rbp-2B40h] BYREF
  int v277; // [rsp+FCh] [rbp-2B3Ch] BYREF
  int v278; // [rsp+100h] [rbp-2B38h] BYREF
  char v279[8]; // [rsp+108h] [rbp-2B30h] BYREF
  char v280[8]; // [rsp+110h] [rbp-2B28h] BYREF
  int v281; // [rsp+118h] [rbp-2B20h] BYREF
  char v282[8]; // [rsp+120h] [rbp-2B18h] BYREF
  char v283[8]; // [rsp+128h] [rbp-2B10h] BYREF
  char v284[8]; // [rsp+130h] [rbp-2B08h] BYREF
  int v285; // [rsp+138h] [rbp-2B00h] BYREF
  int v286; // [rsp+13Ch] [rbp-2AFCh] BYREF
  _DWORD *v287; // [rsp+140h] [rbp-2AF8h]
  volatile signed __int32 *v288; // [rsp+148h] [rbp-2AF0h]
  volatile signed __int32 *v289; // [rsp+150h] [rbp-2AE8h]
  __int64 v290; // [rsp+158h] [rbp-2AE0h]
  GUID v291; // [rsp+160h] [rbp-2AD8h] BYREF
  _DWORD *v292; // [rsp+170h] [rbp-2AC8h]
  _DWORD *v293; // [rsp+178h] [rbp-2AC0h]
  _DWORD *v294; // [rsp+180h] [rbp-2AB8h]
  __int64 v295; // [rsp+188h] [rbp-2AB0h]
  int v296; // [rsp+190h] [rbp-2AA8h]
  __int64 v297; // [rsp+198h] [rbp-2AA0h]
  int v298; // [rsp+1A0h] [rbp-2A98h]
  __int64 v299; // [rsp+1A8h] [rbp-2A90h]
  int v300; // [rsp+1B0h] [rbp-2A88h]
  __int64 v301; // [rsp+1B8h] [rbp-2A80h]
  int v302; // [rsp+1C0h] [rbp-2A78h]
  __int64 v303; // [rsp+1C8h] [rbp-2A70h]
  int v304; // [rsp+1D0h] [rbp-2A68h]
  struct _RTL_CRITICAL_SECTION *v305; // [rsp+1D8h] [rbp-2A60h]
  int v306; // [rsp+1E0h] [rbp-2A58h]
  __int64 v307; // [rsp+1E8h] [rbp-2A50h]
  int v308; // [rsp+1F0h] [rbp-2A48h]
  __int64 v309; // [rsp+1F8h] [rbp-2A40h]
  int v310; // [rsp+200h] [rbp-2A38h]
  __int64 v311; // [rsp+208h] [rbp-2A30h]
  int v312; // [rsp+210h] [rbp-2A28h]
  __int64 v313; // [rsp+218h] [rbp-2A20h]
  int v314; // [rsp+220h] [rbp-2A18h]
  struct _RTL_CRITICAL_SECTION *v315; // [rsp+228h] [rbp-2A10h]
  int v316; // [rsp+230h] [rbp-2A08h]
  __int64 v317; // [rsp+238h] [rbp-2A00h]
  int v318; // [rsp+240h] [rbp-29F8h]
  _DWORD *v319; // [rsp+248h] [rbp-29F0h]
  _DWORD *v320; // [rsp+250h] [rbp-29E8h]
  _DWORD *v321; // [rsp+258h] [rbp-29E0h]
  _DWORD *v322; // [rsp+260h] [rbp-29D8h]
  _DWORD *v323; // [rsp+268h] [rbp-29D0h]
  GUID v324; // [rsp+270h] [rbp-29C8h] BYREF
  GUID v325; // [rsp+280h] [rbp-29B8h] BYREF
  GUID v326; // [rsp+290h] [rbp-29A8h] BYREF
  GUID v327; // [rsp+2A0h] [rbp-2998h] BYREF
  GUID pclsid; // [rsp+2B0h] [rbp-2988h] BYREF
  _BYTE v329[208]; // [rsp+2C0h] [rbp-2978h] BYREF
  _BYTE v330[2064]; // [rsp+390h] [rbp-28A8h] BYREF
  _BYTE v331[2064]; // [rsp+BA0h] [rbp-2098h] BYREF
  _BYTE v332[2064]; // [rsp+13B0h] [rbp-1888h] BYREF
  _BYTE v333[2064]; // [rsp+1BC0h] [rbp-1078h] BYREF
  _BYTE v334[2064]; // [rsp+23D0h] [rbp-868h] BYREF

  v260 = a3;
  v290 = a1;
  v4 = 0;
  v287 = 0;
  v293 = 0;
  v251 = 0;
  v289 = 0;
  v5 = 0;
  v288 = 0;
  v249 = 0;
  if ( !a2 )
  {
    v10 = -2147217407;
    goto LABEL_20;
  }
  v246 = 0;
  Buf2 = guidCFGMGRAPI;
  v6 = (_QWORD *)CResourceManager::sm_TheResourceManager;
  for ( i = (_QWORD *)*CResourceManager::sm_TheResourceManager; ; i = (_QWORD *)*i )
  {
    if ( i == v6 )
    {
      v255 = 0;
      goto LABEL_7;
    }
    v8 = i[2];
    if ( !memcmp_0((const void *)(v8 + 24), &Buf2, 0x10u) )
      break;
  }
  Resource = CResourceList::GetResource((CResourceList *)v8, v9);
  v25 = Resource;
  *(_QWORD *)&v254.Data1 = Resource;
  v255 = 0;
  if ( Resource )
  {
    if ( (*(unsigned int (__fastcall **)(struct CResource *))(*(_QWORD *)Resource + 56LL))(Resource) )
    {
      v26 = (unsigned int (__fastcall *)(int *, _QWORD, _QWORD))*((_QWORD *)v25 + 11);
      if ( v26 && !v26(&v255, *(unsigned int *)(a2 + 68), 0) )
      {
        v172 = malloc(0x58u);
        v4 = v172;
        v287 = v172;
        if ( !v172 )
        {
          v276 = 0;
          throw (CHeap_Exception *)&v276;
        }
        v319 = v172;
        v173 = *(_DWORD *)(a2 + 40);
        v174 = v255;
        *(_QWORD *)v172 = &CRefPtrLite::`vftable';
        v172[2] = 1;
        *(_QWORD *)v172 = &CConfigMgrDevice::`vftable';
        CHString::CHString((CHString *)(v172 + 4));
        CHString::CHString((CHString *)(v4 + 6));
        CHString::CHString((CHString *)(v4 + 8));
        v4[10] = v173;
        *((_QWORD *)v4 + 6) = 0;
        v4[14] = 0;
        v4[17] = v174;
        v324 = GUID_NULL;
        CHString::CHString((CHString *)v279);
        v261 = 0;
        v277 = 2050;
        Buf2 = guidCFGMGRAPI;
        v175 = (_QWORD *)CResourceManager::sm_TheResourceManager;
        for ( j = (_QWORD *)*CResourceManager::sm_TheResourceManager; j != v175; j = (_QWORD *)*j )
        {
          v177 = j[2];
          if ( !memcmp_0((const void *)(v177 + 24), &Buf2, 0x10u) )
          {
            v179 = CResourceList::GetResource((CResourceList *)v177, v178);
            v180 = v179;
            if ( v179 )
            {
              v181 = 0;
              if ( (*(unsigned int (__fastcall **)(struct CResource *))(*(_QWORD *)v179 + 56LL))(v179) )
              {
                v240 = (unsigned int (__fastcall *)(_QWORD, __int64, int *, _BYTE *, int *, _DWORD))*((_QWORD *)v180 + 13);
                if ( v240 )
                {
                  if ( !v240((unsigned int)v4[17], 9, &v261, v330, &v277, 0) && v261 == 1 )
                  {
                    CHString::operator=(v279, v330);
                    v181 = 1;
                  }
                }
              }
              Buf2 = guidCFGMGRAPI;
              v182 = (_QWORD *)CResourceManager::sm_TheResourceManager;
              for ( k = (_QWORD *)*CResourceManager::sm_TheResourceManager; k != v182; k = (_QWORD *)*k )
              {
                v184 = k[2];
                if ( !memcmp_0((const void *)(v184 + 24), &Buf2, 0x10u) )
                {
                  if ( !*(_DWORD *)(v184 + 80) )
                  {
                    v295 = v184;
                    v186 = 0;
                    v296 = 0;
                    if ( v184 )
                    {
                      v187 = v184 + 40;
                      CStaticCritSec::Enter((CStaticCritSec *)(v184 + 40));
                      v186 = 1;
                      v296 = 1;
                    }
                    else
                    {
                      v187 = 40;
                    }
                    if ( *(_DWORD *)(v184 + 80) )
                    {
                      if ( v186 )
                        LeaveCriticalSection((LPCRITICAL_SECTION)v187);
                    }
                    else
                    {
                      for ( m = **(_QWORD ***)v184; m != *(_QWORD **)v184; m = (_QWORD *)*m )
                      {
                        if ( (CResource *)m[2] == v180 )
                        {
                          CResource::Release(v180);
                          break;
                        }
                      }
                      if ( v186 )
                        LeaveCriticalSection((LPCRITICAL_SECTION)(v184 + 40));
                    }
                  }
                  break;
                }
              }
              if ( v181 )
              {
                v185 = (const OLECHAR *)CHString::operator unsigned short const *(v279);
                CLSIDFromString(v185, &v324);
              }
            }
            break;
          }
        }
        *(GUID *)(v4 + 18) = v324;
        CHString::~CHString((CHString *)v279);
        v293 = v4;
        v246 = 1;
        v25 = *(struct CResource **)&v254.Data1;
      }
      else
      {
        v246 = 0;
      }
    }
    Buf2 = guidCFGMGRAPI;
    v27 = (_QWORD *)CResourceManager::sm_TheResourceManager;
    for ( n = (_QWORD *)*CResourceManager::sm_TheResourceManager; n != v27; n = (_QWORD *)*n )
    {
      v29 = n[2];
      if ( !memcmp_0((const void *)(v29 + 24), &Buf2, 0x10u) )
      {
        if ( !*(_DWORD *)(v29 + 80) )
        {
          v297 = v29;
          v30 = 0;
          v298 = 0;
          if ( v29 )
          {
            v31 = v29 + 40;
            CStaticCritSec::Enter((CStaticCritSec *)(v29 + 40));
            v30 = 1;
            v298 = 1;
          }
          else
          {
            v31 = 40;
          }
          if ( *(_DWORD *)(v29 + 80) )
          {
            if ( v30 )
              LeaveCriticalSection((LPCRITICAL_SECTION)v31);
          }
          else
          {
            for ( ii = **(_QWORD ***)v29; ii != *(_QWORD **)v29; ii = (_QWORD *)*ii )
            {
              if ( (struct CResource *)ii[2] == v25 )
              {
                v33 = (*((_DWORD *)v25 + 6))-- == 1;
                v34 = *(_QWORD *)v25;
                if ( v33 )
                  v35 = (*(__int64 (__fastcall **)(struct CResource *))(v34 + 24))(v25);
                else
                  v35 = (*(__int64 (__fastcall **)(struct CResource *))(v34 + 8))(v25);
                if ( v35 && !*((_DWORD *)v25 + 6) )
                {
                  CResourceList::RemoveFromList(*((CResourceList **)v25 + 2), v25);
                  v36 = *((_QWORD *)v25 + 1);
                  if ( v36 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 24LL))(v36);
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v25 + 1) + 16LL))(*((_QWORD *)v25 + 1));
                    *((_QWORD *)v25 + 1) = 0;
                  }
                  (*(void (__fastcall **)(struct CResource *, __int64))(*(_QWORD *)v25 + 32LL))(v25, 1);
                }
                break;
              }
            }
            if ( v30 )
              LeaveCriticalSection((LPCRITICAL_SECTION)(v29 + 40));
          }
        }
        break;
      }
    }
  }
LABEL_7:
  v10 = 0;
  v250 = 0;
  if ( !v246 )
    goto LABEL_20;
  CHString::CHString((CHString *)v267);
  if ( !v4 )
    _com_raise_error(-2147467261, v11);
  v12 = guidCFGMGRAPI;
  Buf2 = guidCFGMGRAPI;
  v13 = (_QWORD *)CResourceManager::sm_TheResourceManager;
  for ( jj = (_QWORD *)*CResourceManager::sm_TheResourceManager; ; jj = (_QWORD *)*jj )
  {
    if ( jj == v13 )
      goto LABEL_15;
    v15 = jj[2];
    if ( !memcmp_0((const void *)(v15 + 24), &Buf2, 0x10u) )
      break;
  }
  v17 = CResourceList::GetResource((CResourceList *)v15, v16);
  v18 = v17;
  if ( !v17 )
    goto LABEL_14;
  v147 = 0;
  if ( (*(unsigned int (__fastcall **)(struct CResource *))(*(_QWORD *)v17 + 56LL))(v17) )
  {
    v148 = (unsigned int (__fastcall *)(_QWORD, _BYTE *, __int64, _QWORD))*((_QWORD *)v18 + 23);
    if ( v148 )
    {
      if ( !v148((unsigned int)v4[17], v329, 201, 0) )
      {
        CHString::operator=(v267, v329);
        v147 = 1;
      }
    }
  }
  v12 = guidCFGMGRAPI;
  Buf2 = guidCFGMGRAPI;
  v13 = (_QWORD *)CResourceManager::sm_TheResourceManager;
  for ( kk = (_QWORD *)*CResourceManager::sm_TheResourceManager; kk != v13; kk = (_QWORD *)*kk )
  {
    v150 = kk[2];
    if ( !memcmp_0((const void *)(v150 + 24), &Buf2, 0x10u) )
    {
      if ( *(_DWORD *)(v150 + 80) )
        break;
      v299 = v150;
      v166 = 0;
      v300 = 0;
      if ( v150 )
      {
        v167 = v150 + 40;
        CStaticCritSec::Enter((CStaticCritSec *)(v150 + 40));
        v166 = 1;
        v300 = 1;
      }
      else
      {
        v167 = 40;
      }
      if ( *(_DWORD *)(v150 + 80) )
      {
        if ( v166 )
        {
          v171 = (struct _RTL_CRITICAL_SECTION *)v167;
LABEL_296:
          LeaveCriticalSection(v171);
        }
      }
      else
      {
        for ( mm = **(_QWORD ***)v150; mm != *(_QWORD **)v150; mm = (_QWORD *)*mm )
        {
          if ( (struct CResource *)mm[2] == v18 )
          {
            v33 = (*((_DWORD *)v18 + 6))-- == 1;
            v169 = *(_QWORD *)v18;
            if ( v33 )
              v170 = (*(__int64 (__fastcall **)(struct CResource *))(v169 + 24))(v18);
            else
              v170 = (*(__int64 (__fastcall **)(struct CResource *))(v169 + 8))(v18);
            if ( v170 && !*((_DWORD *)v18 + 6) )
            {
              CResourceList::RemoveFromList(*((CResourceList **)v18 + 2), v18);
              v189 = *((_QWORD *)v18 + 1);
              if ( v189 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v189 + 24LL))(v189);
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v18 + 1) + 16LL))(*((_QWORD *)v18 + 1));
                *((_QWORD *)v18 + 1) = 0;
              }
              (*(void (__fastcall **)(struct CResource *, __int64))(*(_QWORD *)v18 + 32LL))(v18, 1);
            }
            break;
          }
        }
        if ( v166 )
        {
          v171 = (struct _RTL_CRITICAL_SECTION *)(v150 + 40);
          goto LABEL_296;
        }
      }
      v13 = (_QWORD *)CResourceManager::sm_TheResourceManager;
      v12 = guidCFGMGRAPI;
      break;
    }
  }
  if ( !v147 )
    goto LABEL_15;
  if ( (int)CHString::GetLength((CHString *)v267) <= 0 )
    goto LABEL_14;
  v249 = 0;
  v151 = (CHString *)malloc(8u);
  if ( !v151 )
  {
    v278 = 0;
    throw (CHeap_Exception *)&v278;
  }
  *(_QWORD *)&v254.Data1 = v151;
  v249 = CHString::CHString(v151, (const struct CHString *)v267);
  if ( !v249 )
  {
    pExceptionObject = 0;
    throw (CHeap_Exception *)&pExceptionObject;
  }
  try
  {
    v152 = v260;
    v153 = v260[1];
    if ( (unsigned __int64)&v249 < v153 && *v260 <= (unsigned __int64)&v249 )
    {
      v244 = ((__int64)&v249 - *v260) >> 3;
      if ( v153 == v260[2] )
        std::vector<CHString *>::_Reserve(v260);
      v159 = *(CHString **)(*v152 + 8 * v244);
    }
    else
    {
      v154 = v260[2];
      if ( v153 == v154 && !((__int64)(v154 - v153) >> 3) )
      {
        v155 = (__int64)(v153 - *v260) >> 3;
        if ( v155 == 0x1FFFFFFFFFFFFFFFLL )
          std::_Xlength_error("vector<T> too long");
        v156 = v155 + 1;
        v157 = (v154 - *v260) >> 3;
        v158 = 0;
        if ( 0x1FFFFFFFFFFFFFFFLL - (v157 >> 1) >= v157 )
          v158 = v157 + (v157 >> 1);
        if ( v158 < v156 )
          v158 = v156;
        std::vector<CHString *>::_Reallocate(v260, v158);
      }
      v159 = v249;
    }
    *(_QWORD *)v152[1] = v159;
    v152[1] += 8LL;
  }
  catch ( ... )
  {
    if ( v249 )
      CHString::`scalar deleting destructor'(v249, 1u);
    v249 = 0;
    throw;
  }
  if ( memcmp_0(&GUID_DEVCLASS_USB, v4 + 18, 0x10u) )
    goto LABEL_282;
  v160 = 0;
  v294 = 0;
  Buf2 = guidCFGMGRAPI;
  v161 = (_QWORD *)CResourceManager::sm_TheResourceManager;
  for ( nn = (_QWORD *)*CResourceManager::sm_TheResourceManager; ; nn = (_QWORD *)*nn )
  {
    if ( nn == v161 )
    {
      v256 = 0;
LABEL_277:
      v165 = 0;
      goto LABEL_278;
    }
    v163 = nn[2];
    if ( !memcmp_0((const void *)(v163 + 24), &Buf2, 0x10u) )
      break;
  }
  v201 = CResourceList::GetResource((CResourceList *)v163, v164);
  v202 = v201;
  v253 = v201;
  v256 = 0;
  if ( !v201 )
    goto LABEL_277;
  if ( (*(unsigned int (__fastcall **)(CResource *))(*(_QWORD *)v201 + 56LL))(v201)
    && (v204 = (unsigned int (__fastcall *)(int *, _QWORD, _QWORD))*((_QWORD *)v202 + 25)) != 0
    && !v204(&v256, (unsigned int)v4[17], 0) )
  {
    v205 = malloc(0x58u);
    v160 = v205;
    if ( !v205 )
    {
      v281 = 0;
      throw (CHeap_Exception *)&v281;
    }
    v320 = v205;
    v206 = v4[10];
    v207 = v256;
    *(_QWORD *)v205 = &CRefPtrLite::`vftable';
    v205[2] = 1;
    *(_QWORD *)v205 = &CConfigMgrDevice::`vftable';
    CHString::CHString((CHString *)(v205 + 4));
    CHString::CHString((CHString *)(v160 + 6));
    CHString::CHString((CHString *)(v160 + 8));
    v160[10] = v206;
    *((_QWORD *)v160 + 6) = 0;
    v160[14] = 0;
    v160[17] = v207;
    v327 = GUID_NULL;
    CHString::CHString((CHString *)v280);
    v262 = 0;
    v285 = 2050;
    Buf2 = guidCFGMGRAPI;
    v208 = (_QWORD *)CResourceManager::sm_TheResourceManager;
    for ( i1 = (_QWORD *)*CResourceManager::sm_TheResourceManager; i1 != v208; i1 = (_QWORD *)*i1 )
    {
      v215 = i1[2];
      if ( !memcmp_0((const void *)(v215 + 24), &Buf2, 0x10u) )
      {
        v230 = CResourceList::GetResource((CResourceList *)v215, v216);
        v231 = v230;
        if ( v230 )
        {
          v248 = 0;
          if ( (*(unsigned int (__fastcall **)(struct CResource *))(*(_QWORD *)v230 + 56LL))(v230) )
          {
            v243 = (unsigned int (__fastcall *)(_QWORD, __int64, int *, _BYTE *, int *, _DWORD))*((_QWORD *)v231 + 13);
            if ( v243 && !v243((unsigned int)v160[17], 9, &v262, v331, &v285, 0) && v262 == 1 )
            {
              CHString::operator=(v280, v331);
              v248 = 1;
            }
            else
            {
              v248 = 0;
            }
          }
          Buf2 = guidCFGMGRAPI;
          v232 = (_QWORD *)CResourceManager::sm_TheResourceManager;
          for ( i2 = (_QWORD *)*CResourceManager::sm_TheResourceManager; i2 != v232; i2 = (_QWORD *)*i2 )
          {
            v234 = i2[2];
            if ( !memcmp_0((const void *)(v234 + 24), &Buf2, 0x10u) )
            {
              if ( !*(_DWORD *)(v234 + 80) )
              {
                v301 = v234;
                v236 = 0;
                v302 = 0;
                if ( v234 )
                {
                  v237 = v234 + 40;
                  CStaticCritSec::Enter((CStaticCritSec *)(v234 + 40));
                  v236 = 1;
                  v302 = 1;
                }
                else
                {
                  v237 = 40;
                }
                if ( *(_DWORD *)(v234 + 80) )
                {
                  if ( v236 )
                    LeaveCriticalSection((LPCRITICAL_SECTION)v237);
                }
                else
                {
                  for ( i3 = **(_QWORD ***)v234; i3 != *(_QWORD **)v234; i3 = (_QWORD *)*i3 )
                  {
                    if ( (CResource *)i3[2] == v231 )
                    {
                      CResource::Release(v231);
                      break;
                    }
                  }
                  if ( v236 )
                    LeaveCriticalSection((LPCRITICAL_SECTION)(v234 + 40));
                }
              }
              break;
            }
          }
          if ( v248 )
          {
            v235 = (const OLECHAR *)CHString::operator unsigned short const *(v280);
            CLSIDFromString(v235, &v327);
          }
        }
        break;
      }
    }
    *(GUID *)(v160 + 18) = v327;
    CHString::~CHString((CHString *)v280);
    v294 = v160;
    v210 = 1;
  }
  else
  {
    v253 = v202;
    v210 = 0;
  }
  Buf2 = guidCFGMGRAPI;
  v211 = (_QWORD *)CResourceManager::sm_TheResourceManager;
  for ( i4 = (_QWORD *)*CResourceManager::sm_TheResourceManager; i4 != v211; i4 = (_QWORD *)*i4 )
  {
    v213 = (struct _RTL_CRITICAL_SECTION *)i4[2];
    if ( !memcmp_0(&v213->LockSemaphore, &Buf2, 0x10u) )
    {
      if ( !LODWORD(v213[2].DebugInfo) )
      {
        v305 = v213;
        v217 = 0;
        v306 = 0;
        if ( v213 )
        {
          v218 = (__int64)&v213[1];
          CStaticCritSec::Enter((CStaticCritSec *)&v213[1]);
          v217 = 1;
          v306 = 1;
        }
        else
        {
          v218 = 40;
        }
        if ( LODWORD(v213[2].DebugInfo) )
        {
          if ( v217 )
            LeaveCriticalSection((LPCRITICAL_SECTION)v218);
        }
        else
        {
          v219 = *(__int64 ***)&v213->DebugInfo->Type;
          v203 = v253;
          while ( v219 != (__int64 **)v213->DebugInfo )
          {
            if ( v219[2] == (__int64 *)v253 )
            {
              CResource::Release(v253);
              break;
            }
            v219 = (__int64 **)*v219;
          }
          if ( v217 )
            LeaveCriticalSection(v213 + 1);
        }
      }
      break;
    }
  }
  if ( !v210 )
  {
    v152 = v260;
    goto LABEL_277;
  }
  if ( !v160 )
    _com_raise_error(-2147467261, (struct IErrorInfo *)v203);
  v214 = memcmp_0(&GUID_DEVCLASS_USB, v160 + 18, 0x10u);
  v152 = v260;
  if ( !v214 )
    goto LABEL_277;
  v165 = 1;
LABEL_278:
  if ( v160 && !_InterlockedDecrement(v160 + 2) )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v160 + 8LL))(v160);
  if ( !v165 )
  {
LABEL_282:
    v10 = CW32USBCntrlDev::RecursiveFillDeviceBranch(v290, v4, v152);
    v250 = v10;
    if ( v10 < 0 )
      goto LABEL_19;
  }
LABEL_14:
  v13 = (_QWORD *)CResourceManager::sm_TheResourceManager;
  v12 = guidCFGMGRAPI;
LABEL_15:
  Buf2 = v12;
  v19 = (_QWORD *)*v13;
  while ( 2 )
  {
    if ( v19 == v13 )
    {
      v259 = 0;
      goto LABEL_18;
    }
    v22 = v19[2];
    if ( memcmp_0((const void *)(v22 + 24), &Buf2, 0x10u) )
    {
      v19 = (_QWORD *)*v19;
      continue;
    }
    break;
  }
  v37 = CResourceList::GetResource((CResourceList *)v22, v23);
  v38 = v37;
  v253 = v37;
  v259 = 0;
  if ( !v37 )
    goto LABEL_18;
  if ( (*(unsigned int (__fastcall **)(CResource *))(*(_QWORD *)v37 + 56LL))(v37)
    && (v39 = (unsigned int (__fastcall *)(int *, _QWORD, _QWORD))*((_QWORD *)v38 + 12)) != 0
    && !v39(&v259, (unsigned int)v4[17], 0) )
  {
    v40 = malloc(0x58u);
    v41 = v40;
    v251 = v40;
    if ( !v40 )
    {
      v274 = 0;
      throw (CHeap_Exception *)&v274;
    }
    v321 = v40;
    v42 = v4[10];
    v43 = v259;
    *(_QWORD *)v40 = &CRefPtrLite::`vftable';
    v40[2] = 1;
    *(_QWORD *)v40 = &CConfigMgrDevice::`vftable';
    CHString::CHString((CHString *)(v40 + 4));
    CHString::CHString((CHString *)(v41 + 6));
    CHString::CHString((CHString *)(v41 + 8));
    v41[10] = v42;
    *((_QWORD *)v41 + 6) = 0;
    v41[14] = 0;
    v41[17] = v43;
    v325 = GUID_NULL;
    CHString::CHString((CHString *)v282);
    v263 = 0;
    v286 = 2050;
    Buf2 = guidCFGMGRAPI;
    v44 = (_QWORD *)CResourceManager::sm_TheResourceManager;
    for ( i5 = (_QWORD *)*CResourceManager::sm_TheResourceManager; i5 != v44; i5 = (_QWORD *)*i5 )
    {
      v61 = i5[2];
      if ( !memcmp_0((const void *)(v61 + 24), &Buf2, 0x10u) )
      {
        v220 = CResourceList::GetResource((CResourceList *)v61, v62);
        v221 = v220;
        if ( v220 )
        {
          v222 = 0;
          if ( (*(unsigned int (__fastcall **)(struct CResource *))(*(_QWORD *)v220 + 56LL))(v220) )
          {
            v242 = (unsigned int (__fastcall *)(_QWORD, __int64, int *, _BYTE *, int *, _DWORD))*((_QWORD *)v221 + 13);
            if ( v242 )
            {
              if ( !v242(*((unsigned int *)v251 + 17), 9, &v263, v332, &v286, 0) && v263 == 1 )
              {
                CHString::operator=(v282, v332);
                v222 = 1;
              }
            }
          }
          Buf2 = guidCFGMGRAPI;
          v223 = (_QWORD *)CResourceManager::sm_TheResourceManager;
          for ( i6 = (_QWORD *)*CResourceManager::sm_TheResourceManager; i6 != v223; i6 = (_QWORD *)*i6 )
          {
            v225 = i6[2];
            if ( !memcmp_0((const void *)(v225 + 24), &Buf2, 0x10u) )
            {
              if ( !*(_DWORD *)(v225 + 80) )
              {
                v307 = v225;
                v227 = 0;
                v308 = 0;
                if ( v225 )
                {
                  v228 = v225 + 40;
                  CStaticCritSec::Enter((CStaticCritSec *)(v225 + 40));
                  v227 = 1;
                  v308 = 1;
                }
                else
                {
                  v228 = 40;
                }
                if ( *(_DWORD *)(v225 + 80) )
                {
                  if ( v227 )
                    LeaveCriticalSection((LPCRITICAL_SECTION)v228);
                }
                else
                {
                  for ( i7 = **(_QWORD ***)v225; i7 != *(_QWORD **)v225; i7 = (_QWORD *)*i7 )
                  {
                    if ( (CResource *)i7[2] == v221 )
                    {
                      CResource::Release(v221);
                      break;
                    }
                  }
                  if ( v227 )
                    LeaveCriticalSection((LPCRITICAL_SECTION)(v225 + 40));
                }
              }
              break;
            }
          }
          if ( v222 )
          {
            v226 = (const OLECHAR *)CHString::operator unsigned short const *(v282);
            CLSIDFromString(v226, &v325);
          }
          v38 = v253;
        }
        break;
      }
    }
    v46 = v251;
    *(GUID *)(v251 + 18) = v325;
    CHString::~CHString((CHString *)v282);
    v289 = v46;
    v47 = 1;
  }
  else
  {
    v47 = 0;
  }
  Buf2 = guidCFGMGRAPI;
  v48 = (_QWORD *)CResourceManager::sm_TheResourceManager;
  for ( i8 = (_QWORD *)*CResourceManager::sm_TheResourceManager; i8 != v48; i8 = (_QWORD *)*i8 )
  {
    v60 = i8[2];
    if ( !memcmp_0((const void *)(v60 + 24), &Buf2, 0x10u) )
    {
      if ( !*(_DWORD *)(v60 + 80) )
      {
        v309 = v60;
        v123 = 0;
        v310 = 0;
        if ( v60 )
        {
          v124 = v60 + 40;
          CStaticCritSec::Enter((CStaticCritSec *)(v60 + 40));
          v123 = 1;
          v310 = 1;
        }
        else
        {
          v124 = 40;
        }
        if ( *(_DWORD *)(v60 + 80) )
        {
          if ( v123 )
            LeaveCriticalSection((LPCRITICAL_SECTION)v124);
        }
        else
        {
          for ( i9 = **(_QWORD ***)v60; i9 != *(_QWORD **)v60; i9 = (_QWORD *)*i9 )
          {
            if ( (CResource *)i9[2] == v38 )
            {
              v33 = (*((_DWORD *)v38 + 6))-- == 1;
              v126 = *(_QWORD *)v38;
              if ( v33 )
                v127 = (*(__int64 (__fastcall **)(CResource *))(v126 + 24))(v38);
              else
                v127 = (*(__int64 (__fastcall **)(CResource *))(v126 + 8))(v38);
              if ( v127 && !*((_DWORD *)v38 + 6) )
              {
                CResourceList::RemoveFromList(*((CResourceList **)v38 + 2), v38);
                v239 = *((_QWORD *)v38 + 1);
                if ( v239 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v239 + 24LL))(v239);
                  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v38 + 1) + 16LL))(*((_QWORD *)v38 + 1));
                  *((_QWORD *)v38 + 1) = 0;
                }
                (*(void (__fastcall **)(CResource *, __int64))(*(_QWORD *)v38 + 32LL))(v38, 1);
              }
              break;
            }
          }
          if ( v123 )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v60 + 40));
        }
      }
      break;
    }
  }
  if ( !v47 )
  {
LABEL_18:
    v10 = v250;
    goto LABEL_19;
  }
  v50 = 1;
  CHString::CHString((CHString *)v266);
LABEL_72:
  v52 = (_QWORD *)CResourceManager::sm_TheResourceManager;
  v53 = guidCFGMGRAPI;
  while ( 1 )
  {
    v10 = v250;
    if ( v250 < 0 || !v50 )
      break;
    v54 = v251;
    if ( !v251 )
      _com_raise_error(-2147467261, (struct IErrorInfo *)v51);
    v254 = v53;
    for ( i10 = (_QWORD *)*v52; i10 != v52; i10 = (_QWORD *)*i10 )
    {
      v56 = i10[2];
      if ( !memcmp_0((const void *)(v56 + 24), &v254, 0x10u) )
      {
        v63 = CResourceList::GetResource((CResourceList *)v56, v57);
        v64 = v63;
        if ( v63 )
        {
          v65 = 0;
          if ( (*(unsigned int (__fastcall **)(struct CResource *))(*(_QWORD *)v63 + 56LL))(v63) )
          {
            v66 = (unsigned int (__fastcall *)(_QWORD, _BYTE *, __int64, _QWORD))*((_QWORD *)v64 + 23);
            if ( v66 )
            {
              if ( !v66(*((unsigned int *)v251 + 17), v329, 201, 0) )
              {
                CHString::operator=(v266, v329);
                v65 = 1;
              }
            }
          }
          v254 = guidCFGMGRAPI;
          v67 = (_QWORD *)CResourceManager::sm_TheResourceManager;
          for ( i11 = (_QWORD *)*CResourceManager::sm_TheResourceManager; i11 != v67; i11 = (_QWORD *)*i11 )
          {
            v69 = i11[2];
            if ( !memcmp_0((const void *)(v69 + 24), &v254, 0x10u) )
            {
              if ( !*(_DWORD *)(v69 + 80) )
              {
                v311 = v69;
                v79 = 0;
                v312 = 0;
                if ( v69 )
                {
                  v80 = v69 + 40;
                  CStaticCritSec::Enter((CStaticCritSec *)(v69 + 40));
                  v79 = 1;
                  v312 = 1;
                }
                else
                {
                  v80 = 40;
                }
                if ( *(_DWORD *)(v69 + 80) )
                {
                  if ( v79 )
                    LeaveCriticalSection((LPCRITICAL_SECTION)v80);
                }
                else
                {
                  for ( i12 = **(_QWORD ***)v69; i12 != *(_QWORD **)v69; i12 = (_QWORD *)*i12 )
                  {
                    if ( (struct CResource *)i12[2] == v64 )
                    {
                      v33 = (*((_DWORD *)v64 + 6))-- == 1;
                      v82 = *(_QWORD *)v64;
                      if ( v33 )
                        v83 = (*(__int64 (__fastcall **)(struct CResource *))(v82 + 24))(v64);
                      else
                        v83 = (*(__int64 (__fastcall **)(struct CResource *))(v82 + 8))(v64);
                      if ( v83 && !*((_DWORD *)v64 + 6) )
                      {
                        CResourceList::RemoveFromList(*((CResourceList **)v64 + 2), v64);
                        v128 = *((_QWORD *)v64 + 1);
                        if ( v128 )
                        {
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 24LL))(v128);
                          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v64 + 1) + 16LL))(*((_QWORD *)v64 + 1));
                          *((_QWORD *)v64 + 1) = 0;
                        }
                        (*(void (__fastcall **)(struct CResource *, __int64))(*(_QWORD *)v64 + 32LL))(v64, 1);
                      }
                      break;
                    }
                  }
                  if ( v79 )
                    LeaveCriticalSection((LPCRITICAL_SECTION)(v69 + 40));
                }
              }
              break;
            }
          }
          if ( v65 && (int)CHString::GetLength((CHString *)v266) > 0 )
          {
            v249 = 0;
            v70 = (CHString *)malloc(8u);
            if ( !v70 )
            {
              v268 = 0;
              throw (CHeap_Exception *)&v268;
            }
            *(_QWORD *)&Buf2.Data1 = v70;
            v249 = CHString::CHString(v70, (const struct CHString *)v266);
            if ( !v249 )
            {
              v269 = 0;
              throw (CHeap_Exception *)&v269;
            }
            try
            {
              v71 = v260;
              v72 = v260[1];
              v73 = (unsigned __int64)&v249 < v72 && *v260 <= (unsigned __int64)&v249;
              v74 = v260[2];
              if ( v73 )
              {
                v245 = ((__int64)&v249 - *v260) >> 3;
                if ( v72 == v74 )
                  std::vector<CHString *>::_Reserve(v260);
                *(_QWORD *)v71[1] = *(_QWORD *)(*v71 + 8 * v245);
                v71[1] += 8LL;
              }
              else
              {
                if ( v72 == v74 && !((__int64)(v74 - v72) >> 3) )
                {
                  v75 = (__int64)(v72 - *v260) >> 3;
                  if ( v75 == 0x1FFFFFFFFFFFFFFFLL )
                    std::_Xlength_error("vector<T> too long");
                  v76 = (v74 - *v260) >> 3;
                  if ( 0x1FFFFFFFFFFFFFFFLL - (v76 >> 1) >= v76 )
                    v77 = v76 + (v76 >> 1);
                  else
                    v77 = 0;
                  v78 = v75 + 1;
                  if ( v77 >= v75 + 1 )
                    v78 = v77;
                  std::vector<CHString *>::_Reallocate(v260, v78);
                }
                *(_QWORD *)v71[1] = v249;
                v71[1] += 8LL;
              }
            }
            catch ( ... )
            {
              if ( v249 )
                CHString::`scalar deleting destructor'(v249, 1u);
              v249 = 0;
              throw;
            }
          }
          v54 = v251;
        }
        break;
      }
    }
    if ( !v54 || memcmp_0(&GUID_DEVCLASS_USB, (const void *)(v54 + 18), 0x10u) )
      goto LABEL_82;
    v105 = 0;
    v292 = 0;
    v254 = guidCFGMGRAPI;
    v106 = (_QWORD *)CResourceManager::sm_TheResourceManager;
    for ( i13 = (_QWORD *)*CResourceManager::sm_TheResourceManager; ; i13 = (_QWORD *)*i13 )
    {
      if ( i13 == v106 )
      {
        v257 = 0;
LABEL_171:
        v109 = 0;
        goto LABEL_172;
      }
      v108 = i13[2];
      if ( !memcmp_0((const void *)(v108 + 24), &v254, 0x10u) )
        break;
    }
    v129 = CResourceList::GetResource((CResourceList *)v108, v51);
    v130 = v129;
    v253 = v129;
    v257 = 0;
    if ( !v129 )
      goto LABEL_171;
    if ( (*(unsigned int (__fastcall **)(CResource *))(*(_QWORD *)v129 + 56LL))(v129)
      && (v131 = (unsigned int (__fastcall *)(int *, _QWORD, _QWORD))*((_QWORD *)v130 + 25)) != 0
      && !v131(&v257, *((unsigned int *)v54 + 17), 0) )
    {
      v132 = malloc(0x58u);
      v105 = v132;
      if ( !v132 )
      {
        v270 = 0;
        throw (CHeap_Exception *)&v270;
      }
      v322 = v132;
      v133 = *((_DWORD *)v54 + 10);
      v134 = v257;
      *(_QWORD *)v132 = &CRefPtrLite::`vftable';
      v132[2] = 1;
      *(_QWORD *)v132 = &CConfigMgrDevice::`vftable';
      CHString::CHString((CHString *)(v132 + 4));
      CHString::CHString((CHString *)(v105 + 6));
      CHString::CHString((CHString *)(v105 + 8));
      v105[10] = v133;
      *((_QWORD *)v105 + 6) = 0;
      v105[14] = 0;
      v105[17] = v134;
      v326 = GUID_NULL;
      CHString::CHString((CHString *)v283);
      v264 = 0;
      v271 = 2050;
      v254 = guidCFGMGRAPI;
      v135 = (_QWORD *)CResourceManager::sm_TheResourceManager;
      v136 = (_QWORD *)*CResourceManager::sm_TheResourceManager;
      v4 = v287;
      v5 = v288;
      while ( v136 != v135 )
      {
        v142 = v136[2];
        if ( !memcmp_0((const void *)(v142 + 24), &v254, 0x10u) )
        {
          v191 = CResourceList::GetResource((CResourceList *)v142, v143);
          v192 = v191;
          if ( v191 )
          {
            v247 = 0;
            if ( (*(unsigned int (__fastcall **)(struct CResource *))(*(_QWORD *)v191 + 56LL))(v191) )
            {
              v241 = (unsigned int (__fastcall *)(_QWORD, __int64, int *, _BYTE *, int *, _DWORD))*((_QWORD *)v192 + 13);
              if ( v241 && !v241((unsigned int)v105[17], 9, &v264, v333, &v271, 0) && v264 == 1 )
              {
                CHString::operator=(v283, v333);
                v247 = 1;
              }
              else
              {
                v247 = 0;
              }
            }
            v254 = guidCFGMGRAPI;
            v193 = (_QWORD *)CResourceManager::sm_TheResourceManager;
            for ( i14 = (_QWORD *)*CResourceManager::sm_TheResourceManager; i14 != v193; i14 = (_QWORD *)*i14 )
            {
              v195 = i14[2];
              if ( !memcmp_0((const void *)(v195 + 24), &v254, 0x10u) )
              {
                if ( !*(_DWORD *)(v195 + 80) )
                {
                  v313 = v195;
                  v197 = 0;
                  v314 = 0;
                  if ( v195 )
                  {
                    v198 = v195 + 40;
                    CStaticCritSec::Enter((CStaticCritSec *)(v195 + 40));
                    v197 = 1;
                    v314 = 1;
                  }
                  else
                  {
                    v198 = 40;
                  }
                  if ( *(_DWORD *)(v195 + 80) )
                  {
                    if ( v197 )
                      LeaveCriticalSection((LPCRITICAL_SECTION)v198);
                  }
                  else
                  {
                    for ( i15 = **(_QWORD ***)v195; i15 != *(_QWORD **)v195; i15 = (_QWORD *)*i15 )
                    {
                      if ( (CResource *)i15[2] == v192 )
                      {
                        CResource::Release(v192);
                        break;
                      }
                    }
                    if ( v197 )
                      LeaveCriticalSection((LPCRITICAL_SECTION)(v195 + 40));
                  }
                }
                break;
              }
            }
            if ( v247 )
            {
              v196 = (const OLECHAR *)CHString::operator unsigned short const *(v283);
              CLSIDFromString(v196, &v326);
            }
          }
          break;
        }
        v136 = (_QWORD *)*v136;
      }
      *(GUID *)(v105 + 18) = v326;
      CHString::~CHString((CHString *)v283);
      v292 = v105;
      v137 = 1;
    }
    else
    {
      v253 = v130;
      v137 = 0;
    }
    v254 = guidCFGMGRAPI;
    v138 = (_QWORD *)CResourceManager::sm_TheResourceManager;
    for ( i16 = (_QWORD *)*CResourceManager::sm_TheResourceManager; i16 != v138; i16 = (_QWORD *)*i16 )
    {
      v140 = (struct _RTL_CRITICAL_SECTION *)i16[2];
      if ( !memcmp_0(&v140->LockSemaphore, &v254, 0x10u) )
      {
        if ( !LODWORD(v140[2].DebugInfo) )
        {
          v315 = v140;
          v144 = 0;
          v316 = 0;
          if ( v140 )
          {
            v145 = (__int64)&v140[1];
            CStaticCritSec::Enter((CStaticCritSec *)&v140[1]);
            v144 = 1;
            v316 = 1;
          }
          else
          {
            v145 = 40;
          }
          if ( LODWORD(v140[2].DebugInfo) )
          {
            if ( v144 )
              LeaveCriticalSection((LPCRITICAL_SECTION)v145);
          }
          else
          {
            v146 = *(__int64 ***)&v140->DebugInfo->Type;
            v51 = v253;
            while ( v146 != (__int64 **)v140->DebugInfo )
            {
              if ( v146[2] == (__int64 *)v253 )
              {
                CResource::Release(v253);
                break;
              }
              v146 = (__int64 **)*v146;
            }
            if ( v144 )
              LeaveCriticalSection(v140 + 1);
          }
        }
        break;
      }
    }
    if ( !v137 )
    {
      v54 = v251;
      goto LABEL_171;
    }
    if ( !v105 )
      _com_raise_error(-2147467261, (struct IErrorInfo *)v51);
    v141 = memcmp_0(&GUID_DEVCLASS_USB, v105 + 18, 0x10u);
    v54 = v251;
    if ( !v141 )
      goto LABEL_171;
    v109 = 1;
LABEL_172:
    if ( v105 && _InterlockedExchangeAdd(v105 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v105 + 8LL))(v105);
    if ( !v109 )
LABEL_82:
      v250 = CW32USBCntrlDev::RecursiveFillDeviceBranch(v290, v54, v260);
    v50 = 0;
    v53 = guidCFGMGRAPI;
    v254 = guidCFGMGRAPI;
    v52 = (_QWORD *)CResourceManager::sm_TheResourceManager;
    for ( i17 = (_QWORD *)*CResourceManager::sm_TheResourceManager; ; i17 = (_QWORD *)*i17 )
    {
      if ( i17 == v52 )
      {
        v258 = 0;
        goto LABEL_131;
      }
      v59 = i17[2];
      if ( !memcmp_0((const void *)(v59 + 24), &v254, 0x10u) )
        break;
    }
    v85 = CResourceList::GetResource((CResourceList *)v59, v51);
    v86 = v85;
    v253 = v85;
    v258 = 0;
    if ( v85 )
    {
      if ( (*(unsigned int (__fastcall **)(CResource *))(*(_QWORD *)v85 + 56LL))(v85) )
      {
        v87 = (unsigned int (__fastcall *)(int *, _QWORD, _QWORD))*((_QWORD *)v86 + 12);
        if ( v87 )
        {
          v88 = v251;
          if ( !v87(&v258, *((unsigned int *)v251 + 17), 0) )
          {
            v89 = malloc(0x58u);
            v90 = v89;
            *(_QWORD *)&v254.Data1 = v89;
            if ( !v89 )
            {
              v272 = 0;
              throw (CHeap_Exception *)&v272;
            }
            v323 = v89;
            v91 = *((_DWORD *)v88 + 10);
            v92 = v258;
            *(_QWORD *)v89 = &CRefPtrLite::`vftable';
            v89[2] = 1;
            *(_QWORD *)v89 = &CConfigMgrDevice::`vftable';
            CHString::CHString((CHString *)(v89 + 4));
            CHString::CHString((CHString *)(v90 + 6));
            CHString::CHString((CHString *)(v90 + 8));
            v90[10] = v91;
            *((_QWORD *)v90 + 6) = 0;
            v90[14] = 0;
            v90[17] = v92;
            pclsid = GUID_NULL;
            CHString::CHString((CHString *)v284);
            v265 = 0;
            v273 = 2050;
            v291 = guidCFGMGRAPI;
            v93 = (_QWORD *)CResourceManager::sm_TheResourceManager;
            for ( i18 = (_QWORD *)*CResourceManager::sm_TheResourceManager; i18 != v93; i18 = (_QWORD *)*i18 )
            {
              v95 = i18[2];
              if ( !memcmp_0((const void *)(v95 + 24), &v291, 0x10u) )
              {
                v110 = CResourceList::GetResource((CResourceList *)v95, v96);
                v111 = v110;
                if ( v110 )
                {
                  v112 = 0;
                  if ( (*(unsigned int (__fastcall **)(struct CResource *))(*(_QWORD *)v110 + 56LL))(v110) )
                  {
                    v200 = (unsigned int (__fastcall *)(_QWORD, __int64, int *, _BYTE *, int *, _DWORD))*((_QWORD *)v111 + 13);
                    if ( v200 )
                    {
                      if ( !v200(*(unsigned int *)(*(_QWORD *)&v254.Data1 + 68LL), 9, &v265, v334, &v273, 0)
                        && v265 == 1 )
                      {
                        CHString::operator=(v284, v334);
                        v112 = 1;
                      }
                    }
                  }
                  v291 = guidCFGMGRAPI;
                  v113 = (_QWORD *)CResourceManager::sm_TheResourceManager;
                  for ( i19 = (_QWORD *)*CResourceManager::sm_TheResourceManager; i19 != v113; i19 = (_QWORD *)*i19 )
                  {
                    v115 = i19[2];
                    if ( !memcmp_0((const void *)(v115 + 24), &v291, 0x10u) )
                    {
                      if ( !*(_DWORD *)(v115 + 80) )
                      {
                        v303 = v115;
                        v117 = 0;
                        v304 = 0;
                        if ( v115 )
                        {
                          v118 = v115 + 40;
                          CStaticCritSec::Enter((CStaticCritSec *)(v115 + 40));
                          v117 = 1;
                          v304 = 1;
                        }
                        else
                        {
                          v118 = 40;
                        }
                        if ( *(_DWORD *)(v115 + 80) )
                        {
                          if ( v117 )
                            LeaveCriticalSection((LPCRITICAL_SECTION)v118);
                        }
                        else
                        {
                          for ( i20 = **(_QWORD ***)v115; i20 != *(_QWORD **)v115; i20 = (_QWORD *)*i20 )
                          {
                            if ( (struct CResource *)i20[2] == v111 )
                            {
                              v33 = (*((_DWORD *)v111 + 6))-- == 1;
                              v120 = *(_QWORD *)v111;
                              if ( v33 )
                                v121 = (*(__int64 (__fastcall **)(struct CResource *))(v120 + 24))(v111);
                              else
                                v121 = (*(__int64 (__fastcall **)(struct CResource *))(v120 + 8))(v111);
                              if ( v121 && !*((_DWORD *)v111 + 6) )
                              {
                                CResourceList::RemoveFromList(*((CResourceList **)v111 + 2), v111);
                                v190 = *((_QWORD *)v111 + 1);
                                if ( v190 )
                                {
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v190 + 24LL))(v190);
                                  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v111 + 1) + 16LL))(*((_QWORD *)v111 + 1));
                                  *((_QWORD *)v111 + 1) = 0;
                                }
                                (*(void (__fastcall **)(struct CResource *, __int64))(*(_QWORD *)v111 + 32LL))(v111, 1);
                              }
                              break;
                            }
                          }
                          if ( v117 )
                            LeaveCriticalSection((LPCRITICAL_SECTION)(v115 + 40));
                        }
                      }
                      break;
                    }
                  }
                  if ( v112 )
                  {
                    v116 = (const OLECHAR *)CHString::operator unsigned short const *(v284);
                    CLSIDFromString(v116, &pclsid);
                  }
                  v86 = v253;
                }
                break;
              }
            }
            v97 = *(volatile signed __int32 **)&v254.Data1;
            *(GUID *)(*(_QWORD *)&v254.Data1 + 72LL) = pclsid;
            CHString::~CHString((CHString *)v284);
            if ( v5 && _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
            v5 = v97;
            v288 = v97;
            v50 = 1;
          }
        }
      }
      v53 = guidCFGMGRAPI;
      v291 = guidCFGMGRAPI;
      v52 = (_QWORD *)CResourceManager::sm_TheResourceManager;
      for ( i21 = (_QWORD *)*CResourceManager::sm_TheResourceManager; i21 != v52; i21 = (_QWORD *)*i21 )
      {
        v99 = i21[2];
        if ( !memcmp_0((const void *)(v99 + 24), &v291, 0x10u) )
        {
          if ( *(_DWORD *)(v99 + 80) )
            break;
          v317 = v99;
          v100 = 0;
          v318 = 0;
          if ( v99 )
          {
            v101 = v99 + 40;
            CStaticCritSec::Enter((CStaticCritSec *)(v99 + 40));
            v100 = 1;
            v318 = 1;
          }
          else
          {
            v101 = 40;
          }
          if ( *(_DWORD *)(v99 + 80) )
          {
            if ( v100 )
              LeaveCriticalSection((LPCRITICAL_SECTION)v101);
          }
          else
          {
            for ( i22 = **(_QWORD ***)v99; i22 != *(_QWORD **)v99; i22 = (_QWORD *)*i22 )
            {
              if ( (CResource *)i22[2] == v86 )
              {
                v33 = (*((_DWORD *)v86 + 6))-- == 1;
                v103 = *(_QWORD *)v86;
                if ( v33 )
                  v104 = (*(__int64 (__fastcall **)(CResource *))(v103 + 24))(v86);
                else
                  v104 = (*(__int64 (__fastcall **)(CResource *))(v103 + 8))(v86);
                if ( v104 && !*((_DWORD *)v86 + 6) )
                {
                  CResourceList::RemoveFromList(*((CResourceList **)v86 + 2), v86);
                  v122 = *((_QWORD *)v86 + 1);
                  if ( v122 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 24LL))(v122);
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v86 + 1) + 16LL))(*((_QWORD *)v86 + 1));
                    *((_QWORD *)v86 + 1) = 0;
                  }
                  (*(void (__fastcall **)(CResource *, __int64))(*(_QWORD *)v86 + 32LL))(v86, 1);
                }
                break;
              }
            }
            if ( v100 )
            {
              LeaveCriticalSection((LPCRITICAL_SECTION)(v99 + 40));
              v52 = (_QWORD *)CResourceManager::sm_TheResourceManager;
              v53 = guidCFGMGRAPI;
              break;
            }
          }
          goto LABEL_352;
        }
      }
    }
    else
    {
LABEL_352:
      v52 = (_QWORD *)CResourceManager::sm_TheResourceManager;
      v53 = guidCFGMGRAPI;
    }
LABEL_131:
    if ( v251 != v5 )
    {
      v84 = v251;
      v251 = v5;
      v289 = v5;
      if ( v5 )
      {
        _InterlockedIncrement(v5 + 2);
        v52 = (_QWORD *)CResourceManager::sm_TheResourceManager;
        v53 = guidCFGMGRAPI;
      }
      if ( v84 )
      {
        if ( _InterlockedExchangeAdd(v84 + 2, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v84 + 8LL))(v84);
        goto LABEL_72;
      }
    }
  }
  CHString::~CHString((CHString *)v266);
LABEL_19:
  CHString::~CHString((CHString *)v267);
LABEL_20:
  if ( v5 && _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
  v20 = v251;
  if ( v251 && _InterlockedExchangeAdd(v251 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
  if ( v4 && _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 8LL))(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000cfa0  push    rbx
0x18000cfa2  push    rsi
0x18000cfa3  push    rdi
0x18000cfa4  push    r12
0x18000cfa6  push    r13
0x18000cfa8  push    r14
0x18000cfaa  push    r15
0x18000cfac  mov     eax, 2C00h
0x18000cfb1  call    _alloca_probe
0x18000cfb6  sub     rsp, rax
0x18000cfb9  movaps  [rsp+2C38h+var_48], xmm6
0x18000cfc1  mov     rax, cs:__security_cookie
0x18000cfc8  xor     rax, rsp
0x18000cfcb  mov     [rsp+2C38h+var_58], rax
0x18000cfd3  mov     [rsp+2C38h+var_2B90], r8
0x18000cfdb  mov     r13, rdx
0x18000cfde  mov     [rsp+2C38h+var_2AE0], rcx
0x18000cfe6  xor     esi, esi
0x18000cfe8  mov     [rsp+2C38h+var_2AF8], rsi
0x18000cff0  mov     [rsp+2C38h+var_2AC0], rsi
0x18000cff8  xor     eax, eax
0x18000cffa  mov     [rsp+2C38h+var_2BE0], rax
0x18000cfff  mov     [rsp+2C38h+var_2AE8], rax
0x18000d007  xor     r14d, r14d
0x18000d00a  mov     [rsp+2C38h+var_2AF0], r14
0x18000d012  mov     [rsp+2C38h+var_2BF0], r14
0x18000d017  test    rdx, rdx
0x18000d01a  jz      loc_18000D35A
0x18000d020  mov     [rsp+2C38h+var_2BF8], r14d
0x18000d025  movups  xmm0, xmmword ptr cs:?guidCFGMGRAPI@@3U_GUID@@B.Data1; _GUID const guidCFGMGRAPI ...
0x18000d02c  movaps  [rsp+2C38h+Buf2], xmm0
0x18000d031  mov     r15, cs:?sm_TheResourceManager@CResourceManager@@2V1@A; CResourceManager CResourceManager::sm_TheResourceManager
0x18000d038  mov     rbx, [r15]
0x18000d03b  nop     dword ptr [rax+rax+00h]
0x18000d040  cmp     rbx, r15
0x18000d043  jz      short loc_18000D06A
0x18000d045  mov     rdi, [rbx+10h]
0x18000d049  lea     rcx, [rdi+18h]; Buf1
0x18000d04d  mov     r8d, 10h; Size
0x18000d053  lea     rdx, [rsp+2C38h+Buf2]; Buf2
0x18000d058  call    memcmp_0
0x18000d05d  test    eax, eax
0x18000d05f  jz      loc_18000D1EB
0x18000d065  mov     rbx, [rbx]
0x18000d068  jmp     short loc_18000D040
0x18000d06a  mov     [rsp+2C38h+var_2BA8], 0
0x18000d075  xor     ebx, ebx
0x18000d077  mov     [rsp+2C38h+var_2BE8], ebx
0x18000d07b  cmp     [rsp+2C38h+var_2BF8], ebx
0x18000d07f  jz      loc_18000D129
0x18000d085  lea     rcx, [rsp+2C38h+var_2B68]
0x18000d08d  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18000d093  nop
0x18000d094  test    rsi, rsi
0x18000d097  jz      loc_18000F37F
0x18000d09d  movups  xmm6, xmmword ptr cs:?guidCFGMGRAPI@@3U_GUID@@B.Data1; _GUID const guidCFGMGRAPI ...
0x18000d0a4  movaps  [rsp+2C38h+Buf2], xmm6
0x18000d0a9  mov     rdi, cs:?sm_TheResourceManager@CResourceManager@@2V1@A; CResourceManager CResourceManager::sm_TheResourceManager
0x18000d0b0  mov     rbx, [rdi]
0x18000d0b3  cmp     rbx, rdi
0x18000d0b6  jz      short loc_18000D0FB
0x18000d0b8  mov     r15, [rbx+10h]
0x18000d0bc  lea     rcx, [r15+18h]; Buf1
0x18000d0c0  mov     r8d, 10h; Size
0x18000d0c6  lea     rdx, [rsp+2C38h+Buf2]; Buf2
0x18000d0cb  call    memcmp_0
0x18000d0d0  test    eax, eax
0x18000d0d2  jz      short loc_18000D0D9
0x18000d0d4  mov     rbx, [rbx]
0x18000d0d7  jmp     short loc_18000D0B3
0x18000d0d9  mov     rcx, r15; this
0x18000d0dc  call    ?GetResource@CResourceList@@IEAAPEAVCResource@@PEAX@Z; CResourceList::GetResource(void *)
0x18000d0e1  mov     r12, rax
0x18000d0e4  test    rax, rax
0x18000d0e7  jnz     loc_18000E1F8
0x18000d0ed  mov     rdi, cs:?sm_TheResourceManager@CResourceManager@@2V1@A; CResourceManager CResourceManager::sm_TheResourceManager
0x18000d0f4  movups  xmm6, xmmword ptr cs:?guidCFGMGRAPI@@3U_GUID@@B.Data1; _GUID const guidCFGMGRAPI ...
0x18000d0fb  movaps  [rsp+2C38h+Buf2], xmm6
0x18000d100  mov     rbx, [rdi]
0x18000d103  cmp     rbx, rdi
0x18000d106  jnz     loc_18000D1C3
0x18000d10c  mov     [rsp+2C38h+var_2B98], 0
0x18000d117  mov     ebx, [rsp+2C38h+var_2BE8]
0x18000d11b  lea     rcx, [rsp+2C38h+var_2B68]
0x18000d123  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18000d129  mov     r15d, 0FFFFFFFFh
0x18000d12f  test    r14, r14
0x18000d132  jz      short loc_18000D152
0x18000d134  mov     eax, r15d
0x18000d137  lock xadd [r14+8], eax
0x18000d13d  cmp     eax, 1
0x18000d140  jnz     short loc_18000D152
0x18000d142  mov     rax, [r14]
0x18000d145  mov     rcx, r14
0x18000d148  mov     rax, [rax+8]
0x18000d14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d151  nop
0x18000d152  mov     rcx, [rsp+2C38h+var_2BE0]
0x18000d157  test    rcx, rcx
0x18000d15a  jz      short loc_18000D176
0x18000d15c  mov     eax, r15d
0x18000d15f  lock xadd [rcx+8], eax
0x18000d164  cmp     eax, 1
0x18000d167  jnz     short loc_18000D176
0x18000d169  mov     rax, [rcx]
0x18000d16c  mov     rax, [rax+8]
0x18000d170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d175  nop
0x18000d176  test    rsi, rsi
0x18000d179  jz      short loc_18000D196
0x18000d17b  lock xadd [rsi+8], r15d
0x18000d181  cmp     r15d, 1
0x18000d185  jnz     short loc_18000D196
0x18000d187  mov     rax, [rsi]
0x18000d18a  mov     rcx, rsi
0x18000d18d  mov     rax, [rax+8]
0x18000d191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d196  mov     eax, ebx
0x18000d198  mov     rcx, [rsp+2C38h+var_58]
0x18000d1a0  xor     rcx, rsp; StackCookie
0x18000d1a3  call    __security_check_cookie
0x18000d1a8  movaps  xmm6, [rsp+2C38h+var_48]
0x18000d1b0  add     rsp, 2C00h
0x18000d1b7  pop     r15
0x18000d1b9  pop     r14
0x18000d1bb  pop     r13
0x18000d1bd  pop     r12
0x18000d1bf  pop     rdi
0x18000d1c0  pop     rsi
0x18000d1c1  pop     rbx
0x18000d1c2  retn
0x18000d1c3  mov     r15, [rbx+10h]
0x18000d1c7  lea     rcx, [r15+18h]; Buf1
0x18000d1cb  mov     r8d, 10h; Size
0x18000d1d1  lea     rdx, [rsp+2C38h+Buf2]; Buf2
0x18000d1d6  call    memcmp_0
0x18000d1db  test    eax, eax
0x18000d1dd  jz      loc_18000D3C9
0x18000d1e3  mov     rbx, [rbx]
0x18000d1e6  jmp     loc_18000D103
0x18000d1eb  mov     rcx, rdi; this
0x18000d1ee  call    ?GetResource@CResourceList@@IEAAPEAVCResource@@PEAX@Z; CResourceList::GetResource(void *)
0x18000d1f3  mov     r12, rax
0x18000d1f6  mov     qword ptr [rsp+2C38h+var_2BB8], rax
0x18000d1fe  xor     r15d, r15d
0x18000d201  mov     [rsp+2C38h+var_2BA8], r15d
0x18000d209  test    rax, rax
0x18000d20c  jz      loc_18000D075
0x18000d212  mov     rax, [rax]
0x18000d215  mov     rcx, r12
0x18000d218  mov     rax, [rax+38h]
0x18000d21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d221  test    eax, eax
0x18000d223  jz      short loc_18000D285
0x18000d225  mov     rax, [r12+58h]
0x18000d22a  test    rax, rax
0x18000d22d  jz      short loc_18000D24B
0x18000d22f  xor     r8d, r8d
0x18000d232  mov     edx, [r13+44h]
0x18000d236  lea     rcx, [rsp+2C38h+var_2BA8]
0x18000d23e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d243  test    eax, eax
0x18000d245  jz      loc_18000E514
0x18000d24b  mov     [rsp+2C38h+var_2BF8], r15d
0x18000d250  jmp     short loc_18000D285
0x18000d252  movups  xmm0, xmmword ptr [rsp+2C38h+var_29C8.Data1]
0x18000d25a  movups  xmmword ptr [rsi+48h], xmm0
0x18000d25e  lea     rcx, [rsp+2C38h+var_2B30]
0x18000d266  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18000d26c  nop
0x18000d26d  mov     [rsp+2C38h+var_2AC0], rsi
0x18000d275  mov     [rsp+2C38h+var_2BF8], 1
0x18000d27d  mov     r12, qword ptr [rsp+2C38h+var_2BB8]
0x18000d285  movups  xmm0, xmmword ptr cs:?guidCFGMGRAPI@@3U_GUID@@B.Data1; _GUID const guidCFGMGRAPI ...
0x18000d28c  movaps  [rsp+2C38h+Buf2], xmm0
0x18000d291  mov     rdi, cs:?sm_TheResourceManager@CResourceManager@@2V1@A; CResourceManager CResourceManager::sm_TheResourceManager
0x18000d298  mov     rbx, [rdi]
0x18000d29b  nop     dword ptr [rax+rax+00h]
0x18000d2a0  cmp     rbx, rdi
0x18000d2a3  jz      loc_18000D075
0x18000d2a9  mov     r15, [rbx+10h]
0x18000d2ad  lea     rcx, [r15+18h]; Buf1
0x18000d2b1  mov     r8d, 10h; Size
0x18000d2b7  lea     rdx, [rsp+2C38h+Buf2]; Buf2
0x18000d2bc  call    memcmp_0
0x18000d2c1  test    eax, eax
0x18000d2c3  jz      short loc_18000D2CA
0x18000d2c5  mov     rbx, [rbx]
0x18000d2c8  jmp     short loc_18000D2A0
0x18000d2ca  cmp     dword ptr [r15+50h], 0
0x18000d2cf  jnz     loc_18000D075
0x18000d2d5  mov     [rsp+2C38h+var_2AA0], r15
0x18000d2dd  xor     ebx, ebx
0x18000d2df  mov     [rsp+2C38h+var_2A98], ebx
0x18000d2e6  test    r15, r15
0x18000d2e9  jz      loc_18000F375
0x18000d2ef  lea     rdi, [r15+28h]
0x18000d2f3  mov     rcx, rdi; this
0x18000d2f6  call    ?Enter@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Enter(void)
0x18000d2fb  mov     ebx, 1
0x18000d300  mov     [rsp+2C38h+var_2A98], ebx
0x18000d307  cmp     dword ptr [r15+50h], 0
0x18000d30c  jnz     loc_18000EF88
0x18000d312  mov     rcx, [r15]
0x18000d315  mov     rax, [rcx]
0x18000d318  cmp     rax, rcx
0x18000d31b  jz      short loc_18000D343
0x18000d31d  cmp     [rax+10h], r12
0x18000d321  jnz     loc_18000F21E
0x18000d327  sub     dword ptr [r12+18h], 1
0x18000d32d  mov     rax, [r12]
0x18000d331  mov     rcx, r12
0x18000d334  jz      short loc_18000D364
0x18000d336  mov     rax, [rax+8]
0x18000d33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d33f  test    eax, eax
0x18000d341  jnz     short loc_18000D36A
0x18000d343  test    ebx, ebx
0x18000d345  jz      loc_18000D075
0x18000d34b  lea     rcx, [r15+28h]; lpCriticalSection
0x18000d34f  call    cs:__imp_LeaveCriticalSection
0x18000d355  jmp     loc_18000D075
0x18000d35a  mov     ebx, 80041001h
0x18000d35f  jmp     loc_18000D129
0x18000d364  mov     rax, [rax+18h]
0x18000d368  jmp     short loc_18000D33A
0x18000d36a  cmp     dword ptr [r12+18h], 0
0x18000d370  jnz     short loc_18000D343
0x18000d372  mov     rdx, r12; struct CResource *
0x18000d375  mov     rcx, [r12+10h]; this
0x18000d37a  call    ?RemoveFromList@CResourceList@@QEAAXPEAVCResource@@@Z; CResourceList::RemoveFromList(CResource *)
0x18000d37f  mov     rcx, [r12+8]
0x18000d384  test    rcx, rcx
0x18000d387  jz      short loc_18000D3AF
0x18000d389  mov     rax, [rcx]
0x18000d38c  mov     rax, [rax+18h]
0x18000d390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d395  mov     rcx, [r12+8]
0x18000d39a  mov     rax, [rcx]
0x18000d39d  mov     rax, [rax+10h]
0x18000d3a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a6  mov     qword ptr [r12+8], 0
0x18000d3af  mov     rax, [r12]
0x18000d3b3  mov     edx, 1
0x18000d3b8  mov     rcx, r12
0x18000d3bb  mov     rax, [rax+20h]
0x18000d3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3c4  jmp     loc_18000D343
0x18000d3c9  mov     rcx, r15; this
0x18000d3cc  call    ?GetResource@CResourceList@@IEAAPEAVCResource@@PEAX@Z; CResourceList::GetResource(void *)
0x18000d3d1  mov     r13, rax
0x18000d3d4  mov     [rsp+2C38h+var_2BC8], rax
0x18000d3d9  mov     [rsp+2C38h+var_2B98], 0
0x18000d3e4  test    rax, rax
0x18000d3e7  jz      loc_18000D117
0x18000d3ed  mov     rax, [rax]
0x18000d3f0  mov     rcx, r13
0x18000d3f3  mov     rax, [rax+38h]
0x18000d3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3fc  test    eax, eax
0x18000d3fe  jz      loc_18000EF0C
0x18000d404  mov     rax, [r13+60h]
0x18000d408  test    rax, rax
0x18000d40b  jz      loc_18000EF0C
0x18000d411  xor     r8d, r8d
0x18000d414  mov     edx, [rsi+44h]
0x18000d417  lea     rcx, [rsp+2C38h+var_2B98]
0x18000d41f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d424  test    eax, eax
0x18000d426  jnz     loc_18000EF0C
0x18000d42c  mov     ecx, 58h ; 'X'; Size
0x18000d431  call    cs:__imp_malloc
0x18000d437  mov     r15, rax
0x18000d43a  mov     [rsp+2C38h+var_2BE0], rax
0x18000d43f  test    rax, rax
0x18000d442  jz      loc_18000F310
0x18000d448  mov     [rsp+2C38h+var_29E0], rax
0x18000d450  mov     ebx, [rsi+28h]
0x18000d453  mov     edi, [rsp+2C38h+var_2B98]
0x18000d45a  lea     rax, ??_7CRefPtrLite@@6B@; const CRefPtrLite::`vftable'
0x18000d461  mov     [r15], rax
0x18000d464  mov     dword ptr [r15+8], 1
0x18000d46c  lea     rax, ??_7CConfigMgrDevice@@6B@; const CConfigMgrDevice::`vftable'
0x18000d473  mov     [r15], rax
0x18000d476  lea     rcx, [r15+10h]
0x18000d47a  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18000d480  nop
0x18000d481  lea     rcx, [r15+18h]
0x18000d485  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18000d48b  nop
0x18000d48c  lea     rcx, [r15+20h]
0x18000d490  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18000d496  nop
0x18000d497  mov     [r15+28h], ebx
0x18000d49b  mov     qword ptr [r15+30h], 0
0x18000d4a3  mov     dword ptr [r15+38h], 0
0x18000d4ab  mov     [r15+44h], edi
0x18000d4af  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000d4b6  movups  xmmword ptr [rsp+2C38h+var_29B8.Data1], xmm0
0x18000d4be  lea     rcx, [rsp+2C38h+var_2B18]
  ... truncated ...
```
