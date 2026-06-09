# HsmFltPreSetRenameInformation

- ea: `0x1400536e0`
- end: `0x1400547a1`
- name: `HsmFltPreSetRenameInformation`
- size: `4289`
- prototype: `__int64 __usercall@<rax>(PFLT_CONTEXT Context@<rcx>, PFLT_CONTEXT@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400525b0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x14000ac28`
- `0x14000d388`
- `0x14001e140`
- `0x14001e280`
- `0x14001e580`
- `0x14001eaa0`
- `0x140050ca0`
- `0x1400520d0`
- `0x1400536e0`
- `0x1400547b0`
- `0x1400547cc`
- `0x140054a04`
- `0x140054a9c`
- `0x140055250`
- `0x140057a00`
- `0x140058f70`
- `0x14005f550`

## import_xrefs

- `ntoskrnl!IoGetTransactionParameterBlock` at `0x1400539d5`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x1400539d5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140054195`
- `ntoskrnl!KeWaitForSingleObject` at `0x140054195`
- `ntoskrnl!KeInitializeEvent` at `0x140054109`
- `ntoskrnl!KeInitializeEvent` at `0x140054109`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400538ae`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400538ae`
- `ntoskrnl!ObfDereferenceObject` at `0x14005454a`
- `ntoskrnl!ObfDereferenceObject` at `0x140054756`
- `ntoskrnl!ObfDereferenceObject` at `0x14005454a`
- `ntoskrnl!ObfDereferenceObject` at `0x140054756`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053cb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054734`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005476f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053cb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054734`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005476f`
- `ntoskrnl!ExAllocatePool2` at `0x140053ed3`
- `ntoskrnl!ExAllocatePool2` at `0x14005442c`
- `ntoskrnl!ExAllocatePool2` at `0x140053ed3`
- `ntoskrnl!ExAllocatePool2` at `0x14005442c`
- `FLTMGR!FltQueryInformationByName` at `0x140053a62`
- `FLTMGR!FltQueryInformationByName` at `0x140053a62`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x140053982`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x140053982`
- `FLTMGR!FltClose` at `0x140054533`
- `FLTMGR!FltClose` at `0x140054745`
- `FLTMGR!FltClose` at `0x140054533`
- `FLTMGR!FltClose` at `0x140054745`
- `FLTMGR!FltQueryInformationFile` at `0x140053b27`
- `FLTMGR!FltQueryInformationFile` at `0x140053b27`
- `FLTMGR!FltReferenceContext` at `0x140053b69`
- `FLTMGR!FltReferenceContext` at `0x140053cc4`
- `FLTMGR!FltReferenceContext` at `0x140053b69`
- `FLTMGR!FltReferenceContext` at `0x140053cc4`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14005414c`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14005414c`
- `FLTMGR!FltQueryDirectoryFile` at `0x1400544ae`
- `FLTMGR!FltQueryDirectoryFile` at `0x1400544ae`
- `FLTMGR!FltCreateFileEx2` at `0x1400543ca`
- `FLTMGR!FltCreateFileEx2` at `0x1400543ca`
- `FLTMGR!FltCancelIo` at `0x140054174`
- `FLTMGR!FltCancelIo` at `0x140054174`
- `FLTMGR!FltGetRequestorProcess` at `0x1400545ff`
- `FLTMGR!FltGetRequestorProcess` at `0x1400545ff`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140053bff`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140053bff`
- `FLTMGR!FltReleaseContext` at `0x140053c4e`
- `FLTMGR!FltReleaseContext` at `0x140053f51`
- `FLTMGR!FltReleaseContext` at `0x140054783`
- `FLTMGR!FltReleaseContext` at `0x140053c4e`
- `FLTMGR!FltReleaseContext` at `0x140053f51`
- `FLTMGR!FltReleaseContext` at `0x140054783`

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
  __int64 DestinationFileNameInformation; // rdi
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  struct _FILE_OBJECT *v20; // r8
  void *v21; // r8
  WCHAR *v22; // r9
  ULONG FileNameLength; // eax
  struct _FILE_OBJECT *v24; // rbx
  int v25; // ebx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 Status; // rdx
  unsigned int v29; // esi
  __int64 v31; // rdi
  size_t Length; // r8
  char *v33; // rax
  int v34; // edi
  __int64 v35; // rdx
  PFLT_FILE_NAME_INFORMATION *v36; // rax
  __int64 v37; // rax
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  int v39; // eax
  int v40; // edi
  unsigned int v41; // ebx
  _QWORD *Pool2; // rax
  _QWORD *v43; // r9
  PDEVICE_OBJECT v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rcx
  union _LARGE_INTEGER v47; // r14
  unsigned int v48; // edx
  char *v49; // rdi
  __int64 v50; // rbx
  PVOID v51; // r9
  int v52; // r8d
  __int64 v53; // r8
  __int64 v54; // rdi
  int v55; // eax
  __int64 v56; // rcx
  int v57; // r9d
  int v58; // edx
  PFLT_IO_PARAMETER_BLOCK v59; // rdx
  char *v60; // r14
  __int64 v61; // rbx
  __int64 v62; // rax
  unsigned int v63; // ecx
  unsigned int RequestorProcess; // eax
  PFILE_OBJECT NameOptions; // [rsp+28h] [rbp-D8h]
  PFLT_FILE_NAME_INFORMATION *RetFileNameInformation; // [rsp+30h] [rbp-D0h]
  PLARGE_INTEGER AllocationSize; // [rsp+38h] [rbp-C8h]
  int AllocationSizea; // [rsp+38h] [rbp-C8h]
  int FileAttributes; // [rsp+40h] [rbp-C0h]
  bool v70[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v71; // [rsp+82h] [rbp-7Eh]
  char v72; // [rsp+84h] [rbp-7Ch]
  PFLT_FILE_NAME_INFORMATION *v73; // [rsp+88h] [rbp-78h]
  unsigned int v74; // [rsp+90h] [rbp-70h] BYREF
  unsigned int SyncRootFileIdByFileObject; // [rsp+94h] [rbp-6Ch] BYREF
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp-68h]
  PFLT_INSTANCE Instance; // [rsp+A0h] [rbp-60h]
  __int64 v78; // [rsp+A8h] [rbp-58h]
  PFILE_OBJECT v79; // [rsp+B0h] [rbp-50h] BYREF
  __int64 QuadPart; // [rsp+B8h] [rbp-48h] BYREF
  void *FileHandle; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v82; // [rsp+C8h] [rbp-38h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+D0h] [rbp-30h] BYREF
  __int64 FileInformation; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v85; // [rsp+E0h] [rbp-20h] BYREF
  PVOID P; // [rsp+E8h] [rbp-18h]
  PFLT_CONTEXT v87; // [rsp+F0h] [rbp-10h]
  ULONG LengthReturned; // [rsp+F8h] [rbp-8h] BYREF
  UNICODE_STRING String2; // [rsp+100h] [rbp+0h] BYREF
  struct _KEVENT String1; // [rsp+110h] [rbp+10h] BYREF
  __int128 v91; // [rsp+128h] [rbp+28h] BYREF
  PFLT_FILE_NAME_INFORMATION *v92; // [rsp+138h] [rbp+38h] BYREF
  __int64 v93; // [rsp+140h] [rbp+40h]
  PVOID v94; // [rsp+148h] [rbp+48h]
  PFLT_CONTEXT Contexta[2]; // [rsp+150h] [rbp+50h] BYREF
  PFLT_CONTEXT v96[2]; // [rsp+160h] [rbp+60h]
  __int128 v97; // [rsp+170h] [rbp+70h]
  __int64 v98; // [rsp+180h] [rbp+80h]
  __int64 v99; // [rsp+188h] [rbp+88h]
  PFLT_CONTEXT v100; // [rsp+190h] [rbp+90h]
  PVOID v101[2]; // [rsp+198h] [rbp+98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1A8h] [rbp+A8h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v104; // [rsp+1F8h] [rbp+F8h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+200h] [rbp+100h] BYREF
  _QWORD v106[10]; // [rsp+210h] [rbp+110h] BYREF

  v93 = a6;
  StreamContext = a2;
  v100 = a3;
  v99 = a5;
  v9 = *(struct _FILE_OBJECT **)(a5 + 32);
  Instance = *(PFLT_INSTANCE *)(a5 + 24);
  Iopb = a4->Iopb;
  FileObject = v9;
  Options = Iopb->Parameters.Create.Options;
  EaBuffer = (char *)Iopb->Parameters.Create.EaBuffer;
  FileNameInformation = 0;
  if ( a2 && (v47 = a2[2], v47.QuadPart) )
    v13 = *(PFLT_FILE_NAME_INFORMATION **)(v47.QuadPart + 32);
  else
    v13 = 0;
  FileInformation = 0;
  QuadPart = Iopb->Parameters.Read.ByteOffset.QuadPart;
  v73 = v13;
  v85 = 0;
  v82 = 0;
  v92 = 0;
  v78 = 0;
  v74 = 0;
  SyncRootFileIdByFileObject = 0;
  P = 0;
  v72 = 0;
  v91 = 0;
  *(_OWORD *)v101 = 0;
  v70[0] = Options == 10 && *EaBuffer || Options == 65 && (*(_DWORD *)EaBuffer & 1) != 0;
  if ( Options != 65 || (v19 = *(_DWORD *)EaBuffer, LOBYTE(v71) = 1, (v19 & 2) == 0) )
    LOBYTE(v71) = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(v106, 0, 0x48u);
  FileHandle = 0;
  v79 = 0;
  v94 = 0;
  *(_OWORD *)Contexta = 0;
  v98 = 0;
  *(_OWORD *)v96 = 0;
  v97 = 0;
  v87 = (PFLT_CONTEXT)HsmpAcquireFileNameLock(Context);
  if ( !v87 )
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
      v72 = 0;
      goto LABEL_29;
    }
    v72 = 1;
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
      LODWORD(DestinationFileNameInformation) = -1073688808;
      HsmDbgBreakOnStatus(3221278488LL);
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
  DestinationFileNameInformation = (unsigned int)FltGetDestinationFileNameInformation(
                                                   v14,
                                                   FileObject,
                                                   v21,
                                                   v22,
                                                   FileNameLength,
                                                   0x101u,
                                                   &FileNameInformation);
  HsmDbgBreakOnStatus(DestinationFileNameInformation);
  if ( (int)DestinationFileNameInformation < 0 )
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
    RetFileNameInformation = v73;
    NameOptions = FileObject;
    goto LABEL_95;
  }
  if ( !(_BYTE)v71 && !StreamContext )
    goto LABEL_40;
  v104 = 1;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  DriverContext.TxnParameters = IoGetTransactionParameterBlock(FileObject);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &FileNameInformation->Name;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  DestinationFileNameInformation = (unsigned int)FltQueryInformationByName(
                                                   Filter,
                                                   Instance,
                                                   &ObjectAttributes,
                                                   &IoStatusBlock,
                                                   v106,
                                                   72,
                                                   68,
                                                   &DriverContext);
  HsmDbgBreakOnStatus(DestinationFileNameInformation);
  if ( (int)DestinationFileNameInformation < 0 )
  {
    if ( (_DWORD)DestinationFileNameInformation != -1073741772 && (_DWORD)DestinationFileNameInformation != -1073741766 )
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
          v73,
          StreamContext,
          DestinationFileNameInformation);
      }
      goto LABEL_75;
    }
