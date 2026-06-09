# HsmFltPreSetRenameInformation

- ea: `0x140053800`
- end: `0x1400548c1`
- name: `HsmFltPreSetRenameInformation`
- size: `4289`
- prototype: `__int64 __fastcall(unsigned __int16 *Context, union _LARGE_INTEGER *, void *, struct _FLT_CALLBACK_DATA *, __int64, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400526d0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x14000ac28`
- `0x14000d388`
- `0x14001e1c0`
- `0x14001e300`
- `0x14001e600`
- `0x14001eb20`
- `0x140050dc0`
- `0x1400521f0`
- `0x140053800`
- `0x1400548d0`
- `0x1400548ec`
- `0x140054b24`
- `0x140054bbc`
- `0x140055370`
- `0x140057b20`
- `0x140059090`
- `0x14005f670`

## import_xrefs

- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140053af5`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140053af5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400542b5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400542b5`
- `ntoskrnl!KeInitializeEvent` at `0x140054229`
- `ntoskrnl!KeInitializeEvent` at `0x140054229`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400539ce`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400539ce`
- `ntoskrnl!ObfDereferenceObject` at `0x14005466a`
- `ntoskrnl!ObfDereferenceObject` at `0x140054876`
- `ntoskrnl!ObfDereferenceObject` at `0x14005466a`
- `ntoskrnl!ObfDereferenceObject` at `0x140054876`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053dd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054854`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005488f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053dd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054854`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005488f`
- `ntoskrnl!ExAllocatePool2` at `0x140053ff3`
- `ntoskrnl!ExAllocatePool2` at `0x14005454c`
- `ntoskrnl!ExAllocatePool2` at `0x140053ff3`
- `ntoskrnl!ExAllocatePool2` at `0x14005454c`
- `FLTMGR!FltQueryInformationByName` at `0x140053b82`
- `FLTMGR!FltQueryInformationByName` at `0x140053b82`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x140053aa2`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x140053aa2`
- `FLTMGR!FltClose` at `0x140054653`
- `FLTMGR!FltClose` at `0x140054865`
- `FLTMGR!FltClose` at `0x140054653`
- `FLTMGR!FltClose` at `0x140054865`
- `FLTMGR!FltQueryInformationFile` at `0x140053c47`
- `FLTMGR!FltQueryInformationFile` at `0x140053c47`
- `FLTMGR!FltReferenceContext` at `0x140053c89`
- `FLTMGR!FltReferenceContext` at `0x140053de4`
- `FLTMGR!FltReferenceContext` at `0x140053c89`
- `FLTMGR!FltReferenceContext` at `0x140053de4`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14005426c`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14005426c`
- `FLTMGR!FltQueryDirectoryFile` at `0x1400545ce`
- `FLTMGR!FltQueryDirectoryFile` at `0x1400545ce`
- `FLTMGR!FltCreateFileEx2` at `0x1400544ea`
- `FLTMGR!FltCreateFileEx2` at `0x1400544ea`
- `FLTMGR!FltCancelIo` at `0x140054294`
- `FLTMGR!FltCancelIo` at `0x140054294`
- `FLTMGR!FltGetRequestorProcess` at `0x14005471f`
- `FLTMGR!FltGetRequestorProcess` at `0x14005471f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140053d1f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140053d1f`
- `FLTMGR!FltReleaseContext` at `0x140053d6e`
- `FLTMGR!FltReleaseContext` at `0x140054071`
- `FLTMGR!FltReleaseContext` at `0x1400548a3`
- `FLTMGR!FltReleaseContext` at `0x140053d6e`
- `FLTMGR!FltReleaseContext` at `0x140054071`
- `FLTMGR!FltReleaseContext` at `0x1400548a3`

## pseudocode

```c
__int64 __fastcall HsmFltPreSetRenameInformation(
        unsigned __int16 *Context,
        union _LARGE_INTEGER *a2,
        void *a3,
        struct _FLT_CALLBACK_DATA *a4,
        __int64 a5,
        __int64 a6)
{
  union _LARGE_INTEGER *StreamContext; // r13
  struct _FILE_OBJECT *v9; // rdi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  ULONG Options; // ecx
  char *EaBuffer; // rbx
  PFLT_FILE_NAME_INFORMATION *v13; // r14
  struct _FLT_INSTANCE *v14; // rdi
  __int16 v15; // ax
  NTSTATUS DestinationFileNameInformation; // edi
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  struct _FILE_OBJECT *v20; // r8
  void *v21; // r8
  WCHAR *v22; // r9
  ULONG FileNameLength; // eax
  PFILE_OBJECT v24; // rbx
  int v25; // ebx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 Status; // rdx
  unsigned int v30; // esi
  __int64 v32; // rdi
  size_t Length; // r8
  char *v34; // rax
  int v35; // edi
  __int64 v36; // rdx
  PFLT_FILE_NAME_INFORMATION *v37; // rax
  __int64 v38; // rax
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  int v40; // eax
  int v41; // edi
  unsigned int v42; // ebx
  _QWORD *Pool2; // rax
  _QWORD *v44; // r9
  PDEVICE_OBJECT v45; // rcx
  __int64 v46; // rdx
  int v47; // ecx
  union _LARGE_INTEGER v48; // r14
  unsigned int v49; // edx
  char *v50; // rdi
  __int64 v51; // rbx
  PVOID v52; // r9
  __int64 v53; // r8
  __int64 v54; // r8
  __int64 v55; // rdi
  int v56; // eax
  int v57; // ecx
  int v58; // r9d
  int v59; // edx
  PFLT_IO_PARAMETER_BLOCK v60; // rdx
  char *v61; // r14
  NTSTATUS v62; // ebx
  __int64 v63; // rax
  unsigned int v64; // ecx
  unsigned int RequestorProcess; // eax
  PFILE_OBJECT NameOptions; // [rsp+28h] [rbp-D8h]
  PFLT_FILE_NAME_INFORMATION *RetFileNameInformation; // [rsp+30h] [rbp-D0h]
  PLARGE_INTEGER AllocationSize; // [rsp+38h] [rbp-C8h]
  int AllocationSizea; // [rsp+38h] [rbp-C8h]
  int FileAttributes; // [rsp+40h] [rbp-C0h]
  bool v71[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v72; // [rsp+82h] [rbp-7Eh]
  char v73; // [rsp+84h] [rbp-7Ch]
  PFLT_FILE_NAME_INFORMATION *v74; // [rsp+88h] [rbp-78h]
  unsigned int v75; // [rsp+90h] [rbp-70h] BYREF
  int SyncRootFileIdByFileObject; // [rsp+94h] [rbp-6Ch] BYREF
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp-68h]
  PFLT_INSTANCE Instance; // [rsp+A0h] [rbp-60h]
  __int64 v79; // [rsp+A8h] [rbp-58h]
  PFILE_OBJECT v80; // [rsp+B0h] [rbp-50h] BYREF
  __int64 QuadPart; // [rsp+B8h] [rbp-48h] BYREF
  void *FileHandle; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v83; // [rsp+C8h] [rbp-38h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+D0h] [rbp-30h] BYREF
  __int64 FileInformation; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v86; // [rsp+E0h] [rbp-20h] BYREF
  PVOID P; // [rsp+E8h] [rbp-18h]
  PFLT_CONTEXT v88; // [rsp+F0h] [rbp-10h]
  ULONG LengthReturned; // [rsp+F8h] [rbp-8h] BYREF
  UNICODE_STRING String2; // [rsp+100h] [rbp+0h] BYREF
  struct _KEVENT String1; // [rsp+110h] [rbp+10h] BYREF
  __int128 v92; // [rsp+128h] [rbp+28h] BYREF
  PFLT_FILE_NAME_INFORMATION *v93; // [rsp+138h] [rbp+38h] BYREF
  __int64 v94; // [rsp+140h] [rbp+40h]
  PVOID v95; // [rsp+148h] [rbp+48h]
  PFLT_CONTEXT Contexta[2]; // [rsp+150h] [rbp+50h] BYREF
  PFLT_CONTEXT v97[2]; // [rsp+160h] [rbp+60h]
  __int128 v98; // [rsp+170h] [rbp+70h]
  __int64 v99; // [rsp+180h] [rbp+80h]
  __int64 v100; // [rsp+188h] [rbp+88h]
  PFLT_CONTEXT v101; // [rsp+190h] [rbp+90h]
  PVOID v102[2]; // [rsp+198h] [rbp+98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1A8h] [rbp+A8h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v105; // [rsp+1F8h] [rbp+F8h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+200h] [rbp+100h] BYREF
  _QWORD v107[10]; // [rsp+210h] [rbp+110h] BYREF

  v94 = a6;
  StreamContext = a2;
  v101 = a3;
  v100 = a5;
  v9 = *(struct _FILE_OBJECT **)(a5 + 32);
  Instance = *(PFLT_INSTANCE *)(a5 + 24);
  Iopb = a4->Iopb;
  FileObject = v9;
  Options = Iopb->Parameters.Create.Options;
  EaBuffer = (char *)Iopb->Parameters.Create.EaBuffer;
  FileNameInformation = 0;
  if ( a2 && (v48 = a2[2], v48.QuadPart) )
    v13 = *(PFLT_FILE_NAME_INFORMATION **)(v48.QuadPart + 32);
  else
    v13 = 0;
  FileInformation = 0;
  QuadPart = Iopb->Parameters.Read.ByteOffset.QuadPart;
  v74 = v13;
  v86 = 0;
  v83 = 0;
  v93 = 0;
  v79 = 0;
  v75 = 0;
  SyncRootFileIdByFileObject = 0;
  P = 0;
  v73 = 0;
  v92 = 0;
  *(_OWORD *)v102 = 0;
  v71[0] = Options == 10 && *EaBuffer || Options == 65 && (*(_DWORD *)EaBuffer & 1) != 0;
  if ( Options != 65 || (v19 = *(_DWORD *)EaBuffer, LOBYTE(v72) = 1, (v19 & 2) == 0) )
    LOBYTE(v72) = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(v107, 0, 0x48u);
  FileHandle = 0;
  v80 = 0;
  v95 = 0;
  *(_OWORD *)Contexta = 0;
  v99 = 0;
  *(_OWORD *)v97 = 0;
  v98 = 0;
  v88 = (PFLT_CONTEXT)HsmpAcquireFileNameLock(Context);
  if ( !v88 )
    goto LABEL_76;
  if ( StreamContext )
  {
    v14 = Instance;
  }
  else
  {
    v20 = v9;
    v14 = Instance;
    StreamContext = (union _LARGE_INTEGER *)HsmpGetStreamContext(a4, Instance, v20);
    if ( !StreamContext )
    {
      v73 = 0;
      goto LABEL_29;
    }
    v73 = 1;
  }
  if ( !QuadPart && *((_DWORD *)EaBuffer + 4) >= 2u && *((_WORD *)EaBuffer + 10) == 58 )
  {
    *(_QWORD *)&String2.Length = 5505106;
    *(_QWORD *)&String1.Header.Lock = 0;
    String1.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)(EaBuffer + 20);
    *(_WORD *)&String1.Header.Size = *((_WORD *)EaBuffer + 8);
    v15 = *(_WORD *)&String1.Header.Size;
    String2.Buffer = L":${3D0CE612-FDEE-43f7-8ACA-957BEC0CCBA0}.";
    if ( *(_WORD *)&String1.Header.Size > 0x52u )
      v15 = 82;
    LOWORD(String1.Header.Lock) = v15;
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)&String1, &String2, 1u) )
    {
      DestinationFileNameInformation = -1073688808;
      HsmDbgBreakOnStatus(-1073688808);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_75;
      }
      v18 = 39;
      goto LABEL_145;
    }
  }
