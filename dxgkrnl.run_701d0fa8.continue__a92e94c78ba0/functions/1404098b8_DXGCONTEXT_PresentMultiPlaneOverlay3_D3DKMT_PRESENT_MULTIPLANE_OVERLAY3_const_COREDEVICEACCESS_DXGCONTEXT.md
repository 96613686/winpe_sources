# DXGCONTEXT::PresentMultiPlaneOverlay3(_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 const *,COREDEVICEACCESS *,DXGCONTEXT * *)

- ea: `0x1404098b8`
- end: `0x14040bd3a`
- name: `?PresentMultiPlaneOverlay3@DXGCONTEXT@@QEAAJPEBU_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3@@PEAVCOREDEVICEACCESS@@PEAPEAV1@@Z`
- size: `9346`
- prototype: `__int64 __fastcall(DXGCONTEXT *__hidden this, const struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *, struct COREDEVICEACCESS *, struct DXGCONTEXT **)`
- caller_count: `3`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140247f6c`
- `0x1402482d0`
- `0x14040bd40`

## callees

- `0x140012540`
- `0x140015f7c`
- `0x14001a970`
- `0x14001b9c0`
- `0x14001d1a0`
- `0x14001dee4`
- `0x14001f2f0`
- `0x14002dbc0`
- `0x14002dc10`
- `0x140034910`
- `0x14003940c`
- `0x140042b34`
- `0x140049424`
- `0x14004d4a4`
- `0x14004e700`
- `0x140057ac8`
- `0x14006210c`
- `0x140079454`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x140247c84`
- `0x140247f40`
- `0x140318248`
- `0x14032e900`
- `0x14032e980`
- `0x14032eb9c`
- `0x14032f080`
- `0x14032fd70`
- `0x14037e3f0`
- `0x14037ecf0`
- `0x140384d48`
- `0x1403929a0`
- `0x140393f58`
- `0x1403b4724`
- `0x1403bf5bc`
- `0x1403cb11c`
- `0x1403d056c`
- `0x1403f1668`
- `0x1403ffc70`
- `0x1404098b8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140409cc5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14040a4aa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140409cc5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14040a4aa`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140409cb9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14040a49e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140409cb9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14040a49e`
- `watchdog!WdLogSingleEntry4` at `0x14040a61c`
- `watchdog!WdLogSingleEntry4` at `0x14040a847`
- `watchdog!WdLogSingleEntry4` at `0x14040ab64`
- `watchdog!WdLogSingleEntry4` at `0x14040b26c`
- `watchdog!WdLogSingleEntry4` at `0x14040a61c`
- `watchdog!WdLogSingleEntry4` at `0x14040a847`
- `watchdog!WdLogSingleEntry4` at `0x14040ab64`
- `watchdog!WdLogSingleEntry4` at `0x14040b26c`
- `watchdog!WdLogSingleEntry2` at `0x140409b03`
- `watchdog!WdLogSingleEntry2` at `0x14040a1ac`
- `watchdog!WdLogSingleEntry2` at `0x14040a1d9`
- `watchdog!WdLogSingleEntry2` at `0x14040a206`
- `watchdog!WdLogSingleEntry2` at `0x14040a233`
- `watchdog!WdLogSingleEntry2` at `0x14040afea`
- `watchdog!WdLogSingleEntry2` at `0x14040b3a4`
- `watchdog!WdLogSingleEntry2` at `0x14040b8c8`
- `watchdog!WdLogSingleEntry2` at `0x14040b909`
- `watchdog!WdLogSingleEntry2` at `0x14040bcb3`
- `watchdog!WdLogSingleEntry2` at `0x140409b03`
- `watchdog!WdLogSingleEntry2` at `0x14040a1ac`
- `watchdog!WdLogSingleEntry2` at `0x14040a1d9`
- `watchdog!WdLogSingleEntry2` at `0x14040a206`
- `watchdog!WdLogSingleEntry2` at `0x14040a233`
- `watchdog!WdLogSingleEntry2` at `0x14040afea`
- `watchdog!WdLogSingleEntry2` at `0x14040b3a4`
- `watchdog!WdLogSingleEntry2` at `0x14040b8c8`
- `watchdog!WdLogSingleEntry2` at `0x14040b909`
- `watchdog!WdLogSingleEntry2` at `0x14040bcb3`
- `watchdog!WdLogSingleEntry3` at `0x140409a18`
- `watchdog!WdLogSingleEntry3` at `0x140409a70`
- `watchdog!WdLogSingleEntry3` at `0x140409ab3`
- `watchdog!WdLogSingleEntry3` at `0x140409d06`
- `watchdog!WdLogSingleEntry3` at `0x140409f9f`
- `watchdog!WdLogSingleEntry3` at `0x14040a02b`
- `watchdog!WdLogSingleEntry3` at `0x14040a063`
- `watchdog!WdLogSingleEntry3` at `0x14040a283`
- `watchdog!WdLogSingleEntry3` at `0x14040a2eb`
- `watchdog!WdLogSingleEntry3` at `0x14040ad90`
- `watchdog!WdLogSingleEntry3` at `0x14040ae06`
- `watchdog!WdLogSingleEntry3` at `0x14040ae36`
- `watchdog!WdLogSingleEntry3` at `0x14040aeb7`
- `watchdog!WdLogSingleEntry3` at `0x14040aefb`
- `watchdog!WdLogSingleEntry3` at `0x14040af2e`
- `watchdog!WdLogSingleEntry3` at `0x14040af68`
- `watchdog!WdLogSingleEntry3` at `0x14040af98`
- `watchdog!WdLogSingleEntry3` at `0x14040b035`
- `watchdog!WdLogSingleEntry3` at `0x14040b0c8`
- `watchdog!WdLogSingleEntry3` at `0x14040b15b`
- `watchdog!WdLogSingleEntry3` at `0x14040b19f`
- `watchdog!WdLogSingleEntry3` at `0x14040b1e3`
- `watchdog!WdLogSingleEntry3` at `0x14040b227`
- `watchdog!WdLogSingleEntry3` at `0x14040b2c9`
- `watchdog!WdLogSingleEntry3` at `0x14040b2f9`
- `watchdog!WdLogSingleEntry3` at `0x14040b329`
- `watchdog!WdLogSingleEntry3` at `0x140409a18`
- `watchdog!WdLogSingleEntry3` at `0x140409a70`
- `watchdog!WdLogSingleEntry3` at `0x140409ab3`
- `watchdog!WdLogSingleEntry3` at `0x140409d06`
- `watchdog!WdLogSingleEntry3` at `0x140409f9f`
- `watchdog!WdLogSingleEntry3` at `0x14040a02b`
- `watchdog!WdLogSingleEntry3` at `0x14040a063`
- `watchdog!WdLogSingleEntry3` at `0x14040a283`
- `watchdog!WdLogSingleEntry3` at `0x14040a2eb`
- `watchdog!WdLogSingleEntry3` at `0x14040ad90`
- `watchdog!WdLogSingleEntry3` at `0x14040ae06`
- `watchdog!WdLogSingleEntry3` at `0x14040ae36`
- `watchdog!WdLogSingleEntry3` at `0x14040aeb7`
- `watchdog!WdLogSingleEntry3` at `0x14040aefb`
- `watchdog!WdLogSingleEntry3` at `0x14040af2e`
- `watchdog!WdLogSingleEntry3` at `0x14040af68`
- `watchdog!WdLogSingleEntry3` at `0x14040af98`
- `watchdog!WdLogSingleEntry3` at `0x14040b035`
- `watchdog!WdLogSingleEntry3` at `0x14040b0c8`
- `watchdog!WdLogSingleEntry3` at `0x14040b15b`
- `watchdog!WdLogSingleEntry3` at `0x14040b19f`
- `watchdog!WdLogSingleEntry3` at `0x14040b1e3`
- `watchdog!WdLogSingleEntry3` at `0x14040b227`
- `watchdog!WdLogSingleEntry3` at `0x14040b2c9`
- `watchdog!WdLogSingleEntry3` at `0x14040b2f9`
- `watchdog!WdLogSingleEntry3` at `0x14040b329`
- `watchdog!WdLogSingleEntry0` at `0x14040992f`
- `watchdog!WdLogSingleEntry0` at `0x140409994`
- `watchdog!WdLogSingleEntry0` at `0x140409b57`
- `watchdog!WdLogSingleEntry0` at `0x140409baa`
- `watchdog!WdLogSingleEntry0` at `0x140409c44`
- `watchdog!WdLogSingleEntry0` at `0x140409d6d`
- `watchdog!WdLogSingleEntry0` at `0x140409ddf`
- `watchdog!WdLogSingleEntry0` at `0x140409e07`
- `watchdog!WdLogSingleEntry0` at `0x140409e8d`
- `watchdog!WdLogSingleEntry0` at `0x14040a432`
- `watchdog!WdLogSingleEntry0` at `0x14040b371`
- `watchdog!WdLogSingleEntry0` at `0x14040b426`
- `watchdog!WdLogSingleEntry0` at `0x14040b5f4`
- `watchdog!WdLogSingleEntry0` at `0x14040b6ad`
- `watchdog!WdLogSingleEntry0` at `0x14040b705`
- `watchdog!WdLogSingleEntry0` at `0x14040b981`
- `watchdog!WdLogSingleEntry0` at `0x14040ba4d`
- `watchdog!WdLogSingleEntry0` at `0x14040bb09`
- `watchdog!WdLogSingleEntry0` at `0x14040bbfa`
- `watchdog!WdLogSingleEntry0` at `0x14040bc4f`
- `watchdog!WdLogSingleEntry0` at `0x14040992f`
- `watchdog!WdLogSingleEntry0` at `0x140409994`
- `watchdog!WdLogSingleEntry0` at `0x140409b57`
- `watchdog!WdLogSingleEntry0` at `0x140409baa`
- `watchdog!WdLogSingleEntry0` at `0x140409c44`
- `watchdog!WdLogSingleEntry0` at `0x140409d6d`
- `watchdog!WdLogSingleEntry0` at `0x140409ddf`
- `watchdog!WdLogSingleEntry0` at `0x140409e07`
- `watchdog!WdLogSingleEntry0` at `0x140409e8d`
- `watchdog!WdLogSingleEntry0` at `0x14040a432`
- `watchdog!WdLogSingleEntry0` at `0x14040b371`
- `watchdog!WdLogSingleEntry0` at `0x14040b426`
- `watchdog!WdLogSingleEntry0` at `0x14040b5f4`
- `watchdog!WdLogSingleEntry0` at `0x14040b6ad`
- `watchdog!WdLogSingleEntry0` at `0x14040b705`
- `watchdog!WdLogSingleEntry0` at `0x14040b981`
- `watchdog!WdLogSingleEntry0` at `0x14040ba4d`
- `watchdog!WdLogSingleEntry0` at `0x14040bb09`
- `watchdog!WdLogSingleEntry0` at `0x14040bbfa`
- `watchdog!WdLogSingleEntry0` at `0x14040bc4f`
- `watchdog!WdLogSingleEntry5` at `0x14040a686`
- `watchdog!WdLogSingleEntry5` at `0x14040ae7f`
- `watchdog!WdLogSingleEntry5` at `0x14040a686`
- `watchdog!WdLogSingleEntry5` at `0x14040ae7f`
- `watchdog!WdLogSingleEntry1` at `0x14040b7f0`
- `watchdog!WdLogSingleEntry1` at `0x14040b818`
- `watchdog!WdLogSingleEntry1` at `0x14040b862`
- `watchdog!WdLogSingleEntry1` at `0x14040b7f0`
- `watchdog!WdLogSingleEntry1` at `0x14040b818`
- `watchdog!WdLogSingleEntry1` at `0x14040b862`

## string_xrefs

- `0x14040b046`: `ret = 0x%I64x Context 0x%I64x Clip rect is outside of destination rect, index 0x%I64x`
- `0x14040b1fe`: `ret = 0x%I64x Context 0x%I64x Source rect is outside of allocation rect, index 0x%I64x`
- `0x140409bbb`: `FlipStereoTemporaryMono cannot be used with FlipStereoPreferRight. STATUS_INVALID_PARAMETER`
- `0x140409b68`: `FlipStereoTemporaryMono and FlipStereo cannot be set together. STATUS_INVALID_PARAMETER`
- `0x140409d7e`: `FlipStereoTemporaryMono and FlipStereo can only be used with stereo primary allocations. STATUS_INVALID_PARAMETER`
- `0x140409e18`: `FlipStereoTemporaryMono flag is set but the current display mode does not support it. STATUS_GRAPHICS_PRESENT_MODE_CHANGED`
- `0x14040b11f`: `ClipRect outside VirtualModeRect`
- `0x14040b0d9`: `ret = 0x%I64x Context 0x%I64x Clip rect is outside of virtual mode rect, index 0x%I64x`
- `0x14040b090`: `ClipRect outside DestRect`
- `0x14040aec8`: `ret = 0x%I64x Context 0x%I64x Dest rect is outside of screen rect, index 0x%I64x`
- `0x14040bc0b`: `GetRenderCore()->IsCoreResourceSharedOwner() || Status == STATUS_DEVICE_REMOVED`

## pseudocode

```c
__int64 __fastcall DXGCONTEXT::PresentMultiPlaneOverlay3(
        DXGCONTEXT *this,
        const struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *a2,
        struct COREDEVICEACCESS *a3,
        struct DXGCONTEXT **a4)
{
  __int64 v5; // rcx
  __int64 v7; // rax
  ADAPTER_RENDER *v8; // rcx
  int v9; // ebx
  char v10; // r12
  __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // esi
  UINT PresentPlaneCount; // eax
  __int64 v15; // r8
  __int64 LayerIndex; // rsi
  __int64 VidPnSourceId; // r13
  int v19; // eax
  unsigned int v20; // ebx
  struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY_FLAGS::$0C0DBF3D833AEF0C1CBA798B5E28D5B2::$8C6F21D9FE8836A187EDBDD85607E321 Value; // eax
  __int64 v22; // rax
  const wchar_t *v23; // r9
  __int64 v24; // r12
  __int64 v25; // rsi
  D3DKMT_MULTIPLANE_OVERLAY3 *v26; // r13
  D3DKMT_HANDLE v27; // ebx
  unsigned int v28; // eax
  __int64 v29; // r8
  int v30; // ecx
  struct DXGALLOCATION *v31; // rdx
  int v32; // ecx
  __int64 v33; // rax
  const wchar_t *v34; // r9
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rcx
  ADAPTER_RENDER *v38; // rcx
  const struct _DXGK_DISPLAYMODE_INFO *DisplayModeInfo; // rax
  __int64 v40; // rbx
  const wchar_t *v41; // r9
  D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION *pPostComposition; // rcx
  LONG v43; // r8d
  LONG v44; // r10d
  LONG right; // r11d
  LONG top; // esi
  LONG bottom; // ebx
  LONG v48; // r9d
  int v49; // edx
  LONG v50; // eax
  __int64 v51; // rax
  int v52; // ebx
  int v53; // esi
  __int64 v54; // rcx
  __int64 v55; // rax
  UINT v56; // eax
  D3DKMT_MULTIPLANE_OVERLAY3 *v57; // rax
  UINT v58; // eax
  unsigned int v59; // edx
  D3DKMT_MULTIPLANE_OVERLAY3 *v60; // r13
  __int64 v61; // r12
  struct DXGALLOCATIONREFERENCE *v62; // r9
  UINT v63; // ebx
  __int64 v64; // r13
  D3DKMT_HANDLE v65; // esi
  unsigned int v66; // eax
  __int64 v67; // r8
  int v68; // ecx
  struct DXGALLOCATION *v69; // rdx
  __int64 v70; // r8
  unsigned __int8 v71; // r8
  __int64 v72; // r11
  const struct DXGALLOCATION *v73; // rdx
  int v74; // ecx
  __int64 v75; // rcx
  int v76; // eax
  __int64 v77; // rcx
  int v78; // eax
  int v79; // eax
  const D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *pPlaneAttributes; // rbx
  int v81; // r8d
  int v82; // edx
  int v83; // ecx
  int v84; // eax
  LONG v85; // ecx
  LONG v86; // eax
  LONG v87; // edx
  LONG v88; // r9d
  LONG v89; // r8d
  LONG v90; // r10d
  LONG v91; // r11d
  LONG v92; // esi
  __int64 Rotation; // rcx
  UINT DirtyRectCount; // r12d
  char v95; // r9
  int v96; // esi
  RECT *pDirtyRects; // rax
  int v98; // r11d
  int *p_left; // rdx
  const D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *v100; // rdx
  int v101; // r10d
  int v102; // r8d
  int v103; // eax
  int v104; // ecx
  LONG v105; // edx
  LONG v106; // r9d
  LONG v107; // r11d
  LONG v108; // esi
  int v109; // edx
  int v110; // r10d
  int v111; // r8d
  LONG v112; // eax
  LONG v113; // ecx
  LONG v114; // edx
  LONG v115; // r8d
  const D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *v116; // rax
  __int64 v117; // rdi
  __int64 v118; // rbx
  _QWORD *v119; // rbx
  D3DDDI_FLIPINTERVAL_TYPE FlipInterval; // ecx
  const D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *v121; // rbx
  D3DKMT_MULTIPLANE_OVERLAY3 *v122; // rcx
  D3DDDI_HDR_METADATA_TYPE v123; // r12d
  D3DKMT_MULTIPLANE_OVERLAY_BLEND Blend; // r9d
  D3DDDI_ROTATION v125; // r10d
  UINT Flags; // r11d
  UINT SDRWhiteLevel; // esi
  unsigned int v128; // r8d
  D3DDDI_COLOR_SPACE_TYPE ColorSpace; // r13d
  unsigned int v130; // eax
  unsigned int v131; // edx
  __int64 v132; // r9
  const D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *v133; // r9
  const D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *v134; // rax
  LONG v135; // edi
  LONG v136; // ebx
  __int64 v137; // rcx
  D3DDDI_FLIPINTERVAL_TYPE v138; // r15d
  __int64 v139; // rdx
  int v140; // ecx
  struct VIDSCH_SUBMIT_DATA_BASE *v141; // rbx
  int v142; // ecx
  bool v143; // zf
  int v144; // ecx
  int v145; // eax
  int v146; // ecx
  UINT v147; // eax
  UINT v148; // ecx
  UINT v149; // eax
  UINT v150; // ecx
  UINT Duration; // eax
  D3DKMT_HANDLE hAdapter; // eax
  struct DXGGLOBAL *Global; // rax
  __int64 v154; // rdx
  unsigned __int8 IsHdrEnabled; // al
  int v156; // edx
  UINT v157; // ecx
  D3DDDI_HDR_METADATA_TYPE HDRMetaDataType; // edx
  __int32 v159; // edx
  _OWORD *pHDRMetaData; // rax
  _OWORD *v161; // rax
  __int64 v162; // rdx
  __int64 v163; // rcx
  int v164; // eax
  int v165; // eax
  int v166; // r15d
  const char *v167; // rdx
  int v168; // eax
  int v169; // eax
  unsigned int v170; // r9d
  unsigned int v171; // r8d
  unsigned __int8 v172; // dl
  struct ADAPTER_DISPLAY *v173; // rax
  D3DKMT_MULTIPLANE_OVERLAY3 **ppPresentPlanes; // rax
  const struct _D3DKMT_MULTIPLANE_OVERLAY3 *v175; // rbx
  __int64 v176; // [rsp+30h] [rbp-120h]
  __int64 v177; // [rsp+38h] [rbp-118h]
  __int64 v178; // [rsp+40h] [rbp-110h]
  int v179; // [rsp+B0h] [rbp-A0h]
  char v180; // [rsp+B8h] [rbp-98h]
  char v181; // [rsp+D0h] [rbp-80h]
  unsigned __int8 v182; // [rsp+D1h] [rbp-7Fh]
  unsigned __int8 v183; // [rsp+D2h] [rbp-7Eh]
  char v184; // [rsp+D3h] [rbp-7Dh]
  char v185; // [rsp+D4h] [rbp-7Ch]
  UINT v186; // [rsp+D8h] [rbp-78h]
  bool v187; // [rsp+DCh] [rbp-74h]
  D3DKMT_MULTIPLANE_OVERLAY3 *v188; // [rsp+E0h] [rbp-70h] BYREF
  D3DDDI_VIDEO_PRESENT_SOURCE_ID v189; // [rsp+E8h] [rbp-68h]
  unsigned int v190; // [rsp+ECh] [rbp-64h]
  unsigned int v191; // [rsp+F0h] [rbp-60h]
  LONG left; // [rsp+F4h] [rbp-5Ch]
  LONG v193; // [rsp+F8h] [rbp-58h]
  LONG v194; // [rsp+FCh] [rbp-54h]
  int v195; // [rsp+100h] [rbp-50h]
  int v196; // [rsp+104h] [rbp-4Ch]
  LONG v197; // [rsp+108h] [rbp-48h]
  int v198; // [rsp+10Ch] [rbp-44h]
  unsigned int v199; // [rsp+110h] [rbp-40h]
  int v200; // [rsp+114h] [rbp-3Ch]
  int v201; // [rsp+118h] [rbp-38h]
  int v202; // [rsp+11Ch] [rbp-34h]
  __int64 v203; // [rsp+120h] [rbp-30h]
  char *v204; // [rsp+128h] [rbp-28h]
  struct VIDSCH_SUBMIT_DATA_BASE *v205[2]; // [rsp+130h] [rbp-20h] BYREF
  int v206; // [rsp+140h] [rbp-10h] BYREF
  COREDEVICEACCESS *v207; // [rsp+148h] [rbp-8h]
  int v208; // [rsp+150h] [rbp+0h]
  int v209; // [rsp+154h] [rbp+4h]
  int v210; // [rsp+158h] [rbp+8h]
  char v211[8]; // [rsp+160h] [rbp+10h] BYREF
  char v212[8]; // [rsp+168h] [rbp+18h] BYREF
  struct DXGCONTEXT **v213; // [rsp+170h] [rbp+20h]
  struct _D3DKMT_PRESENT_RGNS v214; // [rsp+178h] [rbp+28h] BYREF
  struct _DXGKARG_DESCRIBEALLOCATION v215; // [rsp+198h] [rbp+48h] BYREF
  struct DXGALLOCATIONREFERENCE *v216[5]; // [rsp+1C8h] [rbp+78h] BYREF
  int v217; // [rsp+1F0h] [rbp+A0h]
  struct _DXGKARG_PRESENT v218; // [rsp+200h] [rbp+B0h] BYREF
  _D3DKMT_PRESENT v219; // [rsp+2B0h] [rbp+160h] BYREF
  enum _D3DDDIFORMAT v220[4]; // [rsp+890h] [rbp+740h] BYREF
  __int128 v221; // [rsp+8A0h] [rbp+750h]
  __int64 v222; // [rsp+8B0h] [rbp+760h]
  unsigned __int8 v223[16]; // [rsp+8B8h] [rbp+768h] BYREF

