# RefsZeroRangeInStream(_IRP_CONTEXT *,_FILE_OBJECT *,_SCB *,__int64 *,__int64)

- ea: `0x140295fb0`
- end: `0x140297339`
- name: `?RefsZeroRangeInStream@@YAJPEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAU_SCB@@PEA_J_J@Z`
- size: `5001`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct _FILE_OBJECT *, struct _SCB *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `38`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1402c8958`

## callees

- `0x140009d5c`
- `0x140011c60`
- `0x14001b59c`
- `0x1400298a0`
- `0x140037820`
- `0x140075c94`
- `0x140075ff0`
- `0x140076060`
- `0x140076ad0`
- `0x1400862c0`
- `0x140088990`
- `0x1400889f0`
- `0x140089680`
- `0x1400921a0`
- `0x140095370`
- `0x140097c50`
- `0x140097fe0`
- `0x1400a79f8`
- `0x1400b5ba0`
- `0x1400cea34`
- `0x1400d0fd8`
- `0x1400e5d88`
- `0x1400e6038`
- `0x1400e6488`
- `0x140112064`
- `0x1401f4400`
- `0x140294acc`
- `0x1402950e4`
- `0x140295fb0`
- `0x140297340`
- `0x140302e10`
- `0x1403040f0`
- `0x140304230`
- `0x140306290`
- `0x140332094`
- `0x140333e98`
- `0x14033ae88`
- `0x14033afa0`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x140296f07`
- `ntoskrnl!CcFlushCache` at `0x140296f07`
- `ntoskrnl!CcMdlWriteComplete` at `0x140296bb1`
- `ntoskrnl!CcMdlWriteComplete` at `0x140296d62`
- `ntoskrnl!CcMdlWriteComplete` at `0x1403457b0`
- `ntoskrnl!CcMdlWriteComplete` at `0x1403457e8`
- `ntoskrnl!CcMdlWriteComplete` at `0x140296bb1`
- `ntoskrnl!CcMdlWriteComplete` at `0x140296d62`
- `ntoskrnl!CcMdlWriteComplete` at `0x1403457b0`
- `ntoskrnl!CcMdlWriteComplete` at `0x1403457e8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140296b78`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140296d25`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140296b78`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140296d25`
- `ntoskrnl!CcPrepareMdlWrite` at `0x140296b42`
- `ntoskrnl!CcPrepareMdlWrite` at `0x140296cf2`
- `ntoskrnl!CcPrepareMdlWrite` at `0x140296b42`
- `ntoskrnl!CcPrepareMdlWrite` at `0x140296cf2`
- `ntoskrnl!CcPurgeCacheSection` at `0x140296ddf`
- `ntoskrnl!CcPurgeCacheSection` at `0x140296e5c`
- `ntoskrnl!CcPurgeCacheSection` at `0x140296ddf`
- `ntoskrnl!CcPurgeCacheSection` at `0x140296e5c`

## pseudocode

```c
__int64 __fastcall RefsZeroRangeInStream(
        struct _IRP_CONTEXT *a1,
        struct _FILE_OBJECT *a2,
        struct _SCB *a3,
        __int64 *a4,
        __int64 a5)
{
  unsigned int *v5; // r12
  struct _FILE_OBJECT *v7; // r15
  __int64 v9; // r13
  int v10; // ebx
  NTSTATUS valid; // edi
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // rcx
  unsigned int v15; // ebx
  __int64 v16; // r9
  __int64 v17; // rcx
  PDEVICE_OBJECT v18; // rcx
  unsigned int v19; // r9d
  int v20; // eax
  __int64 v21; // rcx
  __int16 v22; // ax
  __int64 *v23; // r8
  unsigned int v24; // r9d
  __int64 v25; // rdx
  __int64 v26; // rax
  int v27; // eax
  struct _IRP *v28; // rdx
  unsigned __int8 v29; // r9
  int v30; // ecx
  __int64 v31; // r9
  unsigned __int64 v32; // r15
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rax
  signed __int64 v37; // r13
  __int64 v38; // r12
  __int64 v39; // rcx
  __int64 v40; // r15
  int v41; // r13d
  __int64 v42; // rax
  char v43; // cl
  __int64 v44; // r13
  unsigned __int64 v45; // r15
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r15
  __int64 v49; // r8
  __int64 v50; // rax
  LONGLONG v51; // r15
  unsigned int v52; // r8d
  PVOID v53; // rax
  __int64 v54; // r13
  unsigned int v55; // r8d
  PVOID MappedSystemVa; // rax
  __int64 v57; // r12
  __int64 v58; // r12
  SECTION_OBJECT_POINTERS *v59; // rcx
  struct _IRP *v60; // rdx
  __int64 v61; // r13
  unsigned __int64 v62; // rcx
  __int64 v63; // r12
  __int64 v64; // rdi
  unsigned int v65; // r8d
  unsigned __int8 v66; // r8
  int v67; // r9d
  NTSTATUS v69; // ebx
  unsigned int v70; // r8d
  PIO_STATUS_BLOCK IoStatus; // [rsp+58h] [rbp-1E8h]
  int v72; // [rsp+7Ch] [rbp-1C4h] BYREF
  unsigned __int8 v73[4]; // [rsp+80h] [rbp-1C0h] BYREF
  unsigned int v74; // [rsp+84h] [rbp-1BCh]
  __int64 v75; // [rsp+88h] [rbp-1B8h]
  union _LARGE_INTEGER v76; // [rsp+90h] [rbp-1B0h] BYREF
  PMDL MdlChain; // [rsp+98h] [rbp-1A8h] BYREF
  int v78; // [rsp+A0h] [rbp-1A0h]
  unsigned int v79; // [rsp+A4h] [rbp-19Ch]
  __int64 QuadPart; // [rsp+A8h] [rbp-198h]
  union _LARGE_INTEGER FileOffset; // [rsp+B0h] [rbp-190h] BYREF
  __int64 v82; // [rsp+B8h] [rbp-188h]
  __int64 v83; // [rsp+C0h] [rbp-180h]
  int v84; // [rsp+C8h] [rbp-178h]
  __int64 v85; // [rsp+D0h] [rbp-170h]
  __int64 v86; // [rsp+D8h] [rbp-168h]
  __int64 v87; // [rsp+E0h] [rbp-160h]
  unsigned __int64 v88; // [rsp+E8h] [rbp-158h] BYREF
  __int64 v89; // [rsp+F0h] [rbp-150h]
  __int64 v90; // [rsp+F8h] [rbp-148h]
  __int64 v91; // [rsp+100h] [rbp-140h]
  __int128 v92; // [rsp+108h] [rbp-138h] BYREF
  __int64 v93; // [rsp+118h] [rbp-128h]
  struct _SCB *v94; // [rsp+120h] [rbp-120h]
  __int64 v95; // [rsp+128h] [rbp-118h] BYREF
  __int64 v96; // [rsp+130h] [rbp-110h]
  __int128 v97; // [rsp+138h] [rbp-108h]
  struct _IO_STATUS_BLOCK v98; // [rsp+148h] [rbp-F8h] BYREF
  _QWORD v99[8]; // [rsp+158h] [rbp-E8h] BYREF
  __int128 v100; // [rsp+198h] [rbp-A8h] BYREF
  _BYTE v101[96]; // [rsp+1A8h] [rbp-98h] BYREF

  v5 = (unsigned int *)a4;
  v7 = a2;
  v9 = a5;
  v10 = 0;
  valid = 0;
  v72 = 0;
  v89 = -1;
  v76.QuadPart = 0;
  QuadPart = 0;
  v83 = 0;
  v92 = 0;
  memset(v101, 0, 0x58u);
  v78 = 0;
  v95 = 0;
  v96 = 0;
  v91 = 0;
  MdlChain = 0;
  v98 = 0;
  MsInitializeFastResourceOwnerEntry(v101);
  while ( 1 )
  {
    if ( *((_QWORD *)a3 + 2) )
    {
      if ( *((_QWORD *)a1 + 7) )
        goto LABEL_22;
      if ( (v10 & 4) != 0 )
        goto LABEL_19;
      if ( *(_QWORD *)(*((_QWORD *)a3 + 31) + 8LL) )
        goto LABEL_19;
      v12 = *((unsigned int *)a3 + 38);
      if ( (*((_DWORD *)a3 + 38) & 8) != 0 && (v12 & 0x40) == 0 )
        goto LABEL_19;
      if ( (v12 & 0x10) != 0 )
      {
        v12 = *(_QWORD *)(*((_QWORD *)a3 + 17) + 8LL) & 0x40000100LL;
        if ( v12 == 0x40000000 )
          goto LABEL_19;
        v12 = *((unsigned int *)a3 + 38);
      }
      if ( (v12 & 0x20) != 0 )
      {
        v99[2] = a3;
        RefsAcquirePagingFastResourceShared(v12, a3, v101);
        v15 = v10 & 0xFFFFFFFD;
        if ( *(_QWORD *)(*((_QWORD *)a3 + 31) + 8LL)
          || (v14 = *((unsigned int *)a3 + 38), (*((_DWORD *)a3 + 38) & 8) != 0) && (v14 & 0x40) == 0
          || (v14 & 0x20) == 0
          || (v14 & 0x10) != 0 && _FCB::HasPurgeableEAs(*((_FCB **)a3 + 17)) )
        {
          v99[3] = a3;
          RefsReleasePagingFastResource(v14, a3, v101);
          v99[4] = a3;
          LOBYTE(v16) = 1;
          RefsAcquirePagingFastResourceExclusive(v17, a3, v101, v16);
          v15 |= 2u;
        }
        goto LABEL_20;
      }
LABEL_19:
      v99[5] = a3;
      LOBYTE(v13) = 1;
      RefsAcquirePagingFastResourceExclusive(v12, a3, v101, v13);
      v15 = v10 & 0xFFFFFFF9 | 2;
LABEL_20:
      v10 = v15 | 1;
      goto LABEL_22;
    }
    RefsAcquireExclusiveScb(a1, a3, 0);
    v10 |= 8u;
LABEL_22:
    if ( (*((_DWORD *)a3 + 38) & 0x80u) != 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        valid = -1073740610;
      }
      else
      {
        valid = -1073740610;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids, 3221226686LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v19 = 3901;
        goto LABEL_30;
      }
      goto LABEL_31;
    }
    v20 = *((_DWORD *)a3 + 75);
    if ( (v20 & 0x40) != 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        valid = -1073741533;
      }
      else
      {
        valid = -1073741533;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids, 3221225763LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v19 = 3911;
        goto LABEL_30;
      }
      goto LABEL_31;
    }
    if ( (v20 & 0x4000) != 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        valid = -1073741202;
      }
      else
      {
        valid = -1073741202;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids, 3221226094LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v19 = 3916;
        goto LABEL_30;
      }
      goto LABEL_31;
    }
    v21 = *((_QWORD *)a3 + 17);
    if ( (*(_BYTE *)(v21 + 8) & 0x20) != 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        valid = -1073741431;
      }
      else
      {
        valid = -1073741431;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids, 3221225865LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v19 = 3926;
        goto LABEL_30;
      }
      goto LABEL_31;
    }
    if ( *((_DWORD *)a3 + 74) == 3 )
    {
      v22 = *((_WORD *)a3 + 108);
      if ( v22 == 128 || v22 == 176 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          valid = -1073740637;
        }
        else
        {
          valid = -1073740637;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids,
            3221226659LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v19 = 3936;
          goto LABEL_30;
        }
        goto LABEL_31;
      }
    }
    if ( !RefsIsFileOpen((const struct _FCB *)v21) )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        valid = -1073741528;
      }
      else
      {
        valid = -1073741528;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids, 3221225768LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v19 = 3941;
        goto LABEL_30;
      }
      goto LABEL_31;
    }
    if ( (*((_DWORD *)a3 + 38) & 0x20) == 0 )
      RefsUpdateScbFromAttribute(a1, a3, 0);
    v25 = *((_QWORD *)a3 + 4);
    v18 = *(PDEVICE_OBJECT *)v5;
    if ( *(_QWORD *)v5 >= v25 || (__int64)v18 >= v9 )
      goto LABEL_106;
    if ( v7 )
    {
      v26 = v9 - (_QWORD)v18;
      v75 = v9 - (_QWORD)v18;
      if ( v9 > v25 )
      {
        v26 = v25 - (_QWORD)v18;
        v75 = v25 - (_QWORD)v18;
      }
      if ( v26 > 0x40000000 )
        v26 = 0x40000000;
      v75 = v26;
      v27 = RefsCheckLocksInZeroRange(a1, *((PIRP *)a1 + 9), (__int64)v5, v26);
      valid = v27;
      v72 = v27;
      if ( v27 )
      {
        if ( v27 != 264 )
          goto LABEL_233;
      }
    }
    RefsPostUsnChange(a1, (struct _FCB *)a3, 1u, 0);
    if ( v7 )
      RefsUpdateFileTimestampsForModification(v7, *((struct _FCB **)a3 + 17), (struct _CCB *)v7->FsContext2, v29);
    v30 = *((_DWORD *)a3 + 38);
    if ( (v30 & 8) != 0 && (v30 & 0x40) == 0 )
    {
      v31 = *(_QWORD *)v5;
      v32 = v9 - *(_QWORD *)v5;
      v75 = v32;
      v33 = *((_QWORD *)a3 + 4);
      if ( v9 > v33 )
      {
        v32 = v33 - v31;
        v75 = v33 - v31;
      }
      if ( *(_QWORD *)(*((_QWORD *)a3 + 31) + 8LL) )
      {
        v34 = RefsCacheCoherencyFlush(a1, v28, a3, v31, v32, 1u, 0);
        valid = v34;
        v72 = v34;
        if ( v34 == -1073740747 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            valid = -1073741797;
          }
          else
          {
            valid = -1073741797;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              25,
              WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids,
              3221225499LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741797, 0, "AttrHelpers.c", 0xFCCu);
          v72 = -1073741797;
          v34 = -1073741797;
        }
        if ( v34 < 0 )
          goto LABEL_233;
      }
      if ( (v10 & 8) == 0 )
      {
        RefsAcquireExclusiveScb(a1, a3, 0);
        LOBYTE(v10) = v10 | 8;
      }
      RefsResidentWrite(a1, 0, a3, *v5, v32);
      RefsCheckpointCurrentTransaction(a1);
      *(_QWORD *)v5 += v32;
