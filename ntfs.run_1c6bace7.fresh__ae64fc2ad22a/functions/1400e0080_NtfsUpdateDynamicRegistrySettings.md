# NtfsUpdateDynamicRegistrySettings

- ea: `0x1400e0080`
- end: `0x1400e2473`
- name: `NtfsUpdateDynamicRegistrySettings`
- size: `9203`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1402d3458`

## callees

- `0x1400082b0`
- `0x140012ab0`
- `0x140016ea0`
- `0x140017030`
- `0x140017480`
- `0x1400291f0`
- `0x140029d80`
- `0x140030a80`
- `0x14003e468`
- `0x140059250`
- `0x1400596c0`
- `0x1400e0080`
- `0x14011bd84`
- `0x14013ad80`
- `0x1401aa6dc`
- `0x14025253c`
- `0x1402525a8`
- `0x140290cac`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e01fc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e01fc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e2439`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e2439`
- `ntoskrnl!FsRtlIsMobileOS` at `0x1400e20d5`
- `ntoskrnl!FsRtlIsMobileOS` at `0x1400e20d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e03ea`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e03ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e241a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e241a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400e0212`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400e1c97`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400e0212`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400e1c97`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400e21a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400e22f2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400e242d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400e21a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400e22f2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400e242d`

## string_xrefs

- `0x1400e042b`: `DisableDeleteNotification`
- `0x1400e04c8`: `DisableDeleteNotificationDrain`
- `0x1400e05be`: `NtfsDisableLastAccessUpdate`
- `0x1400e0681`: `NtfsLastAccessUpdatePolicyVolumeSizeThreshold`
- `0x1400e06dc`: `NtfsForceReadOnlyMount`
- `0x1400e07dd`: `NtfsDisableCompressionDelayedAllocation`
- `0x1400e0884`: `NtfsDisableCompressionLimit`
- `0x1400e0a78`: `NtfsMaxFspWorkerThreadsPerVolume`
- `0x1400e0cd8`: `NtfsFlushTrimRequestsOnDismount`
- `0x1400e0d3c`: `NtfsAllowMaximumSupportedHardLinks`
- `0x1400e0da0`: `NtfsDisableTrueAsyncCachedReads`
- `0x1400e0e7e`: `NtfsMaxFileMetadataOptimizationThread`
- `0x1400e0ef9`: `NtfsEnableDirectAccess`
- `0x1400e0fb4`: `NtfsAllowQueryFreeSpaceConsiderPool`
- `0x1400e100f`: `AllowHardLinkWithNoAccess`
- `0x1400e1729`: `NtfsCachedRunsBinMaxLengthInBytes`
- `0x1400e1899`: `NtfsMaxCachedRuns`
- `0x1400e1928`: `NtfsInitialCachedRuns`
- `0x1400e19ad`: `NtfsCachedRunsDelta`
- `0x1400e1a6e`: `NtfsCachedRunsLimitMode`
- `0x1400e1ade`: `NtfsCachedRunsInsertLimit`
- `0x1400e1bfe`: `EnforceDirectoryChangeNotificationPermissionCheck`

## pseudocode

