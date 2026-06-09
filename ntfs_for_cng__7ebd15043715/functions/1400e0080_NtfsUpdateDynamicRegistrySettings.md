# NtfsUpdateDynamicRegistrySettings

- ea: `0x1400e0080`
- end: `0x1400e2473`
- name: `NtfsUpdateDynamicRegistrySettings`
- size: `9203`
- prototype: `void __fastcall(__int64)`
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
  ULONG_PTR v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // r14d
  unsigned int v11; // r13d
  char v12; // si
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // r15d
  unsigned int v17; // r13d
  unsigned int v18; // edi
  unsigned int v19; // edi
  unsigned int v20; // edi
  unsigned int v21; // edi
  unsigned int v22; // edi
  unsigned int v23; // edi
  unsigned int v24; // edi
  unsigned int v25; // eax
  int v26; // ecx
  unsigned int v27; // eax
  unsigned __int64 v28; // rdi
  unsigned int v29; // esi
  unsigned int v30; // edi
  unsigned int v31; // edi
  int v32; // ecx
  unsigned int v33; // edi
  int v34; // r15d
  int v35; // edi
  unsigned int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  unsigned int v42; // ecx
  int v43; // ecx
  __int64 v44; // rcx
  unsigned int v45; // eax
  int v46; // r13d
  char v47; // r13
  int v48; // eax
  unsigned int v49; // r8d
  bool v50; // zf
  int v51; // eax
  int v52; // ecx
  int v53; // edi
  _BYTE v54[8]; // [rsp+30h] [rbp-498h] BYREF
  unsigned int *v55; // [rsp+38h] [rbp-490h] BYREF
  int v56; // [rsp+40h] [rbp-488h] BYREF
  int ValueKeyWithFallBack; // [rsp+44h] [rbp-484h]
  __int128 v58; // [rsp+48h] [rbp-480h] BYREF
  char v59; // [rsp+58h] [rbp-470h]
  char v60; // [rsp+59h] [rbp-46Fh]
  char v61; // [rsp+5Ah] [rbp-46Eh]
  char v62; // [rsp+5Bh] [rbp-46Dh]
  char v63; // [rsp+5Ch] [rbp-46Ch]
  char v64; // [rsp+5Dh] [rbp-46Bh]
  char v65; // [rsp+5Eh] [rbp-46Ah]
  char v66; // [rsp+5Fh] [rbp-469h]
  char v67; // [rsp+60h] [rbp-468h]
  char v68; // [rsp+61h] [rbp-467h]
  char v69; // [rsp+62h] [rbp-466h]
  char v70; // [rsp+63h] [rbp-465h]
  char v71; // [rsp+64h] [rbp-464h]
  char v72; // [rsp+65h] [rbp-463h]
  __int128 v73; // [rsp+68h] [rbp-460h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-450h] BYREF
  unsigned int v75; // [rsp+88h] [rbp-440h]
  int v76; // [rsp+8Ch] [rbp-43Ch]
  unsigned int v77; // [rsp+90h] [rbp-438h]
  int v78; // [rsp+94h] [rbp-434h]
  int v79; // [rsp+98h] [rbp-430h]
  int v80; // [rsp+9Ch] [rbp-42Ch]
  int v81; // [rsp+A0h] [rbp-428h]
  int v82; // [rsp+A4h] [rbp-424h]
  unsigned int v83; // [rsp+A8h] [rbp-420h]
  int v84; // [rsp+ACh] [rbp-41Ch]
  int v85; // [rsp+B0h] [rbp-418h]
  int v86; // [rsp+B4h] [rbp-414h]
  int v87; // [rsp+B8h] [rbp-410h]
  unsigned int v88; // [rsp+BCh] [rbp-40Ch]
  int v89; // [rsp+C0h] [rbp-408h]
  int v90; // [rsp+C4h] [rbp-404h]
  int v91; // [rsp+C8h] [rbp-400h]
  __int128 v92; // [rsp+D0h] [rbp-3F8h] BYREF
  unsigned int v93; // [rsp+E0h] [rbp-3E8h]
  unsigned int v94; // [rsp+E4h] [rbp-3E4h]
  int v95; // [rsp+E8h] [rbp-3E0h]
  int v96; // [rsp+ECh] [rbp-3DCh]
  int v97; // [rsp+F0h] [rbp-3D8h]
  int v98; // [rsp+F4h] [rbp-3D4h]
  int v99; // [rsp+F8h] [rbp-3D0h]
  int v100; // [rsp+FCh] [rbp-3CCh]
  int v101; // [rsp+100h] [rbp-3C8h]
  int v102; // [rsp+104h] [rbp-3C4h]
  int v103; // [rsp+108h] [rbp-3C0h]
  _BYTE *v104; // [rsp+110h] [rbp-3B8h] BYREF
  int v105; // [rsp+118h] [rbp-3B0h]
  int v106; // [rsp+11Ch] [rbp-3ACh]
  int v107; // [rsp+120h] [rbp-3A8h]
  int v108; // [rsp+124h] [rbp-3A4h]
  int v109; // [rsp+128h] [rbp-3A0h]
  int v110; // [rsp+12Ch] [rbp-39Ch]
  int v111; // [rsp+130h] [rbp-398h]
  int v112; // [rsp+134h] [rbp-394h]
  int v113; // [rsp+138h] [rbp-390h]
  int v114; // [rsp+13Ch] [rbp-38Ch]
  int v115; // [rsp+140h] [rbp-388h]
  int v116; // [rsp+144h] [rbp-384h]
  unsigned int v117; // [rsp+148h] [rbp-380h]
  int v118; // [rsp+14Ch] [rbp-37Ch]
  unsigned int v119; // [rsp+150h] [rbp-378h]
  unsigned int v120; // [rsp+154h] [rbp-374h]
  int v121; // [rsp+158h] [rbp-370h]
  int v122; // [rsp+15Ch] [rbp-36Ch]
  int v123; // [rsp+160h] [rbp-368h]
  int v124; // [rsp+164h] [rbp-364h]
  unsigned int v125; // [rsp+168h] [rbp-360h]
  int v126; // [rsp+16Ch] [rbp-35Ch]
  __int64 v127; // [rsp+170h] [rbp-358h]
  __int64 v128; // [rsp+178h] [rbp-350h]
  int v129; // [rsp+180h] [rbp-348h]
  int v130; // [rsp+184h] [rbp-344h]
  int v131; // [rsp+188h] [rbp-340h]
  _OWORD v132[2]; // [rsp+190h] [rbp-338h] BYREF
  __int64 v133; // [rsp+1B0h] [rbp-318h]
  _BYTE v134[560]; // [rsp+1C0h] [rbp-308h] BYREF
  _BYTE P[160]; // [rsp+3F0h] [rbp-D8h] BYREF

  memset(v134, 0, 0x228u);
  v104 = v134;
  memset(v132, 0, sizeof(v132));
  v133 = 0;
  v92 = 0;
  DestinationString = 0;
  v73 = 0;
  v58 = 0;
  v56 = 156;
  v1 = (unsigned int *)P;
  v55 = (unsigned int *)P;
  v54[0] = 0;
  v82 = 65534;
  v79 = 32;
  v78 = 32;
  v81 = 512;
  v80 = 512;
  v2 = 0x4000;
  v89 = 0x4000;
  if ( byte_1400951DA != 1 )
  {
    v79 = 512;
    v78 = 512;
    v81 = 0x2000;
    v80 = 0x2000;
    v2 = 0x4000;
  }
  v3 = NtfsInitializeTopLevelIrp((__int64)v132, 0, 0);
  memset(v134, 0, 0x228u);
  if ( (int)NtfsInitializeIrpContextInternal(0, 1, 0, (__int64 *)&v104) >= 0 )
  {
    v4 = v3;
    v5 = (__int64)v104;
    NtfsUpdateIrpContextWithTopLevel((__int64)v104, v4);
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&NtfsDynamicRegistrySettingsResource, 1u);
    v92 = *(_OWORD *)L"fh";
    v10 = NtfsInitializeCompatibilityModeKeyPath(v7, v6, v8, v9);
    if ( v10 >= 0 )
    {
      v65 = 0;
      v110 = 0;
      v63 = 0;
      v116 = 0;
      v69 = 0;
      v111 = 0;
      v108 = 1;
      v107 = 1;
      v94 = 0;
      v93 = 0;
      v83 = 16;
      v95 = 16;
      v70 = 0;
      v11 = 1;
      v96 = 1;
      v71 = 0;
      v98 = 1;
      v97 = 1;
      v72 = 0;
      v88 = 0;
      v66 = 0;
      v121 = 0;
      v67 = 0;
      v103 = 70;
      v105 = 8;
      v130 = 100000;
      v131 = 25;
      v60 = 0;
      v61 = 0;
      v122 = 0;
      v68 = 0;
      v99 = -2147483645;
      v109 = -2147483645;
      v117 = 0;
      v123 = 3;
      v124 = 0;
      v85 = 0;
      v84 = 0;
      v76 = 0;
      v75 = 0;
      v91 = 0;
      v90 = 0;
      v87 = 0;
      v86 = 0;
      v113 = 0;
      v62 = 0;
      v106 = 30000;
      v12 = 0;
      v59 = 0;
      v101 = 2;
      v100 = 2;
      v77 = 0x4000;
      v102 = 0x4000;
      v114 = 0;
      v128 = 0x40000000;
      v127 = 0x40000000;
      v115 = 4;
      v64 = 0;
      RtlInitUnicodeString(&DestinationString, &NtfsCompatibilityModeKeyPath);
      v73 = *(_OWORD *)L"z|";
      while ( 1 )
      {
        if ( v10 == -1073741432 )
          NtfsCheckpointForLogFileFull(v5);
        if ( v5 )
          NtfsPreRequestProcessingExtend(v5, v10);
        *((_QWORD *)&v58 + 1) = L"DisableDeleteNotification";
        LODWORD(v58) = 3407922;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack < 0 )
        {
          ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                   (unsigned int)&DestinationString,
                                   (unsigned int)&v73,
                                   (unsigned int)&v58,
                                   (unsigned int)&v56,
                                   (__int64)&v55,
                                   (__int64)v54);
          if ( ValueKeyWithFallBack >= 0 )
            v110 = *(unsigned int *)((char *)v55 + v55[2]);
        }
        else
        {
          v110 = *(unsigned int *)((char *)v55 + v55[2]);
        }
        *((_QWORD *)&v58 + 1) = L"DisableDeleteNotificationDrain";
        LODWORD(v58) = 4063292;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack >= 0 )
          v116 = *(unsigned int *)((char *)v55 + v55[2]);
        *((_QWORD *)&v58 + 1) = L"NtfsDisable8dot3NameCreation";
        LODWORD(v58) = 3801144;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack < 0
          && (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v73,
                                       (unsigned int)&v58,
                                       (unsigned int)&v56,
                                       (__int64)&v55,
                                       (__int64)v54),
              ValueKeyWithFallBack < 0) )
        {
          v13 = 2;
        }
        else
        {
          v13 = *(unsigned int *)((char *)v55 + v55[2]);
        }
        if ( v13 > 3 )
          v13 = 2;
        v129 = v13;
        *((_QWORD *)&v58 + 1) = L"NtfsDisableLastAccessUpdate";
        LODWORD(v58) = 3670070;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack < 0 )
        {
          ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                   (unsigned int)&DestinationString,
                                   (unsigned int)&v73,
                                   (unsigned int)&v58,
                                   (unsigned int)&v56,
                                   (__int64)&v55,
                                   (__int64)v54);
          if ( ValueKeyWithFallBack >= 0 )
          {
            v99 = *(unsigned int *)((char *)v55 + v55[2]) & 0x80000003;
            v109 = v99;
          }
        }
        else
        {
          v99 = *(unsigned int *)((char *)v55 + v55[2]) & 1;
          v109 = v99;
          dword_140095AC4 |= 0x40000000u;
        }
        *((_QWORD *)&v58 + 1) = L"NtfsLastAccessUpdatePolicyVolumeSizeThreshold";
        LODWORD(v58) = 6029402;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack >= 0 )
          v117 = *(unsigned int *)((char *)v55 + v55[2]);
        *((_QWORD *)&v58 + 1) = L"NtfsForceReadOnlyMount";
        LODWORD(v58) = 3014700;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack < 0 )
          v118 = 0;
        else
          v118 = *(unsigned int *)((char *)v55 + v55[2]);
        *((_QWORD *)&v58 + 1) = L"NtfsDisableFileMetadataOptimization";
        LODWORD(v58) = 4718662;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack < 0 )
        {
          ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                   (unsigned int)&DestinationString,
                                   (unsigned int)&v73,
                                   (unsigned int)&v58,
                                   (unsigned int)&v56,
                                   (__int64)&v55,
                                   (__int64)v54);
          if ( ValueKeyWithFallBack >= 0 )
            v111 = *(unsigned int *)((char *)v55 + v55[2]);
        }
        else
        {
          v111 = *(unsigned int *)((char *)v55 + v55[2]);
        }
        *((_QWORD *)&v58 + 1) = L"NtfsDisableCompressionDelayedAllocation";
        LODWORD(v58) = 5242958;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v73,
                                       (unsigned int)&v58,
                                       (unsigned int)&v56,
                                       (__int64)&v55,
                                       (__int64)v54),
              ValueKeyWithFallBack >= 0) )
        {
          v14 = *(unsigned int *)((char *)v55 + v55[2]);
          v107 = v14;
        }
        else
        {
          v14 = v108;
        }
        if ( v14 > 1 )
          v14 = 1;
        v108 = v14;
        v107 = v14;
        *((_QWORD *)&v58 + 1) = L"NtfsDisableCompressionLimit";
        LODWORD(v58) = 3670070;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v73,
                                       (unsigned int)&v58,
                                       (unsigned int)&v56,
                                       (__int64)&v55,
                                       (__int64)v54),
              ValueKeyWithFallBack >= 0) )
        {
          v15 = *(unsigned int *)((char *)v55 + v55[2]);
          v93 = v15;
        }
        else
        {
          v15 = v94;
        }
        if ( v15 > 1 )
          v15 = 0;
        v94 = v15;
        v93 = v15;
        *((_QWORD *)&v58 + 1) = L"NtfsDisableSpotCorruptionHandling";
        LODWORD(v58) = 4456514;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack < 0 )
        {
          ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                   (unsigned int)&DestinationString,
                                   (unsigned int)&v73,
                                   (unsigned int)&v58,
                                   (unsigned int)&v56,
                                   (__int64)&v55,
                                   (__int64)v54);
          if ( ValueKeyWithFallBack >= 0 )
          {
            v83 = *(unsigned int *)((char *)v55 + v55[2]);
            v95 = v83;
          }
        }
        else
        {
          v83 = *(unsigned int *)((char *)v55 + v55[2]);
          v95 = v83;
        }
        *((_QWORD *)&v58 + 1) = L"NtfsBypassSpotCorruptionHandlingOnCritical";
        LODWORD(v58) = 5636180;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v73,
                                       (unsigned int)&v58,
                                       (unsigned int)&v56,
                                       (__int64)&v55,
                                       (__int64)v54),
              ValueKeyWithFallBack >= 0) )
        {
          v11 = *(unsigned int *)((char *)v55 + v55[2]);
          v96 = v11;
        }
        if ( v11 > 0xF )
          v11 = 1;
        v125 = v11;
        v96 = v11;
        *((_QWORD *)&v58 + 1) = L"NtfsMaxFspWorkerThreadsPerVolume";
        LODWORD(v58) = 4325440;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v16 = *(unsigned int *)((char *)v55 + v55[2]);
          v88 = v16;
          if ( v16 )
          {
            if ( v16 >= 4 )
            {
              if ( v16 > 0x3E8 )
                v16 = 1000;
              v88 = v16;
            }
            else
            {
              v88 = 4;
            }
          }
          else
          {
            v88 = 10;
          }
          v66 = 1;
          v2 = v77;
        }
        *((_QWORD *)&v58 + 1) = L"NtfsMinTrimTotalSize";
        LODWORD(v58) = 2752552;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack < 0 )
        {
          v17 = 0x100000;
        }
        else
        {
          v17 = *(unsigned int *)((char *)v55 + v55[2]);
          if ( v17 < 0x200000 )
            v17 = 0x200000;
        }
        *((_QWORD *)&v58 + 1) = L"NtfsMaxTrimTotalSize";
        LODWORD(v58) = 2752552;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack < 0 )
        {
          v119 = 0x40000000;
        }
        else
        {
          v18 = *(unsigned int *)((char *)v55 + v55[2]);
          if ( v18 < NtfsMinTrimTotalSize )
            v18 = NtfsMinTrimTotalSize;
          v119 = v18;
        }
        *((_QWORD *)&v58 + 1) = L"NtfsTrimListLengthThreshold";
        LODWORD(v58) = 3670070;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack < 0 )
        {
          v126 = 100000;
        }
        else
        {
          v126 = *(unsigned int *)((char *)v55 + v55[2]);
          if ( (unsigned int)(v126 - 1) <= 0x270E )
            goto LABEL_81;
        }
        v61 = 1;