  v213 = a4;
  v5 = *((_QWORD *)this + 2);
  v207 = a3;
  v7 = *(_QWORD *)(v5 + 1896);
  v8 = *(ADAPTER_RENDER **)(v5 + 16);
  v9 = *(_DWORD *)(v7 + 444) & 0x100;
  v210 = v9;
  v10 = 0;
  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(v8) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 3258;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner()",
      3258,
      0,
      0,
      0,
      0);
  }
  v11 = *((_QWORD *)this + 2);
  v12 = *(_QWORD *)(*(_QWORD *)(v11 + 16) + 16LL);
  if ( (v12 || !v9) && *(_QWORD *)(v11 + 1896) != v12 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 3259;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"(!GetRenderAdapter() && IsIndirectDisplayDevice) || (GetDisplayAdapter() == GetRenderAdapter())",
      3259,
      0,
      0,
      0,
      0);
  }
  *((_BYTE *)this + 435) = 1;
  if ( v9 )
    v13 = 1;
  else
    v13 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 16LL) + 3072LL);
  PresentPlaneCount = a2->PresentPlaneCount;
  v190 = v13;
  if ( PresentPlaneCount > v13 )
  {
    v15 = v13;
    LODWORD(LayerIndex) = -1073741811;
    WdLogSingleEntry3(3, PresentPlaneCount, v15, -1073741811);
    WdLogGlobalForLineNumber = 3276;
    return (unsigned int)LayerIndex;
  }
  VidPnSourceId = a2->VidPnSourceId;
  v189 = a2->VidPnSourceId;
  if ( !v9 )
  {
    v19 = DXGCONTEXT::CheckDevicePresentSettings(this, 1, 0, 1, VidPnSourceId);
    v20 = v19;
    if ( v19 < 0 )
    {
      WdLogSingleEntry3(3, v19, this, (unsigned int)VidPnSourceId);
      WdLogGlobalForLineNumber = 3295;
      return v20;
    }
    if ( (*(_DWORD *)(*((_QWORD *)this + 2) + 4 * VidPnSourceId + 1240) & 0x200) == 0 )
    {
      v20 = -1071775719;
      WdLogSingleEntry3(3, -1071775719, this, (unsigned int)VidPnSourceId);
      WdLogGlobalForLineNumber = 3304;
      return v20;
    }
  }
  Value = (struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY_FLAGS::$0C0DBF3D833AEF0C1CBA798B5E28D5B2::$8C6F21D9FE8836A187EDBDD85607E321)a2->Flags.Value;
  if ( (*(_BYTE *)&Value & 2) == 0 && (*(_BYTE *)&Value & 1) == 0 )
    goto LABEL_50;
  if ( a2->PresentPlaneCount > 1 )
  {
    LODWORD(LayerIndex) = -1073741811;
    WdLogSingleEntry2(2, this, -1073741811);
    WdLogGlobalForLineNumber = 3319;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"DxgkPresentMultiPlaneOverlay doesn't support Stereo on more than 1 plane. Context 0x%I64x, Returning 0x%I64x",
      (__int64)this,
      -1073741811,
      0,
      0,
      0);
    return (unsigned int)LayerIndex;
  }
  if ( (a2->Flags.Value & 2) != 0 && (*(_BYTE *)&Value & 1) != 0 )
  {
    WdLogSingleEntry0(2);
    v22 = 3326;
    v23 = L"FlipStereoTemporaryMono and FlipStereo cannot be set together. STATUS_INVALID_PARAMETER";
LABEL_26:
    WdLogGlobalForLineNumber = v22;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v23, v22, 0, 0, 0, 0);
    return -1073741811;
  }
  if ( (*(_BYTE *)&Value & 6) == 6 )
  {
    WdLogSingleEntry0(2);
    v22 = 3332;
    v23 = L"FlipStereoTemporaryMono cannot be used with FlipStereoPreferRight. STATUS_INVALID_PARAMETER";
    goto LABEL_26;
  }
  DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v188, 0);
  v24 = *(_QWORD *)(*((_QWORD *)this + 2) + 40LL);
  v25 = v24 + 248;
  v26 = *a2->ppPresentPlanes;
  v27 = *v26->pAllocationList;
  DXGPUSHLOCK::AcquireShared((DXGPUSHLOCK *)(v24 + 248));
  v28 = (v27 >> 6) & 0xFFFFFF;
  if ( v28 >= *(_DWORD *)(v24 + 296)
    || (v29 = *(_QWORD *)(v24 + 280), ((v27 >> 25) & 0x60) != (*(_BYTE *)(v29 + 16LL * v28 + 8) & 0x60))
    || (*(_DWORD *)(v29 + 16LL * v28 + 8) & 0x2000) != 0
    || (v30 = *(_DWORD *)(v29 + 16LL * v28 + 8) & 0x1F) == 0 )
  {
    v10 = 0;
    goto LABEL_37;
  }
  if ( v30 != 5 )
  {
    WdLogSingleEntry0(2);
    v10 = 0;
    WdLogGlobalForLineNumber = 318;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
LABEL_37:
    v31 = 0;
    goto LABEL_38;
  }
  v31 = *(struct DXGALLOCATION **)(v29 + 16LL * v28);
  v10 = 0;
