# DxgkQueryAdapterInfoImpl(_D3DKMT_QUERYADAPTERINFO const *,uchar,DXGADAPTER *)

- ea: `0x14035feb0`
- end: `0x140363251`
- name: `?DxgkQueryAdapterInfoImpl@@YAJPEBU_D3DKMT_QUERYADAPTERINFO@@EPEAVDXGADAPTER@@@Z`
- size: `13217`
- prototype: `__int64 __fastcall(const struct _D3DKMT_QUERYADAPTERINFO *Src, unsigned __int8, struct DXGADAPTER *)`
- caller_count: `3`
- callee_count: `72`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14020e5e0`
- `0x1402916b0`
- `0x14035fe90`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140012540`
- `0x140012cd4`
- `0x140013a20`
- `0x140015710`
- `0x1400157bc`
- `0x1400157dc`
- `0x140015940`
- `0x140015a70`
- `0x140015bc0`
- `0x140018190`
- `0x14001b9c0`
- `0x14001ca40`
- `0x14001cff0`
- `0x14001d214`
- `0x14001f630`
- `0x14002e160`
- `0x14002ee60`
- `0x1400309f0`
- `0x140033a40`
- `0x140033d80`
- `0x140034b40`
- `0x1400367b8`
- `0x140041ddc`
- `0x140047754`
- `0x14004d4a4`
- `0x140060ea4`
- `0x1400674c4`
- `0x14006d7c8`
- `0x14006df00`
- `0x1400a0ba8`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x140195cd4`
- `0x14019d330`
- `0x1401e76e0`
- `0x1401e9f80`
- `0x1401ea29c`
- `0x1401eef90`
- `0x1401fc7d4`
- `0x14020c850`
- `0x14020cad8`
- `0x140298324`
- `0x1402a4efc`
- `0x14032a5c4`
- `0x14035a180`
- `0x14035f758`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140360eab`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140360eab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140360f04`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140360f04`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140360ef8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140360ef8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140360ebd`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140360ebd`
- `ntoskrnl!ObfDereferenceObject` at `0x140362a97`
- `ntoskrnl!ObfDereferenceObject` at `0x140362a97`
- `ntoskrnl!ObfReferenceObject` at `0x140362a73`
- `ntoskrnl!ObfReferenceObject` at `0x140362a73`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140361165`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1403625a0`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140361165`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1403625a0`
- `ntoskrnl!PsGetHostSilo` at `0x140362591`
- `ntoskrnl!PsGetHostSilo` at `0x140362591`
- `watchdog!WdLogSingleEntry2` at `0x1403606cd`
- `watchdog!WdLogSingleEntry2` at `0x140360845`
- `watchdog!WdLogSingleEntry2` at `0x1403608a7`
- `watchdog!WdLogSingleEntry2` at `0x140360908`
- `watchdog!WdLogSingleEntry2` at `0x1403609c7`
- `watchdog!WdLogSingleEntry2` at `0x140360b17`
- `watchdog!WdLogSingleEntry2` at `0x140360d1e`
- `watchdog!WdLogSingleEntry2` at `0x140360d4e`
- `watchdog!WdLogSingleEntry2` at `0x140360dca`
- `watchdog!WdLogSingleEntry2` at `0x140361073`
- `watchdog!WdLogSingleEntry2` at `0x1403611c2`
- `watchdog!WdLogSingleEntry2` at `0x14036126d`
- `watchdog!WdLogSingleEntry2` at `0x14036129d`
- `watchdog!WdLogSingleEntry2` at `0x1403612cd`
- `watchdog!WdLogSingleEntry2` at `0x140361340`
- `watchdog!WdLogSingleEntry2` at `0x140361370`
- `watchdog!WdLogSingleEntry2` at `0x14036139a`
- `watchdog!WdLogSingleEntry2` at `0x14036174e`
- `watchdog!WdLogSingleEntry2` at `0x140361782`
- `watchdog!WdLogSingleEntry2` at `0x1403617b2`
- `watchdog!WdLogSingleEntry2` at `0x1403618d2`
- `watchdog!WdLogSingleEntry2` at `0x140361963`
- `watchdog!WdLogSingleEntry2` at `0x14036199e`
- `watchdog!WdLogSingleEntry2` at `0x1403619d5`
- `watchdog!WdLogSingleEntry2` at `0x140361a3c`
- `watchdog!WdLogSingleEntry2` at `0x140361bd9`
- `watchdog!WdLogSingleEntry2` at `0x140361cd0`
- `watchdog!WdLogSingleEntry2` at `0x140361d2a`
- `watchdog!WdLogSingleEntry2` at `0x140361d61`
- `watchdog!WdLogSingleEntry2` at `0x140361e00`
- `watchdog!WdLogSingleEntry2` at `0x140361e52`
- `watchdog!WdLogSingleEntry2` at `0x140361e7e`
- `watchdog!WdLogSingleEntry2` at `0x140361f12`
- `watchdog!WdLogSingleEntry2` at `0x140361f9f`
- `watchdog!WdLogSingleEntry2` at `0x140361ff9`
- `watchdog!WdLogSingleEntry2` at `0x140362086`
- `watchdog!WdLogSingleEntry2` at `0x14036213f`
- `watchdog!WdLogSingleEntry2` at `0x1403621cc`
- `watchdog!WdLogSingleEntry2` at `0x140362233`
- `watchdog!WdLogSingleEntry2` at `0x14036227e`
- `watchdog!WdLogSingleEntry2` at `0x1403622cc`
- `watchdog!WdLogSingleEntry2` at `0x14036231a`
- `watchdog!WdLogSingleEntry2` at `0x140362361`
- `watchdog!WdLogSingleEntry2` at `0x1403623b3`
- `watchdog!WdLogSingleEntry2` at `0x1403623e7`
- `watchdog!WdLogSingleEntry2` at `0x140362433`
- `watchdog!WdLogSingleEntry2` at `0x1403624bf`
- `watchdog!WdLogSingleEntry2` at `0x14036252b`
- `watchdog!WdLogSingleEntry2` at `0x140362562`
- `watchdog!WdLogSingleEntry2` at `0x1403625d0`
- `watchdog!WdLogSingleEntry2` at `0x1403626b4`
- `watchdog!WdLogSingleEntry2` at `0x1403626f9`
- `watchdog!WdLogSingleEntry2` at `0x140362749`
- `watchdog!WdLogSingleEntry2` at `0x140362809`
- `watchdog!WdLogSingleEntry2` at `0x140362840`
- `watchdog!WdLogSingleEntry2` at `0x1403628ce`
- `watchdog!WdLogSingleEntry2` at `0x140362999`
- `watchdog!WdLogSingleEntry2` at `0x140362a4e`
- `watchdog!WdLogSingleEntry2` at `0x140362ae9`
- `watchdog!WdLogSingleEntry2` at `0x140362b20`
- `watchdog!WdLogSingleEntry2` at `0x140362b9d`
- `watchdog!WdLogSingleEntry2` at `0x140362bf2`
- `watchdog!WdLogSingleEntry2` at `0x140362c90`
- `watchdog!WdLogSingleEntry2` at `0x140362cd0`
- `watchdog!WdLogSingleEntry2` at `0x140362d32`
- `watchdog!WdLogSingleEntry2` at `0x140362d79`
- `watchdog!WdLogSingleEntry2` at `0x140362dc0`
- `watchdog!WdLogSingleEntry2` at `0x140362e07`
- `watchdog!WdLogSingleEntry2` at `0x140362ebf`
- `watchdog!WdLogSingleEntry2` at `0x140362eee`
- `watchdog!WdLogSingleEntry2` at `0x140362f71`
- `watchdog!WdLogSingleEntry2` at `0x140362fac`
- `watchdog!WdLogSingleEntry2` at `0x14036302f`
- `watchdog!WdLogSingleEntry2` at `0x140363087`
- `watchdog!WdLogSingleEntry2` at `0x1403630ce`
- `watchdog!WdLogSingleEntry2` at `0x140363209`
- `watchdog!WdLogSingleEntry2` at `0x1403606cd`
- `watchdog!WdLogSingleEntry2` at `0x140360845`
- `watchdog!WdLogSingleEntry2` at `0x1403608a7`
- `watchdog!WdLogSingleEntry2` at `0x140360908`
- `watchdog!WdLogSingleEntry2` at `0x1403609c7`
- `watchdog!WdLogSingleEntry2` at `0x140360b17`
- `watchdog!WdLogSingleEntry2` at `0x140360d1e`
- `watchdog!WdLogSingleEntry2` at `0x140360d4e`
- `watchdog!WdLogSingleEntry2` at `0x140360dca`
- `watchdog!WdLogSingleEntry2` at `0x140361073`
- `watchdog!WdLogSingleEntry2` at `0x1403611c2`
- `watchdog!WdLogSingleEntry2` at `0x14036126d`
- `watchdog!WdLogSingleEntry2` at `0x14036129d`
- `watchdog!WdLogSingleEntry2` at `0x1403612cd`
- `watchdog!WdLogSingleEntry2` at `0x140361340`
- `watchdog!WdLogSingleEntry2` at `0x140361370`
- `watchdog!WdLogSingleEntry2` at `0x14036139a`
- `watchdog!WdLogSingleEntry2` at `0x14036174e`
- `watchdog!WdLogSingleEntry2` at `0x140361782`
- `watchdog!WdLogSingleEntry2` at `0x1403617b2`
- `watchdog!WdLogSingleEntry2` at `0x1403618d2`
- `watchdog!WdLogSingleEntry2` at `0x140361963`
- `watchdog!WdLogSingleEntry2` at `0x14036199e`
- `watchdog!WdLogSingleEntry2` at `0x1403619d5`
- `watchdog!WdLogSingleEntry2` at `0x140361a3c`
- `watchdog!WdLogSingleEntry2` at `0x140361bd9`
- `watchdog!WdLogSingleEntry2` at `0x140361cd0`
- `watchdog!WdLogSingleEntry2` at `0x140361d2a`
- `watchdog!WdLogSingleEntry2` at `0x140361d61`
- `watchdog!WdLogSingleEntry2` at `0x140361e00`
- `watchdog!WdLogSingleEntry2` at `0x140361e52`
- `watchdog!WdLogSingleEntry2` at `0x140361e7e`
- `watchdog!WdLogSingleEntry2` at `0x140361f12`
- `watchdog!WdLogSingleEntry2` at `0x140361f9f`
- `watchdog!WdLogSingleEntry2` at `0x140361ff9`
- `watchdog!WdLogSingleEntry2` at `0x140362086`
- `watchdog!WdLogSingleEntry2` at `0x14036213f`
- `watchdog!WdLogSingleEntry2` at `0x1403621cc`
- `watchdog!WdLogSingleEntry2` at `0x140362233`
- `watchdog!WdLogSingleEntry2` at `0x14036227e`
- `watchdog!WdLogSingleEntry2` at `0x1403622cc`
- `watchdog!WdLogSingleEntry2` at `0x14036231a`
- `watchdog!WdLogSingleEntry2` at `0x140362361`
- `watchdog!WdLogSingleEntry2` at `0x1403623b3`
- `watchdog!WdLogSingleEntry2` at `0x1403623e7`
- `watchdog!WdLogSingleEntry2` at `0x140362433`
- `watchdog!WdLogSingleEntry2` at `0x1403624bf`
- `watchdog!WdLogSingleEntry2` at `0x14036252b`
- `watchdog!WdLogSingleEntry2` at `0x140362562`
- `watchdog!WdLogSingleEntry2` at `0x1403625d0`
- `watchdog!WdLogSingleEntry2` at `0x1403626b4`
- `watchdog!WdLogSingleEntry2` at `0x1403626f9`
- `watchdog!WdLogSingleEntry2` at `0x140362749`
- `watchdog!WdLogSingleEntry2` at `0x140362809`
- `watchdog!WdLogSingleEntry2` at `0x140362840`
- `watchdog!WdLogSingleEntry2` at `0x1403628ce`
- `watchdog!WdLogSingleEntry2` at `0x140362999`
- `watchdog!WdLogSingleEntry2` at `0x140362a4e`
- `watchdog!WdLogSingleEntry2` at `0x140362ae9`
- `watchdog!WdLogSingleEntry2` at `0x140362b20`
- `watchdog!WdLogSingleEntry2` at `0x140362b9d`
- `watchdog!WdLogSingleEntry2` at `0x140362bf2`
- `watchdog!WdLogSingleEntry2` at `0x140362c90`
- `watchdog!WdLogSingleEntry2` at `0x140362cd0`
- `watchdog!WdLogSingleEntry2` at `0x140362d32`
- `watchdog!WdLogSingleEntry2` at `0x140362d79`
- `watchdog!WdLogSingleEntry2` at `0x140362dc0`
- `watchdog!WdLogSingleEntry2` at `0x140362e07`
- `watchdog!WdLogSingleEntry2` at `0x140362ebf`
- `watchdog!WdLogSingleEntry2` at `0x140362eee`
- `watchdog!WdLogSingleEntry2` at `0x140362f71`
- `watchdog!WdLogSingleEntry2` at `0x140362fac`
- `watchdog!WdLogSingleEntry2` at `0x14036302f`
- `watchdog!WdLogSingleEntry2` at `0x140363087`
- `watchdog!WdLogSingleEntry2` at `0x1403630ce`
- `watchdog!WdLogSingleEntry2` at `0x140363209`
- `watchdog!WdLogSingleEntry3` at `0x1403614af`
- `watchdog!WdLogSingleEntry3` at `0x140361506`
- `watchdog!WdLogSingleEntry3` at `0x1403615f4`
- `watchdog!WdLogSingleEntry3` at `0x140361b5b`
- `watchdog!WdLogSingleEntry3` at `0x140361c44`
- `watchdog!WdLogSingleEntry3` at `0x140361c99`
- `watchdog!WdLogSingleEntry3` at `0x140361f68`
- `watchdog!WdLogSingleEntry3` at `0x14036204f`
- `watchdog!WdLogSingleEntry3` at `0x140362c59`
- `watchdog!WdLogSingleEntry3` at `0x140362e68`
- `watchdog!WdLogSingleEntry3` at `0x140362f36`
- `watchdog!WdLogSingleEntry3` at `0x1403614af`
- `watchdog!WdLogSingleEntry3` at `0x140361506`
- `watchdog!WdLogSingleEntry3` at `0x1403615f4`
- `watchdog!WdLogSingleEntry3` at `0x140361b5b`
- `watchdog!WdLogSingleEntry3` at `0x140361c44`
- `watchdog!WdLogSingleEntry3` at `0x140361c99`
- `watchdog!WdLogSingleEntry3` at `0x140361f68`
- `watchdog!WdLogSingleEntry3` at `0x14036204f`
- `watchdog!WdLogSingleEntry3` at `0x140362c59`
- `watchdog!WdLogSingleEntry3` at `0x140362e68`
- `watchdog!WdLogSingleEntry3` at `0x140362f36`
- `watchdog!WdLogSingleEntry0` at `0x1403604d0`
- `watchdog!WdLogSingleEntry0` at `0x14036094f`
- `watchdog!WdLogSingleEntry0` at `0x140360f3c`
- `watchdog!WdLogSingleEntry0` at `0x14036182f`
- `watchdog!WdLogSingleEntry0` at `0x140362907`
- `watchdog!WdLogSingleEntry0` at `0x1403604d0`
- `watchdog!WdLogSingleEntry0` at `0x14036094f`
- `watchdog!WdLogSingleEntry0` at `0x140360f3c`

