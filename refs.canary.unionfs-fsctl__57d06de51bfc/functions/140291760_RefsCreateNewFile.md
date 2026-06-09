# RefsCreateNewFile

- ea: `0x140291760`
- end: `0x140292dbf`
- name: `RefsCreateNewFile`
- size: `5727`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, __int64, __int64, __int64, __int16, __int64, __int64)`
- caller_count: `1`
- callee_count: `56`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14030a1a0`

## callees

- `0x140008c10`
- `0x14000bcc0`
- `0x14000cd70`
- `0x14000f3f0`
- `0x140081670`
- `0x14008ba50`
- `0x14008dbd0`
- `0x140091da0`
- `0x140094fc0`
- `0x140099b80`
- `0x14009f140`
- `0x1400a3bec`
- `0x1400ad0c8`
- `0x1400b6230`
- `0x1400b86c0`
- `0x1400bd6f0`
- `0x1400ca788`
- `0x1400caad0`
- `0x1400e1584`
- `0x1400e96a4`
- `0x1401e9cb2`
- `0x1401e9cc4`
- `0x1401e9ce0`
- `0x1401ea140`
- `0x140285fa0`
- `0x14028639c`
- `0x1402877f8`
- `0x14028cc8c`
- `0x140291760`
- `0x1402949ec`
- `0x1402cf3d8`
- `0x1402fde30`
- `0x1402fec90`
- `0x1402ff280`
- `0x1402ff698`
- `0x1403000b0`
- `0x1403008f0`
- `0x140304220`
- `0x140304dc0`
- `0x140306630`
- `0x140307140`
- `0x14030ffc0`
- `0x14031f1f0`
- `0x14031f610`
- `0x14031f700`
- `0x14031fda0`
- `0x140324070`
- `0x140325110`
- `0x140326aa0`
- `0x140327670`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140292c11`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140292c85`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140292ce9`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140342eff`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140342f7a`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140342fe0`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140292c11`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140292c85`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140292ce9`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140342eff`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140342f7a`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140342fe0`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x140291ac9`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x140291ac9`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140292af9`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140342dc9`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140292af9`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140342dc9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140292b0c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140342ddc`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140292b0c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140342ddc`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140292842`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140292842`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140292b35`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140342e0e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140292b35`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140342e0e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140292b41`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140342e1a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140292b41`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140342e1a`
- `ntoskrnl!ExReleaseFastResource` at `0x140292c32`
- `ntoskrnl!ExReleaseFastResource` at `0x140292ca2`
- `ntoskrnl!ExReleaseFastResource` at `0x140292d06`
- `ntoskrnl!ExReleaseFastResource` at `0x140342f20`
- `ntoskrnl!ExReleaseFastResource` at `0x140342f97`
- `ntoskrnl!ExReleaseFastResource` at `0x140342ffd`
- `ntoskrnl!ExReleaseFastResource` at `0x140292c32`
- `ntoskrnl!ExReleaseFastResource` at `0x140292ca2`
- `ntoskrnl!ExReleaseFastResource` at `0x140292d06`
- `ntoskrnl!ExReleaseFastResource` at `0x140342f20`
- `ntoskrnl!ExReleaseFastResource` at `0x140342f97`
- `ntoskrnl!ExReleaseFastResource` at `0x140342ffd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140292b22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140342df2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140292b22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140342df2`

## string_xrefs

- `0x1402919e3`: `Create.c`
- `0x140291a71`: `Create.c`
- `0x140291b23`: `Create.c`
- `0x140291f2c`: `Create.c`
- `0x140292265`: `Create.c`
- `0x140292605`: `Create.c`
- `0x14029276f`: `Create.c`
- `0x140292d83`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsCreateNewFile(
        struct _IRP_CONTEXT *a1,
        IRP *a2,
        __int64 a3,
        struct _FILE_NAME *a4,
        __int64 a5,
        struct _UNICODE_STRING *a6,
        __int64 a7,
        unsigned __int16 a8,
        struct _CREATE_CONTEXT *a9,
        struct _LCB **a10)
{
  bool v12; // r12
  int v13; // ebx
  __int64 v14; // r13
  __int64 result; // rax
  int v16; // r15d
  char v17; // r8
  unsigned int v18; // r9d
  __int64 v19; // rax
  __int64 v20; // rcx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  _DWORD *v26; // rbx
  unsigned int v27; // ecx
  int v28; // edx
  int v29; // eax
  int v30; // eax
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r9
  __int128 *v35; // rdx
  struct _FCB *v36; // r14
  __int64 v37; // rcx
  PMRX_NET_ROOT pNetRoot; // rcx
  __int64 v39; // r8
  __int64 Scb; // rsi
  int v41; // edx
  int v42; // r15d
  unsigned __int16 v43; // dx
  unsigned __int16 StreamChecksumType; // ax
  __int64 v45; // r10
  struct _LIST_ENTRY *v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  unsigned int v49; // r10d
  char v50; // dl
  __int64 v51; // r8
  __int64 v52; // rcx
  char v53; // r15
  __int16 v54; // ax
  struct _REFS_FILE_REFERENCE *v55; // r11
  int v56; // eax
  __int64 v57; // rcx
  __int16 v58; // bx
  int v59; // eax
  int v60; // eax
  int v61; // eax
  char v62; // cl
  int v63; // eax
  __int64 v64; // r8
  struct _IRP_CONTEXT *v65; // r12
  char *v66; // rbx
  struct _UNICODE_STRING *v67; // r15
  const struct _UNICODE_STRING *v68; // rdx
  unsigned __int64 CmsKeyLength; // r9
  __int64 v70; // rax
  void *v71; // rsp
  NTSTATUS v72; // ebx
  unsigned int v73; // r8d
  char v74; // al
  __int64 v75; // rax
  __int64 v76; // rbx
  struct _SCB **v77; // r12
  int v78; // ecx
  struct _IRP_CONTEXT *v79; // rsi
  int v80; // eax
  __int16 v81; // dx
  int v82; // eax
  int v83; // edx
  NTSTATUS v84; // r15d
  struct _SCB *v85; // rsi
  struct CmsTransactionContext **v86; // r15
  __int64 v87; // rcx
  NTSTATUS v88; // ebx
  unsigned int v89; // r8d
  int v90; // eax
  __int64 v91; // rcx
  int v92; // eax
  NTSTATUS v93; // ebx
  unsigned int v94; // r8d
  struct _IRP *MasterIrp; // rdx
  __int64 v96; // rax
  struct _SCB *v97; // r8
  IRP *v98; // rsi
  unsigned int v99; // r9d
  struct _IRP *v100; // rdx
  __int64 v101; // rax
  struct _SCB *v102; // r8
  __int64 v103; // rcx
  __int64 v104; // rcx
  __int64 v105; // rcx
  __int64 v106; // rax
  struct _UNICODE_STRING *v107; // rdx
  struct _UNICODE_STRING *v108; // r8
  PWSTR Buffer; // rax
  struct _UNICODE_STRING *v110; // rax
  int v111; // eax
  unsigned int v112; // r8d
  _DWORD *v113; // rsi
  __int64 v115; // rdx
  struct _IRP_CONTEXT *v116; // r13
  __int64 v117; // r8
  struct _LCB *v118; // rbx
  __int64 v119; // r8
  _QWORD *i; // rbx
  __int64 v121; // rbx
  __int64 v122; // r8
  struct _LCB *v123; // rsi
  __int64 v124; // rbx
  __int64 v125; // [rsp+0h] [rbp-80h] BYREF
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine; // [rsp+20h] [rbp-60h]
  POPLOCK_FS_PREPOST_IRP PostIrpRoutine; // [rsp+28h] [rbp-58h]
  ULONG v128[2]; // [rsp+30h] [rbp-50h]
  unsigned __int8 *v129; // [rsp+48h] [rbp-38h]
  char v130; // [rsp+80h] [rbp+0h] BYREF
  unsigned __int8 v131; // [rsp+81h] [rbp+1h] BYREF
  char v132; // [rsp+82h] [rbp+2h]
  char v133; // [rsp+83h] [rbp+3h]
  unsigned __int16 v134; // [rsp+88h] [rbp+8h] BYREF
  int v135; // [rsp+90h] [rbp+10h] BYREF
  NTSTATUS v136; // [rsp+94h] [rbp+14h]
  struct _IRP_CONTEXT *v137; // [rsp+98h] [rbp+18h]
  __int64 v138; // [rsp+A0h] [rbp+20h]
  PIRP Irp; // [rsp+A8h] [rbp+28h]
  char v140; // [rsp+B0h] [rbp+30h]
  unsigned int v141; // [rsp+B4h] [rbp+34h]
  unsigned int v142; // [rsp+B8h] [rbp+38h]
  struct _LCB *v143[2]; // [rsp+C0h] [rbp+40h] BYREF
  PVOID P; // [rsp+D0h] [rbp+50h]
  unsigned int v145; // [rsp+D8h] [rbp+58h]
  int v146; // [rsp+DCh] [rbp+5Ch]
  struct _FCB *Fcb; // [rsp+E0h] [rbp+60h]
  struct _LCB *v148; // [rsp+E8h] [rbp+68h]
  struct _REFS_FILE_REFERENCE *v149; // [rsp+F0h] [rbp+70h] BYREF
  __int64 v150; // [rsp+F8h] [rbp+78h] BYREF
  struct _FILE_NAME *v151; // [rsp+100h] [rbp+80h]
  struct _CREATE_CONTEXT *v152; // [rsp+108h] [rbp+88h]
  struct _UNICODE_STRING *v153; // [rsp+110h] [rbp+90h]
  __int64 v154; // [rsp+118h] [rbp+98h]
  struct _IRP_CONTEXT *v155; // [rsp+120h] [rbp+A0h]
  struct _UNICODE_STRING *v156; // [rsp+128h] [rbp+A8h]
  struct _LCB **v157; // [rsp+130h] [rbp+B0h]
  __int64 v158; // [rsp+138h] [rbp+B8h]
  struct _FCB *v159; // [rsp+140h] [rbp+C0h]
  __int64 v160; // [rsp+148h] [rbp+C8h]
  _OWORD v161[5]; // [rsp+150h] [rbp+D0h] BYREF
  __int64 v162; // [rsp+1A0h] [rbp+120h]
  struct _REFS_FILE_REFERENCE *v163; // [rsp+1A8h] [rbp+128h]
  __int128 v164; // [rsp+1B0h] [rbp+130h] BYREF
  __int128 v165; // [rsp+1C0h] [rbp+140h] BYREF
  __int128 v166; // [rsp+1D0h] [rbp+150h]