LABEL_38:
  DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v206, v31);
  _InterlockedDecrement((volatile signed __int32 *)(v25 + 16));
  ExReleasePushLockSharedEx(v25, 0);
  KeLeaveCriticalRegion();
  DXGALLOCATIONREFERENCE::MoveAssign(&v188, &v206);
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v206);
  if ( !v188 )
  {
    LODWORD(LayerIndex) = -1073741811;
    WdLogSingleEntry3(2, -1073741811, this, *v26->pAllocationList);
    WdLogGlobalForLineNumber = 3343;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"ret = 0x%I64x Context 0x%I64x: Invalid allocation handle for plane 0 specified: 0x%I64x",
      -1073741811,
      (__int64)this,
      *v26->pAllocationList,
      0,
      0);
LABEL_40:
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v188);
    return (unsigned int)LayerIndex;
  }
  if ( (v188->pPlaneAttributes->SrcRect.left & 0x1000) == 0 )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 3350;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"FlipStereoTemporaryMono and FlipStereo can only be used with stereo primary allocations. STATUS_INVALID_PARAMETER",
      3350,
      0,
      0,
      0,
      0);
    LODWORD(LayerIndex) = -1073741811;
    goto LABEL_40;
  }
  v32 = *((_DWORD *)ADAPTER_DISPLAY::GetDisplayModeInfo(
                      *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) + 3248LL),
                      a2->VidPnSourceId)
        + 10);
  if ( (v32 & 0x10) == 0 )
  {
    WdLogSingleEntry0(2);
    v33 = 3357;
    v34 = L"Stereo flag is set but the current display mode does not support stereo. STATUS_GRAPHICS_PRESENT_MODE_CHANGED";
LABEL_48:
    WdLogGlobalForLineNumber = v33;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v34, v33, 0, 0, 0, 0);
    LODWORD(LayerIndex) = -1071775739;
    goto LABEL_40;
  }
  if ( (a2->Flags.Value & 2) != 0 && (v32 & 0x20) == 0 )
  {
    WdLogSingleEntry0(2);
    v33 = 3363;
    v34 = L"FlipStereoTemporaryMono flag is set but the current display mode does not support it. STATUS_GRAPHICS_PRESENT_MODE_CHANGED";
    goto LABEL_48;
  }
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v188);
  LODWORD(VidPnSourceId) = v189;
  v13 = v190;
LABEL_50:
  v216[0] = 0;
  v35 = a2->ContextCount * v13;
  v217 = 0;
  PagedPoolArray<DXGALLOCATIONREFERENCE,4>::AllocateElements(v216, v35);
  if ( !v216[0] )
  {
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 3375;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to allocate memory for MPO allocation references",
      3375,
      0,
      0,
      0,
      0);
