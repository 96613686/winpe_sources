# PdbManager::Initialize(_LARGE_INTEGER const &,int,int &,Guid &,_LARGE_INTEGER &,int &,int &,int &,int &,FrsStringImpl<ushort,char> &,_GUID &)

- ea: `0x140072eac`
- end: `0x140074ad2`
- name: `?Initialize@PdbManager@@QEAAPEAVFrsStatus@@AEBT_LARGE_INTEGER@@HAEAHAEAVGuid@@AEAT3@1111AEAV?$FrsStringImpl@GD@@AEAU_GUID@@@Z`
- size: `7206`
- prototype: `__int64 __usercall@<rax>(PdbManager *this@<rcx>, union _LARGE_INTEGER *@<rdx>, __int64, __int64, __int64, __int64, int *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `47`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140083130`

## callees

- `0x1400036a0`
- `0x14000cb00`
- `0x14000cdc0`
- `0x14000d980`
- `0x14000dcc0`
- `0x14000dd10`
- `0x14000e34c`
- `0x14000ee94`
- `0x140022ce4`
- `0x1400248f4`
- `0x1400249a4`
- `0x140047e14`
- `0x14004d52c`
- `0x14006afe8`
- `0x14006b418`
- `0x14006b4d4`
- `0x14006b6fc`
- `0x14006c740`
- `0x14006f668`
- `0x14006fc2c`
- `0x14006fee8`
- `0x140070634`
- `0x140070ba4`
- `0x140072414`
- `0x1400727e8`
- `0x140072830`
- `0x14007293c`
- `0x140072a34`
- `0x140072bb0`
- `0x140072eac`
- `0x140074ad8`
- `0x1400753d4`
- `0x140075b9c`
- `0x140078214`
- `0x1400782e0`
- `0x14007a244`
- `0x1400aef70`
- `0x1400bdc18`
- `0x1400be2b8`
- `0x1401b9494`
- `0x1401bda10`
- `0x1401be04c`
- `0x1401be200`
- `0x1401beb7c`
- `0x1401bebec`
- `0x1401bec7c`
- `0x140223010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14007342e`
- `KERNEL32!DeleteFileW` at `0x14007342e`
- `KERNEL32!MoveFileExW` at `0x1400731f1`
- `KERNEL32!MoveFileExW` at `0x1400733eb`
- `KERNEL32!MoveFileExW` at `0x1400731f1`
- `KERNEL32!MoveFileExW` at `0x1400733eb`
- `KERNEL32!GetLastError` at `0x140073213`
- `KERNEL32!GetLastError` at `0x140073409`
- `KERNEL32!GetLastError` at `0x14007344c`
- `KERNEL32!GetLastError` at `0x140073213`
- `KERNEL32!GetLastError` at `0x140073409`
- `KERNEL32!GetLastError` at `0x14007344c`
- `KERNEL32!GetCurrentThreadId` at `0x140073205`
- `KERNEL32!GetCurrentThreadId` at `0x14007338e`
- `KERNEL32!GetCurrentThreadId` at `0x1400733fb`
- `KERNEL32!GetCurrentThreadId` at `0x14007343e`
- `KERNEL32!GetCurrentThreadId` at `0x14007351e`
- `KERNEL32!GetCurrentThreadId` at `0x140073603`
- `KERNEL32!GetCurrentThreadId` at `0x14007368a`
- `KERNEL32!GetCurrentThreadId` at `0x1400736ea`
- `KERNEL32!GetCurrentThreadId` at `0x1400737f6`
- `KERNEL32!GetCurrentThreadId` at `0x140073885`
- `KERNEL32!GetCurrentThreadId` at `0x1400738f6`
- `KERNEL32!GetCurrentThreadId` at `0x140073946`
- `KERNEL32!GetCurrentThreadId` at `0x14007399b`
- `KERNEL32!GetCurrentThreadId` at `0x140073a0c`
- `KERNEL32!GetCurrentThreadId` at `0x140073a5c`
- `KERNEL32!GetCurrentThreadId` at `0x140073aab`
- `KERNEL32!GetCurrentThreadId` at `0x140073b0c`
- `KERNEL32!GetCurrentThreadId` at `0x140073b5b`
- `KERNEL32!GetCurrentThreadId` at `0x140073bab`
- `KERNEL32!GetCurrentThreadId` at `0x140073bfe`
- `KERNEL32!GetCurrentThreadId` at `0x140073c50`
- `KERNEL32!GetCurrentThreadId` at `0x140073ca2`
- `KERNEL32!GetCurrentThreadId` at `0x140073cdf`
- `KERNEL32!GetCurrentThreadId` at `0x140073d20`
- `KERNEL32!GetCurrentThreadId` at `0x140073d97`
- `KERNEL32!GetCurrentThreadId` at `0x140073e02`
- `KERNEL32!GetCurrentThreadId` at `0x140073ed1`
- `KERNEL32!GetCurrentThreadId` at `0x140073f12`
- `KERNEL32!GetCurrentThreadId` at `0x140073f65`
- `KERNEL32!GetCurrentThreadId` at `0x140073fbe`
- `KERNEL32!GetCurrentThreadId` at `0x140074007`
- `KERNEL32!GetCurrentThreadId` at `0x140074053`
- `KERNEL32!GetCurrentThreadId` at `0x1400740e5`
- `KERNEL32!GetCurrentThreadId` at `0x140074131`
- `KERNEL32!GetCurrentThreadId` at `0x14007417d`
- `KERNEL32!GetCurrentThreadId` at `0x1400741c9`
- `KERNEL32!GetCurrentThreadId` at `0x140074310`
- `KERNEL32!GetCurrentThreadId` at `0x140074383`
- `KERNEL32!GetCurrentThreadId` at `0x1400743d5`
- `KERNEL32!GetCurrentThreadId` at `0x140074429`
- `KERNEL32!GetCurrentThreadId` at `0x14007448c`
- `KERNEL32!GetCurrentThreadId` at `0x140074565`
- `KERNEL32!GetCurrentThreadId` at `0x14007462e`
- `KERNEL32!GetCurrentThreadId` at `0x14007468f`
- `KERNEL32!GetCurrentThreadId` at `0x140074859`
- `KERNEL32!GetCurrentThreadId` at `0x140073205`
- `KERNEL32!GetCurrentThreadId` at `0x14007338e`
- `KERNEL32!GetCurrentThreadId` at `0x1400733fb`
- `KERNEL32!GetCurrentThreadId` at `0x14007343e`
- `KERNEL32!GetCurrentThreadId` at `0x14007351e`
- `KERNEL32!GetCurrentThreadId` at `0x140073603`
- `KERNEL32!GetCurrentThreadId` at `0x14007368a`
- `KERNEL32!GetCurrentThreadId` at `0x1400736ea`
- `KERNEL32!GetCurrentThreadId` at `0x1400737f6`
- `KERNEL32!GetCurrentThreadId` at `0x140073885`
- `KERNEL32!GetCurrentThreadId` at `0x1400738f6`
- `KERNEL32!GetCurrentThreadId` at `0x140073946`
- `KERNEL32!GetCurrentThreadId` at `0x14007399b`
- `KERNEL32!GetCurrentThreadId` at `0x140073a0c`
- `KERNEL32!GetCurrentThreadId` at `0x140073a5c`
- `KERNEL32!GetCurrentThreadId` at `0x140073aab`
- `KERNEL32!GetCurrentThreadId` at `0x140073b0c`
- `KERNEL32!GetCurrentThreadId` at `0x140073b5b`
- `KERNEL32!GetCurrentThreadId` at `0x140073bab`
- `KERNEL32!GetCurrentThreadId` at `0x140073bfe`
- `KERNEL32!GetCurrentThreadId` at `0x140073c50`
- `KERNEL32!GetCurrentThreadId` at `0x140073ca2`
- `KERNEL32!GetCurrentThreadId` at `0x140073cdf`
- `KERNEL32!GetCurrentThreadId` at `0x140073d20`
- `KERNEL32!GetCurrentThreadId` at `0x140073d97`
- `KERNEL32!GetCurrentThreadId` at `0x140073e02`
- `KERNEL32!GetCurrentThreadId` at `0x140073ed1`
- `KERNEL32!GetCurrentThreadId` at `0x140073f12`
- `KERNEL32!GetCurrentThreadId` at `0x140073f65`
- `KERNEL32!GetCurrentThreadId` at `0x140073fbe`
- `KERNEL32!GetCurrentThreadId` at `0x140074007`
- `KERNEL32!GetCurrentThreadId` at `0x140074053`
- `KERNEL32!GetCurrentThreadId` at `0x1400740e5`
- `KERNEL32!GetCurrentThreadId` at `0x140074131`
- `KERNEL32!GetCurrentThreadId` at `0x14007417d`
- `KERNEL32!GetCurrentThreadId` at `0x1400741c9`
- `KERNEL32!GetCurrentThreadId` at `0x140074310`
- `KERNEL32!GetCurrentThreadId` at `0x140074383`
- `KERNEL32!GetCurrentThreadId` at `0x1400743d5`
- `KERNEL32!GetCurrentThreadId` at `0x140074429`
- `KERNEL32!GetCurrentThreadId` at `0x14007448c`
- `KERNEL32!GetCurrentThreadId` at `0x140074565`
- `KERNEL32!GetCurrentThreadId` at `0x14007462e`
- `KERNEL32!GetCurrentThreadId` at `0x14007468f`
- `KERNEL32!GetCurrentThreadId` at `0x140074859`
- `ESENT!JetTerm2` at `0x14007331d`
- `ESENT!JetTerm2` at `0x14007331d`
- `ESENT!JetSetSystemParameterA` at `0x140073678`
- `ESENT!JetSetSystemParameterA` at `0x1400736d8`
- `ESENT!JetSetSystemParameterA` at `0x140073867`
- `ESENT!JetSetSystemParameterA` at `0x1400738d8`
- `ESENT!JetSetSystemParameterA` at `0x140073934`
- `ESENT!JetSetSystemParameterA` at `0x140073989`
- `ESENT!JetSetSystemParameterA` at `0x1400739ee`
- `ESENT!JetSetSystemParameterA` at `0x140073a4a`
- `ESENT!JetSetSystemParameterA` at `0x140073a99`
- `ESENT!JetSetSystemParameterA` at `0x140073afa`
- `ESENT!JetSetSystemParameterA` at `0x140073b49`
- `ESENT!JetSetSystemParameterA` at `0x140073b99`
- `ESENT!JetSetSystemParameterA` at `0x140073bec`
- `ESENT!JetSetSystemParameterA` at `0x140073c3e`
- `ESENT!JetSetSystemParameterA` at `0x140073c90`
- `ESENT!JetSetSystemParameterA` at `0x140073678`
- `ESENT!JetSetSystemParameterA` at `0x1400736d8`
- `ESENT!JetSetSystemParameterA` at `0x140073867`
- `ESENT!JetSetSystemParameterA` at `0x1400738d8`
- `ESENT!JetSetSystemParameterA` at `0x140073934`
- `ESENT!JetSetSystemParameterA` at `0x140073989`
- `ESENT!JetSetSystemParameterA` at `0x1400739ee`
- `ESENT!JetSetSystemParameterA` at `0x140073a4a`
- `ESENT!JetSetSystemParameterA` at `0x140073a99`
- `ESENT!JetSetSystemParameterA` at `0x140073afa`
- `ESENT!JetSetSystemParameterA` at `0x140073b49`
- `ESENT!JetSetSystemParameterA` at `0x140073b99`
- `ESENT!JetSetSystemParameterA` at `0x140073bec`
- `ESENT!JetSetSystemParameterA` at `0x140073c3e`
- `ESENT!JetSetSystemParameterA` at `0x140073c90`
- `ESENT!JetCreateInstanceA` at `0x1400737db`
- `ESENT!JetCreateInstanceA` at `0x1400737db`
- `ESENT!JetInit` at `0x140073cd1`
- `ESENT!JetInit` at `0x140073cd1`
- `ESENT!JetCreateDatabaseA` at `0x140073eb6`
- `ESENT!JetCreateDatabaseA` at `0x140073eb6`
- `ESENT!JetBeginTransaction` at `0x140073f00`
- `ESENT!JetBeginTransaction` at `0x140073f00`
- `ESENT!JetCreateTableColumnIndexA` at `0x140073f53`
- `ESENT!JetCreateTableColumnIndexA` at `0x140073fac`
- `ESENT!JetCreateTableColumnIndexA` at `0x140073ff5`
- `ESENT!JetCreateTableColumnIndexA` at `0x140074041`
- `ESENT!JetCreateTableColumnIndexA` at `0x1400740d3`
- `ESENT!JetCreateTableColumnIndexA` at `0x14007411f`
- `ESENT!JetCreateTableColumnIndexA` at `0x14007416b`
- `ESENT!JetCreateTableColumnIndexA` at `0x1400741b7`
- `ESENT!JetCreateTableColumnIndexA` at `0x140073f53`
- `ESENT!JetCreateTableColumnIndexA` at `0x140073fac`
- `ESENT!JetCreateTableColumnIndexA` at `0x140073ff5`
- `ESENT!JetCreateTableColumnIndexA` at `0x140074041`
- `ESENT!JetCreateTableColumnIndexA` at `0x1400740d3`
- `ESENT!JetCreateTableColumnIndexA` at `0x14007411f`
- `ESENT!JetCreateTableColumnIndexA` at `0x14007416b`
- `ESENT!JetCreateTableColumnIndexA` at `0x1400741b7`
- `ESENT!JetCommitTransaction` at `0x140074371`
- `ESENT!JetCommitTransaction` at `0x140074371`
- `ESENT!JetRollback` at `0x1400749d4`
- `ESENT!JetRollback` at `0x1400749d4`
- `ESENT!JetCloseDatabase` at `0x1400743c3`
- `ESENT!JetCloseDatabase` at `0x1400743c3`
- `ESENT!JetEndSession` at `0x1400732aa`
- `ESENT!JetEndSession` at `0x140074417`
- `ESENT!JetEndSession` at `0x14007447a`
- `ESENT!JetEndSession` at `0x1400732aa`
- `ESENT!JetEndSession` at `0x140074417`
- `ESENT!JetEndSession` at `0x14007447a`
- `ESENT!JetAttachDatabaseA` at `0x140073de8`
- `ESENT!JetAttachDatabaseA` at `0x140073de8`
- `ESENT!JetBeginSessionA` at `0x140073d85`
- `ESENT!JetBeginSessionA` at `0x140073d85`

