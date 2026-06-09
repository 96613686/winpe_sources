# HsmiBitmapNORMALOpenOnDisk

- ea: `0x140070864`
- end: `0x140071bb0`
- name: `HsmiBitmapNORMALOpenOnDisk`
- size: `4940`
- prototype: ``
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
- `0x14001886c`
- `0x140018b60`
- `0x140018d80`
- `0x140018e90`
- `0x140019090`
- `0x14001917c`
- `0x1400196f4`
- `0x140019e0c`
- `0x14001a930`
- `0x14001b42c`
- `0x14001b590`
- `0x14001b85c`
- `0x14001c554`
- `0x14001e140`
- `0x140036400`
- `0x140044aa4`
- `0x140044b78`
- `0x140070864`
- `0x14007243c`
- `0x140072eec`
- `0x14007e2d0`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x140071962`
- `ntoskrnl!RtlComputeCrc32` at `0x140071962`
- `ntoskrnl!ObfDereferenceObject` at `0x140071b19`
- `ntoskrnl!ObfDereferenceObject` at `0x140071b51`
- `ntoskrnl!ObfDereferenceObject` at `0x140071b19`
- `ntoskrnl!ObfDereferenceObject` at `0x140071b51`
- `ntoskrnl!ExAllocatePool2` at `0x140070f78`
- `ntoskrnl!ExAllocatePool2` at `0x140070f78`
- `FLTMGR!FltSetInformationFile` at `0x1400715eb`
- `FLTMGR!FltSetInformationFile` at `0x1400715eb`
- `FLTMGR!FltClose` at `0x14007118d`
- `FLTMGR!FltClose` at `0x1400712c8`
- `FLTMGR!FltClose` at `0x140071acf`
- `FLTMGR!FltClose` at `0x14007118d`
- `FLTMGR!FltClose` at `0x1400712c8`
- `FLTMGR!FltClose` at `0x140071acf`
- `FLTMGR!FltQueryInformationFile` at `0x140071551`
- `FLTMGR!FltQueryInformationFile` at `0x140071551`
- `FLTMGR!FltFsControlFile` at `0x14007129a`
- `FLTMGR!FltFsControlFile` at `0x14007129a`
- `FLTMGR!FltReleasePushLockEx` at `0x140070946`
- `FLTMGR!FltReleasePushLockEx` at `0x140070946`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400708f9`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400708f9`

## string_xrefs

- `0x14007113d`: `Opened`
- `0x140071144`: `Created`
- `0x140071335`: `create`

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
      HsmDbgBreakOnStatus(3221225626LL);
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
      HsmDbgBreakOnStatus((unsigned int)FileObject);
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
        HsmDbgBreakOnStatus((unsigned int)FileObject);
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
        HsmDbgBreakOnStatus((unsigned int)FileObject);
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
    HsmDbgBreakOnStatus((unsigned int)FileObject);
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
        HsmDbgBreakOnStatus(3221278466LL);
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
      HsmDbgBreakOnStatus((unsigned int)FileObject);
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
      HsmDbgBreakOnStatus((unsigned int)FileObject);
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
      HsmDbgBreakOnStatus((unsigned int)FileObject);
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
    HsmDbgBreakOnStatus((unsigned int)v58);
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
        HsmDbgBreakOnStatus((unsigned int)v59);
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
                HsmDbgBreakOnStatus(3221278466LL);
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
            HsmDbgBreakOnStatus(3221278466LL);
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
        HsmDbgBreakOnStatus(3221278466LL);
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
      HsmDbgBreakOnStatus(3221225535LL);
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
  HsmDbgBreakOnStatus((unsigned int)FileObject);
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
    HsmDbgBreakOnStatus((unsigned int)FileObject);
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
  HsmDbgBreakOnStatus((unsigned int)FileObject);
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
0x140070864  mov     [rsp+arg_8], edx
0x140070868  push    rbx
0x140070869  push    rsi
0x14007086a  push    rdi
0x14007086b  push    r12
0x14007086d  push    r13
0x14007086f  push    r14
0x140070871  push    r15
0x140070873  sub     rsp, 150h
0x14007087a  mov     rax, cs:__security_cookie
0x140070881  xor     rax, rsp
0x140070884  mov     [rsp+188h+var_48], rax
0x14007088c  mov     [rsp+188h+var_B0], r9
0x140070894  mov     [rsp+188h+var_110], r8d
0x140070899  mov     r14d, edx
0x14007089c  mov     r13, rcx
0x14007089f  mov     [rsp+188h+var_B8], rcx
0x1400708a7  mov     [rsp+188h+var_A8], rcx
0x1400708af  mov     rdi, rcx
0x1400708b2  mov     [rsp+188h+var_C0], rcx
0x1400708ba  xor     esi, esi
0x1400708bc  mov     ebx, esi
0x1400708be  mov     [rsp+188h+var_128], ebx
0x1400708c2  mov     r15d, esi
0x1400708c5  mov     [rsp+188h+var_124], esi
0x1400708c9  mov     [rsp+188h+FileHandle], rsi
0x1400708d1  mov     [rsp+188h+Buffer], rsi
0x1400708d6  mov     [rsp+188h+var_D8], rsi
0x1400708de  xor     eax, eax
0x1400708e0  mov     [rsp+188h+var_D8+8], rax
0x1400708e8  lea     rax, [rcx+30h]
0x1400708ec  mov     [rsp+188h+var_88], rax
0x1400708f4  xor     edx, edx
0x1400708f6  mov     rcx, rax
0x1400708f9  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140070900  nop     dword ptr [rax+rax+00h]
0x140070905  test    r14d, r14d
0x140070908  jnz     short loc_14007095A
0x14007090a  lea     r12, WPP_GLOBAL_Control
0x140070911  mov     r14d, 2
0x140070917  mov     rcx, [rsp+188h+FileHandle]; FileHandle
0x14007091f  test    rcx, rcx
0x140070922  jnz     loc_140071ACF
0x140070928  cmp     dword ptr [rsp+188h+var_D8], esi
0x14007092f  jnz     loc_140071AE0
0x140070935  test    ebx, ebx
0x140070937  js      short loc_1400709B4
0x140070939  mov     [rdi+18h], ebx
0x14007093c  xor     edx, edx
0x14007093e  mov     rcx, [rsp+188h+var_88]
0x140070946  call    cs:__imp_FltReleasePushLockEx
0x14007094d  nop     dword ptr [rax+rax+00h]
0x140070952  mov     eax, ebx
0x140070954  jmp     loc_140071B8D
0x14007095a  lea     r11, [r13+0A0h]
0x140070961  mov     [rsp+188h+var_F8], r11
0x140070969  cmp     [r11], rsi
0x14007096c  jz      loc_140070F68
0x140070972  lea     rdx, [r13+10h]
0x140070976  mov     [rsp+188h+var_C8], rdx
0x14007097e  mov     ecx, [rdx]
0x140070980  test    cl, 8
0x140070983  jz      loc_140070A7D
0x140070989  mov     r15d, ecx
0x14007098c  shr     r15d, 0Ch
0x140070990  and     r15d, 7
0x140070994  mov     [rsp+188h+var_124], r15d
0x140070999  mov     [rsp+188h+var_F0], r15d
0x1400709a1  cmp     r15d, r14d
0x1400709a4  jz      loc_14007090A
0x1400709aa  mov     [rsp+188h+var_120+1], sil
0x1400709af  jmp     loc_140070A8F
0x1400709b4  mov     rax, [rdi+0A0h]
0x1400709bb  test    rax, rax
0x1400709be  jz      short loc_140070A27
0x1400709c0  mov     r13d, [rsp+188h+var_124]
0x1400709c5  cmp     r13d, 1
0x1400709c9  jnb     short loc_140070A1A
0x1400709cb  mov     r15d, r13d
0x1400709ce  mov     rcx, [rax+r15*8+8]; Object
0x1400709d3  test    rcx, rcx
0x1400709d6  jnz     loc_140071B03
0x1400709dc  mov     rax, [rdi+0A0h]
0x1400709e3  mov     rcx, [rax+r15*8]; Object
0x1400709e7  test    rcx, rcx
0x1400709ea  jnz     loc_140071B19
0x1400709f0  mov     edx, esi
0x1400709f2  mov     [rsp+188h+var_110], edx
0x1400709f6  mov     rcx, rdi
0x1400709f9  call    HsmiBitmapNORMALGetNumberOfPlexCopies
0x1400709fe  test    eax, eax
0x140070a00  jnz     loc_140071B35
0x140070a06  inc     r13d
0x140070a09  mov     [rsp+188h+var_124], r13d
0x140070a0e  mov     rax, [rdi+0A0h]
0x140070a15  test    rax, rax
0x140070a18  jnz     short loc_1400709C5
0x140070a1a  mov     r13, [rsp+188h+var_B8]
0x140070a22  mov     r15d, [rsp+188h+var_124]
0x140070a27  mov     rcx, cs:WPP_GLOBAL_Control
0x140070a2e  cmp     rcx, r12
0x140070a31  jz      loc_140070939
0x140070a37  mov     eax, [rcx+2Ch]
0x140070a3a  test    al, 1
0x140070a3c  jz      loc_140070939
0x140070a42  cmp     [rcx+29h], r14b
0x140070a46  jb      loc_140070939
0x140070a4c  lea     rax, [rdi+20h]
0x140070a50  mov     edx, 54h ; 'T'
0x140070a55  mov     dword ptr [rsp+188h+LengthReturned], ebx
0x140070a59  mov     [rsp+188h+OutputBufferLength], r15d
0x140070a5e  mov     [rsp+188h+OutputBuffer], rax
0x140070a63  mov     rax, [r13+0]
0x140070a67  mov     qword ptr [rsp+188h+InputBufferLength], rax
0x140070a6c  mov     r9, rdi
0x140070a6f  mov     rcx, [rcx+18h]
0x140070a73  call    WPP_SF_qisdd
0x140070a78  jmp     loc_140070939
0x140070a7d  mov     [rsp+188h+var_124], r15d
0x140070a82  mov     [rsp+188h+var_F0], r15d
0x140070a8a  mov     [rsp+188h+var_120+1], 1
0x140070a8f  mov     qword ptr [rsp+188h+var_98], rdx
0x140070a97  mov     rax, [r13+28h]
0x140070a9b  mov     qword ptr [rsp+188h+var_E8], rax
0x140070aa3  shr     ecx, 6
0x140070aa6  and     ecx, 3Fh
0x140070aa9  mov     r8d, 1
0x140070aaf  shl     r8d, cl
0x140070ab2  mov     [rsp+188h+var_100], r8d
0x140070aba  lea     r12, WPP_GLOBAL_Control
0x140070ac1  cmp     r15d, r14d
0x140070ac4  jb      loc_140071001
0x140070aca  mov     r15d, esi
0x140070acd  cmp     r15d, r14d
0x140070ad0  jb      loc_14007147E
0x140070ad6  mov     r15d, esi
0x140070ad9  mov     r14d, 2
0x140070adf  mov     [rsp+188h+var_100], r15d
0x140070ae7  cmp     r15d, [rsp+188h+arg_8]
0x140070aef  jnb     loc_140070F53
0x140070af5  mov     eax, [rdx]
0x140070af7  shr     eax, 0Ch
0x140070afa  and     eax, 7
0x140070afd  mov     [rsp+188h+var_110], eax
0x140070b01  mov     dword ptr [rsp+188h+var_108], eax
0x140070b08  cmp     r15d, eax
0x140070b0b  jnb     loc_140071862
0x140070b11  mov     rax, [rdi+90h]
0x140070b18  inc     rax
0x140070b1b  cqo
0x140070b1d  idiv    r14
0x140070b20  mov     rbx, rdx
0x140070b23  shl     rbx, 0Ch
0x140070b27  cmp     dword ptr [rsp+188h+var_D8], esi
0x140070b2e  jnz     loc_140071A69
0x140070b34  lea     rax, [rsp+188h+var_D8]
0x140070b3c  mov     qword ptr [rsp+188h+InputBufferLength], rax
0x140070b41  lea     r9, [rsp+188h+Buffer]
0x140070b46  mov     r8, rbx
0x140070b49  mov     edx, r15d
0x140070b4c  mov     rcx, rdi
0x140070b4f  call    HsmiBitmapNORMALLoadFromDisk
0x140070b54  mov     [rsp+188h+var_128], eax
0x140070b58  mov     ecx, [rsp+188h+var_128]
0x140070b5c  call    HsmDbgBreakOnStatus
0x140070b61  mov     eax, [rsp+188h+var_128]
0x140070b65  test    eax, eax
0x140070b67  js      short loc_140070BAE
0x140070b69  mov     rcx, [rsp+188h+Buffer]
0x140070b6e  movzx   edx, byte ptr [rcx+5]
0x140070b72  movzx   r8d, byte ptr [rcx+4]
0x140070b77  movzx   eax, r8w
0x140070b7b  shl     ax, 8
0x140070b7f  or      ax, dx
0x140070b82  cmp     ax, [rcx+6]
0x140070b86  jz      loc_140070C72
0x140070b8c  mov     [rsp+188h+var_128], 0C000003Fh
0x140070b94  mov     ecx, [rsp+188h+var_128]
0x140070b98  call    HsmDbgBreakOnStatus
0x140070b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140070ba4  cmp     rcx, r12
0x140070ba7  jnz     short loc_140070C0A
0x140070ba9  jmp     loc_140070E7D
0x140070bae  mov     rcx, cs:WPP_GLOBAL_Control
0x140070bb5  cmp     rcx, r12
0x140070bb8  jz      short loc_140070BFC
0x140070bba  mov     eax, [rcx+2Ch]
0x140070bbd  test    al, 1
0x140070bbf  jz      short loc_140070BFC
0x140070bc1  cmp     [rcx+29h], r14b
0x140070bc5  jb      short loc_140070BFC
0x140070bc7  mov     r9, [r13+0]
0x140070bcb  mov     rcx, [rcx+18h]
0x140070bcf  lea     r8, [rdi+20h]
0x140070bd3  mov     edx, 4Ch ; 'L'
0x140070bd8  mov     eax, [rsp+188h+var_128]
0x140070bdc  mov     dword ptr [rsp+188h+var_148], eax
0x140070be0  mov     [rsp+188h+LengthReturned], rbx
0x140070be5  mov     [rsp+188h+OutputBufferLength], r15d
0x140070bea  mov     [rsp+188h+OutputBuffer], r8
0x140070bef  mov     qword ptr [rsp+188h+InputBufferLength], r9
0x140070bf4  mov     r9, rdi
0x140070bf7  call    WPP_SF_qisdil
0x140070bfc  mov     ebx, [rsp+188h+var_128]
0x140070c00  mov     r15d, [rsp+188h+var_124]
0x140070c05  jmp     loc_140070917
0x140070c0a  mov     eax, [rcx+2Ch]
0x140070c0d  test    al, 1
0x140070c0f  jz      loc_140070E7D
0x140070c15  cmp     [rcx+29h], r14b
0x140070c19  jb      loc_140070E7D
0x140070c1f  mov     rax, [rsp+188h+Buffer]
0x140070c24  movzx   r8d, word ptr [rax+6]
0x140070c29  movzx   r9d, byte ptr [rax+5]
0x140070c2e  movzx   r10d, byte ptr [rax+4]
0x140070c33  mov     r11, [r13+0]
0x140070c37  mov     rcx, [rcx+18h]
0x140070c3b  lea     rdx, [rdi+20h]
0x140070c3f  mov     eax, [rsp+188h+var_128]
0x140070c43  mov     [rsp+188h+var_138], eax
0x140070c47  mov     [rsp+188h+var_140], r8d
0x140070c4c  mov     dword ptr [rsp+188h+var_148], r9d
0x140070c51  mov     dword ptr [rsp+188h+LengthReturned], r10d
0x140070c56  mov     [rsp+188h+OutputBufferLength], r15d
0x140070c5b  mov     [rsp+188h+OutputBuffer], rdx
0x140070c60  mov     qword ptr [rsp+188h+InputBufferLength], r11
0x140070c65  mov     r9, rdi
0x140070c68  call    WPP_SF_qisdDDLd
0x140070c6d  jmp     loc_140070E7D
0x140070c72  cmp     dword ptr [rcx], 704D7442h
0x140070c78  jz      short loc_140070CED
0x140070c7a  mov     [rsp+188h+var_128], 0C000CF02h
0x140070c82  mov     ecx, [rsp+188h+var_128]
0x140070c86  call    HsmDbgBreakOnStatus
0x140070c8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140070c92  cmp     rcx, r12
0x140070c95  jz      loc_140070E7D
0x140070c9b  mov     eax, [rcx+2Ch]
0x140070c9e  test    al, 1
0x140070ca0  jz      loc_140070E7D
0x140070ca6  cmp     [rcx+29h], r14b
0x140070caa  jb      loc_140070E7D
0x140070cb0  mov     rax, [rsp+188h+Buffer]
0x140070cb5  mov     r8d, [rax]
0x140070cb8  mov     r9, [r13+0]
0x140070cbc  mov     rcx, [rcx+18h]
0x140070cc0  lea     rdx, [rdi+20h]
0x140070cc4  mov     eax, [rsp+188h+var_128]
0x140070cc8  mov     [rsp+188h+var_140], eax
0x140070ccc  mov     dword ptr [rsp+188h+LengthReturned], r8d
0x140070cd1  mov     [rsp+188h+OutputBufferLength], r15d
0x140070cd6  mov     [rsp+188h+OutputBuffer], rdx
0x140070cdb  mov     qword ptr [rsp+188h+InputBufferLength], r9
0x140070ce0  mov     r9, rdi
0x140070ce3  call    WPP_SF_qisdLLd
0x140070ce8  jmp     loc_140070E7D
0x140070ced  mov     cl, r8b
0x140070cf0  call    HsmiBitmapCheckVersion
0x140070cf5  mov     [rsp+188h+var_128], eax
0x140070cf9  mov     ecx, [rsp+188h+var_128]
0x140070cfd  call    HsmDbgBreakOnStatus
0x140070d02  mov     eax, [rsp+188h+var_128]
0x140070d06  test    eax, eax
0x140070d08  jns     short loc_140070D78
0x140070d0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140070d11  cmp     rcx, r12
0x140070d14  jz      loc_140070E7D
0x140070d1a  mov     eax, [rcx+2Ch]
0x140070d1d  test    al, 1
0x140070d1f  jz      loc_140070E7D
0x140070d25  cmp     [rcx+29h], r14b
0x140070d29  jb      loc_140070E7D
0x140070d2f  mov     rax, [rsp+188h+Buffer]
0x140070d34  movzx   r8d, byte ptr [rax+5]
0x140070d39  movzx   r9d, byte ptr [rax+4]
0x140070d3e  mov     r10, [r13+0]
0x140070d42  mov     rcx, [rcx+18h]
0x140070d46  lea     rdx, [rdi+20h]
0x140070d4a  mov     eax, [rsp+188h+var_128]
0x140070d4e  mov     [rsp+188h+var_140], eax
0x140070d52  mov     dword ptr [rsp+188h+var_148], r8d
0x140070d57  mov     dword ptr [rsp+188h+LengthReturned], r9d
0x140070d5c  mov     [rsp+188h+OutputBufferLength], r15d
0x140070d61  mov     [rsp+188h+OutputBuffer], rdx
0x140070d66  mov     qword ptr [rsp+188h+InputBufferLength], r10
0x140070d6b  mov     r9, rdi
0x140070d6e  call    WPP_SF_qisdddd
0x140070d73  jmp     loc_140070E7D
0x140070d78  mov     rax, [rsp+188h+Buffer]
0x140070d7d  cmp     [rax+8], r15d
0x140070d81  jz      short loc_140070DFC
0x140070d83  mov     [rsp+188h+var_128], 0C000CF02h
0x140070d8b  mov     ecx, [rsp+188h+var_128]
0x140070d8f  call    HsmDbgBreakOnStatus
0x140070d94  mov     rcx, cs:WPP_GLOBAL_Control
0x140070d9b  cmp     rcx, r12
0x140070d9e  jz      loc_140070E7D
0x140070da4  mov     eax, [rcx+2Ch]
0x140070da7  test    al, 1
0x140070da9  jz      loc_140070E7D
  ... truncated ...
```
