# RefsReadUsnJournal

- ea: `0x1c01cfef4`
- end: `0x1c01d107d`
- name: `RefsReadUsnJournal`
- size: `4489`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c015c128`
- `0x1c01cf588`

## callees

- `0x1c00049a0`
- `0x1c0004a30`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c005d258`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006acc0`
- `0x1c00aa3ac`
- `0x1c016154c`
- `0x1c01cfef4`
- `0x1c01d1084`
- `0x1c01d255c`
- `0x1c01d2c48`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c01d00cf`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c01d00cf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01d03d9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01d08d1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01d0d92`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01d0db1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01d104a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01d1068`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01d03d9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01d08d1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01d0d92`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01d0db1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01d104a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01d1068`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c01d0e2e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c01d0e2e`
- `ntoskrnl!CcMapData` at `0x1c01d07e6`
- `ntoskrnl!CcMapData` at `0x1c01d07e6`
- `ntoskrnl!ExRaiseStatus` at `0x1c01d0f29`
- `ntoskrnl!ExRaiseStatus` at `0x1c01d0f29`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c01d00eb`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c01d08be`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c01d0d7f`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c01d1037`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c01d00eb`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c01d08be`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c01d0d7f`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c01d1037`
- `ntoskrnl!CcUnpinData` at `0x1c01d0884`
- `ntoskrnl!CcUnpinData` at `0x1c01d0b4e`
- `ntoskrnl!CcUnpinData` at `0x1c01d0d48`
- `ntoskrnl!CcUnpinData` at `0x1c01d0ffb`
- `ntoskrnl!CcUnpinData` at `0x1c01d0884`
- `ntoskrnl!CcUnpinData` at `0x1c01d0b4e`
- `ntoskrnl!CcUnpinData` at `0x1c01d0d48`
- `ntoskrnl!CcUnpinData` at `0x1c01d0ffb`
- `ntoskrnl!ProbeForWrite` at `0x1c01d006a`
- `ntoskrnl!ProbeForWrite` at `0x1c01d006a`
- `ntoskrnl!ProbeForRead` at `0x1c01d0044`
- `ntoskrnl!ProbeForRead` at `0x1c01d0044`

## pseudocode

```c
__int64 __fastcall RefsReadUsnJournal(__int64 a1, __int64 a2, char a3)
{
  int v3; // r14d
  __int64 v5; // r13
  __int64 v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 *v12; // r9
  int v13; // edx
  __int64 v14; // rbx
  int v15; // ecx
  __int64 v16; // r12
  unsigned int v17; // eax
  size_t v18; // r8
  unsigned int v19; // eax
  unsigned int v20; // r15d
  __int64 v21; // rdx
  bool v22; // sf
  __int64 v23; // r8
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rbx
  __int64 v27; // rbx
  char *v28; // rcx
  __int64 v29; // rbx
  unsigned int *v30; // rcx
  __int64 v31; // r13
  int v32; // eax
  unsigned int v33; // r14d
  _DWORD *v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rax
  char *v40; // rcx
  __int64 v41; // rbx
  __int64 v42; // rdx
  unsigned int v43; // ebx
  bool v45; // [rsp+41h] [rbp-117h]
  int Status; // [rsp+44h] [rbp-114h]
  char v47; // [rsp+48h] [rbp-110h]
  char v48; // [rsp+49h] [rbp-10Fh] BYREF
  char v49; // [rsp+4Ah] [rbp-10Eh]
  __int64 v50; // [rsp+50h] [rbp-108h] BYREF
  unsigned int v51; // [rsp+58h] [rbp-100h]
  PVOID Src; // [rsp+60h] [rbp-F8h] BYREF
  char v53; // [rsp+68h] [rbp-F0h]
  void *v54; // [rsp+70h] [rbp-E8h]
  __int64 v55; // [rsp+78h] [rbp-E0h] BYREF
  unsigned int v56; // [rsp+80h] [rbp-D8h]
  int v57; // [rsp+84h] [rbp-D4h]
  __int64 v58; // [rsp+88h] [rbp-D0h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+90h] [rbp-C8h] BYREF
  __int64 v60; // [rsp+98h] [rbp-C0h]
  __int64 *v61; // [rsp+A0h] [rbp-B8h]
  union _LARGE_INTEGER v62; // [rsp+A8h] [rbp-B0h]
  __int128 v63; // [rsp+B0h] [rbp-A8h]
  PVOID Bcb; // [rsp+C0h] [rbp-98h] BYREF
  __int64 v65; // [rsp+C8h] [rbp-90h]
  __int64 v66; // [rsp+D0h] [rbp-88h]
  __int64 v67; // [rsp+D8h] [rbp-80h] BYREF
  __int64 v68; // [rsp+E0h] [rbp-78h] BYREF
  __int128 v69; // [rsp+E8h] [rbp-70h] BYREF
  __int128 v70; // [rsp+F8h] [rbp-60h]
  __int128 v71; // [rsp+108h] [rbp-50h] BYREF

  v49 = a3;
  v5 = a2;
  v65 = a2;
  v6 = a1;
  v66 = a1;
  Status = 0;
  Src = 0;
  v62.QuadPart = 0;
  v63 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v45 = 0;
  v47 = 0;
  v50 = 0;
  v67 = 0;
  v55 = 0;
  v7 = *(_QWORD *)(a2 + 184);
  RefsDecodeFileObject(
    a1,
    *(_QWORD *)(v7 + 48),
    (unsigned int)&v50,
    (unsigned int)&v68,
    (__int64)&v67,
    (__int64)&v55,
    1);
  if ( !v55 || (*(_WORD *)(v55 + 88) & 0x200) == 0 )
  {
    v43 = -1073741790;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741790);
    RefsExtendedCompleteRequestInternal(v6, v5, 3221225506LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225506LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741790);
    return v43;
  }
  LOBYTE(v3) = 1;
  LODWORD(v55) = v3;
  if ( a3 )
  {
    LOBYTE(v3) = (*(_BYTE *)(v6 + 8) & 1) != 0;
    LODWORD(v55) = v3;
  }
  Bcb = 0;
  v12 = (__int64 *)RefsMapUserBuffer(v5, v8, v9, v10);
  v61 = v12;
  v13 = *(_DWORD *)(v6 + 8);
  v57 = (v13 & 1) == 0;
  *(_DWORD *)(v6 + 8) = v13 | 1;
  if ( *(_BYTE *)(v5 + 64) )
  {
    if ( a3 )
    {
      ProbeForRead(*(volatile void **)(v7 + 32), *(unsigned int *)(v7 + 16), 4u);
      v12 = v61;
    }
    if ( !*(_QWORD *)(v5 + 8) )
      ProbeForWrite(v12, *(unsigned int *)(v7 + 8), 4u);
  }
  else if ( *(_QWORD *)(v7 + 32) != ((*(_QWORD *)(v7 + 32) + 3LL) & 0xFFFFFFFFFFFFFFFCuLL)
         || !*(_QWORD *)(v5 + 8) && v12 != (__int64 *)(((unsigned __int64)v12 + 3) & 0xFFFFFFFFFFFFFFFCuLL) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_186;
    goto LABEL_185;
  }
  if ( a3 )
  {
    LOBYTE(v11) = 1;
    v47 = RefsAcquireSharedVcb(v6, v50, v11, v12);
  }
  v14 = v50;
  ExAcquireResourceSharedLite((PERESOURCE)(v50 + 1176), 1u);
  RtlCaptureStackBackTrace(0, 9u, (PVOID *)(v14 + 1280), 0);
  *(_DWORD *)(v6 + 4) |= 0x2000u;
  v45 = 1;
  v15 = *(_DWORD *)(v14 + 4);
  if ( (v15 & 0x100000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221226167LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_22;
    goto LABEL_21;
  }
  v16 = *(_QWORD *)(v50 + 40);
  if ( !v16 || (v15 & 0x80000) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221226168LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_179;
    goto LABEL_178;
  }
  v17 = *(_DWORD *)(v7 + 16);
  if ( v17 < 0x28 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225704LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741592);
    Status = -1073741592;
    goto LABEL_187;
  }
  v18 = 48;
  if ( v17 != 48 )
  {
    DWORD2(v71) = 131074;
    v18 = 40;
  }
  memmove(&v69, *(const void **)(v7 + 32), v18);
  if ( (_QWORD)v71 != *(_QWORD *)(v50 + 864) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_186;
    goto LABEL_185;
  }
  if ( WORD4(v71) > WORD5(v71) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_186;
    goto LABEL_185;
  }
  if ( WORD4(v71) > 3u || WORD5(v71) < 2u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_186;
    goto LABEL_185;
  }
  v19 = *(_DWORD *)(v7 + 8);
  if ( v19 < 8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225507LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741789);
    Status = -1073741789;
    goto LABEL_187;
  }
  v20 = v19 - 8;
  v56 = v19 - 8;
  v54 = v61 + 1;
  v51 = 8;
  if ( v47 )
  {
    ExReleaseResourceLite((PERESOURCE)(v50 + 1424));
    v47 = 0;
  }
  if ( (*(_DWORD *)(v16 + 304) & 0x10000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221226094LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741202);
    Status = -1073741202;
    goto LABEL_187;
  }
  v21 = v69;
  v22 = (__int64)v69 < 0;
  if ( !(_QWORD)v69 )
  {
    v21 = *(_QWORD *)(v50 + 880);
    *(_QWORD *)&v69 = v21;
    v22 = v21 < 0;
  }
  if ( v22 || *((_QWORD *)&v70 + 1) > 0x7FFFFFFFFFFFFFFFuLL || v21 + *((_QWORD *)&v70 + 1) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_186;
    goto LABEL_185;
  }
  v23 = v51;
  while ( 1 )
  {
    if ( v21 < *(_QWORD *)(*(_QWORD *)(v16 + 128) + 888LL) )
      goto LABEL_109;
    if ( (*(_DWORD *)(v50 + 4) & 0x2000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225634LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741662);
      Status = -1073741662;
      goto LABEL_187;
    }
    if ( !*((_QWORD *)&v70 + 1) )
      goto LABEL_160;
    v3 = (unsigned __int8)v3;
    if ( v5 != *(_QWORD *)(v6 + 72) )
      v3 = 0;
    LODWORD(v55) = v3;
    v53 = v3;
    v24 = RefsWaitForUsn(v6, v5, (__int64)&v69);
    Status = v24;
    if ( !(_BYTE)v3 )
      break;
    if ( v24 < 0 )
      goto LABEL_187;
    v25 = *(_QWORD *)(v16 + 128);
    if ( v16 != *(_QWORD *)(v25 + 40) )
    {
      if ( (*(_DWORD *)(v25 + 4) & 0x100000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            29,
            WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids,
            3221226167LL);
        }
        if ( !RefsStatusDebugEnabled )
          goto LABEL_22;
LABEL_21:
        RefsStatusDebug(-1073741129);
LABEL_22:
        Status = -1073741129;
        goto LABEL_187;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221226168LL);
      }
      if ( !RefsStatusDebugEnabled )
      {
LABEL_179:
        Status = -1073741128;
        goto LABEL_187;
      }