## string_xrefs

- `0x1400730ec`: `$db_update$`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
struct FrsStatus *__fastcall PdbManager::Initialize(
        PdbManager::PdbManagerData **this,
        union _LARGE_INTEGER *a2,
        int a3,
        _DWORD *a4,
        struct _GUID *a5,
        _QWORD *a6,
        int *a7,
        int *a8,
        int *a9,
        unsigned __int16 *a10,
        __int64 a11,
        struct _GUID *a12)
{
  struct FrsStatus *v14; // rdi
  JET_ERR TableColumnIndexA; // esi
  __int64 v16; // rax
  JET_API_PTR v17; // r12
  __int64 v18; // rdx
  PdbManager::PdbManagerData *v19; // rax
  __int64 v20; // rbx
  PdbManager *v21; // rcx
  PdbManager *v22; // rcx
  struct FrsStatus *AsrInstanceKey; // rbx
  const unsigned __int16 *v24; // r14
  __int64 v25; // rcx
  __int64 v26; // rbx
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  unsigned __int16 **v29; // rcx
  DWORD v30; // eax
  int v31; // edx
  __int64 v32; // rcx
  char *v33; // r8
  struct FrsStatus *v34; // rax
  DWORD v35; // ebx
  DWORD v36; // ebx
  DWORD v37; // eax
  struct FrsStatus *v38; // rax
  __int64 v39; // r13
  struct FrsStatus *Directory; // rax
  DWORD v41; // eax
  struct FrsStatus *v42; // rax
  int v43; // edx
  char *v44; // r8
  struct FrsStatus *v45; // r8
  __int64 v46; // rax
  __int64 v47; // r8
  int v48; // edx
  char *v49; // r8
  __int64 v50; // rax
  __int64 v51; // r8
  __int64 v52; // rax
  __int64 v53; // r8
  __int64 v54; // rax
  unsigned int v55; // eax
  DWORD v56; // eax
  int v57; // edx
  char *const v58; // r8
  struct FrsStatus *v59; // rax
  DWORD v60; // eax
  struct FrsStatus *v61; // rax
  __int64 v62; // r8
  int v63; // edx
  char *const v64; // r8
  __int64 v65; // r13
  __int64 v66; // rax
  DWORD v67; // eax
  int v68; // edx
  char *const v69; // r8
  struct FrsStatus *v70; // rax
  __int64 v71; // r8
  __int64 v72; // rax
  int v73; // edx
  char *const v74; // r8
  int v75; // edx
  char *const v76; // r8
  int v77; // edx
  char *const v78; // r8
  struct FrsStatus *v79; // rax
  int v80; // edx
  char *const v81; // r8
  int v82; // edx
  char *const v83; // r8
  int v84; // edx
  char *const v85; // r8
  int v86; // edx
  char *const v87; // r8
  int v88; // edx
  char *const v89; // r8
  int v90; // edx
  char *const v91; // r8
  PdbManager *v92; // rcx
  int v93; // edx
  char *const v94; // r8
  struct _GUID *v95; // r14
  struct _GUID *v96; // r12
  int v97; // edx
  int *inserted; // rbx
  DWORD v99; // eax
  int v100; // edx
  char *const v101; // r8
  DWORD v102; // eax
  int v103; // edx
  char *const v104; // r8
  int v105; // edx
  char *const v106; // r8
  struct FrsStatus *v107; // rax
  int v108; // edx
  char *const v109; // r8
  int v110; // edx
  char *const v111; // r8
  struct FrsStatus *GiRecordMinimal; // rax
  int v113; // edx
  DWORD v114; // eax
  __int64 v115; // rcx
  unsigned int v116; // eax
  DWORD v117; // eax
  __int64 v118; // rcx
  bool v119; // cf
  DWORD v120; // eax
  __int64 v121; // rcx
  __int64 v122; // rax
  __int64 v123; // rcx
  union _LARGE_INTEGER *v124; // r8
  DWORD v125; // eax
  __int64 v126; // rcx
  struct _GUID v127; // xmm0
  unsigned int szParam; // [rsp+20h] [rbp-E0h]
  unsigned int szParama; // [rsp+20h] [rbp-E0h]
  DWORD v131; // [rsp+28h] [rbp-D8h]
  DWORD v132; // [rsp+28h] [rbp-D8h]
  DWORD v133; // [rsp+28h] [rbp-D8h]
  DWORD v134; // [rsp+28h] [rbp-D8h]
  DWORD v135; // [rsp+28h] [rbp-D8h]
  DWORD v136; // [rsp+28h] [rbp-D8h]
  DWORD v137; // [rsp+28h] [rbp-D8h]
  DWORD v138; // [rsp+28h] [rbp-D8h]
  DWORD v139; // [rsp+28h] [rbp-D8h]
  DWORD v140; // [rsp+28h] [rbp-D8h]
  DWORD v141; // [rsp+28h] [rbp-D8h]
  DWORD v142; // [rsp+28h] [rbp-D8h]
  DWORD v143; // [rsp+28h] [rbp-D8h]
  DWORD v144; // [rsp+28h] [rbp-D8h]
  DWORD v145; // [rsp+28h] [rbp-D8h]
  DWORD v146; // [rsp+28h] [rbp-D8h]
  int v147; // [rsp+30h] [rbp-D0h]
  DWORD v148; // [rsp+38h] [rbp-C8h]
  JET_ERR v149; // [rsp+50h] [rbp-B0h] BYREF
  JET_DBID pdbid; // [rsp+54h] [rbp-ACh] BYREF
  JET_INSTANCE instance; // [rsp+58h] [rbp-A8h] BYREF
  JET_SESID sesid; // [rsp+60h] [rbp-A0h] BYREF
  int v153; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v154; // [rsp+70h] [rbp-90h] BYREF
  int v155; // [rsp+78h] [rbp-88h]
  int v156; // [rsp+7Ch] [rbp-84h]
  const wchar_t *v157; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v158; // [rsp+88h] [rbp-78h] BYREF
  int v159; // [rsp+90h] [rbp-70h] BYREF
  int *v160; // [rsp+98h] [rbp-68h] BYREF
  __int16 v161; // [rsp+A0h] [rbp-60h] BYREF
  void **v162; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v163; // [rsp+B0h] [rbp-50h] BYREF
  void **v164; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v165; // [rsp+C0h] [rbp-40h] BYREF
  int v166; // [rsp+C8h] [rbp-38h] BYREF
  int v167; // [rsp+CCh] [rbp-34h]
  int v168; // [rsp+D0h] [rbp-30h] BYREF
  int v169; // [rsp+D4h] [rbp-2Ch] BYREF
  void **v170; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v171; // [rsp+E0h] [rbp-20h] BYREF
  void **v172; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v173; // [rsp+F0h] [rbp-10h] BYREF
  struct FrsStatus *v174; // [rsp+F8h] [rbp-8h] BYREF
  union _LARGE_INTEGER *v175; // [rsp+100h] [rbp+0h] BYREF
  _QWORD *v176; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 *v177; // [rsp+110h] [rbp+10h] BYREF
  __int64 v178; // [rsp+118h] [rbp+18h]
  _DWORD *v179; // [rsp+120h] [rbp+20h]
  struct _GUID *v180; // [rsp+128h] [rbp+28h]
  struct _GUID *v181; // [rsp+130h] [rbp+30h]
  void **v182; // [rsp+138h] [rbp+38h] BYREF
  __int64 v183; // [rsp+140h] [rbp+40h] BYREF
  void **v184; // [rsp+148h] [rbp+48h] BYREF
  __int64 v185; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v186[16]; // [rsp+158h] [rbp+58h] BYREF
  void **v187; // [rsp+168h] [rbp+68h] BYREF
  struct FrsStatus *v188; // [rsp+170h] [rbp+70h] BYREF
  char v189[8]; // [rsp+178h] [rbp+78h] BYREF
  char v190[8]; // [rsp+180h] [rbp+80h] BYREF
  char v191[8]; // [rsp+188h] [rbp+88h] BYREF
  char v192[8]; // [rsp+190h] [rbp+90h] BYREF
  char v193[8]; // [rsp+198h] [rbp+98h] BYREF
  struct FrsStatus *v194; // [rsp+1A0h] [rbp+A0h] BYREF
  const wchar_t *v195; // [rsp+1A8h] [rbp+A8h] BYREF
  int v196; // [rsp+1B0h] [rbp+B0h]
  int v197; // [rsp+1B4h] [rbp+B4h]
  const wchar_t *v198; // [rsp+1B8h] [rbp+B8h]
  JET_TABLECREATE_A ptablecreate; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _GUID v200; // [rsp+210h] [rbp+110h] BYREF
  int *v201[2]; // [rsp+220h] [rbp+120h] BYREF
  _QWORD v202[2]; // [rsp+230h] [rbp+130h] BYREF
  __int128 v203; // [rsp+240h] [rbp+140h]
  __int128 v204; // [rsp+250h] [rbp+150h]
  __int128 v205; // [rsp+260h] [rbp+160h]
  _QWORD v206[2]; // [rsp+270h] [rbp+170h] BYREF
  __int128 v207; // [rsp+280h] [rbp+180h] BYREF
  _QWORD v208[2]; // [rsp+290h] [rbp+190h] BYREF
  __int128 v209; // [rsp+2A0h] [rbp+1A0h] BYREF
  struct _GUID v210; // [rsp+2B0h] [rbp+1B0h]
  struct _GUID v211; // [rsp+2C0h] [rbp+1C0h]
  __int64 v212; // [rsp+2D0h] [rbp+1D0h]
  __int64 v213; // [rsp+2D8h] [rbp+1D8h]
  __int128 v214; // [rsp+2E0h] [rbp+1E0h]
  _BYTE v215[16]; // [rsp+2F0h] [rbp+1F0h] BYREF
  char v216[40]; // [rsp+300h] [rbp+200h] BYREF

