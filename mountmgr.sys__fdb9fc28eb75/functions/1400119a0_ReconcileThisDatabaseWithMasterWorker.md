# ReconcileThisDatabaseWithMasterWorker

- ea: `0x1400119a0`
- end: `0x140012de2`
- name: `ReconcileThisDatabaseWithMasterWorker`
- size: `5186`
- prototype: `int __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140013a20`

## callees

- `0x140001730`
- `0x140001ae0`
- `0x140001b30`
- `0x140002d70`
- `0x140002f80`
- `0x14000a550`
- `0x14000a810`
- `0x14000b5e8`
- `0x14000bc48`
- `0x14001045c`
- `0x140010600`
- `0x140010680`
- `0x140010800`
- `0x140010970`
- `0x140010d00`
- `0x140010e70`
- `0x140011500`
- `0x1400119a0`
- `0x140012df0`
- `0x140012e60`
- `0x1400135a0`
- `0x1400139f0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14001279b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001279b`
- `ntoskrnl!ObfDereferenceObject` at `0x140011afb`
- `ntoskrnl!ObfDereferenceObject` at `0x140011afb`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140011acc`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140011acc`
- `ntoskrnl!KeReleaseMutex` at `0x140011bbe`
- `ntoskrnl!KeReleaseMutex` at `0x140011c95`
- `ntoskrnl!KeReleaseMutex` at `0x140011d65`
- `ntoskrnl!KeReleaseMutex` at `0x140011ece`
- `ntoskrnl!KeReleaseMutex` at `0x140012085`
- `ntoskrnl!KeReleaseMutex` at `0x140012227`
- `ntoskrnl!KeReleaseMutex` at `0x14001232b`
- `ntoskrnl!KeReleaseMutex` at `0x140011bbe`
- `ntoskrnl!KeReleaseMutex` at `0x140011c95`
- `ntoskrnl!KeReleaseMutex` at `0x140011d65`
- `ntoskrnl!KeReleaseMutex` at `0x140011ece`
- `ntoskrnl!KeReleaseMutex` at `0x140012085`
- `ntoskrnl!KeReleaseMutex` at `0x140012227`
- `ntoskrnl!KeReleaseMutex` at `0x14001232b`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x140011db1`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x140011f24`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x140011db1`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x140011f24`
- `ntoskrnl!ExAllocatePool2` at `0x140011ba4`
- `ntoskrnl!ExAllocatePool2` at `0x140012515`
- `ntoskrnl!ExAllocatePool2` at `0x140012885`
- `ntoskrnl!ExAllocatePool2` at `0x1400129c7`
- `ntoskrnl!ExAllocatePool2` at `0x140011ba4`
- `ntoskrnl!ExAllocatePool2` at `0x140012515`
- `ntoskrnl!ExAllocatePool2` at `0x140012885`
- `ntoskrnl!ExAllocatePool2` at `0x1400129c7`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140011ca3`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140011ce4`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140011ca3`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140011ce4`
- `ntoskrnl!KeReleaseSemaphore` at `0x140011be7`
- `ntoskrnl!KeReleaseSemaphore` at `0x140011be7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011cf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012108`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012121`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400121e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400124bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400124d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012592`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012614`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400127b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001285b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400129eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012aad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012acc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011cf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012108`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012121`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400121e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400124bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400124d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012592`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012614`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400127b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001285b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400129eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012aad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012acc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d99`
- `ntoskrnl!ZwOpenFile` at `0x140011cd3`
- `ntoskrnl!ZwOpenFile` at `0x140011cd3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011a83`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011d18`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011dcf`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011f47`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011a83`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011d18`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011dcf`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011f47`
- `ntoskrnl!ZwClose` at `0x140012095`
- `ntoskrnl!ZwClose` at `0x1400120ac`
- `ntoskrnl!ZwClose` at `0x140012095`
- `ntoskrnl!ZwClose` at `0x1400120ac`
- `ntoskrnl!RtlCompareMemory` at `0x14001247d`
- `ntoskrnl!RtlCompareMemory` at `0x14001247d`

## pseudocode

```c
int __fastcall ReconcileThisDatabaseWithMasterWorker(__int64 *a1)
{
  int result; // eax
  unsigned int *v2; // r12
  bool v3; // di
  __int64 v4; // rsi
  __int64 v5; // r15
  __int64 v6; // r8
  struct _KMUTANT *v7; // r14
  __int64 Device; // rax
  __int64 v9; // r8
  NTSTATUS DeviceObjectPointer; // eax
  __int64 v11; // r8
  int RemoteDatabaseEntry; // ebx
  _QWORD *v13; // rax
  _QWORD *v14; // rbx
  _QWORD *v15; // r14
  PVPB v16; // rax
  void *Pool2; // rax
  __int64 v18; // r12
  _QWORD *v19; // r13
  BOOLEAN v20; // bl
  NTSTATUS v21; // edi
  NTSTATUS v22; // edi
  HANDLE v23; // rdx
  unsigned int v24; // edi
  _DWORD *v25; // r12
  PVPB Vpb; // rax
  BOOLEAN v27; // r14
  __int64 v28; // rdi
  int v29; // r12d
  struct _UNICODE_STRING *p_FileName; // rcx
  int v31; // eax
  __int64 v32; // r9
  int VolumeName; // eax
  __int64 v34; // r8
  __int64 v35; // r14
  unsigned int v36; // edi
  _DWORD *v37; // r12
  __int64 v38; // rcx
  _QWORD *v39; // rax
  unsigned int v40; // edi
  _DWORD *v41; // r12
  int v42; // eax
  PVOID v43; // rdi
  PDEVICE_OBJECT v44; // rcx
  __int64 v45; // rdx
  int v46; // eax
  SIZE_T v47; // rbx
  __int64 v48; // r8
  __int64 v49; // rax
  _QWORD *v50; // rbx
  __int64 *v51; // rdx
  unsigned int v52; // ebx
  __int64 v53; // rax
  unsigned int v54; // ebx
  unsigned int *v55; // rax
  PDEVICE_OBJECT v56; // rcx
  __int64 v57; // rdx
  PDEVICE_OBJECT v58; // rcx
  __int64 v59; // rdx
  PVOID v60; // [rsp+68h] [rbp-A0h]
  char v61; // [rsp+70h] [rbp-98h] BYREF
  char v62; // [rsp+71h] [rbp-97h]
  HANDLE Handle; // [rsp+78h] [rbp-90h] BYREF
  char *v64; // [rsp+80h] [rbp-88h] BYREF
  PVOID v65; // [rsp+88h] [rbp-80h] BYREF
  void *FileHandle; // [rsp+90h] [rbp-78h] BYREF
  UNICODE_STRING String2; // [rsp+98h] [rbp-70h] BYREF
  __int64 v68; // [rsp+A8h] [rbp-60h]
  PVOID P[2]; // [rsp+B0h] [rbp-58h] BYREF
  PVOID v70[2]; // [rsp+C0h] [rbp-48h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD *v72; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD *v73; // [rsp+E0h] [rbp-28h]
  PFILE_OBJECT FileObject; // [rsp+E8h] [rbp-20h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+F0h] [rbp-18h] BYREF
  UNICODE_STRING String1; // [rsp+100h] [rbp-8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+110h] [rbp+8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+120h] [rbp+18h] BYREF
  __int128 FileInformation; // [rsp+150h] [rbp+48h] BYREF
  _QWORD v80[3]; // [rsp+160h] [rbp+58h] BYREF
  char v81; // [rsp+178h] [rbp+70h] BYREF

  result = 0;
  v72 = 0;
  v2 = 0;
  Handle = 0;
  FileHandle = 0;
  v3 = 0;
  v60 = 0;
  v65 = 0;
  v64 = 0;
  FileObject = 0;
  DeviceObject = 0;
  v61 = 0;
  *(_OWORD *)P = 0;
  memset(v80, 0, 12);
  *(_OWORD *)v70 = 0;
  String2 = 0;
  String1 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  FileInformation = 0;
  FileName = 0;
  if ( gUnloading )
    return result;
  v4 = *a1;
  v5 = a1[1];
  result = WaitForRemoteDatabaseSemaphore(*a1);
  if ( result < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      return WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 123, v6, (unsigned int)result);
    return result;
  }
  if ( gUnloading )
    return KeReleaseSemaphore((PRKSEMAPHORE)(v4 + 112), 0, 1, 0);
  v7 = (struct _KMUTANT *)(v4 + 56);
  KeWaitForSingleObject((PVOID)(v4 + 56), Executive, 0, 0, 0);
  Device = MntMgrFindDevice(v4, v5, v4 + 16);
  if ( Device == v9 || *(_BYTE *)(v5 + 124) || *(_BYTE *)(v5 + 125) )
  {
    KeReleaseMutex((PRKMUTEX)(v4 + 56), 0);
    return KeReleaseSemaphore((PRKSEMAPHORE)(v4 + 112), 0, 1, 0);
  }
  DeviceObjectPointer = IoGetDeviceObjectPointer((PUNICODE_STRING)(v5 + 80), 0x80u, &FileObject, &DeviceObject);
  RemoteDatabaseEntry = DeviceObjectPointer;
  if ( DeviceObjectPointer < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 124, v11, (unsigned int)DeviceObjectPointer);
    goto LABEL_75;
  }
  LODWORD(v68) = 0;
  if ( DeviceObject )
  {
    Vpb = DeviceObject->Vpb;
    if ( Vpb )
    {
      v3 = (Vpb->Flags & 1) != 0;
      LODWORD(v68) = v3;
    }
  }
  ObfDereferenceObject(FileObject);
  v13 = (_QWORD *)(v4 + 16);
  *(_WORD *)(v5 + 131) = 257;
  v14 = *(_QWORD **)(v4 + 16);
  if ( v14 != (_QWORD *)(v4 + 16) )
  {
    do
    {
      v15 = (_QWORD *)v14[6];
      v72 = v14;
      v2 = (unsigned int *)v14;
      if ( v15 != v14 + 6 )
      {
        do
        {
          if ( v15[2] == v5 )
          {
            v14[22] = ++*(_QWORD *)(v4 + 336);
            v38 = *v15;
            if ( *(_QWORD **)(*v15 + 8LL) != v15 || (v39 = (_QWORD *)v15[1], v73 = v39, (_QWORD *)*v39 != v15) )
LABEL_204:
              __fastfail(3u);
            *v39 = v38;
            *(_QWORD *)(v38 + 8) = v39;
            ExFreePoolWithTag((PVOID)v15[4], 0);
            v15[4] = 0;
            ExFreePoolWithTag(v15, 0);
            v15 = v73;
          }
          v15 = (_QWORD *)*v15;
        }
        while ( v15 != v14 + 6 );
        v13 = (_QWORD *)(v4 + 16);
      }
      v14 = (_QWORD *)*v14;
    }
    while ( v14 != v13 );
    v3 = v68;
    v7 = (struct _KMUTANT *)(v4 + 56);
  }
  RemoteDatabaseEntry = OpenRemoteDatabase(v5, 0, &v61, &Handle);
  if ( v61 )
  {
    v44 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v45 = 125;
      goto LABEL_131;
    }
    goto LABEL_97;
  }
  if ( DeviceObject )
  {
    v16 = DeviceObject->Vpb;
    if ( v16 )
    {
      if ( Handle && !v3 && (v16->Flags & 1) != 0 )
        _InterlockedIncrement((volatile signed __int32 *)v2 + 34);
    }
  }
  LOWORD(P[0]) = *(_WORD *)(v5 + 80) + word_140007000;
  WORD1(P[0]) = LOWORD(P[0]) + 2;
  Pool2 = (void *)ExAllocatePool2(258, (unsigned __int16)(LOWORD(P[0]) + 2), 1098149453);
  P[1] = Pool2;
  if ( !Pool2 )
  {
    KeReleaseMutex(v7, 0);
    if ( Handle )
      CloseFileHandleOutsideExtensionMutexLock(0);
    return KeReleaseSemaphore((PRKSEMAPHORE)(v4 + 112), 0, 1, 0);
  }
  memmove(Pool2, *(const void **)(v5 + 88), *(unsigned __int16 *)(v5 + 80));
  memmove((char *)P[1] + *(unsigned __int16 *)(v5 + 80), off_140007008, (unsigned __int16)word_140007000);
  *((_WORD *)P[1] + ((unsigned __int64)LOWORD(P[0]) >> 1)) = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v19 = *(_QWORD **)(v5 + 176);
  v68 = *(_QWORD *)(v4 + 336);
  v18 = v68;
  v73 = v19;
  KeReleaseMutex(v7, 0);
  v20 = IoSetThreadHardErrorMode(0);
  v21 = ZwOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  IoSetThreadHardErrorMode(v20);
  ExFreePoolWithTag(P[1], 0);
  P[1] = 0;
  KeWaitForSingleObject(v7, Executive, 0, 0, 0);
  RemoteDatabaseEntry = VerifyEpoch(v4, v18, v19);
  if ( RemoteDatabaseEntry < 0 )
  {
    LOBYTE(v2) = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 126, v11, (unsigned int)RemoteDatabaseEntry);
    goto LABEL_75;
  }
  if ( v21 < 0 )
  {
    RemoteDatabaseEntry = v21;
    LOBYTE(v2) = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 127, v11, (unsigned int)v21);
    goto LABEL_75;
  }
  LODWORD(v80[0]) = -1610612733;
  FileName.Buffer = (PWSTR)v80;
  *(_QWORD *)((char *)v80 + 4) = 0;
  *(_DWORD *)&FileName.Length = 786444;
  KeReleaseMutex(v7, 0);
  v22 = ZwQueryDirectoryFile(
          FileHandle,
          0,
          0,
          0,
          &IoStatusBlock,
          &FileInformation,
          0x10u,
          FileReparsePointInformation,
          1u,
          &FileName,
          0);
  KeWaitForSingleObject(v7, Executive, 0, 0, 0);
  RemoteDatabaseEntry = VerifyEpoch(v4, v18, v19);
  if ( RemoteDatabaseEntry < 0 )
  {
    LOBYTE(v2) = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 128, v11, (unsigned int)RemoteDatabaseEntry);
    goto LABEL_75;
  }
  if ( v22 < 0 )
  {
    LOBYTE(v2) = 1;
    if ( v22 != -1073741809 )
    {
      RemoteDatabaseEntry = v22;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 130, v11, (unsigned int)v22);
      goto LABEL_75;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 129, v11, 3221225487LL);
    }
    goto LABEL_197;
  }
  v23 = Handle;
  if ( !Handle )
  {
    RemoteDatabaseEntry = OpenRemoteDatabase(v5, 1, &v61, &Handle);
    if ( v61 )
      goto LABEL_97;
    v23 = Handle;
    if ( !Handle )
    {
      v35 = v4 + 16;
LABEL_152:
      v43 = v60;
      goto LABEL_153;
    }
  }
  v24 = 0;
  while ( 1 )
  {
    RemoteDatabaseEntry = GetRemoteDatabaseEntry(v5, v23, v24, (unsigned __int16 **)&v65);
    if ( RemoteDatabaseEntry < 0 )
    {
      v56 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v57 = 131;
        goto LABEL_209;
      }
LABEL_228:
      v35 = v4 + 16;
      goto LABEL_229;
    }
    v25 = v65;
    v60 = v65;
    if ( !v65 )
      break;
    *((_DWORD *)v65 + 1) = 0;
    RemoteDatabaseEntry = WriteRemoteDatabaseEntry(v5, Handle, v24, v25);
    if ( RemoteDatabaseEntry < 0 )
    {
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v45 = 132;
        goto LABEL_131;
      }
      goto LABEL_97;
    }
    v24 += *v25;
    ExFreePoolWithTag(v25, 0);
    v23 = Handle;
    v65 = 0;
  }
  v62 = 0;
  String2.Buffer = (PWSTR)&v81;
  *(_DWORD *)&String2.Length = 13107200;
  v27 = 1;
  while ( 1 )
  {
    while ( 1 )
    {
      v28 = FileInformation;
      v29 = DWORD2(FileInformation);
      KeReleaseMutex((PRKMUTEX)(v4 + 56), 0);
      p_FileName = &FileName;
      if ( !v27 )
        p_FileName = 0;
      RemoteDatabaseEntry = ZwQueryDirectoryFile(
                              FileHandle,
                              0,
                              0,
                              0,
                              &IoStatusBlock,
                              &FileInformation,
                              0x10u,
                              FileReparsePointInformation,
                              1u,
                              p_FileName,
                              v27);
      KeWaitForSingleObject((PVOID)(v4 + 56), Executive, 0, 0, 0);
      v31 = VerifyEpoch(v4, v68, v73);
      v32 = (unsigned int)v31;
      if ( v31 < 0 )
      {
        RemoteDatabaseEntry = v31;
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_97;
        v45 = 133;
        goto LABEL_132;
      }
      if ( v27 )
      {
        v27 = 0;
      }
      else if ( v28 == (_QWORD)FileInformation && v29 == DWORD2(FileInformation) )
      {
        goto LABEL_49;
      }
      if ( RemoteDatabaseEntry < 0 )
      {
        v58 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v59 = 134;
LABEL_217:
          WPP_SF_L(v58->AttachedDevice, v59, v11, (unsigned int)RemoteDatabaseEntry);
        }
LABEL_49:
        v35 = v4 + 16;
        if ( MntMgrFindDevice(v4, v5, v11) == v4 + 16 )
        {
          v43 = 0;
          v5 = 0;
          LOBYTE(v2) = 0;
          goto LABEL_77;
        }
        v36 = 0;
        while ( 1 )
        {
          RemoteDatabaseEntry = GetRemoteDatabaseEntry(v5, Handle, v36, (unsigned __int16 **)&v65);
          if ( RemoteDatabaseEntry < 0 )
            break;
          v37 = v65;
          v60 = v65;
          if ( !v65 )
          {
            if ( !v62 )
              *(_BYTE *)(v5 + 132) = (_BYTE)v65;
            KeReleaseMutex((PRKMUTEX)(v4 + 56), 0);
            ZwClose(FileHandle);
            FileHandle = 0;
            ZwClose(Handle);
            Handle = 0;
            return KeReleaseSemaphore((PRKSEMAPHORE)(v4 + 112), 0, 1, 0);
          }
          if ( *((_DWORD *)v65 + 1) )
          {
            UpdateReplicatedUniqueIds(v5, v65);
            v36 += *v37;
          }
          else
          {
            RemoteDatabaseEntry = DeleteRemoteDatabaseEntry(v5, Handle, v36);
            if ( RemoteDatabaseEntry < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 152, v11, (unsigned int)RemoteDatabaseEntry);
                v43 = v60;
                LOBYTE(v2) = 0;
                goto LABEL_77;
              }
              goto LABEL_152;
            }
          }
          ExFreePoolWithTag(v37, 0);
          v65 = 0;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 151, v11, (unsigned int)RemoteDatabaseEntry);
          v43 = v65;
          LOBYTE(v2) = 0;
          goto LABEL_77;
        }
