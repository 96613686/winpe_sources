# ClassDeviceControl

- ea: `0x140019de0`
- end: `0x14001c9cc`
- name: `ClassDeviceControl`
- size: `11244`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `66`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140001130`
- `0x140005190`
- `0x14000cab0`
- `0x14000f3e0`
- `0x140012a00`
- `0x140013000`
- `0x140013240`
- `0x1400134a0`
- `0x140014418`
- `0x14001522c`
- `0x1400157d0`
- `0x140017630`
- `0x140019de0`
- `0x14001e86c`
- `0x14001ecc0`
- `0x14001fbf4`
- `0x14001fc38`
- `0x14001feac`
- `0x140020278`
- `0x14002249c`
- `0x140022514`
- `0x140022614`
- `0x140026b94`
- `0x140026bf0`
- `0x140026c84`
- `0x14002a47c`
- `0x14002a8d0`
- `0x14002b2d4`
- `0x14002cf20`
- `0x14002d800`
- `0x14002e3f0`
- `0x14002f308`
- `0x14002f7f4`
- `0x14002f9fc`
- `0x14002fdd8`
- `0x140030338`
- `0x140030604`
- `0x140030be8`
- `0x1400319bc`
- `0x140031d6c`
- `0x1400320dc`
- `0x140032444`
- `0x1400327ac`
- `0x140032d74`
- `0x140033924`
- `0x140033d94`
- `0x1400340b4`
- `0x1400344a8`
- `0x1400347bc`
- `0x140034e08`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b219`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b219`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001c3e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001c837`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001c3e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001c837`
- `ntoskrnl!IoSetActivityIdIrp` at `0x14001af21`
- `ntoskrnl!IoSetActivityIdIrp` at `0x14001af21`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14001c417`
- `ntoskrnl!KeSetEvent` at `0x14001b2d4`
- `ntoskrnl!KeSetEvent` at `0x14001b2d4`
- `ntoskrnl!ExAllocatePool2` at `0x140019f4f`
- `ntoskrnl!ExAllocatePool2` at `0x14001bd6d`
- `ntoskrnl!ExAllocatePool2` at `0x14001bee6`
- `ntoskrnl!ExAllocatePool2` at `0x14001c374`
- `ntoskrnl!ExAllocatePool2` at `0x140019f4f`
- `ntoskrnl!ExAllocatePool2` at `0x14001bd6d`
- `ntoskrnl!ExAllocatePool2` at `0x14001bee6`
- `ntoskrnl!ExAllocatePool2` at `0x14001c374`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001c3f4`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001c3f4`
- `ntoskrnl!IoAllocateIrp` at `0x14001ae32`
- `ntoskrnl!IoAllocateIrp` at `0x14001ae32`
- `ntoskrnl!IofCallDriver` at `0x14001a149`
- `ntoskrnl!IofCallDriver` at `0x14001c102`
- `ntoskrnl!IofCallDriver` at `0x14001c952`
- `ntoskrnl!IofCallDriver` at `0x14001a149`
- `ntoskrnl!IofCallDriver` at `0x14001c102`
- `ntoskrnl!IofCallDriver` at `0x14001c952`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a165`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a189`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a26e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a31a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a391`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a4e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a558`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a708`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a72e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a754`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ad9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ae5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b1eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b2a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b4a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b780`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b901`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b9f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bceb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bdfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bf92`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c4a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c4d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a165`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a189`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a26e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a31a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a391`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a4e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a558`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a708`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a72e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a754`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ad9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ae5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b1eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b2a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b4a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b780`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b901`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b9f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bceb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bdfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bf92`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c4a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c4d6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b23f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b23f`
- `ntoskrnl!ZwClose` at `0x14001c896`
- `ntoskrnl!ZwClose` at `0x14001c896`
- `ntoskrnl!ZwOpenKey` at `0x14001c874`
- `ntoskrnl!ZwOpenKey` at `0x14001c874`
- `ntoskrnl!RtlCompareMemory` at `0x14001a1d8`
- `ntoskrnl!RtlCompareMemory` at `0x14001a1d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b2e0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b2e0`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14001bc89`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14001bc89`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14001c4c5`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14001c4c5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001be2f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001be2f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140019e45`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140019e45`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001bc6f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001bc6f`
- `ntoskrnl!IoIs32bitProcess` at `0x14001c688`
- `ntoskrnl!IoIs32bitProcess` at `0x14001c794`
- `ntoskrnl!IoIs32bitProcess` at `0x14001c688`
- `ntoskrnl!IoIs32bitProcess` at `0x14001c794`
- `ntoskrnl!IofCompleteRequest` at `0x14001c622`
- `ntoskrnl!IofCompleteRequest` at `0x14001c622`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001a8df`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001aaf3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001bfef`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001c6df`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001c93f`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001a8df`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001aaf3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001bfef`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001c6df`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001c93f`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14001be15`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14001be15`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14001b921`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14001b921`

## string_xrefs

- `0x14001c3b4`: `RtlQueryRegistryValuesEx`
- `0x14001c811`: `\Registry\Machine\System\CurrentControlSet\Control\MiniNT`
- `0x14001c410`: `\Registry\Machine\System\DISK`
- `0x14001c4bc`: `\Registry\Machine\System\DISK`
- `0x14001ba73`: `WriteCacheEnableOverride`

## pseudocode

```c
NTSTATUS __stdcall ClassDeviceControl(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // r12
  PIRP v3; // rbx
  struct _FUNCTIONAL_DEVICE_EXTENSION *DeviceExtension; // r14
  PDEVICE_OBJECT v5; // r15
  __int64 v6; // rdi
  __int64 Pool2; // rsi
  int v8; // r13d
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  _STORAGE_ADAPTER_DESCRIPTOR *AdapterDescriptor; // rax
  unsigned __int8 AddressType; // al
  unsigned int v13; // edi
  int LBProvisioningResources; // edi
  _STORAGE_ADAPTER_DESCRIPTOR *v15; // rax
  int v16; // eax
  unsigned int v17; // r9d
  __int64 IoctlStr; // rax
  __int64 v19; // r8
  int v20; // edx
  int v21; // r9d
  PIRP v22; // rdx
  struct _DEVICE_OBJECT *v23; // rcx
  NTSTATUS DiskByPassIOProperty; // eax
  _IO_STACK_LOCATION *v25; // rax
  _IRP *v26; // rdi
  unsigned int v27; // r12d
  _IO_STACK_LOCATION *v28; // rax
  __int64 Blink_high; // rdx
  unsigned int Status; // ecx
  _IO_STACK_LOCATION *v31; // rcx
  _FUNCTIONAL_DEVICE_EXTENSION *v32; // rdx
  _IRP *v33; // r8
  unsigned int PartitionNumber; // eax
  _FUNCTIONAL_DEVICE_EXTENSION *PartitionZeroExtension; // rdx
  _IRP *v36; // r8
  unsigned int DeviceNumber; // r9d
  _IO_STACK_LOCATION *v38; // rax
  int v39; // ecx
  NTSTATUS InfoProcess; // eax
  bool v41; // zf
  _IO_STACK_LOCATION *v42; // rax
  _IRP *v43; // rcx
  void *v44; // rcx
  _IRP *v45; // rsi
  _IO_STACK_LOCATION *v46; // rdx
  __int64 v47; // rax
  _IO_STACK_LOCATION *v48; // rax
  __int64 v49; // r9
  _DWORD **v50; // r8
  signed __int32 v51; // eax
  signed __int32 v52; // ett
  _IRP *v53; // r12
  int v54; // eax
  __int64 v55; // rax
  _IO_STACK_LOCATION *v56; // r14
  _BYTE *v57; // r13
  unsigned int v58; // ecx
  int v59; // ecx
  _DWORD **v60; // r8
  signed __int32 v61; // eax
  signed __int32 v62; // ett
  _IO_STACK_LOCATION *v63; // rcx
  void *v64; // rax
  __int64 v65; // r12
  _IRP *v66; // r14
  signed __int32 v67; // eax
  signed __int32 v68; // ett
  _DWORD *v69; // r14
  PIRP v70; // rax
  PIRP v71; // rdi
  _ETHREAD *Thread; // rax
  _IO_STACK_LOCATION *v73; // rax
  _IO_STACK_LOCATION *v74; // rax
  bool v75; // sf
  _IO_STACK_LOCATION *v76; // rcx
  _IO_STACK_LOCATION *v77; // rax
  unsigned int v78; // r11d
  __int64 i; // r9
  __int64 v80; // rcx
  unsigned __int64 v81; // rdx
  __int64 v82; // r10
  __int64 v83; // r8
  int v84; // ecx
  int v85; // ecx
  unsigned __int64 v86; // rcx
  _BYTE *v87; // r11
  unsigned int v88; // edi
  __int64 v89; // r10
  __int64 v90; // rcx
  unsigned __int64 v91; // rdx
  __int64 v92; // r9
  __int64 v93; // r8
  int v94; // ecx
  int v95; // ecx
  unsigned __int64 v96; // rcx
  char v97; // cl
  int v98; // eax
  _DWORD *v99; // r14
  char v100; // dl
  unsigned int v101; // r11d
  __int64 k; // r9
  __int64 v103; // rcx
  unsigned __int64 v104; // rdx
  __int64 v105; // r10
  __int64 v106; // r8
  int v107; // ecx
  int v108; // ecx
  char *v109; // r14
  unsigned int v110; // r11d
  unsigned int j; // r9d
  __int64 v112; // rcx
  unsigned __int64 v113; // rdx
  __int64 v114; // r10
  __int64 v115; // r8
  int v116; // ecx
  int v117; // ecx
  unsigned __int64 v118; // rcx
  _BYTE *v119; // r11
  unsigned int v120; // edi
  unsigned int v121; // r10d
  __int64 v122; // rcx
  unsigned __int64 v123; // rdx
  __int64 v124; // r9
  __int64 v125; // r8
  int v126; // ecx
  int v127; // ecx
  unsigned __int64 v128; // rcx
  char v129; // cl
  char v130; // al
  char v131; // cl
  char v132; // al
  int v133; // eax
  _IRP *v134; // rdi
  NTSTATUS v135; // eax
  unsigned __int64 v136; // rcx
  _BYTE *v137; // r11
  unsigned int v138; // edi
  __int64 v139; // r10
  __int64 v140; // rcx
  unsigned __int64 v141; // rdx
  __int64 v142; // r9
  __int64 v143; // r8
  int v144; // ecx
  int v145; // ecx
  unsigned __int64 v146; // rcx
  unsigned int v147; // r8d
  char v148; // al
  unsigned int v149; // r11d
  __int64 m; // r9
  __int64 v151; // rcx
  unsigned __int64 v152; // rdx
  __int64 v153; // r10
  __int64 v154; // r8
  int v155; // ecx
  int v156; // ecx
  unsigned __int64 v157; // rcx
  unsigned int v158; // edi
  __int64 v159; // r10
  __int64 v160; // rcx
  unsigned __int64 v161; // rdx
  __int64 v162; // r9
  __int64 v163; // r8
  int v164; // ecx
  int v165; // ecx
  unsigned __int64 v166; // rcx
  char v167; // cl
  int v168; // eax
  __int64 v169; // rcx
  void *v170; // r13
  _IRP *v171; // r14
  _BYTE *v172; // rsi
  __int64 v173; // rdx
  __int64 v174; // r8
  _IRP *v175; // r14
  ULONG_PTR v176; // rax
  signed __int32 v177; // eax
  signed __int32 v178; // ett
  _CLASS_PRIVATE_FDO_DATA *PrivateFdoData; // rdx
  _IRP *v180; // rsi
  unsigned __int8 v181; // al
  _IRP *v182; // rdi
  unsigned int v183; // eax
  __int64 MdlAddress_high; // r12
  __int64 Flags; // r9
  __int64 v186; // r8
  __int64 IrpCount; // rdx
  _CLASS_PRIVATE_FDO_DATA *v188; // r13
  int v189; // eax
  unsigned int v190; // eax
  unsigned int v191; // eax
  unsigned int v192; // eax
  int v193; // eax
  _SLIST_ENTRY **v194; // r13
  unsigned __int64 v195; // r10
  _SLIST_ENTRY *p_PageFilesInfo; // rdx
  _SLIST_ENTRY *Next; // rcx
  _SLIST_ENTRY *v198; // rax
  __int64 v199; // r11
  char *v200; // rcx
  __int64 v201; // r8
  __int64 v202; // r9
  unsigned __int64 v203; // rdx
  __int64 v204; // rax
  _SLIST_ENTRY *v205; // r12
  _CLASS_PRIVATE_FDO_DATA *v206; // rdx
  _SLIST_ENTRY *v207; // rdx
  _SLIST_ENTRY *v208; // rcx
  _SLIST_ENTRY *v209; // rax
  _QWORD *v210; // r9
  __int64 v211; // rcx
  unsigned __int64 v212; // r8
  unsigned __int64 v213; // rax
  unsigned __int64 v214; // rdi
  PVOID v215; // r8
  unsigned int v216; // r14d
  int v217; // r13d
  unsigned __int64 v218; // rax
  int v219; // r12d
  _DWORD **v220; // r8
  signed __int32 v221; // eax
  signed __int32 v222; // ett
  NTSTATUS LBAStatus; // eax
  _IO_STACK_LOCATION *v224; // rax
  char v225; // r14
  PIRP v226; // rdx
  struct _DEVICE_OBJECT *v227; // rcx
  _IO_STACK_LOCATION *v228; // rax
  bool v229; // cf
  void *v230; // rax
  void *v231; // rsi
  PVOID SystemRoutineAddress; // rax
  _IRP *v233; // rdi
  _IRP *v234; // rsi
  __int64 v235; // rax
  size_t v236; // r8
  wchar_t *Buffer; // rdx
  __int64 Length; // rax
  int v239; // ecx
  BOOLEAN v240; // al
  unsigned int Options; // ecx
  _DWORD **v242; // r8
  signed __int32 v243; // eax
  signed __int32 v244; // ett
  signed __int32 v245; // eax
  signed __int32 v246; // ett
  _IO_STACK_LOCATION *v247; // rsi
  unsigned int LowPart; // ecx
  unsigned __int64 v249; // rax
  __int64 v250; // rdx
  _IRP *MasterIrp; // rdi
  unsigned int v252; // esi
  char v253; // r12
  _BYTE *p_IoStatus; // rax
  _IO_STACK_LOCATION *v255; // rax
  _DWORD **v256; // r8
  signed __int32 v257; // eax
  signed __int32 v258; // ett
  __int64 v259; // rax
  __int64 v260; // r8
  int v261; // edx
  unsigned int v263; // [rsp+40h] [rbp-C0h]
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v265; // [rsp+50h] [rbp-B0h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h]
  int v267[2]; // [rsp+68h] [rbp-98h]
  unsigned __int64 v268; // [rsp+70h] [rbp-90h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  int v270[2]; // [rsp+88h] [rbp-78h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  __int128 v272; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v273; // [rsp+D0h] [rbp-30h]
  __int128 v274; // [rsp+E0h] [rbp-20h]
  __int128 v275; // [rsp+F0h] [rbp-10h]
  __int128 v276; // [rsp+100h] [rbp+0h]
  __int128 v277; // [rsp+110h] [rbp+10h]
  __int128 v278; // [rsp+120h] [rbp+20h]
  __int128 v279; // [rsp+130h] [rbp+30h] BYREF
  __int128 v280; // [rsp+140h] [rbp+40h] BYREF
  int v281; // [rsp+150h] [rbp+50h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v3 = Irp;
  DeviceExtension = (struct _FUNCTIONAL_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
  v5 = DeviceObject;
  *(_QWORD *)&DestinationString.Length = Irp;
  *(_QWORD *)&v265.Length = DeviceObject;
  LODWORD(v6) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  Pool2 = 0;
  LODWORD(P) = v6;
  v279 = 0;
  v263 = 0;
  v8 = 0;
  LODWORD(KeyHandle) = IoGetActivityIdIrp(Irp, &v279);
  if ( (int)KeyHandle >= 0 )
    v8 = (unsigned __int8)ClassPnPETWEnabled;
  v9 = 0x11000000000001LL;
  if ( (_DWORD)v6 == 315396 || (v10 = (unsigned int)(v6 - 315412), (unsigned int)v10 <= 0x34) && _bittest64(&v9, v10) )
  {
    if ( v8 && SBYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) < 0 )
      McTemplateK0qpddd_EtwWriteTransfer(
        CurrentStackLocation->MajorFunction,
        (unsigned int)EventPassThrough,
        (unsigned int)&v279,
        DeviceExtension->DeviceNumber,
        (char)v3,
        CurrentStackLocation->MajorFunction,
        CurrentStackLocation->MinorFunction,
        v6);
    if ( (((_DWORD)v6 - 315396) & 0xFFFFFFEF) == 0 )
    {
      v240 = IoIs32bitProcess(v3);
      Options = CurrentStackLocation->Parameters.Create.Options;
      if ( v240 )
      {
        if ( Options < 0x2C )
        {
          LBProvisioningResources = -1073741811;
          v3->IoStatus.Status = -1073741811;
          v242 = (_DWORD **)v5->DeviceExtension;
          v243 = *v242[55];
          while ( v243 )
          {
            v244 = v243;
            v243 = _InterlockedCompareExchange(v242[55], v243 - 1, v243);
            if ( v244 == v243 )
              goto LABEL_686;
          }
LABEL_685:
          ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v242[55] + 2));
LABEL_686:
          ClassCompleteRequest(v5, v3, 0);
          goto LABEL_726;
        }
      }
      else if ( Options < 0x38 )
      {
        LBProvisioningResources = -1073741811;
        v3->IoStatus.Status = -1073741811;
        v242 = (_DWORD **)v5->DeviceExtension;
        v245 = *v242[55];
        if ( v245 )
        {
          while ( 1 )
          {
            v246 = v245;
            v245 = _InterlockedCompareExchange(v242[55], v245 - 1, v245);
            if ( v246 == v245 )
              goto LABEL_686;
            if ( !v245 )
              goto LABEL_685;
          }
        }
        goto LABEL_685;
      }
    }
    v247 = v3->Tail.Overlay.CurrentStackLocation;
    LowPart = v247->Parameters.Read.ByteOffset.LowPart;
    if ( LowPart == 315396
      || (v249 = LowPart - 315412, (unsigned int)v249 <= 0x34) && (v250 = 0x11000000000001LL, _bittest64(&v250, v249)) )
    {
      MasterIrp = v3->AssociatedIrp.MasterIrp;
      if ( MasterIrp )
      {
        v252 = v247->Parameters.Create.Options;
        if ( LowPart == 315460 || (v253 = 1, LowPart == 315464) )
          v253 = 0;
        if ( IoIs32bitProcess(v3) )
        {
          if ( v253 )
          {
            if ( v252 < 0x2C )
              goto LABEL_716;
            p_IoStatus = (char *)&MasterIrp->AssociatedIrp.SystemBuffer + 4;
          }
          else
          {
            if ( v252 < 0x34 )
              goto LABEL_716;
            p_IoStatus = &MasterIrp->IoStatus;
          }
        }
        else if ( v253 )
        {
          if ( v252 < 0x38 )
            goto LABEL_716;
          p_IoStatus = (char *)&MasterIrp->ThreadListEntry.Flink + 4;
        }
        else
        {
          if ( v252 < 0x40 )
            goto LABEL_716;
          p_IoStatus = &MasterIrp->IoStatus.Information;
        }
        if ( p_IoStatus && *p_IoStatus == 72 && DeviceExtension->PrivateFdoData->IsBootDevice )
        {
          KeyHandle = 0;
          v265 = 0;
          memset(&ObjectAttributes, 0, 44);
          RtlInitUnicodeString(&v265, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MiniNT");
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &v265;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
          {
            LBProvisioningResources = -1073741637;
            v3->IoStatus.Status = -1073741637;
            goto LABEL_476;
          }
          ZwClose(KeyHandle);
        }
      }
    }
LABEL_716:
    if ( v8 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 4) != 0 )
      McTemplateK0qpd_EtwWriteTransfer(
        LowPart,
        (unsigned int)EventNonReadWriteRequestComplete,
        (unsigned int)&v279,
        DeviceExtension->DeviceNumber,
        (char)v3,
        v3->IoStatus.Status);
    v255 = v3->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v255[-1].MajorFunction = *(_OWORD *)&v255->MajorFunction;
    *(_OWORD *)&v255[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v255->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v255[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v255->Parameters.SetQuota + 6);
    v255[-1].FileObject = v255->FileObject;
    v255[-1].Control = 0;
    v3->Tail.Overlay.CurrentStackLocation[-1].MinorFunction = 1;
    v256 = (_DWORD **)v5->DeviceExtension;
    v257 = *v256[55];
    if ( v257 )
    {
      while ( 1 )
      {
        v258 = v257;
        v257 = _InterlockedCompareExchange(v256[55], v257 - 1, v257);
        if ( v258 == v257 )
          break;
        if ( !v257 )
          goto LABEL_722;
      }
    }
    else
    {
LABEL_722:
      ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v256[55] + 2));
    }
    goto LABEL_723;
  }
  v3->IoStatus.Information = 0;
  if ( v8 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 1) != 0 )
    McTemplateK0qpddd_EtwWriteTransfer(
      CurrentStackLocation->MajorFunction,
      (unsigned int)EventIOCTL,
      (unsigned int)&v279,
      DeviceExtension->DeviceNumber,
      (char)v3,
      CurrentStackLocation->MajorFunction,
      CurrentStackLocation->MinorFunction,
      v6);
  if ( (_DWORD)v6 == 5046272 )
  {
    if ( !DeviceExtension->CommonExtension.MountedDeviceInterfaceName.Buffer )
    {
      LBProvisioningResources = -1073741811;
      goto LABEL_672;
    }
    if ( CurrentStackLocation->Parameters.Read.Length < 4 )
    {
      LBProvisioningResources = -1073741789;
      v3->IoStatus.Information = 4;
      goto LABEL_672;
    }
    v234 = v3->AssociatedIrp.MasterIrp;
    *(_DWORD *)&v234->Type = 0;
    Length = DeviceExtension->CommonExtension.MountedDeviceInterfaceName.Length;
    v234->Type = Length;
    v236 = (unsigned int)Length;
    if ( CurrentStackLocation->Parameters.Read.Length < (unsigned __int64)(Length + 2) )
    {
      LBProvisioningResources = -2147483643;
      v3->IoStatus.Information = 4;
      goto LABEL_672;
    }
    Buffer = DeviceExtension->CommonExtension.MountedDeviceInterfaceName.Buffer;
    goto LABEL_671;
  }
  if ( (_DWORD)v6 == 5046280 )
  {
    if ( CurrentStackLocation->Parameters.Read.Length < 4 )
    {
      LBProvisioningResources = -1073741789;
      v3->IoStatus.Information = 4;
      goto LABEL_672;
    }
    v234 = v3->AssociatedIrp.MasterIrp;
    *(_DWORD *)&v234->Type = 0;
    v235 = DeviceExtension->CommonExtension.DeviceName.Length;
    v234->Type = v235;
    v236 = (unsigned int)v235;
    if ( CurrentStackLocation->Parameters.Read.Length < (unsigned __int64)(v235 + 2) )
    {
      LBProvisioningResources = -2147483643;
      v3->IoStatus.Information = 4;
      goto LABEL_672;
    }
    Buffer = DeviceExtension->CommonExtension.DeviceName.Buffer;
LABEL_671:
    memmove(&v234->Size, Buffer, v236);
    LBProvisioningResources = 0;
    v3->IoStatus.Information = (unsigned __int16)v234->Type + 2LL;
    goto LABEL_672;
  }
  if ( (_DWORD)v6 != 5046284 )
  {
    if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
    {
      AdapterDescriptor = DeviceExtension->AdapterDescriptor;
      if ( AdapterDescriptor && AdapterDescriptor->SrbType == 1 )
      {
        AddressType = AdapterDescriptor->AddressType;
        v13 = 308;
        if ( AddressType != 1 )
          v13 = 184;
        LODWORD(v268) = AddressType == 1;
      }
      else
      {
        v13 = 88;
        LOWORD(v268) = 0;
      }
      *(_QWORD *)v267 = v13;
      Pool2 = ExAllocatePool2(64, v13 + 16LL, 960717651);
      if ( !Pool2 )
      {
        LBProvisioningResources = -1073741670;
        v3->IoStatus.Status = -1073741670;
        ClassReleaseRemoveLock(v5, v3);
        ClassCompleteRequest(v5, v3, 0);
LABEL_725:
        LODWORD(Pool2) = v263;
        goto LABEL_726;
      }
      v15 = DeviceExtension->AdapterDescriptor;
      if ( v15 && v15->SrbType == 1 )
      {
        LBProvisioningResources = InitializeStorageRequestBlock(Pool2, (unsigned __int16)v268, v13, 1, 64);
        if ( LBProvisioningResources < 0 )
          goto LABEL_725;
        v10 = Pool2 + *(_QWORD *)v267;
        *(_DWORD *)(Pool2 + 20) = 0;
      }
      else
      {
        *(_WORD *)Pool2 = 88;
        v10 = Pool2 + 88;
        *(_BYTE *)(Pool2 + 2) = 0;
      }
      v6 = (unsigned int)P;
      *(_QWORD *)v10 = v5;
      *(_QWORD *)(v10 + 8) = v6;
    }
    v16 = v6 & 0xFFFF0000;
    if ( (v6 & 0xFFFF0000) == 0x70000 || v16 == 2031616 || v16 == 0x20000 )
      v17 = (unsigned __int16)v6 | 0x2D0000;
    else
      v17 = v6;
    v263 = v17;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      IoctlStr = DbgGetIoctlStr(v17, v9);
      WPP_SF_Ds(*(_QWORD *)(v19 + 24), v20, v19, v21, IoctlStr);
    }
    if ( v8 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 1) != 0 )
      McTemplateK0qpddd_EtwWriteTransfer(
        CurrentStackLocation->MajorFunction,
        (unsigned int)EventIOCTL,
        (unsigned int)&v279,
        DeviceExtension->DeviceNumber,
        (char)v3,
        CurrentStackLocation->MajorFunction,
        CurrentStackLocation->MinorFunction,
        v263);
    if ( v263 <= 0x2D4800 )
    {
      if ( v263 == 2967552 )
      {
LABEL_231:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 153, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
        }
        LODWORD(v10) = CurrentStackLocation->Parameters.Read.Length;
        if ( (unsigned int)(v10 - 1) <= 2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 154, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
          }
          v3->IoStatus.Information = 4;
          LBProvisioningResources = -1073741789;
          v3->IoStatus.Status = -1073741789;
          if ( Pool2 )
            ExFreePoolWithTag((PVOID)Pool2, 0);
          goto LABEL_332;
        }
        if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) == 0 )
          goto LABEL_244;
        v69 = v5->DeviceExtension;
        if ( (_DWORD)v10 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 155, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
          }
          v70 = IoAllocateIrp(v5->StackSize + 3, 0);
          v71 = v70;
          if ( !v70 )
          {
            v3->IoStatus.Information = 0;
            LBProvisioningResources = -1073741670;
            v3->IoStatus.Status = -1073741670;
            if ( Pool2 )
              ExFreePoolWithTag((PVOID)Pool2, 0);
            goto LABEL_332;
          }
          ClassAcquireRemoveLockEx(v5, v70, "minkernel\\storage\\classpnp\\class.c", 0x26CFu);
          Thread = v3->Tail.Overlay.Thread;
          --v71->Tail.Overlay.CurrentStackLocation;
          --v71->CurrentLocation;
          v71->Tail.Overlay.Thread = Thread;
          v73 = v71->Tail.Overlay.CurrentStackLocation;
          v73->Parameters.WMI.ProviderId = (unsigned __int64)v3;
          v73->DeviceObject = v5;
          v74 = v71->Tail.Overlay.CurrentStackLocation;
          v74[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))ClassCheckVerifyComplete;
          v74[-1].Context = 0;
          v74[-1].Control = -32;
          --v71->Tail.Overlay.CurrentStackLocation;
          --v71->CurrentLocation;
          v75 = (int)KeyHandle < 0;
          v76 = v71->Tail.Overlay.CurrentStackLocation;
          v76->DeviceObject = v5;
          v76->MajorFunction = CurrentStackLocation->MajorFunction;
          v76->MinorFunction = CurrentStackLocation->MinorFunction;
          v76->Flags = CurrentStackLocation->Flags;
          if ( !v75 )
            IoSetActivityIdIrp(v71, &v279);
          v77 = v3->Tail.Overlay.CurrentStackLocation;
          v3 = v71;
          v77->Control |= 1u;
        }
        if ( *(_BYTE *)(Pool2 + 2) == 40 )
        {
          if ( !*(_DWORD *)(Pool2 + 20) )
          {
            v78 = *(_DWORD *)(Pool2 + 56);
            for ( i = 0; (unsigned int)i < v78; i = (unsigned int)(i + 1) )
            {
              v80 = *(unsigned int *)(Pool2 + 4 * i + 120);
              if ( (unsigned int)v80 < 0x80 )
                continue;
              v81 = *(unsigned int *)(Pool2 + 16);
              if ( (unsigned int)v80 >= (unsigned int)v81 )
                continue;
              v82 = v80 + Pool2;
              v83 = (unsigned int)v80;
              v84 = *(_DWORD *)(v80 + Pool2) - 64;
              if ( v84 )
              {
                v85 = v84 - 1;
                if ( v85 )
                {
                  if ( v85 == 1 && v83 + 40 <= v81 )
                    break;
                  continue;
                }
                v86 = v83 + 56;
              }
              else
              {
                v86 = v83 + 40;
              }
              if ( v86 <= v81 )
              {
                *(_BYTE *)(v82 + 10) = 6;
                break;
              }
            }
          }
        }
        else
        {
          *(_BYTE *)(Pool2 + 10) = 6;
        }
        if ( *(_BYTE *)(Pool2 + 2) != 40 )
        {
          v87 = (_BYTE *)(Pool2 + 72);
          goto LABEL_296;
        }
        v87 = 0;
        if ( !*(_DWORD *)(Pool2 + 20) )
        {
          v88 = *(_DWORD *)(Pool2 + 56);
          if ( v88 )
          {
            v89 = 0;
            do
            {
              v90 = *(unsigned int *)(Pool2 + 4 * v89 + 120);
              if ( (unsigned int)v90 < 0x80 )
                goto LABEL_291;
              v91 = *(unsigned int *)(Pool2 + 16);
              if ( (unsigned int)v90 >= (unsigned int)v91 )
                goto LABEL_291;
              v92 = v90 + Pool2;
              v93 = (unsigned int)v90;
              v94 = *(_DWORD *)(v90 + Pool2) - 64;
              if ( v94 )
              {
                v95 = v94 - 1;
                if ( v95 )
                {
                  if ( v95 == 1 && v93 + 40 <= v91 )
                  {
                    if ( *(_DWORD *)(v92 + 12) )
                      v87 = (_BYTE *)(v92 + 32);
                    break;
                  }
                  goto LABEL_291;
                }
                v96 = v93 + 56;
              }
              else
              {
                v96 = v93 + 40;
              }
              if ( v96 <= v91 )
              {
                if ( *(_BYTE *)(v92 + 10) )
                  v87 = (_BYTE *)(v92 + 24);
                break;
              }
LABEL_291:
              v89 = (unsigned int)(v89 + 1);
            }
            while ( (unsigned int)v89 < v88 );
          }
        }
