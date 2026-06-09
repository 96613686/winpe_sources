# HsmiOpUpdatePlaceholderFile

- ea: `0x14007b5ec`
- end: `0x14007c9cb`
- name: `HsmiOpUpdatePlaceholderFile`
- size: `5087`
- prototype: ``
- caller_count: `2`
- callee_count: `40`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x140043f04`
- `0x14007a9c0`

## callees

- `0x140003c50`
- `0x140009ed4`
- `0x14000a048`
- `0x14000abb8`
- `0x14000d388`
- `0x140015248`
- `0x140015e40`
- `0x140017d68`
- `0x14001d810`
- `0x14001d9a8`
- `0x14001da30`
- `0x14001dac4`
- `0x14001db58`
- `0x14001e140`
- `0x14001e220`
- `0x14001e280`
- `0x140033e90`
- `0x1400356f0`
- `0x1400365e8`
- `0x140043234`
- `0x140052454`
- `0x140056520`
- `0x140058cbc`
- `0x140059618`
- `0x14005cd20`
- `0x140065194`
- `0x1400651c4`
- `0x14006781c`
- `0x140067838`
- `0x140067d04`
- `0x14006f16c`
- `0x14007446c`
- `0x140075cd0`
- `0x140075d4c`
- `0x140075eb8`
- `0x14007658c`
- `0x14007b5ec`
- `0x14007e2d0`
- `0x14007ecd4`
- `0x140081b90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007c97c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c97c`
- `ntoskrnl!ExAllocatePool2` at `0x14007bfd3`
- `ntoskrnl!ExAllocatePool2` at `0x14007bfd3`
- `FLTMGR!FltSetInformationFile` at `0x14007bdc6`
- `FLTMGR!FltSetInformationFile` at `0x14007bf3f`
- `FLTMGR!FltSetInformationFile` at `0x14007bdc6`
- `FLTMGR!FltSetInformationFile` at `0x14007bf3f`
- `FLTMGR!FltQueryInformationFile` at `0x14007b9b0`
- `FLTMGR!FltQueryInformationFile` at `0x14007b9b0`
- `FLTMGR!FltFsControlFile` at `0x14007c6b9`
- `FLTMGR!FltFsControlFile` at `0x14007c6b9`
- `FLTMGR!FltReleasePushLockEx` at `0x14007c07e`
- `FLTMGR!FltReleasePushLockEx` at `0x14007c0c4`
- `FLTMGR!FltReleasePushLockEx` at `0x14007c95b`
- `FLTMGR!FltReleasePushLockEx` at `0x14007c07e`
- `FLTMGR!FltReleasePushLockEx` at `0x14007c0c4`
- `FLTMGR!FltReleasePushLockEx` at `0x14007c95b`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007c059`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007c09a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007c059`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007c09a`

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
  __int64 v18; // rbx
  char StreamSize; // al
  __int64 v20; // r10
  unsigned int v21; // r14d
  __int64 v22; // rdx
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
  _QWORD *v61; // rbx
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // r8
  __int64 v65; // rdx
  unsigned int v66; // edx
  __int64 v67; // rax
  __int64 v68; // rcx
  __int64 v69; // rdx
  __int64 v70; // r13
  __int64 v71; // rcx
  unsigned __int64 v72; // rdi
  unsigned int v73; // eax
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // r8
  __int64 LastHydrationTime; // rax
  __int64 v78; // rdx
  __int64 v79; // rcx
  int LastDehydrationReason; // eax
  int v81; // r8d
  int v82; // r9d
  __int64 v83; // r10
  int v84; // r11d
  __int64 v85; // r8
  char v86; // al
  __int64 v87; // r10
  int v88; // edx
  __int64 v89; // rax
  __int64 v90; // rdx
  __int64 v91; // r8
  int v92; // edi
  __int64 v93; // r9
  __int64 v94; // rdx
  __int64 v95; // r9
  __int64 v96; // r10
  __int64 v97; // rax
  char v98; // al
  __int64 v99; // r10
  char v100; // r8
  __int64 v101; // r9
  void *v103; // [rsp+50h] [rbp-B0h]
  char v104; // [rsp+58h] [rbp-A8h]
  int v106; // [rsp+60h] [rbp-A0h]
  int v107; // [rsp+60h] [rbp-A0h]
  NTSTATUS v108; // [rsp+60h] [rbp-A0h]
  int v110; // [rsp+70h] [rbp-90h]
  unsigned int v111; // [rsp+70h] [rbp-90h]
  _QWORD *v112; // [rsp+78h] [rbp-88h] BYREF
  PVOID v113; // [rsp+80h] [rbp-80h]
  __int64 v114; // [rsp+88h] [rbp-78h]
  size_t Size; // [rsp+90h] [rbp-70h]
  __int128 *v116; // [rsp+98h] [rbp-68h]
  __int64 v117; // [rsp+A0h] [rbp-60h] BYREF
  void *Src; // [rsp+A8h] [rbp-58h]
  _QWORD *v119; // [rsp+B0h] [rbp-50h]
  _QWORD *v120; // [rsp+B8h] [rbp-48h]
  _QWORD *v121; // [rsp+C0h] [rbp-40h]
  _QWORD *v122; // [rsp+C8h] [rbp-38h]
  _DWORD *v123; // [rsp+D0h] [rbp-30h]
  __int128 v124; // [rsp+D8h] [rbp-28h] BYREF
  __int128 InputBuffer; // [rsp+E8h] [rbp-18h] BYREF
  __int128 FileInformation; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v127; // [rsp+108h] [rbp+8h]
  __int64 v128; // [rsp+118h] [rbp+18h]

  Src = a7;
  v15 = a1;
  LODWORD(Size) = a8;
  v123 = a10;
  v121 = a11;
  v120 = a12;
  v122 = a13;
  v119 = a14;
  v16 = *(_QWORD *)(a2 + 16);
  *(_QWORD *)&InputBuffer = a1;
  v17 = *(_QWORD *)(v16 + 32);
  v113 = a9;
  LODWORD(v112) = 0;
  v128 = 0;
  v117 = 0;
  v124 = 0;
  FileInformation = 0;
  v127 = 0;
  if ( a9 && *a9 < 0 )
  {
    LODWORD(v18) = -1073688821;
    HsmDbgBreakOnStatus(3221278475LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(a2);
      WPP_SF_qLiid(
        *(_QWORD *)(v20 + 24),
        68,
        (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        a2,
        *(_DWORD *)(a2 + 28),
        StreamSize,
        v17,
        11);
    }
LABEL_7:
    v21 = a6;
    goto LABEL_266;
  }
  LODWORD(v114) = *(_DWORD *)(a2 + 28);
  LODWORD(v18) = HsmpAcquireSyncOpRundownProtection((PFLT_CONTEXT)a2, 0);
  HsmDbgBreakOnStatus((unsigned int)v18);
  if ( (int)v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v23 = HsmpGetStreamSize(a2);
      WPP_SF_qLiid(
        *(_QWORD *)(v20 + 24),
        69,
        (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        a2,
        *(_DWORD *)(a2 + 28),
        v23,
        v17,
        v18);
    }
    goto LABEL_7;
  }
  v103 = 0;
  v104 = 0;
  v21 = a6;
  if ( (a4 & 0x800) == 0 && ((a4 & 2) != 0 || a6 || (a4 & 1) != 0) )
  {
    HsmpWaitForUserRequestRundownRelease(a2);
    v104 = 1;
  }
  LOBYTE(v22) = 1;
  HsmpAcquireReparseUpdateLock(a2, v22);
  LODWORD(v18) = HsmpCldGetSyncPolicy(v15, a2, (_DWORD)a3, 5, (__int64)&v112);
  HsmDbgBreakOnStatus((unsigned int)v18);
  LengthReturned = 0;
  if ( (int)v18 < 0 )
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
  v110 = a4 & 0x800000;
  if ( (a4 & 0x400) != 0 )
  {
    if ( v29 )
    {
      v30 = 11;
      LODWORD(v18) = -1073688821;
      HsmDbgBreakOnStatus(3221278475LL);
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
    v110 = a4 & 0x800000;
  }
  LODWORD(v114) = v114 & 2;
  if ( ((unsigned __int8)v112 & 0xFu) < 4 )
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
    LODWORD(v18) = -1073688800;
    HsmDbgBreakOnStatus(3221278496LL);
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
  v21 = v35;
  v36 = &v124;
  if ( !v34 )
    v36 = a5;
  v116 = v36;
  if ( (v21 || (*(_DWORD *)(a2 + 28) & 0x100) == 0)
    && (Src == LengthReturned && *(ULONG **)(a2 + 48) == LengthReturned || v28 < 0) )
  {
    v30 = 11;
    LODWORD(v18) = -1073688821;
    HsmDbgBreakOnStatus(3221278475LL);
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
  LODWORD(v18) = FltQueryInformationFile(
                   *(PFLT_INSTANCE *)(v15 + 32),
                   a3,
                   &FileInformation,
                   0x28u,
                   FileBasicInformation,
                   LengthReturned);
  HsmDbgBreakOnStatus((unsigned int)v18);
  if ( (int)v18 < 0 )
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
  if ( (a4 & 0x8000) == 0 && v21 && (v128 & 0x80000) != 0 )
  {
    LODWORD(v18) = -1073688821;
    if ( (v128 & 0x180000) != 0x180000 )
      LODWORD(v18) = -1073688811;
    HsmDbgBreakOnStatus((unsigned int)v18);
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
      v18);
    goto LABEL_261;
  }
  if ( (a4 & 0x1000) != 0 )
  {
LABEL_80:
    if ( v21 )
    {
      v39 = 0;
      if ( a9 )
      {
        v40 = v114;
        while ( 1 )
        {
          v41 = v39;
          v42 = (-(__int64)(v40 != 0) & 0xFFFFF000LL) + 4095;
          v43 = (_QWORD *)&v116[v41] + 1;
          v114 = v41 * 16;
          v112 = v43;
          if ( (v42 & *(_QWORD *)&v116[v41]) != 0 )
            break;
          if ( *v43 && (*v43 & v42) != 0 )
            goto LABEL_93;
          if ( ++v39 >= v21 )
            goto LABEL_87;
        }
        v112 = (_QWORD *)&v116[v41] + 1;
LABEL_93:
        LODWORD(v18) = -1073688821;
        HsmDbgBreakOnStatus(3221278475LL);
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
            *(_QWORD *)((char *)v116 + v114),
            *v112,
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
    LODWORD(v18) = -1073688824;
    HsmDbgBreakOnStatus(3221278472LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v37 = HsmpGetStreamSize(a2);
      WPP_SF_qqLiid(*(_QWORD *)(v38 + 24), 76, v38, v15, a2, *(_DWORD *)(a2 + 28), v37, v17, -1073688824);
    }
    goto LABEL_261;
  }
  if ( v21 )
  {
    if ( !_bittest((const signed __int32 *)(a2 + 28), 0xDu) && (a4 & 1) == 0 )
      goto LABEL_75;
    goto LABEL_80;
  }
LABEL_87:
  v18 = (unsigned int)HsmpPrepareForMgmtOperation(v15, a3, 8, 0);
  HsmDbgBreakOnStatus(v18);
  if ( (int)v18 < 0 )
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
  v47 = v119;
  if ( v119 && *v119 )
  {
    v18 = (unsigned int)HsmpQueryLastEffectiveUsn(*(PFLT_INSTANCE *)(v15 + 32), a3, &v117);
    HsmDbgBreakOnStatus(v18);
    if ( (int)v18 < 0 )
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
    if ( *v47 != v117 )
    {
      v30 = 8;
      LODWORD(v18) = -1073688824;
      HsmDbgBreakOnStatus(3221278472LL);
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
  v48 = v128 & 0x800;
  v128 = 0;
  v49 = 0;
  LODWORD(v112) = v48;
  FileInformation = 0;
  v127 = 0;
  if ( v120 )
  {
    *((_QWORD *)&v127 + 1) = *v120;
    *(_QWORD *)&v127 = *((_QWORD *)&v127 + 1);
    v49 = 1;
  }
  if ( v121 )
  {
    *(_QWORD *)&FileInformation = *v121;
    v49 = 1;
  }
  if ( v122 )
  {
    *((_QWORD *)&FileInformation + 1) = *v122;
    v49 = 1;
  }
  if ( v123 )
  {
    LODWORD(v128) = *v123;
    goto LABEL_118;
  }
  if ( v49 )
  {
LABEL_118:
    v18 = (unsigned int)FltSetInformationFile(
                          *(PFLT_INSTANCE *)(v15 + 32),
                          a3,
                          &FileInformation,
                          0x28u,
                          FileBasicInformation);
    HsmDbgBreakOnStatus(v18);
    if ( (int)v18 < 0 )
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
  if ( v113 )
  {
    if ( !HsmpGetStreamSize(a2) && (*(_DWORD *)(a2 + 28) & 0x100) == 0 )
    {
      LOBYTE(v53) = 1;
      v18 = (unsigned int)HsmpToggleFileSparseAttribute(v15, a3, v53);
      HsmDbgBreakOnStatus(v18);
      if ( (int)v18 < 0 )
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
            *(_QWORD *)v113,
            v17,
            v18);
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
          *(_QWORD *)v113,
          v17);
      }
    }
    v18 = (unsigned int)FltSetInformationFile(*(PFLT_INSTANCE *)(v15 + 32), a3, v113, 8u, FileEndOfFileInformation);
    HsmDbgBreakOnStatus(v18);
    if ( (int)v18 < 0 )
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
      WPP_SF_qqLiid(*(_QWORD *)(v51 + 24), v52, v51, v15, a2, *(_DWORD *)(a2 + 28), v50, v17, v18);
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
      LODWORD(v18) = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
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
    v103 = *(void **)(a2 + 48);
    *(_DWORD *)(a2 + 56) = Size;
    *(_QWORD *)(a2 + 48) = v59;
    FltReleasePushLockEx(a2 + 64, 0);
    v48 = (int)v112;
  }
  else if ( v56 < 0 )
  {
    FltAcquirePushLockExclusiveEx(a2 + 64, 0);
    v103 = *(void **)(a2 + 48);
    *(_QWORD *)(a2 + 48) = 0;
    *(_DWORD *)(a2 + 56) = 0;
    FltReleasePushLockEx(a2 + 64, 0);
  }
  LOBYTE(v44) = 1;
  HsmpAcquireBitmapLock(a2, v44);
  v61 = v113;
  if ( v113 )
  {
    v62 = HsmpGetStreamSize(a2);
    if ( v60 != v62 )
    {
      HsmpUpdateBitmapSizesNoLock();
      **(_QWORD **)(a2 + 160) = *v61;
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
  if ( v110 )
    *(_DWORD *)(a2 + 28) &= ~0x8000u;
  if ( v21 )
  {
    if ( (a4 & 0x40000) == 0 )
    {
      v18 = (unsigned int)HsmpNotifyDataChange(a2);
      HsmDbgBreakOnStatus(v18);
      if ( (int)v18 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v63 = HsmpGetStreamSize(a2);
          v65 = 86;
          goto LABEL_218;
        }
        goto LABEL_219;
      }
    }
    if ( v48 )
    {
      LODWORD(v18) = HsmpSetCompressionNoLock(v15, (unsigned __int64)a3 & -(__int64)((a3->Flags & 2) != 0), 0, v17);
      HsmDbgBreakOnStatus((unsigned int)v18);
      if ( (int)v18 < 0 )
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
            v18);
        }
        goto LABEL_219;
      }
      *(_DWORD *)(a2 + 28) |= 0x10000u;
    }
  }
  v66 = 0;
  v111 = 0;
  if ( !v21 )
    goto LABEL_188;
  do
  {
    v67 = v66;
    v68 = (*(_DWORD *)(a2 + 28) & 2) == 0 ? 0x1000 : 0;
    v69 = *(_QWORD *)&v116[v66];
    v70 = -v68 & (v69 + v68 - 1);
    v71 = *((_QWORD *)&v116[v67] + 1);
    if ( (unsigned __int64)(v71 + 1) <= 1 )
      v72 = 0x7FFFFFFFFFFFFFFFLL;
    else
      v72 = -(__int64)((*(_DWORD *)(a2 + 28) & 2) == 0) & 0xFFFFFFFFFFFFF000uLL & (v71 + v69);
    if ( v70 < 0 )
    {
      LODWORD(v18) = -1073688821;
      HsmDbgBreakOnStatus(3221278475LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v89 = HsmpGetStreamSize(a2);
        WPP_SF_qLiiid(*(_QWORD *)(v90 + 24), v90, v91, a2, *(_DWORD *)(a2 + 28), v89, v17, v70);
      }
      goto LABEL_219;
    }
    LODWORD(v18) = HsmiMarkFileRangeNoLock(a2, 16964, v70, v72, 0);
    HsmDbgBreakOnStatus((unsigned int)v18);
    if ( (int)v18 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_219;
      }
      v86 = HsmpGetStreamSize(a2);
      v88 = 89;
LABEL_207:
      WPP_SF_qLiiiid(
        *(_QWORD *)(v87 + 24),
        v88,
        (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        a2,
        *(_DWORD *)(a2 + 28),
        v86,
        v17,
        v70,
        v72,
        v18);
      goto LABEL_219;
    }
    LODWORD(v18) = HsmiMarkFileRangeNoLock(a2, 16982, v70, v72, 0);
    HsmDbgBreakOnStatus((unsigned int)v18);
    if ( (int)v18 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_219;
      }
      v86 = HsmpGetStreamSize(a2);
      v88 = 90;
      goto LABEL_207;
    }
    LODWORD(v18) = HsmpMarkModificationBitmapNoLock(a2, v70, v72, 0);
    HsmDbgBreakOnStatus((unsigned int)v18);
    if ( (int)v18 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_219;
      }
      v86 = HsmpGetStreamSize(a2);
      v88 = 91;
      goto LABEL_207;
    }
    v66 = v111 + 1;
    v111 = v66;
  }
  while ( v66 < v21 );
  v15 = InputBuffer;
