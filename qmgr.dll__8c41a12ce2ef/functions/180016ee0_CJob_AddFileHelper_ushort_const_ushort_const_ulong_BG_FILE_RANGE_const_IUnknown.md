# CJob::AddFileHelper(ushort const *,ushort const *,ulong,_BG_FILE_RANGE * const,IUnknown *)

- ea: `0x180016ee0`
- end: `0x1800185f2`
- name: `?AddFileHelper@CJob@@QEAAJPEBG0KQEAU_BG_FILE_RANGE@@PEAUIUnknown@@@Z`
- size: `5906`
- prototype: `__int64 __fastcall(CJob *this, unsigned __int16 *, unsigned __int16 *, unsigned int, struct _BG_FILE_RANGE *const, struct IUnknown *)`
- caller_count: `3`
- callee_count: `39`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b640`
- `0x18008abdc`
- `0x1800cc950`

## callees

- `0x180006640`
- `0x180008b70`
- `0x18000c7d0`
- `0x18000dcb0`
- `0x180016d60`
- `0x180016ee0`
- `0x180018d00`
- `0x180019690`
- `0x180019a30`
- `0x180019d90`
- `0x18001a6fc`
- `0x18002887c`
- `0x18002fd88`
- `0x1800302e8`
- `0x18004e6b4`
- `0x18005e894`
- `0x18006263c`
- `0x180066e20`
- `0x180066e6c`
- `0x180068424`
- `0x18008a9a0`
- `0x18008c444`
- `0x18008db34`
- `0x180096b4c`
- `0x180099074`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800a3de8`
- `0x1800ab7b0`
- `0x1800acacc`
- `0x1800b13b4`
- `0x1800b674c`
- `0x1800c6b38`
- `0x1800d950c`
- `0x1800eb15c`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800175c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001768b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017c82`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800175c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001768b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017c82`
- `ntdll!EtwEventEnabled` at `0x180017530`
- `ntdll!EtwEventEnabled` at `0x18001813f`
- `ntdll!EtwEventEnabled` at `0x180017530`
- `ntdll!EtwEventEnabled` at `0x18001813f`
- `ntdll!EtwEventWrite` at `0x180018484`
- `ntdll!EtwEventWrite` at `0x180018484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001778a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001809d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001833b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001778a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001809d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001833b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001793c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017a55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001793c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017a55`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001711e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001711e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180017987`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180017987`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017032`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001704d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017068`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017233`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001724e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017269`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017032`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001704d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017068`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017233`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001724e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017269`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001776c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001776c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180018097`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180018102`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180018239`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180018331`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180018097`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180018102`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180018239`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180018331`

## pseudocode