LABEL_81:
        *((_QWORD *)&v58 + 1) = L"NtfsMaxWaitTimeForDeallocatedClustersInTrim";
        LODWORD(v58) = 5767254;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack < 0 )
          v120 = 60000;
        else
          v120 = *(unsigned int *)((char *)v55 + v55[2]);
        *((_QWORD *)&v58 + 1) = L"NtfsFlushTrimRequestsOnDismount";
        LODWORD(v58) = 4194366;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        NtfsFlushTrimRequestsOnDismount = ValueKeyWithFallBack >= 0 && *(unsigned int *)((char *)v55 + v55[2]) == 1;
        *((_QWORD *)&v58 + 1) = L"NtfsAllowMaximumSupportedHardLinks";
        LODWORD(v58) = 4587588;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        NtfsAllowMaximumSupportedHardLinks = ValueKeyWithFallBack >= 0 && *(unsigned int *)((char *)v55 + v55[2]) == 1;
        *((_QWORD *)&v58 + 1) = L"NtfsDisableTrueAsyncCachedReads";
        LODWORD(v58) = 4194366;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v121 = *(unsigned int *)((char *)v55 + v55[2]);
          v67 = 1;
        }
        *((_QWORD *)&v58 + 1) = L"NtfsFileMetadataOptimizationThreshold";
        LODWORD(v58) = 4980810;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v19 = *(unsigned int *)((char *)v55 + v55[2]);
          v103 = v19;
          if ( v19 >= 0xA )
          {
            if ( v19 > 0x5A )
              v19 = 90;
            v103 = v19;
          }
          else
          {
            v103 = 10;
          }
        }
        *((_QWORD *)&v58 + 1) = L"NtfsMaxFileMetadataOptimizationThread";
        LODWORD(v58) = 4980810;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v20 = *(unsigned int *)((char *)v55 + v55[2]);
          v105 = v20;
          if ( v20 )
          {
            if ( v20 > 0x3E8 )
              v20 = 1000;
            v105 = v20;
          }
          else
          {
            v105 = 1;
          }
        }
        *((_QWORD *)&v58 + 1) = L"NtfsEnableDirectAccess";
        LODWORD(v58) = 3014700;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v122 = *(unsigned int *)((char *)v55 + v55[2]);
          v68 = 1;
        }
        *((_QWORD *)&v58 + 1) = L"NtfsEnableDirCaseSensitivity";
        LODWORD(v58) = 3801144;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack >= 0 )
          v123 = *(unsigned int *)((char *)v55 + v55[2]);
        *((_QWORD *)&v58 + 1) = L"NtfsAllowQueryFreeSpaceConsiderPool";
        LODWORD(v58) = 4718662;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack >= 0 )
          v124 = *(unsigned int *)((char *)v55 + v55[2]);
        *((_QWORD *)&v58 + 1) = L"AllowHardLinkWithNoAccess";
        LODWORD(v58) = 3407922;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack < 0
          && (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v73,
                                       (unsigned int)&v58,
                                       (unsigned int)&v56,
                                       (__int64)&v55,
                                       (__int64)v54),
              ValueKeyWithFallBack < 0) )
        {
          v112 = 0;
        }
        else
        {
          v112 = *(unsigned int *)((char *)v55 + v55[2]);
        }
        *((_QWORD *)&v58 + 1) = L"NtfsParallelFlushThreshold";
        LODWORD(v58) = 3538996;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v73,
                                       (unsigned int)&v58,
                                       (unsigned int)&v56,
                                       (__int64)&v55,
                                       (__int64)v54),
              ValueKeyWithFallBack >= 0) )
        {
          v21 = *(unsigned int *)((char *)v55 + v55[2]);
          v84 = v21;
        }
        else
        {
          v21 = v85;
        }
        if ( !v21 )
        {
          v21 = 1000;
LABEL_124:
          v84 = v21;
          v85 = v21;
          goto LABEL_125;
        }
        if ( v21 >= 0x64 )
        {
          if ( v21 > 0xF4240 )
            v21 = 1000000;
          goto LABEL_124;
        }
        v85 = 100;
        v84 = 100;