LABEL_229:
        v43 = v65;
LABEL_153:
        LOBYTE(v2) = 0;
        goto LABEL_77;
      }
      if ( gUnloading )
      {
        v58 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          v59 = 135;
          goto LABEL_217;
        }
        goto LABEL_49;
      }
      if ( DWORD2(FileInformation) != -1610612733 )
        goto LABEL_49;
      VolumeName = QueryVolumeName(
                     v4,
                     v5,
                     FileHandle,
                     (__int64)&FileInformation,
                     0,
                     &String2.Length,
                     (unsigned __int16 *)v70);
      if ( VolumeName >= 0 )
        break;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 136, v34, (unsigned int)VolumeName);
      }
    }
    v40 = 0;
    while ( 1 )
    {
      RemoteDatabaseEntry = GetRemoteDatabaseEntry(v5, Handle, v40, (unsigned __int16 **)&v65);
      if ( RemoteDatabaseEntry < 0 )
      {
        v56 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v57 = 137;
LABEL_209:
          WPP_SF_L(v56->AttachedDevice, v57, v11, (unsigned int)RemoteDatabaseEntry);
          v43 = v65;
          LOBYTE(v2) = 0;
          goto LABEL_76;
        }
        goto LABEL_228;
      }
      v41 = v65;
      v60 = v65;
      if ( !v65 )
      {
        v42 = QueryUniqueIdFromMaster(v4, &String2, &v64);
        if ( v42 >= 0 )
        {
          v54 = String2.Length + 16 + *(unsigned __int16 *)v64;
          v55 = (unsigned int *)ExAllocatePool2(258, v54, 1098149453);
          v60 = v55;
          v2 = v55;
          v65 = v55;
          if ( v55 )
          {
            *v55 = v54;
            v55[1] = 1;
            *((_WORD *)v55 + 4) = 16;
            *((_WORD *)v55 + 5) = String2.Length;
            *((_WORD *)v55 + 6) = *((_WORD *)v55 + 4) + String2.Length;
            *((_WORD *)v55 + 7) = *(_WORD *)v64;
            memmove((char *)v55 + *((unsigned __int16 *)v55 + 4), String2.Buffer, *((unsigned __int16 *)v55 + 5));
            memmove((char *)v2 + *((unsigned __int16 *)v2 + 6), v64 + 2, *((unsigned __int16 *)v2 + 7));
            RemoteDatabaseEntry = AddRemoteDatabaseEntry(v5, Handle, v2);
            ExFreePoolWithTag(v2, 0);
            LOBYTE(v2) = 0;
            v60 = 0;
            v65 = 0;
            ExFreePoolWithTag(v64, 0);
            v64 = 0;
            if ( RemoteDatabaseEntry < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 140, v11, (unsigned int)RemoteDatabaseEntry);
              }
              goto LABEL_75;
            }
          }
          else
          {
            ExFreePoolWithTag(v64, 0);
            v64 = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 139);
            }
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 138, v11, (unsigned int)v42);
        }
        goto LABEL_120;
      }
      String1.MaximumLength = *((_WORD *)v65 + 5);
      String1.Length = String1.MaximumLength;
      String1.Buffer = (PWSTR)((char *)v65 + *((unsigned __int16 *)v65 + 4));
      if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
        break;
      v40 += *v41;
      ExFreePoolWithTag(v41, 0);
      v65 = 0;
    }
    v46 = v41[1];
    if ( v46 )
    {
      v41[1] = v46 + 1;
      RemoteDatabaseEntry = WriteRemoteDatabaseEntry(v5, Handle, v40, v41);
      if ( RemoteDatabaseEntry < 0 )
      {
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v45 = 141;
          goto LABEL_131;
        }
        goto LABEL_97;
      }
      goto LABEL_119;
    }
    if ( (int)QueryUniqueIdFromMaster(v4, &String2, &v64) < 0 )
    {
      RemoteDatabaseEntry = WriteUniqueIdToMaster((PVOID)v4);
      if ( RemoteDatabaseEntry >= 0 )
      {
        ++v41[1];
        RemoteDatabaseEntry = WriteRemoteDatabaseEntry(v5, Handle, v40, v41);
        if ( RemoteDatabaseEntry < 0 )
        {
          v44 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v45 = 149;
            goto LABEL_131;
          }
          goto LABEL_97;
        }
        goto LABEL_119;
      }
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_97;
      v45 = 148;
