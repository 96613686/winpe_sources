# DXGADAPTER::Initialize(_DEVICE_OBJECT *,_DXGK_ADAPTER_CAPS *)

- ea: `0x1401c6fe0`
- end: `0x1401c98f0`
- name: `?Initialize@DXGADAPTER@@QEAAJPEAU_DEVICE_OBJECT@@PEAU_DXGK_ADAPTER_CAPS@@@Z`
- size: `10512`
- prototype: `__int64 __fastcall(DXGADAPTER *__hidden this, PDEVICE_OBJECT DeviceObject, struct _DXGK_ADAPTER_CAPS *)`
- caller_count: `1`
- callee_count: `51`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1401921f4`

## callees

- `0x1400091f0`
- `0x140012540`
- `0x1400146ac`
- `0x140015290`
- `0x14001b9c0`
- `0x14002e2e0`
- `0x14002ff90`
- `0x14003bd18`
- `0x14003eba4`
- `0x14003f9fc`
- `0x14003fa30`
- `0x1400480b4`
- `0x14004bf5c`
- `0x140050484`
- `0x140067f18`
- `0x140068848`
- `0x1400688a0`
- `0x140076844`
- `0x140080ef4`
- `0x140081ff0`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x14019608c`
- `0x140196118`
- `0x1401c6fe0`
- `0x1401cf650`
- `0x1401d3a20`
- `0x1401e8324`
- `0x1401e877c`
- `0x1401ea010`
- `0x1401ea190`
- `0x1401ea324`
- `0x1401ea758`
- `0x1401eacdc`
- `0x1401eb410`
- `0x1401ed908`
- `0x1401eebf0`
- `0x1401ef014`
- `0x1401f0a74`
- `0x1401f1628`
- `0x1401fa368`
- `0x14023e9d0`
- `0x14023ec4c`
- `0x14023ee04`
- `0x140242ab4`
- `0x140266bf0`
- `0x1402a1608`
- `0x14035fa08`
- `0x140364040`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401c975b`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401c975b`
- `ntoskrnl!ExInitializeResourceLite` at `0x1401c70e8`
- `ntoskrnl!ExInitializeResourceLite` at `0x1401c7211`
- `ntoskrnl!ExInitializeResourceLite` at `0x1401c70e8`
- `ntoskrnl!ExInitializeResourceLite` at `0x1401c7211`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1401c713c`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1401c713c`
- `ntoskrnl!ObfDereferenceObject` at `0x1401c7152`
- `ntoskrnl!ObfDereferenceObject` at `0x1401c7152`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x1401c7165`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x1401c7165`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401c7018`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401c7018`
- `watchdog!WdLogSingleEntry2` at `0x1401c70c5`
- `watchdog!WdLogSingleEntry2` at `0x1401c7106`
- `watchdog!WdLogSingleEntry2` at `0x1401c71f3`
- `watchdog!WdLogSingleEntry2` at `0x1401c722f`
- `watchdog!WdLogSingleEntry2` at `0x1401c730d`
- `watchdog!WdLogSingleEntry2` at `0x1401c73d6`
- `watchdog!WdLogSingleEntry2` at `0x1401c8c19`
- `watchdog!WdLogSingleEntry2` at `0x1401c8c6b`
- `watchdog!WdLogSingleEntry2` at `0x1401c903f`
- `watchdog!WdLogSingleEntry2` at `0x1401c90fa`
- `watchdog!WdLogSingleEntry2` at `0x1401c9201`
- `watchdog!WdLogSingleEntry2` at `0x1401c9257`
- `watchdog!WdLogSingleEntry2` at `0x1401c94df`
- `watchdog!WdLogSingleEntry2` at `0x1401c957b`
- `watchdog!WdLogSingleEntry2` at `0x1401c70c5`
- `watchdog!WdLogSingleEntry2` at `0x1401c7106`
- `watchdog!WdLogSingleEntry2` at `0x1401c71f3`
- `watchdog!WdLogSingleEntry2` at `0x1401c722f`
- `watchdog!WdLogSingleEntry2` at `0x1401c730d`
- `watchdog!WdLogSingleEntry2` at `0x1401c73d6`
- `watchdog!WdLogSingleEntry2` at `0x1401c8c19`
- `watchdog!WdLogSingleEntry2` at `0x1401c8c6b`
- `watchdog!WdLogSingleEntry2` at `0x1401c903f`
- `watchdog!WdLogSingleEntry2` at `0x1401c90fa`
- `watchdog!WdLogSingleEntry2` at `0x1401c9201`
- `watchdog!WdLogSingleEntry2` at `0x1401c9257`
- `watchdog!WdLogSingleEntry2` at `0x1401c94df`
- `watchdog!WdLogSingleEntry2` at `0x1401c957b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401c755f`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401c8e58`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401c755f`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401c8e58`
- `watchdog!WdLogSingleEntry3` at `0x1401c7da2`
- `watchdog!WdLogSingleEntry3` at `0x1401c7f7e`
- `watchdog!WdLogSingleEntry3` at `0x1401c7da2`
- `watchdog!WdLogSingleEntry3` at `0x1401c7f7e`
- `watchdog!WdLogSingleEntry0` at `0x1401c7033`
- `watchdog!WdLogSingleEntry0` at `0x1401c717c`
- `watchdog!WdLogSingleEntry0` at `0x1401c746c`
- `watchdog!WdLogSingleEntry0` at `0x1401c74c0`
- `watchdog!WdLogSingleEntry0` at `0x1401c760d`
- `watchdog!WdLogSingleEntry0` at `0x1401c77ed`
- `watchdog!WdLogSingleEntry0` at `0x1401c7872`
- `watchdog!WdLogSingleEntry0` at `0x1401c79cd`
- `watchdog!WdLogSingleEntry0` at `0x1401c81ae`
- `watchdog!WdLogSingleEntry0` at `0x1401c820a`
- `watchdog!WdLogSingleEntry0` at `0x1401c8303`
- `watchdog!WdLogSingleEntry0` at `0x1401c8469`
- `watchdog!WdLogSingleEntry0` at `0x1401c84b1`
- `watchdog!WdLogSingleEntry0` at `0x1401c84fe`
- `watchdog!WdLogSingleEntry0` at `0x1401c8539`
- `watchdog!WdLogSingleEntry0` at `0x1401c8839`
- `watchdog!WdLogSingleEntry0` at `0x1401c8881`
- `watchdog!WdLogSingleEntry0` at `0x1401c88cf`
- `watchdog!WdLogSingleEntry0` at `0x1401c8949`
- `watchdog!WdLogSingleEntry0` at `0x1401c89a7`
- `watchdog!WdLogSingleEntry0` at `0x1401c89f0`
- `watchdog!WdLogSingleEntry0` at `0x1401c8a3d`
- `watchdog!WdLogSingleEntry0` at `0x1401c8a81`
- `watchdog!WdLogSingleEntry0` at `0x1401c8ad9`
- `watchdog!WdLogSingleEntry0` at `0x1401c8af7`
- `watchdog!WdLogSingleEntry0` at `0x1401c8f31`
- `watchdog!WdLogSingleEntry0` at `0x1401c8fa8`
- `watchdog!WdLogSingleEntry0` at `0x1401c90aa`
- `watchdog!WdLogSingleEntry0` at `0x1401c9145`
- `watchdog!WdLogSingleEntry0` at `0x1401c91b1`
- `watchdog!WdLogSingleEntry0` at `0x1401c93bd`
- `watchdog!WdLogSingleEntry0` at `0x1401c9404`
- `watchdog!WdLogSingleEntry0` at `0x1401c964e`
- `watchdog!WdLogSingleEntry0` at `0x1401c967d`
- `watchdog!WdLogSingleEntry0` at `0x1401c96cc`
- `watchdog!WdLogSingleEntry0` at `0x1401c970c`
- `watchdog!WdLogSingleEntry0` at `0x1401c976e`
- `watchdog!WdLogSingleEntry0` at `0x1401c7033`
- `watchdog!WdLogSingleEntry0` at `0x1401c717c`
- `watchdog!WdLogSingleEntry0` at `0x1401c746c`
- `watchdog!WdLogSingleEntry0` at `0x1401c74c0`
- `watchdog!WdLogSingleEntry0` at `0x1401c760d`
- `watchdog!WdLogSingleEntry0` at `0x1401c77ed`
- `watchdog!WdLogSingleEntry0` at `0x1401c7872`
- `watchdog!WdLogSingleEntry0` at `0x1401c79cd`
- `watchdog!WdLogSingleEntry0` at `0x1401c81ae`
- `watchdog!WdLogSingleEntry0` at `0x1401c820a`
- `watchdog!WdLogSingleEntry0` at `0x1401c8303`
- `watchdog!WdLogSingleEntry0` at `0x1401c8469`
- `watchdog!WdLogSingleEntry0` at `0x1401c84b1`
- `watchdog!WdLogSingleEntry0` at `0x1401c84fe`
- `watchdog!WdLogSingleEntry0` at `0x1401c8539`
- `watchdog!WdLogSingleEntry0` at `0x1401c8839`
- `watchdog!WdLogSingleEntry0` at `0x1401c8881`
- `watchdog!WdLogSingleEntry0` at `0x1401c88cf`
- `watchdog!WdLogSingleEntry0` at `0x1401c8949`
- `watchdog!WdLogSingleEntry0` at `0x1401c89a7`
- `watchdog!WdLogSingleEntry0` at `0x1401c89f0`
- `watchdog!WdLogSingleEntry0` at `0x1401c8a3d`
- `watchdog!WdLogSingleEntry0` at `0x1401c8a81`
- `watchdog!WdLogSingleEntry0` at `0x1401c8ad9`
- `watchdog!WdLogSingleEntry0` at `0x1401c8af7`
- `watchdog!WdLogSingleEntry0` at `0x1401c8f31`
- `watchdog!WdLogSingleEntry0` at `0x1401c8fa8`
- `watchdog!WdLogSingleEntry0` at `0x1401c90aa`
- `watchdog!WdLogSingleEntry0` at `0x1401c9145`
- `watchdog!WdLogSingleEntry0` at `0x1401c91b1`
- `watchdog!WdLogSingleEntry0` at `0x1401c93bd`
- `watchdog!WdLogSingleEntry0` at `0x1401c9404`
- `watchdog!WdLogSingleEntry0` at `0x1401c964e`
- `watchdog!WdLogSingleEntry0` at `0x1401c967d`
- `watchdog!WdLogSingleEntry0` at `0x1401c96cc`
- `watchdog!WdLogSingleEntry0` at `0x1401c970c`
- `watchdog!WdLogSingleEntry0` at `0x1401c976e`
- `watchdog!WdLogSingleEntry1` at `0x1401c7289`
- `watchdog!WdLogSingleEntry1` at `0x1401c76b0`
- `watchdog!WdLogSingleEntry1` at `0x1401c770f`
- `watchdog!WdLogSingleEntry1` at `0x1401c7d59`
- `watchdog!WdLogSingleEntry1` at `0x1401c7df1`
- `watchdog!WdLogSingleEntry1` at `0x1401c7e34`
- `watchdog!WdLogSingleEntry1` at `0x1401c7e79`
- `watchdog!WdLogSingleEntry1` at `0x1401c7fdd`
- `watchdog!WdLogSingleEntry1` at `0x1401c801d`
- `watchdog!WdLogSingleEntry1` at `0x1401c805f`
- `watchdog!WdLogSingleEntry1` at `0x1401c83f0`
- `watchdog!WdLogSingleEntry1` at `0x1401c86b8`
- `watchdog!WdLogSingleEntry1` at `0x1401c8733`
- `watchdog!WdLogSingleEntry1` at `0x1401c8783`
- `watchdog!WdLogSingleEntry1` at `0x1401c87d6`
- `watchdog!WdLogSingleEntry1` at `0x1401c8cfd`
- `watchdog!WdLogSingleEntry1` at `0x1401c8ff7`
- `watchdog!WdLogSingleEntry1` at `0x1401c92b4`
- `watchdog!WdLogSingleEntry1` at `0x1401c7289`
- `watchdog!WdLogSingleEntry1` at `0x1401c76b0`
- `watchdog!WdLogSingleEntry1` at `0x1401c770f`
- `watchdog!WdLogSingleEntry1` at `0x1401c7d59`
- `watchdog!WdLogSingleEntry1` at `0x1401c7df1`
- `watchdog!WdLogSingleEntry1` at `0x1401c7e34`
- `watchdog!WdLogSingleEntry1` at `0x1401c7e79`
- `watchdog!WdLogSingleEntry1` at `0x1401c7fdd`
- `watchdog!WdLogSingleEntry1` at `0x1401c801d`
- `watchdog!WdLogSingleEntry1` at `0x1401c805f`
- `watchdog!WdLogSingleEntry1` at `0x1401c83f0`
- `watchdog!WdLogSingleEntry1` at `0x1401c86b8`
- `watchdog!WdLogSingleEntry1` at `0x1401c8733`
- `watchdog!WdLogSingleEntry1` at `0x1401c8783`
- `watchdog!WdLogSingleEntry1` at `0x1401c87d6`
- `watchdog!WdLogSingleEntry1` at `0x1401c8cfd`
- `watchdog!WdLogSingleEntry1` at `0x1401c8ff7`
- `watchdog!WdLogSingleEntry1` at `0x1401c92b4`

## string_xrefs

- `0x1401c7880`: `MiscCaps.ComputeOnly is not set, but the device belongs to the ComputeAccelerator class`
- `0x1401c77fb`: `UMD name is missing and device is not compute only`
- `0x1401c7db7`: `Adapter 0x%I64x: VirtualCopyEngineSupported but node index is invalid (VirtualCopyIndex:%u, NumExecutionNodes:%u)`
- `0x1401c7d76`: `Adapter 0x%I64x: IoMmuSecureModeRequired must be set for a device exposing a virtual copy engine`
- `0x1401c8892`: `Driver reports SupportKernelModeCommandBuffer cap but does not fill in the pfnRenderKm DDI.`
- `0x1401c88e0`: `Driver reports SupportRuntimePowerManagement cap but does not fill in the pfnSetPowerComponentFState or pfnPowerRuntimeControlRequest DDI.`
- `0x1401c895a`: `Driver reports SupportMultiPlaneOverlay cap but it is not compiled with expected header files.`
- `0x1401c9117`: `Failed to create ADAPTER_RENDER on adapter 0x%I64x (Status = 0x%I64x).`
- `0x1401c9212`: `Failed to create ADAPTER_DISPLAY on adapter 0x%I64x (Status = 0x%I64x).`
- `0x1401c93ce`: `Driver is compiled against DXGKDDI_INTERFACE_VERSION_WDDM2_0_M2_2_1 or greater, but does not fill in the pfnCalibrateGpuClock or pfnSetStablePowerState DDI.`

## pseudocode

```c
__int64 __fastcall DXGADAPTER::Initialize(DXGADAPTER *this, PDEVICE_OBJECT DeviceObject, struct _DXGK_ADAPTER_CAPS *a3)
{
  struct _DXGK_ADAPTER_CAPS *v3; // r12
  struct _ERESOURCE *v6; // rax
  __int64 result; // rax
  NTSTATUS v8; // eax
  NTSTATUS LocallyUniqueId; // ebx
  PDEVICE_OBJECT DeviceAttachmentBaseRef; // rax
  __int64 v11; // rax
  const wchar_t *v12; // r9
  int v13; // edx
  struct _ERESOURCE *v14; // rax
  NTSTATUS v15; // eax
  _BYTE *DeviceExtension; // rax
  int v17; // eax
  __int64 v18; // r15
  int AdapterInfo; // eax
  struct _LUID *v20; // rdx
  int (__fastcall *v21)(_QWORD, __int128 *); // rax
  unsigned __int8 v22; // bl
  DXGSESSIONDATA *SessionDataForSpecifiedSession; // rax
  unsigned int v24; // eax
  __int64 v25; // rax
  const wchar_t *v26; // r9
  unsigned int v27; // eax
  const struct _GUID *v28; // rdx
  unsigned __int16 v29; // r8
  unsigned __int16 v30; // r9
  int v31; // eax
  const wchar_t *v32; // r9
  unsigned __int8 v33; // dl
  __int64 v34; // r14
  __int64 v35; // rax
  unsigned int v36; // r13d
  unsigned __int8 v37; // r8
  __int64 v38; // rax
  const wchar_t *v39; // r9
  __int64 v40; // r8
  int v41; // eax
  int v42; // ecx
  int v43; // eax
  __int64 v44; // r15
  unsigned int v45; // edx
  __int64 v46; // rcx
  int v47; // eax
  unsigned int v48; // edx
  unsigned int v49; // ebx
  char v50; // al
  int v51; // eax
  unsigned int v52; // edi
  unsigned __int64 v53; // rax
  __int64 v54; // rax
  unsigned __int64 v55; // r8
  unsigned int v56; // edx
  unsigned int v57; // eax
  unsigned __int16 *v58; // rbx
  __int64 v59; // r8
  int v60; // eax
  void (__fastcall *v61)(_QWORD, unsigned int *); // rax
  void (__fastcall *v62)(__int64, _QWORD, unsigned int *); // rax
  __int64 v63; // rcx
  DXGGLOBAL *Global; // rax
  __int64 v65; // rcx
  __int64 v66; // rbx
  unsigned int v67; // edx
  __int64 v68; // r8
  __int64 v69; // rcx
  __int64 v70; // rdi
  __int64 v71; // rbx
  __int64 v72; // rdi
  __int64 v73; // rbx
  char v74; // bl
  unsigned int i; // edx
  int v76; // eax
  __int64 RenderCore; // rdi
  unsigned int v78; // edx
  const wchar_t *v79; // r9
  unsigned int v80; // r12d
  unsigned int v81; // r15d
  __int64 v82; // rdx
  __int64 v83; // r13
  __int16 v84; // ax
  int v85; // ecx
  int v86; // ebx
  int v87; // edi
  __int64 v88; // rbx
  unsigned __int8 IsGpuVaIoMmuGlobalSupported; // al
  int v90; // eax
  char v91; // al
  int v92; // eax
  __int64 v93; // rax
  unsigned int v94; // ecx
  int v95; // eax
  char v96; // cl
  char v97; // dl
  char v98; // al
  char v99; // dl
  char v100; // r8
  char v101; // cl
  int v102; // eax
  char v103; // al
  char v104; // dl
  unsigned __int8 v105; // dl
  char v106; // cl
  unsigned int v107; // eax
  int v108; // ecx
  __int64 v109; // rax
  struct DXGGLOBAL *v110; // rax
  struct DXGGLOBAL *v111; // rax
  struct DXGGLOBAL *v112; // rax
  char v113; // r8
  unsigned int v114; // ecx
  unsigned int v115; // edx
  DXGGLOBAL *v116; // rax
  int v117; // eax
  __int64 v118; // r8
  int v119; // eax
  int v120; // eax
  char v121; // cl
  struct DXGGLOBAL *v122; // rdi
  __int64 v123; // r8
  _DWORD *v124; // rbx
  int v125; // eax
  __int64 v126; // rax
  _QWORD *v127; // rbx
  int DisplayCore; // eax
  char v129; // cl
  char v130; // dl
  __int64 v131; // rax
  int v132; // eax
  char v133; // al
  __int64 v134; // rdx
  DXGADAPTER *v135; // rcx
  int v136; // eax
  __int64 v137; // rcx
  bool v138; // cf
  int v139; // eax
  DXGGLOBAL *v140; // rax
  int v141; // eax
  __int64 v142; // rax
  int v143; // eax
  __int64 v144; // r14
  __int64 v145; // rbx
  struct DXGGLOBAL *v146; // rax
  int v147; // eax
  struct DXGGLOBAL *v148; // rax
  __int64 v149; // rdx
  struct DXGGLOBAL *v150; // r14
  DXGGLOBAL *v151; // rcx
  unsigned int v152; // ebx
  struct DXGGLOBAL *v153; // rax
  struct DXGGLOBAL *v154; // rax
  __int64 v155; // [rsp+20h] [rbp-E0h]
  void *v156; // [rsp+20h] [rbp-E0h]
  void *v157; // [rsp+20h] [rbp-E0h]
  void *v158; // [rsp+20h] [rbp-E0h]
  void *v159; // [rsp+28h] [rbp-D8h]
  __int64 v160; // [rsp+28h] [rbp-D8h]
  __int64 v161; // [rsp+28h] [rbp-D8h]
  unsigned int v162; // [rsp+50h] [rbp-B0h] BYREF
  bool IsAdapterSessionized; // [rsp+54h] [rbp-ACh]
  unsigned int v164; // [rsp+58h] [rbp-A8h] BYREF
  int v165; // [rsp+5Ch] [rbp-A4h] BYREF
  __int128 v166; // [rsp+60h] [rbp-A0h] BYREF
  int v167; // [rsp+70h] [rbp-90h] BYREF
  __int64 v168; // [rsp+78h] [rbp-88h]
  __int64 v169; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v170; // [rsp+88h] [rbp-78h]
  struct _DXGKARG_QUERYADAPTERINFO v171; // [rsp+90h] [rbp-70h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v172; // [rsp+C0h] [rbp-40h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v173; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v174; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v175[2]; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v176[4]; // [rsp+138h] [rbp+38h] BYREF

  v3 = a3;
  *(_QWORD *)&v166 = a3;
  if ( KeGetCurrentIrql() )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 6985;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"KeGetCurrentIrql() == PASSIVE_LEVEL", 6985, 0, 0, 0, 0);
  }
  if ( *((_DWORD *)this + 50) )
    return 3221225485LL;
  g_Feature_FenceStorageUsingVidMmAlloc = (unsigned int)Feature_FenceStorageUsingVidMmAlloc__private_IsEnabledDeviceUsageNoInline() != 0;
  v6 = (struct _ERESOURCE *)operator new(104, 1265072196, 64);
  *((_QWORD *)this + 21) = v6;
  if ( !v6 )
  {
    WdLogSingleEntry2(3, this, -1073741801);
    WdLogGlobalForLineNumber = 7005;
    return 3221225495LL;
  }
  v8 = ExInitializeResourceLite(v6);
  LocallyUniqueId = v8;
  if ( v8 < 0 )
  {
    WdLogSingleEntry2(3, this, v8);
    WdLogGlobalForLineNumber = 7016;
    return (unsigned int)LocallyUniqueId;
  }
  *((_QWORD *)this + 27) = DeviceObject;
  *((_QWORD *)this + 28) = DpiGetSysMmAdapterFromDevice(DeviceObject);
  DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(DeviceObject);
  *((_QWORD *)this + 29) = DeviceAttachmentBaseRef;
  ObfDereferenceObject(DeviceAttachmentBaseRef);
  LocallyUniqueId = ZwAllocateLocallyUniqueId((PLUID)((char *)this + 4884));
  if ( LocallyUniqueId < 0 )
  {
    WdLogSingleEntry0(6);
    v11 = 7037;
    v12 = L"ZwAllocateLocallyUniqueId failed";
LABEL_12:
    v13 = 262145;
LABEL_13:
    WdLogGlobalForLineNumber = v11;
    DxgkLogInternalTriageEvent(0, v13, -1, (_DWORD)v12, v11, 0, 0, 0, 0);
    return (unsigned int)LocallyUniqueId;
  }
  v14 = (struct _ERESOURCE *)operator new(104, 1265072196, 64);
  *((_QWORD *)this + 35) = v14;
  if ( !v14 )
  {
    WdLogSingleEntry2(3, this, -1073741801);
    WdLogGlobalForLineNumber = 7050;
    return 3221225495LL;
  }
  v15 = ExInitializeResourceLite(v14);
  LocallyUniqueId = v15;
  if ( v15 < 0 )
  {
    WdLogSingleEntry2(3, this, v15);
    WdLogGlobalForLineNumber = 7061;
    return (unsigned int)LocallyUniqueId;
  }
  _InterlockedIncrement64((volatile signed __int64 *)this + 3);
  *((_QWORD *)this + 5) = -1;
  DeviceExtension = DeviceObject->DeviceExtension;
  v169 = 0;
  if ( DeviceExtension[481] )
  {
    v17 = DXGADAPTER::InitializeParavirtualizedAdapter(this, (struct DRIVER_WORKAROUNDS *)&v169);
    v18 = v17;
    if ( v17 < 0 )
    {
      WdLogSingleEntry1(2, v17);
      WdLogGlobalForLineNumber = 7084;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"InitializeParavirtualizedAdapter failed: 0x%I64x",
        v18,
        0,
        0,
        0,
        0);
      return (unsigned int)v18;
    }
  }
  else
  {
    *((_BYTE *)this + 1913) = 0;
    AdapterInfo = DpiGetAdapterInfo((int)DeviceObject, (char *)this + 1872, (char *)this + 288);
    LocallyUniqueId = AdapterInfo;
    if ( AdapterInfo < 0 )
    {
      WdLogSingleEntry2(3, this, AdapterInfo);
      WdLogGlobalForLineNumber = 7101;
      return (unsigned int)LocallyUniqueId;
    }
  }
  DpiFdoSetFeatureDatabaseDxgAdapter(*((_QWORD *)this + 27), this);
  *(_QWORD *)v175 = 0;
  v21 = (int (__fastcall *)(_QWORD, __int128 *))*((_QWORD *)this + 312);
  v174 = 0;
  if ( v21 && v21(*((_QWORD *)this + 303), &v174) >= 0 )
  {
    *(_QWORD *)((char *)this + 4956) = *((_QWORD *)&v174 + 1);
    *((_DWORD *)this + 1241) = v175[0];
  }
  IsAdapterSessionized = DXGADAPTER::IsAdapterSessionized(this, v20, v175, 0);
  v22 = IsAdapterSessionized;
  if ( IsAdapterSessionized )
  {
    SessionDataForSpecifiedSession = DXGSESSIONMGR::GetSessionDataForSpecifiedSession(
                                       *(DXGSESSIONMGR **)(*((_QWORD *)this + 2) + 984LL),
                                       v175[0]);
    if ( !SessionDataForSpecifiedSession
      || (v24 = DXGSESSIONDATA::AcquireSessionAdapterOrdinal(SessionDataForSpecifiedSession),
          *((_DWORD *)this + 61) = v24,
          v24 == -1) )
    {
      WdLogSingleEntry2(2, v175[0], -1073741801);
      v25 = v175[0];
      v26 = L"Exceeded the maximum number of sessionized adapter in session 0x%I64x, returning 0x%I64x.";
      v160 = -1073741801;
      WdLogGlobalForLineNumber = 7134;
LABEL_31:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v26, v25, v160, 0, 0, 0);
      return 3221225495LL;
    }
  }
  v27 = DXGGLOBAL::AcquireAdapterOrdinal(*((DXGGLOBAL **)this + 2), v22);
  *((_DWORD *)this + 60) = v27;
  if ( v27 == -1 )
    return 3221225495LL;
  if ( (*((_DWORD *)this + 111) & 0x200) != 0 )
    *((_BYTE *)DXGGLOBAL::GetGlobal() + 304896) = 1;
  v31 = *((_DWORD *)this + 111);
  if ( (v31 & 8) != 0 && (v31 & 0x10) != 0 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 7158;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"!(IsSoftGPU() && IsWarpAdapter())", 7158, 0, 0, 0, 0);
  }
  if ( !*((_QWORD *)this + 57) )
  {
    WdLogSingleEntry0(2);
    v32 = L"Miniport did not provide required DDIs";
    v161 = 0;
    v155 = 7165;
    WdLogGlobalForLineNumber = 7165;
LABEL_40:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v32, v155, v161, 0, 0, 0);
    return 3221225561LL;
  }
  if ( !*((_QWORD *)this + 74) )
    *((_QWORD *)this + 74) = DXGADAPTER::DefaultDdiEscape;
  if ( !*((_QWORD *)this + 135) )
    *((_QWORD *)this + 135) = W32kStub_GreSfmOpenTokenEvent;
  v34 = (int)DXGADAPTER::CallDriverQueryInterface(this, v28, v29, v30, (char *)this + 2224, v159);
  if ( (int)v34 >= 0 )
  {
    if ( *((_WORD *)this + 1113) >= 4u )
      goto LABEL_49;
  }
  else
  {
    v35 = WdLogNewEntry5_WdTrace();
    *(_QWORD *)(v35 + 24) = this;
    *(_QWORD *)(v35 + 32) = v34;
    WdLogGlobalForLineNumber = 7196;
  }
  memset((char *)this + 2224, 0, 0xB8u);