LABEL_105:
      v7 = a2;
LABEL_106:
      if ( !valid && v7 && ((v7->Flags & 8) != 0 || (v7->Flags & 0x10) != 0) )
      {
        if ( *((_DWORD *)a3 + 40) == *((_DWORD *)a3 + 39) )
        {
          if ( (v10 & 8) != 0 )
          {
            RefsReleaseFcb(a1, *((struct _FCB **)a3 + 17));
            LOBYTE(v10) = v10 & 0xF7;
          }
          RefsFlushAndPurgeScb(a1, a3);
        }
        else
        {
          v72 = RefsFlushUserStream(a1, a3, v23, v24, (unsigned __int8)IoStatus);
          RefsNormalizeAndCleanupTransaction(a1, &v72, v66, v67);
          valid = v72;
        }
        if ( (v10 & 8) == 0 )
        {
          RefsAcquireExclusiveScb(a1, a3, 0);
          LOBYTE(v10) = v10 | 8;
        }
        if ( (v7->Flags & 0x10) != 0 )
        {
          v73[0] = 0;
          RefsHasPendingRedo(a1, a3, v73);
          if ( v73[0] )
            *((_QWORD *)a1 + 1) |= 0x400uLL;
        }
        RefsFlushForWriteThrough(a1, a3, 0);
      }
      goto LABEL_233;
    }
    LODWORD(v75) = *((_WORD *)a3 + 128) >> 15;
    v10 = v10 & 0xFFFFFFEF | (16 * v75);
    v35 = *((_QWORD *)a3 + 18);
    v36 = *(int *)(v35 + 272);
    v79 = *(_DWORD *)(v35 + 272);
    if ( !(_DWORD)v75
      && *(_WORD *)a3 == 2053
      && *((_QWORD *)a3 + 54)
      && *((_WORD *)a3 + 130)
      && a1 == *((struct _IRP_CONTEXT **)a1 + 13) )
    {
      *((_QWORD *)a1 + 1) |= 8uLL;
      v35 = *((_QWORD *)a3 + 18);
    }
    v74 = v36 - 1;
    v37 = *(_QWORD *)v5 & ~(unsigned __int64)(unsigned int)(v36 - 1);
    v76.QuadPart = v37;
    v38 = a5;
    v86 = a5;
    v39 = *((_QWORD *)a3 + 4);
    if ( a5 >= v39 )
    {
      v38 = -v36 & (v36 + v39 - 1);
      v86 = v38;
    }
    v87 = v37 >> *(_BYTE *)(v35 + 552);
    v93 = v87;
    v40 = v87;
    v82 = v87;
    v85 = v87;
    v41 = 0;
    do
    {
      v42 = ((v38 + *(unsigned int *)(v35 + 544)) >> *(_BYTE *)(v35 + 552)) - v40;
      *(_QWORD *)&v97 = v40;
      *((_QWORD *)&v97 + 1) = v42;
      v100 = v97;
      IoStatus = (PIO_STATUS_BLOCK)&v95;
      if ( (unsigned __int8)RefsLookupAllocation(a1, a3, &v100, 4) || BYTE1(v91) )
        goto LABEL_128;
      if ( *((__int16 *)a3 + 128) >= 0 )
      {
        v69 = RefsQueueTriageForDeadFcb(a1, *((struct _FCB **)a3 + 17));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qd(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids,
            *((_QWORD *)a3 + 17),
            v69);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(v69, a1, "AttrHelpers.c", 0x1025u);
        RefsRaiseStatusInternal(a1, v69, v70);
LABEL_248:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            28,
            WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids,
            3221225626LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741670, a1, "AttrHelpers.c", 0x10B8u);
        RefsRaiseStatusInternal(a1, -1073741670, v52);
LABEL_255:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            30,
            WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids,
            3221225626LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741670, a1, "AttrHelpers.c", 0x110Du);
        RefsRaiseStatusInternal(a1, -1073741670, v55);
