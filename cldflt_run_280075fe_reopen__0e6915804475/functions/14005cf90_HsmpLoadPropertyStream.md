# HsmpLoadPropertyStream

- ea: `0x14005cf90`
- end: `0x14005e2c0`
- name: `HsmpLoadPropertyStream`
- size: `4912`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14004a54c`
- `0x14005062c`

## callees

- `0x140001b00`
- `0x140003c50`
- `0x140009300`
- `0x14000abb8`
- `0x14000db8c`
- `0x14001ac4c`
- `0x14001e140`
- `0x14001e280`
- `0x140035610`
- `0x1400430ec`
- `0x14004c708`
- `0x14005cd20`
- `0x14005cf90`
- `0x14005e2d0`
- `0x14005eb40`
- `0x14005f194`
- `0x14007e3b8`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14005d2c7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005d2c7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005d26c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005d26c`
- `ntoskrnl!RtlCrc32` at `0x14005d667`
- `ntoskrnl!RtlCrc32` at `0x14005db72`
- `ntoskrnl!RtlCrc32` at `0x14005d667`
- `ntoskrnl!RtlCrc32` at `0x14005db72`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14005d8d9`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14005daa2`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14005d8d9`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14005daa2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005d2a6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005dc54`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e1f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e2af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005d2a6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005dc54`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e1f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e2af`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d29a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dc48`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e1e7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e2a3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d29a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dc48`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e1e7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e2a3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005d0a4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005d0a4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005d093`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005d257`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005d093`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005d257`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d427`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d95f`
- `ntoskrnl!ObfDereferenceObject` at `0x14005dda7`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d427`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d95f`
- `ntoskrnl!ObfDereferenceObject` at `0x14005dda7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d342`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d342`
- `ntoskrnl!ExAllocatePool2` at `0x14005d1da`
- `ntoskrnl!ExAllocatePool2` at `0x14005d7bb`
- `ntoskrnl!ExAllocatePool2` at `0x14005d9c1`
- `ntoskrnl!ExAllocatePool2` at `0x14005d1da`
- `ntoskrnl!ExAllocatePool2` at `0x14005d7bb`
- `ntoskrnl!ExAllocatePool2` at `0x14005d9c1`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x14005d889`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x14005d889`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14005d5d3`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14005d6fb`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14005db2c`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14005d5d3`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14005d6fb`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14005db2c`
- `FLTMGR!FltSetInformationFile` at `0x14005dae1`
- `FLTMGR!FltSetInformationFile` at `0x14005dae1`
- `FLTMGR!FltCreateFileEx` at `0x14005d3e6`
- `FLTMGR!FltCreateFileEx` at `0x14005d3e6`
- `FLTMGR!FltWriteFile` at `0x14005dbb0`
- `FLTMGR!FltWriteFile` at `0x14005dbb0`
- `FLTMGR!FltReadFile` at `0x14005d55a`
- `FLTMGR!FltReadFile` at `0x14005d633`
- `FLTMGR!FltReadFile` at `0x14005d55a`
- `FLTMGR!FltReadFile` at `0x14005d633`
- `FLTMGR!FltClose` at `0x14005d43b`
- `FLTMGR!FltClose` at `0x14005ddb8`
- `FLTMGR!FltClose` at `0x14005e17a`
- `FLTMGR!FltClose` at `0x14005d43b`
- `FLTMGR!FltClose` at `0x14005ddb8`
- `FLTMGR!FltClose` at `0x14005e17a`
- `FLTMGR!FltQueryInformationFile` at `0x14005d161`
- `FLTMGR!FltQueryInformationFile` at `0x14005d4ea`
- `FLTMGR!FltQueryInformationFile` at `0x14005d161`
- `FLTMGR!FltQueryInformationFile` at `0x14005d4ea`

## pseudocode

```c
__int64 __fastcall HsmpLoadPropertyStream(__int64 a1, __int64 a2, struct _FILE_OBJECT *a3, __int64 a4, char a5)
{
  struct _FLT_INSTANCE *v5; // rsi
  char v6; // al
  struct _FILE_OBJECT *v7; // r12
  char v8; // r11
  _BYTE *v9; // r15
  __int64 v10; // r13
  char v11; // dl
  char v12; // r9
  struct _FILE_OBJECT *v13; // r10
  char v14; // r8
  __int64 v15; // rbx
  __int64 v16; // rdi
  char v17; // al
  struct _ERESOURCE *v18; // rbx
  _DWORD *v19; // rax
  char v20; // si
  int *v21; // r14
  int v22; // ecx
  struct _FLT_INSTANCE *v23; // rcx
  __int64 v24; // r15
  HANDLE v25; // rbx
  __int64 v26; // r14
  USHORT v27; // ax
  PVOID v28; // rsi
  __int64 v29; // r14
  _DWORD *v30; // rax
  __int64 v31; // rdx
  struct _FLT_INSTANCE *v32; // rdx
  char v33; // si
  bool v34; // zf
  _QWORD *PoolAlignedWithTag; // rax
  unsigned int *v36; // rsi
  int v37; // ebx
  __int64 v38; // rdx
  int v39; // eax
  SIZE_T v40; // r9
  unsigned int v41; // edx
  unsigned int v42; // eax
  unsigned int v43; // ecx
  char v44; // r11
  unsigned int v45; // ebx
  unsigned int v46; // r12d
  __int64 i; // r13
  int v48; // ecx
  _BYTE *v49; // r8
  PVOID v50; // rax
  __int64 v51; // rax
  __int64 v52; // r15
  __int64 v53; // rbx
  int v54; // ecx
  __int64 v55; // rcx
  unsigned int v56; // r9d
  char *v57; // rsi
  unsigned int v58; // edx
  unsigned int v59; // r9d
  __int64 v60; // rax
  int *v61; // rdx
  unsigned int v62; // r9d
  int *j; // rax
  int **v64; // rcx
  HANDLE v65; // rax
  PDEVICE_OBJECT v67; // rcx
  __int64 v68; // rdx
  __int64 Pool2; // rax
  _QWORD *v70; // rcx
  _QWORD *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // r8
  _WORD *v74; // rax
  unsigned __int16 *v75; // rbx
  PDEVICE_OBJECT v76; // rcx
  __int64 v77; // rdx
  __int64 v78; // rax
  __int64 v79; // r9
  __int64 v80; // r9
  PDEVICE_OBJECT v81; // rcx
  __int64 v82; // rdx
  __int64 v83; // r10
  unsigned int v84; // r10d
  unsigned int v85; // eax
  unsigned int v86; // ecx
  __int64 v87; // rdx
  unsigned int v88; // r14d
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-D0h]
  char v90; // [rsp+80h] [rbp-80h]
  char v91; // [rsp+81h] [rbp-7Fh]
  char v92; // [rsp+82h] [rbp-7Eh]
  struct _FLT_INSTANCE *Instance; // [rsp+88h] [rbp-78h]
  char v94; // [rsp+90h] [rbp-70h]
  char v95; // [rsp+91h] [rbp-6Fh]
  char v96; // [rsp+92h] [rbp-6Eh]
  char v97; // [rsp+93h] [rbp-6Dh]
  char v98; // [rsp+94h] [rbp-6Ch]
  _BYTE *v100; // [rsp+A0h] [rbp-60h]
  ULONG BytesRead; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v104; // [rsp+BCh] [rbp-44h]
  union _LARGE_INTEGER ByteOffset; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE v106; // [rsp+C8h] [rbp-38h]
  PVOID v107; // [rsp+D0h] [rbp-30h]
  __int64 v108; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v109; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E8h] [rbp-18h] BYREF
  PFILE_OBJECT FileObject; // [rsp+F8h] [rbp-8h] BYREF
  void *FileHandle; // [rsp+100h] [rbp+0h] BYREF
  __int64 Buffer; // [rsp+108h] [rbp+8h] BYREF
  int *v114; // [rsp+110h] [rbp+10h]
  HANDLE v115; // [rsp+118h] [rbp+18h]
  PVOID Object; // [rsp+120h] [rbp+20h]
  __int64 FileInformation; // [rsp+128h] [rbp+28h] BYREF
  __int64 v118; // [rsp+130h] [rbp+30h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+138h] [rbp+38h] BYREF
  struct _IO_STATUS_BLOCK v120; // [rsp+168h] [rbp+68h] BYREF
  __int128 v121; // [rsp+178h] [rbp+78h] BYREF
  __int64 v122; // [rsp+188h] [rbp+88h]

  v5 = *(struct _FLT_INSTANCE **)(a1 + 32);
  v6 = 0;
  v7 = 0;
  v90 = 0;
  v8 = *(_BYTE *)(a1 + 24);
  v9 = 0;
  v10 = a4;
  v118 = a2;
  v11 = 0;
  v12 = 0;
  v104 = 2;
  Instance = v5;
  v13 = a3;
  v14 = a5;
  v15 = a1;
  v106 = 0;
  v108 = 0;
  v107 = 0;
  v109 = 0;
  ByteOffset.QuadPart = 0;
  BytesRead = 0;
  v122 = 0;
  Buffer = 0;
  v100 = 0;
  v92 = 0;
  v91 = 0;
  v98 = 0;
  v97 = 0;
  v96 = 0;
  v95 = 0;
  v94 = v8;
  v121 = 0;
  if ( v8 && a5 )
  {
    LODWORD(v16) = -1073741662;
    HsmDbgBreakOnStatus(3221225634LL);
    goto LABEL_106;
  }
  while ( 1 )
  {
    LODWORD(v16) = 0;
    if ( !v11 )
    {
      if ( v14 || v6 )
        LOBYTE(v16) = 1;
      v17 = 0;
      v18 = (struct _ERESOURCE *)(v10 + 120);
      while ( *(_QWORD *)(v10 + 224) )
      {
        v18 = (struct _ERESOURCE *)(v10 + 120);
        if ( (_BYTE)v16 )
          break;
        v18 = (struct _ERESOURCE *)(v10 + 120);
        if ( v17 )
          break;
        KeEnterCriticalRegion();
        v18 = (struct _ERESOURCE *)(v10 + 120);
        ExAcquireResourceSharedLite((PERESOURCE)(v10 + 120), 1u);
        v30 = *(_DWORD **)(v10 + 224);
        if ( v30 )
        {
          v20 = 0;
          if ( (*v30 & 3u) - 1 <= 1 )
            goto LABEL_13;
        }
        ExReleaseResourceLite((PERESOURCE)(v10 + 120));
        KeLeaveCriticalRegion();
        v17 = 1;
      }
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(v18, 1u);
      v19 = *(_DWORD **)(v10 + 224);
      v20 = 1;
      if ( v19 && !(_BYTE)v16 && (*v19 & 3u) - 1 <= 1 )
      {
        ExConvertExclusiveToSharedLite(v18);
        v20 = 0;
      }
LABEL_13:
      if ( !*(_QWORD *)(v10 + 224) )
      {
        Pool2 = ExAllocatePool2(64, 112, 1917875016);
        v70 = (_QWORD *)Pool2;
        if ( !Pool2 )
        {
          HsmDbgBreakOnStatus(3221225626LL);
          ExReleaseResourceLite((PERESOURCE)(v10 + 120));
          KeLeaveCriticalRegion();
          HsmDbgBreakOnStatus(3221225626LL);
          LODWORD(v16) = -1073741670;
          goto LABEL_105;
        }
        *(_QWORD *)(Pool2 + 8) = v10;
        v71 = (_QWORD *)(Pool2 + 64);
        v70[9] = v71;
        *v71 = v71;
        v70[11] = v70 + 10;
        v70[10] = v70 + 10;
        v70[13] = v70 + 12;
        v70[12] = v70 + 12;
        *(_QWORD *)(v10 + 224) = v70;
      }
      LODWORD(v16) = 0;
      HsmDbgBreakOnStatus(0);
      v15 = a1;
      v12 = v20;
      v14 = a5;
      v13 = a3;
      v8 = v94;
      v91 = v20;
      v5 = Instance;
      v92 = 1;
    }
    v21 = *(int **)(v10 + 224);
    v114 = v21;
    v22 = *v21;
    if ( (*(_BYTE *)v21 & 3) == 3 )
    {
      if ( v12 && !v8 )
      {
        v16 = (unsigned int)HsmpDeleteAlternateStream(v15, v13, PropertyStreamName);
        HsmDbgBreakOnStatus(v16);
        if ( (int)v16 >= 0 )
        {
          HsmiUnloadPropertyStream(v21);
          v78 = v118;
          *v21 |= 2u;
          if ( v78 )
            HsmpPersistEssentialPropPresent(v78, a3, 0);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_qqqd(
              WPP_GLOBAL_Control->AttachedDevice,
              10,
              WPP_7aae8ba2065034a53a58944ee54ad7f8_Traceguids,
              v15,
              v10,
              *(_QWORD *)(v10 + 32),
              v16);
          }
          v96 = 1;
        }
        v14 = a5;
        v13 = a3;
      }
      v22 = *v21;
      if ( (*(_BYTE *)v21 & 3) == 3 )
      {
        LODWORD(v16) = v104;
        HsmDbgBreakOnStatus(v104);
        goto LABEL_106;
      }
    }
    if ( (v22 & 1) == 0 && ((v22 & 2) == 0 || v14) )
    {
      v23 = *(struct _FLT_INSTANCE **)(v15 + 32);
      FileInformation = 0;
      v16 = (unsigned int)FltQueryInformationFile(v23, v13, &FileInformation, 8u, FileInternalInformation, 0);
      HsmDbgBreakOnStatus(v16);
      if ( (int)v16 >= 0 )
      {
        v24 = FileInformation;
        v115 = 0;
        Object = 0;
        v25 = 0;
        v26 = *(_QWORD *)(a1 + 32);
        v27 = *(_WORD *)(a1 + 64) + 8;
        DestinationString = 0;
        v28 = 0;
        FileHandle = 0;
        FileObject = 0;
        DestinationString.Length = 0;
        DestinationString.MaximumLength = v27;
        memset(&ObjectAttributes, 0, 44);
        v120 = 0;
        DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, v27, 1934979912);
        if ( DestinationString.Buffer )
        {
          HsmDbgBreakOnStatus(0);
          RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(a1 + 64));
          v31 = v26;
          v29 = a1;
          *(_QWORD *)((char *)DestinationString.Buffer + DestinationString.Length) = v24;
          DestinationString.Length += 8;
          LOBYTE(IoStatusBlock) = 0;
          v16 = (unsigned int)HsmiOpenFile(a1, v31, &DestinationString, 1048704);
          HsmDbgBreakOnStatus(v16);
          if ( (int)v16 < 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, v24);
          }
          v25 = v115;
          v28 = Object;
        }
        else
        {
          HsmDbgBreakOnStatus(3221225626LL);
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
          {
            v29 = a1;
          }
          else
          {
            v29 = a1;
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_qqd(
                WPP_GLOBAL_Control->AttachedDevice,
                27,
                WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
                a1,
                v24);
          }
          LODWORD(v16) = -1073741670;
        }
        if ( DestinationString.Buffer )
          ExFreePoolWithTag(DestinationString.Buffer, 0x73557348u);
        HsmDbgBreakOnStatus((unsigned int)v16);
        if ( (int)v16 >= 0 )
        {
          v32 = *(struct _FLT_INSTANCE **)(v29 + 32);
          ObjectAttributes.ObjectName = (PUNICODE_STRING)PropertyStreamName;
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = v25;
          ObjectAttributes.Attributes = 512;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v16 = (unsigned int)FltCreateFileEx(
                                Filter,
                                v32,
                                &FileHandle,
                                &FileObject,
                                0x110183u,
                                &ObjectAttributes,
                                &v120,
                                0,
                                0,
                                7u,
                                1u,
                                0x200020u,
                                0,
                                0,
                                0x840u);
          HsmDbgBreakOnStatus(v16);
          if ( (int)v16 >= 0 )
          {
            v7 = FileObject;
            v107 = FileObject;
            v109 = (__int64)FileObject;
            v106 = FileHandle;
            v108 = (__int64)FileHandle;
            FileObject = 0;
            FileHandle = 0;
          }
        }
        if ( v28 )
          ObfDereferenceObject(v28);
        if ( v25 )
          FltClose(v25);
        if ( FileObject )
          ObfDereferenceObject(FileObject);
        if ( FileHandle )
          FltClose(FileHandle);
        HsmDbgBreakOnStatus((unsigned int)v16);
        v21 = v114;
        v9 = v100;
        v15 = a1;
      }
      HsmDbgBreakOnStatus((unsigned int)v16);
      if ( (_DWORD)v16 == -1073741772 )
      {
        if ( !a5 )
        {
LABEL_102:
          *v21 |= 2u;
          if ( (_DWORD)v16 == -1073741772 && !a5 )
          {
            LODWORD(v16) = 0;
            HsmDbgBreakOnStatus(0);
          }
          goto LABEL_105;
        }
        v33 = 1;
        v90 = 1;
        v16 = (unsigned int)HsmpRelativeStreamOpen(
                              v15,
                              (int)a3,
                              (int)PropertyStreamName,
                              1114499,
                              5u,
                              2097184,
                              IoStatusBlock,
                              (__int64)&v108,
                              (__int64)&v109);
        HsmDbgBreakOnStatus(v16);
        v7 = (struct _FILE_OBJECT *)v109;
        v106 = (HANDLE)v108;
        v107 = (PVOID)v109;
      }
      else
      {
        v33 = v90;
      }
      if ( (int)v16 < 0 )
        goto LABEL_102;
      v16 = (unsigned int)HsmpPrepareForMgmtOperation(v15, v7, 0xFFFFFFFFLL, 0);
      HsmDbgBreakOnStatus(v16);
      if ( (int)v16 < 0 )
      {
        v76 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v77 = 11;
          goto LABEL_161;
        }
        goto LABEL_105;
      }
      *v21 |= 3u;
      v34 = v33 == 0;
      v5 = Instance;
      if ( v34 )
      {
        v16 = (unsigned int)FltQueryInformationFile(Instance, v7, &v121, 0x18u, FileStandardInformation, 0);
        HsmDbgBreakOnStatus(v16);
        if ( (int)v16 < 0 )
          goto LABEL_106;
        if ( *((_QWORD *)&v121 + 1) < 8u || *((__int64 *)&v121 + 1) > 786432 )
          goto LABEL_180;
        ByteOffset.QuadPart = 0;
        v16 = (unsigned int)FltReadFile(Instance, v7, &ByteOffset, 8u, &Buffer, 0, &BytesRead, 0, 0);
        HsmDbgBreakOnStatus(v16);
        if ( (int)v16 >= 0 )
        {
          if ( !(_BYTE)Buffer || WORD1(Buffer) < 8u || (unsigned int)WORD1(Buffer) > DWORD2(v121) && !HIDWORD(v121) )
          {
            HsmDbgBreakOnCorruption();
            LODWORD(v16) = -1073688809;
            HsmDbgBreakOnStatus(3221278487LL);
            v67 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_106;
            }
            v68 = 15;
LABEL_168:
            v80 = v15;
LABEL_169:
            WPP_SF_qqqd(
              v67->AttachedDevice,
              v68,
              WPP_7aae8ba2065034a53a58944ee54ad7f8_Traceguids,
              v80,
              v10,
              *(_QWORD *)(v10 + 32),
              v16);
            goto LABEL_106;
          }
          if ( *((__int64 *)&v121 + 1) > 786432 )
          {
LABEL_180:
            HsmDbgBreakOnCorruption();
            LODWORD(v16) = -1073688809;
            HsmDbgBreakOnStatus(3221278487LL);
            goto LABEL_106;
          }
          v21[8] = DWORD2(v121);
          *(_BYTE *)(v10 + 232) = 1;
          *(_DWORD *)(v10 + 236) = v21[8];
          PoolAlignedWithTag = FltAllocatePoolAlignedWithTag(Instance, PagedPool, (unsigned int)v21[8], 0x72507348u);
          v100 = PoolAlignedWithTag;
          v9 = PoolAlignedWithTag;
          if ( !PoolAlignedWithTag )
          {
LABEL_170:
            LODWORD(v16) = -1073741670;
            HsmDbgBreakOnStatus(3221225626LL);
            goto LABEL_106;
          }
          v36 = (unsigned int *)(PoolAlignedWithTag + 1);
          *PoolAlignedWithTag = Buffer;
          ByteOffset.QuadPart = 8;
          v16 = (unsigned int)FltReadFile(
                                Instance,
                                v7,
                                &ByteOffset,
                                v21[8] - 8,
                                PoolAlignedWithTag + 1,
                                0,
                                &BytesRead,
                                0,
                                0);
          HsmDbgBreakOnStatus(v16);
          if ( (int)v16 >= 0 )
          {
            v37 = *((_DWORD *)v9 + 1);
            v38 = *((unsigned __int16 *)v9 + 1);
            *((_DWORD *)v9 + 1) = 0;
            v39 = RtlCrc32(v9, v38, 0);
            *((_DWORD *)v9 + 1) = v37;
            if ( v37 == v39 )
            {
              if ( *v9 == 2 )
              {
                v40 = *((unsigned __int16 *)v9 + 1);
                if ( (unsigned int)v40 >= 0x10 )
                {
                  v41 = *v36;
                  if ( *v36 >= (unsigned int)v40 )
                  {
                    v42 = v21[8];
                    if ( v41 <= v42 )
                    {
                      v43 = *((_DWORD *)v9 + 3);
                      if ( v43 <= v42 - v41 )
                      {
                        v44 = v90;
                        v45 = (unsigned int)(v40 - 16) >> 3;
                        v46 = v43 + v41;
                        for ( i = 0; ; i = (unsigned int)(i + 1) )
                        {
                          if ( (unsigned int)i >= v45 || (v48 = *(_DWORD *)&v9[8 * i + 16], v49 = &v9[8 * i], !v48) )
                          {
                            v5 = Instance;
                            v50 = FltAllocatePoolAlignedWithTag(Instance, PagedPool, v40, 0x72507348u);
                            *((_QWORD *)v21 + 5) = v50;
                            if ( !v50 )
                            {
                              LODWORD(v16) = -1073741670;
                              HsmDbgBreakOnStatus(3221225626LL);
                              v10 = a4;
                              goto LABEL_106;
                            }
                            memmove(v50, v9, *((unsigned __int16 *)v9 + 1));
                            v51 = *((_QWORD *)v21 + 5) + 16LL;
                            v21[14] = v45;
                            *((_QWORD *)v21 + 6) = v51;
                            v52 = 0;
                            v21[15] = i;
                            while ( 1 )
                            {
                              if ( (unsigned int)v52 >= (unsigned int)i )
                              {
                                v10 = a4;
                                v9 = v100;
                                v7 = (struct _FILE_OBJECT *)v107;
                                v5 = Instance;
                                goto LABEL_87;
                              }
                              v53 = *(unsigned int *)&v100[8 * v52 + 20];
                              v54 = (_DWORD)v52 == v114[15] - 1
                                  ? v46
                                  : *(_DWORD *)&v100[8 * (unsigned int)(v52 + 1) + 20];
                              v55 = (unsigned int)(v54 - v53);
                              if ( (unsigned int)(v55 - 8) > 0x80000 )
                                break;
                              v56 = *(_DWORD *)&v100[v53];
                              v57 = &v100[v53];
                              v58 = v56 & 0xFFFFFF;
                              if ( (v56 & 0xFFFFFF) == 0 )
                                break;
                              if ( (v56 & 0xFFFFFF) > (unsigned __int64)(v55 - 8) )
                                break;
                              v59 = HIBYTE(v56);
                              if ( (_BYTE)v59 )
                              {
                                if ( v58 <= 4
                                  || !HsmiFindSupportedCompressionType(
                                        (unsigned __int8)v59,
                                        (unsigned __int8)v57[7],
                                        *((_DWORD *)v57 + 1) & 0xFFFFFF) )
                                {
                                  break;
                                }
                              }
                              v60 = ExAllocatePool2(256, 40, 1917875016);
                              v61 = (int *)v60;
                              if ( !v60 )
                              {
                                LODWORD(v16) = -1073741670;
                                HsmDbgBreakOnStatus(3221225626LL);
LABEL_125:
                                v10 = a4;
                                goto LABEL_126;
                              }
                              v34 = *(_QWORD *)(v60 + 32) == 0;
                              v21 = v114;
                              v62 = *(_DWORD *)&v100[8 * v52 + 16];
                              *(_DWORD *)(v60 + 16) = v62;
                              *(_DWORD *)(v60 + 20) = *(_DWORD *)&v100[8 * v52 + 20];
                              *(_QWORD *)(v60 + 24) = *(_QWORD *)v57;
                              if ( v34 )
                              {
                                for ( j = (int *)*((_QWORD *)v21 + 10); j != v21 + 20; j = *(int **)j )
                                {
                                  if ( j[4] == v62 )
                                  {
                                    *((_QWORD *)j + 5) = v61;
                                    *((_QWORD *)v61 + 4) = j;
                                    break;
                                  }
                                  if ( j[4] > v62 )
                                    break;
                                }
                              }
                              v64 = (int **)*((_QWORD *)v21 + 9);
                              if ( *v64 != v21 + 16 )
                                __fastfail(3u);
                              *(_QWORD *)v61 = v21 + 16;
                              v52 = (unsigned int)(v52 + 1);
                              *((_QWORD *)v61 + 1) = v64;
                              *v64 = v61;
                              *((_QWORD *)v21 + 9) = v61;
                            }
                            HsmDbgBreakOnCorruption();
                            LODWORD(v16) = -1073688809;
                            HsmDbgBreakOnStatus(3221278487LL);
                            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
                            {
                              goto LABEL_125;
                            }
                            v10 = a4;
                            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                            {
                              LODWORD(IoStatusBlock) = v53;
                              WPP_SF_qqiLd(WPP_GLOBAL_Control->AttachedDevice, v72, v73, a1, a4, *(_QWORD *)(a4 + 32));
                            }
LABEL_126:
                            v9 = v100;
                            goto LABEL_105;
                          }
                          v83 = 0;
                          if ( (_DWORD)i )
                            break;
                          v90 = v44;
                          if ( *((_DWORD *)v49 + 5) < v41 )
                            goto LABEL_202;
                          v90 = v44;
LABEL_198:
                          v86 = *((_DWORD *)v49 + 5);
                          if ( v86 > v46 || v46 - v86 < 8 || v86 != ((v86 + 3) & 0xFFFFFFFC) )
                            goto LABEL_202;
                        }
                        while ( *(_DWORD *)&v9[8 * v83 + 16] != v48 )
                        {
                          v83 = (unsigned int)(v83 + 1);
                          if ( (unsigned int)v83 >= (unsigned int)i )
                          {
                            v84 = *((_DWORD *)v49 + 5);
                            v85 = *(_DWORD *)&v9[8 * (unsigned int)(i - 1) + 20];
                            if ( v84 < v85 || v84 - v85 < 8 )
                              break;
                            goto LABEL_198;
                          }
                        }
LABEL_202:
                        HsmDbgBreakOnCorruption();
                        LODWORD(v16) = -1073688809;
                        HsmDbgBreakOnStatus(3221278487LL);
                        v76 = WPP_GLOBAL_Control;
                        v10 = a4;
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                        {
                          v77 = 20;
                          goto LABEL_162;
                        }
                        goto LABEL_105;
                      }
                    }
                  }
                }
                HsmDbgBreakOnCorruption();
                LODWORD(v16) = -1073688809;
                HsmDbgBreakOnStatus(3221278487LL);
                v76 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
LABEL_105:
                  v5 = Instance;
                  goto LABEL_106;
                }
                v77 = 19;
LABEL_162:
                v79 = a1;
LABEL_163:
                WPP_SF_qqqd(
                  v76->AttachedDevice,
                  v77,
                  WPP_7aae8ba2065034a53a58944ee54ad7f8_Traceguids,
                  v79,
                  v10,
                  *(_QWORD *)(v10 + 32),
                  v16);
                goto LABEL_105;
              }
              HsmDbgBreakOnCorruption();
              LODWORD(v16) = -1073688826;
              HsmDbgBreakOnStatus(3221278470LL);
              v81 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_105;
              }
              v82 = 18;
            }
            else
            {
              HsmDbgBreakOnCorruption();
              LODWORD(v16) = -1073688809;
              HsmDbgBreakOnStatus(3221278487LL);
              v81 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_105;
              }
              v82 = 17;
            }
            LODWORD(IoStatusBlock) = (unsigned __int8)*v9;
            WPP_SF_qqiDd(
              v81->AttachedDevice,
              v82,
              WPP_7aae8ba2065034a53a58944ee54ad7f8_Traceguids,
              a1,
              v10,
              *(_QWORD *)(v10 + 32));
            goto LABEL_105;
          }
          v76 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_105;
          }
          v77 = 16;