## string_xrefs

- `0x140361b16`: `CopyIcdFileName failed with 0x%I64x`
- `0x140362778`: `Qualcomm Adreno 530`

## pseudocode

```c
__int64 __fastcall DxgkQueryAdapterInfoImpl(struct _D3DKMT_QUERYADAPTERINFO *Src, char a2, struct DXGADAPTER *a3)
{
  struct DXGPROCESS *Current; // r13
  __int64 v7; // rcx
  unsigned int *v8; // rax
  unsigned int *v9; // rsi
  bool v10; // zf
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // r8
  struct DXGADAPTER **v20; // r9
  struct DXGADAPTER *v21; // r13
  unsigned int v22; // eax
  int PairingAdapters; // r14d
  struct DXGADAPTER *v24; // rbx
  struct DXGADAPTER *v25; // r14
  int v26; // eax
  unsigned __int8 v27; // cf
  char v28; // al
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // rdx
  unsigned __int8 v31; // r9
  __int64 v32; // r9
  unsigned __int64 v33; // rdx
  unsigned int v34; // ebx
  __int64 v35; // rcx
  __int64 v36; // r8
  struct DXGPROCESS *v37; // r13
  unsigned __int64 v38; // rdx
  unsigned __int64 v39; // rdx
  unsigned int v40; // eax
  __int64 v41; // rdx
  _DWORD *v42; // rdx
  const struct _DXGK_DISPLAYMODE_INFO *DisplayModeInfo; // rax
  int NodePerfData; // eax
  const void **v45; // rbx
  char v46; // cl
  __int64 v47; // rcx
  __int64 v48; // rax
  unsigned int v49; // r9d
  DXGADAPTER *v50; // rbx
  unsigned int *v51; // rax
  unsigned int v52; // ecx
  int v53; // eax
  int v54; // eax
  char v55; // cl
  int v56; // eax
  unsigned __int8 IsDriverUpdateInProgress; // al
  DXGPROCESS *v58; // r15
  __int64 v59; // rbx
  struct DXGPROCESS_RENDER_ADAPTER_INFO *RenderAdapterInfo; // rax
  int v61; // eax
  unsigned __int64 v62; // rdx
  int v63; // eax
  int v64; // eax
  __int64 v65; // rbx
  int v66; // eax
  int v67; // edx
  __int64 Value; // rbx
  __int64 v69; // rcx
  __int64 v70; // r8
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // rcx
  int v74; // eax
  int v75; // eax
  unsigned int v76; // eax
  ADAPTER_RENDER *v77; // r14
  __int64 v78; // rbx
  char v79; // cl
  __int64 v80; // rcx
  _BYTE *v81; // rax
  __int64 v82; // r8
  int v83; // ebx
  int v84; // ebx
  int v85; // eax
  const wchar_t *v86; // r9
  __int64 v87; // r8
  unsigned __int64 v88; // r9
  const unsigned __int16 *v89; // r8
  int v90; // eax
  unsigned int v91; // r8d
  int v92; // eax
  unsigned int v93; // r8d
  int v94; // ecx
  __int64 v95; // r8
  int v96; // eax
  __int64 v97; // r8
  int v98; // eax
  bool v99; // zf
  int v100; // eax
  __int64 HostSilo; // rax
  int v102; // ebx
  unsigned int NumDifferentPhysicalAdapters; // eax
  unsigned int v104; // r8d
  size_t v105; // r8
  DXGADAPTER *v106; // rax
  void *v107; // rbx
  const struct _UNICODE_STRING *DisplayUMDFileName; // rax
  unsigned __int64 v109; // rdx
  const unsigned __int16 **v110; // r8
  size_t v111; // rbx
  __int64 v112; // r14
  unsigned __int64 v113; // rdx
  int DisplayOnlyDriverPreferPhysicallyContiguous; // eax
  int Registry; // [rsp+50h] [rbp-208h] BYREF
  struct DXGPROCESS *v116; // [rsp+58h] [rbp-200h]
  void *Srca[2]; // [rsp+60h] [rbp-1F8h] BYREF
  size_t Size; // [rsp+70h] [rbp-1E8h]
  char v119; // [rsp+78h] [rbp-1E0h] BYREF
  char v120; // [rsp+79h] [rbp-1DFh]
  _D3DKMT_WDDM_1_3_CAPS v121; // [rsp+7Ch] [rbp-1DCh] BYREF
  struct DXGADAPTER *v122; // [rsp+80h] [rbp-1D8h] BYREF
  unsigned int v123; // [rsp+88h] [rbp-1D0h] BYREF
  __int64 v124; // [rsp+90h] [rbp-1C8h]
  char v125; // [rsp+98h] [rbp-1C0h]
  unsigned int v126; // [rsp+A0h] [rbp-1B8h] BYREF
  int *v127; // [rsp+A8h] [rbp-1B0h] BYREF
  __int128 v128; // [rsp+B0h] [rbp-1A8h]
  struct DXGPROCESS *v129; // [rsp+C0h] [rbp-198h]
  int v130; // [rsp+C8h] [rbp-190h]
  char v131; // [rsp+CCh] [rbp-18Ch]
  char v132; // [rsp+CDh] [rbp-18Bh]
  struct DXGADAPTER *v133; // [rsp+D0h] [rbp-188h] BYREF
  unsigned __int64 v134; // [rsp+D8h] [rbp-180h] BYREF
  void *v135; // [rsp+E0h] [rbp-178h]
  DXGADAPTER *v136[2]; // [rsp+E8h] [rbp-170h] BYREF
  struct _D3DKMT_QUERYADAPTERINFO v137; // [rsp+F8h] [rbp-160h] BYREF
  int v138; // [rsp+110h] [rbp-148h]
  unsigned int *v139; // [rsp+118h] [rbp-140h]
  unsigned __int64 v140; // [rsp+120h] [rbp-138h] BYREF
  _BYTE v141[56]; // [rsp+128h] [rbp-130h] BYREF
  _BYTE v142[144]; // [rsp+160h] [rbp-F8h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO Str2; // [rsp+1F0h] [rbp-68h] BYREF

  v120 = a2;
  v123 = -1;
  v124 = 0;
  if ( (qword_1401604F0 & 2) != 0 )
  {
    v125 = 1;
    v123 = 2015;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(Src, EventProfilerEnter, a3, 2015);
  }
  else
  {
    v125 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v123, 2015);
  Current = DXGPROCESS::GetCurrent();
  v116 = Current;
  Registry = 0;
  v128 = 0;
  v130 = -1;
  v131 = 0;
  v127 = &Registry;
  v132 = a2;
  v129 = Current;
  if ( !Current )
  {
    v34 = -1073741811;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 3297;
    v86 = L"Invalid process context, returning 0x%I64x";
LABEL_330:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v86, -1073741811, 0, 0, 0, 0);
    Registry = -1073741811;
LABEL_89:
    DxgkQueryAdapterInfoImpl_::_2_::LKDONFAILURE::_LKDONFAILURE(&v127);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v123);
    if ( v125 )
    {
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v35, EventProfilerExit, v36, v123);
    }
    return v34;
  }
  if ( a3 && a2 )
  {
    v34 = -1073741811;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 3306;
    v86 = L"Not valid to provide pAdapter when calling from usermode, return 0x%I64x";
    goto LABEL_330;
  }
  *(_OWORD *)Srca = 0;
  Size = 0;
  v135 = 0;
  if ( a2 )
  {
    RtlCopyFromUser(Srca, Src, 0x18u);
  }
  else
  {
    *(_OWORD *)Srca = *(_OWORD *)&Src->hAdapter;
    Size = *(_QWORD *)&Src->PrivateDriverDataSize;
  }
  v130 = HIDWORD(Srca[0]);
  if ( !Srca[1] )
  {
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 3331;
    Registry = -1073741811;
    DxgkQueryAdapterInfoImpl_::_2_::LKDONFAILURE::_LKDONFAILURE(&v127);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v123);
    if ( v125 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v11, EventProfilerExit, v12, v123);
    return 3221225485LL;
  }
  if ( !(_DWORD)Size )
  {
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 3340;
    Registry = -1073741811;
    DxgkQueryAdapterInfoImpl_::_2_::LKDONFAILURE::_LKDONFAILURE(&v127);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v123);
    if ( v125 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v14, EventProfilerExit, v15, v123);
    return 3221225485LL;
  }
  v7 = ((_DWORD)Size + 7) & 0xFFFFFFF8;
  v126 = v7;
  v138 = (Size + 7) & 0xFFFFFFF8;
  if ( (unsigned int)v7 < (unsigned int)Size )
  {
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 3354;
    Registry = -1073741811;
    DxgkQueryAdapterInfoImpl_::_2_::LKDONFAILURE::_LKDONFAILURE(&v127);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v123);
    if ( v125 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v16, EventProfilerExit, v17, v123);
    return 3221225485LL;
  }
  v8 = (unsigned int *)operator new[](v7, 1265072196, 64);
  v9 = v8;
  v139 = v8;
  v135 = v8;
  if ( !v8 )
  {
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 3364;
    Registry = -1073741801;
    DxgkQueryAdapterInfoImpl_::_2_::LKDONFAILURE::_LKDONFAILURE(&v127);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v123);
    if ( v125 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v18, EventProfilerExit, v19, v123);
    return 3221225495LL;
  }
  if ( SHIDWORD(Srca[0]) <= 47 )
  {
    if ( HIDWORD(Srca[0]) == 47 )
      goto LABEL_29;
    if ( SHIDWORD(Srca[0]) > 25 )
    {
      if ( HIDWORD(Srca[0]) != 31
        && HIDWORD(Srca[0]) != 34
        && HIDWORD(Srca[0]) != 41
        && HIDWORD(Srca[0]) != 42
        && HIDWORD(Srca[0]) != 46 )
      {
        goto LABEL_18;
      }
      goto LABEL_29;
    }
    if ( HIDWORD(Srca[0]) == 25
      || HIDWORD(Srca[0]) == 1
      || HIDWORD(Srca[0]) == 7
      || HIDWORD(Srca[0]) == 9
      || HIDWORD(Srca[0]) == 16 )
    {
      goto LABEL_29;
    }
    v10 = HIDWORD(Srca[0]) == 23;
  }
  else
  {
    if ( SHIDWORD(Srca[0]) > 63 )
    {
      if ( HIDWORD(Srca[0]) != 64 && HIDWORD(Srca[0]) != 67 && (unsigned int)(HIDWORD(Srca[0]) - 71) >= 2 )
        goto LABEL_18;
      goto LABEL_29;
    }
    if ( HIDWORD(Srca[0]) == 63
      || HIDWORD(Srca[0]) == 48
      || HIDWORD(Srca[0]) == 50
      || HIDWORD(Srca[0]) == 51
      || HIDWORD(Srca[0]) == 61 )
    {
      goto LABEL_29;
    }
    v10 = HIDWORD(Srca[0]) == 62;
  }
  if ( !v10 )
  {
LABEL_18:
    memset(v8, 0, (unsigned int)Size);
    goto LABEL_62;
  }
LABEL_29:
  if ( v120 )
    RtlCopyFromUser(v8, Srca[1], (unsigned int)Size);
  else
    memmove(v8, Srca[1], (unsigned int)Size);
LABEL_62:
  v122 = a3;
  v20 = &v122;
  if ( a3 )
    v20 = 0;
  DXGADAPTERBYHANDLE::DXGADAPTERBYHANDLE((DXGADAPTERBYHANDLE *)v136, (unsigned int)Srca[0], Current, v20, 1);
  v21 = v122;
  if ( !v122 )
  {
    v34 = -1073741811;
    WdLogSingleEntry2(3, LODWORD(Srca[0]));
    WdLogGlobalForLineNumber = 3431;
    goto LABEL_338;
  }
  *(_QWORD *)&v128 = v122;
  if ( HIDWORD(Srca[0]) == 9 )
  {
    if ( (_DWORD)Size == 48 )
      goto LABEL_339;
    v34 = -1073741811;
    WdLogSingleEntry2(3, (unsigned int)Size);
    WdLogGlobalForLineNumber = 3452;
LABEL_338:
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v9);
    Registry = -1073741811;
    DXGADAPTERBYHANDLE::~DXGADAPTERBYHANDLE((DXGADAPTERBYHANDLE *)v136);
    goto LABEL_89;
  }
  v22 = 0;
  v121.0 = 0;
  if ( HIDWORD(Srca[0]) != 67 )
    goto LABEL_67;
  if ( (_DWORD)Size != 8 )
  {
    v34 = -1073741811;
    WdLogSingleEntry2(3, (unsigned int)Size);
    WdLogGlobalForLineNumber = 3473;
    goto LABEL_338;
  }
LABEL_339:
  v22 = *v9;
  v121.0 = (struct _D3DKMT_WDDM_1_3_CAPS::$8A47ABFD9AA338C12B97FEFAAE8A2639::$9EDE049D1B618E27315CC52023435B22)*v9;
LABEL_67:
  v122 = 0;
  v133 = 0;
  PairingAdapters = DxgkpGetPairingAdapters(v21, v22, &v122, &v134, &v133, &v140, 0);
  if ( PairingAdapters >= 0 || HIDWORD(Srca[0]) == 9 || HIDWORD(Srca[0]) == 67 )
  {
    v24 = v133;
  }
  else
  {
    v24 = 0;
    PairingAdapters = DxgkpGetPairingAdapters(v21, v121.Value, &v122, &v134, 0, 0, 0);
  }
  if ( PairingAdapters >= 0 )
  {
    v25 = v122;
    if ( v122 != v21 && v24 != v21 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 3530;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"(pRenderAdapter == pAdapterIn) || (pDisplayAdapter == pAdapterIn)",
        3530,
        0,
        0,
        0,
        0);
    }
    if ( v24 && !*((_QWORD *)v24 + 406) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 3532;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"(pDisplayAdapter == NULL) || (pDisplayAdapter->IsDisplayAdapter())",
        3532,
        0,
        0,
        0,
        0);
    }
    if ( !v25 || !*((_QWORD *)v25 + 407) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 3534;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"(pRenderAdapter != NULL) && (pRenderAdapter->IsRenderAdapter())",
        3534,
        0,
        0,
        0,
        0);
    }
    if ( HIDWORD(Srca[0]) > 0x1B || (v26 = 138619200, v27 = _bittest(&v26, HIDWORD(Srca[0])), v28 = 1, !v27) )
      v28 = 0;
    *((_QWORD *)&v128 + 1) = v25;
    v131 = v28;
    if ( v21 == v25 && *((_BYTE *)v21 + 209) || v25 && *((_BYTE *)v25 + 209) && !v28 )
    {
      if ( HIDWORD(Srca[0]) > 0x39 || (v48 = 0x210F85840908010LL, !_bittest64(&v48, HIDWORD(Srca[0]))) )
      {
        if ( HIDWORD(Srca[0]) != 68 )
        {
          DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)&Str2, v25, 1u);
          if ( *((_DWORD *)v25 + 50) == 1 )
          {
            *(void **)&v137.hAdapter = Srca[0];
            *(_QWORD *)&v137.PrivateDriverDataSize = Size;
            v137.pPrivateDriverData = v9;
            Registry = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendQueryAdapterInfo(
                         (struct DXGADAPTER *)((char *)v25 + 4792),
                         v116,
                         &v137,
                         v49);
            if ( Registry >= 0 )
            {
              Registry = PostProcessUMDFileName(SHIDWORD(Srca[0]), v9, v126);
            }
            else
            {
              WdLogSingleEntry2(3, LODWORD(Srca[0]));
              WdLogGlobalForLineNumber = 3586;
            }
          }
          else
          {
            Registry = -1073741130;
          }
          DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)&Str2);
          goto LABEL_86;
        }
      }
    }
    COREADAPTERACCESS::COREADAPTERACCESS((COREADAPTERACCESS *)v142, v25, v24);
    DXGADAPTER::ReleaseReference(v25, v29);
    if ( v24 )
      DXGADAPTER::ReleaseReference(v24, v30);
    if ( HIDWORD(Srca[0]) == 67 || HIDWORD(Srca[0]) == 9 )
    {
      Registry = COREADAPTERACCESS::AcquireShared((COREADAPTERACCESS *)v142, 0);
      if ( Registry >= 0 )
      {
        if ( !v24 || !*((_QWORD *)v24 + 406) )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 3619;
          DxgkLogInternalTriageEvent(
            0,
            262146,
            -1,
            (unsigned int)L"(pDisplayAdapter != NULL) && (pDisplayAdapter->IsDisplayAdapter())",
            3619,
            0,
            0,
            0,
            0);
        }
        if ( HIDWORD(Srca[0]) == 9 )
        {
          DisplayModeInfo = ADAPTER_DISPLAY::GetDisplayModeInfo(*((ADAPTER_DISPLAY **)v24 + 406), *v9);
          if ( *(_DWORD *)DisplayModeInfo )
          {
            *(_OWORD *)(v9 + 1) = *(_OWORD *)DisplayModeInfo;
            *(_OWORD *)(v9 + 5) = *((_OWORD *)DisplayModeInfo + 1);
            *((_OWORD *)v9 + 2) = *(_OWORD *)((char *)DisplayModeInfo + 28);
          }
          else
          {
            Registry = -1071774919;
            WdLogSingleEntry2(3, *v9);
            WdLogGlobalForLineNumber = 3637;
          }
        }
        else if ( HIDWORD(Srca[0]) == 67 )
        {
          v126 = *v9;
          v121.0 = 0;
          *(_QWORD *)&Str2.Type = 33;
          *(_QWORD *)&Str2.InputDataSize = 4;
          *(_QWORD *)&Str2.Flags.0 = 0;
          HIDWORD(Str2.hKmdProcessHandle) = 0;
          Str2.pOutputData = &v121;
          Str2.OutputDataSize = 4;
          Str2.pInputData = &v126;
          Registry = DXGADAPTER::DdiQueryAdapterInfo(v24, &Str2);
          if ( Registry < 0 )
          {
            WdLogSingleEntry2(3, *v9);
            WdLogGlobalForLineNumber = 3672;
          }
          else
          {
            v9[1] = v121.Value;
          }
        }
        v37 = v116;
        goto LABEL_109;
      }
    }
    else
    {
      DXGPAIREDADAPTERSTOPRESETLOCKSHARED::DXGPAIREDADAPTERSTOPRESETLOCKSHARED(
        (DXGPAIREDADAPTERSTOPRESETLOCKSHARED *)v141,
        v25,
        v24,
        v31);
      if ( *((_DWORD *)v21 + 50) == 1 && *((_DWORD *)v25 + 50) == 1 && (!v24 || *((_DWORD *)v24 + 50) == 1) )
      {
        if ( SHIDWORD(Srca[0]) > 41 )
        {
          if ( SHIDWORD(Srca[0]) <= 61 )
          {
            if ( HIDWORD(Srca[0]) == 61 )
            {
              if ( (_DWORD)Size != 56 )
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 5254;
                goto LABEL_107;
              }
              NodePerfData = DXGADAPTER::GetNodePerfData(v25, (struct _D3DKMT_NODE_PERFDATA *)v9);
              goto LABEL_161;
            }
            if ( SHIDWORD(Srca[0]) > 51 )
            {
              if ( HIDWORD(Srca[0]) != 52 )
              {
                if ( HIDWORD(Srca[0]) != 53 )
                {
                  if ( HIDWORD(Srca[0]) != 54 )
                  {
                    if ( HIDWORD(Srca[0]) != 55 )
                    {
                      if ( HIDWORD(Srca[0]) != 56 )
                      {
                        if ( HIDWORD(Srca[0]) == 57 )
                          goto LABEL_105;
                        if ( HIDWORD(Srca[0]) != 58 )
                        {
                          if ( HIDWORD(Srca[0]) == 59 )
                          {
LABEL_130:
                            if ( (_DWORD)Size != 4 )
                            {
                              Registry = -1073741811;
                              WdLogSingleEntry2(3, (unsigned int)Size);
                              WdLogGlobalForLineNumber = 4519;
                              goto LABEL_107;
                            }
                            Registry = -1073741823;
                            v106 = v25;
                            if ( HIDWORD(Srca[0]) == 22 )
                              v106 = v21;
                            if ( !v106 )
                              goto LABEL_107;
                            DXGADAPTER::QueryWDDM1_3Caps(v106, (struct _D3DKMT_WDDM_1_3_CAPS *)v9);
                            if ( v21 != v25 )
                            {
                              v121.0 = 0;
                              DXGADAPTER::QueryWDDM1_3Caps(v25, &v121);
                              *v9 = *(_BYTE *)&v121.0 & 0x20 | *v9 & 0xFFFFFFDF;
                            }
                            goto LABEL_223;
                          }
                          if ( (_DWORD)Size != 80 )
                          {
                            Registry = -1073741811;
                            WdLogSingleEntry2(3, (unsigned int)Size);
                            WdLogGlobalForLineNumber = 4101;
                            goto LABEL_107;
                          }
                          if ( !*((_QWORD *)v21 + 27) )
                          {
                            WdLogSingleEntry0(1);
                            WdLogGlobalForLineNumber = 4109;
                            DxgkLogInternalTriageEvent(
                              0,
                              262146,
                              -1,
                              (unsigned int)L"pAdapterIn->GetFdo() != NULL",
                              4109,
                              0,
                              0,
                              0,
                              0);
                          }
                          v45 = (const void **)((*(_QWORD *)(*((_QWORD *)v21 + 27) + 64LL) + 4896LL)
                                              & -(__int64)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v21 + 27) + 64LL) + 4904LL) != 0));
                          if ( !v45 )
                          {
                            Registry = -1073741823;
                            goto LABEL_107;
                          }
                          memset(v9, 0, 0x50u);
                          v105 = 78;
                          if ( *(_WORD *)v45 < 0x4Eu )
                            v105 = *(unsigned __int16 *)v45;
                          memmove(v9, v45[1], v105);
LABEL_127:
                          Registry = 0;
                          goto LABEL_107;
                        }
LABEL_170:
                        if ( (_DWORD)Size != 12 )
                        {
                          Registry = -1073741811;
                          WdLogSingleEntry2(3, (unsigned int)Size);
                          WdLogGlobalForLineNumber = 4373;
                          goto LABEL_107;
                        }
                        Registry = -1073741823;
                        if ( HIDWORD(Srca[0]) == 17 )
                          v25 = v21;
                        if ( !v25 )
                          goto LABEL_107;
                        DXGADAPTER::QueryWDDM1_2Caps(v25, (struct _D3DKMT_WDDM_1_2_CAPS *)v9);
                        goto LABEL_127;
                      }
LABEL_206:
                      if ( (_DWORD)Size != 4 )
                      {
                        Registry = -1073741811;
                        WdLogSingleEntry2(3, (unsigned int)Size);
                        WdLogGlobalForLineNumber = 4274;
                        goto LABEL_107;
                      }
                      Registry = -1073741823;
                      if ( HIDWORD(Srca[0]) == 13 )
                        v25 = v21;
                      if ( !v25 )
                        goto LABEL_107;
                      v67 = *((_DWORD *)v25 + 783);
                      *v9 = v67;
                      if ( (*((_DWORD *)v116 + 102) & 0x100) == 0
                        || *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v116 + 75) + 600LL) + 392LL) > 0x10u )
                      {
                        v37 = v116;
                        goto LABEL_189;
                      }
                      v54 = 2600;
                      v37 = v116;
                      if ( v67 <= 2600 )
                        goto LABEL_189;
                      goto LABEL_205;
                    }
                    goto LABEL_213;
                  }
                  goto LABEL_351;
                }
LABEL_184:
                if ( (_DWORD)Size != 12 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 4160;
                  goto LABEL_107;
                }
                Registry = -1073741823;
                if ( HIDWORD(Srca[0]) == 6 )
                  v25 = v21;
                v37 = v116;
                if ( !v25 )
                  goto LABEL_108;
                v47 = *(_QWORD *)(*((_QWORD *)v25 + 27) + 64LL);
                *v9 = *(_DWORD *)(v47 + 1144);
                v9[1] = *(unsigned __int16 *)(v47 + 1150);
                v9[2] = (unsigned __int16)*(_DWORD *)(v47 + 1148);
                goto LABEL_189;
              }
LABEL_515:
              if ( (_DWORD)Size != 16 )
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 4072;
                goto LABEL_107;
              }
              if ( HIDWORD(Srca[0]) == 4 )
                v25 = v21;
              v37 = v116;
              if ( !v25 )
              {
                Registry = -1073741823;
                goto LABEL_108;
              }
              *(_OWORD *)v9 = *(_OWORD *)((char *)v25 + 300);
              goto LABEL_189;
            }
            if ( HIDWORD(Srca[0]) == 51 )
              goto LABEL_464;
            if ( HIDWORD(Srca[0]) == 42 )
            {
              if ( (_DWORD)Size != 56 )
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 3984;
                goto LABEL_107;
              }
              NumDifferentPhysicalAdapters = DXGADAPTER::GetNumDifferentPhysicalAdapters(v25);
              if ( v104 >= NumDifferentPhysicalAdapters )
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, *v9);
                WdLogGlobalForLineNumber = 4008;
              }
              else
              {
                VIDMM_EXPORT::VidMmGetTotalSegmentSize(
                  *(VIDMM_EXPORT **)(*((_QWORD *)v25 + 407) + 760LL),
                  *(const struct VIDMM_GLOBAL **)(*((_QWORD *)v25 + 407) + 768LL),
                  v104,
                  (unsigned __int64 *)v9 + 4,
                  (unsigned __int64 *)v9 + 5,
                  (unsigned __int64 *)v9 + 6,
                  (unsigned __int64 *)v9 + 1,
                  (unsigned __int64 *)v9 + 2,
                  (unsigned __int64 *)v9 + 3);
              }
              goto LABEL_223;
            }
            if ( HIDWORD(Srca[0]) != 43 )
            {
              if ( HIDWORD(Srca[0]) == 44 )
              {
                if ( (_DWORD)Size == 1 )
                {
                  *(_BYTE *)v9 = 1;
                  if ( *((_DWORD *)v25 + 105) == 1297040209 )
                  {
                    wcscpy((wchar_t *)&Str2, L"Qualcomm Adreno 530");
                    if ( !wcsncmp_0(*((const wchar_t **)v25 + 256), (const wchar_t *)&Str2, 0x14u) )
                    {
                      v37 = v116;
                      if ( (*(_DWORD *)(*((_QWORD *)v25 + 390) + 16LL) & 0x10) == 0 )
                        *(_BYTE *)v9 = 0;
                      goto LABEL_108;
                    }
                  }
                }
                else
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 5104;
                }
                goto LABEL_107;
              }
              if ( HIDWORD(Srca[0]) != 45 )
              {
                switch ( HIDWORD(Srca[0]) )
                {
                  case '.':
                    if ( (_DWORD)Size == 12 )
                    {
                      if ( v9[1] )
                      {
                        v37 = v116;
                        if ( *v9 < 0x10 )
                          *(_BYTE *)(*((_QWORD *)v25 + 407) + *v9 + 1224LL) = v9[2] != 0;
                        goto LABEL_108;
                      }
                      v77 = (ADAPTER_RENDER *)*((_QWORD *)v25 + 407);
                      v78 = *v9;
                      if ( ADAPTER_RENDER::IsMultiPlaneOverlaySupported(v77) && (unsigned int)v78 < 0x10 )
                        v79 = *((_BYTE *)v77 + v78 + 1224);
                      else
                        v79 = 0;
                      v9[2] = v79 != 0;
                    }
                    else
                    {
                      Registry = -1073741811;
                      WdLogSingleEntry2(3, (unsigned int)Size);
                      WdLogGlobalForLineNumber = 5179;
                    }
                    goto LABEL_107;
                  case '/':
                    if ( (_DWORD)Size == 8 )
                    {
                      v122 = 0;
                      v37 = v116;
                      DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE((DXGDEVICEBYHANDLE *)&v134, *v9, v116, &v122);
                      if ( v122 )
                      {
                        *((_BYTE *)v9 + 4) = *((_BYTE *)v122 + 1954);
                        v102 = 0;
                      }
                      else
                      {
                        WdLogSingleEntry1(2);
                        WdLogGlobalForLineNumber = 5216;
                        DxgkLogInternalTriageEvent(
                          0,
                          0x40000,
                          -1,
                          (unsigned int)L"Invalid hDevice (0x%I64x) specified",
                          *v9,
                          0,
                          0,
                          0,
                          0);
                        v102 = -1073741811;
                      }
                      Registry = v102;
                      ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v134);
                      goto LABEL_108;
                    }
                    Registry = -1073741811;
                    WdLogSingleEntry2(3, (unsigned int)Size);
                    WdLogGlobalForLineNumber = 5201;
                    goto LABEL_107;
                  case '0':
                    v65 = 0;
                    v37 = v116;
                    if ( (*((_DWORD *)v116 + 102) & 0x200) != 0 )
                    {
                      HostSilo = PsGetHostSilo();
                      v65 = PsAttachSiloToCurrentThread(HostSilo);
                    }
                    Registry = DxgkpQueryRegistry(v25, v9, Size);
                    if ( v65 )
                      PsAttachSiloToCurrentThread(v65);
                    goto LABEL_108;
                }
                if ( HIDWORD(Srca[0]) != 49 )
                {
LABEL_464:
                  if ( (unsigned int)Size < 8 )
                  {
                    Registry = -1073741811;
                    WdLogSingleEntry2(3, (unsigned int)Size);
                    WdLogGlobalForLineNumber = 5233;
                    goto LABEL_107;
                  }
                  LOBYTE(v32) = HIDWORD(Srca[0]) == 50;
                  NodePerfData = DpiReadBlockListInfo(*((_QWORD *)v25 + 27), v9, (unsigned int)Size, v32);
                  goto LABEL_161;
                }
                if ( (_DWORD)Size != 8 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 4415;
                  goto LABEL_107;
                }
                NodePerfData = ADAPTER_RENDER::GetKmdFileVersion(
                                 *((ADAPTER_RENDER **)v25 + 407),
                                 (union _LARGE_INTEGER *)v9);
LABEL_161:
                Registry = NodePerfData;
                goto LABEL_107;
              }
              if ( (_DWORD)Size != 4 )
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 5151;
                goto LABEL_107;
              }
              if ( ADAPTER_RENDER::IsMultiPlaneOverlaySupported(*((ADAPTER_RENDER **)v25 + 407)) )
              {
                v80 = *(_QWORD *)(*((_QWORD *)v25 + 407) + 16LL);
                v81 = (_BYTE *)(v80 + 3177);
                if ( (!*(_QWORD *)(v80 + 1224) || !*v81) && (!*(_QWORD *)(v80 + 1232) || !*v81) )
                {
LABEL_281:
                  *v9 = 0;
                  goto LABEL_107;
                }
              }
LABEL_243:
              *v9 = 1;
              goto LABEL_107;
            }
            if ( (_DWORD)Size != 4 )
            {
              Registry = -1073741811;
              WdLogSingleEntry2(3, (unsigned int)Size);
              WdLogGlobalForLineNumber = 5079;
              goto LABEL_107;
            }
            v99 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)v25 + 407) + 16LL) + 3177LL) == 0;
            goto LABEL_434;
          }
          if ( SHIDWORD(Srca[0]) <= 73 )
          {
            switch ( HIDWORD(Srca[0]) )
            {
              case 'I':
                if ( (_DWORD)Size != 4 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 3863;
                  goto LABEL_107;
                }
                if ( !(_BYTE)word_140162E5D || !*((_BYTE *)v25 + 3071) )
                {
                  Registry = -1073741637;
                  WdLogSingleEntry3(4, v9, v25, -1073741637);
                  WdLogGlobalForLineNumber = 3877;
                  goto LABEL_107;
                }
                v63 = *((_DWORD *)v25 + 776) >> 5;
                goto LABEL_557;
              case '>':
                if ( (_DWORD)Size != 64 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 5271;
                  goto LABEL_107;
                }
                NodePerfData = DXGADAPTER::GetAdapterPerfData(v25, (struct _D3DKMT_ADAPTER_PERFDATA *)v9);
                goto LABEL_161;
              case '?':
                if ( (_DWORD)Size != 40 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 5288;
                  goto LABEL_107;
                }
                NodePerfData = DXGADAPTER::GetAdapterPerfDataCaps(v25, (struct _D3DKMT_ADAPTER_PERFDATACAPS *)v9);
                goto LABEL_161;
              case '@':
                if ( (_DWORD)Size != 132 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 5305;
                  goto LABEL_107;
                }
                NodePerfData = DXGADAPTER::GetGpuVersion(v25, (struct _D3DKMT_GPUVERSION *)v9);
                goto LABEL_161;
              case 'A':
              case 'B':
                if ( (_DWORD)Size != 0x2000 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 5324;
                  goto LABEL_107;
                }
                Registry = -1073741823;
                if ( HIDWORD(Srca[0]) == 65 )
                  v25 = v21;
                if ( !v25 )
                  goto LABEL_107;
                DXGADAPTER::GetDeviceDescriptor(v25, 0x2000u, (unsigned __int16 *)v9);
                goto LABEL_127;
              case 'D':
                if ( (_DWORD)Size != 1 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 5372;
                  goto LABEL_107;
                }
                if ( v25 )
                  v46 = *((_BYTE *)v25 + 210);
                else
                  v46 = 0;
                *(_BYTE *)v9 = v46;
                goto LABEL_127;
              case 'F':
                if ( (_DWORD)Size == 4 )
                {
                  DXGADAPTER::QueryWDDM2_7Caps(v25, (struct _D3DKMT_WDDM_2_7_CAPS *)v9);
                }
                else
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 4567;
                }
                goto LABEL_107;
              case 'G':
                if ( (_DWORD)Size == 524 )
                {
                  if ( *v9
                    || (DisplayUMDFileName = (const struct _UNICODE_STRING *)ADAPTER_RENDER::GetDisplayUMDFileName(*((_QWORD *)v25 + 407)),
                        (unsigned int)IsNullUmdDriver(DisplayUMDFileName)) )
                  {
                    v84 = -1073741811;
                  }
                  else
                  {
                    v84 = RtlStringCbCopyNW((unsigned __int16 *)v9 + 2, v109, v110[1], *(unsigned __int16 *)v110);
                  }
                  Registry = v84;
                  if ( v84 < 0 )
                  {
                    WdLogSingleEntry3(4, v9, v25, v84);
                    WdLogGlobalForLineNumber = 5356;
                  }
                }
                else
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 5347;
                }
                goto LABEL_107;
              case 'H':
                if ( (_DWORD)Size != 12 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 5392;
                  goto LABEL_107;
                }
                NodePerfData = DXGADAPTER::QueryTrackedWorkloadSupport(
                                 v25,
                                 *v9,
                                 (enum DXGK_ENGINE_TYPE)v9[1],
                                 (int *)v9 + 2);
                goto LABEL_161;
            }
          }
          else
          {
            switch ( HIDWORD(Srca[0]) )
            {
              case 'J':
                if ( (_DWORD)Size == 8 )
                {
                  if ( v24 )
                  {
                    *(_QWORD *)v9 = 0;
                    v113 = 0;
                    if ( !*((_QWORD *)v24 + 407) )
                    {
                      DisplayOnlyDriverPreferPhysicallyContiguous = ADAPTER_DISPLAY::GetDisplayOnlyDriverPreferPhysicallyContiguous(*((ADAPTER_DISPLAY **)v24 + 406));
                      v113 = DisplayOnlyDriverPreferPhysicallyContiguous
                           ^ (*(_QWORD *)v9
                            ^ DisplayOnlyDriverPreferPhysicallyContiguous)
                           & 0xFFFFFFFFFFFFFFFEuLL;
                      *(_QWORD *)v9 = v113;
                    }
                    if ( *((_BYTE *)v24 + 3098) )
                    {
                      v113 |= 2u;
                      *(_QWORD *)v9 = v113;
                    }
                    if ( (*((_DWORD *)v24 + 776) & 0x100) != 0 )
                      *(_QWORD *)v9 = v113 | 4;
                  }
                  else
                  {
                    Registry = -1073741811;
                    WdLogSingleEntry1(3);
                    WdLogGlobalForLineNumber = 5416;
                  }
                }
                else
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 5410;
                }
                goto LABEL_107;
              case 'K':
                if ( (_DWORD)Size == 4 )
                {
                  DXGADAPTER::QueryWDDM2_9Caps(v25, (struct _D3DKMT_WDDM_2_9_CAPS *)v9);
                }
                else
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 4585;
                }
                goto LABEL_107;
              case 'L':
                if ( (_DWORD)Size != 4 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 5446;
                  goto LABEL_107;
                }
                v66 = *((_DWORD *)v25 + 649);
                if ( (v66 & 0x10000) != 0 )
                {
                  *v9 = 3;
                  goto LABEL_107;
                }
                v37 = v116;
                if ( (v66 & 0x8000) != 0 )
                {
                  *v9 = 2;
                  goto LABEL_108;
                }
                v85 = (unsigned __int8)v66 >> 4;
LABEL_328:
                *v9 = v85 & 1;
                goto LABEL_108;
              case 'M':
                if ( (_DWORD)Size == 4 )
                {
                  DXGADAPTER::QueryWDDM3_0Caps(v25, (struct _D3DKMT_WDDM_3_0_CAPS *)v9);
                }
                else
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 4603;
                }
                goto LABEL_107;
              case 'N':
                if ( (unsigned int)Size >= 0x208 )
                {
                  v82 = *((_QWORD *)v25 + 407);
                  if ( *(_WORD *)(v82 + 592) )
                    v83 = RtlStringCbCopyNW(
                            (unsigned __int16 *)v9,
                            (unsigned int)(HIDWORD(Srca[0]) - 78),
                            *(const unsigned __int16 **)(v82 + 600),
                            *(unsigned __int16 *)(v82 + 592));
                  else
                    v83 = -1073741811;
                  Registry = v83;
                  if ( v83 < 0 )
                  {
                    WdLogSingleEntry3(4, v9, v25, v83);
                    WdLogGlobalForLineNumber = 3753;
                  }
                }
                else
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 3744;
                }
                goto LABEL_107;
              case 'O':
                v111 = 520;
                if ( (unsigned int)Size < 0x208 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 3767;
                  goto LABEL_107;
                }
                v112 = *(_QWORD *)(*((_QWORD *)v25 + 27) + 64LL);
                memset(v9, 0, 0x208u);
                if ( *(_WORD *)(v112 + 2896) <= 0x208u )
                  v111 = *(unsigned __int16 *)(v112 + 2896);
                memmove(v9, *(const void **)(v112 + 2904), v111);
                *((_WORD *)v9 + 1) = 92;
                goto LABEL_127;
              case 'P':
                if ( (_DWORD)Size != 4 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 4621;
                  goto LABEL_107;
                }
                *v9 = 0;
                v37 = v116;
                if ( !*((_QWORD *)v25 + 407) )
                  goto LABEL_108;
                v85 = *((_DWORD *)v25 + 648) >> 11;
                goto LABEL_328;
              case 'Q':
                if ( (_DWORD)Size != 4 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 3888;
                  goto LABEL_107;
                }
                if ( !(_BYTE)word_140162E5D || !*((_BYTE *)v25 + 3071) )
                {
                  Registry = -1073741637;
                  WdLogSingleEntry3(4, v9, v25, -1073741637);
                  WdLogGlobalForLineNumber = 3902;
                  goto LABEL_107;
                }
                v63 = *((_DWORD *)v25 + 776) >> 7;
LABEL_557:
                LOBYTE(v63) = ~(_BYTE)v63;
LABEL_248:
                v64 = v63 & 1;
LABEL_249:
                *v9 = v64;
                goto LABEL_107;
            }
          }
LABEL_565:
          Registry = -1073741811;
          WdLogSingleEntry2(3, SHIDWORD(Srca[0]));
          WdLogGlobalForLineNumber = 5478;
          goto LABEL_107;
        }
        if ( HIDWORD(Srca[0]) == 41 )
        {
          if ( (_DWORD)Size != 24 )
          {
            Registry = -1073741811;
            WdLogSingleEntry2(3, (unsigned int)Size);
            WdLogGlobalForLineNumber = 4823;
            goto LABEL_107;
          }
          NodePerfData = DxgkReadPnPRegistryPath(v25, *v9, v9[1], *((_QWORD *)v9 + 1), *((_QWORD *)v9 + 2));
          goto LABEL_161;
        }
        if ( SHIDWORD(Srca[0]) <= 22 )
        {
          if ( HIDWORD(Srca[0]) == 22 )
            goto LABEL_130;
          if ( SHIDWORD(Srca[0]) <= 11 )
          {
            if ( HIDWORD(Srca[0]) == 11 )
            {
LABEL_213:
              if ( (_DWORD)Size != 4 )
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 4210;
                goto LABEL_107;
              }
              Registry = -1073741823;
              if ( HIDWORD(Srca[0]) == 11 )
                v25 = v21;
              if ( !v25 )
                goto LABEL_107;
              v55 = 0;
              v119 = 0;
              v56 = *((_DWORD *)v25 + 111);
              if ( (v56 & 0x20) != 0 || (v56 & 4) != 0 )
              {
                IsDriverUpdateInProgress = 0;
              }
              else
              {
                IsDriverUpdateInProgress = DpiIsDriverUpdateInProgress(*((_QWORD *)v25 + 27), &v119);
                v55 = v119;
              }
              *v9 = IsDriverUpdateInProgress;
              if ( v55 )
              {
                v107 = (void *)*((_QWORD *)v25 + 27);
                ObfReferenceObject(v107);
                DXGPAIREDADAPTERSTOPRESETLOCKSHARED::Release((DXGPAIREDADAPTERSTOPRESETLOCKSHARED *)v141);
                DxgkInvalidateDeviceState(v107);
                ObfDereferenceObject(v107);
              }
LABEL_223:
              v37 = v116;
              goto LABEL_189;
            }
            if ( HIDWORD(Srca[0]) )
            {
              if ( HIDWORD(Srca[0]) == 1 )
              {
                if ( (_DWORD)Size == 524 )
                {
                  v90 = ADAPTER_RENDER::CopyUmdFileName(
                          *((ADAPTER_RENDER **)v25 + 407),
                          (struct _D3DKMT_UMDFILENAMEINFO *)v9);
                  Registry = v90;
                  if ( v90 < 0 )
                  {
                    WdLogSingleEntry3(4, v9, v25, v90);
                    WdLogGlobalForLineNumber = 3731;
                  }
                }
                else
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 3722;
                }
                goto LABEL_107;
              }
              v62 = (unsigned int)(HIDWORD(Srca[0]) - 2);
              switch ( HIDWORD(Srca[0]) )
              {
                case 2:
                  if ( (_DWORD)Size == 528 )
                  {
                    v37 = v116;
                    v87 = *((_QWORD *)v25 + 407);
                    if ( (*((_DWORD *)v116 + 102) & 8) != 0 )
                    {
                      v9[130] = *(_DWORD *)(v87 + 712);
                      v9[131] = *(_DWORD *)(v87 + 716);
                      v88 = *(unsigned __int16 *)(v87 + 696);
                      v89 = *(const unsigned __int16 **)(v87 + 704);
                    }
                    else
                    {
                      v9[130] = *(_DWORD *)(v87 + 688);
                      v9[131] = *(_DWORD *)(v87 + 692);
                      v88 = *(unsigned __int16 *)(v87 + 672);
                      v89 = *(const unsigned __int16 **)(v87 + 680);
                    }
                    Registry = RtlStringCbCopyNW((unsigned __int16 *)v9, v62, v89, v88);
                    if ( Registry < 0 )
                    {
                      WdLogSingleEntry1(2);
                      WdLogGlobalForLineNumber = 3939;
                      DxgkLogInternalTriageEvent(
                        0,
                        0x40000,
                        -1,
                        (unsigned int)L"CopyIcdFileName failed with 0x%I64x",
                        Registry,
                        0,
                        0,
                        0,
                        0);
                    }
                    goto LABEL_108;
                  }
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 3916;
                  goto LABEL_107;
                case 3:
                  if ( (_DWORD)Size != 24 )
                  {
                    Registry = -1073741811;
                    WdLogSingleEntry2(3, (unsigned int)Size);
                    WdLogGlobalForLineNumber = 3955;
                    goto LABEL_107;
                  }
                  v122 = 0;
                  (*(void (__fastcall **)(_QWORD, _QWORD, struct DXGADAPTER **, struct DXGADAPTER **, struct DXGADAPTER **, unsigned int *, unsigned int *, unsigned int *))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v25 + 407) + 760LL) + 8LL) + 64LL))(
                    *(_QWORD *)(*((_QWORD *)v25 + 407) + 768LL),
                    0,
                    &v122,
                    &v122,
                    &v122,
                    v9,
                    v9 + 2,
                    v9 + 4);
                  goto LABEL_127;
                case 4:
                  goto LABEL_515;
                case 5:
                  if ( (_DWORD)Size != 12 )
                  {
                    Registry = -1073741811;
                    WdLogSingleEntry2(3, (unsigned int)Size);
                    WdLogGlobalForLineNumber = 4139;
                    goto LABEL_107;
                  }
                  NodePerfData = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v25 + 407) + 736LL)
                                                                                               + 8LL)
                                                                                   + 528LL))(
                                   *(_QWORD *)(*((_QWORD *)v25 + 407) + 744LL),
                                   v9);
                  goto LABEL_161;
                case 6:
                  goto LABEL_184;
              }
              if ( HIDWORD(Srca[0]) != 7 )
              {
                if ( HIDWORD(Srca[0]) == 8 )
                {
LABEL_351:
                  if ( (_DWORD)Size != 2080 )
                  {
                    Registry = -1073741811;
                    WdLogSingleEntry2(3, (unsigned int)Size);
                    WdLogGlobalForLineNumber = 4185;
                    goto LABEL_107;
                  }
                  Registry = -1073741823;
                  if ( HIDWORD(Srca[0]) == 8 )
                    v25 = v21;
                  if ( !v25 )
                    goto LABEL_107;
                  NodePerfData = DpiQueryAdapterRegistryInfo(*((_QWORD *)v25 + 27), v9);
                  goto LABEL_161;
                }
                goto LABEL_565;
              }
              if ( (_DWORD)Size != 12 )
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 4025;
                goto LABEL_107;
              }
              v71 = *(_QWORD *)(*((_QWORD *)v25 + 407) + 760LL);
              v58 = v116;
              v72 = *((_QWORD *)v116 + 8);
              if ( v72 )
                v73 = *(_QWORD *)(v72 + 8LL * (unsigned int)(*(_DWORD *)v71 - 1));
              else
                v73 = 0;
              v61 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)(v71 + 8) + 360LL))(v73, v9);
            }
            else
            {
              memset(&Str2, 0, 24);
              *(_OWORD *)&Str2.OutputDataSize = 0;
              Str2.pOutputData = v9;
              Str2.OutputDataSize = Size;
              v58 = v116;
              if ( (*((_DWORD *)v116 + 102) & 0x100) != 0 )
              {
                Str2.Flags.Value = 1;
                Str2.Flags.Value = (2 * (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)v116 + 75) + 600LL) + 336LL) & 1)) | 1;
              }
              v59 = *((_QWORD *)v25 + 407);
              KeEnterCriticalRegion();
              ExAcquirePushLockSharedEx(v59 + 72, 0);
              _InterlockedAdd((volatile signed __int32 *)(v59 + 88), 1u);
              RenderAdapterInfo = DXGPROCESS::GetRenderAdapterInfo(v58, *((_DWORD *)v25 + 60));
              if ( RenderAdapterInfo )
                Str2.hKmdProcessHandle = (HANDLE)*((_QWORD *)RenderAdapterInfo + 6);
              _InterlockedDecrement((volatile signed __int32 *)(v59 + 88));
              ExReleasePushLockSharedEx(v59 + 72, 0);
              KeLeaveCriticalRegion();
              v61 = DXGADAPTER::DdiQueryAdapterInfo(v25, &Str2);
            }
            Registry = v61;
            v37 = v58;
            goto LABEL_108;
          }
          switch ( HIDWORD(Srca[0]) )
          {
            case 0xC:
              if ( (_DWORD)Size != 4 )
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 4252;
                goto LABEL_107;
              }
              *v9 = 0;
              *v9 = (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v25 + 407) + 16LL) + 2596LL) >> 5) & 1;
              goto LABEL_127;
            case 0xD:
              goto LABEL_206;
            case 0xF:
LABEL_105:
              if ( (_DWORD)Size != 4 )
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 4309;
                goto LABEL_107;
              }
              Registry = -1073741823;
              v50 = v25;
              if ( HIDWORD(Srca[0]) == 15 )
                v50 = v21;
              if ( !v50 )
                goto LABEL_107;
              LODWORD(v51) = DXGADAPTER::GetAdapterType(v50);
              v52 = *v51;
              *v9 = *v51;
              v53 = v52 ^ ((unsigned __int16)v52 ^ (unsigned __int16)(*((unsigned __int8 *)v25 + 212) << 8)) & 0x100;
              *v9 = v53;
              v37 = v116;
              if ( *((_DWORD *)v50 + 874) )
              {
                v54 = v53 | 0x2000;
LABEL_205:
                *v9 = v54;
              }
LABEL_189:
              Registry = 0;
              goto LABEL_108;
            case 0x10:
              if ( (_DWORD)Size != 8 )
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 4342;
                goto LABEL_107;
              }
              if ( (*((_DWORD *)DXGPROCESS::GetCurrent() + 102) & 4) == 0 )
              {
                Registry = -1073741790;
                WdLogSingleEntry1(3);
                WdLogGlobalForLineNumber = 4351;
                goto LABEL_107;
              }
              DXGPAIREDADAPTERSTOPRESETLOCKSHARED::Release((DXGPAIREDADAPTERSTOPRESETLOCKSHARED *)v141);
              NodePerfData = OutputDuplThunks<_D3DKMT_OUTPUTDUPLCONTEXTSCOUNT *>::RunForAdapter(
                               v21,
                               (__int64)lambda_d61da4d51b31b33ef5e605a1dd45d7b4_::_lambda_invoker_cdecl_);
              goto LABEL_161;
            case 0x11:
              goto LABEL_170;
            case 0x12:
              if ( (_DWORD)Size != 8 )
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 4397;
                goto LABEL_107;
              }
              NodePerfData = ADAPTER_RENDER::GetUmdFileVersion(
                               *((ADAPTER_RENDER **)v25 + 407),
                               (union _LARGE_INTEGER *)v9);
              goto LABEL_161;
            case 0x13:
              if ( (_DWORD)Size != 4 )
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 4433;
                goto LABEL_107;
              }
              if ( v24 && (*((_DWORD *)v24 + 111) & 0x100) != 0
                || !*(_BYTE *)(*(_QWORD *)(*((_QWORD *)v25 + 407) + 16LL) + 3067LL) )
              {
                goto LABEL_281;
              }
              goto LABEL_243;
          }
          if ( HIDWORD(Srca[0]) != 20 )
          {
            if ( HIDWORD(Srca[0]) == 21 )
            {
              if ( (_DWORD)Size == 520 )
              {
                if ( (unsigned int)Feature_DisplayMux_PostGA_BugBundle_3__private_IsEnabledDeviceUsageNoInline() )
                {
                  if ( (unsigned int)Feature_DisplayMux_PostGA_BugBundle_3__private_IsEnabledDeviceUsageNoInline() )
                  {
                    if ( (_BYTE)word_140162E5D
                      && *((_BYTE *)v25 + 3071)
                      && ((v74 = *((_DWORD *)v25 + 776), (v74 & 0x20) == 0) || (v74 & 0x80u) == 0) )
                    {
                      v75 = ADAPTER_RENDER::CopyDListFileName(
                              *((ADAPTER_RENDER **)v25 + 407),
                              (unsigned __int16 *)v9,
                              v93);
                      Registry = v75;
                      if ( v75 < 0 )
                      {
                        WdLogSingleEntry3(4, v9, v25, v75);
                        WdLogGlobalForLineNumber = 3841;
                      }
                    }
                    else
                    {
                      Registry = -1073741637;
                      WdLogSingleEntry3(4, v9, v25, -1073741637);
                      WdLogGlobalForLineNumber = 3851;
                    }
                  }
                }
                else if ( (_BYTE)word_140162E5D && *((_BYTE *)v25 + 3071) && (*((_DWORD *)v25 + 776) & 0x20) == 0 )
                {
                  v92 = ADAPTER_RENDER::CopyDListFileName(*((ADAPTER_RENDER **)v25 + 407), (unsigned __int16 *)v9, v91);
                  Registry = v92;
                  if ( v92 < 0 )
                  {
                    WdLogSingleEntry3(4, v9, v25, v92);
                    WdLogGlobalForLineNumber = 3810;
                  }
                }
                else
                {
                  Registry = -1073741637;
                  WdLogSingleEntry3(4, v9, v25, -1073741637);
                  WdLogGlobalForLineNumber = 3820;
                }
              }
              else
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 3791;
              }
              goto LABEL_107;
            }
            goto LABEL_565;
          }
          if ( (_DWORD)Size != 4 )
          {
            Registry = -1073741811;
            WdLogSingleEntry2(3, (unsigned int)Size);
            WdLogGlobalForLineNumber = 4465;
            goto LABEL_107;
          }
          v94 = ADAPTER_RENDER::IsMultiPlaneOverlaySupported(*((ADAPTER_RENDER **)v25 + 407)) != 0;
        }
        else if ( SHIDWORD(Srca[0]) > 32 )
        {
          if ( HIDWORD(Srca[0]) != 33 )
          {
            switch ( HIDWORD(Srca[0]) )
            {
              case '"':
                if ( (_DWORD)Size == 12 )
                {
                  v76 = DXGADAPTER::GetNumDifferentPhysicalAdapters(v25);
                  if ( (*((_DWORD *)v25 + 649) & 0x40) != 0 )
                  {
                    if ( *v9 < v76 )
                    {
                      ADAPTER_RENDER::QueryGpuMmuCaps(
                        *((ADAPTER_RENDER **)v25 + 407),
                        *v9,
                        (struct _D3DKMT_GPUMMU_CAPS *)(v9 + 1));
                    }
                    else
                    {
                      Registry = -1073741811;
                      WdLogSingleEntry2(3, *v9);
                      WdLogGlobalForLineNumber = 4917;
                    }
                  }
                  else
                  {
                    Registry = -1073741811;
                    WdLogSingleEntry1(3);
                    WdLogGlobalForLineNumber = 4907;
                  }
                }
                else
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 4896;
                }
                goto LABEL_107;
              case '#':
                if ( (_DWORD)Size != 4 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 4936;
                  goto LABEL_107;
                }
                v99 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)v25 + 407) + 16LL) + 3172LL) == 0;
                break;
              case '$':
                if ( (_DWORD)Size != 4 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 4961;
                  goto LABEL_107;
                }
                v94 = *((_DWORD *)DXGGLOBAL::GetGlobal() + 368);
                goto LABEL_385;
              case '%':
                if ( (_DWORD)Size != 4 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 4979;
                  goto LABEL_107;
                }
                v99 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)v25 + 407) + 16LL) + 3173LL) == 0;
                break;
              case '&':
                if ( (_DWORD)Size != 4 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 5004;
                  goto LABEL_107;
                }
                v99 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)v25 + 407) + 16LL) + 3174LL) == 0;
                break;
              case '\'':
                if ( (_DWORD)Size != 4 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 5029;
                  goto LABEL_107;
                }
                v99 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)v25 + 407) + 16LL) + 3175LL) == 0;
                break;
              default:
                if ( (_DWORD)Size != 4 )
                {
                  Registry = -1073741811;
                  WdLogSingleEntry2(3, (unsigned int)Size);
                  WdLogGlobalForLineNumber = 5054;
                  goto LABEL_107;
                }
                v99 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)v25 + 407) + 16LL) + 3176LL) == 0;
                break;
            }
LABEL_434:
            v64 = !v99;
            goto LABEL_249;
          }
          if ( (_DWORD)Size != 4 )
          {
            Registry = -1073741811;
            WdLogSingleEntry2(3, (unsigned int)Size);
            WdLogGlobalForLineNumber = 4859;
            goto LABEL_107;
          }
          *(_OWORD *)&v137.hAdapter = 0;
          v100 = DxgkMiracastQueryMiracastSupportInternal(&v137);
          if ( v100 == -1073741637 )
            goto LABEL_281;
          if ( v100 < 0 )
          {
            Registry = v100;
            WdLogSingleEntry1(3);
            WdLogGlobalForLineNumber = 4873;
            goto LABEL_107;
          }
          v94 = 2 - (LOBYTE(v137.pPrivateDriverData) != 0);
        }
        else
        {
          switch ( HIDWORD(Srca[0]) )
          {
            case 0x20:
              if ( (_DWORD)Size == 4 )
              {
                QueryDriverCapsExt(v24, (struct _D3DKMT_DRIVERCAPS_EXT *)v9);
              }
              else
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 4841;
              }
              goto LABEL_107;
            case 0x17:
              if ( (_DWORD)Size == 16 )
              {
                if ( v9[1] )
                {
                  if ( (*((_DWORD *)DXGPROCESS::GetCurrent() + 102) & 4) == 0 )
                  {
                    Registry = -1073741790;
                    WdLogSingleEntry1(3);
                    WdLogGlobalForLineNumber = 4495;
                    goto LABEL_107;
                  }
                  if ( v9[1] )
                  {
                    *(_DWORD *)(*((_QWORD *)v25 + 407) + 1240LL) = v9[3];
                    goto LABEL_107;
                  }
                }
                v9[2] = ADAPTER_RENDER::IsMultiPlaneOverlaySupported(*((ADAPTER_RENDER **)v25 + 407));
                v9[3] = *(_DWORD *)(*((_QWORD *)v25 + 407) + 1240LL);
                goto LABEL_107;
              }
              Registry = -1073741811;
              WdLogSingleEntry2(3, (unsigned int)Size);
              WdLogGlobalForLineNumber = 4490;
LABEL_107:
              v37 = v116;
LABEL_108:
              DXGPAIREDADAPTERSTOPRESETLOCKSHARED::~DXGPAIREDADAPTERSTOPRESETLOCKSHARED((DXGPAIREDADAPTERSTOPRESETLOCKSHARED *)v141);
LABEL_109:
              if ( Registry >= 0 && (*((_DWORD *)v37 + 102) & 0x200) != 0 )
                Registry = PostProcessUMDFileName(SHIDWORD(Srca[0]), v9, Size);
              goto LABEL_85;
            case 0x18:
              if ( (_DWORD)Size == 4 )
              {
                DXGADAPTER::QueryWDDM2_0Caps(v25, (struct _D3DKMT_WDDM_2_0_CAPS *)v9);
              }
              else
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 4549;
              }
              goto LABEL_107;
            case 0x19:
              if ( (_DWORD)Size != 78 )
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 4639;
                goto LABEL_107;
              }
              NodePerfData = DXGADAPTER::QueryNodeMetadata(v25, *v9, (struct _DXGK_NODEMETADATA *)(v9 + 1));
              goto LABEL_161;
          }
          v38 = (unsigned int)(HIDWORD(Srca[0]) - 26);
          if ( HIDWORD(Srca[0]) == 26 )
          {
            if ( (_DWORD)Size == 520 )
            {
              v97 = *((_QWORD *)v25 + 407);
              *(_WORD *)v9 = 0;
              v98 = RtlStringCbCopyNW(
                      (unsigned __int16 *)v9,
                      v38,
                      *(const unsigned __int16 **)(v97 + 648),
                      *(unsigned __int16 *)(v97 + 640));
              Registry = v98;
              if ( v98 < 0 )
              {
                WdLogSingleEntry3(4, v9, v25, v98);
                WdLogGlobalForLineNumber = 4668;
              }
            }
            else
            {
              Registry = -1073741811;
              WdLogSingleEntry2(3, (unsigned int)Size);
              WdLogGlobalForLineNumber = 4656;
            }
            goto LABEL_107;
          }
          if ( HIDWORD(Srca[0]) == 27 )
          {
            if ( (_DWORD)Size != 4 )
            {
              Registry = -1073741811;
              WdLogSingleEntry2(3, (unsigned int)Size);
              WdLogGlobalForLineNumber = 4709;
              goto LABEL_107;
            }
            v63 = *((_DWORD *)v21 + 111) >> 9;
            goto LABEL_248;
          }
          if ( HIDWORD(Srca[0]) != 28 )
          {
            v39 = (unsigned int)(HIDWORD(Srca[0]) - 29);
            if ( HIDWORD(Srca[0]) == 29 )
            {
              if ( (_DWORD)Size == 520 )
              {
                v95 = *((_QWORD *)v25 + 407);
                *(_WORD *)v9 = 0;
                v96 = RtlStringCbCopyNW(
                        (unsigned __int16 *)v9,
                        v39,
                        *(const unsigned __int16 **)(v95 + 664),
                        *(unsigned __int16 *)(v95 + 656));
                Registry = v96;
                if ( v96 < 0 )
                {
                  WdLogSingleEntry3(4, v9, v25, v96);
                  WdLogGlobalForLineNumber = 4694;
                }
              }
              else
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 4682;
              }
              goto LABEL_107;
            }
            if ( HIDWORD(Srca[0]) == 30 )
            {
              if ( (_DWORD)Size != 4 )
              {
                Registry = -1073741811;
                WdLogSingleEntry2(3, (unsigned int)Size);
                WdLogGlobalForLineNumber = 4753;
                goto LABEL_107;
              }
              *v9 = DXGADAPTER::GetNumDifferentPhysicalAdapters(v25);
              v37 = v116;
              if ( (*((_DWORD *)v116 + 102) & 0x100) != 0
                && (**((_DWORD **)v25 + 392) & 0x1000000) == 0
                && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v25 + 27) + 64LL) + 40LL) + 28LL) >= 0xF003u )
              {
                *v9 = 1;
              }
              goto LABEL_189;
            }
            if ( (_DWORD)Size != 28 )
            {
              Registry = -1073741811;
              WdLogSingleEntry2(3, (unsigned int)Size);
              WdLogGlobalForLineNumber = 4783;
              goto LABEL_107;
            }
            v40 = DXGADAPTER::GetNumDifferentPhysicalAdapters(v25);
            if ( (unsigned int)v41 >= v40 )
            {
              Registry = -1073741811;
              WdLogSingleEntry2(3, v41);
              WdLogGlobalForLineNumber = 4807;
              goto LABEL_107;
            }
            _mm_lfence();
            v42 = *(_DWORD **)(*(_QWORD *)(352 * v41 + *((_QWORD *)v25 + 390) + 8) + 64LL);
            v9[1] = v42[281];
            v9[2] = v42[282];
            v9[3] = v42[283];
            v9[4] = v42[284];
            v9[5] = v42[285];
            v9[6] = v42[280];
            goto LABEL_127;
          }
          if ( (_DWORD)Size != 4 )
          {
            Registry = -1073741811;
            WdLogSingleEntry2(3, (unsigned int)Size);
            WdLogGlobalForLineNumber = 4727;
            goto LABEL_107;
          }
          v94 = (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v25 + 407) + 16LL) + 2588LL) & 0x10) != 0;
        }
LABEL_385:
        *v9 = v94;
        goto LABEL_107;
      }
      Registry = -1073741130;
      DXGPAIREDADAPTERSTOPRESETLOCKSHARED::~DXGPAIREDADAPTERSTOPRESETLOCKSHARED((DXGPAIREDADAPTERSTOPRESETLOCKSHARED *)v141);
    }
LABEL_85:
    COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v142);
LABEL_86:
    if ( Registry >= 0 )
    {
      if ( v120 )
        RtlCopyToUser(Srca[1], v9, (unsigned int)Size);
      else
        memmove(Srca[1], v9, (unsigned int)Size);
    }
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v9);
    v34 = Registry;
    if ( v136[0] )
      DXGADAPTER::ReleaseReference(v136[0], v33);
    goto LABEL_89;
  }
  Value = v121.Value;
  WdLogSingleEntry2(2, v21);
  WdLogGlobalForLineNumber = 3521;
  DxgkLogInternalTriageEvent(
    0,
    0x40000,
    -1,
    (unsigned int)L"Failed to get pairing adapters from adapter 0x%I64x VidPn source 0x%I64x!",
    (__int64)v21,
    Value,
    0,
    0,
    0);
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v9);
  Registry = PairingAdapters;
  DXGADAPTERBYHANDLE::~DXGADAPTERBYHANDLE((DXGADAPTERBYHANDLE *)v136);
  DxgkQueryAdapterInfoImpl_::_2_::LKDONFAILURE::_LKDONFAILURE(&v127);
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v123);
  if ( v125 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v69, EventProfilerExit, v70, v123);
  return (unsigned int)PairingAdapters;
}

```

