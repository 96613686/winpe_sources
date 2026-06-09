# ClfsCreateLogFile

- ea: `0x14005d740`
- end: `0x14005e8b1`
- name: `ClfsCreateLogFile`
- size: `4465`
- prototype: `NTSTATUS __stdcall(PPLOG_FILE_OBJECT pplfoLog, PUNICODE_STRING puszLogFileName, ACCESS_MASK fDesiredAccess, ULONG dwShareMode, PSECURITY_DESCRIPTOR psdLogFile, ULONG fCreateDisposition, ULONG fCreateOptions, ULONG fFlagsAndAttributes, ULONG fLogOptionFlag, PVOID pvContext, ULONG cbContext)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14004b920`
- `0x14005d6b0`

## callees

- `0x14000b17c`
- `0x14000c2f0`
- `0x14000e074`
- `0x14000ed64`
- `0x140011d90`
- `0x140016f64`
- `0x140017e40`
- `0x140018280`
- `0x1400371a4`
- `0x140047f34`
- `0x14004b3e0`
- `0x140059e80`
- `0x14005d740`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x14005dcef`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14005dd1d`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14005dd5b`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14005dcef`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14005dd1d`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14005dd5b`
- `ntoskrnl!ObfDereferenceObject` at `0x14005e201`
- `ntoskrnl!ObfDereferenceObject` at `0x14005e6de`
- `ntoskrnl!ObfDereferenceObject` at `0x14005e201`
- `ntoskrnl!ObfDereferenceObject` at `0x14005e6de`
- `ntoskrnl!ZwClose` at `0x14005e7cb`
- `ntoskrnl!ZwClose` at `0x14005e7e4`
- `ntoskrnl!ZwClose` at `0x14007a183`
- `ntoskrnl!ZwClose` at `0x14007a19c`
- `ntoskrnl!ZwClose` at `0x14005e7cb`
- `ntoskrnl!ZwClose` at `0x14005e7e4`
- `ntoskrnl!ZwClose` at `0x14007a183`
- `ntoskrnl!ZwClose` at `0x14007a19c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005e18e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005e668`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005e18e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005e668`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14005defc`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14005defc`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x14005e03d`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x14005e31a`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x14005e4be`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x14005e5df`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x14005e03d`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x14005e31a`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x14005e4be`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x14005e5df`
- `ntoskrnl!RtlIsSandboxedToken` at `0x14005d8c1`
- `ntoskrnl!RtlIsSandboxedToken` at `0x14005d8c1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14005dee0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14005df17`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14005dee0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14005df17`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005dcb5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005dcd0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005dd94`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005dcb5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005dcd0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005dd94`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e802`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a1c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e802`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a1c5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005dde9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005dde9`

## string_xrefs

- `0x14005d8f7`: `ClfsCreateLogFile`
- `0x14005d9f8`: `ClfsCreateLogFile`
- `0x14005dc4b`: `ClfsCreateLogFile`
- `0x14005de30`: `ClfsCreateLogFile`
- `0x14005e13c`: `ClfsCreateLogFile`
- `0x14005e1e5`: `ClfsCreateLogFile`
- `0x14005e409`: `ClfsCreateLogFile`
- `0x14005e61e`: `ClfsCreateLogFile`
- `0x14005e6c2`: `ClfsCreateLogFile`
- `0x14005e73c`: `ClfsCreateLogFile`
- `0x14005e830`: `ClfsCreateLogFile`
- `0x14005e871`: `ClfsCreateLogFile`

## pseudocode

```c
NTSTATUS __stdcall ClfsCreateLogFile(
        PPLOG_FILE_OBJECT pplfoLog,
        PUNICODE_STRING puszLogFileName,
        ACCESS_MASK fDesiredAccess,
        ULONG dwShareMode,
        PSECURITY_DESCRIPTOR psdLogFile,
        ULONG fCreateDisposition,
        ULONG fCreateOptions,
        ULONG fFlagsAndAttributes,
        ULONG fLogOptionFlag,
        PVOID pvContext,
        ULONG cbContext)
{
  ULONG EaLength; // r12d
  struct _KTHREAD *CurrentThread; // rdx
  ULONG v16; // esi
  int v17; // eax
  __int64 *EaBuffer; // rbx
  BOOLEAN v19; // al
  unsigned __int16 Length; // r15
  SIZE_T v21; // rax
  wchar_t *PoolWithTag; // rax
  wchar_t *v23; // r15
  bool v24; // r15
  ULONG Options; // r13d
  int v26; // ebx
  ACCESS_MASK v27; // r14d
  int v28; // eax
  PPLOG_FILE_OBJECT v29; // r15
  PVOID v30; // rcx
  CClfsLogCcb *v31; // rcx
  PVOID v32; // rcx
  ULONG FileAttributes; // r12d
  ULONG CreateOptions; // r14d
  NTSTATUS v35; // eax
  int v36; // eax
  ULONG v37; // r14d
  ACCESS_MASK v38; // r14d
  PVOID v39; // rcx
  CClfsLogCcb *FsContext2; // r14
  unsigned int v41; // edx
  ULONG_PTR v42; // rcx
  union _LARGE_INTEGER *ShareAccess; // [rsp+30h] [rbp-1B8h]
  union _LARGE_INTEGER *ShareAccessa; // [rsp+30h] [rbp-1B8h]
  unsigned __int8 v45[4]; // [rsp+80h] [rbp-168h] BYREF
  int v46; // [rsp+84h] [rbp-164h]
  ACCESS_MASK DesiredAccess; // [rsp+88h] [rbp-160h]
  ULONG v48; // [rsp+8Ch] [rbp-15Ch]
  PPLOG_FILE_OBJECT v49; // [rsp+90h] [rbp-158h]
  void *FileHandle; // [rsp+98h] [rbp-150h] BYREF
  unsigned __int16 v51; // [rsp+A0h] [rbp-148h]
  ULONG v52; // [rsp+A4h] [rbp-144h]
  PVOID Object; // [rsp+A8h] [rbp-140h] BYREF
  UNICODE_STRING String2; // [rsp+B0h] [rbp-138h] BYREF
  UNICODE_STRING Destination; // [rsp+C0h] [rbp-128h] BYREF
  HANDLE Handle; // [rsp+D0h] [rbp-118h] BYREF
  PVOID v57; // [rsp+D8h] [rbp-110h] BYREF
  void *v58; // [rsp+E0h] [rbp-108h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-100h] BYREF
  struct _CLFS_EA *v60; // [rsp+F8h] [rbp-F0h]
  PVOID P; // [rsp+100h] [rbp-E8h]
  UNICODE_STRING DestinationString; // [rsp+108h] [rbp-E0h] BYREF
  UNICODE_STRING Source; // [rsp+118h] [rbp-D0h] BYREF
  UNICODE_STRING String1; // [rsp+128h] [rbp-C0h] BYREF
  UNICODE_STRING v65; // [rsp+138h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+148h] [rbp-A0h] BYREF
  PPLOG_FILE_OBJECT v67; // [rsp+178h] [rbp-70h]
  __int64 v68; // [rsp+180h] [rbp-68h] BYREF
  char v69; // [rsp+188h] [rbp-60h]
  __int16 v70; // [rsp+189h] [rbp-5Fh]
  char v71; // [rsp+18Bh] [rbp-5Dh]
  __int64 v72; // [rsp+18Ch] [rbp-5Ch]
  ULONG v73; // [rsp+194h] [rbp-54h]
  PVOID v74; // [rsp+198h] [rbp-50h]
  ULONG fCreateOptionsa; // [rsp+220h] [rbp+38h]

  v52 = dwShareMode;
  DesiredAccess = fDesiredAccess;
  Object = puszLogFileName;
  v49 = pplfoLog;
  v67 = pplfoLog;
  v57 = psdLogFile;
  EaLength = 0;
  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = 0;
  *(_QWORD *)&v65.Length = 0;
  v65.Buffer = 0;
  *(_QWORD *)&Destination.Length = 0;
  Destination.Buffer = 0;
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  IoStatusBlock.Pointer = 0;
  IoStatusBlock.Information = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  FileHandle = 0;
  Handle = 0;
  v58 = 0;
  v45[0] = 0;
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_slDDDDDD(*((_QWORD *)WPP_GLOBAL_Control + 3));
  }
  CurrentThread = KeGetCurrentThread();
  LOBYTE(CurrentThread) = *((_BYTE *)CurrentThread + 562);
  if ( (unsigned __int8)RtlIsSandboxedToken(0, CurrentThread) )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        36,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateLogFile",
        194,
        34);
    }
    return -1073741790;
  }
  v68 = 0x10000000000000LL;
  v69 = 0;
  v73 = 0;
  v74 = 0;
  if ( !CClfsDriver::m_fInitialized )
    CClfsDriver::m_fInitialized = 1;
  if ( !puszLogFileName || !pplfoLog )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        37,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateLogFile",
        235,
        13);
    }
    return -1073741811;
  }
  if ( !pvContext )
  {
    if ( !cbContext )
      goto LABEL_20;
LABEL_17:
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        38,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateLogFile",
        249,
        13);
    }
    return -1073741811;
  }
  if ( !cbContext )
    goto LABEL_17;