LABEL_296:
        *v87 = 0;
        v97 = *(_BYTE *)(Pool2 + 2);
        v98 = v69[146];
        if ( v97 == 40 )
          *(_DWORD *)(Pool2 + 40) = v98;
        else
          *(_DWORD *)(Pool2 + 20) = v98;
        if ( (_DWORD)P == 2951168 )
        {
          if ( v97 == 40 )
            *(_DWORD *)(Pool2 + 24) |= 0x10000000u;
          else
            *(_DWORD *)(Pool2 + 12) |= 0x10000000u;
        }
        goto LABEL_303;
      }
      if ( v263 <= 0x2D13F8 )
      {
        if ( v263 != 2954232 )
        {
          if ( v263 <= 0x2D0940 )
          {
            if ( v263 != 2951488 )
            {
              if ( v263 == 315400 )
              {
                v26 = v3->AssociatedIrp.MasterIrp;
                v27 = CurrentStackLocation->Parameters.Create.Options;
                if ( Pool2 )
                  ExFreePoolWithTag((PVOID)Pool2, 0);
                v28 = v3->Tail.Overlay.CurrentStackLocation;
                *(_OWORD *)&v28[-1].MajorFunction = *(_OWORD *)&v28->MajorFunction;
                *(_OWORD *)&v28[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v28->Parameters.NotifyDirectoryEx.CompletionFilter;
                *(_OWORD *)(&v28[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v28->Parameters.SetQuota + 6);
                v28[-1].FileObject = v28->FileObject;
                v28[-1].Control = 0;
                if ( v27 >= 0x7C
                  && (unsigned int)RtlCompareMemory(&v26->Size + 1, "HYBRDISK", 8u) == 8
                  && *(_DWORD *)&v26->Type == 28
                  && HIDWORD(v26->ThreadListEntry.Flink) == 1 )
                {
                  Blink_high = HIDWORD(v26->ThreadListEntry.Blink);
                  Status = v26->IoStatus.Status;
                  if ( Status + (unsigned int)Blink_high <= v27 && (unsigned int)Blink_high <= v27 && Status <= v27 )
                  {
                    v31 = v3->Tail.Overlay.CurrentStackLocation;
                    v31[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))ClasspMiniportGetHybridInfoIoctlCompletion;
                    v31[-1].Context = (char *)v26 + Blink_high;
                    v31[-1].Control = -32;
                  }
                }
                ClassReleaseRemoveLock(v5, v3);
                goto LABEL_723;
              }
              if ( v263 != 2951168 )
              {
                if ( v263 != 2951180 )
                {
                  if ( v263 == 2951360 )
                  {
                    v22 = v3;
                    v23 = v5;
                    if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
                    {
                      DiskByPassIOProperty = ClasspDeviceManageBypassIO(v5, v3);
LABEL_53:
                      LBProvisioningResources = DiskByPassIOProperty;
                      goto LABEL_54;
                    }
                    goto LABEL_51;
                  }
                  goto LABEL_631;
                }
LABEL_324:
                if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
                {
                  if ( DeviceExtension->CommonExtension.PagingPathCount )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                    {
                      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 158, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
                    }
                    v3->IoStatus.Information = 0;
                    LBProvisioningResources = -1073741561;
                    v3->IoStatus.Status = -1073741561;
                    if ( Pool2 )
                      ExFreePoolWithTag((PVOID)Pool2, 0);
LABEL_332:
                    ClassReleaseRemoveLock(v5, v3);
                    ClassCompleteRequest(v5, v3, 0);
                    goto LABEL_725;
                  }
                  v109 = (char *)v5->DeviceExtension;
                  KeEnterCriticalRegion();
                  KeWaitForSingleObject(v109 + 616, UserRequest, 0, 0, 0);
                  if ( *((_DWORD *)v109 + 151) )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                    {
                      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 159, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
                    }
                    v3->IoStatus.Information = 0;
                    LBProvisioningResources = -2147483631;
                    v3->IoStatus.Status = -2147483631;
                    if ( Pool2 )
                      ExFreePoolWithTag((PVOID)Pool2, 0);
                    ClassReleaseRemoveLock(v5, v3);
                    ClassCompleteRequest(v5, v3, 0);
LABEL_341:
                    KeSetEvent((PRKEVENT)(v109 + 616), 0, 0);
                    KeLeaveCriticalRegion();
                    goto LABEL_725;
                  }
                  if ( *(_BYTE *)(Pool2 + 2) == 40 )
                  {
                    if ( !*(_DWORD *)(Pool2 + 20) )
                    {
                      v110 = *(_DWORD *)(Pool2 + 56);
                      for ( j = 0; j < v110; ++j )
                      {
                        v112 = *(unsigned int *)(Pool2 + 4LL * j + 120);
                        if ( (unsigned int)v112 < 0x80 )
                          continue;
                        v113 = *(unsigned int *)(Pool2 + 16);
                        if ( (unsigned int)v112 >= (unsigned int)v113 )
                          continue;
                        v114 = v112 + Pool2;
                        v115 = (unsigned int)v112;
                        v116 = *(_DWORD *)(v112 + Pool2) - 64;
                        if ( v116 )
                        {
                          v117 = v116 - 1;
                          if ( v117 )
                          {
                            if ( v117 == 1 && v115 + 40 <= v113 )
                              break;
                            continue;
                          }
                          v118 = v115 + 56;
                        }
                        else
                        {
                          v118 = v115 + 40;
                        }
                        if ( v118 <= v113 )
                        {
                          *(_BYTE *)(v114 + 10) = 6;
                          break;
                        }
                      }
                    }
                  }
                  else
                  {
                    *(_BYTE *)(Pool2 + 10) = 6;
                  }
                  if ( *(_BYTE *)(Pool2 + 2) != 40 )
                  {
                    v119 = (_BYTE *)(Pool2 + 72);
                    goto LABEL_379;
                  }
                  v119 = 0;
                  if ( *(_DWORD *)(Pool2 + 20) || (v120 = *(_DWORD *)(Pool2 + 56)) == 0 )
                  {
LABEL_379:
                    v129 = v119[4] | 2;
                    *v119 = 27;
                    v130 = v129;
                    v131 = v129 & 0xFE;
                    v132 = v130 | 1;
                    if ( v263 != 2967560 )
                      v131 = v132;
                    v119[4] = v131;
                    v133 = *((_DWORD *)v109 + 146);
                    if ( *(_BYTE *)(Pool2 + 2) == 40 )
                      *(_DWORD *)(Pool2 + 40) = v133;
                    else
                      *(_DWORD *)(Pool2 + 20) = v133;
                    LBProvisioningResources = ClassSendSrbAsynchronous(v5, (PSCSI_REQUEST_BLOCK)Pool2, v3, 0, 0, 0);
                    goto LABEL_341;
                  }
                  v121 = 0;
                  while ( 1 )
                  {
                    v122 = *(unsigned int *)(Pool2 + 4LL * v121 + 120);
                    if ( (unsigned int)v122 < 0x80 )
                      goto LABEL_374;
                    v123 = *(unsigned int *)(Pool2 + 16);
                    if ( (unsigned int)v122 >= (unsigned int)v123 )
                      goto LABEL_374;
                    v124 = v122 + Pool2;
                    v125 = (unsigned int)v122;
                    v126 = *(_DWORD *)(v122 + Pool2) - 64;
                    if ( v126 )
                    {
                      v127 = v126 - 1;
                      if ( v127 )
                      {
                        if ( v127 == 1 && v125 + 40 <= v123 )
                        {
                          if ( *(_DWORD *)(v124 + 12) )
                            v119 = (_BYTE *)(v124 + 32);
                          goto LABEL_379;
                        }
                        goto LABEL_374;
                      }
                      v128 = v125 + 56;
                    }
                    else
                    {
                      v128 = v125 + 40;
                    }
                    if ( v128 <= v123 )
                    {
                      if ( *(_BYTE *)(v124 + 10) )
                        v119 = (_BYTE *)(v124 + 24);
                      goto LABEL_379;
                    }
LABEL_374:
                    if ( ++v121 >= v120 )
                      goto LABEL_379;
                  }
                }
                goto LABEL_244;
              }
              goto LABEL_231;
            }
LABEL_385:
            v134 = v3->AssociatedIrp.MasterIrp;
            LODWORD(v10) = (_DWORD)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 156, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
            }
            if ( Pool2 )
              ExFreePoolWithTag((PVOID)Pool2, 0);
            if ( !CurrentStackLocation->Parameters.Create.Options )
            {
LABEL_392:
              v3->IoStatus.Status = -1073741820;
              ClassReleaseRemoveLock(v5, v3);
              ClassCompleteRequest(v5, v3, 0);
              LBProvisioningResources = -1073741820;
              goto LABEL_725;
            }
            if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
            {
              LODWORD(Pool2) = v263;
              v135 = ClasspEjectionControl(v5, v3, v263 == 2951488, LOBYTE(v134->Type));
              v3->IoStatus.Status = v135;
              LBProvisioningResources = v135;
              ClassReleaseRemoveLock(v5, v3);
              ClassCompleteRequest(v5, v3, 0);
LABEL_726:
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                v259 = DbgGetIoctlStr((unsigned int)Pool2, v9);
                WPP_SF_DsD(*(_QWORD *)(v260 + 24), v261, v260, Pool2, v259, LBProvisioningResources);
              }
              return LBProvisioningResources;
            }
