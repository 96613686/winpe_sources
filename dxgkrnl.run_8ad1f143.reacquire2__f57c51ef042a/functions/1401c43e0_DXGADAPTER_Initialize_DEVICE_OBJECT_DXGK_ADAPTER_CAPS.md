# DXGADAPTER::Initialize(_DEVICE_OBJECT *,_DXGK_ADAPTER_CAPS *)

- ea: `0x1401c43e0`
- end: `0x1401c6cf0`
- name: `?Initialize@DXGADAPTER@@QEAAJPEAU_DEVICE_OBJECT@@PEAU_DXGK_ADAPTER_CAPS@@@Z`
- size: `10512`
- prototype: `__int64 __fastcall(DXGADAPTER *__hidden this, PDEVICE_OBJECT DeviceObject, struct _DXGK_ADAPTER_CAPS *)`
- caller_count: `1`
- callee_count: `51`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14018e1f4`

## callees

- `0x140009030`
- `0x140012380`
- `0x1400144ec`
- `0x1400150d0`
- `0x14001b890`
- `0x14002e110`
- `0x14002fdc0`
- `0x14003bab8`
- `0x14003e944`
- `0x14003f79c`
- `0x14003f7d0`
- `0x140047eb4`
- `0x14004bd5c`
- `0x140050284`
- `0x140067a88`
- `0x140068378`
- `0x1400683d0`
- `0x1400761a4`
- `0x1400805f4`
- `0x140081620`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x14019208c`
- `0x140192114`
- `0x1401c43e0`
- `0x1401cca50`
- `0x1401d0e20`
- `0x1401e5f4c`
- `0x1401e63a4`
- `0x1401e7c40`
- `0x1401e7dc0`
- `0x1401e7f54`
- `0x1401e8388`
- `0x1401e890c`
- `0x1401e9040`
- `0x1401eb538`
- `0x1401ec820`
- `0x1401ecc44`
- `0x1401ee6a4`
- `0x1401ef258`
- `0x1401f7f88`
- `0x14023be70`
- `0x14023c0ec`
- `0x14023c2a4`
- `0x14023ff54`
- `0x14026163c`
- `0x14029aca8`
- `0x14035f558`
- `0x140363b90`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401c6b5b`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401c6b5b`
- `ntoskrnl!ExInitializeResourceLite` at `0x1401c44e8`
- `ntoskrnl!ExInitializeResourceLite` at `0x1401c4611`
- `ntoskrnl!ExInitializeResourceLite` at `0x1401c44e8`
- `ntoskrnl!ExInitializeResourceLite` at `0x1401c4611`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1401c453c`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1401c453c`
- `ntoskrnl!ObfDereferenceObject` at `0x1401c4552`
- `ntoskrnl!ObfDereferenceObject` at `0x1401c4552`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x1401c4565`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x1401c4565`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401c4418`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401c4418`
- `watchdog!WdLogSingleEntry2` at `0x1401c44c5`
- `watchdog!WdLogSingleEntry2` at `0x1401c4506`
- `watchdog!WdLogSingleEntry2` at `0x1401c45f3`
- `watchdog!WdLogSingleEntry2` at `0x1401c462f`
- `watchdog!WdLogSingleEntry2` at `0x1401c470d`
- `watchdog!WdLogSingleEntry2` at `0x1401c47d6`
- `watchdog!WdLogSingleEntry2` at `0x1401c6019`
- `watchdog!WdLogSingleEntry2` at `0x1401c606b`
- `watchdog!WdLogSingleEntry2` at `0x1401c643f`
- `watchdog!WdLogSingleEntry2` at `0x1401c64fa`
- `watchdog!WdLogSingleEntry2` at `0x1401c6601`
- `watchdog!WdLogSingleEntry2` at `0x1401c6657`
- `watchdog!WdLogSingleEntry2` at `0x1401c68df`
- `watchdog!WdLogSingleEntry2` at `0x1401c697b`
- `watchdog!WdLogSingleEntry2` at `0x1401c44c5`
- `watchdog!WdLogSingleEntry2` at `0x1401c4506`
- `watchdog!WdLogSingleEntry2` at `0x1401c45f3`
- `watchdog!WdLogSingleEntry2` at `0x1401c462f`
- `watchdog!WdLogSingleEntry2` at `0x1401c470d`
- `watchdog!WdLogSingleEntry2` at `0x1401c47d6`
- `watchdog!WdLogSingleEntry2` at `0x1401c6019`
- `watchdog!WdLogSingleEntry2` at `0x1401c606b`
- `watchdog!WdLogSingleEntry2` at `0x1401c643f`
- `watchdog!WdLogSingleEntry2` at `0x1401c64fa`
- `watchdog!WdLogSingleEntry2` at `0x1401c6601`
- `watchdog!WdLogSingleEntry2` at `0x1401c6657`
- `watchdog!WdLogSingleEntry2` at `0x1401c68df`
- `watchdog!WdLogSingleEntry2` at `0x1401c697b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401c495f`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401c6258`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401c495f`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401c6258`
- `watchdog!WdLogSingleEntry3` at `0x1401c51a2`
- `watchdog!WdLogSingleEntry3` at `0x1401c537e`
- `watchdog!WdLogSingleEntry3` at `0x1401c51a2`
- `watchdog!WdLogSingleEntry3` at `0x1401c537e`
- `watchdog!WdLogSingleEntry0` at `0x1401c4433`
- `watchdog!WdLogSingleEntry0` at `0x1401c457c`
- `watchdog!WdLogSingleEntry0` at `0x1401c486c`
- `watchdog!WdLogSingleEntry0` at `0x1401c48c0`
- `watchdog!WdLogSingleEntry0` at `0x1401c4a0d`
- `watchdog!WdLogSingleEntry0` at `0x1401c4bed`
- `watchdog!WdLogSingleEntry0` at `0x1401c4c72`
- `watchdog!WdLogSingleEntry0` at `0x1401c4dcd`
- `watchdog!WdLogSingleEntry0` at `0x1401c55ae`
- `watchdog!WdLogSingleEntry0` at `0x1401c560a`
- `watchdog!WdLogSingleEntry0` at `0x1401c5703`
- `watchdog!WdLogSingleEntry0` at `0x1401c5869`
- `watchdog!WdLogSingleEntry0` at `0x1401c58b1`
- `watchdog!WdLogSingleEntry0` at `0x1401c58fe`
- `watchdog!WdLogSingleEntry0` at `0x1401c5939`
- `watchdog!WdLogSingleEntry0` at `0x1401c5c39`
- `watchdog!WdLogSingleEntry0` at `0x1401c5c81`
- `watchdog!WdLogSingleEntry0` at `0x1401c5ccf`
- `watchdog!WdLogSingleEntry0` at `0x1401c5d49`
- `watchdog!WdLogSingleEntry0` at `0x1401c5da7`
- `watchdog!WdLogSingleEntry0` at `0x1401c5df0`
- `watchdog!WdLogSingleEntry0` at `0x1401c5e3d`
- `watchdog!WdLogSingleEntry0` at `0x1401c5e81`
- `watchdog!WdLogSingleEntry0` at `0x1401c5ed9`
- `watchdog!WdLogSingleEntry0` at `0x1401c5ef7`
- `watchdog!WdLogSingleEntry0` at `0x1401c6331`
- `watchdog!WdLogSingleEntry0` at `0x1401c63a8`
- `watchdog!WdLogSingleEntry0` at `0x1401c64aa`
- `watchdog!WdLogSingleEntry0` at `0x1401c6545`
- `watchdog!WdLogSingleEntry0` at `0x1401c65b1`
- `watchdog!WdLogSingleEntry0` at `0x1401c67bd`
- `watchdog!WdLogSingleEntry0` at `0x1401c6804`
- `watchdog!WdLogSingleEntry0` at `0x1401c6a4e`
- `watchdog!WdLogSingleEntry0` at `0x1401c6a7d`
- `watchdog!WdLogSingleEntry0` at `0x1401c6acc`
- `watchdog!WdLogSingleEntry0` at `0x1401c6b0c`
- `watchdog!WdLogSingleEntry0` at `0x1401c6b6e`
- `watchdog!WdLogSingleEntry0` at `0x1401c4433`
- `watchdog!WdLogSingleEntry0` at `0x1401c457c`
- `watchdog!WdLogSingleEntry0` at `0x1401c486c`
- `watchdog!WdLogSingleEntry0` at `0x1401c48c0`
- `watchdog!WdLogSingleEntry0` at `0x1401c4a0d`
- `watchdog!WdLogSingleEntry0` at `0x1401c4bed`
- `watchdog!WdLogSingleEntry0` at `0x1401c4c72`
- `watchdog!WdLogSingleEntry0` at `0x1401c4dcd`
- `watchdog!WdLogSingleEntry0` at `0x1401c55ae`
- `watchdog!WdLogSingleEntry0` at `0x1401c560a`
- `watchdog!WdLogSingleEntry0` at `0x1401c5703`
- `watchdog!WdLogSingleEntry0` at `0x1401c5869`
- `watchdog!WdLogSingleEntry0` at `0x1401c58b1`
- `watchdog!WdLogSingleEntry0` at `0x1401c58fe`
- `watchdog!WdLogSingleEntry0` at `0x1401c5939`
- `watchdog!WdLogSingleEntry0` at `0x1401c5c39`
- `watchdog!WdLogSingleEntry0` at `0x1401c5c81`
- `watchdog!WdLogSingleEntry0` at `0x1401c5ccf`
- `watchdog!WdLogSingleEntry0` at `0x1401c5d49`
- `watchdog!WdLogSingleEntry0` at `0x1401c5da7`
- `watchdog!WdLogSingleEntry0` at `0x1401c5df0`
- `watchdog!WdLogSingleEntry0` at `0x1401c5e3d`
- `watchdog!WdLogSingleEntry0` at `0x1401c5e81`
- `watchdog!WdLogSingleEntry0` at `0x1401c5ed9`
- `watchdog!WdLogSingleEntry0` at `0x1401c5ef7`
- `watchdog!WdLogSingleEntry0` at `0x1401c6331`
- `watchdog!WdLogSingleEntry0` at `0x1401c63a8`
- `watchdog!WdLogSingleEntry0` at `0x1401c64aa`
- `watchdog!WdLogSingleEntry0` at `0x1401c6545`
- `watchdog!WdLogSingleEntry0` at `0x1401c65b1`
- `watchdog!WdLogSingleEntry0` at `0x1401c67bd`
- `watchdog!WdLogSingleEntry0` at `0x1401c6804`
- `watchdog!WdLogSingleEntry0` at `0x1401c6a4e`
- `watchdog!WdLogSingleEntry0` at `0x1401c6a7d`
- `watchdog!WdLogSingleEntry0` at `0x1401c6acc`
- `watchdog!WdLogSingleEntry0` at `0x1401c6b0c`
- `watchdog!WdLogSingleEntry0` at `0x1401c6b6e`
- `watchdog!WdLogSingleEntry1` at `0x1401c4689`
- `watchdog!WdLogSingleEntry1` at `0x1401c4ab0`
- `watchdog!WdLogSingleEntry1` at `0x1401c4b0f`
- `watchdog!WdLogSingleEntry1` at `0x1401c5159`
- `watchdog!WdLogSingleEntry1` at `0x1401c51f1`
- `watchdog!WdLogSingleEntry1` at `0x1401c5234`
- `watchdog!WdLogSingleEntry1` at `0x1401c5279`
- `watchdog!WdLogSingleEntry1` at `0x1401c53dd`
- `watchdog!WdLogSingleEntry1` at `0x1401c541d`
- `watchdog!WdLogSingleEntry1` at `0x1401c545f`
- `watchdog!WdLogSingleEntry1` at `0x1401c57f0`
- `watchdog!WdLogSingleEntry1` at `0x1401c5ab8`
- `watchdog!WdLogSingleEntry1` at `0x1401c5b33`
- `watchdog!WdLogSingleEntry1` at `0x1401c5b83`
- `watchdog!WdLogSingleEntry1` at `0x1401c5bd6`
- `watchdog!WdLogSingleEntry1` at `0x1401c60fd`
- `watchdog!WdLogSingleEntry1` at `0x1401c63f7`
- `watchdog!WdLogSingleEntry1` at `0x1401c66b4`
- `watchdog!WdLogSingleEntry1` at `0x1401c4689`
- `watchdog!WdLogSingleEntry1` at `0x1401c4ab0`
- `watchdog!WdLogSingleEntry1` at `0x1401c4b0f`
- `watchdog!WdLogSingleEntry1` at `0x1401c5159`
- `watchdog!WdLogSingleEntry1` at `0x1401c51f1`
- `watchdog!WdLogSingleEntry1` at `0x1401c5234`
- `watchdog!WdLogSingleEntry1` at `0x1401c5279`
- `watchdog!WdLogSingleEntry1` at `0x1401c53dd`
- `watchdog!WdLogSingleEntry1` at `0x1401c541d`
- `watchdog!WdLogSingleEntry1` at `0x1401c545f`
- `watchdog!WdLogSingleEntry1` at `0x1401c57f0`
- `watchdog!WdLogSingleEntry1` at `0x1401c5ab8`
- `watchdog!WdLogSingleEntry1` at `0x1401c5b33`
- `watchdog!WdLogSingleEntry1` at `0x1401c5b83`
- `watchdog!WdLogSingleEntry1` at `0x1401c5bd6`
- `watchdog!WdLogSingleEntry1` at `0x1401c60fd`
- `watchdog!WdLogSingleEntry1` at `0x1401c63f7`
- `watchdog!WdLogSingleEntry1` at `0x1401c66b4`

## string_xrefs

- `0x1401c4c80`: `MiscCaps.ComputeOnly is not set, but the device belongs to the ComputeAccelerator class`
- `0x1401c4bfb`: `UMD name is missing and device is not compute only`
- `0x1401c51b7`: `Adapter 0x%I64x: VirtualCopyEngineSupported but node index is invalid (VirtualCopyIndex:%u, NumExecutionNodes:%u)`
- `0x1401c5176`: `Adapter 0x%I64x: IoMmuSecureModeRequired must be set for a device exposing a virtual copy engine`
- `0x1401c5c92`: `Driver reports SupportKernelModeCommandBuffer cap but does not fill in the pfnRenderKm DDI.`
- `0x1401c5ce0`: `Driver reports SupportRuntimePowerManagement cap but does not fill in the pfnSetPowerComponentFState or pfnPowerRuntimeControlRequest DDI.`
- `0x1401c5d5a`: `Driver reports SupportMultiPlaneOverlay cap but it is not compiled with expected header files.`
- `0x1401c6517`: `Failed to create ADAPTER_RENDER on adapter 0x%I64x (Status = 0x%I64x).`
- `0x1401c6612`: `Failed to create ADAPTER_DISPLAY on adapter 0x%I64x (Status = 0x%I64x).`
- `0x1401c67ce`: `Driver is compiled against DXGKDDI_INTERFACE_VERSION_WDDM2_0_M2_2_1 or greater, but does not fill in the pfnCalibrateGpuClock or pfnSetStablePowerState DDI.`

## pseudocode

```c
__int64 __fastcall DXGADAPTER::Initialize(DXGADAPTER *this, PDEVICE_OBJECT DeviceObject, struct _DXGK_ADAPTER_CAPS *a3)
{
  struct _DXGK_ADAPTER_CAPS *v3; // r12
  struct _ERESOURCE *v6; // rax
  __int64 result; // rax
  int LocallyUniqueId; // ebx
  PDEVICE_OBJECT DeviceAttachmentBaseRef; // rax
  __int64 v10; // rax
  const wchar_t *v11; // r9
  int v12; // edx
  struct _ERESOURCE *v13; // rax
  _BYTE *DeviceExtension; // rax
  int v15; // eax
  __int64 v16; // r15
  struct _LUID *v17; // rdx
  int (__fastcall *v18)(_QWORD, __int128 *); // rax
  unsigned __int8 v19; // bl
  DXGSESSIONDATA *SessionDataForSpecifiedSession; // rax
  unsigned int v21; // eax
  __int64 v22; // rax
  const wchar_t *v23; // r9
  unsigned int v24; // eax
  const struct _GUID *v25; // rdx
  unsigned __int16 v26; // r8
  unsigned __int16 v27; // r9
  int v28; // eax
  const wchar_t *v29; // r9
  unsigned __int8 v30; // dl
  __int64 v31; // r14
  __int64 v32; // rax
  unsigned int v33; // r13d
  unsigned __int8 v34; // r8
  __int64 v35; // rax
  const wchar_t *v36; // r9
  int v37; // eax
  int v38; // ecx
  int v39; // eax
  __int64 v40; // r15
  unsigned int v41; // edx
  __int64 v42; // rcx
  int v43; // eax
  unsigned int v44; // edx
  unsigned int v45; // ebx
  char v46; // al
  int v47; // eax
  unsigned int v48; // edi
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // r8
  unsigned int v52; // edx
  unsigned int v53; // eax
  unsigned __int16 *v54; // rbx
  void (__fastcall *v55)(_QWORD, unsigned int *); // rax
  void (__fastcall *v56)(__int64, _QWORD, unsigned int *); // rax
  __int64 v57; // rcx
  DXGGLOBAL *Global; // rax
  __int64 v59; // rcx
  __int64 v60; // rbx
  unsigned int v61; // edx
  __int64 v62; // r8
  __int64 v63; // rcx
  __int64 v64; // rdi
  __int64 v65; // rbx
  __int64 v66; // rdi
  __int64 v67; // rbx
  char v68; // bl
  unsigned int i; // edx
  int v70; // eax
  __int64 RenderCore; // rdi
  unsigned int v72; // edx
  unsigned __int64 v73; // r8
  const wchar_t *v74; // r9
  unsigned int v75; // r12d
  unsigned int v76; // r15d
  __int64 v77; // rdx
  __int64 v78; // r13
  __int16 v79; // ax
  int v80; // ecx
  int v81; // ebx
  int v82; // edi
  __int64 v83; // rbx
  unsigned __int8 IsGpuVaIoMmuGlobalSupported; // al
  int v85; // eax
  char v86; // al
  int v87; // eax
  __int64 v88; // rax
  unsigned int v89; // ecx
  int v90; // eax
  char v91; // cl
  char v92; // dl
  char v93; // al
  char v94; // dl
  char v95; // r8
  char v96; // cl
  int v97; // eax
  char v98; // al
  char v99; // dl
  unsigned __int8 v100; // dl
  char v101; // cl
  unsigned int v102; // eax
  int v103; // ecx
  __int64 v104; // rax
  struct DXGGLOBAL *v105; // rax
  struct DXGGLOBAL *v106; // rax
  struct DXGGLOBAL *v107; // rax
  char v108; // r8
  unsigned int v109; // ecx
  unsigned int v110; // edx
  DXGGLOBAL *v111; // rax
  int v112; // eax
  int v113; // eax
  int v114; // eax
  char v115; // cl
  struct DXGGLOBAL *v116; // rdi
  _DWORD *v117; // rbx
  int v118; // eax
  __int64 v119; // rax
  _QWORD *v120; // rbx
  int DisplayCore; // eax
  char v122; // cl
  char v123; // dl
  __int64 v124; // rax
  int v125; // eax
  char v126; // al
  __int64 v127; // rdx
  DXGADAPTER *v128; // rcx
  int v129; // eax
  __int64 v130; // rcx
  bool v131; // cf
  __int64 v132; // rdx
  __int64 v133; // r8
  int v134; // eax
  DXGGLOBAL *v135; // rax
  int v136; // eax
  __int64 v137; // rax
  int v138; // eax
  __int64 v139; // r14
  __int64 v140; // rbx
  struct DXGGLOBAL *v141; // rax
  int v142; // eax
  struct DXGGLOBAL *v143; // rax
  __int64 v144; // rdx
  struct DXGGLOBAL *v145; // r14
  DXGGLOBAL *v146; // rcx
  unsigned int v147; // ebx
  struct DXGGLOBAL *v148; // rax
  struct DXGGLOBAL *v149; // rax
  __int64 v150; // [rsp+20h] [rbp-E0h]
  void *v151; // [rsp+28h] [rbp-D8h]
  __int64 v152; // [rsp+28h] [rbp-D8h]
  __int64 v153; // [rsp+28h] [rbp-D8h]
  unsigned int v154; // [rsp+50h] [rbp-B0h] BYREF
  bool IsAdapterSessionized; // [rsp+54h] [rbp-ACh]
  unsigned int v156; // [rsp+58h] [rbp-A8h] BYREF
  int v157; // [rsp+5Ch] [rbp-A4h] BYREF
  __int128 v158; // [rsp+60h] [rbp-A0h] BYREF
  int v159; // [rsp+70h] [rbp-90h] BYREF
  __int64 v160; // [rsp+78h] [rbp-88h]
  __int64 v161; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v162; // [rsp+88h] [rbp-78h]
  struct _DXGKARG_QUERYADAPTERINFO v163; // [rsp+90h] [rbp-70h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v164; // [rsp+C0h] [rbp-40h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v165; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v166; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v167[2]; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v168[4]; // [rsp+138h] [rbp+38h] BYREF

  v3 = a3;
  *(_QWORD *)&v158 = a3;
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
    WdLogSingleEntry2(3, this);
    WdLogGlobalForLineNumber = 7005;
    return 3221225495LL;
  }
  LocallyUniqueId = ExInitializeResourceLite(v6);
  if ( LocallyUniqueId < 0 )
  {
    WdLogSingleEntry2(3, this);
    WdLogGlobalForLineNumber = 7016;
    return (unsigned int)LocallyUniqueId;
  }
  *((_QWORD *)this + 27) = DeviceObject;
  *((_QWORD *)this + 28) = DpiGetSysMmAdapterFromDevice(DeviceObject);
  DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(DeviceObject);
  *((_QWORD *)this + 29) = DeviceAttachmentBaseRef;
  ObfDereferenceObject(DeviceAttachmentBaseRef);
  LocallyUniqueId = ZwAllocateLocallyUniqueId((PLUID)((char *)this + 4868));
  if ( LocallyUniqueId < 0 )
  {
    WdLogSingleEntry0(6);
    v10 = 7037;
    v11 = L"ZwAllocateLocallyUniqueId failed";
LABEL_12:
    v12 = 262145;
LABEL_13:
    WdLogGlobalForLineNumber = v10;
    DxgkLogInternalTriageEvent(0, v12, -1, (_DWORD)v11, v10, 0, 0, 0, 0);
    return (unsigned int)LocallyUniqueId;
  }
  v13 = (struct _ERESOURCE *)operator new(104, 1265072196, 64);
  *((_QWORD *)this + 35) = v13;
  if ( !v13 )
  {
    WdLogSingleEntry2(3, this);
    WdLogGlobalForLineNumber = 7050;
    return 3221225495LL;
  }
  LocallyUniqueId = ExInitializeResourceLite(v13);
  if ( LocallyUniqueId < 0 )
  {
    WdLogSingleEntry2(3, this);
    WdLogGlobalForLineNumber = 7061;
    return (unsigned int)LocallyUniqueId;
  }
  _InterlockedIncrement64((volatile signed __int64 *)this + 3);
  *((_QWORD *)this + 5) = -1;
  DeviceExtension = DeviceObject->DeviceExtension;
  v161 = 0;
  if ( DeviceExtension[481] )
  {
    v15 = DXGADAPTER::InitializeParavirtualizedAdapter(this, (struct DRIVER_WORKAROUNDS *)&v161);
    v16 = v15;
    if ( v15 < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 7084;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"InitializeParavirtualizedAdapter failed: 0x%I64x",
        v16,
        0,
        0,
        0,
        0);
      return (unsigned int)v16;
    }
  }
  else
  {
    *((_BYTE *)this + 1897) = 0;
    LocallyUniqueId = DpiGetAdapterInfo(
                        (__int64)DeviceObject,
                        (_BYTE *)this + 1856,
                        (char *)this + 288,
                        (_OWORD *)this + 150);
    if ( LocallyUniqueId < 0 )
    {
      WdLogSingleEntry2(3, this);
      WdLogGlobalForLineNumber = 7101;
      return (unsigned int)LocallyUniqueId;
    }
  }
  DpiFdoSetFeatureDatabaseDxgAdapter(*((_QWORD *)this + 27), this);
  *(_QWORD *)v167 = 0;
  v18 = (int (__fastcall *)(_QWORD, __int128 *))*((_QWORD *)this + 310);
  v166 = 0;
  if ( v18 && v18(*((_QWORD *)this + 301), &v166) >= 0 )
  {
    *(_QWORD *)((char *)this + 4940) = *((_QWORD *)&v166 + 1);
    *((_DWORD *)this + 1237) = v167[0];
  }
  IsAdapterSessionized = DXGADAPTER::IsAdapterSessionized(this, v17, v167, 0);
  v19 = IsAdapterSessionized;
  if ( IsAdapterSessionized )
  {
    SessionDataForSpecifiedSession = DXGSESSIONMGR::GetSessionDataForSpecifiedSession(
                                       *(DXGSESSIONMGR **)(*((_QWORD *)this + 2) + 984LL),
                                       v167[0]);
    if ( !SessionDataForSpecifiedSession
      || (v21 = DXGSESSIONDATA::AcquireSessionAdapterOrdinal(SessionDataForSpecifiedSession),
          *((_DWORD *)this + 61) = v21,
          v21 == -1) )
    {
      WdLogSingleEntry2(2, v167[0]);
      v22 = v167[0];
      v23 = L"Exceeded the maximum number of sessionized adapter in session 0x%I64x, returning 0x%I64x.";
      v152 = -1073741801;
      WdLogGlobalForLineNumber = 7134;
LABEL_31:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v23, v22, v152, 0, 0, 0);
      return 3221225495LL;
    }
  }
  v24 = DXGGLOBAL::AcquireAdapterOrdinal(*((DXGGLOBAL **)this + 2), v19);
  *((_DWORD *)this + 60) = v24;
  if ( v24 == -1 )
    return 3221225495LL;
  if ( (*((_DWORD *)this + 111) & 0x200) != 0 )
    *((_BYTE *)DXGGLOBAL::GetGlobal() + 304896) = 1;
  v28 = *((_DWORD *)this + 111);
  if ( (v28 & 8) != 0 && (v28 & 0x10) != 0 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 7158;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"!(IsSoftGPU() && IsWarpAdapter())", 7158, 0, 0, 0, 0);
  }
  if ( !*((_QWORD *)this + 57) )
  {
    WdLogSingleEntry0(2);
    v29 = L"Miniport did not provide required DDIs";
    v153 = 0;
    v150 = 7165;
    WdLogGlobalForLineNumber = 7165;
LABEL_40:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v29, v150, v153, 0, 0, 0);
    return 3221225561LL;
  }
  if ( !*((_QWORD *)this + 74) )
    *((_QWORD *)this + 74) = DXGADAPTER::DefaultDdiEscape;
  if ( !*((_QWORD *)this + 135) )
    *((_QWORD *)this + 135) = W32kStub_GreSfmOpenTokenEvent;
  v31 = (int)DXGADAPTER::CallDriverQueryInterface(this, v25, v26, v27, (char *)this + 2208, v151);
  if ( (int)v31 >= 0 )
  {
    if ( *((_WORD *)this + 1105) >= 4u )
      goto LABEL_49;
  }
  else
  {
    v32 = WdLogNewEntry5_WdTrace();
    *(_QWORD *)(v32 + 24) = this;
    *(_QWORD *)(v32 + 32) = v31;
    WdLogGlobalForLineNumber = 7196;
  }
  memset((char *)this + 2208, 0, 0xB8u);