LABEL_264:
    LODWORD(LayerIndex) = -1073741801;
    goto LABEL_309;
  }
  DXGDEVICE::GetDisplayedAllMultiPlaneOverlays(*((DXGDEVICE **)this + 2), VidPnSourceId, v216[0], v13);
  v36 = *((_QWORD *)this + 2);
  v205[0] = *(struct VIDSCH_SUBMIT_DATA_BASE **)v216[0];
  ADAPTER_DISPLAY::GetDDIEnabledPlanes(*(ADAPTER_DISPLAY **)(*(_QWORD *)(v36 + 1896) + 3248LL), VidPnSourceId, v223);
  v37 = *((_QWORD *)this + 2);
  *(_OWORD *)v220 = 0;
  v222 = 0;
  v38 = *(ADAPTER_RENDER **)(v37 + 16);
  v221 = 0;
  if ( !ADAPTER_RENDER::IsMultiPlaneOverlaySupported(v38)
    || *(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) != *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 16LL) )
  {
    v10 = 1;
  }
  v184 = v10;
  DisplayModeInfo = ADAPTER_DISPLAY::GetDisplayModeInfo(
                      *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) + 3248LL),
                      VidPnSourceId);
  if ( !DisplayModeInfo )
  {
    LayerIndex = -1073741811;
    v40 = (unsigned int)VidPnSourceId;
    WdLogSingleEntry3(2, -1073741811, this, (unsigned int)VidPnSourceId);
    v41 = L"ret = 0x%I64x Context 0x%I64x Failed to obtain display mode, VidPnSourceId 0x%I64x";
    WdLogGlobalForLineNumber = 3404;
    goto LABEL_57;
  }
  pPostComposition = a2->pPostComposition;
  v43 = *(_DWORD *)DisplayModeInfo;
  v44 = *((_DWORD *)DisplayModeInfo + 1);
  v185 = 0;
  v199 = 0;
  v198 = 0;
  if ( pPostComposition )
  {
    if ( pPostComposition->Flags.Value )
    {
      LODWORD(LayerIndex) = -1073741811;
      WdLogSingleEntry3(3, this, pPostComposition->Flags.Value, -1073741811);
      WdLogGlobalForLineNumber = 3419;
      goto LABEL_309;
    }
    if ( pPostComposition->Rotation != D3DDDI_ROTATION_IDENTITY )
    {
      LODWORD(LayerIndex) = -1073741811;
      WdLogSingleEntry3(3, this, pPostComposition->Rotation, -1073741811);
      WdLogGlobalForLineNumber = 3425;
      goto LABEL_309;
    }
    right = pPostComposition->SrcRect.right;
    left = pPostComposition->SrcRect.left;
    v193 = right;
    if ( left >= right
      || (top = pPostComposition->SrcRect.top,
          bottom = pPostComposition->SrcRect.bottom,
          v197 = top,
          v194 = bottom,
          top >= bottom) )
    {
      LODWORD(LayerIndex) = -1073741811;
      WdLogSingleEntry2(3, this, -1073741811);
      WdLogGlobalForLineNumber = 3431;
      goto LABEL_309;
    }
    v48 = pPostComposition->DstRect.right;
    v49 = pPostComposition->DstRect.left;
    if ( v49 >= v48 || (v50 = pPostComposition->DstRect.bottom, pPostComposition->DstRect.top >= v50) )
    {
      LODWORD(LayerIndex) = -1073741811;
      WdLogSingleEntry2(3, this, -1073741811);
      WdLogGlobalForLineNumber = 3437;
      goto LABEL_309;
    }
    if ( v49 < 0 || v43 < v48 || pPostComposition->DstRect.top < 0 || v44 < v50 )
    {
      LODWORD(LayerIndex) = -1073741811;
      WdLogSingleEntry2(3, this, -1073741811);
      WdLogGlobalForLineNumber = 3443;
      goto LABEL_309;
    }
    if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 16LL) + 3177LL) || v10 )
    {
      LODWORD(LayerIndex) = -1073741811;
      WdLogSingleEntry2(3, -1073741811, this);
      WdLogGlobalForLineNumber = 3454;
      goto LABEL_309;
    }
    if ( left || right != v43 || top || bottom != v44 )
    {
      v185 = 1;
      v199 = right - left;
      v198 = bottom - top;
    }
  }
  else
  {
    left = 0;
    v197 = 0;
    v193 = v43;
    v194 = v44;
    if ( v10 )
    {
      v56 = a2->PresentPlaneCount;
      if ( v56 != 1 )
      {
        LayerIndex = -1073741811;
        WdLogSingleEntry3(2, -1073741811, this, v56);
        v178 = 0;
        v41 = L"0x%I64x Context 0x%I64x PresentMPO fails because the driver doesn't support MPO and 0x%I64x planes are specified";
        WdLogGlobalForLineNumber = 3488;
        v177 = 0;
        v176 = a2->PresentPlaneCount;
        goto LABEL_59;
      }
      v57 = *a2->ppPresentPlanes;
      if ( v57->LayerIndex || (v57->InputFlags.Value & 1) == 0 )
      {
        LayerIndex = -1073741811;
        WdLogSingleEntry3(2, -1073741811, this, 1);
        v178 = 0;
        v41 = L"0x%I64x Context 0x%I64x PresentMPO fails because the driver doesn't support MPO and plane 0 is not enabled";
        WdLogGlobalForLineNumber = 3497;
        v177 = 0;
        v176 = a2->PresentPlaneCount;
        goto LABEL_59;
      }
    }
  }
  v51 = *((_QWORD *)this + 2);
  v52 = 0;
  v201 = 0;
  v53 = 0;
  v182 = 0;
  v183 = 0;
  v54 = *(_QWORD *)(v51 + 16);
  v181 = 0;
  v196 = -1;
  LOBYTE(v195) = 0;
  v55 = *(_QWORD *)(v54 + 16);
  v202 = 0;
  v187 = *(int *)(v55 + 3132) >= 3000 || *((_BYTE *)DXGGLOBAL::GetGlobal() + 304896);
  v58 = 0;
  v186 = 0;
  if ( !a2->PresentPlaneCount )
  {
LABEL_251:
    v138 = D3DDDI_FLIPINTERVAL_ONE;
    if ( !v53 )
    {
      if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 16LL) + 3177LL) )
      {
        v138 = D3DDDI_FLIPINTERVAL_IMMEDIATE;
      }
      else
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 3986;
      }
    }
    if ( !v183 && !v182 && !v181 )
    {
      WdLogSingleEntry2(4, 0, this);
      WdLogGlobalForLineNumber = 3997;
LABEL_259:
      LODWORD(LayerIndex) = 0;
      goto LABEL_309;
    }
    memset(&v218, 0, sizeof(v218));
    v139 = *((_QWORD *)this + 2);
    v218.FlipInterval = v138;
    v140 = 4;
    if ( !v10 )
      v140 = 4100;
    v218.Flags.Value = v140
                     ^ ((unsigned __int16)v140
                      ^ (unsigned __int16)((unsigned __int16)*(_DWORD *)&a2->Flags.0 << 8))
                     & 0x700
                     | 8;
    CVidSchSubmitData::CVidSchSubmitData((CVidSchSubmitData *)v205, *(struct ADAPTER_RENDER **)(v139 + 16), 1);
    v141 = v205[0];
    if ( !v205[0] )
    {
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 4022;
      DxgkLogInternalTriageEvent(0, 262145, -1, (unsigned int)L"Failed to allocate VidSchSubmitData", 4022, 0, 0, 0, 0);
      CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v205);
      goto LABEL_264;
    }
    *(_DWORD *)v205[0] |= 0x30020u;
    v142 = *(_DWORD *)v141 | 1;
    v143 = (_BYTE)v195 == 0;
    *((_DWORD *)v141 + 28) = a2->PresentCount;
    if ( !v143 )
      v142 |= 0x400000u;
    v144 = v142 | 4;
    *(_DWORD *)v141 = v144;
    if ( !v10 && a2->ContextCount <= 1 )
    {
      v144 |= 0x800000u;
      *(_DWORD *)v141 = v144;
    }
    v145 = v144 ^ ((unsigned __int8)v144 ^ (unsigned __int8)(a2->Flags.Value >> 1)) & 8;
    *(_DWORD *)v141 = v145;
    v146 = v145 ^ ((unsigned __int8)v145 ^ (unsigned __int8)(a2->Flags.Value >> 1)) & 0x10;
    *(_DWORD *)v141 = v146;
    v147 = v146 ^ (v146 ^ (a2->Flags.Value << 19)) & 0x80000;
    *(_DWORD *)v141 = v147;
    v148 = v147 ^ (v147 ^ (a2->Flags.Value << 19)) & 0x100000;
    *(_DWORD *)v141 = v148;
    v149 = v148 ^ (v148 ^ (a2->Flags.Value << 19)) & 0x200000;
    *(_DWORD *)v141 = v149;
    v150 = v149 ^ (v149 ^ (a2->Flags.Value << 21)) & 0x20000000;
    *(_DWORD *)v141 = v150;
    if ( (a2->Flags.Value & 0x40) != 0 )
      Duration = a2->Duration;
    else
      Duration = 0;
    *((_DWORD *)v141 + 36) = Duration;
    if ( (a2->Flags.Value & 0x40) != 0 )
      hAdapter = a2[1].hAdapter;
    else
      hAdapter = 1;
    *((_DWORD *)v141 + 38) = hAdapter;
    *((_DWORD *)v141 + 29) = VidPnSourceId;
    *((_DWORD *)v141 + 31) = v138;
    *((_DWORD *)v141 + 30) = 5;
    if ( (a2->Flags.Value & 0x200) != 0 && v138 == D3DDDI_FLIPINTERVAL_IMMEDIATE )
      *(_DWORD *)v141 = v150 | 0x10000000;
    Global = DXGGLOBAL::GetGlobal();
    v154 = *((_QWORD *)this + 2);
    if ( *((_BYTE *)Global + 304896) || (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v154 + 1896) + 3248LL) + 24LL) & 0x10) != 0 )
    {
      IsHdrEnabled = ADAPTER_DISPLAY::IsHdrEnabled(
                       *(ADAPTER_DISPLAY **)(*(_QWORD *)(v154 + 1896) + 3248LL),
                       VidPnSourceId);
      v156 = *(_DWORD *)v141;
      if ( IsHdrEnabled )
      {
        v157 = v156 ^ (v156 ^ (a2->Flags.Value << 23)) & 0x40000000;
        *(_DWORD *)v141 = v157;
        *((_DWORD *)v141 + 90) = a2->HDRMetaDataType;
        HDRMetaDataType = a2->HDRMetaDataType;
        if ( (v157 & 0x40000000) != 0 )
        {
          if ( HDRMetaDataType )
          {
            v159 = HDRMetaDataType - 1;
            if ( v159 )
            {
              if ( v159 == 1 )
              {
                pHDRMetaData = a2->pHDRMetaData;
                *(_OWORD *)((char *)v141 + 364) = *pHDRMetaData;
                *(_OWORD *)((char *)v141 + 380) = pHDRMetaData[1];
                *(_OWORD *)((char *)v141 + 396) = pHDRMetaData[2];
                *(_OWORD *)((char *)v141 + 412) = pHDRMetaData[3];
                *(_QWORD *)((char *)v141 + 428) = *((_QWORD *)pHDRMetaData + 8);
              }
              else
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 4103;
                DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"FALSE", 4103, 0, 0, 0, 0);
                *(_DWORD *)v141 &= ~0x40000000u;
              }
            }
            else
            {
              v161 = a2->pHDRMetaData;
              *(_OWORD *)((char *)v141 + 364) = *v161;
              *(_OWORD *)((char *)v141 + 376) = *(_OWORD *)((char *)v161 + 12);
            }
          }
        }
        else
        {
          if ( (unsigned int)HDRMetaDataType > D3DDDI_HDR_METADATA_TYPE_HDR10PLUS )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 4113;
            DxgkLogInternalTriageEvent(
              0,
              262146,
              -1,
              (unsigned int)L"D3DDDI_HDR_METADATA_TYPE_HDR10 == pArgs->HDRMetaDataType || D3DDDI_HDR_METADATA_TYPE_HDR10PL"
                             "US == pArgs->HDRMetaDataType || D3DDDI_HDR_METADATA_TYPE_NONE == pArgs->HDRMetaDataType",
              4113,
              0,
              0,
              0,
              0);
          }
          if ( a2->pHDRMetaData || a2->HDRMetaDataSize )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 4116;
            DxgkLogInternalTriageEvent(
              0,
              262146,
              -1,
              (unsigned int)L"NULL == pArgs->pHDRMetaData && NULL == pArgs->HDRMetaDataSize",
              4116,
              0,
              0,
              0,
              0);
          }
          *(_DWORD *)v141 |= 0x40000000u;
          if ( a2->HDRMetaDataType == D3DDDI_HDR_METADATA_TYPE_HDR10 )
          {
            *((_DWORD *)v141 + 90) = 134217729;
          }
          else if ( a2->HDRMetaDataType == D3DDDI_HDR_METADATA_TYPE_HDR10PLUS )
          {
            *((_DWORD *)v141 + 90) = -2147483646;
          }
        }
      }
      else
      {
        *((_DWORD *)v141 + 90) = 0;
        *(_DWORD *)v141 = v156 | 0x40000000;
      }
    }
    if ( a2->pPostComposition )
    {
      *(_DWORD *)v141 |= 0x80000000;
      *(RECT *)((char *)v141 + 436) = a2->pPostComposition->SrcRect;
      *(RECT *)((char *)v141 + 452) = a2->pPostComposition->DstRect;
    }
    v162 = *((_QWORD *)this + 2);
    v163 = *(_QWORD *)(v162 + 1896);
    if ( v163 == *(_QWORD *)(*(_QWORD *)(v162 + 16) + 16LL) )
    {
      v164 = *(_DWORD *)(v162 + 4LL * (unsigned int)VidPnSourceId + 1832);
      if ( *((_DWORD *)v141 + 30) != v164 && v164 )
      {
        if ( (a2->Flags.Value & 8) != 0 )
        {
          WdLogSingleEntry1(4, -1071775739);
          WdLogGlobalForLineNumber = 4168;
          CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v205);
          LODWORD(LayerIndex) = -1071775739;
          goto LABEL_309;
        }
        WdLogSingleEntry1(4, v162);
        WdLogGlobalForLineNumber = 4176;
        COREDEVICEACCESS::Release(v207);
        DXGDEVICE::FlushScheduler(*((_QWORD *)this + 2), 3, (unsigned int)VidPnSourceId);
        v165 = COREDEVICEACCESS::AcquireShared(v207, 0);
        v166 = v165;
        if ( v165 < 0 )
        {
          WdLogSingleEntry1(4, v165);
          WdLogGlobalForLineNumber = 4184;
          COREDEVICEACCESS::AcquireSharedUncheck(v207, v167);
          goto LABEL_308;
        }
      }
      v168 = DXGCONTEXT::WaitForQueuedPresentLimit(this, VidPnSourceId, (a2->Flags.Value & 8) == 0, v207);
      v166 = v168;
      if ( v168 < 0 )
      {
        WdLogSingleEntry2(4, v168, this);
        WdLogGlobalForLineNumber = 4198;
        goto LABEL_308;
      }
      v169 = DXGCONTEXT::CheckDevicePresentSettings(this, 1, 0, 1, VidPnSourceId);
      v166 = v169;
      if ( v169 < 0 )
      {
        WdLogSingleEntry2(4, v169, this);
        WdLogGlobalForLineNumber = 4209;
        if ( v166 == -1071774920 )
        {
          DXGCONTEXT::UpdateDisplayStateForFullWDDMDevice(this, a2, v216[0], v220, v196, *((_DWORD *)v141 + 34));
          *(_DWORD *)(*((_QWORD *)this + 2) + 4LL * (unsigned int)VidPnSourceId + 1832) = *((_DWORD *)v141 + 30);
          CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v205);
          goto LABEL_259;
        }
