# RefsUpdateDynamicRegistrySettings(void *)

- ea: `0x1402cead0`
- end: `0x1402d1191`
- name: `?RefsUpdateDynamicRegistrySettings@@_Y2PAGE@@AXPEAX@Z`
- size: `9921`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14034fc48`

## callees

- `0x14000b1b0`
- `0x14000e0e0`
- `0x140050ba0`
- `0x140075660`
- `0x1400862c0`
- `0x14009a130`
- `0x1400a069c`
- `0x1400cfa78`
- `0x1400d0fd8`
- `0x1400d2248`
- `0x1401f3fb0`
- `0x1402cead0`
- `0x1402fe258`
- `0x14032cd40`
- `0x140332720`
- `0x14033a7a8`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1402ced95`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1402ced95`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402ceda9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402ceda9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402d1157`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402d1157`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402cedc1`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402cee33`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402cedc1`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402cee33`
- `ntoskrnl!KdDebuggerEnabled` at `0x1402cf35d`
- `ntoskrnl!KdDebuggerEnabled` at `0x1402cf5ba`
- `ntoskrnl!KdDebuggerEnabled` at `0x1402cf69c`
- `ntoskrnl!KdDebuggerEnabled` at `0x1402cf77c`
- `ntoskrnl!ExReleaseFastResource` at `0x1402d0e0c`
- `ntoskrnl!ExReleaseFastResource` at `0x1402d1035`
- `ntoskrnl!ExReleaseFastResource` at `0x1402d114b`
- `ntoskrnl!ExReleaseFastResource` at `0x1402d0e0c`
- `ntoskrnl!ExReleaseFastResource` at `0x1402d1035`
- `ntoskrnl!ExReleaseFastResource` at `0x1402d114b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d1136`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d1136`
- `ntoskrnl!__imp_RtlIsFeatureEnabledForEnterprise` at `0x1402d07b7`
- `ntoskrnl!__imp_RtlIsFeatureEnabledForEnterprise` at `0x1402d07b7`

## string_xrefs