```c
// Hidden C++ exception states: #wind=18 #try_helpers=1
__int64 __fastcall CJob::AddFileHelper(
        CJob *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        struct _BG_FILE_RANGE *const a5,
        struct IUnknown *a6)
{
  PSID *v11; // rbx
  bool v12; // bl
  unsigned int v13; // ebx
  unsigned int v14; // edi
  const unsigned __int16 *v15; // rdi
  PSID *v16; // rbx
  bool v17; // bl
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // ebx
  int v21; // ecx
  __int64 v22; // r13
  int v23; // ecx
  volatile signed __int32 *v24; // rdi
  _DWORD *v25; // rax
  void *v26; // r15
  volatile signed __int32 *v27; // rax
  volatile signed __int32 *v28; // rbx
  unsigned int LastError; // ecx
  unsigned int TokenIntegrityLevel; // esi
  AppPackageInfo *v31; // r8
  int v32; // ecx
  HANDLE *v33; // rdx
  void *v34; // rcx
  __int64 v35; // rcx
  signed int v36; // eax
  unsigned int v37; // ecx
  PSID v38; // rcx
  struct CRangeCollection *v39; // rbx
  unsigned int v40; // r15d
  CRangeCollection *v41; // rax
  unsigned int i; // edx
  __int64 v43; // rax
  unsigned __int64 v44; // r8
  CFile *v45; // rax
  CFile *v46; // r15
  CFile *v47; // rax
  CFile **v48; // rdx
  int v49; // ecx
  int v50; // ecx
  __int64 v51; // rbx
  __int64 v52; // r15
  void *v53; // rax
  void *v54; // r13
  _DWORD *v55; // rax
  void *v56; // r12
  void *v57; // r13
  WCHAR *v58; // rbx
  PSID v59; // r12
  DWORD v60; // eax
  unsigned __int64 v61; // rdx
  WCHAR *InitialOffset; // rbx
  DWORD v63; // eax
  unsigned __int64 v64; // rdx
  PSID v65; // r15
  struct _BG_FILE_RANGE *v66; // rbx
  EVENT_LOG *v67; // rcx
  DWORD v68; // eax
  __int64 v69; // rax
  DWORD v70; // eax
  __int64 v71; // rax
  EVENT_LOG *v72; // rcx
  EVENT_LOG *v73; // rcx
  int v74; // eax
  DWORD cchName; // [rsp+40h] [rbp-9F8h] BYREF
  _BYTE v76[4]; // [rsp+44h] [rbp-9F4h] BYREF
  PSID v77; // [rsp+48h] [rbp-9F0h] BYREF
  __int64 TokenInformation; // [rsp+50h] [rbp-9E8h] BYREF
  char v79; // [rsp+58h] [rbp-9E0h]
  DWORD ReturnLength[2]; // [rsp+60h] [rbp-9D8h] BYREF
  unsigned int v81[2]; // [rsp+68h] [rbp-9D0h] BYREF
  void *v82; // [rsp+70h] [rbp-9C8h] BYREF
  struct _BG_FILE_RANGE *v83; // [rsp+78h] [rbp-9C0h] BYREF
  int v84; // [rsp+80h] [rbp-9B8h]
  PSID Sid; // [rsp+88h] [rbp-9B0h] BYREF
  void *v86; // [rsp+90h] [rbp-9A8h]
  struct _BG_FILE_RANGE *v87; // [rsp+98h] [rbp-9A0h] BYREF
  unsigned __int64 UserContextToken; // [rsp+A0h] [rbp-998h] BYREF
  PSID *p_Sid; // [rsp+A8h] [rbp-990h] BYREF
  volatile signed __int32 *v90; // [rsp+B0h] [rbp-988h]
  CFile *v91; // [rsp+B8h] [rbp-980h] BYREF
  volatile signed __int32 *v92; // [rsp+C0h] [rbp-978h] BYREF
  _BYTE v93[8]; // [rsp+C8h] [rbp-970h] BYREF
  char v94; // [rsp+D0h] [rbp-968h]
  void *v95; // [rsp+D8h] [rbp-960h]
  void *v96; // [rsp+E0h] [rbp-958h]
  void *v97; // [rsp+E8h] [rbp-950h]
  volatile signed __int32 *v98; // [rsp+F8h] [rbp-940h]
  struct IUnknown *v99; // [rsp+100h] [rbp-938h]
  __int64 v100; // [rsp+108h] [rbp-930h]
  void *v101; // [rsp+110h] [rbp-928h] BYREF
  void *v102; // [rsp+118h] [rbp-920h]
  __int64 v103; // [rsp+120h] [rbp-918h] BYREF
  char v104; // [rsp+128h] [rbp-910h]
  volatile signed __int32 *v105; // [rsp+130h] [rbp-908h] BYREF
  unsigned __int16 *v106; // [rsp+138h] [rbp-900h]
  unsigned __int16 *v107; // [rsp+140h] [rbp-8F8h]
  CJob *v108; // [rsp+150h] [rbp-8E8h]
  void *v109; // [rsp+158h] [rbp-8E0h]
  __int64 v110; // [rsp+160h] [rbp-8D8h]
  char v111; // [rsp+168h] [rbp-8D0h]
  void *v112; // [rsp+170h] [rbp-8C8h]
  volatile signed __int32 *v113; // [rsp+178h] [rbp-8C0h]
  void **pExceptionObject; // [rsp+190h] [rbp-8A8h] BYREF
  __int128 v115; // [rsp+198h] [rbp-8A0h]
  int v116; // [rsp+1A8h] [rbp-890h]
  int v117; // [rsp+1ACh] [rbp-88Ch]
  int v118; // [rsp+1B0h] [rbp-888h]
  void **v119; // [rsp+1F0h] [rbp-848h] BYREF
  __int128 v120; // [rsp+1F8h] [rbp-840h]
  int v121; // [rsp+208h] [rbp-830h]
  int v122; // [rsp+20Ch] [rbp-82Ch]
  int v123; // [rsp+210h] [rbp-828h]
  void **v124; // [rsp+250h] [rbp-7E8h] BYREF
  __int128 v125; // [rsp+258h] [rbp-7E0h]
  int v126; // [rsp+268h] [rbp-7D0h]
  int v127; // [rsp+26Ch] [rbp-7CCh]
  int v128; // [rsp+270h] [rbp-7C8h]
  void **v129; // [rsp+2B0h] [rbp-788h] BYREF
  __int128 v130; // [rsp+2B8h] [rbp-780h]
  int v131; // [rsp+2C8h] [rbp-770h]
  int v132; // [rsp+2CCh] [rbp-76Ch]
  int v133; // [rsp+2D0h] [rbp-768h]
  void **v134; // [rsp+310h] [rbp-728h] BYREF
  __int128 v135; // [rsp+318h] [rbp-720h]
  int v136; // [rsp+328h] [rbp-710h]
  int v137; // [rsp+32Ch] [rbp-70Ch]
  int v138; // [rsp+330h] [rbp-708h]
  void **v139; // [rsp+370h] [rbp-6C8h] BYREF
  __int128 v140; // [rsp+378h] [rbp-6C0h]
  int v141; // [rsp+388h] [rbp-6B0h]
  int v142; // [rsp+38Ch] [rbp-6ACh]
  int v143; // [rsp+390h] [rbp-6A8h]
  void **v144; // [rsp+3D0h] [rbp-668h] BYREF
  __int128 v145; // [rsp+3D8h] [rbp-660h]
  unsigned int v146; // [rsp+3E8h] [rbp-650h]
  int v147; // [rsp+3ECh] [rbp-64Ch]
  int v148; // [rsp+3F0h] [rbp-648h]
  void **v149; // [rsp+430h] [rbp-608h] BYREF
  __int128 v150; // [rsp+438h] [rbp-600h]
  int v151; // [rsp+448h] [rbp-5F0h]
  int v152; // [rsp+44Ch] [rbp-5ECh]
  int v153; // [rsp+450h] [rbp-5E8h]
  void **v154; // [rsp+490h] [rbp-5A8h] BYREF
  __int128 v155; // [rsp+498h] [rbp-5A0h]
  unsigned int v156; // [rsp+4A8h] [rbp-590h]
  int v157; // [rsp+4ACh] [rbp-58Ch]
  int v158; // [rsp+4B0h] [rbp-588h]
  void **v159; // [rsp+4F0h] [rbp-548h] BYREF
  __int128 v160; // [rsp+4F8h] [rbp-540h]
  int v161; // [rsp+508h] [rbp-530h]
  int v162; // [rsp+50Ch] [rbp-52Ch]
  int v163; // [rsp+510h] [rbp-528h]
  void **v164; // [rsp+550h] [rbp-4E8h] BYREF
  __int128 v165; // [rsp+558h] [rbp-4E0h]
  int v166; // [rsp+568h] [rbp-4D0h]
  int v167; // [rsp+56Ch] [rbp-4CCh]
  int v168; // [rsp+570h] [rbp-4C8h]
  void **v169; // [rsp+5B0h] [rbp-488h] BYREF
  __int128 v170; // [rsp+5B8h] [rbp-480h]
  int v171; // [rsp+5C8h] [rbp-470h]
  int v172; // [rsp+5CCh] [rbp-46Ch]
  int v173; // [rsp+5D0h] [rbp-468h]
  void **v174; // [rsp+610h] [rbp-428h] BYREF
  __int128 v175; // [rsp+618h] [rbp-420h]
  int v176; // [rsp+628h] [rbp-410h]
  int v177; // [rsp+62Ch] [rbp-40Ch]
  int v178; // [rsp+630h] [rbp-408h]
  void **v179; // [rsp+670h] [rbp-3C8h] BYREF
  __int128 v180; // [rsp+678h] [rbp-3C0h]
  int v181; // [rsp+688h] [rbp-3B0h]
  int v182; // [rsp+68Ch] [rbp-3ACh]
  int v183; // [rsp+690h] [rbp-3A8h]
  void **v184; // [rsp+6D0h] [rbp-368h] BYREF
  __int128 v185; // [rsp+6D8h] [rbp-360h]
  int v186; // [rsp+6E8h] [rbp-350h]
  int v187; // [rsp+6ECh] [rbp-34Ch]
  int v188; // [rsp+6F0h] [rbp-348h]
  void **v189; // [rsp+730h] [rbp-308h] BYREF
  __int128 v190; // [rsp+738h] [rbp-300h]
  int v191; // [rsp+748h] [rbp-2F0h]
  int v192; // [rsp+74Ch] [rbp-2ECh]
  int v193; // [rsp+750h] [rbp-2E8h]
  void **v194; // [rsp+790h] [rbp-2A8h] BYREF
  __int128 v195; // [rsp+798h] [rbp-2A0h]
  int v196; // [rsp+7A8h] [rbp-290h]
  int v197; // [rsp+7ACh] [rbp-28Ch]
  int v198; // [rsp+7B0h] [rbp-288h]
  struct _EVENT_DATA_DESCRIPTOR sz; // [rsp+7F0h] [rbp-248h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v200; // [rsp+800h] [rbp-238h] BYREF
  char *v201; // [rsp+810h] [rbp-228h]
  __int64 v202; // [rsp+818h] [rbp-220h]
  struct _EVENT_DATA_DESCRIPTOR v203; // [rsp+820h] [rbp-218h] BYREF
  __int64 *p_UserContextToken; // [rsp+830h] [rbp-208h]
  __int64 v205; // [rsp+838h] [rbp-200h]
  struct _EVENT_DATA_DESCRIPTOR v206; // [rsp+840h] [rbp-1F8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v207; // [rsp+850h] [rbp-1E8h] BYREF
  unsigned int *v208; // [rsp+860h] [rbp-1D8h]
  __int64 v209; // [rsp+868h] [rbp-1D0h]
  struct _BG_FILE_RANGE **v210; // [rsp+870h] [rbp-1C8h]
  __int64 v211; // [rsp+878h] [rbp-1C0h]

  v81[0] = a4;
  v107 = a3;
  v106 = a2;
  v108 = this;
  v83 = a5;
  v99 = a6;
  LODWORD(TokenInformation) = 0;
  if ( !a4 )
    return 0;
  if ( a4 == -1 )
  {
    if ( *((_DWORD *)this + 166) && (__int64)(*((_QWORD *)this + 107) - *((_QWORD *)this + 106)) >> 3 )
      return 2149580828LL;
  }
  else
  {
    if ( *((_BYTE *)this + 1296) )
      return 2149580913LL;
    if ( !a5 )
      return 2147942487LL;
    if ( *((_DWORD *)this + 166) )
      return 2147500033LL;
  }
  v91 = 0;
  v84 = (__int64)(*((_QWORD *)this + 107) - *((_QWORD *)this + 106)) >> 3;
  v79 = *((_BYTE *)this + 1297);
  if ( !a2 || !a3 )
  {
    v195 = 0;
    v194 = &ComError::`vftable';
    v196 = -2147024809;
    v197 = 1820;
    v198 = 1;
    throw (ComError *)&v194;
  }
  v11 = (PSID *)(*(__int64 (__fastcall **)(CJob *, __int64 *))(*(_QWORD *)this + 16LL))(this, &v103);
  LODWORD(TokenInformation) = 1;
  v12 = 0;
  if ( !EqualSid(*v11, *((PSID *)g_GlobalInfo + 11))
    && !EqualSid(*v11, *((PSID *)g_GlobalInfo + 17))
    && !EqualSid(*v11, *((PSID *)g_GlobalInfo + 19)) )
  {
    p_Sid = (PSID *)*((_QWORD *)g_GlobalInfo + 7);
    v90 = (volatile signed __int32 *)*((_QWORD *)g_GlobalInfo + 8);
    _InterlockedIncrement(v90);
    if ( (unsigned int)CheckClientGroupMembership((SidHandle *)&p_Sid) )
    {
      if ( *((_BYTE *)g_Manager + 1496) )
        v12 = 1;
    }
  }
  SidHandle::~SidHandle((SidHandle *)&v103);
  if ( v12 )
  {
    v13 = *((_DWORD *)g_Manager + 377);
    v14 = ((__int64)(*((_QWORD *)this + 107) - *((_QWORD *)this + 106)) >> 3) + 1;
    if ( v13 < v14 )
    {
      memset_0(&sz, 0, 0x1FEu);
      if ( !StringFromGUID2((const GUID *const)((char *)this + 676), (LPOLESTR)&sz, 39) )
        StringCchCopyW((unsigned __int16 *)&sz, 0xFFu, (const unsigned __int16 *)(*((_QWORD *)this + 87) + 12LL));
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          (unsigned int)&WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
          (unsigned int)&sz,
          v14,
          v13);
      EVENT_LOG::ReportObjectLimitExceededFailure(
        g_EventLogger,
        &EVT_EXCEEDED_FILELIMIT_PER_JOB,
        (const unsigned __int16 *)&sz,
        v14,
        v13);
      v115 = 0;
      pExceptionObject = &ComError::`vftable';
      v116 = -2145386415;
      v117 = 1320;
      v118 = 1;
      throw (ComError *)&pExceptionObject;
    }
  }
  v15 = a2;
  if ( *((_DWORD *)this + 166) )
    v15 = a3;
  v16 = (PSID *)(*(__int64 (__fastcall **)(CJob *, __int64 *))(*(_QWORD *)this + 16LL))(this, &v103);
  LODWORD(TokenInformation) = 2;
  v17 = 0;
  if ( !EqualSid(*v16, *((PSID *)g_GlobalInfo + 11))
    && !EqualSid(*v16, *((PSID *)g_GlobalInfo + 17))
    && !EqualSid(*v16, *((PSID *)g_GlobalInfo + 19)) )
  {
    p_Sid = (PSID *)*((_QWORD *)g_GlobalInfo + 7);
    v90 = (volatile signed __int32 *)*((_QWORD *)g_GlobalInfo + 8);
    _InterlockedIncrement(v90);
    if ( (unsigned int)CheckClientGroupMembership((SidHandle *)&p_Sid) )
    {
      if ( *((_BYTE *)g_Manager + 1496) )
        v17 = 1;
    }
  }
  SidHandle::~SidHandle((SidHandle *)&v103);
  if ( v17 )
  {
    v20 = *((_DWORD *)g_Manager + 378);
    if ( v20 < a4 && a4 != -1 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          (unsigned int)&WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
          (_DWORD)v15,
          a4,
          *((_DWORD *)g_Manager + 378));
      EVENT_LOG::ReportObjectLimitExceededFailure(g_EventLogger, &EVT_EXCEEDED_RANGELIMIT_PER_FILE, v15, a4, v20);
      v120 = 0;
      v119 = &ComError::`vftable';
      v121 = -2145386414;
      v122 = 1347;
      v123 = 1;
      throw (ComError *)&v119;
    }
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_qSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, (_DWORD)this, (__int64)a2, (__int64)a3, a4);
  if ( (unsigned int)(*((_DWORD *)this + 165) - 7) <= 1 )
  {
    v190 = 0;
    v189 = &ComError::`vftable';
    v191 = -2145386494;
    v192 = 1832;
    v193 = 1;
    throw (ComError *)&v189;
  }
  v100 = *((_QWORD *)g_Manager + 83);
  v110 = v100;
  v111 = 0;
  v76[0] = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v100 + 24LL))(v100, v76);
  if ( v21 < 0 )
  {
    v125 = 0;
    v124 = &ComError::`vftable';
    v126 = v21;
    v127 = 16;
    v128 = 1;
    throw (ComError *)&v124;
  }
  if ( !v76[0] )
    v111 = 1;
  v22 = *((_QWORD *)g_Manager + 83);
  v103 = v22;
  v104 = 0;
  v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 40LL))(v22);
  if ( v23 < 0 )
  {
    v130 = 0;
    v129 = &ComError::`vftable';
    v131 = v23;
    v132 = 15;
    v133 = 1;
    throw (ComError *)&v129;
  }
  cchName = 0;
  _InterlockedIncrement(&dword_180145058);
  v24 = (volatile signed __int32 *)&GenericStringHandle<unsigned short>::s_EmptyString;
  v105 = (volatile signed __int32 *)&GenericStringHandle<unsigned short>::s_EmptyString;
  v87 = 0;
  if ( *(_QWORD *)g_EventLogger && (unsigned __int8)EtwEventEnabled(*(_QWORD *)g_EventLogger, &EVT_JOB_ADDFILE) )
  {
    CJobManager::TryGetCallingProcessInformation(&v105, &cchName, &v87);
    v24 = v105;
  }
  CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)v93);
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 191) + 8LL));
  v82 = (void *)*((_QWORD *)this + 191);
  v109 = &v82;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids);
  v25 = HeapAlloc(hBitsHeap, 8u, 0x10u);
  if ( !v25 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
    v135 = 0;
    v134 = &ComError::`vftable';
    v136 = -2147024882;
    v137 = 0;
    v138 = 1;
    throw (ComError *)&v134;
  }
  v77 = v25;
  v25[2] = 1;
  *(_QWORD *)v77 = 0;
  v26 = CopyTokenSid(*(HANDLE *)v95);
  v112 = v26;
  v27 = (volatile signed __int32 *)HeapAlloc(hBitsHeap, 8u, 4u);
  v28 = v27;
  if ( !v27 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 4);
    v140 = 0;
    v139 = &ComError::`vftable';
    v141 = -2147024882;
    v142 = 0;
    v143 = 1;
    throw (ComError *)&v139;
  }
  *v27 = 1;
  v113 = v27;
  GetPackageInfoFromToken(&Sid, *(_QWORD *)v95);
  ReturnLength[0] = 0;
  LODWORD(TokenInformation) = 0;
  if ( !GetTokenInformation(*(HANDLE *)v95, TokenElevation, &TokenInformation, 4u, ReturnLength) )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v145 = 0;
    v144 = &ComError::`vftable';
    v146 = LastError;
    v147 = 437;
    v148 = 1;
    throw (ComError *)&v144;
  }
  TokenIntegrityLevel = GetTokenIntegrityLevel(*(void **)v95);
  UserContextToken = QueryUserContextToken(*(void **)v95);
  _InterlockedIncrement((volatile signed __int32 *)v82 + 2);
  *(_QWORD *)ReturnLength = v82;
  CNestedImpersonation::UpdateServiceName(v93, ReturnLength);
  _InterlockedIncrement(v98 + 2);
  v92 = v98;
  v31 = (AppPackageInfo *)Sid;
  v101 = v26;
  v102 = (void *)v28;
  _InterlockedIncrement(v28);
  v32 = CJobManager::CloneUserToken(
          (__int64)g_Manager,
          (SidHandle *)&v101,
          v31,
          TokenInformation,
          TokenIntegrityLevel,
          (__int64 *)&UserContextToken,
          (void **)&v92,
          (TokenHandle *)&v77);
  if ( v32 < 0 )
  {
    v150 = 0;
    v149 = &ComError::`vftable';
    v151 = v32;
    v152 = 452;
    v153 = 1;
    throw (ComError *)&v149;
  }
  v33 = (HANDLE *)v95;
  if ( *(_QWORD *)v95 != *(_QWORD *)v77 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v95 + 2, 0xFFFFFFFF) == 1 )
    {
      v34 = v95;
      if ( (unsigned __int64)(*(_QWORD *)v95 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v95);
        *(_QWORD *)v95 = 0;
        v34 = v95;
      }
      operator delete(v34, 0x10u);
    }
    v95 = v77;
    _InterlockedIncrement((volatile signed __int32 *)v77 + 2);
    v33 = (HANDLE *)v95;
  }
  v94 = 0;
  if ( !ImpersonateLoggedOnUser(*v33) )
  {
    v36 = GetLastError();
    v37 = v36;
    if ( v36 > 0 )
      v37 = (unsigned __int16)v36 | 0x80070000;
    v155 = 0;
    v154 = &ComError::`vftable';
    v156 = v37;
    v157 = 0;
    v158 = 1;
    throw (ComError *)&v154;
  }
  v94 = 1;
  if ( Sid )
    std::default_delete<AppPackageInfo>::operator()(v35, Sid);
  if ( _InterlockedExchangeAdd(v28, 0xFFFFFFFF) == 1 )
  {
    operator delete((void *)v28, 4u);
    operator delete(v26, 0);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v77 + 2, 0xFFFFFFFF) == 1 )
  {
    v38 = v77;
    if ( (unsigned __int64)(*(_QWORD *)v77 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v77);
      *(_QWORD *)v77 = 0;
      v38 = v77;
    }
    operator delete(v38, 0x10u);
    v77 = 0;
  }
  if ( v82 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v82 + 2, 0xFFFFFFFF) == 1 )
      operator delete(v82, 0x10u);
    v82 = 0;
  }
  v39 = 0;
  *(_QWORD *)ReturnLength = 0;
  if ( (*((_BYTE *)this + 1232) & 1) != 0 )
  {
    if ( !**((_QWORD **)this + 155) )
    {
      v160 = 0;
      v159 = &ComError::`vftable';
      v161 = -2145386410;
      v162 = 1862;
      v163 = 1;
      throw (ComError *)&v159;
    }
    CNestedImpersonation::Impersonate((CNestedImpersonation *)v93, (CJob *)((char *)this + 1240));
  }
  v40 = v81[0];
  if ( v81[0] != -1 )
  {
    v41 = (CRangeCollection *)operator new(0x38u);
    p_Sid = (PSID *)v41;
    if ( v41 )
      v41 = CRangeCollection::CRangeCollection(v41, v40, v83, 0, 0xFFFFFFFFFFFFFFFFuLL);
    *(_QWORD *)v81 = v41;
    std::unique_ptr<CRangeCollection>::operator=<std::default_delete<CRangeCollection>,0>(ReturnLength, v81);
    std::unique_ptr<CRangeCollection>::~unique_ptr<CRangeCollection>(v81);
    v39 = *(struct CRangeCollection **)ReturnLength;
    LogRangeCollection(*(struct CRangeCollection **)ReturnLength);
    for ( i = 0; i < *((_DWORD *)v39 + 8); ++i )
    {
      v43 = *((_QWORD *)v39 + 5);
      v44 = *(_QWORD *)(v43 + 16LL * i + 8);
      if ( v44 != -1 && ~*(_QWORD *)(v43 + 16LL * i) < v44 )
      {
        v165 = 0;
        v164 = &ComError::`vftable';
        v166 = -2145386453;
        v167 = 1876;
        v168 = 1;
        throw (ComError *)&v164;
      }
    }
    if ( CRangeCollection::IsOverlapping(v39) )
    {
      v170 = 0;
      v169 = &ComError::`vftable';
      v171 = -2145386452;
      v172 = 1881;
      v173 = 1;
      throw (ComError *)&v169;
    }
    *((_BYTE *)this + 1297) = 1;
  }
  v45 = (CFile *)HeapAlloc(hBitsHeap, 8u, 0x1A0u);
  v46 = v45;
  if ( !v45 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 416);
    v175 = 0;
    v174 = &ComError::`vftable';
    v176 = -2147024882;
    v177 = 0;
    v178 = 1;
    throw (ComError *)&v174;
  }
  p_Sid = (PSID *)v45;
  v109 = v81;
  *(_QWORD *)ReturnLength = 0;
  *(_QWORD *)v81 = v39;
  UserContextToken = (unsigned __int64)&TokenInformation;
  TokenInformation = GenericStringHandle<unsigned short>::NewString(v107);
  v83 = (struct _BG_FILE_RANGE *)GenericStringHandle<unsigned short>::NewString(v106);
  v47 = CFile::CFile(
          v46,
          this,
          (enum BG_JOB_TYPE)*((_DWORD *)this + 166),
          (void **)&v83,
          (void **)&TokenInformation,
          (CRangeCollection **)v81,
          (__int64)v99);
  v91 = v47;
  v48 = (CFile **)*((_QWORD *)this + 107);
  if ( v48 == *((CFile ***)this + 108) )
  {
    std::vector<ServiceAccountUserSession *>::_Emplace_reallocate<ServiceAccountUserSession * const &>(
      (char *)this + 848,
      v48,
      &v91);
  }
  else
  {
    *v48 = v47;
    *((_QWORD *)this + 107) += 8LL;
  }
  v91 = 0;
  if ( *((_DWORD *)this + 166) == 2 )
    CUploadJob::GenerateReplyFile(this, 0);
  v49 = CJob::HandleAddFile(this);
  if ( v49 < 0 )
  {
    v180 = 0;
    v179 = &ComError::`vftable';
    v181 = v49;
    v182 = 1906;
    v183 = 1;
    throw (ComError *)&v179;
  }
  v50 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 48LL))(v22);
  if ( v50 < 0 )
  {
    v185 = 0;
    v184 = &ComError::`vftable';
    v186 = v50;
    v187 = 20;
    v188 = 1;
    throw (ComError *)&v184;
  }
  v104 = 1;
  v51 = *((_QWORD *)this + 107);
  v52 = *((_QWORD *)this + 106);
  p_Sid = &Sid;
  Sid = (PSID)*((_QWORD *)this + 89);
  v86 = (void *)*((_QWORD *)this + 90);
  _InterlockedIncrement((volatile signed __int32 *)v86);
  v99 = (struct IUnknown *)*((_QWORD *)this + 87);
  v53 = v96;
  v77 = v96;
  if ( !v96 )
  {
    v54 = CopyTokenSid(*(HANDLE *)v95);
    v55 = operator new(4u);
    v56 = v55;
    if ( v55 )
      *v55 = 1;
    else
      v56 = 0;
    if ( v96 != v54 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v97, 0xFFFFFFFF) == 1 )
      {
        operator delete(v97, 4u);
        operator delete(v96, 0);
      }
      v96 = v54;
      v97 = v56;
      _InterlockedIncrement((volatile signed __int32 *)v56);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v56, 0xFFFFFFFF) == 1 )
    {
      operator delete(v56, 4u);
      operator delete(v54, 0);
    }
    v53 = v96;
    v77 = v96;
  }
  v101 = v53;
  v57 = v97;
  v102 = v97;
  _InterlockedIncrement((volatile signed __int32 *)v97);
  v83 = v87;
  v81[0] = cchName;
  UserContextToken = (v51 - v52) >> 3;
  v87 = (struct _BG_FILE_RANGE *)g_EventLogger;
  if ( !*(_QWORD *)g_EventLogger )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids);
    goto LABEL_184;
  }
  v58 = (WCHAR *)*((_QWORD *)g_EventLogger + 1);
  v59 = Sid;
  cchName = 0;
  LODWORD(TokenInformation) = 0;
  ReturnLength[0] = 0;
  *v58 = 0;
  LookupAccountSidLocalW(v59, 0, &cchName, 0, (LPDWORD)&TokenInformation, (PSID_NAME_USE)ReturnLength);
  v60 = GetLastError();
  if ( v60 == 1332 )
  {
    EVENT_LOG::GetUnknownUserName(v58, v61);
  }
  else if ( v60 == 122 )
  {
    if ( (unsigned int)TokenInformation + cchName <= 0xC8 )
    {
      cchName = 200 - TokenInformation;
      if ( LookupAccountSidLocalW(
             v59,
             &v58[(unsigned int)TokenInformation],
             &cchName,
             v58,
             (LPDWORD)&TokenInformation,
             (PSID_NAME_USE)ReturnLength) )
      {
        v69 = -1;
        do
          ++v69;
        while ( v58[v69] );
        v58[v69] = 92;
      }
      else
      {
        v68 = GetLastError();
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids, v68);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids, v60);
  }
  InitialOffset = (WCHAR *)v87[1].InitialOffset;
  cchName = 0;
  LODWORD(TokenInformation) = 0;
  ReturnLength[0] = 0;
  *InitialOffset = 0;
  LookupAccountSidLocalW(v77, 0, &cchName, 0, (LPDWORD)&TokenInformation, (PSID_NAME_USE)ReturnLength);
  v63 = GetLastError();
  if ( v63 == 1332 )
  {
    EVENT_LOG::GetUnknownUserName(InitialOffset, v64);
  }
  else if ( v63 == 122 )
  {
    if ( (unsigned int)TokenInformation + cchName <= 0xC8 )
    {
      cchName = 200 - TokenInformation;
      v65 = v77;
      if ( LookupAccountSidLocalW(
             v77,
             &InitialOffset[(unsigned int)TokenInformation],
             &cchName,
             InitialOffset,
             (LPDWORD)&TokenInformation,
             (PSID_NAME_USE)ReturnLength) )
      {
        v71 = -1;
        do
          ++v71;
        while ( InitialOffset[v71] );
        InitialOffset[v71] = 92;
      }
      else
      {
        v70 = GetLastError();
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids, v70);
      }
      goto LABEL_151;
    }
  }
  else if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids, v63);
  }
  v65 = v77;
