# RefsUpdateDynamicRegistrySettings

- ea: `0x1c0175ab0`
- end: `0x1c017748f`
- name: `RefsUpdateDynamicRegistrySettings`
- size: `6623`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1c01d7324`

## callees

- `0x1c0005564`
- `0x1c0005650`
- `0x1c000f480`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c00588cc`
- `0x1c0062ce0`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c01716fc`
- `0x1c0175ab0`
- `0x1c0177498`
- `0x1c01cd29c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c0177436`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0177436`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017716d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01773d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0177449`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017716d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01773d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0177449`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0175ce0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0175d47`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0175ce0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0175d47`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0175cb6`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0175cb6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0175cca`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0175cca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0177455`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0177455`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c0176162`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c01762eb`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c01763ae`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c0176454`

## string_xrefs

- `0x1c0175d06`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x1c0175cec`: `\Registry\Machine\System\CurrentControlSet\Policies`
- `0x1c0175d58`: `RefsDisableDeleteNotification`
- `0x1c0175ebb`: `RefsFailIncompleteLogRedo`
- `0x1c01761a6`: `RefsDisableAsyncDelete`
- `0x1c0176830`: `DataDestageCompactionThreshold`
- `0x1c0176a18`: `RefsContainerRotationThreadCount`
- `0x1c0176dca`: `RefsReadCacheSampleInterval`
- `0x1c0176e76`: `RefsSmrUpdateSampleInterval`
- `0x1c017707a`: `RefsDisableTrueAsyncCachedReads`
- `0x1c01770e5`: `EnforceDirectoryChangeNotificationPermissionCheck`

## pseudocode

```c
void __fastcall RefsUpdateDynamicRegistrySettings(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v2; // rdx
  int v3; // r14d
  __int64 v4; // rcx
  _BYTE *v5; // rdi
  int v6; // edx
  int v7; // eax
  int v8; // eax
  char *v9; // rdx
  unsigned int v10; // ecx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  char v15; // cl
  int v16; // edx
  int v17; // edi
  int v18; // edi
  _BYTE v19[4]; // [rsp+30h] [rbp-2E8h] BYREF
  int v20; // [rsp+34h] [rbp-2E4h] BYREF
  PVOID P; // [rsp+38h] [rbp-2E0h] BYREF
  int v22; // [rsp+40h] [rbp-2D8h]
  __int128 v23; // [rsp+48h] [rbp-2D0h] BYREF
  char v24; // [rsp+58h] [rbp-2C0h]
  char v25; // [rsp+59h] [rbp-2BFh]
  char v26; // [rsp+5Ah] [rbp-2BEh]
  char v27; // [rsp+5Bh] [rbp-2BDh]
  char v28; // [rsp+5Ch] [rbp-2BCh]
  char v29; // [rsp+5Dh] [rbp-2BBh]
  char v30; // [rsp+5Eh] [rbp-2BAh]
  char v31; // [rsp+5Fh] [rbp-2B9h]
  char v32; // [rsp+60h] [rbp-2B8h]
  char v33; // [rsp+61h] [rbp-2B7h]
  char v34; // [rsp+62h] [rbp-2B6h]
  char v35; // [rsp+63h] [rbp-2B5h]
  char v36; // [rsp+64h] [rbp-2B4h]
  char v37; // [rsp+65h] [rbp-2B3h]
  char v38; // [rsp+66h] [rbp-2B2h]
  char v39; // [rsp+67h] [rbp-2B1h]
  char v40; // [rsp+68h] [rbp-2B0h]
  char v41; // [rsp+69h] [rbp-2AFh]
  char v42; // [rsp+6Ah] [rbp-2AEh]
  char v43; // [rsp+6Bh] [rbp-2ADh]
  char v44; // [rsp+6Ch] [rbp-2ACh]
  _DWORD v45[2]; // [rsp+70h] [rbp-2A8h] BYREF
  const wchar_t *v46; // [rsp+78h] [rbp-2A0h]
  _DWORD v47[2]; // [rsp+80h] [rbp-298h] BYREF
  const wchar_t *v48; // [rsp+88h] [rbp-290h]
  unsigned int v49; // [rsp+90h] [rbp-288h]
  unsigned int v50; // [rsp+94h] [rbp-284h]
  unsigned int v51; // [rsp+98h] [rbp-280h]
  unsigned int v52; // [rsp+9Ch] [rbp-27Ch]
  int v53; // [rsp+A0h] [rbp-278h]
  _BYTE *v54; // [rsp+A8h] [rbp-270h] BYREF
  unsigned int v55; // [rsp+B0h] [rbp-268h]
  unsigned int v56; // [rsp+B4h] [rbp-264h]
  unsigned int v57; // [rsp+B8h] [rbp-260h]
  unsigned int v58; // [rsp+BCh] [rbp-25Ch]
  int v59; // [rsp+C0h] [rbp-258h]
  int v60; // [rsp+C4h] [rbp-254h]
  unsigned int v61; // [rsp+C8h] [rbp-250h]
  unsigned int v62; // [rsp+CCh] [rbp-24Ch]
  unsigned int v63; // [rsp+D0h] [rbp-248h]
  unsigned int v64; // [rsp+D4h] [rbp-244h]
  unsigned int v65; // [rsp+D8h] [rbp-240h]
  int v66; // [rsp+DCh] [rbp-23Ch]
  int v67; // [rsp+E0h] [rbp-238h]
  int v68; // [rsp+E4h] [rbp-234h]
  int v69; // [rsp+E8h] [rbp-230h]
  unsigned int v70; // [rsp+ECh] [rbp-22Ch]
  int v71; // [rsp+F0h] [rbp-228h]
  int v72; // [rsp+F4h] [rbp-224h]
  int v73; // [rsp+F8h] [rbp-220h]
  int v74; // [rsp+FCh] [rbp-21Ch]
  unsigned int v75; // [rsp+100h] [rbp-218h]
  int v76; // [rsp+104h] [rbp-214h]
  _OWORD v77[2]; // [rsp+110h] [rbp-208h] BYREF
  __int64 v78; // [rsp+130h] [rbp-1E8h]
  _BYTE v79[256]; // [rsp+140h] [rbp-1D8h] BYREF
  _BYTE v80[160]; // [rsp+240h] [rbp-D8h] BYREF

  memset(v79, 0, sizeof(v79));
  v54 = v79;
  memset(v77, 0, sizeof(v77));
  v78 = 0;
  v26 = 0;
  v47[1] = 0;
  v45[1] = 0;
  v23 = 0;
  v20 = 156;
  P = v80;
  v19[0] = 0;
  v25 = 0;
  v27 = 0;
  v53 = 1;
  v69 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v59 = 0;
  v60 = 0;
  v55 = -1;
  v37 = 0;
  v56 = -1;
  v38 = 0;
  v57 = -1;
  v39 = 0;
  v58 = -1;
  v40 = 0;
  v49 = -1;
  v41 = 0;
  v50 = -1;
  v42 = 0;
  v51 = -1;
  v43 = 0;
  v52 = -1;
  v44 = 0;
  v31 = 0;
  v62 = 0;
  v32 = 0;
  v63 = 0;
  v33 = 0;
  v64 = 0;
  v34 = 0;
  v65 = 0;
  v35 = 0;
  v70 = 0;
  v36 = 0;
  v61 = 0;
  v30 = 0;
  v24 = 0;
  v29 = 0;
  v67 = 0;
  v28 = 0;
  v68 = 0;
  v66 = 0;
  v1 = RefsInitializeTopLevelIrp(v77, 0, 0);
  LOBYTE(v2) = 1;
  v3 = RefsInitializeIrpContext(0, v2, 0, &v54);
  if ( v3 < 0 )
    return;
  v4 = *(_QWORD *)(v1 + 32);
  v5 = v54;
  if ( !v4 )
  {
    *(_DWORD *)(v1 + 4) = 1397140410;
    *(_QWORD *)(v1 + 32) = v5;
    *((_DWORD *)v5 + 2) |= 0x100000u;
    IoSetTopLevelIrp((PIRP)v1);
    v4 = *(_QWORD *)(v1 + 32);
  }
  *((_QWORD *)v5 + 13) = v4;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&RefsDynamicRegistrySettingsResource, 1u);
  v48 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies";
  v47[0] = 6815846;
  v46 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem";
  v45[0] = 8126586;
  do
  {
    if ( v3 == -1073741432 )
      RefsCheckpointForLogFileFull(v5);
    if ( v5 )
      RefsPreRequestProcessingExtend(v5);
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    v26 = 1;
    *((_QWORD *)&v23 + 1) = L"RefsDisableDeleteNotification";
    LODWORD(v23) = 3932218;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 < 0 && (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 < 0) )
    {
      v6 = 0;
      v74 = 0;
    }
    else
    {
      v6 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v74 = v6;
    }
    if ( v6 == 1 )
    {
      if ( (dword_1C012E0B0 & 0x8000) == 0 )
      {
        v7 = dword_1C012E0B0 | 0x8000;
LABEL_18:
        dword_1C012E0B0 = v7;
        v25 = 1;
      }
    }
    else if ( (dword_1C012E0B0 & 0x8000) != 0 )
    {
      v7 = dword_1C012E0B0 & 0xFFFF7FFF;
      goto LABEL_18;
    }
    *((_QWORD *)&v23 + 1) = L"EnableMetadataPrefetch";
    LODWORD(v23) = 3014700;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v53 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v53 == 1 )
    {
      if ( (dword_1C012E0B0 & 0x80000) == 0 )
      {
        v8 = dword_1C012E0B0 | 0x80000;
LABEL_27:
        dword_1C012E0B0 = v8;
      }
    }
    else if ( (dword_1C012E0B0 & 0x80000) != 0 )
    {
      v8 = dword_1C012E0B0 & 0xFFF7FFFF;
      goto LABEL_27;
    }
    *((_QWORD *)&v23 + 1) = L"RefsFailIncompleteLogRedo";
    LODWORD(v23) = 3407922;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v66 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    RefsFailIncompleteLogRedo = v66 == 1;
    *((_QWORD *)&v23 + 1) = L"RefsInvalidateOnFileLevelTrim";
    LODWORD(v23) = 3932218;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 )
    {
      v9 = (char *)P;
LABEL_34:
      v10 = *(_DWORD *)&v9[*((unsigned int *)v9 + 2)];
      v75 = v10;
      goto LABEL_36;
    }
    v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19);
    v9 = (char *)P;
    if ( v22 >= 0 )
      goto LABEL_34;
    v10 = 0;
    v75 = 0;