- `0x1402cedd9`: `\Registry\Machine\System\CurrentControlSet\Policies`
- `0x1402cedf1`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x1402cee4f`: `RefsDisableDeleteNotification`
- `0x1402cef1a`: `RefsFailIncompleteLogRedo`
- `0x1402cf38f`: `RefsDisableAsyncDelete`
- `0x1402cf454`: `RefsDisableLastAccessUpdate`
- `0x1402cfba0`: `DataDestageCompactionThreshold`
- `0x1402cfeaa`: `RefsContainerRotationThreadCount`
- `0x1402d03f0`: `RefsSmrUpdateSampleInterval`
- `0x1402d0651`: `RefsDisableTrueAsyncCachedReads`
- `0x1402d0c83`: `RefsMaxQueuedDecompressWorkItems`
- `0x1402d0d5e`: `EnforceDirectoryChangeNotificationPermissionCheck`

## pseudocode

```c
void __fastcall RefsUpdateDynamicRegistrySettings(void *a1)
{
  struct _TOP_LEVEL_CONTEXT *v1; // rdi
  int v2; // r14d
  struct _IRP_CONTEXT *v3; // r13
  __int64 v4; // r8
  int v5; // edx
  __int64 v6; // r8
  int v7; // edx
  unsigned int v8; // eax
  int v9; // eax
  char v10; // al
  char v11; // al
  int v12; // edx
  unsigned int v13; // edx
  int v14; // eax
  bool v15; // zf
  int v16; // eax
  unsigned int v17; // eax
  int v18; // eax
  unsigned int v19; // eax
  int v20; // eax
  unsigned int v21; // eax
  int v22; // eax
  unsigned int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned __int8 v33; // cl
  int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  int v45; // edx
  ULONG v46; // edx
  int v47; // edi
  BOOLEAN v48; // r8
  struct _DRIVE_LAYOUT_INFORMATION **v49; // r9
  int v50; // r14d
  unsigned int v51; // eax
  int v52; // eax
  int v53; // ecx
  char v54; // al
  unsigned int v55; // ecx
  unsigned int v56; // edx
  int v57; // ecx
  int v58; // edi
  unsigned int *v59; // rsi
  unsigned __int8 v60[4]; // [rsp+30h] [rbp-798h] BYREF
  int v61; // [rsp+34h] [rbp-794h]
  unsigned int v62; // [rsp+38h] [rbp-790h] BYREF
  PVOID P; // [rsp+40h] [rbp-788h] BYREF
  struct _UNICODE_STRING v64; // [rsp+48h] [rbp-780h] BYREF
  char v65; // [rsp+58h] [rbp-770h]
  char v66; // [rsp+59h] [rbp-76Fh]
  char v67; // [rsp+5Ah] [rbp-76Eh]
  unsigned __int8 v68; // [rsp+5Bh] [rbp-76Dh]
  char v69; // [rsp+5Ch] [rbp-76Ch]
  char v70; // [rsp+5Dh] [rbp-76Bh]
  char v71; // [rsp+5Eh] [rbp-76Ah]
  char v72; // [rsp+5Fh] [rbp-769h]
  char v73; // [rsp+60h] [rbp-768h]
  char v74; // [rsp+61h] [rbp-767h]
  char v75; // [rsp+62h] [rbp-766h]
  char v76; // [rsp+63h] [rbp-765h]
  char v77; // [rsp+64h] [rbp-764h]
  char v78; // [rsp+65h] [rbp-763h]
  char v79; // [rsp+66h] [rbp-762h]
  char v80; // [rsp+67h] [rbp-761h]
  char v81; // [rsp+68h] [rbp-760h]
  char v82; // [rsp+69h] [rbp-75Fh]
  char v83; // [rsp+6Ah] [rbp-75Eh]
  unsigned __int8 v84; // [rsp+6Bh] [rbp-75Dh]
  char v85; // [rsp+6Ch] [rbp-75Ch]
  char v86; // [rsp+6Dh] [rbp-75Bh]
  char v87; // [rsp+6Eh] [rbp-75Ah]
  char v88; // [rsp+6Fh] [rbp-759h]
  struct _UNICODE_STRING v89; // [rsp+70h] [rbp-758h] BYREF
  struct _UNICODE_STRING v90; // [rsp+80h] [rbp-748h] BYREF
  unsigned int v91; // [rsp+90h] [rbp-738h]
  unsigned int v92; // [rsp+94h] [rbp-734h]
  unsigned int v93; // [rsp+98h] [rbp-730h]
  int v94; // [rsp+9Ch] [rbp-72Ch]
  int v95; // [rsp+A0h] [rbp-728h]
  int v96; // [rsp+A4h] [rbp-724h]
  int v97; // [rsp+A8h] [rbp-720h]
  int v98; // [rsp+ACh] [rbp-71Ch]
  int v99; // [rsp+B0h] [rbp-718h]
  unsigned int v100; // [rsp+B4h] [rbp-714h]
  int v101; // [rsp+B8h] [rbp-710h]
  BOOL v102; // [rsp+BCh] [rbp-70Ch]
  unsigned int v103; // [rsp+C0h] [rbp-708h]
  int v104; // [rsp+C4h] [rbp-704h]
  int v105; // [rsp+C8h] [rbp-700h]
  int v106; // [rsp+CCh] [rbp-6FCh]
  unsigned int v107; // [rsp+D0h] [rbp-6F8h]
  unsigned int v108; // [rsp+D4h] [rbp-6F4h]
  unsigned int v109; // [rsp+D8h] [rbp-6F0h]
  unsigned int v110; // [rsp+DCh] [rbp-6ECh]
  unsigned int v111; // [rsp+E0h] [rbp-6E8h]
  unsigned int v112; // [rsp+E4h] [rbp-6E4h]
  unsigned int v113; // [rsp+E8h] [rbp-6E0h]
  unsigned int v114; // [rsp+ECh] [rbp-6DCh]
  int v115; // [rsp+F0h] [rbp-6D8h]
  int v116; // [rsp+F4h] [rbp-6D4h]
  int v117; // [rsp+F8h] [rbp-6D0h]
  int v118; // [rsp+FCh] [rbp-6CCh]
  int v119; // [rsp+100h] [rbp-6C8h]
  int v120; // [rsp+104h] [rbp-6C4h]
  int v121; // [rsp+108h] [rbp-6C0h]
  int v122; // [rsp+10Ch] [rbp-6BCh]
  unsigned int v123; // [rsp+110h] [rbp-6B8h]
  unsigned int v124; // [rsp+114h] [rbp-6B4h]
  BOOL v125; // [rsp+118h] [rbp-6B0h]
  int v126; // [rsp+11Ch] [rbp-6ACh]
  int v127; // [rsp+120h] [rbp-6A8h]
  int v128; // [rsp+124h] [rbp-6A4h]
  int v129; // [rsp+128h] [rbp-6A0h]
  int v130; // [rsp+12Ch] [rbp-69Ch]
  int v131; // [rsp+130h] [rbp-698h]
  struct _IRP_CONTEXT *v132; // [rsp+138h] [rbp-690h] BYREF
  int v133; // [rsp+140h] [rbp-688h]
  int v134; // [rsp+144h] [rbp-684h]
  int v135; // [rsp+148h] [rbp-680h] BYREF
  char v136; // [rsp+14Ch] [rbp-67Ch]
  _QWORD v137[2]; // [rsp+150h] [rbp-678h] BYREF
  int v138; // [rsp+160h] [rbp-668h]
  int v139; // [rsp+168h] [rbp-660h]
  const wchar_t *v140; // [rsp+170h] [rbp-658h]
  int v141; // [rsp+178h] [rbp-650h]
  const wchar_t *v142; // [rsp+180h] [rbp-648h]
  int v143; // [rsp+188h] [rbp-640h]
  const wchar_t *v144; // [rsp+190h] [rbp-638h]
  int v145; // [rsp+198h] [rbp-630h]
  const wchar_t *v146; // [rsp+1A0h] [rbp-628h]
  int v147; // [rsp+1A8h] [rbp-620h]
  const wchar_t *v148; // [rsp+1B0h] [rbp-618h]
  int v149; // [rsp+1B8h] [rbp-610h]
  const wchar_t *v150; // [rsp+1C0h] [rbp-608h]
  int v151; // [rsp+1C8h] [rbp-600h]
  const wchar_t *v152; // [rsp+1D0h] [rbp-5F8h]
  int v153; // [rsp+1D8h] [rbp-5F0h]
  const wchar_t *v154; // [rsp+1E0h] [rbp-5E8h]
  int v155; // [rsp+1E8h] [rbp-5E0h]
  const wchar_t *v156; // [rsp+1F0h] [rbp-5D8h]
  int v157; // [rsp+1F8h] [rbp-5D0h]
  const wchar_t *v158; // [rsp+200h] [rbp-5C8h]
  int v159; // [rsp+208h] [rbp-5C0h]
  const wchar_t *v160; // [rsp+210h] [rbp-5B8h]
  int v161; // [rsp+218h] [rbp-5B0h]
  const wchar_t *v162; // [rsp+220h] [rbp-5A8h]
  int v163; // [rsp+228h] [rbp-5A0h]
  const wchar_t *v164; // [rsp+230h] [rbp-598h]
  int v165; // [rsp+238h] [rbp-590h]
  const wchar_t *v166; // [rsp+240h] [rbp-588h]
  int v167; // [rsp+248h] [rbp-580h]
  const wchar_t *v168; // [rsp+250h] [rbp-578h]
  int v169; // [rsp+258h] [rbp-570h]
  const wchar_t *v170; // [rsp+260h] [rbp-568h]
  int v171; // [rsp+268h] [rbp-560h]
  const wchar_t *v172; // [rsp+270h] [rbp-558h]
  int v173; // [rsp+278h] [rbp-550h]
  const wchar_t *v174; // [rsp+280h] [rbp-548h]
  int v175; // [rsp+288h] [rbp-540h]
  const wchar_t *v176; // [rsp+290h] [rbp-538h]
  int v177; // [rsp+298h] [rbp-530h]
  const wchar_t *v178; // [rsp+2A0h] [rbp-528h]
  int v179; // [rsp+2A8h] [rbp-520h]
  const wchar_t *v180; // [rsp+2B0h] [rbp-518h]
  int v181; // [rsp+2B8h] [rbp-510h]
  const wchar_t *v182; // [rsp+2C0h] [rbp-508h]
  int v183; // [rsp+2C8h] [rbp-500h]
  const wchar_t *v184; // [rsp+2D0h] [rbp-4F8h]
  int v185; // [rsp+2D8h] [rbp-4F0h]
  const wchar_t *v186; // [rsp+2E0h] [rbp-4E8h]
  int v187; // [rsp+2E8h] [rbp-4E0h]
  const wchar_t *v188; // [rsp+2F0h] [rbp-4D8h]
  int v189; // [rsp+2F8h] [rbp-4D0h]
  const wchar_t *v190; // [rsp+300h] [rbp-4C8h]
  int v191; // [rsp+308h] [rbp-4C0h]
  const wchar_t *v192; // [rsp+310h] [rbp-4B8h]
  int v193; // [rsp+318h] [rbp-4B0h]
  const wchar_t *v194; // [rsp+320h] [rbp-4A8h]
  int v195; // [rsp+328h] [rbp-4A0h]
  const wchar_t *v196; // [rsp+330h] [rbp-498h]
  int v197; // [rsp+338h] [rbp-490h]
  const wchar_t *v198; // [rsp+340h] [rbp-488h]
  int v199; // [rsp+348h] [rbp-480h]
  const wchar_t *v200; // [rsp+350h] [rbp-478h]
  int v201; // [rsp+358h] [rbp-470h]
  const wchar_t *v202; // [rsp+360h] [rbp-468h]
  int v203; // [rsp+368h] [rbp-460h]
  const wchar_t *v204; // [rsp+370h] [rbp-458h]
  int v205; // [rsp+378h] [rbp-450h]
  const wchar_t *v206; // [rsp+380h] [rbp-448h]
  int v207; // [rsp+388h] [rbp-440h]
  const wchar_t *v208; // [rsp+390h] [rbp-438h]
  int v209; // [rsp+398h] [rbp-430h]
  const wchar_t *v210; // [rsp+3A0h] [rbp-428h]
  int v211; // [rsp+3A8h] [rbp-420h]
  const wchar_t *v212; // [rsp+3B0h] [rbp-418h]
  int v213; // [rsp+3B8h] [rbp-410h]
  const wchar_t *v214; // [rsp+3C0h] [rbp-408h]
  int v215; // [rsp+3C8h] [rbp-400h]
  const wchar_t *v216; // [rsp+3D0h] [rbp-3F8h]
  int v217; // [rsp+3D8h] [rbp-3F0h]
  const wchar_t *v218; // [rsp+3E0h] [rbp-3E8h]
  int v219; // [rsp+3E8h] [rbp-3E0h]
  const wchar_t *v220; // [rsp+3F0h] [rbp-3D8h]
  __int128 v221; // [rsp+3F8h] [rbp-3D0h] BYREF
  __int64 v222; // [rsp+408h] [rbp-3C0h]
  __int64 v223; // [rsp+410h] [rbp-3B8h] BYREF
  __int64 v224; // [rsp+6F0h] [rbp-D8h] BYREF

  v132 = (struct _IRP_CONTEXT *)&v223;
  v221 = 0;
  v222 = 0;
  v90 = 0;
  v89 = 0;
  v64 = 0;
  v62 = 156;
  P = &v224;
  v60[0] = 0;
  v95 = dword_1402688A4;
  v117 = dword_1402688A4;
  v96 = dword_1402688A8;
  v118 = dword_1402688A8;
  v101 = dword_1402688AC;
  v119 = dword_1402688AC;
  v97 = dword_1402688B0;
  v120 = dword_1402688B0;
  v98 = dword_1402688B4;
  v130 = dword_1402688B4;
  v99 = dword_1402688B8;
  v122 = dword_1402688B8;
  v68 = RefsEnableParallelContainerRotation;
  v84 = RefsEnableParallelContainerRotation;
  v100 = RefsContainerRotationQueueSizeLimit;
  v123 = RefsContainerRotationQueueSizeLimit;
  v103 = RefsContainerRotationThreadCount;
  v124 = RefsContainerRotationThreadCount;
  v102 = RefsFailIncompleteLogRedo != 0;
  v125 = v102;
  v126 = dword_140269054;
  v134 = dword_140269054;
  v91 = 0;
  v1 = RefsInitializeTopLevelIrp((struct _TOP_LEVEL_CONTEXT *)&v221, 0, 0);
  v2 = RefsInitializeIrpContext(0, 1, 0, &v132);
  if ( v2 < 0 )
    return;
  v67 = 0;
  v66 = 0;
  v86 = 0;
  v127 = 0;
  v128 = 0;
  v129 = 0;
  v104 = 1;
  v105 = 0;
  v106 = 0;
  v121 = 0;
  v107 = -1;
  v76 = 0;
  v108 = -1;
  v77 = 0;
  v109 = -1;
  v78 = 0;
  v110 = -1;
  v79 = 0;
  v111 = -1;
  v80 = 0;
  v112 = -1;
  v81 = 0;
  v113 = -1;
  v82 = 0;
  v114 = -1;
  v83 = 0;
  v94 = 1;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v69 = 0;
  v88 = 0;
  v87 = 0;
  v115 = 0;
  v93 = 0;
  v92 = 0;
  v116 = 100;
  v133 = 0;
  v85 = 0;
  v131 = 30000;
  v65 = 0;
  v3 = v132;
  if ( !*((_QWORD *)v1 + 2) )
  {
    *((_DWORD *)v1 + 1) = 1397140410;
    *((_QWORD *)v1 + 2) = v3;
    *((_QWORD *)v3 + 1) |= 0x100000uLL;
    IoSetTopLevelIrp((PIRP)v1);
  }
  *((_QWORD *)v3 + 13) = *((_QWORD *)v1 + 2);
  KeEnterCriticalRegion();
  LOBYTE(v4) = 1;
  ExAcquireFastResourceExclusive(&RefsDynamicRegistrySettingsResource, 0, v4);
  *(_QWORD *)&v90.Length = 6815846;
  v90.Buffer = (PWSTR)L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies";
  *(_QWORD *)&v89.Length = 8126586;
  v89.Buffer = (PWSTR)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem";
  do
  {
    if ( v2 == -1073741432 )
      RefsCheckpointForLogFileFull(v3);
    if ( v3 )
      RefsPreRequestProcessingExtend(v3, v5);
    LOBYTE(v6) = 1;
    ExAcquireFastResourceExclusive(qword_1402680F8, 0, v6);
    v67 = 1;
    v139 = 3932218;
    v140 = L"RefsDisableDeleteNotification";
    *(_QWORD *)&v64.Length = 3932218;
    v64.Buffer = L"RefsDisableDeleteNotification";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 < 0
      && (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 < 0) )
    {
      v7 = 0;
    }
    else
    {
      v7 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    if ( v7 == 1 )
    {
      if ( ((unsigned __int16)dword_1402682EC & 0x8000) == 0 )
      {
        v8 = (unsigned int)dword_1402682EC | 0x8000;
LABEL_18:
        LODWORD(dword_1402682EC) = v8;
        v66 = 1;
      }
    }
    else if ( ((unsigned __int16)dword_1402682EC & 0x8000) != 0 )
    {
      v8 = (unsigned int)dword_1402682EC & 0xFFFF7FFF;
      goto LABEL_18;
    }
    v141 = 3407922;
    v142 = L"RefsFailIncompleteLogRedo";
    *(_QWORD *)&v64.Length = 3407922;
    v64.Buffer = L"RefsFailIncompleteLogRedo";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v9 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v102 = v9;
      v125 = v9;
    }
    else
    {
      v9 = v102;
    }
    if ( v9 == 1 )
    {
      RefsFailIncompleteLogRedo = 1;
      v10 = 1;
    }
    else
    {
      RefsFailIncompleteLogRedo = 0;
      v10 = 0;
    }
    byte_140269011 = v10;
    v143 = 4456514;
    v144 = L"RefsEnableBreakOnChecksumMismatch";
    *(_QWORD *)&v64.Length = 4456514;
    v64.Buffer = L"RefsEnableBreakOnChecksumMismatch";
    v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0 && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
    {
      v11 = 1;
      RefsEnableBreakOnChecksumMismatch = 1;
    }
    else
    {
      v11 = 0;
      RefsEnableBreakOnChecksumMismatch = 0;
    }
    MsControl = v11;
    v145 = 3801144;
    v146 = L"RefsEnableMetadataValidation";
    *(_QWORD *)&v64.Length = 3801144;
    v64.Buffer = L"RefsEnableMetadataValidation";
    v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0 )
    {
      v12 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      LOBYTE(word_140268FD1) = v12 & 1;
      HIBYTE(word_140268FD1) = (v12 & 2) != 0;
    }
    v137[0] = 2883626;
    v137[1] = L"RefsDebugDisableFlags";
    RefsQueryValueKeyTyped<unsigned long>(&v135, &v89, v137);
    if ( v136 )
      dword_1402691A0 = v135;
    v147 = 3932218;
    v148 = L"RefsInvalidateOnFileLevelTrim";
    *(_QWORD *)&v64.Length = 3932218;
    v64.Buffer = L"RefsInvalidateOnFileLevelTrim";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 < 0
      && (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 < 0) )
    {
      v13 = 0;
    }
    else
    {
      v13 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    if ( dword_140268164 != (v13 < 3 ? v13 : 0) )
    {
      dword_140268164 = v13 < 3 ? v13 : 0;
      v86 = 1;
    }
    v149 = 2883626;
    v150 = L"EnableExtraIoAnalysis";
    *(_QWORD *)&v64.Length = 2883626;
    v64.Buffer = L"EnableExtraIoAnalysis";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v14 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v127 = v14;
    }
    else
    {
      LOBYTE(v14) = v127;
    }
    v15 = (v14 & 1) == 0;
    v16 = (int)dword_1402682EC;
    if ( v15 )
    {
      v17 = (unsigned int)dword_1402682EC & 0xFFFFFDFF;
    }
    else
    {
      LODWORD(dword_1402682EC) = (unsigned int)dword_1402682EC | 0x200;
      v17 = v16 | 0x600;
    }
    LODWORD(dword_1402682EC) = v17;
    v151 = 4718662;
    v152 = L"RefsEnableMetadataRetrievalPointers";
    *(_QWORD *)&v64.Length = 4718662;
    v64.Buffer = L"RefsEnableMetadataRetrievalPointers";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v18 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v128 = v18;
    }
    else
    {
      LOBYTE(v18) = v128;
    }
    if ( (v18 & 1) != 0 && (_BYTE)KdDebuggerEnabled )
      v19 = (unsigned int)dword_1402682EC | 0x20000;
    else
      v19 = (unsigned int)dword_1402682EC & 0xFFFDFFFF;
    LODWORD(dword_1402682EC) = v19;
    v153 = 3014700;
    v154 = L"RefsDisableAsyncDelete";
    *(_QWORD *)&v64.Length = 3014700;
    v64.Buffer = L"RefsDisableAsyncDelete";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v20 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v129 = v20;
    }
    else
    {
      LOBYTE(v20) = v129;
    }
    if ( (v20 & 1) != 0 )
      v21 = (unsigned int)dword_1402682EC & 0xFFDFFFFF;
    else
      v21 = (unsigned int)dword_1402682EC | 0x200000;
    LODWORD(dword_1402682EC) = v21;
    v155 = 3670070;
    v156 = L"RefsDisableLastAccessUpdate";
    *(_QWORD *)&v64.Length = 3670070;
    v64.Buffer = L"RefsDisableLastAccessUpdate";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v22 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v104 = v22;
    }
    else
    {
      v22 = v104;
    }
    if ( v22 == 1 )
      v23 = (unsigned int)dword_1402682EC | 0x40;
    else
      v23 = (unsigned int)dword_1402682EC & 0xFFFFFFBF;
    LODWORD(dword_1402682EC) = v23;
    v157 = 3276848;
    v158 = L"RefsDisableSqmThrottling";
    *(_QWORD *)&v64.Length = 3276848;
    v64.Buffer = L"RefsDisableSqmThrottling";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v24 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v105 = v24;
    }
    else
    {
      v24 = v105;
    }
    if ( v24 == 1 && (_BYTE)KdDebuggerEnabled )
    {
      if ( (InstrumentThrottle & 1) == 0 )
        _InterlockedOr((volatile signed __int32 *)&InstrumentThrottle, 1u);
    }
    else if ( (InstrumentThrottle & 1) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)&InstrumentThrottle, 0xFFFFFFFE);
    }
    v159 = 3276848;
    v160 = L"RefsDisableEtwThrottling";
    *(_QWORD *)&v64.Length = 3276848;
    v64.Buffer = L"RefsDisableEtwThrottling";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v25 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v106 = v25;
    }
    else
    {
      v25 = v106;
    }
    if ( v25 == 1 && (_BYTE)KdDebuggerEnabled )
    {
      if ( (InstrumentThrottle & 2) == 0 )
        _InterlockedOr((volatile signed __int32 *)&InstrumentThrottle, 2u);
    }
    else if ( (InstrumentThrottle & 2) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)&InstrumentThrottle, 0xFFFFFFFD);
    }
    v161 = 4063292;
    v162 = L"RefsDisableTelemetryThrottling";
    *(_QWORD *)&v64.Length = 4063292;
    v64.Buffer = L"RefsDisableTelemetryThrottling";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v26 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v121 = v26;
    }
    else
    {
      v26 = v121;
    }
    if ( v26 == 1 && (_BYTE)KdDebuggerEnabled )
    {
      if ( (InstrumentThrottle & 4) == 0 )
        _InterlockedOr((volatile signed __int32 *)&InstrumentThrottle, 4u);
    }
    else if ( (InstrumentThrottle & 4) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)&InstrumentThrottle, 0xFFFFFFFB);
    }
    v163 = 4980810;
    v164 = L"DataDestageSsdFillRatioEventThreshold";
    *(_QWORD *)&v64.Length = 4980810;
    v64.Buffer = L"DataDestageSsdFillRatioEventThreshold";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v27 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v99 = v27;
      v122 = v27;
    }
    else
    {
      v27 = v99;
    }
    if ( v27 <= 0x64 && v27 != dword_1402688B8 )
    {
      dword_1402688B8 = v27;
      v75 = 1;
    }
    v165 = 4325440;
    v166 = L"DataDestageSsdFillRatioThreshold";
    *(_QWORD *)&v64.Length = 4325440;
    v64.Buffer = L"DataDestageSsdFillRatioThreshold";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v28 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v95 = v28;
      v117 = v28;
    }
    else
    {
      v28 = v95;
    }
    if ( v28 <= 0x64 && v28 != dword_1402688A4 )
    {
      dword_1402688A4 = v28;
      v70 = 1;
    }
    v167 = 4849736;
    v168 = L"MetadataDestageSsdFillRatioThreshold";
    *(_QWORD *)&v64.Length = 4849736;
    v64.Buffer = L"MetadataDestageSsdFillRatioThreshold";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v29 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v96 = v29;
      v118 = v29;
    }
    else
    {
      v29 = v96;
    }
    if ( v29 <= 0x64 && v29 != dword_1402688A8 )
    {
      dword_1402688A8 = v29;
      v71 = 1;
    }
    v169 = 4325440;
    v170 = L"DataDestageHddFillRatioThreshold";
    *(_QWORD *)&v64.Length = 4325440;
    v64.Buffer = L"DataDestageHddFillRatioThreshold";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v30 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v101 = v30;
      v119 = v30;
    }
    else
    {
      v30 = v101;
    }
    if ( v30 <= 0x64 && v30 != dword_1402688AC )
    {
      dword_1402688AC = v30;
      v72 = 1;
    }
    v171 = 4849736;
    v172 = L"MetadataDestageHddFillRatioThreshold";
    *(_QWORD *)&v64.Length = 4849736;
    v64.Buffer = L"MetadataDestageHddFillRatioThreshold";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v31 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v97 = v31;
      v120 = v31;
    }
    else
    {
      v31 = v97;
    }
    if ( v31 <= 0x64 && v31 != dword_1402688B0 )
    {
      dword_1402688B0 = v31;
      v73 = 1;
    }
    v173 = 4063292;
    v174 = L"DataDestageCompactionThreshold";
    *(_QWORD *)&v64.Length = 4063292;
    v64.Buffer = L"DataDestageCompactionThreshold";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v32 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v98 = v32;
      v130 = v32;
    }
    else
    {
      v32 = v98;
    }
    if ( v32 <= 0x64 && v32 != dword_1402688B4 )
    {
      dword_1402688B4 = v32;
      v74 = 1;
    }
    v175 = 4718662;
    v176 = L"RefsEnableParallelContainerRotation";
    *(_QWORD *)&v64.Length = 4718662;
    v64.Buffer = L"RefsEnableParallelContainerRotation";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 < 0
      && (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 < 0) )
    {
      v33 = v68;
    }
    else
    {
      v33 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1;
      v68 = v33;
      v84 = v33;
    }
    if ( RefsEnableParallelContainerRotation != v33 )
    {
      RefsEnableParallelContainerRotation = v33;
      v69 = 1;
    }
    v177 = 5636180;
    v178 = L"RefsTableSetEntriesToNavigateBeforeCaching";
    *(_QWORD *)&v64.Length = 5636180;
    v64.Buffer = L"RefsTableSetEntriesToNavigateBeforeCaching";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 < 0
      && (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 < 0) )
    {
      v34 = v126;
    }
    else
    {
      v34 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v126 = v34;
      v134 = v34;
    }
    if ( v34 != dword_140269054 )
      dword_140269054 = v34;
    v179 = 4718662;
    v180 = L"RefsContainerRotationQueueSizeLimit";
    *(_QWORD *)&v64.Length = 4718662;
    v64.Buffer = L"RefsContainerRotationQueueSizeLimit";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v35 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v100 = v35;
      v123 = v35;
    }
    else
    {
      v35 = v100;
    }
    if ( RefsContainerRotationQueueSizeLimit != v35 )
    {
      RefsContainerRotationQueueSizeLimit = v35;
      v88 = 1;
    }
    v181 = 4325440;
    v182 = L"RefsContainerRotationThreadCount";
    *(_QWORD *)&v64.Length = 4325440;
    v64.Buffer = L"RefsContainerRotationThreadCount";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v36 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v103 = v36;
      v124 = v36;
    }
    else
    {
      v36 = v103;
    }
    if ( v36 != RefsContainerRotationThreadCount )
    {
      RefsContainerRotationThreadCount = v36;
      v87 = 1;
    }
    v183 = 3801144;
    v184 = L"RefsCheckpointSampleInterval";
    *(_QWORD *)&v64.Length = 3801144;
    v64.Buffer = L"RefsCheckpointSampleInterval";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v37 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v107 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v37 = v107;
    }
    if ( (_DWORD)v37 != -1 && RefsTelemetrySampling != 10000000 * v37 )
    {
      RefsTelemetrySampling = 10000000 * v37;
      v76 = 1;
    }
    v185 = 4194366;
    v186 = L"RefsBlockRefcountSampleInterval";
    *(_QWORD *)&v64.Length = 4194366;
    v64.Buffer = L"RefsBlockRefcountSampleInterval";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v38 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v108 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v38 = v108;
    }
    if ( (_DWORD)v38 != -1 && *(&RefsTelemetrySampling + 1) != 10000000 * v38 )
    {
      *(&RefsTelemetrySampling + 1) = 10000000 * v38;
      v77 = 1;
    }
    v187 = 4063292;
    v188 = L"RefsGhostExtentsSampleInterval";
    *(_QWORD *)&v64.Length = 4063292;
    v64.Buffer = L"RefsGhostExtentsSampleInterval";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v39 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v109 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v39 = v109;
    }
    if ( (_DWORD)v39 != -1 && qword_140267900 != 10000000 * v39 )
    {
      qword_140267900 = 10000000 * v39;
      v78 = 1;
    }
    v189 = 4325440;
    v190 = L"RefsStreamSnapshotSampleInterval";
    *(_QWORD *)&v64.Length = 4325440;
    v64.Buffer = L"RefsStreamSnapshotSampleInterval";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v40 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v110 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v40 = v110;
    }
    if ( (_DWORD)v40 != -1 && qword_140267930 != 10000000 * v40 )
    {
      qword_140267930 = 10000000 * v40;
      v79 = 1;
    }
    v191 = 4063292;
    v192 = L"RefsPerfCountersSampleInterval";
    *(_QWORD *)&v64.Length = 4063292;
    v64.Buffer = L"RefsPerfCountersSampleInterval";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 < 0 )
      v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    v193 = 4718662;
    v194 = L"RefsContainerRotationSampleInterval";
    *(_QWORD *)&v64.Length = 4718662;
    v64.Buffer = L"RefsContainerRotationSampleInterval";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v41 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v111 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v41 = v111;
    }
    if ( (_DWORD)v41 != -1 && qword_140267910 != 10000000 * v41 )
    {
      qword_140267910 = 10000000 * v41;
      v80 = 1;
    }
    v195 = 3670070;
    v196 = L"RefsSmrUpdateSampleInterval";
    *(_QWORD *)&v64.Length = 3670070;
    v64.Buffer = L"RefsSmrUpdateSampleInterval";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v42 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v112 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v42 = v112;
    }
    if ( (_DWORD)v42 != -1 && qword_140267918 != 10000000 * v42 )
    {
      qword_140267918 = 10000000 * v42;
      v81 = 1;
    }
    v197 = 2883626;
    v198 = L"RefsSmrSampleInterval";
    *(_QWORD *)&v64.Length = 2883626;
    v64.Buffer = L"RefsSmrSampleInterval";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v43 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v113 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v43 = v113;
    }
    if ( (_DWORD)v43 != -1 && qword_140267920 != 10000000 * v43 )
    {
      qword_140267920 = 10000000 * v43;
      v82 = 1;
    }
    v199 = 3932218;
    v200 = L"RefsLogFileFullSampleInterval";
    *(_QWORD *)&v64.Length = 3932218;
    v64.Buffer = L"RefsLogFileFullSampleInterval";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v44 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v114 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v44 = v114;
    }
    if ( (_DWORD)v44 != -1 && qword_140267928 != 10000000 * v44 )
    {
      qword_140267928 = 10000000 * v44;
      v83 = 1;
    }
    v201 = 4194366;
    v202 = L"RefsDisableTrueAsyncCachedReads";
    *(_QWORD *)&v64.Length = 4194366;
    v64.Buffer = L"RefsDisableTrueAsyncCachedReads";
    v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0 )
    {
      v45 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      if ( v45 )
      {
        if ( v45 == 1 )
          byte_1402688A0 = 1;
      }
      else
      {
        byte_1402688A0 = 0;
      }
    }
    v203 = 3801144;
    v204 = L"RefsEnableDirCaseSensitivity";
    *(_QWORD *)&v64.Length = 3801144;
    v64.Buffer = L"RefsEnableDirCaseSensitivity";
    v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 < 0 )
      dword_1402688BC = 3;
    else
      dword_1402688BC = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    v205 = 2228256;
    v206 = L"FsEnableDevDrive";
    *(_QWORD *)&v64.Length = 2228256;
    v64.Buffer = L"FsEnableDevDrive";
    v47 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    v61 = v47;
    if ( v47 < 0 )
    {
      if ( (unsigned __int8)RtlIsFeatureEnabledForEnterprise((PDEVICE_OBJECT)0x2ADD198, v46, v48, v49) )
      {
        v50 = v94;
      }
      else
      {
        v50 = 0;
        v94 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_823e6dba7932309d1ad2e841189c99ac_Traceguids, 0);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(0, 0, "NtfsInit.c", 0x1274u);
        v47 = 0;
        v61 = 0;
      }
    }
    else
    {
      v50 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v94 = v50;
    }
    if ( v47 >= 0 && !v50 )
      goto LABEL_248;
    v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0 )
    {
      v50 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v94 = v50;
    }
    if ( v50 )
      v51 = (unsigned int)dword_1402682EC | 0x2000000;
    else