LABEL_151:
  v66 = v87;
  if ( !(unsigned __int8)EtwEventEnabled(v87->InitialOffset, &EVT_JOB_ADDFILE) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v57, 0xFFFFFFFF) == 1 )
    {
      operator delete(v57, 4u);
      operator delete(v65, 0);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v86, 0xFFFFFFFF) == 1 )
    {
      operator delete(v86, 4u);
      operator delete(Sid, 0);
    }
    goto LABEL_185;
  }
  EVENT_LOG::EventDataDescCreate_UnicodeString(v67, &sz, (const unsigned __int16 *)v66[1].InitialOffset);
  EVENT_LOG::EventDataDescCreate_UnicodeString(v72, &v200, (const unsigned __int16 *)&v99[1].lpVtbl + 2);
  v201 = (char *)this + 676;
  v202 = 16;
  EVENT_LOG::EventDataDescCreate_UnicodeString(
    (CJob *)((char *)this + 676),
    &v203,
    (const unsigned __int16 *)v66->Length);
  p_UserContextToken = (__int64 *)&UserContextToken;
  v205 = 8;
  EVENT_LOG::EventDataDescCreate_UnicodeString((EVENT_LOG *)&UserContextToken, &v206, v106);
  EVENT_LOG::EventDataDescCreate_UnicodeString(v73, &v207, v107);
  v208 = v81;
  v209 = 4;
  v210 = &v83;
  v211 = 8;
  v74 = EtwEventWrite(v66->InitialOffset, &EVT_JOB_ADDFILE, 9, &sz);
  if ( v74 && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids, 16403, v74);