  v162 = (__int64)&v125;
  v151 = a4;
  Irp = a2;
  v137 = a1;
  v155 = a1;
  v158 = a3;
  *(_QWORD *)&v166 = a5;
  v153 = a6;
  v150 = a7;
  v134 = a8;
  v138 = (__int64)a9;
  v152 = a9;
  v157 = a10;
  v160 = (__int64)a10;
  v12 = 0;
  v135 = 0;
  *(_OWORD *)v143 = 0;
  v130 = 0;
  v131 = 0;
  v13 = *(unsigned __int16 *)(*((_QWORD *)a9 + 20) + 24LL);
  *((_DWORD *)a1 + 175) = 27;
  v14 = *(_QWORD *)(a3 + 144);
  result = RefsCheckValidAttributeAccess(
             (_DWORD)a1,
             *((_QWORD *)a9 + 20),
             v14,
             0,
             (__int64)&v150,
             (__int64)&v134,
             *((_DWORD *)a9 + 36),
             (__int64)&v135,
             (__int64)&v130);
  v136 = result;
  if ( (int)result < 0 )
    return result;
  v16 = v13;
  v17 = v130;
  if ( v130 )
  {
    if ( (v13 & 0x100) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 113, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225485LL;
      v18 = 8533;
LABEL_32:
      RefsStatusDebug(-1073741811, 0, "Create.c", v18);
      return 3221225485LL;
    }
    v19 = *((_QWORD *)a9 + 25);
    if ( v19 && (*(_BYTE *)(v19 + 2) & 0xD) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 114, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225485LL;
      v18 = 8546;
      goto LABEL_32;
    }
  }
  else
  {
    v20 = *((_QWORD *)a9 + 25);
    if ( v20 )
    {
      if ( *(char *)(v20 + 2) >= 0 )
        LOBYTE(v21) = 0;
      else
        v21 = *(_DWORD *)(v20 + 60);
      if ( (v21 & 1) != 0 )
        v22 = *(_DWORD *)(v20 + 76);
      else
        LOBYTE(v22) = 0;
      if ( (v22 & 1) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            115,
            WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
            3221225485LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          return 3221225485LL;
        v18 = 8557;
        goto LABEL_32;
      }
    }
  }
  v23 = *((_QWORD *)a9 + 20);
  if ( (*(_DWORD *)(v23 + 16) & 0x1000) != 0 && (v13 & 1) != 0 && (*(_BYTE *)(v23 + 2) & 0x40) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 116, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225761LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741535, 0, "Create.c", 0x2178u);
    return 3221225761LL;
  }
  v24 = *(_QWORD *)(a3 + 136);
  v25 = *(_QWORD *)(v24 + 88);
  if ( !*(_QWORD *)(v25 + 248) && *(_QWORD *)(v25 + 256) && (*(_DWORD *)(v24 + 152) & 0x400) != 0 )
  {
    if ( !(unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(*(unsigned int *)(v24 + 156)) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 117, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221226113LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741183, 0, "Create.c", 0x2184u);
      return 3221226113LL;
    }
    v17 = v130;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a3 + 136) + 8LL) & 0x100LL) == 0 || a3 == *(_QWORD *)(v14 + 32) )
  {
    v148 = 0;
    Fcb = 0;
    P = 0;
    v133 = 0;
    LOBYTE(v146) = 0;
    v149 = 0;
    v154 = v14;
    if ( ((v134 - 128) & 0xFFCF) == 0 && v134 != 144 )
    {
      *((_DWORD *)a9 + 43) |= 0x100u;
      v26 = *(_DWORD **)(*(_QWORD *)(*((_QWORD *)a9 + 20) + 8LL) + 8LL);
      v27 = 4;
      if ( !v17 )
        v27 = 2;
      v145 = v27;
      v28 = v26[4];
      if ( (v28 & 0x1000000) != 0 )
      {
        v27 |= 0x1000000u;
        v145 = v27;
      }
      if ( (v26[3] & 4) != 0 )
      {
        v26[5] |= v28 & 0xFEFFFFFF;
        v26[4] = v28 & ~v26[5];
        v27 = 0;
        v145 = 0;
      }
      RefsAccessCheck(a1, a9, *(struct _FCB **)(a3 + 136), 0, Irp, v27, 1u, 1u, 0);
      v26[5] |= v26[4];
      v29 = v26[5];
      if ( (v29 & 0x2000000) != 0 )
      {
        v30 = v29 | 0x1F01FF;
        v26[5] = v30;
        v26[5] = v30 & 0xFDFFFFFF;
      }
      v26[4] = 0;
      P = RefsCacheSharedSecurityForCreate(a1, *(struct _FCB **)(a3 + 136));
      if ( v134 == 160 )
        IndexSCB::EnsureDirectoryNormalizedName((IndexSCB *)a3, a1);
      v31 = *((_QWORD *)a9 + 25);
      if ( v31 )
      {
        if ( (*(_BYTE *)(v31 + 2) & 2) != 0 )
        {
          v32 = *(_QWORD *)(v14 + 48);
          if ( v32 )
          {
            RefsAcquireExclusiveScb(a1, v32, 0);
            v131 = 1;
          }
        }
      }
      if ( v130 )
      {
        RefsAllocateObjectId(a1, (struct _REFS_FILE_REFERENCE *)v143);
      }
      else
      {
        v143[1] = *(struct _LCB **)(*(_QWORD *)(*(_QWORD *)(a3 + 136) + 88LL) + 256LL);
        v143[0] = (struct _LCB *)_InterlockedIncrement64((volatile signed __int64 *)(a3 + 424));
      }
      if ( Irp->Overlay.AllocationSize.QuadPart )
      {
        v12 = 1;
      }
      else
      {
        v33 = *((_QWORD *)a9 + 25);
        if ( v33 && (*(_BYTE *)(v33 + 2) & 4) != 0 )
          v12 = *(_QWORD *)(v33 + 16) > 0LL;
      }
      *((_DWORD *)a1 + 1) |= 0x10000u;
      if ( v130 )
      {
        v164 = *(_OWORD *)v143;
        PostIrpRoutine = 0;
        CompletionRoutine = 0;
        v34 = 0;
        v35 = &v164;
      }
      else
      {
        v34 = (*(unsigned __int8 *)(*((_QWORD *)a9 + 20) + 2LL) >> 1) & 1;
        v165 = *(_OWORD *)v143;
        PostIrpRoutine = 0;
        CompletionRoutine = (POPLOCK_WAIT_COMPLETE_ROUTINE)a3;
        v35 = &v165;
      }
      Fcb = (struct _FCB *)RefsCreateFcb(a1, v35, 17, v34, CompletionRoutine, PostIrpRoutine);
      v36 = Fcb;
      v143[0] = (struct _LCB *)RefsCreateLcb(v37, a3, Fcb, v153, 0);
      v148 = v143[0];
      pNetRoot = v36->pNetRoot;
      if ( pNetRoot[2].pSrvCall || !pNetRoot[2].Context )
        v39 = 128;
      else
        v39 = 160;
      Scb = RefsCreateScb(v137, v36, v39, 0, 0, 0);
      v41 = *(_DWORD *)(*(_QWORD *)(a3 + 136) + 152LL) & 0x28000;
      v42 = v41 | v16;
      v141 = v42;
      *((_DWORD *)&v36->1 + 38) |= v41;
      *(_WORD *)(Scb + 258) = *(_WORD *)(a3 + 258);
      v43 = *(_WORD *)(a3 + 260);
      *(_WORD *)(Scb + 260) = v43;
      if ( (*(_BYTE *)(*(_QWORD *)(v138 + 160) + 2LL) & 2) != 0 )
      {
        StreamChecksumType = 0;
        *(_WORD *)(Scb + 260) = 0;
      }
      else
      {
        StreamChecksumType = v43;
      }
      if ( (v42 & 0x8000) != 0 && !*(_WORD *)(a3 + 260) )
      {
        StreamChecksumType = RefsGetStreamChecksumType(*(struct _VCB **)(*(_QWORD *)(a3 + 136) + 80LL));
        *(_WORD *)(Scb + 260) = StreamChecksumType;
      }
      if ( StreamChecksumType )
      {
        v42 |= 0x8000u;
        v141 = v42;
        *((_DWORD *)&v36->1 + 38) |= 0x8000u;
      }
      RefsIncrementFcbCloseCount(v36);
      v133 = 1;
      if ( Irp->AssociatedIrp.MasterIrp
        && ((*(_DWORD *)(*(_QWORD *)(v45 + 160) + 16LL) & 0x200) != 0 || (v135 & 2) == 0) )
      {
        RefsCompleteCreateRequest(v137, v45, Irp, 3221225506LL);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            119,
            WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
            3221225506LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741790, 0, "Create.c", 0x22B9u);
        local_unwind_0(v162, &loc_140292D96);
      }
      if ( *((_QWORD *)v36->Header.FileContextSupportPointer + 8) )
      {
        v46 = (struct _LIST_ENTRY *)P;
        *(PKEVENT *)((char *)&v36->pBufferingStateChangeCompletedEvent + 4) = (PKEVENT)*((_QWORD *)P + 1);
        v36->ScavengerFinalizationList.Flink = v46;
        P = 0;
      }
      v47 = *(_QWORD *)(a3 + 136);
      if ( (*(_BYTE *)(v47 + 8) & 8) == 0 )
        RefsUpdateFcbInfoFromDisk(v137, (struct _FCB *)v47, 0);
      RefsReloadSharedSecurityBySecurityIdIfNeeded(v137, *(struct _FCB **)(a3 + 136));
      v141 = v42 & 0xFFFFDFFF;
      v48 = *(_QWORD *)(a3 + 136);
      v49 = v42 & 0xFFFFDFFF | *(_DWORD *)(v48 + 152) & 0x2000;
      v142 = v49;
      v141 = v49;
      v50 = 0;
      v132 = 0;
      if ( v130 && (dword_14026188C & 1) != 0 && (*(_DWORD *)(v48 + 8) & 0x400000) != 0 )
      {
        v50 = 1;
        v132 = 1;
      }
      v51 = v138;
      v52 = *(_QWORD *)(v138 + 200);
      v53 = v146;
      if ( !v52 )
      {
        v55 = v149;
        goto LABEL_144;
      }
      v54 = *(_WORD *)(v52 + 2);
      if ( (v54 & 1) != 0 )
        v53 = 1;
      v140 = v53;
      if ( (v54 & 0x10) != 0 )
      {
        v55 = *(struct _REFS_FILE_REFERENCE **)(v52 + 32);
        v163 = v55;
        v56 = v135;
        if ( *((_QWORD *)v55 + 1) == -1 )
        {
          v56 = v135 | 0x40;
          v135 |= 0x40u;
        }
        if ( *((_QWORD *)v55 + 2) == -1 )
        {
          v56 |= 0x10u;
          v135 = v56;
        }
        if ( *((_QWORD *)v55 + 3) == -1 )
          v135 = v56 | 0x20;
        *(_WORD *)(v52 + 4) |= 0x10u;
      }
      else
      {
        v55 = v149;
      }
      v57 = *(_QWORD *)(v51 + 200);
      v58 = *(_WORD *)(v57 + 2) & 0x80;
      if ( v58 )
        v59 = *(_DWORD *)(v57 + 60);
      else
        LOBYTE(v59) = 0;
      if ( (v59 & 1) != 0 )
        v60 = *(_DWORD *)(v57 + 76);
      else
        LOBYTE(v60) = 0;
      if ( (v60 & 1) == 0 )
        goto LABEL_137;
      if ( (*(_DWORD *)(v57 + 80) & 1) == 0 )
      {
        v50 = 0;
        v132 = 0;
LABEL_144:
        if ( v130 )
        {
          *(_BYTE *)(Scb + 262) = 4;
          v62 = 4;
        }
        else if ( *(_WORD *)(Scb + 260) )
        {
          *(_BYTE *)(Scb + 262) = 1;
          v62 = 1;
        }
        else if ( v12
               || (v49 & 0x4200) != 0
               || (*(_DWORD *)(*(_QWORD *)(a3 + 136) + 152LL) & 0x4000) != 0
               || (*(unsigned __int8 *)(v14 + 793) | (*(unsigned __int8 *)(v14 + 792) << 8)) < 0x30Bu
               || (unsigned __int8)MsIsVolumeOnSmr(*(_QWORD *)(v14 + 112))
               || ((__int64)v36->spacer.Resource & 0x8104LL) != 0 )
        {
          *(_BYTE *)(Scb + 262) = 0;
          v62 = 0;
        }
        else
        {
          *(_BYTE *)(Scb + 262) = 2;
          v62 = 2;
        }
        v63 = 0;
        if ( v62 == 2 )
          v63 = 4;
        v64 = 0;
        if ( v130 )
          v64 = Scb;
        PostIrpRoutine = (POPLOCK_FS_PREPOST_IRP)v55;
        v65 = v137;
        RefsInitializeFcbStdInfo(v137, v36, v64, v53 & 1 | v63 | (2 * (v50 & 1u)), v49);
        v66 = 0;
        v67 = v153;
        if ( !v130 )
        {
          v149 = 0;
          CmsKeyLength = RefsGetCmsKeyLength(0, v153, &v149);
          v70 = CmsKeyLength + 15;
          if ( CmsKeyLength + 15 <= CmsKeyLength )
            v70 = 0xFFFFFFFFFFFFFF0LL;
          v71 = alloca(v70 & 0xFFFFFFFFFFFFFFF0uLL);
          v66 = &v130;
          RefsInitCmsKey((struct _CmsKey *)&v130, v68, v149, CmsKeyLength);
        }
        v72 = RefsInitializeFileFromDisk(v65, Scb, 1, v66);
        v136 = v72;
        if ( v72 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              120,
              WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
              (unsigned int)v72);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v72, v65, "Create.c", 0x236Bu);
          RefsRaiseStatusInternal(v65, v72, v73);
        }
        v74 = v130;
        if ( v130 || !*(_WORD *)v150 )
        {
          v76 = v138;
          v77 = (struct _SCB **)(v138 + 104);
          *(_QWORD *)(v138 + 104) = Scb;
        }
        else
        {
          v75 = RefsCreateScb(v65, v36, v134, v150, 0, 0);
          v76 = v138;
          v77 = (struct _SCB **)(v138 + 104);
          *(_QWORD *)(v138 + 104) = v75;
          *(_WORD *)(v75 + 258) = *(_WORD *)(Scb + 258);
          *((_WORD *)*v77 + 130) = *(_WORD *)(Scb + 260);
          *((_BYTE *)*v77 + 262) = 6;
          v74 = v130;
        }
        if ( v74 )
        {
          v79 = v137;
          RefsCreateDirectoryIndex(v137, v36);
          v78 = v135;
        }
        else
        {
          v78 = v135;
          if ( (v135 & 2) != 0 )
          {
            v79 = v137;
          }
          else
          {
            LOWORD(v128[0]) = (v142 & 0xFE00) << 6;
            v79 = v137;
            RefsCreateDataAttribute(v137, 0, (int)PostIrpRoutine, v128[0], 0);
            *(_DWORD *)(v76 + 172) |= 0x200000u;
            v78 = v135;
          }
        }
        v80 = *(_DWORD *)(v76 + 144);
        if ( v134 == 160 )
        {
          if ( (v80 & 0x40) != 0 )
          {
            v78 |= 8u;
            v81 = 0;
          }
          else
          {
            v81 = *(_WORD *)v166 - v67->Length;
          }
          v82 = RefsOpenAttribute(
                  (struct _IRP **)v79,
                  *(_QWORD *)(v76 + 160),
                  v14,
                  v143[0],
                  v76,
                  v36,
                  v81,
                  (__int64)&RefsFileNameIndex,
                  0xA0u,
                  2,
                  3,
                  1,
                  v78,
                  0,
                  v77,
                  (_QWORD *)(v76 + 112));
        }
        else
        {
          if ( (v80 & 0x40) != 0 )
            v83 = 0;
          else
            v83 = *(unsigned __int16 *)v166 - v67->Length;
          LOBYTE(v129) = 0;
          v82 = RefsOpenNewAttr(v79, v83, v150, v134, 1, v78, (int)v129, v76);
        }
        v136 = v82;
        v84 = v82;
        if ( v82 >= 0 )
        {
          v85 = *v77;
          v86 = (struct CmsTransactionContext **)v137;
          if ( !v130 )
          {
            if ( (*((_DWORD *)v85 + 38) & 0x20) == 0 )
              RefsUpdateScbFromAttribute(v137, *v77, 0);
            v87 = *(_QWORD *)(v76 + 160);
            if ( (*(_DWORD *)(v87 + 16) & 8) == 0 )
            {
              *(_DWORD *)(*(_QWORD *)(v87 + 48) + 80LL) |= 0x40u;
              if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v76 + 160) + 48LL) + 80LL) & 2) != 0 )
              {
                if ( *((_BYTE *)v85 + 5) )
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v76 + 160) + 48LL) + 48LL) = 1;
              }
            }
            if ( (*((_DWORD *)v85 + 38) & 0x10) != 0 )
            {
              memset(v161, 0, 40);
              RefsGetStreamSummary((struct _IRP_CONTEXT *)v86, v85, (struct _SmsStreamSummary *)v161);
              if ( v36->ActualAllocationLength != *(_QWORD *)&v161[2]
                || *((_QWORD *)&v36->1 + 18) != *((_QWORD *)v85 + 4) )
              {
                v36->ActualAllocationLength = *(_QWORD *)&v161[2];
                *((_QWORD *)&v36->1 + 18) = *((_QWORD *)v85 + 4);
                RefsUpdateStandardInformation((struct _IRP_CONTEXT *)v86, v36);
                *(_DWORD *)(*(_QWORD *)(v76 + 112) + 4LL) |= 0x10000u;
              }
            }
          }
          RefsAddLink((struct _IRP_CONTEXT *)v86, (struct IndexSCB *)a3, v36, v151);
          if ( v130 )
          {
            v166 = 0;
            v166 = *(_OWORD *)v151;
            RefsBindMinstoreTransaction((struct _IRP_CONTEXT *)v86);
            v88 = MsSetDurableTableObjectParentId(v86[3], (CmsBPlusTable *)v36->InternalSrvOpen[1].SrvOpenKeyList.Blink);
            v136 = v88;
            if ( v88 < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  121,
                  WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
                  (unsigned int)v88);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(v88, (struct _IRP_CONTEXT *)v86, "Create.c", 0x2424u);
              RefsRaiseStatusInternal((struct _IRP_CONTEXT *)v86, v88, v89);
            }
            v76 = v138;
          }
          v90 = *((_DWORD *)&v36->1 + 38);
          if ( (v90 & 0x20000000) != 0 || (v90 & 0x40000000) != 0 )
          {
            if ( (*((_DWORD *)&v36->1 + 43) & 4) != 0 )
              *((_DWORD *)&v36->1 + 43) &= 4u;
            else
              *((_DWORD *)&v36->1 + 43) = 0;
          }
          else
          {
            *((_DWORD *)&v36->1 + 43) = 0;
            v36->Header.Resource = (PERESOURCE)((unsigned __int64)v36->Header.Resource & ~0x10uLL);
          }
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v76 + 160) + 48LL) + 80LL) &= 0xFFF7CFFF;
          *(_DWORD *)(*(_QWORD *)(v76 + 112) + 4LL) &= 0xFD8FFFFF;
          v91 = *(_QWORD *)(v76 + 200);
          if ( v91 && (*(_BYTE *)(v91 + 2) & 2) != 0 )
          {
            RefsSetReparsePointInternal(
              (struct _IRP_CONTEXT *)v86,
              Irp,
              (struct _FCB *)v85,
              *(struct _CCB **)(v76 + 112),
              0,
              0,
              0,
              *(_WORD *)(v91 + 6),
              *(PREPARSE_DATA_BUFFER *)(v91 + 8),
              &v131);
            v93 = v92;
            v136 = v92;
            if ( v92 < 0 )
            {
              v94 = v138;
              if ( !_bittest16((const signed __int16 *)(*(_QWORD *)(v138 + 200) + 2LL), 8u) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    122,
                    WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
                    (unsigned int)v92);
                }
                if ( (_BYTE)RefsStatusDebugEnabled )
                  RefsStatusDebug(v93, (struct _IRP_CONTEXT *)v86, "Create.c", 0x246Cu);
                RefsRaiseStatusInternal((struct _IRP_CONTEXT *)v86, v93, v94);
              }
              v76 = v138;
            }
            else
            {
              v76 = v138;
              *(_WORD *)(*(_QWORD *)(v138 + 200) + 4LL) |= 2u;
              *(_DWORD *)(v76 + 172) |= 0x100000u;
            }
          }
          MasterIrp = Irp->AssociatedIrp.MasterIrp;
          if ( MasterIrp )
            RefsAddEa(
              (struct _IRP_CONTEXT *)v86,
              (PFILE_FULL_EA_INFORMATION)MasterIrp,
              *(_DWORD *)(*(_QWORD *)(v76 + 160) + 32LL),
              (__int64)&Irp->IoStatus);
          v96 = *(_QWORD *)(v76 + 200);
          if ( !v96 || !_bittest16((const signed __int16 *)(v96 + 2), 9u) )
            RefsUpdateFcbTimestamps(*(_QWORD *)(a3 + 136), *(_QWORD *)(v76 + 112), 2684354576LL);
          if ( ((__int64)v36->spacer.Resource & 4) != 0 )
          {
            RefsSetStreamStationaryAndPreloaded((struct _IRP_CONTEXT *)v86, v85, 1u);
            v97 = v85;
            v98 = Irp;
            RefsPrepareForCriticalIo((struct _IRP_CONTEXT *)v86, Irp, v97, v99);
          }
          else
          {
            v98 = Irp;
          }
          v84 = FsRtlCheckOplockEx((POPLOCK)(a3 + 88), v98, 0x10u, 0, 0, 0);
          v136 = v84;
          if ( v84 < 0 )
          {
            v79 = v137;
          }
          else
          {
            *(_QWORD *)(v76 + 96) = v36;
            LOBYTE(v128[0]) = 1;
            PostIrpRoutine = (POPLOCK_FS_PREPOST_IRP)v76;
            CompletionRoutine = *(POPLOCK_WAIT_COMPLETE_ROUTINE *)(a3 + 136);
            v100 = v98;
            v79 = v137;
            RefsEncryptionCreateCallback(v137, v100, (__int64)CompletionRoutine, v76, 1);
            *(_QWORD *)(v76 + 96) = 0;
            RefsPostUsnChange(v79, (struct _FCB *)*v77, *(_DWORD *)(v76 + 172), 0);
            v101 = *(_QWORD *)(v76 + 200);
            if ( v101 && *(int *)(v76 + 172) < 0 )
              *(_WORD *)(v101 + 4) |= 0x800u;
            v102 = *v77;
            if ( *(_WORD *)*v77 == 2051 && !*((_WORD *)v102 + 196) && *(_WORD *)(a3 + 392) )
              RefsUpdateNormalizedName(v79, a3, v102, v151);
            if ( *((_QWORD *)v79 + 76) )
            {
              RefsWriteUsnJournalChanges(v79);
              RefsCheckpointCurrentTransaction(v79);
            }
            v103 = *(_QWORD *)(v76 + 200);
            if ( v103 )
            {
              if ( (*(_BYTE *)(v103 + 2) & 0x10) != 0 )
              {
                **(_QWORD **)(v103 + 32) = v36->Context2;
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v76 + 200) + 32LL) + 8LL) = *((_QWORD *)&v36->1 + 16);
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v76 + 200) + 32LL) + 16LL) = *((_QWORD *)&v36->1 + 14);
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v76 + 200) + 32LL) + 24LL) = *((_QWORD *)&v36->1 + 15);
                *(_WORD *)(*(_QWORD *)(v76 + 200) + 4LL) |= 0x100u;
              }
              v104 = *(_QWORD *)(v76 + 200);
              if ( *(_WORD *)v104 >= 0x2Cu )
              {
                *(_DWORD *)(v104 + 40) = *((_DWORD *)&v36->1 + 38);
                *(_WORD *)(*(_QWORD *)(v76 + 200) + 4LL) |= 0x200u;
              }
              v105 = *(_QWORD *)(v76 + 200);
              if ( *(_WORD *)v105 >= 0x38u )
              {
                *(_QWORD *)(v105 + 48) = *(_QWORD *)&v36->FcbTableEntry.NodeTypeCode;
                *(_WORD *)(*(_QWORD *)(v76 + 200) + 4LL) |= 0x1000u;
              }
            }
            if ( (*(_DWORD *)(v76 + 144) & 0x40) == 0 )
            {
              v106 = *(_QWORD *)(v76 + 200);
              if ( !v106 || !_bittest16((const signed __int16 *)(v106 + 2), 0xAu) )
              {
                v107 = 0;
                v156 = 0;
                v108 = *(struct _UNICODE_STRING **)(v76 + 112);
                Buffer = v108[4].Buffer;
                if ( Buffer )
                {
                  v110 = (struct _UNICODE_STRING *)(*((_QWORD *)Buffer + 3) + 392LL);
                  if ( v110->Length )
                    v107 = v110;
                  v156 = v107;
                }
                RefsReportDirNotify(
                  (struct _IRP_CONTEXT *)((unsigned int)(v130 != 0) + 1),
                  (struct _VCB *)v36->Header.FileContextSupportPointer,
                  v108 + 1,
                  v108[2].Length,
                  0,
                  v107,
                  (v130 != 0) + 1,
                  1u,
                  *(struct _FCB **)(a3 + 136));
              }
            }
            v111 = *((_DWORD *)&v36->1 + 38);
            if ( ((v111 & 0x20000000) != 0 || (v111 & 0x40000000) != 0) && (*((_DWORD *)&v36->1 + 43) & 4) != 0 )
              *((_DWORD *)&v36->1 + 43) &= 4u;
            else
              *((_DWORD *)&v36->1 + 43) = 0;
            v112 = *(_DWORD *)(v76 + 76);
            if ( v112 )
              RefsInsertPrefixHashEntry(v79, v143[0], v112, *(_DWORD *)(v76 + 72));
            else
              RefsInsertLcbInPrefixHash(v79, v143[0]);
            Irp->IoStatus.Information = 2;
          }
        }
        if ( v131 )
          RefsReleaseFcb(v79, *(struct _FCB **)(*(_QWORD *)(v14 + 48) + 136LL));
        RefsDecrementFcbCloseCount(v36);
        v113 = P;
        if ( P )
        {
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v14 + 728));
          if ( (*v113)-- == 1 )
            ExFreePoolWithTag(v113, 0);
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v14 + 728));
          KeLeaveGuardedRegion();
          v76 = v138;
        }
        if ( v84 >= 0 )
        {
          v123 = v143[0];
        }
        else
        {
          v115 = *(_QWORD *)(v76 + 160);
          CompletionRoutine = (POPLOCK_WAIT_COMPLETE_ROUTINE)(v76 + 112);
          v116 = v137;
          RefsBackoutFailedOpens(v137, *(PFILE_OBJECT *)(v115 + 48), v36, *(struct _SCB **)(v76 + 104), v76 + 112);
          memset(v161, 0, 0x44u);
          *(_OWORD *)((char *)&v36->1 + 104) = v161[0];
          *(_OWORD *)((char *)&v36->1 + 120) = v161[1];
          *(_OWORD *)((char *)&v36->1 + 136) = v161[2];
          *(_OWORD *)((char *)&v36->1 + 152) = v161[3];
          v36->SrvOpenListVersion = v161[4];
          v118 = v143[0];
          if ( v143[0] )
          {
            RefsRemovePrefixHashEntry(v143[0]);
            *((_DWORD *)v118 + 1) = *((_DWORD *)v118 + 1) & 0xFFFFFFBD | 2;
            *((_DWORD *)v118 + 19) = 0;
          }
          v36->Header.Resource = (PERESOURCE)((unsigned __int64)v36->Header.Resource & ~8uLL);
          LOBYTE(v117) = 1;
          ExAcquireFastResourceExclusive(*((_QWORD *)v116 + 8) + 624LL, 0, v117);
          v36->Header.Resource = (PERESOURCE)((unsigned __int64)v36->Header.Resource | 0x2000001);
          ExReleaseFastResource(*((_QWORD *)v116 + 8) + 624LL, 0);
          *((_QWORD *)v116 + 1) |= 0x2000000000uLL;
          for ( i = &v36->Header.FastMutex->Count; i != &v36->spacer.FastMutex; i = (_QWORD *)*i )
            RefsMarkScbAsDeleted(i - 15);
          *v77 = 0;
          v121 = *(_QWORD *)(a3 + 136);
          LOBYTE(v119) = 1;
          ExAcquireFastResourceExclusive(*(_QWORD *)(v121 + 80) + 624LL, 0, v119);
          _InterlockedIncrement((volatile signed __int32 *)(v121 + 24));
          ExReleaseFastResource(*(_QWORD *)(v121 + 80) + 624LL, 0);
          v159 = v36;
          if ( (unsigned __int8)RefsTeardownStructures(v116, v36, 0) )
          {
            v36 = 0;
            v123 = 0;
          }
          else
          {
            v123 = v143[0];
          }
          v124 = *(_QWORD *)(a3 + 136);
          LOBYTE(v122) = 1;
          ExAcquireFastResourceExclusive(*(_QWORD *)(v124 + 80) + 624LL, 0, v122);
          _InterlockedDecrement((volatile signed __int32 *)(v124 + 24));
          ExReleaseFastResource(*(_QWORD *)(v124 + 80) + 624LL, 0);
          v76 = v138;
        }
        if ( v36 && v123 )
        {
          *v157 = v123;
          *(_QWORD *)(v76 + 96) = v36;
        }
        return (unsigned int)v84;
      }
      if ( (dword_14026188C & 1) != 0 )
      {
        v50 = 1;
        v132 = 1;
      }
      else
      {
LABEL_137:
        if ( !v50 )
          goto LABEL_144;
      }
      if ( v58 )
        v61 = *(_DWORD *)(v57 + 60);
      else
        LOBYTE(v61) = 0;
      if ( (v61 & 1) != 0 )
        *(_DWORD *)(v57 + 84) |= 1u;
      goto LABEL_144;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 118, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225506LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741790, 0, "Create.c", 0x2190u);
  return 3221225506LL;
}

