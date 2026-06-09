# HsmpCtxCreateInstanceContext

- ea: `0x140072f78`
- end: `0x140074446`
- name: `HsmpCtxCreateInstanceContext`
- size: `5326`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140072f60`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000abb8`
- `0x14000b62c`
- `0x14000c12c`
- `0x140011ef4`
- `0x14001e140`
- `0x14001e220`
- `0x14001e580`
- `0x14001eaa0`
- `0x140072f78`

## import_xrefs

- `ntoskrnl!RtlGUIDFromString` at `0x140073c38`
- `ntoskrnl!RtlGUIDFromString` at `0x140073c38`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400731d4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400731eb`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140073883`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14007389a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400731d4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400731eb`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140073883`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14007389a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400731bd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140073864`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400731bd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140073864`
- `ntoskrnl!RtlGetNtSystemRoot` at `0x1400737b9`
- `ntoskrnl!RtlGetNtSystemRoot` at `0x1400737b9`
- `ntoskrnl!KeInitializeEvent` at `0x1400740ef`
- `ntoskrnl!KeInitializeEvent` at `0x140074108`
- `ntoskrnl!KeInitializeEvent` at `0x1400740ef`
- `ntoskrnl!KeInitializeEvent` at `0x140074108`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14007411f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14007411f`
- `ntoskrnl!ObfDereferenceObject` at `0x1400743f0`
- `ntoskrnl!ObfDereferenceObject` at `0x140074401`
- `ntoskrnl!ObfDereferenceObject` at `0x1400743f0`
- `ntoskrnl!ObfDereferenceObject` at `0x140074401`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400735d8`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14007360d`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400735d8`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14007360d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400737cc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400737cc`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400735a6`
- `ntoskrnl!ExInitializeResourceLite` at `0x140074136`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400735a6`
- `ntoskrnl!ExInitializeResourceLite` at `0x140074136`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007330d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073323`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007340c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400743a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400743b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400743ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007330d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073323`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007340c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400743a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400743b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400743ce`
- `ntoskrnl!ExAllocatePool2` at `0x140073426`
- `ntoskrnl!ExAllocatePool2` at `0x14007369b`
- `ntoskrnl!ExAllocatePool2` at `0x1400736e3`
- `ntoskrnl!ExAllocatePool2` at `0x1400737f8`
- `ntoskrnl!ExAllocatePool2` at `0x140073cca`
- `ntoskrnl!ExAllocatePool2` at `0x140073426`
- `ntoskrnl!ExAllocatePool2` at `0x14007369b`
- `ntoskrnl!ExAllocatePool2` at `0x1400736e3`
- `ntoskrnl!ExAllocatePool2` at `0x1400737f8`
- `ntoskrnl!ExAllocatePool2` at `0x140073cca`
- `FLTMGR!FltClose` at `0x1400732ca`
- `FLTMGR!FltClose` at `0x1400743df`
- `FLTMGR!FltClose` at `0x1400732ca`
- `FLTMGR!FltClose` at `0x1400743df`
- `FLTMGR!FltSetInstanceContext` at `0x140073627`
- `FLTMGR!FltSetInstanceContext` at `0x140073627`
- `FLTMGR!FltGetVolumeFromName` at `0x140073388`
- `FLTMGR!FltGetVolumeFromName` at `0x140073388`
- `FLTMGR!FltQueryVolumeInformation` at `0x140073b05`
- `FLTMGR!FltQueryVolumeInformation` at `0x140073d54`
- `FLTMGR!FltQueryVolumeInformation` at `0x140073db6`
- `FLTMGR!FltQueryVolumeInformation` at `0x140073b05`
- `FLTMGR!FltQueryVolumeInformation` at `0x140073d54`
- `FLTMGR!FltQueryVolumeInformation` at `0x140073db6`
- `FLTMGR!FltFsControlFile` at `0x140073ec0`
- `FLTMGR!FltFsControlFile` at `0x140073f46`
- `FLTMGR!FltFsControlFile` at `0x140073f99`
- `FLTMGR!FltFsControlFile` at `0x140073ec0`
- `FLTMGR!FltFsControlFile` at `0x140073f46`
- `FLTMGR!FltFsControlFile` at `0x140073f99`
- `FLTMGR!FltGetVolumeGuidName` at `0x140073b89`
- `FLTMGR!FltGetVolumeGuidName` at `0x140073b89`
- `FLTMGR!FltOpenVolume` at `0x140073e1d`
- `FLTMGR!FltOpenVolume` at `0x140073e1d`
- `FLTMGR!FltQueryDirectoryFile` at `0x140073aba`
- `FLTMGR!FltQueryDirectoryFile` at `0x140073aba`
- `FLTMGR!FltGetVolumeProperties` at `0x140074003`
- `FLTMGR!FltGetVolumeProperties` at `0x140074003`
- `FLTMGR!FltGetVolumeName` at `0x140073188`
- `FLTMGR!FltGetVolumeName` at `0x140073188`
- `FLTMGR!FltGetInstanceInformation` at `0x140073114`
- `FLTMGR!FltGetInstanceInformation` at `0x140073114`
- `FLTMGR!FltAllocateContext` at `0x140073504`
- `FLTMGR!FltAllocateContext` at `0x14007406f`
- `FLTMGR!FltAllocateContext` at `0x140073504`
- `FLTMGR!FltAllocateContext` at `0x14007406f`
- `FLTMGR!FltCreateFileEx2` at `0x1400739a3`
- `FLTMGR!FltCreateFileEx2` at `0x1400739a3`
- `FLTMGR!FltCbdqInitialize` at `0x14007418e`
- `FLTMGR!FltCbdqInitialize` at `0x14007418e`
- `FLTMGR!FltInitializePushLock` at `0x1400740d3`
- `FLTMGR!FltInitializePushLock` at `0x1400740d3`
- `FLTMGR!FltObjectDereference` at `0x1400733ee`
- `FLTMGR!FltObjectDereference` at `0x1400733ee`
- `FLTMGR!FltReleaseContext` at `0x140074412`
- `FLTMGR!FltReleaseContext` at `0x140074412`

## string_xrefs

- `0x140072fa5`: `\$Extend\$Reparse:$R:$INDEX_ALLOCATION`

## pseudocode

