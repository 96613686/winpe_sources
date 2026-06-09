# HsmpOpCreatePlaceholders

- ea: `0x14006079c`
- end: `0x140061b3a`
- name: `HsmpOpCreatePlaceholders`
- size: `5022`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140043bac`
- `0x14006037c`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000b62c`
- `0x14000c12c`
- `0x14000dbd0`
- `0x1400155e0`
- `0x14001dbfc`
- `0x14001e140`
- `0x14001e580`
- `0x140035384`
- `0x140037010`
- `0x140050280`
- `0x14006079c`
- `0x14006ac24`
- `0x14006b728`
- `0x14007658c`
- `0x140077898`
- `0x14007e2d0`
- `0x140081b90`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006094b`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006094b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140060b2e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140060b2e`
- `ntoskrnl!IoFileObjectType` at `0x140060b1f`
- `ntoskrnl!ObfDereferenceObject` at `0x1400617ec`
- `ntoskrnl!ObfDereferenceObject` at `0x140061b08`
- `ntoskrnl!ObfDereferenceObject` at `0x1400617ec`
- `ntoskrnl!ObfDereferenceObject` at `0x140061b08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061a3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061aef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061a3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061aef`
- `ntoskrnl!ExAllocatePool2` at `0x1400608b8`
- `ntoskrnl!ExAllocatePool2` at `0x14006097f`
- `ntoskrnl!ExAllocatePool2` at `0x1400608b8`
- `ntoskrnl!ExAllocatePool2` at `0x14006097f`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x1400609ed`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x1400609ed`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140061a5a`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140061a5a`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140060afe`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140060afe`
- `FLTMGR!FltSetInformationFile` at `0x140061556`
- `FLTMGR!FltSetInformationFile` at `0x140061659`
- `FLTMGR!FltSetInformationFile` at `0x140061556`
- `FLTMGR!FltSetInformationFile` at `0x140061659`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140060a94`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140060a94`
- `FLTMGR!FltCreateFileEx` at `0x140061346`
- `FLTMGR!FltCreateFileEx` at `0x140061346`
- `FLTMGR!FltClose` at `0x14006180d`
- `FLTMGR!FltClose` at `0x14006180d`
- `FLTMGR!FltQueryInformationFile` at `0x140061721`
- `FLTMGR!FltQueryInformationFile` at `0x140061721`
- `FLTMGR!FltCreateFileEx2` at `0x140061272`
- `FLTMGR!FltCreateFileEx2` at `0x140061272`

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
  __int64 LastEffectiveUsn; // rsi
  unsigned int v19; // edx
  unsigned __int64 v20; // xmm2_8
  unsigned int v21; // r9d
  unsigned int v22; // r13d
  int v23; // r11d
  __int8 *v24; // r9
  unsigned __int16 v25; // cx
  char v26; // r13
  __int16 v27; // dx
  __int64 v28; // r8
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  ULONG FileAttributes; // r9d
  int v32; // ecx
  int v33; // eax
  char v34; // cl
  PDEVICE_OBJECT v35; // rcx
  __int64 v36; // rdx
  _WORD *v37; // rcx
  __int64 v38; // rcx
  char v39; // r13
  __m128i *v40; // r13
  __m128i *v41; // r13
  PFILE_OBJECT v42; // rdx
  __int32 v43; // eax
  PDEVICE_OBJECT v44; // rcx
  __int64 v45; // rdx
  int v46; // r12d
  __int16 LookasideList; // [rsp+28h] [rbp-240h]
  unsigned __int8 v50; // [rsp+88h] [rbp-1E0h]
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp-1D8h] BYREF
  PVOID EcpContext; // [rsp+98h] [rbp-1D0h] BYREF
  int v53; // [rsp+A0h] [rbp-1C8h]
  char *v54; // [rsp+A8h] [rbp-1C0h]
  unsigned __int32 v55; // [rsp+B0h] [rbp-1B8h]
  __m128i *v56; // [rsp+B8h] [rbp-1B0h]
  int v57; // [rsp+C0h] [rbp-1A8h]
  unsigned __int32 v58; // [rsp+C4h] [rbp-1A4h]
  int v59; // [rsp+C8h] [rbp-1A0h]
  PFLT_INSTANCE Instance; // [rsp+D0h] [rbp-198h]
  void *v61; // [rsp+D8h] [rbp-190h]
  unsigned int v62; // [rsp+E0h] [rbp-188h]
  PVOID P; // [rsp+E8h] [rbp-180h]
  void *FileHandle; // [rsp+F0h] [rbp-178h] BYREF
  PECP_LIST EcpList; // [rsp+F8h] [rbp-170h] BYREF
  void *v66; // [rsp+100h] [rbp-168h]
  PVOID Object; // [rsp+108h] [rbp-160h] BYREF
  union _LARGE_INTEGER AllocationSize; // [rsp+110h] [rbp-158h] BYREF
  void *v69; // [rsp+118h] [rbp-150h]
  __int64 v70; // [rsp+120h] [rbp-148h]
  __int128 v71; // [rsp+128h] [rbp-140h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+138h] [rbp-130h] BYREF
  __int64 v73; // [rsp+158h] [rbp-110h]
  _DWORD *v74; // [rsp+160h] [rbp-108h]
  size_t v75; // [rsp+168h] [rbp-100h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+170h] [rbp-F8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+1A0h] [rbp-C8h] BYREF
  __m128i v78[5]; // [rsp+1B0h] [rbp-B8h] BYREF
  __m128i v79; // [rsp+200h] [rbp-68h] BYREF
  __m128i v80; // [rsp+210h] [rbp-58h]
  unsigned __int64 v81; // [rsp+220h] [rbp-48h]

  v7 = a4;
  v61 = a4;
  v59 = a3;
  v8 = a2;
  v70 = a1;
  v69 = a2;
  v66 = a4;
  v62 = Size;
  v74 = a6;
  Instance = *(PFLT_INSTANCE *)(a1 + 32);
  AllocationSize.QuadPart = 0;
  FileHandle = 0;
  FileObject = 0;
  LOBYTE(v6) = 1;
  v57 = v6;
  Object = 0;
  if ( (unsigned int)Feature_ReFS_OneDrive_Support__private_IsEnabledDeviceUsageNoInline() )
  {
    LOBYTE(v6) = *(_DWORD *)(a1 + 80) != 28;
    v57 = (unsigned __int8)v6;
  }
  memset(&DriverContext, 0, sizeof(DriverContext));
  LOWORD(v73) = 0;
  P = 0;
  EcpList = 0;
  EcpContext = 0;
  v75 = Size;
  Pool2 = (char *)ExAllocatePool2(258, Size, 1884517192);
  v11 = Pool2;
  v54 = Pool2;
  if ( !Pool2 )
  {
    v12 = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
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
  if ( v62 && ((unsigned __int8)v7 & 3) != 0 )
    ExRaiseDatatypeMisalignment();
  RtlCopyFromUser(Pool2, v7, Size);
  if ( (_BYTE)v6 )
  {
    P = (PVOID)ExAllocatePool2(256, 0x4000, 1884451656);
    if ( !P )
    {
      v12 = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
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
    HsmDbgBreakOnStatus((unsigned int)v12);
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
      v7 = v61;
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
    HsmDbgBreakOnStatus((unsigned int)v12);
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
  HsmDbgBreakOnStatus((unsigned int)v12);
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
  v53 = 0;
  v55 = 0;
  v12 = 0;
  LODWORD(LastEffectiveUsn) = 0;
  while ( 1 )
  {
    memset(v78, 0, sizeof(v78));
    v71 = 0;
    memset(&ObjectAttributes, 0, 44);
    IoStatusBlock = 0;
    v79 = 0;
    v80 = 0;
    v81 = 0;
    v19 = v62 - v55;
    if ( v62 - v55 < 0x50 )
    {
      LODWORD(LastEffectiveUsn) = -1073688821;
      HsmDbgBreakOnStatus(3221278475LL);
      v12 = v53 == 0 ? 0xC000CF0B : 0;
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_192;
      }
      v45 = 108;
LABEL_182:
      WPP_SF_qqd(v44->AttachedDevice, v45, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids, a1, v8, -1073688821);
      goto LABEL_192;
    }
    v56 = (__m128i *)&v54[v55];
    v78[0] = *v56;
    v78[1] = v56[1];
    v78[2] = v56[2];
    v78[3] = v56[3];
    v78[4] = v56[4];
    v20 = _mm_srli_si128(v78[0], 8).m128i_u64[0];
    v21 = HIWORD(v20);
    v22 = v21 + WORD2(v20);
    v78[0].m128i_i16[4] = v20;
    if ( WORD1(v20) + (unsigned int)(unsigned __int16)v20 > v22 )
      v22 = WORD1(v20) + (unsigned __int16)v20;
    if ( (unsigned __int16)v20 > v19
      || WORD1(v20) > v19 - (unsigned __int16)v20
      || WORD2(v20) > v19
      || v21 > v19 - WORD2(v20)
      || HIWORD(v20) > 0x1000u
      || v78[0].m128i_i32[0] && (v78[0].m128i_i32[0] < v22 || v78[0].m128i_i32[0] > v19) )
    {
      break;
    }
    v23 = (int)v56;
    v24 = &v56->m128i_i8[v78[0].m128i_u16[4]];
    v25 = 0;
    v26 = 1;
    if ( WORD1(v20) >> 1 )
    {
      while ( 1 )
      {
        v27 = *(_WORD *)&v24[2 * v25];
        if ( v27 == 92 || v27 == 58 )
          break;
        if ( ++v25 >= (unsigned __int16)(WORD1(v20) >> 1) )
          goto LABEL_53;
      }
      LODWORD(LastEffectiveUsn) = -1073688821;
      HsmDbgBreakOnStatus(3221278475LL);
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_164;
      v8 = a2;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v30 = 110;
        goto LABEL_68;
      }
      goto LABEL_165;
    }
LABEL_53:
    if ( (v78[0].m128i_i8[0] & 3) != 0 )
    {
      LODWORD(LastEffectiveUsn) = -1073688821;
      HsmDbgBreakOnStatus(3221278475LL);
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_191;
      v8 = a2;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_192;
      v45 = 111;
      goto LABEL_182;
    }
    if ( ((v78[3].m128i_i8[0] & 0x10) != 0 || (v59 & 2) != 0 || !v78[3].m128i_i64[1])
      && ((v78[3].m128i_i8[0] & 0x10) == 0 || (v59 & 4) != 0 || (v78[0].m128i_i8[4] & 0x40) != 0) )
    {
      if ( !v78[0].m128i_i16[7] )
      {
        LODWORD(LastEffectiveUsn) = -1073688821;
        HsmDbgBreakOnStatus(3221278475LL);
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_164;
        v8 = a2;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v30 = 113;
          goto LABEL_68;
        }
        goto LABEL_165;
      }
      ++v53;
      v78[4].m128i_i32[0] = -1073688825;
      v78[4].m128i_i64[1] = 0;
      if ( (v78[3].m128i_i8[0] & 0x10) != 0 )
      {
        v50 = 1;
        LastEffectiveUsn = (unsigned int)HsmpAccessCheck(a1, Object, 4, v24);
        HsmDbgBreakOnStatus(LastEffectiveUsn);
        if ( (int)LastEffectiveUsn < 0 )
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
        v23 = (int)v56;
      }
      else
      {
        v26 = 0;
        v50 = 0;
      }
      FileAttributes = v78[3].m128i_i32[0] | 0x401000;
      v58 = v78[3].m128i_i32[0] | 0x401000;
      if ( v26 )
      {
        v28 = 16;
        if ( (v78[0].m128i_i8[4] & 0x40) != 0 )
        {
          v28 = 22;
          FileAttributes = v78[3].m128i_i32[0] & 0xFFBFEFFF;
          v58 = v78[3].m128i_i32[0] & 0xFFBFEFFF;
        }
      }
      else
      {
        v28 = ((unsigned __int32)v78[3].m128i_i32[0] >> 9) & 1;
      }
      v32 = v28 | 0x40;
      if ( (v78[0].m128i_i8[4] & 1) == 0 )
        v32 = v28;
      v33 = v32 | 0x100;
      if ( (v78[0].m128i_i16[2] & 0x400) == 0 )
        v33 = v32;
      LODWORD(v66) = v33;
      v34 = v57;
      if ( (_BYTE)v57 )
      {
        LastEffectiveUsn = (unsigned int)HsmpRpBuildBuffer(
                                           v78[3].m128i_i32[2],
                                           v33,
                                           v23 + (unsigned int)v78[0].m128i_u16[6],
                                           v78[0].m128i_u16[7],
                                           (__int64)P,
                                           LookasideList);
        HsmDbgBreakOnStatus(LastEffectiveUsn);
        if ( (int)LastEffectiveUsn < 0 )
        {
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v36 = 115;
            goto LABEL_97;
          }
LABEL_164:
          v8 = a2;
          goto LABEL_165;
        }
        *(_WORD *)EcpContext = 88;
        *((_WORD *)EcpContext + 1) = 7730;
        *((_WORD *)EcpContext + 2) = 0;
        v37 = P;
        *((_QWORD *)EcpContext + 1) = P;
        *((_WORD *)EcpContext + 3) = v37[2] + 8;
        *((_QWORD *)EcpContext + 4) = &v78[1];
        FileAttributes = v58;
        *((_DWORD *)EcpContext + 10) = v58;
        if ( !v26 )
        {
          v38 = v78[3].m128i_i64[1];
          if ( v78[3].m128i_i64[1] > 0 )
          {
            *((_WORD *)EcpContext + 1) |= 1u;
            v38 = v78[3].m128i_i64[1];
          }
          *((_QWORD *)EcpContext + 2) = v38;
          *((_QWORD *)EcpContext + 3) = v78[3].m128i_i64[1];
          *((_WORD *)EcpContext + 1) |= 0xCu;
        }
        *((_DWORD *)EcpContext + 11) = 8;
        *(_DWORD *)(&DriverContext.Size + 1) = 0;
        *(&DriverContext.Size + 3) = 0;
        *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
        DriverContext.Size = 40;
        v73 = 1;
        DriverContext.ExtraCreateParameter = EcpList;
        v34 = v57;
      }
      v39 = v34;
      *((_QWORD *)&v71 + 1) = (char *)v56 + v78[0].m128i_u16[4];
      LOWORD(v71) = v78[0].m128i_i16[5];
      WORD1(v71) = v78[0].m128i_i16[5];
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = a2;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v71;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( v34 )
      {
        LastEffectiveUsn = (unsigned int)FltCreateFileEx2(
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
                                           v50 | 0x208020,
                                           0,
                                           0,
                                           0x800u,
                                           &DriverContext);
        HsmDbgBreakOnStatus(LastEffectiveUsn);
        if ( ((_DWORD)LastEffectiveUsn == -1073741771 || (_DWORD)LastEffectiveUsn == -1073741191)
          && (v78[0].m128i_i16[2] & 0x4000) != 0 )
        {
          v39 = 0;
        }
      }
      if ( !v39 )
      {
        LastEffectiveUsn = (unsigned int)FltCreateFileEx(
                                           Filter,
                                           Instance,
                                           &FileHandle,
                                           &FileObject,
                                           0x100180u,
                                           &ObjectAttributes,
                                           &IoStatusBlock,
                                           &AllocationSize,
                                           v78[3].m128i_i32[0] | 0x1000,
                                           0,
                                           ~(unsigned __int8)((unsigned __int32)v78[0].m128i_i32[1] >> 13) & 2,
                                           v50 | 0x208020,
                                           0,
                                           0,
                                           0x800u);
        HsmDbgBreakOnStatus(LastEffectiveUsn);
      }
      if ( (int)LastEffectiveUsn < 0 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_164;
        }
        v36 = 116;
        goto LABEL_97;
      }
      if ( v39 )
      {
        v40 = v56;
        v56[1] = v78[1];
        v40[2] = v78[2];
        v40[3].m128i_i32[0] = *((_DWORD *)EcpContext + 10);
        v40[4].m128i_i64[1] = *((_QWORD *)EcpContext + 6);
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
      LastEffectiveUsn = (unsigned int)HsmpMarkHandleUsnSourceInfo(a1, FileObject, 8, 0);
      HsmDbgBreakOnStatus(LastEffectiveUsn);
      if ( (int)LastEffectiveUsn < 0 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_164;
        }
        v36 = 117;
        goto LABEL_97;
      }
      v41 = v56;
      LookasideList = v78[0].m128i_i16[7];
      LastEffectiveUsn = (unsigned int)HsmpRpCreate(
                                         a1,
                                         FileObject,
                                         v78[3].m128i_i64[1],
                                         (unsigned int)v66,
                                         &v56->m128i_i8[v78[0].m128i_u16[6]]);
      HsmDbgBreakOnStatus(LastEffectiveUsn);
      if ( (int)LastEffectiveUsn < 0 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_164;
        }
        v36 = 118;
        goto LABEL_97;
      }
      if ( v50 || !v78[3].m128i_i64[1] )
        goto LABEL_144;
      LOBYTE(v28) = 1;
      LastEffectiveUsn = (unsigned int)HsmpToggleFileSparseAttribute(a1, FileObject, v28);
      HsmDbgBreakOnStatus(LastEffectiveUsn);
      if ( (int)LastEffectiveUsn < 0 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_164;
        }
        v36 = 119;
        goto LABEL_97;
      }
      LastEffectiveUsn = (unsigned int)FltSetInformationFile(
                                         Instance,
                                         FileObject,
                                         &v78[3].m128i_u64[1],
                                         8u,
                                         FileEndOfFileInformation);
      HsmDbgBreakOnStatus(LastEffectiveUsn);
      if ( (int)LastEffectiveUsn < 0 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_164;
        }
        v36 = 120;
        goto LABEL_97;
      }
      LastEffectiveUsn = (unsigned int)HsmpSetFileVDL(Instance, FileObject, v78[3].m128i_i64[1]);
      HsmDbgBreakOnStatus(LastEffectiveUsn);
      if ( (int)LastEffectiveUsn >= 0 )
      {
LABEL_144:
        v79 = v78[1];
        v80 = v78[2];
        v81 = __PAIR64__(v78[3].m128i_u32[1], v58);
        LastEffectiveUsn = (unsigned int)FltSetInformationFile(Instance, FileObject, &v79, 0x28u, FileBasicInformation);
        HsmDbgBreakOnStatus(LastEffectiveUsn);
        if ( (int)LastEffectiveUsn >= 0 )
        {
          LastEffectiveUsn = (unsigned int)HsmpQueryLastEffectiveUsn(Instance, FileObject, &v41[4].m128i_i64[1]);
          HsmDbgBreakOnStatus(LastEffectiveUsn);
          if ( (int)LastEffectiveUsn >= 0 )
          {
            LastEffectiveUsn = (unsigned int)FltQueryInformationFile(
                                               Instance,
                                               FileObject,
                                               &v79,
                                               0x28u,
                                               FileBasicInformation,
                                               0);
            HsmDbgBreakOnStatus(LastEffectiveUsn);
            if ( (int)LastEffectiveUsn >= 0 )
            {
              v41[1] = v79;
              v41[2] = v80;
              v41[3].m128i_i64[0] = v81;
              goto LABEL_160;
            }
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_164;
            }
            v36 = 124;
          }
          else
          {
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_164;
            }
            v36 = 123;
          }
        }
        else
        {
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_164;
          }
          v36 = 122;
        }
      }
      else
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_164;
        }
        v36 = 121;
      }