LABEL_131:
      v32 = (unsigned int)RemoteDatabaseEntry;
LABEL_132:
      WPP_SF_L(v44->AttachedDevice, v45, v11, v32);
      goto LABEL_97;
    }
    if ( *(_WORD *)v64 == *((_WORD *)v41 + 7) )
    {
      v47 = *((unsigned __int16 *)v41 + 7);
      if ( RtlCompareMemory(v64 + 2, (char *)v41 + *((unsigned __int16 *)v41 + 6), v47) == v47 )
        break;
    }
    if ( (unsigned __int8)IsUniqueIdPresent(v4, v41) )
    {
      RemoteDatabaseEntry = WriteUniqueIdToMaster((PVOID)v4);
      if ( RemoteDatabaseEntry < 0 )
      {
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_97;
        v45 = 143;
        goto LABEL_131;
      }
      ++v41[1];
      RemoteDatabaseEntry = WriteRemoteDatabaseEntry(v5, Handle, v40, v41);
      if ( RemoteDatabaseEntry < 0 )
      {
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v45 = 144;
          goto LABEL_131;
        }
        goto LABEL_97;
      }
    }
    else
    {
      RemoteDatabaseEntry = DeleteRemoteDatabaseEntry(v5, Handle, v40);
      if ( RemoteDatabaseEntry < 0 )
      {
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_97;
        v45 = 145;
        goto LABEL_131;
      }
      ExFreePoolWithTag(v41, 0);
      v52 = String2.Length + 16 + *(unsigned __int16 *)v64;
      v53 = ExAllocatePool2(258, v52, 1098149453);
      v60 = (PVOID)v53;
      v41 = (_DWORD *)v53;
      if ( !v53 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 146);
        LOBYTE(v2) = 0;
LABEL_197:
        v43 = 0;
        v35 = v4 + 16;
LABEL_90:
        if ( v5 && MntMgrFindDevice(v4, v5, v11) != v35 )
          *(_BYTE *)(v5 + 132) = 0;
        goto LABEL_78;
      }
      *(_DWORD *)v53 = v52;
      *(_DWORD *)(v53 + 4) = 1;
      *(_WORD *)(v53 + 8) = 16;
      *(_WORD *)(v53 + 10) = String2.Length;
      *(_WORD *)(v53 + 12) = *(_WORD *)(v53 + 8) + String2.Length;
      *(_WORD *)(v53 + 14) = *(_WORD *)v64;
      memmove((void *)(v53 + *(unsigned __int16 *)(v53 + 8)), String2.Buffer, *(unsigned __int16 *)(v53 + 10));
      memmove((char *)v41 + *((unsigned __int16 *)v41 + 6), v64 + 2, *((unsigned __int16 *)v41 + 7));
      RemoteDatabaseEntry = AddRemoteDatabaseEntry(v5, Handle, v41);
      if ( RemoteDatabaseEntry < 0 )
      {
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v45 = 147;
          goto LABEL_131;
        }
        goto LABEL_97;
      }
    }