LABEL_161:
          v79 = v15;
          goto LABEL_163;
        }
        v67 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v68 = 14;
          goto LABEL_168;
        }
      }
      else
      {
        *(_QWORD *)&v121 = 32;
        v16 = (unsigned int)FltSetInformationFile(Instance, v7, &v121, 8u, FileEndOfFileInformation);
        HsmDbgBreakOnStatus(v16);
        if ( (int)v16 < 0 )
        {
          v67 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v68 = 12;
            goto LABEL_168;
          }
        }
        else
        {
          v21[8] = v121;
          *(_BYTE *)(v10 + 232) = 1;
          *(_DWORD *)(v10 + 236) = v21[8];
          v74 = FltAllocatePoolAlignedWithTag(Instance, PagedPool, 0x20u, 0x72507348u);
          v100 = v74;
          v75 = v74;
          v9 = v74;
          if ( !v74 )
            goto LABEL_170;
          *((_DWORD *)v74 + 1) = 0;
          *((_QWORD *)v74 + 2) = 0;
          *((_QWORD *)v74 + 3) = 0;
          *v74 = 2;
          v74[1] = 32;
          *((_QWORD *)v74 + 1) = 32;
          *((_DWORD *)v74 + 1) = RtlCrc32(v74, 32, 0);
          ByteOffset.QuadPart = 0;
          LODWORD(v16) = FltWriteFile(Instance, v7, &ByteOffset, v75[1], v75, 0, &BytesRead, 0, 0);
          if ( (int)v16 >= 0 )
          {
            v9 = 0;
            *((_QWORD *)v21 + 5) = v75;
            v100 = 0;
            *((_QWORD *)v21 + 6) = v75 + 8;
            *((_QWORD *)v21 + 7) = 0;
LABEL_87:
            v65 = v106;
            *v21 &= ~2u;
            *((_QWORD *)v21 + 2) = v65;
            v106 = 0;
            v108 = 0;
            *((_QWORD *)v21 + 3) = v7;
            goto LABEL_88;
          }
          v67 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v80 = a1;
            v68 = 13;
            goto LABEL_169;
          }
        }
      }
    }