LABEL_49:
  v36 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 27) + 64LL) + 40LL) + 28LL);
  v170 = v36;
  *((_DWORD *)this + 602) = v36;
  if ( v36 < 0x7000 )
  {
    if ( v36 < 0x6002 )
      goto LABEL_58;
  }
  else
  {
    if ( !*((_DWORD *)this + 496) )
      goto LABEL_58;
    if ( *((_DWORD *)this + 497) )
    {
      v37 = 0;
LABEL_57:
      DXGADAPTER::SetModeBehavior(this, v33, v37);
      goto LABEL_58;
    }
  }
  if ( *((_DWORD *)this + 496) && *((_DWORD *)this + 497) )
  {
    v37 = 1;
    goto LABEL_57;
  }
LABEL_58:
  if ( v36 - 20480 <= 5 )
  {
    WdLogSingleEntry0(2);
    v38 = 7240;
    v39 = L"Cannot load an M1 threshold driver on later builds.";
LABEL_60:
    WdLogGlobalForLineNumber = v38;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v39, v38, 0, 0, 0, 0);
    return 3221225485LL;
  }
  *(_QWORD *)&v171.Type = 1;
  *(_QWORD *)&v171.InputDataSize = 0;
  v171.pOutputData = (char *)this + 2528;
  *(_OWORD *)&v171.OutputDataSize = 0;
  v171.pInputData = 0;
  v171.OutputDataSize = GetDriverCapsSizeFromDdiVersion(v36);
  if ( !v171.OutputDataSize )
    return 3221225485LL;
  v41 = DXGADAPTER::DdiQueryAdapterInfo(this, &v171, v40);
  v18 = v41;
  if ( v41 < 0 )
  {
    WdLogSingleEntry1(2, v41);
    WdLogGlobalForLineNumber = 7263;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Miniport failed DdiQueryAdapterInfo(DXGKQAITYPE_DRIVERCAPS) with status 0x%I64x",
      v18,
      0,
      0,
      0,
      0);
    return (unsigned int)v18;
  }
  v42 = *((_DWORD *)this + 716);
  if ( v42 > 9472 )
  {
    if ( *((_DWORD *)DeviceObject->DeviceExtension + 687) <= 0xA00Bu )
    {
      WdLogSingleEntry1(2, *((int *)this + 716));
      WdLogGlobalForLineNumber = 7269;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Miniport returned incorrect WDDMVersion: 0x%I64x",
        *((int *)this + 716),
        0,
        0,
        0,
        0);
      return 3221225485LL;
    }
    goto LABEL_69;
  }
  if ( v42 >= 4864 )
  {
LABEL_69:
    v43 = DxgkConvertWddmVersionToD3DKMTDriverVersion();
    goto LABEL_77;
  }
  if ( *((_QWORD *)this + 104) )
  {
    v43 = 1300;
  }
  else if ( v42 == 4608 )
  {
    v43 = 1200;
  }
  else if ( !*((_QWORD *)this + 100) || (v43 = 1105, (*((_DWORD *)this + 645) & 4) == 0) )
  {
    v43 = 1000;
  }