LABEL_125:
        *((_QWORD *)&v58 + 1) = L"NtfsParallelFlushWorkers";
        LODWORD(v58) = 3276848;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v73,
                                       (unsigned int)&v58,
                                       (unsigned int)&v56,
                                       (__int64)&v55,
                                       (__int64)v54),
              ValueKeyWithFallBack >= 0) )
        {
          v22 = *(unsigned int *)((char *)v55 + v55[2]);
          v75 = v22;
        }
        else
        {
          v22 = v76;
        }
        if ( v22 )
        {
          if ( v22 > 2 * NtfsNumberProcessors )
            v22 = 2 * NtfsNumberProcessors;
        }
        else
        {
          v75 = ((unsigned int)NtfsNumberProcessors >> 1) + 1;
          v22 = 16;
          if ( v75 < 0x10 )
            v22 = ((unsigned int)NtfsNumberProcessors >> 1) + 1;
        }
        v75 = v22;
        v76 = v22;
        *((_QWORD *)&v58 + 1) = L"NtfsMinLengthForAZeroWorker";
        LODWORD(v58) = 3670070;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v73,
                                       (unsigned int)&v58,
                                       (unsigned int)&v56,
                                       (__int64)&v55,
                                       (__int64)v54),
              ValueKeyWithFallBack >= 0) )
        {
          v23 = *(unsigned int *)((char *)v55 + v55[2]);
          v90 = v23;
        }
        else
        {
          v23 = v91;
        }
        if ( v23 )
        {
          if ( v23 < 0x400000 )
            v23 = 0x400000;
          v91 = v23;
          v90 = v23;
        }
        else
        {
          v91 = 0x8000000;
          v90 = 0x8000000;
        }
        *((_QWORD *)&v58 + 1) = L"NtfsParallelZeroWorkers";
        LODWORD(v58) = 3145774;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v73,
                                       (unsigned int)&v58,
                                       (unsigned int)&v56,
                                       (__int64)&v55,
                                       (__int64)v54),
              ValueKeyWithFallBack >= 0) )
        {
          v24 = *(unsigned int *)((char *)v55 + v55[2]);
          v86 = v24;
        }
        else
        {
          v24 = v87;
        }
        if ( v24 )
        {
          if ( v24 > 0x10 )
            v24 = 16;
          v87 = v24;
          v86 = v24;
        }
        else
        {
          v87 = 1;
          v86 = 1;
        }
        *((_QWORD *)&v58 + 1) = L"NtfsLockSystemFilePages";
        LODWORD(v58) = 3145774;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v73,
                                       (unsigned int)&v58,
                                       (unsigned int)&v56,
                                       (__int64)&v55,
                                       (__int64)v54),
              ValueKeyWithFallBack >= 0) )
        {
          v25 = *(unsigned int *)((char *)v55 + v55[2]);
          v97 = v25;
        }
        else
        {
          v25 = v98;
        }
        if ( v25 > 3 )
          v25 = 1;
        v98 = v25;
        v97 = v25;
        *((_QWORD *)&v58 + 1) = L"NtfsDisableIoPerf";
        LODWORD(v58) = 2359330;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack < 0 )
        {
          ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                   (unsigned int)&DestinationString,
                                   (unsigned int)&v73,
                                   (unsigned int)&v58,
                                   (unsigned int)&v56,
                                   (__int64)&v55,
                                   (__int64)v54);
          if ( ValueKeyWithFallBack < 0 )
            goto LABEL_164;
          v113 = *(unsigned int *)((char *)v55 + v55[2]);
        }
        else
        {
          v113 = *(unsigned int *)((char *)v55 + v55[2]);
        }
        v62 = 1;