LABEL_97:
      WPP_SF_qqd(
        v35->AttachedDevice,
        v36,
        WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        a1,
        FileObject,
        LastEffectiveUsn);
      goto LABEL_164;
    }
    LODWORD(LastEffectiveUsn) = -1073688821;
    HsmDbgBreakOnStatus(3221278475LL);
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_164;
    v8 = a2;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v30 = 112;
LABEL_68:
      WPP_SF_qqd(v29->AttachedDevice, v30, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids, a1, v8, -1073688821);
    }
LABEL_165:
    v56[4].m128i_i32[0] = LastEffectiveUsn;
    v42 = FileObject;
    if ( FileObject )
    {
      if ( (int)LastEffectiveUsn < 0 )
        HsmpSetFileDisposition(*(struct _FLT_INSTANCE **)(a1 + 32), FileObject);
      ObfDereferenceObject(FileObject);
      FileObject = 0;
    }
    if ( FileHandle )
    {
      FltClose(FileHandle);
      FileHandle = 0;
    }
    if ( (int)LastEffectiveUsn >= 0 || (v59 & 1) == 0 )
    {
      v43 = v78[0].m128i_i32[0] ? v78[0].m128i_i32[0] + v55 : 0;
      v55 = v43;
      if ( v43 )
        continue;
    }
    goto LABEL_192;
  }
  LODWORD(LastEffectiveUsn) = -1073688821;
  HsmDbgBreakOnStatus(3221278475LL);
  v12 = v53 == 0 ? 0xC000CF0B : 0;
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
  v46 = v53;
  if ( v53 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqdd(WPP_GLOBAL_Control->AttachedDevice, v42, v28, a1, v8, v53, v12);
    }
  }
  else
  {
    v12 = LastEffectiveUsn;
  }
  *v74 = v46;