LABEL_118:
    ExFreePoolWithTag(v64, 0);
    v64 = 0;
LABEL_119:
    ExFreePoolWithTag(v41, 0);
    v60 = 0;
    v65 = 0;
LABEL_120:
    if ( (int)FindDeviceInfo(v4, &String2, v11, &v72) < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 150, v48, 0);
      }
      v62 = 1;
      ExFreePoolWithTag(v70[1], 0);
      v70[1] = 0;
    }
    else
    {
      v49 = ExAllocatePool2(258, 40, 1098149453);
      v50 = v72;
      if ( v49 )
      {
        v51 = (__int64 *)v72[7];
        if ( (_QWORD *)*v51 != v72 + 6 )
          goto LABEL_204;
        *(_QWORD *)v49 = v72 + 6;
        *(_QWORD *)(v49 + 8) = v51;
        *v51 = v49;
        v50[7] = v49;
        *(_QWORD *)(v49 + 16) = v5;
        *(_OWORD *)(v49 + 24) = *(_OWORD *)v70;
        v70[1] = 0;
        v50[22] = ++*(_QWORD *)(v4 + 336);
      }
      else
      {
        ExFreePoolWithTag(v70[1], 0);
        v70[1] = 0;
      }
      if ( !*((_BYTE *)v50 + 133) )
        PostOnlineNotification(v4, v50 + 8);
    }
  }
  ++v41[1];
  RemoteDatabaseEntry = WriteRemoteDatabaseEntry(v5, Handle, v40, v41);
  if ( RemoteDatabaseEntry >= 0 )
    goto LABEL_118;
  v44 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v45 = 142;
    goto LABEL_131;
  }