LABEL_88:
            if ( !v8 || (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 4) == 0 )
              goto LABEL_92;
            DeviceNumber = DeviceExtension->DeviceNumber;
            goto LABEL_91;
          }
          if ( v263 != 2951492 )
          {
            switch ( v263 )
            {
              case 0x2D0C14u:
                if ( Pool2 )
                  ExFreePoolWithTag((PVOID)Pool2, 0);
                if ( CurrentStackLocation->Parameters.Read.Length < 8 )
                {
                  LBProvisioningResources = -1073741789;
                  v3->IoStatus.Status = -1073741789;
                  v3->IoStatus.Information = 8;
                  ClassReleaseRemoveLock(v5, v3);
                  ClassCompleteRequest(v5, v3, 0);
                  goto LABEL_725;
                }
                if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
                {
                  *(_STORAGE_HOTPLUG_INFO *)v3->AssociatedIrp.MasterIrp = DeviceExtension->PrivateFdoData->HotplugInfo;
                  v3->IoStatus.Information = 8;
                  v3->IoStatus.Status = 0;
                  ClassReleaseRemoveLock(v5, v3);
                  ClassCompleteRequest(v5, v3, 0);
                  LBProvisioningResources = 0;
                  goto LABEL_725;
                }
                goto LABEL_88;
              case 0x2D1080u:
                if ( Pool2 )
                  ExFreePoolWithTag((PVOID)Pool2, 0);
                if ( CurrentStackLocation->Parameters.Read.Length < 0xC )
                {
                  LBProvisioningResources = -1073741789;
                }
                else
                {
                  PartitionZeroExtension = DeviceExtension->CommonExtension.PartitionZeroExtension;
                  LBProvisioningResources = 0;
                  v36 = v3->AssociatedIrp.MasterIrp;
                  *(_DWORD *)&v36->Type = PartitionZeroExtension->DeviceObject->DeviceType;
                  *(_DWORD *)(&v36->Size + 1) = PartitionZeroExtension->DeviceNumber;
                  LODWORD(v36->MdlAddress) = DeviceExtension->CommonExtension.PartitionNumber;
                }
                v3->IoStatus.Information = 12;
                v3->IoStatus.Status = LBProvisioningResources;
                ClassReleaseRemoveLock(v5, v3);
                ClassCompleteRequest(v5, v3, 0);
                goto LABEL_725;
              case 0x2D1084u:
                if ( Pool2 )
                  ExFreePoolWithTag((PVOID)Pool2, 0);
                if ( CurrentStackLocation->Parameters.Read.Length < 0x28 )
                {
                  LBProvisioningResources = -1073741789;
                }
                else
                {
                  v32 = DeviceExtension->CommonExtension.PartitionZeroExtension;
                  LBProvisioningResources = 0;
                  v33 = v3->AssociatedIrp.MasterIrp;
                  *(_DWORD *)&v33->Type = 40;
                  *(_DWORD *)(&v33->Size + 1) = 40;
                  HIDWORD(v33->MdlAddress) = v32->DeviceObject->DeviceType;
                  v33->Flags = v32->DeviceNumber;
                  PartitionNumber = DeviceExtension->CommonExtension.PartitionNumber;
                  LODWORD(v33->MdlAddress) = 0;
                  HIDWORD(v33->ThreadListEntry.Flink) = PartitionNumber;
                  LODWORD(v33->MdlAddress) = v32->AdditionalFdoData->DeviceGuidFlags;
                  *(_GUID *)(&v33->Flags + 1) = v32->AdditionalFdoData->DeviceGuid;
                }
                v3->IoStatus.Information = 40;
                v3->IoStatus.Status = LBProvisioningResources;
                ClassReleaseRemoveLock(v5, v3);
                ClassCompleteRequest(v5, v3, 0);
                goto LABEL_725;
            }
            goto LABEL_631;
          }
          v39 = (int)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 157, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
          }
          if ( !CurrentStackLocation->Parameters.Create.Options )
          {
            v3->IoStatus.Status = -1073741820;
            v3->IoStatus.Information = 0;
            if ( Pool2 )
              ExFreePoolWithTag((PVOID)Pool2, 0);
            ClassReleaseRemoveLock(v5, v3);
            ClassCompleteRequest(v5, v3, 0);
            LBProvisioningResources = -1073741820;
            goto LABEL_725;
          }
          if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) == 0 )
            goto LABEL_103;
          InfoProcess = ClasspMcnControl((PFUNCTIONAL_DEVICE_EXTENSION)v5->DeviceExtension, v3, (PVOID)Pool2);
