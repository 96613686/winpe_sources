# TxfStartRm

- ea: `0x14025a2c8`
- end: `0x14025cc93`
- name: `TxfStartRm`
- size: `10699`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400fe104`
- `0x1401f4220`

## callees

- `0x140007ea0`
- `0x140008740`
- `0x14000c290`
- `0x14000c450`
- `0x14000cb00`
- `0x14000d1e0`
- `0x140010be0`
- `0x140012e70`
- `0x140020de0`
- `0x1400365b0`
- `0x140038398`
- `0x14003c804`
- `0x14003e410`
- `0x14003e734`
- `0x1400414f4`
- `0x14004173c`
- `0x140049c90`
- `0x140051c0c`
- `0x140051e20`
- `0x140051ed4`
- `0x140051fb0`
- `0x140059250`
- `0x1400593c0`
- `0x1400596c0`
- `0x1400fa3d8`
- `0x140140380`
- `0x14017517c`
- `0x140191158`
- `0x1401919d0`
- `0x140192f44`
- `0x140193844`
- `0x1401aab20`
- `0x1401d2c34`
- `0x1401d2f50`
- `0x140209fc4`
- `0x14020a724`
- `0x14020b5f4`
- `0x14025a01c`
- `0x14025a2c8`
- `0x14025cc9c`
- `0x140262b6c`
- `0x140268014`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14025b378`
- `ntoskrnl!ObfDereferenceObject` at `0x14025b378`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14025ab17`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14025ab17`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14025ab29`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14025ab29`
- `ntoskrnl!ExUuidCreate` at `0x14025bb4d`
- `ntoskrnl!ExUuidCreate` at `0x14025bb4d`
- `ntoskrnl!KeResetEvent` at `0x14025a7bc`
- `ntoskrnl!KeResetEvent` at `0x14025a7bc`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14025b343`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14025b343`
- `ntoskrnl!FsRtlGetVirtualDiskNestingLevel` at `0x14025b360`
- `ntoskrnl!FsRtlGetVirtualDiskNestingLevel` at `0x14025b3a4`
- `ntoskrnl!FsRtlGetVirtualDiskNestingLevel` at `0x14025b360`
- `ntoskrnl!FsRtlGetVirtualDiskNestingLevel` at `0x14025b3a4`
- `ntoskrnl!ZwRecoverTransactionManager` at `0x14025b8ab`
- `ntoskrnl!ZwRecoverTransactionManager` at `0x14025b8ab`
- `ntoskrnl!ZwQueryInformationTransactionManager` at `0x14025ba6f`
- `ntoskrnl!ZwQueryInformationTransactionManager` at `0x14025ba6f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14025a514`
- `ntoskrnl!RtlInitUnicodeString` at `0x14025a52b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14025a514`
- `ntoskrnl!RtlInitUnicodeString` at `0x14025a52b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14025c0fd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14025c0fd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14025a6f3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14025a72f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14025a7cb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14025aa75`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14025ae63`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14025ae93`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14025a6f3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14025a72f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14025a7cb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14025aa75`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14025ae63`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14025ae93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025c893`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025cacf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025caf4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025cb12`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025cb33`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025cb54`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025cb75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025cb96`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b9617`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b9639`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b965e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b9683`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b96a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b96cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b96f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025c893`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025cacf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025caf4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025cb12`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025cb33`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025cb54`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025cb75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025cb96`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b9617`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b9639`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b965e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b9683`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b96a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b96cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b96f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025a451`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025a48b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025a4b1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025a4d8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025a560`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025b577`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025b99d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025c4d7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025a451`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025a48b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025a4b1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025a4d8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025a560`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025b577`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025b99d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025c4d7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14025a62f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14025a7a2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14025a955`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14025adb3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14025a62f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14025a7a2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14025a955`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14025adb3`
- `ntoskrnl!ExAcquireFastMutex` at `0x14025c082`
- `ntoskrnl!ExAcquireFastMutex` at `0x14025c7f2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14025c836`
- `ntoskrnl!ExAcquireFastMutex` at `0x14025c082`
- `ntoskrnl!ExAcquireFastMutex` at `0x14025c7f2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14025c836`
- `ntoskrnl!ExReleaseFastMutex` at `0x14025c0db`
- `ntoskrnl!ExReleaseFastMutex` at `0x14025c882`
- `ntoskrnl!ExReleaseFastMutex` at `0x14025c0db`
- `ntoskrnl!ExReleaseFastMutex` at `0x14025c882`
- `ntoskrnl!RtlCompareMemory` at `0x14025bafc`
- `ntoskrnl!RtlCompareMemory` at `0x14025bb30`
- `ntoskrnl!RtlCompareMemory` at `0x14025c43f`
- `ntoskrnl!RtlCompareMemory` at `0x14025bafc`
- `ntoskrnl!RtlCompareMemory` at `0x14025bb30`
- `ntoskrnl!RtlCompareMemory` at `0x14025c43f`
- `ntoskrnl!KeDelayExecutionThread` at `0x14025bb8d`
- `ntoskrnl!KeDelayExecutionThread` at `0x14025bb8d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x14025b9df`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x14025c51c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x14025b9df`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x14025c51c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14025bccd`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14025c6ff`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14025c7d4`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14025bccd`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14025c6ff`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14025c7d4`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14025c0a0`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14025c676`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14025c68e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14025c795`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14025c804`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14025c848`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14025c0a0`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14025c676`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14025c68e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14025c795`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14025c804`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14025c848`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14025c71e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14025c71e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReserveAndAppendLog` at `0x14025bf41`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReserveAndAppendLog` at `0x14025bf41`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x14025cc4f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x14025cc4f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadRestartArea` at `0x14025bd58`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadRestartArea` at `0x14025c383`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadRestartArea` at `0x14025bd58`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadRestartArea` at `0x14025c383`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateMarshallingArea` at `0x14025b79d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateMarshallingArea` at `0x14025b79d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtSetLogFileSize` at `0x14025b6b6`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtSetLogFileSize` at `0x14025b6b6`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtRegisterManagedClient` at `0x14025b49e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtRegisterManagedClient` at `0x14025b49e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsPrivGetBaseLogFileFromFileObjectPointer` at `0x14025b322`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsPrivGetBaseLogFileFromFileObjectPointer` at `0x14025b322`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x14025ac1e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x14025b1e1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x14025ac1e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x14025b1e1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x14025b5fe`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x14025b5fe`

## pseudocode