LABEL_40:
    if ( !StreamContext )
    {
      *(_QWORD *)&String2.Length = *((_QWORD *)&v91 + 1);
      v71 = v91;
      goto LABEL_42;
    }
    v31 = QuadPart;
    Length = FileNameInformation->Volume.Length;
    v33 = (char *)FileNameInformation->Name.Buffer + Length;
    v71 = FileNameInformation->Name.Length - Length;
    LOWORD(v91) = v71;
    *(_QWORD *)&String2.Length = v33;
    *((_QWORD *)&v91 + 1) = v33;
    WORD1(v91) = v71;
    if ( QuadPart
      && (Context[32] != Length + 2 || memcmp(*((const void **)Context + 9), FileNameInformation->Volume.Buffer, Length)) )
    {
      LODWORD(DestinationFileNameInformation) = -1073741612;
      HsmDbgBreakOnStatus(3221225684LL);
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
    QuadPart = v78 & -(__int64)(v31 != 0);
    SyncRootFileIdByFileObject = HsmiCldGetSyncRootFileIdByFileObject(
                                   Context,
                                   v24,
                                   &v85,
                                   &v74,
                                   &SyncRootFileIdByFileObject);
    v34 = SyncRootFileIdByFileObject;
    HsmDbgBreakOnStatus(SyncRootFileIdByFileObject);
    if ( v34 < 0
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
        v34);
    }
    HsmDbgBreakOnStatus((unsigned int)v34);
    LODWORD(DestinationFileNameInformation) = 0;
    if ( SyncRootFileIdByFileObject != -1073688813 )
      LODWORD(DestinationFileNameInformation) = SyncRootFileIdByFileObject;
    if ( (int)DestinationFileNameInformation < 0 )
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
    DestinationFileNameInformation = (unsigned int)HsmiQueryFullFilePath((__int64)Instance, v35, v24, 0x102u, v101);
    HsmDbgBreakOnStatus(DestinationFileNameInformation);
    if ( (int)DestinationFileNameInformation < 0 )
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
    DestinationFileNameInformation = (unsigned int)HsmiCldGetSyncRootFileIdByPath(Context, v101, &v92);
    HsmDbgBreakOnStatus(DestinationFileNameInformation);
    if ( (_DWORD)DestinationFileNameInformation == -1073688813 )
    {
      v36 = 0;
    }
    else
    {
      if ( (int)DestinationFileNameInformation < 0 )
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
      v36 = v92;
    }
    v82 = (__int64)v36;
    if ( v36 != v73 )
    {
      DestinationFileNameInformation = (unsigned int)HsmiCldGetSyncRootFileIdByPath(Context, &v91, &QuadPart);
      HsmDbgBreakOnStatus(DestinationFileNameInformation);
      if ( (_DWORD)DestinationFileNameInformation == -1073688813 )
      {
        v78 = 0;
LABEL_42:
        DestinationFileNameInformation = (unsigned int)FltQueryInformationFile(
                                                         *((PFLT_INSTANCE *)Context + 4),
                                                         *(PFILE_OBJECT *)(v99 + 32),
                                                         &FileInformation,
                                                         8u,
                                                         FileAttributeTagInformation,
                                                         0);
        HsmDbgBreakOnStatus(DestinationFileNameInformation);
        if ( (int)DestinationFileNameInformation < 0 )
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
              v73,
              DestinationFileNameInformation);
          }
          goto LABEL_75;
        }
        v25 = FileInformation & 0x10;
        Contexta[1] = v100;
        if ( v100 )
          FltReferenceContext(v100);
        Contexta[0] = Context;
        FltReferenceContext(Context);
        v96[0] = v87;
        v87 = 0;
        *(_QWORD *)&v97 = v85;
        LODWORD(v98) = FileInformation;
        v96[1] = a4;
        *((_QWORD *)&v97 + 1) = v78;
        BYTE4(v98) = v25 != 0;
        if ( !(unsigned __int8)HsmpIsPlaceholder(StreamContext) || v74 > 1 || (BYTE5(v98) = 1, !v82) )
          BYTE5(v98) = 0;
        if ( (unsigned __int8)HsmpIsPlaceholder(v26) && v85 )
        {
          v39 = v25 != 0 ? 48 : 32;
          if ( v27 )
            v39 |= 0x40u;
          v40 = v71;
          v74 = v39;
          v41 = v71 + 26;
          Pool2 = (_QWORD *)ExAllocatePool2(258, v41, 1666085704);
          P = Pool2;
          v43 = Pool2;
          if ( !Pool2 )
          {
            LODWORD(DestinationFileNameInformation) = -1073741670;
            HsmDbgBreakOnStatus(3221225626LL);
            v44 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_75;
            }
            v45 = 52;
            AllocationSizea = -1073741670;
            goto LABEL_142;
          }
          *Pool2 = 1666085704;
          *((_DWORD *)Pool2 + 2) = 24;
          *((_DWORD *)Pool2 + 3) = 0x10000;
          Pool2[2] = 0;
          if ( v41 < 0x18
            || (v48 = v40 + 2, (unsigned int)(v40 + 2) > 0x10000)
            || (v53 = *((unsigned int *)Pool2 + 2), v48 + ((v53 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v41) )
          {
            v49 = 0;
          }
          else
          {
            v54 = ((_DWORD)v53 + 3) & 0xFFFFFFFC;
            *((_WORD *)Pool2 + 9) = v48;
            v55 = v54 + (unsigned __int16)v48;
            *((_DWORD *)v43 + 5) = v54;
            *((_WORD *)v43 + 8) = 17;
            v49 = (char *)v43 + v54;
            *((_DWORD *)v43 + 2) = v55;
          }
          v50 = v71;
          memmove(v49, *(const void **)&String2.Length, v71);
          *(_WORD *)&v49[v50] = 0;
          memset(&String1, 0, sizeof(String1));
          KeInitializeEvent(&String1, SynchronizationEvent, 0);
          v51 = P;
          v52 = v74;
          a4->QueueContext[0] = &String1;
          HsmpCldNotifyPreOperation(
            5u,
            a4,
            v52,
            (__int64)v51,
            (void (__fastcall *)(__int64, _QWORD, _QWORD))HsmiDeleteOnCloseNotificationCallback,
            (__int64)a4);
          DestinationFileNameInformation = (unsigned int)FltCancellableWaitForSingleObject(&String1, 0, a4);
          HsmDbgBreakOnStatus(DestinationFileNameInformation);
          if ( (_DWORD)DestinationFileNameInformation == -1073741749
            || (_DWORD)DestinationFileNameInformation == -1073741536 )
          {
            FltCancelIo(a4);
            KeWaitForSingleObject(&String1, Executive, 0, 0, 0);
          }
          a4->QueueContext[0] = 0;
          if ( (int)DestinationFileNameInformation < 0 )
          {
            v44 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_75;
            }
            v45 = 53;
            AllocationSizea = DestinationFileNameInformation;
LABEL_142:
            WPP_SF_qqiqd(
              v44->AttachedDevice,
              v45,
              WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
              a4,
              Context,
              FileObject,
              v73,
              AllocationSizea);
            goto LABEL_75;
          }
          Status = (unsigned int)a4->IoStatus.Status;
        }
        else
        {
          Status = 0;
        }
        v29 = HsmiInfoPrepareForPostRename(Contexta, Status, v93);
        goto LABEL_51;
      }
      if ( (int)DestinationFileNameInformation < 0 )
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
        RetFileNameInformation = v73;
        goto LABEL_129;
      }
      v37 = QuadPart;