LABEL_724:
          LBProvisioningResources = InfoProcess;
          goto LABEL_725;
        }
        if ( CurrentStackLocation->Parameters.Create.Options < 0xC )
          goto LABEL_110;
        if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) == 0 )
          goto LABEL_114;
        v43 = v3->AssociatedIrp.MasterIrp;
        switch ( *(_DWORD *)&v43->Type )
        {
          case 6:
            DiskByPassIOProperty = ClasspQueryDiskByPassIOProperty(v5, v3);
            goto LABEL_53;
          case 7:
            DiskByPassIOProperty = ClasspQueryDiskObjectProperty(v5, v3);
            goto LABEL_53;
          case 0x13:
            DiskByPassIOProperty = ClasspQueryDeviceCommandDurationLimitEntriesProperty(v5, v3);
            goto LABEL_53;
          case 0x14:
            DiskByPassIOProperty = ClasspQueryDeviceCommandDurationLimitMappingProperty(v5, v3);
            goto LABEL_53;
          case 0x16:
            DiskByPassIOProperty = ClasspQueryDeviceCommandDurationLimitStatusProperty(v5, v3);
            goto LABEL_53;
        }
        goto LABEL_124;
      }
      if ( v263 <= 0x2D1CA4 )
      {
        if ( v263 == 2956452 )
        {
          v22 = v3;
          v23 = v5;
          if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
          {
            DiskByPassIOProperty = ClasspDeviceGetPhysicalElementStatus(v5, v3, Pool2);
            goto LABEL_53;
          }
          goto LABEL_51;
        }
        if ( v263 != 2954240 )
        {
          if ( v263 != 2955392 )
          {
            if ( v263 == 2956288 )
            {
              if ( Pool2 )
                ExFreePoolWithTag((PVOID)Pool2, 0);
              InfoProcess = ClassDeviceHwFirmwareGetInfoProcess(v5, v3);
              goto LABEL_724;
            }
            if ( v263 == 2956432 )
            {
              if ( Pool2 )
                ExFreePoolWithTag((PVOID)Pool2, 0);
              InfoProcess = ClasspStorageEventNotification(v5, v3);
              goto LABEL_724;
            }
            goto LABEL_631;
          }
          if ( Pool2 )
            ExFreePoolWithTag((PVOID)Pool2, 0);
          if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
          {
            v44 = v5->DeviceExtension;
            v45 = v3->AssociatedIrp.MasterIrp;
            v46 = v3->Tail.Overlay.CurrentStackLocation;
            v47 = *((_QWORD *)v44 + 143);
            v3->IoStatus.Information = 0;
            if ( (*(_DWORD *)(v47 + 664) & 1) != 0 )
            {
              if ( v46->Parameters.Read.Length >= 4 )
              {
                *(_DWORD *)&v45->Type = 0;
                v48 = v3->Tail.Overlay.CurrentStackLocation;
                *(_OWORD *)&v48[-1].MajorFunction = *(_OWORD *)&v48->MajorFunction;
                *(_OWORD *)&v48[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v48->Parameters.NotifyDirectoryEx.CompletionFilter;
                *(_OWORD *)(&v48[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v48->Parameters.SetQuota + 6);
                v48[-1].FileObject = v48->FileObject;
                v48[-1].Control = 0;
                LBProvisioningResources = ClassSendIrpSynchronous(*((PDEVICE_OBJECT *)v44 + 2), v3);
                if ( LBProvisioningResources >= 0 )
                {
                  v49 = *(unsigned int *)&v45->Type;
                }
                else
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids);
                  }
                  *(_DWORD *)&v45->Type = 0;
                  LBProvisioningResources = 0;
                  v49 = 0;
                }
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, v49);
                }
                *(_DWORD *)&v45->Type |= 7u;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    91,
                    WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
                    *(unsigned int *)&v45->Type);
                }
                v3->IoStatus.Information = 4;
              }
              else
              {
                LBProvisioningResources = -1073741789;
              }
            }
            else
            {
              LBProvisioningResources = -1073741637;
            }
            v3->IoStatus.Status = LBProvisioningResources;
            v50 = (_DWORD **)v5->DeviceExtension;
            v51 = *v50[55];
            if ( v51 )
            {
              while ( 1 )
              {
                v52 = v51;
                v51 = _InterlockedCompareExchange(v50[55], v51 - 1, v51);
                if ( v52 == v51 )
                  break;
                if ( !v51 )
                  goto LABEL_171;
              }
            }
            else
            {
LABEL_171:
              ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v50[55] + 2));
            }
            ClassCompleteRequest(v5, v3, 0);
            goto LABEL_725;
          }
          goto LABEL_88;
        }
        if ( CurrentStackLocation->Parameters.Create.Options >= 0xC )
        {
          if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
          {
            v53 = v3->AssociatedIrp.MasterIrp;
            switch ( *(_DWORD *)&v53->Type )
            {
              case 3:
                DiskByPassIOProperty = ClasspDuidQueryProperty(v5, v3);
                goto LABEL_53;
              case 4:
                DiskByPassIOProperty = ClasspWriteCacheProperty(v5, v3, (PSCSI_REQUEST_BLOCK)Pool2);
                goto LABEL_53;
              case 6:
                DiskByPassIOProperty = ClasspAccessAlignmentProperty(v5, v3);
                goto LABEL_53;
              case 7:
                DiskByPassIOProperty = ClasspDeviceSeekPenaltyProperty(v5, v3);
                goto LABEL_53;
              case 8:
                DiskByPassIOProperty = ClasspDeviceTrimProperty(v5, v3);
                goto LABEL_53;
              case 0xB:
                DiskByPassIOProperty = ClasspDeviceLBProvisioningProperty(v5, v3);
                goto LABEL_53;
              case 0xD:
                DiskByPassIOProperty = ClasspDeviceCopyOffloadProperty(v5, v3);
                goto LABEL_53;
              case 0xF:
                DiskByPassIOProperty = ClasspDeviceMediaTypeProperty(v5, v3);
                goto LABEL_53;
              case 0x38:
                v54 = *(_DWORD *)(&v53->Size + 1);
                if ( v54 == 1 )
                {
                  LBProvisioningResources = 0;
                  v55 = 0;
                }
                else if ( v54 )
                {
                  LBProvisioningResources = -1073741822;
                  v55 = 0;
                }
                else
                {
                  v56 = v3->Tail.Overlay.CurrentStackLocation;
                  if ( v56->Parameters.Read.Length >= 8 )
                  {
                    v57 = v5->DeviceExtension;
                    LBProvisioningResources = 0;
                    memset(v3->AssociatedIrp.MasterIrp, 0, v56->Parameters.Read.Length);
                    v55 = 100;
                    v58 = 84;
                    *(_DWORD *)&v53->Type = 100;
                    *(_DWORD *)(&v53->Size + 1) = 84;
                    if ( v57[819] )
                    {
                      *(_DWORD *)(&v53->Size + 1) = 100;
                      v58 = 100;
                    }
                    else
                    {
                      v55 = 84;
                    }
                    if ( v56->Parameters.Read.Length >= v58 )
                    {
                      HIDWORD(v53->MdlAddress) = 1;
                      v59 = 2;
                      if ( v57[819] )
                      {
                        LODWORD(v53->MdlAddress) = 2;
                        v53->Overlay.AllocationSize.HighPart = 2;
                        v59 = 3;
                        v53->Flags = 1;
                        HIDWORD(v53->UserEvent) = 16;
                        v53->Overlay.AllocationSize.LowPart = 16;
                      }
                      else
                      {
                        LODWORD(v53->MdlAddress) = 3;
                      }
                      *(&v53->Flags + 1) = v59;
                    }
                    else
                    {
                      v55 = 8;
                    }
                  }
                  else
                  {
                    LBProvisioningResources = -1073741789;
                    v55 = 0;
                  }
                }
                v3->IoStatus.Information = v55;
                v3->IoStatus.Status = LBProvisioningResources;
                v60 = (_DWORD **)v5->DeviceExtension;
                v61 = *v60[55];
                if ( !v61 )
                  goto LABEL_202;
                break;
              case 0x3C:
                DiskByPassIOProperty = ClasspDeviceZonedDeviceProperty(v5, v3);
                goto LABEL_53;
              default:
                goto LABEL_114;
            }
            while ( 1 )
            {
              v62 = v61;
              v61 = _InterlockedCompareExchange(v60[55], v61 - 1, v61);
              if ( v62 == v61 )
                goto LABEL_112;
              if ( !v61 )
                goto LABEL_202;
            }
          }
          goto LABEL_114;
        }
        goto LABEL_110;
      }
      if ( v263 != 2956480 )
      {
        if ( v263 == 2956484 )
        {
          v22 = v3;
          v23 = v5;
          if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
          {
            DiskByPassIOProperty = ClasspDeviceGetInternalStatusData(v5, v3, Pool2);
            goto LABEL_53;
          }
          goto LABEL_51;
        }
        if ( v263 != 2959376 )
          goto LABEL_631;
        v63 = v3->Tail.Overlay.CurrentStackLocation;
        if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
        {
          if ( v63->Parameters.Read.Length >= 0x24 )
          {
            v64 = v5->DeviceExtension;
            v65 = *((_QWORD *)v64 + 143);
            if ( v65 )
            {
              v66 = v3->AssociatedIrp.MasterIrp;
              if ( *(_BYTE *)(v65 + 3915) )
              {
                *(_OWORD *)&v63[-1].MajorFunction = *(_OWORD *)&v63->MajorFunction;
                *(_OWORD *)&v63[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v63->Parameters.NotifyDirectoryEx.CompletionFilter;
                *(_OWORD *)(&v63[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v63->Parameters.SetQuota + 6);
                v63[-1].FileObject = v63->FileObject;
                v63[-1].Control = 0;
                LBProvisioningResources = ClassSendIrpSynchronous(*((PDEVICE_OBJECT *)v64 + 2), v3);
                if ( LBProvisioningResources >= 0 )
                {
                  HIDWORD(v66->MdlAddress) = *(unsigned __int8 *)(v65 + 662);
                  v3->IoStatus.Information = 36;
                }
              }
              else
              {
                *(_OWORD *)&v66->Type = 0;
                LBProvisioningResources = 0;
                *(_OWORD *)&v66->Flags = 0;
                LODWORD(v66->ThreadListEntry.Flink) = 0;
                *(_DWORD *)&v66->Type = 36;
                *(_DWORD *)(&v66->Size + 1) = 36;
                v3->IoStatus.Information = 36;
              }
            }
            else
            {
              LBProvisioningResources = -1073741823;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 147, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, v5);
            }
            LBProvisioningResources = -1073741789;
          }
          v3->IoStatus.Status = LBProvisioningResources;
          v60 = (_DWORD **)v5->DeviceExtension;
          v67 = *v60[55];
          if ( v67 )
          {
            while ( 1 )
            {
              v68 = v67;
              v67 = _InterlockedCompareExchange(v60[55], v67 - 1, v67);
              if ( v68 == v67 )
                goto LABEL_112;
              if ( !v67 )
                goto LABEL_202;
            }
          }
          goto LABEL_202;
        }
        goto LABEL_226;
      }
      v22 = v3;
      v23 = v5;
      if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
      {
        InfoProcess = ClasspDeviceRemoveElementAndTruncate(v5, v3, (PVOID)Pool2);
        goto LABEL_724;
      }
LABEL_51:
      v25 = v3->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v25[-1].MajorFunction = *(_OWORD *)&v25->MajorFunction;
      *(_OWORD *)&v25[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v25->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v25[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v25->Parameters.SetQuota + 6);
      v25[-1].FileObject = v25->FileObject;
      v25[-1].Control = 0;
LABEL_52:
      ClassReleaseRemoveLock(v23, v22);
      DiskByPassIOProperty = IofCallDriver(DeviceExtension->CommonExtension.LowerDeviceObject, v3);
      goto LABEL_53;
    }
    if ( v263 <= 0x2D5408 )
    {
      if ( v263 == 2970632 )
      {
        v63 = v3->Tail.Overlay.CurrentStackLocation;
        if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
        {
          v175 = v3->AssociatedIrp.MasterIrp;
          LBProvisioningResources = ClassGetLBProvisioningResources(v5, Pool2, v63->Parameters.Read.Length, v175);
          if ( LBProvisioningResources < 0 )
            v176 = 0;
          else
            v176 = *(unsigned int *)&v175->Type;
          v3->IoStatus.Information = v176;
          v3->IoStatus.Status = LBProvisioningResources;
          v60 = (_DWORD **)v5->DeviceExtension;
          v177 = *v60[55];
          while ( v177 )
          {
            v178 = v177;
            v177 = _InterlockedCompareExchange(v60[55], v177 - 1, v177);
            if ( v178 == v177 )
              goto LABEL_112;
          }
LABEL_202:
          ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v60[55] + 2));
          ClassCompleteRequest(v5, v3, 0);
          goto LABEL_54;
        }
LABEL_226:
        v22 = v3;
        *(_OWORD *)&v63[-1].MajorFunction = *(_OWORD *)&v63->MajorFunction;
        *(_OWORD *)&v63[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v63->Parameters.NotifyDirectoryEx.CompletionFilter;
        *(_OWORD *)(&v63[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v63->Parameters.SetQuota + 6);
        v63[-1].FileObject = v63->FileObject;
        v63[-1].Control = 0;
        v23 = v5;
        goto LABEL_52;
      }
      if ( v263 <= 0x2D4814 )
      {
        if ( v263 != 2967572 )
        {
          if ( v263 == 2967556 )
            goto LABEL_385;
          if ( v263 == 2967560 || v263 == 2967564 )
            goto LABEL_324;
          if ( v263 != 2967568 )
          {
LABEL_631:
            v39 = (int)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_Dq(
                WPP_GLOBAL_Control->AttachedDevice,
                161,
                WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
                (unsigned int)v6,
                v5);
            }
LABEL_103:
            if ( v8 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 4) != 0 )
              McTemplateK0qpd_EtwWriteTransfer(
                v39,
                (unsigned int)EventNonReadWriteRequestComplete,
                (unsigned int)&v279,
                DeviceExtension->DeviceNumber,
                (char)v3,
                v3->IoStatus.Status);
            if ( Pool2 )
              ExFreePoolWithTag((PVOID)Pool2, 0);
            goto LABEL_92;
          }
        }
        if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) == 0 )
        {
LABEL_244:
          if ( !v8 || (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 4) == 0 )
            goto LABEL_92;
          DeviceNumber = MEMORY[0x24C];
LABEL_91:
          McTemplateK0qpd_EtwWriteTransfer(
            v10,
            (unsigned int)EventNonReadWriteRequestComplete,
            (unsigned int)&v279,
            DeviceNumber,
            (char)v3,
            v3->IoStatus.Status);
LABEL_92:
          v38 = v3->Tail.Overlay.CurrentStackLocation;
          *(_OWORD *)&v38[-1].MajorFunction = *(_OWORD *)&v38->MajorFunction;
          *(_OWORD *)&v38[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v38->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v38[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v38->Parameters.SetQuota + 6);
          v38[-1].FileObject = v38->FileObject;
          v38[-1].Control = 0;
          ClassReleaseRemoveLock(v5, v3);
LABEL_723:
          InfoProcess = IofCallDriver(DeviceExtension->CommonExtension.LowerDeviceObject, v3);
          goto LABEL_724;
        }
        v99 = v5->DeviceExtension;
        v100 = *(_BYTE *)(Pool2 + 2);
        if ( (*(_BYTE *)(*((_QWORD *)v99 + 143) + 1320LL) & 8) != 0 )
        {
          if ( v100 == 40 )
          {
            if ( !*(_DWORD *)(Pool2 + 20) )
            {
              v101 = *(_DWORD *)(Pool2 + 56);
              for ( k = 0; (unsigned int)k < v101; k = (unsigned int)(k + 1) )
              {
                v103 = *(unsigned int *)(Pool2 + 4 * k + 120);
                if ( (unsigned int)v103 < 0x80 )
                  continue;
                v104 = *(unsigned int *)(Pool2 + 16);
                if ( (unsigned int)v103 >= (unsigned int)v104 )
                  continue;
                v105 = Pool2 + v103;
                v106 = (unsigned int)v103;
                v107 = *(_DWORD *)(Pool2 + v103) - 64;
                if ( v107 )
                {
                  v108 = v107 - 1;
                  if ( v108 )
                  {
                    if ( v108 == 1 && v106 + 40 <= v104 )
                      break;
                    continue;
                  }
                  v136 = v106 + 56;
                }
                else
                {
                  v136 = v106 + 40;
                }
                if ( v136 <= v104 )
                {
                  *(_BYTE *)(v105 + 10) = 10;
                  break;
                }
              }
            }
          }
          else
          {
            *(_BYTE *)(Pool2 + 10) = 10;
          }
          if ( *(_BYTE *)(Pool2 + 2) != 40 )
          {
            v137 = (_BYTE *)(Pool2 + 72);
            goto LABEL_422;
          }
          v137 = 0;
          if ( !*(_DWORD *)(Pool2 + 20) )
          {
            v138 = *(_DWORD *)(Pool2 + 56);
            if ( v138 )
            {
              v139 = 0;
              do
              {
                v140 = *(unsigned int *)(Pool2 + 4 * v139 + 120);
                if ( (unsigned int)v140 < 0x80 )
                  goto LABEL_417;
                v141 = *(unsigned int *)(Pool2 + 16);
                if ( (unsigned int)v140 >= (unsigned int)v141 )
                  goto LABEL_417;
                v142 = v140 + Pool2;
                v143 = (unsigned int)v140;
                v144 = *(_DWORD *)(v140 + Pool2) - 64;
                if ( v144 )
                {
                  v145 = v144 - 1;
                  if ( v145 )
                  {
                    if ( v145 == 1 && v143 + 40 <= v141 )
                    {
                      if ( *(_DWORD *)(v142 + 12) )
                        v137 = (_BYTE *)(v142 + 32);
                      break;
                    }
                    goto LABEL_417;
                  }
                  v146 = v143 + 56;
                }
                else
                {
                  v146 = v143 + 40;
                }
                if ( v146 <= v141 )
                {
                  if ( *(_BYTE *)(v142 + 10) )
                    v137 = (_BYTE *)(v142 + 24);
                  break;
                }
LABEL_417:
                v139 = (unsigned int)(v139 + 1);
              }
              while ( (unsigned int)v139 < v138 );
            }
          }
LABEL_422:
          v147 = v263;
          v148 = (v263 != 2967568) + 86;
LABEL_461:
          *v137 = v148;
          v167 = *(_BYTE *)(Pool2 + 2);
          v168 = v99[146];
          if ( v167 == 40 )
            *(_DWORD *)(Pool2 + 40) = v168;
          else
            *(_DWORD *)(Pool2 + 20) = v168;
          if ( v147 == 2967568 )
          {
            if ( v167 == 40 )
            {
              *(_DWORD *)(Pool2 + 24) |= 2u;
              *(_WORD *)(Pool2 + 38) = 32;
            }
            else
            {
              *(_DWORD *)(Pool2 + 12) |= 2u;
              *(_BYTE *)(Pool2 + 9) = 32;
            }
          }
LABEL_303:
          InfoProcess = ClassSendSrbAsynchronous(v5, (PSCSI_REQUEST_BLOCK)Pool2, v3, 0, 0, 0);
          goto LABEL_724;
        }
        if ( v100 == 40 )
        {
          if ( !*(_DWORD *)(Pool2 + 20) )
          {
            v149 = *(_DWORD *)(Pool2 + 56);
            for ( m = 0; (unsigned int)m < v149; m = (unsigned int)(m + 1) )
            {
              v151 = *(unsigned int *)(Pool2 + 4 * m + 120);
              if ( (unsigned int)v151 < 0x80 )
                continue;
              v152 = *(unsigned int *)(Pool2 + 16);
              if ( (unsigned int)v151 >= (unsigned int)v152 )
                continue;
              v153 = v151 + Pool2;
              v154 = (unsigned int)v151;
              v155 = *(_DWORD *)(v151 + Pool2) - 64;
              if ( v155 )
              {
                v156 = v155 - 1;
                if ( v156 )
                {
                  if ( v156 == 1 && v154 + 40 <= v152 )
                    break;
                  continue;
                }
                v157 = v154 + 56;
              }
              else
              {
                v157 = v154 + 40;
              }
              if ( v157 <= v152 )
              {
                *(_BYTE *)(v153 + 10) = 6;
                break;
              }
            }
          }
        }
        else
        {
          *(_BYTE *)(Pool2 + 10) = 6;
        }
        if ( *(_BYTE *)(Pool2 + 2) != 40 )
        {
          v137 = (_BYTE *)(Pool2 + 72);
          goto LABEL_460;
        }
        v137 = 0;
        if ( *(_DWORD *)(Pool2 + 20) || (v158 = *(_DWORD *)(Pool2 + 56)) == 0 )
        {
LABEL_460:
          v147 = v263;
          v148 = (v263 != 2967568) + 22;
          goto LABEL_461;
        }
        v159 = 0;
        while ( 1 )
        {
          v160 = *(unsigned int *)(Pool2 + 4 * v159 + 120);
          if ( (unsigned int)v160 < 0x80 )
            goto LABEL_455;
          v161 = *(unsigned int *)(Pool2 + 16);
          if ( (unsigned int)v160 >= (unsigned int)v161 )
            goto LABEL_455;
          v162 = v160 + Pool2;
          v163 = (unsigned int)v160;
          v164 = *(_DWORD *)(v160 + Pool2) - 64;
          if ( v164 )
          {
            v165 = v164 - 1;
            if ( v165 )
            {
              if ( v165 == 1 && v163 + 40 <= v161 )
              {
                if ( *(_DWORD *)(v162 + 12) )
                  v137 = (_BYTE *)(v162 + 32);
                goto LABEL_460;
              }
              goto LABEL_455;
            }
            v166 = v163 + 56;
          }
          else
          {
            v166 = v163 + 40;
          }
          if ( v166 <= v161 )
          {
            if ( *(_BYTE *)(v162 + 10) )
              v137 = (_BYTE *)(v162 + 24);
            goto LABEL_460;
          }
LABEL_455:
          v159 = (unsigned int)(v159 + 1);
          if ( (unsigned int)v159 >= v158 )
            goto LABEL_460;
        }
      }
      if ( v263 == 2967576 )
      {
        if ( Pool2 )
          ExFreePoolWithTag((PVOID)Pool2, 0);
        if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) == 0 )
          goto LABEL_88;
        IoInvalidateDeviceRelations(DeviceExtension->LowerPdo, BusRelations);
        LBProvisioningResources = 0;
        v3->IoStatus.Status = 0;
        goto LABEL_476;
      }
      if ( v263 != 2969624 )
      {
        if ( v263 != 2969920 )
          goto LABEL_631;
        if ( Pool2 )
          ExFreePoolWithTag((PVOID)Pool2, 0);
        if ( CurrentStackLocation->Parameters.Read.Length >= 0x20 )
        {
          if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) == 0 )
            goto LABEL_88;
          v170 = v5->DeviceExtension;
          v171 = v3->AssociatedIrp.MasterIrp;
          v172 = (_BYTE *)*((_QWORD *)v170 + 143);
          LBProvisioningResources = ClassReadDriveCapacity(v5);
          if ( LBProvisioningResources >= 0 && v172[1580] )
          {
            v169 = 32;
            *(_DWORD *)&v171->Type = 32;
            *(_DWORD *)(&v171->Size + 1) = 32;
            BYTE3(v171->MdlAddress) = v172[1576];
            BYTE2(v171->MdlAddress) = v172[1577];
            BYTE1(v171->MdlAddress) = v172[1578];
            LOBYTE(v171->MdlAddress) = v172[1579];
            *((_BYTE *)&v171->Flags + 7) = v172[1568];
            *((_BYTE *)&v171->Flags + 6) = v172[1569];
            *((_BYTE *)&v171->Flags + 5) = v172[1570];
            *((_BYTE *)&v171->Flags + 4) = v172[1571];
            HIBYTE(v171->Flags) = v172[1572];
            BYTE2(v171->Flags) = v172[1573];
            BYTE1(v171->Flags) = v172[1574];
            LOBYTE(v171->Flags) = v172[1575];
            ++*(_QWORD *)&v171->Flags;
            v171->AssociatedIrp.MasterIrp = (_IRP *)*((_QWORD *)v170 + 18);
            v3->IoStatus.Status = 0;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            {
              WPP_SF_Dd(
                WPP_GLOBAL_Control->AttachedDevice,
                v173,
                v174,
                (unsigned int)LBProvisioningResources,
                (unsigned __int8)v172[1580]);
            }
            v169 = 0;
            v3->IoStatus.Status = LBProvisioningResources;
          }
        }
        else
        {
          LBProvisioningResources = -1073741789;
          v169 = 32;
          v3->IoStatus.Status = -1073741789;
        }
        v3->IoStatus.Information = v169;
        goto LABEL_476;
      }
      goto LABEL_625;
    }
    if ( v263 > 0x2DD01C )
    {
      switch ( v263 )
      {
        case 0x2DDC04u:
          v226 = v3;
          v227 = v5;
          if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
          {
            InfoProcess = ClassDeviceHwFirmwareDownloadProcess(v5, v3, (PSCSI_REQUEST_BLOCK)Pool2);
            goto LABEL_724;
          }
          break;
        case 0x2DDC08u:
          v226 = v3;
          v227 = v5;
          if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
          {
            InfoProcess = ClassDeviceHwFirmwareActivateProcess(v5, v3, (PVOID)Pool2);
            goto LABEL_724;
          }
          break;
        case 0x2DE814u:
          v22 = v3;
          v23 = v5;
          if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
          {
            DiskByPassIOProperty = ClasspDeviceSetQOS(v5, v3);
            goto LABEL_53;
          }
          goto LABEL_51;
        default:
          goto LABEL_631;
      }
LABEL_626:
      v228 = v3->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v228[-1].MajorFunction = *(_OWORD *)&v228->MajorFunction;
      *(_OWORD *)&v228[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v228->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v228[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v228->Parameters.SetQuota + 6);
      v228[-1].FileObject = v228->FileObject;
      v228[-1].Control = 0;
      ClassReleaseRemoveLock(v227, v226);
      goto LABEL_723;
    }
    if ( v263 == 3002396 )
    {
LABEL_625:
      v226 = v3;
      v227 = v5;
      if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
      {
        InfoProcess = ClasspPersistentReserve(v5, v3, (PVOID)Pool2);
        goto LABEL_724;
      }
      goto LABEL_626;
    }
    if ( v263 == 2986996 )
    {
      if ( CurrentStackLocation->Parameters.Create.Options >= 0xC )
      {
        if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
        {
          v43 = v3->AssociatedIrp.MasterIrp;
          switch ( *(_DWORD *)&v43->Type )
          {
            case 0x13:
              DiskByPassIOProperty = ClasspSetDeviceCommandDurationLimitEntriesProperty(v5, v3);
              goto LABEL_53;
            case 0x14:
              DiskByPassIOProperty = ClasspSetDeviceCommandDurationLimitMappingProperty(v5, v3);
              goto LABEL_53;
            case 0x15:
              DiskByPassIOProperty = ClasspSetDeviceCommandDurationLimitControlProperty(v5, v3);
              goto LABEL_53;
          }
LABEL_124:
          if ( v8 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 4) != 0 )
            McTemplateK0qpd_EtwWriteTransfer(
              (_DWORD)v43,
              (unsigned int)EventNonReadWriteRequestComplete,
              (unsigned int)&v279,
              DeviceExtension->DeviceNumber,
              (char)v3,
              v3->IoStatus.Status);
          v22 = v3;
          v23 = v5;
          goto LABEL_51;
        }
LABEL_114:
        v41 = v8 == 0;
        goto LABEL_115;
      }
LABEL_110:
      LBProvisioningResources = -1073741820;
LABEL_111:
      v3->IoStatus.Status = LBProvisioningResources;
      ClassReleaseRemoveLock(v5, v3);
LABEL_112:
      ClassCompleteRequest(v5, v3, 0);
      goto LABEL_54;
    }
    if ( v263 != 2987012 )
    {
      if ( v263 == 2987584 )
      {
        v22 = v3;
        v23 = v5;
        if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
        {
          DiskByPassIOProperty = ClasspDeviceSanitize(v5, v3, Pool2);
          goto LABEL_53;
        }
        goto LABEL_51;
      }
      if ( v263 != 3001368 )
        goto LABEL_631;
      if ( Pool2 )
        ExFreePoolWithTag((PVOID)Pool2, 0);
      if ( CurrentStackLocation->Parameters.Create.Options < 8 )
        goto LABEL_392;
      if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) == 0 )
        goto LABEL_88;
      PrivateFdoData = DeviceExtension->PrivateFdoData;
      v180 = v3->AssociatedIrp.MasterIrp;
      LBProvisioningResources = -1073741585;
      if ( *(_DWORD *)&v180->Type == PrivateFdoData->HotplugInfo.Size )
        LBProvisioningResources = 0;
      if ( *((_BYTE *)&v180->Size + 2) != PrivateFdoData->HotplugInfo.MediaRemovable )
        LBProvisioningResources = -1073741584;
      if ( *((_BYTE *)&v180->Size + 3) == PrivateFdoData->HotplugInfo.MediaHotplug )
      {
        if ( LBProvisioningResources >= 0 )
        {
          v181 = *((_BYTE *)&v180->Size + 5);
          if ( v181 != PrivateFdoData->HotplugInfo.WriteCacheEnableOverride )
          {
            PrivateFdoData->HotplugInfo.WriteCacheEnableOverride = v181;
            ClassSetDeviceParameter(
              DeviceExtension,
              (PWSTR)L"Classpnp",
              (PWSTR)L"WriteCacheEnableOverride",
              *((unsigned __int8 *)&v180->Size + 5));
          }
          DeviceExtension->PrivateFdoData->HotplugInfo.DeviceHotplug = *((_BYTE *)&v180->Size + 4);
          ClassSetDeviceParameter(
            DeviceExtension,
            (PWSTR)L"Classpnp",
            (PWSTR)L"UserRemovalPolicy",
            (*((_BYTE *)&v180->Size + 4) != 0) + 2);
        }
        v3->IoStatus.Status = LBProvisioningResources;
      }
      else
      {
        LBProvisioningResources = -1073741583;
        v3->IoStatus.Status = -1073741583;
      }