LABEL_77:
  v44 = 3132;
  v168 = 3132;
  *((_DWORD *)this + 783) = v43;
  v45 = *((_DWORD *)this + 776);
  if ( v43 >= 2600 )
  {
    if ( (v45 & 8) != 0 )
    {
      *((_DWORD *)this + 111) |= 0x80000u;
    }
    else if ( (*((_DWORD *)this + 111) & 0x80000) != 0 && v36 >= 0x11002 )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 7323;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"MiscCaps.ComputeOnly is not set, but the device belongs to the ComputeAccelerator class",
        7323,
        0,
        0,
        0,
        0);
      return 3221225485LL;
    }
  }
  else
  {
    v45 &= ~8u;
    *((_DWORD *)this + 776) = v45;
  }
  if ( *((_BYTE *)this + 1912) && (((v45 & 4) == 0) & (unsigned __int8)~(unsigned __int8)(v45 >> 3)) != 0 )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 7330;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"UMD name is missing and device is not compute only",
      7330,
      0,
      0,
      0,
      0);
    return 3221225524LL;
  }
  v46 = *((_QWORD *)this + 27);
  v164 = 0;
  LODWORD(v156) = 2;
  v47 = DpiReadPnpRegistryValue(v46, L"ACGSupported", &v164, 4, v156);
  v48 = v164;
  if ( v47 < 0 )
    v48 = 0;
  if ( v48 || *((int *)this + 783) >= 2200 )
  {
    v50 = 1;
    v49 = 0;
  }
  else
  {
    v49 = 0;
    v50 = 0;
  }
  *((_BYTE *)this + 212) = v50;
  if ( *((_BYTE *)this + 209) )
  {
    *((_BYTE *)v3 + 1) &= ~1u;
    *(_BYTE *)v3 &= 0x7Bu;
    *((_DWORD *)this + 776) &= 0xFFFFFFEB;
    *((_DWORD *)this + 649) &= 0xFFFFD2FF;
    *((_BYTE *)this + 3068) = 0;
    *((_BYTE *)this + 3096) = 1;
    *((_BYTE *)this + 3070) = 1;
    if ( *((_BYTE *)this + 210) )
      *((_DWORD *)this + 645) &= ~0x100000u;
  }
  else if ( v36 >= 0x5023 )
  {
    if ( g_bCreateParavirtualizedGpu )
    {
      v51 = *((_DWORD *)this + 111);
      if ( (v51 & 4) == 0 && (v51 & 0x10) == 0 && !*(_BYTE *)(*((_QWORD *)DeviceObject->DeviceExtension + 5) + 133LL) )
        *((_DWORD *)this + 649) |= 0x400u;
    }
  }
  v164 = *((_DWORD *)this + 74);
  v52 = v164;
  v53 = 352LL * v164;
  if ( !is_mul_ok(v164, 0x160u) )
    v53 = -1;
  v54 = operator new[](v53, 0x4B677844u, 64);
  *((_QWORD *)this + 390) = v54;
  v55 = v54;
  if ( !v54 )
  {
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 7389;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to allocate DXGK_PHYSICALADAPTERINFO",
      7389,
      0,
      0,
      0,
      0);
    return 3221225495LL;
  }
  if ( *((int *)this + 716) >= 0x2000 && v36 >= 0x5005 )
  {
    *((_DWORD *)this + 782) = 0;
    v56 = 0;
    v162 = 0;
    v57 = 0;
    while ( v56 < v52 )
    {
      *(_QWORD *)&v172.Type = 15;
      v58 = (unsigned __int16 *)(v55 + 352LL * v56);
      *(_QWORD *)&v172.InputDataSize = 4;
      v172.pOutputData = v58;
      *(_QWORD *)&v172.Flags.0 = 0;
      HIDWORD(v172.hKmdProcessHandle) = 0;
      v172.pInputData = &v162;
      v172.OutputDataSize = GetPhysicalAdapterCapsSizeFromDdiVersion(v36);
      v60 = DXGADAPTER::DdiQueryAdapterInfo(this, &v172, v59);
      if ( v60 < 0 )
      {
        WdLogSingleEntry1(4, v60);
        WdLogGlobalForLineNumber = 7417;
        v74 = 1;
        goto LABEL_144;
      }
      if ( v36 >= 0xC003 )
      {
        if ( (*((_DWORD *)v58 + 4) & 0x20) != 0 )
        {
          if ( *((_DWORD *)v58 + 6) >= (unsigned int)*v58 )
          {
            WdLogSingleEntry3(2, this, *((unsigned int *)v58 + 6), *v58);
            WdLogGlobalForLineNumber = 7435;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Adapter 0x%I64x: VirtualCopyEngineSupported but node index is invalid (VirtualCopyIndex:%u, "
                             "NumExecutionNodes:%u)",
              (__int64)this,
              *((unsigned int *)v58 + 6),
              *v58,
              0,
              0);
            return 3221225485LL;
          }
          if ( (*((_DWORD *)this + 649) & 0x2000) == 0 )
          {
            WdLogSingleEntry1(2, this);
            WdLogGlobalForLineNumber = 7442;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Adapter 0x%I64x: IoMmuSecureModeRequired must be set for a device exposing a virtual copy engine",
              (__int64)this,
              0,
              0,
              0,
              0);
            return 3221225485LL;
          }
        }
        v61 = (void (__fastcall *)(_QWORD, unsigned int *))*((_QWORD *)this + 221);
        if ( v61 )
        {
          *(_OWORD *)v176 = 0;
          v176[0] = v162;
          v61(*((_QWORD *)this + 36), v176);
          *((_BYTE *)v58 + 50) = v176[1] & 1;
        }
        v62 = (void (__fastcall *)(__int64, _QWORD, unsigned int *))*((_QWORD *)this + 222);
        if ( v62 )
        {
          v63 = *((_QWORD *)this + 36);
          *(_QWORD *)v176 = 0;
          v62(v63, v162, v176);
          *((_QWORD *)v58 + 43) = *(_QWORD *)v176;
        }
      }
      if ( !*((_BYTE *)this + 209) )
      {
        Global = DXGGLOBAL::GetGlobal();
        if ( DXGGLOBAL::GpuVaIoMmuEnabled(Global) )
        {
          v165 = 0;
          v176[0] = 0;
          LODWORD(v157) = 2;
          if ( (unsigned int)Feature_GpuVaIommuFixes__private_IsEnabledDeviceUsageNoInline() )
          {
            v66 = *(_QWORD *)(352LL * v162 + *((_QWORD *)this + 390) + 8);
            if ( (int)DpiReadPnpRegistryValue(v66, L"DxgkGpuVaIommuSupported", &v165, 4, v157) >= 0 )
              *(_DWORD *)(352LL * v162 + *((_QWORD *)this + 390) + 16) = (v165 != 0 ? 0x40 : 0)
                                                                       | *(_DWORD *)(352LL * v162
                                                                                   + *((_QWORD *)this + 390)
                                                                                   + 16)
                                                                       & 0xFFFFFFBF;
            v65 = v66;
          }
          else
          {
            if ( (int)DpiReadPnpRegistryValue(*((_QWORD *)this + 27), L"DxgkGpuVaIommuRequired", &v165, 4, v157) >= 0 )
              *(_DWORD *)(352LL * v162 + *((_QWORD *)this + 390) + 16) = (v165 != 0 ? 0x40 : 0)
                                                                       | *(_DWORD *)(352LL * v162
                                                                                   + *((_QWORD *)this + 390)
                                                                                   + 16)
                                                                       & 0xFFFFFFBF;
            v65 = *((_QWORD *)this + 27);
          }
          LODWORD(v158) = 2;
          if ( (int)DpiReadPnpRegistryValue(v65, L"DxgkGpuVaIommuGlobalSupported", v176, 4, v158) >= 0 )
            *(_DWORD *)(352LL * v162 + *((_QWORD *)this + 390) + 16) = (v176[0] != 0 ? 0x80 : 0)
                                                                     | *(_DWORD *)(352LL * v162
                                                                                 + *((_QWORD *)this + 390)
                                                                                 + 16)
                                                                     & 0xFFFFFF7F;
        }
      }
      v67 = v162;
      v68 = *((_QWORD *)this + 390);
      v69 = 352LL * v162;
      if ( (*(_DWORD *)(v69 + v68 + 16) & 2) != 0 )
      {
        *(_BYTE *)(v69 + v68 + 49) = 1;
        v67 = v162;
      }
      v70 = *((_QWORD *)this + 390);
      v71 = 352LL * v67;
      if ( (*(_DWORD *)(v71 + v70 + 16) & 0x40) != 0 )
      {
        if ( !DXGADAPTER::IsGpuVaIoMmuSupported(this) )
        {
          WdLogSingleEntry1(2, this);
          WdLogGlobalForLineNumber = 7519;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Adapter 0x%I64x: GpuVaIommuRequired is set for a physical adapter, but not in IOMMU_CAPS",
            (__int64)this,
            0,
            0,
            0,
            0);
          return 3221225485LL;
        }
        *(_BYTE *)(v71 + v70 + 49) = 1;
        *(_BYTE *)(352LL * v162 + *((_QWORD *)this + 390) + 48) = 1;
        v67 = v162;
      }
      v72 = *((_QWORD *)this + 390);
      v73 = 352LL * v67;
      if ( (*(_DWORD *)(v73 + v72 + 16) & 0x80u) != 0 )
      {
        if ( !DXGADAPTER::IsGpuVaIoMmuGlobalSupported(this) )
        {
          WdLogSingleEntry1(2, this);
          WdLogGlobalForLineNumber = 7530;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Adapter 0x%I64x: GpuVaIommuGlobalRequired is set for a physical adapter, but not in IOMMU_CAPS",
            (__int64)this,
            0,
            0,
            0,
            0);
          return 3221225485LL;
        }
        *(_BYTE *)(v73 + v72 + 49) = 1;
        *(_BYTE *)(352LL * v162 + *((_QWORD *)this + 390) + 48) = 1;
        v67 = v162;
      }
      v55 = *((_QWORD *)this + 390);
      v52 = v164;
      *((_DWORD *)this + 782) += *(unsigned __int16 *)(352LL * v67 + v55);
      v57 = *((_DWORD *)this + 782);
      v56 = v67 + 1;
      v162 = v56;
    }
    if ( *((int *)this + 783) <= 2400 && v57 > 0x40 )
    {
      WdLogSingleEntry3(2, this, 64, v57);
      WdLogGlobalForLineNumber = 7548;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Adapter 0x%I64x: Exceeded maximum number of %I64d nodes on pre-WDDM 2.5 adapter. Total node count: %I64d",
        (__int64)this,
        64,
        *((unsigned int *)this + 782),
        0,
        0);
      return 3221225485LL;
    }
    v74 = 0;
    if ( (*((_DWORD *)this + 648) & 1) == 0 )
    {
      WdLogSingleEntry1(2, this);
      WdLogGlobalForLineNumber = 7553;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Adapter 0x%I64x: SchedulingCaps.MultiEngineAware is not set by WDDMv2 driver",
        (__int64)this,
        0,
        0,
        0,
        0);
      return 3221225485LL;
    }