LABEL_90:
      v78 = v37;
      goto LABEL_42;
    }
    v70[0] = 0;
    RequestorProcess = (unsigned int)FltGetRequestorProcess(a4);
    DestinationFileNameInformation = (unsigned int)HsmpCldCheckSyncProviderAccess(
                                                     (_DWORD)Context,
                                                     (_DWORD)StreamContext,
                                                     (_DWORD)v24,
                                                     RequestorProcess,
                                                     (__int64)v70);
    HsmDbgBreakOnStatus(DestinationFileNameInformation);
    if ( (int)DestinationFileNameInformation >= 0 )
    {
      if ( v70[0] )
      {
        v37 = v82;
        goto LABEL_90;
      }
      LODWORD(DestinationFileNameInformation) = -1073688808;
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
        v73,
        StreamContext,
        DestinationFileNameInformation);
    }
    goto LABEL_75;
  }
  if ( (PFLT_FILE_NAME_INFORMATION *)v106[0] == v13 )
    goto LABEL_40;
  if ( !(_BYTE)v71 )
  {
    if ( !StreamContext )
      goto LABEL_40;
    if ( v70[0] )
    {
      if ( (v106[7] & 0x10) != 0 )
      {
        LODWORD(DestinationFileNameInformation) = -1073741638;
        v46 = 3221225658LL;
LABEL_150:
        HsmDbgBreakOnStatus(v46);
        goto LABEL_35;
      }
      if ( (v106[7] & 1) == 0 )
        goto LABEL_40;
      v56 = 3221225506LL;
      LODWORD(DestinationFileNameInformation) = -1073741790;
      goto LABEL_164;
    }
    goto LABEL_147;
  }
  if ( !v70[0] )
  {
LABEL_147:
    v46 = 3221225525LL;
LABEL_149:
    LODWORD(DestinationFileNameInformation) = v46;
    goto LABEL_150;
  }
  if ( (v106[7] & 0x10) != 0 && (HIDWORD(v106[7]) & 0xFFFF0FFF) == 0x9000001A && (v106[7] & 0x440000) != 0 )
  {
    v46 = 3221225506LL;
    goto LABEL_149;
  }
  if ( !StreamContext )
    goto LABEL_40;
  if ( (v106[7] & 0x10) == 0 || HIDWORD(v106[7]) == -1610612724 || (v57 = 1, HIDWORD(v106[7]) == -1610612733) )
    v57 = 0;
  v58 = StreamContext[3].HighPart & 2;
  if ( (v58 != 0) != v57 )
  {
    LODWORD(DestinationFileNameInformation) = v58 != 0 ? -1073741565 : -1073741638;
    v56 = (unsigned int)DestinationFileNameInformation;
LABEL_164:
    HsmDbgBreakOnStatus(v56);
    goto LABEL_39;
  }
  if ( (v106[7] & 0x10) == 0 || HIDWORD(v106[7]) == -1610612724 || HIDWORD(v106[7]) == -1610612733 )
    goto LABEL_40;
  v59 = a4->Iopb;
  LengthReturned = 0;
  DestinationFileNameInformation = (unsigned int)FltCreateFileEx2(
                                                   Filter,
                                                   v59->TargetInstance,
                                                   &FileHandle,
                                                   &v79,
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
  if ( (int)DestinationFileNameInformation >= 0 )
  {
    v94 = (PVOID)ExAllocatePool2(256, 4096, 1649701704);
    v60 = (char *)v94;
    if ( !v94 )
    {
      LODWORD(DestinationFileNameInformation) = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
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
    v61 = (unsigned int)FltQueryDirectoryFile(
                          Instance,
                          v79,
                          v94,
                          0x1000u,
                          FileDirectoryInformation,
                          0,
                          0,
                          0,
                          &LengthReturned);
    HsmDbgBreakOnStatus(v61);
    LODWORD(DestinationFileNameInformation) = 0;
    if ( (_DWORD)v61 != -2147483643 )
      LODWORD(DestinationFileNameInformation) = v61;
    if ( (int)DestinationFileNameInformation < 0 )
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
      RetFileNameInformation = v73;
      NameOptions = FileObject;
      goto LABEL_130;
    }
    v62 = 0;
    v63 = 0;
    while ( (unsigned int)v62 < 0x1000 )
    {
      LODWORD(v62) = *(_DWORD *)&v60[v62];
      ++v63;
      if ( !(_DWORD)v62 || v63 > 2 )
      {
        if ( v63 > 2 )
        {
          LODWORD(DestinationFileNameInformation) = -1073741790;
          HsmDbgBreakOnStatus(3221225506LL);
        }
        break;
      }
    }
    FltClose(FileHandle);
    FileHandle = 0;
    ObfDereferenceObject(v79);
    v24 = FileObject;
    v79 = 0;
LABEL_39:
    if ( (int)DestinationFileNameInformation < 0 )
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
  RetFileNameInformation = v73;
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
  v29 = 4;
LABEL_51:
  if ( v101[1] )
    ExFreePoolWithTag(v101[1], 0x73557348u);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v79 )
    ObfDereferenceObject(v79);
  if ( v94 )
    ExFreePoolWithTag(v94, 0x62547348u);
  if ( P )
    ExFreePoolWithTag(P, 0x634E7348u);
  if ( v72 )
    FltReleaseContext(StreamContext);
  if ( Contexta[0] )
    FltReleaseContext(Contexta[0]);
  if ( Contexta[1] )
    FltReleaseContext(Contexta[1]);
  if ( v96[0] )
    HsmpReleaseFileNameLock(v96[0]);
  if ( v87 )
    HsmpReleaseFileNameLock(v87);
  return v29;
}