LABEL_9:
  v7 = v61;
LABEL_199:
  v11 = v54;
LABEL_200:
  if ( P )
    ExFreePoolWithTag(P, 0x70527348u);
  if ( EcpList )
    FltFreeExtraCreateParameterList(Filter, EcpList);
  if ( v11 )
  {
    if ( v12 >= 0 )
      RtlCopyToUser(v7, v11, v75);
    ExFreePoolWithTag(v11, 0x70537348u);
  }
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14006079c  mov     r11, rsp
0x14006079f  push    rbx
0x1400607a0  push    rsi
0x1400607a1  push    rdi
0x1400607a2  push    r12
0x1400607a4  push    r13
0x1400607a6  push    r14
0x1400607a8  push    r15
0x1400607aa  sub     rsp, 230h
0x1400607b1  mov     rax, cs:__security_cookie
0x1400607b8  xor     rax, rsp
0x1400607bb  mov     [rsp+268h+var_40], rax
0x1400607c3  mov     r12, r9
0x1400607c6  mov     [rsp+268h+var_190], r9
0x1400607ce  mov     [rsp+268h+var_1A0], r8d
0x1400607d6  mov     r13, rdx
0x1400607d9  mov     [rsp+268h+var_1E8], rdx
0x1400607e1  mov     r15, rcx
0x1400607e4  mov     [rsp+268h+var_148], rcx
0x1400607ec  mov     [rsp+268h+var_150], rdx
0x1400607f4  mov     [rsp+268h+var_168], r9
0x1400607fc  mov     esi, dword ptr [rsp+268h+Size]
0x140060803  mov     [rsp+268h+var_188], esi
0x14006080a  mov     rax, [rsp+268h+arg_28]
0x140060812  mov     [rsp+268h+var_108], rax
0x14006081a  mov     rax, [rcx+20h]
0x14006081e  mov     [rsp+268h+Instance], rax
0x140060826  xor     ebx, ebx
0x140060828  mov     [r11-158h], rbx
0x14006082f  mov     [r11-178h], rbx
0x140060836  mov     [r11-1D8h], rbx
0x14006083d  mov     dil, 1
0x140060840  mov     [rsp+268h+var_1A8], edi
0x140060847  mov     [r11-160h], rbx
0x14006084e  call    Feature_ReFS_OneDrive_Support__private_IsEnabledDeviceUsageNoInline
0x140060853  test    eax, eax
0x140060855  jz      short loc_14006086A
0x140060857  movzx   edi, dil
0x14006085b  cmp     dword ptr [r15+50h], 1Ch
0x140060860  cmovz   edi, ebx
0x140060863  mov     [rsp+268h+var_1A8], edi
0x14006086a  xor     eax, eax
0x14006086c  xorps   xmm0, xmm0
0x14006086f  movups  xmmword ptr [rsp+268h+var_130.Size], xmm0
0x140060877  movups  xmmword ptr [rsp+268h+var_130.DeviceObjectHint], xmm0
0x14006087f  mov     word ptr [rsp+268h+var_110], ax
0x140060887  mov     [rsp+268h+P], rbx
0x14006088f  mov     [rsp+268h+EcpList], rbx
0x140060897  mov     [rsp+268h+var_1D0], rbx
0x14006089f  mov     r14, rsi
0x1400608a2  mov     [rsp+268h+var_100], rsi
0x1400608aa  mov     r8d, 70537348h
0x1400608b0  mov     rdx, rsi
0x1400608b3  mov     ecx, 102h
0x1400608b8  call    cs:__imp_ExAllocatePool2
0x1400608bf  nop     dword ptr [rax+rax+00h]
0x1400608c4  mov     rsi, rax
0x1400608c7  mov     [rsp+268h+var_1C0], rax
0x1400608cf  test    rax, rax
0x1400608d2  jnz     short loc_14006093C
0x1400608d4  mov     esi, 0C000009Ah
0x1400608d9  mov     edi, esi
0x1400608db  mov     ecx, esi
0x1400608dd  call    HsmDbgBreakOnStatus
0x1400608e2  lea     r14, WPP_GLOBAL_Control
0x1400608e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400608f0  cmp     rcx, r14
0x1400608f3  jz      loc_140061A1D
0x1400608f9  mov     eax, [rcx+2Ch]
0x1400608fc  test    al, 1
0x1400608fe  jz      loc_140061A1D
0x140060904  cmp     byte ptr [rcx+29h], 2
0x140060908  jb      loc_140061A1D
0x14006090e  mov     edx, 63h ; 'c'
0x140060913  mov     dword ptr [rsp+268h+LookasideList], esi
0x140060917  mov     [rsp+268h+CleanupCallback], r13
0x14006091c  mov     r9, r15
0x14006091f  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140060926  mov     rcx, [rcx+18h]
0x14006092a  call    WPP_SF_qqd
0x14006092f  mov     r12, [rsp+268h+var_190]
0x140060937  jmp     loc_140061A1D
0x14006093c  cmp     [rsp+268h+var_188], ebx
0x140060943  jz      short loc_140060957
0x140060945  test    r12b, 3
0x140060949  jz      short loc_140060957
0x14006094b  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140060952  nop     dword ptr [rax+rax+00h]
0x140060957  mov     r8, r14; Size
0x14006095a  mov     rdx, r12; Src
0x14006095d  mov     rcx, rax; void *
0x140060960  call    RtlCopyFromUser
0x140060965  nop
0x140060966  test    dil, dil
0x140060969  jz      loc_140060B0A
0x14006096f  mov     edx, 4000h
0x140060974  mov     ecx, 100h
0x140060979  mov     r8d, 70527348h
0x14006097f  call    cs:__imp_ExAllocatePool2
0x140060986  nop     dword ptr [rax+rax+00h]
0x14006098b  mov     [rsp+268h+P], rax
0x140060993  test    rax, rax
0x140060996  jnz     short loc_1400609DC
0x140060998  mov     esi, 0C000009Ah
0x14006099d  mov     edi, esi
0x14006099f  mov     ecx, esi
0x1400609a1  call    HsmDbgBreakOnStatus
0x1400609a6  lea     r14, WPP_GLOBAL_Control
0x1400609ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400609b4  cmp     rcx, r14
0x1400609b7  jz      loc_140061A1D
0x1400609bd  mov     eax, [rcx+2Ch]
0x1400609c0  test    al, 1
0x1400609c2  jz      loc_140061A1D
0x1400609c8  cmp     byte ptr [rcx+29h], 2
0x1400609cc  jb      loc_140061A1D
0x1400609d2  mov     edx, 68h ; 'h'
0x1400609d7  jmp     loc_140060913
0x1400609dc  lea     r8, [rsp+268h+EcpList]; EcpList
0x1400609e4  xor     edx, edx; Flags
0x1400609e6  mov     rcx, cs:Filter; Filter
0x1400609ed  call    cs:__imp_FltAllocateExtraCreateParameterList
0x1400609f4  nop     dword ptr [rax+rax+00h]
0x1400609f9  mov     edi, eax
0x1400609fb  mov     ecx, eax
0x1400609fd  call    HsmDbgBreakOnStatus
0x140060a02  test    edi, edi
0x140060a04  jns     short loc_140060A61
0x140060a06  lea     r14, WPP_GLOBAL_Control
0x140060a0d  mov     rax, cs:WPP_GLOBAL_Control
0x140060a14  cmp     rax, r14
0x140060a17  jz      loc_140061A25
0x140060a1d  mov     ecx, [rax+2Ch]
0x140060a20  test    cl, 1
0x140060a23  jz      loc_140061A25
0x140060a29  cmp     byte ptr [rax+29h], 2
0x140060a2d  jb      loc_140061A25
0x140060a33  mov     edx, 69h ; 'i'
0x140060a38  mov     rcx, [rax+18h]
0x140060a3c  mov     dword ptr [rsp+268h+LookasideList], edi
0x140060a40  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140060a47  mov     r9, r15
0x140060a4a  mov     [rsp+268h+CleanupCallback], r13
0x140060a4f  call    WPP_SF_qqd
0x140060a54  mov     r12, [rsp+268h+var_190]
0x140060a5c  jmp     loc_140061A25
0x140060a61  lea     rax, [rsp+268h+var_1D0]
0x140060a69  mov     [rsp+268h+EcpContext], rax; EcpContext
0x140060a6e  lea     rax, qword_1400291C0
0x140060a75  mov     [rsp+268h+LookasideList], rax; LookasideList
0x140060a7a  mov     [rsp+268h+CleanupCallback], rbx; CleanupCallback
0x140060a7f  xor     r9d, r9d; Flags
0x140060a82  lea     r8d, [r9+58h]; SizeOfContext
0x140060a86  lea     rdx, GUID_ECP_ATOMIC_CREATE; EcpType
0x140060a8d  mov     rcx, cs:Filter; Filter
0x140060a94  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x140060a9b  nop     dword ptr [rax+rax+00h]
0x140060aa0  mov     edi, eax
0x140060aa2  mov     ecx, eax
0x140060aa4  call    HsmDbgBreakOnStatus
0x140060aa9  test    edi, edi
0x140060aab  jns     short loc_140060AE7
0x140060aad  lea     r14, WPP_GLOBAL_Control
0x140060ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x140060abb  cmp     rcx, r14
0x140060abe  jz      loc_140061A25
0x140060ac4  mov     eax, [rcx+2Ch]
0x140060ac7  test    al, 1
0x140060ac9  jz      loc_140061A25
0x140060acf  cmp     byte ptr [rcx+29h], 2
0x140060ad3  jb      loc_140061A25
0x140060ad9  mov     edx, 6Ah ; 'j'
0x140060ade  mov     rcx, [rcx+18h]
0x140060ae2  jmp     loc_140060A3C
0x140060ae7  mov     r8, [rsp+268h+var_1D0]; EcpContext
0x140060aef  mov     rdx, [rsp+268h+EcpList]; EcpList
0x140060af7  mov     rcx, cs:Filter; Filter
0x140060afe  call    cs:__imp_FltInsertExtraCreateParameter
0x140060b05  nop     dword ptr [rax+rax+00h]
0x140060b0a  mov     [rsp+268h+LookasideList], rbx; HandleInformation
0x140060b0f  lea     rax, [rsp+268h+Object]
0x140060b17  mov     [rsp+268h+CleanupCallback], rax; Object
0x140060b1c  xor     r9d, r9d; AccessMode
0x140060b1f  mov     r8, cs:__imp_IoFileObjectType
0x140060b26  mov     r8, [r8]; ObjectType
0x140060b29  xor     edx, edx; DesiredAccess
0x140060b2b  mov     rcx, r13; Handle
0x140060b2e  call    cs:__imp_ObReferenceObjectByHandle
0x140060b35  nop     dword ptr [rax+rax+00h]
0x140060b3a  mov     edi, eax
0x140060b3c  mov     ecx, eax
0x140060b3e  call    HsmDbgBreakOnStatus
0x140060b43  test    edi, edi
0x140060b45  jns     short loc_140060B7D
0x140060b47  lea     r14, WPP_GLOBAL_Control
0x140060b4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140060b55  cmp     rcx, r14
0x140060b58  jz      loc_140061A25
0x140060b5e  mov     eax, [rcx+2Ch]
0x140060b61  test    al, 1
0x140060b63  jz      loc_140061A25
0x140060b69  cmp     byte ptr [rcx+29h], 2
0x140060b6d  jb      loc_140061A25
0x140060b73  mov     edx, 6Bh ; 'k'
0x140060b78  jmp     loc_140060ADE
0x140060b7d  mov     [rsp+268h+var_1C8], ebx
0x140060b84  mov     [rsp+268h+var_1B8], ebx
0x140060b8b  mov     edi, ebx
0x140060b8d  mov     esi, ebx
0x140060b8f  lea     r14, WPP_GLOBAL_Control
0x140060b96  lea     r12, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140060b9d  xor     edx, edx; Val
0x140060b9f  lea     r8d, [rdx+50h]; Size
0x140060ba3  lea     rcx, [rsp+268h+var_B8]; void *
0x140060bab  call    memset
0x140060bb0  xorps   xmm0, xmm0
0x140060bb3  movups  [rsp+268h+var_140], xmm0
0x140060bbb  xor     eax, eax
0x140060bbd  movups  xmmword ptr [rsp+268h+ObjectAttributes.Length], xmm0
0x140060bc5  movups  xmmword ptr [rsp+268h+ObjectAttributes.ObjectName], xmm0
0x140060bcd  movups  xmmword ptr [rsp+268h+ObjectAttributes+1Ch], xmm0
0x140060bd5  movups  xmmword ptr [rsp+268h+IoStatusBlock], xmm0
0x140060bdd  xorps   xmm1, xmm1
0x140060be0  movups  [rsp+268h+var_68], xmm1
0x140060be8  movups  [rsp+268h+var_58], xmm1
0x140060bf0  mov     [rsp+268h+var_48], rax
0x140060bf8  mov     edx, [rsp+268h+var_188]
0x140060bff  mov     eax, [rsp+268h+var_1B8]
0x140060c06  sub     edx, eax
0x140060c08  cmp     edx, 50h ; 'P'
0x140060c0b  jb      loc_14006190E
0x140060c11  add     rax, [rsp+268h+var_1C0]
0x140060c19  mov     [rsp+268h+var_1B0], rax
0x140060c21  movups  xmm2, xmmword ptr [rax]
0x140060c24  movaps  [rsp+268h+var_B8], xmm2
0x140060c2c  movups  xmm0, xmmword ptr [rax+10h]
0x140060c30  movaps  [rsp+268h+var_A8], xmm0
0x140060c38  movups  xmm1, xmmword ptr [rax+20h]
0x140060c3c  movaps  [rsp+268h+var_98], xmm1
0x140060c44  movups  xmm0, xmmword ptr [rax+30h]
0x140060c48  movaps  [rsp+268h+FileInformation], xmm0
0x140060c50  movups  xmm1, xmmword ptr [rax+40h]
0x140060c54  movaps  [rsp+268h+var_78], xmm1
0x140060c5c  psrldq  xmm2, 8
0x140060c61  movq    rcx, xmm2
0x140060c66  mov     rax, rcx
0x140060c69  shr     rax, 20h
0x140060c6d  movzx   r8d, ax
0x140060c71  mov     rax, rcx
0x140060c74  shr     rax, 30h
0x140060c78  mov     r9d, eax
0x140060c7b  lea     r13d, [rax+r8]
0x140060c7f  mov     word ptr [rsp+268h+var_B8+8], cx
0x140060c87  movzx   r11d, cx
0x140060c8b  shr     rcx, 10h
0x140060c8f  movzx   r10d, cx
0x140060c93  lea     eax, [r10+r11]
0x140060c97  cmp     eax, r13d
0x140060c9a  cmova   r13d, eax
0x140060c9e  cmp     r11d, edx
0x140060ca1  ja      loc_1400618C0
0x140060ca7  mov     eax, edx
0x140060ca9  sub     eax, r11d
0x140060cac  cmp     r10d, eax
0x140060caf  ja      loc_1400618C0
0x140060cb5  cmp     r8d, edx
0x140060cb8  ja      loc_1400618C0
0x140060cbe  mov     eax, edx
0x140060cc0  sub     eax, r8d
0x140060cc3  cmp     r9d, eax
0x140060cc6  ja      loc_1400618C0
0x140060ccc  mov     eax, 1000h
0x140060cd1  cmp     r9w, ax
0x140060cd5  ja      loc_1400618C0
0x140060cdb  mov     r8d, dword ptr [rsp+268h+var_B8]
0x140060ce3  test    r8d, r8d
0x140060ce6  jz      short loc_140060CFA
0x140060ce8  cmp     r8d, r13d
0x140060ceb  jb      loc_1400618C0
0x140060cf1  cmp     r8d, edx
0x140060cf4  ja      loc_1400618C0
0x140060cfa  movzx   r9d, word ptr [rsp+268h+var_B8+8]
0x140060d03  mov     r11, [rsp+268h+var_1B0]
0x140060d0b  add     r9, r11
0x140060d0e  shr     r10w, 1
0x140060d12  movzx   ecx, bx
0x140060d15  mov     r13d, 1
0x140060d1b  cmp     bx, r10w
0x140060d1f  jnb     short loc_140060D47
0x140060d21  movzx   eax, cx
0x140060d24  movzx   edx, word ptr [r9+rax*2]
0x140060d29  cmp     dx, 5Ch ; '\'
0x140060d2d  jz      loc_140060DD5
0x140060d33  cmp     dx, 3Ah ; ':'
0x140060d37  jz      loc_140060DD5
0x140060d3d  add     cx, r13w
0x140060d41  cmp     cx, r10w
0x140060d45  jb      short loc_140060D21
0x140060d47  test    r8b, 3
0x140060d4b  jnz     loc_140061862
  ... truncated ...
```