LABEL_476:
      ClassReleaseRemoveLock(v5, v3);
      ClassCompleteRequest(v5, v3, 0);
      goto LABEL_725;
    }
    v182 = v3->AssociatedIrp.MasterIrp;
    if ( !v182
      || (v183 = CurrentStackLocation->Parameters.Create.Options, v183 < 0x1C)
      || (MdlAddress_high = HIDWORD(v182->MdlAddress),
          LODWORD(v10) = v183,
          Flags = v182->Flags,
          v183 < (unsigned __int64)(Flags + MdlAddress_high))
      || (v186 = *(&v182->Flags + 1),
          IrpCount = (unsigned int)v182->AssociatedIrp.IrpCount,
          v183 < (unsigned __int64)(IrpCount + v186))
      || v183 < (unsigned __int64)(IrpCount + Flags + 28) )
    {
      LBProvisioningResources = -1073741811;
      goto LABEL_111;
    }
    if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) == 0 )
    {
      v41 = ClassPnPETWEnabled == 0;
      goto LABEL_115;
    }
    v188 = DeviceExtension->PrivateFdoData;
    if ( v188->VirtualDevicePropertiesData.Spaces )
    {
      if ( DeviceExtension->DeviceDescriptor->BusType != BusTypeSpaces )
      {
        v189 = *(_DWORD *)(&v182->Size + 1);
        if ( v189 == -2147483636 || v189 == -2147483621 )
        {
          InfoProcess = ClasspDeviceSendIoctlPassThrough(v5, v3, (PSCSI_REQUEST_BLOCK)Pool2);
          goto LABEL_724;
        }
      }
    }
    if ( DeviceExtension->DeviceDescriptor->BusType == BusTypeSpaces )
    {
      if ( (v190 = *(_DWORD *)(&v182->Size + 1), v190 <= 0x19)
        && (LODWORD(v10) = 41943042, _bittest((const int *)&v10, v190))
        || v190 + 2147483629 <= 3 )
      {
        v41 = ClassPnPETWEnabled == 0;
LABEL_115:
        if ( !v41 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 4) != 0 )
          McTemplateK0qpd_EtwWriteTransfer(
            v10,
            (unsigned int)EventNonReadWriteRequestComplete,
            (unsigned int)&v279,
            DeviceExtension->DeviceNumber,
            (char)v3,
            v3->IoStatus.Status);
        v42 = v3->Tail.Overlay.CurrentStackLocation;
        v22 = v3;
        v23 = v5;
        *(_OWORD *)&v42[-1].MajorFunction = *(_OWORD *)&v42->MajorFunction;
        *(_OWORD *)&v42[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v42->Parameters.NotifyDirectoryEx.CompletionFilter;
        *(_OWORD *)(&v42[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v42->Parameters.SetQuota + 6);
        v42[-1].FileObject = v42->FileObject;
        v42[-1].Control = 0;
        goto LABEL_52;
      }
    }
    v191 = *(_DWORD *)(&v182->Size + 1);
    if ( v191 > 0x80000003 )
    {
      if ( v191 != -2147483643 )
      {
        switch ( v191 )
        {
          case 0x80000013:
            v225 = 1;
            LBProvisioningResources = ClasspProcessReportZones(v5, v3);
            break;
          case 0x80000014:
            v225 = 1;
            LBProvisioningResources = ClasspProcessOpenZone(v5, v3, (PSCSI_REQUEST_BLOCK)Pool2);
            break;
          case 0x80000015:
            v225 = 1;
            LBProvisioningResources = ClasspProcessFinishZone(v5, v3, (PSCSI_REQUEST_BLOCK)Pool2);
            break;
          case 0x80000016:
            v225 = 1;
            LBProvisioningResources = ClasspProcessCloseZone(v5, v3, (PSCSI_REQUEST_BLOCK)Pool2);
            break;
          default:
LABEL_602:
            if ( ClassPnPETWEnabled && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 4) != 0 )
              McTemplateK0qpd_EtwWriteTransfer(
                v10,
                (unsigned int)EventNonReadWriteRequestComplete,
                (unsigned int)&v279,
                DeviceExtension->DeviceNumber,
                (char)v3,
                v3->IoStatus.Status);
            v224 = v3->Tail.Overlay.CurrentStackLocation;
            *(_OWORD *)&v224[-1].MajorFunction = *(_OWORD *)&v224->MajorFunction;
            *(_OWORD *)&v224[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v224->Parameters.NotifyDirectoryEx.CompletionFilter;
            *(_OWORD *)(&v224[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v224->Parameters.SetQuota + 6);
            v224[-1].FileObject = v224->FileObject;
            v224[-1].Control = 0;
            ClassReleaseRemoveLock(v5, v3);
            LBAStatus = IofCallDriver(DeviceExtension->CommonExtension.LowerDeviceObject, v3);
            goto LABEL_611;
        }
LABEL_613:
        if ( LBProvisioningResources == 259 && v225 )
          goto LABEL_725;
LABEL_54:
        if ( Pool2 )
          ExFreePoolWithTag((PVOID)Pool2, 0);
        goto LABEL_725;
      }
      LBAStatus = ClasspDeviceGetLBAStatus(v5, v3, Pool2);
    }
    else if ( v191 == -2147483645 )
    {
      LBAStatus = ClassDeviceProcessOffloadRead(v5, v3);
    }
    else if ( v191 == 1 )
    {
      LBAStatus = ClasspDeviceTrimProcess(v5, v3);
    }
    else if ( v191 == 4 )
    {
      LBAStatus = ClassDeviceProcessOffloadWrite(v5, v3);
    }
    else
    {
      if ( v191 != 23 )
      {
        if ( v191 == 25 )
        {
          if ( !(_DWORD)v186
            || (unsigned int)IrpCount < 0x10
            || (v210 = v5->DeviceExtension,
                v211 = *(_QWORD *)((char *)&v182->Type + v186),
                *(_QWORD *)v270 = v210,
                LODWORD(KeyHandle) = *((_DWORD *)v210 + 143),
                v211 % (unsigned int)KeyHandle)
            || (v212 = *(unsigned __int64 *)((char *)&v182->MdlAddress + v186), v212 % (unsigned int)KeyHandle) )
          {
            LBProvisioningResources = -1073741811;
          }
          else
          {
            LBProvisioningResources = 0;
            *(_QWORD *)v267 = v211 / (unsigned int)KeyHandle;
            v213 = v212 / (unsigned int)KeyHandle;
            v268 = v213;
            if ( v213 + *(_QWORD *)v267 > *(_QWORD *)v267 )
            {
              v214 = *(unsigned int *)(v210[143] + 652LL);
              if ( v214 >= (unsigned int)KeyHandle * v213 )
                v214 = (unsigned int)KeyHandle * v213;
              P = (PVOID)ExAllocatePool2(64, v214, 1296327507);
              v215 = P;
              if ( P )
              {
                v216 = 0;
                v217 = v267[0];
                v218 = v214 / (unsigned int)KeyHandle;
                *(_QWORD *)v267 = v218;
                do
                {
                  v219 = v218;
                  if ( v218 >= v268 - v216 )
                    v219 = v268 - v216;
                  LBProvisioningResources = ClasspDeviceWriteZeros(
                                              v270[0],
                                              Pool2,
                                              v217,
                                              v219,
                                              v215,
                                              (int)KeyHandle * v219);
                  if ( LBProvisioningResources < 0 )
                    break;
                  v215 = P;
                  v216 += v219;
                  v217 += v219;
                  v218 = *(_QWORD *)v267;
                }
                while ( v216 < v268 );
                ExFreePoolWithTag(P, 0);
                v3 = *(PIRP *)&DestinationString.Length;
                v5 = *(PDEVICE_OBJECT *)&v265.Length;
              }
              else
              {
                LBProvisioningResources = -1073741670;
              }
            }
          }
          v3->IoStatus.Information = 0;
          v3->IoStatus.Status = LBProvisioningResources;
          v220 = (_DWORD **)v5->DeviceExtension;
          v221 = *v220[55];
          if ( v221 )
          {
            while ( 1 )
            {
              v222 = v221;
              v221 = _InterlockedCompareExchange(v220[55], v221 - 1, v221);
              if ( v222 == v221 )
                break;
              if ( !v221 )
                goto LABEL_591;
            }
          }
          else
          {
LABEL_591:
            ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v220[55] + 2));
          }
          ClassCompleteRequest(v5, v3, 0);
          goto LABEL_612;
        }
        if ( v191 == -2147483646 )
        {
          if ( v188->PageHashErrorLog )
          {
            if ( (unsigned int)MdlAddress_high >= 0x1C )
            {
              v192 = *(_DWORD *)((char *)&v182->Type + MdlAddress_high);
              if ( v192 >= 0x1C
                && v192 <= (unsigned int)Flags
                && *(_DWORD *)((char *)&v182->MdlAddress + MdlAddress_high) == 1
                && !memcmp(
                      (char *)&v182->MdlAddress + MdlAddress_high + 4,
                      &FILE_TYPE_NOTIFICATION_GUID_PAGE_FILE,
                      0x10u) )
              {
                ExAcquireFastMutex(&v188->PageFileInfoMutex);
                ExWaitForRundownProtectionReleaseCacheAware(DeviceExtension->PrivateFdoData->PageFileRunDown);
                v193 = *(_DWORD *)((char *)&v182->Size + MdlAddress_high + 2);
                v194 = (_SLIST_ENTRY **)((char *)v182 + *(&v182->Flags + 1));
                if ( (v193 & 1) != 0 )
                {
                  v195 = 0;
                  p_PageFilesInfo = &DeviceExtension->PrivateFdoData->PageFilesInfo;
                  KeyHandle = 0;
                  Next = p_PageFilesInfo->Next;
                  if ( p_PageFilesInfo->Next )
                  {
                    while ( 1 )
                    {
                      v198 = Next->Next;
                      if ( *v194 == Next[2].Next )
                        break;
                      p_PageFilesInfo = Next;
                      Next = Next->Next;
                      if ( !v198 )
                        goto LABEL_557;
                    }
                    p_PageFilesInfo->Next = v198;
                    ExFreePoolWithTag(Next, 0);
                    v195 = (unsigned __int64)KeyHandle;
                  }
LABEL_557:
                  v199 = (unsigned int)v182->AssociatedIrp.IrpCount;
                  v200 = (char *)v194 + v199;
                  if ( v194 < (_SLIST_ENTRY **)((char *)v194 + v199) )
                  {
                    v201 = 0;
                    v202 = 0;
                    v203 = (unsigned __int64)v194;
                    if ( ((v199 + 15) & 0xFFFFFFFFFFFFFFF0uLL) < 0x20 )
                      goto LABEL_561;
                    do
                    {
                      v201 += *(_QWORD *)(v203 + 8);
                      v202 += *(_QWORD *)(v203 + 24);
                      v203 += 32LL;
                    }
                    while ( v203 < (unsigned __int64)(v200 - 16) );
                    if ( v203 < (unsigned __int64)v200 )
LABEL_561:
                      v195 = *(_QWORD *)(v203 + 8);
                    v195 += v201 + v202;
                    KeyHandle = (void *)v195;
                  }
                  v204 = ExAllocatePool2(64, v199 + 48 + 4 * (v195 >> 12), 1129341779);
                  v205 = (_SLIST_ENTRY *)v204;
                  if ( v204 )
                  {
                    *(_DWORD *)(v204 + 24) = v182->AssociatedIrp.IrpCount;
                    *(_QWORD *)(v204 + 16) = KeyHandle;
                    memmove((void *)(v204 + 32), v194, (unsigned int)v182->AssociatedIrp.IrpCount);
                    v206 = DeviceExtension->PrivateFdoData;
                    v205->Next = v206->PageFilesInfo.Next;
                    v206->PageFilesInfo.Next = v205;
                  }
                }
                else if ( (v193 & 2) != 0 )
                {
                  v207 = &DeviceExtension->PrivateFdoData->PageFilesInfo;
                  v208 = v207->Next;
                  if ( v207->Next )
                  {
                    while ( 1 )
                    {
                      v209 = v208->Next;
                      if ( *v194 == v208[2].Next )
                        break;
                      v207 = v208;
                      v208 = v208->Next;
                      if ( !v209 )
                        goto LABEL_571;
                    }
                    v207->Next = v209;
                    ExFreePoolWithTag(v208, 0);
                  }
                }
LABEL_571:
                ExReInitializeRundownProtectionCacheAware(DeviceExtension->PrivateFdoData->PageFileRunDown);
                ExReleaseFastMutex(&DeviceExtension->PrivateFdoData->PageFileInfoMutex);
              }
            }
          }
        }
        goto LABEL_602;
      }
      LBAStatus = ClasspProcessResetWritePointer(v5, v3);
    }
