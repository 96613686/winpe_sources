# PrjfInstanceSetup

- ea: `0x14003f240`
- end: `0x14003fdcc`
- name: `PrjfInstanceSetup`
- size: `2956`
- prototype: `__int64 __fastcall(struct _FLT_FILTER **, int, __int64, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400083b0`
- `0x140009aa4`
- `0x14000b1d0`
- `0x14000ba20`
- `0x14000bb80`
- `0x14000be80`
- `0x14000d008`
- `0x14000d128`
- `0x14000ef78`
- `0x1400130f8`
- `0x140013238`
- `0x14003f240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003f437`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f601`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f437`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f601`
- `ntoskrnl!RtlGUIDFromString` at `0x14003fb7c`
- `ntoskrnl!RtlGUIDFromString` at `0x14003fb7c`
- `ntoskrnl!ObfDereferenceObject` at `0x14003f44c`
- `ntoskrnl!ObfDereferenceObject` at `0x14003f44c`
- `ntoskrnl!ExAllocatePool2` at `0x14003f698`
- `ntoskrnl!ExAllocatePool2` at `0x14003f70e`
- `ntoskrnl!ExAllocatePool2` at `0x14003f77b`
- `ntoskrnl!ExAllocatePool2` at `0x14003f698`
- `ntoskrnl!ExAllocatePool2` at `0x14003f70e`
- `ntoskrnl!ExAllocatePool2` at `0x14003f77b`
- `ntoskrnl!ExInitializeResourceLite` at `0x14003f64e`
- `ntoskrnl!ExInitializeResourceLite` at `0x14003f64e`
- `FLTMGR!FltSetInstanceContext` at `0x14003fbf9`
- `FLTMGR!FltSetInstanceContext` at `0x14003fbf9`
- `FLTMGR!FltGetVolumeGuidName` at `0x14003faef`
- `FLTMGR!FltGetVolumeGuidName` at `0x14003faef`
- `FLTMGR!FltQueryVolumeInformationFile` at `0x14003fa58`
- `FLTMGR!FltQueryVolumeInformationFile` at `0x14003fa58`
- `FLTMGR!FltGetVolumeProperties` at `0x14003f758`
- `FLTMGR!FltGetVolumeProperties` at `0x14003f83e`
- `FLTMGR!FltGetVolumeProperties` at `0x14003f758`
- `FLTMGR!FltGetVolumeProperties` at `0x14003f83e`
- `FLTMGR!FltGetInstanceInformation` at `0x14003f671`
- `FLTMGR!FltGetInstanceInformation` at `0x14003f6cf`
- `FLTMGR!FltGetInstanceInformation` at `0x14003f671`
- `FLTMGR!FltGetInstanceInformation` at `0x14003f6cf`
- `FLTMGR!FltIsVolumeSnapshot` at `0x14003f38e`
- `FLTMGR!FltIsVolumeSnapshot` at `0x14003f38e`
- `FLTMGR!FltCreateFileEx` at `0x14003f9ca`
- `FLTMGR!FltCreateFileEx` at `0x14003f9ca`
- `FLTMGR!FltClose` at `0x14003f461`
- `FLTMGR!FltClose` at `0x14003f461`
- `FLTMGR!FltAllocateContext` at `0x14003f53b`
- `FLTMGR!FltAllocateContext` at `0x14003f53b`
- `FLTMGR!FltReleaseContext` at `0x14003f41e`
- `FLTMGR!FltReleaseContext` at `0x14003f41e`

## pseudocode

```c
__int64 __fastcall PrjfInstanceSetup(struct _FLT_FILTER **a1, int a2, __int64 a3, int a4)
{
  _WORD *Pool2; // r15
  struct _FLT_VOLUME_PROPERTIES *v8; // r14
  char v9; // dl
  char v10; // r8
  NTSTATUS IsVolumeSnapshot; // eax
  int v12; // edx
  int v13; // r8d
  NTSTATUS v14; // ebx
  struct _FLT_FILTER *v16; // rcx
  NTSTATUS v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  _UNKNOWN **v20; // rcx
  _QWORD *v21; // rax
  NTSTATUS InstanceInformation; // eax
  __int16 v23; // cx
  _QWORD *v24; // rbx
  NTSTATUS VolumeProperties; // eax
  NTSTATUS v26; // eax
  unsigned int AlignmentRequirement; // eax
  int SectorSize; // eax
  struct _FLT_INSTANCE *v29; // rdx
  NTSTATUS v30; // eax
  NTSTATUS v31; // eax
  struct _FLT_VOLUME *v32; // rcx
  NTSTATUS v33; // eax
  NTSTATUS v34; // eax
  NTSTATUS v35; // eax
  int ReturnedContext; // [rsp+20h] [rbp-E0h]
  int EaBuffer; // [rsp+60h] [rbp-A0h]
  unsigned __int8 IsSnapshotVolume[8]; // [rsp+80h] [rbp-80h] BYREF
  PFLT_CONTEXT Context; // [rsp+88h] [rbp-78h] BYREF
  ULONG LengthReturned; // [rsp+90h] [rbp-70h] BYREF
  ULONG BytesReturned; // [rsp+94h] [rbp-6Ch] BYREF
  int v42; // [rsp+98h] [rbp-68h]
  struct _UNICODE_STRING VolumeGuidName; // [rsp+A0h] [rbp-60h] BYREF
  ULONG v44; // [rsp+B0h] [rbp-50h] BYREF
  PVOID Object; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD *Buffer; // [rsp+C0h] [rbp-40h]
  HANDLE FileHandle; // [rsp+C8h] [rbp-38h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  __int128 FsInformation; // [rsp+110h] [rbp+10h] BYREF
  __int64 v51; // [rsp+120h] [rbp+20h]
  __int128 v52; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v53[22]; // [rsp+138h] [rbp+38h]
  char v54; // [rsp+150h] [rbp+50h] BYREF

  Pool2 = 0;
  Context = 0;
  FsInformation = 0;
  v51 = 0;
  v8 = 0;
  memset(&ObjectAttributes, 0, 44);
  LengthReturned = 0;
  IoStatusBlock = 0;
  Object = 0;
  FileHandle = 0;
  v52 = *(_OWORD *)L"Name Not Available";
  IsSnapshotVolume[0] = 0;
  *(_OWORD *)v53 = *(_OWORD *)L" Available";
  BytesReturned = 0;
  *(_QWORD *)&v53[14] = *(_QWORD *)L"ble";
  VolumeGuidName = 0;
  v44 = 0;
  v9 = BYTE8(xmmword_14001A3E0) & 0x10;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (v10 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
  {
    v10 = 0;
  }
  if ( v9 || v10 )
  {
    EaBuffer = a2;
    WPP_RECORDER_AND_TRACE_SF_sDlLD(1284, v9, v10, PrjfTraceRecorder, 5);
  }
  if ( ((a2 & 1) == 0 || a4 != 2 && a4 != 28 || !PrjfShouldAutoAttach(a1[3], a1[2]))
    && ((a2 & 2) == 0 || a4 != 2 && a4 != 28) )
  {
    goto LABEL_18;
  }
  IsVolumeSnapshot = FltIsVolumeSnapshot(a1[2], IsSnapshotVolume);
  if ( IsVolumeSnapshot < 0 )
  {
    if ( (xmmword_14001A3D0 & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = xmmword_14001A3D0 & 0x10;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        516,
        v12,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        4,
        11,
        (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
        121,
        IsVolumeSnapshot);
    }
LABEL_18:
    v14 = -1071906801;
    goto LABEL_19;
  }
  if ( IsSnapshotVolume[0] )
  {
    if ( (xmmword_14001A3E0 & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = xmmword_14001A3E0 & 0x10;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        1028,
        v12,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        4,
        4,
        12,
        (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
        128);
    }
    goto LABEL_18;
  }
  v16 = a1[1];
  LOWORD(v42) = 19;
  Buffer = &v52;
  v17 = FltAllocateContext(v16, 2u, 0xB0u, (POOL_TYPE)512, &Context);
  v14 = v17;
  if ( v17 < 0 )
  {
    v20 = &WPP_RECORDER_INITIALIZED;
    LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v18) = xmmword_14001A3D0 & 0x10;
    if ( (xmmword_14001A3D0 & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sDL(
        516,
        v18,
        v19,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        4,
        13,
        (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
        141,
        v17);
    goto LABEL_36;
  }
  memset(Context, 0, 0xB0u);
  *(_QWORD *)Context = a1[3];
  *((_DWORD *)Context + 6) = a4;
  v21 = (char *)Context + 152;
  *((_QWORD *)Context + 20) = (char *)Context + 152;
  *v21 = v21;
  ExInitializeResourceLite((PERESOURCE)((char *)Context + 48));
  InstanceInformation = FltGetInstanceInformation(a1[3], InstancePartialInformation, 0, 0, &BytesReturned);
  v14 = InstanceInformation;
  if ( InstanceInformation == -1073741789 )
  {
    Pool2 = (_WORD *)ExAllocatePool2(256, BytesReturned, 1952860752);
    if ( !Pool2 )
      goto LABEL_43;
    v14 = FltGetInstanceInformation(a1[3], InstancePartialInformation, Pool2, BytesReturned, &v44);
    if ( v14 < 0 )
      goto LABEL_36;
    v23 = Pool2[4];
    *((_WORD *)Context + 5) = v23;
    *((_WORD *)Context + 4) = v23;
    v24 = Context;
    v24[2] = ExAllocatePool2(256, (unsigned __int16)Pool2[4], 1667844688);
    v20 = (_UNKNOWN **)*((_QWORD *)Context + 2);
    if ( v20 )
    {
      memmove(v20, (char *)Pool2 + (unsigned __int16)Pool2[5], *((unsigned __int16 *)Context + 4));
      VolumeProperties = FltGetVolumeProperties(a1[2], 0, 0, &LengthReturned);
      v14 = VolumeProperties;
      if ( VolumeProperties == -1073741789 )
      {
        v8 = (struct _FLT_VOLUME_PROPERTIES *)ExAllocatePool2(256, LengthReturned, 1667844688);
        if ( !v8 )
        {
          v14 = -1073741670;
LABEL_50:
          v20 = &WPP_RECORDER_INITIALIZED;
          LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(v18) = xmmword_14001A3D0 & 0x10;
          if ( (xmmword_14001A3D0 & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_AND_TRACE_SF_sDL(
              516,
              v18,
              v19,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              4,
              14,
              (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
              239,
              v14);
          if ( v14 < 0 )
          {
            v42 = 19;
            goto LABEL_36;
          }
LABEL_40:
          ExFreePoolWithTag(Pool2, 0x74664A50u);
          goto LABEL_19;
        }
      }
      else if ( VolumeProperties < 0 )
      {
        goto LABEL_50;
      }
      v26 = FltGetVolumeProperties(a1[2], v8, LengthReturned, &LengthReturned);
      v14 = v26;
      if ( v26 < 0 )
      {
        v20 = &WPP_RECORDER_INITIALIZED;
        LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v18) = xmmword_14001A3D0 & 0x10;
        if ( (xmmword_14001A3D0 & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_sDL(
            516,
            v18,
            v19,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            4,
            15,
            (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
            250,
            v26);
        goto LABEL_36;
      }
      AlignmentRequirement = v8->AlignmentRequirement;
      if ( AlignmentRequirement == -1
        || ((AlignmentRequirement + 1) & AlignmentRequirement) != 0
        || AlignmentRequirement > 0x1FF )
      {
        v14 = -1073741438;
        v20 = &WPP_RECORDER_INITIALIZED;
        LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v18) = xmmword_14001A3D0 & 0x10;
        if ( (xmmword_14001A3D0 & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_sDDd(
            516,
            v18,
            v19,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            4,
            16,
            (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
            12,
            AlignmentRequirement,
            -1073741438,
            EaBuffer);
      }
      else
      {
        SectorSize = v8->SectorSize;
        if ( !(_WORD)SectorSize || ((SectorSize - 1) & SectorSize) != 0 )
        {
          v14 = -1073741438;
          v20 = &WPP_RECORDER_INITIALIZED;
          LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(v18) = xmmword_14001A3D0 & 0x10;
          if ( (xmmword_14001A3D0 & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_AND_TRACE_SF_sDDd(
              516,
              v18,
              v19,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              4,
              17,
              (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
              27,
              SectorSize,
              -1073741438,
              EaBuffer);
        }
        else
        {
          if ( ((SectorSize - 1) & 0x100000) == 0 )
          {
            v29 = a1[3];
            Buffer = v8->RealDeviceName.Buffer;
            LOWORD(v42) = v8->RealDeviceName.Length >> 1;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.ObjectName = &v8->RealDeviceName;
            ObjectAttributes.Length = 48;
            ObjectAttributes.Attributes = 576;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v30 = FltCreateFileEx(
                    Globals,
                    v29,
                    &FileHandle,
                    (PFILE_OBJECT *)&Object,
                    0x180u,
                    &ObjectAttributes,
                    &IoStatusBlock,
                    0,
                    0,
                    7u,
                    1u,
                    0x20u,
                    0,
                    0,
                    0);
            v14 = v30;
            if ( v30 >= 0 )
            {
              v31 = FltQueryVolumeInformationFile(
                      a1[3],
                      (PFILE_OBJECT)Object,
                      &FsInformation,
                      0x18u,
                      FileFsSizeInformation,
                      0);
              v14 = v31;
              if ( v31 >= 0 )
              {
                *((_DWORD *)Context + 7) = HIDWORD(v51) * v51;
                v32 = a1[2];
                VolumeGuidName.Buffer = (PWSTR)&v54;
                *(_DWORD *)&VolumeGuidName.Length = 6422528;
                v33 = FltGetVolumeGuidName(v32, &VolumeGuidName, &LengthReturned);
                v14 = v33;
                if ( v33 >= 0 )
                {
                  VolumeGuidName.Buffer += 10;
                  VolumeGuidName.Length -= 20;
                  v34 = RtlGUIDFromString(&VolumeGuidName, (GUID *)Context + 2);
                  v14 = v34;
                  if ( v34 >= 0 )
                  {
                    v35 = FltSetInstanceContext(a1[3], FLT_SET_CONTEXT_KEEP_IF_EXISTS, Context, 0);
                    v14 = v35;
                    if ( v35 >= 0 )
                    {
                      if ( (xmmword_14001A3E0 & 0x10) != 0
                        || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      {
                        WPP_RECORDER_AND_TRACE_SF_sDlLD(
                          1028,
                          xmmword_14001A3E0 & 0x10,
                          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
                          *((_QWORD *)WPP_GLOBAL_Control + 8),
                          4);
                      }
                      v14 = 0;
                      goto LABEL_40;
                    }
                    v20 = &WPP_RECORDER_INITIALIZED;
                    LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                    LOBYTE(v18) = xmmword_14001A3D0 & 0x10;
                    if ( (xmmword_14001A3D0 & 0x10) != 0
                      || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      WPP_RECORDER_AND_TRACE_SF_sDL(
                        516,
                        v18,
                        v19,
                        *((_QWORD *)WPP_GLOBAL_Control + 8),
                        2,
                        4,
                        23,
                        (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
                        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
                        132,
                        v35);
                    }
                  }
                  else
                  {
                    v20 = &WPP_RECORDER_INITIALIZED;
                    LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                    LOBYTE(v18) = xmmword_14001A3D0 & 0x10;
                    if ( (xmmword_14001A3D0 & 0x10) != 0
                      || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      WPP_RECORDER_AND_TRACE_SF_sDL(
                        516,
                        v18,
                        v19,
                        *((_QWORD *)WPP_GLOBAL_Control + 8),
                        2,
                        4,
                        22,
                        (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
                        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
                        120,
                        v34);
                    }
                  }
                }
                else
                {
                  v20 = &WPP_RECORDER_INITIALIZED;
                  LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                  LOBYTE(v18) = xmmword_14001A3D0 & 0x10;
                  if ( (xmmword_14001A3D0 & 0x10) != 0
                    || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    WPP_RECORDER_AND_TRACE_SF_sDL(
                      516,
                      v18,
                      v19,
                      *((_QWORD *)WPP_GLOBAL_Control + 8),
                      2,
                      4,
                      21,
                      (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
                      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
                      109,
                      v33);
                  }
                }
              }
              else
              {
                v20 = &WPP_RECORDER_INITIALIZED;
                LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                LOBYTE(v18) = xmmword_14001A3D0 & 0x10;
                if ( (xmmword_14001A3D0 & 0x10) != 0
                  || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  WPP_RECORDER_AND_TRACE_SF_sDL(
                    516,
                    v18,
                    v19,
                    *((_QWORD *)WPP_GLOBAL_Control + 8),
                    2,
                    4,
                    20,
                    (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
                    (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
                    95,
                    v31);
                }
              }
            }
            else
            {
              v20 = &WPP_RECORDER_INITIALIZED;
              LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              LOBYTE(v18) = xmmword_14001A3D0 & 0x10;
              if ( (xmmword_14001A3D0 & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_AND_TRACE_SF_sDL(
                  516,
                  v18,
                  v19,
                  *((_QWORD *)WPP_GLOBAL_Control + 8),
                  2,
                  4,
                  19,
                  (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
                  (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
                  82,
                  v30);
            }
LABEL_36:
            if ( v14 == -1071906801 )
              goto LABEL_39;
            goto LABEL_37;
          }
          v14 = -1073741438;
          v20 = &WPP_RECORDER_INITIALIZED;
          LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(v18) = xmmword_14001A3D0 & 0x10;
          if ( (xmmword_14001A3D0 & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_AND_TRACE_SF_sDLLd(
              (unsigned int)&WPP_RECORDER_INITIALIZED,
              v18,
              v19,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              ReturnedContext);
        }
      }
    }
    else
    {
LABEL_43:
      v14 = -1073741670;
    }
LABEL_37:
    if ( (Microsoft_Windows_ProjFS_FilterEnableBits & 1) != 0 )
      McTemplateK0dhzr1_EtwWriteTransfer((_DWORD)v20, v18, v19, v14, v42, (__int64)Buffer);
LABEL_39:
    if ( !Pool2 )
      goto LABEL_19;
    goto LABEL_40;
  }
  if ( InstanceInformation < 0 )
    goto LABEL_36;
  MicrosoftTelemetryAssertTriggeredNoArgsKM(v20, v18, v19);
LABEL_19:
  if ( Context )
    FltReleaseContext(Context);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x63694A50u);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14003f240  push    rbp
0x14003f242  push    rbx
0x14003f243  push    rsi
0x14003f244  push    rdi
0x14003f245  push    r12
0x14003f247  push    r13
0x14003f249  push    r14
0x14003f24b  push    r15
0x14003f24d  lea     rbp, [rsp-0D8h]
0x14003f255  sub     rsp, 1D8h
0x14003f25c  mov     rax, cs:__security_cookie
0x14003f263  xor     rax, rsp
0x14003f266  mov     [rbp+110h+var_50], rax
0x14003f26d  movups  xmm1, xmmword ptr cs:aNameNotAvailab; "Name Not Available"
0x14003f274  xor     r15d, r15d
0x14003f277  mov     esi, r9d
0x14003f27a  xorps   xmm0, xmm0
0x14003f27d  mov     [rbp+110h+Context], r15
0x14003f281  movups  xmmword ptr [rbp+110h+var_140.ObjectName], xmm0
0x14003f285  xor     eax, eax
0x14003f287  mov     r13d, r8d
0x14003f28a  movups  xmmword ptr [rbp+110h+var_140+1Ch], xmm0
0x14003f28e  mov     r12d, edx
0x14003f291  mov     rdi, rcx
0x14003f294  movups  [rbp+110h+FsInformation], xmm0
0x14003f298  mov     [rbp+110h+var_F0], rax
0x14003f29c  mov     r14d, r15d
0x14003f29f  movups  xmmword ptr [rbp+110h+var_140.Length], xmm0
0x14003f2a3  mov     [rbp+110h+LengthReturned], r15d
0x14003f2a7  movups  xmmword ptr [rbp+110h+var_110], xmm0
0x14003f2ab  mov     [rbp+110h+Object], r15
0x14003f2af  movups  xmm0, xmmword ptr cs:aNameNotAvailab+10h; " Available"
0x14003f2b6  mov     [rbp+110h+FileHandle], r15
0x14003f2ba  movups  [rbp+110h+var_E8], xmm1
0x14003f2be  mov     [rbp+110h+IsSnapshotVolume], r15b
0x14003f2c2  movsd   xmm1, qword ptr cs:aNameNotAvailab+1Eh; "ble"
0x14003f2ca  movups  xmmword ptr [rbp+110h+var_D8], xmm0
0x14003f2ce  mov     [rbp+110h+BytesReturned], r15d
0x14003f2d2  xorps   xmm0, xmm0
0x14003f2d5  movsd   qword ptr [rbp+110h+var_D8+0Eh], xmm1
0x14003f2da  movups  xmmword ptr [rbp+110h+VolumeGuidName.Length], xmm0
0x14003f2de  mov     [rbp+110h+var_160], r15d
0x14003f2e2  mov     dl, byte ptr cs:xmmword_14001A3E0+8
0x14003f2e8  lea     ebx, [rax+10h]
0x14003f2eb  and     dl, bl
0x14003f2ed  lea     rax, WPP_RECORDER_INITIALIZED
0x14003f2f4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003f2fb  jz      short loc_14003F30E
0x14003f2fd  mov     rax, cs:WPP_GLOBAL_Control
0x14003f304  mov     r8b, 1
0x14003f307  cmp     [rax+48h], r15w
0x14003f30c  jnz     short loc_14003F311
0x14003f30e  mov     r8b, r15b
0x14003f311  test    dl, dl
0x14003f313  jnz     short loc_14003F31A
0x14003f315  test    r8b, r8b
0x14003f318  jz      short loc_14003F34D
0x14003f31a  mov     r9, cs:_PrjfTraceRecorder
0x14003f321  mov     ecx, 504h
0x14003f326  mov     dword ptr [rsp+210h+EaBuffer], r12d
0x14003f32b  mov     [rsp+210h+CreateOptions], esi
0x14003f32f  mov     [rsp+210h+CreateDisposition], r13d
0x14003f334  mov     [rsp+210h+ShareAccess], 16Ah
0x14003f33c  mov     word ptr [rsp+210h+IoStatusBlock], 0Ah
0x14003f343  mov     byte ptr [rsp+210h+ReturnedContext], 5
0x14003f348  call    WPP_RECORDER_AND_TRACE_SF_sDlLD
0x14003f34d  test    r12b, 1
0x14003f351  jz      short loc_14003F36E
0x14003f353  cmp     esi, 2
0x14003f356  jz      short loc_14003F35D
0x14003f358  cmp     esi, 1Ch
0x14003f35b  jnz     short loc_14003F36E
0x14003f35d  mov     rdx, [rdi+10h]; Volume
0x14003f361  mov     rcx, [rdi+18h]; Instance
0x14003f365  call    PrjfShouldAutoAttach
0x14003f36a  test    al, al
0x14003f36c  jnz     short loc_14003F386
0x14003f36e  test    r12b, 2
0x14003f372  jz      loc_14003F410
0x14003f378  cmp     esi, 2
0x14003f37b  jz      short loc_14003F386
0x14003f37d  cmp     esi, 1Ch
0x14003f380  jnz     loc_14003F410
0x14003f386  mov     rcx, [rdi+10h]; FltObject
0x14003f38a  lea     rdx, [rbp+110h+IsSnapshotVolume]; IsSnapshotVolume
0x14003f38e  call    cs:__imp_FltIsVolumeSnapshot
0x14003f395  nop     dword ptr [rax+rax+00h]
0x14003f39a  test    eax, eax
0x14003f39c  jns     loc_14003F493
0x14003f3a2  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003f3a8  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003f3af  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003f3b6  setnz   r8b
0x14003f3ba  and     dl, bl
0x14003f3bc  jnz     short loc_14003F3C3
0x14003f3be  test    r8b, r8b
0x14003f3c1  jz      short loc_14003F410
0x14003f3c3  mov     r9, cs:WPP_GLOBAL_Control
0x14003f3ca  mov     ecx, 204h
0x14003f3cf  mov     [rsp+210h+CreateDisposition], eax
0x14003f3d3  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003f3da  mov     [rsp+210h+ShareAccess], 179h
0x14003f3e2  mov     qword ptr [rsp+210h+FileAttributes], rax
0x14003f3e7  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x14003f3ee  mov     r9, [r9+40h]
0x14003f3f2  mov     [rsp+210h+AllocationSize], rax
0x14003f3f7  mov     word ptr [rsp+210h+IoStatusBlock], 0Bh
0x14003f3fe  mov     dword ptr [rsp+210h+ObjectAttributes], 4
0x14003f406  mov     byte ptr [rsp+210h+ReturnedContext], 2
0x14003f40b  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003f410  mov     ebx, 0C01C000Fh
0x14003f415  mov     rcx, [rbp+110h+Context]; Context
0x14003f419  test    rcx, rcx
0x14003f41c  jz      short loc_14003F42A
0x14003f41e  call    cs:__imp_FltReleaseContext
0x14003f425  nop     dword ptr [rax+rax+00h]
0x14003f42a  test    r14, r14
0x14003f42d  jz      short loc_14003F443
0x14003f42f  mov     edx, 63694A50h; Tag
0x14003f434  mov     rcx, r14; P
0x14003f437  call    cs:__imp_ExFreePoolWithTag
0x14003f43e  nop     dword ptr [rax+rax+00h]
0x14003f443  mov     rcx, [rbp+110h+Object]; Object
0x14003f447  test    rcx, rcx
0x14003f44a  jz      short loc_14003F458
0x14003f44c  call    cs:__imp_ObfDereferenceObject
0x14003f453  nop     dword ptr [rax+rax+00h]
0x14003f458  mov     rcx, [rbp+110h+FileHandle]; FileHandle
0x14003f45c  test    rcx, rcx
0x14003f45f  jz      short loc_14003F46D
0x14003f461  call    cs:__imp_FltClose
0x14003f468  nop     dword ptr [rax+rax+00h]
0x14003f46d  mov     eax, ebx
0x14003f46f  mov     rcx, [rbp+110h+var_50]
0x14003f476  xor     rcx, rsp; StackCookie
0x14003f479  call    __security_check_cookie
0x14003f47e  add     rsp, 1D8h
0x14003f485  pop     r15
0x14003f487  pop     r14
0x14003f489  pop     r13
0x14003f48b  pop     r12
0x14003f48d  pop     rdi
0x14003f48e  pop     rsi
0x14003f48f  pop     rbx
0x14003f490  pop     rbp
0x14003f491  retn
0x14003f493  cmp     [rbp+110h+IsSnapshotVolume], r15b
0x14003f497  jz      short loc_14003F50C
0x14003f499  mov     dl, byte ptr cs:xmmword_14001A3E0
0x14003f49f  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003f4a6  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003f4ad  setnz   r8b
0x14003f4b1  and     dl, bl
0x14003f4b3  jnz     short loc_14003F4BE
0x14003f4b5  test    r8b, r8b
0x14003f4b8  jz      loc_14003F410
0x14003f4be  mov     r9, cs:WPP_GLOBAL_Control
0x14003f4c5  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003f4cc  mov     [rsp+210h+ShareAccess], 180h
0x14003f4d4  mov     ecx, 404h
0x14003f4d9  mov     qword ptr [rsp+210h+FileAttributes], rax
0x14003f4de  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x14003f4e5  mov     [rsp+210h+AllocationSize], rax
0x14003f4ea  mov     r9, [r9+40h]
0x14003f4ee  mov     word ptr [rsp+210h+IoStatusBlock], 0Ch
0x14003f4f5  mov     dword ptr [rsp+210h+ObjectAttributes], 4
0x14003f4fd  mov     byte ptr [rsp+210h+ReturnedContext], 4
0x14003f502  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14003f507  jmp     loc_14003F410
0x14003f50c  mov     rcx, [rdi+8]; Filter
0x14003f510  mov     eax, 13h
0x14003f515  mov     word ptr [rbp+110h+var_178], ax
0x14003f519  mov     edx, 2; ContextType
0x14003f51e  lea     rax, [rbp+110h+var_E8]
0x14003f522  mov     r9d, 200h; PoolType
0x14003f528  mov     [rbp+110h+var_150], rax
0x14003f52c  mov     r8d, 0B0h; ContextSize
0x14003f532  lea     rax, [rbp+110h+Context]
0x14003f536  mov     [rsp+210h+ReturnedContext], rax; ReturnedContext
0x14003f53b  call    cs:__imp_FltAllocateContext
0x14003f542  nop     dword ptr [rax+rax+00h]
0x14003f547  mov     ebx, eax
0x14003f549  test    eax, eax
0x14003f54b  jns     loc_14003F612
0x14003f551  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003f557  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003f55e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003f565  mov     r10d, 10h
0x14003f56b  setnz   r8b
0x14003f56f  and     dl, r10b
0x14003f572  jnz     short loc_14003F579
0x14003f574  test    r8b, r8b
0x14003f577  jz      short loc_14003F5C6
0x14003f579  mov     [rsp+210h+CreateDisposition], eax
0x14003f57d  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003f584  mov     [rsp+210h+ShareAccess], 18Dh
0x14003f58c  mov     qword ptr [rsp+210h+FileAttributes], rax
0x14003f591  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x14003f598  mov     [rsp+210h+AllocationSize], rax
0x14003f59d  mov     word ptr [rsp+210h+IoStatusBlock], 0Dh
0x14003f5a4  mov     r9, cs:WPP_GLOBAL_Control
0x14003f5ab  mov     ecx, 204h
0x14003f5b0  mov     dword ptr [rsp+210h+ObjectAttributes], 4
0x14003f5b8  mov     byte ptr [rsp+210h+ReturnedContext], 2
0x14003f5bd  mov     r9, [r9+40h]
0x14003f5c1  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003f5c6  cmp     ebx, 0C01C000Fh
0x14003f5cc  jz      short loc_14003F5F0
0x14003f5ce  test    cs:Microsoft_Windows_ProjFS_FilterEnableBits, 1
0x14003f5d5  jz      short loc_14003F5F0
0x14003f5d7  mov     rax, [rbp+110h+var_150]
0x14003f5db  mov     r9d, ebx
0x14003f5de  mov     [rsp+210h+ObjectAttributes], rax
0x14003f5e3  mov     eax, [rbp+110h+var_178]
0x14003f5e6  mov     word ptr [rsp+210h+ReturnedContext], ax
0x14003f5eb  call    McTemplateK0dhzr1_EtwWriteTransfer
0x14003f5f0  test    r15, r15
0x14003f5f3  jz      loc_14003F415
0x14003f5f9  mov     edx, 74664A50h; Tag
0x14003f5fe  mov     rcx, r15; P
0x14003f601  call    cs:__imp_ExFreePoolWithTag
0x14003f608  nop     dword ptr [rax+rax+00h]
0x14003f60d  jmp     loc_14003F415
0x14003f612  mov     rcx, [rbp+110h+Context]; void *
0x14003f616  xor     edx, edx; Val
0x14003f618  mov     r8d, 0B0h; Size
0x14003f61e  call    memset
0x14003f623  mov     rax, [rbp+110h+Context]
0x14003f627  mov     rcx, [rdi+18h]
0x14003f62b  mov     [rax], rcx
0x14003f62e  mov     rax, [rbp+110h+Context]
0x14003f632  mov     [rax+18h], esi
0x14003f635  mov     rax, [rbp+110h+Context]
0x14003f639  add     rax, 98h
0x14003f63f  mov     [rax+8], rax
0x14003f643  mov     [rax], rax
0x14003f646  mov     rcx, [rbp+110h+Context]
0x14003f64a  add     rcx, 30h ; '0'; Resource
0x14003f64e  call    cs:__imp_ExInitializeResourceLite
0x14003f655  nop     dword ptr [rax+rax+00h]
0x14003f65a  mov     rcx, [rdi+18h]; Instance
0x14003f65e  lea     rax, [rbp+110h+BytesReturned]
0x14003f662  xor     r9d, r9d; BufferSize
0x14003f665  mov     [rsp+210h+ReturnedContext], rax; BytesReturned
0x14003f66a  xor     r8d, r8d; Buffer
0x14003f66d  lea     edx, [r9+1]; InformationClass
0x14003f671  call    cs:__imp_FltGetInstanceInformation
0x14003f678  nop     dword ptr [rax+rax+00h]
0x14003f67d  mov     ebx, eax
0x14003f67f  cmp     eax, 0C0000023h
0x14003f684  jnz     loc_14003FDBA
0x14003f68a  mov     edx, [rbp+110h+BytesReturned]
0x14003f68d  mov     ecx, 100h
0x14003f692  mov     r8d, 74664A50h
0x14003f698  call    cs:__imp_ExAllocatePool2
0x14003f69f  nop     dword ptr [rax+rax+00h]
0x14003f6a4  mov     r15, rax
0x14003f6a7  test    rax, rax
0x14003f6aa  jnz     short loc_14003F6B6
0x14003f6ac  mov     ebx, 0C000009Ah
0x14003f6b1  jmp     loc_14003F5CE
0x14003f6b6  mov     r9d, [rbp+110h+BytesReturned]; BufferSize
0x14003f6ba  lea     rax, [rbp+110h+var_160]
0x14003f6be  mov     rcx, [rdi+18h]; Instance
0x14003f6c2  mov     r8, r15; Buffer
0x14003f6c5  mov     edx, 1; InformationClass
0x14003f6ca  mov     [rsp+210h+ReturnedContext], rax; BytesReturned
0x14003f6cf  call    cs:__imp_FltGetInstanceInformation
0x14003f6d6  nop     dword ptr [rax+rax+00h]
0x14003f6db  mov     ebx, eax
0x14003f6dd  test    eax, eax
0x14003f6df  js      loc_14003F5C6
0x14003f6e5  mov     rax, [rbp+110h+Context]
0x14003f6e9  mov     r8d, 63694A50h
0x14003f6ef  movzx   ecx, word ptr [r15+8]
0x14003f6f4  mov     [rax+0Ah], cx
0x14003f6f8  mov     rax, [rbp+110h+Context]
0x14003f6fc  mov     [rax+8], cx
0x14003f700  mov     ecx, 100h
0x14003f705  movzx   edx, word ptr [r15+8]
0x14003f70a  mov     rbx, [rbp+110h+Context]
0x14003f70e  call    cs:__imp_ExAllocatePool2
0x14003f715  nop     dword ptr [rax+rax+00h]
0x14003f71a  mov     [rbx+10h], rax
0x14003f71e  mov     rax, [rbp+110h+Context]
0x14003f722  mov     rcx, [rax+10h]; void *
0x14003f726  test    rcx, rcx
0x14003f729  jz      short loc_14003F6AC
0x14003f72b  movzx   edx, word ptr [r15+0Ah]
0x14003f730  movzx   r8d, word ptr [rax+8]; Size
0x14003f735  add     rdx, r15; Src
0x14003f738  call    memmove
0x14003f73d  cmp     esi, 2
0x14003f740  jz      short loc_14003F74B
0x14003f742  cmp     esi, 1Ch
0x14003f745  jnz     loc_14003FBEA
0x14003f74b  mov     rcx, [rdi+10h]; Volume
0x14003f74f  lea     r9, [rbp+110h+LengthReturned]; LengthReturned
0x14003f753  xor     r8d, r8d; VolumePropertiesLength
0x14003f756  xor     edx, edx; VolumeProperties
  ... truncated ...
```