LABEL_144:
    if ( (*((_DWORD *)this + 649) & 0x800) != 0 )
    {
      v162 = 0;
      for ( i = 0; i < v52; v162 = i )
      {
        *(_QWORD *)v176 = 0;
        v171.pInputData = &v162;
        v171.Type = DXGKQAITYPE_FRAMEBUFFERSAVESIZE;
        v171.pOutputData = v176;
        v171.InputDataSize = 4;
        v171.OutputDataSize = 8;
        v76 = DXGADAPTER::DdiQueryAdapterInfo(this, &v171, v55);
        RenderCore = v76;
        if ( v76 < 0 )
        {
          WdLogSingleEntry1(2, v76);
          v79 = L"Failed to query frame buffer save area size. Status 0x%I64x";
          WdLogGlobalForLineNumber = 7572;
          goto LABEL_160;
        }
        if ( (v176[0] & 0xFFF) != 0 )
        {
          WdLogSingleEntry1(2, *(_QWORD *)v176);
          WdLogGlobalForLineNumber = 7578;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Frame buffer reserve size must be a multiple of PAGE_SIZE. Size=%I64u",
            *(__int64 *)v176,
            0,
            0,
            0,
            0);
          return 3221225485LL;
        }
        *(_QWORD *)(352LL * v162 + *((_QWORD *)this + 390) + 56) = *(_QWORD *)v176;
        v78 = v162;
        v55 = *(_QWORD *)(352LL * v162 + *((_QWORD *)this + 390) + 56);
        if ( v55 )
        {
          result = DXGADAPTER::CreateFrameBufferSaveAreaSection(this, v162, v55);
          if ( (int)result < 0 )
            return result;
          v78 = v162;
        }
        v52 = v164;
        i = v78 + 1;
      }
    }
    if ( !v74 )
      goto LABEL_170;
    v49 = 0;
  }
  v80 = 0;
  if ( v52 )
  {
    v81 = v164;
    do
    {
      v82 = *((_QWORD *)this + 390);
      v83 = 352LL * v80;
      v84 = *((_WORD *)this + 1302);
      *(_QWORD *)v176 = v82;
      *(_WORD *)(v82 + v83) = v84;
      v85 = *(_DWORD *)(v82 + v83 + 16)
          ^ ((unsigned __int8)*(_DWORD *)(v82 + v83 + 16)
           ^ (unsigned __int8)(*((_DWORD *)this + 649) >> 7))
          & 1;
      *(_DWORD *)(v82 + v83 + 16) = v85;
      v86 = v85 ^ (v85 ^ (*((_DWORD *)this + 649) >> 5)) & 2;
      *(_DWORD *)(v82 + v83 + 16) = v86;
      v87 = v86 ^ ((unsigned __int8)v86 ^ (unsigned __int8)(DXGADAPTER::IsGpuVaIoMmuSupported(this) << 6)) & 0x40;
      v88 = *(_QWORD *)v176;
      *(_DWORD *)(*(_QWORD *)v176 + v83 + 16) = v87;
      IsGpuVaIoMmuGlobalSupported = DXGADAPTER::IsGpuVaIoMmuGlobalSupported(this);
      *(_DWORD *)(v88 + v83 + 16) = v87
                                  ^ ((unsigned __int8)v87
                                   ^ (unsigned __int8)(IsGpuVaIoMmuGlobalSupported << 7))
                                  & 0x80;
      *(_WORD *)(v88 + v83 + 2) = *((_WORD *)this + 1300);
      *(_QWORD *)(v88 + v83 + 8) = *((_QWORD *)this + 27);
      if ( (((unsigned __int8)v87
           ^ ((unsigned __int8)v87
            ^ (unsigned __int8)(IsGpuVaIoMmuGlobalSupported << 7))
           & 0x80)
          & 0xC2) != 0 )
        *(_WORD *)(v88 + v83 + 48) = 257;
      ++v80;
    }
    while ( v80 < v81 );
    v44 = v168;
    v36 = v170;
    v3 = (struct _DXGK_ADAPTER_CAPS *)v166;
LABEL_170:
    v49 = 0;
    goto LABEL_171;
  }
  v3 = (struct _DXGK_ADAPTER_CAPS *)v166;
LABEL_171:
  if ( *(int *)((char *)this + v44) >= 2400 )
  {
    if ( *((_DWORD *)this + 776) >= 0x400u )
    {
      WdLogSingleEntry0(2);
      v39 = L"Driver should not set MiscCaps.Reserved bits";
      v38 = 7632;
      goto LABEL_60;
    }
    *((_BYTE *)this + 3185) = *((_BYTE *)this + 3104) & 1;
  }
  v90 = *((_DWORD *)this + 776);
  if ( (v90 & 0x10) != 0 && !*((_QWORD *)this + 175) )
  {
    WdLogSingleEntry0(2);
    v39 = L"Driver sets IndependentVidPnVSyncControl cap but does not support DxgkDdiControlInterrupt3, returning failure";
    v38 = 7642;
    goto LABEL_60;
  }
  if ( *((_BYTE *)this + 3348) )
    *((_DWORD *)this + 776) = v90 & 0xFFFFFFEF;
  if ( v36 >= 0x3001 )
  {
    v92 = *((_DWORD *)this + 716);
    if ( v92 != 4096
      && v92 != 4608
      && v92 != 4864
      && v92 != 0x2000
      && v92 != 8448
      && v92 != 8704
      && v92 != 8960
      && v92 != 9216
      && v92 != 9472
      && v92 != 9728
      && v92 != 9984
      && v92 != 10240
      && v92 != 10496
      && v92 != 12288
      && v92 != 12544
      && v92 != 12800 )
    {
      WdLogSingleEntry1(2, v92);
      WdLogGlobalForLineNumber = 7700;
      v32 = L"Miniport returned unknown WDDM version 0x%I64x";
      v93 = *((int *)this + 716);
LABEL_216:
      v161 = 0;
      v155 = v93;
      goto LABEL_40;
    }
  }
  else
  {
    *((_DWORD *)this + 716) = 4096;
  }
  if ( !*((_BYTE *)DXGGLOBAL::GetGlobal() + 928) || (v91 = 1, (*((_DWORD *)this + 111) & 8) != 0) )
    v91 = 0;
  *((_BYTE *)this + 3144) = v91;
  if ( v91 )
  {
    if ( *((int *)this + 716) < 4608
      && (*((_DWORD *)this + 764)
       || *((_DWORD *)this + 765)
       || *((_BYTE *)this + 3064)
       || *((_BYTE *)this + 3065)
       || *((_BYTE *)this + 3066)
       || (*((_DWORD *)this + 645) & 0x10000000) != 0
       || (*((_DWORD *)this + 648) & 0x14) != 0
       || *((_BYTE *)this + 3067)
       || *((_BYTE *)this + 3069)
       || *((_BYTE *)this + 3070)) )
    {
      WdLogSingleEntry0(2);
      v39 = L"Driver reports WDDM version less than 1.2 but implements some WDDM 1.2 features.";
      v38 = 7726;
      goto LABEL_60;
    }
    if ( *((int *)this + 716) < 4864
      && ((*((_DWORD *)this + 647) & 0x10) != 0
       || (*((_DWORD *)this + 649) & 0x10) != 0
       || *((_BYTE *)this + 3071)
       || *((_DWORD *)this + 768)) )
    {
      WdLogSingleEntry0(2);
      v39 = L"Driver reports WDDM version less than 1.3 but implements some WDDM 1.3 features.";
      v38 = 7741;
      goto LABEL_60;
    }
    if ( *((int *)this + 716) < 0x2000 && *((_BYTE *)this + 3076) )
    {
      WdLogSingleEntry0(2);
      v39 = L"Pre-WDDM 2.0 driver should not set the HybridIntegrated cap.";
      v38 = 7769;
      goto LABEL_60;
    }
  }
  v94 = *((_DWORD *)this + 649);
  v95 = v94 & 0x8010;
  if ( (v94 & 0x10000) != 0 )
  {
    if ( v95 != 32784 )
    {
      WdLogSingleEntry0(2);
      v39 = L"Driver reports CrossAdapterResourceScanout but does not report lower tier support.";
      v38 = 7783;
      goto LABEL_60;
    }
  }
  else if ( v95 == 0x8000 )
  {
    WdLogSingleEntry0(2);
    v39 = L"Driver reports CrossAdapterResourceTexture but does not report lower tier support.";
    v38 = 7791;
    goto LABEL_60;
  }
  if ( v36 >= 0x4000 )
  {
    if ( v36 >= 0x5011 )
      goto LABEL_237;
  }
  else
  {
    v94 &= ~0x10u;
    *((_BYTE *)this + 3071) = 0;
    *((_DWORD *)this + 649) = v94;
  }
  if ( (*((_DWORD *)this + 111) & 1) != 0
    && (((*((_DWORD *)this + 111) & 0x1000) != 0) & (unsigned __int8)(v94 >> 4)) != 0 )
  {
    *((_BYTE *)this + 3076) = 1;
  }
