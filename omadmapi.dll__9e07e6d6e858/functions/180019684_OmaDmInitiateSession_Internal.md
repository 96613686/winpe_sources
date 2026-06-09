# OmaDmInitiateSession_Internal

- ea: `0x180019684`
- end: `0x18001a3e5`
- name: `OmaDmInitiateSession_Internal`
- size: `3425`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned int, __int64, unsigned int, int, __int64, unsigned int, int, int)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180019410`
- `0x180019570`

## callees

- `0x1800031b0`
- `0x180003da0`
- `0x180003db8`
- `0x180007b38`
- `0x18000b67c`
- `0x18000c920`
- `0x18000e0f0`
- `0x18000f47c`
- `0x180014570`
- `0x18001473c`
- `0x180014b20`
- `0x180015bb0`
- `0x180017600`
- `0x180017660`
- `0x180019684`
- `0x18001b0d0`
- `0x18001e844`
- `0x18001f444`
- `0x18001f690`
- `0x18001fa38`
- `0x180020268`
- `0x180021108`
- `0x180021688`
- `0x1800216f4`
- `0x180021a20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180019a72`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180019a72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019b47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019b47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019b33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019b33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800197a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800197b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800197c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800197dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800197ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019802`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019815`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019828`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001983b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001984e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019861`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019874`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019887`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001989a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800198ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800198c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800198d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800198e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800198f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001990c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001991f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001996b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001997f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019993`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800199a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800199cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800199de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019a1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019b57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019b66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019b76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800197a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800197b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800197c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800197dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800197ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019802`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019815`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019828`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001983b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001984e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019861`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019874`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019887`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001989a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800198ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800198c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800198d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800198e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800198f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001990c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001991f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001996b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001997f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019993`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800199a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800199cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800199de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019a1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019b57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019b66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019b76`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a213`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a213`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180019d18`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180019d18`
- `RPCRT4!UuidFromStringW` at `0x180019c5c`
- `RPCRT4!UuidFromStringW` at `0x180019c5c`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x18001a06a`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x18001a06a`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18001a2f4`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18001a2f4`
- `DMCmnUtils!UnicodeToMB` at `0x18001a1e1`
- `DMCmnUtils!UnicodeToMB` at `0x18001a1e1`
- `DMCmnUtils!BigStrcat` at `0x180019d55`
- `DMCmnUtils!BigStrcat` at `0x180019d55`
- `DMCmnUtils!InvStrCmpIW` at `0x180019efe`
- `DMCmnUtils!InvStrCmpIW` at `0x18001a27d`
- `DMCmnUtils!InvStrCmpIW` at `0x180019efe`
- `DMCmnUtils!InvStrCmpIW` at `0x18001a27d`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x180019a8b`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x180019a8b`
- `DMCmnUtils!CopyString` at `0x180019c25`
- `DMCmnUtils!CopyString` at `0x180019c25`
- `DMCmnUtils!InvStrCmpW` at `0x180019e2d`
- `DMCmnUtils!InvStrCmpW` at `0x180019e7e`
- `DMCmnUtils!InvStrCmpW` at `0x180019e2d`
- `DMCmnUtils!InvStrCmpW` at `0x180019e7e`
- `DMPushProxy!__imp_PushRouter_SubmitPush` at `0x18001a384`
- `DMPushProxy!__imp_PushRouter_SubmitPush` at `0x18001a384`
- `dmEnrollEngine!GetEnrollmentState` at `0x180019c85`
- `dmEnrollEngine!GetEnrollmentState` at `0x180019c85`

## string_xrefs

- `0x180019e26`: `com.microsoft:mdm.unenrollment.userrequest`

## pseudocode