LABEL_611:
    LBProvisioningResources = LBAStatus;
LABEL_612:
    v225 = 0;
    goto LABEL_613;
  }
  v229 = CurrentStackLocation->Parameters.Read.Length < 6;
  v280 = 0;
  v281 = 0;
  v272 = 0;
  v273 = 0;
  v274 = 0;
  v275 = 0;
  v276 = 0;
  v277 = 0;
  v278 = 0;
  v265 = 0;
  if ( v229 )
  {
    LBProvisioningResources = -1073741789;
    v3->IoStatus.Information = 6;
    goto LABEL_672;
  }
  v230 = (void *)ExAllocatePool2(256, DeviceExtension->CommonExtension.DeviceName.Length + 2LL, 943940435);
  v231 = v230;
  if ( !v230 )
  {
    LBProvisioningResources = -1073741670;
    goto LABEL_672;
  }
  memmove(v230, DeviceExtension->CommonExtension.DeviceName.Buffer, DeviceExtension->CommonExtension.DeviceName.Length);
  *(_DWORD *)&v265.Length = 1310720;
  v265.Buffer = (wchar_t *)&v280;
  DWORD2(v272) = 292;
  *((_QWORD *)&v273 + 1) = &v265;
  *(_QWORD *)&v273 = v231;
  LODWORD(v274) = 0x1000000;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  LBProvisioningResources = ((__int64 (__fastcall *)(_QWORD, const WCHAR *, __int128 *, _QWORD, _QWORD))SystemRoutineAddress)(
                              0,
                              L"\\Registry\\Machine\\System\\DISK",
                              &v272,
                              0,
                              0);
  if ( LBProvisioningResources < 0 )
    goto LABEL_656;
  if ( v265.Length != 4 )
    goto LABEL_658;
  if ( *v265.Buffer != 37 )
  {
    if ( (unsigned __int16)(*v265.Buffer - 67) <= 0x17u && v265.Buffer[1] == 58 )
      goto LABEL_654;
LABEL_658:
    LBProvisioningResources = -1073741275;
    goto LABEL_656;
  }
  if ( v265.Buffer[1] != 58 )
    goto LABEL_658;
  *v265.Buffer = 255;