LABEL_237:
  v96 = *(_BYTE *)v3 ^ (*(_BYTE *)v3 ^ (4 * *((_BYTE *)this + 3064))) & 4;
  *(_BYTE *)v3 = v96;
  v97 = v96 & 0xF7 | (*((_BYTE *)this + 3070) != 0 ? 8 : 0);
  *(_BYTE *)v3 = v97;
  v98 = v97 ^ (v97 ^ (32 * (*((_DWORD *)this + 649) >> 4))) & 0x20;
  *(_BYTE *)v3 = v98;
  v99 = v98 ^ (v98 ^ (*((_BYTE *)this + 3071) << 6)) & 0x40;
  *(_BYTE *)v3 = v99;
  v100 = v99 & 0xEF;
  *((_DWORD *)v3 + 1) = *((_DWORD *)this + 641);
  v101 = *((_BYTE *)v3 + 1) ^ (*((_BYTE *)this + 3076) ^ *((_BYTE *)v3 + 1)) & 1;
  *((_BYTE *)v3 + 1) = v101;
  *((_DWORD *)v3 + 2) = *((_DWORD *)this + 716);
  v102 = *((_DWORD *)this + 776) >> 3;
  *(_BYTE *)v3 = v99 & 0xEF;
  v103 = v101 ^ (v101 ^ (32 * v102)) & 0x20;
  *((_BYTE *)v3 + 1) = v103;
  if ( v36 >= 0x5021 )
  {
    v100 = v99 ^ (v99 ^ (16 * *((_BYTE *)this + 3096))) & 0x10;
    *(_BYTE *)v3 = v100;
  }
  if ( !*((_BYTE *)this + 209) )
  {
    if ( (v100 & 0x40) != 0 )
    {
      if ( v36 < 0x5005 && (*((_DWORD *)this + 496) || *((_DWORD *)this + 497)) )
      {
        WdLogSingleEntry1(2, *((_QWORD *)this + 27));
        WdLogGlobalForLineNumber = 7854;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Driver reports device 0x%I64x is hybrid discrete device but it has VidPn source and target.",
          *((_QWORD *)this + 27),
          0,
          0,
          0,
          0);
        return 3221225485LL;
      }
      v104 = v103 ^ (v103 ^ (2 * *((_BYTE *)this + 3099))) & 2;
      *((_BYTE *)v3 + 1) = v104;
    }
    else
    {
      v104 = v103;
    }
    v105 = v104 & 1;
    v106 = 0;
    if ( (v100 & 0x40) == 0 )
      v106 = v105 ^ 1;
    if ( !v106 && (v100 & 0x20) == 0 )
    {
      WdLogSingleEntry1(2, *((_QWORD *)this + 27));
      WdLogGlobalForLineNumber = 7868;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Driver reports device 0x%I64x as hybrid device but does not support cross adapter resource.",
        *((_QWORD *)this + 27),
        0,
        0,
        0,
        0);
      return 3221225485LL;
    }
    if ( ((unsigned __int8)-((v100 & 0x40) != 0) & v105) != 0 )
    {
      WdLogSingleEntry1(2, *((_QWORD *)this + 27));
      WdLogGlobalForLineNumber = 7875;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Driver reports both HybridIntegrated and HybridDiscrete caps 0x%I64x",
        *((_QWORD *)this + 27),
        0,
        0,
        0,
        0);
      return 3221225485LL;
    }
    if ( v105 && !*((_DWORD *)this + 497) )
    {
      WdLogSingleEntry1(2, *((_QWORD *)this + 27));
      WdLogGlobalForLineNumber = 7883;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Driver reports the HybridIntegrated cap, but the adapter has no outputs. 0x%I64x",
        *((_QWORD *)this + 27),
        0,
        0,
        0,
        0);
      return 3221225485LL;
    }
    if ( *((_BYTE *)this + 3066) && (!*((_QWORD *)this + 101) || !*((_QWORD *)this + 102) || !*((_QWORD *)this + 103)) )
    {
      WdLogSingleEntry0(2);
      v39 = L"Driver reports SupportPerEngineTDR cap but does not fill in all of the required DDIs.";
      v38 = 7897;
      goto LABEL_60;
    }
    if ( (*((_DWORD *)this + 645) & 4) != 0 && !*((_QWORD *)this + 100) )
    {
      WdLogSingleEntry0(2);
      v39 = L"Driver reports SupportKernelModeCommandBuffer cap but does not fill in the pfnRenderKm DDI.";
      v38 = 7904;
      goto LABEL_60;
    }
    if ( *((_BYTE *)this + 3069) && (!*((_QWORD *)this + 105) || !*((_QWORD *)this + 106)) )
    {
      WdLogSingleEntry0(2);
      v39 = L"Driver reports SupportRuntimePowerManagement cap but does not fill in the pfnSetPowerComponentFState or pfnP"
             "owerRuntimeControlRequest DDI.";
      v38 = 7912;
      goto LABEL_60;
    }
    if ( v36 < 0x300C && *((_QWORD *)this + 105) && *((_QWORD *)this + 106) )
      *((_BYTE *)this + 3069) = 1;
  }
  *((_WORD *)this + 1573) = 0;
  *((_BYTE *)this + 3148) = 0;
  if ( !*((_BYTE *)this + 3068) )
    goto LABEL_311;
  if ( v36 < 0x300B )
  {
    WdLogSingleEntry0(2);
    v39 = L"Driver reports SupportMultiPlaneOverlay cap but it is not compiled with expected header files.";
    v38 = 7934;
    goto LABEL_60;
  }
  if ( v36 < 0x4000 )
  {
    *((_BYTE *)this + 3146) = 1;
    goto LABEL_293;
  }
  if ( v36 == 0x4000 )
  {
    *((_BYTE *)this + 3147) = 1;
    goto LABEL_293;
  }
  v107 = *((_DWORD *)this + 768);
  if ( !v107 )
  {
    WdLogSingleEntry0(2);
    v39 = L"Driver reports SupportMultiPlaneOverlay cap but doesn't report any overlay planes or panel fitter.";
    v38 = 7947;
    goto LABEL_60;
  }
  if ( v107 <= 8 )
  {
    if ( v36 > 0x5000 )
      *((_BYTE *)this + 3148) = 1;
    goto LABEL_293;
  }
  v108 = *((_DWORD *)this + 716);
  if ( v108 < 8704 )
  {
    if ( v108 < 0x2000 || v107 != 10 )
    {
      WdLogSingleEntry0(2);
      v38 = 7970;
      goto LABEL_286;
    }
    *((_DWORD *)this + 768) = 8;
  }
  else if ( v107 > 0xA )
  {
    WdLogSingleEntry0(2);
    v38 = 7957;
LABEL_286:
    v39 = L"Driver reports more than the supported number of overlay planes.";
    goto LABEL_60;
  }
LABEL_293:
  v109 = *((_QWORD *)this + 109);
  if ( !v109 && !*((_QWORD *)this + 125) && !*((_QWORD *)this + 129) )
  {
    WdLogSingleEntry0(2);
    v38 = 7986;
LABEL_297:
    v39 = L"Driver reports SupportMultiPlaneOverlay cap but does not fill in all of the required DDIs.";
    goto LABEL_60;
  }
  if ( v36 > 0x4002 && !*((_QWORD *)this + 113) && !*((_QWORD *)this + 124) && !*((_QWORD *)this + 128) )
  {
    WdLogSingleEntry0(2);
    v38 = 7998;
    goto LABEL_297;
  }
  if ( !*((_BYTE *)this + 3067) )
  {
    WdLogSingleEntry0(2);
    v39 = L"Driver reports SupportMultiPlaneOverlay cap but DirectFlip is not supported.";
    v38 = 8008;
    goto LABEL_60;
  }
  if ( v109 )
  {
    v110 = DXGGLOBAL::GetGlobal();
    DXGGLOBAL::RecordFeatureUsage(v110, 1, 1);
  }
  if ( *((_QWORD *)this + 125) )
  {
    v111 = DXGGLOBAL::GetGlobal();
    DXGGLOBAL::RecordFeatureUsage(v111, 2, 1);
  }
  if ( *((_QWORD *)this + 129) )
  {
    v112 = DXGGLOBAL::GetGlobal();
    DXGGLOBAL::RecordFeatureUsage(v112, 3, 1);
  }