LABEL_29:
  v21 = (void *)*((_QWORD *)EaBuffer + 1);
  v22 = (WCHAR *)(EaBuffer + 20);
  FileNameLength = *((_DWORD *)EaBuffer + 4);
  v24 = FileObject;
  DestinationFileNameInformation = FltGetDestinationFileNameInformation(
                                     v14,
                                     FileObject,
                                     v21,
                                     v22,
                                     FileNameLength,
                                     0x101u,
                                     &FileNameInformation);
  HsmDbgBreakOnStatus(DestinationFileNameInformation);
  if ( DestinationFileNameInformation < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_75;
    }
    v18 = 40;
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    FileAttributes = DestinationFileNameInformation;
    AllocationSize = StreamContext;
    RetFileNameInformation = v74;
    NameOptions = FileObject;
    goto LABEL_95;
  }
  if ( !(_BYTE)v72 && !StreamContext )
    goto LABEL_40;
  v105 = 1;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  DriverContext.TxnParameters = IoGetTransactionParameterBlock(FileObject);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &FileNameInformation->Name;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  DestinationFileNameInformation = FltQueryInformationByName(
                                     Filter,
                                     Instance,
                                     &ObjectAttributes,
                                     &IoStatusBlock,
                                     v107,
                                     72,
                                     68,
                                     &DriverContext);
  HsmDbgBreakOnStatus(DestinationFileNameInformation);
  if ( DestinationFileNameInformation < 0 )
  {
    if ( DestinationFileNameInformation != -1073741772 && DestinationFileNameInformation != -1073741766 )
    {
LABEL_35:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qiqiid(
          WPP_GLOBAL_Control->AttachedDevice,
          44,
          WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
          a4,
          Context,
          v24,
          v74,
          StreamContext,
          DestinationFileNameInformation);
      }
      goto LABEL_75;
    }