LABEL_654:
  v233 = v3->AssociatedIrp.MasterIrp;
  *(_DWORD *)&v233->Type = 0;
  *(_DWORD *)&v233->Size = 28;
  LOBYTE(v233->Type) = 1;
  v3->IoStatus.Information = 32;
  if ( CurrentStackLocation->Parameters.Read.Length < 0x20 )
  {
    v3->IoStatus.Information = 6;
    LBProvisioningResources = -2147483643;
LABEL_656:
    ExFreePoolWithTag(v231, 0);
    goto LABEL_672;
  }
  RtlDeleteRegistryValue(0, L"\\Registry\\Machine\\System\\DISK", (PCWSTR)v231);
  ExFreePoolWithTag(v231, 0);
  *(_OWORD *)(&v233->Size + 1) = *(_OWORD *)L"\\DosDevices\\";
  *(_QWORD *)(&v233->Flags + 1) = *(_QWORD *)L"ces\\";
  WORD2(v233->AssociatedIrp.SystemBuffer) = *v265.Buffer;
  HIWORD(v233->AssociatedIrp.SystemBuffer) = 58;
  LBProvisioningResources = 0;
LABEL_672:
  ClassReleaseRemoveLock(v5, v3);
  v3->IoStatus.Status = LBProvisioningResources;
  if ( v8 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 4) != 0 )
    McTemplateK0qpd_EtwWriteTransfer(
      v239,
      (unsigned int)EventNonReadWriteRequestComplete,
      (unsigned int)&v279,
      DeviceExtension->DeviceNumber,
      (char)v3,
      LBProvisioningResources);
  IofCompleteRequest(v3, 0);
  return LBProvisioningResources;
}

