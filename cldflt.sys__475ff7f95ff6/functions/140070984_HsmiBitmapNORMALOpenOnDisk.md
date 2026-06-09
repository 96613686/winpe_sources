# HsmiBitmapNORMALOpenOnDisk

- ea: `0x140070984`
- end: `0x140071cd0`
- name: `HsmiBitmapNORMALOpenOnDisk`
- size: `4940`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140009180`

## callees

- `0x140003c50`
- `0x140005e84`
- `0x140009c7c`
- `0x140009d14`
- `0x14000a120`
- `0x14000d908`
- `0x14000d95c`
- `0x1400188ec`
- `0x140018be0`
- `0x140018e00`
- `0x140018f10`
- `0x140019110`
- `0x1400191fc`
- `0x140019774`
- `0x140019e8c`
- `0x14001a9b0`
- `0x14001b4ac`
- `0x14001b610`
- `0x14001b8dc`
- `0x14001c5d4`
- `0x14001e1c0`
- `0x140036400`
- `0x140044b94`
- `0x140044c68`
- `0x140070984`
- `0x14007255c`
- `0x14007300c`
- `0x14007e468`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x140071a82`
- `ntoskrnl!RtlComputeCrc32` at `0x140071a82`
- `ntoskrnl!ObfDereferenceObject` at `0x140071c39`
- `ntoskrnl!ObfDereferenceObject` at `0x140071c71`
- `ntoskrnl!ObfDereferenceObject` at `0x140071c39`
- `ntoskrnl!ObfDereferenceObject` at `0x140071c71`
- `ntoskrnl!ExAllocatePool2` at `0x140071098`
- `ntoskrnl!ExAllocatePool2` at `0x140071098`
- `FLTMGR!FltSetInformationFile` at `0x14007170b`
- `FLTMGR!FltSetInformationFile` at `0x14007170b`
- `FLTMGR!FltClose` at `0x1400712ad`
- `FLTMGR!FltClose` at `0x1400713e8`
- `FLTMGR!FltClose` at `0x140071bef`
- `FLTMGR!FltClose` at `0x1400712ad`
- `FLTMGR!FltClose` at `0x1400713e8`
- `FLTMGR!FltClose` at `0x140071bef`
- `FLTMGR!FltQueryInformationFile` at `0x140071671`
- `FLTMGR!FltQueryInformationFile` at `0x140071671`
- `FLTMGR!FltFsControlFile` at `0x1400713ba`
- `FLTMGR!FltFsControlFile` at `0x1400713ba`
- `FLTMGR!FltReleasePushLockEx` at `0x140070a66`
- `FLTMGR!FltReleasePushLockEx` at `0x140070a66`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140070a19`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140070a19`

## string_xrefs

- `0x140071455`: `create`
- `0x140071264`: `Created`
- `0x14007125d`: `Opened`

## pseudocode

