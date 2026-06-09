# HsmpOpCreatePlaceholders

- ea: `0x1400608bc`
- end: `0x140061c5a`
- name: `HsmpOpCreatePlaceholders`
- size: `5022`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140043c9c`
- `0x14006049c`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000b62c`
- `0x14000c12c`
- `0x14000dbd0`
- `0x140015660`
- `0x14001dc7c`
- `0x14001e1c0`
- `0x14001e600`
- `0x140035384`
- `0x140037030`
- `0x1400503a0`
- `0x1400608bc`
- `0x14006ad44`
- `0x14006b848`
- `0x1400766ac`
- `0x1400779d8`
- `0x14007e468`
- `0x140081d30`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140060a6b`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140060a6b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140060c4e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140060c4e`
- `ntoskrnl!IoFileObjectType` at `0x140060c3f`
- `ntoskrnl!ObfDereferenceObject` at `0x14006190c`
- `ntoskrnl!ObfDereferenceObject` at `0x140061c28`
- `ntoskrnl!ObfDereferenceObject` at `0x14006190c`
- `ntoskrnl!ObfDereferenceObject` at `0x140061c28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061b5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061c0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061b5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061c0f`
- `ntoskrnl!ExAllocatePool2` at `0x1400609d8`
- `ntoskrnl!ExAllocatePool2` at `0x140060a9f`
- `ntoskrnl!ExAllocatePool2` at `0x1400609d8`
- `ntoskrnl!ExAllocatePool2` at `0x140060a9f`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140060b0d`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140060b0d`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140061b7a`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140061b7a`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140060c1e`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140060c1e`
- `FLTMGR!FltSetInformationFile` at `0x140061676`
- `FLTMGR!FltSetInformationFile` at `0x140061779`
- `FLTMGR!FltSetInformationFile` at `0x140061676`
- `FLTMGR!FltSetInformationFile` at `0x140061779`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140060bb4`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140060bb4`
- `FLTMGR!FltCreateFileEx` at `0x140061466`
- `FLTMGR!FltCreateFileEx` at `0x140061466`
- `FLTMGR!FltClose` at `0x14006192d`
- `FLTMGR!FltClose` at `0x14006192d`
- `FLTMGR!FltQueryInformationFile` at `0x140061841`
- `FLTMGR!FltQueryInformationFile` at `0x140061841`
- `FLTMGR!FltCreateFileEx2` at `0x140061392`
- `FLTMGR!FltCreateFileEx2` at `0x140061392`

## pseudocode

