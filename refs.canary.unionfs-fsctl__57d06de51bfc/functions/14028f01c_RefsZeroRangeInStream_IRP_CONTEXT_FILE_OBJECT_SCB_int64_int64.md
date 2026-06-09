# RefsZeroRangeInStream(_IRP_CONTEXT *,_FILE_OBJECT *,_SCB *,__int64 *,__int64)

- ea: `0x14028f01c`
- end: `0x1402903a5`
- name: `?RefsZeroRangeInStream@@YAJPEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAU_SCB@@PEA_J_J@Z`
- size: `5001`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct _FILE_OBJECT *, struct _SCB *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `38`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1402c30cc`

## callees

- `0x140008c10`
- `0x14000bcc0`
- `0x14000cd70`
- `0x140024db8`
- `0x14003d1d8`
- `0x140043510`
- `0x140080834`
- `0x140080b90`
- `0x140080c00`
- `0x140081670`
- `0x14008dbd0`
- `0x14008e360`
- `0x14008e3c0`
- `0x140090040`
- `0x140097140`
- `0x14009ca80`
- `0x14009ccb0`
- `0x1400ac4c8`
- `0x1400b87a0`
- `0x1400c8024`
- `0x1400ca788`
- `0x1400e0d98`
- `0x1400e1048`
- `0x1400e1498`
- `0x14010d8f8`
- `0x1401ea140`
- `0x14028db38`
- `0x14028e150`
- `0x14028f01c`
- `0x1402903ac`
- `0x1402fec90`
- `0x1402fff70`
- `0x1403000b0`
- `0x1403021e0`
- `0x140325110`
- `0x140330428`
- `0x1403321d8`
- `0x1403390c4`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x14028ff73`
- `ntoskrnl!CcFlushCache` at `0x14028ff73`
- `ntoskrnl!CcMdlWriteComplete` at `0x14028fc1d`
- `ntoskrnl!CcMdlWriteComplete` at `0x14028fdce`
- `ntoskrnl!CcMdlWriteComplete` at `0x140342941`
- `ntoskrnl!CcMdlWriteComplete` at `0x140342979`
- `ntoskrnl!CcMdlWriteComplete` at `0x14028fc1d`
- `ntoskrnl!CcMdlWriteComplete` at `0x14028fdce`
- `ntoskrnl!CcMdlWriteComplete` at `0x140342941`
- `ntoskrnl!CcMdlWriteComplete` at `0x140342979`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14028fbe4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14028fd91`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14028fbe4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14028fd91`
- `ntoskrnl!CcPrepareMdlWrite` at `0x14028fbae`
- `ntoskrnl!CcPrepareMdlWrite` at `0x14028fd5e`
- `ntoskrnl!CcPrepareMdlWrite` at `0x14028fbae`
- `ntoskrnl!CcPrepareMdlWrite` at `0x14028fd5e`
- `ntoskrnl!CcPurgeCacheSection` at `0x14028fe4b`
- `ntoskrnl!CcPurgeCacheSection` at `0x14028fec8`
- `ntoskrnl!CcPurgeCacheSection` at `0x14028fe4b`
- `ntoskrnl!CcPurgeCacheSection` at `0x14028fec8`

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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_dd88044251a339022b0218b488422d69_Traceguids, 3221226686LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v19 = 3942;
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_dd88044251a339022b0218b488422d69_Traceguids, 3221225763LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v19 = 3952;
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_dd88044251a339022b0218b488422d69_Traceguids, 3221226094LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v19 = 3957;
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_dd88044251a339022b0218b488422d69_Traceguids, 3221225865LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v19 = 3967;
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
            24,
            WPP_dd88044251a339022b0218b488422d69_Traceguids,
            3221226659LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v19 = 3977;
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_dd88044251a339022b0218b488422d69_Traceguids, 3221225768LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v19 = 3982;
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
              26,
              WPP_dd88044251a339022b0218b488422d69_Traceguids,
              3221225499LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741797, 0, "AttrHelpers.c", 0xFF5u);
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
            27,
            WPP_dd88044251a339022b0218b488422d69_Traceguids,
            *((_QWORD *)a3 + 17),
            v69);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(v69, a1, "AttrHelpers.c", 0x104Eu);
        RefsRaiseStatusInternal(a1, v69, v70);
