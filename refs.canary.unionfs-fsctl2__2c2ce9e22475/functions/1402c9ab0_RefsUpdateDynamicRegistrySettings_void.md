# RefsUpdateDynamicRegistrySettings(void *)

- ea: `0x1402c9ab0`
- end: `0x1402cc279`
- name: `?RefsUpdateDynamicRegistrySettings@@_Y2PAGE@@AXPEAX@Z`
- size: `10185`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14034cc48`

## callees

- `0x140039b60`
- `0x14003a520`
- `0x14003ec10`
- `0x140041b40`
- `0x14007dd30`
- `0x14008dbd0`
- `0x1400a648c`
- `0x1400c924c`
- `0x1400ca788`
- `0x1400cc208`
- `0x1401e9ce0`
- `0x1402c9ab0`
- `0x1402fa0d8`
- `0x14032bb40`
- `0x140330af8`
- `0x1403389e4`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1402c9d87`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1402c9d87`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402c9d9b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402c9d9b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402cc23f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402cc23f`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402c9db3`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402c9e25`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402c9db3`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402c9e25`
- `ntoskrnl!KdDebuggerEnabled` at `0x1402ca352`
- `ntoskrnl!KdDebuggerEnabled` at `0x1402ca5af`
- `ntoskrnl!KdDebuggerEnabled` at `0x1402ca691`
- `ntoskrnl!KdDebuggerEnabled` at `0x1402ca771`
- `ntoskrnl!ExReleaseFastResource` at `0x1402cbecf`
- `ntoskrnl!ExReleaseFastResource` at `0x1402cc11d`
- `ntoskrnl!ExReleaseFastResource` at `0x1402cc233`
- `ntoskrnl!ExReleaseFastResource` at `0x1402cbecf`
- `ntoskrnl!ExReleaseFastResource` at `0x1402cc11d`
- `ntoskrnl!ExReleaseFastResource` at `0x1402cc233`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402cc21e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402cc21e`
- `ntoskrnl!__imp_RtlIsFeatureEnabledForEnterprise` at `0x1402cb87a`
- `ntoskrnl!__imp_RtlIsFeatureEnabledForEnterprise` at `0x1402cb87a`

## string_xrefs

- `0x1402c9dcb`: `\Registry\Machine\System\CurrentControlSet\Policies`
- `0x1402c9de3`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x1402c9e41`: `RefsDisableDeleteNotification`
- `0x1402c9f0c`: `RefsFailIncompleteLogRedo`
- `0x1402ca384`: `RefsDisableAsyncDelete`
- `0x1402ca449`: `RefsDisableLastAccessUpdate`
- `0x1402cab95`: `DataDestageCompactionThreshold`
- `0x1402cae9f`: `RefsContainerRotationThreadCount`
- `0x1402cb3e8`: `RefsReadCacheSampleInterval`
- `0x1402cb4b3`: `RefsSmrUpdateSampleInterval`
- `0x1402cb714`: `RefsDisableTrueAsyncCachedReads`
- `0x1402cbd46`: `RefsMaxQueuedDecompressWorkItems`
- `0x1402cbe21`: `EnforceDirectoryChangeNotificationPermissionCheck`

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
  __int64 v45; // rax
  int v46; // edx
  ULONG v47; // edx
  int v48; // edi
  BOOLEAN v49; // r8
  struct _DRIVE_LAYOUT_INFORMATION **v50; // r9
  int v51; // r14d
  unsigned int v52; // eax
  int v53; // eax
  int v54; // ecx
  char v55; // al
  unsigned int v56; // ecx
  unsigned int v57; // edx
  int v58; // ecx
  int v59; // edi
  unsigned int *v60; // rsi
  unsigned __int8 v61[4]; // [rsp+30h] [rbp-7B8h] BYREF
  int v62; // [rsp+34h] [rbp-7B4h]
  unsigned int v63; // [rsp+38h] [rbp-7B0h] BYREF
  PVOID P; // [rsp+40h] [rbp-7A8h] BYREF
  struct _UNICODE_STRING v65; // [rsp+48h] [rbp-7A0h] BYREF
  char v66; // [rsp+58h] [rbp-790h]
  char v67; // [rsp+59h] [rbp-78Fh]
  char v68; // [rsp+5Ah] [rbp-78Eh]
  unsigned __int8 v69; // [rsp+5Bh] [rbp-78Dh]
  char v70; // [rsp+5Ch] [rbp-78Ch]
  char v71; // [rsp+5Dh] [rbp-78Bh]
  char v72; // [rsp+5Eh] [rbp-78Ah]
  char v73; // [rsp+5Fh] [rbp-789h]
  char v74; // [rsp+60h] [rbp-788h]
  char v75; // [rsp+61h] [rbp-787h]
  char v76; // [rsp+62h] [rbp-786h]
  char v77; // [rsp+63h] [rbp-785h]
  char v78; // [rsp+64h] [rbp-784h]
  char v79; // [rsp+65h] [rbp-783h]
  char v80; // [rsp+66h] [rbp-782h]
  char v81; // [rsp+67h] [rbp-781h]
  char v82; // [rsp+68h] [rbp-780h]
  char v83; // [rsp+69h] [rbp-77Fh]
  char v84; // [rsp+6Ah] [rbp-77Eh]
  char v85; // [rsp+6Bh] [rbp-77Dh]
  unsigned __int8 v86; // [rsp+6Ch] [rbp-77Ch]
  char v87; // [rsp+6Dh] [rbp-77Bh]
  char v88; // [rsp+6Eh] [rbp-77Ah]
  struct _UNICODE_STRING v89; // [rsp+70h] [rbp-778h] BYREF
  char v90; // [rsp+80h] [rbp-768h]
  char v91; // [rsp+81h] [rbp-767h]
  struct _UNICODE_STRING v92; // [rsp+88h] [rbp-760h] BYREF
  unsigned int v93; // [rsp+98h] [rbp-750h]
  unsigned int v94; // [rsp+9Ch] [rbp-74Ch]
  unsigned int v95; // [rsp+A0h] [rbp-748h]
  int v96; // [rsp+A4h] [rbp-744h]
  int v97; // [rsp+A8h] [rbp-740h]
  int v98; // [rsp+ACh] [rbp-73Ch]
  int v99; // [rsp+B0h] [rbp-738h]
  int v100; // [rsp+B4h] [rbp-734h]
  int v101; // [rsp+B8h] [rbp-730h]
  unsigned int v102; // [rsp+BCh] [rbp-72Ch]
  int v103; // [rsp+C0h] [rbp-728h]
  BOOL v104; // [rsp+C4h] [rbp-724h]
  unsigned int v105; // [rsp+C8h] [rbp-720h]
  int v106; // [rsp+CCh] [rbp-71Ch]
  int v107; // [rsp+D0h] [rbp-718h]
  int v108; // [rsp+D4h] [rbp-714h]
  unsigned int v109; // [rsp+D8h] [rbp-710h]
  unsigned int v110; // [rsp+DCh] [rbp-70Ch]
  unsigned int v111; // [rsp+E0h] [rbp-708h]
  unsigned int v112; // [rsp+E4h] [rbp-704h]
  unsigned int v113; // [rsp+E8h] [rbp-700h]
  unsigned int v114; // [rsp+ECh] [rbp-6FCh]
  unsigned int v115; // [rsp+F0h] [rbp-6F8h]
  unsigned int v116; // [rsp+F4h] [rbp-6F4h]
  unsigned int v117; // [rsp+F8h] [rbp-6F0h]
  int v118; // [rsp+FCh] [rbp-6ECh]
  int v119; // [rsp+100h] [rbp-6E8h]
  int v120; // [rsp+104h] [rbp-6E4h]
  int v121; // [rsp+108h] [rbp-6E0h]
  int v122; // [rsp+10Ch] [rbp-6DCh]
  int v123; // [rsp+110h] [rbp-6D8h]
  int v124; // [rsp+114h] [rbp-6D4h]
  int v125; // [rsp+118h] [rbp-6D0h]
  unsigned int v126; // [rsp+11Ch] [rbp-6CCh]
  unsigned int v127; // [rsp+120h] [rbp-6C8h]
  BOOL v128; // [rsp+124h] [rbp-6C4h]
  int v129; // [rsp+128h] [rbp-6C0h]
  int v130; // [rsp+12Ch] [rbp-6BCh]
  int v131; // [rsp+130h] [rbp-6B8h]
  int v132; // [rsp+134h] [rbp-6B4h]
  int v133; // [rsp+138h] [rbp-6B0h]
  int v134; // [rsp+13Ch] [rbp-6ACh]
  struct _IRP_CONTEXT *v135; // [rsp+140h] [rbp-6A8h] BYREF
  int v136; // [rsp+148h] [rbp-6A0h]
  int v137; // [rsp+14Ch] [rbp-69Ch]
  int v138; // [rsp+150h] [rbp-698h] BYREF
  char v139; // [rsp+154h] [rbp-694h]
  _QWORD v140[2]; // [rsp+158h] [rbp-690h] BYREF
  int v141; // [rsp+168h] [rbp-680h]
  int v142; // [rsp+170h] [rbp-678h]
  const wchar_t *v143; // [rsp+178h] [rbp-670h]
  int v144; // [rsp+180h] [rbp-668h]
  const wchar_t *v145; // [rsp+188h] [rbp-660h]
  int v146; // [rsp+190h] [rbp-658h]
  const wchar_t *v147; // [rsp+198h] [rbp-650h]
  int v148; // [rsp+1A0h] [rbp-648h]
  const wchar_t *v149; // [rsp+1A8h] [rbp-640h]
  int v150; // [rsp+1B0h] [rbp-638h]
  const wchar_t *v151; // [rsp+1B8h] [rbp-630h]
  int v152; // [rsp+1C0h] [rbp-628h]
  const wchar_t *v153; // [rsp+1C8h] [rbp-620h]
  int v154; // [rsp+1D0h] [rbp-618h]
  const wchar_t *v155; // [rsp+1D8h] [rbp-610h]
  int v156; // [rsp+1E0h] [rbp-608h]
  const wchar_t *v157; // [rsp+1E8h] [rbp-600h]
  int v158; // [rsp+1F0h] [rbp-5F8h]
  const wchar_t *v159; // [rsp+1F8h] [rbp-5F0h]
  int v160; // [rsp+200h] [rbp-5E8h]
  const wchar_t *v161; // [rsp+208h] [rbp-5E0h]
  int v162; // [rsp+210h] [rbp-5D8h]
  const wchar_t *v163; // [rsp+218h] [rbp-5D0h]
  int v164; // [rsp+220h] [rbp-5C8h]
  const wchar_t *v165; // [rsp+228h] [rbp-5C0h]
  int v166; // [rsp+230h] [rbp-5B8h]
  const wchar_t *v167; // [rsp+238h] [rbp-5B0h]
  int v168; // [rsp+240h] [rbp-5A8h]
  const wchar_t *v169; // [rsp+248h] [rbp-5A0h]
  int v170; // [rsp+250h] [rbp-598h]
  const wchar_t *v171; // [rsp+258h] [rbp-590h]
  int v172; // [rsp+260h] [rbp-588h]
  const wchar_t *v173; // [rsp+268h] [rbp-580h]
  int v174; // [rsp+270h] [rbp-578h]
  const wchar_t *v175; // [rsp+278h] [rbp-570h]
  int v176; // [rsp+280h] [rbp-568h]
  const wchar_t *v177; // [rsp+288h] [rbp-560h]
  int v178; // [rsp+290h] [rbp-558h]
  const wchar_t *v179; // [rsp+298h] [rbp-550h]
  int v180; // [rsp+2A0h] [rbp-548h]
  const wchar_t *v181; // [rsp+2A8h] [rbp-540h]
  int v182; // [rsp+2B0h] [rbp-538h]
  const wchar_t *v183; // [rsp+2B8h] [rbp-530h]
  int v184; // [rsp+2C0h] [rbp-528h]
  const wchar_t *v185; // [rsp+2C8h] [rbp-520h]
  int v186; // [rsp+2D0h] [rbp-518h]
  const wchar_t *v187; // [rsp+2D8h] [rbp-510h]
  int v188; // [rsp+2E0h] [rbp-508h]
  const wchar_t *v189; // [rsp+2E8h] [rbp-500h]
  int v190; // [rsp+2F0h] [rbp-4F8h]
  const wchar_t *v191; // [rsp+2F8h] [rbp-4F0h]
  int v192; // [rsp+300h] [rbp-4E8h]
  const wchar_t *v193; // [rsp+308h] [rbp-4E0h]
  int v194; // [rsp+310h] [rbp-4D8h]
  const wchar_t *v195; // [rsp+318h] [rbp-4D0h]
  int v196; // [rsp+320h] [rbp-4C8h]
  const wchar_t *v197; // [rsp+328h] [rbp-4C0h]
  int v198; // [rsp+330h] [rbp-4B8h]
  const wchar_t *v199; // [rsp+338h] [rbp-4B0h]
  int v200; // [rsp+340h] [rbp-4A8h]
  const wchar_t *v201; // [rsp+348h] [rbp-4A0h]
  int v202; // [rsp+350h] [rbp-498h]
  const wchar_t *v203; // [rsp+358h] [rbp-490h]
  int v204; // [rsp+360h] [rbp-488h]
  const wchar_t *v205; // [rsp+368h] [rbp-480h]
  int v206; // [rsp+370h] [rbp-478h]
  const wchar_t *v207; // [rsp+378h] [rbp-470h]
  int v208; // [rsp+380h] [rbp-468h]
  const wchar_t *v209; // [rsp+388h] [rbp-460h]
  int v210; // [rsp+390h] [rbp-458h]
  const wchar_t *v211; // [rsp+398h] [rbp-450h]
  int v212; // [rsp+3A0h] [rbp-448h]
  const wchar_t *v213; // [rsp+3A8h] [rbp-440h]
  int v214; // [rsp+3B0h] [rbp-438h]
  const wchar_t *v215; // [rsp+3B8h] [rbp-430h]
  int v216; // [rsp+3C0h] [rbp-428h]
  const wchar_t *v217; // [rsp+3C8h] [rbp-420h]
  int v218; // [rsp+3D0h] [rbp-418h]
  const wchar_t *v219; // [rsp+3D8h] [rbp-410h]
  int v220; // [rsp+3E0h] [rbp-408h]
  const wchar_t *v221; // [rsp+3E8h] [rbp-400h]
  int v222; // [rsp+3F0h] [rbp-3F8h]
  const wchar_t *v223; // [rsp+3F8h] [rbp-3F0h]
  int v224; // [rsp+400h] [rbp-3E8h]
  const wchar_t *v225; // [rsp+408h] [rbp-3E0h]
  __int128 v226; // [rsp+410h] [rbp-3D8h] BYREF
  __int64 v227; // [rsp+420h] [rbp-3C8h]
  __int64 v228; // [rsp+430h] [rbp-3B8h] BYREF
  __int64 v229; // [rsp+710h] [rbp-D8h] BYREF

  v135 = (struct _IRP_CONTEXT *)&v228;
  v226 = 0;
  v227 = 0;
  v92 = 0;
  v89 = 0;
  v65 = 0;
  v63 = 156;
  P = &v229;
  v61[0] = 0;
  v97 = dword_140261874;
  v120 = dword_140261874;
  v98 = dword_140261878;
  v121 = dword_140261878;
  v103 = dword_14026187C;
  v122 = dword_14026187C;
  v99 = dword_140261880;
  v132 = dword_140261880;
  v100 = dword_140261884;
  v124 = dword_140261884;
  v101 = dword_140261888;
  v125 = dword_140261888;
  v69 = RefsEnableParallelContainerRotation;
  v86 = RefsEnableParallelContainerRotation;
  v102 = RefsContainerRotationQueueSizeLimit;
  v126 = RefsContainerRotationQueueSizeLimit;
  v105 = RefsContainerRotationThreadCount;
  v127 = RefsContainerRotationThreadCount;
  v104 = RefsFailIncompleteLogRedo != 0;
  v128 = v104;
  v129 = dword_140262054;
  v137 = dword_140262054;
  v93 = 0;
  v1 = RefsInitializeTopLevelIrp((struct _TOP_LEVEL_CONTEXT *)&v226, 0, 0);
  v2 = RefsInitializeIrpContext(0, 1, 0, &v135);
  if ( v2 < 0 )
    return;
  v68 = 0;
  v67 = 0;
  v90 = 0;
  v130 = 0;
  v131 = 0;
  v133 = 0;
  v106 = 1;
  v107 = 0;
  v108 = 0;
  v123 = 0;
  v109 = -1;
  v78 = 0;
  v110 = -1;
  v83 = 0;
  v111 = -1;
  v79 = 0;
  v112 = -1;
  v80 = 0;
  v113 = -1;
  v81 = 0;
  v114 = -1;
  v82 = 0;
  v115 = -1;
  v88 = 0;
  v116 = -1;
  v84 = 0;
  v117 = -1;
  v85 = 0;
  v96 = 1;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v71 = 0;
  v70 = 0;
  v91 = 0;
  v118 = 0;
  v95 = 0;
  v94 = 0;
  v119 = 100;
  v136 = 0;
  v87 = 0;
  v134 = 30000;
  v66 = 0;
  v3 = v135;
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
  *(_QWORD *)&v92.Length = 6815846;
  v92.Buffer = (PWSTR)L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies";
  *(_QWORD *)&v89.Length = 8126586;
  v89.Buffer = (PWSTR)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem";
  do
  {
    if ( v2 == -1073741432 )
      RefsCheckpointForLogFileFull(v3);
    if ( v3 )
      RefsPreRequestProcessingExtend(v3, v5);
    LOBYTE(v6) = 1;
    ExAcquireFastResourceExclusive(qword_1402610B8, 0, v6);
    v68 = 1;
    v142 = 3932218;
    v143 = L"RefsDisableDeleteNotification";
    *(_QWORD *)&v65.Length = 3932218;
    v65.Buffer = L"RefsDisableDeleteNotification";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 < 0
      && (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 < 0) )
    {
      v7 = 0;
    }
    else
    {
      v7 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    if ( v7 == 1 )
    {
      if ( ((unsigned __int16)dword_1402612AC & 0x8000) == 0 )
      {
        v8 = (unsigned int)dword_1402612AC | 0x8000;
LABEL_18:
        LODWORD(dword_1402612AC) = v8;
        v67 = 1;
      }
    }
    else if ( ((unsigned __int16)dword_1402612AC & 0x8000) != 0 )
    {
      v8 = (unsigned int)dword_1402612AC & 0xFFFF7FFF;
      goto LABEL_18;
    }
    v144 = 3407922;
    v145 = L"RefsFailIncompleteLogRedo";
    *(_QWORD *)&v65.Length = 3407922;
    v65.Buffer = L"RefsFailIncompleteLogRedo";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v9 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v104 = v9;
      v128 = v9;
    }
    else
    {
      v9 = v104;
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
    byte_140262011 = v10;
    v146 = 4456514;
    v147 = L"RefsEnableBreakOnChecksumMismatch";
    *(_QWORD *)&v65.Length = 4456514;
    v65.Buffer = L"RefsEnableBreakOnChecksumMismatch";
    v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0 && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
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
    v148 = 3801144;
    v149 = L"RefsEnableMetadataValidation";
    *(_QWORD *)&v65.Length = 3801144;
    v65.Buffer = L"RefsEnableMetadataValidation";
    v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0 )
    {
      v12 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      LOBYTE(word_140261FD1) = v12 & 1;
      HIBYTE(word_140261FD1) = (v12 & 2) != 0;
    }
    v140[0] = 2883626;
    v140[1] = L"RefsDebugDisableFlags";
    RefsQueryValueKeyTyped<unsigned long>(&v138, &v89, v140);
    if ( v139 )
      dword_1402621A0 = v138;
    v150 = 3932218;
    v151 = L"RefsInvalidateOnFileLevelTrim";
    *(_QWORD *)&v65.Length = 3932218;
    v65.Buffer = L"RefsInvalidateOnFileLevelTrim";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 < 0
      && (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 < 0) )
    {
      v13 = 0;
    }
    else
    {
      v13 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    if ( dword_140261124 != (v13 < 3 ? v13 : 0) )
    {
      dword_140261124 = v13 < 3 ? v13 : 0;
      v90 = 1;
    }
    v152 = 2883626;
    v153 = L"EnableExtraIoAnalysis";
    *(_QWORD *)&v65.Length = 2883626;
    v65.Buffer = L"EnableExtraIoAnalysis";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v14 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v130 = v14;
    }
    else
    {
      LOBYTE(v14) = v130;
    }
    v15 = (v14 & 1) == 0;
    v16 = (int)dword_1402612AC;
    if ( v15 )
    {
      v17 = (unsigned int)dword_1402612AC & 0xFFFFFDFF;
    }
    else
    {
      LODWORD(dword_1402612AC) = (unsigned int)dword_1402612AC | 0x200;
      v17 = v16 | 0x600;
    }
    LODWORD(dword_1402612AC) = v17;
    v154 = 4718662;
    v155 = L"RefsEnableMetadataRetrievalPointers";
    *(_QWORD *)&v65.Length = 4718662;
    v65.Buffer = L"RefsEnableMetadataRetrievalPointers";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v18 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v131 = v18;
    }
    else
    {
      LOBYTE(v18) = v131;
    }
    if ( (v18 & 1) != 0 && (_BYTE)KdDebuggerEnabled )
      v19 = (unsigned int)dword_1402612AC | 0x20000;
    else
      v19 = (unsigned int)dword_1402612AC & 0xFFFDFFFF;
    LODWORD(dword_1402612AC) = v19;
    v156 = 3014700;
    v157 = L"RefsDisableAsyncDelete";
    *(_QWORD *)&v65.Length = 3014700;
    v65.Buffer = L"RefsDisableAsyncDelete";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v20 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v133 = v20;
    }
    else
    {
      LOBYTE(v20) = v133;
    }
    if ( (v20 & 1) != 0 )
      v21 = (unsigned int)dword_1402612AC & 0xFFDFFFFF;
    else
      v21 = (unsigned int)dword_1402612AC | 0x200000;
    LODWORD(dword_1402612AC) = v21;
    v158 = 3670070;
    v159 = L"RefsDisableLastAccessUpdate";
    *(_QWORD *)&v65.Length = 3670070;
    v65.Buffer = L"RefsDisableLastAccessUpdate";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v22 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v106 = v22;
    }
    else
    {
      v22 = v106;
    }
    if ( v22 == 1 )
      v23 = (unsigned int)dword_1402612AC | 0x40;
    else
      v23 = (unsigned int)dword_1402612AC & 0xFFFFFFBF;
    LODWORD(dword_1402612AC) = v23;
    v160 = 3276848;
    v161 = L"RefsDisableSqmThrottling";
    *(_QWORD *)&v65.Length = 3276848;
    v65.Buffer = L"RefsDisableSqmThrottling";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v24 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v107 = v24;
    }
    else
    {
      v24 = v107;
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
    v162 = 3276848;
    v163 = L"RefsDisableEtwThrottling";
    *(_QWORD *)&v65.Length = 3276848;
    v65.Buffer = L"RefsDisableEtwThrottling";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v25 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v108 = v25;
    }
    else
    {
      v25 = v108;
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
    v164 = 4063292;
    v165 = L"RefsDisableTelemetryThrottling";
    *(_QWORD *)&v65.Length = 4063292;
    v65.Buffer = L"RefsDisableTelemetryThrottling";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v26 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v123 = v26;
    }
    else
    {
      v26 = v123;
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
    v166 = 4980810;
    v167 = L"DataDestageSsdFillRatioEventThreshold";
    *(_QWORD *)&v65.Length = 4980810;
    v65.Buffer = L"DataDestageSsdFillRatioEventThreshold";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v27 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v101 = v27;
      v125 = v27;
    }
    else
    {
      v27 = v101;
    }
    if ( v27 <= 0x64 && v27 != dword_140261888 )
    {
      dword_140261888 = v27;
      v77 = 1;
    }
    v168 = 4325440;
    v169 = L"DataDestageSsdFillRatioThreshold";
    *(_QWORD *)&v65.Length = 4325440;
    v65.Buffer = L"DataDestageSsdFillRatioThreshold";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v28 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v97 = v28;
      v120 = v28;
    }
    else
    {
      v28 = v97;
    }
    if ( v28 <= 0x64 && v28 != dword_140261874 )
    {
      dword_140261874 = v28;
      v72 = 1;
    }
    v170 = 4849736;
    v171 = L"MetadataDestageSsdFillRatioThreshold";
    *(_QWORD *)&v65.Length = 4849736;
    v65.Buffer = L"MetadataDestageSsdFillRatioThreshold";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v29 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v98 = v29;
      v121 = v29;
    }
    else
    {
      v29 = v98;
    }
    if ( v29 <= 0x64 && v29 != dword_140261878 )
    {
      dword_140261878 = v29;
      v73 = 1;
    }
    v172 = 4325440;
    v173 = L"DataDestageHddFillRatioThreshold";
    *(_QWORD *)&v65.Length = 4325440;
    v65.Buffer = L"DataDestageHddFillRatioThreshold";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v30 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v103 = v30;
      v122 = v30;
    }
    else
    {
      v30 = v103;
    }
    if ( v30 <= 0x64 && v30 != dword_14026187C )
    {
      dword_14026187C = v30;
      v74 = 1;
    }
    v174 = 4849736;
    v175 = L"MetadataDestageHddFillRatioThreshold";
    *(_QWORD *)&v65.Length = 4849736;
    v65.Buffer = L"MetadataDestageHddFillRatioThreshold";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v31 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v99 = v31;
      v132 = v31;
    }
    else
    {
      v31 = v99;
    }
    if ( v31 <= 0x64 && v31 != dword_140261880 )
    {
      dword_140261880 = v31;
      v75 = 1;
    }
    v176 = 4063292;
    v177 = L"DataDestageCompactionThreshold";
    *(_QWORD *)&v65.Length = 4063292;
    v65.Buffer = L"DataDestageCompactionThreshold";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v32 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v100 = v32;
      v124 = v32;
    }
    else
    {
      v32 = v100;
    }
    if ( v32 <= 0x64 && v32 != dword_140261884 )
    {
      dword_140261884 = v32;
      v76 = 1;
    }
    v178 = 4718662;
    v179 = L"RefsEnableParallelContainerRotation";
    *(_QWORD *)&v65.Length = 4718662;
    v65.Buffer = L"RefsEnableParallelContainerRotation";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 < 0
      && (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 < 0) )
    {
      v33 = v69;
    }
    else
    {
      v33 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1;
      v69 = v33;
      v86 = v33;
    }
    if ( RefsEnableParallelContainerRotation != v33 )
    {
      RefsEnableParallelContainerRotation = v33;
      v71 = 1;
    }
    v180 = 5636180;
    v181 = L"RefsTableSetEntriesToNavigateBeforeCaching";
    *(_QWORD *)&v65.Length = 5636180;
    v65.Buffer = L"RefsTableSetEntriesToNavigateBeforeCaching";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 < 0
      && (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 < 0) )
    {
      v34 = v129;
    }
    else
    {
      v34 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v129 = v34;
      v137 = v34;
    }
    if ( v34 != dword_140262054 )
      dword_140262054 = v34;
    v182 = 4718662;
    v183 = L"RefsContainerRotationQueueSizeLimit";
    *(_QWORD *)&v65.Length = 4718662;
    v65.Buffer = L"RefsContainerRotationQueueSizeLimit";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v35 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v102 = v35;
      v126 = v35;
    }
    else
    {
      v35 = v102;
    }
    if ( RefsContainerRotationQueueSizeLimit != v35 )
    {
      RefsContainerRotationQueueSizeLimit = v35;
      v70 = 1;
    }
    v184 = 4325440;
    v185 = L"RefsContainerRotationThreadCount";
    *(_QWORD *)&v65.Length = 4325440;
    v65.Buffer = L"RefsContainerRotationThreadCount";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v36 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v105 = v36;
      v127 = v36;
    }
    else
    {
      v36 = v105;
    }
    if ( v36 != RefsContainerRotationThreadCount )
    {
      RefsContainerRotationThreadCount = v36;
      v91 = 1;
    }
    v186 = 3801144;
    v187 = L"RefsCheckpointSampleInterval";
    *(_QWORD *)&v65.Length = 3801144;
    v65.Buffer = L"RefsCheckpointSampleInterval";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v37 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v109 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v37 = v109;
    }
    if ( (_DWORD)v37 != -1 && RefsTelemetrySampling != 10000000 * v37 )
    {
      RefsTelemetrySampling = 10000000 * v37;
      v78 = 1;
    }
    v188 = 4194366;
    v189 = L"RefsBlockRefcountSampleInterval";
    *(_QWORD *)&v65.Length = 4194366;
    v65.Buffer = L"RefsBlockRefcountSampleInterval";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v38 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v110 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v38 = v110;
    }
    if ( (_DWORD)v38 != -1 && *(&RefsTelemetrySampling + 1) != 10000000 * v38 )
    {
      *(&RefsTelemetrySampling + 1) = 10000000 * v38;
      v83 = 1;
    }
    v190 = 4063292;
    v191 = L"RefsGhostExtentsSampleInterval";
    *(_QWORD *)&v65.Length = 4063292;
    v65.Buffer = L"RefsGhostExtentsSampleInterval";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v39 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v111 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v39 = v111;
    }
    if ( (_DWORD)v39 != -1 && qword_1402608C0 != 10000000 * v39 )
    {
      qword_1402608C0 = 10000000 * v39;
      v79 = 1;
    }
    v192 = 4325440;
    v193 = L"RefsStreamSnapshotSampleInterval";
    *(_QWORD *)&v65.Length = 4325440;
    v65.Buffer = L"RefsStreamSnapshotSampleInterval";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v40 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v112 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v40 = v112;
    }
    if ( (_DWORD)v40 != -1 && qword_1402608F8 != 10000000 * v40 )
    {
      qword_1402608F8 = 10000000 * v40;
      v80 = 1;
    }
    v194 = 4063292;
    v195 = L"RefsPerfCountersSampleInterval";
    *(_QWORD *)&v65.Length = 4063292;
    v65.Buffer = L"RefsPerfCountersSampleInterval";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 < 0 )
      v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    v196 = 4718662;
    v197 = L"RefsContainerRotationSampleInterval";
    *(_QWORD *)&v65.Length = 4718662;
    v65.Buffer = L"RefsContainerRotationSampleInterval";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v41 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v113 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v41 = v113;
    }
    if ( (_DWORD)v41 != -1 && qword_1402608D0 != 10000000 * v41 )
    {
      qword_1402608D0 = 10000000 * v41;
      v81 = 1;
    }
    v198 = 3670070;
    v199 = L"RefsReadCacheSampleInterval";
    *(_QWORD *)&v65.Length = 3670070;
    v65.Buffer = L"RefsReadCacheSampleInterval";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v42 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v114 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v42 = v114;
    }
    if ( (_DWORD)v42 != -1 && qword_1402608D8 != 10000000 * v42 )
    {
      qword_1402608D8 = 10000000 * v42;
      v82 = 1;
    }
    v200 = 3670070;
    v201 = L"RefsSmrUpdateSampleInterval";
    *(_QWORD *)&v65.Length = 3670070;
    v65.Buffer = L"RefsSmrUpdateSampleInterval";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v43 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v115 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v43 = v115;
    }
    if ( (_DWORD)v43 != -1 && (_QWORD)xmmword_1402608E0 != 10000000 * v43 )
    {
      *(_QWORD *)&xmmword_1402608E0 = 10000000 * v43;
      v88 = 1;
    }
    v202 = 2883626;
    v203 = L"RefsSmrSampleInterval";
    *(_QWORD *)&v65.Length = 2883626;
    v65.Buffer = L"RefsSmrSampleInterval";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v44 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v116 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v44 = v116;
    }
    if ( (_DWORD)v44 != -1 && *((_QWORD *)&xmmword_1402608E0 + 1) != 10000000 * v44 )
    {
      *((_QWORD *)&xmmword_1402608E0 + 1) = 10000000 * v44;
      v84 = 1;
    }
    v204 = 3932218;
    v205 = L"RefsLogFileFullSampleInterval";
    *(_QWORD *)&v65.Length = 3932218;
    v65.Buffer = L"RefsLogFileFullSampleInterval";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v45 = *(unsigned int *)((char *)P + *((unsigned int *)P + 2));
      v117 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    }
    else
    {
      v45 = v117;
    }
    if ( (_DWORD)v45 != -1 && qword_1402608F0 != 10000000 * v45 )
    {
      qword_1402608F0 = 10000000 * v45;
      v85 = 1;
    }
    v206 = 4194366;
    v207 = L"RefsDisableTrueAsyncCachedReads";
    *(_QWORD *)&v65.Length = 4194366;
    v65.Buffer = L"RefsDisableTrueAsyncCachedReads";
    v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0 )
    {
      v46 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      if ( v46 )
      {
        if ( v46 == 1 )
          byte_140261870 = 1;
      }
      else
      {
        byte_140261870 = 0;
      }
    }
    v208 = 3801144;
    v209 = L"RefsEnableDirCaseSensitivity";
    *(_QWORD *)&v65.Length = 3801144;
    v65.Buffer = L"RefsEnableDirCaseSensitivity";
    v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 < 0 )
      dword_14026188C = 3;
    else
      dword_14026188C = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    v210 = 2228256;
    v211 = L"FsEnableDevDrive";
    *(_QWORD *)&v65.Length = 2228256;
    v65.Buffer = L"FsEnableDevDrive";
    v48 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    v62 = v48;
    if ( v48 < 0 )
    {
      if ( (unsigned __int8)RtlIsFeatureEnabledForEnterprise((PDEVICE_OBJECT)0x2ADD198, v47, v49, v50) )
      {
        v51 = v96;
      }
      else
      {
        v51 = 0;
        v96 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_bee596de7a9331ebd70d5dc28c9a6eb9_Traceguids, 0);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(0, 0, "NtfsInit.c", 0x12B2u);
        v48 = 0;
        v62 = 0;
      }
    }
    else
    {
      v51 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v96 = v51;
    }
    if ( v48 >= 0 && !v51 )
      goto LABEL_255;
    v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0 )
    {
      v51 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v96 = v51;
    }
    if ( v51 )
      v52 = (unsigned int)dword_1402612AC | 0x2000000;
    else