LABEL_164:
        *((_QWORD *)&v58 + 1) = L"NtfsMaxAcceptableLatency";
        LODWORD(v58) = 3276848;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack < 0 )
        {
          ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                   (unsigned int)&DestinationString,
                                   (unsigned int)&v73,
                                   (unsigned int)&v58,
                                   (unsigned int)&v56,
                                   (__int64)&v55,
                                   (__int64)v54);
          if ( ValueKeyWithFallBack < 0 )
          {
            v26 = v106;
          }
          else
          {
            v26 = *(unsigned int *)((char *)v55 + v55[2]);
            v106 = v26;
            v12 = 1;
            v59 = 1;
          }
          if ( !v12 )
            goto LABEL_173;
        }
        else
        {
          v26 = *(unsigned int *)((char *)v55 + v55[2]);
          v106 = v26;
          v59 = 1;
        }
        if ( v26 == dword_14009465C || (unsigned int)(v26 - 1) > 0x1D4BF )
          v59 = 0;
LABEL_173:
        *((_QWORD *)&v58 + 1) = L"NtfsKsrVersion";
        LODWORD(v58) = 1966108;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v73,
                                       (unsigned int)&v58,
                                       (unsigned int)&v56,
                                       (__int64)&v55,
                                       (__int64)v54),
              ValueKeyWithFallBack >= 0) )
        {
          v27 = *(unsigned int *)((char *)v55 + v55[2]);
          v100 = v27;
        }
        else
        {
          v27 = v101;
        }
        if ( v27 > 2 )
          v27 = 0;
        v101 = v27;
        v100 = v27;
        *((_QWORD *)&v58 + 1) = L"NtfsMaxDelayCloseCount";
        LODWORD(v58) = 3014700;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v2 = *(unsigned int *)((char *)v55 + v55[2]);
          v102 = v2;
        }
        if ( v2 >= 0x10 )
        {
          if ( v2 > 0x4000 )
            v2 = 0x4000;
          v77 = v2;
          v102 = v2;
        }
        else
        {
          v77 = 16;
          v102 = 16;
        }
        *((_QWORD *)&v58 + 1) = L"NtfsCachedRunsBinMaxLengthInBytes";
        LODWORD(v58) = 4456514;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v73,
                                       (unsigned int)&v58,
                                       (unsigned int)&v56,
                                       (__int64)&v55,
                                       (__int64)v54),
              ValueKeyWithFallBack >= 0) )
        {
          v28 = *(_QWORD *)((char *)v55 + v55[2]);
          v127 = v28;
        }
        else
        {
          v28 = v128;
        }
        if ( v28 )
        {
          if ( v28 < 0x4000000 )
            v28 = 0x4000000;
          v128 = v28;
          v127 = v28;
        }
        else
        {
          v128 = 0x40000000;
          v127 = 0x40000000;
        }
        *((_QWORD *)&v58 + 1) = L"NtfsDefaultTier";
        LODWORD(v58) = 2097182;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack < 0 )
        {
          ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                   (unsigned int)&DestinationString,
                                   (unsigned int)&v73,
                                   (unsigned int)&v58,
                                   (unsigned int)&v56,
                                   (__int64)&v55,
                                   (__int64)v54);
          if ( ValueKeyWithFallBack >= 0 )
            v114 = *(unsigned int *)((char *)v55 + v55[2]);
        }
        else
        {
          v114 = *(unsigned int *)((char *)v55 + v55[2]);
        }
        *((_QWORD *)&v58 + 1) = L"NtfsMaxCachedRuns";
        LODWORD(v58) = 2359330;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack < 0 )
        {
          v29 = v82;
        }
        else
        {
          v29 = *(unsigned int *)((char *)v55 + v55[2]);
          v82 = v29;
          if ( v29 )
          {
            if ( v29 >= 0x2328 )
            {
              if ( v29 > 0xFFFE )
                v29 = 65534;
            }
            else
            {
              v29 = 9000;
            }
          }
          else
          {
            v29 = 65534;
          }
          v82 = v29;
        }
        *((_QWORD *)&v58 + 1) = L"NtfsInitialCachedRuns";
        LODWORD(v58) = 2883626;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v30 = *(unsigned int *)((char *)v55 + v55[2]);
          v78 = v30;
          if ( !v30 )
          {
            v30 = 512;
            if ( byte_1400951DA == 1 )
              v30 = 32;
LABEL_213:
            v79 = v30;
            v78 = v30;
            goto LABEL_214;
          }
          if ( v30 >= 0x20 )
          {
            if ( v30 > v29 )
              v30 = v29;
            goto LABEL_213;
          }
          v79 = 32;
          v78 = 32;
        }
