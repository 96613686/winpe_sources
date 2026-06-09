# CDplServiceImpl::GetAppKeyForAppCache(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,uchar const *,ulong,_GUID const *,ulong,ulong,uchar const *,uchar const *,uchar * *,ulong *,_GUID *,ulong *,ulong *,uchar *,uchar *,uchar *)

- ea: `0x180090228`
- end: `0x1800912be`
- name: `?GetAppKeyForAppCache@CDplServiceImpl@@AEAAJPEAXPEBG11K1PEBEKPEBU_GUID@@KK22PEAPEAEPEAKPEAU2@55PEAE77@Z`
- size: `4246`
- prototype: `int(CDplServiceImpl *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int8 *, unsigned int, const struct _GUID *, unsigned int, unsigned int, const unsigned __int8 *, const unsigned __int8 *, unsigned __int8 **, unsigned int *, struct _GUID *, unsigned int *, unsigned int *, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800977b0`

## callees

- `0x18000505d`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800672b8`
- `0x180067890`
- `0x180087d68`
- `0x180087d84`
- `0x18008e7b0`
- `0x18008fb78`
- `0x180090228`
- `0x180094bb0`
- `0x1800964ac`
- `0x18009652c`
- `0x1800ac870`
- `0x1800af128`
- `0x1800b5a5c`
- `0x1800bd7a8`
- `0x1800bd810`
- `0x1800bedb4`
- `0x1800c2f44`
- `0x1800c33f8`
- `0x1800c39c8`
- `0x1800caa2c`
- `0x1800d5af8`
- `0x1800dca3c`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180091248`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180091248`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180091256`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180091256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800905ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090f8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800905ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090f8a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800905a1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800908d9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180090908`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800905a1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800908d9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180090908`
- `CRYPT32!CryptProtectMemory` at `0x180090f80`
- `CRYPT32!CryptProtectMemory` at `0x180090f80`

## pseudocode