```c
__int64 __fastcall HsmpCtxCreateInstanceContext(struct _FLT_FILTER **a1, int a2, __int64 a3, int a4)
{
  struct _FLT_INSTANCE *v5; // r13
  void *v7; // rsi
  __int64 *p_Buffer; // rbx
  ULONG v9; // r9d
  __int64 InstanceInformation; // rdi
  int i; // ebx
  struct _FLT_VOLUME *v12; // rcx
  ULONG *v13; // r8
  __int64 VolumeName; // rdi
  PDEVICE_OBJECT v16; // rcx
  __int64 Pool2; // rax
  __int64 v18; // rdx
  struct _FLT_INSTANCE *v19; // r9
  PWSTR v20; // rbx
  PWSTR v21; // rbx
  const WCHAR *NtSystemRoot; // rax
  PWSTR v23; // rbx
  __int64 v24; // rax
  WCHAR *v25; // rdx
  struct _FLT_INSTANCE *v26; // rdx
  struct _FLT_FILTER *v27; // rcx
  NTSTATUS v28; // ebx
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __m128 v32; // xmm1
  int k; // edi
  struct _FLT_INSTANCE *v34; // rcx
  int j; // edi
  struct _FLT_VOLUME *v36; // rcx
  ULONG *v37; // r8
  unsigned int VolumeGuidName; // ebx
  int v39; // edx
  int v40; // r8d
  PVOID v41; // rbx
  NTSTATUS v42; // ebx
  unsigned int v43; // eax
  NTSTATUS v44; // ebx
  int v45; // edx
  unsigned int v46; // ecx
  int v47; // ecx
  unsigned int v48; // eax
  PFLT_CONTEXT ReturnedContext; // [rsp+80h] [rbp-80h] BYREF
  bool v50; // [rsp+88h] [rbp-78h]
  ULONG LengthReturned; // [rsp+8Ch] [rbp-74h] BYREF
  PFLT_VOLUME RetVolume[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v53; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+A8h] [rbp-58h] BYREF
  PFILE_OBJECT VolumeFileObject; // [rsp+B8h] [rbp-48h] BYREF
  int v56; // [rsp+C0h] [rbp-40h] BYREF
  int v57; // [rsp+C4h] [rbp-3Ch]
  UNICODE_STRING GuidString; // [rsp+C8h] [rbp-38h] BYREF
  UNICODE_STRING SourceString; // [rsp+D8h] [rbp-28h] BYREF
  PVOID v60[2]; // [rsp+E8h] [rbp-18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+F8h] [rbp-8h] BYREF
  PFILE_OBJECT FileObject; // [rsp+108h] [rbp+8h] BYREF
  UNICODE_STRING P; // [rsp+110h] [rbp+10h] BYREF
  void *VolumeHandle; // [rsp+120h] [rbp+20h] BYREF
  HANDLE FileHandle; // [rsp+128h] [rbp+28h] BYREF
  struct _IO_STATUS_BLOCK Iosb; // [rsp+130h] [rbp+30h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+140h] [rbp+40h] BYREF
  _FLT_VOLUME_PROPERTIES VolumeProperties; // [rsp+170h] [rbp+70h] BYREF
  __int128 FileInformation; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 Buffer; // [rsp+1D0h] [rbp+D0h] BYREF
  int v71; // [rsp+1D8h] [rbp+D8h]
  __int128 FsInformation; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v73; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v74; // [rsp+200h] [rbp+100h]
  GUID Guid; // [rsp+208h] [rbp+108h] BYREF
  _QWORD OutputBuffer[20]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v77[144]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR Source[40]; // [rsp+350h] [rbp+250h] BYREF

  v5 = a1[3];
  wcscpy(Source, L"\\$Extend\\$Reparse:$R:$INDEX_ALOCATION");
  *(_DWORD *)&GuidString.Length = a2;
  v57 = a4;
  ReturnedContext = 0;
  LengthReturned = 0;
  FileHandle = 0;
  *(_OWORD *)v60 = 0;
  FileObject = 0;
  Guid = 0;
  v74 = 0;
  SourceString = 0;
  v53 = 0;
  Destination = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  Iosb = 0;
  v73 = 0;
  FsInformation = 0;
  memset(&VolumeProperties, 0, sizeof(VolumeProperties));
  memset(OutputBuffer, 0, 0x98u);
  VolumeHandle = 0;
  VolumeFileObject = 0;
  Buffer = 0;
  v71 = 0;
  memset(v77, 0, 0x50u);
  if ( byte_140029552 )
  {
    LODWORD(VolumeName) = -1071906801;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        46,
        WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
        v5,
        a1[2],
        -1071906801);
    }
  }
  else
  {
    if ( a4 != 2 && (a4 != 28 || !(unsigned int)Feature_ReFS_OneDrive_Support__private_IsEnabledDeviceUsageNoInline()) )
    {
      LODWORD(VolumeName) = -1071906801;
      goto LABEL_19;
    }
    v50 = 0;
    if ( String1.Buffer )
      goto LABEL_6;
    P.Buffer = L"\\SystemRoot";
    *(_QWORD *)&P.Length = 1572886;
    RetVolume[0] = 0;
    LODWORD(VolumeName) = FltGetVolumeFromName(Filter, &P, RetVolume);
    HsmDbgBreakOnStatus((unsigned int)VolumeName);
    if ( (int)VolumeName >= 0 )
    {
      v50 = RetVolume[0] == a1[2];
      if ( RetVolume[0] )
        FltObjectDereference(RetVolume[0]);
LABEL_6:
      v7 = 0;
      p_Buffer = &Buffer;
      *(_QWORD *)&P.Length = 0;
      v9 = 12;
      while ( 1 )
      {
        InstanceInformation = (unsigned int)FltGetInstanceInformation(
                                              v5,
                                              InstancePartialInformation,
                                              p_Buffer,
                                              v9,
                                              &LengthReturned);
        HsmDbgBreakOnStatus(InstanceInformation);
        if ( (_DWORD)InstanceInformation != -1073741789 )
          break;
        if ( v7 )
          ExFreePoolWithTag(v7, 0x62547348u);
        Pool2 = ExAllocatePool2(256, LengthReturned, 1649701704);
        *(_QWORD *)&P.Length = Pool2;
        v7 = (void *)Pool2;
        if ( !Pool2 )
        {
          LODWORD(VolumeName) = -1073741670;
          HsmDbgBreakOnStatus(3221225626LL);
          goto LABEL_19;
        }
        v9 = LengthReturned;
        p_Buffer = (__int64 *)Pool2;
      }
      if ( (int)InstanceInformation < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqd(
            WPP_GLOBAL_Control->AttachedDevice,
            48,
            WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
            v5,
            a1[2],
            InstanceInformation);
        }
      }
      else
      {
        if ( *((_WORD *)p_Buffer + 4) == stru_140029640.Length
          && !memcmp(
                (char *)p_Buffer + *((unsigned __int16 *)p_Buffer + 5),
                stru_140029640.Buffer,
                *((unsigned __int16 *)p_Buffer + 4))
          && *((_WORD *)p_Buffer + 2) == stru_140029630.Length
          && !memcmp(
                (char *)p_Buffer + *((unsigned __int16 *)p_Buffer + 3),
                stru_140029630.Buffer,
                *((unsigned __int16 *)p_Buffer + 2)) )
        {
          LODWORD(VolumeName) = FltAllocateContext(Filter, 2u, 0x1A0u, (POOL_TYPE)512, &ReturnedContext);
          HsmDbgBreakOnStatus((unsigned int)VolumeName);
          if ( (int)VolumeName < 0 )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_44;
            }
            v18 = 49;
LABEL_70:
            v19 = v5;
            goto LABEL_72;
          }
          memset(ReturnedContext, 0, 0x1A0u);
          *(_DWORD *)ReturnedContext = 843674440;
          ExInitializeResourceLite((PERESOURCE)((char *)ReturnedContext + 8));
          RtlInitializeGenericTableAvl(
            (PRTL_AVL_TABLE)((char *)ReturnedContext + 112),
            HsmiCbdTableCompare,
            HsmiFileIdTableAllocate,
            HsmiFileIdTableFree,
            0);
          RtlInitializeGenericTableAvl(
            (PRTL_AVL_TABLE)((char *)ReturnedContext + 216),
            HsmiFileIdTableCompare,
            HsmiFileIdTableAllocate,
            HsmiFileIdTableFree,
            0);
LABEL_74:
          LODWORD(VolumeName) = FltSetInstanceContext(a1[3], FLT_SET_CONTEXT_KEEP_IF_EXISTS, ReturnedContext, 0);
          HsmDbgBreakOnStatus((unsigned int)VolumeName);
          if ( (int)VolumeName >= 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_qqqd(
                WPP_GLOBAL_Control->AttachedDevice,
                69,
                WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                a1[3],
                a1[2],
                ReturnedContext,
                VolumeName);
            }
            goto LABEL_44;
          }
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_44;
          }
          v18 = 68;
LABEL_71:
          v19 = a1[3];
LABEL_72:
          WPP_SF_qqd(v16->AttachedDevice, v18, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids, v19, a1[2], VolumeName);
          goto LABEL_44;
        }
        for ( i = 0; ; ++i )
        {
          LODWORD(RetVolume[0]) = i;
          if ( i >= 2 )
            break;
          v12 = a1[2];
          v13 = (ULONG *)&v56;
          v56 = 0;
          if ( i )
            v13 = 0;
          VolumeName = (unsigned int)FltGetVolumeName(
                                       v12,
                                       (PUNICODE_STRING)((unsigned __int64)&SourceString & -(__int64)(i != 0)),
                                       v13);
          HsmDbgBreakOnStatus(VolumeName);
          if ( (int)(VolumeName + 0x80000000) >= 0 && (_DWORD)VolumeName != -1073741789 )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v18 = 50;
              goto LABEL_70;
            }
            goto LABEL_44;
          }
          if ( i )
          {
            RtlCopyUnicodeString(&DestinationString, &SourceString);
            RtlAppendUnicodeToString(&DestinationString, Source);
            RtlAppendUnicodeToString(&SourceString, L"\\");
          }
          else
          {
            DestinationString.MaximumLength = v56 + 78;
            SourceString.Length = 0;
            SourceString.MaximumLength = v56 + 2;
            SourceString.Buffer = (PWSTR)ExAllocatePool2(256, (unsigned __int16)(v56 + 2), 1934979912);
            v20 = SourceString.Buffer;
            LODWORD(VolumeName) = SourceString.Buffer == 0 ? 0xC000009A : 0;
            HsmDbgBreakOnStatus((unsigned int)VolumeName);
            if ( !v20 )
            {
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v18 = 51;
                goto LABEL_70;
              }
              goto LABEL_44;
            }
            DestinationString.Length = 0;
            DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, DestinationString.MaximumLength, 1934979912);
            v21 = DestinationString.Buffer;
            LODWORD(VolumeName) = DestinationString.Buffer == 0 ? 0xC000009A : 0;
            HsmDbgBreakOnStatus((unsigned int)VolumeName);
            if ( !v21 )
            {
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v18 = 52;
                goto LABEL_70;
              }
              goto LABEL_44;
            }
            i = (int)RetVolume[0];
          }
        }
        if ( v50 )
        {
          *(_OWORD *)RetVolume = 0;
          NtSystemRoot = (const WCHAR *)RtlGetNtSystemRoot();
          RtlInitUnicodeString((PUNICODE_STRING)RetVolume, NtSystemRoot);
          Destination.Length = 0;
          Destination.MaximumLength = SourceString.MaximumLength + WORD1(RetVolume[0]);
          Destination.Buffer = (PWSTR)ExAllocatePool2(
                                        256,
                                        (unsigned __int16)(SourceString.MaximumLength + WORD1(RetVolume[0])),
                                        1934979912);
          v23 = Destination.Buffer;
          LODWORD(VolumeName) = Destination.Buffer == 0 ? 0xC000009A : 0;
          HsmDbgBreakOnStatus((unsigned int)VolumeName);
          if ( !v23 )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v18 = 53;
              goto LABEL_70;
            }
LABEL_44:
            if ( *(_QWORD *)&P.Length )
              ExFreePoolWithTag(*(PVOID *)&P.Length, 0x62547348u);
            goto LABEL_19;
          }
          RtlCopyUnicodeString(&Destination, &SourceString);
          if ( LOWORD(RetVolume[0]) >= 6u )
          {
            RtlAppendUnicodeToString(&Destination, (PCWSTR)RetVolume[1] + 3);
            RtlAppendUnicodeToString(&Destination, L"\\");
          }
          v24 = *(_QWORD *)&String1.Length;
          v25 = String1.Buffer;
          String1 = Destination;
          *(_QWORD *)&Destination.Length = v24;
          Destination.Buffer = v25;
        }
        if ( (GuidString.Length & 2) != 0 && !byte_140029553 )
        {
LABEL_118:
          LODWORD(VolumeName) = FltQueryVolumeInformation(v5, &Iosb, &FsInformation, 0x10u, FileFsAttributeInformation);
          HsmDbgBreakOnStatus((unsigned int)VolumeName);
          if ( (_DWORD)VolumeName == -2147483643 )
          {
            for ( j = 0; j < 2; ++j )
            {
              v36 = a1[2];
              v37 = (ULONG *)RetVolume;
              LODWORD(RetVolume[0]) = 0;
              if ( j )
                v37 = 0;
              VolumeGuidName = FltGetVolumeGuidName(
                                 v36,
                                 (PUNICODE_STRING)((unsigned __int64)v60 & -(__int64)(j != 0)),
                                 v37);
              HsmDbgBreakOnStatus(VolumeGuidName);
              if ( (int)(VolumeGuidName + 0x80000000) >= 0 && VolumeGuidName != -1073741789 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                {
                  WPP_SF_qqd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    57,
                    WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                    v5,
                    a1[2],
                    VolumeGuidName);
                }
                break;
              }
              if ( !j )
              {
                LOWORD(v60[0]) = 0;
                WORD1(v60[0]) = LOWORD(RetVolume[0]) + 2;
                v60[1] = (PVOID)ExAllocatePool2(256, (unsigned __int16)(LOWORD(RetVolume[0]) + 2), 1934979912);
                v41 = v60[1];
                *(_DWORD *)&GuidString.Length = v60[1] == 0 ? 0xC000009A : 0;
                HsmDbgBreakOnStatus(*(unsigned int *)&GuidString.Length);
                if ( !v41 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                  {
                    WPP_SF_qqd(
                      WPP_GLOBAL_Control->AttachedDevice,
                      58,
                      WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                      v5,
                      a1[2],
                      *(_DWORD *)&GuidString.Length);
                  }
                  break;
                }
              }
            }
            if ( v60[1] )
            {
              *(&GuidString.MaximumLength + 2) = 0;
              GuidString.Length = LOWORD(v60[0]) - 20;
              *(_DWORD *)&GuidString.MaximumLength = (unsigned __int16)(WORD1(v60[0]) - 20);
              GuidString.Buffer = (PWSTR)((char *)v60[1] + 20);
              LODWORD(VolumeName) = RtlGUIDFromString(&GuidString, &Guid);
              HsmDbgBreakOnStatus((unsigned int)VolumeName);
              if ( (int)VolumeName < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qqZd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    v39,
                    v40,
                    (_DWORD)v5,
                    (char)a1[2],
                    (__int64)&GuidString,
                    VolumeName);
                }
                goto LABEL_44;
              }
            }
            LODWORD(VolumeName) = FltQueryVolumeInformation(v5, &Iosb, &v73, 0x18u, FileFsSizeInformation);
            HsmDbgBreakOnStatus((unsigned int)VolumeName);
            if ( (int)VolumeName >= 0 )
            {
              v42 = FltQueryVolumeInformation(v5, &Iosb, &v53, 4u, FileFsObjectIdInformation|FileFsDeviceInformation);
              HsmDbgBreakOnStatus((unsigned int)v42);
              if ( v42 < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                {
                  WPP_SF_qqd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    61,
                    WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                    v5,
                    a1[2],
                    v42);
                }
                v53 = 1;
              }
              LODWORD(VolumeName) = FltOpenVolume(v5, &VolumeHandle, &VolumeFileObject);
              HsmDbgBreakOnStatus((unsigned int)VolumeName);
              if ( (int)VolumeName < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    62,
                    WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                    v5,
                    VolumeName);
                }
                goto LABEL_44;
              }
              if ( v57 == 2 )
                v43 = FltFsControlFile(v5, VolumeFileObject, 0x90064u, 0, 0, OutputBuffer, 0x60u, 0);
              else
                v43 = FltFsControlFile(v5, VolumeFileObject, 0x902D8u, 0, 0, OutputBuffer, 0x98u, 0);
              LODWORD(VolumeName) = v43;
              HsmDbgBreakOnStatus(v43);
              if ( (int)VolumeName >= 0 )
              {
                if ( (FsInformation & 0x80000) == 0 )
                {
                  v44 = FltFsControlFile(v5, VolumeFileObject, 0x900F4u, 0, 0, v77, 0x50u, 0);
                  HsmDbgBreakOnStatus((unsigned int)v44);
                  if ( v44 == -1073741128 )
                  {
                    FileInformation = 0;
                    v44 = FltFsControlFile(v5, VolumeFileObject, 0x900E7u, &FileInformation, 0x10u, 0, 0, 0);
                    HsmDbgBreakOnStatus((unsigned int)v44);
                  }
                  if ( v44 < 0
                    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                  {
                    WPP_SF_qqd(
                      WPP_GLOBAL_Control->AttachedDevice,
                      64,
                      WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                      v5,
                      a1[2],
                      v44);
                  }
                }
                LODWORD(VolumeName) = FltGetVolumeProperties(a1[2], &VolumeProperties, 0x48u, &LengthReturned);
                HsmDbgBreakOnStatus((unsigned int)VolumeName);
                if ( (_DWORD)VolumeName == -2147483643 )
                {
                  VolumeName = (unsigned int)FltAllocateContext(Filter, 2u, 0x1A0u, (POOL_TYPE)512, &ReturnedContext);
                  HsmDbgBreakOnStatus(VolumeName);
                  if ( (int)VolumeName >= 0 )
                  {
                    memset(ReturnedContext, 0, 0x1A0u);
                    *(_DWORD *)ReturnedContext = 1665758024;
                    FltInitializePushLock((PULONG_PTR)ReturnedContext + 14);
                    KeInitializeEvent((PRKEVENT)ReturnedContext + 6, NotificationEvent, 1u);
                    KeInitializeEvent((PRKEVENT)ReturnedContext + 5, NotificationEvent, 1u);
                    ExInitializeRundownProtection((PEX_RUNDOWN_REF)ReturnedContext + 22);
                    ExInitializeResourceLite((PERESOURCE)ReturnedContext + 3);
                    FltCbdqInitialize(
                      v5,
                      (PFLT_CALLBACK_DATA_QUEUE)((char *)ReturnedContext + 184),
                      HsmiDehydrationCsqINSERT_IO,
                      HsmiDehydrationCsqREMOVE_IO,
                      HsmiDehydrationCsqPEEK_NEXT_IO,
                      CldiStreamCdqACQUIRE,
                      CldiStreamCdqRELEASE,
                      HsmiDehydrationCsqCOMPLETE_CANCELED_IO);
                    v45 = v57;
                    *((_QWORD *)ReturnedContext + 4) = v5;
                    *((_QWORD *)ReturnedContext + 5) = a1[2];
                    *((GUID *)ReturnedContext + 3) = Guid;
                    *((UNICODE_STRING *)ReturnedContext + 4) = SourceString;
                    SourceString.Buffer = 0;
                    *((_DWORD *)ReturnedContext + 20) = v45;
                    v46 = HIDWORD(v74) * v74;
                    *((_DWORD *)ReturnedContext + 21) = HIDWORD(v74) * v74;
                    if ( v45 == 2 )
                    {
                      if ( v46 > 0x1000 )
                      {
                        if ( v46 <= 0x10000 )
                          v46 = 0x10000;
                      }
                      else
                      {
                        v46 *= 16;
                      }
                      *((_DWORD *)ReturnedContext + 22) = v46;
                      *((_DWORD *)ReturnedContext + 23) = OutputBuffer[6];
                      *((_QWORD *)ReturnedContext + 12) = 0x7FFFFFFFFFFFFFFFLL;
                    }
                    else
                    {
                      *((_DWORD *)ReturnedContext + 22) = *((_DWORD *)ReturnedContext + 21);
                      v47 = -1;
                      if ( OutputBuffer[8] < 0xFFFFFFFFLL )
                        v47 = OutputBuffer[8];
                      *((_DWORD *)ReturnedContext + 23) = v47;
                      *((_QWORD *)ReturnedContext + 12) = OutputBuffer[8];
                    }
                    *((_DWORD *)ReturnedContext + 26) = VolumeProperties.SectorSize;
                    v48 = v53;
                    if ( v53 <= 1 )
                      v48 = 0;
                    *((_DWORD *)ReturnedContext + 27) = v48;
                    *((_BYTE *)ReturnedContext + 24) = (FsInformation & 0x80000) != 0;
                    LODWORD(VolumeName) = ((__int64 (__fastcall *)(PFLT_CONTEXT, char *))qword_1400296E8)(
                                            ReturnedContext,
                                            (char *)ReturnedContext + 16);
                    HsmDbgBreakOnStatus((unsigned int)VolumeName);
                    if ( (int)VolumeName >= 0 )
                      goto LABEL_74;
                    v16 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      v18 = 67;
                      goto LABEL_71;
                    }
                  }
                  else
                  {
                    v16 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      v18 = 66;
                      goto LABEL_70;
                    }
                  }
                }
                else
                {
                  v16 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    v18 = 65;
                    goto LABEL_70;
                  }
                }
              }
              else
              {
                v16 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v18 = 63;
                  goto LABEL_70;
                }
              }
            }
            else
            {
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v18 = 60;
                goto LABEL_70;
              }
            }
          }
          else
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v18 = 56;
              goto LABEL_70;
            }
          }
          goto LABEL_44;
        }
        v26 = a1[3];
        v27 = a1[1];
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v28 = FltCreateFileEx2(
                v27,
                v26,
                &FileHandle,
                &FileObject,
                0x100001u,
                &ObjectAttributes,
                &Iosb,
                0,
                0,
                7u,
                1u,
                0x200021u,
                0,
                0,
                0,
                0);
        HsmDbgBreakOnStatus((unsigned int)v28);
        if ( v28 >= 0 )
        {
          v31 = 0;
          v32 = (__m128)_mm_shuffle_epi32(_mm_cvtsi32_si128(dword_140029670), 0);
          do
          {
            *(__m128 *)&v77[4 * v31 + 80] = _mm_or_ps(
                                              (__m128)_mm_slli_epi32(
                                                        (__m128i)_mm_and_ps(
                                                                   (__m128)_mm_add_epi32(
                                                                             _mm_shuffle_epi32(
                                                                               _mm_cvtsi32_si128(v31),
                                                                               0),
                                                                             (__m128i)_xmm),
                                                                   (__m128)_xmm),
                                                        0xCu),
                                              v32);
            v31 = (unsigned int)(v31 + 4);
          }
          while ( (unsigned int)v31 < 0x10 );
          for ( k = 0; (unsigned __int64)k < 0x10; ++k )
          {
            RetVolume[0] = (PFLT_VOLUME)262148;
            v34 = a1[3];
            *(_QWORD *)&GuidString.Length = &v77[4 * k + 80];
            RetVolume[1] = *(PFLT_VOLUME *)&GuidString.Length;
            FileInformation = 0;
            v28 = FltQueryDirectoryFile(
                    v34,
                    FileObject,
                    &FileInformation,
                    0x10u,
                    FileReparsePointInformation,
                    1u,
                    (PUNICODE_STRING)RetVolume,
                    1u,
                    &LengthReturned);
            HsmDbgBreakOnStatus((unsigned int)v28);
            if ( v28 >= 0 && DWORD2(FileInformation) == **(_DWORD **)&GuidString.Length )
              goto LABEL_118;
          }
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            v30 = 55;
            goto LABEL_212;
          }
        }
        else if ( v28 != -1073741772 && v28 != -1073741766 )
        {
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v30 = 54;
LABEL_212:
            WPP_SF_qqd(v29->AttachedDevice, v30, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids, v5, a1[2], v28);
          }
        }
      }
      LODWORD(VolumeName) = -1071906801;
      HsmDbgBreakOnStatus(3223060495LL);
      goto LABEL_44;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        47,
        WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
        v5,
        a1[2],
        VolumeName);
    }
  }
LABEL_19:
  if ( v60[1] )
    ExFreePoolWithTag(v60[1], 0x73557348u);
  if ( Destination.Buffer )
    ExFreePoolWithTag(Destination.Buffer, 0x73557348u);
  if ( SourceString.Buffer )
    ExFreePoolWithTag(SourceString.Buffer, 0x73557348u);
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x73557348u);
  if ( VolumeHandle )
    FltClose(VolumeHandle);
  if ( VolumeFileObject )
    ObfDereferenceObject(VolumeFileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( ReturnedContext )
    FltReleaseContext(ReturnedContext);
  return (unsigned int)VolumeName;
}

```

