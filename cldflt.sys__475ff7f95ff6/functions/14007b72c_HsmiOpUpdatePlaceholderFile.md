# HsmiOpUpdatePlaceholderFile

- ea: `0x14007b72c`
- end: `0x14007cb0b`
- name: `HsmiOpUpdatePlaceholderFile`
- size: `5087`
- prototype: `__int64 __fastcall(__int64, __int64, struct _FILE_OBJECT *, unsigned int, __int128 *, int, void *, int, __int64 *, _DWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `40`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x140043ff4`
- `0x14007ab00`

## callees

- `0x140003c50`
- `0x140009ed4`
- `0x14000a048`
- `0x14000abb8`
- `0x14000d388`
- `0x1400152c8`
- `0x140015ec0`
- `0x140017de8`
- `0x14001d890`
- `0x14001da28`
- `0x14001dab0`
- `0x14001db44`
- `0x14001dbd8`
- `0x14001e1c0`
- `0x14001e2a0`
- `0x14001e300`
- `0x140033e90`
- `0x1400356f0`
- `0x1400365e8`
- `0x140043324`
- `0x140052574`
- `0x140056640`
- `0x140058ddc`
- `0x140059738`
- `0x14005ce40`
- `0x1400652b4`
- `0x1400652e4`
- `0x14006793c`
- `0x140067958`
- `0x140067e24`
- `0x14006f28c`
- `0x14007458c`
- `0x140075df0`
- `0x140075e6c`
- `0x140075fd8`
- `0x1400766ac`
- `0x14007b72c`
- `0x14007e468`
- `0x14007ee6c`
- `0x140081d30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007cabc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007cabc`
- `ntoskrnl!ExAllocatePool2` at `0x14007c113`
- `ntoskrnl!ExAllocatePool2` at `0x14007c113`
- `FLTMGR!FltSetInformationFile` at `0x14007bf06`
- `FLTMGR!FltSetInformationFile` at `0x14007c07f`
- `FLTMGR!FltSetInformationFile` at `0x14007bf06`
- `FLTMGR!FltSetInformationFile` at `0x14007c07f`
- `FLTMGR!FltQueryInformationFile` at `0x14007baf0`
- `FLTMGR!FltQueryInformationFile` at `0x14007baf0`
- `FLTMGR!FltFsControlFile` at `0x14007c7f9`
- `FLTMGR!FltFsControlFile` at `0x14007c7f9`
- `FLTMGR!FltReleasePushLockEx` at `0x14007c1be`
- `FLTMGR!FltReleasePushLockEx` at `0x14007c204`
- `FLTMGR!FltReleasePushLockEx` at `0x14007ca9b`
- `FLTMGR!FltReleasePushLockEx` at `0x14007c1be`
- `FLTMGR!FltReleasePushLockEx` at `0x14007c204`
- `FLTMGR!FltReleasePushLockEx` at `0x14007ca9b`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007c199`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007c1da`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007c199`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007c1da`

## pseudocode