```c
__int64 __fastcall HsmiBitmapNORMALOpenOnDisk(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // r14d
  __int64 v5; // r13
  int FileObject; // ebx
  __int64 v8; // r15
  unsigned int v9; // r8d
  __int64 *v11; // r11
  unsigned int *v12; // rdx
  unsigned int v13; // ecx
  __int64 v14; // rax
  int v15; // r13d
  struct _FILE_OBJECT *v16; // rcx
  void *v17; // rcx
  unsigned int v18; // edx
  __int64 v19; // rbx
  PUCHAR v20; // rcx
  __int64 v21; // rcx
  __int64 Pool2; // rax
  unsigned int v23; // r14d
  __int64 v24; // rcx
  _QWORD *v25; // r10
  __int64 v26; // r9
  unsigned int i; // r8d
  signed __int64 v28; // rcx
  int v29; // r8d
  const char *v30; // r9
  unsigned int j; // r14d
  __int64 v32; // rcx
  PDEVICE_OBJECT v33; // rcx
  const char *v34; // r9
  PDEVICE_OBJECT v35; // rcx
  int v36; // edx
  int v37; // edx
  __int64 v38; // rax
  int v39; // r9d
  unsigned int v40; // r14d
  __int64 v41; // r10
  unsigned int k; // r9d
  signed __int64 v43; // r8
  signed __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rcx
  PDEVICE_OBJECT v48; // rcx
  int v49; // edx
  int v50; // edx
  PUCHAR v51; // rbx
  __int64 v52; // r15
  void *v53; // rcx
  unsigned int v54; // eax
  int InputBufferLength; // [rsp+20h] [rbp-168h]
  __int64 OutputBufferLength; // [rsp+30h] [rbp-158h]
  int v57; // [rsp+40h] [rbp-148h]
  int v58; // [rsp+60h] [rbp-128h]
  int v59; // [rsp+60h] [rbp-128h]
  int v60; // [rsp+64h] [rbp-124h]
  char v61[8]; // [rsp+68h] [rbp-120h] BYREF
  PUCHAR Buffer; // [rsp+70h] [rbp-118h] BYREF
  unsigned int v63; // [rsp+78h] [rbp-110h]
  __int64 v64; // [rsp+80h] [rbp-108h] BYREF
  unsigned int v65; // [rsp+88h] [rbp-100h]
  __int64 *v66; // [rsp+90h] [rbp-F8h]
  int v67; // [rsp+98h] [rbp-F0h]
  int v68[2]; // [rsp+A0h] [rbp-E8h]
  HANDLE FileHandle; // [rsp+A8h] [rbp-E0h] BYREF
  PVOID v70[2]; // [rsp+B0h] [rbp-D8h] BYREF
  unsigned int *v71; // [rsp+C0h] [rbp-C8h]
  __int64 v72; // [rsp+C8h] [rbp-C0h]
  __int64 v73; // [rsp+D0h] [rbp-B8h]
  __int64 v74; // [rsp+D8h] [rbp-B0h]
  __int64 v75; // [rsp+E0h] [rbp-A8h]
  __int128 v76; // [rsp+F0h] [rbp-98h] BYREF
  __int64 v77; // [rsp+100h] [rbp-88h]
  __int128 InputBuffer; // [rsp+108h] [rbp-80h] BYREF
  __int64 v79; // [rsp+118h] [rbp-70h]
  __int128 FileInformation; // [rsp+120h] [rbp-68h] BYREF
  __int64 v81; // [rsp+130h] [rbp-58h]

  v74 = a4;
  v63 = a3;
  v4 = a2;
  v5 = a1;
  v73 = a1;
  v75 = a1;
  v72 = a1;
  FileObject = 0;
  v8 = 0;
  v60 = 0;
  FileHandle = 0;
  Buffer = 0;
  v70[0] = 0;
  v70[1] = 0;
  v77 = a1 + 48;
  FltAcquirePushLockExclusiveEx(a1 + 48, 0);
  if ( !v4 )
    goto LABEL_2;
  v11 = (__int64 *)(v5 + 160);
  v66 = (__int64 *)(v5 + 160);
  if ( !*(_QWORD *)(v5 + 160) )
  {
    Pool2 = ExAllocatePool2(256, 40, 1698853704);
    v11 = v66;
    *v66 = Pool2;
    if ( !Pool2 )
    {
      FileObject = -1073741670;
      HsmDbgBreakOnStatus(-1073741670);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qisd(WPP_GLOBAL_Control->AttachedDevice, 62, v9, v5, *(_QWORD *)v5, v5 + 32, 154);
      }
      goto LABEL_2;
    }
  }
  v12 = (unsigned int *)(v5 + 16);
  v71 = (unsigned int *)(v5 + 16);
  v13 = *(_DWORD *)(v5 + 16);
  if ( (v13 & 8) != 0 )
  {
    v8 = (v13 >> 12) & 7;
    v60 = v8;
    v67 = (v13 >> 12) & 7;
    if ( (_DWORD)v8 == v4 )
      goto LABEL_2;
    v61[1] = 0;
  }
  else
  {
    v60 = 0;
    v67 = 0;
    v61[1] = 1;
  }
  *(_QWORD *)&v76 = v5 + 16;
  *(_QWORD *)v68 = *(_QWORD *)(v5 + 40);
  v9 = 1 << ((v13 >> 6) & 0x3F);
  v65 = v9;
  while ( (unsigned int)v8 < v4 )
  {
    v23 = (*v12 >> 12) & 7;
    LODWORD(v64) = v23;
    v61[0] = (unsigned int)v8 >= v23;
    v24 = (unsigned int)v8;
    v25 = (_QWORD *)(*v11 + 8 * v8);
    if ( !*v25 )
    {
      v26 = (v9 + v74 - 1) / v9;
      for ( i = 0; i < a2; ++i )
      {
        if ( i >= (unsigned int)v8 )
          break;
        v28 = (-(__int64)(i != 0) & 0xFFFFFFFFFFFFC010uLL) + 32736;
        v26 = (v28 + v26 - 1) / v28;
      }
      *(_QWORD *)&FileInformation = ((__int64)(v26 + (-(__int64)((_DWORD)v8 != 0) & 0xFFFFFFFFFFFFC010uLL) + 32735)
                                   / (__int64)((-(__int64)((_DWORD)v8 != 0) & 0xFFFFFFFFFFFFC010uLL) + 32736)
                                   + 1) << 13;
      FileObject = HsmiBitmapNormalOpenStream(
                     v68[0],
                     *(_QWORD *)v5,
                     v61[0],
                     0,
                     (PLARGE_INTEGER)&FileInformation,
                     (__int64)&FileHandle,
                     (__int64)v25);
      HsmDbgBreakOnStatus(FileObject);
      if ( FileObject < 0 )
      {
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v34 = "create";
          if ( (unsigned int)v8 < (unsigned int)v64 )
            v34 = "open";
          WPP_SF_sqisdd(
            WPP_GLOBAL_Control->AttachedDevice,
            63,
            v29,
            (_DWORD)v34,
            v5,
            *(_QWORD *)v5,
            v5 + 32,
            v8,
            FileObject);
        }
        goto LABEL_109;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        v30 = "Created";
        if ( (unsigned int)v8 < v23 )
          v30 = "Opened";
        WPP_SF_sqisdd(
          WPP_GLOBAL_Control->AttachedDevice,
          64,
          v29,
          (_DWORD)v30,
          v5,
          *(_QWORD *)v5,
          v5 + 32,
          (*v71 >> 12) & 7,
          v8);
      }
      if ( FileHandle )
      {
        FltClose(FileHandle);
        FileHandle = 0;
      }
      v24 = (unsigned int)v8;
      v11 = v66;
    }
    for ( j = 0; j < v63; ++j )
    {
      InputBuffer = 0;
      v79 = 0;
      v32 = j + 3 * v24;
      *(_QWORD *)&FileInformation = v32;
      if ( !*(_QWORD *)(*v11 + 8 * (v32 + 2)) )
      {
        FileObject = HsmiBitmapNormalOpenStream(
                       v68[0],
                       *(_QWORD *)v5,
                       0,
                       1,
                       0,
                       (__int64)&FileHandle,
                       *v11 + 8 * (v32 + 2));
        HsmDbgBreakOnStatus(FileObject);
        if ( FileObject < 0 )
        {
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_109;
          }
          v37 = 65;
          goto LABEL_119;
        }
        LODWORD(v79) = 128;
        LODWORD(InputBuffer) = j;
        FileObject = FltFsControlFile(
                       *(PFLT_INSTANCE *)(*(_QWORD *)v68 + 32LL),
                       *(PFILE_OBJECT *)(*v66 + 8 * FileInformation + 16),
                       0x900FCu,
                       &InputBuffer,
                       0x18u,
                       0,
                       0,
                       0);
        HsmDbgBreakOnStatus(FileObject);
        if ( FileObject < 0 )
        {
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_73;
          }
          v36 = 66;
LABEL_114:
          WPP_SF_qisdd(v35->AttachedDevice, v36, v9, v5, *(_QWORD *)v5, v5 + 32, v8, FileObject);
          goto LABEL_73;
        }
        if ( FileHandle )
        {
          FltClose(FileHandle);
          FileHandle = 0;
        }
        v11 = v66;
      }
      v24 = (unsigned int)v8;
    }
    v8 = (unsigned int)(v8 + 1);
    v4 = a2;
    v12 = v71;
    v9 = v65;
  }
  LODWORD(v8) = 0;
  while ( (unsigned int)v8 < v4 )
  {
    FileInformation = 0;
    v81 = 0;
    v40 = *v12;
    v41 = (v9 + v74 - 1) / v9;
    for ( k = 0; k < a2; ++k )
    {
      if ( k >= (unsigned int)v8 )
        break;
      v43 = (-(__int64)(k != 0) & 0xFFFFFFFFFFFFC010uLL) + 32736;
      v41 = (v43 + v41 - 1) / v43;
    }
    v44 = (-(__int64)((_DWORD)v8 != 0) & 0xFFFFFFFFFFFFC010uLL) + 32736;
    v64 = ((v44 + v41 - 1) / v44 + 1) << 13;
    FileObject = FltQueryInformationFile(
                   *(PFLT_INSTANCE *)(*(_QWORD *)v68 + 32LL),
                   *(PFILE_OBJECT *)(*v11 + 8LL * (unsigned int)v8),
                   &FileInformation,
                   0x18u,
                   FileStandardInformation,
                   0);
    HsmDbgBreakOnStatus(FileObject);
    if ( FileObject < 0 )
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_109;
      }
      v37 = 67;
LABEL_119:
      v38 = v5 + 32;
      v39 = v5;
LABEL_121:
      WPP_SF_qisdd(v33->AttachedDevice, v37, v9, v39, *(_QWORD *)v5, v38, v8, FileObject);
      goto LABEL_109;
    }
    if ( (unsigned int)v8 < ((v40 >> 12) & 7) )
    {
      v45 = *((_QWORD *)&FileInformation + 1);
      if ( *((__int64 *)&FileInformation + 1) < v64 )
      {
        FileObject = -1073688830;
        HsmDbgBreakOnStatus(-1073688830);
        goto LABEL_73;
      }
      if ( *((_QWORD *)&FileInformation + 1) != v64 )
        v45 = 0;
      *((_QWORD *)&FileInformation + 1) = v45;
    }
    if ( *((__int64 *)&FileInformation + 1) >= v64 )
    {
      v46 = *((_QWORD *)&FileInformation + 1);
      v64 = *((_QWORD *)&FileInformation + 1);
    }
    else
    {
      FileObject = FltSetInformationFile(
                     *(PFLT_INSTANCE *)(*(_QWORD *)v68 + 32LL),
                     *(PFILE_OBJECT *)(*v66 + 8LL * (unsigned int)v8),
                     &v64,
                     8u,
                     FileEndOfFileInformation);
      HsmDbgBreakOnStatus(FileObject);
      if ( FileObject < 0 )
      {
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_109;
        }
        v50 = 68;
LABEL_154:
        WPP_SF_qisdil(v33->AttachedDevice, v50, v5 + 32, v5, *(_QWORD *)v5, v5 + 32, v8, v64, FileObject);
        goto LABEL_109;
      }
      FileObject = HsmpSetFileVDL(*(_QWORD *)(*(_QWORD *)v68 + 32LL), *(_QWORD *)(*v66 + 8LL * (unsigned int)v8), v64);
      HsmDbgBreakOnStatus(FileObject);
      if ( FileObject < 0 )
      {
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_109;
        }
        v50 = 69;
        goto LABEL_154;
      }
      v46 = v64;
    }
    v47 = *(_QWORD *)(*v66 + 8 + 8LL * (unsigned int)v8);
    if ( v47 )
    {
      HsmpFileCacheSetFileSize(v47, v46);
      v48 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        v49 = 72;
        goto LABEL_146;
      }
    }
    else
    {
      FileObject = HsmFileCacheCreateFileObject(
                     *(_QWORD *)(*(_QWORD *)v68 + 32LL),
                     *(_DWORD *)(*(_QWORD *)v68 + 104LL),
                     *(_QWORD *)(*v66 + 8LL * (unsigned int)v8),
                     v46,
                     InputBufferLength,
                     v5,
                     OutputBufferLength,
                     (PFILE_OBJECT *)(*v66 + 8 + 8LL * (unsigned int)v8));
      HsmDbgBreakOnStatus(FileObject);
      if ( FileObject < 0 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_73;
        }
        v36 = 70;
        goto LABEL_114;
      }
      v48 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        v49 = 71;
LABEL_146:
        WPP_SF_qisdi(v48->AttachedDevice, v49, v5 + 32, v5, *(_QWORD *)v5, v5 + 32, v8, v64);
      }
    }
    LODWORD(v8) = v8 + 1;
    v11 = v66;
    v4 = a2;
    v12 = v71;
    v9 = v65;
  }
  LODWORD(v8) = 0;
  while ( 1 )
  {
    v65 = v8;
    if ( (unsigned int)v8 >= a2 )
    {
      if ( v61[1] )
        *v12 |= 8u;
      goto LABEL_73;
    }
    v63 = (*v12 >> 12) & 7;
    LODWORD(v64) = v63;
    if ( (unsigned int)v8 >= v63 )
      break;
LABEL_34:
    v19 = ((*(_QWORD *)(a1 + 144) + 1LL) % 2) << 12;
    if ( LODWORD(v70[0]) )
    {
      FileInformation = *(_OWORD *)v70;
      HsmIBitmapNORMALUnpinBlock(&FileInformation);
      LODWORD(v70[0]) = 0;
      Buffer = 0;
    }
    v58 = HsmiBitmapNORMALLoadFromDisk(a1, v8, v19, (unsigned int)&Buffer, (__int64)v70);
    HsmDbgBreakOnStatus(v58);
    if ( v58 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qisdil(WPP_GLOBAL_Control->AttachedDevice, 76, a1 + 32, a1, *(_QWORD *)v5, a1 + 32, v8, v19, v58);
      }
      FileObject = v58;
      LOBYTE(v8) = v60;
      goto LABEL_2;
    }
    v20 = Buffer;
    if ( _byteswap_ushort(*((_WORD *)Buffer + 2)) == *((_WORD *)Buffer + 3) )
    {
      if ( *(_DWORD *)Buffer == 1884124226 )
      {
        LOBYTE(v20) = Buffer[4];
        v59 = HsmiBitmapCheckVersion(v20);
        HsmDbgBreakOnStatus(v59);
        if ( v59 >= 0 )
        {
          if ( *((_DWORD *)Buffer + 2) == (_DWORD)v8 )
          {
            v21 = *((_QWORD *)Buffer + 2);
            if ( v21 )
            {
              if ( v21 < *(_QWORD *)(a1 + 144) )
              {
                v59 = -1073688830;
                HsmDbgBreakOnStatus(-1073688830);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qisdiid(
                    WPP_GLOBAL_Control->AttachedDevice,
                    a1 + 32,
                    *((_QWORD *)Buffer + 2),
                    a1,
                    *(_QWORD *)v5,
                    a1 + 32,
                    v8,
                    *((_QWORD *)Buffer + 2),
                    *(_QWORD *)(a1 + 144),
                    2);
                }
              }
            }
          }
          else
          {
            v59 = -1073688830;
            HsmDbgBreakOnStatus(-1073688830);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qisddd(
                WPP_GLOBAL_Control->AttachedDevice,
                80,
                a1 + 32,
                a1,
                *(_QWORD *)v5,
                a1 + 32,
                *((_DWORD *)Buffer + 2),
                v8,
                2);
            }
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qisdddd(
            WPP_GLOBAL_Control->AttachedDevice,
            a1 + 32,
            Buffer[5],
            a1,
            *(_QWORD *)v5,
            a1 + 32,
            v8,
            Buffer[4],
            Buffer[5],
            v59);
        }
      }
      else
      {
        v59 = -1073688830;
        HsmDbgBreakOnStatus(-1073688830);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qisdLLd(
            WPP_GLOBAL_Control->AttachedDevice,
            a1 + 32,
            *(_DWORD *)Buffer,
            a1,
            *(_QWORD *)v5,
            a1 + 32,
            v8,
            *(_DWORD *)Buffer,
            v57,
            2);
        }
      }
    }
    else
    {
      v59 = -1073741761;
      HsmDbgBreakOnStatus(-1073741761);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qisdDDLd(
          WPP_GLOBAL_Control->AttachedDevice,
          a1 + 32,
          *((unsigned __int16 *)Buffer + 3),
          a1,
          *(_QWORD *)v5,
          a1 + 32,
          v8,
          Buffer[4],
          Buffer[5],
          *((_WORD *)Buffer + 3),
          63);
      }
    }
    FileObject = v59;
    if ( v59 < 0 )
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v37 = 83;
        goto LABEL_120;
      }
      goto LABEL_109;
    }
LABEL_70:
    LODWORD(v8) = v8 + 1;
    v12 = v71;
  }
  v61[0] = 0;
  if ( LODWORD(v70[0]) )
  {
    FileInformation = *(_OWORD *)v70;
    HsmIBitmapNORMALUnpinBlock(&FileInformation);
    LODWORD(v70[0]) = 0;
    Buffer = 0;
  }
  FileObject = HsmpFileCachePreparePinWrite(
                 *(PFILE_OBJECT *)(*v66 + 8LL * (unsigned int)v8 + 8),
                 InputBufferLength,
                 &v70[1],
                 (PVOID *)&Buffer,
                 (__int64)v61);
  HsmDbgBreakOnStatus(FileObject);
  if ( FileObject >= 0 )
  {
    LODWORD(v70[0]) = 1;
    *(_DWORD *)Buffer = 1884124226;
    Buffer[4] = 1;
    Buffer[5] = 3;
    *((_WORD *)Buffer + 3) = 259;
    *((_DWORD *)Buffer + 2) = v8;
    v51 = Buffer;
    *((_DWORD *)v51 + 1023) = RtlComputeCrc32(0, Buffer, 0xFFCu);
    FileObject = HsmpFileCacheSetAddressRangeModified(Buffer);
    HsmDbgBreakOnStatus(FileObject);
    if ( FileObject < 0 )
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          75,
          WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids,
          (unsigned int)FileObject);
      }
      goto LABEL_109;
    }
    if ( (unsigned int)v8 >= v63 )
      goto LABEL_70;
    goto LABEL_34;
  }
  v33 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v37 = 73;
LABEL_120:
    v38 = a1 + 32;
    v39 = a1;
    goto LABEL_121;
  }
LABEL_109:
  FileObject = HsmiBitmapTranslateIOStatus(v33, (unsigned int)FileObject);
  HsmDbgBreakOnStatus(FileObject);
LABEL_73:
  LOBYTE(v8) = v60;
LABEL_2:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( LODWORD(v70[0]) )
  {
    v76 = *(_OWORD *)v70;
    HsmIBitmapNORMALUnpinBlock(&v76);
  }
  if ( FileObject < 0 )
  {
    v14 = *(_QWORD *)(a1 + 160);
    if ( v14 )
    {
      v15 = v60;
      do
      {
        if ( v15 )
          break;
        v16 = *(struct _FILE_OBJECT **)(v14 + 8);
        if ( v16 )
        {
          HsmFileCacheCloseFileObject(v16);
          *(_QWORD *)(*(_QWORD *)(a1 + 160) + 8LL) = 0;
        }
        v17 = **(void ***)(a1 + 160);
        if ( v17 )
        {
          ObfDereferenceObject(v17);
          **(_QWORD **)(a1 + 160) = 0;
        }
        v63 = 0;
        if ( (unsigned int)HsmiBitmapNORMALGetNumberOfPlexCopies(a1) )
        {
          do
          {
            v52 = v18;
            v53 = *(void **)(*(_QWORD *)(a1 + 160) + 8LL * v18 + 16);
            if ( v53 )
            {
              ObfDereferenceObject(v53);
              *(_QWORD *)(*(_QWORD *)(a1 + 160) + 8 * v52 + 16) = 0;
              v18 = v63;
            }
            v63 = v18 + 1;
            v54 = HsmiBitmapNORMALGetNumberOfPlexCopies(a1);
          }
          while ( v18 < v54 );
          v15 = v60;
        }
        v60 = ++v15;
        v14 = *(_QWORD *)(a1 + 160);
      }
      while ( v14 );
      v5 = v73;
      LOBYTE(v8) = v60;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qisdd(WPP_GLOBAL_Control->AttachedDevice, 84, v9, a1, *(_QWORD *)v5, a1 + 32, v8, FileObject);
    }
  }
  *(_DWORD *)(a1 + 24) = FileObject;
  FltReleasePushLockEx(v77, 0);
  return (unsigned int)FileObject;
}

```