```c
__int64 __fastcall OmaDmInitiateSession_Internal(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        int a8,
        WCHAR **a9,
        unsigned int a10,
        int a11,
        int a12)
{
  __int64 v12; // r15
  __int64 v17; // rsi
  WCHAR *v18; // r14
  unsigned int v19; // r13d
  int AccountIDFromLookupID; // edi
  __int64 v21; // rbx
  unsigned int v22; // r12d
  _BYTE *v23; // rax
  __int64 v24; // rcx
  __int64 j; // rsi
  unsigned int k; // ebx
  const unsigned __int16 *v27; // rsi
  const unsigned __int16 *v28; // rcx
  DWORD ModuleFileNameW; // eax
  DWORD v30; // ebx
  COmaDmLogger *Logger; // rax
  const unsigned __int16 *v32; // rbx
  int v33; // ecx
  COmaDmLogger *v34; // rax
  const unsigned __int16 *v35; // rdx
  unsigned int v36; // r9d
  void *v37; // rbx
  HANDLE ProcessHeap; // rax
  bool v40; // zf
  int v41; // eax
  __int64 v42; // rcx
  __int64 v43; // rcx
  HLOCAL v44; // rbx
  char IsStateSeparationEnabled; // al
  HLOCAL v46; // r9
  const wchar_t *v47; // rdx
  HLOCAL v48; // rbx
  __int64 v49; // rdx
  __int64 v50; // rax
  const unsigned __int16 *v51; // rcx
  unsigned int v52; // ebx
  int i; // edi
  __int64 v54; // rbx
  HLOCAL *v55; // r14
  const unsigned __int16 *v56; // rcx
  __int64 v57; // rsi
  int v58; // edx
  const unsigned __int16 **v59; // r15
  const BYTE **v60; // r12
  DWORD *v61; // r13
  _DWORD *v62; // rbx
  const unsigned __int16 *v63; // rdx
  __int64 *v64; // rax
  wchar_t ***v65; // r9
  const unsigned __int16 *v66; // rcx
  _OWORD *v67; // rax
  int *v68; // rcx
  __int64 v69; // rdx
  __int128 v70; // xmm1
  __int128 v71; // xmm0
  __int128 v72; // xmm1
  __int128 v73; // xmm0
  __int128 v74; // xmm1
  __int128 v75; // xmm0
  __int128 v76; // xmm1
  _OWORD *v77; // rax
  int *v78; // rcx
  __int128 v79; // xmm1
  __int128 v80; // xmm0
  __int128 v81; // xmm1
  __int128 v82; // xmm0
  __int128 v83; // xmm1
  __int128 v84; // xmm0
  __int128 v85; // xmm1
  unsigned int v86; // eax
  unsigned int v87; // ebx
  SIZE_T v88; // rsi
  char *v89; // rax
  char *v90; // rdi
  char v91; // al
  int v92; // eax
  __int64 v93; // rdx
  HLOCAL v94; // rsi
  int AccountRootKey; // eax
  WCHAR *v96; // rax
  __int64 v97; // rdx
  int v98; // ecx
  __int64 v99; // rdx
  bool v100; // [rsp+80h] [rbp-80h] BYREF
  char v101[3]; // [rsp+81h] [rbp-7Fh] BYREF
  int v102; // [rsp+84h] [rbp-7Ch]
  HLOCAL v103; // [rsp+88h] [rbp-78h] BYREF
  size_t v104[2]; // [rsp+90h] [rbp-70h] BYREF
  void *v105[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v106; // [rsp+B0h] [rbp-50h]
  int v107; // [rsp+B8h] [rbp-48h] BYREF
  int v108; // [rsp+BCh] [rbp-44h]
  int v109; // [rsp+C0h] [rbp-40h]
  int v110; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned int v111; // [rsp+C8h] [rbp-38h]
  HLOCAL v112; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v113; // [rsp+D8h] [rbp-28h]
  LPVOID lpMem; // [rsp+E0h] [rbp-20h] BYREF
  HKEY v115; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v116; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v117; // [rsp+F8h] [rbp-8h]
  WCHAR **v118; // [rsp+100h] [rbp+0h]
  _DWORD v119[4]; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v120; // [rsp+120h] [rbp+20h]
  __int64 v121; // [rsp+128h] [rbp+28h]
  unsigned int v122; // [rsp+130h] [rbp+30h]
  unsigned int v123; // [rsp+134h] [rbp+34h]
  unsigned int v124; // [rsp+138h] [rbp+38h]
  int v125; // [rsp+13Ch] [rbp+3Ch]
  int v126; // [rsp+140h] [rbp+40h]
  unsigned __int16 *v127; // [rsp+148h] [rbp+48h]
  __int128 v128; // [rsp+150h] [rbp+50h] BYREF
  __int128 v129; // [rsp+160h] [rbp+60h]
  __int128 v130; // [rsp+170h] [rbp+70h]
  __int64 v131; // [rsp+180h] [rbp+80h]
  _BYTE v132[512]; // [rsp+190h] [rbp+90h] BYREF
  UUID Uuid; // [rsp+390h] [rbp+290h] BYREF
  int v134; // [rsp+3A0h] [rbp+2A0h] BYREF
  int v135; // [rsp+3A4h] [rbp+2A4h]
  HLOCAL hMem; // [rsp+3A8h] [rbp+2A8h]
  HLOCAL v137; // [rsp+3B0h] [rbp+2B0h]
  HLOCAL v138; // [rsp+3B8h] [rbp+2B8h]
  HLOCAL v139; // [rsp+3C0h] [rbp+2C0h]
  HLOCAL v140; // [rsp+3C8h] [rbp+2C8h]
  HLOCAL v141; // [rsp+3D0h] [rbp+2D0h]
  HLOCAL v142; // [rsp+3D8h] [rbp+2D8h]
  HLOCAL v143; // [rsp+3E0h] [rbp+2E0h]
  HLOCAL v144; // [rsp+3E8h] [rbp+2E8h]
  HLOCAL v145; // [rsp+3F0h] [rbp+2F0h]
  unsigned int v146; // [rsp+3F8h] [rbp+2F8h]
  HLOCAL v147; // [rsp+410h] [rbp+310h]
  int v148; // [rsp+418h] [rbp+318h]
  int v149; // [rsp+428h] [rbp+328h]
  HLOCAL v150; // [rsp+430h] [rbp+330h]
  HLOCAL v151; // [rsp+438h] [rbp+338h]
  HLOCAL v152; // [rsp+440h] [rbp+340h]
  HLOCAL v153; // [rsp+448h] [rbp+348h]
  HLOCAL v154; // [rsp+450h] [rbp+350h]
  HLOCAL v156[19]; // [rsp+468h] [rbp+368h] BYREF
  int v157; // [rsp+504h] [rbp+404h]
  HLOCAL v158; // [rsp+510h] [rbp+410h]
  HLOCAL v159; // [rsp+518h] [rbp+418h]
  HLOCAL v160; // [rsp+558h] [rbp+458h]
  HLOCAL v161; // [rsp+560h] [rbp+460h]
  HLOCAL v162; // [rsp+570h] [rbp+470h]
  HLOCAL v163; // [rsp+578h] [rbp+478h]
  HLOCAL v164; // [rsp+588h] [rbp+488h]
  unsigned int v165; // [rsp+590h] [rbp+490h]
  HLOCAL v166; // [rsp+598h] [rbp+498h]
  WCHAR Filename[264]; // [rsp+5A0h] [rbp+4A0h] BYREF

  v12 = a6;
  v116 = a1;
  v118 = a9;
  v109 = 0;
  LODWORD(v104[0]) = 0;
  lpMem = 0;
  v112 = 0;
  v117 = a3;
  v113 = a2;
  v131 = 0;
  v111 = a4;
  v106 = a6;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  memset_0(&v134, 0, 0x200u);
  v17 = 0;
  v103 = 0;
  v18 = 0;
  memset_0(v119, 0, 0x40u);
  v115 = 0;
  v107 = 63;
  Uuid = 0;
  if ( !a2 )
    goto LABEL_2;
  v40 = a3 == 0;
  v19 = a7;
  if ( v40 || a7 && !a6 )
  {
LABEL_38:
    AccountIDFromLookupID = -2147024809;
    goto LABEL_3;
  }
  if ( a1 && !(unsigned int)IsValidUserSid(a1) )
  {
    AccountIDFromLookupID = -2102788085;
    goto LABEL_3;
  }
  if ( a5 )
  {
    if ( a5 != 1 && a5 != 2 && a5 - 3 > 1 )
      goto LABEL_38;
    v41 = a5 - 1;
  }
  else
  {
    v41 = 1;
  }
  v108 = v41;
  if ( !a4 )
  {
    AccountIDFromLookupID = OmaDmGetAccountIDFromLookupID(a2, 0, &v103);
LABEL_42:
    if ( AccountIDFromLookupID < 0 )
      goto LABEL_3;
    goto LABEL_43;
  }
  if ( a4 != 1 )
    goto LABEL_38;
  AccountIDFromLookupID = CopyString(a2, 0xFFFFFFFF, (unsigned __int16 **)&v103);
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_42;
LABEL_43:
  if ( UuidFromStringW((RPC_WSTR)v103, &Uuid) )
    goto LABEL_38;
  v21 = 0;
  *(UUID *)v105 = Uuid;
  v102 = 0;
  AccountIDFromLookupID = GetEnrollmentState(v105, &v107);
  if ( AccountIDFromLookupID < 0 )
  {
LABEL_80:
    if ( AccountIDFromLookupID >= 0 || !(_DWORD)v21 )
    {
      v21 = 0;
      goto LABEL_102;
    }
    goto LABEL_82;
  }
  if ( v107 == 5 )
  {
    AccountIDFromLookupID = -2147024891;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        MDM_ENTERPRISE_DIAGNOSTICS_Context,
        EnterpriseDiagnosticsInitiateSessionForDormantEnrollmentBlocked,
        v103);
      goto LABEL_4;
    }
LABEL_102:
    v12 = v106;
    v19 = a7;
    goto LABEL_4;
  }
  v22 = a10;
  if ( a10 <= 0x2D )
  {
    v42 = 0x208080000000LL;
    if ( _bittest64(&v42, a10) )
    {
      if ( (int)DC_CheckAndUpdatePendingDocs((__int64)v103, a10, a6, a7) < 0 && byte_180032C41 < 0 )
        McTemplateU0zzd_EventWriteTransfer(v43);
    }
  }
  v44 = v103;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v46 = v44;
  v47 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  if ( !IsStateSeparationEnabled )
    v47 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  v21 = 0;
  v105[0] = BigStrcat(5u, v47, L"\\", v46, L"\\", v117);
  v18 = (WCHAR *)v105[0];
  if ( !v105[0] )
  {
    AccountIDFromLookupID = -2147024882;
    goto LABEL_5;
  }
  v48 = v103;
  v134 = 512;
  if ( !v103 )
  {
    AccountIDFromLookupID = -2147024809;
LABEL_76:
    v21 = 0;
    goto LABEL_5;
  }
  memset_0(&v134, 0, 0x200u);
  v134 = 512;
  v135 = -1;
  v49 = 0;
  v149 = -1;
  v157 = -1;
  do
  {
    v50 = 9 * v49++;
    LODWORD(v156[v50]) = -1;
  }
  while ( v49 != 2 );
  AccountIDFromLookupID = OmaDmGetAcctInfo(v48, 1, &v134);
  v21 = 0;
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_5;
  if ( (v148 & 0x2000000) != 0
    && (v135 & 0x800000) != 0
    && (!a6
     || (v51 = *(const unsigned __int16 **)(a6 + 8)) == 0
     || InvStrCmpW(v51, L"com.microsoft:mdm.unenrollment.userrequest")) )
  {
    AccountIDFromLookupID = -2147024891;
    v109 = -2102657015;
    goto LABEL_5;
  }
  v52 = -1;
  for ( i = 0; i < 2; ++i )
  {
    if ( ((__int64)v156[9 * v17 + 7] & 0x10) != 0
      && ((__int64)v156[9 * v17] & 0x10) != 0
      && !InvStrCmpW((const unsigned __int16 *)v156[9 * v17 + 5], L"SRVCRED") )
    {
      v52 = i;
    }
    ++v17;
  }
  if ( v52 == -1 )
  {
    AccountIDFromLookupID = -2147418113;
    goto LABEL_76;
  }
  if ( v52 > 1 )
  {
    AccountIDFromLookupID = -2147024809;
LABEL_79:
    LODWORD(v21) = v102;
    goto LABEL_80;
  }
  v54 = 9LL * (int)v52;
  v55 = &v156[v54];
  if ( !v55 )
  {
    AccountIDFromLookupID = -2147418113;
    goto LABEL_135;
  }
  v57 = 4;
  if ( InvStrCmpIW((const unsigned __int16 *)v55[7], L"TRANSPORT") )
  {
    v58 = (int)v156[v54 + 7];
    v21 = 0;
    if ( (v58 & 4) == 0
      || (v56 = (const unsigned __int16 *)*(unsigned int *)v55, (*(_BYTE *)v55 & 4) == 0)
      || (v58 & 8) == 0
      || ((unsigned __int8)v56 & 8) == 0 )
    {
      v18 = (WCHAR *)v105[0];
      AccountIDFromLookupID = -2147024809;
      goto LABEL_5;
    }
    v59 = (const unsigned __int16 **)(v55 + 3);
    v60 = (const BYTE **)(v55 + 4);
    v61 = (DWORD *)(v55 + 5);
  }
  else
  {
    v61 = 0;
    v59 = 0;
    v60 = 0;
  }
  v62 = (_DWORD *)v106;
  v120 = a5;
  v122 = a7;
  v123 = v111;
  v124 = a10;
  v125 = a11;
  v126 = a12;
  v127 = v116;
  v119[0] = 64;
  v121 = v106;
  if ( IsCriticalMsg(v56, (struct OMADMINITIATIONINFO *const)v119) || !v121 )
  {
    v21 = 0;
  }
  else
  {
    v40 = *v62 == 64;
    v100 = 0;
    if ( v40 )
    {
      v64 = qword_180025C50;
      v65 = &off_180025C48;
    }
    else
    {
      if ( *v62 != 56 )
      {
        v18 = (WCHAR *)v105[0];
        v12 = (__int64)v62;
LABEL_2:
        v19 = a7;
        AccountIDFromLookupID = -2147024809;
LABEL_3:
        v21 = 0;
LABEL_4:
        v22 = a10;
        goto LABEL_5;
      }
      v64 = &qword_180025C40;
      v65 = &off_180025C38;
    }
    v21 = 0;
    AccountIDFromLookupID = ShouldBlockMsg(
                              (PUCHAR)v103,
                              v63,
                              (struct OMADMINITIATIONINFO *const)v119,
                              (struct STRUCTMEMBERDATA *const)*v65,
                              *(_DWORD *)v64,
                              &v100);
    if ( AccountIDFromLookupID < 0 )
      goto LABEL_136;
    if ( v100 )
    {
      v18 = (WCHAR *)v105[0];
      AccountIDFromLookupID = -2102656507;
      goto LABEL_102;
    }
  }
  AccountIDFromLookupID = OmaDmSetInitiationInfo((WCHAR *)v105[0], (__int64)v119, a8);
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_135;
  if ( !IsWvdFeatureAllowed((const unsigned __int16 *)v103)
    && !IsCriticalMsg(v66, (struct OMADMINITIATIONINFO *const)v119) )
  {
    v100 = 0;
    v67 = v132;
    v101[0] = 0;
    v68 = &v134;
    v69 = 4;
    do
    {
      v70 = *((_OWORD *)v68 + 1);
      *v67 = *(_OWORD *)v68;
      v71 = *((_OWORD *)v68 + 2);
      v67[1] = v70;
      v72 = *((_OWORD *)v68 + 3);
      v67[2] = v71;
      v73 = *((_OWORD *)v68 + 4);
      v67[3] = v72;
      v74 = *((_OWORD *)v68 + 5);
      v67[4] = v73;
      v75 = *((_OWORD *)v68 + 6);
      v67[5] = v74;
      v76 = *((_OWORD *)v68 + 7);
      v68 += 32;
      v67[6] = v75;
      v67[7] = v76;
      v67 += 8;
      --v69;
    }
    while ( v69 );
    AccountIDFromLookupID = ShouldMsgBeQueued((__int64)v103, (__int64)v132, a10, &v100, v101);
    if ( AccountIDFromLookupID < 0 )
      goto LABEL_135;
    if ( v100 )
    {
      v18 = (WCHAR *)v105[0];
      AccountIDFromLookupID = UpdateSessionState((const WCHAR *)v105[0]);
      if ( AccountIDFromLookupID >= 0 )
      {
        v77 = v132;
        v78 = &v134;
        do
        {
          v79 = *((_OWORD *)v78 + 1);
          *v77 = *(_OWORD *)v78;
          v80 = *((_OWORD *)v78 + 2);
          v77[1] = v79;
          v81 = *((_OWORD *)v78 + 3);
          v77[2] = v80;
          v82 = *((_OWORD *)v78 + 4);
          v77[3] = v81;
          v83 = *((_OWORD *)v78 + 5);
          v77[4] = v82;
          v84 = *((_OWORD *)v78 + 6);
          v77[5] = v83;
          v85 = *((_OWORD *)v78 + 7);
          v78 += 32;
          v77[6] = v84;
          v77[7] = v85;
          v77 += 8;
          --v57;
        }
        while ( v57 );
        AccountIDFromLookupID = ScheduleQueuedTask((__int64)v132, (const unsigned __int16 *)v103, v101[0]);
        if ( AccountIDFromLookupID >= 0 )
        {
          AccountIDFromLookupID = -2102656508;
          goto LABEL_102;
        }
      }
      goto LABEL_79;
    }
  }
  LODWORD(v21) = 1;
  v102 = 1;
  AccountIDFromLookupID = UnicodeToMB(v113, 0xFDE9u, (char **)&lpMem, (unsigned int *)v104);
  if ( AccountIDFromLookupID < 0 )
  {
LABEL_136:
    v18 = (WCHAR *)v105[0];
    goto LABEL_80;
  }
  v86 = LODWORD(v104[0]) - 1;
  LODWORD(v104[0]) = v86;
  if ( v86 > 0xFF )
  {
    AccountIDFromLookupID = -2147024809;
    goto LABEL_121;
  }
  v87 = v86 + 24;
  v88 = v86 + 24;
  v89 = (char *)LocalAlloc(0, v88);
  v112 = v89;
  if ( !v89 )
  {
    AccountIDFromLookupID = -2147024882;
LABEL_121:
    v18 = (WCHAR *)v105[0];
LABEL_82:
    v21 = 0;
LABEL_83:
    OmaDmCloseSession(v18);
    goto LABEL_102;
  }
  v90 = v89 + 16;
  memset_0(v89, 0, v88);
  v91 = v108;
  *v90 = 2;
  v90[1] = 16 * (v91 | 0xFC);
  *(_WORD *)(v90 + 5) = 0;
  v90[7] = v104[0];
  memcpy_0(v90 + 8, lpMem, LODWORD(v104[0]));
  v92 = InvStrCmpIW((const unsigned __int16 *)v55[7], L"TRANSPORT");
  v94 = v112;
  if ( v92 )
  {
    AccountIDFromLookupID = OmaDmCalcTriggerDigest(v113, *v59, *v60, *v61, (BYTE *)v90, v87 - 16, (BYTE *)v112, 0x10u);
    if ( AccountIDFromLookupID < 0 )
    {
LABEL_135:
      v18 = (WCHAR *)v105[0];
      goto LABEL_79;
    }
  }
  AccountRootKey = GetAccountRootKey(v103, v93, &v115);
  v18 = (WCHAR *)v105[0];
  AccountIDFromLookupID = AccountRootKey;
  if ( AccountRootKey < 0 )
    goto LABEL_79;
  AccountIDFromLookupID = OmaDmRegistrySetDWORD(v115, (const unsigned __int16 *)v105[0], L"SessionAbort", 0);
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_79;
  v22 = a10;
  *((_QWORD *)&v128 + 1) = L"Content-Type: application/vnd.syncml.notification\r\n"
                            "X-Wap-Application-Id: x-wap-application:syncml.dm";
  *((_QWORD *)&v129 + 1) = __PAIR64__(a10, v87);
  v96 = v18;
  LODWORD(v128) = 56;
  v97 = 260;
  *(_QWORD *)&v129 = v94;
  v21 = 0;
  *((_QWORD *)&v130 + 1) = v18;
  do
  {
    if ( !*v96 )
      break;
    ++v96;
    --v97;
  }
  while ( v97 );
  AccountIDFromLookupID = v97 == 0 ? 0x80070057 : 0;
  if ( !v97 )
    goto LABEL_83;
  v98 = 2 * (260 - v97);
  v99 = -v97;
  LODWORD(v131) = v99 != 0 ? v98 + 2 : 2;
  AccountIDFromLookupID = PushRouter_SubmitPush(&v128, v99);
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_79;
  if ( !v118 )
    goto LABEL_102;
  v12 = v106;
  v19 = a7;
  *v118 = v18;
  v18 = 0;
LABEL_5:
  if ( v134 == 512 )
  {
    v23 = v145;
    if ( v145 )
    {
      v24 = v146;
      if ( v146 )
      {
        do
        {
          *v23++ = 0;
          --v24;
        }
        while ( v24 );
      }
    }
    LocalFree(hMem);
    LocalFree(v137);
    LocalFree(v138);
    LocalFree(v139);
    LocalFree(v140);
    LocalFree(v141);
    LocalFree(v142);
    LocalFree(v143);
    LocalFree(v144);
    LocalFree(v145);
    LocalFree(v147);
    LocalFree(v160);
    LocalFree(v161);
    LocalFree(v162);
    LocalFree(v163);
    LocalFree(v164);
    LocalFree(v150);
    LocalFree(v151);
    LocalFree(v152);
    LocalFree(v153);
    LocalFree(v154);
    for ( j = 0; j != 2; ++j )
    {
      ZeroAndFreeString((unsigned __int16 **)((char *)&v156[1] + v21));
      ZeroAndFreeString((unsigned __int16 **)((char *)&v156[2] + v21));
      memset_0(*(HLOCAL *)((char *)&v156[3] + v21), 0, *(unsigned int *)((char *)&v156[4] + v21));
      LocalFree(*(HLOCAL *)((char *)&v156[3] + v21));
      LocalFree(*(HLOCAL *)((char *)v156 + v21));
      LocalFree(*(HLOCAL *)((char *)&v156[5] + v21));
      LocalFree(*(HLOCAL *)((char *)&v156[6] + v21));
      v21 += 72;
    }
    LocalFree(v158);
    LocalFree(v159);
    for ( k = 0; k < v165; ++k )
      OmaDmFreeUserInfo((char *)v166 + 24 * k);
    LocalFree(v166);
    memset_0(&v134, 0, 0x200u);
  }
  v27 = 0;
  if ( v19 && v12 )
    v27 = *(const unsigned __int16 **)(v12 + 8);
  v28 = v113;
  if ( v103 )
    v28 = (const unsigned __int16 *)v103;
  InitializeCVMapForDmSession(v28);
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  v110 = 0;
  v30 = ModuleFileNameW;
  DmIsSystemOrAdmin(&v110);
  Logger = COmaDmLogger::GetLogger();
  v32 = (const unsigned __int16 *)((unsigned __int64)Filename & -(__int64)(v30 != 0));
  v33 = v109;
  if ( !v109 )
    v33 = AccountIDFromLookupID;
  COmaDmLogger::LogOmaDmApiInitiateSession(
    Logger,
    v113,
    v111,
    v117,
    a5,
    v22,
    a8,
    v19,
    v27,
    v116,
    a11,
    a12,
    v32,
    v110,
    v33);
  if ( AccountIDFromLookupID < 0 )
  {
    v34 = COmaDmLogger::GetLogger();
    COmaDmLogger::LogOmaDmApiCallstack(v34, v35, v32, v36, AccountIDFromLookupID);
  }
  v37 = lpMem;
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v37);
  LocalFree(v112);
  LocalFree(v18);
  LocalFree(v103);
  return (unsigned int)AccountIDFromLookupID;
}

```