LABEL_184:
  SidHandle::~SidHandle((SidHandle *)&v101);
  SidHandle::~SidHandle((SidHandle *)&Sid);
LABEL_185:
  CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)v93);
  if ( v24 && _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
    operator delete((void *)v24, 0x10u);
  if ( v111 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 32LL))(v100);
  return 0;
}

```

## disassembly

```asm
0x180016ee0  push    rbx
0x180016ee2  push    rsi
0x180016ee3  push    rdi
0x180016ee4  push    r12
0x180016ee6  push    r13
0x180016ee8  push    r14
0x180016eea  push    r15
0x180016eec  sub     rsp, 0A00h
0x180016ef3  mov     rax, cs:__security_cookie
0x180016efa  xor     rax, rsp
0x180016efd  mov     [rsp+0A38h+var_48], rax
0x180016f05  mov     esi, r9d
0x180016f08  mov     [rsp+0A38h+var_9D0], r9d
0x180016f0d  mov     r13, r8
0x180016f10  mov     [rsp+0A38h+var_8F8], r8
0x180016f18  mov     r15, rdx
0x180016f1b  mov     [rsp+0A38h+var_900], rdx
0x180016f23  mov     r14, rcx
0x180016f26  mov     [rsp+0A38h+var_8E8], rcx
0x180016f2e  mov     rcx, [rsp+0A38h+arg_20]
0x180016f36  mov     [rsp+0A38h+var_9C0], rcx
0x180016f3b  mov     rax, [rsp+0A38h+arg_28]
0x180016f43  mov     [rsp+0A38h+var_938], rax
0x180016f4b  xor     edx, edx
0x180016f4d  mov     dword ptr [rsp+0A38h+TokenInformation], edx
0x180016f51  test    r9d, r9d
0x180016f54  jnz     short loc_180016F5D
0x180016f56  xor     eax, eax
0x180016f58  jmp     loc_1800185CE
0x180016f5d  cmp     esi, 0FFFFFFFFh
0x180016f60  jz      short loc_180016F97
0x180016f62  cmp     [r14+510h], dl
0x180016f69  jz      short loc_180016F75
0x180016f6b  mov     eax, 80200071h
0x180016f70  jmp     loc_1800185CE
0x180016f75  test    rcx, rcx
0x180016f78  jnz     short loc_180016F84
0x180016f7a  mov     eax, 80070057h
0x180016f7f  jmp     loc_1800185CE
0x180016f84  cmp     [r14+298h], edx
0x180016f8b  jz      short loc_180016FC1
0x180016f8d  mov     eax, 80004001h
0x180016f92  jmp     loc_1800185CE
0x180016f97  cmp     [r14+298h], edx
0x180016f9e  jz      short loc_180016FC1
0x180016fa0  mov     rax, [r14+358h]
0x180016fa7  sub     rax, [r14+350h]
0x180016fae  sar     rax, 3
0x180016fb2  test    rax, rax
0x180016fb5  jz      short loc_180016FC1
0x180016fb7  mov     eax, 8020001Ch
0x180016fbc  jmp     loc_1800185CE
0x180016fc1  mov     [rsp+0A38h+var_980], rdx
0x180016fc9  lea     r12, [r14+350h]
0x180016fd0  mov     rax, [r12+8]
0x180016fd5  sub     rax, [r12]
0x180016fd9  sar     rax, 3
0x180016fdd  mov     [rsp+0A38h+var_9B8], eax
0x180016fe4  movzx   eax, byte ptr [r14+511h]
0x180016fec  mov     [rsp+0A38h+var_9E0], al
0x180016ff0  test    r15, r15
0x180016ff3  jz      loc_18001857A
0x180016ff9  test    r13, r13
0x180016ffc  jz      loc_18001857A
0x180017002  mov     rax, [r14]
0x180017005  lea     rdx, [rsp+0A38h+var_918]
0x18001700d  mov     rcx, r14
0x180017010  mov     rax, [rax+10h]
0x180017014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017019  mov     rbx, rax
0x18001701c  mov     dword ptr [rsp+0A38h+TokenInformation], 1
0x180017024  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x18001702b  mov     rdx, [rdx+58h]; pSid2
0x18001702f  mov     rcx, [rax]; pSid1
0x180017032  call    cs:__imp_EqualSid
0x180017038  test    eax, eax
0x18001703a  jnz     short loc_1800170B9
0x18001703c  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180017043  mov     rdx, [rdx+88h]; pSid2
0x18001704a  mov     rcx, [rbx]; pSid1
0x18001704d  call    cs:__imp_EqualSid
0x180017053  test    eax, eax
0x180017055  jnz     short loc_1800170B9
0x180017057  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x18001705e  mov     rdx, [rdx+98h]; pSid2
0x180017065  mov     rcx, [rbx]; pSid1
0x180017068  call    cs:__imp_EqualSid
0x18001706e  test    eax, eax
0x180017070  jnz     short loc_1800170B9
0x180017072  mov     rcx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180017079  mov     rax, [rcx+38h]
0x18001707d  mov     [rsp+0A38h+var_990], rax
0x180017085  mov     rax, [rcx+40h]
0x180017089  mov     [rsp+0A38h+var_988], rax
0x180017091  lock inc dword ptr [rax]
0x180017094  lea     rcx, [rsp+0A38h+var_990]
0x18001709c  call    ?CheckClientGroupMembership@@YAJVSidHandle@@@Z; CheckClientGroupMembership(SidHandle)
0x1800170a1  test    eax, eax
0x1800170a3  jz      short loc_1800170B9
0x1800170a5  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x1800170ac  cmp     byte ptr [rax+5D8h], 0
0x1800170b3  jz      short loc_1800170B9
0x1800170b5  mov     bl, 1
0x1800170b7  jmp     short loc_1800170BB
0x1800170b9  xor     bl, bl
0x1800170bb  lea     rcx, [rsp+0A38h+var_918]; this
0x1800170c3  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x1800170c8  test    bl, bl
0x1800170ca  jz      loc_1800171F4
0x1800170d0  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x1800170d7  mov     ebx, [rax+5E4h]
0x1800170dd  mov     rdi, [r12+8]
0x1800170e2  sub     rdi, [r12]
0x1800170e6  sar     rdi, 3
0x1800170ea  inc     edi
0x1800170ec  cmp     ebx, edi
0x1800170ee  jnb     loc_1800171F4
0x1800170f4  xor     edx, edx; Val
0x1800170f6  mov     r8d, 1FEh; Size
0x1800170fc  lea     rcx, [rsp+0A38h+sz]; void *
0x180017104  call    memset_0
0x180017109  lea     rcx, [r14+2A4h]; rguid
0x180017110  mov     r8d, 27h ; '''; cchMax
0x180017116  lea     rdx, [rsp+0A38h+sz]; lpsz
0x18001711e  call    cs:__imp_StringFromGUID2
0x180017124  test    eax, eax
0x180017126  jnz     short loc_180017145
0x180017128  mov     r8, [r14+2B8h]
0x18001712f  add     r8, 0Ch; unsigned __int16 *
0x180017133  mov     edx, 0FFh; unsigned __int64
0x180017138  lea     rcx, [rsp+0A38h+sz]; unsigned __int16 *
0x180017140  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017145  lea     rax, WPP_GLOBAL_Control
0x18001714c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017153  cmp     rcx, rax
0x180017156  jz      short loc_180017183
0x180017158  test    byte ptr [rcx+1Ch], 4
0x18001715c  jz      short loc_180017183
0x18001715e  mov     edx, 42h ; 'B'
0x180017163  mov     dword ptr [rsp+0A38h+peUse], ebx
0x180017167  mov     dword ptr [rsp+0A38h+ReturnLength], edi
0x18001716b  lea     r9, [rsp+0A38h+sz]
0x180017173  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18001717a  mov     rcx, [rcx+10h]
0x18001717e  call    WPP_SF_Sdd
0x180017183  mov     dword ptr [rsp+0A38h+ReturnLength], ebx; unsigned int
0x180017187  mov     r9d, edi; unsigned int
0x18001718a  lea     r8, [rsp+0A38h+sz]; unsigned __int16 *
0x180017192  lea     rdx, EVT_EXCEEDED_FILELIMIT_PER_JOB; struct _EVENT_DESCRIPTOR *
0x180017199  mov     rcx, cs:?g_EventLogger@@3PEAVEVENT_LOG@@EA; this
0x1800171a0  call    ?ReportObjectLimitExceededFailure@EVENT_LOG@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKK@Z; EVENT_LOG::ReportObjectLimitExceededFailure(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ulong)
0x1800171a5  xorps   xmm0, xmm0
0x1800171a8  movups  [rsp+0A38h+var_8A0], xmm0
0x1800171b0  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800171b7  mov     [rsp+0A38h+pExceptionObject], rax
0x1800171bf  mov     [rsp+0A38h+var_890], 80200051h
0x1800171ca  mov     [rsp+0A38h+var_88C], 528h
0x1800171d5  mov     [rsp+0A38h+var_888], 1
0x1800171e0  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800171e7  lea     rcx, [rsp+0A38h+pExceptionObject]; pExceptionObject
0x1800171ef  call    _CxxThrowException_0
0x1800171f4  mov     rdi, r15
0x1800171f7  cmp     dword ptr [r14+298h], 0
0x1800171ff  cmovnz  rdi, r13
0x180017203  mov     rax, [r14]
0x180017206  lea     rdx, [rsp+0A38h+var_918]
0x18001720e  mov     rcx, r14
0x180017211  mov     rax, [rax+10h]
0x180017215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001721a  mov     rbx, rax
0x18001721d  mov     dword ptr [rsp+0A38h+TokenInformation], 2
0x180017225  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x18001722c  mov     rdx, [rdx+58h]; pSid2
0x180017230  mov     rcx, [rax]; pSid1
0x180017233  call    cs:__imp_EqualSid
0x180017239  test    eax, eax
0x18001723b  jnz     short loc_1800172BA
0x18001723d  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180017244  mov     rdx, [rdx+88h]; pSid2
0x18001724b  mov     rcx, [rbx]; pSid1
0x18001724e  call    cs:__imp_EqualSid
0x180017254  test    eax, eax
0x180017256  jnz     short loc_1800172BA
0x180017258  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x18001725f  mov     rdx, [rdx+98h]; pSid2
0x180017266  mov     rcx, [rbx]; pSid1
0x180017269  call    cs:__imp_EqualSid
0x18001726f  test    eax, eax
0x180017271  jnz     short loc_1800172BA
0x180017273  mov     rcx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x18001727a  mov     rax, [rcx+38h]
0x18001727e  mov     [rsp+0A38h+var_990], rax
0x180017286  mov     rax, [rcx+40h]
0x18001728a  mov     [rsp+0A38h+var_988], rax
0x180017292  lock inc dword ptr [rax]
0x180017295  lea     rcx, [rsp+0A38h+var_990]
0x18001729d  call    ?CheckClientGroupMembership@@YAJVSidHandle@@@Z; CheckClientGroupMembership(SidHandle)
0x1800172a2  test    eax, eax
0x1800172a4  jz      short loc_1800172BA
0x1800172a6  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x1800172ad  cmp     byte ptr [rax+5D8h], 0
0x1800172b4  jz      short loc_1800172BA
0x1800172b6  mov     bl, 1
0x1800172b8  jmp     short loc_1800172BC
0x1800172ba  xor     bl, bl
0x1800172bc  lea     rcx, [rsp+0A38h+var_918]; this
0x1800172c4  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x1800172c9  test    bl, bl
0x1800172cb  jz      loc_180017394
0x1800172d1  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x1800172d8  mov     ebx, [rax+5E8h]
0x1800172de  cmp     ebx, esi
0x1800172e0  jnb     loc_180017394
0x1800172e6  cmp     esi, 0FFFFFFFFh
0x1800172e9  jz      loc_180017394
0x1800172ef  lea     rax, WPP_GLOBAL_Control
0x1800172f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800172fd  cmp     rcx, rax
0x180017300  jz      short loc_180017328
0x180017302  test    byte ptr [rcx+1Ch], 4
0x180017306  jz      short loc_180017328
0x180017308  mov     edx, 43h ; 'C'
0x18001730d  mov     dword ptr [rsp+0A38h+peUse], ebx
0x180017311  mov     dword ptr [rsp+0A38h+ReturnLength], esi
0x180017315  mov     r9, rdi
0x180017318  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18001731f  mov     rcx, [rcx+10h]
0x180017323  call    WPP_SF_Sdd
0x180017328  mov     dword ptr [rsp+0A38h+ReturnLength], ebx; unsigned int
0x18001732c  mov     r9d, esi; unsigned int
0x18001732f  mov     r8, rdi; unsigned __int16 *
0x180017332  lea     rdx, EVT_EXCEEDED_RANGELIMIT_PER_FILE; struct _EVENT_DESCRIPTOR *
0x180017339  mov     rcx, cs:?g_EventLogger@@3PEAVEVENT_LOG@@EA; this
0x180017340  call    ?ReportObjectLimitExceededFailure@EVENT_LOG@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKK@Z; EVENT_LOG::ReportObjectLimitExceededFailure(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ulong)
0x180017345  xorps   xmm0, xmm0
0x180017348  movups  [rsp+0A38h+var_840], xmm0
0x180017350  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180017357  mov     [rsp+0A38h+var_848], rax
0x18001735f  mov     [rsp+0A38h+var_830], 80200052h
0x18001736a  mov     [rsp+0A38h+var_82C], 543h
0x180017375  mov     [rsp+0A38h+var_828], 1
0x180017380  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180017387  lea     rcx, [rsp+0A38h+var_848]; pExceptionObject
0x18001738f  call    _CxxThrowException_0
0x180017394  lea     rbx, WPP_GLOBAL_Control
0x18001739b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173a2  cmp     rcx, rbx
0x1800173a5  jz      short loc_1800173C7
0x1800173a7  test    byte ptr [rcx+1Ch], 1
0x1800173ab  jz      short loc_1800173C7
0x1800173ad  mov     dword ptr [rsp+0A38h+var_A08], esi
0x1800173b1  mov     [rsp+0A38h+peUse], r13
0x1800173b6  mov     [rsp+0A38h+ReturnLength], r15
0x1800173bb  mov     r9, r14
0x1800173be  mov     rcx, [rcx+10h]
0x1800173c2  call    WPP_SF_qSSd
0x1800173c7  mov     eax, [r14+294h]
0x1800173ce  sub     eax, 7
0x1800173d1  cmp     eax, 1
0x1800173d4  jbe     loc_18001852B
0x1800173da  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x1800173e1  mov     rcx, [rax+298h]
0x1800173e8  mov     [rsp+0A38h+var_930], rcx
0x1800173f0  mov     [rsp+0A38h+var_8D8], rcx
0x1800173f8  mov     [rsp+0A38h+var_8D0], 0
0x180017400  mov     [rsp+0A38h+var_9F4], 0
0x180017405  mov     rax, [rcx]
0x180017408  lea     rdx, [rsp+0A38h+var_9F4]
0x18001740d  mov     rax, [rax+18h]
0x180017411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017416  mov     ecx, eax
0x180017418  test    eax, eax
0x18001741a  jns     short loc_180017467
0x18001741c  xorps   xmm0, xmm0
0x18001741f  movups  [rsp+0A38h+var_7E0], xmm0
0x180017427  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18001742e  mov     [rsp+0A38h+var_7E8], rax
0x180017436  mov     [rsp+0A38h+var_7D0], ecx
0x18001743d  mov     [rsp+0A38h+var_7CC], 10h
0x180017448  mov     [rsp+0A38h+var_7C8], 1
0x180017453  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001745a  lea     rcx, [rsp+0A38h+var_7E8]; pExceptionObject
0x180017462  call    _CxxThrowException_0
0x180017467  cmp     [rsp+0A38h+var_9F4], 0
0x18001746c  jnz     short loc_180017476
0x18001746e  mov     [rsp+0A38h+var_8D0], 1
0x180017476  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18001747d  mov     r13, [rax+298h]
0x180017484  mov     [rsp+0A38h+var_918], r13
0x18001748c  mov     [rsp+0A38h+var_910], 0
0x180017494  mov     rax, [r13+0]
0x180017498  mov     rcx, r13
0x18001749b  mov     rax, [rax+28h]
0x18001749f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174a4  mov     ecx, eax
0x1800174a6  test    eax, eax
0x1800174a8  jns     short loc_1800174F6
0x1800174aa  xorps   xmm0, xmm0
0x1800174ad  movups  [rsp+0A38h+var_780], xmm0
0x1800174b5  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
  ... truncated ...
```