LABEL_188:
  *(_DWORD *)(a2 + 28) |= 1u;
  if ( v21 )
  {
    *(_QWORD *)(*(_QWORD *)(a2 + 160) + 8LL) = MEMORY[0xFFFFF78000000014];
    v73 = HsmpComputeDehydrationReason(a4);
    HsmpSetLastDehydrationReasonNoLock(a2, v73);
    HsmpGetStreamSize(a2);
    LastHydrationTime = HsmpGetLastHydrationTime(v75, v74, v76);
    LastDehydrationReason = HsmpGetLastDehydrationReason(v79, v78, LastHydrationTime);
    TlmWriteDehydrationEvent(v84, LastDehydrationReason, v81, v82, v17, v83);
  }
  v18 = (unsigned int)HsmpRpCommitNoLock(v15, a2, a3, 1, 0);
  HsmDbgBreakOnStatus(v18);
  if ( (int)v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v63 = HsmpGetStreamSize(a2);
      v65 = 92;
      goto LABEL_218;
    }
    goto LABEL_219;
  }
  if ( v113 )
  {
    v18 = (unsigned int)HsmpSetFileVDL(*(_QWORD *)(v15 + 32), a3, *(_QWORD *)v113);
    HsmDbgBreakOnStatus(v18);
    if ( (int)v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v63 = HsmpGetStreamSize(a2);
        v65 = 93;
LABEL_218:
        WPP_SF_qqLiid(*(_QWORD *)(v64 + 24), v65, v64, v15, a2, *(_DWORD *)(a2 + 28), v63, v17, v18);
      }
LABEL_219:
      HsmpReleaseBitmapLock(a2);
      goto LABEL_261;
    }
  }
  v92 = 0;
  if ( !v21 )
    goto LABEL_243;
  while ( 2 )
  {
    InputBuffer = 0;
    if ( v92 )
    {
LABEL_224:
      v94 = ~(*(unsigned int *)(v15 + 88) - 1LL);
      v95 = *(_QWORD *)&v116[v92];
      v96 = *((_QWORD *)&v116[v92] + 1);
      v85 = v94 & (v95 + *(unsigned int *)(v15 + 88) - 1LL);
      *(_QWORD *)&InputBuffer = v85;
      if ( (unsigned __int64)(v96 + 1) <= 1 )
        v97 = 0x7FFFFFFFFFFFFFFFLL;
      else
        v97 = v94 & (v96 + v95);
      *((_QWORD *)&InputBuffer + 1) = v97;
      if ( v97 > v85 )
      {
        v108 = FltFsControlFile(*(PFLT_INSTANCE *)(v15 + 32), a3, 0x980C8u, &InputBuffer, 0x10u, 0, 0, 0);
        HsmDbgBreakOnStatus((unsigned int)v108);
        v85 = (unsigned int)v108;
        if ( v108 < 0 )
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
              v108);
          }
          goto LABEL_243;
        }
      }
      if ( ++v92 >= v21 )
        goto LABEL_243;
      continue;
    }
    break;
  }
  LOBYTE(v85) = 1;
  v106 = HsmpToggleFileSparseAttribute(v15, a3, v85);
  HsmDbgBreakOnStatus((unsigned int)v106);
  if ( v106 >= 0 )
  {
    LOBYTE(v93) = 1;
    v107 = HsmpPrepareForMgmtOperation(v15, a3, 1, v93);
    HsmDbgBreakOnStatus((unsigned int)v107);
    if ( v107 < 0 )
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
          v107);
      }
      goto LABEL_243;
    }
    goto LABEL_224;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v98 = HsmpGetStreamSize(a2);
    WPP_SF_qLiid(
      *(_QWORD *)(v99 + 24),
      94,
      (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
      a2,
      *(_DWORD *)(a2 + 28),
      v98,
      v17,
      v100);
  }