LABEL_20:
  v16 = fLogOptionFlag & 0xFFFFFFBF;
  if ( (fLogOptionFlag & 0x40) == 0 )
    v16 = fLogOptionFlag;
  if ( (v16 & 0x20) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        39,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateLogFile",
        23,
        187);
    }
    return -1073741637;
  }
  if ( v16 && (v16 & 0x1000318) == 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        40,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateLogFile",
        43,
        13);
    }
    return -1073741811;
  }
  if ( (v16 & 0x10) != 0 && (v16 & 0x100) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        41,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateLogFile",
        57,
        13);
    }
    return -1073741811;
  }
  if ( (v16 & 0x10) != 0 )
  {
    if ( (v16 & 0x100) != 0 )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          42,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsCreateLogFile",
          72,
          13);
      }
      return -1073741811;
    }
    if ( !pvContext )
    {
      if ( !cbContext )
        goto LABEL_50;
LABEL_46:
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          43,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsCreateLogFile",
          90,
          13);
      }
      return -1073741811;
    }
    if ( !cbContext )
      goto LABEL_46;
    HIDWORD(v72) |= 0x10u;
    v73 = cbContext;
    v74 = pvContext;
  }
LABEL_50:
  if ( (v16 & 0x100) != 0 || (v16 & 0x200) != 0 )
  {
    v17 = HIDWORD(v72);
    if ( (v16 & 0x100) != 0 )
    {
      if ( !pvContext || cbContext < 0x18 )
      {
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
        {
          WPP_SF_slD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            44,
            (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
            (unsigned int)"ClfsCreateLogFile",
            129,
            13);
        }
        return -1073741811;
      }
      v17 = HIDWORD(v72) | 0x100;
    }
    if ( (v16 & 0x200) != 0 )
      v17 |= 0x200u;
    HIDWORD(v72) = v17;
    v73 = cbContext;
    v74 = pvContext;
  }
  EaBuffer = 0;
  v60 = 0;
  v48 = 0;
  if ( (v16 & 0x1000000) != 0 )
    HIDWORD(v72) |= 0x1000000u;
  if ( (v16 & 8) != 0 )
    HIDWORD(v72) |= 8u;
  if ( HIDWORD(v72) )
  {
    EaBuffer = &v68;
    v60 = (struct _CLFS_EA *)&v68;
    EaLength = 32;
    v48 = 32;
  }
  *pplfoLog = 0;
  if ( !ClfsTokenizeStreamNames((const struct _UNICODE_STRING *)Object, &String2, &v65) )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        45,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateLogFile",
        203,
        51);
    }
    return -1073741773;
  }
  RtlInitUnicodeString(&DestinationString, L"\\??\\LOG:");
  RtlInitUnicodeString(&String1, L"LOG:");
  if ( RtlPrefixUnicodeString(&String1, &String2, 1u)
    || (P = 0, RtlPrefixUnicodeString(&DestinationString, &String2, 1u)) )
  {
    *(_QWORD *)&Source.Length = 0;
    Source.Buffer = 0;
    v19 = RtlPrefixUnicodeString(&DestinationString, &String2, 1u);
    Length = String1.Length;
    if ( v19 )
      Length = DestinationString.Length;
    v51 = Length;
    RtlInitUnicodeString(&Destination, L"\\GLOBAL??\\LOG:");
    LOWORD(Object) = String2.Length + Destination.Length - Length + 2;
    v21 = 2 * (((unsigned __int64)(unsigned __int16)Object + 1) >> 1);
    if ( !is_mul_ok(((unsigned __int64)(unsigned __int16)Object + 1) >> 1, 2u) )
      v21 = -1;
    PoolWithTag = (wchar_t *)ExAllocatePoolWithTag(PagedPool, v21, 0x73666C43u);
    v23 = PoolWithTag;
    P = PoolWithTag;
    if ( !PoolWithTag )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          46,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsCreateLogFile",
          6,
          154);
      }
      return -1073741670;
    }
    memset(PoolWithTag, 0, (unsigned __int16)Object);
    Destination.Buffer = v23;
    Destination.Length = 0;
    Destination.MaximumLength = (unsigned __int16)Object;
    Source.Buffer = &String2.Buffer[(unsigned __int64)v51 >> 1];
    Source.Length = String2.Length - v51;
    Source.MaximumLength = String2.MaximumLength - v51;
    RtlAppendUnicodeToString(&Destination, L"\\GLOBAL??\\LOG:");
    RtlAppendUnicodeStringToString(&Destination, &Source);
    RtlAppendUnicodeToString(&Destination, &word_14001C188);
    String2 = Destination;
  }
  v46 = 0;
  v24 = 0;
  Options = (fLogOptionFlag & 0x40) != 0 ? 2304 : 256;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 578;
  ObjectAttributes.ObjectName = &String2;
  ObjectAttributes.SecurityDescriptor = v57;
  ObjectAttributes.SecurityQualityOfService = 0;
  if ( v57 )
    v24 = (*((_WORD *)v57 + 1) & 0x2000) != 0;
  if ( !v65.Length )
  {
    v48 = fFlagsAndAttributes | 0x180;
    v26 = IoCreateFileSpecifyDeviceObjectHint(
            &FileHandle,
            DesiredAccess,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            fFlagsAndAttributes | 0x180,
            v52,
            fCreateDisposition,
            fCreateOptions | 0x8040,
            EaBuffer,
            EaLength,
            CreateFileTypeNone,
            0,
            Options,
            0);
    v46 = v26;
    if ( v26 == -1073741727 && v24 && fCreateDisposition - 2 <= 1 )
    {
      v27 = DesiredAccess;
      v28 = ClfsCreateSaclProtectedLogFileWithHint(
              &FileHandle,
              &v58,
              v45,
              DesiredAccess,
              &ObjectAttributes,
              &IoStatusBlock,
              ShareAccess,
              v48,
              v52,
              fCreateDisposition,
              fCreateOptions | 0x8040,
              v60,
              EaLength,
              Options);
      if ( v28 >= 0 )
        v26 = v28;
      v46 = v26;
    }
    else
    {
      v27 = DesiredAccess;
    }
    if ( v26 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          47,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsCreateLogFile",
          147,
          v26);
      }