LABEL_262:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            (unsigned int)(v41 + 32),
            WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids,
            (unsigned int)valid);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(valid, a1, "AttrHelpers.c", 0x11EEu);
        RefsRaiseStatusInternal(a1, valid, v65);
        __debugbreak();
        JUMPOUT(0x140297339LL);
      }
      v40 += v96;
      v82 = v40;
      v85 = v40;
      v35 = *((_QWORD *)a3 + 18);
      v43 = *(_BYTE *)(v35 + 552);
    }
    while ( v40 < (v38 + *(unsigned int *)(v35 + 544)) >> v43 );
    v40 = v38 >> v43;
    v82 = v38 >> v43;
    v85 = v38 >> v43;
LABEL_128:
    RefsCheckpointCurrentTransaction(a1);
    v85 = v40;
    v44 = v87;
    if ( v40 != v87 )
    {
      v45 = v40 - v87;
      v88 = v45;
      if ( *(_QWORD *)(*((_QWORD *)a3 + 31) + 8LL) && (_DWORD)v75 )
      {
        RefsCheckForReservedClusters(a3, v87, &v88);
        v45 = v88;
      }
      v44 += v45;
      v87 = v44;
      v93 = v44;
    }
    v18 = (PDEVICE_OBJECT)*((_QWORD *)a3 + 18);
    LOBYTE(v18) = v18[1].Dpc.ProcessorHistory;
    v46 = v44 << (char)v18;
    v76.QuadPart = v44 << (char)v18;
    if ( v44 << (char)v18 >= v38 )
    {
      *a4 = v38;
      goto LABEL_105;
    }
    v41 = (int)a4;
    v47 = *a4;
    if ( v46 < *a4 )
      break;
    v54 = v79;
    if ( v46 + v79 <= v38 )
    {
      v57 = v38 - v46;
      v75 = v57;
      if ( v57 > 0x40000000 )
      {
        v75 = 0x40000000;
        v57 = 0x40000000;
      }
      v51 = v57 & -(__int64)(int)v79;
      v75 = v51;
      if ( v47 == v89 && v51 > v79 )
      {
        v51 = v79;
        v75 = v79;
        v86 = v46 + v79;
        v58 = v79;
      }
      else
      {
        v58 = v57 & -(__int64)(int)v79;
      }
      v59 = (SECTION_OBJECT_POINTERS *)(*((_QWORD *)a3 + 31) + 8LL);
      if ( v59->DataSectionObject )
      {
        if ( CcPurgeCacheSection(v59, &v76, v51, 0) )
        {
          CcFlushCache((PSECTION_OBJECT_POINTERS)(*((_QWORD *)a3 + 31) + 8LL), &v76, v51, 0);
        }
        else
        {
          valid = RefsCacheCoherencyFlush(a1, v60, a3, v76.QuadPart, v51, 1u, 0);
          v72 = valid;
          if ( valid == -1073740747 )
          {
            if ( v58 <= v54 )
            {
              v54 = v58;
            }
            else
            {
              v51 = v54;
              v75 = v54;
              v86 = v54 + v76.QuadPart;
            }
            v58 = 0;
            if ( CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*((_QWORD *)a3 + 31) + 8LL), &v76, v51, 0) )
            {
LABEL_215:
              if ( v54 )
              {
                if ( (v10 & 8) == 0 )
                {
                  if ( (v10 & 2) == 0 )
                  {
                    QuadPart = v76.QuadPart;
                    v83 = v51;
                    RefsAcquireRangeLock(
                      a1,
                      *((struct _SCB_NONPAGED **)a3 + 31),
                      v76.QuadPart,
                      v51,
                      1,
                      (struct _RANGE_LOCK_STATE *)&v92);
                    v10 |= 0x20u;
                  }
                  RefsCheckpointCurrentTransaction(a1);
                  RefsAcquireExclusiveScb(a1, a3, 0);
                  v10 |= 8u;
                }
                v61 = v54 >> *(_BYTE *)(*((_QWORD *)a3 + 18) + 552LL);
                v62 = v61 + v87 - 1;
                v88 = v62;
                if ( (v10 & 0x10) != 0 )
                {
                  if ( v82 <= v62 )
                  {
                    RefsDeleteAllocation(a1, a3, v82, v61 + v87 - 1, *((_WORD *)a3 + 128) >= 0);
                    RefsCheckpointCurrentTransaction(a1);
                  }
                  RefsFreeReservedClusters(a1, a3, v76.QuadPart, v51);
                }
                else
                {
                  v41 = 0;
                  v63 = v82;
                  v89 = v82;
                  v64 = v62 - v82 + 1;
                  v90 = v64;
                  RefsBindMinstoreTransaction(a1);
                  v99[0] = v63;
                  v99[1] = v64;
                  valid = MsSetRangeValidState(*((_QWORD *)a1 + 3), *((_QWORD *)a3 + 54), v99, 0);
                  v72 = valid;
                  if ( valid < 0 )
                    goto LABEL_262;
                }
              }
              goto LABEL_152;
            }
            if ( *a4 == v89 )
            {
              v18 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
              {
                valid = -1073741797;
              }
              else
              {
                valid = -1073741797;
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  31,
                  WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids,
                  3221225499LL);
              }
              if ( !(_BYTE)RefsStatusDebugEnabled )
                goto LABEL_31;
              v19 = 4463;
LABEL_30:
              RefsStatusDebug(valid, 0, "AttrHelpers.c", v19);
              goto LABEL_31;
            }
            v51 = 0;
            v75 = 0;
          }
        }
      }
      v54 = v58;
      goto LABEL_215;
    }
    v41 = 0;
    if ( (_WORD)v75 && !RefsReserveClusters(a1, a3, v76.QuadPart, v79) )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        valid = -1073741697;
      }
      else
      {
        valid = -1073741697;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids, 3221225599LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_31;
      v19 = 4314;
      goto LABEL_30;
    }
    v51 = v74 & (unsigned int)v38;
    v75 = v51;
    if ( !*((_QWORD *)a3 + 30) )
    {
      if ( (v10 & 1) != 0 && (v10 & 2) == 0 )
      {
LABEL_151:
        v10 |= 4u;
        v51 = 0;
        v75 = 0;
        v84 = ++v78;
        goto LABEL_152;
      }
      RefsCreateInternalAttributeStream(a1, a3, 0, &stru_140206F50);
    }
    if ( (v74 & (unsigned int)v38) != 0 )
    {
      MdlChain = 0;
      CcPrepareMdlWrite(*((PFILE_OBJECT *)a3 + 30), &v76, v51, &MdlChain, &v98);
      if ( (MdlChain->MdlFlags & 5) != 0 )
        MappedSystemVa = MdlChain->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlChain, 0, MmCached, 0, 0, 0x40000010u);
      if ( !MappedSystemVa )
        goto LABEL_255;
      memset(MappedSystemVa, 0, (unsigned int)v51);
      if ( MdlChain )
        CcMdlWriteComplete(*((PFILE_OBJECT *)a3 + 30), &v76, MdlChain);
    }