## disassembly

```asm
0x14035feb0  mov     r11, rsp
0x14035feb3  mov     [r11+10h], rbx
0x14035feb7  mov     [r11+20h], rsi
0x14035febb  push    rdi
0x14035febc  push    r12
0x14035febe  push    r13
0x14035fec0  push    r14
0x14035fec2  push    r15
0x14035fec4  sub     rsp, 230h
0x14035fecb  mov     rax, cs:__security_cookie
0x14035fed2  xor     rax, rsp
0x14035fed5  mov     [rsp+258h+var_38], rax
0x14035fedd  mov     r14, r8
0x14035fee0  mov     sil, dl
0x14035fee3  mov     [rsp+258h+var_1DF], dl
0x14035fee7  mov     rbx, rcx
0x14035feea  or      r15d, 0FFFFFFFFh
0x14035feee  mov     [r11-1D0h], r15d
0x14035fef5  xor     edi, edi
0x14035fef7  mov     [r11-1C8h], rdi
0x14035fefe  mov     rax, cs:qword_1401604F0
0x14035ff05  lea     r12d, [r15+2]
0x14035ff09  test    al, 2
0x14035ff0b  jnz     short loc_14035FF17
0x14035ff0d  mov     [rsp+258h+var_1C0], dil
0x14035ff15  jmp     short loc_14035FF37
0x14035ff17  mov     [rsp+258h+var_1C0], r12b
0x14035ff1f  mov     [rsp+258h+var_1D0], 7DFh
0x14035ff2a  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, r12b
0x14035ff31  jnz     loc_14036168F
0x14035ff37  mov     edx, 7DFh
0x14035ff3c  lea     rcx, [rsp+258h+var_1D0]
0x14035ff44  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x14035ff49  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14035ff4e  mov     r13, rax
0x14035ff51  mov     [rsp+258h+var_200], rax
0x14035ff56  mov     [rsp+258h+var_208], edi
0x14035ff5a  xorps   xmm0, xmm0
0x14035ff5d  movdqu  [rsp+258h+var_1A8], xmm0
0x14035ff66  mov     [rsp+258h+var_190], r15d
0x14035ff6e  mov     [rsp+258h+var_18C], dil
0x14035ff76  lea     rax, [rsp+258h+var_208]
0x14035ff7b  mov     [rsp+258h+var_1B0], rax
0x14035ff83  mov     [rsp+258h+var_18B], sil
0x14035ff8b  mov     [rsp+258h+var_198], r13
0x14035ff93  test    r13, r13
0x14035ff96  jz      loc_1403616A6
0x14035ff9c  test    r14, r14
0x14035ff9f  jnz     loc_140361732
0x14035ffa5  xor     eax, eax
0x14035ffa7  movups  xmmword ptr [rsp+258h+Src], xmm0
0x14035ffac  mov     [rsp+258h+Size], rax
0x14035ffb1  mov     [rsp+258h+var_178], rdi
0x14035ffb9  test    sil, sil
0x14035ffbc  jnz     loc_1403600FA
0x14035ffc2  movups  xmm0, xmmword ptr [rbx]
0x14035ffc5  movups  xmmword ptr [rsp+258h+Src], xmm0
0x14035ffca  movsd   xmm1, qword ptr [rbx+10h]
0x14035ffcf  movsd   [rsp+258h+Size], xmm1
0x14035ffd5  mov     rax, [rsp+258h+Src]
0x14035ffda  shr     rax, 20h
0x14035ffde  mov     [rsp+258h+var_190], eax
0x14035ffe5  cmp     [rsp+258h+Src+8], rdi
0x14035ffea  jz      loc_140360112
0x14035fff0  mov     eax, dword ptr [rsp+258h+Size]
0x14035fff4  test    eax, eax
0x14035fff6  jz      loc_140360173
0x14035fffc  lea     ecx, [rax+7]
0x14035ffff  and     ecx, 0FFFFFFF8h
0x140360002  mov     [rsp+258h+var_1B8], ecx
0x140360009  mov     [rsp+258h+var_148], ecx
0x140360010  cmp     ecx, eax
0x140360012  jb      loc_1403601D4
0x140360018  mov     edx, 4B677844h
0x14036001d  mov     r8d, 40h ; '@'
0x140360023  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140360028  mov     rsi, rax
0x14036002b  mov     [rsp+258h+var_140], rax
0x140360033  mov     [rsp+258h+var_178], rax
0x14036003b  test    rax, rax
0x14036003e  jz      loc_140360235
0x140360044  mov     ecx, dword ptr [rsp+258h+Src+4]
0x140360048  cmp     ecx, 2Fh ; '/'
0x14036004b  jle     short loc_140360088
0x14036004d  cmp     ecx, 3Fh ; '?'
0x140360050  jle     loc_14036032B
0x140360056  sub     ecx, 40h ; '@'
0x140360059  jz      loc_140360349
0x14036005f  mov     r15d, 3
0x140360065  sub     ecx, r15d
0x140360068  jz      short loc_1403600D2
0x14036006a  sub     ecx, 4
0x14036006d  jz      short loc_1403600D2
0x14036006f  cmp     ecx, 1
0x140360072  jz      short loc_1403600D2
0x140360074  mov     r8d, dword ptr [rsp+258h+Size]; Size
0x140360079  xor     edx, edx; Val
0x14036007b  mov     rcx, rsi; void *
0x14036007e  call    memset
0x140360083  jmp     loc_140360354
0x140360088  jz      loc_140360349
0x14036008e  cmp     ecx, 19h
0x140360091  jg      loc_1403602F3
0x140360097  jz      loc_140360349
0x14036009d  sub     ecx, 1
0x1403600a0  jz      loc_140360349
0x1403600a6  sub     ecx, 6
0x1403600a9  jz      loc_140360349
0x1403600af  sub     ecx, 2
0x1403600b2  jz      loc_140360349
0x1403600b8  sub     ecx, 7
0x1403600bb  jz      loc_140360349
0x1403600c1  cmp     ecx, 7
0x1403600c4  jz      loc_140360349
0x1403600ca  mov     r15d, 3
0x1403600d0  jmp     short loc_140360074
0x1403600d2  mov     r8d, dword ptr [rsp+258h+Size]; Size
0x1403600d7  mov     rdx, [rsp+258h+Src+8]; Src
0x1403600dc  mov     rcx, rsi; void *
0x1403600df  cmp     [rsp+258h+var_1DF], dil
0x1403600e4  jz      short loc_1403600F0
0x1403600e6  call    RtlCopyFromUser
0x1403600eb  jmp     loc_140360354
0x1403600f0  call    memmove
0x1403600f5  jmp     loc_140360354
0x1403600fa  mov     r8d, 18h; Size
0x140360100  mov     rdx, rbx; Src
0x140360103  lea     rcx, [rsp+258h+Src]; void *
0x140360108  call    RtlCopyFromUser
0x14036010d  jmp     loc_14035FFD5
0x140360112  mov     rbx, 0FFFFFFFFC000000Dh
0x140360119  mov     rdx, rbx
0x14036011c  mov     ecx, 3
0x140360121  call    cs:__imp_WdLogSingleEntry1
0x140360128  nop     dword ptr [rax+rax+00h]
0x14036012d  mov     cs:WdLogGlobalForLineNumber, 0D03h
0x140360137  mov     [rsp+258h+var_208], ebx
0x14036013b  lea     rcx, [rsp+258h+var_1B0]
0x140360143  call    _DxgkQueryAdapterInfoImpl____2___LKDONFAILURE___LKDONFAILURE
0x140360148  lea     rcx, [rsp+258h+var_1D0]; this
0x140360150  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x140360155  cmp     [rsp+258h+var_1C0], dil
0x14036015d  jz      short loc_14036016C
0x14036015f  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, r12b
0x140360166  jnz     loc_140360292
0x14036016c  mov     eax, ebx
0x14036016e  jmp     loc_140363224
0x140360173  mov     rbx, 0FFFFFFFFC000000Dh
0x14036017a  mov     rdx, rbx
0x14036017d  mov     ecx, 3
0x140360182  call    cs:__imp_WdLogSingleEntry1
0x140360189  nop     dword ptr [rax+rax+00h]
0x14036018e  mov     cs:WdLogGlobalForLineNumber, 0D0Ch
0x140360198  mov     [rsp+258h+var_208], ebx
0x14036019c  lea     rcx, [rsp+258h+var_1B0]
0x1403601a4  call    _DxgkQueryAdapterInfoImpl____2___LKDONFAILURE___LKDONFAILURE
0x1403601a9  lea     rcx, [rsp+258h+var_1D0]; this
0x1403601b1  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1403601b6  cmp     [rsp+258h+var_1C0], dil
0x1403601be  jz      short loc_1403601CD
0x1403601c0  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, r12b
0x1403601c7  jnz     loc_1403602AB
0x1403601cd  mov     eax, ebx
0x1403601cf  jmp     loc_140363224
0x1403601d4  mov     rbx, 0FFFFFFFFC000000Dh
0x1403601db  mov     rdx, rbx
0x1403601de  mov     ecx, 3
0x1403601e3  call    cs:__imp_WdLogSingleEntry1
0x1403601ea  nop     dword ptr [rax+rax+00h]
0x1403601ef  mov     cs:WdLogGlobalForLineNumber, 0D1Ah
0x1403601f9  mov     [rsp+258h+var_208], ebx
0x1403601fd  lea     rcx, [rsp+258h+var_1B0]
0x140360205  call    _DxgkQueryAdapterInfoImpl____2___LKDONFAILURE___LKDONFAILURE
0x14036020a  lea     rcx, [rsp+258h+var_1D0]; this
0x140360212  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x140360217  cmp     [rsp+258h+var_1C0], dil
0x14036021f  jz      short loc_14036022E
0x140360221  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, r12b
0x140360228  jnz     loc_1403602C4
0x14036022e  mov     eax, ebx
0x140360230  jmp     loc_140363224
0x140360235  mov     rbx, 0FFFFFFFFC0000017h
0x14036023c  mov     rdx, rbx
0x14036023f  mov     ecx, 3
0x140360244  call    cs:__imp_WdLogSingleEntry1
0x14036024b  nop     dword ptr [rax+rax+00h]
0x140360250  mov     cs:WdLogGlobalForLineNumber, 0D24h
0x14036025a  mov     [rsp+258h+var_208], ebx
0x14036025e  lea     rcx, [rsp+258h+var_1B0]
0x140360266  call    _DxgkQueryAdapterInfoImpl____2___LKDONFAILURE___LKDONFAILURE
0x14036026b  lea     rcx, [rsp+258h+var_1D0]; this
0x140360273  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x140360278  cmp     [rsp+258h+var_1C0], dil
0x140360280  jz      short loc_14036028B
0x140360282  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, r12b
0x140360289  jnz     short loc_1403602DD
0x14036028b  mov     eax, ebx
0x14036028d  jmp     loc_140363224
0x140360292  mov     r9d, [rsp+258h+var_1D0]
0x14036029a  lea     rdx, EventProfilerExit
0x1403602a1  call    McTemplateK0q_EtwWriteTransfer
0x1403602a6  jmp     loc_14036016C
0x1403602ab  mov     r9d, [rsp+258h+var_1D0]
0x1403602b3  lea     rdx, EventProfilerExit
0x1403602ba  call    McTemplateK0q_EtwWriteTransfer
0x1403602bf  jmp     loc_1403601CD
0x1403602c4  mov     r9d, [rsp+258h+var_1D0]
0x1403602cc  lea     rdx, EventProfilerExit
0x1403602d3  call    McTemplateK0q_EtwWriteTransfer
0x1403602d8  jmp     loc_14036022E
0x1403602dd  mov     r9d, [rsp+258h+var_1D0]
0x1403602e5  lea     rdx, EventProfilerExit
0x1403602ec  call    McTemplateK0q_EtwWriteTransfer
0x1403602f1  jmp     short loc_14036028B
0x1403602f3  sub     ecx, 1Fh
0x1403602f6  mov     r15d, 3
0x1403602fc  jz      loc_1403600D2
0x140360302  sub     ecx, r15d
0x140360305  jz      loc_1403600D2
0x14036030b  sub     ecx, 7
0x14036030e  jz      loc_1403600D2
0x140360314  sub     ecx, 1
0x140360317  jz      loc_1403600D2
0x14036031d  cmp     ecx, 4
0x140360320  jnz     loc_140360074
0x140360326  jmp     loc_1403600D2
0x14036032b  jz      short loc_140360349
0x14036032d  sub     ecx, 30h ; '0'
0x140360330  jz      short loc_140360349
0x140360332  sub     ecx, 2
0x140360335  jz      short loc_140360349
0x140360337  sub     ecx, 1
0x14036033a  jz      short loc_140360349
0x14036033c  sub     ecx, 0Ah
0x14036033f  jz      short loc_140360349
0x140360341  cmp     ecx, 1
0x140360344  jmp     loc_1403600C4
0x140360349  mov     r15d, 3
0x14036034f  jmp     loc_1403600D2
0x140360354  jmp     loc_1403603DB
0x140360359  mov     rdx, 0FFFFFFFFC000000Dh
0x140360360  mov     ecx, 3
0x140360365  call    cs:__imp_WdLogSingleEntry1
0x14036036c  nop     dword ptr [rax+rax+00h]
0x140360371  mov     cs:WdLogGlobalForLineNumber, 0D5Ah
0x14036037b  mov     rcx, [rsp+258h+var_178]; void *
0x140360383  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x140360388  mov     [rsp+258h+var_208], 0C000000Dh
0x140360390  lea     rcx, [rsp+258h+var_1B0]
0x140360398  call    _DxgkQueryAdapterInfoImpl____2___LKDONFAILURE___LKDONFAILURE
0x14036039d  lea     rcx, [rsp+258h+var_1D0]; this
0x1403603a5  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1403603aa  cmp     [rsp+258h+var_1C0], 0
0x1403603b2  jz      short loc_1403603D1
0x1403603b4  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1403603bb  jz      short loc_1403603D1
0x1403603bd  mov     r9d, [rsp+258h+var_1D0]
0x1403603c5  lea     rdx, EventProfilerExit
0x1403603cc  call    McTemplateK0q_EtwWriteTransfer
0x1403603d1  mov     eax, 0C000000Dh
0x1403603d6  jmp     loc_140363224
0x1403603db  mov     [rsp+258h+var_1D8], r14
0x1403603e3  lea     r9, [rsp+258h+var_1D8]
0x1403603eb  test    r14, r14
0x1403603ee  cmovnz  r9, rdi; struct DXGADAPTER **
0x1403603f2  mov     byte ptr [rsp+258h+var_238], r12b; bool
0x1403603f7  mov     r8, r13; struct DXGPROCESS *
0x1403603fa  mov     edx, dword ptr [rsp+258h+Src]; unsigned int
0x1403603fe  lea     rcx, [rsp+258h+var_170]; this
0x140360406  call    ??0DXGADAPTERBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGADAPTER@@_N@Z; DXGADAPTERBYHANDLE::DXGADAPTERBYHANDLE(uint,DXGPROCESS *,DXGADAPTER * *,bool)
0x14036040b  mov     r13, [rsp+258h+var_1D8]
0x140360413  test    r13, r13
0x140360416  jz      loc_14036173D
0x14036041c  mov     qword ptr [rsp+258h+var_1A8], r13
0x140360424  cmp     dword ptr [rsp+258h+Src+4], 9
0x140360429  jz      loc_140361766
0x14036042f  mov     eax, edi
0x140360431  mov     dword ptr [rsp+258h+var_1DC], eax
0x140360435  cmp     dword ptr [rsp+258h+Src+4], 43h ; 'C'
0x14036043a  jz      loc_14036179A
0x140360440  mov     [rsp+258h+var_1D8], rdi
0x140360448  mov     [rsp+258h+var_188], rdi
0x140360450  mov     byte ptr [rsp+258h+var_228], dil; unsigned __int8
0x140360455  lea     rcx, [rsp+258h+var_138]
0x14036045d  mov     [rsp+258h+var_230], rcx; unsigned __int64 *
0x140360462  lea     rcx, [rsp+258h+var_188]
0x14036046a  mov     [rsp+258h+var_238], rcx; struct DXGADAPTER **
0x14036046f  lea     r9, [rsp+258h+var_180]; unsigned __int64 *
0x140360477  lea     r8, [rsp+258h+var_1D8]; struct DXGADAPTER **
0x14036047f  mov     edx, eax; unsigned int
0x140360481  mov     rcx, r13; this
0x140360484  call    ?DxgkpGetPairingAdapters@@YAJPEAVDXGADAPTER@@IPEAPEAV1@PEA_K12E@Z; DxgkpGetPairingAdapters(DXGADAPTER *,uint,DXGADAPTER * *,unsigned __int64 *,DXGADAPTER * *,unsigned __int64 *,uchar)
0x140360489  mov     r14d, eax
0x14036048c  test    eax, eax
0x14036048e  js      loc_140360D69
0x140360494  mov     rbx, [rsp+258h+var_188]
0x14036049c  test    r14d, r14d
0x14036049f  js      loc_14036138B
0x1403604a5  mov     r14, [rsp+258h+var_1D8]
0x1403604ad  cmp     r14, r13
  ... truncated ...
```