LABEL_40:
    if ( !StreamContext )
    {
      *(_QWORD *)&String2.Length = *((_QWORD *)&v92 + 1);
      v72 = v92;
      goto LABEL_42;
    }
    v32 = QuadPart;
    Length = FileNameInformation->Volume.Length;
    v34 = (char *)FileNameInformation->Name.Buffer + Length;
    v72 = FileNameInformation->Name.Length - Length;
    LOWORD(v92) = v72;
    *(_QWORD *)&String2.Length = v34;
    *((_QWORD *)&v92 + 1) = v34;
    WORD1(v92) = v72;
    if ( QuadPart
      && (Context[32] != Length + 2 || memcmp(*((const void **)Context + 9), FileNameInformation->Volume.Buffer, Length)) )
    {
      DestinationFileNameInformation = -1073741612;
      HsmDbgBreakOnStatus(-1073741612);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_75;
      }
      v18 = 45;
      goto LABEL_128;
    }
    QuadPart = v79 & -(__int64)(v32 != 0);
    SyncRootFileIdByFileObject = HsmiCldGetSyncRootFileIdByFileObject(
                                   Context,
                                   v24,
                                   &v86,
                                   &v75,
                                   &SyncRootFileIdByFileObject);
    v35 = SyncRootFileIdByFileObject;
    HsmDbgBreakOnStatus(SyncRootFileIdByFileObject);
    if ( v35 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_qqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        55,
        WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
        Context,
        StreamContext,
        v24,
        v35);
    }
    HsmDbgBreakOnStatus(v35);
    DestinationFileNameInformation = 0;
    if ( SyncRootFileIdByFileObject != -1073688813 )
      DestinationFileNameInformation = SyncRootFileIdByFileObject;
    if ( DestinationFileNameInformation < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_75;
      }
      v18 = 46;
      goto LABEL_128;
    }
    DestinationFileNameInformation = HsmiQueryFullFilePath(Instance, v36, v24, 258, v102);
    HsmDbgBreakOnStatus(DestinationFileNameInformation);
    if ( DestinationFileNameInformation < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_75;
      }
      v18 = 47;
      goto LABEL_128;
    }
    DestinationFileNameInformation = HsmiCldGetSyncRootFileIdByPath(Context, v102, &v93);
    HsmDbgBreakOnStatus(DestinationFileNameInformation);
    if ( DestinationFileNameInformation == -1073688813 )
    {
      v37 = 0;
    }
    else
    {
      if ( DestinationFileNameInformation < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_75;
        }
        v18 = 48;
        goto LABEL_128;
      }
      v37 = v93;
    }
    v83 = (__int64)v37;
    if ( v37 != v74 )
    {
      DestinationFileNameInformation = HsmiCldGetSyncRootFileIdByPath(Context, &v92, &QuadPart);
      HsmDbgBreakOnStatus(DestinationFileNameInformation);
      if ( DestinationFileNameInformation == -1073688813 )
      {
        v79 = 0;
LABEL_42:
        DestinationFileNameInformation = FltQueryInformationFile(
                                           *((PFLT_INSTANCE *)Context + 4),
                                           *(PFILE_OBJECT *)(v100 + 32),
                                           &FileInformation,
                                           8u,
                                           FileAttributeTagInformation,
                                           0);
        HsmDbgBreakOnStatus(DestinationFileNameInformation);
        if ( DestinationFileNameInformation < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqiqd(
              WPP_GLOBAL_Control->AttachedDevice,
              51,
              WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
              a4,
              Context,
              v24,
              v74,
              DestinationFileNameInformation);
          }
          goto LABEL_75;
        }
        v25 = FileInformation & 0x10;
        Contexta[1] = v101;
        if ( v101 )
          FltReferenceContext(v101);
        Contexta[0] = Context;
        FltReferenceContext(Context);
        v97[0] = v88;
        v88 = 0;
        *(_QWORD *)&v98 = v86;
        LODWORD(v99) = FileInformation;
        v97[1] = a4;
        *((_QWORD *)&v98 + 1) = v79;
        BYTE4(v99) = v25 != 0;
        if ( !(unsigned __int8)HsmpIsPlaceholder(StreamContext, v79) || v75 > 1 || (BYTE5(v99) = 1, !v83) )
          BYTE5(v99) = 0;
        if ( (unsigned __int8)HsmpIsPlaceholder(v27, v26) && v86 )
        {
          v40 = v25 != 0 ? 48 : 32;
          if ( v28 )
            v40 |= 0x40u;
          v41 = v72;
          v75 = v40;
          v42 = v72 + 26;
          Pool2 = (_QWORD *)ExAllocatePool2(258, v42, 1666085704);
          P = Pool2;
          v44 = Pool2;
          if ( !Pool2 )
          {
            DestinationFileNameInformation = -1073741670;
            HsmDbgBreakOnStatus(-1073741670);
            v45 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_75;
            }
            v46 = 52;
            AllocationSizea = -1073741670;
            goto LABEL_142;
          }
          *Pool2 = 1666085704;
          *((_DWORD *)Pool2 + 2) = 24;
          *((_DWORD *)Pool2 + 3) = 0x10000;
          Pool2[2] = 0;
          if ( v42 < 0x18
            || (v49 = v41 + 2, (unsigned int)(v41 + 2) > 0x10000)
            || (v54 = *((unsigned int *)Pool2 + 2), v49 + ((v54 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v42) )
          {
            v50 = 0;
          }
          else
          {
            v55 = ((_DWORD)v54 + 3) & 0xFFFFFFFC;
            *((_WORD *)Pool2 + 9) = v49;
            v56 = v55 + (unsigned __int16)v49;
            *((_DWORD *)v44 + 5) = v55;
            *((_WORD *)v44 + 8) = 17;
            v50 = (char *)v44 + v55;
            *((_DWORD *)v44 + 2) = v56;
          }
          v51 = v72;
          memmove(v50, *(const void **)&String2.Length, v72);
          *(_WORD *)&v50[v51] = 0;
          memset(&String1, 0, sizeof(String1));
          KeInitializeEvent(&String1, SynchronizationEvent, 0);
          v52 = P;
          v53 = v75;
          a4->QueueContext[0] = &String1;
          HsmpCldNotifyPreOperation(5, a4, v53, v52, HsmiDeleteOnCloseNotificationCallback, a4);
          DestinationFileNameInformation = FltCancellableWaitForSingleObject(&String1, 0, a4);
          HsmDbgBreakOnStatus(DestinationFileNameInformation);
          if ( DestinationFileNameInformation == -1073741749 || DestinationFileNameInformation == -1073741536 )
          {
            FltCancelIo(a4);
            KeWaitForSingleObject(&String1, Executive, 0, 0, 0);
          }
          a4->QueueContext[0] = 0;
          if ( DestinationFileNameInformation < 0 )
          {
            v45 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_75;
            }
            v46 = 53;
            AllocationSizea = DestinationFileNameInformation;
LABEL_142:
            WPP_SF_qqiqd(
              v45->AttachedDevice,
              v46,
              WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
              a4,
              Context,
              FileObject,
              v74,
              AllocationSizea);
            goto LABEL_75;
          }
          Status = (unsigned int)a4->IoStatus.Status;
        }
        else
        {
          Status = 0;
        }
        v30 = HsmiInfoPrepareForPostRename(Contexta, Status, v94);
        goto LABEL_51;
      }
      if ( DestinationFileNameInformation < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_75;
        }
        v18 = 50;
        FileAttributes = DestinationFileNameInformation;
        AllocationSize = StreamContext;
        RetFileNameInformation = v74;
        goto LABEL_129;
      }
      v38 = QuadPart;