LABEL_214:
        *((_QWORD *)&v58 + 1) = L"NtfsCachedRunsDelta";
        LODWORD(v58) = 2621478;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack < 0 )
          goto LABEL_229;
        v31 = *(unsigned int *)((char *)v55 + v55[2]);
        v80 = v31;
        if ( v31 )
        {
          if ( v31 < 0x200 )
          {
            v81 = 512;
            v80 = 512;
            goto LABEL_229;
          }
          if ( v31 > v29 )
            v31 = v29;
        }
        else
        {
          v31 = 0x2000;
          if ( byte_1400951DA == 1 )
            v31 = 512;
        }
        v80 = v31;
        v81 = v31;
LABEL_229:
        *((_QWORD *)&v58 + 1) = L"NtfsCachedRunsLimitMode";
        LODWORD(v58) = 3145774;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v32 = *(unsigned int *)((char *)v55 + v55[2]);
          v115 = v32;
          if ( (unsigned int)(v32 - 1) > 3 )
            v32 = 4;
          v115 = v32;
        }
        *((_QWORD *)&v58 + 1) = L"NtfsCachedRunsInsertLimit";
        LODWORD(v58) = 3407922;
        ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                 (unsigned int)&DestinationString,
                                 (unsigned int)&v73,
                                 (unsigned int)&v58,
                                 (unsigned int)&v56,
                                 (__int64)&v55,
                                 (__int64)v54);
        if ( ValueKeyWithFallBack >= 0 )
        {
          v33 = *(unsigned int *)((char *)v55 + v55[2]);
          v89 = v33;
          if ( v33 )
          {
            if ( v33 >= 0x400 )
            {
              if ( v33 > v29 )
                v33 = v29;
              v89 = v33;
            }
            else
            {
              v89 = 1024;
            }
          }
          else
          {
            v89 = 0x4000;
          }
        }
        v34 = 1;
        *((_QWORD *)&v58 + 1) = L"NtfsLimitPhysicalSectorSize";
        LODWORD(v58) = 3670070;
        ValueKeyWithFallBack = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        if ( ValueKeyWithFallBack >= 0
          || (ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                                       (unsigned int)&DestinationString,
                                       (unsigned int)&v73,
                                       (unsigned int)&v58,
                                       (unsigned int)&v56,
                                       (__int64)&v55,
                                       (__int64)v54),
              ValueKeyWithFallBack >= 0) )
        {
          v34 = *(unsigned int *)((char *)v55 + v55[2]);
        }
        v35 = Feature_NTFS_DirectoryChangeNotifyListDirectoryAccessCheck__private_IsEnabledDeviceUsageNoInline() != 0;
        *((_QWORD *)&v58 + 1) = L"EnforceDirectoryChangeNotificationPermissionCheck";
        LODWORD(v58) = 6553698;
        v10 = NtfsQueryValueKey(&v92, &v58, &v56, &v55, v54);
        ValueKeyWithFallBack = v10;
        if ( v10 < 0 )
        {
          v10 = NtfsQueryValueKeyWithFallBack(
                  (unsigned int)&DestinationString,
                  (unsigned int)&v73,
                  (unsigned int)&v58,
                  (unsigned int)&v56,
                  (__int64)&v55,
                  (__int64)v54);
          ValueKeyWithFallBack = v10;
          v1 = v55;
          if ( v10 < 0 )
            goto LABEL_248;
        }
        else
        {
          v1 = v55;
        }
        v35 = *(unsigned int *)((char *)v1 + v1[2]);