LABEL_311:
  *((_BYTE *)this + 3183) = 0;
  if ( *((_BYTE *)this + 209) )
    goto LABEL_324;
  v113 = 0;
  if ( v36 >= 0x700A && *((int *)this + 716) >= 8704 && (!*((_QWORD *)this + 83) || *((_QWORD *)this + 146)) )
  {
    *((_BYTE *)this + 3183) = 1;
    v113 = 1;
  }
  if ( *((int *)this + 716) < 8960 )
  {
LABEL_324:
    *((_DWORD *)this + 644) &= 0xFFFFFFE3;
  }
  else
  {
    v114 = (*((_DWORD *)this + 644) >> 3) & 1;
    v115 = (*((_DWORD *)this + 644) >> 2) & 1;
    if ( v115 < v114 || v114 < ((*((_DWORD *)this + 644) >> 4) & 1u) )
    {
      WdLogSingleEntry2(2, *((_QWORD *)this + 27), -1073741811);
      WdLogGlobalForLineNumber = 8058;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Driver reports support higher level of colorSpaceTransform but not lower levels on device 0x%I64x,"
                       " returning 0x%I64x.",
        *((_QWORD *)this + 27),
        -1073741811,
        0,
        0,
        0);
      return 3221225485LL;
    }
    if ( !v113 && v115 )
    {
      WdLogSingleEntry2(2, *((_QWORD *)this + 27), -1073741811);
      WdLogGlobalForLineNumber = 8066;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"ColorSpaceTransform is supported on the device 0x%I64x which does not have pfnSetTargetGamma, returning 0x%I64x.",
        *((_QWORD *)this + 27),
        -1073741811,
        0,
        0,
        0);
      return 3221225485LL;
    }
  }
  if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 27) + 64LL) + 40LL) + 133LL) && !*((_BYTE *)this + 209) )
  {
    LOBYTE(v49) = *((_DWORD *)this + 716) >= 0x2000;
    v116 = DXGGLOBAL::GetGlobal();
    v117 = DXGGLOBAL::DeferredInitialize(v116, v49);
    v49 = 0;
    RenderCore = v117;
    if ( v117 < 0 )
    {
      WdLogSingleEntry1(2, v117);
      v79 = L"DXGGLOBAL::DeferredInitialize failed (Status = 0x%I64x).";
      WdLogGlobalForLineNumber = 8093;
LABEL_160:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v79, RenderCore, 0, 0, 0, 0);
      return (unsigned int)RenderCore;
    }
  }
  DXGADAPTER::Config = 0;
  DXGADAPTER::ReadConfig(this, v3);
  DXGADAPTER::InitializeDriverWorkarounds(this);
  if ( *((_BYTE *)this + 209) )
  {
    **((_DWORD **)this + 392) = **((_DWORD **)this + 392) & 0xFFFDFFFF | v169 & 0x20000;
    **((_DWORD **)this + 392) = **((_DWORD **)this + 392) & 0xFFFE7FFF | v169 & 0x18000;
    **((_DWORD **)this + 392) = **((_DWORD **)this + 392) & 0xFFEFFFFF | v169 & 0x100000;
    **((_DWORD **)this + 392) = **((_DWORD **)this + 392) & 0xFFF3FFFF | v169 & 0xC0000;
    *((_BYTE *)this + 3149) = 0;
  }
  else if ( (*((_DWORD *)this + 111) & 0x10) != 0 && *((_BYTE *)this + 3199) )
  {
    *((_DWORD *)this + 649) |= 0x400u;
  }
  v119 = *((_DWORD *)this + 716);
  if ( v119 < 9216 )
    goto LABEL_337;
  if ( *((_QWORD *)this + 166) )
  {
    if ( *((_QWORD *)this + 167) )
      goto LABEL_338;
LABEL_351:
    WdLogSingleEntry0(2);
    v39 = L"Driver cannot support only one of DdiQueryDiagnosticTypesSupport and DdiControlDiagnosticReporting.";
    v38 = 8147;
    goto LABEL_60;
  }
  if ( *((_QWORD *)this + 167) )
    goto LABEL_351;
LABEL_337:
  *((_QWORD *)this + 166) = W32kStub_UserRemoveWindowedSwapChain;
  *((_QWORD *)this + 167) = DXGADAPTER::DefaultDdiControlDiagnosticReporting;
LABEL_338:
  if ( v119 >= 12800 && v36 >= 0x11001 )
  {
    memset(&v172, 0, 24);
    v172.Type = DXGKQAITYPE_POWERCOMPONENTINFO|0x20;
    *(_OWORD *)&v172.OutputDataSize = 0;
    v172.pOutputData = (char *)this + 5300;
    v172.OutputDataSize = 4;
    if ( (int)DXGADAPTER::DdiQueryAdapterInfo(this, &v172, v118) < 0 )
    {
      *(_QWORD *)(WdLogNewEntry5_WdTrace() + 24) = this;
      WdLogGlobalForLineNumber = 8162;
    }
  }
  v167 = 0;
  memset(&v173, 0, 24);
  v173.Type = DXGKQAITYPE_PHYSICALADAPTERCAPS|0x20;
  v173.pOutputData = &v167;
  *(_OWORD *)&v173.OutputDataSize = 0;
  v173.OutputDataSize = 4;
  v120 = DXGADAPTER::DdiQueryAdapterInfo(this, &v173, v118);
  v121 = *((_BYTE *)this + 3200) & 0xFD;
  if ( v120 >= 0 )
    v121 |= 2 * (v167 & 1);
  *((_BYTE *)this + 3200) = v121;
  result = DXGADAPTER::CheckMcdmDdiOverall(this);
  if ( (int)result >= 0 )
  {
    v122 = DXGGLOBAL::GetGlobal();
    *(_QWORD *)((char *)this + 4940) = 0;
    *(_QWORD *)((char *)this + 4948) = -1;
    v166 = 0;
    while ( v49 < 2 )
    {
      DWORD1(v166) = *((_DWORD *)v122 + v49 + 76239);
      if ( DWORD1(v166) )
      {
        if ( v49 )
        {
          LODWORD(v166) = v166 | 2;
          DWORD2(v166) |= 0xFFFFFFFE;
        }
        else
        {
          LODWORD(v166) = v166 | 1;
          DWORD2(v166) |= 0xFFFFFFFC;
        }
        HIDWORD(v166) = v49;
        DXGADAPTER::UpdateDiagnosticReporting(this, (struct DXGADAPTER::_ADAPTER_UPDATE_DIAGNOSTIC_REPORTING *)&v166);
      }
      ++v49;
    }
    DXGADAPTER::QueryFeatureEnablement(this);
    if ( (*((_DWORD *)this + 648) & 0x800) != 0 )
    {
      if ( (*((_BYTE *)this + 5172) & 1) == 0 )
      {
        WdLogSingleEntry0(2);
        v38 = 8202;
        v39 = L"Driver reports NativeGpuFence cap when NativeFence feature is disabled, returning failure";
        goto LABEL_60;
      }
      v124 = (_DWORD *)((char *)this + 5208);
      v171.Type = DXGKQAITYPE_QUERYSEGMENT3|0x20;
      v171.pOutputData = (char *)this + 5208;
      v171.OutputDataSize = 56;
      v125 = DXGADAPTER::DdiQueryAdapterInfo(this, &v171, v123);
      RenderCore = v125;
      if ( v125 < 0 )
      {
        WdLogSingleEntry1(2, v125);
        v79 = L"Failed to get DXGK_NATIVE_FENCE_CAPS. Status 0x%I64x";
        WdLogGlobalForLineNumber = 8213;
        goto LABEL_160;
      }
      if ( *v124 > 0x38u )
      {
        WdLogSingleEntry2(2, (unsigned int)*v124, 56);
        WdLogGlobalForLineNumber = 8221;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Driver specified native fence MonitoredValuePadding (%u) greater than maximum limit of %u bytes",
          (unsigned int)*v124,
          56,
          0,
          0,
          0);
        return (unsigned int)RenderCore;
      }
    }
    RenderCore = (int)ADAPTER_RENDER::CreateRenderCore(this, (struct ADAPTER_RENDER **)this + 407);
    v126 = *((_QWORD *)this + 407);
    if ( (int)RenderCore < 0 )
    {
      if ( v126 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 8233;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pRenderCore == NULL", 8233, 0, 0, 0, 0);
      }
      WdLogSingleEntry2(2, this, RenderCore);
      WdLogGlobalForLineNumber = 8236;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to create ADAPTER_RENDER on adapter 0x%I64x (Status = 0x%I64x).",
        (__int64)this,
        RenderCore,
        0,
        0,
        0);
      return (unsigned int)RenderCore;
    }
    if ( v126 )
    {
      if ( IsAdapterSessionized )
      {
        WdLogSingleEntry0(2);
        v93 = 8252;
        v32 = L"Render capable adapter should NOT be sessionized!";
        WdLogGlobalForLineNumber = 8252;
        goto LABEL_216;
      }
      if ( (((*((_DWORD *)this + 776) & 4) == 0) & (unsigned __int8)~(unsigned __int8)(*((_DWORD *)this + 776) >> 3)) != 0 )
        *((_BYTE *)this + 3200) |= 1u;
    }
    v127 = (_QWORD *)((char *)this + 3248);
    DisplayCore = ADAPTER_DISPLAY::CreateDisplayCore(this, (struct ADAPTER_DISPLAY **)this + 406);
    RenderCore = DisplayCore;
    if ( DisplayCore < 0 )
    {
      if ( *v127 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 8267;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pDisplayCore == NULL", 8267, 0, 0, 0, 0);
      }
      WdLogSingleEntry2(2, this, RenderCore);
      WdLogGlobalForLineNumber = 8270;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to create ADAPTER_DISPLAY on adapter 0x%I64x (Status = 0x%I64x).",
        (__int64)this,
        RenderCore,
        0,
        0,
        0);
      return (unsigned int)RenderCore;
    }
    if ( !*((_QWORD *)this + 407) && !*v127 )
    {
      WdLogSingleEntry2(2, this, -1073741735);
      v32 = L"Current adapter 0x%I64x does not have display or render capabilities (Status = 0x%I64x).";
      v161 = -1073741735;
      v155 = (__int64)this;
      WdLogGlobalForLineNumber = 8283;
      goto LABEL_40;
    }
    if ( (*((_DWORD *)this + 776) & 0x200) != 0 && *v127 )
    {
      WdLogSingleEntry1(2, -1073741811);
      WdLogGlobalForLineNumber = 8292;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"TestOnly cannot be used with display adapters. Status=0x%.8x",
        -1073741811,
        0,
        0,
        0,
        0);
      return 3221225485LL;
    }
    v129 = *(_BYTE *)v3 & 0xFE | (*((_QWORD *)this + 406) != 0);
    *(_BYTE *)v3 = v129;
    v130 = v129 & 0xFD | (*((_QWORD *)this + 407) != 0 ? 2 : 0);
    *(_BYTE *)v3 = v130;
    v131 = *((_QWORD *)this + 406);
    if ( v131 )
      v132 = *(_DWORD *)(v131 + 24) & 1;
    else
      LOBYTE(v132) = 0;
    v133 = v130 & 0x7F | ((_BYTE)v132 << 7);
    *(_BYTE *)v3 = v133;
    if ( (v133 & 1) != 0 )
      *((_BYTE *)v3 + 1) = *((_BYTE *)v3 + 1) & 0xFB | (DXGADAPTER::DriverSupportSetTimingsFromVidPn(this) != 0 ? 4 : 0);
    else
      *((_BYTE *)v3 + 1) &= ~4u;
    if ( !*((_QWORD *)this + 407) )
      *((_DWORD *)this + 645) |= 1u;
    if ( DXGADAPTER::IsDxgmms2(this) )
    {
      v136 = *((_DWORD *)this + 111);
      if ( (v136 & 4) == 0
        && (v136 & 8) == 0
        && v134
        && v36 >= 0x5008
        && (!*((_QWORD *)this + 114) || !*((_QWORD *)this + 126)) )
      {
        WdLogSingleEntry0(2);
        v38 = 8333;
        v39 = L"Driver is compiled against DXGKDDI_INTERFACE_VERSION_WDDM2_0_M2_2_1 or greater, but does not fill in the p"
               "fnCalibrateGpuClock or pfnSetStablePowerState DDI.";
        goto LABEL_60;
      }
    }
    if ( *((_BYTE *)this + 3144) && DXGADAPTER::IsFullWDDMAdapter(v135) && *((int *)this + 716) >= 4608 )
    {
      if ( !*((_BYTE *)this + 3067) )
      {
        WdLogSingleEntry0(2);
        v38 = 8348;
        v39 = L"Driver reports WDDM version 1.2 but does not implement all mandatory WDDM 1.2 full adapter features.";
        goto LABEL_60;
      }
    }
    else if ( !*((_BYTE *)this + 3067) )
    {
      goto LABEL_407;
    }
    if ( *((_BYTE *)this + 209) )
      goto LABEL_408;
    v137 = *((_QWORD *)this + 407);
    if ( !v137
      || !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)(*(_QWORD *)(v137 + 760) + 8LL) + 664LL))(*(_QWORD *)(v137 + 768)) )
    {
      *(_WORD *)((char *)this + 3067) = 0;
    }