LABEL_90:
      v79 = v38;
      goto LABEL_42;
    }
    v71[0] = 0;
    RequestorProcess = (unsigned int)FltGetRequestorProcess(a4);
    DestinationFileNameInformation = HsmpCldCheckSyncProviderAccess(
                                       (_DWORD)Context,
                                       (_DWORD)StreamContext,
                                       (_DWORD)v24,
                                       RequestorProcess,
                                       (__int64)v71);
    HsmDbgBreakOnStatus(DestinationFileNameInformation);
    if ( DestinationFileNameInformation >= 0 )
    {
      if ( v71[0] )
      {
        v38 = v83;
        goto LABEL_90;
      }
      DestinationFileNameInformation = -1073688808;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qiqiid(
        WPP_GLOBAL_Control->AttachedDevice,
        49,
        WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
        a4,
        Context,
        v24,
        v74,
        StreamContext,
        DestinationFileNameInformation);
    }
    goto LABEL_75;
  }
  if ( (PFLT_FILE_NAME_INFORMATION *)v107[0] == v13 )
    goto LABEL_40;
  if ( !(_BYTE)v72 )
  {
    if ( !StreamContext )
      goto LABEL_40;
    if ( v71[0] )
    {
      if ( (v107[7] & 0x10) != 0 )
      {
        DestinationFileNameInformation = -1073741638;
        v47 = -1073741638;
LABEL_150:
        HsmDbgBreakOnStatus(v47);
        goto LABEL_35;
      }
      if ( (v107[7] & 1) == 0 )
        goto LABEL_40;
      v57 = -1073741790;
      DestinationFileNameInformation = -1073741790;
      goto LABEL_164;
    }
    goto LABEL_147;
  }
  if ( !v71[0] )
  {
LABEL_147:
    v47 = -1073741771;
LABEL_149:
    DestinationFileNameInformation = v47;
    goto LABEL_150;
  }
  if ( (v107[7] & 0x10) != 0 && (HIDWORD(v107[7]) & 0xFFFF0FFF) == 0x9000001A && (v107[7] & 0x440000) != 0 )
  {
    v47 = -1073741790;
    goto LABEL_149;
  }
  if ( !StreamContext )
    goto LABEL_40;
  if ( (v107[7] & 0x10) == 0 || HIDWORD(v107[7]) == -1610612724 || (v58 = 1, HIDWORD(v107[7]) == -1610612733) )
    v58 = 0;
  v59 = StreamContext[3].HighPart & 2;
  if ( (v59 != 0) != v58 )
  {
    DestinationFileNameInformation = v59 != 0 ? -1073741565 : -1073741638;
    v57 = DestinationFileNameInformation;
LABEL_164:
    HsmDbgBreakOnStatus(v57);
    goto LABEL_39;
  }
  if ( (v107[7] & 0x10) == 0 || HIDWORD(v107[7]) == -1610612724 || HIDWORD(v107[7]) == -1610612733 )
    goto LABEL_40;
  v60 = a4->Iopb;
  LengthReturned = 0;
  DestinationFileNameInformation = FltCreateFileEx2(
                                     Filter,
                                     v60->TargetInstance,
                                     &FileHandle,
                                     &v80,
                                     1u,
                                     &ObjectAttributes,
                                     &IoStatusBlock,
                                     0,
                                     0,
                                     7u,
                                     1u,
                                     1u,
                                     0,
                                     0,
                                     0x800u,
                                     &DriverContext);
  HsmDbgBreakOnStatus(DestinationFileNameInformation);
  if ( DestinationFileNameInformation >= 0 )
  {
    v95 = (PVOID)ExAllocatePool2(256, 4096, 1649701704);
    v61 = (char *)v95;
    if ( !v95 )
    {
      DestinationFileNameInformation = -1073741670;
      HsmDbgBreakOnStatus(-1073741670);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_75;
      }
      v18 = 42;
      FileAttributes = -1073741670;
      goto LABEL_146;
    }
    v62 = FltQueryDirectoryFile(Instance, v80, v95, 0x1000u, FileDirectoryInformation, 0, 0, 0, &LengthReturned);
    HsmDbgBreakOnStatus(v62);
    DestinationFileNameInformation = 0;
    if ( v62 != -2147483643 )
      DestinationFileNameInformation = v62;
    if ( DestinationFileNameInformation < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_75;
      }
      v18 = 43;