LABEL_99:
      v29 = v49;
      goto LABEL_147;
    }
    Object = 0;
    v26 = ObReferenceObjectByHandle(FileHandle, v27, 0, 0, &Object, 0);
    v30 = Object;
    v29 = v49;
    *v49 = (FILE_OBJECT *)Object;
    v46 = v26;
    if ( v26 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          48,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsCreateLogFile",
          177,
          v26);
      }
      goto LABEL_147;
    }
    ObfDereferenceObject(v30);
    CClfsLogCcb::AddRef((CClfsLogCcb *)(*v29)->FsContext2);
    CClfsLogCcb::SetPhysicalHandle(v31, FileHandle);
    CClfsLogCcb::Release(v32);
LABEL_137:
    FsContext2 = (CClfsLogCcb *)(*v29)->FsContext2;
    CClfsLogCcb::AddRef(FsContext2);
    if ( (v16 & 8) != 0 )
    {
      v26 = CClfsLogCcb::SetFileSystemFlag(v42, v41);
      v46 = v26;
      if ( v26 < 0
        && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          54,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsCreateLogFile",
          219,
          v26);
      }
    }
    CClfsLogCcb::SetPhysicalHandle(FsContext2, FileHandle);
    if ( Handle && (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      *((_QWORD *)FsContext2 + 7) = Handle;
    CClfsLogCcb::Release(FsContext2);
    goto LABEL_147;
  }
  FileAttributes = fCreateOptions & 0x20 | 0x80;
  if ( fCreateDisposition == 1 )
  {
    v37 = fCreateOptions | 0x8001;
    fCreateOptionsa = fCreateOptions | 0x8001;
    if ( (DesiredAccess & 0x10000) != 0 )
      fCreateOptionsa = v37 | 0x40;
    v26 = IoCreateFileSpecifyDeviceObjectHint(
            &FileHandle,
            0xC0010000,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            FileAttributes,
            7u,
            1u,
            fCreateOptionsa,
            EaBuffer,
            v48,
            CreateFileTypeNone,
            0,
            0x101u,
            0);
    v46 = v26;
    if ( v26 < 0
      && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        49,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateLogFile",
        2,
        v26);
    }
  }
  else
  {
    if ( fCreateDisposition - 2 >= 2 )
    {
      v26 = -1073741637;
      v46 = -1073741637;
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          51,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsCreateLogFile",
          94,
          187);
      }
      goto LABEL_99;
    }
    CreateOptions = fCreateOptions | 3;
    fCreateOptionsa = CreateOptions;
    v35 = IoCreateFileSpecifyDeviceObjectHint(
            &FileHandle,
            0xC0010000,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            FileAttributes,
            7u,
            3u,
            CreateOptions,
            EaBuffer,
            v48,
            CreateFileTypeNone,
            0,
            0x101u,
            0);
    v26 = v35;
    v46 = v35;
    if ( v24 && v35 == -1073741727 )
    {
      v36 = ClfsCreateSaclProtectedLogFileWithHint(
              &FileHandle,
              &v58,
              v45,
              0xC0010000,
              &ObjectAttributes,
              &IoStatusBlock,
              ShareAccessa,
              FileAttributes,
              7u,
              3u,
              CreateOptions,
              v60,
              v48,
              0x101u);
      if ( v36 >= 0 )
        v26 = v36;
      v46 = v26;
    }
    if ( v26 < 0
      && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        50,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateLogFile",
        81,
        v26);
    }
  }
  if ( v26 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = FileHandle;
    ObjectAttributes.Attributes = 578;
    ObjectAttributes.ObjectName = &v65;
    ObjectAttributes.SecurityDescriptor = v57;
    ObjectAttributes.SecurityQualityOfService = 0;
    v38 = DesiredAccess;
    v26 = IoCreateFileSpecifyDeviceObjectHint(
            &Handle,
            DesiredAccess,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            fFlagsAndAttributes | 0x80,
            v52,
            fCreateDisposition,
            fCreateOptionsa | 0x40,
            0,
            0,
            CreateFileTypeNone,
            0,
            Options,
            0);
    v46 = v26;
    if ( v26 >= 0 )
    {
      v57 = 0;
      v26 = ObReferenceObjectByHandle(Handle, v38, 0, 0, &v57, 0);
      v39 = v57;
      v29 = v49;
      *v49 = (FILE_OBJECT *)v57;
      v46 = v26;
      if ( v26 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
        {
          WPP_SF_slD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            53,
            (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
            (unsigned int)"ClfsCreateLogFile",
            185,
            v26);
        }
        goto LABEL_147;
      }
      ObfDereferenceObject(v39);
      goto LABEL_137;
    }
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        52,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateLogFile",
        156,
        v26);
    }
  }
  v29 = v49;