## disassembly

```asm
0x140072f78  push    rbp
0x140072f7a  push    rbx
0x140072f7b  push    rsi
0x140072f7c  push    rdi
0x140072f7d  push    r12
0x140072f7f  push    r13
0x140072f81  push    r14
0x140072f83  push    r15
0x140072f85  lea     rbp, [rsp-2B8h]
0x140072f8d  sub     rsp, 3B8h
0x140072f94  mov     rax, cs:__security_cookie
0x140072f9b  xor     rax, rsp
0x140072f9e  mov     [rbp+2F0h+var_50], rax
0x140072fa5  movups  xmm0, xmmword ptr cs:aExtendReparseR; "\\$Extend\\$Reparse:$R:$INDEX_ALLOCATIO"...
0x140072fac  xor     eax, eax
0x140072fae  movups  xmm1, xmmword ptr cs:aExtendReparseR+10h; "\\$Reparse:$R:$INDEX_ALLOCATION"
0x140072fb5  mov     ebx, r9d
0x140072fb8  mov     r13, [rcx+18h]
0x140072fbc  mov     r15, rcx
0x140072fbf  movups  xmmword ptr [rbp+2F0h+Source], xmm0
0x140072fc6  lea     rcx, [rbp+2F0h+VolumeProperties]; void *
0x140072fca  movups  xmm0, xmmword ptr cs:aExtendReparseR+20h; "e:$R:$INDEX_ALLOCATION"
0x140072fd1  lea     r8d, [rax+48h]; Size
0x140072fd5  movups  [rbp+2F0h+var_80], xmm0
0x140072fdc  movups  xmm0, xmmword ptr cs:aExtendReparseR+3Eh; "OCATION"
0x140072fe3  mov     dword ptr [rbp+2F0h+GuidString.Length], edx
0x140072fe6  xor     edx, edx; Val
0x140072fe8  movups  [rbp+2F0h+var_90], xmm1
0x140072fef  movups  xmm1, xmmword ptr cs:aExtendReparseR+30h; "DEX_ALLOCATION"
0x140072ff6  movups  [rbp+2F0h+var_70], xmm1
0x140072ffd  xorps   xmm1, xmm1
0x140073000  movups  [rbp+2F0h+var_70+0Eh], xmm0
0x140073007  mov     [rbp+2F0h+var_32C], ebx
0x14007300a  xorps   xmm0, xmm0
0x14007300d  mov     [rbp+2F0h+ReturnedContext], 0
0x140073015  movups  xmmword ptr [rbp+2F0h+var_2B0.ObjectName], xmm0
0x140073019  mov     [rbp+2F0h+LengthReturned], 0
0x140073020  movups  xmmword ptr [rbp+2F0h+var_2B0+1Ch], xmm0
0x140073024  mov     [rbp+2F0h+FileHandle], rax
0x140073028  movups  xmmword ptr [rbp+2F0h+var_308], xmm0
0x14007302c  mov     [rbp+2F0h+FileObject], rax
0x140073030  movups  xmmword ptr [rbp+2F0h+Guid.Data1], xmm1
0x140073037  mov     [rbp+2F0h+var_1F0], rax
0x14007303e  movups  xmmword ptr [rbp+2F0h+SourceString.Length], xmm0
0x140073042  mov     [rbp+2F0h+var_350], eax
0x140073045  movups  xmmword ptr [rbp+2F0h+Destination.Length], xmm1
0x140073049  movups  xmmword ptr [rbp+2F0h+DestinationString.Length], xmm0
0x14007304d  movups  xmmword ptr [rbp+2F0h+var_2B0.Length], xmm0
0x140073051  movups  xmmword ptr [rbp+2F0h+Iosb], xmm0
0x140073055  movups  [rbp+2F0h+var_200], xmm1
0x14007305c  movups  [rbp+2F0h+FsInformation], xmm0
0x140073063  call    memset
0x140073068  xor     edx, edx; Val
0x14007306a  lea     rcx, [rbp+2F0h+OutputBuffer]; void *
0x140073071  mov     r8d, 98h; Size
0x140073077  call    memset
0x14007307c  xor     eax, eax
0x14007307e  mov     [rbp+2F0h+VolumeHandle], 0
0x140073086  xor     edx, edx; Val
0x140073088  mov     [rbp+2F0h+VolumeFileObject], 0
0x140073090  lea     rcx, [rbp+2F0h+var_130]; void *
0x140073097  mov     [rbp+2F0h+Buffer], rax
0x14007309e  mov     [rbp+2F0h+var_218], eax
0x1400730a4  lea     r8d, [rax+50h]; Size
0x1400730a8  call    memset
0x1400730ad  cmp     cs:byte_140029552, 0
0x1400730b4  jnz     loc_14007327D
0x1400730ba  mov     r12d, 2
0x1400730c0  cmp     ebx, r12d
0x1400730c3  jz      short loc_1400730DB
0x1400730c5  cmp     ebx, 1Ch
0x1400730c8  jnz     loc_1400731FF
0x1400730ce  call    Feature_ReFS_OneDrive_Support__private_IsEnabledDeviceUsageNoInline
0x1400730d3  test    eax, eax
0x1400730d5  jz      loc_1400731FF
0x1400730db  cmp     cs:String1.Buffer, 0
0x1400730e3  mov     [rbp+2F0h+var_368], 0
0x1400730e7  jz      loc_14007335E
0x1400730ed  xor     esi, esi
0x1400730ef  lea     rbx, [rbp+2F0h+Buffer]
0x1400730f6  mov     [rbp+2F0h+P], rsi
0x1400730fa  lea     r9d, [rsi+0Ch]; BufferSize
0x1400730fe  lea     r14d, [rsi+1]
0x140073102  lea     rax, [rbp+2F0h+LengthReturned]
0x140073106  mov     r8, rbx; Buffer
0x140073109  mov     edx, r14d; InformationClass
0x14007310c  mov     [rsp+3F0h+BytesReturned], rax; BytesReturned
0x140073111  mov     rcx, r13; Instance
0x140073114  call    cs:__imp_FltGetInstanceInformation
0x14007311b  nop     dword ptr [rax+rax+00h]
0x140073120  mov     ecx, eax
0x140073122  mov     edi, eax
0x140073124  call    HsmDbgBreakOnStatus
0x140073129  cmp     edi, 0C0000023h
0x14007312f  jz      loc_1400733FF
0x140073135  test    edi, edi
0x140073137  js      loc_14007345D
0x14007313d  movzx   eax, word ptr [rbx+8]
0x140073141  lea     rsi, WPP_GLOBAL_Control
0x140073148  cmp     ax, cs:stru_140029640.Length
0x14007314f  jz      loc_140073498
0x140073155  xor     ebx, ebx
0x140073157  mov     dword ptr [rbp+2F0h+RetVolume], ebx
0x14007315a  cmp     ebx, r12d
0x14007315d  jge     loc_1400737A8
0x140073163  mov     rcx, [r15+10h]; Volume
0x140073167  lea     r8, [rbp+2F0h+var_330]
0x14007316b  xor     eax, eax
0x14007316d  mov     [rbp+2F0h+var_330], 0
0x140073174  test    ebx, ebx
0x140073176  cmovnz  r8, rax; BufferSizeNeeded
0x14007317a  mov     eax, ebx
0x14007317c  neg     eax
0x14007317e  lea     rax, [rbp+2F0h+SourceString]
0x140073182  sbb     rdx, rdx
0x140073185  and     rdx, rax; VolumeName
0x140073188  call    cs:__imp_FltGetVolumeName
0x14007318f  nop     dword ptr [rax+rax+00h]
0x140073194  mov     ecx, eax
0x140073196  mov     edi, eax
0x140073198  call    HsmDbgBreakOnStatus
0x14007319d  mov     ecx, 80000000h
0x1400731a2  lea     eax, [rdi+rcx]
0x1400731a5  test    ecx, eax
0x1400731a7  jz      loc_1400732D8
0x1400731ad  test    ebx, ebx
0x1400731af  jz      loc_140073674
0x1400731b5  lea     rdx, [rbp+2F0h+SourceString]; SourceString
0x1400731b9  lea     rcx, [rbp+2F0h+DestinationString]; DestinationString
0x1400731bd  call    cs:__imp_RtlCopyUnicodeString
0x1400731c4  nop     dword ptr [rax+rax+00h]
0x1400731c9  lea     rdx, [rbp+2F0h+Source]; Source
0x1400731d0  lea     rcx, [rbp+2F0h+DestinationString]; Destination
0x1400731d4  call    cs:__imp_RtlAppendUnicodeToString
0x1400731db  nop     dword ptr [rax+rax+00h]
0x1400731e0  lea     rdx, asc_1400206E8; "\\"
0x1400731e7  lea     rcx, [rbp+2F0h+SourceString]; Destination
0x1400731eb  call    cs:__imp_RtlAppendUnicodeToString
0x1400731f2  nop     dword ptr [rax+rax+00h]
0x1400731f7  add     ebx, r14d
0x1400731fa  jmp     loc_140073157
0x1400731ff  mov     edi, 0C01C000Fh
0x140073204  mov     rcx, [rbp+2F0h+var_308+8]; P
0x140073208  test    rcx, rcx
0x14007320b  jnz     loc_14007439D
0x140073211  mov     rcx, [rbp+2F0h+Destination.Buffer]; P
0x140073215  test    rcx, rcx
0x140073218  jnz     loc_1400743B3
0x14007321e  mov     rcx, [rbp+2F0h+SourceString.Buffer]; P
0x140073222  test    rcx, rcx
0x140073225  jnz     loc_1400743C9
0x14007322b  mov     rcx, [rbp+2F0h+DestinationString.Buffer]; P
0x14007322f  test    rcx, rcx
0x140073232  jnz     loc_14007331E
0x140073238  mov     rcx, [rbp+2F0h+VolumeHandle]; FileHandle
0x14007323c  test    rcx, rcx
0x14007323f  jnz     loc_1400743DF
0x140073245  mov     rcx, [rbp+2F0h+VolumeFileObject]; Object
0x140073249  test    rcx, rcx
0x14007324c  jnz     loc_1400743F0
0x140073252  mov     rcx, [rbp+2F0h+FileHandle]; FileHandle
0x140073256  test    rcx, rcx
0x140073259  jnz     short loc_1400732CA
0x14007325b  mov     rcx, [rbp+2F0h+FileObject]; Object
0x14007325f  test    rcx, rcx
0x140073262  jnz     loc_140074401
0x140073268  mov     rcx, [rbp+2F0h+ReturnedContext]; Context
0x14007326c  test    rcx, rcx
0x14007326f  jnz     loc_140074412
0x140073275  mov     eax, edi
0x140073277  jmp     loc_140074423
0x14007327d  mov     ecx, 0C01C000Fh
0x140073282  mov     edi, ecx
0x140073284  mov     r10, cs:WPP_GLOBAL_Control
0x14007328b  lea     rsi, WPP_GLOBAL_Control
0x140073292  cmp     r10, rsi
0x140073295  jz      loc_140073204
0x14007329b  mov     eax, [r10+2Ch]
0x14007329f  mov     r14d, 1
0x1400732a5  test    r14b, al
0x1400732a8  jz      loc_140073204
0x1400732ae  lea     r12d, [r14+1]
0x1400732b2  cmp     [r10+29h], r12b
0x1400732b6  jb      loc_140073204
0x1400732bc  mov     dword ptr [rsp+3F0h+ObjectAttributes], ecx
0x1400732c0  lea     edx, [r14+2Dh]
0x1400732c4  mov     rcx, [r10+18h]
0x1400732c8  jmp     short loc_140073341
0x1400732ca  call    cs:__imp_FltClose
0x1400732d1  nop     dword ptr [rax+rax+00h]
0x1400732d6  jmp     short loc_14007325B
0x1400732d8  cmp     edi, 0C0000023h
0x1400732de  jz      loc_1400731AD
0x1400732e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400732eb  lea     rsi, WPP_GLOBAL_Control
0x1400732f2  cmp     rcx, rsi
0x1400732f5  jnz     loc_14007371A
0x1400732fb  mov     rcx, [rbp+2F0h+P]; P
0x1400732ff  test    rcx, rcx
0x140073302  jz      loc_140073204
0x140073308  mov     edx, 62547348h; Tag
0x14007330d  call    cs:__imp_ExFreePoolWithTag
0x140073314  nop     dword ptr [rax+rax+00h]
0x140073319  jmp     loc_140073204
0x14007331e  mov     edx, 73557348h; Tag
0x140073323  call    cs:__imp_ExFreePoolWithTag
0x14007332a  nop     dword ptr [rax+rax+00h]
0x14007332f  jmp     loc_140073238
0x140073334  mov     rcx, [rcx+18h]
0x140073338  mov     edx, 2Fh ; '/'
0x14007333d  mov     dword ptr [rsp+3F0h+ObjectAttributes], edi
0x140073341  mov     rax, [r15+10h]
0x140073345  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x14007334c  mov     r9, r13
0x14007334f  mov     [rsp+3F0h+BytesReturned], rax
0x140073354  call    WPP_SF_qqd
0x140073359  jmp     loc_140073204
0x14007335e  mov     rcx, cs:Filter; Filter
0x140073365  lea     rax, aSystemroot; "\\SystemRoot"
0x14007336c  lea     r8, [rbp+2F0h+RetVolume]; RetVolume
0x140073370  mov     [rbp+2F0h+var_2D8], rax
0x140073374  lea     rdx, [rbp+2F0h+P]; VolumeName
0x140073378  mov     [rbp+2F0h+P], 180016h
0x140073380  mov     [rbp+2F0h+RetVolume], 0
0x140073388  call    cs:__imp_FltGetVolumeFromName
0x14007338f  nop     dword ptr [rax+rax+00h]
0x140073394  mov     ecx, eax
0x140073396  mov     edi, eax
0x140073398  call    HsmDbgBreakOnStatus
0x14007339d  test    edi, edi
0x14007339f  jns     short loc_1400733D9
0x1400733a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400733a8  lea     rsi, WPP_GLOBAL_Control
0x1400733af  cmp     rcx, rsi
0x1400733b2  jz      loc_140073204
0x1400733b8  mov     edx, [rcx+2Ch]
0x1400733bb  mov     r14d, 1
0x1400733c1  test    r14b, dl
0x1400733c4  jz      loc_140073204
0x1400733ca  cmp     [rcx+29h], r12b
0x1400733ce  jb      loc_140073204
0x1400733d4  jmp     loc_140073334
0x1400733d9  mov     rcx, [rbp+2F0h+RetVolume]; FltObject
0x1400733dd  cmp     rcx, [r15+10h]
0x1400733e1  setz    [rbp+2F0h+var_368]
0x1400733e5  test    rcx, rcx
0x1400733e8  jz      loc_1400730ED
0x1400733ee  call    cs:__imp_FltObjectDereference
0x1400733f5  nop     dword ptr [rax+rax+00h]
0x1400733fa  jmp     loc_1400730ED
0x1400733ff  test    rsi, rsi
0x140073402  jz      short loc_140073418
0x140073404  mov     edx, 62547348h; Tag
0x140073409  mov     rcx, rsi; P
0x14007340c  call    cs:__imp_ExFreePoolWithTag
0x140073413  nop     dword ptr [rax+rax+00h]
0x140073418  mov     edx, [rbp+2F0h+LengthReturned]
0x14007341b  mov     ecx, 100h
0x140073420  mov     r8d, 62547348h
0x140073426  call    cs:__imp_ExAllocatePool2
0x14007342d  nop     dword ptr [rax+rax+00h]
0x140073432  mov     [rbp+2F0h+P], rax
0x140073436  mov     rsi, rax
0x140073439  test    rax, rax
0x14007343c  jz      short loc_14007344A
0x14007343e  mov     r9d, [rbp+2F0h+LengthReturned]
0x140073442  mov     rbx, rax
0x140073445  jmp     loc_140073102
0x14007344a  mov     eax, 0C000009Ah
0x14007344f  mov     ecx, eax
0x140073451  mov     edi, eax
0x140073453  call    HsmDbgBreakOnStatus
0x140073458  jmp     loc_140073204
0x14007345d  mov     rcx, cs:WPP_GLOBAL_Control
0x140073464  lea     rsi, WPP_GLOBAL_Control
0x14007346b  cmp     rcx, rsi
0x14007346e  jz      loc_14007438C
0x140073474  mov     eax, [rcx+2Ch]
0x140073477  test    r14b, al
0x14007347a  jz      loc_14007438C
0x140073480  cmp     [rcx+29h], r12b
0x140073484  jb      loc_14007438C
0x14007348a  mov     edx, 30h ; '0'
0x14007348f  mov     dword ptr [rsp+3F0h+ObjectAttributes], edi
0x140073493  jmp     loc_140074370
0x140073498  movzx   ecx, word ptr [rbx+0Ah]
0x14007349c  mov     r8, rax; Size
0x14007349f  mov     rdx, cs:stru_140029640.Buffer; Buf2
0x1400734a6  add     rcx, rbx; Buf1
0x1400734a9  call    memcmp
0x1400734ae  test    eax, eax
0x1400734b0  jnz     loc_140073155
0x1400734b6  movzx   eax, word ptr [rbx+4]
0x1400734ba  cmp     ax, cs:stru_140029630.Length
0x1400734c1  jnz     loc_140073155
0x1400734c7  movzx   ecx, word ptr [rbx+6]
0x1400734cb  mov     r8d, eax; Size
0x1400734ce  mov     rdx, cs:stru_140029630.Buffer; Buf2
0x1400734d5  add     rcx, rbx; Buf1
0x1400734d8  call    memcmp
  ... truncated ...
```