LABEL_152:
    RefsCheckpointCurrentTransaction(a1);
    RefsFlushForWriteThrough(a1, a3, 0);
    v5 = (unsigned int *)a4;
    v89 = *a4;
    if ( v51 )
    {
      v12 = v76.QuadPart + v51;
      *a4 = v76.QuadPart + v51;
    }
    if ( (v10 & 0x20) != 0 )
    {
      RefsReleaseRangeLock(*((struct _SCB_NONPAGED **)a3 + 31), QuadPart, v83, 1u, (struct _RANGE_LOCK_STATE *)&v92);
      v10 &= ~0x20u;
    }
    if ( (v10 & 1) != 0 )
    {
      v99[6] = a3;
      RefsReleasePagingFastResource(v12, a3, v101);
      v10 &= ~1u;
    }
    if ( (v10 & 8) != 0 )
    {
      RefsReleaseFcb(a1, *((struct _FCB **)a3 + 17));
      v10 &= ~8u;
    }
    v7 = a2;
    v9 = a5;
  }
  FileOffset.QuadPart = 0;
  v48 = v79;
  if ( !(_WORD)v75 || RefsReserveClusters(a1, a3, v76.QuadPart, v79) )
  {
    v49 = *a4;
    v50 = (unsigned int)v48;
    v51 = v76.QuadPart + v48 - *a4;
    v75 = v51;
    if ( v76.QuadPart + v50 > v38 )
    {
      v51 = v38 - v49;
      v75 = v38 - v49;
    }
    if ( !*((_QWORD *)a3 + 30) )
    {
      if ( (v10 & 1) != 0 && (v10 & 2) == 0 )
        goto LABEL_151;
      RefsCreateInternalAttributeStream(a1, a3, 0, &stru_140206F40);
    }
    if ( v51 )
    {
      FileOffset.QuadPart = v76.QuadPart + (*(_DWORD *)a4 & v74);
      MdlChain = 0;
      CcPrepareMdlWrite(*((PFILE_OBJECT *)a3 + 30), &FileOffset, v51, &MdlChain, &v98);
      if ( (MdlChain->MdlFlags & 5) != 0 )
        v53 = MdlChain->MappedSystemVa;
      else
        v53 = MmMapLockedPagesSpecifyCache(MdlChain, 0, MmCached, 0, 0, 0x40000010u);
      if ( !v53 )
        goto LABEL_248;
      memset(v53, 0, (unsigned int)v51);
      if ( MdlChain )
        CcMdlWriteComplete(*((PFILE_OBJECT *)a3 + 30), &FileOffset, MdlChain);
      v76.QuadPart += v74 & *(_DWORD *)a4;
    }
    goto LABEL_152;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    valid = -1073741697;
  }
  else
  {
    valid = -1073741697;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids, 3221225599LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v19 = 4222;
    goto LABEL_30;
  }