LABEL_147:
  if ( v45[0] )
    ClfsSetThreadImpersonationToken(v58);
  if ( v26 < 0 )
  {
    if ( Handle )
      ZwClose(Handle);
    if ( FileHandle )
      ZwClose(FileHandle);
    *v29 = 0;
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v26 >= 0
    && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      55,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsCreateLogFile",
      80);
  }
  return v26;
}

```

## disassembly

```asm
0x14005d740  mov     r11, rsp
0x14005d743  push    rbx
0x14005d744  push    rsi
0x14005d745  push    rdi
0x14005d746  push    r12
0x14005d748  push    r13
0x14005d74a  push    r14
0x14005d74c  push    r15
0x14005d74e  sub     rsp, 1B0h
0x14005d755  mov     rax, cs:__security_cookie
0x14005d75c  xor     rax, rsp
0x14005d75f  mov     [rsp+1E8h+var_48], rax
0x14005d767  mov     [rsp+1E8h+var_144], r9d
0x14005d76f  mov     [rsp+1E8h+DesiredAccess], r8d
0x14005d777  mov     rsi, rdx
0x14005d77a  mov     [rsp+1E8h+Object], rdx
0x14005d782  mov     r15, rcx
0x14005d785  mov     [rsp+1E8h+var_158], rcx
0x14005d78d  mov     [rsp+1E8h+var_70], rcx
0x14005d795  mov     rax, [rsp+1E8h+psdLogFile]
0x14005d79d  mov     [rsp+1E8h+var_110], rax
0x14005d7a5  mov     rbx, [rsp+1E8h+pvContext]
0x14005d7ad  xor     r12d, r12d
0x14005d7b0  mov     [r11-138h], r12
0x14005d7b7  mov     [r11-130h], r12
0x14005d7be  mov     [r11-0B0h], r12
0x14005d7c5  mov     [r11-0A8h], r12
0x14005d7cc  mov     [r11-128h], r12
0x14005d7d3  mov     [r11-120h], r12
0x14005d7da  mov     [r11-0C0h], r12
0x14005d7e1  mov     [r11-0B8h], r12
0x14005d7e8  mov     [r11-0E0h], r12
0x14005d7ef  mov     [r11-0D8h], r12
0x14005d7f6  mov     [r11-100h], r12
0x14005d7fd  mov     [r11-0F8h], r12
0x14005d804  mov     [r11-68h], r12
0x14005d808  mov     [r11-60h], r12b
0x14005d80c  xor     eax, eax
0x14005d80e  mov     [r11-5Fh], ax
0x14005d813  mov     [r11-5Dh], al
0x14005d817  mov     [r11-5Ch], rax
0x14005d81b  mov     [r11-54h], r12d
0x14005d81f  mov     [r11-50h], r12
0x14005d823  xorps   xmm0, xmm0
0x14005d826  movups  xmmword ptr [rsp+1E8h+ObjectAttributes.Length], xmm0
0x14005d82e  movups  xmmword ptr [rsp+1E8h+ObjectAttributes.ObjectName], xmm0
0x14005d836  movups  xmmword ptr [r11-80h], xmm0
0x14005d83b  mov     [r11-150h], r12
0x14005d842  mov     [r11-118h], r12
0x14005d849  mov     [r11-108h], r12
0x14005d850  mov     [r11-168h], r12b
0x14005d857  lea     r14, WPP_GLOBAL_Control
0x14005d85e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d865  mov     edi, 4000000h
0x14005d86a  cmp     rcx, r14
0x14005d86d  jz      short loc_14005D8B0
0x14005d86f  test    [rcx+2Ch], edi
0x14005d872  jz      short loc_14005D8B0
0x14005d874  mov     eax, [rsp+1E8h+fLogOptionFlag]
0x14005d87b  mov     [rsp+1E8h+EaLength], eax
0x14005d87f  mov     eax, [rsp+1E8h+fFlagsAndAttributes]
0x14005d886  mov     dword ptr [rsp+1E8h+EaBuffer], eax
0x14005d88a  mov     eax, [r11+38h]
0x14005d88e  mov     [rsp+1E8h+CreateOptions], eax
0x14005d892  mov     eax, [rsp+1E8h+fCreateDisposition]
0x14005d899  mov     [rsp+1E8h+Disposition], eax
0x14005d89d  mov     dword ptr [rsp+1E8h+ShareAccess], r9d
0x14005d8a2  mov     [rsp+1E8h+FileAttributes], r8d
0x14005d8a7  mov     rcx, [rcx+18h]
0x14005d8ab  call    WPP_SF_slDDDDDD
0x14005d8b0  mov     rdx, gs:188h
0x14005d8b9  mov     dl, [rdx+232h]
0x14005d8bf  xor     ecx, ecx
0x14005d8c1  call    cs:__imp_RtlIsSandboxedToken
0x14005d8c8  nop     dword ptr [rax+rax+00h]
0x14005d8cd  test    al, al
0x14005d8cf  jz      short loc_14005D918
0x14005d8d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d8d8  cmp     rcx, r14
0x14005d8db  jz      short loc_14005D90E
0x14005d8dd  test    [rcx+2Ch], edi
0x14005d8e0  jz      short loc_14005D90E
0x14005d8e2  mov     edx, 24h ; '$'
0x14005d8e7  mov     [rsp+1E8h+FileAttributes], 0C0000022h
0x14005d8ef  mov     dword ptr [rsp+1E8h+AllocationSize], 3C2h
0x14005d8f7  lea     r9, aClfscreatelogf; "ClfsCreateLogFile"
0x14005d8fe  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005d905  mov     rcx, [rcx+18h]
0x14005d909  call    WPP_SF_slD
0x14005d90e  mov     eax, 0C0000022h
0x14005d913  jmp     loc_14005E88D
0x14005d918  mov     [rsp+1E8h+var_68], r12d
0x14005d920  mov     [rsp+1E8h+var_64], 100000h
0x14005d92b  mov     edx, 10h
0x14005d930  mov     [rsp+1E8h+var_60], r12b
0x14005d938  mov     [rsp+1E8h+var_54], r12d
0x14005d940  mov     [rsp+1E8h+var_50], r12
0x14005d948  cmp     cs:?m_fInitialized@CClfsDriver@@0EA, r12b; uchar CClfsDriver::m_fInitialized
0x14005d94f  jnz     short loc_14005D958
0x14005d951  mov     cs:?m_fInitialized@CClfsDriver@@0EA, 1; uchar CClfsDriver::m_fInitialized
0x14005d958  test    rsi, rsi
0x14005d95b  jz      loc_14005E84B
0x14005d961  test    r15, r15
0x14005d964  jz      loc_14005E84B
0x14005d96a  mov     ecx, [rsp+1E8h+cbContext]
0x14005d971  test    rbx, rbx
0x14005d974  jz      short loc_14005D97F
0x14005d976  test    ecx, ecx
0x14005d978  jz      short loc_14005D983
0x14005d97a  test    rbx, rbx
0x14005d97d  jnz     short loc_14005D9B6
0x14005d97f  test    ecx, ecx
0x14005d981  jz      short loc_14005D9B6
0x14005d983  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d98a  cmp     rcx, r14
0x14005d98d  jz      loc_14005E888
0x14005d993  test    [rcx+2Ch], edi
0x14005d996  jz      loc_14005E888
0x14005d99c  mov     edx, 26h ; '&'
0x14005d9a1  mov     [rsp+1E8h+FileAttributes], 0C000000Dh
0x14005d9a9  mov     dword ptr [rsp+1E8h+AllocationSize], 3F9h
0x14005d9b1  jmp     loc_14005E871
0x14005d9b6  mov     eax, [rsp+1E8h+fLogOptionFlag]
0x14005d9bd  mov     r13d, eax
0x14005d9c0  mov     esi, eax
0x14005d9c2  and     esi, 0FFFFFFBFh
0x14005d9c5  and     r13d, 40h
0x14005d9c9  cmovz   esi, eax
0x14005d9cc  test    sil, 20h
0x14005d9d0  jz      short loc_14005DA19
0x14005d9d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d9d9  cmp     rcx, r14
0x14005d9dc  jz      short loc_14005DA0F
0x14005d9de  test    [rcx+2Ch], edi
0x14005d9e1  jz      short loc_14005DA0F
0x14005d9e3  mov     edx, 27h ; '''
0x14005d9e8  mov     [rsp+1E8h+FileAttributes], 0C00000BBh
0x14005d9f0  mov     dword ptr [rsp+1E8h+AllocationSize], 417h
0x14005d9f8  lea     r9, aClfscreatelogf; "ClfsCreateLogFile"
0x14005d9ff  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005da06  mov     rcx, [rcx+18h]
0x14005da0a  call    WPP_SF_slD
0x14005da0f  mov     eax, 0C00000BBh
0x14005da14  jmp     loc_14005E88D
0x14005da19  test    esi, esi
0x14005da1b  jz      short loc_14005DA58
0x14005da1d  test    esi, 1000318h
0x14005da23  jnz     short loc_14005DA58
0x14005da25  mov     rcx, cs:WPP_GLOBAL_Control
0x14005da2c  cmp     rcx, r14
0x14005da2f  jz      loc_14005E888
0x14005da35  test    [rcx+2Ch], edi
0x14005da38  jz      loc_14005E888
0x14005da3e  mov     edx, 28h ; '('
0x14005da43  mov     [rsp+1E8h+FileAttributes], 0C000000Dh
0x14005da4b  mov     dword ptr [rsp+1E8h+AllocationSize], 42Bh
0x14005da53  jmp     loc_14005E871
0x14005da58  mov     eax, esi
0x14005da5a  and     eax, edx
0x14005da5c  mov     r14d, 100h
0x14005da62  jz      short loc_14005DAA3
0x14005da64  test    r14d, esi
0x14005da67  jz      short loc_14005DAA3
0x14005da69  mov     rcx, cs:WPP_GLOBAL_Control
0x14005da70  lea     rsi, WPP_GLOBAL_Control
0x14005da77  cmp     rcx, rsi
0x14005da7a  jz      loc_14005E888
0x14005da80  test    [rcx+2Ch], edi
0x14005da83  jz      loc_14005E888
0x14005da89  mov     edx, 29h ; ')'
0x14005da8e  mov     [rsp+1E8h+FileAttributes], 0C000000Dh
0x14005da96  mov     dword ptr [rsp+1E8h+AllocationSize], 439h
0x14005da9e  jmp     loc_14005E871
0x14005daa3  test    eax, eax
0x14005daa5  jz      loc_14005DB50
0x14005daab  test    r14d, esi
0x14005daae  jz      short loc_14005DAEA
0x14005dab0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005dab7  lea     rsi, WPP_GLOBAL_Control
0x14005dabe  cmp     rcx, rsi
0x14005dac1  jz      loc_14005E888
0x14005dac7  test    [rcx+2Ch], edi
0x14005daca  jz      loc_14005E888
0x14005dad0  mov     edx, 2Ah ; '*'
0x14005dad5  mov     [rsp+1E8h+FileAttributes], 0C000000Dh
0x14005dadd  mov     dword ptr [rsp+1E8h+AllocationSize], 448h
0x14005dae5  jmp     loc_14005E871
0x14005daea  test    rbx, rbx
0x14005daed  jnz     short loc_14005DAF8
0x14005daef  test    ecx, ecx
0x14005daf1  jnz     short loc_14005DAFC
0x14005daf3  test    rbx, rbx
0x14005daf6  jz      short loc_14005DB36
0x14005daf8  test    ecx, ecx
0x14005dafa  jnz     short loc_14005DB3A
0x14005dafc  mov     rcx, cs:WPP_GLOBAL_Control
0x14005db03  lea     rsi, WPP_GLOBAL_Control
0x14005db0a  cmp     rcx, rsi
0x14005db0d  jz      loc_14005E888
0x14005db13  test    [rcx+2Ch], edi
0x14005db16  jz      loc_14005E888
0x14005db1c  mov     edx, 2Bh ; '+'
0x14005db21  mov     [rsp+1E8h+FileAttributes], 0C000000Dh
0x14005db29  mov     dword ptr [rsp+1E8h+AllocationSize], 45Ah
0x14005db31  jmp     loc_14005E871
0x14005db36  test    ecx, ecx
0x14005db38  jz      short loc_14005DB50
0x14005db3a  or      [rsp+1E8h+var_58], edx
0x14005db41  mov     [rsp+1E8h+var_54], ecx
0x14005db48  mov     [rsp+1E8h+var_50], rbx
0x14005db50  mov     r8d, esi
0x14005db53  and     r8d, r14d
0x14005db56  mov     edx, 200h
0x14005db5b  jnz     short loc_14005DB61
0x14005db5d  test    edx, esi
0x14005db5f  jz      short loc_14005DB9E
0x14005db61  mov     eax, [rsp+1E8h+var_58]
0x14005db68  test    r8d, r8d
0x14005db6b  jz      short loc_14005DB82
0x14005db6d  test    rbx, rbx
0x14005db70  jz      loc_14005DC6C
0x14005db76  cmp     ecx, 18h
0x14005db79  jb      loc_14005DC6C
0x14005db7f  or      eax, r14d
0x14005db82  test    edx, esi
0x14005db84  jz      short loc_14005DB88
0x14005db86  or      eax, edx
0x14005db88  mov     [rsp+1E8h+var_58], eax
0x14005db8f  mov     [rsp+1E8h+var_54], ecx
0x14005db96  mov     [rsp+1E8h+var_50], rbx
0x14005db9e  mov     rbx, r12
0x14005dba1  mov     [rsp+1E8h+var_F0], rbx
0x14005dba9  mov     [rsp+1E8h+var_15C], r12d
0x14005dbb1  mov     eax, 1000000h
0x14005dbb6  test    eax, esi
0x14005dbb8  jz      short loc_14005DBC1
0x14005dbba  or      [rsp+1E8h+var_58], eax
0x14005dbc1  test    sil, 8
0x14005dbc5  jz      short loc_14005DBCF
0x14005dbc7  or      [rsp+1E8h+var_58], 8
0x14005dbcf  xor     eax, eax
0x14005dbd1  cmp     [rsp+1E8h+var_58], eax
0x14005dbd8  jz      short loc_14005DBF6
0x14005dbda  lea     rbx, [rsp+1E8h+var_68]
0x14005dbe2  mov     [rsp+1E8h+var_F0], rbx
0x14005dbea  lea     r12d, [rax+20h]
0x14005dbee  mov     [rsp+1E8h+var_15C], r12d
0x14005dbf6  mov     [r15], rax
0x14005dbf9  lea     r8, [rsp+1E8h+var_B0]; PUNICODE_STRING
0x14005dc01  lea     rdx, [rsp+1E8h+String2]; DestinationString
0x14005dc09  mov     rcx, [rsp+1E8h+Object]; struct _UNICODE_STRING *
0x14005dc11  call    ?ClfsTokenizeStreamNames@@YAEAEBU_UNICODE_STRING@@AEAU1@1@Z; ClfsTokenizeStreamNames(_UNICODE_STRING const &,_UNICODE_STRING &,_UNICODE_STRING &)
0x14005dc16  test    al, al
0x14005dc18  jnz     loc_14005DCA6
0x14005dc1e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005dc25  lea     rsi, WPP_GLOBAL_Control
0x14005dc2c  cmp     rcx, rsi
0x14005dc2f  jz      short loc_14005DC62
0x14005dc31  test    [rcx+2Ch], edi
0x14005dc34  jz      short loc_14005DC62
0x14005dc36  mov     edx, 2Dh ; '-'
0x14005dc3b  mov     [rsp+1E8h+FileAttributes], 0C0000033h
0x14005dc43  mov     dword ptr [rsp+1E8h+AllocationSize], 4CBh
0x14005dc4b  lea     r9, aClfscreatelogf; "ClfsCreateLogFile"
0x14005dc52  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005dc59  mov     rcx, [rcx+18h]
0x14005dc5d  call    WPP_SF_slD
0x14005dc62  mov     eax, 0C0000033h
0x14005dc67  jmp     loc_14005E88D
0x14005dc6c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005dc73  lea     rsi, WPP_GLOBAL_Control
0x14005dc7a  cmp     rcx, rsi
0x14005dc7d  jz      loc_14005E888
0x14005dc83  test    [rcx+2Ch], edi
0x14005dc86  jz      loc_14005E888
0x14005dc8c  mov     edx, 2Ch ; ','
0x14005dc91  mov     [rsp+1E8h+FileAttributes], 0C000000Dh
0x14005dc99  mov     dword ptr [rsp+1E8h+AllocationSize], 481h
0x14005dca1  jmp     loc_14005E871
0x14005dca6  lea     rdx, aLog; "\\??\\LOG:"
0x14005dcad  lea     rcx, [rsp+1E8h+DestinationString]; DestinationString
0x14005dcb5  call    cs:__imp_RtlInitUnicodeString
0x14005dcbc  nop     dword ptr [rax+rax+00h]
0x14005dcc1  lea     rdx, aLog_0; "LOG:"
0x14005dcc8  lea     rcx, [rsp+1E8h+String1]; DestinationString
0x14005dcd0  call    cs:__imp_RtlInitUnicodeString
0x14005dcd7  nop     dword ptr [rax+rax+00h]
0x14005dcdc  mov     r8b, 1; CaseInSensitive
0x14005dcdf  lea     rdx, [rsp+1E8h+String2]; String2
0x14005dce7  lea     rcx, [rsp+1E8h+String1]; String1
0x14005dcef  call    cs:__imp_RtlPrefixUnicodeString
0x14005dcf6  nop     dword ptr [rax+rax+00h]
0x14005dcfb  xor     r8d, r8d
0x14005dcfe  test    al, al
0x14005dd00  jnz     short loc_14005DD34
0x14005dd02  mov     [rsp+1E8h+P], r8
0x14005dd0a  mov     r8b, 1; CaseInSensitive
0x14005dd0d  lea     rdx, [rsp+1E8h+String2]; String2
0x14005dd15  lea     rcx, [rsp+1E8h+DestinationString]; String1
0x14005dd1d  call    cs:__imp_RtlPrefixUnicodeString
  ... truncated ...
```