LABEL_308:
        CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v205);
        LODWORD(LayerIndex) = v166;
        goto LABEL_309;
      }
      if ( *((_QWORD *)this + 45) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 4226;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pPresentDmaBuffer == NULL", 4226, 0, 0, 0, 0);
      }
      LODWORD(LayerIndex) = DXGCONTEXT::SubmitPresentMultiPlaneOverlays3(
                              this,
                              a2,
                              v183,
                              v182,
                              v181,
                              v216[0],
                              v223,
                              &v218,
                              v141,
                              v213);
      if ( (int)LayerIndex < 0 )
      {
LABEL_326:
        if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(*(ADAPTER_RENDER **)(*((_QWORD *)this + 2) + 16LL))
          && (_DWORD)LayerIndex != -1073741130 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 4290;
          DxgkLogInternalTriageEvent(
            0,
            262146,
            -1,
            (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner() || Status == STATUS_DEVICE_REMOVED",
            4290,
            0,
            0,
            0,
            0);
        }
        if ( *((_QWORD *)this + 45) )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 4291;
          DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pPresentDmaBuffer == NULL", 4291, 0, 0, 0, 0);
        }
        CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v205);
        goto LABEL_309;
      }
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) + 3248LL) + 128LL)
                     + 4024LL * (unsigned int)VidPnSourceId
                     + 1072) == -1 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 4243;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"!NT_SUCCESS(Status) || (GetDisplayAdapter(VidPnSourceId)->GetDisplayCore()->MapVidPnSourceToVidP"
                         "nTarget(VidPnSourceId) != D3DDDI_ID_UNINITIALIZED)",
          4243,
          0,
          0,
          0,
          0);
      }
      DXGCONTEXT::UpdateDisplayStateForFullWDDMDevice(this, a2, v216[0], v220, v196, *((_DWORD *)v141 + 34));
      v170 = v198;
      v171 = v199;
      v172 = v185;
      *(_DWORD *)(*((_QWORD *)this + 2) + 4LL * (unsigned int)VidPnSourceId + 1832) = *((_DWORD *)v141 + 30);
      v173 = *(struct ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) + 3248LL);
    }
    else
    {
      if ( !v163 )
      {
        WdLogSingleEntry2(1, v162, -1073741822);
        WdLogGlobalForLineNumber = 4285;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"DxgkPresent is called for flip on a render only device 0x%I64x, returning 0x%I64x.",
          *((_QWORD *)this + 2),
          -1073741822,
          0,
          0,
          0);
        CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v205);
        PagedPoolArray<DXGALLOCATIONREFERENCE,4>::~PagedPoolArray<DXGALLOCATIONREFERENCE,4>(v216);
        return -1073741811;
      }
      ppPresentPlanes = a2->ppPresentPlanes;
      v175 = *ppPresentPlanes;
      if ( (*ppPresentPlanes)->LayerIndex )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 4267;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pPlane0->LayerIndex == 0", 4267, 0, 0, 0, 0);
      }
      memset(&v219, 0, sizeof(v219));
      memset(&v214, 0, sizeof(v214));
      ConvertMPOThunkToLegacyPresentThunk(&v219, &v214, a2, v175);
      LODWORD(LayerIndex) = DXGCONTEXT::DisplayOnlyPresent(
                              this,
                              &v219,
                              *(struct DXGALLOCATION **)v216[0],
                              VidPnSourceId,
                              &v218,
                              v207);
      v170 = 0;
      v171 = 0;
      v172 = 0;
      v173 = *(struct ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) + 3248LL);
    }
    UpdatePostComposition(VidPnSourceId, v172, v171, v170, v173);
    goto LABEL_326;
  }
  while ( 1 )
  {
    v59 = v190;
    v60 = a2->ppPresentPlanes[v58];
    v188 = v60;
    LayerIndex = v60->LayerIndex;
    v191 = LayerIndex;
    v61 = (unsigned int)LayerIndex;
    if ( (unsigned int)LayerIndex >= v190 )
    {
      LODWORD(LayerIndex) = -1073741811;
      WdLogSingleEntry3(3, this, v61, -1073741811);
      WdLogGlobalForLineNumber = 3519;
      goto LABEL_309;
    }
    _mm_lfence();
    v206 = 1 << LayerIndex;
    if ( ((1 << LayerIndex) & v52) != 0 )
    {
      LODWORD(LayerIndex) = -1073741811;
      WdLogSingleEntry3(3, this, v61, -1073741811);
      WdLogGlobalForLineNumber = 3526;
      goto LABEL_309;
    }
    if ( (v60->InputFlags.Value & 1) == 0 )
    {
      v119 = (_QWORD *)((char *)v216[0] + 8 * LayerIndex);
      if ( *v119 || v223[LayerIndex] )
        ++v181;
      DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v211, 0);
      DXGALLOCATIONREFERENCE::MoveAssign(v119, v211);
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v211);
      goto LABEL_213;
    }
    v62 = v216[0];
    if ( *((_QWORD *)v216[0] + LayerIndex) || v223[LayerIndex] )
      ++v182;
    else
      ++v183;
    v63 = 0;
    if ( v60->AllocationCount )
      break;
LABEL_114:
    if ( (unsigned int)IsMSRC110351_61431726_Enabled() && *((_QWORD *)v216[0] + v61) == v72 )
    {
      v132 = (unsigned int)LayerIndex;
      LODWORD(LayerIndex) = -1073741811;
      WdLogSingleEntry3(3, -1073741811, this, v132);
      WdLogGlobalForLineNumber = 3581;
      goto LABEL_309;
    }
    _mm_lfence();
    v73 = (const struct DXGALLOCATION *)*((_QWORD *)v216[0] + v61);
    v74 = *(_DWORD *)(*((_QWORD *)v73 + 6) + 4LL);
    if ( (v74 & 0x2000) != 0 )
    {
      if ( (v74 & 0x20) == 0 )
      {
        if ( !DXGDEVICE::IsDirectFlipAllocationRequestedPinned(*((DXGDEVICE **)this + 2), v73) )
        {
          _mm_lfence();
          WdLogSingleEntry5(
            4,
            -1071775739,
            this,
            *((_QWORD *)v216[0] + v61),
            *(_QWORD *)(*((_QWORD *)v216[0] + v61) + 48LL),
            *v60->pAllocationList);
          WdLogGlobalForLineNumber = 3614;
          goto LABEL_231;
        }
        _mm_lfence();
        if ( !VIDMM_EXPORT::VidMmIsAllocationPinned(
                *(VIDMM_EXPORT **)(*(_QWORD *)(v75 + 16) + 760LL),
                *(struct VIDMM_GLOBAL **)(*(_QWORD *)(v75 + 16) + 768LL),
                *(struct VIDMM_MULTI_ALLOC **)(*((_QWORD *)v216[0] + v61) + 24LL)) )
        {
          _mm_lfence();
          MicrosoftTelemetryAssertTriggeredArgsMsgKM(
            *(_QWORD *)(*((_QWORD *)this + 2) + 16LL),
            *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 16LL) + 3132LL),
            0,
            "DFlip allocation unpinned");
          v76 = VIDMM_EXPORT::VidMmPinAllocation(
                  *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 760LL),
                  *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 768LL),
                  *(struct VIDMM_MULTI_ALLOC **)(*((_QWORD *)v216[0] + v61) + 24LL),
                  0,
                  0);
          if ( v76 < 0 )
          {
            _mm_lfence();
            WdLogSingleEntry4(
              4,
              *((_QWORD *)v216[0] + (unsigned int)LayerIndex),
              *(_QWORD *)(*((_QWORD *)v216[0] + (unsigned int)LayerIndex) + 48LL),
              *v60->pAllocationList,
              v76);
            WdLogGlobalForLineNumber = 3646;
LABEL_231:
            LODWORD(LayerIndex) = -1071775720;
            goto LABEL_309;
          }
        }
      }
    }
    else if ( (v74 & 0xB) != 0 )
    {
      v78 = v196;
      if ( ((unsigned __int8)v74 & v71) != 0 )
        v78 = LayerIndex;
      v196 = v78;
    }
    else if ( v210 == (_DWORD)v72 || (a2->Flags.Value & 0x400) == 0 )
    {
      _mm_lfence();
      v77 = (unsigned int)LayerIndex;
      LayerIndex = -1073741811;
      WdLogSingleEntry5(
        2,
        -1073741811,
        this,
        *((_QWORD *)v216[0] + v77),
        *(_QWORD *)(*((_QWORD *)v216[0] + v77) + 48LL),
        *v60->pAllocationList);
      WdLogGlobalForLineNumber = 3679;
      v41 = L"0x%I64x 0x%I64x Source of Flip must be primary 0x%I64x 0x%I64x 0x%I64x";
      v178 = *v60->pAllocationList;
      v177 = *(_QWORD *)(*((_QWORD *)v216[0] + (unsigned int)v61) + 48LL);
      v176 = *((_QWORD *)v216[0] + (unsigned int)v61);
      goto LABEL_59;
    }
    _mm_lfence();
    memset(&v215, 0, sizeof(v215));
    v215.hAllocation = *(HANDLE *)(*(_QWORD *)(*((_QWORD *)v216[0] + v61) + 48LL) + 16LL);
    v79 = ADAPTER_RENDER::DdiDescribeAllocation(*(ADAPTER_RENDER **)(*((_QWORD *)this + 2) + 16LL), &v215);
    LayerIndex = v79;
    if ( v79 < 0 )
    {
      _mm_lfence();
      WdLogSingleEntry4(
        2,
        v79,
        this,
        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v216[0] + v61) + 48LL) + 16LL),
        *((_QWORD *)v216[0] + v61));
      WdLogGlobalForLineNumber = 3692;
      v178 = 0;
      v41 = L"ret = 0x%I64x Context 0x%I64x: DdiDescribeAllocation failed 0x%I64x 0x%I64x";
      v177 = *((_QWORD *)v216[0] + (unsigned int)v61);
      v176 = *(_QWORD *)(*(_QWORD *)(v177 + 48) + 16LL);
      goto LABEL_59;
    }
    pPlaneAttributes = v60->pPlaneAttributes;
    v220[v61] = v215.Format;
    v81 = pPlaneAttributes->SrcRect.right;
    v82 = pPlaneAttributes->SrcRect.left;
    v209 = v81;
    v208 = v82;
    if ( v82 >= v81
      || (v83 = pPlaneAttributes->SrcRect.bottom, v84 = pPlaneAttributes->SrcRect.top, v200 = v83, v84 >= v83) )
    {
      v40 = v186;
      LayerIndex = -1073741811;
      WdLogSingleEntry3(2, -1073741811, this, v186);
      WdLogGlobalForLineNumber = 3704;
LABEL_245:
      v41 = L"ret = 0x%I64x Context 0x%I64x Source rect is invalid, index 0x%I64x";
LABEL_57:
      v178 = 0;
      v177 = 0;
      goto LABEL_58;
    }
    if ( v82 < 0
      || (LODWORD(v203) = v215.Width, (int)v215.Width < v81)
      || v84 < 0
      || (LODWORD(v204) = v215.Height, (int)v215.Height < v83) )
    {
      v40 = v186;
      LayerIndex = -1073741811;
      WdLogSingleEntry3(2, -1073741811, this, v186);
      WdLogGlobalForLineNumber = 3712;
LABEL_243:
      v178 = 0;
      v41 = L"ret = 0x%I64x Context 0x%I64x Source rect is outside of allocation rect, index 0x%I64x";
      v177 = 0;
LABEL_58:
      v176 = v40;
LABEL_59:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v41, LayerIndex, (__int64)this, v176, v177, v178);
      goto LABEL_309;
    }
    v85 = pPlaneAttributes->ClipRect.right;
    v86 = pPlaneAttributes->ClipRect.left;
    if ( v86 >= v85 || (v87 = pPlaneAttributes->ClipRect.top, v88 = pPlaneAttributes->ClipRect.bottom, v87 >= v88) )
    {
      v40 = v186;
      LayerIndex = -1073741811;
      WdLogSingleEntry3(2, -1073741811, this, v186);
      v178 = 0;
      v41 = L"ret = 0x%I64x Context 0x%I64x Clip rect is invalid, index 0x%I64x";
      v177 = 0;
      WdLogGlobalForLineNumber = 3723;
      goto LABEL_58;
    }
    v89 = pPlaneAttributes->DstRect.left;
    v90 = pPlaneAttributes->DstRect.right;
    if ( v89 >= v90 || (v91 = pPlaneAttributes->DstRect.top, v92 = pPlaneAttributes->DstRect.bottom, v91 >= v92) )
    {
      v40 = v186;
      LayerIndex = -1073741811;
      WdLogSingleEntry3(2, -1073741811, this, v186);
      v178 = 0;
      v41 = L"ret = 0x%I64x Context 0x%I64x Destination rect is invalid, index 0x%I64x";
      v177 = 0;
      WdLogGlobalForLineNumber = 3730;
      goto LABEL_58;
    }
    if ( left > v86 || v193 < v85 || v197 > v87 || v194 < v88 )
    {
      LODWORD(LayerIndex) = -1073741811;
      WdLogSingleEntry3(2, -1073741811, this, v186);
      WdLogGlobalForLineNumber = 3737;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"ret = 0x%I64x Context 0x%I64x Clip rect is outside of virtual mode rect, index 0x%I64x",
        -1073741811,
        (__int64)this,
        v186,
        0,
        0);
      v134 = v60->pPlaneAttributes;
      v135 = v134->ClipRect.right;
      v136 = v134->ClipRect.bottom;
      Feature_EnableNonCriticalAsserts__private_IsEnabledPreCheck();
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        v137,
        (v135 << 16) | (unsigned int)(unsigned __int16)v136,
        (unsigned __int16)v194 | (unsigned int)(v193 << 16),
        "ClipRect outside VirtualModeRect");
      goto LABEL_309;
    }
    if ( v89 > v86 || v90 < v85 || v91 > v87 || v92 < v88 )
    {
      LODWORD(LayerIndex) = -1073741811;
      WdLogSingleEntry3(2, -1073741811, this, v186);
      WdLogGlobalForLineNumber = 3756;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"ret = 0x%I64x Context 0x%I64x Clip rect is outside of destination rect, index 0x%I64x",
        -1073741811,
        (__int64)this,
        v186,
        0,
        0);
      v133 = v60->pPlaneAttributes;
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        (unsigned __int16)v133->ClipRect.bottom,
        (unsigned int)(unsigned __int16)v133->ClipRect.bottom | (v133->ClipRect.right << 16),
        (unsigned int)(unsigned __int16)v133->DstRect.bottom | (v133->DstRect.right << 16),
        "ClipRect outside DestRect");
      goto LABEL_309;
    }
    Rotation = pPlaneAttributes->Rotation;
    if ( (_DWORD)Rotation )
    {
      if ( (_DWORD)Rotation != 1 && (_DWORD)Rotation != 2 && (unsigned int)(Rotation - 3) >= 2 )
      {
        v40 = v186;
        LayerIndex = -1073741811;
        WdLogSingleEntry4(2, -1073741811, this, v186, Rotation);
        WdLogGlobalForLineNumber = 3791;
        v41 = L"ret = 0x%I64x Context 0x%I64x rotation is not valid, index 0x%I64x, rotation 0xI64x";
        v178 = 0;
        v177 = v60->pPlaneAttributes->Rotation;
        goto LABEL_58;
      }
    }
    else
    {
      pPlaneAttributes->Rotation = D3DDDI_ROTATION_IDENTITY;
    }
    DirtyRectCount = pPlaneAttributes->DirtyRectCount;
    if ( DirtyRectCount )
    {
      v95 = 1;
      v96 = 0;
      while ( v95 )
      {
        pDirtyRects = pPlaneAttributes->pDirtyRects;
        v98 = pDirtyRects[v96].right;
        p_left = &pDirtyRects[v96].left;
        if ( *p_left >= v98 || p_left[1] >= p_left[3] )
          v95 = 0;
        if ( v208 > *p_left || v209 < v98 || pPlaneAttributes->SrcRect.top > p_left[1] || v200 < p_left[3] )
          v95 = 0;
        if ( ++v96 >= DirtyRectCount )
        {
          if ( v95 )
            goto LABEL_168;
          break;
        }
      }
      pPlaneAttributes->DirtyRectCount = 0;
    }