LABEL_248:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            29,
            WPP_dd88044251a339022b0218b488422d69_Traceguids,
            3221225626LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741670, a1, "AttrHelpers.c", 0x10E1u);
        RefsRaiseStatusInternal(a1, -1073741670, v52);
LABEL_255:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            31,
            WPP_dd88044251a339022b0218b488422d69_Traceguids,
            3221225626LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741670, a1, "AttrHelpers.c", 0x1136u);
        RefsRaiseStatusInternal(a1, -1073741670, v55);
LABEL_262:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            (unsigned int)(v41 + 33),
            WPP_dd88044251a339022b0218b488422d69_Traceguids,
            (unsigned int)valid);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(valid, a1, "AttrHelpers.c", 0x1217u);
        RefsRaiseStatusInternal(a1, valid, v65);
        __debugbreak();
        JUMPOUT(0x1402903A5LL);
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
                  32,
                  WPP_dd88044251a339022b0218b488422d69_Traceguids,
                  3221225499LL);
              }
              if ( !(_BYTE)RefsStatusDebugEnabled )
                goto LABEL_31;
              v19 = 4504;
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_dd88044251a339022b0218b488422d69_Traceguids, 3221225599LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_31;
      v19 = 4355;
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
      RefsCreateInternalAttributeStream(a1, a3, 0, &stru_1401FFF50);
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
      RefsCreateInternalAttributeStream(a1, a3, 0, &stru_1401FFF40);
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_dd88044251a339022b0218b488422d69_Traceguids, 3221225599LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v19 = 4263;
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
0x14028f01c  mov     rax, rsp
0x14028f01f  mov     [rax+20h], r9
0x14028f023  mov     [rax+18h], r8
0x14028f027  mov     [rax+10h], rdx
0x14028f02b  mov     [rax+8], rcx
0x14028f02f  push    rbx
0x14028f030  push    rsi
0x14028f031  push    rdi
0x14028f032  push    r12
0x14028f034  push    r13
0x14028f036  push    r14
0x14028f038  push    r15
0x14028f03a  sub     rsp, 1D0h
0x14028f041  mov     r12, r9
0x14028f044  mov     rsi, r8
0x14028f047  mov     r15, rdx
0x14028f04a  mov     r14, rcx
0x14028f04d  mov     r13, [rsp+208h+arg_20]
0x14028f055  xor     ebx, ebx
0x14028f057  mov     edi, ebx
0x14028f059  mov     [rsp+208h+var_1C4], ebx
0x14028f05d  mov     qword ptr [rax-150h], 0FFFFFFFFFFFFFFFFh
0x14028f068  mov     qword ptr [rsp+208h+var_1B0], rbx
0x14028f06d  mov     [rsp+208h+var_198], rbx
0x14028f072  mov     [rax-180h], rbx
0x14028f079  xorps   xmm0, xmm0
0x14028f07c  movups  xmmword ptr [rax-138h], xmm0
0x14028f083  xor     edx, edx; Val
0x14028f085  lea     r8d, [rbx+58h]; Size
0x14028f089  lea     rcx, [rax-98h]; void *
0x14028f090  call    memset
0x14028f095  mov     eax, ebx
0x14028f097  mov     [rsp+208h+var_1A0], ebx
0x14028f09b  mov     [rsp+208h+var_118], rbx
0x14028f0a3  mov     [rsp+208h+var_110], rbx
0x14028f0ab  mov     [rsp+208h+var_140], rbx
0x14028f0b3  mov     [rsp+208h+MdlChain], rbx
0x14028f0b8  xorps   xmm0, xmm0
0x14028f0bb  movups  xmmword ptr [rsp+208h+var_F8], xmm0
0x14028f0c3  mov     [rsp+208h+var_1C8], ebx
0x14028f0c7  lea     rcx, [rsp+208h+var_98]
0x14028f0cf  call    MsInitializeFastResourceOwnerEntry
0x14028f0d4  nop
0x14028f0d5  mov     edx, 40000000h
0x14028f0da  cmp     qword ptr [rsi+10h], 0
0x14028f0df  jz      loc_14028F219
0x14028f0e5  cmp     qword ptr [r14+38h], 0
0x14028f0ea  jnz     loc_14028F22E
0x14028f0f0  test    bl, 4
0x14028f0f3  jnz     loc_14028F1EB
0x14028f0f9  mov     rax, [rsi+0F8h]
0x14028f100  cmp     qword ptr [rax+8], 0
0x14028f105  jnz     loc_14028F1EB
0x14028f10b  mov     ecx, [rsi+98h]
0x14028f111  mov     eax, ecx
0x14028f113  and     eax, 8
0x14028f116  jz      short loc_14028F123
0x14028f118  mov     eax, ecx
0x14028f11a  and     eax, 40h
0x14028f11d  jz      loc_14028F1EB
0x14028f123  mov     eax, ecx
0x14028f125  and     eax, 10h
0x14028f128  jz      short loc_14028F14A
0x14028f12a  mov     rax, [rsi+88h]
0x14028f131  mov     rcx, [rax+8]
0x14028f135  and     ecx, 40000100h
0x14028f13b  cmp     rcx, rdx
0x14028f13e  jz      loc_14028F1EB
0x14028f144  mov     ecx, [rsi+98h]
0x14028f14a  test    cl, 20h
0x14028f14d  jz      loc_14028F1EB
0x14028f153  mov     [rsp+208h+var_D8], rsi
0x14028f15b  mov     r9b, 1
0x14028f15e  lea     r8, [rsp+208h+var_98]
0x14028f166  mov     rdx, rsi
0x14028f169  call    ?RefsAcquirePagingFastResourceShared@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@E@Z; RefsAcquirePagingFastResourceShared(_IRP_CONTEXT *,PFCBOrSCB,_MS_FAST_RESOURCE_OWNER_ENTRY *,uchar)
0x14028f16e  and     ebx, 0FFFFFFFDh
0x14028f171  mov     [rsp+208h+var_1C8], ebx
0x14028f175  mov     rax, [rsi+0F8h]
0x14028f17c  cmp     qword ptr [rax+8], 0
0x14028f181  jnz     short loc_14028F1B3
0x14028f183  mov     ecx, [rsi+98h]
0x14028f189  mov     eax, ecx
0x14028f18b  and     eax, 8
0x14028f18e  jz      short loc_14028F197
0x14028f190  mov     eax, ecx
0x14028f192  and     eax, 40h
0x14028f195  jz      short loc_14028F1B3
0x14028f197  mov     eax, ecx
0x14028f199  and     eax, 20h
0x14028f19c  jz      short loc_14028F1B3
0x14028f19e  and     ecx, 10h
0x14028f1a1  jz      short loc_14028F214
0x14028f1a3  mov     rcx, [rsi+88h]; this
0x14028f1aa  call    ?HasPurgeableEAs@_FCB@@QEAA_NXZ; _FCB::HasPurgeableEAs(void)
0x14028f1af  test    al, al
0x14028f1b1  jz      short loc_14028F214
0x14028f1b3  mov     [rsp+208h+var_D0], rsi
0x14028f1bb  lea     r8, [rsp+208h+var_98]
0x14028f1c3  mov     rdx, rsi
0x14028f1c6  call    ?RefsReleasePagingFastResource@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@@Z; RefsReleasePagingFastResource(_IRP_CONTEXT *,PFCBOrSCB,_MS_FAST_RESOURCE_OWNER_ENTRY *)
0x14028f1cb  mov     [rsp+208h+var_C8], rsi
0x14028f1d3  mov     r9b, 1
0x14028f1d6  lea     r8, [rsp+208h+var_98]
0x14028f1de  mov     rdx, rsi
0x14028f1e1  call    ?RefsAcquirePagingFastResourceExclusive@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@E@Z; RefsAcquirePagingFastResourceExclusive(_IRP_CONTEXT *,PFCBOrSCB,_MS_FAST_RESOURCE_OWNER_ENTRY *,uchar)
0x14028f1e6  or      ebx, 2
0x14028f1e9  jmp     short loc_14028F210
0x14028f1eb  mov     [rsp+208h+var_C0], rsi
0x14028f1f3  mov     r9b, 1
0x14028f1f6  lea     r8, [rsp+208h+var_98]
0x14028f1fe  mov     rdx, rsi
0x14028f201  call    ?RefsAcquirePagingFastResourceExclusive@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@E@Z; RefsAcquirePagingFastResourceExclusive(_IRP_CONTEXT *,PFCBOrSCB,_MS_FAST_RESOURCE_OWNER_ENTRY *,uchar)
0x14028f206  or      ebx, 2
0x14028f209  mov     [rsp+208h+var_1C8], ebx
0x14028f20d  and     ebx, 0FFFFFFFBh
0x14028f210  mov     [rsp+208h+var_1C8], ebx
0x14028f214  or      ebx, 1
0x14028f217  jmp     short loc_14028F22A
0x14028f219  xor     r8d, r8d
0x14028f21c  mov     rdx, rsi
0x14028f21f  mov     rcx, r14
0x14028f222  call    ?RefsAcquireExclusiveScb@@YAEPEAU_IRP_CONTEXT@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveScb(_IRP_CONTEXT *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x14028f227  or      ebx, 8
0x14028f22a  mov     [rsp+208h+var_1C8], ebx
0x14028f22e  mov     eax, [rsi+98h]
0x14028f234  mov     edx, 80h
0x14028f239  test    dl, al
0x14028f23b  jz      short loc_14028F2AC
0x14028f23d  lea     rax, WPP_GLOBAL_Control
0x14028f244  mov     rcx, cs:WPP_GLOBAL_Control
0x14028f24b  cmp     rcx, rax
0x14028f24e  jz      short loc_14028F27E
0x14028f250  mov     eax, [rcx+2Ch]
0x14028f253  bt      eax, 8
0x14028f257  jnb     short loc_14028F27E
0x14028f259  cmp     byte ptr [rcx+29h], 4
0x14028f25d  jb      short loc_14028F27E
0x14028f25f  mov     edx, 14h
0x14028f264  mov     edi, 0C00004BEh
0x14028f269  mov     r9d, edi
0x14028f26c  lea     r8, WPP_dd88044251a339022b0218b488422d69_Traceguids
0x14028f273  mov     rcx, [rcx+18h]
0x14028f277  call    WPP_SF_d
0x14028f27c  jmp     short loc_14028F283
0x14028f27e  mov     edi, 0C00004BEh
0x14028f283  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14028f289  test    al, al
0x14028f28b  jz      short loc_14028F2A3
0x14028f28d  mov     r9d, 0F66h; unsigned int
0x14028f293  lea     r8, aAttrhelpersC; "AttrHelpers.c"
0x14028f29a  xor     edx, edx; struct _IRP_CONTEXT *
0x14028f29c  mov     ecx, edi; Status
0x14028f29e  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14028f2a3  mov     [rsp+208h+var_1C4], edi
0x14028f2a7  jmp     loc_140290157
0x14028f2ac  mov     eax, [rsi+12Ch]
0x14028f2b2  test    al, 40h
0x14028f2b4  jz      short loc_14028F30E
0x14028f2b6  lea     rax, WPP_GLOBAL_Control
0x14028f2bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14028f2c4  cmp     rcx, rax
0x14028f2c7  jz      short loc_14028F2F7
0x14028f2c9  mov     eax, [rcx+2Ch]
0x14028f2cc  bt      eax, 8
0x14028f2d0  jnb     short loc_14028F2F7
0x14028f2d2  cmp     byte ptr [rcx+29h], 4
0x14028f2d6  jb      short loc_14028F2F7
0x14028f2d8  mov     edx, 15h
0x14028f2dd  mov     edi, 0C0000123h
0x14028f2e2  mov     r9d, edi
0x14028f2e5  lea     r8, WPP_dd88044251a339022b0218b488422d69_Traceguids
0x14028f2ec  mov     rcx, [rcx+18h]
0x14028f2f0  call    WPP_SF_d
0x14028f2f5  jmp     short loc_14028F2FC
0x14028f2f7  mov     edi, 0C0000123h
0x14028f2fc  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14028f302  test    al, al
0x14028f304  jz      short loc_14028F2A3
0x14028f306  mov     r9d, 0F70h
0x14028f30c  jmp     short loc_14028F293
0x14028f30e  bt      eax, 0Eh
0x14028f312  jnb     short loc_14028F373
0x14028f314  lea     rax, WPP_GLOBAL_Control
0x14028f31b  mov     rcx, cs:WPP_GLOBAL_Control
0x14028f322  cmp     rcx, rax
0x14028f325  jz      short loc_14028F355
0x14028f327  mov     eax, [rcx+2Ch]
0x14028f32a  bt      eax, 8
0x14028f32e  jnb     short loc_14028F355
0x14028f330  cmp     byte ptr [rcx+29h], 4
0x14028f334  jb      short loc_14028F355
0x14028f336  mov     edx, 16h
0x14028f33b  mov     edi, 0C000026Eh
0x14028f340  mov     r9d, edi
0x14028f343  lea     r8, WPP_dd88044251a339022b0218b488422d69_Traceguids
0x14028f34a  mov     rcx, [rcx+18h]
0x14028f34e  call    WPP_SF_d
0x14028f353  jmp     short loc_14028F35A
0x14028f355  mov     edi, 0C000026Eh
0x14028f35a  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14028f360  test    al, al
0x14028f362  jz      loc_14028F2A3
0x14028f368  mov     r9d, 0F75h
0x14028f36e  jmp     loc_14028F293
0x14028f373  mov     rcx, [rsi+88h]; struct _FCB *
0x14028f37a  test    byte ptr [rcx+8], 20h
0x14028f37e  jz      short loc_14028F3DF
0x14028f380  lea     rax, WPP_GLOBAL_Control
0x14028f387  mov     rcx, cs:WPP_GLOBAL_Control
0x14028f38e  cmp     rcx, rax
0x14028f391  jz      short loc_14028F3C1
0x14028f393  mov     eax, [rcx+2Ch]
0x14028f396  bt      eax, 8
0x14028f39a  jnb     short loc_14028F3C1
0x14028f39c  cmp     byte ptr [rcx+29h], 4
0x14028f3a0  jb      short loc_14028F3C1
0x14028f3a2  mov     edx, 17h
0x14028f3a7  mov     edi, 0C0000189h
0x14028f3ac  mov     r9d, edi
0x14028f3af  lea     r8, WPP_dd88044251a339022b0218b488422d69_Traceguids
0x14028f3b6  mov     rcx, [rcx+18h]
0x14028f3ba  call    WPP_SF_d
0x14028f3bf  jmp     short loc_14028F3C6
0x14028f3c1  mov     edi, 0C0000189h
0x14028f3c6  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14028f3cc  test    al, al
0x14028f3ce  jz      loc_14028F2A3
0x14028f3d4  mov     r9d, 0F7Fh
0x14028f3da  jmp     loc_14028F293
0x14028f3df  cmp     dword ptr [rsi+128h], 3
0x14028f3e6  jnz     short loc_14028F45D
0x14028f3e8  movzx   eax, word ptr [rsi+0D8h]
0x14028f3ef  cmp     ax, dx
0x14028f3f2  jz      short loc_14028F3FE
0x14028f3f4  mov     edx, 0B0h
0x14028f3f9  cmp     ax, dx
0x14028f3fc  jnz     short loc_14028F45D
0x14028f3fe  lea     rax, WPP_GLOBAL_Control
0x14028f405  mov     rcx, cs:WPP_GLOBAL_Control
0x14028f40c  cmp     rcx, rax
0x14028f40f  jz      short loc_14028F43F
0x14028f411  mov     eax, [rcx+2Ch]
0x14028f414  bt      eax, 8
0x14028f418  jnb     short loc_14028F43F
0x14028f41a  cmp     byte ptr [rcx+29h], 4
0x14028f41e  jb      short loc_14028F43F
0x14028f420  mov     edx, 18h
0x14028f425  mov     edi, 0C00004A3h
0x14028f42a  mov     r9d, edi
0x14028f42d  lea     r8, WPP_dd88044251a339022b0218b488422d69_Traceguids
0x14028f434  mov     rcx, [rcx+18h]
0x14028f438  call    WPP_SF_d
0x14028f43d  jmp     short loc_14028F444
0x14028f43f  mov     edi, 0C00004A3h
0x14028f444  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14028f44a  test    al, al
0x14028f44c  jz      loc_14028F2A3
0x14028f452  mov     r9d, 0F89h
0x14028f458  jmp     loc_14028F293
0x14028f45d  call    ?RefsIsFileOpen@@YAEPEBU_FCB@@@Z; RefsIsFileOpen(_FCB const *)
0x14028f462  test    al, al
0x14028f464  jnz     short loc_14028F4C5
0x14028f466  lea     rax, WPP_GLOBAL_Control
0x14028f46d  mov     rcx, cs:WPP_GLOBAL_Control
0x14028f474  cmp     rcx, rax
0x14028f477  jz      short loc_14028F4A7
0x14028f479  mov     eax, [rcx+2Ch]
0x14028f47c  bt      eax, 8
0x14028f480  jnb     short loc_14028F4A7
0x14028f482  cmp     byte ptr [rcx+29h], 4
0x14028f486  jb      short loc_14028F4A7
0x14028f488  mov     edx, 19h
0x14028f48d  mov     edi, 0C0000128h
0x14028f492  mov     r9d, edi
0x14028f495  lea     r8, WPP_dd88044251a339022b0218b488422d69_Traceguids
0x14028f49c  mov     rcx, [rcx+18h]
0x14028f4a0  call    WPP_SF_d
0x14028f4a5  jmp     short loc_14028F4AC
0x14028f4a7  mov     edi, 0C0000128h
0x14028f4ac  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14028f4b2  test    al, al
0x14028f4b4  jz      loc_14028F2A3
0x14028f4ba  mov     r9d, 0F8Eh
0x14028f4c0  jmp     loc_14028F293
0x14028f4c5  mov     eax, [rsi+98h]
0x14028f4cb  test    al, 20h
0x14028f4cd  jnz     short loc_14028F4DD
0x14028f4cf  xor     r8d, r8d; this
0x14028f4d2  mov     rdx, rsi; struct _SCB *
0x14028f4d5  mov     rcx, r14; struct _IRP_CONTEXT *
0x14028f4d8  call    ?RefsUpdateScbFromAttribute@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@PEAVRefsAttributeManager@@@Z; RefsUpdateScbFromAttribute(_IRP_CONTEXT *,_SCB *,RefsAttributeManager *)
0x14028f4dd  mov     rdx, [rsi+20h]
0x14028f4e1  mov     rcx, [r12]
0x14028f4e5  cmp     rcx, rdx
0x14028f4e8  jge     loc_14028F6B8
0x14028f4ee  cmp     rcx, r13
0x14028f4f1  jge     loc_14028F6B8
0x14028f4f7  test    r15, r15
0x14028f4fa  jz      short loc_14028F55B
  ... truncated ...
```