LABEL_145:
      FileAttributes = DestinationFileNameInformation;
LABEL_146:
      AllocationSize = StreamContext;
      RetFileNameInformation = v74;
      NameOptions = FileObject;
      goto LABEL_130;
    }
    v63 = 0;
    v64 = 0;
    while ( (unsigned int)v63 < 0x1000 )
    {
      LODWORD(v63) = *(_DWORD *)&v61[v63];
      ++v64;
      if ( !(_DWORD)v63 || v64 > 2 )
      {
        if ( v64 > 2 )
        {
          DestinationFileNameInformation = -1073741790;
          HsmDbgBreakOnStatus(-1073741790);
        }
        break;
      }
    }
    FltClose(FileHandle);
    FileHandle = 0;
    ObfDereferenceObject(v80);
    v24 = FileObject;
    v80 = 0;
LABEL_39:
    if ( DestinationFileNameInformation < 0 )
      goto LABEL_35;
    goto LABEL_40;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    goto LABEL_75;
  }
  v18 = 41;
LABEL_128:
  FileAttributes = DestinationFileNameInformation;
  AllocationSize = StreamContext;
  RetFileNameInformation = v74;
LABEL_129:
  NameOptions = v24;
LABEL_130:
  AttachedDevice = v17->AttachedDevice;
LABEL_95:
  WPP_SF_qiqiid(
    AttachedDevice,
    v18,
    WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
    a4,
    Context,
    NameOptions,
    RetFileNameInformation,
    AllocationSize,
    FileAttributes);
LABEL_75:
  a4->IoStatus.Status = DestinationFileNameInformation;
  a4->IoStatus.Information = 0;
LABEL_76:
  v30 = 4;
LABEL_51:
  if ( v102[1] )
    ExFreePoolWithTag(v102[1], 0x73557348u);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v80 )
    ObfDereferenceObject(v80);
  if ( v95 )
    ExFreePoolWithTag(v95, 0x62547348u);
  if ( P )
    ExFreePoolWithTag(P, 0x634E7348u);
  if ( v73 )
    FltReleaseContext(StreamContext);
  if ( Contexta[0] )
    FltReleaseContext(Contexta[0]);
  if ( Contexta[1] )
    FltReleaseContext(Contexta[1]);
  if ( v97[0] )
    HsmpReleaseFileNameLock(v97[0]);
  if ( v88 )
    HsmpReleaseFileNameLock(v88);
  return v30;
}