LABEL_168:
    if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) + 3146LL) )
    {
      v100 = v60->pPlaneAttributes;
      if ( v100->DstRect.left != v100->ClipRect.left
        || v100->DstRect.right != v100->ClipRect.right
        || v100->DstRect.top != v100->ClipRect.top
        || v100->DstRect.bottom != v100->ClipRect.bottom )
      {
        *(_OWORD *)&v214.DirtyRectCount = 0;
        InverseXformMPORect3(&v214);
        pPlaneAttributes->SrcRect = *(RECT *)&v214.DirtyRectCount;
        pPlaneAttributes->DstRect = v60->pPlaneAttributes->ClipRect;
        v101 = pPlaneAttributes->SrcRect.right;
        v102 = pPlaneAttributes->SrcRect.left;
        if ( v102 >= v101
          || (v103 = pPlaneAttributes->SrcRect.top, v104 = pPlaneAttributes->SrcRect.bottom, v103 >= v104) )
        {
          v40 = v186;
          LayerIndex = -1073741811;
          WdLogSingleEntry3(2, -1073741811, this, v186);
          WdLogGlobalForLineNumber = 3835;
          goto LABEL_245;
        }
        v105 = pPlaneAttributes->DstRect.left;
        v106 = pPlaneAttributes->DstRect.right;
        if ( v105 >= v106
          || (v107 = pPlaneAttributes->DstRect.top, v108 = pPlaneAttributes->DstRect.bottom, v107 >= v108) )
        {
          v40 = v186;
          LayerIndex = -1073741811;
          WdLogSingleEntry3(2, -1073741811, this, v186);
          v41 = L"ret = 0x%I64x Context 0x%I64x Dest rect is invalid, index 0x%I64x";
          WdLogGlobalForLineNumber = 3842;
          goto LABEL_57;
        }
        if ( v102 < 0 || (int)v203 < v101 || v103 < 0 || (int)v204 < v104 )
        {
          v40 = v186;
          LayerIndex = -1073741811;
          WdLogSingleEntry3(2, -1073741811, this, v186);
          WdLogGlobalForLineNumber = 3849;
          goto LABEL_243;
        }
        if ( left > v105 || v193 < v106 || v197 > v107 || v194 < v108 )
        {
          v40 = v186;
          LayerIndex = -1073741811;
          WdLogSingleEntry3(2, -1073741811, this, v186);
          v178 = 0;
          v41 = L"ret = 0x%I64x Context 0x%I64x Dest rect is outside of screen rect, index 0x%I64x";
          v177 = 0;
          WdLogGlobalForLineNumber = 3856;
          goto LABEL_58;
        }
      }
    }
    if ( !v191 )
    {
      if ( v205[0] )
      {
        v109 = *(_DWORD *)(*((_QWORD *)v205[0] + 6) + 4LL) & 0x2000;
        if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v216[0] + 48LL) + 4LL) & 0x2000) != 0 )
        {
          if ( !v109 )
            LOBYTE(v195) = 1;
        }
        else
        {
          v110 = (unsigned __int8)v195;
          if ( v109 )
            v110 = 1;
          v195 = v110;
        }
      }
      v111 = pPlaneAttributes->SrcRect.right - pPlaneAttributes->SrcRect.left;
      if ( (pPlaneAttributes->DstRect.right - pPlaneAttributes->DstRect.left != v111
         || pPlaneAttributes->DstRect.bottom - pPlaneAttributes->DstRect.top != pPlaneAttributes->SrcRect.bottom
                                                                              - pPlaneAttributes->SrcRect.top)
        && *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) + 3098LL) )
      {
        v198 = pPlaneAttributes->SrcRect.bottom - pPlaneAttributes->SrcRect.top;
        v185 = 1;
        v199 = v111;
      }
    }
    if ( v184 )
    {
      v112 = pPlaneAttributes->DstRect.left;
      if ( v112 != pPlaneAttributes->SrcRect.left
        || (v113 = pPlaneAttributes->DstRect.right, v113 != pPlaneAttributes->SrcRect.right)
        || (v114 = pPlaneAttributes->DstRect.top, v114 != pPlaneAttributes->SrcRect.top)
        || (v115 = pPlaneAttributes->DstRect.bottom, v115 != pPlaneAttributes->SrcRect.bottom)
        || v112 != pPlaneAttributes->ClipRect.left
        || v113 != pPlaneAttributes->ClipRect.right
        || v114 != pPlaneAttributes->ClipRect.top
        || v115 != pPlaneAttributes->ClipRect.bottom )
      {
        LayerIndex = -1073741811;
        WdLogSingleEntry2(2, -1073741811, this);
        WdLogGlobalForLineNumber = 3896;
        v178 = 0;
        v41 = L"0x%I64x Context 0x%I64x PresentMPO fails because the driver doesn't support MPO and Source/Dest/Clip rects"
               " are not identical";
        v177 = 0;
        v176 = 0;
        goto LABEL_59;
      }
      v116 = v60->pPlaneAttributes;
      if ( v116->Rotation != D3DDDI_ROTATION_IDENTITY )
      {
        LayerIndex = -1073741811;
        WdLogSingleEntry3(2, -1073741811, this, (unsigned int)v116->Rotation);
        WdLogGlobalForLineNumber = 3905;
        v41 = L"0x%I64x Context 0x%I64x PresentMPO fails because the driver doesn't support MPO and rotation 0x%I64x is specified";
        v178 = 0;
        v177 = 0;
        v176 = (unsigned int)v60->pPlaneAttributes->Rotation;
        goto LABEL_59;
      }
      _mm_lfence();
      if ( v189 != ((*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v216[0] + v191) + 48LL) + 4LL) >> 6) & 0xF) )
      {
        _mm_lfence();
        v117 = v189;
        v118 = v191;
        LayerIndex = -1073741811;
        WdLogSingleEntry4(
          2,
          -1073741811,
          this,
          v189,
          (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v216[0] + v191) + 48LL) + 4LL) >> 6) & 0xF);
        v41 = L"0x%I64x Context 0x%I64x PresentMPO fails because the driver doesn't support MPO and VidPnSourceId (0x%I64x"
               ") doesn't match the surface VidPnSOurceId (0x%I64x)";
        WdLogGlobalForLineNumber = 3914;
        v178 = 0;
        v177 = (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v216[0] + v118) + 48LL) + 4LL) >> 6) & 0xF;
        v176 = v117;
        goto LABEL_59;
      }
    }
