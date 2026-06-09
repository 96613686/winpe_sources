# DXGCONTEXT::PresentMultiPlaneOverlay3(_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 const *,COREDEVICEACCESS *,DXGCONTEXT * *)

- ea: `0x14033de10`
- end: `0x140340513`
- name: `?PresentMultiPlaneOverlay3@DXGCONTEXT@@QEAAJPEBU_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3@@PEAVCOREDEVICEACCESS@@PEAPEAV1@@Z`
- size: `9987`
- prototype: `__int64 __fastcall(DXGCONTEXT *__hidden this, const struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *, struct COREDEVICEACCESS *, struct DXGCONTEXT **)`
- caller_count: `3`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140245298`
- `0x1402455fc`
- `0x14033bd80`

## callees

- `0x140012380`
- `0x140015dbc`
- `0x14001a8d0`
- `0x14001ab20`
- `0x14001b890`
- `0x14001d070`
- `0x14001dd14`
- `0x14001f120`
- `0x14002d9f0`
- `0x14002da40`
- `0x140034740`
- `0x1400391ac`
- `0x1400428d4`
- `0x140049224`
- `0x14004d2a4`
- `0x14004e500`
- `0x1400556dc`
- `0x140057858`
- `0x140061d5c`
- `0x140068954`
- `0x1400a0100`
- `0x1400a0540`
- `0x140244fdc`
- `0x1403114d8`
- `0x140327864`
- `0x140327b90`
- `0x140327c10`
- `0x140327e2c`
- `0x140328310`
- `0x140329000`
- `0x14033de10`
- `0x140340858`
- `0x140340bd8`
- `0x140340c40`
- `0x140340d50`
- `0x140340d9c`
- `0x140340f18`
- `0x1403b7524`
- `0x1403c029c`
- `0x1403d014c`
- `0x1403f2f38`
- `0x140402060`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14033e823`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14033f383`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14033e823`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14033f383`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14033e817`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14033f377`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14033e817`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14033f377`
- `watchdog!WdLogSingleEntry4` at `0x14033f006`
- `watchdog!WdLogSingleEntry4` at `0x14033f5dd`
- `watchdog!WdLogSingleEntry4` at `0x14033fd6f`
- `watchdog!WdLogSingleEntry4` at `0x14033fef9`
- `watchdog!WdLogSingleEntry4` at `0x14033f006`
- `watchdog!WdLogSingleEntry4` at `0x14033f5dd`
- `watchdog!WdLogSingleEntry4` at `0x14033fd6f`
- `watchdog!WdLogSingleEntry4` at `0x14033fef9`
- `watchdog!WdLogSingleEntry2` at `0x14033e518`
- `watchdog!WdLogSingleEntry2` at `0x14033e977`
- `watchdog!WdLogSingleEntry2` at `0x14033eaf0`
- `watchdog!WdLogSingleEntry2` at `0x14033f059`
- `watchdog!WdLogSingleEntry2` at `0x14033f0a7`
- `watchdog!WdLogSingleEntry2` at `0x14033f18c`
- `watchdog!WdLogSingleEntry2` at `0x14033f1cd`
- `watchdog!WdLogSingleEntry2` at `0x14033f73d`
- `watchdog!WdLogSingleEntry2` at `0x14033fa6b`
- `watchdog!WdLogSingleEntry2` at `0x14034025b`
- `watchdog!WdLogSingleEntry2` at `0x14033e518`
- `watchdog!WdLogSingleEntry2` at `0x14033e977`
- `watchdog!WdLogSingleEntry2` at `0x14033eaf0`
- `watchdog!WdLogSingleEntry2` at `0x14033f059`
- `watchdog!WdLogSingleEntry2` at `0x14033f0a7`
- `watchdog!WdLogSingleEntry2` at `0x14033f18c`
- `watchdog!WdLogSingleEntry2` at `0x14033f1cd`
- `watchdog!WdLogSingleEntry2` at `0x14033f73d`
- `watchdog!WdLogSingleEntry2` at `0x14033fa6b`
- `watchdog!WdLogSingleEntry2` at `0x14034025b`
- `watchdog!WdLogSingleEntry3` at `0x14033e88a`
- `watchdog!WdLogSingleEntry3` at `0x14033eb96`
- `watchdog!WdLogSingleEntry3` at `0x14033ec3f`
- `watchdog!WdLogSingleEntry3` at `0x14033ec92`
- `watchdog!WdLogSingleEntry3` at `0x14033edee`
- `watchdog!WdLogSingleEntry3` at `0x14033ee3a`
- `watchdog!WdLogSingleEntry3` at `0x14033ee7e`
- `watchdog!WdLogSingleEntry3` at `0x14033f0e3`
- `watchdog!WdLogSingleEntry3` at `0x14033f12c`
- `watchdog!WdLogSingleEntry3` at `0x14033f210`
- `watchdog!WdLogSingleEntry3` at `0x14033f262`
- `watchdog!WdLogSingleEntry3` at `0x14033f3ce`
- `watchdog!WdLogSingleEntry3` at `0x14033f6e6`
- `watchdog!WdLogSingleEntry3` at `0x14033f70f`
- `watchdog!WdLogSingleEntry3` at `0x14033f98d`
- `watchdog!WdLogSingleEntry3` at `0x14033f9dc`
- `watchdog!WdLogSingleEntry3` at `0x14033fa18`
- `watchdog!WdLogSingleEntry3` at `0x14033faa2`
- `watchdog!WdLogSingleEntry3` at `0x14033fb0e`
- `watchdog!WdLogSingleEntry3` at `0x14033fce9`
- `watchdog!WdLogSingleEntry3` at `0x14033fdbc`
- `watchdog!WdLogSingleEntry3` at `0x14033fe0c`
- `watchdog!WdLogSingleEntry3` at `0x14033ff56`
- `watchdog!WdLogSingleEntry3` at `0x14033ff86`
- `watchdog!WdLogSingleEntry3` at `0x14033ffb6`
- `watchdog!WdLogSingleEntry3` at `0x14033e88a`
- `watchdog!WdLogSingleEntry3` at `0x14033eb96`
- `watchdog!WdLogSingleEntry3` at `0x14033ec3f`
- `watchdog!WdLogSingleEntry3` at `0x14033ec92`
- `watchdog!WdLogSingleEntry3` at `0x14033edee`
- `watchdog!WdLogSingleEntry3` at `0x14033ee3a`
- `watchdog!WdLogSingleEntry3` at `0x14033ee7e`
- `watchdog!WdLogSingleEntry3` at `0x14033f0e3`
- `watchdog!WdLogSingleEntry3` at `0x14033f12c`
- `watchdog!WdLogSingleEntry3` at `0x14033f210`
- `watchdog!WdLogSingleEntry3` at `0x14033f262`
- `watchdog!WdLogSingleEntry3` at `0x14033f3ce`
- `watchdog!WdLogSingleEntry3` at `0x14033f6e6`
- `watchdog!WdLogSingleEntry3` at `0x14033f70f`
- `watchdog!WdLogSingleEntry3` at `0x14033f98d`
- `watchdog!WdLogSingleEntry3` at `0x14033f9dc`
- `watchdog!WdLogSingleEntry3` at `0x14033fa18`
- `watchdog!WdLogSingleEntry3` at `0x14033faa2`
- `watchdog!WdLogSingleEntry3` at `0x14033fb0e`
- `watchdog!WdLogSingleEntry3` at `0x14033fce9`
- `watchdog!WdLogSingleEntry3` at `0x14033fdbc`
- `watchdog!WdLogSingleEntry3` at `0x14033fe0c`
- `watchdog!WdLogSingleEntry3` at `0x14033ff56`
- `watchdog!WdLogSingleEntry3` at `0x14033ff86`
- `watchdog!WdLogSingleEntry3` at `0x14033ffb6`
- `watchdog!WdLogSingleEntry0` at `0x14033e585`
- `watchdog!WdLogSingleEntry0` at `0x14033ebd9`
- `watchdog!WdLogSingleEntry0` at `0x14033eef3`
- `watchdog!WdLogSingleEntry0` at `0x14033f31a`
- `watchdog!WdLogSingleEntry0` at `0x14033f627`
- `watchdog!WdLogSingleEntry0` at `0x14033f680`
- `watchdog!WdLogSingleEntry0` at `0x14033f78f`
- `watchdog!WdLogSingleEntry0` at `0x14033f7a9`
- `watchdog!WdLogSingleEntry0` at `0x14033f805`
- `watchdog!WdLogSingleEntry0` at `0x14033f86f`
- `watchdog!WdLogSingleEntry0` at `0x14033f8e4`
- `watchdog!WdLogSingleEntry0` at `0x14033f92c`
- `watchdog!WdLogSingleEntry0` at `0x14033fff3`
- `watchdog!WdLogSingleEntry0` at `0x1403400a4`
- `watchdog!WdLogSingleEntry0` at `0x1403400fc`
- `watchdog!WdLogSingleEntry0` at `0x1403402c9`
- `watchdog!WdLogSingleEntry0` at `0x14034031a`
- `watchdog!WdLogSingleEntry0` at `0x140340377`
- `watchdog!WdLogSingleEntry0` at `0x140340453`
- `watchdog!WdLogSingleEntry0` at `0x1403404a4`
- `watchdog!WdLogSingleEntry0` at `0x14033e585`
- `watchdog!WdLogSingleEntry0` at `0x14033ebd9`
- `watchdog!WdLogSingleEntry0` at `0x14033eef3`
- `watchdog!WdLogSingleEntry0` at `0x14033f31a`
- `watchdog!WdLogSingleEntry0` at `0x14033f627`
- `watchdog!WdLogSingleEntry0` at `0x14033f680`
- `watchdog!WdLogSingleEntry0` at `0x14033f78f`
- `watchdog!WdLogSingleEntry0` at `0x14033f7a9`
- `watchdog!WdLogSingleEntry0` at `0x14033f805`
- `watchdog!WdLogSingleEntry0` at `0x14033f86f`
- `watchdog!WdLogSingleEntry0` at `0x14033f8e4`
- `watchdog!WdLogSingleEntry0` at `0x14033f92c`
- `watchdog!WdLogSingleEntry0` at `0x14033fff3`
- `watchdog!WdLogSingleEntry0` at `0x1403400a4`
- `watchdog!WdLogSingleEntry0` at `0x1403400fc`
- `watchdog!WdLogSingleEntry0` at `0x1403402c9`
- `watchdog!WdLogSingleEntry0` at `0x14034031a`
- `watchdog!WdLogSingleEntry0` at `0x140340377`
- `watchdog!WdLogSingleEntry0` at `0x140340453`
- `watchdog!WdLogSingleEntry0` at `0x1403404a4`
- `watchdog!WdLogSingleEntry5` at `0x14033fb9f`
- `watchdog!WdLogSingleEntry5` at `0x14033fd32`
- `watchdog!WdLogSingleEntry5` at `0x14033fb9f`
- `watchdog!WdLogSingleEntry5` at `0x14033fd32`
- `watchdog!WdLogSingleEntry1` at `0x1403401b6`
- `watchdog!WdLogSingleEntry1` at `0x1403401e1`
- `watchdog!WdLogSingleEntry1` at `0x14034022f`
- `watchdog!WdLogSingleEntry1` at `0x1403401b6`
- `watchdog!WdLogSingleEntry1` at `0x1403401e1`
- `watchdog!WdLogSingleEntry1` at `0x14034022f`

## string_xrefs

- `0x14033ec5a`: `ret = 0x%I64x Context 0x%I64x Source rect is outside of allocation rect, index 0x%I64x`
- `0x14033eca7`: `ret = 0x%I64x Context 0x%I64x Clip rect is outside of destination rect, index 0x%I64x`
- `0x14033ecf5`: `ClipRect outside DestRect`
- `0x14033f0f4`: `ret = 0x%I64x Context 0x%I64x Dest rect is outside of screen rect, index 0x%I64x`
- `0x14033f7a0`: `FlipStereoTemporaryMono and FlipStereo cannot be set together. STATUS_INVALID_PARAMETER`
- `0x14033f7ba`: `FlipStereoTemporaryMono cannot be used with FlipStereoPreferRight. STATUS_INVALID_PARAMETER`
- `0x14033f880`: `FlipStereoTemporaryMono and FlipStereo can only be used with stereo primary allocations. STATUS_INVALID_PARAMETER`
- `0x14033f816`: `FlipStereoTemporaryMono flag is set but the current display mode does not support it. STATUS_GRAPHICS_PRESENT_MODE_CHANGED`
- `0x14033fe21`: `ret = 0x%I64x Context 0x%I64x Clip rect is outside of virtual mode rect, index 0x%I64x`
- `0x14033feb6`: `ClipRect outside VirtualModeRect`
- `0x140340464`: `GetRenderCore()->IsCoreResourceSharedOwner() || Status == STATUS_DEVICE_REMOVED`

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
  int v9; // esi
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // ecx
  __int64 PresentPlaneCount; // rax
  __int64 VidPnSourceId; // r13
  __int64 v15; // rbx
  struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY_FLAGS::$0C0DBF3D833AEF0C1CBA798B5E28D5B2::$8C6F21D9FE8836A187EDBDD85607E321 Value; // eax
  __int64 v17; // rdx
  struct DXGALLOCATIONREFERENCE *v18; // r12
  _QWORD *v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  ADAPTER_RENDER *v23; // rcx
  bool v24; // r12
  const struct _DXGK_DISPLAYMODE_INFO *DisplayModeInfo; // rax
  LONG v26; // r9d
  LONG v27; // r10d
  D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION *pPostComposition; // rcx
  int v29; // ebx
  __int64 v30; // rax
  UINT i; // eax
  unsigned int v32; // edx
  D3DKMT_MULTIPLANE_OVERLAY3 *v33; // r13
  __int64 LayerIndex; // rsi
  __int64 v35; // r12
  struct DXGALLOCATIONREFERENCE *v36; // r9
  __int64 v37; // rbx
  const struct DXGALLOCATION *v38; // rdx
  int v39; // ecx
  int v40; // eax
  __int64 v41; // rsi
  const D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *pPlaneAttributes; // rbx
  int v43; // r8d
  int v44; // edx
  int v45; // eax
  int v46; // ecx
  LONG v47; // ecx
  LONG v48; // eax
  LONG v49; // edx
  LONG v50; // r9d
  LONG v51; // r8d
  LONG v52; // r10d
  LONG v53; // r11d
  LONG v54; // esi
  LONG v55; // r12d
  __int64 Rotation; // rcx
  UINT DirtyRectCount; // r12d
  int v58; // edx
  __int64 v59; // rax
  int v60; // r10d
  unsigned int v61; // r8d
  D3DDDI_FLIPINTERVAL_TYPE FlipInterval; // ecx
  D3DDDI_FLIPINTERVAL_TYPE v63; // r15d
  __int64 v64; // rdx
  int v65; // ecx
  struct VIDSCH_SUBMIT_DATA_BASE *v66; // rbx
  int v67; // ecx
  bool v68; // zf
  int v69; // ecx
  int v70; // eax
  int v71; // ecx
  UINT v72; // eax
  UINT v73; // ecx
  UINT v74; // eax
  UINT v75; // ecx
  UINT Duration; // eax
  D3DKMT_HANDLE hAdapter; // eax
  struct DXGGLOBAL *Global; // rax
  __int64 v79; // rdx
  __int64 v80; // rdx
  __int64 v81; // rcx
  __int64 result; // rax
  int v83; // eax
  int v84; // eax
  int v85; // r15d
  int v86; // eax
  int v87; // eax
  unsigned __int8 IsHdrEnabled; // al
  int v89; // edx
  __int64 v90; // r13
  D3DKMT_HANDLE v91; // esi
  unsigned int v92; // eax
  __int64 v93; // r8
  int v94; // ecx
  struct DXGALLOCATION *v95; // rdx
  __int64 v96; // r8
  char v97; // r8
  int v98; // esi
  RECT *pDirtyRects; // r9
  int v100; // r11d
  int *p_left; // rcx
  const D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *v102; // rbx
  D3DKMT_MULTIPLANE_OVERLAY3 *v103; // rcx
  D3DDDI_HDR_METADATA_TYPE v104; // r12d
  int Blend; // r9d
  D3DDDI_ROTATION v106; // r10d
  UINT Flags; // r11d
  UINT SDRWhiteLevel; // esi
  unsigned int v109; // r8d
  D3DDDI_COLOR_SPACE_TYPE ColorSpace; // r13d
  unsigned int v111; // eax
  unsigned int v112; // edx
  unsigned int v113; // r9d
  unsigned int v114; // r8d
  unsigned __int8 v115; // dl
  struct ADAPTER_DISPLAY *v116; // rax
  int v117; // eax
  const wchar_t *v118; // r9
  const D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *v119; // r9
  UINT v120; // ecx
  D3DDDI_HDR_METADATA_TYPE HDRMetaDataType; // edx
  __int32 v122; // edx
  __int64 v123; // rcx
  int v124; // eax
  LONG v125; // edx
  LONG v126; // r8d
  LONG v127; // eax
  LONG top; // esi
  LONG bottom; // ebx
  LONG v130; // r11d
  LONG v131; // esi
  int v132; // eax
  int v133; // ecx
  D3DKMT_MULTIPLANE_OVERLAY3 **ppPresentPlanes; // rax
  __int64 v135; // r12
  D3DKMT_MULTIPLANE_OVERLAY3 *v136; // r13
  D3DKMT_HANDLE v137; // esi
  unsigned int v138; // eax
  __int64 v139; // r8
  int v140; // ecx
  struct DXGALLOCATION *v141; // rdx
  LONG left; // r12d
  LONG right; // r11d
  LONG v144; // r8d
  int v145; // edx
  const D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *v146; // rdx
  int v147; // r10d
  int v148; // r8d
  LONG v149; // edx
  LONG v150; // r9d
  LONG v151; // eax
  LONG v152; // ecx
  const D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *v153; // rax
  __int64 v154; // rdi
  __int64 v155; // rbx
  __int64 v156; // rax
  const wchar_t *v157; // r9
  __int64 v158; // rax
  const wchar_t *v159; // r9
  int v160; // ecx
  UINT v161; // eax
  D3DKMT_MULTIPLANE_OVERLAY3 *v162; // rax
  __int64 v163; // rcx
  _QWORD *v164; // rbx
  const D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *v165; // rax
  LONG v166; // ebx
  LONG v167; // edi
  __int64 v168; // rcx
  _OWORD *pHDRMetaData; // rax
  _OWORD *v170; // rax
  const char *v171; // rdx
  D3DKMT_MULTIPLANE_OVERLAY3 **v172; // rax
  const struct _D3DKMT_MULTIPLANE_OVERLAY3 *v173; // rbx
  __int64 v174; // [rsp+30h] [rbp-120h]
  __int64 v175; // [rsp+38h] [rbp-118h]
  __int64 v176; // [rsp+40h] [rbp-110h]
  int v177; // [rsp+B0h] [rbp-A0h]
  char v178; // [rsp+B8h] [rbp-98h]
  bool v179; // [rsp+D0h] [rbp-80h]
  char v180; // [rsp+D1h] [rbp-7Fh]
  unsigned __int8 v181; // [rsp+D2h] [rbp-7Eh]
  unsigned __int8 v182; // [rsp+D3h] [rbp-7Dh]
  unsigned __int8 v183; // [rsp+D4h] [rbp-7Ch]
  UINT v184; // [rsp+D8h] [rbp-78h]
  bool v185; // [rsp+DCh] [rbp-74h]
  D3DKMT_MULTIPLANE_OVERLAY3 *v186; // [rsp+E0h] [rbp-70h] BYREF
  unsigned int v187; // [rsp+E8h] [rbp-68h]
  unsigned int v188; // [rsp+ECh] [rbp-64h]
  unsigned int v189; // [rsp+F0h] [rbp-60h]
  int v190; // [rsp+F4h] [rbp-5Ch]
  LONG v191; // [rsp+F8h] [rbp-58h]
  LONG v192; // [rsp+FCh] [rbp-54h]
  int v193; // [rsp+100h] [rbp-50h]
  int v194; // [rsp+104h] [rbp-4Ch]
  COREDEVICEACCESS *v195; // [rsp+108h] [rbp-48h]
  LONG v196; // [rsp+110h] [rbp-40h]
  LONG v197; // [rsp+114h] [rbp-3Ch]
  unsigned int v198; // [rsp+118h] [rbp-38h]
  unsigned int v199; // [rsp+11Ch] [rbp-34h]
  __int64 v200; // [rsp+120h] [rbp-30h] BYREF
  int v201; // [rsp+128h] [rbp-28h] BYREF
  __int64 v202; // [rsp+130h] [rbp-20h]
  char *v203; // [rsp+138h] [rbp-18h]
  int v204; // [rsp+140h] [rbp-10h]
  struct VIDSCH_SUBMIT_DATA_BASE *v205[2]; // [rsp+148h] [rbp-8h] BYREF
  int v206; // [rsp+158h] [rbp+8h]
  int v207; // [rsp+15Ch] [rbp+Ch]
  int v208; // [rsp+160h] [rbp+10h]
  char v209[8]; // [rsp+168h] [rbp+18h] BYREF
  struct DXGCONTEXT **v210; // [rsp+170h] [rbp+20h]
  struct _D3DKMT_PRESENT_RGNS v211; // [rsp+178h] [rbp+28h] BYREF
  struct _DXGKARG_DESCRIBEALLOCATION v212; // [rsp+198h] [rbp+48h] BYREF
  struct DXGALLOCATIONREFERENCE *v213[5]; // [rsp+1C8h] [rbp+78h] BYREF
  int v214; // [rsp+1F0h] [rbp+A0h]
  struct _DXGKARG_PRESENT v215; // [rsp+200h] [rbp+B0h] BYREF
  _D3DKMT_PRESENT v216; // [rsp+2B0h] [rbp+160h] BYREF
  enum _D3DDDIFORMAT v217[4]; // [rsp+890h] [rbp+740h] BYREF
  __int128 v218; // [rsp+8A0h] [rbp+750h]
  __int64 v219; // [rsp+8B0h] [rbp+760h]
  unsigned __int8 v220[16]; // [rsp+8B8h] [rbp+768h] BYREF

  v210 = a4;
  v5 = *((_QWORD *)this + 2);
  v195 = a3;
  v7 = *(_QWORD *)(v5 + 1896);
  v8 = *(ADAPTER_RENDER **)(v5 + 16);
  v9 = *(_DWORD *)(v7 + 444) & 0x100;
  v208 = v9;
  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(v8) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 3197;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner()",
      3197,
      0,
      0,
      0,
      0);
  }
  v10 = *((_QWORD *)this + 2);
  v11 = *(_QWORD *)(*(_QWORD *)(v10 + 16) + 16LL);
  if ( (v11 || !v9) && *(_QWORD *)(v10 + 1896) != v11 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 3198;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"(!GetRenderAdapter() && IsIndirectDisplayDevice) || (GetDisplayAdapter() == GetRenderAdapter())",
      3198,
      0,
      0,
      0,
      0);
  }
  *((_BYTE *)this + 435) = 1;
  if ( v9 )
    v12 = 1;
  else
    v12 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 16LL) + 3056LL);
  PresentPlaneCount = a2->PresentPlaneCount;
  v187 = v12;
  if ( (unsigned int)PresentPlaneCount > v12 )
  {
    LODWORD(v41) = -1073741811;
    WdLogSingleEntry3(3, PresentPlaneCount, v12, -1073741811);
    WdLogGlobalForLineNumber = 3215;
    return (unsigned int)v41;
  }
  VidPnSourceId = a2->VidPnSourceId;
  v188 = VidPnSourceId;
  v15 = (unsigned int)VidPnSourceId;
  if ( !v9 )
  {
    v117 = DXGCONTEXT::CheckDevicePresentSettings(this, 1, 0, 1, VidPnSourceId);
    LODWORD(v41) = v117;
    if ( v117 < 0 )
    {
      WdLogSingleEntry3(3, v117, this, (unsigned int)VidPnSourceId);
      WdLogGlobalForLineNumber = 3234;
      return (unsigned int)v41;
    }
    if ( (*(_DWORD *)(*((_QWORD *)this + 2) + 4 * VidPnSourceId + 1240) & 0x200) == 0 )
    {
      WdLogSingleEntry3(3, -1071775719, this, (unsigned int)VidPnSourceId);
      result = 3223191577LL;
      WdLogGlobalForLineNumber = 3243;
      return result;
    }
  }
  Value = (struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY_FLAGS::$0C0DBF3D833AEF0C1CBA798B5E28D5B2::$8C6F21D9FE8836A187EDBDD85607E321)a2->Flags.Value;
  if ( (*(_BYTE *)&Value & 2) != 0 || (*(_BYTE *)&Value & 1) != 0 )
  {
    if ( a2->PresentPlaneCount > 1 )
    {
      LODWORD(v41) = -1073741811;
      WdLogSingleEntry2(2, this);
      WdLogGlobalForLineNumber = 3258;
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
      return (unsigned int)v41;
    }
    if ( (a2->Flags.Value & 2) != 0 && (*(_BYTE *)&Value & 1) != 0 )
    {
      WdLogSingleEntry0(2);
      v156 = 3265;
      v157 = L"FlipStereoTemporaryMono and FlipStereo cannot be set together. STATUS_INVALID_PARAMETER";
    }
    else
    {
      if ( (*(_BYTE *)&Value & 6) != 6 )
      {
        DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v186, 0);
        ppPresentPlanes = a2->ppPresentPlanes;
        v200 = *(_QWORD *)(*((_QWORD *)this + 2) + 40LL);
        v135 = v200 + 248;
        v136 = *ppPresentPlanes;
        v137 = *(*ppPresentPlanes)->pAllocationList;
        DXGPUSHLOCK::AcquireShared((DXGPUSHLOCK *)(v200 + 248));
        v138 = (v137 >> 6) & 0xFFFFFF;
        if ( v138 < *(_DWORD *)(v200 + 296)
          && (v139 = *(_QWORD *)(v200 + 280), ((v137 >> 25) & 0x60) == (*(_BYTE *)(v139 + 16LL * v138 + 8) & 0x60))
          && (*(_DWORD *)(v139 + 16LL * v138 + 8) & 0x2000) == 0
          && (v140 = *(_DWORD *)(v139 + 16LL * v138 + 8) & 0x1F) != 0 )
        {
          if ( v140 == 5 )
          {
            v141 = *(struct DXGALLOCATION **)(v139 + 16LL * v138);
          }
          else
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 318;
            DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
            v141 = 0;
          }
        }
        else
        {
          v141 = 0;
        }
        DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v201, v141);
        _InterlockedDecrement((volatile signed __int32 *)(v135 + 16));
        ExReleasePushLockSharedEx(v135, 0);
        KeLeaveCriticalRegion();
        DXGALLOCATIONREFERENCE::MoveAssign(&v186, &v201);
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v201);
        if ( v186 )
        {
          if ( (v186->pPlaneAttributes->SrcRect.left & 0x1000) != 0 )
          {
            v160 = *((_DWORD *)ADAPTER_DISPLAY::GetDisplayModeInfo(
                                 *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) + 3232LL),
                                 a2->VidPnSourceId)
                   + 10);
            if ( (v160 & 0x10) != 0 )
            {
              if ( (v160 & 0x20) != 0 || (*(_BYTE *)&a2->Flags.0 & 2) == 0 )
              {
                DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v186);
                LODWORD(VidPnSourceId) = v15;
                goto LABEL_12;
              }
              WdLogSingleEntry0(2);
              v158 = 3302;
              v159 = L"FlipStereoTemporaryMono flag is set but the current display mode does not support it. STATUS_GRAPHI"
                      "CS_PRESENT_MODE_CHANGED";
            }
            else
            {
              WdLogSingleEntry0(2);
              v158 = 3296;
              v159 = L"Stereo flag is set but the current display mode does not support stereo. STATUS_GRAPHICS_PRESENT_MODE_CHANGED";
            }
            WdLogGlobalForLineNumber = v158;
            DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v159, v158, 0, 0, 0, 0);
            LODWORD(v41) = -1071775739;
          }
          else
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 3289;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"FlipStereoTemporaryMono and FlipStereo can only be used with stereo primary allocations. STA"
                             "TUS_INVALID_PARAMETER",
              3289,
              0,
              0,
              0,
              0);
            LODWORD(v41) = -1073741811;
          }
        }
        else
        {
          LODWORD(v41) = -1073741811;
          WdLogSingleEntry3(2, -1073741811, this, *v136->pAllocationList);
          WdLogGlobalForLineNumber = 3282;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"ret = 0x%I64x Context 0x%I64x: Invalid allocation handle for plane 0 specified: 0x%I64x",
            -1073741811,
            (__int64)this,
            *v136->pAllocationList,
            0,
            0);
        }
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v186);
        return (unsigned int)v41;
      }
      WdLogSingleEntry0(2);
      v156 = 3271;
      v157 = L"FlipStereoTemporaryMono cannot be used with FlipStereoPreferRight. STATUS_INVALID_PARAMETER";
    }
    WdLogGlobalForLineNumber = v156;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v157, v156, 0, 0, 0, 0);
    return -1073741811;
  }
LABEL_12:
  v17 = a2->ContextCount * v187;
  v213[0] = 0;
  v214 = 0;
  PagedPoolArray<DXGALLOCATIONREFERENCE,4>::AllocateElements(v213, v17);
  v18 = v213[0];
  if ( !v213[0] )
  {
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 3314;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to allocate memory for MPO allocation references",
      3314,
      0,
      0,
      0,
      0);
    goto LABEL_94;
  }
  v19 = (_QWORD *)*((_QWORD *)this + 2);
  v20 = v19[237];
  if ( v20 == *(_QWORD *)(v19[2] + 16LL) )
  {
    ADAPTER_DISPLAY::GetAllocationsForAllPlanes(*(ADAPTER_DISPLAY **)(v20 + 3232), VidPnSourceId, v213[0], v187);
  }
  else
  {
    DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
      (DXGAUTOPUSHLOCKEXCLUSIVE *)&v211,
      (struct DXGPUSHLOCK *const)(v19 + 38));
    DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(
      (DXGALLOCATIONREFERENCE *)&v186,
      (struct DXGALLOCATION *)v19[v15 + 131]);
    DXGALLOCATIONREFERENCE::MoveAssign(v18, &v186);
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v186);
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)&v211);
  }
  v21 = *((_QWORD *)this + 2);
  v205[0] = *(struct VIDSCH_SUBMIT_DATA_BASE **)v213[0];
  ADAPTER_DISPLAY::GetDDIEnabledPlanes(*(ADAPTER_DISPLAY **)(*(_QWORD *)(v21 + 1896) + 3232LL), VidPnSourceId, v220);
  v22 = *((_QWORD *)this + 2);
  *(_OWORD *)v217 = 0;
  v219 = 0;
  v23 = *(ADAPTER_RENDER **)(v22 + 16);
  v218 = 0;
  v24 = !ADAPTER_RENDER::IsMultiPlaneOverlaySupported(v23)
     || *(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) != *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 16LL);
  v179 = v24;
  DisplayModeInfo = ADAPTER_DISPLAY::GetDisplayModeInfo(
                      *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) + 3232LL),
                      VidPnSourceId);
  if ( !DisplayModeInfo )
  {
    v41 = -1073741811;
    WdLogSingleEntry3(2, -1073741811, this, v15);
    v176 = 0;
    v118 = L"ret = 0x%I64x Context 0x%I64x Failed to obtain display mode, VidPnSourceId 0x%I64x";
    v175 = 0;
    WdLogGlobalForLineNumber = 3343;
    goto LABEL_161;
  }
  v26 = *(_DWORD *)DisplayModeInfo;
  v27 = *((_DWORD *)DisplayModeInfo + 1);
  pPostComposition = a2->pPostComposition;
  v183 = 0;
  v199 = 0;
  v198 = 0;
  if ( pPostComposition )
  {
    if ( pPostComposition->Flags.Value )
    {
      LODWORD(v41) = -1073741811;
      WdLogSingleEntry3(3, this, pPostComposition->Flags.Value, -1073741811);
      WdLogGlobalForLineNumber = 3358;
      goto LABEL_95;
    }
    if ( pPostComposition->Rotation != D3DDDI_ROTATION_IDENTITY )
    {
      LODWORD(v41) = -1073741811;
      WdLogSingleEntry3(3, this, pPostComposition->Rotation, -1073741811);
      WdLogGlobalForLineNumber = 3364;
      goto LABEL_95;
    }
    left = pPostComposition->SrcRect.left;
    right = pPostComposition->SrcRect.right;
    v196 = left;
    v191 = right;
    if ( left >= right
      || (top = pPostComposition->SrcRect.top,
          bottom = pPostComposition->SrcRect.bottom,
          v197 = top,
          v192 = bottom,
          top >= bottom) )
    {
      LODWORD(v41) = -1073741811;
      WdLogSingleEntry2(3, this);
      WdLogGlobalForLineNumber = 3370;
      goto LABEL_95;
    }
    v144 = pPostComposition->DstRect.right;
    v145 = pPostComposition->DstRect.left;
    if ( v145 >= v144 || (v127 = pPostComposition->DstRect.bottom, pPostComposition->DstRect.top >= v127) )
    {
      LODWORD(v41) = -1073741811;
      WdLogSingleEntry2(3, this);
      WdLogGlobalForLineNumber = 3376;
      goto LABEL_95;
    }
    if ( v145 < 0 || v26 < v144 || v27 < v127 || pPostComposition->DstRect.top < 0 )
    {
      LODWORD(v41) = -1073741811;
      WdLogSingleEntry2(3, this);
      WdLogGlobalForLineNumber = 3382;
      goto LABEL_95;
    }
    if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 16LL) + 3161LL) || v179 )
    {
      LODWORD(v41) = -1073741811;
      WdLogSingleEntry2(3, -1073741811);
      WdLogGlobalForLineNumber = 3393;
      goto LABEL_95;
    }
    if ( left || right != v26 || top || bottom != v27 )
    {
      v183 = 1;
      v199 = right - left;
      v198 = bottom - top;
    }
  }
  else
  {
    v196 = 0;
    v197 = 0;
    v191 = v26;
    v192 = v27;
    if ( v24 )
    {
      v161 = a2->PresentPlaneCount;
      if ( v161 != 1 )
      {
        v41 = -1073741811;
        WdLogSingleEntry3(2, -1073741811, this, v161);
        v176 = 0;
        v118 = L"0x%I64x Context 0x%I64x PresentMPO fails because the driver doesn't support MPO and 0x%I64x planes are specified";
        WdLogGlobalForLineNumber = 3427;
        v175 = 0;
        v174 = a2->PresentPlaneCount;
        goto LABEL_162;
      }
      v162 = *a2->ppPresentPlanes;
      if ( v162->LayerIndex || (v162->InputFlags.Value & 1) == 0 )
      {
        v41 = -1073741811;
        WdLogSingleEntry3(2, -1073741811, this, 1);
        v176 = 0;
        v118 = L"0x%I64x Context 0x%I64x PresentMPO fails because the driver doesn't support MPO and plane 0 is not enabled";
        WdLogGlobalForLineNumber = 3436;
        v175 = 0;
        v174 = a2->PresentPlaneCount;
        goto LABEL_162;
      }
    }
  }
  v181 = 0;
  v194 = -1;
  v29 = 0;
  v190 = 0;
  v193 = -256;
  v30 = *((_QWORD *)this + 2);
  v182 = 0;
  v180 = 0;
  v204 = 0;
  v185 = *(int *)(*(_QWORD *)(*(_QWORD *)(v30 + 16) + 16LL) + 3116LL) >= 3000
      || *((_BYTE *)DXGGLOBAL::GetGlobal() + 304896);
  for ( i = 0; ; i = v184 + 1 )
  {
    v184 = i;
    if ( i >= a2->PresentPlaneCount )
    {
      v63 = D3DDDI_FLIPINTERVAL_ONE;
      if ( !v204 )
      {
        if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 16LL) + 3161LL) )
        {
          v63 = D3DDDI_FLIPINTERVAL_IMMEDIATE;
        }
        else
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 3909;
        }
      }
      if ( !v182 && !v181 && !v180 )
      {
        WdLogSingleEntry2(4, 0);
        WdLogGlobalForLineNumber = 3920;
        LODWORD(v41) = 0;
        goto LABEL_95;
      }
      memset(&v215, 0, sizeof(v215));
      v64 = *((_QWORD *)this + 2);
      v65 = 4;
      v215.FlipInterval = v63;
      if ( !v179 )
        v65 = 4100;
      v215.Flags.Value = v65
                       ^ ((unsigned __int16)v65
                        ^ (unsigned __int16)((unsigned __int16)*(_DWORD *)&a2->Flags.0 << 8))
                       & 0x700
                       | 8;
      CVidSchSubmitData::CVidSchSubmitData((CVidSchSubmitData *)v205, *(struct ADAPTER_RENDER **)(v64 + 16), 1);
      v66 = v205[0];
      if ( v205[0] )
      {
        *(_DWORD *)v205[0] |= 0x30020u;
        v67 = *(_DWORD *)v66 | 1;
        v68 = (_BYTE)v193 == 0;
        *((_DWORD *)v66 + 28) = a2->PresentCount;
        if ( !v68 )
          v67 |= 0x400000u;
        v69 = v67 | 4;
        *(_DWORD *)v66 = v69;
        if ( !v179 && a2->ContextCount <= 1 )
        {
          v69 |= 0x800000u;
          *(_DWORD *)v66 = v69;
        }
        v70 = v69 ^ ((unsigned __int8)v69 ^ (unsigned __int8)(a2->Flags.Value >> 1)) & 8;
        *(_DWORD *)v66 = v70;
        v71 = v70 ^ ((unsigned __int8)v70 ^ (unsigned __int8)(a2->Flags.Value >> 1)) & 0x10;
        *(_DWORD *)v66 = v71;
        v72 = v71 ^ (v71 ^ (a2->Flags.Value << 19)) & 0x80000;
        *(_DWORD *)v66 = v72;
        v73 = v72 ^ (v72 ^ (a2->Flags.Value << 19)) & 0x100000;
        *(_DWORD *)v66 = v73;
        v74 = v73 ^ (v73 ^ (a2->Flags.Value << 19)) & 0x200000;
        *(_DWORD *)v66 = v74;
        v75 = v74 ^ (v74 ^ (a2->Flags.Value << 21)) & 0x20000000;
        *(_DWORD *)v66 = v75;
        if ( (a2->Flags.Value & 0x40) != 0 )
          Duration = a2->Duration;
        else
          Duration = 0;
        *((_DWORD *)v66 + 36) = Duration;
        if ( (a2->Flags.Value & 0x40) != 0 )
          hAdapter = a2[1].hAdapter;
        else
          hAdapter = 1;
        *((_DWORD *)v66 + 38) = hAdapter;
        *((_DWORD *)v66 + 29) = VidPnSourceId;
        *((_DWORD *)v66 + 31) = v63;
        *((_DWORD *)v66 + 30) = 5;
        if ( (a2->Flags.Value & 0x200) != 0 && v63 == D3DDDI_FLIPINTERVAL_IMMEDIATE )
          *(_DWORD *)v66 = v75 | 0x10000000;
        Global = DXGGLOBAL::GetGlobal();
        v79 = *((_QWORD *)this + 2);
        if ( *((_BYTE *)Global + 304896)
          || (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v79 + 1896) + 3232LL) + 24LL) & 0x10) != 0 )
        {
          IsHdrEnabled = ADAPTER_DISPLAY::IsHdrEnabled(
                           *(ADAPTER_DISPLAY **)(*(_QWORD *)(v79 + 1896) + 3232LL),
                           VidPnSourceId);
          v89 = *(_DWORD *)v66;
          if ( IsHdrEnabled )
          {
            v120 = v89 ^ (v89 ^ (a2->Flags.Value << 23)) & 0x40000000;
            *(_DWORD *)v66 = v120;
            *((_DWORD *)v66 + 90) = a2->HDRMetaDataType;
            HDRMetaDataType = a2->HDRMetaDataType;
            if ( (v120 & 0x40000000) != 0 )
            {
              if ( HDRMetaDataType )
              {
                v122 = HDRMetaDataType - 1;
                if ( v122 )
                {
                  if ( v122 == 1 )
                  {
                    pHDRMetaData = a2->pHDRMetaData;
                    *(_OWORD *)((char *)v66 + 364) = *pHDRMetaData;
                    *(_OWORD *)((char *)v66 + 380) = pHDRMetaData[1];
                    *(_OWORD *)((char *)v66 + 396) = pHDRMetaData[2];
                    *(_OWORD *)((char *)v66 + 412) = pHDRMetaData[3];
                    *(_QWORD *)((char *)v66 + 428) = *((_QWORD *)pHDRMetaData + 8);
                  }
                  else
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 4026;
                    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"FALSE", 4026, 0, 0, 0, 0);
                    *(_DWORD *)v66 &= ~0x40000000u;
                  }
                }
                else
                {
                  v170 = a2->pHDRMetaData;
                  *(_OWORD *)((char *)v66 + 364) = *v170;
                  *(_OWORD *)((char *)v66 + 376) = *(_OWORD *)((char *)v170 + 12);
                }
              }
            }
            else
            {
              if ( (unsigned int)HDRMetaDataType > D3DDDI_HDR_METADATA_TYPE_HDR10PLUS )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 4036;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"D3DDDI_HDR_METADATA_TYPE_HDR10 == pArgs->HDRMetaDataType || D3DDDI_HDR_METADATA_TYPE_HDR"
                                 "10PLUS == pArgs->HDRMetaDataType || D3DDDI_HDR_METADATA_TYPE_NONE == pArgs->HDRMetaDataType",
                  4036,
                  0,
                  0,
                  0,
                  0);
              }
              if ( a2->pHDRMetaData || a2->HDRMetaDataSize )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 4039;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"NULL == pArgs->pHDRMetaData && NULL == pArgs->HDRMetaDataSize",
                  4039,
                  0,
                  0,
                  0,
                  0);
              }
              *(_DWORD *)v66 |= 0x40000000u;
              if ( a2->HDRMetaDataType == D3DDDI_HDR_METADATA_TYPE_HDR10 )
              {
                *((_DWORD *)v66 + 90) = 134217729;
              }
              else if ( a2->HDRMetaDataType == D3DDDI_HDR_METADATA_TYPE_HDR10PLUS )
              {
                *((_DWORD *)v66 + 90) = -2147483646;
              }
            }
          }
          else
          {
            *((_DWORD *)v66 + 90) = 0;
            *(_DWORD *)v66 = v89 | 0x40000000;
          }
        }
        if ( a2->pPostComposition )
        {
          *(_DWORD *)v66 |= 0x80000000;
          *(RECT *)((char *)v66 + 436) = a2->pPostComposition->SrcRect;
          *(RECT *)((char *)v66 + 452) = a2->pPostComposition->DstRect;
        }
        v80 = *((_QWORD *)this + 2);
        v81 = *(_QWORD *)(v80 + 1896);
        if ( v81 != *(_QWORD *)(*(_QWORD *)(v80 + 16) + 16LL) )
        {
          if ( !v81 )
          {
            WdLogSingleEntry2(1, v80);
            WdLogGlobalForLineNumber = 4208;
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
            PagedPoolArray<DXGALLOCATIONREFERENCE,4>::~PagedPoolArray<DXGALLOCATIONREFERENCE,4>(v213);
            return -1073741811;
          }
          v172 = a2->ppPresentPlanes;
          v173 = *v172;
          if ( (*v172)->LayerIndex )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 4190;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pPlane0->LayerIndex == 0", 4190, 0, 0, 0, 0);
          }
          memset(&v216, 0, sizeof(v216));
          memset(&v211, 0, sizeof(v211));
          ConvertMPOThunkToLegacyPresentThunk(&v216, &v211, a2, v173);
          LODWORD(v41) = DXGCONTEXT::DisplayOnlyPresent(
                           this,
                           &v216,
                           *(struct DXGALLOCATION **)v213[0],
                           VidPnSourceId,
                           &v215,
                           v195);
          v113 = 0;
          v114 = 0;
          v115 = 0;
          v116 = *(struct ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) + 3232LL);
          goto LABEL_144;
        }
        v83 = *(_DWORD *)(v80 + 4LL * (unsigned int)VidPnSourceId + 1832);
        if ( *((_DWORD *)v66 + 30) == v83 || !v83 )
          goto LABEL_99;
        if ( (a2->Flags.Value & 8) != 0 )
        {
          WdLogSingleEntry1(4);
          WdLogGlobalForLineNumber = 4091;
          CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v205);
          LODWORD(v41) = -1071775739;
          goto LABEL_95;
        }
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 4099;
        COREDEVICEACCESS::Release(v195);
        DXGDEVICE::FlushScheduler(*((_QWORD *)this + 2), 3, (unsigned int)VidPnSourceId);
        v85 = COREDEVICEACCESS::AcquireShared(v195, 0);
        if ( v85 >= 0 )
        {
LABEL_99:
          v84 = DXGCONTEXT::WaitForQueuedPresentLimit(this, VidPnSourceId, (a2->Flags.Value & 8) == 0, v195);
          v85 = v84;
          if ( v84 < 0 )
          {
            WdLogSingleEntry2(4, v84);
            WdLogGlobalForLineNumber = 4121;
          }
          else
          {
            v86 = DXGCONTEXT::CheckDevicePresentSettings(this, 1, 0, 1, VidPnSourceId);
            v85 = v86;
            if ( v86 >= 0 )
            {
              if ( *((_QWORD *)this + 45) )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 4149;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"m_pPresentDmaBuffer == NULL",
                  4149,
                  0,
                  0,
                  0,
                  0);
              }
              LODWORD(v41) = DXGCONTEXT::SubmitPresentMultiPlaneOverlays3(
                               this,
                               a2,
                               v182,
                               v181,
                               v180,
                               v213[0],
                               v220,
                               &v215,
                               v66,
                               v210);
              if ( (int)v41 < 0 )
                goto LABEL_104;
              if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) + 3232LL) + 128LL)
                             + 4024LL * (unsigned int)VidPnSourceId
                             + 1072) == -1 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 4166;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"!NT_SUCCESS(Status) || (GetDisplayAdapter(VidPnSourceId)->GetDisplayCore()->MapVidPnSour"
                                 "ceToVidPnTarget(VidPnSourceId) != D3DDDI_ID_UNINITIALIZED)",
                  4166,
                  0,
                  0,
                  0,
                  0);
              }
              DXGCONTEXT::UpdateDisplayStateForFullWDDMDevice(this, a2, v213[0], v217, v194, *((_DWORD *)v66 + 34));
              v113 = v198;
              v114 = v199;
              v115 = v183;
              *(_DWORD *)(*((_QWORD *)this + 2) + 4LL * (unsigned int)VidPnSourceId + 1832) = *((_DWORD *)v66 + 30);
              v116 = *(struct ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) + 3232LL);
LABEL_144:
              UpdatePostComposition(VidPnSourceId, v115, v114, v113, v116);
LABEL_104:
              if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(*(ADAPTER_RENDER **)(*((_QWORD *)this + 2) + 16LL))
                && (_DWORD)v41 != -1073741130 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 4213;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner() || Status == STATUS_DEVICE_REMOVED",
                  4213,
                  0,
                  0,
                  0,
                  0);
              }
              if ( *((_QWORD *)this + 45) )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 4214;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"m_pPresentDmaBuffer == NULL",
                  4214,
                  0,
                  0,
                  0,
                  0);
              }
              CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v205);
              goto LABEL_95;
            }
            WdLogSingleEntry2(4, v86);
            WdLogGlobalForLineNumber = 4132;
            if ( v85 == -1071774920 )
            {
              DXGCONTEXT::UpdateDisplayStateForFullWDDMDevice(this, a2, v213[0], v217, v194, *((_DWORD *)v66 + 34));
              *(_DWORD *)(*((_QWORD *)this + 2) + 4LL * (unsigned int)VidPnSourceId + 1832) = *((_DWORD *)v66 + 30);
              CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v205);
              LODWORD(v41) = 0;
              goto LABEL_95;
            }
          }
        }
        else
        {
          WdLogSingleEntry1(4);
          WdLogGlobalForLineNumber = 4107;
          COREDEVICEACCESS::AcquireSharedUncheck(v195, v171);
        }
        CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v205);
        LODWORD(v41) = v85;
        goto LABEL_95;
      }
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 3945;
      DxgkLogInternalTriageEvent(0, 262145, -1, (unsigned int)L"Failed to allocate VidSchSubmitData", 3945, 0, 0, 0, 0);
      CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v205);
LABEL_94:
      LODWORD(v41) = -1073741801;
      goto LABEL_95;
    }
    v32 = v187;
    v33 = a2->ppPresentPlanes[i];
    v186 = v33;
    LayerIndex = v33->LayerIndex;
    v189 = LayerIndex;
    v35 = (unsigned int)LayerIndex;
    if ( (unsigned int)LayerIndex >= v187 )
    {
      LODWORD(v41) = -1073741811;
      WdLogSingleEntry3(3, this, v35, -1073741811);
      WdLogGlobalForLineNumber = 3458;
      goto LABEL_95;
    }
    _mm_lfence();
    v201 = 1 << LayerIndex;
    if ( (v29 & (1 << LayerIndex)) != 0 )
    {
      LODWORD(v41) = -1073741811;
      WdLogSingleEntry3(3, this, v35, -1073741811);
      WdLogGlobalForLineNumber = 3465;
      goto LABEL_95;
    }
    if ( (v33->InputFlags.Value & 1) == 0 )
    {
      v164 = (_QWORD *)((char *)v213[0] + 8 * LayerIndex);
      if ( *v164 || v220[LayerIndex] )
        ++v180;
      DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v200, 0);
      DXGALLOCATIONREFERENCE::MoveAssign(v164, &v200);
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v200);
      goto LABEL_67;
    }
    v36 = v213[0];
    if ( *((_QWORD *)v213[0] + LayerIndex) || v220[LayerIndex] )
      ++v181;
    else
      ++v182;
    v37 = 0;
    while ( (unsigned int)v37 < v33->AllocationCount )
    {
      v202 = (unsigned int)LayerIndex + v32 * (_DWORD)v37;
      v203 = (char *)v36 + 8 * v202;
      v90 = *(_QWORD *)(*((_QWORD *)this + 2) + 40LL);
      v91 = v186->pAllocationList[v37];
      DXGPUSHLOCK::AcquireShared((DXGPUSHLOCK *)(v90 + 248));
      v92 = (v91 >> 6) & 0xFFFFFF;
      if ( v92 < *(_DWORD *)(v90 + 296) )
      {
        v93 = *(_QWORD *)(v90 + 280);
        if ( ((v91 >> 25) & 0x60) == (*(_BYTE *)(v93 + 16LL * v92 + 8) & 0x60)
          && (*(_DWORD *)(v93 + 16LL * v92 + 8) & 0x2000) == 0 )
        {
          v94 = *(_DWORD *)(v93 + 16LL * v92 + 8) & 0x1F;
          if ( v94 )
          {
            if ( v94 == 5 )
            {
              v95 = *(struct DXGALLOCATION **)(v93 + 16LL * v92);
              goto LABEL_120;
            }
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 318;
            DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
          }
        }
      }
      v95 = 0;
LABEL_120:
      DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v209, v95);
      _InterlockedDecrement((volatile signed __int32 *)(v90 + 264));
      ExReleasePushLockSharedEx(v90 + 248, 0);
      KeLeaveCriticalRegion();
      DXGALLOCATIONREFERENCE::MoveAssign(v203, v209);
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v209);
      v36 = v213[0];
      v96 = *((_QWORD *)v213[0] + v202);
      if ( !v96 )
      {
        LODWORD(v41) = -1073741811;
        WdLogSingleEntry3(3, -1073741811, this, v186->pAllocationList[v37]);
        WdLogGlobalForLineNumber = 3495;
        goto LABEL_95;
      }
      if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v96 + 8) + 16LL) + 16LL) != *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2)
                                                                                                 + 16LL)
                                                                                     + 16LL) )
      {
        LODWORD(v41) = -1073741811;
        WdLogSingleEntry3(2, *((_QWORD *)this + 2), v96, -1073741811);
        WdLogGlobalForLineNumber = 3504;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Device 0x%p does not match allocation 0x%p owner, returning 0x%I64x",
          *((_QWORD *)this + 2),
          *((_QWORD *)v213[0] + (unsigned int)v35 + v187 * (_DWORD)v37),
          -1073741811,
          0,
          0);
        goto LABEL_95;
      }
      v33 = v186;
      v32 = v187;
      v37 = (unsigned int)(v37 + 1);
      LODWORD(LayerIndex) = v35;
    }
    _mm_lfence();
    v38 = (const struct DXGALLOCATION *)*((_QWORD *)v213[0] + v35);
    v39 = *(_DWORD *)(*((_QWORD *)v38 + 6) + 4LL);
    if ( (v39 & 0x2000) == 0 )
    {
      if ( (v39 & 0xB) != 0 )
      {
        v87 = v194;
        if ( (v39 & 1) != 0 )
          v87 = LayerIndex;
        v194 = v87;
        goto LABEL_33;
      }
      if ( v208 && (a2->Flags.Value & 0x400) != 0 )
        goto LABEL_33;
      _mm_lfence();
      v163 = (unsigned int)LayerIndex;
      v41 = -1073741811;
      WdLogSingleEntry5(
        2,
        -1073741811,
        this,
        *((_QWORD *)v213[0] + v163),
        *(_QWORD *)(*((_QWORD *)v213[0] + v163) + 48LL),
        *v33->pAllocationList);
      WdLogGlobalForLineNumber = 3602;
      v118 = L"0x%I64x 0x%I64x Source of Flip must be primary 0x%I64x 0x%I64x 0x%I64x";
      v176 = *v33->pAllocationList;
      v175 = *(_QWORD *)(*((_QWORD *)v213[0] + (unsigned int)v35) + 48LL);
      v174 = *((_QWORD *)v213[0] + (unsigned int)v35);
      goto LABEL_162;
    }
    if ( (v39 & 0x20) != 0 )
      goto LABEL_33;
    if ( !DXGDEVICE::IsDirectFlipAllocationRequestedPinned(*((DXGDEVICE **)this + 2), v38) )
    {
      _mm_lfence();
      WdLogSingleEntry5(
        4,
        -1071775739,
        this,
        *((_QWORD *)v213[0] + v35),
        *(_QWORD *)(*((_QWORD *)v213[0] + v35) + 48LL),
        *v33->pAllocationList);
      WdLogGlobalForLineNumber = 3537;
LABEL_305:
      LODWORD(v41) = -1071775720;
      goto LABEL_95;
    }
    _mm_lfence();
    if ( !VIDMM_EXPORT::VidMmIsAllocationPinned(
            *(VIDMM_EXPORT **)(*(_QWORD *)(v123 + 16) + 760LL),
            *(struct VIDMM_GLOBAL **)(*(_QWORD *)(v123 + 16) + 768LL),
            *(struct VIDMM_MULTI_ALLOC **)(*((_QWORD *)v213[0] + v35) + 24LL)) )
    {
      _mm_lfence();
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        *(_QWORD *)(*((_QWORD *)this + 2) + 16LL),
        *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 16LL) + 3116LL),
        0,
        "DFlip allocation unpinned");
      v124 = VIDMM_EXPORT::VidMmPinAllocation(
               *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 760LL),
               *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 768LL),
               *(struct VIDMM_MULTI_ALLOC **)(*((_QWORD *)v213[0] + v35) + 24LL),
               0,
               0);
      if ( v124 < 0 )
      {
        _mm_lfence();
        WdLogSingleEntry4(
          4,
          *((_QWORD *)v213[0] + (unsigned int)LayerIndex),
          *(_QWORD *)(*((_QWORD *)v213[0] + (unsigned int)LayerIndex) + 48LL),
          *v33->pAllocationList,
          v124);
        WdLogGlobalForLineNumber = 3569;
        goto LABEL_305;
      }
    }
LABEL_33:
    _mm_lfence();
    memset(&v212, 0, sizeof(v212));
    v212.hAllocation = *(HANDLE *)(*(_QWORD *)(*((_QWORD *)v213[0] + v35) + 48LL) + 16LL);
    v40 = ADAPTER_RENDER::DdiDescribeAllocation(*(ADAPTER_RENDER **)(*((_QWORD *)this + 2) + 16LL), &v212);
    v41 = v40;
    if ( v40 < 0 )
    {
      _mm_lfence();
      WdLogSingleEntry4(
        2,
        v40,
        this,
        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v213[0] + v35) + 48LL) + 16LL),
        *((_QWORD *)v213[0] + v35));
      WdLogGlobalForLineNumber = 3615;
      v176 = 0;
      v118 = L"ret = 0x%I64x Context 0x%I64x: DdiDescribeAllocation failed 0x%I64x 0x%I64x";
      v175 = *((_QWORD *)v213[0] + (unsigned int)v35);
      v174 = *(_QWORD *)(*(_QWORD *)(v175 + 48) + 16LL);
      goto LABEL_162;
    }
    pPlaneAttributes = v33->pPlaneAttributes;
    v217[v35] = v212.Format;
    v43 = pPlaneAttributes->SrcRect.right;
    v44 = pPlaneAttributes->SrcRect.left;
    v207 = v43;
    v206 = v44;
    if ( v44 >= v43 || (v45 = pPlaneAttributes->SrcRect.top, v46 = pPlaneAttributes->SrcRect.bottom, v45 >= v46) )
    {
      v15 = v184;
      v41 = -1073741811;
      WdLogSingleEntry3(2, -1073741811, this, v184);
      v176 = 0;
      v175 = 0;
      WdLogGlobalForLineNumber = 3627;
      goto LABEL_166;
    }
    if ( v44 < 0
      || (LODWORD(v202) = v212.Width, (int)v212.Width < v43)
      || v45 < 0
      || (LODWORD(v203) = v212.Height, (int)v212.Height < v46) )
    {
      v15 = v184;
      v41 = -1073741811;
      WdLogSingleEntry3(2, -1073741811, this, v184);
      WdLogGlobalForLineNumber = 3635;
LABEL_160:
      v176 = 0;
      v118 = L"ret = 0x%I64x Context 0x%I64x Source rect is outside of allocation rect, index 0x%I64x";
      v175 = 0;
      goto LABEL_161;
    }
    v47 = pPlaneAttributes->ClipRect.right;
    v48 = pPlaneAttributes->ClipRect.left;
    if ( v48 >= v47 || (v49 = pPlaneAttributes->ClipRect.top, v50 = pPlaneAttributes->ClipRect.bottom, v49 >= v50) )
    {
      v15 = v184;
      v41 = -1073741811;
      WdLogSingleEntry3(2, -1073741811, this, v184);
      v176 = 0;
      v118 = L"ret = 0x%I64x Context 0x%I64x Clip rect is invalid, index 0x%I64x";
      v175 = 0;
      WdLogGlobalForLineNumber = 3646;
      goto LABEL_161;
    }
    v51 = pPlaneAttributes->DstRect.left;
    v52 = pPlaneAttributes->DstRect.right;
    if ( v51 >= v52 || (v53 = pPlaneAttributes->DstRect.top, v54 = pPlaneAttributes->DstRect.bottom, v53 >= v54) )
    {
      v15 = v184;
      v41 = -1073741811;
      WdLogSingleEntry3(2, -1073741811, this, v184);
      v176 = 0;
      v118 = L"ret = 0x%I64x Context 0x%I64x Destination rect is invalid, index 0x%I64x";
      v175 = 0;
      WdLogGlobalForLineNumber = 3653;
      goto LABEL_161;
    }
    v55 = v191;
    if ( v192 < v50 || v191 < v47 || v197 > v49 || v196 > v48 )
    {
      LODWORD(v41) = -1073741811;
      WdLogSingleEntry3(2, -1073741811, this, v184);
      WdLogGlobalForLineNumber = 3660;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"ret = 0x%I64x Context 0x%I64x Clip rect is outside of virtual mode rect, index 0x%I64x",
        -1073741811,
        (__int64)this,
        v184,
        0,
        0);
      v165 = v33->pPlaneAttributes;
      v166 = v165->ClipRect.right;
      v167 = v165->ClipRect.bottom;
      v168 = (unsigned int)Feature_EnableNonCriticalAsserts__private_featureState;
      v200 = (unsigned int)Feature_EnableNonCriticalAsserts__private_featureState;
      if ( (Feature_EnableNonCriticalAsserts__private_featureState & 0x10) == 0 )
      {
        v195 = (COREDEVICEACCESS *)__PAIR64__(
                                     HIDWORD(v200),
                                     Feature_EnableNonCriticalAsserts__private_featureState | 1u);
        wil_details_FeatureReporting_ReportUsageToService(
          Feature_EnableNonCriticalAsserts__private_descriptor,
          __PAIR64__(HIDWORD(v200), Feature_EnableNonCriticalAsserts__private_featureState | 1u),
          3);
        wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
          v195,
          3,
          Feature_EnableNonCriticalAsserts__private_descriptor);
      }
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        v168,
        (v166 << 16) | (unsigned int)(unsigned __int16)v167,
        (v55 << 16) | (unsigned int)(unsigned __int16)v192,
        "ClipRect outside VirtualModeRect");
      goto LABEL_95;
    }
    if ( v54 < v50 || v52 < v47 || v53 > v49 || v51 > v48 )
    {
      LODWORD(v41) = -1073741811;
      WdLogSingleEntry3(2, -1073741811, this, v184);
      WdLogGlobalForLineNumber = 3679;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"ret = 0x%I64x Context 0x%I64x Clip rect is outside of destination rect, index 0x%I64x",
        -1073741811,
        (__int64)this,
        v184,
        0,
        0);
      v119 = v33->pPlaneAttributes;
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        (unsigned __int16)v119->ClipRect.bottom,
        (unsigned int)(unsigned __int16)v119->ClipRect.bottom | (v119->ClipRect.right << 16),
        (unsigned int)(unsigned __int16)v119->DstRect.bottom | (v119->DstRect.right << 16),
        "ClipRect outside DestRect");
      goto LABEL_95;
    }
    Rotation = pPlaneAttributes->Rotation;
    if ( !(_DWORD)Rotation )
    {
      pPlaneAttributes->Rotation = D3DDDI_ROTATION_IDENTITY;
      goto LABEL_56;
    }
    if ( (_DWORD)Rotation != 1 && (_DWORD)Rotation != 2 && (unsigned int)(Rotation - 3) > 1 )
    {
      v15 = v184;
      v41 = -1073741811;
      WdLogSingleEntry4(2, -1073741811, this, v184, Rotation);
      WdLogGlobalForLineNumber = 3714;
      v118 = L"ret = 0x%I64x Context 0x%I64x rotation is not valid, index 0x%I64x, rotation 0xI64x";
      v176 = 0;
      v175 = v33->pPlaneAttributes->Rotation;
      goto LABEL_161;
    }
LABEL_56:
    DirtyRectCount = pPlaneAttributes->DirtyRectCount;
    if ( DirtyRectCount )
    {
      v97 = 1;
      v98 = 0;
      while ( v97 )
      {
        pDirtyRects = pPlaneAttributes->pDirtyRects;
        v100 = pDirtyRects[v98].right;
        p_left = &pDirtyRects[v98].left;
        if ( *p_left >= v100 || p_left[1] >= pDirtyRects[v98].bottom )
          v97 = 0;
        if ( v206 > *p_left
          || v207 < v100
          || pPlaneAttributes->SrcRect.top > p_left[1]
          || pPlaneAttributes->SrcRect.bottom < pDirtyRects[v98].bottom )
        {
          v97 = 0;
        }
        if ( ++v98 >= DirtyRectCount )
        {
          if ( v97 )
            goto LABEL_57;
          break;
        }
      }
      pPlaneAttributes->DirtyRectCount = 0;
    }
LABEL_57:
    if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) + 3130LL) )
    {
      v146 = v33->pPlaneAttributes;
      if ( v146->DstRect.left != v146->ClipRect.left
        || v146->DstRect.right != v146->ClipRect.right
        || v146->DstRect.top != v146->ClipRect.top
        || v146->DstRect.bottom != v146->ClipRect.bottom )
      {
        *(_OWORD *)&v211.DirtyRectCount = 0;
        InverseXformMPORect3(&v211);
        pPlaneAttributes->SrcRect = *(RECT *)&v211.DirtyRectCount;
        pPlaneAttributes->DstRect = v33->pPlaneAttributes->ClipRect;
        v147 = pPlaneAttributes->SrcRect.right;
        v148 = pPlaneAttributes->SrcRect.left;
        if ( v148 >= v147
          || (v132 = pPlaneAttributes->SrcRect.top, v133 = pPlaneAttributes->SrcRect.bottom, v132 >= v133) )
        {
          v15 = v184;
          v41 = -1073741811;
          WdLogSingleEntry3(2, -1073741811, this, v184);
          v176 = 0;
          v175 = 0;
          WdLogGlobalForLineNumber = 3758;
LABEL_166:
          v118 = L"ret = 0x%I64x Context 0x%I64x Source rect is invalid, index 0x%I64x";
LABEL_161:
          v174 = v15;
LABEL_162:
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v118, v41, (__int64)this, v174, v175, v176);
          goto LABEL_95;
        }
        v149 = pPlaneAttributes->DstRect.left;
        v150 = pPlaneAttributes->DstRect.right;
        if ( v149 >= v150
          || (v130 = pPlaneAttributes->DstRect.top, v131 = pPlaneAttributes->DstRect.bottom, v130 >= v131) )
        {
          v15 = v184;
          v41 = -1073741811;
          WdLogSingleEntry3(2, -1073741811, this, v184);
          v176 = 0;
          v118 = L"ret = 0x%I64x Context 0x%I64x Dest rect is invalid, index 0x%I64x";
          v175 = 0;
          WdLogGlobalForLineNumber = 3765;
          goto LABEL_161;
        }
        if ( v148 < 0 || (int)v202 < v147 || v132 < 0 || (int)v203 < v133 )
        {
          v15 = v184;
          v41 = -1073741811;
          WdLogSingleEntry3(2, -1073741811, this, v184);
          WdLogGlobalForLineNumber = 3772;
          goto LABEL_160;
        }
        if ( v192 < v131 || v196 > v149 || v191 < v150 || v197 > v130 )
        {
          v15 = v184;
          v41 = -1073741811;
          WdLogSingleEntry3(2, -1073741811, this, v184);
          v176 = 0;
          v118 = L"ret = 0x%I64x Context 0x%I64x Dest rect is outside of screen rect, index 0x%I64x";
          v175 = 0;
          WdLogGlobalForLineNumber = 3779;
          goto LABEL_161;
        }
      }
    }
    if ( !v189 )
    {
      if ( v205[0] )
      {
        v58 = *(_DWORD *)(*((_QWORD *)v205[0] + 6) + 4LL) & 0x2000;
        v59 = *(_QWORD *)(*(_QWORD *)v213[0] + 48LL);
        if ( (*(_DWORD *)(v59 + 4) & 0x2000) != 0 )
        {
          if ( !v58 )
          {
            LOBYTE(v59) = 1;
            v193 = v59;
          }
        }
        else
        {
          v60 = (unsigned __int8)v193;
          if ( v58 )
            v60 = 1;
          v193 = v60;
        }
      }
      v61 = pPlaneAttributes->SrcRect.right - pPlaneAttributes->SrcRect.left;
      if ( (pPlaneAttributes->DstRect.right - pPlaneAttributes->DstRect.left != v61
         || pPlaneAttributes->DstRect.bottom - pPlaneAttributes->DstRect.top != pPlaneAttributes->SrcRect.bottom
                                                                              - pPlaneAttributes->SrcRect.top)
        && *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 2) + 1896LL) + 3082LL) )
      {
        v198 = pPlaneAttributes->SrcRect.bottom - pPlaneAttributes->SrcRect.top;
        v183 = 1;
        v199 = v61;
      }
    }
    if ( v179 )
    {
      v151 = pPlaneAttributes->DstRect.left;
      if ( v151 != pPlaneAttributes->SrcRect.left
        || (v152 = pPlaneAttributes->DstRect.right, v152 != pPlaneAttributes->SrcRect.right)
        || (v125 = pPlaneAttributes->DstRect.top, v125 != pPlaneAttributes->SrcRect.top)
        || (v126 = pPlaneAttributes->DstRect.bottom, v126 != pPlaneAttributes->SrcRect.bottom)
        || v151 != pPlaneAttributes->ClipRect.left
        || v152 != pPlaneAttributes->ClipRect.right
        || v125 != pPlaneAttributes->ClipRect.top
        || v126 != pPlaneAttributes->ClipRect.bottom )
      {
        v41 = -1073741811;
        WdLogSingleEntry2(2, -1073741811);
        v176 = 0;
        v118 = L"0x%I64x Context 0x%I64x PresentMPO fails because the driver doesn't support MPO and Source/Dest/Clip rect"
                "s are not identical";
        v175 = 0;
        v174 = 0;
        WdLogGlobalForLineNumber = 3819;
        goto LABEL_162;
      }
      v153 = v33->pPlaneAttributes;
      if ( v153->Rotation != D3DDDI_ROTATION_IDENTITY )
      {
        v41 = -1073741811;
        WdLogSingleEntry3(2, -1073741811, this, (unsigned int)v153->Rotation);
        WdLogGlobalForLineNumber = 3828;
        v118 = L"0x%I64x Context 0x%I64x PresentMPO fails because the driver doesn't support MPO and rotation 0x%I64x is specified";
        v176 = 0;
        v175 = 0;
        v174 = (unsigned int)v33->pPlaneAttributes->Rotation;
        goto LABEL_162;
      }
      _mm_lfence();
      if ( v188 != ((*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v213[0] + v189) + 48LL) + 4LL) >> 6) & 0xF) )
      {
        _mm_lfence();
        v154 = v188;
        v155 = v189;
        v41 = -1073741811;
        WdLogSingleEntry4(
          2,
          -1073741811,
          this,
          v188,
          (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v213[0] + v189) + 48LL) + 4LL) >> 6) & 0xF);
        v118 = L"0x%I64x Context 0x%I64x PresentMPO fails because the driver doesn't support MPO and VidPnSourceId (0x%I64"
                "x) doesn't match the surface VidPnSOurceId (0x%I64x)";
        WdLogGlobalForLineNumber = 3837;
        v176 = 0;
        v175 = (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v213[0] + v155) + 48LL) + 4LL) >> 6) & 0xF;
        v174 = v154;
        goto LABEL_162;
      }
    }
LABEL_67:
    if ( (v33->InputFlags.Value & 1) != 0 || v185 )
    {
      FlipInterval = v33->FlipInterval;
      if ( FlipInterval )
        break;
    }
LABEL_69:
    v29 = v201 | v190;
    v190 |= v201;
    if ( !bTracingEnabled )
      goto LABEL_70;
    v102 = v33->pPlaneAttributes;
    v103 = v186;
    v104 = a2->HDRMetaDataType;
    Blend = v102->Blend;
    v106 = v102->Rotation;
    Flags = v102->Flags;
    SDRWhiteLevel = v102->SDRWhiteLevel;
    v109 = *v186->pAllocationList;
    ColorSpace = v102->ColorSpace;
    v201 = Blend;
    LODWORD(v203) = v106;
    LODWORD(v202) = Flags;
    if ( v109 )
    {
      v111 = (unsigned int)VIDMM_EXPORT::VidMmETWAllocationHandle(
                             *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 760LL),
                             *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 768LL),
                             v109);
      LOBYTE(Blend) = v201;
      v112 = v111;
      LOBYTE(v106) = (_BYTE)v203;
      LOBYTE(Flags) = v202;
      v103 = v186;
    }
    else
    {
      v112 = 0;
    }
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
    {
      v178 = ColorSpace;
      LODWORD(VidPnSourceId) = v188;
      McTemplateK0qqqpqddddddddddddqqqqqq_EtwWriteTransfer(
        v103->InputFlags.Value & 1,
        v112,
        v109,
        v188,
        v186->LayerIndex,
        *(_BYTE *)&v103->InputFlags.0 & 1,
        v112,
        Flags,
        v102->SrcRect.left,
        v102->SrcRect.right,
        v102->SrcRect.top,
        v102->SrcRect.bottom,
        v102->DstRect.left,
        v102->DstRect.right,
        v102->DstRect.top,
        v102->DstRect.bottom,
        v102->ClipRect.left,
        v102->ClipRect.right,
        v102->ClipRect.top,
        v102->ClipRect.bottom,
        v106,
        Blend,
        v177,
        v178,
        v104,
        SDRWhiteLevel);
      v29 = v190;
    }
    else
    {
      v29 = v190;
LABEL_70:
      LODWORD(VidPnSourceId) = v188;
    }
  }
  if ( FlipInterval == D3DDDI_FLIPINTERVAL_ONE )
  {
    v204 = 1;
    goto LABEL_69;
  }
  LODWORD(v41) = -1073741811;
  WdLogSingleEntry3(3, this, v33->FlipInterval, -1073741811);
  WdLogGlobalForLineNumber = 3875;
LABEL_95:
  PagedPoolArray<DXGALLOCATIONREFERENCE,4>::~PagedPoolArray<DXGALLOCATIONREFERENCE,4>(v213);
  return (unsigned int)v41;
}

```