LABEL_36:
    if ( dword_1C012DED4 != (v10 < 3 ? v10 : 0) )
    {
      dword_1C012DED4 = v10 < 3 ? v10 : 0;
      v27 = 1;
    }
    if ( !v9 )
    {
      v19[0] = 0;
      v20 = 156;
      P = v80;
    }
    *((_QWORD *)&v23 + 1) = L"EnableExtraIoAnalysis";
    LODWORD(v23) = 2883626;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v69 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    v11 = dword_1C012E0B0;
    if ( (v69 & 1) != 0 )
    {
      dword_1C012E0B0 |= 0x200u;
      v12 = v11 | 0x600;
    }
    else
    {
      v12 = dword_1C012E0B0 & 0xFFFFFDFF;
    }
    dword_1C012E0B0 = v12;
    if ( !P )
    {
      v19[0] = 0;
      v20 = 156;
      P = v80;
    }
    *((_QWORD *)&v23 + 1) = L"RefsEnableMetadataRetrievalPointers";
    LODWORD(v23) = 4718662;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v71 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( (v71 & 1) != 0 && (_BYTE)KdDebuggerEnabled )
      v13 = dword_1C012E0B0 | 0x20000;
    else
      v13 = dword_1C012E0B0 & 0xFFFDFFFF;
    dword_1C012E0B0 = v13;
    if ( !P )
    {
      v19[0] = 0;
      v20 = 156;
      P = v80;
    }
    *((_QWORD *)&v23 + 1) = L"RefsDisableAsyncDelete";
    LODWORD(v23) = 3014700;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v72 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( (v72 & 1) != 0 )
      v14 = dword_1C012E0B0 & 0xFFDFFFFF;
    else
      v14 = dword_1C012E0B0 | 0x200000;
    dword_1C012E0B0 = v14;
    if ( !P )
    {
      v19[0] = 0;
      v20 = 156;
      P = v80;
    }
    *((_QWORD *)&v23 + 1) = L"RefsDisableSqmThrottling";
    LODWORD(v23) = 3276848;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v73 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v73 == 1 && (_BYTE)KdDebuggerEnabled )
      _InterlockedOr(&InstrumentThrottle, 1u);
    else
      _InterlockedAnd(&InstrumentThrottle, 0xFFFFFFFE);
    if ( !P )
    {
      v19[0] = 0;
      v20 = 156;
      P = v80;
    }
    *((_QWORD *)&v23 + 1) = L"RefsDisableEtwThrottling";
    LODWORD(v23) = 3276848;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v59 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v59 == 1 && (_BYTE)KdDebuggerEnabled )
      _InterlockedOr(&InstrumentThrottle, 2u);
    else
      _InterlockedAnd(&InstrumentThrottle, 0xFFFFFFFD);
    *((_QWORD *)&v23 + 1) = L"RefsDisableTelemetryThrottling";
    LODWORD(v23) = 4063292;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v60 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v60 == 1 && (_BYTE)KdDebuggerEnabled )
      _InterlockedOr(&InstrumentThrottle, 4u);
    else
      _InterlockedAnd(&InstrumentThrottle, 0xFFFFFFFB);
    if ( !P )
    {
      v19[0] = 0;
      v20 = 156;
      P = v80;
    }
    *((_QWORD *)&v23 + 1) = L"DataDestageSsdFillRatioEventThreshold";
    LODWORD(v23) = 4980810;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v61 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v61 <= 0x64 && v61 != dword_1C012E6D0 )
    {
      dword_1C012E6D0 = v61;
      v36 = 1;
    }
    if ( !P )
    {
      v19[0] = 0;
      v20 = 156;
      P = v80;
    }
    *((_QWORD *)&v23 + 1) = L"DataDestageSsdFillRatioThreshold";
    LODWORD(v23) = 4325440;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v62 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v62 <= 0x64 && v62 != dword_1C012E6BC )
    {
      dword_1C012E6BC = v62;
      v31 = 1;
    }
    if ( !P )
    {
      v19[0] = 0;
      v20 = 156;
      P = v80;
    }
    *((_QWORD *)&v23 + 1) = L"MetadataDestageSsdFillRatioThreshold";
    LODWORD(v23) = 4849736;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v63 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v63 <= 0x64 && v63 != dword_1C012E6C0 )
    {
      dword_1C012E6C0 = v63;
      v32 = 1;
    }
    if ( !P )
    {
      v19[0] = 0;
      v20 = 156;
      P = v80;
    }
    *((_QWORD *)&v23 + 1) = L"DataDestageHddFillRatioThreshold";
    LODWORD(v23) = 4325440;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v64 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v64 <= 0x64 && v64 != dword_1C012E6C4 )
    {
      dword_1C012E6C4 = v64;
      v33 = 1;
    }
    if ( !P )
    {
      v19[0] = 0;
      v20 = 156;
      P = v80;
    }
    *((_QWORD *)&v23 + 1) = L"MetadataDestageHddFillRatioThreshold";
    LODWORD(v23) = 4849736;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v65 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v65 <= 0x64 && v65 != dword_1C012E6C8 )
    {
      dword_1C012E6C8 = v65;
      v34 = 1;
    }
    if ( !P )
    {
      v19[0] = 0;
      v20 = 156;
      P = v80;
    }
    *((_QWORD *)&v23 + 1) = L"DataDestageCompactionThreshold";
    LODWORD(v23) = 4063292;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v70 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v70 <= 0x64 && v70 != dword_1C012E6CC )
    {
      dword_1C012E6CC = v70;
      v35 = 1;
    }
    *((_QWORD *)&v23 + 1) = L"RefsEnableParallelContainerRotation";
    LODWORD(v23) = 4718662;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
    {
      v24 = 1;
    }
    else
    {
      v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19);
      if ( v22 >= 0 )
      {
        v15 = v24;
        if ( *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
          v15 = 1;
        v24 = v15;
      }
    }
    if ( RefsEnableParallelContainerRotation != v24 )
    {
      RefsEnableParallelContainerRotation = v24;
      v30 = 1;
    }
    *((_QWORD *)&v23 + 1) = L"RefsContainerRotationQueueSizeLimit";
    LODWORD(v23) = 4718662;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v67 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( RefsContainerRotationQueueSizeLimit != v67 )
    {
      RefsContainerRotationQueueSizeLimit = v67;
      v29 = 1;
    }
    *((_QWORD *)&v23 + 1) = L"RefsContainerRotationThreadCount";
    LODWORD(v23) = 4325440;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v68 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v68 != RefsContainerRotationThreadCount )
    {
      RefsContainerRotationThreadCount = v68;
      v28 = 1;
    }
    *((_QWORD *)&v23 + 1) = L"RefsCheckpointSampleInterval";
    LODWORD(v23) = 3801144;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v55 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v55 != -1 && (_QWORD)RefsTelemetrySampling != 10000000LL * v55 )
    {
      *(_QWORD *)&RefsTelemetrySampling = 10000000LL * v55;
      v37 = 1;
    }
    *((_QWORD *)&v23 + 1) = L"RefsBlockRefcountSampleInterval";
    LODWORD(v23) = 4194366;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v56 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v56 != -1 && *((_QWORD *)&RefsTelemetrySampling + 1) != 10000000LL * v56 )
    {
      *((_QWORD *)&RefsTelemetrySampling + 1) = 10000000LL * v56;
      v38 = 1;
    }
    *((_QWORD *)&v23 + 1) = L"RefsGhostExtentsSampleInterval";
    LODWORD(v23) = 4063292;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v57 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v57 != -1 && (_QWORD)xmmword_1C012DD50 != 10000000LL * v57 )
    {
      *(_QWORD *)&xmmword_1C012DD50 = 10000000LL * v57;
      v39 = 1;
    }
    *((_QWORD *)&v23 + 1) = L"RefsPerfCountersSampleInterval";
    LODWORD(v23) = 4063292;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 < 0 )
      v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19);
    *((_QWORD *)&v23 + 1) = L"RefsContainerRotationSampleInterval";
    LODWORD(v23) = 4718662;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v58 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v58 != -1 && qword_1C012DD60 != 10000000LL * v58 )
    {
      qword_1C012DD60 = 10000000LL * v58;
      v40 = 1;
    }
    *((_QWORD *)&v23 + 1) = L"RefsReadCacheSampleInterval";
    LODWORD(v23) = 3670070;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v49 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v49 != -1 && qword_1C012DD68 != 10000000LL * v49 )
    {
      qword_1C012DD68 = 10000000LL * v49;
      v41 = 1;
    }
    *((_QWORD *)&v23 + 1) = L"RefsSmrUpdateSampleInterval";
    LODWORD(v23) = 3670070;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v50 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v50 != -1 && (_QWORD)xmmword_1C012DD70 != 10000000LL * v50 )
    {
      *(_QWORD *)&xmmword_1C012DD70 = 10000000LL * v50;
      v42 = 1;
    }
    *((_QWORD *)&v23 + 1) = L"RefsSmrSampleInterval";
    LODWORD(v23) = 2883626;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v51 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v51 != -1 && *((_QWORD *)&xmmword_1C012DD70 + 1) != 10000000LL * v51 )
    {
      *((_QWORD *)&xmmword_1C012DD70 + 1) = 10000000LL * v51;
      v43 = 1;
    }
    *((_QWORD *)&v23 + 1) = L"RefsLogFileFullSampleInterval";
    LODWORD(v23) = 3932218;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v52 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v52 != -1 && qword_1C012DD80 != 10000000LL * v52 )
    {
      qword_1C012DD80 = 10000000LL * v52;
      v44 = 1;
    }
    *((_QWORD *)&v23 + 1) = L"RefsDisableTrueAsyncCachedReads";
    LODWORD(v23) = 4194366;
    v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19);
    if ( v22 >= 0 )
    {
      v16 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      v76 = v16;
      if ( v16 )
      {
        if ( v16 == 1 )
          byte_1C012E6B8 = 1;
      }
      else
      {
        byte_1C012E6B8 = 0;
      }
    }
    v17 = 0;
    *((_QWORD *)&v23 + 1) = L"EnforceDirectoryChangeNotificationPermissionCheck";
    LODWORD(v23) = 6553698;
    v22 = RefsQueryValueKey(v47, &v23, &v20, &P, v19);
    if ( v22 >= 0 || (v22 = RefsQueryValueKey(v45, &v23, &v20, &P, v19), v22 >= 0) )
      v17 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    byte_1C012E6D4 = v17 != 0;
    ExReleaseResourceLite(&Resource);
    v26 = 0;
    v18 = (int)v54;
    if ( a1 )
    {
      if ( v25 )
        RefsForEachVcb((_DWORD)v54, 0, (unsigned int)RefsUpdateDeleteNotificationVolumeSetting, 0, 0);
      if ( v53 )
        RefsForEachVcb(v18, 0, (unsigned int)RefsUpdateEnableMetadataPrefetchVolumeSetting, 0, 0);
      if ( v27 )
        RefsForEachVcb(v18, 0, (unsigned int)RefsUpdateFileLevelTrimVolumeSetting, 0, 0);
      if ( v28 || v29 || v30 )
      {
        dword_1C0136988 = RefsContainerRotationThreadCount;
        dword_1C013698C = RefsContainerRotationQueueSizeLimit;
        byte_1C0136986 = RefsEnableParallelContainerRotation;
        RefsForEachVcb(v18, 0, (unsigned int)RefsUpdateContainerRotationThreadCount, 0, 0);
      }
    }
    if ( v31 || v32 || v33 || v34 || v35 )
      RefsForEachVcb(v18, 0, (unsigned int)RefsUpdateContainerMoveThresholdsVolumeSetting, 0, 0);
    if ( v36 )
      RefsForEachVcb(v18, 0, (unsigned int)RefsUpdateContainerMoveEventThresholdsVolumeSetting, 0, 0);
    if ( v37 )
      RefsForEachVcb(v18, 0, (unsigned int)RefsUpdateCheckpointSampleIntervalVolumeSetting, 0, 1);
    if ( v38 )
      RefsForEachVcb(v18, 0, (unsigned int)RefsUpdateBlockRefcountSampleIntervalVolumeSetting, 0, 1);
    if ( v39 )
      RefsForEachVcb(v18, 0, (unsigned int)RefsUpdateGhostExtentsSampleIntervalVolumeSetting, 0, 1);
    if ( v40 )
      RefsForEachVcb(v18, 0, (unsigned int)RefsUpdateContainerRotationSampleIntervalVolumeSetting, 0, 1);
    if ( v41 )
      RefsForEachVcb(v18, 0, (unsigned int)RefsUpdateReadCacheSampleIntervalVolumeSetting, 0, 1);
    if ( v42 )
      RefsForEachVcb(v18, 0, (unsigned int)RefsUpdateSmrUpdateSampleIntervalVolumeSetting, 0, 1);
    if ( v43 )
      RefsForEachVcb(v18, 0, (unsigned int)RefsUpdateSmrSampleIntervalVolumeSetting, 0, 1);
    if ( v44 )
      RefsForEachVcb(v18, 0, (unsigned int)RefsUpdateLogFileFullSampleIntervalVolumeSetting, 0, 1);
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(0);
    v5 = v54;
    RefsExtendedCompleteRequestInternal(v54, 0, 0);
    v3 = v22;
  }
  while ( v22 == -1073741608 || v22 == -1073741432 );
  if ( v19[0] )
    ExFreePoolWithTag(P, 0);
  ExReleaseResourceLite(&RefsDynamicRegistrySettingsResource);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1c0175ab0  mov     r11, rsp