LABEL_213:
    if ( (v60->InputFlags.Value & 1) != 0 || v187 )
    {
      FlipInterval = v60->FlipInterval;
      if ( FlipInterval )
      {
        if ( FlipInterval != D3DDDI_FLIPINTERVAL_ONE )
        {
          LODWORD(LayerIndex) = -1073741811;
          WdLogSingleEntry3(3, this, v60->FlipInterval, -1073741811);
          WdLogGlobalForLineNumber = 3952;
          goto LABEL_309;
        }
        v202 = 1;
      }
    }
    if ( !bTracingEnabled )
      goto LABEL_224;
    v121 = v60->pPlaneAttributes;
    v122 = v188;
    v123 = a2->HDRMetaDataType;
    Blend = v121->Blend;
    v125 = v121->Rotation;
    Flags = v121->Flags;
    SDRWhiteLevel = v121->SDRWhiteLevel;
    v128 = *v188->pAllocationList;
    ColorSpace = v121->ColorSpace;
    LODWORD(v204) = Blend;
    LODWORD(v203) = v125;
    v200 = Flags;
    if ( v128 )
    {
      v130 = (unsigned int)VIDMM_EXPORT::VidMmETWAllocationHandle(
                             *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 760LL),
                             *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 768LL),
                             v128);
      LOBYTE(Blend) = (_BYTE)v204;
      v131 = v130;
      LOBYTE(v125) = v203;
      LOBYTE(Flags) = v200;
      v122 = v188;
    }
    else
    {
      v131 = 0;
    }
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
    {
      v180 = ColorSpace;
      LODWORD(VidPnSourceId) = v189;
      McTemplateK0qqqpqddddddddddddqqqqqq_EtwWriteTransfer(
        v122->InputFlags.Value & 1,
        v131,
        v128,
        v189,
        v188->LayerIndex,
        *(_BYTE *)&v122->InputFlags.0 & 1,
        v131,
        Flags,
        v121->SrcRect.left,
        v121->SrcRect.right,
        v121->SrcRect.top,
        v121->SrcRect.bottom,
        v121->DstRect.left,
        v121->DstRect.right,
        v121->DstRect.top,
        v121->DstRect.bottom,
        v121->ClipRect.left,
        v121->ClipRect.right,
        v121->ClipRect.top,
        v121->ClipRect.bottom,
        v125,
        Blend,
        v179,
        v180,
        v123,
        SDRWhiteLevel);
    }
    else
    {
LABEL_224:
      LODWORD(VidPnSourceId) = v189;
    }
    v58 = v186 + 1;
    v186 = v58;
    if ( v58 >= a2->PresentPlaneCount )
    {
      v10 = v184;
      v53 = v202;
      goto LABEL_251;
    }
    v52 = v206 | v201;
    v201 |= v206;
  }
  while ( 1 )
  {
    v203 = (unsigned int)LayerIndex + v59 * v63;
    v204 = (char *)v62 + 8 * v203;
    v64 = *(_QWORD *)(*((_QWORD *)this + 2) + 40LL);
    v65 = v188->pAllocationList[v63];
    DXGPUSHLOCK::AcquireShared((DXGPUSHLOCK *)(v64 + 248));
    v66 = (v65 >> 6) & 0xFFFFFF;
    if ( v66 >= *(_DWORD *)(v64 + 296) )
      goto LABEL_110;
    v67 = *(_QWORD *)(v64 + 280);
    if ( ((v65 >> 25) & 0x60) == (*(_BYTE *)(v67 + 16LL * v66 + 8) & 0x60)
      && (*(_DWORD *)(v67 + 16LL * v66 + 8) & 0x2000) == 0
      && (v68 = *(_DWORD *)(v67 + 16LL * v66 + 8) & 0x1F) != 0 )
    {
      if ( v68 == 5 )
      {
        v69 = *(struct DXGALLOCATION **)(v67 + 16LL * v66);
      }
      else
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 318;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        v69 = 0;
      }
    }
    else
    {
LABEL_110:
      v69 = 0;
    }
    DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v212, v69);
    _InterlockedDecrement((volatile signed __int32 *)(v64 + 264));
    ExReleasePushLockSharedEx(v64 + 248, 0);
    KeLeaveCriticalRegion();
    DXGALLOCATIONREFERENCE::MoveAssign(v204, v212);
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v212);
    v62 = v216[0];
    v70 = *((_QWORD *)v216[0] + v203);
    if ( !v70 )
      break;
    if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v70 + 8) + 16LL) + 16LL) != *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2)
                                                                                               + 16LL)
                                                                                   + 16LL) )
    {
      LODWORD(LayerIndex) = -1073741811;
      WdLogSingleEntry3(2, *((_QWORD *)this + 2), v70, -1073741811);
      WdLogGlobalForLineNumber = 3565;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Device 0x%p does not match allocation 0x%p owner, returning 0x%I64x",
        *((_QWORD *)this + 2),
        *((_QWORD *)v216[0] + (unsigned int)v61 + v190 * v63),
        -1073741811,
        0,
        0);
      goto LABEL_309;
    }
    v60 = v188;
    v59 = v190;
    ++v63;
    LODWORD(LayerIndex) = v61;
    if ( v63 >= v188->AllocationCount )
      goto LABEL_114;
  }
  LODWORD(LayerIndex) = -1073741811;
  WdLogSingleEntry3(3, -1073741811, this, v188->pAllocationList[v63]);
  WdLogGlobalForLineNumber = 3556;
LABEL_309:
  PagedPoolArray<DXGALLOCATIONREFERENCE,4>::~PagedPoolArray<DXGALLOCATIONREFERENCE,4>(v216);
  return (unsigned int)LayerIndex;
}