LABEL_49:
  v33 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 27) + 64LL) + 40LL) + 28LL);
  v162 = v33;
  *((_DWORD *)this + 598) = v33;
  if ( v33 < 0x7000 )
  {
    if ( v33 < 0x6002 )
      goto LABEL_58;
  }
  else
  {
    if ( !*((_DWORD *)this + 492) )
      goto LABEL_58;
    if ( *((_DWORD *)this + 493) )
    {
      v34 = 0;
LABEL_57:
      DXGADAPTER::SetModeBehavior(this, v30, v34);
      goto LABEL_58;
    }
  }
  if ( *((_DWORD *)this + 492) && *((_DWORD *)this + 493) )
  {
    v34 = 1;
    goto LABEL_57;
  }
LABEL_58:
  if ( v33 - 20480 <= 5 )
  {
    WdLogSingleEntry0(2);
    v35 = 7240;
    v36 = L"Cannot load an M1 threshold driver on later builds.";
LABEL_60:
    WdLogGlobalForLineNumber = v35;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v36, v35, 0, 0, 0, 0);
    return 3221225485LL;
  }
  *(_QWORD *)&v163.Type = 1;
  *(_QWORD *)&v163.InputDataSize = 0;
  v163.pOutputData = (char *)this + 2512;
  *(_OWORD *)&v163.OutputDataSize = 0;
  v163.pInputData = 0;
  v163.OutputDataSize = GetDriverCapsSizeFromDdiVersion(v33);
  if ( !v163.OutputDataSize )
    return 3221225485LL;
  v37 = DXGADAPTER::DdiQueryAdapterInfo(this, &v163);
  v16 = v37;
  if ( v37 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 7263;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Miniport failed DdiQueryAdapterInfo(DXGKQAITYPE_DRIVERCAPS) with status 0x%I64x",
      v16,
      0,
      0,
      0,
      0);
    return (unsigned int)v16;
  }
  v38 = *((_DWORD *)this + 712);
  if ( v38 > 9472 )
  {
    if ( *((_DWORD *)DeviceObject->DeviceExtension + 687) <= 0xA00Bu )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 7269;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Miniport returned incorrect WDDMVersion: 0x%I64x",
        *((int *)this + 712),
        0,
        0,
        0,
        0);
      return 3221225485LL;
    }
    goto LABEL_69;
  }
  if ( v38 >= 4864 )
  {
LABEL_69:
    v39 = DxgkConvertWddmVersionToD3DKMTDriverVersion();
    goto LABEL_77;
  }
  if ( *((_QWORD *)this + 104) )
  {
    v39 = 1300;
  }
  else if ( v38 == 4608 )
  {
    v39 = 1200;
  }
  else if ( !*((_QWORD *)this + 100) || (v39 = 1105, (*((_DWORD *)this + 641) & 4) == 0) )
  {
    v39 = 1000;
  }