LABEL_178:
      RefsStatusDebug(-1073741128);
      goto LABEL_179;
    }
    v21 = v69;
LABEL_109:
    if ( v21 < *(_QWORD *)(v50 + 880) )
    {
      *(_QWORD *)&v69 = *(_QWORD *)(v50 + 880);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221226191LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741105);
      Status = -1073741105;
      v21 = v69;
      LODWORD(v23) = v51;
      goto LABEL_160;
    }
LABEL_117:
    if ( !v20 )
    {
      LODWORD(v23) = v51;
LABEL_160:
      *(_QWORD *)(v5 + 56) = (unsigned int)v23;
      *v61 = v21;
      goto LABEL_187;
    }
    v26 = *(_QWORD *)(*(_QWORD *)(v16 + 128) + 888LL);
    if ( v21 < v26 )
    {
      FileOffset.QuadPart = 0;
      v48 = 0;
      v58 = 0;
      v27 = v26 - v21;
      v60 = v27;
      if ( v27 > 0x40000 - ((unsigned int)v69 & 0x3FFFF) )
        v27 = 0x40000 - ((unsigned int)v69 & 0x3FFFF);
      v60 = v27;
      FileOffset.QuadPart = RefsFileOffsetFromUsn(v16, v21, v23);
      CcMapData(*(PFILE_OBJECT *)(v16 + 224), &FileOffset, v27, 1u, &Bcb, &Src);
      v62 = FileOffset;
      LODWORD(v63) = v27;
      LODWORD(v28) = (_DWORD)Src;
      *((_QWORD *)&v63 + 1) = Src;
      LODWORD(v21) = v69;
      while ( 1 )
      {
        if ( !(unsigned __int8)RefsValidateUsnPage(
                                 v6,
                                 (unsigned int)v28 & 0xFFFFF000,
                                 (unsigned int)v21 & 0xFFFFF000,
                                 (unsigned int)&v69,
                                 *(_QWORD *)(*(_QWORD *)(v16 + 128) + 888LL),
                                 (__int64)&v48,
                                 (__int64)&v58) )
        {
          if ( Bcb )
          {
            CcUnpinData(Bcb);
            Bcb = 0;
          }
          *(_DWORD *)(v6 + 4) &= 0xFFFFCFFF;
          v29 = v50;
          RtlCaptureStackBackTrace(0, 9u, (PVOID *)(v50 + 1352), 0);
          ExReleaseResourceLite((PERESOURCE)(v29 + 1176));
          v45 = 0;
          Status = RefsRepairUsnJournal(v6, v5, v69, 0, (__int64)&v71, v49, (__int64)&v48, (__int64)&v58);
          if ( Status >= 0 )
          {
            v45 = 1;
            v21 = v69;
            goto LABEL_117;
          }
          goto LABEL_187;
        }
        if ( !v48 )
          break;
        v30 = (unsigned int *)Src;
        v21 = v69;
        v23 = v58;
        while ( v21 < v23 )
        {
          v31 = *v30;
          v32 = v30[14];
          if ( (v32 & DWORD2(v69)) != 0 && (!HIDWORD(v69) || v32 < 0) && *((_WORD *)v30 + 2) == 3 )
          {
            v33 = v31 - 16;
            if ( WORD5(v71) >= 3u )
              v33 = *v30;
            if ( v33 > v20 )
            {
              v20 = 0;
              v56 = 0;
LABEL_154:
              if ( Bcb )
              {
                CcUnpinData(Bcb);
                Bcb = 0;
                v21 = v69;
              }
              v5 = v65;
              goto LABEL_117;
            }
            if ( WORD5(v71) >= 3u )
            {
              memmove(v54, v30, v33);
            }
            else
            {
              v34 = v54;
              *(_DWORD *)v54 = v33;
              v34[1] = 2;
              v35 = RefsPackFileId((char *)Src + 8, v21, v23, 0);
              *((_QWORD *)v54 + 1) = v35;
              v39 = RefsPackFileId((char *)Src + 24, v36, v37, v38);
              v40 = (char *)v54;
              *((_QWORD *)v54 + 2) = v39;
              memmove(v40 + 24, (char *)Src + 40, (unsigned int)(v31 - 40));
              *((_WORD *)v54 + 29) = 60;
            }
            v20 -= v33;
            v56 = v20;
            v51 += v33;
            v54 = (char *)v54 + v33;
            v30 = (unsigned int *)Src;
            v21 = v69;
            v23 = v58;
          }
          v21 += v31;
          *(_QWORD *)&v69 = v21;
          v30 = (unsigned int *)((char *)v30 + v31);
          Src = v30;
          v27 -= v31;
          v60 = v27;
        }
        if ( v20 )
        {
          v23 = -(int)v23 & 0xFFF;
          if ( (unsigned int)v23 > v27 )
            v23 = (unsigned int)v27;
          v28 = (char *)v30 + (unsigned int)v23;
          Src = v28;
          v21 += (unsigned int)v23;
          *(_QWORD *)&v69 = v21;
          v27 -= (unsigned int)v23;
          v60 = v27;
          v5 = v65;
          if ( v27 )
            continue;
        }
        goto LABEL_154;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids, 3221225485LL);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_186;
LABEL_185:
      RefsStatusDebug(-1073741811);
LABEL_186:
      Status = -1073741811;
      goto LABEL_187;
    }
    v23 = v51;
    LOBYTE(v3) = v55;
    if ( v51 != 8 )
      goto LABEL_160;
  }
  if ( v24 == 259 || v24 == -1073741536 || v24 == -1073741129 )
    v45 = v5 != *(_QWORD *)(v6 + 72);