LABEL_248:
        ExAcquireResourceExclusiveLite(&Resource, 1u);
        v65 = 1;
        v36 = dword_1400956B8;
        if ( v110 == 1 )
        {
          if ( (dword_1400956B8 & 0x80000) != 0 )
            goto LABEL_254;
          v36 = dword_1400956B8 | 0x80000;
        }
        else
        {
          if ( (dword_1400956B8 & 0x80000) == 0 )
            goto LABEL_254;
          v36 = dword_1400956B8 & 0xFFF7FFFF;
        }
        dword_1400956B8 = v36;
        v63 = 1;
LABEL_254:
        if ( v116 == 1 )
          v37 = v36 | 0x20000;
        else
          v37 = v36 & 0xFFFDFFFF;
        dword_1400956B8 = v37;
        if ( dword_1400953B4 != v129 )
        {
          dword_1400953B4 = v129;
          v69 = 1;
        }
        dword_140095AC4 = v99;
        qword_140095AC8 = (unsigned __int64)v117 << 30;
        if ( v118 )
          v38 = v37 | 0x10;
        else
          v38 = v37 & 0xFFFFFFEF;
        dword_1400956B8 = v38;
        if ( (v111 & 1) != 0 )
          v39 = v38 | 4;
        else
          v39 = v38 & 0xFFFFFFFB;
        dword_1400956B8 = v39;
        if ( (v111 & 2) != 0 )
          v40 = v39 | 8;
        else
          v40 = v39 & 0xFFFFFFF7;
        dword_1400956B8 = v40;
        if ( v108 == 1 )
          v41 = v40 | 0x100;
        else
          v41 = v40 & 0xFFFFFEFF;
        dword_1400956B8 = v41;
        if ( v94 == 1 )
          v42 = v41 | 0x200;
        else
          v42 = v41 & 0xFFFFFDFF;
        dword_1400956B8 = v42;
        if ( v83 <= 0xF )
        {
          v43 = v83;
        }
        else
        {
          v43 = (v42 >> 14) & 1;
          v83 = v43;
          v95 = v43;
        }
        if ( dword_1400953B8 != v43 )
        {
          dword_1400953B8 = v43;
          v70 = 1;
        }
        v44 = v125;
        if ( dword_1400953BC != v125 )
        {
          dword_1400953BC = v125;
          v71 = 1;
        }
        if ( v66 )
        {
          if ( a1 )
          {
            v44 = v88;
            if ( dword_140095AB0 != v88 )
            {
              dword_140095AB0 = v88;
              dword_140095AC0 = v88 < 0x2EE ? 1000 : 2000;
            }
          }
        }
        if ( NtfsMaxTrimTotalSize < v17 )
        {
          v17 = NtfsMaxTrimTotalSize;
          v60 = 1;
        }
        v45 = NtfsMinTrimTotalSize;
        if ( NtfsMinTrimTotalSize != v17 )
        {
          if ( (!v104 || (*((_DWORD *)v104 + 4) & 0x100000) == 0)
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
          {
            McTemplateU0q_EtwWriteTransfer(v44, (const EVENT_DESCRIPTOR *)ntfsinit_c6389, v17);
          }
          v45 = v17;
          NtfsMinTrimTotalSize = v17;
          v60 = 1;
        }
        v46 = v119;
        if ( v119 < v45 )
          v46 = v45;
        if ( NtfsMaxTrimTotalSize == v46 )
        {
          v47 = v60;
        }
        else
        {
          if ( (!v104 || (*((_DWORD *)v104 + 4) & 0x100000) == 0)
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
          {
            McTemplateU0q_EtwWriteTransfer(v44, (const EVENT_DESCRIPTOR *)ntfsinit_c6410, v46);
          }
          NtfsMaxTrimTotalSize = v46;
          v47 = 1;
          v60 = 1;
        }
        if ( v61 )
          NtfsTrimListLengthThreshold = v126;
        NtfsMaxWaitTimeForDeallocatedClustersInTrim = 10000 * (unsigned __int64)v120 / (unsigned int)dword_1400953B0;
        if ( v67 )
        {
          if ( v121 )
          {
            if ( v121 == 1 )
              LOBYTE(word_140095AD0) = 1;
          }
          else
          {
            LOBYTE(word_140095AD0) = 0;
          }
        }
        if ( v103 != dword_140095AB4 )
          dword_140095AB4 = v103;
        if ( v105 != dword_1400958A4 )
          dword_1400958A4 = v105;
        if ( v130 != dword_140095AB8 )
          dword_140095AB8 = 100000;
        if ( v131 != dword_140095ABC )
          dword_140095ABC = 25;
        if ( v68 )
          HIBYTE(word_140095AD0) = v122 != 0;
        dword_140095AD4 = v123;
        if ( v124 )
        {
          if ( dword_1400956B8 < 0 )
            goto LABEL_325;
          v48 = dword_1400956B8 | 0x80000000;
        }
        else
        {
          if ( dword_1400956B8 >= 0 )
            goto LABEL_325;
          v48 = dword_1400956B8 & 0x7FFFFFFF;
        }
        dword_1400956B8 = v48;
LABEL_325:
        byte_140095AD2 = v112 == 1;
        dword_140095AD8 = v85;
        dword_140095ADC = v76;
        dword_140095C60 = v91;
        dword_140095C64 = v87;
        if ( dword_140095C14 != v98 )
        {
          dword_140095C14 = v98;
          v72 = 1;
        }
        if ( v62 )
          IoPerfRegistryConfig = v113 != 0;
        if ( v59 )
          dword_14009465C = v106;
        dword_140095BEC = v101;
        v49 = NtfsMaxDelayCloseCount;
        if ( !NtfsMaxDelayCloseCount )
        {
          v49 = 0x4000;
          NtfsMaxDelayCloseCount = 0x4000;
        }
        if ( v77 < v49 )
        {
          NtfsMinDelayCloseCount = 4 * v77 / 5;
          NtfsMaxDelayCloseCount = v77;
        }
        else
        {
          NtfsMaxDelayCloseCount = v77;
          NtfsMinDelayCloseCount = 4 * v77 / 5;
        }
        v50 = (unsigned __int8)FsRtlIsMobileOS() == 0;
        v51 = NtfsMinDelayCloseCount;
        if ( v50 )
          v51 = 2 * NtfsMinDelayCloseCount;
        NtfsThrottleCreates = v51;
        if ( qword_140095C58 != v128 )
        {
          qword_140095C58 = v128;
          v64 = 1;
        }
        v52 = v114;
        if ( (unsigned int)(v114 - 1) > 1 )
          v52 = (byte_1400951DA == 1) + 1;
        dword_140095C6C = v52;
        if ( word_140095C70 != (_WORD)v82 )
        {
          word_140095C70 = v82;
          v64 = 1;
        }
        word_140095C72 = v79;
        word_140095C74 = v81;
        dword_140095C78 = v115;
        word_140095C7C = v89;
        byte_140095C56 = v34 != 0;
        byte_140095C7E = v35 != 0;
        ExReleaseResourceLite(&Resource);
        v65 = 0;
        if ( a1 )
        {
          v53 = (int)v104;
          if ( v63 )
            NtfsForEachVcb((_DWORD)v104, 0, 0, (unsigned int)NtfsUpdateDeleteNotificationVolumeSetting, 0, 0);
          if ( v47 )
            NtfsForEachVcb(v53, 0, 0, (unsigned int)NtfsUpdateTrimLimitsVolumeSetting, 0, 0);
          if ( v69 )
            NtfsForEachVcb(v53, 0, 0, (unsigned int)NtfsUpdateShortNameCreationVolumeSetting, 0, 0);
          if ( v70 || v71 )
            NtfsForEachVcb(v53, 0, 0, (unsigned int)NtfsUpdateCorruptionHandlingVolumeSetting, 0, 0);
          if ( v72 )
            NtfsForEachVcb(v53, 0, 0, (unsigned int)NtfsUpdateLockSystemFilePagesVolumeSetting, 0, 1);
          if ( v64 )
            NtfsForEachVcb(v53, 0, 0, (unsigned int)NtfsUpdateVcbStateToReloadClusters, 0, 0);
          if ( v59 )
            IoPerfRegistryUpdateConfig();
        }
        v5 = (__int64)v104;
        NtfsExtendedCompleteRequestInternal((__int64)v104, 0, 0, 0, 1);
        v2 = v77;
        v11 = v125;
        if ( v10 != -1073741608 && v10 != -1073741432 )
          break;
        v12 = v59;
      }
    }
    if ( v54[0] )
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