```c
__int64 __fastcall TxfStartRm(__int64 a1, CLFS_LSN a2, _DWORD *a3, _BYTE *a4)
{
  CLFS_LSN v4; // rbx
  __int64 v6; // rsi
  unsigned __int64 v7; // r13
  unsigned __int64 v8; // rax
  unsigned int v9; // edi
  _BYTE *v10; // r12
  struct _CLFS_MGMT_CLIENT_REGISTRATION *PoolWithTag; // rax
  UNICODE_STRING *v13; // r15
  USHORT v14; // ax
  PUNICODE_STRING v15; // r15
  WCHAR *v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  NTSTATUS MarshallingArea; // ebx
  __int64 v20; // r9
  int v21; // r9d
  __int64 v22; // rdx
  unsigned int v23; // eax
  __int64 v24; // r8
  int v25; // ecx
  unsigned int v26; // ecx
  int v27; // ecx
  __int64 v28; // r8
  __int64 v29; // r8
  signed __int64 v30; // rdx
  signed __int64 v31; // rcx
  signed __int64 v32; // rax
  signed __int64 v33; // rcx
  signed __int64 v34; // rax
  __int64 v35; // r8
  signed __int64 v36; // rdx
  signed __int64 v37; // rcx
  signed __int64 v38; // rax
  signed __int64 v39; // rcx
  signed __int64 v40; // rax
  CLFS_LSN v41; // rax
  USHORT v42; // cx
  UNICODE_STRING *v43; // rbx
  struct _UNICODE_STRING *v44; // rdi
  int v45; // eax
  ULONG fLogOptionFlag; // ebx
  __int64 v47; // rax
  void *pvContext; // r8
  ULONG cbContext; // ecx
  ULONG v50; // r9d
  NTSTATUS LogFile; // eax
  char v52; // di
  unsigned __int64 v53; // rax
  __int64 v54; // rcx
  unsigned __int64 v55; // rax
  __int64 v56; // rcx
  int v57; // ecx
  int v58; // ecx
  __int64 v59; // r9
  unsigned int v60; // eax
  CLFS_LSN v61; // rbx
  int v62; // ecx
  __int64 v63; // r8
  _DWORD *ullOffset; // r10
  __int16 v65; // ax
  __int16 v66; // cx
  __int64 v67; // rax
  ULONG v68; // ebx
  __int64 v69; // rax
  void *v70; // rdx
  ULONG v71; // r10d
  ULONG v72; // r9d
  _QWORD *v73; // rdi
  __int64 v74; // r8
  unsigned __int64 v75; // rax
  __int64 v76; // r13
  unsigned __int64 v77; // rax
  __int64 v78; // r12
  int v79; // edi
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rdi
  PCLFS_MGMT_CLIENT_REGISTRATION v81; // rbx
  CLFS_LSN v82; // rdi
  int TmInstance; // eax
  PCUNICODE_STRING v84; // rbx
  PCLFS_MGMT_POLICY v85; // rcx
  USHORT v86; // ax
  PCUNICODE_STRING v87; // rbx
  HANDLE *v88; // rdi
  NTSTATUS v89; // eax
  NTSTATUS v90; // ecx
  unsigned __int64 v91; // rax
  __int64 v92; // r13
  unsigned __int64 v93; // rax
  __int64 v94; // r12
  int v95; // edi
  void *v96; // rcx
  unsigned int v97; // ebx
  UUID *v98; // rbx
  NTSTATUS restarted; // eax
  int v100; // ecx
  unsigned int v101; // eax
  __int64 v102; // r13
  __int64 v103; // r12
  int v104; // edi
  unsigned __int64 v105; // rdi
  unsigned int v106; // eax
  volatile signed __int64 *v107; // rbx
  signed __int64 v108; // rdx
  int KtmResourceManagerObject; // eax
  unsigned int v110; // eax
  int v111; // ecx
  int v112; // ecx
  int v113; // ecx
  CLFS_INFORMATION *v114; // rbx
  int v115; // ecx
  __int64 v116; // r8
  unsigned __int64 v117; // rax
  __int64 v118; // r13
  unsigned __int64 v119; // rax
  __int64 v120; // r12
  const CLFS_LSN *v121; // r12
  const CLFS_LSN *v122; // rbx
  BOOLEAN v123; // al
  int v124; // ecx
  BOOLEAN v125; // al
  int v126; // ecx
  void *v127; // rdi
  BOOLEAN v128; // al
  struct _FAST_MUTEX *v129; // rcx
  volatile signed __int64 *v130; // rbx
  signed __int64 v131; // rcx
  signed __int64 v132; // rdx
  _BYTE *v133; // r15
  PUNICODE_STRING v134; // rdi
  PWSTR Buffer; // rcx
  char v136; // al
  __int64 v137; // rdx
  __int64 v138; // r8
  NTSTATUS VirtualDiskNestingLevel; // [rsp+90h] [rbp-1C8h]
  unsigned __int64 v140; // [rsp+98h] [rbp-1C0h]
  char v141; // [rsp+A1h] [rbp-1B7h]
  _WORD v142[7]; // [rsp+A2h] [rbp-1B6h] BYREF
  CLFS_LSN plsn1; // [rsp+B0h] [rbp-1A8h] BYREF
  ULONG pcbInfoBuffer; // [rsp+B8h] [rbp-1A0h] BYREF
  ULONG v145; // [rsp+BCh] [rbp-19Ch]
  ULONG v146; // [rsp+C0h] [rbp-198h] BYREF
  ULONG NestingLevel; // [rsp+C4h] [rbp-194h] BYREF
  PCUNICODE_STRING Source; // [rsp+C8h] [rbp-190h]
  PCLFS_MGMT_POLICY Policy; // [rsp+D0h] [rbp-188h]
  CLFS_LSN plsnUndoNext; // [rsp+D8h] [rbp-180h] BYREF
  UUID *Uuid; // [rsp+E0h] [rbp-178h]
  ULONG pcbRestartBuffer; // [rsp+E8h] [rbp-170h] BYREF
  signed __int32 v153; // [rsp+ECh] [rbp-16Ch]
  _BYTE *v154; // [rsp+F0h] [rbp-168h]
  PUNICODE_STRING puszLogFileName; // [rsp+F8h] [rbp-160h]
  PCLFS_MGMT_CLIENT_REGISTRATION RegistrationData; // [rsp+100h] [rbp-158h]
  void *Source1; // [rsp+108h] [rbp-150h]
  PVOID ppvRestartBuffer; // [rsp+110h] [rbp-148h] BYREF
  int v159; // [rsp+118h] [rbp-140h]
  __int64 v160; // [rsp+120h] [rbp-138h]
  __int64 v161; // [rsp+128h] [rbp-130h] BYREF
  unsigned __int64 ResultingSizeInContainers; // [rsp+130h] [rbp-128h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+138h] [rbp-120h] BYREF
  CLFS_LSN plsn; // [rsp+140h] [rbp-118h] BYREF
  __int64 v165; // [rsp+148h] [rbp-110h]
  unsigned __int64 NewSizeInContainers[3]; // [rsp+150h] [rbp-108h] BYREF
  CLFS_WRITE_ENTRY rgWriteEntries; // [rsp+168h] [rbp-F0h] BYREF
  __int16 v168; // [rsp+178h] [rbp-E0h]
  __int64 v169; // [rsp+180h] [rbp-D8h]
  __int16 v170; // [rsp+188h] [rbp-D0h]
  __int64 v171; // [rsp+190h] [rbp-C8h]
  __int128 TransactionManagerInformation; // [rsp+198h] [rbp-C0h] BYREF
  _OWORD v173[6]; // [rsp+1B0h] [rbp-A8h] BYREF

  plsn1.ullOffset = (ULONGLONG)a3;
  v4 = a2;
  plsnUndoNext = a2;
  v160 = a1;
  NewSizeInContainers[1] = a2.ullOffset;
  v6 = *(_QWORD *)(a2.ullOffset + 320);
  v165 = v6;
  v7 = *(_QWORD *)(v6 + 16);
  v140 = v7;
  NewSizeInContainers[2] = v7;
  ppvRestartBuffer = 0;
  pcbRestartBuffer = 0;
  plsn.ullOffset = 0;
  v141 = 0;
  HIBYTE(v142[0]) = 0;
  *(_QWORD *)&v142[3] = 0;
  RegistrationData = 0;
  if ( (*a3 & 2) != 0 )
    v8 = (unsigned int)a3[4];
  else
    v8 = 2;
  NewSizeInContainers[0] = v8;
  ResultingSizeInContainers = 0;
  Source1 = 0;
  Uuid = 0;
  Policy = 0;
  Source = 0;
  puszLogFileName = 0;
  TransactionManagerInformation = 0;
  pcbInfoBuffer = 0;
  v9 = 0;
  v10 = (char *)v142 + 1;
  if ( a4 )
    v10 = a4;
  v154 = v10;
  if ( *v10 )
  {
    NtfsReleaseVcb(a1, v7);
    *v10 = 0;
  }
  if ( (*(_DWORD *)(v7 + 4) & 0x2000000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225634LL, 2648805);
    return 3221225634LL;
  }
  PoolWithTag = (struct _CLFS_MGMT_CLIENT_REGISTRATION *)ExAllocatePoolWithTag(
                                                           (POOL_TYPE)(PoolType | 0x10),
                                                           0x38u,
                                                           0x75667854u);
  RegistrationData = PoolWithTag;
  *(_OWORD *)&PoolWithTag->Version = 0;
  *(_OWORD *)&PoolWithTag->AdvanceTailCallbackData = 0;
  *(_OWORD *)&PoolWithTag->LogGrowthCompleteCallbackData = 0;
  PoolWithTag->LogUnpinnedCallbackData = 0;
  Source1 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x10u, 0x30667854u);
  Uuid = (UUID *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x10u, 0x30667854u);
  v13 = (UNICODE_STRING *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x50u, 0x30667854u);
  Source = v13;
  memset(v13, 0, 0x50u);
  puszLogFileName = v13 + 1;
  RtlInitUnicodeString(v13 + 3, L"%BLF%\\$TxfLogContainer");
  RtlInitUnicodeString(v13 + 4, L"\\??\\log:");
  v14 = v13[4].Length + 530;
  v15 = puszLogFileName;
  puszLogFileName->MaximumLength = v14;
  v16 = (WCHAR *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v14, 0x30667854u);
  v15->Buffer = v16;
  memset(v16, 0, v15->MaximumLength);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 132), 4, 4) != 3 )
  {
LABEL_15:
    LOBYTE(v17) = 1;
    NtfsAcquireSharedVcb(a1, v7, v17);
    *v10 = 1;
    if ( (*(_DWORD *)(v7 + 4) & 0x8000823) != 1 )
    {
      v20 = 0;
      if ( NtfsStatusDebugFlags )
      {
        NtfsStatusTraceAndDebugInternal(0, 3221226094LL, 2648878);
        v20 = 0;
      }
      MarshallingArea = -1073741202;
      goto LABEL_493;
    }
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v7 + 6256));
    v21 = *(_DWORD *)(v7 + 6436);
    if ( (v21 & 1) != 0 )
    {
      if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v22 = *(_QWORD *)(v7 + 248);
        v23 = *(unsigned __int16 *)(v22 + 6);
        if ( v23 > 0x40 || (v23 & 1) != 0 )
        {
          LOWORD(v23) = 0;
          v159 = 0;
        }
        else
        {
          v159 = *(unsigned __int16 *)(v22 + 6);
        }
        v168 = v23;
        v169 = v22 + 32;
        McTemplateU0ppwwd_EtwWriteTransfer(
          *(unsigned __int16 *)(v7 + 7872) >> 1,
          (unsigned int)txfcallbacks_c27445,
          (unsigned int)KeGetCurrentThread(),
          v7,
          *(_WORD *)(v7 + 7872) >> 1,
          *(_QWORD *)(v7 + 7880),
          (unsigned __int16)v23 >> 1,
          v22 + 32,
          v21);
      }
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v7 + 6256));
      v20 = 0;
      MarshallingArea = -1073741790;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_493;
      v24 = 2648897;
      goto LABEL_31;
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v7 + 6256));
    v153 = _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 132), 1, 0);
    if ( v153 )
    {
      v20 = 0;
      MarshallingArea = 1075380277;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_493;
      v24 = 2648917;
      goto LABEL_31;
    }
    v25 = *(_DWORD *)(v6 + 128);
    if ( (*(_DWORD *)plsn1.ullOffset & 0x200) != 0 )
      v26 = v25 | 0x2000;
    else
      v26 = v25 & 0xFFFFDFFF;
    *(_DWORD *)(v6 + 128) = v26;
    _InterlockedAnd((volatile signed __int32 *)(v6 + 136), 0xFBFFFFFF);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v7 + 6256));
    ++*(_DWORD *)(v7 + 6432);
    KeResetEvent((PRKEVENT)(v7 + 6440));
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v7 + 6256));
    v141 = 1;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))NtfsAcquireSharedFcb)(a1, (CLFS_LSN)v4.ullOffset, 0, 0);
    memset(v173, 0, 56);
    if ( (unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))TxfReadTxfDataAttribute)(
                            a1,
                            (CLFS_LSN)v4.ullOffset,
                            v173) )
      v9 = v173[3] & 0xFFF00000;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))NtfsReleaseFcbEx)(a1, (CLFS_LSN)v4.ullOffset, 0);
    NtfsReleaseVcb(a1, v7);
    v20 = 0;
    *v154 = 0;
    if ( (v9 & 0x200000) != 0 )
    {
      if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v27,
          (unsigned int)txfcallbacks_c27548,
          (unsigned int)"TxfStartRm",
          v6,
          v6 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3222863878LL, 2648996);
      NtfsRaiseStatusInternal(a1, -1072103418, 0, 0, 2648996);
    }
    if ( (*(_DWORD *)(v6 + 128) & 0x400) == 0 )
    {
      v28 = *(_QWORD *)(v7 + 304) - (*(__int64 *)(v7 + 328) >> 8) - *(_QWORD *)(v7 + 6368) - *(_QWORD *)(v7 + 328);
      if ( v28 <= 0 )
        v28 = v20;
      if ( v28 <= (*(unsigned int *)(v7 + 480) + 0x400000LL) >> *(_BYTE *)(v7 + 488) )
      {
        NtfsAllocateDiskFullContext(a1, 0x400000, 0x27F00286BC1LL);
        v20 = 0;
        MarshallingArea = -1073741697;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_493;
        v24 = 2649026;
        goto LABEL_31;
      }
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v7 + 6376));
      *(_QWORD *)(v7 + 6368) += (*(unsigned int *)(v7 + 480) + 0x400000LL) >> *(_BYTE *)(v7 + 488);
      v29 = *(_QWORD *)(v7 + 6368);
      if ( v29 > *(_QWORD *)(v7 + 8336) )
        *(_QWORD *)(v7 + 8336) = v29;
      v30 = *(_QWORD *)(v7 + 304) - (*(__int64 *)(v7 + 328) >> 8) - v29 - *(_QWORD *)(v7 + 328);
      if ( v30 <= 0 )
        v30 = 0;
      do
      {
        v31 = *(_QWORD *)(v7 + 8344);
        v32 = v31;
        if ( v30 < v31 )
          v32 = _InterlockedCompareExchange64((volatile signed __int64 *)(v7 + 8344), v30, v31);
      }
      while ( v32 != v31 );
      do
      {
        v33 = *(_QWORD *)(v7 + 8352);
        v34 = v33;
        if ( v30 > v33 )
          v34 = _InterlockedCompareExchange64((volatile signed __int64 *)(v7 + 8352), v30, v33);
      }
      while ( v34 != v33 );
      v35 = *(_QWORD *)(v7 + 6368);
      *(_QWORD *)(v7 + 6368) = v35;
      if ( v35 < *(_QWORD *)(v7 + 8328) )
        *(_QWORD *)(v7 + 8328) = v35;
      v36 = *(_QWORD *)(v7 + 304) - (*(__int64 *)(v7 + 328) >> 8) - v35 - *(_QWORD *)(v7 + 328);
      if ( v36 <= 0 )
        v36 = 0;
      do
      {
        v37 = *(_QWORD *)(v7 + 8344);
        v38 = v37;
        if ( v36 < v37 )
          v38 = _InterlockedCompareExchange64((volatile signed __int64 *)(v7 + 8344), v36, v37);
      }
      while ( v38 != v37 );
      do
      {
        v39 = *(_QWORD *)(v7 + 8352);
        v40 = v39;
        if ( v36 > v39 )
          v40 = _InterlockedCompareExchange64((volatile signed __int64 *)(v7 + 8352), v36, v39);
      }
      while ( v40 != v39 );
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v7 + 6376));
      *(_DWORD *)(v6 + 128) |= 0x400u;
      v20 = 0;
    }
    v41 = plsn1;
    v42 = *(_WORD *)(plsn1.ullOffset + 40);
    v43 = (UNICODE_STRING *)Source;
    Source->MaximumLength = v42;
    v43->Length = v42;
    v43->Buffer = (PWSTR)(v41.ullOffset + 44);
    if ( v42 > 0x1FEu )
    {
      MarshallingArea = -1073741811;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_493;
      v24 = 2649044;
      goto LABEL_31;
    }
    v44 = v43 + 1;
    RtlCopyUnicodeString(v43 + 1, v43 + 4);
    RtlAppendUnicodeStringToString(v43 + 1, v43);
    v45 = *(_DWORD *)(v6 + 128);
    if ( (v45 & 0x8000000) != 0 )
    {
      *(_DWORD *)(v6 + 128) = v45 & 0xF7FFFFFF;
      v20 = 0;
      MarshallingArea = -1072037879;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_493;
      v24 = 2649076;
      goto LABEL_31;
    }
    NtfsPurgeFileRecordCache(a1);
    *(_DWORD *)(a1 + 4) |= 0x200u;
    fLogOptionFlag = 24;
    if ( v6 != *(_QWORD *)(*(_QWORD *)(v6 + 16) + 6248LL) )
      fLogOptionFlag = 8;
    v145 = fLogOptionFlag;
    if ( (unsigned int)Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline()
      && v6 == *(_QWORD *)(*(_QWORD *)(v6 + 16) + 6248LL) )
    {
      fLogOptionFlag |= 0x1000000u;
      v145 = fLogOptionFlag;
    }
    v47 = *(_QWORD *)(v6 + 16);
    if ( v6 == *(_QWORD *)(v47 + 6248) )
      pvContext = *(void **)(*(_QWORD *)(v7 + 248) + 8LL);
    else
      pvContext = 0;
    cbContext = 336;
    if ( v6 != *(_QWORD *)(v47 + 6248) )
      cbContext = 0;
    v50 = 3;
    if ( v6 == *(_QWORD *)(v47 + 6248) )
      v50 = 1;
    LogFile = ClfsCreateLogFile(
                (PPLOG_FILE_OBJECT)(v6 + 496),
                v44,
                0xC0000000,
                v50,
                0,
                1u,
                0,
                0,
                fLogOptionFlag,
                pvContext,
                cbContext);
    MarshallingArea = LogFile;
    *(_DWORD *)(a1 + 4) &= ~0x200u;
    if ( LogFile == -1073741772 )
    {
      v52 = 1;
    }
    else
    {
      v53 = (unsigned int)(LogFile + 1072037879);
      if ( (unsigned int)v53 <= 0x26 && (v54 = 0x4400600001LL, _bittest64(&v54, v53))
        || MarshallingArea == -1073741077
        || MarshallingArea == -1073741202
        || MarshallingArea == -1073741435
        || MarshallingArea == -1073741496
        || MarshallingArea == -1073741632
        || (v55 = (unsigned int)(MarshallingArea + 1073741697), (unsigned int)v55 <= 0x24)
        && (v56 = 0x1448000001LL, _bittest64(&v56, v55))
        || (unsigned int)(MarshallingArea + 1073741811) <= 0x15
        && (v57 = 2098243, _bittest(&v57, MarshallingArea + 1073741811))
        || MarshallingArea == -2147483626 )
      {
        v20 = 0;
        if ( !NtfsStatusDebugFlags
          || !MarshallingArea
          || MarshallingArea == 294
          || (unsigned int)(MarshallingArea - 298) <= 1
          || (unsigned int)MarshallingArea >= 0xFFFFFFED
          || MarshallingArea == -1073741608
          || MarshallingArea == -1073741802
          || MarshallingArea == -1073741807
          || (unsigned int)(MarshallingArea + 2147483643) <= 1
          || MarshallingArea == 259 )
        {
          goto LABEL_493;
        }
        NtfsStatusTraceAndDebugInternal(0, (unsigned int)MarshallingArea, 2649145);
        goto LABEL_210;
      }
      v20 = 0;
      if ( MarshallingArea < 0 )
      {
        if ( NtfsStatusDebugFlags
          && (unsigned int)MarshallingArea < 0xFFFFFFED
          && MarshallingArea != -1073741802
          && MarshallingArea != -1073741807
          && (unsigned int)(MarshallingArea + 2147483643) > 1
          && MarshallingArea != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(0, (unsigned int)MarshallingArea, 2649154);
          v20 = 0;
        }
        goto LABEL_493;
      }
      v52 = 0;
    }
    LOBYTE(v17) = 1;
    NtfsAcquireExclusiveVcb(a1, v7, v17);
    *v154 = 1;
    if ( (*(_DWORD *)(v7 + 4) & 0x8000823) != 1 )
    {
      v20 = 0;
      if ( NtfsStatusDebugFlags )
      {
        NtfsStatusTraceAndDebugInternal(0, 3221226094LL, 2649177);
        v20 = 0;
      }
      MarshallingArea = -1073741202;
      goto LABEL_493;
    }
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v7 + 6256));
    v58 = *(_DWORD *)(v7 + 6436);
    if ( (v58 & 1) != 0 )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v59 = *(_QWORD *)(v7 + 248);
        v60 = *(unsigned __int16 *)(v59 + 6);
        if ( v60 > 0x40 || (v60 & 1) != 0 )
          v60 = 0;
        v153 = v60;
        v170 = v60;
        v171 = v59 + 32;
        McTemplateU0ppwwd_EtwWriteTransfer(
          v58,
          (unsigned int)txfcallbacks_c27750,
          (unsigned int)KeGetCurrentThread(),
          v7,
          *(_WORD *)(v7 + 7872) >> 1,
          *(_QWORD *)(v7 + 7880),
          (unsigned __int16)v60 >> 1,
          v59 + 32,
          v58);
      }
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v7 + 6256));
      v20 = 0;
      MarshallingArea = -1073741790;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_493;
      v24 = 2649202;
      goto LABEL_31;
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v7 + 6256));
    v61 = plsnUndoNext;
    TxfInitializeRootDirScb(a1);
    TxfInitializeTxfDir(a1, v52);
    TxfInitializeTopsStream(a1);
    if ( (*(_DWORD *)(v61.ullOffset + 4) & 0x40000) == 0 && v52 && v6 == *(_QWORD *)(*(_QWORD *)(v6 + 16) + 6248LL) )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))NtfsAcquireExclusiveFcb)(a1, (CLFS_LSN)v61.ullOffset, 0, 0);
      TxfAddTxfDataAttribute(a1, 1, 0, 0);
      NtfsCheckpointCurrentTransaction(a1);
    }
    *(_DWORD *)(a1 + 4) |= 0x400u;
    NtfsCleanupIrpContext(a1, 0);
    NtfsReleaseVcb(a1, v7);
    v20 = 0;
    *v154 = 0;
    if ( (*(_DWORD *)(v61.ullOffset + 4) & 0x40000) == 0 )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v62,
          (unsigned int)txfcallbacks_c27819,
          (unsigned int)"TxfStartRm",
          v6,
          v6 + 672);
        v20 = 0;
      }
      MarshallingArea = -1072103418;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_493;
      v63 = 2649268;
      goto LABEL_139;
    }
    NtfsPurgeFileRecordCache(a1);
    MarshallingArea = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))TxfMergeTopsDefaultSettingsWithSpecifiedSettings)(
                        a1,
                        *(_QWORD *)(v61.ullOffset + 320),
                        (CLFS_LSN)plsn1.ullOffset);
    v20 = 0;
    if ( MarshallingArea )
      goto LABEL_493;
    ullOffset = (_DWORD *)plsn1.ullOffset;
    v65 = *(_WORD *)(plsn1.ullOffset + 38) & 2;
    v66 = *(_WORD *)(plsn1.ullOffset + 38) & 1;
    if ( v66 )
    {
      if ( !v65 )
      {
        *(_DWORD *)(v6 + 128) &= ~0x10u;
LABEL_148:
        LODWORD(v18) = *(_DWORD *)(v6 + 128);
        LODWORD(v17) = *ullOffset;
        if ( (*ullOffset & 0x1000) != 0 && (v17 & 0x2000) != 0 )
        {
          v20 = 0;
          MarshallingArea = -1073741811;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_493;
          v24 = 2649354;
          goto LABEL_31;
        }
        v67 = *(_QWORD *)(v6 + 16);
        if ( v6 == *(_QWORD *)(v67 + 6248)
          && ((*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v67 + 248) + 16LL) + 48LL) & 0x100) != 0
           || (dword_1400956B8 & 0x100000) == 0) )
        {
          if ( (v17 & 0x2000) == 0 )
          {
            v20 = 0;
            MarshallingArea = -1073741811;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_493;
            v24 = 2649370;
            goto LABEL_31;
          }
        }
        else
        {
          if ( (*ullOffset & 0x1000) != 0 )
          {
            LODWORD(v18) = v18 & 0xFFFBFFFF;
            *(_DWORD *)(v6 + 128) = v18;
          }
          if ( (*ullOffset & 0x2000) == 0 )
          {
LABEL_162:
            if ( v52 )
            {
              *(_QWORD *)(v6 + 416) = CLFS_LSN_NULL_EXT;
              *(_QWORD *)(v6 + 424) = CLFS_LSN_NULL_EXT;
              *(_QWORD *)(v6 + 448) = CLFS_LSN_NULL_EXT;
              NtfsPurgeFileRecordCache(a1);
              *(_DWORD *)(a1 + 4) |= 0x200u;
              v68 = 24;
              if ( v6 != *(_QWORD *)(*(_QWORD *)(v6 + 16) + 6248LL) )
                v68 = 8;
              v145 = v68;
              if ( (unsigned int)Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline()
                && v6 == *(_QWORD *)(*(_QWORD *)(v6 + 16) + 6248LL) )
              {
                v68 |= 0x1000000u;
                v145 = v68;
              }
              v69 = *(_QWORD *)(v6 + 16);
              if ( v6 == *(_QWORD *)(v69 + 6248) )
                v70 = *(void **)(*(_QWORD *)(v7 + 248) + 8LL);
              else
                v70 = 0;
              v71 = 336;
              if ( v6 != *(_QWORD *)(v69 + 6248) )
                v71 = 0;
              v72 = 3;
              if ( v6 == *(_QWORD *)(v69 + 6248) )
                v72 = 1;
              v73 = (_QWORD *)(v6 + 496);
              MarshallingArea = ClfsCreateLogFile(
                                  (PPLOG_FILE_OBJECT)(v6 + 496),
                                  puszLogFileName,
                                  0xC0000000,
                                  v72,
                                  0,
                                  2u,
                                  0,
                                  0,
                                  v68,
                                  v70,
                                  v71);
              *(_DWORD *)(a1 + 4) &= ~0x200u;
              v20 = 0;
              if ( MarshallingArea < 0 )
              {
                if ( !NtfsStatusDebugFlags
                  || (unsigned int)MarshallingArea >= 0xFFFFFFED
                  || MarshallingArea == -1073741802
                  || MarshallingArea == -1073741807
                  || (unsigned int)(MarshallingArea + 2147483643) <= 1
                  || MarshallingArea == -1073741608 )
                {
                  goto LABEL_184;
                }
                v74 = 2649446;
LABEL_183:
                NtfsStatusTraceAndDebugInternal(0, (unsigned int)MarshallingArea, v74);
                v20 = 0;
LABEL_184:
                if ( MarshallingArea == -1073741801 )
                  goto LABEL_396;
                v75 = (unsigned int)(MarshallingArea + 1073741697);
LABEL_186:
                if ( (unsigned int)v75 > 0x22 || (v76 = 0x408000001LL, !_bittest64(&v76, v75)) )
                {
                  if ( MarshallingArea != -1072037845
                    && MarshallingArea != -1073741202
                    && MarshallingArea != -1073741435
                    && MarshallingArea != -1073741496 )
                  {
                    v77 = (unsigned int)(MarshallingArea + 1073741667);
                    if ( (unsigned int)v77 > 0x23 || (v78 = 0x800000041LL, !_bittest64(&v78, v77)) )
                    {
                      if ( (unsigned int)(MarshallingArea + 1073741811) > 0x15
                        || (v79 = 2097219, !_bittest(&v79, MarshallingArea + 1073741811)) )
                      {
                        if ( MarshallingArea != -2147483626 && MarshallingArea != -1072037841 )
                          goto LABEL_493;
                      }
                    }
                  }
                  goto LABEL_198;
                }
LABEL_396:
                ++HIDWORD((*TxfData)[1]);
                goto LABEL_493;
              }
            }
            else
            {
              v73 = (_QWORD *)(v6 + 496);
            }
            if ( v6 != *(_QWORD *)(*(_QWORD *)(v6 + 16) + 6248LL) )
            {
              v161 = 0;
              NestingLevel = 0;
              v146 = 0;
              ClfsPrivGetBaseLogFileFromFileObjectPointer(*v73, &v161);
              if ( v161 )
              {
                AttachedDeviceReference = IoGetAttachedDeviceReference(*(PDEVICE_OBJECT *)(v161 + 8));
                VirtualDiskNestingLevel = FsRtlGetVirtualDiskNestingLevel(AttachedDeviceReference, &NestingLevel, 0);
                ObfDereferenceObject(AttachedDeviceReference);
                if ( VirtualDiskNestingLevel >= 0
                  && FsRtlGetVirtualDiskNestingLevel(*(PDEVICE_OBJECT *)(*(_QWORD *)(v7 + 248) + 16LL), &v146, 0) >= 0
                  && NestingLevel > v146 )
                {
                  MarshallingArea = -1073740761;
                  if ( NtfsStatusDebugFlags )
                    NtfsStatusTraceAndDebugInternal(0, 3221226535LL, 2649487);
                  if ( (*(_DWORD *)(v7 + 16) & 0x100000LL) == 0
                    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
                  {
                    McTemplateU0spjdd_EtwWriteTransfer(v6 + 672, v18, v17, v6, v6 + 672, NestingLevel, v146);
                  }
LABEL_210:
                  v20 = 0;
                  goto LABEL_493;
                }
              }
            }
            v81 = RegistrationData;
            RegistrationData->Version = 1;
            v81->AdvanceTailCallback = (PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK)TxfAdvanceBaseLsnRequiredNotification;
            v81->AdvanceTailCallbackData = (PVOID)v6;
            v81->LogGrowthCompleteCallback = (PCLFS_CLIENT_LFF_HANDLER_COMPLETE_CALLBACK)TxfLogFullHandlerCompletionNotification;
            v81->LogGrowthCompleteCallbackData = (PVOID)v6;
            v81->LogUnpinnedCallback = (PCLFS_CLIENT_LOG_UNPINNED_CALLBACK)TxfLogUnpinnedNotification;
            v81->LogUnpinnedCallbackData = (PVOID)v6;
            NtfsPurgeFileRecordCache(a1);
            *(_DWORD *)(a1 + 4) |= 0x200u;
            MarshallingArea = ClfsMgmtRegisterManagedClient(
                                *(PLOG_FILE_OBJECT *)(v6 + 496),
                                v81,
                                (PCLFS_MGMT_CLIENT)(v6 + 560));
            *(_DWORD *)(a1 + 4) &= ~0x200u;
            v20 = 0;
            if ( MarshallingArea < 0 )
            {
              if ( !NtfsStatusDebugFlags
                || (unsigned int)MarshallingArea >= 0xFFFFFFED
                || MarshallingArea == -1073741802
                || MarshallingArea == -1073741807
                || (unsigned int)(MarshallingArea + 2147483643) <= 1
                || MarshallingArea == -1073741608 )
              {
                goto LABEL_184;
              }
              v74 = 2649533;
              goto LABEL_183;
            }
            *(_BYTE *)(v6 + 572) = 1;
            v82 = plsn1;
            TmInstance = TxfConvertRmPoliciesToClfsPolicies(a1);
            MarshallingArea = TmInstance;
            v20 = 0;
            if ( TmInstance < 0 )
              goto LABEL_220;
            v84 = Source;
            Policy = (PCLFS_MGMT_POLICY)ExAllocatePoolWithTag(
                                          (POOL_TYPE)(PoolType | 0x10),
                                          Source[3].Length + 24LL,
                                          0x30667854u);
            memset(Policy, 0, v84[3].Length + 24LL);
            v85 = Policy;
            Policy->Version = 1;
            v85->LengthInBytes = v84[3].Length + 24;
            v85->PolicyFlags |= 1u;
            v85->PolicyType = ClfsMgmtPolicyNewContainerPrefix;
            v85->PolicyParameters.NewContainerPrefix.PrefixLengthInBytes = v84[3].Length;
            memmove((char *)&v85->PolicyParameters + 2, v84[3].Buffer, v84[3].Length);
            NtfsPurgeFileRecordCache(a1);
            *(_DWORD *)(a1 + 4) |= 0x200u;
            MarshallingArea = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(v6 + 496), Policy, v84[3].Length + 24);
            *(_DWORD *)(a1 + 4) &= ~0x200u;
            v20 = 0;
            if ( MarshallingArea == -1072037865 )
              MarshallingArea = 0;
            if ( MarshallingArea < 0 )
            {
              if ( !NtfsStatusDebugFlags
                || (unsigned int)MarshallingArea >= 0xFFFFFFED
                || MarshallingArea == -1073741802
                || MarshallingArea == -1073741807
                || (unsigned int)(MarshallingArea + 2147483643) <= 1
                || MarshallingArea == -1073741608 )
              {
                goto LABEL_184;
              }
              v74 = 2649596;
              goto LABEL_183;
            }
            NtfsPurgeFileRecordCache(a1);
            *(_DWORD *)(a1 + 4) |= 0x200u;
            MarshallingArea = ClfsMgmtSetLogFileSize(
                                *(PLOG_FILE_OBJECT *)(v6 + 496),
                                NewSizeInContainers,
                                &ResultingSizeInContainers,
                                0,
                                0);
            *(_DWORD *)(a1 + 4) &= ~0x200u;
            v20 = 0;
            if ( MarshallingArea == -1072037865 )
              MarshallingArea = 0;
            if ( MarshallingArea < 0 && (MarshallingArea != -2145845239 || ResultingSizeInContainers < 2) )
            {
              if ( !NtfsStatusDebugFlags
                || (unsigned int)MarshallingArea >= 0xFFFFFFED
                || MarshallingArea == -1073741802
                || MarshallingArea == -1073741807
                || (unsigned int)(MarshallingArea + 2147483643) <= 1
                || MarshallingArea == -1073741608 )
              {
                goto LABEL_184;
              }
              v74 = 2649635;
              goto LABEL_183;
            }
            NtfsPurgeFileRecordCache(a1);
            *(_DWORD *)(a1 + 4) |= 0x200u;
            MarshallingArea = ClfsCreateMarshallingArea(
                                *(PLOG_FILE_OBJECT *)(v6 + 496),
                                PoolType,
                                0,
                                0,
                                0x40000u,
                                0xAu,
                                0x14u,
                                (PVOID *)(v6 + 512));
            *(_DWORD *)(a1 + 4) &= ~0x200u;
            v20 = 0;
            if ( MarshallingArea < 0 )
            {
              if ( !NtfsStatusDebugFlags
                || (unsigned int)MarshallingArea >= 0xFFFFFFED
                || MarshallingArea == -1073741802
                || MarshallingArea == -1073741807
                || (unsigned int)(MarshallingArea + 2147483643) <= 1
                || MarshallingArea == -1073741608 )
              {
                goto LABEL_184;
              }
              v74 = 2649667;
              goto LABEL_183;
            }
            _InterlockedAnd((volatile signed __int32 *)(v6 + 136), 0xFFFBFFFF);
            v86 = *(_WORD *)(v82.ullOffset + 36);
            v87 = Source;
            Source[2].MaximumLength = v86;
            v87[2].Length = v86;
            v87[2].Buffer = (PWSTR)(v82.ullOffset + *(unsigned int *)(v82.ullOffset + 32));
            NtfsPurgeFileRecordCache(a1);
            *(_DWORD *)(a1 + 4) |= 0x200u;
            v88 = (HANDLE *)(v6 + 664);
            TmInstance = TxfCreateTmInstance(v6, &v87[2], v6 + 664);
            MarshallingArea = TmInstance;
            *(_DWORD *)(a1 + 4) &= ~0x200u;
            v20 = 0;
            if ( TmInstance
              || (TmInstance = TxfUpdateTmInstanceSecurityDescriptor(v6, v18, v17, 0),
                  MarshallingArea = TmInstance,
                  v20 = 0,
                  TmInstance) )
            {
LABEL_220:
              if ( MarshallingArea == -1073741801 )
                goto LABEL_396;
              v75 = (unsigned int)(TmInstance + 1073741697);
              goto LABEL_186;
            }
            NtfsPurgeFileRecordCache(a1);
            *(_DWORD *)(a1 + 4) |= 0x200u;
            v89 = ZwRecoverTransactionManager(*v88);
            v90 = v89;
            *(_DWORD *)(a1 + 4) &= ~0x200u;
            v20 = 0;
            if ( v89 )
            {
              if ( v89 == -1073741801
                || (v91 = (unsigned int)(v89 + 1073741697), (unsigned int)v91 <= 0x22)
                && (v92 = 0x408000001LL, _bittest64(&v92, v91)) )
              {
                ++HIDWORD((*TxfData)[1]);
              }
              else if ( v90 == -1072037845
                     || v90 == -1073741202
                     || v90 == -1073741435
                     || v90 == -1073741496
                     || (v93 = (unsigned int)(v90 + 1073741667), (unsigned int)v93 <= 0x23)
                     && (v94 = 0x800000041LL, _bittest64(&v94, v93))
                     || (unsigned int)(v90 + 1073741811) <= 0x15 && (v95 = 2097219, _bittest(&v95, v90 + 1073741811))
                     || v90 == -2147483626
                     || v90 == -1072037841 )
              {
                ++LODWORD((*TxfData)[2]);
              }
              MarshallingArea = -1072103420;
              if ( !NtfsStatusDebugFlags )
                goto LABEL_493;
              v24 = 2649742;
LABEL_31:
              NtfsStatusTraceAndDebugInternal(0, (unsigned int)MarshallingArea, v24);
              v20 = 0;
              goto LABEL_493;
            }
            *(_QWORD *)&v142[3] = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x78u, 0x76667854u);
            pcbInfoBuffer = 120;
            NtfsPurgeFileRecordCache(a1);
            *(_DWORD *)(a1 + 4) |= 0x200u;
            MarshallingArea = ClfsGetLogFileInformation(
                                *(PLOG_FILE_OBJECT *)(v6 + 496),
                                *(PCLFS_INFORMATION *)&v142[3],
                                &pcbInfoBuffer);
            *(_DWORD *)(a1 + 4) &= ~0x200u;
            v20 = 0;
            if ( MarshallingArea < 0 )
            {
              if ( !NtfsStatusDebugFlags
                || (unsigned int)MarshallingArea >= 0xFFFFFFED
                || MarshallingArea == -1073741802
                || MarshallingArea == -1073741807
                || (unsigned int)(MarshallingArea + 2147483643) <= 1
                || MarshallingArea == -1073741608 )
              {
                goto LABEL_184;
              }
              v74 = 2649773;
              goto LABEL_183;
            }
            MarshallingArea = ZwQueryInformationTransactionManager(
                                *v88,
                                TransactionManagerLogInformation,
                                &TransactionManagerInformation,
                                0x10u,
                                0);
            v20 = 0;
            if ( MarshallingArea < 0 )
            {
              if ( !NtfsStatusDebugFlags
                || (unsigned int)MarshallingArea >= 0xFFFFFFED
                || MarshallingArea == -1073741802
                || MarshallingArea == -1073741807
                || (unsigned int)(MarshallingArea + 2147483643) <= 1
                || MarshallingArea == -1073741608 )
              {
                goto LABEL_184;
              }
              v74 = 2649790;
              goto LABEL_183;
            }
            if ( RtlCompareMemory(&TransactionManagerInformation, (const void *)(*(_QWORD *)&v142[3] + 104LL), 0x10u) == 16 )
              *(_DWORD *)(v6 + 128) |= 0x80000000;
            v96 = Source1;
            *(_OWORD *)Source1 = 0;
            if ( RtlCompareMemory(v96, (const void *)(v6 + 672), 0x10u) == 16 )
            {
              while ( 1 )
              {
                v97 = ExUuidCreate(Uuid);
                if ( v97 != -1073741267 )
                  break;
                Interval.QuadPart = -10000000;
                KeDelayExecutionThread(0, 0, &Interval);
              }
              if ( v97 && v97 != 1073872982 )
              {
                if ( NtfsStatusDebugFlags
                  && (((v97 - 294) & 0xFFFFFFFA) != 0 || v97 == 295)
                  && v97 < 0xFFFFFFED
                  && v97 != -1073741608
                  && v97 != -1073741802
                  && v97 != -1073741807
                  && v97 + 2147483643 > 1
                  && v97 != 259 )
                {
                  NtfsStatusTraceAndDebugInternal(a1, v97, 2649849);
                }
                NtfsRaiseStatusInternal(a1, v97, 0, 0, 2649849);
              }
              NtfsAcquireExclusiveScbEx(a1, *(_QWORD *)(v6 + 288), 0);
              v98 = Uuid;
              TxfUpdateTopsMetadataStream(a1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
              NtfsCheckpointCurrentTransaction(a1);
              *(UUID *)(v6 + 672) = *v98;
              NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v6 + 288) + 184LL), 0);
            }
            if ( ClfsLsnInvalid((const CLFS_LSN *)(v6 + 408)) )
            {
              rgWriteEntries = 0;
              plsnUndoNext.ullOffset = 0;
              plsn1.ullOffset = 0;
              memset(v173, 0, 0x54u);
              LOBYTE(v142[0]) = 0;
              *(_DWORD *)(v6 + 128) &= ~2u;
              NtfsPurgeFileRecordCache(a1);
              *(_DWORD *)(a1 + 4) |= 0x200u;
              restarted = ClfsReadRestartArea(
                            *(PVOID *)(v6 + 512),
                            &ppvRestartBuffer,
                            &pcbRestartBuffer,
                            &plsn,
                            (PVOID *)(v6 + 520));
              MarshallingArea = restarted;
              *(_DWORD *)(a1 + 4) &= ~0x200u;
              if ( restarted == -1073741801
                || (v101 = restarted + 1073741697, v102 = 0x408000001LL, v101 <= 0x22) && _bittest64(&v102, (int)v101) )
              {
                v20 = 0;
                if ( NtfsStatusDebugFlags
                  && MarshallingArea
                  && MarshallingArea != 294
                  && (unsigned int)(MarshallingArea - 298) > 1
                  && (unsigned int)MarshallingArea < 0xFFFFFFED
                  && MarshallingArea != -1073741608
                  && MarshallingArea != -1073741802
                  && MarshallingArea != -1073741807
                  && (unsigned int)(MarshallingArea + 2147483643) > 1
                  && MarshallingArea != 259 )
                {
                  NtfsStatusTraceAndDebugInternal(0, (unsigned int)MarshallingArea, 2649926);
                  v20 = 0;
                }
                goto LABEL_396;
              }
              if ( MarshallingArea == -1072037845
                || MarshallingArea == -1073741202
                || MarshallingArea == -1073741435
                || MarshallingArea == -1073741496
                || (v103 = 0x800000041LL, (unsigned int)(MarshallingArea + 1073741667) <= 0x23)
                && _bittest64(&v103, MarshallingArea + 1073741667)
                || (v104 = 2097219, (unsigned int)(MarshallingArea + 1073741811) <= 0x15)
                && _bittest(&v104, MarshallingArea + 1073741811)
                || MarshallingArea == -2147483626
                || MarshallingArea == -1072037841 )
              {
                v20 = 0;
                if ( NtfsStatusDebugFlags
                  && MarshallingArea
                  && MarshallingArea != 294
                  && (unsigned int)(MarshallingArea - 298) > 1
                  && (unsigned int)MarshallingArea < 0xFFFFFFED
                  && MarshallingArea != -1073741608
                  && MarshallingArea != -1073741802
                  && MarshallingArea != -1073741807
                  && (unsigned int)(MarshallingArea + 2147483643) > 1
                  && MarshallingArea != 259 )
                {
                  NtfsStatusTraceAndDebugInternal(0, (unsigned int)MarshallingArea, 2649932);
                  v20 = 0;
                }
LABEL_198:
                ++LODWORD((*TxfData)[2]);
                goto LABEL_493;
              }
              if ( MarshallingArea != 1075445772 )
              {
                v105 = v140;
                if ( (*(_DWORD *)(v140 + 16) & 0x100000LL) == 0
                  && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
                {
                  McTemplateU0spj_EtwWriteTransfer(
                    v100,
                    (unsigned int)txfcallbacks_c28498,
                    (unsigned int)"TxfStartRm",
                    v6,
                    v6 + 672);
                }
                v20 = 0;
                MarshallingArea = -1072103418;
                if ( NtfsStatusDebugFlags )
                {
                  NtfsStatusTraceAndDebugInternal(0, 3222863878LL, 2649947);
                  v20 = 0;
                }
                goto LABEL_494;
              }
              plsnUndoNext.ullOffset = CLFS_LSN_NULL_EXT;
              memset(v173, 0, 0x54u);
              LOWORD(v173[0]) = 1;
              DWORD1(v173[0]) = 24;
              LODWORD(v173[4]) = 84;
              rgWriteEntries.Buffer = v173;
              rgWriteEntries.ByteLength = 84;
              NtfsPurgeFileRecordCache(a1);
              *(_DWORD *)(a1 + 4) |= 0x200u;
              MarshallingArea = ClfsReserveAndAppendLog(
                                  *(PVOID *)(v6 + 512),
                                  &rgWriteEntries,
                                  1u,
                                  &plsnUndoNext,
                                  &plsnUndoNext,
                                  0,
                                  0,
                                  0,
                                  &plsn1);
              *(_DWORD *)(a1 + 4) &= ~0x200u;
              v20 = 0;
              if ( MarshallingArea < 0 )
              {
                if ( NtfsStatusDebugFlags
                  && (unsigned int)MarshallingArea < 0xFFFFFFED
                  && MarshallingArea != -1073741802
                  && MarshallingArea != -1073741807
                  && (unsigned int)(MarshallingArea + 2147483643) > 1
                  && MarshallingArea != -1073741608 )
                {
                  NtfsStatusTraceAndDebugInternal(0, (unsigned int)MarshallingArea, 2649985);
                  v20 = 0;
                }
                if ( MarshallingArea != -1073741801
                  && ((unsigned int)(MarshallingArea + 1073741697) > 0x22
                   || !_bittest64(&v102, MarshallingArea + 1073741697)) )
                {
                  if ( MarshallingArea == -1072037845
                    || MarshallingArea == -1073741202
                    || MarshallingArea == -1073741435
                    || MarshallingArea == -1073741496
                    || (unsigned int)(MarshallingArea + 1073741667) <= 0x23
                    && _bittest64(&v103, MarshallingArea + 1073741667) )
                  {
                    goto LABEL_349;
                  }
                  v106 = MarshallingArea + 1073741811;
                  if ( (unsigned int)(MarshallingArea + 1073741811) > 0x15 )
                    goto LABEL_347;
                  goto LABEL_346;
                }
                goto LABEL_351;
              }
              ExAcquireFastMutex(*(PFAST_MUTEX *)(v6 + 472));
              v107 = (volatile signed __int64 *)(v6 + 464);
              if ( ClfsLsnGreater(&plsn1, (const CLFS_LSN *)(v6 + 464)) )
              {
                do
                  v108 = _InterlockedCompareExchange64(v107, NtfsLarge0.QuadPart, NtfsLarge0.QuadPart);
                while ( v108 != _InterlockedCompareExchange64(v107, plsn1.ullOffset, v108) );
              }
              ExReleaseFastMutex(*(PFAST_MUTEX *)(v6 + 472));
              KeWaitForSingleObject(*(PVOID *)(v6 + 184), Executive, 0, 0, 0);
              LOBYTE(v142[0]) = 1;
              KtmResourceManagerObject = TxfTransMgrCheckpoint(a1, 0, 0, (__int64)v142, 1, 0, 0);
              MarshallingArea = KtmResourceManagerObject;
              v20 = 0;
              if ( KtmResourceManagerObject < 0 )
              {
LABEL_356:
                if ( MarshallingArea == -1073741801
                  || (v110 = KtmResourceManagerObject + 1073741697, v110 <= 0x22) && _bittest64(&v102, (int)v110) )
                {
                  if ( TxfBreakOnHardError )
                    ++HIDWORD((*TxfData)[1]);
                }
                else if ( (MarshallingArea == -1072037845
                        || MarshallingArea == -1073741202
                        || MarshallingArea == -1073741435
                        || MarshallingArea == -1073741496
                        || (unsigned int)(MarshallingArea + 1073741667) <= 0x23
                        && _bittest64(&v103, MarshallingArea + 1073741667)
                        || (unsigned int)(MarshallingArea + 1073741811) <= 0x15
                        && _bittest(&v104, MarshallingArea + 1073741811)
                        || MarshallingArea == -2147483626
                        || MarshallingArea == -1072037841)
                       && TxfBreakOnHardError )
                {
                  ++LODWORD((*TxfData)[2]);
                }
                goto LABEL_493;
              }
              TxfUpdateHighestFlushedLsn(v6, &plsn1, v17, 0);
              v20 = 0;
LABEL_464:
              if ( (*(_DWORD *)(v6 + 128) & 2) != 0 )
              {
                _InterlockedAnd((volatile signed __int32 *)(v6 + 136), 0xFFFFDFFF);
                _InterlockedAnd((volatile signed __int32 *)(v6 + 136), 0xFFEFFFFF);
              }
              else
              {
                KtmResourceManagerObject = TxfCreateKtmResourceManagerObject(a1, v6, v17, 0);
                MarshallingArea = KtmResourceManagerObject;
                v20 = 0;
                if ( KtmResourceManagerObject < 0 )
                  goto LABEL_356;
                KtmResourceManagerObject = TxfScanForHighestTxfFileId(a1);
                MarshallingArea = KtmResourceManagerObject;
                v20 = 0;
                if ( KtmResourceManagerObject < 0 )
                  goto LABEL_356;
                _InterlockedAnd((volatile signed __int32 *)(v6 + 136), 0xFFFFDFFF);
                _InterlockedAnd((volatile signed __int32 *)(v6 + 136), 0xFFEFFFFF);
                MarshallingArea = TxfMakeRmLive(a1);
                v20 = 0;
                if ( MarshallingArea < 0 )
                  goto LABEL_493;
              }
              *(_DWORD *)(v6 + 128) |= 0x20000u;
              if ( (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0
                && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
              {
                McTemplateU0spj_EtwWriteTransfer(
                  v111,
                  (unsigned int)txfcallbacks_c28878,
                  (unsigned int)"TxfStartRm",
                  v6,
                  v6 + 672);
                v20 = 0;
              }
              MarshallingArea = 0;
              goto LABEL_493;
            }
            pcbInfoBuffer = 120;
            NtfsPurgeFileRecordCache(a1);
            *(_DWORD *)(a1 + 4) |= 0x200u;
            MarshallingArea = ClfsReadRestartArea(
                                *(PVOID *)(v6 + 512),
                                &ppvRestartBuffer,
                                &pcbRestartBuffer,
                                &plsn,
                                (PVOID *)(v6 + 520));
            *(_DWORD *)(a1 + 4) &= ~0x200u;
            if ( MarshallingArea == 1075445772 )
            {
              if ( (*(_DWORD *)(v7 + 16) & 0x100000LL) == 0
                && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
              {
                McTemplateU0spj_EtwWriteTransfer(
                  v112,
                  (unsigned int)txfcallbacks_c28620,
                  (unsigned int)"TxfStartRm",
                  v6,
                  v6 + 672);
              }
              v20 = 0;
              MarshallingArea = -1072103418;
              if ( !NtfsStatusDebugFlags )
                goto LABEL_493;
              v63 = 2650069;
              goto LABEL_139;
            }
            v20 = 0;
            if ( MarshallingArea < 0 )
            {
              if ( NtfsStatusDebugFlags
                && (unsigned int)MarshallingArea < 0xFFFFFFED
                && MarshallingArea != -1073741802
                && MarshallingArea != -1073741807
                && (unsigned int)(MarshallingArea + 2147483643) > 1
                && MarshallingArea != -1073741608 )
              {
                v116 = 2650111;
                goto LABEL_429;
              }
            }
            else
            {
              if ( *((_DWORD *)ppvRestartBuffer + 26) != 44 )
              {
                MarshallingArea = -1072037879;
                if ( !NtfsStatusDebugFlags )
                  goto LABEL_493;
                v24 = 2650084;
                goto LABEL_31;
              }
              if ( RtlCompareMemory((char *)ppvRestartBuffer + 88, (const void *)(v6 + 672), 0x10u) != 16 )
              {
                if ( (*(_DWORD *)(v7 + 16) & 0x100000LL) == 0
                  && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
                {
                  McTemplateU0spjj_EtwWriteTransfer(
                    v113,
                    (unsigned int)txfcallbacks_c28655,
                    (unsigned int)"TxfStartRm",
                    v6,
                    v6 + 672,
                    (__int64)ppvRestartBuffer + 88);
                }
                v20 = 0;
                MarshallingArea = -1072103418;
                if ( !NtfsStatusDebugFlags )
                  goto LABEL_493;
                v63 = 2650105;
                goto LABEL_139;
              }
              v114 = *(CLFS_INFORMATION **)&v142[3];
              if ( !*(_QWORD *)&v142[3] )
              {
                v114 = (CLFS_INFORMATION *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x78u, 0x77667854u);
                *(_QWORD *)&v142[3] = v114;
              }
              memset(v114, 0, sizeof(CLFS_INFORMATION));
              NtfsPurgeFileRecordCache(a1);
              *(_DWORD *)(a1 + 4) |= 0x200u;
              MarshallingArea = ClfsGetLogFileInformation(*(PLOG_FILE_OBJECT *)(v6 + 496), v114, &pcbInfoBuffer);
              *(_DWORD *)(a1 + 4) &= ~0x200u;
              v20 = 0;
              if ( !MarshallingArea )
              {
                v121 = *(const CLFS_LSN **)&v142[3];
                v122 = (const CLFS_LSN *)(*(_QWORD *)&v142[3] + 72LL);
                if ( ClfsLsnGreater((const CLFS_LSN *)(*(_QWORD *)&v142[3] + 72LL), (const CLFS_LSN *)(v6 + 408))
                  && (v123 = ClfsLsnGreater(v121 + 8, (const CLFS_LSN *)(v6 + 408)), v20 = 0, v123) )
                {
                  if ( (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0
                    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
                  {
                    McTemplateU0spj_EtwWriteTransfer(
                      v124,
                      (unsigned int)txfcallbacks_c28721,
                      (unsigned int)"TxfStartRm",
                      v6,
                      v6 + 672);
                    v20 = 0;
                  }
                  MarshallingArea = -1072103418;
                  if ( !NtfsStatusDebugFlags )
                    goto LABEL_493;
                  v63 = 2650170;
                }
                else
                {
                  if ( ClfsLsnInvalid((const CLFS_LSN *)(v6 + 432))
                    || (v125 = ClfsLsnLess((const CLFS_LSN *)(*(_QWORD *)&v142[3] + 88LL), (const CLFS_LSN *)(v6 + 432)),
                        v20 = 0,
                        !v125) )
                  {
                    *(CLFS_LSN *)(v6 + 416) = *v122;
                    if ( ClfsLsnGreater(v122, (const CLFS_LSN *)(v6 + 408)) )
                      _InterlockedOr((volatile signed __int32 *)(v6 + 136), 0x20000u);
                    v127 = *(void **)&v142[3];
                    *(_QWORD *)(v6 + 424) = *(_QWORD *)(*(_QWORD *)&v142[3] + 64LL);
                    *(_QWORD *)(v6 + 448) = CLFS_LSN_NULL_EXT;
                    v128 = ClfsLsnInvalid((const CLFS_LSN *)(v6 + 432));
                    v129 = *(struct _FAST_MUTEX **)(v6 + 472);
                    v130 = (volatile signed __int64 *)(v6 + 464);
                    if ( v128 )
                    {
                      ExAcquireFastMutex(v129);
                      if ( ClfsLsnGreater((const CLFS_LSN *)(v6 + 408), (const CLFS_LSN *)(v6 + 464)) )
                      {
                        do
                          v132 = _InterlockedCompareExchange64(v130, NtfsLarge0.QuadPart, NtfsLarge0.QuadPart);
                        while ( v132 != _InterlockedCompareExchange64(v130, *(_QWORD *)(v6 + 408), v132) );
                      }
                    }
                    else
                    {
                      ExAcquireFastMutex(v129);
                      if ( ClfsLsnGreater((const CLFS_LSN *)(v6 + 432), (const CLFS_LSN *)(v6 + 464)) )
                      {
                        do
                          v131 = _InterlockedCompareExchange64(v130, NtfsLarge0.QuadPart, NtfsLarge0.QuadPart);
                        while ( v131 != _InterlockedCompareExchange64(v130, *(_QWORD *)(v6 + 432), v131) );
                      }
                    }
                    ExReleaseFastMutex(*(PFAST_MUTEX *)(v6 + 472));
                    ExFreePoolWithTag(v127, 0);
                    v20 = 0;
                    *(_QWORD *)&v142[3] = 0;
                    v104 = 2097219;
                    v102 = 0x408000001LL;
                    v103 = 0x800000041LL;
                    goto LABEL_464;
                  }
                  if ( (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0
                    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
                  {
                    McTemplateU0spj_EtwWriteTransfer(
                      v126,
                      (unsigned int)txfcallbacks_c28743,
                      (unsigned int)"TxfStartRm",
                      v6,
                      v6 + 672);
                    v20 = 0;
                  }
                  MarshallingArea = -1072103418;
                  if ( !NtfsStatusDebugFlags )
                    goto LABEL_493;
                  v63 = 2650192;
                }
LABEL_139:
                NtfsStatusTraceAndDebugInternal(0, 3222863878LL, v63);
                v20 = 0;
                goto LABEL_493;
              }
              if ( (*(_DWORD *)(v7 + 16) & 0x100000LL) == 0
                && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
              {
                McTemplateU0sdpj_EtwWriteTransfer(v115, v18, v17, MarshallingArea, v6, v6 + 672);
                v20 = 0;
              }
              if ( NtfsStatusDebugFlags
                && (((MarshallingArea - 294) & 0xFFFFFFFA) != 0 || MarshallingArea == 295)
                && (unsigned int)MarshallingArea < 0xFFFFFFED
                && MarshallingArea != -1073741608
                && MarshallingArea != -1073741802
                && MarshallingArea != -1073741807
                && (unsigned int)(MarshallingArea + 2147483643) > 1
                && MarshallingArea != 259 )
              {
                v116 = 2650145;
LABEL_429:
                NtfsStatusTraceAndDebugInternal(0, (unsigned int)MarshallingArea, v116);
                v20 = 0;
              }
            }
            if ( MarshallingArea != -1073741801 )
            {
              v117 = (unsigned int)(MarshallingArea + 1073741697);
              if ( (unsigned int)v117 > 0x22 || (v118 = 0x408000001LL, !_bittest64(&v118, v117)) )
              {
                switch ( MarshallingArea )
                {
                  case -1072037845:
                    goto LABEL_349;
                  case -1073741202:
                    goto LABEL_349;
                  case -1073741435:
                    goto LABEL_349;
                  case -1073741496:
                    goto LABEL_349;
                }
                v119 = (unsigned int)(MarshallingArea + 1073741667);
                if ( (unsigned int)v119 <= 0x23 )
                {
                  v120 = 0x800000041LL;
                  if ( _bittest64(&v120, v119) )
                    goto LABEL_349;
                }
                v106 = MarshallingArea + 1073741811;
                if ( (unsigned int)(MarshallingArea + 1073741811) > 0x15 )
                {
LABEL_347:
                  if ( MarshallingArea != -2147483626 && MarshallingArea != -1072037841 )
                    goto LABEL_493;
LABEL_349:
                  v105 = v140;
                  if ( TxfBreakOnHardError )
                    ++LODWORD((*TxfData)[2]);
                  goto LABEL_494;
                }
                v104 = 2097219;
LABEL_346:
                if ( _bittest(&v104, v106) )
                  goto LABEL_349;
                goto LABEL_347;
              }
            }
LABEL_351:
            v105 = v140;
            if ( TxfBreakOnHardError )
              ++HIDWORD((*TxfData)[1]);
            goto LABEL_494;
          }
        }
        *(_DWORD *)(v6 + 128) = v18 | 0x40000;
        goto LABEL_162;
      }
    }
    else if ( !v65 )
    {
      goto LABEL_480;
    }
    if ( !v66 )
    {
      *(_DWORD *)(v6 + 128) |= 0x10u;
      goto LABEL_148;
    }
LABEL_480:
    MarshallingArea = -1073741811;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_493;
    v24 = 2649332;
    goto LABEL_31;
  }
  MarshallingArea = TxfShutdownRm(a1, 1, 0);
  v20 = 0;
  if ( MarshallingArea >= 0 )
  {
    v4 = plsnUndoNext;
    goto LABEL_15;
  }
LABEL_493:
  v105 = v140;
LABEL_494:
  v133 = v154;
  if ( *v154 != (_BYTE)v20 )
  {
    NtfsReleaseVcb(a1, v105);
    v20 = 0;
    *v133 = 0;
  }
  v134 = puszLogFileName;
  Buffer = puszLogFileName->Buffer;
  if ( Buffer )
  {
    ExFreePoolWithTag(Buffer, 0);
    v20 = 0;
    v134->Buffer = 0;
  }
  if ( *(_QWORD *)&v142[3] )
  {
    ExFreePoolWithTag(*(PVOID *)&v142[3], 0);
    v20 = 0;
  }
  if ( RegistrationData )
  {
    ExFreePoolWithTag(RegistrationData, 0);
    v20 = 0;
  }
  if ( Policy )
  {
    ExFreePoolWithTag(Policy, 0);
    v20 = 0;
  }
  if ( Source )
  {
    ExFreePoolWithTag((PVOID)Source, 0);
    v20 = 0;
  }
  if ( Uuid )
  {
    ExFreePoolWithTag(Uuid, 0);
    v20 = 0;
  }
  if ( Source1 )
  {
    ExFreePoolWithTag(Source1, 0);
    v20 = 0;
  }
  if ( MarshallingArea < 0 && v141 != (_BYTE)v20 )
  {
    if ( MarshallingArea != -1073741608
      && MarshallingArea != -1073741432
      && (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
    {
      McTemplateU0spjds_EtwWriteTransfer(
        (unsigned int)byte_140064C38,
        v18,
        v17,
        v6,
        v6 + 672,
        MarshallingArea,
        (__int64)byte_140064C38);
    }
    _InterlockedOr((volatile signed __int32 *)(v6 + 136), 0x8000u);
    v136 = TxfMarkRmForShutdown(v6);
    v20 = 0;
    if ( v136 )
    {
      _InterlockedOr((volatile signed __int32 *)(v6 + 136), 4u);
      TxfQueueDelayedRmWorkItem(v6, v137, v138, 0);
      v20 = 0;
    }
  }
  if ( *(_QWORD *)(v6 + 520) != v20 )
  {
    NtfsPurgeFileRecordCache(a1);
    *(_DWORD *)(a1 + 4) |= 0x200u;
    ClfsTerminateReadLog(*(PVOID *)(v6 + 520));
    *(_QWORD *)(v6 + 520) = 0;
    *(_DWORD *)(a1 + 4) &= ~0x200u;
  }
  return (unsigned int)MarshallingArea;
}

```