```c
__int64 __fastcall CDplServiceImpl::GetAppKeyForAppCache(
        CDplServiceImpl *this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        unsigned __int16 *a7,
        unsigned __int8 *a8,
        unsigned int Size,
        struct _GUID *a10,
        unsigned int a11,
        unsigned int a12,
        const unsigned __int8 *Buf1,
        const unsigned __int8 *a14,
        unsigned __int8 **a15,
        unsigned int *a16,
        struct _GUID *a17,
        unsigned int *a18,
        unsigned int *a19,
        unsigned __int8 *a20,
        unsigned __int8 *a21,
        unsigned __int8 *a22)
{
  unsigned int *v25; // rcx
  struct _GUID *v26; // rdx
  unsigned int *v27; // r8
  unsigned __int8 *v28; // rax
  __int64 v29; // r14
  unsigned int AppHash; // ebx
  int v31; // r8d
  unsigned int v32; // r13d
  __int64 v33; // rcx
  int v34; // eax
  int v35; // ecx
  signed int LastError; // eax
  int v37; // ecx
  const unsigned __int16 *v38; // rbx
  int v39; // ecx
  unsigned __int16 *v40; // r12
  int v41; // ecx
  CDplServiceImpl *v42; // rsi
  int v43; // ebx
  unsigned __int16 *v44; // r12
  BOOL v45; // ecx
  unsigned __int8 *v46; // r14
  int v47; // eax
  signed int v48; // eax
  int v49; // r8d
  int v50; // eax
  __int64 v51; // rcx
  PSID *v52; // rsi
  int v53; // r8d
  int v54; // ecx
  int v55; // ecx
  __int64 v56; // rcx
  __int64 v57; // rax
  int v58; // ecx
  int v59; // ecx
  unsigned int v60; // esi
  unsigned int v61; // edi
  struct _GUID *v62; // r14
  struct CDplKeyPair *v63; // rcx
  unsigned __int8 *v64; // r15
  struct _GUID v65; // xmm6
  int v66; // eax
  __int64 v67; // rax
  unsigned __int8 *v68; // rcx
  signed int v69; // eax
  unsigned __int8 *v70; // rax
  __int64 v71; // rcx
  __int128 v72; // xmm1
  __int128 *p_pDataIn; // rax
  unsigned __int8 *v74; // rax
  struct _GUID *v75; // rcx
  __int128 v76; // xmm1
  __int128 v77; // xmm0
  unsigned __int8 *v78; // rax
  __int128 v79; // xmm1
  unsigned int *v80; // rax
  unsigned __int8 **v81; // rcx
  unsigned __int8 *v82; // rdi
  __int128 *v83; // rax
  struct CDplKeyPair **v84; // rcx
  struct CDplKeyPair *v85; // rax
  void *v86; // rdi
  HANDLE ProcessHeap; // rax
  char bIgnoreCase; // [rsp+28h] [rbp-E0h]
  char bIgnoreCasea; // [rsp+28h] [rbp-E0h]
  char bIgnoreCaseb; // [rsp+28h] [rbp-E0h]
  char bIgnoreCasec; // [rsp+28h] [rbp-E0h]
  unsigned int bIgnoreCased; // [rsp+28h] [rbp-E0h]
  unsigned int v94; // [rsp+38h] [rbp-D0h]
  unsigned int v95; // [rsp+48h] [rbp-C0h]
  unsigned __int8 *v96; // [rsp+68h] [rbp-A0h]
  unsigned __int8 *v97; // [rsp+70h] [rbp-98h] BYREF
  CDplUser *v98; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 *v99; // [rsp+80h] [rbp-88h] BYREF
  struct CDplKeyPair **v100; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v101; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v102; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int8 *v103; // [rsp+A0h] [rbp-68h] BYREF
  int v104; // [rsp+A8h] [rbp-60h] BYREF
  int v105; // [rsp+ACh] [rbp-5Ch] BYREF
  unsigned int v106; // [rsp+B0h] [rbp-58h] BYREF
  unsigned int v107; // [rsp+B4h] [rbp-54h] BYREF
  unsigned int v108; // [rsp+B8h] [rbp-50h] BYREF
  unsigned int v109; // [rsp+BCh] [rbp-4Ch] BYREF
  int v110; // [rsp+C0h] [rbp-48h]
  CDplServiceImpl *v111; // [rsp+C8h] [rbp-40h]
  unsigned __int16 *v112; // [rsp+D0h] [rbp-38h] BYREF
  int v113; // [rsp+D8h] [rbp-30h]
  LPCWCH lpString2; // [rsp+E0h] [rbp-28h]
  unsigned __int8 *v115; // [rsp+E8h] [rbp-20h] BYREF
  void *v116; // [rsp+F0h] [rbp-18h] BYREF
  LPCWCH v117; // [rsp+F8h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+100h] [rbp-8h]
  unsigned __int8 *v119; // [rsp+108h] [rbp+0h]
  struct _GUID *v120; // [rsp+110h] [rbp+8h]
  unsigned __int8 *v121; // [rsp+118h] [rbp+10h]
  unsigned __int8 *v122; // [rsp+120h] [rbp+18h]
  struct _GUID *v123; // [rsp+128h] [rbp+20h]
  unsigned int *v124; // [rsp+130h] [rbp+28h]
  unsigned int *v125; // [rsp+138h] [rbp+30h]
  unsigned __int8 **v126; // [rsp+140h] [rbp+38h]
  unsigned __int16 *v127; // [rsp+148h] [rbp+40h] BYREF
  unsigned __int16 *v128; // [rsp+150h] [rbp+48h]
  LPCWCH v129; // [rsp+158h] [rbp+50h]
  unsigned __int8 *v130; // [rsp+160h] [rbp+58h]
  unsigned int *v131; // [rsp+168h] [rbp+60h]
  struct _GUID v132; // [rsp+170h] [rbp+68h] BYREF
  __int128 pDataIn; // [rsp+180h] [rbp+78h] BYREF
  __int128 v134; // [rsp+190h] [rbp+88h]
  __int128 Buf2; // [rsp+1A0h] [rbp+98h] BYREF
  __int128 v136; // [rsp+1B0h] [rbp+A8h]
  unsigned __int8 v137[16]; // [rsp+1C0h] [rbp+B8h] BYREF
  __int128 v138; // [rsp+1D0h] [rbp+C8h]

  v129 = a5;
  v120 = a10;
  v111 = this;
  v125 = a16;
  v126 = a15;
  v124 = a18;
  v123 = a17;
  v131 = a19;
  lpString2 = a4;
  v122 = a21;
  v128 = a7;
  v119 = a8;
  v121 = a20;
  v130 = a22;
  v116 = 0;
  v104 = 1;
  v113 = 0;
  lpMem = 0;
  v99 = 0;
  v127 = 0;
  v112 = 0;
  v117 = 0;
  v106 = 0;
  v105 = 0;
  v98 = 0;
  v100 = 0;
  v102 = 0;
  v96 = 0;
  v115 = 0;
  v107 = 0;
  v132 = 0;
  v109 = 0;
  v103 = 0;
  v101 = 0;
  v97 = 0;
  v108 = 0;
  v110 = 0;
  Buf2 = 0;
  v136 = 0;
  *(_OWORD *)v137 = 0;
  v138 = 0;
  pDataIn = 0;
  v134 = 0;
  fnEfsLogTrace1Strings(0, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 37, 21);
  if ( a15 )
    *v126 = 0;
  v25 = v125;
  if ( v125 )
    *v125 = 0;
  v26 = v123;
  if ( v123 )
    *v123 = 0;
  v27 = v124;
  if ( v124 )
    *v124 = -1;
  if ( a20 )
  {
    *(_OWORD *)a20 = 0;
    *((_OWORD *)a20 + 1) = 0;
  }
  v28 = v122;
  if ( v122 )
  {
    *(_OWORD *)v122 = 0;
    *((_OWORD *)v28 + 1) = 0;
  }
  if ( a22 )
  {
    *(_OWORD *)a22 = 0;
    *((_OWORD *)a22 + 1) = 0;
  }
  v29 = 32;
  if ( !a2 )
  {
    bIgnoreCase = 48;
LABEL_17:
    AppHash = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 37, bIgnoreCase);
LABEL_146:
    v44 = v99;
    goto LABEL_147;
  }
  if ( !a3 )
  {
    bIgnoreCase = 49;
    goto LABEL_17;
  }
  if ( !a4 )
  {
    bIgnoreCase = 50;
    goto LABEL_17;
  }
  if ( !a7 )
  {
    bIgnoreCase = 51;
    goto LABEL_17;
  }
  if ( !Buf1 )
  {
    bIgnoreCase = 52;
    goto LABEL_17;
  }
  if ( !a14 )
  {
    bIgnoreCasea = 53;
LABEL_143:
    AppHash = -2147024809;
    v31 = -2147024809;
    goto LABEL_144;
  }
  if ( !a15 )
  {
    bIgnoreCasea = 54;
LABEL_30:
    AppHash = -2147467261;
    v31 = -2147467261;
LABEL_144:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v31, 37, bIgnoreCasea);
    goto LABEL_145;
  }
  if ( !v25 )
  {
    bIgnoreCasea = 55;
    goto LABEL_30;
  }
  if ( !v26 )
  {
    bIgnoreCasea = 56;
    goto LABEL_30;
  }
  if ( !v27 )
  {
    bIgnoreCasea = 57;
    goto LABEL_30;
  }
  if ( !v121 )
  {
    bIgnoreCasea = 58;
    goto LABEL_30;
  }
  if ( !v28 )
  {
    bIgnoreCasea = 59;
    goto LABEL_30;
  }
  if ( !a22 )
  {
    bIgnoreCasea = 60;
    goto LABEL_30;
  }
  if ( (a8 == 0) != (Size == 0) )
  {
    bIgnoreCasea = 61;
    goto LABEL_143;
  }
  v32 = a11;
  if ( (v120 == 0) != (a11 == -1) )
  {
    bIgnoreCasea = 62;
    goto LABEL_143;
  }
  v33 = 0;
  while ( a6 != *((_DWORD *)&gc_ConsumerAccountLevelList + v33) )
  {
    v33 = (unsigned int)(v33 + 1);
    if ( (unsigned int)v33 >= 2 )
    {
      if ( a6 != -1 )
      {
        bIgnoreCasea = 64;
        goto LABEL_143;
      }
      break;
    }
  }
  v34 = CompareStringOrdinal(a3, -1, lpString2, -1, 1);
  if ( !v34 )
  {
    LastError = GetLastError();
    AppHash = LastError;
    if ( LastError > 0 )
      AppHash = (unsigned __int16)LastError | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, AppHash, 37, 73);
    goto LABEL_145;
  }
  if ( v34 != 2 )
  {
    bIgnoreCasea = 77;
    goto LABEL_143;
  }
  fnEfsLogTrace1Strings(v35, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 80);
  AppHash = CDplServiceImpl::RevertToSelf(v111, &v116);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              AppHash,
              37,
              80) < 0 )
    goto LABEL_145;
  if ( !(unsigned int)EfsDplAppKeyCachingFeatureEnabled(&v104) )
  {
    bIgnoreCasea = 87;
LABEL_59:
    AppHash = -2147024846;
    v31 = -2147024846;
    goto LABEL_144;
  }
  fnEfsLogTrace1Strings(v37, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 94);
  AppHash = EfsResolveProcessInfo(a2);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              AppHash,
              37,
              94) < 0 )
    goto LABEL_145;
  v38 = (const unsigned __int16 *)lpMem;
  if ( !lpMem )
  {
    bIgnoreCasea = 95;
    goto LABEL_59;
  }
  CDplServiceImpl::RestoreImpersonation(v111, &v116);
  fnEfsLogTrace1Strings(v39, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 103);
  v40 = v128;
  AppHash = CDplServiceImpl::MakeAppHash(v111, v128, v38, (unsigned __int8 *)&Buf2, v137);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              AppHash,
              37,
              103) < 0 )
    goto LABEL_145;
  if ( v119 && (memcmp_0(Buf1, &Buf2, 0x20u) || memcmp_0(a14, v137, 0x20u)) )
  {
    bIgnoreCasea = 113;
    goto LABEL_143;
  }
  fnEfsLogTrace1Strings(v41, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 126);
  v42 = v111;
  AppHash = CDplServiceImpl::EdpProtectorParse(v111, v40, &v99, &v127, &v112, (unsigned __int16 **)&v117, &v106, &v105);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              AppHash,
              37,
              126) < 0 )
  {
LABEL_145:
    v29 = 32;
    goto LABEL_146;
  }
  v43 = v105;
  if ( v105 && (a6 == -1 || a6 != v106) )
  {
    bIgnoreCasea = -123;
    goto LABEL_143;
  }
  v44 = v99;
  v45 = v99 == 0;
  if ( v45 != (v129 == 0) || v129 && CompareStringOrdinal(v99, -1, v129, -1, 1) != 2 )
  {
    AppHash = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 37, 137);
    goto LABEL_82;
  }
  v46 = v119;
  if ( !v119 )
  {
    v47 = CompareStringOrdinal(lpString2, -1, v117, -1, 1);
    if ( !v47 )
    {
      v48 = GetLastError();
      AppHash = v48;
      if ( v48 > 0 )
        AppHash = (unsigned __int16)v48 | 0x80070000;
      bIgnoreCaseb = -107;
      v49 = AppHash;
      goto LABEL_81;
    }
    if ( v47 != 2 )
    {
      bIgnoreCaseb = -98;
LABEL_85:
      AppHash = -2147024891;
      v49 = -2147024891;
LABEL_81:
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v49, 37, bIgnoreCaseb);
LABEL_82:
      v29 = 32;
LABEL_147:
      v52 = (PSID *)v98;
      goto LABEL_148;
    }
  }
  fnEfsLogTrace1Strings(v45, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 166);
  AppHash = CDplServiceImpl::FindUser(v42, lpString2, v43, &v98);
  v50 = fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
          (unsigned int)&sourceString,
          AppHash,
          37,
          166);
  v52 = (PSID *)v98;
  if ( v50 < 0 )
  {
LABEL_92:
    v29 = 32;
LABEL_148:
    v64 = v97;
    goto LABEL_149;
  }
  if ( !v98 )
  {
    if ( AppHash != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v51);
    AppHash = -2147024891;
    bIgnoreCasec = -84;
    v53 = -2147024891;
    goto LABEL_91;
  }
  if ( AppHash )
    MicrosoftTelemetryAssertTriggeredNoArgs(v51);
  fnEfsLogTrace1Strings(v51, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 182);
  AppHash = CDplUser::CheckCaller(v52);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              AppHash,
              37,
              182) < 0 )
    goto LABEL_92;
  fnEfsLogTrace1Strings(v54, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 188);
  AppHash = CDplUser::LoadDplAccountsAndPolicies((CDplUser *)v52, v112);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              AppHash,
              37,
              188) < 0 )
    goto LABEL_92;
  v110 = CDplUser::UserSvcLock((CDplUser *)v52);
  fnEfsLogTrace1Strings(v55, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 205);
  AppHash = CDplUser::EnumRefEnterpriseCredentials(
              (CDplUser *)v52,
              v44,
              (const unsigned __int16 *)0xFFFFFFFFFFFFFFFFLL,
              v112,
              a6,
              v46,
              Size,
              0,
              &v100,
              0,
              &v102);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              AppHash,
              37,
              205) < 0 )
    goto LABEL_92;
  if ( AppHash == 1 )
  {
    if ( v100 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v56);
    AppHash = -2147024894;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024894, 37, 216);
    goto LABEL_92;
  }
  if ( v102 != 1 )
  {
    bIgnoreCasec = -37;
    goto LABEL_135;
  }
  if ( !v100 )
  {
    bIgnoreCasec = -36;
    goto LABEL_135;
  }
  if ( !*v100 )
  {
    bIgnoreCasec = -35;
    goto LABEL_135;
  }
  v57 = *((_QWORD *)*v100 + 3);
  if ( !v57 )
  {
    bIgnoreCasec = -34;
    goto LABEL_135;
  }
  if ( *(_DWORD *)(v57 + 144) )
  {
    bIgnoreCasec = -33;
LABEL_135:
    AppHash = -2147418113;
    v53 = -2147418113;
LABEL_91:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v53, 37, bIgnoreCasec);
    goto LABEL_92;
  }
  fnEfsLogTrace1Strings(v56, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 231);
  AppHash = CDplKeyPair::UnprotectKdfKey(*v100);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              AppHash,
              37,
              231) < 0 )
    goto LABEL_92;
  fnEfsLogTrace1Strings(v58, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 237);
  AppHash = CDplKeyPair::GetKeyID(*v100, &v115, &v107);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              AppHash,
              37,
              237) < 0 )
  {
    v82 = v115;
    v29 = 32;
    v64 = v97;
    goto LABEL_150;
  }
  v60 = v107;
  v96 = v115;
  if ( v46 )
  {
    if ( Size != v107 || memcmp_0(v46, v115, Size) || (v61 = a12, a12 != *((unsigned __int16 *)*v100 + 82)) )
    {
      bIgnoreCaseb = -9;
      goto LABEL_85;
    }
    fnEfsLogTrace1Strings((unsigned int)*v100, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 0);
    v62 = v120;
    AppHash = CDplKeyPair::GetKdfUnprotectionKey(*v100, a12, v120, a11, 0, 0, &v103, &v101);
    v64 = v97;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                AppHash,
                37,
                0) >= 0 )
    {
      v65 = *v62;
      goto LABEL_121;
    }
LABEL_132:
    v52 = (PSID *)v98;
    v29 = 32;
LABEL_149:
    v82 = v96;
    goto LABEL_150;
  }
  fnEfsLogTrace1Strings(v59, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 17);
  AppHash = CDplKeyPair::GetKdfProtectionKey(*v100, &v132, &v109, &v97, &v108, &v103, &v101);
  v66 = fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
          (unsigned int)&sourceString,
          AppHash,
          37,
          17);
  v64 = v97;
  if ( v66 < 0 )
    goto LABEL_132;
  if ( v97 || v108 || (v32 = v109) != 0 )
  {
    AppHash = -2147024891;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024891, 37, 20);
    goto LABEL_132;
  }
  v65 = v132;
  v63 = *v100;
  v61 = *((unsigned __int16 *)*v100 + 82);
LABEL_121:
  fnEfsLogTrace1Strings((_DWORD)v63, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 37);
  AppHash = CDplKeyPair::DeriveKey(
              *v100,
              v103,
              v101,
              (const unsigned __int8 *)&Buf2,
              bIgnoreCased,
              v137,
              v94,
              (unsigned __int8 *)&pDataIn,
              v95);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              AppHash,
              37,
              37) < 0 )
    goto LABEL_132;
  v67 = v101;
  v68 = v103;
  if ( v101 )
  {
    do
    {
      *v68++ = 0;
      --v67;
    }
    while ( v67 );
  }
  v29 = 32;
  if ( !CryptProtectMemory(&pDataIn, 0x20u, 1u) )
  {
    v69 = GetLastError();
    AppHash = v69;
    if ( v69 > 0 )
      AppHash = (unsigned __int16)v69 | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, AppHash, 37, 46);
    v52 = (PSID *)v98;
    goto LABEL_149;
  }
  v70 = v130;
  v71 = 32;
  v72 = v134;
  *(_OWORD *)v130 = pDataIn;
  *((_OWORD *)v70 + 1) = v72;
  p_pDataIn = &pDataIn;
  do
  {
    *(_BYTE *)p_pDataIn = 0;
    p_pDataIn = (__int128 *)((char *)p_pDataIn + 1);
    --v71;
  }
  while ( v71 );
  v74 = v121;
  v75 = v123;
  v76 = v136;
  *(_OWORD *)v121 = Buf2;
  v77 = *(_OWORD *)v137;
  *((_OWORD *)v74 + 1) = v76;
  v78 = v122;
  v79 = v138;
  *(_OWORD *)v122 = v77;
  *((_OWORD *)v78 + 1) = v79;
  v80 = v124;
  *v75 = v65;
  v81 = v126;
  *v80 = v32;
  *v131 = v61;
  v82 = 0;
  *v125 = v60;
  v52 = (PSID *)v98;
  *v81 = v96;
LABEL_150:
  v83 = &pDataIn;
  do
  {
    *(_BYTE *)v83 = 0;
    v83 = (__int128 *)((char *)v83 + 1);
    --v29;
  }
  while ( v29 );
  if ( v103 )
    DplibMemFree(v103);
  v103 = 0;
  if ( v52 )
    CDplUser::UserSvcUnlock((CDplUser *)v52, v110);
  CDplServiceImpl::RestoreImpersonation(v111, &v116);
  if ( v64 )
    DplibMemFree(v64);
  if ( v117 )
    DplibMemFree((void *)v117);
  if ( v44 )
    DplibMemFree(v44);
  if ( v127 )
    DplibMemFree(v127);
  if ( v112 )
    DplibMemFree(v112);
  if ( v82 )
    DplibMemFree(v82);
  v84 = v100;
  if ( v100 )
  {
    while ( v102 )
    {
      v85 = (struct CDplKeyPair *)ReleaseIf<CDplKeyPair>(v84[--v102]);
      v100[v102] = v85;
      v84 = v100;
    }
    v102 = -1;
    if ( v84 )
      DplibMemFree(v84);
    v100 = 0;
  }
  ReleaseIf<CDplUser>(v52);
  v86 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v86);
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    AppHash,
    37,
    101);
  return AppHash;
}

```

