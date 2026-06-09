# RefsCreateNewFile

- ea: `0x1402986f0`
- end: `0x140299ce9`
- name: `RefsCreateNewFile`
- size: `5625`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, __int64, __int64, __int64, __int16, __int64, __int64)`
- caller_count: `1`
- callee_count: `55`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14030d820`

## callees

- `0x1400298a0`
- `0x140037820`
- `0x140038d4c`
- `0x14005dbd0`
- `0x140076ad0`
- `0x140083e30`
- `0x1400862c0`
- `0x14008b930`
- `0x14008ec60`
- `0x140093d20`
- `0x140095370`
- `0x140099d90`
- `0x14009e59c`
- `0x1400a8498`
- `0x1400b5ac0`
- `0x1400bdcd0`
- `0x1400d0fd8`
- `0x1400d132c`
- `0x1400e6574`
- `0x1400ee6ec`
- `0x1401f3f82`
- `0x1401f3f94`
- `0x1401f3fb0`
- `0x14028cfa0`
- `0x14028d39c`
- `0x14028e7f8`
- `0x140293c2c`
- `0x1402986f0`
- `0x14029b914`
- `0x1402d4318`
- `0x140301fb0`
- `0x140302e10`
- `0x140303400`
- `0x140303818`
- `0x140304230`
- `0x140304a70`
- `0x1403078a0`
- `0x140308440`
- `0x140309cb0`
- `0x14030a7c0`
- `0x1403141f0`
- `0x140322310`
- `0x140322730`
- `0x140322820`
- `0x140322ec0`
- `0x140327bf0`
- `0x140329e20`
- `0x14032a5d0`
- `0x14032ac50`
- `0x140330f04`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140299a15`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140299a8d`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140299af1`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140345d3d`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140345db9`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140345e1e`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140299a15`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140299a8d`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140299af1`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140345d3d`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140345db9`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140345e1e`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x140298a5e`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x140298a5e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140299937`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140345c3c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140299937`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140345c3c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14029994a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140345c4f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14029994a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140345c4f`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140299681`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140299681`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140299974`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140345c81`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140299974`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140345c81`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140299980`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140345c8d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140299980`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140345c8d`
- `ntoskrnl!ExReleaseFastResource` at `0x140299a36`
- `ntoskrnl!ExReleaseFastResource` at `0x140299aaa`
- `ntoskrnl!ExReleaseFastResource` at `0x140299b0e`
- `ntoskrnl!ExReleaseFastResource` at `0x140345d5e`
- `ntoskrnl!ExReleaseFastResource` at `0x140345dd6`
- `ntoskrnl!ExReleaseFastResource` at `0x140345e3b`
- `ntoskrnl!ExReleaseFastResource` at `0x140299a36`
- `ntoskrnl!ExReleaseFastResource` at `0x140299aaa`
- `ntoskrnl!ExReleaseFastResource` at `0x140299b0e`
- `ntoskrnl!ExReleaseFastResource` at `0x140345d5e`
- `ntoskrnl!ExReleaseFastResource` at `0x140345dd6`
- `ntoskrnl!ExReleaseFastResource` at `0x140345e3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140299961`
- `ntoskrnl!ExFreePoolWithTag` at `0x140345c65`
- `ntoskrnl!ExFreePoolWithTag` at `0x140299961`
- `ntoskrnl!ExFreePoolWithTag` at `0x140345c65`

## string_xrefs

- `0x140298979`: `Create.c`
- `0x140298a03`: `Create.c`
- `0x140298ab9`: `Create.c`
- `0x140298ed9`: `Create.c`
- `0x140299b82`: `Create.c`
- `0x140299c06`: `Create.c`
- `0x140299c69`: `Create.c`
- `0x140299ccc`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsCreateNewFile(
        struct CmsTransactionContext **a1,
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
  int v12; // ebx
  __int64 v13; // rdi
  __int64 result; // rax
  int v15; // r15d
  char v16; // dl
  unsigned int v17; // r9d
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax
  _DWORD *v25; // rbx
  unsigned int v26; // ecx
  int v27; // edx
  int v28; // eax
  int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r9
  struct _LCB **v34; // rdx
  struct _FCB *v35; // rdi
  __int64 v36; // rcx
  PMRX_NET_ROOT pNetRoot; // rcx
  __int64 v38; // r8
  __int64 Scb; // rbx
  int v40; // edx
  int v41; // r15d
  unsigned __int16 v42; // dx
  unsigned __int16 StreamChecksumType; // ax
  struct _LIST_ENTRY *v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rcx
  unsigned int v47; // r10d
  bool v48; // dl
  __int64 v49; // rcx
  char v50; // r11
  __int16 v51; // ax
  __int64 v52; // r8
  int v53; // eax
  __int64 v54; // rcx
  __int16 v55; // r8
  int v56; // eax
  int v57; // eax
  int v58; // eax
  char v59; // cl
  int v60; // eax
  __int64 v61; // r8
  char *v62; // rbx
  const struct _UNICODE_STRING *v63; // rdx
  unsigned __int64 CmsKeyLength; // r9
  __int64 v65; // rax
  void *v66; // rsp
  __int64 v67; // r15
  NTSTATUS v68; // ebx
  unsigned int v69; // r8d
  char v70; // al
  __int64 v71; // rax
  struct _SCB **v72; // rbx
  int v73; // ecx
  struct _LCB *v74; // r12
  int v75; // eax
  __int16 v76; // dx
  int v77; // eax
  int v78; // edx
  NTSTATUS v79; // r12d
  struct _SCB *v80; // r15
  __int64 v81; // rcx
  struct _FILE_NAME *v82; // rbx
  unsigned int v83; // r8d
  __int64 v84; // rcx
  PIRP v85; // r12
  unsigned int v86; // r8d
  int v87; // eax
  bool v88; // sf
  __int64 v89; // rax
  struct _FILE_FULL_EA_INFORMATION *MasterIrp; // rdx
  __int64 v91; // rax
  struct IndexSCB *v92; // rbx
  unsigned int v93; // r9d
  __int64 v94; // rax
  _WORD *v95; // r8
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // rcx
  __int64 v99; // rax
  struct _UNICODE_STRING *v100; // rdx
  struct _UNICODE_STRING *v101; // r8
  PWSTR Buffer; // rax
  struct _UNICODE_STRING *v103; // rax
  unsigned int v104; // r8d
  struct _LCB *v105; // r13
  struct _FAST_MUTEX *v106; // rbx
  _DWORD *v107; // r15
  __int64 v109; // r8
  struct _LCB *v110; // r13
  __int64 v111; // r8
  _QWORD *i; // rbx
  struct IndexSCB *v113; // r15
  __int64 v114; // rbx
  __int64 v115; // r8
  __int64 v116; // rbx
  __int64 v117; // [rsp+A8h] [rbp-80h] BYREF
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine; // [rsp+C8h] [rbp-60h]
  POPLOCK_FS_PREPOST_IRP PostIrpRoutine; // [rsp+D0h] [rbp-58h]
  ULONG v120[2]; // [rsp+D8h] [rbp-50h]
  unsigned __int8 *v121; // [rsp+F0h] [rbp-38h]
  char v122; // [rsp+128h] [rbp+0h] BYREF
  unsigned __int8 v123; // [rsp+129h] [rbp+1h] BYREF
  char v124; // [rsp+12Ah] [rbp+2h]
  char v125; // [rsp+12Bh] [rbp+3h]
  unsigned __int16 v126; // [rsp+130h] [rbp+8h] BYREF
  int v127; // [rsp+138h] [rbp+10h] BYREF
  NTSTATUS v128; // [rsp+13Ch] [rbp+14h]
  PIRP Irp; // [rsp+140h] [rbp+18h]
  char v130; // [rsp+148h] [rbp+20h]
  unsigned int v131; // [rsp+14Ch] [rbp+24h]
  BOOL v132; // [rsp+150h] [rbp+28h]
  unsigned int v133; // [rsp+154h] [rbp+2Ch]
  __int64 v134; // [rsp+158h] [rbp+30h]
  PVOID P; // [rsp+160h] [rbp+38h]
  unsigned int v136; // [rsp+168h] [rbp+40h]
  int v137; // [rsp+16Ch] [rbp+44h]
  struct _LCB *v138[2]; // [rsp+178h] [rbp+50h] BYREF
  struct _FCB *Fcb; // [rsp+188h] [rbp+60h]
  struct _LCB *v140; // [rsp+190h] [rbp+68h]
  struct _REFS_FILE_REFERENCE *v141; // [rsp+198h] [rbp+70h] BYREF
  struct IndexSCB *v142; // [rsp+1A0h] [rbp+78h]
  struct _UNICODE_STRING *v143; // [rsp+1A8h] [rbp+80h]
  struct _CREATE_CONTEXT *v144; // [rsp+1B0h] [rbp+88h]
  __int64 v145; // [rsp+1B8h] [rbp+90h] BYREF
  __int128 v146; // [rsp+1C8h] [rbp+A0h] BYREF
  struct _FILE_NAME *v147; // [rsp+1D8h] [rbp+B0h]
  __int64 v148; // [rsp+1E0h] [rbp+B8h]
  struct _IRP_CONTEXT *v149; // [rsp+1E8h] [rbp+C0h]
  struct _UNICODE_STRING *v150; // [rsp+1F0h] [rbp+C8h]
  struct _LCB **v151; // [rsp+1F8h] [rbp+D0h]
  __int64 v152; // [rsp+200h] [rbp+D8h]
  struct _FCB *v153; // [rsp+208h] [rbp+E0h]
  __int64 v154; // [rsp+210h] [rbp+E8h]
  __int64 v155; // [rsp+218h] [rbp+F0h]
  __int64 v156; // [rsp+220h] [rbp+F8h]
  __int128 v157; // [rsp+228h] [rbp+100h] BYREF
  _OWORD v158[2]; // [rsp+238h] [rbp+110h] BYREF
  ULONGLONG v159; // [rsp+258h] [rbp+130h]
  __int128 v160; // [rsp+260h] [rbp+138h]

  v155 = (__int64)&v117;
  v147 = a4;
  v142 = (struct IndexSCB *)a3;
  Irp = a2;
  v149 = (struct _IRP_CONTEXT *)a1;
  v152 = a3;
  *(_QWORD *)&v160 = a5;
  v143 = a6;
  v145 = a7;
  v126 = a8;
  v144 = a9;
  v151 = a10;
  v154 = (__int64)a10;
  v127 = 0;
  v146 = 0;
  v122 = 0;
  v123 = 0;
  v12 = *(unsigned __int16 *)(*((_QWORD *)a9 + 20) + 24LL);
  *((_DWORD *)a1 + 175) = 27;
  v13 = *(_QWORD *)(a3 + 144);
  v134 = v13;
  result = RefsCheckValidAttributeAccess(
             (_DWORD)a1,
             *((_QWORD *)a9 + 20),
             v13,
             0,
             (__int64)&v145,
             (__int64)&v126,
             *((_DWORD *)a9 + 36),
             (__int64)&v127,
             (__int64)&v122);
  v128 = result;
  if ( (int)result < 0 )
    return result;
  v15 = v12;
  v16 = v122;
  if ( v122 )
  {
    if ( (v12 & 0x100) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 113, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225485LL;
      v17 = 8533;
LABEL_32:
      RefsStatusDebug(-1073741811, 0, "Create.c", v17);
      return 3221225485LL;
    }
    v18 = *((_QWORD *)a9 + 25);
    if ( v18 && (*(_BYTE *)(v18 + 2) & 0xD) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 114, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225485LL;
      v17 = 8546;
      goto LABEL_32;
    }
  }
  else
  {
    v19 = *((_QWORD *)a9 + 25);
    if ( v19 )
    {
      if ( *(char *)(v19 + 2) >= 0 )
        LOBYTE(v20) = 0;
      else
        v20 = *(_DWORD *)(v19 + 60);
      if ( (v20 & 1) != 0 )
        v21 = *(_DWORD *)(v19 + 76);
      else
        LOBYTE(v21) = 0;
      if ( (v21 & 1) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            115,
            WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
            3221225485LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          return 3221225485LL;
        v17 = 8557;
        goto LABEL_32;
      }
    }
  }
  v22 = *((_QWORD *)a9 + 20);
  if ( (*(_DWORD *)(v22 + 16) & 0x1000) != 0 && (v12 & 1) != 0 && (*(_BYTE *)(v22 + 2) & 0x40) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 116, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225761LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741535, 0, "Create.c", 0x2178u);
    return 3221225761LL;
  }
  v23 = *(_QWORD *)(a3 + 136);
  v24 = *(_QWORD *)(v23 + 88);
  if ( !*(_QWORD *)(v24 + 248) && *(_QWORD *)(v24 + 256) && (*(_DWORD *)(v23 + 152) & 0x400) != 0 )
  {
    if ( !(unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(*(unsigned int *)(v23 + 156)) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 117, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221226113LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741183, 0, "Create.c", 0x2184u);
      return 3221226113LL;
    }
    v16 = v122;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a3 + 136) + 8LL) & 0x100LL) == 0 || a3 == *(_QWORD *)(v13 + 32) )
  {
    v140 = 0;
    Fcb = 0;
    P = 0;
    v125 = 0;
    LOBYTE(v137) = 0;
    LOBYTE(v13) = 0;
    v132 = v13;
    v141 = 0;
    v148 = v134;
    if ( ((v126 - 128) & 0xFFCF) == 0 && v126 != 144 )
    {
      *((_DWORD *)a9 + 43) |= 0x100u;
      v25 = *(_DWORD **)(*(_QWORD *)(*((_QWORD *)a9 + 20) + 8LL) + 8LL);
      v26 = 4;
      if ( !v16 )
        v26 = 2;
      v136 = v26;
      v27 = v25[4];
      if ( (v27 & 0x1000000) != 0 )
      {
        v26 |= 0x1000000u;
        v136 = v26;
      }
      if ( (v25[3] & 4) != 0 )
      {
        v25[5] |= v27 & 0xFEFFFFFF;
        v25[4] = v27 & ~v25[5];
        v26 = 0;
        v136 = 0;
      }
      RefsAccessCheck((struct _IRP_CONTEXT *)a1, a9, *(struct _FCB **)(a3 + 136), 0, Irp, v26, 1u, 1u, 0);
      v25[5] |= v25[4];
      v28 = v25[5];
      if ( (v28 & 0x2000000) != 0 )
      {
        v29 = v28 | 0x1F01FF;
        v25[5] = v29;
        v25[5] = v29 & 0xFDFFFFFF;
      }
      v25[4] = 0;
      P = RefsCacheSharedSecurityForCreate((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(a3 + 136));
      if ( v126 == 160 )
        IndexSCB::EnsureDirectoryNormalizedName((IndexSCB *)a3, (struct _IRP_CONTEXT *)a1);
      v30 = *((_QWORD *)a9 + 25);
      if ( v30 )
      {
        if ( (*(_BYTE *)(v30 + 2) & 2) != 0 )
        {
          v31 = *(_QWORD *)(v134 + 48);
          if ( v31 )
          {
            RefsAcquireExclusiveScb(a1, v31, 0);
            v123 = 1;
          }
        }
      }
      if ( v122 )
      {
        RefsAllocateObjectId((struct _IRP_CONTEXT *)a1, (struct _REFS_FILE_REFERENCE *)&v146);
      }
      else
      {
        *((_QWORD *)&v146 + 1) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 136) + 88LL) + 256LL);
        *(_QWORD *)&v146 = _InterlockedIncrement64((volatile signed __int64 *)(a3 + 424));
      }
      if ( Irp->Overlay.AllocationSize.QuadPart )
      {
        LOBYTE(v132) = 1;
      }
      else
      {
        v32 = *((_QWORD *)a9 + 25);
        if ( v32 && (*(_BYTE *)(v32 + 2) & 4) != 0 )
          v132 = *(_QWORD *)(v32 + 16) > 0LL;
      }
      *((_DWORD *)a1 + 1) |= 0x10000u;
      PostIrpRoutine = 0;
      if ( v122 )
      {
        *(_OWORD *)v138 = v146;
        CompletionRoutine = 0;
        v33 = 0;
        v34 = v138;
      }
      else
      {
        v33 = (*(unsigned __int8 *)(*((_QWORD *)a9 + 20) + 2LL) >> 1) & 1;
        v157 = v146;
        CompletionRoutine = (POPLOCK_WAIT_COMPLETE_ROUTINE)a3;
        v34 = (struct _LCB **)&v157;
      }
      Fcb = (struct _FCB *)RefsCreateFcb(a1, v34, 17, v33, CompletionRoutine, PostIrpRoutine);
      v35 = Fcb;
      v138[0] = (struct _LCB *)RefsCreateLcb(v36, a3, Fcb, v143, 0);
      v140 = v138[0];
      pNetRoot = v35->pNetRoot;
      if ( pNetRoot[2].pSrvCall || (v38 = 160, !pNetRoot[2].Context) )
        v38 = 128;
      Scb = RefsCreateScb(a1, v35, v38, 0, 0, 0);
      *(_QWORD *)&v146 = Scb;
      v40 = *(_DWORD *)(*(_QWORD *)(a3 + 136) + 152LL) & 0x28000;
      v41 = v40 | v15;
      v131 = v41;
      *((_DWORD *)&v35->1 + 38) |= v40;
      *(_WORD *)(Scb + 258) = *(_WORD *)(a3 + 258);
      v42 = *(_WORD *)(a3 + 260);
      *(_WORD *)(Scb + 260) = v42;
      if ( (*(_BYTE *)(*((_QWORD *)a9 + 20) + 2LL) & 2) != 0 )
      {
        StreamChecksumType = 0;
        *(_WORD *)(Scb + 260) = 0;
      }
      else
      {
        StreamChecksumType = v42;
      }
      if ( (v41 & 0x8000) != 0 && !*(_WORD *)(a3 + 260) )
      {
        StreamChecksumType = RefsGetStreamChecksumType(*(struct _VCB **)(*(_QWORD *)(a3 + 136) + 80LL));
        *(_WORD *)(Scb + 260) = StreamChecksumType;
      }
      if ( StreamChecksumType )
      {
        v41 |= 0x8000u;
        v131 = v41;
        *((_DWORD *)&v35->1 + 38) |= 0x8000u;
      }
      RefsIncrementFcbCloseCount(v35);
      v125 = 1;
      if ( Irp->AssociatedIrp.MasterIrp && ((*(_DWORD *)(*((_QWORD *)a9 + 20) + 16LL) & 0x200) != 0 || (v127 & 2) == 0) )
      {
        RefsCompleteCreateRequest(a1, a9, Irp, 3221225506LL);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            119,
            WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
            3221225506LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741790, 0, "Create.c", 0x22B9u);
        local_unwind_0(v155, &loc_140299B95);
      }
      if ( *((_QWORD *)v35->Header.FileContextSupportPointer + 8) )
      {
        v44 = (struct _LIST_ENTRY *)P;
        *(PKEVENT *)((char *)&v35->pBufferingStateChangeCompletedEvent + 4) = (PKEVENT)*((_QWORD *)P + 1);
        v35->ScavengerFinalizationList.Flink = v44;
        P = 0;
      }
      v45 = *(_QWORD *)(a3 + 136);
      if ( (*(_BYTE *)(v45 + 8) & 8) == 0 )
        RefsUpdateFcbInfoFromDisk((struct _IRP_CONTEXT *)a1, (struct _FCB *)v45, 0);
      RefsReloadSharedSecurityBySecurityIdIfNeeded((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(a3 + 136));
      v131 = v41 & 0xFFFFDFFF;
      v46 = *(_QWORD *)(a3 + 136);
      v47 = v41 & 0xFFFFDFFF | *(_DWORD *)(v46 + 152) & 0x2000;
      v133 = v47;
      v131 = v47;
      v48 = 0;
      v124 = 0;
      if ( v122 && (dword_1402688BC & 1) != 0 )
      {
        v48 = (*(_DWORD *)(v46 + 8) & 0x400000) != 0;
        v124 = v48;
      }
      v49 = *((_QWORD *)a9 + 25);
      v50 = v137;
      if ( v49 )
      {
        v51 = *(_WORD *)(v49 + 2);
        if ( (v51 & 1) != 0 )
          v50 = 1;
        v130 = v50;
        if ( (v51 & 0x10) != 0 )
        {
          v52 = *(_QWORD *)(v49 + 32);
          v141 = (struct _REFS_FILE_REFERENCE *)v52;
          v156 = v52;
          v53 = v127;
          if ( *(_QWORD *)(v52 + 8) == -1 )
          {
            v53 = v127 | 0x40;
            v127 |= 0x40u;
          }
          if ( *(_QWORD *)(v52 + 16) == -1 )
          {
            v53 |= 0x10u;
            v127 = v53;
          }
          if ( *(_QWORD *)(v52 + 24) == -1 )
            v127 = v53 | 0x20;
          *(_WORD *)(v49 + 4) |= 0x10u;
        }
        v54 = *((_QWORD *)a9 + 25);
        v55 = *(_WORD *)(v54 + 2) & 0x80;
        if ( v55 )
          v56 = *(_DWORD *)(v54 + 60);
        else
          LOBYTE(v56) = 0;
        if ( (v56 & 1) != 0 )
          v57 = *(_DWORD *)(v54 + 76);
        else
          LOBYTE(v57) = 0;
        if ( (v57 & 1) == 0 )
          goto LABEL_135;
        if ( (*(_DWORD *)(v54 + 80) & 1) == 0 )
        {
          v48 = 0;
          v124 = 0;
          goto LABEL_141;
        }
        if ( (dword_1402688BC & 1) != 0 )
        {
          v48 = 1;
          v124 = 1;
        }
        else
        {
LABEL_135:
          if ( !v48 )
            goto LABEL_141;
        }
        if ( v55 )
          v58 = *(_DWORD *)(v54 + 60);
        else
          LOBYTE(v58) = 0;
        if ( (v58 & 1) != 0 )
          *(_DWORD *)(v54 + 84) |= 1u;
      }
LABEL_141:
      if ( v122 )
      {
        *(_BYTE *)(Scb + 262) = 4;
        v59 = 4;
      }
      else if ( *(_WORD *)(Scb + 260) )
      {
        *(_BYTE *)(Scb + 262) = 1;
        v59 = 1;
      }
      else if ( v132
             || (v47 & 0x4200) != 0
             || (*(_DWORD *)(*(_QWORD *)(a3 + 136) + 152LL) & 0x4000) != 0
             || (*(unsigned __int8 *)(v134 + 793) | (*(unsigned __int8 *)(v134 + 792) << 8)) < 0x30Bu
             || (unsigned __int8)MsIsVolumeOnSmr(*(_QWORD *)(v134 + 112))
             || ((__int64)v35->spacer.Resource & 0x8104LL) != 0 )
      {
        *(_BYTE *)(Scb + 262) = 0;
        v59 = 0;
      }
      else
      {
        *(_BYTE *)(Scb + 262) = 2;
        v59 = 2;
      }
      v60 = 0;
      if ( v59 == 2 )
        v60 = 4;
      v61 = 0;
      if ( v122 )
        v61 = Scb;
      PostIrpRoutine = (POPLOCK_FS_PREPOST_IRP)v141;
      RefsInitializeFcbStdInfo(a1, v35, v61, v50 & 1 | v60 | (2 * (unsigned int)v48), v47);
      v62 = 0;
      if ( !v122 )
      {
        v141 = 0;
        CmsKeyLength = RefsGetCmsKeyLength(0, v143, &v141);
        v65 = CmsKeyLength + 15;
        if ( CmsKeyLength + 15 <= CmsKeyLength )
          v65 = 0xFFFFFFFFFFFFFF0LL;
        v66 = alloca(v65 & 0xFFFFFFFFFFFFFFF0uLL);
        v62 = &v122;
        RefsInitCmsKey((struct _CmsKey *)&v122, v63, v141, CmsKeyLength);
      }
      v67 = v146;
      v68 = RefsInitializeFileFromDisk(a1, v146, 1, v62);
      v128 = v68;
      if ( v68 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            120,
            WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
            (unsigned int)v68);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(v68, (struct _IRP_CONTEXT *)a1, "Create.c", 0x236Bu);
        RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v68, v69);
        goto LABEL_280;
      }
      v70 = v122;
      if ( v122 || !*(_WORD *)v145 )
      {
        v72 = (struct _SCB **)((char *)a9 + 104);
        *((_QWORD *)a9 + 13) = v67;
      }
      else
      {
        v71 = RefsCreateScb(a1, v35, v126, v145, 0, 0);
        v72 = (struct _SCB **)((char *)a9 + 104);
        *((_QWORD *)a9 + 13) = v71;
        *(_WORD *)(v71 + 258) = *(_WORD *)(v67 + 258);
        *(_WORD *)(*((_QWORD *)a9 + 13) + 260LL) = *(_WORD *)(v67 + 260);
        *(_BYTE *)(*((_QWORD *)a9 + 13) + 262LL) = 6;
        v70 = v122;
      }
      if ( v70 )
      {
        RefsCreateDirectoryIndex(a1, v35);
        v73 = v127;
      }
      else
      {
        v73 = v127;
        if ( (v127 & 2) == 0 )
        {
          LOWORD(v120[0]) = (v133 & 0xFE00) << 6;
          v74 = v138[0];
          RefsCreateDataAttribute((struct _IRP_CONTEXT *)a1, 0, (int)PostIrpRoutine, v120[0], 0);
          *((_DWORD *)a9 + 43) |= 0x200000u;
          v73 = v127;
          goto LABEL_171;
        }
      }
      v74 = v138[0];
LABEL_171:
      v75 = *((_DWORD *)a9 + 36);
      if ( v126 == 160 )
      {
        if ( (v75 & 0x40) != 0 )
        {
          v73 |= 8u;
          v76 = 0;
        }
        else
        {
          v76 = *(_WORD *)v160 - v143->Length;
        }
        v77 = RefsOpenAttribute(
                (struct _IRP **)a1,
                *((_QWORD *)a9 + 20),
                v134,
                v74,
                (__int64)a9,
                v35,
                v76,
                (__int64)&RefsFileNameIndex,
                0xA0u,
                2,
                3,
                1,
                v73,
                0,
                v72,
                (_QWORD *)a9 + 14);
      }
      else
      {
        if ( (v75 & 0x40) != 0 )
          v78 = 0;
        else
          v78 = *(unsigned __int16 *)v160 - v143->Length;
        LOBYTE(v121) = 0;
        v77 = RefsOpenNewAttr((struct _IRP_CONTEXT *)a1, v78, v145, v126, 1, v73, (int)v121, (__int64)a9);
      }
      v128 = v77;
      v79 = v77;
      if ( v77 < 0 )
        goto LABEL_244;
      v80 = *v72;
      if ( !v122 )
      {
        if ( (*((_DWORD *)v80 + 38) & 0x20) == 0 )
          RefsUpdateScbFromAttribute((struct _IRP_CONTEXT *)a1, *v72, 0);
        v81 = *((_QWORD *)a9 + 20);
        if ( (*(_DWORD *)(v81 + 16) & 8) == 0 )
        {
          *(_DWORD *)(*(_QWORD *)(v81 + 48) + 80LL) |= 0x40u;
          if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)a9 + 20) + 48LL) + 80LL) & 2) != 0 )
          {
            if ( *((_BYTE *)v80 + 5) )
              *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a9 + 20) + 48LL) + 48LL) = 1;
          }
        }
        if ( (*((_DWORD *)v80 + 38) & 0x10) != 0 )
        {
          memset(v158, 0, sizeof(v158));
          v159 = 0;
          RefsGetStreamSummary((struct _IRP_CONTEXT *)a1, v80, (struct _SmsStreamSummary *)v158);
          if ( v35->ActualAllocationLength != v159 || *((_QWORD *)&v35->1 + 18) != *((_QWORD *)v80 + 4) )
          {
            v35->ActualAllocationLength = v159;
            *((_QWORD *)&v35->1 + 18) = *((_QWORD *)v80 + 4);
            RefsUpdateStandardInformation((struct _IRP_CONTEXT *)a1, v35);
            *(_DWORD *)(*((_QWORD *)a9 + 14) + 4LL) |= 0x10000u;
          }
        }
      }
      v82 = v147;
      RefsAddLink((struct _IRP_CONTEXT *)a1, v142, v35, v147);
      if ( !v122
        || (v160 = 0,
            v160 = *(_OWORD *)v82,
            RefsBindMinstoreTransaction((struct _IRP_CONTEXT *)a1),
            v68 = MsSetDurableTableObjectParentId(a1[3], (CmsBPlusTable *)v35->InternalSrvOpen[1].SrvOpenKeyList.Blink),
            v128 = v68,
            v68 >= 0) )
      {
        if ( (*((_DWORD *)&v35->1 + 38) & 0x20000000) != 0 )
        {
          *((_DWORD *)&v35->1 + 43) &= 4u;
        }
        else
        {
          *((_DWORD *)&v35->1 + 43) = 0;
          v35->Header.Resource = (PERESOURCE)((unsigned __int64)v35->Header.Resource & ~0x10uLL);
        }
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a9 + 20) + 48LL) + 80LL) &= 0xFFF7CFFF;
        *(_DWORD *)(*((_QWORD *)a9 + 14) + 4LL) &= 0xFD8FFFFF;
        v84 = *((_QWORD *)a9 + 25);
        v85 = Irp;
        if ( !v84 || (*(_BYTE *)(v84 + 2) & 2) == 0 )
          goto LABEL_201;
        RefsSetReparsePointInternal(
          (struct _IRP_CONTEXT *)a1,
          Irp,
          (struct _FCB *)v80,
          *((struct _CCB **)a9 + 14),
          0,
          0,
          0,
          *(_WORD *)(v84 + 6),
          *(PREPARSE_DATA_BUFFER *)(v84 + 8),
          &v123);
        v68 = v87;
        v128 = v87;
        v88 = v87 < 0;
        v89 = *((_QWORD *)a9 + 25);
        if ( !v88 )
        {
          *(_WORD *)(v89 + 4) |= 2u;
          *((_DWORD *)a9 + 43) |= 0x100000u;
          goto LABEL_201;
        }
        if ( (*(_WORD *)(v89 + 2) & 0x100) != 0 )
        {
LABEL_201:
          MasterIrp = (struct _FILE_FULL_EA_INFORMATION *)v85->AssociatedIrp.MasterIrp;
          if ( MasterIrp )
            RefsAddEa(
              (struct _IRP_CONTEXT *)a1,
              MasterIrp,
              *(_DWORD *)(*((_QWORD *)a9 + 20) + 32LL),
              (__int64)&v85->IoStatus);
          v91 = *((_QWORD *)a9 + 25);
          if ( v91 && _bittest16((const signed __int16 *)(v91 + 2), 9u) )
          {
            v92 = v142;
          }
          else
          {
            v92 = v142;
            RefsUpdateFcbTimestamps(*((_QWORD *)v142 + 17), *((_QWORD *)a9 + 14), 2684354576LL);
          }
          if ( ((__int64)v35->spacer.Resource & 4) != 0 )
          {
            RefsSetStreamStationaryAndPreloaded((struct _IRP_CONTEXT *)a1, v80, 1u);
            RefsPrepareForCriticalIo((struct _IRP_CONTEXT *)a1, v85, v80, v93);
          }
          v79 = FsRtlCheckOplockEx((POPLOCK)v92 + 11, v85, 0x10u, 0, 0, 0);
          v128 = v79;
          if ( v79 >= 0 )
          {
            *((_QWORD *)a9 + 12) = v35;
            RefsEncryptionCreateCallback((struct _IRP_CONTEXT *)a1, Irp, *((_QWORD *)v92 + 17), (__int64)a9, 1);
            *((_QWORD *)a9 + 12) = 0;
            RefsPostUsnChange((struct _IRP_CONTEXT *)a1, *((struct _FCB **)a9 + 13), *((_DWORD *)a9 + 43), 0);
            v94 = *((_QWORD *)a9 + 25);
            if ( v94 && *((int *)a9 + 43) < 0 )
              *(_WORD *)(v94 + 4) |= 0x800u;
            v95 = (_WORD *)*((_QWORD *)a9 + 13);
            if ( *v95 == 2051 && !v95[196] && *((_WORD *)v92 + 196) )
              RefsUpdateNormalizedName(a1, v92, v95, v147);
            if ( a1[76] )
            {
              RefsWriteUsnJournalChanges((struct _IRP_CONTEXT *)a1);
              RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
            }
            v96 = *((_QWORD *)a9 + 25);
            if ( v96 )
            {
              if ( (*(_BYTE *)(v96 + 2) & 0x10) != 0 )
              {
                **(_QWORD **)(v96 + 32) = v35->Context2;
                *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a9 + 25) + 32LL) + 8LL) = *((_QWORD *)&v35->1 + 16);
                *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a9 + 25) + 32LL) + 16LL) = *((_QWORD *)&v35->1 + 14);
                *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a9 + 25) + 32LL) + 24LL) = *((_QWORD *)&v35->1 + 15);
                *(_WORD *)(*((_QWORD *)a9 + 25) + 4LL) |= 0x100u;
              }
              v97 = *((_QWORD *)a9 + 25);
              if ( *(_WORD *)v97 >= 0x2Cu )
              {
                *(_DWORD *)(v97 + 40) = *((_DWORD *)&v35->1 + 38);
                *(_WORD *)(*((_QWORD *)a9 + 25) + 4LL) |= 0x200u;
              }
              v98 = *((_QWORD *)a9 + 25);
              if ( *(_WORD *)v98 >= 0x38u )
              {
                *(_QWORD *)(v98 + 48) = *(_QWORD *)&v35->FcbTableEntry.NodeTypeCode;
                *(_WORD *)(*((_QWORD *)a9 + 25) + 4LL) |= 0x1000u;
              }
            }
            if ( (*((_DWORD *)a9 + 36) & 0x40) == 0 )
            {
              v99 = *((_QWORD *)a9 + 25);
              if ( !v99 || !_bittest16((const signed __int16 *)(v99 + 2), 0xAu) )
              {
                v100 = 0;
                v150 = 0;
                v101 = (struct _UNICODE_STRING *)*((_QWORD *)a9 + 14);
                Buffer = v101[4].Buffer;
                if ( Buffer )
                {
                  v103 = (struct _UNICODE_STRING *)(*((_QWORD *)Buffer + 3) + 392LL);
                  if ( v103->Length )
                    v100 = v103;
                  v150 = v100;
                }
                RefsReportDirNotify(
                  (struct _IRP_CONTEXT *)((unsigned int)(v122 != 0) + 1),
                  (struct _VCB *)v35->Header.FileContextSupportPointer,
                  v101 + 1,
                  v101[2].Length,
                  0,
                  v100,
                  (v122 != 0) + 1,
                  1u,
                  *((struct _FCB **)v92 + 17));
              }
            }
            if ( (*((_DWORD *)&v35->1 + 38) & 0x20000000) != 0 && (*((_DWORD *)&v35->1 + 43) & 4) != 0 )
              *((_DWORD *)&v35->1 + 43) &= 4u;
            else
              *((_DWORD *)&v35->1 + 43) = 0;
            v104 = *((_DWORD *)a9 + 19);
            v105 = v138[0];
            if ( v104 )
              RefsInsertPrefixHashEntry((struct _IRP_CONTEXT *)a1, v138[0], v104, *((_DWORD *)a9 + 18));
            else
              RefsInsertLcbInPrefixHash((struct _IRP_CONTEXT *)a1, v138[0]);
            Irp->IoStatus.Information = 2;
            goto LABEL_245;
          }
LABEL_244:
          v105 = v138[0];
LABEL_245:
          v106 = (struct _FAST_MUTEX *)v134;
          if ( v123 )
            RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*(_QWORD *)(v134 + 48) + 136LL));
          RefsDecrementFcbCloseCount(v35);
          v107 = P;
          if ( P )
          {
            KeEnterGuardedRegion();
            ExAcquireFastMutexUnsafe(v106 + 13);
            if ( (*v107)-- == 1 )
              ExFreePoolWithTag(v107, 0);
            ExReleaseFastMutexUnsafe(v106 + 13);
            KeLeaveGuardedRegion();
          }
          if ( v79 < 0 )
          {
            RefsBackoutFailedOpens(
              (struct _IRP_CONTEXT *)a1,
              *(PFILE_OBJECT *)(*((_QWORD *)a9 + 20) + 48LL),
              v35,
              *((struct _SCB **)a9 + 13),
              (__int64)a9 + 112);
            *(_OWORD *)((char *)&v35->1 + 104) = 0;
            *(_OWORD *)((char *)&v35->1 + 120) = 0;
            *(_OWORD *)((char *)&v35->1 + 136) = 0;
            *(_OWORD *)((char *)&v35->1 + 152) = 0;
            v35->SrvOpenListVersion = 0;
            v110 = v138[0];
            if ( v138[0] )
            {
              RefsRemovePrefixHashEntry(v138[0]);
              *((_DWORD *)v110 + 1) = *((_DWORD *)v110 + 1) & 0xFFFFFFBD | 2;
              *((_DWORD *)v110 + 19) = 0;
            }
            v35->Header.Resource = (PERESOURCE)((unsigned __int64)v35->Header.Resource & ~8uLL);
            LOBYTE(v109) = 1;
            ExAcquireFastResourceExclusive((char *)a1[8] + 624, 0, v109);
            v35->Header.Resource = (PERESOURCE)((unsigned __int64)v35->Header.Resource | 0x2000001);
            ExReleaseFastResource((char *)a1[8] + 624, 0);
            a1[1] = (struct CmsTransactionContext *)((unsigned __int64)a1[1] | 0x2000000000LL);
            for ( i = &v35->Header.FastMutex->Count; i != &v35->spacer.FastMutex; i = (_QWORD *)*i )
              RefsMarkScbAsDeleted(i - 15);
            *((_QWORD *)a9 + 13) = 0;
            v113 = v142;
            v114 = *((_QWORD *)v142 + 17);
            LOBYTE(v111) = 1;
            ExAcquireFastResourceExclusive(*(_QWORD *)(v114 + 80) + 624LL, 0, v111);
            _InterlockedIncrement((volatile signed __int32 *)(v114 + 24));
            ExReleaseFastResource(*(_QWORD *)(v114 + 80) + 624LL, 0);
            v153 = v35;
            if ( (unsigned __int8)RefsTeardownStructures(a1, v35, 0) )
            {
              v35 = 0;
              v105 = 0;
            }
            else
            {
              v105 = v138[0];
            }
            v116 = *((_QWORD *)v113 + 17);
            LOBYTE(v115) = 1;
            ExAcquireFastResourceExclusive(*(_QWORD *)(v116 + 80) + 624LL, 0, v115);
            _InterlockedDecrement((volatile signed __int32 *)(v116 + 24));
            ExReleaseFastResource(*(_QWORD *)(v116 + 80) + 624LL, 0);
          }
          if ( v35 && v105 )
          {
            *v151 = v105;
            *((_QWORD *)a9 + 12) = v35;
          }
          return (unsigned int)v79;
        }
LABEL_287:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            122,
            WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
            (unsigned int)v68);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(v68, (struct _IRP_CONTEXT *)a1, "Create.c", 0x246Bu);
        RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v68, v86);
        __debugbreak();
        JUMPOUT(0x140299CE9LL);
      }
LABEL_280:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          121,
          WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
          (unsigned int)v68);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(v68, (struct _IRP_CONTEXT *)a1, "Create.c", 0x2424u);
      RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v68, v83);
      goto LABEL_287;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 118, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225506LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741790, 0, "Create.c", 0x2190u);
  return 3221225506LL;
}

```