  v179 = a4;
  v153 = a3;
  v175 = a2;
  v181 = a5;
  v176 = a6;
  v201[0] = a7;
  v160 = a8;
  v158 = a10;
  v180 = a12;
  v14 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  *a9 = 0;
  *(_DWORD *)a10 = 0;
  v177 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !byte_140315A80 )
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
  FrsStringImpl<unsigned short,char>::Set(a11, &v177);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v177);
  instance = -1;
  sesid = -1;
  pdbid = -1;
  TableColumnIndexA = 0;
  *a12 = 0;
  PdbManager::PdbManagerData::Initialize(*this, a2);
  v16 = Config::ConfigInstance<Config::ContentSet>::Get(*(_QWORD *)*this);
  v17 = (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v16 + 624));
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 48LL))(v18);
  v187 = &NtfsFileSystem::`vftable';
  FilePath::FilePath((FilePath *)&v164);
  v19 = *this;
  v178 = (__int64)*this + 32;
  v20 = v178;
  VolumeId::VolumeId((VolumeId *)v215, (const struct VolumeId *)(*((_QWORD *)v19 + 1) + 168LL));
  v167 = 0;
  v202[0] = 0;
  v202[1] = 0;
  v203 = 0;
  v204 = 0;
  v205 = 0;
  v206[0] = 0;
  v206[1] = 0;
  v207 = 0;
  v200 = 0;
  v166 = 0;
  v159 = 0;
  FilePath::FilePath((FilePath *)&v184);
  *v179 = 0;
  FilePath::operator=(&v164, v20);
  FilePath::ChopToParent((FilePath *)&v164);
  v161 = 92;
  FrsStringImpl<unsigned short,char>::Append(&v165, &v161, 1);
  AsrInstanceKey = PdbManager::DBExportImportExists(v21, (const struct FilePath *)&v164, 1, &v166);
  if ( AsrInstanceKey )
    goto LABEL_198;
  AsrInstanceKey = PdbManager::DBExportImportExists(v22, (const struct FilePath *)&v164, 0, a9);
  if ( AsrInstanceKey )
    goto LABEL_198;
  FileUtil::CreateWin32LongPath((const struct FilePath *)&v164, (struct FilePath *)&v184);
  FilePath::Append((FilePath *)&v184, L"$db_update$");
  v24 = (const unsigned __int16 *)(v185 + 18);
  AsrInstanceKey = FileUtil::FileExists((const unsigned __int16 *)(v185 + 18), &v159);
  if ( AsrInstanceKey )
    goto LABEL_198;
  if ( v159 )
  {
    FilePath::FilePath((FilePath *)&v162);
    FileUtil::CreateWin32LongPath((const struct FilePath *)&v164, (struct FilePath *)&v162);
    FilePath::Append((FilePath *)&v162, L"dfsr.db.backup");
    AsrInstanceKey = FileUtil::FileExists(v24, &v159);
    if ( AsrInstanceKey )
    {
      v162 = &FilePath::`vftable';
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v163);
      v149 = 0;
      goto LABEL_15;
    }
    if ( v159 )
    {
      FilePath::FilePath((FilePath *)&v172);
      FilePath::FilePath((FilePath *)&v170);
      FileUtil::CreateWin32LongPath((const struct FilePath *)&v164, (struct FilePath *)&v172);
      FilePath::Append((FilePath *)&v172, L"dfsr.db.old");
      FileUtil::CreateWin32LongPath((const struct FilePath *)&v164, (struct FilePath *)&v170);
      FilePath::Append((FilePath *)&v170, L"dfsr.db");
      v26 = v171;
      if ( !MoveFileExW((LPCWSTR)(v171 + 18), (LPCWSTR)(v173 + 18), 1u) )
      {
        CurrentThreadId = GetCurrentThreadId();
        LastError = GetLastError();
        v148 = CurrentThreadId;
        v147 = 5321;
LABEL_12:
        AsrInstanceKey = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                               LastError,
                                               0,
                                               1,
                                               "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                               "PdbManager::Initialize",
                                               v147,
                                               v148,
                                               0);
        v170 = &FilePath::`vftable';
        FrsStringImpl<char,unsigned short>::ReleaseBody(&v171);
        v172 = &FilePath::`vftable';
        FrsStringImpl<char,unsigned short>::ReleaseBody(&v173);
        v162 = &FilePath::`vftable';
        v29 = (unsigned __int16 **)&v163;
LABEL_13:
        FrsStringImpl<char,unsigned short>::ReleaseBody(v29);
LABEL_14:
        v149 = 0;
        goto LABEL_15;
      }
      if ( !MoveFileExW((LPCWSTR)(v163 + 18), (LPCWSTR)(v26 + 18), 1u) )
      {
        v35 = GetCurrentThreadId();
        LastError = GetLastError();
        v148 = v35;
        v147 = 5329;
        goto LABEL_12;
      }
      if ( !DeleteFileW(v24) )
      {
        v36 = GetCurrentThreadId();
        LastError = GetLastError();
        v148 = v36;
        v147 = 5337;
        goto LABEL_12;
      }
      v170 = &FilePath::`vftable';
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v171);
      v172 = &FilePath::`vftable';
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v173);
    }
    v162 = &FilePath::`vftable';
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v163);
  }
  if ( !v153 )
  {
    v169 = 1;
    FilePath::FilePath((FilePath *)&v182);
    FileUtil::CreateWin32LongPath((const struct FilePath *)&v164, (struct FilePath *)&v182);
    FilePath::Append((FilePath *)&v182, L"dfsr.db");
    v194 = FileUtil::FileExists((const unsigned __int16 *)(v183 + 18), &v169);
    CLEAR_ERROR(&v194);
    v182 = &FilePath::`vftable';
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v183);
    if ( !v169 )
    {
      v37 = GetCurrentThreadId();
      v38 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                  9209,
                                  0,
                                  3,
                                  "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                  "PdbManager::Initialize",
                                  5344,
                                  v37,
                                  0);
LABEL_38:
      AsrInstanceKey = v38;
      goto LABEL_14;
    }
  }
  AsrInstanceKey = (struct FrsStatus *)PdbManager::GetAsrInstanceKey(v25, &v200, a11);
  if ( AsrInstanceKey )
    goto LABEL_198;
  ScopedLock::ScopedLock((ScopedLock *)v186, (struct ScopedCS *)PdbManager::cs);
  v39 = v165;
  if ( !PdbManager::globalInited )
  {
    v168 = 0;
    Directory = NtfsFileSystem::ForceMakeDirectory(
                  (NtfsFileSystem *)&v187,
                  (const struct VolumeId *)v215,
                  (const unsigned __int16 *)(v165 + 18),
                  1,
                  1,
                  1,
                  &v168);
    AsrInstanceKey = Directory;
    v174 = Directory;
    if ( Directory && *((_DWORD *)Directory + 1) == 3 )
    {
      if ( v153 )
      {
LABEL_46:
        ScopedLock::~ScopedLock((ScopedLock *)v186);
        goto LABEL_14;
      }
      CLEAR_ERROR(&v174);
      v41 = GetCurrentThreadId();
      v42 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                  9209,
                                  0,
                                  3,
                                  "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                  "PdbManager::Initialize",
                                  5366,
                                  v41,
                                  0);
LABEL_45:
      AsrInstanceKey = v42;
      goto LABEL_46;
    }
    TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 0x68u, 0x80u, 0);
    if ( TableColumnIndexA )
    {
      v131 = GetCurrentThreadId();
      szParam = 5373;
LABEL_49:
      v42 = LogTranslatedError(TableColumnIndexA, v43, v44, "PdbManager::Initialize", szParam, v131, 1, 0);
      goto LABEL_45;
    }
    TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 0x40u, 0x2000u, 0);
    if ( TableColumnIndexA )
    {
      v131 = GetCurrentThreadId();
      szParam = 5377;
      goto LABEL_49;
    }
    PdbManager::globalInited = 1;
  }
  ScopedLock::~ScopedLock((ScopedLock *)v186);
  AsrInstanceKey = PdbManager::GetDbLossState((PdbManager *)this, v160);
  if ( AsrInstanceKey )
    goto LABEL_198;
  if ( *v160 )
  {
    v45 = PdbManager::Delete((PdbManager *)this, 0);
    v188 = v45;
    if ( v45 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v195 = L"PdbManager::Initialize";
        v196 = 5392;
        v197 = 3;
        v198 = L"PDBX";
        dbgobj::DbgPrint<unsigned short,FrsStatus>(&v195, L"%?", v45);
      }
      CLEAR_ERROR(&v188);
    }
  }
  v46 = FrsStringImpl<char,unsigned short>::FrsStringImpl<char,unsigned short>(v189, *(_QWORD *)(v178 + 8) + 18LL, v45);
  TableColumnIndexA = JetCreateInstanceA(&instance, (JET_PCSTR)(*(_QWORD *)v46 + 17LL));
  FrsStringImpl<char,unsigned short>::ReleaseBody(v189);
  if ( TableColumnIndexA )
  {
    v132 = GetCurrentThreadId();
    szParama = 5398;
LABEL_63:
    v38 = LogTranslatedError(TableColumnIndexA, v48, v49, "PdbManager::Initialize", szParama, v132, 1, 0);
    goto LABEL_38;
  }
  *((_DWORD *)*this + 14) = 1;
  v50 = FrsStringImpl<char,unsigned short>::FrsStringImpl<char,unsigned short>(v190, v39 + 18, v47);
  TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 0, 0, (JET_PCSTR)(*(_QWORD *)v50 + 17LL));
  FrsStringImpl<char,unsigned short>::ReleaseBody(v190);
  if ( TableColumnIndexA )
  {
    v132 = GetCurrentThreadId();
    szParama = 5407;
    goto LABEL_63;
  }
  v52 = FrsStringImpl<char,unsigned short>::FrsStringImpl<char,unsigned short>(v191, v39 + 18, v51);
  TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 1u, 0, (JET_PCSTR)(*(_QWORD *)v52 + 17LL));
  FrsStringImpl<char,unsigned short>::ReleaseBody(v191);
  if ( TableColumnIndexA )
  {
    v132 = GetCurrentThreadId();
    szParama = 5411;
    goto LABEL_63;
  }
  TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 0x64u, 1u, 0);
  if ( TableColumnIndexA )
  {
    v132 = GetCurrentThreadId();
    szParama = 5415;
    goto LABEL_63;
  }
  TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 3u, 0, "fsr");
  if ( TableColumnIndexA )
  {
    v132 = GetCurrentThreadId();
    szParama = 5419;
    goto LABEL_63;
  }
  v54 = FrsStringImpl<char,unsigned short>::FrsStringImpl<char,unsigned short>(v192, v39 + 18, v53);
  TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 2u, 0, (JET_PCSTR)(*(_QWORD *)v54 + 17LL));
  FrsStringImpl<char,unsigned short>::ReleaseBody(v192);
  if ( TableColumnIndexA )
  {
    v132 = GetCurrentThreadId();
    szParama = 5423;
    goto LABEL_63;
  }
  TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 0x11u, 1u, 0);
  if ( TableColumnIndexA )
  {
    v132 = GetCurrentThreadId();
    szParama = 5427;
    goto LABEL_63;
  }
  TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 0x2Du, 0, 0);
  if ( TableColumnIndexA )
  {
    v132 = GetCurrentThreadId();
    szParama = 5431;
    goto LABEL_63;
  }
  v55 = 4 * v17;
  if ( (unsigned int)(4 * v17) < 0x40 )
    v55 = 64;
  TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 0x3Cu, v55, 0);
  if ( TableColumnIndexA )
  {
    v132 = GetCurrentThreadId();
    szParama = 5436;
    goto LABEL_63;
  }
  TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 5u, v17, 0);
  if ( TableColumnIndexA )
  {
    v132 = GetCurrentThreadId();
    szParama = 5440;
    goto LABEL_63;
  }
  TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 6u, 0x20u, 0);
  if ( TableColumnIndexA )
  {
    v132 = GetCurrentThreadId();
    szParama = 5444;
    goto LABEL_63;
  }
  TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 8u, (unsigned int)(32 * v17), 0);
  if ( TableColumnIndexA )
  {
    v132 = GetCurrentThreadId();
    szParama = 5448;
    goto LABEL_63;
  }
  TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 9u, 0x1000u, 0);
  if ( TableColumnIndexA )
  {
    v132 = GetCurrentThreadId();
    szParama = 5452;
    goto LABEL_63;
  }
  TableColumnIndexA = JetSetSystemParameterA(&instance, 0, 0xCu, 0x400u, 0);
  if ( TableColumnIndexA )
  {
    v132 = GetCurrentThreadId();
    szParama = 5456;
    goto LABEL_63;
  }
  TableColumnIndexA = JetInit(&instance);
  v56 = GetCurrentThreadId();
  v59 = LogTranslatedError(TableColumnIndexA, v57, v58, "PdbManager::Initialize", 0x1554u, v56, 1, 0);
  AsrInstanceKey = v59;
  if ( TableColumnIndexA == -1811 )
  {
    v60 = GetCurrentThreadId();
    v61 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                9214,
                                0,
                                3,
                                "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                "PdbManager::Initialize",
                                5468,
                                v60,
                                0);
    v59 = PROPAGATE_ERROR_WITH_NEW_STATUS(AsrInstanceKey, v61);
    AsrInstanceKey = v59;
  }
  if ( v59 )
    goto LABEL_198;
  TableColumnIndexA = JetBeginSessionA(instance, &sesid, 0, 0);
  if ( TableColumnIndexA )
  {
    v133 = GetCurrentThreadId();
    v38 = LogTranslatedError(TableColumnIndexA, v63, v64, "PdbManager::Initialize", 0x1567u, v133, 1, 0);
    goto LABEL_38;
  }
  v65 = v178;
  v66 = FrsStringImpl<char,unsigned short>::FrsStringImpl<char,unsigned short>(v193, *(_QWORD *)(v178 + 8) + 18LL, v62);
  TableColumnIndexA = JetAttachDatabaseA(sesid, (JET_PCSTR)(*(_QWORD *)v66 + 17LL), 0);
  FrsStringImpl<char,unsigned short>::ReleaseBody(v193);
  v67 = GetCurrentThreadId();
  v70 = LogTranslatedError(TableColumnIndexA, v68, v69, "PdbManager::Initialize", 0x156Bu, v67, 1, 0);
  AsrInstanceKey = v70;
  v174 = v70;
  if ( TableColumnIndexA != -1811 || !v153 )
  {
    if ( v70 )
      goto LABEL_198;
    TableColumnIndexA = JetEndSession(sesid, 0);
    if ( TableColumnIndexA )
    {
      v146 = GetCurrentThreadId();
      v38 = LogTranslatedError(TableColumnIndexA, v110, v111, "PdbManager::Initialize", 0x15D4u, v146, 1, 0);
      goto LABEL_38;
    }
    sesid = -1;
    *((_QWORD *)*this + 6) = instance;
    GiRecordMinimal = PdbManager::RetrieveGiRecordMinimal((PdbManager *)this, (struct _GI_RECORD *)v202);
    AsrInstanceKey = GiRecordMinimal;
    if ( !GiRecordMinimal && !v166 )
    {
      v113 = (int)v175;
      if ( v206[0] != v175->QuadPart )
      {
        *v176 = v206[0];
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v154 = L"PdbManager::Initialize";
          v155 = 5608;
          v156 = 2;
          v157 = L"PDBX";
          dbgobj::DbgPrint<unsigned short,__int64,__int64,VolumeId>(
            (unsigned int)&v154,
            v113,
            (unsigned int)v206,
            v113,
            (__int64)v215);
        }
        v114 = GetCurrentThreadId();
        GiRecordMinimal = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                v115,
                                                9212,
                                                0,
                                                3,
                                                "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                                "PdbManager::Initialize",
                                                5614,
                                                v114,
                                                0);
        AsrInstanceKey = GiRecordMinimal;
      }
    }
    if ( !GiRecordMinimal
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v154 = L"PdbManager::Initialize";
      v155 = 5618;
      v156 = 4;
      v157 = L"PDBX";
      v153 = 14;
      dbgobj::DbgPrint<unsigned short,unsigned long,int>(
        &v154,
        L"Database schema version: %d current version: %d",
        &v207,
        &v153);
    }
    if ( AsrInstanceKey )
      goto LABEL_169;
    if ( DWORD1(v207) > 0xE || (v116 = v207) == 0 )
    {
      v117 = GetCurrentThreadId();
      AsrInstanceKey = (struct FrsStatus *)FrsStatusList::PushNewError(
                                             v118,
                                             9213,
                                             0,
                                             3,
                                             "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                             "PdbManager::Initialize",
                                             5627,
                                             v117,
                                             0);
      if ( AsrInstanceKey )
        goto LABEL_169;
      v116 = v207;
    }
    v119 = v116 < 0xE;
    if ( v116 > 0xE )
    {
      if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DeleteDbOnWrongSchema) )
      {
        v120 = GetCurrentThreadId();
        AsrInstanceKey = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v121,
                                               9213,
                                               0,
                                               3,
                                               "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                               "PdbManager::Initialize",
                                               5640,
                                               v120,
                                               0);
        if ( AsrInstanceKey )
          goto LABEL_169;
      }
      v119 = (unsigned int)v207 < 0xE;
    }
    if ( v119 )
      AsrInstanceKey = PdbManager::UpgradeDbSchema((PdbManager *)this, (struct _GI_RECORD *)v202);
LABEL_169:
    v208[0] = 0;
    v208[1] = 0;
    v209 = 0;
    v210 = 0;
    v211 = 0;
    v212 = 0;
    v213 = 0;
    v214 = 0;
    if ( !AsrInstanceKey )
    {
      AsrInstanceKey = PdbManager::RetrieveGiRecord((PdbManager *)this, (struct _GI_RECORD *)v208);
      if ( !AsrInstanceKey
        && (v200.Data1 || *(_DWORD *)&v200.Data2 || *(_DWORD *)v200.Data4 || *(_DWORD *)&v200.Data4[4]) )
      {
        v122 = v209 - *(_QWORD *)&v200.Data1;
        if ( (_QWORD)v209 == *(_QWORD *)&v200.Data1 )
          v122 = *((_QWORD *)&v209 + 1) - *(_QWORD *)v200.Data4;
        if ( v122 )
        {
          v153 = 0;
          FrsGUIDToStringW(&v160, *((_QWORD *)*this + 1) + 184LL);
          v124 = (union _LARGE_INTEGER *)PdbManager::CheckASRRestoredVolume(v123, &v160, &v153);
          v175 = v124;
          if ( v124 )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
            {
              v154 = L"PdbManager::Initialize";
              v155 = 5702;
              v156 = 3;
              v157 = L"PDBX";
              dbgobj::DbgPrint<unsigned short,FrsStatus>(&v154, L"CheckASRRestoredVolumeASR failed. Error:%?", v124);
            }
            CLEAR_ERROR((struct FrsStatus **)&v175);
          }
          else if ( v153 )
          {
            v125 = GetCurrentThreadId();
            AsrInstanceKey = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                   v126,
                                                   9220,
                                                   0,
                                                   3,
                                                   "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                                   "PdbManager::Initialize",
                                                   5695,
                                                   v125,
                                                   0);
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v154 = L"PdbManager::Initialize";
              v155 = 5696;
              v156 = 4;
              v157 = L"PDBX";
              dbgobj::DbgPrint<unsigned short,_GUID,_GUID,FrsStringImpl<unsigned short,char>>(
                (unsigned int)&v154,
                (unsigned int)L"ASR ID Change. Previous value:%?, new value:%?. Begin non authoritative restore for volume:{%?}",
                (unsigned int)&v209,
                (unsigned int)&v200,
                (__int64)&v160);
            }
            *(_DWORD *)v158 = 1;
          }
          else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v154 = L"PdbManager::Initialize";
            v155 = 5690;
            v156 = 4;
            v157 = L"PDBX";
            dbgobj::DbgPrint<unsigned short,_GUID,_GUID,FrsStringImpl<unsigned short,char>>(
              (unsigned int)&v154,
              (unsigned int)L"ASR ID Change. Previous value:%?, new value:%?. Volume:{%?} is not listed to be restored",
              (unsigned int)&v209,
              (unsigned int)&v200,
              (__int64)&v160);
          }
          FrsStringImpl<char,unsigned short>::ReleaseBody(&v160);
        }
      }
      if ( !AsrInstanceKey )
      {
        *v180 = v210;
        AsrInstanceKey = PdbManager::GetDirtyFileState((PdbManager *)this, v201[0]);
        if ( !AsrInstanceKey )
        {
          v127 = v211;
          *v181 = v211;
          *((struct _GUID *)*this + 1) = v127;
          goto LABEL_208;
        }
      }
    }
    goto LABEL_198;
  }
  CLEAR_ERROR(&v174);
  if ( *v160 || (AsrInstanceKey = PdbManager::CreateDbLossNameHolderFile((PdbManager *)this)) == 0 )
  {
    AsrInstanceKey = PdbManager::CreateDirtyFile((PdbManager *)this, 0);
    if ( !AsrInstanceKey )
    {
      v72 = FrsStringImpl<char,unsigned short>::FrsStringImpl<char,unsigned short>(
              &v176,
              *(_QWORD *)(v65 + 8) + 18LL,
              v71);
      TableColumnIndexA = JetCreateDatabaseA(sesid, (JET_PCSTR)(*(_QWORD *)v72 + 17LL), szConnect, &pdbid, 0);
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v176);
      if ( TableColumnIndexA )
      {
        v134 = GetCurrentThreadId();
        v38 = LogTranslatedError(TableColumnIndexA, v73, v74, "PdbManager::Initialize", 0x1584u, v134, 1, 0);
        goto LABEL_38;
      }
      TableColumnIndexA = JetBeginTransaction(sesid);
      if ( TableColumnIndexA )
      {
        v135 = GetCurrentThreadId();
        v38 = LogTranslatedError(TableColumnIndexA, v75, v76, "PdbManager::Initialize", 0x1586u, v135, 1, 0);
        goto LABEL_38;
      }
      v167 = 1;
      TableColumnIndexA = JetCreateTableColumnIndexA(sesid, pdbid, &PdbManager::PdbManagerData::tables);
      if ( TableColumnIndexA )
      {
        v136 = GetCurrentThreadId();
        v79 = LogTranslatedError(TableColumnIndexA, v77, v78, "PdbManager::Initialize", 0x158Bu, v136, 1, 0);
LABEL_108:
        AsrInstanceKey = v79;
        goto LABEL_199;
      }
      TableColumnIndexA = JetCreateTableColumnIndexA(sesid, pdbid, &::ptablecreate);
      if ( TableColumnIndexA )
      {
        v137 = GetCurrentThreadId();
        v79 = LogTranslatedError(TableColumnIndexA, v80, v81, "PdbManager::Initialize", 0x158Fu, v137, 1, 0);
        goto LABEL_108;
      }
      TableColumnIndexA = JetCreateTableColumnIndexA(sesid, pdbid, &stru_14030C4D0);
      if ( TableColumnIndexA )
      {
        v138 = GetCurrentThreadId();
        v79 = LogTranslatedError(TableColumnIndexA, v82, v83, "PdbManager::Initialize", 0x1592u, v138, 1, 0);
        goto LABEL_108;
      }
      TableColumnIndexA = JetCreateTableColumnIndexA(sesid, pdbid, &stru_14030C520);
      if ( TableColumnIndexA )
      {
        v139 = GetCurrentThreadId();
        v79 = LogTranslatedError(TableColumnIndexA, v84, v85, "PdbManager::Initialize", 0x1595u, v139, 1, 0);
        goto LABEL_108;
      }
      ptablecreate = off_14030C570;
      TableColumnIndexA = JetCreateTableColumnIndexA(sesid, pdbid, &ptablecreate);
      if ( TableColumnIndexA )
      {
        v140 = GetCurrentThreadId();
        v79 = LogTranslatedError(TableColumnIndexA, v86, v87, "PdbManager::Initialize", 0x1599u, v140, 1, 0);
        goto LABEL_108;
      }
      TableColumnIndexA = JetCreateTableColumnIndexA(sesid, pdbid, &stru_14030C5C0);
      if ( TableColumnIndexA )
      {
        v141 = GetCurrentThreadId();
        v79 = LogTranslatedError(TableColumnIndexA, v88, v89, "PdbManager::Initialize", 0x159Cu, v141, 1, 0);
        goto LABEL_108;
      }
      TableColumnIndexA = JetCreateTableColumnIndexA(sesid, pdbid, &stru_14030C610);
      if ( TableColumnIndexA )
      {
        v142 = GetCurrentThreadId();
        v79 = LogTranslatedError(TableColumnIndexA, v90, v91, "PdbManager::Initialize", 0x159Fu, v142, 1, 0);
        goto LABEL_108;
      }
      TableColumnIndexA = JetCreateTableColumnIndexA(sesid, pdbid, &stru_14030C660);
      if ( TableColumnIndexA )
      {
        v143 = GetCurrentThreadId();
        v79 = LogTranslatedError(TableColumnIndexA, v93, v94, "PdbManager::Initialize", 0x15A2u, v143, 1, 0);
        goto LABEL_108;
      }
      v95 = v181;
      AsrInstanceKey = PdbManager::GenerateNewDBGuid(v92, (struct Guid *)v181);
      v174 = AsrInstanceKey;
      if ( !AsrInstanceKey )
      {
        v158 = &FrsStringImpl<unsigned short,char>::s_Empty;
        if ( !byte_140315A80 )
          _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
        v96 = v180;
        AsrInstanceKey = (struct FrsStatus *)PdbManager::GetSsrInstanceKey(v180, &v158);
        if ( !AsrInstanceKey )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v154 = L"PdbManager::Initialize";
            v155 = 5552;
            v156 = 4;
            v157 = L"PDBX";
            *(struct _GUID *)v201 = *v95;
            dbgobj::DbgPrint<unsigned short,_GUID,_GUID,FrsStringImpl<unsigned short,char>,_GUID,_GUID>(
              (unsigned int)&v154,
              v97,
              (unsigned int)v201,
              (unsigned int)&v200,
              (__int64)&v158,
              (__int64)v96,
              (__int64)v216);
          }
          *((struct _GUID *)*this + 1) = *v95;
          inserted = (int *)GITableHelper::InsertInitialRec(sesid, &ptablecreate, v175, v95, &v200, v96);
          if ( !inserted
            || (v99 = GetCurrentThreadId(),
                (AsrInstanceKey = LogTranslatedError(
                                    inserted[1],
                                    v100,
                                    v101,
                                    "PdbManager::Initialize",
                                    0x15BBu,
                                    v99,
                                    0,
                                    (struct FrsStatus *)inserted)) == 0) )
          {
            *v179 = 1;
            TableColumnIndexA = JetCommitTransaction(sesid, 0);
            if ( !TableColumnIndexA )
            {
              TableColumnIndexA = JetCloseDatabase(sesid, pdbid, 0);
              if ( TableColumnIndexA )
              {
                v144 = GetCurrentThreadId();
                v107 = LogTranslatedError(TableColumnIndexA, v105, v106, "PdbManager::Initialize", 0x15C6u, v144, 1, 0);
              }
              else
              {
                TableColumnIndexA = JetEndSession(sesid, 0);
                if ( !TableColumnIndexA )
                {
                  *((_QWORD *)*this + 6) = instance;
                  FrsStringImpl<char,unsigned short>::ReleaseBody(&v158);
                  goto LABEL_208;
                }
                v145 = GetCurrentThreadId();
                v107 = LogTranslatedError(TableColumnIndexA, v108, v109, "PdbManager::Initialize", 0x15C7u, v145, 1, 0);
              }
              AsrInstanceKey = v107;
              v29 = &v158;
              goto LABEL_13;
            }
            v102 = GetCurrentThreadId();
            AsrInstanceKey = LogTranslatedError(
                               TableColumnIndexA,
                               v103,
                               v104,
                               "PdbManager::Initialize",
                               0x15C3u,
                               v102,
                               1,
                               0);
          }
        }
        FrsStringImpl<char,unsigned short>::ReleaseBody(&v158);
LABEL_199:
        v149 = JetRollback(sesid, 0);
        if ( v149 < 0 && g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v154 = L"PdbManager::Initialize";
          v155 = 5733;
          v156 = 4;
          v157 = L"PDBX";
          dbgobj::DbgPrint<unsigned short,unsigned int>(&v154, L"Ignoring JET error. Error:%d", &v149);
        }
        goto LABEL_15;
      }
    }
  }
LABEL_198:
  v149 = 0;
  if ( v167 )
    goto LABEL_199;
LABEL_15:
  if ( sesid != -1 )
  {
    v149 = JetEndSession(sesid, 0);
    if ( v149 < 0 && g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v154 = L"PdbManager::Initialize";
      v155 = 5740;
      v156 = 4;
      v157 = L"PDBX";
      dbgobj::DbgPrint<unsigned short,unsigned int>(&v154, L"Ignoring JET error. Error:%d", &v149);
    }
  }
  if ( *((_DWORD *)*this + 14) )
  {
    v149 = JetTerm2(instance, 6u);
    *((_DWORD *)*this + 14) = 0;
    *((_QWORD *)*this + 6) = -1;
    if ( v149 < 0 && g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v154 = L"PdbManager::Initialize";
      v155 = 5751;
      v156 = 4;
      v157 = L"PDBX";
      dbgobj::DbgPrint<unsigned short,unsigned int>(&v154, L"Ignoring JET error. Error:%d", &v149);
    }
  }
  v30 = GetCurrentThreadId();
  if ( AsrInstanceKey )
    v34 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v32,
                                *((unsigned int *)AsrInstanceKey + 1),
                                *((unsigned int *)AsrInstanceKey + 2),
                                *(unsigned int *)AsrInstanceKey,
                                "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                "PdbManager::Initialize",
                                5760,
                                v30,
                                AsrInstanceKey);
  else
    v34 = LogTranslatedError(TableColumnIndexA, v31, v33, "PdbManager::Initialize", 0x1682u, v30, 1, 0);
  v14 = v34;
LABEL_208:
  v184 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v185);
  VolumeId::~VolumeId((VolumeId *)v215);
  v164 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v165);
  return v14;
}

```

## disassembly

```asm
0x140072eac  mov     [rsp-8+arg_10], rbx
0x140072eb1  push    rbp
0x140072eb2  push    rsi
0x140072eb3  push    rdi
0x140072eb4  push    r12
0x140072eb6  push    r13
0x140072eb8  push    r14
0x140072eba  push    r15
0x140072ebc  lea     rbp, [rsp-230h]
0x140072ec4  sub     rsp, 330h
0x140072ecb  mov     rax, cs:__security_cookie
0x140072ed2  xor     rax, rsp
0x140072ed5  mov     [rbp+260h+var_38], rax
0x140072edc  mov     [rbp+260h+var_240], r9
0x140072ee0  mov     [rsp+360h+var_2F8], r8d
0x140072ee5  mov     rbx, rdx
0x140072ee8  mov     [rbp+260h+var_260], rdx
0x140072eec  mov     r15, rcx
0x140072eef  mov     rcx, [rbp+260h+arg_20]
0x140072ef6  mov     [rbp+260h+var_230], rcx
0x140072efa  mov     rdx, [rbp+260h+arg_28]
0x140072f01  mov     [rbp+260h+var_258], rdx
0x140072f05  mov     r10, [rbp+260h+arg_30]
0x140072f0c  mov     [rbp+260h+var_140], r10
0x140072f13  mov     rax, [rbp+260h+arg_38]
0x140072f1a  mov     [rbp+260h+var_2C8], rax
0x140072f1e  mov     r14, [rbp+260h+arg_40]
0x140072f25  mov     r8, [rbp+260h+arg_48]
0x140072f2c  mov     [rbp+260h+var_2D8], r8
0x140072f30  mov     r13, [rbp+260h+arg_50]
0x140072f37  mov     r12, [rbp+260h+arg_58]
0x140072f3e  mov     [rbp+260h+var_238], r12
0x140072f42  xor     edi, edi
0x140072f44  mov     [r9], edi
0x140072f47  xorps   xmm0, xmm0
0x140072f4a  movups  xmmword ptr [rcx], xmm0
0x140072f4d  mov     [rdx], rdi
0x140072f50  mov     [r10], edi
0x140072f53  mov     [rax], edi
0x140072f55  mov     [r14], edi
0x140072f58  mov     [r8], edi
0x140072f5b  lea     rax, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x140072f62  mov     [rbp+260h+var_250], rax
0x140072f66  cmp     cs:byte_140315A80, dil
0x140072f6d  jnz     short loc_140072F76
0x140072f6f  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x140072f76  lea     rdx, [rbp+260h+var_250]
0x140072f7a  mov     rcx, r13
0x140072f7d  call    ?Set@?$FrsStringImpl@GD@@QEAA_NAEBV1@@Z; FrsStringImpl<ushort,char>::Set(FrsStringImpl<ushort,char> const &)
0x140072f82  lea     rcx, [rbp+260h+var_250]
0x140072f86  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140072f8b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140072f8f  mov     [rsp+360h+instance], rax
0x140072f94  mov     [rsp+360h+sesid], rax
0x140072f99  or      [rsp+360h+pdbid], 0FFFFFFFFh
0x140072f9e  mov     esi, edi
0x140072fa0  xorps   xmm0, xmm0
0x140072fa3  movups  xmmword ptr [r12], xmm0
0x140072fa8  mov     rdx, rbx; union _LARGE_INTEGER *
0x140072fab  mov     rcx, [r15]; this
0x140072fae  call    ?Initialize@PdbManagerData@PdbManager@@QEAAXAEBT_LARGE_INTEGER@@@Z; PdbManager::PdbManagerData::Initialize(_LARGE_INTEGER const &)
0x140072fb3  mov     rcx, [r15]
0x140072fb6  mov     rcx, [rcx]
0x140072fb9  call    ?Get@?$ConfigInstance@VContentSet@Config@@@Config@@QEAAPEAVContentSet@2@XZ; Config::ConfigInstance<Config::ContentSet>::Get(void)
0x140072fbe  mov     rdx, rax
0x140072fc1  lea     rcx, [rax+270h]; this
0x140072fc8  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x140072fcd  mov     r12d, eax
0x140072fd0  mov     rax, [rdx]
0x140072fd3  mov     rcx, rdx
0x140072fd6  mov     rax, [rax+30h]
0x140072fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072fdf  lea     rax, ??_7NtfsFileSystem@@6B@; const NtfsFileSystem::`vftable'
0x140072fe6  mov     [rbp+260h+var_1F8], rax
0x140072fea  lea     rcx, [rbp+260h+var_2A8]; this
0x140072fee  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x140072ff3  nop
0x140072ff4  mov     rax, [r15]
0x140072ff7  lea     rbx, [rax+20h]
0x140072ffb  mov     [rbp+260h+var_248], rbx
0x140072fff  mov     rdx, [rax+8]
0x140073003  add     rdx, 0A8h; struct VolumeId *
0x14007300a  lea     rcx, [rbp+260h+var_70]; this
0x140073011  call    ??0VolumeId@@QEAA@AEBV0@@Z; VolumeId::VolumeId(VolumeId const &)
0x140073016  nop
0x140073017  mov     [rbp+260h+var_294], edi
0x14007301a  mov     [rbp+260h+var_130], rdi
0x140073021  xor     eax, eax
0x140073023  mov     [rbp+260h+var_128], rax
0x14007302a  xorps   xmm0, xmm0
0x14007302d  movups  [rbp+260h+var_120], xmm0
0x140073034  movups  [rbp+260h+var_110], xmm0
0x14007303b  movups  [rbp+260h+var_100], xmm0
0x140073042  mov     [rbp+260h+var_F0], rax
0x140073049  mov     [rbp+260h+var_E8], rdi
0x140073050  movups  [rbp+260h+var_E0], xmm0
0x140073057  xorps   xmm1, xmm1
0x14007305a  movups  xmmword ptr [rbp+260h+var_150.Data1], xmm1
0x140073061  mov     [rbp+260h+var_298], edi
0x140073064  mov     [rbp+260h+var_2D0], edi
0x140073067  lea     rcx, [rbp+260h+var_218]; this
0x14007306b  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x140073070  nop
0x140073071  mov     rax, [rbp+260h+var_240]
0x140073075  mov     [rax], edi
0x140073077  mov     rdx, rbx
0x14007307a  lea     rcx, [rbp+260h+var_2A8]
0x14007307e  call    ??4FilePath@@QEAAAEAV0@AEBV0@@Z; FilePath::operator=(FilePath const &)
0x140073083  lea     rcx, [rbp+260h+var_2A8]; this
0x140073087  call    ?ChopToParent@FilePath@@QEAAHXZ; FilePath::ChopToParent(void)
0x14007308c  mov     eax, 5Ch ; '\'
0x140073091  mov     [rbp+260h+var_2C0], ax
0x140073095  lea     ebx, [rax-5Bh]
0x140073098  mov     r8d, ebx
0x14007309b  lea     rdx, [rbp+260h+var_2C0]
0x14007309f  lea     rcx, [rbp+260h+var_2A0]
0x1400730a3  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG_K@Z; FrsStringImpl<ushort,char>::Append(ushort const *,unsigned __int64)
0x1400730a8  lea     r9, [rbp+260h+var_298]; int *
0x1400730ac  mov     r8d, ebx; int
0x1400730af  lea     rdx, [rbp+260h+var_2A8]; struct FilePath *
0x1400730b3  call    ?DBExportImportExists@PdbManager@@AEAAPEAVFrsStatus@@AEBVFilePath@@HAEAH@Z; PdbManager::DBExportImportExists(FilePath const &,int,int &)
0x1400730b8  mov     rbx, rax
0x1400730bb  test    rax, rax
0x1400730be  jnz     loc_1400749B9
0x1400730c4  mov     r9, r14; int *
0x1400730c7  xor     r8d, r8d; int
0x1400730ca  lea     rdx, [rbp+260h+var_2A8]; struct FilePath *
0x1400730ce  call    ?DBExportImportExists@PdbManager@@AEAAPEAVFrsStatus@@AEBVFilePath@@HAEAH@Z; PdbManager::DBExportImportExists(FilePath const &,int,int &)
0x1400730d3  mov     rbx, rax
0x1400730d6  test    rax, rax
0x1400730d9  jnz     loc_1400749B9
0x1400730df  lea     rdx, [rbp+260h+var_218]; struct FilePath *
0x1400730e3  lea     rcx, [rbp+260h+var_2A8]; struct FilePath *
0x1400730e7  call    ?CreateWin32LongPath@FileUtil@@SAXAEBVFilePath@@AEAV2@@Z; FileUtil::CreateWin32LongPath(FilePath const &,FilePath &)
0x1400730ec  lea     rdx, aDbUpdate; "$db_update$"
0x1400730f3  lea     rcx, [rbp+260h+var_218]; this
0x1400730f7  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x1400730fc  mov     r14, [rbp+260h+var_210]
0x140073100  add     r14, 12h
0x140073104  lea     rdx, [rbp+260h+var_2D0]; int *
0x140073108  mov     rcx, r14; unsigned __int16 *
0x14007310b  call    ?FileExists@FileUtil@@SAPEAVFrsStatus@@PEBGAEAH@Z; FileUtil::FileExists(ushort const *,int &)
0x140073110  mov     rbx, rax
0x140073113  test    rax, rax
0x140073116  jnz     loc_1400749B9
0x14007311c  cmp     [rbp+260h+var_2D0], edi
0x14007311f  jz      loc_1400734A8
0x140073125  lea     rcx, [rbp+260h+var_2B8]; this
0x140073129  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14007312e  nop
0x14007312f  lea     rdx, [rbp+260h+var_2B8]; struct FilePath *
0x140073133  lea     rcx, [rbp+260h+var_2A8]; struct FilePath *
0x140073137  call    ?CreateWin32LongPath@FileUtil@@SAXAEBVFilePath@@AEAV2@@Z; FileUtil::CreateWin32LongPath(FilePath const &,FilePath &)
0x14007313c  lea     rdx, aDfsrDbBackup; "dfsr.db.backup"
0x140073143  lea     rcx, [rbp+260h+var_2B8]; this
0x140073147  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x14007314c  lea     rdx, [rbp+260h+var_2D0]; int *
0x140073150  mov     rcx, r14; unsigned __int16 *
0x140073153  call    ?FileExists@FileUtil@@SAPEAVFrsStatus@@PEBGAEAH@Z; FileUtil::FileExists(ushort const *,int &)
0x140073158  mov     rbx, rax
0x14007315b  test    rax, rax
0x14007315e  jz      short loc_140073184
0x140073160  lea     r14, ??_7FilePath@@6B@; const FilePath::`vftable'
0x140073167  mov     [rbp+260h+var_2B8], r14
0x14007316b  lea     rcx, [rbp+260h+var_2B0]
0x14007316f  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140073174  mov     [rsp+360h+var_310], edi
0x140073178  lea     r12, aPdbmanagerInit_0; "PdbManager::Initialize"
0x14007317f  jmp     loc_140073296
0x140073184  cmp     [rbp+260h+var_2D0], edi
0x140073187  jz      loc_140073492
0x14007318d  lea     rcx, [rbp+260h+var_278]; this
0x140073191  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x140073196  nop
0x140073197  lea     rcx, [rbp+260h+var_288]; this
0x14007319b  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x1400731a0  nop
0x1400731a1  lea     rdx, [rbp+260h+var_278]; struct FilePath *
0x1400731a5  lea     rcx, [rbp+260h+var_2A8]; struct FilePath *
0x1400731a9  call    ?CreateWin32LongPath@FileUtil@@SAXAEBVFilePath@@AEAV2@@Z; FileUtil::CreateWin32LongPath(FilePath const &,FilePath &)
0x1400731ae  lea     rdx, aDfsrDbOld; "dfsr.db.old"
0x1400731b5  lea     rcx, [rbp+260h+var_278]; this
0x1400731b9  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x1400731be  lea     rdx, [rbp+260h+var_288]; struct FilePath *
0x1400731c2  lea     rcx, [rbp+260h+var_2A8]; struct FilePath *
0x1400731c6  call    ?CreateWin32LongPath@FileUtil@@SAXAEBVFilePath@@AEAV2@@Z; FileUtil::CreateWin32LongPath(FilePath const &,FilePath &)
0x1400731cb  lea     rdx, aDfsrDb; "dfsr.db"
0x1400731d2  lea     rcx, [rbp+260h+var_288]; this
0x1400731d6  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x1400731db  mov     rdx, [rbp+260h+var_270]
0x1400731df  add     rdx, 12h; lpNewFileName
0x1400731e3  mov     rbx, [rbp+260h+var_280]
0x1400731e7  mov     r8d, 1; dwFlags
0x1400731ed  lea     rcx, [rbx+12h]; lpExistingFileName
0x1400731f1  call    cs:__imp_MoveFileExW
0x1400731f8  nop     dword ptr [rax+rax+00h]
0x1400731fd  test    eax, eax
0x1400731ff  jnz     loc_1400733D9
0x140073205  call    cs:__imp_GetCurrentThreadId
0x14007320c  nop     dword ptr [rax+rax+00h]
0x140073211  mov     ebx, eax
0x140073213  call    cs:__imp_GetLastError
0x14007321a  nop     dword ptr [rax+rax+00h]
0x14007321f  mov     [rsp+360h+var_320], rdi
0x140073224  mov     dword ptr [rsp+360h+var_328], ebx
0x140073228  mov     dword ptr [rsp+360h+var_330], 14C9h
0x140073230  lea     r12, aPdbmanagerInit_0; "PdbManager::Initialize"
0x140073237  mov     [rsp+360h+var_338], r12
0x14007323c  lea     rcx, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x140073243  mov     [rsp+360h+szParam], rcx
0x140073248  mov     r9d, 1
0x14007324e  xor     r8d, r8d
0x140073251  mov     edx, eax
0x140073253  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140073258  mov     rbx, rax
0x14007325b  lea     r14, ??_7FilePath@@6B@; const FilePath::`vftable'
0x140073262  mov     [rbp+260h+var_288], r14
0x140073266  lea     rcx, [rbp+260h+var_280]
0x14007326a  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14007326f  nop
0x140073270  mov     [rbp+260h+var_278], r14
0x140073274  lea     rcx, [rbp+260h+var_270]
0x140073278  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14007327d  nop
0x14007327e  mov     [rbp+260h+var_2B8], r14
0x140073282  lea     rcx, [rbp+260h+var_2B0]
0x140073286  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14007328b  mov     [rsp+360h+var_310], edi
0x14007328f  lea     r14, ??_7FilePath@@6B@; const FilePath::`vftable'
0x140073296  lea     r13, aPdbmanagerInit; "PdbManager::Initialize"
0x14007329d  mov     rcx, [rsp+360h+sesid]; sesid
0x1400732a2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400732a6  jz      short loc_14007330B
0x1400732a8  xor     edx, edx; grbit
0x1400732aa  call    cs:__imp_JetEndSession
0x1400732b1  nop     dword ptr [rax+rax+00h]
0x1400732b6  mov     [rsp+360h+var_310], eax
0x1400732ba  test    eax, eax
0x1400732bc  jns     short loc_14007330B
0x1400732be  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400732c5  test    rax, rax
0x1400732c8  jz      short loc_14007330B
0x1400732ca  cmp     [rax+40h], edi
0x1400732cd  jz      short loc_14007330B
0x1400732cf  cmp     dword ptr [rax+38h], 4
0x1400732d3  jl      short loc_14007330B
0x1400732d5  mov     [rsp+360h+var_2F0], r13
0x1400732da  mov     [rsp+360h+var_2E8], 166Ch
0x1400732e2  mov     [rsp+360h+var_2E4], 4
0x1400732ea  lea     rax, aPdbx; "PDBX"
0x1400732f1  mov     [rbp+260h+var_2E0], rax
0x1400732f5  lea     r8, [rsp+360h+var_310]
0x1400732fa  lea     rdx, aIgnoringJetErr; "Ignoring JET error. Error:%d"
0x140073301  lea     rcx, [rsp+360h+var_2F0]
0x140073306  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x14007330b  mov     rax, [r15]
0x14007330e  cmp     [rax+38h], edi
0x140073311  jz      short loc_14007338E
0x140073313  mov     edx, 6; grbit
0x140073318  mov     rcx, [rsp+360h+instance]; instance
0x14007331d  call    cs:__imp_JetTerm2
0x140073324  nop     dword ptr [rax+rax+00h]
0x140073329  mov     [rsp+360h+var_310], eax
0x14007332d  mov     rax, [r15]
0x140073330  mov     [rax+38h], edi
0x140073333  mov     rax, [r15]
0x140073336  or      qword ptr [rax+30h], 0FFFFFFFFFFFFFFFFh
0x14007333b  cmp     [rsp+360h+var_310], edi
0x14007333f  jge     short loc_14007338E
0x140073341  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140073348  test    rax, rax
0x14007334b  jz      short loc_14007338E
0x14007334d  cmp     [rax+40h], edi
0x140073350  jz      short loc_14007338E
0x140073352  cmp     dword ptr [rax+38h], 4
0x140073356  jl      short loc_14007338E
0x140073358  mov     [rsp+360h+var_2F0], r13
0x14007335d  mov     [rsp+360h+var_2E8], 1677h
0x140073365  mov     [rsp+360h+var_2E4], 4
0x14007336d  lea     rax, aPdbx; "PDBX"
0x140073374  mov     [rbp+260h+var_2E0], rax
0x140073378  lea     r8, [rsp+360h+var_310]
0x14007337d  lea     rdx, aIgnoringJetErr; "Ignoring JET error. Error:%d"
0x140073384  lea     rcx, [rsp+360h+var_2F0]
0x140073389  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x14007338e  call    cs:__imp_GetCurrentThreadId
0x140073395  nop     dword ptr [rax+rax+00h]
0x14007339a  test    rbx, rbx
0x14007339d  jz      loc_140074A55
0x1400733a3  mov     [rsp+360h+var_320], rbx
0x1400733a8  mov     dword ptr [rsp+360h+var_328], eax
0x1400733ac  mov     dword ptr [rsp+360h+var_330], 1680h
0x1400733b4  mov     [rsp+360h+var_338], r12
0x1400733b9  lea     rax, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x1400733c0  mov     [rsp+360h+szParam], rax
0x1400733c5  mov     r9d, [rbx]
0x1400733c8  mov     r8d, [rbx+8]
0x1400733cc  mov     edx, [rbx+4]
0x1400733cf  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400733d4  jmp     loc_140074A78
  ... truncated ...
```