LABEL_255:
      v52 = (unsigned int)dword_1402612AC & 0xFDFFFFFF;
    LODWORD(dword_1402612AC) = v52;
    v212 = 4325440;
    v213 = L"DisableAssociatedIrpAsyncPosting";
    *(_QWORD *)&v65.Length = 4325440;
    v65.Buffer = L"DisableAssociatedIrpAsyncPosting";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v53 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v118 = v53;
    }
    else
    {
      v53 = v118;
    }
    RefsDisableAssociatedIrpAsyncPosting = v53 != 0;
    v214 = 2359330;
    v215 = L"RefsDisableIoPerf";
    *(_QWORD *)&v65.Length = 2359330;
    v65.Buffer = L"RefsDisableIoPerf";
    v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0 )
    {
      v136 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v87 = 1;
    }
    v216 = 3276848;
    v217 = L"RefsMaxAcceptableLatency";
    *(_QWORD *)&v65.Length = 3276848;
    v65.Buffer = L"RefsMaxAcceptableLatency";
    v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 < 0 )
    {
      v55 = v66;
      v54 = v134;
    }
    else
    {
      v54 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v134 = v54;
      v55 = 1;
      v66 = 1;
    }
    if ( v55 )
    {
      if ( v54 == dword_1402673E4 || (unsigned int)(v54 - 1) > 0x1D4BF )
      {
        v55 = 0;
        v66 = 0;
      }
      else
      {
        v55 = v66;
      }
    }
    if ( v87 )
      IoPerfRegistryConfig = v136 != 0;
    if ( v55 )
      dword_1402673E4 = v54;
    v218 = 3538996;
    v219 = L"RefsParallelFlushThreshold";
    *(_QWORD *)&v65.Length = 3538996;
    v65.Buffer = L"RefsParallelFlushThreshold";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v56 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v94 = v56;
    }
    else
    {
      v56 = v95;
    }
    if ( v56 )
    {
      if ( v56 >= 0x64 )
      {
        if ( v56 > 0xF4240 )
          v56 = 1000000;
      }
      else
      {
        v56 = 100;
      }
    }
    else
    {
      v56 = 1000;
    }
    v94 = v56;
    v95 = v56;
    if ( dword_1402618C4 != v56 )
      dword_1402618C4 = v56;
    v220 = 3276848;
    v221 = L"RefsParallelFlushWorkers";
    *(_QWORD *)&v65.Length = 3276848;
    v65.Buffer = L"RefsParallelFlushWorkers";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v57 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v93 = v57;
    }
    else
    {
      v57 = v93;
    }
    if ( v57 )
    {
      if ( v57 > 2 * RefsNumberProcessors )
      {
        v57 = 2 * RefsNumberProcessors;
        v93 = 2 * RefsNumberProcessors;
      }
    }
    else
    {
      v57 = (RefsNumberProcessors >> 1) + 1;
      v93 = v57;
      v141 = 16;
      if ( v57 > 0x10 )
        v57 = 16;
      v93 = v57;
    }
    if ( dword_1402618C0 != v57 )
      dword_1402618C0 = v57;
    v222 = 4325440;
    v223 = L"RefsMaxQueuedDecompressWorkItems";
    *(_QWORD *)&v65.Length = 4325440;
    v65.Buffer = L"RefsMaxQueuedDecompressWorkItems";
    v62 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    if ( v62 >= 0
      || (v62 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61), v62 >= 0) )
    {
      v58 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v119 = v58;
    }
    else
    {
      v58 = v119;
    }
    if ( (unsigned int)(v58 - 1) > 0xFFFFFE )
    {
      dword_1402618D4 = 0xFFFFFF;
    }
    else if ( dword_1402618D4 != v58 )
    {
      dword_1402618D4 = v58;
    }
    v59 = Feature_NTFS_DirectoryChangeNotifyListDirectoryAccessCheck__private_IsEnabledDeviceUsageNoInline() != 0;
    v224 = 6553698;
    v225 = L"EnforceDirectoryChangeNotificationPermissionCheck";
    *(_QWORD *)&v65.Length = 6553698;
    v65.Buffer = L"EnforceDirectoryChangeNotificationPermissionCheck";
    v2 = RefsQueryValueKeyEx(&v92, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
    v62 = v2;
    if ( v2 < 0 )
    {
      v2 = RefsQueryValueKeyEx(&v89, 0, &v65, &v63, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v61);
      v62 = v2;
      v60 = (unsigned int *)P;
      if ( v2 < 0 )
        goto LABEL_310;
    }
    else
    {
      v60 = (unsigned int *)P;
    }
    v59 = *(unsigned int *)((char *)v60 + v60[2]);
LABEL_310:
    byte_1402618D8 = v59 != 0;
    ExReleaseFastResource(qword_1402610B8, 0);
    v68 = 0;
    if ( a1 )
    {
      if ( v67 )
        RefsForEachVcb(
          v3,
          0,
          (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateDeleteNotificationVolumeSetting,
          0,
          0);
      if ( v90 )
        RefsForEachVcb(
          v3,
          0,
          (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateFileLevelTrimVolumeSetting,
          0,
          0);
      if ( v91 || v70 || v71 )
      {
        dword_14026210C = RefsContainerRotationThreadCount;
        dword_140262110 = RefsContainerRotationQueueSizeLimit;
        byte_14026210A = RefsEnableParallelContainerRotation;
        RefsForEachVcb(
          v3,
          0,
          (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateContainerRotationThreadCount,
          0,
          0);
      }
      if ( v66 )
        IoPerfRegistryUpdateConfig();
    }
    if ( v72 || v73 || v74 || v75 || v76 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateContainerMoveThresholdsVolumeSetting,
        0,
        0);
    if ( v77 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateContainerMoveEventThresholdsVolumeSetting,
        0,
        0);
    if ( v78 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateCheckpointSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v83 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateBlockRefcountSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v79 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateGhostExtentsSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v80 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateStreamSnapshotSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v81 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateContainerRotationSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v82 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateReadCacheSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v88 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateSmrUpdateSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v84 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateSmrSampleIntervalVolumeSetting,
        0,
        1u);
    if ( v85 )
      RefsForEachVcb(
        v3,
        0,
        (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsUpdateLogFileFullSampleIntervalVolumeSetting,
        0,
        1u);
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v3, 0, 0);
  }
  while ( v2 == -1073741608 || v2 == -1073741432 );
  if ( v61[0] )
    ExFreePoolWithTag(v60, 0);
  ExReleaseFastResource(&RefsDynamicRegistrySettingsResource, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1402c9ab0  mov     r11, rsp
0x1402c9ab3  mov     [r11+10h], rbx
0x1402c9ab7  mov     [r11+18h], rsi
0x1402c9abb  mov     [r11+8], rcx
0x1402c9abf  push    rdi
0x1402c9ac0  push    r12
0x1402c9ac2  push    r13
0x1402c9ac4  push    r14
0x1402c9ac6  push    r15
0x1402c9ac8  sub     rsp, 7C0h
0x1402c9acf  mov     rax, cs:__security_cookie
0x1402c9ad6  xor     rax, rsp
0x1402c9ad9  mov     [rsp+7E8h+var_38], rax
0x1402c9ae1  lea     rax, [r11-3B8h]
0x1402c9ae8  mov     [r11-6A8h], rax
0x1402c9aef  xorps   xmm0, xmm0
0x1402c9af2  xor     eax, eax
0x1402c9af4  movups  [rsp+7E8h+var_3D8], xmm0
0x1402c9afc  mov     [r11-3C8h], rax
0x1402c9b03  movups  xmmword ptr [rsp+7E8h+var_760.Length], xmm0
0x1402c9b0b  xorps   xmm1, xmm1
0x1402c9b0e  movups  xmmword ptr [rsp+7E8h+var_778.Length], xmm1
0x1402c9b13  movups  xmmword ptr [rsp+7E8h+var_7A0.Length], xmm0
0x1402c9b18  mov     [rsp+7E8h+var_7B0], 9Ch
0x1402c9b20  lea     rax, [r11-0D8h]
0x1402c9b27  mov     [rsp+7E8h+P], rax
0x1402c9b2c  xor     ebx, ebx
0x1402c9b2e  mov     [rsp+7E8h+var_7B8], bl
0x1402c9b32  mov     eax, cs:dword_140261874
0x1402c9b38  mov     [rsp+7E8h+var_740], eax
0x1402c9b3f  mov     [rsp+7E8h+var_6E4], eax
0x1402c9b46  mov     eax, cs:dword_140261878
0x1402c9b4c  mov     [rsp+7E8h+var_73C], eax
0x1402c9b53  mov     [rsp+7E8h+var_6E0], eax
0x1402c9b5a  mov     eax, cs:dword_14026187C
0x1402c9b60  mov     [rsp+7E8h+var_728], eax
0x1402c9b67  mov     [rsp+7E8h+var_6DC], eax
0x1402c9b6e  mov     eax, cs:dword_140261880
0x1402c9b74  mov     [rsp+7E8h+var_738], eax
0x1402c9b7b  mov     [rsp+7E8h+var_6B4], eax
0x1402c9b82  mov     eax, cs:dword_140261884
0x1402c9b88  mov     [rsp+7E8h+var_734], eax
0x1402c9b8f  mov     [rsp+7E8h+var_6D4], eax
0x1402c9b96  mov     eax, cs:dword_140261888
0x1402c9b9c  mov     [rsp+7E8h+var_730], eax
0x1402c9ba3  mov     [rsp+7E8h+var_6D0], eax
0x1402c9baa  mov     al, cs:?RefsEnableParallelContainerRotation@@3EA; uchar RefsEnableParallelContainerRotation
0x1402c9bb0  mov     [rsp+7E8h+var_78D], al
0x1402c9bb4  mov     [rsp+7E8h+var_77C], al
0x1402c9bb8  mov     eax, cs:?RefsContainerRotationQueueSizeLimit@@3KA; ulong RefsContainerRotationQueueSizeLimit
0x1402c9bbe  mov     [rsp+7E8h+var_72C], eax
0x1402c9bc5  mov     [rsp+7E8h+var_6CC], eax
0x1402c9bcc  mov     eax, cs:?RefsContainerRotationThreadCount@@3KA; ulong RefsContainerRotationThreadCount
0x1402c9bd2  mov     [rsp+7E8h+var_720], eax
0x1402c9bd9  mov     [rsp+7E8h+var_6C8], eax
0x1402c9be0  mov     ecx, ebx
0x1402c9be2  cmp     cs:?RefsFailIncompleteLogRedo@@3EA, bl; uchar RefsFailIncompleteLogRedo
0x1402c9be8  setnz   cl
0x1402c9beb  mov     [rsp+7E8h+var_724], ecx
0x1402c9bf2  mov     [rsp+7E8h+var_6C4], ecx
0x1402c9bf9  mov     eax, cs:dword_140262054
0x1402c9bff  mov     [rsp+7E8h+var_6C0], eax
0x1402c9c06  mov     [rsp+7E8h+var_69C], eax
0x1402c9c0d  mov     [rsp+7E8h+var_750], ebx
0x1402c9c14  xor     r8d, r8d; unsigned __int8
0x1402c9c17  xor     edx, edx; unsigned __int8
0x1402c9c19  lea     rcx, [r11-3D8h]; struct _TOP_LEVEL_CONTEXT *
0x1402c9c20  call    ?RefsInitializeTopLevelIrp@@YAPEAU_TOP_LEVEL_CONTEXT@@PEAU1@EE@Z; RefsInitializeTopLevelIrp(_TOP_LEVEL_CONTEXT *,uchar,uchar)
0x1402c9c25  mov     rdi, rax
0x1402c9c28  lea     r9, [rsp+7E8h+var_6A8]; struct _IRP_CONTEXT **
0x1402c9c30  xor     r8d, r8d; unsigned __int8
0x1402c9c33  lea     r15d, [rbx+1]
0x1402c9c37  mov     dl, r15b; unsigned __int8
0x1402c9c3a  xor     ecx, ecx; Irp
0x1402c9c3c  call    ?RefsInitializeIrpContext@@YAJPEAU_IRP@@EEPEAPEAU_IRP_CONTEXT@@@Z; RefsInitializeIrpContext(_IRP *,uchar,uchar,_IRP_CONTEXT * *)
0x1402c9c41  mov     r14d, eax
0x1402c9c44  test    eax, eax
0x1402c9c46  js      loc_1402CC24B
0x1402c9c4c  mov     [rsp+7E8h+var_78E], bl
0x1402c9c50  mov     [rsp+7E8h+var_78F], bl
0x1402c9c54  mov     [rsp+7E8h+var_768], bl
0x1402c9c5b  mov     [rsp+7E8h+var_6BC], ebx
0x1402c9c62  mov     [rsp+7E8h+var_6B8], ebx
0x1402c9c69  mov     [rsp+7E8h+var_6B0], ebx
0x1402c9c70  mov     [rsp+7E8h+var_71C], r15d
0x1402c9c78  mov     [rsp+7E8h+var_718], ebx
0x1402c9c7f  mov     [rsp+7E8h+var_714], ebx
0x1402c9c86  mov     [rsp+7E8h+var_6D8], ebx
0x1402c9c8d  or      r12d, 0FFFFFFFFh
0x1402c9c91  mov     [rsp+7E8h+var_710], r12d
0x1402c9c99  mov     [rsp+7E8h+var_784], bl
0x1402c9c9d  mov     [rsp+7E8h+var_70C], r12d
0x1402c9ca5  mov     [rsp+7E8h+var_77F], bl
0x1402c9ca9  mov     [rsp+7E8h+var_708], r12d
0x1402c9cb1  mov     [rsp+7E8h+var_783], bl
0x1402c9cb5  mov     [rsp+7E8h+var_704], r12d
0x1402c9cbd  mov     [rsp+7E8h+var_782], bl
0x1402c9cc1  mov     [rsp+7E8h+var_700], r12d
0x1402c9cc9  mov     [rsp+7E8h+var_781], bl
0x1402c9ccd  mov     [rsp+7E8h+var_6FC], r12d
0x1402c9cd5  mov     [rsp+7E8h+var_780], bl
0x1402c9cd9  mov     [rsp+7E8h+var_6F8], r12d
0x1402c9ce1  mov     [rsp+7E8h+var_77A], bl
0x1402c9ce5  mov     [rsp+7E8h+var_6F4], r12d
0x1402c9ced  mov     [rsp+7E8h+var_77E], bl
0x1402c9cf1  mov     [rsp+7E8h+var_6F0], r12d
0x1402c9cf9  mov     [rsp+7E8h+var_77D], bl
0x1402c9cfd  mov     [rsp+7E8h+var_744], r15d
0x1402c9d05  mov     [rsp+7E8h+var_78A], bl
0x1402c9d09  mov     [rsp+7E8h+var_789], bl
0x1402c9d0d  mov     [rsp+7E8h+var_788], bl
0x1402c9d11  mov     [rsp+7E8h+var_787], bl
0x1402c9d15  mov     [rsp+7E8h+var_786], bl
0x1402c9d19  mov     [rsp+7E8h+var_785], bl
0x1402c9d1d  mov     [rsp+7E8h+var_78B], bl
0x1402c9d21  mov     [rsp+7E8h+var_78C], bl
0x1402c9d25  mov     [rsp+7E8h+var_767], bl
0x1402c9d2c  mov     [rsp+7E8h+var_6EC], ebx
0x1402c9d33  mov     [rsp+7E8h+var_748], ebx
0x1402c9d3a  mov     [rsp+7E8h+var_74C], ebx
0x1402c9d41  lea     esi, [rbx+64h]
0x1402c9d44  mov     [rsp+7E8h+var_6E8], esi
0x1402c9d4b  mov     [rsp+7E8h+var_6A0], ebx
0x1402c9d52  mov     [rsp+7E8h+var_77B], bl
0x1402c9d56  mov     [rsp+7E8h+var_6AC], 7530h
0x1402c9d61  mov     [rsp+7E8h+var_790], bl
0x1402c9d65  mov     r13, [rsp+7E8h+var_6A8]
0x1402c9d6d  cmp     [rdi+10h], rbx
0x1402c9d71  jnz     short loc_1402C9D93
0x1402c9d73  mov     dword ptr [rdi+4], 5346ABBAh
0x1402c9d7a  mov     [rdi+10h], r13
0x1402c9d7e  bts     qword ptr [r13+8], 14h
0x1402c9d84  mov     rcx, rdi; Irp
0x1402c9d87  call    cs:__imp_IoSetTopLevelIrp
0x1402c9d8e  nop     dword ptr [rax+rax+00h]
0x1402c9d93  mov     rax, [rdi+10h]
0x1402c9d97  mov     [r13+68h], rax
0x1402c9d9b  call    cs:__imp_KeEnterCriticalRegion
0x1402c9da2  nop     dword ptr [rax+rax+00h]
0x1402c9da7  mov     r8b, r15b
0x1402c9daa  xor     edx, edx
0x1402c9dac  lea     rcx, ?RefsDynamicRegistrySettingsResource@@3U_FAST_ERESOURCE@@A; _FAST_ERESOURCE RefsDynamicRegistrySettingsResource
0x1402c9db3  call    cs:__imp_ExAcquireFastResourceExclusive
0x1402c9dba  nop     dword ptr [rax+rax+00h]
0x1402c9dbf  mov     qword ptr [rsp+7E8h+var_760.Length], 680066h
0x1402c9dcb  lea     rax, aRegistryMachin_10; "\\Registry\\Machine\\System\\CurrentCon"...
0x1402c9dd2  mov     [rsp+7E8h+var_760.Buffer], rax
0x1402c9dda  mov     qword ptr [rsp+7E8h+var_778.Length], 7C007Ah
0x1402c9de3  lea     rax, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x1402c9dea  mov     [rsp+7E8h+var_778.Buffer], rax
0x1402c9def  mov     edi, 40h ; '@'
0x1402c9df4  jmp     short loc_1402C9DFB
0x1402c9df6  mov     esi, 64h ; 'd'
0x1402c9dfb  cmp     r14d, 0C0000188h
0x1402c9e02  jnz     short loc_1402C9E0C
0x1402c9e04  mov     rcx, r13; struct _IRP_CONTEXT *
0x1402c9e07  call    ?RefsCheckpointForLogFileFull@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointForLogFileFull(_IRP_CONTEXT *)
0x1402c9e0c  test    r13, r13
0x1402c9e0f  jz      short loc_1402C9E19
0x1402c9e11  mov     rcx, r13; struct _IRP_CONTEXT *
0x1402c9e14  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x1402c9e19  mov     r8b, r15b
0x1402c9e1c  xor     edx, edx
0x1402c9e1e  lea     rcx, qword_1402610B8
0x1402c9e25  call    cs:__imp_ExAcquireFastResourceExclusive
0x1402c9e2c  nop     dword ptr [rax+rax+00h]
0x1402c9e31  mov     [rsp+7E8h+var_78E], r15b
0x1402c9e36  mov     [rsp+7E8h+var_678], 3C003Ah
0x1402c9e41  lea     rdx, aRefsdisabledel; "RefsDisableDeleteNotification"
0x1402c9e48  mov     [rsp+7E8h+var_670], rdx
0x1402c9e50  mov     qword ptr [rsp+7E8h+var_7A0.Length], 3C003Ah
0x1402c9e59  mov     [rsp+7E8h+var_7A0.Buffer], rdx
0x1402c9e5e  lea     rax, [rsp+7E8h+var_7B8]
0x1402c9e63  mov     [rsp+7E8h+var_7C0], rax; unsigned __int8 *
0x1402c9e68  lea     rax, [rsp+7E8h+P]
0x1402c9e6d  mov     [rsp+7E8h+var_7C8], rax; struct _KEY_VALUE_FULL_INFORMATION **
0x1402c9e72  lea     r9, [rsp+7E8h+var_7B0]; unsigned int *
0x1402c9e77  lea     r8, [rsp+7E8h+var_7A0]; struct _UNICODE_STRING *
0x1402c9e7c  xor     edx, edx; void *
0x1402c9e7e  lea     rcx, [rsp+7E8h+var_760]; struct _UNICODE_STRING *
0x1402c9e86  call    ?RefsQueryValueKeyEx@@YAJPEAU_UNICODE_STRING@@PEAX0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKeyEx(_UNICODE_STRING *,void *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x1402c9e8b  mov     [rsp+7E8h+var_7B4], eax
0x1402c9e8f  test    eax, eax
0x1402c9e91  jns     short loc_1402C9EC5
0x1402c9e93  lea     rax, [rsp+7E8h+var_7B8]
0x1402c9e98  mov     [rsp+7E8h+var_7C0], rax; unsigned __int8 *
0x1402c9e9d  lea     rax, [rsp+7E8h+P]
0x1402c9ea2  mov     [rsp+7E8h+var_7C8], rax; struct _KEY_VALUE_FULL_INFORMATION **
0x1402c9ea7  lea     r9, [rsp+7E8h+var_7B0]; unsigned int *
0x1402c9eac  lea     r8, [rsp+7E8h+var_7A0]; struct _UNICODE_STRING *
0x1402c9eb1  xor     edx, edx; void *
0x1402c9eb3  lea     rcx, [rsp+7E8h+var_778]; struct _UNICODE_STRING *
0x1402c9eb8  call    ?RefsQueryValueKeyEx@@YAJPEAU_UNICODE_STRING@@PEAX0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKeyEx(_UNICODE_STRING *,void *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x1402c9ebd  mov     [rsp+7E8h+var_7B4], eax
0x1402c9ec1  test    eax, eax
0x1402c9ec3  js      short loc_1402C9ED2
0x1402c9ec5  mov     rcx, [rsp+7E8h+P]
0x1402c9eca  mov     eax, [rcx+8]
0x1402c9ecd  mov     edx, [rax+rcx]
0x1402c9ed0  jmp     short loc_1402C9ED4
0x1402c9ed2  mov     edx, ebx
0x1402c9ed4  mov     eax, cs:dword_1402612AC
0x1402c9eda  cmp     edx, r15d
0x1402c9edd  jnz     short loc_1402C9EEC
0x1402c9edf  mov     ecx, 8000h
0x1402c9ee4  test    ecx, eax
0x1402c9ee6  jnz     short loc_1402C9F01
0x1402c9ee8  or      eax, ecx
0x1402c9eea  jmp     short loc_1402C9EF6
0x1402c9eec  bt      eax, 0Fh
0x1402c9ef0  jnb     short loc_1402C9F01
0x1402c9ef2  btr     eax, 0Fh
0x1402c9ef6  mov     cs:dword_1402612AC, eax
0x1402c9efc  mov     [rsp+7E8h+var_78F], r15b
0x1402c9f01  mov     [rsp+7E8h+var_668], 340032h
0x1402c9f0c  lea     rdx, aRefsfailincomp; "RefsFailIncompleteLogRedo"
0x1402c9f13  mov     [rsp+7E8h+var_660], rdx
0x1402c9f1b  mov     qword ptr [rsp+7E8h+var_7A0.Length], 340032h
0x1402c9f24  mov     [rsp+7E8h+var_7A0.Buffer], rdx
0x1402c9f29  lea     rax, [rsp+7E8h+var_7B8]
0x1402c9f2e  mov     [rsp+7E8h+var_7C0], rax; unsigned __int8 *
0x1402c9f33  lea     rax, [rsp+7E8h+P]
0x1402c9f38  mov     [rsp+7E8h+var_7C8], rax; struct _KEY_VALUE_FULL_INFORMATION **
0x1402c9f3d  lea     r9, [rsp+7E8h+var_7B0]; unsigned int *
0x1402c9f42  lea     r8, [rsp+7E8h+var_7A0]; struct _UNICODE_STRING *
0x1402c9f47  xor     edx, edx; void *
0x1402c9f49  lea     rcx, [rsp+7E8h+var_760]; struct _UNICODE_STRING *
0x1402c9f51  call    ?RefsQueryValueKeyEx@@YAJPEAU_UNICODE_STRING@@PEAX0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKeyEx(_UNICODE_STRING *,void *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x1402c9f56  mov     [rsp+7E8h+var_7B4], eax
0x1402c9f5a  test    eax, eax
0x1402c9f5c  js      short loc_1402C9F79
0x1402c9f5e  mov     rcx, [rsp+7E8h+P]
0x1402c9f63  mov     eax, [rcx+8]
0x1402c9f66  mov     eax, [rax+rcx]
0x1402c9f69  mov     [rsp+7E8h+var_724], eax
0x1402c9f70  mov     [rsp+7E8h+var_6C4], eax
0x1402c9f77  jmp     short loc_1402C9FB2
0x1402c9f79  lea     rax, [rsp+7E8h+var_7B8]
0x1402c9f7e  mov     [rsp+7E8h+var_7C0], rax; unsigned __int8 *
0x1402c9f83  lea     rax, [rsp+7E8h+P]
0x1402c9f88  mov     [rsp+7E8h+var_7C8], rax; struct _KEY_VALUE_FULL_INFORMATION **
0x1402c9f8d  lea     r9, [rsp+7E8h+var_7B0]; unsigned int *
0x1402c9f92  lea     r8, [rsp+7E8h+var_7A0]; struct _UNICODE_STRING *
0x1402c9f97  xor     edx, edx; void *
0x1402c9f99  lea     rcx, [rsp+7E8h+var_778]; struct _UNICODE_STRING *
0x1402c9f9e  call    ?RefsQueryValueKeyEx@@YAJPEAU_UNICODE_STRING@@PEAX0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKeyEx(_UNICODE_STRING *,void *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x1402c9fa3  mov     [rsp+7E8h+var_7B4], eax
0x1402c9fa7  test    eax, eax
0x1402c9fa9  jns     short loc_1402C9F5E
0x1402c9fab  mov     eax, [rsp+7E8h+var_724]
0x1402c9fb2  cmp     eax, r15d
0x1402c9fb5  jnz     short loc_1402C9FC3
0x1402c9fb7  mov     cs:?RefsFailIncompleteLogRedo@@3EA, r15b; uchar RefsFailIncompleteLogRedo
0x1402c9fbe  mov     al, r15b
0x1402c9fc1  jmp     short loc_1402C9FCB
0x1402c9fc3  mov     cs:?RefsFailIncompleteLogRedo@@3EA, bl; uchar RefsFailIncompleteLogRedo
0x1402c9fc9  mov     al, bl
0x1402c9fcb  mov     cs:byte_140262011, al
0x1402c9fd1  mov     [rsp+7E8h+var_658], 440042h
0x1402c9fdc  lea     rax, aRefsenablebrea; "RefsEnableBreakOnChecksumMismatch"
0x1402c9fe3  mov     [rsp+7E8h+var_650], rax
0x1402c9feb  mov     qword ptr [rsp+7E8h+var_7A0.Length], 440042h
0x1402c9ff4  mov     [rsp+7E8h+var_7A0.Buffer], rax
0x1402c9ff9  lea     rax, [rsp+7E8h+var_7B8]
0x1402c9ffe  mov     [rsp+7E8h+var_7C0], rax; unsigned __int8 *
0x1402ca003  lea     rax, [rsp+7E8h+P]
0x1402ca008  mov     [rsp+7E8h+var_7C8], rax; struct _KEY_VALUE_FULL_INFORMATION **
0x1402ca00d  lea     r9, [rsp+7E8h+var_7B0]; unsigned int *
0x1402ca012  lea     r8, [rsp+7E8h+var_7A0]; struct _UNICODE_STRING *
0x1402ca017  xor     edx, edx; void *
0x1402ca019  lea     rcx, [rsp+7E8h+var_778]; struct _UNICODE_STRING *
0x1402ca01e  call    ?RefsQueryValueKeyEx@@YAJPEAU_UNICODE_STRING@@PEAX0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKeyEx(_UNICODE_STRING *,void *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x1402ca023  mov     [rsp+7E8h+var_7B4], eax
0x1402ca027  test    eax, eax
0x1402ca029  js      short loc_1402CA044
0x1402ca02b  mov     rcx, [rsp+7E8h+P]
0x1402ca030  mov     eax, [rcx+8]
0x1402ca033  cmp     [rax+rcx], r15d
0x1402ca037  jnz     short loc_1402CA044
0x1402ca039  mov     al, r15b
0x1402ca03c  mov     cs:?RefsEnableBreakOnChecksumMismatch@@3EA, al; uchar RefsEnableBreakOnChecksumMismatch
0x1402ca042  jmp     short loc_1402CA04C
0x1402ca044  mov     al, bl
0x1402ca046  mov     cs:?RefsEnableBreakOnChecksumMismatch@@3EA, bl; uchar RefsEnableBreakOnChecksumMismatch
0x1402ca04c  mov     cs:MsControl, al
0x1402ca052  mov     [rsp+7E8h+var_648], 3A0038h
0x1402ca05d  lea     rdx, aRefsenablemeta_0; "RefsEnableMetadataValidation"
0x1402ca064  mov     [rsp+7E8h+var_640], rdx
0x1402ca06c  mov     qword ptr [rsp+7E8h+var_7A0.Length], 3A0038h
0x1402ca075  mov     [rsp+7E8h+var_7A0.Buffer], rdx
0x1402ca07a  lea     rax, [rsp+7E8h+var_7B8]
0x1402ca07f  mov     [rsp+7E8h+var_7C0], rax; unsigned __int8 *
0x1402ca084  lea     rax, [rsp+7E8h+P]
0x1402ca089  mov     [rsp+7E8h+var_7C8], rax; struct _KEY_VALUE_FULL_INFORMATION **
0x1402ca08e  lea     r9, [rsp+7E8h+var_7B0]; unsigned int *
0x1402ca093  lea     r8, [rsp+7E8h+var_7A0]; struct _UNICODE_STRING *
0x1402ca098  xor     edx, edx; void *
0x1402ca09a  lea     rcx, [rsp+7E8h+var_778]; struct _UNICODE_STRING *
0x1402ca09f  call    ?RefsQueryValueKeyEx@@YAJPEAU_UNICODE_STRING@@PEAX0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKeyEx(_UNICODE_STRING *,void *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x1402ca0a4  mov     [rsp+7E8h+var_7B4], eax
  ... truncated ...
```