## disassembly

```asm
0x14033de10  push    rbp
0x14033de12  push    rbx
0x14033de13  push    rsi
0x14033de14  push    rdi
0x14033de15  push    r12
0x14033de17  push    r13
0x14033de19  push    r14
0x14033de1b  push    r15
0x14033de1d  lea     rbp, [rsp-788h]
0x14033de25  sub     rsp, 8D8h
0x14033de2c  mov     rax, cs:__security_cookie
0x14033de33  xor     rax, rsp
0x14033de36  mov     [rbp+7C0h+var_48], rax
0x14033de3d  mov     r14, rcx
0x14033de40  mov     [rbp+7C0h+var_7A0], r9
0x14033de44  mov     rcx, [rcx+10h]
0x14033de48  mov     rdi, rdx
0x14033de4b  mov     [rbp+7C0h+var_808], r8
0x14033de4f  mov     rax, [rcx+768h]
0x14033de56  mov     rcx, [rcx+10h]; this
0x14033de5a  mov     esi, [rax+1BCh]
0x14033de60  and     esi, 100h
0x14033de66  mov     [rbp+7C0h+var_7B0], esi
0x14033de69  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x14033de6e  or      ebx, 0FFFFFFFFh
0x14033de71  xor     r12d, r12d
0x14033de74  mov     r15d, 1
0x14033de7a  mov     r13d, 40002h
0x14033de80  test    al, al
0x14033de82  jz      loc_14033F624
0x14033de88  mov     rcx, [r14+10h]
0x14033de8c  mov     rax, [rcx+10h]
0x14033de90  mov     rdx, [rax+10h]
0x14033de94  test    rdx, rdx
0x14033de97  jz      loc_14033F670
0x14033de9d  cmp     [rcx+768h], rdx
0x14033dea4  jnz     loc_14033F67D
0x14033deaa  mov     [r14+1B3h], r15b
0x14033deb1  test    esi, esi
0x14033deb3  jnz     loc_14033F6C9
0x14033deb9  mov     rax, [r14+10h]
0x14033debd  mov     rcx, [rax+10h]
0x14033dec1  mov     rax, [rcx+10h]
0x14033dec5  mov     ecx, [rax+0BF0h]
0x14033decb  mov     eax, [rdi+1Ch]
0x14033dece  mov     [rbp+7C0h+var_828], ecx
0x14033ded1  cmp     eax, ecx
0x14033ded3  ja      loc_14033F6D1
0x14033ded9  mov     r13d, [rdi+10h]
0x14033dedd  mov     [rbp+7C0h+var_824], r13d
0x14033dee1  mov     ebx, r13d
0x14033dee4  test    esi, esi
0x14033dee6  jz      loc_14033EB48
0x14033deec  mov     eax, [rdi+18h]
0x14033deef  mov     ecx, 2
0x14033def4  mov     edx, eax
0x14033def6  mov     r8d, eax
0x14033def9  and     edx, r15d
0x14033defc  mov     r15d, 40000h
0x14033df02  and     r8d, ecx
0x14033df05  jnz     loc_14033F72A
0x14033df0b  test    edx, edx
0x14033df0d  jnz     loc_14033F72A
0x14033df13  mov     edx, [rbp+7C0h+var_828]
0x14033df16  lea     rcx, [rbp+7C0h+var_748]
0x14033df1a  imul    edx, [rdi+4]
0x14033df1e  mov     [rbp+7C0h+var_748], r12
0x14033df22  mov     [rbp+7C0h+var_720], r12d
0x14033df29  call    ?AllocateElements@?$PagedPoolArray@VDXGALLOCATIONREFERENCE@@$03@@QEAAPEAVDXGALLOCATIONREFERENCE@@I@Z; PagedPoolArray<DXGALLOCATIONREFERENCE,4>::AllocateElements(uint)
0x14033df2e  mov     r12, [rbp+7C0h+var_748]
0x14033df32  xor     esi, esi
0x14033df34  test    r12, r12
0x14033df37  jz      loc_14033F927
0x14033df3d  mov     rsi, [r14+10h]
0x14033df41  mov     rax, [rsi+10h]
0x14033df45  mov     rcx, [rsi+768h]
0x14033df4c  cmp     rcx, [rax+10h]
0x14033df50  jnz     loc_14033E5EB
0x14033df56  mov     r9d, [rbp+7C0h+var_828]; unsigned int
0x14033df5a  mov     r8, r12; struct DXGALLOCATIONREFERENCE *
0x14033df5d  mov     rcx, [rcx+0CA0h]; this
0x14033df64  mov     edx, r13d; unsigned int
0x14033df67  call    ?GetAllocationsForAllPlanes@ADAPTER_DISPLAY@@QEAAXIPEAVDXGALLOCATIONREFERENCE@@I@Z; ADAPTER_DISPLAY::GetAllocationsForAllPlanes(uint,DXGALLOCATIONREFERENCE *,uint)
0x14033df6c  mov     rax, [rbp+7C0h+var_748]
0x14033df70  lea     r8, [rbp+7C0h+var_58]; unsigned __int8 *
0x14033df77  mov     edx, r13d; unsigned int
0x14033df7a  mov     rcx, [rax]
0x14033df7d  mov     rax, [r14+10h]
0x14033df81  mov     [rbp+7C0h+var_7C8], rcx
0x14033df85  mov     rcx, [rax+768h]
0x14033df8c  mov     rcx, [rcx+0CA0h]; this
0x14033df93  call    ?GetDDIEnabledPlanes@ADAPTER_DISPLAY@@QEAAXIPEAE@Z; ADAPTER_DISPLAY::GetDDIEnabledPlanes(uint,uchar *)
0x14033df98  mov     rcx, [r14+10h]
0x14033df9c  xorps   xmm0, xmm0
0x14033df9f  xor     eax, eax
0x14033dfa1  movups  xmmword ptr [rbp+7C0h+var_80], xmm0
0x14033dfa8  mov     [rbp+7C0h+var_60], rax
0x14033dfaf  mov     rcx, [rcx+10h]; this
0x14033dfb3  movups  [rbp+7C0h+var_70], xmm0
0x14033dfba  call    ?IsMultiPlaneOverlaySupported@ADAPTER_RENDER@@QEAAEXZ; ADAPTER_RENDER::IsMultiPlaneOverlaySupported(void)
0x14033dfbf  test    al, al
0x14033dfc1  jnz     loc_14033EB0E
0x14033dfc7  mov     esi, 1
0x14033dfcc  mov     r12b, sil
0x14033dfcf  mov     rax, [r14+10h]
0x14033dfd3  mov     edx, r13d; unsigned int
0x14033dfd6  mov     [rbp+7C0h+var_840], r12b
0x14033dfda  mov     rcx, [rax+768h]
0x14033dfe1  mov     rcx, [rcx+0CA0h]; this
0x14033dfe8  call    ?GetDisplayModeInfo@ADAPTER_DISPLAY@@QEBAQEBU_DXGK_DISPLAYMODE_INFO@@I@Z; ADAPTER_DISPLAY::GetDisplayModeInfo(uint)
0x14033dfed  test    rax, rax
0x14033dff0  jz      loc_14033F978
0x14033dff6  mov     r9d, [rax]
0x14033dff9  xor     dl, dl
0x14033dffb  mov     r10d, [rax+4]
0x14033dfff  xor     r8d, r8d
0x14033e002  mov     rcx, [rdi+28h]
0x14033e006  xor     eax, eax
0x14033e008  mov     [rbp+7C0h+var_83C], dl
0x14033e00b  mov     [rbp+7C0h+var_7F4], r8d
0x14033e00f  mov     [rbp+7C0h+var_7F8], eax
0x14033e012  test    rcx, rcx
0x14033e015  jnz     loc_14033F9C1
0x14033e01b  mov     [rbp+7C0h+var_800], eax
0x14033e01e  mov     [rbp+7C0h+var_7FC], eax
0x14033e021  mov     [rbp+7C0h+var_818], r9d
0x14033e025  mov     [rbp+7C0h+var_814], r10d
0x14033e029  test    r12b, r12b
0x14033e02c  jnz     loc_14033FA86
0x14033e032  xor     r12d, r12d
0x14033e035  or      eax, 0FFFFFFFFh
0x14033e038  mov     [rbp+7C0h+var_83E], r12b
0x14033e03c  mov     [rbp+7C0h+var_80C], eax
0x14033e03f  mov     ebx, r12d
0x14033e042  mov     al, r12b
0x14033e045  mov     [rbp+7C0h+var_81C], ebx
0x14033e048  mov     [rbp+7C0h+var_810], eax
0x14033e04b  mov     rax, [r14+10h]
0x14033e04f  mov     [rbp+7C0h+var_83D], r12b
0x14033e053  mov     [rbp+7C0h+var_83F], r12b
0x14033e057  mov     [rbp+7C0h+var_7D0], r12d
0x14033e05b  mov     rcx, [rax+10h]
0x14033e05f  mov     rax, [rcx+10h]
0x14033e063  cmp     dword ptr [rax+0C2Ch], 0BB8h
0x14033e06d  jl      loc_14033EBB3
0x14033e073  mov     r8d, 1
0x14033e079  mov     [rbp+7C0h+var_834], r8b
0x14033e07d  mov     eax, r12d
0x14033e080  mov     [rbp+7C0h+var_838], eax
0x14033e083  cmp     eax, [rdi+1Ch]
0x14033e086  jnb     loc_14033E35B
0x14033e08c  mov     edx, [rbp+7C0h+var_828]
0x14033e08f  mov     ecx, eax
0x14033e091  mov     rax, [rdi+20h]
0x14033e095  mov     r13, [rax+rcx*8]
0x14033e099  mov     [rbp+7C0h+var_830], r13
0x14033e09d  mov     esi, [r13+0]
0x14033e0a1  mov     [rbp+7C0h+var_820], esi
0x14033e0a4  mov     r12d, esi
0x14033e0a7  cmp     esi, edx
0x14033e0a9  jnb     loc_14033FFA1
0x14033e0af  lfence
0x14033e0b2  mov     ecx, esi
0x14033e0b4  mov     eax, r8d
0x14033e0b7  shl     eax, cl
0x14033e0b9  mov     [rbp+7C0h+var_7E8], eax
0x14033e0bc  test    eax, ebx
0x14033e0be  jnz     loc_14033FF71
0x14033e0c4  mov     eax, [r13+4]
0x14033e0c8  test    r8b, al
0x14033e0cb  jz      loc_14033FC5F
0x14033e0d1  mov     r9, [rbp+7C0h+var_748]
0x14033e0d5  cmp     qword ptr [r9+rsi*8], 0
0x14033e0da  jz      loc_14033FB42
0x14033e0e0  add     [rbp+7C0h+var_83E], r8b
0x14033e0e4  xor     ebx, ebx
0x14033e0e6  cmp     ebx, [r13+10h]
0x14033e0ea  jb      loc_14033E770
0x14033e0f0  lfence
0x14033e0f3  mov     rax, [rbp+7C0h+var_748]
0x14033e0f7  mov     rdx, [rax+r12*8]; struct DXGALLOCATION *
0x14033e0fb  mov     rax, [rdx+30h]
0x14033e0ff  mov     ecx, [rax+4]
0x14033e102  bt      ecx, 0Dh
0x14033e106  jnb     loc_14033E724
0x14033e10c  test    cl, 20h
0x14033e10f  jz      loc_14033EF43
0x14033e115  lfence
0x14033e118  mov     rax, [rbp+7C0h+var_748]
0x14033e11c  lea     rdx, [rbp+7C0h+var_778]; struct _DXGKARG_DESCRIBEALLOCATION *
0x14033e120  xorps   xmm0, xmm0
0x14033e123  movups  xmmword ptr [rbp+7C0h+var_778.hAllocation], xmm0
0x14033e127  movups  xmmword ptr [rbp+7C0h+var_778.Format], xmm0
0x14033e12b  movups  xmmword ptr [rbp+7C0h+var_778.RefreshRate.Denominator], xmm0
0x14033e12f  mov     rcx, [rax+r12*8]
0x14033e133  mov     rax, [rcx+30h]
0x14033e137  mov     rcx, [rax+10h]
0x14033e13b  mov     [rbp+7C0h+var_778.hAllocation], rcx
0x14033e13f  mov     rcx, [r14+10h]
0x14033e143  mov     rcx, [rcx+10h]; this
0x14033e147  call    ?DdiDescribeAllocation@ADAPTER_RENDER@@QEAAJPEAU_DXGKARG_DESCRIBEALLOCATION@@@Z; ADAPTER_RENDER::DdiDescribeAllocation(_DXGKARG_DESCRIBEALLOCATION *)
0x14033e14c  movsxd  rsi, eax
0x14033e14f  test    eax, eax
0x14033e151  js      loc_14033FED6
0x14033e157  mov     rbx, [r13+30h]
0x14033e15b  mov     eax, [rbp+7C0h+var_778.Format]
0x14033e15e  mov     [rbp+r12*4+7C0h+var_80], eax
0x14033e166  mov     r8d, [rbx+0Ch]
0x14033e16a  mov     edx, [rbx+4]
0x14033e16d  mov     [rbp+7C0h+var_7B4], r8d
0x14033e171  mov     [rbp+7C0h+var_7B8], edx
0x14033e174  cmp     edx, r8d
0x14033e177  jge     loc_14033EDD6
0x14033e17d  mov     eax, [rbx+8]
0x14033e180  mov     ecx, [rbx+10h]
0x14033e183  cmp     eax, ecx
0x14033e185  jge     loc_14033EDD6
0x14033e18b  xor     r12d, r12d
0x14033e18e  test    edx, edx
0x14033e190  js      loc_14033EC27
0x14033e196  mov     edx, [rbp+7C0h+var_778.Width]
0x14033e199  mov     dword ptr [rbp+7C0h+var_7E0], edx
0x14033e19c  cmp     edx, r8d
0x14033e19f  jl      loc_14033EC27
0x14033e1a5  test    eax, eax
0x14033e1a7  js      loc_14033EC27
0x14033e1ad  mov     eax, [rbp+7C0h+var_778.Height]
0x14033e1b0  mov     dword ptr [rbp+7C0h+var_7D8], eax
0x14033e1b3  cmp     eax, ecx
0x14033e1b5  jl      loc_14033EC27
0x14033e1bb  mov     ecx, [rbx+2Ch]
0x14033e1be  mov     eax, [rbx+24h]
0x14033e1c1  cmp     eax, ecx
0x14033e1c3  jge     loc_14033EE66
0x14033e1c9  mov     edx, [rbx+28h]
0x14033e1cc  mov     r9d, [rbx+30h]
0x14033e1d0  cmp     edx, r9d
0x14033e1d3  jge     loc_14033EE66
0x14033e1d9  mov     r8d, [rbx+14h]
0x14033e1dd  mov     r10d, [rbx+1Ch]
0x14033e1e1  cmp     r8d, r10d
0x14033e1e4  jge     loc_14033EE22
0x14033e1ea  mov     r11d, [rbx+18h]
0x14033e1ee  mov     esi, [rbx+20h]
0x14033e1f1  cmp     r11d, esi
0x14033e1f4  jge     loc_14033EE22
0x14033e1fa  mov     r12d, [rbp+7C0h+var_818]
0x14033e1fe  cmp     [rbp+7C0h+var_814], r9d
0x14033e202  jl      loc_14033FDF4
0x14033e208  cmp     r12d, ecx
0x14033e20b  jl      loc_14033FDF4
0x14033e211  cmp     [rbp+7C0h+var_7FC], edx
0x14033e214  jg      loc_14033FDF4
0x14033e21a  cmp     [rbp+7C0h+var_800], eax
0x14033e21d  jg      loc_14033FDF4
0x14033e223  cmp     esi, r9d
0x14033e226  jl      loc_14033EC7A
0x14033e22c  cmp     r10d, ecx
0x14033e22f  jl      loc_14033EC7A
0x14033e235  cmp     r11d, edx
0x14033e238  jg      loc_14033EC7A
0x14033e23e  cmp     r8d, eax
0x14033e241  jg      loc_14033EC7A
0x14033e247  movsxd  rcx, dword ptr [rbx+34h]
0x14033e24b  mov     eax, ecx
0x14033e24d  test    ecx, ecx
0x14033e24f  jz      loc_14033FBE5
0x14033e255  sub     eax, 1
0x14033e258  jz      short loc_14033E26D
0x14033e25a  sub     eax, 1
0x14033e25d  jz      short loc_14033E26D
0x14033e25f  sub     eax, 1
0x14033e262  jz      short loc_14033E26D
0x14033e264  cmp     eax, 1
0x14033e267  jnz     loc_14033FD52
0x14033e26d  mov     r12d, [rbx+3Ch]
0x14033e271  test    r12d, r12d
0x14033e274  jnz     loc_14033E8EE
0x14033e27a  xor     r12d, r12d
0x14033e27d  mov     rax, [r14+10h]
0x14033e281  mov     rcx, [rax+768h]
0x14033e288  cmp     [rcx+0C3Ah], r12b
0x14033e28f  jnz     loc_14033F48D
0x14033e295  mov     r9d, [rbp+7C0h+var_820]
0x14033e299  test    r9d, r9d
0x14033e29c  jnz     short loc_14033E30D
0x14033e29e  mov     rax, [rbp+7C0h+var_7C8]
0x14033e2a2  test    rax, rax
0x14033e2a5  jz      short loc_14033E2E2
0x14033e2a7  mov     rax, [rax+30h]
0x14033e2ab  mov     r8d, 2000h
0x14033e2b1  mov     edx, [rax+4]
0x14033e2b4  mov     rax, [rbp+7C0h+var_748]
0x14033e2b8  and     edx, r8d
0x14033e2bb  mov     rcx, [rax]
0x14033e2be  mov     rax, [rcx+30h]
0x14033e2c2  test    [rax+4], r8d
0x14033e2c6  jnz     loc_14033FC1F
0x14033e2cc  mov     r10d, [rbp+7C0h+var_810]
0x14033e2d0  lea     eax, [r9+1]
  ... truncated ...
```