## disassembly

```asm
0x140070984  mov     [rsp+arg_8], edx
0x140070988  push    rbx
0x140070989  push    rsi
0x14007098a  push    rdi
0x14007098b  push    r12
0x14007098d  push    r13
0x14007098f  push    r14
0x140070991  push    r15
0x140070993  sub     rsp, 150h
0x14007099a  mov     rax, cs:__security_cookie
0x1400709a1  xor     rax, rsp
0x1400709a4  mov     [rsp+188h+var_48], rax
0x1400709ac  mov     [rsp+188h+var_B0], r9
0x1400709b4  mov     [rsp+188h+var_110], r8d
0x1400709b9  mov     r14d, edx
0x1400709bc  mov     r13, rcx
0x1400709bf  mov     [rsp+188h+var_B8], rcx
0x1400709c7  mov     [rsp+188h+var_A8], rcx
0x1400709cf  mov     rdi, rcx
0x1400709d2  mov     [rsp+188h+var_C0], rcx
0x1400709da  xor     esi, esi
0x1400709dc  mov     ebx, esi
0x1400709de  mov     [rsp+188h+var_128], ebx
0x1400709e2  mov     r15d, esi
0x1400709e5  mov     [rsp+188h+var_124], esi
0x1400709e9  mov     [rsp+188h+FileHandle], rsi
0x1400709f1  mov     [rsp+188h+Buffer], rsi
0x1400709f6  mov     [rsp+188h+var_D8], rsi
0x1400709fe  xor     eax, eax
0x140070a00  mov     [rsp+188h+var_D8+8], rax
0x140070a08  lea     rax, [rcx+30h]
0x140070a0c  mov     [rsp+188h+var_88], rax
0x140070a14  xor     edx, edx
0x140070a16  mov     rcx, rax
0x140070a19  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140070a20  nop     dword ptr [rax+rax+00h]
0x140070a25  test    r14d, r14d
0x140070a28  jnz     short loc_140070A7A
0x140070a2a  lea     r12, WPP_GLOBAL_Control
0x140070a31  mov     r14d, 2
0x140070a37  mov     rcx, [rsp+188h+FileHandle]; FileHandle
0x140070a3f  test    rcx, rcx
0x140070a42  jnz     loc_140071BEF
0x140070a48  cmp     dword ptr [rsp+188h+var_D8], esi
0x140070a4f  jnz     loc_140071C00
0x140070a55  test    ebx, ebx
0x140070a57  js      short loc_140070AD4
0x140070a59  mov     [rdi+18h], ebx
0x140070a5c  xor     edx, edx
0x140070a5e  mov     rcx, [rsp+188h+var_88]
0x140070a66  call    cs:__imp_FltReleasePushLockEx
0x140070a6d  nop     dword ptr [rax+rax+00h]
0x140070a72  mov     eax, ebx
0x140070a74  jmp     loc_140071CAD
0x140070a7a  lea     r11, [r13+0A0h]
0x140070a81  mov     [rsp+188h+var_F8], r11
0x140070a89  cmp     [r11], rsi
0x140070a8c  jz      loc_140071088
0x140070a92  lea     rdx, [r13+10h]
0x140070a96  mov     [rsp+188h+var_C8], rdx
0x140070a9e  mov     ecx, [rdx]
0x140070aa0  test    cl, 8
0x140070aa3  jz      loc_140070B9D
0x140070aa9  mov     r15d, ecx
0x140070aac  shr     r15d, 0Ch
0x140070ab0  and     r15d, 7
0x140070ab4  mov     [rsp+188h+var_124], r15d
0x140070ab9  mov     [rsp+188h+var_F0], r15d
0x140070ac1  cmp     r15d, r14d
0x140070ac4  jz      loc_140070A2A
0x140070aca  mov     [rsp+188h+var_120+1], sil
0x140070acf  jmp     loc_140070BAF
0x140070ad4  mov     rax, [rdi+0A0h]
0x140070adb  test    rax, rax
0x140070ade  jz      short loc_140070B47
0x140070ae0  mov     r13d, [rsp+188h+var_124]
0x140070ae5  cmp     r13d, 1
0x140070ae9  jnb     short loc_140070B3A
0x140070aeb  mov     r15d, r13d
0x140070aee  mov     rcx, [rax+r15*8+8]; Object
0x140070af3  test    rcx, rcx
0x140070af6  jnz     loc_140071C23
0x140070afc  mov     rax, [rdi+0A0h]
0x140070b03  mov     rcx, [rax+r15*8]; Object
0x140070b07  test    rcx, rcx
0x140070b0a  jnz     loc_140071C39
0x140070b10  mov     edx, esi
0x140070b12  mov     [rsp+188h+var_110], edx
0x140070b16  mov     rcx, rdi
0x140070b19  call    HsmiBitmapNORMALGetNumberOfPlexCopies
0x140070b1e  test    eax, eax
0x140070b20  jnz     loc_140071C55
0x140070b26  inc     r13d
0x140070b29  mov     [rsp+188h+var_124], r13d
0x140070b2e  mov     rax, [rdi+0A0h]
0x140070b35  test    rax, rax
0x140070b38  jnz     short loc_140070AE5
0x140070b3a  mov     r13, [rsp+188h+var_B8]
0x140070b42  mov     r15d, [rsp+188h+var_124]
0x140070b47  mov     rcx, cs:WPP_GLOBAL_Control
0x140070b4e  cmp     rcx, r12
0x140070b51  jz      loc_140070A59
0x140070b57  mov     eax, [rcx+2Ch]
0x140070b5a  test    al, 1
0x140070b5c  jz      loc_140070A59
0x140070b62  cmp     [rcx+29h], r14b
0x140070b66  jb      loc_140070A59
0x140070b6c  lea     rax, [rdi+20h]
0x140070b70  mov     edx, 54h ; 'T'
0x140070b75  mov     dword ptr [rsp+188h+LengthReturned], ebx
0x140070b79  mov     [rsp+188h+OutputBufferLength], r15d
0x140070b7e  mov     [rsp+188h+OutputBuffer], rax
0x140070b83  mov     rax, [r13+0]
0x140070b87  mov     qword ptr [rsp+188h+InputBufferLength], rax
0x140070b8c  mov     r9, rdi
0x140070b8f  mov     rcx, [rcx+18h]
0x140070b93  call    WPP_SF_qisdd
0x140070b98  jmp     loc_140070A59
0x140070b9d  mov     [rsp+188h+var_124], r15d
0x140070ba2  mov     [rsp+188h+var_F0], r15d
0x140070baa  mov     [rsp+188h+var_120+1], 1
0x140070baf  mov     qword ptr [rsp+188h+var_98], rdx
0x140070bb7  mov     rax, [r13+28h]
0x140070bbb  mov     qword ptr [rsp+188h+var_E8], rax
0x140070bc3  shr     ecx, 6
0x140070bc6  and     ecx, 3Fh
0x140070bc9  mov     r8d, 1
0x140070bcf  shl     r8d, cl
0x140070bd2  mov     [rsp+188h+var_100], r8d
0x140070bda  lea     r12, WPP_GLOBAL_Control
0x140070be1  cmp     r15d, r14d
0x140070be4  jb      loc_140071121
0x140070bea  mov     r15d, esi
0x140070bed  cmp     r15d, r14d
0x140070bf0  jb      loc_14007159E
0x140070bf6  mov     r15d, esi
0x140070bf9  mov     r14d, 2
0x140070bff  mov     [rsp+188h+var_100], r15d
0x140070c07  cmp     r15d, [rsp+188h+arg_8]
0x140070c0f  jnb     loc_140071073
0x140070c15  mov     eax, [rdx]
0x140070c17  shr     eax, 0Ch
0x140070c1a  and     eax, 7
0x140070c1d  mov     [rsp+188h+var_110], eax
0x140070c21  mov     dword ptr [rsp+188h+var_108], eax
0x140070c28  cmp     r15d, eax
0x140070c2b  jnb     loc_140071982
0x140070c31  mov     rax, [rdi+90h]
0x140070c38  inc     rax
0x140070c3b  cqo
0x140070c3d  idiv    r14
0x140070c40  mov     rbx, rdx
0x140070c43  shl     rbx, 0Ch
0x140070c47  cmp     dword ptr [rsp+188h+var_D8], esi
0x140070c4e  jnz     loc_140071B89
0x140070c54  lea     rax, [rsp+188h+var_D8]
0x140070c5c  mov     qword ptr [rsp+188h+InputBufferLength], rax
0x140070c61  lea     r9, [rsp+188h+Buffer]
0x140070c66  mov     r8, rbx
0x140070c69  mov     edx, r15d
0x140070c6c  mov     rcx, rdi
0x140070c6f  call    HsmiBitmapNORMALLoadFromDisk
0x140070c74  mov     [rsp+188h+var_128], eax
0x140070c78  mov     ecx, [rsp+188h+var_128]
0x140070c7c  call    HsmDbgBreakOnStatus
0x140070c81  mov     eax, [rsp+188h+var_128]
0x140070c85  test    eax, eax
0x140070c87  js      short loc_140070CCE
0x140070c89  mov     rcx, [rsp+188h+Buffer]
0x140070c8e  movzx   edx, byte ptr [rcx+5]
0x140070c92  movzx   r8d, byte ptr [rcx+4]
0x140070c97  movzx   eax, r8w
0x140070c9b  shl     ax, 8
0x140070c9f  or      ax, dx
0x140070ca2  cmp     ax, [rcx+6]
0x140070ca6  jz      loc_140070D92
0x140070cac  mov     [rsp+188h+var_128], 0C000003Fh
0x140070cb4  mov     ecx, [rsp+188h+var_128]
0x140070cb8  call    HsmDbgBreakOnStatus
0x140070cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x140070cc4  cmp     rcx, r12
0x140070cc7  jnz     short loc_140070D2A
0x140070cc9  jmp     loc_140070F9D
0x140070cce  mov     rcx, cs:WPP_GLOBAL_Control
0x140070cd5  cmp     rcx, r12
0x140070cd8  jz      short loc_140070D1C
0x140070cda  mov     eax, [rcx+2Ch]
0x140070cdd  test    al, 1
0x140070cdf  jz      short loc_140070D1C
0x140070ce1  cmp     [rcx+29h], r14b
0x140070ce5  jb      short loc_140070D1C
0x140070ce7  mov     r9, [r13+0]
0x140070ceb  mov     rcx, [rcx+18h]
0x140070cef  lea     r8, [rdi+20h]
0x140070cf3  mov     edx, 4Ch ; 'L'
0x140070cf8  mov     eax, [rsp+188h+var_128]
0x140070cfc  mov     dword ptr [rsp+188h+var_148], eax
0x140070d00  mov     [rsp+188h+LengthReturned], rbx
0x140070d05  mov     [rsp+188h+OutputBufferLength], r15d
0x140070d0a  mov     [rsp+188h+OutputBuffer], r8
0x140070d0f  mov     qword ptr [rsp+188h+InputBufferLength], r9
0x140070d14  mov     r9, rdi
0x140070d17  call    WPP_SF_qisdil
0x140070d1c  mov     ebx, [rsp+188h+var_128]
0x140070d20  mov     r15d, [rsp+188h+var_124]
0x140070d25  jmp     loc_140070A37
0x140070d2a  mov     eax, [rcx+2Ch]
0x140070d2d  test    al, 1
0x140070d2f  jz      loc_140070F9D
0x140070d35  cmp     [rcx+29h], r14b
0x140070d39  jb      loc_140070F9D
0x140070d3f  mov     rax, [rsp+188h+Buffer]
0x140070d44  movzx   r8d, word ptr [rax+6]
0x140070d49  movzx   r9d, byte ptr [rax+5]
0x140070d4e  movzx   r10d, byte ptr [rax+4]
0x140070d53  mov     r11, [r13+0]
0x140070d57  mov     rcx, [rcx+18h]
0x140070d5b  lea     rdx, [rdi+20h]
0x140070d5f  mov     eax, [rsp+188h+var_128]
0x140070d63  mov     [rsp+188h+var_138], eax
0x140070d67  mov     [rsp+188h+var_140], r8d
0x140070d6c  mov     dword ptr [rsp+188h+var_148], r9d
0x140070d71  mov     dword ptr [rsp+188h+LengthReturned], r10d
0x140070d76  mov     [rsp+188h+OutputBufferLength], r15d
0x140070d7b  mov     [rsp+188h+OutputBuffer], rdx
0x140070d80  mov     qword ptr [rsp+188h+InputBufferLength], r11
0x140070d85  mov     r9, rdi
0x140070d88  call    WPP_SF_qisdDDLd
0x140070d8d  jmp     loc_140070F9D
0x140070d92  cmp     dword ptr [rcx], 704D7442h
0x140070d98  jz      short loc_140070E0D
0x140070d9a  mov     [rsp+188h+var_128], 0C000CF02h
0x140070da2  mov     ecx, [rsp+188h+var_128]
0x140070da6  call    HsmDbgBreakOnStatus
0x140070dab  mov     rcx, cs:WPP_GLOBAL_Control
0x140070db2  cmp     rcx, r12
0x140070db5  jz      loc_140070F9D
0x140070dbb  mov     eax, [rcx+2Ch]
0x140070dbe  test    al, 1
0x140070dc0  jz      loc_140070F9D
0x140070dc6  cmp     [rcx+29h], r14b
0x140070dca  jb      loc_140070F9D
0x140070dd0  mov     rax, [rsp+188h+Buffer]
0x140070dd5  mov     r8d, [rax]
0x140070dd8  mov     r9, [r13+0]
0x140070ddc  mov     rcx, [rcx+18h]
0x140070de0  lea     rdx, [rdi+20h]
0x140070de4  mov     eax, [rsp+188h+var_128]
0x140070de8  mov     [rsp+188h+var_140], eax
0x140070dec  mov     dword ptr [rsp+188h+LengthReturned], r8d
0x140070df1  mov     [rsp+188h+OutputBufferLength], r15d
0x140070df6  mov     [rsp+188h+OutputBuffer], rdx
0x140070dfb  mov     qword ptr [rsp+188h+InputBufferLength], r9
0x140070e00  mov     r9, rdi
0x140070e03  call    WPP_SF_qisdLLd
0x140070e08  jmp     loc_140070F9D
0x140070e0d  mov     cl, r8b
0x140070e10  call    HsmiBitmapCheckVersion
0x140070e15  mov     [rsp+188h+var_128], eax
0x140070e19  mov     ecx, [rsp+188h+var_128]
0x140070e1d  call    HsmDbgBreakOnStatus
0x140070e22  mov     eax, [rsp+188h+var_128]
0x140070e26  test    eax, eax
0x140070e28  jns     short loc_140070E98
0x140070e2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140070e31  cmp     rcx, r12
0x140070e34  jz      loc_140070F9D
0x140070e3a  mov     eax, [rcx+2Ch]
0x140070e3d  test    al, 1
0x140070e3f  jz      loc_140070F9D
0x140070e45  cmp     [rcx+29h], r14b
0x140070e49  jb      loc_140070F9D
0x140070e4f  mov     rax, [rsp+188h+Buffer]
0x140070e54  movzx   r8d, byte ptr [rax+5]
0x140070e59  movzx   r9d, byte ptr [rax+4]
0x140070e5e  mov     r10, [r13+0]
0x140070e62  mov     rcx, [rcx+18h]
0x140070e66  lea     rdx, [rdi+20h]
0x140070e6a  mov     eax, [rsp+188h+var_128]
0x140070e6e  mov     [rsp+188h+var_140], eax
0x140070e72  mov     dword ptr [rsp+188h+var_148], r8d
0x140070e77  mov     dword ptr [rsp+188h+LengthReturned], r9d
0x140070e7c  mov     [rsp+188h+OutputBufferLength], r15d
0x140070e81  mov     [rsp+188h+OutputBuffer], rdx
0x140070e86  mov     qword ptr [rsp+188h+InputBufferLength], r10
0x140070e8b  mov     r9, rdi
0x140070e8e  call    WPP_SF_qisdddd
0x140070e93  jmp     loc_140070F9D
0x140070e98  mov     rax, [rsp+188h+Buffer]
0x140070e9d  cmp     [rax+8], r15d
0x140070ea1  jz      short loc_140070F1C
0x140070ea3  mov     [rsp+188h+var_128], 0C000CF02h
0x140070eab  mov     ecx, [rsp+188h+var_128]
0x140070eaf  call    HsmDbgBreakOnStatus
0x140070eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x140070ebb  cmp     rcx, r12
0x140070ebe  jz      loc_140070F9D
0x140070ec4  mov     eax, [rcx+2Ch]
0x140070ec7  test    al, 1
0x140070ec9  jz      loc_140070F9D
  ... truncated ...
```