LABEL_77:
  v40 = 3116;
  v160 = 3116;
  *((_DWORD *)this + 779) = v39;
  v41 = *((_DWORD *)this + 772);
  if ( v39 >= 2600 )
  {
    if ( (v41 & 8) != 0 )
    {
      *((_DWORD *)this + 111) |= 0x80000u;
    }
    else if ( (*((_DWORD *)this + 111) & 0x80000) != 0 && v33 >= 0x11002 )
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
    v41 &= ~8u;
    *((_DWORD *)this + 772) = v41;
  }
  if ( *((_BYTE *)this + 1896) && (((v41 & 4) == 0) & (unsigned __int8)~(unsigned __int8)(v41 >> 3)) != 0 )
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
  v42 = *((_QWORD *)this + 27);
  v156 = 0;
  v43 = DpiReadPnpRegistryValue(v42, L"ACGSupported", &v156, 4, 2);
  v44 = v156;
  if ( v43 < 0 )
    v44 = 0;
  if ( v44 || *((int *)this + 779) >= 2200 )
  {
    v46 = 1;
    v45 = 0;
  }
  else
  {
    v45 = 0;
    v46 = 0;
  }
  *((_BYTE *)this + 212) = v46;
  if ( *((_BYTE *)this + 209) )
  {
    *((_BYTE *)v3 + 1) &= ~1u;
    *(_BYTE *)v3 &= 0x7Bu;
    *((_DWORD *)this + 772) &= 0xFFFFFFEB;
    *((_DWORD *)this + 645) &= 0xFFFFD2FF;
    *((_BYTE *)this + 3052) = 0;
    *((_BYTE *)this + 3080) = 1;
    *((_BYTE *)this + 3054) = 1;
    if ( *((_BYTE *)this + 210) )
      *((_DWORD *)this + 641) &= ~0x100000u;
  }
  else if ( v33 >= 0x5023 )
  {
    if ( g_bCreateParavirtualizedGpu )
    {
      v47 = *((_DWORD *)this + 111);
      if ( (v47 & 4) == 0 && (v47 & 0x10) == 0 && !*(_BYTE *)(*((_QWORD *)DeviceObject->DeviceExtension + 5) + 133LL) )
        *((_DWORD *)this + 645) |= 0x400u;
    }
  }
  v156 = *((_DWORD *)this + 74);
  v48 = v156;
  v49 = 352LL * v156;
  if ( !is_mul_ok(v156, 0x160u) )
    v49 = -1;
  v50 = operator new[](v49, 1265072196, 64);
  *((_QWORD *)this + 388) = v50;
  v51 = v50;
  if ( !v50 )
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
  if ( *((int *)this + 712) >= 0x2000 && v33 >= 0x5005 )
  {
    *((_DWORD *)this + 778) = 0;
    v52 = 0;
    v154 = 0;
    v53 = 0;
    while ( v52 < v48 )
    {
      *(_QWORD *)&v164.Type = 15;
      v54 = (unsigned __int16 *)(v51 + 352LL * v52);
      *(_QWORD *)&v164.InputDataSize = 4;
      v164.pOutputData = v54;
      *(_QWORD *)&v164.Flags.0 = 0;
      HIDWORD(v164.hKmdProcessHandle) = 0;
      v164.pInputData = &v154;
      v164.OutputDataSize = GetPhysicalAdapterCapsSizeFromDdiVersion(v33);
      if ( (int)DXGADAPTER::DdiQueryAdapterInfo(this, &v164) < 0 )
      {
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 7417;
        v68 = 1;
        goto LABEL_144;
      }
      if ( v33 >= 0xC003 )
      {
        if ( (*((_DWORD *)v54 + 4) & 0x20) != 0 )
        {
          if ( *((_DWORD *)v54 + 6) >= (unsigned int)*v54 )
          {
            WdLogSingleEntry3(2, this, *((unsigned int *)v54 + 6), *v54);
            WdLogGlobalForLineNumber = 7435;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Adapter 0x%I64x: VirtualCopyEngineSupported but node index is invalid (VirtualCopyIndex:%u, "
                             "NumExecutionNodes:%u)",
              (__int64)this,
              *((unsigned int *)v54 + 6),
              *v54,
              0,
              0);
            return 3221225485LL;
          }
          if ( (*((_DWORD *)this + 645) & 0x2000) == 0 )
          {
            WdLogSingleEntry1(2);
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
        v55 = (void (__fastcall *)(_QWORD, unsigned int *))*((_QWORD *)this + 221);
        if ( v55 )
        {
          *(_OWORD *)v168 = 0;
          v168[0] = v154;
          v55(*((_QWORD *)this + 36), v168);
          *((_BYTE *)v54 + 50) = v168[1] & 1;
        }
        v56 = (void (__fastcall *)(__int64, _QWORD, unsigned int *))*((_QWORD *)this + 222);
        if ( v56 )
        {
          v57 = *((_QWORD *)this + 36);
          *(_QWORD *)v168 = 0;
          v56(v57, v154, v168);
          *((_QWORD *)v54 + 43) = *(_QWORD *)v168;
        }
      }
      if ( !*((_BYTE *)this + 209) )
      {
        Global = DXGGLOBAL::GetGlobal();
        if ( DXGGLOBAL::GpuVaIoMmuEnabled(Global) )
        {
          v157 = 0;
          v168[0] = 0;
          if ( (unsigned int)Feature_GpuVaIommuFixes__private_IsEnabledDeviceUsageNoInline() )
          {
            v60 = *(_QWORD *)(352LL * v154 + *((_QWORD *)this + 388) + 8);
            if ( (int)DpiReadPnpRegistryValue(v60, L"DxgkGpuVaIommuSupported", &v157, 4, 2) >= 0 )
              *(_DWORD *)(352LL * v154 + *((_QWORD *)this + 388) + 16) = (v157 != 0 ? 0x40 : 0)
                                                                       | *(_DWORD *)(352LL * v154
                                                                                   + *((_QWORD *)this + 388)
                                                                                   + 16)
                                                                       & 0xFFFFFFBF;
            v59 = v60;
          }
          else
          {
            if ( (int)DpiReadPnpRegistryValue(*((_QWORD *)this + 27), L"DxgkGpuVaIommuRequired", &v157, 4, 2) >= 0 )
              *(_DWORD *)(352LL * v154 + *((_QWORD *)this + 388) + 16) = (v157 != 0 ? 0x40 : 0)
                                                                       | *(_DWORD *)(352LL * v154
                                                                                   + *((_QWORD *)this + 388)
                                                                                   + 16)
                                                                       & 0xFFFFFFBF;
            v59 = *((_QWORD *)this + 27);
          }
          if ( (int)DpiReadPnpRegistryValue(v59, L"DxgkGpuVaIommuGlobalSupported", v168, 4, 2) >= 0 )
            *(_DWORD *)(352LL * v154 + *((_QWORD *)this + 388) + 16) = (v168[0] != 0 ? 0x80 : 0)
                                                                     | *(_DWORD *)(352LL * v154
                                                                                 + *((_QWORD *)this + 388)
                                                                                 + 16)
                                                                     & 0xFFFFFF7F;
        }
      }
      v61 = v154;
      v62 = *((_QWORD *)this + 388);
      v63 = 352LL * v154;
      if ( (*(_DWORD *)(v63 + v62 + 16) & 2) != 0 )
      {
        *(_BYTE *)(v63 + v62 + 49) = 1;
        v61 = v154;
      }
      v64 = *((_QWORD *)this + 388);
      v65 = 352LL * v61;
      if ( (*(_DWORD *)(v65 + v64 + 16) & 0x40) != 0 )
      {
        if ( !DXGADAPTER::IsGpuVaIoMmuSupported(this) )
        {
          WdLogSingleEntry1(2);
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
        *(_BYTE *)(v65 + v64 + 49) = 1;
        *(_BYTE *)(352LL * v154 + *((_QWORD *)this + 388) + 48) = 1;
        v61 = v154;
      }
      v66 = *((_QWORD *)this + 388);
      v67 = 352LL * v61;
      if ( (*(_DWORD *)(v67 + v66 + 16) & 0x80u) != 0 )
      {
        if ( !DXGADAPTER::IsGpuVaIoMmuGlobalSupported(this) )
        {
          WdLogSingleEntry1(2);
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
        *(_BYTE *)(v67 + v66 + 49) = 1;
        *(_BYTE *)(352LL * v154 + *((_QWORD *)this + 388) + 48) = 1;
        v61 = v154;
      }
      v51 = *((_QWORD *)this + 388);
      v48 = v156;
      *((_DWORD *)this + 778) += *(unsigned __int16 *)(352LL * v61 + v51);
      v53 = *((_DWORD *)this + 778);
      v52 = v61 + 1;
      v154 = v52;
    }
    if ( *((int *)this + 779) <= 2400 && v53 > 0x40 )
    {
      WdLogSingleEntry3(2, this, 64, v53);
      WdLogGlobalForLineNumber = 7548;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Adapter 0x%I64x: Exceeded maximum number of %I64d nodes on pre-WDDM 2.5 adapter. Total node count: %I64d",
        (__int64)this,
        64,
        *((unsigned int *)this + 778),
        0,
        0);
      return 3221225485LL;
    }
    v68 = 0;
    if ( (*((_DWORD *)this + 644) & 1) == 0 )
    {
      WdLogSingleEntry1(2);
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
    if ( (*((_DWORD *)this + 645) & 0x800) != 0 )
    {
      v154 = 0;
      for ( i = 0; i < v48; v154 = i )
      {
        *(_QWORD *)v168 = 0;
        v163.pInputData = &v154;
        v163.Type = DXGKQAITYPE_FRAMEBUFFERSAVESIZE;
        v163.pOutputData = v168;
        v163.InputDataSize = 4;
        v163.OutputDataSize = 8;
        v70 = DXGADAPTER::DdiQueryAdapterInfo(this, &v163);
        RenderCore = v70;
        if ( v70 < 0 )
        {
          WdLogSingleEntry1(2);
          v74 = L"Failed to query frame buffer save area size. Status 0x%I64x";
          WdLogGlobalForLineNumber = 7572;
          goto LABEL_160;
        }
        if ( (v168[0] & 0xFFF) != 0 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 7578;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Frame buffer reserve size must be a multiple of PAGE_SIZE. Size=%I64u",
            *(__int64 *)v168,
            0,
            0,
            0,
            0);
          return 3221225485LL;
        }
        *(_QWORD *)(352LL * v154 + *((_QWORD *)this + 388) + 56) = *(_QWORD *)v168;
        v72 = v154;
        v73 = *(_QWORD *)(352LL * v154 + *((_QWORD *)this + 388) + 56);
        if ( v73 )
        {
          result = DXGADAPTER::CreateFrameBufferSaveAreaSection(this, v154, v73);
          if ( (int)result < 0 )
            return result;
          v72 = v154;
        }
        v48 = v156;
        i = v72 + 1;
      }
    }
    if ( !v68 )
      goto LABEL_170;
    v45 = 0;
  }
  v75 = 0;
  if ( v48 )
  {
    v76 = v156;
    do
    {
      v77 = *((_QWORD *)this + 388);
      v78 = 352LL * v75;
      v79 = *((_WORD *)this + 1294);
      *(_QWORD *)v168 = v77;
      *(_WORD *)(v77 + v78) = v79;
      v80 = *(_DWORD *)(v77 + v78 + 16)
          ^ ((unsigned __int8)*(_DWORD *)(v77 + v78 + 16)
           ^ (unsigned __int8)(*((_DWORD *)this + 645) >> 7))
          & 1;
      *(_DWORD *)(v77 + v78 + 16) = v80;
      v81 = v80 ^ (v80 ^ (*((_DWORD *)this + 645) >> 5)) & 2;
      *(_DWORD *)(v77 + v78 + 16) = v81;
      v82 = v81 ^ ((unsigned __int8)v81 ^ (unsigned __int8)(DXGADAPTER::IsGpuVaIoMmuSupported(this) << 6)) & 0x40;
      v83 = *(_QWORD *)v168;
      *(_DWORD *)(*(_QWORD *)v168 + v78 + 16) = v82;
      IsGpuVaIoMmuGlobalSupported = DXGADAPTER::IsGpuVaIoMmuGlobalSupported(this);
      *(_DWORD *)(v83 + v78 + 16) = v82
                                  ^ ((unsigned __int8)v82
                                   ^ (unsigned __int8)(IsGpuVaIoMmuGlobalSupported << 7))
                                  & 0x80;
      *(_WORD *)(v83 + v78 + 2) = *((_WORD *)this + 1292);
      *(_QWORD *)(v83 + v78 + 8) = *((_QWORD *)this + 27);
      if ( (((unsigned __int8)v82
           ^ ((unsigned __int8)v82
            ^ (unsigned __int8)(IsGpuVaIoMmuGlobalSupported << 7))
           & 0x80)
          & 0xC2) != 0 )
        *(_WORD *)(v83 + v78 + 48) = 257;
      ++v75;
    }
    while ( v75 < v76 );
    v40 = v160;
    v33 = v162;
    v3 = (struct _DXGK_ADAPTER_CAPS *)v158;
LABEL_170:
    v45 = 0;
    goto LABEL_171;
  }
  v3 = (struct _DXGK_ADAPTER_CAPS *)v158;
LABEL_171:
  if ( *(int *)((char *)this + v40) >= 2400 )
  {
    if ( *((_DWORD *)this + 772) >= 0x400u )
    {
      WdLogSingleEntry0(2);
      v36 = L"Driver should not set MiscCaps.Reserved bits";
      v35 = 7632;
      goto LABEL_60;
    }
    *((_BYTE *)this + 3169) = *((_BYTE *)this + 3088) & 1;
  }
  v85 = *((_DWORD *)this + 772);
  if ( (v85 & 0x10) != 0 && !*((_QWORD *)this + 175) )
  {
    WdLogSingleEntry0(2);
    v36 = L"Driver sets IndependentVidPnVSyncControl cap but does not support DxgkDdiControlInterrupt3, returning failure";
    v35 = 7642;
    goto LABEL_60;
  }
  if ( *((_BYTE *)this + 3332) )
    *((_DWORD *)this + 772) = v85 & 0xFFFFFFEF;
  if ( v33 >= 0x3001 )
  {
    v87 = *((_DWORD *)this + 712);
    if ( v87 != 4096
      && v87 != 4608
      && v87 != 4864
      && v87 != 0x2000
      && v87 != 8448
      && v87 != 8704
      && v87 != 8960
      && v87 != 9216
      && v87 != 9472
      && v87 != 9728
      && v87 != 9984
      && v87 != 10240
      && v87 != 10496
      && v87 != 12288
      && v87 != 12544
      && v87 != 12800 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 7700;
      v29 = L"Miniport returned unknown WDDM version 0x%I64x";
      v88 = *((int *)this + 712);
LABEL_216:
      v153 = 0;
      v150 = v88;
      goto LABEL_40;
    }
  }
  else
  {
    *((_DWORD *)this + 712) = 4096;
  }
  if ( !*((_BYTE *)DXGGLOBAL::GetGlobal() + 928) || (v86 = 1, (*((_DWORD *)this + 111) & 8) != 0) )
    v86 = 0;
  *((_BYTE *)this + 3128) = v86;
  if ( v86 )
  {
    if ( *((int *)this + 712) < 4608
      && (*((_DWORD *)this + 760)
       || *((_DWORD *)this + 761)
       || *((_BYTE *)this + 3048)
       || *((_BYTE *)this + 3049)
       || *((_BYTE *)this + 3050)
       || (*((_DWORD *)this + 641) & 0x10000000) != 0
       || (*((_DWORD *)this + 644) & 0x14) != 0
       || *((_BYTE *)this + 3051)
       || *((_BYTE *)this + 3053)
       || *((_BYTE *)this + 3054)) )
    {
      WdLogSingleEntry0(2);
      v36 = L"Driver reports WDDM version less than 1.2 but implements some WDDM 1.2 features.";
      v35 = 7726;
      goto LABEL_60;
    }
    if ( *((int *)this + 712) < 4864
      && ((*((_DWORD *)this + 643) & 0x10) != 0
       || (*((_DWORD *)this + 645) & 0x10) != 0
       || *((_BYTE *)this + 3055)
       || *((_DWORD *)this + 764)) )
    {
      WdLogSingleEntry0(2);
      v36 = L"Driver reports WDDM version less than 1.3 but implements some WDDM 1.3 features.";
      v35 = 7741;
      goto LABEL_60;
    }
    if ( *((int *)this + 712) < 0x2000 && *((_BYTE *)this + 3060) )
    {
      WdLogSingleEntry0(2);
      v36 = L"Pre-WDDM 2.0 driver should not set the HybridIntegrated cap.";
      v35 = 7769;
      goto LABEL_60;
    }
  }
  v89 = *((_DWORD *)this + 645);
  v90 = v89 & 0x8010;
  if ( (v89 & 0x10000) != 0 )
  {
    if ( v90 != 32784 )
    {
      WdLogSingleEntry0(2);
      v36 = L"Driver reports CrossAdapterResourceScanout but does not report lower tier support.";
      v35 = 7783;
      goto LABEL_60;
    }
  }
  else if ( v90 == 0x8000 )
  {
    WdLogSingleEntry0(2);
    v36 = L"Driver reports CrossAdapterResourceTexture but does not report lower tier support.";
    v35 = 7791;
    goto LABEL_60;
  }
  if ( v33 >= 0x4000 )
  {
    if ( v33 >= 0x5011 )
      goto LABEL_237;
  }
  else
  {
    v89 &= ~0x10u;
    *((_BYTE *)this + 3055) = 0;
    *((_DWORD *)this + 645) = v89;
  }
  if ( (*((_DWORD *)this + 111) & 1) != 0
    && (((*((_DWORD *)this + 111) & 0x1000) != 0) & (unsigned __int8)(v89 >> 4)) != 0 )
  {
    *((_BYTE *)this + 3060) = 1;
  }
LABEL_237:
  v91 = *(_BYTE *)v3 ^ (*(_BYTE *)v3 ^ (4 * *((_BYTE *)this + 3048))) & 4;
  *(_BYTE *)v3 = v91;
  v92 = v91 & 0xF7 | (*((_BYTE *)this + 3054) != 0 ? 8 : 0);
  *(_BYTE *)v3 = v92;
  v93 = v92 ^ (v92 ^ (32 * (*((_DWORD *)this + 645) >> 4))) & 0x20;
  *(_BYTE *)v3 = v93;
  v94 = v93 ^ (v93 ^ (*((_BYTE *)this + 3055) << 6)) & 0x40;
  *(_BYTE *)v3 = v94;
  v95 = v94 & 0xEF;
  *((_DWORD *)v3 + 1) = *((_DWORD *)this + 637);
  v96 = *((_BYTE *)v3 + 1) ^ (*((_BYTE *)this + 3060) ^ *((_BYTE *)v3 + 1)) & 1;
  *((_BYTE *)v3 + 1) = v96;
  *((_DWORD *)v3 + 2) = *((_DWORD *)this + 712);
  v97 = *((_DWORD *)this + 772) >> 3;
  *(_BYTE *)v3 = v94 & 0xEF;
  v98 = v96 ^ (v96 ^ (32 * v97)) & 0x20;
  *((_BYTE *)v3 + 1) = v98;
  if ( v33 >= 0x5021 )
  {
    v95 = v94 ^ (v94 ^ (16 * *((_BYTE *)this + 3080))) & 0x10;
    *(_BYTE *)v3 = v95;
  }
  if ( !*((_BYTE *)this + 209) )
  {
    if ( (v95 & 0x40) != 0 )
    {
      if ( v33 < 0x5005 && (*((_DWORD *)this + 492) || *((_DWORD *)this + 493)) )
      {
        WdLogSingleEntry1(2);
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
      v99 = v98 ^ (v98 ^ (2 * *((_BYTE *)this + 3083))) & 2;
      *((_BYTE *)v3 + 1) = v99;
    }
    else
    {
      v99 = v98;
    }
    v100 = v99 & 1;
    v101 = 0;
    if ( (v95 & 0x40) == 0 )
      v101 = v100 ^ 1;
    if ( !v101 && (v95 & 0x20) == 0 )
    {
      WdLogSingleEntry1(2);
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
    if ( ((unsigned __int8)-((v95 & 0x40) != 0) & v100) != 0 )
    {
      WdLogSingleEntry1(2);
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
    if ( v100 && !*((_DWORD *)this + 493) )
    {
      WdLogSingleEntry1(2);
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
    if ( *((_BYTE *)this + 3050) && (!*((_QWORD *)this + 101) || !*((_QWORD *)this + 102) || !*((_QWORD *)this + 103)) )
    {
      WdLogSingleEntry0(2);
      v36 = L"Driver reports SupportPerEngineTDR cap but does not fill in all of the required DDIs.";
      v35 = 7897;
      goto LABEL_60;
    }
    if ( (*((_DWORD *)this + 641) & 4) != 0 && !*((_QWORD *)this + 100) )
    {
      WdLogSingleEntry0(2);
      v36 = L"Driver reports SupportKernelModeCommandBuffer cap but does not fill in the pfnRenderKm DDI.";
      v35 = 7904;
      goto LABEL_60;
    }
    if ( *((_BYTE *)this + 3053) && (!*((_QWORD *)this + 105) || !*((_QWORD *)this + 106)) )
    {
      WdLogSingleEntry0(2);
      v36 = L"Driver reports SupportRuntimePowerManagement cap but does not fill in the pfnSetPowerComponentFState or pfnP"
             "owerRuntimeControlRequest DDI.";
      v35 = 7912;
      goto LABEL_60;
    }
    if ( v33 < 0x300C && *((_QWORD *)this + 105) && *((_QWORD *)this + 106) )
      *((_BYTE *)this + 3053) = 1;
  }
  *((_WORD *)this + 1565) = 0;
  *((_BYTE *)this + 3132) = 0;
  if ( !*((_BYTE *)this + 3052) )
    goto LABEL_311;
  if ( v33 < 0x300B )
  {
    WdLogSingleEntry0(2);
    v36 = L"Driver reports SupportMultiPlaneOverlay cap but it is not compiled with expected header files.";
    v35 = 7934;
    goto LABEL_60;
  }
  if ( v33 < 0x4000 )
  {
    *((_BYTE *)this + 3130) = 1;
    goto LABEL_293;
  }
  if ( v33 == 0x4000 )
  {
    *((_BYTE *)this + 3131) = 1;
    goto LABEL_293;
  }
  v102 = *((_DWORD *)this + 764);
  if ( !v102 )
  {
    WdLogSingleEntry0(2);
    v36 = L"Driver reports SupportMultiPlaneOverlay cap but doesn't report any overlay planes or panel fitter.";
    v35 = 7947;
    goto LABEL_60;
  }
  if ( v102 <= 8 )
  {
    if ( v33 > 0x5000 )
      *((_BYTE *)this + 3132) = 1;
    goto LABEL_293;
  }
  v103 = *((_DWORD *)this + 712);
  if ( v103 < 8704 )
  {
    if ( v103 < 0x2000 || v102 != 10 )
    {
      WdLogSingleEntry0(2);
      v35 = 7970;
      goto LABEL_286;
    }
    *((_DWORD *)this + 764) = 8;
  }
  else if ( v102 > 0xA )
  {
    WdLogSingleEntry0(2);
    v35 = 7957;
LABEL_286:
    v36 = L"Driver reports more than the supported number of overlay planes.";
    goto LABEL_60;
  }
LABEL_293:
  v104 = *((_QWORD *)this + 109);
  if ( !v104 && !*((_QWORD *)this + 125) && !*((_QWORD *)this + 129) )
  {
    WdLogSingleEntry0(2);
    v35 = 7986;
LABEL_297:
    v36 = L"Driver reports SupportMultiPlaneOverlay cap but does not fill in all of the required DDIs.";
    goto LABEL_60;
  }
  if ( v33 > 0x4002 && !*((_QWORD *)this + 113) && !*((_QWORD *)this + 124) && !*((_QWORD *)this + 128) )
  {
    WdLogSingleEntry0(2);
    v35 = 7998;
    goto LABEL_297;
  }
  if ( !*((_BYTE *)this + 3051) )
  {
    WdLogSingleEntry0(2);
    v36 = L"Driver reports SupportMultiPlaneOverlay cap but DirectFlip is not supported.";
    v35 = 8008;
    goto LABEL_60;
  }
  if ( v104 )
  {
    v105 = DXGGLOBAL::GetGlobal();
    DXGGLOBAL::RecordFeatureUsage(v105, 1, 1);
  }
  if ( *((_QWORD *)this + 125) )
  {
    v106 = DXGGLOBAL::GetGlobal();
    DXGGLOBAL::RecordFeatureUsage(v106, 2, 1);
  }
  if ( *((_QWORD *)this + 129) )
  {
    v107 = DXGGLOBAL::GetGlobal();
    DXGGLOBAL::RecordFeatureUsage(v107, 3, 1);
  }
LABEL_311:
  *((_BYTE *)this + 3167) = 0;
  if ( *((_BYTE *)this + 209) )
    goto LABEL_324;
  v108 = 0;
  if ( v33 >= 0x700A && *((int *)this + 712) >= 8704 && (!*((_QWORD *)this + 83) || *((_QWORD *)this + 146)) )
  {
    *((_BYTE *)this + 3167) = 1;
    v108 = 1;
  }
  if ( *((int *)this + 712) < 8960 )
  {
LABEL_324:
    *((_DWORD *)this + 640) &= 0xFFFFFFE3;
  }
  else
  {
    v109 = (*((_DWORD *)this + 640) >> 3) & 1;
    v110 = (*((_DWORD *)this + 640) >> 2) & 1;
    if ( v110 < v109 || v109 < ((*((_DWORD *)this + 640) >> 4) & 1u) )
    {
      WdLogSingleEntry2(2, *((_QWORD *)this + 27));
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
    if ( !v108 && v110 )
    {
      WdLogSingleEntry2(2, *((_QWORD *)this + 27));
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
    LOBYTE(v45) = *((_DWORD *)this + 712) >= 0x2000;
    v111 = DXGGLOBAL::GetGlobal();
    v112 = DXGGLOBAL::DeferredInitialize(v111, v45);
    v45 = 0;
    RenderCore = v112;
    if ( v112 < 0 )
    {
      WdLogSingleEntry1(2);
      v74 = L"DXGGLOBAL::DeferredInitialize failed (Status = 0x%I64x).";
      WdLogGlobalForLineNumber = 8093;
LABEL_160:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v74, RenderCore, 0, 0, 0, 0);
      return (unsigned int)RenderCore;
    }
  }
  DXGADAPTER::Config = 0;
  DXGADAPTER::ReadConfig(this, v3);
  DXGADAPTER::InitializeDriverWorkarounds(this);
  if ( *((_BYTE *)this + 209) )
  {
    **((_DWORD **)this + 390) = **((_DWORD **)this + 390) & 0xFFFDFFFF | v161 & 0x20000;
    **((_DWORD **)this + 390) = **((_DWORD **)this + 390) & 0xFFFE7FFF | v161 & 0x18000;
    **((_DWORD **)this + 390) = **((_DWORD **)this + 390) & 0xFFEFFFFF | v161 & 0x100000;
    **((_DWORD **)this + 390) = **((_DWORD **)this + 390) & 0xFFF3FFFF | v161 & 0xC0000;
    *((_BYTE *)this + 3133) = 0;
  }
  else if ( (*((_DWORD *)this + 111) & 0x10) != 0 && *((_BYTE *)this + 3183) )
  {
    *((_DWORD *)this + 645) |= 0x400u;
  }
  v113 = *((_DWORD *)this + 712);
  if ( v113 < 9216 )
    goto LABEL_337;
  if ( *((_QWORD *)this + 166) )
  {
    if ( *((_QWORD *)this + 167) )
      goto LABEL_338;
LABEL_351:
    WdLogSingleEntry0(2);
    v36 = L"Driver cannot support only one of DdiQueryDiagnosticTypesSupport and DdiControlDiagnosticReporting.";
    v35 = 8147;
    goto LABEL_60;
  }
  if ( *((_QWORD *)this + 167) )
    goto LABEL_351;
LABEL_337:
  *((_QWORD *)this + 166) = W32kStub_UserRemoveWindowedSwapChain;
  *((_QWORD *)this + 167) = DXGADAPTER::DefaultDdiControlDiagnosticReporting;
LABEL_338:
  if ( v113 >= 12800 && v33 >= 0x11001 )
  {
    memset(&v164, 0, 24);
    v164.Type = DXGKQAITYPE_POWERCOMPONENTINFO|0x20;
    *(_OWORD *)&v164.OutputDataSize = 0;
    v164.pOutputData = (char *)this + 5284;
    v164.OutputDataSize = 4;
    if ( (int)DXGADAPTER::DdiQueryAdapterInfo(this, &v164) < 0 )
    {
      *(_QWORD *)(WdLogNewEntry5_WdTrace() + 24) = this;
      WdLogGlobalForLineNumber = 8162;
    }
  }
  v159 = 0;
  memset(&v165, 0, 24);
  v165.Type = DXGKQAITYPE_PHYSICALADAPTERCAPS|0x20;
  v165.pOutputData = &v159;
  *(_OWORD *)&v165.OutputDataSize = 0;
  v165.OutputDataSize = 4;
  v114 = DXGADAPTER::DdiQueryAdapterInfo(this, &v165);
  v115 = *((_BYTE *)this + 3184) & 0xFD;
  if ( v114 >= 0 )
    v115 |= 2 * (v159 & 1);
  *((_BYTE *)this + 3184) = v115;
  result = DXGADAPTER::CheckMcdmDdiOverall(this);
  if ( (int)result >= 0 )
  {
    v116 = DXGGLOBAL::GetGlobal();
    *(_QWORD *)((char *)this + 4924) = 0;
    *(_QWORD *)((char *)this + 4932) = -1;
    v158 = 0;
    while ( v45 < 2 )
    {
      DWORD1(v158) = *((_DWORD *)v116 + v45 + 76239);
      if ( DWORD1(v158) )
      {
        if ( v45 )
        {
          LODWORD(v158) = v158 | 2;
          DWORD2(v158) |= 0xFFFFFFFE;
        }
        else
        {
          LODWORD(v158) = v158 | 1;
          DWORD2(v158) |= 0xFFFFFFFC;
        }
        HIDWORD(v158) = v45;
        DXGADAPTER::UpdateDiagnosticReporting(this, (struct DXGADAPTER::_ADAPTER_UPDATE_DIAGNOSTIC_REPORTING *)&v158);
      }
      ++v45;
    }
    DXGADAPTER::QueryFeatureEnablement(this);
    if ( (*((_DWORD *)this + 644) & 0x800) != 0 )
    {
      if ( (*((_BYTE *)this + 5156) & 1) == 0 )
      {
        WdLogSingleEntry0(2);
        v35 = 8202;
        v36 = L"Driver reports NativeGpuFence cap when NativeFence feature is disabled, returning failure";
        goto LABEL_60;
      }
      v117 = (_DWORD *)((char *)this + 5192);
      v163.Type = DXGKQAITYPE_QUERYSEGMENT3|0x20;
      v163.pOutputData = (char *)this + 5192;
      v163.OutputDataSize = 56;
      v118 = DXGADAPTER::DdiQueryAdapterInfo(this, &v163);
      RenderCore = v118;
      if ( v118 < 0 )
      {
        WdLogSingleEntry1(2);
        v74 = L"Failed to get DXGK_NATIVE_FENCE_CAPS. Status 0x%I64x";
        WdLogGlobalForLineNumber = 8213;
        goto LABEL_160;
      }
      if ( *v117 > 0x38u )
      {
        WdLogSingleEntry2(2, (unsigned int)*v117);
        WdLogGlobalForLineNumber = 8221;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Driver specified native fence MonitoredValuePadding (%u) greater than maximum limit of %u bytes",
          (unsigned int)*v117,
          56,
          0,
          0,
          0);
        return (unsigned int)RenderCore;
      }
    }
    RenderCore = (int)ADAPTER_RENDER::CreateRenderCore(this, (struct ADAPTER_RENDER **)this + 405);
    v119 = *((_QWORD *)this + 405);
    if ( (int)RenderCore < 0 )
    {
      if ( v119 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 8233;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pRenderCore == NULL", 8233, 0, 0, 0, 0);
      }
      WdLogSingleEntry2(2, this);
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
    if ( v119 )
    {
      if ( IsAdapterSessionized )
      {
        WdLogSingleEntry0(2);
        v88 = 8252;
        v29 = L"Render capable adapter should NOT be sessionized!";
        WdLogGlobalForLineNumber = 8252;
        goto LABEL_216;
      }
      if ( (((*((_DWORD *)this + 772) & 4) == 0) & (unsigned __int8)~(unsigned __int8)(*((_DWORD *)this + 772) >> 3)) != 0 )
        *((_BYTE *)this + 3184) |= 1u;
    }
    v120 = (_QWORD *)((char *)this + 3232);
    DisplayCore = ADAPTER_DISPLAY::CreateDisplayCore(this, (struct ADAPTER_DISPLAY **)this + 404);
    RenderCore = DisplayCore;
    if ( DisplayCore < 0 )
    {
      if ( *v120 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 8267;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pDisplayCore == NULL", 8267, 0, 0, 0, 0);
      }
      WdLogSingleEntry2(2, this);
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
    if ( !*((_QWORD *)this + 405) && !*v120 )
    {
      WdLogSingleEntry2(2, this);
      v29 = L"Current adapter 0x%I64x does not have display or render capabilities (Status = 0x%I64x).";
      v153 = -1073741735;
      v150 = (__int64)this;
      WdLogGlobalForLineNumber = 8283;
      goto LABEL_40;
    }
    if ( (*((_DWORD *)this + 772) & 0x200) != 0 && *v120 )
    {
      WdLogSingleEntry1(2);
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
    v122 = *(_BYTE *)v3 & 0xFE | (*((_QWORD *)this + 404) != 0);
    *(_BYTE *)v3 = v122;
    v123 = v122 & 0xFD | (*((_QWORD *)this + 405) != 0 ? 2 : 0);
    *(_BYTE *)v3 = v123;
    v124 = *((_QWORD *)this + 404);
    if ( v124 )
      v125 = *(_DWORD *)(v124 + 24) & 1;
    else
      LOBYTE(v125) = 0;
    v126 = v123 & 0x7F | ((_BYTE)v125 << 7);
    *(_BYTE *)v3 = v126;
    if ( (v126 & 1) != 0 )
      *((_BYTE *)v3 + 1) = *((_BYTE *)v3 + 1) & 0xFB | (DXGADAPTER::DriverSupportSetTimingsFromVidPn(this) != 0 ? 4 : 0);
    else
      *((_BYTE *)v3 + 1) &= ~4u;
    if ( !*((_QWORD *)this + 405) )
      *((_DWORD *)this + 641) |= 1u;
    if ( DXGADAPTER::IsDxgmms2(this) )
    {
      v129 = *((_DWORD *)this + 111);
      if ( (v129 & 4) == 0
        && (v129 & 8) == 0
        && v127
        && v33 >= 0x5008
        && (!*((_QWORD *)this + 114) || !*((_QWORD *)this + 126)) )
      {
        WdLogSingleEntry0(2);
        v35 = 8333;
        v36 = L"Driver is compiled against DXGKDDI_INTERFACE_VERSION_WDDM2_0_M2_2_1 or greater, but does not fill in the p"
               "fnCalibrateGpuClock or pfnSetStablePowerState DDI.";
        goto LABEL_60;
      }
    }
    if ( *((_BYTE *)this + 3128) && DXGADAPTER::IsFullWDDMAdapter(v128) && *((int *)this + 712) >= 4608 )
    {
      if ( !*((_BYTE *)this + 3051) )
      {
        WdLogSingleEntry0(2);
        v35 = 8348;
        v36 = L"Driver reports WDDM version 1.2 but does not implement all mandatory WDDM 1.2 full adapter features.";
        goto LABEL_60;
      }
    }
    else if ( !*((_BYTE *)this + 3051) )
    {
      goto LABEL_407;
    }
    if ( *((_BYTE *)this + 209) )
      goto LABEL_408;
    v130 = *((_QWORD *)this + 405);
    if ( !v130
      || !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)(*(_QWORD *)(v130 + 760) + 8LL) + 664LL))(*(_QWORD *)(v130 + 768)) )
    {
      *(_WORD *)((char *)this + 3051) = 0;
    }
LABEL_407:
    if ( !*((_BYTE *)this + 209) )
    {
LABEL_409:
      v131 = DXGADAPTER::IsBddFallbackDriver(this) != 0;
      v134 = *((_DWORD *)this + 111);
      *((_DWORD *)this + 50) = v131 ? 3 : 1;
      if ( (v134 & 0x10) != 0 && !*((_QWORD *)this + 404) )
      {
        DXGGLOBALSHAREMUTEX::DXGGLOBALSHAREMUTEX((DXGGLOBALSHAREMUTEX *)&v158);
        DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)&v158);
        if ( *((_QWORD *)DXGGLOBAL::GetGlobal() + 124) )
        {
          WdLogSingleEntry2(2, this);
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
          v135 = DXGGLOBAL::GetGlobal();
          DXGGLOBAL::SetWarpAdapter(v135, this);
        }
        DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v158);
      }
      if ( *((_BYTE *)this + 209)
        || (v136 = DXGADAPTER::InitializePowerManagement(this, v132, v133), RenderCore = v136, v136 >= 0) )
      {
        if ( *((_BYTE *)this + 3128) )
        {
          if ( *((int *)this + 712) >= 4864 )
          {
            if ( DXGADAPTER::IsFullWDDMAdapter(this) )
            {
              v138 = *((_DWORD *)this + 111);
              if ( (v138 & 4) == 0 && (v138 & 0x20) == 0 && (*((_DWORD *)this + 643) & 0x10) == 0 )
              {
                WdLogSingleEntry0(2);
                v35 = 8429;
                v36 = L"WDDM 1.3 driver must support independent flip.";
                goto LABEL_60;
              }
            }
          }
        }
      }
      else
      {
        WdLogSingleEntry2(2, this);
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
        *((_BYTE *)this + 3170) = 1;
      if ( v33 >= 0xA008 )
        *((_BYTE *)this + 3170) = 1;
      v137 = operator new(40, 1265072196, 64);
      if ( v137 )
      {
        *(_OWORD *)v137 = 0;
        *(_OWORD *)(v137 + 16) = 0;
        *(_QWORD *)(v137 + 32) = 0;
      }
      else
      {
        v137 = 0;
      }
      *((_QWORD *)this + 635) = v137;
      if ( !v137 )
      {
        WdLogSingleEntry0(2);
        v23 = L"Failed to allocate MockDriverState object";
        v22 = 8467;
        WdLogGlobalForLineNumber = 8467;
        v152 = 0;
        goto LABEL_31;
      }
      LocallyUniqueId = MOCKDRIVERSTATE::Initialize((MOCKDRIVERSTATE *)v137, this);
      if ( LocallyUniqueId < 0 )
      {
        WdLogSingleEntry0(2);
        v10 = 8474;
        v11 = L"Failed to initialize MockDriverState object";
        v12 = 0x40000;
        goto LABEL_13;
      }
      *((_BYTE *)this + 5088) = 0;
      LocallyUniqueId = DXGADAPTER::InitializeVSyncPhaseState(this);
      if ( LocallyUniqueId < 0 )
      {
        WdLogSingleEntry0(6);
        v10 = 8487;
        v11 = L"Failed to allocate VSync Phase Timer state";
        goto LABEL_12;
      }
      v168[0] = 0;
      GetCabcOptionFromRegistry(v168);
      if ( (int)ZwUpdateWnfStateData(&WNF_DXGK_CABC_OPTION_CHANGED, v168, 4) < 0 )
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 8502;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Failed to initialize CABC State", 8502, 0, 0, 0, 0);
      }
      v139 = *((_QWORD *)this + 405);
      if ( v139 && !*((_BYTE *)this + 209) )
      {
        v140 = *(_QWORD *)(v139 + 736);
        v141 = DXGGLOBAL::GetGlobal();
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)(v140 + 8) + 936LL))(
          *(_QWORD *)(v139 + 744),
          (__int64)v141 + 1344);
      }
      if ( (*((_DWORD *)this + 111) & 1) != 0 )
        *((_QWORD *)DXGGLOBAL::GetGlobal() + 128) = *(_QWORD *)((char *)this + 412);
      if ( (int)RenderCore < 0 )
        return (unsigned int)RenderCore;
      if ( v156 <= 1 )
        goto LABEL_452;
      v142 = *((_DWORD *)this + 105);
      if ( v142 == 4318 )
      {
        v143 = DXGGLOBAL::GetGlobal();
        v144 = 7;
      }
      else
      {
        if ( v142 != 4098 )
          goto LABEL_452;
        v143 = DXGGLOBAL::GetGlobal();
        v144 = 8;
      }
      DXGGLOBAL::RecordFeatureUsage(v143, v144, 1);
LABEL_452:
      v145 = DXGGLOBAL::GetGlobal();
      if ( DXGGLOBAL::ConsiderForMultiAdapterFeatureUsage(v146, this) )
      {
        v147 = *((_DWORD *)this + 779);
        if ( v147 > *((_DWORD *)v145 + 76316) )
        {
          v148 = DXGGLOBAL::GetGlobal();
          DXGGLOBAL::RecordFeatureUsage(v148, 11, v147);
          *((_DWORD *)v145 + 76316) = v147;
        }
        if ( v147 < *((_DWORD *)v145 + 76315) )
        {
          v149 = DXGGLOBAL::GetGlobal();
          DXGGLOBAL::RecordFeatureUsage(v149, 10, v147);
          *((_DWORD *)v145 + 76315) = v147;
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
0x1401c43e0  mov     [rsp-8+arg_18], rbx
0x1401c43e5  push    rbp
0x1401c43e6  push    rsi
0x1401c43e7  push    rdi
0x1401c43e8  push    r12
0x1401c43ea  push    r13
0x1401c43ec  push    r14
0x1401c43ee  push    r15
0x1401c43f0  lea     rbp, [rsp-50h]
0x1401c43f5  sub     rsp, 150h
0x1401c43fc  mov     rax, cs:__security_cookie
0x1401c4403  xor     rax, rsp
0x1401c4406  mov     [rbp+80h+var_38], rax
0x1401c440a  mov     r12, r8
0x1401c440d  mov     qword ptr [rsp+180h+var_120], r8
0x1401c4412  mov     rdi, rdx
0x1401c4415  mov     rsi, rcx
0x1401c4418  call    cs:__imp_KeGetCurrentIrql
0x1401c441f  nop     dword ptr [rax+rax+00h]
0x1401c4424  or      r13d, 0FFFFFFFFh
0x1401c4428  xor     r15d, r15d
0x1401c442b  test    al, al
0x1401c442d  jz      short loc_1401C4479
0x1401c442f  lea     ecx, [r15+1]
0x1401c4433  call    cs:__imp_WdLogSingleEntry0
0x1401c443a  nop     dword ptr [rax+rax+00h]
0x1401c443f  mov     [rsp+180h+var_140], r15
0x1401c4444  lea     r9, aKegetcurrentir_4; "KeGetCurrentIrql() == PASSIVE_LEVEL"
0x1401c444b  mov     [rsp+180h+var_148], r15
0x1401c4450  mov     eax, 1B49h
0x1401c4455  mov     [rsp+180h+var_150], r15
0x1401c445a  mov     r8d, r13d
0x1401c445d  mov     [rsp+180h+var_158], r15
0x1401c4462  mov     edx, 40002h
0x1401c4467  xor     ecx, ecx
0x1401c4469  mov     [rsp+180h+var_160], rax
0x1401c446e  mov     cs:WdLogGlobalForLineNumber, eax
0x1401c4474  call    DxgkLogInternalTriageEvent
0x1401c4479  mov     eax, [rsi+0C8h]
0x1401c447f  test    eax, eax
0x1401c4481  jnz     loc_1401C4A54
0x1401c4487  call    Feature_FenceStorageUsingVidMmAlloc__private_IsEnabledDeviceUsageNoInline
0x1401c448c  mov     r8d, 40h ; '@'
0x1401c4492  test    eax, eax
0x1401c4494  mov     edx, 4B677844h
0x1401c4499  setnz   cs:?g_Feature_FenceStorageUsingVidMmAlloc@@3EC; uchar volatile g_Feature_FenceStorageUsingVidMmAlloc
0x1401c44a0  lea     r14d, [r8+28h]
0x1401c44a4  mov     ecx, r14d
0x1401c44a7  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401c44ac  mov     [rsi+0A8h], rax
0x1401c44b3  test    rax, rax
0x1401c44b6  jnz     short loc_1401C44E5
0x1401c44b8  mov     r8, 0FFFFFFFFC0000017h
0x1401c44bf  lea     ecx, [rax+3]
0x1401c44c2  mov     rdx, rsi
0x1401c44c5  call    cs:__imp_WdLogSingleEntry2
0x1401c44cc  nop     dword ptr [rax+rax+00h]
0x1401c44d1  mov     cs:WdLogGlobalForLineNumber, 1B5Dh
0x1401c44db  mov     eax, 0C0000017h
0x1401c44e0  jmp     loc_1401C6CC9
0x1401c44e5  mov     rcx, rax; Resource
0x1401c44e8  call    cs:__imp_ExInitializeResourceLite
0x1401c44ef  nop     dword ptr [rax+rax+00h]
0x1401c44f4  movsxd  rbx, eax
0x1401c44f7  test    eax, eax
0x1401c44f9  jns     short loc_1401C4523
0x1401c44fb  mov     r8, rbx
0x1401c44fe  mov     rdx, rsi
0x1401c4501  mov     ecx, 3
0x1401c4506  call    cs:__imp_WdLogSingleEntry2
0x1401c450d  nop     dword ptr [rax+rax+00h]
0x1401c4512  mov     cs:WdLogGlobalForLineNumber, 1B68h
0x1401c451c  mov     eax, ebx
0x1401c451e  jmp     loc_1401C6CC9
0x1401c4523  mov     rcx, rdi
0x1401c4526  mov     [rsi+0D8h], rdi
0x1401c452d  call    DpiGetSysMmAdapterFromDevice
0x1401c4532  mov     rcx, rdi; DeviceObject
0x1401c4535  mov     [rsi+0E0h], rax
0x1401c453c  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x1401c4543  nop     dword ptr [rax+rax+00h]
0x1401c4548  mov     rcx, rax; Object
0x1401c454b  mov     [rsi+0E8h], rax
0x1401c4552  call    cs:__imp_ObfDereferenceObject
0x1401c4559  nop     dword ptr [rax+rax+00h]
0x1401c455e  lea     rcx, [rsi+1304h]; Luid
0x1401c4565  call    cs:__imp_ZwAllocateLocallyUniqueId
0x1401c456c  nop     dword ptr [rax+rax+00h]
0x1401c4571  mov     ebx, eax
0x1401c4573  test    eax, eax
0x1401c4575  jns     short loc_1401C45C7
0x1401c4577  mov     ecx, 6
0x1401c457c  call    cs:__imp_WdLogSingleEntry0
0x1401c4583  nop     dword ptr [rax+rax+00h]
0x1401c4588  mov     eax, 1B7Dh
0x1401c458d  lea     r9, aZwallocateloca; "ZwAllocateLocallyUniqueId failed"
0x1401c4594  mov     r8d, r13d
0x1401c4597  mov     edx, 40001h
0x1401c459c  mov     [rsp+180h+var_140], r15
0x1401c45a1  xor     ecx, ecx
0x1401c45a3  mov     [rsp+180h+var_148], r15
0x1401c45a8  mov     [rsp+180h+var_150], r15
0x1401c45ad  mov     [rsp+180h+var_158], r15
0x1401c45b2  mov     [rsp+180h+var_160], rax
0x1401c45b7  mov     cs:WdLogGlobalForLineNumber, eax
0x1401c45bd  call    DxgkLogInternalTriageEvent
0x1401c45c2  jmp     loc_1401C451C
0x1401c45c7  mov     edx, 4B677844h
0x1401c45cc  mov     r8d, 40h ; '@'
0x1401c45d2  mov     rcx, r14
0x1401c45d5  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401c45da  mov     [rsi+118h], rax
0x1401c45e1  test    rax, rax
0x1401c45e4  jnz     short loc_1401C460E
0x1401c45e6  mov     r8, 0FFFFFFFFC0000017h
0x1401c45ed  lea     ecx, [rax+3]
0x1401c45f0  mov     rdx, rsi
0x1401c45f3  call    cs:__imp_WdLogSingleEntry2
0x1401c45fa  nop     dword ptr [rax+rax+00h]
0x1401c45ff  mov     cs:WdLogGlobalForLineNumber, 1B8Ah
0x1401c4609  jmp     loc_1401C44DB
0x1401c460e  mov     rcx, rax; Resource
0x1401c4611  call    cs:__imp_ExInitializeResourceLite
0x1401c4618  nop     dword ptr [rax+rax+00h]
0x1401c461d  movsxd  rbx, eax
0x1401c4620  test    eax, eax
0x1401c4622  jns     short loc_1401C464A
0x1401c4624  mov     r8, rbx
0x1401c4627  mov     rdx, rsi
0x1401c462a  mov     ecx, 3
0x1401c462f  call    cs:__imp_WdLogSingleEntry2
0x1401c4636  nop     dword ptr [rax+rax+00h]
0x1401c463b  mov     cs:WdLogGlobalForLineNumber, 1B95h
0x1401c4645  jmp     loc_1401C451C
0x1401c464a  lock inc qword ptr [rsi+18h]
0x1401c464f  mov     qword ptr [rsi+28h], 0FFFFFFFFFFFFFFFFh
0x1401c4657  mov     rax, [rdi+40h]
0x1401c465b  mov     [rbp+80h+var_100], r15
0x1401c465f  cmp     [rax+1E1h], r15b
0x1401c4666  jz      short loc_1401C46D7
0x1401c4668  lea     rdx, [rbp+80h+var_100]; struct DRIVER_WORKAROUNDS *
0x1401c466c  mov     rcx, rsi; this
0x1401c466f  call    ?InitializeParavirtualizedAdapter@DXGADAPTER@@QEAAJPEAUDRIVER_WORKAROUNDS@@@Z; DXGADAPTER::InitializeParavirtualizedAdapter(DRIVER_WORKAROUNDS *)
0x1401c4674  xor     r13d, r13d
0x1401c4677  movsxd  r15, eax
0x1401c467a  test    eax, eax
0x1401c467c  jns     loc_1401C4728
0x1401c4682  mov     rdx, r15
0x1401c4685  lea     ecx, [r13+2]
0x1401c4689  call    cs:__imp_WdLogSingleEntry1
0x1401c4690  nop     dword ptr [rax+rax+00h]
0x1401c4695  mov     [rsp+180h+var_140], r13
0x1401c469a  lea     r9, aInitializepara; "InitializeParavirtualizedAdapter failed"...
0x1401c46a1  mov     [rsp+180h+var_148], r13
0x1401c46a6  mov     [rsp+180h+var_150], r13
0x1401c46ab  mov     [rsp+180h+var_158], r13
0x1401c46b0  mov     cs:WdLogGlobalForLineNumber, 1BACh
0x1401c46ba  or      r8d, 0FFFFFFFFh
0x1401c46be  mov     [rsp+180h+var_160], r15
0x1401c46c3  mov     edx, 40000h
0x1401c46c8  xor     ecx, ecx
0x1401c46ca  call    DxgkLogInternalTriageEvent
0x1401c46cf  mov     eax, r15d
0x1401c46d2  jmp     loc_1401C6CC9
0x1401c46d7  lea     r9, [rsi+960h]
0x1401c46de  mov     [rsi+769h], r15b
0x1401c46e5  lea     r8, [rsi+120h]; void *
0x1401c46ec  mov     rcx, rdi; int
0x1401c46ef  lea     rdx, [rsi+740h]; void *
0x1401c46f6  call    DpiGetAdapterInfo
0x1401c46fb  movsxd  rbx, eax
0x1401c46fe  test    eax, eax
0x1401c4700  jns     short loc_1401C472F
0x1401c4702  mov     r8, rbx
0x1401c4705  mov     rdx, rsi
0x1401c4708  mov     ecx, 3
0x1401c470d  call    cs:__imp_WdLogSingleEntry2
0x1401c4714  nop     dword ptr [rax+rax+00h]
0x1401c4719  mov     cs:WdLogGlobalForLineNumber, 1BBDh
0x1401c4723  jmp     loc_1401C451C
0x1401c4728  xor     r15d, r15d
0x1401c472b  or      r13d, 0FFFFFFFFh
0x1401c472f  mov     rcx, [rsi+0D8h]
0x1401c4736  mov     rdx, rsi
0x1401c4739  call    DpiFdoSetFeatureDatabaseDxgAdapter
0x1401c473e  xor     eax, eax
0x1401c4740  xorps   xmm0, xmm0
0x1401c4743  mov     qword ptr [rbp+80h+var_50], rax
0x1401c4747  mov     rax, [rsi+9B0h]
0x1401c474e  movups  [rbp+80h+var_60], xmm0
0x1401c4752  test    rax, rax
0x1401c4755  jz      short loc_1401C477F
0x1401c4757  mov     rcx, [rsi+968h]
0x1401c475e  lea     rdx, [rbp+80h+var_60]
0x1401c4762  call    _guard_dispatch_icall
0x1401c4767  test    eax, eax
0x1401c4769  js      short loc_1401C477F
0x1401c476b  mov     rax, qword ptr [rbp+80h+var_60+8]
0x1401c476f  mov     [rsi+134Ch], rax
0x1401c4776  mov     eax, [rbp+80h+var_50]
0x1401c4779  mov     [rsi+1354h], eax
0x1401c477f  xor     r9d, r9d; unsigned __int64 *
0x1401c4782  lea     r8, [rbp+80h+var_50]; unsigned int *
0x1401c4786  mov     rcx, rsi; this
0x1401c4789  call    ?IsAdapterSessionized@DXGADAPTER@@QEBA_NPEAU_LUID@@PEAIPEA_K@Z; DXGADAPTER::IsAdapterSessionized(_LUID *,uint *,unsigned __int64 *)
0x1401c478e  mov     [rsp+180h+var_12C], al
0x1401c4792  mov     bl, al
0x1401c4794  test    al, al
0x1401c4796  jz      loc_1401C4827
0x1401c479c  mov     rcx, [rsi+10h]
0x1401c47a0  mov     edx, [rbp+80h+var_50]; unsigned int
0x1401c47a3  mov     rcx, [rcx+3D8h]; this
0x1401c47aa  call    ?GetSessionDataForSpecifiedSession@DXGSESSIONMGR@@QEAAPEAVDXGSESSIONDATA@@K@Z; DXGSESSIONMGR::GetSessionDataForSpecifiedSession(ulong)
0x1401c47af  test    rax, rax
0x1401c47b2  jz      short loc_1401C47C7
0x1401c47b4  mov     rcx, rax; this
0x1401c47b7  call    ?AcquireSessionAdapterOrdinal@DXGSESSIONDATA@@QEAAKXZ; DXGSESSIONDATA::AcquireSessionAdapterOrdinal(void)
0x1401c47bc  mov     [rsi+0F4h], eax
0x1401c47c2  cmp     eax, r13d
0x1401c47c5  jnz     short loc_1401C4827
0x1401c47c7  mov     edx, [rbp+80h+var_50]
0x1401c47ca  mov     ecx, 2
0x1401c47cf  mov     r8, 0FFFFFFFFC0000017h
0x1401c47d6  call    cs:__imp_WdLogSingleEntry2
0x1401c47dd  nop     dword ptr [rax+rax+00h]
0x1401c47e2  mov     eax, [rbp+80h+var_50]
0x1401c47e5  lea     r9, aExceededTheMax; "Exceeded the maximum number of sessioni"...
0x1401c47ec  mov     [rsp+180h+var_140], r15
0x1401c47f1  mov     r8d, r13d
0x1401c47f4  mov     [rsp+180h+var_148], r15
0x1401c47f9  mov     [rsp+180h+var_150], r15
0x1401c47fe  mov     [rsp+180h+var_158], 0FFFFFFFFC0000017h
0x1401c4807  mov     cs:WdLogGlobalForLineNumber, 1BDEh
0x1401c4811  mov     edx, 40000h
0x1401c4816  xor     ecx, ecx
0x1401c4818  mov     [rsp+180h+var_160], rax
0x1401c481d  call    DxgkLogInternalTriageEvent
0x1401c4822  jmp     loc_1401C44DB
0x1401c4827  mov     rcx, [rsi+10h]; this
0x1401c482b  mov     dl, bl; unsigned __int8
0x1401c482d  call    ?AcquireAdapterOrdinal@DXGGLOBAL@@QEAAKE@Z; DXGGLOBAL::AcquireAdapterOrdinal(uchar)
0x1401c4832  mov     [rsi+0F0h], eax
0x1401c4838  cmp     eax, r13d
0x1401c483b  jz      loc_1401C44DB
0x1401c4841  test    dword ptr [rsi+1BCh], 200h
0x1401c484b  jz      short loc_1401C4859
0x1401c484d  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401c4852  mov     byte ptr [rax+4A700h], 1
0x1401c4859  mov     eax, [rsi+1BCh]
0x1401c485f  test    al, 8
0x1401c4861  jz      short loc_1401C48B2
0x1401c4863  test    al, 10h
0x1401c4865  jz      short loc_1401C48B2
0x1401c4867  mov     ecx, 1
0x1401c486c  call    cs:__imp_WdLogSingleEntry0
0x1401c4873  nop     dword ptr [rax+rax+00h]
0x1401c4878  mov     [rsp+180h+var_140], r15
0x1401c487d  lea     r9, aIssoftgpuIswar; "!(IsSoftGPU() && IsWarpAdapter())"
0x1401c4884  mov     [rsp+180h+var_148], r15
0x1401c4889  mov     eax, 1BF6h
0x1401c488e  mov     [rsp+180h+var_150], r15
0x1401c4893  mov     r8d, r13d
0x1401c4896  mov     [rsp+180h+var_158], r15; void *
0x1401c489b  mov     edx, 40002h
0x1401c48a0  xor     ecx, ecx
0x1401c48a2  mov     [rsp+180h+var_160], rax
0x1401c48a7  mov     cs:WdLogGlobalForLineNumber, eax
0x1401c48ad  call    DxgkLogInternalTriageEvent
0x1401c48b2  cmp     [rsi+1C8h], r15
0x1401c48b9  jnz     short loc_1401C4910
0x1401c48bb  mov     ecx, 2
0x1401c48c0  call    cs:__imp_WdLogSingleEntry0
0x1401c48c7  nop     dword ptr [rax+rax+00h]
0x1401c48cc  mov     [rsp+180h+var_140], r15
0x1401c48d1  lea     r9, aMiniportDidNot_2; "Miniport did not provide required DDIs"
0x1401c48d8  mov     [rsp+180h+var_148], r15
0x1401c48dd  mov     eax, 1BFDh
0x1401c48e2  mov     [rsp+180h+var_150], r15
0x1401c48e7  mov     r8d, r13d
0x1401c48ea  mov     [rsp+180h+var_158], r15
0x1401c48ef  mov     [rsp+180h+var_160], rax
0x1401c48f4  mov     cs:WdLogGlobalForLineNumber, eax
0x1401c48fa  mov     edx, 40000h
0x1401c48ff  xor     ecx, ecx
0x1401c4901  call    DxgkLogInternalTriageEvent
0x1401c4906  mov     eax, 0C0000059h
0x1401c490b  jmp     loc_1401C6CC9
0x1401c4910  cmp     [rsi+250h], r15
0x1401c4917  jnz     short loc_1401C4927
0x1401c4919  lea     rax, ?DefaultDdiEscape@DXGADAPTER@@CAJQEAXPEBU_DXGKARG_ESCAPE@@@Z; DXGADAPTER::DefaultDdiEscape(void * const,_DXGKARG_ESCAPE const *)
0x1401c4920  mov     [rsi+250h], rax
0x1401c4927  cmp     [rsi+438h], r15
0x1401c492e  jnz     short loc_1401C493E
0x1401c4930  lea     rax, W32kStub_GreSfmOpenTokenEvent
0x1401c4937  mov     [rsi+438h], rax
0x1401c493e  lea     rbx, [rsi+8A0h]
0x1401c4945  mov     rcx, rsi; this
0x1401c4948  mov     [rsp+180h+var_160], rbx; void *
0x1401c494d  call    ?CallDriverQueryInterface@DXGADAPTER@@QEAAJPEBU_GUID@@GGPEAX1@Z; DXGADAPTER::CallDriverQueryInterface(_GUID const *,ushort,ushort,void *,void *)
0x1401c4952  movsxd  r14, eax
  ... truncated ...
```