LABEL_31:
  v72 = valid;
LABEL_233:
  if ( (v10 & 0x20) != 0 )
    RefsReleaseRangeLock(*((struct _SCB_NONPAGED **)a3 + 31), QuadPart, v83, 1u, (struct _RANGE_LOCK_STATE *)&v92);
  if ( (v10 & 1) != 0 )
  {
    v94 = a3;
    RefsReleasePagingFastResource(v18, a3, v101);
  }
  MsCleanupFastResourceOwnerEntry(v101);
  if ( valid != 259 && (v10 & 8) != 0 )
    RefsReleaseFcb(a1, *((struct _FCB **)a3 + 17));
  return (unsigned int)valid;
}

```

## disassembly

```asm
0x140295fb0  mov     rax, rsp
0x140295fb3  mov     [rax+20h], r9
0x140295fb7  mov     [rax+18h], r8
0x140295fbb  mov     [rax+10h], rdx
0x140295fbf  mov     [rax+8], rcx
0x140295fc3  push    rbx
0x140295fc4  push    rsi
0x140295fc5  push    rdi
0x140295fc6  push    r12
0x140295fc8  push    r13
0x140295fca  push    r14
0x140295fcc  push    r15
0x140295fce  sub     rsp, 1D0h
0x140295fd5  mov     r12, r9
0x140295fd8  mov     rsi, r8
0x140295fdb  mov     r15, rdx
0x140295fde  mov     r14, rcx
0x140295fe1  mov     r13, [rsp+208h+arg_20]
0x140295fe9  xor     ebx, ebx
0x140295feb  mov     edi, ebx
0x140295fed  mov     [rsp+208h+var_1C4], ebx
0x140295ff1  mov     qword ptr [rax-150h], 0FFFFFFFFFFFFFFFFh
0x140295ffc  mov     qword ptr [rsp+208h+var_1B0], rbx
0x140296001  mov     [rsp+208h+var_198], rbx
0x140296006  mov     [rax-180h], rbx
0x14029600d  xorps   xmm0, xmm0
0x140296010  movups  xmmword ptr [rax-138h], xmm0
0x140296017  xor     edx, edx; Val
0x140296019  lea     r8d, [rbx+58h]; Size
0x14029601d  lea     rcx, [rax-98h]; void *
0x140296024  call    memset
0x140296029  mov     eax, ebx
0x14029602b  mov     [rsp+208h+var_1A0], ebx
0x14029602f  mov     [rsp+208h+var_118], rbx
0x140296037  mov     [rsp+208h+var_110], rbx
0x14029603f  mov     [rsp+208h+var_140], rbx
0x140296047  mov     [rsp+208h+MdlChain], rbx
0x14029604c  xorps   xmm0, xmm0
0x14029604f  movups  xmmword ptr [rsp+208h+var_F8], xmm0
0x140296057  mov     [rsp+208h+var_1C8], ebx
0x14029605b  lea     rcx, [rsp+208h+var_98]
0x140296063  call    MsInitializeFastResourceOwnerEntry
0x140296068  nop
0x140296069  mov     edx, 40000000h
0x14029606e  cmp     qword ptr [rsi+10h], 0
0x140296073  jz      loc_1402961AD
0x140296079  cmp     qword ptr [r14+38h], 0
0x14029607e  jnz     loc_1402961C2
0x140296084  test    bl, 4
0x140296087  jnz     loc_14029617F
0x14029608d  mov     rax, [rsi+0F8h]
0x140296094  cmp     qword ptr [rax+8], 0
0x140296099  jnz     loc_14029617F
0x14029609f  mov     ecx, [rsi+98h]
0x1402960a5  mov     eax, ecx
0x1402960a7  and     eax, 8
0x1402960aa  jz      short loc_1402960B7
0x1402960ac  mov     eax, ecx
0x1402960ae  and     eax, 40h
0x1402960b1  jz      loc_14029617F
0x1402960b7  mov     eax, ecx
0x1402960b9  and     eax, 10h
0x1402960bc  jz      short loc_1402960DE
0x1402960be  mov     rax, [rsi+88h]
0x1402960c5  mov     rcx, [rax+8]
0x1402960c9  and     ecx, 40000100h
0x1402960cf  cmp     rcx, rdx
0x1402960d2  jz      loc_14029617F
0x1402960d8  mov     ecx, [rsi+98h]
0x1402960de  test    cl, 20h
0x1402960e1  jz      loc_14029617F
0x1402960e7  mov     [rsp+208h+var_D8], rsi
0x1402960ef  mov     r9b, 1
0x1402960f2  lea     r8, [rsp+208h+var_98]
0x1402960fa  mov     rdx, rsi
0x1402960fd  call    ?RefsAcquirePagingFastResourceShared@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@E@Z; RefsAcquirePagingFastResourceShared(_IRP_CONTEXT *,PFCBOrSCB,_MS_FAST_RESOURCE_OWNER_ENTRY *,uchar)
0x140296102  and     ebx, 0FFFFFFFDh
0x140296105  mov     [rsp+208h+var_1C8], ebx
0x140296109  mov     rax, [rsi+0F8h]
0x140296110  cmp     qword ptr [rax+8], 0
0x140296115  jnz     short loc_140296147
0x140296117  mov     ecx, [rsi+98h]
0x14029611d  mov     eax, ecx
0x14029611f  and     eax, 8
0x140296122  jz      short loc_14029612B
0x140296124  mov     eax, ecx
0x140296126  and     eax, 40h
0x140296129  jz      short loc_140296147
0x14029612b  mov     eax, ecx
0x14029612d  and     eax, 20h
0x140296130  jz      short loc_140296147
0x140296132  and     ecx, 10h
0x140296135  jz      short loc_1402961A8
0x140296137  mov     rcx, [rsi+88h]; this
0x14029613e  call    ?HasPurgeableEAs@_FCB@@QEAA_NXZ; _FCB::HasPurgeableEAs(void)
0x140296143  test    al, al
0x140296145  jz      short loc_1402961A8
0x140296147  mov     [rsp+208h+var_D0], rsi
0x14029614f  lea     r8, [rsp+208h+var_98]
0x140296157  mov     rdx, rsi
0x14029615a  call    ?RefsReleasePagingFastResource@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@@Z; RefsReleasePagingFastResource(_IRP_CONTEXT *,PFCBOrSCB,_MS_FAST_RESOURCE_OWNER_ENTRY *)
0x14029615f  mov     [rsp+208h+var_C8], rsi
0x140296167  mov     r9b, 1
0x14029616a  lea     r8, [rsp+208h+var_98]
0x140296172  mov     rdx, rsi
0x140296175  call    ?RefsAcquirePagingFastResourceExclusive@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@E@Z; RefsAcquirePagingFastResourceExclusive(_IRP_CONTEXT *,PFCBOrSCB,_MS_FAST_RESOURCE_OWNER_ENTRY *,uchar)
0x14029617a  or      ebx, 2
0x14029617d  jmp     short loc_1402961A4
0x14029617f  mov     [rsp+208h+var_C0], rsi
0x140296187  mov     r9b, 1
0x14029618a  lea     r8, [rsp+208h+var_98]
0x140296192  mov     rdx, rsi
0x140296195  call    ?RefsAcquirePagingFastResourceExclusive@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@E@Z; RefsAcquirePagingFastResourceExclusive(_IRP_CONTEXT *,PFCBOrSCB,_MS_FAST_RESOURCE_OWNER_ENTRY *,uchar)
0x14029619a  or      ebx, 2
0x14029619d  mov     [rsp+208h+var_1C8], ebx
0x1402961a1  and     ebx, 0FFFFFFFBh
0x1402961a4  mov     [rsp+208h+var_1C8], ebx
0x1402961a8  or      ebx, 1
0x1402961ab  jmp     short loc_1402961BE
0x1402961ad  xor     r8d, r8d
0x1402961b0  mov     rdx, rsi
0x1402961b3  mov     rcx, r14
0x1402961b6  call    ?RefsAcquireExclusiveScb@@YAEPEAU_IRP_CONTEXT@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveScb(_IRP_CONTEXT *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x1402961bb  or      ebx, 8
0x1402961be  mov     [rsp+208h+var_1C8], ebx
0x1402961c2  mov     eax, [rsi+98h]
0x1402961c8  mov     edx, 80h
0x1402961cd  test    dl, al
0x1402961cf  jz      short loc_140296240
0x1402961d1  lea     rax, WPP_GLOBAL_Control
0x1402961d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1402961df  cmp     rcx, rax
0x1402961e2  jz      short loc_140296212
0x1402961e4  mov     eax, [rcx+2Ch]
0x1402961e7  bt      eax, 8
0x1402961eb  jnb     short loc_140296212
0x1402961ed  cmp     byte ptr [rcx+29h], 4
0x1402961f1  jb      short loc_140296212
0x1402961f3  mov     edx, 13h
0x1402961f8  mov     edi, 0C00004BEh
0x1402961fd  mov     r9d, edi
0x140296200  lea     r8, WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids
0x140296207  mov     rcx, [rcx+18h]
0x14029620b  call    WPP_SF_d
0x140296210  jmp     short loc_140296217
0x140296212  mov     edi, 0C00004BEh
0x140296217  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14029621d  test    al, al
0x14029621f  jz      short loc_140296237
0x140296221  mov     r9d, 0F3Dh; unsigned int
0x140296227  lea     r8, aAttrhelpersC; "AttrHelpers.c"
0x14029622e  xor     edx, edx; struct _IRP_CONTEXT *
0x140296230  mov     ecx, edi; Status
0x140296232  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140296237  mov     [rsp+208h+var_1C4], edi
0x14029623b  jmp     loc_1402970EB
0x140296240  mov     eax, [rsi+12Ch]
0x140296246  test    al, 40h
0x140296248  jz      short loc_1402962A2
0x14029624a  lea     rax, WPP_GLOBAL_Control
0x140296251  mov     rcx, cs:WPP_GLOBAL_Control
0x140296258  cmp     rcx, rax
0x14029625b  jz      short loc_14029628B
0x14029625d  mov     eax, [rcx+2Ch]
0x140296260  bt      eax, 8
0x140296264  jnb     short loc_14029628B
0x140296266  cmp     byte ptr [rcx+29h], 4
0x14029626a  jb      short loc_14029628B
0x14029626c  mov     edx, 14h
0x140296271  mov     edi, 0C0000123h
0x140296276  mov     r9d, edi
0x140296279  lea     r8, WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids
0x140296280  mov     rcx, [rcx+18h]
0x140296284  call    WPP_SF_d
0x140296289  jmp     short loc_140296290
0x14029628b  mov     edi, 0C0000123h
0x140296290  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140296296  test    al, al
0x140296298  jz      short loc_140296237
0x14029629a  mov     r9d, 0F47h
0x1402962a0  jmp     short loc_140296227
0x1402962a2  bt      eax, 0Eh
0x1402962a6  jnb     short loc_140296307
0x1402962a8  lea     rax, WPP_GLOBAL_Control
0x1402962af  mov     rcx, cs:WPP_GLOBAL_Control
0x1402962b6  cmp     rcx, rax
0x1402962b9  jz      short loc_1402962E9
0x1402962bb  mov     eax, [rcx+2Ch]
0x1402962be  bt      eax, 8
0x1402962c2  jnb     short loc_1402962E9
0x1402962c4  cmp     byte ptr [rcx+29h], 4
0x1402962c8  jb      short loc_1402962E9
0x1402962ca  mov     edx, 15h
0x1402962cf  mov     edi, 0C000026Eh
0x1402962d4  mov     r9d, edi
0x1402962d7  lea     r8, WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids
0x1402962de  mov     rcx, [rcx+18h]
0x1402962e2  call    WPP_SF_d
0x1402962e7  jmp     short loc_1402962EE
0x1402962e9  mov     edi, 0C000026Eh
0x1402962ee  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402962f4  test    al, al
0x1402962f6  jz      loc_140296237
0x1402962fc  mov     r9d, 0F4Ch
0x140296302  jmp     loc_140296227
0x140296307  mov     rcx, [rsi+88h]; struct _FCB *
0x14029630e  test    byte ptr [rcx+8], 20h
0x140296312  jz      short loc_140296373
0x140296314  lea     rax, WPP_GLOBAL_Control
0x14029631b  mov     rcx, cs:WPP_GLOBAL_Control
0x140296322  cmp     rcx, rax
0x140296325  jz      short loc_140296355
0x140296327  mov     eax, [rcx+2Ch]
0x14029632a  bt      eax, 8
0x14029632e  jnb     short loc_140296355
0x140296330  cmp     byte ptr [rcx+29h], 4
0x140296334  jb      short loc_140296355
0x140296336  mov     edx, 16h
0x14029633b  mov     edi, 0C0000189h
0x140296340  mov     r9d, edi
0x140296343  lea     r8, WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids
0x14029634a  mov     rcx, [rcx+18h]
0x14029634e  call    WPP_SF_d
0x140296353  jmp     short loc_14029635A
0x140296355  mov     edi, 0C0000189h
0x14029635a  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140296360  test    al, al
0x140296362  jz      loc_140296237
0x140296368  mov     r9d, 0F56h
0x14029636e  jmp     loc_140296227
0x140296373  cmp     dword ptr [rsi+128h], 3
0x14029637a  jnz     short loc_1402963F1
0x14029637c  movzx   eax, word ptr [rsi+0D8h]
0x140296383  cmp     ax, dx
0x140296386  jz      short loc_140296392
0x140296388  mov     edx, 0B0h
0x14029638d  cmp     ax, dx
0x140296390  jnz     short loc_1402963F1
0x140296392  lea     rax, WPP_GLOBAL_Control
0x140296399  mov     rcx, cs:WPP_GLOBAL_Control
0x1402963a0  cmp     rcx, rax
0x1402963a3  jz      short loc_1402963D3
0x1402963a5  mov     eax, [rcx+2Ch]
0x1402963a8  bt      eax, 8
0x1402963ac  jnb     short loc_1402963D3
0x1402963ae  cmp     byte ptr [rcx+29h], 4
0x1402963b2  jb      short loc_1402963D3
0x1402963b4  mov     edx, 17h
0x1402963b9  mov     edi, 0C00004A3h
0x1402963be  mov     r9d, edi
0x1402963c1  lea     r8, WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids
0x1402963c8  mov     rcx, [rcx+18h]
0x1402963cc  call    WPP_SF_d
0x1402963d1  jmp     short loc_1402963D8
0x1402963d3  mov     edi, 0C00004A3h
0x1402963d8  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402963de  test    al, al
0x1402963e0  jz      loc_140296237
0x1402963e6  mov     r9d, 0F60h
0x1402963ec  jmp     loc_140296227
0x1402963f1  call    ?RefsIsFileOpen@@YAEPEBU_FCB@@@Z; RefsIsFileOpen(_FCB const *)
0x1402963f6  test    al, al
0x1402963f8  jnz     short loc_140296459
0x1402963fa  lea     rax, WPP_GLOBAL_Control
0x140296401  mov     rcx, cs:WPP_GLOBAL_Control
0x140296408  cmp     rcx, rax
0x14029640b  jz      short loc_14029643B
0x14029640d  mov     eax, [rcx+2Ch]
0x140296410  bt      eax, 8
0x140296414  jnb     short loc_14029643B
0x140296416  cmp     byte ptr [rcx+29h], 4
0x14029641a  jb      short loc_14029643B
0x14029641c  mov     edx, 18h
0x140296421  mov     edi, 0C0000128h
0x140296426  mov     r9d, edi
0x140296429  lea     r8, WPP_34c05d45765f3b87687bb7e942b40e58_Traceguids
0x140296430  mov     rcx, [rcx+18h]
0x140296434  call    WPP_SF_d
0x140296439  jmp     short loc_140296440
0x14029643b  mov     edi, 0C0000128h
0x140296440  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140296446  test    al, al
0x140296448  jz      loc_140296237
0x14029644e  mov     r9d, 0F65h
0x140296454  jmp     loc_140296227
0x140296459  mov     eax, [rsi+98h]
0x14029645f  test    al, 20h
0x140296461  jnz     short loc_140296471
0x140296463  xor     r8d, r8d; this
0x140296466  mov     rdx, rsi; struct _SCB *
0x140296469  mov     rcx, r14; struct _IRP_CONTEXT *
0x14029646c  call    ?RefsUpdateScbFromAttribute@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@PEAVRefsAttributeManager@@@Z; RefsUpdateScbFromAttribute(_IRP_CONTEXT *,_SCB *,RefsAttributeManager *)
0x140296471  mov     rdx, [rsi+20h]
0x140296475  mov     rcx, [r12]
0x140296479  cmp     rcx, rdx
0x14029647c  jge     loc_14029664C
0x140296482  cmp     rcx, r13
0x140296485  jge     loc_14029664C
0x14029648b  test    r15, r15
0x14029648e  jz      short loc_1402964EF
  ... truncated ...
```