```c
__int64 __fastcall HsmiOpUpdatePlaceholderFile(
        __int64 a1,
        __int64 a2,
        struct _FILE_OBJECT *a3,
        unsigned int a4,
        __int128 *a5,
        int a6,
        void *a7,
        int a8,
        __int64 *a9,
        _DWORD *a10,
        _QWORD *a11,
        _QWORD *a12,
        _QWORD *a13,
        _QWORD *a14)
{
  __int64 v15; // r13
  __int64 v16; // rax
  __int64 v17; // r12
  NTSTATUS SyncPolicy; // ebx
  __int64 v19; // rdx
  char StreamSize; // al
  __int64 v21; // r10
  unsigned int v22; // r14d
  char v23; // al
  ULONG *LengthReturned; // r10
  char v25; // al
  __int64 v26; // r10
  int v27; // edx
  char v28; // r8
  int v29; // ecx
  char v30; // di
  char v31; // al
  __int64 v32; // r10
  int v33; // edx
  char v34; // cl
  int v35; // eax
  __int128 *v36; // rax
  __int64 v37; // rax
  __int64 v38; // r8
  unsigned int v39; // edx
  int v40; // r9d
  __int64 v41; // rax
  __int64 v42; // r8
  _QWORD *v43; // rcx
  __int64 v44; // rdx
  char v45; // al
  __int64 v46; // r10
  _QWORD *v47; // r15
  int v48; // edi
  char v49; // al
  __int64 v50; // rax
  __int64 v51; // r8
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // r8
  char v56; // cl
  size_t v57; // rbx
  void *Pool2; // rax
  void *v59; // rdi
  __int64 v60; // rdx
  int v61; // r9d
  _QWORD *v62; // rbx
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // r8
  __int64 v67; // rdx
  unsigned int v68; // edx
  __int64 v69; // rax
  __int64 v70; // rcx
  __int64 v71; // rdx
  __int64 v72; // r13
  __int64 v73; // rcx
  unsigned __int64 v74; // rdi
  unsigned int v75; // eax
  __int64 LastHydrationTime; // rax
  __int64 v77; // rdx
  __int64 v78; // rcx
  int LastDehydrationReason; // eax
  int v80; // r8d
  int v81; // r9d
  __int64 v82; // r10
  int v83; // r11d
  __int64 v84; // r8
  char v85; // al
  __int64 v86; // r10
  int v87; // edx
  __int64 v88; // rax
  __int64 v89; // rdx
  __int64 v90; // r8
  int v91; // edi
  __int64 v92; // rdx
  __int64 v93; // r9
  __int64 v94; // r10
  __int64 v95; // rax
  char v96; // al
  __int64 v97; // r10
  char v98; // r8
  void *v100; // [rsp+50h] [rbp-B0h]
  char v101; // [rsp+58h] [rbp-A8h]
  int v103; // [rsp+60h] [rbp-A0h]
  int v104; // [rsp+60h] [rbp-A0h]
  NTSTATUS v105; // [rsp+60h] [rbp-A0h]
  int v107; // [rsp+70h] [rbp-90h]
  unsigned int v108; // [rsp+70h] [rbp-90h]
  _QWORD *v109; // [rsp+78h] [rbp-88h] BYREF
  PVOID v110; // [rsp+80h] [rbp-80h]
  __int64 v111; // [rsp+88h] [rbp-78h]
  size_t Size; // [rsp+90h] [rbp-70h]
  __int128 *v113; // [rsp+98h] [rbp-68h]
  __int64 v114; // [rsp+A0h] [rbp-60h]
  void *Src; // [rsp+A8h] [rbp-58h]
  _QWORD *v116; // [rsp+B0h] [rbp-50h]
  _QWORD *v117; // [rsp+B8h] [rbp-48h]
  _QWORD *v118; // [rsp+C0h] [rbp-40h]
  _QWORD *v119; // [rsp+C8h] [rbp-38h]
  _DWORD *v120; // [rsp+D0h] [rbp-30h]
  __int128 v121; // [rsp+D8h] [rbp-28h] BYREF
  __int128 InputBuffer; // [rsp+E8h] [rbp-18h] BYREF
  __int128 FileInformation; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v124; // [rsp+108h] [rbp+8h]
  __int64 v125; // [rsp+118h] [rbp+18h]

  Src = a7;
  v15 = a1;
  LODWORD(Size) = a8;
  v120 = a10;
  v118 = a11;
  v117 = a12;
  v119 = a13;
  v116 = a14;
  v16 = *(_QWORD *)(a2 + 16);
  *(_QWORD *)&InputBuffer = a1;
  v17 = *(_QWORD *)(v16 + 32);
  v110 = a9;
  LODWORD(v109) = 0;
  v125 = 0;
  v114 = 0;
  v121 = 0;
  FileInformation = 0;
  v124 = 0;
  if ( a9 && *a9 < 0 )
  {
    SyncPolicy = -1073688821;
    HsmDbgBreakOnStatus(-1073688821);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(a2);
      WPP_SF_qLiid(
        *(_QWORD *)(v21 + 24),
        68,
        (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        a2,
        *(_DWORD *)(a2 + 28),
        StreamSize,
        v17,
        11);
    }
LABEL_7:
    v22 = a6;
    goto LABEL_266;
  }
  LODWORD(v111) = *(_DWORD *)(a2 + 28);
  SyncPolicy = HsmpAcquireSyncOpRundownProtection((PFLT_CONTEXT)a2, 0);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v23 = HsmpGetStreamSize(a2);
      WPP_SF_qLiid(
        *(_QWORD *)(v21 + 24),
        69,
        (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        a2,
        *(_DWORD *)(a2 + 28),
        v23,
        v17,
        SyncPolicy);
    }
    goto LABEL_7;
  }
  v100 = 0;
  v101 = 0;
  v22 = a6;
  if ( (a4 & 0x800) == 0 && ((a4 & 2) != 0 || a6 || (a4 & 1) != 0) )
  {
    HsmpWaitForUserRequestRundownRelease(a2);
    v101 = 1;
  }
  LOBYTE(v19) = 1;
  HsmpAcquireReparseUpdateLock(a2, v19);
  SyncPolicy = HsmpCldGetSyncPolicy(v15, a2, (_DWORD)a3, 5, (__int64)&v109);
  HsmDbgBreakOnStatus(SyncPolicy);
  LengthReturned = 0;
  if ( SyncPolicy < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_261;
    }
    v25 = HsmpGetStreamSize(a2);
    v27 = 70;
    goto LABEL_260;
  }
  v28 = a4;
  v29 = a4 & 0x800000;
  v107 = a4 & 0x800000;
  if ( (a4 & 0x400) != 0 )
  {
    if ( v29 )
    {
      v30 = 11;
      SyncPolicy = -1073688821;
      HsmDbgBreakOnStatus(-1073688821);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_261;
      }
      v31 = HsmpGetStreamSize(a2);
      v33 = 71;
      goto LABEL_29;
    }
  }
  else
  {
    v107 = a4 & 0x800000;
  }
  LODWORD(v111) = v111 & 2;
  if ( ((unsigned __int8)v109 & 0xFu) < 4 )
  {
    if ( (*(_DWORD *)(a2 + 28) & 0x8000) != 0 )
    {
      if ( v29 )
      {
LABEL_40:
        v34 = 1;
        if ( (v28 & 2) != 0 )
          goto LABEL_42;
        goto LABEL_41;
      }
    }
    else if ( (a4 & 0x400) == 0 )
    {
      goto LABEL_40;
    }
  }
  if ( (a4 & 2) != 0 || a6 )
  {
LABEL_256:
    SyncPolicy = -1073688800;
    HsmDbgBreakOnStatus(-1073688800);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_261;
    }
    v25 = HsmpGetStreamSize(a2);
    v27 = 72;
    goto LABEL_260;
  }
  if ( a9 )
  {
    if ( HsmpGetStreamSize(a2) >= *a9 )
      goto LABEL_40;
    goto LABEL_256;
  }
LABEL_41:
  v34 = (char)LengthReturned;
LABEL_42:
  v35 = 1;
  if ( !v34 )
    v35 = a6;
  v22 = v35;
  v36 = &v121;
  if ( !v34 )
    v36 = a5;
  v113 = v36;
  if ( (v22 || (*(_DWORD *)(a2 + 28) & 0x100) == 0)
    && (Src == LengthReturned && *(ULONG **)(a2 + 48) == LengthReturned || v28 < 0) )
  {
    v30 = 11;
    SyncPolicy = -1073688821;
    HsmDbgBreakOnStatus(-1073688821);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_261;
    }
    v31 = HsmpGetStreamSize(a2);
    v33 = 73;
    goto LABEL_29;
  }
  SyncPolicy = FltQueryInformationFile(
                 *(PFLT_INSTANCE *)(v15 + 32),
                 a3,
                 &FileInformation,
                 0x28u,
                 FileBasicInformation,
                 LengthReturned);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_261;
    }
    v25 = HsmpGetStreamSize(a2);
    v27 = 74;
    goto LABEL_260;
  }
  if ( (a4 & 0x8000) == 0 && v22 && (v125 & 0x80000) != 0 )
  {
    SyncPolicy = -1073688821;
    if ( (v125 & 0x180000) != 0x180000 )
      SyncPolicy = -1073688811;
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_261;
    }
    v25 = HsmpGetStreamSize(a2);
    v27 = 75;
LABEL_260:
    WPP_SF_qLiid(
      *(_QWORD *)(v26 + 24),
      v27,
      (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
      a2,
      *(_DWORD *)(a2 + 28),
      v25,
      v17,
      SyncPolicy);
    goto LABEL_261;
  }
  if ( (a4 & 0x1000) != 0 )
  {
LABEL_80:
    if ( v22 )
    {
      v39 = 0;
      if ( a9 )
      {
        v40 = v111;
        while ( 1 )
        {
          v41 = v39;
          v42 = (-(__int64)(v40 != 0) & 0xFFFFF000LL) + 4095;
          v43 = (_QWORD *)&v113[v41] + 1;
          v111 = v41 * 16;
          v109 = v43;
          if ( (v42 & *(_QWORD *)&v113[v41]) != 0 )
            break;
          if ( *v43 && (*v43 & v42) != 0 )
            goto LABEL_93;
          if ( ++v39 >= v22 )
            goto LABEL_87;
        }
        v109 = (_QWORD *)&v113[v41] + 1;
LABEL_93:
        SyncPolicy = -1073688821;
        HsmDbgBreakOnStatus(-1073688821);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v45 = HsmpGetStreamSize(a2);
          WPP_SF_qLiiiid(
            *(_QWORD *)(v46 + 24),
            77,
            (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
            a2,
            *(_DWORD *)(a2 + 28),
            v45,
            v17,
            *(_QWORD *)((char *)v113 + v111),
            *v109,
            11);
        }
        goto LABEL_261;
      }
    }
    goto LABEL_87;
  }
  if ( (a4 & 8) != 0 && !_bittest((const signed __int32 *)(a2 + 28), 0xDu) )
  {
LABEL_75:
    SyncPolicy = -1073688824;
    HsmDbgBreakOnStatus(-1073688824);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v37 = HsmpGetStreamSize(a2);
      WPP_SF_qqLiid(*(_QWORD *)(v38 + 24), 76, v38, v15, a2, *(_DWORD *)(a2 + 28), v37, v17, -1073688824);
    }
    goto LABEL_261;
  }
  if ( v22 )
  {
    if ( !_bittest((const signed __int32 *)(a2 + 28), 0xDu) && (a4 & 1) == 0 )
      goto LABEL_75;
    goto LABEL_80;
  }
LABEL_87:
  SyncPolicy = HsmpPrepareForMgmtOperation(v15, a3, 8);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_261;
    }
    v25 = HsmpGetStreamSize(a2);
    v27 = 78;
    goto LABEL_260;
  }
  v47 = v116;
  if ( v116 && *v116 )
  {
    SyncPolicy = HsmpQueryLastEffectiveUsn(*(PFLT_INSTANCE *)(v15 + 32), a3);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( SyncPolicy < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_261;
      }
      v25 = HsmpGetStreamSize(a2);
      v27 = 79;
      goto LABEL_260;
    }
    if ( *v47 != v114 )
    {
      v30 = 8;
      SyncPolicy = -1073688824;
      HsmDbgBreakOnStatus(-1073688824);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_261;
      }
      v31 = HsmpGetStreamSize(a2);
      v33 = 80;
LABEL_29:
      WPP_SF_qLiid(
        *(_QWORD *)(v32 + 24),
        v33,
        (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        a2,
        *(_DWORD *)(a2 + 28),
        v31,
        v17,
        v30);
      goto LABEL_261;
    }
  }
  v48 = v125 & 0x800;
  v125 = 0;
  v49 = 0;
  LODWORD(v109) = v48;
  FileInformation = 0;
  v124 = 0;
  if ( v117 )
  {
    *((_QWORD *)&v124 + 1) = *v117;
    *(_QWORD *)&v124 = *((_QWORD *)&v124 + 1);
    v49 = 1;
  }
  if ( v118 )
  {
    *(_QWORD *)&FileInformation = *v118;
    v49 = 1;
  }
  if ( v119 )
  {
    *((_QWORD *)&FileInformation + 1) = *v119;
    v49 = 1;
  }
  if ( v120 )
  {
    LODWORD(v125) = *v120;
    goto LABEL_118;
  }
  if ( v49 )
  {
LABEL_118:
    SyncPolicy = FltSetInformationFile(*(PFLT_INSTANCE *)(v15 + 32), a3, &FileInformation, 0x28u, FileBasicInformation);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( SyncPolicy < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_261;
      }
      v50 = HsmpGetStreamSize(a2);
      v52 = 81;
      goto LABEL_123;
    }
  }
  if ( v110 )
  {
    if ( !HsmpGetStreamSize(a2) && (*(_DWORD *)(a2 + 28) & 0x100) == 0 )
    {
      LOBYTE(v53) = 1;
      SyncPolicy = HsmpToggleFileSparseAttribute(v15, a3, v53);
      HsmDbgBreakOnStatus(SyncPolicy);
      if ( SyncPolicy < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqLqiid(
            WPP_GLOBAL_Control->AttachedDevice,
            v54,
            v55,
            v15,
            a2,
            *(_DWORD *)(a2 + 28),
            a3,
            *(_QWORD *)v110,
            v17,
            SyncPolicy);
        }
        goto LABEL_261;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_qqLqii(
          WPP_GLOBAL_Control->AttachedDevice,
          v54,
          v55,
          v15,
          a2,
          *(_DWORD *)(a2 + 28),
          a3,
          *(_QWORD *)v110,
          v17);
      }
    }
    SyncPolicy = FltSetInformationFile(*(PFLT_INSTANCE *)(v15 + 32), a3, v110, 8u, FileEndOfFileInformation);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( SyncPolicy < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_261;
      }
      v50 = HsmpGetStreamSize(a2);
      v52 = 84;
LABEL_123:
      WPP_SF_qqLiid(*(_QWORD *)(v51 + 24), v52, v51, v15, a2, *(_DWORD *)(a2 + 28), v50, v17, SyncPolicy);
      goto LABEL_261;
    }
  }
  v56 = a4;
  if ( (a4 & 4) != 0 )
  {
    ((void (__fastcall *)(_QWORD))qword_140029728)(*(_QWORD *)(a2 + 8));
    v56 = a4;
  }
  if ( Src && (_DWORD)Size )
  {
    v57 = (unsigned int)Size;
    Pool2 = (void *)ExAllocatePool2(258, (unsigned int)Size, 1766224712);
    v59 = Pool2;
    if ( !Pool2 )
    {
      SyncPolicy = -1073741670;
      HsmDbgBreakOnStatus(-1073741670);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqLid(
          WPP_GLOBAL_Control->AttachedDevice,
          85,
          WPP_GLOBAL_Control,
          v15,
          a2,
          *(_DWORD *)(a2 + 28),
          v17,
          -1073741670);
      }
      goto LABEL_262;
    }
    memmove(Pool2, Src, v57);
    FltAcquirePushLockExclusiveEx(a2 + 64, 0);
    v100 = *(void **)(a2 + 48);
    *(_DWORD *)(a2 + 56) = Size;
    *(_QWORD *)(a2 + 48) = v59;
    FltReleasePushLockEx(a2 + 64, 0);
    v48 = (int)v109;
  }
  else if ( v56 < 0 )
  {
    FltAcquirePushLockExclusiveEx(a2 + 64, 0);
    v100 = *(void **)(a2 + 48);
    *(_QWORD *)(a2 + 48) = 0;
    *(_DWORD *)(a2 + 56) = 0;
    FltReleasePushLockEx(a2 + 64, 0);
  }
  LOBYTE(v44) = 1;
  HsmpAcquireBitmapLock(a2, v44);
  v62 = v110;
  if ( v110 )
  {
    v63 = HsmpGetStreamSize(a2);
    if ( v60 != v63 )
    {
      HsmpUpdateBitmapSizesNoLock(v64, v60);
      **(_QWORD **)(a2 + 160) = *v62;
    }
  }
  if ( (a4 & 1) != 0 )
  {
    LOBYTE(v60) = 1;
    HsmpSetInSyncNoLock(a2, v60);
  }
  if ( (a4 & 0x100) != 0 )
    HsmpSetInSyncNoLock(a2, 0);
  if ( (a4 & 0x400) != 0 )
    *(_DWORD *)(a2 + 28) |= 0x8000u;
  if ( v107 )
    *(_DWORD *)(a2 + 28) &= ~0x8000u;
  if ( v22 )
  {
    if ( (a4 & 0x40000) == 0 )
    {
      SyncPolicy = HsmpNotifyDataChange(a2);
      HsmDbgBreakOnStatus(SyncPolicy);
      if ( SyncPolicy < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v65 = HsmpGetStreamSize(a2);
          v67 = 86;
          goto LABEL_218;
        }
        goto LABEL_219;
      }
    }
    if ( v48 )
    {
      SyncPolicy = HsmpSetCompressionNoLock(v15, (unsigned __int64)a3 & -(__int64)((a3->Flags & 2) != 0), 0, v17);
      HsmDbgBreakOnStatus(SyncPolicy);
      if ( SyncPolicy < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqqd(
            WPP_GLOBAL_Control->AttachedDevice,
            87,
            WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
            v15,
            v17,
            a2,
            SyncPolicy);
        }
        goto LABEL_219;
      }
      *(_DWORD *)(a2 + 28) |= 0x10000u;
    }
  }
  v68 = 0;
  v108 = 0;
  if ( !v22 )
    goto LABEL_188;
  do
  {
    v69 = v68;
    v70 = (*(_DWORD *)(a2 + 28) & 2) == 0 ? 0x1000 : 0;
    v71 = *(_QWORD *)&v113[v68];
    v72 = -v70 & (v71 + v70 - 1);
    v73 = *((_QWORD *)&v113[v69] + 1);
    if ( (unsigned __int64)(v73 + 1) <= 1 )
      v74 = 0x7FFFFFFFFFFFFFFFLL;
    else
      v74 = -(__int64)((*(_DWORD *)(a2 + 28) & 2) == 0) & 0xFFFFFFFFFFFFF000uLL & (v73 + v71);
    if ( v72 < 0 )
    {
      SyncPolicy = -1073688821;
      HsmDbgBreakOnStatus(-1073688821);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v88 = HsmpGetStreamSize(a2);
        WPP_SF_qLiiid(*(_QWORD *)(v89 + 24), v89, v90, a2, *(_DWORD *)(a2 + 28), v88, v17, v72);
      }
      goto LABEL_219;
    }
    SyncPolicy = HsmiMarkFileRangeNoLock(a2, 16964, v72, v74, 0);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( SyncPolicy < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_219;
      }
      v85 = HsmpGetStreamSize(a2);
      v87 = 89;
LABEL_207:
      WPP_SF_qLiiiid(
        *(_QWORD *)(v86 + 24),
        v87,
        (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        a2,
        *(_DWORD *)(a2 + 28),
        v85,
        v17,
        v72,
        v74,
        SyncPolicy);
      goto LABEL_219;
    }
    SyncPolicy = HsmiMarkFileRangeNoLock(a2, 16982, v72, v74, 0);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( SyncPolicy < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_219;
      }
      v85 = HsmpGetStreamSize(a2);
      v87 = 90;
      goto LABEL_207;
    }
    SyncPolicy = HsmpMarkModificationBitmapNoLock(a2, v72, v74, 0);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( SyncPolicy < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_219;
      }
      v85 = HsmpGetStreamSize(a2);
      v87 = 91;
      goto LABEL_207;
    }
    v68 = v108 + 1;
    v108 = v68;
  }
  while ( v68 < v22 );
  v15 = InputBuffer;
LABEL_188:
  *(_DWORD *)(a2 + 28) |= 1u;
  if ( v22 )
  {
    *(_QWORD *)(*(_QWORD *)(a2 + 160) + 8LL) = MEMORY[0xFFFFF78000000014];
    v75 = HsmpComputeDehydrationReason(a4);
    HsmpSetLastDehydrationReasonNoLock(a2, v75);
    HsmpGetStreamSize(a2);
    LastHydrationTime = HsmpGetLastHydrationTime();
    LastDehydrationReason = HsmpGetLastDehydrationReason(v78, v77, LastHydrationTime);
    TlmWriteDehydrationEvent(v83, LastDehydrationReason, v80, v81, v17, v82);
  }
  LOBYTE(v61) = 1;
  SyncPolicy = HsmpRpCommitNoLock(v15, a2, (_DWORD)a3, v61, 0);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v65 = HsmpGetStreamSize(a2);
      v67 = 92;
      goto LABEL_218;
    }
    goto LABEL_219;
  }
  if ( v110 )
  {
    SyncPolicy = HsmpSetFileVDL(*(_QWORD *)(v15 + 32), a3, *(_QWORD *)v110);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( SyncPolicy < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v65 = HsmpGetStreamSize(a2);
        v67 = 93;
LABEL_218:
        WPP_SF_qqLiid(*(_QWORD *)(v66 + 24), v67, v66, v15, a2, *(_DWORD *)(a2 + 28), v65, v17, SyncPolicy);
      }
LABEL_219:
      HsmpReleaseBitmapLock(a2);
      goto LABEL_261;
    }
  }
  v91 = 0;
  if ( !v22 )
    goto LABEL_243;
  while ( 2 )
  {
    InputBuffer = 0;
    if ( v91 )
    {
LABEL_224:
      v92 = ~(*(unsigned int *)(v15 + 88) - 1LL);
      v93 = *(_QWORD *)&v113[v91];
      v94 = *((_QWORD *)&v113[v91] + 1);
      v84 = v92 & (v93 + *(unsigned int *)(v15 + 88) - 1LL);
      *(_QWORD *)&InputBuffer = v84;
      if ( (unsigned __int64)(v94 + 1) <= 1 )
        v95 = 0x7FFFFFFFFFFFFFFFLL;
      else
        v95 = v92 & (v94 + v93);
      *((_QWORD *)&InputBuffer + 1) = v95;
      if ( v95 > v84 )
      {
        v105 = FltFsControlFile(*(PFLT_INSTANCE *)(v15 + 32), a3, 0x980C8u, &InputBuffer, 0x10u, 0, 0, 0);
        HsmDbgBreakOnStatus(v105);
        v84 = (unsigned int)v105;
        if ( v105 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qiqiid(
              WPP_GLOBAL_Control->AttachedDevice,
              96,
              WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
              v15,
              v17,
              a2,
              InputBuffer,
              *((_QWORD *)&InputBuffer + 1),
              v105);
          }
          goto LABEL_243;
        }
      }
      if ( ++v91 >= v22 )
        goto LABEL_243;
      continue;
    }
    break;
  }
  LOBYTE(v84) = 1;
  v103 = HsmpToggleFileSparseAttribute(v15, a3, v84);
  HsmDbgBreakOnStatus(v103);
  if ( v103 >= 0 )
  {
    v104 = HsmpPrepareForMgmtOperation(v15, a3, 1);
    HsmDbgBreakOnStatus(v104);
    if ( v104 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          95,
          WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
          v15,
          v17,
          a2,
          v104);
      }
      goto LABEL_243;
    }
    goto LABEL_224;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v96 = HsmpGetStreamSize(a2);
    WPP_SF_qLiid(
      *(_QWORD *)(v97 + 24),
      94,
      (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
      a2,
      *(_DWORD *)(a2 + 28),
      v96,
      v17,
      v98);
  }
LABEL_243:
  HsmpReleaseBitmapLock(a2);
  if ( v22 )
  {
    SyncPolicy = HsmpPrepareForMgmtOperation(v15, a3, 8);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( SyncPolicy < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          97,
          WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
          v15,
          v17,
          a2,
          SyncPolicy);
      }
      goto LABEL_261;
    }
  }
  if ( !v116 )
    goto LABEL_261;
  SyncPolicy = HsmpQueryLastEffectiveUsn(*(PFLT_INSTANCE *)(v15 + 32), a3);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy >= 0 )
  {
    *v116 = v114;
    goto LABEL_261;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v25 = HsmpGetStreamSize(a2);
    v27 = 98;
    goto LABEL_260;
  }
LABEL_261:
  v59 = v100;
LABEL_262:
  if ( v101 )
    HsmpReInitializeUserRequestRundownProtection(a2);
  FltReleasePushLockEx(*(_QWORD *)(a2 + 16) + 24LL, 0);
  HsmpReleaseSyncOpRundownProtection((PFLT_CONTEXT)a2);
  if ( v59 )
    ExFreePoolWithTag(v59, 0x69467348u);
LABEL_266:
  if ( (a4 & 2) != 0 || v22 )
  {
    LOBYTE(v19) = 1;
    HsmpCompletePendedDehydrationRequests(a2, v19, (unsigned int)SyncPolicy);
  }
  return (unsigned int)SyncPolicy;
}

```