```

## disassembly

```asm
0x140053800  push    rbp
0x140053802  push    rbx
0x140053803  push    rsi
0x140053804  push    rdi
0x140053805  push    r12
0x140053807  push    r13
0x140053809  push    r14
0x14005380b  push    r15
0x14005380d  lea     rbp, [rsp-178h]
0x140053815  sub     rsp, 278h
0x14005381c  mov     rax, cs:__security_cookie
0x140053823  xor     rax, rsp
0x140053826  mov     [rbp+1B0h+var_50], rax
0x14005382d  mov     rax, [rbp+1B0h+arg_28]
0x140053834  mov     r12, rcx
0x140053837  mov     rcx, [rbp+1B0h+arg_20]
0x14005383e  mov     r15, r9
0x140053841  mov     [rbp+1B0h+var_170], rax
0x140053845  mov     r13, rdx
0x140053848  mov     [rbp+1B0h+var_120], r8
0x14005384f  xor     r8d, r8d
0x140053852  mov     [rbp+1B0h+var_128], rcx
0x140053859  mov     rax, [rcx+18h]
0x14005385d  mov     rdi, [rcx+20h]
0x140053861  mov     [rbp+1B0h+Instance], rax
0x140053865  mov     rax, [r9+10h]
0x140053869  mov     [rbp+1B0h+FileObject], rdi
0x14005386d  mov     ecx, [rax+20h]
0x140053870  mov     rbx, [rax+38h]
0x140053874  mov     [rbp+1B0h+FileNameInformation], r8
0x140053878  test    rdx, rdx
0x14005387b  jnz     loc_140054152
0x140053881  mov     r14, r8
0x140053884  mov     [rbp+1B0h+FileInformation], r8
0x140053888  mov     rdx, r8; Val
0x14005388b  mov     rax, [rax+28h]
0x14005388f  xorps   xmm0, xmm0
0x140053892  mov     [rbp+1B0h+var_1F8], rax
0x140053896  xorps   xmm1, xmm1
0x140053899  mov     [rbp+1B0h+var_228], r14
0x14005389d  mov     esi, 1
0x1400538a2  mov     [rbp+1B0h+var_1D0], r8
0x1400538a6  mov     [rbp+1B0h+var_1E8], rdx
0x1400538aa  mov     [rbp+1B0h+var_178], rdx
0x1400538ae  mov     [rbp+1B0h+var_208], r8
0x1400538b2  mov     [rbp+1B0h+var_220], r8d
0x1400538b6  mov     [rbp+1B0h+var_21C], r8d
0x1400538ba  mov     [rbp+1B0h+P], r8
0x1400538be  mov     [rbp+1B0h+var_22C], r8b
0x1400538c2  movups  [rbp+1B0h+var_188], xmm0
0x1400538c6  movups  xmmword ptr [rbp+1B0h+var_118], xmm1
0x1400538cd  cmp     ecx, 0Ah
0x1400538d0  jz      loc_140053A45
0x1400538d6  cmp     ecx, 41h ; 'A'
0x1400538d9  jz      loc_140053A38
0x1400538df  mov     [rbp+1B0h+var_230], r8b
0x1400538e3  cmp     ecx, 41h ; 'A'
0x1400538e6  jz      loc_140053A25
0x1400538ec  mov     byte ptr [rbp+1B0h+var_22E], r8b
0x1400538f0  xor     eax, eax
0x1400538f2  lea     rcx, [rbp+1B0h+var_A0]; void *
0x1400538f9  movups  xmmword ptr [rbp+1B0h+ObjectAttributes.ObjectName], xmm0
0x140053900  movups  xmmword ptr [rbp+1B0h+ObjectAttributes.Length], xmm0
0x140053907  lea     r8d, [rax+48h]; Size
0x14005390b  movups  xmmword ptr [rbp+1B0h+ObjectAttributes+1Ch], xmm0
0x140053912  movups  xmmword ptr [rbp+1B0h+IoStatusBlock], xmm0
0x140053919  call    memset
0x14005391e  xor     eax, eax
0x140053920  xorps   xmm0, xmm0
0x140053923  mov     r8, r15
0x140053926  mov     [rbp+1B0h+FileHandle], rax
0x14005392a  mov     rdx, r13
0x14005392d  mov     [rbp+1B0h+var_200], rax
0x140053931  mov     rcx, r12; Context
0x140053934  mov     [rbp+1B0h+var_168], rax
0x140053938  movups  xmmword ptr [rbp+1B0h+Context], xmm0
0x14005393c  mov     [rbp+1B0h+var_130], rax
0x140053943  movups  xmmword ptr [rbp+1B0h+var_150], xmm0
0x140053947  movups  [rbp+1B0h+var_140], xmm0
0x14005394b  call    HsmpAcquireFileNameLock
0x140053950  mov     [rbp+1B0h+var_1C0], rax
0x140053954  test    rax, rax
0x140053957  jz      loc_140053E11
0x14005395d  test    r13, r13
0x140053960  jz      loc_140053A57
0x140053966  mov     rdi, [rbp+1B0h+Instance]
0x14005396a  cmp     [rbp+1B0h+var_1F8], 0
0x14005396f  jnz     loc_140053A78
0x140053975  cmp     dword ptr [rbx+10h], 2
0x140053979  jb      loc_140053A78
0x14005397f  lea     rax, [rbx+14h]
0x140053983  cmp     word ptr [rax], 3Ah ; ':'
0x140053987  jnz     loc_140053A78
0x14005398d  mov     edx, 52h ; 'R'
0x140053992  mov     qword ptr [rbp+1B0h+String2.Length], 540052h
0x14005399a  xorps   xmm0, xmm0
0x14005399d  lea     rcx, a3d0ce612Fdee43_1
0x1400539a4  movups  xmmword ptr [rbp+1B0h+String1.Length], xmm0
0x1400539a8  mov     [rbp+1B0h+String1.Buffer], rax
0x1400539ac  mov     r8b, sil; CaseInSensitive
0x1400539af  movzx   eax, word ptr [rbx+10h]
0x1400539b3  cmp     ax, dx
0x1400539b6  mov     [rbp+1B0h+String1.MaximumLength], ax
0x1400539ba  mov     [rbp+1B0h+String2.Buffer], rcx
0x1400539be  lea     rcx, [rbp+1B0h+String1]; String1
0x1400539c2  cmova   ax, dx
0x1400539c6  lea     rdx, [rbp+1B0h+String2]; String2
0x1400539ca  mov     [rbp+1B0h+String1.Length], ax
0x1400539ce  call    cs:__imp_RtlEqualUnicodeString
0x1400539d5  nop     dword ptr [rax+rax+00h]
0x1400539da  test    al, al
0x1400539dc  jz      loc_140053A78
0x1400539e2  mov     edi, 0C000CF18h
0x1400539e7  mov     ecx, edi
0x1400539e9  call    HsmDbgBreakOnStatus
0x1400539ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400539f5  lea     r14, WPP_GLOBAL_Control
0x1400539fc  cmp     rcx, r14
0x1400539ff  jz      loc_140053E05
0x140053a05  mov     eax, [rcx+2Ch]
0x140053a08  test    sil, al
0x140053a0b  jz      loc_140053E05
0x140053a11  cmp     byte ptr [rcx+29h], 2
0x140053a15  jb      loc_140053E05
0x140053a1b  mov     edx, 27h ; '''
0x140053a20  jmp     loc_140054378
0x140053a25  mov     eax, [rbx]
0x140053a27  mov     byte ptr [rbp+1B0h+var_22E], sil
0x140053a2b  test    al, 2
0x140053a2d  jnz     loc_1400538F0
0x140053a33  jmp     loc_1400538EC
0x140053a38  mov     eax, [rbx]
0x140053a3a  test    sil, al
0x140053a3d  jz      loc_1400538DF
0x140053a43  jmp     short loc_140053A4E
0x140053a45  cmp     [rbx], r8b
0x140053a48  jz      loc_1400538D6
0x140053a4e  mov     [rbp+1B0h+var_230], sil
0x140053a52  jmp     loc_1400538E3
0x140053a57  mov     r8, rdi; FileObject
0x140053a5a  mov     rcx, r15; CallbackData
0x140053a5d  mov     rdi, [rbp+1B0h+Instance]
0x140053a61  mov     rdx, rdi; Instance
0x140053a64  call    HsmpGetStreamContext
0x140053a69  mov     r13, rax
0x140053a6c  test    rax, rax
0x140053a6f  jnz     loc_140054082
0x140053a75  mov     [rbp+1B0h+var_22C], al
0x140053a78  mov     r8, [rbx+8]; RootDirectory
0x140053a7c  lea     rax, [rbp+1B0h+FileNameInformation]
0x140053a80  mov     [rsp+2B0h+RetFileNameInformation], rax; RetFileNameInformation
0x140053a85  lea     r9, [rbx+14h]; FileName
0x140053a89  mov     eax, [rbx+10h]
0x140053a8c  mov     rcx, rdi; Instance
0x140053a8f  mov     rbx, [rbp+1B0h+FileObject]
0x140053a93  mov     rdx, rbx; FileObject
0x140053a96  mov     [rsp+2B0h+NameOptions], 101h; NameOptions
0x140053a9e  mov     [rsp+2B0h+FileNameLength], eax; FileNameLength
0x140053aa2  call    cs:__imp_FltGetDestinationFileNameInformation
0x140053aa9  nop     dword ptr [rax+rax+00h]
0x140053aae  mov     ecx, eax
0x140053ab0  mov     edi, eax
0x140053ab2  call    HsmDbgBreakOnStatus
0x140053ab7  test    edi, edi
0x140053ab9  js      loc_140053F59
0x140053abf  cmp     byte ptr [rbp+1B0h+var_22E], 0
0x140053ac3  jnz     short loc_140053ACE
0x140053ac5  test    r13, r13
0x140053ac8  jz      loc_140053BFC
0x140053ace  xorps   xmm0, xmm0
0x140053ad1  mov     [rbp+1B0h+var_B8], rsi
0x140053ad8  mov     ecx, 28h ; '('
0x140053add  movups  xmmword ptr [rbp+1B0h+var_D8.Size], xmm0
0x140053ae4  mov     [rbp+1B0h+var_D8.Size], cx
0x140053aeb  mov     rcx, rbx; FileObject
0x140053aee  movups  xmmword ptr [rbp+1B0h+var_D8.DeviceObjectHint], xmm0
0x140053af5  call    cs:__imp_IoGetTransactionParameterBlock
0x140053afc  nop     dword ptr [rax+rax+00h]
0x140053b01  mov     rdx, [rbp+1B0h+Instance]
0x140053b05  lea     r9, [rbp+1B0h+IoStatusBlock]
0x140053b0c  mov     rcx, cs:Filter
0x140053b13  lea     r8, [rbp+1B0h+ObjectAttributes]
0x140053b1a  mov     [rbp+1B0h+var_D8.TxnParameters], rax
0x140053b21  xorps   xmm0, xmm0
0x140053b24  mov     rax, [rbp+1B0h+FileNameInformation]
0x140053b28  add     rax, 8
0x140053b2c  mov     [rbp+1B0h+ObjectAttributes.Length], 30h ; '0'
0x140053b36  mov     [rbp+1B0h+ObjectAttributes.ObjectName], rax
0x140053b3d  lea     rax, [rbp+1B0h+var_D8]
0x140053b44  mov     [rsp+2B0h+AllocationSize], rax
0x140053b49  lea     rax, [rbp+1B0h+var_A0]
0x140053b50  mov     dword ptr [rsp+2B0h+RetFileNameInformation], 44h ; 'D'
0x140053b58  mov     [rsp+2B0h+NameOptions], 48h ; 'H'
0x140053b60  mov     qword ptr [rsp+2B0h+FileNameLength], rax
0x140053b65  mov     [rbp+1B0h+ObjectAttributes.RootDirectory], 0
0x140053b70  mov     [rbp+1B0h+ObjectAttributes.Attributes], 240h
0x140053b7a  movdqu  xmmword ptr [rbp+1B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140053b82  call    cs:__imp_FltQueryInformationByName
0x140053b89  nop     dword ptr [rax+rax+00h]
0x140053b8e  mov     ecx, eax
0x140053b90  mov     edi, eax
0x140053b92  call    HsmDbgBreakOnStatus
0x140053b97  test    edi, edi
0x140053b99  jns     loc_14005408B
0x140053b9f  cmp     edi, 0C0000034h
0x140053ba5  jz      short loc_140053BFC
0x140053ba7  cmp     edi, 0C000003Ah
0x140053bad  jz      short loc_140053BFC
0x140053baf  mov     rcx, cs:WPP_GLOBAL_Control
0x140053bb6  lea     r14, WPP_GLOBAL_Control
0x140053bbd  cmp     rcx, r14
0x140053bc0  jz      loc_140053CFE
0x140053bc6  mov     eax, [rcx+2Ch]
0x140053bc9  test    sil, al
0x140053bcc  jz      loc_140053CFE
0x140053bd2  cmp     byte ptr [rcx+29h], 2
0x140053bd6  jb      loc_140053CFE
0x140053bdc  mov     r8, [rbp+1B0h+var_228]
0x140053be0  mov     edx, 2Ch ; ','
0x140053be5  mov     [rsp+2B0h+FileAttributes], edi
0x140053be9  mov     [rsp+2B0h+AllocationSize], r13
0x140053bee  mov     [rsp+2B0h+RetFileNameInformation], r8
0x140053bf3  jmp     loc_14005479A
0x140053bf8  test    edi, edi
0x140053bfa  js      short loc_140053BAF
0x140053bfc  lea     r14, WPP_GLOBAL_Control
0x140053c03  test    r13, r13
0x140053c06  jnz     loc_140053E1B
0x140053c0c  mov     rax, qword ptr [rbp+1B0h+var_188+8]
0x140053c10  mov     qword ptr [rbp+1B0h+String2.Length], rax
0x140053c14  movzx   eax, word ptr [rbp+1B0h+var_188]
0x140053c18  mov     [rbp+1B0h+var_22E], ax
0x140053c1c  mov     rdx, [rbp+1B0h+var_128]
0x140053c23  lea     r8, [rbp+1B0h+FileInformation]; FileInformation
0x140053c27  mov     rcx, [r12+20h]; Instance
0x140053c2c  mov     r9d, 8; Length
0x140053c32  mov     qword ptr [rsp+2B0h+NameOptions], 0; LengthReturned
0x140053c3b  mov     [rsp+2B0h+FileNameLength], 23h ; '#'; FileInformationClass
0x140053c43  mov     rdx, [rdx+20h]; FileObject
0x140053c47  call    cs:__imp_FltQueryInformationFile
0x140053c4e  nop     dword ptr [rax+rax+00h]
0x140053c53  mov     ecx, eax
0x140053c55  mov     edi, eax
0x140053c57  call    HsmDbgBreakOnStatus
0x140053c5c  test    edi, edi
0x140053c5e  js      loc_140053DF5
0x140053c64  mov     rax, [rbp+1B0h+var_120]
0x140053c6b  mov     ebx, dword ptr [rbp+1B0h+FileInformation]
0x140053c6e  and     ebx, 10h
0x140053c71  mov     [rbp+1B0h+Context+8], rax
0x140053c75  setnz   dil
0x140053c79  test    rax, rax
0x140053c7c  jnz     loc_140053DE1
0x140053c82  mov     rcx, r12; Context
0x140053c85  mov     [rbp+1B0h+Context], r12
0x140053c89  call    cs:__imp_FltReferenceContext
0x140053c90  nop     dword ptr [rax+rax+00h]
0x140053c95  mov     rax, [rbp+1B0h+var_1C0]
0x140053c99  mov     rcx, r13
0x140053c9c  mov     rdx, [rbp+1B0h+var_208]
0x140053ca0  mov     [rbp+1B0h+var_150], rax
0x140053ca4  xor     eax, eax
0x140053ca6  mov     [rbp+1B0h+var_1C0], rax
0x140053caa  mov     rax, [rbp+1B0h+var_1D0]
0x140053cae  mov     qword ptr [rbp+1B0h+var_140], rax
0x140053cb2  mov     eax, dword ptr [rbp+1B0h+FileInformation]
0x140053cb5  mov     dword ptr [rbp+1B0h+var_130], eax
0x140053cbb  mov     [rbp+1B0h+var_150+8], r15
0x140053cbf  mov     qword ptr [rbp+1B0h+var_140+8], rdx
0x140053cc3  mov     byte ptr [rbp+1B0h+var_130+4], dil
0x140053cca  call    HsmpIsPlaceholder
0x140053ccf  test    al, al
0x140053cd1  jnz     loc_140054051
0x140053cd7  mov     byte ptr [rbp+1B0h+var_130+5], 0
0x140053cde  call    HsmpIsPlaceholder
0x140053ce3  test    al, al
0x140053ce5  jnz     loc_140053FBF
0x140053ceb  xor     edx, edx
0x140053ced  mov     r8, [rbp+1B0h+var_170]
0x140053cf1  lea     rcx, [rbp+1B0h+Context]
0x140053cf5  call    HsmiInfoPrepareForPostRename
0x140053cfa  mov     esi, eax
0x140053cfc  jmp     short loc_140053D06
0x140053cfe  test    edi, edi
0x140053d00  js      loc_140053E05
0x140053d06  mov     rcx, [rbp+1B0h+var_118+8]; P
0x140053d0d  test    rcx, rcx
0x140053d10  jnz     loc_14005484F
0x140053d16  mov     rcx, [rbp+1B0h+FileNameInformation]; FileNameInformation
0x140053d1a  test    rcx, rcx
0x140053d1d  jz      short loc_140053D2B
0x140053d1f  call    cs:__imp_FltReleaseFileNameInformation
0x140053d26  nop     dword ptr [rax+rax+00h]
0x140053d2b  mov     rcx, [rbp+1B0h+FileHandle]; FileHandle
0x140053d2f  test    rcx, rcx
0x140053d32  jnz     loc_140054865
0x140053d38  mov     rcx, [rbp+1B0h+var_200]; Object
0x140053d3c  test    rcx, rcx
0x140053d3f  jnz     loc_140054876
0x140053d45  mov     rax, [rbp+1B0h+var_168]
  ... truncated ...
```