LABEL_407:
    if ( !*((_BYTE *)this + 209) )
    {
LABEL_409:
      v138 = DXGADAPTER::IsBddFallbackDriver(this) != 0;
      v139 = *((_DWORD *)this + 111);
      *((_DWORD *)this + 50) = v138 ? 3 : 1;
      if ( (v139 & 0x10) != 0 && !*((_QWORD *)this + 406) )
      {
        DXGGLOBALSHAREMUTEX::DXGGLOBALSHAREMUTEX((DXGGLOBALSHAREMUTEX *)&v166);
        DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)&v166);
        if ( *((_QWORD *)DXGGLOBAL::GetGlobal() + 124) )
        {
          WdLogSingleEntry2(2, this, -1073741735);
          WdLogGlobalForLineNumber = 8398;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Current adapter 0x%I64x does not have display or render capabilities (Status = 0x%I64x).",
            (__int64)this,
            -1073741735,
            0,
            0,
            0);
        }
        else
        {
          _InterlockedIncrement64((volatile signed __int64 *)this + 3);
          *((_QWORD *)this + 4) = -1;
          v140 = DXGGLOBAL::GetGlobal();
          DXGGLOBAL::SetWarpAdapter(v140, this);
        }
        DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v166);
      }
      if ( *((_BYTE *)this + 209) || (v141 = DXGADAPTER::InitializePowerManagement(this), RenderCore = v141, v141 >= 0) )
      {
        if ( *((_BYTE *)this + 3144) )
        {
          if ( *((int *)this + 716) >= 4864 )
          {
            if ( DXGADAPTER::IsFullWDDMAdapter(this) )
            {
              v143 = *((_DWORD *)this + 111);
              if ( (v143 & 4) == 0 && (v143 & 0x20) == 0 && (*((_DWORD *)this + 647) & 0x10) == 0 )
              {
                WdLogSingleEntry0(2);
                v38 = 8429;
                v39 = L"WDDM 1.3 driver must support independent flip.";
                goto LABEL_60;
              }
            }
          }
        }
      }
      else
      {
        WdLogSingleEntry2(2, this, v141);
        WdLogGlobalForLineNumber = 8416;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed to initialize power management for the adapter 0x%I64x (Status = 0x%I64x).",
          (__int64)this,
          RenderCore,
          0,
          0,
          0);
      }
      if ( (*((_DWORD *)this + 111) & 0x10) != 0 )
        *((_BYTE *)this + 3186) = 1;
      if ( v36 >= 0xA008 )
        *((_BYTE *)this + 3186) = 1;
      v142 = operator new(40, 1265072196, 64);
      if ( v142 )
      {
        *(_OWORD *)v142 = 0;
        *(_OWORD *)(v142 + 16) = 0;
        *(_QWORD *)(v142 + 32) = 0;
      }
      else
      {
        v142 = 0;
      }
      *((_QWORD *)this + 637) = v142;
      if ( !v142 )
      {
        WdLogSingleEntry0(2);
        v26 = L"Failed to allocate MockDriverState object";
        v25 = 8467;
        WdLogGlobalForLineNumber = 8467;
        v160 = 0;
        goto LABEL_31;
      }
      LocallyUniqueId = MOCKDRIVERSTATE::Initialize((MOCKDRIVERSTATE *)v142, this);
      if ( LocallyUniqueId < 0 )
      {
        WdLogSingleEntry0(2);
        v11 = 8474;
        v12 = L"Failed to initialize MockDriverState object";
        v13 = 0x40000;
        goto LABEL_13;
      }
      *((_BYTE *)this + 5104) = 0;
      LocallyUniqueId = DXGADAPTER::InitializeVSyncPhaseState(this);
      if ( LocallyUniqueId < 0 )
      {
        WdLogSingleEntry0(6);
        v11 = 8487;
        v12 = L"Failed to allocate VSync Phase Timer state";
        goto LABEL_12;
      }
      v176[0] = 0;
      GetCabcOptionFromRegistry(v176);
      if ( (int)ZwUpdateWnfStateData(&WNF_DXGK_CABC_OPTION_CHANGED, v176, 4) < 0 )
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 8502;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Failed to initialize CABC State", 8502, 0, 0, 0, 0);
      }
      v144 = *((_QWORD *)this + 407);
      if ( v144 && !*((_BYTE *)this + 209) )
      {
        v145 = *(_QWORD *)(v144 + 736);
        v146 = DXGGLOBAL::GetGlobal();
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)(v145 + 8) + 936LL))(
          *(_QWORD *)(v144 + 744),
          (__int64)v146 + 1344);
      }
      if ( (*((_DWORD *)this + 111) & 1) != 0 )
        *((_QWORD *)DXGGLOBAL::GetGlobal() + 128) = *(_QWORD *)((char *)this + 412);
      if ( (int)RenderCore < 0 )
        return (unsigned int)RenderCore;
      if ( v164 <= 1 )
        goto LABEL_452;
      v147 = *((_DWORD *)this + 105);
      if ( v147 == 4318 )
      {
        v148 = DXGGLOBAL::GetGlobal();
        v149 = 7;
      }
      else
      {
        if ( v147 != 4098 )
          goto LABEL_452;
        v148 = DXGGLOBAL::GetGlobal();
        v149 = 8;
      }
      DXGGLOBAL::RecordFeatureUsage(v148, v149, 1);
LABEL_452:
      v150 = DXGGLOBAL::GetGlobal();
      if ( DXGGLOBAL::ConsiderForMultiAdapterFeatureUsage(v151, this) )
      {
        v152 = *((_DWORD *)this + 783);
        if ( v152 > *((_DWORD *)v150 + 76316) )
        {
          v153 = DXGGLOBAL::GetGlobal();
          DXGGLOBAL::RecordFeatureUsage(v153, 11, v152);
          *((_DWORD *)v150 + 76316) = v152;
        }
        if ( v152 < *((_DWORD *)v150 + 76315) )
        {
          v154 = DXGGLOBAL::GetGlobal();
          DXGGLOBAL::RecordFeatureUsage(v154, 10, v152);
          *((_DWORD *)v150 + 76315) = v152;
        }
      }
      return (unsigned int)RenderCore;
    }
LABEL_408:
    *((_QWORD *)this + 114) = 0;
    goto LABEL_409;
  }
  return result;
}