## disassembly

```asm
0x14007b72c  mov     [rsp-8+arg_18], rbx
0x14007b731  push    rbp
0x14007b732  push    rsi
0x14007b733  push    rdi
0x14007b734  push    r12
0x14007b736  push    r13
0x14007b738  push    r14
0x14007b73a  push    r15
0x14007b73c  lea     rbp, [rsp-30h]
0x14007b741  sub     rsp, 130h
0x14007b748  mov     rax, cs:__security_cookie
0x14007b74f  xor     rax, rsp
0x14007b752  mov     [rbp+60h+var_40], rax
0x14007b756  mov     rax, [rbp+60h+arg_30]
0x14007b75d  xor     r14d, r14d
0x14007b760  mov     r15, [rbp+60h+arg_40]
0x14007b767  xorps   xmm1, xmm1
0x14007b76a  mov     rdi, [rbp+60h+arg_20]
0x14007b771  xorps   xmm0, xmm0
0x14007b774  mov     [rbp+60h+Src], rax
0x14007b778  mov     rsi, rdx
0x14007b77b  mov     eax, [rbp+60h+arg_38]
0x14007b781  mov     r13, rcx
0x14007b784  mov     dword ptr [rbp+60h+Size], eax
0x14007b787  mov     rax, [rbp+60h+arg_48]
0x14007b78e  mov     [rbp+60h+var_90], rax
0x14007b792  mov     rax, [rbp+60h+arg_50]
0x14007b799  mov     [rbp+60h+var_A0], rax
0x14007b79d  mov     rax, [rbp+60h+arg_58]
0x14007b7a4  mov     [rbp+60h+var_A8], rax
0x14007b7a8  mov     rax, [rbp+60h+arg_60]
0x14007b7af  mov     [rbp+60h+var_98], rax
0x14007b7b3  mov     rax, [rbp+60h+arg_68]
0x14007b7ba  mov     [rbp+60h+var_B0], rax
0x14007b7be  mov     rax, [rdx+10h]
0x14007b7c2  mov     [rsp+160h+var_104], r9d
0x14007b7c7  mov     [rsp+160h+FileObject], r8
0x14007b7cc  mov     qword ptr [rbp+60h+InputBuffer], rcx
0x14007b7d0  mov     r12, [rax+20h]
0x14007b7d4  xor     eax, eax
0x14007b7d6  mov     [rbp+60h+var_E0], r15
0x14007b7da  mov     dword ptr [rsp+160h+var_E8], r14d
0x14007b7df  mov     [rbp+60h+var_48], rax
0x14007b7e3  mov     [rbp+60h+var_C0], r14
0x14007b7e7  movups  [rbp+60h+var_88], xmm0
0x14007b7eb  movups  [rbp+60h+FileInformation], xmm1
0x14007b7ef  movups  [rbp+60h+var_58], xmm1
0x14007b7f3  test    r15, r15
0x14007b7f6  jz      short loc_14007B86D
0x14007b7f8  cmp     [r15], r14
0x14007b7fb  jge     short loc_14007B86D
0x14007b7fd  mov     edi, 0C000CF0Bh
0x14007b802  mov     ecx, edi
0x14007b804  mov     ebx, edi
0x14007b806  call    HsmDbgBreakOnStatus
0x14007b80b  mov     r10, cs:WPP_GLOBAL_Control
0x14007b812  lea     r15, WPP_GLOBAL_Control
0x14007b819  cmp     r10, r15
0x14007b81c  jz      short loc_14007B861
0x14007b81e  mov     eax, [r10+2Ch]
0x14007b822  test    al, 1
0x14007b824  jz      short loc_14007B861
0x14007b826  cmp     byte ptr [r10+29h], 2
0x14007b82b  jb      short loc_14007B861
0x14007b82d  mov     rcx, rsi
0x14007b830  call    HsmpGetStreamSize
0x14007b835  lea     edx, [r14+44h]
0x14007b839  mov     dword ptr [rsp+160h+OutputBufferLength+8], edi
0x14007b83d  mov     rcx, [r10+18h]
0x14007b841  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x14007b848  mov     qword ptr [rsp+160h+OutputBufferLength], r12
0x14007b84d  mov     r9, rsi
0x14007b850  mov     [rsp+160h+LengthReturned], rax
0x14007b855  mov     eax, [rsi+1Ch]
0x14007b858  mov     [rsp+160h+FileInformationClass], eax
0x14007b85c  call    WPP_SF_qLiid
0x14007b861  mov     r14d, [rbp+60h+arg_28]
0x14007b868  jmp     loc_14007CAC8
0x14007b86d  mov     r9d, [rdx+1Ch]
0x14007b871  mov     rcx, rsi; Context
0x14007b874  xor     edx, edx; CallbackData
0x14007b876  mov     dword ptr [rbp+60h+var_D8], r9d
0x14007b87a  call    HsmpAcquireSyncOpRundownProtection
0x14007b87f  mov     ecx, eax
0x14007b881  mov     ebx, eax
0x14007b883  call    HsmDbgBreakOnStatus
0x14007b888  test    ebx, ebx
0x14007b88a  jns     short loc_14007B8C5
0x14007b88c  mov     r10, cs:WPP_GLOBAL_Control
0x14007b893  lea     r15, WPP_GLOBAL_Control
0x14007b89a  cmp     r10, r15
0x14007b89d  jz      short loc_14007B861
0x14007b89f  mov     ecx, [r10+2Ch]
0x14007b8a3  test    cl, 1
0x14007b8a6  jz      short loc_14007B861
0x14007b8a8  cmp     byte ptr [r10+29h], 2
0x14007b8ad  jb      short loc_14007B861
0x14007b8af  mov     rcx, rsi
0x14007b8b2  call    HsmpGetStreamSize
0x14007b8b7  mov     edx, 45h ; 'E'
0x14007b8bc  mov     dword ptr [rsp+160h+OutputBufferLength+8], ebx
0x14007b8c0  jmp     loc_14007B83D
0x14007b8c5  mov     eax, [rsp+160h+var_104]
0x14007b8c9  mov     [rsp+160h+var_110], r14
0x14007b8ce  mov     [rsp+160h+var_108], r14b
0x14007b8d3  mov     r14d, [rbp+60h+arg_28]
0x14007b8da  bt      eax, 0Bh
0x14007b8de  jb      short loc_14007B8FA
0x14007b8e0  test    al, 2
0x14007b8e2  jnz     short loc_14007B8ED
0x14007b8e4  test    r14d, r14d
0x14007b8e7  jnz     short loc_14007B8ED
0x14007b8e9  test    al, 1
0x14007b8eb  jz      short loc_14007B8FA
0x14007b8ed  mov     rcx, rsi
0x14007b8f0  call    HsmpWaitForUserRequestRundownRelease
0x14007b8f5  mov     [rsp+160h+var_108], 1
0x14007b8fa  mov     dl, 1
0x14007b8fc  mov     rcx, rsi
0x14007b8ff  call    HsmpAcquireReparseUpdateLock
0x14007b904  mov     r8, [rsp+160h+FileObject]
0x14007b909  lea     rax, [rsp+160h+var_E8]
0x14007b90e  mov     r9d, 5
0x14007b914  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x14007b919  mov     rdx, rsi
0x14007b91c  mov     rcx, r13
0x14007b91f  call    HsmpCldGetSyncPolicy
0x14007b924  mov     ecx, eax
0x14007b926  mov     ebx, eax
0x14007b928  call    HsmDbgBreakOnStatus
0x14007b92d  xor     r10d, r10d
0x14007b930  test    ebx, ebx
0x14007b932  jns     short loc_14007B974
0x14007b934  mov     r10, cs:WPP_GLOBAL_Control
0x14007b93b  lea     r15, WPP_GLOBAL_Control
0x14007b942  cmp     r10, r15
0x14007b945  jz      loc_14007CA7D
0x14007b94b  mov     eax, [r10+2Ch]
0x14007b94f  test    al, 1
0x14007b951  jz      loc_14007CA7D
0x14007b957  cmp     byte ptr [r10+29h], 2
0x14007b95c  jb      loc_14007CA7D
0x14007b962  mov     rcx, rsi
0x14007b965  call    HsmpGetStreamSize
0x14007b96a  mov     edx, 46h ; 'F'
0x14007b96f  jmp     loc_14007CA55
0x14007b974  mov     r8d, [rsp+160h+var_104]
0x14007b979  mov     edx, r8d
0x14007b97c  and     edx, 400h
0x14007b982  mov     ecx, r8d
0x14007b985  and     ecx, 800000h
0x14007b98b  mov     [rsp+160h+var_100], edx
0x14007b98f  mov     [rsp+160h+var_F0], ecx
0x14007b993  test    edx, edx
0x14007b995  jz      short loc_14007B9ED
0x14007b997  test    ecx, ecx
0x14007b999  jz      short loc_14007B9F1
0x14007b99b  mov     edi, 0C000CF0Bh
0x14007b9a0  mov     ecx, edi
0x14007b9a2  mov     ebx, edi
0x14007b9a4  call    HsmDbgBreakOnStatus
0x14007b9a9  mov     r10, cs:WPP_GLOBAL_Control
0x14007b9b0  lea     r15, WPP_GLOBAL_Control
0x14007b9b7  cmp     r10, r15
0x14007b9ba  jz      loc_14007CA7D
0x14007b9c0  mov     eax, [r10+2Ch]
0x14007b9c4  test    al, 1
0x14007b9c6  jz      loc_14007CA7D
0x14007b9cc  cmp     byte ptr [r10+29h], 2
0x14007b9d1  jb      loc_14007CA7D
0x14007b9d7  mov     rcx, rsi
0x14007b9da  call    HsmpGetStreamSize
0x14007b9df  mov     edx, 47h ; 'G'
0x14007b9e4  mov     dword ptr [rsp+160h+OutputBufferLength+8], edi
0x14007b9e8  jmp     loc_14007CA59
0x14007b9ed  mov     [rsp+160h+var_F0], ecx
0x14007b9f1  mov     eax, dword ptr [rsp+160h+var_E8]
0x14007b9f5  and     dword ptr [rbp+60h+var_D8], 2
0x14007b9f9  and     al, 0Fh
0x14007b9fb  cmp     al, 4
0x14007b9fd  jnb     short loc_14007BA12
0x14007b9ff  test    dword ptr [rsi+1Ch], 8000h
0x14007ba06  jz      short loc_14007BA0E
0x14007ba08  test    ecx, ecx
0x14007ba0a  jz      short loc_14007BA12
0x14007ba0c  jmp     short loc_14007BA3B
0x14007ba0e  test    edx, edx
0x14007ba10  jz      short loc_14007BA3B
0x14007ba12  test    r8b, 2
0x14007ba16  jnz     loc_14007CA1A
0x14007ba1c  test    r14d, r14d
0x14007ba1f  jnz     loc_14007CA1A
0x14007ba25  test    r15, r15
0x14007ba28  jz      short loc_14007BA43
0x14007ba2a  mov     rcx, rsi
0x14007ba2d  call    HsmpGetStreamSize
0x14007ba32  cmp     rax, [r15]
0x14007ba35  jl      loc_14007CA1A
0x14007ba3b  mov     cl, 1
0x14007ba3d  test    r8b, 2
0x14007ba41  jnz     short loc_14007BA46
0x14007ba43  mov     cl, r10b
0x14007ba46  test    cl, cl
0x14007ba48  mov     eax, 1
0x14007ba4d  cmovz   eax, r14d
0x14007ba51  mov     r14d, eax
0x14007ba54  lea     rax, [rbp+60h+var_88]
0x14007ba58  cmovz   rax, rdi
0x14007ba5c  mov     [rbp+60h+var_C8], rax
0x14007ba60  test    r14d, r14d
0x14007ba63  jnz     short loc_14007BA6E
0x14007ba65  test    dword ptr [rsi+1Ch], 100h
0x14007ba6c  jnz     short loc_14007BACD
0x14007ba6e  cmp     [rbp+60h+Src], r10
0x14007ba72  jnz     short loc_14007BA7A
0x14007ba74  cmp     [rsi+30h], r10
0x14007ba78  jz      short loc_14007BA7F
0x14007ba7a  test    r8b, r8b
0x14007ba7d  jns     short loc_14007BACD
0x14007ba7f  mov     edi, 0C000CF0Bh
0x14007ba84  mov     ecx, edi
0x14007ba86  mov     ebx, edi
0x14007ba88  call    HsmDbgBreakOnStatus
0x14007ba8d  mov     r10, cs:WPP_GLOBAL_Control
0x14007ba94  lea     r15, WPP_GLOBAL_Control
0x14007ba9b  cmp     r10, r15
0x14007ba9e  jz      loc_14007CA7D
0x14007baa4  mov     eax, [r10+2Ch]
0x14007baa8  test    al, 1
0x14007baaa  jz      loc_14007CA7D
0x14007bab0  cmp     byte ptr [r10+29h], 2
0x14007bab5  jb      loc_14007CA7D
0x14007babb  mov     rcx, rsi
0x14007babe  call    HsmpGetStreamSize
0x14007bac3  mov     edx, 49h ; 'I'
0x14007bac8  jmp     loc_14007B9E4
0x14007bacd  mov     rdi, [rsp+160h+FileObject]
0x14007bad2  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x14007bad6  mov     rcx, [r13+20h]; Instance
0x14007bada  mov     rdx, rdi; FileObject
0x14007badd  mov     [rsp+160h+LengthReturned], r10; LengthReturned
0x14007bae2  mov     r9d, 28h ; '('; Length
0x14007bae8  mov     [rsp+160h+FileInformationClass], 4; FileInformationClass
0x14007baf0  call    cs:__imp_FltQueryInformationFile
0x14007baf7  nop     dword ptr [rax+rax+00h]
0x14007bafc  mov     ecx, eax
0x14007bafe  mov     ebx, eax
0x14007bb00  call    HsmDbgBreakOnStatus
0x14007bb05  test    ebx, ebx
0x14007bb07  jns     short loc_14007BB49
0x14007bb09  mov     r10, cs:WPP_GLOBAL_Control
0x14007bb10  lea     r15, WPP_GLOBAL_Control
0x14007bb17  cmp     r10, r15
0x14007bb1a  jz      loc_14007CA7D
0x14007bb20  mov     eax, [r10+2Ch]
0x14007bb24  test    al, 1
0x14007bb26  jz      loc_14007CA7D
0x14007bb2c  cmp     byte ptr [r10+29h], 2
0x14007bb31  jb      loc_14007CA7D
0x14007bb37  mov     rcx, rsi
0x14007bb3a  call    HsmpGetStreamSize
0x14007bb3f  mov     edx, 4Ah ; 'J'
0x14007bb44  jmp     loc_14007CA55
0x14007bb49  mov     ecx, [rsp+160h+var_104]
0x14007bb4d  bt      ecx, 0Fh
0x14007bb51  jb      short loc_14007BBBC
0x14007bb53  test    r14d, r14d
0x14007bb56  jz      short loc_14007BBBC
0x14007bb58  mov     eax, dword ptr [rbp+60h+var_48]
0x14007bb5b  bt      eax, 13h
0x14007bb5f  jnb     short loc_14007BBBC
0x14007bb61  mov     edx, 180000h
0x14007bb66  mov     ebx, 0C000CF0Bh
0x14007bb6b  and     eax, edx
0x14007bb6d  cmp     eax, edx
0x14007bb6f  lea     ecx, [rbx+0Ah]
0x14007bb72  cmovnz  ebx, ecx
0x14007bb75  mov     ecx, ebx
0x14007bb77  call    HsmDbgBreakOnStatus
0x14007bb7c  mov     r10, cs:WPP_GLOBAL_Control
0x14007bb83  lea     r15, WPP_GLOBAL_Control
0x14007bb8a  cmp     r10, r15
0x14007bb8d  jz      loc_14007CA7D
0x14007bb93  mov     eax, [r10+2Ch]
0x14007bb97  test    al, 1
0x14007bb99  jz      loc_14007CA7D
0x14007bb9f  cmp     byte ptr [r10+29h], 2
0x14007bba4  jb      loc_14007CA7D
0x14007bbaa  mov     rcx, rsi
0x14007bbad  call    HsmpGetStreamSize
0x14007bbb2  mov     edx, 4Bh ; 'K'
0x14007bbb7  jmp     loc_14007CA55
0x14007bbbc  bt      ecx, 0Ch
0x14007bbc0  jb      loc_14007BC5B
0x14007bbc6  test    cl, 8
0x14007bbc9  jz      short loc_14007BBD2
0x14007bbcb  bt      dword ptr [rsi+1Ch], 0Dh
0x14007bbd0  jnb     short loc_14007BBE7
0x14007bbd2  test    r14d, r14d
0x14007bbd5  jz      loc_14007BCB6
  ... truncated ...
```
