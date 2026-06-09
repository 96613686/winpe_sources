# HsmpLoadPropertyStream

- ea: `0x14005d0b0`
- end: `0x14005e3e0`
- name: `HsmpLoadPropertyStream`
- size: `4912`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14004a63c`
- `0x14005074c`

## callees

- `0x140001b00`
- `0x140003c50`
- `0x140009300`
- `0x14000abb8`
- `0x14000db8c`
- `0x14001accc`
- `0x14001e1c0`
- `0x14001e300`
- `0x140035610`
- `0x1400431dc`
- `0x14004c7f8`
- `0x14005ce40`
- `0x14005d0b0`
- `0x14005e3f0`
- `0x14005ec60`
- `0x14005f2b4`
- `0x14007e550`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14005d3e7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005d3e7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005d38c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005d38c`
- `ntoskrnl!RtlCrc32` at `0x14005d787`
- `ntoskrnl!RtlCrc32` at `0x14005dc92`
- `ntoskrnl!RtlCrc32` at `0x14005d787`
- `ntoskrnl!RtlCrc32` at `0x14005dc92`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14005d9f9`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14005dbc2`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14005d9f9`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14005dbc2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005d3c6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005dd74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e313`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e3cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005d3c6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005dd74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e313`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e3cf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d3ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dd68`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e307`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e3c3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d3ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dd68`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e307`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e3c3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005d1c4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005d1c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005d1b3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005d377`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005d1b3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005d377`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d547`
- `ntoskrnl!ObfDereferenceObject` at `0x14005da7f`
- `ntoskrnl!ObfDereferenceObject` at `0x14005dec7`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d547`
- `ntoskrnl!ObfDereferenceObject` at `0x14005da7f`
- `ntoskrnl!ObfDereferenceObject` at `0x14005dec7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d462`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d462`
- `ntoskrnl!ExAllocatePool2` at `0x14005d2fa`
- `ntoskrnl!ExAllocatePool2` at `0x14005d8db`
- `ntoskrnl!ExAllocatePool2` at `0x14005dae1`
- `ntoskrnl!ExAllocatePool2` at `0x14005d2fa`
- `ntoskrnl!ExAllocatePool2` at `0x14005d8db`
- `ntoskrnl!ExAllocatePool2` at `0x14005dae1`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x14005d9a9`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x14005d9a9`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14005d6f3`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14005d81b`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14005dc4c`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14005d6f3`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14005d81b`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14005dc4c`
- `FLTMGR!FltSetInformationFile` at `0x14005dc01`
- `FLTMGR!FltSetInformationFile` at `0x14005dc01`
- `FLTMGR!FltCreateFileEx` at `0x14005d506`
- `FLTMGR!FltCreateFileEx` at `0x14005d506`
- `FLTMGR!FltWriteFile` at `0x14005dcd0`
- `FLTMGR!FltWriteFile` at `0x14005dcd0`
- `FLTMGR!FltReadFile` at `0x14005d67a`
- `FLTMGR!FltReadFile` at `0x14005d753`
- `FLTMGR!FltReadFile` at `0x14005d67a`
- `FLTMGR!FltReadFile` at `0x14005d753`
- `FLTMGR!FltClose` at `0x14005d55b`
- `FLTMGR!FltClose` at `0x14005ded8`
- `FLTMGR!FltClose` at `0x14005e29a`
- `FLTMGR!FltClose` at `0x14005d55b`
- `FLTMGR!FltClose` at `0x14005ded8`
- `FLTMGR!FltClose` at `0x14005e29a`
- `FLTMGR!FltQueryInformationFile` at `0x14005d281`
- `FLTMGR!FltQueryInformationFile` at `0x14005d60a`
- `FLTMGR!FltQueryInformationFile` at `0x14005d281`
- `FLTMGR!FltQueryInformationFile` at `0x14005d60a`

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
  int v16; // edi
  char v17; // al
  struct _ERESOURCE *v18; // rbx
  _DWORD *v19; // rax
  char v20; // si
  int *v21; // r14
  int v22; // ecx
  struct _FLT_INSTANCE *v23; // rcx
  __int64 v24; // r15
  HANDLE v25; // rbx
  struct _FLT_INSTANCE *v26; // r14
  USHORT v27; // ax
  PVOID v28; // rsi
  __int64 v29; // r14
  _DWORD *v30; // rax
  struct _FLT_INSTANCE *v31; // rdx
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
  int v88; // r14d
  __int64 FileInformationClass; // [rsp+20h] [rbp-E0h]
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-D0h]
  char v91; // [rsp+80h] [rbp-80h]
  char v92; // [rsp+81h] [rbp-7Fh]
  char v93; // [rsp+82h] [rbp-7Eh]
  struct _FLT_INSTANCE *Instance; // [rsp+88h] [rbp-78h]
  char v95; // [rsp+90h] [rbp-70h]
  char v96; // [rsp+91h] [rbp-6Fh]
  char v97; // [rsp+92h] [rbp-6Eh]
  char v98; // [rsp+93h] [rbp-6Dh]
  char v99; // [rsp+94h] [rbp-6Ch]
  _BYTE *v101; // [rsp+A0h] [rbp-60h]
  ULONG BytesRead; // [rsp+B8h] [rbp-48h] BYREF
  int v105; // [rsp+BCh] [rbp-44h]
  union _LARGE_INTEGER ByteOffset; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE v107; // [rsp+C8h] [rbp-38h]
  PVOID v108; // [rsp+D0h] [rbp-30h]
  __int64 v109; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v110; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E8h] [rbp-18h] BYREF
  PFILE_OBJECT FileObject; // [rsp+F8h] [rbp-8h] BYREF
  void *FileHandle; // [rsp+100h] [rbp+0h] BYREF
  __int64 Buffer; // [rsp+108h] [rbp+8h] BYREF
  int *v115; // [rsp+110h] [rbp+10h]
  HANDLE v116; // [rsp+118h] [rbp+18h] BYREF
  PVOID Object; // [rsp+120h] [rbp+20h] BYREF
  __int64 FileInformation; // [rsp+128h] [rbp+28h] BYREF
  __int64 v119; // [rsp+130h] [rbp+30h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+138h] [rbp+38h] BYREF
  struct _IO_STATUS_BLOCK v121; // [rsp+168h] [rbp+68h] BYREF
  __int128 v122; // [rsp+178h] [rbp+78h] BYREF
  __int64 v123; // [rsp+188h] [rbp+88h]

  v5 = *(struct _FLT_INSTANCE **)(a1 + 32);
  v6 = 0;
  v7 = 0;
  v91 = 0;
  v8 = *(_BYTE *)(a1 + 24);
  v9 = 0;
  v10 = a4;
  v119 = a2;
  v11 = 0;
  v12 = 0;
  v105 = 2;
  Instance = v5;
  v13 = a3;
  v14 = a5;
  v15 = a1;
  v107 = 0;
  v109 = 0;
  v108 = 0;
  v110 = 0;
  ByteOffset.QuadPart = 0;
  BytesRead = 0;
  v123 = 0;
  Buffer = 0;
  v101 = 0;
  v93 = 0;
  v92 = 0;
  v99 = 0;
  v98 = 0;
  v97 = 0;
  v96 = 0;
  v95 = v8;
  v122 = 0;
  if ( v8 && a5 )
  {
    v16 = -1073741662;
    HsmDbgBreakOnStatus(-1073741662);
    goto LABEL_106;
  }
  while ( 1 )
  {
    v16 = 0;
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
          HsmDbgBreakOnStatus(-1073741670);
          ExReleaseResourceLite((PERESOURCE)(v10 + 120));
          KeLeaveCriticalRegion();
          HsmDbgBreakOnStatus(-1073741670);
          v16 = -1073741670;
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
      v16 = 0;
      HsmDbgBreakOnStatus(0);
      v15 = a1;
      v12 = v20;
      v14 = a5;
      v13 = a3;
      v8 = v95;
      v92 = v20;
      v5 = Instance;
      v93 = 1;
    }
    v21 = *(int **)(v10 + 224);
    v115 = v21;
    v22 = *v21;
    if ( (*(_BYTE *)v21 & 3) == 3 )
    {
      if ( v12 && !v8 )
      {
        v16 = HsmpDeleteAlternateStream(v15, v13, PropertyStreamName);
        HsmDbgBreakOnStatus(v16);
        if ( v16 >= 0 )
        {
          HsmiUnloadPropertyStream(v21);
          v78 = v119;
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
          v97 = 1;
        }
        v14 = a5;
        v13 = a3;
      }
      v22 = *v21;
      if ( (*(_BYTE *)v21 & 3) == 3 )
      {
        v16 = v105;
        HsmDbgBreakOnStatus(v105);
        goto LABEL_106;
      }
    }
    if ( (v22 & 1) == 0 && ((v22 & 2) == 0 || v14) )
    {
      v23 = *(struct _FLT_INSTANCE **)(v15 + 32);
      FileInformation = 0;
      v16 = FltQueryInformationFile(v23, v13, &FileInformation, 8u, FileInternalInformation, 0);
      HsmDbgBreakOnStatus(v16);
      if ( v16 >= 0 )
      {
        v24 = FileInformation;
        v116 = 0;
        Object = 0;
        v25 = 0;
        v26 = *(struct _FLT_INSTANCE **)(a1 + 32);
        v27 = *(_WORD *)(a1 + 64) + 8;
        DestinationString = 0;
        v28 = 0;
        FileHandle = 0;
        FileObject = 0;
        DestinationString.Length = 0;
        DestinationString.MaximumLength = v27;
        memset(&ObjectAttributes, 0, 44);
        v121 = 0;
        DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, v27, 1934979912);
        if ( DestinationString.Buffer )
        {
          HsmDbgBreakOnStatus(0);
          RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(a1 + 64));
          v31 = v26;
          v29 = a1;
          *(_QWORD *)((char *)DestinationString.Buffer + DestinationString.Length) = v24;
          DestinationString.Length += 8;
          v16 = HsmiOpenFile(
                  a1,
                  v31,
                  &DestinationString,
                  0x100080u,
                  FileInformationClass,
                  0x202100u,
                  0,
                  &v116,
                  (PFILE_OBJECT *)&Object);
          HsmDbgBreakOnStatus(v16);
          if ( v16 < 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqd(
              WPP_GLOBAL_Control->AttachedDevice,
              28,
              WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
              a1,
              v24,
              v16);
          }
          v25 = v116;
          v28 = Object;
        }
        else
        {
          HsmDbgBreakOnStatus(-1073741670);
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
                v24,
                -1073741670);
          }
          v16 = -1073741670;
        }
        if ( DestinationString.Buffer )
          ExFreePoolWithTag(DestinationString.Buffer, 0x73557348u);
        HsmDbgBreakOnStatus(v16);
        if ( v16 >= 0 )
        {
          v32 = *(struct _FLT_INSTANCE **)(v29 + 32);
          ObjectAttributes.ObjectName = (PUNICODE_STRING)PropertyStreamName;
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = v25;
          ObjectAttributes.Attributes = 512;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v16 = FltCreateFileEx(
                  Filter,
                  v32,
                  &FileHandle,
                  &FileObject,
                  0x110183u,
                  &ObjectAttributes,
                  &v121,
                  0,
                  0,
                  7u,
                  1u,
                  0x200020u,
                  0,
                  0,
                  0x840u);
          HsmDbgBreakOnStatus(v16);
          if ( v16 >= 0 )
          {
            v7 = FileObject;
            v108 = FileObject;
            v110 = (__int64)FileObject;
            v107 = FileHandle;
            v109 = (__int64)FileHandle;
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
        HsmDbgBreakOnStatus(v16);
        v21 = v115;
        v9 = v101;
        v15 = a1;
      }
      HsmDbgBreakOnStatus(v16);
      if ( v16 == -1073741772 )
      {
        if ( !a5 )
        {
LABEL_102:
          *v21 |= 2u;
          if ( v16 == -1073741772 && !a5 )
          {
            v16 = 0;
            HsmDbgBreakOnStatus(0);
          }
          goto LABEL_105;
        }
        v33 = 1;
        v91 = 1;
        v16 = HsmpRelativeStreamOpen(
                v15,
                (int)a3,
                (int)PropertyStreamName,
                1114499,
                5u,
                2097184,
                IoStatusBlock,
                (__int64)&v109,
                (__int64)&v110);
        HsmDbgBreakOnStatus(v16);
        v7 = (struct _FILE_OBJECT *)v110;
        v107 = (HANDLE)v109;
        v108 = (PVOID)v110;
      }
      else
      {
        v33 = v91;
      }
      if ( v16 < 0 )
        goto LABEL_102;
      v16 = HsmpPrepareForMgmtOperation(v15, v7, 0xFFFFFFFFLL);
      HsmDbgBreakOnStatus(v16);
      if ( v16 < 0 )
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
        v16 = FltQueryInformationFile(Instance, v7, &v122, 0x18u, FileStandardInformation, 0);
        HsmDbgBreakOnStatus(v16);
        if ( v16 < 0 )
          goto LABEL_106;
        if ( *((_QWORD *)&v122 + 1) < 8u || *((__int64 *)&v122 + 1) > 786432 )
          goto LABEL_180;
        ByteOffset.QuadPart = 0;
        v16 = FltReadFile(Instance, v7, &ByteOffset, 8u, &Buffer, 0, &BytesRead, 0, 0);
        HsmDbgBreakOnStatus(v16);
        if ( v16 >= 0 )
        {
          if ( !(_BYTE)Buffer || WORD1(Buffer) < 8u || (unsigned int)WORD1(Buffer) > DWORD2(v122) && !HIDWORD(v122) )
          {
            HsmDbgBreakOnCorruption();
            v16 = -1073688809;
            HsmDbgBreakOnStatus(-1073688809);
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
          if ( *((__int64 *)&v122 + 1) > 786432 )
          {
LABEL_180:
            HsmDbgBreakOnCorruption();
            v16 = -1073688809;
            HsmDbgBreakOnStatus(-1073688809);
            goto LABEL_106;
          }
          v21[8] = DWORD2(v122);
          *(_BYTE *)(v10 + 232) = 1;
          *(_DWORD *)(v10 + 236) = v21[8];
          PoolAlignedWithTag = FltAllocatePoolAlignedWithTag(Instance, PagedPool, (unsigned int)v21[8], 0x72507348u);
          v101 = PoolAlignedWithTag;
          v9 = PoolAlignedWithTag;
          if ( !PoolAlignedWithTag )
          {
LABEL_170:
            v16 = -1073741670;
            HsmDbgBreakOnStatus(-1073741670);
            goto LABEL_106;
          }
          v36 = (unsigned int *)(PoolAlignedWithTag + 1);
          *PoolAlignedWithTag = Buffer;
          ByteOffset.QuadPart = 8;
          v16 = FltReadFile(Instance, v7, &ByteOffset, v21[8] - 8, PoolAlignedWithTag + 1, 0, &BytesRead, 0, 0);
          HsmDbgBreakOnStatus(v16);
          if ( v16 >= 0 )
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
                        v44 = v91;
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
                              v16 = -1073741670;
                              HsmDbgBreakOnStatus(-1073741670);
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
                                v9 = v101;
                                v7 = (struct _FILE_OBJECT *)v108;
                                v5 = Instance;
                                goto LABEL_87;
                              }
                              v53 = *(unsigned int *)&v101[8 * v52 + 20];
                              v54 = (_DWORD)v52 == v115[15] - 1
                                  ? v46
                                  : *(_DWORD *)&v101[8 * (unsigned int)(v52 + 1) + 20];
                              v55 = (unsigned int)(v54 - v53);
                              if ( (unsigned int)(v55 - 8) > 0x80000 )
                                break;
                              v56 = *(_DWORD *)&v101[v53];
                              v57 = &v101[v53];
                              v58 = v56 & 0xFFFFFF;
                              if ( (v56 & 0xFFFFFF) == 0 )
                                break;
                              if ( (v56 & 0xFFFFFF) > (unsigned __int64)(v55 - 8) )
                                break;
                              v59 = HIBYTE(v56);
                              if ( (_BYTE)v59 )
                              {
                                if ( v58 <= 4
                                  || !HsmiFindSupportedCompressionType(v59, v57[7], *((_DWORD *)v57 + 1) & 0xFFFFFF) )
                                {
                                  break;
                                }
                              }
                              v60 = ExAllocatePool2(256, 40, 1917875016);
                              v61 = (int *)v60;
                              if ( !v60 )
                              {
                                v16 = -1073741670;
                                HsmDbgBreakOnStatus(-1073741670);
LABEL_125:
                                v10 = a4;
                                goto LABEL_126;
                              }
                              v34 = *(_QWORD *)(v60 + 32) == 0;
                              v21 = v115;
                              v62 = *(_DWORD *)&v101[8 * v52 + 16];
                              *(_DWORD *)(v60 + 16) = v62;
                              *(_DWORD *)(v60 + 20) = *(_DWORD *)&v101[8 * v52 + 20];
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
                            v16 = -1073688809;
                            HsmDbgBreakOnStatus(-1073688809);
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
                            v9 = v101;
                            goto LABEL_105;
                          }
                          v83 = 0;
                          if ( (_DWORD)i )
                            break;
                          v91 = v44;
                          if ( *((_DWORD *)v49 + 5) < v41 )
                            goto LABEL_202;
                          v91 = v44;
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
                        v16 = -1073688809;
                        HsmDbgBreakOnStatus(-1073688809);
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
                v16 = -1073688809;
                HsmDbgBreakOnStatus(-1073688809);
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
              v16 = -1073688826;
              HsmDbgBreakOnStatus(-1073688826);
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
              v16 = -1073688809;
              HsmDbgBreakOnStatus(-1073688809);
              v81 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_105;
              }
              v82 = 17;
            }
            WPP_SF_qqiDd(
              v81->AttachedDevice,
              v82,
              WPP_7aae8ba2065034a53a58944ee54ad7f8_Traceguids,
              a1,
              v10,
              *(_QWORD *)(v10 + 32),
              (unsigned __int8)*v9,
              v16);
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
        *(_QWORD *)&v122 = 32;
        v16 = FltSetInformationFile(Instance, v7, &v122, 8u, FileEndOfFileInformation);
        HsmDbgBreakOnStatus(v16);
        if ( v16 < 0 )
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
          v21[8] = v122;
          *(_BYTE *)(v10 + 232) = 1;
          *(_DWORD *)(v10 + 236) = v21[8];
          v74 = FltAllocatePoolAlignedWithTag(Instance, PagedPool, 0x20u, 0x72507348u);
          v101 = v74;
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
          v16 = FltWriteFile(Instance, v7, &ByteOffset, v75[1], v75, 0, &BytesRead, 0, 0);
          if ( v16 >= 0 )
          {
            v9 = 0;
            *((_QWORD *)v21 + 5) = v75;
            v101 = 0;
            *((_QWORD *)v21 + 6) = v75 + 8;
            *((_QWORD *)v21 + 7) = 0;
LABEL_87:
            v65 = v107;
            *v21 &= ~2u;
            *((_QWORD *)v21 + 2) = v65;
            v107 = 0;
            v109 = 0;
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
    if ( v107 )
    {
      FltClose(v107);
      v107 = 0;
      v109 = 0;
    }
    v7 = (struct _FILE_OBJECT *)v108;
    if ( v108 )
    {
      ObfDereferenceObject(v108);
LABEL_88:
      v7 = 0;
      v110 = 0;
      v108 = 0;
    }
    if ( v9 )
    {
      FltFreePoolAlignedWithTag(v5, v9, 0x72507348u);
      v9 = 0;
      v101 = 0;
    }
    if ( v16 != -1073688809 && v16 != -1073688826 )
      goto LABEL_93;
    v15 = a1;
    if ( v96 )
    {
      v88 = v105;
    }
    else
    {
      v87 = *(_QWORD *)(v10 + 32);
      v105 = v16;
      v88 = v16;
      HsmpReportCorruption(a1, v87, (unsigned int)v16);
      v96 = 1;
    }
    v12 = v92;
    if ( v92 )
    {
      if ( v98 )
        break;
    }
    v8 = v95;
    if ( v95 || v97 )
      break;
    if ( v92 )
    {
      v11 = v93;
      v14 = a5;
      v13 = a3;
      v6 = v99;
      v98 = 1;
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
      v93 = 0;
      v92 = 0;
      v99 = 1;
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
    v12 = v92;
  }
  if ( v93 )
  {
    if ( v16 < 0 )
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
0x14005d0b0  push    rbp
0x14005d0b2  push    rbx
0x14005d0b3  push    rsi
0x14005d0b4  push    rdi
0x14005d0b5  push    r12
0x14005d0b7  push    r13
0x14005d0b9  push    r14
0x14005d0bb  push    r15
0x14005d0bd  lea     rbp, [rsp-0A8h]
0x14005d0c5  sub     rsp, 1A8h
0x14005d0cc  mov     rax, cs:__security_cookie
0x14005d0d3  xor     rax, rsp
0x14005d0d6  mov     [rbp+0E0h+var_50], rax
0x14005d0dd  mov     rsi, [rcx+20h]
0x14005d0e1  xor     eax, eax
0x14005d0e3  xor     r11b, r11b
0x14005d0e6  mov     [rbp+0E0h+var_138], r9
0x14005d0ea  xor     r12d, r12d
0x14005d0ed  mov     [rbp+0E0h+var_160], r11b
0x14005d0f1  movzx   r11d, byte ptr [rcx+18h]
0x14005d0f6  xor     r15d, r15d
0x14005d0f9  mov     r13, r9
0x14005d0fc  mov     [rbp+0E0h+var_B0], rdx
0x14005d100  xor     dl, dl
0x14005d102  mov     qword ptr [rbp+0E0h+var_130], r8
0x14005d106  xor     r9b, r9b
0x14005d109  mov     [rbp+0E0h+var_148], rcx
0x14005d10d  mov     [rbp+0E0h+var_124], 2
0x14005d114  xorps   xmm0, xmm0
0x14005d117  mov     [rbp+0E0h+Instance], rsi
0x14005d11b  mov     r10, r8
0x14005d11e  movzx   r8d, [rbp+0E0h+arg_20]
0x14005d126  mov     rbx, rcx
0x14005d129  mov     [rbp+0E0h+var_118], rax
0x14005d12d  mov     [rbp+0E0h+var_108], rax
0x14005d131  mov     [rbp+0E0h+var_110], r12
0x14005d135  mov     [rbp+0E0h+var_100], r12
0x14005d139  mov     qword ptr [rbp+0E0h+ByteOffset], rax
0x14005d13d  mov     [rbp+0E0h+BytesRead], eax
0x14005d140  mov     [rbp+0E0h+var_58], rax
0x14005d147  mov     [rbp+0E0h+Buffer], rax
0x14005d14b  mov     [rbp+0E0h+var_140], r15
0x14005d14f  mov     [rbp+0E0h+var_15E], dl
0x14005d152  mov     [rbp+0E0h+var_15F], r9b
0x14005d156  mov     [rbp+0E0h+var_14C], al
0x14005d159  mov     [rbp+0E0h+var_14D], al
0x14005d15c  mov     [rbp+0E0h+var_14E], al
0x14005d15f  mov     [rbp+0E0h+var_14F], al
0x14005d162  mov     [rbp+0E0h+var_150], r11b
0x14005d166  movups  [rbp+0E0h+var_68], xmm0
0x14005d16a  test    r11b, r11b
0x14005d16d  jnz     loc_14005DA90
0x14005d173  xor     edi, edi
0x14005d175  test    dl, dl
0x14005d177  jnz     loc_14005D230
0x14005d17d  test    r8b, r8b
0x14005d180  jnz     loc_14005DA2B
0x14005d186  test    al, al
0x14005d188  jnz     loc_14005DA2B
0x14005d18e  xor     al, al
0x14005d190  lea     rbx, [r13+78h]
0x14005d194  cmp     qword ptr [r13+0E0h], 0
0x14005d19c  jz      short loc_14005D1B3
0x14005d19e  lea     rbx, [r13+78h]
0x14005d1a2  test    dil, dil
0x14005d1a5  jnz     short loc_14005D1B3
0x14005d1a7  lea     rbx, [r13+78h]
0x14005d1ab  test    al, al
0x14005d1ad  jz      loc_14005D377
0x14005d1b3  call    cs:__imp_KeEnterCriticalRegion
0x14005d1ba  nop     dword ptr [rax+rax+00h]
0x14005d1bf  mov     dl, 1; Wait
0x14005d1c1  mov     rcx, rbx; Resource
0x14005d1c4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005d1cb  nop     dword ptr [rax+rax+00h]
0x14005d1d0  mov     rax, [r13+0E0h]
0x14005d1d7  mov     sil, 1
0x14005d1da  test    rax, rax
0x14005d1dd  jz      short loc_14005D1F4
0x14005d1df  test    dil, dil
0x14005d1e2  jnz     short loc_14005D1F4
0x14005d1e4  mov     eax, [rax]
0x14005d1e6  and     eax, 3
0x14005d1e9  dec     eax
0x14005d1eb  cmp     eax, 1
0x14005d1ee  jbe     loc_14005DBBF
0x14005d1f4  cmp     qword ptr [r13+0E0h], 0
0x14005d1fc  jz      loc_14005DAD1
0x14005d202  xor     edi, edi
0x14005d204  mov     ecx, edi
0x14005d206  call    HsmDbgBreakOnStatus
0x14005d20b  mov     rbx, [rbp+0E0h+var_148]
0x14005d20f  movzx   r9d, sil
0x14005d213  movzx   r8d, [rbp+0E0h+arg_20]
0x14005d21b  mov     r10, qword ptr [rbp+0E0h+var_130]
0x14005d21f  movzx   r11d, [rbp+0E0h+var_150]
0x14005d224  mov     [rbp+0E0h+var_15F], sil
0x14005d228  mov     rsi, [rbp+0E0h+Instance]
0x14005d22c  mov     [rbp+0E0h+var_15E], 1
0x14005d230  mov     r14, [r13+0E0h]
0x14005d237  mov     [rbp+0E0h+var_D0], r14
0x14005d23b  mov     ecx, [r14]
0x14005d23e  mov     eax, ecx
0x14005d240  and     eax, 3
0x14005d243  cmp     al, 3
0x14005d245  jz      loc_14005DD94
0x14005d24b  test    cl, 1
0x14005d24e  jnz     loc_14005DA62
0x14005d254  test    cl, 2
0x14005d257  jnz     loc_14005DBDD
0x14005d25d  mov     rcx, [rbx+20h]; Instance
0x14005d261  lea     r8, [rbp+0E0h+FileInformation]; FileInformation
0x14005d265  xor     eax, eax
0x14005d267  mov     r9d, 8; Length
0x14005d26d  mov     [rsp+1E0h+LengthReturned], rax; LengthReturned
0x14005d272  mov     rdx, r10; FileObject
0x14005d275  mov     [rsp+1E0h+FileInformationClass], 6; FileInformationClass
0x14005d27d  mov     [rbp+0E0h+FileInformation], rax
0x14005d281  call    cs:__imp_FltQueryInformationFile
0x14005d288  nop     dword ptr [rax+rax+00h]
0x14005d28d  mov     ecx, eax
0x14005d28f  mov     edi, eax
0x14005d291  call    HsmDbgBreakOnStatus
0x14005d296  test    edi, edi
0x14005d298  js      loc_14005D594
0x14005d29e  mov     r9, [rbp+0E0h+var_148]
0x14005d2a2  xor     ecx, ecx
0x14005d2a4  mov     r15, [rbp+0E0h+FileInformation]
0x14005d2a8  lea     rdi, [r9+40h]
0x14005d2ac  xorps   xmm0, xmm0
0x14005d2af  mov     [rbp+0E0h+var_C8], rcx
0x14005d2b3  xor     eax, eax
0x14005d2b5  mov     [rbp+0E0h+Object], rcx
0x14005d2b9  movzx   eax, word ptr [rdi]
0x14005d2bc  mov     ebx, ecx
0x14005d2be  mov     r14, [r9+20h]
0x14005d2c2  add     ax, 8
0x14005d2c6  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x14005d2ca  movzx   edx, ax
0x14005d2cd  mov     esi, ecx
0x14005d2cf  mov     [rbp+0E0h+FileHandle], rcx
0x14005d2d3  mov     r8d, 73557348h
0x14005d2d9  mov     [rbp+0E0h+FileObject], rcx
0x14005d2dd  mov     [rbp+0E0h+DestinationString.Length], cx
0x14005d2e1  mov     ecx, 100h
0x14005d2e6  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.ObjectName], xmm0
0x14005d2ea  mov     [rbp+0E0h+DestinationString.MaximumLength], dx
0x14005d2ee  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.Length], xmm0
0x14005d2f2  movups  xmmword ptr [rbp+0E0h+ObjectAttributes+1Ch], xmm0
0x14005d2f6  movups  xmmword ptr [rbp+0E0h+var_78], xmm0
0x14005d2fa  call    cs:__imp_ExAllocatePool2
0x14005d301  nop     dword ptr [rax+rax+00h]
0x14005d306  mov     [rbp+0E0h+DestinationString.Buffer], rax
0x14005d30a  test    rax, rax
0x14005d30d  jnz     loc_14005D3D9
0x14005d313  mov     ecx, 0C000009Ah
0x14005d318  call    HsmDbgBreakOnStatus
0x14005d31d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d324  lea     rax, WPP_GLOBAL_Control
0x14005d32b  cmp     rcx, rax
0x14005d32e  jz      loc_14005DEB9
0x14005d334  mov     eax, [rcx+2Ch]
0x14005d337  test    al, 8
0x14005d339  jz      loc_14005DEB9
0x14005d33f  cmp     byte ptr [rcx+29h], 2
0x14005d343  mov     r14, [rbp+0E0h+var_148]
0x14005d347  jb      loc_14005DEBD
0x14005d34d  mov     rcx, [rcx+18h]
0x14005d351  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005d358  mov     edx, 1Bh
0x14005d35d  mov     dword ptr [rsp+1E0h+LengthReturned], 0C000009Ah
0x14005d365  mov     r9, r14
0x14005d368  mov     qword ptr [rsp+1E0h+FileInformationClass], r15
0x14005d36d  call    WPP_SF_qqd
0x14005d372  jmp     loc_14005DEBD
0x14005d377  call    cs:__imp_KeEnterCriticalRegion
0x14005d37e  nop     dword ptr [rax+rax+00h]
0x14005d383  lea     rbx, [r13+78h]
0x14005d387  mov     dl, 1; Wait
0x14005d389  mov     rcx, rbx; Resource
0x14005d38c  call    cs:__imp_ExAcquireResourceSharedLite
0x14005d393  nop     dword ptr [rax+rax+00h]
0x14005d398  mov     rax, [r13+0E0h]
0x14005d39f  test    rax, rax
0x14005d3a2  jz      short loc_14005D3B7
0x14005d3a4  mov     ecx, [rax]
0x14005d3a6  xor     sil, sil
0x14005d3a9  and     ecx, 3
0x14005d3ac  dec     ecx
0x14005d3ae  cmp     ecx, 1
0x14005d3b1  jbe     loc_14005D1F4
0x14005d3b7  mov     rcx, rbx; Resource
0x14005d3ba  call    cs:__imp_ExReleaseResourceLite
0x14005d3c1  nop     dword ptr [rax+rax+00h]
0x14005d3c6  call    cs:__imp_KeLeaveCriticalRegion
0x14005d3cd  nop     dword ptr [rax+rax+00h]
0x14005d3d2  mov     al, 1
0x14005d3d4  jmp     loc_14005D194
0x14005d3d9  xor     ecx, ecx
0x14005d3db  call    HsmDbgBreakOnStatus
0x14005d3e0  mov     rdx, rdi; SourceString
0x14005d3e3  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x14005d3e7  call    cs:__imp_RtlCopyUnicodeString
0x14005d3ee  nop     dword ptr [rax+rax+00h]
0x14005d3f3  movzx   ecx, [rbp+0E0h+DestinationString.Length]
0x14005d3f7  lea     r8, [rbp+0E0h+DestinationString]
0x14005d3fb  mov     rax, [rbp+0E0h+DestinationString.Buffer]
0x14005d3ff  mov     rdx, r14
0x14005d402  mov     r14, [rbp+0E0h+var_148]
0x14005d406  mov     r9d, 100080h
0x14005d40c  mov     [rcx+rax], r15
0x14005d410  lea     rax, [rbp+0E0h+Object]
0x14005d414  add     [rbp+0E0h+DestinationString.Length], 8
0x14005d419  mov     rcx, r14
0x14005d41c  mov     qword ptr [rsp+1E0h+FileAttributes], rax
0x14005d421  lea     rax, [rbp+0E0h+var_C8]
0x14005d425  mov     [rsp+1E0h+AllocationSize], rax
0x14005d42a  mov     byte ptr [rsp+1E0h+IoStatusBlock], bl
0x14005d42e  mov     dword ptr [rsp+1E0h+LengthReturned], 202100h
0x14005d436  call    HsmiOpenFile
0x14005d43b  mov     ecx, eax
0x14005d43d  mov     edi, eax
0x14005d43f  call    HsmDbgBreakOnStatus
0x14005d444  test    edi, edi
0x14005d446  js      loc_14005DE67
0x14005d44c  mov     rbx, [rbp+0E0h+var_C8]
0x14005d450  mov     rsi, [rbp+0E0h+Object]
0x14005d454  mov     rcx, [rbp+0E0h+DestinationString.Buffer]; P
0x14005d458  test    rcx, rcx
0x14005d45b  jz      short loc_14005D46E
0x14005d45d  mov     edx, 73557348h; Tag
0x14005d462  call    cs:__imp_ExFreePoolWithTag
0x14005d469  nop     dword ptr [rax+rax+00h]
0x14005d46e  mov     ecx, edi
0x14005d470  call    HsmDbgBreakOnStatus
0x14005d475  test    edi, edi
0x14005d477  js      loc_14005D53F
0x14005d47d  mov     rdx, [r14+20h]; Instance
0x14005d481  lea     rax, PropertyStreamName; "bd"
0x14005d488  mov     rcx, cs:Filter; Filter
0x14005d48f  lea     r9, [rbp+0E0h+FileObject]; FileObject
0x14005d493  mov     [rsp+1E0h+Flags], 840h; Flags
0x14005d49b  lea     r8, [rbp+0E0h+FileHandle]; FileHandle
0x14005d49f  xor     r15d, r15d
0x14005d4a2  mov     [rbp+0E0h+ObjectAttributes.ObjectName], rax
0x14005d4a6  mov     [rsp+1E0h+EaLength], r15d; EaLength
0x14005d4ab  lea     rax, [rbp+0E0h+var_78]
0x14005d4af  mov     [rsp+1E0h+EaBuffer], r15; EaBuffer
0x14005d4b4  xorps   xmm0, xmm0
0x14005d4b7  mov     [rsp+1E0h+CreateOptions], 200020h; CreateOptions
0x14005d4bf  mov     [rsp+1E0h+CreateDisposition], 1; CreateDisposition
0x14005d4c7  mov     [rsp+1E0h+ShareAccess], 7; ShareAccess
0x14005d4cf  mov     [rsp+1E0h+FileAttributes], r15d; FileAttributes
0x14005d4d4  mov     [rsp+1E0h+AllocationSize], r15; AllocationSize
0x14005d4d9  mov     [rsp+1E0h+IoStatusBlock], rax; FileHandle
0x14005d4de  lea     rax, [rbp+0E0h+ObjectAttributes]
0x14005d4e2  mov     [rsp+1E0h+LengthReturned], rax; ObjectAttributes
0x14005d4e7  mov     [rsp+1E0h+FileInformationClass], 110183h; DesiredAccess
0x14005d4ef  mov     [rbp+0E0h+ObjectAttributes.Length], 30h ; '0'
0x14005d4f6  mov     [rbp+0E0h+ObjectAttributes.RootDirectory], rbx
0x14005d4fa  mov     [rbp+0E0h+ObjectAttributes.Attributes], 200h
0x14005d501  movdqu  xmmword ptr [rbp+0E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005d506  call    cs:__imp_FltCreateFileEx
0x14005d50d  nop     dword ptr [rax+rax+00h]
0x14005d512  mov     ecx, eax
0x14005d514  mov     edi, eax
0x14005d516  call    HsmDbgBreakOnStatus
0x14005d51b  test    edi, edi
0x14005d51d  js      short loc_14005D53F
0x14005d51f  mov     r12, [rbp+0E0h+FileObject]
0x14005d523  mov     rax, [rbp+0E0h+FileHandle]
0x14005d527  mov     [rbp+0E0h+var_110], r12
0x14005d52b  mov     [rbp+0E0h+var_100], r12
0x14005d52f  mov     [rbp+0E0h+var_118], rax
0x14005d533  mov     [rbp+0E0h+var_108], rax
0x14005d537  mov     [rbp+0E0h+FileObject], r15
0x14005d53b  mov     [rbp+0E0h+FileHandle], r15
0x14005d53f  test    rsi, rsi
0x14005d542  jz      short loc_14005D553
0x14005d544  mov     rcx, rsi; Object
0x14005d547  call    cs:__imp_ObfDereferenceObject
0x14005d54e  nop     dword ptr [rax+rax+00h]
0x14005d553  test    rbx, rbx
0x14005d556  jz      short loc_14005D567
0x14005d558  mov     rcx, rbx; FileHandle
0x14005d55b  call    cs:__imp_FltClose
0x14005d562  nop     dword ptr [rax+rax+00h]
0x14005d567  mov     rcx, [rbp+0E0h+FileObject]; Object
0x14005d56b  test    rcx, rcx
0x14005d56e  jnz     loc_14005DEC7
0x14005d574  mov     rcx, [rbp+0E0h+FileHandle]; FileHandle
0x14005d578  test    rcx, rcx
0x14005d57b  jnz     loc_14005DED8
0x14005d581  mov     ecx, edi
0x14005d583  call    HsmDbgBreakOnStatus
0x14005d588  mov     r14, [rbp+0E0h+var_D0]
0x14005d58c  mov     r15, [rbp+0E0h+var_140]
0x14005d590  mov     rbx, [rbp+0E0h+var_148]
0x14005d594  mov     ecx, edi
0x14005d596  call    HsmDbgBreakOnStatus
  ... truncated ...
```