## disassembly

```asm
0x180019684  push    rbp
0x180019686  push    rbx
0x180019687  push    rsi
0x180019688  push    rdi
0x180019689  push    r12
0x18001968b  push    r13
0x18001968d  push    r14
0x18001968f  push    r15
0x180019691  lea     rbp, [rsp-6C8h]
0x180019699  sub     rsp, 7C8h
0x1800196a0  mov     rax, cs:__security_cookie
0x1800196a7  xor     rax, rsp
0x1800196aa  mov     [rbp+700h+var_50], rax
0x1800196b1  mov     rax, [rbp+700h+arg_40]
0x1800196b8  xorps   xmm0, xmm0
0x1800196bb  mov     r15, [rbp+700h+arg_28]
0x1800196c2  mov     rdi, rcx
0x1800196c5  mov     [rbp+700h+var_710], rcx
0x1800196c9  mov     r13, r8
0x1800196cc  xor     ecx, ecx
0x1800196ce  mov     [rbp+700h+var_700], rax
0x1800196d2  mov     [rbp+700h+var_740], ecx
0x1800196d5  xor     eax, eax
0x1800196d7  mov     dword ptr [rbp+700h+var_770], ecx
0x1800196da  mov     rbx, rdx
0x1800196dd  mov     [rbp+700h+lpMem], rcx
0x1800196e1  mov     r12d, r9d
0x1800196e4  mov     [rbp+700h+var_730], rcx
0x1800196e8  lea     rcx, [rbp+700h+var_460]; void *
0x1800196ef  mov     [rbp+700h+var_708], r8
0x1800196f3  mov     r8d, 200h; Size
0x1800196f9  mov     [rbp+700h+var_728], rdx
0x1800196fd  xor     edx, edx; Val
0x1800196ff  mov     [rbp+700h+var_680], rax
0x180019706  mov     [rbp+700h+var_738], r9d
0x18001970a  mov     [rbp+700h+var_750], r15
0x18001970e  movups  [rbp+700h+var_6B0], xmm0
0x180019712  movups  [rbp+700h+var_6A0], xmm0
0x180019716  movups  [rbp+700h+var_690], xmm0
0x18001971a  call    memset_0
0x18001971f  xor     esi, esi
0x180019721  lea     rcx, [rbp+700h+var_6F0]; void *
0x180019725  xor     edx, edx; Val
0x180019727  mov     [rbp+700h+var_778], rsi
0x18001972b  mov     r14d, esi
0x18001972e  lea     r8d, [rsi+40h]; Size
0x180019732  call    memset_0
0x180019737  mov     [rbp+700h+var_718], rsi
0x18001973b  xorps   xmm0, xmm0
0x18001973e  mov     [rbp+700h+var_748], 3Fh ; '?'
0x180019745  movups  xmmword ptr [rbp+700h+Uuid.Data1], xmm0
0x18001974c  test    rbx, rbx
0x18001974f  jnz     loc_180019BA8
0x180019755  mov     r13d, [rbp+700h+arg_30]
0x18001975c  mov     edi, 80070057h
0x180019761  xor     ebx, ebx
0x180019763  mov     r12d, [rbp+700h+arg_48]
0x18001976a  cmp     [rbp+700h+var_460], 200h
0x180019774  jnz     loc_180019A3D
0x18001977a  mov     rax, [rbp+700h+var_410]
0x180019781  test    rax, rax
0x180019784  jz      short loc_18001979C
0x180019786  mov     ecx, [rbp+700h+var_408]
0x18001978c  test    rcx, rcx
0x18001978f  jz      short loc_18001979C
0x180019791  mov     [rax], bl
0x180019793  inc     rax
0x180019796  sub     rcx, 1
0x18001979a  jnz     short loc_180019791
0x18001979c  mov     rcx, [rbp+700h+hMem]; hMem
0x1800197a3  call    cs:__imp_LocalFree
0x1800197aa  nop     dword ptr [rax+rax+00h]
0x1800197af  mov     rcx, [rbp+700h+var_450]; hMem
0x1800197b6  call    cs:__imp_LocalFree
0x1800197bd  nop     dword ptr [rax+rax+00h]
0x1800197c2  mov     rcx, [rbp+700h+var_448]; hMem
0x1800197c9  call    cs:__imp_LocalFree
0x1800197d0  nop     dword ptr [rax+rax+00h]
0x1800197d5  mov     rcx, [rbp+700h+var_440]; hMem
0x1800197dc  call    cs:__imp_LocalFree
0x1800197e3  nop     dword ptr [rax+rax+00h]
0x1800197e8  mov     rcx, [rbp+700h+var_438]; hMem
0x1800197ef  call    cs:__imp_LocalFree
0x1800197f6  nop     dword ptr [rax+rax+00h]
0x1800197fb  mov     rcx, [rbp+700h+var_430]; hMem
0x180019802  call    cs:__imp_LocalFree
0x180019809  nop     dword ptr [rax+rax+00h]
0x18001980e  mov     rcx, [rbp+700h+var_428]; hMem
0x180019815  call    cs:__imp_LocalFree
0x18001981c  nop     dword ptr [rax+rax+00h]
0x180019821  mov     rcx, [rbp+700h+var_420]; hMem
0x180019828  call    cs:__imp_LocalFree
0x18001982f  nop     dword ptr [rax+rax+00h]
0x180019834  mov     rcx, [rbp+700h+var_418]; hMem
0x18001983b  call    cs:__imp_LocalFree
0x180019842  nop     dword ptr [rax+rax+00h]
0x180019847  mov     rcx, [rbp+700h+var_410]; hMem
0x18001984e  call    cs:__imp_LocalFree
0x180019855  nop     dword ptr [rax+rax+00h]
0x18001985a  mov     rcx, [rbp+700h+var_3F0]; hMem
0x180019861  call    cs:__imp_LocalFree
0x180019868  nop     dword ptr [rax+rax+00h]
0x18001986d  mov     rcx, [rbp+700h+var_2A8]; hMem
0x180019874  call    cs:__imp_LocalFree
0x18001987b  nop     dword ptr [rax+rax+00h]
0x180019880  mov     rcx, [rbp+700h+var_2A0]; hMem
0x180019887  call    cs:__imp_LocalFree
0x18001988e  nop     dword ptr [rax+rax+00h]
0x180019893  mov     rcx, [rbp+700h+var_290]; hMem
0x18001989a  call    cs:__imp_LocalFree
0x1800198a1  nop     dword ptr [rax+rax+00h]
0x1800198a6  mov     rcx, [rbp+700h+var_288]; hMem
0x1800198ad  call    cs:__imp_LocalFree
0x1800198b4  nop     dword ptr [rax+rax+00h]
0x1800198b9  mov     rcx, [rbp+700h+var_278]; hMem
0x1800198c0  call    cs:__imp_LocalFree
0x1800198c7  nop     dword ptr [rax+rax+00h]
0x1800198cc  mov     rcx, [rbp+700h+var_3D0]; hMem
0x1800198d3  call    cs:__imp_LocalFree
0x1800198da  nop     dword ptr [rax+rax+00h]
0x1800198df  mov     rcx, [rbp+700h+var_3C8]; hMem
0x1800198e6  call    cs:__imp_LocalFree
0x1800198ed  nop     dword ptr [rax+rax+00h]
0x1800198f2  mov     rcx, [rbp+700h+var_3C0]; hMem
0x1800198f9  call    cs:__imp_LocalFree
0x180019900  nop     dword ptr [rax+rax+00h]
0x180019905  mov     rcx, [rbp+700h+var_3B8]; hMem
0x18001990c  call    cs:__imp_LocalFree
0x180019913  nop     dword ptr [rax+rax+00h]
0x180019918  mov     rcx, [rbp+700h+var_3B0]; hMem
0x18001991f  call    cs:__imp_LocalFree
0x180019926  nop     dword ptr [rax+rax+00h]
0x18001992b  mov     rsi, rbx
0x18001992e  lea     rcx, [rbp+700h+var_390]
0x180019935  add     rcx, rbx; unsigned __int16 **
0x180019938  call    ?ZeroAndFreeString@@YAJPEAPEAG@Z; ZeroAndFreeString(ushort * *)
0x18001993d  lea     rcx, [rbp+700h+var_388]
0x180019944  add     rcx, rbx; unsigned __int16 **
0x180019947  call    ?ZeroAndFreeString@@YAJPEAPEAG@Z; ZeroAndFreeString(ushort * *)
0x18001994c  mov     r8d, dword ptr [rbp+rbx+700h+Size]; Size
0x180019954  xor     edx, edx; Val
0x180019956  mov     rcx, [rbp+rbx+700h+var_380]; void *
0x18001995e  call    memset_0
0x180019963  mov     rcx, [rbp+rbx+700h+var_380]; hMem
0x18001996b  call    cs:__imp_LocalFree
0x180019972  nop     dword ptr [rax+rax+00h]
0x180019977  mov     rcx, [rbp+rbx+700h+var_398]; hMem
0x18001997f  call    cs:__imp_LocalFree
0x180019986  nop     dword ptr [rax+rax+00h]
0x18001998b  mov     rcx, [rbp+rbx+700h+var_370]; hMem
0x180019993  call    cs:__imp_LocalFree
0x18001999a  nop     dword ptr [rax+rax+00h]
0x18001999f  mov     rcx, [rbp+rbx+700h+var_368]; hMem
0x1800199a7  call    cs:__imp_LocalFree
0x1800199ae  nop     dword ptr [rax+rax+00h]
0x1800199b3  inc     rsi
0x1800199b6  add     rbx, 48h ; 'H'
0x1800199ba  cmp     rsi, 2
0x1800199be  jnz     loc_18001992E
0x1800199c4  mov     rcx, [rbp+700h+var_2F0]; hMem
0x1800199cb  call    cs:__imp_LocalFree
0x1800199d2  nop     dword ptr [rax+rax+00h]
0x1800199d7  mov     rcx, [rbp+700h+var_2E8]; hMem
0x1800199de  call    cs:__imp_LocalFree
0x1800199e5  nop     dword ptr [rax+rax+00h]
0x1800199ea  xor     eax, eax
0x1800199ec  mov     ebx, eax
0x1800199ee  cmp     [rbp+700h+var_270], eax
0x1800199f4  jbe     short loc_180019A16
0x1800199f6  mov     eax, ebx
0x1800199f8  lea     rcx, [rax+rax*2]
0x1800199fc  mov     rax, [rbp+700h+var_268]
0x180019a03  lea     rcx, [rax+rcx*8]
0x180019a07  call    OmaDmFreeUserInfo
0x180019a0c  inc     ebx
0x180019a0e  cmp     ebx, [rbp+700h+var_270]
0x180019a14  jb      short loc_1800199F6
0x180019a16  mov     rcx, [rbp+700h+var_268]; hMem
0x180019a1d  call    cs:__imp_LocalFree
0x180019a24  nop     dword ptr [rax+rax+00h]
0x180019a29  xor     edx, edx; Val
0x180019a2b  lea     rcx, [rbp+700h+var_460]; void *
0x180019a32  mov     r8d, 200h; Size
0x180019a38  call    memset_0
0x180019a3d  xor     edx, edx
0x180019a3f  mov     esi, edx
0x180019a41  test    r13d, r13d
0x180019a44  jz      short loc_180019A4F
0x180019a46  test    r15, r15
0x180019a49  jz      short loc_180019A4F
0x180019a4b  mov     rsi, [r15+8]
0x180019a4f  mov     rax, [rbp+700h+var_778]
0x180019a53  mov     rcx, [rbp+700h+var_728]
0x180019a57  test    rax, rax
0x180019a5a  cmovnz  rcx, rax; unsigned __int16 *
0x180019a5e  call    ?InitializeCVMapForDmSession@@YAJPEBG@Z; InitializeCVMapForDmSession(ushort const *)
0x180019a63  mov     r8d, 104h; nSize
0x180019a69  lea     rdx, [rbp+700h+Filename]; lpFilename
0x180019a70  xor     ecx, ecx; hModule
0x180019a72  call    cs:__imp_GetModuleFileNameW
0x180019a79  nop     dword ptr [rax+rax+00h]
0x180019a7e  lea     rcx, [rbp+700h+var_73C]
0x180019a82  mov     [rbp+700h+var_73C], 0
0x180019a89  mov     ebx, eax
0x180019a8b  call    cs:__imp_?DmIsSystemOrAdmin@@YAJPEAH@Z; DmIsSystemOrAdmin(int *)
0x180019a92  nop     dword ptr [rax+rax+00h]
0x180019a97  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x180019a9c  mov     r9, [rbp+700h+var_708]; unsigned __int16 *
0x180019aa0  lea     rcx, [rbp+700h+Filename]
0x180019aa7  mov     r8d, [rbp+700h+var_738]; unsigned int
0x180019aab  neg     ebx
0x180019aad  mov     rdx, [rbp+700h+var_728]; unsigned __int16 *
0x180019ab1  sbb     rbx, rbx
0x180019ab4  and     rbx, rcx
0x180019ab7  mov     ecx, [rbp+700h+var_740]
0x180019aba  test    ecx, ecx
0x180019abc  cmovz   ecx, edi
0x180019abf  mov     [rsp+800h+var_790], ecx; int
0x180019ac3  mov     ecx, [rbp+700h+var_73C]
0x180019ac6  mov     [rsp+800h+var_798], ecx; int
0x180019aca  mov     ecx, [rbp+700h+arg_58]
0x180019ad0  mov     [rsp+800h+var_7A0], rbx; unsigned __int16 *
0x180019ad5  mov     [rsp+800h+var_7A8], ecx; int
0x180019ad9  mov     ecx, [rbp+700h+arg_50]
0x180019adf  mov     [rsp+800h+var_7B0], ecx; int
0x180019ae3  mov     rcx, [rbp+700h+var_710]
0x180019ae7  mov     [rsp+800h+var_7B8], rcx; unsigned __int16 *
0x180019aec  mov     ecx, [rbp+700h+arg_38]
0x180019af2  mov     [rsp+800h+var_7C0], rsi; unsigned __int16 *
0x180019af7  mov     [rsp+800h+var_7C8], r13d; unsigned int
0x180019afc  mov     [rsp+800h+var_7D0], ecx; int
0x180019b00  mov     ecx, [rbp+700h+arg_20]
0x180019b06  mov     dword ptr [rsp+800h+var_7D8], r12d; unsigned int
0x180019b0b  mov     [rsp+800h+var_7E0], ecx; unsigned int
0x180019b0f  mov     rcx, rax; this
0x180019b12  call    ?LogOmaDmApiInitiateSession@COmaDmLogger@@QEAAXPEBGK0KKHK00HH0HJ@Z; COmaDmLogger::LogOmaDmApiInitiateSession(ushort const *,ulong,ushort const *,ulong,ulong,int,ulong,ushort const *,ushort const *,int,int,ushort const *,int,long)
0x180019b17  test    edi, edi
0x180019b19  jns     short loc_180019B2F
0x180019b1b  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x180019b20  mov     r8, rbx; unsigned __int16 *
0x180019b23  mov     [rsp+800h+var_7E0], edi; int
0x180019b27  mov     rcx, rax; this
0x180019b2a  call    ?LogOmaDmApiCallstack@COmaDmLogger@@QEAAXPEBG0KJ@Z; COmaDmLogger::LogOmaDmApiCallstack(ushort const *,ushort const *,ulong,long)
0x180019b2f  mov     rbx, [rbp+700h+lpMem]
0x180019b33  call    cs:__imp_GetProcessHeap
0x180019b3a  nop     dword ptr [rax+rax+00h]
0x180019b3f  mov     r8, rbx; lpMem
0x180019b42  xor     edx, edx; dwFlags
0x180019b44  mov     rcx, rax; hHeap
0x180019b47  call    cs:__imp_HeapFree
0x180019b4e  nop     dword ptr [rax+rax+00h]
0x180019b53  mov     rcx, [rbp+700h+var_730]; hMem
0x180019b57  call    cs:__imp_LocalFree
0x180019b5e  nop     dword ptr [rax+rax+00h]
0x180019b63  mov     rcx, r14; hMem
0x180019b66  call    cs:__imp_LocalFree
0x180019b6d  nop     dword ptr [rax+rax+00h]
0x180019b72  mov     rcx, [rbp+700h+var_778]; hMem
0x180019b76  call    cs:__imp_LocalFree
0x180019b7d  nop     dword ptr [rax+rax+00h]
0x180019b82  mov     eax, edi
0x180019b84  mov     rcx, [rbp+700h+var_50]
0x180019b8b  xor     rcx, rsp; StackCookie
0x180019b8e  call    __security_check_cookie
0x180019b93  add     rsp, 7C8h
0x180019b9a  pop     r15
0x180019b9c  pop     r14
0x180019b9e  pop     r13
0x180019ba0  pop     r12
0x180019ba2  pop     rdi
0x180019ba3  pop     rsi
0x180019ba4  pop     rbx
0x180019ba5  pop     rbp
0x180019ba6  retn
0x180019ba8  test    r13, r13
0x180019bab  mov     r13d, [rbp+700h+arg_30]
0x180019bb2  jz      short loc_180019C11
0x180019bb4  test    r13d, r13d
0x180019bb7  jz      short loc_180019BBE
0x180019bb9  test    r15, r15
0x180019bbc  jz      short loc_180019C11
0x180019bbe  test    rdi, rdi
0x180019bc1  jz      short loc_180019BD9
0x180019bc3  mov     rcx, rdi; unsigned __int16 *
0x180019bc6  call    ?IsValidUserSid@@YAHPEBG@Z; IsValidUserSid(ushort const *)
0x180019bcb  test    eax, eax
0x180019bcd  jnz     short loc_180019BD9
0x180019bcf  mov     edi, 82AA000Bh
0x180019bd4  jmp     loc_180019761
0x180019bd9  mov     edx, [rbp+700h+arg_20]
0x180019bdf  mov     ecx, edx
0x180019be1  test    edx, edx
0x180019be3  jz      short loc_180019BFE
0x180019be5  sub     ecx, 1
0x180019be8  jz      short loc_180019BF9
0x180019bea  sub     ecx, 1
0x180019bed  jz      short loc_180019BF9
0x180019bef  sub     ecx, 1
0x180019bf2  jz      short loc_180019BF9
0x180019bf4  cmp     ecx, 1
  ... truncated ...
```