## disassembly

```asm
0x1402986f0  push    rbp
0x1402986f2  push    rbx
0x1402986f3  push    rsi
0x1402986f4  push    rdi
0x1402986f5  push    r12
0x1402986f7  push    r13
0x1402986f9  push    r14
0x1402986fb  push    r15
0x1402986fd  sub     rsp, 1D8h
0x140298704  lea     rbp, [rsp+80h]
0x14029870c  mov     rax, cs:__security_cookie
0x140298713  xor     rax, rbp
0x140298716  mov     [rbp+190h+var_48], rax
0x14029871d  mov     [rbp+190h+var_A0], rsp
0x140298724  mov     [rbp+190h+var_E0], r9
0x14029872b  mov     r12, r8
0x14029872e  mov     [rbp+190h+var_118], r8
0x140298732  mov     [rbp+190h+Irp], rdx
0x140298736  mov     r14, rcx
0x140298739  mov     [rbp+190h+var_D0], rcx
0x140298740  mov     [rbp+190h+var_B8], r8
0x140298747  mov     rax, [rbp+190h+arg_20]
0x14029874e  mov     qword ptr [rbp+190h+var_58], rax
0x140298755  mov     rax, [rbp+190h+arg_28]
0x14029875c  mov     [rbp+190h+var_110], rax
0x140298763  mov     rax, [rbp+190h+arg_30]
0x14029876a  mov     [rbp+190h+var_100], rax
0x140298771  movzx   eax, [rbp+190h+arg_38]
0x140298778  mov     [rbp+190h+var_188], ax
0x14029877c  mov     rsi, [rbp+190h+arg_40]
0x140298783  mov     [rbp+190h+var_108], rsi
0x14029878a  mov     rax, [rbp+190h+arg_48]
0x140298791  mov     [rbp+190h+var_C0], rax
0x140298798  mov     [rbp+190h+var_A8], rax
0x14029879f  mov     [rbp+190h+var_180], 0
0x1402987a6  xorps   xmm0, xmm0
0x1402987a9  movups  [rbp+190h+var_F0], xmm0
0x1402987b0  mov     [rbp+190h+var_190], 0
0x1402987b4  mov     [rbp+190h+var_18F], 0
0x1402987b8  mov     rax, [rsi+0A0h]
0x1402987bf  movzx   ebx, word ptr [rax+18h]
0x1402987c3  mov     dword ptr [rcx+2BCh], 1Bh
0x1402987cd  mov     rdi, [r8+90h]
0x1402987d4  mov     [rbp+190h+var_160], rdi
0x1402987d8  lea     rax, [rbp+190h+var_190]
0x1402987dc  mov     [rsp+210h+var_1D0], rax
0x1402987e1  lea     rax, [rbp+190h+var_180]
0x1402987e5  mov     qword ptr [rsp+210h+var_1D8], rax
0x1402987ea  mov     eax, [rsi+90h]
0x1402987f0  mov     [rsp+210h+var_1E0], eax
0x1402987f4  lea     rax, [rbp+190h+var_188]
0x1402987f8  mov     [rsp+210h+PostIrpRoutine], rax
0x1402987fd  lea     rax, [rbp+190h+var_100]
0x140298804  mov     [rsp+210h+CompletionRoutine], rax
0x140298809  xor     r9d, r9d
0x14029880c  mov     r8, rdi
0x14029880f  mov     rdx, [rsi+0A0h]
0x140298816  call    RefsCheckValidAttributeAccess
0x14029881b  mov     [rbp+190h+var_17C], eax
0x14029881e  test    eax, eax
0x140298820  js      loc_140299B9A
0x140298826  mov     r15d, ebx
0x140298829  movzx   edx, [rbp+190h+var_190]
0x14029882d  test    dl, dl
0x14029882f  jz      loc_1402988FF
0x140298835  mov     r13d, 100h
0x14029883b  test    r13d, ebx
0x14029883e  jz      short loc_140298894
0x140298840  lea     rax, WPP_GLOBAL_Control
0x140298847  mov     rcx, cs:WPP_GLOBAL_Control
0x14029884e  cmp     rcx, rax
0x140298851  jz      short loc_14029887A
0x140298853  test    [rcx+2Ch], r13d
0x140298857  jz      short loc_14029887A
0x140298859  cmp     byte ptr [rcx+29h], 4
0x14029885d  jb      short loc_14029887A
0x14029885f  mov     edx, 71h ; 'q'
0x140298864  mov     r9d, 0C000000Dh
0x14029886a  lea     r8, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids
0x140298871  mov     rcx, [rcx+18h]
0x140298875  call    WPP_SF_d
0x14029887a  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140298881  test    al, al
0x140298883  jz      loc_14029898C
0x140298889  mov     r9d, 2155h
0x14029888f  jmp     loc_140298979
0x140298894  mov     rax, [rsi+0C8h]
0x14029889b  test    rax, rax
0x14029889e  jz      loc_14029899C
0x1402988a4  test    byte ptr [rax+2], 0Dh
0x1402988a8  jz      loc_14029899C
0x1402988ae  lea     rax, WPP_GLOBAL_Control
0x1402988b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1402988bc  cmp     rcx, rax
0x1402988bf  jz      short loc_1402988E8
0x1402988c1  test    [rcx+2Ch], r13d
0x1402988c5  jz      short loc_1402988E8
0x1402988c7  cmp     byte ptr [rcx+29h], 4
0x1402988cb  jb      short loc_1402988E8
0x1402988cd  mov     edx, 72h ; 'r'
0x1402988d2  mov     r9d, 0C000000Dh
0x1402988d8  lea     r8, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids
0x1402988df  mov     rcx, [rcx+18h]
0x1402988e3  call    WPP_SF_d
0x1402988e8  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402988ef  test    al, al
0x1402988f1  jz      loc_14029898C
0x1402988f7  mov     r9d, 2162h
0x1402988fd  jmp     short loc_140298979
0x1402988ff  mov     rcx, [rsi+0C8h]
0x140298906  test    rcx, rcx
0x140298909  jz      loc_140298996
0x14029890f  movzx   eax, byte ptr [rcx+2]
0x140298913  test    al, al
0x140298915  jns     short loc_14029891C
0x140298917  mov     eax, [rcx+3Ch]
0x14029891a  jmp     short loc_14029891E
0x14029891c  xor     eax, eax
0x14029891e  test    al, 1
0x140298920  jz      short loc_140298927
0x140298922  mov     eax, [rcx+4Ch]
0x140298925  jmp     short loc_140298929
0x140298927  xor     eax, eax
0x140298929  test    al, 1
0x14029892b  jz      short loc_140298996
0x14029892d  lea     rax, WPP_GLOBAL_Control
0x140298934  mov     rcx, cs:WPP_GLOBAL_Control
0x14029893b  cmp     rcx, rax
0x14029893e  jz      short loc_140298968
0x140298940  bt      dword ptr [rcx+2Ch], 8
0x140298945  jnb     short loc_140298968
0x140298947  cmp     byte ptr [rcx+29h], 4
0x14029894b  jb      short loc_140298968
0x14029894d  mov     edx, 73h ; 's'
0x140298952  mov     r9d, 0C000000Dh
0x140298958  lea     r8, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids
0x14029895f  mov     rcx, [rcx+18h]
0x140298963  call    WPP_SF_d
0x140298968  movzx   ecx, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14029896f  test    cl, cl
0x140298971  jz      short loc_14029898C
0x140298973  mov     r9d, 216Dh; unsigned int
0x140298979  lea     r8, aCreateC; "Create.c"
0x140298980  xor     edx, edx; struct _IRP_CONTEXT *
0x140298982  mov     ecx, 0C000000Dh; Status
0x140298987  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14029898c  mov     eax, 0C000000Dh
0x140298991  jmp     loc_140299B9A
0x140298996  mov     r13d, 100h
0x14029899c  mov     rcx, [rsi+0A0h]
0x1402989a3  test    dword ptr [rcx+10h], 1000h
0x1402989aa  jz      short loc_140298A20
0x1402989ac  test    r15b, 1
0x1402989b0  jz      short loc_140298A20
0x1402989b2  test    byte ptr [rcx+2], 40h
0x1402989b6  jnz     short loc_140298A20
0x1402989b8  lea     rax, WPP_GLOBAL_Control
0x1402989bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1402989c6  cmp     rcx, rax
0x1402989c9  jz      short loc_1402989F2
0x1402989cb  test    [rcx+2Ch], r13d
0x1402989cf  jz      short loc_1402989F2
0x1402989d1  cmp     byte ptr [rcx+29h], 4
0x1402989d5  jb      short loc_1402989F2
0x1402989d7  mov     edx, 74h ; 't'
0x1402989dc  mov     r9d, 0C0000121h
0x1402989e2  lea     r8, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids
0x1402989e9  mov     rcx, [rcx+18h]
0x1402989ed  call    WPP_SF_d
0x1402989f2  movzx   ecx, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402989f9  test    cl, cl
0x1402989fb  jz      short loc_140298A16
0x1402989fd  mov     r9d, 2178h; unsigned int
0x140298a03  lea     r8, aCreateC; "Create.c"
0x140298a0a  xor     edx, edx; struct _IRP_CONTEXT *
0x140298a0c  mov     ecx, 0C0000121h; Status
0x140298a11  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140298a16  mov     eax, 0C0000121h
0x140298a1b  jmp     loc_140299B9A
0x140298a20  mov     rcx, [r12+88h]
0x140298a28  mov     rax, [rcx+58h]
0x140298a2c  cmp     qword ptr [rax+0F8h], 0
0x140298a34  jnz     loc_140298ADA
0x140298a3a  cmp     qword ptr [rax+100h], 0
0x140298a42  jz      loc_140298ADA
0x140298a48  test    dword ptr [rcx+98h], 400h
0x140298a52  jz      loc_140298ADA
0x140298a58  mov     ecx, [rcx+9Ch]
0x140298a5e  call    cs:__imp_FsRtlIsNonEmptyDirectoryReparsePointAllowed
0x140298a65  nop     dword ptr [rax+rax+00h]
0x140298a6a  test    al, al
0x140298a6c  jnz     short loc_140298AD6
0x140298a6e  lea     rax, WPP_GLOBAL_Control
0x140298a75  mov     rcx, cs:WPP_GLOBAL_Control
0x140298a7c  cmp     rcx, rax
0x140298a7f  jz      short loc_140298AA8
0x140298a81  test    [rcx+2Ch], r13d
0x140298a85  jz      short loc_140298AA8
0x140298a87  cmp     byte ptr [rcx+29h], 4
0x140298a8b  jb      short loc_140298AA8
0x140298a8d  mov     edx, 75h ; 'u'
0x140298a92  mov     r9d, 0C0000281h
0x140298a98  lea     r8, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids
0x140298a9f  mov     rcx, [rcx+18h]
0x140298aa3  call    WPP_SF_d
0x140298aa8  movzx   ecx, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140298aaf  test    cl, cl
0x140298ab1  jz      short loc_140298ACC
0x140298ab3  mov     r9d, 2184h; unsigned int
0x140298ab9  lea     r8, aCreateC; "Create.c"
0x140298ac0  xor     edx, edx; struct _IRP_CONTEXT *
0x140298ac2  mov     ecx, 0C0000281h; Status
0x140298ac7  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140298acc  mov     eax, 0C0000281h
0x140298ad1  jmp     loc_140299B9A
0x140298ad6  movzx   edx, [rbp+190h+var_190]
0x140298ada  mov     rax, [r12+88h]
0x140298ae2  mov     ecx, [rax+8]
0x140298ae5  test    r13, rcx
0x140298ae8  jz      short loc_140298AF4
0x140298aea  cmp     r12, [rdi+20h]
0x140298aee  jnz     loc_140299B37
0x140298af4  xor     r9d, r9d
0x140298af7  mov     [rbp+190h+var_128], r9
0x140298afb  mov     [rbp+190h+var_130], r9
0x140298aff  mov     [rbp+190h+P], r9
0x140298b03  mov     [rbp+190h+var_18D], r9b
0x140298b07  mov     byte ptr [rbp+190h+var_14C], r9b
0x140298b0b  xor     dil, dil
0x140298b0e  mov     [rbp+190h+var_168], edi
0x140298b11  mov     [rbp+190h+var_120], r9
0x140298b15  mov     rax, [rbp+190h+var_160]
0x140298b19  mov     [rbp+190h+var_D8], rax
0x140298b20  mov     r8d, 80h
0x140298b26  movzx   ecx, [rbp+190h+var_188]
0x140298b2a  movzx   eax, cx
0x140298b2d  sub     ax, r8w
0x140298b31  mov     r8d, 0FFCFh
0x140298b37  test    r8w, ax
0x140298b3b  jnz     loc_140299B37
0x140298b41  mov     eax, 90h
0x140298b46  cmp     cx, ax
0x140298b49  jz      loc_140299B37
0x140298b4f  or      [rsi+0ACh], r13d
0x140298b56  mov     rax, [rsi+0A0h]
0x140298b5d  mov     rcx, [rax+8]
0x140298b61  mov     rbx, [rcx+8]
0x140298b65  mov     ecx, 4
0x140298b6a  mov     eax, 2
0x140298b6f  test    dl, dl
0x140298b71  cmovz   ecx, eax
0x140298b74  mov     [rbp+190h+var_150], ecx
0x140298b77  mov     edx, [rbx+10h]
0x140298b7a  bt      edx, 18h
0x140298b7e  jnb     short loc_140298B87
0x140298b80  bts     ecx, 18h
0x140298b84  mov     [rbp+190h+var_150], ecx
0x140298b87  mov     eax, [rbx+0Ch]
0x140298b8a  test    al, 4
0x140298b8c  jz      short loc_140298BA7
0x140298b8e  mov     eax, edx
0x140298b90  btr     eax, 18h
0x140298b94  or      [rbx+14h], eax
0x140298b97  mov     eax, [rbx+14h]
0x140298b9a  not     eax
0x140298b9c  and     eax, edx
0x140298b9e  mov     [rbx+10h], eax
0x140298ba1  mov     ecx, r9d
0x140298ba4  mov     [rbp+190h+var_150], ecx
0x140298ba7  mov     byte ptr [rsp+210h+var_1D0], 0; unsigned __int8
0x140298bac  mov     byte ptr [rsp+210h+var_1D8], 1; unsigned __int8
0x140298bb1  mov     byte ptr [rsp+210h+var_1E0], 1; unsigned __int8
0x140298bb6  mov     dword ptr [rsp+210h+PostIrpRoutine], ecx; unsigned int
0x140298bba  mov     rax, [rbp+190h+Irp]
0x140298bbe  mov     [rsp+210h+CompletionRoutine], rax; struct _IRP *
0x140298bc3  xor     r9d, r9d; struct _FCB *
0x140298bc6  mov     r8, [r12+88h]; struct _FCB *
0x140298bce  mov     rdx, rsi; struct _CREATE_CONTEXT *
0x140298bd1  mov     rcx, r14; struct _IRP_CONTEXT *
0x140298bd4  call    ?RefsAccessCheck@@YAXPEAU_IRP_CONTEXT@@PEAU_CREATE_CONTEXT@@PEAU_FCB@@2PEAU_IRP@@KEEE@Z; RefsAccessCheck(_IRP_CONTEXT *,_CREATE_CONTEXT *,_FCB *,_FCB *,_IRP *,ulong,uchar,uchar,uchar)
0x140298bd9  mov     eax, [rbx+10h]
0x140298bdc  or      [rbx+14h], eax
0x140298bdf  mov     eax, [rbx+14h]
0x140298be2  bt      eax, 19h
0x140298be6  jnb     short loc_140298BF7
0x140298be8  or      eax, 1F01FFh
0x140298bed  mov     [rbx+14h], eax
0x140298bf0  btr     eax, 19h
0x140298bf4  mov     [rbx+14h], eax
0x140298bf7  mov     dword ptr [rbx+10h], 0
0x140298bfe  mov     rdx, [r12+88h]; struct _FCB *
0x140298c06  mov     rcx, r14; struct _IRP_CONTEXT *
0x140298c09  call    ?RefsCacheSharedSecurityForCreate@@YAPEAU_SHARED_SECURITY@@PEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsCacheSharedSecurityForCreate(_IRP_CONTEXT *,_FCB *)
0x140298c0e  mov     [rbp+190h+P], rax
0x140298c12  mov     eax, 0A0h
0x140298c17  cmp     [rbp+190h+var_188], ax
0x140298c1b  jnz     short loc_140298C28
0x140298c1d  mov     rdx, r14; struct _IRP_CONTEXT *
0x140298c20  mov     rcx, r12; this
0x140298c23  call    ?EnsureDirectoryNormalizedName@IndexSCB@@QEAAXAEAU_IRP_CONTEXT@@@Z; IndexSCB::EnsureDirectoryNormalizedName(_IRP_CONTEXT &)
  ... truncated ...
```