```

## disassembly

```asm
0x140291760  push    rbp
0x140291762  push    rbx
0x140291763  push    rsi
0x140291764  push    rdi
0x140291765  push    r12
0x140291767  push    r13
0x140291769  push    r14
0x14029176b  push    r15
0x14029176d  sub     rsp, 1F8h
0x140291774  lea     rbp, [rsp+80h]
0x14029177c  mov     rax, cs:__security_cookie
0x140291783  xor     rax, rbp
0x140291786  mov     [rbp+1B0h+var_50], rax
0x14029178d  mov     [rbp+1B0h+var_90], rsp
0x140291794  mov     [rbp+1B0h+var_130], r9
0x14029179b  mov     rdi, r8
0x14029179e  mov     [rbp+1B0h+Irp], rdx
0x1402917a2  mov     r14, rcx
0x1402917a5  mov     [rbp+1B0h+var_198], rcx
0x1402917a9  mov     [rbp+1B0h+var_110], rcx
0x1402917b0  mov     [rbp+1B0h+var_F8], r8
0x1402917b7  mov     rax, [rbp+1B0h+arg_20]
0x1402917be  mov     qword ptr [rbp+1B0h+var_60], rax
0x1402917c5  mov     rax, [rbp+1B0h+arg_28]
0x1402917cc  mov     [rbp+1B0h+var_120], rax
0x1402917d3  mov     rax, [rbp+1B0h+arg_30]
0x1402917da  mov     [rbp+1B0h+var_138], rax
0x1402917de  movzx   eax, [rbp+1B0h+arg_38]
0x1402917e5  mov     [rbp+1B0h+var_1A8], ax
0x1402917e9  mov     rsi, [rbp+1B0h+arg_40]
0x1402917f0  mov     [rbp+1B0h+var_190], rsi
0x1402917f4  mov     [rbp+1B0h+var_128], rsi
0x1402917fb  mov     rax, [rbp+1B0h+arg_48]
0x140291802  mov     [rbp+1B0h+var_100], rax
0x140291809  mov     [rbp+1B0h+var_E8], rax
0x140291810  xor     r12d, r12d
0x140291813  mov     [rbp+1B0h+var_1A0], r12d
0x140291817  xorps   xmm0, xmm0
0x14029181a  movups  xmmword ptr [rbp+1B0h+var_170], xmm0
0x14029181e  mov     [rbp+1B0h+var_1B0], r12b
0x140291822  mov     [rbp+1B0h+var_1AF], r12b
0x140291826  mov     rax, [rsi+0A0h]
0x14029182d  movzx   ebx, word ptr [rax+18h]
0x140291831  mov     dword ptr [rcx+2BCh], 1Bh
0x14029183b  mov     r13, [r8+90h]
0x140291842  lea     rax, [rbp+1B0h+var_1B0]
0x140291846  mov     [rsp+230h+var_1F0], rax
0x14029184b  lea     rax, [rbp+1B0h+var_1A0]
0x14029184f  mov     qword ptr [rsp+230h+var_1F8], rax
0x140291854  mov     eax, [rsi+90h]
0x14029185a  mov     [rsp+230h+var_200], eax
0x14029185e  lea     rax, [rbp+1B0h+var_1A8]
0x140291862  mov     [rsp+230h+PostIrpRoutine], rax
0x140291867  lea     rax, [rbp+1B0h+var_138]
0x14029186b  mov     [rsp+230h+CompletionRoutine], rax
0x140291870  xor     r9d, r9d
0x140291873  mov     r8, r13
0x140291876  mov     rdx, [rsi+0A0h]
0x14029187d  call    RefsCheckValidAttributeAccess
0x140291882  mov     [rbp+1B0h+var_19C], eax
0x140291885  test    eax, eax
0x140291887  js      loc_140292D9B
0x14029188d  mov     r15d, ebx
0x140291890  movzx   r8d, [rbp+1B0h+var_1B0]
0x140291895  test    r8b, r8b
0x140291898  jz      loc_140291965
0x14029189e  mov     ebx, 100h
0x1402918a3  test    ebx, r15d
0x1402918a6  jz      short loc_1402918FB
0x1402918a8  lea     rax, WPP_GLOBAL_Control
0x1402918af  mov     rcx, cs:WPP_GLOBAL_Control
0x1402918b6  cmp     rcx, rax
0x1402918b9  jz      short loc_1402918E1
0x1402918bb  test    [rcx+2Ch], ebx
0x1402918be  jz      short loc_1402918E1
0x1402918c0  cmp     byte ptr [rcx+29h], 4
0x1402918c4  jb      short loc_1402918E1
0x1402918c6  mov     edx, 71h ; 'q'
0x1402918cb  mov     r9d, 0C000000Dh
0x1402918d1  lea     r8, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids
0x1402918d8  mov     rcx, [rcx+18h]
0x1402918dc  call    WPP_SF_d
0x1402918e1  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402918e8  test    al, al
0x1402918ea  jz      loc_1402919F6
0x1402918f0  mov     r9d, 2155h
0x1402918f6  jmp     loc_1402919E3
0x1402918fb  mov     rax, [rsi+0C8h]
0x140291902  test    rax, rax
0x140291905  jz      loc_140291A05
0x14029190b  test    byte ptr [rax+2], 0Dh
0x14029190f  jz      loc_140291A05
0x140291915  lea     rax, WPP_GLOBAL_Control
0x14029191c  mov     rcx, cs:WPP_GLOBAL_Control
0x140291923  cmp     rcx, rax
0x140291926  jz      short loc_14029194E
0x140291928  test    [rcx+2Ch], ebx
0x14029192b  jz      short loc_14029194E
0x14029192d  cmp     byte ptr [rcx+29h], 4
0x140291931  jb      short loc_14029194E
0x140291933  mov     edx, 72h ; 'r'
0x140291938  mov     r9d, 0C000000Dh
0x14029193e  lea     r8, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids
0x140291945  mov     rcx, [rcx+18h]
0x140291949  call    WPP_SF_d
0x14029194e  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140291955  test    al, al
0x140291957  jz      loc_1402919F6
0x14029195d  mov     r9d, 2162h
0x140291963  jmp     short loc_1402919E3
0x140291965  mov     rcx, [rsi+0C8h]
0x14029196c  test    rcx, rcx
0x14029196f  jz      loc_140291A00
0x140291975  movzx   eax, byte ptr [rcx+2]
0x140291979  test    al, al
0x14029197b  jns     short loc_140291982
0x14029197d  mov     eax, [rcx+3Ch]
0x140291980  jmp     short loc_140291985
0x140291982  mov     eax, r12d
0x140291985  test    al, 1
0x140291987  jz      short loc_14029198E
0x140291989  mov     eax, [rcx+4Ch]
0x14029198c  jmp     short loc_140291991
0x14029198e  mov     eax, r12d
0x140291991  test    al, 1
0x140291993  jz      short loc_140291A00
0x140291995  lea     rax, WPP_GLOBAL_Control
0x14029199c  mov     rcx, cs:WPP_GLOBAL_Control
0x1402919a3  cmp     rcx, rax
0x1402919a6  jz      short loc_1402919D2
0x1402919a8  test    dword ptr [rcx+2Ch], 100h
0x1402919af  jz      short loc_1402919D2
0x1402919b1  cmp     byte ptr [rcx+29h], 4
0x1402919b5  jb      short loc_1402919D2
0x1402919b7  mov     edx, 73h ; 's'
0x1402919bc  mov     r9d, 0C000000Dh
0x1402919c2  lea     r8, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids
0x1402919c9  mov     rcx, [rcx+18h]
0x1402919cd  call    WPP_SF_d
0x1402919d2  movzx   ecx, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402919d9  test    cl, cl
0x1402919db  jz      short loc_1402919F6
0x1402919dd  mov     r9d, 216Dh; unsigned int
0x1402919e3  lea     r8, aCreateC; "Create.c"
0x1402919ea  xor     edx, edx; struct _IRP_CONTEXT *
0x1402919ec  mov     ecx, 0C000000Dh; Status
0x1402919f1  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402919f6  mov     eax, 0C000000Dh
0x1402919fb  jmp     loc_140292D9B
0x140291a00  mov     ebx, 100h
0x140291a05  mov     rdx, [rsi+0A0h]
0x140291a0c  test    dword ptr [rdx+10h], 1000h
0x140291a13  setnz   cl
0x140291a16  test    r15b, 1
0x140291a1a  setnz   al
0x140291a1d  test    al, cl
0x140291a1f  jz      short loc_140291A8E
0x140291a21  test    byte ptr [rdx+2], 40h
0x140291a25  jnz     short loc_140291A8E
0x140291a27  lea     rax, WPP_GLOBAL_Control
0x140291a2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140291a35  cmp     rcx, rax
0x140291a38  jz      short loc_140291A60
0x140291a3a  test    [rcx+2Ch], ebx
0x140291a3d  jz      short loc_140291A60
0x140291a3f  cmp     byte ptr [rcx+29h], 4
0x140291a43  jb      short loc_140291A60
0x140291a45  mov     edx, 74h ; 't'
0x140291a4a  mov     r9d, 0C0000121h
0x140291a50  lea     r8, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids
0x140291a57  mov     rcx, [rcx+18h]
0x140291a5b  call    WPP_SF_d
0x140291a60  movzx   ecx, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140291a67  test    cl, cl
0x140291a69  jz      short loc_140291A84
0x140291a6b  mov     r9d, 2178h; unsigned int
0x140291a71  lea     r8, aCreateC; "Create.c"
0x140291a78  xor     edx, edx; struct _IRP_CONTEXT *
0x140291a7a  mov     ecx, 0C0000121h; Status
0x140291a7f  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140291a84  mov     eax, 0C0000121h
0x140291a89  jmp     loc_140292D9B
0x140291a8e  mov     rcx, [rdi+88h]
0x140291a95  mov     rax, [rcx+58h]
0x140291a99  cmp     [rax+0F8h], r12
0x140291aa0  jnz     loc_140291B45
0x140291aa6  cmp     [rax+100h], r12
0x140291aad  jz      loc_140291B45
0x140291ab3  test    dword ptr [rcx+98h], 400h
0x140291abd  jz      loc_140291B45
0x140291ac3  mov     ecx, [rcx+9Ch]
0x140291ac9  call    cs:__imp_FsRtlIsNonEmptyDirectoryReparsePointAllowed
0x140291ad0  nop     dword ptr [rax+rax+00h]
0x140291ad5  test    al, al
0x140291ad7  jnz     short loc_140291B40
0x140291ad9  lea     rax, WPP_GLOBAL_Control
0x140291ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x140291ae7  cmp     rcx, rax
0x140291aea  jz      short loc_140291B12
0x140291aec  test    [rcx+2Ch], ebx
0x140291aef  jz      short loc_140291B12
0x140291af1  cmp     byte ptr [rcx+29h], 4
0x140291af5  jb      short loc_140291B12
0x140291af7  mov     edx, 75h ; 'u'
0x140291afc  mov     r9d, 0C0000281h
0x140291b02  lea     r8, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids
0x140291b09  mov     rcx, [rcx+18h]
0x140291b0d  call    WPP_SF_d
0x140291b12  movzx   ecx, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140291b19  test    cl, cl
0x140291b1b  jz      short loc_140291B36
0x140291b1d  mov     r9d, 2184h; unsigned int
0x140291b23  lea     r8, aCreateC; "Create.c"
0x140291b2a  xor     edx, edx; struct _IRP_CONTEXT *
0x140291b2c  mov     ecx, 0C0000281h; Status
0x140291b31  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140291b36  mov     eax, 0C0000281h
0x140291b3b  jmp     loc_140292D9B
0x140291b40  movzx   r8d, [rbp+1B0h+var_1B0]
0x140291b45  mov     rax, [rdi+88h]
0x140291b4c  mov     ecx, [rax+8]
0x140291b4f  test    rbx, rcx
0x140291b52  jz      short loc_140291B5E
0x140291b54  cmp     rdi, [r13+20h]
0x140291b58  jnz     loc_140292D39
0x140291b5e  mov     [rbp+1B0h+var_148], r12
0x140291b62  mov     [rbp+1B0h+var_150], r12
0x140291b66  mov     [rbp+1B0h+P], r12
0x140291b6a  mov     [rbp+1B0h+var_1AD], r12b
0x140291b6e  mov     byte ptr [rbp+1B0h+var_154], r12b
0x140291b72  mov     [rbp+1B0h+var_140], 0
0x140291b7a  mov     [rbp+1B0h+var_118], r13
0x140291b81  mov     edx, 80h
0x140291b86  movzx   ecx, [rbp+1B0h+var_1A8]
0x140291b8a  movzx   eax, cx
0x140291b8d  sub     ax, dx
0x140291b90  mov     edx, 0FFCFh
0x140291b95  test    dx, ax
0x140291b98  jnz     loc_140292D39
0x140291b9e  mov     eax, 90h
0x140291ba3  cmp     cx, ax
0x140291ba6  jz      loc_140292D39
0x140291bac  or      [rsi+0ACh], ebx
0x140291bb2  mov     rax, [rsi+0A0h]
0x140291bb9  mov     rcx, [rax+8]
0x140291bbd  mov     rbx, [rcx+8]
0x140291bc1  mov     ecx, 4
0x140291bc6  mov     eax, 2
0x140291bcb  test    r8b, r8b
0x140291bce  cmovz   ecx, eax
0x140291bd1  mov     [rbp+1B0h+var_158], ecx
0x140291bd4  mov     edx, [rbx+10h]
0x140291bd7  bt      edx, 18h
0x140291bdb  jnb     short loc_140291BE4
0x140291bdd  bts     ecx, 18h
0x140291be1  mov     [rbp+1B0h+var_158], ecx
0x140291be4  mov     eax, [rbx+0Ch]
0x140291be7  test    al, 4
0x140291be9  jz      short loc_140291C03
0x140291beb  mov     eax, edx
0x140291bed  btr     eax, 18h
0x140291bf1  or      [rbx+14h], eax
0x140291bf4  mov     eax, [rbx+14h]
0x140291bf7  not     eax
0x140291bf9  and     eax, edx
0x140291bfb  mov     [rbx+10h], eax
0x140291bfe  xor     ecx, ecx
0x140291c00  mov     [rbp+1B0h+var_158], ecx
0x140291c03  mov     byte ptr [rsp+230h+var_1F0], 0; unsigned __int8
0x140291c08  mov     byte ptr [rsp+230h+var_1F8], 1; unsigned __int8
0x140291c0d  mov     byte ptr [rsp+230h+var_200], 1; unsigned __int8
0x140291c12  mov     dword ptr [rsp+230h+PostIrpRoutine], ecx; unsigned int
0x140291c16  mov     rax, [rbp+1B0h+Irp]
0x140291c1a  mov     [rsp+230h+CompletionRoutine], rax; struct _IRP *
0x140291c1f  xor     r9d, r9d; struct _FCB *
0x140291c22  mov     r8, [rdi+88h]; struct _FCB *
0x140291c29  mov     rdx, rsi; struct _CREATE_CONTEXT *
0x140291c2c  mov     rcx, r14; struct _IRP_CONTEXT *
0x140291c2f  call    ?RefsAccessCheck@@YAXPEAU_IRP_CONTEXT@@PEAU_CREATE_CONTEXT@@PEAU_FCB@@2PEAU_IRP@@KEEE@Z; RefsAccessCheck(_IRP_CONTEXT *,_CREATE_CONTEXT *,_FCB *,_FCB *,_IRP *,ulong,uchar,uchar,uchar)
0x140291c34  mov     eax, [rbx+10h]
0x140291c37  or      [rbx+14h], eax
0x140291c3a  mov     eax, [rbx+14h]
0x140291c3d  bt      eax, 19h
0x140291c41  jnb     short loc_140291C52
0x140291c43  or      eax, 1F01FFh
0x140291c48  mov     [rbx+14h], eax
0x140291c4b  btr     eax, 19h
0x140291c4f  mov     [rbx+14h], eax
0x140291c52  mov     dword ptr [rbx+10h], 0
0x140291c59  mov     rdx, [rdi+88h]; struct _FCB *
0x140291c60  mov     rcx, r14; struct _IRP_CONTEXT *
0x140291c63  call    ?RefsCacheSharedSecurityForCreate@@YAPEAU_SHARED_SECURITY@@PEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsCacheSharedSecurityForCreate(_IRP_CONTEXT *,_FCB *)
0x140291c68  mov     [rbp+1B0h+P], rax
0x140291c6c  mov     ebx, 0A0h
0x140291c71  cmp     [rbp+1B0h+var_1A8], bx
0x140291c75  jnz     short loc_140291C82
0x140291c77  mov     rdx, r14; struct _IRP_CONTEXT *
0x140291c7a  mov     rcx, rdi; this
0x140291c7d  call    ?EnsureDirectoryNormalizedName@IndexSCB@@QEAAXAEAU_IRP_CONTEXT@@@Z; IndexSCB::EnsureDirectoryNormalizedName(_IRP_CONTEXT &)
0x140291c82  mov     rax, [rsi+0C8h]
  ... truncated ...
```