0x1c0175ab3  mov     [r11+10h], rbx
0x1c0175ab7  mov     [r11+18h], rsi
0x1c0175abb  mov     [r11+8], rcx
0x1c0175abf  push    rdi
0x1c0175ac0  push    r12
0x1c0175ac2  push    r13
0x1c0175ac4  push    r14
0x1c0175ac6  push    r15
0x1c0175ac8  sub     rsp, 2F0h
0x1c0175acf  mov     rax, cs:__security_cookie
0x1c0175ad6  xor     rax, rsp
0x1c0175ad9  mov     [rsp+318h+var_38], rax
0x1c0175ae1  xor     edx, edx; Val
0x1c0175ae3  mov     r8d, 100h; Size
0x1c0175ae9  lea     rcx, [r11-1D8h]; void *
0x1c0175af0  call    memset
0x1c0175af5  lea     rax, [rsp+318h+var_1D8]
0x1c0175afd  mov     [rsp+318h+var_270], rax
0x1c0175b05  xorps   xmm0, xmm0
0x1c0175b08  xor     eax, eax
0x1c0175b0a  movups  [rsp+318h+var_208], xmm0
0x1c0175b12  movups  [rsp+318h+var_1F8], xmm0
0x1c0175b1a  mov     [rsp+318h+var_1E8], rax
0x1c0175b22  xor     ebx, ebx
0x1c0175b24  mov     [rsp+318h+var_2BE], bl
0x1c0175b28  mov     [rsp+318h+var_294], ebx
0x1c0175b2f  mov     [rsp+318h+var_2A4], ebx
0x1c0175b33  movups  [rsp+318h+var_2D0], xmm0
0x1c0175b38  mov     r13d, 9Ch
0x1c0175b3e  mov     [rsp+318h+var_2E4], r13d
0x1c0175b43  lea     rax, [rsp+318h+var_D8]
0x1c0175b4b  mov     [rsp+318h+P], rax
0x1c0175b50  mov     [rsp+318h+var_2E8], bl
0x1c0175b54  mov     [rsp+318h+var_2BF], bl
0x1c0175b58  mov     [rsp+318h+var_2BD], bl
0x1c0175b5c  lea     r15d, [rbx+1]
0x1c0175b60  mov     [rsp+318h+var_278], r15d
0x1c0175b68  mov     [rsp+318h+var_230], ebx
0x1c0175b6f  mov     [rsp+318h+var_228], ebx
0x1c0175b76  mov     [rsp+318h+var_224], ebx
0x1c0175b7d  mov     [rsp+318h+var_220], ebx
0x1c0175b84  mov     [rsp+318h+var_258], ebx
0x1c0175b8b  mov     [rsp+318h+var_254], ebx
0x1c0175b92  or      r12d, 0FFFFFFFFh
0x1c0175b96  mov     [rsp+318h+var_268], r12d
0x1c0175b9e  mov     [rsp+318h+var_2B3], bl
0x1c0175ba2  mov     [rsp+318h+var_264], r12d
0x1c0175baa  mov     [rsp+318h+var_2B2], bl
0x1c0175bae  mov     [rsp+318h+var_260], r12d
0x1c0175bb6  mov     [rsp+318h+var_2B1], bl
0x1c0175bba  mov     [rsp+318h+var_25C], r12d
0x1c0175bc2  mov     [rsp+318h+var_2B0], bl
0x1c0175bc6  mov     [rsp+318h+var_288], r12d
0x1c0175bce  mov     [rsp+318h+var_2AF], bl
0x1c0175bd2  mov     [rsp+318h+var_284], r12d
0x1c0175bda  mov     [rsp+318h+var_2AE], bl
0x1c0175bde  mov     [rsp+318h+var_280], r12d
0x1c0175be6  mov     [rsp+318h+var_2AD], bl
0x1c0175bea  mov     [rsp+318h+var_27C], r12d
0x1c0175bf2  mov     [rsp+318h+var_2AC], bl
0x1c0175bf6  mov     [rsp+318h+var_2B9], bl
0x1c0175bfa  mov     [rsp+318h+var_24C], ebx
0x1c0175c01  mov     [rsp+318h+var_2B8], bl
0x1c0175c05  mov     [rsp+318h+var_248], ebx
0x1c0175c0c  mov     [rsp+318h+var_2B7], bl
0x1c0175c10  mov     [rsp+318h+var_244], ebx
0x1c0175c17  mov     [rsp+318h+var_2B6], bl
0x1c0175c1b  mov     [rsp+318h+var_240], ebx
0x1c0175c22  mov     [rsp+318h+var_2B5], bl
0x1c0175c26  mov     [rsp+318h+var_22C], ebx
0x1c0175c2d  mov     [rsp+318h+var_2B4], bl
0x1c0175c31  mov     [rsp+318h+var_250], ebx
0x1c0175c38  mov     [rsp+318h+var_2BA], bl
0x1c0175c3c  mov     [rsp+318h+var_2C0], bl
0x1c0175c40  mov     [rsp+318h+var_2BB], bl
0x1c0175c44  mov     [rsp+318h+var_238], ebx
0x1c0175c4b  mov     [rsp+318h+var_2BC], bl
0x1c0175c4f  mov     [rsp+318h+var_234], ebx
0x1c0175c56  mov     [rsp+318h+var_23C], ebx
0x1c0175c5d  xor     r8d, r8d
0x1c0175c60  xor     edx, edx
0x1c0175c62  lea     rcx, [rsp+318h+var_208]
0x1c0175c6a  call    RefsInitializeTopLevelIrp
0x1c0175c6f  mov     rsi, rax
0x1c0175c72  lea     r9, [rsp+318h+var_270]
0x1c0175c7a  xor     r8d, r8d
0x1c0175c7d  mov     dl, r15b
0x1c0175c80  xor     ecx, ecx
0x1c0175c82  call    RefsInitializeIrpContext
0x1c0175c87  mov     r14d, eax
0x1c0175c8a  test    eax, eax
0x1c0175c8c  js      loc_1C0177461
0x1c0175c92  mov     rcx, [rsi+20h]
0x1c0175c96  mov     rdi, [rsp+318h+var_270]
0x1c0175c9e  test    rcx, rcx
0x1c0175ca1  jnz     short loc_1C0175CC6
0x1c0175ca3  mov     dword ptr [rsi+4], 5346ABBAh
0x1c0175caa  mov     [rsi+20h], rdi
0x1c0175cae  bts     dword ptr [rdi+8], 14h
0x1c0175cb3  mov     rcx, rsi; Irp
0x1c0175cb6  call    cs:__imp_IoSetTopLevelIrp
0x1c0175cbd  nop     dword ptr [rax+rax+00h]
0x1c0175cc2  mov     rcx, [rsi+20h]
0x1c0175cc6  mov     [rdi+68h], rcx
0x1c0175cca  call    cs:__imp_KeEnterCriticalRegion
0x1c0175cd1  nop     dword ptr [rax+rax+00h]
0x1c0175cd6  mov     dl, r15b; Wait
0x1c0175cd9  lea     rcx, RefsDynamicRegistrySettingsResource; Resource
0x1c0175ce0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1c0175ce7  nop     dword ptr [rax+rax+00h]
0x1c0175cec  lea     rax, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x1c0175cf3  mov     [rsp+318h+var_290], rax
0x1c0175cfb  mov     [rsp+318h+var_298], 680066h
0x1c0175d06  lea     rax, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x1c0175d0d  mov     [rsp+318h+var_2A0], rax
0x1c0175d12  mov     [rsp+318h+var_2A8], 7C007Ah
0x1c0175d1a  mov     esi, 64h ; 'd'
0x1c0175d1f  cmp     r14d, 0C0000188h
0x1c0175d26  jnz     short loc_1C0175D30
0x1c0175d28  mov     rcx, rdi
0x1c0175d2b  call    RefsCheckpointForLogFileFull
0x1c0175d30  test    rdi, rdi
0x1c0175d33  jz      short loc_1C0175D3D
0x1c0175d35  mov     rcx, rdi
0x1c0175d38  call    RefsPreRequestProcessingExtend
0x1c0175d3d  mov     dl, r15b; Wait
0x1c0175d40  lea     rcx, Resource; Resource
0x1c0175d47  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1c0175d4e  nop     dword ptr [rax+rax+00h]
0x1c0175d53  mov     [rsp+318h+var_2BE], r15b
0x1c0175d58  lea     rax, aRefsdisabledel; "RefsDisableDeleteNotification"
0x1c0175d5f  mov     qword ptr [rsp+318h+var_2D0+8], rax
0x1c0175d64  mov     dword ptr [rsp+318h+var_2D0], 3C003Ah
0x1c0175d6c  lea     rax, [rsp+318h+var_2E8]
0x1c0175d71  mov     [rsp+318h+var_2F8], rax
0x1c0175d76  lea     r9, [rsp+318h+P]
0x1c0175d7b  lea     r8, [rsp+318h+var_2E4]
0x1c0175d80  lea     rdx, [rsp+318h+var_2D0]
0x1c0175d85  lea     rcx, [rsp+318h+var_298]
0x1c0175d8d  call    RefsQueryValueKey
0x1c0175d92  mov     [rsp+318h+var_2D8], eax
0x1c0175d96  test    eax, eax
0x1c0175d98  jns     short loc_1C0175DC5
0x1c0175d9a  lea     rax, [rsp+318h+var_2E8]
0x1c0175d9f  mov     [rsp+318h+var_2F8], rax
0x1c0175da4  lea     r9, [rsp+318h+P]
0x1c0175da9  lea     r8, [rsp+318h+var_2E4]
0x1c0175dae  lea     rdx, [rsp+318h+var_2D0]
0x1c0175db3  lea     rcx, [rsp+318h+var_2A8]
0x1c0175db8  call    RefsQueryValueKey
0x1c0175dbd  mov     [rsp+318h+var_2D8], eax
0x1c0175dc1  test    eax, eax
0x1c0175dc3  js      short loc_1C0175DD9
0x1c0175dc5  mov     rcx, [rsp+318h+P]
0x1c0175dca  mov     eax, [rcx+8]
0x1c0175dcd  mov     edx, [rax+rcx]
0x1c0175dd0  mov     [rsp+318h+var_21C], edx
0x1c0175dd7  jmp     short loc_1C0175DE2
0x1c0175dd9  mov     edx, ebx
0x1c0175ddb  mov     [rsp+318h+var_21C], ebx
0x1c0175de2  mov     eax, cs:dword_1C012E0B0
0x1c0175de8  cmp     edx, r15d
0x1c0175deb  jnz     short loc_1C0175DFA
0x1c0175ded  mov     ecx, 8000h
0x1c0175df2  test    ecx, eax
0x1c0175df4  jnz     short loc_1C0175E0F
0x1c0175df6  or      eax, ecx
0x1c0175df8  jmp     short loc_1C0175E04
0x1c0175dfa  bt      eax, 0Fh
0x1c0175dfe  jnb     short loc_1C0175E0F
0x1c0175e00  btr     eax, 0Fh
0x1c0175e04  mov     cs:dword_1C012E0B0, eax
0x1c0175e0a  mov     [rsp+318h+var_2BF], r15b
0x1c0175e0f  lea     rax, aEnablemetadata; "EnableMetadataPrefetch"
0x1c0175e16  mov     qword ptr [rsp+318h+var_2D0+8], rax
0x1c0175e1b  mov     dword ptr [rsp+318h+var_2D0], 2E002Ch
0x1c0175e23  lea     rax, [rsp+318h+var_2E8]
0x1c0175e28  mov     [rsp+318h+var_2F8], rax
0x1c0175e2d  lea     r9, [rsp+318h+P]
0x1c0175e32  lea     r8, [rsp+318h+var_2E4]
0x1c0175e37  lea     rdx, [rsp+318h+var_2D0]
0x1c0175e3c  lea     rcx, [rsp+318h+var_298]
0x1c0175e44  call    RefsQueryValueKey
0x1c0175e49  mov     [rsp+318h+var_2D8], eax
0x1c0175e4d  test    eax, eax
0x1c0175e4f  jns     short loc_1C0175E7C
0x1c0175e51  lea     rax, [rsp+318h+var_2E8]
0x1c0175e56  mov     [rsp+318h+var_2F8], rax
0x1c0175e5b  lea     r9, [rsp+318h+P]
0x1c0175e60  lea     r8, [rsp+318h+var_2E4]
0x1c0175e65  lea     rdx, [rsp+318h+var_2D0]
0x1c0175e6a  lea     rcx, [rsp+318h+var_2A8]
0x1c0175e6f  call    RefsQueryValueKey
0x1c0175e74  mov     [rsp+318h+var_2D8], eax
0x1c0175e78  test    eax, eax
0x1c0175e7a  js      short loc_1C0175E8E
0x1c0175e7c  mov     rcx, [rsp+318h+P]
0x1c0175e81  mov     eax, [rcx+8]
0x1c0175e84  mov     ecx, [rax+rcx]
0x1c0175e87  mov     [rsp+318h+var_278], ecx
0x1c0175e8e  mov     eax, cs:dword_1C012E0B0
0x1c0175e94  cmp     [rsp+318h+var_278], r15d
0x1c0175e9c  jnz     short loc_1C0175EAB
0x1c0175e9e  mov     ecx, 80000h
0x1c0175ea3  test    ecx, eax
0x1c0175ea5  jnz     short loc_1C0175EBB
0x1c0175ea7  or      eax, ecx
0x1c0175ea9  jmp     short loc_1C0175EB5
0x1c0175eab  bt      eax, 13h
0x1c0175eaf  jnb     short loc_1C0175EBB
0x1c0175eb1  btr     eax, 13h
0x1c0175eb5  mov     cs:dword_1C012E0B0, eax
0x1c0175ebb  lea     rax, aRefsfailincomp; "RefsFailIncompleteLogRedo"
0x1c0175ec2  mov     qword ptr [rsp+318h+var_2D0+8], rax
0x1c0175ec7  mov     dword ptr [rsp+318h+var_2D0], 340032h
0x1c0175ecf  lea     rax, [rsp+318h+var_2E8]
0x1c0175ed4  mov     [rsp+318h+var_2F8], rax
0x1c0175ed9  lea     r9, [rsp+318h+P]
0x1c0175ede  lea     r8, [rsp+318h+var_2E4]
0x1c0175ee3  lea     rdx, [rsp+318h+var_2D0]
0x1c0175ee8  lea     rcx, [rsp+318h+var_298]
0x1c0175ef0  call    RefsQueryValueKey
0x1c0175ef5  mov     [rsp+318h+var_2D8], eax
0x1c0175ef9  test    eax, eax
0x1c0175efb  jns     short loc_1C0175F28
0x1c0175efd  lea     rax, [rsp+318h+var_2E8]
0x1c0175f02  mov     [rsp+318h+var_2F8], rax
0x1c0175f07  lea     r9, [rsp+318h+P]
0x1c0175f0c  lea     r8, [rsp+318h+var_2E4]
0x1c0175f11  lea     rdx, [rsp+318h+var_2D0]
0x1c0175f16  lea     rcx, [rsp+318h+var_2A8]
0x1c0175f1b  call    RefsQueryValueKey
0x1c0175f20  mov     [rsp+318h+var_2D8], eax
0x1c0175f24  test    eax, eax
0x1c0175f26  js      short loc_1C0175F3A
0x1c0175f28  mov     rcx, [rsp+318h+P]
0x1c0175f2d  mov     eax, [rcx+8]
0x1c0175f30  mov     ecx, [rax+rcx]
0x1c0175f33  mov     [rsp+318h+var_23C], ecx
0x1c0175f3a  cmp     [rsp+318h+var_23C], r15d
0x1c0175f42  setz    cs:RefsFailIncompleteLogRedo
0x1c0175f49  lea     rax, aRefsinvalidate; "RefsInvalidateOnFileLevelTrim"
0x1c0175f50  mov     qword ptr [rsp+318h+var_2D0+8], rax
0x1c0175f55  mov     dword ptr [rsp+318h+var_2D0], 3C003Ah
0x1c0175f5d  lea     rax, [rsp+318h+var_2E8]
0x1c0175f62  mov     [rsp+318h+var_2F8], rax
0x1c0175f67  lea     r9, [rsp+318h+P]
0x1c0175f6c  lea     r8, [rsp+318h+var_2E4]
0x1c0175f71  lea     rdx, [rsp+318h+var_2D0]
0x1c0175f76  lea     rcx, [rsp+318h+var_298]
0x1c0175f7e  call    RefsQueryValueKey
0x1c0175f83  mov     [rsp+318h+var_2D8], eax
0x1c0175f87  test    eax, eax
0x1c0175f89  js      short loc_1C0175F92
0x1c0175f8b  mov     rdx, [rsp+318h+P]
0x1c0175f90  jmp     short loc_1C0175FC2
0x1c0175f92  lea     rax, [rsp+318h+var_2E8]
0x1c0175f97  mov     [rsp+318h+var_2F8], rax
0x1c0175f9c  lea     r9, [rsp+318h+P]
0x1c0175fa1  lea     r8, [rsp+318h+var_2E4]
0x1c0175fa6  lea     rdx, [rsp+318h+var_2D0]
0x1c0175fab  lea     rcx, [rsp+318h+var_2A8]
0x1c0175fb0  call    RefsQueryValueKey
0x1c0175fb5  mov     [rsp+318h+var_2D8], eax
0x1c0175fb9  mov     rdx, [rsp+318h+P]
0x1c0175fbe  test    eax, eax
0x1c0175fc0  js      short loc_1C0175FD1
0x1c0175fc2  mov     eax, [rdx+8]
0x1c0175fc5  mov     ecx, [rax+rdx]
0x1c0175fc8  mov     [rsp+318h+var_218], ecx
0x1c0175fcf  jmp     short loc_1C0175FDA
0x1c0175fd1  mov     ecx, ebx
0x1c0175fd3  mov     [rsp+318h+var_218], ebx
0x1c0175fda  cmp     ecx, 3
0x1c0175fdd  sbb     r8d, r8d
0x1c0175fe0  and     r8d, ecx
0x1c0175fe3  cmp     cs:dword_1C012DED4, r8d
0x1c0175fea  jz      short loc_1C0175FF8
0x1c0175fec  mov     cs:dword_1C012DED4, r8d
0x1c0175ff3  mov     [rsp+318h+var_2BD], r15b
0x1c0175ff8  test    rdx, rdx
0x1c0175ffb  jnz     short loc_1C0176013
0x1c0175ffd  mov     [rsp+318h+var_2E8], bl
0x1c0176001  mov     [rsp+318h+var_2E4], r13d
0x1c0176006  lea     rax, [rsp+318h+var_D8]
0x1c017600e  mov     [rsp+318h+P], rax
0x1c0176013  lea     rax, aEnableextraioa; "EnableExtraIoAnalysis"
0x1c017601a  mov     qword ptr [rsp+318h+var_2D0+8], rax
0x1c017601f  mov     dword ptr [rsp+318h+var_2D0], 2C002Ah
0x1c0176027  lea     rax, [rsp+318h+var_2E8]
0x1c017602c  mov     [rsp+318h+var_2F8], rax
0x1c0176031  lea     r9, [rsp+318h+P]
0x1c0176036  lea     r8, [rsp+318h+var_2E4]
0x1c017603b  lea     rdx, [rsp+318h+var_2D0]
0x1c0176040  lea     rcx, [rsp+318h+var_298]
0x1c0176048  call    RefsQueryValueKey
0x1c017604d  mov     [rsp+318h+var_2D8], eax
0x1c0176051  test    eax, eax
0x1c0176053  jns     short loc_1C0176080
  ... truncated ...
```