LABEL_97:
  LOBYTE(v2) = 0;
LABEL_75:
  v43 = v60;
LABEL_76:
  v35 = v4 + 16;
LABEL_77:
  if ( RemoteDatabaseEntry != -1073741810 )
    goto LABEL_90;
LABEL_78:
  KeReleaseMutex((PRKMUTEX)(v4 + 56), 0);
  if ( v64 )
  {
    ExFreePoolWithTag(v64, 0);
    v64 = 0;
  }
  if ( v43 )
    ExFreePoolWithTag(v43, 0);
  if ( v70[1] )
  {
    ExFreePoolWithTag(v70[1], 0);
    v70[1] = 0;
  }
  if ( FileHandle )
  {
    CloseFileHandleOutsideExtensionMutexLock(0);
    FileHandle = 0;
  }
  if ( Handle )
  {
    if ( (_BYTE)v2 == 1 )
      TruncateRemoteDatabase(Handle);
    CloseFileHandleOutsideExtensionMutexLock(0);
    Handle = 0;
  }
  return KeReleaseSemaphore((PRKSEMAPHORE)(v4 + 112), 0, 1, 0);
}

```

## disassembly

```asm
0x1400119a0  mov     r11, rsp
0x1400119a3  push    rbp
0x1400119a4  push    rbx
0x1400119a5  push    rdi
0x1400119a6  push    r12
0x1400119a8  lea     rbp, [r11-178h]
0x1400119af  sub     rsp, 258h
0x1400119b6  mov     rax, cs:__security_cookie
0x1400119bd  xor     rax, rsp
0x1400119c0  mov     [rbp+170h+var_30], rax
0x1400119c7  xor     ebx, ebx
0x1400119c9  xorps   xmm0, xmm0
0x1400119cc  xor     eax, eax
0x1400119ce  mov     [rbp+170h+var_1A0], rbx
0x1400119d2  cmp     cs:gUnloading, eax
0x1400119d8  xorps   xmm1, xmm1
0x1400119db  mov     r12d, ebx
0x1400119de  mov     [rsp+270h+Handle], rbx
0x1400119e3  mov     [rbp+170h+FileHandle], rbx
0x1400119e7  mov     edi, ebx
0x1400119e9  mov     [rsp+270h+var_210], rbx
0x1400119ee  mov     [rbp+170h+var_1F0], rbx
0x1400119f2  mov     [rsp+270h+var_1F8], rbx
0x1400119f7  mov     [rbp+170h+FileObject], rbx
0x1400119fb  mov     [rbp+170h+DeviceObject], rbx
0x1400119ff  mov     byte ptr [rsp+270h+var_208], bl
0x140011a03  movups  xmmword ptr [rbp+170h+P], xmm0
0x140011a07  mov     [rbp+170h+var_118], rax
0x140011a0b  movups  xmmword ptr [rbp+170h+var_1B8], xmm1
0x140011a0f  mov     [rbp+170h+var_110], eax
0x140011a12  movups  xmmword ptr [rbp+170h+String2.Length], xmm0
0x140011a16  movups  xmmword ptr [rbp+170h+String1.Length], xmm1
0x140011a1a  movups  xmmword ptr [rbp+170h+ObjectAttributes.Length], xmm0
0x140011a1e  movups  xmmword ptr [rbp+170h+ObjectAttributes.ObjectName], xmm0
0x140011a22  movups  xmmword ptr [rbp+170h+ObjectAttributes.SecurityDescriptor], xmm0
0x140011a26  movups  xmmword ptr [rbp+170h+IoStatusBlock], xmm0
0x140011a2a  movups  [rbp+170h+FileInformation], xmm1
0x140011a2e  movups  xmmword ptr [rbp+170h+var_188.Length], xmm0
0x140011a32  jnz     loc_140012DC6
0x140011a38  mov     [r11+10h], rsi
0x140011a3c  mov     rsi, [rcx]
0x140011a3f  mov     [r11-28h], r15
0x140011a43  mov     r15, [rcx+8]
0x140011a47  mov     rcx, rsi
0x140011a4a  mov     [r11+18h], r13
0x140011a4e  call    WaitForRemoteDatabaseSemaphore
0x140011a53  test    eax, eax
0x140011a55  js      loc_140012629
0x140011a5b  cmp     cs:gUnloading, ebx
0x140011a61  mov     [rsp+270h+arg_18], r14
0x140011a69  jnz     loc_140011BD8
0x140011a6f  lea     r14, [rsi+38h]
0x140011a73  mov     [rsp+270h+Timeout], rbx; Timeout
0x140011a78  mov     rcx, r14; Object
0x140011a7b  xor     r9d, r9d; Alertable
0x140011a7e  xor     r8d, r8d; WaitMode
0x140011a81  xor     edx, edx; WaitReason
0x140011a83  call    cs:__imp_KeWaitForSingleObject
0x140011a8a  nop     dword ptr [rax+rax+00h]
0x140011a8f  mov     rdx, r15
0x140011a92  lea     r8, [rsi+10h]
0x140011a96  mov     rcx, rsi
0x140011a99  call    MntMgrFindDevice
0x140011a9e  cmp     rax, r8
0x140011aa1  jz      loc_140012326
0x140011aa7  cmp     [r15+7Ch], bl
0x140011aab  jnz     loc_140012326
0x140011ab1  cmp     [r15+7Dh], bl
0x140011ab5  jnz     loc_140012326
0x140011abb  lea     r9, [rbp+170h+DeviceObject]; DeviceObject
0x140011abf  mov     edx, 80h; DesiredAccess
0x140011ac4  lea     r8, [rbp+170h+FileObject]; FileObject
0x140011ac8  lea     rcx, [r15+50h]; ObjectName
0x140011acc  call    cs:__imp_IoGetDeviceObjectPointer
0x140011ad3  nop     dword ptr [rax+rax+00h]
0x140011ad8  mov     ebx, eax
0x140011ada  test    eax, eax
0x140011adc  js      loc_1400121F9
0x140011ae2  mov     rax, [rbp+170h+DeviceObject]
0x140011ae6  mov     ecx, 1
0x140011aeb  mov     dword ptr [rbp+170h+var_1D0], edi
0x140011aee  test    rax, rax
0x140011af1  jnz     loc_140011E78
0x140011af7  mov     rcx, [rbp+170h+FileObject]; Object
0x140011afb  call    cs:__imp_ObfDereferenceObject
0x140011b02  nop     dword ptr [rax+rax+00h]
0x140011b07  lea     rax, [rsi+10h]
0x140011b0b  mov     word ptr [r15+83h], 101h
0x140011b15  mov     rbx, [rax]
0x140011b18  cmp     rbx, rax
0x140011b1b  jz      short loc_140011B47
0x140011b1d  nop     dword ptr [rax]
0x140011b20  mov     r14, [rbx+30h]
0x140011b24  lea     rdi, [rbx+30h]
0x140011b28  mov     [rbp+170h+var_1A0], rbx
0x140011b2c  mov     r12, rbx
0x140011b2f  cmp     r14, rdi
0x140011b32  jnz     loc_1400120C2
0x140011b38  mov     rbx, [rbx]
0x140011b3b  cmp     rbx, rax
0x140011b3e  jnz     short loc_140011B20
0x140011b40  mov     edi, dword ptr [rbp+170h+var_1D0]
0x140011b43  lea     r14, [rsi+38h]
0x140011b47  lea     r9, [rsp+270h+Handle]
0x140011b4c  xor     edx, edx
0x140011b4e  lea     r8, [rsp+270h+var_208]
0x140011b53  mov     rcx, r15
0x140011b56  call    OpenRemoteDatabase
0x140011b5b  cmp     byte ptr [rsp+270h+var_208], 0
0x140011b60  mov     ebx, eax
0x140011b62  jnz     loc_140012307
0x140011b68  mov     rax, [rbp+170h+DeviceObject]
0x140011b6c  test    rax, rax
0x140011b6f  jz      short loc_140011B7E
0x140011b71  mov     rax, [rax+38h]
0x140011b75  test    rax, rax
0x140011b78  jnz     loc_140012699
0x140011b7e  movzx   eax, cs:word_140007000
0x140011b85  mov     ecx, 102h
0x140011b8a  add     ax, [r15+50h]
0x140011b8f  mov     r8d, 41746E4Dh
0x140011b95  mov     word ptr [rbp+170h+P], ax
0x140011b99  add     ax, 2
0x140011b9d  movzx   edx, ax
0x140011ba0  mov     word ptr [rbp+170h+P+2], dx
0x140011ba4  call    cs:__imp_ExAllocatePool2
0x140011bab  nop     dword ptr [rax+rax+00h]
0x140011bb0  mov     [rbp+170h+P+8], rax
0x140011bb4  test    rax, rax
0x140011bb7  jnz     short loc_140011C19
0x140011bb9  xor     edx, edx; Wait
0x140011bbb  mov     rcx, r14; Mutex
0x140011bbe  call    cs:__imp_KeReleaseMutex
0x140011bc5  nop     dword ptr [rax+rax+00h]
0x140011bca  mov     rdx, [rsp+270h+Handle]
0x140011bcf  test    rdx, rdx
0x140011bd2  jnz     loc_1400126C6
0x140011bd8  xor     r9d, r9d; Wait
0x140011bdb  lea     rcx, [rsi+70h]; Semaphore
0x140011bdf  mov     r8d, 1; Adjustment
0x140011be5  xor     edx, edx; Increment
0x140011be7  call    cs:__imp_KeReleaseSemaphore
0x140011bee  nop     dword ptr [rax+rax+00h]
0x140011bf3  mov     r14, [rsp+270h+arg_18]
0x140011bfb  mov     r13, [rsp+270h+arg_10]
0x140011c03  mov     rsi, [rsp+270h+arg_8]
0x140011c0b  mov     r15, [rsp+250h]
0x140011c13  jmp     loc_140012DC6
0x140011c19  movzx   r8d, word ptr [r15+50h]; Size
0x140011c1e  mov     rcx, rax; void *
0x140011c21  mov     rdx, [r15+58h]; Src
0x140011c25  call    memmove
0x140011c2a  movzx   ecx, word ptr [r15+50h]
0x140011c2f  add     rcx, [rbp+170h+P+8]; void *
0x140011c33  movzx   r8d, cs:word_140007000; Size
0x140011c3b  mov     rdx, cs:off_140007008; Src
0x140011c42  call    memmove
0x140011c47  movzx   edx, word ptr [rbp+170h+P]
0x140011c4b  xor     ecx, ecx
0x140011c4d  mov     rax, [rbp+170h+P+8]
0x140011c51  xorps   xmm0, xmm0
0x140011c54  shr     rdx, 1
0x140011c57  mov     [rax+rdx*2], cx
0x140011c5b  lea     rax, [rbp+170h+P]
0x140011c5f  mov     [rbp+170h+ObjectAttributes.RootDirectory], rcx
0x140011c63  xor     edx, edx; Wait
0x140011c65  mov     [rbp+170h+ObjectAttributes.ObjectName], rax
0x140011c69  mov     rcx, r14; Mutex
0x140011c6c  mov     [rbp+170h+ObjectAttributes.Length], 30h ; '0'
0x140011c73  mov     [rbp+170h+ObjectAttributes.Attributes], 240h
0x140011c7a  movdqu  xmmword ptr [rbp+170h+ObjectAttributes.SecurityDescriptor], xmm0
0x140011c7f  mov     r12, [rsi+150h]
0x140011c86  mov     r13, [r15+0B0h]
0x140011c8d  mov     [rbp+170h+var_1D0], r12
0x140011c91  mov     [rbp+170h+var_198], r13
0x140011c95  call    cs:__imp_KeReleaseMutex
0x140011c9c  nop     dword ptr [rax+rax+00h]
0x140011ca1  xor     ecx, ecx; EnableHardErrors
0x140011ca3  call    cs:__imp_IoSetThreadHardErrorMode
0x140011caa  nop     dword ptr [rax+rax+00h]
0x140011caf  lea     r9, [rbp+170h+IoStatusBlock]; IoStatusBlock
0x140011cb3  mov     [rsp+270h+OpenOptions], 20h ; ' '; OpenOptions
0x140011cbb  lea     r8, [rbp+170h+ObjectAttributes]; ObjectAttributes
0x140011cbf  mov     dword ptr [rsp+270h+Timeout], 3; ShareAccess
0x140011cc7  mov     edx, 120089h; DesiredAccess
0x140011ccc  lea     rcx, [rbp+170h+FileHandle]; FileHandle
0x140011cd0  movzx   ebx, al
0x140011cd3  call    cs:__imp_ZwOpenFile
0x140011cda  nop     dword ptr [rax+rax+00h]
0x140011cdf  movzx   ecx, bl; EnableHardErrors
0x140011ce2  mov     edi, eax
0x140011ce4  call    cs:__imp_IoSetThreadHardErrorMode
0x140011ceb  nop     dword ptr [rax+rax+00h]
0x140011cf0  mov     rcx, [rbp+170h+P+8]; P
0x140011cf4  xor     edx, edx; Tag
0x140011cf6  call    cs:__imp_ExFreePoolWithTag
0x140011cfd  nop     dword ptr [rax+rax+00h]
0x140011d02  xor     eax, eax
0x140011d04  xor     r9d, r9d; Alertable
0x140011d07  xor     r8d, r8d; WaitMode
0x140011d0a  mov     [rbp+170h+P+8], rax
0x140011d0e  xor     edx, edx; WaitReason
0x140011d10  mov     [rsp+270h+Timeout], rax; Timeout
0x140011d15  mov     rcx, r14; Object
0x140011d18  call    cs:__imp_KeWaitForSingleObject
0x140011d1f  nop     dword ptr [rax+rax+00h]
0x140011d24  mov     r8, r13
0x140011d27  mov     rdx, r12
0x140011d2a  mov     rcx, rsi
0x140011d2d  call    VerifyEpoch
0x140011d32  mov     ebx, eax
0x140011d34  test    eax, eax
0x140011d36  js      loc_14001233C
0x140011d3c  test    edi, edi
0x140011d3e  js      loc_1400122C9
0x140011d44  lea     rax, [rbp+170h+var_118]
0x140011d48  mov     dword ptr [rbp+170h+var_118], 0A0000003h
0x140011d4f  xor     ebx, ebx
0x140011d51  mov     [rbp+170h+var_188.Buffer], rax
0x140011d55  xor     edx, edx; Wait
0x140011d57  mov     [rbp+170h+var_118+4], rbx
0x140011d5b  mov     rcx, r14; Mutex
0x140011d5e  mov     dword ptr [rbp+170h+var_188.Length], 0C000Ch
0x140011d65  call    cs:__imp_KeReleaseMutex
0x140011d6c  nop     dword ptr [rax+rax+00h]
0x140011d71  mov     rcx, [rbp+170h+FileHandle]; FileHandle
0x140011d75  lea     rax, [rbp+170h+var_188]
0x140011d79  mov     [rsp+50h], bl; RestartScan
0x140011d7d  xor     r9d, r9d; ApcContext
0x140011d80  mov     [rsp+270h+FileName], rax; FileName
0x140011d85  xor     r8d, r8d; ApcRoutine
0x140011d88  mov     [rsp+270h+ReturnSingleEntry], 1; ReturnSingleEntry
0x140011d8d  lea     rax, [rbp+170h+FileInformation]
0x140011d91  mov     [rsp+270h+FileInformationClass], 21h ; '!'; FileInformationClass
0x140011d99  xor     edx, edx; Event
0x140011d9b  mov     [rsp+270h+Length], 10h; Length
0x140011da3  mov     qword ptr [rsp+270h+OpenOptions], rax; FileInformation
0x140011da8  lea     rax, [rbp+170h+IoStatusBlock]
0x140011dac  mov     [rsp+270h+Timeout], rax; IoStatusBlock
0x140011db1  call    cs:__imp_ZwQueryDirectoryFile
0x140011db8  nop     dword ptr [rax+rax+00h]
0x140011dbd  xor     r9d, r9d; Alertable
0x140011dc0  mov     [rsp+270h+Timeout], rbx; Timeout
0x140011dc5  xor     r8d, r8d; WaitMode
0x140011dc8  xor     edx, edx; WaitReason
0x140011dca  mov     rcx, r14; Object
0x140011dcd  mov     edi, eax
0x140011dcf  call    cs:__imp_KeWaitForSingleObject
0x140011dd6  nop     dword ptr [rax+rax+00h]
0x140011ddb  mov     r8, r13
0x140011dde  mov     rdx, r12
0x140011de1  mov     rcx, rsi
0x140011de4  call    VerifyEpoch
0x140011de9  mov     ebx, eax
0x140011deb  test    eax, eax
0x140011ded  js      loc_140012378
0x140011df3  test    edi, edi
0x140011df5  js      loc_1400123B4
0x140011dfb  mov     rdx, [rsp+270h+Handle]
0x140011e00  test    rdx, rdx
0x140011e03  jz      loc_14001270D
0x140011e09  xor     r14d, r14d
0x140011e0c  mov     edi, r14d
0x140011e0f  lea     r9, [rbp+170h+var_1F0]
0x140011e13  mov     r8d, edi
0x140011e16  mov     rcx, r15
0x140011e19  call    GetRemoteDatabaseEntry
0x140011e1e  mov     ebx, eax
0x140011e20  test    eax, eax
0x140011e22  js      loc_140012D3A
0x140011e28  mov     r12, [rbp+170h+var_1F0]
0x140011e2c  mov     [rsp+270h+var_210], r12
0x140011e31  test    r12, r12
0x140011e34  jz      short loc_140011E97
0x140011e36  mov     [r12+4], r14d
0x140011e3b  mov     r9, r12
0x140011e3e  mov     rdx, [rsp+270h+Handle]
0x140011e43  mov     r8d, edi
0x140011e46  mov     rcx, r15
0x140011e49  call    WriteRemoteDatabaseEntry
0x140011e4e  mov     ebx, eax
0x140011e50  test    eax, eax
0x140011e52  js      loc_14001274D
0x140011e58  add     edi, [r12]
0x140011e5c  xor     edx, edx; Tag
0x140011e5e  mov     rcx, r12; P
0x140011e61  call    cs:__imp_ExFreePoolWithTag
0x140011e68  nop     dword ptr [rax+rax+00h]
0x140011e6d  mov     rdx, [rsp+270h+Handle]
0x140011e72  mov     [rbp+170h+var_1F0], r14
0x140011e76  jmp     short loc_140011E0F
0x140011e78  mov     rax, [rax+38h]
0x140011e7c  test    rax, rax
0x140011e7f  jz      loc_140011AF7
0x140011e85  test    [rax+4], cl
0x140011e88  movzx   edi, dil
0x140011e8c  cmovnz  edi, ecx
0x140011e8f  mov     dword ptr [rbp+170h+var_1D0], edi
0x140011e92  jmp     loc_140011AF7
0x140011e97  lea     rax, [rbp+170h+var_100]
  ... truncated ...
```