## disassembly

```asm
0x180090228  mov     rax, rsp
0x18009022b  push    rbp
0x18009022c  push    rbx
0x18009022d  push    rsi
0x18009022e  push    rdi
0x18009022f  push    r12
0x180090231  push    r13
0x180090233  push    r14
0x180090235  push    r15
0x180090237  lea     rbp, [rax-138h]
0x18009023e  sub     rsp, 1F8h
0x180090245  movaps  xmmword ptr [rax-58h], xmm6
0x180090249  mov     rax, cs:__security_cookie
0x180090250  xor     rax, rsp
0x180090253  mov     qword ptr [rbp+130h+var_58], rax
0x18009025a  mov     rax, [rbp+130h+arg_20]
0x180090261  xorps   xmm0, xmm0
0x180090264  mov     rsi, [rbp+130h+arg_30]
0x18009026b  xorps   xmm1, xmm1
0x18009026e  mov     r15, [rbp+130h+arg_38]
0x180090275  mov     rdi, r9
0x180090278  mov     r14, [rbp+130h+arg_98]
0x18009027f  mov     rbx, r8
0x180090282  mov     r13, [rbp+130h+arg_A8]
0x180090289  lea     r8, sourceString
0x180090290  mov     [rbp+130h+var_E0], rax
0x180090294  mov     r12, rdx
0x180090297  mov     rax, [rbp+130h+arg_48]
0x18009029e  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800902a5  mov     [rbp+130h+var_128], rax
0x1800902a9  mov     rax, [rbp+130h+arg_78]
0x1800902b0  mov     [rbp+130h+var_170], rcx
0x1800902b4  mov     rcx, [rbp+130h+arg_70]
0x1800902bb  mov     [rbp+130h+var_100], rax
0x1800902bf  mov     rax, [rbp+130h+arg_88]
0x1800902c6  mov     [rbp+130h+var_F8], rcx
0x1800902ca  mov     rcx, [rbp+130h+arg_80]
0x1800902d1  mov     [rbp+130h+var_108], rax
0x1800902d5  mov     rax, [rbp+130h+arg_90]
0x1800902dc  mov     [rbp+130h+var_110], rcx
0x1800902e0  xor     ecx, ecx
0x1800902e2  mov     [rbp+130h+var_D0], rax
0x1800902e6  mov     rax, [rbp+130h+arg_A0]
0x1800902ed  mov     [rbp+130h+lpString2], r9
0x1800902f1  lea     r9d, [rcx+25h]
0x1800902f5  mov     [rbp+130h+var_118], rax
0x1800902f9  mov     [rbp+130h+var_E8], rsi
0x1800902fd  mov     [rbp+130h+var_130], r15
0x180090301  mov     [rbp+130h+var_120], r14
0x180090305  mov     [rbp+130h+var_D8], r13
0x180090309  mov     [rbp+130h+var_148], rcx
0x18009030d  mov     [rbp+130h+var_190], 1
0x180090314  mov     [rbp+130h+var_160], ecx
0x180090317  mov     [rbp+130h+lpMem], rcx
0x18009031b  mov     [rsp+230h+var_1B8], rcx
0x180090320  mov     [rbp+130h+var_F0], rcx
0x180090324  mov     [rbp+130h+var_168], rcx
0x180090328  mov     [rbp+130h+var_140], rcx
0x18009032c  mov     [rbp+130h+var_188], ecx
0x18009032f  mov     [rbp+130h+var_18C], ecx
0x180090332  mov     [rsp+230h+var_1C0], rcx
0x180090337  mov     [rbp+130h+var_1B0], rcx
0x18009033b  mov     [rbp+130h+var_1A0], rcx
0x18009033f  mov     [rsp+230h+var_1D0], rcx
0x180090344  mov     [rbp+130h+var_150], rcx
0x180090348  mov     [rbp+130h+var_184], ecx
0x18009034b  movups  xmmword ptr [rbp+130h+var_C8.Data1], xmm0
0x18009034f  mov     [rbp+130h+var_17C], ecx
0x180090352  mov     [rbp+130h+var_198], rcx
0x180090356  mov     [rbp+130h+var_1A8], ecx
0x180090359  mov     [rsp+230h+var_1C8], rcx
0x18009035e  mov     [rbp+130h+var_180], ecx
0x180090361  mov     [rbp+130h+var_178], ecx
0x180090364  movups  [rbp+130h+Buf2], xmm0
0x18009036b  mov     [rsp+230h+bIgnoreCase], 1915h
0x180090373  movups  [rbp+130h+var_88], xmm0
0x18009037a  movups  xmmword ptr [rbp+130h+var_78], xmm1
0x180090381  movups  [rbp+130h+var_68], xmm1
0x180090388  movups  [rbp+130h+pDataIn], xmm0
0x18009038c  movups  [rbp+130h+var_A8], xmm0
0x180090393  call    fnEfsLogTrace1Strings
0x180090398  mov     r9, [rbp+130h+var_F8]
0x18009039c  test    r9, r9
0x18009039f  jz      short loc_1800903A6
0x1800903a1  xor     eax, eax
0x1800903a3  mov     [r9], rax
0x1800903a6  mov     rcx, [rbp+130h+var_100]
0x1800903aa  test    rcx, rcx
0x1800903ad  jz      short loc_1800903B3
0x1800903af  xor     eax, eax
0x1800903b1  mov     [rcx], eax
0x1800903b3  mov     rdx, [rbp+130h+var_110]
0x1800903b7  test    rdx, rdx
0x1800903ba  jz      short loc_1800903C2
0x1800903bc  xorps   xmm0, xmm0
0x1800903bf  movups  xmmword ptr [rdx], xmm0
0x1800903c2  mov     r8, [rbp+130h+var_108]
0x1800903c6  or      r10d, 0FFFFFFFFh
0x1800903ca  test    r8, r8
0x1800903cd  jz      short loc_1800903D2
0x1800903cf  mov     [r8], r10d
0x1800903d2  test    r14, r14
0x1800903d5  jz      short loc_1800903E3
0x1800903d7  xorps   xmm0, xmm0
0x1800903da  movups  xmmword ptr [r14], xmm0
0x1800903de  movups  xmmword ptr [r14+10h], xmm0
0x1800903e3  mov     rax, [rbp+130h+var_118]
0x1800903e7  test    rax, rax
0x1800903ea  jz      short loc_1800903F6
0x1800903ec  xorps   xmm0, xmm0
0x1800903ef  movups  xmmword ptr [rax], xmm0
0x1800903f2  movups  xmmword ptr [rax+10h], xmm0
0x1800903f6  test    r13, r13
0x1800903f9  jz      short loc_180090408
0x1800903fb  xorps   xmm0, xmm0
0x1800903fe  movups  xmmword ptr [r13+0], xmm0
0x180090403  movups  xmmword ptr [r13+10h], xmm0
0x180090408  mov     r14d, 20h ; ' '
0x18009040e  test    r12, r12
0x180090411  jnz     short loc_180090444
0x180090413  mov     [rsp+230h+bIgnoreCase], 1930h
0x18009041b  mov     rcx, cs:g_hPublisher
0x180090422  lea     rdx, EFS_TRACE_ERROR
0x180090429  mov     r9d, 25h ; '%'
0x18009042f  mov     r8d, 80070057h
0x180090435  mov     ebx, 80070057h
0x18009043a  call    fnEfsLogTrace1
0x18009043f  jmp     loc_180091142
0x180090444  test    rbx, rbx
0x180090447  jnz     short loc_180090453
0x180090449  mov     [rsp+230h+bIgnoreCase], 1931h
0x180090451  jmp     short loc_18009041B
0x180090453  test    rdi, rdi
0x180090456  jnz     short loc_180090462
0x180090458  mov     [rsp+230h+bIgnoreCase], 1932h
0x180090460  jmp     short loc_18009041B
0x180090462  test    rsi, rsi
0x180090465  jnz     short loc_180090471
0x180090467  mov     [rsp+230h+bIgnoreCase], 1933h
0x18009046f  jmp     short loc_18009041B
0x180090471  mov     rsi, [rbp+130h+Buf1]
0x180090478  test    rsi, rsi
0x18009047b  jnz     short loc_180090487
0x18009047d  mov     [rsp+230h+bIgnoreCase], 1934h
0x180090485  jmp     short loc_18009041B
0x180090487  mov     r14, [rbp+130h+arg_68]
0x18009048e  test    r14, r14
0x180090491  jnz     short loc_1800904A0
0x180090493  mov     [rsp+230h+bIgnoreCase], 1935h
0x18009049b  jmp     loc_180091118
0x1800904a0  test    r9, r9
0x1800904a3  jnz     short loc_1800904C3
0x1800904a5  mov     [rsp+230h+bIgnoreCase], 1936h
0x1800904ad  mov     ebx, 80004003h
0x1800904b2  mov     r9d, 25h ; '%'
0x1800904b8  mov     r8d, 80004003h
0x1800904be  jmp     loc_180091129
0x1800904c3  test    rcx, rcx
0x1800904c6  jnz     short loc_1800904D2
0x1800904c8  mov     [rsp+230h+bIgnoreCase], 1937h
0x1800904d0  jmp     short loc_1800904AD
0x1800904d2  test    rdx, rdx
0x1800904d5  jnz     short loc_1800904E1
0x1800904d7  mov     [rsp+230h+bIgnoreCase], 1938h
0x1800904df  jmp     short loc_1800904AD
0x1800904e1  test    r8, r8
0x1800904e4  jnz     short loc_1800904F0
0x1800904e6  mov     [rsp+230h+bIgnoreCase], 1939h
0x1800904ee  jmp     short loc_1800904AD
0x1800904f0  cmp     [rbp+130h+var_120], 0
0x1800904f5  jnz     short loc_180090501
0x1800904f7  mov     [rsp+230h+bIgnoreCase], 193Ah
0x1800904ff  jmp     short loc_1800904AD
0x180090501  test    rax, rax
0x180090504  jnz     short loc_180090510
0x180090506  mov     [rsp+230h+bIgnoreCase], 193Bh
0x18009050e  jmp     short loc_1800904AD
0x180090510  test    r13, r13
0x180090513  jnz     short loc_18009051F
0x180090515  mov     [rsp+230h+bIgnoreCase], 193Ch
0x18009051d  jmp     short loc_1800904AD
0x18009051f  xor     ecx, ecx
0x180090521  test    r15, r15
0x180090524  mov     r15d, dword ptr [rbp+130h+Size]
0x18009052b  setz    cl
0x18009052e  xor     eax, eax
0x180090530  test    r15d, r15d
0x180090533  setz    al
0x180090536  cmp     ecx, eax
0x180090538  jnz     loc_180091110
0x18009053e  mov     r13d, [rbp+130h+arg_50]
0x180090545  xor     ecx, ecx
0x180090547  cmp     [rbp+130h+var_128], rcx
0x18009054b  setz    cl
0x18009054e  xor     eax, eax
0x180090550  cmp     r13d, r10d
0x180090553  setz    al
0x180090556  cmp     ecx, eax
0x180090558  jnz     loc_180091106
0x18009055e  mov     edi, [rbp+130h+arg_28]
0x180090564  xor     ecx, ecx
0x180090566  lea     rdx, gc_ConsumerAccountLevelList
0x18009056d  cmp     edi, [rdx+rcx*4]
0x180090570  jz      short loc_18009058B
0x180090572  inc     ecx
0x180090574  cmp     ecx, 2
0x180090577  jb      short loc_180090566
0x180090579  cmp     edi, r10d
0x18009057c  jz      short loc_18009058B
0x18009057e  mov     [rsp+230h+bIgnoreCase], 1940h
0x180090586  jmp     loc_180091118
0x18009058b  mov     r8, [rbp+130h+lpString2]; lpString2
0x18009058f  or      r9d, 0FFFFFFFFh; cchCount2
0x180090593  or      edx, r9d; cchCount1
0x180090596  mov     [rsp+230h+bIgnoreCase], 1; bIgnoreCase
0x18009059e  mov     rcx, rbx; lpString1
0x1800905a1  call    cs:__imp_CompareStringOrdinal
0x1800905a7  test    eax, eax
0x1800905a9  jnz     short loc_1800905D6
0x1800905ab  call    cs:__imp_GetLastError
0x1800905b1  mov     ebx, eax
0x1800905b3  test    eax, eax
0x1800905b5  jle     short loc_1800905C0
0x1800905b7  movzx   ebx, ax
0x1800905ba  or      ebx, 80070000h
0x1800905c0  mov     [rsp+230h+bIgnoreCase], 1949h
0x1800905c8  mov     r9d, 25h ; '%'
0x1800905ce  mov     r8d, ebx
0x1800905d1  jmp     loc_180091129
0x1800905d6  mov     r9d, 25h ; '%'
0x1800905dc  cmp     eax, 2
0x1800905df  jz      short loc_1800905EE
0x1800905e1  mov     [rsp+230h+bIgnoreCase], 194Dh
0x1800905e9  jmp     loc_18009111E
0x1800905ee  lea     r8, sourceString
0x1800905f5  mov     [rsp+230h+bIgnoreCase], 1950h
0x1800905fd  lea     rdx, EFS_TRACE_START_EVENT
0x180090604  call    fnEfsLogTrace1Strings
0x180090609  mov     rcx, [rbp+130h+var_170]; this
0x18009060d  lea     rdx, [rbp+130h+var_148]; void **
0x180090611  call    ?RevertToSelf@CDplServiceImpl@@AEAAJPEAPEAX@Z; CDplServiceImpl::RevertToSelf(void * *)
0x180090616  mov     rcx, cs:g_hPublisher
0x18009061d  lea     r9, sourceString
0x180090624  mov     dword ptr [rsp+230h+var_200], 1950h
0x18009062c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180090633  mov     dword ptr [rsp+230h+var_208], 25h ; '%'
0x18009063b  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180090642  mov     [rsp+230h+bIgnoreCase], eax
0x180090646  mov     ebx, eax
0x180090648  call    fnEfsLogTrace1String1Dword
0x18009064d  test    eax, eax
0x18009064f  js      loc_18009113C
0x180090655  lea     rcx, [rbp+130h+var_190]
0x180090659  call    EfsDplAppKeyCachingFeatureEnabled
0x18009065e  mov     r9d, 25h ; '%'
0x180090664  test    eax, eax
0x180090666  jnz     short loc_180090680
0x180090668  mov     [rsp+230h+bIgnoreCase], 1957h
0x180090670  mov     ebx, 80070032h
0x180090675  mov     r8d, 80070032h
0x18009067b  jmp     loc_180091129
0x180090680  lea     r8, sourceString
0x180090687  mov     [rsp+230h+bIgnoreCase], 195Eh
0x18009068f  lea     rdx, EFS_TRACE_START_EVENT
0x180090696  call    fnEfsLogTrace1Strings
0x18009069b  mov     edx, [rbp+130h+var_190]
0x18009069e  lea     r9, [rbp+130h+lpMem]
0x1800906a2  lea     r8, [rbp+130h+var_160]
0x1800906a6  mov     rcx, r12; ProcessHandle
0x1800906a9  call    EfsResolveProcessInfo
0x1800906ae  mov     rcx, cs:g_hPublisher
0x1800906b5  lea     r9, sourceString
0x1800906bc  mov     dword ptr [rsp+230h+var_200], 195Eh
0x1800906c4  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800906cb  mov     r12d, 25h ; '%'
0x1800906d1  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800906d8  mov     dword ptr [rsp+230h+var_208], r12d
0x1800906dd  mov     ebx, eax
0x1800906df  mov     [rsp+230h+bIgnoreCase], eax
0x1800906e3  call    fnEfsLogTrace1String1Dword
0x1800906e8  test    eax, eax
0x1800906ea  js      loc_18009113C
0x1800906f0  mov     rbx, [rbp+130h+lpMem]
0x1800906f4  test    rbx, rbx
0x1800906f7  jnz     short loc_180090709
0x1800906f9  mov     [rsp+230h+bIgnoreCase], 195Fh
0x180090701  mov     r9d, r12d
0x180090704  jmp     loc_180090670
0x180090709  mov     rcx, [rbp+130h+var_170]; this
0x18009070d  lea     rdx, [rbp+130h+var_148]; void **
0x180090711  call    ?RestoreImpersonation@CDplServiceImpl@@AEAAXPEAPEAX@Z; CDplServiceImpl::RestoreImpersonation(void * *)
0x180090716  mov     r9d, r12d
0x180090719  mov     [rsp+230h+bIgnoreCase], 1967h
0x180090721  lea     r8, sourceString
0x180090728  lea     rdx, EFS_TRACE_START_EVENT
0x18009072f  call    fnEfsLogTrace1Strings
0x180090734  mov     r12, [rbp+130h+var_E8]
0x180090738  lea     rax, [rbp+130h+var_78]
0x18009073f  mov     rcx, [rbp+130h+var_170]; this
0x180090743  lea     r9, [rbp+130h+Buf2]; unsigned __int8 *
  ... truncated ...
```