## disassembly

```asm
0x14025a2c8  mov     r11, rsp
0x14025a2cb  push    rbx
0x14025a2cc  push    rsi
0x14025a2cd  push    rdi
0x14025a2ce  push    r12
0x14025a2d0  push    r13
0x14025a2d2  push    r14
0x14025a2d4  push    r15
0x14025a2d6  sub     rsp, 220h
0x14025a2dd  mov     rax, cs:__security_cookie
0x14025a2e4  xor     rax, rsp
0x14025a2e7  mov     [rsp+258h+var_48], rax
0x14025a2ef  mov     qword ptr [rsp+258h+plsn1], r8
0x14025a2f7  mov     rbx, rdx
0x14025a2fa  mov     qword ptr [rsp+258h+plsnUndoNext], rdx
0x14025a302  mov     r14, rcx
0x14025a305  mov     [rsp+258h+var_138], rcx
0x14025a30d  mov     [rsp+258h+var_100], rdx
0x14025a315  mov     rsi, [rdx+140h]
0x14025a31c  mov     [rsp+258h+var_110], rsi
0x14025a324  mov     r13, [rsi+10h]
0x14025a328  mov     [rsp+258h+var_1C0], r13
0x14025a330  mov     [rsp+258h+var_F8], r13
0x14025a338  xor     r15d, r15d
0x14025a33b  mov     [r11-1C8h], r15d
0x14025a342  mov     [r11-148h], r15
0x14025a349  mov     [r11-170h], r15d
0x14025a350  mov     [r11-118h], r15
0x14025a357  mov     [r11-1B7h], r15b
0x14025a35e  mov     [r11-1B5h], r15b
0x14025a365  mov     [r11-1B8h], r15b
0x14025a36c  mov     [r11-1B0h], r15
0x14025a373  mov     [r11-158h], r15
0x14025a37a  mov     eax, [r8]
0x14025a37d  lea     ecx, [r15+2]
0x14025a381  test    cl, al
0x14025a383  jz      short loc_14025A38B
0x14025a385  mov     eax, [r8+10h]
0x14025a389  jmp     short loc_14025A38D
0x14025a38b  mov     eax, ecx
0x14025a38d  mov     [rsp+258h+NewSizeInContainers], rax
0x14025a395  mov     [rsp+258h+ResultingSizeInContainers], r15
0x14025a39d  mov     [rsp+258h+Source1], r15
0x14025a3a5  mov     [rsp+258h+Uuid], r15
0x14025a3ad  mov     [rsp+258h+Policy], r15
0x14025a3b5  mov     [rsp+258h+Source], r15
0x14025a3bd  mov     [rsp+258h+puszLogFileName], r15
0x14025a3c5  xorps   xmm0, xmm0
0x14025a3c8  movups  [rsp+258h+TransactionManagerInformation], xmm0
0x14025a3d0  mov     [rsp+258h+pcbInfoBuffer], r15d
0x14025a3d8  mov     edi, r15d
0x14025a3db  lea     r12, [rsp+258h+var_1B6+1]
0x14025a3e3  test    r9, r9
0x14025a3e6  cmovnz  r12, r9
0x14025a3ea  mov     [rsp+258h+var_168], r12
0x14025a3f2  cmp     [r12], r15b
0x14025a3f6  jz      short loc_14025A407
0x14025a3f8  mov     rdx, r13
0x14025a3fb  mov     rcx, r14
0x14025a3fe  call    NtfsReleaseVcb
0x14025a403  mov     [r12], r15b
0x14025a407  test    dword ptr [r13+4], 2000000h
0x14025a40f  jz      short loc_14025A438
0x14025a411  mov     al, cs:NtfsStatusDebugFlags
0x14025a417  test    al, al
0x14025a419  jz      short loc_14025A42D
0x14025a41b  mov     edx, 0C00000A2h
0x14025a420  xor     ecx, ecx
0x14025a422  mov     r8d, 286AE5h
0x14025a428  call    NtfsStatusTraceAndDebugInternal
0x14025a42d  mov     eax, 0C00000A2h
0x14025a432  jmp     loc_14025CC70
0x14025a438  mov     ecx, cs:PoolType
0x14025a43e  mov     r15d, 10h
0x14025a444  or      ecx, r15d; PoolType
0x14025a447  lea     edx, [r15+28h]; NumberOfBytes
0x14025a44b  mov     r8d, 75667854h; Tag
0x14025a451  call    cs:__imp_ExAllocatePoolWithTag
0x14025a458  nop     dword ptr [rax+rax+00h]
0x14025a45d  mov     [rsp+258h+RegistrationData], rax
0x14025a465  xorps   xmm0, xmm0
0x14025a468  xor     ecx, ecx
0x14025a46a  movups  xmmword ptr [rax], xmm0
0x14025a46d  movups  xmmword ptr [rax+10h], xmm0
0x14025a471  movups  xmmword ptr [rax+20h], xmm0
0x14025a475  mov     [rax+30h], rcx
0x14025a479  mov     ecx, cs:PoolType
0x14025a47f  or      ecx, r15d; PoolType
0x14025a482  mov     r8d, 30667854h; Tag
0x14025a488  mov     edx, r15d; NumberOfBytes
0x14025a48b  call    cs:__imp_ExAllocatePoolWithTag
0x14025a492  nop     dword ptr [rax+rax+00h]
0x14025a497  mov     [rsp+258h+Source1], rax
0x14025a49f  mov     ecx, cs:PoolType
0x14025a4a5  or      ecx, r15d; PoolType
0x14025a4a8  mov     r8d, 30667854h; Tag
0x14025a4ae  mov     edx, r15d; NumberOfBytes
0x14025a4b1  call    cs:__imp_ExAllocatePoolWithTag
0x14025a4b8  nop     dword ptr [rax+rax+00h]
0x14025a4bd  mov     [rsp+258h+Uuid], rax
0x14025a4c5  mov     ecx, cs:PoolType
0x14025a4cb  or      ecx, r15d; PoolType
0x14025a4ce  lea     edx, [r15+40h]; NumberOfBytes
0x14025a4d2  mov     r8d, 30667854h; Tag
0x14025a4d8  call    cs:__imp_ExAllocatePoolWithTag
0x14025a4df  nop     dword ptr [rax+rax+00h]
0x14025a4e4  mov     r15, rax
0x14025a4e7  mov     [rsp+258h+Source], rax
0x14025a4ef  xor     edx, edx; Val
0x14025a4f1  lea     r8d, [rdx+50h]; Size
0x14025a4f5  mov     rcx, rax; void *
0x14025a4f8  call    memset
0x14025a4fd  lea     rax, [r15+10h]
0x14025a501  mov     [rsp+258h+puszLogFileName], rax
0x14025a509  lea     rcx, [r15+30h]; DestinationString
0x14025a50d  lea     rdx, aBlfTxflogconta; "%BLF%\\$TxfLogContainer"
0x14025a514  call    cs:__imp_RtlInitUnicodeString
0x14025a51b  nop     dword ptr [rax+rax+00h]
0x14025a520  lea     rdx, Source; "\\??\\log:"
0x14025a527  lea     rcx, [r15+40h]; DestinationString
0x14025a52b  call    cs:__imp_RtlInitUnicodeString
0x14025a532  nop     dword ptr [rax+rax+00h]
0x14025a537  mov     eax, 212h
0x14025a53c  add     ax, [r15+40h]
0x14025a541  movzx   edx, ax; NumberOfBytes
0x14025a544  mov     r15, [rsp+258h+puszLogFileName]
0x14025a54c  mov     [r15+2], dx
0x14025a551  mov     ecx, cs:PoolType
0x14025a557  or      ecx, 10h; PoolType
0x14025a55a  mov     r8d, 30667854h; Tag
0x14025a560  call    cs:__imp_ExAllocatePoolWithTag
0x14025a567  nop     dword ptr [rax+rax+00h]
0x14025a56c  mov     [r15+8], rax
0x14025a570  movzx   r8d, word ptr [r15+2]; Size
0x14025a575  xor     edx, edx; Val
0x14025a577  mov     rcx, rax; void *
0x14025a57a  call    memset
0x14025a57f  mov     ecx, 4
0x14025a584  mov     eax, ecx
0x14025a586  lock cmpxchg [rsi+84h], ecx
0x14025a58e  lea     r15d, [rcx-3]
0x14025a592  cmp     eax, 3
0x14025a595  jnz     short loc_14025A5D2
0x14025a597  mov     qword ptr [rsp+258h+fCreateDisposition], 0
0x14025a5a0  mov     byte ptr [rsp+258h+psdLogFile], r15b
0x14025a5a5  xor     r9d, r9d
0x14025a5a8  mov     r8b, r15b
0x14025a5ab  mov     rdx, rsi
0x14025a5ae  mov     rcx, r14
0x14025a5b1  call    TxfShutdownRm
0x14025a5b6  mov     ebx, eax
0x14025a5b8  mov     [rsp+258h+var_1C8], eax
0x14025a5bf  xor     r9d, r9d
0x14025a5c2  test    eax, eax
0x14025a5c4  js      loc_14025CA90
0x14025a5ca  mov     rbx, qword ptr [rsp+258h+plsnUndoNext]
0x14025a5d2  mov     r8b, r15b
0x14025a5d5  mov     rdx, r13
0x14025a5d8  mov     rcx, r14
0x14025a5db  call    NtfsAcquireSharedVcb
0x14025a5e0  mov     [r12], r15b
0x14025a5e4  mov     eax, [r13+4]
0x14025a5e8  and     eax, 8000823h
0x14025a5ed  cmp     eax, r15d
0x14025a5f0  jz      short loc_14025A625
0x14025a5f2  mov     al, cs:NtfsStatusDebugFlags
0x14025a5f8  xor     r9d, r9d
0x14025a5fb  test    al, al
0x14025a5fd  jz      short loc_14025A614
0x14025a5ff  mov     edx, 0C000026Eh
0x14025a604  xor     ecx, ecx
0x14025a606  mov     r8d, 286B2Eh
0x14025a60c  call    NtfsStatusTraceAndDebugInternal
0x14025a611  xor     r9d, r9d
0x14025a614  mov     ebx, 0C000026Eh
0x14025a619  mov     [rsp+258h+var_1C8], ebx
0x14025a620  jmp     loc_14025CA90
0x14025a625  lea     r12, [r13+1870h]
0x14025a62c  mov     rcx, r12; FastMutex
0x14025a62f  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14025a636  nop     dword ptr [rax+rax+00h]
0x14025a63b  mov     r9d, [r13+1924h]
0x14025a642  test    r15b, r9b
0x14025a645  jz      loc_14025A72C
0x14025a64b  xor     ecx, ecx
0x14025a64d  test    r14, r14
0x14025a650  jz      short loc_14025A661
0x14025a652  mov     eax, [r14+10h]
0x14025a656  bt      rax, 14h
0x14025a65b  jb      loc_14025A6F0
0x14025a661  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x14025a668  test    al, 20h
0x14025a66a  jz      loc_14025A6F0
0x14025a670  mov     rdx, [r13+0F8h]
0x14025a677  movzx   eax, word ptr [rdx+6]
0x14025a67b  cmp     eax, 40h ; '@'
0x14025a67e  ja      short loc_14025A68E
0x14025a680  test    r15b, al
0x14025a683  jnz     short loc_14025A68E
0x14025a685  mov     [rsp+258h+var_140], eax
0x14025a68c  jmp     short loc_14025A697
0x14025a68e  mov     eax, ecx
0x14025a690  mov     [rsp+258h+var_140], ecx
0x14025a697  mov     [rsp+258h+var_E0], ax
0x14025a69f  add     rdx, 20h ; ' '
0x14025a6a3  mov     [rsp+258h+var_D8], rdx
0x14025a6ab  mov     r8, gs:188h
0x14025a6b4  movzx   eax, ax
0x14025a6b7  shr     eax, 1
0x14025a6b9  movzx   ecx, word ptr [r13+1EC0h]
0x14025a6c1  shr     ecx, 1
0x14025a6c3  mov     [rsp+258h+fLogOptionFlag], r9d
0x14025a6c8  mov     qword ptr [rsp+258h+fFlagsAndAttributes], rdx
0x14025a6cd  mov     [rsp+258h+fCreateOptions], eax
0x14025a6d1  mov     rax, [r13+1EC8h]
0x14025a6d8  mov     qword ptr [rsp+258h+fCreateDisposition], rax
0x14025a6dd  mov     dword ptr [rsp+258h+psdLogFile], ecx
0x14025a6e1  mov     r9, r13
0x14025a6e4  lea     rdx, txfcallbacks_c27445
0x14025a6eb  call    McTemplateU0ppwwd_EtwWriteTransfer
0x14025a6f0  mov     rcx, r12; FastMutex
0x14025a6f3  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14025a6fa  nop     dword ptr [rax+rax+00h]
0x14025a6ff  mov     al, cs:NtfsStatusDebugFlags
0x14025a705  xor     r9d, r9d
0x14025a708  mov     ebx, 0C0000022h
0x14025a70d  test    al, al
0x14025a70f  jz      loc_14025A619
0x14025a715  mov     r8d, 286B41h
0x14025a71b  mov     edx, ebx
0x14025a71d  xor     ecx, ecx
0x14025a71f  call    NtfsStatusTraceAndDebugInternal
0x14025a724  xor     r9d, r9d
0x14025a727  jmp     loc_14025A619
0x14025a72c  mov     rcx, r12; FastMutex
0x14025a72f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14025a736  nop     dword ptr [rax+rax+00h]
0x14025a73b  xor     eax, eax
0x14025a73d  lock cmpxchg [rsi+84h], r15d
0x14025a746  mov     [rsp+258h+var_16C], eax
0x14025a74d  jz      short loc_14025A76D
0x14025a74f  mov     al, cs:NtfsStatusDebugFlags
0x14025a755  xor     r9d, r9d
0x14025a758  mov     ebx, 40190035h
0x14025a75d  test    al, al
0x14025a75f  jz      loc_14025A619
0x14025a765  mov     r8d, 286B55h
0x14025a76b  jmp     short loc_14025A71B
0x14025a76d  mov     ecx, [rsi+80h]
0x14025a773  mov     r8, qword ptr [rsp+258h+plsn1]
0x14025a77b  test    dword ptr [r8], 200h
0x14025a782  jz      short loc_14025A78A
0x14025a784  bts     ecx, 0Dh
0x14025a788  jmp     short loc_14025A78E
0x14025a78a  btr     ecx, 0Dh
0x14025a78e  mov     [rsi+80h], ecx
0x14025a794  lock and dword ptr [rsi+88h], 0FBFFFFFFh
0x14025a79f  mov     rcx, r12; FastMutex
0x14025a7a2  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14025a7a9  nop     dword ptr [rax+rax+00h]
0x14025a7ae  add     [r13+1920h], r15d
0x14025a7b5  lea     rcx, [r13+1928h]; Event
0x14025a7bc  call    cs:__imp_KeResetEvent
0x14025a7c3  nop     dword ptr [rax+rax+00h]
0x14025a7c8  mov     rcx, r12; FastMutex
0x14025a7cb  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14025a7d2  nop     dword ptr [rax+rax+00h]
0x14025a7d7  mov     [rsp+258h+var_1B7], r15b
0x14025a7df  xor     r9d, r9d
0x14025a7e2  xor     r8d, r8d
0x14025a7e5  mov     rdx, rbx
0x14025a7e8  mov     rcx, r14
0x14025a7eb  call    NtfsAcquireSharedFcb
0x14025a7f0  mov     [rsp+258h+var_1B8], r15b
0x14025a7f8  xorps   xmm0, xmm0
0x14025a7fb  xor     eax, eax
0x14025a7fd  movups  [rsp+258h+var_A8], xmm0
0x14025a805  movups  [rsp+258h+var_98], xmm0
0x14025a80d  movups  [rsp+258h+var_88], xmm0
0x14025a815  mov     [rsp+258h+var_78], rax
0x14025a81d  lea     r8, [rsp+258h+var_A8]
0x14025a825  mov     rdx, rbx
0x14025a828  mov     rcx, r14
0x14025a82b  call    TxfReadTxfDataAttribute
0x14025a830  xor     r12d, r12d
0x14025a833  test    al, al
0x14025a835  jz      short loc_14025A845
0x14025a837  mov     rdi, [rsp+258h+var_78]
0x14025a83f  and     edi, 0FFF00000h
0x14025a845  xor     r8d, r8d
0x14025a848  mov     rdx, rbx
0x14025a84b  mov     rcx, r14
0x14025a84e  call    NtfsReleaseFcbEx
0x14025a853  mov     [rsp+258h+var_1B8], r12b
0x14025a85b  mov     rdx, r13
0x14025a85e  mov     rcx, r14
0x14025a861  call    NtfsReleaseVcb
0x14025a866  mov     rax, [rsp+258h+var_168]
0x14025a86e  xor     r9d, r9d
0x14025a871  mov     [rax], r9b
  ... truncated ...
```