LABEL_187:
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  if ( v45 )
  {
    *(_DWORD *)(v6 + 4) &= 0xFFFFCFFF;
    v41 = v50;
    RtlCaptureStackBackTrace(0, 9u, (PVOID *)(v50 + 1352), 0);
    ExReleaseResourceLite((PERESOURCE)(v41 + 1176));
  }
  if ( v47 )
    ExReleaseResourceLite((PERESOURCE)(v50 + 1424));
  *(_DWORD *)(v6 + 8) &= ~v57;
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  v42 = 0;
  v43 = Status;
  if ( Status != 259 )
    v42 = v5;
  if ( v5 != *(_QWORD *)(v6 + 72) )
    v6 = 0;
  RefsExtendedCompleteRequestInternal(v6, v42, (unsigned int)Status);
  return v43;
}

```

## disassembly

```asm
0x1c01cfef4  mov     r11, rsp
0x1c01cfef7  push    rbx
0x1c01cfef8  push    rsi
0x1c01cfef9  push    rdi
0x1c01cfefa  push    r12
0x1c01cfefc  push    r13
0x1c01cfefe  push    r14
0x1c01cff00  push    r15
0x1c01cff02  sub     rsp, 120h
0x1c01cff09  mov     rax, cs:__security_cookie
0x1c01cff10  xor     rax, rsp
0x1c01cff13  mov     [rsp+158h+var_40], rax
0x1c01cff1b  mov     bl, r8b
0x1c01cff1e  mov     [rsp+158h+var_10E], bl
0x1c01cff22  mov     r13, rdx
0x1c01cff25  mov     [rsp+158h+var_90], rdx
0x1c01cff2d  mov     rdi, rcx
0x1c01cff30  mov     [rsp+158h+var_88], rcx
0x1c01cff38  xor     r15d, r15d
0x1c01cff3b  mov     [rsp+158h+Status], r15d
0x1c01cff40  mov     [rsp+158h+Src], r15
0x1c01cff45  mov     [r11-0B0h], r15
0x1c01cff4c  xorps   xmm0, xmm0
0x1c01cff4f  movdqu  [rsp+158h+var_A8], xmm0
0x1c01cff58  xorps   xmm1, xmm1
0x1c01cff5b  movups  xmmword ptr [r11-70h], xmm1
0x1c01cff60  movups  xmmword ptr [r11-60h], xmm1
0x1c01cff65  movups  xmmword ptr [r11-50h], xmm1
0x1c01cff6a  mov     [rsp+158h+var_117], r15b
0x1c01cff6f  mov     [rsp+158h+var_118], r15b
0x1c01cff74  mov     [rsp+158h+var_110], r15b
0x1c01cff79  mov     [rsp+158h+var_108], r15
0x1c01cff7e  mov     [r11-80h], r15
0x1c01cff82  mov     [rsp+158h+var_E0], r15
0x1c01cff87  mov     rsi, [rdx+0B8h]
0x1c01cff8e  mov     rdx, [rsi+30h]
0x1c01cff92  mov     byte ptr [rsp+158h+var_128], 1
0x1c01cff97  lea     rax, [rsp+158h+var_E0]
0x1c01cff9c  mov     [rsp+158h+Buffer], rax
0x1c01cffa1  lea     rax, [r11-80h]
0x1c01cffa5  mov     [rsp+158h+Bcb], rax
0x1c01cffaa  lea     r9, [r11-78h]
0x1c01cffae  lea     r8, [rsp+158h+var_108]
0x1c01cffb3  call    RefsDecodeFileObject
0x1c01cffb8  mov     rax, [rsp+158h+var_E0]
0x1c01cffbd  test    rax, rax
0x1c01cffc0  jz      loc_1C01D0F36
0x1c01cffc6  movzx   eax, word ptr [rax+58h]
0x1c01cffca  mov     ecx, 200h
0x1c01cffcf  test    cx, ax
0x1c01cffd2  jz      loc_1C01D0F36
0x1c01cffd8  mov     r14b, 1
0x1c01cffdb  mov     dword ptr [rsp+158h+var_E0], r14d
0x1c01cffe0  test    bl, bl
0x1c01cffe2  jz      short loc_1C01CFFF6
0x1c01cffe4  mov     al, [rdi+8]
0x1c01cffe7  and     al, r14b
0x1c01cffea  neg     al
0x1c01cffec  sbb     al, al
0x1c01cffee  and     r14b, al
0x1c01cfff1  mov     dword ptr [rsp+158h+var_E0], r14d
0x1c01cfff6  mov     [rsp+158h+var_98], r15
0x1c01cfffe  mov     rcx, r13
0x1c01d0001  call    RefsMapUserBuffer
0x1c01d0006  mov     r9, rax
0x1c01d0009  mov     [rsp+158h+var_B8], rax
0x1c01d0011  mov     edx, [rdi+8]
0x1c01d0014  mov     ecx, edx
0x1c01d0016  not     ecx
0x1c01d0018  and     ecx, 1
0x1c01d001b  mov     [rsp+158h+var_D4], ecx
0x1c01d0022  or      edx, 1
0x1c01d0025  mov     [rdi+8], edx
0x1c01d0028  mov     [rsp+158h+var_118], 1
0x1c01d002d  cmp     [r13+40h], r15b
0x1c01d0031  jz      short loc_1C01D0078
0x1c01d0033  test    bl, bl
0x1c01d0035  jz      short loc_1C01D0058
0x1c01d0037  mov     edx, [rsi+10h]; Length
0x1c01d003a  mov     r8d, 4; Alignment
0x1c01d0040  mov     rcx, [rsi+20h]; Address
0x1c01d0044  call    cs:__imp_ProbeForRead
0x1c01d004b  nop     dword ptr [rax+rax+00h]
0x1c01d0050  mov     r9, [rsp+158h+var_B8]
0x1c01d0058  cmp     [r13+8], r15
0x1c01d005c  jnz     short loc_1C01D00A4
0x1c01d005e  mov     edx, [rsi+8]; Length
0x1c01d0061  mov     r8d, 4; Alignment
0x1c01d0067  mov     rcx, r9; Address
0x1c01d006a  call    cs:__imp_ProbeForWrite
0x1c01d0071  nop     dword ptr [rax+rax+00h]
0x1c01d0076  jmp     short loc_1C01D00A4
0x1c01d0078  mov     rcx, [rsi+20h]
0x1c01d007c  lea     rax, [rcx+3]
0x1c01d0080  and     rax, 0FFFFFFFFFFFFFFFCh
0x1c01d0084  cmp     rcx, rax
0x1c01d0087  jnz     loc_1C01D0CD5
0x1c01d008d  cmp     [r13+8], r15
0x1c01d0091  jnz     short loc_1C01D00A4
0x1c01d0093  lea     rax, [r9+3]
0x1c01d0097  and     rax, 0FFFFFFFFFFFFFFFCh
0x1c01d009b  cmp     r9, rax
0x1c01d009e  jnz     loc_1C01D0CD5
0x1c01d00a4  mov     [rsp+158h+var_118], r15b
0x1c01d00a9  test    bl, bl
0x1c01d00ab  jz      short loc_1C01D00C1
0x1c01d00ad  mov     r8b, 1
0x1c01d00b0  mov     rdx, [rsp+158h+var_108]
0x1c01d00b5  mov     rcx, rdi
0x1c01d00b8  call    RefsAcquireSharedVcb
0x1c01d00bd  mov     [rsp+158h+var_110], al
0x1c01d00c1  mov     rbx, [rsp+158h+var_108]
0x1c01d00c6  lea     rcx, [rbx+498h]; Resource
0x1c01d00cd  mov     dl, 1; Wait
0x1c01d00cf  call    cs:__imp_ExAcquireResourceSharedLite
0x1c01d00d6  nop     dword ptr [rax+rax+00h]
0x1c01d00db  lea     r8, [rbx+500h]; BackTrace
0x1c01d00e2  xor     r9d, r9d; BackTraceHash
0x1c01d00e5  lea     edx, [r9+9]; FramesToCapture
0x1c01d00e9  xor     ecx, ecx; FramesToSkip
0x1c01d00eb  call    cs:__imp_RtlCaptureStackBackTrace
0x1c01d00f2  nop     dword ptr [rax+rax+00h]
0x1c01d00f7  bts     dword ptr [rdi+4], 0Dh
0x1c01d00fc  mov     [rsp+158h+var_117], 1
0x1c01d0101  mov     ecx, [rbx+4]
0x1c01d0104  bt      ecx, 14h
0x1c01d0108  jnb     short loc_1C01D0177
0x1c01d010a  lea     rax, WPP_GLOBAL_Control
0x1c01d0111  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01d0118  cmp     rcx, rax
0x1c01d011b  jz      short loc_1C01D014B
0x1c01d011d  mov     eax, [rcx+2Ch]
0x1c01d0120  bt      eax, 8
0x1c01d0124  jnb     short loc_1C01D014B
0x1c01d0126  cmp     byte ptr [rcx+29h], 4
0x1c01d012a  jb      short loc_1C01D014B
0x1c01d012c  mov     edx, 13h
0x1c01d0131  mov     esi, 0C00002B7h
0x1c01d0136  mov     r9d, esi
0x1c01d0139  lea     r8, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids
0x1c01d0140  mov     rcx, [rcx+18h]
0x1c01d0144  call    WPP_SF_D
0x1c01d0149  jmp     short loc_1C01D0150
0x1c01d014b  mov     esi, 0C00002B7h
0x1c01d0150  mov     al, cs:RefsStatusDebugEnabled
0x1c01d0156  test    al, al
0x1c01d0158  jz      short loc_1C01D016E
0x1c01d015a  mov     r8d, 3FEh
0x1c01d0160  lea     rdx, aUsnsupC; "UsnSup.c"
0x1c01d0167  mov     ecx, esi; Status
0x1c01d0169  call    RefsStatusDebug
0x1c01d016e  mov     [rsp+158h+Status], esi
0x1c01d0172  jmp     loc_1C01D0D3B
0x1c01d0177  mov     rax, [rsp+158h+var_108]
0x1c01d017c  mov     r12, [rax+28h]
0x1c01d0180  test    r12, r12
0x1c01d0183  jz      loc_1C01D0C6D
0x1c01d0189  bt      ecx, 13h
0x1c01d018d  jnb     loc_1C01D0C6D
0x1c01d0193  mov     eax, [rsi+10h]
0x1c01d0196  cmp     eax, 28h ; '('
0x1c01d0199  jnb     short loc_1C01D0206
0x1c01d019b  lea     rax, WPP_GLOBAL_Control
0x1c01d01a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01d01a9  cmp     rcx, rax
0x1c01d01ac  jz      short loc_1C01D01D8
0x1c01d01ae  mov     eax, [rcx+2Ch]
0x1c01d01b1  bt      eax, 8
0x1c01d01b5  jnb     short loc_1C01D01D8
0x1c01d01b7  cmp     byte ptr [rcx+29h], 4
0x1c01d01bb  jb      short loc_1C01D01D8
0x1c01d01bd  mov     edx, 15h
0x1c01d01c2  mov     r9d, 0C00000E8h
0x1c01d01c8  lea     r8, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids
0x1c01d01cf  mov     rcx, [rcx+18h]
0x1c01d01d3  call    WPP_SF_D
0x1c01d01d8  mov     al, cs:RefsStatusDebugEnabled
0x1c01d01de  test    al, al
0x1c01d01e0  jz      short loc_1C01D01F9
0x1c01d01e2  mov     r8d, 414h
0x1c01d01e8  lea     rdx, aUsnsupC; "UsnSup.c"
0x1c01d01ef  mov     ecx, 0C00000E8h; Status
0x1c01d01f4  call    RefsStatusDebug
0x1c01d01f9  mov     [rsp+158h+Status], 0C00000E8h
0x1c01d0201  jmp     loc_1C01D0D3B
0x1c01d0206  mov     r8d, 30h ; '0'
0x1c01d020c  lea     ebx, [r8-2Eh]
0x1c01d0210  cmp     eax, r8d
0x1c01d0213  jz      short loc_1C01D0224
0x1c01d0215  mov     [rsp+158h+var_48], 20002h
0x1c01d0220  lea     r8d, [rbx+26h]; Size
0x1c01d0224  mov     [rsp+158h+var_118], 1
0x1c01d0229  mov     rdx, [rsi+20h]; Src
0x1c01d022d  lea     rcx, [rsp+158h+var_70]; void *
0x1c01d0235  call    memmove
0x1c01d023a  mov     [rsp+158h+var_118], r15b
0x1c01d023f  mov     rcx, [rsp+158h+var_50]
0x1c01d0247  mov     rax, [rsp+158h+var_108]
0x1c01d024c  cmp     rcx, [rax+360h]
0x1c01d0253  jz      short loc_1C01D02AB
0x1c01d0255  lea     rax, WPP_GLOBAL_Control
0x1c01d025c  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01d0263  cmp     rcx, rax
0x1c01d0266  jz      short loc_1C01D0292
0x1c01d0268  mov     eax, [rcx+2Ch]
0x1c01d026b  bt      eax, 8
0x1c01d026f  jnb     short loc_1C01D0292
0x1c01d0271  cmp     byte ptr [rcx+29h], 4
0x1c01d0275  jb      short loc_1C01D0292
0x1c01d0277  mov     edx, 16h
0x1c01d027c  mov     r9d, 0C000000Dh
0x1c01d0282  lea     r8, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids
0x1c01d0289  mov     rcx, [rcx+18h]
0x1c01d028d  call    WPP_SF_D
0x1c01d0292  mov     al, cs:RefsStatusDebugEnabled
0x1c01d0298  test    al, al
0x1c01d029a  jz      loc_1C01D0D33
0x1c01d02a0  mov     r8d, 439h
0x1c01d02a6  jmp     loc_1C01D0D22
0x1c01d02ab  movzx   eax, word ptr [rsp+158h+var_48+2]
0x1c01d02b3  cmp     word ptr [rsp+158h+var_48], ax
0x1c01d02bb  jbe     short loc_1C01D0313
0x1c01d02bd  lea     rax, WPP_GLOBAL_Control
0x1c01d02c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01d02cb  cmp     rcx, rax
0x1c01d02ce  jz      short loc_1C01D02FA
0x1c01d02d0  mov     eax, [rcx+2Ch]
0x1c01d02d3  bt      eax, 8
0x1c01d02d7  jnb     short loc_1C01D02FA
0x1c01d02d9  cmp     byte ptr [rcx+29h], 4
0x1c01d02dd  jb      short loc_1C01D02FA
0x1c01d02df  mov     edx, 17h
0x1c01d02e4  mov     r9d, 0C000000Dh
0x1c01d02ea  lea     r8, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids
0x1c01d02f1  mov     rcx, [rcx+18h]
0x1c01d02f5  call    WPP_SF_D
0x1c01d02fa  mov     al, cs:RefsStatusDebugEnabled
0x1c01d0300  test    al, al
0x1c01d0302  jz      loc_1C01D0D33
0x1c01d0308  mov     r8d, 443h
0x1c01d030e  jmp     loc_1C01D0D22
0x1c01d0313  cmp     word ptr [rsp+158h+var_48], 3
0x1c01d031c  ja      loc_1C01D0C17
0x1c01d0322  cmp     ax, bx
0x1c01d0325  jb      loc_1C01D0C17
0x1c01d032b  mov     eax, [rsi+8]
0x1c01d032e  cmp     eax, 8
0x1c01d0331  jnb     short loc_1C01D039E
0x1c01d0333  lea     rax, WPP_GLOBAL_Control
0x1c01d033a  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01d0341  cmp     rcx, rax
0x1c01d0344  jz      short loc_1C01D0370
0x1c01d0346  mov     eax, [rcx+2Ch]
0x1c01d0349  bt      eax, 8
0x1c01d034d  jnb     short loc_1C01D0370
0x1c01d034f  cmp     byte ptr [rcx+29h], 4
0x1c01d0353  jb      short loc_1C01D0370
0x1c01d0355  mov     edx, 19h
0x1c01d035a  mov     r9d, 0C0000023h
0x1c01d0360  lea     r8, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids
0x1c01d0367  mov     rcx, [rcx+18h]
0x1c01d036b  call    WPP_SF_D
0x1c01d0370  mov     al, cs:RefsStatusDebugEnabled
0x1c01d0376  test    al, al
0x1c01d0378  jz      short loc_1C01D0391
0x1c01d037a  mov     r8d, 459h
0x1c01d0380  lea     rdx, aUsnsupC; "UsnSup.c"
0x1c01d0387  mov     ecx, 0C0000023h; Status
0x1c01d038c  call    RefsStatusDebug
0x1c01d0391  mov     [rsp+158h+Status], 0C0000023h
0x1c01d0399  jmp     loc_1C01D0D3B
0x1c01d039e  lea     r15d, [rax-8]
0x1c01d03a2  mov     [rsp+158h+var_D8], r15d
0x1c01d03aa  mov     rax, [rsp+158h+var_B8]
0x1c01d03b2  add     rax, 8
0x1c01d03b6  mov     [rsp+158h+var_E8], rax
0x1c01d03bb  mov     [rsp+158h+var_100], 8
0x1c01d03c3  xor     r9d, r9d
0x1c01d03c6  cmp     [rsp+158h+var_110], r9b
0x1c01d03cb  jz      short loc_1C01D03ED
0x1c01d03cd  mov     rcx, [rsp+158h+var_108]
0x1c01d03d2  add     rcx, 590h; Resource
0x1c01d03d9  call    cs:__imp_ExReleaseResourceLite
0x1c01d03e0  nop     dword ptr [rax+rax+00h]
0x1c01d03e5  xor     r9d, r9d
0x1c01d03e8  mov     [rsp+158h+var_110], r9b
0x1c01d03ed  test    dword ptr [r12+130h], 10000h
0x1c01d03f9  jz      short loc_1C01D0469
0x1c01d03fb  lea     rax, WPP_GLOBAL_Control
0x1c01d0402  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01d0409  cmp     rcx, rax
0x1c01d040c  jz      short loc_1C01D0438
0x1c01d040e  mov     eax, [rcx+2Ch]
0x1c01d0411  bt      eax, 8
0x1c01d0415  jnb     short loc_1C01D0438
0x1c01d0417  cmp     byte ptr [rcx+29h], 4
0x1c01d041b  jb      short loc_1C01D0438
0x1c01d041d  mov     edx, 1Ah
0x1c01d0422  mov     r9d, 0C000026Eh
0x1c01d0428  lea     r8, WPP_1a90efa3d1a73f74592aa4b1ffeba664_Traceguids
  ... truncated ...
```