```c
__int64 __fastcall HsmpOpCreatePlaceholders(__int64 a1, void *a2, int a3, void *a4, unsigned int Size, _DWORD *a6)
{
  int v6; // edi
  void *v7; // r12
  void *v8; // r13
  char *Pool2; // rax
  void *v11; // rsi
  NTSTATUS v12; // edi
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  PDEVICE_OBJECT v17; // rcx
  int LastEffectiveUsn; // esi
  unsigned int v19; // edx
  unsigned __int64 v20; // xmm2_8
  unsigned int v21; // r9d
  unsigned int v22; // r13d
  int v23; // r11d
  unsigned __int16 v24; // cx
  char v25; // r13
  __int16 v26; // dx
  __int64 v27; // r8
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  ULONG FileAttributes; // r9d
  int v31; // ecx
  int v32; // eax
  char v33; // cl
  PDEVICE_OBJECT v34; // rcx
  __int64 v35; // rdx
  _WORD *v36; // rcx
  __int64 v37; // rcx
  char v38; // r13
  __m128i *v39; // r13
  __m128i *v40; // r13
  PFILE_OBJECT v41; // rdx
  __int32 v42; // eax
  PDEVICE_OBJECT v43; // rcx
  __int64 v44; // rdx
  int v45; // r12d
  __int16 LookasideList; // [rsp+28h] [rbp-240h]
  unsigned __int8 v49; // [rsp+88h] [rbp-1E0h]
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp-1D8h] BYREF
  PVOID EcpContext; // [rsp+98h] [rbp-1D0h] BYREF
  int v52; // [rsp+A0h] [rbp-1C8h]
  char *v53; // [rsp+A8h] [rbp-1C0h]
  unsigned __int32 v54; // [rsp+B0h] [rbp-1B8h]
  __m128i *v55; // [rsp+B8h] [rbp-1B0h]
  int v56; // [rsp+C0h] [rbp-1A8h]
  unsigned __int32 v57; // [rsp+C4h] [rbp-1A4h]
  int v58; // [rsp+C8h] [rbp-1A0h]
  PFLT_INSTANCE Instance; // [rsp+D0h] [rbp-198h]
  void *v60; // [rsp+D8h] [rbp-190h]
  unsigned int v61; // [rsp+E0h] [rbp-188h]
  PVOID P; // [rsp+E8h] [rbp-180h]
  void *FileHandle; // [rsp+F0h] [rbp-178h] BYREF
  PECP_LIST EcpList; // [rsp+F8h] [rbp-170h] BYREF
  void *v65; // [rsp+100h] [rbp-168h]
  PVOID Object; // [rsp+108h] [rbp-160h] BYREF
  union _LARGE_INTEGER AllocationSize; // [rsp+110h] [rbp-158h] BYREF
  void *v68; // [rsp+118h] [rbp-150h]
  __int64 v69; // [rsp+120h] [rbp-148h]
  __int128 v70; // [rsp+128h] [rbp-140h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+138h] [rbp-130h] BYREF
  __int64 v72; // [rsp+158h] [rbp-110h]
  _DWORD *v73; // [rsp+160h] [rbp-108h]
  size_t v74; // [rsp+168h] [rbp-100h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+170h] [rbp-F8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+1A0h] [rbp-C8h] BYREF
  __m128i v77[5]; // [rsp+1B0h] [rbp-B8h] BYREF
  __m128i v78; // [rsp+200h] [rbp-68h] BYREF
  __m128i v79; // [rsp+210h] [rbp-58h]
  unsigned __int64 v80; // [rsp+220h] [rbp-48h]

  v7 = a4;
  v60 = a4;
  v58 = a3;
  v8 = a2;
  v69 = a1;
  v68 = a2;
  v65 = a4;
  v61 = Size;
  v73 = a6;
  Instance = *(PFLT_INSTANCE *)(a1 + 32);
  AllocationSize.QuadPart = 0;
  FileHandle = 0;
  FileObject = 0;
  LOBYTE(v6) = 1;
  v56 = v6;
  Object = 0;
  if ( (unsigned int)Feature_ReFS_OneDrive_Support__private_IsEnabledDeviceUsageNoInline() )
  {
    LOBYTE(v6) = *(_DWORD *)(a1 + 80) != 28;
    v56 = (unsigned __int8)v6;
  }
  memset(&DriverContext, 0, sizeof(DriverContext));
  LOWORD(v72) = 0;
  P = 0;
  EcpList = 0;
  EcpContext = 0;
  v74 = Size;
  Pool2 = (char *)ExAllocatePool2(258, Size, 1884517192);
  v11 = Pool2;
  v53 = Pool2;
  if ( !Pool2 )
  {
    v12 = -1073741670;
    HsmDbgBreakOnStatus(-1073741670);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_199;
    }
    v14 = 99;
    goto LABEL_8;
  }
  if ( v61 && ((unsigned __int8)v7 & 3) != 0 )
    ExRaiseDatatypeMisalignment();
  RtlCopyFromUser(Pool2, v7, Size);
  if ( (_BYTE)v6 )
  {
    P = (PVOID)ExAllocatePool2(256, 0x4000, 1884451656);
    if ( !P )
    {
      v12 = -1073741670;
      HsmDbgBreakOnStatus(-1073741670);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_199;
      }
      v14 = 104;
LABEL_8:
      WPP_SF_qqd(v13->AttachedDevice, v14, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids, a1, v8, -1073741670);
      goto LABEL_9;
    }
    v12 = FltAllocateExtraCreateParameterList(Filter, 0, &EcpList);
    HsmDbgBreakOnStatus(v12);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_200;
      }
      v15 = 105;
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
LABEL_24:
      WPP_SF_qqd(AttachedDevice, v15, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids, a1, v8, v12);
      v7 = v60;
      goto LABEL_200;
    }
    v12 = FltAllocateExtraCreateParameterFromLookasideList(
            Filter,
            &GUID_ECP_ATOMIC_CREATE,
            0x58u,
            0,
            0,
            qword_1400291C0,
            &EcpContext);
    HsmDbgBreakOnStatus(v12);
    if ( v12 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_200;
      }
      v15 = 106;
LABEL_30:
      AttachedDevice = v17->AttachedDevice;
      goto LABEL_24;
    }
    FltInsertExtraCreateParameter(Filter, EcpList, EcpContext);
  }
  v12 = ObReferenceObjectByHandle(v8, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
  HsmDbgBreakOnStatus(v12);
  if ( v12 < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_200;
    }
    v15 = 107;
    goto LABEL_30;
  }
  v52 = 0;
  v54 = 0;
  v12 = 0;
  LastEffectiveUsn = 0;
  while ( 1 )
  {
    memset(v77, 0, sizeof(v77));
    v70 = 0;
    memset(&ObjectAttributes, 0, 44);
    IoStatusBlock = 0;
    v78 = 0;
    v79 = 0;
    v80 = 0;
    v19 = v61 - v54;
    if ( v61 - v54 < 0x50 )
    {
      LastEffectiveUsn = -1073688821;
      HsmDbgBreakOnStatus(-1073688821);
      v12 = v52 == 0 ? 0xC000CF0B : 0;
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_192;
      }
      v44 = 108;
LABEL_182:
      WPP_SF_qqd(v43->AttachedDevice, v44, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids, a1, v8, -1073688821);
      goto LABEL_192;
    }
    v55 = (__m128i *)&v53[v54];
    v77[0] = *v55;
    v77[1] = v55[1];
    v77[2] = v55[2];
    v77[3] = v55[3];
    v77[4] = v55[4];
    v20 = _mm_srli_si128(v77[0], 8).m128i_u64[0];
    v21 = HIWORD(v20);
    v22 = v21 + WORD2(v20);
    v77[0].m128i_i16[4] = v20;
    if ( WORD1(v20) + (unsigned int)(unsigned __int16)v20 > v22 )
      v22 = WORD1(v20) + (unsigned __int16)v20;
    if ( (unsigned __int16)v20 > v19
      || WORD1(v20) > v19 - (unsigned __int16)v20
      || WORD2(v20) > v19
      || v21 > v19 - WORD2(v20)
      || HIWORD(v20) > 0x1000u
      || v77[0].m128i_i32[0] && (v77[0].m128i_i32[0] < v22 || v77[0].m128i_i32[0] > v19) )
    {
      break;
    }
    v23 = (int)v55;
    v24 = 0;
    v25 = 1;
    if ( WORD1(v20) >> 1 )
    {
      while ( 1 )
      {
        v26 = *(__int16 *)((char *)&v55->m128i_i16[v24] + v77[0].m128i_u16[4]);
        if ( v26 == 92 || v26 == 58 )
          break;
        if ( ++v24 >= (unsigned __int16)(WORD1(v20) >> 1) )
          goto LABEL_53;
      }
      LastEffectiveUsn = -1073688821;
      HsmDbgBreakOnStatus(-1073688821);
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_164;
      v8 = a2;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v29 = 110;
        goto LABEL_68;
      }
      goto LABEL_165;
    }
LABEL_53:
    if ( (v77[0].m128i_i8[0] & 3) != 0 )
    {
      LastEffectiveUsn = -1073688821;
      HsmDbgBreakOnStatus(-1073688821);
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_191;
      v8 = a2;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_192;
      v44 = 111;
      goto LABEL_182;
    }
    if ( ((v77[3].m128i_i8[0] & 0x10) != 0 || (v58 & 2) != 0 || !v77[3].m128i_i64[1])
      && ((v77[3].m128i_i8[0] & 0x10) == 0 || (v58 & 4) != 0 || (v77[0].m128i_i8[4] & 0x40) != 0) )
    {
      if ( !v77[0].m128i_i16[7] )
      {
        LastEffectiveUsn = -1073688821;
        HsmDbgBreakOnStatus(-1073688821);
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_164;
        v8 = a2;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v29 = 113;
          goto LABEL_68;
        }
        goto LABEL_165;
      }
      ++v52;
      v77[4].m128i_i32[0] = -1073688825;
      v77[4].m128i_i64[1] = 0;
      if ( (v77[3].m128i_i8[0] & 0x10) != 0 )
      {
        v49 = 1;
        LastEffectiveUsn = HsmpAccessCheck(a1, (struct _FILE_OBJECT *)Object, 4u);
        HsmDbgBreakOnStatus(LastEffectiveUsn);
        if ( LastEffectiveUsn < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqd(
              WPP_GLOBAL_Control->AttachedDevice,
              114,
              WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
              a1,
              FileObject,
              LastEffectiveUsn);
          }
          TlmWriteAccessDeniedForAddSubDirectory();
          goto LABEL_164;
        }
        v23 = (int)v55;
      }
      else
      {
        v25 = 0;
        v49 = 0;
      }
      FileAttributes = v77[3].m128i_i32[0] | 0x401000;
      v57 = v77[3].m128i_i32[0] | 0x401000;
      if ( v25 )
      {
        v27 = 16;
        if ( (v77[0].m128i_i8[4] & 0x40) != 0 )
        {
          v27 = 22;
          FileAttributes = v77[3].m128i_i32[0] & 0xFFBFEFFF;
          v57 = v77[3].m128i_i32[0] & 0xFFBFEFFF;
        }
      }
      else
      {
        v27 = ((unsigned __int32)v77[3].m128i_i32[0] >> 9) & 1;
      }
      v31 = v27 | 0x40;
      if ( (v77[0].m128i_i8[4] & 1) == 0 )
        v31 = v27;
      v32 = v31 | 0x100;
      if ( (v77[0].m128i_i16[2] & 0x400) == 0 )
        v32 = v31;
      LODWORD(v65) = v32;
      v33 = v56;
      if ( (_BYTE)v56 )
      {
        LastEffectiveUsn = HsmpRpBuildBuffer(
                             v77[3].m128i_i32[2],
                             v32,
                             v23 + (unsigned int)v77[0].m128i_u16[6],
                             v77[0].m128i_u16[7],
                             (__int64)P,
                             LookasideList);
        HsmDbgBreakOnStatus(LastEffectiveUsn);
        if ( LastEffectiveUsn < 0 )
        {
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v35 = 115;
            goto LABEL_97;
          }
LABEL_164:
          v8 = a2;
          goto LABEL_165;
        }
        *(_WORD *)EcpContext = 88;
        *((_WORD *)EcpContext + 1) = 7730;
        *((_WORD *)EcpContext + 2) = 0;
        v36 = P;
        *((_QWORD *)EcpContext + 1) = P;
        *((_WORD *)EcpContext + 3) = v36[2] + 8;
        *((_QWORD *)EcpContext + 4) = &v77[1];
        FileAttributes = v57;
        *((_DWORD *)EcpContext + 10) = v57;
        if ( !v25 )
        {
          v37 = v77[3].m128i_i64[1];
          if ( v77[3].m128i_i64[1] > 0 )
          {
            *((_WORD *)EcpContext + 1) |= 1u;
            v37 = v77[3].m128i_i64[1];
          }
          *((_QWORD *)EcpContext + 2) = v37;
          *((_QWORD *)EcpContext + 3) = v77[3].m128i_i64[1];
          *((_WORD *)EcpContext + 1) |= 0xCu;
        }
        *((_DWORD *)EcpContext + 11) = 8;
        *(_DWORD *)(&DriverContext.Size + 1) = 0;
        *(&DriverContext.Size + 3) = 0;
        *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
        DriverContext.Size = 40;
        v72 = 1;
        DriverContext.ExtraCreateParameter = EcpList;
        v33 = v56;
      }
      v38 = v33;
      *((_QWORD *)&v70 + 1) = (char *)v55 + v77[0].m128i_u16[4];
      LOWORD(v70) = v77[0].m128i_i16[5];
      WORD1(v70) = v77[0].m128i_i16[5];
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = a2;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v70;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( v33 )
      {
        LastEffectiveUsn = FltCreateFileEx2(
                             Filter,
                             Instance,
                             &FileHandle,
                             &FileObject,
                             0x100180u,
                             &ObjectAttributes,
                             &IoStatusBlock,
                             &AllocationSize,
                             FileAttributes,
                             0,
                             2u,
                             v49 | 0x208020,
                             0,
                             0,
                             0x800u,
                             &DriverContext);
        HsmDbgBreakOnStatus(LastEffectiveUsn);
        if ( (LastEffectiveUsn == -1073741771 || LastEffectiveUsn == -1073741191) && (v77[0].m128i_i16[2] & 0x4000) != 0 )
          v38 = 0;
      }
      if ( !v38 )
      {
        LastEffectiveUsn = FltCreateFileEx(
                             Filter,
                             Instance,
                             &FileHandle,
                             &FileObject,
                             0x100180u,
                             &ObjectAttributes,
                             &IoStatusBlock,
                             &AllocationSize,
                             v77[3].m128i_i32[0] | 0x1000,
                             0,
                             ~(unsigned __int8)((unsigned __int32)v77[0].m128i_i32[1] >> 13) & 2,
                             v49 | 0x208020,
                             0,
                             0,
                             0x800u);
        HsmDbgBreakOnStatus(LastEffectiveUsn);
      }
      if ( LastEffectiveUsn < 0 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_164;
        }
        v35 = 116;
        goto LABEL_97;
      }
      if ( v38 )
      {
        v39 = v55;
        v55[1] = v77[1];
        v39[2] = v77[2];
        v39[3].m128i_i32[0] = *((_DWORD *)EcpContext + 10);
        v39[4].m128i_i64[1] = *((_QWORD *)EcpContext + 6);
LABEL_160:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qd(
            WPP_GLOBAL_Control->AttachedDevice,
            125,
            WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
            a1,
            LastEffectiveUsn);
        }
        goto LABEL_164;
      }
      LastEffectiveUsn = HsmpMarkHandleUsnSourceInfo(a1, FileObject, 8);
      HsmDbgBreakOnStatus(LastEffectiveUsn);
      if ( LastEffectiveUsn < 0 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_164;
        }
        v35 = 117;
        goto LABEL_97;
      }
      v40 = v55;
      LookasideList = v77[0].m128i_i16[7];
      LastEffectiveUsn = HsmpRpCreate(
                           a1,
                           FileObject,
                           v77[3].m128i_i64[1],
                           (unsigned int)v65,
                           &v55->m128i_i8[v77[0].m128i_u16[6]]);
      HsmDbgBreakOnStatus(LastEffectiveUsn);
      if ( LastEffectiveUsn < 0 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_164;
        }
        v35 = 118;
        goto LABEL_97;
      }
      if ( v49 || !v77[3].m128i_i64[1] )
        goto LABEL_144;
      LOBYTE(v27) = 1;
      LastEffectiveUsn = HsmpToggleFileSparseAttribute(a1, FileObject, v27);
      HsmDbgBreakOnStatus(LastEffectiveUsn);
      if ( LastEffectiveUsn < 0 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_164;
        }
        v35 = 119;
        goto LABEL_97;
      }
      LastEffectiveUsn = FltSetInformationFile(Instance, FileObject, &v77[3].m128i_u64[1], 8u, FileEndOfFileInformation);
      HsmDbgBreakOnStatus(LastEffectiveUsn);
      if ( LastEffectiveUsn < 0 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_164;
        }
        v35 = 120;
        goto LABEL_97;
      }
      LastEffectiveUsn = HsmpSetFileVDL(Instance, FileObject, v77[3].m128i_i64[1]);
      HsmDbgBreakOnStatus(LastEffectiveUsn);
      if ( LastEffectiveUsn >= 0 )
      {
LABEL_144:
        v78 = v77[1];
        v79 = v77[2];
        v80 = __PAIR64__(v77[3].m128i_u32[1], v57);
        LastEffectiveUsn = FltSetInformationFile(Instance, FileObject, &v78, 0x28u, FileBasicInformation);
        HsmDbgBreakOnStatus(LastEffectiveUsn);
        if ( LastEffectiveUsn >= 0 )
        {
          LastEffectiveUsn = HsmpQueryLastEffectiveUsn(Instance, FileObject);
          HsmDbgBreakOnStatus(LastEffectiveUsn);
          if ( LastEffectiveUsn >= 0 )
          {
            LastEffectiveUsn = FltQueryInformationFile(Instance, FileObject, &v78, 0x28u, FileBasicInformation, 0);
            HsmDbgBreakOnStatus(LastEffectiveUsn);
            if ( LastEffectiveUsn >= 0 )
            {
              v40[1] = v78;
              v40[2] = v79;
              v40[3].m128i_i64[0] = v80;
              goto LABEL_160;
            }
            v34 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_164;
            }
            v35 = 124;
          }
          else
          {
            v34 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_164;
            }
            v35 = 123;
          }
        }
        else
        {
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_164;
          }
          v35 = 122;
        }
      }
      else
      {
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_164;
        }
        v35 = 121;
      }
LABEL_97:
      WPP_SF_qqd(
        v34->AttachedDevice,
        v35,
        WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        a1,
        FileObject,
        LastEffectiveUsn);
      goto LABEL_164;
    }
    LastEffectiveUsn = -1073688821;
    HsmDbgBreakOnStatus(-1073688821);
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_164;
    v8 = a2;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v29 = 112;
LABEL_68:
      WPP_SF_qqd(v28->AttachedDevice, v29, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids, a1, v8, -1073688821);
    }
LABEL_165:
    v55[4].m128i_i32[0] = LastEffectiveUsn;
    v41 = FileObject;
    if ( FileObject )
    {
      if ( LastEffectiveUsn < 0 )
        HsmpSetFileDisposition(*(_QWORD *)(a1 + 32));
      ObfDereferenceObject(FileObject);
      FileObject = 0;
    }
    if ( FileHandle )
    {
      FltClose(FileHandle);
      FileHandle = 0;
    }
    if ( LastEffectiveUsn >= 0 || (v58 & 1) == 0 )
    {
      v42 = v77[0].m128i_i32[0] ? v77[0].m128i_i32[0] + v54 : 0;
      v54 = v42;
      if ( v42 )
        continue;
    }
    goto LABEL_192;
  }
  LastEffectiveUsn = -1073688821;
  HsmDbgBreakOnStatus(-1073688821);
  v12 = v52 == 0 ? 0xC000CF0B : 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v8 = a2;
    WPP_SF_qqd(
      WPP_GLOBAL_Control->AttachedDevice,
      109,
      WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
      a1,
      a2,
      -1073688821);
    goto LABEL_192;
  }
LABEL_191:
  v8 = a2;
LABEL_192:
  v45 = v52;
  if ( v52 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqdd(WPP_GLOBAL_Control->AttachedDevice, v41, v27, a1, v8, v52, v12);
    }
  }
  else
  {
    v12 = LastEffectiveUsn;
  }
  *v73 = v45;
LABEL_9:
  v7 = v60;
LABEL_199:
  v11 = v53;
LABEL_200:
  if ( P )
    ExFreePoolWithTag(P, 0x70527348u);
  if ( EcpList )
    FltFreeExtraCreateParameterList(Filter, EcpList);
  if ( v11 )
  {
    if ( v12 >= 0 )
      RtlCopyToUser(v7, v11, v74);
    ExFreePoolWithTag(v11, 0x70537348u);
  }
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400608bc  mov     r11, rsp
0x1400608bf  push    rbx
0x1400608c0  push    rsi
0x1400608c1  push    rdi
0x1400608c2  push    r12
0x1400608c4  push    r13
0x1400608c6  push    r14
0x1400608c8  push    r15
0x1400608ca  sub     rsp, 230h
0x1400608d1  mov     rax, cs:__security_cookie
0x1400608d8  xor     rax, rsp
0x1400608db  mov     [rsp+268h+var_40], rax
0x1400608e3  mov     r12, r9
0x1400608e6  mov     [rsp+268h+var_190], r9
0x1400608ee  mov     [rsp+268h+var_1A0], r8d
0x1400608f6  mov     r13, rdx
0x1400608f9  mov     [rsp+268h+var_1E8], rdx
0x140060901  mov     r15, rcx
0x140060904  mov     [rsp+268h+var_148], rcx
0x14006090c  mov     [rsp+268h+var_150], rdx
0x140060914  mov     [rsp+268h+var_168], r9
0x14006091c  mov     esi, dword ptr [rsp+268h+Size]
0x140060923  mov     [rsp+268h+var_188], esi
0x14006092a  mov     rax, [rsp+268h+arg_28]
0x140060932  mov     [rsp+268h+var_108], rax
0x14006093a  mov     rax, [rcx+20h]
0x14006093e  mov     [rsp+268h+Instance], rax
0x140060946  xor     ebx, ebx
0x140060948  mov     [r11-158h], rbx
0x14006094f  mov     [r11-178h], rbx
0x140060956  mov     [r11-1D8h], rbx
0x14006095d  mov     dil, 1
0x140060960  mov     [rsp+268h+var_1A8], edi
0x140060967  mov     [r11-160h], rbx
0x14006096e  call    Feature_ReFS_OneDrive_Support__private_IsEnabledDeviceUsageNoInline
0x140060973  test    eax, eax
0x140060975  jz      short loc_14006098A
0x140060977  movzx   edi, dil
0x14006097b  cmp     dword ptr [r15+50h], 1Ch
0x140060980  cmovz   edi, ebx
0x140060983  mov     [rsp+268h+var_1A8], edi
0x14006098a  xor     eax, eax
0x14006098c  xorps   xmm0, xmm0
0x14006098f  movups  xmmword ptr [rsp+268h+var_130.Size], xmm0
0x140060997  movups  xmmword ptr [rsp+268h+var_130.DeviceObjectHint], xmm0
0x14006099f  mov     word ptr [rsp+268h+var_110], ax
0x1400609a7  mov     [rsp+268h+P], rbx
0x1400609af  mov     [rsp+268h+EcpList], rbx
0x1400609b7  mov     [rsp+268h+var_1D0], rbx
0x1400609bf  mov     r14, rsi
0x1400609c2  mov     [rsp+268h+var_100], rsi
0x1400609ca  mov     r8d, 70537348h
0x1400609d0  mov     rdx, rsi
0x1400609d3  mov     ecx, 102h
0x1400609d8  call    cs:__imp_ExAllocatePool2
0x1400609df  nop     dword ptr [rax+rax+00h]
0x1400609e4  mov     rsi, rax
0x1400609e7  mov     [rsp+268h+var_1C0], rax
0x1400609ef  test    rax, rax
0x1400609f2  jnz     short loc_140060A5C
0x1400609f4  mov     esi, 0C000009Ah
0x1400609f9  mov     edi, esi
0x1400609fb  mov     ecx, esi
0x1400609fd  call    HsmDbgBreakOnStatus
0x140060a02  lea     r14, WPP_GLOBAL_Control
0x140060a09  mov     rcx, cs:WPP_GLOBAL_Control
0x140060a10  cmp     rcx, r14
0x140060a13  jz      loc_140061B3D
0x140060a19  mov     eax, [rcx+2Ch]
0x140060a1c  test    al, 1
0x140060a1e  jz      loc_140061B3D
0x140060a24  cmp     byte ptr [rcx+29h], 2
0x140060a28  jb      loc_140061B3D
0x140060a2e  mov     edx, 63h ; 'c'
0x140060a33  mov     dword ptr [rsp+268h+LookasideList], esi
0x140060a37  mov     [rsp+268h+CleanupCallback], r13
0x140060a3c  mov     r9, r15
0x140060a3f  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140060a46  mov     rcx, [rcx+18h]
0x140060a4a  call    WPP_SF_qqd
0x140060a4f  mov     r12, [rsp+268h+var_190]
0x140060a57  jmp     loc_140061B3D
0x140060a5c  cmp     [rsp+268h+var_188], ebx
0x140060a63  jz      short loc_140060A77
0x140060a65  test    r12b, 3
0x140060a69  jz      short loc_140060A77
0x140060a6b  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140060a72  nop     dword ptr [rax+rax+00h]
0x140060a77  mov     r8, r14; Size
0x140060a7a  mov     rdx, r12; Src
0x140060a7d  mov     rcx, rax; void *
0x140060a80  call    RtlCopyFromUser
0x140060a85  nop
0x140060a86  test    dil, dil
0x140060a89  jz      loc_140060C2A
0x140060a8f  mov     edx, 4000h
0x140060a94  mov     ecx, 100h
0x140060a99  mov     r8d, 70527348h
0x140060a9f  call    cs:__imp_ExAllocatePool2
0x140060aa6  nop     dword ptr [rax+rax+00h]
0x140060aab  mov     [rsp+268h+P], rax
0x140060ab3  test    rax, rax
0x140060ab6  jnz     short loc_140060AFC
0x140060ab8  mov     esi, 0C000009Ah
0x140060abd  mov     edi, esi
0x140060abf  mov     ecx, esi
0x140060ac1  call    HsmDbgBreakOnStatus
0x140060ac6  lea     r14, WPP_GLOBAL_Control
0x140060acd  mov     rcx, cs:WPP_GLOBAL_Control
0x140060ad4  cmp     rcx, r14
0x140060ad7  jz      loc_140061B3D
0x140060add  mov     eax, [rcx+2Ch]
0x140060ae0  test    al, 1
0x140060ae2  jz      loc_140061B3D
0x140060ae8  cmp     byte ptr [rcx+29h], 2
0x140060aec  jb      loc_140061B3D
0x140060af2  mov     edx, 68h ; 'h'
0x140060af7  jmp     loc_140060A33
0x140060afc  lea     r8, [rsp+268h+EcpList]; EcpList
0x140060b04  xor     edx, edx; Flags
0x140060b06  mov     rcx, cs:Filter; Filter
0x140060b0d  call    cs:__imp_FltAllocateExtraCreateParameterList
0x140060b14  nop     dword ptr [rax+rax+00h]
0x140060b19  mov     edi, eax
0x140060b1b  mov     ecx, eax
0x140060b1d  call    HsmDbgBreakOnStatus
0x140060b22  test    edi, edi
0x140060b24  jns     short loc_140060B81
0x140060b26  lea     r14, WPP_GLOBAL_Control
0x140060b2d  mov     rax, cs:WPP_GLOBAL_Control
0x140060b34  cmp     rax, r14
0x140060b37  jz      loc_140061B45
0x140060b3d  mov     ecx, [rax+2Ch]
0x140060b40  test    cl, 1
0x140060b43  jz      loc_140061B45
0x140060b49  cmp     byte ptr [rax+29h], 2
0x140060b4d  jb      loc_140061B45
0x140060b53  mov     edx, 69h ; 'i'
0x140060b58  mov     rcx, [rax+18h]
0x140060b5c  mov     dword ptr [rsp+268h+LookasideList], edi
0x140060b60  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140060b67  mov     r9, r15
0x140060b6a  mov     [rsp+268h+CleanupCallback], r13
0x140060b6f  call    WPP_SF_qqd
0x140060b74  mov     r12, [rsp+268h+var_190]
0x140060b7c  jmp     loc_140061B45
0x140060b81  lea     rax, [rsp+268h+var_1D0]
0x140060b89  mov     [rsp+268h+EcpContext], rax; EcpContext
0x140060b8e  lea     rax, qword_1400291C0
0x140060b95  mov     [rsp+268h+LookasideList], rax; LookasideList
0x140060b9a  mov     [rsp+268h+CleanupCallback], rbx; CleanupCallback
0x140060b9f  xor     r9d, r9d; Flags
0x140060ba2  lea     r8d, [r9+58h]; SizeOfContext
0x140060ba6  lea     rdx, GUID_ECP_ATOMIC_CREATE; EcpType
0x140060bad  mov     rcx, cs:Filter; Filter
0x140060bb4  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x140060bbb  nop     dword ptr [rax+rax+00h]
0x140060bc0  mov     edi, eax
0x140060bc2  mov     ecx, eax
0x140060bc4  call    HsmDbgBreakOnStatus
0x140060bc9  test    edi, edi
0x140060bcb  jns     short loc_140060C07
0x140060bcd  lea     r14, WPP_GLOBAL_Control
0x140060bd4  mov     rcx, cs:WPP_GLOBAL_Control
0x140060bdb  cmp     rcx, r14
0x140060bde  jz      loc_140061B45
0x140060be4  mov     eax, [rcx+2Ch]
0x140060be7  test    al, 1
0x140060be9  jz      loc_140061B45
0x140060bef  cmp     byte ptr [rcx+29h], 2
0x140060bf3  jb      loc_140061B45
0x140060bf9  mov     edx, 6Ah ; 'j'
0x140060bfe  mov     rcx, [rcx+18h]
0x140060c02  jmp     loc_140060B5C
0x140060c07  mov     r8, [rsp+268h+var_1D0]; EcpContext
0x140060c0f  mov     rdx, [rsp+268h+EcpList]; EcpList
0x140060c17  mov     rcx, cs:Filter; Filter
0x140060c1e  call    cs:__imp_FltInsertExtraCreateParameter
0x140060c25  nop     dword ptr [rax+rax+00h]
0x140060c2a  mov     [rsp+268h+LookasideList], rbx; HandleInformation
0x140060c2f  lea     rax, [rsp+268h+Object]
0x140060c37  mov     [rsp+268h+CleanupCallback], rax; Object
0x140060c3c  xor     r9d, r9d; AccessMode
0x140060c3f  mov     r8, cs:__imp_IoFileObjectType
0x140060c46  mov     r8, [r8]; ObjectType
0x140060c49  xor     edx, edx; DesiredAccess
0x140060c4b  mov     rcx, r13; Handle
0x140060c4e  call    cs:__imp_ObReferenceObjectByHandle
0x140060c55  nop     dword ptr [rax+rax+00h]
0x140060c5a  mov     edi, eax
0x140060c5c  mov     ecx, eax
0x140060c5e  call    HsmDbgBreakOnStatus
0x140060c63  test    edi, edi
0x140060c65  jns     short loc_140060C9D
0x140060c67  lea     r14, WPP_GLOBAL_Control
0x140060c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140060c75  cmp     rcx, r14
0x140060c78  jz      loc_140061B45
0x140060c7e  mov     eax, [rcx+2Ch]
0x140060c81  test    al, 1
0x140060c83  jz      loc_140061B45
0x140060c89  cmp     byte ptr [rcx+29h], 2
0x140060c8d  jb      loc_140061B45
0x140060c93  mov     edx, 6Bh ; 'k'
0x140060c98  jmp     loc_140060BFE
0x140060c9d  mov     [rsp+268h+var_1C8], ebx
0x140060ca4  mov     [rsp+268h+var_1B8], ebx
0x140060cab  mov     edi, ebx
0x140060cad  mov     esi, ebx
0x140060caf  lea     r14, WPP_GLOBAL_Control
0x140060cb6  lea     r12, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140060cbd  xor     edx, edx; Val
0x140060cbf  lea     r8d, [rdx+50h]; Size
0x140060cc3  lea     rcx, [rsp+268h+var_B8]; void *
0x140060ccb  call    memset
0x140060cd0  xorps   xmm0, xmm0
0x140060cd3  movups  [rsp+268h+var_140], xmm0
0x140060cdb  xor     eax, eax
0x140060cdd  movups  xmmword ptr [rsp+268h+ObjectAttributes.Length], xmm0
0x140060ce5  movups  xmmword ptr [rsp+268h+ObjectAttributes.ObjectName], xmm0
0x140060ced  movups  xmmword ptr [rsp+268h+ObjectAttributes+1Ch], xmm0
0x140060cf5  movups  xmmword ptr [rsp+268h+IoStatusBlock], xmm0
0x140060cfd  xorps   xmm1, xmm1
0x140060d00  movups  [rsp+268h+var_68], xmm1
0x140060d08  movups  [rsp+268h+var_58], xmm1
0x140060d10  mov     [rsp+268h+var_48], rax
0x140060d18  mov     edx, [rsp+268h+var_188]
0x140060d1f  mov     eax, [rsp+268h+var_1B8]
0x140060d26  sub     edx, eax
0x140060d28  cmp     edx, 50h ; 'P'
0x140060d2b  jb      loc_140061A2E
0x140060d31  add     rax, [rsp+268h+var_1C0]
0x140060d39  mov     [rsp+268h+var_1B0], rax
0x140060d41  movups  xmm2, xmmword ptr [rax]
0x140060d44  movaps  [rsp+268h+var_B8], xmm2
0x140060d4c  movups  xmm0, xmmword ptr [rax+10h]
0x140060d50  movaps  [rsp+268h+var_A8], xmm0
0x140060d58  movups  xmm1, xmmword ptr [rax+20h]
0x140060d5c  movaps  [rsp+268h+var_98], xmm1
0x140060d64  movups  xmm0, xmmword ptr [rax+30h]
0x140060d68  movaps  [rsp+268h+FileInformation], xmm0
0x140060d70  movups  xmm1, xmmword ptr [rax+40h]
0x140060d74  movaps  [rsp+268h+var_78], xmm1
0x140060d7c  psrldq  xmm2, 8
0x140060d81  movq    rcx, xmm2
0x140060d86  mov     rax, rcx
0x140060d89  shr     rax, 20h
0x140060d8d  movzx   r8d, ax
0x140060d91  mov     rax, rcx
0x140060d94  shr     rax, 30h
0x140060d98  mov     r9d, eax
0x140060d9b  lea     r13d, [rax+r8]
0x140060d9f  mov     word ptr [rsp+268h+var_B8+8], cx
0x140060da7  movzx   r11d, cx
0x140060dab  shr     rcx, 10h
0x140060daf  movzx   r10d, cx
0x140060db3  lea     eax, [r10+r11]
0x140060db7  cmp     eax, r13d
0x140060dba  cmova   r13d, eax
0x140060dbe  cmp     r11d, edx
0x140060dc1  ja      loc_1400619E0
0x140060dc7  mov     eax, edx
0x140060dc9  sub     eax, r11d
0x140060dcc  cmp     r10d, eax
0x140060dcf  ja      loc_1400619E0
0x140060dd5  cmp     r8d, edx
0x140060dd8  ja      loc_1400619E0
0x140060dde  mov     eax, edx
0x140060de0  sub     eax, r8d
0x140060de3  cmp     r9d, eax
0x140060de6  ja      loc_1400619E0
0x140060dec  mov     eax, 1000h
0x140060df1  cmp     r9w, ax
0x140060df5  ja      loc_1400619E0
0x140060dfb  mov     r8d, dword ptr [rsp+268h+var_B8]
0x140060e03  test    r8d, r8d
0x140060e06  jz      short loc_140060E1A
0x140060e08  cmp     r8d, r13d
0x140060e0b  jb      loc_1400619E0
0x140060e11  cmp     r8d, edx
0x140060e14  ja      loc_1400619E0
0x140060e1a  movzx   r9d, word ptr [rsp+268h+var_B8+8]
0x140060e23  mov     r11, [rsp+268h+var_1B0]
0x140060e2b  add     r9, r11
0x140060e2e  shr     r10w, 1
0x140060e32  movzx   ecx, bx
0x140060e35  mov     r13d, 1
0x140060e3b  cmp     bx, r10w
0x140060e3f  jnb     short loc_140060E67
0x140060e41  movzx   eax, cx
0x140060e44  movzx   edx, word ptr [r9+rax*2]
0x140060e49  cmp     dx, 5Ch ; '\'
0x140060e4d  jz      loc_140060EF5
0x140060e53  cmp     dx, 3Ah ; ':'
0x140060e57  jz      loc_140060EF5
0x140060e5d  add     cx, r13w
0x140060e61  cmp     cx, r10w
0x140060e65  jb      short loc_140060E41
0x140060e67  test    r8b, 3
0x140060e6b  jnz     loc_140061982
  ... truncated ...
```