```

## disassembly

```asm
0x1401c6fe0  mov     [rsp-8+arg_18], rbx
0x1401c6fe5  push    rbp
0x1401c6fe6  push    rsi
0x1401c6fe7  push    rdi
0x1401c6fe8  push    r12
0x1401c6fea  push    r13
0x1401c6fec  push    r14
0x1401c6fee  push    r15
0x1401c6ff0  lea     rbp, [rsp-50h]
0x1401c6ff5  sub     rsp, 150h
0x1401c6ffc  mov     rax, cs:__security_cookie
0x1401c7003  xor     rax, rsp
0x1401c7006  mov     [rbp+80h+var_38], rax
0x1401c700a  mov     r12, r8
0x1401c700d  mov     qword ptr [rsp+180h+var_120], r8
0x1401c7012  mov     rdi, rdx
0x1401c7015  mov     rsi, rcx
0x1401c7018  call    cs:__imp_KeGetCurrentIrql
0x1401c701f  nop     dword ptr [rax+rax+00h]
0x1401c7024  or      r13d, 0FFFFFFFFh
0x1401c7028  xor     r15d, r15d
0x1401c702b  test    al, al
0x1401c702d  jz      short loc_1401C7079
0x1401c702f  lea     ecx, [r15+1]
0x1401c7033  call    cs:__imp_WdLogSingleEntry0
0x1401c703a  nop     dword ptr [rax+rax+00h]
0x1401c703f  mov     [rsp+180h+var_140], r15
0x1401c7044  lea     r9, aKegetcurrentir_4; "KeGetCurrentIrql() == PASSIVE_LEVEL"
0x1401c704b  mov     [rsp+180h+var_148], r15
0x1401c7050  mov     eax, 1B49h
0x1401c7055  mov     [rsp+180h+var_150], r15
0x1401c705a  mov     r8d, r13d
0x1401c705d  mov     [rsp+180h+var_158], r15
0x1401c7062  mov     edx, 40002h
0x1401c7067  xor     ecx, ecx
0x1401c7069  mov     [rsp+180h+var_160], rax
0x1401c706e  mov     cs:WdLogGlobalForLineNumber, eax
0x1401c7074  call    DxgkLogInternalTriageEvent
0x1401c7079  mov     eax, [rsi+0C8h]
0x1401c707f  test    eax, eax
0x1401c7081  jnz     loc_1401C7654
0x1401c7087  call    Feature_FenceStorageUsingVidMmAlloc__private_IsEnabledDeviceUsageNoInline
0x1401c708c  mov     r8d, 40h ; '@'
0x1401c7092  test    eax, eax
0x1401c7094  mov     edx, 4B677844h
0x1401c7099  setnz   cs:?g_Feature_FenceStorageUsingVidMmAlloc@@3EC; uchar volatile g_Feature_FenceStorageUsingVidMmAlloc
0x1401c70a0  lea     r14d, [r8+28h]
0x1401c70a4  mov     ecx, r14d
0x1401c70a7  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401c70ac  mov     [rsi+0A8h], rax
0x1401c70b3  test    rax, rax
0x1401c70b6  jnz     short loc_1401C70E5
0x1401c70b8  mov     r8, 0FFFFFFFFC0000017h
0x1401c70bf  lea     ecx, [rax+3]
0x1401c70c2  mov     rdx, rsi
0x1401c70c5  call    cs:__imp_WdLogSingleEntry2
0x1401c70cc  nop     dword ptr [rax+rax+00h]
0x1401c70d1  mov     cs:WdLogGlobalForLineNumber, 1B5Dh
0x1401c70db  mov     eax, 0C0000017h
0x1401c70e0  jmp     loc_1401C98C9
0x1401c70e5  mov     rcx, rax; Resource
0x1401c70e8  call    cs:__imp_ExInitializeResourceLite
0x1401c70ef  nop     dword ptr [rax+rax+00h]
0x1401c70f4  movsxd  rbx, eax
0x1401c70f7  test    eax, eax
0x1401c70f9  jns     short loc_1401C7123
0x1401c70fb  mov     r8, rbx
0x1401c70fe  mov     rdx, rsi
0x1401c7101  mov     ecx, 3
0x1401c7106  call    cs:__imp_WdLogSingleEntry2
0x1401c710d  nop     dword ptr [rax+rax+00h]
0x1401c7112  mov     cs:WdLogGlobalForLineNumber, 1B68h
0x1401c711c  mov     eax, ebx
0x1401c711e  jmp     loc_1401C98C9
0x1401c7123  mov     rcx, rdi
0x1401c7126  mov     [rsi+0D8h], rdi
0x1401c712d  call    DpiGetSysMmAdapterFromDevice
0x1401c7132  mov     rcx, rdi; DeviceObject
0x1401c7135  mov     [rsi+0E0h], rax
0x1401c713c  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x1401c7143  nop     dword ptr [rax+rax+00h]
0x1401c7148  mov     rcx, rax; Object
0x1401c714b  mov     [rsi+0E8h], rax
0x1401c7152  call    cs:__imp_ObfDereferenceObject
0x1401c7159  nop     dword ptr [rax+rax+00h]
0x1401c715e  lea     rcx, [rsi+1314h]; Luid
0x1401c7165  call    cs:__imp_ZwAllocateLocallyUniqueId
0x1401c716c  nop     dword ptr [rax+rax+00h]
0x1401c7171  mov     ebx, eax
0x1401c7173  test    eax, eax
0x1401c7175  jns     short loc_1401C71C7
0x1401c7177  mov     ecx, 6
0x1401c717c  call    cs:__imp_WdLogSingleEntry0
0x1401c7183  nop     dword ptr [rax+rax+00h]
0x1401c7188  mov     eax, 1B7Dh
0x1401c718d  lea     r9, aZwallocateloca; "ZwAllocateLocallyUniqueId failed"
0x1401c7194  mov     r8d, r13d
0x1401c7197  mov     edx, 40001h
0x1401c719c  mov     [rsp+180h+var_140], r15
0x1401c71a1  xor     ecx, ecx
0x1401c71a3  mov     [rsp+180h+var_148], r15
0x1401c71a8  mov     [rsp+180h+var_150], r15
0x1401c71ad  mov     [rsp+180h+var_158], r15
0x1401c71b2  mov     [rsp+180h+var_160], rax
0x1401c71b7  mov     cs:WdLogGlobalForLineNumber, eax
0x1401c71bd  call    DxgkLogInternalTriageEvent
0x1401c71c2  jmp     loc_1401C711C
0x1401c71c7  mov     edx, 4B677844h
0x1401c71cc  mov     r8d, 40h ; '@'
0x1401c71d2  mov     rcx, r14
0x1401c71d5  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401c71da  mov     [rsi+118h], rax
0x1401c71e1  test    rax, rax
0x1401c71e4  jnz     short loc_1401C720E
0x1401c71e6  mov     r8, 0FFFFFFFFC0000017h
0x1401c71ed  lea     ecx, [rax+3]
0x1401c71f0  mov     rdx, rsi
0x1401c71f3  call    cs:__imp_WdLogSingleEntry2
0x1401c71fa  nop     dword ptr [rax+rax+00h]
0x1401c71ff  mov     cs:WdLogGlobalForLineNumber, 1B8Ah
0x1401c7209  jmp     loc_1401C70DB
0x1401c720e  mov     rcx, rax; Resource
0x1401c7211  call    cs:__imp_ExInitializeResourceLite
0x1401c7218  nop     dword ptr [rax+rax+00h]
0x1401c721d  movsxd  rbx, eax
0x1401c7220  test    eax, eax
0x1401c7222  jns     short loc_1401C724A
0x1401c7224  mov     r8, rbx
0x1401c7227  mov     rdx, rsi
0x1401c722a  mov     ecx, 3
0x1401c722f  call    cs:__imp_WdLogSingleEntry2
0x1401c7236  nop     dword ptr [rax+rax+00h]
0x1401c723b  mov     cs:WdLogGlobalForLineNumber, 1B95h
0x1401c7245  jmp     loc_1401C711C
0x1401c724a  lock inc qword ptr [rsi+18h]
0x1401c724f  mov     qword ptr [rsi+28h], 0FFFFFFFFFFFFFFFFh
0x1401c7257  mov     rax, [rdi+40h]
0x1401c725b  mov     [rbp+80h+var_100], r15
0x1401c725f  cmp     [rax+1E1h], r15b
0x1401c7266  jz      short loc_1401C72D7
0x1401c7268  lea     rdx, [rbp+80h+var_100]; struct DRIVER_WORKAROUNDS *
0x1401c726c  mov     rcx, rsi; this
0x1401c726f  call    ?InitializeParavirtualizedAdapter@DXGADAPTER@@QEAAJPEAUDRIVER_WORKAROUNDS@@@Z; DXGADAPTER::InitializeParavirtualizedAdapter(DRIVER_WORKAROUNDS *)
0x1401c7274  xor     r13d, r13d
0x1401c7277  movsxd  r15, eax
0x1401c727a  test    eax, eax
0x1401c727c  jns     loc_1401C7328
0x1401c7282  mov     rdx, r15
0x1401c7285  lea     ecx, [r13+2]
0x1401c7289  call    cs:__imp_WdLogSingleEntry1
0x1401c7290  nop     dword ptr [rax+rax+00h]
0x1401c7295  mov     [rsp+180h+var_140], r13
0x1401c729a  lea     r9, aInitializepara; "InitializeParavirtualizedAdapter failed"...
0x1401c72a1  mov     [rsp+180h+var_148], r13
0x1401c72a6  mov     [rsp+180h+var_150], r13
0x1401c72ab  mov     [rsp+180h+var_158], r13
0x1401c72b0  mov     cs:WdLogGlobalForLineNumber, 1BACh
0x1401c72ba  or      r8d, 0FFFFFFFFh
0x1401c72be  mov     [rsp+180h+var_160], r15
0x1401c72c3  mov     edx, 40000h
0x1401c72c8  xor     ecx, ecx
0x1401c72ca  call    DxgkLogInternalTriageEvent
0x1401c72cf  mov     eax, r15d
0x1401c72d2  jmp     loc_1401C98C9
0x1401c72d7  lea     r9, [rsi+970h]
0x1401c72de  mov     [rsi+779h], r15b
0x1401c72e5  lea     r8, [rsi+120h]; void *
0x1401c72ec  mov     rcx, rdi; int
0x1401c72ef  lea     rdx, [rsi+750h]; void *
0x1401c72f6  call    DpiGetAdapterInfo
0x1401c72fb  movsxd  rbx, eax
0x1401c72fe  test    eax, eax
0x1401c7300  jns     short loc_1401C732F
0x1401c7302  mov     r8, rbx
0x1401c7305  mov     rdx, rsi
0x1401c7308  mov     ecx, 3
0x1401c730d  call    cs:__imp_WdLogSingleEntry2
0x1401c7314  nop     dword ptr [rax+rax+00h]
0x1401c7319  mov     cs:WdLogGlobalForLineNumber, 1BBDh
0x1401c7323  jmp     loc_1401C711C
0x1401c7328  xor     r15d, r15d
0x1401c732b  or      r13d, 0FFFFFFFFh
0x1401c732f  mov     rcx, [rsi+0D8h]
0x1401c7336  mov     rdx, rsi
0x1401c7339  call    DpiFdoSetFeatureDatabaseDxgAdapter
0x1401c733e  xor     eax, eax
0x1401c7340  xorps   xmm0, xmm0
0x1401c7343  mov     qword ptr [rbp+80h+var_50], rax
0x1401c7347  mov     rax, [rsi+9C0h]
0x1401c734e  movups  [rbp+80h+var_60], xmm0
0x1401c7352  test    rax, rax
0x1401c7355  jz      short loc_1401C737F
0x1401c7357  mov     rcx, [rsi+978h]
0x1401c735e  lea     rdx, [rbp+80h+var_60]
0x1401c7362  call    _guard_dispatch_icall
0x1401c7367  test    eax, eax
0x1401c7369  js      short loc_1401C737F
0x1401c736b  mov     rax, qword ptr [rbp+80h+var_60+8]
0x1401c736f  mov     [rsi+135Ch], rax
0x1401c7376  mov     eax, [rbp+80h+var_50]
0x1401c7379  mov     [rsi+1364h], eax
0x1401c737f  xor     r9d, r9d; unsigned __int64 *
0x1401c7382  lea     r8, [rbp+80h+var_50]; unsigned int *
0x1401c7386  mov     rcx, rsi; this
0x1401c7389  call    ?IsAdapterSessionized@DXGADAPTER@@QEBA_NPEAU_LUID@@PEAIPEA_K@Z; DXGADAPTER::IsAdapterSessionized(_LUID *,uint *,unsigned __int64 *)
0x1401c738e  mov     [rsp+180h+var_12C], al
0x1401c7392  mov     bl, al
0x1401c7394  test    al, al
0x1401c7396  jz      loc_1401C7427
0x1401c739c  mov     rcx, [rsi+10h]
0x1401c73a0  mov     edx, [rbp+80h+var_50]; unsigned int
0x1401c73a3  mov     rcx, [rcx+3D8h]; this
0x1401c73aa  call    ?GetSessionDataForSpecifiedSession@DXGSESSIONMGR@@QEAAPEAVDXGSESSIONDATA@@K@Z; DXGSESSIONMGR::GetSessionDataForSpecifiedSession(ulong)
0x1401c73af  test    rax, rax
0x1401c73b2  jz      short loc_1401C73C7
0x1401c73b4  mov     rcx, rax; this
0x1401c73b7  call    ?AcquireSessionAdapterOrdinal@DXGSESSIONDATA@@QEAAKXZ; DXGSESSIONDATA::AcquireSessionAdapterOrdinal(void)
0x1401c73bc  mov     [rsi+0F4h], eax
0x1401c73c2  cmp     eax, r13d
0x1401c73c5  jnz     short loc_1401C7427
0x1401c73c7  mov     edx, [rbp+80h+var_50]
0x1401c73ca  mov     ecx, 2
0x1401c73cf  mov     r8, 0FFFFFFFFC0000017h
0x1401c73d6  call    cs:__imp_WdLogSingleEntry2
0x1401c73dd  nop     dword ptr [rax+rax+00h]
0x1401c73e2  mov     eax, [rbp+80h+var_50]
0x1401c73e5  lea     r9, aExceededTheMax; "Exceeded the maximum number of sessioni"...
0x1401c73ec  mov     [rsp+180h+var_140], r15
0x1401c73f1  mov     r8d, r13d
0x1401c73f4  mov     [rsp+180h+var_148], r15
0x1401c73f9  mov     [rsp+180h+var_150], r15
0x1401c73fe  mov     [rsp+180h+var_158], 0FFFFFFFFC0000017h
0x1401c7407  mov     cs:WdLogGlobalForLineNumber, 1BDEh
0x1401c7411  mov     edx, 40000h
0x1401c7416  xor     ecx, ecx
0x1401c7418  mov     [rsp+180h+var_160], rax
0x1401c741d  call    DxgkLogInternalTriageEvent
0x1401c7422  jmp     loc_1401C70DB
0x1401c7427  mov     rcx, [rsi+10h]; this
0x1401c742b  mov     dl, bl; unsigned __int8
0x1401c742d  call    ?AcquireAdapterOrdinal@DXGGLOBAL@@QEAAKE@Z; DXGGLOBAL::AcquireAdapterOrdinal(uchar)
0x1401c7432  mov     [rsi+0F0h], eax
0x1401c7438  cmp     eax, r13d
0x1401c743b  jz      loc_1401C70DB
0x1401c7441  test    dword ptr [rsi+1BCh], 200h
0x1401c744b  jz      short loc_1401C7459
0x1401c744d  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401c7452  mov     byte ptr [rax+4A700h], 1
0x1401c7459  mov     eax, [rsi+1BCh]
0x1401c745f  test    al, 8
0x1401c7461  jz      short loc_1401C74B2
0x1401c7463  test    al, 10h
0x1401c7465  jz      short loc_1401C74B2
0x1401c7467  mov     ecx, 1
0x1401c746c  call    cs:__imp_WdLogSingleEntry0
0x1401c7473  nop     dword ptr [rax+rax+00h]
0x1401c7478  mov     [rsp+180h+var_140], r15
0x1401c747d  lea     r9, aIssoftgpuIswar; "!(IsSoftGPU() && IsWarpAdapter())"
0x1401c7484  mov     [rsp+180h+var_148], r15
0x1401c7489  mov     eax, 1BF6h
0x1401c748e  mov     [rsp+180h+var_150], r15
0x1401c7493  mov     r8d, r13d
0x1401c7496  mov     [rsp+180h+var_158], r15; void *
0x1401c749b  mov     edx, 40002h
0x1401c74a0  xor     ecx, ecx
0x1401c74a2  mov     [rsp+180h+var_160], rax
0x1401c74a7  mov     cs:WdLogGlobalForLineNumber, eax
0x1401c74ad  call    DxgkLogInternalTriageEvent
0x1401c74b2  cmp     [rsi+1C8h], r15
0x1401c74b9  jnz     short loc_1401C7510
0x1401c74bb  mov     ecx, 2
0x1401c74c0  call    cs:__imp_WdLogSingleEntry0
0x1401c74c7  nop     dword ptr [rax+rax+00h]
0x1401c74cc  mov     [rsp+180h+var_140], r15
0x1401c74d1  lea     r9, aMiniportDidNot_2; "Miniport did not provide required DDIs"
0x1401c74d8  mov     [rsp+180h+var_148], r15
0x1401c74dd  mov     eax, 1BFDh
0x1401c74e2  mov     [rsp+180h+var_150], r15
0x1401c74e7  mov     r8d, r13d
0x1401c74ea  mov     [rsp+180h+var_158], r15
0x1401c74ef  mov     [rsp+180h+var_160], rax
0x1401c74f4  mov     cs:WdLogGlobalForLineNumber, eax
0x1401c74fa  mov     edx, 40000h
0x1401c74ff  xor     ecx, ecx
0x1401c7501  call    DxgkLogInternalTriageEvent
0x1401c7506  mov     eax, 0C0000059h
0x1401c750b  jmp     loc_1401C98C9
0x1401c7510  cmp     [rsi+250h], r15
0x1401c7517  jnz     short loc_1401C7527
0x1401c7519  lea     rax, ?DefaultDdiEscape@DXGADAPTER@@CAJQEAXPEBU_DXGKARG_ESCAPE@@@Z; DXGADAPTER::DefaultDdiEscape(void * const,_DXGKARG_ESCAPE const *)
0x1401c7520  mov     [rsi+250h], rax
0x1401c7527  cmp     [rsi+438h], r15
0x1401c752e  jnz     short loc_1401C753E
0x1401c7530  lea     rax, W32kStub_GreSfmOpenTokenEvent
0x1401c7537  mov     [rsi+438h], rax
0x1401c753e  lea     rbx, [rsi+8B0h]
0x1401c7545  mov     rcx, rsi; this
0x1401c7548  mov     [rsp+180h+var_160], rbx; void *
0x1401c754d  call    ?CallDriverQueryInterface@DXGADAPTER@@QEAAJPEBU_GUID@@GGPEAX1@Z; DXGADAPTER::CallDriverQueryInterface(_GUID const *,ushort,ushort,void *,void *)
0x1401c7552  movsxd  r14, eax
  ... truncated ...
```