LABEL_248:
      v51 = (unsigned int)dword_1402682EC & 0xFDFFFFFF;
    LODWORD(dword_1402682EC) = v51;
    v207 = 4325440;
    v208 = L"DisableAssociatedIrpAsyncPosting";
    *(_QWORD *)&v64.Length = 4325440;
    v64.Buffer = L"DisableAssociatedIrpAsyncPosting";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v52 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v115 = v52;
    }
    else
    {
      v52 = v115;
    }
    RefsDisableAssociatedIrpAsyncPosting = v52 != 0;
    v209 = 2359330;
    v210 = L"RefsDisableIoPerf";
    *(_QWORD *)&v64.Length = 2359330;
    v64.Buffer = L"RefsDisableIoPerf";
    v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0 )
    {
      v133 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v85 = 1;
    }
    v211 = 3276848;
    v212 = L"RefsMaxAcceptableLatency";
    *(_QWORD *)&v64.Length = 3276848;
    v64.Buffer = L"RefsMaxAcceptableLatency";
    v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 < 0 )
    {
      v54 = v65;
      v53 = v131;
    }
    else
    {
      v53 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v131 = v53;
      v54 = 1;
      v65 = 1;
    }
    if ( v54 )
    {
      if ( v53 == dword_14026E3B4 || (unsigned int)(v53 - 1) > 0x1D4BF )
      {
        v54 = 0;
        v65 = 0;
      }
      else
      {
        v54 = v65;
      }
    }
    if ( v85 )
      IoPerfRegistryConfig = v133 != 0;
    if ( v54 )
      dword_14026E3B4 = v53;
    v213 = 3538996;
    v214 = L"RefsParallelFlushThreshold";
    *(_QWORD *)&v64.Length = 3538996;
    v64.Buffer = L"RefsParallelFlushThreshold";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v55 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v92 = v55;
    }
    else
    {
      v55 = v93;
    }
    if ( v55 )
    {
      if ( v55 >= 0x64 )
      {
        if ( v55 > 0xF4240 )
          v55 = 1000000;
      }
      else
      {
        v55 = 100;
      }
    }
    else
    {
      v55 = 1000;
    }
    v92 = v55;
    v93 = v55;
    if ( dword_1402688F4 != v55 )
      dword_1402688F4 = v55;
    v215 = 3276848;
    v216 = L"RefsParallelFlushWorkers";
    *(_QWORD *)&v64.Length = 3276848;
    v64.Buffer = L"RefsParallelFlushWorkers";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v56 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v91 = v56;
    }
    else
    {
      v56 = v91;
    }
    if ( v56 )
    {
      if ( v56 > 2 * RefsNumberProcessors )
      {
        v56 = 2 * RefsNumberProcessors;
        v91 = 2 * RefsNumberProcessors;
      }
    }
    else
    {
      v56 = (RefsNumberProcessors >> 1) + 1;
      v91 = v56;
      v138 = 16;
      if ( v56 > 0x10 )
        v56 = 16;
      v91 = v56;
    }
    if ( dword_1402688F0 != v56 )
      dword_1402688F0 = v56;
    v217 = 4325440;
    v218 = L"RefsMaxQueuedDecompressWorkItems";
    *(_QWORD *)&v64.Length = 4325440;
    v64.Buffer = L"RefsMaxQueuedDecompressWorkItems";
    v61 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    if ( v61 >= 0
      || (v61 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60), v61 >= 0) )
    {
      v57 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v116 = v57;
    }
    else
    {
      v57 = v116;
    }
    if ( (unsigned int)(v57 - 1) > 0xFFFFFE )
    {
      dword_140268904 = 0xFFFFFF;
    }
    else if ( dword_140268904 != v57 )
    {
      dword_140268904 = v57;
    }
    v58 = Feature_NTFS_DirectoryChangeNotifyListDirectoryAccessCheck__private_IsEnabledDeviceUsageNoInline() != 0;
    v219 = 6553698;
    v220 = L"EnforceDirectoryChangeNotificationPermissionCheck";
    *(_QWORD *)&v64.Length = 6553698;
    v64.Buffer = L"EnforceDirectoryChangeNotificationPermissionCheck";
    v2 = RefsQueryValueKeyEx(&v90, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
    v61 = v2;
    if ( v2 < 0 )
    {
      v2 = RefsQueryValueKeyEx(&v89, 0, &v64, &v62, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v60);
      v61 = v2;
      v59 = (unsigned int *)P;
      if ( v2 < 0 )
        goto LABEL_303;
    }
    else
    {
      v59 = (unsigned int *)P;
    }
    v58 = *(unsigned int *)((char *)v59 + v59[2]);
LABEL_303:
    byte_140268908 = v58 != 0;
    ExReleaseFastResource(qword_1402680F8, 0);
    v67 = 0;
    if ( a1 )
    {
      if ( v66 )
        RefsForEachVcb(
          v3,
          0,
          (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateDeleteNotificationVolumeSetting,
          0,
          0);
      if ( v86 )
        RefsForEachVcb(
          v3,
          0,
          (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateFileLevelTrimVolumeSetting,
          0,
          0);
      if ( v87 || v88 || v69 )
      {
        dword_14026910C = RefsContainerRotationThreadCount;
        dword_140269110 = RefsContainerRotationQueueSizeLimit;
        byte_14026910A = RefsEnableParallelContainerRotation;
        RefsForEachVcb(
          v3,
          0,
          (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateContainerRotationThreadCount,
          0,
          0);
      }
      if ( v65 )
        IoPerfRegistryUpdateConfig();
    }
    if ( v70 || v71 || v72 || v73 || v74 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateContainerMoveThresholdsVolumeSetting,
        0,
        0);
    if ( v75 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateContainerMoveEventThresholdsVolumeSetting,
        0,
        0);
    if ( v76 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateCheckpointSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v77 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateBlockRefcountSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v78 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateGhostExtentsSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v79 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateStreamSnapshotSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v80 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateContainerRotationSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v81 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateSmrUpdateSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v82 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateSmrSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v83 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateLogFileFullSampleIntervalVolumeSetting,
        0,
        1u);
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v3, 0, 0);
  }
  while ( v2 == -1073741608 || v2 == -1073741432 );
  if ( v60[0] )
    ExFreePoolWithTag(v59, 0);
  ExReleaseFastResource(&RefsDynamicRegistrySettingsResource, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1402cead0  mov     r11, rsp
0x1402cead3  mov     [r11+10h], rbx
0x1402cead7  mov     [r11+18h], rsi
0x1402ceadb  mov     [r11+8], rcx
0x1402ceadf  push    rdi
0x1402ceae0  push    r12
0x1402ceae2  push    r13
0x1402ceae4  push    r14
0x1402ceae6  push    r15
0x1402ceae8  sub     rsp, 7A0h
0x1402ceaef  mov     rax, cs:__security_cookie
0x1402ceaf6  xor     rax, rsp
0x1402ceaf9  mov     [rsp+7C8h+var_38], rax
0x1402ceb01  lea     rax, [r11-3B8h]
0x1402ceb08  mov     [r11-690h], rax
0x1402ceb0f  xorps   xmm0, xmm0
0x1402ceb12  xor     eax, eax
0x1402ceb14  movups  [rsp+7C8h+var_3D0], xmm0
0x1402ceb1c  mov     [r11-3C0h], rax
0x1402ceb23  movups  xmmword ptr [rsp+7C8h+var_748.Length], xmm0
0x1402ceb2b  xorps   xmm1, xmm1
0x1402ceb2e  movups  xmmword ptr [rsp+7C8h+var_758.Length], xmm1
0x1402ceb33  movups  xmmword ptr [rsp+7C8h+var_780.Length], xmm0
0x1402ceb38  mov     [rsp+7C8h+var_790], 9Ch
0x1402ceb40  lea     rax, [r11-0D8h]
0x1402ceb47  mov     [rsp+7C8h+P], rax
0x1402ceb4c  xor     ebx, ebx
0x1402ceb4e  mov     [rsp+7C8h+var_798], bl
0x1402ceb52  mov     eax, cs:dword_1402688A4
0x1402ceb58  mov     [rsp+7C8h+var_728], eax
0x1402ceb5f  mov     [rsp+7C8h+var_6D0], eax
0x1402ceb66  mov     eax, cs:dword_1402688A8
0x1402ceb6c  mov     [rsp+7C8h+var_724], eax
0x1402ceb73  mov     [rsp+7C8h+var_6CC], eax
0x1402ceb7a  mov     eax, cs:dword_1402688AC
0x1402ceb80  mov     [rsp+7C8h+var_710], eax
0x1402ceb87  mov     [rsp+7C8h+var_6C8], eax
0x1402ceb8e  mov     eax, cs:dword_1402688B0
0x1402ceb94  mov     [rsp+7C8h+var_720], eax
0x1402ceb9b  mov     [rsp+7C8h+var_6C4], eax
0x1402ceba2  mov     eax, cs:dword_1402688B4
0x1402ceba8  mov     [rsp+7C8h+var_71C], eax
0x1402cebaf  mov     [rsp+7C8h+var_69C], eax
0x1402cebb6  mov     eax, cs:dword_1402688B8
0x1402cebbc  mov     [rsp+7C8h+var_718], eax
0x1402cebc3  mov     [rsp+7C8h+var_6BC], eax
0x1402cebca  mov     al, cs:?RefsEnableParallelContainerRotation@@3EA; uchar RefsEnableParallelContainerRotation
0x1402cebd0  mov     [rsp+7C8h+var_76D], al
0x1402cebd4  mov     [rsp+7C8h+var_75D], al
0x1402cebd8  mov     eax, cs:?RefsContainerRotationQueueSizeLimit@@3KA; ulong RefsContainerRotationQueueSizeLimit
0x1402cebde  mov     [rsp+7C8h+var_714], eax
0x1402cebe5  mov     [rsp+7C8h+var_6B8], eax
0x1402cebec  mov     eax, cs:?RefsContainerRotationThreadCount@@3KA; ulong RefsContainerRotationThreadCount
0x1402cebf2  mov     [rsp+7C8h+var_708], eax
0x1402cebf9  mov     [rsp+7C8h+var_6B4], eax
0x1402cec00  mov     ecx, ebx
0x1402cec02  cmp     cs:?RefsFailIncompleteLogRedo@@3EA, bl; uchar RefsFailIncompleteLogRedo
0x1402cec08  setnz   cl
0x1402cec0b  mov     [rsp+7C8h+var_70C], ecx
0x1402cec12  mov     [rsp+7C8h+var_6B0], ecx
0x1402cec19  mov     eax, cs:dword_140269054
0x1402cec1f  mov     [rsp+7C8h+var_6AC], eax
0x1402cec26  mov     [rsp+7C8h+var_684], eax
0x1402cec2d  mov     [rsp+7C8h+var_738], ebx
0x1402cec34  xor     r8d, r8d; unsigned __int8
0x1402cec37  xor     edx, edx; unsigned __int8
0x1402cec39  lea     rcx, [r11-3D0h]; struct _TOP_LEVEL_CONTEXT *
0x1402cec40  call    ?RefsInitializeTopLevelIrp@@YAPEAU_TOP_LEVEL_CONTEXT@@PEAU1@EE@Z; RefsInitializeTopLevelIrp(_TOP_LEVEL_CONTEXT *,uchar,uchar)
0x1402cec45  mov     rdi, rax
0x1402cec48  lea     r9, [rsp+7C8h+var_690]; struct _IRP_CONTEXT **
0x1402cec50  xor     r8d, r8d; unsigned __int8
0x1402cec53  lea     r15d, [rbx+1]
0x1402cec57  mov     dl, r15b; unsigned __int8
0x1402cec5a  xor     ecx, ecx; Irp
0x1402cec5c  call    ?RefsInitializeIrpContext@@YAJPEAU_IRP@@EEPEAPEAU_IRP_CONTEXT@@@Z; RefsInitializeIrpContext(_IRP *,uchar,uchar,_IRP_CONTEXT * *)
0x1402cec61  mov     r14d, eax
0x1402cec64  test    eax, eax
0x1402cec66  js      loc_1402D1163
0x1402cec6c  mov     [rsp+7C8h+var_76E], bl
0x1402cec70  mov     [rsp+7C8h+var_76F], bl
0x1402cec74  mov     [rsp+7C8h+var_75B], bl
0x1402cec78  mov     [rsp+7C8h+var_6A8], ebx
0x1402cec7f  mov     [rsp+7C8h+var_6A4], ebx
0x1402cec86  mov     [rsp+7C8h+var_6A0], ebx
0x1402cec8d  mov     [rsp+7C8h+var_704], r15d
0x1402cec95  mov     [rsp+7C8h+var_700], ebx
0x1402cec9c  mov     [rsp+7C8h+var_6FC], ebx
0x1402ceca3  mov     [rsp+7C8h+var_6C0], ebx
0x1402cecaa  or      r12d, 0FFFFFFFFh
0x1402cecae  mov     [rsp+7C8h+var_6F8], r12d
0x1402cecb6  mov     [rsp+7C8h+var_765], bl
0x1402cecba  mov     [rsp+7C8h+var_6F4], r12d
0x1402cecc2  mov     [rsp+7C8h+var_764], bl
0x1402cecc6  mov     [rsp+7C8h+var_6F0], r12d
0x1402cecce  mov     [rsp+7C8h+var_763], bl
0x1402cecd2  mov     [rsp+7C8h+var_6EC], r12d
0x1402cecda  mov     [rsp+7C8h+var_762], bl
0x1402cecde  mov     [rsp+7C8h+var_6E8], r12d
0x1402cece6  mov     [rsp+7C8h+var_761], bl
0x1402cecea  mov     [rsp+7C8h+var_6E4], r12d
0x1402cecf2  mov     [rsp+7C8h+var_760], bl
0x1402cecf6  mov     [rsp+7C8h+var_6E0], r12d
0x1402cecfe  mov     [rsp+7C8h+var_75F], bl
0x1402ced02  mov     [rsp+7C8h+var_6DC], r12d
0x1402ced0a  mov     [rsp+7C8h+var_75E], bl
0x1402ced0e  mov     [rsp+7C8h+var_72C], r15d
0x1402ced16  mov     [rsp+7C8h+var_76B], bl
0x1402ced1a  mov     [rsp+7C8h+var_76A], bl
0x1402ced1e  mov     [rsp+7C8h+var_769], bl
0x1402ced22  mov     [rsp+7C8h+var_768], bl
0x1402ced26  mov     [rsp+7C8h+var_767], bl
0x1402ced2a  mov     [rsp+7C8h+var_766], bl
0x1402ced2e  mov     [rsp+7C8h+var_76C], bl
0x1402ced32  mov     [rsp+7C8h+var_759], bl
0x1402ced36  mov     [rsp+7C8h+var_75A], bl
0x1402ced3a  mov     [rsp+7C8h+var_6D8], ebx
0x1402ced41  mov     [rsp+7C8h+var_730], ebx
0x1402ced48  mov     [rsp+7C8h+var_734], ebx
0x1402ced4f  lea     esi, [rbx+64h]
0x1402ced52  mov     [rsp+7C8h+var_6D4], esi
0x1402ced59  mov     [rsp+7C8h+var_688], ebx
0x1402ced60  mov     [rsp+7C8h+var_75C], bl
0x1402ced64  mov     [rsp+7C8h+var_698], 7530h
0x1402ced6f  mov     [rsp+7C8h+var_770], bl
0x1402ced73  mov     r13, [rsp+7C8h+var_690]
0x1402ced7b  cmp     [rdi+10h], rbx
0x1402ced7f  jnz     short loc_1402CEDA1
0x1402ced81  mov     dword ptr [rdi+4], 5346ABBAh
0x1402ced88  mov     [rdi+10h], r13
0x1402ced8c  bts     qword ptr [r13+8], 14h
0x1402ced92  mov     rcx, rdi; Irp
0x1402ced95  call    cs:__imp_IoSetTopLevelIrp
0x1402ced9c  nop     dword ptr [rax+rax+00h]
0x1402ceda1  mov     rax, [rdi+10h]
0x1402ceda5  mov     [r13+68h], rax
0x1402ceda9  call    cs:__imp_KeEnterCriticalRegion
0x1402cedb0  nop     dword ptr [rax+rax+00h]
0x1402cedb5  mov     r8b, r15b
0x1402cedb8  xor     edx, edx
0x1402cedba  lea     rcx, ?RefsDynamicRegistrySettingsResource@@3U_FAST_ERESOURCE@@A; _FAST_ERESOURCE RefsDynamicRegistrySettingsResource
0x1402cedc1  call    cs:__imp_ExAcquireFastResourceExclusive
0x1402cedc8  nop     dword ptr [rax+rax+00h]
0x1402cedcd  mov     qword ptr [rsp+7C8h+var_748.Length], 680066h
0x1402cedd9  lea     rax, aRegistryMachin_10; "\\Registry\\Machine\\System\\CurrentCon"...
0x1402cede0  mov     [rsp+7C8h+var_748.Buffer], rax
0x1402cede8  mov     qword ptr [rsp+7C8h+var_758.Length], 7C007Ah
0x1402cedf1  lea     rax, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x1402cedf8  mov     [rsp+7C8h+var_758.Buffer], rax
0x1402cedfd  mov     edi, 40h ; '@'
0x1402cee02  jmp     short loc_1402CEE09
0x1402cee04  mov     esi, 64h ; 'd'
0x1402cee09  cmp     r14d, 0C0000188h
0x1402cee10  jnz     short loc_1402CEE1A
0x1402cee12  mov     rcx, r13; struct _IRP_CONTEXT *
0x1402cee15  call    ?RefsCheckpointForLogFileFull@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointForLogFileFull(_IRP_CONTEXT *)
0x1402cee1a  test    r13, r13
0x1402cee1d  jz      short loc_1402CEE27
0x1402cee1f  mov     rcx, r13; struct _IRP_CONTEXT *
0x1402cee22  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x1402cee27  mov     r8b, r15b
0x1402cee2a  xor     edx, edx
0x1402cee2c  lea     rcx, qword_1402680F8
0x1402cee33  call    cs:__imp_ExAcquireFastResourceExclusive
0x1402cee3a  nop     dword ptr [rax+rax+00h]
0x1402cee3f  mov     [rsp+7C8h+var_76E], r15b
0x1402cee44  mov     [rsp+7C8h+var_660], 3C003Ah
0x1402cee4f  lea     rdx, aRefsdisabledel; "RefsDisableDeleteNotification"
0x1402cee56  mov     [rsp+7C8h+var_658], rdx
0x1402cee5e  mov     qword ptr [rsp+7C8h+var_780.Length], 3C003Ah
0x1402cee67  mov     [rsp+7C8h+var_780.Buffer], rdx
0x1402cee6c  lea     rax, [rsp+7C8h+var_798]
0x1402cee71  mov     [rsp+7C8h+var_7A0], rax; unsigned __int8 *
0x1402cee76  lea     rax, [rsp+7C8h+P]
0x1402cee7b  mov     [rsp+7C8h+var_7A8], rax; struct _KEY_VALUE_FULL_INFORMATION **
0x1402cee80  lea     r9, [rsp+7C8h+var_790]; unsigned int *
0x1402cee85  lea     r8, [rsp+7C8h+var_780]; struct _UNICODE_STRING *
0x1402cee8a  xor     edx, edx; void *
0x1402cee8c  lea     rcx, [rsp+7C8h+var_748]; struct _UNICODE_STRING *
0x1402cee94  call    ?RefsQueryValueKeyEx@@YAJPEAU_UNICODE_STRING@@PEAX0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKeyEx(_UNICODE_STRING *,void *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x1402cee99  mov     [rsp+7C8h+var_794], eax
0x1402cee9d  test    eax, eax
0x1402cee9f  jns     short loc_1402CEED3
0x1402ceea1  lea     rax, [rsp+7C8h+var_798]
0x1402ceea6  mov     [rsp+7C8h+var_7A0], rax; unsigned __int8 *
0x1402ceeab  lea     rax, [rsp+7C8h+P]
0x1402ceeb0  mov     [rsp+7C8h+var_7A8], rax; struct _KEY_VALUE_FULL_INFORMATION **
0x1402ceeb5  lea     r9, [rsp+7C8h+var_790]; unsigned int *
0x1402ceeba  lea     r8, [rsp+7C8h+var_780]; struct _UNICODE_STRING *
0x1402ceebf  xor     edx, edx; void *
0x1402ceec1  lea     rcx, [rsp+7C8h+var_758]; struct _UNICODE_STRING *
0x1402ceec6  call    ?RefsQueryValueKeyEx@@YAJPEAU_UNICODE_STRING@@PEAX0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKeyEx(_UNICODE_STRING *,void *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x1402ceecb  mov     [rsp+7C8h+var_794], eax
0x1402ceecf  test    eax, eax
0x1402ceed1  js      short loc_1402CEEE0
0x1402ceed3  mov     rcx, [rsp+7C8h+P]
0x1402ceed8  mov     eax, [rcx+8]
0x1402ceedb  mov     edx, [rax+rcx]
0x1402ceede  jmp     short loc_1402CEEE2
0x1402ceee0  mov     edx, ebx
0x1402ceee2  mov     eax, cs:dword_1402682EC
0x1402ceee8  cmp     edx, r15d
0x1402ceeeb  jnz     short loc_1402CEEFA
0x1402ceeed  mov     ecx, 8000h
0x1402ceef2  test    ecx, eax
0x1402ceef4  jnz     short loc_1402CEF0F
0x1402ceef6  or      eax, ecx
0x1402ceef8  jmp     short loc_1402CEF04
0x1402ceefa  bt      eax, 0Fh
0x1402ceefe  jnb     short loc_1402CEF0F
0x1402cef00  btr     eax, 0Fh
0x1402cef04  mov     cs:dword_1402682EC, eax
0x1402cef0a  mov     [rsp+7C8h+var_76F], r15b
0x1402cef0f  mov     [rsp+7C8h+var_650], 340032h
0x1402cef1a  lea     rdx, aRefsfailincomp; "RefsFailIncompleteLogRedo"
0x1402cef21  mov     [rsp+7C8h+var_648], rdx
0x1402cef29  mov     qword ptr [rsp+7C8h+var_780.Length], 340032h
0x1402cef32  mov     [rsp+7C8h+var_780.Buffer], rdx
0x1402cef37  lea     rax, [rsp+7C8h+var_798]
0x1402cef3c  mov     [rsp+7C8h+var_7A0], rax; unsigned __int8 *
0x1402cef41  lea     rax, [rsp+7C8h+P]
0x1402cef46  mov     [rsp+7C8h+var_7A8], rax; struct _KEY_VALUE_FULL_INFORMATION **
0x1402cef4b  lea     r9, [rsp+7C8h+var_790]; unsigned int *
0x1402cef50  lea     r8, [rsp+7C8h+var_780]; struct _UNICODE_STRING *
0x1402cef55  xor     edx, edx; void *
0x1402cef57  lea     rcx, [rsp+7C8h+var_748]; struct _UNICODE_STRING *
0x1402cef5f  call    ?RefsQueryValueKeyEx@@YAJPEAU_UNICODE_STRING@@PEAX0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKeyEx(_UNICODE_STRING *,void *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x1402cef64  mov     [rsp+7C8h+var_794], eax
0x1402cef68  test    eax, eax
0x1402cef6a  js      short loc_1402CEF87
0x1402cef6c  mov     rcx, [rsp+7C8h+P]
0x1402cef71  mov     eax, [rcx+8]
0x1402cef74  mov     eax, [rax+rcx]
0x1402cef77  mov     [rsp+7C8h+var_70C], eax
0x1402cef7e  mov     [rsp+7C8h+var_6B0], eax
0x1402cef85  jmp     short loc_1402CEFC0
0x1402cef87  lea     rax, [rsp+7C8h+var_798]
0x1402cef8c  mov     [rsp+7C8h+var_7A0], rax; unsigned __int8 *
0x1402cef91  lea     rax, [rsp+7C8h+P]
0x1402cef96  mov     [rsp+7C8h+var_7A8], rax; struct _KEY_VALUE_FULL_INFORMATION **
0x1402cef9b  lea     r9, [rsp+7C8h+var_790]; unsigned int *
0x1402cefa0  lea     r8, [rsp+7C8h+var_780]; struct _UNICODE_STRING *
0x1402cefa5  xor     edx, edx; void *
0x1402cefa7  lea     rcx, [rsp+7C8h+var_758]; struct _UNICODE_STRING *
0x1402cefac  call    ?RefsQueryValueKeyEx@@YAJPEAU_UNICODE_STRING@@PEAX0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKeyEx(_UNICODE_STRING *,void *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x1402cefb1  mov     [rsp+7C8h+var_794], eax
0x1402cefb5  test    eax, eax
0x1402cefb7  jns     short loc_1402CEF6C
0x1402cefb9  mov     eax, [rsp+7C8h+var_70C]
0x1402cefc0  cmp     eax, r15d
0x1402cefc3  jnz     short loc_1402CEFD1
0x1402cefc5  mov     cs:?RefsFailIncompleteLogRedo@@3EA, r15b; uchar RefsFailIncompleteLogRedo
0x1402cefcc  mov     al, r15b
0x1402cefcf  jmp     short loc_1402CEFD9
0x1402cefd1  mov     cs:?RefsFailIncompleteLogRedo@@3EA, bl; uchar RefsFailIncompleteLogRedo
0x1402cefd7  mov     al, bl
0x1402cefd9  mov     cs:byte_140269011, al
0x1402cefdf  mov     [rsp+7C8h+var_640], 440042h
0x1402cefea  lea     rax, aRefsenablebrea; "RefsEnableBreakOnChecksumMismatch"
0x1402ceff1  mov     [rsp+7C8h+var_638], rax
0x1402ceff9  mov     qword ptr [rsp+7C8h+var_780.Length], 440042h
0x1402cf002  mov     [rsp+7C8h+var_780.Buffer], rax
0x1402cf007  lea     rax, [rsp+7C8h+var_798]
0x1402cf00c  mov     [rsp+7C8h+var_7A0], rax; unsigned __int8 *
0x1402cf011  lea     rax, [rsp+7C8h+P]
0x1402cf016  mov     [rsp+7C8h+var_7A8], rax; struct _KEY_VALUE_FULL_INFORMATION **
0x1402cf01b  lea     r9, [rsp+7C8h+var_790]; unsigned int *
0x1402cf020  lea     r8, [rsp+7C8h+var_780]; struct _UNICODE_STRING *
0x1402cf025  xor     edx, edx; void *
0x1402cf027  lea     rcx, [rsp+7C8h+var_758]; struct _UNICODE_STRING *
0x1402cf02c  call    ?RefsQueryValueKeyEx@@YAJPEAU_UNICODE_STRING@@PEAX0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKeyEx(_UNICODE_STRING *,void *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x1402cf031  mov     [rsp+7C8h+var_794], eax
0x1402cf035  test    eax, eax
0x1402cf037  js      short loc_1402CF052
0x1402cf039  mov     rcx, [rsp+7C8h+P]
0x1402cf03e  mov     eax, [rcx+8]
0x1402cf041  cmp     [rax+rcx], r15d
0x1402cf045  jnz     short loc_1402CF052
0x1402cf047  mov     al, r15b
0x1402cf04a  mov     cs:?RefsEnableBreakOnChecksumMismatch@@3EA, al; uchar RefsEnableBreakOnChecksumMismatch
0x1402cf050  jmp     short loc_1402CF05A
0x1402cf052  mov     al, bl
0x1402cf054  mov     cs:?RefsEnableBreakOnChecksumMismatch@@3EA, bl; uchar RefsEnableBreakOnChecksumMismatch
0x1402cf05a  mov     cs:MsControl, al
0x1402cf060  mov     [rsp+7C8h+var_630], 3A0038h
0x1402cf06b  lea     rdx, aRefsenablemeta_0; "RefsEnableMetadataValidation"
0x1402cf072  mov     [rsp+7C8h+var_628], rdx
0x1402cf07a  mov     qword ptr [rsp+7C8h+var_780.Length], 3A0038h
0x1402cf083  mov     [rsp+7C8h+var_780.Buffer], rdx
0x1402cf088  lea     rax, [rsp+7C8h+var_798]
0x1402cf08d  mov     [rsp+7C8h+var_7A0], rax; unsigned __int8 *
0x1402cf092  lea     rax, [rsp+7C8h+P]
0x1402cf097  mov     [rsp+7C8h+var_7A8], rax; struct _KEY_VALUE_FULL_INFORMATION **
0x1402cf09c  lea     r9, [rsp+7C8h+var_790]; unsigned int *
0x1402cf0a1  lea     r8, [rsp+7C8h+var_780]; struct _UNICODE_STRING *
0x1402cf0a6  xor     edx, edx; void *
0x1402cf0a8  lea     rcx, [rsp+7C8h+var_758]; struct _UNICODE_STRING *
0x1402cf0ad  call    ?RefsQueryValueKeyEx@@YAJPEAU_UNICODE_STRING@@PEAX0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKeyEx(_UNICODE_STRING *,void *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x1402cf0b2  mov     [rsp+7C8h+var_794], eax
0x1402cf0b6  test    eax, eax
0x1402cf0b8  js      short loc_1402CF0DB
  ... truncated ...
```