LABEL_106:
    if ( v106 )
    {
      FltClose(v106);
      v106 = 0;
      v108 = 0;
    }
    v7 = (struct _FILE_OBJECT *)v107;
    if ( v107 )
    {
      ObfDereferenceObject(v107);
LABEL_88:
      v7 = 0;
      v109 = 0;
      v107 = 0;
    }
    if ( v9 )
    {
      FltFreePoolAlignedWithTag(v5, v9, 0x72507348u);
      v9 = 0;
      v100 = 0;
    }
    if ( (_DWORD)v16 != -1073688809 && (_DWORD)v16 != -1073688826 )
      goto LABEL_93;
    v15 = a1;
    if ( v95 )
    {
      v88 = v104;
    }
    else
    {
      v87 = *(_QWORD *)(v10 + 32);
      v104 = v16;
      v88 = v16;
      HsmpReportCorruption(a1, v87, (unsigned int)v16);
      v95 = 1;
    }
    v12 = v91;
    if ( v91 )
    {
      if ( v97 )
        break;
    }
    v8 = v94;
    if ( v94 || v96 )
      break;
    if ( v91 )
    {
      v11 = v92;
      v14 = a5;
      v13 = a3;
      v6 = v98;
      v97 = 1;
    }
    else
    {
      ExReleaseResourceLite((PERESOURCE)(v10 + 120));
      KeLeaveCriticalRegion();
      v14 = a5;
      v12 = 0;
      v13 = a3;
      v11 = 0;
      v8 = 0;
      v6 = 1;
      v92 = 0;
      v91 = 0;
      v98 = 1;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqqd(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      WPP_7aae8ba2065034a53a58944ee54ad7f8_Traceguids,
      a1,
      v10,
      *(_QWORD *)(v10 + 32),
      v88);
LABEL_93:
    v12 = v91;
  }
  if ( v92 )
  {
    if ( (int)v16 < 0 )
    {
      ExReleaseResourceLite((PERESOURCE)(v10 + 120));
      KeLeaveCriticalRegion();
    }
    else if ( v12 && !a5 )
    {
      ExConvertExclusiveToSharedLite((PERESOURCE)(v10 + 120));
    }
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14005cf90  push    rbp
0x14005cf92  push    rbx
0x14005cf93  push    rsi
0x14005cf94  push    rdi
0x14005cf95  push    r12
0x14005cf97  push    r13
0x14005cf99  push    r14
0x14005cf9b  push    r15
0x14005cf9d  lea     rbp, [rsp-0A8h]
0x14005cfa5  sub     rsp, 1A8h
0x14005cfac  mov     rax, cs:__security_cookie
0x14005cfb3  xor     rax, rsp
0x14005cfb6  mov     [rbp+0E0h+var_50], rax
0x14005cfbd  mov     rsi, [rcx+20h]
0x14005cfc1  xor     eax, eax
0x14005cfc3  xor     r11b, r11b
0x14005cfc6  mov     [rbp+0E0h+var_138], r9
0x14005cfca  xor     r12d, r12d
0x14005cfcd  mov     [rbp+0E0h+var_160], r11b
0x14005cfd1  movzx   r11d, byte ptr [rcx+18h]
0x14005cfd6  xor     r15d, r15d
0x14005cfd9  mov     r13, r9
0x14005cfdc  mov     [rbp+0E0h+var_B0], rdx
0x14005cfe0  xor     dl, dl
0x14005cfe2  mov     qword ptr [rbp+0E0h+var_130], r8
0x14005cfe6  xor     r9b, r9b
0x14005cfe9  mov     [rbp+0E0h+var_148], rcx
0x14005cfed  mov     [rbp+0E0h+var_124], 2
0x14005cff4  xorps   xmm0, xmm0
0x14005cff7  mov     [rbp+0E0h+Instance], rsi
0x14005cffb  mov     r10, r8
0x14005cffe  movzx   r8d, [rbp+0E0h+arg_20]
0x14005d006  mov     rbx, rcx
0x14005d009  mov     [rbp+0E0h+var_118], rax
0x14005d00d  mov     [rbp+0E0h+var_108], rax
0x14005d011  mov     [rbp+0E0h+var_110], r12
0x14005d015  mov     [rbp+0E0h+var_100], r12
0x14005d019  mov     qword ptr [rbp+0E0h+ByteOffset], rax
0x14005d01d  mov     [rbp+0E0h+BytesRead], eax
0x14005d020  mov     [rbp+0E0h+var_58], rax
0x14005d027  mov     [rbp+0E0h+Buffer], rax
0x14005d02b  mov     [rbp+0E0h+var_140], r15
0x14005d02f  mov     [rbp+0E0h+var_15E], dl
0x14005d032  mov     [rbp+0E0h+var_15F], r9b
0x14005d036  mov     [rbp+0E0h+var_14C], al
0x14005d039  mov     [rbp+0E0h+var_14D], al
0x14005d03c  mov     [rbp+0E0h+var_14E], al
0x14005d03f  mov     [rbp+0E0h+var_14F], al
0x14005d042  mov     [rbp+0E0h+var_150], r11b
0x14005d046  movups  [rbp+0E0h+var_68], xmm0
0x14005d04a  test    r11b, r11b
0x14005d04d  jnz     loc_14005D970
0x14005d053  xor     edi, edi
0x14005d055  test    dl, dl
0x14005d057  jnz     loc_14005D110
0x14005d05d  test    r8b, r8b
0x14005d060  jnz     loc_14005D90B
0x14005d066  test    al, al
0x14005d068  jnz     loc_14005D90B
0x14005d06e  xor     al, al
0x14005d070  lea     rbx, [r13+78h]
0x14005d074  cmp     qword ptr [r13+0E0h], 0
0x14005d07c  jz      short loc_14005D093
0x14005d07e  lea     rbx, [r13+78h]
0x14005d082  test    dil, dil
0x14005d085  jnz     short loc_14005D093
0x14005d087  lea     rbx, [r13+78h]
0x14005d08b  test    al, al
0x14005d08d  jz      loc_14005D257
0x14005d093  call    cs:__imp_KeEnterCriticalRegion
0x14005d09a  nop     dword ptr [rax+rax+00h]
0x14005d09f  mov     dl, 1; Wait
0x14005d0a1  mov     rcx, rbx; Resource
0x14005d0a4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005d0ab  nop     dword ptr [rax+rax+00h]
0x14005d0b0  mov     rax, [r13+0E0h]
0x14005d0b7  mov     sil, 1
0x14005d0ba  test    rax, rax
0x14005d0bd  jz      short loc_14005D0D4
0x14005d0bf  test    dil, dil
0x14005d0c2  jnz     short loc_14005D0D4
0x14005d0c4  mov     eax, [rax]
0x14005d0c6  and     eax, 3
0x14005d0c9  dec     eax
0x14005d0cb  cmp     eax, 1
0x14005d0ce  jbe     loc_14005DA9F
0x14005d0d4  cmp     qword ptr [r13+0E0h], 0
0x14005d0dc  jz      loc_14005D9B1
0x14005d0e2  xor     edi, edi
0x14005d0e4  mov     ecx, edi
0x14005d0e6  call    HsmDbgBreakOnStatus
0x14005d0eb  mov     rbx, [rbp+0E0h+var_148]
0x14005d0ef  movzx   r9d, sil
0x14005d0f3  movzx   r8d, [rbp+0E0h+arg_20]
0x14005d0fb  mov     r10, qword ptr [rbp+0E0h+var_130]
0x14005d0ff  movzx   r11d, [rbp+0E0h+var_150]
0x14005d104  mov     [rbp+0E0h+var_15F], sil
0x14005d108  mov     rsi, [rbp+0E0h+Instance]
0x14005d10c  mov     [rbp+0E0h+var_15E], 1
0x14005d110  mov     r14, [r13+0E0h]
0x14005d117  mov     [rbp+0E0h+var_D0], r14
0x14005d11b  mov     ecx, [r14]
0x14005d11e  mov     eax, ecx
0x14005d120  and     eax, 3
0x14005d123  cmp     al, 3
0x14005d125  jz      loc_14005DC74
0x14005d12b  test    cl, 1
0x14005d12e  jnz     loc_14005D942
0x14005d134  test    cl, 2
0x14005d137  jnz     loc_14005DABD
0x14005d13d  mov     rcx, [rbx+20h]; Instance
0x14005d141  lea     r8, [rbp+0E0h+FileInformation]; FileInformation
0x14005d145  xor     eax, eax
0x14005d147  mov     r9d, 8; Length
0x14005d14d  mov     [rsp+1E0h+LengthReturned], rax; LengthReturned
0x14005d152  mov     rdx, r10; FileObject
0x14005d155  mov     [rsp+1E0h+FileInformationClass], 6; FileInformationClass
0x14005d15d  mov     [rbp+0E0h+FileInformation], rax
0x14005d161  call    cs:__imp_FltQueryInformationFile
0x14005d168  nop     dword ptr [rax+rax+00h]
0x14005d16d  mov     ecx, eax
0x14005d16f  mov     edi, eax
0x14005d171  call    HsmDbgBreakOnStatus
0x14005d176  test    edi, edi
0x14005d178  js      loc_14005D474
0x14005d17e  mov     r9, [rbp+0E0h+var_148]
0x14005d182  xor     ecx, ecx
0x14005d184  mov     r15, [rbp+0E0h+FileInformation]
0x14005d188  lea     rdi, [r9+40h]
0x14005d18c  xorps   xmm0, xmm0
0x14005d18f  mov     [rbp+0E0h+var_C8], rcx
0x14005d193  xor     eax, eax
0x14005d195  mov     [rbp+0E0h+Object], rcx
0x14005d199  movzx   eax, word ptr [rdi]
0x14005d19c  mov     ebx, ecx
0x14005d19e  mov     r14, [r9+20h]
0x14005d1a2  add     ax, 8
0x14005d1a6  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x14005d1aa  movzx   edx, ax
0x14005d1ad  mov     esi, ecx
0x14005d1af  mov     [rbp+0E0h+FileHandle], rcx
0x14005d1b3  mov     r8d, 73557348h
0x14005d1b9  mov     [rbp+0E0h+FileObject], rcx
0x14005d1bd  mov     [rbp+0E0h+DestinationString.Length], cx
0x14005d1c1  mov     ecx, 100h
0x14005d1c6  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.ObjectName], xmm0
0x14005d1ca  mov     [rbp+0E0h+DestinationString.MaximumLength], dx
0x14005d1ce  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.Length], xmm0
0x14005d1d2  movups  xmmword ptr [rbp+0E0h+ObjectAttributes+1Ch], xmm0
0x14005d1d6  movups  xmmword ptr [rbp+0E0h+var_78], xmm0
0x14005d1da  call    cs:__imp_ExAllocatePool2
0x14005d1e1  nop     dword ptr [rax+rax+00h]
0x14005d1e6  mov     [rbp+0E0h+DestinationString.Buffer], rax
0x14005d1ea  test    rax, rax
0x14005d1ed  jnz     loc_14005D2B9
0x14005d1f3  mov     ecx, 0C000009Ah
0x14005d1f8  call    HsmDbgBreakOnStatus
0x14005d1fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d204  lea     rax, WPP_GLOBAL_Control
0x14005d20b  cmp     rcx, rax
0x14005d20e  jz      loc_14005DD99
0x14005d214  mov     eax, [rcx+2Ch]
0x14005d217  test    al, 8
0x14005d219  jz      loc_14005DD99
0x14005d21f  cmp     byte ptr [rcx+29h], 2
0x14005d223  mov     r14, [rbp+0E0h+var_148]
0x14005d227  jb      loc_14005DD9D
0x14005d22d  mov     rcx, [rcx+18h]
0x14005d231  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005d238  mov     edx, 1Bh
0x14005d23d  mov     dword ptr [rsp+1E0h+LengthReturned], 0C000009Ah
0x14005d245  mov     r9, r14
0x14005d248  mov     qword ptr [rsp+1E0h+FileInformationClass], r15
0x14005d24d  call    WPP_SF_qqd
0x14005d252  jmp     loc_14005DD9D
0x14005d257  call    cs:__imp_KeEnterCriticalRegion
0x14005d25e  nop     dword ptr [rax+rax+00h]
0x14005d263  lea     rbx, [r13+78h]
0x14005d267  mov     dl, 1; Wait
0x14005d269  mov     rcx, rbx; Resource
0x14005d26c  call    cs:__imp_ExAcquireResourceSharedLite
0x14005d273  nop     dword ptr [rax+rax+00h]
0x14005d278  mov     rax, [r13+0E0h]
0x14005d27f  test    rax, rax
0x14005d282  jz      short loc_14005D297
0x14005d284  mov     ecx, [rax]
0x14005d286  xor     sil, sil
0x14005d289  and     ecx, 3
0x14005d28c  dec     ecx
0x14005d28e  cmp     ecx, 1
0x14005d291  jbe     loc_14005D0D4
0x14005d297  mov     rcx, rbx; Resource
0x14005d29a  call    cs:__imp_ExReleaseResourceLite
0x14005d2a1  nop     dword ptr [rax+rax+00h]
0x14005d2a6  call    cs:__imp_KeLeaveCriticalRegion
0x14005d2ad  nop     dword ptr [rax+rax+00h]
0x14005d2b2  mov     al, 1
0x14005d2b4  jmp     loc_14005D074
0x14005d2b9  xor     ecx, ecx
0x14005d2bb  call    HsmDbgBreakOnStatus
0x14005d2c0  mov     rdx, rdi; SourceString
0x14005d2c3  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x14005d2c7  call    cs:__imp_RtlCopyUnicodeString
0x14005d2ce  nop     dword ptr [rax+rax+00h]
0x14005d2d3  movzx   ecx, [rbp+0E0h+DestinationString.Length]
0x14005d2d7  lea     r8, [rbp+0E0h+DestinationString]
0x14005d2db  mov     rax, [rbp+0E0h+DestinationString.Buffer]
0x14005d2df  mov     rdx, r14
0x14005d2e2  mov     r14, [rbp+0E0h+var_148]
0x14005d2e6  mov     r9d, 100080h
0x14005d2ec  mov     [rcx+rax], r15
0x14005d2f0  lea     rax, [rbp+0E0h+Object]
0x14005d2f4  add     [rbp+0E0h+DestinationString.Length], 8
0x14005d2f9  mov     rcx, r14
0x14005d2fc  mov     qword ptr [rsp+1E0h+FileAttributes], rax
0x14005d301  lea     rax, [rbp+0E0h+var_C8]
0x14005d305  mov     [rsp+1E0h+AllocationSize], rax
0x14005d30a  mov     byte ptr [rsp+1E0h+IoStatusBlock], bl
0x14005d30e  mov     dword ptr [rsp+1E0h+LengthReturned], 202100h
0x14005d316  call    HsmiOpenFile
0x14005d31b  mov     ecx, eax
0x14005d31d  mov     edi, eax
0x14005d31f  call    HsmDbgBreakOnStatus
0x14005d324  test    edi, edi
0x14005d326  js      loc_14005DD47
0x14005d32c  mov     rbx, [rbp+0E0h+var_C8]
0x14005d330  mov     rsi, [rbp+0E0h+Object]
0x14005d334  mov     rcx, [rbp+0E0h+DestinationString.Buffer]; P
0x14005d338  test    rcx, rcx
0x14005d33b  jz      short loc_14005D34E
0x14005d33d  mov     edx, 73557348h; Tag
0x14005d342  call    cs:__imp_ExFreePoolWithTag
0x14005d349  nop     dword ptr [rax+rax+00h]
0x14005d34e  mov     ecx, edi
0x14005d350  call    HsmDbgBreakOnStatus
0x14005d355  test    edi, edi
0x14005d357  js      loc_14005D41F
0x14005d35d  mov     rdx, [r14+20h]; Instance
0x14005d361  lea     rax, PropertyStreamName; "bd"
0x14005d368  mov     rcx, cs:Filter; Filter
0x14005d36f  lea     r9, [rbp+0E0h+FileObject]; FileObject
0x14005d373  mov     [rsp+1E0h+Flags], 840h; Flags
0x14005d37b  lea     r8, [rbp+0E0h+FileHandle]; FileHandle
0x14005d37f  xor     r15d, r15d
0x14005d382  mov     [rbp+0E0h+ObjectAttributes.ObjectName], rax
0x14005d386  mov     [rsp+1E0h+EaLength], r15d; EaLength
0x14005d38b  lea     rax, [rbp+0E0h+var_78]
0x14005d38f  mov     [rsp+1E0h+EaBuffer], r15; EaBuffer
0x14005d394  xorps   xmm0, xmm0
0x14005d397  mov     [rsp+1E0h+CreateOptions], 200020h; CreateOptions
0x14005d39f  mov     [rsp+1E0h+CreateDisposition], 1; CreateDisposition
0x14005d3a7  mov     [rsp+1E0h+ShareAccess], 7; ShareAccess
0x14005d3af  mov     [rsp+1E0h+FileAttributes], r15d; FileAttributes
0x14005d3b4  mov     [rsp+1E0h+AllocationSize], r15; AllocationSize
0x14005d3b9  mov     [rsp+1E0h+IoStatusBlock], rax; FileHandle
0x14005d3be  lea     rax, [rbp+0E0h+ObjectAttributes]
0x14005d3c2  mov     [rsp+1E0h+LengthReturned], rax; ObjectAttributes
0x14005d3c7  mov     [rsp+1E0h+FileInformationClass], 110183h; DesiredAccess
0x14005d3cf  mov     [rbp+0E0h+ObjectAttributes.Length], 30h ; '0'
0x14005d3d6  mov     [rbp+0E0h+ObjectAttributes.RootDirectory], rbx
0x14005d3da  mov     [rbp+0E0h+ObjectAttributes.Attributes], 200h
0x14005d3e1  movdqu  xmmword ptr [rbp+0E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005d3e6  call    cs:__imp_FltCreateFileEx
0x14005d3ed  nop     dword ptr [rax+rax+00h]
0x14005d3f2  mov     ecx, eax
0x14005d3f4  mov     edi, eax
0x14005d3f6  call    HsmDbgBreakOnStatus
0x14005d3fb  test    edi, edi
0x14005d3fd  js      short loc_14005D41F
0x14005d3ff  mov     r12, [rbp+0E0h+FileObject]
0x14005d403  mov     rax, [rbp+0E0h+FileHandle]
0x14005d407  mov     [rbp+0E0h+var_110], r12
0x14005d40b  mov     [rbp+0E0h+var_100], r12
0x14005d40f  mov     [rbp+0E0h+var_118], rax
0x14005d413  mov     [rbp+0E0h+var_108], rax
0x14005d417  mov     [rbp+0E0h+FileObject], r15
0x14005d41b  mov     [rbp+0E0h+FileHandle], r15
0x14005d41f  test    rsi, rsi
0x14005d422  jz      short loc_14005D433
0x14005d424  mov     rcx, rsi; Object
0x14005d427  call    cs:__imp_ObfDereferenceObject
0x14005d42e  nop     dword ptr [rax+rax+00h]
0x14005d433  test    rbx, rbx
0x14005d436  jz      short loc_14005D447
0x14005d438  mov     rcx, rbx; FileHandle
0x14005d43b  call    cs:__imp_FltClose
0x14005d442  nop     dword ptr [rax+rax+00h]
0x14005d447  mov     rcx, [rbp+0E0h+FileObject]; Object
0x14005d44b  test    rcx, rcx
0x14005d44e  jnz     loc_14005DDA7
0x14005d454  mov     rcx, [rbp+0E0h+FileHandle]; FileHandle
0x14005d458  test    rcx, rcx
0x14005d45b  jnz     loc_14005DDB8
0x14005d461  mov     ecx, edi
0x14005d463  call    HsmDbgBreakOnStatus
0x14005d468  mov     r14, [rbp+0E0h+var_D0]
0x14005d46c  mov     r15, [rbp+0E0h+var_140]
0x14005d470  mov     rbx, [rbp+0E0h+var_148]
0x14005d474  mov     ecx, edi
0x14005d476  call    HsmDbgBreakOnStatus
  ... truncated ...
```