```

## disassembly

```asm
0x1404098b8  push    rbp
0x1404098ba  push    rbx
0x1404098bb  push    rsi
0x1404098bc  push    rdi
0x1404098bd  push    r12
0x1404098bf  push    r13
0x1404098c1  push    r14
0x1404098c3  push    r15
0x1404098c5  lea     rbp, [rsp-788h]
0x1404098cd  sub     rsp, 8D8h
0x1404098d4  mov     rax, cs:__security_cookie
0x1404098db  xor     rax, rsp
0x1404098de  mov     [rbp+7C0h+var_48], rax
0x1404098e5  mov     r14, rcx
0x1404098e8  mov     [rbp+7C0h+var_7A0], r9
0x1404098ec  mov     rcx, [rcx+10h]
0x1404098f0  mov     rdi, rdx
0x1404098f3  mov     [rbp+7C0h+var_7C8], r8
0x1404098f7  mov     rax, [rcx+768h]
0x1404098fe  mov     rcx, [rcx+10h]; this
0x140409902  mov     ebx, [rax+1BCh]
0x140409908  and     ebx, 100h
0x14040990e  mov     [rbp+7C0h+var_7B8], ebx
0x140409911  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x140409916  or      esi, 0FFFFFFFFh
0x140409919  xor     r12d, r12d
0x14040991c  mov     r15d, 1
0x140409922  mov     r13d, 40002h
0x140409928  test    al, al
0x14040992a  jnz     short loc_140409973
0x14040992c  mov     ecx, r15d
0x14040992f  call    cs:__imp_WdLogSingleEntry0
0x140409936  nop     dword ptr [rax+rax+00h]
0x14040993b  mov     [rsp+910h+var_8D0], r12
0x140409940  lea     r9, aGetrendercoreI_1; "GetRenderCore()->IsCoreResourceSharedOw"...
0x140409947  mov     [rsp+910h+var_8D8], r12
0x14040994c  mov     eax, 0CBAh
0x140409951  mov     [rsp+910h+var_8E0], r12
0x140409956  mov     r8d, esi
0x140409959  mov     [rsp+910h+var_8E8], r12
0x14040995e  mov     edx, r13d
0x140409961  xor     ecx, ecx
0x140409963  mov     [rsp+910h+var_8F0], rax
0x140409968  mov     cs:WdLogGlobalForLineNumber, eax
0x14040996e  call    DxgkLogInternalTriageEvent
0x140409973  mov     rcx, [r14+10h]
0x140409977  mov     rax, [rcx+10h]
0x14040997b  mov     rdx, [rax+10h]
0x14040997f  test    rdx, rdx
0x140409982  jnz     short loc_140409988
0x140409984  test    ebx, ebx
0x140409986  jnz     short loc_1404099D8
0x140409988  cmp     [rcx+768h], rdx
0x14040998f  jz      short loc_1404099D8
0x140409991  mov     ecx, r15d
0x140409994  call    cs:__imp_WdLogSingleEntry0
0x14040999b  nop     dword ptr [rax+rax+00h]
0x1404099a0  mov     [rsp+910h+var_8D0], r12
0x1404099a5  lea     r9, aGetrenderadapt_1; "(!GetRenderAdapter() && IsIndirectDispl"...
0x1404099ac  mov     [rsp+910h+var_8D8], r12
0x1404099b1  mov     eax, 0CBBh
0x1404099b6  mov     [rsp+910h+var_8E0], r12
0x1404099bb  mov     r8d, esi
0x1404099be  mov     [rsp+910h+var_8E8], r12
0x1404099c3  mov     edx, r13d
0x1404099c6  xor     ecx, ecx
0x1404099c8  mov     [rsp+910h+var_8F0], rax
0x1404099cd  mov     cs:WdLogGlobalForLineNumber, eax
0x1404099d3  call    DxgkLogInternalTriageEvent
0x1404099d8  mov     [r14+1B3h], r15b
0x1404099df  test    ebx, ebx
0x1404099e1  jz      short loc_1404099E8
0x1404099e3  mov     esi, r15d
0x1404099e6  jmp     short loc_1404099FA
0x1404099e8  mov     rax, [r14+10h]
0x1404099ec  mov     rcx, [rax+10h]
0x1404099f0  mov     rax, [rcx+10h]
0x1404099f4  mov     esi, [rax+0C00h]
0x1404099fa  mov     eax, [rdi+1Ch]
0x1404099fd  mov     [rbp+7C0h+var_824], esi
0x140409a00  cmp     eax, esi
0x140409a02  jbe     short loc_140409A35
0x140409a04  mov     r8d, esi
0x140409a07  mov     edx, eax
0x140409a09  mov     rsi, 0FFFFFFFFC000000Dh
0x140409a10  mov     ecx, 3
0x140409a15  mov     r9, rsi
0x140409a18  call    cs:__imp_WdLogSingleEntry3
0x140409a1f  nop     dword ptr [rax+rax+00h]
0x140409a24  mov     cs:WdLogGlobalForLineNumber, 0CCCh
0x140409a2e  mov     eax, esi
0x140409a30  jmp     loc_14040BD16
0x140409a35  mov     r13d, [rdi+10h]
0x140409a39  mov     [rbp+7C0h+var_828], r13d
0x140409a3d  test    ebx, ebx
0x140409a3f  jnz     loc_140409ACB
0x140409a45  mov     r9d, r15d; int
0x140409a48  mov     dword ptr [rsp+910h+var_8F0], r13d; unsigned int
0x140409a4d  xor     r8d, r8d; int
0x140409a50  mov     edx, r15d; int
0x140409a53  mov     rcx, r14; this
0x140409a56  call    ?CheckDevicePresentSettings@DXGCONTEXT@@QEAAJHHHI@Z; DXGCONTEXT::CheckDevicePresentSettings(int,int,int,uint)
0x140409a5b  movsxd  rbx, eax
0x140409a5e  mov     r9d, r13d
0x140409a61  test    eax, eax
0x140409a63  jns     short loc_140409A8D
0x140409a65  mov     rdx, rbx
0x140409a68  mov     r8, r14
0x140409a6b  mov     ecx, 3
0x140409a70  call    cs:__imp_WdLogSingleEntry3
0x140409a77  nop     dword ptr [rax+rax+00h]
0x140409a7c  mov     cs:WdLogGlobalForLineNumber, 0CDFh
0x140409a86  mov     eax, ebx
0x140409a88  jmp     loc_14040BD16
0x140409a8d  mov     rax, [r14+10h]
0x140409a91  mov     ecx, [rax+r13*4+4D8h]
0x140409a99  shr     ecx, 9
0x140409a9c  test    r15b, cl
0x140409a9f  jnz     short loc_140409ACB
0x140409aa1  mov     rbx, 0FFFFFFFFC01E0019h
0x140409aa8  mov     r8, r14
0x140409aab  mov     rdx, rbx
0x140409aae  mov     ecx, 3
0x140409ab3  call    cs:__imp_WdLogSingleEntry3
0x140409aba  nop     dword ptr [rax+rax+00h]
0x140409abf  mov     cs:WdLogGlobalForLineNumber, 0CE8h
0x140409ac9  jmp     short loc_140409A86
0x140409acb  mov     eax, [rdi+18h]
0x140409ace  mov     ebx, 2
0x140409ad3  mov     edx, eax
0x140409ad5  mov     r8d, eax
0x140409ad8  and     edx, r15d
0x140409adb  mov     r15d, 40000h
0x140409ae1  and     r8d, ebx
0x140409ae4  jnz     short loc_140409AEE
0x140409ae6  test    edx, edx
0x140409ae8  jz      loc_140409E66
0x140409aee  cmp     dword ptr [rdi+1Ch], 1
0x140409af2  jbe     short loc_140409B4C
0x140409af4  mov     rsi, 0FFFFFFFFC000000Dh
0x140409afb  mov     rdx, r14
0x140409afe  mov     r8, rsi
0x140409b01  mov     ecx, ebx
0x140409b03  call    cs:__imp_WdLogSingleEntry2
0x140409b0a  nop     dword ptr [rax+rax+00h]
0x140409b0f  mov     [rsp+910h+var_8D0], r12
0x140409b14  lea     r9, aDxgkpresentmul_0; "DxgkPresentMultiPlaneOverlay doesn't su"...
0x140409b1b  mov     [rsp+910h+var_8D8], r12
0x140409b20  or      r8d, 0FFFFFFFFh
0x140409b24  mov     [rsp+910h+var_8E0], r12
0x140409b29  mov     edx, r15d
0x140409b2c  mov     [rsp+910h+var_8E8], rsi
0x140409b31  xor     ecx, ecx
0x140409b33  mov     [rsp+910h+var_8F0], r14
0x140409b38  mov     cs:WdLogGlobalForLineNumber, 0CF7h
0x140409b42  call    DxgkLogInternalTriageEvent
0x140409b47  jmp     loc_140409A2E
0x140409b4c  test    r8d, r8d
0x140409b4f  jz      short loc_140409BA1
0x140409b51  test    edx, edx
0x140409b53  jz      short loc_140409BA1
0x140409b55  mov     ecx, ebx
0x140409b57  call    cs:__imp_WdLogSingleEntry0
0x140409b5e  nop     dword ptr [rax+rax+00h]
0x140409b63  mov     eax, 0CFEh
0x140409b68  lea     r9, aFlipstereotemp_0; "FlipStereoTemporaryMono and FlipStereo "...
0x140409b6f  mov     [rsp+910h+var_8D0], r12
0x140409b74  or      r8d, 0FFFFFFFFh
0x140409b78  mov     [rsp+910h+var_8D8], r12
0x140409b7d  mov     edx, r15d
0x140409b80  mov     [rsp+910h+var_8E0], r12
0x140409b85  xor     ecx, ecx
0x140409b87  mov     [rsp+910h+var_8E8], r12
0x140409b8c  mov     [rsp+910h+var_8F0], rax
0x140409b91  mov     cs:WdLogGlobalForLineNumber, eax
0x140409b97  call    DxgkLogInternalTriageEvent
0x140409b9c  jmp     loc_14040BD0F
0x140409ba1  and     eax, 6
0x140409ba4  cmp     al, 6
0x140409ba6  jnz     short loc_140409BC4
0x140409ba8  mov     ecx, ebx
0x140409baa  call    cs:__imp_WdLogSingleEntry0
0x140409bb1  nop     dword ptr [rax+rax+00h]
0x140409bb6  mov     eax, 0D04h
0x140409bbb  lea     r9, aFlipstereotemp_2; "FlipStereoTemporaryMono cannot be used "...
0x140409bc2  jmp     short loc_140409B6F
0x140409bc4  xor     edx, edx; struct DXGALLOCATION *
0x140409bc6  lea     rcx, [rbp+7C0h+var_830]; this
0x140409bca  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x140409bcf  mov     rax, [r14+10h]
0x140409bd3  mov     r12, [rax+28h]
0x140409bd7  mov     rax, [rdi+20h]
0x140409bdb  lea     rsi, [r12+0F8h]
0x140409be3  mov     r13, [rax]
0x140409be6  mov     rcx, rsi; this
0x140409be9  mov     rax, [r13+18h]
0x140409bed  mov     ebx, [rax]
0x140409bef  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x140409bf4  mov     eax, ebx
0x140409bf6  shr     eax, 6
0x140409bf9  and     eax, 0FFFFFFh
0x140409bfe  cmp     eax, [r12+128h]
0x140409c06  jnb     loc_140409C9C
0x140409c0c  mov     r8, [r12+118h]
0x140409c14  mov     edx, eax
0x140409c16  add     rdx, rdx
0x140409c19  shr     ebx, 19h
0x140409c1c  and     ebx, 60h
0x140409c1f  mov     ecx, [r8+rdx*8+8]
0x140409c24  mov     eax, ecx
0x140409c26  and     eax, 60h
0x140409c29  cmp     bl, al
0x140409c2b  jnz     short loc_140409C9C
0x140409c2d  bt      ecx, 0Dh
0x140409c31  jb      short loc_140409C9C
0x140409c33  and     ecx, 1Fh
0x140409c36  jz      short loc_140409C9C
0x140409c38  cmp     ecx, 5
0x140409c3b  jz      short loc_140409C8E
0x140409c3d  mov     ebx, 2
0x140409c42  mov     ecx, ebx
0x140409c44  call    cs:__imp_WdLogSingleEntry0
0x140409c4b  nop     dword ptr [rax+rax+00h]
0x140409c50  xor     r12d, r12d
0x140409c53  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x140409c5a  mov     [rsp+910h+var_8D0], r12
0x140409c5f  mov     eax, 13Eh
0x140409c64  mov     [rsp+910h+var_8D8], r12
0x140409c69  or      r8d, 0FFFFFFFFh
0x140409c6d  mov     [rsp+910h+var_8E0], r12
0x140409c72  mov     edx, r15d
0x140409c75  mov     [rsp+910h+var_8E8], r12
0x140409c7a  xor     ecx, ecx
0x140409c7c  mov     [rsp+910h+var_8F0], rax
0x140409c81  mov     cs:WdLogGlobalForLineNumber, eax
0x140409c87  call    DxgkLogInternalTriageEvent
0x140409c8c  jmp     short loc_140409CA4
0x140409c8e  mov     rdx, [r8+rdx*8]
0x140409c92  xor     r12d, r12d
0x140409c95  lea     ebx, [r12+2]
0x140409c9a  jmp     short loc_140409CA7
0x140409c9c  xor     r12d, r12d
0x140409c9f  lea     ebx, [r12+2]
0x140409ca4  mov     rdx, r12; struct DXGALLOCATION *
0x140409ca7  lea     rcx, [rbp+7C0h+var_7D0]; this
0x140409cab  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x140409cb0  lock dec dword ptr [rsi+10h]
0x140409cb4  xor     edx, edx
0x140409cb6  mov     rcx, rsi
0x140409cb9  call    cs:__imp_ExReleasePushLockSharedEx
0x140409cc0  nop     dword ptr [rax+rax+00h]
0x140409cc5  call    cs:__imp_KeLeaveCriticalRegion
0x140409ccc  nop     dword ptr [rax+rax+00h]
0x140409cd1  lea     rdx, [rbp+7C0h+var_7D0]
0x140409cd5  lea     rcx, [rbp+7C0h+var_830]
0x140409cd9  call    ?MoveAssign@DXGALLOCATIONREFERENCE@@QEAAAEAV1@$$QEAV1@@Z; DXGALLOCATIONREFERENCE::MoveAssign(DXGALLOCATIONREFERENCE &&)
0x140409cde  lea     rcx, [rbp+7C0h+var_7D0]; this
0x140409ce2  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x140409ce7  mov     rax, [rbp+7C0h+var_830]
0x140409ceb  test    rax, rax
0x140409cee  jnz     short loc_140409D5E
0x140409cf0  mov     rax, [r13+18h]
0x140409cf4  mov     rsi, 0FFFFFFFFC000000Dh
0x140409cfb  mov     r8, r14
0x140409cfe  mov     rdx, rsi
0x140409d01  mov     ecx, ebx
0x140409d03  mov     r9d, [rax]
0x140409d06  call    cs:__imp_WdLogSingleEntry3
0x140409d0d  nop     dword ptr [rax+rax+00h]
0x140409d12  mov     [rsp+910h+var_8D0], r12
0x140409d17  lea     r9, aRet0xI64xConte_14; "ret = 0x%I64x Context 0x%I64x: Invalid "...
0x140409d1e  mov     cs:WdLogGlobalForLineNumber, 0D0Fh
0x140409d28  or      r8d, 0FFFFFFFFh
0x140409d2c  mov     rax, [r13+18h]
0x140409d30  mov     edx, r15d
0x140409d33  mov     [rsp+910h+var_8D8], r12
0x140409d38  mov     ecx, [rax]
0x140409d3a  mov     [rsp+910h+var_8E0], rcx
0x140409d3f  xor     ecx, ecx
0x140409d41  mov     [rsp+910h+var_8E8], r14
0x140409d46  mov     [rsp+910h+var_8F0], rsi
0x140409d4b  call    DxgkLogInternalTriageEvent
0x140409d50  lea     rcx, [rbp+7C0h+var_830]; this
0x140409d54  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x140409d59  jmp     loc_140409A2E
0x140409d5e  mov     rcx, [rax+30h]
0x140409d62  test    dword ptr [rcx+4], 1000h
0x140409d69  jnz     short loc_140409DBB
0x140409d6b  mov     ecx, ebx
0x140409d6d  call    cs:__imp_WdLogSingleEntry0
0x140409d74  nop     dword ptr [rax+rax+00h]
0x140409d79  mov     [rsp+910h+var_8D0], r12
0x140409d7e  lea     r9, aFlipstereotemp; "FlipStereoTemporaryMono and FlipStereo "...
0x140409d85  mov     [rsp+910h+var_8D8], r12
0x140409d8a  mov     eax, 0D16h
0x140409d8f  mov     [rsp+910h+var_8E0], r12
0x140409d94  or      r8d, 0FFFFFFFFh
0x140409d98  mov     [rsp+910h+var_8E8], r12
0x140409d9d  mov     edx, r15d
0x140409da0  xor     ecx, ecx
  ... truncated ...
```