```

## disassembly

```asm
0x140019de0  mov     [rsp-8+arg_10], rbx
0x140019de5  push    rbp
0x140019de6  push    rsi
0x140019de7  push    rdi
0x140019de8  push    r12
0x140019dea  push    r13
0x140019dec  push    r14
0x140019dee  push    r15
0x140019df0  lea     rbp, [rsp-60h]
0x140019df5  sub     rsp, 160h
0x140019dfc  mov     rax, cs:__security_cookie
0x140019e03  xor     rax, rsp
0x140019e06  mov     [rbp+90h+var_38], rax
0x140019e0a  mov     r12, [rdx+0B8h]
0x140019e11  mov     rbx, rdx
0x140019e14  mov     r14, [rcx+40h]
0x140019e18  mov     r15, rcx
0x140019e1b  mov     qword ptr [rsp+190h+DestinationString.Length], rdx
0x140019e20  xorps   xmm0, xmm0
0x140019e23  mov     qword ptr [rsp+190h+var_140.Length], rcx
0x140019e28  lea     rdx, [rbp+90h+var_60]
0x140019e2c  mov     edi, [r12+18h]
0x140019e31  xor     esi, esi
0x140019e33  mov     rcx, rbx
0x140019e36  mov     dword ptr [rsp+190h+P], edi
0x140019e3a  movups  [rbp+90h+var_60], xmm0
0x140019e3e  mov     [rsp+190h+var_150], esi
0x140019e42  xor     r13d, r13d
0x140019e45  call    cs:__imp_IoGetActivityIdIrp
0x140019e4c  nop     dword ptr [rax+rax+00h]
0x140019e51  mov     dword ptr [rsp+190h+KeyHandle], eax
0x140019e55  test    eax, eax
0x140019e57  js      short loc_140019E61
0x140019e59  movzx   r13d, cs:ClassPnPETWEnabled
0x140019e61  mov     rdx, 11000000000001h
0x140019e6b  cmp     edi, 4D004h
0x140019e71  jz      loc_14001C633
0x140019e77  lea     ecx, [rdi-4D014h]
0x140019e7d  cmp     ecx, 34h ; '4'
0x140019e80  ja      short loc_140019E8C
0x140019e82  bt      rdx, rcx
0x140019e86  jb      loc_14001C633
0x140019e8c  mov     [rbx+38h], rsi
0x140019e90  test    r13d, r13d
0x140019e93  jz      short loc_140019ED1
0x140019e95  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 1
0x140019e9c  jz      short loc_140019ED1
0x140019e9e  movzx   eax, byte ptr [r12+1]
0x140019ea4  lea     r8, [rbp+90h+var_60]
0x140019ea8  movzx   ecx, byte ptr [r12]
0x140019ead  lea     rdx, EventIOCTL
0x140019eb4  mov     r9d, [r14+24Ch]
0x140019ebb  mov     [rsp+190h+var_158], edi
0x140019ebf  mov     [rsp+190h+var_160], eax
0x140019ec3  mov     dword ptr [rsp+190h+WriteToDevice], ecx
0x140019ec7  mov     qword ptr [rsp+190h+BufferLength], rbx
0x140019ecc  call    McTemplateK0qpddd_EtwWriteTransfer
0x140019ed1  mov     eax, edi
0x140019ed3  sub     eax, 4D0000h
0x140019ed8  jz      loc_14001C56A
0x140019ede  sub     eax, 8
0x140019ee1  jz      loc_14001C51A
0x140019ee7  cmp     eax, 4
0x140019eea  jz      loc_14001C316
0x140019ef0  test    byte ptr [r14+68h], 1
0x140019ef5  jz      loc_140019FEC
0x140019efb  mov     rax, [r14+210h]
0x140019f02  test    rax, rax
0x140019f05  jz      short loc_140019F2D
0x140019f07  cmp     byte ptr [rax+1Eh], 1
0x140019f0b  jnz     short loc_140019F2D
0x140019f0d  movzx   eax, byte ptr [rax+1Fh]
0x140019f11  mov     ecx, 0B8h
0x140019f16  cmp     al, 1
0x140019f18  mov     edi, 134h
0x140019f1d  cmovnz  edi, ecx
0x140019f20  xor     ecx, ecx
0x140019f22  cmp     al, 1
0x140019f24  setz    cl
0x140019f27  mov     dword ptr [rsp+190h+var_120], ecx
0x140019f2b  jmp     short loc_140019F39
0x140019f2d  xor     eax, eax
0x140019f2f  mov     edi, 58h ; 'X'
0x140019f34  mov     word ptr [rsp+190h+var_120], ax
0x140019f39  mov     eax, edi
0x140019f3b  mov     ecx, 40h ; '@'
0x140019f40  mov     r8d, 39436353h
0x140019f46  mov     qword ptr [rsp+190h+var_128], rax
0x140019f4b  lea     rdx, [rax+10h]
0x140019f4f  call    cs:__imp_ExAllocatePool2
0x140019f56  nop     dword ptr [rax+rax+00h]
0x140019f5b  mov     rsi, rax
0x140019f5e  test    rax, rax
0x140019f61  jnz     short loc_140019F89
0x140019f63  mov     edi, 0C000009Ah
0x140019f68  mov     rdx, rbx; Tag
0x140019f6b  mov     rcx, r15; DeviceObject
0x140019f6e  mov     [rbx+30h], edi
0x140019f71  call    ClassReleaseRemoveLock
0x140019f76  xor     r8d, r8d; PriorityBoost
0x140019f79  mov     rdx, rbx; Irp
0x140019f7c  mov     rcx, r15; DeviceObject
0x140019f7f  call    ClassCompleteRequest
0x140019f84  jmp     loc_14001C960
0x140019f89  mov     rax, [r14+210h]
0x140019f90  test    rax, rax
0x140019f93  jz      short loc_140019FD4
0x140019f95  cmp     byte ptr [rax+1Eh], 1
0x140019f99  jnz     short loc_140019FD4
0x140019f9b  movzx   edx, word ptr [rsp+190h+var_120]
0x140019fa0  mov     r9d, 1
0x140019fa6  mov     r8d, edi
0x140019fa9  mov     [rsp+190h+BufferLength], 40h ; '@'
0x140019fb1  mov     rcx, rsi
0x140019fb4  call    InitializeStorageRequestBlock
0x140019fb9  mov     edi, eax
0x140019fbb  test    eax, eax
0x140019fbd  js      loc_14001C960
0x140019fc3  mov     rcx, qword ptr [rsp+190h+var_128]
0x140019fc8  add     rcx, rsi
0x140019fcb  mov     dword ptr [rsi+14h], 0
0x140019fd2  jmp     short loc_140019FE1
0x140019fd4  mov     word ptr [rsi], 58h ; 'X'
0x140019fd9  lea     rcx, [rsi+58h]
0x140019fdd  mov     byte ptr [rsi+2], 0
0x140019fe1  mov     edi, dword ptr [rsp+190h+P]
0x140019fe5  mov     [rcx], r15
0x140019fe8  mov     [rcx+8], rdi
0x140019fec  mov     eax, edi
0x140019fee  and     eax, 0FFFF0000h
0x140019ff3  cmp     eax, 70000h
0x140019ff8  jz      short loc_14001A00D
0x140019ffa  cmp     eax, 1F0000h
0x140019fff  jz      short loc_14001A00D
0x14001a001  cmp     eax, 20000h
0x14001a006  jz      short loc_14001A00D
0x14001a008  mov     r9d, edi
0x14001a00b  jmp     short loc_14001A018
0x14001a00d  movzx   r9d, di
0x14001a011  or      r9d, 2D0000h
0x14001a018  mov     [rsp+190h+var_150], r9d
0x14001a01d  mov     r8, cs:WPP_GLOBAL_Control
0x14001a024  lea     rax, WPP_GLOBAL_Control
0x14001a02b  cmp     r8, rax
0x14001a02e  jz      short loc_14001A055
0x14001a030  mov     eax, [r8+2Ch]
0x14001a034  test    al, 1
0x14001a036  jz      short loc_14001A055
0x14001a038  cmp     byte ptr [r8+29h], 5
0x14001a03d  jb      short loc_14001A055
0x14001a03f  mov     ecx, r9d
0x14001a042  call    DbgGetIoctlStr
0x14001a047  mov     rcx, [r8+18h]
0x14001a04b  mov     qword ptr [rsp+190h+BufferLength], rax
0x14001a050  call    WPP_SF_Ds
0x14001a055  test    r13d, r13d
0x14001a058  jz      short loc_14001A09C
0x14001a05a  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 1
0x14001a061  jz      short loc_14001A09C
0x14001a063  movzx   eax, byte ptr [r12+1]
0x14001a069  lea     rdx, EventIOCTL
0x14001a070  mov     r8d, [rsp+190h+var_150]
0x14001a075  movzx   ecx, byte ptr [r12]
0x14001a07a  mov     r9d, [r14+24Ch]
0x14001a081  mov     [rsp+190h+var_158], r8d
0x14001a086  lea     r8, [rbp+90h+var_60]
0x14001a08a  mov     [rsp+190h+var_160], eax
0x14001a08e  mov     dword ptr [rsp+190h+WriteToDevice], ecx
0x14001a092  mov     qword ptr [rsp+190h+BufferLength], rbx
0x14001a097  call    McTemplateK0qpddd_EtwWriteTransfer
0x14001a09c  mov     eax, [rsp+190h+var_150]
0x14001a0a0  cmp     eax, 2D4800h
0x14001a0a5  ja      loc_14001B099
0x14001a0ab  jz      loc_14001AD09
0x14001a0b1  cmp     eax, 2D13F8h
0x14001a0b6  ja      loc_14001A6C9
0x14001a0bc  jz      loc_14001A57D
0x14001a0c2  cmp     eax, 2D0940h
0x14001a0c7  ja      loc_14001A23A
0x14001a0cd  jz      loc_14001B45D
0x14001a0d3  sub     eax, 4D008h
0x14001a0d8  jz      loc_14001A176
0x14001a0de  sub     eax, 2837F8h
0x14001a0e3  jz      loc_14001AD09
0x14001a0e9  sub     eax, 0Ch
0x14001a0ec  jz      loc_14001B183
0x14001a0f2  cmp     eax, 0B4h
0x14001a0f7  jnz     loc_14001C271
0x14001a0fd  test    byte ptr [r14+68h], 1
0x14001a102  mov     rdx, rbx; Tag
0x14001a105  mov     rcx, r15; DeviceObject
0x14001a108  jz      short loc_14001A111
0x14001a10a  call    ClasspDeviceManageBypassIO
0x14001a10f  jmp     short loc_14001A155
0x14001a111  mov     rax, [rbx+0B8h]
0x14001a118  movups  xmm0, xmmword ptr [rax]
0x14001a11b  movups  xmmword ptr [rax-48h], xmm0
0x14001a11f  movups  xmm1, xmmword ptr [rax+10h]
0x14001a123  movups  xmmword ptr [rax-38h], xmm1
0x14001a127  movups  xmm0, xmmword ptr [rax+20h]
0x14001a12b  movups  xmmword ptr [rax-28h], xmm0
0x14001a12f  movsd   xmm1, qword ptr [rax+30h]
0x14001a134  movsd   qword ptr [rax-18h], xmm1
0x14001a139  mov     byte ptr [rax-45h], 0
0x14001a13d  call    ClassReleaseRemoveLock
0x14001a142  mov     rcx, [r14+10h]; DeviceObject
0x14001a146  mov     rdx, rbx; Irp
0x14001a149  call    cs:__imp_IofCallDriver
0x14001a150  nop     dword ptr [rax+rax+00h]
0x14001a155  mov     edi, eax
0x14001a157  test    rsi, rsi
0x14001a15a  jz      loc_14001C960
0x14001a160  xor     edx, edx; Tag
0x14001a162  mov     rcx, rsi; P
0x14001a165  call    cs:__imp_ExFreePoolWithTag
0x14001a16c  nop     dword ptr [rax+rax+00h]
0x14001a171  jmp     loc_14001C960
0x14001a176  mov     rdi, [rbx+18h]
0x14001a17a  mov     r12d, [r12+10h]
0x14001a17f  test    rsi, rsi
0x14001a182  jz      short loc_14001A195
0x14001a184  xor     edx, edx; Tag
0x14001a186  mov     rcx, rsi; P
0x14001a189  call    cs:__imp_ExFreePoolWithTag
0x14001a190  nop     dword ptr [rax+rax+00h]
0x14001a195  mov     rax, [rbx+0B8h]
0x14001a19c  movups  xmm0, xmmword ptr [rax]
0x14001a19f  movups  xmmword ptr [rax-48h], xmm0
0x14001a1a3  movups  xmm1, xmmword ptr [rax+10h]
0x14001a1a7  movups  xmmword ptr [rax-38h], xmm1
0x14001a1ab  movups  xmm0, xmmword ptr [rax+20h]
0x14001a1af  movups  xmmword ptr [rax-28h], xmm0
0x14001a1b3  movsd   xmm1, qword ptr [rax+30h]
0x14001a1b8  movsd   qword ptr [rax-18h], xmm1
0x14001a1bd  mov     byte ptr [rax-45h], 0
0x14001a1c1  cmp     r12d, 7Ch ; '|'
0x14001a1c5  jb      short loc_14001A22A
0x14001a1c7  lea     rcx, [rdi+4]; Source1
0x14001a1cb  mov     r8d, 8; Length
0x14001a1d1  lea     rdx, aHybrdisk; "HYBRDISK"
0x14001a1d8  call    cs:__imp_RtlCompareMemory
0x14001a1df  nop     dword ptr [rax+rax+00h]
0x14001a1e4  cmp     eax, 8
0x14001a1e7  jnz     short loc_14001A22A
0x14001a1e9  cmp     dword ptr [rdi], 1Ch
0x14001a1ec  jnz     short loc_14001A22A
0x14001a1ee  cmp     dword ptr [rdi+24h], 1
0x14001a1f2  jnz     short loc_14001A22A
0x14001a1f4  mov     edx, [rdi+2Ch]
0x14001a1f7  mov     ecx, [rdi+30h]
0x14001a1fa  lea     eax, [rcx+rdx]
0x14001a1fd  cmp     eax, r12d
0x14001a200  ja      short loc_14001A22A
0x14001a202  cmp     edx, r12d
0x14001a205  ja      short loc_14001A22A
0x14001a207  cmp     ecx, r12d
0x14001a20a  ja      short loc_14001A22A
0x14001a20c  mov     rcx, [rbx+0B8h]
0x14001a213  lea     rax, ClasspMiniportGetHybridInfoIoctlCompletion
0x14001a21a  mov     [rcx-10h], rax
0x14001a21e  lea     rax, [rdi+rdx]
0x14001a222  mov     [rcx-8], rax
0x14001a226  mov     byte ptr [rcx-45h], 0E0h
0x14001a22a  mov     rdx, rbx; Tag
0x14001a22d  mov     rcx, r15; DeviceObject
0x14001a230  call    ClassReleaseRemoveLock
0x14001a235  jmp     loc_14001C94B
0x14001a23a  sub     eax, 2D0944h
0x14001a23f  jz      loc_14001A48D
0x14001a245  sub     eax, 2D0h
0x14001a24a  jz      loc_14001A387
0x14001a250  sub     eax, 46Ch
0x14001a255  jz      loc_14001A310
0x14001a25b  cmp     eax, 4
0x14001a25e  jnz     loc_14001C271
0x14001a264  test    rsi, rsi
0x14001a267  jz      short loc_14001A27A
0x14001a269  xor     edx, edx; Tag
0x14001a26b  mov     rcx, rsi; P
0x14001a26e  call    cs:__imp_ExFreePoolWithTag
0x14001a275  nop     dword ptr [rax+rax+00h]
0x14001a27a  cmp     dword ptr [r12+8], 28h ; '('
0x14001a280  jb      short loc_14001A2E2
0x14001a282  mov     rdx, [r14+18h]
0x14001a286  xor     edi, edi
0x14001a288  mov     r8, [rbx+18h]
0x14001a28c  mov     dword ptr [r8], 28h ; '('
0x14001a293  mov     dword ptr [r8+4], 28h ; '('
0x14001a29b  mov     rax, [rdx+8]
0x14001a29f  mov     ecx, [rax+48h]
0x14001a2a2  mov     [r8+0Ch], ecx
0x14001a2a6  mov     eax, [rdx+24Ch]
0x14001a2ac  mov     [r8+10h], eax
0x14001a2b0  mov     eax, [r14+88h]
0x14001a2b7  mov     dword ptr [r8+8], 0
0x14001a2bf  mov     [r8+24h], eax
0x14001a2c3  mov     rax, [rdx+490h]
0x14001a2ca  mov     ecx, [rax]
0x14001a2cc  mov     [r8+8], ecx
0x14001a2d0  mov     rax, [rdx+490h]
  ... truncated ...
```