```

## disassembly

```asm
0x1400536e0  push    rbp
0x1400536e2  push    rbx
0x1400536e3  push    rsi
0x1400536e4  push    rdi
0x1400536e5  push    r12
0x1400536e7  push    r13
0x1400536e9  push    r14
0x1400536eb  push    r15
0x1400536ed  lea     rbp, [rsp-178h]
0x1400536f5  sub     rsp, 278h
0x1400536fc  mov     rax, cs:__security_cookie
0x140053703  xor     rax, rsp
0x140053706  mov     [rbp+1B0h+var_50], rax
0x14005370d  mov     rax, [rbp+1B0h+arg_28]
0x140053714  mov     r12, rcx
0x140053717  mov     rcx, [rbp+1B0h+arg_20]
0x14005371e  mov     r15, r9
0x140053721  mov     [rbp+1B0h+var_170], rax
0x140053725  mov     r13, rdx
0x140053728  mov     [rbp+1B0h+var_120], r8
0x14005372f  xor     r8d, r8d
0x140053732  mov     [rbp+1B0h+var_128], rcx
0x140053739  mov     rax, [rcx+18h]
0x14005373d  mov     rdi, [rcx+20h]
0x140053741  mov     [rbp+1B0h+Instance], rax
0x140053745  mov     rax, [r9+10h]
0x140053749  mov     [rbp+1B0h+FileObject], rdi
0x14005374d  mov     ecx, [rax+20h]
0x140053750  mov     rbx, [rax+38h]
0x140053754  mov     [rbp+1B0h+FileNameInformation], r8
0x140053758  test    rdx, rdx
0x14005375b  jnz     loc_140054032
0x140053761  mov     r14, r8
0x140053764  mov     [rbp+1B0h+FileInformation], r8
0x140053768  mov     rdx, r8; Val
0x14005376b  mov     rax, [rax+28h]
0x14005376f  xorps   xmm0, xmm0
0x140053772  mov     [rbp+1B0h+var_1F8], rax
0x140053776  xorps   xmm1, xmm1
0x140053779  mov     [rbp+1B0h+var_228], r14
0x14005377d  mov     esi, 1
0x140053782  mov     [rbp+1B0h+var_1D0], r8
0x140053786  mov     [rbp+1B0h+var_1E8], rdx
0x14005378a  mov     [rbp+1B0h+var_178], rdx
0x14005378e  mov     [rbp+1B0h+var_208], r8
0x140053792  mov     [rbp+1B0h+var_220], r8d
0x140053796  mov     [rbp+1B0h+var_21C], r8d
0x14005379a  mov     [rbp+1B0h+P], r8
0x14005379e  mov     [rbp+1B0h+var_22C], r8b
0x1400537a2  movups  [rbp+1B0h+var_188], xmm0
0x1400537a6  movups  xmmword ptr [rbp+1B0h+var_118], xmm1
0x1400537ad  cmp     ecx, 0Ah
0x1400537b0  jz      loc_140053925
0x1400537b6  cmp     ecx, 41h ; 'A'
0x1400537b9  jz      loc_140053918
0x1400537bf  mov     [rbp+1B0h+var_230], r8b
0x1400537c3  cmp     ecx, 41h ; 'A'
0x1400537c6  jz      loc_140053905
0x1400537cc  mov     byte ptr [rbp+1B0h+var_22E], r8b
0x1400537d0  xor     eax, eax
0x1400537d2  lea     rcx, [rbp+1B0h+var_A0]; void *
0x1400537d9  movups  xmmword ptr [rbp+1B0h+ObjectAttributes.ObjectName], xmm0
0x1400537e0  movups  xmmword ptr [rbp+1B0h+ObjectAttributes.Length], xmm0
0x1400537e7  lea     r8d, [rax+48h]; Size
0x1400537eb  movups  xmmword ptr [rbp+1B0h+ObjectAttributes+1Ch], xmm0
0x1400537f2  movups  xmmword ptr [rbp+1B0h+IoStatusBlock], xmm0
0x1400537f9  call    memset
0x1400537fe  xor     eax, eax
0x140053800  xorps   xmm0, xmm0
0x140053803  mov     r8, r15
0x140053806  mov     [rbp+1B0h+FileHandle], rax
0x14005380a  mov     rdx, r13
0x14005380d  mov     [rbp+1B0h+var_200], rax
0x140053811  mov     rcx, r12; Context
0x140053814  mov     [rbp+1B0h+var_168], rax
0x140053818  movups  xmmword ptr [rbp+1B0h+Context], xmm0
0x14005381c  mov     [rbp+1B0h+var_130], rax
0x140053823  movups  xmmword ptr [rbp+1B0h+var_150], xmm0
0x140053827  movups  [rbp+1B0h+var_140], xmm0
0x14005382b  call    HsmpAcquireFileNameLock
0x140053830  mov     [rbp+1B0h+var_1C0], rax
0x140053834  test    rax, rax
0x140053837  jz      loc_140053CF1
0x14005383d  test    r13, r13
0x140053840  jz      loc_140053937
0x140053846  mov     rdi, [rbp+1B0h+Instance]
0x14005384a  cmp     [rbp+1B0h+var_1F8], 0
0x14005384f  jnz     loc_140053958
0x140053855  cmp     dword ptr [rbx+10h], 2
0x140053859  jb      loc_140053958
0x14005385f  lea     rax, [rbx+14h]
0x140053863  cmp     word ptr [rax], 3Ah ; ':'
0x140053867  jnz     loc_140053958
0x14005386d  mov     edx, 52h ; 'R'
0x140053872  mov     qword ptr [rbp+1B0h+String2.Length], 540052h
0x14005387a  xorps   xmm0, xmm0
0x14005387d  lea     rcx, a3d0ce612Fdee43_1
0x140053884  movups  xmmword ptr [rbp+1B0h+String1.Length], xmm0
0x140053888  mov     [rbp+1B0h+String1.Buffer], rax
0x14005388c  mov     r8b, sil; CaseInSensitive
0x14005388f  movzx   eax, word ptr [rbx+10h]
0x140053893  cmp     ax, dx
0x140053896  mov     [rbp+1B0h+String1.MaximumLength], ax
0x14005389a  mov     [rbp+1B0h+String2.Buffer], rcx
0x14005389e  lea     rcx, [rbp+1B0h+String1]; String1
0x1400538a2  cmova   ax, dx
0x1400538a6  lea     rdx, [rbp+1B0h+String2]; String2
0x1400538aa  mov     [rbp+1B0h+String1.Length], ax
0x1400538ae  call    cs:__imp_RtlEqualUnicodeString
0x1400538b5  nop     dword ptr [rax+rax+00h]
0x1400538ba  test    al, al
0x1400538bc  jz      loc_140053958
0x1400538c2  mov     edi, 0C000CF18h
0x1400538c7  mov     ecx, edi
0x1400538c9  call    HsmDbgBreakOnStatus
0x1400538ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400538d5  lea     r14, WPP_GLOBAL_Control
0x1400538dc  cmp     rcx, r14
0x1400538df  jz      loc_140053CE5
0x1400538e5  mov     eax, [rcx+2Ch]
0x1400538e8  test    sil, al
0x1400538eb  jz      loc_140053CE5
0x1400538f1  cmp     byte ptr [rcx+29h], 2
0x1400538f5  jb      loc_140053CE5
0x1400538fb  mov     edx, 27h ; '''
0x140053900  jmp     loc_140054258
0x140053905  mov     eax, [rbx]
0x140053907  mov     byte ptr [rbp+1B0h+var_22E], sil
0x14005390b  test    al, 2
0x14005390d  jnz     loc_1400537D0
0x140053913  jmp     loc_1400537CC
0x140053918  mov     eax, [rbx]
0x14005391a  test    sil, al
0x14005391d  jz      loc_1400537BF
0x140053923  jmp     short loc_14005392E
0x140053925  cmp     [rbx], r8b
0x140053928  jz      loc_1400537B6
0x14005392e  mov     [rbp+1B0h+var_230], sil
0x140053932  jmp     loc_1400537C3
0x140053937  mov     r8, rdi; FileObject
0x14005393a  mov     rcx, r15; CallbackData
0x14005393d  mov     rdi, [rbp+1B0h+Instance]
0x140053941  mov     rdx, rdi; Instance
0x140053944  call    HsmpGetStreamContext
0x140053949  mov     r13, rax
0x14005394c  test    rax, rax
0x14005394f  jnz     loc_140053F62
0x140053955  mov     [rbp+1B0h+var_22C], al
0x140053958  mov     r8, [rbx+8]; RootDirectory
0x14005395c  lea     rax, [rbp+1B0h+FileNameInformation]
0x140053960  mov     [rsp+2B0h+RetFileNameInformation], rax; RetFileNameInformation
0x140053965  lea     r9, [rbx+14h]; FileName
0x140053969  mov     eax, [rbx+10h]
0x14005396c  mov     rcx, rdi; Instance
0x14005396f  mov     rbx, [rbp+1B0h+FileObject]
0x140053973  mov     rdx, rbx; FileObject
0x140053976  mov     [rsp+2B0h+NameOptions], 101h; NameOptions
0x14005397e  mov     [rsp+2B0h+FileNameLength], eax; FileNameLength
0x140053982  call    cs:__imp_FltGetDestinationFileNameInformation
0x140053989  nop     dword ptr [rax+rax+00h]
0x14005398e  mov     ecx, eax
0x140053990  mov     edi, eax
0x140053992  call    HsmDbgBreakOnStatus
0x140053997  test    edi, edi
0x140053999  js      loc_140053E39
0x14005399f  cmp     byte ptr [rbp+1B0h+var_22E], 0
0x1400539a3  jnz     short loc_1400539AE
0x1400539a5  test    r13, r13
0x1400539a8  jz      loc_140053ADC
0x1400539ae  xorps   xmm0, xmm0
0x1400539b1  mov     [rbp+1B0h+var_B8], rsi
0x1400539b8  mov     ecx, 28h ; '('
0x1400539bd  movups  xmmword ptr [rbp+1B0h+var_D8.Size], xmm0
0x1400539c4  mov     [rbp+1B0h+var_D8.Size], cx
0x1400539cb  mov     rcx, rbx; FileObject
0x1400539ce  movups  xmmword ptr [rbp+1B0h+var_D8.DeviceObjectHint], xmm0
0x1400539d5  call    cs:__imp_IoGetTransactionParameterBlock
0x1400539dc  nop     dword ptr [rax+rax+00h]
0x1400539e1  mov     rdx, [rbp+1B0h+Instance]
0x1400539e5  lea     r9, [rbp+1B0h+IoStatusBlock]
0x1400539ec  mov     rcx, cs:Filter
0x1400539f3  lea     r8, [rbp+1B0h+ObjectAttributes]
0x1400539fa  mov     [rbp+1B0h+var_D8.TxnParameters], rax
0x140053a01  xorps   xmm0, xmm0
0x140053a04  mov     rax, [rbp+1B0h+FileNameInformation]
0x140053a08  add     rax, 8
0x140053a0c  mov     [rbp+1B0h+ObjectAttributes.Length], 30h ; '0'
0x140053a16  mov     [rbp+1B0h+ObjectAttributes.ObjectName], rax
0x140053a1d  lea     rax, [rbp+1B0h+var_D8]
0x140053a24  mov     [rsp+2B0h+AllocationSize], rax
0x140053a29  lea     rax, [rbp+1B0h+var_A0]
0x140053a30  mov     dword ptr [rsp+2B0h+RetFileNameInformation], 44h ; 'D'
0x140053a38  mov     [rsp+2B0h+NameOptions], 48h ; 'H'
0x140053a40  mov     qword ptr [rsp+2B0h+FileNameLength], rax
0x140053a45  mov     [rbp+1B0h+ObjectAttributes.RootDirectory], 0
0x140053a50  mov     [rbp+1B0h+ObjectAttributes.Attributes], 240h
0x140053a5a  movdqu  xmmword ptr [rbp+1B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140053a62  call    cs:__imp_FltQueryInformationByName
0x140053a69  nop     dword ptr [rax+rax+00h]
0x140053a6e  mov     ecx, eax
0x140053a70  mov     edi, eax
0x140053a72  call    HsmDbgBreakOnStatus
0x140053a77  test    edi, edi
0x140053a79  jns     loc_140053F6B
0x140053a7f  cmp     edi, 0C0000034h
0x140053a85  jz      short loc_140053ADC
0x140053a87  cmp     edi, 0C000003Ah
0x140053a8d  jz      short loc_140053ADC
0x140053a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140053a96  lea     r14, WPP_GLOBAL_Control
0x140053a9d  cmp     rcx, r14
0x140053aa0  jz      loc_140053BDE
0x140053aa6  mov     eax, [rcx+2Ch]
0x140053aa9  test    sil, al
0x140053aac  jz      loc_140053BDE
0x140053ab2  cmp     byte ptr [rcx+29h], 2
0x140053ab6  jb      loc_140053BDE
0x140053abc  mov     r8, [rbp+1B0h+var_228]
0x140053ac0  mov     edx, 2Ch ; ','
0x140053ac5  mov     [rsp+2B0h+FileAttributes], edi
0x140053ac9  mov     [rsp+2B0h+AllocationSize], r13
0x140053ace  mov     [rsp+2B0h+RetFileNameInformation], r8
0x140053ad3  jmp     loc_14005467A
0x140053ad8  test    edi, edi
0x140053ada  js      short loc_140053A8F
0x140053adc  lea     r14, WPP_GLOBAL_Control
0x140053ae3  test    r13, r13
0x140053ae6  jnz     loc_140053CFB
0x140053aec  mov     rax, qword ptr [rbp+1B0h+var_188+8]
0x140053af0  mov     qword ptr [rbp+1B0h+String2.Length], rax
0x140053af4  movzx   eax, word ptr [rbp+1B0h+var_188]
0x140053af8  mov     [rbp+1B0h+var_22E], ax
0x140053afc  mov     rdx, [rbp+1B0h+var_128]
0x140053b03  lea     r8, [rbp+1B0h+FileInformation]; FileInformation
0x140053b07  mov     rcx, [r12+20h]; Instance
0x140053b0c  mov     r9d, 8; Length
0x140053b12  mov     qword ptr [rsp+2B0h+NameOptions], 0; LengthReturned
0x140053b1b  mov     [rsp+2B0h+FileNameLength], 23h ; '#'; FileInformationClass
0x140053b23  mov     rdx, [rdx+20h]; FileObject
0x140053b27  call    cs:__imp_FltQueryInformationFile
0x140053b2e  nop     dword ptr [rax+rax+00h]
0x140053b33  mov     ecx, eax
0x140053b35  mov     edi, eax
0x140053b37  call    HsmDbgBreakOnStatus
0x140053b3c  test    edi, edi
0x140053b3e  js      loc_140053CD5
0x140053b44  mov     rax, [rbp+1B0h+var_120]
0x140053b4b  mov     ebx, dword ptr [rbp+1B0h+FileInformation]
0x140053b4e  and     ebx, 10h
0x140053b51  mov     [rbp+1B0h+Context+8], rax
0x140053b55  setnz   dil
0x140053b59  test    rax, rax
0x140053b5c  jnz     loc_140053CC1
0x140053b62  mov     rcx, r12; Context
0x140053b65  mov     [rbp+1B0h+Context], r12
0x140053b69  call    cs:__imp_FltReferenceContext
0x140053b70  nop     dword ptr [rax+rax+00h]
0x140053b75  mov     rax, [rbp+1B0h+var_1C0]
0x140053b79  mov     rcx, r13
0x140053b7c  mov     rdx, [rbp+1B0h+var_208]
0x140053b80  mov     [rbp+1B0h+var_150], rax
0x140053b84  xor     eax, eax
0x140053b86  mov     [rbp+1B0h+var_1C0], rax
0x140053b8a  mov     rax, [rbp+1B0h+var_1D0]
0x140053b8e  mov     qword ptr [rbp+1B0h+var_140], rax
0x140053b92  mov     eax, dword ptr [rbp+1B0h+FileInformation]
0x140053b95  mov     dword ptr [rbp+1B0h+var_130], eax
0x140053b9b  mov     [rbp+1B0h+var_150+8], r15
0x140053b9f  mov     qword ptr [rbp+1B0h+var_140+8], rdx
0x140053ba3  mov     byte ptr [rbp+1B0h+var_130+4], dil
0x140053baa  call    HsmpIsPlaceholder
0x140053baf  test    al, al
0x140053bb1  jnz     loc_140053F31
0x140053bb7  mov     byte ptr [rbp+1B0h+var_130+5], 0
0x140053bbe  call    HsmpIsPlaceholder
0x140053bc3  test    al, al
0x140053bc5  jnz     loc_140053E9F
0x140053bcb  xor     edx, edx
0x140053bcd  mov     r8, [rbp+1B0h+var_170]
0x140053bd1  lea     rcx, [rbp+1B0h+Context]
0x140053bd5  call    HsmiInfoPrepareForPostRename
0x140053bda  mov     esi, eax
0x140053bdc  jmp     short loc_140053BE6
0x140053bde  test    edi, edi
0x140053be0  js      loc_140053CE5
0x140053be6  mov     rcx, [rbp+1B0h+var_118+8]; P
0x140053bed  test    rcx, rcx
0x140053bf0  jnz     loc_14005472F
0x140053bf6  mov     rcx, [rbp+1B0h+FileNameInformation]; FileNameInformation
0x140053bfa  test    rcx, rcx
0x140053bfd  jz      short loc_140053C0B
0x140053bff  call    cs:__imp_FltReleaseFileNameInformation
0x140053c06  nop     dword ptr [rax+rax+00h]
0x140053c0b  mov     rcx, [rbp+1B0h+FileHandle]; FileHandle
0x140053c0f  test    rcx, rcx
0x140053c12  jnz     loc_140054745
0x140053c18  mov     rcx, [rbp+1B0h+var_200]; Object
0x140053c1c  test    rcx, rcx
0x140053c1f  jnz     loc_140054756
0x140053c25  mov     rax, [rbp+1B0h+var_168]
  ... truncated ...
```