```c
void __fastcall NtfsUpdateDynamicRegistrySettings(__int64 a1)
{
  unsigned int *v1; // rsi
  unsigned int v2; // r15d
  __int64 v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rdi
  int v6; // r14d
  unsigned int v7; // r13d
  char v8; // si
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // r15d
  unsigned int v13; // r13d
  unsigned int v14; // edi
  unsigned int v15; // edi
  unsigned int v16; // edi
  unsigned int v17; // edi
  unsigned int v18; // edi
  unsigned int v19; // edi
  unsigned int v20; // edi
  unsigned int v21; // eax
  int v22; // ecx
  unsigned int v23; // eax
  unsigned __int64 v24; // rdi
  unsigned int v25; // esi
  unsigned int v26; // edi
  unsigned int v27; // edi
  int v28; // ecx
  unsigned int v29; // edi
  int v30; // r15d
  int v31; // edi
  unsigned int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  unsigned int v38; // ecx
  int v39; // ecx
  __int64 v40; // rcx
  unsigned int v41; // eax
  unsigned int v42; // r13d
  char v43; // r13
  int v44; // eax
  unsigned int v45; // r8d
  bool v46; // zf
  int v47; // eax
  int v48; // ecx
  int v49; // edi
  _BYTE v50[8]; // [rsp+30h] [rbp-498h] BYREF
  unsigned int *v51; // [rsp+38h] [rbp-490h] BYREF
  int v52; // [rsp+40h] [rbp-488h] BYREF
  int ValueKeyWithFallBack; // [rsp+44h] [rbp-484h]
  __int128 v54; // [rsp+48h] [rbp-480h] BYREF
  char v55; // [rsp+58h] [rbp-470h]
  char v56; // [rsp+59h] [rbp-46Fh]
  char v57; // [rsp+5Ah] [rbp-46Eh]
  char v58; // [rsp+5Bh] [rbp-46Dh]
  char v59; // [rsp+5Ch] [rbp-46Ch]
  char v60; // [rsp+5Dh] [rbp-46Bh]
  char v61; // [rsp+5Eh] [rbp-46Ah]
  char v62; // [rsp+5Fh] [rbp-469h]
  char v63; // [rsp+60h] [rbp-468h]
  char v64; // [rsp+61h] [rbp-467h]
  char v65; // [rsp+62h] [rbp-466h]
  char v66; // [rsp+63h] [rbp-465h]
  char v67; // [rsp+64h] [rbp-464h]
  char v68; // [rsp+65h] [rbp-463h]
  __int128 v69; // [rsp+68h] [rbp-460h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-450h] BYREF
  unsigned int v71; // [rsp+88h] [rbp-440h]
  int v72; // [rsp+8Ch] [rbp-43Ch]
  unsigned int v73; // [rsp+90h] [rbp-438h]
  int v74; // [rsp+94h] [rbp-434h]
  int v75; // [rsp+98h] [rbp-430h]
  int v76; // [rsp+9Ch] [rbp-42Ch]
  int v77; // [rsp+A0h] [rbp-428h]
  int v78; // [rsp+A4h] [rbp-424h]
  unsigned int v79; // [rsp+A8h] [rbp-420h]
  int v80; // [rsp+ACh] [rbp-41Ch]
  int v81; // [rsp+B0h] [rbp-418h]
  int v82; // [rsp+B4h] [rbp-414h]
  int v83; // [rsp+B8h] [rbp-410h]
  unsigned int v84; // [rsp+BCh] [rbp-40Ch]
  int v85; // [rsp+C0h] [rbp-408h]
  int v86; // [rsp+C4h] [rbp-404h]
  int v87; // [rsp+C8h] [rbp-400h]
  __int128 v88; // [rsp+D0h] [rbp-3F8h] BYREF
  unsigned int v89; // [rsp+E0h] [rbp-3E8h]
  unsigned int v90; // [rsp+E4h] [rbp-3E4h]
  int v91; // [rsp+E8h] [rbp-3E0h]
  int v92; // [rsp+ECh] [rbp-3DCh]
  int v93; // [rsp+F0h] [rbp-3D8h]
  int v94; // [rsp+F4h] [rbp-3D4h]
  int v95; // [rsp+F8h] [rbp-3D0h]
  int v96; // [rsp+FCh] [rbp-3CCh]
  int v97; // [rsp+100h] [rbp-3C8h]
  int v98; // [rsp+104h] [rbp-3C4h]
  int v99; // [rsp+108h] [rbp-3C0h]
  _BYTE *v100; // [rsp+110h] [rbp-3B8h] BYREF
  int v101; // [rsp+118h] [rbp-3B0h]
  int v102; // [rsp+11Ch] [rbp-3ACh]
  int v103; // [rsp+120h] [rbp-3A8h]
  int v104; // [rsp+124h] [rbp-3A4h]
  int v105; // [rsp+128h] [rbp-3A0h]
  int v106; // [rsp+12Ch] [rbp-39Ch]
  int v107; // [rsp+130h] [rbp-398h]
  int v108; // [rsp+134h] [rbp-394h]
  int v109; // [rsp+138h] [rbp-390h]
  int v110; // [rsp+13Ch] [rbp-38Ch]
  int v111; // [rsp+140h] [rbp-388h]
  int v112; // [rsp+144h] [rbp-384h]
  unsigned int v113; // [rsp+148h] [rbp-380h]
  int v114; // [rsp+14Ch] [rbp-37Ch]
  unsigned int v115; // [rsp+150h] [rbp-378h]
  unsigned int v116; // [rsp+154h] [rbp-374h]
  int v117; // [rsp+158h] [rbp-370h]
  int v118; // [rsp+15Ch] [rbp-36Ch]
  int v119; // [rsp+160h] [rbp-368h]
  int v120; // [rsp+164h] [rbp-364h]
  unsigned int v121; // [rsp+168h] [rbp-360h]
  int v122; // [rsp+16Ch] [rbp-35Ch]
  __int64 v123; // [rsp+170h] [rbp-358h]
  __int64 v124; // [rsp+178h] [rbp-350h]
  int v125; // [rsp+180h] [rbp-348h]
  int v126; // [rsp+184h] [rbp-344h]
  int v127; // [rsp+188h] [rbp-340h]
  _OWORD v128[2]; // [rsp+190h] [rbp-338h] BYREF
  __int64 v129; // [rsp+1B0h] [rbp-318h]
  _BYTE v130[560]; // [rsp+1C0h] [rbp-308h] BYREF
  _BYTE P[160]; // [rsp+3F0h] [rbp-D8h] BYREF

  memset(v130, 0, 0x228u);
  v100 = v130;
  memset(v128, 0, sizeof(v128));
  v129 = 0;
  v88 = 0;
  DestinationString = 0;
  v69 = 0;
  v54 = 0;
  v52 = 156;
  v1 = (unsigned int *)P;
  v51 = (unsigned int *)P;
  v50[0] = 0;
  v78 = 65534;
  v75 = 32;
  v74 = 32;
  v77 = 512;
  v76 = 512;
  v2 = 0x4000;
  v85 = 0x4000;
  if ( byte_1400951DA != 1 )
  {
    v75 = 512;
    v74 = 512;
    v77 = 0x2000;
    v76 = 0x2000;
    v2 = 0x4000;
  }
  v3 = NtfsInitializeTopLevelIrp(v128, 0, 0);
  memset(v130, 0, 0x228u);
  if ( (int)NtfsInitializeIrpContextInternal(0, 1, 0, (__int64 *)&v100) >= 0 )
  {
    v4 = v3;
    v5 = (__int64)v100;
    NtfsUpdateIrpContextWithTopLevel(v100, v4);
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&NtfsDynamicRegistrySettingsResource, 1u);
    v88 = *(_OWORD *)L"fh";
    v6 = NtfsInitializeCompatibilityModeKeyPath();
    if ( v6 >= 0 )
    {
      v61 = 0;
      v106 = 0;
      v59 = 0;
      v112 = 0;
      v65 = 0;
      v107 = 0;
      v104 = 1;
      v103 = 1;
      v90 = 0;
      v89 = 0;
      v79 = 16;
      v91 = 16;
      v66 = 0;
      v7 = 1;
      v92 = 1;
      v67 = 0;
      v94 = 1;
      v93 = 1;
      v68 = 0;
      v84 = 0;
      v62 = 0;
      v117 = 0;
      v63 = 0;
      v99 = 70;
      v101 = 8;
      v126 = 100000;
      v127 = 25;
      v56 = 0;
      v57 = 0;
      v118 = 0;
      v64 = 0;
      v95 = -2147483645;
      v105 = -2147483645;
      v113 = 0;
      v119 = 3;
      v120 = 0;
      v81 = 0;
      v80 = 0;
      v72 = 0;
      v71 = 0;
      v87 = 0;
      v86 = 0;
      v83 = 0;
      v82 = 0;
      v109 = 0;
      v58 = 0;
      v102 = 30000;
      v8 = 0;
      v55 = 0;
      v97 = 2;
      v96 = 2;
      v73 = 0x4000;
      v98 = 0x4000;
      v110 = 0;
      v124 = 0x40000000;
      v123 = 0x40000000;
      v111 = 4;
      v60 = 0;
      RtlInitUnicodeString(&DestinationString, &NtfsCompatibilityModeKeyPath);
      v69 = *(_OWORD *)L"z|";
      while ( 1 )
      {
        if ( v6 == -1073741432 )
          NtfsCheckpointForLogFileFull(v5);
        if ( v5 )
          NtfsPreRequestProcessingExtend(v5);
        *((_QWORD *)&v54 + 1) = L"DisableDeleteNotification";
        LODWORD(v54) = 3407922;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack < 0 )
        {
          ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                   (unsigned int)&DestinationString,
                                   (unsigned int)&v69,
                                   (unsigned int)&v54,
                                   (unsigned int)&v52,
                                   (__int64)&v51,
                                   (__int64)v50);
          if ( ValueKeyWithFallBack >= 0 )
            v106 = *(unsigned int *)((char *)v51 + v51[2]);
        }
        else
        {
          v106 = *(unsigned int *)((char *)v51 + v51[2]);
        }
        *((_QWORD *)&v54 + 1) = L"DisableDeleteNotificationDrain";
        LODWORD(v54) = 4063292;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack >= 0 )
          v112 = *(unsigned int *)((char *)v51 + v51[2]);
        *((_QWORD *)&v54 + 1) = L"NtfsDisable8dot3NameCreation";
        LODWORD(v54) = 3801144;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack < 0
          && (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v69,
                                       (unsigned int)&v54,
                                       (unsigned int)&v52,
                                       (__int64)&v51,
                                       (__int64)v50),
              ValueKeyWithFallBack < 0) )
        {
          v9 = 2;
        }
        else
        {
          v9 = *(unsigned int *)((char *)v51 + v51[2]);
        }
        if ( v9 > 3 )
          v9 = 2;
        v125 = v9;
        *((_QWORD *)&v54 + 1) = L"NtfsDisableLastAccessUpdate";
        LODWORD(v54) = 3670070;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack < 0 )
        {
          ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                   (unsigned int)&DestinationString,
                                   (unsigned int)&v69,
                                   (unsigned int)&v54,
                                   (unsigned int)&v52,
                                   (__int64)&v51,
                                   (__int64)v50);
          if ( ValueKeyWithFallBack >= 0 )
          {
            v95 = *(unsigned int *)((char *)v51 + v51[2]) & 0x80000003;
            v105 = v95;
          }
        }
        else
        {
          v95 = *(unsigned int *)((char *)v51 + v51[2]) & 1;
          v105 = v95;
          dword_140095AC4 |= 0x40000000u;
        }
        *((_QWORD *)&v54 + 1) = L"NtfsLastAccessUpdatePolicyVolumeSizeThreshold";
        LODWORD(v54) = 6029402;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack >= 0 )
          v113 = *(unsigned int *)((char *)v51 + v51[2]);
        *((_QWORD *)&v54 + 1) = L"NtfsForceReadOnlyMount";
        LODWORD(v54) = 3014700;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack < 0 )
          v114 = 0;
        else
          v114 = *(unsigned int *)((char *)v51 + v51[2]);
        *((_QWORD *)&v54 + 1) = L"NtfsDisableFileMetadataOptimization";
        LODWORD(v54) = 4718662;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack < 0 )
        {
          ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                   (unsigned int)&DestinationString,
                                   (unsigned int)&v69,
                                   (unsigned int)&v54,
                                   (unsigned int)&v52,
                                   (__int64)&v51,
                                   (__int64)v50);
          if ( ValueKeyWithFallBack >= 0 )
            v107 = *(unsigned int *)((char *)v51 + v51[2]);
        }
        else
        {
          v107 = *(unsigned int *)((char *)v51 + v51[2]);
        }
        *((_QWORD *)&v54 + 1) = L"NtfsDisableCompressionDelayedAllocation";
        LODWORD(v54) = 5242958;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v69,
                                       (unsigned int)&v54,
                                       (unsigned int)&v52,
                                       (__int64)&v51,
                                       (__int64)v50),
              ValueKeyWithFallBack >= 0) )
        {
          v10 = *(unsigned int *)((char *)v51 + v51[2]);
          v103 = v10;
        }
        else
        {
          v10 = v104;
        }
        if ( v10 > 1 )
          v10 = 1;
        v104 = v10;
        v103 = v10;
        *((_QWORD *)&v54 + 1) = L"NtfsDisableCompressionLimit";
        LODWORD(v54) = 3670070;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v69,
                                       (unsigned int)&v54,
                                       (unsigned int)&v52,
                                       (__int64)&v51,
                                       (__int64)v50),
              ValueKeyWithFallBack >= 0) )
        {
          v11 = *(unsigned int *)((char *)v51 + v51[2]);
          v89 = v11;
        }
        else
        {
          v11 = v90;
        }
        if ( v11 > 1 )
          v11 = 0;
        v90 = v11;
        v89 = v11;
        *((_QWORD *)&v54 + 1) = L"NtfsDisableSpotCorruptionHandling";
        LODWORD(v54) = 4456514;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack < 0 )
        {
          ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                   (unsigned int)&DestinationString,
                                   (unsigned int)&v69,
                                   (unsigned int)&v54,
                                   (unsigned int)&v52,
                                   (__int64)&v51,
                                   (__int64)v50);
          if ( ValueKeyWithFallBack >= 0 )
          {
            v79 = *(unsigned int *)((char *)v51 + v51[2]);
            v91 = v79;
          }
        }
        else
        {
          v79 = *(unsigned int *)((char *)v51 + v51[2]);
          v91 = v79;
        }
        *((_QWORD *)&v54 + 1) = L"NtfsBypassSpotCorruptionHandlingOnCritical";
        LODWORD(v54) = 5636180;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v69,
                                       (unsigned int)&v54,
                                       (unsigned int)&v52,
                                       (__int64)&v51,
                                       (__int64)v50),
              ValueKeyWithFallBack >= 0) )
        {
          v7 = *(unsigned int *)((char *)v51 + v51[2]);
          v92 = v7;
        }
        if ( v7 > 0xF )
          v7 = 1;
        v121 = v7;
        v92 = v7;
        *((_QWORD *)&v54 + 1) = L"NtfsMaxFspWorkerThreadsPerVolume";
        LODWORD(v54) = 4325440;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v12 = *(unsigned int *)((char *)v51 + v51[2]);
          v84 = v12;
          if ( v12 )
          {
            if ( v12 >= 4 )
            {
              if ( v12 > 0x3E8 )
                v12 = 1000;
              v84 = v12;
            }
            else
            {
              v84 = 4;
            }
          }
          else
          {
            v84 = 10;
          }
          v62 = 1;
          v2 = v73;
        }
        *((_QWORD *)&v54 + 1) = L"NtfsMinTrimTotalSize";
        LODWORD(v54) = 2752552;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack < 0 )
        {
          v13 = 0x100000;
        }
        else
        {
          v13 = *(unsigned int *)((char *)v51 + v51[2]);
          if ( v13 < 0x200000 )
            v13 = 0x200000;
        }
        *((_QWORD *)&v54 + 1) = L"NtfsMaxTrimTotalSize";
        LODWORD(v54) = 2752552;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack < 0 )
        {
          v115 = 0x40000000;
        }
        else
        {
          v14 = *(unsigned int *)((char *)v51 + v51[2]);
          if ( v14 < NtfsMinTrimTotalSize )
            v14 = NtfsMinTrimTotalSize;
          v115 = v14;
        }
        *((_QWORD *)&v54 + 1) = L"NtfsTrimListLengthThreshold";
        LODWORD(v54) = 3670070;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack < 0 )
        {
          v122 = 100000;
        }
        else
        {
          v122 = *(unsigned int *)((char *)v51 + v51[2]);
          if ( (unsigned int)(v122 - 1) <= 0x270E )
            goto LABEL_81;
        }
        v57 = 1;
LABEL_81:
        *((_QWORD *)&v54 + 1) = L"NtfsMaxWaitTimeForDeallocatedClustersInTrim";
        LODWORD(v54) = 5767254;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack < 0 )
          v116 = 60000;
        else
          v116 = *(unsigned int *)((char *)v51 + v51[2]);
        *((_QWORD *)&v54 + 1) = L"NtfsFlushTrimRequestsOnDismount";
        LODWORD(v54) = 4194366;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        NtfsFlushTrimRequestsOnDismount = ValueKeyWithFallBack >= 0 && *(unsigned int *)((char *)v51 + v51[2]) == 1;
        *((_QWORD *)&v54 + 1) = L"NtfsAllowMaximumSupportedHardLinks";
        LODWORD(v54) = 4587588;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        NtfsAllowMaximumSupportedHardLinks = ValueKeyWithFallBack >= 0 && *(unsigned int *)((char *)v51 + v51[2]) == 1;
        *((_QWORD *)&v54 + 1) = L"NtfsDisableTrueAsyncCachedReads";
        LODWORD(v54) = 4194366;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v117 = *(unsigned int *)((char *)v51 + v51[2]);
          v63 = 1;
        }
        *((_QWORD *)&v54 + 1) = L"NtfsFileMetadataOptimizationThreshold";
        LODWORD(v54) = 4980810;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v15 = *(unsigned int *)((char *)v51 + v51[2]);
          v99 = v15;
          if ( v15 >= 0xA )
          {
            if ( v15 > 0x5A )
              v15 = 90;
            v99 = v15;
          }
          else
          {
            v99 = 10;
          }
        }
        *((_QWORD *)&v54 + 1) = L"NtfsMaxFileMetadataOptimizationThread";
        LODWORD(v54) = 4980810;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v16 = *(unsigned int *)((char *)v51 + v51[2]);
          v101 = v16;
          if ( v16 )
          {
            if ( v16 > 0x3E8 )
              v16 = 1000;
            v101 = v16;
          }
          else
          {
            v101 = 1;
          }
        }
        *((_QWORD *)&v54 + 1) = L"NtfsEnableDirectAccess";
        LODWORD(v54) = 3014700;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v118 = *(unsigned int *)((char *)v51 + v51[2]);
          v64 = 1;
        }
        *((_QWORD *)&v54 + 1) = L"NtfsEnableDirCaseSensitivity";
        LODWORD(v54) = 3801144;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack >= 0 )
          v119 = *(unsigned int *)((char *)v51 + v51[2]);
        *((_QWORD *)&v54 + 1) = L"NtfsAllowQueryFreeSpaceConsiderPool";
        LODWORD(v54) = 4718662;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack >= 0 )
          v120 = *(unsigned int *)((char *)v51 + v51[2]);
        *((_QWORD *)&v54 + 1) = L"AllowHardLinkWithNoAccess";
        LODWORD(v54) = 3407922;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack < 0
          && (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v69,
                                       (unsigned int)&v54,
                                       (unsigned int)&v52,
                                       (__int64)&v51,
                                       (__int64)v50),
              ValueKeyWithFallBack < 0) )
        {
          v108 = 0;
        }
        else
        {
          v108 = *(unsigned int *)((char *)v51 + v51[2]);
        }
        *((_QWORD *)&v54 + 1) = L"NtfsParallelFlushThreshold";
        LODWORD(v54) = 3538996;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v69,
                                       (unsigned int)&v54,
                                       (unsigned int)&v52,
                                       (__int64)&v51,
                                       (__int64)v50),
              ValueKeyWithFallBack >= 0) )
        {
          v17 = *(unsigned int *)((char *)v51 + v51[2]);
          v80 = v17;
        }
        else
        {
          v17 = v81;
        }
        if ( !v17 )
        {
          v17 = 1000;
LABEL_124:
          v80 = v17;
          v81 = v17;
          goto LABEL_125;
        }
        if ( v17 >= 0x64 )
        {
          if ( v17 > 0xF4240 )
            v17 = 1000000;
          goto LABEL_124;
        }
        v81 = 100;
        v80 = 100;
LABEL_125:
        *((_QWORD *)&v54 + 1) = L"NtfsParallelFlushWorkers";
        LODWORD(v54) = 3276848;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v69,
                                       (unsigned int)&v54,
                                       (unsigned int)&v52,
                                       (__int64)&v51,
                                       (__int64)v50),
              ValueKeyWithFallBack >= 0) )
        {
          v18 = *(unsigned int *)((char *)v51 + v51[2]);
          v71 = v18;
        }
        else
        {
          v18 = v72;
        }
        if ( v18 )
        {
          if ( v18 > 2 * NtfsNumberProcessors )
            v18 = 2 * NtfsNumberProcessors;
        }
        else
        {
          v71 = ((unsigned int)NtfsNumberProcessors >> 1) + 1;
          v18 = 16;
          if ( v71 < 0x10 )
            v18 = ((unsigned int)NtfsNumberProcessors >> 1) + 1;
        }
        v71 = v18;
        v72 = v18;
        *((_QWORD *)&v54 + 1) = L"NtfsMinLengthForAZeroWorker";
        LODWORD(v54) = 3670070;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v69,
                                       (unsigned int)&v54,
                                       (unsigned int)&v52,
                                       (__int64)&v51,
                                       (__int64)v50),
              ValueKeyWithFallBack >= 0) )
        {
          v19 = *(unsigned int *)((char *)v51 + v51[2]);
          v86 = v19;
        }
        else
        {
          v19 = v87;
        }
        if ( v19 )
        {
          if ( v19 < 0x400000 )
            v19 = 0x400000;
          v87 = v19;
          v86 = v19;
        }
        else
        {
          v87 = 0x8000000;
          v86 = 0x8000000;
        }
        *((_QWORD *)&v54 + 1) = L"NtfsParallelZeroWorkers";
        LODWORD(v54) = 3145774;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v69,
                                       (unsigned int)&v54,
                                       (unsigned int)&v52,
                                       (__int64)&v51,
                                       (__int64)v50),
              ValueKeyWithFallBack >= 0) )
        {
          v20 = *(unsigned int *)((char *)v51 + v51[2]);
          v82 = v20;
        }
        else
        {
          v20 = v83;
        }
        if ( v20 )
        {
          if ( v20 > 0x10 )
            v20 = 16;
          v83 = v20;
          v82 = v20;
        }
        else
        {
          v83 = 1;
          v82 = 1;
        }
        *((_QWORD *)&v54 + 1) = L"NtfsLockSystemFilePages";
        LODWORD(v54) = 3145774;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v69,
                                       (unsigned int)&v54,
                                       (unsigned int)&v52,
                                       (__int64)&v51,
                                       (__int64)v50),
              ValueKeyWithFallBack >= 0) )
        {
          v21 = *(unsigned int *)((char *)v51 + v51[2]);
          v93 = v21;
        }
        else
        {
          v21 = v94;
        }
        if ( v21 > 3 )
          v21 = 1;
        v94 = v21;
        v93 = v21;
        *((_QWORD *)&v54 + 1) = L"NtfsDisableIoPerf";
        LODWORD(v54) = 2359330;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack < 0 )
        {
          ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                   (unsigned int)&DestinationString,
                                   (unsigned int)&v69,
                                   (unsigned int)&v54,
                                   (unsigned int)&v52,
                                   (__int64)&v51,
                                   (__int64)v50);
          if ( ValueKeyWithFallBack < 0 )
            goto LABEL_164;
          v109 = *(unsigned int *)((char *)v51 + v51[2]);
        }
        else
        {
          v109 = *(unsigned int *)((char *)v51 + v51[2]);
        }
        v58 = 1;
LABEL_164:
        *((_QWORD *)&v54 + 1) = L"NtfsMaxAcceptableLatency";
        LODWORD(v54) = 3276848;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack < 0 )
        {
          ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                   (unsigned int)&DestinationString,
                                   (unsigned int)&v69,
                                   (unsigned int)&v54,
                                   (unsigned int)&v52,
                                   (__int64)&v51,
                                   (__int64)v50);
          if ( ValueKeyWithFallBack < 0 )
          {
            v22 = v102;
          }
          else
          {
            v22 = *(unsigned int *)((char *)v51 + v51[2]);
            v102 = v22;
            v8 = 1;
            v55 = 1;
          }
          if ( !v8 )
            goto LABEL_173;
        }
        else
        {
          v22 = *(unsigned int *)((char *)v51 + v51[2]);
          v102 = v22;
          v55 = 1;
        }
        if ( v22 == dword_14009465C || (unsigned int)(v22 - 1) > 0x1D4BF )
          v55 = 0;
LABEL_173:
        *((_QWORD *)&v54 + 1) = L"NtfsKsrVersion";
        LODWORD(v54) = 1966108;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v69,
                                       (unsigned int)&v54,
                                       (unsigned int)&v52,
                                       (__int64)&v51,
                                       (__int64)v50),
              ValueKeyWithFallBack >= 0) )
        {
          v23 = *(unsigned int *)((char *)v51 + v51[2]);
          v96 = v23;
        }
        else
        {
          v23 = v97;
        }
        if ( v23 > 2 )
          v23 = 0;
        v97 = v23;
        v96 = v23;
        *((_QWORD *)&v54 + 1) = L"NtfsMaxDelayCloseCount";
        LODWORD(v54) = 3014700;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v2 = *(unsigned int *)((char *)v51 + v51[2]);
          v98 = v2;
        }
        if ( v2 >= 0x10 )
        {
          if ( v2 > 0x4000 )
            v2 = 0x4000;
          v73 = v2;
          v98 = v2;
        }
        else
        {
          v73 = 16;
          v98 = 16;
        }
        *((_QWORD *)&v54 + 1) = L"NtfsCachedRunsBinMaxLengthInBytes";
        LODWORD(v54) = 4456514;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v69,
                                       (unsigned int)&v54,
                                       (unsigned int)&v52,
                                       (__int64)&v51,
                                       (__int64)v50),
              ValueKeyWithFallBack >= 0) )
        {
          v24 = *(_QWORD *)((char *)v51 + v51[2]);
          v123 = v24;
        }
        else
        {
          v24 = v124;
        }
        if ( v24 )
        {
          if ( v24 < 0x4000000 )
            v24 = 0x4000000;
          v124 = v24;
          v123 = v24;
        }
        else
        {
          v124 = 0x40000000;
          v123 = 0x40000000;
        }
        *((_QWORD *)&v54 + 1) = L"NtfsDefaultTier";
        LODWORD(v54) = 2097182;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack < 0 )
        {
          ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                   (unsigned int)&DestinationString,
                                   (unsigned int)&v69,
                                   (unsigned int)&v54,
                                   (unsigned int)&v52,
                                   (__int64)&v51,
                                   (__int64)v50);
          if ( ValueKeyWithFallBack >= 0 )
            v110 = *(unsigned int *)((char *)v51 + v51[2]);
        }
        else
        {
          v110 = *(unsigned int *)((char *)v51 + v51[2]);
        }
        *((_QWORD *)&v54 + 1) = L"NtfsMaxCachedRuns";
        LODWORD(v54) = 2359330;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack < 0 )
        {
          v25 = v78;
        }
        else
        {
          v25 = *(unsigned int *)((char *)v51 + v51[2]);
          v78 = v25;
          if ( v25 )
          {
            if ( v25 >= 0x2328 )
            {
              if ( v25 > 0xFFFE )
                v25 = 65534;
            }
            else
            {
              v25 = 9000;
            }
          }
          else
          {
            v25 = 65534;
          }
          v78 = v25;
        }
        *((_QWORD *)&v54 + 1) = L"NtfsInitialCachedRuns";
        LODWORD(v54) = 2883626;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v26 = *(unsigned int *)((char *)v51 + v51[2]);
          v74 = v26;
          if ( !v26 )
          {
            v26 = 512;
            if ( byte_1400951DA == 1 )
              v26 = 32;
LABEL_213:
            v75 = v26;
            v74 = v26;
            goto LABEL_214;
          }
          if ( v26 >= 0x20 )
          {
            if ( v26 > v25 )
              v26 = v25;
            goto LABEL_213;
          }
          v75 = 32;
          v74 = 32;
        }
LABEL_214:
        *((_QWORD *)&v54 + 1) = L"NtfsCachedRunsDelta";
        LODWORD(v54) = 2621478;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack < 0 )
          goto LABEL_229;
        v27 = *(unsigned int *)((char *)v51 + v51[2]);
        v76 = v27;
        if ( v27 )
        {
          if ( v27 < 0x200 )
          {
            v77 = 512;
            v76 = 512;
            goto LABEL_229;
          }
          if ( v27 > v25 )
            v27 = v25;
        }
        else
        {
          v27 = 0x2000;
          if ( byte_1400951DA == 1 )
            v27 = 512;
        }
        v76 = v27;
        v77 = v27;
LABEL_229:
        *((_QWORD *)&v54 + 1) = L"NtfsCachedRunsLimitMode";
        LODWORD(v54) = 3145774;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v28 = *(unsigned int *)((char *)v51 + v51[2]);
          v111 = v28;
          if ( (unsigned int)(v28 - 1) > 3 )
            v28 = 4;
          v111 = v28;
        }
        *((_QWORD *)&v54 + 1) = L"NtfsCachedRunsInsertLimit";
        LODWORD(v54) = 3407922;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v69,
                                 (unsigned int)&v54,
                                 (unsigned int)&v52,
                                 (__int64)&v51,
                                 (__int64)v50);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v29 = *(unsigned int *)((char *)v51 + v51[2]);
          v85 = v29;
          if ( v29 )
          {
            if ( v29 >= 0x400 )
            {
              if ( v29 > v25 )
                v29 = v25;
              v85 = v29;
            }
            else
            {
              v85 = 1024;
            }
          }
          else
          {
            v85 = 0x4000;
          }
        }
        v30 = 1;
        *((_QWORD *)&v54 + 1) = L"NtfsLimitPhysicalSectorSize";
        LODWORD(v54) = 3670070;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v69,
                                       (unsigned int)&v54,
                                       (unsigned int)&v52,
                                       (__int64)&v51,
                                       (__int64)v50),
              ValueKeyWithFallBack >= 0) )
        {
          v30 = *(unsigned int *)((char *)v51 + v51[2]);
        }
        v31 = Feature_NTFS_DirectoryChangeNotifyListDirectoryAccessCheck__private_IsEnabledDeviceUsageNoInline() != 0;
        *((_QWORD *)&v54 + 1) = L"EnforceDirectoryChangeNotificationPermissionCheck";
        LODWORD(v54) = 6553698;
        v6 = NtfsQueryValueKey(&v88, &v54, &v52, &v51, v50);
        ValueKeyWithFallBack = v6;
        if ( v6 < 0 )
        {
          v6 = NtfsQueryValueKeyWithFallBack(
                 (unsigned int)&DestinationString,
                 (unsigned int)&v69,
                 (unsigned int)&v54,
                 (unsigned int)&v52,
                 (__int64)&v51,
                 (__int64)v50);
          ValueKeyWithFallBack = v6;
          v1 = v51;
          if ( v6 < 0 )
            goto LABEL_248;
        }
        else
        {
          v1 = v51;
        }
        v31 = *(unsigned int *)((char *)v1 + v1[2]);
LABEL_248:
        ExAcquireResourceExclusiveLite(&Resource, 1u);
        v61 = 1;
        v32 = dword_1400956B8;
        if ( v106 == 1 )
        {
          if ( (dword_1400956B8 & 0x80000) != 0 )
            goto LABEL_254;
          v32 = dword_1400956B8 | 0x80000;
        }
        else
        {
          if ( (dword_1400956B8 & 0x80000) == 0 )
            goto LABEL_254;
          v32 = dword_1400956B8 & 0xFFF7FFFF;
        }
        dword_1400956B8 = v32;
        v59 = 1;
LABEL_254:
        if ( v112 == 1 )
          v33 = v32 | 0x20000;
        else
          v33 = v32 & 0xFFFDFFFF;
        dword_1400956B8 = v33;
        if ( dword_1400953B4 != v125 )
        {
          dword_1400953B4 = v125;
          v65 = 1;
        }
        dword_140095AC4 = v95;
        qword_140095AC8 = (unsigned __int64)v113 << 30;
        if ( v114 )
          v34 = v33 | 0x10;
        else
          v34 = v33 & 0xFFFFFFEF;
        dword_1400956B8 = v34;
        if ( (v107 & 1) != 0 )
          v35 = v34 | 4;
        else
          v35 = v34 & 0xFFFFFFFB;
        dword_1400956B8 = v35;
        if ( (v107 & 2) != 0 )
          v36 = v35 | 8;
        else
          v36 = v35 & 0xFFFFFFF7;
        dword_1400956B8 = v36;
        if ( v104 == 1 )
          v37 = v36 | 0x100;
        else
          v37 = v36 & 0xFFFFFEFF;
        dword_1400956B8 = v37;
        if ( v90 == 1 )
          v38 = v37 | 0x200;
        else
          v38 = v37 & 0xFFFFFDFF;
        dword_1400956B8 = v38;
        if ( v79 <= 0xF )
        {
          v39 = v79;
        }
        else
        {
          v39 = (v38 >> 14) & 1;
          v79 = v39;
          v91 = v39;
        }
        if ( dword_1400953B8 != v39 )
        {
          dword_1400953B8 = v39;
          v66 = 1;
        }
        v40 = v121;
        if ( dword_1400953BC != v121 )
        {
          dword_1400953BC = v121;
          v67 = 1;
        }
        if ( v62 )
        {
          if ( a1 )
          {
            v40 = v84;
            if ( dword_140095AB0 != v84 )
            {
              dword_140095AB0 = v84;
              dword_140095AC0 = v84 < 0x2EE ? 1000 : 2000;
            }
          }
        }
        if ( NtfsMaxTrimTotalSize < v13 )
        {
          v13 = NtfsMaxTrimTotalSize;
          v56 = 1;
        }
        v41 = NtfsMinTrimTotalSize;
        if ( NtfsMinTrimTotalSize != v13 )
        {
          if ( (!v100 || (*((_DWORD *)v100 + 4) & 0x100000) == 0)
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
          {
            McTemplateU0q_EtwWriteTransfer(v40, ntfsinit_c6389, v13);
          }
          v41 = v13;
          NtfsMinTrimTotalSize = v13;
          v56 = 1;
        }
        v42 = v115;
        if ( v115 < v41 )
          v42 = v41;
        if ( NtfsMaxTrimTotalSize == v42 )
        {
          v43 = v56;
        }
        else
        {
          if ( (!v100 || (*((_DWORD *)v100 + 4) & 0x100000) == 0)
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
          {
            McTemplateU0q_EtwWriteTransfer(v40, ntfsinit_c6410, v42);
          }
          NtfsMaxTrimTotalSize = v42;
          v43 = 1;
          v56 = 1;
        }
        if ( v57 )
          NtfsTrimListLengthThreshold = v122;
        NtfsMaxWaitTimeForDeallocatedClustersInTrim = 10000 * (unsigned __int64)v116 / (unsigned int)dword_1400953B0;
        if ( v63 )
        {
          if ( v117 )
          {
            if ( v117 == 1 )
              LOBYTE(word_140095AD0) = 1;
          }
          else
          {
            LOBYTE(word_140095AD0) = 0;
          }
        }
        if ( v99 != dword_140095AB4 )
          dword_140095AB4 = v99;
        if ( v101 != dword_1400958A4 )
          dword_1400958A4 = v101;
        if ( v126 != dword_140095AB8 )
          dword_140095AB8 = 100000;
        if ( v127 != dword_140095ABC )
          dword_140095ABC = 25;
        if ( v64 )
          HIBYTE(word_140095AD0) = v118 != 0;
        dword_140095AD4 = v119;
        if ( v120 )
        {
          if ( dword_1400956B8 < 0 )
            goto LABEL_325;
          v44 = dword_1400956B8 | 0x80000000;
        }
        else
        {
          if ( dword_1400956B8 >= 0 )
            goto LABEL_325;
          v44 = dword_1400956B8 & 0x7FFFFFFF;
        }
        dword_1400956B8 = v44;
LABEL_325:
        byte_140095AD2 = v108 == 1;
        dword_140095AD8 = v81;
        dword_140095ADC = v72;
        dword_140095C60 = v87;
        dword_140095C64 = v83;
        if ( dword_140095C14 != v94 )
        {
          dword_140095C14 = v94;
          v68 = 1;
        }
        if ( v58 )
          IoPerfRegistryConfig = v109 != 0;
        if ( v55 )
          dword_14009465C = v102;
        dword_140095BEC = v97;
        v45 = NtfsMaxDelayCloseCount;
        if ( !NtfsMaxDelayCloseCount )
        {
          v45 = 0x4000;
          NtfsMaxDelayCloseCount = 0x4000;
        }
        if ( v73 < v45 )
        {
          NtfsMinDelayCloseCount = 4 * v73 / 5;
          NtfsMaxDelayCloseCount = v73;
        }
        else
        {
          NtfsMaxDelayCloseCount = v73;
          NtfsMinDelayCloseCount = 4 * v73 / 5;
        }
        v46 = (unsigned __int8)FsRtlIsMobileOS() == 0;
        v47 = NtfsMinDelayCloseCount;
        if ( v46 )
          v47 = 2 * NtfsMinDelayCloseCount;
        NtfsThrottleCreates = v47;
        if ( qword_140095C58 != v124 )
        {
          qword_140095C58 = v124;
          v60 = 1;
        }
        v48 = v110;
        if ( (unsigned int)(v110 - 1) > 1 )
          v48 = (byte_1400951DA == 1) + 1;
        dword_140095C6C = v48;
        if ( word_140095C70 != (_WORD)v78 )
        {
          word_140095C70 = v78;
          v60 = 1;
        }
        word_140095C72 = v75;
        word_140095C74 = v77;
        dword_140095C78 = v111;
        word_140095C7C = v85;
        byte_140095C56 = v30 != 0;
        byte_140095C7E = v31 != 0;
        ExReleaseResourceLite(&Resource);
        v61 = 0;
        if ( a1 )
        {
          v49 = (int)v100;
          if ( v59 )
            NtfsForEachVcb((_DWORD)v100, 0, 0, (unsigned int)NtfsUpdateDeleteNotificationVolumeSetting, 0, 0);
          if ( v43 )
            NtfsForEachVcb(v49, 0, 0, (unsigned int)NtfsUpdateTrimLimitsVolumeSetting, 0, 0);
          if ( v65 )
            NtfsForEachVcb(v49, 0, 0, (unsigned int)NtfsUpdateShortNameCreationVolumeSetting, 0, 0);
          if ( v66 || v67 )
            NtfsForEachVcb(v49, 0, 0, (unsigned int)NtfsUpdateCorruptionHandlingVolumeSetting, 0, 0);
          if ( v68 )
            NtfsForEachVcb(v49, 0, 0, (unsigned int)NtfsUpdateLockSystemFilePagesVolumeSetting, 0, 1);
          if ( v60 )
            NtfsForEachVcb(v49, 0, 0, (unsigned int)NtfsUpdateVcbStateToReloadClusters, 0, 0);
          if ( v55 )
            IoPerfRegistryUpdateConfig();
        }
        v5 = (__int64)v100;
        NtfsExtendedCompleteRequestInternal(v100, 0, 0, 0, 1);
        v2 = v73;
        v7 = v121;
        if ( v6 != -1073741608 && v6 != -1073741432 )
          break;
        v8 = v55;
      }
    }
    if ( v50[0] )
      ExFreePoolWithTag(v1, 0);
    ExReleaseResourceLite(&NtfsDynamicRegistrySettingsResource);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x1400e0080  mov     r11, rsp
0x1400e0083  mov     [r11+10h], rbx
0x1400e0087  mov     [r11+18h], rsi
0x1400e008b  mov     [r11+8], rcx
0x1400e008f  push    rdi
0x1400e0090  push    r12
0x1400e0092  push    r13
0x1400e0094  push    r14
0x1400e0096  push    r15
0x1400e0098  sub     rsp, 4A0h
0x1400e009f  mov     rax, cs:__security_cookie
0x1400e00a6  xor     rax, rsp
0x1400e00a9  mov     [rsp+4C8h+var_38], rax
0x1400e00b1  mov     r14d, 228h
0x1400e00b7  mov     r8d, r14d; Size
0x1400e00ba  xor     edx, edx; Val
0x1400e00bc  lea     rcx, [r11-308h]; void *
0x1400e00c3  call    memset
0x1400e00c8  lea     rax, [rsp+4C8h+var_308]
0x1400e00d0  mov     [rsp+4C8h+var_3B8], rax
0x1400e00d8  xorps   xmm0, xmm0
0x1400e00db  xor     eax, eax
0x1400e00dd  movups  [rsp+4C8h+var_338], xmm0
0x1400e00e5  movups  [rsp+4C8h+var_328], xmm0
0x1400e00ed  mov     [rsp+4C8h+var_318], rax
0x1400e00f5  movups  [rsp+4C8h+var_3F8], xmm0
0x1400e00fd  xorps   xmm1, xmm1
0x1400e0100  movups  xmmword ptr [rsp+4C8h+DestinationString.Length], xmm1
0x1400e0105  movups  [rsp+4C8h+var_460], xmm0
0x1400e010a  movups  [rsp+4C8h+var_480], xmm1
0x1400e010f  mov     [rsp+4C8h+var_488], 9Ch
0x1400e0117  lea     rsi, [rsp+4C8h+P]
0x1400e011f  mov     [rsp+4C8h+var_490], rsi
0x1400e0124  xor     ebx, ebx
0x1400e0126  mov     [rsp+4C8h+var_498], bl
0x1400e012a  mov     ecx, 0FFFEh
0x1400e012f  mov     [rsp+4C8h+var_424], ecx
0x1400e0136  lea     r15d, [rax+20h]
0x1400e013a  mov     [rsp+4C8h+var_430], r15d
0x1400e0142  mov     [rsp+4C8h+var_434], r15d
0x1400e014a  lea     r13d, [r14-28h]
0x1400e014e  mov     [rsp+4C8h+var_428], r13d
0x1400e0156  mov     [rsp+4C8h+var_42C], r13d
0x1400e015e  mov     r15d, 4000h
0x1400e0164  mov     [rsp+4C8h+var_408], r15d
0x1400e016c  lea     r12d, [rax+1]
0x1400e0170  cmp     cs:byte_1400951DA, r12b
0x1400e0177  jz      short loc_1400E01A5
0x1400e0179  mov     [rsp+4C8h+var_430], r13d
0x1400e0181  mov     [rsp+4C8h+var_434], r13d
0x1400e0189  mov     r15d, 2000h
0x1400e018f  mov     [rsp+4C8h+var_428], r15d
0x1400e0197  mov     [rsp+4C8h+var_42C], r15d
0x1400e019f  mov     r15d, 4000h
0x1400e01a5  xor     r8d, r8d
0x1400e01a8  xor     edx, edx
0x1400e01aa  lea     rcx, [rsp+4C8h+var_338]
0x1400e01b2  call    NtfsInitializeTopLevelIrp
0x1400e01b7  mov     rdi, rax
0x1400e01ba  mov     r8, r14; Size
0x1400e01bd  xor     edx, edx; Val
0x1400e01bf  lea     rcx, [rsp+4C8h+var_308]; void *
0x1400e01c7  call    memset
0x1400e01cc  lea     r9, [rsp+4C8h+var_3B8]
0x1400e01d4  xor     r8d, r8d
0x1400e01d7  mov     dl, r12b
0x1400e01da  xor     ecx, ecx; Irp
0x1400e01dc  call    NtfsInitializeIrpContextInternal
0x1400e01e1  test    eax, eax
0x1400e01e3  js      loc_1400E2445
0x1400e01e9  mov     rdx, rdi
0x1400e01ec  mov     rdi, [rsp+4C8h+var_3B8]
0x1400e01f4  mov     rcx, rdi
0x1400e01f7  call    NtfsUpdateIrpContextWithTopLevel
0x1400e01fc  call    cs:__imp_KeEnterCriticalRegion
0x1400e0203  nop     dword ptr [rax+rax+00h]
0x1400e0208  mov     dl, r12b; Wait
0x1400e020b  lea     rcx, NtfsDynamicRegistrySettingsResource; Resource
0x1400e0212  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400e0219  nop     dword ptr [rax+rax+00h]
0x1400e021e  movups  xmm0, xmmword ptr cs:aFh; "fh"
0x1400e0225  movdqu  [rsp+4C8h+var_3F8], xmm0
0x1400e022e  call    NtfsInitializeCompatibilityModeKeyPath
0x1400e0233  mov     r14d, eax
0x1400e0236  test    eax, eax
0x1400e0238  js      loc_1400E240F
0x1400e023e  mov     [rsp+4C8h+var_46A], bl
0x1400e0242  mov     [rsp+4C8h+var_39C], ebx
0x1400e0249  mov     [rsp+4C8h+var_46C], bl
0x1400e024d  mov     [rsp+4C8h+var_384], ebx
0x1400e0254  mov     [rsp+4C8h+var_466], bl
0x1400e0258  mov     [rsp+4C8h+var_398], ebx
0x1400e025f  mov     eax, r12d
0x1400e0262  mov     [rsp+4C8h+var_3A4], eax
0x1400e0269  mov     [rsp+4C8h+var_3A8], eax
0x1400e0270  mov     [rsp+4C8h+var_3E4], ebx
0x1400e0277  mov     [rsp+4C8h+var_3E8], ebx
0x1400e027e  mov     eax, 10h
0x1400e0283  mov     [rsp+4C8h+var_420], eax
0x1400e028a  mov     [rsp+4C8h+var_3E0], eax
0x1400e0291  mov     [rsp+4C8h+var_465], bl
0x1400e0295  mov     r13d, r12d
0x1400e0298  mov     [rsp+4C8h+var_3DC], r12d
0x1400e02a0  mov     [rsp+4C8h+var_464], bl
0x1400e02a4  mov     ecx, r12d
0x1400e02a7  mov     [rsp+4C8h+var_3D4], ecx
0x1400e02ae  mov     [rsp+4C8h+var_3D8], ecx
0x1400e02b5  mov     [rsp+4C8h+var_463], bl
0x1400e02b9  mov     [rsp+4C8h+var_40C], ebx
0x1400e02c0  mov     [rsp+4C8h+var_469], bl
0x1400e02c4  mov     [rsp+4C8h+var_370], ebx
0x1400e02cb  mov     [rsp+4C8h+var_468], bl
0x1400e02cf  mov     [rsp+4C8h+var_3C0], 46h ; 'F'
0x1400e02da  mov     [rsp+4C8h+var_3B0], 8
0x1400e02e5  mov     [rsp+4C8h+var_344], 186A0h
0x1400e02f0  mov     [rsp+4C8h+var_340], 19h
0x1400e02fb  mov     [rsp+4C8h+var_46F], bl
0x1400e02ff  mov     [rsp+4C8h+var_46E], bl
0x1400e0303  mov     [rsp+4C8h+var_36C], ebx
0x1400e030a  mov     [rsp+4C8h+var_467], bl
0x1400e030e  mov     eax, 80000003h
0x1400e0313  mov     [rsp+4C8h+var_3D0], eax
0x1400e031a  mov     [rsp+4C8h+var_3A0], eax
0x1400e0321  mov     [rsp+4C8h+var_380], ebx
0x1400e0328  mov     [rsp+4C8h+var_368], 3
0x1400e0333  mov     [rsp+4C8h+var_364], ebx
0x1400e033a  mov     [rsp+4C8h+var_418], ebx
0x1400e0341  mov     [rsp+4C8h+var_41C], ebx
0x1400e0348  mov     [rsp+4C8h+var_43C], ebx
0x1400e034f  mov     [rsp+4C8h+var_440], ebx
0x1400e0356  mov     [rsp+4C8h+var_400], ebx
0x1400e035d  mov     [rsp+4C8h+var_404], ebx
0x1400e0364  mov     [rsp+4C8h+var_410], ebx
0x1400e036b  mov     [rsp+4C8h+var_414], ebx
0x1400e0372  mov     [rsp+4C8h+var_390], ebx
0x1400e0379  mov     [rsp+4C8h+var_46D], bl
0x1400e037d  mov     eax, 7530h
0x1400e0382  mov     [rsp+4C8h+var_3AC], eax
0x1400e0389  mov     sil, bl
0x1400e038c  mov     [rsp+4C8h+var_470], bl
0x1400e0390  mov     eax, 2
0x1400e0395  mov     [rsp+4C8h+var_3C8], eax
0x1400e039c  mov     [rsp+4C8h+var_3CC], eax
0x1400e03a3  mov     [rsp+4C8h+var_438], r15d
0x1400e03ab  mov     [rsp+4C8h+var_3C4], r15d
0x1400e03b3  mov     [rsp+4C8h+var_38C], ebx
0x1400e03ba  mov     ecx, 40000000h
0x1400e03bf  mov     [rsp+4C8h+var_350], rcx
0x1400e03c7  mov     [rsp+4C8h+var_358], rcx
0x1400e03cf  mov     [rsp+4C8h+var_388], 4
0x1400e03da  mov     [rsp+4C8h+var_46B], bl
0x1400e03de  lea     rdx, NtfsCompatibilityModeKeyPath; SourceString
0x1400e03e5  lea     rcx, [rsp+4C8h+DestinationString]; DestinationString
0x1400e03ea  call    cs:__imp_RtlInitUnicodeString
0x1400e03f1  nop     dword ptr [rax+rax+00h]
0x1400e03f6  movups  xmm0, xmmword ptr cs:aZ; "z|"
0x1400e03fd  movdqu  [rsp+4C8h+var_460], xmm0
0x1400e0403  jmp     short loc_1400E040A
0x1400e0405  mov     sil, [rsp+4C8h+var_470]
0x1400e040a  cmp     r14d, 0C0000188h
0x1400e0411  jnz     short loc_1400E041B
0x1400e0413  mov     rcx, rdi
0x1400e0416  call    NtfsCheckpointForLogFileFull
0x1400e041b  test    rdi, rdi
0x1400e041e  jz      short loc_1400E042B
0x1400e0420  mov     edx, r14d
0x1400e0423  mov     rcx, rdi
0x1400e0426  call    NtfsPreRequestProcessingExtend
0x1400e042b  lea     rax, aDisabledeleten_0; "DisableDeleteNotification"
0x1400e0432  mov     qword ptr [rsp+4C8h+var_480+8], rax
0x1400e0437  mov     dword ptr [rsp+4C8h+var_480], 340032h
0x1400e043f  lea     rax, [rsp+4C8h+var_498]
0x1400e0444  mov     [rsp+4C8h+var_4A8], rax
0x1400e0449  lea     r9, [rsp+4C8h+var_490]
0x1400e044e  lea     r8, [rsp+4C8h+var_488]
0x1400e0453  lea     rdx, [rsp+4C8h+var_480]
0x1400e0458  lea     rcx, [rsp+4C8h+var_3F8]
0x1400e0460  call    NtfsQueryValueKey
0x1400e0465  mov     [rsp+4C8h+var_484], eax
0x1400e0469  test    eax, eax
0x1400e046b  js      short loc_1400E0481
0x1400e046d  mov     rcx, [rsp+4C8h+var_490]
0x1400e0472  mov     eax, [rcx+8]
0x1400e0475  mov     edi, [rax+rcx]
0x1400e0478  mov     [rsp+4C8h+var_39C], edi
0x1400e047f  jmp     short loc_1400E04C8
0x1400e0481  lea     rax, [rsp+4C8h+var_498]
0x1400e0486  mov     [rsp+4C8h+var_4A0], rax
0x1400e048b  lea     rax, [rsp+4C8h+var_490]
0x1400e0490  mov     [rsp+4C8h+var_4A8], rax
0x1400e0495  lea     r9, [rsp+4C8h+var_488]
0x1400e049a  lea     r8, [rsp+4C8h+var_480]
0x1400e049f  lea     rdx, [rsp+4C8h+var_460]
0x1400e04a4  lea     rcx, [rsp+4C8h+DestinationString]
0x1400e04a9  call    NtfsQueryValueKeyWithFallBack
0x1400e04ae  mov     [rsp+4C8h+var_484], eax
0x1400e04b2  test    eax, eax
0x1400e04b4  js      short loc_1400E04C8
0x1400e04b6  mov     rcx, [rsp+4C8h+var_490]
0x1400e04bb  mov     eax, [rcx+8]
0x1400e04be  mov     eax, [rax+rcx]
0x1400e04c1  mov     [rsp+4C8h+var_39C], eax
0x1400e04c8  lea     rax, aDisabledeleten; "DisableDeleteNotificationDrain"
0x1400e04cf  mov     qword ptr [rsp+4C8h+var_480+8], rax
0x1400e04d4  mov     dword ptr [rsp+4C8h+var_480], 3E003Ch
0x1400e04dc  lea     rax, [rsp+4C8h+var_498]
0x1400e04e1  mov     [rsp+4C8h+var_4A0], rax
0x1400e04e6  lea     rax, [rsp+4C8h+var_490]
0x1400e04eb  mov     [rsp+4C8h+var_4A8], rax
0x1400e04f0  lea     r9, [rsp+4C8h+var_488]
0x1400e04f5  lea     r8, [rsp+4C8h+var_480]
0x1400e04fa  lea     rdx, [rsp+4C8h+var_460]
0x1400e04ff  lea     rcx, [rsp+4C8h+DestinationString]
0x1400e0504  call    NtfsQueryValueKeyWithFallBack
0x1400e0509  mov     [rsp+4C8h+var_484], eax
0x1400e050d  test    eax, eax
0x1400e050f  js      short loc_1400E0523
0x1400e0511  mov     rcx, [rsp+4C8h+var_490]
0x1400e0516  mov     eax, [rcx+8]
0x1400e0519  mov     eax, [rax+rcx]
0x1400e051c  mov     [rsp+4C8h+var_384], eax
0x1400e0523  lea     rax, aNtfsdisable8do; "NtfsDisable8dot3NameCreation"
0x1400e052a  mov     qword ptr [rsp+4C8h+var_480+8], rax
0x1400e052f  mov     dword ptr [rsp+4C8h+var_480], 3A0038h
0x1400e0537  lea     rax, [rsp+4C8h+var_498]
0x1400e053c  mov     [rsp+4C8h+var_4A8], rax
0x1400e0541  lea     r9, [rsp+4C8h+var_490]
0x1400e0546  lea     r8, [rsp+4C8h+var_488]
0x1400e054b  lea     rdx, [rsp+4C8h+var_480]
0x1400e0550  lea     rcx, [rsp+4C8h+var_3F8]
0x1400e0558  call    NtfsQueryValueKey
0x1400e055d  mov     [rsp+4C8h+var_484], eax
0x1400e0561  test    eax, eax
0x1400e0563  jns     short loc_1400E059A
0x1400e0565  lea     rax, [rsp+4C8h+var_498]
0x1400e056a  mov     [rsp+4C8h+var_4A0], rax
0x1400e056f  lea     rax, [rsp+4C8h+var_490]
0x1400e0574  mov     [rsp+4C8h+var_4A8], rax
0x1400e0579  lea     r9, [rsp+4C8h+var_488]
0x1400e057e  lea     r8, [rsp+4C8h+var_480]
0x1400e0583  lea     rdx, [rsp+4C8h+var_460]
0x1400e0588  lea     rcx, [rsp+4C8h+DestinationString]
0x1400e058d  call    NtfsQueryValueKeyWithFallBack
0x1400e0592  mov     [rsp+4C8h+var_484], eax
0x1400e0596  test    eax, eax
0x1400e0598  js      short loc_1400E05A7
0x1400e059a  mov     rcx, [rsp+4C8h+var_490]
0x1400e059f  mov     eax, [rcx+8]
0x1400e05a2  mov     eax, [rax+rcx]
0x1400e05a5  jmp     short loc_1400E05AC
0x1400e05a7  mov     eax, 2
0x1400e05ac  cmp     eax, 3
0x1400e05af  mov     ecx, 2
0x1400e05b4  cmova   eax, ecx
0x1400e05b7  mov     [rsp+4C8h+var_348], eax
0x1400e05be  lea     rax, aNtfsdisablelas; "NtfsDisableLastAccessUpdate"
0x1400e05c5  mov     qword ptr [rsp+4C8h+var_480+8], rax
0x1400e05ca  mov     dword ptr [rsp+4C8h+var_480], 380036h
0x1400e05d2  lea     rax, [rsp+4C8h+var_498]
0x1400e05d7  mov     [rsp+4C8h+var_4A8], rax
0x1400e05dc  lea     r9, [rsp+4C8h+var_490]
0x1400e05e1  lea     r8, [rsp+4C8h+var_488]
0x1400e05e6  lea     rdx, [rsp+4C8h+var_480]
0x1400e05eb  lea     rcx, [rsp+4C8h+var_3F8]
0x1400e05f3  call    NtfsQueryValueKey
0x1400e05f8  mov     [rsp+4C8h+var_484], eax
0x1400e05fc  test    eax, eax
0x1400e05fe  js      short loc_1400E062E
0x1400e0600  mov     rcx, [rsp+4C8h+var_490]
0x1400e0605  mov     eax, [rcx+8]
0x1400e0608  mov     edi, [rax+rcx]
0x1400e060b  and     edi, r12d
0x1400e060e  mov     [rsp+4C8h+var_3D0], edi
0x1400e0615  mov     [rsp+4C8h+var_3A0], edi
0x1400e061c  mov     eax, cs:dword_140095AC4
0x1400e0622  bts     eax, 1Eh
0x1400e0626  mov     cs:dword_140095AC4, eax
0x1400e062c  jmp     short loc_1400E0681
0x1400e062e  lea     rax, [rsp+4C8h+var_498]
0x1400e0633  mov     [rsp+4C8h+var_4A0], rax
0x1400e0638  lea     rax, [rsp+4C8h+var_490]
0x1400e063d  mov     [rsp+4C8h+var_4A8], rax
0x1400e0642  lea     r9, [rsp+4C8h+var_488]
0x1400e0647  lea     r8, [rsp+4C8h+var_480]
0x1400e064c  lea     rdx, [rsp+4C8h+var_460]
0x1400e0651  lea     rcx, [rsp+4C8h+DestinationString]
0x1400e0656  call    NtfsQueryValueKeyWithFallBack
0x1400e065b  mov     [rsp+4C8h+var_484], eax
0x1400e065f  test    eax, eax
0x1400e0661  js      short loc_1400E0681
0x1400e0663  mov     rcx, [rsp+4C8h+var_490]
0x1400e0668  mov     eax, [rcx+8]
0x1400e066b  mov     eax, [rax+rcx]
0x1400e066e  and     eax, 80000003h
0x1400e0673  mov     [rsp+4C8h+var_3D0], eax
0x1400e067a  mov     [rsp+4C8h+var_3A0], eax
0x1400e0681  lea     rax, aNtfslastaccess; "NtfsLastAccessUpdatePolicyVolumeSizeThr"...
0x1400e0688  mov     qword ptr [rsp+4C8h+var_480+8], rax
0x1400e068d  mov     dword ptr [rsp+4C8h+var_480], 5C005Ah
0x1400e0695  lea     rax, [rsp+4C8h+var_498]
  ... truncated ...
```