LABEL_243:
  HsmpReleaseBitmapLock(a2);
  if ( v21 )
  {
    LOBYTE(v101) = 1;
    LODWORD(v18) = HsmpPrepareForMgmtOperation(v15, a3, 8, v101);
    HsmDbgBreakOnStatus((unsigned int)v18);
    if ( (int)v18 < 0 )
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
          v18);
      }
      goto LABEL_261;
    }
  }
  if ( !v119 )
    goto LABEL_261;
  LODWORD(v18) = HsmpQueryLastEffectiveUsn(*(PFLT_INSTANCE *)(v15 + 32), a3, &v117);
  HsmDbgBreakOnStatus((unsigned int)v18);
  if ( (int)v18 >= 0 )
  {
    *v119 = v117;
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
  v59 = v103;
LABEL_262:
  if ( v104 )
    HsmpReInitializeUserRequestRundownProtection(a2);
  FltReleasePushLockEx(*(_QWORD *)(a2 + 16) + 24LL, 0);
  HsmpReleaseSyncOpRundownProtection((PFLT_CONTEXT)a2);
  if ( v59 )
    ExFreePoolWithTag(v59, 0x69467348u);
LABEL_266:
  if ( (a4 & 2) != 0 || v21 )
    HsmpCompletePendedDehydrationRequests(a2, 1, v18);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14007b5ec  mov     [rsp-8+arg_18], rbx
0x14007b5f1  push    rbp
0x14007b5f2  push    rsi
0x14007b5f3  push    rdi
0x14007b5f4  push    r12
0x14007b5f6  push    r13
0x14007b5f8  push    r14
0x14007b5fa  push    r15
0x14007b5fc  lea     rbp, [rsp-30h]
0x14007b601  sub     rsp, 130h
0x14007b608  mov     rax, cs:__security_cookie
0x14007b60f  xor     rax, rsp
0x14007b612  mov     [rbp+60h+var_40], rax
0x14007b616  mov     rax, [rbp+60h+arg_30]
0x14007b61d  xor     r14d, r14d
0x14007b620  mov     r15, [rbp+60h+arg_40]
0x14007b627  xorps   xmm1, xmm1
0x14007b62a  mov     rdi, [rbp+60h+arg_20]
0x14007b631  xorps   xmm0, xmm0
0x14007b634  mov     [rbp+60h+Src], rax
0x14007b638  mov     rsi, rdx
0x14007b63b  mov     eax, [rbp+60h+arg_38]
0x14007b641  mov     r13, rcx
0x14007b644  mov     dword ptr [rbp+60h+Size], eax
0x14007b647  mov     rax, [rbp+60h+arg_48]
0x14007b64e  mov     [rbp+60h+var_90], rax
0x14007b652  mov     rax, [rbp+60h+arg_50]
0x14007b659  mov     [rbp+60h+var_A0], rax
0x14007b65d  mov     rax, [rbp+60h+arg_58]
0x14007b664  mov     [rbp+60h+var_A8], rax
0x14007b668  mov     rax, [rbp+60h+arg_60]
0x14007b66f  mov     [rbp+60h+var_98], rax
0x14007b673  mov     rax, [rbp+60h+arg_68]
0x14007b67a  mov     [rbp+60h+var_B0], rax
0x14007b67e  mov     rax, [rdx+10h]
0x14007b682  mov     [rsp+160h+var_104], r9d
0x14007b687  mov     [rsp+160h+FileObject], r8
0x14007b68c  mov     qword ptr [rbp+60h+InputBuffer], rcx
0x14007b690  mov     r12, [rax+20h]
0x14007b694  xor     eax, eax
0x14007b696  mov     [rbp+60h+var_E0], r15
0x14007b69a  mov     dword ptr [rsp+160h+var_E8], r14d
0x14007b69f  mov     [rbp+60h+var_48], rax
0x14007b6a3  mov     [rbp+60h+var_C0], r14
0x14007b6a7  movups  [rbp+60h+var_88], xmm0
0x14007b6ab  movups  [rbp+60h+FileInformation], xmm1
0x14007b6af  movups  [rbp+60h+var_58], xmm1
0x14007b6b3  test    r15, r15
0x14007b6b6  jz      short loc_14007B72D
0x14007b6b8  cmp     [r15], r14
0x14007b6bb  jge     short loc_14007B72D
0x14007b6bd  mov     edi, 0C000CF0Bh
0x14007b6c2  mov     ecx, edi
0x14007b6c4  mov     ebx, edi
0x14007b6c6  call    HsmDbgBreakOnStatus
0x14007b6cb  mov     r10, cs:WPP_GLOBAL_Control
0x14007b6d2  lea     r15, WPP_GLOBAL_Control
0x14007b6d9  cmp     r10, r15
0x14007b6dc  jz      short loc_14007B721
0x14007b6de  mov     eax, [r10+2Ch]
0x14007b6e2  test    al, 1
0x14007b6e4  jz      short loc_14007B721
0x14007b6e6  cmp     byte ptr [r10+29h], 2
0x14007b6eb  jb      short loc_14007B721
0x14007b6ed  mov     rcx, rsi
0x14007b6f0  call    HsmpGetStreamSize
0x14007b6f5  lea     edx, [r14+44h]
0x14007b6f9  mov     dword ptr [rsp+160h+OutputBufferLength+8], edi
0x14007b6fd  mov     rcx, [r10+18h]
0x14007b701  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x14007b708  mov     qword ptr [rsp+160h+OutputBufferLength], r12
0x14007b70d  mov     r9, rsi
0x14007b710  mov     [rsp+160h+LengthReturned], rax
0x14007b715  mov     eax, [rsi+1Ch]
0x14007b718  mov     [rsp+160h+FileInformationClass], eax
0x14007b71c  call    WPP_SF_qLiid
0x14007b721  mov     r14d, [rbp+60h+arg_28]
0x14007b728  jmp     loc_14007C988
0x14007b72d  mov     r9d, [rdx+1Ch]
0x14007b731  mov     rcx, rsi; Context
0x14007b734  xor     edx, edx; CallbackData
0x14007b736  mov     dword ptr [rbp+60h+var_D8], r9d
0x14007b73a  call    HsmpAcquireSyncOpRundownProtection
0x14007b73f  mov     ecx, eax
0x14007b741  mov     ebx, eax
0x14007b743  call    HsmDbgBreakOnStatus
0x14007b748  test    ebx, ebx
0x14007b74a  jns     short loc_14007B785
0x14007b74c  mov     r10, cs:WPP_GLOBAL_Control
0x14007b753  lea     r15, WPP_GLOBAL_Control
0x14007b75a  cmp     r10, r15
0x14007b75d  jz      short loc_14007B721
0x14007b75f  mov     ecx, [r10+2Ch]
0x14007b763  test    cl, 1
0x14007b766  jz      short loc_14007B721
0x14007b768  cmp     byte ptr [r10+29h], 2
0x14007b76d  jb      short loc_14007B721
0x14007b76f  mov     rcx, rsi
0x14007b772  call    HsmpGetStreamSize
0x14007b777  mov     edx, 45h ; 'E'
0x14007b77c  mov     dword ptr [rsp+160h+OutputBufferLength+8], ebx
0x14007b780  jmp     loc_14007B6FD
0x14007b785  mov     eax, [rsp+160h+var_104]
0x14007b789  mov     [rsp+160h+var_110], r14
0x14007b78e  mov     [rsp+160h+var_108], r14b
0x14007b793  mov     r14d, [rbp+60h+arg_28]
0x14007b79a  bt      eax, 0Bh
0x14007b79e  jb      short loc_14007B7BA
0x14007b7a0  test    al, 2
0x14007b7a2  jnz     short loc_14007B7AD
0x14007b7a4  test    r14d, r14d
0x14007b7a7  jnz     short loc_14007B7AD
0x14007b7a9  test    al, 1
0x14007b7ab  jz      short loc_14007B7BA
0x14007b7ad  mov     rcx, rsi
0x14007b7b0  call    HsmpWaitForUserRequestRundownRelease
0x14007b7b5  mov     [rsp+160h+var_108], 1
0x14007b7ba  mov     dl, 1
0x14007b7bc  mov     rcx, rsi
0x14007b7bf  call    HsmpAcquireReparseUpdateLock
0x14007b7c4  mov     r8, [rsp+160h+FileObject]
0x14007b7c9  lea     rax, [rsp+160h+var_E8]
0x14007b7ce  mov     r9d, 5
0x14007b7d4  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x14007b7d9  mov     rdx, rsi
0x14007b7dc  mov     rcx, r13
0x14007b7df  call    HsmpCldGetSyncPolicy
0x14007b7e4  mov     ecx, eax
0x14007b7e6  mov     ebx, eax
0x14007b7e8  call    HsmDbgBreakOnStatus
0x14007b7ed  xor     r10d, r10d
0x14007b7f0  test    ebx, ebx
0x14007b7f2  jns     short loc_14007B834
0x14007b7f4  mov     r10, cs:WPP_GLOBAL_Control
0x14007b7fb  lea     r15, WPP_GLOBAL_Control
0x14007b802  cmp     r10, r15
0x14007b805  jz      loc_14007C93D
0x14007b80b  mov     eax, [r10+2Ch]
0x14007b80f  test    al, 1
0x14007b811  jz      loc_14007C93D
0x14007b817  cmp     byte ptr [r10+29h], 2
0x14007b81c  jb      loc_14007C93D
0x14007b822  mov     rcx, rsi
0x14007b825  call    HsmpGetStreamSize
0x14007b82a  mov     edx, 46h ; 'F'
0x14007b82f  jmp     loc_14007C915
0x14007b834  mov     r8d, [rsp+160h+var_104]
0x14007b839  mov     edx, r8d
0x14007b83c  and     edx, 400h
0x14007b842  mov     ecx, r8d
0x14007b845  and     ecx, 800000h
0x14007b84b  mov     [rsp+160h+var_100], edx
0x14007b84f  mov     [rsp+160h+var_F0], ecx
0x14007b853  test    edx, edx
0x14007b855  jz      short loc_14007B8AD
0x14007b857  test    ecx, ecx
0x14007b859  jz      short loc_14007B8B1
0x14007b85b  mov     edi, 0C000CF0Bh
0x14007b860  mov     ecx, edi
0x14007b862  mov     ebx, edi
0x14007b864  call    HsmDbgBreakOnStatus
0x14007b869  mov     r10, cs:WPP_GLOBAL_Control
0x14007b870  lea     r15, WPP_GLOBAL_Control
0x14007b877  cmp     r10, r15
0x14007b87a  jz      loc_14007C93D
0x14007b880  mov     eax, [r10+2Ch]
0x14007b884  test    al, 1
0x14007b886  jz      loc_14007C93D
0x14007b88c  cmp     byte ptr [r10+29h], 2
0x14007b891  jb      loc_14007C93D
0x14007b897  mov     rcx, rsi
0x14007b89a  call    HsmpGetStreamSize
0x14007b89f  mov     edx, 47h ; 'G'
0x14007b8a4  mov     dword ptr [rsp+160h+OutputBufferLength+8], edi
0x14007b8a8  jmp     loc_14007C919
0x14007b8ad  mov     [rsp+160h+var_F0], ecx
0x14007b8b1  mov     eax, dword ptr [rsp+160h+var_E8]
0x14007b8b5  and     dword ptr [rbp+60h+var_D8], 2
0x14007b8b9  and     al, 0Fh
0x14007b8bb  cmp     al, 4
0x14007b8bd  jnb     short loc_14007B8D2
0x14007b8bf  test    dword ptr [rsi+1Ch], 8000h
0x14007b8c6  jz      short loc_14007B8CE
0x14007b8c8  test    ecx, ecx
0x14007b8ca  jz      short loc_14007B8D2
0x14007b8cc  jmp     short loc_14007B8FB
0x14007b8ce  test    edx, edx
0x14007b8d0  jz      short loc_14007B8FB
0x14007b8d2  test    r8b, 2
0x14007b8d6  jnz     loc_14007C8DA
0x14007b8dc  test    r14d, r14d
0x14007b8df  jnz     loc_14007C8DA
0x14007b8e5  test    r15, r15
0x14007b8e8  jz      short loc_14007B903
0x14007b8ea  mov     rcx, rsi
0x14007b8ed  call    HsmpGetStreamSize
0x14007b8f2  cmp     rax, [r15]
0x14007b8f5  jl      loc_14007C8DA
0x14007b8fb  mov     cl, 1
0x14007b8fd  test    r8b, 2
0x14007b901  jnz     short loc_14007B906
0x14007b903  mov     cl, r10b
0x14007b906  test    cl, cl
0x14007b908  mov     eax, 1
0x14007b90d  cmovz   eax, r14d
0x14007b911  mov     r14d, eax
0x14007b914  lea     rax, [rbp+60h+var_88]
0x14007b918  cmovz   rax, rdi
0x14007b91c  mov     [rbp+60h+var_C8], rax
0x14007b920  test    r14d, r14d
0x14007b923  jnz     short loc_14007B92E
0x14007b925  test    dword ptr [rsi+1Ch], 100h
0x14007b92c  jnz     short loc_14007B98D
0x14007b92e  cmp     [rbp+60h+Src], r10
0x14007b932  jnz     short loc_14007B93A
0x14007b934  cmp     [rsi+30h], r10
0x14007b938  jz      short loc_14007B93F
0x14007b93a  test    r8b, r8b
0x14007b93d  jns     short loc_14007B98D
0x14007b93f  mov     edi, 0C000CF0Bh
0x14007b944  mov     ecx, edi
0x14007b946  mov     ebx, edi
0x14007b948  call    HsmDbgBreakOnStatus
0x14007b94d  mov     r10, cs:WPP_GLOBAL_Control
0x14007b954  lea     r15, WPP_GLOBAL_Control
0x14007b95b  cmp     r10, r15
0x14007b95e  jz      loc_14007C93D
0x14007b964  mov     eax, [r10+2Ch]
0x14007b968  test    al, 1
0x14007b96a  jz      loc_14007C93D
0x14007b970  cmp     byte ptr [r10+29h], 2
0x14007b975  jb      loc_14007C93D
0x14007b97b  mov     rcx, rsi
0x14007b97e  call    HsmpGetStreamSize
0x14007b983  mov     edx, 49h ; 'I'
0x14007b988  jmp     loc_14007B8A4
0x14007b98d  mov     rdi, [rsp+160h+FileObject]
0x14007b992  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x14007b996  mov     rcx, [r13+20h]; Instance
0x14007b99a  mov     rdx, rdi; FileObject
0x14007b99d  mov     [rsp+160h+LengthReturned], r10; LengthReturned
0x14007b9a2  mov     r9d, 28h ; '('; Length
0x14007b9a8  mov     [rsp+160h+FileInformationClass], 4; FileInformationClass
0x14007b9b0  call    cs:__imp_FltQueryInformationFile
0x14007b9b7  nop     dword ptr [rax+rax+00h]
0x14007b9bc  mov     ecx, eax
0x14007b9be  mov     ebx, eax
0x14007b9c0  call    HsmDbgBreakOnStatus
0x14007b9c5  test    ebx, ebx
0x14007b9c7  jns     short loc_14007BA09
0x14007b9c9  mov     r10, cs:WPP_GLOBAL_Control
0x14007b9d0  lea     r15, WPP_GLOBAL_Control
0x14007b9d7  cmp     r10, r15
0x14007b9da  jz      loc_14007C93D
0x14007b9e0  mov     eax, [r10+2Ch]
0x14007b9e4  test    al, 1
0x14007b9e6  jz      loc_14007C93D
0x14007b9ec  cmp     byte ptr [r10+29h], 2
0x14007b9f1  jb      loc_14007C93D
0x14007b9f7  mov     rcx, rsi
0x14007b9fa  call    HsmpGetStreamSize
0x14007b9ff  mov     edx, 4Ah ; 'J'
0x14007ba04  jmp     loc_14007C915
0x14007ba09  mov     ecx, [rsp+160h+var_104]
0x14007ba0d  bt      ecx, 0Fh
0x14007ba11  jb      short loc_14007BA7C
0x14007ba13  test    r14d, r14d
0x14007ba16  jz      short loc_14007BA7C
0x14007ba18  mov     eax, dword ptr [rbp+60h+var_48]
0x14007ba1b  bt      eax, 13h
0x14007ba1f  jnb     short loc_14007BA7C
0x14007ba21  mov     edx, 180000h
0x14007ba26  mov     ebx, 0C000CF0Bh
0x14007ba2b  and     eax, edx
0x14007ba2d  cmp     eax, edx
0x14007ba2f  lea     ecx, [rbx+0Ah]
0x14007ba32  cmovnz  ebx, ecx
0x14007ba35  mov     ecx, ebx
0x14007ba37  call    HsmDbgBreakOnStatus
0x14007ba3c  mov     r10, cs:WPP_GLOBAL_Control
0x14007ba43  lea     r15, WPP_GLOBAL_Control
0x14007ba4a  cmp     r10, r15
0x14007ba4d  jz      loc_14007C93D
0x14007ba53  mov     eax, [r10+2Ch]
0x14007ba57  test    al, 1
0x14007ba59  jz      loc_14007C93D
0x14007ba5f  cmp     byte ptr [r10+29h], 2
0x14007ba64  jb      loc_14007C93D
0x14007ba6a  mov     rcx, rsi
0x14007ba6d  call    HsmpGetStreamSize
0x14007ba72  mov     edx, 4Bh ; 'K'
0x14007ba77  jmp     loc_14007C915
0x14007ba7c  bt      ecx, 0Ch
0x14007ba80  jb      loc_14007BB1B
0x14007ba86  test    cl, 8
0x14007ba89  jz      short loc_14007BA92
0x14007ba8b  bt      dword ptr [rsi+1Ch], 0Dh
0x14007ba90  jnb     short loc_14007BAA7
0x14007ba92  test    r14d, r14d
0x14007ba95  jz      loc_14007BB76
  ... truncated ...
```
